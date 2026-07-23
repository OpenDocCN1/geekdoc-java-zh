![](images/00041.jpeg)

Java 8

Foundational java up to Java8 for beginners.

Feyisayo Dosunmu.

Acknowledgment

My acknowledgment goes in particular to my darling wife Omolabake, for her staunch support, also to all the beautiful people who have been of great assistance in the creation of this book, and in general to the readers for their continuous loyalty through the years. This book is my appreciation of that unflinching support.

I say thank you all.

Copyright © August 2015 Feyisayo Dosunmu.

All rights reserved.

Written permission must be secured from the publisher to use or reproduce any part of this book, except for brief quotation in critical review or articles.

Storage or recording of this material is prohibited unless with a written permission from the publisher. While all attempts have been made to verify information provided in this publication, neither the author, the publisher nor the editor assumes any responsibility for any errors, omissions, or contrary interpretation of subject matter herein.

The information provided herein is stated to be truthful and consistent and any liability in terms of inattention or misuse is the solitary responsibility of the recipient reader.

The purchaser or reader of this publication assumes responsibility for the use of these materials and information, including adherence to all applicable laws and regulations, federal, state and local, governing professional licensing, business practices, advertising and all other aspects of doing business in any jurisdiction in the world. No guarantees of income are made. Under no circumstances will legal responsibility or blame be held against the publisher, editor or the author for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly. The Author, editor and publisher accept no responsibility or liability whatsoever on the behalf of any reader or purchaser of these materials.

Thank you.

Dedication

This book is dedicated first to God almighty, the giver of all things, who gave the inspiration for it with the promise to lift the heavy stone for me, if I continued to push. And secondly, to everyone out there, who believes that knowledge is light and that with knowledge, darkness is past and the true light shines through.

Table of Content

[Acknowledgment](#part0000_split_001.html__Toc428274189)

[Dedication](#part0000_split_003.html__Toc428274190)

[Table of Content](#part0000_split_004.html__Toc428274191)

[Introduction](#part0000_split_005.html__Toc428274192)

[Chapter 1](#part0000_split_006.html__Toc428274193)

[Introduction to Java Programming](#part0000_split_006.html__Toc428274194)

[1.2 Java Flavors (applications, applets and servlets)](#part0000_split_007.html__Toc428274195)

[1.3 The Java API (application programming interface) and the JDK](#part0000_split_008.html__Toc428274196)

[1.4 Downloading and Installing Java Tools](#part0000_split_009.html__Toc428274197)

[Chapter 2](#part0000_split_010.html__Toc428274198)

[Java Data types and Operators](#part0000_split_010.html__Toc428274199)

[2.1 Primitive Data types](#part0000_split_011.html__Toc428274200)

[2.2 Wrapper Classes for the Primitive Data types](#part0000_split_012.html__Toc428274201)

[2.2b Converting to String with Wrapper Classes](#part0000_split_013.html__Toc428274202)

[2.2c Converting from String with Wrapper Classes](#part0000_split_014.html__Toc428274203)

[2.3 The String Data Type](#part0000_split_015.html__Toc428274204)

[2.4 Variable Declaration](#part0000_split_016.html__Toc428274205)

[2.5 The Final Declaration Modifier](#part0000_split_017.html__Toc428274206)

[2.6 Identifiers Naming Convention](#part0000_split_018.html__Toc428274207)

[2.7 Java Operators and Expressions](#part0000_split_019.html__Toc428274208)

[2.8 The Lambda Indirection Operator (->)](#part0000_split_020.html__Toc428274209)

[Chapter 3](#part0000_split_021.html__Toc428274210)

[Java Classes, Objects and Access Modifiers](#part0000_split_021.html__Toc428274211)

[3.1 Class Definition](#part0000_split_022.html__Toc428274212)

[3.2 Access Modifiers](#part0000_split_023.html__Toc428274213)

[3.3 Class Objects](#part0000_split_024.html__Toc428274214)

[3.4 Compilation and Running of Applications with the JDK](#part0000_split_025.html__Toc428274215)

[3.5 Running a Java Class file (Byte codes)](#part0000_split_026.html__Toc428274216)

[3.6 Returning Class Parameter Names at Runtime](#part0000_split_027.html__Toc428274217)

[Chapter 4](#part0000_split_028.html__Toc428274218)

[Object Oriented Programming and Default Interface Methods](#part0000_split_028.html__Toc428274219)

[4.1 Class Inheritance](#part0000_split_029.html__Toc428274220)

[4.2 Variable and Method Overriding](#part0000_split_030.html__Toc428274221)

[4.3 The Constructor Function](#part0000_split_031.html__Toc428274222)

[4.4 The super and this keywords Application](#part0000_split_032.html__Toc428274223)

[4.5 Function Overloading](#part0000_split_033.html__Toc428274224)

[4.6 Abstract Classes](#part0000_split_034.html__Toc428274225)

[4.7 Interfaces](#part0000_split_035.html__Toc428274226)

[4.8 Interface Implementation](#part0000_split_036.html__Toc428274227)

[4.9 Lambda Expressions and Functional Interfaces](#part0000_split_037.html__Toc428274228)

[Chapter 5](#part0000_split_038.html__Toc428274229)

[Program Control Loops and ForEach Loop](#part0000_split_038.html__Toc428274230)

[5.1 The For Loop Statement](#part0000_split_039.html__Toc428274231)

[5.2 The Nested For Loop Statement](#part0000_split_040.html__Toc428274232)

[5.3 The Enhanced For Loop](#part0000_split_041.html__Toc428274233)

[5.4 The Lambda foreach Loop](#part0000_split_042.html__Toc428274234)

[5.5 The While Loop statement](#part0000_split_043.html__Toc428274235)

[5.6 The Do statement](#part0000_split_044.html__Toc428274236)

[5.7 The Stream “filter” Method](#part0000_split_045.html__Toc428274237)

[Chapter 6](#part0000_split_046.html__Toc428274238)

[Program Decision Statements](#part0000_split_046.html__Toc428274239)

[6.1 The if statement](#part0000_split_047.html__Toc428274240)

[6.2 The if else Statement](#part0000_split_048.html__Toc428274241)

[6.3 The Ternary Operator](#part0000_split_049.html__Toc428274242)

[6.4 The else if statement](#part0000_split_050.html__Toc428274243)

[6.5 The Switch Statement](#part0000_split_051.html__Toc428274244)

[Chapter 7](#part0000_split_052.html__Toc428274245)

[Array and ArrayList and Parallel Sorting](#part0000_split_052.html__Toc428274246)

[7.1 Array Declaration](#part0000_split_053.html__Toc428274247)

[7.2 Array Assignment](#part0000_split_054.html__Toc428274248)

[7.3 Multi-dimensional Arrays](#part0000_split_055.html__Toc428274249)

[7.4 The Enhanced For Loop](#part0000_split_056.html__Toc428274250)

[7.5 ArraySorting](#part0000_split_057.html__Toc428274251)

[7.5b Parallel Array Sorting](#part0000_split_058.html__Toc428274252)

[7.6 Array Copying](#part0000_split_059.html__Toc428274253)

[7.7 An ArrayList](#part0000_split_060.html__Toc428274254)

[7.8a ArrayList Assignment and Iteration with Enhanced for loop](#part0000_split_061.html__Toc428274255)

[7.8b ArrayList Iteration with Lambda](#part0000_split_062.html__Toc428274256)

[7.9 Deleting Array list’s  Object Elements](#part0000_split_063.html__Toc428274257)

[7.10 The Iterator Interface:](#part0000_split_064.html__Toc428274258)

[Chapter 8](#part0000_split_065.html__Toc428274259)

[Strings and Regular Expressions](#part0000_split_065.html__Toc428274260)

[8.1 String Class Methods](#part0000_split_066.html__Toc428274261)

[8.2 Regular Expressions](#part0000_split_067.html__Toc428274262)

[8.3 Regular Expression Formulation](#part0000_split_068.html__Toc428274263)

[8.4 Regular Expressions Application](#part0000_split_069.html__Toc428274264)

[Chapter 9](#part0000_split_070.html__Toc428274265)

[Exception Handling](#part0000_split_070.html__Toc428274266)

[9.1 The “try..catch”  Statement Model](#part0000_split_071.html__Toc428274267)

[9.2 Benefits of Exception Handling](#part0000_split_072.html__Toc428274268)

[9.3 Catching Two or More Exceptions in a Catch Statement](#part0000_split_073.html__Toc428274269)

[9.4 Exception Hierarchy](#part0000_split_074.html__Toc428274270)

[Chapter 10](#part0000_split_075.html__Toc428274271)

[XML Processing](#part0000_split_075.html__Toc428274272)

[10.1 Creating XML with Java](#part0000_split_076.html__Toc428274273)

[10.2 Reading XML with Java](#part0000_split_077.html__Toc428274274)

[Chapter 11](#part0000_split_078.html__Toc428274275)

[Java Applets](#part0000_split_078.html__Toc428274276)

[11.1 The Applet Element](#part0000_split_079.html__Toc428274277)

[11.2 An Applet’s Structure](#part0000_split_080.html__Toc428274278)

[11.3 An Example Applet](#part0000_split_081.html__Toc428274279)

[Conclusion](#part0000_split_082.html__Toc428274280)

# Introduction

This is a special java book. It aims to allay the fear associated with Java programming that is usually experienced by new java programmers, by explaining in simple terms object oriented programming concepts, by building solid foundations for a deep and easy understanding of design patterns theory in software design and development with the ultimate goal of passing on a lasting java legacy, by working with the core Java APIs, avoiding as much as possible the version insanity syndrome, discussing only the necessary additions that are relevant to the developer, showing how the additions became necessary and their applications.

The more things change the more they remain the same. Though in Java things hardly change, but new additions are always around the corner (version insanity). The latest addition was made necessary due to the development of multiple cores computers, the dual cores and even the quad cores which made it important to improve core APIs resulting in smarter java codes with lambda expressions, so they can run on multiple processors, saving time and having improved efficiency. This led to the emergence of the new Java 8 introduced in this book. This said, this book would remain evergreen and a treasure that can always be used as a reference guide.

At this juncture, I like to be the first to congratulate you for finding this book, as I am very happy to share my love of programming and most especially java programming with you as a certified software developer and a Microsoft Certified Technology Specialist. Stay with me and don’t lose your mobile device yet, as this is the beginning of something very special.

Thank you.

# Chapter 1

# Introduction to Java Programming

Back in the early 1990’s James Gosling working with the Sun Microsystems was mandated to develop a better and more portable programming language better than C++ in terms of memory management and system portability for the development of embedded systems.

James improved on the short comings of C++ in the areas of memory management by making garbage collection (the returning of memory slots no longer in use to the system) and making platform independency a possibility for embedded systems through the introduction of the virtual machine with the new programming language he developed called Oak.

Oak was soon discovered to be the perfect tool for web application development in 1994 and was renamed HotJava and eventually in the following year (1995), HotJava was renamed Java. In 1996 the first Java compiler was released, and since then it has been Java, Java everywhere, on the web and around the world.

Lots of thanks to James Gosling and the Sun Microsystems who have continued to support Java till this day. You are free to visit the sun’s website for the latest version of Java development tools at [http://java.sun.com](http://java.sun.com).

## 1.2 Java Flavors (applications, applets and servlets)

Java is available in three flavors; applications, applets and servlets. These are enumerated below:

### 1.2.1 Java Applications

Java applications are embedded java programs in consumer electronic devices like the cameras, microwaves, television sets, and java programs that are executed through the computer command prompt to mention but a few. You can develop a java application by writing a java class in a text editor like note pad and saving it with the name of the class with an extension .java in any directory of your choice in your computer system. Provided you have downloaded and install the jdk (java development kit) on your computer. More on this later.

### 1.2.2 Java Applets

Java applets are java programs embedded within the applet tags in web documents (hypertext markup documents) like the [HTML5](http://www.amazon.co.uk/dp/B00PIMD5P2) and [XML](http://www.amazon.co.uk/dp/B00XRRB2TG). These java programs are launched from the web documents they are embedded in and therefore preferred to java applications in situations where graphical user interface is a priority. They lack the static main method, the “init()” method is called to launch the applet. Applets inherit from the “Panel” class, more on inheritance later in the book.

### 1.2.3 Java Servlets

Java servlets are web based versions of java programs. Great sites are developed with java servlets. Java servlets are built by extending the java servlet class.

## 1.3 The Java API (application programming interface) and the JDK

The java application programming interface is a group of readymade utilities called class libraries that can be used to carry out some common operations like the mathematics and string manipulation operations which are available in the API package “java.lang”. To find out more about java API visit the link http://docs.oracle.com/javase/8/docs/api/index.html

## 1.4 Downloading and Installing Java Tools

In this book we shall be dealing with java applications at the beginning and smoothly advancing through the foundational concepts and java 8 additions to the java applet, to ultimately conclude on the development and application of java servlets in another series due to length limitation. For this reason there is a need to describe how to download the Java Development Kit (JDK) and the Java Netbeans with an integrated development environment for the development of java applications, applets and servlets.

### 1.4.1 Downloading Java Development Kit and Installation

The java development kit can be downloaded by visiting the link: [http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) . Download the latest version of the jdk. To get the complete java development tool download the jdk to your computer and run the executable file to install it on your machine.

After the installation, you need to set the path to the command line tools to enable the operating system find them when you call for them. You do this by taking the following steps:

Step 1:

Right click the computer icon on your desktop if available and if not then left click the start menu and right click “computer”.

Step 2:

In the pop up menu that comes up, left click the property menu.

Step 3:

Left click the “advance system settings” in the pane of the pop up system page.

Step 4:

Click on the “Environment variable” button in the pop up system properties window.

Step 5:

In the pop up “Environment Variables” dialog box, scroll down the “system variable” list and select “path” under the “Variable” column.

Step 6:

Click the edit button in the “Edit system variable” dialog box that pops up and move your cursor to the end of the content to type in your jdk bin folder’s path by first typing in a semicolon to separate your to be added path from the last path in the list like shown below:

%\system32\windowsPowerShell\V1.0\;c\program files\java\jdk1.8.0_51\bin

Step 7:

Click the ok button of the “Edit System Variable” dialogue box.

Step 8:

Click the ok button of the “Environment Variable” dialogue box.

Step 9:

Click the ok button of the “System Property” pop up box to conclusively set the path.

Step 10:

You can confirm that the path has been successfully set by running the set path command at the prompt like described below:

C:\> set path

The output from running this command at the prompt should be as described in figure 1.1 below:

![](images/00001.jpeg)

Figure 1.1\. The output of running the set path command at the command prompt.

You should see your jdk path in the path listing. If not please close the cmd window and reopen it again.

### 1.4.2 Downloading and Installing Java Netbeans IDE Development tool

To download the Netbeans IDE visit the link [http://www.netbeans.org/downloads/index.html](http://www.netbeans.org/downloads/index.html) and download the latest edition. After the download is complete install it on your computer. Working with the java DB is a lot easier with the Netbeans integrated development environment, more on this later. You are now very ready for the exercises in this book, you can now take a little break and let’s start the journey together when ready.

# 
Chapter 2

# Java Data types and Operators

Java as an object oriented programming language comes with its own data types and operators that help with expression creation, access modifiers for classes and class member variables and methods. Since the building blocks of java programs are the classes which are the definition for the objects of interest. The classes cannot do without the primitive data types, which also have their own wrapper classes. We therefore begin this chapter with the description of the primitive data types.

## 2.1 Primitive Data types

The primitive data types are the java built in data types that the compiler recognizes without any reference to any package in the core application programming interface (API). They are classified into three subsets; the numeric, character and Boolean. The following table 2.1 lists the primitive data types with their descriptions.

| Primitive Data types | Size | Description |
| int | 32 bits | An integer constant which is a sequence of one or more digits. It can be positive or negative if preceded by a minus sign. It’s in the range -2147483648 to 2147483647 |
| short | 16 bits | A short integer which takes up half the storage size of an integer constant. It is represented in the range -32768 to 32767 |
| long | 64 bits | A long integer constant with an extended precision which takes up a double storage size of an integer |
| byte | 8 bits | A tiny integer constant with restricted precision in the range -128 to 127 |
| float | 32 bits | Values with decimal points .e.g. 8.0, 1.23 |
| double | 64 bits | A floating type that can store twice as much value as the float type |
| boolean |  | A variable type that holds a ‘true’ or ‘false’ value |
| char | 16 bits | A variable type that holds a single character |

Table 2.1 The Numeric Primitive Data types.

## 2.2 Wrapper Classes for the Primitive Data types

It is worthy of mentioning that the above described primitive data types also have classes defined for them in the java.lang package stored in the core API. We call these classes the wrapper classes. The objective is to make the primitive class behave like objects and align with the founding concept of java programming. Table 2.2 below lists the primitive data types and their corresponding wrapper classes.

| Numeric Primitive Data types | Corresponding Wrapper Class |
| int | Integer |
| byte | Byte |
| short | Short |
| long | Long |
| float | Float |
| double | Double |
| boolean | Boolean |
| char | Character |

Table 2.2 Wrapper classes for the numeric primitive data types.

## 2.2b Converting to String with Wrapper Classes

Data types can be converted to String type with the “toString( )” method of wrapper classes, the syntax of usage is as described below:

String s = wrapper_class.toString(variable_name);

For example, to convert a double variable type “price” of value 0.32 to a String type use the following statement:

String s= Double.toString(price);

## 2.2c Converting from String with Wrapper Classes

You can also convert back from String type to the primitive data types by using the various parse methods of the wrapper classes. For example, to convert the String s type back to its original Double type you can use the following statement:

double price = Double.parseByte(s);

The parseByte(String) methods is also applicable to the following wrapper classes; Float and Byte. Others include parseInt(String), parseLong(String), parseShort(String), and parseBoolean, for Interger, Long, Short and Boolean wrapper classes accordingly.

## 2.3 The String Data Type

The string data type is not a primitive data type. It is an object of the class “java.lang.String” in the java core API (Application Programming Interface). A string literal is a combination of characters to any length which is enclosed in double quotes. For example, “Feyisayo Dosunmu” is a string and you can assign a reference to a string as described below:

String name = “Feyisayo Dosunmu”;

In java programming a statement is terminated with a semi colon (;). The reference to the storage location of the string “Feyisayo Dosunmu” is stored in the variable “name” with the execution of the above statement. The variable name is declared to the java compiler as a string object.

## 2.4 Variable Declaration

The variable declaration operation is the process of declaring a variable type to the compiler in order for the compiler to create the required memory space for the variable content. Variable declaration syntax specifies the data type, the variable name and optionally the default data value as described below:

Data_type Variable_name = Default_value;

Or

Data_type Variable_name;

For example to declare a string variable “surname” with a default value “Dosunmu” the following java statement is appropriate:

String surname = “Dosunmu”;

A variable must be declared in java programming before its usage and can be located in any part of the program.

## 2.5 The Final Declaration Modifier

A declaration modified with the key word “final” turns the variable into a constant with an unchangeable default value. The syntax of usage is as described below:

final string lastMonth = “December”;

The value of the sting constant “lastMonth” remains constant and unchangeable from this point on.  The final keyword can also be applied to class member variables with the same consequence by preceding the final keyword with the “static” keyword as described below:

static final string lastMonth = “December”;

If the string variable lastMonth was a class member variable, then from the declaration point on, variable lastMonth becomes a class variable independent of any object of the class and with a constant value. More on classes later in the book. At this point there is a need to discuss variable, class and method naming rules. It is not an absolutely must to follow these rules but it is a good thing to do as it is the mark that differentiates the professional java programmer from the amateurs. The application of these conventional rules also aids program readability.

## 2.6 Identifiers Naming Convention

In this section we shall be discussing about the rules and conventions guiding variable, class and function name formation in java programming. As earlier said, your programs will still run without them but it is always a good practice to abide by the convention and rules of the game. These guiding rules are as described in table 2.3 below:

| Identifier | Naming convention | Sample |
| Variable name | Leave only the first word of a variable name un-capitalized | firstName |
| Function name | Leave only the first word of a function name un-capitalized | getName( ) |
| Constant variable | Every letter of a constant variable name should be capitalized with each word separated with an underscore | LAST_MONTH |
| Class | Every first letter of a class name is capitalized. A class name is preferably a noun. Please avoid API class names | ScrewDriver |

Table 2.3\. Identifier naming convention.

## 2.7 Java Operators and Expressions

Operators are the building blocks of java expressions and expressions are always terminated with semi colons. The operator types are the unary, binary, assignment, relational and the logical operators. We shall be starting out with the assignment operator.

### 2.7.1 The Assignment Operator (=)

The assignment operator is a very common operator in all programming languages. It is use for assigning a value to a variable in java programming. The syntax of usage is as described below:

Variable_name = some_value;

For example, to assign the numerical value 7 to the variable “monthJuly” in java programming, the following program statement is applicable:

monthJuly = 7;

It must however be noted that there are two types of assignment operations in java programming, we have the value assignment and the reference assignment. The value assignment was earlier explained. The reference assignment occurs when an address of a memory location is assigned to the variable instead of the real value. This occurs anytime an object or a string is assigned to a variable name, as described below:

myName = “Feyisayo Dosunmu”;

### 2.7.2 The Unary Operators

The unary operator acts on single operands. They are the decrement, increment, and negation operator. The symbol for the increment operator is the double addition (++) and the syntax of usage is as described below:

++variable_name;

The symbol for the decrement operator is the double minus symbol (--) and the syntax of usage is also as described below:

--variable_name;

The symbol for the negation operator which inverts the sign of a value in a variable depending on its initial sign is a minus sign (-). The multiplication rule is as shown below:

a) - * - = +

b) - * + = -

c) + * - = -

d) + * + =+

According to the sign multiplication rule above, the application of a negation operator on a negative value would yield a positive value and the application of a negation operator on a positive value would yield a negative value. The following program listing 2.1 demonstrates the use of the unary and assignment operators.

Program listing 2.1:

public class UnaryOperators {

  public static void main(String[] args){

  int monthJuly, monthValue, followingMonth, prevMonth;

  monthJuly = 7;

  monthValue = monthJuly;

  followingMonth = (++monthValue);

  monthValue = monthJuly;

  prevMonth = (--monthValue);

    System.out.println("\n" );

    System.out.println("The Month of June is the " + prevMonth + "th month of the year. \n" );

    System.out.println("The Month of July is the " + monthJuly + "th month of the year. \n" );

    System.out.println("The Month of August is the " + followingMonth + "th month of the year. \n" );

  }

}

To run the above program listing 2.1, download the java development toolkit as earlier advised and set the operating system path to it by following the steps listed in section 1.4.1 of this book. You can type the codes in a text editor and store it in any directory of your choice in your computer using the name as the class name but with a .java extension (UnaryOperators.java). Next compile the code into java byte codes by changing to the command prompt (you do this in windows by selecting the start menu, All Programs, Accessories, run, and typing “cmd” in the open text field and clicking the ok button). In the command window change directory to the program source code directory with the change directory command (cd\program_folder_path) and type the following java command at the command prompt:

Program_folder> javac UnaryOperators.java

If the program is successfully compiled, you will receive no error messages, and if there is any error message please review the entered codes, correct the typos and try it again. When done with the compilation, you can then run the byte codes by typing the following java command at the prompt:

Program_folder> Java UnaryOperators

This is as illustrated in figure 2.1 below, which contains the output of program listing 2.1 above:

![](images/00002.jpeg)

Figure 2.1\. The Output of program listing 2.1\.

The application started by declaring variables monthJuly, monthValue, followingMonth, and prevMonth as integers. It then copied the value of monthJuly to monthValue since the effect of the increment and decrement operator is real, with this we can always re-initialize the value of month value with monthJuly’s value.

### 2.7.3 Binary Arithmetic Operators

Binary operators process two operands at the same time. They are the addition, subtraction, multiplication, division and the modulus operator as enumerated below:

The Arithmetic Addition Binary Operator (+)

The addition binary operator is represented with the plus sign. It adds the contents of numeric values or numeric variables. The syntax of usage in java programming is as described below:

result = value1 + value2;

The Arithmetic Multiplication Binary Operator (*)

The multiplication binary operator is represented by the asterisk symbol in most programing languages including java. It multiplies two numeric values or numeric variable contents together. The syntax of usage is as described below:

result = value1 * value2;

The Arithmetic Subtraction Binary Operator (-)

The arithmetic subtraction operator subtracts operates on two operands. It returns the result of subtracting the numeric value or content of the right operand from the numeric value or content of the left operand. The syntax of usage is as described below:

result = value1 – value2;

The Arithmetic Division Binary Operator (/)

The arithmetic division binary operator also acts on two operands and it is represented by the forward slash in most programming languages. It returns the result of dividing the numerator or the left side operand with the denominator or the right side operand. The syntax of usage is as described below:

result = value1 / value2;

The Arithmetic Modulus Binary Operator (%)

The arithmetic modulus binary operator acts on two numeric operands and is represented by the percentage symbol in most programming languages including java. It returns the remainder of the normal division operation. The usage syntax is as described below:

result = value1 % value2;

Program listing 2.2 below illustrates the application of the various binary arithmetic operators earlier discussed.

Program listing 2.2

public class BinaryOperators

{

  public static void main(String[] args){

  float result, leftOperand, rightOperand;

  leftOperand = 68;

  rightOperand = 10;

    System.out.println("\n" );

    result = leftOperand + rightOperand;

    System.out.println( leftOperand + " + " + rightOperand + " = " + result);

    result = leftOperand - rightOperand;

    System.out.println( leftOperand + " - " + rightOperand + " = " + result);

    result = leftOperand * rightOperand;

    System.out.println( leftOperand + " * " + rightOperand + " = " + result);

    result = leftOperand / rightOperand;

    System.out.println( leftOperand + " / " + rightOperand + " = " + result);

    result = leftOperand % rightOperand;

    System.out.println( leftOperand + " % " + rightOperand + " = " + result);

  }

}

The output from program listing 2.2 above is presented in figure 2.2 below:

![](images/00003.jpeg)

Figure 2.2\. The output from program listing 2.2.

### 2.7.4 The Relational Operators

Relational operators are more or less like the binary operators in the sense that they also act on two operands at the same time, except that they are used to test for the existence of certain conditions in affected operands. The available relational operators and their interpretations are listed in table 2.4 below:

| Relational Operator | Interpretation | Usage syntax |
| == | Equal to | a == b |
| != | Not equal to | a != b |
| < | Less than | a < b |
| > | Greater than | a > b |
| <= | Less than or equal to | a <= b |
| >= | Greater than or equal to | a >= b |

Table 2.4 Relational operators and their interpretations.

Relational operators are often used to create test expressions for conditional statements like the “if” and the “while” statements that shall be discussing later. Relational operators have lower precedence to the arithmetic operators. For example,

sum < value1 * value2

Shall be evaluated by the compiler as

sum < (value1 * value2)

## 2.8 The Lambda Indirection Operator (->)

The newly introduced lambda indirection operator that looks much like the good old days C/C++ programming pointer operator performs a pretty similar operation with the assignment operator (=). For example, the following expression;

y -> y * y

Takes the content of variable y at the left side, multiplies it with itself as directed at the right side of the indirection operator and returns the result. More on this in chapter four of this book where the concept of interface was discussed under the title “object oriented programming”. 

# Chapter 3

# Java Classes, Objects and Access Modifiers

Java as an object oriented programming language has its basic building block as the objects. This is the reason why a solid understanding of java classes and objects is paramount to the understanding and mastering of java programming.

An object is an instance of a class, where a class is the definition of a place, a thing, or a concept. In object oriented programming parlance, a class is usually a noun.

## 3.1 Class Definition

A class definition is made up of member variables and member methods with optional access modifiers. It may also include the constructor functions for class initialization purposes. The general syntax of a class definition is as described below:

[access modifier] class class_name {

            [access modifier] data-type member_variable-1;

            [access modifier] data-type member_variable-2;

            [access modifier] class_name( ){  //class constructor

              //class constructor body

            }

            [access modifier] class_method-1( ){  //class method

              //class method body

            }

  }

The usage of access modifiers with the class member variables and method is optional except with the main method which must have the public access modifier to enable the machine have access to it at execution time. However, any member function or variable with no access modifier shall be automatically assigned a default access modifier. There are seven major access modifiers in java, though we have more than seven modifiers which you shall be made aware of with time. Next, we discuss and describe the usage of these major access modifiers.

## 3.2 Access Modifiers

The seven major access modifiers are the followings; public, private, protected, private protected, abstract, static and final.  They are applied to classes, class member variables and methods. For example, to define a class for an object book, the class definition may be written as shown below:

   class Book{

    private String bookTitle, bookAuthors;

    private int noOfPages;

    public Book(String booktitle, String bookAuthors, int pages ){

      bookTitle= booktitle;

      bookAuthors= bookAuthors;

      noOfPages= pages;

    }

}

Here the Book class has no access modifier, and for this reason it is assigned a default modifier by the compiler, and the default modifier lacks a keyword. This means that the class is accessible only to other classes in its package or same directory. The class has a public constructor function with arguments bookTitles, bookAuthors and pages for initializing the private member variables with private access modifiers upon a book object declaration.

A class may have more than one constructor functions as long as they have different signatures this concept is what is termed polymorphism in object oriented programming, and for this reason another public class constructor with no arguments list can also be written for the class as shown below:

    public Book( ){

      bookTitle="No title yet";

      bookAuthors= "No author yet";

      noOfPages= 0;

    }

Public members of a default class are accessible to other classes in the same package, for this reason the constructors were provided with public access modifiers to allow access to all other classes within the same package. The function of the constructor is to help initialize the class member variables upon declaration. It is not compulsory that you provide a constructor for your class, if you do not, the compiler would provide a default one, but it’s a good practice to write one yourself in order to have the control in your own hands, because if you do not, in an instance where your class member variable is not of the primitive type the compiler would make the variable null instead of initializing it.

The private member variables “bookTitle”, “bookAuthors”, “noOfPages” with the private access modifiers are not accessible by any other classes except the declaring class itself (Book). Therefore there is a need to provide public accessor methods “getBookTitle()” and “getBookAuthors()” to help retrieve this information. These methods may be written as described below:

    public String getBookTitle( ){

      return bookTitle;

     }

    public String getBookAuthors( ){

      return bookAuthors;

     }

The above java codes defined public class member methods that return string objects to the calling methods.  This is of course an overview of the need and functions of the access modifiers. The following sub sections enumerate further on access modifiers.

### 3.2.1 Public Access Modifier

A class with a public access modifier (a public class) is accessible to all other classes. Therefore there can only be one public class in a file, which serves as the only entry and starting point into the application for the executing machine. As earlier said a class with no access modifier is not a public class but a default class and is only accessible to other classes in the same package. For example, to define a public class for a library object, the class definition may be written as done below:

public class BookLibrary

{

     public static void main(String[] args){

      Book myBook = new Book("Java Programming", "Feyisayo Dosunmu", 312);

      }

  }

The public class BookLibrary declares an object mybook of the type Book with the statement;

Book myBook = new Book(“Java Programming”, “Feyisayo Dosunmu”, 312);

Remember that the class Book is a default class so it can be stored in the same file with the class BookLibrary, now the compiler knows to look for the static main method in the only public class BookLibrary.

### 3.2.2 Private Access Modifiers

Private access modifiers may be applied to class member variables and methods. Private members and methods are accessible only by their class members and not by other classes and subclasses in the same package. For example, the class member variables “bookTitle”, “bookAuthors” and “noOfPages” were made private to the class “Book” to ensure proper encapsulation, and therefore made inaccessible to other classes of the same package. The full program listing is as provided in program listing 3.1 below:

Program listing 3.1 

public class BookLibrary

{

  public static void main(String[] args){

    Book myBook = new Book("Java Programming", "Feyisayo Dosunmu", 312);

    System.out.println("\n" );

    System.out.println("The title of my book is " + myBook.getBookTitle() );

  }

  }

   class Book{

    private String bookTitle, bookAuthors;

    private int noOfPages;

    public Book(String booktitle, String bookAuthors, int pages ){

      bookTitle= booktitle;

      bookAuthors= bookAuthors;

      noOfPages= pages;

    }

    public Book( ){

      bookTitle="No title yet";

      bookAuthors= "No author yet";

      noOfPages= 0;

    }

    public String getBookTitle( ){

      return bookTitle;

     }

    public String getBookAuthors( ){

      return bookAuthors;

     }

  }  

The output from the above program listing 3.1 when run is as shown in figure 3.1 below:

![](images/00004.jpeg)

Figure 3.1 Output of program listing 3.1.

### 3.2.3 Protected Access Modifier

The protected access modifier is applicable to class member variables and methods. The protected members are accessible within their own class hierarchy only. That is, a protected class member variable or method is accessible through sub classes in the same package and to subclasses in other packages. Protected access modifiers are applied to member methods that are created to be inherited or overridden by sub classes.

### 3.2.4 Private Protected Modifier

A private protected class member can be accessed through inheritance by classes in other packages. While private protected class members may not be accessed by any other non-sub classes in the same package but by subclasses in the same package.

### 3.2.5 The Default Access Modifier

A class with no specified access modifier is assigned a default access modifier by default. Note that the default access modifier has no keyword to represent it. The default access modifier only gives access to other classes in the same package.

### 3.2.6 The Abstract Modifier

A class that is modified with the abstract keyword is called an abstract class, which means that the class contains one or more un-implemented methods. An un-implemented method contains no body and therefore must be overridden in a sub class, this and more to be discussed later in the book.

### 3.2.7 The Static Modifier

A class member that is modified with the static access modifier belongs only to the class. It is unique and does not have instance copies. Normally, when instance objects are created from a class the objects get their own copies of the class member. But with the static modifier there is only one copy of such a class member variable.

A static member is accessed by using the class name followed by a dot, and it can be accessed before the creation of the class object. For this reason, static member variable must be initialized because they must have a value, and static methods must be defined. Member methods and variables can be declared as static. More importantly, the static keyword cannot be used in the class methods.

### 3.2.8 The Final Modifier

The final modifier can be used with a class, a method, or a member variable with different implications which are as explained below:

a) The Final Class

The keyword “final” when used as a class modifier renders the class un-inheritable. The syntax of usage is as described below:

final Book{

// class body

}

b) The Final Method

A method modified with the final key word is not overridable by inheriting or subclasses. The syntax of usage is as described below:

class book {

  final borrowBook( ){

      //body of method

  }

}

This acts just like the private access modifier.

c) The Final Variable

A variable modified with the final keyword becomes a constant whose value cannot be altered or updated after being initialized. The syntax of usage is as described below:

final String bookTitle;

## 3.3 Class Objects

An object is an instance of a class and do have characteristics which are the followings; identity, state, type and behavior. These characteristics are as further explained below:

### 3.3.1 An Object’s Type

The word “object” is a generic word for anything that can be named. An object must therefore belong in a category which may be a concept (an idea, knowledge or a method), a place, a thing, an animal or human. Therefore we say that an object has a type. Since an object will always belong in a category. For example the following java codes create an object of the type birds in the animal category.

Bird sparrow = new Bird( );

The word “Bird” at the left declares sparrow as a type Bird and the new keyword at the right allocated the needed memory space for the type Bird as defined by the Bird class and assigned the memory space address to the sparrow object. To use the above statement, you must have earlier created a class Bird somewhere in the program and the class may look like written below:

   class Bird{

    private int flightStatus;

    public Bird( ){

      flightStatus= 0;

    }

    void setFlightStatus(int flightHieght ){

      flightStatus = flightHieght;

    }

    int tellHeight( ){

      return flightStatus;

    }

  } 

### 3.3.2 An Object’s State

An Object has properties and these properties can be the object’s color, shape, weight, position, or size. An object’s property is always an attribute than can be measured and the value of this measurement determines the object’s state at any point in time. For example, the object sparrow has the property “flightStatus” which can be used to determine the flight status of the bird, whether in flight (when “flightStatus” is greater than 0) or perched (when flightStatus is 0).

### 3.3.3 An Object’s Identity

An object maintains a unique identity and is different to similar objects. For example, another object sparrow cannot be created in the same program block as long as the earlier created object sparrow is still in use and undeleted from the memory, but a similar type sparrow2 or eagle may be created. For this reason the following program statements are legal:

Bird sparrow2 = new Bird( );

Bird sparrow = new Bird( );

Bird eagle = new Bird( );

While the following declaration statements are not legal:

Bird sparrow = new Bird( );

Bird sparrow = new Bird( );

### 3.3.4 An Object’s Behavior

Since objects like bird, kite and plane can fly. Objects like robots and cameras can move and see, and objects like fish and submarines can swim. You would agree with me that objects have behaviors which are closely linked to their types. This phenomenon is what is defined in the class definition as object methods.

These methods (behaviors) are usually named with action words (verbs). For example, the “setFlightStatus( )” method of the class Bird is a general behavior of all objects in the category bird as a bird may decide to fly so high into the sky by setting its flight status to a value thousands of feet above sea level, or may decide to perch somewhere at the sea level, at zero foot above sea level. The following program listing 3.1 brings this concept to life.

Program listing 3.1

/* Importing the JOption class to create a visual input pane. */

import javax.swing.JOptionPane;

public class BirdObject

{

  public static void main(String[] args){

     Bird eagle = new Bird( );

  /*Reading a height value with the imported JOptionPlane class's method */

    String m = JOptionPane.showInputDialog("Enter a height in figure ");

    /*Setting eagle's flight behavior with the method setFlightStatus.*/

    eagle.setFlightStatus(Integer.parseInt(m));

    System.out.println("\n" );

    if(eagle.tellHeight() > 0 )

        System.out.println("Eagle is in flight mode. " );

    else

        System.out.println("Eagle has perched. " );        

   }

  }

   class Bird{

    private int flightStatus;

    public Bird( ){

      flightStatus= 0;

    }

    void setFlightStatus(int flightHieght ){

      flightStatus = flightHieght;

     }

    int tellHeight( ){

      return flightStatus;

    }

  }

Program listing 3.1 when executed would produce the following output shown in figures 3.1 and 3.2 below:

![](images/00005.jpeg)

Figure 3.1 Program listing 3.1 JOption input pane.

![](images/00006.jpeg)

Figure 3.2\. The output from program listing 3.1.

Program listing 3.1 started by importing the class JOptionPane to allow for the use of “JOptionPane” input method “showInputDialog( )” that will enable us enter a figure for the bird’s height above sea level later in our program. This action helps us alter the flight state for the object (eagle). The import keyword helps us import utility classes and packages called application programming interfaces (API) that we may need and there are many of them. We have available the input, the maths, the string and so on, for a full documentation of java core API classes please visit the following link: [http://docs.oracle.com/javase/8/docs/api/index.html](http://docs.oracle.com/javase/8/docs/api/index.html)

Next a public class BirdObject is defined, this is the main class and there can only be one of such class in a java file. The public class is what shall be referenced by the interpreter, and the starting point of execution is always the static main function of the public class. Therefore every java application must have a static main function and its signature is as given below:

Public static void main(String[ ] args){ }

The args string array is filled with the set of arguments supplied at the command prompt if any. An object eagle is created and an input dialog box object is called to get the height information with which the eagle’s state is set. After which we can then determine the eagle’s flight’s state through its behavioral methods “tellFlightStatus()”. To run this application you need to copy program listing 3.1 in a text editor saving it as BirdObject.java. If you haven’t downloaded and installed the java development kit, please visit section 1.4.1 of this book for a full guidance on how to download, install and set the path to the JDK.

## 3.4 Compilation and Running of Applications with the JDK

The java command line tool is used for compiling and running of your java source codes at the command prompt. To compile and run program listing 3.1 into byte codes that can be executed by any java virtual machine, simply go to the command prompt of your computer and change the directory to the folder where you saved your program file by using the “cd” (change directory) command and enter the javac command “javac” followed by the application’s file name as described below:

C:\users\computer name> cd\my_java_folder

C:\my_java_folder>javac BirdOBject.java

This assumes that your program listing is stored in a folder “my_java_folder” in your C drive. After entering the javac command if compilation is successful nothing is displayed and the byte codes for the class “BirdObject” is created in the directory as “BirdObject.class” which can now be executed with any machine that has the java virtual machine installed.

## 3.5 Running a Java Class file (Byte codes)

A java class file can be executed on any java virtual machine by using the java command with the java class name omitting the extension .java as shown below:

C:\my_java_folder>java BirdObjects

The expected output of the execution is a shown in figure 3.2 above. Please note that the directory path used in the output is different from the one used for the explanation. This is to let you know that you are free to save your source codes in any directory of your choice so long as you apply your javac and java command after changing to the source directory, all should be fine.

## 3.6 Returning Class Parameter Names at Runtime

Two types of parameter passing techniques are available in programming languages; positional parameter passing- where parameters are received according to their positions in the parameter list, and the nominal parameter passing- where a name-value pair is passed to the receiving method or function.

Java uses positional parameter passing techniques and it often becomes a challenge when interfacing with other nominal programming languages as there were no standard ways of retrieving class parameter names in the earlier versions of java including java 7\. This has been handled in java 8 by making it easier to return class parameter names through the class constructor method with the addition of the Parameter class to the core reflection package. Therefore to use the parameter class you need to import the class with the following statement:

import java.lang.reflect.Parameter;

You may also import the class Executable, a parent class of class “Method”, in order to retrieve an array of parameter objects, with the following import statement:

import java.lang.reflect.Executable;

With these additions it is now possible to access class parameter names in java 8\. This is done as illustrated in program listing 3.2 below. Please enjoy.

Program listing 3.2:

import java.lang.reflect.Parameter;

import java.lang.reflect.Executable;

public class Courier

{

  public static void main(String[] args){

    Letter myLetter = new Letter("London", "United State", "intransit" );

    myLetter.TellParameterNames( );

      }

  }

   class Letter{

    private String deliveryAddr, senderAddr, status;

    public Letter( ){

      deliveryAddr= " ";

      senderAddr= " ";

      status= " ";   

    }

    public Letter(String addr, String sender, String stat ){

      deliveryAddr= addr;

      senderAddr= sender;

      status= stat;   

    }

    void TellParameterNames( ){

     Parameter[] letterParameters;

     try{

     letterParameters =

       Letter.class.getConstructor(String.class, String.class, String.class).getParameters();

      for(Parameter paraName : letterParameters){

         if(paraName.isNamePresent()){

           System.out.println("parameters" +paraName.getName());

          }

      }

     }

     catch(NoSuchMethodException | SecurityException e ){

       System.out.println ("Exception");

     }

  }

}   

The output from program listing 3.2 above is as described below:

Parameters deliveryAddr

Parameters  senderAddr

Parameters status

In order to have this output, you need to compile the program at the command prompt with the option –parameters as described below:

C:\java_codes> javac –parameters Courier.java

With this said. We have come to the end of another interesting chapter. The following chapter promises to be more interesting as it discusses more about the concept of object’s behavior which is termed object oriented programming. See you there. Thank you for staying on.

# Chapter 4

# Object Oriented Programming and Default Interface Methods

Object oriented programming concepts enhance code re-usability, readability and program maintainability. Object oriented programmers do less coding and have lesser method names to remember and cope with. The key concepts of object oriented programming are object inheritance, abstract classes, interface and method overloading all working together to make the grand idea of polymorphism a possibility. Polymorphic methods and functions accept any argument type of a parent class and execute as expected. We begin our journey into the world of object oriented programming with a concept termed inheritance.

## 4.1 Class Inheritance

A subclass may inherit the member functions (methods) and variables (attributes) from a parent class in java by using the keyword ‘extends’. The syntax for inheritance is as shown below:

class SubclassClassName extends ParentClassName {

  //Sub class body

}

For example, a subclass ‘SmartPhone’ may inherit from a parent class ‘MobilePhone’, where the ‘MobilePhone’ class is as defined below:

   class MobilePhone{

    String textMessage, model;

    public MobilePhone(String phoneModel ){

      textMessage= " ";

      model= phoneModel;

    }

    public MobilePhone( ){

     textMessage= " ";

      model= "Nokia 310";

    }

    public String getModel( ){

      return model;

     }

    public String getTextMessage( ){

      return textMessage;

     }

     void receiveACall( ){

      System.out.println("Receiving a call." );

    }

    void makeACall( ){

      System.out.println("Making a call." );

    }

    void receiveTextMessage( ){

      System.out.println("Receiving a text message." );

    }

     void playAGame( ){

      System.out.println("Playing a 2D game." );

    }

   }   

The sub class SmartPhone inherits attributes and methods from the MobilePhone class (parent class) with the following java codes:

   class SmartPhone extends MobilePhone {

   String textMessage;

   String model;

   public SmartPhone( ){

    super("Nokia Old");

     textMessage= " ";

      model= " ";

    }

    public SmartPhone(String nmodel ){

      this( ); //Calls the SmartPhone( ) constructor

      model= nmodel;

    }

    @Override public String getModel( ){

      return model;

     }

    public String getOldModel( ){

      return super.model;

     }

    @Override public String getTextMessage( ){

      return textMessage;

     }

    @Override void playAGame( ){

      System.out.println("Play a 2D or 3D game." );

    }

    void browse( ){

     System.out.println("Browsing the net." );

    }

    void snapAPicture( ){

     System.out.println("Taking a picture." );

    }

    void scan_system( ){

     System.out.println("Scanning phone for possible damage." );

    }

   }    

Now the class “SmartPhone” has inherited methods from its parent class “MobilePhone” in addition to its own defined methods. A smart phone object would inherit all of the attributes of a mobile phone object and the programmer does not need to recode the methods “receiveACall()” for receiving calls, “makeACall( )” for making a call, “receiveTextMessage()” and “sendTextMessage( )” for receiving and sending text messages, which are the basic functionalities of a mobile phone.

These basic functionalities can be performed on any smart phone with the following java statements;

SmartPhone nokia = new SmartPhone( );

nokia.makeACall();

The program statement “nokia.makeACall();” uses the base method “makeACall( )” defined in the parent class “MobilePhone”. This is possible due to the inheritance relationship between the two classes. A sub class may also override variables and methods in a parent class by defining variables and methods with same names. This is term variable or method overriding.

## 4.2 Variable and Method Overriding

A variable can be overridden in a sub class by defining a member variable with a similar name in the subclass. This is necessary in situations where there is a need to process a similar attribute in the sub class as a class method can only process its class member variable or attribute.

In the same vain a base class method may be overridden by defining a method with a similar name in the sub class and also by adhering to the following rules of function overriding:

a) The sub class must have inherited from a parent class with a similarly named method

b) The overriding method must have a similar signature to the method to be overridden in the parent class

For example, the “playAGame( )” method of the parent class “MobilePhone” is overridden in the sub class “SmartPhone” by defining a similar method with same signature in the sub class as shown below:

    @Override void playAGame( ){

      System.out.println("Play a 2D or 3D game." );

    }

The difference is that the playAGame( ) method of the “SmartPhone” class is superior in functionality to that of the “MobilePhone” class as it can allow its users play 2D or 3D games due to its superior user interface and display screen. You would notice the method modifier “@override”. The method “@override” modifier is not mandatory but helps with program readability and compiler checking, as you can easily see which method has been overridden in the parent class, and the compiler will quickly help you know if you have not actually overridden a method thinking in error that you have.

This is possible if you did not fully abide by the rules of method overriding previously stated. The compiler would issue an error message “method does not override or implement a method from a super type”. More importantly if you changed the parent class later the compiler ensures that you also update the overridden method in the sub class too. Therefore the “@override” method modifier should be used in the following cases:

a) When a method in a subclass overrides a method in the parent class

b) When a class implements an interface and implements the virtual interface’s method

c) When a class extends an abstract class and implements its abstract method

d) When a sub interface extends another interface

## 4.3 The Constructor Function

A constructor function has the function of initializing the class member variables in instance objects upon declaration. The function is defined just like a class method except that it has no return data type but with the same name with the containing class. All classes in java inherit from the parent class “Object”. If you do not define a constructor function for your class and by so doing not overriding the default constructor, your class would use the inherited one from its default parent class. The constructor function that overrides the default constructor for the “MobilePhone” class is as shown below:

    public MobilePhone( ){

     textMessage= " ";

      model= "Nokia 310";

    }

The constructor must execute on every declaration of an object. Therefore when a class inherits from a parent class, whenever the sub class is declared the parent class constructor is implicitly called and executed by the java compiler.

You would notice that there are two constructor functions in the class “MobilePhone”, the compiler would only implicitly execute the one with no parameters, that is the one that met the override condition of the default constructor. But you may explicitly execute the second constructor with parameter from a sub class through the use of the “super” keyword.

## 4.4 The super and this keywords Application

The “super” keyword is used for referring to the parent class object and to execute the parent class constructor function. For example, you may use the following statement to execute the second constructor function for the class “MobilePhone” with the parameter “phoneModel” from its sub class “SmartPhone” as shown below:

    public SmartPhone( ){

    super("Nokia Old");

     textMessage= " ";

      model= " ";

    }

You can now use the “super” keyword to access the parent class method in the sub class “SmartPhone” like shown below:

    public String getOldModel( ){

      return super.model;

     }

While the “this” keyword is for referencing the current class’s instance object and this is done as illustrated below:

    public SmartPhone( ){

    super("Blackberry Old");

     textMessage= " ";

      model= " ";

    }

    public SmartPhone(String nmodel ){

      this( ); //Calls the SmartPhone( ) constructor

      model= nmodel;

    }

The statement “this();” in the parameter constructor “SmartPhone(String nmodel)” refers to the no parameter constructor “SmartPhone( )” of the current class. This constructor is therefore executed first before the body of the parameter constructor. Note that if you are going to be using the “this” and “super” keywords to execute the constructors they must be the first statement you write in the constructor functions to enable the default and base constructor execute before any other constructor.

Program listing 4.1 below puts the classes together in the same file with the public class “CellPhones” which contains the public main function for the execution of the package.

Program listing 4.1:

public class CellPhones

{

  public static void main(String[] args){

    SmartPhone myPhone = new SmartPhone("Nokia");

    System.out.println("\n" );

    System.out.println("My phone model is " + myPhone.getModel( )+ "\n" );

    System.out.println("The old model is " + myPhone.getOldModel( ) );

  }

  }

   class MobilePhone{

    String textMessage, model;

    public MobilePhone(String phoneModel ){

      textMessage= " ";

      model= phoneModel;

    }

    public MobilePhone( ){

     textMessage= " ";

      model= "Nokia 310";

    }

    public String getModel( ){

      return model;

     }

    public String getTextMessage( ){

      return textMessage;

     }

     void receiveACall( ){

      System.out.println("Receiving a call." );

    }

    void makeACall( ){

      System.out.println("Making a call." );

    }

    void receiveTextMessage( ){

      System.out.println("Receiving a text message." );

    }

     void playAGame( ){

      System.out.println("Playing a 2D game." );

    }

   }   

   class SmartPhone extends MobilePhone {

   String textMessage;

   String model;

    public SmartPhone( ){

    super("Nokia Old");

     textMessage= " ";

      model= " ";

    }

    public SmartPhone(String nmodel ){

      this( ); //Calls the SmartPhone( ) constructor

      model= nmodel;

    }

    @Override public String getModel( ){

      return model;

     }

    public String getOldModel( ){

      return super.model;

     }

    @Override public String getTextMessage( ){

      return textMessage;

     }

    @Override void playAGame( ){

      System.out.println("Play a 2D or 3D game." );

    }

    void browse( ){

     System.out.println("Browsing the net." );

    }

    void snapAPicture( ){

     System.out.println("Taking a picture." );

    }

    void scan_system( ){

     System.out.println("Scanning phone for possible damage." );

    }

   }

The output of program listing 4.1 when executed is as shown in figure 4.1 below:

![](images/00007.jpeg)

Figure 4.1 The output of program listing 4.1.

You are free to experiment with the program listing, the reason for providing the full listing.

## 4.5 Function Overloading

A function is overloaded when another function of similar name but with a different signature is written, a good example are the “SmartPhone” constructors. The two constructors have similar names but differ in parameter list. The first accepted no parameter at all, while the second accepted a string parameter (nmodel), and the compiler knew which constructor to call based on the differing signatures.

## 4.6 Abstract Classes

An abstract class is a class with at least an un-implemented method (abstract method) and has an abstract modifier. An Abstract method is a method with no implementation but with a signature (method name with its optional parameter list). This is as shown in the syntax of usage below:

Public abstract method_name(optional parameter_list);

Since an abstract class has at least one abstract method, no instance of such a class can be created. Such a class is only good for inheritance purposes only, and a subclass must inherit and provide the required implementation for the inherited abstract method, if not, the subclass becomes an abstract class too. The syntax for an abstract class is described below:

abstract class class_name{

  public abstract method_name(optional parameter_list);

}

The abstract method is implicitly declared as public for it to be implementable by an inheriting class and if not implemented by the inheriting class the class also become abstract as earlier said.

The concept is illustrated with a “MotorVehicle” class. All types of cars inherit from their parent “MotorVechicle” class and all kinds of cars perform similar tasks and their interface is used in the same way (a car steering wheel is used in the same way for all cars), the difference is in the technology applied for efficiency in performance (power steering wheels). But there is an exception to the rule, the gearing system in an automatic car is different both in appearance and usage to the gearing system in a manual car.

For this reason we cannot have a generic parent class “MotorVehicle” with all its method fully implemented for overriding when necessary in its sub classes as we did with the “MobilePhone” class in program listing 4.1 because we do not know for sure what kind of vehicle (automatic or manual) would be inheriting from the class “MotorVehicle”. It is therefore wise to leave the implementation of the gearing system method to the implementing class by making the method an abstract one in the parent class. This action ultimately turned the parent class into an abstract class. The definition is therefore as written below:

abstract class MotorVehicle{

   public abstract void applyGear( );

}

Now the manual vehicle class can inherit the abstract “MotorVehicle” class and implement its own version of the applyGear( ) method as shown below:

class ManualVehicle extends MotorVehicle{

  String gearType;

  public ManualVehicle( ){

   gearType = "A manual gearing system.";

  }

  @Override public void applyGear( ){

    System.out.println("\n Manually change the gear by applying the clutch." );

  }

  String displayGearType( ){

   return gearType;

  }

}

Also the automatic vehicle class can implement its own version of the gearing system method by implementing the abstract “applyGear( )” method inherited from the MotorVehicle class as shown below:

class AutomaticVehicle extends MotorVehicle{

  String gearType;

  public AutomaticVehicle( ){

   gearType = "An automatic gearing system.";

  }

  @Override public void applyGear( ){

    System.out.println("\n Change the gear by gently pushing or pulling the gear lever." );

  }

  String displayGearType( ){

   return gearType;

  }

}

The sub classes can now be utilized in a CarMart main class as described below in program listing 4.2 below:

Program listing 4.2:

/* Importing the JOption class to create a visual input pane. */

import javax.swing.JOptionPane;

public class CarMart

{

  public static void main(String[] args){

   AutomaticVehicle myAutomaticCar = new AutomaticVehicle( );

   ManualVehicle myManualCar = new ManualVehicle( );

    /*Reading the desire vehicular type with the imported JOptionPlane class's method */

    String m = JOptionPane.showInputDialog("Enter (1) for a Manual vehcice (2) for an automatic one ");

    if(Integer.parseInt(m) == 1 )

       myManualCar.applyGear( );

    else

       myAutomaticCar.applyGear( );     

  }

  }

Program listing 4.2 input and output upon execution are as shown in figure 4.2 below:

![](images/00008.jpeg)

Figure 4.2a the input pane for program listing 4.2.

![](images/00009.jpeg)

Figure 4.2b the output from running program listing 4.2\.

We haven’t exhausted the advantages of using abstract classes just yet. You would notice that the class “AutomaticVehicle” and “ManualVehicle” have similar “applyGear()” methods in common, these methods expose an interface opportunity between the two classes. This is also an opportunity for implementing polymorphism since a method that accepts a class as an argument would also accept all sub types of that class. This takes us to another object oriented programming concept “interface”.

## 4.7 Interfaces

Abstract classes lead naturally to the creation of interfaces between classes. Interfaces aid polymorphism in programming just like abstract classes do, but the difference is that abstract classes do this through inheritance as earlier described and interfaces achieve this through parameters.

In previous versions of java up to java 7, an interface does not implement any of its methods. The methods are left to the implementing classes as contracts that must be implemented. But in java 8 there is an improvement to java, which allows for a default implementation of the interface methods in the interface itself. Therefore an implementing class is no longer enforced to implement the defaulted method.

A class does not extend an interface but implements one or more interfaces. A class can only extend one class at a time making interfaces lot more flexible and polymorphic in application. An interface is given an adjective name by standard and created with the “interface” keyword. An interface member variable is declared as public and static if present, and its member methods are declared as public and abstract by default. In summary an interface can only have constants, abstract and default methods as its member variables and methods. The syntax of creation is as described below:

interface interface_name{

Static variables ;

abstract method declarations;

default method declaration;

}

Program listing 4.3 illustrates the declaration of a default interface method “myMessage()” and provides a default implementation of the default method, please enjoy.

Program listing 4.3:

public class FunctionalInterface

{

    public static void main(String[] args){

  Confidential toMum = new Confidential( );

  MyMessage toCarthy = new MyMessage( );

  System.out.println("\n My message to mum: " + toMum.myMessage( ));

  System.out.println("\n My message to Carthy: " + toCarthy.myMessage( ));

  }

}

//The Message interface

interface Messaging{

  default String myMessage( ){

   return "Sorry, I am out of the office at the moment.";

  }

}

class MyMessage implements Messaging {

  //Fails to implement myMessage( ) interface  method.

  }

class Confidential implements Messaging {

    public String myMessage(){

    return "See you soon mum. Love you.";

  }

}

An interface is defined with the keyword interface. If an interface has a default method and the implementing class did not implement the defaulted method then the defaulted method shall be implemented when a call to that method is made in the implementing class as shown in figure 4.3, the program output of program listing 4.3 below:

![](images/00010.jpeg)

Figure 4.3 An output from program listing 4.3 above.

The call to the object “toMum” of class “Confidential” which implemented the defaulted method “myMessage” in the implemented interface “Messaging” gave a customized message to mum. While a similar call to the object “toCarthy” of class “MyMessage” also implementing the same interface with class Confidential, but failing to implement its defaulted method “myMessage” produced a default out of office message.  A more advance interface implementation is discussed in the following section 4.8\.

## 4.8 Interface Implementation

Now to define an interface for the common methods names “applyGear()” in classes “AutomaticVehicle” and “ManualVehicle” of program listing 4.1 above, we write the following java codes:

interface AutoManual{

   public void operateGear(MotorVehicle motor);

}

Notice that the argument type declared for the “operateGear()” abstract method of “AutoManual” interface is the abstract class “MotorVehicle” from which the “AutomaticVehicle” and “ManualVehicle” classes inherited. Therefore any other class that implements the “AutoManual” interface must implement the “operateGear( )” abstract method (since this method is not defaulted) and can operate any motor car object whether automatic or manual. The implementing class is as shown below:

class AutoManualOperator implements AutoManual{

    public void operateGear(MotorVehicle m){

       m.applyGear();

    }

}

This is seriously polymorphic and this is what interfaces do. I demonstrate this in program listing 4.3 by improving on the public class CarMart of program listing 4.2 to have a new public class CarMartInterface as shown below:

Program listing 4.3:

/* Importing the JOption class to create a visual input pane. */

import javax.swing.JOptionPane;

public class CarMartInterface

{

  public static void main(String[] args){

  AutomaticVehicle myAutomaticCar = new AutomaticVehicle( );

   ManualVehicle myManualCar = new ManualVehicle( );

 AutoManualOperator operator = new AutoManualOperator( );

    /*Reading the desire vehicular type with the imported JOptionPlane class's method */

    String m = JOptionPane.showInputDialog("Enter (1) for a Manual vehcice (2) for an automatic one ");

    if(Integer.parseInt(m) == 1 )

       //myManualCar.applyGear( );

 operator.operateGear(myManualCar);

    else

       //myAutomaticCar.applyGear( );     

 operator.operateGear(myAutomaticCar);

  }

  }

abstract class MotorVehicle{

   public abstract void applyGear( );

}

class ManualVehicle extends MotorVehicle{

  String gearType;

  public ManualVehicle( ){

   gearType = "A manual gearing system.";

  }

   @Override public void applyGear( ){

    System.out.println("\n Manually change the gear by applying the clutch." );

  }

  String displayGearType( ){

   return gearType;

  }

}

class AutomaticVehicle extends MotorVehicle{

  String gearType;

  public AutomaticVehicle( ){

   gearType = "An automatic gearing system.";

  }

   @Override public void applyGear( ){

    System.out.println("\n Change the gear by gently pushing or pulling the gear lever." );

  }

  String displayGearType( ){

   return gearType;

  }

}

interface AutoManual{

public void operateGear(MotorVehicle motor);

}

class AutoManualOperator implements AutoManual{

    public void operateGear(MotorVehicle m){

       m.applyGear();

    }

}

Notice that the method “operateGear()” of class AutoManualOperator accepted different objects “myAutomaticCar” and “myManualCar” without any problem. The method “operatorGear()” is therefore an interface and serves as an interface between the two classes. I have also been using the “if statement”, please pardon me for now, it is just that I couldn’t have avoided its usage at this time. The idea is that if the expression in the “if statement” is true then the interpreter executes its code block and avoid the else’s code block, but if not, does not execute the “if statement” block but executes the else’s. I hope you got the idea. Decision statements shall be treated later in another chapter in this book, trust me. The double forward slashes (//) are used for line comments. This slashes were used to comment out previous non interfacing program statement of program listing 4.1\.

When executed program listing 4.2 has the same output with that of 4.1 but do not have to deal with two different methods to operate the car gear system whether manual or automatic. The program knows how to do this itself. That is true automation and that is what interfaces do.

### 4.8.1 A functional Interface

A functional interface is an interface with only a single abstract method. The following interface definition is a functional interface:

interface multiplier{

  float processMyNumber(float r);

}

A functional interface is a good candidate for lambda expression, the newly introduced short hand of writing inline functions in java. As a matter of fact polymorphism is taken to the next level with lambda expressions. The following section discusses lambda expressions and functional interfaces.

## 4.9 Lambda Expressions and Functional Interfaces

Lambda expressions are functions in mathematics and also in computing. They are better replacements for anonymous functions in java 8 and very useful with functional interfaces. Whenever you find yourself dealing with an interface having a single abstract function you can safely use lambda expressions to simplify your codes.

### 4.9.1 Lambda Expressions

The following are the basic syntax of lambda expressions:

parameter -> expression

or

(type_declaration parameter) -> expression

or

(parameters) -> expression

or

(type_declaration1 parameter, type_declaration2 parameter) -> {statements}

The parenthesis are optional and the also the braces. If you have more than one statement at the right side you may enclose you statement in braces as described above, and if you have more than one parameter at the left side you may also enclose them in parentheses. The type declaration is also optional; the compiler can infer it from the supplied parameter. Also the return keyword is not required. The followings are examples of valid lambda expressions:

(a)->a *a;

Takes an argument ‘a’ multiplies it by itself and returns the result.

a -> a + a;

Takes an argument ‘a’ add it together and return the result.

(int a, int b) -> a – b;

Takes arguments “a” and “b” at the left side of the indirection, minus the value of argument “b” from argument “a” and returns the result.

(String t) -> System.out.println(t);

The lambda expression prints out the content of string t to the console.

### 4.9.2 Using Lambda Expressions with a Functional Interface

The following program listing illustrates the use of lambda expression in carrying out mathematic calculations through the use of a functional interface:

interface multiplier{

  float processMyNumber(float r);

}

Earlier defined in section 4.8.1 above.

Program listing 4.4:

public class LambdaOperator

{

  public static void main(String[] args){

   Result res = new Result( );

   float n=8;

   multiplier square = (a) -> a * a;

   multiplier doubler = a -> a + a;

   System.out.printf("\nResult of squaring %f is %f ", n, res.numberNSquare(n,square));

   System.out.printf("\nResult of doubling %f is %f ", n, res.numberNSquare(n,doubler));

  }

}

interface multiplier{

  float processMyNumber(float r);

}

class Result {

   float hold;

   void result(){

     hold =0;

   }

   float numberNSquare(float n, multiplier squaredNo){

     return (squaredNo.processMyNumber(n));

   }

}

The output from program listing 4.4 above is as shown in figure 4.4 below:

![](images/00011.jpeg)

Figure 4.4 The output from program listing 4.4.

The “square” and the “doubler” lambda expressions implicitly implemented the only abstract method “processMyNumber” of the interface “Multiplier”. The interface “Multiplier” was declared as a second argument to the method numberNSquare(int, Multiplier ) of class  “Result”, and with this the method “numberNSquare” would accept any object type of the interface.  So we were able to pass in the lambda expressions into the method “numberNSquare” as required. This greatly simplified the codes and making it more polymorphic.

Before I round up this chapter, one final note, an interface can extend another interface. Give it a try and let’s meet again in the next chapter to discuss program loops and arrays. Thank you for being there.

# Chapter 5

# Program Control Loops and ForEach Loop

Program loops are program statements that execute blocks of statements for repeated number of times. We have three basic types of control loop statements; the for loop statement, the while loop statement, and the do statement. We shall be looking at each in turn in this chapter.

## 5.1 The For Loop Statement

The “for loop statement” executes a block of program statements or a single program statement within an opening and closing braces for a specific number of times. The general syntax for a “for loop” statement is as shown below:

for( loop_variable; loop_conditional_expr ; loop_incremental_stmt ){

   loop statements

}

The loop variable set the initial value for the incremental statement variable. The execution of a “for loop statement” starts with the loop variable initialization. There may be more than one loop variables so long as they are separated with commas all should be fine. After the loop variable is initialized, the loop conditional expression is evaluated, and if it evaluates to a true value the loop statement is executed and the increment statement is executed for another iteration. And if the conditional expression does not evaluate to a value true the loop is exited. For an illustration, program listing 5.1 prints out a set of numbers from 1 to 10 on the console by using a for loop statement.

Program listing 5.1:

public class ForLoop

{

  public static void main(String[] args){

     for(int i=1; i < 11 ; ++i)

     System.out.println(i);

   }

}

The output from program listing 5.1 is shown in figure 5.1 below:

![](images/00012.jpeg)

Figure 5.1 Output from program listing 5.1.

The for loop statement in program listing 5.1 started with the initialization of variable i to 1 in the loop variable statement (i = 1). It then evaluated the loop conditional statement (i<10) to test if variable "i” was still less than 10 and if true the for loop statement body is executed. You can omit the loop statement opening and closing braces if you have a single line of statement in your for loop block as in program listing 5.1 above.

## 5.2 The Nested For Loop Statement

A nested for loop represents an occurrence of an iterative event for a specific number of times. It is a “for loop” inside of another for loop’s block. The syntax for a “for loop” statement is as described below:

for (loop_var1; conditional_expr; incremental_stmt1)

   for(loop_var2; conditional_expr2; incremental_stmt2)

     loop statement;

For an illustration, program listing 5.2 generates a set of multiplication tables from 1 to 4 using a nested for loop program structure.

Program listing 5.2:

public class NestedForLoop

{

  public static void main(String[] args){

    for(int i=1; i < 5 ; ++i){

        System.out.println( "\n" + i + " Series Times Table" + "\n" );

       for(int j=1; j < 4 ; ++j)

          System.out.println( i + " * " + j + " = " + (i*j) );

       }

  }

}

The output from program listing 5.2 is as shown in figure 5.2 below:

![](images/00013.jpeg)

Figure 5.2 the output from program listing 5.2\.

Please not that you cannot re-use variable names already used in the outer loop again in the inner for loop. This is because the scope rule also applies here. The inner and outer loops are in same program block and therefore have the same scope.

## 5.3 The Enhanced For Loop

The enhanced for loop is often used with the array and its general syntax of usage is as shown below:

for( data_type element: array_name )

          program stament;

More on the enhanced for loop later in the array section.

## 5.4 The Lambda foreach Loop

The lambda foreach is introduced into java 8 SE with the inclusion of the stream class to the java utility’s Collections package (java.util.Collections) of the core API. The stream class comes with some utility methods of its own like the min, max, filter, findFirst, and many others. Now, stream can be used in combination with the lambda for foreach loop to simplify the enhanced for loop to the following statement:

collection_name.stream  ().forEach((object) -> {

statement;  })

Collections like arrayLists can now use the method stream with forEach functional statement block to process their collections. An array is a collection of objects of the same type e.g. a set of integer numbers from 1 to 10, while an arraylist is a collection of objects of the same type.  We discuss more on this in sections 5.7 and 7.8b of this chapter and chapter seven of this book. The following program listing 5.3 illustrates the use of for each Loop by converting an array into an arraylist and then list out the contents of the array list with the “forEach” functional lambda expression.

Program listing 5.3:

import java.util.Arrays;

import java.util.ArrayList;

public class FilterLoop

{

  public static void main(String[] args){

   //Declaring and initializing an arraylist counter with odd numbers

  ArrayList<Integer> counter = new ArrayList<Integer>(Arrays.asList(1,3,5,7,9));

  System.out.println("\n A list of Odd numbers: ");

//Using the forEach inline statement to print out a list of odd numbers

   counter.stream().forEach((num) -> System.out.println(num));

     }

  }

The output is as shown in figure 5.3 below:

![](images/00014.jpeg)

Figure 5.3 The output from program listing 5.3.

Do not worry too much about the array and arraylist as they shall be discussed in full details in chapter 7 of this book, just take them as presented for now.

## 5.5 The While Loop statement

The while loop is employed in situations where we require a program statement or a statement block to be executed based on the outcome of the evaluation of a conditional expression. The syntax for a while statement is as shown below:

While (conditional expression){

    Program statement;

    Loop expression;

}

For example, to produce a list of odd numbers between the range 0 and 10, we would require a while loop as we may not know how many odd numbers there are until we start counting. Therefore, all we need to do is set a limit for the program and let the program list the odd numbers for us, whether in the range 0 to 10 or in the range 0 to 1000\. Program listing 5.4 produces a list of odd numbers in the range 0 to 10:

Program listing 5.4:

public class WhileLoop

{

  public static void main(String[] args){

   int counter = 10;

    System.out.println("\n A list of Odd numbers: ");

    while (counter > 0 ){

      if( (counter % 2 ) != 0 )

         System.out.println(counter);

      --counter;

        }

   }

  }

The while loop executed the “if program block” iteratively decrementing the value in variable “counter” until “counter” becomes 0 and the while loop terminates. The conditional expression of the “if” statement tested the value in variable counter for oddness by dividing counter with the modulus operator (%) which returns the remainder of a division operation. If the “if” conditional expression returned a value greater than 0 then the operand in question is odd and the value was printed to the output. The output from the execution of program listing 5.4 is as shown in figure 5.4 below:

![](images/00015.jpeg)

Figure 5.4 The output from program listing 5.4\.

## 5.6 The Do statement

The do statement is a variation of the while statement. It is used in situations where we want a program statement or a statement block executed at least once. The syntax for the do statement is as described below:

do{

program statement;

}

While(conditional _expression);

The do loop statement block is executed before the conditional expression can be evaluated.

## 5.7 The Stream “filter” Method

The newly introduced stream’s filter method of java 8 SE can be used in combination with the “forEach” lambda expression to replace the while loop when processing a collection, for simplicity as described in program listing 5.5 below:

Program listing 5.5:

import java.util.Arrays;

import java.util.ArrayList;

public class FilterLoop

{

  public static void main(String[] args){

ArrayList<Integer> counter = new ArrayList<Integer>(Arrays.asList(0,1,2,3,4,5,6,7,9));

System.out.println("\n A list of Odd numbers: ");

  counter.stream().filter((num) -> ((num % 2 ) != 0 )).forEach((num) -> System.out.println(num));

  }

}

The output from program listing 5.5 is as presented in figure 5.5 below:

![](images/00016.jpeg)

Figure 5.5 The output from program listing 5.5 above.

At this juncture we bring another chapter to a close to begin with another one on decision statements. Thank you for being there, I hope you had a beautiful programming experience.

# Chapter 6

# Program Decision Statements

Computers are considered intelligent because of their inherent ability to make intelligent decisions. The ability comes from the decision statements in computer programs. Decision statements help computers programs make intelligent decisions based on some criteria in their conditional expressions that are evaluated during execution.

There are basically three types of decision statements; the “if” statement, the “if.. else” statement, and the “switch case”. In this chapter we shall be looking into each one in turn, starting with the simplest of all, the “if” statement.

## 6.1 The if statement

The “if” statement executes its statement block only if its conditional expression evaluates to a Boolean value true and transfers the flow of control to the program statement immediately after the “if block” if a false Boolean value is returned. The general syntax of an “if” statement is as described below:

if (conditional_expression){

  Program statement;

}

Below is a segment of program listing 5.3 where the “if” statement was used to test a numeric counter value for oddness.

if ((counter % 2) != 0)

     System.out.println(counter);

## 6.2 The if else Statement

The “if else” statement is a compound if statement. In addition to having the if program block it also has the else program block, which is processed when the outcome of the evaluation of its conditional expression is a Boolean value “false”. The syntax for the “if else” statement is as described below:

if ( conditional_expression ){

   // if statement block

}

else{

   //else statement block

}

The opening and closing braces may be omitted from the “if block” if only a program statement is available in the “if block”. The same exception applies to the else block. For a short illustration of the “if else” statement program listing 6.1 tests that an integer input is provided:

Program listing 6.1:

import javax.swing.JOptionPane;

import java.util.Scanner;

public class IfElse

{

  static Scanner inc = new Scanner(System.in);

  public static void main(String[] args){

    System.out.print("\n Please enter a value-> ");

      if( inc.hasNextInt( ) )

         System.out.println("You entered an integer");

      else

         System.out.println("\n You entered a non integer");

   }

  }

Program listing 6.1 makes use of the Scanner class that is available in the java utility package. To use the Scanner methods for reading inputs, you need to import the class and this was done with the import statement in the second line of the program listing. The program uses the “hasNextInt( )” method of the “Scanner” class to test if an input is an integer value, it returns the Boolean value “true” if the input is an integer and Boolean value “false” if otherwise, and the if statement block makes the appropriate decision based on the returned value. The input and output from listing 6.1 is as shown in figure 6.1 below:

![](images/00017.jpeg)

Figure 6.1 Inputs and outputs of program listing 6.1.

## 6.3 The Ternary Operator

The ternary operator is another form of the “if else” statement that can be compactly used to perform the same decision making function of the ”if else” construct in some cases. The symbols used to denote the ternary operator are the question mark (?) and the full colon (:). The general syntax of usage is as described below:

conditional_expression ? expression-1 : expression-2;

If the conditional expression returns a Boolean value “true” expression-1 is executed and if otherwise expression-2 is executed and returned. Program listing 6.2 illustrates the use of the ternary operator.

Program listing 6.2:

public class TernaryOperator

{

  public static void main(String[] args){

    int num=-9;

System.out.println( num < 0 ? 0 : 1 );

  }

}

The ternary statement tested its conditional expression to know if the value in variable num is less than zero, if so its returns 0 else it returns value 1\. The output from program listing 6.2 as shown in figure 6.2 below:

![](images/00018.jpeg)

Figure 6.2 The output from program listing 6.2.

## 6.4 The else if statement

The “else if” statement is another compound “if” statement that can test more than two alternatives conditional expressions for their returned Boolean results and execute an appropriate if block based on the returned result. The usage syntax for the “else if” statement is as described below:

If(conditional_expression1){

  program statement;

}

else if (conditional_expression2){

  program statement;

}

else if (conditional_expression3){

    program statement;

}

else{

  Program statement;

}

The else if statement can process more than one conditional expression options. Program listing 6.3 illustrates this with a program that can determine the input data type.

Program listing 6.3:

import javax.swing.JOptionPane;

import java.util.Scanner;

public class ElseIf

{

  static Scanner inc = new Scanner(System.in);

  public static void main(String[] args){

    System.out.print("\n Please enter a value-> ");

      if( inc.hasNextInt( ) )

         System.out.println("You entered an integer. ");

      else if ( inc.hasNextFloat( ) )

         System.out.println("\n You entered a floating point number.");

      else if ( inc.hasNextDouble( ) )

         System.out.println("\n You entered a double data type.");

      else if ( inc.hasNextBoolean( ) )

         System.out.println("\n You entered a booleann value.");

      else if ( inc.hasNextByte( ) )

         System.out.println("\n Your entered data is in bytes.");

      else if ( inc.hasNextShort( ) )

         System.out.println("\n You entered a short integer value.");

      else if ( inc.hasNextLong( ) )

         System.out.println("\n You entered a long integer value.");

      else

         System.out.println("\n You entered other type of data.");

   }

  }

Program listing 6.3 makes use of the scanner class methods for comparing the input types in its conditional expression to determine what the data input type is, printing the type out to the standard output.

The conditional expressions in the else-if statement are much like that of the if-else statement, must return Boolean true or false values to be legal. The values 0 and 1 cannot be used in place of the Boolean values ‘false’ and ‘true’, meaning that the conditional expressions may not evaluate to an integer or char value.

## 6.5 The Switch Statement

A switch statement works much like the else-if statement except that the expressions must evaluate to an integer, String or enumerated type which is compared with the switch’s case values to determine the case block to execute. Therefore, in instances where alternative code blocks are required for execution based on a given char, int or enumerated input value, the switch statement is the most appropriate statement construct option. The general syntax for a switch statement is as described below:

switch (expression)

   case value-1:

      program statement;

   break;

   case value-2:

      program statement;

   break;

   case value-3:

      program statement;

   break;

   default:

      default program statement;

   break;

}

A case block does not require the opening and closing braces.  A case block is terminated with a break statement as described above and if the break statement is omitted program execution would continue on to the following case block and on and on until a break statement is encountered or the end of the switch statement is reached. Program listing 6.4 below illustrates the use of a switch statement:

Program listing 6.4:

import javax.swing.JOptionPane;

public class SwitchStatement

{

  public static void main(String[] args){

    /*Presenting the menu */

    String m = JOptionPane.showInputDialog("What would you prefer for breakfast; Enter (1)for chicken and chips (2) for porridge and (3) for bread and tea ");

     switch(Integer.parseInt(m)) {

      case 1:

        System.out.println("\n You selected chicken and chips for breakfast");

      break;

      case 2:

        System.out.println("\n You selected porrage for breakfast");

      break;

      case 3:

        System.out.println("\n You selected bread and tea for breakfast");

      break;

      default:

         System.out.println("\n Please pick a menu from the list.");

      break;     

     }

   }

  }

And the input and output from program listing 6.4 is as shown in figure 6.4a and 6.4b below:

![](images/00019.jpeg)

Figure 6.4a Input into program listing 6.4 above.

![](images/00020.jpeg)

Figure 6.4b Output from program listing 6.4 above.

This brings us once again to the end of another exciting chapter. I can only hope that you have enjoyed the content. Please let’s meet again in the next chapter to discuss arrays and strings. Thank you for being there once again.

# Chapter 7

# Array and ArrayList and Parallel Sorting

An array is a collection of similar data types that share an indexed group name. It is considered to be an object in java and always passed as a reference to receiving methods, and never by value as done with variable names.

## 7.1 Array Declaration

The syntax for an array declaration is as described below:

Data_type[] array_name;

For example, to declare a String array “balls” that holds a collection of different types of balls, the following java statement is written:

String[] balls;

However, declaring a variable name as an array does not automatically allocate the required memory space to the array name. To make the compiler do this you need to use the new keyword as done below:

balls = new String[4];

Or you may have declaration and memory space allocation on a single line like done below:

String[] balls = new String[4];

The phrase “new String[4]” phrase allocated four contiguous memory spaces of size String in the heap memory area of the computer system to the array variable name balls. Now array balls can store four different balls names.

## 7.2 Array Assignment

Array memory slots can be initiated with preset values at creation like shown below:

String[] balls = {"Basketball", "Baseball", "Volley Ball", "Football" };

Also an array slot may be assigned with a value through an assignment like shown below:

balls[0] = "Basketball";

However, the assignment can only be done after memory space allocation is done for an array. You must also note that an array index starts from 0 in java, C, C++ and C#. Also an array object in java has a public field “length” that you can always use to return the length of an array object. For example to determine the length of the array “balls” the following statement is applicable.

int array_length = balls.length;

## 7.3 Multi-dimensional Arrays

A multi-dimensional array is an array of arrays. For example, the following statement declares a two dimensional array “rooms” that holds the available rooms in a two story house.

int[][] rooms;

You can allocate the necessary memory space for a two story building with ten rooms on each floor (an array of two arrays with ten slots each) with the following statement:

rooms = new int[2][10];

or you may have the two statements together as shown below:

int[][] rooms = new int[2][10];

You can now assign values to the rooms’ slots to indicate their availability. That is, you may assign a value 1 to a room that is occupied and a value 0 to a vacant room’s slot. This is as described in the code statement below:

rooms[1][4] = 0;

The above statement assigns a value 0 to room five on the second floor of the house. Remember that our index will always start from 0\. An easier way of initiating all rooms to a value 0 is to use a nested for loop statement as described below:

    for(int floor=0; floor < rooms.length; ++floor)

      for(int room_no=0; room_no < 10; ++room_no)

                rooms[floor][room_no] = 0;

The first “for” statement’s initialization expression initialized the floor variable to 0, setting it to the beginning of the two dimensional array (first floor), and the conditional expression uses the length public array field to retrieve the length of the two dimensional array which is 2\. The second for statement loops through the rooms on each floor. 

## 7.4 The Enhanced For Loop

The enhanced for loop was introduced with java5\. It can be used for accessing the contents of an array without you having to worry about the array index or checking the array length. It is a more compact statement and its syntax of usage is as described below:

for (data_type slot_identifier : array_name)

   program statement;

For example, if we were interested in displaying the contents of the balls array, we could achieve this with the following enhanced “for loop” statement in program listing 7.1 below:

Program listing 7.1:

public class ArrayTester

{

  public static void main(String[] args){

     String[] balls = {"Basket ball", "Base ball", "Volley Ball", "Foot ball" };

 for(String ball : balls)

     System.out.println(ball);

  }

}

The output from program listing 7.1 is as shown in figure 7.1 below:

![](images/00021.jpeg)

Figure 7.1 Output from program listing 7.1.

You can also display the content of the two dimensional array rooms with the following enhanced for loop statement of program listing 7.2 below:

Program listing 7.2:

public class ArrayTester

{

  public static void main(String[] args){

     int[][] rooms = new int[2][10];

    for(int floor=0; floor < rooms.length; ++floor)

      for(int room_no=0; room_no < 10; ++room_no)

        rooms[floor][room_no] = 0;

    //The enhanced for loop statement

    for(int[] flr: rooms)

     for(int rm : flr)

        System.out.printf(" %d", rm);

  }

}

The output from program listing 7.2 above is shown in figure 7.2 below:

![](images/00022.jpeg)

Figure 7.2 The output from program listing 7.2\.

## 7.5 ArraySorting

The java Arrays class of the java utility package has many static methods for frequently performed operations on arrays like array sorting. For example, the balls array can be sorted by the application of the Arrays’ utility method “sort( )” like demonstrated in program listing 7.3 below:

Program listing 7.3:

import java.util.*;

public class ArraySorter

{

  public static void main(String[] args){

     String[] balls = {"Basket ball", "Base ball", "Volley Ball", "Foot ball" };

    System.out.println("\n A list of array balls' content before sorting -> \n");

    for(String ball : balls)

     System.out.println(ball);

    Arrays.sort(balls);

    System.out.println("\n A list of array balls' content after sorting ->\n");

    for(String ball : balls)

     System.out.println(ball);

  }

}

The output from program listing 7.3 is shown in figure 7.3 below:

![](images/00023.jpeg)

Figure 7.3 Output from program listing 7.3.

## 7.5b Parallel Array Sorting

The new java8 has introduced the concept of parallel array sorting that has improved the java sorting programs efficiency by about thirty percent (30%). The technology is designed for sorting on dual or quad core computers and the only drawback is that the system would require another memory space equivalent to the array size to be sorted. The newly added “parallelSort()” method to the  “java.util.Arrays” package and its constructor variants are as described and applied in program listing 7.4 below:

Program listing 7.4:

import java.util.Collections;

import java.util.Arrays;

public class ArraySorter

{

  public static void main(String[] args){

     String[] balls = {"Basket ball", "Base ball", "Volley Ball", "Foot ball" };

    System.out.println("\n A list of array balls' content before sorting -> \n");

    for(String ball : balls)

     System.out.println(ball);

    System.out.println("\n Array balls with 1st and 2nd contents sorted in ascending order ->\n");

 Arrays.parallelSort(balls,0,2);

    for(String ball : balls)

     System.out.println(ball);

System.out.println("\n Array balls contents sorted in ascending order with parallel sorting->\n");

 Arrays.parallelSort(balls);

    for(String ball : balls)

      System.out.println(ball);

  System.out.println("\n Array balls with 1st and 2nd contents sorted in descending order ->\n");

 Arrays.parallelSort(balls,0,2, Collections.reverseOrder());

    for(String ball : balls)

     System.out.println(ball); 

    System.out.println("\n Array balls contents sorted in descending order ->\n");

 Arrays.parallelSort(balls, Collections.reverseOrder());

     for(String ball : balls)

     System.out.println(ball);

  }

}

The output from program listing 7.4 above is as shown in figure 7.4 below:

run:

A list of array balls' content before sorting ->

Basket ball

Base ball

Volley Ball

Foot ball

Array balls with 1st and 2nd contents sorted in ascending order ->

Base ball

Basket ball

Volley Ball

Foot ball

Array balls contents sorted in ascending order with parallel sorting->

Base ball

Basket ball

Foot ball

Volley Ball

Array balls with 1st and 2nd contents sorted in descending order ->

Basket ball

Base ball

Foot ball

Volley Ball

Array balls contents sorted in descending order ->

Volley Ball

Foot ball

Basket ball

Base ball

BUILD SUCCESSFUL (total time: 0 seconds)

## 7.6 Array Copying

The content of one array can be copied into another of similar type through the usage of the “arraycopy( )” method of the java language package, which is included with your program by default and you do not need to import it. To illustrate this, program listing 7.3 is updated to include the copy method and listed as program listing 7.5 below:

Program listing 7.5:

import java.util.*;

public class ArraySorter

{

  public static void main(String[] args){

     String[] balls = {"Basket ball", "Base ball", "Volley Ball", "Foot ball" };

    System.out.println("\n A list of array balls' content before sorting -> \n");

    for(String ball : balls)

     System.out.println(ball);

    Arrays.sort(balls);

    System.out.println("\n A list of array balls' content after sorting ->\n");

    for(String ball : balls)

     System.out.println(ball);

   String[] ballsCopy = new String[balls.length];

 System.arraycopy(balls,0, ballsCopy,0, 2);

    System.out.println("\n A list of array ballsCopy's content after a copy operation ->\n");

    for(String ball : ballsCopy)

     System.out.println(ball);

  }

}

The output from program listing 7.5 is as shown in figure 7.5 below:

![](images/00024.jpeg)

Figure 7.5 Output from program listing 7.5.

The “arraycopy( )” method takes as its first argument the source array, as its second argument the starting position in the source array, as its third argument the destination array and as its fourth argument the number of elements to be copied. In program listing 7.5 above, the “arraycopy( )” method was supplied value 2 as the number of elements to be copied into array “ballsCopy” which has a length four, from array “balls” of equal length. Therefore, on listing out the content of array “ballsCopy” it gave out the last two slots value as nulls. The reason for this is that primitive memory addresses that have not been initialized with values are assigned null values by default by the compiler.

## 7.7 An ArrayList

An ArrayList in java performs basically the same functions as an array, but an ArrayList stores only a list of objects while an array can store both the primitive types and objects. An ArrayList does not have a fix length like an array does. Its size can be changed to accommodate new element addition and a deletion. The size method is used to retrieve its new length much like using the length field of the array class. More, the array belongs to the core java API, while the ArrayList class belongs in the java utility package (java.util.ArrayList) that must be imported before you can use the ArrayList class in your java programs. The declaration syntax for an ArrayList is as described below:

ArrayList array_name = new ArrayList( );

You can also use generics with ArrayList as described below:

ArrayList<data_type> array_name = new ArrayList<data_type>( );

For an example, you can define an ArrayList that can accept all string object types using generics like done below:

ArrayList<String> softDrinks = new ArrayList<String>( );

With this concept I can create an ArrayList that can store different objects from the same class or that inherited from the same parent class. For example, if I have a class named “customerNames” as defined below:

   class customerNames{

    String firstName, lastName;

    public customerNames(String firstNm, String lastNm){

    firstName = firstNm;

    lastName = lastNm;

    }

   String getFirstName( ){return firstName;}

   String getLastName( ){return lastName;}

}

I may declare the following customer objects:

customerNames customer1 = new customerNames("Feyisayo", "Dosunmu");

customerNames customer2 = new customerNames("Brian", "Tracy");

customerNames customer3 = new customerNames("Zig", "Ziglar");

customerNames customer4 = new customerNames("Ben", "Carson");

And then have them stored in an ArrayList for further processing with the following statement:

ArrayList<customerNames> customers = new

ArrayList<customerNames>(Arrays.asList(customer1,customer2,customer3, customer4));

This list of all customers first name can then be generated with following enhanced for loop:

for (customerNames t : customers)

System.out.printf("\n Index is %d for the element object %s ", customers.indexOf(t),t.getFirstName());

Everything is put together in program listing 7.6 below:

Program listing 7.6:

import java.util.*;

public class ArrayListObjs

{

  public static void main(String[] args){

  customerNames customer1 = new customerNames("Feyisayo", "Dosunmu");

  customerNames customer2 = new customerNames("Brian", "Tracy");

  customerNames customer3 = new customerNames("Zig", "Ziglar");

  customerNames customer4 = new customerNames("Ben", "Carson");

ArrayList<customerNames> customers = new ArrayList<customerNames>(Arrays.asList(customer1,customer2,customer3));

   for (customerNames t : customers)

     System.out.printf("\n Index is %d for the element object %s ",   customers.indexOf(t),t.getFirstName());

  }

}

   class customerNames{

    String firstName, lastName;

    public customerNames(String firstNm, String lastNm){

    firstName = firstNm;

    lastName = lastNm;

    }

   String getFirstName( ){return firstName;}

   String getLastName( ){return lastName;}

}

And the output of program listing 7.6 when executed is as shown in figure 7.6 below:

![](images/00025.jpeg)

Figure 7.6 The output of program listing 7.6 above.

Arraylists ensure type safety through the use of generics in their declarations.

## 7.8a ArrayList Assignment and Iteration with Enhanced for loop

Sure you can use the assignment operator to assign values to the elements of an array as earlier described, but you cannot do that with ArrayList, the add method of the ArrayList is used to insert new elements into the ArrayList object. Since the memory space for the element to be inserted is created dynamically on request as against the array which has all needed element slots already created and initialized to null values. The following statement adds an element to the “softDrinks” arraylist object:

softDrinks.add("Coca Cola");

You can also use the ArrayList’s “get()” method in combination with a “for loop” statement to retrieve the elements or contents of an ArrayList, the syntax of usage is as described below;

arraylist_object.get(element_index);

For example, to retrieve the first object in the arraylist “softDrinks”, the following statement is applicable:

softDrinks.get(0);

The object’s index can be retrieved with the method “indexof” of the arraylist class. This is used in combination with an enhanced for loop statement as shown in program listing 7.7 below:

Program listing 7.7:

import java.util.ArrayList;

public class ArrayListProg

{

  public static void main(String[] args){

        ArrayList<String> softDrinks = new ArrayList<String>( );

        softDrinks.add("Coca Cola");

      for (String t : softDrinks)

         System.out.printf("\n Index is %d for the element object %s ", softDrinks.indexOf(t),t);

  }

}

The output of program listing 7.7 is shown in figure 7.7 below:

![](images/00026.jpeg)

Figure 7.7\. The output from program listing 7.7\.

Program listing 7.7 used the “printf” method to print out the program’s output to the standard output device. The “printf” method uses the character formats “%d” for integer data, “%f” for floating point number, and “%s” for strings in its message string to represent the parameter to be substituted in the message string as done in program listing 7.7 above.

## 7.8b ArrayList Iteration with Lambda

The inclusion of the Collections package and the stream method as earlier stated in section 4.5 of chapter 4 in this book has made the processing of collections in java8 a lot simpler and faster for the underlying hardware. To illustrate this, program listing 7.7 above is modified to use the foreach functional statement in iterating through the contents of the “softDrinks” ArrayList by replacing the enhanced for loop with the lambda’s foreach statement. This modification is presented as program listing 7.8 below. Please enjoy.

Program listing 7.8:

import java.util.ArrayList;

import java.util.Collections;

public class ArrayListLambda

{

  public static void main(String[] args){

       ArrayList<String> softDrinks = new ArrayList<String>( );

       softDrinks.add("Coca Cola");

    /* Enhanced for loop is commented out */

      //for (String t : softDrinks)

         //System.out.printf("\n Index is %d for the element object %s ", softDrinks.indexOf(t),t);

    /* The enhanced for loop is now replaced with the forEach loop */

 softDrinks.stream().forEach((t) -> {

        System.out.printf("\n Index is %d for the element object %s \n", softDrinks.indexOf(t),t);

       });

  }

}

And the output from the program listing is as shown in figure 7.8 below:

![](images/00027.jpeg)

Figure 7.8\. The output from program listing 7.8 above.

## 7.9 Deleting Array list’s Object Elements

All objects element can be deleted from an ArrayList with the use of the ArrayList’s class method “clear()”. The syntax of usage is as described below:

arraylist_object.clear( );

For example, to delete all object elements from the arraylist “softDrinks” use the following statement:

softDrinks.clear( );

And to delete a particular object element from an arraylist, the following syntax is applicable:

arraylist_object.remove(object_element_index );

For example, to remove the first object element from the arraylist softDrinks, use the following statement:

softDrinks.remove(0);

## 7.10 The Iterator Interface:

The ArrayList class implements the iterator interface which has the following methods; next(), hasNext() and remove(). The next method returns the next object element in the arraylist. The hasNext() method checks to confirm that another object element is still available in the ArrayList, and the remove() method removes the current object from the list. To use the iterator interface in your java program you must import the Iterator class from the java utility package (java.util.Iterator) or all the classes in the utility package once and for all with the statement (java.util.*) as done in program listing 7.9 below:

Program listing 7.9:

import java.util.ArrayList;

import java.util.Iterator;

public class IteratorProg

{

  public static void main(String[] args){

       ArrayList<String> softDrinks = new ArrayList<String>( );

       String t;

       softDrinks.add("Coca Cola");

       softDrinks.add("Fanta");

       softDrinks.add("Pepsi");

       Iterator itr =  softDrinks.iterator( );

      while (itr.hasNext( )){

         t= (String) itr.next( );

         System.out.printf("\n Index is %d for the element object %s ", softDrinks.indexOf(t),t);

      }

  }

}

And the output from program listing 7.9 is shown in figure 7.9 below:

![](images/00028.jpeg)

Figure 7.8 Output from program listing 7.8.

Program listing 7.9 demonstrated the use of the Iterator interface by using the “hasNext()” method of the Iterator interface in the while loop expression to test for a non-empty list and then used the “next()” method to retrieve the next object element from the list. This brings us again to the end of another illumining chapter on java arrays. I hope you had a wonderful time as I had putting this chapter together. Please come with me to the next chapter for a shorter discussion on Strings.

# Chapter 8

# Strings and Regular Expressions

The string data type is an object in java programming language. A string is represented as an unlimited combination of characters within double quotes. For example “John” is a string literal. Now you can define the string variable “firstname” as pointing to the string literal “John” with the following statement:

String firstName = “John”;

Note that string content cannot be changed once assigned to a variable as done above, though the reference to the string can be changed to another in the variable. For example, when you try to modify the string variable firstName’s content to a new value “Johnson” by using the plus sign for string concatenation as shown below:

firstName = firstName + “son”;

When the compiler encounters such a statement as above, it uses its core API stringBuffer method “append()” to rewrite the statement as shown below:

firstName = new StringBuffer(firstName).append(“son”).toString();

and produce the output: Johnson

Similar process occur when you use string modifying methods like the “toLowerCase()” and the “trim()” string methods. We shall be discussing more on this in the following section. Array contents can also be converted to strings by the “toString()” Array class method. For example, you can display the contents of array balls on the standard output device with the following statement:

System.out.println(Arrays.toString(ballsCopy));

There are a number of available string class methods that shall be discussed about in the following section.

## 8.1 String Class Methods

The string class has many utility method such as the “length( )” method for returning the length of a string, “charAt(int)” for returning the character at a given position in a string, compareTo(string) for comparing two strings for similarity, returning an integer value 0 if the strings are similar, an integer value less than 0 if compared string comes before the supplied string argument and 1 if compared string comes after the supplied string argument to the method.

A similar method to the “compareTo(string)” method is the “compareToIgnoreCase(String)” the difference is that it carries out a case insensitive comparison. The “trim()” method removes leading and trailing spaces from a string and the “toLowerCase()” converts a string to the lowercase.Program listing 8.1 below illustrates the use of the string class methods.

Program listing 8.1:

import java.util.*;

public class StringMethods

{

  public static void main(String[] args){

  String name = "Feyisayo Dosunmu";

  String nameUpper = "FEYISAYO DOSUNMU";

  //Method length( ) returns a string's length

   System.out.printf("\n The lenght of name (name.length()) is %d ",name.length( ));

  //Method toLowerCase( ) returns a string's length

   System.out.printf("\n nameUpper in lowercases (name.toLowerCase()) is %s ",name.toLowerCase( ));

  //Method charAt(int) returns the character in the supplied position

   System.out.printf("\n The character in position 3 counting from 0 (name.CharAt(3)) is %c ",name.charAt(3));

  //Method compareTo(string) returns the result of Strings Comparison

   System.out.printf("\n The result of comparing  with (name.compareTo(nameUpper) ) is %d ",name.compareTo(nameUpper));

  //Method compareToIgnoreCase(string) returns the result of Strings Comparison

   System.out.printf("\n The result of comparing with (name.compareToIgnoreCase(nameUpper) ) is %d \n",name.compareToIgnoreCase(nameUpper));

  }

}

The output from program listing 8.1 is shown in figure 8.1 below:

![](images/00029.jpeg)

Figure 8.1 Output from program listing 8.1.

## 8.2 Regular Expressions

Regular expressions are string patterns that are created for the validation of program inputs. Though java provided some input checking methods like those provided by the Scanner class but this method are not that effective in most cases of input validation. For example, you may need to create your own method for validating a phone number or a particular security code number. Then you would need to create your own unique pattern for validating the users’ input and you do this with regular expressions.

## 8.3 Regular Expression Formulation

Regular expressions are formulated by using optional quantifiers and character combinations with implied meanings. The tables of some characters and quantifiers are as provided in figures 8.2 and 8.3 below:

| Regular expression character | Meaning |
| \d | Represents a numerical input and matches a single digit e.g 1 |
| \D | Represents a  non-numerical input and matches a single character input e.g. “a” |
| \w | Represents  a single alpha-numeric character and matches a single input in the ranges 0 – 9, a – z and A – Z including the underscore |
| /…/ | Encloses a regular expression pattern |
| […] | Represents a character set or a range |

Figure 8.2 A table of some regular expression characters and their meanings.

| Quantifiers | Meaning |
| ? | 0 or 1 or occurrence |
| * | 0 or more occurrence |
| + | 1 or more occurrence |

Figure 8.3 A table of regular expression quantifiers.

Now to create a regular expression pattern for validating a name input of unlimited character length that may begin with an upper or lower case letter, we take the following steps:

Step 1: Create a range for the set of upper case alphabetic letters from A to Z to represent the starting letter as done below:

[A –Z]

Step 2: Consider the right quantifier for the range. In this case the quantifier is the question mark, which represents a 0 or 1 occurrence. This is applicable since the name may or may not start with a capital letter. Therefore the new representation is as shown below:

[A – Z]?

Step 3: Create a range for the set of lower case letters as done below:

[a – z]

Step 4: Determine the quantifier for the created lower case letter range. In this case, since we may have an unlimited combination of lower case letters, the eligible quantifier would be the addition symbol (+) for one or more occurrences as shown below:

[a – z]+

Step 5: Now bring the starting letter and the following lower case combinational letters together to form a name regular expression as shown below:

[A-Z]?[a-z]+

Yeah, you’ve done it. You have a regular expression for validating a name input. But the process may not always be this simple, for example, it is not this simple to formulate a regular expression for valid email addresses, phone numbers for different regions of the world, master card numbers and so on. But these you should be able to do as a professional software developer.

I do not have to say that you need to be armed with the knowledge of regular expression formulation. A day is surely coming in your career that you would need it as a programmer, so it is better you understand the concepts now when it is not desperately needed, than to wait until it is desperately needed, and having to master the concept in a hurry. It’s sure not going to be as easy then (we prepare for war in times of peace).

However, this book cannot cover regular expression in full details as that would be clearly beyond its scope, as regular expression is a subject in its own right and deserves its own book. Therefore the author recommends that you download the book on regular expressions titled “[Regular Expressions; for beginners and advanced level programmers](http://www.amazon.co.uk/dp/B00U4VPZ5U).” Also by the author, for a deeper understanding of the subject. You can download this book from Amazon by clicking on the link or by typing the title into the search box in the kindle books store. Thank you as you do so.

## 8.4 Regular Expressions Application

The string class provides a “matches(string)” method that matches a string against a provided regular expression argument and returns a Boolean true if the string matches the regular expression or false if it does not. Next, program listing 8.4 uses our previously created name regular expression pattern created in section 8.3 above to validate a name input. Please enjoy.

Program listing 8.4:

import javax.swing.JOptionPane;

public class RegularExp

{

  public static void main(String[] args){

String nam = JOptionPane.showInputDialog("Please enter a name -> ");

  StringRegex name = new StringRegex(nam);

  if(name.validateName( ))

   System.out.println("\n You entered a valid name." );

  else

   System.out.println("\n You entered an invalid name.");     

  }

}

  class StringRegex{

    String namToValidate;

    public StringRegex(String n){

       namToValidate= n;

    }

    public StringRegex( ){

     namToValidate= " ";

    }

    boolean validateName( ){

       String RegPattern = "[A-Z]?[a-z]+";

 return namToValidate.matches(RegPattern);

    }

  }

The input and output of program listing 8.4 is shown in figure 8.4a and 8.4b below:

![](images/00030.jpeg)

Figure 8.4a Input pane with a name input for program listing 8.4.

![](images/00031.jpeg)

Figure 8.4b The output from program listing 8.4 above.

I want to thank you for being there once again as another chapter comes to an end. Things are getting better; from here on, we move on to a cooler level of exception handling, can’t wait to meet you there. Thanks for hanging on.

# Chapter 9

# Exception Handling

Exceptions are abnormal program flow interruptions that affect the smooth execution of computer programs. These disruptions are program errors that are undetectable by the compiler at compilation times but become mysteriously unavoidable at run times.

Some of these exceptions are the followings; FileNotFoundException- a file you wanted to open suddenly became unavailable due to a mysterious deletion operation or an unclosed disk drive; division by zero exception- when a divisor suddenly turn zero due to an illegal operation. To avoid these ugly and sometimes unavoidable situations the “try..catch” exception handling  statement structure was introduced to handle statement blocks that are at risk of generating exceptions.

## 9.1 The “try..catch” Statement Model

Programming exceptions are caught and handled within the “try..catch” statement block just like done in c++ and C#. The general syntax for a “try..catch” statement is as stated below:

try{

A statement block at risk of throwing an exception;

}

catch(Exception_type exception_obj){

  Exception handling statements;

}

finally{

  Statements to be executed after an exception or not;

}

The catch statement block handles a generated exception if any and the finally statement block contains a statement block that must be executed if there was an exception or not.

## 9.2 Benefits of Exception Handling

Benefits of using the “try..catch” statement structure is easily noticeable with the lack of need for the if statement in the handling of the caught exceptions; if there is a need to catch more exceptions all you need to do is provide more catch statement block to handle such previously uncaught exceptions. This is done as described below:

try{

A statement block at risk of throwing an exception;

}

catch(Exception_type exception_obj){

  Exception handling statements;

}

catch(Exception_type exception_obj2){

  Exception handling statements;

}

catch(Exception_type exception_obj3){

  Exception handling statements;

}

finally{

  Statements to be executed after an exception or not;

}

This naturally leads to a robust program design that enables readability and easy program maintainability.

The second benefit of using the “try..catch” statement structure is that you can determine at which level you want the caught exception to be handled; at the point of generation or higher up at the method calling level somewhere in the program. This is possible because exceptions do travel up the call stack starting from the point of generation up to the calling method until caught and handled by an exception handler.

If the programmer is interested in catching an exception at the method calling level, he or she would write the calling statement within a “try..catch” statement and the method must be declared with the throws clause, where a throw clause is the throws keyword  followed by the exception type, for example;

                       throws ArrayIndexOutOfBoundsException

Throws an “ArrayIndexOutOfBoundException” if the method tries to process non-existing location in an array as illustrated in program listing 9.1 below:

Program listing 9.1:

import javax.swing.JOptionPane;

public class OutOfBoundExceptn

{

  public static void main(String[] args){

     House sheraton = new House( );

 try{

String roomNum = JOptionPane.showInputDialog("Please enter a room number of interest -> ");

     int room = Integer.parseInt(roomNum) % 10;

     int floor = (Integer.parseInt(roomNum) - room) / 10;

 int vacancy = sheraton.isVacant(floor,room);

     if(vacancy == 0)

        System.out.printf("\n room is vacant.");

     else

        System.out.printf("\n room is not vacant.");

 }

 catch(ArrayIndexOutOfBoundsException e){

       System.out.printf("\n Room out of bound.");

 }

  }

}

class House{

  private int[][] rooms = new int[2][10];

   void House( ){

     for(int floor=0; floor < rooms.length; ++floor)

      for(int room_no=0; room_no < 10; ++room_no)

        rooms[floor][room_no] = 0;

   }

 int isVacant(int floor, int room) throws ArrayIndexOutOfBoundsException{

   return rooms[floor][room];

  }

}

The input and output of program listing 9.1 above is listed in figures 9.1a and 9.1b below:

![](images/00032.jpeg)

Figure 9.1a Input into program listing 9.1.

![](images/00033.jpeg)

Figure 9.1b The output from program listing 9.1\.

Program listing 9.1 reserves twenty rooms in a two story building of just one floor. The ground floor rooms started from room 0 as to room 9, and the first floor started from room 10 to room 19\. When a user enters any room number outside of the range 0 to 19 the user shall be accessing a location outside of the array boundary. This will surely generate an “ArrayIndexOutOfBounds” exception as we have witnessed in this instance. 

## 9.3 Catching Two or More Exceptions in a Catch Statement

Java 7 makes it possible to catch two or more exceptions with a catch statement. This is achieved by separating the exception types with vertical bars. The usage syntax is as described below:

try{

A statement block at risk of throwing an exception;

}

catch(Exception_type_1 | Exception_type_2  exception_obj){

  Exception handling statements;

}

finally{

  Statements to be executed after an exception or not;

}

For example, program listing 9.1 can also test for a division by zero mathematics exemption and get it reported all in one catch statement block as done by an updated version program listing 9.2 below:

Program listing 9.2:

import javax.swing.JOptionPane;

public class TwoExceptions

{

  public static void main(String[] args){

     House sheraton = new House( );

try{

     String roomNum = JOptionPane.showInputDialog("Please enter a room number of interest -> ");

     int room = Integer.parseInt(roomNum) % 10;

 int floor = (Integer.parseInt(roomNum) - room) / 0;

     int vacancy = sheraton.isVacant(floor,room);

     if(vacancy == 0)

        System.out.printf("\n room is vacant.");

     else

        System.out.printf("\n room is not vacant.");

    }

    catch(ArrayIndexOutOfBoundsException | ArithmeticException e){

       System.out.printf("\n  %s", e);

    }

  }

}

class House{

  private int[][] rooms = new int[2][10];

   void House( ){

     for(int floor=0; floor < rooms.length; ++floor)

      for(int room_no=0; room_no < 10; ++room_no)

        rooms[floor][room_no] = 0;

   }

  int isVacant(int floor, int room) throws ArrayIndexOutOfBoundsException{

   return rooms[floor][room];

  }

}

The input and output from program listing 9.2 above are shown in figure 9.2a and 9.2b below:

![](images/00034.jpeg)

Figure 9.2a. The input into program listing 9.2 above.

![](images/00035.jpeg)

Figure 9.2b. The output from program listing 9.2 above.

The statement line;

int floor = (Integer.parseInt(roomNum) - room) / 0;

carried out a division by zero operation in program listing 9.2 above and therefore generated a division by zero exception, which was promptly handled by the catch statement;

catch(ArrayIndexOutOfBoundsException | ArithmeticException e)

which was written to handle another an addition exception (ArithmeticException) and everything was fine thereafter. If you do not know what exception type you are trying to catch simply use the parent class for all exceptions (Exception) and print out the object to know what type of exception you are dealing with. Remember polymorphism.

## 9.4 Exception Hierarchy

In summary all exceptions belong to the parent class “Throwable” and there are two sub classes of class “Throwable”; the “Error” and the “Exception” classes. The “Error” type object when created in our program make our programs report error messages, with the compiler refusing to compile the program. Whereas when an “Exception” object is encountered in our programs the program would still compile but would have a runtime error called exception.

We can provide for an exception and handled it as it occurs, but this is not compulsory but it makes a lot of sense to do so. One thing you should note is that all subclasses of “Exceptions” class have the suffix Exception and all sub classes of class “Error” have the suffix “Error. And always remember that if you do not know what particular exception you are trying to catch, you can use the parent class of all exceptions “Exception” and print out the object to know what exception it is. Good luck. 

This brings us to the end of another interesting chapter and I hope that you also found it interesting. Next we move on to a higher ground of XML (Extensible Markup Language), where all barriers of communications between various computing platforms are broken. Please have a break and let’s go there.

# Chapter 10

# XML Processing

I am happy to introduce you to the world of creativity and opportunities, the world of XML that promises to deliver to us a web of meanings instead of the web of data that is currently being celebrated. You would agree with me that we deserve more from the web.

[XML](http://www.amazon.co.uk/dp/B00XRRB2TG) stands for Extensible Markup Language much like [HTML](http://www.amazon.co.uk/dp/B00PIMD5P2) stands for Hypertext Markup Language. It can be described as a logically structured data. Actually XML was supposed to be an improvement on HTML but ended up complimenting it. Today the two web development technologies are inseparable and indispensable when interested in building truly dynamic websites.

Yes, as a java programmer and as a professional software developer, demands are going to be made of you for the delivery of dynamic and reliable websites- websites that would process heavy data in secured and efficient manners. You would be requested to develop applications that can communicate with other applications that are developed in other programming languages and running on different platforms. The knowledge of xml technology would help you do that and more.  Now what do you think you can do without the knowledge of XML?

Not to worry, this chapter would show you how to create an xml document from your output data and how to receive one into your applications, but beyond this, it will be beyond the scope of this book to explain xml in full details that you require to be able to produce truly professional websites that can process dynamic data, as xml technology is a fully developed technology and deserves a book of its own.

In order to make this easy for you as an xml master myself, I have prepared a book for your easy comprehension, and you can download it from Amazon kindle book store by clicking on this title: “[XML; Extensible Markup Language (Simplified)](http://www.amazon.co.uk/dp/B00XRRB2TG)“ or by copying the title into the search box.

## 10.1 Creating XML with Java

Xml can be created in java either with DOM or with String. If you need to create xml documents that can be consumed by other applications or that need to conform to a particular schema then you need to create your xml document with the DOM (Document Object Model). But if you just want to create an xml document for the fun of creating one, using the String approach is okay. However, since we are interested in creating professional xml documents that can be consumed by other applications from varying platforms we shall be focusing on the production of xml documents through the DOM.

To create an xml document we would need a data source. The data source may be a database, an array or a program output. Our data source shall be an ArrayList for now as it can be made to hold record objects. For example, program listing 10.1 shows an ArrayList of drink objects. 

Program listing 10.1:

package xmlapplication2;

import java.util.ArrayList;

import java.util.Arrays;

/**

*

* @author Dosunmu

*/

public class DrinksRecord {

    /**

     * @param args the command line arguments

     */

    public static void main(String[] args) {

        Drinks soda1 = new Drinks("CocaCola",0.32,"Soft drink");

        Drinks soda2 = new Drinks("Fanta   ",0.32,"Soft drink");

        Drinks soda3 = new Drinks("Pepsi   ",0.32,"Soft drink");

        Drinks soda4 = new Drinks("Limca   ",0.30,"Soft drink");

//Creating a record of soft drinks with an array list

ArrayList<Drinks> softDrinks = new ArrayList<Drinks>(Arrays.asList(soda1,soda2,soda3,soda4));

//Printing out the drinks record       

System.out.println("Drink Name   Drink Type     Price");

        for(Drinks d: softDrinks){

            System.out.println(d.drinkName+ "     " +d.drinkType +"      " + d.drinkPrice);

        }

    }

}

   class Drinks{

    String drinkName, drinkType;

    Double drinkPrice;

    public Drinks(String drinkNm, double Prc,String type){

    drinkName = drinkNm;

    drinkPrice = Prc;

    drinkType = type;

    }

   String getDrinkName(){return drinkName;}

   String getDrinkType(){return drinkType;}

   double getDrinkPrice(){return drinkPrice;}

}

And the output from program listing 10.1 above is shown in the figure 10.1 below:

run:

Drink Name   Drink Type     Price

CocaCola       Soft drink      0.32

Fanta            Soft drink      0.32

Pepsi             Soft drink      0.32

Limca            Soft drink      0.3

BUILD SUCCESSFUL (total time: 1 second)

Figure 10.1\. The output of program listing 10.1 above.

The data has been arranged in a table format like in a database table good for data base processing operation with [SQL (Structured Query Language for Relational Database Management Systems)](http://www.amazon.co.uk/dp/B00UI3KF9K). However, our next challenge is to organize this data in a logical way and by so doing making the data independent of any database or programming applications for easy sharing and process communication. This is done by converting the contents of ArrayList softDrinks to an xml document. Program listing 10.2 improved on program listing 10.1 by converting the ArrayList softDrinks to an xml document using the DOM object.

Program listing 10.2:

package xmlapplication;

/**

*

* @author Dosunmu

*/

import java.io.FileNotFoundException;

import java.io.StringWriter;

import java.io.IOException;

import java.io.FileOutputStream;

import java.io.File;

import org.w3c.dom.Element;

import org.w3c.dom.Text;

import org.w3c.dom.Document;

import javax.xml.transform.stream.StreamResult;

import javax.xml.transform.Transformer;

import javax.xml.transform.TransformerException;

import javax.xml.transform.TransformerConfigurationException;

import javax.xml.transform.OutputKeys;

import javax.xml.transform.TransformerFactory;

import javax.xml.transform.dom.DOMSource;

import javax.xml.parsers.ParserConfigurationException;

import javax.xml.parsers.DocumentBuilder;

import javax.xml.parsers.DocumentBuilderFactory;

import java.util.ArrayList;

import java.util.Arrays;

import java.util.Iterator;

public class XmlWDom {

    /**

     * @param args the command line arguments

     */

    public static void main(String[] args) {

        //creating softdrinks objects

        Drinks soda1 = new Drinks("CocaCola",0.32,"Soft drink");

        Drinks soda2 = new Drinks("Fanta",0.32,"Soft drink");

        Drinks soda3 = new Drinks("Pepsi",0.32,"Soft drink");

        Drinks soda4 = new Drinks("Limca",0.30,"Soft drink");

        //Creating a record of softdrinks with an array list

ArrayList<Drinks> softDrinks = new ArrayList<Drinks>(Arrays.asList(soda1,soda2,soda3,soda4));

//Creating an xml document from the softDrinks arraylist record

        CreateXmlDoc xmldoc = new CreateXmlDoc();

        Document myXml = xmldoc.createEmptyXmlDoc( );

       //Creating an xml document by adding elements and attributes to the empty xml document

        CreateXML xmlDocument = new CreateXML();

        xmlDocument.createXmlEleAndAttrs(myXml, softDrinks);

        //Creating a representation of the xml doc in string

        XmlConverter converter = new XmlConverter();

        String xmlRepresentation = converter.ConvertXmlToString(myXml);

        //Write xml representation to the standard output

        System.out.println(xmlRepresentation);

        //Write xml representation to a folder

        XmlWriter xmlWriter = new XmlWriter();

        xmlWriter.FileXml(xmlRepresentation);

    }

}

class CreateXmlDoc{

Document createEmptyXmlDoc( ){

Document xmlDoc = null;

try{

  DocumentBuilderFactory myDocFactory = DocumentBuilderFactory.newInstance();

  DocumentBuilder myDocBuilder= myDocFactory.newDocumentBuilder();

  xmlDoc= myDocBuilder.newDocument();

  xmlDoc.setXmlStandalone(true);

}

catch(ParserConfigurationException e ){

  System.out.println("Enable to create a document bulider");

  System.exit(2);

}

return xmlDoc;

}

}

   class Drinks{

    String drinkName, drinkType;

    Double drinkPrice;

    public Drinks(String drinkNm, double Prc,String type){

    drinkName = drinkNm;

    drinkPrice = Prc;

    drinkType = type;

    }

   String getDrinkName(){return drinkName;}

   String getDrinkType(){return drinkType;}

   double getDrinkPrice(){return drinkPrice;}

}

class CreateXML{

    void createXmlEleAndAttrs(Document myDoc, ArrayList myDrinks){

      //Creating the root eleement

       Element softDrink  = myDoc.createElement("Soft_Drinks");

       softDrink.setAttribute("type","soft_drink");

       //Adding root element to the empty document myDoc

       myDoc.appendChild(softDrink);

       //Creating child elements for the root element

        Iterator itr =  myDrinks.iterator( );

        Drinks p;

        while (itr.hasNext( )){

         p= (Drinks) itr.next( );

         Element drink = myDoc.createElement("Drink");

          Element name = myDoc.createElement("Name");

          Text drinkText = myDoc.createTextNode(p.getDrinkName());

          name.appendChild(drinkText);

          //append element name to element drink as a child element

          drink.appendChild(name);

          //Build the second element price

          Element price =  myDoc.createElement("Price");

           //Converts price to string because all nodes in xml are basically strings

          Text priceText = myDoc.createTextNode(Double.toString(p.getDrinkPrice()));

          price.appendChild(priceText);

          //append element price to element drink as a child element

          drink.appendChild(price);

          //Append element drink to the root element SoftDrink

          softDrink.appendChild(drink);

        }

       }

    }

class XmlConverter{

String ConvertXmlToString(Document myXml){

  //Transforming Dom to String

     Transformer transformingObj= null;

     StringWriter writeStringXml = new StringWriter();

     try{

      TransformerFactory transformingFactory = TransformerFactory.newInstance();

      transformingObj= transformingFactory.newTransformer();

      transformingObj.setOutputProperty(OutputKeys.OMIT_XML_DECLARATION, "no");

      transformingObj.setOutputProperty(OutputKeys.INDENT, "yes");

      //Pass the xml into a string

      StreamResult outputXml = new StreamResult(writeStringXml);

      DOMSource xmlSource = new DOMSource(myXml);

      transformingObj.transform(xmlSource,outputXml);

     }

     catch(TransformerConfigurationException e){

         System.out.println("Unable to create a tranformer");

         System.exit(1);

     }

     catch(TransformerException  e){

         System.out.println("Unable to covert DOM to a string output");

         System.exit(1);

     }

     return(writeStringXml.toString());

}

}

class XmlWriter{

    void FileXml(String xmlrep){

       String path= "C:" +File.separator + "practice" + File.separator +"drinks.xml";

       try{

           File newOutput = new File(path);

           FileOutputStream newOutputStream = new FileOutputStream(newOutput,true);

           newOutputStream.write(xmlrep.getBytes());

           newOutputStream.close();

           System.out.println(path +" successfully written.");

       }

        catch(FileNotFoundException e){

          System.out.println(path + "not found.");

        }

       catch(IOException e){

          System.out.println(path + "Unwritable.");

        }

    }

}

The output of running from program listing 10.2 in NetBeans is as shown in figure 10.2 below:

run:

<?xml version="1.0" encoding="UTF-8"?>

<Soft_Drinks type="soft_drink">

<Drink>

  <Name>CocaCola</Name>

  <Price>0.32</Price>

</Drink>

<Drink>

  <Name>Fanta</Name>

  <Price>0.32</Price>

</Drink>

<Drink>

  <Name>Pepsi</Name>

  <Price>0.32</Price>

</Drink>

<Drink>

  <Name>Limca</Name>

  <Price>0.3</Price>

</Drink>

</Soft_Drinks>

C:\practice\drinks.xml successfully written.

BUILD SUCCESSFUL (total time: 0 seconds)

Figure 10.2\. The xml output from program listing 10.2 above.

Program listing 10.2 converted the structured data into a logical data representation in xml for an easy portability. To covert a data record to an xml document the main method took the following steps;

a) Created an empty xml document “myXml”

b) Added created elements and attributes to the empty “myXml” document in a logical manner

c) Created  a String representation of the created dom object “myXml” document by converting the “myXml” dom object to String

d) Wrote the String representation to the standard output

e) Also wrote the String representation to a file

These are the standard steps to take when writing an xml document with the DOM objects. Next we discuss how to read an xml document with java.

## 10.2 Reading XML with Java

XML documents can be read with the DOM or SAX in java. However the DOM requires that the whole document be read into the computer memory therefore it is memory intensive. While the SAX would only read an element into memory at a time and therefore uses less memory and can process any length of xml document. For this reason the SAX method is preferred and discussed in this book (considering book length and other factors).

The idea on which a SAX reader is developed is that SAX exposes an interface called contentHandler with some utility default methods like the startDocument(), startElement(), endElement() and endDocument() methods for triggering a start of document, a start of element, an end of element and an end of document event as the names of the methods implied. The methods are default implementations simply do nothing.

Therefore the contentHandler() interface must  be implemented and its necessary methods overridden to suit your purpose. This was done in program listing 10.3 by the class “Xmlhandler”. Next the reader object of the type “XmlReader” uses SAX and the “Xmlhandler” object to read the xml file content and print them to the standard output. It is really as simple as that. Please take your time to go through the program listing. The listing can be as short or as long as you desire depending on your purpose again.

Program listing 10.3 shows how to read the xml document (drinks.xml) created in program listing 10.2 with SAX above.

Program listing 10.3:

package xmlapplication3;

import javax.xml.parsers.SAXParser;

import javax.xml.parsers.ParserConfigurationException;

import javax.xml.parsers.SAXParserFactory;

import org.xml.sax.SAXException;

import org.xml.sax.Attributes;

import org.xml.sax.helpers.DefaultHandler;

import java.io.File;

import java.io.IOException;

/**

*

* @author Dosunmu

*/

public class XmlSaxReader {

    /**

     * @param args the command line arguments

     */

    public static void main(String[] args) {

        String xmlFile = "C:" + File.separator + "practice" + File.separator + "drinks.xml";

        XmlReader reader =new XmlReader();

        reader.readXmlContents(xmlFile);

    }

}

class Xmlhandler extends DefaultHandler{

   //Detect and handle the event of locating the start of the document

    int endingElementFlag;

    String elementName;

    void xmlhandler(){

        endingElementFlag = 0;

        elementName= null;

    }

    @Override

    public void startDocument(){

        System.out.println("Found the beginning of the document");

    }

    //Detect and handle the event of locating a starting element tag

   @Override

    public void startElement(String url,String lName,String eleName, Attributes attr)

            throws SAXException{

        endingElementFlag=0;

        elementName= eleName;

        StringBuilder content = new StringBuilder();

        content.append("A starting element tag " +"\"" +eleName +"\""+" is located");

        //Process elemeent's attributes if any

        if(attr.getLength() >0 ){

            content.append(" with the following attribute(s); ");

            for(int t=0; t < attr.getLength(); t++){

             content.append ( "\""+attr.getLocalName(t)+"\"");

             content.append(" with a value " +"\""+ attr.getValue(t)+"\""+"\n");

            }

        }

        //Print discovered element to the conseole

        System.out.println(content.toString());

    }

    //Processing the content of the element

    @Override

    public void characters(char[] ele_content, int start_position, int content_length)throws SAXException{

        String elemNm= new String(ele_content,start_position, content_length);

        if(endingElementFlag== 0 && (!(elementName.equalsIgnoreCase("Drink") ||(elementName.equalsIgnoreCase("Soft_Drinks"))) ) )

          System.out.println("with a content: " +"\"" + new String(ele_content,start_position, content_length)+"\"" );

    }

    //Detect and handle an element ending 

    @Override

    public void endElement  (String ele, String lName, String eleName)throws SAXException{

        endingElementFlag=1;

        System.out.println ("An ending Element tag " +"\"" + eleName + "\"" + " is found.\n ");

    }

    //Detect and handle a the document's ending

    @Override

    public void endDocument()throws SAXException{

        System.out.println("End of document reached.");

    }

}

class XmlReader{

    void readXmlContents(String xmlDoc){

        try{

            //create an xmlHanlder instance

            Xmlhandler xhandler = new Xmlhandler();

            //Create a parser factory instance

            SAXParserFactory sxFactory = SAXParserFactory.newInstance();

            // Create a parser using the parser factory instance

            SAXParser sxParser = sxFactory.newSAXParser();

            //Passing the xml file with the handler

            sxParser.parse(xmlDoc, xhandler);

        }

        catch(SAXException e){

           System.out.println("Could not parse the XML document-> "+ e.getMessage());

        }

        catch(IOException e){

           System.out.println("Could not open path."+xmlDoc);

        }

        catch(ParserConfigurationException e){

           System.out.println("Unable to create a parser-> " + e.getMessage());

        }

    }

}

And the output of program listing 10.3 above is a presented in figure 10.3 below:

Found the beginning of the document

A starting element tag "Soft_Drinks" is located with the following attribute(s); "type" with a value "soft_drink"

A starting element tag "Drink" is located

A starting element tag "Name" is located

with a content: "CocaCola"

An ending Element tag "Name" is found.

A starting element tag "Price" is located

with a content: "0.32"

An ending Element tag "Price" is found.

An ending Element tag "Drink" is found.

A starting element tag "Drink" is located

A starting element tag "Name" is located

with a content: "Fanta"

An ending Element tag "Name" is found.

A starting element tag "Price" is located

with a content: "0.32"

An ending Element tag "Price" is found.

An ending Element tag "Drink" is found.

A starting element tag "Drink" is located

A starting element tag "Name" is located

with a content: "Pepsi"

An ending Element tag "Name" is found.

A starting element tag "Price" is located

with a content: "0.32"

An ending Element tag "Price" is found.

An ending Element tag "Drink" is found.

A starting element tag "Drink" is located

A starting element tag "Name" is located

with a content: "Limca"

An ending Element tag "Name" is found.

A starting element tag "Price" is located

with a content: "0.3"

An ending Element tag "Price" is found.

An ending Element tag "Drink" is found.

An ending Element tag "Soft_Drinks" is found.

End of document reached.

BUILD SUCCESSFUL (total time: 2 seconds)

Figure 10.3\. The output from program listing 10.3 above.

We have come a long way truly. And I hope that you comprehend the program listings, if so congratulations. If not yet, take a little break to try again later. In the meantime, even if you have comprehended the listing I still like you to take a little break and have some inspirational tonic at this point by downloading this title: “[Best Inspirational Quotes for Success; a subject by subject inspiration for life.](http://www.amazon.co.uk/dp/B00OBDHMSA)” from the likes of Theodore Roosevelt, Jack Canfield, Mother Teresa, Zig Ziglar, Henry Ford, Abraham Lincoln, Ben Carson and so many lion hearts.

Believe me you will always need this success quotes to keep you going when things get tough as it often does in the world of programming. So I have compiled these for you to also help make you a psychologically sound programmer. Just keep holding on and you will soon see the light. Thank you once again for the effort and determination.

# Chapter 11

# Java Applets

Applets are mainly used for animations and game creations. They are embedded in hypertext markup language documents. Therefore you need a foundational knowledge of [HTML5](http://www.amazon.co.uk/dp/B00PIMD5P2) to use applets. The basic structure of an HTML5 document is as described in listing 11.1 below:

Listing 11.1:

<!DOCTYPE html>

<html>

<head>

<title> My First HTML5 Web Page </title>

<meta charset="UTF-8">

</head>

<body>

    <header ><em ><u> MY APPLET PROJECT.</u></em><br/> </header>

    <nav><a href="#">Home</a> |<a href="#">Exit</a>  </nav><br/><br/>

    <header ><i> My Applet Image Section</i> </header><br/>

    <section id=”image_applet”>

    </section><br/>

    <footer> &copy copyright August 2015</footer>

</body>

</html>

The “<!DOCTYPE html>” element describes the document as a HTML5 document to the browser. The “<html>” element acts as the parent container for the html document. The “<head>” element acts as the head of the document containing the followings; “<title>” element for displaying the document’s title in the web browser, the character encoding for the page described in the “<meta >” element tag, and the in some cases the page style sheet- included by the “<style>” element.

After the head element comes the “<body>” element which contains the body of the html document that includes the “<header>” elements for displaying the various sections’ titles enclosed in “<section>” elements across the page, the page footer element for displaying footer information like the copyright and the address information, and various other minor text editing elements like the “<br/>” singleton element for inserting new lines, <u> element for text underlining, <em> element for creating emphatic texts. The major elements must be in the order described or you end up with a malformed html document.

When you save listing 11.1 in a text document with an extension “.html” and as type “ALL Files”. You can double click the file to have it displayed in your browser as shown in figure 11.1 below:

![](images/00036.jpeg)

Figure 11.1\. The output of program listing 11.1 above.

Sure this is just a basic html5 web page devoid of any [CSS](http://www.amazon.co.uk/dp/B00QZ2S2JI) styling, though sufficient for our discussion in this chapter. I recommend that you download the book titled “[HTML5; simplified beginners to intermediate level](http://www.amazon.co.uk/dp/B00PIMD5P2)”, if you are not already familiar with html or has not upgraded to the new html5 for a serious applet web development project, and the book titled “[CSS3; CSS2 and 3 from beginners’ level up (Two in one)](http://www.amazon.co.uk/dp/B00QZ2S2JI)” for html page outlaying and styling for a professional looking web page. Both from amazon kindle book store, by clicking on the links or by typing the book titles into the search box.  Thank you as you do so.

## 11.1 The Applet Element

An applet is embedded into an html document with the applet element. The applet element is as described below:

<applet code=”applet.class” width=200 height=100 > </applet>

The code attribute specifies the applet byte code (applet class) gotten by compiling the applet source file while the width and height set the width and height of the applet. The applet is compiled in the same way as a java application is compiled with the “javac” command after which it can be run with the “appletviewer” command. And if your applet would require some parameters, the parameter can be gotten from the web page with the “param” element as shown below:

<applet code=”applet.class” width=200 height=100 >

<param name=sex value=”Male” >

</applet>

The “param” element’s attribute “name” is used for specifying the name of the parameter, while the attribute “value” is used for supplying the parameter’s value. 

## 11.2 An Applet’s Structure

An applet does not have a static public main method common to java applications, instead what it has is the public “init()” method which initializes the applet upon starting. Java applets have no need of a required method. The methods are invoked by the browser as required by the java virtual machine. The following methods of the Applet class (that extends the Panel class) are important for the implementation of an applet.

a) public void init(): Used by the web browser for applet initializations

b) pubic void start(): Used by the web browser for starting the applet after initialization. Called as many times as the embedding page is loaded

c) public void stop(): Invoked by the web browser to stop an applet whenever the embedding page is minimized, the user browses away, or the applet is stopped

d) public void destroy(): The destroy method is invoked by the web browser to destroy the applet by clearing it out of its memory

The containing Applet class for the above listed methods must be imported for your applets to be able to use them. The containing Applet’s class hierarchy is as described in figure 11.2 below:

![](images/00037.jpeg)

Figure 11.2\. The Applet’s class inheritance hierarchy tree.

According to the hierarchical Applet’s family tree, the class applet inherited from its parent class Panel which inherited from its parent class Container also inheriting from the parent class Component which inherited from the mother of all classes, the Object class. Thus the Applet class is seriously enriched. However, there is still an important method not of the applet class’s hierarchy; the public void paint( ) method of the java.awt.Grahphics class, used for painting the applet in the browser. Without you overriding these methods the applet does nothing as the default behavior is to do nothing. Next let’s create an example applet that overrides the utility applet’s paint(Graphics )  method.

## 11.3 An Example Applet

The following example applet in program listing 11.2 below displays the current time in the embedding web page when started by the browser.

Program listing 11.2:

import java.applet.Applet;

import java.awt.Graphics;

import java.time.LocalTime;

/**

*

* @author Dosunmu

*/

public class LocalTimeApplet extends Applet {

    /**

     * Initialization method that will be called after the applet is loaded into

     * the browser.

     */

    @Override

    public void init() {

        // TODO start asynchronous download of heavy resources

    }

    @Override

    public void paint(Graphics t){

      t.drawString("The time is " + LocalTime.now(), 100,90); 

    }

    // No need to overwrite start(), stop() and destroy() methods

}

There is no need to override the start(), stop() and destroy methods as the browser will automatically invoke the default start() method when the applet comes into view in the browser, invoke the default stop() method when it goes out of view and invoke the default destroy() method when the page is remove from the browser.

The above applet can be compiled the same way a java code is compiled with the javac command or in netbeans for produce the byte codes which can then be embedded in a web document such as described in program listing 11.1 above. The embedding is done as described in the modified program listing 11.1 (11.3) below;

Program listing 11.3:

<!DOCTYPE html>

<html>

<head>

<title> My First HTML5 Web Page </title>

<meta charset="UTF-8">

</head>

<body>

    <header ><em ><u> MY APPLET PROJECT.</u></em><br/> </header>

    <nav><a href="#">Home</a> |<a href="#">Exit</a>  </nav><br/><br/>

    <header ><i> My Local Time Applet Section</i> </header><br/>

    <section id=”Local Time_applet”>

 <applet code="LocalTimeApplet.class" width=300 height=100> </applet>

     </section><br/>

    <footer> &copy copyright August 2015</footer>

</body>

</html>

To run the applet at the command prompt use the “appletviewer” command to execute the html document as described in figure 11.3 below:

C:\practice>appletviewer LocalTimeApplet.htm

The output of the program listing when executed at the command prompt and even in Netbeans IDE is as shown in figure 11.3 below:

![](images/00038.jpeg)

Figure 11.3\. The output of program listing 11.2 (applet).

The Graphics class is mainly used for drawing objects to the system output devices. The following are the commonly used Graphics class methods:

a) public abstract void drawLine (int x, int y, int x2, int y2); for drawing a line from a point(x, y) to a point (x2, y2)

b) public abstract void drawImage(Image img, int x, int y, ImageObserver obs); for drawing an a given image to the output device

c) public abstract void drawArc(int x, int y, int width, int height, int startAngle, int arcAngle); for drawing an acr to the output device

d) public abstract drawOval(int x, int y, int width, int height); for drawing an oval shape to the output device

e) public abstract void drawRect(int x, int y, int width, int height); for drawing and outputting a rectangle to the output device

f) public abstract void drawstring(String str, int x, int y); for outputting a string to the output device

g) public abstract void fillArc(int x, int y, int width, int height, int startAngle, int arcAngle); for filling a drawn arc with a set color

h) public abstract void fillOval(int x, int y, int width, int height); for filling a drawn oval shape with a set color

i) public abstract void fillRect(int x, int y, int width, int height); use for filling a drawn rectangle with a set color

j) public abstract void setColor(Color c); use for setting graphic current filling color

For example, the following applet code in program listing 11.3 below is responsible for drawing a rectangular object filled with color pink to the output device with the use of the Graphics and the Color class.

Program listing 11.3:

import java.applet.Applet;

import java.awt.Color;

import java.awt.Graphics;

/**

*

* @author Dosunmu

*/

public class FilledRectangle extends Applet {

    /**

     * Initialization method that will be called after the applet is loaded into

     * the browser.

     */

    @Override

    public void init() {

        // TODO start asynchronous download of heavy resources

    }

    @Override

    public void paint(Graphics p){

      p.setColor(Color.pink);

      p.drawRect(140, 70, 45, 60); 

      p.fillRect(140, 70, 45, 60);

    }

}

The output of program listing 11.3 is as shown in figure 11.4 below:

![](images/00039.jpeg)

Figure 11.4\. The output from program listing 11.3 above.

However, applets have their own short comings and limitations which are as listed:

a) They require plugins to be able to execute in the client browser

b) The browser security setting may forbid your applet from executing

Still with these, applets also have their own advantages in the sense that they are more secure, faster because they execute on the client side and can run on varieties of platforms once the java runtime environment is installed.

In conclusion applets are not the best way to building great websites and user experiences, servlets make better promises when it gets to that level. From here on, you can easily understand any other advance book you pick up on java 8 programming and servlet development as I shall have to come to a stop here in as much as I love to continue writing on. I may include the treatment of servlet and database manipulation in the next series of this book if the demand requires them.

I know you have a reason for downloading this book in the first instance, in the first instance I hope that the purpose is met, and in the second instance a motivating purpose that brought you to this end, which may be that you have an impending project, or that you are in the middle of one. If this is the reason, I suggest that you also download another of my highly recommended book titled [“Literature Review Writing; a simplified approach.](http://www.amazon.co.uk/dp/B00OG1YACS)” It will simplify your project for you a great deal; more it is going to be a treasure for your keeping. Thank you.

# Conclusion

We started from the very simple of java development concept to the most advanced and ever useful XML technology to the latest java 8 additions. Though you may be a beginner but our experience in software development with God on our side have made this book a possibility.

If you have been blessed one way or the other no matter how little, please also contribute your own little quota by giving your own review of appreciation for this work, so others may also find this book and benefit from it. You can give your five star reviews by simply moving to the review page of this book. You will get there if you keep moving on. Thank you for your review.

Before I take my leave, how about a little distraction, afterall all work and no play, they say makes Jack a dull boy. Now enjoy the rest of the day with this little treasure:

[![](images/00040.jpeg)](http://www.amazon.co.uk/dp/B00ZFVZ0K4)

Learn to make beautiful gift boxes and present your gifts in your heart desired way in style by downloading the above book. Till will meet again, lots of thanks and keep safe. Bye for now.