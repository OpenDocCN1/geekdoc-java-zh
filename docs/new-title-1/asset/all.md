![](Images/cover00286.jpeg)

JAVA CRASH COURSE

Beginner’s Course To Learn The Basics Of Java Programming Language

# Table Of Contents

Introduction

Chapter 1: Getting Acquainted with Java

Chapter 2: It Always Starts with “Hello”

Chapter 3: Getting to Know the Different Data Types, Variables, and Reserved Words

Chapter 4: Useful Pocket Tables and the Different Operators

Chapter 5: All About the Math

Chapter 6: Talk About Taking Control

Chapter 7: More Practice

Chapter 8: Your Own Java in your Computer

Conclusion

Introduction

I want to thank you and congratulate you for downloading the book, “Java Crash Course – Beginner’s Course To Learn the Basics of Java Programming Language”.

This book contains basic steps and strategies in learning Java programming, and helpsyou create your own program.  It is this book’s best interest to teach you everything you need to know about the basics of Java programming.  After reading each chapter, you will be a step closer to understanding, and eventually mastering this programming language.  I wrote this book using simple terminologies, with a bit of programming jargon, to make it easier to understand.    

You should be able to grasp the essence of each lesson within a day.  There are lessons that you can fully understand within 5 hours, but then again, some might take you a day or two to grasp fully.  You need to allot a bit of your time every day, and also have a bit more patience than usual, for the lessons that you find challenging to meet the goal of learning Java within seven days or less. 

You can double the time that you want to allot in learning Java if you are a fast learner.  You can choose to take two lessons at a time, but it is not advisable.  While you learn the language, don’t take away the fun in learning.  Pushing yourself too hard might wear you out quickly before you get to the more fun part of learning Java.

This book will give you lots of sample programs with accompanying explanations.  It is always better to learn by example.  There are programming or coding exercises that you need to do on your own.  But you will be provided with an output so you will know if you got it right.

Your Java journey starts right here, right now. 

Thanks again for downloading this book, I hope you enjoy it!

 Copyright 2015 by LIFE-STYLE EBOOKS - All rights reserved.

This document is geared towards providing exact and reliable information in regards to the topic and issue covered. The publication is sold with the idea that the publisher is not required to render accounting, officially permitted, or otherwise, qualified services. If advice is necessary, legal or professional, a practiced individual in the profession should be ordered.

- From a Declaration of Principles which was accepted and approved equally by a Committee of the American Bar Association and a Committee of Publishers and Associations.

In no way is it legal to reproduce, duplicate, or transmit any part of this document in either electronic means or in printed format. Recording of this publication is strictly prohibited and any storage of this document is not allowed unless with written permission from the publisher. All rights reserved.

The information provided herein is stated to be truthful and consistent, in that any liability, in terms of inattention or otherwise, by any usage or abuse of any policies, processes, or directions contained within is the solitary and utter responsibility of the recipient reader. Under no circumstances will any legal responsibility or blame be held against the publisher for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly.

Respective authors own all copyrights not held by the publisher.

The information herein is offered for informational purposes solely, and is universal as so. The presentation of the information is without contract or any type of guarantee assurance.

The trademarks that are used are without any consent, and the publication of the trademark is without permission or backing by the trademark owner. All trademarks and brands within this book are for clarifying purposes only and are the owned by the owners themselves, not affiliated with this document.

Chapter 1: Getting Acquainted with Java

You are here now because you are interested to know and learn Java programming.  It is best to start right away, but you need to understand a few things before you can start your Java journey.  For online coding it is recommended to go to this site: [https://www.compilejava.net/](https://www.compilejava.net/).

The link provided is an online Java IDE (Integrated Development Environment).  You need to clear the written codes on the online Java IDE prior to writing your own codes.  It is also advisable to type your codes directly on the online Java IDE. 

If you know a few things about Java, then you must have learned that when you install this programming language to your computer, you need to use a text editor.  But, if you choose to write your codes on the online Java IDE, then you don’t need to use a text editor.  Copy-pasting your work from a text editor to the online IDE might introduce characters or symbols that the online Java IDE might not recognize, such as the quotation marks.  The online IDE only accepts these symbols for quotation marks: '  ' and  "  ". 

Take this sample program that has been written on a text editor and copy-pasted on the online Java IDE :

| 1 | public class CompareData { |  |  |  |  |  |
| 2 |      public static void main(String []arqs) { |  |  |  |
| 3 |        char tChar=‘r’; |  |  |  |  |  |  |
| 4 |        int tDigit=3; |  |  |  |  |  |  |
| 5 |        system.out.prntln(tChar==tDigit); |  |  |  |
| 6 |      } |  |  |  |  |  |  |  |  |
| 7 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

The sample program gave this error:

| /tmp/java_hZowrg/CompareData.java:3: error: unmappable character for encoding ASCII |
|       char testSampChar = ???R???;; |  |  |  |  |  |  |
|                           ^ |  |  |  |  |  |  |  |

The error means the program used unacceptable quotation marks; you need to change it directly on the online Java IDE.  

Before you can proceed to learning Java, you must have at least a basic understanding of how to operate a computer.  It would take you less than 7 days to learn Java if you already know a particular programming language and knows how to write the codes for that language.

If you are a beginner at coding, you need to draw a flowchart because it will serve as your guide in creating your program or writing your codes.  A flowchart is a diagram that uses different shapes or boxes.  Each shape represents a certain process.  You need to put the instructions, data, or variable inside each box. 

You can use a particular flowchart for one programming language and then use the same flowchart for another programming language.

This is what a flow chart looks like:

![](Images/image00278.jpeg)

You can use the sample flowchart to create a Java program, and use it again for your C+ program. 

The Meaning of Each Shape in Flowchart

You only need to learn the basic flowcharting shapes and their use so you can make your own.

| ![](Images/image00279.jpeg)  | process | You use this symbol to indicate internal operation in the memory or processor. |
|  ![](Images/image00280.jpeg) | predefined process | You use this symbol to call on a subroutine. |
| ![](Images/image00281.jpeg)  | decision | You use this symbol if there's a decision that must be made.  It should be answerable by yes or no, true or false. |
|  ![](Images/image00282.jpeg) | input/output | You use this symbol for input/ output.  Your program tells the computer to obtain data. |
| ![](Images/image00283.jpeg)  | terminal | You use this symbol to indicate the start or end of the program flow. |
| ![](Images/image00284.jpeg)  | connector | You use this symbol to indicate the continuation of the flow to the next page or routine. |
| ![](Images/image00285.jpeg)  | flow lines | These lines show the direction of the flow. |

Learning a programming language is like learning a spoken language.  You need to familiarize yourself with the syntax of a particular programming language that you want to learn and use.  Otherwise, your program won’t run.

A Glimpse of the Past

Java is a high-level programming language that can create powerful and secure applications.  It runs on a variety of platforms or operating systems (OS), such as Linux, Windows, Mac OS X, and numerous versions of UNIX.  It is a programming language that is flexible, scalable, and easy to maintain.  It is not difficult to learn Java and you will be able to write your simple code before you reach the last page of this ebook.

James Gosling started the Java programming language project in June, 1991.  Back then it was called Oak and then a bit later, Green.  It ended up with the name Java for no specific reason. In 1995, Sun Microsystems developed and introduced the programming language called Java 1.0.  The latest version of Java that programmers use today is already at version 8.

The Java Advantages

Java is much simpler and easier to learn if you have a basic understanding of OOP (Object Oriented Programming).  An OOP programmer can create or code different modules that don’t need any modification or alteration even when there’s an addition of a new type of object. 

Unlike C, C++, and other programming languages, Java is platform independent or does not interact with the operating system of your computer during compilation.  You don’t compile your Java source file into platform independent codes; you compile it into byte code.  You can carry the compiled Java program via flash drive, unlike the other programming languages that need to use a compiler.

Java has the ability to generate a virus-free and tamper-free system.  Java is also portable.  You can execute the compiled code on different operating systems just as long as they have Java runtime environment.

Many programmers believe that Java is more dynamic than C language and its other variations.  It can effectively and easily adapt to any type of environment.

That will be all for day one, and for your assignment, make sure read more about object oriented programming.  A little more information can help a lot to better understand how Java works.

Chapter 2: It Always Starts with“Hello”

It is clear from the beginning that this book will use as many examples as necessary to teach Java basics.  If you have tried learning a programming language prior to this one then you might have encountered a“Hello”program.  Most programming language tutorials start with a“Hello”program as a sample program.  Let us start with a simple“Hello Java”as our sample program.  You can click the provided link now and start writing your codes or you can do that later–anything is acceptable, whichever is more comfortable to you.

At the end of this tutorial, you will receive different links that you can access in order to install Java into your own computer.  You can still opt to use the online Java IDE, whichever you prefer is fine.

The online Java console has different font colors.  For the purpose of simplification, we will only use one font color in all the examples.

The Basic Java Syntax

We will start with the sample program below and analyze what each line means.  It is imperative to remember that Java is case sensitive.  When you use an identifier and write it using lower cases, make sure that the identifier you use is written in the same manner all throughout the program.   

If you have an identifier called ‘Hello’ that begins with a capital letter H, then don’t write the same identifier using a lower caseh as in‘hello’.  Even though it is obvious that you are referring to the same identifier, the Java program does not recognize it as such.  It will treat‘Hello’as different from‘hello’.

Now look at the first sample program below:

| 1 | public class FirstCoding { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |    /* This is our first program sample.  |  |  |  |
| 4 |     * This should print 'Hello Java' later |  |  |  |
| 5 |     */ |  |  |  |  |  |  |  |  |
| 6 |  |  |  |  |  |  |  |  |
| 7 |     public static void main(String []args) { |  |  |  |
| 8 |        System.out.println("Hello Java"); // prints Hello Java |  |
| 9 |     } |  |  |  |  |  |  |  |  |
| 10 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Also, look at line 7 and 9.  The beginning curly bracket in line 7 to the closing curly bracket in line 9 is called a block of codes.  Anything inside a pair of curly brackets is a block of codes.  

Dissecting the First Line of the Program

The first line should always begin with‘public class’written in lower cases immediately followed by the class name, in this case we use‘FirstCoding’ as the class name. 

When writing the class name, make sure that there is no space in between the previous word and the next word of the name.  Every first letter of the word in a class name must be in upper case.

At the end of the class name is an open or beginning curly bracket, which prompts the computer that the succeeding lines or sentences must be executed.

Explanation for the Second and Sixth Lines

Thesecond and sixth lines don’t contain any codes.  The blank lines create readability.  It is also easier for the assigned programmer or team of programmers to maintain the system or modify the program should a problem suddenly occurs. 

Analyzing the Third, Fourth, and Fifth Lines

The third line is indented and starts with ‘/*’, which marks the start of a multi-line comment.  You use the asterisk (*) if you need to insert a multi-line comment.  After the‘/*’symbol, you write the comment that you would like to put.  The comment serves as reminder about the program.  It can be used to inform the programmer about the task that the program or module needs to accomplish.  

The fourth line is also indented and has asterisk to signify the continuation of the comment in line 3.

The fifth line is indented and has this symbol‘*/’that signifies the end of the multi-line comment.  The computer does not consider the comments as part of the program and won’t bother with it when you run the program.

The Seventh and Ninth Lines

The seventh line is indented and it contains the method name.  Remember to write the method name always in lower case, like this:

public static void main(String []args) {

The ninth line is indented and only contains the closing curly bracket.  The seventh line’s curly bracket at the end of the method name and the closing bracket in the ninth line are indicators that tell the computer to execute the codes within the brackets. 

What the Eighth Line Tells

The eighth line should be indented and it contains the command that instructs the computer to print or write ‘Hello Java’ on your computer screen.  It should appear like this:

System.out.println("Hello Java");

The command starts with an upper case, and the semi colon (;) at the end of the sentence means that there could be other things that the block of codes needs to do.  In our example, the next line (the ninth line) bears the closing bracket, which means the program has reached the end of the block.

The ‘//’ symbol means that the written code after it is a single line comment. 

The ‘.println’ is the command that you use if you want to print something on screen.  It is usually written like this:

println("Hello Java")

It tells the computer to print the characters inside the parentheses.  When printing a string, make sure to enclose it in quotes like you see above.

The Tenth Line

The tenth line contains the closing bracket that signifies the end of the entire program.  It is important to keep in mind that a beginning curly bracket must always have a closing curly bracket.  When you look at the example, the first line’s curly bracket has a corresponding closing curly bracket in the tenth line.  The beginning curly bracket in line 7 has a closing curly bracket in line 9.

Saving your File

If you are using the online Java IDE to write your program, then you don’t need to save your work.  However if you want to keep your work as reference, you need to open a text editor and copy-paste your work in the text editor.

In saving your file, write the class name that you used in your program and just add ‘.java’ at the end of the class name.  The file name of the sample program above should be:

FirstCoding.java

Look at this second sample program:

| 1 | public class SamplePrint { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |     public static void main(String []args) { |  |  |  |
| 4 |        System.out.println("I will now print this sentence."); |  |
| 5 |     } |  |  |  |  |  |  |  |  |
| 6 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

The sample program prints this result:

| I will now print this sentence. |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Indention does not affect how the program runs, it just makes it easier to read.  A well-structured program is easier to maintain and modify.  There’s also a possibility that you might forget what your program does, you can add a comment on your program to serve as your reference or reminder.

Important Notes to Remember

Java is case sensitive, so make sure to write your codes properly.  Most of the time, an error occurs due to incorrect use of upper and lower cases.

Make sure that each beginning bracket has a closing bracket.  If you forget to put one, then expect an error to occur.

The semi-colon (;) must be present at the end of each line that contains a command.

It’s Time for some Practice

Look at the second sample program once more.  For this exercise, you also need to print this sentence:

I will now print another sentence.

Your output should look like this:

| I will now print this sentence. |  |  |  |  |  |
| I will now print another sentence. |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

You will find the answer on the next chapter as well as learn about the data types and variables.  You should practice more to hone your skill.

Chapter 3: Getting to Know the Different Data Types, Variables, and Reserved Words

Before proceeding with today’s lesson, let us first reveal the answer to the practice exercise in the last chapter.  Your answer should look like this:

| 1 | public class SamplePrint { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |   public static void main(String []args) { |  |  |  |
| 4 |      System.out.println("I will now print this sentence."); |  |
| 5 |      System.out.println("I will now print another sentence."); |  |
| 6 |   } |  |  |  |  |  |  |  |  |
| 7 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Did you notice the semi-colon at the end of line 5? If you remove that, you will get an error message.

Now let us discuss today’s lesson, it’s time to learn the different data types that you need to work on when coding your Java program.  This chapter also covers the topic about assigning value to a variable. 

There are reserved words in Java that you should not use as variable name.  You need to know and memorize those reserved words and avoid using them as names of your variables.

The Data Type Integer (int)

An integer can be a positive or negative number, even zero is an integer.  If you need to include a variable that contains integer, then you need to put int before the name of your variable to identify it as an integer. The data type integer or int can only accept the numbers between -2,147,483,648 and 2,147,483,647.

Note:  You don’t need to put the integer in quotes if you want to print it.

Take a look at this program:

| 1 | public class PrintingInteger { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |   public static void main(String []args) { |  |  |  |
| 4 |      System.out.println(15); |  |  |  |  |  |
| 5 |      System.out.println(14); |  |  |  |  |  |
| 6 |      System.out.println(13); |  |  |  |  |  |
| 7 |   } |  |  |  |  |  |  |  |  |
| 8 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

It will print this result:

| 15 |  |  |  |  |  |  |  |  |  |
| 14 |  |  |  |  |  |  |  |  |  |
| 13 |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Any number, within the allowed range of numbers, that you want to place inside the parentheses in‘System.out.println();’ will be printed.  Make sure to follow the correct syntax, like in the given example.

The Data Type Boolean (true or false)

The“boolean" data type has specific values, and it is either true or false; it will not give any other answer.  There’s also no need for you to put anything in quotes because the program automatically assigns true or false (depending on the given condition) as the legit value of boolean expression.

Take a look at this sample program:

| 1 | public class PrintBoolean { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |     public static void main(String  []args) { |  |  |  |
| 4 |        System.out.println(false); |  |  |  |  |
| 5 |     } |  |  |  |  |  |  |  |  |
| 6 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

It prints this result:

| false |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

When you try to replace the value inside the parentheses with‘jabberwocky’, like this:

| 1 | public class PrintBoolean { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |     public static void main(String  []args) { |  |  |  |
| 4 |        System.out.println(jabberwocky); |  |  |  |
| 5 |     } |  |  |  |  |  |  |  |  |
| 6 | } |  |  |  |  |  |  |  |  |

It yields this result:

| /tmp/java_J0wki9/PrintBoolean.java:4: error: cannot find symbol |  |
|        System.out.println(jabberwocky); |  |  |  |  |
|                           ^ |  |  |  |  |  |
|   symbol:   variable jabberwocky |  |  |  |  |  |
|   location: class PrintBoolean |  |  |  |  |  |
| 1 error |  |  |  |  |  |  |  |  |

| Unable to execute program; could not compile! |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Java did not treat the word‘jabberwocky’ as Boolean, and it did not print it because it is a string.  The rule for string is that you need to put it in quotes so the program can recognize it as string and prints it.

The Data Type Character (char) 

The data type character or char represents a single character.  All characters must be enclosed in single quotes (' '), otherwise you will get an error message.  It is a string after all, but you only need to use single quotes.

Take a look at the sample below:

| 1 | public class PrintCharacter { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |     public static void main(String  []args) { |  |  |  |
| 4 |        System.out.println('a'); |  |  |  |  |
| 5 |     } |  |  |  |  |  |  |  |  |
| 6 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

It prints this result:

| a |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Keep in mind that Java’s basic data types are int, boolean, and char.  You will almost always encounter these data types while you learn Java.  Expect to see more of them later.

Variables

Java and other programming languages use variables to store data.  You can store any data type in a variable, and you just need to make sure to specify the data type by following the right syntax in declaring them.

Below is the list of Java reserved words that you need to avoid using as variable name:

| abstract | assert | boolean | break |
| byte | case | catch | char |
| class | const | continue | default |
| do | double | else | enum |
| extends | final | finally | float |
| for | goto | if | implements |
| import | instanceof | int | interface |
| transient | protected | public | return |
| long | private | short | throws |
| switch | native | volatile | while |
| synchronized | new | package | super |
| try | this | static | strictfp |
| void | throw |  |  |

When you use any of the reserved words as a variable name, your program will surely recognize it as something else.  Expect to get an error message when you inadvertently use any of the reserved words as your variable name.

It is also important to remember to write the variable name in lower cases.  Do not capitalize the first letter of your variable name–it is one of Java’s programming rules.  Ignoring the rules can only get you in trouble.  However, you can use an upper case letter within your variable name, like so:

int mostUsefulNum = 7;

If you are using integers, then you need to write int before the name of your variable to identify the data typethat you need to store in your variable‘mostUsefulNum’.  In the above sample, we store‘7’ in the variable. 

Try this practice exercise:

1.  Create a class name of your choice.

2.  Add a multi-line comment that goes: This is my first sample program using everything that I have learned so far.

3.  Make sure that your program is readable;don’t forget to include blank lines.

4.  Assign int data type to myFirstSampleInt.

5.  myFirst SampleInt must be equal to 7.

6.  Assign boolean data type to myFirstSampleBool.

7.  myFirstSampleBoolean must be equal to false.

8.  Assign char data type to myFirstSampleChar.

9.  myFirstSampleChar must be equal to A.

10.  Print myFirstSampleInt.

11.  Print myFirstSampleBoolean.

12.  Print myFirstSampleChar.

Read and analyze the instruction carefully and do exactly what the instruction tells you to do.  This practice exercise is a sort of review about the lessons we’ve covered so far.  After doing this, you can try something on your own.  If there’s an error message, see if you can detect and fix the problem. 

The answer to this practice exercise is on the next page, so don’t cheat.  Create your own program first, and only turn the page if you have finished your code. 

Answering this practice exercise can help you evaluate yourself.  You can always go back to the past lessons if you need to clarify something.

Now, your program should look like this:

| 1 | public class NameofYourChoice { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |   public static void main(String []args) { |  |  |  |
| 4 |      /*This is my first sample program using |  |  |  |
| 5 |      *everything that I have learned so far |  |  |  |
| 6 |      */ |  |  |  |  |  |  |  |
| 7 |      int myFirstSampleInt = 7; |  |  |  |  |  |
| 8 |      boolean myFirstSampleBool = false; |  |  |  |
| 9 |      char myFirstSampleChar  = 'A'; |  |  |  |  |
| 10 |      System.out.println(myFirstSampleInt); |  |  |  |
| 11 |      System.out.println(myFirSampleBool);                             |  |  |  |  |
| 12 |      System.out.println(myFirstSampleChar); |  |  |  |  |
| 13 |    } |  |  |  |  |  |  |  |  |
| 14 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Your output should look like this:

| 7 |  |  |  |  |  |  |  |  |  |
| false |  |  |  |  |  |  |  |  |
| A |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Did you get the same answer? There are times when writing it differently still yields the same result.

Look at this program:

| 1 | public class NameOfYourChoice { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |   public static void main(String []args) { |  |  |  |
| 4 |    /*This is my first sample program using |  |  |  |
| 5 |    *everything that I have learned so far |  |  |  |
| 6 |    */ |  |  |  |  |  |  |  |  |
| 7 |    int myFirstSampleInt; |  |  |  |  |  |
| 8 |    myFirstSampleInt = 7; |  |  |  |  |  |
| 9 |    boolean myFirstSampleBool; |  |  |  |  |
| 10 |    myFirstSampleBoolean = false; |  |  |  |  |
| 11 |    char myFirstSampleChar; |  |  |  |  |  |
| 12 |    myFirstSampleChar  = 'A'; |  |  |  |  |  |
| 13 |    System.out.println(myFirstSampleInt); |  |  |  |
| 14 |    System.out.println(myFirstSampleBool); |  |  |  |  |
| 15 |    System.out.println(myFirstSampleChar); |  |  |  |  |
| 16 | } |  |  |  |  |  |  |  |  |
| 17 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

You will still get the same output even if you did not write the program the same way as the first.  Did you notice the differences between the two programs? The codes are two lines longer in the second program and you need to write the variable names again.

Keep in mind that in programming, the fewer lines that you use in writing your codes, the better.  If you can write the codes or program module within one sheet then do it.  The fewer lines you use, the easier it will be to spot the errors.  It is also easier to maintain the system.

It’s Time to Detect the Errors

| 1 | public class NameofYourChoice { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |   public static void main(String []args) { |  |  |  |
| 4 |      /*This is my first sample program using |  |  |  |
| 5 |      *everything that I have learned so far |  |  |  |
| 6 |      */ |  |  |  |  |  |  |  |
| 7 |      myFirstSampleInt = 7; |  |  |  |  |  |
| 8 |      myFirstSampleBool = false; |  |  |  |
| 9 |      myFirstSampleChar  = A; |  |  |  |  |
| 10 |      System.out.println(myFirstSampleInt); |  |  |  |
| 11 |      System.out.println(myFirstSampleBool);                             |  |  |  |  |
| 12 |      System.out.println(myFirstSampleChar); |  |  |  |  |
| 13 |    } |  |  |  |  |  |  |  |  |
| 14 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Without looking at the previous practice exercise, try detecting the errors in the given program above.  You can try running this program and you to see the error message.

For your assignment, try practicing more during your free time and you will notice that things become easier.

Chapter 4: Useful Pocket Tables and the Different Operators

In using Java as your programming language, it is best if you keep a table for Java numeric operators, comparison operators, and logical operators.  There are also different truth tables.  It is likewise advisable to keep the different tables handy.  For now it may sound a bit too much, but as the days go by you will be able to learn everything like the back of your hand.

The different tables serve as quick references.  It is better if you can memorize them immediately, but even if you have memorized them you still need to keep the tables handy. 

The Numeric Operators

The different programming languages share the same symbols for their numeric operators.  If you already know a programming language, then you can see that the symbols used in Java programming and the programming language that you know are mostly (if not all) the same.  There might be slight differences with the other programming language.      

| NUMERIC OPERATORS |
| Sign | Operand | Example |
| + | Addition | 5 + 9 |
| - | Subtraction | 35 - 24 |
| * | Multiplication | 7*6 |
| / | Division | 168/3 |
| % | Remainder | 15%2 |

It is better if you can quickly memorize all the numeric operators and how to use them properly.  You will almost always need them when you start coding a more complex program. 

For samples of Java program using the mathematical operators, please refer to Chapter 5\.

The Comparison Operators or Relational Operators

It is easier to memorize the table below if you are already familiar with any of the programming languages.  All programming languages practically use the same symbols for their comparison operators.  You will definitely need this when coding a more complex program. 

| COMPARISON OPERATORS |
| less than | <  |
| less than or equal to | <= |
| greater than | >  |
| greater than or equal to | >= |
| equal to | == |
| not equal to | != |

It is easier to use the operators instead of thinking of another way to write the program.  Memorizing the different tables should be your priority.

Boolean Logical Operators

The boolean logical operators are different from the comparison operators.  The  logical operators are commonly used to find the final outcome of the conditional statement or test the arguments.

| BOOLEAN LOGICAL OPERATORS |
| NOT | ! |
| AND | && |
| OR | &#124;&#124; |
| EXCLUSIVE OR | ^ |

The Different Truth Tables

This section is dedicated to the different truth tables that you can use as quick reference.  Keep them handy because you’ll never know when you’ll need them again.

In Chapter 6,you will learn how to use the different Java control statements, and that’s where the truth tables come in handy.  The control statements usually tell the program to execute a certain block of codes as long as the conditional statement above the block remains true.  If the statement returns a false answer, then the program will stop executing the loop for that particular block.  The program will execute the succeeding lines of your code until it encounters a condition that tells it to stop.

Truth Table for AND

| TRUTH TABLE FOR 'AND' |
| A | B | A && B |
| FALSE | FALSE | FALSE |
| FALSE | TRUE | FALSE |
| TRUE | FALSE | FALSE |
| TRUE | TRUE | TRUE |

Explanation on How to Use the AND Table

A and B rows are the condition of each argument in a statement, and the A&&B row shows the final answer in case argument A is true/false and argument B is true/false.

If A is false and B is false then the statement will return false for an answer.  If A is false and B is true, then the statement will return false.  The same explanation goes with the rest of the arguments.

Truth Table for OR

| TRUTH TABLE FOR 'OR' |
| C | D | C &#124;&#124; D |
| FALSE | FALSE | FALSE |
| FALSE | TRUE | TRUE |
| TRUE | FALSE | TRUE |
| TRUE | TRUE | TRUE |

Explanation on How to Use the OR Table

C and D rows are the condition of each argument in a statement, and the CǁD row shows the final answer in case argument C is true/false or argument D is true/false.

If C is false or D is false then the statement will return false for an answer.  If C is false or D is true, then the statement will return true.  The same explanation goes with the rest of the arguments.

Truth Table for NOT

| TRUTH TABLE FOR 'NOT' |
| A | !A |
| FALSE | TRUE |
| TRUE | FALSE |

The NOT table gives the opposite of the argument or expression as its final answer.  If A is false, then !A’s final answer is true.

Truth Table for EXCLUSIVE OR

| TRUTH TABLE FOR 'EXCLUSIVE OR' |
| A | B | A ^ B |
| FALSE | FALSE | FALSE |
| FALSE | TRUE | TRUE |
| TRUE | FALSE | TRUE |
| TRUE | TRUE | FALSE |

The exclusive OR works like the previous OR table, except when both arguments are true, the final answer that exclusive OR gives is false.

It is not easy to memorize all the tables right away.  You need to do it one at a time.  If you have memorized the first table, then you can proceed with the next one. 

For your next assignment, find an easier method of remembering the different truth tables.  You should find it. Hint: remember the instances when the answer is mostly true or mostly false.

Chapter 5: All About the Math

Time sure does fly when you’re having fun, it is now the fifth day of your Java lessons.  This time you need to deal purely with numbers, it’s time to do the Math.  You can add, subtract, multiply, and divide in Java as well as get the remainder.  This lesson is not difficult to understand.  In fact, it is similar to doing your math on paper.  The remainder or modulo may look useless now, but you will appreciate it when the time comes.

Before proceeding to the lessons in this chapter, make sure that you have memorized most of the tables in Chapter 4.  Make sure that you understood the previous lesson before going to the next one.

Addition via Java

When learning how each numeric operator works in Java, it is best to show sample programs using numeric operators.  

Take this sample program:

| 1 | public class AddingProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |        System.out.println(11 + 12); |  |  |  |  |
| 4 |     } |  |  |  |  |  |  |  |  |
| 5 | } |  |  |  |  |  |  |  |  |

You can also write it like this:

| 1 | public class AddingProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 4 |        int e = 11; |  |  |  |  |  |  |
| 5 |        int f = 12; |  |  |  |  |  |  |
| 6 |        System.out.println(e + f); |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |
| 8 |     } |  |  |  |  |  |  |  |  |
| 9 | } |  |  |  |  |  |  |  |  |

Subtraction via Java

It’s better to see the visuals than read the explanation.  We will use the same sample program as pattern in explaining the rest of the mathematical operations.

Look at this sample program for subtraction:

| 1 | public class MinusProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |        System.out.println(21 - 10); |  |  |  |  |
| 4 |     } |  |  |  |  |  |  |  |  |
| 5 | } |  |  |  |  |  |  |  |  |

You can also code it like this:

| 1 | public class MinusProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 4 |        int c = 21; |  |  |  |  |  |  |
| 5 |        int d = 10; |  |  |  |  |  |  |
| 6 |        System.out.println(c - d); |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |
| 8 |     } |  |  |  |  |  |  |  |  |
| 9 | } |  |  |  |  |  |  |  |  |

Multiplication via Java

Look at this sample program for multiplication:

| 1 | public class MultProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |        System.out.println(45 * 2); |  |  |  |  |
| 4 |     } |  |  |  |  |  |  |  |  |
| 5 | } |  |  |  |  |  |  |  |  |

You can also code it like this:

| 1 | public class MultProgSamp { |  |  |  |  |  |
| 2 | public static void main(String  []args) { |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 4 |   int unoNum = 45; |  |  |  |  |  |  |
| 5 |   int secNum = 2; |  |  |  |  |  |  |
| 6 |   System.out.println(unoNum * secNum); |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |
| 8 | } |  |  |  |  |  |  |  |  |
| 9 | } |  |  |  |  |  |  |  |  |

You can use a single character variable name for small programs, and it is more convenient to use.  However, it is advisable to use a variable name that gives a hint regarding the usage of a particular variable if you have a long program.

Division via Java

Look at this sample program for division:

| 1 | public class DivProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |        System.out.println(21 / 3); |  |  |  |  |
| 4 |     } |  |  |  |  |  |  |  |  |
| 5 | } |  |  |  |  |  |  |  |  |

You can also code it like this:

| 1 | public class DivProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 4 |        int m = 21; |  |  |  |  |  |  |
| 5 |        int n = 3; |  |  |  |  |  |  |
| 6 |        System.out.println(m / n); |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |
| 8 |     } |  |  |  |  |  |  |  |  |
| 9 | } |  |  |  |  |  |  |  |  |

The Modulo or Remainder

This is how you get the remainder using Java programming:

| 1 | public class ModuloProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |        System.out.println(27 % 5); |  |  |  |  |
| 4 |     } |  |  |  |  |  |  |  |  |
| 5 | } |  |  |  |  |  |  |  |  |

You can also code it like this:

| 1 | public class ModuloProgSamp { |  |  |  |  |  |
| 2 |     public static void main(String  []args) { |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 4 |        int q = 27; |  |  |  |  |  |  |
| 5 |        int d = 5; |  |  |  |  |  |  |
| 6 |        System.out.println(q % d); |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |
| 8 |     } |  |  |  |  |  |  |  |  |
| 9 | } |  |  |  |  |  |  |  |  |

Using Comparison Operators

Comparison operators, also known as relational operators, compare data types, and always yield a boolean value (true or false) for an answer.  You should be familiar with the different truth tables at this point because you will be using them a lot from here on out.  It is true that you can always go back and look at the table, but going back every now and then takes so much time.  It makes you less productive. 

Whenthere’s a presence of a comparison operator between two data (known as operands), the answer you need to expect from this is always true or false.  Look at the sample statement below:

System.out.println(56<77);

When the program executes it, expect that it will print trueon your computer screen instead of‘56<77’.  Why? It’s because the sentence used a comparison operator that automatically prompts the system to look only for a true or false answer and nothing else.

A Java program is quick to recognize it as something that looks for a boolean answer and the presence of the print command prompts it to print the boolean answer on screen.

The comparison operators equal to (==) and not equal to (!=) are also known as equality operators.  A Java programmer uses the equality operators to test and see the equality of the data.  The programmer has the option to test the equality of data that has int, boolean, or char data type.  You can only get a true or false answer when you use a comparison operator between the data.

If you want to print the ones inside the parentheses, then you need to put them in quotes, and the program will treat them as string.  

To explain further, look at the example below:

| 1 | public class CompareData { |  |  |  |  |  |
| 2 |      public static void main(String []arqs) { |  |  |  |
| 3 |        char testSampChar='r'; |  |  |  |  |  |
| 4 |        int testSampDigit=3; |  |  |  |  |  |
| 5 |        system.out.prntln(testSampChar==testSampDigit); |  |  |
| 6 |      } |  |  |  |  |  |  |  |  |
| 7 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

What do you think will be printed on screen? You are correct if your answer is this one:

| false |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

This is just a simple example.  Expect ones that are more complicated when you begin coding your own program.  There are times when testing the equality among the different data is the only way to go.

Look at this program:

| 1 | public class CompareData { |  |  |  |  |  |
| 2 |      public static void main(String []arqs) { |  |  |  |
| 3 |        char testSampChar='r'; |  |  |  |  |  |
| 4 |        int testSampDigit=3; |  |  |  |  |  |
| 5 |        system.out.prntln(testSampChar!=testSampDigit); |  |  |
| 6 |      } |  |  |  |  |  |  |  |  |
| 7 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

This time, you will be asking the program to test the inequality between testSampChar and testSampDigit.  Since we already know they are not equal, the statement is:

| true |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Try this Practice Exercise

It is time to test what you learned in this chapter.  You might not be aware, but you have been doing simple coding for quite some time now.  This awareness (if you are still not aware of it) should enhance your motivation to go further.  There’s no way for you to reach this chapter if you did not understand anything.  Doing the practice exercises and accomplishing your assignments without fail definitely contribute a lot to your advancement.

You need to practice what you have learned immediately so you won’t forget.  If you keep the habit, then you won’t have trouble except trying to figure out a way of improving the flow of your program.  You need to be careful when writing your codes, and always keep in mind that Java is case sensitive.

If you assign a value to variable greatNum, then make sure to declare it properly and write it correctly all throughout the program.  The program recognizes the declared variable greatNum, but not greatnum.  A slight difference, the manner of writing included, can break your program.

Now try writing the codes for the program below, and make sure to observe proper capitalization and syntax.

1.  Use‘want this program’as the class name of your program.

2.  On the third line, write a single line commentthat goes: Let’s start here.

3.  Create a boolean variable iWantThis and make it true.

4.  Assign‘450 + 60’to the int variable iAlsoWant.

5.  Assign the value of iAlsoWant divided by 3 to int variable isThatIt.

6.  Print the value iWantThis, iAlsoWant, and isThatIt.

Try coding the given sample on your own before looking at the answer.  You can also try practicing more.

Did you get the same answer as the one below?

| 1 | public class WantThisProgram { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |   //let's start here. |  |  |  |  |  |  |
| 4 |     public static void main(String  []args) { |  |  |  |
| 5 |        boolean iWantThis = true; |  |  |  |  |
| 6 |        int iAlsoWant = 450 + 60; |  |  |  |  |
| 7 |        int isThatIt = iAlsoWant / 3; |  |  |  |  |
| 8 |        System.out.println(iWantThis); |  |  |  |  |
| 9 |        System.out.println(iAlsoWant); |  |  |  |  |
| 10 |        System.out.println(isThatIt); |  |  |  |  |
| 11 |     } |  |  |  |  |  |  |  |  |
| 12 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

You will get this output:

| true |  |  |  |  |  |  |  |  |  |
| 510 |  |  |  |  |  |  |  |  |  |
| 170 |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

For your next assignment you only need to practice some more.  Do you think you’re ready for the next lesson?

Chapter 6: Talk About Taking Control

There are control statements in Java programming that can help regulate the program’s order of execution.  The control statements that we will discuss in this ebook are:

1.  The if statement.

2.  The if-else statement.

3.  The switch statement.

4.  The while statement.

5.  The do-while statement.

6.  The for statement.

You can use any of the mentioned control statements depending on what you want your program to do.  These control statements are enough for now since you are only a beginner.  They are also the widely used control statements in Java programming.

Understanding the If Statement

The if statement tells the computer to continue executing the block of codes as long as the expression within the if statement remains true.  If under a certain event that the statement becomes false, then it should prompt the computer to stop executing that particular block of codes.  If there are other if statements somewhere in the program, the computer will continue executing them as long as the condition or expression within the block of codes is true.

There are cases when the execution of the if statement might not continue unless a separate block of codes within the if block is satisfied.  Upon meeting all of the conditions and the expression within the block returns false as reply, then the computer will stop executing that block of codes.

The if statements follow this syntax:

if <conditional expression>

<statement action>

if <conditional expression>

<statement action>

Look at the sample below:

| 1 | public class SampleStatementIf { |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |         public static void main(String[] args) { |  |  |
| 4 |             int a = 40, b = 50; |  |  |  |  |
| 5 |             if (a > b) |  |  |  |  |  |
| 6 |                 System.out.println("a is greater than b"); |
| 7 |             if (a < b) |  |  |  |  |  |
| 8 |                 System.out.println("b is greater than a"); |
| 9 |         } |  |  |  |  |  |  |  |
| 10 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

This will print:

| b is greater than a |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Let us analyze:

In line 4, the variables are declared as int together with their corresponding value.

In line 5, there’s if statement that says, ‘a is greater b’.  Since the statement is false the program prompts the computer to bypass the next statement.  It stops executing that particular if statement because the condition is not true.  Hence, it did not print anything.

In line 7, there’s an if statement that says, ‘b is greater a’.  Since the statement is true the program allows the execution of the next statement, which tells the computer to print ‘b is greater than a’.  Since the condition in if statement this time is true, the computer finally prints the output.

The closing bracket in line 9 informs the computer that the task has been satisfied and there are no more codes to execute.

In case the condition in the first if statement is true, the computer will still execute the next if statement and will do what the codes tell it to do as long as the statement is true.  It will only stop when it finally encountered the corresponding closing bracket.

Dealing with the If-Else (or Nested If) Statement

Just like the if statement, the if-else statement also tells the computer to execute the if-else block of codes only if the condition of the statement is true.  In case the statement is false, then the else statement will be executed provided that the condition in the else statement is true.

The if-else statement follows this syntax:

if <conditional expression> {

<statement action>

} else {

<statement action>

}else {

<statement action>

Take the sample program below:

| 1 | public class IfElseSample { |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |     public static void main(String[] args) { |  |  |
| 4 |             int g = 50, h = 20; |  |  |  |  |
| 5 |             if (g > h) { |  |  |  |  |  |
| 6 |                     System.out.println("g is greater than h"); |
| 7 |             } else if (g < h){ |  |  |  |  |
| 8 |                     System.out.println("h is greater than g"); |
| 9 |             } else { |  |  |  |  |  |
| 10 |                     System.out.println("g is equal to h"); |  |
| 11 |             } |  |  |  |  |  |  |
| 12 |     } |  |  |  |  |  |  |  |
| 13 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

This will print:

| g is greater than h |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Let us analyze:

In line 4, the variables are declared as int together with their corresponding value.

In line 5, there’s an if statement that says, ‘g is greater h’.  Since the statement is true the program prompts the computer to stop executing the rest of the codes.  The nested if or if-else statement stops executing the rest of the codes once the program encounters a condition that proves to be true.  In an if statement, the program will still execute the other lines even if it has already encountered a condition that proves to be true; there’s a sample program below that explains this in a more detailed manner.

In case the first if statement is false, the program will then execute the first else statement only if it’s true.  Otherwise, it will execute the last else statement that has no conditional statement, just an instruction to proceed with printing ‘g is equal to h’.

But, if you have this program:

| 1 | public class IfElseSample { |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |     public static void main(String[] args) { |  |  |
| 4 |             int g = 50, h = 20; |  |  |  |  |
| 5 |             if (g > h) |  |  |  |  |  |
| 6 |                     System.out.println("g is greater than h"); |
| 7 |             if (g > h){ |  |  |  |  |
| 8 |                     System.out.println("h is greater than g"); |
| 9 |             } else { |  |  |  |  |  |
| 10 |                     System.out.println("g is equal to h"); |  |
| 11 |             } |  |  |  |  |  |  |
| 12 |     } |  |  |  |  |  |  |  |
| 13 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

It will print this one:

| g is greater than h |  |  |  |  |  |  |
| h is greater than g |  |  |  |  |  |  |

The second statement is false, but the program doesn’t care what it prints as long as the conditional statement is true.  Also, the program is compelled to execute the next if statement even though the first one is already true.  The reason is because both if statements are independent, unlike in nested if.  It is safe to say that the if-else statements give you more control over your program, especially if there are many available options, but the program must only execute one specific choice.

Try this practice exercise using if-else statement:

1.  The class name of your program is‘MyOwnProg’.

2.  Skip the second line for readability.

3.  Declare the following boolean variables:

     a = true, b = false, c = false

4.  If a is equal to b, then print: a is equal to b.

5\. If b is equal to c, then print: b is equal to c.

6.  If a is equal to c, then print: a is equal to c.

After running the code, you should get this result:

| b is equal to c. |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

If you did not get it, then just this once, here is the answer:

| 1 | public class MyOwnProg { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 | public static void main(String  []args) { |  |  |  |
| 4 |      boolean a = true, b = false, c = false; |  |  |  |
| 5 |      if (a==b) |  |  |  |  |  |  |  |
| 6 |        System.out.println("a is equal to b"); |  |  |  |
| 7 |      if (b==c) |  |  |  |  |  |  |  |
| 8 |        System.out.println("b is equal to c"); |  |  |  |
| 9 |      if (a==c) |  |  |  |  |  |  |  |
| 10 |        System.out.println("a is equal to c"); |  |  |  |
| 11 |     } |  |  |  |  |  |  |  |  |
| 12 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

You can also try doing the if-else statement version of this program if you want.

Before we proceed to the next topic, you can choose to do the next one right away, practice some more of the if and nested if statement, or take a break and have the next one tomorrow.

The Switch

The switch statement is also called the case statement.  The programmer provides different options or choices for the program to execute.  You can say that the switch statement is similar to if-else statement but it looks more organized than the nested if.  The program will only execute the statement that proves to be true.    

You will appreciate the orderliness of the switch statement and it is easier to update and maintain as compared to the nested if statement.  If you need to provide a lot of choices or options, it is advisable to use the switch statement instead of if-else statement.

Below is the syntax for the switch statement:

  switch <non-long integral expression> {
     case 1: 

<statement  1>

break;

     case 2: 

<statement  2>

break;

     case 3: 

<statement  3>

break;

     .

     .

     .

    case n: 

<statement  n>

break;

    default:

<statement>
} // end of switch or case statement

Look at the sample program below:

| 1 | public class SwitchStatementDemo { |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |
| 3 |     //This is a practice program. |  |  |  |
| 4 |     public static void main(String  []args) { |  |  |
| 5 |     boolean a=false, b=false, c=true, d=false; |  |  |
| 6 |     int answer = 0; |  |  |  |  |  |
| 7 |     System.out.println("This is My Sample Output"); |  |
| 8 |     if (a == c) { |  |  |  |  |  |  |
| 9 |     answer = 1; |  |  |  |  |  |
| 10 |     } else if (b == a) { |  |  |  |  |
| 11 |        answer = 2; |  |  |  |  |  |
| 12 |     } else if (c == b){ |  |  |  |  |  |
| 13 |        answer = 3; |  |  |  |  |  |  |
| 14 |     } else if (d == b) { |  |  |  |  |
| 15 |        answer = 4; |  |  |  |  |  |
| 16 |     } |  |  |  |  |  |  |  |
| 17 |        switch (answer) { |  |  |  |  |
| 18 |        case 1: |  |  |  |  |  |  |
| 19 |           System.out.println("a is the same as c"); |  |
| 20 |           break; |  |  |  |  |  |  |
| 21 |        case 2: |  |  |  |  |  |  |
| 22 |           System.out.println("b is the same as a"); |  |
| 23 |           break; |  |  |  |  |  |  |
| 24 |        case 3: |  |  |  |  |  |  |
| 25 |           System.out.println("c is the same as b"); |  |
| 26 |           break; |  |  |  |  |  |
| 27 |        case 4: |  |  |  |  |  |  |
| 28 |           System.out.println("d is the same as b"); |  |
| 29 |           break; |  |  |  |  |  |
| 30 |        default: |  |  |  |  |  |  |
| 31 |           System.out.println("Error encountered, try again"); |
| 32 |        } |  |  |  |  |  |  |
| 33 |    } |  |  |  |  |  |  |  |
| 34 | } |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

Let us analyze the program.  You need to declare the variables that you need to use as well as their assigned values.  There’s also a need for you to initialize the int answer.  As you can see, you need it for your switch statement.  If you won’t initialize it, your program will not run.

The first if statement bears a condition that a is equal to c.  Since the statement is false, the program will no longer execute it.  However, if the answer is true, then 1 will be assigned to the variable answer.

Else ifb is equal to a, then 2 will be assigned to the variable answer.  The same explanation goes to the rest of the nested ifs.

Next is the switch part of the program.  There are different options, and each option corresponds to each value of the variable answer.  In this case, the clear answer is 2 and the program has no choice but to execute the print command under it.  

You can change the assigned boolean value if you want and see the result.  You can also try changing the condition in each if-else statement and see what happens.

You can re-write your codes or modify them, but make sure that the changes are consistent throughout the program, i.e the declared variable name and corresponding data type.  Expect your program to yield a different result or won’t run at all if you failed to change all the things that you need to change.

The While Statement

The while loop compels the program to keep doing the block of codes under it as long as the condition in the while statement remains true.  The program automatically stops doing the instructions once the while statement yields a false response.

You will find the syntax for the while statement or loop below:

while (<loop condition>)
<statement>

<statement>

To illustrate it further, take a look at the sample program:

| 1 | public class WhileLoopDemo { |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |    public static void main(String[] args) { |  |  |
| 4 |       int count = 10; |  |  |  |  |  |
| 5 |      System.out.println("Numbers 10 to 1"); |  |
| 6 |       while (count != 0) { |  |  |  |  |
| 7 |           System.out.println(count--); |  |  |
| 8 |      } |  |  |  |  |  |  |
| 9 |    } |  |  |  |  |  |  |  |
| 10 | } |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

The sample program prints this output:

| Numbers 10 to 1 |  |  |  |  |  |  |
| 10 |  |  |  |  |  |  |  |  |  |
| 9 |  |  |  |  |  |  |  |  |  |
| 8 |  |  |  |  |  |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |  |
| 6 |  |  |  |  |  |  |  |  |  |
| 5 |  |  |  |  |  |  |  |  |  |
| 4 |  |  |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 1 |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

The variable count must be declared as int with an initial value of 10.  In line 5, the heading must be printed.  In line 6, the program must execute the block of codes while the variable count is not yet equal to zero.

It will print the initial number 10 on screen and this symbol ‘--’ means that variable count must decrement by 1.  The next time it goes back to the loop, the variable count will be equal to 9 and it gets printed.  The variable count decreases by 1, and the next time it goes back to the loop its value becomes 8 until the value of the variable count turns 0.

The moment the variable count acquires the value 0, it stops doing the block of code and exits the program.

Try re-writing the sample program, but this time print the numbers 1 to 10 in ascending order.

The Do-While Statement

The do-while loop or statement is just the same as while statement, except the action is given first and the checking of the actual condition comes later.  The presence of while signifies the start of the loop for the program.  The do-while statement allows you to gain more control because it makes sure that the action happens at least once.

Below is the syntax for the do-while statement:

do
<loop body>
while <loop condition>;

Look at this sample program:

| 1 | public class SampleDoWhileStatement { |  |  |  |
| 2 |  |  |  |  |  |  |  |  |
| 3 |    public static void main(String[] args) { |  |  |
| 4 |       int rabbit = 10; |  |  |  |  |  |
| 5 |       System.out.println("Numerals 10 to 1"); |  |  |
| 6 |       do { |  |  |  |  |  |  |
| 7 |              System.out.println(rabbit--); |  |  |
| 8 |       } while (rabbit >= 1); |  |  |  |  |
| 9 |   } |  |  |  |  |  |  |  |
| 10 | } |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

It will give this output:

| Numerals 10 to 1 |  |  |  |  |  |
| 10 |  |  |  |  |  |  |  |  |
| 9 |  |  |  |  |  |  |  |  |
| 8 |  |  |  |  |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |
| 6 |  |  |  |  |  |  |  |  |
| 5 |  |  |  |  |  |  |  |  |
| 4 |  |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |
| 1 |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

The variable rabbit must be declared as int with an initial value of 10.  In line 5, the program prints the heading.  In line 6, the program must print the value of variable rabbit, which is 10, and then decrement it by 1.  Again, the symbol ‘--’ tells the program to decrement the value of the variable by 1.

It then checks if the value of variable rabbit is still greater than or equal to 1.  The value of variable rabbit this time is 9, which is still greater than 1.  It will go back to do the block of codes once more and print 9 on screen.  The program will keep doing the loop until the value of variable rabbit turns 0.

When variable rabbit becomes less than 1, the loop stops and the program ends.

Now, try re-writing the sample program and print the numbers 1 to 10 in ascending order.  Be careful about the numbers that you need to use.

The For Loop

You can use the for loop when you want to repeat executing a block of codes for a certain number of times.  The program will continue executing the block of codes as long as the condition proves to be true.

Instead of writing repetitive statements or codes, you can just write a line or two and the program will keep doing the same thing within a specified number of times.  You also gain more control because the program stops when it has repeated the number of times that it supposed to execute the block of codes.

Below is the syntax for the for loop:

for <initialization>; <loop condition>; <increment/decrement expression)
<loop body>

Here is the sample program:

| 1 | public class SampleForLoop { |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |
| 3 |    public static void main(String[] args) { |  |  |
| 4 |        System.out.println("Output Numbers 10 to 1"); |  |
| 5 |        for (int number = 10; number >= 1; number--) { |  |
| 6 |            System.out.println(number); |  |  |  |
| 7 |        } |  |  |  |  |  |  |
| 8 |    } |  |  |  |  |  |  |  |
| 9 | } |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

The program prints this output:

| Output Numbers 10 to 1 |  |  |  |  |  |
| 10 |  |  |  |  |  |  |  |  |
| 9 |  |  |  |  |  |  |  |  |
| 8 |  |  |  |  |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |
| 6 |  |  |  |  |  |  |  |  |
| 5 |  |  |  |  |  |  |  |  |
| 4 |  |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |
| 1 |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |

At Line 5, you need to initialize your counter ‘number’ to 10, set the condition that the number must be greater than or equal to 1, and decrease number by 1.  The next statement prints the counter number, which is 10.

In the next loop, the counter number has a value of 9, which still proves the condition to be true, so the counter number must decrement by 1 once more.  The next statement will print the number 9 on screen.

The loop will keep doing the block of coded until the counter number is equal to 1.  When the counter number turns less than 1, it will no longer print the value of the counter and the program ends the routine.  It won’t print any number once it has reached its goal.  The for loop sees to it that the program terminates once the specific number of repetition has been satisfied.

You can try re-writing the different codes for practice.  You can add some more to the printed output.  Let your imagination run wild and try to design something out of your own effort and idea.

Java is fun to learn.  Don’t stop here.  Keep improving yourself and discover more wonderful and amazing things that you can do with Java.

Chapter 7: More Practice

You have learned all the Java basics that you need to learn. You can now write your own simple codes.

Practice makes perfect–remember that.  Whenever you have free time, make sure to practice what you have learned.

You can get ideas for programs from everyday tasks or chores that you do and other simple things.  Here are some ideas that you can use to create a program that you might like to try your hands on:

1.  Plotting your budget.

2\. Creating a uniform mathematical formula for the calculations that you routinely do.

3.  Creating a simple puzzle that can help take the boredom away at some days.

4.  Writing a story with different endings depending on the choice that the reader makes.

You can search the net for more sample programs if you want to advance. However, be warned that not all the programs you can find online will not always work.  Although it can actually provide a good training by finding the errors and correcting them.  There’s nothing more fulfilling than being able to make a certain program run even if you did not code it.

Importance of Comments for a Team of Programmers

Comments in a program are actually helpful, especially if you are thinking about working in an IT company or a company that has its own IT experts that maintains their system.   It is usual for companies to have an in-house team that will code or develop a certain part of the system, and another team for maintaining the system.

The team that maintains or upgrades the system will benefit a lot from the comments in the code about the task that a particular block of codes must accomplish.  If there’s a bug in the system, then the maintenance team would be able to point out the problem in a matter of time.

Sometimes, testing the efficiency of the program for a few days is not enough.  There are cases where the problems only begin to occur after several months of running the program.  If you leave comments within the codes, then it would be easier to trace the possible problem and correct it before it gets worse.

The Best Time to Practice and Other Tips

You can practice your newly acquired skill in Java programming whenever you have free time.  It is best to allot a schedule for it to compel yourself to practice at your allotted schedule.

It is important to practice so you can familiarize yourself well with the different commands of Java and make programming more fun and easier.  You can use your skill in different things and you might even learn to develop your own online game when you get better at Java programming.

If you aren’t feeling well, but your schedule states that you should practice your coding, then you should just rest and do nothing.  You need to pour your full attention when coding a program.  It could be so frustrating when your program failed to work. 

Always remember the important things that you need to keep in mind while working with Java.  The most important one being that Java is extremely case sensitive; one . 

You also need to be careful in declaring your variables.  It is important to remain consistent so as to not confuse the program.  When it comes to Java programming, what you regard as a slight difference is actually a huge thing.

If you can’t install Java in your computer, you can still use the online Java coding platform. There is a possibility that you might lose any initial enthusiasm that you have in learning Java when you get frustrated.  You need to keep a high level of enthusiasm in anything you do to make the activity or work more fun and less stressful.

One Last Try

Have you heard of the Fibonacci sequence? Look at this sequence of numbers:

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, .....

You start with 0 followed by 1.  The third number is the sum of the two numbers before it –add 0 and 1, you get 1.  The fourth number is the sum of the two numbers before it –add 1 and 1, you get 2.  The same goes to the rest of the numbers in the series.

Now, let us try to create a program that prints the Fibonacci sequence that should not exceed 90.  Try solving this one on your own before looking at the next page.

Your program should look like this:

| 1 | public class FibonacciSeq { |  |  |  |  |  |
| 2 | //This program prints the Fibonacci sequence < 90 |  |  |
| 3 |   public static void main(String[] args) { |  |  |  |
| 4 |    int loNum = 0; |  |  |  |  |  |  |
| 5 |    int hiNum = 1; |  |  |  |  |  |  |
| 6 |    System.out.println(loNum); |  |  |  |  |  |
| 7 |    while (hiNum < 90) { |  |  |  |  |  |  |
| 8 |       System.out.println(hiNum); |  |  |  |  |
| 9 |       hiNum = loNum + hiNum; //new hiNum |  |  |  |
| 10 |       loNum = hiNum - loNum; //new loNum, the former hiNum |  |
| 11 |  |  |  |  |  |  |  |  |
| 12 |    } |  |  |  |  |  |  |  |  |
| 13 | } |  |  |  |  |  |  |  |  |
| 14 | }  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

It should print this output:

| 0 |  |  |  |  |  |  |  |  |  |
| 1 |  |  |  |  |  |  |  |  |  |
| 1 |  |  |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |  |  |
| 5 |  |  |  |  |  |  |  |  |  |
| 8 |  |  |  |  |  |  |  |  |  |
| 13 |  |  |  |  |  |  |  |  |  |
| 21 |  |  |  |  |  |  |  |  |  |
| 34 |  |  |  |  |  |  |  |  |  |
| 55 |  |  |  |  |  |  |  |  |  |
| 89 |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

Now, try the same program using if, or nested if statements.  You need to generate the same output.  It is quite challenging, but it is also a good training.

This ebook only covers the basics of Java programming.  There are still more advanced commands that you can learn, although most of them are not always necessary. 

The commands that you have learned in this book are the ones that are widely used.  You can still achieve the results that you want to get even if you only use the things that you have learned so far.  The more advanced commands, however, can make the program less complicated and more organized.

Chapter 8: Your Own Java in your Computer

You can install Java in your computer so you can have unlimited access to it even though you’re not online.  However, your computer must fulfill a couple of basic requirements before you can install Java.

System Requirements

It is important that your computer runs on Pentium 200-MHz or better.  It is also necessary for it to have a minimum of 64 MB RAM (Random Access Memory).  These are the most basic system requirements for Java, and as you can see they are quite low, even the most basic computer systems available today have more than enough power.

Your computer needs to have an Operating System (OS) like Windows XP, Windows 7, Windows 8, or Linux.  It is also fine if you are using Mac.  This book has included the set up paths for the different platforms.  Choose Java JDK8 when installing Java in your computer.

It is also recommended to have a Microsoft Notepad or other text editor handy.  It is best to use a text editor when coding your Java program.

Local Environment

If you would like to create a local environment set up for your Java programming, then you need to go to this link: [http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html%20)

You can download the Java programming language for free.  Just choose the version of Java that’s compatible to your operating system.

After making the right Java that’s compatible to your operating system, follow the instructions on how to download Java to your computer system.  Run the “.exe” file that makes installation of Java to your computer possible.  Once the Java programming language is properly installed the next thing that you need to do is set the path that is appropriate to your platform.

Setting the Path for Windows

If you have successfully installed Java to your computer, then you will see something like the one below when you view your directory:

c:\Program Files\java\jdk

You need to point your cursor to ‘My Computer’ and click on it.  You need to open it and once it has been opened it, right-click your mouse and choose ‘Properties’ (it is located at the bottom part of the available choices).

Below the tab that says ‘Advance’, you will see a button with a label ‘Environment variables’ on it.  Click on that button.

The next step you need to make is to modify the ‘Path’ variable.  It should contain the path to Java.exe.  If the current path you see is set to this one:

C:\WINDOWS\SYSTEM32

Then there’s a need for you to change or modify the path into this one:

C:\WINDOWS\SYSTEM32;c:\Program Files\java\jdk\bin

Once you set the right path for Windows OS you can start coding your Java program.

Setting the Path for Linux, UNIX, Solaris, FreeBSD

For Linux, UNIX, Solaris, or FreeBSD, you need to properly set the environment variable PATH to accurately point the location of the installed Java binaries.  You have a shell documentation that serves as your reference in case you encounter some problem or difficulty in setting the path.

If you prefer to use ‘bash’, for example, then you also need to add ‘export PATH=/path/to/java: $PATH'.  It looks like this:

.bashrc: export PATH=/path/to/java:$PATH

Popular Java Editors

The earlier batches of programming language don’t use any text editor, unlike most modern programming languages today.  Java requires the programmers to code or write the Java program using a text editor.  There are several sophisticated Integrated Development Environments or IDEs that you can use for your Java programming. 

IDE is a software application that provides or presents comprehensive facilities for the software development or creation that the programmers will benefit a lot from.  IDE usually have build automation tools, text editor, and debugger.

Below is the list of some of the most popular text editors that a Java programmer can use:

1.  Notepad – if you have a Windows OS in your computer, then you can use the built-in Notepad editor that comes with Windows and code your program.  There’s also TextPad that you can choose if you prefer it.  The beauty of Notepad is that you don’t need to worry if ever you need to copy paste something with picture.  Notepad only allows text and it won’t accept the picture even if you try to paste it.

2.  Netbeans – this is actually one of the Java IDEs that you can download for free from this link [http://www.netbeans.org/index.html](http://www.netbeans.org/index.html).

3.  Eclipse – another recommended Java IDE that is created by the eclipse open-source community.  You can get it from this link [http://www.eclipse.org/](http://www.eclipse.org/). 

You can explore the net for other IDEs that you might like to try or want to keep.  Once you have installed the Java programming language in your computer, you got no more reason to put off your practice session.  Your success depends on your diligence and hunger to learn more about Java.

Conclusion

Thank you again for downloading this book! 

I hope this book was able to help you start your Java programming journey and has kept you motivated till the end of this book.  There are more things that Java can offer and you can advance further if you continue to explore the many wonderful things about Java.

You might want to take advance lessons when you feel like you are ready to do them.  You only need to know the proper syntax for the additional commands.  The right work attitude and views in solving certain problems have been instilled within you, and it should aid you in tackling the problem with positivity.

I hope this book has served its purpose real well and made you understand the Java basics that you need to know to help you code a Java program with ease.

The next step is to continue practicing what you have learned and share the knowledge with your loved ones if needed.  You can take on another programming language if you choose, and discover the many things that you can do.

Finally, if you enjoyed this book, then I’d like to ask you for a favor, would you be kind enough to leave a review for this book on Amazon? It’d be greatly appreciated!

Thank you and good luck!