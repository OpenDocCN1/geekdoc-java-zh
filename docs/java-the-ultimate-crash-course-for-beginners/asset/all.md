![](images/00034.jpeg)

Java

The Ultimate Crash Course For Beginners!

Disclaimer

Effort has been made to ensure that the information in this book is accurate and complete. However, the author and the publisher do not warrant the accuracy of the information, text and graphics contained within the book due to the rapidly changing nature of science, research, known and unknown facts. The author and the publisher do not hold any responsibility for errors, omissions or contrary interpretation of the subject matter herein. This book is presented solely for motivational and informational purposes only.

All Rights Reserved.

No part of this publication or the information in it may be quoted from or reproduced in any form by means such as printing, scanning, photocopying or otherwise without prior written permission of the copyright holder.

TABLE OF CONTENTS

[Introduction](#part0000_split_003.html__Toc442248231)

[Chapter 1 – Java Fundamentals](#part0000_split_004.html__Toc442248232)

[Chapter 2 – Writing Your First Program](#part0000_split_005.html__Toc442248233)

[Chapter 3 – Syntax Errors and Data Types](#part0000_split_007.html__Toc442248234)

[Chapter 4 – Java Control Statements](#part0000_split_009.html__Toc442248235)

[Chapter 5 – Java Methods, Objects, and Classes](#part0000_split_014.html__Toc442248236)

[Chapter 6 – Arrays](#part0000_split_015.html__Toc442248237)

[Conclusion](#part0000_split_017.html__Toc442248238)

# Introduction

This book offers a step-by-step approach in learning Java programming through actual examples and screenshots of codes done in Java language.

The Java Programming Language was first built in 1991 by five employees of Sun Microsystems Inc – Ed Frank, Mike Sheridan, Chris Warth, James Gosling and Patrick Naughton. Their idea was to build a programming language, which can be used on different platforms and could create embedded software that can be sued for consumer electronics. During those times, C and C++ were the accepted programming languages. However, these are not efficient for consumer applications. These languages also rely on their platform as the programs written using them should be compiled first for certain hardware before they become useful.

Below are the primary features of Java:

Simple - Java doesn’t have sophisticated features such as operator overloading, multiple inheritance, memory allocation, and pointers.

Safe - Java features a virtual firewall in between the app and the PC. The codes written in Java are limited within the Java Runtime Environment that doesn’t allow prohibited access.

Portable -  You can run Java codes on any platform or any machine. Java codes are portable as the byte code can be transmitted to any operational platform.

Platform Independent - In the compilation phase, a program written in java is transformed into a byte code that can be used to any platform – Windows, Mac/OS, or Linux. Hence, you can still use a program, which has been compiled on Mac/OS, on Linux and the other way around.

Multi-threading – Java allows a program to do numerous tasks simultaneously

Object Oriented – Java can organize the programs as a bunch of objects, which can represent a class instance.

Distributed – With java programming, it is easy to create applications that can be distributed. You can use a Remote Method Invocation (RMI) or Enterprise Java Beans to develop distributed apps through the Internet.

Robust – Java can handle memory management glitches as well as runtime errors efficiently.

Take note that this crash course is just a beginning of your journey towards exploring the wonderful world of Java programming. This popular programming language is more than the technicalities and programming that supports it. This also involves helpful libraries, which can help you in creating amazing programs.

# Chapter 1 – Java Fundamentals

Changes in the computing world and improvements in the science of programming are the two factors that drive the computer language forward. These two factors also affect the innovation of Java programming. Establishing upon the dynamic legacy of C and C++, Java introduced features and refinements, which mirrors the present state of the programming world. As a response to the emerging web environment, Java has features, which streamline programming for an architecture for high distribution.

Java, C and the C++

Before going any further, it is important first to know the relationship between Java and C/C++. Java is considered as a descendant of C and C++. Java based its syntax from C, while its object model was patterned after C++. Many programmers have been using the syntax of C/C++. This makes it easy for a programmer to learn Java as there is already background information and skills.

Java became popular mainly because it improved an already effective programming structure. C initiated modern programming. It evolved to C++, and now Java. By building upon this rich heritage, Java offers a programming language that is powerful, logical, and takes the best of earlier languages and offers new features that are adaptable for the online structure.

Because of the common elements found on these three languages, it is easy for a professional programmer to switch from one language to another.

A key design philosophy of C and C++ is that you, as a programmer, is in command. This is also true in Java. Except from the limitations of the online world, Java provides you with complete control. Your program will reflect your skills. Even though it is an easy-to-learn language, Java does not have training wheels, it is a language for professional programmers.

Some people consider Java as the internet version of C++, mainly because of the similarities of Java to C and C++, particularly their accessibility through object oriented programming. This is not true. Java still has differences when it comes to philosophy and practical application.

Even though Java was inspired by C++, it is not an improved version of C++. First, it is not downwardly or upwardly compatible with C++. In addition, Java was not created to replace C++. Instead, Java was developed to solve specific problem sets, while C++ was also developed to solve different problem sets. Java doesn’t compete with C++. C++ and Java will continue to be used as separate programming languages.

Java and C#

Several years after the development of Java, Microsoft introduced C #. This is crucial because C# is relevant to Java. As a matter of fact, most of the features of C# is parallel to Java. Java and C# are both founded on the standard C++ syntax, uses the same object model, and provides support for distributed programming.

Of course, there are differences between C# and Java, but the general interface of these two programming languages are quite the same. Hence, if you are familiar with C#, then it will be easier to learn Java. On the other hand, if you are familiar with Java, it will be easier to learn C#.

But C# will not replace Java, because these two are optimized for two distinct types of computing platforms. As Java and C++ will coexist for more years to come, so will Java and C#.

Significant Contributions of Java to the Internet

The Internet greatly helped in the popularity of Java, and conversely, Java had a crucial contribution on the Internet. Aside from streamlining online programming as a whole, Java also developed a new kind of networked program known as applet, which transformed the manner that the internet world consider content. Java also resolved some of the most important concerns about the Web such as security and portability.

Java Applets

Java applets are special types of program, which are developed to be carried over online and instantly applied by an online browser that is enabled with Java. Moreover, Java applets are downloaded depending on the demand, without complicated user interaction. Once a user access a link, which has an applet, the computer will instantly download the files and execute the download codes. Applets are designed to be minor programs. These are usually utilized to display information from the server, deliver basic functions, and manage input from the user.

Applet’s development transformed the online programming as this widened the range of objects, which can move easily in cyberspace. Generally, we have two wide object categories that are channeled from the user to the server such as programs that are passive, dynamic, and active.

If you read an email, you’re reading a passive type of data. Even when downloading a program, the code of the program is still passive unless you launch it. Meanwhile, the applet is a vibrant, self-launching program.

Portability

Portability is a primary aspect of the Internet, because there are various kinds of operating systems and computers attached to it. If you run a Java program to any computer connected to the Web, there should be a method to enable this program to launch on different systems.

For the applet, it should be downloaded and run by the wide range of several CPUs, browsers, OS that are connected online. It is not ideal to have different applet versions for various computers. One code should work for all computers. Hence, there should be a way to generate codes that are portable and executable.

Security

Whenever you are downloading anything from the Internet, there is always the risk of getting your computer or server infected with virus. A harmful code may cause damage to the system once it gains access to your system. For instance, a virus could collect private data such as bank account information, credit card numbers, and passwords.

To allow applets to be downloaded safely and launched on the user’s computer, it was important to prohibit an applet from executing the attack. Java enabled this protection by restricting applets to the execution platform of Java, and not permitting access to other parts of the system.

The capacity to download applets with security is the most innovative aspect of Java.

The Java Byte-code

The reason why Java can address both portability and security concerns is because the compiler output is not an executable code. Instead, it is bytecode, which is a well-optimized chunk of commands developed to run in JVM.

Converting Java program into byte-code will make it easier to execute a program in different platforms as the JVM requires to be executed for every platform. When the package is available for a specific system, a Java program could run. Take note, that even though the JVM details could differ from every platform, everyone can interpret the same bytecode. Once the program is compiled, the various programs of similar program should exist for every type of computer with Internet.

Object Oriented Programming

Object-Oriented Programming (OOP) is a core element of Java. The OOP method is indispensable in Java. Hence, it is crucial to understand OOP in learning Java.

OOP is an effective method to write programs. The methodologies in programming have significantly changed since the rise of computers to address growing program complexity.

For instance, when computers were first developed, programming was performed by changing the binary machine instructions through the front panel of the PC. This method is practical if the programs are of an average length. Assembly language was developed as the programs grew, to make it easier for the programmer to manage larger and more complex programs using symbolic representations of machine instructions.

As programs continue to expand, programmers developed high-level languages, which gave the programmer more tools that could manage complexity.

OOP used the best ideas of structured programs and integrated them with different concepts. This resulted to a special way in structuring a program. In general, a program could be structured through a code or through data. Using only structured program techniques, programs are usually organized relevant to the code.

In order to support OOP, Java, as well as other languages, have three common attributes: inheritance, polymorphism, and encapsulation.

Inheritance

Inheritance refers to the process by which an object can obtain the properties of another object. This is crucial as it supports the idea of hierarchical organization. Without hierarchies, every object should be defined explicitly. Through inheritance, an object is only required to define the qualities, which make it unique within the class. This could inherit its basic attributes from the parent. Hence, this is the inheritance mechanism that makes it easy for an object to be a specific occurrence.

Polymorphism

Polymorphism (many forms) is the attribute, which allows an interface to access basic class of actions. The certain action is defined by the specific nature of the situation. The concept of polymorphism is usually defined by the phrase “multiple methods, one interface.” Hence, it is possible to design a generic interface to a group of relevant activities. Polymorphism can help in decreasing complexity by accessing similar interface that you can use to ascertain a general class of action.

Encapsulation

Encapsulation is a programming method, which integrates the code including the data that it handles, and that stores both to avoid misuse and external interference. In an OOP language, the data and code can be combined together in such a manner that a self-containing black box is built. Inside the box are the all-important code and data. If code and data are combined together in this manner, we can create an object. Hence, an object is the device that supports encapsulation.

# Chapter 2 – Writing Your First Program

Now that you have learned the fundamentals of Java, it is time to begin writing your first Java program. Before compiling and running the programs, you should install the Java Development Kit (JDK). This is a free program from Oracle. As of press time, the latest release is JDK 8\.

Since JDK 8 offers several new features that are not included in the initial Java versions, it is best to use JDK 8 to compile and run the programs you will learn in this book. Using an earlier version may result to the programs not compiling.

You can download the latest version of the JDK through this link:

[http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

Just visit the Oracle download page and choose your computer type. After installing the JDK, you can compile and run programs. JDK supports two main programs: javac and java. The latter is the basic Java interpreter and also known as the app launcher.

Take note that JDK is not a windowed application. It runs in a command prompt environment, which uses command-line tools. This is also not an integrated development environment (IDE).

Aside from the standard command-line tools offered with the JDK, you can use other IDEs like NetBeans. Using an IDE could be helpful in the development and deployment of commercial applications.

Write Your First Java Program

Now that we are all set, we can start compiling and running a short program. Use the code below:

![nuno.jpg](images/00001.jpeg)

There are three basic steps that you need to follow: Enter, Compile, and Run

Entering Programs

It is possible to enter programs manually. In this example, you can enter the program into the computer through a text editor. Remember not to use a word processor, which usually store format data alongside text. This data will conflict with the Java compiler. If you are using a Windows PC, you can use WordPad or any programming software that you want.

In other programming languages, the file name that stores the source code to a program can be random. In Java, this is not true. The name of the source file is very crucial in Java. In our example, the name of the source file must be FirstProgram.java.

In Java programming, the source file is formally known as a compilation unit. This is a text file, which contains one or several class definitions. At this point, we will use source files, which contain a single class.

The Java compiler calls for a source file, which use the filename .java. As you can see in our first program, the class name of the program is also FirstProgram. This is not a random occurrence. All code should be confined within a class. Conventionally, the name of the main class must match the file name, which holds the program.

Take note that the capitalization of the filename must match the name of the class. Java is sensitive to character case. This format makes it easier to keep and organize programs.

Compiling Programs

In compiling the FirstProgram, launch the compiler javac by specifying the source file name on the control line like below:

![nuno1.jpg](images/00002.jpeg)

The java compiler will create a file named as FirstProgram.class, which stores the bytecode version of the program. Take note that the bytecode is not an executable code. Bytecode should be executed using a JVM. Hence, the output of javac is not a code, which could be executed directly.

To run the program, you can use the Java interpreter, java. In order to do this, pass the class name FirstProgram as a control-line argument as you can see below:

![nuno2.jpg](images/00003.jpeg)

Once you run the program, the output below will be shown:

![nuno3.jpg](images/00004.jpeg)

When you compile the program, every class will be confined into the output file named after the class and using the extension .class.  Therefore, it is ideal to provide your Java source files similar name as the class they handle – the source file name would match the name of the file .class. Once you run the Java interpreter, you are really specifying the class name that you like the interpreter to run. This will instantly search for a file through that name with the extension .class. Once it finds the file, this will run the code containing the defined class.

Even though FirstProgram.java is a bit short, this will include few key features that are common to all Java programs.

Our program starts with the following lines:

![nuno4.jpg](images/00005.jpeg)

The starting line is the “comment”. Similar to other programming languages, Java will allow you to insert a comment directly into the actual source file of the program. The compiler ignores these comments so they do not affect the code in any way. Rather, the comment explains or describes the program operation to other readers of the source file. At this point, the comment provides a description of the program and includes a reminder that the source file must be named as FirstProgram.java.

There are three comment styles in Java. A comment inserted at the top of the program is a “multiline” comment. This comment type should start with /* and ends with */. All the text confined inside these two comment symbols will be ignored by the compiler. As the name implies, a multiline comment could be several lines long.

The next code line in our first program is shown below:

![nuno5.jpg](images/00006.jpeg)

In this line, we will use the class keyword to state that a new class will be defined. Remember, the class is the basic unit of encapsulation in Java. FirstProgram is the class name. The class definition starts with the opening curvy bracket ({) and terminates with the closing curvy bracket (}). The codes confined between these braces are known as class members.

For now, don’t worry about the specifics of a class, but do take note that in Java the program activity happens inside one.

The next line in this program is the single-line comment like below:

![nuno6.jpg](images/00007.jpeg)

This is another type of comment in Java. A one-line comment starts with two right slanting lines (//) and terminates at the end of the line. In programming, you can use multiline comments for longer comments and one-line comments for short, line after line remarks.

Here is the next code line:

![nuno7.jpg](images/00008.jpeg)

This line starts the main( ) method. In Java, a subroutine is a method. As described in the earlier comment, this is the line where the program starts the execution. Java apps start executing codes by calling main( ).

We still cannot provide the specific meaning of every part of the line because it requires deeper understanding of other Java features. But because many of the examples in this book will use this code line, here’s a basic information about every part.

The keyword public is the access modifier, which defines how other parts of the program could access the class members. When you see a class member preceded by the keyword public, this member could be accessed by the code outside the class. The opposite keyword is private that prohibits a member from being used by code declared outside the class. At this point, main( ) should be defined as public, because it should be called by code outside the class once the program runs. The keyword static lets main( ) to be called before the object of the class has been made. This is crucial because main( ) is known by the JVM before any objects are created. Next, the keyword void will basically tell the compiler, which main( ) does not yield a value. Methods can also yield values.

As already described, main( ) is the method called once a Java application runs. Any data, which you need to pass through a method, is accepted by variables defined within the set of parentheses, which follow the name of the method. These variables are known as parameters. If there are no required parameters, you can still include empty parameters. In main( ), we only have one parameter:

String args[ ]

This declares a parameter known as args. This is an array of objects of String type. Arrays refer to the group of similar objects. String type objects handle character sequences. At this point, args will receive any control-line arguments present once you run the program.

The last element on the line is the {, which signals the start of the body of main( ). All the code confined within a method will happen between the opening curvy brackets of the method and the closing curvy bracket.

Here is the next code line. Take note that this is confined within main( ).

![nuno8.jpg](images/00009.jpeg)

This code line will display the string “Java is a great programming language” followed by a new line on the screen. The output can be accomplished through the built-in method: printIn( ). At this point, print( ) shows the string that has been passed to it. As you can see, printIn( ) could also be used to show other kinds of information. The line starts with System.out.

System is a pre-established class, which provides access to the system, while out is the output stream, which is linked to the console. Hence, System.out is an object, which encapsulates output console.

Take note that the printIn( ) statement terminates with a semicolon. Java statements should be ended with a semicolon. Other lines in the programs that are not ending in a semicolon are actually not statements.

The first curvy bracket in the program terminates main( ), and the last } terminates the FirstProgram class definition.

As we have already discussed, Java is case sensitive. Disregarding this might cause serious problems. For instance, if you have mistakenly type Main instead of main, or PrintIN rather than println, the program before this could wrong. Moreover, even though the Java compiler could compile classes, which don’t contain the main( ) method, there is no way to run them. Hence, if you had incorrectly entered main, the compiler will still compile the program. But the interpreter will result to an error, because it is not capable of finding the method main( ).

# Chapter 3 – Syntax Errors and Data Types

If you have tried programming before, you know by now that typos are very common, which could lead to errors. If there is a mistake in the code, the compiler will show a syntax error prompt after trying to compile it. The Java compiler will try to interpret the source code regardless of what you have written. Hence, the error that is shown doesn’t always represent the actual cause of the problem.

For instance, in our FirstProgram example, an unintended omission of the opening curvy bracket after the method main( ) will cause the compiler to display the following errors:

![nuno9.jpg](images/00010.jpeg)

The first message error is clearly wrong, because what has been omitted is a curvy bracket and not a semicolon.

If your program has a syntax error, there is no need to interpret the message compiler literally. More often than not, the messages could be misleading. You still need to assess the error message to find out the real problem. You should also pay attention to the last several code lines in the program that precedes the line with suspected error.

Second Program

Probably no other construct is as crucial to a programming language as the assigning of a value to a variable. A variable refers to a defined memory location, which could be allocated with a value. Moreover, the value of a variable could be transformed during the program run. It is important to take note that the variable content can be changed. It is not fixed. In the program below, we can create two variables known as var1 and var2.

![nuno10.jpg](images/00011.jpeg)

![nuno11.jpg](images/00012.jpeg)

Once you run this program, the following output should display on your screen:

![nuno12.jpg](images/00013.jpeg)

We are introduced with new concepts in this program. First, we have the statement:

![nuno13.jpg](images/00014.jpeg)

This expresses a variable known as var1 of integer type. Take note that in Java, you need to declare all variables before you can use them. Moreover, you should also specify the type of values that the variable can hold. This is known as the variable type. In this example, var1 can store values of the integer type or whole number values. To express an integer variable in Java, it should be preceded with the int keyword. Hence, the preceding statement expresses a variable known as var1 of the int type.

The line below expresses another variable known as var2:

![nuno14.jpg](images/00015.jpeg)

Take note that this line utilizes the same format similar to the first line. The only difference is the name of the variable.

Generally, you need to use the line below to express a variable:

type var-name;

In this format, the type  specifies the type of variable you want to express, while the var-name is the variable name. Aside from int, Java is supporting other types of data.

Take note that in Java, the operator assignment is the equals sign. Its function is to copy the value in the left side to the right side.

The next line displays the value assigned to var1 preceded by the string: “var1 has”:

![nuno15.jpg](images/00016.jpeg)

In the line above, the plus symbol will cause the var1 value to be shown after the string, which precedes it. This method could be generalized. Through the plus sign operator, you can combine together several objects as you prefer inside a single println( ) statement.

The next code defines the value of var2 – the var1 value divided by 3:

![nuno16.jpg](images/00017.jpeg)

This code will divide the value assigned in var1 by 3, and then store the result in var2. Hence, after executing the line, var2 will store the value of 345\. The value assigned to var1 will be fixed. Similar to most other programming languages, Java uses arithmetic operators: addition (+), subtraction (-), multiplication (*), and division (/).

Below are the next codes in the program:

![nuno17.jpg](images/00018.jpeg)

There are two new things that are happening here: the print( ) method is used to show the string “var 2 contains var1 / 3: ”. Notice that this string is not followed by a new line. Hence, once we generate the next output, it will begin on the same line. The print( ) method is similar to println( ), except that it doesn’t display a new line after every call. Next, in the line to println( ), take note that var2 is used as itself. The print( ) and println( ) could be utilized to display the values of any of Java’s built-in types.

Before we proceed, you first need to understand another important concept in expressing variables. You can express two or more variables even with one declaration line. You just need to separate the variable names by using commas.

For instance, var1 and var2 could be expressed like this:

![nuno18.jpg](images/00019.jpeg)

Floating Point Data Types

In the previous program, we have used the int variable type. But this type can only store whole numbers. Hence, it cannot be used for fractional components. For instance, a variable int can store the value of 20, but not 20.5\.

But in Java, int is only one of the many data types that you can use. To store numbers with fractional components, you can use either float or double. These floating point types represent single and double precision values. The double type is commonly used.

In order to declare a double variable type, you can use a statement like this:

![nuno19.jpg](images/00020.jpeg)

In this statement, a refers to the variable name, which is double type. Since a has a floating-point type, it could store values such as 133.43, 0.045, or -20.5

In order to understand the difference between int and double you can try the following program:

![nuno20.jpg](images/00021.jpeg)

When you run this program, you will see the output below:

![nuno21.jpg](images/00022.jpeg)

As you will notice, when var was divided by 8, the program performed a whole number division, and the result is 2 instead of 2.5 because the fractional component was lost. But when a was divided by 8, the program preserved the fractional component and the correct answer was shown.

Another new component in this program is the use of println( ) without any args in order to insert a blank line.

# Chapter 4 – Java Control Statements

Within a method, the program runs from one line to another, from up to down. But like other programming languages, Java also allows the programmer to control the flow by using the different Java program control statements such as the if Statement and the for Loop Statement.

The if Statement

It is possible to selectively run a part of a program by using the conditional if statement. The if statement in Java works much like the IF statement in other languages. Below is its simplest form:

If(condition) statement;

In this line, condition is a Boolean expression. If  the condition is true, then the program will run the code. If the condition is not true, then the statement will be ignored. Below is an example:

![nuno22.jpg](images/00023.jpeg)

In this example, because 20 is lower than 21, the conditional expression is true, so the println( ) will run.

Take a look in the line below:

![nuno23.jpg](images/00024.jpeg)

In this example, 20 is not lower than 19. Hence, the println( ) will not be executed.

Java supports a range of complementary relational operators, which could be used in conditional expressions:

Less Than ( < )

Less Than or Equal ( <= )

Greater Than ( > )

Greater Than or Equal ( >= )

Equal To ( = = )

Not Equal ( != )

Take note that the double equal sign is used for equality test. Below is the program that shows the if statement:

![](images/00025.jpeg)

When this program is ran, the output should be like this:

![](images/00026.jpeg)

Take note of another new concept in this program:

int x, y, z;

This line expresses the variables, x, y, and z, by using a list separated by list. As we have discussed earlier, if you need several variables of similar type, you can express them even in a single statement. You just need to separate the variables by using commas.

The for Loop

In Java, it is possible to execute a series of code repeatedly through a loop. Java supports a powerful range of loops. For now, we will take a look at for loop. Below is the simplest format of the for loop:

for(initialization; condition; iteration) statement;

In this common format, the initialization part of the loop will set the loop control variable to an initial value. The condition is a Boolean line, which checks the variable control loop. If the result of that test is true, the for loop will continue to run. If the result is false, the for loop will be terminated. The iteration line defines how the variable control loop is changed every time the loop iterates.

Below is a simple program, which shows the for loop:

![nuno27.jpg](images/00027.jpeg)

The output displayed when you run the program should be like this:

![nuno28.jpg](images/00028.jpeg)

In this case, the loop control variable is count. The default zero in the initialization part of the for. At the beginning of every iteration, which includes the first one, the conditional test count < 6 is executed. If the result of this test is true, the print( ) line is performed and then the iteration part of the loop will run by increasing the count by one unit. This sequence will continue until the condition test will be false, in which the execution will pick up at the bottom of the loop.

It is interesting to take note that in a well-written program, you will not see a part of the loop written in the iteration. Rare is the chance that you will see line such as this:

count = count + 1;

In Java, you can use a special increment operator to perform this operation. The double plus sign (++) is the increment operator, which increases the operand by 1\. Through this increment operator, the statement can be written like this:

count++;

Hence, the for in the previous program can be written like this:

for(count=0; count < 6; count++)

You can try this, and you will notice that the loop will run the same. Meanwhile, Java also supports a decrement operator using the two minus signs (--), which decreases the operand by 1\.

Code Blocks Creation

Code block is another core element of Java. Code block refers to a group of two or more statements. Creating code blocks can be done by confining the statements within opening and closing curvy brackets { }. When you create a code block, it will become a logical unit, which could be used in any place that one statement can. For instance, a code block could be a target for if and for statements in Java. Take a look at this if statement:

![nuno29.jpg](images/00029.jpeg)

In this example, if k is less than l, the statements within the block will run. Hence, the two statements within the block will create a logical unit, and a statement cannot run without the other also running.

The main point here is that creating a block will allow you to logically connect two or more statements. Code block also permit several algorithms to be executed with better efficiency and clarity.

Below is a program, which uses a code block to prohibit division by zero:

![nuno30.jpg](images/00030.jpeg)

Running this program will display this output:

![nuno31.jpg](images/00031.jpeg)

In this program, the target of the if statement is a code block and not only one statement. If the condition that is controlling the if is true (like in our example), the three statements within the block will run. Try setting h to zero, and take a look at the result. You will notice that the whole block will be ignored by the program.

Using Semicolon in Java

In Java programming, the semicolon is used as a separator, which is used to end a statement. Hence, every statement should be terminated with a semicolon. It signifies the end of one logical object.

As you already know, a block is a group of logically related statements confined by opening and closing brackets. A block should not be ended with a semicolon. Because a block is a collection of statements, with a semicolon after every statement, there is no need to end the block with a semicolon. Rather, the code block is ended with a closing brace.

Java doesn’t read the end of the line as a terminator. Hence, the position of the statement doesn’t matter.

For instance:

a = b;

b = b + 1;

System.out.println(x + “ ” + b);

This line will be interpreted as the same with Java:

a = b; b = b + 1; System.out.println(x + “ ” + b);

Moreover, each element of a statement can also be confined on individual lines. For instance, this line is acceptable:

System.out.println(“This is a lengthy output” + a + b + c + “more display”);

Breaking down lengthy lines in this manner is typically used to make the programs more readable. This could also prevent too much lines for wrapping.

Indentation

Probably you have already noticed that in the previous programs, specific statements were indented. It really doesn’t matter where you position the statements on a line. But through the years, a conventional manner of indentation has been developed to make the programs more readable. This book adheres to that style, and it is best to follow this convention. In this style, you should indent a level after every opening bracket, and move back a level after every closing bracket.

Java Keywords

There are 50 keywords defined by Java, which you can combine with the syntax of separators and operators. Take note that you cannot use these keywords as name for your method, class, or variable.

The following are Java keywords:

![nuno32.jpg](images/00032.jpeg)

The keywords goto and const are reserved by Java but these are not used. During the initial years of Java, there are keywords that were reserved so that they can be used in the future. But the existing specification for Java described only the keywords that are listed above.

Aside from these keywords, Java also reserves the following: null, true, and false. These are values that are already defined by Java. You cannot use these words to name your variables or classes.

Java Identifiers

Java identifiers refer to the name of a specific variable, a method, or any other item that are defined by the user. They could run from one to several characters long. Variable names may begin with any letter, a dollar sign, or an underscore. The underscore is ideal to use as it enhances the readability of the variable name such as java_data_program instead of javadataprogram. Also take note that uppercase and lowercase are not the same. Hence, datavar is different from DataVar.

The following identifiers are acceptable:

Test

b

b3

LoadInfo

$pu

_bot

var_one

sampler_18

Take note that starting an identifier using a digit is not allowed. Hence, 23sampler is not allowed.

As discussed earlier, we cannot use the reserved Java keywords as the name identifier. You must not also use the name of Java methods like println. Beyond these limitations, professional programming practice recommend using identifier names, which reflect the usage or meaning of the items named.

Java Class Libraries

The programs that we have worked on this chapter used two of the commonly used built-in methods in Java: print( ) and println( ). You can access these methods by using System.out. System refers to a class that has been defined by Java, which is instantly encoded in your program. In general, the Java platform depends on different built-in class libraries, which contain numerous built-in method that offer support for these things as graphics, networking, string management, and I/O.

Standard Java classes can also support graphical user interface (GUI). Hence, Java as a whole is an integration of the programming language itself on top of its standard classes.

As you practice Java, you will see that the class libraries provide much of the function that comes with the code. As a programmer, it is important for you to learn the standard Java classes. You can’t learn all the Java library by reading this book, as this is an area that you need to explore more on your own.

# Chapter 5 – Java Methods, Objects, and Classes

An important concept that you must learn in Java is the use of class. The class is considered as the core of Java, because it serves as the foundation upon which the whole Java language is created, because the class can describe the nature of the object. Hence, we can say that in Java, the class forms the foundation for object-oriented programming.

Inside a class are defined data and code, which acts according to that data. The code is confined in the methods. Since methods, objects, and classes are basic to Java, they are included in this book. Learning the basic of these features will train you to write more complicated programs, and you can better understand specific key element of Java.

Fundamentals of Java Class

Because all activities of Java happen inside a class, we have been utilizing classes since the beginning of this book. But simple examples have been used, and there is more to them in programming. There are classes with substantial power compared to what we have used.

Let’s start by going over the basics. A class is generally a template, which defines the object form. It also describes the data as well as the code, which will operate on this data. Objects are occurrences of a class. So in essence, a class is a set of plans, which define how you can build an object. It is crucial to clarify this one concern: a class is a logical abstraction. A physical representation of this class will exist in memory only when an object of that particular class has been made.

Also take note that the variables and methods that compose a class are known as members of the class. The members of data are also named instance variables.

Class Forms

Once you define a class, you are declaring its actual nature and form. You can do this by specifying the instance variables, which it contains as well as the methods you use to operate them.

Even though simple classes may contain only instance variables or only methods, many actual classes can handle both.

The keyword class is used to create a class. Below is a simple general form of a class:

![nuno33.jpg](images/00033.jpeg)

Even though there’s no solid rule, which enforces it, a class that is well-designed must describe only one logical object. For instance, a class storing employee names and their ID numbers will normally not store information about the daily temperature, stock market prices, or foreign exchange rates. The key here is that class groups that are well-written will only group information that are logically related. Confining unrelated information within the same class will affect the structure of your code.

At this point, we have been only using one method: main( ). As you study Java programming, you will also learn how to create other methods. But you should take note that the general form of a class does not define a main( ) method. A main( ) method is only required if this class is the beginning point for your program. In addition, some types of Java applications like applets do not need a main( ).

Methods

Methods and instance variables are components of classes. Even though data-only classes are valid, most classes will have methods. Methods are subroutines, which control the data assigned by the class, and in most cases, offer access to this data. More often than not, other portions of the program will engage with a class using its methods.

A method confines several statements. A code that is well-written will define one method to function a single task. Every method has its name, and this name will be used to call the method. Generally, you can provide a method, regardless of the name you want. But bear in mind that main( ) is reserved for the method, which starts running the program. Meanwhile, you should not use Java keywords for the name of the methods.

A method is always followed by parentheses after the name. For instance, if a method is obtainval, it should be written as obtainval( ) when the name is used in the sentence. This notation could help you in distinguishing variable names.

Below is a general form of a method:

ret-type name( par list ) {

// method body

}

In this format, the ret-type will specify the data type that is returned by the method. This could be any valid type, which includes the class types that you are creating. If the method is not returning a value, the return type should be void.

The method name is specified by the name. This could be any legal identifier other than those already used by other objects in the present scope. The par-list is a series of type and identifier pairs isolated by commas. Parameters are basically variables, which receive the value or args passed to the method once it is called. The parameter list will be empty if the method has no parameters.

In Java, it is possible to pass several values to the method once you call a method. Remember, a value passed to a method is known as an argument. Within the method, the variable, which receives the argument is known as a parameter.

Parameters are expressed within the parentheses, which follow the name of the method. The parameter expression syntax is the same as used for variables. A parameter is confined within the method scope, and apart from the special function of obtaining an argument, it serves like other local variables.

# Chapter 6 – Arrays

In Java programming, an array refers to the group of variables of similar kind, which is referred by a common name. Arrays could have several dimensions, even though the one-dimensional array is the most common.

Arrays are used for different purposes, because they provide an easy way to group together variables that are related to each other. For instance, you can use an array to store a record of temperature readings every day for a year, a list of forex market exchange, or a list of all books about computers in a library.

The main benefit of an array is that it could organize data in such a way, which it could be controlled easily. If you have an array holding the salaries of people in a specific profession, it will be easy to calculate the average salary by organizing an array. In addition, arrays arrange data in such a manner, which it could be easily sorted.

Even though arrays in Java could be used similar to arrays in other languages, they have one special trait: they are executed as objects. There are several benefits of running arrays as objects.

One-Dimensional Java Arrays

A one-dimensional array refers to a list of variables that are connected to each other. This is very common in programming. For instance, you can use a one-dimensional array to hold the ID numbers of active employees on a company. Another array could be used to hold the present survey ratings for a media network.

To express a one-dimensional array, this format can be used:

type name-array[ ] = new size[type];

In this format, type expresses the type of element of the array, which is also known as the base type. The element type defines the data type for every element confined in the array. The number of elements, which the array can hold is determined by size. Because arrays are run as objects, the creation of an array is a dual process. You first need to express the reference for the variable array. Then, you can define memory for the array, defining a reference to the memory to the variable array. Hence, Java arrays are allocated dynamically by using the operator new.

In the example below, the code generates an int array of 10 elements and connects it to the variable reference array named javalist:

int javalist[] = new int[5];

The function of this declaration is quite similar to the declaration of an object. The variable sample stores a reference to the memory defined by new. This memory is large enough to store 10 elements of type int. Like objects, you can break the first expression into two lines:

int javalist[];

javalist = new int[5];

In this format, if the javalist is first created, it will refer to no physical object. It is only after the second statement runs the javalist will be connected through an array.

You can access a separate element confined in an array, using an index. The index describes the element position confined in an array. In Java, the arrays have zero as the index of the first element.

Since javalist has 10 elements, the index values will be from zero to nine. To index the array, you can specify the number of the element that you like, confined by square brackets. Hence, the first element in javalist is javalist[0], and the last element will be javalist[9].

Multidimensional Arrays

In Java, a multidimensional array is considered as an array of arrays. The most basic form of multidimensional array is the two-dimensional array. In general, a two-dimensional array is a list of one-dimensional arrays. In order to express a two-dimensional integer array score of size 5, 10, 15 you can write in this format:

int score[ ] [ ] = new int [ 5 ] [ 10 ];

Take note of the declaration. Not similar to other programming languages that use commas to separate the dimension array, Java can place every dimension on its confined brackets. In order to access point 4 and 8 of array score, you can use score [4] [8].

# Conclusion

Thank you again for downloading this book!

I hope that you have learned the fundamentals of Java programming.

The next step is to learn more about this language and continue practicing until you achieve mastery.

Thank you and good luck!

Did you like this book?

If you enjoyed this book, please give your review on Amazon: [CLICK HERE!](https://www.amazon.com/review/create-review?ie=UTF8&asin=B01BF1YXWI&ref_=dpx_acr_wr_link)

If you believe this book is worth sharing, would you take a few seconds to let your friends know about it?

If it turns out to make a difference in their lives, they'll be forever grateful to you.

As I will.

All the best,

Mark Heisenberg