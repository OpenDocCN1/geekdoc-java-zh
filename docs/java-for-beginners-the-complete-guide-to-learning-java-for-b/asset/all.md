![](cover.jpeg)

Java for Beginners

The Complete Guide To Learning Java for Beginners

Bruce Berke

© 2018

 Copyright 2018 by Bruce Berke - All rights reserved.

This document is geared towards providing exact and reliable information in regards to the topic and issue covered. The publication is sold with the idea that the publisher is not required to render accounting, officially permitted, or otherwise, qualified services. If advice is necessary, legal or professional, a practiced individual in the profession should be ordered.

- From a Declaration of Principles which was accepted and approved equally by a Committee of the American Bar Association and a Committee of Publishers and Associations.

In no way is it legal to reproduce, duplicate, or transmit any part of this document in either electronic means or in printed format. Recording of this publication is strictly prohibited and any storage of this document is not allowed unless with written permission from the publisher. All rights reserved.

The information provided herein is stated to be truthful and consistent, in that any liability, in terms of inattention or otherwise, by any usage or abuse of any policies, processes, or directions contained within is the solitary and utter responsibility of the recipient reader. Under no circumstances will any legal responsibility or blame be held against the publisher for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly.

Respective authors own all copyrights not held by the publisher.

The information herein is offered for informational purposes solely, and is universal as so. The presentation of the information is without contract or any type of guarantee assurance.

The trademarks that are used are without any consent, and the publication of the trademark is without permission or backing by the trademark owner. All trademarks and brands within this book are for clarifying purposes only and are the owned by the owners themselves, not affiliated with this document.

Table of Contents

[Introduction](#part0000_split_003.html__Toc515373968)

[Chapter 1: Getting Started with java](#part0000_split_004.html__Toc515373969)

[Chapter 2: Java Variables](#part0000_split_009.html__Toc515373970)

[Chapter 3: Java operators](#part0000_split_018.html__Toc515373971)

[Chapter 4: Java arrays](#part0000_split_023.html__Toc515373972)

[Chapter 5: Decision making](#part0000_split_026.html__Toc515373973)

[Chapter 6: looping](#part0000_split_032.html__Toc515373974)

[Chapter 7: Inheritance](#part0000_split_038.html__Toc515373975)

[Chapter 8: overriding](#part0000_split_042.html__Toc515373976)

[Chapter 9: Polymorphism](#part0000_split_044.html__Toc515373977)

[Chapter 10: Abstraction](#part0000_split_045.html__Toc515373978)

[Chapter 11- encapsulation](#part0000_split_047.html__Toc515373979)

[Chapter 12- Interfaces](#part0000_split_048.html__Toc515373980)

[Chapter 13- Packages](#part0000_split_049.html__Toc515373981)

[Chapter 14- Command-Line Arguments](#part0000_split_051.html__Toc515373982)

[Chapter 15- Recursion](#part0000_split_052.html__Toc515373983)

[Chapter 16- Method Calls](#part0000_split_053.html__Toc515373984)

[Chapter 17- Java Applets](#part0000_split_054.html__Toc515373985)

[Conclusion](#part0000_split_060.html__Toc515373986)

# Introduction

Java is a wide programming language, packed with lots of features good for application development. It’s a good coding language for the design/development of desktop apps. These are popular as standalone applications. If you need a distributed application, Java is the best language to use. Java applets can be embedded/added on web pages. The many features offered by Java have made it a popular coding language. Its wide features make it applicable in the development of apps applicable in various industries. To code in Java, you should get the Java compiler. Java is compiled, not interpreted. You need an editor in which you can write your Java codes. Notepad is good for this. With these, you can start writing and running your Java codes. This means it’s easy to get started with Java, making Java a good language for beginners. The Java bytecode, normally generated after compiling Java source codes, is platform-independent, meaning it can be run on any platform including Windows, Solaris, Linux, etc. Java apps are secured via public-key cryptography, making them safe/secure. Java apps can be linked to various database management systems, for example, MySQL, Oracle, SQL Server, etc. This book is an excellent guide on Java programming. Get it and know every aspect of Java and transition from Java Beginner to Java Expert!

# Chapter 1: Getting Started with java

Java is a platform as well as a coding language. It is a robust, high-level, object-oriented and secured programming language. It was released in 1995 by the Sun Microsystems. Java treats everything as an object. Its object model makes it easy to extend. The language is compiled, meaning that we have a Java compiler. Java is also platform independent. After compiling your Java source code, you get the byte code which can be executed on any platform. Java is also well known for being easy to learn. If you know some basic concepts about object-oriented programming, it will be easy for you to learn Java. It is packed with numerous features, making it widely functional.

Authentication in Java is done using a public-key encryption, making its systems very secure. This is the reason we can develop temper-free and virus-free systems with Java. In Java, errors are identified during the compile time, meaning that you cannot go to the run phase without first sorting out the error.

## Environment Setup

For you to write and run Java programs, you need a text editor and the Java compiler. The Java compiler comes with the JDK (Java Development Kit) which can be downloaded and installed for free. You also need to have a text editor where you will be writing your Java programs. You can even use a basic text editor like Notepad and it will be okay. However, there are advanced text editors for Java such as Eclipse and Netbeans.

First, download and install the JDK on your computer. After that, you will have installed Java on your machine. Open your browser then type or paste the following URL:

[http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

From there, you can get the latest version of the JDK. You will then have to set the environment variables to know the right Java installation directories. This means you should set the path variable. Mostly, the installation is done in the c:\Program Files\java\jdk directory.  To set the path on Windows, correctly “My Computer”, choose “Properties”, open the “Advanced” tab then choose “Environment variables”. Add the “c:\Program Files\java\jdk\bin” path. For Linux users, read the documentation of your shell.

## Java Syntax

A Java program consists of objects communicating via invocation of methods from each other. Below are the main constructs in a Java program:

*   Object- Objects are characterized by state and behavior. For example, a cat has states like color, breed name and behaviors like eating, meowing and wagging tail.
*   Class- This is a blueprint/template describing the state/behaviors supported by its objects.
*   Method- A method is a behavior. Logic is written in methods, and they are usable in data manipulation.

## First Program

This is our first Java program. It should print “Hello World” once executed:

public class OurFirstProgram{

public static void main(String args[]){

System.out.println("Hello World");

}

}

Open your text editor like Notepad and create a new file named “FirstProgram.java. Save the file. The .java extension marks the file as a Java file. Type the above program code in the file and save the changes. Open the command prompt then navigate to the directory in which you have saved the file. Run the commands given below from that directory:

javac FirstProgram.java

java FirstProgram

In my case, I saved the file on the desktop. I executed the commands as follows:

![](images/00001.gif)

The program prints “Hello World” as the result. In the command “javac FirstProgram.java”, we are invoking the java compiler (javac) to compile the program. The command returned nothing on the command prompt since the program has no error, and no warning was generated. The command generates a .class file (FirstProgram.class) in the directory; please confirm. In the command “java FirstProgram”, we are simply running the program to give us the result.

Consider the following line extracted from the code:

public class FirstProgram{

The line simply declares a class named FirstProgram. Java is a case sensitive language, hence this class must always be referred to as it is written above. The “public” keyword declares that class as public, meaning it is accessible from any other class within the same package. The { declares the beginning of the class body, and it should be closed by a }.

Note: The filename in which we write the program should match the class-name; otherwise, you will experience trouble when running the program. In our case, the class was named “FirstProgram”, hence the filename should be FirstProgram.java.

Consider the following line extracted from the code:

public static void main(String args[]){

That’s the main method. A java program cannot be executed or run without this method. Consider the following line extracted from the code:

System.out.println("Hello World");

We are simply invoking or calling the “println” method to print the text Hello World on the terminal of the command prompt.

Lastly, we have two closing curly braces, }}. The first one closes the opening brace for the main method while the second one closes the opening brace for the class.

# Chapter 2: Java Variables

A variable can be seen as a container responsible for holding a value during the life of a program. Each variable is of a certain data type, designative the kind of value that it can hold. There are two steps in using Java variables, that is, variable declaration and variable initialization.

## Variable Declaration

The declaration of a variable involves giving it a name and specifying its data type. Below are examples of valid variable declaration:

int x,j,z;

float pi;

double a;

char c;

The int, float, double and char are the data types, specifying the type of value each variable can or should hold. To declare several variables in one line, separate them using a comma (,) as in the first example. A variable declaration should end with a semicolon (;).

## Variable Initialization

Variable initializing involves assigning it a valid value. The value to be assigned to the variable is determined by the variable’s data type. Below are examples of valid variable initializations.

pi =3.14f;

a =20.22778765;

c=’v’;

Both the declaration and initialization of a variable can be done at once as shown below:

int x=1,z=4,y=5;

float pi=3.14f;

double d=19.12d;

char c=’v’;

## Variable Types

Java supports three variable types:

1.  Local Variables
2.  Static Variables
3.  Instance Variables

## Local Variables

These are variables declared within a method body. They can only be accessed from within that method.

## Instance Variables

These are the variables that have been defined without the use of STATIC keyword. These variables are specific to an object.

## Static Variables

These are variables initialized once at the beginning of the program execution. You should initialize them before instance variables.

The following example demonstrates the different types of Java variables:

class JavaVariables {

    int i = 10; //an instance variable 

    static int b = 2; //a static variable 

    void methodExample() {

        int c = 3; //a local variable 

    }

}

The variable integer b is a static variable since it has been defined with the static keyword. The variable int c has been declared within the methodExample method, making it a local variable. It can only be accessed from within that method.

## Data Types

In Java, a data type can be either primitive or non-primitive.

### Primitive Data Types

These are the predefined data types that are already provided by Java. They are 8 in number including byte, short, long, char, int, float, Boolean and double  data types.

### Non-Primitive Data Types

These are defined by the use of defined class constructors. They help programmers access objects.

The example given below demonstrates the use of variables:

public class VariableAddition{ 

    public static void main(String[] args){ 

    int ax=5; 

    int jk=12; 

    int z=ax+jk; 

    System.out.println(z); 

    }

} 

We have defined three integer variables x, j and z. The values for x and j have been initialized, while the value for z is the addition of the previous two variables. We have then invoked the “println” function to print the value of z. It should print 17, the result of the addition of 5 and 12\.

## Type Casting and Type Conversion

It is possible for a variable of a particular type to get a value of some other type. Type conversion is when a variable of a smaller capacity is assigned a variable of a bigger capacity. Example:

double db;

int x=5;

db-x;

Type casting is when a variable of a larger capacity is assigned some other variable of a smaller capacity. Example:

db =5;

int x;

x= (int) db;

The (int) is known as the type cast operator. If it is not specified, you get an error. Typecasting example:

public class TypecastingExample{  

public static void main(String[] args){  

float ft=11.8f;  

//int x=ft;//a compile time error  

int x=(int)ft;  

System.out.println(ft);  

System.out.println(x);  

}

}  

# Chapter 3: Java operators

Operators are symbols used to perform operations. For example, the + symbol is used for arithmetic operations. Java supports different operators:

## Unary Operator

This is an operator that takes one operand. They increment/decrement a value. They include ++ (increment) and - -(decrement). Example:

public class UnaryOperatorExample{  

public static void main(String args[]){  

int j=0;  

System.out.println(j++);//from 0 to 1  

System.out.println(++j);//2  

System.out.println(j--);//1  

System.out.println(--j);//0  

}

}  

The program will print 0, 2, 2, 0\. The j++ means that the value of j is read first before the increment is done, hence we got the value of j as 0\. If it was ++j, then we would get a 1 as the first value of j. You can try it.

## Arithmetic Operators

These operators are used for performing mathematical operations like multiplication, addition, division, subtraction etc. They are used as mathematical operators. Example:

public class JavaArithmeticOperatorsExample{  

public static void main(String args[]){  

int x=0;  

int y=10;  

System.out.println(x+y);//10 

System.out.println(x-y);//-10  

System.out.println(x*y);//0  

System.out.println(x/y);//0 

System.out.println(x%7);//0  

}

}  

The only operator that may look unfamiliar is the % (modulus operator), which returns the remainder after division.

## Logical Operators

These operators are used together with the binary values. They help in evaluation of conditions in loops and conditional statements. They include ||, &&, !. Suppose we have two Boolean variables, a1 and a2, the following conditions apply:

a1&&a2 will return true if both a1 and a2 are true; otherwise, they will return false.

a1||a2 will return false if both a1 and a2 are false; otherwise, they will return true.

!a1 will return opposite of a1\.

Example:

public class LogicalOperatorExample {

   public static void main(String args[]) {

      boolean a1 = true;

      boolean a2 = false;

      System.out.println("a1 && a2: " + (a1&&a2));

      System.out.println("a1 || a2: " + (a1||a2));

      System.out.println("!(a1 && a2): " + !(a1&&a2));

   }

}

The program will return false, true, true.  

## Comparison Operators

Java supports 6 types of comparison operators, ==, !=, <, >, >=, <=:

== will return true if both the left and right sides are equal.

!= will return true if the left and right sides of the operator are not equal.

 Returns true if the left side is greater than the right side.

< returns true if the left side is less than the right side.

>= returns true if the left side is greater than/equal to the right.

<= returns true if the left side is less than the right side.

Example:

public class JavaRelationalOperatorExample {

   public static void main(String args[]) {

      int n1 = 20;

      int n2 = 30;

      if (n1==n2) {

System.out.println("n1 and n2 are equal");

      }

      else{

System.out.println("n1 and n2 aren’t equal");

      }

      if( n1 != n2 ){

System.out.println("n1 and n2 aren’t equal");

      }

      else{

System.out.println("n1 and n2 are equal");

      }

      if( n1 > n2 ){

System.out.println("n1 is greater than n2");

      }

      else{

System.out.println("n1 isn’t greater than n2");

      }

      if( n1 >= n2 ){

System.out.println("n1 is equal to or greater than n2");

      }

      else{

System.out.println("n1 is less than n2");

      }

      if( n1 < n2 ){

System.out.println("n1 is less than n2");

      }

      else{

System.out.println("n1 isn’t less than n2");

      }

      if( n1 <= n2){

System.out.println("n1 is equal to or less than n2");

      }

      else{

System.out.println("n1 is greater than n2");

      }

   }

}

The program uses the if statement which is discussed in the next chapters.

# Chapter 4: Java arrays

Arrays are storage structures used for storing same-type elements. An array has a fixed size, which cannot be increased after definition. The first element in an array is at index 0.

## Single Dimensional Arrays

These are arrays in which the elements are stored linearly. The declaration of an array takes the syntax given below:

<elementDataType>[] <arrayName>;

Another syntax:

<elementDataType> <arrayName>[];

Example:

int arrayExample[];

int []arrayExample;

An array can be initialized as follows:

arrayExample[0]=1;

The line states that the element 1 should be stored at index 0 of the array. An array can also be declared and initialized simultaneously as follows:

int arrayExample[] = {5, 20, 35, 43};

The value 5 will be stored at the index 0 of the array 20 at index 1 and so on.

Example:

public class JavaArrayExample{

     public static void main(String args[]){

        int array1[] = new int[8];

        for (int c=0;c<8;c++){

           array1[c]=c+1;

       }

       for (int c=0;c<8;c++){

           System.out.println("array1["+c+"] = "+array1[c]);

       }

      System.out.println("The Array Length  =  "+array1.length);

      }

}

The array will print the elements contained at different indices. You will also get the array length, which is 8.

## Multi-Dimensional Arrays

These can be seen as arrays of other arrays. In multi-dimensional array declaration, you only add another set of square brackets to define the other index. Example:

int array2[ ][ ] = new int[6][10] ;

You have the authority to control the length of your multi-dimensional array. Example:

public class JavaArrayExample2 {

public static void main(String[] args) {

// Creating a 2-dimensional array.

  int[][] array2 = new int[6][8];

  // Assign only three elements

  array2[0][0] = 2;

  array2 [1][1] = 12;

  array2 [3][2] = 11;

  System.out.print(array2[0][0] + " ");

}

}

The program will return the value stored at index [0][0], which is 2\.

# Chapter 5: Decision making

In Java, decision making helps us evaluate conditions and run statements based on the outcome of the condition. Let us discuss the statements for decision making:

## if statement

This statement has a Boolean expression and statement(s). Its syntax is given below:

if(A_boolean_expression) {

   // Statement(s) to be run if true

}

The statements within the body of the expression will run if the condition is true; otherwise, no result from the program will run. Example:

public class JavaIfStatement {

   public static void main(String args[]) {

      int marks = 20;

      if( marks < 50 ) {

         System.out.print("The marks is below 50");

      }

   }

}

## if…else statement

This statement combines an “if” with “else”, with the latter specifying the statement(s) to run if the expression is found to be false. Syntax:

if(A_boolean_expression) {

   // Statement(S) to run if expression is true

}else {

   // Statement(s) to run if expression is false

}

Example:

public class JavaIfElseStatement {

   public static void main(String args[]) {

      int marks = 30;

      if( marks < 50 ) {

         System.out.print("The marks is below 50");

      }else {

         System.out.print("The marks is above 50");

      }

   }

}

The first statement will be printed, that is, The marks is below 50\. This is because the Boolean expression will be true. If it is false, the other statement will be printed. Example:

public class JavaIfElseStatement {

   public static void main(String args[]) {

      int marks = 70;

      if( marks < 50 ) {

         System.out.print("The marks is below 50");

      }else {

         System.out.print("The marks is above 50");

      }

   }

}

## if...else if...else Statement

If you have several conditions to evaluate, use this statement. Syntax:

if(A_boolean_expression a) {

   // Statement(s)

}else if(A_boolean_expression b) {

   // Statement(s)

}else if(A_boolean_expression c) {

   // Statement(s)

}else {

   // Statement(s)

}

Example:

public class JavaIfElseIfStatement {

   public static void main(String args[]) {

      int marks = 20;

      if( marks == 10 ) {

         System.out.print("Marks is 10");

      }else if( marks == 20 ) {

         System.out.print("Marks is 20");

      }else if( marks == 30 ) {

         System.out.print("Marks is 30");

      }else {

         System.out.print("None of the above");

      }

   }

}

The result from the program will be Marks is 20\.

## Nested if

The if…else statements can be nested, meaning that one may use an if inside another if or an if…else inside another if…else. The nesting syntax is shown below:

if(A_boolean_expression a) {

   // Statament(s)

   if(A_boolean_expression b) {

      // Statament(s)

   }

}

Example:

public class NestingExample {

   public static void main(String args[]) {

      int ab = 10;

      int xy = 30;

      if( ab == 10 ) {

         if( xy == 30 ) {

            System.out.print("The value of ab is 10 and xy is 10");

         }

      }

   }

}

If the first condition becomes true, the second condition will evaluate. This is true in our case, hence the println statement will be executed. If any of the conditions is false, then the println statement will not be executed.

## switch statement

This statement allows us to test a certain variable for equality against some values list. Every value is referred to as case. The following syntax is used:

switch(an_expression) {

   case value:

      // Statement(s)

      break; //optional

   case value:

      // Statement(s)

      break; //optional

   default : //Optional

      // Statement(s)

}

The switch will terminate once it has reached the break statement. The flow will then jump to the next line. However, note that it isn’t a must to add a break to every case. A default case may be added to the end of the switch, and this will run if none of the cases are true.

Example:

public class JavaSwitchStatement {

   public static void main(String args[]) {

      char student_grade = 'B';

      switch(student_grade) {

         case 'A':

            System.out.println("That is Excellent!");

            break;

         case 'B':

            System.out.println("That is Good!");

            break;

         case 'C':

           System.out.println("That is Fair!");

            break;

         case 'D':

            System.out.println("That is Poor!");

         case 'F':

            System.out.println("You Failed!");

            break;

         default:

            System.out.println("Unknown grade");

      }

      System.out.println("The student got grade " + student_grade);

   }

}

The case for grade B will be true, so you will get the message for Good. After that, the program will execute the last println statement, hence the value for student_grade will be printed.

# Chapter 6: looping

Java loops help us do some tasks repeatedly. Loops execute the statements in a sequential manner. The first one is run first, followed by the second, etc. Let us discuss the Java loops:

## for Loop

The loop is run, provided the condition evaluates to true. The execution will stop immediately if the condition becomes false. Syntax:

for(initialization; loop_condition ; Increment/decrement_part)

{

   the_statement(s);

}

The initialization defines the initial value of the loop condition. The loop_condition specifies the condition that must always be true for the loop to run. The loop_increment/decrement defines the amount by which the initialization value will be incremented or decremented after each iteration. Example:

public class ForLoopDemo {

    public static void main(String args[]){

         for(int ix=0; ix<10; ix++){

              System.out.println("The ix value is currently: "+ix);

         }

    }

}

The program will print the value of ix from 0 to 9\. When the loop increments the 9 to get 10, it will find that it is violating the loop condition, that is, ix<10, hence the execution will halt immediately.

## while Loop

This loop executes the statement(s) as long as the specified condition is true. The condition is first evaluated, and if true, the loop statement(s) are executed. If the condition becomes false, the control will jump to execute statements that come after the loop. It is recommended you add an increment/decrement to the loop and a test condition so that the loop halts execution when the condition becomes false. Otherwise, the loop may run indefinitely. Syntax:

while(A_boolean_expression) {

   // Statement(s)

}

Example:

public class JavaWhileLoop {

   public static void main(String args[]) {

      int xy = 20;

      while( xy < 25 ) {

         System.out.print("The value of xy is: " + xy );

         xy++;

         System.out.print("\n");

      }

   }

}

The program prints xy’s value from 20 to 24. The variable’s initial value is 20\. The test condition checks whether this value is less than 25, which is true. This means the loop will run. When it reached 24, it will check and find the value of xy is 25\. The execution of the loop then halts immediately since continuing to execute it will violate the loop condition.

## do…while Loop

This is closely related to the while loop. In while, the loop condition execution is done before the loop body execution. This is opposite in a do…while loop as the body is executed first before the condition. In a while loop, the loop body may never be executed, but in a do…while loop, the loop body must be executed for at least once. Syntax:

do

{

   Statement or statements;

} while(loop_condition);

Example:

public class JavaDoWhileLoopExample {

   public static void main(String args[]) {

      int xy = 20;

      do {

         System.out.print("The value of xy is: " + xy );

         xy++;

         System.out.print("\n");

      }while( xy < 25 );

   }

}

The code will print the value of xy from 20 to 24 just as in the previous loop. This is because the condition is true, that is, 20 is less than 25\. Suppose we set the loop condition as false, for example, initialize the value of xy to 30 as shown below:

public class DoWhileLoopExample {

   public static void main(String args[]) {

      int xy = 30;

      do {

         System.out.print("The value of xy is: " + xy );

         xy++;

         System.out.print("\n");

      }while( xy < 25 );

   }

}

After running the above program, you will get “The value of xy is: 30” as the output. This means that the while condition is false. This is because the Java compiler first runs through the program for the initial value of xy which is 30\. That value is printed. Once it moves to the loop condition, it finds itself violating the condition, that is, xy<25, hence the loop execution halts immediately.

There are two statements that are used for controlling how Java loops are executed. They are namely continue and break statements. They work by changing the normal way of executing a loop. Let us discuss them.

## break Statement

This statement causes the execution of a loop to halt, and the control jumps to the statement that comes next after the loop. It also halts a case in a switch statement. Syntax:

your-jump-statement;    

break;   

Example:

public class JavaBreakStatementExample {  

public static void main(String[] args) {  

    for(int ix=0;ix<=10;ix++){  

        if(ix==6){  

            break;  

        }  

        System.out.println(ix);  

    }  

}  

}  

The program will print from 0 to 5\. This is because of the following section of our program:

if(ix==6){ 

            break;

The increment is done from 0 to 5, and once it notices that the value of ix is 6, it will halt immediately as it will be violating the above condition. For the case of nested loops, the break can be added to the inner loop, and it will break it. This will cause the inner loop to break once the specified condition is met. Example:

    public class BreakStatement2 { 

    public static void main(String[] args) { 

                for(int ix=1;ix<=5;ix++){   

                        for(int jk=1;jk<=5;jk++){   

                            if(ix==3&&jk==3){   

                                break;   

                            }   

                            System.out.println(ix+" "+jk);   

                        }   

                }   

    } 

    } 

## continue Statement

This statement makes the loop jump to next iteration immediately. It helps the loop to continue after a jump. Note that in previous case, the loop halted immediately. This statement can help it resume execution in the next iteration after the jump. Example:

your_jump-statement;    

continue;   

Example:

public class ContinueStatamentExample {  

public static void main(String[] args) {  

    for(int ix=1;ix<=10;ix++){  

        if(ix==5){  

            continue;  

        }  

        System.out.println(ix);  

    }  

}  

}  

The code will not print 5, but all the other numbers from 1 to 10 will be printed.

The continue statement may also be used with an inner loop. In such a case, it will only continue your inner loop. Example:

public class ContinueStatament2 {  

 public static void main(String[] args) {  

              for(int ix=1;ix<=3;ix++){    

                      for(int jk=1;jk<=3;jk++){    

                          if(ix==2&&jk==2){    

                              continue;    

                          }    

                          System.out.println(ix+" "+jk);    

                      }    

              }    

  }  

} 

# Chapter 7: Inheritance

In inheritance, an object acquires the behaviors and properties of another object. The object acquiring the behaviors and the properties is the child, while the object from which they are inherited is the parent. They can also be referred to as subclass and superclass respectively. Inheritance makes information manageable in an hierarchical order. The methods that had been defined in the superclass can be reused in the subclass without defining them again.

To inherit from a parent class, we use the extends keyword. Inheritance is done using the syntax given below:

class Child-class-name extends Parent-class-name  

{  

   // fields  and methods

}  

The extends keyword is an indication that we are creating some new class from an existing class. Example:

class CompanyEmployee{ 

     float employee_salary=40000;

    } 

    public class JavaProgrammer extends CompanyEmployee{ 

     int bonus=10000; 

     public static void main(String args[]){ 

       JavaProgrammer p=new JavaProgrammer(); 

       System.out.println("Programmer salary is:"+p.salary); 

       System.out.println("Bonus of Programmer is:"+p.bonus); 

    } 

    } 

There are different inheritance types:

## Single Inheritance

In this case, a single class inherits from another class. The Worker and DBA classes given previously are an example of this. Example:

    class Mammal{ 

    void drink(){

        System.out.println("Drinking...");

            } 

    } 

    class Cow extends Mammal{ 

    void moow(){System.out.println("Moowing...");} 

    } 

    public class JavaInheritanceTest{ 

    public static void main(String args[]){ 

    Cow c=new Cow(); 

    c.moow(); 

    c.drink(); 

    }

}

In the above example, the drink() method has been defined in the Mammal class while the moow() method has been defined in the Cow class which extends the Mammal class. In the InheritanceTest class, we have created an instance of Cow class and named it c. We have then used this instance to access the two methods that have been defined in two different classes. That is how single inheritance works.

## Multilevel Inheritance

 This inheritance occurs when a class B inherits from class A, while class C inherits from class B. Example:

    class Mammal{ 

    void drink(){

        System.out.println("Drinking...");

    } 

    } 

    class Cow extends Mammal{ 

    void moow(){

        System.out.println("Moowing...");

    } 

    } 

    class BabyCow extends Cow{ 

    void jump(){

        System.out.println("Jumping...");} 

    } 

    public class JavaInheritanceTest2{ 

    public static void main(String args[]){ 

    BabyCow bc=new BabyCow(); 

    bc.moow(); 

    bc.jump(); 

    bc.drink(); 

    }

}

The drink() method has been defined in the Mammal class. The moow() method is defined in the Cow class which extends the Mammal class. The jump method has been defined in the BabyCow class which extends the Cow class. In the InheritanceTest2 class, we have created an instance of BabyCow class named bc. This instance has then been used to access the various properties or methods. We are able to use the instance of BabyCow class to access methods defined in the Cow and Mammal classes. The methods in various classes can be seen as their properties.

## Hierarchical Inheritance

This type of inheritance can be demonstrated like in this example:

    class Mammal{ 

    void drink(){

        System.out.println("Drinking...");

    } 

    } 

    class Cow extends Mammal{ 

    void moow(){

        System.out.println("Moowing...");

    } 

    } 

    class Goat extends Mammal{ 

    void meew(){

        System.out.println("Meewing...");

    } 

    } 

   public class JavaInheritanceTest3{ 

    public static void main(String args[]){ 

    Goat g=new Goat(); 

    g.meew(); 

    g.drink(); 

    //g.moow(); will give an Error 

    }

   } 

After creating an instance of Goat class in the InheritanceTest3 class, we are able to inherit the properties defined in the Mammal class since the Goat class inherits from the Mammal class. However, we are unable to access the properties defined in the Cow class since the Goat class does not inherit from the Cow class. If we attempt to do that, for example, run the g.moow(); statement, we will get an error.

Some languages support multiple inheritance, in which a single class inherits from two classes. Java doesn’t support this, and the closest we can get to this is by creating an interface, then use the implements on the interface. Suppose we create an interface named Interface1, then we can create a class named Class2 that extends from Class1 and implements the interface Interface1:

public class Class2 extends Class1 implements Interface1{

}

That is the closest we can get to the multiple inheritance feature in Java. For the class, we use the keyword “extends”, but this cannot be used for an interface. Instead, we use the keyword implements. This way, we can inherit the features of an interface. Inheritance helps in the reuse of existing properties and methods.

# Chapter 8: overriding

A subclass can override a method defined in the parent class if it was not declared with the final keyword. Overriding simply means overriding the functionality of the existing method. Example:

class Mammal {

   public void drink() {

      System.out.println("Mammals can drink");

   }

}

class Cow extends Mammal {

   public void drink() {

      System.out.println("Cows can drink and eat");

   }

}

public class JavaTestOverriding {

   public static void main(String args[]) {

      Mammal a = new Mammal ();   // Animal reference and object

      Mammal b = new Cow();   // Animal reference but Dog object

      a.drink();   // to execute the method of Mammal class

      b.drink();   // to execute the method of Cow class

   }

}

In this case, b is a Mammal type, but it can use the method defined in the Cow class. Example 2:

We will give a bank example. Different banks offer different interest rates on loans:

    class Banks{ 

    int getInterestRat(){

        return 0;

    } 

    } 

    class Bank1 extends Banks{ 

    int getInterestRat(){

        return 5;

    } 

    } 

    class Bank2 extends Banks{ 

    int getInterestRat(){

        return 7;

    } 

    } 

    class Bank3 extends Banks{ 

    int getInterestRat(){

        return 9;

    } 

    } 

    public class TestBanks{ 

    public static void main(String args[]){ 

    Bank1 b1=new Bank1(); 

    Bank2 b2=new Bank2(); 

    Bank3 b3=new Bank3(); 

    System.out.println("Bank1 Interest Rate: "+b1.getInterestRat()); 

    System.out.println("Bank1 Interest Rate: "+b2.getInterestRat()); 

    System.out.println("Bank1 Interest Rate: "+b3.getInterestRat()); 

    } 

    } 

The method has been used differently for different classes.

## super Keyword

 We use the “super” keyword to access a method overridden from the super class. Example:

class Mammals {

   public void drink() {

      System.out.println("Mammals can drink");

   }

}

class Cow extends Mammals {

   public void drink() {

      super.drink();   // to invoke method in super class

      System.out.println("Cows can drink and eat");

   }

}

public class TestCow {

   public static void main(String args[]) {

      Mammals c = new Cow();   // mammal reference but Cow object

      c.drink();   // to execute method in Cow class

   }

}

# Chapter 9: Polymorphism

This feature allows us to perform an action through divergent ways. With polymorphism, one object may take different forms. Example:

public interface Animals{}

public class Mammals{}

public class Cow extends Animals implements Mammals{

}

The Cow class above has numerous inheritances, making it polymorphic. These references may be generated from above:

Cow c = new Cow();

Mammals m = c;

Animals an = c;

Object ob = c;

All above reference variables are referring to a similar object. All variables are referring to the same object.

Example:

class Cars{ 

  void consume(){

      System.out.println("Cars consume fuel");

  } 

} 

public class Mercedez extends Cars{ 

  void consume(){

      System.out.println("Mercedez consumes petrol");

  } 

  public static void main(String args[]){ 

    Cars cr = new Mercedez();//upcasting 

    cr.consume(); 

  } 

}

The call to override the method has been resolved during runtime. This is runtime polymorphism. The overridden method has been called via reference variable for superclass.

With polymorphism, one may perform an action via different ways. If you have the class Mammals with the method sound(), the implementation of the method will be different for different animal classes like Goat, Cow, Donkey etc. You will have meow, moow etc. Example:

public class Animals{

   public void makeSound(){

      System.out.println("Animals make sound");  

   }

}

We can have a class for Cats that meows and extending the Animals class:

Class Cats extends Animals{

    @Override

    public void makeSound(){

        System.out.println("Meow");

    }

    public static void main(String args[]){

 Animals anim = new Cats();

 anim.makeSound();

    }

}

We can have a class Cows that extends the Animals class as follows:

Class Cows extends Animals{

    @Override

    public void makeSound(){

        System.out.println("Moow");

    }

    public static void main(String args[]){

 Animals anim = new Cows();

 anim.makeSound();

    }

}

We achieve compile-time polymorphism via method overloading. Example:

class Class1

{

    void demoMethod (int ab)

    {

       System.out.println ("ab: " + ab);

    }

    void demoMethod (int ab, int bc)

    {

       System.out.println ("ab and bc: " + ab + "," + bc);

    }

    double demoMethod(double ab) {

       System.out.println("double ab: " + ab);

       return ab*ab;

    }

}

public class Class2

{

    public static void main (String args [])

    {

        Class1 cs1 = new Class1();

        double res;

        cs1 .demoMethod(5);

        cs1 .demoMethod(5, 10);

        res = cs1 .demoMethod(10.5);

        System.out.println("Finally : " + res);

    }

}

The demoMethod() has been overloaded 3 times. It has a one int parameter, two int parameters and a double parameter. The method to be called in this case depends on arguments passed during the call. This is done during the function call, hence we have compile time polymorphism.

# Chapter 10: Abstraction

This feature makes a developer present to the user only what is necessary and hides the rest from users. The developer can differentiate what needs to be shown to users and what does not. When driving a car, you press the accelerator, and the car’s speed increases; you press the brakes, and the car stops. The driver is not aware of what happens inside the car, but an engineer worked on the car, presenting to the users the brakes, accelerator, handbrake, etc. (what is necessary to the user), and hid implementation details. When sending an email, you are required to type the content, attach documents and press the “Send” button, without knowing what happens behind the scenes. This is abstraction.

With abstraction, users aren’t aware of implementation details. The developer hides them. The user gets only the functionality of the app. That is, the user gets information on what an app does rather than how it’s done. An abstract class has the abstract keyword. If any class has an abstract method, it must be declared abstract. The abstract class must also be inherited from some other abstract class. Example:

abstract class cars {

 abstract void consume();

}

public class Mercedez extends cars {

 void consume() {

  System.out.println("Mercedez consumes petrol");

}

 public static void main(String argu[]) {

  cars cr = new Mercedez();

  cr.consume();

  System.out.println("Done");

}

}

It isn’t a must for an abstract class to have abstract methods in it. You can’t instantiate an abstract class. That is why we instantiated the Mercedez class as it has inherited a method from the abstract class. Example:

public abstract class Worker {

   private String workerName;

   private String workerAddress;

   private int workerNumber;

   public Worker(String workerName, String workerAddress, int workerNumber) {

      System.out.println("Worker Construction");

      this.workerName = workerName;

      this.workerAddress = workerAddress;

      this.workerNumber = workerNumber;

   }

   public double getWorkerPay() {

     System.out.println("Inside getWorkerPay");

     return 0.00;

   }

   public void checkMail() {

      System.out.println("Sending check to " + this.workerName + " " + this.workerAddress);

   }

   public String toString() {

      return workerName + " " + workerAddress + " " + workerNumber;

   }

   public String getWorkerName() {

      return workerName;

   }

   public String getWorkerAddress() {

      return workerAddress;

   }

   public void setWorkerAddress(String newWorkerAddress) {

      workerAddress = newWorkerAddress;

   }

   public int getWorkerNumber() {

      return workerNumber;

   }

   }

The class Worker is similar to other Java classes except the use of the abstract keyword. Attempt to instantiate it as follows:

public class AbstractInstantiation {

   public static void main(String [] args) {

      /* This will generate error */

      Worker wk = new Worker("George P.", "Texas, USA", 44);

      System.out.println("\n Calling checkMail with Worker reference");

      wk.checkMail();

   }

}

The properties of the Worker class must be inherited rather than instantiating the class. Example:

public class Wage extends Worker {

   private double wage;   // Annual salary

   public Wage(String workerName, String workerAddress, int workerNumber, double wage) {

      super(workerName, workerAddress, workerNumber);

      setWage(wage);

   }

   public void checkMail() {

      System.out.println("In checkMail for Wage class ");

      System.out.println("Sending check to " + getWorkerName() + " with wage " + wage);

   }

   public double getWage() {

      return wage;

   }

   public void setWage(double newWage) {

      if(newWage >= 0.0) {

         wage = newWage;

      }

   }

   public double getWorkerPay() {

      System.out.println("Getting wage for " + getWorkerName());

      return wage/52;

   }

}

The Worker class cannot be instantiated, but the Wage class can be instantiated then use its instance to access all fields and methods of the Worker class. Example:

public class AbstractInsta {

   public static void main(String [] args) {

      Wage wg = new Wage("Boss Lilly", "Washington, USA", 4, 4400.00);

      Worker wk = new Wage("John Terez", "Ne Jersey, USA", 3, 3400.00);

      System.out.println("Calling checkMail via Wage reference");

      wg.checkMail();

      System.out.println("\n Calling checkMail via Worker reference");

      wk.checkMail();

   }

}

## Abstract Methods

You may declare a method, then need its implementation to be done in child classes. The class can be marked as abstract in the parent class. Add the abstract keyword before the method name. Abstract methods don’t have a method body. You only add a semicolon (;) at its end. Example:

public abstract class Worker {

   private String workerName;

   private String workerAddress;

   private int workerNumber;

   public abstract double getPay();

}

Note that an abstract method must only be declared in an abstract class. The getPay() method above is abstract. We can have a class inheriting from the Worker class then implement the getPay() method in it:

public class Wage extends Worker {

   private double wake;  

   public double getWage() {

      System.out.println("Getting wage for " + getWorkerName());

      return wage/52;

   }

}

# Chapter 11- encapsulation

This mechanism helps in grouping data and methods together. The data are the variables while methods are code to act on the data. With encapsulation, the class variables can be hidden from other classes, and access to these may only be via methods of the class. Encapsulation is the same as Data Hiding. It’s achieved by declaring class variables as private. The “setter” and “getter” methods for the variables should be declared public and be used to modify the value of the variables.

Example:

public class Students{ 

private String studentName; 

public String getStudName(){ 

return studentName; 

} 

public void setStudName(String studentName){ 

this.studentName=studentName;

} 

} 

You can add a new file to the same package with this code:

public class TestStudents { 

public static void main(String[] args){ 

Students st=new Students(); 

st.setStudName("John"); 

System.out.println(st.getStudName()); 

} 

}

The variable studentName was marked as private in the Students class. The methods setStudName() and getStudName() were declared as public in the Students class. We have instantiated the Students class in the TestStudents class, then we have used this instance to access its variable and methods.

Example 2:

public class Class3 {

   private String personName;

   private String personID;

   private int personAge;

   public int getPersonAge() {

      return personAge;

   }

   public String getPersonName() {

      return personName;

   }

   public String getPersonID() {

      return personID;

   }

   public void setPersonAge( int newPersonAge) {

      personAge = newPersonAge;

   }

   public void setPersName(String newPersonName) {

      personName = newPersonName;

   }

   public void setPersonID( String newPersonID) {

      personID = newPersonID;

   }

}

Any class in need of accessing private variables must use the public methods, that is, the setters and getters. We may access the above as follows:

public class Class3Test {

   public static void main(String args[]) {

      Class3Test cs3 = new Class3Test();

      cs3.setPerName("John");

      cs3.setPersonAge(26);

      cs3.setPersonID("3452673");

      System.out.print("Name : " + cs3.getPersonName() + " Age : " + cs3.getPersonAge());

   }

}

# Chapter 12- Interfaces

An interface refers to the blueprint for the class and it’s abstract methods and static constants. An interface provides a mechanism for achieving abstraction. An interface must only have abstract methods rather than method body. It’s good for achieving multiple inheritances. It’s similar to a class, but with abstract methods only. A class must implement an interface to use its methods. Other than abstract methods, it may have constants, static methods, default methods, nested types etc.

An interface has methods that can be implemented by classes. For a class to implement interface methods, it must be abstract. Otherwise, all interface methods must be defined in the class. An interface can’t be instantiated. It also can’t have constructors. All its fields must be final or static, not instance fields.

To declare one, we use the interface keyword. Syntax:

interface <interfaceName>{  

          //constant fields  

    // abstract methods   

}  

An interface is abstract implicitly, hence don’t add the abstract keyword when declaring it. The methods are implicitly abstract, hence don’t use the abstract keyword when declaring one. They are implicitly public. Example:

interface Mammal {

   public void drink();

   public void makeSound();

}

An interface may be implemented by class:

interface Mammal{

  public void drink();

}

class Cow implements Mammal{

   public void drink(){

     System.out.println("An Interface Method already Implemented");

  }

   public static void main(String args[]){

     Mammal mm = new Cow();

     mm.drink();

  }

}

We created the interface Mammal which has been implemented by the Cow class. Its drink() has been used in the Cow class.

For two interfaces, one interface may extend another one via the extends keyword. The sub-interface (child) will inherit methods of the super-interface (parent). Example:

public interface Toyotas {

   public void setPrice(String carPrice);

   public void setCC(String cc);

}

public interface Premio extends Toyotas {

   public void maximumMileage(int miles);

   public void seats(int seats);

   public void kilometersPerLiter(int kms);

}

public interface Crown extends Toyotas {

   public void interiorSpace();

   public void carLength();

   public void setPrice(String carPrice);

   public void setCC(String cc);

}

We defined the Toyotas interface. The others, Premio and Crown, are extending the Toyotas interface. The interface Crown has four methods, but two of these have been inherited from the Toyotas interface. You may inherit from several interfaces by use of (,) to separate them. Example:

public interface Premio extends Toyotas, Cars

Java doesn’t support multiple inheritance, but we may achieve it via interfaces. Here is another interface example:

interface ObjectInterface{  

void drawObject();  

static int cubeObject(int ab){return ab*ab*ab;}  

}  

class Cuboid implements ObjectInterface{  

public void drawObject(){

System.out.println("drawing cuboid");

}  

}  

public class InterfaceTest{  

public static void main(String args[]){  

ObjectInterface ob=new Cuboid();  

ob.drawObject();  

System.out.println(ObjectInterface.cubeObject(3));  

}

}  

A nested interface is one added inside another interface. Example:

interface Message{  

 void printMessage();  

 interface ShortMessage{  

   void message();  

 }  

}  

The ShortMessage interface has been defined inside the Message interface, making it a nested interface.

# Chapter 13- Packages

Packages help group related interfaces and classes together. The grouping depends on functionality. With packages, we can group classes and find the ones we need easily and avoid naming conflicts. I recommend you create a package and use it to group related classes, interfaces etc. With packages, it’s easy to access variables and methods defined in classes and interfaces in the same package.

A package can be user-defined or built-in. Examples of built-in Java packages include lang, awt, java, javax, net, io, swing, util, sql and others. To use these, use the import statement to be made available in your class. To create packages, use the package keyword then package name. Example:

package testpackage;  

public class PackageTest{  

  public static void main(String args[]){  

     System.out.println("My first package");  

    }  

} 

The package definition statements end with semicolon (; ). When creating packages, use lowercase letters for the name to avoid conflicting with interface/class names. Example 2:

package mammal;

interface MammalsInterface {

   public void drink();

   public void makeSound();

}

We have the package mammal with an interface named Mammals. We can now implement the interface in the package mammal:

package mammal;

public class Cow implements MammalsInterface {

   public void drink() {

      System.out.println("Mammals drink");

   }

   public void makeSound() {

      System.out.println("Mammals make sound");

   }

   public int legCount() {

      return 0;

   }

   public static void main(String args[]) {

      Cow c = new Cow();

      c.drink();

      c.makeSound();

   }

}

If not using a package, the two may be combined into one:

interface MammalsInterface {

   public void drink();

   public void makeSound();

}

public class Cow implements MammalsInterface {

   public void drink() {

      System.out.println("Mammals drink");

   }

   public void makeSound() {

      System.out.println("Mammals make sound");

   }

   public int legCount() {

      return 0;

   }

   public static void main(String args[]) {

      Cow c = new Cow();

      c.drink();

      c.makeSound();

   }

}

## import Keyword

You can access packages outside a certain package. The import keyword is one way of doing it. To access a class in the same package, there is no need for the package to be used. After importing using the packagename.classname syntax, only methods in an imported class will be accessible. Example:

package mypackage;  

public class HelloClass{  

   public void messsage(){

System.out.println("Hi all!");

}  

} 

We have a class named “HelloClass” defined in the package named “mypackage”. Save it in the file HelloClass.java. We have this class:

package pack1;  

 class HelloStudentsClass{  

   public static void main(String args[]){  

   HelloClass hello = new HelloClass();  

    hello.message();  

   }  

}  

The second program will generate an error once executed. We have instantiated the class HelloClass to get the instance hello. We have used the instance to access the message() method defined in HelloClass. Note the two aren’t in a single package. This will generate an error. For this reason, we are instantiating a class not in the same package as the current one. We have to import the class, that is, HelloClass from the package mypackage. We use the packagename.classname syntax at the top of the class as follows:

package pack1;  

import mypackage.HelloClass;

 class HelloStudentsClass{  

   public static void main(String args[]){  

   HelloClass hello = new HelloClass();  

    hello.message();  

   }  

}  

A name for the package and class is useful to avoid the error. With this, no need to use the import keyword as the name will direct to the package and class, then the method will be accessed from there. Example:

package mypackage;  

public class HelloClass{  

   public void messsage(){

System.out.println("Hi all!");

}  

} 

To use the message() method in a class in another package, we can do it as follows:

package pack1;  

 class HelloStudentsClass{  

   public static void main(String args[]){  

   mypackage.HelloClass hello = new mypackage.HelloClass();  

    hello.message();  

   }  

}  

Consider this line:

  mypackage.HelloClass hello = new mypackage.HelloClass();  

The mypackage.HelloClass  helps us access the HelloClass class in the package named mypackage. After that, we can access the message() method defined in the class. Note you access only methods and variables in that class only, not in other classes of the package. Another example:

package armory;

interface weapons {

 public void pistol();

 public void gun();

}

The weapons interface is in the armory interface. We can implement the interface in a similar package:

package armory;

public class ceska implements weapons {

 public void bullets() {

  System.out.println("Ceska has bullets");

}

 public void pistol() {

  System.out.println("It has 10 bullets");

}

 public int ownerID() {

  return 0;

}

 public static void main(String args[]) {

  ceska cs = new ceska();

  cs.bullets();

  cs.ak47();

}

}

# Chapter 14- Command-Line Arguments

These arguments are passed when executing a program. The arguments may be passed via console and received by program, which may act as input. Use command-line arguments to determine how programs behave under different values. Consider this:

public static void main(String args[]){  

We stated it’s the main method, and a program can’t run without it. Consider this:

args[]

It’s part of the main method. Remember Java arrays. They are declared using square brackets. What we have above is an array named args. Command-line arguments originate from here. We pass arguments to the array. Remember the elements begin at index 0. Example:

Open text editor, create a file named CommandLine.java. Add this code to it:

class CommandLine{  

public static void main(String args[]){  

System.out.println("First argument: "+args[0]);  

}  

}  

Save the file the launch command prompt. First, you need to compile it to check errors:

javac CommandLine.java

Next, run it, while passing one argument to it:

java CommandLine Nicholas

It will print something on the console:

![](images/00002.gif)

The argument pass was successful. Without the argument, we could run the program as:

java CommandLine

However, we added the argument after the above. The program was expecting it due to the use of this:

args[0]

The code expects one argument to be kept at index 0 of the array. This will be the first element of our array. Index 0 marks the first element in the arrays.

Sometimes, a user may enter numerous values and need to show them on console. We can use a loop to traverse all elements entered by the user. A “for” loop suits this. Example:

In editor, create a new file named UserInput.java. Add this code to it:

    class UserInput{ 

    public static void main(String args[]){ 

    for(int ix=0;ix<args.length;ix++) 

    System.out.println(args[ix]); 

          } 

    } 

Save the file. It’s time to run it. On console, run this command:

javac UserInput.java

The code will be compiled. Next, run it while passing several arguments to it as follows:

java UserInput Nicholas John James 1 2 3 4

The arguments will be displayed one per line:

![](images/00003.jpeg)

# Chapter 15- Recursion

Recursion occurs after a method calls itself repeatedly. The method becomes a recursive method. With recursive methods, a code will be compact but complicated for understanding. Recursion syntax:

returntype method(){  

//code to run

method();//call same method  

}  

Example:

public class JavaRecursion1 {  

static void helloMethod(){  

System.out.println("Hi all");  

helloMethod();  

}  

public static void main(String[] args) {  

helloMethod();  

}  

}  

The method helloMethod() will call itself infinite times. The implementation for the method to call itself finite times may be implemented this way:

    public class JavaRecursion2 { 

    static int times=0; 

    static void helloMethod(){ 

    times++; 

    if(times<=5){ 

    System.out.println("Hi "+times); 

    helloMethod(); 

    } 

    } 

    public static void main(String[] args) { 

    helloMethod(); 

    } 

    } 

The method prints 1- 5\. We are increasing the value of the times variable until it’s 5\. Note <=5 means 5 is included. With recursion, one can get the factorial for a number:

    public class JavaRecursion3 { 

        static int numberFactorial(int nm){     

              if (nm == 1)     

                return 1;     

              else     

                return(nm * numberFactorial(nm-1));     

        }     

    public static void main(String[] args) { 

    System.out.println("10 factorial gives: "+numberFactorial(10)); 

    } 

    } 

For factorial, a number is multiplied by its preceding numbers except 0\.

With recursion, one may get Fibonacci for a number. Example:

    public class JavaRecursion4 { 

        static int num1=0,num2=1,num3=0;     

         static void showFib(int times){     

            if(times>0){     

                 num3 = num1 + num2;     

                 num1 = num2;     

                 num2 = num3;     

                 System.out.print(" "+num3);    

                 showFib(times-1);     

             }     

         }       

    public static void main(String[] args) { 

        int times=15;     

          System.out.print(num1+" "+num2);//print 0, 1     

          showFib(times-2);//2 numbers already printed    

    } 

    } 

Note the Fibonacci of a number is the sum of two of its previous numbers.

# Chapter 16- Method Calls

Method call is a way of invoking java functions. Java supports call-by-value. There is no call-by-reference in Java. When calling by-value, the original value isn’t changed. Example:

    public class MethodCallExample{ 

     int val=10; 

     void changeValue(int val){ 

     val=val+10;//changes to/in local variable

     } 

     public static void main(String args[]){ 

       MethodCallExample met=new MethodCallExample(); 

       System.out.println("The initial "+met.val); 

       met.changeValue(50); 

       System.out.println("New value "+met.val); 

     } 

    } 

The value won’t change. When calling by-reference, the original value will change if changes are made to the called method. If an object is passed in place of a primitive value, the original value changes. Example:

    public class MethodCallExample2{ 

     int val=10; 

     void changeValue(MethodCallExample2 meth){ 

     meth.val=meth.val+50;//change to instance variable 

     } 

     public static void main(String args[]){ 

       MethodCallExample2 meth=new MethodCallExample2(); 

       System.out.println("Initial value "+meth.val); 

       meth.changeValue(meth);//passing the object 

       System.out.println("New value "+meth.val); 

           } 

    } 

The value has changed from 10 to 60, that is, after adding 50\.

# Chapter 17- Java Applets

Applets are Java programs capable of running on web browsers. It can act like a full functional app since it has full Java API. The applet class extends java.applet.Applet. Applets don’t have a main method, hence they don’t invoke main(). They are embedded on HTML pages. After an HTML page with an applet is opened, its code is downloaded to the local machine. The JVM (Java Virtual Machine) is mandatory for you to view applets.

Applets are processed on the client’s side, hence they give users a quick response compared to other apps. Applets offer good security.

## Applets’ Lifecycle

Applets go through these steps:

1.  Initialization- the init() method initializes applets.
2.  Starting- the start() method starts applets.
3.  Painting- done after calling paint() method.
4.  Stopping- we invoke the stop() method to stop an applet.
5.  Destroying- the applet is destroyed by invoking the destroy() method.

Applets are viewed by HTML. Example:

Create a new file in text editor with the name “MyApplet.java”. Add this code to it:

import java.awt.Graphics;  

import java.applet.Applet;  

public class OurApplet extends Applet{  

public void paint(Graphics gc){  

gc.drawString("First Applet!",150,150);  

}  

    }  

Create a new file in editor named code1.html. Add this code to it:

<html>  

<body>  

<applet code="OurApplet.class" width="320" height="320">  

</applet>  

</body>  

</html>

First, we have Java code in which we added code regarding what our applet should do. The class is named MyApplet. Consider this:

gc.drawString("First Applet!",150,150);  

We are drawing the “First Applet! Text at points 150, 150 of the applet window. Note the two libraries added via the import statement, that is, Graphics and Applet libraries. The paint() method is defined in the Graphics library. If we don’t import it, an error will be generated since Java compiler won’t understand what we mean. We have HTML code in file code1.html. In this, we created a window on which to draw text. Note how we have linked HTML code and Java code:

<applet code="MyApplet.class" width="320" height="320">  

We linked to MyApplet.class rather than MyApplet.java. This means Java code should compile first to give the .class file, then HTML code will recognize it.

Open the OS terminal, navigate to the location of the files. Run this command to compile Java code:

javac MyApplet.java

This will generate the MyApplet.class file. We can use the appletviewer for our applet viewing. Run this command on console:

appletviewer Code1.html

A window should popup with the text First Applet!. That is the Applet.

![](images/00004.gif)

![](images/00005.jpeg)

Change the point where the text is drawn by altering the coordinates. It will change the location on the window.

Try this and see the shapes generated:

Create the file MyPaint1.java with this code:

import java.applet.Applet;

import java.awt.*;

public class Mypaint1 extends Applet

{

public void paint(Graphics gc){

gc.drawOval(130, 40, 60, 50);

gc.drawOval(120, 60, 10, 15);

gc.drawOval(190, 60, 10, 15);

gc.drawOval(160, 50, 10, 10); 

gc.drawOval(140, 50, 10, 10);

gc.drawOval(150, 70, 15, 10);   

gc.drawRect(145, 90, 30, 30);

gc.drawRect(120, 120, 80, 120);

gc.drawRect(130, 240, 20, 120 );

gc.drawRect(170, 240, 20, 120);

gc.drawRect(130, 360, 30, 20);

gc.drawRect(170, 360, 30, 20);

gc.drawLine(200,160,240,240);

gc.drawLine(240,240, 280,160);

gc.drawRect(280, 130, 120, 30);

gc.setColor (Color.red);

gc.fillRect (280, 130, 120, 30);

gc.drawRect(280, 160, 120, 30);

gc.setColor (Color.green);

gc.fillRect (280, 160, 120, 30);

gc.drawRect(280, 190, 120, 30);

gc.setColor (Color.black);

gc.fillRect (280, 190, 120, 30);

}

}

Create the new file Code2.html with this code:

<HTML>

<TITLE>Hellow World</TITLE>

<HEAD>The Hellow Applet</HEAD>

<Applet code="Mypaint1.class" width=500 height=500>

</Applet>

</html>

Compile MyPaint1.java, then run Code2.html.

Graphics library comes with functions/methods that can draw numerous shapes. To draw an oval shape, call the drawOval() method. Pass 4 parameters to it, which are the points to be touched by the edges of the oval. To draw a rectangle, call the drawRect() method and pass 4 coordinates to it which specify its corners. The drawLine() method helps one draw a line. The setColor() method helps in setting object color.

Example 3:

Write this code in the MyPaintClass.java file:

import java.applet.Applet;

import java.awt.*;

public class MyPaintClass extends Applet

{

public void paint(Graphics gc){

gc.drawRect(120, 120, 160, 120);

gc.drawLine(120, 120, 440, 365);

}

}

Its HTML code:

<HTML>

<TITLE>Hellow World</TITLE>

<HEAD>The Hellow Applet</HEAD>

<Applet code="MyPaintClass.class" width=500 height=500>

</Applet>

</html>

Compile the MyPaintClass.java class then run MyPaint.html code with ap-pletviewer. You will get a rectangle and line.

## Displaying Images

Images can be displayed on applets as applets are popular in animations and games. The class java.awt.Graphics has the drawImage() method for image display. The method getImage() returns an image object. The method getCodeBase() returns base URL. The getDocumentBase() image returns document URL in which the applet has been embedded. Example:

import java.awt.*;  

import java.applet.*;  

public class ShowImage extends Applet {  

  Image img;  

  public void init(){  

    img = getImage(getDocumentBase(),"house.png");  

  }  

  public void paint(Graphics gc) {  

    gc.drawImage(img, 30,30, this);  

  }  

  }  

The drawImage() method displays the image. Its 4th parameter is an object for ImageObserver. Save the code in the file named ShowImage.java. Add this code to the file named imageshow.html:

<html>  

<body>  

<applet code="ShowImage.class" width="350" height="350">  

</applet>  

</body>  

</html>  

Compile Java class via the command javac ShowImage.java, then invoke the imageshow.html file via appletviewer. If you specified a correct image in the same directory with these files, it will be shown on the window.

## Applet Animations

Since applets are common in games, images should be moved. Example:

Create the file AppletAnimationExample.java. Add this code:

 import java.applet.*; 

    import java.awt.*;

    public class AppletAnimationExample extends Applet { 

      Image img; 

      public void init() { 

        img =getImage(getDocumentBase(),"car.gif"); 

      } 

      public void paint(Graphics gc) { 

        for(int ix=0;ix<500;ix++){ 

          gc.drawImage(img, ix,30, this); 

          try{

              Thread.sleep(100);

          }

          catch(Exception exc){

          } 

        } 

      } 

    } 

The method drawImage() helps us display an image. Create a new file named animation.html. Add this code:

    <html> 

    <body> 

    <applet code="AppletAnimationExample.class" width="350" height="300"> 

    </applet> 

    </body> 

    </html> 

Compile the .java class then run the .html file. Ensure the correct image is specified in the .java class and keep it in the same directory as the files. It will move after running the code.

## Events on Applets

Events may be added on the applets. Here, we add an event for the applet to display a message after clicking a button: Create the file AppletEvent.java then add this code:

    import java.applet.*; 

    import java.awt.event.*; 

    import java.awt.*; 

    public class AppletEvent extends Applet implements ActionListener{ 

    Button btn; 

    TextField txf; 

    public void init(){ 

    txf=new TextField(); 

    txf.setBounds(30,40,150,20); 

    btn=new Button("Click Here"); 

    btn.setBounds(80,150,60,50); 

    add(btn);

add(txf); 

    btn.addActionListener(this); 

    setLayout(null); 

    } 

     public void actionPerformed(ActionEvent eve){ 

      txf.setText("Message on Applet!"); 

     }  

    } 

Note the applet class implements an interface named ActionListener. This has methods for listening to action events and responding appropriately. New classes have been introduced, that is, Button and Textfield classes. We created instances of these classes, that is, btn and txf respectively to get a button and a textfield. The text Click Here was added to the button, and the setBounds() method is for setting the bounds for the two elements. Consider this:

    btn.addActionListener(this); 

The command adds an action listener event to our button, that is, the button will be waiting or listening to be clicked. After the click, the action specified in the actionPerformed() method will be performed. A text will be added to the textfield, that is, Message on Applet!

Create a new file myapplet.html then add this:

    <html> 

    <body> 

    <applet code="AppletEvent.class" width="350" height="350"> 

    </applet> 

    </body> 

    </html> 

Compile your Java code via the command javac AppletEvent.java, then invoke the .html file via appletviewer  myapplet.html. The applet window will popup, Click the “Click Here” button. A new message will be added to textfield.

![](images/00006.jpeg)

## Applet Parameters

Information on the HTML file may be used as a parameter to the applet. The parameters may be acquired via the getParameter() method of the Applet class. Example:

Create a new file, AppletParameters.java. Add this code:

   import java.awt.Graphics; 

    import java.applet.Applet;

    public class AppletParameters extends Applet{ 

    public void paint(Graphics gc){ 

    String st=getParameter("message"); 

    gc.drawString(st,50, 50); 

    } 

   } 

Create a new file for the HTML code, appletcode.html:

<html>  

<body>  

<applet code="AppletParameters.class" width="350" height="350">  

<param name="message" value="Applet Parameters">  

</applet>  

</body>  

</html>  

In the above HTML code, the value for param name should match the value of the argument passed to the getParameter() method in Java class.

Now, compile your Java code via the javac AppletParameters.java command. The AppletParameters.class file will be generated. Invoke the html code via appletviewer appletcode.html. A window will pop up with text “AppletParameters” on it. This text was specified in value attribute of param name in HTML code.

# Conclusion

Java is a coding language. It’s very popular for being one of the wide programming languages. A lot can be achieved with Java. It is good for development of desktop applications, commonly called standalone applications. It has applets, which can be added/embedded on web pages. It’s easy to learn Java, especially with a background in object-oriented programming. Java supports features of object-oriented programming. Examples include polymorphism, classes, inheritance, encapsulation, etc. To code in Java, you need the Java compiler. This tells you Java is compiled, not interpreted. The compiler is installed automatically after installing the JDK (Java Development Kit).

The JDK is an open-source software, so get it for free and install it on your computer. A text editor is needed, which is where you will write your Java code. Examples include Netbeans, Notepad, Eclipse, etc. With those, you can begin to write your Java codes and run them from the console/terminal of your OS. You invoke the java compiler (javac) to compile the code and generate a .class file, then execute the .class file. The .class file has bytecode, which is platform-independent, that is, it can be run on any platform, for example, Unix, Windows, Mac OS, Solaris, etc.