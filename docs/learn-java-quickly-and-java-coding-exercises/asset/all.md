![](Images/cover00186.jpeg)

LEARN JAVA

QUICKLY

AND

JAVA

CODING EXERCISES

CODING FOR BEGINNERS

WITH HANDS ON PROJECTS

BY

J J TAM

[Introduction to Java](#part0002.xhtml__Toc60743687)

[Running Simple Hello World Applcation in Java](#part0003.xhtml__Toc60743688)

[Data Types in Java](#part0004.xhtml__Toc60743689)

[More About primitive types](#part0005.xhtml__Toc60743690)

[Operators in Java](#part0006.xhtml__Toc60743691)

[Arithmetic Operators](#part0007.xhtml__Toc60743692)

[Arithmetic Operators: ++, --](#part0008.xhtml__Toc60743693)

[Conditional operators](#part0009.xhtml__Toc60743694)

[Logical Operators](#part0010.xhtml__Toc60743695)

[Bit Wise Operators](#part0011.xhtml__Toc60743696)

[Other Operators in Java](#part0012.xhtml__Toc60743697)

[Control flow statements : Decision Making: if-then, if-else, if-else if-else](#part0013.xhtml__Toc60743698)

[Control flow statements : Decision Making: switch](#part0014.xhtml__Toc60743699)

[Control flow statements : looping : while, do-while](#part0015.xhtml__Toc60743700)

[Control flow statements : looping : for](#part0016.xhtml__Toc60743701)

[Branching statement: break](#part0016.xhtml__Toc60743702)

[Branching statement: continue](#part0017.xhtml__Toc60743703)

[Arrays](#part0018.xhtml__Toc60743704)

[One Dimensional Array](#part0019.xhtml__Toc60743705)

[Multi Dimensional Arrays](#part0020.xhtml__Toc60743706)

[Classes and Objects](#part0021.xhtml__Toc60743707)

[Declaring a class](#part0022.xhtml__Toc60743708)

[Creating Object](#part0023.xhtml__Toc60743709)

[Constructors](#part0024.xhtml__Toc60743710)

[class variables](#part0025.xhtml__Toc60743711)

[JAVA CODING EXERCISES](#part0027.xhtml__Toc60743712)

[Print hello](#part0027.xhtml__Toc60743713)

[Print the sum](#part0028.xhtml__Toc60743714)

[Divide two numbers](#part0029.xhtml__Toc60743715)

[Print the result](#part0030.xhtml__Toc60743716)

[Print multiplication table](#part0031.xhtml__Toc60743717)

[Find the area](#part0032.xhtml__Toc60743718)

[Swap two variables](#part0033.xhtml__Toc60743719)

[Print a face](#part0034.xhtml__Toc60743720)

[Fahrenheit to Celsius degree](#part0035.xhtml__Toc60743721)

[Inches to meters](#part0036.xhtml__Toc60743722)

[Adds all the digits](#part0037.xhtml__Toc60743723)

[Print the number of years and days](#part0038.xhtml__Toc60743724)

[Compute (BMI)](#part0039.xhtml__Toc60743725)

[Calculate speed in meters](#part0040.xhtml__Toc60743726)

[Divide the two specified integers](#part0041.xhtml__Toc60743727)

[Multiply two specified integers](#part0042.xhtml__Toc60743728)

[Print the sum](#part0043.xhtml__Toc60743729)

[Find the greatest of three numbers](#part0044.xhtml__Toc60743730)

[Display the multiplication table](#part0045.xhtml__Toc60743731)

[Display the pattern](#part0046.xhtml__Toc60743732)

[Print a pattern like a pyramid](#part0047.xhtml__Toc60743733)

[Display the number rhombus structure](#part0048.xhtml__Toc60743734)

LEARN JAVA

QUICKLY

# Introduction to Java

# Running Simple Hello World Applcation in Java

                                       Installation and setting up java

Installation :

   You can download the java software from the below location

      http://www.oracle.com/technetwork/java/javase/downloads/index.html

1\. Install the product.

2\. Setting up the java environment

2.a On Windows

   Suppose you install the java in the below directory,

       C:\Program Files\Java

   Then java compiler (javac) and java launcher (java) will present in

        C:\Program Files\Java\jdk1.7.0_13\bin

  We need to add the “C:\Program Files\Java\jdk1.7.0_13\bin” to system path, then we can run our java programs from any where

Follow the below steps

Step1 : Right click computer icon, and open the properties window.

![https://2.bp.blogspot.com/-2eDkOF8rUJY/UvBxH2Fb7FI/AAAAAAAAAHI/gDMGzQZsX0g/s1600/1.png](Images/image00169.jpeg)

Step 2:Click on the Advanced system settings tab as shown below. Then it will open the system properties window.

![https://1.bp.blogspot.com/-V36tJIqVIKE/UvSiZxRcKLI/AAAAAAAAAJs/ylgetP6wy3k/s1600/set.png](Images/image00170.jpeg) 

Step3: Open the System properties and choose the Advanced tab. Click on the “Environment Variable” button.

![https://3.bp.blogspot.com/-mZPcMRjy2Kg/UvB0fRTRbAI/AAAAAAAAAIQ/tp0X-Gqpo4Y/s1600/3.bmp](Images/image00171.jpeg)

Step 4

You will get a window like below. It contains 2 sections, one for user variables and other for System variables section.

![https://1.bp.blogspot.com/-gVC3iEKM6ik/UvB0nqSLNNI/AAAAAAAAAIY/qVt-qN-sSFE/s1600/4.bmp](Images/image00172.jpeg)

Edit the path from system variables section

Append the java bin path to the value filed of System variable "path".

Before appending prepend a semicolon like below

;C:\Program Files\Java\jdk1.7.0_13\bin

![https://1.bp.blogspot.com/-irgAHkSs7cM/UvB0vO8_gWI/AAAAAAAAAIg/yzZc7diKRlc/s1600/5.bmp](Images/image00173.jpeg)

Press Ok.

How to check whether you set the path properly or not

Open command prompt and type javac. If you see the output like below. You successfully set up the java environment.

![https://4.bp.blogspot.com/-qAVfAmcL8dc/UvB1dv8NydI/AAAAAAAAAIs/GekF7QD0_Hw/s1600/6.bmp](Images/image00174.jpeg)

On Open Systems

If you install the java on below directory “/usr/java7”

Then java compiler (javac) and java launcher (java) present in the directory “/usr/java7/bin”

You have to update the path like below

      export PATH=/usr/java7/bin/:$PATH

              OR

     you update the path variable in /etc/environment file for linux or .profile file in AIX like below

       export PATH=/usr/java7/bin/:$PATH

Hello World Application

 Lets start by simple program usually printing "Hello World".

Open notepad, and type the below code

class Hello{

    public static void main(String args[]){      

        System.out.println("Hello World");

    }

}

Save the file as Hello.java

Let the file saved in location "C:\java Programs". Open command prompt and goto the directory where the file is saved.

![https://2.bp.blogspot.com/-_HOHMB1ktew/UvB53FTFKmI/AAAAAAAAAJE/4Y5LAk3g_0U/s1600/7.bmp](Images/image00175.jpeg)

How to compile the Program

   Use the below command

      javac Hello.java

How to run the Program

   Use the below Command

      java Hello

After you run the program with the command "java Hello" You will see the output "Hello World" on the console

Discussion:

1\. File name should be exactly equal with your class Name. Here class name is "Hello", so i saved the file name as Hello.java.

Close Look at the Hello World program

--------------------------------------

Hello World Program has mainly 3 Components.

1\. Class Definition

2\. The Main Method

3\. println method

1\. Class Definition

class Hello{

   public static void main(String args[]){

        System.out.println("Hello World");

   }

}

Java is Object Oriented language. So Everything you write must be enclosed in the class declaration.

Basic Syntax of class is

class Class_Name{

//Statements

}

By convention, a class Name always starts with Capital letter followed by small letters like Abc, Hello, and each subsequent word in the class declaration also starts with capital letter like "ThreadExample"

2\. The Main Method

class Hello{

    public static void main(String args[]){

      System.out.println("Hello World");

   }

}

In the Java programming language, every application must contain a main method whose signature is:

public static void main(String[] args)

Don't bother about the signature of the main method, you will learn later. Now remember, Program execution always starts from main method.

3\. println method

it simply prints the information whatever you given to it, to the terminal or console.

# Data Types in Java

Java supports mainly two categories of Data Types

     1\. Primitive Types

    2\. Reference Types

1\. Primitive Types

    Java language supports 8 primitive types of data.

    Those are:

        byte, short, int, long

        float, double

        boolean

        char

        byte, short, int and long used to store integer values

        float and double used to store real values.

        Boolean used to store true or false values

        char is used to store single character.

How to define variable

    Syntax:

        dataType variableName = value;

    Example:

       int intVariable = 10;

        Here

            dataType is int

            variableName is intVariable

            value is 10

A variable is a named memory location, which holds a value.

Naming convention to define a variable

1\. A variable name must start with a character or underscore

2\. Variable name can contain alpha numeric characters

3\. varibale names shouldn't be a reserverd or keyword of java

4\. By convention a variable name starts with small letter, abd each sub sequent word starts with capital letter.

Ex: noOfChar, mySalary etc.,

Java Keywords

Keyword is a reserved word, which has special meaning defined for it.

| abstract | continue | for | New | switch |

Note: All keywords are in lower case only

/* Simple Program to Print the variable values */

class DataTypes{

     public static void main(String args[]){

        byte byteVariable = 10;

        short shortVariable = 20;

        int intVariable = 30;

        long longVariable = 40;

        float floatVariable = 10;

        double doubleVariable = 20.123;

        boolean booleanVariable = false;

        char charVariable ='A';

        System.out.println("******************************************");

        System.out.println("Value Of byte Variable is " + byteVariable);

        System.out.println("Value Of short Variable is " + shortVariable);

        System.out.println("Value Of int Variable is " + intVariable);

        System.out.println("Value Of long Variable is " + longVariable);

        System.out.println("Value Of float Variable is " + floatVariable);

        System.out.println("Value Of double Variable is " + doubleVariable);

        System.out.println("Value Of boolean Variable is " + booleanVariable);

        System.out.println("Value Of char Variable is " + charVariable);

        System.out.println("******************************************");

     }

}

Output

******************************************

Value Of byte Variable is 10

Value Of short Variable is 20

Value Of int Variable is 30

Value Of long Variable is 40

Value Of float Variable is 10.0

Value Of double Variable is 20.123

Value Of boolean Variable is false

Value Of char Variable is A

******************************************

Reference Types

In java Strings, Arrays and Objects are considered to be reference types. Will discuss more about these in later posts.

Some Points to Remember

1\. Like many other languages Java doesn't support unsigned numbers. There is no unsigned specifier in Java

class UnsignedEx{

unsigned int a;

}

When you try to compile the above class, below error is thrown.

UnsignedEx.java:2: error: <identifier> expected

   unsigned int a;

    ^

UnsignedEx.java:2: error: <identifier> expected

   unsigned int a;

   ^

2 errors

2\. In java all the bytes, shorts are promoted to int before performing operations on them, So we need to explicitly cast them.

class ConversionEx{

    public static void main(String args[]){

        byte b1 = 1;

        byte b2 = 2;

        byte b = (b1 + b2);

        System.out.println(b);

        short s1 = 1;

        short s2 = 2;

        short s = (s1 + s2);

        System.out.println(s);

    }

}

When you tries to compile the above program, compiler throws the below error

ConversionEx.java:6: error: possible loss of precision

byte b = (b1 + b2);

^

required: byte

found:    int

ConversionEx.java:10: error: possible loss of precision

short s = (s1 + s2);

^

required: short

found:    int

2 errors

To make the program compiles fine, we need to explicitly cast, after performing the operation

class ConversionEx{

    public static void main(String args[]){

        byte b1 = 1;

        byte b2 = 2;

        byte b = (byte)(b1 + b2);

        System.out.println(b);

        short s1 = 1;

        short s2 = 2;

        short s = (short)(s1 + s2);

        System.out.println(s);

    }

}

Output
3
3

3\. In Java, if one of the operand is double, then other also promoted as double, and the final result will be double

Example

class ConversionEx{

    public static void main(String args[]){

        float f1 = 1.1f;

        double f2 = 1.2f;

        float f = (f1 + f2);

        System.out.println(f);

    }

}

When you tries to compile the above program, compiler throws the below error

   ConversionEx.java:6: error: possible loss of precision

      float f = (f1 + f2);

      ^

      required: float

      found: double

1 error

To make the program run, cast the result to float.

class ConversionEx{

    public static void main(String args[]){

        float f1 = 1.1f;

        double f2 = 1.2f;

        float f = (float)(f1 + f2);

        System.out.println(f);

    }

}

Output

2.3000002

# More About primitive types

1\. sizes Of primitive data types

Data Type-Size (in bytes)

byte-1

short-2

int-4

long-8

float-4

double-8

char-2

boolean: The boolean data type has only two possible values: true and false. This data type represents one bit of information, but its "size" isn't something that's precisely defined.

2\. If you are using primitive data types as local variables, then you must initialize the variable before using. Other wise compiler will throw error.

Example

class PrimitiveDeclaration{

public static void main(String args[]){

  int var1;

  System.out.println(var1);

}

}

When you tries to compile the above program below error thrown

PrimitiveDeclaration.java:5: error: variable var1 might not have been initialized

System.out.println(var1);

^

1 error

3\. Assigning data to compatibility types

Java permits to assign a value of one data type to the value of other if types are compatible. I.e, we can assign a data of float to double, byte to int, char to int etc.,

When you assign a character variable to int variable, then int variables store the Uni code of the variable.

Example

class Compatible{

public static void main(String args[]){

  char charVar = 'a';

  int intCharVar = charVar;

  byte byteVar = 100;

  short shortVar = byteVar;

  int intVar = shortVar;

  long longVar = intVar;

  float floatVar = longVar;

  double doubleVar = floatVar;

  System.out.println(charVar);

  System.out.println(intCharVar);

  System.out.println(byteVar);

  System.out.println(shortVar);

  System.out.println(intVar);

  System.out.println(longVar);

  System.out.println(floatVar);

  System.out.println(doubleVar);

}

}

Output

a

97

100

100

100

100

100.0

100.0

4\. If you are trying to assign data of one type to the other incompatible type compiler will throw error.

Example

class Compatible{

public static void main(String args[]){

  int intVar = 10;

  boolean a = intVar;

}

}

While compiling you will get the below error

Compatible.java:6: error: incompatible types

boolean a = floatVar;

^

required: boolean

found: float

1 error

5\. If you want to assign a higher data type value to compatible lower data type, then you should externally cast it, otherwise compiler will throw an error by saying “possible loss of precision”.

Syntax:  

   dataType value1 = (dataType) value2;

class Compatible{

public static void main(String args[]){

  double doubleVar = 109.05;

  char ch = doubleVar;

  System.out.println(doubleVar);

  System.out.println(ch);

}

}

while compiling you will get the below error.

Compatible.java:5: error: possible loss of precision

char ch = doubleVar;

^

required: char

found: double

1 error

To solve the above error, we need to cast explicitly like below

class Compatible{

public static void main(String args[]){

  double doubleVar = 109.05;

  char ch = (char)doubleVar;

  System.out.println(doubleVar);

  System.out.println(ch);

}

}

6. Always assign a value to a float variable by appending “f” to it like below

float floatVar = 10.09f

other wise compiler will throw error.

class Compatible{

public static void main(String args[]){

  float floatVar = 10.09;

  System.out.println(floatVar);

}

}

While compiling you will get the below error

Compatible.java:3: error: possible loss of precision

float floatVar = 10.09;

^

required: float

found: double

1 error

To solve the above error define the float variable like below

    float floatVar = 10.09f;

# Operators in Java

An operator is a symbol which perform an operation

An operator is said to be unary, if it performs operation on single operand.

   Ex:

int a = 10;

a++;

An operator is said to be binary, if it performs operation on two operands

Ex:

int a=10, b=20;

int c = a-b;

An Operator is said to be ternary if it perform operation on three operands

Ex:

int a = 10, b=20, c;

c= (a>b) ? a : b;

Operators in java are divided into 4 major categories

Arithmetic

Conditional

Logical

Bitwise

otheroperators like (assignment, comma, etc.,)

# Arithmetic Operators

| Operator | Performs |
| + | Additon (also used for String concatenation) |
| - | Subtraction |
| / | Division |
| * | Multiplication |
| % | Gives Remainder |
| ++ | Pre or post increment |
| -- | Pre or post decrement |

class ArithmeticOperation{

public static void main(String args[]){

  int operand1 = 30;

  int operand2 = 10;

  System.out.println("Addition of operand1 and operand2 is " + (operand1 + operand2));

  System.out.println("Subtraction of operand1 and operand2 is " + (operand1 - operand2));

  System.out.println("Multiplication of operand1 and operand2 is " + (operand1 * operand2));

  System.out.println("Division of operand1 and operand2 is " + (operand1 / operand2));

  System.out.println("Remainder of operand1 and operand2 is " + (operand1 % operand2));

}

}

Output

Addition of operand1 and operand2 is 40

Subtraction of operand1 and operand2 is 20

Multiplication of operand1 and operand2 is 300

Division of operand1 and operand2 is 3

Remainder of operand1 and operand2 is 0

Some points to be Noted

1. Multiplication, Division and remainder operators has more priority than Addition and Subtraction operators.

  Example

class ArithmeticPriority{

public static void main(String args[]){

  int var1 = 10, var2 = 20;

  int result = var1+var2*var1;

  System.out.println(result);

  result = var1-var2/var1;

  System.out.println(result);

  result = var1+var2%var1;

  System.out.println(result);

}

}

Output

210

8

10

Explanation

    for the Expression

        result = var1+var2*var1

                = 10 + 20*10

                = 10 +200

                = 210

        result = var1-var2/var1

                = 10-20/10

                = 10-2

                = 8

        result = var1+var2%var1

                = 10 + 20 % 10

                = 10 + 0

                = 10

2\. Remainder operator always returns the sign of numerator

    Ex:

        5 % 2 = 1

        -5 % 2 = -1

class RemainderEx{

public static void main(String args[]){

  int var1 = 25, var2 = 10;

  System.out.println(var1%var2);

  var1= -25;

  System.out.println(var1%var2);

}

}

# Arithmetic Operators: ++, --

++ Increment operator; increments a value by 1

-- Decrement operator; decrements a value by 1

Pre increment

    Syntax:

    ++variable

      pre increment operator increments the variable value by 1 immediately.

Example

class PreIncrement{

public static void main(String args[]){

  int var = 10;

  System.out.println(++var);

}

}

Output

11

Post increment

    Syntax:

        variable++

    post increment operator increments the variable value by 1 after executing the current statement.

class PostIncrement{

public static void main(String args[]){

  int var = 10;

  System.out.println(var++);

  System.out.println(var);

}

}

Output

10

11

Pre Decrement

    Syntax:

        --variable

    pre decrement operator decrements the variable value by 1 immediately.

    Example

class PreDecrement{

public static void main(String args[]){

  int var = 10;

  System.out.println(--var);

}

}

Output

9

Post Decrement

    Syntax:

        variable--

post decrement operator decrements the variable value by 1 after executing the current statement.

class PostIncrement{

public static void main(String args[]){

  int var = 10;

  System.out.println(var--);

  System.out.println(var);

}

}

Output

10

9

Some more Examples

Class ArithmeticEx{

public static void main(String args[]){

  int var = 10;

  int result = var++ + var++ ;

  System.out.println("value of variable is " + var);

  System.out.println("Result is " +result);

  result = var++ + ++var;

  System.out.println("value of variable is " + var);

  System.out.println("Result is " +result);

  result = var++ + var--;

  System.out.println("value of variable is " + var);

  System.out.println("Result is " +result);

  result = --var + var--;

  System.out.println("value of variable is " + var);

  System.out.println("Result is " +result);

}

}

Output

value of variable is 12

Result is 21

value of variable is 14

Result is 26

value of variable is 14

Result is 29

value of variable is 12

Result is 26

# Conditional operators

Conditional operators determine if one operand is greater than, less than, equal to, or not equal to another operand.

Operator             Description

    ==                     equal to

    !=                      not equal to

    >                       greater than

    >=                     greater than or equal to

    <                       less than

    <=                     less than or equal to

Conditional operators takes two operands and return true, if the condition evaluates to true, otherwise return false.

Example

class ConditionalEx{

public static void main(String args[]){

  int a = 10, b=11;

  System.out.println("is a equals to a " + (a==a));

  System.out.println("is a equals to b " + (a==b));

  System.out.println("is a not equals to a " + (a!=a));

  System.out.println("is a not equals to b " + (a!=b));

  System.out.println("is a less than a " + (a<a));

  System.out.println("is a less than b " + (a<b));

  System.out.println("is a less than or equal to a " + (a<=a));

  System.out.println("is a less than or equal b " + (a<=b));

  System.out.println("is a greater than a " + (a>a));

  System.out.println("is a greater than b " + (a>b));

  System.out.println("is a greater than or equal to a " + (a>=a));

  System.out.println("is a greater than or equal to b " + (a>=b));

}

}

Output

is a equals to a true

is a equals to b false

is a not equals to a false

is a not equals to b true

is a less than a false

is a less than b true

is a less than or equal to a true

is a less than or equal b true

is a greater than a false

is a greater than b false

is a greater than or equal to a true

is a greater than or equal to b false

Some points to remember

1\. You can compare one type of data with another if types are compatible.

class ConditionalEx{

public static void main(String args[]){

  int a = 10;

  float b = 1.09f;

  char c = 'a';

  System.out.println("a less than b " + (a<b));

  System.out.println("a less than c " + (a<c));

}

}

Output    

a less than b false

a less than c true

2. If you try to compare two incompatible type values, compiler will throw error.

class ConditionalEx{

public static void main(String args[]){

  int a = 10;

  boolean b = true;

  System.out.println("a less than b " + (a<b));

}

}

If you try to compile the above program, you will get the below error

ConditionalEx.java:8: error: bad operand types for binary operator '<'

System.out.println("a less than b " + (a<b));

^

first type: int

second type: boolean

1 error

# Logical Operators

Java provides three logical operators, These are &&(AND), || (OR), and !(NOT)

Logical AND is also called Conditional AND

Logical OR is also called Conditional OR

Logical AND, OR are called Short circuit operators, will see why these are called short circuit soon.

Logical AND Operator

| Operand1 | Operand2 | Evaluates To |
| TRUE | TRUE | TRUE |
| TRUE | FALSE | FALSE |
| FALSE | TRUE | FALSE |
| FALSE | FALSE | FALSE |

As shown in the above table, && operator returns true if both the operands evaluates to true, otherwise returns false.

Example

class AndEx{

public static void main(String args[]){

  boolean operand1 = true;

  boolean operand2 = true;

  System.out.println((operand1 && operand2));

  operand1 = true;

  operand2 = false;

  System.out.println((operand1 && operand2));

  operand1 = false;

  operand2 = true;

  System.out.println((operand1 && operand2));

  operand1 = false;

  operand2 = false;

  System.out.println((operand1 && operand2));

}

}

Output

true

false

false

false

Why Logical AND is called short circuit operator

Since if the first statement in the expression evaluates to false, then java won't evaluates the entire expression. So Logical AND is called short circuit AND

Example

class ShortCircuitAnd{

public static void main(String args[]){

  int a = 10, b=21;

  if( (a>b) && (a++ > b) ){

   System.out.println("This statement not evaluated");

  }

  System.out.println("a is not incremented " + a);

  if( (a<b) && (a++ < b) ){

   System.out.println("This statement is evaluated");

  }

  System.out.println("a is not incremented " + a);

}

}

Output

a is not incremented 10

This statement is evaluated

a is not incremented 11

Observation

In the expression (a>b) && (a++ > b), a>b is false, so && operator won't evaluates second statement in the expression, so a is not incremented.

Logical OR Operator

| Operand1 | Operand2 | Evaluates To |
| TRUE | TRUE | TRUE |
| TRUE | FALSE | TRUE |
| FALSE | TRUE | TRUE |
| FALSE | FALSE | FALSE |

As shown in the above table, || operator returns true if any of the operand evaluates to true, otherwise returns false.

Example

class OrEx{

public static void main(String args[]){

  boolean operand1 = true;

  boolean operand2 = true;

  System.out.println((operand1 || operand2));

  operand1 = true;

  operand2 = false;

  System.out.println((operand1 || operand2));

  operand1 = false;

  operand2 = true;

  System.out.println((operand1 || operand2));

  operand1 = false;

  operand2 = false;

  System.out.println((operand1 || operand2));

}

}

Output

true

true

true

false

Why Logical OR is called short circuit operator

Since if the first statement evaluates to true, then java won't evaluates the entire expression. So Logial OR is called short circuit OR

Example

class ShortCircuitOr{

public static void main(String args[]){

  int a = 10, b=21;

  if( (a<b) || (a++ < b) ){

   System.out.println("This statement evaluated");

  }

  System.out.println("a is not incremented " + a);

  if( (a>b) || (a++ > b) ){

   System.out.println("This statement is evaluated");

  }

  System.out.println("a is incremented " + a);

}

}

Output

This statement evaluated

a is not incremented 10

a is incremented 11

Logical (!)NOT operator

| Operand | Evalutes To |
| FALSE | TRUE |
| TRUE | FALSE |

If the operand is FALSE, ! Operator evaluates it to TRUE

If the operand is TRUE, ! Operator evaluates it to FALSE

Example

class LogicalNot{

public static void main(String args[]){

  boolean a = true;

  System.out.println((!a));

  a = false;

  System.out.println((!a));

}

}

Output

false

true

# Bit Wise Operators

The Java programming language provides operators that perform bit wise and bit shift operations on integral types.

| Operator | Description |
| ~ | Inverts a bit pattern |
| << | Perform Left shift |
| >> | Perform Right Shift |
| >>> | Perform unsigned right shift |
| & | Bit wise AND |
| &#124; | Bit wise OR |
| ^ | Bit wise Exclusive OR |

Before discuss about the Bit wise operators, will discuss about Binary representations of a number

1's Complement

1's complement simply inverts the bits, if the bit is set to zero, it sets the bit to 1 and if the bit is set to 1 it sets the bit to zero.

Ex:

8 in binary            = 0 0 0 0 1 0 0 0

1's complement(8) = 1 1 1 1 0 1 1 1

2's complement

Negative numbers are stored in 2's complement form. i.e., -8 is 2's complement of 8.

2's complement is sum of (1's complement of a number + 1)

Ex:

8 in binary            = 0 0 0 0 1 0 0 0

1's complement(8) = 1 1 1 1 0 1 1 1

2's complement(8) =               (+) 1

                                             -----------------

                                             1 1 1 1 1 0 0 0

                                              ----------------

there for -8 in 2's complement form is 11111000

Inversion (~)

Inversion operator change the bit value to zero, if it is one and change the bit value to one if it is zero.

Example

byte a = 7;

a in binary format is       0 0 0 0 0 1 1 1

~(a) in binary format is  1 1 1 1 1 0 0 0

~(a) represents -8 in binary format.

Example

class BitWiseEx{

public static void main(String args[]){

  byte byteVar = 7;

  System.out.println("Value of Byte variable is " + byteVar);

  System.out.println("Value of Byte variable after inversion is " + ~(byteVar));

}

}

Output

Value of Byte variable is 7

Value of Byte variable after inversion is -8

Bit Wise Left Shift(<<)

Left shift operator simply shifts all the bits to one bit left, i.e, it simply doubles the value.

Syntax:

    variable << n

    left shift the variable by 'n' number of times.

    Variable << n is equals to variable = variable * 2 power n

        int var = 2;

        var << 1 = 2 * 2 power 1 = 4

        var << 2 = 2 * 2 power 2 = 8

        var << 9 = 2 * 2 power 9 = 1024

Example

class BitWiseEx{

public static void main(String args[]){

  byte byteVar = 7;

  System.out.println("Value of Byte variable is " + byteVar);

  System.out.println("After shifting 1 bit left " + (byteVar<<1));

  System.out.println("After shifting 2 bits left " + (byteVar<<2));

  System.out.println("After shifting 3 bits left " + (byteVar<<3));

  System.out.println("After shifting 4 bits left " + (byteVar<<4));

  System.out.println("After shifting 5 bits left " + (byteVar<<5));

  System.out.println("After shifting 6 bits left " + (byteVar<<6));

  System.out.println("Value of Byte variable is " + byteVar);

}

}

Output

Value of Byte variable is 7

After shifting 1 bit left 14

After shifting 2 bits left 28

After shifting 3 bits left 56

After shifting 4 bits left 112

After shifting 5 bits left 224

After shifting 6 bits left 448

Value of Byte variable is 7

Bit Wise Right Shift(>>)

   Right shift operator simply shifts all the bits to one bit right, i.e, it simply half (divide by 2) the value

   Syntax:

   variable >> n

      right shift the variable by 'n' number of times.

   Variable >> n is equals to variable = variable / 2 power n

   int var = 128;

   var >> 1 = 128 / (2 power 1) = 64

   var >> 2 = 128 / (2 power 2) = 32

Example

class BitWiseEx{

public static void main(String args[]){

  int intVar = 128;

  System.out.println("Value of int variable is " + intVar);

  System.out.println("After shifting 1 bit Right " + (intVar>>1));

  System.out.println("After shifting 2 bits Right " + (intVar>>2));

  System.out.println("After shifting 3 bits Right " + (intVar>>3));

  System.out.println("After shifting 4 bits Right " + (intVar>>4));

  System.out.println("After shifting 5 bits Right " + (intVar>>5));

  System.out.println("After shifting 6 bits Right " + (intVar>>6));

  System.out.println("After shifting 6 bits Right " + (intVar>>7));

  System.out.println("Value of int variable is " + intVar);

}

}

Output

Value of int variable is 128

After shifting 1 bit Right 64

After shifting 2 bits Right 32

After shifting 3 bits Right 16

After shifting 4 bits Right 8

After shifting 5 bits Right 4

After shifting 6 bits Right 2

After shifting 6 bits Right 1

Value of int variable is 128

Bit Wise unsigned Right Shift(>>>)

   shifts all the bits to one bit right, and make the left most bit to zero

class BitWiseEx{

public static void main(String args[]){

  int intVar = -128;

  System.out.println("Value of int variable is " + intVar);

  System.out.println("After shifting 1 bit Right " + (intVar>>>1));

}

}

Output

Value of int variable is -128

After shifting 1 bit Right 2147483584

Explanation

-128 in 2's complement form is

11111111 11111111 11111111 10000000

>>> shifts the one bit right and replace leftmost bit by zero

so (-128>>>1) is like below sequence

01111111 11111111 11111111 11000000

Bit Wise AND(&), OR(|), Exclusive OR(^)

| Bit 1 | Bit 2 | & | &#124; | ^ |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

Example

class BitWiseEx{

public static void main(String args[]){

  byte a = 8;

  byte b = 9;

  System.out.println("a & b is " + (a&b));

  System.out.println("a | b is " + (a|b));

  System.out.println("a ^ b is " + (a^b));

}

}

Output

a & b is 8

a | b is 9

a ^ b is 1

Explanation

   a    = 0000 1000

   b    = 0000 1001

   a&b = 0000 1000

   a    = 0000 1000

   b    = 0000 1001

   a|b = 0000 10001

   a     = 0000 1000

   b     = 0000 1001

   a^b = 0000 0001

Note:

   Bit wise operators are applicable only to integer values like byte, short etc., these are not applicable to float, double, Boolean.

# Other Operators in Java

Assignment Operator

   Assignment operator is used to assign a value to a variable.

   Syntax

      type variable = value;

   Example

      int a = 10.

      int b = 20

Java supports compound assignments

   Compound Assignment

      Syntax:

         variable operator= value

      Example:

         lets say

         int a = 10;

         a+=10 evaluates to a=a+10

| Compound Operator | Example | Description |
| += | a+=10 | a=a+10 |
| -= | a-=10 | a=a-10 |
| *= | a*=10 | a=a*10 |
| /= | a/=10 | a=a/10 |

Example Program

class CompoundAssignment{

public static void main(String args[]){

  int var1 = 100;

  int sum=10, sub=10, mul=10, div=1000;

  System.out.println("sum+var1 is " + (sum+=var1));

  System.out.println("sub-var1 is " + (sub-=var1));

  System.out.println("mul*var1 is " + (mul*=var1));

  System.out.println("div/var1 is" + (div/=var1));

}

}

Output

sum+var1 is 110

sub-var1 is -90

mul*var1 is 1000

div/var1 is10

The Type Comparison Operator instanceof

The instanceof operator compares an object to a specified type. You can use it to test if an object is an instance of a class, an instance of a subclass, or an instance of a class that implements a particular interface.

Example

class InstanceOfEx{

public static void main(String args[]){

  Object obj = new Object();

  System.out.println(obj instanceof Object);

  System.out.println(obj instanceof InstanceOfEx);

}

}

Output

true

false

Don't worry much about this program, you will learn about this while discussing about class and object.

Ternary operator( ?: )

   Returns one of two expressions depending on a condition.

    Syntax

       test ? expression1 : expression2

          Returns expression1 if the “test” condition evaluates to true other wise returns expression 2.

Example

class TernaryEx{

public static void main(String args[]){

  int a = 100;

  int flag = a>10 ? 1 : 0;

  System.out.println(flag);

  flag = a>1000 ? 1 : 0;

  System.out.println(flag);

}

}

Output

1

0

Observation

See the statement “flag = a>10 ? 1 : 0”, a>10 is true, so 1 is returned and assigned to the flag

# Control flow statements : Decision Making: if-then, if-else, if-else if-else

Java provides control flow statements

     for decision making (if, if-else, switch) and

     for looping (for, while, do-while)

Block of statements

In java the statements between { } are called block of statements.

     {

          //block of code

     }

Decision making statements

if statement

“ if ” tell the program execute the section of code when the condition evaluates to true.

     Syntax

          if(condition){

               // Executes if the condition true

          }

Example

class Grades{

public static void main(String args[]){

  int marks = 20;

  if(marks < 35 ){

   System.out.println("You failed in the Exam. Better luck next time");

  }

}

}

Output

You failed in the Exam. Better luck next time

Some points to remember

1\. In java the condition in the if must evaluates to boolean value, other wise compiler will throw error

Example

class Grades{

public static void main(String args[]){

  int var1;

  if(var1 = 10){

  }

}

}

When you try to compile the above program, you will get the below error

Grades.java:5: error: incompatible types

if(var1 = 10){

^

required: boolean

found: int

1 error

if-else statement

    Syntax:

    if(condition){

    }

    else{

    }

If the condition true, then if block code executed. other wise else block code executed.

Example

class Grades{

public static void main(String args[]){

  int marks = 36;

  if(marks < 35)

   System.out.println("You are failed");

  else

   System.out.println("You are passed");

}

}

Output

You are passed

Observation

In the above program we haven't written the if, else block codes in between { }, since if there is only one statement in between the blocks, we can omit { }.

if-else if-else

By using if-else if-else construct, you can choose number of alternatives.

An if statement can be followed by an optional else if...else statement, which is very useful to test various conditions using single if...else if statement.

class Grades{

public static void main(String args[]){

  int marks = 69;

  if(marks < 35)

   System.out.println("You are failed");

  else if( marks < 50)

   System.out.println("You are passed and got third class");

  else if( marks < 60)

   System.out.println("You are passed and got second class");

  else if( marks < 70)

   System.out.println("You are passed and got first class");

  else

   System.out.println("You are passed and got distinction");

}

}

Output

You are passed and got first class

# Control flow statements : Decision Making: switch

The body of a switch statement is known as a switch block. A statement in the switch block can be labelled with one or more case or default labels. The switch statement evaluates its expression, then executes all statements that follow the matching case label.

switch works with the byte, short, char, and int primitive data types. It supports enums also

java 7 supporting strings also in switch case evaluation, and a few special classes that wrap certain primitive types: Character, Byte, Short, and Integer.

Integer, Char, Byte, Short are called wrapper classes. Will discuss about these more on coming posts.

Example

class SwitchEx{

public static void main(String args[]){

  int day = 5;

  switch(day){

   case 1:

    System.out.println("Sunday");

    break;

   case 2:

    System.out.println("Monday");

    break;

   case 3:

    System.out.println("Tueday");

    break;

   case 4:

    System.out.println("Wednesday");

    break;

   case 5:

    System.out.println("ThursDay");

    break;

   case 6:

    System.out.println("Friday");

    break;

   case 7:

    System.out.println("Saturday");

    break;

   default:

    System.out.println("You entered wrong day number");

  }

}

}

Output

ThursDay

Explanation

As you see in the above program, variable “day” set to the value 5\. So in the switch case, case 5 is executed. If the day is set to 1, then case 1 will execute and come out of the switch.

You can see in the above program, each case has a break statement associates with it, is it necessary ? Yes of course, if you don't specify the break for case statements, then all the case statement below the evaluated case are executed.

And one more thing is, case statements need not be in proper order. They can be written in any way.

class SwitchEx{

public static void main(String args[]){

  int day = 5;

  switch(day){

   case 2:

    System.out.println("Monday");

   case 3:

    System.out.println("Tueday");

   case 4:

    System.out.println("Wednesday");

   case 5:

    System.out.println("ThursDay");

   case 6:

    System.out.println("Friday");

   case 7:

    System.out.println("Saturday");

   case 1:

    System.out.println("Sunday");

   default:

    System.out.println("You entered wrong day number");

  }

}

}

Output

ThursDay

Friday

Saturday

Sunday

You entered wrong day number

As you see in the above program, “day” is set to 5, and there is no breaks in the corresponding cases. So case 5, 6,7, 1 and default are executed.

One more thing is in the above program, case 1 came after 7, it is acceptable behaviour in java.

What is the necessity of default here

If no case is evaluated, then default executes, just like else block in if-else if-else ladder.

Example

class SwitchEx{

public static void main(String args[]){

  int day = 9;

  switch(day){

   case 1:

    System.out.println("Sunday");

    break;

   case 2:

    System.out.println("Monday");

    break;

   case 3:

    System.out.println("Tueday");

    break;

   case 4:

    System.out.println("Wednesday");

    break;

   case 5:

    System.out.println("ThursDay");

    break;

   case 6:

    System.out.println("Friday");

    break;

   case 7:

    System.out.println("Saturday");

    break;

   default:

    System.out.println("You entered wrong day number");

  }

}

}

Output

You entered wrong day number

Some points to remember

1\. When to use if-else if -else ladder, than switch ?

Switch case won't supports range checks like age>30, year<2000 etc., in those cases better to go for if-else if-else ladder.

# Control flow statements : looping : while, do-while

while

while statement executes a block of statements until a particular condition is true

Syntax

    while (expression) {

      //statements

}

The expression in the while statement must evaluates to a boolean value, other wise compiler will throw error. While statement first evaluates the expression, until the expression evaluates to true, it  executes the code inside the while block, other wise it comes out of the while loop.

Example : Print numbers from 0 to 9 using while loop.

class WhileEx{

public static void main(String args[]){

  int var1 = 0;

  while(var1 < 10){

   System.out.println(var1);

   var1++;

  }

}

}

Output

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

do-while

   do-while is also a loop construct like while, but evaluates its expression at the bottom of the loop instead of the top.

    Syntax

    do {

        //statement(s)

    } while (expression);

Example

class DoWhileEx{

public static void main(String args[]){

  int var1 = 0;

  do{

   System.out.println(var1);

   var1++;

  }while(var1<10);

}

}

Output   

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

Some points to Remember

1\. What is the difference between while and do-while ?

 Statements within the do block are always execute at least once even if the expression evaluates to false.

Example

class CompareLoop{

public static void main(String args[]){

  boolean flag = false;

  while(flag)

   System.out.println("I am in while loop");

  do

   System.out.println("I am in do-while loop");

  while(flag);

}

}

Output

I am in do-while loop

Observation

Note that do-while executed, even if the expression “flag” is false. And if you have only one statement, then no need to put the line in between blocks{ }

# Control flow statements : looping : for

The for statement provides a compact way to iterate over a range of values.

Syntax

    for(initialization; condition; update){

        //statements to be executed

    }

for loop execute the statements until the condition evaluates to false.

Initialization section executed only once, at the starting of loop.

Condition section evaluated every time, before executing the loop statements

update section executes immediately after every execution of loop finishes.

Example : Printing numbers from 0 to 9

class ForEx{

public static void main(String args[]){

  int var1;

  for(var1 = 0; var1 < 10; var1++){

   System.out.println(var1);

  }

}

}

Output

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

Some points to remember

1\. You can declare a variable inside the for loop itself

        for(int i=0; i<10; i++) is a valid construct

2\. for( ; ; )

     Above for loop run for infinite times.

# Branching statement: break

The break Statement

We already seen the use of break in switch case. Similarly, break is used in while, do-while and for loops. Break has two forms in java.

   1\. unlabelled break

   2\. labelled break

unlabelled break

   Example

class BreakEx{

public static void main(String args[]){

  for(int i=0; i < 10; i++){

   if(i==5) break;

   System.out.println(i);

  }

  System.out.println("I am out of the loop");

}

}

Output

0

1

2

3

4

I am out of the loop

As you in the above program, when variable “i” reached to 5, break is called, and execution comes out of the loop

labelled break

   label is a group of statements, identified by using labelname.

Syntax

    labelName:{

      statement 1

      statement 2

      …....

      statement N

    }

Example

class BreakEx{

public static void main(String args[]){

  myLoop: {

   for(int i=0; i < 10; i++){

    if(i==5) break myLoop;

    System.out.println(i);

   }

   System.out.println("I am also in label");

  }

  System.out.println("I am out of the loop");

}

}

Output

0

1

2

3

4

I am out of the loop

As you see in the above program label name is myLoop. When variable 'i' value reaches to 5,  execution comes out of the label.

# Branching statement: continue

continue statement skips the current iteration of a for, while, do-while loops. Just like break, continue also has two forms.

    1\. unlabelled continue

    2\. labelled continue

Unlabelled continue

    Syntax

        continue;

Example: Count the number of odd values from 0 to 10

class ContinueEx{

public static void main(String args[]){

  int counter = 0;

  for(int i=0; i < 11; i++){

   if(i % 2 == 0)

    continue;

   System.out.println(i);

   counter++;

  }

  System.out.println("Total number of odd numbers from 0 to 10 is " + counter);

}

}

Output

1

3

5

7

9 

Total number of odd numbers from 0 to 10 is 5

Labelled continue

     Syntax

     continue labelName;

Example

class ContinueEx{

public static void main(String args[]){

  int counter = 0;

  myLabel:

   for(int i=0; i < 11; i++){

    if( i < 10)

     continue myLabel;

    System.out.println(i);

   }

  System.out.println("I am out of the label");

}

}

Output

10

I am out of the label

# Arrays

An array is a series of elements of the same type placed in contiguous memory locations. Elements in the array are accessed by using index positions.

Suppose if you want to calculate sum of 9 integers, you have to define 9 variables like below

    int var1, var2, var3, var4, var5, var6, var7, var8, var9;

    var1 = 5;

    var2 = -10;

    var3 = 7;

    var4 = 8

    var5 = 11;

    var6 = 12;

    var7 = 14;

    var8 = 21;

    var9 = 0;

By using new keyword we can declare like below

    int var[] = new int[9];

    var[0] = 5;

    var[1] = -10;

    var[2] = 7;

    var[3] = 8

    var[4] = 11;

    var[5] = 12;

    var[6] = 14;

    var[7] = 21;

    var[8] = 0;

As you see, Array indexes starts from 0\. var[0] represents 5, var[2] represents 7 and so on.

# One Dimensional Array

Syntax:

    dataType arrayName[] = new dataType[size];

          (OR)

    dataType arrayName[];

    arrayName = new dataType[size];

Here the dataType can be any primitive type or reference type.

Size is the How many number of elements are stored into the array.

Example

    char arr[] = new char[9];

        (OR)

    char arr[];

    arr = new char[9];

Above two declarations are syntactically correct and create an array named “arr” of type char and has the capacity to store 9 characters.

How to define an Array

You can assign elements to the array using indexes or at the time of creation. Array index starts from zero. If the array of size 'n', then the maximum index is 'n-1', since the index starts from 0.

Assigning values using indexes

    char arr[] = new char[9];

    arr[0] = 'H';

    arr[1] = 'E';

    arr[2] = 'L';

    arr[3] = 'L';

    arr[4] = 'O';

    arr[5] = 'J';

    arr[6]='A';

    arr[7] = 'V';

    arr[8] = 'A';

Assigning values At the time of creation

    char arr[] = {'H', 'E', 'L', 'L', 'O', 'J', 'A', 'V', 'A'};

Elements in the array “arr” store like following

![https://3.bp.blogspot.com/-H3cfhR3m6-8/UvXQj6EGNsI/AAAAAAAAAJ8/CFm8SWTZHqI/s1600/Array3.bmp](Images/image00176.jpeg)

Example 1

class ArrayEx{

public static void main(String args[]){

  char arr[] = new char[9];

  arr[0] = 'H';

  arr[1] = 'E';

  arr[2] = 'L';

  arr[3] = 'L';

  arr[4] = 'O';

  arr[5] = 'J';

  arr[6] = 'A';

  arr[7] = 'V';

  arr[8] = 'A';

  System.out.println(arr);

}

}

Output

HELLOJAVA

Example 2

class ArrayEx{

public static void main(String args[]){

  char arr[] = {'H', 'E', 'L', 'L', 'O', 'J', 'A', 'V', 'A'};

  System.out.println(arr);

}

}

Output

HELLOJAVA

As you see, when you pass the array name as an argument to println method, it prints the entire array data to the console.

How to declare number of Arrays at a time

    Syntax

    dataType[] arr1, arr2;

    Example

class ArrayEx{

public static void main(String args[]){

  char[] arr1, arr2;

  arr1 = new char[6];

  arr2 = new char[4];

  arr1[0] = 'H';

  arr1[1] = 'E';

  arr1[2] = 'L';

  arr1[3] = 'L';

  arr1[4] = 'O';

  arr1[5] = ' ';

  arr2[0] = 'J';

  arr2[1] = 'A';

  arr2[2] = 'V';

  arr2[3] = 'A';

  System.out.print(arr1);

  System.out.println(arr2);

}

}

Output

HELLO JAVA

How to find the length of Array

java provides a property called “length” for an array to calculate the length of an array

   syntax

arrayName.length;

returns the size of the array.

Example

class ArrayEx{

public static void main(String args[]){

  char[] arr1, arr2;

  arr1 = new char[6];

  arr2 = new char[4];

  System.out.println("Length of Array1 is " +arr1.length);

  System.out.println("Length of Array2 is " +arr2.length);

}

}

Output

Length of Array1 is 6

Length of Array2 is 4

How to Traverse Array Elements Using Loops

Example: Calculate the sum of numbers from 1 to 10 using Arrays

class SumOfNum{

public static void main(String args[]){

     int arr[] = {1,2,3,4,5,6,7,8,9,10};

     int sum = 0;

     /* Initialize the array */

     for(int i=0; i < 10; i++)

          sum = sum + arr[i];

     System.out.println("Sum of Numbers is " + sum);

}

}

Output

Sum of Numbers is 55

Some points to remember

1\. If you try to access an array with illegal index, then compiler throws “ArrayIndexOutOfBoundsException”

    Example

class ArrayEx{

public static void main(String args[]){

  int arr[] = new int[10];

  arr[11] = 100;

}

}

When you try to compile, compiler will throw the below error

Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 11

            at ArrayEx.main(ArrayEx.java:5)

2.If Program defined with array of negative size, then program compiles fine, but “NegativeArraySizeException” will be thrown at run time.

    Example

class ArrayEx{

public static void main(String args[]){

  String arr[] = new String[-10];

}

}

Program compiles fine, but run time error come

Exception in thread "main" java.lang.NegativeArraySizeException

    at ArrayEx.main(ArrayEx.java:3)

3\. Array size is always an integer, so it is correct to give array size as byte, short and int. But not long.

     Example 1

class ArrayEx{

public static void main(String args[]){

  byte b = 10;

  short s = 11;

  int i = 5;

  String arr1[] = new String[b];

  String arr2[] = new String[s];

  String arr3[] = new String[i];

  System.out.println(arr1.length +"\t" + arr2.length + "\t" + arr3.length);

}

}

Output

10 11 5

Example 2

class ArrayEx{

public static void main(String args[]){

  long i = 10;

  String arr3[] = new String[i];

}

}

When you try to compile, you will get compiler error like below

ArrayEx.java:6: error: possible loss of precision

String arr3[] = new String[i];

^

required: int

found: long

1 error

4\. The problem with Arrays is, they can't grow dynamically, once Array is initialized, you can't change the size of the array.

# Multi Dimensional Arrays

Multidimensional arrays are actually arrays of arrays.

   Syntax to create two dimensional Array

dataType arrayName[][] = new dataType[size1][size2]

(OR)

dataType[][] arrayName;

arrayName = new dataType[size1][size2]

for Example consider the array of size 5*4.

int arr[][] = new int[5][4];

| 00 | 01 | 02 | 03 |
| 10 | 11 | 12 | 13 |
| 20 | 21 | 22 | 23 |
| 30 | 31 | 32 | 33 |
| 40 | 41 | 42 | 42 |

Table 1 : Array indexes

| 100 | 553 | 512 | -9 |
| 12 | 32 | 43 | 56 |
| 1 | 3 | 5 | 7 |
| 9 | -87 | -98 | 0 |
| -12 | 46 | 78 | 97 |

Table 2 : Values stored in Array

When you compare table1 and table 2

arr[0][0] = 100

arr[0][1] = 553

arr[0][2] = 512

arr[0][3] = -9

Example

class ArrayEx{

public static void main(String args[]){

  int arr[][] = new int[5][4];

  arr[0][0] = 100;

  arr[0][1] = 553;

  arr[0][2] = 512;

  arr[0][3] = -9;

  arr[1][0] = 12;

  arr[1][1] = 32;

  arr[1][2] = 43;

  arr[1][3] = 56;

  arr[2][0] = 1;

  arr[2][1] = 3;

  arr[2][2] = 5;

  arr[2][3] = 7;

  arr[3][0] = 9;

  arr[3][1] = -87;

  arr[3][2] = -98;

  arr[3][3] = 0;

  arr[4][0] = -12;

  arr[4][1] = 46;

  arr[4][2] = 78;

  arr[4][3] = 97;

  /*Display Elements */

  for(int i=0; i<5; i++){

   for(int j=0; j<4; j++){

    System.out.print(arr[i][j] +"\t");

   }

   System.out.println();

  }

}

}

Output

100 553 512 -9

12 32 43 56

1 3 5 7

9 -87 -98 0

-12 46 78 97

# Classes and Objects

Before, moving in depth details of Object oriented and java features, will discuss what an object and class is.

Objects and class in Real World scenario

Object

An Object is a real world entity. For example, book, cat, box, bus, keyboard, person, screen, cell phone etc., all are objects.

So How can we differentiate objects

1\. Depend on their properties

2\. Depend on their behaviors

Differentiating two objects based on their properties

Lets say, there are two persons A and B, we already discussed, each real time entity is an object. So these two persons are objects.

First lets try to find what are the possible properties for the person object

Possible properties for a person

height, weight, color, Education Qualification, country, address are all come under person properties.

Now by comparing these properties we can easily differentiate two persons.

| Properties | Person A | Person B |
| Height | 6ft | 5.5ft |
| Weight | 75Kg | 60Kg |
| Color | white | Black |
| Country | India | America |

As shown in the above table, both the persons has their own properties, So we can differentiate based on them.

Differentiating two objects based on their behavior

consider the same two persons A and B. will try to figure out possible behaviors for the person object

Possible behaviors are

walk, run, swim, eat, sleep, see, hear etc., Now by comparing these behaviors we can easily differentiate two persons. 

| Behavior | Person A | Person B |
| Walk | 10km/hr | 12km/hr |
| run | 20km/hr | 18km/hr |
| sleep | 8 Hrs/day | 6Hrs/day |

Class

In normal terms I call class as a category.

All persons come under Human category

cat, lion, Elephant come under Animals Category

So a class or category is a group of objects with similar properties and behaviors.

Objects and class in Programming Terminology

What Is an Object?

An object is a software bundle of related state and behavior. The main advantage of java is you can compare objects in Java with real world objects. So it is very easy to work with objects in Java

What Is a Class?

A class is a blueprint or prototype from which objects are created.

# Declaring a class

class in java declared with a keyword “class”

    Syntax

    class ClassName{

    }

   Example

    class Person{

    }

How to declare properties of a class

  Each property is represented by a variable.

class Person{

float height, weight;

String color, country;

}

Since height and weight are real type values, so these are declared as a float. Where as color and country are of type String. So these are declared as type string.

Note:

   We haven't discussed anything about strings, just note that string a group of characters.

How to define behaviors for a class

   Each behaviour in Java represented by a method.

   Method is a block of statements, with a name associated with it.

      Syntax:

         returnType methodName(parameters){

         }

      Example

         int sum(int a, int b){

            return (a+b);

         }

      here,

         returnType is int

         parameters are a, b.

return value must match with the return type of the method.

After adding the behaviors for the class Person, code changed like below

class Person{

float height, weight;

String color, country;

float getHeight(){

  return height;

}

float getWeight(){

  return weight;

}

String getColor(){

  return color;

}

String getCountry(){

  return country;

}

}

# Creating Object

Syntax to create an Object

     ClassName objectName = new ClassName();

     Example

          Person personA = new Person();

          Here Person is the class name

          personA is the object created for the class Person.

    Once the class is defiined, you can create any number of objects to it.

               Person personB = new Person();

               Person personC = new Person();

How to access properties of an object

     java provides '.' opertor to access th properties of an object.

     Syntax:

          objectName.propertyName = value;

     Example

          personA.height = 6;

          personB.height = 5.5;

How to call the behaviors

     Just like how you are accessing properties, you can call the behaviours.

     Syntax

     objectName.behavior();

     Example

     personA.getHeight();

     personB.getHeight();

Complete Working Example of Person class

class Person{

float height, weight;

String color, country;

float getHeight(){

  return height;

}

float getWeight(){

  return weight;

}

String getColor(){

  return color;

}

String getCountry(){

  return country;

}

public static void main(String args[]){

  /* Declaring two person objects */

  Person personA = new Person();

  Person personB = new Person();

  /* Setting properties for personA object */

  personA.height = 6;

  personA.weight = 75;

  personA.color = "White";

  personA.country = "India";

  /* Setting properties for personB object */

  personB.height = 5.5f;

  personB.weight = 76;

  personB.color = "Black";

  personB.country = "America";

  /* Calling the behaviors and printing the details of personA */

  System.out.println("PersonA Height is " + personA.getHeight());

  System.out.println("PersonA Weight is " + personA.getWeight());

  System.out.println("PersonA color is " + personA.getColor());

  System.out.println("PersonA country is " + personA.getCountry());

  System.out.println();

  /* Calling the behaviors and printing the details of personB */

  System.out.println("PersonB Height is " + personB.getHeight());

  System.out.println("PersonB Weight is " + personB.getWeight());

  System.out.println("PersonB color is " + personB.getColor());

  System.out.println("PersonB country is " + personB.getCountry());

}

}

Output

PersonA Height is 6.0

PersonA Weight is 75.0

PersonA color is White

PersonA country is India

PersonB Height is 5.5

PersonB Weight is 76.0

PersonB color is Black

PersonB country is America

# Constructors

Constructors are used to initialize object at the time of creation.

syntax

    modifier className(){

    }

Here modifier is anything like private, public, protected, default. Will discuss more about modifiers in the packages section. As you see constructors don't have any return type and constructor name equals to the class name.

If you don't provide the constructor, then compiler provides the default constructor for your class.

Example

class Box{

int width,height;

Box(){

  width = 10;

  height = 10;

}

public static void main(String args[]){

  Box b1 = new Box();

  System.out.println(b1.width +"\t"+b1.height);

}

}

Output

10 10

As you see in the above program, Box() is initializing the properties for an object to 10 at the time of creation.

Overloading Constructors

Just like overloading methods, we can overload the constructors also.

Example

class Box{

int width,height;

Box(){

  width = 0;

  height = 0;

}

Box(int h){

  width = height = h;

}

Box(int w, int h){

  width = w;

  height = h;

}

public static void main(String args[]){

  Box b1 = new Box();

  Box b2 = new Box(15);

  Box b3 = new Box(15, 25);

  System.out.println(b1.width +"\t"+b1.height);

  System.out.println(b2.width +"\t"+b2.height);

  System.out.println(b3.width +"\t"+b3.height);

}

}

Output

0 0

15 15

15 25

Some points to Remember

1\. Can we make constructor and method with the same name ?

    Yes, it is valid in Java   

  Example

class Box{

int width,height;

Box(){

  width = 10;

  height = 10;

}

void Box(){

  System.out.println(width +"\t"+height);

}

public static void main(String args[]){

  Box b1 = new Box();

  System.out.println(b1.width +"\t"+b1.height);

}

}

Output

10 10

2\. Can constructors throw exceptions ?

Yes, Constructors are like special methods in java.

Example

   public Socket(String host,int port)throws UnknownHostException,IOException

Socket class in the java.net.Socket, throws UnknownHostException, if the IP address of the host could not be determined.

# class variables

As we know, instance variables are associated with object, where as class variables associated with class, i.e, available for all objects.

    Syntax

         static dataType variableName;

    Example

        static int count;

static variables are accessed by using class name.

    Syntax to access static variable

        ClassName.variablename

Example : program to count number of objects created for a class

class Person{

static int count =0;

Person(){

  count++;

}

}

class PersonTest{

public static void main(String args[]){

  Person personA = new Person();

  Person personB = new Person();

  System.out.println("Number Of persons created are " + Person.count);

}

}

Output

Number Of persons created are 2

JAVA

CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

JAVA CODING EXERCISES

Print hello

And your name

On a separate lines

JAVACODE

import java.util.Scanner;

public class Main {

  public static void main(String[] args)

  {

    Scanner input = new Scanner (System.in);

    System.out.print("Input your first name: ");

    String fname = input.next();

    System.out.print("Input your last name: ");

    String lname = input.next();

    System.out.println();

    System.out.println("Hello \n"+fname+" "+lname);

  }

}

OUTPUT

Input your first name: JJ

Input your last name: TAM

Hello

JJ TAM

Print the sum

Of two numbers

JAVACODE

import java.util.Scanner;

public class Main {

  public static void main(String[] args)

  {

    Scanner input = new Scanner (System.in);

    System.out.print("Input the first number: ");

    int num1 = input.nextInt();

    System.out.print("Input the second number: ");

    int num2 = input.nextInt();

    int sum = num1 + num2;

    System.out.println();

    System.out.println("Sum: "+sum);

  }

}

OUTPUT

Input the first number: 545

Input the second number: 455

Sum: 1000

Divide two numbers

And print on the screen

JAVA CODE

import java.util.Scanner;

public class Main {

  public static void main(String[] args)

  {

    Scanner input = new Scanner (System.in);

    System.out.print("Input the first number: ");

    int a = input.nextInt();

    System.out.print("Input the second number: ");

    int b = input.nextInt();

    int d = (a/b);

    System.out.println();

    System.out.println("The division of a and b is:" +d);

  }

}

OUTPUT

Input the first number: 100

Input the second number: 25

The division of a and b is:4

Print the result

Of specified operations

JAVA CODE

public class Main {

public static void main(String[] args) {

   int w = -5 + 8 * 6;

   int x = (55 + 9) % 9;

   int y = 20 + (-3 * 5 / 8);

   int z = 5 + 15 / 3 * 2 - 8 % 3;

   System.out.print(w + "\n" + x + "\n" + y + "\n" + z);

  }

}

Print multiplication table

JAVA CODE

import java.util.Scanner;

public class Main {

public static void main(String[] args) {

  Scanner in = new Scanner(System.in);

  System.out.println("Input the Number: ");

  int n = in .nextInt();

  for (int i = 1; i <= 10; i++) {

   System.out.println(n + "*" + i + " = " + (n * i));

  }

}

}

OUTPUT

Input the Number:

15

15*1 = 15

15*2 = 30

15*3 = 45

15*4 = 60

15*5 = 75

15*6 = 90

15*7 = 105

15*8 = 120

15*9 = 135

15*10 = 150

Find the area

And perimeter of a circle

JAVA CODE

import java.util.Scanner;

public class Main {

public static void main(String[] args) {

  Scanner io = new Scanner(System.in);

  System.out.println("Input the radius of the circle: ");

  double radius = io.nextDouble();

  System.out.println("Perimeter is = " + (2 * radius * Math.PI));

  System.out.println("Area is = " + (Math.PI * radius * radius));

}

}

OUTPUT

Input the radius of the circle:

10

Perimeter is = 62.83185307179586

Area is = 314.1592653589793

Swap two variables

JAVA CODE

import java.util.Scanner;

public class Main {

public static void main(String[] args) {

   int x, y, z;

   Scanner in = new Scanner(System.in);

   System.out.println("Input the first number: ");

   x = in.nextInt();

   System.out.println("Input the second number: ");

   y = in.nextInt();

   z = x;

   x = y;

   y = z;

   System.out.println(" Swapped values are3:" + x + " and " + y);

  }

}

OUTPUT

Input the first number:

25

Input the second number:

50

Swapped values are3:50 and 25

Print a face

JAVA CODE

public class Main {

public static void main(String[] args) {

  String[] arra = new String[5];

  arra[0] = " +\"\"\"\"\"+ ";

  arra[1] = "[| o o |]";

  arra[2] = " |  ^  |";

  arra[3] = " | '-' |";

  arra[4] = " +-----+";

  for (int i = 0; i < 5; i++) {

   System.out.println(arra[i]);

  }

}

}

OUTPUT

+"""""+

[| o o |]

|  ^  |

| '-' |

+-----+

Fahrenheit to Celsius degree

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] Strings) {

        Scanner input = new Scanner(System.in);

        System.out.print("Input a degree in Fahrenheit: ");

        double fahrenheit = input.nextDouble();

        double  celsius =(( 5 *(fahrenheit - 32.0)) / 9.0);

        System.out.println(fahrenheit + " degree Fahrenheit is equal to " + celsius + " in Celsius");

    }

}

OUTPUT

Input a degree in Fahrenheit: 96

96.0 degree Fahrenheit is equal to 35.55555555555556 in Celsius

Inches to meters

![](Images/image00177.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] Strings) {

        Scanner input = new Scanner(System.in);

        System.out.print("Input a value for inch: ");

        double inch = input.nextDouble();

        double meters = inch * 0.0254;

        System.out.println(inch + " inch is " + meters + " meters");

    }

}

OUTPUT

Input a value for inch: 5

5.0 inch is 0.127 meters

Adds all the digits

![](Images/image00178.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] Strings) {

        Scanner input = new Scanner(System.in);

        System.out.print("Input an integer between 0 and 1000: ");

        int num = input.nextInt();

        int firstDigit = num % 10;

        int remainingNumber = num / 10;

        int SecondDigit = remainingNumber % 10;

        remainingNumber = remainingNumber / 10;

        int thirdDigit = remainingNumber % 10;

        remainingNumber = remainingNumber / 10;

        int fourthDigit = remainingNumber % 10;

        int sum = thirdDigit + SecondDigit + firstDigit + fourthDigit;

        System.out.println("The sum of all digits in " + num + " is " + sum);

    }

}

OUTPUT

Input an integer between 0 and 1000: 750

The sum of all digits in 750 is 12

Print the number of years and days

From minutes

![](Images/image00179.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] Strings) {

        double minutesInYear = 60 * 24 * 365;

        Scanner input = new Scanner(System.in);

        System.out.print("Input the number of minutes: ");

        double min = input.nextDouble();

        long years = (long) (min / minutesInYear);

        int days = (int) (min / 60 / 24) % 365;

        System.out.println((int) min + " minutes is approximately " + years + " years and " + days + " days");

    }

}

OUTPUT

Input the number of minutes: 123456

123456 minutes is approximately 0 years and 85 days

Compute (BMI)

Body mass index

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] Strings) {

        Scanner input = new Scanner(System.in);

        System.out.print("Input weight in pounds: ");

        double weight = input.nextDouble();

        System.out.print("Input height in inches: ");

        double inches = input.nextDouble();

        double BMI = weight * 0.45359237 / (inches * 0.0254 * inches * 0.0254);

        System.out.print("Body Mass Index is " + BMI+"\n");

    }

}

OUTPUT

Input weight in pounds: 450

Input height in inches: 72

Body Mass Index is 61.03034545478814

Calculate speed in meters

per second, kilometers and miles per hour

![](Images/image00180.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

float timeSeconds;

float mps,kph, mph;

System.out.print("Input distance in meters: ");

float distance = scanner.nextFloat();

System.out.print("Input hour: ");

float hr = scanner.nextFloat();

System.out.print("Input minutes: ");

float min = scanner.nextFloat();

System.out.print("Input seconds: ");

float sec = scanner.nextFloat();

timeSeconds = (hr*3600) + (min*60) + sec;

mps = distance / timeSeconds;

kph = ( distance/1000.0f ) / ( timeSeconds/3600.0f );

mph = kph / 1.609f;

System.out.println("Your speed in meters/second is "+mps);

System.out.println("Your speed in km/h is "+kph);

System.out.println("Your speed in miles/h is "+mph);

scanner.close();

}

}

OUTPUT

Input distance in meters: 3000

Input hour: 5

Input minutes: 32

Input seconds: 29

Your speed in meters/second is 0.15038347

Your speed in km/h is 0.5413805

Your speed in miles/h is 0.3364702

Divide the two specified integers

using subtraction operator

JAVA CODE

import java.util.Scanner;

public class Main {

public static float divide_using_subtraction(int dividend, int divider) {

if (divider == 0) {

       return 0;

}  

    float result = 0;

    while (dividend > divider) {

      dividend -= divider;

      result++;

    }

    float decimalPart = (float) dividend / (float) divider;

    result += decimalPart;

    return result;

  }

    public static void main(String[] args) {

Scanner in = new Scanner(System.in);

        System.out.print("Input the dividend: ");

        int dividend = in.nextInt();

System.out.print("Input the divider: ");

        int divider = in.nextInt();

System.out.println("\nResult: " + divide_using_subtraction(dividend,divider));                           

}

}

OUTPUT

Input the dividend: 900

Input the divider: 30

Result: 30.0

Multiply two specified integers

without using the multiply operator

JAVA CODE

import java.util.*;

public class Main {

  public static int multiply(int n1, int n2) {

    int result = 0;

    boolean negative_num = (n1 < 0 && n2 >= 0) || (n2 < 0 && n1 >= 0);

    boolean positive_num = !negative_num;

    n1 = Math.abs(n1);

    for (int i = 0; i < n1; i++) {

      if (negative_num && n2 > 0 || positive_num && n2 < 0)

        result -= n2;

      else

        result += n2;

    }

    return result;

}

   public static void main(String[] args) {

        Scanner in = new Scanner(System.in);

        System.out.print("Input the first number: ");

        int n1 = in.nextInt();

System.out.print("Input the second number: ");

        int n2 = in.nextInt();

System.out.println("\nResult: " + multiply(n1,n2));

}

}

OUTPUT

Input the first number: 25

Input the second number: 30

Result: 750

Print the sum

Difference, product, average, distance, maximum and minimum

![](Images/image00181.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

    public static void main(String[] args)

    {

        Scanner in = new Scanner(System.in);

        System.out.print("Input 1st integer: ");

        int firstInt = in.nextInt();

        System.out.print("Input 2nd integer: ");

        int secondInt = in.nextInt();

        System.out.printf("Sum of two integers: %d%n", firstInt + secondInt);

        System.out.printf("Difference of two integers: %d%n", firstInt - secondInt);

        System.out.printf("Product of two integers: %d%n", firstInt * secondInt);

        System.out.printf("Average of two integers: %.2f%n", (double) (firstInt + secondInt) / 2);

        System.out.printf("Distance of two integers: %d%n", Math.abs(firstInt - secondInt));

        System.out.printf("Max integer: %d%n", Math.max(firstInt, secondInt));

        System.out.printf("Min integer: %d%n", Math.min(firstInt, secondInt));

    }

}

OUTPUT

Input 1st integer: 50

Input 2nd integer: 30

Sum of two integers: 80

Difference of two integers: 20

Product of two integers: 1500

Average of two integers: 40.00

Distance of two integers: 20

Max integer: 50

Min integer: 30

Find the greatest of three numbers

Java Conditional Statement

![](Images/image00182.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

  public static void main(String[] args) {

  Scanner in = new Scanner(System.in);

  System.out.print("Input the 1st number: ");

  int num1 = in.nextInt();

  System.out.print("Input the 2nd number: ");

  int num2 = in.nextInt();

  System.out.print("Input the 3rd number: ");

  int num3 = in.nextInt();

  if (num1 > num2)

   if (num1 > num3)

    System.out.println("The greatest: " + num1);

  if (num2 > num1)

   if (num2 > num3)

    System.out.println("The greatest: " + num2);

  if (num3 > num1)

   if (num3 > num2)

    System.out.println("The greatest: " + num3);

}

}

OUTPUT

Input the 1st number: 25

Input the 2nd number: 58

Input the 3rd number: 98

The greatest: 98

Display the multiplication table

of a given integer

JAVA CODE

import java.util.Scanner;

public class Main {

   public static void main(String[] args)

{

   int j,n;

   System.out.print("Input the number(Table to be calculated): ");

{

   System.out.print("Input number of terms : ");

    Scanner in = new Scanner(System.in);

    n = in.nextInt();

   System.out.println ("\n");

   for(j=0;j<=n;j++)

     System.out.println(n+" X "+j+" = " +n*j);

   }

}

}

OUTPUT

Input the number(Table to be calculated): Input number of terms : 7

7 X 0 = 0

7 X 1 = 7

7 X 2 = 14

7 X 3 = 21

7 X 4 = 28

7 X 5 = 35

7 X 6 = 42

7 X 7 = 49

Display the pattern

like right angle triangle

with a number

![](Images/image00183.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

   public static void main(String[] args)

{

   int i,j,n;

   System.out.print("Input number of rows : ");

Scanner in = new Scanner(System.in);

    n = in.nextInt();

   for(i=1;i<=n;i++)

   {

for(j=1;j<=i;j++)

  System.out.print(j);

    System.out.println("");

    }

}

}

OUTPUT

Input number of rows : 9

1

12

123

1234

12345

123456

1234567

12345678

123456789

Print a pattern like a pyramid

![](Images/image00184.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

  public static void main(String[] args)

{

   int i,j,n,s,x;

   System.out.print ("Input number of rows : ");

   Scanner in = new Scanner(System.in);

    n = in.nextInt();

   s=n+4-1;

    for(i=1;i<=n;i++)

   {

   for(x=s;x!=0;x--)

    {

   System.out.print(" ");

    }

    for(j=1;j<=i;j++)

    {

     System.out.print(i+" ");

     }

System.out.println();

    s--;

   }

}

}

OUTPUT

Input number of rows : 7

          1

         2 2

        3 3 3

       4 4 4 4

      5 5 5 5 5

     6 6 6 6 6 6

    7 7 7 7 7 7 7

Display the number rhombus structure

![](Images/image00185.jpeg)

JAVA CODE

import java.util.Scanner;

public class Main {

  public static void main(String args[])

    {

        Scanner in = new Scanner(System.in);

        System.out.print("Input the number:  ");

        int n = in.nextInt();

        int count = 1;

        int no_of_spaces = 1;

        int start = 0;

        for (int i = 1; i < (n * 2); i++)

        {

            for (int spc = n - no_of_spaces; spc > 0; spc--)

            {

                System.out.print(" ");

            }

            if (i < n)

            {

                start = i;          //for number

                no_of_spaces++;    //for spaces

            } else

            {

                start = n * 2 - i;   //for number

                no_of_spaces--;      //for space

            }

            for (int j = 0; j < count; j++)

            {

                System.out.print(start);

                if (j < count / 2)

                {

                    start--;

                } else

                {

                    start++;

                }

            }

            if (i < n)

            {

                count = count + 2;

            } else {

                count = count - 2;

            }

            System.out.println();

        }

    }

}

OUTPUT

Input the number: 7

      1

     212

    32123

   4321234

  543212345

65432123456

7654321234567

65432123456

  543212345

   4321234

    32123

     212

      1