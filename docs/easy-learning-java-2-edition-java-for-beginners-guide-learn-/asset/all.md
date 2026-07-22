![](Image00169.jpg)

Easy Learning

Java

(2 Edition)

![](Image00000.jpg)

YANG HU

Simple is the beginning of wisdom. This book briefly explain the concept and vividly cultivate programming interest, this book fast learn Java object-oriented programming.

[http://en.verejava.com](http://en.verejava.com)

Copyright © 2020 Yang Hu

All rights reserved.

ISBN : 9798634831589

CONTENTS

1. [Java JDK Installation](#text00001.html_Java_JDK_installation)

2. [Set Java Environment Variables](#text00007.html_Set_Java_Environment_Variables)

3. [The First Java Program](#text00015.html_The_First_Java_Program)

4. [Basic Concepts of Java](#text00024.html_Variable)

    4.1 [Variable](#text00024.html_Variable)

    4.2 [Basic Data Types](#text00027.html_Basic_data_types)

    4.3 [Constant](#text00030.html_constant)

    4.4 [Type Casting](#text00031.html_Data_Type_Conversion)

5. [Operator](#text00035.html_Arithmetic_operator)

    5.1 [Arithmetic Operator](#text00035.html_Arithmetic_operator)

    5.2 [Method](#text00036.html_Method)

    5.3 [Class](#text00039.html_Class2)

    5.4 [Package](#text00041.html_Package)[](#text00039.html_Class2)

    5.5 [Increment and Decrement](#text00043.html_Increment_and_Decrement)

[](#text00043.html_Increment_and_Decrement)    5.6 [Relational Operator](#text00044.html_Relational_operator2)

    5.7 [Logical Operators](#text00045.html_Logical_Operators)

6. [Statements](#text00047.html_If_Conditional_Statement)

    6.1 [If](#text00047.html_If_Conditional_Statement)

    6.2 [Switch](#text00049.html_Switch_statement)

    6.3 [While Loop](#text00051.html_While_loop_statement)

    6.4 [Do While Loop](#text00052.html_Do_While_Loop)

    6.5 [While Loop Games](#text00053.html_While_Loop_Games)

    6.6 [For Loop](#text00055.html_For_loop_statement)

    6.7 [Continue and Break](#text00057.html_Continue_and_Break)

7. [Java Array](#text00058.html_One_dimensional_array)

    7.1 [One-Dimensional Array](#text00058.html_One_dimensional_array)

    7.2 [Two-Dimensional Array](#text00060.html_Two_Dimensional_Array)

8. [Java Object-Oriented](#text00062.html_Class3)

    8.1 [Class](#text00062.html_Class3)

    8.2 [Encapsulation](#text00063.html_Methods_Encapsulation)

    8.3 [Constructor Method](#text00065.html_Construction_method)

    8.4 [Method Overload](#text00067.html_Method_overload)

    8.5 [Static Keyword](#text00069.html_Static_keyword)

    8.6 [Inheritance](#text00072.html_Inheritance)

    8.7 [Method Override](#text00075.html_Method_Override)

    8.8 [Super Keyword](#text00077.html_Super_Keyword)

    8.9 [Polymorphism](#text00078.html_Polymorphism)

    8.10 [Object Relationship One-to-One](#text00080.html_Object_Relationship_One_to_One)

    8.11 [Abstract Class](#text00081.html_Abstract_class)

    8.12 [Interface](#text00084.html_Interface)

    8.13 [Enum](#text00088.html_Enum_enumerated_type)

    8.14 [Internal Class](#text00090.html_Internal_class)

9. [IDE Eclipse Installation](#text00092.html_IDE_Eclipse_Installation)

10. [String](#text00105.html_String_Operation)

11. [Primitive Types and Wrapper Classes](#text00111.html_Wrapper_Classes)

12. [Object](#text00113.html_Object)

13. [Collection](#text00115.html_List_and_ArrayList)

    13.1 [ArrayList](#text00115.html_List_and_ArrayList)

    13.2 [LinkedList](#text00119.html_LinkedList)

    13.3 [Iterator](#text00122.html_Iterator)

    13.4 [HashSet](#text00123.html_HashSet)

    13.5 [HashMap](#text00124.html_Map_HashMap_Hashtable)

    13.6 [Generic](#text00126.html_Generic)

    13.7 [Random](#text00129.html_Random)

14. [Exception](#text00131.html_Exception)

15. [File IO](#text00134.html_File2)

    15.1 [File](#text00134.html_File2)

    15.2 [FileInputStream](#text00138.html_FileInputStream_Reads_File)

    15.3 [FileOutputStream](#text00141.html_FileOutputStream_writes_to_file)

16. [Java Thread](#text00142.html_Java_Thread)

17. [Canvas](#text00145.html_Java_GUI_Window_Application)

[](#text00145.html_Java_GUI_Window_Application)    17.1 [Create GUI Window Application](#text00145.html_Java_GUI_Window_Application)

[](#text00145.html_Java_GUI_Window_Application)    17.2 [Create Canvas](#text00146.html_Create_Canvas2)

[](#text00146.html_Create_Canvas2)    17.3 [Graphics Draw on Canvas](#text00148.html_Graphics_Draw_on_Canvas)

[](#text00148.html_Graphics_Draw_on_Canvas)18. [Animation](#text00155.html_Animation)

[](#text00155.html_Animation)19. [Airplane Game](#text00166.html_Airplane_GUI_Game)

[](#text00166.html_Airplane_GUI_Game)

Java JDK Installation

Java: is an object-oriented programming language that produces software for multiple platforms. When a programmer writes a Java application, the compiled code (known as bytecode) runs on most operating systems (OS), including Windows, Linux and Mac OS.

JDK(Java Development Kit ): is a software development environment that offers a collection of tools and libraries necessary for developing Java applications.

1\. Download the JDK ( Java development kit )

    [https://java.com/en/download/](https://java.com/en/download/)

    or

    [http://en.verejava.com/download.jsp?id=1](http://en.verejava.com/download.jsp?id=1)

There are many JDK versions. We use jdk-8u91-windows-x64.zip as an example.

Open the link in Google Chrome Browser: [http://en.verejava.com/download.jsp?id=1](http://en.verejava.com/download.jsp?id=1)

![](Image00001.jpg)

2\. Install JDK ( Java development kit )

Unzip jdk-6u45-windows-i586.zip to jdk-6u45-windows-i586.exe

![](Image00002.jpg)

Double click jdk-6u45-windows-i586.exe start to install

![](Image00003.jpg)

Click Next Button

C:\Program Files\Java\jdk1.8.0_91\: is the path of installation

![](Image00004.jpg)

Click Next Button

Successfully Installed

![](Image00005.jpg)

Click Close Button

The structure of directory after JDK installation

![](Image00006.jpg)

Set Java Environment Variables

Environment variables: are global system variables accessible by all the processes/users running under the Operating System (OS), such as Windows, macOS and Linux.

for examples:

1\. Set Environment variables under Windows(OS)

    Right click: Computer -> Properties

    ![](Image00007.jpg)

Click: Advanced System Settings

  ![](Image00008.jpg)

Click: Advanced -> Environment Variables

![](Image00009.jpg)

Click the New Button to create 3 Environment Variables

![](Image00010.jpg)

1\. JAVA_HOME is an Environment Variable set to the location of the Java directory on your computer.

JAVA_HOME= C:\Program Files\Java\jdk1.8.0_91\

![](Image00011.jpg)

2\. CLASSPATH: is the path where to find the java class when java application executes.

CLASSPATH= %JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;.

![](Image00012.jpg)

![](Image00013.jpg)

3\. PATH : is used define where the system can find the executables(.exe) files and classpath is used to specify the location.

PATH= %JAVA_HOME%\bin

![](Image00014.jpg)

javac: compiles java code into bytecode class files.

java: run java bytecode class files.

![](Image00015.jpg)

The 3 Environment Variable is completed

![](Image00016.jpg)

Click Ok Button

The following figure indicates that the environment variables are successfully installed

Click Window Icon and then input cmd click cmd.exe to open command window

Input command:  java -version

![](Image00017.jpg)

The First Java Program

1\. Install Java Development tool

    There are many tools to develop java like:

        Text Editor: Notepad, Notepad++ etc.

        IDE:               NetBeans, IDEA, Eclipse etc.

If you are a beginner We would suggest using a Notepad/Notepad++ rather than an IDE.

the right time I feel to move on to using the IDEs is when you have learned sufficient knowledge and experience in Java.

Download Nodepad++.zip

[http://en.verejava.com/download.jsp?id=1](http://en.verejava.com/download.jsp?id=1)

Unzip Nodepad++.zip to Nodepad++

![](Image00018.jpg)

Double click npp.7.5.8.Installer.x64.exe to install.

![](Image00019.jpg)

Click Ok Button

Notepad++ installation successful

![](Image00020.jpg)

2\. The first java program steps:

    1\. Create a java file: Hello.java

| public class Hello {    public static void main ( String [] args ) {        System . out . println ( "I love Java" );    }} |

    2\. Open a command prompt window and go to the directory C:\java where you saved the java program ( Hello.java ).

    3\. Type ' javac Hello.java ' and press enter to compile Hello.java to Hello.class .

    4\. Type ' java Hello ' to run your program.

    You will be able to see the result: I love Java printed on the window.

![](Image00021.gif)

3\. Create and run the first java program by Nodepad++

1\. Create a java file: Hello.java by Nodepad++

![](Image00022.jpg)

Click Save Button

2\. Enter the code in Hello.java and then save again

System.out.println(): Print message to the console and then wrap a new line

| public class Hello {    public static void main ( String [] args ) {        System . out . println ( "I love Java" );    }} |

![](Image00023.jpg)

3\. Open a command prompt window and go to the directory C:\java where you saved the java program ( Hello.java ).

Type ' javac Hello.java ' and press enter to compile Hello.java to Hello.class .

![](Image00024.jpg)

4\. Type ' java Hello ' to run your program.

    You will be able to see the result: I love Java printed on the window.

![](Image00025.jpg)

The java program is executed from top to bottom and from left to right

4\. Explain in detail Hello.java

| public class Hello {    public static void main ( String [] args ) {        System . out . println ( "I love Java" );    }} |

the class definition block for the java application, every application begins with a class definition.

Hello is class name that the first letter need be capitalized, and the code for each class appears between the opening and closing curly braces { }

| public class Hello {} |

In the Java programming, every application must contain a main method.

The main method is the entry point for your application.

The main method accepts a single argument named: args that an array of String .

The code for each method appears between the opening and closing curly braces { }

|     public static void main ( String [] args ) {    } |

Uses the System class from the core library to print the "I love Java" message to standard output.

Core library (also known as the "Application Programming Interface", or "API")

|         System . out . println ( "I love Java" ); |

Just remember these concepts first and will discuss them in detail later

Variable

Variable: a memory area allocated by the system to store data.

   Example: Put "Apple" to basket

   basket is variable, "Apple" is a value assigned to basket

![](Image00026.jpg)

1\. Create a file in Nodepad++ : Variable.java save to directory c:\java

String: is a sequence of characters are surrounded by double quotes " "

              like: "Apple", "12345", "_name", "Keep going" etc.

| public class Variable {    public static void main(String[] args) {        String basket = "Apple" ;        System. out .println(basket);    }} |

Open cmd Window type "javac Variable.java" and then type "java Variable".

You will be able to see the result: Apple printed on the window.

![](Image00027.jpg)

2\. The value of the variable can be changed.

Replace the value of variable basket from "Apple" to "Orange"

![](Image00028.jpg)

Two forward slashes //: Single-line comments can be used to explain Java code, Any text between // and the end of the line is ignored by Java (will not be executed).

| public class Variable {    public static void main ( String [] args ) {        String basket = "Apple" ; // Put "Apple" to basket        System . out . println ( basket );        basket = "Orange" ; // Put "Orange" to replace "Apple"        System . out . println ( basket );    }} |

Open cmd Window type "javac Variable.java" and then type "java Variable" run again .

![](Image00029.jpg)

3\. Variable naming rules:

     1.consisting of characters, underscores, $, numbers.

     2.The first letter must be a character, _ or $, can not be a number.

     3.The first letter needs to be lowercase.

     4 . Cannot use a java keyword (reserved word) as a variable name.

    Example:

        Correct variable naming:    name , age , _salary , peopleColor etc

        Incorrect variable naming: 1234 , 2_name , a@mail, public, static etc

Create a file in Nodepad++ : Variable.java save to directory c:\java

| public class Variable {    public static void main ( String [] args ) {        String cup = "mineral water" ;        System . out . println ( cup );        String _bottle = "juice" ;        System . out . println ( _bottle );        String peopleColor = "white" ;        System . out . println ( peopleColor );    }} |

Open cmd Window type "javac Variable.java" and then type "java Variable".

![](Image00030.jpg)

Basic Data Types

Java has 8 basic data types ( Also called primitive types ).

    byte, short, int, long, float, double, char, boolean

The Category and parameters of each primitive types are as follows:

| Category | Types | Sizes(bit) |  |
| Integer | byte | 1 byte = 8 bits | 8 bits =-2^7~2^7-1 (-128~127) |
| short | 2 bytes=16 bits |  |
| int | 4 bytes = 32 bits |  |
| long | 8 bytes = 64 bits |  |
| Floating-Point | float | 4 bytes = 32 bits |  |
| double | 8 bytes = 64 bits |  |
| Character | char | 2 bytes = 16 bits |  |
| Boolean | boolean | 1 byte = 8 bits |  |

1\. Integer ( byte, short, int, long ).

Create a file in Nodepad++: DataType.java

| public class DataType {    public static void main ( String [] args ) {        byte a1 = 1 ;        short a2 = 10 ;        int a3 = 100 ;        long a4 = 1000 ;        System . out . println ( a1 );        System . out . println ( a2 );        System . out . println ( a3 );        System . out . println ( a4 );    }} |

Open cmd type "javac DataType.java" and then type "java DataType ". ![](Image00031.jpg)

2\. Floating-Point ( float double ).

During compilation, all floating point numbers default to double . Therefore, if you want it as float , you have to explicitly tell the compiler by adding a f or F at end of the numbers.

Create a file in Nodepad++: DataType.java

| public class DataType {    public static void main ( String [] args ) {        double b1 = 10.1 ;        float b2 = 12.2f ; // add a f or F at the end        System . out . println ( b1 );        System . out . println ( b2 );    }} |

Open cmd type "javac DataType.java" and then type "java DataType " . ![](Image00032.jpg)

3 . Character and Boolean ( char boolean ).

char: is a single character that enclosed in single quote marks, that is a letter 'a' , a digit '9' , a punctuation mark '!' , a tab '    ' , a space ' ' etc.

Escape Sequences : A character preceded by a backslash (\) is an escape sequence and has special meaning to the compiler.

| \t | Insert a tab in the text at this point. |
| \n | Insert a newline in the text at this point. |
| \' | Insert a single quote character in the text at this point. |
| \" | Insert a double quote character in the text at this point. |
| \\ | Insert a backslash character in the text at this point. |

boolean: boolean data type which can only take the values true or false .

| public class DataType {    public static void main ( String [] args ) {        char c1 = 'a' ;        char c2 = '9' ;        String str1 = "Good\tJob" ; // \t Insert a tab        String str2 = "Keep\nGoing" ; // \n Insert a newline        System . out . println ( c1 );        System . out . println ( c2 );        System . out . println ( str1 );        System . out . println ( str2 );        boolean d1 = true ;        boolean d2 = false ;        System . out . println ( d1 );        System . out . println ( d2 );    }} |

Open cmd type "javac DataType.java" and then type "java DataType " .

![](Image00033.jpg)

Constant

Constant: A constant whose value cannot change once it has been assigned.

    1\. the definition of a constant need be capitalized.

    2\. To define a constant, we just need to add the keyword final in front of the variable.

       final float PI = 3.14f ;

        the value of PI cannot change once it has been assigned

1. Create a file in Nodepad++: FinalVariable.java

| public class FinalVariable {    public static void main ( String [] args ) {        final int UP = 0 ;        final int DOWN = 1 ;        System . out . println ( UP );        System . out . println ( DOWN );        final float PI = 3.14f ;        System . out . println ( PI );        final boolean RUN = true ;        System . out . println ( RUN );    }} |

Open cmd type "javac FinalVariable.java" and then type "java FinalVariable " .

![](Image00034.jpg)

Type Casting

Type Casting: is when you assign a value of one primitive data type to another type.

there are two types of casting:

    1\. Widening Casting: converting a smaller type to a larger type size automatically

        byte -> short -> char -> int -> long -> float -> double

    2\. Narrowing Casting: converting a larger type to a smaller size type manually

        double -> float -> long -> int -> char -> short -> byte

1\. Widening Casting

Create a file in Nodepad++: TypeCasting.java

| public class TypeCasting {    public static void main(String[] args) {        // converting a smaller type to a larger type size automatically        byte varByte = 1;        int varInt = varByte;        System. out .println(varInt);        int varInt2 = 10;        float varFloat2 = varInt2;        System. out .println(varFloat2);    }} |

Open cmd type "javac TypeCasting.java" and then type "java TypeCasting " .

![](Image00035.jpg)

2\. Narrowing Casting

Create a file in Nodepad++: TypeCasting.java

| public class TypeCasting {    public static void main ( String [] args ) {        // converting a larger type to a smaller size type manually        int varInt = 2 ;        byte varByte = ( byte ) varInt ; // Need downcast: add  ( byte ) at the beginning        System . out . println ( varByte );        float varFloat = 10.5f ;        int varInt2 = ( int ) varFloat ; // Need downcast: add  ( int ) at the beginning        System . out . println ( varInt2 );    }} |

Open cmd type "javac TypeCasting.java" and then type "java TypeCasting " .

![](Image00036.jpg)

3. char and int (Widening Casting and Narrowing Casting)

int and char conversion, the rules follow ASCII Table

ASCII stands for American Standard Code for Information Interchange. Below is the ASCII character table, including descriptions of the first 32 characters.

    char 'a' convert to int 97

    char 'b' convert to int 98

    int 99 convert to char 'c'

    int 100 convert to char 'd'

![](Image00037.gif)

Create a file in Nodepad++: TypeCasting.java

| public class TypeCasting {    public static void main ( String [] args ) {        // char convert to int rules follow ASCII Table        char varChar = 'a' ;        int varInt = varChar ;        System . out . println ( varInt );        // int convert to char rules follow ASCII Table        int varInt2 = 99 ;        char varChar2 = ( char ) varInt2 ; // Need downcast: add  ( char ) at the beginning        System . out . println ( varChar2 );    }} |

Open cmd type "javac TypeCasting.java" and then type "java TypeCasting " .

![](Image00038.jpg)

Arithmetic Operator

Arithmetic operator: are used to perform common mathematical operations.

    Addition + , Subtraction - , Multiplication * , Division / , Modulus %

![](Image00039.jpg)

1. Create a file in Nodepad++ : Arithmetic.java

| public class Arithmetic {    public static void main ( String [] args ) {        int a = 1 ;        int b = 2 ;        int c = 3 ;        System . out . println ( a + b );    // 1 + 2 = 3        System . out . println ( a - b );     // 1 - 2 = -1        System . out . println ( a * b );     // 1 * 2 = 2        System . out . println ( a / b );      // 1 / 2 = 0        System . out . println ( c % b );   // 1 % 2 = 1 Returns the division remainder    }} |

Open cmd type "javac Arithmetic.java" and then type "java Arithmetic " .

![](Image00040.jpg)

Method

![](Image00041.jpg)

![](Image00042.jpg)

Method: is a block of code which only runs when it is called, You can pass data, known as parameters into a method. define a method once and then reuse it many times.

![](Image00043.gif)

1. Create a file in Nodepad++ : TestMethod.java

| public class TestMethod {    // define a add method, two parameters a and b    public static int add ( int a , int b ){        return a + b ;    }    public static void main ( String [] args ) {        int result = add ( 4 , 2 ); // call the add method        System . out . println ( result ); // result = 6        result = add ( 5 , 3 );        System . out . println ( result ); // result = 8    }} |

Open cmd type "javac TestMethod.java" and then type "java TestMethod " .

![](Image00044.jpg)

2\. Add 3 more methods about - , *, /

| public class TestMethod {    public static int add ( int a , int b ){        return a + b ;    }    public static int sub ( int a , int b ){        return a - b ;    }    public static int multiply ( int a , int b ){        return a * b ;    }    public static int divide ( int a , int b ){        return a / b ;    }    public static void main ( String [] args ) {        int result = add ( 4 , 2 );        System . out . println ( result ); // result = 6        result = sub ( 4 , 2 );        System . out . println ( result ); // result = 2        result = multiply ( 4 , 2 );        System . out . println ( result ); // result = 8        result = divide ( 4 , 2 );        System . out . println ( result ); // result = 2    }} |

Open cmd type "javac TestMethod.java" and then type "java TestMethod " .

You will be able to see the result printed on the window.

Class

class: is a user defined blueprint or prototype from which objects are created.

Everything in Java is associated with classes and objects , along with its attributes and methods . an object is created from a class.

We can create the class named Caculator , and then create 4 methods: add, sub, multiply, divide in Caculator , so now we can use this to new objects.

![](Image00045.jpg)

1. Create a file in Nodepad++ : TestClass.java

| // define the class named Caculatorclass Caculator {    // create 4 methods: add, sub, multiply, divide    public   int add ( int a , int b ){        return a + b ;    }    public   int sub ( int a , int b ){        return a - b ;    }    public   int multiply ( int a , int b ){        return a * b ;    }    public   int divide ( int a , int b ){        return a / b ;    }}public class TestClass {        public static void main ( String [] args ) {        Caculator cal = new Caculator (); // Create a object name: cal        int result = cal . add ( 4 , 2 ); // Invoke method add by cal        System . out . println ( result ); //6        result = cal . sub ( 4 , 2 );        System . out . println ( result ); //2        result = cal . multiply ( 4 , 2 );        System . out . println ( result ); //8        result = cal.divide(4, 2);        System.out.println(result); // 2    }} |

Open cmd type "javac TestClass.java" and then type "java TestClass " .

You will be able to see the result printed on the window.

Package

package: is used to group related classes. Think of package as a folder in a file directory.

Example:

Create java  file: TestClass.java and Caculator.java in directory: c:/java

![](Image00046.gif)

1\. com/tool/ Caculator.java

| package com . tool ; // define Caculator in package com.toolpublic class Caculator {    public   int add ( int a , int b ){        return a + b ;    }    public   int sub ( int a , int b ){        return a - b ;    }} |

Open cmd type "javac com/tool/Caculator.java"

Compile com/tool/Caculator.java to com/tool/Caculator.class

![](Image00047.jpg)

2. TestClass.java

if we want to use the Caculator class from the com.tool package.

We need import Caculator of package: import com . tool . Caculator ;

or

Import a whole package: import com . tool . * ;

| import com . tool . Caculator ; // import Caculator of packagepublic class TestClass {        public static void main ( String [] args ) {        Caculator cal = new Caculator ();        int result = cal . add ( 4 , 2 );        System . out . println ( result ); //6        result = cal . sub ( 4 , 2 );        System . out . println ( result ); //2    }} |

Open cmd type "javac TestClass.java" and then type "java TestClass " .

![](Image00048.jpg)

Increment and Decrement

Increment ++: unary operator increases the value of the variable by one.

Decrement --: unary operator decreases the value of the variable by one.

1\. Create a file in Nodepad++ : Unary.java

| public class Unary {    public static void main ( String [] args ) {        int d = 4 ;        System . out . println ( d ++); // = 4 print d and then increment 1        d = 4 ;        System . out . println (++ d ); // = 5 increment 1 and then print d        d = 4 ;        System . out . println ( d --); // = 4 print d and then decrement 1        d = 4 ;        System . out . println (-- d ); // = 3 decrement 1 and then print d        int result = 10 ;        result = result + 1 ;        System . out . println ( result ); // = 11        result = 10 ;        result ++;        System . out . println ( result ); // = 11        result = 10 ;        result += 1 ;        System . out . println ( result );   // = 11    }} |

Open cmd type "javac Unary.java" and then type "java Unary " .

You will be able to see the result printed on the window.

Relational Operator

Relational Operators: are used to comparing two variables for equality, non-equality, greater than, less than, etc. always returns a boolean value: true or false .

1\. Create a file: Relational.java

| public class Relational {    public static void main ( String [] args ) {        System . out . println ( 100 > 200 );        System . out . println ( 100 >= 100 );        System . out . println ( 100 < 200 );        System . out . println ( 100 <= 200 );        System . out . println ( 100 == 100 );        System . out . println ( 100 != 200 );    }} |

Open cmd type "javac Relational.java" and then type "java Relational" .

![](Image00049.jpg)

Logical Operators

Logical Operator: and && , or || , not !

    1\. && returns true if both sides of the operation are true , otherwise false

    2\. || returns false when both sides of the operation are false , otherwise true ;

    3\. ! if returns true , the result is false , otherwise is true

1\. Create a file: Logical.java

| public class Logical {    public static void main ( String [] args ) {        // && returns true if both sides are true , otherwise false        System . out . println ( true && false ); // = false        System . out . println ( false && true ); // = false        System . out . println ( false && false ); // = false        System . out . println ( true && true ); // = true        System . out . println ( "---------------" );        // &#124;&#124; returns false when both sides are false , otherwise true ;        System . out . println ( true &#124;&#124; false ); // = true        System . out . println ( false &#124;&#124; true ); // = true        System . out . println ( true &#124;&#124; true ); // = true        System . out . println ( false &#124;&#124; false ); // = false        System . out . println ( "---------------" );        // !   if returns true , the result is false , otherwise is true        System . out . println (! true ); // = false        System . out . println (! false ); // = true    }} |

Open cmd type "javac Logical.java" and then type "java Logical " .

You will be able to see the result printed on the window.

2\. Create a file: Logical2.java

| public class Logical2 {    public static void main ( String [] args ) {        boolean b = true ;        System . out . println ( b ); // = true        System . out . println ( 1 > 2 && b ); // = false        System . out . println ( 2 > 1 && b ); // = true        System . out . println ( "--------------" );        boolean b1 = true ;        System . out . println ( b1 ); // = true        System . out . println ( 2 > 1 &#124;&#124; b1 ); // = true        System . out . println ( 1 > 2 &#124;&#124; b1 ); // = true    }} |

Open cmd type "javac Logical2.java" and then type "java Logical2" .

You will be able to see the result printed on the window.

If

If statement

| if ( condition1 ) {  // block of code to be executed if condition1 is true} else if ( condition2 ) {  // block of code to be executed if the condition1 is false and condition2 is true} else {  // block of code to be executed if the condition1 is false and condition2 is false} |

Score example:

    if score == 5 :  Excellent

    else if score == 4 :   Good

    else : Need to catch up

1\. Create a IfStatement.java

| public class IfStatement {    public static void main ( String [] args ) {        int score = 5 ;        if ( score == 5 ){            System . out . println ( "Excellent" );        } else if ( score == 4 ){            System . out . println ( "Good" );        } else {            System . out . println ( "Need to catch up" );        }    }} |

Open cmd type "javac IfStatement .java" and then type "java IfStatement " .

Result:

Excellent

Change int score = 4 Result:

Good

2\. Get user input from keyboard

Scanner: class is used to get user input, and it is found in the java.util package.

To use the Scanner class, create an object of the class. In our example, we will use the nextInt() method, which is used to Read a int value from the user input from keyboard

| import java . util . Scanner ; // Import the Scanner classpublic class IfStatement {    public static void main ( String [] args ) {        Scanner in = new Scanner ( System . in ); // Create a Scanner object        System . out . println ( "Please input your score:" );        int score = in . nextInt (); // Read a int value from user        if ( score == 5 ){            System . out . println ( "Excellent" );        } else if ( score == 4 ){            System . out . println ( "Good" );        } else {            System . out . println ( "Need to catch up" );        }    }} |

Open cmd type "javac IfStatement .java" and then type "java IfStatement " .

![](Image00050.jpg)

Switch

switch: switch statement to select one of many code blocks to be executed.

The switch expression is evaluated once.

The value of the expression is compared with the values of each case . If there is a match, the associated block of code is executed.

The break keyword it breaks out of the switch block.

The default keyword specifies some code to run if there is no case match

| switch ( expression ) {  case a :    // code block    break ;  case b :    // code block    break ;  default :    // code block} |

Score example: use switch statement to replace if statement :

    if score == 5 :  Excellent

    else if score == 4 :   Good

    else : Need to catch up

| switch ( score ) {  case 5 :    System . out . println ( "Excellent" );    break ;  case 4 :    System . out . println ( "Good" );    break ;  default :    System . out . println ( "Need to catch up" );} |

Create SwitchStatement.java

| import java . util . Scanner ;public class SwitchStatement {    public static void main ( String [] args ) {        Scanner in = new Scanner ( System . in ); // Create a Scanner object        System . out . println ( "Please input your score:" );        int score = in . nextInt (); // Read a int value from user        switch ( score ) {          case 5 :            System . out . println ( "Excellent" );            break ;          case 4 :            System . out . println ( "Good" );            break ;          default :            System . out . println ( "Need to catch up" );        }    }} |

Open cmd type "javac SwitchStatement .java" and then type "java SwitchStatement " .

![](Image00051.jpg)

While Loop

while loop: loops through a block of code as long as a specified condition is true

| while ( condition ) {  // code block to be executed} |

1\. Create a file: WhileLoop.java

the code in the loop will run, over and over again, as long as a variable (i) is less than 3:

| public class WhileLoop {    public static void main ( String [] args ) {        int i = 0 ;        while ( i < 3 ) {            System . out . println ( i );            i = i + 1 ;        }    }} |

![](Image00052.gif)

Do While Loop

Do while loop: will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

| do {  // code block to be executed}while ( condition ); |

1\. Create a file: DoWhile.java

the code in the loop will run, over and over again, as long as a variable (i) is less than 3:

| public class DoWhile {    public static void main ( String [] args ) {        int i = 0 ;        do {          System . out . println ( i );          i ++;        }        while ( i < 3 );    }} |

Open cmd type "javac DoWhile.java" and then type "java DoWhile " .

![](Image00053.jpg)

While Loop Games

![1753341314145](Image00054.jpg)

Simulation Games exmple:

While ( num!= 0 ){

        if num == 1: You cut the watermelon

        else if num == 2: You cut the banana

        else if num == 3: You cut the peach

        else if num == 0: You cut the thunder

}

![](Image00055.jpg)

1\. Create WhileLoopGames.java

| import java . util . Scanner ;public class WhileLoopGames {    public static void main ( String [] args ) {        System . out . println ( "Input 1: Watermelon, 2: Banana, 3: Peach, 0: Thunder" );        Scanner in = new Scanner ( System . in );        int num = 0 ;        while ( num != - 1 ) { //If you enter -1 to terminate the game            num = in . nextInt ();            if ( num == 1 ) {                System . out . println ( "You cut the watermelon" );            } else if ( num == 2 ) {                System . out . println ( "You cut the banana" );            } else if ( num == 3 ) {                System . out . println ( "You cut the peach" );            } else if ( num == 0 ) {                System . out . println ( "You cut the thunder game termination" );                num = - 1 ;            }        }    }} |

Open cmd type "javac WhileLoopGames.java" and then type "java WhileLoopGames " .

![](Image00056.jpg)

For Loop

for loop: exactly how many times loop through a block of code.

Statement 1 is executed one time before the execution of the code block.

Statement 2 defines the condition for executing the code block.

Statement 3 is executed every time after the code block has been executed.

| for ( statement 1 ; statement 2 ; statement 3 ) {  // code block to be executed} |

1\. Create ForLoop.java Print the numbers 0 to 2:

| public class ForLoop {    public static void main ( String [] args ) {        for ( int i = 0 ; i < 3 ; i ++) {            System . out . print ( i + " , " ); // Plus sign +: concatenate two strings        }    }} |

Open cmd type "javac ForLoop.java" and then type "java ForLoop " .

Result: 0 , 1 , 2 ,

![](Image00057.gif)

For Loop Print Ball

![1753356993756](Image00058.jpg)

Ball game example:

    the game starts with 64 balls.

    8 balls per line. * Representative ball.

1\. Create file: PrintBall.java

| public class PrintBall {    public static void main ( String [] args ) {        for ( int i = 1 ; i <= 64 ; i ++) {            System . out . print ( "* " );            if ( i % 8 == 0 ) // 8%8=0, 16%8=0, 24%8=0, 32%8=0, 48%8=0, 64%8=0            {                System . out . println ( "" ); //wrap a new line            }        }    }} |

Open cmd type "javac PrintBall.java" and then type "java PrintBall " .

Result:

* * * * * * * *

* * * * * * * *

* * * * * * * *

* * * * * * * *

* * * * * * * *

* * * * * * * *

* * * * * * * *

* * * * * * * *

Continue and Break

break: can be used to jump out of a loop.

continue: breaks one iteration and continues with the next iteration in the loop.

1\. Create BreakLoop.java

when i==1 jumps out of the loop:

| public class BreakLoop {    public static void main ( String [] args ) {        for ( int i = 0 ; i < 3 ; i ++) {            if ( i == 1 ){                break ; // jumps out of the loop            }            System . out . println ( i );        }    }} |

Result:

0

2\. Create ContinueLoop.java

when i==1 breaks current iteration and continues with the next iteration.:

| public class ContinueLoop {    public static void main ( String [] args ) {        for ( int i = 0 ; i < 3 ; i ++) {            if ( i == 1 ){                continue ; // breaks current iteration and continues with the next iteration.            }            System . out . println ( i );        }    }} |

Result:

0

2

One-Dimensional Array

Arrays: are used to store multiple values in a single variable.

To declare an array, define the variable type with square brackets, create an array of integers

| int [] scores ; |

You access an array element by referring to the index number.

Array indexes start with 0: [0] is the first element. [1] is the second element, etc.

![](Image00059.jpg)

1\. Create a file: OneArray.java

| public class OneArray {    public static void main ( String [] args ) {        int [] scores = { 90 , 70 , 50 , 80 , 60 , 85 }; // Define a one-dimensional array        System . out . println ( scores [ 0 ]); // =90        System . out . println ( scores [ 2 ]); // =50        System . out . println ( scores [ 4 ]); // =60    }} |

2\. Array Length

scores. length: how many elements an array has, use the length property

Create a file: OneArray2.java

| public class OneArray2 {    public static void main ( String [] args ) {        // Define a one-dimensional array        int [] scores = { 90 , 70 , 50 , 80 , 60 , 85 };        //print all the data of the scores        for ( int i = 0 ; i < scores . length ; i ++) {            System . out . print ( scores [ i ] + "," );        }    }} |

Result:

90,70,50,80,60,85,

Two-Dimensional Array

Two-Dimensional array: is an array containing one or more arrays.

To create a two-dimensional array, add each array within its own set of curly braces:

| int [][] arrs ; |

![](Image00060.jpg)

1\. Create a file: BinaryArray.java

| public class BinaryArray {    public static void main ( String [] args ) {        // Two-dimensional array definition and initialization        int [][] arrs = {                { 10 , 20 , 30 },                { 40 , 50 , 60 },                { 70 , 80 , 90 }             };        System . out . println ( arrs [ 0 ][ 0 ]); // =10        System . out . println ( arrs [ 0 ][ 2 ]); // =30        System . out . println ( arrs [ 1 ][ 1 ]); // =50        System . out . println ( arrs [ 2 ][ 2 ]); // =90    }} |

2\. Create a TwoArray2.java print all elements of two-dimension array

We can also use a for loop inside another for loop to get the elements of a two-dimensional array (we still have to point to the two indexes):

![](Image00061.gif)

| public class BinaryArray2 {    public static void main ( String [] args ) {        int [][] arrs = {                { 10 , 20 , 30 },                { 40 , 50 , 60 },                { 70 , 80 , 90 } };        // arrs.length : size of row, arrs[i].length : size of column        for ( int i = 0 ; i < arrs . length ; i ++) {            for ( int j = 0 ; j < arrs [ i ]. length ; j ++) {                System . out . print ( arrs [ i ][ j ] + " " );            }            System . out . println ( "" );        }    }} |

Result:

10 20 30

40 50 60

70 80 90

Class

class: is a user defined blueprint or prototype from which objects are created.

Everything in Java is associated with classes and objects , along with its attributes and methods . an object is created from a class.

We can create the class named Person , There are two attributes in the Person: name, age and then create a method: say() in Person , so now we can use this to new objects.

![](Image00062.jpg)

1\. Create a file: TestPerson.java

| // Define a Person class, There are two attributes: name , age and a method: say()class Person {    String name ;    int age ;    public void say () {        System . out . println ( "My name is: " + name + ", this year: " + age + " years old" );    }}public class TestPerson {    public static void main ( String [] args ) {        //Create a object p by new keyword        Person p = new Person ();        // Use the p invoke attributes and methods        p . name = "Joseph" ;        p . age = 22 ;        p . say ();    }} |

Open cmd type "javac TestPerson.java" and then type "java TestPerson " .

Result:

My name is: Joseph, this year: 22 years old

Encapsulation

Encapsulation: is a mechanism of wrapping the data together as a single unit. the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class.

To achieve Encapsulation:

    Declare the variables of a class as private.

    Provide public setter and getter methods to set and get the values of variables.

Example:

    Declare the name and age as private in Person class

    Provide public setName(String name) and String getName() to set and get the values of name .

    Provide public setAge(String age) and String getAge() to set and get the values of age .

![](Image00063.jpg)

Note:

1\. The variables defined in the class are called member variables.

2\. The variables defined in the method are called local variables.

In order to distinguish between member variables and local variables , add this in front of member variables

this: refers to the current object in a method

![](Image00064.gif)

1\. Create a file: TestEncapsulation.java

| class Person {    // Declare the name and age as private    private String name ;    private int age ;    // Provide public setter methods to set the values of name.    public void setName ( String name ) {        this . name = name ;    }    // Provide public getter methods to get the values of name.    public String getName () {        return this . name ;    }    public void setAge ( int age ) {        this . age = age ;    }    public int getAge () {        return this . age ;    }}public class TestEncapsulation {    public static void main ( String [] args ) {        Person p = new Person ();        p . setName ( "Joseph" );        p . setAge ( 22 );        System . out . println ( p . getName () + " " + p . getAge ());    }} |

Open cmd type "javac TestEncapsulation.java" and then type "java TestEncapsulation " .

Result:

Joseph 22

Constructor Method

Constructor method: is used to initialize objects. When create a object, the constructor method is called automatically. It can be used to set initial values for object attributes.

The constructor name must match the class name, and it cannot have a return type. All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you.

Example:

    Define a Person class

    Create a constructor method without parameter: Person()

    Create a constructor method with two parameter: Person(String name, int age)

![](Image00065.jpg)

![](Image00066.gif)

1\. Create file: TestConstructor.java

| class Person {    private String name ;    private int age ;    public Person () {        System . out . println ( "constructor method without parameter is called" );    }    public Person ( String name , int age ) {        System . out . println ( "constructor method with parameter is called" );        this . name = name ;        this . age = age ;    }    public void say () {        System . out . println ( "My name is :" + name + ", this year: " + age + " years old" );    }}public class TestConstructor {    public static void main ( String [] args ) {        // Create a person object by the constructor method without parameters        Person p = new Person ();        // Create a person object by the constructor method with two parameters        Person p2 = new Person ( "Joseph" , 22 );        p2 . say ();    }} |

Result:

constructor method without parameter is called

constructor method with parameter is called

My name is :Joseph, this year: 22 years old

Method Overload

Method overload: In the same class, there is a method with the same name but different parameter numbers or parameter types.

Example:

    Define a Caculator class

    Define an add method: int add( int a, int b)

    Define anther add method with the same name but different parameter types:

    double add( double a, double b)

![](Image00067.jpg)

![](Image00068.gif)

1\. Create a file: TestOverLoad.java

| class Caculator {    public double add ( double a , double b ) {        return a + b ;    }    public int add ( int a , int b ) {        return a + b ;    }}public class TestOverLoad {    public static void main ( String [] args ) {        Caculator c = new Caculator ();        int result = c . add ( 10 , 20 );        System . out . println ( result );        // Call the overload method with different parameter types        double result2 = c . add ( 10.5 , 20.5 );        System . out . println ( result2 );    }} |

Result:

30

31.0

Static Keyword

static : if static variable is created which is shared across all objects of the class. This means all objects share the same variable.

Example 1:

    Create User class contain no static member variable: count

    Create 2 objects user1 and user2 and then user1.count++ ,   user2.count++

| class User {    public int count ;} |

![](Image00069.gif)

Example 2:

    Create User class contain static member variable: count

    Create 2 objects user1 and user2 and then user1.count++ ,   user2.count++

| class User {    public static int count ;} |

![](Image00070.gif)

Example 1: 2 users have their own variable count

Example 2: 2 users share the same static variable count

1\. Create a file: TestNoStatic.java

| class User {    public int count ;}public class TestNoStatic {    public static void main ( String [] args ) {        User user1 = new User ();        user1 . count ++;        User user2 = new User ();        user2 . count ++;        System . out . println ( "User1 Count : " + user1 . count );        System . out . println ( "User2 Count : " + user2 . count );    }} |

Result:

User1 Count : 1

User2 Count : 1

2\. Create a file: TestStatic.java

| class User {    public static int count ;}public class TestStatic {    public static void main ( String [] args ) {        User user1 = new User ();        user1 . count ++;        User user2 = new User ();        user2 . count ++;        System . out . println ( "User1 Count : " + user1 . count );        System . out . println ( "User2 Count : " + user2 . count );    }} |

Result:

User1 Count : 2

User2 Count : 2

3\. If variables and methods are modified by static , they can be called directly by the class name.

Create a file: TestStatic.java

| class User {    public static int count ;    public static int getCount (){        return count ;    }}public class TestStatic {    public static void main ( String [] args ) {        // can be called directly by the class name User        User . count ++;        User . count ++;        // can be called directly by the class name User        System . out . println ( "User Count : " + User . count );        System . out . println ( "User Count : " + User . getCount ());    }} |

Result:

User Count : 2

User Count : 2

Inheritance

Inheritance: is a mechanism in which one object acquires all the attributes and method of a parent object.

Example:

        Student inherit the Person

Step:

    1.Class:                  Student, Person

    2\. Relationship:      Student extends Person

    3\. Attributes:          Person attributes ( name , age )

    4\. Methods:          Person actions ( say )

    Person is called parent class or super class

    Student is called a subclass of Person or child class of Person

![](Image00071.gif)

Note:

1\. The subclass cannot access the private attribute,method of the parent class

2\. The subclass can access the protected , public attribute,method of the parent class.

1\. Create a file: TestInheritence.java

| // Person is called parent class or super classclass Person {    protected String name ;    protected int age ;    public void say () {        System . out . println ( "Person can speaking" );    }}// Student is called a subclass of Person or child class of Personclass Student extends Person {}public class TestInheritence {    public static void main ( String [] args ) {        Student s = new Student (); // Create subclass Student object        s . name = "Sumi" ;        s . age = 22 ;        s . say ();    }} |

Result:

Person can speaking

2\. The calling sequence of the constructor method in the inheritance relationship

If parent class has constructor method without parameters

    First call the constructor method of the parent class without parameters

If child class has constructor method without parameters

    And then call the constructor method of the child class without parameters

Create a file: TestInheritence.java

| class Person {    public Person () {        System . out . println ( "Parent class Person is created" );    }    public void say () {        System . out . println ( "Person can speaking" );    }}class Student extends Person {    public Student () {        System . out . println ( "Child class Student is created" );    }}public class TestInheritence {    public static void main ( String [] args ) {        Student s = new Student ();        s . say ();    }} |

Result:

Parent class Person is created

Child class Student is created

Person can speaking

Method Override

Override:

the child class overwrites the method of the parent class, the instance of the child class will call the method of child class, not call the method of the parent class.

Example:

1\. Create a parent class: Person , there is a method: say()

2\. Create a child class: ChineseStudent , there is the same method: say()

3\. Create a child class: AmericaStudent , there is the same method: say()

ChineseStudent and AmericaStudent say() will override Person say()

![](Image00072.jpg)

1\. Create a file: TestOverride.java

| class Person {    public void say () {        System . out . println ( "Person speaking" );    }}class ChineseStudent extends Person {    public void say () {        System . out . println ( "Speak Chinese" );    }}class AmericaStudent extends Person {    public void say () {        System . out . println ( "Speak English" );    }}public class TestOverride {    public static void main ( String [] args ) {        ChineseStudent s = new ChineseStudent ();        s . say ();        AmericaStudent as = new AmericaStudent ();        as . say ();    }} |

Result:

Speak Chinese

Speak English

Super Keyword

super: can be used to refer parent class instance variable.

Example:

1\. Create a parent class: Person , there is a method: say()

3\. Create a child class: AmericaStudent , there is the same method: say()

AmericaStudent say() will override Person say(), the instance of the child class will call the method: say() of child class, not call the method: say() of the parent class. If you want to call the method: say() of the parent class. You need call like: super.say().

1\. Create a file: TestSuper.java

| class Person {    public void say () {        System . out . println ( "Person speaking" );    }}class AmericaStudent extends Person {    public void say () {        super . say ();        System . out . println ( "Speak English" );    }}public class TestSuper {    public static void main ( String [] args ) {        AmericaStudent as = new AmericaStudent ();        as . say ();    }} |

Result:

Person speaking

Speak English

Polymorphism

Polymorphism: in inheritance an object can up cast to Parent class, also down cast to Subclass.

Example:

1\. Create a parent class: Person , there is a method: say()

2\. Create a child class: Student , there is the same method: say() override Person say()

    there is anther method: study()

![](Image00073.gif)

Create a Student object and then upcast to Person of Parent

When you call p.say() , the child class’s override method Student say() will be called.

not call the method: Person say() of the parent class.

![](Image00074.gif)

1\. Create a file: TestPolymorphism.java

| class Person {    public void say () {        System . out . println ( "Person speaking" );    }}class Student extends Person {    public void say () {        System . out . println ( "Student speak english" );    }    public void study () {        System . out . println ( "Student study" );    }}public class TestPolymorphism {    public static void main ( String [] args ) {        //Create a Student object and then upcast to Person of Parent        Person p = new Student ();        p . say ();        // Person of Parent: p downcast to Student of child        Student s = ( Student ) p ;        s . say ();        s . study ();    }} |

Result:

Student speak english

Student speak english

Student study

Object Relationship One-to-One

1. Example:

    Baby can eat one fruit

Analysis:

    1\. Class: Baby , Fruit

    2\. Relationship: Fruit One-to-One belong to Baby

    3\. Attributes: Baby (fruit)

    4\. Methods: Baby eat(Fruit fruit)

![](Image00075.gif)

1\. Create a file: TestObjectRelation.java

| class Fruit {    private String name ;    public Fruit ( String name ) {        this . name = name ;    }    public String getName () {        return this . name ;    }}class Baby {    private Fruit fruit ; // Fruit belong to Baby    public Fruit getFruit () {        return this . fruit ;    }    public void eat ( Fruit fruit ) {        this . fruit = fruit ;    }}public class TestObjectRelation {    public static void main ( String [] args ) {        Baby baby = new Baby ();        Fruit apple = new Fruit ( "Red Apple" );        Fruit grape = new Fruit ( "Black Grape" );        baby . eat ( apple );        System . out . println ( "Baby eat " + baby . getFruit (). getName ());        baby . eat ( grape );        System . out . println ( "Baby eat " + baby . getFruit (). getName ());    }} |

Result:

Baby eat Red Apple

Baby eat Black Grape

Abstract Class

abstract class: is a class that is declared abstract . Abstract classes cannot be instantiated, but Its child class can be instantiated.

Example:

    Father told his son to buy some fruit

Analysis:

    1\. Abstract class: Father

    2\. Implementation class: Son

    3\. Relationship: Son inherits Dad

    4\. Method: buy() the father told his son to buy fruit, but father not to buy

![](Image00076.gif)

An abstract method is declared without an implementation

father told son to buy fruit, but father not to buy,

this means method: buy() without an implementation

| abstract class Father {    public abstract void buy ( String fruit );} |

The son fulfills his father to buy fruit, this means method: buy() have an implementation

| class Son extends Father {    public void buy ( String fruit ) {        System . out . println ( "Dad, I bought some : " + fruit );    }} |

1\. Create a file: TestAbstract.java

| abstract class Father {    //father called his son to buy fruit, but father not buy    public abstract void buy ( String fruit );}class Son extends Father {    //The son fulfills the requirement of his father to buy fruit    public void buy ( String fruit ) {        System . out . println ( "Dad, I bought some : " + fruit );    }}public class TestAbstract {    public static void main ( String [] args ) {        Father f = new Son ();        f . buy ( "Apples" );    }} |

Result:

Dad, I bought some : Apples

2\. Abstract classes can also have their own methods of implementation

Example:

    Father is working now, so told his son to buy some fruit

Analysis

    1\. Method: Father have two method: work() and abstract buy()

Create a file: TestAbstract.java

| abstract class Father {    public void work () {        System . out . println ( "Father is working now." );    }    public abstract void buy ( String fruit );}class Son extends Father {    public void buy ( String fruit ) {        System . out . println ( "Dad, I bought some : " + fruit );    }}public class TestAbstract {    public static void main ( String [] args ) {        Father f = new Son ();        f . work ();        f . buy ( "Apples" );} |

Result:

Father is working now.

Dad, Dad, I bought some : Apples

Interface

interface: is a different way to achieve abstraction that is used to group related methods with empty body, the child class must be implemented the interface and its empty method.

Example:

    The boss hires employees to work

Analysis:

    1\. interface: Boss

    2\. Implementation class: Employee

    3\. Relationship: Employee implements Boss

    4\. Method: work() the boss hires employees to work, boss not to do this work.

![](Image00077.jpg)

An interface method is declared without an implementation

boss hires employees to work, boss not to do this work.

this means method: work() without an implementation

| interface Boss {    public void work ();} |

The employees to do work, this means method: work() have an implementation

| class Employee implements Boss {    public void work () {        System . out . println ( "Employee start to work" );    }} |

1\. Create a file: TestInterface.java

| interface Boss {    //boss hires employees to work, boss not to do this work.    public void work ();}class Employee implements Boss {    //The employees to do work    public void work () {        System . out . println ( "Employee start to work" );    }}public class TestInterface {    public static void main ( String [] args ) {        Boss b = new Employee ();        b . work ();    }} |

Result:

Employee start to work

Notes:

    1\. The implementation of the method is not allowed in the interface.

    2\. The methods are all public by default in the interface.

    3\. The attributes are public static in the interface.

    4\. The child class must implement all the declaration methods in the interface.

2\. Child classe can only inherit one class , but can implement multiple interfaces.

Example:

    The boss hires employees to work, and then managers let employees learn business.

Analysis:

    1\. interface: Boss, Manager

    2\. Implementation class: Employee

    3\. Relationship: Employee implements Boss, Manager

    4\. Method: work() the boss hires employees to work, boss not to do this work.

                      learn() the manager let employees to learn, manager not to learn.

![](Image00078.jpg)

Create a file: TestInterface.java

| interface Boss {    //boss hires employees to work, boss not to do this work.    public void work ();}interface Manager {    //the manager let employees to learn, manager not to learn.    public void learn ();}class Employee implements Boss , Manager {    //The employees to do work    public void work () {        System . out . println ( "Employee start to work" );    }    //The employees to learn    public void learn () {        System . out . println ( "Employee start to learn business" );    }}public class TestInterface {    public static void main ( String [] args ) {        Boss b = new Employee ();        b . work ();        Manager m = new Employee ();        m . learn ();    }} |

Result:

Employee start to work

Employee start to learn business

Enum

enum: is a special data type that enables for a variable to be a set of predefined constants. The variable must be equal to one of the values that have been predefined for it.

Example:

    Draw circles of different color

![](Image00079.gif)

Analysis:

    1\. enum: Color ( RED , GREEN, BLUE )

    2\. class: Circle

    3\. Method: draw() draw circles of different color.

Define enum type: Color

| enum Color {  RED , GREEN , BLUE} |

![](Image00080.gif)

1\. Create a file: TestEnum.java

| //Define enum typesenum Color {  RED , GREEN , BLUE}class Circle {  //draw circles of different color.  public void draw ( Color color ) {      String colorName = "" ;      if ( color == Color . RED ) {          colorName = "Red" ;      } else if ( color == Color . GREEN ) {          colorName = "Green" ;      } else if ( color == Color . BLUE ) {          colorName = "Blue" ;      }      System . out . println ( "draw " + colorName + " circle" );  }}public class TestEnum {    public static void main ( String [] args ) {        Circle circle = new Circle ();        circle . draw ( Color . RED );        circle . draw ( Color . GREEN );        circle . draw ( Color . BLUE );    }} |

Result:

draw Red circle

draw Green circle

draw Blue circle

Internal Class

Inner classe: are a security mechanism. if we have the class as a member of other class, then the inner class can be made private.

Example:

    Mother pregnanted, Baby eat food from the mother

Analysis:

    1\. Class: Mother , Baby

    2\. Relationship: Baby in Mother

    3\. Method: Mother eat(food) , Baby eat() from Mother

![](Image00081.gif)

First define the Mother class, then define the Baby class inside the Mother class

| class Mother {    public void eat ( String food ) {        Baby baby = new Baby ();        baby . eat ();    }    class Baby {        public void eat () {        }    }} |

1\. Create a file: TestInnerClass.java

| class Mother {    private String food ;    public void eat ( String food ) {        this . food = food ;        System . out . println ( "Mother eat " + food );        //Baby take nutrition from food        Baby baby = new Baby ();        baby . eat ();    }    //The Baby is the inner class of the mother    class Baby {        public void eat () {            System . out . println ( "Baby absorb nutrients from the mother's " + food );        }    }}public class TestInnerClass {    public static void main ( String [] args ) {        Mother mother = new Mother ();        mother . eat ( "Apple" );    }} |

Result:

Mother eat Apple

Baby absorb nutrients from the mother's Apple

IDE Eclipse Installation

Now it’s the right time to move on to using the IDE( Eclipse ), because you have learned basic knowledge and experience in Java.

Eclipse: is famous for Java Integrated Development Environment (IDE) that is popular for Java application development and Android apps. Eclipse is cross-platform and runs under Windows, Linux and Mac OS.

1\. Download the Eclipse development tools: eclipse-jee-mars-2-win32-x86_64.zip

[https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)

or

[http://en.verejava.com/download.jsp?id=1](http://en.verejava.com/download.jsp?id=1)

![](Image00082.jpg)

2\. Double click eclipse.exe to Open

![](Image00083.jpg)

3\. Double click eclipse.exe to Open

![](Image00084.jpg)

Workspace: contains resources such as: Projects, Files, Folders etc. The workspace has a hierarchical structure. Projects are at the top level of the hierarchy and inside them you can have files and folders.

![](Image00085.jpg)

Click OK Button

![](Image00086.jpg)

4\. Create a new Java Project   Click File -> New -> Project

![](Image00087.jpg)

5\. Select Java Project and then click Next button

![](Image00088.jpg)

6\. Enter the Project name: test and then click Finish button

![](Image00089.jpg)

7\. Project: test has a hierarchical structure.

src: it's a foder the source code files are stored.

JRE System Library: is added by Eclipse automatically on creating Java Projects. JRE System Library implements the Java API in Eclipse. So all the predefined methods of Java, can be accessed by the Java Programs written in Eclipse.

![](Image00090.jpg)

8\. Create a class: Hello , Right click src and then New -> Class

![](Image00091.jpg)

9\. Input class Name: Hello , and then click Finish button

![](Image00092.jpg)

10\. Double click Hello.java in project: test

![](Image00093.jpg)

11\. Input code in main method:

|         System. out .println( "Hello World!" ); |

Right click Hello.java and then Run As -> Java Application

![](Image00094.jpg)

12\. Eclipse will automatically compile Hello.java into Hello.class , and then run Hello ,

the result will be printed in the Console panel.

![](Image00095.jpg)

String

String: is a java default class represents character strings. Strings are constant; their values cannot be changed after they are created.

1\. String Comparison

equals() method and the == operator is used to compare two String.

|     String str1 = "hello" ;    String str2 = "hello" ;    System. out .println( str1 .equals( str2 )); // =true    System. out .println( str1 == str2 ); // = true |

str1 and str2 point to the same "hello" object in the string pool, so equals() and == is true ![](Image00096.gif)

|     String str1 = "hello" ;    String str2 = new String( "hello" );    System. out .println( str1 .equals( str2 )); // =true    System. out .println( str1 == str2 ); // =false |

Why str1 .equals( str2 ) is true but str1 == str2 is false.

Because str1 "hello" created in String Pool, the str2 new String( "hello" ); created in Heap.

the == operator compares reference, but equals() compares the value of String.

str1 and str2 have the same value, but different reference. ![](Image00097.gif)

2. String replace ( char oldChar , char newChar):

Returns a new string resulting from replacing all occurrences of oldChar in this string with newChar.

Replace all || to ,

|     String person = "David&#124;&#124;30&#124;&#124;Male&#124;&#124;Married" ;    person = person .replace( "&#124;&#124;" , "," );    System. out .println( person ); |

Result: David,30,Male,Married

3. boolean startsWith( String prefix):

Tests if this string starts with the specified prefix.

Test if the file path starts with c:

|     String path = "c:/video/loveforever.mp4" ;    System. out .println( path .startsWith( "c:" )); |

Result: true

4. boolean endsWith( String suffix):

Tests if this string ends with the specified suffix.

Test if the file path ends with .mp4

|     String path = "c:/video/loveforever.mp4" ;    System. out .println( path .endsWith( ".mp4" )); |

Result: true

5. int indexOf( char ch):

find the first index of the ch in string from left to right. The index of the string starts at 0

![](Image00098.gif)

find the first index of the / in path from left to right.

|     String path = "c:/video/loveforever.mp4" ;    int index = path.indexOf( "/" );    System. out .println(index); |

Result: 2

6. int lastIndexOf( char ch):

find the first index of the ch in string from right to left.

find the first index of the / in path from right to left.

|     String path = "c:/video/loveforever.mp4" ;    int lastIndex = path.lastIndexOf( "/" );    System. out .println(lastIndex); |

Result: 8

7. String trim():

Remove whitespace from both sides of a string.

|     String str = "  aa bb  " ;    str = str.trim();    System. out .println(str); |

Result: aa bb

8. String substring( int beginIndex):

cut string from the beginIndex to the end.

![](Image00099.gif)

Get the name of file extension

|     String path = "c:/video/loveforever.mp4" ;    String str = path.substring(path.lastIndexOf( "." ));    System. out .println(str); |

Result: .mp4

9. String substring( int beginIndex, int endIndex):

cut string from the beginIndex to the endIndex.

![](Image00100.gif)

Get substring video

|     String path = "c:/video/loveforever.mp4" ;    String str = path.substring(path.indexOf( "/" ) + 1, path.lastIndexOf( "/" ));    System. out .println(str); |

Result: .video

10. String [] split( String regex):

Split a string into an array with regex

Grace's language, math and physics scores are separated by semicolons;

Please split each subject score by ;

|     String scores = "100;98;95" ;    String[] scoreArray = scores.split( ";" );    System. out .println( "Language=" + scoreArray[0] );    System. out .println( "Math =" + scoreArray[1] );    System. out .println( "Physics=" + scoreArray[2]); |

Result:

Language=100

Math =98

Physics=95

11. toLowerCase():

Converts all of the characters to lower case

|     String sentense = "FAITH HOPE AND LOVE" ;    sentense = sentense.toLowerCase ();    System. out .println(sentense); |

Result: faith hope and love

12. toUpperCase():

Converts all of the characters to upper case

|         String sentense = "faith hope and love" ;        sentense = sentense.toUpperCase ();        System. out .println(sentense); |

Result: FAITH HOPE AND LOVE

13. StringBuilder:

StringBuilder are like String except that they can be modified. Internally, these objects are treated like variable-length arrays that contain a sequence of characters.

Use String concatenate a large number of strings

|     public static void main(String[] args) {        String str = "" ;        for ( int i=0; i<5; i++){            str += " day " ;        }        System. out .println(str);    } |

Result: day day day day day

Use StringBuilder concatenate a large number of strings

|     public static void main(String[] args) {        StringBuilder sb = new StringBuilder();        for ( int i=0; i<5; i++){            sb.append( " day " );        }        System. out .println(sb.toString());    } |

Result: day day day day day

Notes:

StringBuilder offer an advantage and better performance. if you need to concatenate a large number of strings, appending to a StringBuilder is more efficient .

Primitive Types and Wrapper Classes

Wrapper class: is a class whose object wraps or contains primitive data types. When we create an object to a wrapper class, we can store primitive data types. we can wrap a primitive value into a wrapper class object.

Java Primitive Type and Corresponding Wrapper Classes

| Primitive Type | Wrapper Class |
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |
| char | Character |
| boolean | Boolean |

1: Primitive type convert to Wrapper Class

|         int age = 20;        Integer ageObj = new Integer(age);        System. out .println(ageObj); |

Result: 20

2: Wrapper Class convert to Primitive type

|         Integer ageObj = new Integer(20);        int age = ageObj.intValue();        System. out .println(age); |

Result: 20

3: Primitive type convert to String

String.valueOf(): converts different types of values into string.

|     int age = 20;    String ageStr = String. valueOf (age);    double money = 1000.5;    String moneyStr = String. valueOf (money);    System. out .println(ageStr);    System. out .println(moneyStr); |

Result:

20

1000.5

4: String convert to Primitive type

Integer. parseInt (String str): convert String to Integer.

Float. parseFloat (String str): convert String to Float.

Double. parseDouble (String str): convert String to Double.

|     String ageStr = "20" ;    int age = Integer. parseInt (ageStr);    String moneyStr = "1000.5" ;    double money = Double. parseDouble (moneyStr);    System. out .println(age);    System. out .println(money); |

Result:

20

1000.5

Object

Object: is the root of the class hierarchy. Every class has Object as a parent class. So all objects are the children of Object.

Object class contains toString() method. We can use toString() method to get string representation of an object. Whenever we try to print the Object reference toString() method is invoked. If we did not define toString() method then Object class toString() method is invoked otherwise our Overridden toString() method will be called.

1\. Create a class: Cat

we not define toString() method, Object class toString() method is invoked

![](Image00101.jpg)

Create test file: TestObject.java

| class Cat {    private String name ;    public Cat(String name) {        this . name = name;    }}public class TestObject {    public static void main(String[] args) {        Object obj = new Cat( "Teddy" );        System. out .println(obj.toString());    }} |

Result:

test.Cat@1f1fba0

2\. Create a class: Cat

we define toString() method in Cat, our Overridden toString() method will be calle d ![](Image00102.jpg)

Create test file: TestObject.java

| class Cat {    private String name ;    public Cat(String name) {        this . name = name;    }    public String toString(){        return name ;    }}public class TestObject {    public static void main(String[] args) {        Object obj = new Cat( "Teddy" );        System. out .println(obj.toString());    }} |

Result:

Teddy

ArrayList

ArrayList: is a part of collection framework and is present in java.util package. It provides us with dynamic arrays. It implements List interface . List inherits the Collection interface

    1\. ArrayList in order of first-in, first-out.

    2\. ArrayList can add repeating elements

    3\. ArrayList can also add null value

    4\. ArrayList is an array of objects

![](Image00103.gif)

1\. add(Object o):

add an element at the end of the list

get( int index):

get the element from the position of the list.

|     public static void main(String[] args) {        List list = new ArrayList();        list.add(100);        list.add( "David" );        System. out .println(list.get(0));        System. out .println(list.get(1));    } |

Result:

100

David

2. int size():

return the number of elements in the list.

|     public static void main(String[] args) {        List list = new ArrayList();        list.add(100);        list.add( "David" );        list.add(25.5);        //Print all elements        for ( int i = 0; i < list.size(); i++) {            Object obj = list.get(i);            System. out .print(obj + "," );        }    } |

Result:

100,David,25.5,

3\. set( int index, Object element):

replace the specified element in the list at the specified position.

|         List list = new ArrayList();        list.add(100);        list.add( "David" );        list.set(1, "Grace" ); // update "David" to "Grace" |

List Result:

100,Grace,

4\. remove( int index):

remove the element at the specified position in the list.

boolean remove(Object o):

remove the first occurrence of the specified element.

|         List list = new ArrayList();        list.add(100);        list.add( "David" );        list.add(10.5);        list.remove(0); // delete element at index = 0        list.remove( "David" ); // delete element "David" |

List Result: 10.5,

5. boolean isEmpty():

returns true if the list is empty, otherwise false.

void clear():

remove all of the elements from list.

boolean contains(Object o):

returns true if the list contains the specified element

|     public static void main(String[] args) {        List list = new ArrayList();        list.add(100);        list.add( "David" );        list.add(10.5);        System. out .println(list.isEmpty()); // false        System. out .println(list.contains( "David" )); // true        list.clear();        System. out .println(list.isEmpty()); // true    } |

6\. List add custom objects: Person

| import java.util.*;class Person {    private String name ;    private int age ;    public Person(String name, int age) {        this . name = name;        this . age = age;    }    public String toString() {        return "name = " + name + " , age = " + age ;    }}public class TestList {    public static void main(String[] args) {        List list = new ArrayList();        list.add( new Person( "David" , 20));        list.add( new Person( "Joseph" , 30));        list.add( new Person( "Grace" , 40));        //Print all Persons        for ( int i = 0; i < list.size(); i++) {            Object obj = list.get(i);            System. out .println(obj); // toString() will be invoked        }    }} |

Result:

name = David , age = 20

name = Joseph , age = 30

name = Grace , age = 40

LinkedList

LinkedList: is a collection which can contain many objects of the same type, just like the ArrayList. The LinkedList class has all of the same methods as the ArrayList class because they both implement the List interface.

![](Image00104.gif)

the different is ArrayList class has a regular array inside it. The LinkedList has a link to the first container and each container has a link to the next and has a link to the prev in the list.

ArrayList has an array inside for storage

![](Image00105.gif)

LinkedList has a linked list for storage

![](Image00106.gif)

So You want to access random items frequently is best to use ArrayList

You frequently need to add and remove items is best to use  LinkedList

1\. addFirst(Object o):

Adds an item to the beginning of the list.

addLast(Object o):

Add an item to the end of the list.

|     public static void main(String[] args) {        LinkedList list = new LinkedList();        list.add( "David" );        list.add( "Joseph" );        list.addFirst( "Grace" );        list.addLast( "Renia" );        for ( int i = 0; i < list.size(); i++) {            System. out .println(list.get(i));        }    } |

Result:

Grace

David

Joseph

Renia

2\. Object getFirst():

Get the item at the beginning of the list

Object getLast():

Get the item at the end of the list

|     public static void main(String[] args) {        LinkedList list = new LinkedList();        list.add( "Grace" );        list.add( "David" );        list.add( "Joseph" );        System. out .println( "First: " + list.getFirst());        System. out .println( "Last: " + list.getLast());    } |

Result:

First: Grace

Last: Joseph

3\. Object removeFirst():

Remove an item from the beginning of the list.

removeLast():

Remove an item from the end of the list

|     public static void main(String[] args) {        LinkedList list = new LinkedList();        list.add( "Grace" );        list.add( "David" );        list.add( "Joseph" );        list.removeFirst();        list.removeLast();        for ( int i = 0; i < list.size(); i++) {            System. out .println(list.get(i));        }    } |

Result:

David

Iterator

Iterator: is an interface which belongs to collection framework. It allows us to traverse the collection, access the data element.

![](Image00107.gif)

1. boolean hasNext():

It returns true if Iterator has more element to iterate.

Object next():

It returns the next element in the collection until the hasNext()method return true.

|     public static void main(String[] args) {        List stationList = new ArrayList();        stationList.add( "Berkeley University" );        stationList.add( "Market Street" );        stationList.add( "Polo Alto" );        stationList.add( "Cuptino" );        Iterator iter = stationList.iterator();        while (iter.hasNext()) { // Returns true if the iterator has more elements.            String station =  iter.next().toString(); // Returns the next element in the iteration.            System. out .print(station + " -> " );        }    } |

Result:

Berkeley University -> Market Street -> Polo Alto -> Cuptino ->

HashSet

HashSet: is used to create a collection that uses a hash table for storage. It implements Set interface. The HashSet class has some of the same methods as the ArrayList.

    1\. HashSet contains unique elements only.

    2\. HashSet allows null value.

    3\. HashSet does not return value in the same order.

![](Image00108.jpg)

|     public static void main(String[] args) {        Set set = new HashSet();        set.add( "Abraham" );        set.add( "Washington" );        set.add( "James" );        set.add( "James" );        set.add( "James" );        Iterator iter = set.iterator();        while (iter.hasNext()) {            String name =  iter.next().toString();            System. out .print(name+ " , " );        }    } |

Result:

Washington , James , Abraham ,

HashMap

HashMap: is a Map based collection class that is used for storing Key = value pairs, it does not return the keys and values in the same order.

![](Image00109.jpg)

![](Image00110.gif)

1\. put(Object key, Object value):

Inserts key value mapping into the map.

Object get(Object key):

It returns the value for the specified key.

boolean containsKey(Object key):

It is returns true or false based on whether the specified key is found in the map.

|     public static void main(String[] args) {        Map map = new HashMap();        map.put( "name" , "David" );        map.put( "age" , 20);        System. out .println(map.get( "name" )); // David        System. out .println(map.get( "age" )); // 20        System. out .println(map.containsKey( "age" )); // true    } |

2\. Set keySet():

It returns the Set of the keys fetched from the map.

|     public static void main(String[] args) {        Map map = new HashMap();        map.put( "name" , "David" );        map.put( "age" , 20);        map.put( "salary" , 12000);        map.put( "married" , false );        Set set = map.keySet();        Iterator iter = set.iterator();        while (iter.hasNext()) {            Object key = iter.next().toString();            Object value = map.get(key);            System. out .println(key + "=" + value);        }    } |

Result:

married=false

age=20

name=David

salary=12000

Generic

Generic: methods and generic classes enable programmers to specify, with a single method declaration, or with a single class declaration, , or with types declaration. Generics also provide compile-time type safety that allows you to catch invalid types at compile time.

All generic method declarations have a type parameter section delimited by angle brackets <  > .

1\. Create a generic for class: Person like Person<T>

| class Person<T> { //<T> pass various data types      private T age ;    public Person(T age) {        this . age = age;    }    public T getAge() {        return age ;    }    public void setAge(T age) {        this . age = age;    }}public class TestGeneric {    public static void main(String[] args) {        Person<String> p1 = new Person<String>( "30" ); // pass String type        System. out .println(p1.getAge());        Person<Integer> p2 = new Person<Integer>(80); // pass Integer type        System. out .println(p2.getAge());    }} |

Result:

30

80

2\. Use a generic for List: ArrayList<String>

|     public static void main(String[] args) {        List<String> list = new ArrayList<String>();        list.add( "Faith" );        list.add( "Danie" );        list.add( "Mathew" );        for ( int i = 0; i < list.size(); i++) {            String element = list.get(i);            System. out .println(element);        }    } |

Result:

Faith

Danie

Mathew

3\. Use a generic for Map: HashMap<String, Integer>

|     public static void main(String[] args) {        Map<String,Integer> map = new HashMap<String,Integer>();        map.put( "English" , 100);        map.put( "Math" , 95);        map.put( "Science" , 98);        Set<String> set = map.keySet();        Iterator<String> iter = set.iterator();        while (iter.hasNext()) {            String key = iter.next();            Integer value = map.get(key);            System. out .println(key + "=" + value);        }    } |

Result:

Math=95

Science=98

English=100

4\. Create a class: Customer

Use a generic for List: ArrayList<Customer>

| import java.util.*;class Customer {    private String name ;    private int age ;    public Customer(String name, int age){        this . name = name;        this . age = age;    }    public String getName(){        return this . name ;    }    public int getAge(){        return this . age ;    }}public class TestGeneric {    public static void main(String[] args) {        List<Customer> customerList = new ArrayList<Customer>();        customerList.add( new Customer( "Grace" , 25));        customerList.add( new Customer( "Renia" , 30));        customerList.add( new Customer( "Rebeka" , 28));        for ( int i = 0; i < customerList.size(); i++) {            Customer customer = customerList.get(i);            System. out .println(customer.getName() + " , " + customer.getAge());        }    }} |

Result:

Grace , 25

Renia , 30

Rebeka , 28

Random

Random: is used to generate random numbers. Random class in java.util package.

1\. Print random numbers 0-9

rn.nextInt(n):

returns a random number between 0  and n-1.

Create a file: RandomNumber.java

| import java.util.Random;public class RandomNumber {    public static void main(String[] args) {        Random rn = new Random();        for ( int i = 0; i < 10; i++) {            int num = rn.nextInt(10);            System. out .println(num + ", " );        }    }} |

Result:

9, 3, 9, 0, 4, 1, 0, 3, 4, 5,

Each run the random number generated may be different

2\. Generate 6 different random verification codes

HashSet contains unique elements, We can continuously generate random numbers to  HashSet until HashSet is filled with 6 different random numbers.

Create a file: VerificationCode.java

| import java.util.Random;public class VerificationCode {    public static void main(String[] args) {        Random rn = new Random();        Set<Integer> set = new HashSet<Integer>();        //Continuously generate random numbers to HashSet        //until HashSet is filled with 6 different random numbers.        while (set.size()<6) {            int num = rn.nextInt(10);            set.add(num);        }        //Print all random numbers from HashSet        Iterator<Integer> iter = set.iterator();        while (iter.hasNext()){            System. out .print(iter.next() + " , " );        }    }} |

Result:

0 , 3 , 4 , 5 , 7 , 8 ,

Each run the random number generated may be different

Exception

Exception: is an unwanted or unexpected event, which occurs during the execution of a program, Exception might try to catch

Error: An Error indicates serious problem that a reasonable application should not try to catch.

![](Image00111.jpg)

try catch block

|     try {        //Statements that may cause an exception    } catch (Exception e) {       //Handling exception    } |

1\. If a/b , and b = 0 , will throw an exception: ArithmeticException .

|     public static void main(String[] args) {        int result = 0;        int a = 10;        int b = 0;        try {            result = a / b;            System. out .println(result);        }  catch (ArithmeticException e) {            System. out .println( "Divisor cannot be 0" );        }    } |

Result:

Divisor cannot be 0

If an exception occurs, the try block will be terminated and jump directly to the catch block .

![](Image00112.gif)

2\. finally block: contains all the crucial statements that must be executed whether exception occurs or not. The statements present in this block will always execute regardless of whether exception occurs in try block or not

If a/b , and b != 0

![](Image00113.gif)

Result:

2

finally

If a/b , and b = 0

![](Image00114.gif)

Result:

Divisor cannot be 0

Finally

finally block will always execute regardless of whether exception occurs in try block or not

File

File: is Java’s representation of a file or directory path name. File class contains several methods for working with the path name, deleting and renaming files, creating new directories, listing the contents of a directory etc. File class in the java.io package.

1\. Create a directory: c:/java

mkdirs():

Creates the directory named by pathname.

| import java.io.*;public class TestFile {    public static void main(String[] args) {        File f = new File( "c:/java" );        f.mkdirs();    }} |

Result:

![](Image00115.jpg)

2. String getAbsolutePath():

Returns the absolute form of this pathname.

|     File f = new File( "c:/java" );    System. out .println(f.getAbsolutePath()); |

Result: c:/java

3. String getName():

Returns the name of the file or directory.

|     File f = new File( "c:/java" );    System. out .println(f.getName()); |

Result: java

4. boolean exists():

Tests whether the file or directory exists.

|     File f = new File( "c:/java" );    System. out .println(f.exists()); |

Result: true

5. boolean isDirectory():

Tests whether is a directory.

|     File f = new File( "c:/java" );    System. out .println(f.isDirectory()); |

Result: true

6. boolean renameTo(File dest):

Renames the directory.

|     File f = new File( "c:/java" );    f.renameTo( new File( "c:/java_new" )); |

Result:

![](Image00116.jpg)

7. boolean createNewFile():

Creates a new, empty file only if a file with this name does not yet exist.

|     public static void main(String[] args) {        File f = new File( "c:/java_new/test.txt" );        try {            f.createNewFile();        } catch (IOException e) {            e.printStackTrace();        }    } |

Result:

![](Image00117.gif)

8. String getAbsolutePath():

Returns the absolute form of this pathname.

|     File f = new File( "c:/java_new/test.txt" );    System. out .println(f.getAbsolutePath()); |

Result: c:\java_new\test.txt

9. String getName():

Returns the name of the file.

|     File f = new File( "c:/java_new/test.txt" );    System. out .println(f.getName()); |

Result: test.txt

10. boolean exists():

Tests whether the file or directory exists.

|     File f = new File( "c:/java_new/test.txt" );    System. out .println(f.exists()); |

Result: true

11. boolean isFile():

Tests whether is a file.

|     File f = new File( "c:/java_new/test.txt" );    System. out .println(f.isFile()); |

Result: true

12. boolean delete():

Deletes the file or directory

|     File f = new File( "c:/java_new/test.txt" );    System. out .println(f.delete()); |

Result: true

FileInputStream

FileInputStream: obtains input bytes from a file. It is used for reading byte-oriented data such as image data, audio, video etc.

![](Image00118.gif)

1 . Manually create a text file : C:/java/english.txt that content below

| every day is good day |

![](Image00119.jpg)

FileInputStream read 5 byte data from C:/java/english.txt

Each character in the file occupies 1 byte

![](Image00120.gif)

int read(byte[] b):

It is used to read up to b.length bytes of data from the input stream.

Return data.length that read, if no data return -1 .

| import java.io.*;public class TestInputStream {    public static void main(String[] args) {        InputStream is = null ;        try {            is = new FileInputStream( new File( "C:/java/english.txt" )); // open file            byte [] data = new byte [5];            int len = is.read(data); //Read 5 byte  from the file into the data            String content = new String(data, 0, len); //convert byte[] to String from 0 to len            System. out .println(content);        } catch (Exception e) {            e.printStackTrace();        } finally {            try {                is.close(); //Close file            } catch (IOException e) {                e.printStackTrace();            }        }    }} |

Result:

every

2 . if you want to read all data from file: C:/java/english.txt

Need to repeatly read 5 bytes of data append to StringBuilder until the end of the file return -1 .

![](Image00121.gif)

|     public static void main(String[] args) {        InputStream is = null ;        StringBuilder sb = new StringBuilder();        try {            is = new FileInputStream( new File( "C:/java/english.txt" )); // open file            byte [] data = new byte [5];            int len = -1;            while ((len = is.read(data)) != -1){ //Read 5 byte until end of file return -1                String content = new String(data, 0 , len); //convert byte[] to String from 0 to len                sb.append(content);            }        } catch (Exception e) {            e.printStackTrace();        } finally {            try {                is.close(); //Close file            } catch (IOException e) {                e.printStackTrace();            }        }        System. out .println(sb.toString());    } |

Result:

every day is good day

FileOutputStream

FileOutputStream: is an output stream used for writing data to a file.

![](Image00122.gif)

1\. Create a file: TestOutputStream.java

| import java.io.*;public class TestOutputStream {    public static void main(String[] args) {        OutputStream os = null ;        try {            os = new FileOutputStream( new File( "c:/java/test.txt" )); //directory must exist            String content = "good morning" ;            byte [] data = content.getBytes(); //convert String to byte[]            os.write(data); // write data to file        } catch (Exception e) {            e.printStackTrace();        } finally {            try {                os.close(); //Close the output stream            } catch (IOException e) {                e.printStackTrace();            }        }    }} |

Java Thread

Thread: is a single sequential flow of control within a program.

the CPU allocates to each thread for a period of time to execute.

Car and train running at the same time

![](Image00123.jpg)

1\. Create file: TestThread.java

Create 2 Thread class : CarThread extends Thread,  TrainThread extends Thread

    Thread . start(): start a thread, and then run() will be called automatically.

| class CarThread extends Thread{    @Override    public void run() {       for ( int i=0;i<5;i++){            System. out .println( "Car Thread Run " +i);            try {                Thread. sleep (200);            } catch (InterruptedException e) {                e.printStackTrace();            }        }    }}class TrainThread extends Thread{    @Override    public void run() {        for ( int i=0;i<5;i++){            System. out .println( "Train Thread Run " +i);            try {                Thread. sleep (200);            } catch (InterruptedException e) {                e.printStackTrace();            }        }    }}public class TestThread {    public static void main(String[] args) {        CarThread carThread = new CarThread();        carThread.start();        TrainThread trainThread = new TrainThread();        trainThread.start();    }} |

Output Result:

Car Thread Run 0

Train Thread Run 0

Car Thread Run 1

Train Thread Run 1

Car Thread Run 2

Train Thread Run 2

Car Thread Run 3

Train Thread Run 3

Car Thread Run 4

Train Thread Run 4

From the results, two threads are alternately executed.

2\. Java have anther way to implement thread :

    CarThread implements Runnable, 

    TrainThread implements Runnable

| class CarThread implements Runnable{    @Override    public void run() {       for ( int i=0;i<5;i++){            System. out .println( "Car Thread Run " +i);            try {                Thread. sleep (200);            } catch (InterruptedException e) {                e.printStackTrace();            }        }    }}class TrainThread implements Runnable{    @Override    public void run() {        for ( int i=0;i<5;i++){            System. out .println( "Train Thread Run " +i);            try {                Thread. sleep (200);            } catch (InterruptedException e) {                e.printStackTrace();            }        }    }}public class TestThread {    public static void main(String[] args) {        CarThread carThread = new CarThread();        new Thread(carThread).start();        TrainThread trainThread = new TrainThread();        new Thread(trainThread).start();    }} |

Output Result:

Car Thread Run 0

Train Thread Run 0

Car Thread Run 1

Train Thread Run 1

Car Thread Run 2

Train Thread Run 2

Car Thread Run 3

Train Thread Run 3

Car Thread Run 4

Train Thread Run 4

From the results, two threads are alternately executed.

Create GUI Window Application

Java offers Swing for developing GUI (Graphical User Interface) .  Swing is the most commonly used. It is a standard Java interface to the GUI toolkit. Java with Swing is the fastest and easiest way to create the GUI applications.

1.Create a file : AirplaneGame.java in Eclipse

JFrame: class is a type of container can create a window.

JFrame.setSize(int width, int height): set the size of the frame.

JFrame.setVisible(true): set visible of the frame to open a window.

import javax.swing.* :   provides classes for java swing  GUI API.

| import javax.swing.*;public class AirplaneGame {    public static void main(String[] args) {        JFrame frame = new JFrame( "Java GUI Application" );        frame.setSize(300,300);        frame.setVisible( true );    }} |

Run as -> Java Application Open a window:

![](Image00124.jpg)

Create Canvas

Canvas: is used to draw graphics and image on screen. The Java library includes a simple package for drawing 2D graphics, called java.awt

There are several ways to create graphics in Java; we can create Canvas inherit from JPanel, A Canvas is a blank rectangular area of the screen onto which the application can draw. ![](Image00125.jpg)

1\. Create a Canvas inherit from JPanel and then add this canvas to the center of JFrame.

![](Image00126.jpg)

1\. Create a file : AirplaneGame.java in Eclipse

this.setLayout(null): must set layout null

this.setBackground(Color c): set the background color in a JPanel

| import javax.swing.*;import java.awt.*;class Canvas extends JPanel{    public Canvas(){        this .setLayout( null );        this .setBackground(Color. WHITE ); // set the background color: white    }}public class AirplaneGame {    public static void main(String[] args) {        JFrame frame = new JFrame( "GUI Canvas Application" );        Canvas canvas = new Canvas();        frame.add(canvas);  // add canvas to the center of JFrame        frame.setSize(300,300);        frame.setVisible( true );    }} |

Run as -> Java Application Open a window:

![](Image00127.jpg)

Graphics Draw on Canvas

The Graphics class provides basic drawing methods such as: drawLine , drawRect , drawString and drawImage .

When we want to draw our own graphics on the screen, we should put our graphics code inside the paintComponent() method in JPanel . The system calls it directly. So our Canvas need to override this paintComponent() method to perform our graphics code.

![](Image00128.jpg)

| class Canvas extends JPanel{    public Canvas(){        this .setLayout( null );        this .setBackground(Color. WHITE );    }    protected void paintComponent(Graphics g){        super .paintComponent(g);        // put our graphics code here    }} |

1. Draw a line on Canvas

Java uses a coordinate system where the origin is in the upper-left corner. Graphical coordinates are measured in pixels; each pixel corresponds to a dot on the screen.

![](Image00129.jpg)

g.drawLine(x1, y1, x2, y2): takes four integers values that represent the start (x1, y1) and end (x2, y2) coordinate of the line.

| import javax.swing.*;import java.awt.*;class Canvas extends JPanel{    public Canvas(){        this .setLayout( null );        this .setBackground(Color. WHITE ); // set the background color: white    }    protected void paintComponent(Graphics g){        super .paintComponent(g);        g.drawLine(50, 50, 200, 50); // draw a line from (50,50) to (200,50)    }}public class AirplaneGame {    public static void main(String[] args) {        JFrame frame = new JFrame( "GUI Canvas Application" );        Canvas canvas = new Canvas();        frame.add(canvas);  // add canvas to the center of JFrame        frame.setSize(300,200);        frame.setVisible( true );    }} |

2. Draw a Rectangle on Canvas

![](Image00130.jpg)

g . drawRect(int x, int y, int width, int height): draw a rectangle on the canvas.

| import java.awt.*;import javax.swing.*;class Canvas extends JPanel{    public Canvas(){        this .setLayout( null );        this .setBackground(Color. WHITE );    }    protected void paintComponent(Graphics g){        super .paintComponent(g);        g.drawRect(50, 50, 100, 50); // draw a Rect from (50,50),width=100 height=50    }}public class AirplaneGame {    public static void main(String[] args) {        JFrame frame = new JFrame( "GUI Canvas Application" );        Canvas canvas = new Canvas();        frame.add(canvas);        frame.setSize(300,200);        frame.setVisible( true );    }} |

3. Fill  a Rectangle on Canvas

![](Image00131.jpg)

g . fillRect(int x, int y, int width, int height): fill a rectangle on the canvas.

g.setColor(Color c): the color ( red : Color.RED, green : Color.GREEN, blue : Color.BLUE).

| import java.awt.*;import javax.swing.*;class Canvas extends JPanel{    public Canvas(){        this .setLayout( null );        this .setBackground(Color. WHITE );    }    protected void paintComponent(Graphics g){        super .paintComponent(g);        // draw a red Rect        g.setColor(Color. RED );        g.fillRect(50, 50, 100, 50);        // draw a green Rect        g.setColor(Color. GREEN );        g.fillRect(160, 50, 100, 50);        // draw a blue Rect        g.setColor(Color . BLUE );        g.fillRect(270, 50, 100, 50);    }} |

4. Draw a image on canvas .

All images in KidsLearningJavascriptImages.zip please find download from this link:

[http://en.verejava.com/download.jsp?id=1](http://en.verejava.com/download.jsp?id=1)

put the images to Project test /images

![](Image00132.jpg)

Project test/images

![](Image00133.jpg)

draw images/blue_plane.png on canvas.

1\. Create a method to load image from test/images/images/blue_plane.png

to BufferedImage

| new File(imagePath): create a file object by image path.ImageIO.read(file): read a image file save to BufferedImageg.drawImage(image, x, y, null): draw a image to canvas |

2\. Draw BufferedImage on canvas

![](Image00134.jpg)

Create a file: AirplaneGame.java in Eclipse

| import java.awt.*;import java.awt.image.BufferedImage;import java.io.*;import javax.imageio.ImageIO;import javax.swing.*;class Canvas extends JPanel{    public Canvas(){        this .setLayout( null );        this .setBackground(Color. WHITE ); // set the background color: white    }    protected void paintComponent(Graphics g) {        super .paintComponent(g);        BufferedImage blueImage=loadImage( "images/blue_plane.png" );        g.drawImage(blueImage, 50, 200, null );    }    public BufferedImage loadImage(String imagePath) {        File file = new File(imagePath);        BufferedImage bufferedImage = null ;        try {            bufferedImage = ImageIO. read (file);        } catch (IOException e) {            e.printStackTrace();        }        return bufferedImage;    }}public class AirplaneGame {    public static void main(String[] args) {        JFrame frame = new JFrame( "GUI Canvas Application" );        Canvas canvas = new Canvas();        frame.add(canvas);  // add canvas to the center of JFrame        frame.setSize(300,300);        frame.setVisible( true );    }} |

Animation

1\. The enemy plane load image draw on the top of Canvas, and then moves down automatically.

![](Image00135.jpg)

Analysis:

    1. Class: EnemyPlane , Canvas

    2. Relationship:

        2.1 Enemy plane draw on the top of Canvas: This means EnemyPlane belong to Canvas

![](Image00136.jpg)

    3. Attributes:

        3.1 Enemy plane load image : this mean EnemyPlane has image and the width and height of image attribute.

        3.2 Enemy plane draw on Canvas: this mean Sprite has x,y coordinates.

![](Image00137.jpg)

    4. Methods:

        4.1 Enemy plane need load image : we can create a class ImageUtil and a method BufferedImage loadImage(String imagePath) to load image, we can create a constructor method EnemyPlane(int x, int y, String imagePath) pass the imagePath and then call the loadImage(String imagePath) to load image .

|     public EnemyPlane( int x, int y, String imagePath){        this . x = x;        this . y = y;        this . image =ImageUtil. loadImage (imagePath); // load image to BufferedImage        this . width = this . image .getWidth();        this . height = this . image .getHeight();    } |

        4.2 Enemy plane draw on the top of Canvas: we can create a method draw(Graphics g).

|     public void draw(Graphics g){        g.drawImage( image , this . x , this . y , null ); // draw image on Canvas    } |

        4.3 Enemy plane moves down: we can create a method move(int distanceX, int distanceY) distanceX, int distanceY indicates the distance moved in the X and Y axis .

|     public void move( int distanceX, int distanceY){        this . x = this . x + distanceX;        this . y = this . y + distanceY;    } |

        4.4 The attribute x, y, width, height has its own public getter and setter methods.

![](Image00138.jpg)

        4.5 Enemy plane want to draw on the top of Canvas: we need create a constructor method Canvas() to initialize the enemy plane and then draw on the Canvas in method paintComponent(Graphics g) .

|     public Canvas() {        enemyPlane = new EnemyPlane(100, 0, "images/enemy.png" );    } |

|     protected void paintComponent(Graphics g) {        super .paintComponent(g);        enemyPlane .draw(g);        enemyPlane .move(0, 3); // enemy plane moves down 3 pixels    } |

        4.6 Enemy plane moves down automatically: We need define a inner class CanvasThread inherit from Thead in Canvas, there is a run() method. we can define " while (true) " where we repeatedly call draw(Graphics g) and move(int distanceX, int distanceY) to change the position of the enemy plane and then we call repaint() , which forces to call the paintComponent(Graphics g)   method to paint again the canvas.

![](Image00139.gif)

repaint flowchart

![](Image00140.jpg)

The final class diagram:

![](Image00141.jpg)

Create a Java Project: animation, and then create a class: ImageUtil

![](Image00142.jpg)

ImageUtil.java

| import java.awt.image.BufferedImage;import java.io.*;import javax.imageio.ImageIO;public class ImageUtil {    public static BufferedImage loadImage(String imagePath) {        File file = new File(imagePath);        BufferedImage bufferedImage = null ;        try {            bufferedImage = ImageIO. read (file);        } catch (IOException e) {            e.printStackTrace();        }        return bufferedImage;    }} |

Create a class: EnemyPlane.java

![](Image00143.jpg)

EnemyPlane.java

| import java.awt.Graphics;import java.awt.image.BufferedImage;public class EnemyPlane{    protected int x ;    protected int y ;    protected BufferedImage image ;    protected int width ;    protected int height ;    public EnemyPlane( int x, int y, String imagePath){        this . x = x;        this . y = y;        this . image =ImageUtil. loadImage (imagePath); // load image to BufferedImage        this . width = this . image .getWidth();        this . height = this . image .getHeight();    }    public void draw(Graphics g){        g.drawImage( image , this . x , this . y , null ); // draw image on Canvas    }    //Move a distance on the x,y axis    public void move( int distanceX, int distanceY){        this . x = this . x + distanceX;        this . y = this . y + distanceY;    }    public int getX() {        return x ;    }    public void setX( int x) {        this . x = x;    }    public int getY() {        return y ;    }    public void setY( int y) {        this . y = y;    }    public int getWidth() {        return width ;    }    public int getHeight() {        return height ;    }} |

Create a class: Canvas.java

![](Image00144.jpg)

Canvas.java

| import java.awt.*;import java.awt.event.*;import java.awt.image.BufferedImage;import java.io.*;import java.util.*;import javax.imageio.ImageIO;import javax.swing.*;public class Canvas extends JPanel {    private EnemyPlane enemyPlane ;    private CanvasThread canvasThread ; //inner class CanvasThread inherit from Thead    private boolean isRun = true ; // define "while (true)" where we repeatedly call  repaint()    public Canvas() {        this .setLayout( null );        this .setBackground(Color. WHITE );        this .requestFocus();        enemyPlane = new EnemyPlane(100, 0, "images/enemy.png" );        canvasThread = new CanvasThread();        canvasThread .start(); // start thread the run() method call automatically    }    protected void paintComponent(Graphics g) {        super .paintComponent(g);        enemyPlane .draw(g); // draw enemy plane        enemyPlane .move(0, 3); // enemy plane moves down 3 pixels    }    class CanvasThread extends Thread{        @Override        public void run() {            while ( isRun ){                try {                    Thread. sleep (200); // Sleep for 200 milliseconds repaint canvas                    Canvas. this .repaint();                } catch (InterruptedException e) {                    e.printStackTrace();                }            }        }    }} |

Create a class: AirplaneGame.java

![](Image00145.jpg)

AirplaneGame.java

static Canvas canvas:   If the keyPressed event takes effect, it needs to be set to static

canvas.requestFocus():   If the keyPressed event takes effect, the focus needs to be obtained

| import java.awt.*;import javax.swing.*;public class AirplaneGame {    private static Canvas canvas ;    public static void main(String[] args) {        JFrame frame = new JFrame( "GUI Canvas Application" );        canvas = new Canvas();        frame.add( canvas );        frame.setSize(300, 300);        frame.setVisible( true );        canvas .requestFocus();    }} |

Right click AirplaneGame.java, and then Run As –> Java Application

![](Image00146.jpg)

Result:

![](Image00147.jpg)

Airplane Game

In this chapter i will demonstrate how to make a basic 2D game in Java by writing a basic Airplane game.

![](Image00148.jpg)

Step:

1 . Create blue plane and then draw on the center of the bottom of the screen.

2 . Press up, down, left, and right keys to move the blue plane

3 . Press enter key to fire a bullet from the top center of the blue plane and move up

4 . If the bullet flies out of the top of the screen and the bullet disappears, press enter key can relaunch

5 . Enemy plane appear randomly from the top of the screen and move down

6 . If the enemy’s plane flies out of the bottom of the screen, the enemy’s plane disappears and reappears randomly from the top of the screen.

7 . If the bullet hits the enemy’s plane, the enemy plane explode and disappear

Analysis:

    1\. Class :                  BluePlane , EnemyPlane , Bullet , Canvas

    2. Relationship:      In the game BluePlane, EnemyPlane, and Bullet are called Sprite

Because they have the same attributes and methods, We can define Sprite as an abstract class , BluePlane , EnemyPlane , and Bullet inherit the attribute and methods from Sprite. All the Sprite will draw and move on Canvas .

![](Image00149.jpg)

    3. Attributes:

        3.1 All the Sprite will draw on Canvas . So Sprite has x,y coordinates, image and the width and height of image.

        3.2 Sprite will appear randomly and may disappear, so it has visible attribute. BluePlane, EnemyPlane, and Bullet inherit these attributes

        3.3 Canvas also have the width and height, we can define: canvasWidth and canvasHeight .

![](Image00150.jpg)

    4. Methods:

        4.1 Sprite need load image : we can create a class ImageUtil and a method BufferedImage loadImage(String imagePath) to load image, we can create a constructor method Sprite(int x, int y, String imagePath) pass the imagePath and then call the loadImage(String imagePath) to load image .

        4.2 Sprite draw on Canvas: we can create a method draw(Graphics g).

        4.3 Sprite moves: we can create a method move(int distanceX, int distanceY) distanceX, int distanceY indicates the distance moved in the X and Y axis .

        4.4 the bullet hits the enemy’s plane: we can create a method collideWith(Sprite sprite).

        4.5 The attribute x, y, width, height, visible has its own public getter and setter methods

![](Image00151.jpg)

bullet collided with the enemy plane

The absolute value of the difference between the center coordinates of the two pictures is less than the sum of half of their width and height, we think they have an intersection and they are collided

| Math.abs(): returns the absolute value of a given argument.Example: Math.abs( 10 ) = 10 , Math.abs( -10 ) = 10 |

![](Image00152.jpg)

        4.6 Sprite draw on the Canvas: we need create a constructor method Canvas() to initialize BluePlane, EnemyPlane, and Bullet and then draw on the Canvas in method paintComponent(Graphics g) .

|     public Canvas() {        this .setLayout( null );        this .setBackground(Color. WHITE );        this .requestFocus();        bluePlane = new BluePlane(100, 200, "images/blue_plane.png" );        bullet = new Bullet(-100, -100, "images/blue_bullet.png" );        bullet .setVisible( false );        enemyPlane = new EnemyPlane(-100, -100, "images/enemy.png" );        enemyPlane .setVisible( false );        canvasThread = new CanvasThread();        canvasThread .start();    } |

|     protected void paintComponent(Graphics g) {        this . canvasWidth = this .getWidth();        this . canvasHeight = this .getHeight();        super .paintComponent(g);        bluePlane .draw(g);        bullet .draw(g);        enemyPlane .draw(g);    } |

        4.7 Press up, down, left, and right keys to move the blue plane: We want to add mouse and key listeners to a Canvas: this.addKeyListener(new KeyAdapter()) . When we press any keys the method keyPressed(KeyEvent e) will called automatically.

![](Image00153.jpg)

|         this .addKeyListener( new KeyAdapter() {            public void keyPressed(KeyEvent e) {                int keyCode = e.getKeyCode();                if (keyCode == KeyEvent. VK_UP ){                    bluePlane .move(0, -10);                } else if (keyCode == KeyEvent. VK_DOWN ){                    bluePlane .move(0, 10);                } else if (keyCode == KeyEvent. VK_RIGHT ){                    bluePlane .move(10, 0);                } else if (keyCode ==  KeyEvent. VK_LEFT ){                    bluePlane .move(-10, 0);                }            }        }); |

        4.8 Press enter key to fire a bullet from the top center of the blue plane and move up:

![](Image00154.jpg)

        4.9 If the bullet visible=true move up on Canvas:

|     public void bulletMove(){        if ( bullet .isVisible()){            bullet .move(0, -10);        }    } |

        4.10 If the bullet flies out of the top of the screen and the bullet disappears

Set visible=false : .

![](Image00155.jpg)

        4.11 Enemy’s plane appear randomly from the top of the screen and move down:

![](Image00156.jpg)

        4.12 When the enemyplane move out of the canvas, the enemy plane need be destroyed set visible = false :

![](Image00157.jpg)

        4.13 If the bullet hits the enemy plane, bullet and enemy plane explode and disappear:

![](Image00158.jpg)

        4.14 Sprite moves on Canvas: We need define a inner class CanvasThread inherit from Thead in Canvas, there is a run() method. we can define " while (true) " where we repeatedly call draw(Graphics g) and move(int distanceX, int distanceY) to change the position of the enemy plane and then we call repaint() , which forces to call the paintComponent(Graphics g)   method to paint again the canvas.

![](Image00159.gif)

The final class diagram:

![](Image00160.jpg)

Create a Java Project: test, and then create a class: ImageUtil

![](Image00161.jpg)

ImageUtil.java

| import java.awt.image.BufferedImage;import java.io.*;import javax.imageio.ImageIO;public class ImageUtil {    public static BufferedImage loadImage(String imagePath) {        File file = new File(imagePath);        BufferedImage bufferedImage = null ;        try {            bufferedImage = ImageIO. read (file);        } catch (IOException e) {            e.printStackTrace();        }        return bufferedImage;    }} |

Create a class: Sprite

![](Image00162.jpg)

Sprite.java

| import java.awt.Graphics;import java.awt.image.BufferedImage;public abstract class Sprite{    protected int x ;    protected int y ;    protected int width ;    protected int height ;    protected BufferedImage image ;    protected boolean visible ;    public Sprite( int x, int y, String imagePath){        this . x = x;        this . y = y;        this . image =ImageUtil. loadImage (imagePath);        this . width = this . image .getWidth();        this . height = this . image .getHeight();    }    public void draw(Graphics g){        g.drawImage( image , this . x , this . y , null );    }    public void move( int distanceX, int distanceY){        this . x = this . x + distanceX;        this . y = this . y + distanceY;    }    public boolean collideWith(Sprite sprite){        int centerX = this . x + this .getWidth()/2;        int centerY = this . y + this .getHeight()/2;        int spriteCenterX = sprite.getX() + sprite.getWidth()/2;        int spriteCenterY = sprite.getY() + sprite.getHeight()/2;        if (Math. abs (centerX - spriteCenterX) < ( this . width /2 + sprite.getWidth()/2)            &&            Math. abs (centerY - spriteCenterY) <  ( this . height /2 + sprite.getHeight()/2))            return true ;        else            return false ;    }    public int getX() {        return x ;    }    public void setX( int x) {        this . x = x;    }    public int getY() {        return y ;    }    public void setY( int y) {        this . y = y;    }    public boolean isVisible() {        return visible ;    }    public void setVisible( boolean visible) {        this . visible = visible;    }    public int getWidth() {        return width ;    }    public int getHeight() {        return height ;    }} |

Create 3 child class: BluePlane.java, EnemyPlane.java, Bullet.java

![](Image00163.jpg)

BluePlane.java

| public class BluePlane extends Sprite{    public BluePlane( int x, int y, String imagePath) {        super (x, y, imagePath);    }} |

EnemyPlane.java

| public class EnemyPlane extends Sprite{    public EnemyPlane( int x, int y, String imagePath) {        super (x, y, imagePath);    }} |

Bullet.java

| public class Bullet extends Sprite{    public Bullet( int x, int y, String imagePath) {        super (x, y, imagePath);    }    public void move( int distanceX, int distanceY){        this . x = this . x + distanceX;        this . y = this . y + distanceY;        if ( this . y + this . height <=0){            this .setVisible( false );        }    }} |

Create a class: Canvas.java

![](Image00164.jpg)

Canvas.java

| import java.awt.*;import java.awt.event.*;import java.awt.image.BufferedImage;import java.io.*;import java.util.*;import javax.imageio.ImageIO;import javax.swing.*;public class Canvas extends JPanel {    private boolean isRun = true ;    private BluePlane bluePlane ;    private Bullet bullet ;    private EnemyPlane enemyPlane ;    private CanvasThread canvasThread ;    private int canvasWidth = 300;    private int canvasHeight = 300;    private Random rn = new Random();    public Canvas() {        this .setLayout( null );        this .setBackground(Color. WHITE );        this .requestFocus();        bluePlane = new BluePlane(100, 200, "images/blue_plane.png" );        bullet = new Bullet(-100, -100, "images/blue_bullet.png" );        bullet .setVisible( false );        enemyPlane = new EnemyPlane(-100, -100, "images/enemy.png" );        enemyPlane .setVisible( false );        canvasThread = new CanvasThread();        canvasThread .start();        this .addKeyListener( new KeyAdapter() {            public void keyPressed(KeyEvent e) {                int keyCode = e.getKeyCode();                if (keyCode == KeyEvent. VK_UP ){                    bluePlane .move(0, -10);                } else if (keyCode == KeyEvent. VK_DOWN ){                    bluePlane .move(0, 10);                } else if (keyCode == KeyEvent. VK_RIGHT ){                    bluePlane .move(10, 0);                } else if (keyCode ==  KeyEvent. VK_LEFT ){                    bluePlane .move(-10, 0);                } else if (keyCode ==  KeyEvent. VK_ENTER ){                    if (! bullet .isVisible()){                        int x = bluePlane .getX()+ bluePlane .getWidth()/2- bullet .getWidth()/2;                        int y = bluePlane .getY() - bullet .getHeight();                        bullet .setX(x);                        bullet .setY(y);                        bullet .setVisible( true );                    }                }            }        });    }    protected void paintComponent(Graphics g) {        this . canvasWidth = this .getWidth();        this . canvasHeight = this .getHeight();        super .paintComponent(g);        bluePlane .draw(g);        bullet .draw(g);        enemyPlane .draw(g);        bulletMove();        enemyPlaneMove();        collide();    }    public void bulletMove(){        if ( bullet .isVisible()){            bullet .move(0, -10);        }    }    public void enemyPlaneMove(){        if ( enemyPlane .getY() >= canvasHeight ){            enemyPlane .setVisible( false );        }        if (! enemyPlane .isVisible()){            int x = rn .nextInt( canvasWidth - enemyPlane .getWidth());            int y = - enemyPlane .getHeight();            enemyPlane .setX(x);            enemyPlane .setY(y);            enemyPlane .setVisible( true );        }        if ( enemyPlane .isVisible()){            enemyPlane .move(0,3);        }    }    public void collide(){        if ( bullet .isVisible() && enemyPlane .isVisible()){            if ( bullet .collideWith( enemyPlane )){                bullet .setX(-100);                bullet .setY(-100);                bullet .setVisible( false );                enemyPlane .setVisible( false );            }        }    }    class CanvasThread extends Thread{        @Override        public void run() {            while ( isRun ){                try {                    Thread. sleep (200); // Sleep for 200 milliseconds repaint canvas                    Canvas. this .repaint();                } catch (InterruptedException e) {                    e.printStackTrace();                }            }        }    }} |

Create a class: AirplaneGame.java

![](Image00165.jpg)

AirplaneGame.java

static Canvas canvas:   If the keyPressed event takes effect, it needs to be set to static

canvas.requestFocus():   If the keyPressed event takes effect, the focus needs to be obtained

| import java.awt.*;import javax.swing.*;public class AirplaneGame {    private static Canvas canvas ;    public static void main(String[] args) {        JFrame frame = new JFrame( "GUI Canvas Application" );        canvas = new Canvas();        frame.add( canvas , BorderLayout. CENTER ); // add canvas to center of JFrame        frame.setSize(300, 300);        frame.setVisible( true );        canvas .requestFocus();    }} |

Right click AirplaneGame.java, and then Run As –> Java Application

![](Image00166.jpg)

Result:

![](Image00148.jpg)

Thanks for learning

  [https://www.amazon.com/dp/B086SPBJ87](https://www.amazon.com/dp/B086SPBJ87)

![](Image00167.jpg)

[https://www.amazon.com/dp/B08BWT6RCT](https://www.amazon.com/dp/B08BWT6RCT)

![](Image00168.jpg)

If you enjoyed this book and found some benefit in reading this, I’d like to hear from you and hope that you could take some time to post a review on Amazon. Your feedback and support will help us to greatly improve in future and make this book even better.

You can follow this link now.

[http://www.amazon.com/review/create-review?&asin=B086PN1CJ6](http://www.amazon.com/review/create-review?&asin=B086PN1CJ6)

[](http://www.amazon.com/review/create-review?&asin=B086PN1CJ6)

Different country reviews only need to modify the amazon domain name in the link:

www.amazon.co.uk

www.amazon.de

www.amazon.fr

www.amazon.es

www.amazon.it

www.amazon.ca

www.amazon.nl

www.amazon.in

www.amazon.co.jp

www.amazon.com.br

www.amazon.com.mx

www.amazon.com.au

I wish you all the best in your future success!