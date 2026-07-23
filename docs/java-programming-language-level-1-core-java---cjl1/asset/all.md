![](image_rsrc2XA5.jpg)

Core-Java

Level 1

Sunshine

![](image_rsrc2XA6.jpg)

Copyright © 2024 Shine N Rise

All Rights Reserved

With a unique focus on early-stage programming language learning, this book is designed to spark and nurture student's interest in computer learning and engineering.

No part of this book may be reproduced, or stored in a retrieval system, or transmitted in any form or by any means, electronic, mechanical, photocopying, recording, or otherwise, without express written permission of the publisher.

ISBN-13: 9781234567890
ISBN-10: 1477123456

Cover design by: Ecomm N Bizz
Library of Congress Control Number: 2018675309
Printed in the United States of America

Shine N Rise

Shine N Rise, abbreviated as 'SNR', was established in 2023 with the aim of assisting individuals, particularly students, in reaching their career objectives and fulfilling their life purposes through various Skills Development Programs such Career Consultation, Life Motivation, and Personality Development.

![](image_rsrc2XA7.jpg)

Dedication

![](image_rsrc2XA8.jpg)

Preface

The purpose of this book is not just to teach Java programming but to empower students with a skill that can open up new opportunities. By starting early, students can accelerate their growth, becoming capable and independent learners who can explore beyond their traditional education field.

This book has been written with a high focus, keeping in mind that students aged 11 to 17 should be able to understand the fundamentals of Java Programming very easily. To do that concepts have been revived from Level 1, so students should focus on basic concepts and implement them as a program.

Students can try Programs even on mobile devices, and each example has been covered and can be run on mobile devices as well because many of them may not have money to buy a computer or laptop. So there is no excuses left for them not to try Programming.

Each concept and example was explained in a paced manner, allowing enough time for understanding, and an explanation was provided so they could understand it independently. However, individuals can submit their questions for assistance if they need help with any concept.

Acknowledgement

With a unique focus on early-stage programming language learning, this book is designed to spark and nurture students' interest in computer learning and engineering. It's an ideal resource for those keen on Skill-Development programs. The inspiration for this book came from many children, including Gungun, Nidhi, Srishty, Mithi, Golu, and Om, who expressed a desire to learn Java but lacked accessible resources. Their valuable input has helped shape the content, ensuring it addresses common learning gaps and promotes a comprehensive understanding of each concept.

My journey into the world of programming languages began with the insightful books of Yashavant Kanetkar  Sir. His works laid the foundation for my understanding of basic concepts, and for that, I am deeply grateful. His influence has been instrumental in shaping this book, which I've strived to make accessible even to a 6th-grade student by using simple language, providing step-by-step instructions, and including plenty of examples and exercises.

I remember my family, especially my mother, father, and sister, who provided an environment so that I could work on my work. Their unwavering support and belief in my abilities have been a constant source of inspiration, motivating me to create a resource to empower and inspire others in their learning journey.

Contents

[Title Page](#part0001.xhtml)

[Copyright](#part0002.xhtml)

[Shine N Rise](#part0003.xhtml)

[Dedication](#part0004.xhtml)

[Preface](#part0005.xhtml)

[Acknowledgement](#part0006.xhtml)

[1\. Introduction](#part0008.xhtml)

[2\. Java-Beginning](#part0009.xhtml)

[3\. Data-Types in Java](#part0010.xhtml)

[4\. Java Instructions](#part0011.xhtml)

[5\. Java First Program](#part0012.xhtml)

[6\. Decision Control Instructions](#part0013.xhtml)

[7\. Loop Control Instructions](#part0014.xhtml)

[8\. Case Control Instructions](#part0015.xhtml)

[Questions](#part0016.xhtml)

[Feedback](#part0017.xhtml)

[Afterword](#part0018.xhtml)

[About The Author](#part0019.xhtml)

[Books By This Author](#part0020.xhtml)

[Our Brands](#part0021.xhtml)

1\. Introduction

To learn Programming, we must understand fundamental terms first to have better Concept building towards becoming a good Programmer. In this Introduction part, I have focused on those basic terms only that are related to computers and their languages. Each concept will become more clear as we go through the chapters one by one.

1) Language: The words or expressions used to communicate with each other are called Language. Language can be either Verbaly or Non-Verbaly.

In our day-to-day lives, we often speak or express ourselves both ways. If we want to say anything, we choose any language we are comfortable with, whether English, Hindi, or any other language. If we convey any message verbally, that comes under Verbal Language, and sometimes we want to convey the news by giving directions, signals, or written manuals. These types of language are where we convey or express ourselves without speaking or saying anything that comes under Non-Verbal Language.

Language is needed for communication purposes to pass our messages. Now, messages can be anything; it could be simply for passing messages, giving instructions, expressing ourselves, or performing any specific task.

Similarly, there are forms of language that Mobile and Computers understand. That can be called Programming Language. Programming Language is one such language that computers understand. We will see more about this language later in this chapter.

2) Object:  Anything that has a state and properties is called an

Object. Each object has an identity, a behavior, and a state. Objects like Pencil, Guitar, Books, and Car are an examples of an Object as shown in Fig. 1.1.

![](image_rsrc2XA9.jpg)

Other examples of Objects are Watches, Laptops, Computers, Mobiles, etc.

An object occupies space like a car or Book and has state and properties associated with it, like its weight, color, and size, as shown in Fig. 1.2.

![](image_rsrc2XAA.jpg)![](image_rsrc2XAB.jpg)

3) Instructions: Instructions specify how to perform any specific task. Instruction is used to communicate so that any particular task can be performed or completed as specified.

In real life, our Parents instruct us to always wash our hands before eating, and Teachers or Principals instruct us to follow the discipline in the classroom. Similarly, through the instructions, we instruct computers to perform any specific task or operations.

4) Statements: In Java, each statement is an instruction that tells the computer what to do.

We instruct the computer by passing multiple statements in the form that the computer understands.

Following are the Examples of Statements...

int sum = 3 + 4;

int div = 5 / 4 ;

5) Programs: A program is a set of instructions and statements a computer uses to perform a specific function or task.

We will see a lot of Programs starting from Chapter No. 5.

6) Programming Languages: The programming language is a program that the computer understands to perform specific tasks.

There are different types of Programming Languages, as mentioned below...

Java

C

C++

Python

Ruby

In Fig. 1.3, several languages are shown based on their popularity.

![](image_rsrc2XAC.jpg)

7) Programming: The process or activity of writing computer programs is called Programming as shown in Fig. 1.4.

![](image_rsrc2XAD.jpg)

8) Programmers:  Programmers are those who understand and write a Program. Anyone who knows how to write Programs is a programmer as shown in Fig. 1.5.

![](image_rsrc2XAE.jpg)

9) Code: Code is each piece of Programming. Each statement we write takes the form of a Code.

10) Coding: It is the act of writing code. Coding involves translating natural language to computer script, making it much easier and simpler to start coding.

The differences between Coding and Programming are shown in Fig. 1.6.  

![](image_rsrc2XAF.jpg)

11) Coder: Those who write codes and do coding are called Coders.

12) Computer Language: A computer language is a language that we use to communicate with a computer. These are all communication forms humans use and that computers understand through language.

![](image_rsrc2XAG.jpg)

There are different types of Computer Language as  shown in Fig. 1.7.

![](image_rsrc2XAH.jpg)

a) Procedural Programming Language- A procedural language is a computer programming language that consists of functions, instructions, and statements that specify the steps that the computer takes to solve a problem. Examples of Computer procedural languages are C, JAVA, BASIC, etc.  We will learn about function in Chapter No. 5.

b) Functional Programming Language- In computer science, functional programming is a programming paradigm where programs are constructed by applying and composing functions.

Examples of Functional programming languages are Java, Python, JavaScript, etc.

c) Scripting Programming Language- Scripting languages are widely used in web applications.

Examples of Scripting programming languages are bash, Ruby, Node js, Python, and Perl.

d) Logic Programming Language- Logic programming is a logic-based programming paradigm. It means a logic programming language has sentences that follow logic to express facts and rules.

An example of Logic programming language is Prolog.

e) Object-Oriented Programming Language- This type of language is very famous and widely used because it can represent real-world objects and their problems with more clarity.

It is based on the concept of objects, which can contain data and code.

It is known as OOPs because they are built around the concept of objects. Java is an Object-Oriented Programming Language.

We will learn more about Object-Oriented Programming Language in Level 2 (i.e. Intermediate Course).

13) Expressions: Expression is a valid combination of constants, variables, and operators. Expressions perform the work of a Java program by assigning values to variables and help control the execution flow of a program. We will see in more detail about constants, variables, and operators in Chapter No. 2.

Following are the Examples of Expressions...

1/2

6 % 3

pi + (10 * 2)

14) Applications: Since Software is a set of Programs, an application, also called an application program or Software, maybe one specific program or program group built to fulfill any particular requirement.

Application is also known as App or Apps.

Fig. 1.8, shows the different types of Applications.

![](image_rsrc2XAJ.jpg)

Others some of the Examples are as follows -

a) Desktop Applications- Microsoft Word, Office, Acrobat Reader, Media Player, Antivirus, etc.

b) Web Applications- Flipkart, Amazon, Irctc, etc.

c) Mobile Applications-  Game Apps, Facebook, Instagram, etc.

The most handy example of the application is the mobile apps we download from Playstore. If we want to scan our document, we can download the Adobe Scan App from Playstore. If we're going to book a Rail Ticket, we download the IRCTC App, or if we are required to test our program, we can download Compiler App.

Similarly, we have different Applications installed on our computers like MS Word, Powerpoint, Chrome, Firefox, etc. All these come under the application. There are many devices where Java is currently running.

Fig. 1.9 shows the differences between Mobile Applications and Desktop Applications. 

![](image_rsrc2XAK.jpg)

15) Software: Software is a set of computer programs that consists of instructions, data, or programs designed to perform multiple tasks.

The mobile devices and computers we use have software built inside. Mobile devices have software installed like Andriod, Windows, and others. Computer devices having software installed like different versions of Windows like Windows 8, Windows 8.1, Windows 11, and others.

We have also often seen notification like Software updates on our mobile phones. Also, there are versions of Windows that keep releasing.

Fig. 1.10 shows different stages make a Software.  

![](image_rsrc2XAM.jpg)

In the first step, Language, as explained before, can be Java, Python, C, and others. You can choose any language you are comfortable with or have learned and want to build Software on some specific language. Once we decide on the Language, we will move to the next step.     

The second step is to write a program statement specific to the Language we choose. We have to write a statement which the computer can understand.   

The third step is the statement we are writing; it passes an instruction to the computer to act.      

The fourth step is to write logic or an exact code as per our requirements or functionality. Coders are those who code.      

Different codes we write with logic develop a Program in the fifth step. Programmers are those who write Programs.     

So, the sixth step is where the application is structured. We write different Programs as per the functionality we need in an Application.       

Finally, the Software is designed in the seventh step, which can be a single application or consist of different applications.  

16) Device: Devices are objects or systems that have a specific purpose or intention. All software is installed inside the device only. In the device, we run multiple Software or Applications.

With the help of devices, we can use and run various Applications. We use multiple devices daily like Mobile Phones, tablets, Computers, laptops, Power Bank, etc.

Fig. 1.11 shows a Mobile Device which can contain applications built in different languages. 

![](image_rsrc2XAN.jpg)![](image_rsrc2XAP.jpg)

17) Memory:  Memory is the electronic holding place or space where a computer stores data or Programs. It's the place where information is stored for immediate use.

The devices we use, like Mobile, Computers, and Pendrive, have some memory associated with them, like humans have memory in their brains.

Memory is one of the essential functions of a computer because, without it, a computer would not be able to function correctly.

18) Browser: A browser is an application program that provides a way to look at and interact with all the information on the World Wide Web.

It is an application where we can search for our query, google it, and gather information for which we are looking.

Examples of browsers are Google Chrome, Internet Explorer, etc.

◆◆◆

Exercise:-

1) Look at the diagrams below and identify the types of image (Device /

     Application / Memory / Program / Browser / Software /

     Programmer):-

![](image_rsrc2XAR.jpg)

2) Answers the following questions:-

a) What type of language is Java?

b) Which are the most famous programming languages?

c) What are the differences between Web Applications   and Desktop    

     Applications?

d) What is the difference between Programs and Programmers?

e) What is the difference between Programmer and Programming?

3) Activity:-

a) Write in 50 words about the importance of learning Computer

      Skills. (Type only on computer using a computer Keyboard)

b) Find out how much RAM is present in your mobile phone which

      you are using currently.

◆◆◆

2\. Java-Beginning

In this Chapter, we will know about Java's background and its types and some of the features of Java. Also, we will understand the meaning of Constants, Variables and Keywords in Java.

1) What is Java:

Java is one of the Programming Languages.

Java is an Object-Oriented Programming Language.

More than 3 billion devices run Java.

There are many devices where Java is currently used.

2) History of Java:

It was developed at Sun Microsystems (Part of Oracle) in 1995.

It was designed by James Gosling, who is known as the father of Java.

This language uses much of its syntax from C and C++.

It is simpler to use than C++.

Before Java, its name was Oak.

James Gosling and his team changed the name from Oak to Java.

3)  Java Types:

Mainly, four types of applications can be created using Java programming are described below -

a) Standalone Application - Desktop or Window-based applications are Standalone application. Examples are  Calculator, Google Chrome, Notepad, etc.

b) Web Application- An application that runs on the server and creates a dynamic page is called a web application. Examples are Email, Online Forms, etc.

c) Enterprise Application- An application that is distributed in nature. Examples are Banking applications.

d) Mobile Application- An application that is created for mobile devices is called a mobile application. Examples are MX Player, Game App, Udemy, etc.

4)  Features of Java:

Java represents today's world and its problems programmatically.

The features of Java are also known as  Java buzzwords.

The most important features of the Java language are given below and also shown in Fig. 2.1...

a) Simple- Java is very simple, easy to write syntax, and represents real word problems.

b) Object-Oriented- Java is an object-oriented programming language. Everything in Java is an object.

c) Portable- Java is portable because it allows us to run on any platform. It doesn't require any implementation.

d) Platform independent- Java code can be executed on multiple platforms.

For example, Windows, Linux, Sun Solaris, Mac/OS, etc.

e) Secured- Java is renowned for its security. With Java, it is possible to develop systems that are free from viruses.

f) High Performance- Java is faster than traditional interpreted programming languages.

![](image_rsrc2XAS.jpg)

5) Java Version:

Many versions of Java are released, starting from JDK 1.0, JDK 1.1, J2SE 1.2, J2SE 1.3, J2SE 1.4, Java SE 5, Java SE 6, Java SE 7, Java SE 8, and so on.

The first version of Java was released in January 1996.

According to Wikipedia, the current version is Java SE 21, which was released in September 2023.

Java SE 22 is supposed to be released in March 2024.

Considering the simplicity of this course at Level 1, we will cover this in more detail in Level 2 (i.e., Intermediate Course). Also, we will get to know more some basic and complicated terms like JDK, Compiler, Interpreter, and others.

Note: All Examples starting from this chapter and all Programs starting from Chapter 5 in this course have been written in Java SE 7.

6)  Java Constants:

A constant is an entity in programming whose value cannot be changed (i.e., immutable).

A constant is often called a literal.

It is assumed to be positive if no sign precedes an integer constant.  

No commas or blanks are allowed within a constant.

There are several types of constants in Java, such as...

        A) Numeric Constants

        a) Integer Constants

        b) Real Constant

        B) Non-numeric Constants

        a) Character Constants

        b) String Constants

Fig. 2.2 shows the hierarchy for Java Constants.

![](image_rsrc2XAT.jpg)

a) Integer Constants -

An integer constant refers to the sequence of digits.

Without any decimal point, numbers are integers.

They are the primary constant in Java programming.

No commas or blank spaces should be allowed in an integer Constant.

It can be represented with both Positive and Negative signs.

If no sign precedes an integer constant, it is positive by default.

Space is allowed between Numbers and Operators.

It should have at least one digit.

It must not have a decimal point.

We can perform Arithmetic operations like Addition, Multiplication, Subtraction, and Divison between Integer constants.

The modular division also can be performed between Integer Constants.

Note: Starting from now, there will be many examples with an explanation. In  Java Programs, we often use comments to let the readers better understand the functionality or purpose of any piece of code. We will see how to put comments in Java Program in Chapter No. 5 in more detail, but as of now, keep in mind that in the below examples, '//' has been used to give some information for an example used, which is one of the ways to give comments in Java.

Below are some of the valid Integer constants...

        2309           // Integer constant can be a number

        + 211          // Integer constant can be a positive number with a Positive symbol. Space is allowed between Numbers and Operators.

        +88              // Integer constant can be a positive number with a Positive symbol

      - 210             // Integer constant can be a negative number with a Negative symbol

        -21               // Integer constant can be a negative number with a Negative symbol

        0                   // Integer constant can be a 0 as well

Below are some of the Invalid Integer constants...

        8 6                // Error: No space is allowed between a single number of two or more digits

        + 8 8            // Error: No space is allowed between a single number of two or more digits, but space is allowed between an operator and a number

Below are some of the Valid Integer constant Expressions...

        - 88 + 1                 // Arithmetic operations like Addition can be done between Integer Constants

        + 2 * 2                   // Arithmetic operations like

Multiplication can be done between Integer Constants

        -2*2                       // Arithmetic operations like

Multiplication can be done between Integer Constants

        21 - 5                    // Arithmetic operations like

Subtraction can be done between Integer Constants

        14 + (-8)             // Arithmetic operations like Addition can be done between Integer Constants

        (-12)/(-5)          // Arithmetic operations like Division can be done between Integer Constants

        (-12) % (-5)      // Modular division can be done between Integer Constants

Below are some of the Invalid Integer constant Expressions...

        - 8 8 + 1              // Error: No space is allowed between a single number of two or more digits

        * 2 * 2                  // Error: Incorrect use of the Multiplication symbol

        -2*2+                  // Error: Incorrect use of Addition symbol

        2 1 - 5                  // Error: No space is allowed between a single number of two or more digits

        14 + (*8)            // Error: Incorrect use of Multiplication symbol

        (-12+)*(-5)       // Error: Incorrect use of Addition symbol

b) Real Constants -

They are also known as the floating-point constant or float.

They are also written in the floating-notation.

They also can be positive or negative.

It should have a decimal point.

No commas or blank spaces are accepted in a Real Constant.

Space is allowed between Numbers and Operators.

It should have at least one digit, Which can be a positive or negative integer.

The default sign is positive.

To represent Real constants, we use the F or f suffix at the end of the decimal number.

A float constant can be expressed in the fractional form (i.e., 3.14f) or exponential form (i.e., 3.14e2f).

We can perform Arithmetic operations like Addition, Multiplication, Subtraction, and division between Real constants.

Modular division can be done between float constants.

Below are some of the Valid Real Constants...

        9.5f                          // float constant can be a decimal number with the suffix f

        0.1f                          // float constant can be a decimal number with the suffix f

        12345789.2F     // Float constant can be a decimal number with the suffix F

        + 0.1f                      // float constant can be a decimal number with the suffix f with a Positive symbol

         -0.1f                      // float constant can be a decimal number with

the suffix f with a Negative symbol

Below are some of the Invalid Real Constants...

        9.5 f                       // Error: No space is allowed between decimal numbers and the suffix

        F                              // Error: Suffix cannot be used alone without decimal numbers

      2\. 0F                       // Error: Space is not allowed between decimal numbers and digits

        8.0                            // Error: float constant should be represented with the suffix f

Below are some of the Valid Real Constant Expressions...

        + 2.0f - 1.1f             // Arithmetic operations like Subtraction can be done between float constants

        - 2.0f  * 1.1F            // Arithmetic operations like Multiplication can be done between Float constants

        2.1f + 2.3f              // Arithmetic operations like Addition can be done between float constants

       2.1f  % 2.3f            // Modular division can be done between float constants

Below are some of the Invalid Real Constant Expressions...

        + 2.0f - 1.1 f            // Error: No space is allowed between decimal numbers and the suffix

        - 2.0 f  * 1.1F             // Error: No space is allowed between decimal numbers and the suffix

        2.1 + 2.3f                  // Error: Float constant should be represented with the suffix f

        2.0F + 2.3                // Error: float constant should be represented with the suffix f

c) Character Constants -

Character Constants refer to a single alphabet, a single digit, or a single special symbol.

It also represents a Character escape sequence and a Unicode escape sequence.

It is enclosed with a pair of single inverted commas (' ').

Both the inverted commas should point to the left.

These character constants are also known as non-printable constants.

The maximum length of a character constant can be one character.

Character Constants can be one space.

Space is allowed after arithmetic operators.

A Character Constants can also be represented as an Expression.

We can perform Arithmetic operations like Addition, Multiplication, Subtraction, Divison, and others between char constants.

Modular division can be done between char constants.

Fig. 2.3 shows the different Character Escape Sequence. We will learn more about these type of constants in Level 2 (i.e. Intermediate Course).

![](image_rsrc2XAU.jpg)![](image_rsrc2XAV.jpg)

Fig. 2.4 shows the different Unicode Escape Sequence.

![](image_rsrc2XAW.jpg)

Each Number, Symbol, and Alphabet in small or large case letters is associated with some ASCII values and has its Unicode representation.

Right now, looking at Unicode representation is difficult to digest, but don't worry, you will not use these constants much in your Programs and your future Projects. So, you don't have to remember all these representations when required you can check the list or see the complete Unicode list on Wikipedia.

Below are some of the Valid Character Constants...

        ' '                            // char constant can be a space

        'd'                          // char constant can be an alphabet in small case

        'S'                             // char constant can be an alphabet in a capital case

        '6'                          // char constant can be a number of single digits

        '$'                         // char constant can be any symbol

Below are some of the Valid Unicode Representations...

        '\u0000'             // char constant can be a unicode representation

        '\u0001'             // char constant can be a unicode representation

        '\u0010'             // char constant can be a unicode representation

        '\u0100'             // char constant can be a unicode representation

        '\uffff'                 // char constant can be a unicode representation

        '\ufff0'                // char constant can be a unicode representation

        '\uff11'               // char constant can be a unicode representation

Below are some of the Invalid Character Constants...

        ' R '                      // Error: Space is also a char constant, so the char constant length cannot be 3

        ' +'                       // Error: Space is also a char constant, so the char constant length cannot be 2

        ''                             // Error: The length of the char constant should be 1

        '"                           // Error: The length of the char constant should be 1 and should be enclosed between ' '

        ' "                          // Error: char constant should be enclosed between ' '

        '  '                        // Error: Only one space is allowed for a char constant, so the char constant length cannot be 2

        '\0000'            // Error: Not a valid unicode representation

Below are some of the Valid Character Constant Expressions...

        'J' + 'A' + 'V' + 'A'             // Arithmetic operations like Addition can be done between char constants

        'e' * 'd'                                  // Arithmetic operations like Multiplication can be done between char constants

        'c' / 's'                                    // Arithmetic operations like Division can be done between char constants

        'd' * '2'                              // Arithmetic operations like Multiplication can be done between char constants of any type

        '$' + 'e' * 'A' -  ' '             // Arithmetic operations can be done between char constants of any type

        '3' % 'w'                            // Modular division can be done between char constants

        'x' - 'x'                             // Arithmetic operations like Subtraction can be done between char constants

Below are some of the Invalid Character Constant Expressions...

        'c' \ 's'                              // Error: \ is an invalid operator

        'S + d'                             // Error: char constant should be enclosed between ' '

        '6'*' d '                            // Error: Space is also a char constant, so the char constant length cannot be 2

d) String Constants -

It refers to a sequence of any number of characters enclosed in the double quote(" ").

The character can be alphabets, digits, special characters, and blank spaces.

String Constants can contain any number of spaces.

Space is allowed after arithmetic operators.

Operators will not perform any operation if present inside the String quote (" ").

We can perform Arithmetic operations like Addition between String constants.

We cannot perform Arithmetic operations between String constants like Subtraction, Division, and Modular Division.

Below are some of the Valid String Constants...

        " Shine N Rise "           // A string constant can be a word with a space in between

        "211"                            // A String constant can be a number

        " "                                   // A String constant can be a space only

        ""                                    // A String constant can be empty also

        "A"                                 // A String constant can be a single alphabet

        "@#$"                          // A String constant can contain any number of symbols

        "+"                                // A String constant can be a single operator

        "21 + 1"                     // A String constant can be a number with a symbol sign in between

        "21  1"                        // A String constant can be a number with space in between

Below are some of the Invalid String Constants...

        ' Shine '                    // Error: String constant should be enclosed between " "

        "20981'                   // Error: String constant should be enclosed between " "

        " '                                // Error: String constant should be enclosed between " "

Below are some of the Valid String Constant Expressions...

        "J" + "A" + "V" + "A"         // Arithmetic operations like Addition can be done between string constants

        " s " + " a "                             // Arithmetic operations like Addition can be done between string constants

        "" + ""                                      // Arithmetic operations like Addition can be done between string constants

        "2" + "a"                                 // Arithmetic operations like Addition can be done between string constants

        "ss+++" + ""                          // Arithmetic operations like Addition can be done between string constants

        "ss+++" + "+"                       // Arithmetic operations like Addition can be done between string constants

        "ss+++" + "-"                        // Arithmetic operations like Addition can be done between string constants

        "ss+++" + "*"                        // Arithmetic operations like Addition can be done between string constants

        "ss+++" + "/"                        // Arithmetic operations like Addition can be done between string constants

        "ss+++" + "-+/"                  // Arithmetic operations like Addition can be done between string constants

Below are some of the Invalid String Constant Expressions...

        "s" * "a"                      // Error: Arithmetic operations like Multiplication cannot be done between String constants

        "s" - "a"                      // Error: Arithmetic operations like Subtraction cannot be done between String constants

        "s" / "a"                     // Error: Arithmetic operations like Division cannot be done between String constants

        "s" \ "a"                     // Error: \ is an invalid operator

        "s" % "a"                   // Error: Modular division cannot be done between String constants

        '' + ""                           // Error: String constants should be enclosed between " "

        "ss+++" + '\'            // Error: String constants should be enclosed between " "

7)  Java Variables:

A variable name is any combination of alphabets, digits, or underscores(_) or currency characters ($).

All Java components require names. Names used to represent classes, variables, and methods are called identifiers.

We should not create unnecessarily long variable names.

The first character in the variable name must be an alphabet or underscore or currency character ($).

No commas or blanks are allowed within a variable name.

Variable names are case-sensitive.

No whitespace is allowed within the variable name.

Note: From Java SE 7 onwards, we can use any number of underscores between digits in a number to improve the readability of your code.

Below are some of the Valid Variable names...

         age                           // Variable names can start from the alphabet with small letters

        $salary                    // Variable names can begin with a dollar symbol and consist of different combination

        _value                     // Variable names can begin with an underscore symbol and consist of different combination

        __1_value             // Variable names can begin with an underscore symbol and consist of different combination

        $sss                         // Variable names can begin with a dollar symbol and consist of different combination

        Shine                     // Variable names can begin from the alphabet with capital letters

        rise                         // Variable names can begin from the alphabet with small letters

        n                              // Variable names can be a single alphabet with small letter

        I                               // Variable names can be a single alphabet with a capital letter

        II                              // Variable names can consist of two alphabets with a capital letter

        ____i                                       // Variable names can begin with an underscore symbol and consist of different combination

        ____i____i____i              // Variable names can begin with an underscore symbol and consist of different combination

        ____i$____i$____i        // Variable names can begin with an underscore symbol and consist of different combination

        _$                                         // Variable names can begin with an underscore symbol and consist of different combination

Below are some of the Invalid Variable names...

        123abc                             // Error: Variable name cannot start from a number

        -salary                                  // Error: Variable name cannot start from an arithmetic operator

        $s ss                                    // Error: Variable name cannot have space between it

        i i                                         // Error: Variable name cannot have space between it

        ____i ____i ____i           // Error: Variable name cannot have space between it

         _ $                                      // Error: Variable name cannot have space between it

8)  Java Keywords:

There are certain words that Java has defined. These are also known as Reserved Words.

A keyword cannot be used as an identifier.

We use these keywords for writing programs.

![](image_rsrc2XAX.jpg)

The meaning of Java Keywords has already been defined in Java.

Reserved Words as variables, method name, class name, or other identifiers.

There are in total 51 keywords used in Java as also shown in Fig.2.5.

abstract, assert, boolean, break, byte, case, catch, char, class, continue, const, default, do, double, else, enum, extends, exports, final, finally, float, for, goto, if, implements, import, instanceof, int, interface, long, native, new, package, private, protected, public, return, short, static, strictfp, super, switch, synchronized, this, throw, throws, transient, try, void, volatile, while

![](image_rsrc2XAY.jpg)

Out of which const, goto is not in use.

All keywords are Case-Sensitive, i.e., we can only use them in small letters while writing programs.

If words are not keywords, it is called a variable in Java.

true, false, and null are not keywords but literals (i.e., constants) and reserved words cannot be used as identifiers (i.e., Variables).

◆◆◆

Exercise:-

1) Fill in the Blanks:-

a) Java was developed at _______ by _______ in _______.

b) There are _______ types of Java applications.

c) Java is a _______ Programming Language.

d) There are _______ keywords used in Java.

e) The first character in the variable name can be an _______ or

      _______ or _______ or _______.

f) The maximum length of a character constant can be _______ char-

     acter.

g) Real Constants are also known as the _______ constant.

h) The default sign of Integer Constants is _______.

i) Variables are also known as _______, and constants are   also known

    as _______.

j) An Integer constant refers to the sequence of _______.

2) State whether the following statements are true or false:-

a) Java is more difficult to use than C++.

b) Candy Crush Mobile App is an example of a standalone Applica

      tion.

c) There is no involvement of servers in Web Applications.

d) Java is an independent platform.

e) Java is portable but not robust.

f) Java represents a real-world entity.

g) Java is slower than other traditional interpreted programming

      languages.

h) The goto keyword is not used in Java.

i) We can use keywords only in small letters while writing programs.

j) Without any decimal point, numbers are Integers.

k) The meaning of Java Keywords has already been explained to Java

      internally. 

l) Java was developed in the 19th century.

m) Whitespace is allowed within the variable name.

n) Variable names are case-sensitive.

o) String Constants is a sequence of any number of characters

      enclosed in the (' ').

p) Space or Blank is allowed in Character Constants.

q) No commas but blank spaces allowed in a Real Constant.

r) Java Constants are immutable.

s) Real Constants are part of a Non-numeric constant.

3) Which of the following are the incorrect variable names and explain

      why:-

a) SHINE N RISE

b) variable

c) keyword

d) constant

e) identifiers

f) literals

g) i_i

h) &I,

i) Java-Course

j) 2022

k) team's  Go

l) sMILE

m) invalid,

n) why?

o) Question

p) this

q) subtraction

r) Division

s) class

t) _class

u) 0

v) i

w) i0

x) +1

y) -e

z) #education

4) Select all that are the correct Alternatives in the below options:-

a) Which of the following are not the features of the Java language?

      Object-oriented, Platform Dependent, Portable, Low Performance

b) Which of the following are the literals?

      SNR, '+', 00, 007  

c) Which of the following Arithmetic operations cannot be per

     formed between String Constants?

     Addition, Subtraction, Multiplication, Division, Modular Division

d) Which of the following are the characters of Character Constants?

      Alphabet, Symbol, Digit, Operators, Numbers, Unicode

e) Which of the following are not the Reserved Words?

      literals, this, keyword, constant, variable, class, try, switch

f) Which of the following are the correct forms of Real Constants?

     1239.2, 8 8.0, 2.1f % 2.3, 2.1f + 2.3f                

g) Java Variable cannot start with?

     %, &, _, -, ?

h) What is the Unicode values of 'S'?

      U+0072, U+0073, U+0053, U+0054

i) Which of the following are not the correct operators?

     /, \, +, -, ==, :, ;

5) Answers to the following questions:-

a) What do you mean by Reserved Words?

b) Who is known as the father of Java?

c) What do you mean by Java Keywords?

d) What do you mean by Mobile Application?

e) Write some other examples of a Mobile Application.

f) Write some other examples of the Web Application.

g) What is Object-Oriented Programming language?

h) What can be the characters of String Constants?

i) What can be the characters of Character Constants?

j) What are the forms of float constant?

6)  Identify the Invalid Constants from the list below and explain

       why?:-

a) "A" / "Z"                               

b) 65536                                   

c) + (- +211)                              

d) '$' + 'e' * 'A' -  ' ' + ' '            

e) (+-12) % (-+5)                        

f) -0.1Ff                                   

g) -.1f                                                        

h) '                                      

i) 01                                   

j) 2 - 5555                                

k) 'x' - 'S'                               

l) "ShineNRise + CJL1"                    

m) "+ss+++" (+) "-+/"                     

n) - 2f * 1.1111F                         

o) f

7) Activity:-

Search for 20 different Mobile Applications(Apps) that are built using Java in the Real World. 

◆◆◆

3\. Data-Types in Java

In programming, a data type specifies a variable's value and what mathematical, relational, or logical operations can be applied to it without causing an error.

1) Java Data-Types:

A data type in Java represents the size and different values that can be stored in a variable. In other words, a Java data type is a set of values and operations defined on those values.

There are two Data-Types in Java -

A) Primitive data types: The primitive data types include boolean, char, byte, short, int, long, float, and double.

Primitive types are predefined (already defined) in Java.

B) Non-primitive data types: The non-primitive data types

include Classes, Interfaces, and Arrays.

Non-primitive types are created by the programmer and is not defined by Java (except for String).

Non-primitive types can be used to call methods to perform certain operations, while primitive types cannot.

Fig. 3.1 shows the different types of Data-Types.

![](image_rsrc2XAZ.jpg)

2) Java Variable Declaration:

In Java, every variable represents a data type and the quantity of value it can hold.

In Chapter 2, we have seen what a variable is and the rules of variable names.

Here, we will look at how Variable Declaration is made in Java with respect to different data types.

Below is the syntax to declare a Java Variable -

        data_type variable_name = value;

There are specific Rules for Variable Declaration - 

Rule No.1: The first part is a data type we wanted to declare.

Rule No. 2: The second part is the name of the variable of our choice as per the Variable name Rules.

Rule No. 3: Third is the Assignment operator.

Rule No. 4: The fourth part is the value assigned to a variable we declare.

Rule No. 5: The fifth part is the statement terminator, which sets the end of the statement which is ; .

Rule No. 6: Type Declaration, and a Variable is declared in LHS of equalTo operator =.

Rule No. 7: A value to be assigned is kept RHS of equalTo operator =.

Rule No. 8: The assignment always starts from the right to the left.

Rule No. 9: A variable must be declared first before assigning value.

Rule No. 10: The left side after the first statement should be a variable if the statement ends after the type declaration.

We will see how all these rules are used for a Variable declaration in the following examples...

![](image_rsrc2XB0.jpg)

Example 1 -

        int aa=3;

In the Fig. 3.2, this is one of the ways we can declare a variable in Java.

![](image_rsrc2XB1.jpg)

Explanation:

As per Rule No. 1, the first part is the type declaration, which is of int type.

As per Rule No. 2, the name of the variable is aa.

As per Rule No. 3, the Assignment operator = is used.

As per Rule No. 4, the value 3 has been assigned to a variable aa.

As per Rule No. 5, the statement terminator is used to set the end of the statement. We will see more about Statement Terminator in Chapter 5.

As per Rule 6, Type declaration, i.e., int and a variable aa, are declared on the left-hand side of =.

As per Rule No. 7, a value 3, which has to be assigned, is kept on RHS.

As per Rule No. 8, the assignment starts from right to left, a value of 3 in RHS assigned to a variable aa in LHS.

As per Rule No. 9, a variable aa is first declared of type int, and then a value 3 has been assigned.

Rule No. 10 does not apply to this example.

Example 2 -

        int aa;

        aa = 3 ;

This is another representation of a variable declaration, the same as Example No. 1.

Explanation:

As per Rule No. 1, the first part is the type declaration, which is of int type in the first line.

As per Rule No. 2, the variable's name is aa, as declared in the first line.

As per Rule No. 3, the Assignment operator = is used, as shown in the second line.

As per Rule No. 4, the value 3 has been assigned to a variable aa, as shown on the second line.

As per Rule No. 5, the statement terminator is used to set the end of the statement. This has been used in both lines. The statement is complete once we put the statement terminator.

As per Rule No. 6, Type declaration, i.e., int and a variable aa, are declared on the left-hand side of =.

As per Rule No. 7, a value 3, which has to be assigned, is kept on the RHS of the second line.

As per Rule No. 8, the assignment starts from right to left, with a value of 3 in RHS assigned to a variable aa in LHS in the second line.

As per Rule No. 9, a variable aa is first declared of type int in the first line, and then a value 3 has been assigned in the second line.

As per Rule No. 10, the left side is a variable aa in the second line after the type declaration of a variable done in the first line.

Example 3 -

        int aa = 3;

        int bb = aa;

        aa = bb ;

This is another example where the value of aa is updated to 3 again indirectly by the use of another variable.

Explanation:

As per Rule No. 1, the first part is a type declaration, which is of int type, done in the first and second lines for two variables.

As per Rule No. 2, the variable's name is aa, as declared in the first line. Also, another variable, bb, is declared in the second line.

As per Rule No. 3, the Assignment operator = is used in all three statements.

As per Rule No. 4, both variables have been assigned values. In the first statement, a value of 3 is assigned to variable aa; in the second line, the value of aa, which becomes 3 now, is assigned to bb. Again, when the value of bb is 3, the value of bb has been assigned to aa in the third statement. So, aa holds the value 3 again.

As per Rule No. 5, the statement terminator is used to set the end of the statement in all three statements.

As per Rule No. 6, Type declaration, i.e., int and variables aa and bb, are declared on the left-hand side of =.

As per Rule No. 7, a value of 3 in the first statement, a variable aa holding value of 3 in the second statement, and the variable bb in the third statement are kept on the RHS.

As per Rule No. 8, the assignment starts from right to left in all three statements.

As per Rule No. 9, a variable aa and bb are first declared of type int in the first and second lines and then assigned to their RHS.

As per Rule No. 10, the Type declaration of aa in the third statement is already made in the first statement, and in the third statement, the value of bb, which is 3 is assigned to the left.

Example 4 -

        int

        aa

        =

        3

        ;

        int

        bb

        =

        aa

        ;

        aa

        =

        bb

        ;

This is another representation of the same variable declaration in Example No. 3.

Explanation:

If you look closely, you will find that the only difference here with respect to the above example is that each syntax has been written in separate lines.

As per Rule No. 5, we know that the statement terminator is used to set the end of the statement. Java is okay with using too much space in between, but what Java takes care of is the proper syntax used to determine whether each part has been declared correctly, and if not, then it will show an error.

There are more ways to represent data types in Java, which we will discuss in the next section. There are many examples around how we can represent a variable with different data types.

3)  Java Primitive Data Types:

These are the most basic data types available in Java language.

There are different types of Primitive data types...

        A) Integer Data Type

        B) Real Data Type

        C) char Data Type

        D) boolean Data Type       

A)  Integer Types:

Integer types are used to define or represent numbers or integers.

There are four types of Integer Types...

        a) byte

        b) short

        c ) int

        d) long

![](image_rsrc2XB2.jpg)

a) byte -

The range of a byte data type is from -128 to +127.

Its minimum value is -128. 

Its maximum value is 127.

The bytes occupied by a byte is 1.

The default value of a byte is 0.

It can also be used in place of the int data type.

There are no Suffixes used to represent byte type.

Both byte and Byte can be used to represent a byte data type.

Fig. 3.3 also highlights the important points for byte data types.

Below is the simplest syntax to declare a Java  byte  Integer Type Representations...

        byte variable_name = value;

        Byte variable_name = value;

During an assignment, the value of a byte should not exceed the range of the variable.

The byte data type is used to save memory where the memory savings are most required. It saves space because a byte is four times smaller than an integer.

Below are some of the valid byte Integer Type Representations...

        byte b1 = 125 ;               // byte Integer Type can be a number in the range of -128 to +127

       byte b2 = - 128 ;             // byte Integer Type can be a number with a Negative sign and in range of -128 to +127

        byte b3 = + 127;           // byte Integer Type can be a number with a Positive sign and in the range of -128 to +127

        byte b4 = - 127 ;           // byte Integer Type can be a number with a Negative sign and in the range of -128 to +127

        Byte b5 = - 127 ;            // byte can be a Byte and in the range of -128 to +127

More Representation of Valid byte Integer Types...   

        byte b6;                           

        b6= - 127 ;                          // First Declaration of b6 is done, and then the value has been assigned in a separate statement

        byte              

        b7

        =

        -

        127

        ;                                              // Each part of a statement can be in a separate line

Below are some of the Invalid byte Integer Type Representations...

        byte biv1 = 130 ;            // Error: byte Integer Type is outside the range

        byte biv2 =  + 128;       // Error: byte Integer Type is outside the range  

        byte biv3 = 128.00 ;    // Error: byte Integer Type cannot be represented with a decimal point

        byte biv4 = - 130 ;         // Error: byte Integer Type is outside the range

        byte biv5 = 125b ;         // Error: No suffix is applied to the byte integer type

More Representation of  Invalid byte Integer Types...   

        byte biv6 ;

        bb=  + 128;                               // Error: According to Rule No. 9, a variable bb must be declared first before assigning value to it

        byte biv7 =  +

        *126;                                           // Error: Incorrect use of operator

More Representation of Valid byte Integer Type Expressions...

        byte bve1 = - 125 + 1 ;            // Arithmetic operations like Addition can be done between byte Integer Type

        byte bve2 = - 128 * 1 ;             // Arithmetic operations like Multiplication can be done between byte Integer Type

        byte bve3 = + 127 - 1 ;            // Arithmetic operations like Subtraction can be done between byte Integer Type

        byte bve4 = - 127 % 5 ;          // Modular division can be done between byte Integer Type

        byte bve5 = - 127 / 5 ;            // Arithmetic operations like Division can be done between byte Integer Type

        byte bve6 = - 130 % 5 ;          // Modular Division can be done between byte Integer Type

Below are some of the Invalid byte Integer Type Expressions...

        byte bve7;                                              

        bve7= - 127 % 5 ;                    // According to Rule No. 9, a variable bve7 must be declared  first before assigning value to it

        byte                                                     

        bve8

        =

        -

        127

        5

        ;                                                       // We can also split each part into a separate line to represent a statement

Below are some of the Invalid byte Integer Type Expressions...

        byte bive1 = - 1 25 + 1 ;          // Error: No space is allowed between a single number of two or more digits

        byte bive2 = - 128 * 2 ;            // Error: The result of the expression is outside the range of -128 to +127

        byte bive3 = - 130 -  2 ;           // Error: The result of the expression is outside the range of -128 to +127

        byte bive4 = - 130 \ 5 ;          // Error: \ is an Invalid operator

More Representation of Invalid byte Integer Type Expressions...

        byte bive5;             

        = - 128 * 2 ;                                             // Error: According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration.

        byte bive6

        bi=- 128 * 2 ;   ;                                    // Error: According to Rule No. 9, a variable bi must be declared  first before assigning value to it

b) short -

The range of short data types is from -32768 to +32767.

Its minimum value is -32768. 

Its maximum value is +32767.

Bytes occupied by short are 2.

The default value of short is 0.

There are no Suffixes used to represent short type.

Both short and Short can be used to represent a short data type.

Fig. 3.3 also highlights the essential points for short data types.

Below is the simplest syntax to declare a Java  short  Integer Type Representations...

        short variable_name = value;

        Short variable_name = value;

During an assignment, the value of the short being assigned should not exceed the range of the variable.

The short data type can also save memory, like byte data. A short data type is two times smaller than an integer.

Below are some of the Valid short Integer Type Representations...

        short s1 = 31800 ;            // short Integer Type can be a number in the range of -32768 to +32767

        short s2 = - 327 ;               // short Integer Type can be a number with a Negative sign and in the range of -32768 to +32767

        short s3 = 1 ;                       // short Integer Type can be a number in the range of -32768 to +32767

        short s4 = + 32767 ;        // short Integer Type can be a number with a Positive sign and in the range of -32768 to +32767

More Representation of  Valid short Integer Types...

        Short            

        s6

       =

       +

       32767

       ;                                                    // Each part can be in a separate line to represent a statement

        Short s7 ;

        s7= 32767 ;          ;                 // First, Declaration of s7 is made, and then the value has been assigned in a separate statement

Below are some of the Invalid short Integer Types...              

        short siv1 = - 32768.00 ;            // Error: short data type cannot be represented by a decimal digit

        short siv2 = + 32767.00 ;           // Error: short data type cannot be represented by a decimal digit

        short siv3 = - 40000 ;                   // Error: short data type is out of range

        short siv4 = 40000 ;                      // Error: short data type is out of range

        Short siv5 = 327s ;                         // Error: No suffix is applied to the short integer type

More Representation of Invalid short Integer Types...        

        short siv6;     

        = - 32768.00 ;                                 // Error: Left-side assignment should be a variable if the statement ends after the type declaration

        short siv7;

        si=- 32768.00 ;                           // Error: According to Rule No. 9, a variable si must be declared first before assigning value to it

Below are some of the Valid short Integer Type Expressions...                     

        short sve1 = - 32768 + 1 ;                // Arithmetic operations like Addition can be done between short

        short sve2 = - 32767 * 1 ;                // Arithmetic operations like Multiplication can be done between short

        short sve3 = 32767 - 1 ;                    // Arithmetic operations like Subtraction can be done between short

        short sve4 = - 32767 % 5 ;              // Modular division can be done between short

        short sve5 = - 32767 / 5 ;                 // Arithmetic operations like Division can be done between short

        short sve6 = + 32770 % 1 ;             // Modular division can be done between short

More Representation of Valid short Integer Type Expressions...

        short sve7;

        sve7= + 32770 % 1 ;                        // First Declaration of sve7 is made, and then the result of an expression is assigned to sve7 as a value

        short sve8 = + 32770 % 1      

                                  -3

                                 +5;                                    // Each part of an expression can be in a separate line to represent a statement

Below are some of the Invalid short Integer Type Expressions...

        short sive1 = + 32770 - 1 ;             // Error: short data type is out of range

        short sive2 = + 32770 * 1 ;             // Error: short data type is out of range

        short sive3 = + 32770 - 9 + 9 ;     // Error: short data type is out of range

        Short sive4 = + 32770 \ 1 ;            // Error: \ is an invalid operator

More Representation of Invalid short Integer Type Expressions...                 

        short sive5 = + 32770 - 9 +         

                            + 9 ;                                       // Error: Incorrect use of operator          

        short sive6;                        

        sive = + 32770 - 9 + 9 ;                    // Error: According to Rule No. 9, a variable sive must be declared first before assigning value to it

c) int -

Out of the different types of integers, int is one of the most commonly used.

The range of an int data type is from -2147483648 to +2147483647.

Its minimum value is -2147483648. 

Its maximum value is +2147483647.

Bytes occupied by int is 4.

The default value of int is 0.

By default, without a decimal point, it is treated as an int.

There are no Suffixes used to represent int type.

Both int and Integer can be used to represent a short data type.

Fig. 3.3 also highlights the essential points for int data types.

Below is the simplest syntax to declare a Java int Integer Type Representations...

        int variable_name = value;

        Integer variable_name = value;

The int data type is generally used for integral values as a default data type.

During an assignment, the value of int being assigned should not exceed the range of the variable.

Below are some of the Valid int Integer Type Representations...

        int i1 = 2309 ;                       // int Integer Type can be a number in the range of -2147483648 to +2147483647

        int i2 = + 211 ;                    // int Integer Type can be a number with a Positive sign and in the range of -2147483648 to +2147483647

        int i3 = +88 ;                        // int Integer Type can be a number with a Positive sign and in the range of -2147483648 to +2147483647

        Integer i4 = - 210 ;             // int Integer Type can be a number with a Negative sign and in the range of -2147483648 to +2147483647

        int i5= -21 ;                           // int Integer Type can be a number with a Negative sign and in the range of -2147483648 to +2147483647

        int i6 = 2147483645 ;    // int Integer Type can be a number with a Positive sign and in the range of -2147483648 to +2147483647

More Representation of Valid int Integer Types...

        int                                                            

        i7

        =

        2147483645

        ;                                                             // Each part of a statement can be in a separate line

        int i8                                                       

                        = 2147483645 ;              // Statement can be in a separate line

        int i9 = 2147483645                   

                                                ;                         // Statement can be in a separate line

        int i10;                                                  

        i10=2147483645 ;                                // First Declaration of i10 is made, and then the value has been assigned in a separate statement

Below are some of the Invalid int Integer Types...

        int iiv1 = - 2147483650;       // Error: int Integer Type is outside the range

        Int iiv2 = 2147483645 ;         // Error:  Int is not a valid data type

        integer iiv3 = + 21 ;                    // Error:  integer is not a valid data type

More Representation of Invalid int Integer Types...

        int iv4;                                                 

        iv4= - 2147483650;                            // Error: int Integer Type is outside the range

        int iv5 = - 2147483650;               

        iv5 = 9;                                                     // Error: int Integer Type is outside the range

Below are some of the Valid int Integer Type Expressions...

        int ie1 = - 88 + 1 ;                            // Arithmetic operations like Addition can be done between Integers  

        int ie2 =  + 2 * 2 ;                                  // Arithmetic operations like Multiplication can be done between Integers

        int ie3 =  -2*2 ;                                      // Arithmetic operations like Multiplication can be done between Integers

        int ie4 = 21 - 5 ;                               // Arithmetic operations like Subtraction can be done between Integers

        Integer ie5 =  14 + (-8);                // Arithmetic operations like Addition can be done between Integers

        int ie6 = (-12)/(-5) ;                      // Arithmetic operations like Division can be done between Integers

        int ie7 = - 2147483645 * 1 ;      // Arithmetic operations like Multiplication can be done between Integers

        int ie8 = (-12) % (-5) ;                 // Modular division can be done between Integers

More Representation of Valid int Integer Types Expressions...

        int ie9 =              

                             (-12) % (-5) ;                // Statement can be in a separate line

        int ie10 =                                          

                          (-12)

                          %

                            (-5) ;                               // Statement can be in a separate line

        int

        ie11                                                      

        =

        (

        12

        )

        %

        (

        -

        5

        ) ;                                 // Each part of a statement can be in a separate line

Below are some of the Invalid int Integer Types Expressions...

        int ive1 = 2147483649 + 1 ;          // Error: int Integer Type is outside the range

        int ive2 = - 2147483649 - 1 ;         // Error: int Integer Type is outside the range

More Representation of Invalid Integer Types Expressions...

        Integer ive3;   

        =  14 + (-8) ;                                       // Error: According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration

        Integer ive4;                                      

        14 + (-8) ;                                            // Error: According to Rule No. 3, Assignment operator is not used and According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration

        Integer ive5;  14 + (-8) ;               // Error: According to Rule No. 3, Assignment operator is not used and According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration

        Integer;

        ive6;

        ivee=

        14 + (-8) ;                                            // Error: According to Rule No. 9, a variable ivee must be declared first before assigning value to it

d) long -

A long data type range is from -9,223,372,036,854,775,808(-2^63) to 9,223,372,036,854,775,807(2^63 -1).

Its minimum value is -9,223,372,036,854,775,808 (-2^63). 

Its maximum value is 9,223,372,036,854,775,807 (2^63 -1).

Bytes occupied by long is 8.

The default value of a long is 0.

The long data type is used when you need a more range of values than those provided by int.

Both long and Long can be used to represent a short data type.

If we wish to treat an integer as a long integer, we simply have to add a suffix L or l at the end of it.

Fig. 3.3 also highlights the essential points for long data types.

Below is the simplest syntax to declare a Java long Integer Type Representations...

        long variable_name = value;

        long variable_name = valuel;

        long variable_name = valueL;

        Long variable_name = valuel;

        Long variable_name = valueL;

During an assignment, the value of long being assigned should not exceed the range of the variable.

We use the Suffix L or l at the end to represent long type.

The suffix l or L is not required if the integer range belongs to the int type and the data type used is long.

If we have used Long type, the suffix l or L is required to use.

Below are some of the Valid long Integer Types...

        long l1 = 2147483645 ;                // long Integer Type can be a number and in range

        long l2 = - 2 ;                                        // long Integer Type can be a number with a Negative sign

        long l3 = + 211 ;                                 // long Integer Type can be a number with a Positive sign

        Long l4 = 2147483645l ;              // Long can be used in place of long 

        long l5=  - 2L ;                                   // long can be used in place of long with the suffix L

        long l6 = 2147483645l;              // long Integer Type can be a number and in range

        Long l7 = - 2l ;                                   // Long can be used in place of long with the suffix l

        long l8 = + 21l ;                                   // long can be used with the suffix l

        long l9 = 2147483645l;                // long can be used with the suffix l

        Long l10 = - 2L;                                // Long can be used in place of long with the suffix L

More Representation of Valid long Integer Types...

        long                                                 

        l11               

        =

        -

        2L

        ;                                                          // Each part of a statement can be in a separate line

        long l12                                       

        = - 2l ;                                             // Statement can be in a separate line

        long l13;                                       

        l13= - 2l ;                                      // Statement can be in a separate line

Below are some of the Invalid long Integer Types...                

        Long liv1 = 2147483645 ;                // Error: No suffix used with Long  

        Long liv2 = - 2 ;                                        // Error: No suffix used with Long

        Long liv3 = + 21 ;                                           // Error: Suffix L should be used with Long

        long liv4 = 2147483645455555 ;       // Error: long Integer Type is outside the range

More Representation of Invalid long Integer Types...

        Long liv5;                                      

        = 21 ;                                    // Error: According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration

        Long liv6;                                       

        liv7=  21 ;                          // Error: According to Rule No. 9, a variable liv7 must be declared first before assigning value to it    

Below are some of the Valid long Integer Type Expressions...

        long le1 = - 88 + 1 ;                                 // Arithmetic operations like Addition can be done between long  

        long le2 =  + 2 * 2 ;                                  // Arithmetic operations like Multiplication can be done between long

        long le3 =  -2*2 ;                                      // Arithmetic operations like Multiplication can be done between long

        Long le4 = 21l - 5l ;                                // Arithmetic operations like Subtraction can be done between long

        Long le5 =  14l + (-8) ;                         // Arithmetic operations like Addition can be done between long

        Long le6 = (-12l)/(-5) ;                       // Arithmetic operations like Division can be done between long

        long le7 = - 2147483645 * 1 ;         // Arithmetic operations like Multiplication can be done between long

        Long le8 = (-12l) % (-5l) ;                 // Modular division can be done between long

More Representation of Valid long Integer Type Expressions...

        Long ie9 =                                          

                               (-12l)

                                      %

                                                (-5l) ;                   // Statement can be in a separate line

        Long                                                     

        ie10

        =

        (

        -

        12l

        )

        %

        (

        -

        5l

        )

        ;                                     // Each part of a statement can be in a separate line

Below are some of the Invalid long Integer Type Expressions...   

        Long lve1 = - 88 + 1 ;           // Error: No suffix used

        Long lve2 = 2 * 2 ;                 // Error: No suffix used

        int lve3 = 14L + (8L) ;          // Error: Cannot convert from long to int

More Representation of Invalid long Integer Type Expressions... 

        long lve4                                       

        =

        14

        L                

        +

        (

        8L

        )

        ;                                                             // Error: Suffix cannot be used separately

        long;                                                

        lve5 = 14L + (8L) ;                 // Error: long cannot be used alone

B) Real Types:

Real numbers can be represented as float and double.

The difference between them is the number of bytes occupied by each, their ranges, and their precision.

Real Types are used to represent decimal numbers.

There are two types of Real Types...

        a) float

        b) double

![](image_rsrc2XB3.jpg)

a) float -

The range of a float data type is from 1.40239846e-45f to 3.40282347e+38f.

Its minimum value is 1.40239846e-45f.

Its maximum value is 3.40282347e+38f.

Bytes occupied by double is 4.

The default value of float is 0.0, 0.0f, or 0.0F.

Both float and Float can be used to represent a float data type.

float type cannot represent a decimal value without a suffix f or F.

Fig. 3.4 also highlights the essential points for float data types.

Below is the simplest syntax to declare a Java float Integer Type Representations...

        float variable_name = value;

        float variable_name = valuef;

        float variable_name = valueF;

        Float variable_name = valuef;

        Float variable_name = valueF;

During an assignment, the value of float being assigned should not exceed the range of the variable.

If the value of a float/double is too small or too large, then instead of using the standard notation, it is easier to specify the number in exponential form.

Using a float (instead of double) is recommended if you need to save memory.

Below are some of the Valid float Real Type Representations...

        float f1 = 9.5f ;                                     // float can be used to represent float type with suffix f and should be in the range                         

        Float f2 = 12345789.2f ;                // Float can be used in place of float with suffix f

        Float f3 = 12345789.2F ;               // Float can be used in place of float with suffix F

        float f4 = 8 ;                                           // float can also be represented without suffix f or F

More Representation of Valid float Integer Types...

        float                                               

        f5                 

        =

        -

        2f

        ;                                                   // Each part of a statement can be in a separate line

         float f6                                         

        = - 2f ;                                       // Statement can be in a separate line

        Float f7;                                        

        f7= - 2F ;                                // Statement can be in a separate line

Below are some of the Invalid float Real Types Expressions...

        float fiv1 = 8.2 ;                                        // float type cannot represent a decimal value without a suffix f or F

        float fiv2 = 9.0 ;                                        // float type cannot represent a decimal value without a suffix f or F

        Float fiv3 = 12345789.2 F ;               // No space is allowed between a decimal number and a suffix

        float fiv4 = 12345789.2 f ;                 // No space is allowed between a decimal number and a suffix

More Representation of Invalid float Real Types...

        Float fiv5;                                           

        = 21f ;                                                // Error: According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration

        float fiv6;                                            

        fiv6=  21 ;                                       // Error: According to Rule No. 9, a variable fiv6 must be declared first before assigning value to it

Below are some of the Valid float Real Type Expressions...  

        float fe1 = 8.2F * 1.2f ;                     // Arithmetic operations like Multiplication can be done between float  

        float fe2 = 9.0f + 8.0f ;                      // Arithmetic operations like Addition can be done between float

        float fe3 = 9.5f + 8.0f ;                      // Arithmetic operations like Addition can be done between float

        Float fe4 = 1.2f / 1F;                          // Arithmetic operations like Division can be done between float

        Float fe5 = 1.2f / 1.0f;                      // Arithmetic operations like Division can be done between float

        float fe6 = 9 - 8 ;                                   // Arithmetic operations like Subtraction can be done between float

        float fe7 = 9f + 8f ;                              // Arithmetic operations like Addition can be done between float

        float fe8 = 9f % 8f ;                            // Modular division can be done between float

More Representation of Valid float Real Type Expressions...

        Float fe9 =                                         

                                (-12F)

                                               %

                                                       (-5f) ;        // Statement can be in a separate line

        float                                                      

        fe10

        =

        (

        -

        12F

        )

        %

        (

        -

        5F

        )

        ;                                     // Each part of a statement can be in a separate line

Below are some of the Invalid float Real Types Expressions...

        float five1 = 8.2 * 1.2f ;                   // Cannot convert double to float

        float five2 = 9.0 + 8.0 ;                   // Cannot convert double to float

        Float five3 = 1.2d / 1.0f;               // Cannot convert double to float

        float five4 = 9.0 - 8f ;                       // Cannot convert double to float

        float five5 = 9.0F + 8.0 ;                // Cannot convert double to float

More Representation of Invalid Real Type Expressions...

        float five6                                            

        =

        14

        F                            

        +

        (

        8f

        )

        ;                                                            // Error: Suffix cannot be used separately

        Float;                                                    

        five7 = 14F + (8f) ;                // Error: Float should not be used alone

b) double -

The range of a double data type is from 4.9E-324 to 1.7976931348623157E308.

Its minimum value is 4.9E-324.

Its maximum value is 1.7976931348623157E308.

Bytes occupied by double is 8.

The default value of double is 0.0 or 0.0d or 0.0D.

The double data type is generally used for decimal values like float.

A number without a decimal point is treated as a double by default.

Both double and Double can be used to represent a double data type.

double type can represent a decimal value without a suffix d or D.

If we wish to treat it as a float, we need to add a suffix F or f at the end of it to make it a float.

Fig. 3.4 also highlights the essential points for double data types.

Below is the simplest syntax to declare a Java double Integer Type Representations...

        double variable_name = value;

        double variable_name = valued;

        double variable_name = valueD;

        Double variable_name = valued;

        Double variable_name = valueD;

During an assignment, the value of double being assigned should not exceed the range of the variable.

Below are some of the Valid double Real Type Representations...  

        double d1 = 8.2 ;                             // double can be used to represent double type without any suffix d and should be in the range

        double d2 = 9.0 ;                            // double can be used to represent double type without any suffix d and should be in the range

         double d3 = 9.5f ;                          // double can also be used to represent float type with suffix f but should be in the range

        Double d4 = 1.2 ;                           // Double can be a used in place of double without any Suffix

        double d5 = 12345789.201245789 ;          // double can be used to represent double type without any suffix d and should be in the range

        Double d6 = 12345789.2d ;                              // Double can be used to represent double type with a suffix d

        Double d7 = 12345789.2D ;                             // Double can be used to represent double type with a suffix D

        double d8 = 8 ;                                                         // double can be used to represent double type without any decimal number

More Representation of double Real Types...

        double                                                              

        d9

        =

        12345789.201245789 ;             // Statement can be in a separate line

        Double d10                                                   

        = 12345789.2D ;                             // Statement can be in a separate line

Below are some of the Invalid double Real Type Representations...

        Double div1 = 12345789.2 D ;            // No space is allowed between an integer and a suffix

        double div2 = 12345789.2 d ;             // No space is allowed between an integer and a suffix

More Representation of Invalid double Real Types...

        Double div3;                                        

        = 12345789.2D ;                           // Error: According to Rule No. 10, the left side after the first statement should be a variable if the statement ends after the type declaration

        double div4;                                           

        div4=  12345789.2d ;                 // Error: According to Rule No. 9, a variable div4 must be declared first before assigning value to it    

Below are some of the Valid double Real Types Expressions...

        double de1 = 8.2 * 1.2d ;             // Arithmetic operations like Multiplication can be done between double

        double de2 = 9.0 + 8.0 ;              // Arithmetic operations like Addition can be done between double

        double de3 = 9.5d + 8.0 ;            // Arithmetic operations like Addition can be done between double

        Double de4 = 1.2 / 1;                     // Arithmetic operations like Division can be done between double

        Double de5 = 1.2d / 1.0;             // Arithmetic operations like Division can be done between double

        double de6 = 9 - 8 ;                        // Arithmetic operations like Subtraction can be done between double

        double de7 = 9d + 8d ;                 // Arithmetic operations like Addition can be done between double

        double de8 = 8.2 * 1.2f ;               // Arithmetic operations like Multiplication can be done between double and float

        double de9 = 9.0 + 8.0 ;                // Arithmetic operations like Addition can be done between double

        double de10 = 1.2d / 1.0f;         // Arithmetic operations like Division can be done between double and float

        Double de11 = 9.0 - 8f ;               // Arithmetic operations like Subtraction can be done between double and float

        Double de12 = 9.0F + 8.0 ;         // Arithmetic operations like Addition can be done between double and float

        Double de13 = 9.0 % 8.0 ;        // Modular Division can be done between double

        Double de14 = 9.0F % 8.0 ;     // Modular Division can be done between double and float

        Double de15 = 1.2d / 1.0f;      // Can covert from float to double

More Representation of Valid double Real Types Expressions...

        Double                              

        de16

        =                      

        9.0F

        %

        8.0

        ;                                     // Each part of a statement can be in a separate line

        double                             

        de17 =                       

        9.0 % 8.0 ;          // Statement can be in a separate line

Below are some of the Invalid double Real Types Expressions...

        double dive1 = 8.2d * 1.2l ;           // Invalid syntax l

        Double dive2 = 9.0D + 8.0l ;        // Invalid syntax l

More Representation of Invalid double Real Types Expressions...

        double                                           

        dive3

        =

        8.2

        d * 1.2d;                                        // Error: Suffix cannot be used separately           

        double       ;                                       

        4

        =

        8.2d * 1.2d;                               // Error: double should not be used alone

C) char Data Types:

Character Constants refer to a single alphabet, digit, or special symbol.  

It is enclosed with single inverted commas (' ').  

The char data type is used to store characters.  

A char data type represents a character in Unicode format.  

The Unicode character encoding standard is a fixed length.

Unicode representation can take a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535).

A char data type also represents a number of ranges 0 to 65535 without being enclosed with a pair of single inverted commas (' ').

The bytes occupied by char is 2.

The default value of char is  \u0000.

char must be used with small letters because it is a keyword.

Below is the simplest syntax to declare a Java char Integer Type Representations...

        char variable_name = value;

Fig. 3.5 also highlights the essential points for char data types.

![](image_rsrc2XB4.jpg)

We can perform Arithmetic operations like Addition, Multiplication, Subtraction, and division between char constants.

A char data type can also be represented as an Expression.

Below are some of the Valid char Character Type Representations...  

        char c1 = ' ' ;                            // char type can store a space enclosed with a pair of single inverted commas (' ')

        char c2 = 'd' ;                          // char type can store an alphabet with small case enclosed with a pair of single inverted commas (' ')

        char c3 = 'S' ;                           // char type can store an alphabet with Capital case enclosed with a pair of single inverted commas (' ')

        Character c4 = '6' ;              // char type can store a single digit enclosed with a pair of single inverted commas (' ')

        char c5 =  '$' ;                         // char type can store any symbol enclosed with a pair of single inverted commas (' ')

        char c6 = '1' ;                          // char type can store a digit enclosed with a pair of single inverted commas (' ')

        char c7 = '0' ;                          // char type can store a digit enclosed with a pair of single inverted commas (' ')

        char c8 = '&' ;                         // char type can store any symbol enclosed with a pair of single inverted commas (' ')

        char c9 = '+' ;                          // char type can store any symbol enclosed with a pair of single inverted commas (' ')

        Character c10 = '*' ;             // char type can store any symbol enclosed with a pair of single inverted commas (' ')

        char c11 = '/' ;                         // char type can store any symbol enclosed with a pair of single inverted commas (' ')

        char c12 = 0 ;                          // char type can also store a number without single inverted commas (' ') if it falls within the range

        char c13 = 1 ;                          // char type can also store a number without single inverted commas (' ') if it falls within the range

        char c14 = 65535 ;              // char type can also store a number without single inverted commas (' ') if it falls within the range

        char c15 = + 21 ;                   // char type can also store a number without single inverted commas (' ') if it falls within the range

Below are some of the Valid Unicode Representations...

        char c16 = '\u0000' ;               // char constant can be a unicode representation

        char c17 = '\u0001' ;               // char constant can be a unicode representation

        char c18 = '\u0010' ;               // char constant can be a unicode representation

        char c19 = '\u0100' ;              // char constant can be a unicode representation

        char c20 = '\uffff' ;                   // char constant can be a unicode representation

        char c21 = '\ufff0' ;                  // char constant can be a unicode representation

        char c22 = '\uff11' ;                 // char constant can be a unicode representation

More Representation of Valid char Character Type...

        Character c23 =                                

                                              '*' ;                           // Statement can be in a separate line

        Character c24=                              

                                           '*'

                                           ;                            // Statement can be in a separate line

        Character c25                                 

        =

                                        '*'

                                     ;                                        // Statement can be in a separate line

       Character c26;                                 

        c26 = '*' ;                                                  // Statement can be in a separate line

        char                                                      

        c27

        ;

        c27

        =   

        '*'

        ;                                     // Each part of a statement can be in a separate line

        Character c28                                 

        ;c28 = '*' ;                                                // Statement can be in a separate line

Below are some of the Invalid char Character Types...

        Character civ1 = '\' ;      // Error: Invalid operator

        char civ2 = 'SS' ;               // Error: char constant length cannot be 2

        char civ3 = '' ;                       // Error: Length of char constant must be 1

        char civ4 = '00' ;              // Error: char constant length cannot be 2

        Character civ5 = ' R ' ;   // Error: Space is also a char constant so char constant length cannot be 3

        char civ6 = S ;                   // Error: char constant should be enclosed between ' '

        char civ7 = '65535' ;      // Error: Length of char constant must be 1  

        Character civ8 = ' + ' ;   // Error: Space is also a char constant so char constant length cannot be 3  

        char civ9 = '" ;                                   // Error: Length of char constant must be 1 and should be enclosed between ' '

        char civ10 = ' " ;                               // Error: Length of char constant must be 1 and should be enclosed between ' '

        char civ11 = '  ' ;                                // Error: Only one space is allowed for a char constant so char constant length cannot be 2

        char civ12 = - 1 ;                              // Error: Number is outside char Type Range

        char civ13 = - 65535 ;                   // Error: Number is outside char Type Range

        char civ14 = 65536 ;                     // Error: Number is outside char Type Range

        char civ15 = '-1' ;                             // Error: char constant length cannot be 2

More Representation of Invalid char Character Types...

        Character civ16;                            

                                          =               '*' ;                            // Error: Left-side assignment should be a variable if the statement ends after the type declaration

        Character civ17;                           

        = ;

                                                        '*'

                                                        ;                                // Error: Left-side assignment should be a variable if the statement ends after the type declaration

Below are some of the Valid char Character Type Expression...       

        char ce1 = 'J' + 'A' + 'V' + 'A' ;        // Arithmetic operations like Addition can be done between char constant

        char ce2 = 'e' * 'd' ;                                // Arithmetic operations like Multiplication can be done between char constant

        char ce3 = 'c' / 's' ;                                // Arithmetic operations like Division can be done between char constant

        char ce4 = 'd' * '2' ;                                // Arithmetic operations like Multiplication can be done between char constants of any type

        char ce5 =  '$' + 'e' * 'A' -  ' ' ;             // Arithmetic operations can be done between char constant of any type

        char ce6 = 'S' + 'A' ;                               // Arithmetic operations like Addition can be done between char constant

        char ce7 = 'S' * 'A' ;                               // Arithmetic operations like Multiplication can be done between char constant

        char ce8 = 'S' - 'A' ;                              // Arithmetic operations like Subtraction can be done between char constant

        char ce9 = 'S' / 'A' ;                             // Arithmetic operations like Division can be done between char constant

        char ce11 = '1' + '2' ;                         // Arithmetic operations like Addition can be done between char constant

        Character ce12 = '3' % 'w' ;           // Modular division can be done between char constant

        char ce13 = 'X' - 'S' ;                           // Arithmetic operations like Subtraction can be done between char constant

        char ce14 = 'x' - 'a' ;                          // Arithmetic operations like Subtraction can be done between char constant

        char ce15 = 'x' - 'x' ;                          // Subtracting 'x' (which is 120 numerically) with 'x' (which is 120 numerically) is 0, and it falls in the range of 0 to 65535

        char ce16 = 1 + 1 ;                              // Addition of 1 with 1 results in 2, which falls in the range of 0 to 65535

        Character ce17 = 'a' + 1 ;                 // The addition of 1 with 'a' (which is 97 numerically) is 98, and it falls in the range of 0 to 65535

More Representation of Valid char Character Type Expressions...      

        char ce18                                                          

        =

        'J'

        +

        'A'

        +

        'V'

        +

        'A'

        ;                                                                             // Statement syntax can be in a separate line

        char ce19;                                                         

        ce19='J'+'A'+'V'+'A';                                    // Statement syntax can be in a separate line

        char ce20 =                                                       

                               'J' + 'A' + 'V' + 'A' ;                   // Statement syntax can be in a separate line

        Character ce21 = 'J' + 'A' + 'V' + 'A'        

         ;                                                                          // Statement syntax can be in a separate line

        char ce22                                                       

                             =  'J'

                                       +

                                            ('A')

                                                       +

                                                           ('V')

                                                                     +

                                                                          ('A') ;          // Statement syntax can be in a separate line

        char x,y;

        int z;

        x='a';

        y='b';

        z=x+y;                                                       // Addition is performed on the Unicode values of the characters and not on the characters themselves. The Unicode values of  'a' and 'b' are 97 and 98, which can be added.

Below are some of the Invalid char Character Type Expressions...

        char cive1 = 'S' - 'X' ;                             // Error: Adding 'S' (which is 83 numerically) with 'X' (which is 88 numerically) falls outside of the range 0 to 65535

        char cive2 = 65535 + 'x' ;                 // Error: Adding 'x' (which is 120 numerically) with 65535 falls outside of the range 0 to 65535

        Character cive3 = 65530 + 6 ;       // Error: The addition of two numbers falls outside of the range 0 to 65535

        char cive4 = 'c' \ 's' ;                            // Error: Invalid operator   

        char cive5 = 'S + d' ;                            // Error: char constant should be enclosed between ' '    

        char cive6 = '6'*' d ' ;                           // Error: Space is also a char constant, so the char constant length cannot be 2

More Representation of Invalid char Character Types...

        char cive7 =

                             'J' + 'A' + 'V' + 'A

                            ' ;                                               // Cannot enclosed a character in a separate line

        char

                               cive8

                              = 'A';                                 // Error : char should not be used alone

D) boolean Data Types:

A boolean data type can take only two possible Boolean values, true or false.

The default value if boolean is fasle.

This data type is used to track true/false conditions.

In Java, a boolean is a literal true or false.

Bytes occupied by booelan is 1.

A variable of the type boolean can be assigned as a Boolean value or an expression that evaluates conditions, whether true or false.

We should not use true or false as variable names.

Unlike C and C++, true and false boolean data types in Java do not mean that true is 1 and false is 0.

Fig. 3.6 also highlights the essential points for boolean data types.

![](image_rsrc2XB5.jpg)

No Arithmetic operations are allowed on boolean data types.

Below are some of the Valid boolean Boolean Type Representations...

        boolean b1 = false ;                       // boolean data type can        store false

        boolean b2 = true ;                        // boolean data type can store true

        Boolean b3 = false ;                      // Boolean can be used in place of  boolean data type

        Boolean b4 = true ;                        // Boolean can be used in place of boolean data type

More Representation of Valid boolean Boolean Type...

        boolean ShineNRise ;                    

        ShineNRise = true ;                         // Statement can be in a separate line

        Boolean condition =                     

        false

        ;                                                               // Satement can be in a separate line

        boolean snr ; snr = false ;            // Different Statement can be written in a same line

        boolean                                               

        S

        ;

        S

        =

        true

        ;                                                                   // Each part of a statement can be in a separate line

        Boolean b =                                            

        false;

        ;

        ;

        ;                                                             // Java don't mind if you give more than one Statement Terminator to mark the end of the statement

Below are some of the Invalid boolean Boolean Type Representations...

        boolean bi1 = 0 ;                         // Error: A boolean data type can take only two possible Boolean values, true or false  

        boolean bi2 = 1 ;                        // Error: A boolean data type can take only two possible Boolean values, true or false

        boolean true = 1 ;                      // Error: true cannot be used as a Variable

        boolean false = 0 ;                   // Error: false cannot be used as a Variable  

More Representation of Invalid boolean Boolean Type...                

        boolean ShineNRise ;            

        ShineRise = true ;                    // Error: According to Rule No. 9, a variable ShineRise must be declared first before assigning value to it

        Boolean bi4 ==                        

        false;

        ;                                                               // Error: Double equal to  operator is not used to assign the value of a variable

        boolean ss  ss = false ;             // Error: Statement terminator is not used

        Boolean ;                                        

        a = false ;                                      // Error: As per Rule No. 2, no variable declared

Below are some of the Valid boolean Boolean Type Expressions...

        boolean sum;

        sum = (1 + 2) > 4;  

        boolean multiply;

        multiply = (1 * 2) > 1;

        Boolean divide= (4/2) > 1;

        boolean sub;

        sub = (1 - 2) > 4;

        boolean sum1;

        sum = (1 + 2) < 4;

        boolean multiply1;

        multiply = (1 * 2) < 1;

        boolean multiply2;

        multiply2 = (1 * 2) == 1;

        boolean bie = 5 >= 8 ;

Below are some of the Invalid boolean Boolean Type Expressions...

        boolean bie1 = 5 => 8 ;             // Error:  = operator should be used after > or < sign

        int bie2 = 5 < 8 ;                          // Error: Invalid data type

        int bie3 = 5 > 8 ;                         // Error: Invalid data type

More Representation of Invalid boolean Boolean Type Expression...

        boolean sum2;

        sum2 = (1 + 2) = 4;                       // Error: Single equal to an operator is not used for comparison

        boolean;                                           

        multiply3 = (1 * 2) == 1;          // Error: No variable declared

        boolean sum1,sum2;                 

        sum2 = sum1+sum2;                // Error: Arithmetic operation cannot be performed directly on two boolean values

![](image_rsrc2XB6.jpg)

2) Non-primitive data types:

Non-primitive data types are outside this course's scope; we will learn this in Level 2 (i.e. Intermediate Course). However, we will cover class data types in Chapter 6.

◆◆◆

Exercise:-

1) Fill in the Blanks:-

a) Each character in Java is represented as a _______ character, not an

      ASCII character.

b) A boolean data type can take only ______ possible values.

c) Boolean is an ______ wrapper for a boolean.

d) A variable of the type ______ can be used to evaluate an expression.

e) A byte is _____ times smaller than an integer.

f) Bytes occupied by double is _______.

g) The Range of a float data type is _______.

h) The default value of int is ______.

i) We use the Suffix ______ at the end to represent long type.

2) State which of the following statements is true or false:-

a) true can be used as a Variable. 

b) A number without a decimal point is treated as a float by default. 

c) Can we treat double as a float ?

d) Bytes occupied by float is 8.

e) Default value of float is 0.0F.

f) The long data type is used when you need a greater  range of values

     than those provided by int.

g) The default value of a long is 1.

h) During an assignment, the value of the long being assigned can

      exceed the range of the variable.

i) All keywords must be used with Capital letters because Java

    already defines them.

j) Long cannot be used to represent long data types.

k) Int is the least commonly used out of the different types of inte-

      gers.

l) Bytes occupied by int is 4.

m) We can use Int to represent Integer data type.

n) A short data type is two times smaller than an integer.

o) Short can be used to represent short data type.

p) Integer can also be used instead of int data type.

q) boolean data types false means 0.

3) Select all the correct Alternatives in the below options.

a) Which are the options are the types of Integer Type?

      2147483l, + 3277, 1.2, '6'

b) Which alphabet is used as a Suffix for different data types ?

      l, e, D, s

c) Which are the correct values of boolean data types?

     boolean, true, 0, 1, false

d) Which are the following numbers that come within range of all

      types of Integer data types?

      - (+2147483648), + (-2147483647), -0, - 21

e) Which are the following are the Valid Unicode Representation ?

      U-0052, U+0030, \ufff0, \uffff0

f) Which of the Arithmetic operations can be performed between

     char constants?

     Addition, Subtraction, Multiplication, Modular Division

4)  Identify which of the following are the Incorrect Data-Type Repre-

       sentations and why?:-

a) char ex1 = 'S' + 'N' + 'R' ;    

b) byte ex2 = - 128 + (+ 128) ;                       

c) float ex3 = 8F * +2f ;                        

d) char ex4 = 'u';;;;;;                              

e) char ex5 = ;'n';                                

f) boolean ex6 = +-5 >= -+8 ;                       

g) short ex7 =  327+67 ;                               

h) Integer ex8 = -(+0);                              

i) float ex9 = + - 0 ;                                

j) int ex10 = (233)/(-5) + (-142) % (-+5) ;           

k) long ex11 = 2147483646 ;     

l) int ex12                                         

    ex12 = (-128) + (+2444) ;

m) int ex13 = ( + 12 ) % ( - +                        

       5 ) ;

n) Long ex14 =                                       

     (-1l) + " :-) " + 1 ;

5) Answers to the following questions:-

a) What are the types of Primitive Integer Types?

b) What is the difference between long and double?

c) What are the Arithmetic operations that are allowed for boolean

      data type?

d) What are the different rules for Variable Declaration?

e) What are the different ways to declare a Variable.

6) Activity:-

Write five complete sentences, each containing at least ten words and two Java reserved words, following the variable name rule defined by Java.

◆◆◆

4\. Java Instructions

Any task is performed by passing Instructions to it. Instructions specify how to perform any specific task. Instruction is used to communicate so that any particular task can be performed or completed as specified. In this chapter, we will learn how to write a Statement to pass different types of Instructions. Also, there are more ways to represent a variable.

1) Java Instructions:

We already know that Instructions specify how to perform any specific task.

Instruction is used to communicate so that any particular task can be performed or completed as specified.

In Java, Instructions are given in the form of statements.

There are different types of Instructions in Java...

               A) Type Declaration Instruction

               B)  Arithmetic Instruction  

               C) Control Instruction

       Fig. 4.1 also shows the different types of Instructions in a structured

       way.

![](image_rsrc2XB7.jpg)

2) Type Declaration Instruction:

The instruction is used to declare the variables used in the program.

Any variable used in the program must be declared before using it in any statement.

We have already seen many Type declarations in Chapter No. 3 for different data types like int, char, double, float, boolean, etc.

Below are the some of the Valid Type Declaration Instruction Representations... 

Example 1 -

        int i1 , i2 ;

        i1 = 1 ;

        i2 = 2 ;

Explanation:

In the first statement, two variables, i1 and i2, are declared of type int, separated by a comma. In Java, We can declare as many as variable in a single statement separated by a comma.

In the second statement, value 1 has been assigned to the variable i1.

In the third statement, value 2 has been assigned to the variable i2.

Example 2 -

        int i3 , i4 = 5 ;   

        i3 = 3 ;

Explanation:

In the first statement, two variables, i3 and i4, are declared of type int, separated by a comma.

Also, no value has been assigned to i3, and value 5 has been assigned to the variable i4.

In the second statement, value 3 has been assigned to the variable i3.

Example 3 -

        int i5=5,i6;​​

        i6=3;

Explanation:

In the first statement, two variables, i5 and i6, are declared of type int, separated by a comma.

Also, no value has been assigned to i6, and value 5 has been assigned to the variable i5.

In the second statement, value 3 has been assigned to the variable i6.

Example 4 -

        int i7=1,i8=6;

Explanation:

Two variables, i7 and i8, are declared of type int, separated by a comma.

Value 1 has been assigned to the variable i7 in the same place where i7 is declared.

Value 6 has been assigned to the variable i8 in the same place where i8 is declared.

Example 5 -

        int i9 = 8 ;

        int i10 = 10 ;

Explanation:

In the first statement, variable i9 is declared and value 8 is assigned to the same.

In the second statement, Integer i10 is created and value 10 is assigned to the same.

Example 6 -

        int i11,i12,i13,i14,i15; i11 = i12 = i13 = i14 = i15 = 21;

Explanation:

In the first statement, variables i11, i12, i13, i14, and i15 are declared with no value assigned.

In the second statement, all Integers i11, i12, i13, i14, and i15 values will equal 21 because we know that LHS should be a variable and RHS should be a value that has to be assigned to a variable. So, the assignment starts from the right to left.

Here, at first, a value, 21, is assigned to i15, i.e., i15 = 21, and then the value of i15 becomes 21 now.

Now, the value of i15, which is 21, is assigned to its LHS i14, i.e., i14 = i15 = 21.

Similarly, the value of i14, which is 21 now, is assigned to its LHS i13, i.e., i13 = i14 =21.

The value of i13, which is 21 now, is assigned to its LHS i12, i.e., i12 = i13 = 21.

Finally, the value of i12, which is 21, is now assigned to its LHS i11, i.e., i11 = i12 = 21.

Example 7 -

        int i21 = 99, i22 = i21 + 3 ;

Explanation:

Two variables, i21 and i22, are declared of type int, separated by a comma.

Value 99 has been assigned to the variable i21\. The value of variable i21 is 99 now.

The second variable, i22, is the sum of i21 and 3\. The value of i22 is already set to 99, so the value of i22 is the 99 + 3 = 102.

Example 8 -

        float ii22 = 1.1f, ii23 = ii22 + 2.1f ;

Explanation:

Two variables, ii22, and ii23, are declared of type float, separated by a comma.

Value 1.1f has been assigned to the variable ii22\. The variable ii22 now holds a value 1.1f.

The second variable, ii23, is a sum of ii22 and 2.1f. The value of ii22 is already set to 1.1f, so i22 is the sum of 1.1f and 2.1f.

Below are some of the Invalid Type Declaration Instruction Representation... 

Example 9 -

        int ii1 = ii2 = ii3 = ii4 = ii5 = 21;       // Error

Explanation:

In this example, no instructions are given to the computer about what ii2, ii3, ii4, and ii5 stand for.  

In Java, we must write a statement indicating the variable's data type before using any variable.  

Since the assignment will start from the right, ii5 has yet to be declared before assigning values.  

So, the computer needs clarification and will show errors.

Example 10 -

        int ii6 = ii7 + 99, ii7 = 1 ;                      // Error

Explanation:

In this example, instruction has yet to be given to the computer about what ii7 stands for.  

In Java, we must write a statement indicating the variable's data type before using any variable.  

Since the assignment will start from the right, ii7 has yet to be declared before adding 99.  

So, the computer needs clarification and will show errors.

Example 11 -

        float ii8 = ii9 + 1.1f, ii9 = 2.1f ;         // Error

Explanation:

Similarly, as in Example 10, ii9 has yet to be declared before adding 1.1f.  So the computer is confused and will show errors.

![](image_rsrc2XB8.jpg)

3) Arithmetic Instruction:

In Chapter 2, we have seen how to define a variable. Defining a variable means we are passing instructions about a variable and its data type to a computer.

So, a Java arithmetic instruction consists of a variable name on the left side of = and variable names and constants on the right of =. We have already seen many examples of how to write an Arithmetic Expression.

Arithmetic operators like Addition, Subtraction, Multiplication, and division connect the variables and constants on the right-hand side of =.   

*, /, -, + are the arithmetic operators where as, = is an assignment operator.

In Java, the variables and constants together are called operands. While executing an arithmetic statement, the operands on the right-hand side are operated upon the arithmetic operators, and the result is then assigned, using the assignment operator, to the variable on the left-hand side. Java allows only one variable on the left-hand side =.  

Arithmetic operations can be performed on ints, floats, and chars.  

There is no operator for performing exponentiation operations.

Java allows only one variable on the left-hand side =.

A Java arithmetic statement could be of three types. These are as follows...

        a) Integer mode arithmetic statement

        b) Real mode arithmetic statement

        c) Mixed mode arithmetic statement

a) Integer mode arithmetic statement -

This is an arithmetic statement in which all operands are integer variables or constants.

Below are some of the Valid Integer Mode Arithmetic Statements...

Example 1 -

        int i1 = 14;

        int i2;

        i2 = i1;

        int i3 = (i1 + i2 + 1) * 0 ;

Explanation:

This Example shows how to write an Integer Mode Arithmetic Statement.

All variables i1, i2, and i3 declared are of int type.

In the first statement, integer i1 has been initialized with the value 14.

In the second statement, i2 has been declared without being assigned any value.

In the third statement, the value of i1, which is 14, has been assigned to i2.

In the fourth statement, the variable i3 is the sum of i1, which is already declared and initialized to 14, and i2, which has already been declared and assigned to 14 by i1, and the sum of 1.

Further, when the whole expression is multiplied by 0 it finally becomes i3 = (14 + 14 + 1) * 0 which results in ultimately 0 only.

Hence, the final value of i3 is 0.

Below are some of the Invalid Integer Mode Arithmetic Statements...

Example 2 -

        int i, j, k ;

        i * j = k ;                       // Error

Explanation:

In Example 2, three variables, i, j, and k, are declared without being assigned any value in the first statement.

In the second line, the variable k was assigned to LHS, which is incorrect because k was not initialized with any value.

Also, the LHS part is the multiplication of i and j, which is the expression, and, according to Java, only one variable is allowed on the left-hand side of =.

So, in this case, the computer needs clarification about both the LHS and RHS parts and will throw an error.

b) Real mode arithmetic statement -

This is an arithmetic statement in which all operands are either real constants or real variables.

Below are some of the Valid Float Mode Arithmetic Statements...

Example 1 -

        float i1 = 14;

       float i2;

        i2 = i1;

        float i3 = (i1 + i2 + 1) * 0 ;

Explanation:

This Example shows how we can write a Float Mode Arithmetic Statement.

All variables i1, i2, and i3 declared are of float type.

In the first statement, Float i1 has been initialized with the value 14.

In the second statement, i2 has been declared without being assigned any value.

In the third statement, the value of i1, which is 14, has been assigned to i2.

In the fourth statement, the variable i3 is the sum of i1, which is already declared and initialized to 14, and i2, which has already been declared and assigned to 14 by i1, and the sum of 1.

Further, when the whole expression is multiplied by 0, it finally becomes i3 = (14 + 14 + 1) * 0, resulting in 0 only.

Hence, the final value of i3 is 0.0.

Below are some of the Invalid Float Mode Arithmetic Statements...

Example 2 -

        float i, j, k ;

        i * j = k ;                         // Error

Explanation:

In Example 2, three variables, i, j, and k, are declared without being assigned any value in the first statement.

In the second line, the variable k was assigned to LHS, which is incorrect because k was not initialized with any value.

Also, the LHS part is the multiplication of i and j, which is the expression, and, according to Java, only one variable is allowed on the left-hand side of =.

So, in this case, the computer is confused about both the LHS and RHS parts and will throw an error.

c) Mixed mode arithmetic statement -

This is an arithmetic statement in which some operands are integers, and some are real.

![](image_rsrc2XB9.jpg)

4) Control Instruction:

Control Instructions enable us to specify the order in which the various instructions in a program are specific the order in which the various instructions in a program are to be executed by the computer.

Control Instruction determines the flow of control in a program.

There are four types of control instructions in Java...

        a) Sequence Control Instruction

   b) Selection or Decision Control Instruction

   c) Repetition or Loop Control Instruction

   d) Case-Control Instruction

◆◆◆

Exercise:-

1) Fill in the Blanks:-

a) Java allows only ________ variable on left-hand side =.

b) = is an _______ operator.

c) There are ______ types of Java Instructions.

d) The variables and constants on the right-hand side of

      = are connected by ______.

e) The variables and constants together are called ______.

2) State which of the following statements is true or

      false:-

a) Any variable used in the program may or may not be declared be

     fore using it in any statement.

b) Arithmetic operations can be performed on chars.

c) An Arithmetic instruction is used for storing character constants  

     in character variables.

d) Integer mode arithmetic statement represents decimal points  

      numbers.

e) Arithmetic operations can be performed on int, float, and char.

3) Identify which of the following are the Incorrect Data-Type

     Representations and why:-

a) int i11,i12=21;

     int i13=i12,i15=5;

     i11=i12;

b) float x,y;float z;

     x=2;

     y=1;

     z=x+y+z;

c) float f1 = 14.00F;

     Float f2 = f1;

     float f3 = (f1 + f2 + 1) * 0 ;

d) int i22 = 0;

      int i23 = 1;

      int i23 = 0;

      int i22 = 1;

e) int i31,i32,i33,i34;

     i35=i34=5;

     i32 = i32 = i31 = i34 = 21;

f) float xx = 14.00F;

     int yy = xx;

     float zz = xx + yy ;

4) Answers to the following questions:-

a) What are Operands?

b) What are arithmetic operators?

c) What are the arithmetic statements?

d) What are the different types of Declaration Instructions?

e) What do you mean by Mixed mode arithmetic statement?

5) Activity:-

Write 10 distinct examples of arithmetic expressions by yourself.

◆◆◆

5\. Java First Program

In this chapter we will write the first Program. Have a look at Program Structure and various its Syntax, Different program Scenarios, Output Programs, and Scenario based Programs.

1) Program Structure:

A Java Program is a set of instructions and statements a computer uses to perform a specific function or task.

In Chapter 1, we understood what we mean by Program, Programming language, and Programming.

A Program consists of a structure. Different elements form the structure of the Program.

Packages, classes and methods, and statements form the structure of a Java Program.

A Program may contain any number of packages, classes, methods, and statements. As of now, focus on understanding the Program Structure. We will learn about all these elements in more detail later in this chapter.

Fig. 5.1 shows the Program Structure of a Java Program consisting of different Packages.

Here, a Java Program contains two Packages, Package1 and Package2.

![](image_rsrc2XBA.jpg)

Each Package can contain different classes. class1 and class2 belongs to Package1, class3 and class4 belongs to Package 2.

Each class can have one or more than one method. class1 and class4 have only one method, whereas class2 and class3 have two methods.

Each method can have different set of statement to be executed.

Fig. 5.2 shows a Project View. Each Java Program in IDE is written inside the Project. IDE is Integrated Development Environment, we will see about IDE later in this chapter.

In IDE, any number of Projects can be created. Here, 0-JavaInterview and 1-Java_Level_1_Beginners_Course are the Projects created.

![](image_rsrc2XBB.jpg)

Each Project can contain one or more than one Packages. com.Chapter_2 and com.Chapter_3 are the two Packages created.

Each Package can have any number of Java Files with .java extension.

The figure shows six Java files, such as CharacterConstant_3, Exercise, and others on the row.

Each Java File contains any number of classes. File CharacterConstant_3 and Exercise contain only class shown in the figure.

Each class can contain any number of methods. Here, main() is created in each class.

Program is written inside each method using different statements, as shown in Fig. 5.1.

2) Program Instruction:

Each instruction in a Java program is written as a separate statement. Therefore, a complete Java program would comprise a series of statements.

3) Program Statements:

Program Statements are used to specify instructions to be executed.

The statements in a program must appear in the same order in which we wish them to be executed.

Blank spaces may be inserted between two words to improve the readability of the statement.

No spaces are allowed within a variable, constant, or keyword.

Every Java statement must end with a semicolon (;), a statement terminator.

4) First Program and its Parameters:

Let us introduce you to the first Program, which is very basic and simple...

class FirstProgram

{

        public static void main(String[] args)

        {

              System.out.println("Welcome to Shine N Rise!");

        }

}

The first Program is also shown in Fig. 5.3 for better understanding.

![](image_rsrc2XBC.jpg)![](image_rsrc2XBD.jpg)

Below are the different syntaxes that are used in Java Programs.

Let's try to understand each one of them...

a) Statement Terminator -

This semicolon (;) acts as a statement terminator.

A statement terminator is a single character.

In a Program, it is used to indicate the end of an instruction or a

statement.

Fig. 5.3 shows how and where to use a Statement Terminator.

b) public -

public keyword is an access modifier that represents visibility. It

means it is visible to other methods and classes.

We will learn more about the different types of Access modifiers in

Level 2 (i.e. Intermediate Course).

Fig. 5.3 shows how and where to use public.

c) class -

class is a keyword.

class cannot be used as a variable name since it is a Reserved word.

The class keyword is used to declare a class in Java.

A semicolon at the end of class is optional in Java.

class is followed by a class name.

We can also use a public access modifier before the class keyword.

Using public is optional; we use it with class keyword for visibility.

Fig. 5.3 shows where to use the class keyword.

d) Parenthesis -

Parenthesis ( ) surround the input parameters of a function call.

We use Parenthesis to pass the argument through a method. Any

number of Arguments can be passed on to any data type.

Fig. 5.3 shows how and where to use Parenthesis.

e) function() -

Every instruction used in a Java program should belong to a function.

In Java, a function is also known as a Method.

Every function must belong to a class, and every class must belong to a package.

A function contains a set of statements.

Fig. 5.3 shows what block represents a method.  

There can be multiple functions in a Java program, but in this course (Level 1), we will concentrate on only those programs with only one function.

The way functions in a calculator return a value; similarly, functions in Java also return a value.

f) Package -

The classes and methods we have seen are present inside a Package.

When using IDE, we create Package first, then inside Package, we create a class, and then we write methods inside a class.

Fig. 5.1 and Fig. 5.2 shows how different packages can contain classes and methods inside it.

g) Pair of Braces -

All statements that belong to the function are enclosed within a pair of braces { }.

We also use a pair of braces to represent everything within a class.

Fig. 5.3 shows where and how to use Pair of Braces at different places.

h) main() -

main() is a function.

The name of the function has to be main(), it cannot be anything else.

All statements that belong to main() are enclosed within a pair of braces { }.

main() method represents the starting point of the program.

Fig. 5.3 shows a single method with main().

Below are some of the Valid Java main() method signature...

        public static void main(String[] args)

        public static void main(String []args)

        public static void main(String args[])

        public static void main(String... args)

        static public void main(String[] args)

Below are some of the Invalid Java main() method signature...

        public void main(String[] args)

        static void main(String[] args)  

        public void static main(String[] args)

i) static -

main() method is always preceded by the keyword static.

static is a keyword.

If we declare any method as static, it is known as the static method.

Fig. 5.3 shows how to use a static keyword.

Our Program cannot run if we have not used a static keyword along with the main() method.

static is used for better memory management.

We will learn more about a static part in  Level 2 (i.e. Intermediate Course).

j) void -

void is the return type of the method. Return type means output.

void means the method does not return any value. No output case.

Since we do not wish to return any value from the main() function we have to specify this using the keyword void before main().

We cannot write any function without using the return type.

Fig. 5.3 shows how to use void as a return type.

This Course Level 1, is limited to void return type only. We will see more return types like int, float, double, and other types of data-type that the method can return in Level 2 (i.e., Intermediate Course).

k) [] -

Square brackets [] are used for the declaration of arrays and the selection of array elements.

Array means a collection of any type. We will learn more about Array  in  Level 2 (i.e. Intermediate Course).

Fig. 5.3 shows how to use Square brackets.

l) String[] -

String[] args or String args[] is used for command line arguments.

command line argument is to provide input to a program by passing arguments to it as a method argument.

At this level, we have not covered any Program where the command line provides input. We will learn and see how to use it in  Level 2 (i.e., Intermediate Course).

We use String[] args to pass multiple arguments to a main() method.  

String[] args means an array of sequences of characters (Strings) that are passed to the main function.

Fig. 5.3 shows how to use Array of String to accept multiple arguments. We will learnmore about Array in Level 2 (i.e., Intermediate Course).

m) args -

args contains all the argument that has been passed to the main() method.

It contains an array of sequences of characters (Strings) that can be used in a method.

Fig. 5.3 shows how to pass arguments.

n) System -

It is a class. Since it is a class it has a method in it.

System classes are used for standard input and standard output purposes.

By using System class we can print the output of a Program.

Fig. 5.3 shows how to use System as a class.

o) out -

out is a static  object defined in a System class.

The out is an instance of the System class.

We will learn about Static object and instance  in  Level 2 (i.e. Intermediate Course).

Fig. 5.3 shows where to use out as a  static object.

p) println() -

Unlike other languages, Java does not contain any instructions to display output on the screen.

All output to the screen is achieved using ready-made library functions. One such function is println().

println() is a function of PrintStream class.

The output of each println() function appears in a new line.

println() cannot only print values of variables, but it can also print the result of an expression.

If we want to split the output of one println() function into two lines we can do so using an Escape Sequence  '\n'.

'\n' comes in handy when we want to format the output properly on separate lines.

We can also use print() in place of println() but the output will not appear in a new line.

Fig. 5.3 shows where to use println() to print a output.

q) Double quotes -

Double quotation marks to enclose quoted material " ".

Double quotes are used to represent String and also to pass some information to be printed in the output.

Fig. 5.3 shows where to use double quotes.

r) System.out.println() -

We use System.out.println() whenever we wish to display output on the screen.

System.out.println() is used to print statements.

Here, System is a class, out is an object of the PrintStream class, and println() is a method of the PrintStream class.

Whatever we write inside Parenthesis inside double quotes will be displayed in the string.

Note: To explain all the Programs starting from this chapter, we will use the sysout word to represent a System.out.println() to print an output.

Fig. 5.3 shows where to use sysout statement. We can use it anywhere in a Program as per requirement.

s) Program Comments -

In Java, a often comments are used in a Program to explain Java code, and to make it more readable.

It helps a reader to better understand the why a piece of code is written and what is the use fo it.

Though comments are not necessary, it is good practice to begin a program with a comment indicating the purpose of the program.

Any number of comments can be written at any place in the program.

Comments cannot be nested.

Comment can be written in two ways...

        i) Single-line Comments

        ii) Multi-line Comments

Single-line comments start with two forward slashes (//).

Any text between // and the end of the line is ignored by Java (will not be executed).

A comment can be split over more than one line. Such a comment is often called a multi-line comment.

Multi-line comments start with /* and ends with */.

Any text between /* and */ will be ignored by Java.

Comment about the program should either be enclosed within /* */ or be preceded by //.

Normally, we use // for short comments, and /* */ for longer.

Run a Program:

We have already seen how to write a first Program. Let us see how we can run any Program to print the desired output.

Running a program means getting the expected behavior of a method written inside a class.

sysout statement is written inside a method to show the desired result.

We can run our Program in multiple ways...

        a) Using Compiler App on Mobile or Tablet

         b) Using the Online compiler on Google or any other search engine

         c) Using IDE on a Computer or Desktop, or Laptop

IDE is an Integrated Development Environment tool which provides a tool to write and run a Program.

The mobile device is used to run short programs with a single method.

We can write a large, complex program with a Proper Program Structure in a Computer device.

All Programs covered in this book can be written and run on all devices.

Please visit www.shinenriseindia.com, Core-Java Level 1 inside the Brainery unit,  to learn more about IDE and see how we can run our Program on mobile and set up a workspace and an IDE to run the Program on a Computer or Desktop.

![](image_rsrc2XBE.jpg)

6) Programs Scenarios:

The following are different Program Scenarios...

Scenario 1 (Program with Single Java Statement inside a function) -

// Program with Single Java Statement inside a function

public class Scenario_1

{

        public static void main(String[] args)

        {

              // Here, only one statement is written in a method

              System.out.println("Welcome to SNR!");

        }

}

Scenario 2 (Program with Single Java Method) -

// Program with Single Java Method

public class Scenario_2

{

        // Here, only one method is created inside a class

        public static void main(String[] args)

        {

        }

}

Scenario 3 (Program with Multiple Java Statements) -

// Program with Multiple Java Statements

// Example 1- The following Program will work

public class Scenario_3

{

        // Here, multiple statements are used inside a method

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Example 2- The following Program will also work

class Scenario_3_2

{

       public static void main(String[] args)

        {

              // Here, multiple statements are used inside a method

              String str="Welcome to SNR!";

              System.out.println(str);

              int i = 5 ;

              System.out.println(i);

              boolean snr=true;

              System.out.println(snr);

              Long l;

              l = 12345l;

              System.out.println(l);

        }

}

Scenario 4 (Program with or without the main() method) -

// Program with the main() method

// Example 1- The following Program will work

public class Scenario_4

{

        // Here, main() is the only method   

        public static void main(String[] args)

        {

             String str="Welcome to SNR!";     

            System.out.println(str);

        }

}

// Program without main() method

// Example 2- The following Program will not work

class Scenario_4_2

{

        // Error: There is no method declared      

              /* Here, variables can be declared without any method but

                       sysout statements will work only inside a method */

              String str="Welcome to SNR!";

              System.out.println(str);

}

Scenario 5 (Program with or without method parameter) -

// Programs with method parameter

// Example 1- The following Program will work

public class Scenario_5

{

        public static void main(String[] args)

        {             

              String str="Welcome to SNR!";              

              System.out.println(str);

        }

}

// Example 2- The following Program will work

class Scenario_5_2

{

        public static void main(String args[])

        {  

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Programs without method parameter

// Example 3- The following Programs will not work

class Scenario_5_3

{

        /* Error: String arguments are required to be passed as an

                 argument inside main() method */

        public static void main()

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Example 4- The following Program will not work

class Scenario_5_4

{

        /* Error: Only one argument i.e., String arguments is required to be

                 passed as an argument */

        public static void main(String[] args, int i)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Example 5- The following Program will not work

class Scenario_5_5

{

        /* Error: Only one argument i.e., String arguments is required to

                 be passed as an argument */

        public static void main(int i)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

Scenario 6 (Program with or without Return type) -

// Program with Return type

// Example 1- The following Program will work

public class Scenario_6

{

        // main() method is returning void as a return type

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Example 2- The following Program will not work

class Scenario_6_2

{

        /* Error: The following method will throw an error as main()

        method is required to return a void as a return type */

        public static int main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without return type

// Example 3- The following Program will not work

class Scenario_6_3

{

        /* Error: The following method will throw an error as main()

                 method has no void as a return type */

        public static main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

Scenario 7 (Program with or without static keyword) -

// Program with static keyword

// Example 1- The following Program will work

public class Scenario_7

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without static keyword

// Example 2- The following Program will not work

class Scenario_7_2

{

        /* Error: The following method will not work as there is no static

                 keyword used */

        public main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

Scenario 8 (Program with System.out.println) -

// Program with System.out.println

// Example 1- The following Program will work

public class Scenario_8

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without System.out.println

// Example 2- The following Program will also work

class Scenario_8_2

{

        // The following method will also fine but no output will be printed

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

        }

}

Scenario 9 (Program with Pair of Braces) -

// Program with method Pair of Braces

// Example 1- The following Program will work

public class Scenario_9

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without method Pair of Braces

// Example 2- The following Program will not work

class Scenario_9_2

{

        /* Error: The following method will not work as there is no braces

                 used for a method */

        public static void main(String[] args)

              String str="Welcome to SNR!";

}

Scenario 10 (Program with or without Statement Terminator) -

// Program with statement terminator

// Example 1- The following Program will work

public class Scenario_10

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without statement terminator

// Example 2- The following Program will not work

class Scenario_10_2

{

        /* Error: The following method will give an error because statement

                 has not ended with a statement terminator */

        public static void main(String[] args)

        {

              String str="Welcome to SNR!"

              System.out.println(str)

        }

}

Scenario 11 (Program with or without Method parenthesis) -

// Program with Method Parenthesis

// Example 1- The following Program will work

public class Scenario_11

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without Method Parenthesis

// Example 2- The following Program will not work

class Scenario_11_2

{

        /* Error: The following method will not work as arguments of

                 main() method is not inside method parenthesis */

        public static void main String[] args

        {

              String str="Welcome to SNR!"

              System.out.println str ;

        }

}

Scenario 12 (Program with or without a public method) -

// Program with public method

// Example 1- The following Program will work

public class Scenario_12

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without public method

// Example 2- The following Program will not work

class Scenario_12_2

{

        /* Error: The following method will give an error as it is not having

                public as visibility */

       static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

Scenario 13 (Program with or without class) -

// Program with class

// Example 1- The following Program will work

public class Scenario_13

{

      public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without class

// Example 2- The following Program will not work

        /* Error: The following method will not work as method should be

                 present inside a class */

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

Scenario 14 (Program with class name) -

// Program with class name

// Example 1- The following Program will work

public class Scenario_14

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without class name

// Example 2- The following Program will not work

// Error: class is not created with a name

class

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

Scenario 15 (Program with or without method) -

// Program with a method

// Example 1- The following Program will work

public class Scenario_15

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without any method

// Example 2- class can be created without any method

class Scenario_15_2

{

        // No method created

}

Scenario 16 (Program wit or without method name) -

// Program with a method name

// Example 1- The following Program will work

public class Scenario_16

{

        // Here, method name is main

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without method name

// Example 2- The following Program will not work

class Scenario_16_2

{

        // Error: A method is with no name

        public static void (String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

         }

}

Scenario 17 (Program with or without println) -

// Program with println

// Example 1- The following Program will work

public class Scenario_17

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without println

// Example 2- The following Program will not work

class Scenario_17_2

{

        /* Error: The following method will not work as println()

                 method is not used for output */

        public static void (String[] args)

        {

              String str="Welcome to SNR!";

              System.out(str);

        }

}

Scenario 18 (Program with or without System.out.println input string) -

// Program with System.out.println input string

// Example 1- The following Program will work

public class Scenario_18

{

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println(str);

        }

}

// Program without System.out.println input string

// Example 2- The following Program will also work

class Scenario_18_2

{

        // The following method is fine but will not print any output

        public static void main(String[] args)

        {

              String str="Welcome to SNR!";

              System.out.println();

        }

}

Scenario 19 (Program with or without System.out.println input string double quotes) -

// Program with System.out.println input string double quotes

// Example 1- The following Program will work

public class Scenario_19

{

        public static void main(String[] args)

        {

              System.out.println("Welcome to SNR!");

        }

}

// Program without System.out.println input string double quotes

// Example 2- The following Program will not work

class Scenario_19_2

{

        // Error: Input string in println method is without double quotes

        public static void main(String[] args)

        {

              System.out.println(Welcome to SNR!);

        }

}

7) Data-Types output Programs:

Data-Type 1 (Program printing byte Integer Type) -

// Program printing byte Integer Type

public class DataType_1

{

        public static void main(String[] args)

        {

              byte b1 = 125 ;

              System.out.println(b1);

              Byte b2;

              b2= - 127 ;

              System.out.println(b2);

              byte

              b3

              =

              -

             127

              ;

              System.out.println(b3);

              byte bve4 = - 130 % 5 ;

              System.out.print(bve4);

        }

}

Output:

125

-127

-127

0

Data-Type 2 (Program printing short Integer Type) -

// Program printing short Integer Type

public class DataType_2

{

        public static void main(String[] args)

        {

              short s1 = 31800 ;

              System.out.println(s1);

             Short

             s2

             =

             +

             32767

             ;

             System.out.println(s2);

             Short s3;

             s3 = 32767 ;

             System.out.println(s3);

             short sve4 = + 32770 % 1 ;

             System.out.println(sve4);

             short sve5;

             sve5= + 32770 % 1 ;

             System.out.println(sve5);

             short sve6 = + 32770 % 1

                                      -3

                                     +5;

              System.out.print(sve6);

        }

}

Output:

31800

32767

32767

0

0

2

Data-Type 3 (Program printing int Integer Type) -

// Program printing int Integer Type

public class DataType_3

{

        public static void main(String[] args)

        {

              int i1 = 2309 ;

              System.out.println(i1);

              int i2 = 2147483645 ;

              System.out.println(i2);

              int

              i3

              =

              2147483645

              ;

              System.out.println(i3);

              int i4

              = 2147483645 ;

              System.out.println(i4);

               int ie5 = (-12)/(-5) ;

               System.out.println(ie5);

               int ie6 =

                                (-12)

                                   %

                               (-5) ;

              System.out.println(ie6);

              int ie7

              =

              (

             12

              )

             %

             (

             -

             5

              ) ;

              System.out.print(ie7);

        }

}

Output:

2309

2147483645

2147483645

2147483645

2

-2

2

Data-Type 4 (Program printing long Integer Type) -

// Program printing long Integer Type

public class DataType_4

{

        public static void main(String[] args)

        {

              long l1 = 2147483645 ;

              System.out.println(l1);

              long l2 = - 2L ;

              System.out.println(l2);

              long l3

              =

              -

              2L

              ;

              System.out.println(l3);

               long l4

               = - 2l ;

               System.out.println(l4);

             Long ie5 = (-12l) % (-5l) ;

             System.out.println(ie5);

             Long

             ie6

             =

             (

             -

             12l

             )

             %

              (

              -

             5l

              )

              ;

             System.out.print(ie6);

        }

}

Output:

2147483645

-2

-2

-2

-2

-2

Data-Type 5 (Program printing double Real Type) -

public class DataType_5

{

        public static void main(String[] args)

        {

              double d1 = 8.2 ;

              System.out.println(d1);

              double d2 = 12345789.201245789 ;

              System.out.println(d2);

              Double d3 = 12345789.2D ;

              System.out.println(d3);

     double de4 = 1.2d / 1.0f;        

     System.out.println(de4);

     Double                              

     de5

     =                       

     9.0F

     %

     8.0

     ;                                

     System.out.println(de5);

     double                             

     de6 =                       

     9.0 % 8.0 ;                      

     System.out.print(de6);

        }

}

Output:

8.2

1.2345789201245788E7

1.23457892E7

1.2

1.0

1.0

Data-Type 6 (Program printing float Real Type) -

public class DataType_6

{

        public static void main(String[] args)

        {

               float f1 = 9.5f ;

              System.out.println(f1);

      Float fe2 =                       

                   (-12F)

                        %

                              (-5f) ;   

      System.out.println(fe2);

         float                             

      fe3

      =

      (

      -

      12F

      )

      %

     (

     -

     5F

     )

     ;

     System.out.println(fe3);

        }

}

Output:

9.5

-2.0

-2.0

Data-Type 7 (Program printing char Character) -

public class DataType_7

{

        public static void main(String[] args)

        {

              char c1 = ' ' ;

              System.out.println(c1);

              char c2 = 'd' ;

              System.out.println(c2);           

              Character c3 =

                                                  '*' ;

              System.out.println(c3);   

              char

              c4

              ;

              c4

              =

              '*'

              ;

              System.out.println(c4);

              Character ce5 = 'a' + 1 ;

              System.out.println(ce5);

              char ce6 = '1' + '2' ;

              System.out.println(ce6);

              Character ce7 = '3' % 'w' ;

              System.out.println(ce7);

              char x,y;

              int z;

              x='a';

              y='b';

              z=x+y;

              System.out.print(z);

        }

}

Output:

d

*

*

b

c

3

195

Data-Type 8 (Program printing boolean Boolean Type) -

public class DataType_8

{

        public static void main(String[] args)

        {

              boolean b1 = false ;

              System.out.println(b1);

              boolean ShineNRise ;

              ShineNRise = true ;

              System.out.println(ShineNRise);

              boolean snr ; snr = false ;

              System.out.println(snr);

              boolean

              S

              ;

              S

              =

              true

              ;

              System.out.println(S)

              boolean multiply2;

              multiply2 = (1 * 2) == 1;

              System.out.print(multiply2);

        }

}

Output:

false

true

false

true

false

Data-Type 9 (Program printing String Constant) -

public class DataType_9

{

        public static void main(String[] args)

        {

              String s1 = " Shine N Rise " ;

              System.out.println(s1);

              String s2 = "21 1" ;

              System.out.println(s2);

              String se3 = "J" + "A" + "V" + "A" ;

              System.out.println(se3);

              String se4 = "ss+++" + "/" ;

              System.out.println(se4);

              String se5 = "ss+++" + "-+/" ;

              System.out.print(se5);

        }

}

Output:

 Shine N Rise

21  1

JAVA

ss+++/

ss+++-+/

![](image_rsrc2XBF.jpg)

8) Output Problems:

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int a1 = 21 ;

              int a2 = 9999 ;

              System.out.println((a1+2) + " " + (a2*0));

              System.out.println((a1*4) + " and " + (a2-999));

              System.out.println((a1%3) + " " + (a2/9));

              System.out.println((a1+a2)*(a2-a1) + " " + (a2%a1));

              System.out.print(" " + a1 + " " + a2);

        }

}

Output:

23 0

84 and 9000

0 1111

99979560 3

 21 9999

Explanation:

Firstly, two variables a1 and a2 are created and values have been as-signed, with 21 and 9999 respectively.

In the first sysout statement, a1 is added to 2, and a2 is multiplied

by 0 so the result will be 23 and 0 respectively.

Also, results 23 and 0 are separated by a space which is achieved by

" ".

Now 23, space, and 0 have been separated by a '+' sign.

println() method will print the output in a new line.

Hence the output is 23 0.

In the second sysout statement, a1 is multiplied by 4, and a2 is subt-racted by 999 so the result will be 84 and 9000 respectively.

Also, results 84 and 9000 are separated by a space which is achieved by " ".

Now 84, and, and 9000 have been separated by a '+' sign.

println() method will print the output in a new line.

Hence, the output is 84 and 9000.

In the third sysout statement, a1 is a modular division by 3, and a2

is divided by 9 so the result will be 0 and 1111 respectively.

Also, results 0 and 1111 are separated by a space which is achieved by " ".

Now 0, a space, and 1111 have been separated by a '+' sign.

println() method will print the output in a new line.

Hence, the output will be 0 and 1111.

In the fourth sysout statement, there are different operations i.e., a1 is added with a2, a2 is subtracted by a1, and a2 is a modular division by a1\. So, the results are 99979560 and 3 respectively.

Also, results 99979560 and 3 are separated by a space which is achi-eved by " ".

Now 99979560, a space, and 3 have been separated by a '+' sign.

println() method will print the output in a new line.

Hence, the output is 99979560 and 3.

In the fifth sysout statement, there are no operations involved, and a1 and a2 are shown separately which are 21 and 9999 respectively.

Also, 21 and 9999 are separated by a space which is achieved by " ".

Now a space, a1, another space and a2 have been separated by a '+'

sign.

Hence, the output will be 21 and 9999.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int first = 24 ;

              int second = 99 ;

              System.out.println("The value of first is " + first + " and " + "the

                                                          value of second is " + second);

              int third = second ;

              second = first ;

              first = third ;

              System.out.println("The value of first becomes " + first + " and "

                                                         + "the value of second becomes " + second);

        }

}

Output:

The value of first is 24 and the value of second is 99

The value of first becomes 99 and the value of second becomes 24

mes 24

Explanation:

In this program, three variables first, second, and third are declared of type int.

first and second have been initialized with 24 and 99 respectively.

Here, the first sysout will print the numbers before swapping them along with a message.

Variable third contains the value of second i.e., third = second = 99.

Also, second is updated with a value of first i.e., second = first = 24.

Again, first is updated with a value x i.e., first = x = 99.

Now, the second sysout will print the numbers after swapping with an updated value along with a message.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {     

              String s1 = "Knowledge" ;

              String s2 = "is" ;

              String s3 = "wisdom" ;

              System.out.println(s1 + s2 + s3);

              System.out.println(s1 + " " + s2 + " " + s3);

             System.out.println(s1 + " Knowledge " + s2 + " is " + s3 +

                                                        " wisdom ");

        }

}

Output:

Knowledgeiswisdom

Knowledge is wisdom

Knowledge Knowledge is is wisdom wisdom

Explanation:

In this problem, three variables s1, s2, and s3 are created of type

String and values have been initialized with "Knowledge", "is" and

"wisdom" respectively.

In the first sysout statement, all the values are separated by using

a '+' sign.

Hence, the output of the first sysout is Knowledgeiswisdom.

In the second sysout statement, all the values are separated by using a '+' sign and a space using " ".

Hence, the output of the second sysout is Knowledge is wisdom.

In the third sysout statement, all the values and a String are separa-ted by using a '+' sign.

Hence, the output of the third sysout is Knowledge Knowledge is

wisdom.

9) Basic Programs:

1) Write a Java Program which calculates a Simple Interest.

public class SimpleInterestProgram_1

{

        public static void main(String[] args)

        {

               float principal = 10000 ;

               float rate = 30 ;

               float time = 2 ;

              float simpleInterest = ( principal * rate * time ) / 100 ;

              System.out.println("Simple Interest is: " + simpleInterest);

        }

}

Output:

Simple Interest is: 6000.0

Explanation:

In this program, four variables principal, rate, time, and simpleInte-rest are declared of type float.

Variables principle, rate, and time have been initialized with 1000,

30, and 2 respectively.

Variable simpleInterest stores the result of the expressions from RHS.

The expression part is the multiplication of principal, rate, time, and divisible by 100.

The result of the expression will be stored in a simpleInterest and

further sysout statement will print Simple Interest along with a

message.

Hence, the output is 6000.0.

2) Write a Java Program to Multiply two Floating Point Numbers.

public class FloatingNumberMultiplicationProgram_2

{

         public static void main(String[] args)

         {

               float f1 = 30 ;

              float f2 = 2.00f ;

              float multiply = (f1 * f2) ;

             System.out.println("The multiplication of Floating Point

                                                         Numbers is: " + multiply);

        }

}

Output:

The multiplication of Floating Point Numbers is: 60.0

Explanation:

In this program, three variables f1, f2, and multiply are declared of

type float.

Variables f1 and f2 have been initialized with 30 and 2.00f respectively.

Variable multiply stores the result of the expression.

The expression part is the multiplication of f1 and f2.

The result of the expression will be stored in a variable multiply and further sysout statement will print the

multiplication of two numbers along with a message.

Hence, the output is 60.0.

3) Write a Java Program to Compute Quotient and Remainder.

public class QuotientAndRemainderProgram_4

{

        public static void main(String[] args)

        {

              int num = 33 ;

              int quotient = num / 2 ;

              int remainder = num % 2 ;

              System.out.println("Quotient of " + num + " is : " + quotient);

              System.out.println("Remainder of " + num + " is : " + remainder);

        }

}

Output:

Quotient of 33 is : 16

Remainder of 33 is : 1

Explanation:

In this program, three variables num, quotient and remainder are

declared of type int. num is initialized with 33.

quotient contains the result of an expression i.e., num / 2 = 16.

remainder contains the result of an expression i.e., num % 2 = 1.

Hence, the output is 16 and 1.

4) Write a Java Program to Swap Two Numbers.

public class SwapTwoNumbersProgram_5

{

        public static void main(String[] args)

        {

              int num1 = 24 ;

              int num2 = 99 ;

              System.out.println("Numbers before Swapping are : " + "num1="

                                                         + num1 + " num2=" + num2);

              int x = num2 ;

              num2 = num1 ;

              num1 = x ;

              System.out.println("Numbers after Swapping are : " + "num1="

                                                           + num1 + " num2=" + num2);

        }

}

Output:

Numbers before Swapping are : num1=24 num2=99

Numbers after Swapping are : num1=99 num2=24

Explanation:

In this program, three variables num1, num2, and x are declared of type int.

num1 and num2 have been initialized with 24 and 99 respectively.

Here, the first sysout will print the numbers before swapping them along with a message.

Variable x contains the value of num2 i.e., x = num2 = 99.

Also, num2 is updated with a value of num1 i.e., num2 = num1 = 24.

Again, num1 is updated with a value x i.e., num1 = x = 99.

Now, the second sysout will print the numbers after swapping with an updated value along with a message.

Hence, the output will be 24, 99, and 99, 24.

5) Write a Java Program to Convert Milliseconds to Minutes and

      Seconds.

public class ConvertMillisecondsToMinutesAndSecondsProgram_12

{

        public static void main(String[] args)

        {

              long milliseconds = 3500000;

              long minutes = (milliseconds / 1000) / 60;

              long seconds = (milliseconds / 1000) % 60;

              System.out.println(milliseconds + " Milliseconds = " + minutes +

                                                        " minutes and " + seconds + " seconds.");

        }

}

Output:

3500000 Milliseconds = 58 minutes and 20 seconds.

Explanation:

In this program, three variables milliseconds, minutes and seconds are declared of type long.

milliseconds is initialized with 3500000.

minutes and seconds contains the results of an expression.

minutes will contain the value 58 as (3500000 / 1000) / 60 = 58.

seconds will contain the value 20 as (3500000 / 1000) % 60 = 20.

Hence, the output is 58 minutes and 20 seconds.

![](image_rsrc2XBG.jpg)

10) More Program:

Write a Java Program to calculate Student Aggregate and Percentage marks for five subjects.

Given that, Fig 5.5 shows the marks obtained in five subjects.

![](image_rsrc2XBH.jpg)

public class TotalMarksAndPercentage_1

{

        public static void main(String[] args)

        {

              int english = 66 ;

              int maths = 92 ;

              int science = 89 ;

              int computer = 90 ;

              int social = 78 ;

              int totalMarks = english + maths + science + computer +  social ;

              System.out.println("Total Marks obtained by a students out of             

                                                          500 is : " + totalMarks);

              int percentage = (totalMarks*100)/500 ;

              System.out.println("Total Percentage marks obtained by a

                                                          student is : " + percentage + "%");

        }

}

Output:

Total Marks obtained by a students out of 500 is : 415

Total Percentage marks obtained by a student is : 83%

Explanation:

In a given diagram, we have given marks for five subjects i.e.,

English, Maths, Science, Computer, and Social.

The problem statement is to calculate the total Marks and

Percentage obtained by a Student.

Let's suppose, each subject is represented by a Java variable of type

int and initialized with english = 66, maths = 92, science = 89, computer = 90, and social = 78.

To calculate the Total Marks obtained by a student, just add all the marks of all the subjects and store them in a variable totalMarks of

type int i.e, totalMarks = 66 + 92 + 89 + 90 + 78 = 415.

To calculate the Total percentage obtained by a student, just

multiply totalMarks with 100 and divide it by 500, and store in a

variable percentage of type int i.e, percentage = (415 * 100) / 500 = 83.

Hence, the output is 415 and 83%.

Exercise:-

1) Fill in the Blanks:-

a) Each _______ in a Java program is written as a separate statement.

b) Every Java statement must end with a _______.

c) We use _______ whenever we wish to display output on the screen.

d) This _______ acts as a statement terminator.

e) We use _______ to pass an argument through a method.

f) function() is also called as _______.

g) All statements that belong to function are enclosed within a

      _______.

h) ______ is the return type of the method main().

i) We use ______ to pass multiple arguments to a main() method. 

j) println() is a function of ______ class.

2) State which of the following statements is true or false:-

a) Separate statement in Java Program is identified by a new line.

b) System is not a class.

c) No blank spaces are allowed within a variable, constant, or key

     word.

d) A statement terminator is a multiple-character.

e) class is not a keyword.

f) There can be only one method inside a class.

g) main() is a method.

h) Program can run if we have not used static keyword along with

      the main() method.

i) We cannot write any function without using the return type.

j) The output of each println() function appears in a different line.

k) There is no difference between print() in place of println() 

l) Program Comments cannot be used inside the class

m) In a Java program, a function is contained inside a class and a

        class is contained inside a package.

3) Find and correct any syntax errors in the following programs:-

a) Program 1 -

public class Program_1

{

        public static void main(String[] args)

        {

              if((true && !false) || check==true)

              {

                    System.out.println(!check);

              }

        }

}

b) Program 2 -

public class Program_2

{

        public static void main(String[] args)

        {  

              if(true && !false)

              {

                    System.out.println(false);

              }

        }

}

c) Program 3 -

public class Program_3

{

        public static void main(String[] args)

        {

              if(false || (boolean b = true))

              {

              }

        }

}

4) Answers to the following questions:-

a) What do you mean by access modifier?

b) What is function()?

c) What do you mean by static method?

d) What do you mean by Return type?

e) What is the use of the println() method?

f) Explain different elements of System.out.println().

g) What is a multi-line comment.

5) Basic Programs:-

a) Write a Java Program to add five Strings.

b) Write a Java Program to find the square of a number.

c) Write a Java Program to print a table of 5 upto 10 in reverse order.

d) Write a Java Program to find the square of a number.

e) Write a Java Program to find the multiplication of all ASCII values

     of Characters from p to s.

6) What is the Output of the following Programs:-

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              System.out.println('S'+'N'+'R');

              System.out.println("S"+"N"+"R");

              System.out.println('S'+'N'+ 24);

      }

}

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              String first, second = "second";

              first = first + second;

               System.out.println(first);

        }

}

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int y = 08;

              y = y + 2;

              System.out.println(y);

        }

}

Problem 4 -

public class Problem_4

{

        public static void main(String[] args)

        {

              System.out.println('j' + 'a' + 'v' + 'a');

        }

}

Problem 5 -

public class Problem_5

{

        public static void main(String[] args)

        {

              System.out.print("A" + "B" + 'A');

              System.out.print(20+ 1.34f + "A" + "B");

        }

}

7) More Problems:-

a) Write a Java Program to calculate the Total Expenditure of Product

     purchases. Given that, Fig 5.6 shows the different expenditures on

     different Products.

![](image_rsrc2XBJ.jpg)

b) Write a Java Program to calculate the Percentage of Hours left in a

     Day. Given that, Fig 5.7 shows the hours used on different

     Activites.

![](image_rsrc2XBK.jpg)

8) Activity:-

a) Setup an IDE - Eclipse or IntelliJ on a Laptop or Computer Device.

b) Write all the Programs given in this Chapter, and run them in IDE

     to get the output if applicable.

◆◆◆

6\. Decision Control Instructions

As the name suggests, we use decision Control Instructions in the form of syntax defined by Java when writing a piece of code to decide over something like yes or no, if or else, if or but. In Real-World, we continuously encounter a situation where we must make multiple daily decisions.  

1) Control Instructions:

Java provides statements that can control the flow of Java code. Such statements are called control flow statements.

Java compiler executes the code from top to bottom.

The statements in the code are executed according to the order in which they appear.

There are different types of Control Instructions in Java...

        A) Decision Control Instructions

        B) Loop Control Instructions

        C) Switch Control Instructions

In this chapter, we will look for Decision Control Instructions and the rest in the subsequent chapters.

2) Decision Control Instructions:

This type of instruction is used to write a statement where some decision condition is encountered.

Java has different major Decision making instructions...

        a) The if statement

        b) The if-else statement

        c) The Nested if-statement

        d) The else if Clause

        e) The Logical operators

        f) The conditional operators

Fig. 6.1 also shows different types of Decision Control Instructions.

![](image_rsrc2XBM.jpg)

3) The if Statement:

Like most languages, Java used the if keyword to implement the decision control instructions.

It is the most basic statement among all control flow statements in Java.

It evaluates a Boolean expression and enables the program to enter a code block if the expression is true.

The if statement is used in Java to evaluate a condition.

The control of the program is diverted depending upon the specific condition.

The if statement condition gives a Boolean value, either true or false.

If the condition, whatever it is, is true, then the statement inside if condition is executed.

If the condition is not true, the statement is not executed.

The condition following the keyword if is always may or not be enclosed within a pair of parentheses.

A common mistake while using the if statement is to write a semicolon (;) after the condition.

The relational operators allow us to compare two values to see whether they are equal, unequal, or greater than the other.

= is used for assignment and == is used for comparing two quantities.

=! is called an inequality operator.

The expression can be any valid relational expression that evaluates to a boolean value.

It may so happen that in a program, we want more than one statement to be executed if the expression following if is satisfied; if such multiple statements are to be executed; then, they must be placed within a pair of braces.

The general form is as follows...

        if (condition)  

              statement;

        if (expression)  

              statement;

Working of the if Process Flow:

![](image_rsrc2XBN.jpg)

As can be seen in Fig. 6.2, whenever a program is written using the if statement, some condition must be checked.

First, before the if condition, all the statements will be executed.

When the control reaches the if condition, it will check the condition inside the parenthesis as required.

If the condition passes, the statement inside the if block will be executed.

After executing the if block, the statement after the if block will be checked.

If the condition inside fails, the if block will not be executed.

Again, if the if block is not executed, even the statement after the if block will be executed.

Below are a few statements that represent real-life scenarios. These can be represented using the if condition...

a) Mom, what if today's school bus does not come for the pickup? Then Mom answered that Dad would drop you at school.

b) Dad, what if my classmate has beaten me in the class? Then Dad says that you should go to your teacher and complain about it.

c) The teacher says that if you concentrate on your studies, you will get excellent marks in your exam.  

d) Golu says that if my Dad gives me a mobile, I will learn Coding.

e) Nidhi wonders if I can learn Java Programming then my goal is to build an App.

A) Program Scenarios -

The following are different Program Scenarios...

Scenario 1 (Java Program with or without only if Condition) -

// Java Program with only if Condition

public class Scenario_1

{

        public static void main(String[] args)

        {

              // Example 1

              if(true);

              // Example 2

              if(false);

        }

}

// Java Program without if condition

class Scenario_1_2

{

        // The following method will throw an error

        public static void main(String[] args)

        {

              if();

        }

}

Scenario 2 (Java Program with Single if Statement) -

// Java Program with Single if Statement

public class Scenario_2

{

        public static void main(String[] args)

        {

              // Example 1

              if(true);

                    System.out.println("This is an Example 1");

              // Example 2

              if(false);

                    System.out.println("This is an Example 2");

        }

}

Scenario 3 (Java Program for if Statement with or without Pair of Braces) -

// Java Program for if Statement with Pair of Braces

public class Scenario_3

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

              {

                    System.out.println("This is an Example 1");

              }

              // Example 2

              if(false)

              {

                    System.out.println("This is an Example 2");

              }

       }

}

// Java Program for if Statement without Pair of Braces

class Scenario_3_2

{

        public static void main(String[] args)

        {

              // The following Examples will also work without Pair of Braces

              // Example 1

              if(true)

                    System.out.println("This is an Example ");

        }

}

Scenario 4 (Java Program for if Statement with or without Statement Terminator) -

// Java Program for if Statement with Statement Terminator

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

              {

                    System.out.println("This is an Example 1");

              };

              // Example 2

              if

              (true)

              {

                    System.out.println("This is an Example 2");

              };

               // Example 3

              if

              (

              true

              )

             {

                   System.out.println("This is an Example 3");

             } ;

              /* The following example will may not work as statement termin-

                       ator not used correctly to print output */

              // Example 4

              if(true);  

              {

                    System.out.println("This is an Example 4");

              };

        }

}

 // Java Program for if Statement without Statement Terminator

class Scenario_4_2

{

        /* The following method will also work but may not be able to print

                 output */

        public static void main(String[] args)

        {

             /* The following Examples will also work but may or may not be

                      able to print */

              // Example 1

              if(true)

              {

                     System.out.println("This is an Example");

              }

              // Example 2

              if(false)

              {

                    System.out.println("This is an Example");

              }

              // Example 3

              if(true)

              {

              }

}

Scenario 5 (Java Program for if Statement with or without System.out.println) -

// Java Program for if Statement with System.out.println

public class Scenario_5

{

        public static void main(String[] args)

        {

              // The following will produce a result

              if(true)

              {

                    System.out.println("This is an Example");

              }

        }

}

// Java Program for if Statement without System.out.println

class Scenario_5_2

{

        // The following method will not produce any result

        public static void main(String[] args)

       {

              if(true)

              {

              }

        }

}

Scenario 6 (Java Program for if Statement with Multiple if Statements) -

// Java Program for if Statement with Multiple if Statements

public class Scenario_6

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

              {

                    int i = 2 ;

                    System.out.println("This is an Example 1" + i);

              };

              // Example 2

              if(false)

              {

                    int i ;

                    i = 5;

                    System.out.println("This is an Example 2" + i);

              }

        }

}

Scenario 7 (Java Programs for if Statement evaluating Expressions) -

// Java Programs for if Statement evaluating Expressions

public class Scenario_7

{

        public static void main(String[] args)

       {

             // Example 1

             if(2 == 2)

             {

                   System.out.println("1st if block");

              }

              // Example 2

              if(3 > 2)

              {

                    System.out.println("2nd if block");

              }

              // Example 3

              if(4/2 == 2)

              {

                    System.out.println("3rd if block");

              }

              // Example 4

              if(4/2 == 0)

              {

                    System.out.println("4th if block");

              }

              // Example 5

              if(5*2+1-1 > 1)

              {

                    System.out.println("5th if block");

              }

              // Example 6

              boolean condition1;

              condition1 = (1 + 2) >= 3;

              if(condition1)

              {

                    System.out.println("6th if block : " + condition1);

              }

              // Example 7

              boolean condition2;

              condition2 = (1 * 2) > 1;

              if(condition2)

              {

                    System.out.println("7th if block : " + condition2);

              }

              // Example 8

              Boolean condition3= (4/2) > 1;

              if(condition3)

              {

                    System.out.println("8th if block : " + condition3);

              }

              // Example 9

              boolean condition4;

              condition4 = (1 - 2) > 4;

              if(condition4)

              {

                    System.out.println("9th if block : " + condition4);

              }

              // Example 10

              boolean condition5;

              condition5 = (1 + 2) < 4;

              if(condition5)

              {

                    System.out.println("10th if block : " + condition5);

              }

        }

}

![](image_rsrc2XBP.jpg)

B) Basic Programs -

1) Write a Program to check that the number is within Range.

      Consider a number is 11 and Range is 21.

public class CheckNumberWithinRangeProgram_1

{

        public static void main(String[] args)

        {

              int num = 11 ;

              if(num < 21)

              {

                    System.out.println(num + " is smaller than 21");

              }

        }

}

Output:

11 is smaller than 21

Explanation:

In this Program, a variable num is declared of type int and initialized with 11.

The Problem statement is to check that the number is within Range.

In the if check, the condition is validated as num = 11 is smaller

than 21, so the if block will be executed.

The sysout statement will print the value of a num along with a

message inside the if block.

Hence, the output is 11 is smaller than 21.

2) Write a Program to check that a number is Positive. Consider a

      number is 41.

public class CheckPositiveNumberProgram_2

{

        public static void main(String[] args)

        {

              int num = 41 ;

              if(num > 0)

              {

                   System.out.println(num + " is a Positive Number");

              }

        }

}

Output:

41 is a Positive Number

Explanation:

In this Program, a variable num is declared of type int and initialized with 41.

The Problem statement is to check that a number is Positive.

In the if check, the condition is validated as num = 41 is greater

than 0, so the if block will be executed.

Inside the if block, the sysout statement will print the value of a

num along with a message.

Hence, the output is 41 is a Positive Number.

3) Write a Java Program to print a number if it is divisible by 11.

      Consider a number is 99.

public class CheckNumberDivisible_3

{

        public static void main(String[] args)

        {

              int num = 99 ;

              if(num % 11 == 0)

              {

                     System.out.println(num + " is divisible by 11");

              }

        }

}

Output:

99 is divisible by 11

Explanation:

In this Program, a variable num is declared of type int and initialized with 99.

The Problem statement is to check that a number is divisible.

In the if check, the condition is validated as num % 11 = 0 equals 0, so the if block will be executed.

Inside the if block, the sysout statement will print the value of a

num along with a message.

Hence, the output is 99 is divisible by 11.

C) Output Programs -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

              {

                    int num1 = 400;

                    int num2 = 400;

                   if(num1 == num2)

                   {

                         System.out.println(num1 + " and " + num2 + " are equal");

                   }

            }

}

Output:

400 and 400 are equal

Explanation:

Two variables, num1, and num2, are declared and initialized with

the value 400.

In the if check, variable num1 is compared to num2 using the ==

operator.

In this case, both num1 and num2 equals to 400, so the condition

will be true, and the sysout will print the statement.

The sysout statement separates num1, num2, and strings using the '+' sign.

Hence, the output is 400 and 400 are equal.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              if(false)

              {

                    System.out.println(false);

              }

              System.out.println(true);

        }

}

Output:

true

Explanation:

The Condition inside if check is already false. So, the if check will

not be executed.

The first sysout statement is not reachable.

The second sysout statement is just printing the true value.

Hence, the output is true.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int a = 1 ;

              if(a > 0)

              {

                    a = 0;

              }

              System.out.println("The value of a is : " + a);

        }

}

Output:

The value of a is : 0

Explanation:

In this problem, variable a is declared of type int and initialized with 1.

The condition inside if check checks whether a is greater than 0.

Since a is already 1 that is greater than 0, the condition will be true, and the statement inside if check will be executed.

Inside, if check again, the value of a is updated to 0, so the latest

value of a is 0 now.

After if check execution is completed sysout statement will finally

print the value of a along with the message set.

Hence, the output is The value of a is : 0.

D) More Problem -

Write a Java Program to check the Candidate's eligibility for the Java course.

Given that, Fig 6.3 shows a candidate's eligibility criteria for taking Java-Course.

Consider that the age of a Candidate is 15, the Class is 8, the Course Java is opted of level is 1, and if all the above conditions are as per eligibility criteria, then only the Candidate is eligible for Registration.

![](image_rsrc2XBR.jpg)

public class JavaCourseEligibility_1

{

        public static void main(String[] args)

        {

               int age = 15 ;

               int standard = 8 ;

               String course = "Java" ;

               int level = 1 ;

               boolean registration = false ;

               if(age >= 11)

               {

                     if(age <= 17)

                     {

                           if(standard >= 6)

                           {

                                 if(standard <= 10)

                                 {

                                       if(course == "Java")

                                       {

                                             if(level == 1)

                                             {

                                                   registration = true ;

                                                   if(registration)

                                                   {

                                                            System.out.println("Candidate is eligible to " +

                                                                                                "take Java-Course");

                                                   }

                                             }

                                       }

                                }

                          }

                    }

              }

       }

}

Output:

Candidate is eligible to take Java-Course

Explanation:

In a figure, given the Age of a candidate is 15, the Class studying is 8 and Course-Type mentioned is Java of Level 1.

The Problem statement is we need to check Candidate's eligibility

for Java-Course.

Let's suppose, Age is represented as a variable age of type int, Class

is represented as a variable standard of type int, Course-Type is

represented as a variable course of type int and Level of a Course is

represented as a variable level of type int i.e., age = 15, standard = 8, course = "Java", level = 1.

Now, another variable registration is declared of boolean type and

initialized to false to check a candidate's eligibility for Java-Course.

To check Candidate's eligibility for Java-Course, all conditions are

validated using nested if check.

Firstly, age = 15 is greater than 11 so check passes. Then age = 15 is

smaller than or not equal to 17 so check passes and further

conditions will be validated.

In the third condition, standard = 8 is greater than 6 so the check

passes. Also, standard = 8 is less than 10 so further condition will be

validated.

Further, the course is already "Java" and the level is equal to 1 so

boolean registration is updated to true because all the conditions

are validated are true so the candidate is eligible for the course.

In the last inner if check, since registration is true now so sysout

statement will print the message.

Hence, the output is Candidate is eligible to take Java-Course.

4) The if-else statement:

The if-else statement is an extension to the if-statement, which uses another block of code, i.e., the else block.

The else block is executed if the condition of the if-block is evaluated as false.

The group of statements after the if condition and not including the else block is called an if block. Similarly, the statement after the else forms the else block.

The else is written exactly below the if block.

Had only one statement to be executed in the if block and only one statement in the else block, we can drop the pair of braces.

The general form is as follows...

        if (condition)  

              statement;

        else

              statement;

Working of the if-else Process Flow:

![](image_rsrc2XBS.jpg)

As seen in Fig. 6.4, some conditions must be checked whenever a program is written using the if-else statement.

First, before the if condition, all the statements will be executed.

When the control reaches the if condition, it will check the condition inside the parenthesis as required.

If the condition passes, the statement inside the if block will be executed.

The else block will be skipped as the condition of the if has already passed.

After executing the if block, the statement after the else block will be executed directly.

If the condition inside if fails, the if block will not be executed and the control will reach directly to block else.

All the statements inside the else block will get executed.

Again, if the else block is executed, the statements after the else block will be executed.

Below are a few statements that represent the daily use scenarios. These can be represented using the if-else condition...

1) Mom, what if today's school bus does not come for the pickup? Then Mom answered that if Dad were free, he would drop you off; otherwise, I would drop you off at school.

2) Dad, what if Rohan will beat me in the class? Then Dad says you should complain about it to your teacher; otherwise, Rohan will beat you every other day.

3) The teacher says that if you concentrate on your studies, you will get excellent marks on your exam; otherwise, your principal will scold you.  

4) Golu says that if my dad gives me a mobile, I will learn Coding on his mobile; otherwise, I will do it on my friend's Phone.

5) Nidhi wonders if I can learn Java Programming, then I will build an App; otherwise, I will not be able to.

A) Program Scenarios -

The following are different Program Scenarios...

Scenario 1 (Java Program with or without single if-else Statement) -

// Java Program with Single if-else Statement

public class Scenario_1

{

        public static void main(String[] args)

        {

              // The following conditions will work

              // Example 1

              if(true)

                    System.out.println("Inside if");

              else

                    System.out.println("Inside else");

              // Example 2

              if(false)

                    System.out.println("Inside if");

              else

                    System.out.println("Inside else");

        }

}

// Java Program without any if-else Statement

class Scenario_1_2

{

        public static void main(String[] args)

        {

              // The following Examples will not work

              // Example 1

              if(true)

              else

                    System.out.println("Inside else");

              // Example 2

              if(false)

                    System.out.println("Inside if");

              else

        }

}

Scenario 2 (Java Program for if-else Statement with or without Pair of Braces) -

// Java Program for if-else Statement with Pair of Braces

public class Scenario_2

{

        public static void main(String[] args)

        {

              // The following examples will work

              // Example 1

              if(true)

              {

                    System.out.println("Inside if");

              }

              else

              {

                    System.out.println("Inside else");

              }

              // Example 2

              if(false)

              {

                    System.out.println("Inside if");

              }

              else

              {

                    System.out.println("Inside else");

              }

              // Example 3

              if(true)

              {

                    System.out.println("Inside if");

              }

              else

                    System.out.println("Inside else");

              // Example 4

              if(true)

                    System.out.println("Inside if");

               else

               {

                     System.out.println("Inside else");

               }

         }

}

// Java Program for if-else Statement without Pair of Braces

class Scenario_3_2

{

        public static void main(String[] args)

         {

               // The following examples will also work

               // Example 1

               if(true)

                      System.out.println("Inside if");

               else

                      System.out.println("Inside else");

                // Example 2

                if(false)

                      System.out.println("Inside if");

                else

                      System.out.println("Inside else");

         }

}

Scenario 3 (Java Program for if-else Statement with Statement Terminator) -

// Java Program for if-else Statement with Statement Terminator

public class Scenario_3

{

        public static void main(String[] args)

        {

              // The following examples will work

              // Example 1

              if(true)

              {

                    System.out.println("This is an Example");

              }

              else

              {

                    System.out.println("This is an Example");

              };

              /* The following examples will not work properly as Statement

                   Terminator is used incorrectly */

              // Example 2

              if(true)

              {

                    System.out.println("This is an Example");

              };

              else

              {

                    System.out.println("This is an Example");

              }

               // Example 3

               if(false);

               {

                     System.out.println("This is an Example");

               }

               else

               {

               }

               // Example 4

               if(false);

               {

                     System.out.println("This is an Example");

               }

               else

               {

               }

              // Example 5

               if(false);

               {

                     System.out.println("This is an Example");

               }

               else ;

               {

                     System.out.println("This is an Example");

               }

        }

}

Scenario 4 (Java Program for if-else Statement with System.out.println) -

// Java Program for if-else Statement with System.out.println

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following examples will print output

              // Example 1

              if(true)

              {

                    System.out.println("This is an Example");

              }

              else

              {

                    System.out.println("This is an Example");

              }

              // The following condition will work but not print anything

              // Example 2

              if(true)

                    System.out.println();

               else

                     System.out.println();

           }

}

Scenario 5 (Java Program for if-else Statement with Multiple Java Statements) -

// Java Program for if-else Statement with Multiple Java Statements

public class Scenario_5

{

        public static void main(String[] args)

        {

              // The following examples will work perfectly

              // Example 1

              if(true)

              {

                    int i = 2 ;

                    System.out.println("This is an Example" + i);

              }

              else

              {

                    System.out.println("Inside else Block");

              }

              // Example 2

              if(false)

              {

                   int i ;

                   i = 5;

                   System.out.println("This is an Example" + i);

              }

              else

              {

                    System.out.println("Inside else Block");

              }

        }

}

Scenario 6 (Java Programs for if-else Statement evaluating Expressions) -

// Java Programs for if-else Statement evaluating Expressions

public class Scenario_6

{

        public static void main(String[] args)

        {

              // Example 1

              if(2 == 2)

              {

                    System.out.println("Inside 1st if block");

              }

              else

              {

                    System.out.println("Inside 1st else block");

              }

              // Example 2

              if(2 > 3)

              {

                    System.out.println("Inside 2nd if block");

              }

              else

               {

                    System.out.println("Inside 2nd else block");

              }

              // Example 3

              if(4/2 == 2)

              {

                    System.out.println("Inside 3rd if block");

              }

              else

              {

                    System.out.println("Inside 3rd else block");

              }

              // Example 4

              if(4/2 != 0)

              {

                    System.out.println("Inside 4th if block");

              }

              else

              {

                    System.out.println("Inside 4th if block");

              }

              // Example 5

              if(5*2+1-1 > 1)

              {

                    System.out.println("Inside 5th if block");

              }

             else

             {

                   System.out.println("Inside 5th else block");

             }

             // Example 6

              boolean condition1;

              condition1 = (1 + 2) >= 4;

              if(condition1)

              {

                    System.out.println("Inside 6th if block :" + condition1);

              }

              else

              {

                    System.out.println("Inside 6th else block :" + condition1);

              }

              // Example 7

              boolean condition2;

              condition2 = (1 * 2) > 1;

              if(condition2)

              {

                    System.out.println("Inside 7th if block :" + condition2);

              }

              else

              {

                    System.out.println("Inside 7th else block :" + condition2);

              }

              // Example 8

             Boolean condition3= (4/2) > 1;

             if(condition3)

             {

                   System.out.println("Inside 8th if block :" + condition3);

             }

             else

             {

                    System.out.println("Inside 8th else block :" + condition3);

              }

              // Example 9

              boolean condition4;

              condition4 = (1 - 2) > 4;

               if(condition4)

               {

                     System.out.println("Inside 9th if block :" + condition4);

               }

               else

               {

                     System.out.println("Inside 9th else block :" + condition4);

               }

               // Example 10

               boolean condition5;

               condition5 = (1 + 2) < 4;

               if(condition5)

               {

                     System.out.println("Inside 10th if block :" + condition5);

               }

               else

               {

                     System.out.println("Inside 10th else block :" + condition5);

               }

        }

}

// Java Programs for if-else Statement evaluating wrong Expressions

class Scenario_6_2

{

        public static void main(String[] args)

        {

              // The following example will not work

              // Example 1

              if(2)

              {

                    System.out.println("True");

              }

              else

                    System.out.println("Inside else block");

              // Example 2

              int a = 0 ;

              if(a+2)

                    System.out.println("True");

              else

                    System.out.println("Inside else block");

        }

}

B) Basic Programs -

1) Write a Java Program to check whether a number is Even or Odd.

      Consider a number is 8.

public class EvenOrOddNumberProgram_1

{

        public static void main(String[] args)

        {

              int num = 8 ;

              if(num % 2 == 0)

              {

                    System.out.println(num + " is a Even Number");

              }

              else

              {

                    System.out.println(num + " is a Odd Number");

              }

        }

}

Output:

8 is an Even Number

Explanation:

In this Program, a variable num is declared of type int and initialized with 8.

The Problem statement is to check whether a number is Even or Odd.

In the if check, the condition is validated as num = 8 is a modular

division by 2 is equal to 0\. So, the condition is true, and the if block will be executed.

Inside the if block, the sysout statement will print the value of a

num along with a message.

Hence, the output is 8 is an Even Number.

2) Write a Java Program to check whether a number is Positive or

      Negative. Consider a number is -121.

public class PositiveOrNegativeNumberProgram_2

{

        public static void main(String[] args)

        {

              int num = - 121 ;

              if(num > 0)

              {

                    System.out.println(num + " is a Positive Number");

              }

              else

              {

                    System.out.println(num + " is a Negative Number");

              }

        }

}

Output:

-121 is a Negative Number

Explanation:

This Program declares a variable num of type int and initializes with -121.

The Problem statement is to check whether a number is Positive or Negative.

In the if check, the condition is validated as the num is not positive, so that the condition will be false, and the if block will not be executed.

Therefore, if block is not reachable, the else block sysout statement will print the value of a num along with a message.

Hence, the output is -121 is a Negative Number.

3) Write a Java Program to check whether a number is divisible by a

      11 or not. Consider a number is 87.

public class CheckNumberDivisible_3

{

        public static void main(String[] args)

        {

              int num = 87 ;

              if(num % 11 == 0)

              {

                    System.out.println(num + " is divisible by 11");

              }

              else

              {

                    System.out.println(num + " is not divisible by 11");

              }

        }

}

Output:

87 is not divisible by 11

Explanation:

In this Program, a variable num is declared of type int and initialized with 87.

The Problem statement is to check whether a number is divisible by a number or not.

In the if check, the condition is validated as num is 87, which is not divisible by 11; the condition will be false, and the if block will not

be executed.

Therefore, if block is not reachable, then the else block sysout state-ment will print the value of a num along with a message.

Hence, the output is 87 is not divisible by 11.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int num = 1;

              if((num+1) == (1-num))

              {

                    System.out.println("Equal");

              }

              else

              {

                  System.out.println("Not Equal");

              }

        }

}

Output:

Not Equal

Explanation:

In this problem, variable num is declared of type int and initialized with the value 1.

In the if condition, there are two operations performed. The first is

(num+1), which is 1 is added to num, and the second is num is subt-racted from 1\. So, num+1 equals 1+1 = 2, and (1-num) equals 1-1 = 0.

When (num+1) is compared to (1-num) using == operator i.e., 1 == 0 the condition will be false

Therefore, if the first if check fails, then the else will be executed,

and sysout will print the output.

Hence, the output is Not Equal.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              long num1 = 21;

              Integer num2 = 21;

              if(num1 == num2)

              {

                     System.out.println("Equal");

              }

              else

              {

                    System.out.println("Not Equal");

              }

        }

}

Output:

Equal

Explanation:

In this problem, two variables, num1, and num2, are declared of

type long and Integer, respectively, and initialized with the same

value, i.e., 21.

In the if condition, when num1 is compared to num2 using the ==

operator, the condition will be true as both are equal.

Therefore, if the first check passes, sysout will print the output, and the else statements will not be executed.

Hence, the output is Equal.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int n1 = 21 ;

              int n2;

              if(n2=24 > n1)

              {

                    System.out.println(1);

              }

         }

}

Output:

Error

Explanation:

In this problem, three variables, i, j, and z, are declared of type int,

and i is initialized to 33.

j has not been initialized but assigned to variable z, which is incorr-ect because any variable can only be assigned to another variable

when it has been initialized. Here, the computer needs clarification

and will throw an error.

Hence, there is an Error and no output.

D) More Problem -

Write a Java Program to check whether a Student is eligible for First-Division or not.

Given that, Fig. 6.5 shows the eligibility criteria for a student to be fulfilled to be passed with First-Division.

Consider that Fig. 6.6 shows marks obtained in five subjects. The Student is in Primary School, studying in 11th Grade, and if all the above conditions are as pereligibility criteria, then only the Student is eligible for registration. If registration is completed, the Student is eligible for an exam.

![](image_rsrc2XBT.jpg)![](image_rsrc2XBU.jpg)

public class FirstDivisionEligibleOrNot_2

{

        public static void main(String[] args)

        {

              int english = 61 ;

              int maths = 87 ;

              int science = 52 ;

              int computer = 92 ;

              int social = 71 ;

              String school = "Primary" ;

              int standard = 11 ;

              int sumOfAllSubjectMarks = 0 ;

              int overallPercentage = 0 ;

              boolean registration = false ;

              boolean eligibleForExam = false ;

              boolean checkFirstDivisionEligibility = false ;

              if(school == "Primary")

              {

                    if(standard == 10)

                    {

                          registration = true ;

                          if(registration)

                          {

                                eligibleForExam = true ;

                                if(eligibleForExam)

                                {

                                     sumOfAllSubjectMarks = english + maths + science +

                                                                                           computer + social ;

                                          overallPercentage = (sumOfAllSubjectMarks / 5) * 100 ;

                                     if(overallPercentage >= 60)

                                     {

                                           checkFirstDivisionEligibility = true ;

                                     }

                               }

                        }

                  }

            }

            if(checkFirstDivisionEligibility)

            {

                  System.out.println("Student passed with First-Division");

            }

            else

            {

                  System.out.println("A student is not eligible for First-Division");

            }

        }

}

Output:

A student is not eligible for First-Division

Explanation:

In a given diagram, we have given marks for five subjects i.e., English, Maths, Science, Computer, and Social.

The Problem statement is to find the First Division Eligibility or not.

Let's suppose, each subject is represented by a Java variable of type

int and initialized with english = 61, maths = 87, science = 52,

computer = 92, and social = 71.

Also given, the School of a candidate is Primary, Class studying in

11\. So, both variables can be represented and declared as school =

"Primary" of type String and standard = 11 of type int.

To get the sum of all the subjects and to store the percentage, two

variables have been declared as sumOfAllSubjectMarks and overall-Percentage and both initialized to 0.

Three boolean variables registration, eligibleForExam, and checkFi-rstDivisionEligibility are declared and set to false to keep count to

check the eligibility of a candidate whether Registration is successf-ul, whether the candidate is Eligible for an exam or not and candid-ate eligibility for First Division respectively.

To check the Student's Eligibility for First-Division, all conditions

are validated using nested if check.

In the if check, school = "Primary" is satisfied so the check passes

but standard = 11 is not equal to 10 which indicates that candidate

is not eligible for registration.

Therefore, the value of a variable checkFirstDivisionEligibility is

still false so if the check will fail and else will be executed and the

sysout statement will print the message.

Hence, the output is Student is not Eligible for First Division.

5) The Nested if-else:

It is perfectly all right to write an entire if-else construct within either the body of the if statement or the body of another statement. This is called nesting of ifs.

No limit exists on how deeply the ifs and the else can be nested.

In nested if-statements, the if statement can contain an if or if-else statement inside another if or else-if statement.

The general form is as follows...

        if (condition)  

              if (condition)       

                    statement;

              else

                    statement;

        if (condition)  

              if (condition)       

                    statement;

              else

                    statement;

        else

              statement;

Working of the Nested if-else Process Flow:

![](image_rsrc2XBV.jpg)

As seen in Fig. 6.7, some conditions must be checked whenever a program is written using the nested if conditions are used.

First, before the if condition, all the statements will be executed.

When the control reaches the if condition, it will check the condition inside the parenthesis as required.

If the condition passes, the statement inside the if block will be executed.

Now, if there is another if condition used inside the 1st if check, then the condition inside the 2nd if check will be validated again.

If the condition inside the 2nd if check passes, the statements inside the inner if block will be executed.

If the condition of the inner if check fails, the control will reach directly to the inner else block, corresponding to the 1st if block, to execute its statements if the else block has been used.

If the else for the inner if block is not used, further statements after the inner if-else block will be checked.

If more conditions are put inside after the 1st inner if-else block, those conditions will also be validated.

After executing all the inner statements the control will directly reach the statement after the else block.

If the else block has been used, it will be skipped as the condition of the 1st if check has already passed.

After executing the if block, the statement after the else block will be executed directly.

If the condition inside the 1st if check fails, the if block will not be executed, and the control will reach directly to block else.

All the statements inside the else block will get executed.

Again, if the else block is executed, the statements after the else block will be executed.

Below are a few statements that represent the daily use scenarios. These can be represented using the nested if-else condition...

a) Mom, what if today's school bus does not come for the pickup? Then Mom answers that if Dad is free, he will drop you off, or if I am free, I will drop you off at school.

b) Dad, what if Rohan will beat me in the class? Then Dad says you should go to your teacher and complain about it, or you can go to your Principal to complain about him.

c) The teacher says that if you concentrate on your studies, then you will get excellent marks in your exam; otherwise, your principal will scold you.    

d) Rohan says that if my dad gives me a mobile, then I will learn Coding on his mobile, or I will do it on Mom's Phone.

e) Rohan wonders if I can learn Java Programming and I will practice in mobile. Then, I look forward to building an app.

A) Program Scenarios -

The following are different Program Scenarios...

Scenario 1 (Java Program with Nested if-else Block) -

// Java Program with Nested if-else Block

public class Scenario_1

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

                        System.out.println("Inside 1");

                   if(true)

                        System.out.println("Inside 2");

              else

                    System.out.println("Inside 3");

              // Example 2

              if(true)

                      if(true)

                           System.out.println("Inside 4");

              else

                    System.out.println("Inside 5");

                    if(true)

                           System.out.println("Inside 6");

              // Example 3

              if(true)

                    System.out.println("Inside 7");

              else

                    if(true)

                          System.out.println("Inside 8");

                    else

                          System.out.println("Inside 9");

              // Example 4

              if(true)

                    System.out.println("Inside 10");

              else

                    if(true)

                          System.out.println("Inside 11");

                    else

                          System.out.println("Inside 12");

                    if(true)

                          System.out.println("Inside 13");

                    else

                          System.out.println("Inside 14");

              // Example 5

              if(false)

                    System.out.println("Inside 15");

              else

                    if(false)

                          System.out.println("Inside 16");

                                  if(true)

                                          System.out.println("Inside 17");

                                  else

                                          System.out.println("Inside 18");

                    if(true)

                            System.out.println("Inside 19");

                    else

                         System.out.println("Inside 20");

              // The following Examples will not work

              // Example 6

              if(true)

                          System.out.println("True");

              else

                         else

                              System.out.println("False");

                               if(true)

                                     System.out.println("True");

                               else

                                      if(false)

                                            System.out.println("True");

                                      else

                                            System.out.println("False");

              // Example 7

              if()

                    System.out.println("True");

                            if(true)

                                  System.out.println("True");

                            if(true)

                                  System.out.println("True");

                                  if()

                                        System.out.println("True");

        }

}

Scenario 2 (Java Program for Nested if-else Block with Pair of Braces) -

// Java Program for Nested if-else Block with Pair of Braces

public class Scenario_2

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

              {

                    System.out.println("Inside 1");

                    if(true)

                          System.out.println("Inside 2");

              }

              else

              {

                    System.out.println("Inside 3");

              }

              // Example 2

              if(true)

              {

                    if(true)

                          System.out.println("Inside 4");

              }

              else

              {

                    System.out.println("Inside 5");

                    if(true)

                          System.out.println("Inside 6");

              }

              // Example 3

              if(true)

              {

                    System.out.println("Inside 7");

              }

              else

              {

                    if(true)

                    {

                          System.out.println("Inside 8");

                    }

                    else

                    {

                          System.out.println("Inside 9");

                    }

              }

              // The following Examples will not work

              // Example 4

              if(true)

              {

                    System.out.println("True");

              }

              else

              {

                    else

                          System.out.println("False");

                          if(true)

                                System.out.println("True");

                          else

                                if(false)

                                      System.out.println("True");

                                else

                                      System.out.println("False");

              }

        }

}

Scenario 3 (Java Program for Nested if-else Block with Statement Terminator) -

// Java Program for nested if-else Block with Statement Terminator

public class Scenario_3

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

              {

                    System.out.println("True");

                    if(false)

                          System.out.println("False");

                    else

                    {

                          System.out.println("True");

                    };

              }

              else

              {

                    System.out.println("This is an Example");

              };

              // The following Example will not work

              // Example 2

              if(true);

              {

                    System.out.println("This is an Example");

                    if(false)

                          System.out.println("True");

                          else

                          {

                                System.out.println("False");

                          };

              };

              else

              {

                    System.out.println("This is an Example");

              }

              // Example 3

              if(false);

              {

                    System.out.println("This is an Example");

                    if(false)

                          System.out.println("True");

                    else

                    {

                          System.out.println("False");

                    };

              }

              else

              {

              }

              // Example 4

              if(false);

              {

                    System.out.println("This is an Example");

              }

              else

              {

                    if(false)

                          System.out.println("True");

                    else

                    {

                          System.out.println("False");

                    };

              }

              // Example 5

              if(false);

              {

                    System.out.println("This is an Example");

                    if(false)

                          System.out.println("True");

                    else

                    {

                          System.out.println("False");

                    };

              }

              else ;

              {

                    System.out.println("This is an Example");

              }

        }

}

Scenario 4 (Java Program for Nested if-else Block with System.out.println) -

// Java Program for nested if-else Block with System.out.println

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(true)

              {

                    System.out.println("This is an Example");

              }

              else

              {

                    if(false)

                          System.out.println("True");

                    else

                          System.out.println("False");

                     System.out.println("This is an Example");

               }

        }

}

Scenario 5 (Java Program for Nested if-else Block with Multiple if-else Statements) -

// Java Program for nested if-else Statement with Multiple Java State

ments

public class Scenario_5

{

        public static void main(String[] args)

        {

               // The following Examples will work

               if(true)

               {

                     int a = 0;

                     System.out.println(a);

                     if(a != 0)

                     {

                           System.out.println(false);

                     }

                     else

                     {

                           System.out.println(true);

                     }

              }

        }

}

Scenario 6 (Java Programs for Nested if-else Block evaluating Expressions) -

// Java Programs for nested if-else Statement evaluating Expressions

public class Scenario_6

{

        public static void main(String[] args)

        {

              // The following Examples will work perfectly

              if(true)

              {

                    int a = 0;

                    int b = 1;

                    if(a * b == 0)

                    {

                          System.out.println(true);

                    }

                    else

                    {

                            System.out.println(false);

                    }

              }

        }

}

B) Basic Programs -

1) Write a Java Program to check whether a number is divisible by 30

      or not and is a Even number or not. Consider a number is 90.

public class CheckDivisibleAndEvenProgram_1

{

        public static void main(String[] args)

        {

              int num = 90 ;

              if(num % 30 == 0)

              {

                    if(num % 2 == 0)

                    {

                          System.out.println(num + " is divisible by 30 and is an " +

                                                                    "Even number");

                    }

                    else

                    {

                          System.out.println(num + " is divisible by 30 but not an " +

                                                                     "Even number");

                    }

              }

              else

              {

                    if(num % 2 == 0)

                    {

                          System.out.println(num + " is not divisible by 30 but is an " +

                                                                  "Even number");

                    }

                    else

                    {

                          System.out.println(num + " is not divisible by 30 and also " +

                                                                  "not an Even number");

                    }

              }

        }

}

Output:

90 is divisible by 30 and is an Even number

Explanation:

In this Program, a variable num is declared of type int and initialized with 90.

The Problem statement is to check whether a Number is divisible by 30 or not and is a Even number or not.

In the if check, the condition is validated as num is 90, which is a

modular division by 30 is equal to 0, and the condition will be true, and the if block will be executed.

Next inner first if block condition is validated as num is 90, which is a modular division by 2 is equal to 0 so the condition will be true, and if the block is executed, the statement will print the value of a

num along with a message.

Hence, the output is 90 is divisible by 30 and is an Even number.

2) Write a Java Program to check if a number is negative or not and

      smaller than -5 or not. Consider a number is 90.

public class CheckNegativeAndSmallerToProgram_2

{

        public static void main(String[] args)

        {

              int num = 90 ;

              if(num < 0)

              {

                    if(num < -5)

                    {

                          System.out.println(num + " is a Negative number and "  +

                                                                           "smaller than -5");

                    }

                    else

                    {

                          System.out.println(num + " is a Negative number but not "       

                                                                     + "smaller than -5");

                    }

              }

              else

              {

                     System.out.println(num + " is not a Negative number and "  +

                                                               "also not smaller than -5");

              }

        }

}

Output:

90 is not a Negative number and also not smaller than -5

Explanation:

In this Program, a variable num is declared of type int and initialized with 90.

The Problem statement is to check if a number is negative or not and smaller than -5 or not.

In the if check, the condition is validated as num is 90, which is not a negative number, so the condition is false, and the if block will not be executed.

Therefore, if block is not reachable, then the else block sysout stat-ment will print the value of a num along with a message.

Hence, the output is 90 is not a Negative number and also not

smaller than -5.

3) Write a Java Program to check if a number is greater than 99 and

      consists of 4-Digit number. Consider a number is 100.

public class CheckGreaterThanAndDigitLengthProgram_3

{

        public  static  void main(String[] args)

        {

              int num = 100 ;

              if(num > 99)

              {

                    if(num > 999)

                    {

                          if(num < 10000)

                          {

                                 System.out.println(num + " is greater than 99 and " +

                                                                            "consists of 4-Digit");

                          }

                          else

                          {

                                System.out.println(num + " is greater than 99 and but " +

                                                                         "not consists of 4-Digit");

                          }

                    }

                    else

                    {

                          System.out.println(num + " is greater than 99 but not " +

                                                                    "consists of 4-Digit");

                    }

              }

              else

              {    

                    System.out.println(num + " is not greater than 99");

              }

      }

}

Output:

100 is greater than 99 but not consists of 4-Digit

Explanation:

In this Program, a variable num is declared of type int and initialized with 100.

The Problem statement is to check if a number is greater than 99 and consists of 4-Digit number.

In the if check, the condition is validated as num is 100, greater than 99, so the condition is true, and the if block will be executed.

Further, the condition is checked, but 100 is not greater than 999, so the condition is false and the if block is not executed.

Therefore, if the inner if block is not reachable, the else block sysout statement will print the value of a num along with a message.

Hence, the output is 100 is greater than 99 but not consists of 4-Digit.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              boolean male = false;

              int age = 30;

              if(male)

                    if(age < 20)

                          System.out.println("Boy");

                    else

                           System.out.println("Man");

              else

              {

                    if(age < 20)

                          System.out.println("Girl");

                    else

                          System.out.println("Woman");

              }

        }

}

Output:

Woman

Explanation:

In this problem, a variable male is declared of type boolean and

initialized with a value false.

Also, a variable age is declared of type int and initialized with a

value of 30.

In the first if check, the condition is false because the value of male

is false. So, the statement inside the if check will not be executed,

and the statement inside the else block will be executed.

Inside the else block, since the age is 30, the condition will not be

true as 30 is greater than 20.

Hence, the output will be Woman.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int totalMarks;

              int subject1 = 77 ;

              int subject2 = 87 ;

              int subject3 = 86 ;

              int subject4 = 94 ;

              int subject5 = 66 ;

              totalMarks = subject1 + subject2 + subject3 + subject4 + subject5;

              if(totalMarks <= 500)

              {

                    if(totalMarks > 400)

                    {

                          System.out.println("Above 400 marks");

                    }

                    else

                    {

                          System.out.println("Below 400 marks");

                    }

              }

        }

}

Output:

Above 400 marks

Explanation:

In this problem, five variables are declared for 5 subjects and initial-ized with 77, 87, 86, 94, and 66, respectively.

Total marks are the sum of all the subjects, i.e., totalMarks = 77 + 87 + 86 +94 + 66 = 410.

In the first if check, totalMarks = 410, less than 500\. So, the conditi-on will be true, and the statements inside the if check will be executed.

Now inside if check, totalMarks is again compared and is greater

than 400, so this condition will be true and sysout statement inside inner if check will be executed.

Hence, the output will be Above 400 marks.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              float f = 6.0f;

              double d = 6.0;

              int i = 6;

              if(f == d)

              {

                    if(f == i)

                    {

                          System.out.println("f, d and i are equal");

                    }

                    else

                    {

                          System.out.println("f, d are equal but i is not equal");

                    }

              }

              else

              {

                    System.out.println("f and d are not equal");

              }

      }

}

Output:

f, d and i are equal

Explanation:

In this problem, three variables, f, d, and i, are declared. f is of type

float, d is of type double, and i is of type int.

Also, all the variable has been initialized with a value of 6.0f, 6.0,

and 6 respectively.

In the first if check, the condition is true because the values of f and d are the same when compared to the equality operator.

So, the statement inside if check is executed, and then again, when

f is compared to i, the condition will be true as both are equal to 6,

and the first sysout statement will be executed.

Hence, the output will be f, d, and i are equal.

![](image_rsrc2XBW.jpg)

D) More Problem -

Write a Java Program to check Candidate's Education for Employer-Mindset.

Given that, Fig 6.8 shows the eligibility criteria for a Candidate's employer Mindset.

Consider that the candidate's focus on development, specifically skill development, and mindset, is a growth mindset.   

![](image_rsrc2XBX.jpg)

public class EmployerOrEmployeeMindsetEligibility_3

{

        public static void main(String[] args)

        {

              String focus = "Skill-Development" ;

              String development = "Skill-Development" ;

              String mindset = "Fixed-Mindset" ;

              if(focus == "Skill-Development")

              {

                    mindset = "Growth-Mindset" ;

                    if(mindset == "Growth-Mindset")

                    {

                          System.out.println("Candidate's Education is of " +

                                                                     "Employer-Mindset");

                    }

              }

              if(focus == "Marks")

              {

                    mindset = "Fixed-Mindset" ;

                    if(mindset == "Fixed-Mindset")

                    {

                          System.out.println("Candidate's Education is of " +

                                                                     "Employee-Mindset");

                    }

              }

        }

}

Output:

Candidate's Education is towards Employer-Mindset.

Explanation:

In a figure, given that the Student's Focus is on Marks and the

Mindset is a fixed mindset.

The Problem statement is that we need to check the Candidate's

Education towards the Employer-Mindset.

Let us suppose the Student's Focus is represented as a variable focus of type String, and the Student's mindset is represented as a

variable mindset of type String, i.e., focus = "Marks," and mindset =

"Fixed-Mindset".

To check the Candidate's Education of Employer-Mindset, the first

condition is validated using the if block.

Inside the first if-check, the Student's Focus on Skill-Development is checked. However, as per the given criteria, students focus on

Marks, and then the if check fails, further conditions will be

validated.

Again, the else-if condition will be checked as Focus is on Marks as

per the given condition, and further, if check also verifies whether

the mindset is Fixed-Mindset as per the given condition so the check passes and if block inside else-if block will be executed and sysout

statement will print the message.

Hence, the output of the Candidate's Education is not towards the

employer mindset.

6) The else if Clause:

The else-if statement is used when there is more than one else condition.

The else-if clause is nothing different; it just rearranges the else with the if that follows it.

The statement of else-if is written inside an else-if block after the else-if condition to be evaluated.

The else-if condition must contain values to be evaluated as a boolean.

Using Parenthesis for else-if block is optional.

In a Program, there can be only one else-if block or multiple else-if blocks, depending on the conditions.

The general form is as follows...

        if(condition)         

              statement;

        else if(condition)

              statement;

Working of the else-if Process Flow:

![](image_rsrc2XBY.jpg)

As seen in Fig. 6.9, some conditions must be checked whenever a program is written using the if and else if statement.

First, before the if condition, all the statements will be executed.

When the control reaches the if condition, it will check the condition inside the parenthesis as required.

If the condition passes, the statement inside the if block will be executed.

All other else-if blocks will be skipped as the if condition has already passed.

After executing the if block, all statements after the last else-if block will be executed directly.

If the condition inside if fails, the if block will not be executed, and the control will reach directly to the first else-if block.

Now, the condition of the first else-if check will be validated.

If the condition inside the first else-if check passes, the statement inside that block will be executed.

Suppose the condition inside the first else-if fails. In that case, the further else-if conditions will be validated one by one if it has been used.

If any particular else-if condition passes, that specific else-if block will be executed, and all other blocks will be skipped.

Again, here, all the statements after the last else-if block will get executed.

Below are a few statements that represent the daily use scenarios. These can be represented using the Logical Operator...

a) Mom, what if today's school bus does not come for the pickup? Then Mom answered that if Dad were free, he would drop you off; otherwise, I would drop you off at school.

b) Dad, what if Rohan will beat me in the class? Then Dad says you should complain about it to your teacher; otherwise, Rohan will beat you every other day.

c) The teacher says that if you concentrate on your studies, you will get excellent marks on your exam; otherwise, your principal will scold you.  

d) Golu says that if my dad gives me a mobile, I will learn Coding on his mobile; otherwise, I will do it on my friend's Phone.

e) Nidhi wonders if I can learn Java Programming, then I will build an App; otherwise, I will not be able to.

A) Program Scenarios -

The following are different Program Scenarios...

Scenario 1 (Java Program with else-if Block) -

// Java Program with else-if Block

public class Scenario_1

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(false)

                    System.out.println("Inside 1");

              else if(true)

                    System.out.println("Inside 2");

              // Example 2

              if(false)

                    System.out.println("Inside 3");

              else if(false)

                    System.out.println("Inside 4");

              else if(true)

                    System.out.println("Inside 5");

              // Example 3

              if(false)

                    System.out.println("Inside 6");

              else if(false)

                    System.out.println("Inside 7");

               if(false)

                    System.out.println("Inside 8");

               else if(false)

                    System.out.println("Inside 9");

               else if(true)

                    System.out.println("Inside 10");

               // The following Examples will not work

              // Example 4

              if(true)

              else if(true)

              System.out.println("True");

               // Example 5

               if(false)

               System.out.println("False");

               else (true)

                     System.out.println("True");

               // Example 6

               if(false)

                     System.out.println("False");

               else if

                     System.out.println("True");

                // Example 7

                if(false)

                      System.out.println("False");

                else if()

                      System.out.println("True");

         }

}

Scenario 2 (Java Program with Single if Statement) -

// Java Program for Nested else-if Block with Pair of Braces

public class Scenario_2

{

        public static void main(String[] args)

        {

              // The following Examples will work

              if(true)

              {

                    System.out.println("True");

              }

              else

              {

                    if(true)

                    {

                          System.out.println("True");

                    }

                    else

                    {

                          System.out.println("False");

                    }

                    if(true)

                          System.out.println("True");

              }

        }

}

Scenario 3 (Java Program for if Statement with or without Pair of Braces) -

// Java Program for nested else-if Block with Statement Terminator

public class Scenario_3

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              if(false)

              {

                    System.out.println("False");

              }

             else if(true)

             {

                   System.out.println("True");

             }

             // The following Examples will not work

             // Example 2

             if(false);

             {

                   System.out.println("False");

             }

             else if(true)

             {

                   System.out.println("True");

             }

             // Example 3        

             if(false)

             {

                   System.out.println("False");

             };

             else if(true)

             {

                   System.out.println("True");

             }

              // Example 4

              if(false);

              {

                    System.out.println("False");

              }

              else if(true);

              {

                    System.out.println("True");

              }

        }

}

// Java Program for nested else-if Block without Statement Terminator

class Scenario_3_2

{

        public static void main(String[] args)

        {

              // The following Examples will give an error

              // Example 1

              if(false)

              {

                    System.out.println("False")

              }

              else if(true)

              {

                    System.out.println("True")

              }

        }

}

Scenario 4 (Java Program for if Statement with or without Statement Terminator) -

***

// Java Program for nested else-if Block with System.out.println

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following Examples will work perfectly

             // Example 1

             if(true)

             {

                   System.out.println("True");

             }

             else if(true)

             {

                   System.out.println("True");

              }

        }

}

// Java Program for nested else-if Block without System.out.println

class Scenario_4_2

{

        public static void main(String[] args)

        {

              // The following Examples will work but not provide any output

              // Example 1

              if(true)

              {

               }

              else if(true)

              {

              }

        }

}

Scenario 5 (Java Program for if Statement with System.out.println) -

/* Java Program for nested if-else Statement with Multiple Java

     Statements */

public class Scenario_5

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              int a = 0;

              if(a !=0)

              {

                    System.out.println(a);

              }

              else if(a ==0)

              {

                    a = 1;

                    System.out.println(a);

              }

        }

}

Scenario 6 (Java Program for if Statement with Multiple Java Statements) -

// Java Programs for nested if-else Statement evaluating Expressions

public class Scenario_6

{

      public static void main(String[] args)

      {

             // The following Examples will work perfectly

             int a = 0;

             int b = 1;

             if(a * b !=0)

             {

                   System.out.println("Inside if block");

             }

             else if(a * b == 0)

             {

                   System.out.println("Inside else-if block");

             }

        }

}

B) Basic Programs -

1) Write a Java Program to check whether a number is Even or Odd.

      Consider a number is 8\. Consider a number is 8.

public class EvenOrOddNumberProgram_1

{

        public static void main(String[] args)

        {

              int num = 8 ;

              if(num % 2 == 0)

              {

                    System.out.println(num + " is a Even Number");

              }

              else if(num % 2 != 0)

              {

                    System.out.println(num + " is a Odd Number");

              }

        }

}

Output:

8 is a Even Number

Explanation:

In this program, a variable num is declared of type int and initialized with 8.

The Problem statement is to check whether a number is Even or Odd.

In the if check, the condition is validated as num is 8, a modular

division by 2 equal to 0, and the condition will be true, and the if

block will be executed.

Hence, the output is 8 is an Even Number.

2) Write a Java Program to check whether a number is Positive or

      Negative. Consider a number is -121\. Consider a number is -121.

public class PositiveOrNegativeNumberProgram_2

{

        public static void main(String[] args)

        {

              int num = - 121 ;

              if(num > 0)

              {

                    System.out.println(num + " is a Positive Number");

              }

              else if(num < 0)

              {

                    System.out.println(num + " is a Negative Number");

              }

        }

}

Output:

-121 is a Negative Number

Explanation:

This program declares a variable num of type int and initializes with -121.

The Problem statement is to check whether a number is Positive or Negative.

In the if check, the condition is validated as num is -121, which is

not a positive number, so the condition is false, and the if block will not be executed.

Therefore, the if block is not reachable, then the else-if condition is checked here, and since num is a negative number, that fulfills the

condition so the sysout statement will print the value of a num

along with a message.

Hence, the output is -121 is a Negative Number.

3) Write a Java Program to check whether a number is divisible by a

      30 or not. Consider a number is 90.

public class CheckDivisibleAndEvenProgram_3

{

        public static void main(String[] args)

        {

              int num = 90 ;

              if(num % 30 == 0)

              {

                    if(num % 2 == 0)

                    {

                          System.out.println(num + " is divisible by 30 and is an " +

                                                                       "Even number");

                    }

                    else if(num % 2 != 0)

                    {

                       System.out.println(num + " is divisible by 30 but not an " +

                                                                    "Even number");

                    }

              }

              else if(num % 30 != 0)

              {

                    if(num % 2 == 0)

                    {

                         System.out.println(num + " is not divisible by 30 but is " +

                                                                       "an Even number");

                    }

                    else

                    {

                        System.out.println(num + " is not divisible by 30 and " +

                                                                     "also not an Even number");

                    }

              }

        }

}

Output:

90 is divisible by 30 and is an Even number

Explanation:

In this program, a variable num is declared of type int and initialized with 90.

The Problem statement is to check whether a number is divisible by 30 or not and is an Even number or not.

In the if check, the condition is validated as num is 90, which is

modular division by 30 equals 0, so the condition is true, and the if block will not be executed.

Further, the condition is checked that 90 on modular division by 2

is equal to 0, so the condition is true, and the first inner if block will be executed.

sysout statement will print the value of a num along with a message.

Hence, the output is 90 is divisible by 30 and is an Even number.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              String laptop = "Dell" ;

              if(laptop == "HP")

              {

                    System.out.println("Inside 1st Block");

              }

              else if(laptop == "Lenovo")

              {

                    System.out.println("Inside 2nd Block");

              }

              else if(laptop == "Dell")

              {

                    System.out.println("Inside 3rd Block");

              }

              else

              {

                    System.out.println("Inside 4th Block");

              }

        }

}

Output:

Inside 3rd Block

Explanation:

In this problem, a variable laptop is declared of type String and is

initialized to "Dell".

In the first if check, the condition is false because laptop = "Dell" is

not equal to "HP" when compared by the equality operator, and then the first else-if block will be checked.

In the first else-if check, the condition is again false because laptop = "Dell" is not equal to "Lenovo" when compared to equality operator and then the second else-if block will be checked.

In the second else-if check, the condition is true because laptop =

"Dell" is equal to "Dell" when compared by equality operator, and the sysout statement inside this check will be executed.

Hence, the output will be Inside 3rd Block.

Problem 2 -   

public class Problem_2

{

        public static void main(String[] args)

        {

              int age = 19 ;

              if(age > 18)

              {

                    System.out.println(1);

                    if(age == 21)

                    {

                          System.out.println(2);

                    }

                    if(age == 17)

                    {

                          System.out.println(3);

                    }

                    else

                    {

                          System.out.println(4);

                    }

              }

        }

}

Output:

1

Explanation:

In this problem, a variable age is declared of type int and is initialized to 19.

In the if check, the condition is true because age = 19 is greater than 18 when compared by the equality operator, and the if block will be checked further.

Inside the if block, the first statement is sysout, which will be execu-ted and no further block  will be checked.

Hence, the output will be 1.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int age = 9 ;

              System.out.println(0);

              if(age % 2 == 0)

              {

                    System.out.println(1);

              }

              else if(age % 5 == 0)

              {

                    System.out.println(2);

              }

              else if(age % 7 == 0)

              {

                    System.out.println(3);

              }

             else

             {

                   System.out.println(4);

             }

        }

}

Output:

0

4

Explanation:

In this problem, a variable age is declared of type int and is initialized to 9.

At first, the sysout statement will be executed.

In the first if check, the condition is false because 9 % 2 is not equal to 0 when compared by the equality operator and the further else-if block will be checked.

Similarly, the first else-if condition is false because 9 % 5 is not

equal to 0 when compared by the equality operator and the further else-if block will be checked.

The second else-if condition is again false because 9 % 7 is not equal to 0 when compared by the equality operator and the further block will be checked.

Finally, the else block will be executed, and the sysout statement

will be printed.

Hence, the output will be 0 and 4.

D) More Problem -

Write a Java Program to check whether the Candidate is eligible for the course or not.

Given that, Fig 6.10 shows the different eligibility criteria for a Candidate to be eligible for the course.

***

Consider that the age of a Candidate is 19, the Class is 12, the Course Java is opted of level is 2, and if all the above conditions are as per eligibility criteria, then only the Candidate is eligible for Registration.

![](image_rsrc2XBZ.jpg)

public class JavaCourseTypeEligibility_1

{

        public static void main(String[] args)

        {

              int age = 19 ;

              int standard = 12 ;

              String course = "Java" ;

              int level = 2 ;

              boolean registration = false ;

              if(age <= 17)

              {

                    if(age >= 11)

                    {

                          if(standard >= 6)

                          {

                                if(standard <= 10)

                                {

                                      if(course == "Java")

                                      {

                                            if(level == 1)

                                            {

                                                  registration = true ;

                                                  if(registration)

                                                  {

                                                        System.out.println("Candidate is Eligible " +

                                                                                  "to take Java Beginner Course " +

                                                                                  "executed in if check");

                                                  }

                                            }

                                      }

                                 }

                          }

                    }

              }

              else if(age <= 20)

              {

                    if(age >= 18)

                    {

                          if(standard >= 11)

                          {

                                if(standard <= 12)

                                {

                                      if(course == "Java")

                                      {

                                            if(level == 2)

                                            {

                                                  registration = true ;

                                                  if(registration)

                                                  {

                                                        System.out.println("Candidate is Eligible " +

                                                                         "to take Java Intermediate Course " +

                                                                         "executed in 1st else if check");

                                                  }

                                            }

                                      }

                                }

                          }

                    }

              }

              else if(age >= 21)

             {

                   if(standard > 12)

                   {

                         if(course == "Java")

                         {

                                if(level == 3)

                                {

                                      registration = true ;

                                      if(registration)

                                      {

                                            System.out.println("Candidate is Eligible to take "       

                                                                                  + Java Advanced Course "

                                                                                     + "executed in 2nd else if check");

                                      }

                                }

                          }

                    }

              }

        }

}

Output:

A candidate is Eligible to take Java Intermediate Course executed in 1st else if check

Explanation:

In a figure, given the Age of a candidate is 19, the Class studying is 812 and Course-Type mentioned is Java of Level 2.

The Problem statement is we need to check Candidate's eligibility

for Java-Course.

Let's suppose, Age is represented as a variable age of type int, Class

is represented as a variable standard of type int, Course-Type is rep-resented as a variable course of type int and Level of a Course is rep-resented as a variable level of type int i.e., age = 19, standard = 12,

course = "Java", level = 2.

Now, another variable registration is declared of boolean type and

initialized to false to check for the registration is successful or not.

To check Candidate's eligibility for Java-Course, all conditions are

validated using nested if and else if blocks.

In the if check, age = 19 is greater than 17 so the check fails and

further conditions will not be validated and the flow will go

directly to the first else-if block.

In the first else-if condition, age = 19 is less than 20 so the check

passes. Then age = 19 is greater than 19 so check passe and further

conditions will be validated.

In the third condition, standard = 12 is greater than 11 so the check passes. Also, standard = 12 is equal to 12 so the further condition

will be validated.

Further, the course is already "Java" and the level is equal to 2 so

boolean registration is updated to true because all the conditions

validated are true so the candidate is eligible for the course.

In the last inner check, since registration is true now so sysout

statement will print the message.

Hence, the output is Candidate is Eligible to take Java Intermediate Course.

7) The  Logical Operator:

Java allows the usage of three logical operators, namely &&, ||, and !. These will be used as AND, OR, and NOT.

Symbols are composed of double symbols.

Do not use single symbols | and &. These single symbols also have a meaning.

They are also called bitwise operators.

The first operators, && and ||, allow two or more conditions to be combined in an if statement.

The third logical operator is the NOT operator written as !.

This operator reverses the result of the expression it operates on.

The NOT operator is often used to reverse the logical value of a single boolean variable.

The general form is as follows...

        if(condition1 && condition2)         

              statement;

        if(condition1 || condition2)         

              statement;

        if(!condition)         

               statement;

Working of the Logical Operator Process Flow:

Some conditions must be checked whenever a program is written using the Logical Operator.

First, before the if condition, all the statements will be executed.

When the control reaches the if condition, it will check the condition inside the Parenthesis as required.

If the condition passes, the statement inside the if block will be executed.

There may be several conditions used inside Parenthesis using logical operators.

All those conditions will be validated one by one. If, as per the operator used, the if condition is true, then the if block will get executed.

If the else block is not used, further statements after the if block will be checked.

If the else block has been used, it will be skipped as the condition of the if check has already passed.

After executing the if block, the statement after the else block will be executed directly.

A) Program Scenarios -

Scenario 1 (Java Scenario to demonstrate the use of ! operator) -

// Java Scenario to demonstrate the use of ! operator

public class Scenario_1

{

        public static void main(String[] args)

        {

              // Example 1

              if(!true)

              {

                    System.out.println(1);

              }

              // Example 2

              if(!false)

              {

                    System.out.println(2);

              }

              // Example 3

              boolean b = true ;

               if(!b)

               {

                     System.out.println(3);

               }

               // Example 4

               boolean check = true ;

               if(check)

               {

                     System.out.println(!check);

               }

        }

}

Scenario 2 (Java Scenario to demonstrate the use of && operator) -

// Java Scenario to demonstrate the use of && operator

public class Scenario_2

{

        public static void main(String[] args)

        {

              // Example 1

              if(true && true)

              {

                    System.out.println(1);

              }

              // Example 2

              if(false && false)

              {

                    System.out.println(2);

              }

              // Example 3

              boolean b = true ;

              if(true && b)

              {

                    System.out.println(3);

              }

        }

}

Scenario 3 (Java Scenario to demonstrate the use of || operator) - 

// Java Scenario to demonstrate the use of || operator

public class Scenario_3

{

        public static void main(String[] args)

        {

              // Example 1

              if(true || false)

              {

                    System.out.println(1);

              }

              // Example 2

              if(false || false)

              {

                    System.out.println(2);

              }

              // Example 3

              boolean b = true ;

              if(false || b)

              {

                    System.out.println(3);

              }

              // Example 4

              boolean check = true ;

              if(check || false)

              {

                    System.out.println(!check);

              }

        }

}

Scenario 4 (Java Scenario to demonstrate the use of all conditional

operators) -

// Java Scenario to demonstrate the use of all conditional operators

public class Scenario_4

{

        public static void main(String[] args)

        {

              // Example 1

              if((false || !false) && true)

              {

                    System.out.println(1);

              }

              // Example 2

              if((false && !false) || true)

              {

                    System.out.println(2);

              }

              // Example 3

              boolean b = true ;

              if((false && !false) || b)

              {

                    System.out.println(3);

              }

              // Example 4

              boolean check = true ;

              if((true && !false) || check)

              {

                    System.out.println(!check);

              }

        }

}

B) Basic Programs -

1) Write a Java Program to check whether a number is divisible by 30

      or not and is a Even number or not. Consider a number is 130.

public class CheckDivisibleAndEvenProgram_1

{

        public static void main(String[] args)

        {

              int num = 130 ;

              if(num % 30 == 0 && num % 2 == 0)

              {

                    System.out.println(num + " is divisible by 30 and is an " +

                                                              "Even number");

              }

              else if((num % 30 == 0 && !(num % 2 == 0)))

              {

                    System.out.println(num + " is divisible by 30 but not an " +

                                                               "Even number");

              }

              else if((num % 30 != 0 && num % 2 == 0))

              {

                    System.out.println(num + " is not divisible by 30 but is " +

                                                             "an Even number");

              }

        }

}

Output:

130 is not divisible by 30 but is an Even number

Explanation:

In this program, a variable num is declared of type int and initialized with 130.

The Problem statement is to check whether a number is divisible by 30 or not and is a Even number or not.

In the first if check, the condition is validated as num is 30, which is a modular division by 30 is not equal to 0, and a modular division

by 2 is equal to 0, so one of the conditions is false, so if block will not be executed.

In the first if check, the condition is validated as num is 30, which is a modular division by 30 is not equal to 0, and a modular division

by 2 equals 0, so one of the conditions is false, so if block will not be executed.

Inside the first else-if block, again, the condition is validated. num is 30, which is a modular division by 30 is not equal to 0, and a modul-ar division by 2 is equal to 0, but NOT of true is false, so here, both

the conditions are false, and the first else-if block will not be executed.

Inside the second else-if block, the condition is validated. num is 30, a modular division by 30 is not equal to 0, which is true, and a

modular division by 2 is equal to 0, which is also true, so here both

the conditions are true; the second else-if block will be executed.

sysout statement will print the value of a num along with a message.

Hence, the output is 130 is not divisible by 30 but is an Even number.

2) Write a Java Program to check if a number is divisible by 3 and an

      odd number or consists of a 4-digit number. Consider a number is

      999.

public class CheckDivisibleAndOddAndConsistsOf4DigitProgram_2

{

        public static void main(String[] args)

        {

              int num = 999 ;

              if((num % 3 == 0 && num % 2 != 0) ||

                                                                                   (num > 999 && num < 10000))

              {

                    System.out.println(num + " is either divisible by 3 and an " +

                                                                         "odd number or consists of 4-Digit");

              }

              else

              {

                    System.out.println(num + " is neither divisible by 3 and an " +

                                                                        "odd number nor consists of 4-Digit");

              }

        }

}

Output:

999 is either divisible by 3 and an odd number or consists of 4-Digit

Explanation:

In this Program, a variable num is declared of type int and initialized with 999.

The Problem statement is to check if a number is divisible by 3 and an odd number or consists of a 4-digit number.

In the if check, different conditions are there.

The first parenthesis will be validated as num is 999 on modular division by 3 is equal to 0 and also on modular division by 3 is not equal to 0, so here both condition is true.

In the second parenthesis, num = 999 does not consist of 4-Digit, so this condition is false.

However, OR conditional operator is used, so any of the conditions has to be true to execute the if block.

else block will be skipped, and the sysout statement of the if block will print the value of a num along with a message.

Hence, the output is 999 is either divisible by 3 and an odd number or consists of 4-Digit.

3) Write a Java Program to check whether an Alphabet is a Vowel or

      Consonant. Consider a charcater  is 'S'.

public class VowelOrConsonantAlphabetProgram_3

{

        public static void main(String[] args)

        {

              char c = 'S' ;

              if(c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U')

              {

                    System.out.println(c + " is a Vowel");

              }

              else

              {

                    System.out.println(c + " is a Consonant");

              }

        }

}

Output:

S is a Consonant

Explanation:

In this Program, a variable c is declared and initialized with a value 'S'.

The Problem statement is to check whether an Alphabet is a Vowel or Consonant.

In the if check, different conditions are validated.

Since any of the comparisons is not equal to 'S', c is not a vowel, and else block will be executed.

Hence, the output will be S is a Consonant.

C) Output Problems -

public class Problem_1

{

        public static void main(String[] args)

        {

              Integer num1 = 21;

              Integer num2 = 21;

              if(num1 != num2)

              {

                    System.out.println(num1 + " and " + num2 + " are equal");

              }

        }

}

Output:

No output

Explanation:

In this problem, two variables, num1 and num2, are declared of

type Integer, and both are initialized with 21.

In the if check, the condition is false because num1 = 21 equals

num2 = 21 when compared by the != operator.

So, the condition is false, and the sysout statement will not be executed.

Hence, the output will be nothing.

public class Problem_2

{

        public static void main(String[] args)

        {

              String message = "Shine N Rise" ;

              if(!(message == "Shine n Rise"))

              {

                    System.out.println("True");

              }

        }

}

Output:

True

Explanation:

In this problem, the variable message is declared of type String and

initialized with "Shine N Rise".

In the if check, message = "Shine N Rise" is compared to

"Shine n Rise" which results in false.

Now, !(false), i.e., NOT of false is true so if condition will be true.

So, the condition is true, and the sysout statement will be executed.

Hence, the output will be True.

public class Problem_5

{

        public static void main(String[] args)

        {

              int num1=23, num2=7, num3=43, num4=23;

              if(num1 > num2 || num3 == num4)

                    System.out.println("One or both the conditions are true");

              else

                    System.out.println("Both conditions are false");

        }

}

Output:

One or both the conditions are true

Explanation:

In this problem, four variables, num1, num2, num3, and num4, are declared of type of type int.

num1 is initialized to 23, num2 is initialized to 7, num3 is initialize-d to 43 and num4 is initialized to 23.

Inside the if condition, there are two conditions, which are num1=

23 is greater than num2=7, i.e., true, and num3=43 is not equal to

num4=23, i.e., false.

Finally, true || false is ultimately true, and the sysout statement will be executed.

Hence, the output will be One or both the conditions are true.

D) More Problem -

Write a Java Program to check whether a Student is eligible for First-Division or not.

Given that, Fig 6.11 shows the eligibility criteria for a student to be

fulfilled to be passed with First-Division.

***

Consider that Fig. 6.12 shows marks obtained in five subjects. The

Student is in Primary School, studying in 10th Grade, and if all the

above conditions are as per eligibility criteria, then only the Student is eligible for registration. If registration is completed, the Student

is eligible for an exam.

![](image_rsrc2XC0.jpg)![](image_rsrc2XC1.jpg)

public class DivisionTypeEligiblity_2

{

        public static void main(String[] args)

        {

              int english = 55 ;

              int maths = 66 ;

              int science = 55 ;

              int computer = 39 ;

                    int social = 22 ;

                    String school = "Primary" ;

                    int standard = 10 ;

                    int sumOfAllSubjectMarks = 0 ;

                    int overallPercentage = 0 ;

                    boolean registration = false ;

                    boolean eligibleForExam = false ;

                    if(school == "Primary" && standard == 10 && registration

                                    && eligibleForExam)

                    {

                          sumOfAllSubjectMarks = english + maths + science + co

                                                                                mputer + social ;

                               overallPercentage = (sumOfAllSubjectMarks * 100) / 500 ;

                          if(overallPercentage >= 60)

                          {

                                System.out.println("Student passed with First-Division" +

                                                                       "executed in inner if block");

                          }

                           else if(overallPercentage < 60 && overallPercent

                                               age >= 33)

                           {

                                  System.out.println("Student passed with " +

                                                     "Second-Division executed in 1st else-if block");

                           }

                           else if(overallPercentage < 33)

                           {

                                 System.out.println("Student fail with Third-Division " +

                                                                          "executed in 2nd else-if block");

                     }

              }

        }

}

Output:

A student passed with Second-Division executed in 1st else-if block

Explanation:

In a given diagram, we have given marks for five subjects i.e.,

English, Maths, Science, Computer, and Social.

Let's suppose, each subject is represented by Java variables of type

int and initialized with english = 55, maths = 66, science = 55,

computer = 39, and social = 22.

Also given, the School of a candidate is Primary, Class studying in

10\. So, both variables can be represented and declared as school =

"Primary" and standard = 10.

Two boolean variables registration and eligibleForExam are declare-d and set to false to keep count to check the eligibility of a candidate whether Registration is successful and candidate is Eligible for an

exam or not respectively.

To check the Student's Eligibility for Second Division, all conditions are validated using a nested if and else-if block using a conditional operator.

Firstly, school = "Primary" is satisfied so check passes. Then standar-d = 10 is equal to 10 which indicates that the candidate is eligible

for registration. Therefore, the value of a variable registration has

been updated to true.

Now, if the student is already eligible so the Eligibility check will

pass and the sum of all subject marks and Percentages will be calculated further.

To calculate the Total Marks obtained by a student, just add all the marks of all the subjects and update in a variable totalMarks i.e,

sumOfAllSubjectMarks = 55 + 66 + 55 + 39 + 22 = 237.

Similarly, the Total percentage obtained by a student is calculated

and updated in a variable overallPercentage i.e, overallPercentage = (163 * 100) / 500 = 47.4.

Since overallPercentage not greater than or equal to 60 so the first if condition will fail and the flow will go to the first else-if block to

check the condition. Here, overallPercentage is less than 60 and greater than 33 so both condition satisfies so the check will pass and  

the sysout statement will print the message.

Hence, the output is Student passed with Second-Division executed in 1st else-if block.

8) The conditional operators:

The conditional operators ? and : are sometimes called ternary operators since they take three arguments.

They are represented as if-then-else.

This expression says: "if expression 1 is true, then the value returned will be the result of expression 2\. otherwise, the value returned will be a result of expression 3".

The conditional operators can be nested.

The limitation of the conditional operators is that only the Java statement can occur after the ? or after the :.

The general form is as follows...

        any_data_types variable = if(condition) ? statement 1 : statement 2 ;

Working of the Conditional Operator Process Flow:

Some conditions must be checked whenever a program is written using the Conditional Operator.

Here, validation is done using two operators, i.e., ? and : in the form of if-then-else.

So, the above if-else form can also be represented by the conditional operator, but here, the format is different.

In this format, the conditions are validated on RHS and stored the result on LHS in the form of a variable, either String, boolean, or any other data type as per requirement.

In RHS, we keep the if condition part before ? and all statements on RHS of ? gets executed if the condition passes.

If the condition before ? fails, the else condition will be executed, which is present on RHS of :.

Suppose there is more than one condition to be validated. In that case, all those conditions can be checked as per the nesting of if-else, or different conditions can be combined using logical operators we have done before.

Below are a few statements that represent real-life scenarios. These can be represented using the if condition...

***

a) Mom, what if today's school bus does not come for the pickup? Then Mom answered that Dad would drop you at school.

b) Dad, what if my classmate has beaten me in the class? Then Dad says that you should go to your teacher and complain about it. c) The teacher says that if you concentrate on your studies, you will get excellent marks in your exam.   

d) Golu says that if my Dad gives me a mobile, I will learn Coding.

e) Nidhi wonders if I can learn Java Programming then my goal is to build an App.

A) Program Scenario -

The following are different Program Scenarios...

Scenario (Java Scenario to demonstrate the use of logical operator) -

// Java Scenario to demonstrate the use of logical operator

public class Scenario

{

        public static void main(String[] args)

        {

              // The following Program will work

              // Example 1

              String s = true ? "Yes" : "No" ;

              System.out.println(s);

              // Example 2

              boolean b = true ? true : false ;

              System.out.println(b);

               // Example 3

               boolean check = false ? true : false ;

               System.out.println(check);

               // Example 4

               int i = true ? 1 : 0 ;

               System.out.println(i);

               // Example 5

               int ii = (true || false) ? 1 : 0 ;

               System.out.println(i);

              // The following Program will not work

              // Example 6

              boolean bb = true : true ? false ;

              System.out.println(bb);

              // Example 7

              boolean b3 = true ? true ;

              // Example 8

              boolean b4 = true : true ;

        }

}

B) Basic Programs -

1) Write a Java Program to check whether a number is Even or Odd.

public class EvenOrOddNumberProgram_1

{

        public static void main(String[] args)

        {

              int num = 8 ;

              String evenOrOdd = (num%2 == 0) ? "Even" : "Odd" ;

              System.out.println(num + " is an " + evenOrOdd + " Number");

        }

}

Output:

8 is an Even Number

Explanation:

In this program, a variable num is declared of type int and initialized with 8.

The Problem statement is to check whether a number is Even or Odd.

Variable evenOrOdd is declared and contains a value that will result from the Ternary operations in RHS.

In RHS, num on modular division by 2 is 0, so the first condition

will be stored to a String evenOrOdd, i.e., evenOrOdd = "Even".

Hence, the output is 8 is an Even Number.

2) Write a Java Program to check whether a number is Positive or

      Negative.

public class PositiveOrNegativeNumberProgram_2

{

        public static void  String[] args)

        {

              int num = -8 ;

              String postiveOrNegative = num > 0 ? "Positive" : "Negative" ;

              System.out.println(num + " is a " +

                                                                          postiveOrNegative + " Number");

        }

}

Output:

-8 is a Negative Number

Explanation:

This program declares a variable num of type int and initializes with -8.

The Problem statement is to check whether a number is Positive or Negative.

Variable postiveOrNegative is declared and contains a value that will result from the Ternary operations in RHS.

In RHS, a num is a negative number so that the first condition will not be true, and the second condition will store the value in the variable postiveOrNegative i.e., postiveOrNegative = "Negative".

Hence, the output is -8 is a Negative Number.

3) Write a Java Program to check whether a number is divisible by 30

      and is an Even number or either of any one condition.

public class CheckDivisibleAndEvenProgram_3

{

        public static void main(String[] args)

        {

              int num = 90 ;

              boolean check = (num % 30 == 0 && num % 2 == 0) ? true : fa

                                                     lse ;

               if(check)

              {

                    System.out.println(num + " is divisible by 30 and is an " +

                                                              "Even number");

              }

               else if(num % 30 == 0 || num % 2 == 0)

               {

                     System.out.println(num + " is either divisible by 30 or " +

                                                               "is an Even number");

               }

        }

}

Output:

90 is divisible by 30 and is an Even number

Explanation:

In this Program, two variables, num, and check, are declared of type int and boolean, respectively.

The Problem statement is to check whether a number is divisible by 30 and is an Even number or either of any one condition.

Variable num is initialized with 90, and the check contains the

result of the Ternary operations in RHS.

In RHS, num on modular division by 30 and 2 is 0, so the first condi-tion will be true and store the value in the variable check, i.e., check = true.

Therefore, if the check is true, the if condition will be true, and the

if block will be executed and print the sysout statement along with a message.

Hence, the output is 90 is divisible by 30 and is an Even number.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int percentage = 66 ;

              String result = (percentage > 60) ? "First Division" :

                                                                                                        "Not a First Division";

              System.out.println(result);

        }

}

Output:

First Division

Explanation:

In this problem, a variable percentage is declared of type int and initialized to 66.

Another variable, result, is declared of type String and updated by

the result of an expression.

In the expression part, percentage = 66, which is greater than 60, so the first string, i.e., "First Division" will be assigned to a variable

result, and the sysout statement will print the value of the same variable.

Hence, the output is First Division.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int marks = 23 ;

              System.out.println((marks > 33) ? "Pass" : "Fail");

        }

}

Output:

Fail

Explanation:

In this problem, a variable marks is declared of type int and initialized to 23.

In the sysout statement, the expression part is evaluated, marks = 23, smaller than 33, so the first string after ? mark will be false, and

the string after : i.e., "Fail" will be printed.

Hence, the output is Fail.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int x,y;

              x = 21;

              y = (x > 1) ? 211 : 210 ;

              System.out.println("Value of y is : " + y);

              y = (x == 20) ? 211 : 210 ;

              System.out.println("Value of y is : " + y);

        }

}

Output:

Value of y is : 211

Value of y is : 210

Explanation:

In this problem, two variables, x and y, are declared of type int, and x is initialized to 21.

Now, the value of first y is the result of the expression, so when x=21 is greater than 1, the first condition will be true, and 211 will be stored in y.

The first sysout statement will print the value of y along with a message.

Similarly, the value of the second y is updated by the result of the

expression, so x=20 is not equal to 20, so the first condition will be

false, and 210 will be stored in y.

The second sysout statement will print the value of updated y along with a message.

Hence, the output will be Value of y is : 211 and Value of y is : 210

D) More Problem -

Write a Java Program to check Candidate's Education for Employer-Mindset.

Given that, Fig 6.13 shows the eligibility criteria for a Candidate's employer Mindset.

Consider that the candidate's focus on development, specifically skill development, and mindset, is a growth mindset.

![](image_rsrc2XC2.jpg)

public class EmployerMindsetEligibility

{

        public static void main(String[] args)

        {

              String focus = "Skill-Development" ;

              String mindset = "Growth-Mindset" ;

              String result = ((focus == "Skill-Development"  

                       && mindset == "Growth-Mindset")

                       ? "Candidate's Education is of Employer-Mindset"

                       :   ((focus == "Marks" && mindset == "Fixed-Mindset")

                           ? "Candidate's Education is not of Employer-Mindset" : null));

              System.out.println(result);

        }

}

Output:

Candidate's Education is of Employer-Mindset

Explanation:

In a figure, given that the Student's Focus is on skill development

and the Mindset is a growth mindset.

The Problem statement is that we need to check the Candidate's

Education towards the Employer-Mindset.

Let us suppose the Student's Focus is represented as a variable focus of type String, and the Student's Mindset is represented as a variable mindset of type String, i.e., focus = "Skill-Development", and

mindset = "Growth-Mindset".

To check the Candidate's Education of Employer-Mindset, all conditions are validated using a nested if and a conditional operator.

Inside the first part condition, two different conditions are validate-d. Since, as per given conditions, Students focus on the development and Mindset of Growth-Mindset, both the conditions are true, and

the further conditions will not be validated, and the String after ?

will be stored in a variable result.

Further, the sysout statement will print the message.

Hence, the output is Candidate's Education is of Employer-Mindset.

◆◆◆

Exercise:-

1) Fill in the Blanks:-

a) The _______ allow us to compare two values to see whether they    

      are equal, unequal, or greater than the other.

b) The _______ in the code are executed according to the order in

      which they appear.

c) The condition following the keyword if is always enclosed within

     a pair of _______.

d) Java allows the usage of three logical operators, namely _______,

      _______, and _______

e) &&, ||, and !. These will be used as _______, _______, and _______.

f) The group of statements till the if block  and not including the

      else is called an _______.

g) The conditional operators _______ and ________ are sometimes

      called ternary operators

2) State which of the following statements are true or false:-

a) ! is called an inequality operator.

b) We can use an arithmetic expression in an if statement. ***

c) else block cannot be used without an if block.

d) NOT operator written as !!.

e) It is mandatory to use else after if.

f) if statement can be written without the use of Parenthesis.

g) The else block is executed if the condition of the if-block is evalu-    

      ated as false.

3) Find and correct any syntax errors in the following programs:-

a) Program 1 -

public class Program_1

{

        public static void main(String[] args)

        {

              if( if(1==1) )

              {

                    System.out.println("null");

              }

        }

}

b) Program 2 -

public class Program_2

{

        public static void main(String[] args)

        {

              if(true==false)

              {

                      ;

              }

        }

}

c) Program 3 -

public class Program_3

{

        public static void main(String[] args)

        {

              if( 0 )

              {

               }

        }

}

d) Program 4 -

public class Program_4

{

        public static void main(String[] args)

        {

              if(true)

                    System.out.println("1"); System.out.println("2");

              else

              {

                    System.out.println("Inside else");

              }

        }

}

e) Program 5 -

public class Program_5

{

        public static void main(String[] args)

        {

              if(true)

                    System.out.println("1");

              else

              {

                    System.out.println("2");

              }

              else

              {

                    System.out.println("3")

              }

        }

}

f) Program 6 -

public class Program_6

{

        public static void main(String[] args)

        {

              if(true)

              {

                    if(false)

                          System.out.println("1");

                    else

                    {

                          System.out.println("Inside else");

                    }

              }

        }

}

g) Program 7 -

public class Program_7

{

        public static void main(String[] args)

        {

              if(true); if(false) {} else 0 ;

        }

}

h) Program 8 -

public class Program_8

{

        public static void main(String[] args)

        {

              if(true)

              {

                    if(false)

                    {

                          System.out.println("1");

                    }

                    else

                    {

                          System.out.println("Inside else");

                    }

                    if(false);

              }

              if(true);

        }

}

i) Program 9 -

public class Program_9

{

        public static void main(String[] args)

        {

              if(true)

              {

                    if(false)

                          System.out.println("1");

                    else if(true)

                    {

                          System.out.println("Inside else-if");

                    }

              }

        }

}

j) Program 10 -

public class Program_10

{

        public static void main(String[] args)

        {

              if(false)

              {

              }

              else if(false)

              {

                    if(false);

                    else if(true)

                    {

                          System.out.println("Inside else-if");

                    }

              }

              else

              {};

        }

}

k) Program 11 -

public class Program_11

{

        public static void main(String[] args)

        {

              if(false)

              {}

              else if(false)

              {};

              else

              {};

        }

}

l) Program 12 -

public class Program_12

{

        public static void main(String[] args)

        {

              if((true && !false) || check==true)

              {

                    System.out.println(!check);

              }

        }

}

m) Program 13 -

public class Program_13

{

        public static void main(String[] args)

        {  

              if(true && !false)

              {

                    System.out.println(false);

              }

        }

}

n) Program 14 -

public class Program_14

{

        public static void main(String[] args)

        {

              if(false || (boolean b = true))

              {

              }

      }

}

o) Program 15 -

public class Program_15

{

        public static void main(String[] args)

        {

              boolean b = true ? 0 : 1 ;

        }

}

p) Program 16 -

public class Program_16

{

        public static void main(String[] args)

        {

              String str = false ? "-" : "+" ;

        }

}

4) Answers to the following questions:-

a) What is the difference between Logical operators and Conditional

      operators?

b) What is the difference between the if-else and else-if clause?

c) What are the different types of Decision Control Instructions?

d) What are bitwise operators?

e) What is the difference between an Assignment operator and an

     equality operator?

f) What is the nesting of ifs?

5) Basic Programs:-

a) Write a Program to check whether 23092019 consists of at least 4

      Digits. (use only if condition)

b) Write a Program to check whether the Sum of Three numbers is

      either Even or Positive. (use only if condition)

c) Write a Java Program to Check if a String is Empty or Null.

      (use only if-else condition)

d) Write a Program to check whether the Sum of Three Positive

      numbers is either Even or Odd. (use only if-else condition)

e) Write a Java Program to Check if a String is not null and is equal to

       SnR or not. (use nested loop)

f) Write a Program to check whether the Sum of Three numbers is

      Positive and Even or Positive and Odd. (use nested loop)

g) Write a Java Program to Check if a String is not null and is equal

     to SnR or null. (use only if and else-if condition)

h) Write a Program to check whether the Sum of Three numbers is

     Positive or Negative and Even or Odd. (use only if and else-if

     condition)

i) Write a Java Program to Check if a String is not null and is equal

      to SnR or null. (use Logical Operator)

j) Write a Program to check whether the Sum of Three numbers is

      Positive and Even or Negative and Odd. (use Logical Operator)

k) Write a Java Program to Check if a String is null or not.

      (use Conditional Operator)

l) Write a Program to check whether the Sum of Three numbers is

     Positive or Negative. (use Conditional Operator)

6) Output Problems:-

a) Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              Integer a = 128, b = 128;

              if(a==b)

              {

                    System.out.println("null");

              }

              Integer c = 100, d = 100;

              if(c==d)

              {

                    System.out.println(-1);

              }

        }

}

b) Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              boolean check = false ;

              if(check)

              {

                    System.out.println("Check");

              }

              check = true ;

              System.out.println(check);

        }

}

c) Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

             double d = 3.14 ;

             if(d > 3)

             {

                   System.out.println("True");

             }

             else

             {

                   System.out.println("False");

             }

       }

}

d) Problem 4 -

public class Problem_4

{

        public static void main(String[] args)

        {

              int a = 1 ;

              int b = 0 ;

              if(a == b+a)

              {

                    System.out.println("True");

              }

              else

              {

                    System.out.println("False");

              }

        }

}

e) Problem 5 -

public class Problem_5

{

        public static void main(String[] args)

        {

              String device = null;

              if(device == "Mobile")

              {

                    device = "Laptop";

                     if(device == "Laptop")

                           System.out.println("Laptop");

                     else

                           System.out.println("Mobile");

              }

              else

               {

                     device = "Mobile";

                     if(device == "Mobile")

                           System.out.println("Mobile");

                    else

                          System.out.println("Laptop");

              }

        }

}

f) Problem 6 -

public class Problem_6

{

        public static void main(String[] args)

        {

              int m1 = 2.0 ;

              float m2 = 2.00f ;

              if(m1 == m2)

              {

                    System.out.println("Equal");

              }

              else

              {

                    System.out.println("Not Equal");

              }           

        }

}

g) Problem 7 -

public class Problem_7

{

        public static void main(String[] args)

        {        

              int age = 58 ;

              if(age < 18)

              {

                    System.out.println("Child");

              }

              else if(age > 18)

              {

                     System.out.println("Boy/Girl");

              }

              else if(age > 59)

              {

                    System.out.println("Senior Citizens");

              }

        }

}

h) Problem 8 -

public class Problem_8

{

        public static void main(String[] args)

        {

              int day = 0 ;

              if(day == 1)

              {

                    System.out.println("Sunday");

              }

              else if(day == 2)

              {

                    System.out.println("Monday");

              }

              else if(day == 3)

              {

                    System.out.println("Tuesday");

              }

              else if(day == 4)

              {

                    System.out.println("Wednesday");

              }

                    else

                    {

                          System.out.println("Funday");

                    }

        }

}

i) Problem 9 -

public class Problem_9

{

        public static void main(String[] args)

        {

              int a = 10, b = 1;

              System.out.println("Var1 = " + a);

              System.out.println("Var2 = " + b);

              System.out.println("!(a < b) = " + !(a < b));

              System.out.println("!(a > b) = " + !(a > b));

        }

}

j) Problem 10 -

public class Problem_10

{

        public static void main(String[] args)

        {

              int a = 25, b = 35, c = 15;

                    System.out.println("Value of b : " + b);

              if((a > c) && (++b > c))

              {

                    System.out.println("Inside if block");

              }

              System.out.println("Value of b : " + b);

        }

}

k) Problem 11 -

public class Problem_11

{

        public static void main(String[] args)

        {

              int x=5, y=4, z=7;

              System.out.println(x>y && x>z || y<z);

              System.out.println((x<z || y>z) && x<y);

        }

}

l) Problem 12 -

public class Problem_12

{

        public static void main(String[] args)

        {

              int largest = (n1 >= n2) ? ((n1 >= n3) ? n1 : n3) :

                                                                                                        ((n2 >= n3) ? n2 : n3);

              System.out.println("Largest Number: " + largest);

        }

}

7) More Programs:-

a) Write a Java Program to find the eligibility criteria for a Student to

     become a school-captain or notusing the below Case Control  

     Instructions.

     i) Using the if condition

     ii) Using the if-else condition

     iii) Using only nested if-else condition

     Given that a Student is eligible for a School-Captain if all the criteria

    as per Fig. 6.14 are  satisfied.

![](image_rsrc2XC3.jpg)

   Consider that a Student got an 87% percentage in class 9. Currently,   

   he is in Class 10, has the quality of leadership, and has got the max-

   imum votes in the voting poll.

b) Write a Java Program to find the eligibility criteria for a student to

     become a vice-captain or not using the case-control instructions

     below.

     i) Using the if and else-if condition          

     ii) Using the Conditional Operators          

     iii) Using the Logical Operators

    Given that a student is eligible for a Vice-Captain if all the criteria as

    per Fig. 6.15 are satisfied.      

![](image_rsrc2XC4.jpg)

   Consider that a Student got an 87% percentage in class 9. Currently,      

   he is in Class 10, has the quality of leadership, and has got the     

   Second-Highest votes in the voting poll.  

8) Activity:-

Write a Java Program for the following statements that represent the daily use scenarios. (Assume different variables as needed to meet the conditions)

a) Mom, what if today's school bus does not come for the pickup?

     Then Mom answered that Dad would drop you at school.

      (use only if condition)

b) Dad, what if my classmate has beaten me in the class?

     Then Dad says that you should go to your teacher and complain   

     about it. (use only if condition)

c) The teacher says that if you concentrate on your studies, you will

     get excellent marks in your exam. (use only if condition)   

d) Golu says that if my Dad gives me a mobile, I will learn Coding.

      (use only if condition)

e) Nidhi wonders if I can learn Java Programming then my goal is to

      build an App. (use only if condition)

f) Mom, what if today's school bus does not come for the pickup?

     Then Mom answered that if Dad were free, he would drop you off;

     otherwise, I would drop you off at school.

     (use only if-else condition)

g) Dad, what if Rohan will beat me in the class? Then Dad says you

     should complain about it to your teacher; otherwise, Rohan will    

     beat you every other day. (use only if-else condition)

h) The teacher says that if you concentrate on your studies, you will

      get excellent marks on your exam; otherwise, your principal will

      scold you.  (use only if-else condition)

i) Golu says that if my dad gives me a mobile, I will learn Coding on

     his mobile; otherwise, I will do it on my friend's Phone.

     (use only if-else condition)

j) Nidhi wonders if I can learn Java Programming, then I will build an

     App; otherwise, I will not be able to. (use only if-else condition)

k) Mom, what if today's school bus does not come for the pickup?

     Then Mom answers that if Dad is free, he will drop you off, or if

      I am free, I will drop you off at school.  (use nested loop)

l) Dad, what if Rohan will beat me in the class? Then Dad says you

    should go to your teacher and complain about it, or you can go to

    your Principal to complain about him. (use nested loop)

m) The teacher says that if you concentrate on your studies, then you

       will get excellent marks in your exam; otherwise, your principal

       will scold you. (use nested loop)

n) Rohan says that if my dad gives me a mobile, then I will learn

      Coding on his mobile, or I will do it on Mom's Phone.

      (use nested loop)

o) Rohan wonders if I can learn Java Programming and I will practice

     in mobile. Then, I look forward to building an app.

     (use nested loop)

p) Mom, what if today's school bus does not come for the pickup?

     Then Mom answers that if Dad is free, he will drop you off;

     otherwise, if I am free, I will drop you off at school.

     (use only if and else-if condition)

r) Dad, what if Rohan will beat me in the class? Then Dad says you

     should go to your teacher and complain about it; otherwise, if the

     teacher is not present, you can go to your Principal to complain

     about him. (use only if and else-if condition)

s) The teacher says that if you concentrate on your studies, then you

     will get excellent marks in your exam; otherwise.   

     (use only if and else-if condition)

t) Rohan says that if my dad gives me a mobile, then I will learn

     Coding on his mobile; otherwise, if I give me her mobile, I will

     learn Coding on her Phone.  (use only if and else-if condition)

u) Rohan wonders if I can learn Java Programming. Then, I will look

     forward to building an App; otherwise, I will practice on mobile.    

     (use only if and else-if condition)

v) Mom, what if today's school bus does not come for the pickup?

     Then Mom answered that if Dad were free, he would drop you off;

     otherwise, I would drop you off at school.

     (use Conditional Operators)

w) Dad, what if Rohan will beat me in the class? Then Dad says you

       should complain about it to your teacher; otherwise, Rohan will

       beat you every other day. (use Conditional Operators)

x) The teacher says that if you concentrate on your studies, you will

      get excellent marks on your exam; otherwise, your principal will

      scold you. (use Conditional Operators)

y) Golu says that if my dad gives me a mobile, I will learn Coding on

      his mobile; otherwise, I will do it on my friend's Phone.

      (use Conditional Operators)

z) Nidhi wonders if I can learn Java Programming, then I will build an

     App; otherwise, I will not be able to. (use Conditional Operators)

aa) Mom, what if today's school bus does not come for the pickup?

        Then Mom answered that if Dad were free, he would drop you off;

        otherwise, I would drop you off at school.

        (use Conditional Operator)

bb) Dad, what if Rohan will beat me in the class? Then Dad says you

         should complain about it to your teacher; otherwise, Rohan will

         beat you every other day. (use Conditional Operator)

cc) The teacher says that if you concentrate on your studies, you

        will get excellent marks on your exam; otherwise, your principal

        will scold you. (use Conditional Operator)

dd) Golu says that if my dad gives me a mobile, I will learn Coding on

         his mobile; otherwise, I will do it on my friend's Phone.

         (use Conditional Operator)

ee) Nidhi wonders if I can learn Java Programming, then I will build  

        an App; otherwise, I will not be able to. (use Conditional Operator)

◆◆◆

7\. Loop Control Instructions

The versalitiy of the computer lies in its ability to perform a set of instructions repeatedly. This involves repeating some portion of the Program either a specified number of times or until a particular condition is being satisfied. This repeatitive operation is done through a loop control Instruction.

1) Loop Control Instructions:

Loop Control Instructions is the form of syntax defined by Java allows us to execute a statement or group of statements multiple times.   

There are four ways by way of which we can repeat a part of program. They are...

        a) Using a for loop

        b) Using a while loop

        c) Using nested Loop

        d) Using a do-whie loop

Fig. 7.1 shows different types of Loop Control Instructions.

![](image_rsrc2XC5.jpg)

2) The for loop:

The Java for loop is used several times to iterate a part of the program.

Iteration simply means repetition of the for loop again and again.

The statement inside the for loop would keep on getting executed till the condition being tested remains true.

When the condition becomes false, the control passes to the first statement that follows the body of the for loop.

The condition being tested may use relational or logical operators.

The statement within the loop may be a single line or a block of statements.

It is not necessary that a loop counter must only be an int. It can even be a float.

The general form is as follows...

         for(initialization; condition; increment/decrement)

        {    

              // statements    

        }    

Working of the for loop Process Flow:

![](image_rsrc2XC6.jpg)

As can be seen in Fig. 7.2, whenever a program is written using the for loop, some iteration is taking place.

Three parts are used to implement the for loop, i.e., initialization, comparison, incrementation/decrementation, and separated using a semicolon.

All these parts are declared inside the same Parenthesis as an if condition.

In the Initialization part, we declare any variable and initialize it with a value.

In the Comparison part, a declared variable is compared with some conditions.

In the Incrementation part, on each iteration, the variable's value keeps increasing and decreasing as per the instruction passed in the third part if the second part comparison is true.

On any iteration, if the comparison fails, then the current value of the variable will remain the same, and no increment or decrement will occur.

Suppose there are no further conditions to be evaluated. In that case, the control will reach after the for loop, and a further statement will be executed.

Below are a few statements that represent Real-life scenarios. These can be represented using the for loop...

a) In a School Assembly, count the number of girls available out of the

      total number of Students, 150.

b) Find the total number of States of India out of 28, which starts from

     Alphabet 'M'.

c) Count the number of mobile devices in your home out of 15 electronic

     devices.   

d) Check how many teachers came today to school with a vehicle out of

      35.

e) Count how many family members have eaten Breakfast out of 6.

A) Programs Scenarios -

Scenario 1 -

// Java Program for for loop

public class Scenario_1

{

        public static void main(String[] args)

        {     

              // The following Examples will work             

              // Example 1

              for(int i=1; i <= 2; i++)

                    System.out.println(i + " ");

              // Example 2

              for(int i=0; i < 2; i++)

                    System.out.println(i + " ");

              // Example 3

              for(int i=5; i > 0; i--)

                    System.out.println(i + " ");

              // Example 4

              for(int i=5; i >=1; i--)

                    System.out.println(i + " ");

              // Example 5

              for(int i=1; i <= 2; i=i+2)

                    System.out.println(i + " ");

              // Example 6

              for(int i=5; i >=1; i=i-1)

                    System.out.println(i + " ");

              // Example 7

              int a = 0 ;

              for(int i=1; i < 2; i++)

                    a = 1;

              // Example 8

              for(int i=1;

                                        i < 2;

                                                    i++)

                    System.out.println(i + " ");

              // Example 9

              for

              (

              int

              i

              =

              1

               ;

               i

               <

               2;

                i

                ++

                )

                      System.out.println(i + " ");

              // The following Examples will not work

              // Example 10

              for(int i=1; i < 2)

                    a = 1;

                     i++;

              // Example  11

              int i=1

              for(i < 2)

                    a = 1;

                    i++;

        }

}

Scenario 2 -

// Java Program for for loop with Pair of Braces

public class Scenario_2

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              for(int i=1; i <= 2; i++)

              {

                    System.out.println(i + " ");

              }

              // Example 2

              for(int i=0; i < 2; i++)

              {

                    System.out.println(i + " ");

              }

              // Example 3

              for(int i=5; i > 0; i--)

              {

                    System.out.println(i + " ");

              }

              // Example 4

              for(int i=5; i >=1; i--)

              {

                    System.out.println(i + " ");

              }

              // Example 5

              for(int i=1; i <= 2; i=i+2)

              {

                    System.out.println(i + " ");

              }

              // Example 6

              for(int i=5; i >=1; i=i-1)

              {

                    System.out.println(i + " ");

              }

              // Example 7

               int a = 0 ;

               for(int i=1; i < 2; i++)

               {

                      a = 1;

               }

               // Example 8

               for(int i=1;

                                         i < 2;

                                                    i++) {

                      System.out.println(i + " "); }

                // Example 9

                for

                (

                int

                i

              =

              1

              ;

              i

              <           

              2;

              i

              ++

               )

               {System.out.println(i + " ");}

        }

}

Scenario 3 -

// Java Program for for loop with Parenthesis

public class Scenario_3

{

        public static void main(String[] args)

        {

               // The following Example will work

               // Example 1

               for(int i=1; i <= 2; i++)

               {

                     System.out.println(i + " ");

               }

         }

}

// Java Program for for loop without Parenthesis

class Scenario_3_2

{

        public static void main(String[] args)

        {

              // The following Example will not work

              // Example 1

              for int i=1; i <= 2; i++

              {

              }

        }

}

Scenario 4:

// Java Program for for loop with Statement Terminator

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following Examples will work but may or may not be able to print the desired output

              // Example 1

              for(int i=1; i <= 2; i++)

              {

                    System.out.println(i + " ");

              }

              // Example 2

              for(int i=1; i <= 2; i++)

              {

                    System.out.println(i + " ");

              };

              // Example 3

              for(int i=1; i <= 2; i++) ;

              {

                    System.out.println(1);

              }

              // Example 4

              for(int i=1; i <= 2; i++) ;

              {

                    System.out.println(1);

              };

        }

}

Scenario 5:

// Java Program for for loop with Multiple Statements

public class Scenario_5

{

        public static void main(String[] args)

        {

               // The following Example will work

              // Example 1

              for(int i=1; i <= 3; i++)

              {

                    int a = 211 ;

                    System.out.println(a);

                    a++;

              }

        }

}

B) Basic Programs -

1) Write a Java Program to display Alphabets (A to Z) using loop.

public class DisplayAlphabetsAtoZ_1

{

        public static void main(String[] args)

        {     

              System.out.println("Alphabets from (A-Z) are: ");

              for(int i='A'; i <= 'Z'; i++)

              {

                    System.out.printf("%c ", i);

              }

        }

}

Output:

Alphabets from (A-Z) are:

A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

Explanation:

In this Program, inside the main() method, the sysout statement is first printing the message.  

The Problem statement is to display Alphabets (A to Z) using loop.

In the for loop, a variable i is initialized with a value 'A,' and on each iteration, the i value will be compared so that i should be less than

or equal to 'Z'.

Once the comparison is true, then the sysout statement will print

the value of i, and the value of i will be incremented to 'B', and simil-arly, the process continues until the comparison part works.

%d is used to print decimal(integer) number ,while %c is used to print

character . If you try to print a character with %d format the computer will print the ASCII code of the character.

To get a clear picture of how the loop is working, let us understand

the iteration scenarios below -

In the 1st iteration, When i = 'A' if 'A' <= 'Z' then i = 'A' so, i = i+1 = 'A'+1 = 'B'.

In the 2nd iteration, When i = 'B' if 'B' <= 'Z' then i = 'B' so, i = i+1 = 'B'+1 = 'C' .

In the 3rd iteration, When i = 'C' if 'C' <= 'Z' then i = 'C' so, i = i+1 = 'C'+1 = 'D' .

.

.  

.

In the 26th iteration, When i = 'Z' if 'Z' <= 'Z' then the loop finishes its execution.

2) Write a Java Program to print all the Even numbers from 1 to 100.

public class EvenNumberBetween1to100_2

{

        public static void main(String[] args)

        {

              System.out.println("All Even Numbers from 1 to 100 are : ");

              for(int i=1; i<=100 ; i++)

              {

                    if(i % 2 == 0)

                    {

                          System.out.print(i + " ");

                    }

              }

        }

}

Output:

All Even Numbers from 1 to 100 are : 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50 52 54 56 58 60 62 64 66 68 70 72 74 76 78 80 82 84 86 88 90 92 94 96 98 100

Explanation:

In this Program, inside the main() method, the sysout statement is first printing the message.

The Problem statement is to print all the Even numbers from 1 to

100.

In the for loop, a variable i is initialized with a value 1, and on each

iteration, the value of i will be compared so that i should be less

than or equal to 100.

Once the comparison is true, the sysout sta tement will print the i

value, and the i value will be incremented as 'B'.

Similarly, the process goes on till the comparison part is true.

To get a clear picture of how the loop is working, let us understand

the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 <= 100 then i = 1 and i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 <= 100 then i = 2 and i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 <= 100 then i = 3 and i = i+1 = 3+1 = 4.

.  

.  

.

In the 99th iteration, When i = 99 if 99 <= 100 then i = 99 and i = i+1 = 99+1 = 100.

In the 100th iteration, When i = 100 if 100 <= 100 then i = 100 and i = i+1 = 100+1 =

   101.

In the 101st iteration, When i = 101, if 101 <= 100, which is not true so loop will be

terminated.

3) Write a Java Program to check whether a number is Prime Number

      or not.

public class PrimeNumber_3

{

        public static void main(String[] args)

        {

              int num = 9 ;

              int factorCount = 0 ;

              for(int i=1; i<=num; i++)

              {

                    if(num % i == 0)

                    {

                          factorCount = factorCount + 1 ;

                    }

              }

              if(factorCount > 2)

              {

                    System.out.println(num + " is not a Prime Number");

              }

             else

             {

                   System.out.println(num + " is a Prime Number");

             }

        }

}

Output:

9 is not a Prime Number

Explanation:

In this Program, inside the main() method, two variables, num and

factorCount, are initialized with 9 and 0, respectively.

The Problem statement is to check whether a number is Prime

Number or not.

The Prime Numbers are divisible by 1 and itself, so there should be 2 factors.

In the for loop, a variable i is initialized with a value 1, and on each

iteration, the value of i will be compared so that i should be less than or equal to num, which is 9, so in total, there will be 9 iterations if the comparison is true.

Inside the for loop, on each iteration, num is a modular division by a number that is equal to or lesser than it starting from 1, and if the

result is 0 then that particular i will be the factors of a num.

If the factor of num is greater than 2 then the block will not be

executed, and the else-block will print the message.

To keep count of the total number of a factor of a num, we store it in a variable factor count.

To get a clearer picture of how the loop is working, let us understan- d the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 <= 9 then (9 % 1) = 0 so, i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 <= 9 then (9 % 2) != 0 so, i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 <= 9 then (9 % 3) != 0 so, i = i+1 = 3+1 = 4.

.

.

In the 9th iteration, When i = 9 if 100 <= 9 then (9 % 9) = 0 so, i = i+1 = 9+1 = 10.

In the 10th iteration, When i = 10 if 10 <= 9, which is not true so the loop will be

      terminated.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int i = 1;

              while(i < 10)

              {

                    System.out.print(i + " ");

                    i++;

              }

        }

}

Output:

1 2 3 4 5 6 7 8 9

Explanation:

In this problem, inside the main() method, a variable i has been

declared and initialized with a value 1.

In the while condition, a variable i should be less than 10, so the

sysout statement will print the i value on each iteration, and the i

value will be incremented by 1.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 < 10 so, i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 10 so, i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 10 so, i = i+1 = 3+1 = 4.

.

.

.

In the 9th iteration, When i = 9 if 9 < 10 so, i = i+1 = 9+1 = 10.

In the 10th iteration, When i = 10 if 10 < 10, which is not true the loop will be

      terminated.

Hence, the output is 1 2 3 4 5 6 7 8 9.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

               int i = 10;

               while(i >= 1)

               {

                     System.out.println(i+1);

                     i--;

               }

        }

}

Output:

11

10

9

8

7

6

5

4

3

2

Explanation:

In this problem, inside the main() method, a variable i has been

declared and initialized with a value of 10.

In the while condition, a variable i should be greater than 1, so the

sysout statement will print the i value on each iteration, and the i

value will be decremented by 1.

To get a clearer picture here how the loop is working, let's understa-nd the iteration scenarios below -

In the 1st iteration, When i = 10 if 10 > 1 then i = i-1 = 10-1 = 9.

In the 2nd iteration, When i = 9 if 9 > 1 then i = i-1 = 10-1 = 8.

In the 3rd iteration, When i = 8 if 8 > 1 then i = i-1 = 10-1 = 7.

 .

 .

.

In the 9th iteration, When i = 2 if 10 > 1 then i = i-1 = 2-1 = 1.

In the 10th iteration, When i = 1 and 10 < 10, which is not true so, the loop will be

      terminated.

Hence, the output is 11 10 9 8 7 6 5 4 3 2.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              while(false)

              {

                    System.out.println("Inside while loop");

              }

        }

}

Output:

Error

Explanation:

The statement inside the while loop is never reachable because the while condition is false.

Hence, the output is an Error.

![](image_rsrc2XC7.jpg)

D) More Programs -

Write a Java Program to print the table of 7 from 1 to 10.

public class Table_1

{

        public static void main(String[] args)

        {

              int table = 7 ;

              for(int i=1; i<11 ; i++)

              {

                     int multiplication = table * i ;

                     System.out.println(table + " * " + i + " = " + multiplication);

              }

        }

}

Output:

7 * 1 = 7

7 * 2 = 14

7 * 3 = 21

7 * 4 = 28

7 * 5 = 35

7 * 6 = 42

7 * 7 = 49

7 * 8 = 56

7 * 9 = 63

7 * 10 = 70

Explanation:

In this Program, one for loop is used inside the main() method.

One variable table is declared of type int and initialized with a value of 7.

In the first for loop, inside the parenthesis, three parts are separated by a semicolon. In the first part, value i is initialized with 1\. In the

second part, i should be less than 11; in the third part, the i value

will be incremented by 1 on each iteration.

On each iteration, the variable multiplication will keep updated by

the value of i and store the updated result, and the sysout statement will print the value of multiplication of table 7 from 1 to 10.

Here in this case, since the value maximum value of i can be 10 so

the total number of iterations will be 10 only.

To get a more clear picture of how the loop is working, let's underst-and the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 < 11 then multiplication = 7 * 1 = 7 so, i = i+1 =        

      1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 11 then multiplication = 7 * 2 = 14 so, i = i+1 =

      2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 11 then multiplication = 7 * 3 = 21 so, i = i+1 =

      3+1 = 4.

.  

.

.

In the 10th iteration, When i = 10 if 10 < 11 then multiplication = 7 * 10 = 70 so,

      i = i+1 = 10+1 = 11.

In the 11th iteration, When i = 11, if 11 < 11, which is not true so the loop will be

      terminated.

3) The While Loop:

The statement inside the while loop would keep on getting executed till the condition being tested remains true.  

When the condition becomes false, the control passes to the first statement that follows the body of the while loop.

The condition being teseted may use relational or logical operators.

The statement within the loop may be a single line or a block of statements.

It is not necessary that a loop counter must only be an int. It can even be a float.

The general form of the while loop with all three conditions is as follows...

        initialization

        while(condition)

        {     

              // statements   

              increment/decrement

        }      

Working of the while loop Process Flow:

![](image_rsrc2XC8.jpg)

As can be seen in Fig. 7.3, whenever a program is written using the while loop, some iteration is taking place.

Like the for loop, three parts are used to implement the while loop, i.e., initialization, comparison, and incrementation/decrementation.

In while loop, all these parts are not declared inside the same Parenthesis as an if condition. ***

First, the Initialization part is done above the while loop; we declare any variable and initialize it with a value.

In the Comparison part, a declared variable is compared with conditions similar to the for loop second part.

In the Incrementation part, on each iteration, the variable's value keeps increasing and decreasing as per the instruction passed in the third part of the while loop if the comparison form the second part is true.

The third part is kept inside the while loop, not with the while condition.

On any iteration, if the comparison fails, then the current value of the variable will remain the same, and no increment or decrement will occur.

Suppose there are no further conditions to be evaluated. In that case, the control will reach after the while loop, and a further statement will be executed.

Below are a few statements that represent real-life scenarios. These can be represented using the while loop...

a) In a School Assembly, count the number of girls available out of the

      total number of Students, 150.

b) Find the total number of States of India out of 28, which starts from

     Alphabet 'M'.

c) Count the number of mobile devices in your home out of 15 electronic

     devices.   

d) Check how many teachers came today to school with a vehicle out of

      35.

e) Count how many family members have eaten Breakfast out of 6.

A) Program Scenarios -

Scenario 1 -

// Java Program with while loop

public class Scenario_1

{

        public static void main(String[] args)

        {

              // Example 1

              int i1 = 1;

              while(i1 <= 2)

                    System.out.println(1);

              i1++ ;

              // Example 2

              int i2=0;

              while(i2 < 2)

                    System.out.println(2);

              i2++;

              // Example 3

              int i3=5;

              while(i3 > 0)

                    System.out.println(3);

              i3--;

              // Example 4

              int i4=5;

              while(i4 >=1)

                    System.out.println(4);

              i4--;

              // Example 5

              int i5=1;

              while(i5 <= 2)

                    System.out.println(5);

              i5 = i5 + 2 ;

              // Example 6

              int i6=5;

              while(i6 >=1)

                    System.out.println(6);

              i6 = i6 - 1 ;

              // Example 7

              int a = 0 ;

              int i7 = 1;

              while(i7 < 2)

                    a = 1;

              i7++;

              // Example 8

              int i8 = 1;

              while(

                                    i8 < 2

                                                       )

                     System.out.println(8);

              i8++;

              // Example 9

              int i9 = 1;

              while

              (

              i9

              <

             2

              )

                    System.out.println(9);

              i9++;

        }

}

Scenario 2 -

// Java Program while while loop with Pair of Braces

public class Scenario_2

{

        public static void main(String[] args)

        {

              // Example 1

              int j1 = 1;

              while(j1 <= 2)

              {

                    System.out.println(1);

                     j1++;

              }

              // Example 2

              int j2=0;

              while(j2 < 2)

              {

                    System.out.println(2);

                    j2++ ;

              }

              // Example 3

              int j3 = 5;

             while(j3 > 0)

              {

                   System.out.println(3);

                   j3--;

              }

              // Example 4

              int j4 = 5;

              while(j4 >=1)

              {

                    System.out.println(4);

                    j4--;

              }

              // Example 5

              int j5 = 1 ;

              while(j5 <= 2)

              {  

                    System.out.println(5);

                    j5 = j5 + 2;

              }

              // Example 6

              int j6 = 5;

              while(j6 >=1)

              {

                    System.out.println(6);

                    j6 = j6 - 1;

              }

              // Example 7

              int a = 0 ;

              int i7 = 1;

              while(i7 < 2)

              {

                    a = 1;

                    i7++;

              }

              // Example 8

              int i8 = 1;

              while(

                                   i8 < 2

                                                      )

              {

                    System.out.println(8);

                    i8++;

              }

              // Example 9

              int i9 = 1;

              while

              (

              i9

              <

              2

               )

                     {System.out.println(9);

              i9++;}

        }

}

Scenario 3 -

// Java Program for while loop with Parenthesis

public class Scenario_3

{

        // The following method will work

        public static void main(String[] args)

        {

              int i=1;

              while(i <= 2)

              {

                    System.out.println(i + " ");

                    i++;

             }

        }

}

// Java Program for while loop without Parenthesis

class Scenario_3_2

{

        // The following method will not work

        public static void main(String[] args)

        {

              for int i=1; i <= 2; i++

              {

              }

        }

}

Scenario 4 -

// Java Program for for loop with Statement Terminator

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following Example will work 

              // Example 1

              int j1 = 1;

              while(j1 <= 2)

              {

                    System.out.println(1);

                     j1++;

              }

              // Example 2

              int j2=0;

              while(j2 < 2)

              {

                    System.out.println(2);

                    j2++ ;

              };

              // Example 3

              int j3 = 5;

              while(j3 > 0) ;

              {

                    System.out.println(3);

                    j3--;

              }

              // Example 4

              int j4 = 5;

              while(j4 >=1) ;

              {

                    System.out.println(4);

                    j4--;

              };

        }

}

Scenario 5 -

// Java Program for while loop with Multiple Statements

public class Scenario_5

{

        // The following method will work

        public static void main(String[] args)

        {

              int i=1;

              while(i <= 3)

              {

                    int a = 211 ;

                    System.out.println(a);

                     a++;

               }

        }

}

B) Basic Programs -

1) Write a Java Program to count the Digits.

public class CountDigitsInInteger_1

{  

        public static void main(String[] args)

        {  

              int num = 25489 ;

              int count = 0 ;

              while(num != 0)

              {

                    num = num / 10;

                    ++count;

              }

              System.out.println("Number of Digit in an Integer is : " + count);

        }

}

Output:

Number of Digit in an Integer is : 5

Explanation:

In this Program, inside the main() method, two variables, num and count, are initialized with 25489 and 0, respectively.

The problem statement is to count the Digits.

In the while loop, the num should not be equal to 0 on each iterationso the value of the count will be increased by 1.

Inside the while loop, on each iteration, value num will be updated

to a value resulting from an expression in RHS.

To get a more clear picture of how the loop is working, let us under-stand the iteration scenarios below -

In the 1st iteration, When count = 0 if 25489 != 0 then 25489 / 10 = 2548 so, count =

      count+1 = 0+1 = 1.

In the 2nd iteration, When count = 1 if 2548 != 0 then 2548 / 10 = 254 so, count =

      count+1 = 1+1 = 2.

In the 3rd iteration, When count = 2 if 254 != 0 then 254 / 10 = 25 so, count = count+1 =

      2+1 = 3.

In the 4th iteration, When count = 3 if 25 != 0 then 25 / 10 = 2 so, count = count+1 =

      3+1 = 4.

In the 5th iteration, When count = 4 if 2 != 0 then 2 / 10 = 0 so, count = count+1 = 4+1 = 5

In the 6th iteration, When count = 5 if 0 != 0, which is not true so the loop will be

      terminated.

2) Write a Java Program to print the Sum of the first 20 Natural

      numbers.

public class NaturalNumbersSum_2

{

        public static void main(String[] args)

        {   

              int n = 20 ;

              int sum = 0 ;

              int i = 1 ;

               while(i <= n)

               {

                     sum = sum + i ;

                     i++ ;

               }

               System.out.println("Sum of First 20 Natural Numbers is : " +sum);

        }

}

Output:

Sum of First 20 Natural Numbers is : 210

Explanation:

In this Program, inside the main() method first, two variables, num, and sum, are initialized with 20 and 0, respectively.

The problem statement is to print the Sum of the first 20 Natural

numbers.

The variable i is initialized with a value 1 for the loop iteration.

In the while loop, the condition is that i should be less than and

equal to n, which is 20, and the i value will increase by 1 on each

iteration.

Inside the while loop, the variable sum will be updated to a value

resulting from an expression in RHS on each iteration.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

In the 1st iteration, When i = 1 and 1 <= 20 then 0 + 1 = 1 so, i = i+1 = 0+1 = 1.

In the 2nd iteration, When i = 2 and 2 <= 20 then 1 + 2 = 2 so, i = i+1 = 1+1 = 2.

In the 3rd iteration, When i = 3 and 3 <= 20 then 2 + 3 = 3 so, i = i+1 = 2+1 = 3.

.

.

.

In the 19th iteration, When i = 19 and 19 <= 20 then 171 + 19 = 190 so, i = 19+1 =

      3+1 = 20.

In the 20th iteration, When i = 20 and 20 <= 20 then 190 + 20 = 210 so, i = 20+1 =

      41 = 21.

In the 21st iteration, When i = 21 and 21 <= 20, which is not true so the loop will be

      terminated.

3) Write a Java Program to find GCD of two numbers.

public class GCD_3

{

        public static void main(String[] args)

        {

              int num1 = 5 ;

              int num2 = 7 ;

              int gcd = 1 ;

              int i=1;

              while(i <= num1 && i <=num2)

              {

                    if(num1%i==0 && num2%i==0)

                    {

                          gcd = i;

                    }

                    i++;

              }

             System.out.println("GCD of " + num1 + " and " + num2 + " is : " +

                                                                 gcd);

        }

}

Output:

GCD of 5 and 7 is : 1

Explanation:

In this Program, inside the main() method first, different variables

num1, num2, and gcd are initialized with 5, 7, and 1, respectively.

The Problem statement is to find GCD of two numbers.

The GCD is the Lowest Common multiplication of two Numbers.

The variable i is initialized with a value 1 for the loop iteration.

In the while loop, a condition is validated, and the value of i will be

compared so that i should be less than or equal to num1, which is 5,

and num2, which is 7, so there will be 5 iterations if the comparison is true.

Inside the while loop, on each iteration, num1 and num2 is a

modular divisions by i, and if the result is 0, then that particular i

will be called as GCD of two numbers, num1 and num2.

At last, the sysout statement will print the GCD along with a message.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 <= 5 && 1 <= 7 then 5 % 1 == 0 && 7 % 1 == 0 so,

     i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 <= 5 && 2 <= 7 then 5 % 2 == 0 && 7 % 2 == 0 so,

      i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 <= 5 && 3 <= 7 then 5 % 3 == 0 && 7 % 3 == 0 so,

      i = i+1 = 9+1 = 4.

In the 4th iteration, When i = 4 if 4 <= 5 && 4 <= 7 then 5 % 4 == 0 && 7 % 4 == 0 so,

      i = i+1 = 9+1 = 5.

In the 5th iteration, When i = 5 if 5 <= 5 && 5 <= 7 then 5 % 5 == 0 && 7 % 5 == 0 so,

      i = i+1 = 9+1 = 6.

In the 6th iteration, When i = 6 if 6 <= 5 && 6 <= 7 which is not true so the loop will

      be terminated.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

               for(int i=1 ; i < 10; i++)

               {

                      System.out.print(i + " ");

               }

        }

}

Output:

1 2 3 4 5 6 7 8 9

Explanation:

In this problem, only for loop is used inside the main() method.

In the for loop inside parenthesis, i is declared and initialized to 1 in the for loop, so the loop will start from 1 since the value of i is 1.

The condition is that i should be less than 10 on each iteration, and the sysout statement will print the value of i and the value of i will

be incremented by 1.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 < 10 so, i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 10 so, i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 10 so, i = i+1 = 3+1 = 4.

.

.

.

In the 9th iteration, When i = 9 if 9 < 10 so, i = i+1 = 9+1 = 10.

In the 10th iteration, When i = 10 if 10 < 10, which is not true the loop will be

      terminated.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              for(int i=10 ; i >= 0; i--)

              {

                    System.out.println(i);

              }

         }

}

Output:

10

9

8

7

6

5

4

3

2

1

0

Explanation:

In this problem, only the loop is used inside the main() method.

In the for loop inside parenthesis, i is declared and initialized to 10, so the loop will start from 10 since the value of i is 10.

On each iteration, the condition is that i should be greater than and equal to 0, and the sysout statement will print the value of i and the value of i will be decremented by 1.

In total, there will be 11 iterations.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

In the 1st iteration, When i = 10 if 10 >= 0 so, i = i-1 = 10-1 = 9.

In the 2nd iteration, When i = 9 if 9 >= 0 so, i = i-1 = 9-1 = 8.

In the 3rd iteration, When i = 8 if 8 >= 0 so, i = i-1 = 8-1 = 7.

.

.

.

In the 11th iteration, When i = 0 if 0 >= 0 so, i = i-1 = 0-1 = -1.

In the 12th iteration, When i = -1 and -1 >= 0, which is not true so the loop will be

      terminated.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              for(true)

              {

                    System.out.println("Inside for loop");

             }

        }

}

Output:

Error

Explanation:

The condition inside the for loop is invalid since boolean values cannot be used as a condition in a for loop.

Hence, the output is Error.

D) More Programs -

Write a Java Program to print all days of the week.

public class WeekAndDays_2

{

        public static void main(String[] args)

        {

              int i=1;

              while(i < 8)

              {

                    if(i == 1)

                    {

                          System.out.println("Day " + i + " is : " + "Sunday");

                    }

                    if(i == 2)

                    {

                          System.out.println("Day " + i + " is : " + "Monday");

                    }

                    if(i == 3)

                    {

                          System.out.println("Day " + i + " is : " + "Tuesday");

                    }

                    if(i == 4)

                    {

                          System.out.println("Day " + i + " is : " + "Wednesday");

                    }

                    if(i == 5)

                    {

                          System.out.println("Day " + i + " is : " + "Thursday");

                    }

                    if(i == 6)

                    {

                          System.out.println("Day " + i + " is : " + "Friday");

                    }

                    if(i == 7)

                    {

                          System.out.println("Day " + i + " is : " + "Saturday");

                    }

                    i++;

              }

        }

}

Output:

Day 1 is : Sunday

Day 2 is : Monday

Day 3 is : Tuesday

Day 4 is : Wednesday

Day 5 is : Thursday

Day 6 is : Friday

Day 7 is : Saturday

Explanation:

In this Program, one loop and multiple if checks are used inside the main() method.

For the while loop, three parts are used separately. In the first part,

value i is initialized with 1\. In the second part, inside the

parenthesis, i should be less than 8; in the third part, at the end of

the loop, the value of i will be incremented by 1.

On each iteration, any if checks will pass, and the sysout statement will print the value of i along with a message.

Here in this case, since the value maximum value of i can be 7 so the total number of iterations will be 7.

To get a more clear picture of how the loop is working, let us under-stand the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 <= 7 then i = 1 so, i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 <= 7 then i = 2 so, i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 <= 7 then i = 3 so, i = i+1 = 3+1 = 4.

In the 4th iteration, When i = 4 if 4 <= 7 then i = 4 so, i = i+1 = 4+1 = 5.

In the 5th iteration, When i = 5 if 5 <= 7 then i = 5 so, i = i+1 = 5+1 = 6.

In the 6th iteration, When i = 6 if 6 <= 7 then i = 6 so, i = i+1 = 6+1 = 7.

In the 7th iteration, When i = 7 if 7 <= 7 then i = 7 so, i = i+1 = 7+1 = 8.

In the 8th iteration, When i = 8 if 8 <= 7, which is not true so the loop will be

      terminated.

![](image_rsrc2XC9.jpg)

4) Nesting of Loops:

The way if statements can be nested, similary while and for loops can also be nested.

One of the general form is as follows...

        for(initialization, condition, increment/decrement)

       {    

              initialization

              while(condition)

              {     

                    // statements   

                    increment/decrement

              }    

        }    

Working of the nested loop Process Flow:

![](image_rsrc2XCA.jpg)

As seen in Fig. 7.4, some iteration occurs whenever a program is written using the nested for or while loop.

If the for loop has been used, the format will be the same as specified before.

Similarly, the same format will be used as specified before for the while loop.

There can be a nesting of multiple for loops, a nesting of multiple while loops, or a combination of for loops and while loops.

Similarly, all the conditions will be validated on each loop, and the value of an iterator will keep incrementing or decreasing as per the instruction specified.

As mentioned in the figure, if condition 1 fails, the control will come out of the loop.

If condition 1 passes, the control will reach inside the inner loop and validate condition 2 of the inner loop.

Again, if condition 2 is true, the loop will keep iterating as long as the comparison is true, and the counter will keep updating.

If all the iterations are completed for the inner loop, then the outer loop condition 1 will be validated for an increment value.

When the inner loop is executed, the control will pass to the outer loop to check another condition.

Similarly, the inner loop iteration starts until the comparison works for a new updated value.

This process continues until the comparisons of the outer and inner loops are satisfied.

If the outer loop finishes executing, the control will pass after the outer loop statement, and a further statement will be executed.

Below are a few statements that represent real-life scenarios. These can be represented using the nested loop...

a) Clock: A clock that rotates on an hourly basis. Each hour has 60 minutes, and each minute has 60 seconds. So here, three loops are required. Hour will be an outer loop; Minutes will be the first the inner loop and seconds will be the second inner loop of the minute loop.

b) Earth: The Earth revolves around the Sun every 365 days. It takes 24 hours for an earth to complete one rotation on its axis. So here, revolving around the Sun is an outer loop, and completing one rotation each day will be the inner loop. This scenario represents two loops.

c) ATM: To withdraw a sum of rupees of 50,000 from an ATM. ATMs have a limit of 10,000 at a time. So, five loops will be used to withdraw a total sum.

A) Program Scenarios -

Scenario 1 -

// Java Program for nested for loop

public class Scenario_1

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              for(int i=1; i <= 2; i++)

                    for(int j=1; j <= 2; j++)

                          System.out.println(i + " " + j);

              // Example 2

              for(int i=0; i < 2; i++)

                    for(int j=1; j <= 2; j++)

                          System.out.println(i + " " + j);

              // Example 3

              for(int i=5; i > 0; i--)

                    for(int j=1; j <= 2; j++)

                          System.out.println(i + " " + j);

              // Example 4

              for(int i=5; i >=1; i--)

                    for(int j=2; j > 0; j--)

                           System.out.println(i + " " + j);

              // Example 5

              for(int i=1; i <= 10; i=i+2)

                    for(int j=1; j > 0; j=j+3)

                          System.out.println(i + " " + j);

              // Example 6

              for(int i=5; i >=1; i=i-1)

                    for(int j=10; j > 0; j=j-2)

                          System.out.println(i + " " + j);

              // Example 7

              int a = 0 ;

              for(int i=1; i < 2; i++)

                    for(int j=1; j < 2; j++)

                          a = 1;

              // Example 8

              for(int i=1;

                                          i < 2;

                                                       i++)

              for(int j=1;

                                           j < 2;

                                                        j++)

                    System.out.println(i + " " + j);

              // Example 9

              for

              (

              int

              i

              =

              1

              ;

              i

              <

              2;

              i

              ++

              )

              for

              (

              int

              j

             =

             1

              ;

              j

             <

              2

              ;

              j++  

              )

                   System.out.println(i + " ");

        }

}

Scenario 2 -

// Java Program for nested for loop with Pair of Braces

public class Scenario_2

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              for(int i=1; i <= 2; i++)

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(i + " " + j);

                    }

               }

                // Example 2

                for(int i=0; i < 2; i++)

                {

                      for(int j=1; j <= 2; j++)

                      {

                            System.out.println(i + " " + j);

                      }

                }

              // Example 3

              for(int i=5; i > 0; i--)

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(i + " " + j);

                    }

              }

              // Example 4

              for(int i=5; i >=1; i--)

              {

                    for(int j=2; j > 0; j--)

                    {

                          System.out.println(i + " " + j);

                    }

              }

              // Example 5

              for(int i=1; i <= 10; i=i+2)

              {

                    for(int j=1; j > 0; j=j+3)

                    {

                          System.out.println(i + " " + j);

                    }

              }

              // Example 6

              for(int i=5; i >=1; i=i-1)

              {

                    for(int j=10; j > 0; j=j-2)

                    {

                         System.out.println(i + " " + j);

                    }

              }

              // Example 7

              int a = 0 ;

              for(int i=1; i < 2; i++)

              {

                    for(int j=1; j < 2; j++)

                    {

                          a = 1;

                    }

              }

              // Example 8

              for(int i=1;

                                           i < 2;

                                                         i++){

              for(int j=1;

                                           j < 2;

                                                         j++) {

                    System.out.println(i + " " + j);

              }}

              // Example 9

              for

              (

              int

              i

              =

              1

              ;

              i

             <

             2;

             i

             ++

             )

             {

             for

              (

              int

              j

             =

             1

              ;

               j

              <

              2

              ;

              j++

              )

              {

                    System.out.println(i + " ");

              }

              }

        }

}

Scenario 3 -

// Java Program for nested for-while loop

public class Scenario_3

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              for(int i=1; i <= 2; i++)

              {

                    int j=1;

                    while(j <= 2)

                    {

                          System.out.println(i + " " + j);

                          j++;

                    }

             }

             // Example 2

             for(int i=0; i < 2; i++)

             {

                   int j=1;

                   while(j <= 2)

                   {

                         System.out.println(i + " " + j);

                         j++;

                   }

             }

             // Example 3

             for(int i=5; i > 0; i--)

             {

                   for(int j=1; j <= 2; j++)

                   {

                          System.out.println(i + " " + j);

                   }

             }

             // Example 4

             int i=5;

             while(i >=1)

             {

                   for(int j=2; j > 0; j--)

                   {

                         System.out.println(i + " " + j);

                   }

                   i--;

              }

              // Example 5

              int i2=1;

              while(i2 <= 10)

              {

                    for(int j=1; j > 0; j=j+3)

                    {

                          System.out.println(i2 + " " + j);

                    }

                    i2=i2+2;

              }

              // Example 6

              for(int i3=5; i3 >=1; i3=i3-1)

              {

                    int j=10;

                    while(j > 0)

                    {

                          System.out.println(i3 + " " + j);

                           j=j-2;

                    }

              }

              // Example 7

              int a = 0 ;

              int i4=1;

              while(i4 < 2)

              {

                   for(int j=1; j < 2; j++)

                   {

                         a = 1;

                    }

                    i4++;

              }

              // Example 8

              for(int i5=1;

                                         i5 < 2;

                                                      i5++){int j=1;

               while(j < 2) {

                      System.out.println(i5 + " " + j);

               j++;}}

              // Example 9

              int

              i6

              =

              1

              ;

              while

              (

              i6

              <

              2

              )

              {

              for

              (

              int

              j

              =

              1

              ;

              j

             <

             2

              ;

              j++

              )

             {

                   System.out.println(i6 + " ");

             }

             i6  

             ++;

              }

        }

}

Scenario 4 -

// Java Program for nested for loop with Statement Terminator

public class Scenario_4

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              for(int i=1; i <= 2; i++)

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(i + " " + j);

                    }

              }

              // Example 2

              for(int i=1; i <= 2; i++)

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(i + " " + j);

                     }

              };

              // Example 3

              for(int i=1; i <= 2; i++) ;

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(1);

                    }

              }

              // Example 4

              for(int i=1; i <= 2; i++) ;

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(1);

                    }

              };

              // Example 5

             for(int i=1; i <= 2; i++)

             {

                   for(int j=1; j <= 2; j++) ;

                   {

                         System.out.println(1);

                   }

              }

              // Example 6

              for(int i=1; i <= 2; i++)

              {

                    for(int j=1; j <= 2; j++)

                    {

                          System.out.println(i + " " + j);

                    };

              }

              // Example 7

              for(int i=1; i <= 2; i++) ;

              {

                    for(int j=1; j <= 2; j++) ;

                    {

                          System.out.println(1);

                    };

              };

        }

}

Scenario 5:

// Java Program for nested for loop with Multiple Statements

public class Scenario_5

{

        // The following method will work        

        public static void main(String[] args)

        {

              int a = 211 ;

              for(int i=1; i <= 3; i++)

              {

                    for(int j=1; j <= 3; j++)

                          System.out.println(i + " " + j);

                    a++;

              }

              System.out.println(a);

        }

}

B) Basic Programs -

1) Write a Java Program to write a table of 1 and 2 till ten.

public class Table1And2TillTen_1

{

        public static void main(String[] args)

        {

              for(int i=1; i<3; i++)

              {

                    System.out.println("Table " + i + " : ");

                    for(int j=1; j<=10; j++)

                    {

                          System.out.print(i * j + " ");

                    }

                    System.out.print("\n\n");

              }

        }

}

Output:

Table 1 :

1 2 3 4 5 6 7 8 9 10

Table 2 :

2 4 6 8 10 12 14 16 18 20

Explanation:

In this Program, nested loops are used inside the main() method.

The Problem statement is to write a table of 1 and 2 till ten.

In the first for loop value, i is initialized with 1, and on each iteration, i should be less than 3 and the value of i will be increased by 1.

sysout statement will print the value of i along with a message.

In the inner for loop, this time, value j is initialized with 1, and on each iteration, j should be less than 10, and the value of the j will be increased by 1.

sysout statement inside the inner for loop will print the result of an expression.

At last, the sysout statement is used to provide an extra line.

To get a clearer picture of how the loop is working, let us understand the iteration scenarios below -

For i = 1,

      When j = 1 and 1 <= 10 then (1 * 1) = 1 so, j = j+1 = 1+1 = 2.

      When j = 2 and 2 <= 10 then (1 * 2) = 2 so, j = j+1 = 2+1 = 3.

      When j = 3 and 3 <= 10 then (1 * 3) = 3 so, j = j+1 = 3+1 = 4.

       .

       .

       .

      When j = 10 and 10 <= 10 then (1 * 10) = 10 so, j = j+1 = 10+1 = 11.

     When j = 11 and 11 <= 10, which is not true so the inner for loop will be terminated. Similarly, the values will be printed for i = 2 and i= 3.

2) Write a Java Program to find the Odd numbers from Table 5 to 7

      till five.

public class OddNumbersFromTable5to7TillFive_2

{

        public static void main(String[] args)

        {

              for(int i=5; i<8; i++)

              {

                    System.out.println("Odd Numbers from Table " + i + " : ");

                    for(int j=1; j<=10; j++)

                    {

                          if((i * j) % 2 != 0)

                           {

                                 System.out.print(i * j + " ");

                           }

                    }

                    System.out.print("\n\n");

              }

        }

}

Output:

Odd Numbers from Table 5 :

5 15 25 35 45

Odd Numbers from Table 6 :

Odd Numbers from Table 7 :

7 21 35 49 63

Explanation:

In this Program, nested loops are used inside the main() method.

The Problem statement is to find the Odd numbers from Table 5 to 7 till five.

In the first for loop value, i is initialized with 5, and on each iteratio-n, i should be less than 8 and the value of i will be increased by 1.

sysout statement will print the value of i along with a message.

In the inner for loop, this time, value j is initialized with 1, and on

each iteration, j should be less than 10, and the value of the j will be increased by 1.

Inside the second for loop, to check odd numbers, the number on

modular division by 2 should not be equal to 0.

sysout statement inside the inner for loop will print the result of an expression.

At last, the sysout statement is used to provide an extra line.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

For i = 5,

      When j = 1 and 1 <= 10 then (5 * 1) % 2 != 0 and so, j = j+1 = 1+1 = 2.

      When j = 2 and 2 <= 10 then (5 * 2) % 2 = 10 so, j = j+1 = 2+1 = 3.

      When j = 3 and 3 <= 10 then (5 * 3) % 2 != 15 so, j = j+1 = 3+1 = 4.

      .

      .

      .

      When j = 10 and 10 <= 10 then (5 * 10) % 2 = 0 so, j = j+1 = 10+1 = 11.

      When j = 11 and 11 <= 10, which is not true, the inner for loop will be terminated.

Similarly, the values will be printed for i = 6 and i= 7.

3)Write a Java Program to print all the Pairs from 1 to 10 whose sum

     is equal to 5.

public class PairSumEqualTo_3

{

        public static void main(String[] args)

        {     

              int k = 5 ;

              int i = 1 ;

              while(i <= 10)

              {

                    for(int j=i+1; j<=10 ; j++)

                    {

                          if(i + j == k)

                          {

                                System.out.println(i + " and " + j);

                          }

                    }

                     i++ ;

               }

        }

}

Output:

1 and 4

2 and 3

Explanation:

In this Program, nested loops are used inside the main() method.

The Problem statement is to print all the Pairs from 1 to 10 whose

sum is equal to 5.

Variable k of type int is initialized to 5.

The problem statement is to

The variable i is initialized with a value of 1 for the while loop iteration.

In the while loop on each iteration, i should be less than 10, and the i value will be increased by 1.

In the for loop on each iteration, j is declared and will be kept updated by adding 1 to the latest i value.

On each iteration, j should be less than 10, and the value of the j will be increased by 1.

To get pairs, i and j will be added, and if the sum is equal to 5, then

the block will be executed, and the sysout statement inside

the loop will print the i and j.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

For i = 1,

      When j = 2 and 2 <= 10 then (1 + 2) != 5 and so, j = j+1 = 2+1 = 3.

      When j = 3 and 3 <= 10 then (1 + 3) != 5 so, j = j+1 = 3+1 = 4.

      When j = 4 and 4 <= 10 then (1 + 4) = 5 so, j = j+1 = 4+1 = 5.

      .

      .

      .

      When j = 10 and 10 <= 10 then (1 + 10) != 5 so, j = j+1 = 10+1 = 11.

      When j = 11 and 11 <= 10, which is not true, the inner for loop will be terminated.

Similarly, for i = 2 to i= 10 the condition will be checked, and the pairs will be printed.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

       {

             for(int i = 1; i <= 5; i++)

             {

                   for(int j = 1; j <= 5; j++)

                   {

                         System.out.println(i + " " + j);

                   }

              }

      }

}

Output:

1 1

1 2

1 3

1 4

1 5

2 1

2 2

2 3

2 4

2 5

3 1

3 2

3 3

3 4

3 5

4 1

4 2

4 3

4 4

4 5

5 1

5 2

5 3

5 4

5 5

Explanation:

In this Program, nested loops are used inside the main() method.

In the first for loop, inside parenthesis, three parts are separated by a semicolon. In the first part, value i is initialized with 1\. In the

second part, i should be less than or equal to 5; in the third part,

the value i will be increased by 1.

Again, in the second inner for loop, inside the parenthesis, three

parts are separated by a semicolon. In the first part, value j is initialized with 1.

In the second part, j should be less than or equal to 5, and in the

third part, the value of j will be increased by 1.

sysout statement inside the inner for loop will print the value of i

and j on each iteration.

In this case, since the value maximum of i can be 5 and the maxim-um value of j can be 5, the total number of iterations will be 5 * 5 = 25.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

For i = 1,

      When j = 1 if 1 <= 5 then (1 * 1) = 1 so, j = j+1 = 1+1 = 2.

      When j = 2 if 2 <= 5 then (1 * 2) = 2 so, j = j+1 = 2+1 = 3.

      When j = 3 if 3 <= 5 then (1 * 3) = 3 so, j = j+1 = 3+1 = 4.

      When j = 4 if 4 <= 5 then (1 * 4) = 4 so, j = j+1 = 4+1 = 5.

      When j = 5 if 5 <= 5 then (1 * 5) = 5 so, j = j+1 = 5+1 = 6.

      When j = 6 if 6 <= 5, which is not true, the inner for loop will be terminated.

Similarly, the values will be printed for i = 2, i= 3, i=4 and i=5.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int weeks = 2;

              int days = 7;

              for(int i = 1; i <= weeks; ++i)

              {

                    for (int j = 1; j <= days; ++j)

                    {

                          System.out.println("Week : " + i + " " + "Day : " + j);

                    }

              }

        }

}

Output:

Week : 1 Day : 1

Week : 1 Day : 2

Week : 1 Day : 3

Week : 1 Day : 4

Week : 1 Day : 5

Week : 1 Day : 6

Week : 1 Day : 7

Week : 2 Day : 1

Week : 2 Day : 2

Week : 2 Day : 3

Week : 2 Day : 4

Week : 2 Day : 5

Week : 2 Day : 6

Week : 2 Day : 7

Explanation:

In this Program, nested loops are used inside the main() method.

Two variables, weeks and days, are declared of type int and initialized with values 2 and 7, respectively.

In the first for loop, inside parenthesis, three parts are separated by a semicolon. In the first part, value i is initialized with 1\. In the

second part, i should be less than or equal to weeks, which is 2, and

in the third part, the i value will be increased by 1.

Again in the second inner for loop, inside parenthesis, three parts

are separated by a semicolon. In the first part, value j is initialized with 1.

In the second part, j should be less than or equal to days, which is 7, and in the third part, the value of j will be increased by 1.

The sysout statement inside the inner for loop will print the value

of i and j and a message on each iteration.

Here, in this case, since the value maximum value of i can be 2 and

the maximum value of j can be 7 so total number of iterations will be 2 * 7 = 14.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

For i = 1,

      When j = 1 if 1 <= 7 then i = 1, j = 1 so, j = j+1 = 1+1 = 2.

      When j = 2 if 2 <= 7 then i = 1, j = 2 so, j = j+1 = 2+1 = 3.

      When j = 3 if 3 <= 7 then i = 1, j = 3 so, j = j+1 = 3+1 = 4.

      When j = 4 if 4 <= 7 then i = 1, j = 4 so, j = j+1 = 4+1 = 5.

      When j = 5 if 5 <= 7 then i = 1, j = 5 so, j = j+1 = 5+1 = 6.

      When j = 6 if 6 <= 7 then i = 1, j = 6 so, j = j+1 = 6+1 = 7.

      When j = 7 if 7 <= 7 then i = 1, j = 7 so, j = j+1 = 7+1 = 8.

      When j = 8 if 8 <= 7, which is not true, the inner for loop will be terminated.

Similarly, the values will be printed for i = 2, i= 3, i=4 and i=5.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

               int i = 1;

               int j = 1;

               while(i <= 5)

               {

                     while(j <= 5)

                     {

                           System.out.println(i + " " + j);

                           j++;

                     }

                     i++ ;

               }

        }

}

Output:

1 1

1 2

1 3

1 4

1 5

Explanation:

In this Program, nested loops are used inside the main() method.

For the first while loop, three parts are used separately.

In the first part, value i is initialized with 1\. In the second part,

inside the parenthesis, i should be less than or equal to 5, and in the third part, at the end of the loop, the value of i will be increased by 1.

Again, for the second while loop, three parts are used separately.

In the first part, value j is initialized with 1\. In the second part, inside

the parenthesis, j should be less than or equal to 5, and in the third

part, at the end of the loop, the value of j will be increased by 1.

sysout statement inside the inner while loop will print the value of i and j on each iteration.

Here, in this case, since the value maximum of i can be 5 and the

maximum value of j can be 5, the total number of iterations will be 5 * 5 = 25.

To get a clearer picture of how the loop is working, let us understan-d the iteration scenarios below -

For i = 1,

      When j = 1 if 1 <= 5 then i = 1, j = 1 so, j = j+1 = 1+1 = 2.

      When j = 2 if 2 <= 5 then i = 1, j = 2 so, j = j+1 = 2+1 = 3.

      When j = 3 if 3 <= 5 then i = 1, j = 3 so, j = j+1 = 3+1 = 4.

      When j = 4 if 4 <= 5 then i = 1, j = 4 so, j = j+1 = 4+1 = 5.

      When j = 5 if 5 <= 5 then i = 1, j = 5 so, j = j+1 = 5+1 = 6.

      When j = 6 if 6 <= 5, which is not true, the inner for loop will be terminated.

Similarly, for i = 2, i= 3, i=4, and i=5 the values will be printed.   

D) More Problems -

Write a Java Program to print all Months of the Year.

public class AllMonths_3

{

        public static void main(String[] args)

        {

              for(int i=2021; i <= 2022; i++)

              {

                    int j = 0;

                    while(j < 12)

                    {

                          if(j == 0)

                          {

                                System.out.println("Year : " + i + " Month : January");

                          }

                          if(j == 1)

                          {

                                System.out.println("Year : " + i + " Month : February");

                          }

                          if(j == 2)

                          {

                                System.out.println("Year : " + i + " Month : March");

                          }

                          if(j == 3)

                          {

                                System.out.println("Year : " + i + " Month : April");

                          }

                          if(j == 4)

                          {

                                System.out.println("Year : " + i + " Month : May");

                          }   

                          if(j == 5)

                          {

                                System.out.println("Year : " + i + " Month : June");

                          }

                          if(j == 6)

                          {

                                System.out.println("Year : " + i + " Month : July");

                          }

                          if(j == 7)

                          {

                                System.out.println("Year : " + i + " Month : August");

                          }

                          if(i == 8)

                          {

                                System.out.println("Year : " + i + " Month : September");

                          }

                          if(j == 9)

                          {

                                System.out.println("Year : " + i + " Month : October");

                          }

                          if(j == 10)

                          {

                                System.out.println("Year : " + i + " Month : November");

                          }

                          if(j == 11)

                          {

                                System.out.println("Year : " + i + " Month : December");

                          }

                          j = j + 1;

                    }

              }

        }

}

Output:

Year : 2021 Month : January

Year : 2021 Month : February

Year : 2021 Month : March

Year : 2021 Month : April

Year : 2021 Month : May

Year : 2021 Month : June

Year : 2021 Month : July

Year : 2021 Month : August

Year : 2021 Month : October

Year : 2021 Month : November

Year : 2021 Month : December

Year : 2022 Month : January

Year : 2022 Month : February

Year : 2022 Month : March

Year : 2022 Month : April

Year : 2022 Month : May

Year : 2022 Month : June

Year : 2022 Month : July

Year : 2022 Month : August

Year : 2022 Month : October

Year : 2022 Month : November

Year : 2022 Month : December

Explanation:

In this Program, inside the main() method, nested loop and

multiple if checks are used.

In the for loop, inside the parenthesis, three parts are separated by a semicolon. In the first part, value i is initialized with 2021\. In the

second part, i should be less than or equal to 2022, and in the third part, the value i will be incremented by 1 on each iteration.

For the while loop, three parts are used separately. In the first part,

value j is initialized with 0\. In the second part, inside the parenthes-is, i should be less than 12, and in the third part at the end of the

loop, the value of j will be incremented by 1.

On each iteration, any if check will pass, and the sysout statement

will print each month along with a year.

Here, in this case, since the value maximum value of i can be 2022

and it starts from 2021, and the maximum value of j can be 11

starts from 0, so the total number of iterations will be 2 * 12 = 24.

To get a more clear picture of how the loop is working, let us under-stand the iteration scenarios below -

For i = 2021,

      In the 1st iteration, When j = 0 if 1 < 12 then "January" so, j = j+1 = 0+1 = 1.

      In the 2nd iteration, When j = 1 if 2 < 12 then "February" so, j = j+1 = 1+1 = 2.

      In the 3rd iteration, When j = 2 if 3 < 12 then "March" so, j = j+1 = 2+1 = 3.

      .

      .

      .

      In the 12th iteration, When j = 11 if 11 < 12 then "December" so, j = j+1 = 11+1 = 12.

      In the 13th iteration, When j = 12, if 12 < 12, which is not true so the loop will be

            terminated.

Similarly, for i = 2022, all months and its year will be printed.

5) do-while:

There is a minor difference between the working of while and do-whie loops. This differences is the place where the condition is tested.

The while tested the condition before executing any of the statements within the while loop. As against this, the do-while tests the condition after having executed the statements within the loop.

do-while would executes its statemets at least once, even if the condition fails for the first time.

The while on the other hand will not execute its statements if the condition fails for the first time.

The general form is as follows...

        do     

        {    

              // statements    

         }

         while (condition);      

Working of the do-while loop Process Flow:

![](image_rsrc2XCB.jpg)

As can be seen in Fig. 7.5, whenever a program is written using the do-while loop, some iteration is taking place.

One extra syntax used here is the do block, where statements to be executed are kept inside.

This is similar to a while loop, but the main difference here is that first, whatever the statement is in the do loop, it will get executed.

The comparison part will not work for the first iteration. Apart from this difference, the process will work similar to the while loop.

The comparison inside the while condition will start from iteration 2.

Below are a few statements that represent Real-life scenarios. These can be represented using the do-while loop...

a) In a School Assembly, count the number of girls available out of the

      total number of Students, 150.

b) Find the total number of States of India out of 28, which starts from

     Alphabet 'M'.

c) Count the number of mobile devices in your home out of 15 electronic

     devices.   

d) Check how many teachers came today to school with a vehicle out of

      35.

e) Count how many family members have eaten Breakfast out of 6.

A) Programs Scenario -

Scenario 1 -

// Java Program for while loop with Multiple Statements

public class Scenario_1

{

        public static void main(String[] args)

        {

                // The following Examples will work

                // Example 1

                int i1 = 1;

                do

                {

                      System.out.print(i1 + " ");

                       i1++ ;

                }

               while(i1 < 3);

                     System.out.println();

                // Example 2

                int i2 = 0;

                do

                {

                      System.out.print(i2 + " ");

                       i2++ ;

                }

              while(i2 < 3);

                    System.out.println();

              // Example 3

              int i3 = 0;

              do

              {

                    System.out.print(i3 + " ");

                    i3++ ;

              }

              while(i3 <= 3);

                    System.out.println();

               // Example 4

               int i4 = 4;

               do

               {

                     System.out.print(i4 + " ");

                     i4-- ;

               }

               while(i4 > 0);

                     System.out.println();

               // Example 5

               int i5 = 4;

               do

               {

                     System.out.print(i5 + " ");

                     i5-- ;

              }

              while(i5 >= 0);

                    System.out.println();

              // Example 6

              int i6 = 0;

              do

              {

                    System.out.print(i6 + " ");

                    i6=i6+2 ;

              }

              while(i6 <= 10);

                    System.out.println();

        }

}

Scenario 2 -

public class Scenario_2

{

        public static void main(String[] args)

        {

              // The following Examples will work

              // Example 1

              int i1 = 1;

              do

              {

                    System.out.print(i1 + " ");

                    i1++ ;

              }

              while(i1 < 3);

                    System.out.println();

              // Example 2

              int i2 = 0;

              do

              {;

                    System.out.print(i2 + " ");

                    i2++ ;

              }

              while(i2 < 3);

                    System.out.println();

        }

}

Scenario 3 -

// Java Program for while loop with Multiple Statements

public class Scenario_3

{

        // The following method will work

        public static void main(String[] args)

        {

              int i=1;

              do

              {

                    int a = 211 ;

                   System.out.println(a);

                   a++;

              }

              while(i <= 3);

        }

}

B) Basic Programs -

1) Write a Java Program to print all the numbers from 1 to 10.

public class PrintNumbersFrom1To10_1

{

        public static void main(String[] args)

        {

              int i=1;

              do

              {

                    System.out.print(i + " ");

                     i++;

              }

              while(i < 11);

        }

}

Output:

1 2 3 4 5 6 7 8 9 10

Explanation:

In this Program, inside the main() method, a variable i of type int is declared and initialized with a value 1.

The problem statement is to print all the numbers from 1 to 10.

In a do-while loop, the first iteration will always execute without

any validation so that the sysout statement will print the value of i,

i.e., 1, and i++ will increment the value of i on each iteration.

From the next iteration, i will compare whether it is smaller than

11\. If the check passes, then the sysout statement will print the

value of i.

To get a clearer picture of how the do-while loop is working, let us

understand the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 < 11 then i = 1 and i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 11 then i = 2 and i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 11 then i = 3 and i = i+1 = 3+1 = 4.

.

.

.

In the 10th iteration, When i = 10 if 10 < 11 then i = 10 and i = i+1 = 10+1 = 11.

In the 11th iteration, When i = 11, if 11 < 11, which is not true so the loop will be

      terminated.

2) Write a Java Program is to print all the tables of 5 till five.

public class Table5TillFive_2

{

       public static void main(String[] args)

       {

             int i = 1;

             int n = 5;

             System.out.println("Table of 5 is : ");

             do

             {

                   System.out.println(n * i);

                    i++;

             }

             while(i <= 5);

        }

}

Output:

Table of 5 is :

5

10

15

20

25

Explanation:

In this Program, inside the main() method, a variable i of type int is declared and initialized with a value 1.

Another variable, n of type int, is declared and initialized with a

value of 5.

The problem statement is to print all the tables of 5 till five.

The first sysout statement will print the message.

In a do-while loop, the first iteration will always execute without

any validation, so the sysout statement inside will print the

result of an expression, and i++ will increment the value of i on each iteration.

From the next iteration, i will compare whether it is less than and

equal to 5\. If the check passes, then the sysout statement will

print the result of an expression by incrementing the value of i.

To get a clearer picture of how the do-while loop is working, let us

understand the iteration scenarios below -

In the 2nd iteration, When i = 1 then i = 1 and i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 11 then i = 2 and i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 11 then i = 3 and i = i+1 = 3+1 = 4.

.

.

.

In the 10th iteration, When i = 10 if 10 < 11 then i = 10 and i = i+1 = 10+1 = 11.

In the 11th iteration, When i = 11, if 11 < 11, which is not true so the loop will be

      terminated.

3) Write a Java Program to print all Even numbers from 1 to 10.

public class AllEvenNumbersTillFrom1to10_3

{

        public static void main(String[] args)

        {

               int i = 1;

               System.out.println("Even Numbers from 1 to 10 are : ");

              do

              {

                    if(i % 2 == 0)

                    {

                          System.out.print(i + " ");

                    }

                    i++;

              }

              while(i <= 10);

        }

}

Output:

Even Numbers from 1 to 10 are :

2 4 6 8 10

Explanation:

In this Program, inside the main() method, a variable i of type int is declared and initialized with a value 1.

The Problem statement is to print all Even numbers from 1 to 10.

The first sysout statement will print the message.

In a do-while loop, the first iteration will always execute without

any comparison, so the sysout statement inside will print the result of an expression if the check passes, and i++ will increment the i

value on each iteration.

From the next iteration, i will compare whether it is less than and

equal to 10\. If the condition is true, then the sysout statement will

print the value of i if the check passes.

To get a clearer picture here how the do-while loop is working, let's understand the iteration scenarios as below -

In the 1st iteration, When i = 1 if 1 <= 10 then (1 % 2) != 0 and i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 11 then (2 % 2) = 0 and i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 11 then (3 % 2) != 0 and i = i+1 = 3+1 = 4.

.

.

.

In the 10th iteration, When i = 10 if 10 < 11 then (10 % 2) = 0 and i = i+1 = 10+1 = 11.

In the 11th iteration, When i = 11, if 11 < 11, which is not true so the loop will be

      terminated.

C) Output Problems -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              do

              {

                    System.out.println("true");

              }

              while(true);

        }

}

Output:

Infinite loop

Explanation:

In this Program, inside the main() method, do-while is used.

In a do-while loop, the first iteration will always execute without

validation so that the sysout statement will print true.

Since while condition is always true and there is no restriction in

the form of a counter that how many times this loop will go so loop will execute for infinite times, i.e., true will be printed infinite times.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {  

              int i = 0;

              do

              {

                    System.out.println("Inside do loop");

                    i++;

              }

              while (i < 0);

        }

}

Output:

Inside do loop

Explanation:

In this Program, a do-while loop is used inside the main() method.

To keep control of the iteration of the do-while loop, i is declared of

type i and initialized to 0.

In a do-while loop, the first iteration will always execute without

any validation so that the sysout statement will print the message,

and i++ will increment the value i on each iteration.

From the next iteration inside the while condition, i will compare

whether it is smaller than 0\. If the check passes, then the sysout

statement will print the message again.

To get a clearer picture here how the do-while loop is working, let's understand the iteration scenarios as below -

In the 1st iteration, When i = 0 then i = 0 so, i = i+1 = 0+1 = 1.

In the 2nd iteration, When i = 1 if 1 < 0, which is not true so the loop will be

      terminated.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int i = 1;

              do

              {

                   System.out.println(i);

                   i++;

              }

              while (i < 6);

        }

}

Output:

1

2

3

4

5

Explanation:

In this Program, a do-while loop is used inside the main() method.

To keep control of the iteration of the do-while loop, i is declared of

type i and initialized to 1.

In a do-while loop, the first iteration will always execute without

validation so that the sysout statement will print the value of i, i.e., 1, and i++ will increment the i value on each iteration.

From the next iteration, i will compare whether it is smaller than 6. If the check passes, then the sysout statement will print the value of i.

To get a clearer picture of how the do-while loop is working, let us

understand the iteration scenarios below -

In the 1st iteration, When i = 1 if 1 < 6 then i = 1 so, i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 < 6 then i = 2 so, i = i+1 = 2+1 = 3.

In the 3rd iteration, When i = 3 if 3 < 6 then i = 3 so, i = i+1 = 3+1 = 4.

In the 4th iteration, When i = 4 if 4 < 6 then i = 4 so, i = i+1 = 4+1 = 5.

In the 5th iteration, When i = 5 if 5 < 6 then i = 5 so, i = i+1 = 5+1 = 6.

In the 6th iteration, When i = 6 if 6 < 6, which is not true so the loop will be

      terminated.

D) More Problems -

Write a Java Program to print the table of 7 from 1 to 10.

public class Table_1

{

        public static void main(String[] args)

        {

              int table = 7 ;

              int i = 1;

              do

              {

                    int multiplication = table * i ;

                    System.out.println(table + " * " + i + " = " + multiplication);

                    i++;

              }

              while(i <= 10);

        }

}

Output:

7 * 1 = 7

7 * 2 = 14

7 * 3 = 21

7 * 4 = 28

7 * 5 = 35

7 * 6 = 42

7 * 7 = 49

7 * 8 = 56

7 * 9 = 63

7 * 10 = 70

Explanation:

In this Program, inside the main() method, a do-while loop is used,

and a variable table of type int is declared and initialized to 7.

To keep control of the iteration of the do-while loop, i is declared of

type int and initialized to 1.

A variable multiplication is declared of type int to store the result of Table 7.

In a do-while loop, the first iteration will always execute without

validation so that the multiplication value will be updated.

On each iteration, the variable multiplication will keep updated by

the value of i and store the updated result, and the sysout statement will print

the value of multiplication of table 7 from 1 to 10.

Here in this case, since the value maximum value of i can be 10 so

the total number of iterations will be 10 only.

To get a more clear picture of how the loop is working, let us under-stand the iteration scenarios below -

In the 1st iteration, When i = 1 then multiplication = 7 * 1 = 7 so, i = i+1 = 1+1 = 2.

In the 2nd iteration, When i = 2 if 2 <= 10 then multiplication = 7 * 2 = 14 so, i = i+1 =

      2+1 = 3.

In the 3rd iteration, When i = 3 if 3 <= 10 then multiplication = 7 * 3 = 21 so, i = i+1 =

      3+1 = 4.

.

.

.

In the 10th iteration, When i = 10 if 10 <= 10 then multiplication = 7 * 10 = 70 so, i =

      i+1 = 10+1 = 11.

In the 11th iteration, When i = 11, if 11 <= 10, which is not true so the loop will be

      terminated.

◆◆◆

Exercise:-

1) Fill in the Blanks:-

a) When the while loop condition becomes _______, the control

    passes to the first statement that follows after the body of the while

   loop.

b) The condition being tested may use _______ or _______ operators.

c) There are in total _______ conditions for using any loop.

d) It is not necessary that a loop counter must only be an int. It can

      even be a ______.

e) In the _______ part, a declared variable is compared with some

     conditions.

2) State which of the following statements are true or false:-

a) Only for loop is used to iterate a part of the program several times.

b) It is not necessary that a loop counter must only be an int.

c) while loop and do-while loop are same.

d) When the condition becomes false, the control passes to the first

      statement that follows the body of the for loop.

e) while loop would executes its statemets at least once, even if the

     condition fails for the first time.

f) In the Comparison part, a declared variable is compared with some

     conditions.

3) Find and correct any syntax errors in the following programs:-

a) Program 1 -

public class Program_1

{

        public static void main(String[] args)

        {  

              for(int i; i=1; i <= 8; i++)

                    System.out.println(i + " ");

        }

}

b) Program 2 -

public class Program_2

{

        public static void main(String[] args)

        {

              for(int i=1; i <= 8; i++);

                    System.out.println(i + " ");

        }

}

c) Program 3 -

public class Program_3

{

        public static void main(String[] args)

        {

              for(int i; i <= 8; i++)

              int i=1;

        }

}

d) Program 4 -

public classProgram_4

{

        public static void main(String[] args)

        {  

              int i1 = 1;

              while(1 <= 2)

                    System.out.println(1);

                    i1++ ;

        }

}

e) Program 5 -

public class Program_5

{

        public static void main(String[] args)

        {  

              int i = 1;

              while(i <= 2)

                    i = i++ ;

        }

}

f) Program 6 -

public class Program_6

{

        public static void main(String[] args)

        {  

              int xyz = 1;

              while(xyz <= 2)

                    System.out.println(1);

                    xyz -- ;

        }

}

g) Program 7 -

public class Exercise_7

{

        public static void main(String[] args)

        {   

              int i = 0 ;

              for(i=1; i <= 2; i++)

                    while(i <= 2)

                          System.out.println(i);

                          i++;

        }

}

h) Program 8 -

public class Exercise_8

{

        public static void main(String[] args)

        {

              int ij = 0 ;

              for(ij=1; ij <= 2; ij--)

                    while(ij <= 2)

              System.out.println(ij);

        }

}

i) Program 9 -

public class Exercise_9

{

        public static void main(String[] args)

        {

              for(int j=1; j <= 10; j++)

              {

                    for(j=1; j <= 10; j++)

                    {

                          i == j;

                    }

              }

        }

}

j) Program 10 -

public class Program_10

{

        public static void main(String[] args)

        {

              int i = 1;

              while(i < 3);

              do

              {

                    System.out.print(i + " ");

                    i++ ;

              };

        }

}

k) Program 11 -

public class Program_11

{

        public static void main(String[] args)

        {

              int i = 1;

              do (i)

              {

                    System.out.print(i + " ");

                    i++ ;

              }

      }

}

l) Program 12 -

public class Program_12

{

        public static void main(String[] args)

        {

              int i = 1;

              do

              {

                    System.out.print(i + " ");

                     i = i -1 ; ;

              }

               while(i < 3);;;

        }

}

4) Answers to the following questions:-

a) What is nesting of loop?

b) what is the difference between while loop and do-while loop?

c) What do you mean by Initialization, Comparison and Incrementa

      tion of a integer while using in a loop.

d) Explain the working of three parts used to implement the while

      loop.

e) Explain the working of for loop.

5) Basic Programs:-

a) Write a Java Program to Find all the Factors of a Number.

      (Use only for loop)

b) Write a Java Program to Check if a Given Number is Perfect Square.

      (Use only for loop)

c) Write a Java Program to Find all the Factors of a Number.

      (Use only while loop)

d) Write a Java Program to Check if a Given Number is Perfect Square.

      (Use only while loop)

e) Write a Java Program to Find all the Factors of a Number between

      7 and 10. (Use nested loop)

f) Write a Java Program to Check if a Given Number between 4 to 10

      is Perfect Square. (Use nested loop)

g) Write a Java Program to print all the numbers from 100 to 1000.

       (Use only do-while loop)

h) Write a Java Program is to print all the tables of 66 till ten.

       (Use only do-while loop)

6) Output Problems:-

a) Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int i = 3;

              while(i <= 10)

              {

                    System.out.print(i + " ");

                    i++;

              }

        }

}

b) Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int i = 10;

              while(i > 1)

              {

                    System.out.println(i);

                    i--;

              }

        }

}

c) Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int num = 33 ;

              num ++;

              if((num*1+3) % 3 == 0)

              {

                    System.out.println("Divisible by 3");

              }

        }

}

d) Problem 4 -

public class Problem_4

{

        public static void main(String[] args)

        {

              for(int i=0 ; i <= 10; i++)

              {

                    System.out.print(i + " ");

              }

        }

}

e) Problem 5 -

public class Problem_5

{

        public static void main(String[] args)

        {

              int num = 25 ;

              for(int i=10 ; i < num; i++)

              {

                    if(i % 5 == 0)

                    {

                          System.out.print(i + " ");

                    }

              }

        }

}

f) Problem 6 -

public class Problem_6

{

        public static void main(String[] args)

        {

              int i=10 ;

              for(i >= 0)

              {

                    System.out.println(i);

                    i-- ;

              }

        }

}

g) Problem 7 -

public class Problem_7

{

        public static void main(String[] args)

        {

              for(int i =0; i < 5;)

              {

                    for(int j = 0; j < 5; j=j+1)

                    {

                          System.out.println(i + " " + j);

                    }

                    i = i + 1;

              }

        }

}

h) Problem 8 -

public class Problem_8

{

        public static void main(String[] args)

        {

               int i = 0;

               int j = 0;

               while(i < 5)

               {

                     while(j < 5)

                     {

                           System.out.println(i + " " + j);

                            j = j + 1;

                     }

                     i = i + 1 ;

              }

        }

}

i) Problem 9 -

public class Problem_9

{

        public static void main(String[] args)

        {

              int num = 3 ;

              int y = 0 ;

              int j = 1 ;

              while(j <= num)

              {

                    for(int i=0; i<num; i++)

                    {

                          y = y + 1 ;

                    }

                    j++ ;

              }

              System.out.println("The value of y is : " + y);

        }

}

j) Problem 10 -

public class Problem_10

{

        public static void main(String[] args)

        {

              do

              {

                    System.out.println("false");

              }

              while(false);

        }

}

k) Problem 11 -

public class Problem_11

{

        public static void main(String[] args)

        {

              do

              {

                    System.out.println("false");

              }

              while(false);

        }

}

l) Problem 12 -

public class Problem_12

{

        public static void main(String[] args)

        {

              int number = 0 ;

              while(number <= 15);

              do

              {

                    System.out.println(number);

              } ;           

        }

}

7) More Programs:-

Write a Java Program to calculate a sum of 100 Natural Numbers using the Loop Control Instructions below.

 a) Using only for loop

 b) Using only a while loop

 c) Using a Nested loop

 d) Using only do-while loop

8) Activity:-

Write a Program for the following statements that represent the daily use scenarios. (Assume different variables as needed to meet the conditions)

a) In a School Assembly, count the number of girls available out of

      the total number of Students, 150.      

      i) Using the for loop

      ii) Using the while loop

      iii) Using the do-while loop

b) Find the total number of States of India out of 28, which starts

      from Alphabet 'M'.

      i) Using the for loop

      ii) Using the while loop

      iii) Using the do-while loop

c) Count the number of mobile devices in your home out of 15 elec

     tronic devices.   

      i) Using the for loop

      ii) Using the while loop

      iii) Using the do-while loop

d) Check how many teachers came today to school with a vehicle out

      of 35.

      i) Using the for loop

      ii) Using the while loop

      iii) Using the do-while loop

e) Count how many family members have eaten Breakfast out of 6.

      i) Using the for loop

      ii) Using the while loop

      iii) Using the do-while loop

◆◆◆

8\. Case Control Instructions

This is another special Control statement that allows us to make a choice between different alternatives. Other types of Control instruction we have seen in Chapter 6\. All those programs can also be re-presenting switch control instructions in Java.

1) The break Statement:

break Statement is used to break any execution of Loop or case-control instruction.

Considering the simplicity of this Level 1, we have yet to cover break for Loop control instructions, but we will cover a little for the switch control statement as it is required to be used here. We will learn more about it and the programs around it in the Intermediate course.

The break statement when used in a switch takes a the control outside the switch.

2) switch Control Instructions:

A switch control instructions is the control statement that allows us to decide on the number of choices provided.

switch and case are the keywords in Java.

switch-case-default are the three keywords that together make the control statement.

We can use integers, boolean, String, and char values inside switch and case.

The general form is as follows...

         switch(expression)

         {     

               case value1:    

                     statements;

                     break;                       // optional  

               case value2:    

                     statements;

                     break;                      // optional  

               default:     

                     statements;

                     break;                       // optional  

         }

The expression should return a result as an integer, boolean, String, or char variable.

case statements are used after switch statements.

At least one case statement should be used.

A pair of Braces is optional if multiple states exist for each case.

There is no specific order in which case can be used. Any order can be maintained.

Each case should have a unique value as per the type of variable we passed in the switch condition.

The default statement is used at last; when any cases are not satisfied, the default statement will be executed.

All if condition that we have seen earlier can also be represented using switch statemnrts.

switch statements can also be used inside another switch called Nesting of a switch. Like we have seen for Nesting of if-else and nesting of loop.

The Flowchart which indiacte the flow of the switch conditions is shown in Fig. 8...

![](image_rsrc2XCC.jpg)

Working of the case control Instruction: What happens when we run a program containing a switch? First, the expression following the keyword switch is evaluated. The value it gives is them matched, one by one, against the constant values that follow the case statements. When a match is found, the program executes the statements following that case intial break is encountered. On encountering break the control goes outside the switch. If no match is found with any of the default are executed.

Below are a few statements that represent the daily use scenarios. These can be represented using the if condition...

a) Select one from the different multiple-choice questions.

b) Mom, I should go to school by walking, cycling, or taking a bus today.

c) Sir, where should I run a program on a mobile device, laptop, or tablet?

A) Program Scenarios -

Scenario 1 (Java Program with or without case) -

// Program with case

public class Scenario_1

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 3 :

                          System.out.println("This is case 3");

              }

        }

}

// Program without case

class Scenario_1_1

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

              }

        }

}

Scenario 2 (Java Program with multiple cases) -

// Program with multiple cases

public class Scenario_2

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 3 :

                          System.out.println("This is case 3");

                    case 4 :

                          System.out.println("This is case 4");

                    case 5 :

                          System.out.println("This is case 5");

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

Scenario 3 (Java Program with or without default) -

// Program with default

public class Scenario_3

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 4 :

                          System.out.println("This is case 3");

                          break;

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

// Program without default

class Scenario_3_1

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 4 :

                          System.out.println("This is case 4");

              }

        }

}

Scenario 4 (Java Program with or without break) -

// Program with break

public class Scenario_4

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 3 :

                          System.out.println("This is case 3");

                          break;

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

// Program without break

class Scenario_4_1

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 4 :

                          System.out.println("This is case 3");

                    default :

                           System.out.println("This is default");

              }

        }

}

B) Basic Programs -

1) Write a Java Program using switch case control instructions so

      that a string APPLE should belong to case 3 between different

      fruits like APPLE, MANGO, and BANANA.

public class Program_1

{

         public static void main(String[] args)

         {

               String fruit = "APPLE" ;

               switch (fruit)

               {

                     case "MANGO" :

                           System.out.println("I am in case 1");

                           break;

                     case "APPLE" :

                           System.out.println("APPLE is in case 2");

                           break;

                     case "BANANA" :

                           System.out.println("I am in case 3");

                           break;

                    default :

                          System.out.println("APPLE is not available");

                          break;

              }

        }

}

Output:

APPLE is in case 2

Explanation:

Inside the main method, the first statement used is to declare a

variable fruit of type String and has been initialized with APPLE.

switch-case has been used further where a string is sent inside the

switch condition to define the type of choices.

In the first case, a String MANGO is used, which is not equal to

APPLE, so this case will not be executed.

In the second case, a String APPLE is used, equal to APPLE, so that

this case will be executed and the sysout statement will print the

output.

Further cases and defaults will be skipped.

So, the final output is APPLE is in case 2.

2) Write a Java Program using switch case control instructions so

      that the number 3 should belong to no case but default between

      numbers 1, 3, and 4.

public class Program_2

{

        public static void main(String[] args)

        {

              int a = 3 ;

              switch (a)

              {

                    case 1 :

                          System.out.println("I am in case 1");

                          break;

                    case 2 :

                          System.out.println("I am in case 2");

                          break;

                    case 4 :

                          System.out.println("I am in case 4");

                          break;

                    default :

                          System.out.println("There is no case for 3");

                          break;

              }

        }

}

Output:

There is no case for 3

Explanation:

The problem statement is to write a program using switch case control instructions so that an integer 3 should belong to no case but

default.

Inside the main method, the first statement used is to declare a

variable a of type int. It has been initialized with a value of 3.

switch-case has been used further where an integer a is sent inside

the switch condition to define the type of choices.

In the first case, an integer 1 is used, which is not equal to 3, so this case will not be executed.

In the second case, an integer 2 is used, which is not equal to 3, so

this case will also not be executed.

In the third case, an integer 4 is used, which is not equal to 3, so this case will also not be executed.

Finally, if no cases were executed, the default will be executed, and

the sysout statement will print the output.

So, the final output is There is no case for 3.

3) Write a Java Program using switch case control instructions so

      that the number a char 'C' should belong to case C between chars   

      'c', 'D', and 'C'.

public class Program_3

{

        public static void main(String[] args)

        {

              char choice = 'C' ;

              switch (choice)

              {

                    case 'c' :

                          System.out.println("I am in case c");

                          break;

                    case 'D' :

                          System.out.println("I am in case D");

                          break;

                    case 'C' :

                          System.out.println("I am in case C");

                          break;

                    default :

                          System.out.println("There is no case for choice C");

                                break;

              }

        }

}

Output:

I am in case C

Explanation:

The problem statement is to write a program using switch case con-trol instructions so that a char 'C' should belong to case C.

Inside the main method, the first statement used is to declare a

variable choice of type char. It has been initialized with 'C'.

switch-case has been used further where a char is sent inside the

switch condition to define the type of choices.

In the first case, a char 'c' is used, which is not equal to 'C', so this

case will not be executed.

In the second case, a char 'D' is used, which is not equal to 'C', so

again, this case will also not be executed.

In the third case, a char 'C' is used, equal to 'C', so this case will get

executed, and the sysout statement will print the output.

default will be skipped.

So, the final output is I am in case C.

C) Output Programs -

Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int i = 3 ;

              switch (i)

              {

                    case 1 :

                          System.out.println("This is case 1");

                          break;

                    case 2 :

                          System.out.println("This is case 2");

                          break;

                    case 3 :

                          System.out.println("This is case 3");

                          break;

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

Output:

This is case 3

Explanation:

The problem statement is to write a program using switch case

control instructions so that an integer 3 should belong to no case but

default.

Inside the main method, the first statement used is to declare a

variable i of type int. It has been initialized with a value of 3.

switch-case has been used further where an integer i is sent inside

the switch condition to define the type of choices.

In the first case, an integer 1 is used, which is not equal to 3, so this case will not be executed.

In the second case, an integer 2 is used, which is not equal to 3, so

this case will also not be executed.

In the third case, the integer 3 is used, equal to 3, so this case will be executed, and the sysout statement will print the output.

So, the final output is There is no case for 3.

Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int i = 99 ;

              switch (i)

              {

                    case 99 :

                          System.out.println("This is case 99");

                          break;

                    case 98 :

                          System.out.println("This is case 98");

                          break;

                    case 999 :

                          System.out.println("This is case 999");

                          break;

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

Output:

This is case 99

Explanation:

The problem statement is to write a program using switch case

control instructions so that an integer 99 should belong to case 99.

Inside the main method, the first statement used is to declare a

variable i of type int. It has been initialized with a value of 99.

switch-case has been used further where an integer i is sent inside

the switch condition to define the type of choices.

In the first case, an integer 99 is used, which is not equal to 99, so

this case will be executed, and the sysout statement will print the

output.

Further all cases will be skipped.

So, the final output is This is case 99.

Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              char c = 's' ;

              switch (c)

              {

                    case 'w' :

                          System.out.println("This is case w");

                          break;

                    case 's' :

                          System.out.println("This is case s");

                          break;

                    case 'f' :

                          System.out.println("This is case f");

                          break;

                    default :

                          System.out.println("This is case default");

                          break;

              }

        }

}

Output:

This is case s

Explanation:

The problem statement is to write a program using switch case

control instructions so that a char 'C' should belong to case C.

Inside the main method, the first statement used is to declare a

variable choice of type char. It has been initialized with 'C'.

switch-case has been used further where a char is sent inside the

switch condition to define the type of choices.

In the first case, a char 'c' is used, which is not equal to 'C', so this

case will not be executed.

In the second case, a char 'D' is used, which is not equal to 'C', so

again, this case will also not be executed.

In the third case, a char 'C' is used, equal to 'C', so this case will get

executed, and the sysout statement will print the output.

default will be skipped.

So, the final output is I am in case C.

◆◆◆

Exercise:-

1) Fill in the Blanks:-

a) The _______ Statement is used to break any execution of Loop or

      case-control instruction.

b) Each case should have a _______ value as per the type of variable

      we passed in the switch condition.

c) At least _______ case statement should be used.

d) We can use _______, _______, _______, and _______ values inside

      switch and case.  

e) A _______ is optional if multiple states exist for each case.

2) State which of the following statements are true or false:-

a) The break statement, when used in a switch, takes control outside

     of the method.

b) In a switch Control Instructions, there can be zero case and one

      default.

 c) Nesting of case-control instruction is possible in Java.

d) A program can print output without using default.

e) A particular order must be followed to use cases inside the switch.

3) Find and correct any syntax errors in the following programs:-

a) Program 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              switch (int i = 3)

              {

                    case 0 :

                          System.out.println("This is case 0");

              }

        }

}

b) Program 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int integer = 21 ;

              switch (integer)

              {

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

c) Program 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              int i = 5 ;

              switch (i)

              {

                    default :

                          System.out.println("This is default");

                          break;

                    case 00 :

                          System.out.println("This is case 3");

                           break;

              }

        }

}

4) Answers to the following questions:-

a) Which two keywords are used to write switch control instruc-

      tions?

b) Which of the three keywords together make the control state-

      ment?

c) How does case-control instruction work in Java?

d) What is the Nesting of switch statements?

e) Why is the break statement used in Java?

5) Basic Programs:-

a) Write a Java Program using switch case control instructions so

     that a fruit APPLE of type string should belong to case 2 between

     among others fruits like APPLE, MANGO, and BANANA.

public class Program_1

{

        public static void main(String[] args)

        {

              String CoreJavaLevel = "Level 1" ;

              switch (CoreJavaLevel)

              {

                    case "Level 1" :

                          System.out.println("This is Level 1");

                          break;

                    case "Level 2" :

                           System.out.println("This is Level 2");

                           break;

                    case "Level 3" :

                          System.out.println("This is Level 3");

                          break;

                    default :

                          System.out.println("Level 1 is not available");

                          break;

              }

        }

}

b) Write a Java Programs use switch case control instructions so that

     an integer 3 should belong to no case but default among another

     integer like 1, 2, 3, and 4.

public class Program_2

{

        public static void main(String[] args)

        {

              String s = "DEFAULT" ;

              switch (s)

              {

                    case "default" :

                          System.out.println("This is case default");

                          break;

                    default :

                          System.out.println("DEFAULT is in default");

                          break;

              }

        }

}   

c) Write a Java Program using switch case control instructions so

     that a char 'C' should belong to case C among 'c', 'D' and 'C'.

public class Program_3

{

         public static void main(String[] args)

         {

               int standard = 8 ;

               switch (standard)

               {

                     case 0 :

                           System.out.println("This is Level 0");

                           break;

                     case 8 :

                           System.out.println("This is Level 8");

                           break;

                     case 16 :

                           System.out.println("This is Level 16");

                           break;

                    default :

                          System.out.println("Standard 8 is not available");

                          break;

              }

        }

}

6) Output Problems:-

a) Problem 1 -

public class Problem_1

{

        public static void main(String[] args)

        {

              int i = 33 ;

              switch (i)

              {

                    case 1 :

                          System.out.println("This is case 1");

                          break;

                    case 2 :

                          System.out.println("This is case 2");

                           break;

                    case 3 :

                          System.out.println("This is case 3");

                          break;

              }

        }

}

b) Problem 2 -

public class Problem_2

{

        public static void main(String[] args)

        {

              int i = 21 ;

              switch (21)

              {

                    case 21 :

                          System.out.println("This is case 21");

                          break;

                    case 21 :

                          System.out.println("This is case 21");

                          break;

                    case 2121 :

                          System.out.println("This is case 2121");

                          break;

                    default :

                          System.out.println("This is default");

                          break;

              }

        }

}

c) Problem 3 -

public class Problem_3

{

        public static void main(String[] args)

        {

              char c0000 = '0' ;

              switch (c0000)

              {

                    case '2' :

                          System.out.println("This is case 2");

                          break;

                    case '1' :

                          System.out.println("This is case 1");

                          break;

                    case '0' :

                          System.out.println("This is case 0");

                          break;

                    default :

                           System.out.println("This is case default");

                           break;

              }

        }

}

7) Activity:-

Write a Program for the following statements that represent the daily use scenarios. (use only switch-case Instructions) (Assume different variables as needed to meet the conditions)

a) Select one from the different multiple-choice questions between

     options a, b, c, and d. The correct option is b.

b) Mom, I should go to school by walking, cycling, or taking a bus

     today. Mom said you should go Cycling.

c) Sir, where should I run a program on a mobile device, Laptop, or

     tablet? He says to run on the Laptop.

◆◆◆

Questions

If you feel any of the content or topics needs improvement, or if you need any help or clarification or have any doubts about any topic, please write to us at CJL1@shinenriseindia.com.

![](image_rsrc2XCD.jpg)

Feedback

If you enjoyed reading this book and found it helpful for learning Java Programming, please show your love by emailing us at feedback@shinenriseindia.com.

![](image_rsrc2XCE.jpg)

Afterword

![](image_rsrc2XCF.jpg)

I believe my work will always remain incomplete without taking blessing of my Big Brother, who is not in between us. I sincerely show gratitude to him everywhere he is.

When I started working towards Shine N Rise  to transform lives and careers, he passed away just a few days later. Initially, it was difficult to continue the work. However, I eventually found strong reasons and purposes that motivated me to focus on skill development programs for a greater cause and vision. Your love and support are essential towards  inspiring and impacting small lives.

     We will always stay connected forever...

About The Author

Sunshine

![](image_rsrc2XCG.jpg)

This has been written by an experienced professional who has worked for different multinational companies in several domains as a developer and has provided solutions to many clients.

Books By This Author

Peace N Hope

Our Brands

Please follow us and support us to help us grow.

![](image_rsrc2XCH.jpg)