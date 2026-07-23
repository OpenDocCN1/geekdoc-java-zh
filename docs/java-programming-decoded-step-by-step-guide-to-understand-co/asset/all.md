![](image_rsrc4ZP.jpg)

JAVA PROGRAMMING DECODED

## STEP-BY-STEP GUIDE TO UNDERSTAND COMPLEX CODE, GRASP CORE CONCEPTS, AND ACE THE DEBUGGING GAME

## N. N. HOLMES

© Copyright 2024 – All rights reserved.

The content contained within this book may not be reproduced, duplicated, or transmitted without direct written permission from the author or the publisher.

Under no circumstances will any blame or legal responsibility be held against the publisher or author for any damages, reparation, or monetary loss due to the information contained within this book, either directly or indirectly.

Legal Notice:

This book is copyright-protected. It is only for personal use. You cannot amend, distribute, sell, use, quote, or paraphrase any part of the content within this book without the consent of the author or publisher.

Disclaimer Notice:

Please note the information contained within this document is for educational and entertainment purposes only. All effort has been executed to present accurate, up-to-date, reliable, and complete information. No warranties of any kind are declared or implied. Readers acknowledge that the author is not engaged in the rendering of legal, financial, medical, or professional advice. The content within this book has been derived from various sources. Please consult a licensed professional before attempting any techniques outlined in this book.

By reading this document, the reader agrees that under no circumstances is the author responsible for any losses, direct or indirect, that are incurred as a result of the use of the information contained within this document, including, but not limited to, errors, omissions, or inaccuracies.

CONTENTS

[Introduction](#part0004.xhtml)

1\. [Getting Started With Java](#part0005.xhtml)

[Introduction to Programming](#part0005.xhtml_a4P8)

[Java Overview](#part0005.xhtml_a4P9)

[Installing Java Development Kit](#part0005.xhtml_a4PA)

[Writing Your First Java Program](#part0005.xhtml_a4PB)

[Basic Syntax](#part0005.xhtml_a4PC)

[Compiling and Running Java Programs](#part0005.xhtml_a4PD)

[Your Turn to Try!](#part0005.xhtml_a4PE)

2\. [Variables and Data Types](#part0006.xhtml)

[Variables and Constants](#part0006.xhtml_a4PG)

[Primitive Data Types](#part0006.xhtml_a4PH)

[Type Conversion and Casting](#part0006.xhtml_a4PJ)

[Working With Strings and Common String Operations](#part0006.xhtml_a4PK)

[Your Turn to Try!](#part0006.xhtml_a4PM)

3\. [Control Flow](#part0007.xhtml)

[Conditional Statements](#part0007.xhtml_a4PP)

[Looping Structures](#part0007.xhtml_a4PR)

[Break and Continue Statements](#part0007.xhtml_a4PS)

[Nested Loops and Control Flow](#part0007.xhtml_a4PT)

[Introduction to Logical Operators](#part0007.xhtml_a4PU)

[Your Turn to Try!](#part0007.xhtml_a4PV)

4\. [Arrays and Collections](#part0008.xhtml)

[Introduction to Arrays](#part0008.xhtml_a4PX)

[Introduction to Collections](#part0008.xhtml_a4PY)

[Your Turn to Try!](#part0008.xhtml_a4PZ)

5\. [Mastering Methods in Java](#part0009.xhtml)

[Introduction to Methods](#part0009.xhtml_a4R1)

[Declaring and Calling Methods](#part0009.xhtml_a4R2)

[Understanding Method Parameters and Return Types](#part0009.xhtml_a4R3)

[Method Overloading](#part0009.xhtml_a4R4)

[The Scope of Variables](#part0009.xhtml_a4R5)

[Recursive Methods](#part0009.xhtml_a4R6)

[Your Turn to Try!](#part0009.xhtml_a4R7)

6\. [Object-Oriented Programming](#part0010.xhtml)

[Introduction to OOP](#part0010.xhtml_a4R9)

[Classes and Objects](#part0010.xhtml_a4RA)

[Encapsulation and Information Hiding](#part0010.xhtml_a4RB)

[Inheritance and Polymorphism](#part0010.xhtml_a4RC)

[Abstract Classes and Interfaces](#part0010.xhtml_a4RD)

[Working With Objects](#part0010.xhtml_a4RE)

[Let's Test Your Knowledge!](#part0010.xhtml_a4RF)

7\. [Exception Handling](#part0012.xhtml)

[Understanding Exceptions](#part0012.xhtml_a4RJ)

[Handling Exceptions With Try and Catch](#part0012.xhtml_a4RK)

[The Finally Block](#part0012.xhtml_a4RM)

[Throwing Exceptions](#part0012.xhtml_a4RN)

[Creating Custom Exceptions](#part0012.xhtml_a4RP)

8\. [File Input and Output](#part0013.xhtml)

[Working With Files in Java](#part0013.xhtml_a4RS)

[Reading and Writing Text Files](#part0013.xhtml_a4RT)

[Serialization and Deserialization](#part0013.xhtml_a4RU)

[Working With Binary Files](#part0013.xhtml_a4RV)

[Your Turn to Try!](#part0013.xhtml_a4RW)

9\. [Introduction to Java APIs](#part0014.xhtml)

[Overview of Java APIs](#part0014.xhtml_a4RY)

[Working With the String API](#part0014.xhtml_a4RZ)

[Manipulating Dates and Times With the Date and Time API](#part0014.xhtml_a4S0)

[Using the Math Random APIs](#part0014.xhtml_a4S1)

[Introduction to Java Collections Framework](#part0014.xhtml_a4S2)

[Let's Test Your Knowledge!](#part0014.xhtml_a4S3)

10\. [Introduction to Graphical User Interface Programming](#part0015.xhtml)

[Introduction to GUI](#part0015.xhtml_a4S5)

[Swing Framework and Components](#part0015.xhtml_a4S6)

[Creating GUI Applications](#part0015.xhtml_a4S7)

[Event Handling and Listener Interfaces](#part0015.xhtml_a4S8)

[Introduction to JavaFX](#part0015.xhtml_a4S9)

[Your Turn to Try!](#part0015.xhtml_a4SA)

11\. [Introduction to Networking](#part0016.xhtml)

[Introduction to Network Programming](#part0016.xhtml_a4SC)

[Working With URLs and Sockets](#part0016.xhtml_a4SD)

[Creating Client-Server Applications](#part0016.xhtml_a4SE)

[Communicating Over a Network](#part0016.xhtml_a4SF)

[Your Turn to Try!](#part0016.xhtml_a4SG)

12\. [Debugging and Testing](#part0017.xhtml)

[Introduction to Debugging](#part0017.xhtml_a4SJ)

[Using Debugging Tools and Techniques](#part0017.xhtml_a4SK)

[Unit Testing With JUnit Framework](#part0017.xhtml_a4SM)

[Writing Test Cases](#part0017.xhtml_a4SN)

[Let's Test Your Knowledge!](#part0017.xhtml_a4SP)

[Conclusion](#part0019.xhtml)

[Appendix](#part0020.xhtml)

[Answers](#part0021.xhtml)

[References](#part0022.xhtml)

INTRODUCTION

Imagine you are sitting in front of your computer, eyes wide open, heart pounding, as you watch the Mars Perseverance rover land safely on the red planet. A technological marvel millions of miles away, orchestrated by a team of NASA scientists on Earth. The joy, the relief, the exhilaration you feel is palpable. What if I told you that the software controlling that rover, making that historic moment possible, was written mainly in Java? (Reuters, 2004). Astonishing, isn't it?

In the world of ever-changing technology, and with new information becoming available almost as fast as we can blink, it might be the case that some people believe "older" technology will become irrelevant. The languages used for software development are constantly in the middle of this debate. With the number of developers using "new" dialects such as Python, Go, Kotlin, and Rust increasing, many question whether there is still space for a decades-old technology like Java.

According to a survey by JetBrains (2023) in 2022, Java remains one of the most popular programming languages, with a usage rate of about 50% among professional developers. To 31%, Java is their primary programming language and had been used at some point in the 12 months preceding the survey. To 16%, Java is their favorite programming language, the second most popular, losing only to Python (JetBrains, 2023).

On the other hand, the same study also reveals that approximately 35% of novice Java programmers find it challenging to understand complex code and debug it efficiently. This data underlines the need for comprehensive resources that can guide you through the intricacies of Java, and that's precisely what this book is designed to do. Most of the people who code in Java have learned the language in an educational institution, which, most of the time, cannot show the students the versatility the language can bring to software development.

This is where this book comes in. It has been developed as a comprehensive guide to help aspiring Java developers and those who have been in the market for some time decode the secrets of coding by using it. From understanding the core concepts of the language to learning how to debug and test the programs you created efficiently, all the information you need to propel your career as a professional Java developer will be found in this book.

Here are some benefits for those reading this book:

*   Fast-track learning: This book is an express elevator to the top floors of Java programming knowledge. It eliminates the necessity of wading through a sea of disjointed online resources and provides a structured and comprehensive learning journey.

*   Practical code examples: The book is laden with practical examples of code, guiding you through understanding and writing Java code. This hands-on approach will help you learn faster and better.

*   Understand core concepts: Break down complex Java programming jargon and concepts into digestible bites. Grasp the core concepts that form the basis of Java programming, solidifying your foundation.

*   Demystify debugging: Debugging can be a daunting task for beginners. With this guide, you'll acquire effective debugging strategies to help you handle errors confidently and improve your code quality.

*   Introduction to advanced topics: Venture beyond the basics with a primer on advanced Java topics such as networking and graphical user interface (GUI) programming. This equips you to take on more complex projects and expand your skills.

*   Career preparation: Whether you're aspiring to land a job in a top tech firm or considering launching your app, the skills you'll acquire from this book will significantly enhance your portfolio and employability.

In addition to all the previously mentioned benefits, this comprehensive guide is written in an easy-to-understand and accessible language for professionals of all different levels. Starting in the first chapter, the straightforward approach to writing code will motivate you to continue learning and developing your skills. As you continue to read, you will undoubtedly feel motivated to continue as you see the content you have learned implemented in the provided exercises.

If you are new to the programming world and unsure if this is the right book for you, rest assured you will find the information you seek. The concepts in this book are applicable to beginners starting their journey, as well as more experienced developers who want to review what they know and increase their knowledge. The first stop of this journey will be to understand what Java is and what you need to start coding today.

## WHAT IS JAVA?

Java is a programming language created in 1995 by Sun Microsystems, currently on version 21\. However, this is not the version used by most developers, who prefer Java 8, 11, or 7\. Java is used in the development of several different applications, including mobile device applications, medical devices, and websites. Although the name is similar, Java should not be confused with JavaScript. While both technologies are a development language, this and the name are their only similarities.

One of Java's main characteristics is that it is an object-oriented language, which means that rather than using logic and functions in the code, it is designed around data, or "objects," that establish the attributes and the message a program needs to send. For comparison's sake, it is possible to say that the syntax and rules applied by Java are based on those observed in the C and C++ languages.

The central premise that rules Java is that it enables the developer to "write once, run anywhere." This description is the foundation stone of the language since its main objective is to be a portable language, easily transported between devices. In addition, Java's versatility enables it to be used with any operating system (Android, Linux, iOS, or Windows) and have the platform change if needed without needing to adjust the code.

Because Java has been around for so long, another advantage the beginner will find is its huge online community. However, this community is not only restricted to the users who support each other but also includes libraries, repositories, and troubleshooting information and documentation that enable an efficient problem-solving approach. Essentially speaking, when you start learning Java, you will find you have access to numerous tools and resources to help you during the development and debugging process.

## PREREQUISITES TO LEARN AND START WORKING WITH JAVA

Although some people say that you must have at least certain experience with programming to learn Java, this is not necessarily true. While those who do have it might have an advantage in understanding the concepts and be more familiarized with the logic of object-oriented programming (OOP), this does not mean that, as a beginner, you will be able to learn. In fact, many people find it easier to learn Java without experience because they do not have any previous context to confuse them.

Another concern is the need for a powerful computer to process incredible amounts of information. While this is undoubtedly an advantage, it is optional for learning Java. In fact, some developers have machines with average processing capacity and memory and do just fine. Additionally, while most professionals work with integrated development environments (IDEs), it is possible to start coding in Java with the notepad available on your computer.

This book teaches you how to set up and use the Java IDE, which will later help you debug and learn more advanced tools. However, if you cannot set it up on your computer, there is no need to worry! You can use your computer notepad to develop and run the code later; the only difference is that you might have more difficulty debugging and finding code errors when you test what you have written.

If you are ready to start your journey into learning one of the most relevant programming languages in the market, then I encourage you to read on! It is recommended you keep your computer next to you while reading to practice the code and any other techniques being taught. We will start with a small introduction to Java applications and how to set up the different development environments on your computer. Hence, you will be fully prepared to start writing your first code lines!

CHAPTER 1

GETTING STARTED WITH JAVA

If you are just beginning your programming journey, you might be curious about some of the digital applications that use Java in their structures. You might not be surprised that, since it is such a popular language, platforms such as Amazon, Netflix, Spotify, Santander, Airbnb, and Goldman Sachs use Java in their programs. In fact, according to Svet (2023), 90% of Fortune 500 companies resort to Java as their preferred programming language when developing new software.

In this chapter, we will explore the history behind the start of programming and how Java became the significant language it is today in the computer science community. In addition, you will learn how to install your Java development environment, set up everything you need, and, as promised, write your first code! You will learn the basics of writing, compiling, and running a simple program and understanding basic Java syntax, which will help you navigate the remainder of the chapters in this book.

To make the learning process easier, it is highly recommended that you have your computer next to you so you can follow the step-by-step processes. Carrying out the suggested tasks, processes, and coding examples as you read is a great way to ensure you have understood the concepts and are carrying them out correctly. Now, without further delay, let's start our journey into the world of programming and, more specifically, Java.

## INTRODUCTION TO PROGRAMMING

To understand programming, I want you to think about the following: Suppose you bought a piece of furniture you need to assemble. Since most of us are not experts on the subject, we will need an instruction manual to follow what must be done to achieve the desired result. This applies not only to furniture but also to any task you do not have the required knowledge to complete and need guidance on to ensure the outcome is the expected one: cooking, driving, etc.

The same logic can be applied to programming: The computer does not know what you want it to do or how it performs unless you tell it what to do and how to do it. This is where coding comes in: It uses a specific language or code to tell a program or computer what it should do according to specific instructions. You can use this code to tell the computer how to solve a problem, process information, and do several other tasks.

However, computers do not usually "understand" human language. This means that, for example, you can't just say create a program that will solve math equations for me when creating software. The computer will not understand this because they have a specific language, or languages, also known as dialects, that are used to communicate with it. These dialects will "translate" what we, humans, want the machine to do by transforming our language into one that the computer understands. These include, for example, Python, Go, Rust, NodeJS, Elixir, C, C++, and, of course, Java.

By using these languages to instruct and "program" computers, developers can tell them what they should do. From the simplest tasks, such as opening word-processing software on your computer, to having computers mimic human language in artificial intelligence applications, these are all done using programming languages. Almost everything that has to do with computer use involves a programming language.

Now, here is the crucial part and where this book comes in: When you want to "communicate" with a computer, so to say, you are going to use one of the languages that allows you to do this. And your language choice will depend on two things: 1\. What you are comfortable with, and 2\. What it is you need to do. In this case, the language choice will directly reflect your personal preference, what you adapt to the most, and, more importantly, the market in which you want to act.

Granted, some languages are considered easier to learn, and others are harder. However, it would be irresponsible to classify them since each reader has their preferences. This being said, as we move further along in this chapter we will explain Java's main characteristics and its differences in comparison to other available languages.

According to Coursera (2023), programming languages can be grouped into these five categories:

1.  Scripting languages

2.  Procedural programming languages

3.  Logic programming languages

4.  Functional programming languages

5.  OOP languages

This might raise the question, In which group does Java fit? That is an excellent point. Let's examine which categories Java fits in and start exploring its characteristics.

## JAVA OVERVIEW

Java is known for being one of the most crucial programming languages when referring to those that are object-oriented. When it was released in 1995, Java "had few elements that were revolutionary, but the key to its success was combining those elements in the right way and learning from predecessors' strengths and weaknesses. Microsoft later used this approach in developing C# by utilizing Java's experience" (Izydorczyk, 2022). As you might imagine, the successful approach led to significant attention in the developer market, and many people learned how to use it.

It would also be impossible to speak about Java and not mention the previous "motto" of write once, run everywhere (WORA) for which it was known, despite this not being as accurate in the present. This was a significant advantage at the time, which meant you could run programs developed with Java on all supported platforms without needing to adjust or recompile the code. With the need to increase accessibility to technology and develop more software, this became another point that attracted many people to work with it and companies to implement it.

In fact, many companies continue to use Java in their programs because of the incredible number of developers with knowledge of it and its reliability. In addition, the language is constantly being updated and improved, which means it evolves and adapts to the market as it changes. The versatility it provides the developer to adapt to most situations remains an attractive attribute that makes learning how to code in Java a valuable skill in the technology market.

Finally, it is crucial to mention that Java's "age" has become one of its most important assets. "Java encourages maturity of solutions and has a large community. It's hard to find technologies without prepared integration with Java or functions that aren't provided by external libraries" (Izydorczyk, 2022). This means that even if you are interested in learning more "modern" languages, such as Kotlin, having previous knowledge of Java will make the journey easier, as will happen with other dialects.

Now that you have a clear picture of Java's characteristics, it is time to start getting to work. The first thing you will need to do is install what is known as the Java Development Kit (JDK), which you will need to write the code. Shall we look into what it is and the need to carry out this process?

## INSTALLING JAVA DEVELOPMENT KIT

To start working with Java, you will need to download the JDK to your computer. Returning to our furniture-building analogy, the JDK is similar to needing a hammer and screwdriver to assemble the piece. Or like the pans, stove, and spoons for cooking. Essentially speaking, the JDK will provide the tools you need to write, compile, and run your code in Java. "The Java Development Kit (JDK) is one of three core technology packages used in Java programming, along with the JVM (Java Virtual Machine) and the JRE (Java Runtime Environment)" (Tyson, 2022). These three parts of the Java technology can be described as follows:

*   JDK: Used to develop the software or simply write, compile, and execute the code, providing the necessary tools to enable the program to run in the JRE and the JVM.

*   JRE: Used to run the developed code and is part of the JDK kit since you will need to run the code to ensure it works.

*   JVM: Used to host the program where the code will be run, "translating" the commands you have given into a language the computer can understand and interpret, enabling it to carry out the instructions.

Now that you know the essential components to set up the Java environment, let's look at the steps to install them.

1\. Go to the [Oracle.com](http://Oracle.com) website.

2\. On the top tab, under "Products," go to the last section,     "Hardware and Software," and click on "Java."

3\. Click on the "Download Java" button.

4\. Under the "Java downloads" section, select between the     JDK 21 or 17 and the operating system (OS) you use     (Linux, macOS, or Windows).

5\. Select the kit you will download according to your     computer's specifications and needs.

Note: In this book, the instructions will be based on the Windows OS. However, you can find the specifications for any different OS in the documentation provided on the website.

6\. Ensure you have a 64-bit operating Windows platform to     download the kit.

7\. Select the link within the provided list to start     downloading. You will need to sign a license agreement     and save an executable (.exe) file on your computer     according to the version of Windows you are using.

8\. Once the .exe file has been saved on your computer,     double-click to open it and start installing the program.     You will need to select the location where you are going     to save it. (The program provides a step-by-step screen     process that will help you carry out each of the actions.)

You will receive a message informing you the program has been correctly downloaded once the installation is finalized and the files have been saved to the computer. The process is now almost done! And you are about to learn why it is almost and not complete.

While it is perfectly acceptable to write and compile your code simply using the JDK, it is improbable that this method will be used in any company you may work for. Most, if not all, Java developers use IDEs. An IDE is a great facilitator for those coding and creating programs because it enables several different functions to be carried out in the same place, such as compiling, debugging, and testing.

By using an IDE, you not only save time but also make the coding process more efficient. To make a simple comparison, when you code using JDK rather than your IDE of choice, it is like using Notepad to write a book instead of Word. While they are both perfectly acceptable, you will likely agree that doing it in Word makes the process easier because of all the tools it provides.

Therefore, in this book, you will be given the option of using an IDE, which is highly recommended. In this case, the top three preferred IDEs for Java are IntelliJ, Eclipse, and VSCode. You can choose either of them (along with many others) for your coding process.

Installing the IDE

While each IDE will have its setup process, in this book, you will be guided through the step-by-step process of downloading Eclipse. Here are the steps that should be taken to carry out this process:

1.  Go to [eclipse.org](http://eclipse.org).

2.  On the top of the page, click the "Download" button.

3.  Click "Download x86_64."

4.  Click "Download."

5.  The Eclipse Installer program with a .exe extension should be downloaded to your machine's "Downloads" folder.

6.  Double-click on the icon to start installing the IDE.

7.  Select "Eclipse IDE for Java Developers."

8.  The folder to install the IDE will be preselected. Click "INSTALL."

9.  Launch the IDE once the download is complete, if the installer has not done it for you, and you have followed the step-by-step process.

10.  Create a workspace for your project (prompted by the program) by giving it a name. When you start a new project, you can create a new workspace.

You are now all set to start writing your first Java program! Shall we begin?

## WRITING YOUR FIRST JAVA PROGRAM

When someone is learning how to code, it is not unusual that their first program is "Hello World." This will not be different in your case. The first thing you need to do is start a project in the IDE. To do this, you must go to File > New > Java Project. A window will open to help you establish the details of the program you will create. Give it the name of your preference, and (this is very important) do not change any of the other configurations that appear on the screen. After this is done, you will click on "Finish."

Once this is done, you will be taken to the IDE's main screen, where you can see your program, with the name you have assigned to it, under a tab named "Package Explorer." Next, you should create a package for this program by right-clicking on the project name, selecting New, and then Package. Here, you will not change the source folder, and you can use the name of your preference once again and click on "Finish."

Note: According to the Java convention, which we will talk about in a little bit, the package's name should be similar to the purpose for which you will use the code.

Now, you will need to create a class, which can be done by right-clicking on top of the package you have created, which should appear below the project name; then, on New and Class, we could name it, for example, FirstProgram. Another dialogue box will appear, and you will fill in the package's name and ensure the box with the public static void main (String[]args) is selected and the one for Inherited abstract methods. Click on "Finish."

In the workspace, you will see there is new information, more specifically, the following (in Eclipse, you will need to type the code under the package name):

package <selected.name> //necessary for Eclipse and downloaded IDEs

public class <class.name> {

public static void main (String[] args) {

}

}

You will then type in your "Hello World" code as follows:

class FirstProgram {

public static void main(String[] args) {

System.out.println("Hello, World!");

}

}

That's it! All you need to do now is click on the green button on the top that says "Play," and the IDE will run your code. If there are no errors, you will see that at the bottom of the screen, the words Hello World will appear as your output.

Now, it's understandable that while you were able to do this successfully, you can't quite explain what happened. To do this, it's important to stop for a minute and look into the language's basic syntax. This will enable you to create more programs and code without issues. To do this, read on to the next section, and let's explore the main points of the Java syntax.

## BASIC SYNTAX

You already know that Java is an object-oriented language, but now, you are about to see the elements that compose the code to make it work, in other words, the syntax. Three essential elements make up the code in Java to create the object. They are, in order of amplitude:

1.  Class: the blueprint of a particular object. For example, we have the class "bird." It is safe to assume that all birds are birds, despite all of them having specific characteristics. For example, all birds have feathers and wings. The word's first letter should always be capitalized when declaring a class name. If you use more than one word, they should be written without spaces between them and the first letter of each word capitalized, such as BirdsProject. Once this is done, we will need to describe the action or behavior that these birds are carrying out, which will be done by invoking what is known as a method.

2.  Method: used to explain or describe the behavior that a particular object will have. This method must be described within the class. One important characteristic is that it is possible for there to be different methods inside the same class. For example, the bird can eat, bathe, hatch, fly, or whatever is permitted that was established by the specific class or "blueprint" to which birds belong. The first word should always start with a lowercase when writing a method's name. If you use more than one word to name the method, they will again need to be used without a space, and you will need to capitalize the first letter of the second word, such as blueBirdFlying.

3.  Instance variables: gives the specific object its unique characteristics. As of now, we have talked about birds. But, in this case, we will assign the attributes that make this bird (object) unique. It is blue, has a black beak, and can sing. These, together with all of its other specific characteristics, are this specific bird's unique traits that make it what it is and lead to the creation of the object.

Now, all these classes, methods, and instance variables have "rules" that must be followed when they are being written. As you have seen in the explanation above, there is a difference in how you should write the class names and methods. Each of these items of the Java code needs to be written within these specifications, primarily because Java is a case-sensitive language, which means something written in uppercase will not mean the same thing written in lowercase.

When programming in Java, you must name everything you code (classes, methods, and variables), meaning they will have identifiers. According to the Java code structure, these must always begin with an uppercase or lowercase letter from A to Z and an underscore (_) or the dollar sign ($). Identifiers cannot start with anything else, including numbers or other special characters. Here, it is always crucial to remember these will have different meanings if you use the uppercase or the lowercase.

Finally, you have the code line public static void main (String[] args), which is what will enable Java to process what you have asked it to do. This line of code will be implemented in all the code you will write in Java. This is because it will give the command, as in your case, the one to "print" the Hello World code.

Although this was not seen in the code, you might run into the case where it is written like this:

/*this is the code you are going

*to use if you want to print

*in your program Hello World

*/

//here is the package

package <selected.name>

//this is the class

public class <ClassName> {

//this is the main method, named as "main"

public static void main (String[] args) {

//this is print statement

System.out.println("Hello World");

}

}

You will see that the code instructions were used by adding the // symbols or the /* symbols. These standards should be used when you want to comment on the code that you are creating. In this case, you are going to use // for comment codes that have one line and /* to start comments that have more than one line; the next line should always start with *, and after you are done writing, you should finish with */ to indicate that the comment has ended.

Another thing that you might have noticed is that the above code has indentations, which means they are not aligned left. While some programming languages, such as Python, have indentations as a mandatory requisite for the code to function, this is not the case in Java. This means you can write your code without indenting if you are not using an IDE. Nevertheless, you should note that using IDEs such as Eclipse will automatically indent the code.

Finally, it is important to note two things about codes in Java: The first is that most experienced developers use the names for classes, methods, and instances that refer to what they will do. This leads to a more understandable and cleaner code, enabling other developers to understand what the intention behind the syntax was. The second is that many developers do not like comments to be used in the code. They claim this makes the code "dirty" and makes understanding it more difficult.

Most of this information is available in documents known as Java conventions. While these are not "rules" that will determine if your code will work, they are standard Java coding applications that most developers use to ensure their code can be read by anyone who needs to. Explaining all the Java conventions in this section would not make sense because there would be some elements you would not understand. However, to ensure you are acquainted with the best practices in the market, convention applications will be explained throughout the book's content as necessary.

Reserved Words

One last thing you should know, which is crucial for coding in Java, is that the language has what are known as reserved words. These words have a particular application when used with the code; therefore, they cannot be used to name variables, classes, or methods, for example. You will likely memorize the terms in this table as time passes and you obtain more experience with Java, so there is no need to worry! In addition, you will see that as you read, many of them will be explained; therefore, you will immediately understand they should not be used. If you need extra help remembering them, try printing or writing them out so you can easily refer to them when needed.

Here is the list of Java's 53 reserved words:

![](image_rsrc4ZR.jpg)

As we move to the last part of the chapter, you are going to learn how to compile and run the Java programs you create. While this process is automatic when using the IDE, it is important you know that carrying out these actions and commands can be done without using one. In addition to this, you will learn about the difference between the Java interpreter and the compiler, essential parts of the Java package.

## COMPILING AND RUNNING JAVA PROGRAMS

Just as the computer does not understand "human" language when you write the code in Java, it is not yet ready to be understood by the machine. This is because computers only understand the binary language, the allocations of "0"s and "1"s that it comprehends. When you have the Java compiler, or the javac, it will act as a "translator" that transforms what you have written in code format into computer language. As the name suggests, the interpreter has the same function: to convert the code into computer code so the machine knows what it must do.

But you might be asking, Does this mean the compiler and the interpreter are the same thing? This is an excellent question. While they act similarly, they have one fundamental difference: While the compiler scans the whole code and only then translates it, the interpreter will do this line by line and translate it simultaneously. If there are any mistakes in your code, the interpreter will catch them as it reads each code line, while the compiler will do this once it is finished scanning.

As you might imagine, this difference significantly impacts a program's performance and debugging. If you are running your code through the compiler, you will see all the errors that need to be fixed at once, which might take a long time since once you want to test it, it will need to run all the code again. This can lead to a tedious process, especially if the code is extensive. However, if correct, it enables the software to run faster since it will read and interpret the complete commands before taking action.

The interpreter will act with the exact opposite characteristics. If you imagine running a code line by line, you will see it enables faster debugging since you will "attack" each problem as you go, and it will only move on to the following line if it works. This means that the code will only stop if there is a mistake. On the other hand, executing this program can take longer since it will read each unique line of code to carry out the needed action.

When you use an IDE, this process is embedded in the software, showing you exactly where the problem is and doing it fast. Additionally, it might help you correct any problems that can be solved without the interference of the developer or tell you where you need to add more code. As mentioned earlier, you should learn how to compile code on your computer without using the IDE.

To do this, you must ensure the JDK is installed. However, instead of using the workspace in the IDE to type in what you need, you will open Notepad (or a similar application) on your computer. Now, remember that the steps you are going to read refer to Windows OS, but a similar approach can be used for whichever other OS you might have.

You will type in the code we have seen in the previous section:

public class JavaProgram {

public static void main (String[] args) {

System.out.println("Hello World");

}

}

Do not type in anything else. Then, save the file with the same name as the class, which is a good practice as per Java convention. In this case, the file would be saved as JavaProgram.java (with the .java as an extension) in your computer, but when you establish the path, you will need to tell the CMD where this file was located, such as the desktop or a specific folder. Open the Command Prompt (cmd) screen and type in javac JavaProgram.java to compile the code. Remember that you should use "javac" since it is the standard compiler for this language. If there are no errors, you can run the program immediately by typing in java JavaProgram and pressing enter. The output the cmd should bring you is none other than Hello World.

If there is an error in the code, this will be identified, and you will need to check and see the possible mistakes made. On the other hand, it is also possible you will receive a system message that reads javac', which is not recognized as an internal or external command, operable program, or batch file. This means that the computer is not finding the path for Java (the full package) on the device, and you will need to show it the path it needs.

This process is called "setting paths" and is relatively simple to carry out. The first thing you will do is locate where the JDK was installed on your computer and get the directory's address. You must copy the full address and then paste it into the command screen by writing before it (on the same line): set path= (paste the address here). Once this is done, you can compile and run your code to see what it looks like. As you can see, this is a rather laborious process, easily fixed by the use of an IDE, which is why, once again, the recommendation is that you use one during the learning process.

## YOUR TURN TO TRY!

Now that you have a general idea of how coding in Java works, it is your turn to try! Practice printing statements in the code provided by substituting "Hello World" with other phrases in Eclipse or any online IDE. These are the programs you should be using to develop all the code you are writing for this exercise and the remainder of the book.

Try and practice as much as you like until you feel comfortable. You can also try to add "incorrect" elements, such as taking out the curly brackets from the code to see what will happen. It is all about trying and experimenting!

You have now taken the first step into the exciting world of programming and crafted your first Java program. As we proceed to the next chapter, you will delve deeper into the language's building blocks and fundamental stones: variables and data types. So, stay curious and keep exploring!

CHAPTER 2

VARIABLES AND DATA TYPES

Now you know the Java syntax and the application of classes, methods, and objects, it is time to take a closer look at other Java components. These will help you write your code and determine what needs to be done and the format that needs to be considered. For this reason, in this chapter, you will learn about variables, constants, primitive data types, and operations in Java.

But you did not think you would only see and not do, did you? Well, of course not. As you learn each of these, you will also see how they work and how to, for example, convert between data types. At the end of the chapter, you will learn how to manipulate strings, perform casting, and initialize variables. To ensure you have understood the content, you will have some exercises at the end to practice your new skills and explore the different coding possibilities.

## VARIABLES AND CONSTANTS

The first thing you will need to understand is that, much like other languages, Java has items that can be classified as a variable or a constant. In this case, when you have a variable, the information can change according to its use in the program. However, for this to be the case, you must declare it, for example:

data_type variable_name;

int x;

On the other hand, when you have a constant, as the name suggests, the value will be the same throughout the program's execution. Just as with the variables, you will need to "tell" the program that the value you are adopting is a constant so it identifies that there will be no change throughout the code by using the word "final." This is the syntax of how a constant should be declared:

final int X = z;

As you might have noticed from the above code, the "x" declared in the variable is lowercase, while the one in the constant is uppercase. This is very important since, as you remember from the previous chapter, Java considers differences between the letter cases used in the code. In this situation, when declaring a constant, the Java convention states that when a constant is being declared, it needs to be used in all caps, and if it is composed of more than one word, you need to use the underscore between them.

While Java has only one way of declaring constants, this is not the case for variables, since the language has three different variable types. They are:

*   Class variables, which relate to the class are usually declared with the keyword static for the class being used. In other words, this variable will define the full block of code for which the specific class is written. When the word static is used, it means that there is, within the entire program, only one copy of this specific variable, and it does not change. In this case, the variables don't necessarily need to be declared. They will automatically refer to the default value, which we will discuss in the next section.

*   Instance variables are nonstatic values that can change as you write your code. Since they are mutable, you should not add the static term before it. In this case, to easily remember what instance variables are, you can refer to the name and remember that its characteristic (or value) will depend on the situation in which it is used. These variables are declared within a class but outside the method. They are used for all the methods within that specific class and should always be declared despite having default values. You can use the keywords "public" or "private" before declaring the instance variable to define its visibility.

*   Local variables are, as the name suggests, the state given to a certain object depending on its location within the program. In this case, it will be used in a simple syntax where the variable = the value, without needing to use any specific keywords and just by placing them between the curly brackets { } in the code. Since these are restricted to a certain location, they will only refer to that part of the code and will not be used in other places. They are usually declared within methods since they will be used as the blocks to build that code and, considered temporary—once used, are destroyed by the program.

These are the different ways that the developer can code and attribute states to the objects they are declaring. However, you must be wondering, is there a difference in how I am supposed to write a number or a word, or even a distinction between a full number and a decimal one? That, in fact, is a very good question because there certainly is.

When you write code in Java, different data types can be used, each of which will store information in a different format. In Java, we have both primitive and nonprimitive data types. If you are wondering what these are, read on to find out!

## PRIMITIVE DATA TYPES

Primitive data types, as the name suggests, are those that are native to the language and have predefined functions. In Java, there are eight primitive data types: those that accept boolean data and the ones that accept numerical values. While in boolean, there is no subcategory, when we talk about numeric types, these can be divided into char, byte, short, int, long, float, and double.

Below, you will find a chart that shows you each data type and its specific characteristics, obtained from Agrawal (2023):

![](image_rsrc4ZS.jpg)

Now, I imagine you must be thinking about where and how each of these can be used and what syntax should be adopted when declaring them. To simplify the identification process and facilitate comprehension of each data type, here is another table containing all the information you need to know.

![](image_rsrc4ZT.jpg)

In this table, you will note a few unique characteristics in some of the demonstrated syntaxes:

*   After the data type has been defined, you must use the semicolon (;) so there is no error when running the code.

*   The underscore character represents the commas in the numbers, while the decimal point remains the same.

*   All the data types that store numbers can be used for mathematical calculations in Java, although there is a difference between doing so with short, int, and long when compared to float and double.

*   The quotation marks you need to use are the straight ones (' or ") rather than the curly ones (‘’ or “”) that might not be recognized by the compiler.

However, after you have read this table, you might think, What if I want to store a sentence, such as Hello World, like we did in the first example? How would this be done? These are outstanding questions and show that you have been paying close attention. Good for you! In this case, we would use what is known as a "string" in Java.

In a string, you can declare text, such as "Hello World," which must be placed between double quotes so they are understood. Here, the function "string" should have the first letter capitalized. In this case, the syntax would be as follows:

String greeting = "Hello World";

However, we will not get into the specifics about strings right now since this will be discussed in the last section of this chapter. In the meantime, I want to take a moment and refresh your memory that when declaring the data types for the variables, according to the Java convention, they should be as close as possible to what they mean, such as:

String name = "Sarah";

int age = 15;

float temperature = 45.9f;

Finally, before we move on to the next section, you should also know the final two details about variables and data types:

1\. It is possible to declare a variable and only define its value later, such as:

int year;

year = 2006;

2\. It is possible to change the variable by assigning it a new value, such as

int year = 2006;

year = 2013;

In this case, the value was changed, and if you ask the program to print the "year" variable, the output you will see is 2013\. Remember that if you want this value fixed, you should add the word "final" to the beginning of the statement so that it cannot be changed or overwritten, transforming it into a constant. In this case, you will only change the variable's value, not its type. When you want to change the data type it refers to, you must resort to what is known as casting, which we will talk about now.

## TYPE CONVERSION AND CASTING

If you are developing your program in Java, you might want to change the data types, for example, from a float to a double, for a calculation to be more precise or consider the larger number. In this case, you will need to use what is known as type conversion or typecasting, which is switching from one data type to the other. According to Badkar (2023), this can also be the case if you want to:

*   have more control of the code

*   optimize program memory use

*   prevent data loss

*   transform user input made in text into numbers

*   make data types compatible for performing calculations and operations.

In this case, this data type change can be carried out in two ways: manually or automatically, also known as explicit and implicit. Java currently supports 13 types of data conversion within its rules, which can range from widening and shortening a number to converting a char into an int. The only data type that does not accept any conversion is the boolean.

Explicit Typecasting

In this manual conversion of data types, the developer will write the code to ensure the conversion is made. The main characteristic of this type of conversion is that it will be used to shorten the values assigned to a variable. In this case, the conversions allowed are as follows:

double → float → long → int → short → byte

This means that you can, for example, reduce a long decimal number into a shorter decimal number and this smaller decimal number into an int whole number. When this last conversion occurs, the decimal points will be discarded, and only the full number will be recognized by the program. Here is an example you can consider for these conversions:

In this first example, we are going to transform a float with a value of 2.2 into an int using the full code block.

class Main {

public static void main(String[] args) {

// create a variable with the float type

float data = 2.2f;

System.out.println("The float value is " + data);

// convert the previously created float into an int

int num = (int)data;

System.out.println("The int value is " + num);

}

}

In this case, the output the program would bring you is the following:

The float value is 2.2

The int value is 2

Since the decimal points will be discarded, the int value is going to be 2\. However, depending on the use of the software you are developing, losing this specific precision where the decimal points in the double or the float are lost may directly impact the calculation results you obtain. For this specific reason, because this type of conversion can be considered "dangerous," the developer must manually carry out the change and not automatically (Gupta, 2020).

Now, if you notice what was mentioned, you might wonder if this same procedure needs to be carried out when you want to widen or increase a number. The short answer is "no." For the cases in which you will move from a "smaller" to a "longer" number, the compiler does the process automatically, in what is also known as implicit typecasting.

Implicit Typecasting

What is known as the "widening" of the number in implicit typecasting will usually happen when the type of the destination is bigger than the one used in the source or if the data types are compatible. This means that even if you try to convert a larger number into a smaller one automatically, the compiler will make an error, and you will need to fix the code line. It is important to understand these acceptable conversions so your program does not produce any errors while compiling. Let's take a look at the available conversions:

byte → short → int → long

char → int → float → double

int → double

long → float

Let's take a look into these conversions with an example using the full code block:

class Main {

public static void main(String[] args) {

// create a variable with the int type

int num = 15;

System.out.println("The number is " + num);

// convert the previously created int into a double

double decimal = num;

System.out.println("The decimal value is " + decimal);

}

}

The output, in this case, is going to be

The number is 15

The decimal value is 15.0

Because we have converted a shorter number into a longer number, this was automatically done without needing to specify the conversion as it happened in the explicit syntax example.

## WORKING WITH STRINGS AND COMMON STRING OPERATIONS

As promised, we have arrived at the final section of this chapter, and we are going to talk about strings. As you saw at the beginning of the chapter when we were discussing data types, strings store a collection of characters, usually letters, that make up a text and are surrounded by double quotation marks. You saw this when we spoke about the "Hello World" example you saw in the first chapter.

The first and most essential characteristic you should know about a string is that it is immutable or, in other words, it cannot be changed after it has been created. However, this does not mean you cannot carry out any operations with it. In fact, there are several actions you can carry out with a string, which we are about to see now. Here is a list compiled by Challa (n.d.) based on the official documentation that specifies all the built-in methods for strings in Java:

*   charAt(): used to return a character at a specified position.

*   concat(): used to append one string to the end of another.

*   equals(): used to compare two strings and return a boolean value (true or false).

*   indexOf(): used to return the first identified position of a character.

*   length(): used to identify the length of a string.

*   substring(): used to extract the substring based on index values, passed as an argument.

*   toLowerCase(): used to convert all the letters in the string to lowercase.

*   toUpperCase(): used to convert all the letters in the string to uppercase.

To exemplify how these functions can be used with a string, I will use one block of code for the strings and ask the compiler to print out the different outputs according to the command requested in a similar model to the one applied by Challa. Are you ready?

class Main{

public static void main(String []args)

{

String name ="Sarah";

String surname="Connor";

String profession="Hunter";

boolean id=name.equals(profession);

System.out.println("The letter in position 3 is: "+name.charAt(3));

// the output in this case will be The letter in position 3 is: a

System.out.println(name.concat(surname));

// the output in this case will be SarahConnor

System.out.println("Compare name and surname: "+id);

// the output in this case will be Compare name and surname: false

System.out.println(name.indexOf('r'));

// the output in this case will be 2

System.out.println(profession.length());

// the output in this case will be 6

System.out.println(profession.toLowerCase());

// the output in this case will be hunter

System.out.println(surname.toUpperCase());

// the output in this case will be CONNOR

System.out.println(surname.substring(1,3));

// the output in this case will be on

System.out.println(name.substring(3));

// the output in this case will be ah

}

}

Now that you have seen the result of the code, here are some comments you must take into consideration regarding the output:

*   When you request to print the index position of "r," the program's output is "2." This is because you start counting with 0 instead of 1 in Java. Therefore, in this case, "s" would be index 0, "a" would be index 1, and "r" index 2.

*   While the concatenation did not add any spaces between the words, in the output Compare name and surname: false, you will notice that there is a space between the colon and the word "false." This is not automatic in Java, and you need to indicate the need for this space when writing what you want the output to be.

*   The concatenation function can also be replaced by the "+" operator. In this case, if you wanted to use it, the syntax would be:

System.out.println(name + " " + surname );

// and the output would be Sarah Connor because you have added the space

Well, that is about all the essential information on data types and variables in Java. You have been given a comprehensive explanation of their main characteristics and how to use them. This information is essential since you will use it when writing your code in the following chapters. However, now it's your turn! Are you ready to try some examples on your own?

## YOUR TURN TO TRY!

Below are five practice examples you can use to test whether you have assimilated the content. Regardless of these examples, I again encourage you to take a moment to explore the different code possibilities using the information you have learned in this chapter, including writing it incorrectly so you know what an error will look like if a mistake is made.

1.  Create a new variable with a string format.

2.  Transform all the letters into uppercase for the previously created string.

3.  Convert the double data type with a value of 458.96 to an int data type.

4.  Convert an int data type with a value of 6 into a float data type.

5.  Super challenge: Add a variable with an int data type with a value of 56 with a variable with a double data type with a value of 897.69.

You've successfully dived deeper into the ocean of Java! From understanding the basic building blocks of Java to juggling with strings, you've broadened your programming knowledge. But there's more to discover. In the next chapter, we'll explore Java operators and control statements. Are you ready to continue the adventure?

CHAPTER 3

CONTROL FLOW

When you are writing code, regardless of what type of language you are using, it is likely you will need to program in some commands. A straightforward example we are used to seeing is when we need to log in to a site or app that requests our password. In this case, if we type in the correct alternative, we can log in. If we don't, we will need to try again. This is an example of an "if-clause," which is one of the things you will learn in this chapter.

To help you become familiar with the control flow in Java and learn how to develop an intelligent decision-making system, you will now learn all about conditional statements. In addition to this, we will also talk about looping structures, break and continue statements, nested loops, and logical operators. At the end of the chapter, as usual, you will work on exercises and develop your young code lines. Let's take a look.

## CONDITIONAL STATEMENTS

Conditional statements are, as you might imagine, a condition. For example, if it is raining, I will take an umbrella; if it is not, I will not. These two keywords, if-then, are the two reserved keywords for these conditional statements. These are useful to create a sequence of the actions the program will need to carry out and the different decisions it will need to make.

In this case, if the condition in the output is true, then this will be the output. If it is not (else), then this other information will come as an output. It is crucial, however, to remember that the computer will follow the order in which your code was written. The if-else condition can be used for floats, char, int, and boolean, and the statement can be composed of more than one declaration. Let's look at an example.

Suppose you create an agenda and want each day to represent a specific number. In this case, you could tell the program that day 1 is equivalent (==) to Monday, day 2 is equivalent to Tuesday, and that day 3 is equivalent to Wednesday. If any other number is placed in the field, the output should be "Other day." This is what the code would look like:

Public class Main{

public static void main(String []args)

{

int day = 3;

String dayName;

if (day == 1) {

dayName = "Monday";

} else if (day == 2) {

dayName = "Tuesday";

} else if (day == 3) {

dayName = "Wednesday";

} else {

dayName = "Other day";

}

System.out.println("Using if-else: " + dayName);

}

}

In this case, we have established that the int number we are using is 3; therefore, the output of the program will be Using if-else: Wednesday. If you were to replace the statement int day = 3; for 2, for example, the output would be Tuesday. Try it! Copy and paste this code into your IDE and test adding different numbers to see the outcome you will have. You can also enhance the code and add other numbers equivalent to other days to make the program more dynamic. Don't forget the curly brackets {} for the code to work!

Although this is an easy and efficient way to make your code work, you must remember that if you use it too much or apply too many statements, your program might be slower. It will also make the process harder to edit if necessary since each change will deal with several variables. For this reason, another conditional keyword can be used in Java that will allow you to optimize the coding and make it faster, replacing the different if-else statements. This conditional is known as the switch statement.

Let's see how the switch statement would be applied in the previous example:

public class Main{

public static void main(String []args)

{

int day = 3;

switch (day){

case 1:

System.out.println("Monday");

break;

case 2:

System.out.println("Tuesday");

break;

case 3:

System.out.println("Wednesday");

break;

default:

System.out.println("Other days of the week");

}

}

}

In this case, as you can see, we have replaced the if-else statements with "cases" and "breaks," which enables the program to make the decision likewise. The program will run all the decisions until the end is reached or the break statement is identified. In this case, you will use one statement for different decisions (look at where the {} open and close), making writing, editing, and testing the code easier. On the other hand, the logic of the code will not be tested, as would happen with if-else.

The other difference you will see is that there is a "default" keyword at the end. This value should be applied if any conditions do not meet the criteria. This means that if you were to input numbers 1–3, you would have the same input as you have seen in the previous section. However, if the number differed from these, the output would be Other days of the week.

While these statements will help you control the program's logic, can you imagine what would happen if you needed to create a countdown program? How many lines of code would you need to write for every output number that should be shown on the screen? If we were talking about 10, that might not be so hard, but what if we were using a timer to count down how much time a person has left to perform a certain task? That would certainly take many code lines and time.

Nonetheless, you should not worry since Java has a solution for avoiding this. We will see these in the next section, and they are called looping structures. When you write these statements, they will enable the program to carry out the same task for a certain number of iterations or until the condition is false. Interested? I can bet you are! Let's take a look!

## LOOPING STRUCTURES

When coding in Java, you have three loops that can be applied to your program: for, while, and do-while statements. These enable the developer to command the program to perform several repetitions (iterations) until it finds a condition that makes the statement false or according to the determined number requested and identified in the code. This section will explore each type of loop, the best time to apply them, and the syntax that should be used according to each situation.

For Loop

The first loop we will look at is the for loop. In this loop, you will tell the program exactly the parameters you want it to run. Due to this characteristic, most programmers use the for loop when they have a certain number of iterations they want the program to carry out. In this case, you will declare the variable and the condition that you will make it follow.

Suppose you are creating a timer that needs to count to five for a test to start. For this, you will need to create a program using a for loop to show the numbers on the screen. In this case, you would use the following code:

public class Main{

public static void main(String []args)

{

for (int i = 1; i <= 5; i++) {

System.out.println(i);

}

}

}

If you wrote this code and executed it, you would see that the output would be

1

2

3

4

5

since you have requested that the program count from one to five, incrementing one (++) every time. If you were to replace these numbers with 0 and 10, your answer would be a list of numbers from 0 to 10\. If, on the other hand, you wanted the list to count every two numbers, then the information would be changed from i++ to i+=2, or i+=3 for three, and so on.

You should know that the for loop can also decrease the numbers as if you were performing a countdown. In this case, the syntax, instead of being int i = 1; i <= 5; i++, it would be int i = 10; i >= 0; i--, for which the output would be a list of numbers decreasing from 10 to 0, one by one. If you were to decrease them two by two, you would also change from i-- to i-=2, or i-=3 for three, and so on. An important thing to note, in this case, is that you will only be able to use this loop when using the data type "int."

But what if the number of iterations I want to add is not defined? That is a very good question! In this case, we would use the while loop, which is the next loop we will look at. However, before we do this, I want you to test the for loop code in your IDE and see if you understand it. Try to paste it with a few different values, use some variations, and print the results to ensure you know what you have. Once you are done, move on to the next section.

While Loop

The while loop, unlike the for loop, should be used when you don't have a preestablished number of iterations you need to carry out. This is because it will analyze the code as a boolean function and process it until it identifies a false example. While in the example, we will see we are talking about small numbers, you should consider that this statement will be used when you must carry out hundreds or even thousands of iterations.

Suppose you have to ask the program to print a statement, such as While loop until it meets a certain condition. In this case, we could say that it should print this statement until it identifies that the number of prints is less than or equal to 5\. Once again, we are using small numbers, but the application for this loop usually considers more significant numbers. In this case, the code would be the following:

public class Main{

public static void main(String []args)

{

int i = 1;

while (i <= 5) {

System.out.println("While loop");

i++;

}

}

}

If you wrote and executed this code, you would see that the output is:

While loop

While loop

While loop

While loop

While loop

The program, in this case, identified that it should print the statement "While loop" until the time was less than or equal to 5, and therefore, we have the words printed five times. Since it had reached five, the program identified that it was now "false," and the iterations stopped. Can you see how easy this would make it to perform several iterations without writing so many code links?

As we saw in the for loop example, you will see that it is also possible to change the different iterations from i++ to i+=2, or i+=3 for three, and so on. The same applies to decreasing the number of iterations. If we had placed i+=2, for example, in the code, we would have While loop printed three times. Once again, this while loop can only be used with the int data type for both increasing and decreasing quantities.

But what if I want to perform an iteration on a list or a group of statements simultaneously? Is this possible? I am glad you asked because it certainly is! When you want to carry out a loop that will execute different statements, then you will use the do-while loop. Let's take a look at its characteristics and applications.

Do-While Loop

Suppose you are working with a code and, despite what the code block says, you want it to run at least once. In this case, you would apply the do-while loop since it will allow you to run a written block of statements at least once. If the conditions are true, it will continue until the boolean statement's "false" affirmation is found.

For our next example, we are going to put an extreme condition. We will say that the number of the integers we are looking for is supposed to be less than or equal to zero, with the first number being one. As you might imagine, this should bring an error, but it won't. Do you know why? Because the program will run the code at least once! Therefore, as an output, you will have… Can you guess? Here is the code for you to examine.

public class Main{

public static void main(String []args)

{

int i = 1;

do {

System.out.println(i);

i++;

} while (i <= 0);

}

}

If you guessed that, in this case, the output would be 1, you are correct! This is because you have asked the program to do a do-while, and for this reason, it will return 1. While this might not make sense in the "real world," it is a good way to see how the do-while loop works. Can you imagine what would happen if the iterations were asked to be i+=2? No, not 2. The answer would still be 1 for all the other changes you applied. The same rationale would be applied to the decrease function.

If we changed the code to

public class Main{

public static void main(String []args)

{

int i = 5;

do {

System.out.println(i);

i+=2;

} while (i <= 10);

}

}

This would now mean that your first number would be 5, and the output would be:

5

7

9

Nice, right? As we move on to the next section, I want to return a little to the switch statement we saw some time ago. If you remember, we used this keyword to leave the switch condition and make it "jump" to the next. However, did you know that this statement can also be used to help you stop loops? They can be used with the conditional "if" to stop loop statements if they reach a certain condition. But let's not get ahead of ourselves.

Before moving on, I would like you to try out the code you have seen so far in this section if you haven't yet. It will be important to understand them since the further along we move in the book, the more complex the code will get, and you will need to understand the basics to comprehend what is to come. If you have done so, let's continue! There is still a lot to be seen.

## BREAK AND CONTINUE STATEMENTS

When you use the break and continue statements, you tell the program to stop (break) or pick up (continue) at a certain part of the code. This means that if you ask for the code to carry out an iteration, if you add the break statement after this is done a certain number of times, the program will automatically stop. If you want the program to skip one of the iterations you have requested to carry out, then you will use the continue statement, such as counting from 0 to 5 and skipping the number 3.

Although we have seen an example of the break statement previously, we will look into an example of how it can be used separately from the switch statement. After this, we will look closer at the continue statement and the different ways it can be used.

Example 1: Print the numbers 0 to 100 and break the loop when the count reaches 3.

public class Main{

public static void main(String []args)

{

for (int i = 0; i < 100; i++) {

if (i == 3)

break;

System.out.println(i);

}

System.out.println("Loop Finalized");

}

}

The output for this first example would be

0

1

2

3

Despite having programmed the code to print numbers 0–100 initially, you have asked that when i=3, the loop be broken, and for this reason, there are only the numbers 0–3 printed in the output. In this case, the break statement was used with the conditional if statement that establishes what should happen for the loop to be broken.

Example 2: Print odd numbers between 1 and 10 using the continue statement. Use the continue statement to skip the even numbers.

public class Main{

public static void main(String []args)

{

for (int i = 1; i <= 10; i++) {

if (i % 2 == 0) {

continue;

}

System.out.println(i);

}

}

}

The output for this first example would be

1

3

5

7

9

Which is correct given what you have asked the program to do. At the same time, you could replace the statement for other conditions that use integers to carry out the process.

Example 3: Compute the sum of five positive numbers. In this example, the negative or the 0 values should not be considered and should be skipped. (For this example, we will use an array to illustrate the exercise, despite talking more about them in the following chapter.)

public class Main {

public static void main(String[] args) {

int[] numbers = {5, 8, -2, 12, 4};

int sum = 0;

for (int i = 0; i < numbers.length; i++) {

int num = numbers[i];

if (num <= 0) {

System.out.println("Skipping negative or zero value: " + num);

continue;

}

sum += num;

}

System.out.println("Sum of positive numbers: " + sum);

}

}

In this case, the output would be the following:

Skipping negative or 0 value: -2 (because you have asked it to skip the negative numbers)

Sum of positive numbers: 29 (because this is the sum of the positive integers that were given: 5, 8, -2, 12, 4.)

Java Continue With Nested Loop

Although we will learn about nested loops in the following section, to understand the example that will be shown, you must know that these are when we have one loop inside another. In this case, it is also possible to use the continue statement to establish the condition you want the program to follow.

In the following example, you will create an outer loop that asks the program to count from 1 to 5 ("i" values). However, you also want this program to skip numbers 3 and 4 ("j" values) if they appear in the count. In this case, you will establish a condition that if i==j, then the number should be skipped. If not, it should be repeated. By using the if statement, this is what the code would look like:

public class Main {

public static void main(String[] args) {

for (int i = 1; i <= 5; i++) {

for (int j = 3; j <= 4; j++) {

if (i == j) {

continue; // Skip the numbers 3 and 4

}

System.out.println(i);

}

}

}

}

The output, in this case, would be:

1

1

2

2

3

4

5

5

This answer is written this way because the numbers 3 and 4 are considered in the outer loop (i values), and they are disregarded and skipped in the inner loop (j values). Since you might be confused about how the nested loop was applied in this situation (and even what the inner and outer loops are), let's closely examine what these are and start understanding how control flow works in Java statements.

## NESTED LOOPS AND CONTROL FLOW

You already know that nested loops are characterized by having one loop inside another, which are named the inner and the outer loops. However, one of their characteristics is that you can use the different control statements with them, not only the continue or those belonging to the loop. This means that you can use for, do, and do-while but also the if-else and if operators  and the associated statements. You can even use the break statement inside or after a nested loop to help you with the program's control flow.

Using nested loops is very practical if you want to analyze a matrix, for example, since you can iterate on a number through the whole matrix to see if there is a coincidence, then the next number, and so on.

In the example you are about to see, we will create a matrix with 3 rows and 4 columns (3x4 matrix). We will then create a for loop that will iterate over the different elements of the matrix. In this case, the "i" elements will be the outer loop, and the "j" items will be the inner loop. We will ask the program to calculate and assign values to each of the elements that will "build" the matrix by indicating the row and columns that say that 1 should be added to the previous number.

public class NestedLoopsExample {

public static void main(String[] args) {

int rows = 3;

int columns = 4;

int[][] matrix = new int[rows][columns];

// Initialize the matrix with values

for (int i = 0; i < rows; i++) {

for (int j = 0; j < columns; j++) {

matrix[i][j] = i * columns + j + 1;

}

}

for (int i = 0; i < rows; i++) {

for (int j = 0; j < columns; j++) {

System.out.print(matrix[i][j] + "\t");

}

System.out.println();

}

}

}

The output for the previous code would be

1     2     3     4

5     6     7     8

9     10   11   12

As you can see, in the previous example, we used the for control flow to determine what the program was supposed to print. In similar situations, you would use all the other control flow statements we have already seen and some that we have yet to study, such as the return statements.

For a quick overview, here are the control flow statements you have learned about so far:

*   if

*   if-else

*   switch

*   for loop

*   while loop

*   do-while loop

*   continue

*   break

Next, in the last section of this chapter, you are going to learn about logical operators. As you will see, they combine different statements and can be used to determine if a condition is true or false. Using these will help you determine the different conditions given to the program and enable better decision-making for the code. Let's jump into the next section and see how to use them!

## INTRODUCTION TO LOGICAL OPERATORS

Logical operators can appear in different ways. Still, they usually combine one or more conditional statements to determine if they are false, true, or if one of them is true or false. As you are reading this section, it is important to keep in mind that "while using the AND operator, the second condition is not evaluated if the first one is false. Whereas, while using the OR operator, the second condition is not evaluated if the first one is true" (Lenka, 2023).

Since we determine logic and conditions, these will usually be applied with the if or if-else statements. In addition to this, many times, we can add boolean expressions, which you will remember are a "yes" or "no" input, to determine the statement's condition. Let's look at each of these operators and how they work.

AND Operator

The AND (all in uppercase) operator is represented by the two ampersand (&&) symbols. When you use this, you are saying that if both conditions are true, then the program should execute the code. In case one or both of them are false, then you will apply the else, which could be to not execute. In the example below, we will see a situation in which both being sunny and warm are true. If this is confirmed, the system should print, "Let's go to the beach!"

Here is how the code should be written:

public class Main {

public static void main(String[] args) {

boolean isSunny = true;

boolean isWarm = true;

if (isSunny && isWarm) {

System.out.println("Let's go to the beach!");

} else {

System.out.println("Stay home.");

}

}

}

In this case, since both conditions are true, you will see that the output  is Let's go to the beach!, which means that the input was confirmed. If you were to replace the statement boolean isSunny = true; for boolean isSunny = false;, can you imagine what would happen? Yes! You are correct! The program's output would be Stay home since the provided input has a false statement. This same logic can be applied to numbers and data types, such as structure.

OR Operator

When you use the OR (also all in uppercase) operator, represented by the two separator (||) symbols, this means that one of the two conditions must be true. Regardless of whether you have 2o or 100 different conditions, if one is true, then this result will be true. On the other hand, if all of them are false, then the result of this logical operator will be false.

Let's suppose, for example, that you are going to a coffee shop and want to drink something. In this case, they will have the product if you ask for coffee, but if you ask for tea, they won't. This is what the code would look like for this situation:

public class Main {

public static void main(String[] args) {

boolean hasCoffee = true;

boolean hasTea = false;

if (hasCoffee || hasTea) {

System.out.println("Enjoy your beverage!");

} else {

System.out.println("No drinks available.");

}

}

}

Can you guess what the output would be in this case? If you guessed, Enjoy your beverage! then you are correct! This is because, according to the established condition, you would like to have either tea or coffee; since one is available, you can enjoy your drink. The same output will be given if both statements are true since you could enjoy at least one drink.

However, what would happen if the boolean hasCoffee = true; was, instead, boolean hasCoffee = false;? Can you guess what the output would be? If you said No drinks available. then you are correct! This is because you only had the option of drinking tea or coffee; therefore, since there was neither option, you would not be able to enjoy any drinks.

NOT Operator

The last operator we will discuss is the NOT (all in uppercase), represented by the exclamation (!) symbol. Unlike the other two logical operators, this one will return the output if the condition is false. "Basically, if the condition is false, the operation returns true, and when the condition is true, the operation returns false" (Lenka, 2023).

In our example, we will use the condition to determine if you should take an umbrella with you or not if it is not raining. This is what the code would look like:

public class Main {

public static void main(String[] args) {

boolean isRaining = false;

if (!isRaining) {

System.out.println("No need for an umbrella.");

} else {

System.out.println("Take an umbrella with you.");

}

}

}

The output,  in this case would be No need for an umbrella. since it was identified that the condition you have given the system is false. Therefore, if the condition is false (or not raining), you do not need to take an umbrella. Now, to do the same exercise with the previous operators: What would happen if we changed boolean isRaining = false; to boolean isRaining = true;?

If you said that the output would be Take an umbrella with you. you are correct! This is exactly what the system would bring as the answer since the condition is true, which was given as the else in the condition. How about that?

You have learned all about Java control methods and can already code your program to make decisions. That is a great advance! To test what you have learned in this section, the final part of this chapter will be a small practice exercise with a super challenge to see how your coding skills are going. Are you ready?

## YOUR TURN TO TRY!

In this activity, you'll flex your creative muscles while reinforcing your understanding of control flow structures in Java. You'll be creating a comic strip that reflects a day in the life of a student, with each panel showcasing a different control flow structure.

Instructions

Think of a typical day in the life of a student. What decisions do they have to make? What routines do they go through daily? What different paths might their day take based on different decisions? For this activity, you will need paper, pencils, or markers for drawing. On a sheet of paper, divide the page into several sections—these will be the panels of your comic strip. For example:

*   Panel 1 (decision-making): A student deciding whether to snooze the alarm or wake up. Here, you can represent an if-else decision. If they wake up, they have breakfast; else, they miss breakfast and rush to school.

*   Panel 2 (looping): Show the student in class taking notes while the teacher is teaching. This can be a while loop. While the teacher is teaching, the student keeps taking notes.

*   Panel 3 (branching): Show the student in the cafeteria deciding what to have for lunch—pizza, burger, or salad. This can represent a switch-case scenario where each food option is a case.

Now, draw the comic strip, illustrating each panel according to the storyboard. Label each panel with the corresponding control flow structure (if-else, while loop, and switch-case). After completing the comic strip, reflect on the activity. Was it easy or hard to create scenarios for each control flow? How does this activity help you understand the control flow better?

Here's an example storyboard:

*   Panel 1: The alarm rings. Decision (If-Else): If the student hits the snooze button, they miss the bus to school. Else, they get ready and catch the bus.

*   Panel 2: The student is in a math class. Loop (While): The student keeps taking notes while the teacher explains a concept.

*   Panel 3: It's lunchtime. Branching (Switch-Case): The student chooses between food stations—pizza station, burger station, or salad station.

Superchallenge: Can you code this in a Java program so that it can make the decisions for you and give you the output? Try it out! The answers and the others from the previous and next chapters are at the end of this book.

Congratulations! You have made great strides in your journey to master Java! From steering the course of your program with control flow to manipulating loop iterations, you are getting the hang of crafting intricate code. Are you starting to feel more comfortable? I hope you are!

Next, we are going to delve into the world of Java arrays. I have mentioned them previously, and now is the time to really understand what they are and how they can be used. Knowing this will be another great upskill in your understanding of Java. Are you ready to uncover the power of collection data types? Let's get started!

CHAPTER 4

ARRAYS AND COLLECTIONS

When you want to organize clothes inside your wardrobe, how do you do it? Do you just place all the clothing in any manner, or does each item have a place? Is there any order for it? If you keep your wardrobe tidy, then you should know that the same logic happens when discussing data. With the increasing amounts of data we have every day, it is important to find optimized ways to store this and ensure it can be easily found.

To solve this data organization problem, Java has two solutions, known as arrays and collections. This chapter will teach you how to declare, initialize, and access arrays, including multidimensional arrays. Since you have already seen some information about arrays in the previous chapters, you might recognize some of the content. Nevertheless, practicing and writing the code in your IDE is important to ensure you understand the concept.

Additionally, we will also talk about collections, such as ArrayList and LinkedList, and how to use them effectively in your Java programs. You will see different ways to use and apply collections to your code and how they will make your coding process faster and more efficient. If you are ready for another lesson, read on! You are about to discover a whole new way to organize and store your information.

## INTRODUCTION TO ARRAYS

When we talk about arrays, we are referring to a group of values with the same data types that are held inside one Java object. These individual values are known as an element, and their quantity will be used to determine the length of the array. Arrays can store most data types, including strings, integers, bytes, and booleans.

To start off, one of the most important things you need to know about arrays is that they usually start in index 0\. This means that if you have an array with 10 elements, the last one will be under the index number 9 and not 10\. This might take some getting used to, but I am sure that with time and practice, you will become a professional at it!

Declaring and Initializing Arrays

Like most other Java structures, you will need to declare and initialize an array to recognize it as such by the IDE. To do this, you will provide a type and a name and place the elements of the array after square brackets ([ ]). The first thing you will do is declare the array according to the data type it will contain. In this case, they can be the following (Arrays, 2017):

*   boolean[] anArrayOfBooleans;

*   byte[] anArrayOfBytes;

*   char[] anArrayOfChars;

*   double[] anArrayOfDoubles;

*   float[] anArrayOfFloats;

*   int[] anArrayOfInts;

*   long[] anArrayOfLongs;

*   short[] anArrayOfShorts;

*   String[] anArrayOfStrings;

In this case, you are going to declare the type of array that you are going to have, add the brackets, and then the name of the array. In the case of the previous examples, you have the names starting with "an," which can be any word as long as they are lowercase, and the next words in camel case (no gaps between words, but each word is capitalized). Although it is also possible to place the brackets after the name, this is not recommended according to the Java convention. Once this is set, you can say that your array is declared.

The next step is to initialize it; this will be done by declaring how many elements your array will have so the memory can be allocated. You will then assign the values to the elements contained within the array. In code, this would look as follows:

public class Main {

public static void main(String[] args) {

//declaring the array

String[] myTestArray;

//allocating memory for the number of elements you will have

myTestArray = new String[5];

//initializing the array

myTestArray = new String []{"grapes", "apples", "bananas", "cherries", "oranges"};

}

}

You now have an array of string data types that contain five elements. Do you remember how many index positions this means? If you said four, you are correct! In this case, you would have:

0=grapes

1=apples

2=bananas

3=cherries

4=oranges

If you want to save space, you can also declare, allocate, and initialize the array within the same line of code. In this case, it would look like this:

public class Main {

public static void main(String[] args) {

String[] myTestArray = {"grapes", "apples", "bananas", "cherries", "oranges"};

}

}

By typing in the information this way, you will be able to save space for the different code lines you are creating and make the visual of what you are programming "cleaner." However, while this concept is fairly understandable, I can imagine you are asking yourself, What do I need to do if I want to access the bananas element of my string? Do I need to count it? Well, it depends. Let's move on to the next section to understand how this can be done and how you can access the elements in an array.

Accessing and Modifying Array Elements

When you want to identify a specific element inside an array, you must use its index number. In this case, you will give the program the number of the element you are searching for, such as

public class Main {

public static void main(String[] args) {

String[] myTestArray = {"grapes", "apples", "bananas", "cherries", "oranges"};

System.out.println(myTestArray[3]);

}

}

In this case, you are asking for the element number 3, and the output  will be cherries. Now, suppose that you have this array, and you want to modify one of the elements. Let's say you want to replace the element bananas with the element lemons. This is also possible without having to rewrite the complete code. What you are going to do is use the following statement in the code:

public class Main {

public static void main(String[] args) {

String[] myTestArray = {"grapes", "apples", "bananas", "cherries", "oranges"};

myTestArray [2] = "lemons";

System.out.println(myTestArray[2]);

}

}

And guess what? The output will now be lemons! This is because in the code above, where you have added the statement myTestArray [2] = "lemons"; you are telling the program that you want the myTestArray index number 2 to be replaced by lemons. Therefore, when you print the new list by changing the print statement from System.out.println(myTestArray[2]); to System.out.println("The fruits I bought were: "+ Arrays.toString(myTestArray)); the output will be: The fruits I bought were: [grapes, apples, lemons, cherries, oranges].

It's your turn to try! Use the code above and see the options you can create using different data types. You might even want to try adding some conditional or loop statements using them to see how it all comes out. If you are unsure, you don't have to worry! At the end of the chapter, you will be given more exercises to practice the content.

Multidimensional Arrays

Do you know what an array of arrays is called? If you guessed multidimensional arrays, you are correct! This type of array consists of different arrays within the same object. These dimensions can range from the second to the "nth" dimension according to the number of arrays you have stored. For example, if we wanted to create a two-dimensional array, we would declare it with the following code:

public class Main {

public static void main(String[] args) {

String[][] myTestArray = {{"grapes", "apples", "bananas"},{"pineapple", "pear", "kiwi"}}

}

}

Our myTestArray now has two different arrays with three elements each. This means we are talking about a matrix or table with two rows and three columns. If you look at it from this perspective, you will understand why some databases store information this way. It is because you can obtain the answer you seek with a simple line of code. Suppose we want to identify the element located in the second column and on the second line. This is what the code would look like:

public class Main {

public static void main(String[] args) {

String[][] myTestArray = {{"grapes", "apples", "bananas"}, {"pineapple", "pear", "kiwi"}};

String element = myTestArray[1][1];

System.out.println("The element in the second column of the second row is: " + element);

}

}

The output for this example would be: The element in the second column of the second row is pear. Did you get it right? For easier visualization, this is how the information is being stored:

grapes             apples             bananas

pineapple       pear                 kiwi

Does this make it easier to identify? Now, you can visualize the information if you created a three-dimensional array or another with more dimensions. Like the array structure, you can use all the previously mentioned data types with arrays as long as all arrays contain the same data type.

Now that you have mastered the art of arrays, in the next section, you will be introduced to the concept of collections, what they can do, and the different types that can be used. You will see that collections are an easy way to organize information without writing many code lines, making your code cleaner and easier to read.

## INTRODUCTION TO COLLECTIONS

In Java, when we talk about different elements grouped in one object, we refer to a collection. This is a "predefined architecture capable of storing a group of elements and behaving like a single unit such as an object or a group" (Ravikiran, 2023). These collections have frameworks designed for specific sets of elements in classes and interfaces and allow the user to sort, search, delete, update, and insert information within the indicated group of elements.

For example, if you have a list of lists, a queue of queues, and a set of sets, you will have a collection. We can say that the more "grouped" different data and elements in the code become, the closer they are to becoming a collection. After a collection, the next step in the hierarchy is iterable, but we will not discuss it in this chapter.

It is important to note that Java has two interfaces: the collection and the map interface. If you use either, you will need to import different libraries into your IDE. If you are going to work with the collection interface, the library to download is the java.util.Collection. On the other hand, if you focus on the map interface, you will need to reference the java.util.Map.

When using either of these different interfaces, there are other actions you can use other than the "regular" words that would be used in a program. These special functions are known as interface methods and consist of the following elements and their description, according to Ravikiran (2023):

![](image_rsrc4ZU.jpg)

Now that you have an idea of the commands you can use in a collection, let's look into two of the most common collections used by developers when creating a program: ArrayList and LinkedList. As you might imagine, these will be used to help group lists, and you will soon find out why. Read on to find out how they work.

ArrayList and LinkedList

The benefit of using ArrayList and LinkedList is that, different from the array, these are lists that do not have a preestablished and fixed limit. This means that while the array has five indexes, which will not change, the two different classes seen in this section are more flexible and can be worked on. While they both have advantages and disadvantages, the main idea here is the possibility of storing incredible amounts of data that can be scaled up or down according to need. They will also store all types of elements, and the only difference is the way they work and the time they take to perform certain actions.

Let's see an example of each (Java List, n.d.):

ArrayList

import java.util.List;

import java.util.ArrayList;

class Main {

public static void main(String[] args) {

// Create a list using the ArrayList class

List<Integer> numbers = new ArrayList<>();

// Add elements to the list

numbers.add(1);

numbers.add(2);

numbers.add(3);

System.out.println("List: " + numbers);

// Access element from the list

int number = numbers.get(2);

System.out.println("Accessed Element: " + number)

// Remove element from the list

int removedNumber = numbers.remove(1);

System.out.println("Removed Element: " + removedNumber);

}

}

In this case, the output will be:

List: [1, 2, 3]

Accessed Element: 3

Removed Element: 2

LinkedList

import java.util.List;

import java.util.LinkedList;

class Main {

public static void main(String[] args) {

// Creating list using the LinkedList class

List<Integer> numbers = new LinkedList<>();

// Add elements to the list

numbers.add(1);

numbers.add(2);

numbers.add(3);

System.out.println("List: " + numbers);

// Access element from the list

int number = numbers.get(2);

System.out.println("Accessed Element: " + number);

// Using the indexOf() method

int index = numbers.indexOf(2);

System.out.println("Position of 3 is " + index);

// Remove element from the list

int removedNumber = numbers.remove(1);

System.out.println("Removed Element: " + removedNumber);

}

}

The output, in this case, will be

List: [1, 2, 3]

Accessed Element: 3

Position of 3 is 1

Removed Element: 2

As you can see from the previous examples, both of these lists have similar processes, but they operate differently. In the ArrayList, you will see that there is a more dynamic array because it is not connected to the other lists that are contained in the collection. In addition, accessing each of the elements of the list (as you can see by comparing the outputs of both examples) is simpler and easier to manage when compared to an array list, making managing these lists, especially when retrieving elements, faster. On the other hand, since it comprises several elements, removing or adding an element from one of the lists might take more time than if you used a LinkedList.

In the LinkedList, the elements are connected to the next and the previous elements, which means they are double-linked. Due to this, it is faster to add and remove items but slower to retrieve the elements of the list. If you add both codes to your IDE, you might not immediately see the difference, but when dealing with a large quantity of elements, this is evident. Finally, you will notice that in the code for this type of collection, there is one statement that reads int index = numbers.indexOf(2);. This exclusive element to the LinkedList will enable you to locate the index of the elements easier and faster.

## YOUR TURN TO TRY!

To see if you have learned the content of this chapter, here are seven exercises that cover its content. You will find the answers to these at the end of the book. Even if you get them all right, I encourage you to continue exploring some more and change the variables to help you retain what you have seen so far.

1.  Write a Java program with an integer array to create an array of integers, and within this array, determine the sum of all elements, the maximum and minimum values, sort the numbers in ascending order, and calculate the average of the elements.

2.  Use ArrayList in Java to create a list of strings. In this example, you should use the list to add, remove, and update elements, check if a specific element exists, find the length, and iterate using a for-each loop and print each element.

3.  Create an integer array and convert it to an ArrayList. Carry out list operations like adding, removing, and iterating through elements.

4.  Create a two-dimensional array (matrix) and perform operations that include adding, subtracting, and multiplying the elements of the two matrices, transposing elements, and finding the determinant of a square matrix.

Super challenge: Use LinkedList or ArrayDeque in Java to create a queue and perform operations (enqueue and dequeue) and create a stack and perform stack operations (push and pop).

If your idea is to work with data in Java, then this is certainly one of the most important chapters in the book for you, since they are essential for optimizing your time. In the next chapter, we will dive deeper into Java's heart and understand its methods and how these are the structures that help it be the force it is today. If you are ready to discover the power of Java, move on to the next chapter and learn how to master methods in Java.

CHAPTER 5

MASTERING METHODS IN JAVA

When we build a house, for it to stand, it needs to have beams and a structure to resist the different weather challenges it might undergo. If the house does not have a strong "backbone," it will not stand, and the structure will not hold. In Java, the methods work in the same way, since they will provide the structure and organization needed for the code to work.

In this chapter, you will learn about one of the main concepts of the language, including the different method parameters, what return types are and how they work, a technique called method overloading, and variable scopes. You will see that these methods are what give the code the needed versatility for it to work and even be reused if necessary. The method is what is going to perform the action we are requesting the system to perform, much like a guide to what it is supposed to do. If you are ready to learn more about Java methods and how they are used, read on! One of the most important parts of your journey is about to start.

## INTRODUCTION TO METHODS

Think about a hotel. In it, there are many employees who carry out different tasks; you have those responsible for the reception, room service, maintenance, guest reservations, cooking, cleaning, and so much more. Each of these individuals is performing a specific task with an established set of instructions that allows them to carry out their jobs. This is exactly what the Java method does. When you apply it, you are giving the code the needed instruction of what it should do and only of that specific instance.

In previous examples you have seen in this book, we have used methods, but these were not given a name. In the example below, we have the following breakdown:

//establishing the name of the class

public class Main {

//establishing the method named myMethod (should be used in camel case)

//does not return anything (void), and the entrance parameters for the logic.

//inside the method you can use ints and strings to create the action you need it to carry out

public void myMethod (int parameter1, String parameter2){

}

}

In this case, we have created a logic that does not return any value, but this is not necessarily the case for all the code you are going to see. In another example we could use, we could create the method "volume" and determine in the logic that we want it to return a specific volume for the application.

For example, when you have a virtual assistant, such as Alexa, you will ask it to "increase volume," and what it will do is obtain the parameter it is already at (current volume) and add the requested increase to make it louder. At the same time, this method can be reused because you are going to apply the same logic to decrease the volume. In this case, the method will have two parameters: action, which is to increase or decrease volume, and how much it should be increased or decreased.

This shows the versatility of a method that allows you to reuse the code for different applications, making your code lines more readable, versatile, and reusable. However, to establish what the method needs to do, it is necessary to declare and call it so it can perform the necessary action. Let's see what this would look like in different Java coding examples.

## DECLARING AND CALLING METHODS

Naming, declaring, and calling methods in Java have specific rules that are not mandatory, but should be used as part of the best practices of the Java convention. For example, when naming a method, you should ensure you name it according to the action you want it to carry out. If you are going to ask the program to manage the volume of an application, for example, it should be named "volume," "tone," or something that makes it understandable for others who read the code. You shouldn't, for example, use something like "count," "add," or even "draw," since these would not be directly related to what the method is going to do.

Additionally, when you are naming a method, and it has more than one word, you should use camel case, with the first letter of the first word being in lowercase and, ideally, a verb. The reason for this is that the method is literally the action that the program will carry out; therefore, it is a verb nonetheless. However, it is important to know that "the only required elements of a method declaration are the method's return type, name, a pair of parentheses, (), and a body between braces, {}" (Defining Methods, n.d.). In the structure of naming and declaring a method, you must have the following:

*   The determination of what modifiers you are going to use, such as private or public, which will determine the access to the method by the other parts of the program.

*   What is the data type that should be returned by the code, such as an integer, boolean, or string? If nothing should be returned, then a void should be declared.

*   Determine the name of the method, specifying what it is supposed to do.

*   The parameters that you want to use for this code should be added inside the parenthesis next to the method name. Even if there are no parameters, you should use empty parenthesis to ensure the code is correct.

*   Check if there are any exceptions in the code.

*   Declare the variables and any other information that needs to be inside the method and what it should do. This information should be written in between the open and closed curly brackets that should be used in the code.

If we look again at our previous code, you will see almost all the information we have listed above is available.

public class Main {

public void myMethod (int parameter1, String parameter2){

}

}

In this case, we are not yet calling the method to have it execute what we want it to do. To do this, you need to call the method so that it can be used. "You can call a method by using its name followed by the parentheses and a semicolon" (Simplilearn, 2023). In our example, this is what it could look like:

public class Main {

//calling the code to act in between the curly brackets

static void myMethod () {

System.out.println ("This is me calling my method!");

}

public static void main(String args[]){

myMethod();

}

}

In this case, you will see the method has two elements we have not talked about yet, although you have been using them: parameters and the return value. Let's understand them a little better and what their use and application are when running your Java code.

## UNDERSTANDING METHOD PARAMETERS AND RETURN TYPES

Suppose we go back to our hotel example. Each person will have an assigned task (method) and within these, they will need to follow rules and guidelines. These are the parameters of the Java method. If you are going to ask Java to perform a countdown, you need to specify if it is going to do so by decreasing one, two, or any other amount from the original number. If you are going to program it to increase or decrease the volume, it must be able to understand the command to "increase the volume in a certain number of tones" or "decrease the volume" according to a parameter.

However, it is rather different if you are going to program for software to understand "increase" and "decrease" the volume, or if it should "increase or decrease in a certain amount of tones." Just like in a hotel where the reception might book reservations that come from walk-ins, and the guest services for those made by the telephone, it is important to specify exactly what you want it to do; therefore, the more possibilities it gives you, the better. Let's say in the hotel there is no one in guest services to answer the phone and make the reservation. This means that the task should be directed somewhere else so the individual can reserve a room. In a code for our volume analysis, this would look like this:

public class Main {

//declaring the variable with the current volume

private static int currentVolume = 5;

//declare the main method

public static void main(String[] args) {

System.out.println(" Current volume: " + currentVolume);

//establish the method call (volume) and the parameters (inside the ())

volume("increase", 4);

System.out.println(" Current volume: " + currentVolume);

//establish the method call (volume) and the parameters (inside the ())

volume("decrease", 2);

System.out.println(" Current volume: " + currentVolume);

}

//declare the Volume method

public static void volume(String action, int quantity){

//establish the actions you want it to do using an if-else statement

if ("increase".equals(action)){

currentVolume = currentVolume + quantity;

}else{

currentVolume = currentVolume - quantity;

}

}

}

In this case, you do not have a return value because you are working with a void method and the established parameters for the current volume, which is 5\. However, in Java, it is also possible to have the method return an action and, for this to happen, you will need to use the return keyword. In this case, it will be placed after the function has been declared to tell it what it is you want the system to return.

Using the Return Value

Suppose you are writing a program that you want to calculate the sum of two numbers. In this case, you would need to use the data types that support this function. For example, we could not use the string or the boolean, since they will not return numbers. On the other hand, it would be possible to use double, float, long, and int. While in the previous example, you had established variables, in the case we are about to see, in which the return keyword is used, you can determine "generic" arguments that will make the code more versatile. Here is an example:

public class ReturnExample {

//declare and write the arguments for the method

public int add(int a, int b) {

int c = a+b;

return c;

}

public static void main(String args[]) {

ReturnExample try = new ReturnExample();

int add = try.add(5, 2);

System.out.println("The sum of a and b is: " + add);

}

}

The output in this case will be: The sum of a and b is 7\. In this case, you will be able to declare different values for a and b depending on what you will add inside the parentheses. For example, if you were to change int add = try.add(5, 2); to int add = try.add(3, 2);, the answer would now be different and it would be 5\. This allows you to reuse the same code for different functions, bringing your code versatility and various applications.

But you must be asking yourself, Is it possible to have a method using different parameters or different types such as we have now seen? The answer is yes, it is possible and there is even a technique for it within Java. This is called method overloading and is exactly what we are about to see next.

## METHOD OVERLOADING

When writing code, it is possible to have more than one method within a specific class. It is also possible to have the same method carrying out different tasks and parameters. This technique is called method overloading and is an excellent way to optimize the number of code lines you are using in your program. This method "allows a class to have more than one method with the same name, but with different parameters" by either changing the number of parameters or modifying the data type that you are using (Great Learning Team, 2023).

To illustrate how method overloading works, let's look at the last example we saw in the previous section. In this case, we had the following:

public class ReturnExample {

//declare and write the arguments for the method

public int add(int a, int b) {

int c = a+b;

return c;

}

public static void main(String args[]) {

ReturnExample try = new ReturnExample();

int add = try.add(5, 2);

System.out.println("The sum of a and b is: " + add);

}

}

Suppose you were dealing with a program that needed to deliver not only the full number as a result but also the different numbers with decimal points. While you could create and declare a method for each of the functions, when you use method overloading, you are giving the system the possibility to find the same answers with one parameter. If we were to create the answers in double, for example, the code would look like this:

public class CalculateSum {

public void line(int numberA, int numberB)

{

int sum = numberA + numberB;

System.out.println("Using the integer calculation, the answer is: " +sum);

}

public void line(double numberA, double numberB)

{

double sum = numberA + numberB;

System.out.println("Using the double calculation, the answer is: " +sum);

}

public static void main(String[] args)

{

CalculateSum calc = new CalculateSum();

calc.line(4, 3);

calc.line(4.3, 3.6);

}

}

In this case, the name of the method is line, and the variable is called sum. You have used the line method for both the int and the double sum; therefore, you are overloading the method. In this case, as you can see, instead of creating different methods and lines for the same calculation, you only added two additional code lines and variables to obtain the result, making the code more readable. The output for this example would be:

Using the integer calculation, the answer is: 7

Using the double calculation, the answer is: 7.9

Another way this could be done is by increasing the number of arguments in the function. Suppose that what you want to do is obtain first the numberA and then the sum of numberA and numberB. Increasing the number of parameters is also considered overloading the method. In this case, the code would look like this:

public class CalculateSum {

public void line(int numberA)

{

int sum = numberA;

System.out.println("Using the integer calculation, the answer is: " +sum);

}

public void line(int numberA, int numberB)

{

int sum = numberA + numberB;

System.out.println("Using the int sum, the answer is: " +sum);

}

public static void main(String[] args)

{

CalculateSum calc = new CalculateSum();

calc.line(4);

calc.line(4,7);

}

}

Here, you have once more overloaded the system and the output should be:

Using the integer calculation, the answer is: 4

Using the int sum, the answer is: 11

Therefore, when you are carrying out method overloading, it is important that you are changing either the number of arguments or their data type. Otherwise, "it is not method overloading if we only change the return type of methods. There must be differences in the number of parameters" (Java Method Overloading, n.d.).

As you have seen, when we declare a method, we will need to use a variable to determine what the storage of the data will be. These variables will be used to store the different characteristics attributed to the data. In the next section, we will see how the variable data containers store values and the scopes that can be applied.

## THE SCOPE OF VARIABLES

When you assign the memory for the location of the data, you are using a variable. This means that when you say int a = 2, you are assigning the variable "a" the value 2\. In the same way that when we type in the string "Hello Data", the values being stored are the letters or the words that are between the quotation marks. When we talk about the scope of the variable, we are referring to what the compiler is being told "about the segment within a program where the variable is accessible or used. Programmers can scope the variables lexically or statically in the case of Java variables" (Vats, 2021).

Variables have different scopes and different characteristics. For example, if you have a public variable, this means it will be available from any place in the program, which means you can call it at any time in the code. On the other hand, if you declare it as "private," this means it will only be accessed within the methods of the class to which it belongs. Let's take a look into each of the variable scopes that can be used in Java and their best applications according to baeldung (2019):

*   Bracket scope: Variables declared inside brackets will determine their scope. This means they can be declared after the class, methods, and even just for themselves. When you input a variable within the brackets, and they are not in any of the previously mentioned examples, this means they will only work inside the brackets. To understand this, let's see an example:

public class BracketScopeExample {

public void mathOperationExample() {

Integer sum = 0;

{

Integer number = 2;

sum = sum + number;

}

// Compiler error, number cannot be resolved as a variable

// Integer number++;

}

public static void main(String[] args) {

BracketScopeExample example = new BracketScopeExample();

// If you uncomment the next line, it would cause a compilation error because the number is out of scope

example.mathOperationExample();

System.out.println("Trying to access number outside its scope: " + example.number);

}

}

*   Class scope: When a class variable is declared, you will need to do it inside the curly brackets that are open after the class is called. In this case, if you add the private to the variable within the class but outside the method, this means it will be accessible inside all the different lines of the class. In this case, we could mention the example:

public class ClassVariable {

// here the double amount is declared and can be accessed within the class

// since it has been declared after the curly brackets placed after the class and declared private.

//if private hadn't been declared, it would be possible to use it throughout the whole program.

private double amount = 5.26;

public void methodName() {

amount+=2.3;

}

public void anotherMethodName() {

double otherAmount= amount + 3.6;

}

}

System.out.println("Other Amount: " + otherAmount);

}

public static void main(String[] args) {

// Create an instance of ClassVariable to use the variable in another example

ClassVariable example = new ClassVariable();

// Access and modify the "amount" variable by using the object instance

System.out.println("Initial Amount: " + example.amount);

example.methodName();

System.out.println("Amount after methodName: " + example.amount);

// Calling anotherMethodName to demonstrate the usage of 'amount'

example.anotherMethodName();

}

}

*   Loop scope: Similar to what you will see in the method scope when you declare a variable inside a loop, it will only be accessible within the loop you are working with. This means that even if you have another loop and try to call this variable, it will be inaccessible and generate a compilation error, such as:

public class ClassVariable {

double amount = 5.26;

public void methodName() {

amount+=2.3;

for (int i = 0; i < 5; i++) {

// Inside the loop, you can use the "amount" variable

double loopAmount = amount + i;

System.out.println("Loop Iteration " + i + ": " + loopAmount);

}

// The "amount" variable is still accessible outside the loop

amount += 1.5;

}

public void anotherMethodName() {

double otherAmount = amount + 3.6;

System.out.println("Other Amount: " + otherAmount);

}

public static void main(String[] args) {

ClassVariable obj = new ClassVariable();

obj.methodName();

obj.anotherMethodName();

}

}

*   Method scope: In the method scope of the variable, you do not need to use a qualifier such as private or public, since if it is declared inside the method, then it will only be accessible inside it. To declare a variable that belongs to the method scope, you should add it within the curly brackets after it has been called, such as

public class ClassVariable {

public void methodName() {

// Declare the variable inside the method. It will only be available inside this method.

double amount = 5.26;

// You can use the "amount" variable within this method

amount += 2.3;

System.out.println("Amount in methodName: " + amount);

}

public void anotherMethodName() {

// There will be a compilation error since you are trying to refer to the "amount"

// that was declared in the previous method, but it cannot be accessed here.

// double otherAmount = amount + 3.6;

}

public static void main(String[] args) {

// Creating an instance of ClassVariable

ClassVariable example = new ClassVariable();

// Call the methodName to demonstrate the usage of the "amount" variable

example.methodName();

// Call anotherMethodName to demonstrate the compilation error

example.anotherMethodName();

}

}

Now that you understand the different scopes variables can have, it is time to learn the last critical element you should know when discussing methods. This is called a Java recursion, and happens when the method calls itself. "A physical world example would be to place two parallel mirrors facing each other. Any object in between them would be reflected recursively" (Java Recursion, n.d.). Let's learn more about them and see how these can be used.

## RECURSIVE METHODS

Recursive methods in Java can be complicated, and the best way to learn them is to use examples. However, they can also be quite tricky, since they can become endless code lines if you are not careful. On the other hand, if they are properly applied, you will have an efficient way to break down complex problems into simpler conditions and work them as you need (Java Recursion, n.d.).

Here is an example of how this would be applied in a situation where we want the program to calculate the value of 5 factorial (5!):

public class RecursionExample {

public static void main(String[] args) {

int factorialResult = calculateFactorial(5);

System.out.println("Factorial of 5 is: " + factorialResult);

}

public static int calculateFactorial(int n) {

//here you are defining that you will use an integer that will have "n" as the parameter

// in this case, base case checks if n is 0 or 1, in which case the factorial is 1

if (n == 0 || n == 1) {

return 1;

} else {

// Recursive call to calculate factorial

return n * calculateFactorial(n - 1);

}

}

}

The output will be the factorial of 5, which is 5! = 5 x 4 x 3 x 2 x 1 = 120\. Nevertheless, as mentioned earlier, this is quite a complex concept that you will need to practice to ensure that it is being properly applied. You can try using different approaches such as adding numbers from 1–10, determining exponential values, and so on. The most important matter is that you practice. Speaking about practice, it's your turn to try! Should we look at the exercises for this chapter on methods?

## YOUR TURN TO TRY!

Create a Java program with overloaded methods to calculate the area of a circle and a rectangle, in which the main method should be used to demonstrate the use of the methods. Here are the requirements you must follow to ensure you obtain the correct result:

*   Create a class named AreaCalculator.

*   Implement overloaded methods for each shape's area calculation: circle and rectangle.

*   Use the following formulas for area calculation:

○ Circle: area = π × r × r (where r is the radius).

○ Rectangle: area = length × width (where length and width    are the sides).

Now that you understand how methods work, we can dive deeper into the heart of Java and what makes it such a unique language. In the next chapter, we will explore how to create classes and objects, and principles of OOP. If you are ready to continue our adventure, let's embark on this exciting journey and decode the mysteries of OOP in Java!

CHAPTER 6

OBJECT-ORIENTED PROGRAMMING

As mentioned way back in this book's introduction, Java is an OOP language, which means that it uses objects to determine what will happen in the code we are building. In this chapter, you will learn everything about creating objects, classes, their principles, characteristics, and concepts such as encapsulation, polymorphism, and inheritance. If you are ready to see the "core" of Java and learn what makes it a unique language to learn and program in, read on! You are about to gain insight into its inner works and the different ways it can be used.

## INTRODUCTION TO OOP

When developers decide to use OOP in their coding, they are striving to achieve the DRY principle, which stands for "Don't repeat yourself." This is because when you create and use objects to code, you are making the code easier to create, modify, maintain, and debug, enabling different uses with less code and less development time. These advantages make the program easier to execute and the code lines more readable with a clear and understandable structure (Java OOP [Object-Oriented Programming], 2020).

Developers who use OOP apply this technique to "real-world entities like inheritance, hiding, and polymorphism in programming. Its main aim is to bind the data and functions that operate on them so that no other part of the code can access this data except that function" (RishabhPrabhu, 2023). Just as we have seen with methods, you can use the access modifiers to determine how accessible the OOP classes are (using public, protected, private, and default), and also by mentioning the different actions you want the object to have.

To better understand what it means to have an OOP that focuses on classes and objects, we should first understand what they are and how they are related. These are the two main characteristics of OOP, which stand on the pillars of encapsulation, polymorphism, abstraction, and inheritance. Together, these six items support the existence of OOP and make Java the versatile and reusable language it is.

Although we are going to learn about each of these pillars in the following sections, it is essential that we understand what classes and objects are. You have already seen these in varied applications in previous exercises but, apart from the initial explanation in Chapter 1, we haven't gone into much detail regarding what each of these are. But do not worry because the time has come, and you are about to learn more about them. Move on to the next section to learn the intricacies of classes and objects, how they relate to each other, and what makes them so special when writing code in Java.

## CLASSES AND OBJECTS

To understand what objects and classes are, all you need to do is look around you: They are everywhere! This is because classes and objects are real-life items, concepts, and entities that are applied to our software. When we are talking about software development, we must consider that these classes and objects also have behaviors and states, and this is exactly how they work in the real world. "A software object's state is stored in fields and behavior is shown via methods. So, in software development, methods operate on the internal state of an object, and the object-to-object communication is done via methods" (Java Object and Classes, 2019).

An association that will make it easy for you to understand is that the class is the "blueprint" that describes a general class, such as "student." In this case, this is a generic approach that determines the characteristics of a group. Next, we can describe its behavior and state, which could be, for example, int age, int grade, double height, and string "loud," which are all characteristics that can be used to describe the "student" class.

Here are a few more examples that will help you associate the differences between classes and objects by using real-world examples:

Class: Vegetables

*   Objects: carrot, squash, broccoli

Class: Motorcycles

*   Objects: Suzuki, Honda, Harley-Davidson

Class: Animals

*   Objects: elephant, giraffe, rhinoceros, monkey

But, at the same time, these objects that we have here can also be classes, such as (and now implementing an example of the data types that could be used):

Class: Carrot

*   Objects: String color, double size, double weight

Class: Harley-Davidson

*   Objects: String color, boolean wheels, int places

Class: Monkey

*   Objects: String color, boolean banana, double weight

In all these classes, you can observe that we have a "general" class that describes a group of objects contained within them, which makes the animal, monkey, for example, an object of the animal class. But monkeys can also be a class, and if this happens, the weight, for example, will be an object of the class. Now that these concepts are clear, we can further explore the concepts of classes and objects in Java and how they can be used.

Classes in Java

As you know, classes are the blueprints that establish what an object does. In this case, the class must be created to relate to the objects used in the code. For example, in the code below, we have the class named School.

public class School {

String teachers;

int grades;

String subjects;

}

The objects that were created in this class relate directly to the main "blueprint" that has been established. This means that we have the objects: teachers, grades, and subjects. In this partial code, we have established the constructor "public," which you already know will be accessible to all parts of the code. Since we have mentioned objects, let's examine what they are and how they can be used.

Objects in Java

When you use objects in Java, you are creating real-world entities that have characteristics that relate to that class. In this case, the object will need to have a state, which is its attributes, a behavior, which will be represented by the method, and an identity, which will establish how an object relates to another. In the case of identity, you should keep in mind that each object will have a unique identity with a unique identifier and state. If we were to use as an example the class "Cat," we could say that the objects that relate to it are breed, color, size, and weight, and the behavior (methods) would be meow, purr, sleep, and eat.

As soon as an object of a certain class is created, we can say it has been instantiated, which means that "all the instances share the attributes and the behavior of the class. But the values of those attributes, i.e., the state, are unique for each object. A single class may have any number of instances" (Miglani, 2023). As you have seen in the previous example with the class Cat, it can have different characteristics, and the more you specify them, the more detailed the class will be.

However, depending on the code you are creating, there can be many different objects; the more objects you create, the more difficult it becomes to read the code. In this case, there is another technique that is applicable in OOP that will prove to be useful for the developer. This is called data encapsulation. In the upcoming section of this chapter, we are going to learn what this is and also understand information hiding.

## ENCAPSULATION AND INFORMATION HIDING

Encapsulation and data hiding are powerful techniques in Java that enable different objects to be grouped together under the same class. When you encapsulate the data from a specific class, you are protecting it from being accessed by other classes, making the code safer. At the same time, when you encapsulate the objects in the Java code, you can hide the information and make it "secret," so to speak, so they cannot be accessed by other parts of the code. When you use both of these features, it makes your code more protected and efficient, since you will be able to divide them into modules and modify only this part without affecting the remainder of the code. In this section, we are going to look at the different ways that encapsulation and information hiding can be used to enhance your code and make your product better.

Encapsulation

If you understand the concept of classes and objects, encapsulation will likely be a stroll in the park. This is because "encapsulation aims to protect the data from outside interference and provide a controlled interface for accessing and modifying the data" (Khan, 2023). When this code is controlled, it is possible to reuse it and provide abstract classes and objects, which we will see more about further along in this chapter.

When you are applying encapsulation to your code, you will need to use what are called access modifiers with methods known as getter and setter. Within these, you will be able to determine the modifiers between public, private, protected, and default. Here is a small explanation of what each of these will do:

*   Public: When this modifier is used, the object can be accessed throughout all the code.

*   Private: This modifier will make the objects available only within the class in which it is located.

*   Protected: "This encapsulation lets you declare that a method or variable can be accessed by subclasses of your current class and its subclasses only (you cannot use this keyword on methods)" (Khan, 2023).

*   Default: When you use the default modifier, you are establishing that the nonstatic members are all defined according to the visibility established by the private package.

Here is one example of how the objects in your code can be encapsulated using public and private modifiers. In this example, you have the "Person" class that encapsulates the name and age variables by declaring them as private and provides public methods (getName, setName, getAge, setAge, printDetails) to access and modify these variables. This helps control access and apply validation logic, making safer and more modular coding possible.

//the Person.java file so it can be accessed by the code

Person.java

public class Person {

// Encapsulated variables (private)

private String name;

private int age;

// Constructor

public Person(String name, int age) {

this.name = name;

this.age = age;

}

// Public methods to access and modify encapsulated variables

public String getName() {

return name;

}

public void setName(String name) {

this.name = name;

}

public int getAge() {

return age;

}

public void setAge(int age) {

// Validation logic can be added here

if (age > 0) {

this.age = age;

} else {

System.out.println("Invalid age");

}

}

// Other methods of the class

public void printDetails() {

System.out.println("Name: " + name);

System.out.println("Age: " + age);

}

}

However, when you carry out encapsulation (or data bundling), it is essential that you test the code to ensure the correct relationships have been established and the necessary elements are being accessed in the code. For this, we will carry out what is called "Class test," which could easily be done using the following application:

Class Test Example

//create the EncapsulationExample file to run the code

//In this case, you will need to add the code from the previous section first

//and the one you are about to see next

public class EncapsulationExample {

public static void main(String[] args) {

// Create an instance of the Person class

Person person = new Person("John", 25);

// Access and modify encapsulated variables using public methods

person.setName("Mary");

person.setAge(30);

// Access information using public methods

person.printDetails();

}

}

If you try this code in your IDE (adding them both as instructed), you will find that the output will be

Name: Mary

Age: 30

This output shows you how encapsulation makes it possible to have a controlled access and modification of the encapsulated variables, guaranteeing the proper functioning of your code.

What Is Data Hiding?

When you have objects that need to be hidden for security purposes (especially for code that is confidential and could be hacked), you can use the concept known as data hiding. This technique is used only if you have encapsulation, since it implies that you are restricting access to the data, as encapsulation allows you to do. In this case, the example that can be mentioned is:

Let [us] declare a BankAccount class, and [that] we have a data member AcBalance inside this class. Here, the account balance is sensitive information. In this example, we may allow an external application to check the account balance, but we [may] not allow the application to change the account balance. Hence, in this case, we restrict the alternation in account balance by declaring the account balance attribute private. The major advantage of data hiding is that it reduces the complexity of the system.

(Difference Between Data Hiding and Encapsulation, n.d.)

To see how data hiding can be applied, you will now see an example that will clearly illustrate this. In it, the Circle class hides the radius field and provides a public method (getRadius) to access it.

//create a file for the class

Circle.java

public class Circle {

private double radius;

public Circle(double radius) {

this.radius = radius;

}

// Public method to get the radius (data hiding)

public double getRadius() {

return radius;

}

}

//create a new file for data access and class testing

DataHidingExample.java

public class DataHidingExample {

public static void main(String[] args) {

Circle circle = new Circle(5.0);

// Accessing the radius through a public method

double radius = circle.getRadius();

System.out.println("Radius: " + radius);

}

}

Since we used the public and private modifiers in this case to hide the information, it is possible you might be confused about the use and the application of data hiding. For this reason, we should take a look into how these two are different and how they should be applied when coding. As we move on to the next section, you will see that these concepts are closely related.

How Are Encapsulation and Data Hiding Different?

In the example you are about to see, encapsulation is demonstrated by bundling the radius data and the calculateArea method together in the Circle class. With this example, you will be able to see that data hiding is a part of encapsulation; therefore, you can have data hiding if you apply encapsulation, but you cannot have data hiding without first encapsulating the objects of the code in the class.

public class Circle {

private double radius;

public Circle(double radius) {

this.radius = radius;

}

// Public method to calculate area (encapsulation)

public double calculateArea() {

return Math.PI * radius * radius;

}

}

public class EncapsulationExample {

public static void main(String[] args) {

Circle circle = new Circle(5.0);

// Accessing the radius indirectly through an encapsulated method

double area = circle.calculateArea();

System.out.println("Area: " + area);

}

}

Encapsulation is a broader concept that involves bundling the data (fields) and methods that operate on the data into a single unit (class). While data hiding is used to secure the data and the information, the encapsulation is not necessarily used for this purpose, although it could be. It not only involves data hiding but also emphasizes the concept of bundling data and methods together. While they can both be used to hide how complex your code is, when you apply data hiding, you are more worried about restricting the data use and are applying specific keywords to ensure this happens.

While these are concepts that are easily achieved with practice and dedication, the next items we are about to see are also important characteristics of OOP: inheritance and polymorphism. These two concepts are features that help increase the usability of the code and make it more versatile for different applications. As we move on to the next section, you will learn more about these concepts and the ways they can be efficiently applied in your code.

## INHERITANCE AND POLYMORPHISM

Inheritance and polymorphism are important concepts of OOP since they enable the code to be more malleable. While the use of inheritance will help you understand the concepts of classes and superclasses, polymorphism will help you comprehend the applications of more than one method and parameter. In this section, we will see how these two concepts are used in Java and examples of their application.

Inheritance

Inheritance, as you might imagine by the name, is when the characteristics of a class are passed on to another. In this case, it is important to understand the difference between the concepts of superclass (parent or base class) and subclass (child or derived class). Before you see the example of the code below, let's see how this can be applied in a real-world example.

Let's say we have the superclass "Animal". In this superclass, we have dogs, cats, birds, giraffes, elephants, and so on. While it is possible to say that all animals eat, we can also say that only the subclass of animal "dog" barks. Therefore, it is possible to assume that under the superclass "Animal," we have the eat method, but we can also have the subclass "dog" that is also an animal, but has different characteristics from the other animals within the Animal subclass.

If you think about inheritance in hierarchical groups, you will see that the concept is rather simple. This is how we can think about it:

Animal → eats / sleeps

dog → barks

cat → purrs

For dog, here is what this information would look like in Java code:

// Base class (superclass)

class Animal {

String name;

Animal(String name) {

this.name = name;

}

void eat() {

System.out.println(name + " is eating.");

}

}

// Derived class (subclass) inheriting from Animal

class Dog extends Animal {

Dog(String name) {

// Calling the constructor of the superclass

super(name);

}

void bark() {

System.out.println(name + " is barking.");

}

}

public class InheritanceExample {

public static void main(String[] args) {

// Creating an instance of the subclass

Dog myDog = new Dog("Buddy");

// Accessing properties and methods from the superclass

System.out.println("Name: " + myDog.name);

myDog.eat();

// Accessing methods specific to the subclass

myDog.bark();

}

}

As you have seen in the above example, we have exactly what was mentioned in the explanation. While the superclass "Animal" has the method "eat" and this characteristic is derived from the main class, when we have the method "bark," this is exclusive to the class dog. The same could be said if we were talking about "car purr," "bird chirp," and all other behaviors demonstrated by animals that are exclusive to their class group.

The example above shows that "Animal" is the superclass with a name property and an "eat" method. The subclass, in this case, is "Dog," which inherits from "Animal" and introduces a new method, "bark." Since the "Dog" class is a subclass of the "Animal" superclass, its class can access the properties and methods of the "Animal" class through inheritance. When you have this relationship, it is possible to reuse the common functionalities defined in the superclass, while you can also specify a unique method in the subclass; thus, showing how the "DRY" principle is applied when developing software.

When you apply inheritance, it bec0mes easier to organize your code and make it less "noisy." When you apply inheritance to your code, you will also see the possibility to implement another technique native to OOP. This is called polymorphism, which we will talk about next.

Polymorphism

Remember when, in inheritance, we said there can be two different subclasses to the superclass? It is possible that the parent class has two or more methods attributed to it, such as eat and sleep, that can be applied to all classes. When this happens, not only are you implementing inheritance, but it also gives you the possibility of applying polymorphism. When you give the parent class an attribution from the child class, you are implementing this technique, since the root of the word means that it has many forms. The possibility of performing the same action in different ways is a characteristic of Java that attracts many users.

When we talk about polymorphism, there are two different ways it can be applied. They are the compile-time and the run-time polymorphism. In these two different method applications, you will see that while one uses method overloading, which we have already seen, the other will apply method overriding that we will talk about now. Here are the characteristics of these two different techniques.

Compile-Time Polymorphism

This method is known as the "static" method since it will happen, as the name suggests, only when the program is being compiled. In this case, what you will do is overload the method, as seen previously. To recap, when you apply overloading in your code, you add different methods but with different parameters. Here is what the code would look like in this situation:

class MathOperations {

int add(int a, int b) {

return a + b;

}

//overload method by adding different parameters (characteristics) to the code, from int to double, but still using add

double add(double a, double b) {

return a + b;

}

}

"Function overloading is one of the ways to achieve polymorphism, but it depends on technology and which type of polymorphism we adopt. In Java, we achieve function overloading at compile-time" (Adware, 2022). In this case, inheritance is not necessarily involved, which makes this code less flexible, since everything will run when the time to compile it comes.

On the other hand, we also have run-time polymorphism, which has unique characteristics that we could mention are almost the opposite of compile-time. As we move on to this next section, you will learn about its characteristics and how it differs from what we have just seen.

Run-Time Polymorphism

This type of polymorphism is also known as dynamic polymorphism, and involves inheritance. To apply this technique, method overloading is not necessary, but you will need to apply method overriding, which "says the child class has the same method as declared in the parent class. It means the child class provides the specific implementation of the method that has been provided by one of its parent classes" (Adware, 2022). This execution is slower than the compile-time, but it is also more flexible.

Here are two code examples where this is applied, and you will be able to identify the difference and the application of inheritance in them:

class Animal {

void makeSound() {

System.out.println("Some generic sound");

}

}

class Dog extends Animal {

void makeSound() {

System.out.println("Bark");

}

}

For interfaces, in this different application, you will see that it is also possible to apply run-time polymorphism when you have a method that is void and does not have any action within it.

interface Shape {

void draw();

}

class Circle implements Shape {

void draw() {

System.out.println("Drawing a circle");

}

}

Essentially speaking, when you have polymorphism, it will allow the objects to adopt different forms and behaviors. In the example below, you will see that the "Dog" class can have a method "sound()" that returns "bark," while the "Cat" class can also have a "sound()" method that returns "meow." The Dog and Cat classes are subclasses of Animal and override the makeSound method with their specific sounds.

// Base class (superclass)

class Animal {

void makeSound() {

System.out.println("Some generic animal sound.");

}

}

// Derived class 1 (subclass)

class Dog extends Animal {

@Override

void makeSound() {

System.out.println("Woof! Woof!");

}

}

// Derived class 2 (subclass)

class Cat extends Animal {

@Override

void makeSound() {

System.out.println("Meow! Meow!");

}

}

public class PolymorphismAnimalExample {

public static void main(String[] args) {

// Creating objects of different subclasses

Animal myDog = new Dog();

Animal myCat = new Cat();

// Calling the overridden method, which varies based on the actual object type

myDog.makeSound(); // Output: Woof! Woof!

myCat.makeSound(); // Output: Meow! Meow!

}

}

If you go back a little in this section, you will see that interfaces were mentioned. But you must be asking yourself, What is an interface, and how is it used? This is a very good question since it is also an important Java characteristic that was implemented in more detail from Java version 8. Based on this information, let's take a look at the last section of this chapter, in which you will learn Java concepts before learning how to create classes and test your knowledge.

## ABSTRACT CLASSES AND INTERFACES

To understand the application of abstract classes and interfaces, it is first important to identify what a normal concrete class is. It is nothing more than the classes you have seen up to now that have methods that represent the behavior of a certain object. However, when you want to hide this implementation or even the complexity of the code you are creating, you can apply two methods known as abstract classes and interfaces (baeldung, 2022). Read on to find out their main characteristics and implementation methods.

Implementation

When you apply to the abstract class, the main thing you should remember is that the keyword abstract needs to be used before the class name. These classes will have no restrictions, and when you have abstract methods, the class should be abstract as well. One of its essential characteristics is that you do not need to use the keyword new when creating an object, it will immediately override the method with an anonymous class, although it will only be extended to one class. At the same time, this does not mean that these methods do not need to be declared or defined. This is a possibility that can or cannot be used when they are being implemented for both abstract classes and interfaces (baeldung, 2022).

Conversely, when you have an interface, it is nothing more than a "contract" that you are establishing in the code that does not take any action. Here, the main characteristic is the use of the interface keyword, which will help implement it in the subclasses. Differently from the abstract class, multiple interfaces can be implemented in your code, which makes it an ideal solution to use if you are using multiple inheritance and different classes with district hierarchies. When we use an interface, we want to understand how the behavior can be added to the object.

Here is an example of how abstract classes and interfaces can be implemented with the use of inheritance:

// Abstract class

abstract class Shape {

// Abstract method (to be implemented by subclasses)

abstract double calculateArea();

// Concrete method

void display() {

System.out.println("This is a shape.");

}

}

// Concrete subclass 1

class Circle extends Shape {

double radius;

Circle(double radius) {

this.radius = radius;

}

@Override

double calculateArea() {

return Math.PI * radius * radius;

}

}

// Concrete subclass 2

class Rectangle extends Shape {

double length;

double width;

Rectangle(double length, double width) {

this.length = length;

this.width = width;

}

@Override

double calculateArea() {

return length * width;

}

}

// Interface

interface Sound {

void makeSound();

}

// Class implementing the interface

class Dog implements Sound {

@Override

public void makeSound() {

System.out.println("Woof! Woof!");

}

}

// Class implementing multiple interfaces

class Parrot implements Sound {

@Override

public void makeSound() {

System.out.println("Squawk! Squawk!");

}

}

public class AbstractClassInterfaceExample {

public static void main(String[] args) {

// Abstract class example

Shape circle = new Circle(5);

circle.display();

System.out.println("Area of Circle: " + circle.calculateArea());

Shape rectangle = new Rectangle(4, 6);

rectangle.display();

System.out.println("Area of Rectangle: " + rectangle.calculateArea());

// Interface example

Sound dog = new Dog();

dog.makeSound();

Sound parrot = new Parrot();

parrot.makeSound();

}

}

As you can see by how the code is set up, it enables abstract classes and interfaces to provide common behavior and structure for related classes in a hierarchy. Here is the output you obtain when you add this code to your IDE:

This is a shape.

Area of Circle: 78.53981633974483

This is a shape.

Area of Rectangle: 24.0

Woof! Woof!

Squawk! Squawk!

In this example, you can see that "Shape" is an abstract class with an abstract method "calculateArea()" and a concrete method "display()." At the same time, "Circle" and "Rectangle" are concrete subclasses of "Shape" that implement the "calculateArea()" method. In the second part of the code, when we are talking about animal sounds, "Sound" is an interface with a method "makeSound()". In this case, "Dog" and "Parrot" are classes that implement the "Sound" interface.

When you create an object, you are likely going to use it for something. After all, it is useless to create an object, method, and even class, if you are not going to use it in your code. This will only pollute the code and make it more difficult to read and understand. For this reason, we must understand how to work and manipulate objects while coding, as well as identify best practices for them.

## WORKING WITH OBJECTS

In this section, you are going to see in practice what you should do to create a class and an instance and how to make them interact with an object. This is the core of the Java code, since what you are doing is establishing these to determine what it will do. However, since you have already seen different applications and implementations of this code, I will take a moment and use this opportunity to show you how different objects can be manipulated using a lambda.

"Lambdas allow programmers to make their code shorter, efficient, and more functional. They help one to iterate through a collection of objects and avoid numerous mistakes" (How to Manipulate Objects, 2021). Nonetheless, before we learn how to use lambdas in Java, let's use two examples to recap how classes and instances are created. Creating this class and these instances will be important to understand the last example, where the lambda will be used. Please note that if you are going to paste this code into your IDE, you should remember to remove the subheadings, so the code can work.

Creating a Class

// Define a simple class

public class Car {

// Fields (attributes)

String model;

int year;

// Constructor

public Car(String model, int year) {

this.model = model;

this.year = year;

}

// Method to display information

public void displayInfo() {

System.out.println("Model: " + model);

System.out.println("Year: " + year);

}

}

Creating an Instance

public class ObjectInteractionExample1 {

public static void main(String[] args) {

// Create instances of the Car class

Car car1 = new Car("Toyota Camry", 2022);

Car car2 = new Car("Honda Accord", 2021);

}

}

Interacting With Objects

public class ObjectInteractionExample2 {

public static void main(String[] args) {

// Create instances of the Car class

Car car1 = new Car("Toyota Camry", 2022);

Car car2 = new Car("Honda Accord", 2021);

// Access and modify object properties

// Display information about car1

car1.displayInfo();

// Display information about car2

car2.displayInfo();

// Modify the year of car1

car1.year = 2023;

// Display updated information

car1.displayInfo();

}

}

In this example, we create a "Car" class with fields (model and year), a constructor to initialize objects, and a method "displayInfo" to display information about the car. The next thing we do is create two instances of the "Car" class ("car1" and "car2") using the new keyword. Finally, we interact with the objects by accessing and modifying their properties and calling methods.

After you have read this chapter, you now know all the different ways and techniques to write basic code in Java. It is time to test your knowledge and see if you have committed to memory what you have read so far. Are you ready to test what you've learned?

## LET'S TEST YOUR KNOWLEDGE!

1\. Which of the following is true about an object in Java?

a. An object is an instance of a method

b. An object is an instance of a class

c. An object is a variable

d. An object is a loop

2\. What is the primary purpose of abstract classes in Java?

a. to create objects directly

b. to provide a blueprint for other classes

c. to hide information

d. to execute code without an object

3\. Polymorphism in Java is achieved through:

a. inheritance

b. encapsulation

c. interfaces

d. overloading and overriding

4\. In Java, what does inheritance represent?

a. the ability of a class to implement multiple interfaces

b. the ability of a class to extend another class

c. the process of creating multiple objects

d. the ability of a method to accept multiple parameters

5\. What is encapsulation in Java?

a. wrapping data and code that operates on the data into a     single unit

b. hiding information by making methods private

c. creating multiple instances of a class

d. achieving multiple inheritances

6\. Which keyword is used to achieve method overriding in Java?

a. override

b. extends

c. implements

d. super

7\. What is the primary purpose of an interface in Java?

a. to define instance variables

b. to provide a common method implementation

c. to achieve multiple inheritances

d. to declare a set of method signatures

8\. Which of the following is an example of data hiding?

a. making a method public

b. making a method private

c. using the "static" keyword

d. implementing an interface

9\. What is the keyword used for explicit casting in Java?

a. cast

b. to

c. convert

d. type

10\. Which concept allows a class to have multiple methods with the same name but different parameters?

a. inheritance

b. polymorphism

c. encapsulation

d. abstraction

Having journeyed through the core of Java with OOP, you are now ready to navigate more complex matters. As you know, you already have the core knowledge of Java and are certainly ready to skill up your level. For this reason, in the next chapter, we will learn all about exception handling. By learning this, you will see how to anticipate, detect, and handle errors in your code. I encourage you to keep going; your mastery of Java is just around the corner!

SPEAK THE LANGUAGE

“It is not enough for code to work.”

ROBERT C. MARTIN

In the introduction, we learned two conflicting things about Java that can cause a problem for many novice programmers: It’s one of the most popular programming languages in usage, and the complex code makes it a challenge for new programmers.  

For many programmers, the theory is all there, but when you’ve learned it formally, you don’t necessarily have an understanding of its depth and versatility. In writing this book, my goal is to make that understanding accessible so that new programmers can access all that Java has to offer without stumbling over issues with debugging or getting stuck at a specific coding hurdle. I want to bridge that gap between accessibility and potential.

Now that we’re further through our journey and your understanding of Java is growing, I’d like your help bridging this gap for other novice programmers. Java is a language like any other: The more people speak it fluently, the richer the possibilities for communication are.

If you would be willing to take a couple of minutes to leave your feedback online, you’ll help more programmers find the information they need to bridge that gap and gain a firm understanding of the language.

By leaving a review of this book on Amazon, you’ll show other programmers where they can find this essential link between what they know already and a true understanding of Java. 

It’s true that Java is a complex language, but the more you discover about its potential and its practical usage, the easier it is to master. Your review will help new readers access that essential understanding.  

Thank you so much for your support. Languages grow when we speak them, and in the case of Java, speaking about them is the first step to enabling this.

CHAPTER 7

EXCEPTION HANDLING

If you are just starting your journey using Java, then, more likely than not, you are going to have to correct errors in your code. Regardless of whether we are talking about a semicolon, a missing bracket or you are missing a class declaration, knowing how to correct your code and handle exceptions is essential for a good developer. In fact, knowing how to handle exceptions in Java is what differentiates a good from a great developer, and the same applies to the quality of your code.

Knowing how to keep your program running even when there are errors is an essential skill for all developers. In this chapter, we are going to highlight the importance of handling exceptions in Java. You will learn how to effectively understand, catch, and manage these errors, ensuring that the program you have created is running according to plan in its execution.

Additionally, you will also learn how to apply the try-catch and the finally blocks in your code to help you handle errors and optimize production. Get ready to understand what expectations are, how to solve them, and make your program's flow the best it can be. You will certainly be impressed and impress others as well.

## UNDERSTANDING EXCEPTIONS

When an exception happens, we are talking about an undesired event happening during the execution of the program. Although this is normal, it is important to be aware of them so that your program's flow is not affected. The exception can happen in a method or an object, and the main exceptions a developer can deal with are:

*   code errors

*   device failure

*   invalid user input

*   loss of network connection

*   opening an unavailable file

*   physical limitations (out-of-disk memory) (GeeksforGeeks, 2023a)

The main difference between an event being named an exception or an error is how it can be solved. Exceptions can usually be solved by modifying something that is affecting the process. On the other hand, when you have an error, these usually cannot help the code be recovered, such as "Java virtual machine (JVM) running out of memory, memory leaks, stack overflow errors, library incompatibility, infinite recursion, [and so on]. Errors are usually beyond the control of the programmer, and we should not try to handle errors" (GeeksforGeeks, 2023a).

Regardless of whether you are using an IDE or not, usually, the error in the code will be shown, and you will be able to identify what is wrong. Sometimes, it might just be a semicolon missing or another matter that is easily managed by the developer. To help you solve different exceptions, there are a few ways enabled by the language, such as applying the try-and-catch or using the finally statement. You will learn about both of these in this chapter.

## HANDLING EXCEPTIONS WITH TRY AND CATCH

Coding can be a complex process that might demand you create a way to handle an exception in case the request you are asking to be carried out generates an error. For example, if you are trying to divide a number by zero, it would lead to an error because this is not possible. Nevertheless, if you are creating a calculator, even if the operation is not allowed, you can still request it to be done.

For these cases, you will use the try-and-catch statements: The try statement will be used to tell the program what it is that you want to test, and the catch statement will define the block of code you want to execute. Both of these come in pairs, though you will always have one try statement but one or more catch blocks. This is the simplest way to handle an exception when coding in Java.

Here is an example of how a code would work when dividing by zero with the try-and-catch exception:

import java.util.Scanner;

public class ExceptionHandlingExample {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

try {

// Get input from the user

System.out.print("Enter a number: ");

int numerator = scanner.nextInt();

System.out.print("Enter another number: ");

int denominator = scanner.nextInt();

// Perform division

int result = divideNumbers(numerator, denominator);

// Display the result

System.out.println("Result: " + result);

} catch (ArithmeticException e) {

// Handle division by zero exception

System.out.println("Error: Division by zero is not allowed.");

} catch (Exception e) {

// Handle other exceptions

System.out.println("An error occurred: " + e.getMessage());

} finally {

// Close the scanner in the finally block to ensure it's always executed

scanner.close();

}

}

private static int divideNumbers(int numerator, int denominator) {

// Attempt to perform division

return numerator / denominator;

}

}

The output, in this case, would be the following:

Execution without the exception

Enter a number: 9

Enter another number: 3

Result: 3

Execution with the exception

Enter a number: 6

Enter another number: 0

Error: Division by zero is not allowed.

You might have noticed that in the code that was shown above, there was a keyword that we have not used yet: finally. In this case, finally is not necessary, but adding it will help you prevent more exceptions in your code. Additionally, you can use the try and finally statements together instead of catch, for example. But you might be wondering how the finally block works and when it should be applied. Let's move on to the next section and see how you can use it and the different application possibilities.

## THE FINALLY BLOCK

As you already know, the finally block can be used without the catch statement. This block should be used when you want the code to run, regardless of whether there is an exception or not. In an example similar to what we have seen before, the finally block will be used to close the scanner once the code has been run. The code for this example, so you can see its differences, is the following:

import java.util.Scanner;

public class ExceptionHandlingExample {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

try {

// Get input from the user

System.out.print("Enter a number: ");

int numerator = scanner.nextInt();

System.out.print("Enter another number: ");

int denominator = scanner.nextInt();

// Perform division

int result = divideNumbers(numerator, denominator);

// Display the result

System.out.println("Result: " + result);

} catch (ArithmeticException e) {

// Handle division by zero exception

System.out.println("Error: Division by zero is not allowed.");

} catch (Exception e) {

// Handle other exceptions

System.out.println("An error occurred: " + e.getMessage());

} finally {

// Close the scanner in the finally block to ensure it's always executed

scanner.close();

System.out.println("Scanner closed in the finally block.");

}

}

private static int divideNumbers(int numerator, int denominator) {

// Attempt to perform division

return numerator / denominator;

}

}

Output:

Enter a number: 6

Enter another number: 0

Error: Division by zero is not allowed.

Scanner closed in the finally block.

In this example, the finally block is added at the end, and it closes the scanner and prints a message indicating that the scanner is closed. The code inside the finally block is guaranteed to execute, regardless of whether an exception occurs in the try block or not.

As you might imagine, the finally block is not only good for handling exceptions but also for helping you clean up the program. For example, if you were to mistype a character after a curly bracket or use a character that is not allowed, your code would run anyway, making it efficient to clean up the code. The Java official documentation even mentions that "it allows the programmer to avoid having cleanup code accidentally bypassed by a return, continue, or break. Putting cleanup code in a finally block is always a good practice, even when no exceptions are anticipated" (The Finally Block, n.d.).

## THROWING EXCEPTIONS

"All methods use the throw statement to throw an exception. The throw statement requires a single argument: a throwable object. Throwable objects are instances of any subclass of the Throwable class" (How to Throw Exceptions, n.d.). The Throwable class can be used both for errors and exceptions, although for errors, they might not be of use. However, when you have an exception class, it will catch the objects or methods that have an error, and they will indicate the different errors that can happen in the code.

Some of these include the IllegalAccessException, which means a method was not found or does not exist, and the RuntimeException, when there is a problem running the code. There is also the NullPointerException, which will happen when the method tries to access an object through the null exception and the NegativeArraySizeException, which shows that the program tried to create an array with a negative size, which is not possible in Java. When you apply exceptions to your code, it will make it easier to catch errors and debug the program, which we will talk more about in the last chapter of this book.

The last thing you should know, before we run the code, is that two different types of exceptions can be thrown: those for compile exceptions (checked) and others for run-time exceptions (unchecked). The main difference between the checked and the unchecked exceptions is that while the compiler will need to be caught and handled by the code during compilation by using the try-and-catch statements, the run-time exceptions will happen when the code is executing. While the first usually happens when there is a missing file or a network problem, the second will occur when bad coding practices are used (How to Throw Exceptions in Java, 2019).

Here is an example where the exception would be thrown for a system that requests the input of the user age:

import java.util.Scanner;

public class ExceptionThrowingExample {

public static void main(String[] args) {

Scanner scanner = new Scanner(System.in);

try {

// Get input from the user

System.out.print("Enter your age: ");

int age = scanner.nextInt();

// Check if age is negative

if (age < 0) {

// Throw an exception if age is negative

throw new IllegalArgumentException("Age cannot be negative");

}

// Display the age

System.out.println("Your age is: " + age);

} catch (IllegalArgumentException e) {

// Handle the thrown exception

System.out.println("Error: " + e.getMessage());

} catch (Exception e) {

// Handle other exceptions

System.out.println("An error occurred: " + e.getMessage());

} finally {

// Close the scanner in the finally block to ensure it's always executed

scanner.close();

System.out.println("Scanner closed in the finally block.");

}

}

}

Here is an example of what would be one possible input and output:

Enter your age: -12

Error: Age cannot be negative

Scanner closed in the finally block.

In this example, the user is entering a negative age, so the code throws a custom exception (IllegalArgumentException) with a directed error message. Here, we also used the catch block to handle this exception and print an error message. Lastly, the finally block ensures that the scanner is always closed, even if an exception occurs.

While built-in exceptions are incredibly useful, many developers prefer creating their own exceptions when creating their systems. This is because they will be able to tailor the exception exactly to the system's needs and the different situations that might be presented. In the last section of this chapter, we will look at what custom exceptions are and how they can be created.

## CREATING CUSTOM EXCEPTIONS

Custom exceptions are created when you extend from the exception class. As you will see in the code below, you will declare the exception class with the name you have according to the specific business need or even that you want to handle, but you will need to extend it from the superclass Exception. When you do this, there are a few rules that you must remember:

1.  Only create exceptions that will be useful and have a purpose. Since most of the exception classes in Java cover the developer's needs, creating an exception needs to fulfill the specific need of the business you are working for, or else there will be no benefit to obtain from it.

2.  When you create an exception, you should document it to explain what you want it to do. Only by doing this will others understand why you created it and the reason it should be used.

3.  Comment on the code if necessary to explain your reasoning. You will need to provide information for the exception you are creating and set the cause and detailed information on the exception you are looking to handle.

4.  Apply the Java convention to the exception. This means using camel case to name the class you are creating and add the word "exception" at the end.

With this in mind, let's take a look at a custom-made (or user-made) exception and how it can be applied.

// Custom exception class

class NegativeAgeException extends Exception {

public NegativeAgeException(String message) {

super(message);

}

}

public class CustomExceptionExample {

// Method that throws a custom exception

public static void validateAge(int age) throws NegativeAgeException {

if (age < 0) {

// Throw the custom exception if age is negative

throw new NegativeAgeException("Age cannot be negative");

}

// Process other logic if age is valid

System.out.println("Valid age: " + age);

}

public static void main(String[] args) {

try {

// Call the method that may throw the custom exception

validateAge(-5);

} catch (NegativeAgeException e) {

// Handle the custom exception

System.out.println("Error: " + e.getMessage());

}

}

}

The output for this case would be: Error: Age cannot be negative. In this example, we created a custom exception class NegativeAgeException that extends the Exception class. The validateAge method throws this custom exception if the age is negative. Finally, to ensure that the exception is applied, we will catch and handle the NegativeAgeException if it occurs in the main method, making the process work and the program maintain its flow.

You will see that there are no exercises in this chapter. However, I do encourage you to look back at the previous exercises and try to create your own code to see the output and whether any errors are identified. When you add these exceptions, you will see that you have a code with more quality and that errors will significantly decrease. Once again, I state that practice makes perfect, and you should certainly put into action what you have seen up to now with exception handling before we move on to more advanced techniques.

If you feel you are ready and have understood the concept and power of exception handling, you are ready to dive deeper into the advanced aspects of Java and upskill your knowledge. In the next chapter, we'll explore file I/O and serialization, broadening your Java programming skills even further. If you are ready to learn how to read, write, delete, and modify files using Java, read on to see all the different possibilities of what it can do for you!

CHAPTER 8

FILE INPUT AND OUTPUT

Sometimes, we need to create programs that interact with elements not native to the system. Suppose that you are developing software that will upload and analyze a file and bring you back a result; for this purpose, you will need to know how to input and output files to ensure the process can be carried out. To see how useful this is, think about different modern software that you can upload a file to then read and modify the data. This is exactly what this technique does.

In this chapter, you will obtain a comprehensive understanding of File I/O in Java, which is the library that allows you to do this. As you will see, it will need to be imported along with other libraries to ensure that your code works. In addition to this, you will learn how to work with text and binary files, as well as the meaning and uses of serialization and deserialization. This is already the first step in your advanced Java knowledge. Are you ready to take one step further into the process?

## WORKING WITH FILES IN JAVA

As mentioned earlier, when you want to handle files in Java, you need to download the relevant package. There are many different options in the market, and it will be up to you to decide which you want to use. For this chapter, we will use the package "java.io," and will need the extensions File, FileWriter, FileReader, BufferedReader, and IOException. These will enable you to carry out some different actions with your Java program.

As usual, you will see that the code you will learn from is commented on at each step, to ease understanding. There will be guided steps for you to carry out all the actions, and you know what? They are actually pretty easy. Let's take a look at the actions you need to carry out and what they do when considering file management.

//Import to create a new file or use directories using method from the package

import java.io.File;

//Import to write a file text or string in Java

import java.io.FileWriter;

//Import to read characters from a file

import java.io.FileReader;

//Import to read a text from the input

import java.io.BufferedReader;

//Import to handle IO exceptions, which occur while using files in Java.

import java.io.IOException;

public class FileIOExample {

public static void main(String[] args) {

// Specify the file path of the file you are going to create and the type

String filePath = "example.txt";

// Create a file

createFile(filePath);

// Write to the file

writeToFile(filePath, "Hello, this is a sample text!");

// Read from the file

readFromFile(filePath);

// Delete the file

deleteFile(filePath);

}

// Method to create a file

private static void createFile(String filePath) {

try {

File file = new File(filePath);

// Create a new file if it doesn't exist

if (file.createNewFile()) {

System.out.println("File created: " + file.getName());

} else {

System.out.println("File already exists.");

}

} catch (IOException e) {

System.out.println("An error occurred while creating the file.");

e.printStackTrace();

}

}

// Method to write to a file

private static void writeToFile(String filePath, String content) {

try (FileWriter writer = new FileWriter(filePath)) {

writer.write(content);

System.out.println("Content written to the file.");

} catch (IOException e) {

System.out.println("An error occurred while writing to the file.");

e.printStackTrace();

}

}

// Method to read from a file

private static void readFromFile(String filePath) {

try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {

String line;

System.out.println("Reading from the file:");

while ((line = reader.readLine()) != null) {

System.out.println(line);

}

} catch (IOException e) {

System.out.println("An error occurred while reading from the file.");

e.printStackTrace();

}

}

// Method to delete a file

private static void deleteFile(String filePath) {

File file = new File(filePath);

if (file.delete()) {

System.out.println("File deleted: " + file.getName());

} else {

System.out.println("Failed to delete the file.");

}

}

}

If you were to execute this code in your IDE with a file with the same name, you would see that the output would be the following:

File already exists.

Content written to the file.

Reading from the file:

Hello, this is a sample text!

File deleted: example.txt

As you might have noticed, we used different packages to use the read and write function to better understand them. Let's take a look at how they work for reading and writing files in Java and the different options you can use when you are working with files.

## READING AND WRITING TEXT FILES

As mentioned earlier, when you are looking to work with files in your Java program, there are different options you can choose from. In this section, we will look into a few of them and then see how they perform in the code. When working with different packages (especially the java.io), you have the option of adopting, among others, the following, according to Minh (2019):

*   FileWriter: This will enable the class to write single, array, and string of characters efficiently. It can be used to efficiently write files and encode what you want to add to the file.

*   FileReader: This will enable the program to read files, including single characters, character array, read while skipping certain characters, and closing the stream.

*   InputStreamReader: This converts bytes into characters according to the specific data type you are looking to use.

*   BufferedReader: This will put the content into a buffer so it can be efficiently read and streamed, granting the ability to read full lines of text.

*   BufferedWriter: Used to enable the character writing stream to be efficient when writing and enable the program to remember what you want it to do.

As you will see, from the java.io package, you are able to create different classes to code and determine what the code will do. If you are looking for more packages to download and their different functions, you can find them in the appendix of this book. In the meantime, let's look at another code example using these different packages.

import java.io.FileWriter;

import java.io.FileReader;

import java.io.BufferedReader;

import java.io.BufferedWriter;

import java.io.IOException;

public class TextFileReadWriteExample {

public static void main(String[] args) {

// Specify the file path

String filePath = "example.txt";

// Write to the file

writeToFile(filePath, "Hello, this is a sample text!");

// Read from the file

String content = readFromFile(filePath);

System.out.println("Read from the file:");

System.out.println("-------------------------------");

System.out.println(content);

System.out.println("-------------------------------");

}

// Method to write to a file

private static void writeToFile(String filePath, String content) {

try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath))) {

writer.write(content);

System.out.println("Content written to the file.");

} catch (IOException e) {

System.out.println("An error occurred while writing to the file.");

e.printStackTrace();

}

}

// Method to read from a file

private static String readFromFile(String filePath) {

StringBuilder content = new StringBuilder();

try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {

String line;

while ((line = reader.readLine()) != null) {

content.append(line);

}

} catch (IOException e) {

System.out.println("An error occurred while reading from the file.");

e.printStackTrace();

}

return content.toString();

}

}

When you run this code, the result will be the following output:

Content written to the file.

Read from the file:

-------------------------------

Hello, this is a sample text!

In this example, you have seen that the BufferedWriter and the BufferedReader classes are used in the code to write and read the code. The methods writeToFile and readFromFile were applied to enable this to happen. The name of the file was just a simulation, but you will be able to name it according to your preferences.

While these are useful ways to work with files and streamline processes, you might face a situation in which you will need to transform its contents into a byte stream. When this happens, you will need to apply serialization and deserialization techniques to ensure that the file can be read appropriately. This is also done to save memory from the program and make it work faster. To see how to carry out these techniques, in the next section, we will talk about them and when they can be applied to make the processing more efficient.

## SERIALIZATION AND DESERIALIZATION

Sometimes, the program we are creating needs to be sent to someone or be stored. When this happens, the developer needs to create alternatives to ensure the program is working efficiently and not much memory is used. This is where serialization comes in. It is used to transform an object's state into a byte stream, which makes it easier to be transferred. As you might imagine, when this happens, the file becomes unreadable, since it will be several "0"s and "1"s; therefore, it needs to be transformed back, or deserialized, which can also be done with the same package.

Many times, these files are transformed into JSON and XML data to make them easier to parse while still being understood by humans. In this case, the developer can choose between transforming into one of these two formats or to a byte stream to make the process more efficient. Since we are still talking about files, you need to use java.io, specifically java.io.Serializable. Here is an example of how this would be processed in a code:

import java.io.*;

import java.nio.*;

// A simple class to be serialized

class Person implements Serializable {

private static final long serialVersionUID = 1L;

private String name;

private int age;

public Person(String name, int age) {

this.name = name;

this.age = age;

}

@Override

public String toString() {

return "Person{" +

"name='" + name + '\'' +

", age=" + age +

'}';

}

}

public class SerializationExample {

public static void main(String[] args) {

// Create an instance of the Person class

Person person = new Person("John Doe", 30);

// Serialize the object to a file

serializeObject(person, "person.ser");

// Deserialize the object from the file

Person deserializedPerson = (Person) deserializeObject("person.ser");

// Display the deserialized object

System.out.println("Deserialized Person: " + deserializedPerson);

}

// Method to serialize an object to a file

private static void serializeObject(Object object, String filePath) {

try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(filePath))) {

oos.writeObject(object);

System.out.println("Object serialized to " + filePath);

} catch (IOException e) {

System.out.println("An error occurred during serialization.");

e.printStackTrace();

}

}

// Method to deserialize an object from a file

try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(filePath))) {

return ois.readObject();

} catch (IOException | ClassNotFoundException e) {

System.out.println("An error occurred during deserialization.");

e.printStackTrace();

return null;

}

}

}

The output in this case is

Object serialized to person.ser and

Deserialized Person: Person{name='John Doe', age=30}.

The example shows how a file was serialized and deserialized to ensure faster processing and data transference. Although this process requires some attention, since the transfer can lead to security issues especially if we are dealing with confidential data, you may also use encryption methods and password alternatives to protect the file. The different methods applied include the "ObjectInputStream ois" to read the object and the"ObjectOutputStream oos" to write the objects.

## WORKING WITH BINARY FILES

Working with binary files can be an extremely beneficial way to work with text in your computer in a way the machine understands that is easy to process. In this case, we will have the java.io package and also the java.nio, where nio stands for "new io." Since these files are smaller, they enable faster processing so that binary image and sound files can be used. In this case, the files you are dealing with might not only be text.

In this final section of the chapter, we will look into an example of how to work with binary files in both the .io and the .nio extensions. You will see that in the case of the latter, the code is significantly smaller and optimized—which is why many developers are migrating to it for their coding processes.

import java.io.*;

public class BinaryContentFileExample {

public static void main(String[] args) {

// Example binary content

byte[] binaryContent = {0x4A, 0x50, 0x47, 0x0D, 0x0A, 0x1A, 0x0A}; // Example JPEG file signature

String filePath = "binarycontentfile.jpg";

// Writing binary content to a file

writeBinaryContent(binaryContent, filePath);

// Reading binary content from a file

byte[] readBinaryContent = readBinaryContent(filePath);

// Display the read binary content

System.out.println("Read binary content: " + bytesToHex(readBinaryContent));

}

// Method to write binary content to a file

private static void writeBinaryContent(byte[] content, String filePath) {

try (FileOutputStream fos = new FileOutputStream(filePath)) {

fos.write(content);

System.out.println("Binary content written to file.");

} catch (IOException e) {

System.out.println("An error occurred while writing binary content to the file.");

e.printStackTrace();

}

}

// Method to read binary content from a file

private static byte[] readBinaryContent(String filePath) {

try (FileInputStream fis = new FileInputStream(filePath)) {

ByteArrayOutputStream buffer = new ByteArrayOutputStream();

int bytesRead;

byte[] data = new byte[1024];

while ((bytesRead = fis.read(data, 0, data.length)) != -1) {

buffer.write(data, 0, bytesRead);

}

return buffer.toByteArray();

} catch (IOException e) {

System.out.println("An error occurred while reading binary content from the file.");

e.printStackTrace();

return null;

}

}

// Helper method to convert bytes to hexadecimal string

private static String bytesToHex(byte[] bytes) {

StringBuilder hexStringBuilder = new StringBuilder();

for (byte b : bytes) {

hexStringBuilder.append(String.format("%02X ", b));

}

return hexStringBuilder.toString().trim();

}

}

In the example you have just seen, we are representing the binary content of a JPEG file (an image) that has been named binarycontentfile.jpg. In this case, we are both serializing and deserializing the content back to make it readable. We have invoked the bytesToBytes method to display the content in binary in the hexadecimal format. However, this does not apply to all images. It will depend on the files you are working with and the objective you are trying to achieve.

NIO

import java.io.IOException;

import java.nio.file.*;

public class BinaryFileNIOExample {

public static void main(String[] args) {

// Example data

byte[] dataToWrite = {0x48, 0x65, 0x6C, 0x6C, 0x6F}; // Hexadecimal representation of "Hello"

Path filePath = Paths.get("binaryfile_nio.bin");

// Writing to a binary file using NIO

writeBinaryFileNIO(dataToWrite, filePath);

// Reading from a binary file using NIO

byte[] readData = readBinaryFileNIO(filePath);

// Display the read data

System.out.print("Read data: ");

for (byte b : readData) {

System.out.print((char) b);

}

}

// Method to write data to a binary file using NIO

private static void writeBinaryFileNIO(byte[] data, Path filePath) {

try {

Files.write(filePath, data, StandardOpenOption.CREATE, StandardOpenOption.WRITE);

System.out.println("Data written to binary file using NIO.");

} catch (IOException e) {

System.out.println("An error occurred while writing to the binary file using NIO.");

e.printStackTrace();

}

}

// Method to read data from a binary file using NIO

private static byte[] readBinaryFileNIO(Path filePath) {

try {

return Files.readAllBytes(filePath);

} catch (IOException e) {

System.out.println("An error occurred while reading from the binary file using NIO.");

e.printStackTrace();

return null;

}

}

}

The output for this second code is

Data written to binary file using NIO.

Read data: Hello

In this example, you are using the File.write to write binary files and the Files.readAllBytes to read the content. In this example, as you can see, the NIO helps you by providing an efficient way to handle these binary files. The end answer will usually be the same as if using the java.io, but you will see that the java.nio provides better tools and a more versatile environment for dealing with bytes.

You now have the necessary knowledge to start reading, writing, and working with files in your Java program. This will help you create more complex programs and work with different files. In the exercise you are about to see, you will need to put all the knowledge you have obtained into action. Are you ready to try working with your own files in Java?

## YOUR TURN TO TRY!

In the exercise for this section, you will need to create programs that perform basic file operations. You will need to create I/O and NIO programs to carry out the ncessary actions. As usual, the answer to the exercise is available at the end of the book.

Task 1: Basic File Operations

1.  Create a file: Write a Java program to create a new text file named "file_io_challenge.txt."

2.  Write to the file: Add the text "Hello, File I/O Challenge!" to the file.

3.  Read from the file: Read the content from the file and print it to the console.

4.  Delete the file: Delete the file you created.

Task 2: Object Serialization

1.  Create an object: Design a simple Java class (such as "Student" with fields like name, age, and grade).

2.  Serialize object: Write code to serialize an instance of the class and save it to a file named "serialized_object.da".

3.  Deserialize object: Read from the serialized file and deserialize the object.

4.  Display object data: Print the details of the deserialized object.

Bonus: Combine Both Tasks

1.  Write multiple objects: Extend the object serialization task to write multiple instances of the class to the same file.

2.  Read and display all objects: Modify the deserialization code to read all objects from the file and display their details.

With this newfound knowledge of File I/O and object serialization, you are ready to take on even more sophisticated tasks in Java programming. In the next chapter, we'll venture into one of the most flexible and used functions of Java: application programming interfaces (APIs)! You will see that despite having all the building blocks and information on the language, the API will help you speed up the development process, especially for specific tasks carried out by developers. Shall we continue?

CHAPTER 9

INTRODUCTION TO JAVA APIS

Adeveloper must know the basic components of the code, but there is one thing they must learn to make their process more efficient: APIs, which are a part of the JDK and are preintegrated Java package components that will help establish the communication between the program and software platforms and components. In this chapter, we will focus on understanding and working with Java APIs, including the String, Date and Time, Math and Random APIs, and the Java Collections Framework.

## OVERVIEW OF JAVA APIS

An API facilitates code since it already comes with the classes, interfaces, and user interfaces the developer will need for a certain purpose. As you will see in this section, there are different APIs the developer can use according to their specific needs. In addition, they can use APIs to integrate applications and developed software with websites, apps, and even the possibility to use real-time information. These are usually third-party services that can help turn complex problems into simple code lines and build programs that make the developer's life easier.

When talking about APIs, the most commonly used architecture style is the REST API, together with the Web API, JAX-RS, Facebook.4J, and Twitter.4J. These APIs can be private, designed by a company for a specific purpose; public, free to access and use; composite, developed by aggregating different APIs; partner, offered by companies to other businesses; and the Web Java API, accessed by the internet for browser-based applications (Java API, 2023). Since explaining the different Java APIs would require almost a full new book, in this section, we will see some APIs that perform different functions. You will see they provide an efficient and straightforward way to code with an all-in-one approach.

## WORKING WITH THE STRING API

As you have learned, strings in Java are not mutable; therefore, every time you need to change or manage it, a new string will be created. When you have the StringApi, you will be able to work with the string you created, including determining its length, concatenating, and other actions you might need. In the example we are about to see, we are going to use the "Hello, World!" string and see the different actions that can be carried out.

import java.util.Arrays;

public class StringApiExample {

public static void main(String[] args) {

// Creating a String

String str1 = "Hello, World!";

// 1\. length(): Returns the length of the string.

int length = str1.length();

System.out.println("1\. Length: " + length);

// 2\. charAt(int index): Returns the character at the specified index.

char charAtIndex = str1.charAt(7);

System.out.println("2\. Character at index 7: " + charAtIndex);

// 3\. substring(int beginIndex): Returns a substring from the specified index to the end.

String substring1 = str1.substring(7);

System.out.println("3\. Substring from index 7: " + substring1);

// 4\. substring(int beginIndex, int endIndex): Returns a substring within the specified range.

String substring2 = str1.substring(7, 12);

System.out.println("4\. Substring from index 7 to 12: " + substring2);

// 5\. concat(String str): Concatenates the specified string to the end.

String concatenated = str1.concat(" Welcome!");

System.out.println("5\. Concatenated String: " + concatenated);

// 6\. equals(Object obj): Compares the string with the specified object.

boolean isEqual = str1.equals("Hello, World!");

System.out.println("6\. String is equal to 'Hello, World!': " + isEqual);

// 7\. equalsIgnoreCase(String anotherString): Case-insensitive comparison.

boolean isEqualIgnoreCase = str1.equalsIgnoreCase("hello, world!");

System.out.println("7\. String is equal to 'hello, world!' (ignore case): " + isEqualIgnoreCase);

// 8\. indexOf(String str): Returns the index of the first occurrence of the specified substring.

int indexOfSubstring = str1.indexOf("World");

System.out.println("8\. Index of 'World': " + indexOfSubstring);

// 9\. toLowerCase(): Converts the string to lowercase.

String lowercase = str1.toLowerCase();

System.out.println("9\. Lowercase String: " + lowercase);

// 10\. toUpperCase(): Converts the string to uppercase.

String uppercase = str1.toUpperCase();

System.out.println("10\. Uppercase String: " + uppercase);

// 11\. trim(): Removes leading and trailing whitespaces.

String stringWithSpaces = " Hello, World! ";

String trimmed = stringWithSpaces.trim();

System.out.println("11\. Trimmed String: '" + trimmed + "'");

// 12\. startsWith(String prefix): Checks if the string starts with the specified prefix.

boolean startsWithHello = str1.startsWith("Hello");

System.out.println("12\. String starts with 'Hello': " + startsWithHello);

// 13\. endsWith(String suffix): Checks if the string ends with the specified suffix.

boolean endsWithWorld = str1.endsWith("World!");

System.out.println("13\. String ends with 'World!': " + endsWithWorld);

// 14\. contains(CharSequence sequence): Checks if the string contains the specified sequence.

boolean containsHello = str1.contains("Hello");

System.out.println("14\. String contains 'Hello': " + containsHello);

// 15\. replace(char oldChar, char newChar): Replaces occurrences of a character.

String replacedString = str1.replace('o', 'X');

System.out.println("15\. Replaced 'o' with 'X': " + replacedString);

// 16\. replace(CharSequence target, CharSequence replacement): Replaces occurrences of a sequence.

String replacedSubstring = str1.replace("World", "Universe");

System.out.println("16\. Replaced 'World' with 'Universe': " + replacedSubstring);

// 17\. split(String regex): Splits the string based on a regular expression.

String[] splitArray = str1.split(",");

System.out.println("17\. Splitted String: " + Arrays.toString(splitArray));

// 18\. isEmpty(): Checks if the string is empty.

boolean isEmpty = str1.isEmpty();

System.out.println("18\. Is String empty: " + isEmpty);

// 19\. compareTo(String anotherString): Compares two strings lexicographically.

int compareToResult = str1.compareTo("Hello, Java!");

System.out.println("19\. Compare To 'Hello, Java!': " + compareToResult);

// 20\. format(String format, Object... args): Formats the string using specified format and arguments.

String formattedString = String.format("Formatted String: %s, %d", "Hello", 2023);

System.out.println("20\. Formatted String: " + formattedString);

}

}

Output:

1\. Length: 13

2\. Character at index 7: W

3\. Substring from index 7: World!

4\. Substring from index 7 to 12: World

5\. Concatenated String: Hello, World! Welcome!

6\. String is equal to 'Hello, World!': true

7\. String is equal to 'hello, world!' (ignore case): true

8\. Index of 'World': 7

9\. Lowercase String: hello, world!

10\. Uppercase String: HELLO, WORLD!

11\. Trimmed String: 'Hello, World!'

12\. String starts with 'Hello': true

13\. String ends with 'World!': true

14\. String contains 'Hello': true

15\. Replaced 'o' with 'X': HellX, WXrld!

16\. Replaced 'World' with 'Universe': Hello, Universe!

17\. Splitted String: [Hello, World!]

18\. Is String empty: false

19\. Compare To 'Hello, Java!': 13

20\. Formatted String: Formatted String: Hello, 2023

## MANIPULATING DATES AND TIMES WITH THE DATE AND TIME API

In the same way as there is an API to manage strings, there is also a specific API to use and manage code that deals with date and time. In the below example, you will see that there are different packages for Date, Time, and Date and Time, which you will need to download to work with code with these characteristics. Similar to the previous example, the code you are about to see has comments explaining what each function is doing.

import java.time.LocalDate;

import java.time.LocalTime;

import java.time.LocalDateTime;

import java.time.format.DateTimeFormatter;

import java.time.temporal.ChronoUnit;

public class DateTimeExample {

public static void main(String[] args) {

// LocalDate: Represents a date (year, month, day)

LocalDate currentDate = LocalDate.now();

System.out.println("Current Date: " + currentDate);

// LocalTime: Represents a time (hour, minute, second)

LocalTime currentTime = LocalTime.now();

System.out.println("Current Time: " + currentTime);

// LocalDateTime: Represents both date and time

LocalDateTime currentDateTime = LocalDateTime.now();

System.out.println("Current Date and Time: " + currentDateTime);

// Formatting and parsing dates

DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");

String formattedDateTime = currentDateTime.format(formatter);

System.out.println("Formatted Date and Time: " + formattedDateTime);

LocalDateTime parsedDateTime = LocalDateTime.parse("2023-10-25 15:30:00", formatter);

System.out.println("Parsed Date and Time: " + parsedDateTime);

// Adding and subtracting time

LocalDateTime futureDateTime = currentDateTime.plus(1, ChronoUnit.HOURS);

System.out.println("Future Date and Time (+1 hour): " + futureDateTime);

LocalDateTime pastDateTime = currentDateTime.minus(2, ChronoUnit.DAYS);

System.out.println("Past Date and Time (-2 days): " + pastDateTime);

// Comparing dates

LocalDate date1 = LocalDate.of(2023, 10, 25);

LocalDate date2 = LocalDate.of(2023, 10, 27);

System.out.println("Is date1 before date2? " + date1.isBefore(date2));

System.out.println("Is date1 after date2? " + date1.isAfter(date2));

// Duration between two times

LocalTime startTime = LocalTime.of(10, 30);

LocalTime endTime = LocalTime.of(15, 45);

long hoursBetween = ChronoUnit.HOURS.between(startTime, endTime);

System.out.println("Hours between startTime and endTime: " + hoursBetween);

}

}

Output:

Current Date: 2023-11-13

Current Time: 12:07:43.309786

Current Date and Time: 2023-11-13T12:07:43.309949

Formatted Date and Time: 2023-11-13 12:07:43

Parsed Date and Time: 2023-10-25T15:30

Future Date and Time (+1 hour): 2023-11-13T13:07:43.309949

Past Date and Time (-2 days): 2023-11-11T12:07:43.309949

Is date1 before date2? True

Is date1 after date2? false

Hours between startTime and endTime: 5

## USING THE MATH RANDOM APIS

Just as there are different APIs for strings and date and time, in Java, there are several APIs that enable you to carry out mathematical functions. While each of them has its characteristics and capabilities, they will all help you with classes and methods to carry out calculations and other functions. In this section, we will look at how a Math and a Random API can work for their respective functions. Similar to what you have seen before, they will all have the explanation within the code lines to make understanding easier. Shall we take a look?

Math

import java.lang.Math;

public class MathExample {

public static void main(String[] args) {

// Basic arithmetic operations

double num1 = 10.5;

double num2 = 5.2;

double sum = Math.addExact((int) num1, (int) num2);

System.out.println("Sum: " + sum);

double difference = Math.subtractExact((int) num1, (int) num2);

System.out.println("Difference: " + difference);

double product = Math.multiplyExact((int) num1, (int) num2);

System.out.println("Product: " + product);

double quotient = Math.floorDiv((int) num1, (int) num2);

System.out.println("Quotient: " + quotient);

// Exponential and logarithmic functions

double base = 2.0;

double exponent = 3.0;

double power = Math.pow(base, exponent);

System.out.println("Power: " + power);

double squareRoot = Math.sqrt(num1);

System.out.println("Square Root: " + squareRoot);

double logarithm = Math.log(num1);

System.out.println("Natural Logarithm: " + logarithm);

// Trigonometric functions

double angleInRadians = Math.toRadians(45.0);

double sine = Math.sin(angleInRadians);

System.out.println("Sine: " + sine);

double cosine = Math.cos(angleInRadians);

System.out.println("Cosine: " + cosine);

double tangent = Math.tan(angleInRadians);

System.out.println("Tangent: " + tangent);

// Rounding and absolute value

double numberToRound = 15.75;

long roundedNumber = Math.round(numberToRound);

System.out.println("Rounded Number: " + roundedNumber);

double absoluteValue = Math.abs(-25.8);

System.out.println("Absolute Value: " + absoluteValue);

}

}

Outputs:

Sum: 15.0

Difference: 5.0

Product: 50.0

Quotient: 2.0

Power: 8.0

Square Root: 3.24037034920393

Natural Logarithm: 2.3513752571634776

Sine: 0.7071067811865475

Cosine: 0.7071067811865476

Tangent: 0.9999999999999999

Rounded Number: 16

Absolute Value: 25.8

Random

import java.util.Random;

public class RandomExample {

public static void main(String[] args) {

// Creating a Random object

Random random = new Random();

// Generating random integers

int randomInt = random.nextInt(); // Generates a random integer

System.out.println("Random Integer: " + randomInt);

// Generating random integers within a specific range

int minRange = 5;

int maxRange = 15;

int randomIntInRange = random.nextInt(maxRange - minRange + 1) + minRange;

System.out.println("Random Integer in Range: " + randomIntInRange);

// Generating random doubles between 0.0 and 1.0

double randomDouble = random.nextDouble();

System.out.println("Random Double: " + randomDouble);

// Generating random booleans

boolean randomBoolean = random.nextBoolean();

System.out.println("Random Boolean: " + randomBoolean);

// Generating random Gaussian-distributed values

double randomGaussian = random.nextGaussian();

System.out.println("Random Gaussian: " + randomGaussian);

// Shuffling an array

int[] arrayToShuffle = {1, 2, 3, 4, 5};

for (int i : random.ints(0, arrayToShuffle.length).distinct().limit(arrayToShuffle.length).toArray()) {

System.out.print(arrayToShuffle[i] + " ");

}

System.out.println();

// Picking a random element from an array

int[] arrayToPickFrom = {10, 20, 30, 40, 50};

int randomElement = arrayToPickFrom[random.nextInt(arrayToPickFrom.length)];

System.out.println("Randomly Picked Element: " + randomElement);

}

}

Output (random):

Random Integer: 1476683965

Random Integer in Range: 10

Random Double: 0.34985790961508445

Random Boolean: false

Random Gaussian: 0.6210980737587507

2 3 5 1 4

Randomly Picked Element: 40

As you have seen, APIs are a great way to make your coding faster and more efficient, and they work similarly to a Java collection. To recap the concept of Java framework collections and how they can be used in your code, read on to the final section of this chapter. You will see how the collection can be used to represent a large group of objects and help you independently manage them while coding.

## INTRODUCTION TO JAVA COLLECTIONS FRAMEWORK

"The Java collections framework provides a set of interfaces and classes to implement various data structures and algorithms" (Java Collections Framework, n.d.). You have already seen the LinkedList examples and the ArrayList, but there are several other interfaces that can be used. In this section, you will see the use of the subinterfaces of sets, lists, and queues in collections and their applications in the code. The main advantages these collections will provide are more organized and efficient code and less need for coding lines. Read on to learn more about them!

import java.util.*;

public class CollectionsExample {

public static void main(String[] args) {

// List Interface (ArrayList)

List<String> list = new ArrayList<>();

list.add("Java");

list.add("Python");

list.add("C++");

// Five most used methods for List

System.out.println("List Methods:");

System.out.println("1\. Elements: " + list);

System.out.println("2\. Size: " + list.size());

System.out.println("3\. Get element at index 1: " + list.get(1));

list.remove("Python");

System.out.println("4\. After removing 'Python': " + list);

list.add(1, "JavaScript");

System.out.println("5\. After adding 'JavaScript' at index 1: " + list);

System.out.println();

// Set Interface (HashSet)

Set<Integer> set = new HashSet<>();

set.add(10);

set.add(20);

set.add(30);

// Five most used methods for Set

System.out.println("Set Methods:");

System.out.println("1\. Elements: " + set);

System.out.println("2\. Size: " + set.size());

System.out.println("3\. Contains 20? " + set.contains(20));

set.remove(10);

System.out.println("4\. After removing 10: " + set);

set.add(40);

System.out.println("5\. After adding 40: " + set);

System.out.println();

// Map Interface (HashMap)

Map<String, Integer> map = new HashMap<>();

map.put("One", 1);

map.put("Two", 2);

map.put("Three", 3);

// Five most used methods for Map

System.out.println("Map Methods:");

System.out.println("1\. Entries: " + map);

System.out.println("2\. Size: " + map.size());

System.out.println("3\. Value for key 'Two': " + map.get("Two"));

map.remove("Three");

System.out.println("4\. After removing key 'Three': " + map);

map.put("Four", 4);

System.out.println("5\. After adding key 'Four': " + map);

System.out.println();

// Queue Interface (PriorityQueue)

Queue<String> queue = new PriorityQueue<>();

queue.add("Apple");

queue.add("Banana");

queue.add("Orange");

// Five most used methods for Queue

System.out.println("Queue Methods:");

System.out.println("1\. Elements: " + queue);

System.out.println("2\. Size: " + queue.size());

System.out.println("3\. Peek: " + queue.peek());

queue.poll();

System.out.println("4\. After polling: " + queue);

queue.add("Grapes");

System.out.println("5\. After adding 'Grapes': " + queue);

System.out.println();

// Iterator for List

Iterator<String> listIterator = list.iterator();

System.out.println("Iterator Methods:");

while (listIterator.hasNext()) {

System.out.print(listIterator.next() + " ");

}

}

}

Output:

List Methods:

1.  Elements: [Java, Python, C++]

2.  Size: 3

3.  Get element at index 1: Python

4.  After removing 'Python': [Java, C++]

5.  After adding 'JavaScript' at index 1: [Java, JavaScript, C++]

Set Methods:

1.  Elements: [20, 10, 30]

2.  Size: 3

3.  Contains 20? true

4.  After removing 10: [20, 30]

5.  After adding 40: [20, 40, 30]

Map Methods:

1.  Entries: {One=1, Two=2, Three=3}

2.  Size: 3

3.  Value for key 'Two': 2

4.  After removing key 'Three': {One=1, Two=2}

5.  After adding key 'Four': {One=1, Four=4, Two=2}

Queue Methods:

1.  Elements: [Apple, Banana, Orange]

2.  Size: 3

3.  Peek: Apple

4.  After polling: [Banana, Orange]

5.  After adding 'Grapes': [Banana, Orange, Grapes]

Iterator Methods:

Java JavaScript C++

As you have seen, sometimes, to write your code in Java, you do not need to write several lines of code. With APIs and collections, it is possible to streamline the coding process and optimize the use for the program you are developing. As you will see in the appendix of this book, there are several different APIs and collections you can use, and most of them can be found in GitHub, a repository for all different types of code made available by developers. As usual, we will now jump into testing your knowledge about what you have learned in this section. Are you prepared?

## LET'S TEST YOUR KNOWLEDGE!

1\. Which method of the "String" class is used to concatenate two strings in Java?

a. concat()

b. append()

c. merge()

d. combine()

e. join()

2\. How can you obtain the length (number of characters) of a string in Java?

a. size()

b. length()

c. count()

d. getSize()

e. charCount()

3\. What class is used to represent dates and times in the Date and Time API?

a. DateTime

b. Timestamp

c. Date

d. Calendar

e. TimeUnit

4\. Which method of the "Math" class is used to calculate the absolute value of a number?

a. abs()

b. absolute()

c. value()

d. getAbsolute()

e. absoluteValue()

5\. How do you generate a random integer in Java using the "Random" class?

a. rand()

b. nextInt()

c. randomInt()

d. generateInt()

e. nextRandomInt()

6\. Which interface in the Java Collections Framework extends the "Collection" interface and represents a collection that does not allow duplicate elements?

a. Set

b. List

c. Map

d. CollectionSet

e. HashSet

7\. What method is used to add an element to a list in the "List" interface?

a. add()

b. insert()

c. put()

d. addElement()

e. append()

8\. In Java, what statement is used to create a map in the "Map" interface?

a. Map<String, Integer> myMap = new HashMap<>();

b. HashMap<String, Integer> myMap = new Map<>();

c. Map<String, Integer> myMap = new TreeMap<>();

d. HashMap<String, Integer> myMap = new HashMap<>();

e. TreeMap<String, Integer> myMap = new TreeMap<>();

9\. What is the main difference between "ArrayList" and "LinkedList" in the Java Collections Framework data structure?

a. ArrayList allows random access, while LinkedList is more     efficient for insertions and removals

b. LinkedList allows random access, while ArrayList is more     efficient for insertions and removals

c. Both are identical in terms of performance

d. ArrayList is suitable only for small collections, while     LinkedList is better for large dataset

e. There is no significant difference between them

10\. Which class implements the "Deque" interface in the Java Collections Framework?

a. ArrayList

b. LinkedList

c. ArrayDeque

d. HashSet

e. TreeSet

So, how were you? The answers, as usual, are available at the end of the book. Before moving forward, I encourage you to search for other APIs and see how they can help you streamline your coding process. These are the building blocks that empower you to create sophisticated applications with ease. In the next chapter, we'll delve deeper into the world of Java graphic interfaces, allowing you to create images with your program—you will even have the chance to create your own. Are you ready?

CHAPTER 10

INTRODUCTION TO GRAPHICAL USER INTERFACE PROGRAMMING

Before we had fancy images and interfaces in computers, they would only have two colors and show numbers and specific forms. There were no different and friendly graphics until the introduction of GUI, which changed the way we use and consume technology. In Java, it is possible to create these different interfaces by using frameworks and components developed for this purpose.

In this chapter, you will be introduced to the concept of GUIs in Java, and the Swing Framework and its components. You will learn how to create GUI applications, find out about event handling, and be given a brief introduction to JavaFX. While we only have a chapter to talk about these topics (there are full books on each subject!) you will be able to grasp the main concepts and start developing your own applications with GUIs.

## INTRODUCTION TO GUI

Programs that have displays for easier user interaction generally implement a GUI . This means they have buttons, frames, windows, labels, and different graphic items to help you use the program better. If you are learning to develop in Java, it is important to know this is possible by applying code to your program. These GUIs will help the user understand what needs to be done and how to carry out the actions in the program.

To name a simple example, think about a calculator. When we open one on our computer, we see an image similar to a real-life one, which makes it easier to carry out calculations. You will see the number buttons, screen, operator signals, and much more. This is a prime example of how a GUI is used in a simple manner, that can also be expanded to other applications.

## SWING FRAMEWORK AND COMPONENTS

One of the most popular GUI implementation frameworks in Java is the javax.swing package, which provides the developer with the necessary tools to create the "art" to be used in a program. Although you could also use the java.awt package, it is preferable to use swing since it has almost four times as many user interfaces when compared to awt, which is considered presently to be limited. Swing is known to be a set of different APIs that will help you develop applications with a light structure that use less memory (Khurpaderushi143, 2023).

In the following example, you will see how you can use java.swing to create a simple button application before we look into more complex functions. As you will see, most of the classes, objects, and methods will start with an uppercase "J," which characterizes the use of GUIs in the Swing collection. Note that this example cannot be used in the online IDE since it does not come embedded with the GUI interface. To test what you are doing, use an IDE such as Eclipse.

import javax.swing.*;

import java.awt.event.ActionEvent;

import java.awt.event.ActionListener;

public class SwingExample {

public static void main(String[] args) {

// Create JFrame

JFrame frame = new JFrame("Swing Example");

frame.setSize(300, 200);

frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

// Create JButton

JButton button = new JButton("Click Me!");

// Create JLabel

JLabel label = new JLabel("Hello, Swing!");

// Add ActionListener to the button

button.addActionListener(new ActionListener() {

@Override

public void actionPerformed(ActionEvent e) {

label.setText("Button Clicked!");

}

});

// Set layout manager (FlowLayout by default)

frame.setLayout(new java.awt.FlowLayout());

// Add components to the frame

frame.add(button);

frame.add(label);

// Set frame visibility

frame.setVisible(true);

}

}

The output of this code example would be the following:

![](image_rsrc4ZV.jpg)

As you can see, we have created a button with a name and a specific label, frame, and button to click. If you think about this application, you will see that creating a user interface for your program is rather simple. For this reason, in the next section, we will explore how you can create the previously mentioned example: a calculator. Let's look into how this GUI application can be used and what would be needed to code in Java.

## CREATING GUI APPLICATIONS

If we were to create a simple calculator, this is what the code would look like:

import javax.swing.*;

import java.awt.*;

import java.awt.event.ActionEvent;

import java.awt.event.ActionListener;

public class SimpleCalculator {

public static void main(String[] args) {

// Create JFrame

JFrame frame = new JFrame("Simple Calculator");

frame.setSize(300, 400);

frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

// Create JTextArea for display

JTextArea display = new JTextArea();

display.setEditable(false);

// Create number buttons

JButton[] numberButtons = new JButton[10];

for (int i = 0; i < 10; i++) {

numberButtons[i] = new JButton(String.valueOf(i));

}

// Create operation buttons

JButton addButton = new JButton("+");

JButton subtractButton = new JButton("-");

JButton multiplyButton = new JButton("*");

JButton divideButton = new JButton("/");

JButton equalsButton = new JButton("=");

// Set layout manager (GridLayout for simplicity)

frame.setLayout(new GridLayout(5, 4));

// Add components to the frame

frame.add(display);

for (int i = 1; i < 10; i++) {

frame.add(numberButtons[i]);

}

frame.add(addButton);

frame.add(numberButtons[0]);

frame.add(subtractButton);

frame.add(multiplyButton);

frame.add(numberButtons[0]);

frame.add(divideButton);

frame.add(equalsButton);

// Add ActionListener to number buttons

for (JButton button : numberButtons) {

button.addActionListener(new ActionListener() {

@Override

public void actionPerformed(ActionEvent e) {

display.append(button.getText());

}

});

}

// Add ActionListener to operation buttons

addButton.addActionListener(new OperationActionListener(display, "+"));

subtractButton.addActionListener(new OperationActionListener(display, "-"));

multiplyButton.addActionListener(new OperationActionListener(display, "*"));

divideButton.addActionListener(new OperationActionListener(display, "/"));

// Handle equals button

equalsButton.addActionListener(new ActionListener() {

@Override

public void actionPerformed(ActionEvent e) {

calculate(display);

}

});

// Set frame visibility

frame.setVisible(true);

}

// ActionListener for operation buttons

static class OperationActionListener implements ActionListener {

private final JTextArea display;

private final String operation;

public OperationActionListener(JTextArea display, String operation) {

this.display = display;

this.operation = operation;

}

@Override

public void actionPerformed(ActionEvent e) {

display.append(" " + operation + " ");

}

}

// Calculate result

private static void calculate(JTextArea display) {

String expression = display.getText();

String[] operands = expression.split("\\s+");

if (operands.length != 3) {

JOptionPane.showMessageDialog(null, "Invalid expression!", "Error", JOptionPane.ERROR_MESSAGE);

return;

}

try {

double num1 = Double.parseDouble(operands[0]);

double num2 = Double.parseDouble(operands[2]);

double result = 0;

switch (operands[1]) {

case "+":

result = num1 + num2;

break;

case "-":

result = num1 - num2;

break;

case "*":

result = num1 * num2;

break;

case "/":

if (num2 != 0) {

result = num1 / num2;

} else {

JOptionPane.showMessageDialog(null, "Cannot divide by zero!", "Error", JOptionPane.ERROR_MESSAGE);

return;

}

break;

default:

JOptionPane.showMessageDialog(null, "Invalid operation!", "Error", JOptionPane.ERROR_MESSAGE);

return;

}

display.setText(String.valueOf(result));

} catch (NumberFormatException ex) {

JOptionPane.showMessageDialog(null, "Invalid number format!", "Error", JOptionPane.ERROR_MESSAGE);

}

}

}

As you have seen, we have created buttons that are characteristic to a calculator, and programmed the code to carry out the mathematical operations of a calculator. While this is a simple calculator, you can use similar codes to create a graphic, financial, or scientific calculator. By using and implementing this technique, you will be one step closer to creating programs ready for the final user.

## EVENT HANDLING AND LISTENER INTERFACES

"Any program that uses GUI (graphical user interface) such as Java applications written for Windows, is event driven. Event describes the change in state of any object. Such as pressing a button, entering a character, clicking, etc." (Event Handling in Java GUI, n.d.). When we talk about event handling, we are referring to the event, which is a change in the state of an object, the event source, which is the object generating an event, and the listener, which is an object that will listen and be notified when an event occurs.

These events will be handled with the packages java.util, java.awt, and java.awt.event. To manage these events, the developer will need to implement the interface class and register with the listener. Specifically speaking, if an object in a GUI is generating an image and there is no listener, there will be no object to make this event happen; thus, their importance. When you carry out event handling, they will control how the events happen and what should happen after the event occurs. As you will see in the following example, these event classes and listener interfaces will be followed by the "event" and the "listener" keywords.

import javax.swing.*;

import java.awt.*;

import java.awt.event.ActionEvent;

import java.awt.event.ActionListener;

public class EventHandlingExample {

public static void main(String[] args) {

// Create JFrame

JFrame frame = new JFrame("Event Handling Example");

frame.setSize(300, 200);

frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

// Create JButton

JButton button = new JButton("Click Me");

// Add ActionListener to the button

button.addActionListener(new MyButtonListener());

// Set layout manager (FlowLayout for simplicity)

frame.setLayout(new FlowLayout());

// Add button to the frame

frame.add(button);

// Set frame visibility

frame.setVisible(true);

}

// Custom ActionListener implementation

static class MyButtonListener implements ActionListener {

@Override

public void actionPerformed(ActionEvent e) {

// Handle button click event

JOptionPane.showMessageDialog(null, "Button Clicked!", "Event Handling", JOptionPane.INFORMATION_MESSAGE);

}

}

}

## INTRODUCTION TO JAVAFX

While Java Swing is still one of the most used package libraries by developers, the new option of applying JavaFX to your code has been adopted in the market. These are more usually applied in modern GUI applications, especially those that can run on different OSs and in mobile and web applications. Its main purpose, when developed, was to replace Java Swing, because it is an open-source, collaborative application made together with different developers.

When you download this API, you will see that some more classes and functions can be implemented, especially as you read the product documentation. Since this is a feature just now being implemented, I will leave the website in case you want to explore a more modern, but not as used, version to apply GUI to your programs. The link to access this program is openjfx.io.

## YOUR TURN TO TRY!

In this exercise section, you will need to create your own GUI software. Although there are different ways to create it, at the end of the book, you will find an example to help you get inspired. I encourage you to create different GUI programs, like the calculator that we have seen, to practice what you have learned in this chapter. Once you are done, we will dive into more complex topics as we explore advanced Java concepts and get closer to becoming proficient Java programmers. We are going to look at an introduction to networking and how it can be a useful technique for more seasoned developers to create their programs.

CHAPTER 11

INTRODUCTION TO NETWORKING

When you are creating code in Java, you will likely need to program it into the network, since many programs are connected to servers and the internet. Network programming refers to the different tools you can apply by using APIs to manage and develop your programs, and how they relate to the network. Due to the importance of this versatile application, the main point of this chapter is to introduce network programming in Java, covering concepts such as URLs, sockets, creating client-server applications, and the basics of communicating over a network.

It is by network programming that companies as large as Meta and X (formerly Twitter) can manage all the different messages exchanged. In addition to this, Java network programming is what enables the program to connect to the internet and have, for example, your company software collect information in real-time or enable the corporate web page to process requests. If you are ready to learn the nuances of network programming and see how the Java code would work for both the client and the network, read on! This is an advanced Java topic that all developers should know.

## INTRODUCTION TO NETWORK PROGRAMMING

When software has network programming embedded in it, it is possible to connect the application with different computers all over the world (as long as they have access to the internet). Due to its robustness and versatility, Java is usually the language chosen by companies and developers to network computers and make different programs available. "One of the biggest secrets about Java is that it makes writing network programs easy. In fact, it is far easier to write network programs in Java than in almost any other language" (Harold, 2000).

For these types of coding, you will need to use the java.net package as well as the java.io. The first will be used for specific networking purposes and the second, as you have already seen in previous chapters, will be used for information input and output. Although this chapter will only cover a few basics of network programming, it will provide you with enough knowledge to help you expand on the matter if needed. To start, let's take a look at how a code would be written from both the server and the client side in Java.

Optional, server

import java.io.IOException;

import java.io.PrintWriter;

import java.net.ServerSocket;

import java.net.Socket;

import java.util.Scanner;

public class SimpleServer {

public static void main(String[] args) {

final int PORT = 12345;

try {

// Create a server socket

ServerSocket serverSocket = new ServerSocket(PORT);

System.out.println("Server is listening on port " + PORT);

// Wait for a client to connect

Socket clientSocket = serverSocket.accept();

System.out.println("Client connected");

// Set up input and output streams

Scanner clientInput = new Scanner(clientSocket.getInputStream());

PrintWriter serverOutput = new PrintWriter(clientSocket.getOutputStream(), true);

// Read and print messages from the client

while (true) {

String clientMessage = clientInput.nextLine();

System.out.println("Client: " + clientMessage);

// Send a response back to the client

serverOutput.println("Server received: " + clientMessage);

}

} catch (IOException e) {

e.printStackTrace();

}

}

}

Client

import java.io.IOException;

import java.io.PrintWriter;

import java.net.Socket;

import java.util.Scanner;

public class SimpleClient {

public static void main(String[] args) {

final String SERVER_IP = "127.0.0.1";

final int SERVER_PORT = 12345;

try {

// Connect to the server

Socket socket = new Socket(SERVER_IP, SERVER_PORT);

System.out.println("Connected to server");

// Set up input and output streams

Scanner userInput = new Scanner(System.in);

Scanner serverInput = new Scanner(socket.getInputStream());

PrintWriter clientOutput = new PrintWriter(socket.getOutputStream(), true);

// Read and send messages to the server

while (true) {

System.out.print("Enter a message for the server: ");

String message = userInput.nextLine();

// Send the message to the server

clientOutput.println(message);

// Receive and print the server's response

String serverResponse = serverInput.nextLine();

System.out.println("Server: " + serverResponse);

}

} catch (IOException e) {

e.printStackTrace();

}

}

}

While reading this exercise, if you are not familiar with networking jargon and terms, you might likely have felt lost. This is completely understandable, especially if this is the first time you are dealing with the matter. For this reason, in the next section, we will learn a little more about working with URLs and sockets, as well as what these are and their importance in network programming. Are you ready to see your universe expand and take your program global?

## WORKING WITH URLS AND SOCKETS

Two important concepts you must understand to program networks in Java are URLs and sockets. URL stands for Uniform Resource Locator, which is nothing more than the internet address to a certain location, and sockets are one of the endpoints in a two-way communication. These sockets have a number called the TCP (transmission control protocol) which is what will enable communication between two computers.

For the network programming to work, both the socket and the URL must be programmed to receive the information. When you block the IP addresses of a certain website, what you are doing is restricting the communication between sockets for a specific URL. In this case, the client and the server are unable to communicate. However, when you are creating a program that will connect with several computers, they must be well established to ensure that most, if not all, of the users can access it.

To program these sockets and URLs, you will need to use the java.net package, including the extensions ServerSocket class that will provide the different methods, classes, and objects. In this case, it will be essential that both the client network and the URL are programmed with the specific IP (which stands for internet protocol) and the host and client addresses. All these can be accessed with the previously mentioned java.net package. Since you will be likely inputting and outputting information, this makes the java.io package essential for the data to be conveyed.

Here is an example of a detailed code in which communication is made between the sockets, servers, and IP addresses.

import java.io.BufferedReader;

import java.io.IOException;

import java.io.InputStreamReader;

import java.net.HttpURLConnection;

import java.net.URL;

public class SimpleHTTPClient {

public static void main(String[] args) {

try {

// Create a URL object

URL url = new URL("https://www.google.com");

// Open a connection to the URL

HttpURLConnection connection = (HttpURLConnection) url.openConnection();

// Set up the request method

connection.setRequestMethod("GET");

// Get the response code

int responseCode = connection.getResponseCode();

System.out.println("Response Code: " + responseCode);

// Read the response from the server

BufferedReader reader = new BufferedReader(new InputStreamReader(connection.getInputStream()));

String line;

StringBuilder response = new StringBuilder();

while ((line = reader.readLine()) != null) {

response.append(line);

}

reader.close();

// Display the response

System.out.println("Response from Server:\n" + response.toString());

// Disconnect the connection

connection.disconnect();

} catch (IOException e) {

e.printStackTrace();

}

}

}

Output:

Response Code: 200

Response from Server:

<!doctype html><html itemscope="" itemtype="http://schema.org/WebPage" lang="es"><head><...</body></html>

## CREATING CLIENT-SERVER APPLICATIONS

Although it might seem that creating a client-server application is complicated, the process is rather simple and can be carried out by downloading the java.io and the java.net packages and their specific classes. According to Nishkarshgandhi (2023), these are the five steps that should be followed to start creating your own code:

1.  Instantiate a ServerSocket object in the server informing it at which number the communication will happen.

2.  The server will request the accept() method and pause until the connection is made between the TCPs.

3.  The server will instantiate an object of the socket class in the client, and the server and port number will be given for connection.

4.  The constructor tries to connect to the designated server and port number. If the contact is authenticated, both servers will connect and start exchanging information.

5.  The server returns a reference to the new socket based on the client socket.

6.  Connection is closed between server and client ports.

In the two different code blocks you will see below, it will be possible to understand how the server and the client should have their network coded for this communication to work.

Server

import java.io.IOException;

import java.io.ObjectInputStream;

import java.io.ObjectOutputStream;

import java.net.ServerSocket;

import java.net.Socket;

public class SimpleServer {

public static void main(String[] args) {

final int PORT = 12345;

try {

// Create a server socket

ServerSocket serverSocket = new ServerSocket(PORT);

System.out.println("Server is listening on port " + PORT);

// Wait for a client to connect

Socket clientSocket = serverSocket.accept();

System.out.println("Client connected");

// Set up object input and output streams

ObjectInputStream objectInput = new ObjectInputStream(clientSocket.getInputStream());

ObjectOutputStream objectOutput = new ObjectOutputStream(clientSocket.getOutputStream());

// Read and print an object from the client

Object receivedObject = objectInput.readObject();

System.out.println("Received from client: " + receivedObject);

// Send a response object back to the client

Object response = "Hello from server!";

objectOutput.writeObject(response);

// Close the server socket

serverSocket.close();

} catch (IOException | ClassNotFoundException e) {

e.printStackTrace();

}

}

}

Client

import java.io.IOException;

import java.io.ObjectInputStream;

import java.io.ObjectOutputStream;

import java.net.Socket;

public class SimpleClient {

public static void main(String[] args) {

final String SERVER_IP = "127.0.0.1";

final int SERVER_PORT = 12345;

try {

// Connect to the server

Socket socket = new Socket(SERVER_IP, SERVER_PORT);

System.out.println("Connected to server");

// Set up object input and output streams

ObjectOutputStream objectOutput = new ObjectOutputStream(socket.getOutputStream());

ObjectInputStream objectInput = new ObjectInputStream(socket.getInputStream());

// Send an object to the server

Object message = "Hello from client!";

objectOutput.writeObject(message);

// Receive and print an object from the server

Object receivedObject = objectInput.readObject();

System.out.println("Received from server: " + receivedObject);

// Close the client socket

socket.close();

} catch (IOException | ClassNotFoundException e) {

e.printStackTrace();

}

}

}

While this is one of the ways to create and connect a network between client and server, there are other ways this can be done. To help you understand another way to make two computers communicate over a network, in the next section, we will see another code example that can be used as an alternative. This will give you more insight into the process of how the code should be generated and more options to select from.

## COMMUNICATING OVER A NETWORK

To look at the different options for communicating over a network, here is another example you can use to establish this connection between the client and the server. Once again, we will be using the java.io and java.net packages to carry out the code and all the steps that will be taken will be detailed as comments. This is another way to code this communication, giving you more diversification possibilities depending on the structure you are working with.

Server

import java.io.BufferedReader;

import java.io.IOException;

import java.io.InputStreamReader;

import java.io.PrintWriter;

import java.net.ServerSocket;

import java.net.Socket;

public class Server {

public static void main(String[] args) {

final int PORT = 8081;

try {

// Create a server socket

ServerSocket serverSocket = new ServerSocket(PORT);

System.out.println("Server listening on port " + PORT);

// Wait for a client to connect

Socket clientSocket = serverSocket.accept();

System.out.println("Client connected");

// Set up input and output streams

BufferedReader input = new BufferedReader(new InputStreamReader(clientSocket.getInputStream()));

PrintWriter output = new PrintWriter(clientSocket.getOutputStream(), true);

// Receive data from the client

String clientMessage = input.readLine();

System.out.println("Received from client: " + clientMessage);

// Send a response back to the client

output.println("Hello from server!");

// Close the server socket

serverSocket.close();

} catch (IOException e) {

e.printStackTrace();

}

}

}

Client

import java.io.BufferedReader;

import java.io.IOException;

import java.io.InputStreamReader;

import java.io.PrintWriter;

import java.net.Socket;

public class Client {

public static void main(String[] args) {

final String SERVER_IP = "127.0.0.1";

final int SERVER_PORT = 8081;

try {

// Connect to the server

Socket socket = new Socket(SERVER_IP, SERVER_PORT);

System.out.println("Connected to server");

// Set up input and output streams

BufferedReader input = new BufferedReader(new InputStreamReader(socket.getInputStream()));

PrintWriter output = new PrintWriter(socket.getOutputStream(), true);

// Send data to the server

output.println("Hello from client!");

// Receive and print the response from the server

String serverResponse = input.readLine();

System.out.println("Received from server: " + serverResponse);

// Close the client socket

socket.close();

} catch (IOException e) {

e.printStackTrace();

}

}

}

As you have seen, there are different ways to establish connections, as long as you understand that correctly programming the sockets and the URL are essential parts of the process. Despite this having been only an introduction, it will give you a starting knowledge for further study. In the following exercise, you will use all the knowledge you have obtained to code two different networks and establish communication between them.

## YOUR TURN TO TRY!

Using the knowledge you have gained in this chapter, the task you will create a basic client-server chat application in Java. You will be given instructions and a path to follow and a tentative solution to the exercise is provided at the end of the book.

Instructions:

1\. Server Implementation:

*   Implement a server that listens for incoming connections.

*   Upon connection, the server should store the client's socket and be ready to receive messages.

*   Implement a method to broadcast received messages from one client to all connected clients.

2\. Client Implementation:

*   Implement a client that connects to the server.

*   Allow the user to input messages on the client side.

*   Send the messages to the server for broadcasting.

3\. Testing:

*   Start the server.

*   Start multiple clients.

*   Allow clients to send messages, and ensure they are received by all connected clients.

You have now unlocked the power of network programming, enabling your applications to communicate across machines, platforms, and even across the globe! As we move to the last chapter of this book, we will learn how to debug and test your code, the final phase of software development. As you read its contents, remember to consider everything you have learned so far, all the items you have tested, and the exceptions you have encountered. You will see that most of them can be solved and caught in this last part of the process, which will help you prepare your software for launching and the production phase.

CHAPTER 12

DEBUGGING AND TESTING

According to a Cambridge University study, software bugs cost the economy $312 billion per year (Research by Cambridge MBAs, 2013). Want to learn how to save yourself and the world from this expense? In this chapter, you will learn about the last part of the programming process, which is the testing and debugging of your code. You will see different debugging tools and techniques in Java, as well as learn to understand unit testing with the JUnit framework, and how to write effective test cases. If you are ready for the last part of the start of your journey, read on! I am sure you will see that the different ways to carry out these tasks will make your life much easier.

## INTRODUCTION TO DEBUGGING

A bug in a program is an error that will occur in the code when it compiles and runs. This can happen due to different reasons, and usually, the output will not be produced, even if you apply a try-and-catch conditional to the code. Finding bugs can be quite hard, especially if we are talking about many lines of code and small differences. If you speak to a seasoned developer, you will likely hear stories about bugs they took forever to find, just because they were so subtle. For this reason, understanding the different tools that can be used to debug and test your code is essential: It will save you an incredible amount of time and effort.

## USING DEBUGGING TOOLS AND TECHNIQUES

If you are using an IDE to write your code, you are applying a best practice that will help you debug the code, since these have tools that will enable you to do this. In Eclipse, for example, you will be able to add breakpoints and watchpoints that will divide the code and make it run in parts. This will enable you to find the code block that has a problem per section. Eclipse also has a watch and inspect section that will enable you to check values while debugging, a useful feature that will help you understand why the output is as it is (How to Debug Java Errors, 2019).

If using the IntelliJ IDE, there are also a few tools you will be able to implement, similar to those in Eclipse. Nevertheless, if you are not using an IDE for your code, Monus (2020) suggests powerful Java code debugging tools you can download and use on your computer that include software for these purposes and even other online or open-source IDEs. They include and also expand to:

*   Java Discovery Protocol

*   JDeveloper

*   NetBeans

*   Raygun Crash Reporting

*   Rookout

*   The Java Debugger (jdb)

*   Visual Studio Code

## UNIT TESTING WITH JUNIT FRAMEWORK

When we are talking about unit testing, the benchmark is a program named JUnit. In this open-source framework, the developer can run automated tests that will show the results in graphs and other statistics that enable the code to be more reliable and bug-free. By testing the code "units" or small pieces of code, you will be able to break it down into segments that make the testing process more efficient (Gaba, 2023).

## WRITING TEST CASES

Regardless of the way you are going to test your code, you must understand how to write test cases that make this process feasible. When you create a test case, it should ideally have "test steps, test data, precondition, postcondition developed for specific test scenarios to verify any requirement. The test case includes specific variables or conditions, using which a testing engineer can compare expected and actual results" (Hamilton, 2023). Nonetheless, each test you write should serve a specific purpose, which means it will depend on what you are trying to identify. In the code below, you will find an example of a code test with explanations of what needs to be done in each step.

import org.junit.jupiter.api.*;

import static org.junit.jupiter.api.Assertions.assertEquals;

import static org.junit.jupiter.api.Assertions.assertThrows;

public class MathUtilsTest {

private MathUtils mathUtils;

@BeforeEach

void setUp() {

mathUtils = new MathUtils();

}

@Test

@DisplayName("Test Addition")

void testAddition() {

assertEquals(4, mathUtils.add(2, 2), "Addition should work");

}

@Test

@DisplayName("Test Subtraction")

void testSubtraction() {

assertEquals(2, mathUtils.subtract(4, 2), "Subtraction should work");

}

@Test

@DisplayName("Test Multiplication")

void testMultiplication() {

assertEquals(6, mathUtils.multiply(2, 3), "Multiplication should work");

}

@Test

@DisplayName("Test Division")

void testDivision() {

assertEquals(3, mathUtils.divide(9, 3), "Division should work");

}

@Test

@DisplayName("Test Divide By Zero")

void testDivideByZero() {

ArithmeticException exception = assertThrows(ArithmeticException.class,

() -> mathUtils.divide(5, 0), "Divide by zero should throw ArithmeticException");

assertEquals("Cannot divide by zero", exception.getMessage(), "Exception message should be correct");

}

@AfterEach

void tearDown() {

// Release any resources used for testing

mathUtils = null;

}

}

class MathUtils {

int add(int a, int b) {

return a + b;

}

int subtract(int a, int b) {

return a - b;

}

int multiply(int a, int b) {

return a * b;

}

int divide(int a, int b) {

if (b == 0) {

throw new ArithmeticException("Cannot divide by zero");

}

return a / b;

}

}

Whenever you are going to write test cases, you must remember to document what you are doing and use unique techniques for each case. The code should also be 100% covered and the end user must be kept in mind, after all, they will be the ones using the code. Finally, you should never assume the code is understandable or correct; creating code that is reusable and has undergone peer reviews will be essential to ensure optimal performance and efficient programs (Hamilton, 2023).

## LET'S TEST YOUR KNOWLEDGE!

1\. What is the purpose of a breakpoint in a debugger?

a. to halt the execution of the program at a specific point

b. to optimize the program execution

c. to print debug statements

d. to speed up the program

e. to create a new variable

2\. Which of the following is a benefit of using a debugger during development?

a. It helps write code faster

b. It allows real-time collaboration with teammates

c. It aids in identifying and fixing bugs in the code

d. It automates code documentation

e. It generates random test data

3\. What does JUnit provide for Java developers?

a. integrated development environment (IDE)

b. testing framework for unit tests

c. debugging tools

d. code versioning system

e. graphic design tools

4\. In JUnit, what annotation is used to denote a method as a test method?

a. @Test

b. @TestMethod

c. @Unit

d. @TestCase

e. @RunTest

5\. What is the purpose of the JUnit assertEquals method?

a. to check if two objects are the same instance

b. to verify that a condition is true

c. to check if the actual value is equal to the expected value

d. to compare objects for ordering

e. to calculate the square root of a number

6\. What is the role of a mock object in unit testing?

a. to simulate the behavior of a real object

b. to create graphical user interfaces

c. to generate random test data

d. to secure the test environment

e. to define new data types

7\. Which JUnit annotation is used for running code before each test method?

a. @BeforeEach

b. @BeforeTest

c. @Setup

d. @Before

e. @Initialize

8\. What is the purpose of the JUnit @Ignore annotation?

a. to mark a test method as not to be executed

b. to hide the test code from other developers

c. to increase the priority of a test method

d. to skip a test in case of an assertion failure

e. to generate test reports

9\. What is a common reason for a test case to fail in JUnit?

a. lack of comments in the code

b. insufficient test coverage

c. incorrect assertions or expectations

d. excessive code documentation

e. unused variables

10\. How can a developer debug a Java program in an IDE like IntelliJ IDEA?

a. by manually adding print statements

b. by using breakpoints and stepping through the code

c. by relying solely on error messages

d. by writing a separate debugging script

e. by automating the debugging process

As we move on to the conclusion of this book, we will look back into everything we have seen and learned throughout its 12 chapters. We will recap some of the content and see the different applications of Java in your life. All the necessary tools to start working in the area have been taught, and now it is time that you start exploring the full potential of this language based on what you have learned.

THE GATEWAY TO JAVA PROGRAMMING

Your coding journey is just beginning, and you have an exciting future ahead. Before you go, take a moment to help someone else out on their journey. 

Simply by sharing your honest opinion of this book and a little about your own experience, you’ll help new readers find the gateway to Java Programming they’re looking for.

![](image_rsrc4ZW.jpg)

Thank you so much for your support. I wish you the best of luck!

CONCLUSION

You have now unleashed the full power of Java and are ready to start exploring the fascinating world of programming. With the techniques you have learned in this book, you will be able to explore your way from the simplest types of programs to the most complex, such as integrating your program with networks. Throughout your journey, you have gone from the basics of installing a Java IDE to the final stages of debugging and testing your code.

We have looked into classes, methods, objects, interfaces, collections, GUI, and many other functions used in the developer's day-to-day. I encourage you to keep this book by your side as a reference guide, to which you can always come back to clarify doubts and look into the basics of Java programming. In addition, keeping a notebook and going back and testing all the code you have seen so far will be an excellent way to practice.

But you shouldn't stop there! Create your own code and test it! Make small and big programs to test the lessons and the content in this book. Remember that it is practice that makes perfect, and this will be essential for your development and growth as a Java coder. My main advice to you now is to keep studying and learning! There will always be different packages to learn and new versions of Java to explore. To help you with this process, you will see in the appendix the different online sources that have both been used in this book and help you to explore more aspects of Java.

If you feel this book has helped you and will be able to help other readers, I encourage you to leave a review and let others know! Finding resources that provide comprehensive content is sometimes hard, and others might benefit from this book's content. Lastly, I wish you good luck in your adventure as you continue your journey. Happy coding and see you soon!

APPENDIX

## JAVA KEYWORDS

In this section, you will find the Java keywords and a small explanation of what they are:

*   abstract: Used to declare abstract classes or methods.

*   assert: Used to debug and test assumptions in the code.

*   boolean: Used when there is only one choice out of two values, true or false.

*   break: Used to finalize a loop or a switch statement.

*   byte: Used to represent an integer with eight digits.

*   case: Used by the coder in the switch statements to detail each instance.

*   catch: Used to handle exceptions.

*   char: Used to represent a character with 16 bits in Unicode form.

*   class: Used to declare a class in Java.

*   const: Used to define constants.

*   continue: Used to skip a part of the loop and goes to the next part of the iteration.

*   default: Used to determine the default situation in a switch statement.

*   do: Used to start a while loop.

*   double: Used to represent a floating point with a 64-bit precision.

*   else: Used in conditional statements together with the if statement.

*   enum: Used to declare an enumerated type.

*   extends: Used to indicate that a class is inherited from another class previously declared.

*   final: Used to declare a constant or prevent overriding and inheritance.

*   finally: Used to handle exceptions and specify a block of code that must be run.

*   float: Used to represent a floating point with 32-bit precision.

*   for: Used to start a for loop.

*   goto: Although in disuse, it is used to reserve a code for future use.

*   if: Used to start an if statement.

*   implements: Used to indicate a class that implements a specific interface.

*   import: Used to import a package or a class in a program.

*   instanceof: Used to test if a specific object is an instance of an interface or a class.

*   int: Used to represent a 32-bit integer.

*   interface: Used to declare an interface in Java.

*   long: Used to represent an integer with 64 bits.

*   native: Used to indicate that the method is dependent on another code.

*   new: Used to create a new instance or object.

*   package: Used to declare a package in Java.

*   private: Used to specify a method or a variable that can only be accessible within the class into which it was declared.

*   protected: Used to specify that a variable or method can only be accessed in its own package or subclasses.

*   public: Used to specify that the method or variable can be accessed from any other class.

*   return: Used to exit a method and return a value.

*   short: Used to represent an integer with 16 bits.

*   static: Used to specify that a method or variable belongs to the class and not to the instances of the class.

*   strictfp: Used to ensure that the arithmetic operations with the floating point produce the same results on all platforms.

*   super: Used to refer to the immediate parent class object.

*   switch: Used to select what is the code block that will be executed.

*   synchronized: Used to specify that a method can only be accessed by a thread at a time.

*   this: Used to refer to a specific object.

*   throw: Used to throw an expression.

*   throws: Used to indicate that the method might throw one or more exceptions.

*   transient: Used to specify that the variable is not part of the object's state.

*   try: Used to specify a statement block that should be tried and handled for the exception.

*   void: Used to specify that there is no return value for a method.

*   volatile: Used to indicate that the variable can be changed by multiple threads.

*   while: Used to start a while loop.

(Java Language Keywords, n.d.; Java Keywords, n.d.)

## JAVA STANDARD LIBRARY PACKAGES

Here are a few useful and popular library packages that you might want to consider looking into to enhance the process of coding in Java:

*   java.applet: Used to create classes for Java applets and specialized applications to embed in webpages.

*   java.awt: Used for GUIs and image creation.

*   java.beans: Used to provide reusable components such as classes for code, which is specific for JavaBeans architecture.

*   java.io: Used for files or input and output operations.

*   java.lang: Used for the main built-in classes that can be imported into a Java program.

*   java.lang.reflect: Used to access information on fields, methods, and constructors for classes.

*   java.math: Used to perform mathematical operations, including providing additional classes.

*   java.net: Used for networking operations that use sockets, URLs, and other functionalities related to networks.

*   java.nio: Used as an alternative for java.io for high-performance operations and more efficient buffer handling.

*   java.rmi: Used for remote method invocation, using different JVMs.

*   java.security: Used to implement security features in Java, such as random numbers and cryptography.

*   java.sql: Used to connect your program to a database and interact with it.

*   java.swing: More advanced version of java.awt.

*   java.text: Used to work with data in text format, including formatting.

*   java.util: Used for enabling the developer to use classes and data structures such as collections, date, and time classes.

*   java.util.concurrent: Used to be applied for concurrent programming and includes classes for different states.

*   java.xml: Used to work with XML files.

## ONLINE RESOURCES

Here are a few online sources that might help you clarify any doubts you might have or for additional information regarding Java:

*   Official Oracle Java documentation

*   Coursera

*   Baeldung

*   Tutorials Point

*   GeeksforGeeks

*   Java Brains

*   GitHub

*   Stack Overflow

*   Programiz

*   Java Code Geeks

*   Vogella

*   Java Tutorials (Oracle)

*   Java Ranch

*   Oracle Java Magazine

ANSWERS

Here are the answers for the examples and tests throughout the book.

## CHAPTER 2

1\. Create a new variable with a string format.

public class <ClassName> {

public static void main(String[] args) {

String <variableName> = "Hello, World!";

System.out.println(<variableName>);

}

}

Output: Hello, World!

2\. For the previously created string, transform all the letters into upper case.

public class <ClassName> {

public static void main(String[] args) {

String <variableName> = "Hello, World!";

System.out.println(<variableName>);

String upperCaseString = myString.toUpperCase();

System.out.println(upperCaseString);

}

}

Output: HELLO, WORLD!

3\. Convert the double data type with value 458.96 to an int data type.

public class <ClassName> {

public static void main(String[] args) {

double <variableName> = 458.96;

int intValue = (int) <variableName>;

System.out.println(intValue);

}

}

Output: 458

4\. Convert an int data type with value of 6 into a float data type.

public class <ClassName> {

public static void main(String[] args) {

int <intVariableName> = 6;

float <floatVariableName> = (float) <intVariableName>;

System.out.println(<floatVariableName>);

}

}

Output: 6.0

5\. Super challenge: Add a variable with an int data type with a value of 56 with a variable with a double data type with value 897.69.

public class <ClassName> {

public static void main(String[] args) {

int <intVariableName>= 56;

double <doubleVariableName>= 897.69;

double sum = <intVariableName>+ <doubleVariableName>;

System.out.println(sum);

}

}

Output: 953.69

## CHAPTER 3

Panel 1 (Decision-Making—If-Else):

public class WakeUp {

public static void main(String[] args) {

boolean isAlarmRinging = true;

boolean isSnoozePressed = false;

if (isAlarmRinging) {

if (isSnoozePressed) {

System.out.println("The student hits snooze and misses the bus.");

} else {

System.out.println("The student gets up and catches the bus.");

}

} else {

System.out.println("No alarm, no rush.");

}

}

In this panel, it is possible to use an if-else decision statement to simulate the student's decision to snooze the alarm or get up. As you can see, the code checks if the alarm is ringing and if the snooze button is pressed. Depending on these conditions, different actions are taken.

Panel 2 (Looping—While):

public class InClass {

public static void main(String[] args) {

boolean isTeacherExplaining = true;

boolean isTakingNotes = false;

while (isTeacherExplaining) {

isTakingNotes = true;

System.out.println("The student keeps taking notes.");

// Additional logic to stop taking notes when the teacher stops explaining.

}

}

}

In this example, we are using a while loop to represent the student's action of taking notes continuously during the teacher's explanation. The loop continues as long as the teacher is explaining, and the student keeps taking notes.

Panel 3 (Branching—Switch-Case):

public class LunchTime {

public static void main(String[] args) {

int lunchChoice = 2; // 1 for pizza, 2 for burger, 3 for salad

switch (lunchChoice) {

case 1:

System.out.println("The student chooses pizza for lunch.");

break;

case 2:

System.out.println("The student selects a burger for lunch.");

break;

case 3:

System.out.println("The student opts for a healthy salad.");

break;

default:

System.out.println("Invalid lunch choice.");

}

}

In this answer, we are applying a switch-case statement to indicate the student's lunch choice. The variable lunchChoice holds the value that corresponds to the selected food option. Depending on the value, the student's lunch choice is displayed.

## CHAPTER 4

1\. Write a Java program with an integer array to create an array of integers, and within this array, determine: the sum of all elements, the maximum and minimum values, sort the numbers in ascending order, and calculate the average of the elements.

public class ArrayManipulation {

public static void main(String[] args) {

// Create an array of integers

int[] arr = {5, 2, 9, 1, 3};

// Find the sum of all elements in the array

int sum = 0;

for (int num : arr) {

sum += num;

}

System.out.println("Sum: " + sum);

// Find the maximum and minimum values in the array

int max = Integer.MIN_VALUE;

int min = Integer.MAX_VALUE;

for (int num : arr) {

if (num > max) {

max = num;

}

if (num < min) {

min = num;

}

}

System.out.println("Max: " + max);

System.out.println("Min: " + min);

// Sort the array in ascending order

Arrays.sort(arr);

System.out.println("Sorted Array: " + Arrays.toString(arr));

// Calculate the average of the elements in the array

double average = (double) sum / arr.length;

System.out.println("Average: " + average);

}

}

Output:

Sum: 20

Max: 9

Min: 1

Sorted Array: [1, 2, 3, 5, 9]

Average: 4.0

2\. Use ArrayList in Java to create a list of strings. In this example, you should use the list to add, remove, and update elements, check if a specific element exists, find the length, and iterate using a for-each loop, and print each element.

import java.util.ArrayList;

public class ListOperations {

public static void main(String[] args) {

// Create a list of strings

ArrayList<String> list = new ArrayList<>();

list.add("Apple");

list.add("Banana");

list.add("Cherry");

// Add, remove, and update elements in the list

list.add("Date");

list.remove(0);

list.set(1, "Blueberry");

// Check if a specific element exists in the list

boolean exists = list.contains("Banana");

System.out.println("Contains Banana: " + exists);

// Find the length of the list

int length = list.size();

System.out.println("List Length: " + length);

// Iterate through the list using a for-each loop and print each element

for (String fruit : list) {

System.out.println(fruit);

}

}

}

Output:

Contains Banana: true

List Length: 3

Banana

Blueberry

Date

3\. Create an integer array and convert it to an ArrayList. Carry out list operations like adding, removing, and iterating through elements.

import java.util.ArrayList;

import java.util.List;

public class ArrayToListConversion {

public static void main(String[] args) {

// Create an integer array

int[] intArray = {1, 2, 3, 4, 5};

// Convert the array to an ArrayList

List<Integer> arrayList = new ArrayList<>();

for (int value : intArray) {

arrayList.add(value);

}

// Perform various list operations

arrayList.add(6); // Adding an element

arrayList.remove(2); // Removing an element

for (int element : arrayList) {

System.out.print(element + " "); // Iterating through elements

}

}

}

Output: 1 2 4 5 6

4\. Create a two-dimensional array (matrix) and perform operations that include adding, subtracting, and multiplying the elements of the two matrices, transposing elements, and finding the determinant of a square matrix.

public class MatrixOperations {

public static void main(String[] args) {

int[][] matrixA = {

{1, 2, 3},

{4, 5, 6},

{7, 8, 9}

};

int[][] matrixB = {

{9, 8, 7},

{6, 5, 4},

{3, 2, 1}

};

// Adding two matrices

int[][] additionResult = addMatrices(matrixA, matrixB);

// Subtracting two matrices

int[][] subtractionResult = subtractMatrices(matrixA, matrixB);

// Multiplying two matrices

int[][] multiplicationResult = multiplyMatrices(matrixA, matrixB);

// Transposing matrices

int[][] transposeResult = transposeMatrix(matrixA);

// Finding the determinant of a square matrix

int determinant = calculateDeterminant(matrixA);

// Displaying results

System.out.println("Matrix A:");

printMatrix(matrixA);

System.out.println("Matrix B:");

printMatrix(matrixB);

System.out.println("Matrix A + Matrix B:");

printMatrix(additionResult);

System.out.println("Matrix A - Matrix B:");

printMatrix(subtractionResult);

System.out.println("Matrix A * Matrix B:");

printMatrix(multiplicationResult);

System.out.println("Transpose of Matrix A:");

printMatrix(transposeResult);

System.out.println("Determinant of Matrix A: " + determinant);

}

// Function for adding two matrices

public static int[][] addMatrices(int[][] A, int[][] B) {

int rows = A.length;

int cols = A[0].length;

int[][] result = new int[rows][cols];

for (int i = 0; i < rows; i++) {

for (int j = 0; j < cols; j++) {

result[i][j] = A[i][j] + B[i][j];

}

}

return result;

}

// Function for subtracting two matrices

public static int[][] subtractMatrices(int[][] A, int[][] B) {

int rows = A.length;

int cols = A[0].length;

int[][] result = new int[rows][cols];

for (int i = 0; i < rows; i++) {

for (int j = 0; j < cols; j++) {

result[i][j] = A[i][j] - B[i][j];

}

}

return result;

}

// Function for multiplying two matrices

public static int[][] multiplyMatrices(int[][] A, int[][] B) {

int rowsA = A.length;

int colsA = A[0].length;

int colsB = B[0].length;

int[][] result = new int[rowsA][colsB];

for (int i = 0; i < rowsA; i++) {

for (int j = 0; j < colsB; j++) {

int sum = 0;

for (int k = 0; k < colsA; k++) {

sum += A[i][k] * B[k][j];

}

result[i][j] = sum;

}

}

return result;

}

// Function for transposing a matrix

public static int[][] transposeMatrix(int[][] matrix) {

int rows = matrix.length;

int cols = matrix[0].length;

int[][] result = new int[cols][rows];

for (int i = 0; i < rows; i++) {

for (int j = 0; j < cols; j++) {

result[j][i] = matrix[i][j];

}

}

return result;

}

// Function to calculate the determinant of a 3x3 matrix

public static int calculateDeterminant(int[][] matrix) {

return matrix[0][0] * (matrix[1][1] * matrix[2][2] - matrix[1][2] * matrix[2][1])

- matrix[0][1] * (matrix[1][0] * matrix[2][2] - matrix[1][2] * matrix[2][0])

+ matrix[0][2] * (matrix[1][0] * matrix[2][1] - matrix[1][1] * matrix[2][0]);

}

// Function to print a matrix

public static void printMatrix(int[][] matrix) {

for (int i = 0; i < matrix.length; i++) {

for (int j = 0; j < matrix[i].length; j++) {

System.out.print(matrix[i][j] + " ");

}

System.out.println();

}

}

}

Output:

Matrix A:

1 2 3

4 5 6

7 8 9

Matrix B:

9 8 7

6 5 4

3 2 1

Matrix A + Matrix B:

10 10 10

10 10 10

10 10 10

Matrix A - Matrix B:

-8 -6 -4

-2 0 2

4 6 8

Matrix A * Matrix B:

30 24 18

84 69 54

138 114 90

Transpose of Matrix A:

1 4 7

2 5 8

3 6 9

Determinant of Matrix A: 0

5\. Use the HashSet or TreeSet in Java to create sets of integers and perform operations within it such as union, intersection, difference, and checking an element's existence.

import java.util.HashSet;

import java.util.Set;

public class SetOperations {

public static void main(String[] args) {

// Create sets of integers

Set<Integer> set1 = new HashSet<>();

set1.add(1);

set1.add(2);

set1.add(3);

Set<Integer> set2 = new HashSet<>();

set2.add(2);

set2.add(3);

set2.add(4);

// Perform set operations

Set<Integer> union = new HashSet<>(set1);

union.addAll(set2);

System.out.println("Union: " + union);

Set<Integer> intersection = new HashSet<>(set1);

intersection.retainAll(set2);

System.out.println("Intersection: " + intersection);

Set<Integer> difference = new HashSet<>(set1);

difference.removeAll(set2);

System.out.println("Difference: " + difference);

boolean exists = set1.contains(2);

System.out.println("Element 2 exists in set1: " + exists);

}

}

Output:

Union: [1, 2, 3, 4]

Intersection: [2, 3]

Difference: [1]

Element 2 exists in set1: true

6\. Work with HashMap in Java to create a map that associates names with ages. Once it has been created, you will need to add, remove, or update entries, retrieve the age of a specific name, iterate through it, and print all key-value pairs.

import java.util.HashMap;

import java.util.Map;

public class MapOperations {

public static void main(String[] args) {

// Create a map that associates names with ages

Map<String, Integer> ageMap = new HashMap<>();

ageMap.put("Alice", 25);

ageMap.put("Bob", 30);

ageMap.put("Charlie", 22);

// Add, remove, or update entries

ageMap.put("David", 28);

ageMap.remove("Charlie");

ageMap.put("Alice", 26); // Updating Alice's age

// Retrieve the age of a specific name

int ageOfBob = ageMap.get("Bob");

System.out.println("Bob's age: " + ageOfBob);

// Iterate through the map and print all key-value pairs

for (Map.Entry<String, Integer> entry : ageMap.entrySet()) {

System.out.println(entry.getKey() + ": " + entry.getValue());

}

}

}

Output:

Bob's age: 30

Bob: 30

Alice: 26

David: 28

7\. Use LinkedList or ArrayDeque in Java to create a queue and perform operations (enqueue and dequeue) and create a stack and perform stack operations (push and pop).

public class QueueExample {

public static void main(String[] args) {

Queue<String> queue = new LinkedList<>();

queue.add("First");

queue.add("Second");

String dequeued = queue.poll(); // Dequeue

System.out.println(dequeued);

}

}

Output: First

import java.util.ArrayDeque;

import java.util.Deque;

public class StackExample {

public static void main(String[] args) {

Deque<String> stack = new ArrayDeque<>();

stack.push("First");

stack.push("Second");

String popped = stack.pop(); // Pop

System.out.println(popped); // Output: Second

}

}

Output: Second

## CHAPTER 5

Create a Java program with overloaded methods to calculate the area of a circle and a rectangle, in which the main method should be used to demonstrate the use of the methods.

public class AreaCalculator {

// Method to calculate the area of a circle

public static double calculateArea(double radius) {

return Math.PI * radius * radius;}

// Method to calculate the area of a rectangle

public static double calculateArea(double length, double width) {

return length * width;

}

public static void main(String[] args) {

// Example of usage

double circleArea = Main.calculateArea(5.0);

double rectangleArea = Main.calculateArea(4.0, 6.0);

System.out.println("Circle area: " + circleArea);

System.out.println("Rectangle area: " + rectangleArea);

}

}

Output:

Circle area: 78.53981633974483

Rectangle area: 24.0

## CHAPTER 6

1.  b. An object is an instance of a class

2.  b. to provide a blueprint for other classes

3.  d. overloading and overriding

4.  b. the ability of a class to extend another class

5.  a. wrapping data and code that operates on the data into a single unit

6.  a. override

7.  d. to declare a set of method signatures

8.  b. making a method private

9.  d. type

10.  b. polymorphism

## CHAPTER 8

IO Answer

import java.io.*;

public class FileIOChallenge {

public static void main(String[] args) {

// Task 1

createFile("file_io_challenge.txt");

writeToFile("file_io_challenge.txt", "Hello, File I/O Challenge!");

String content = readFromFile("file_io_challenge.txt");

System.out.println("Content read from the file: " + content);

deleteFile("file_io_challenge.txt");

// Task 2

Student student = new Student("John Doe", 20, 'A');

serializeObject(student, "serialized_object.dat");

Student deserializedStudent = deserializeObject("serialized_object.dat");

System.out.println("Deserialized Object: " + deserializedStudent);

}

// Task 1 - Basic File Operations

private static void createFile(String fileName) {

try {

File file = new File(fileName);

file.createNewFile();

} catch (IOException e) {

e.printStackTrace();

}

}

private static void writeToFile(String fileName, String content) {

try (FileWriter writer = new FileWriter(fileName)) {

writer.write(content);

} catch (IOException e) {

e.printStackTrace();

}

}

private static String readFromFile(String fileName) {

StringBuilder content = new StringBuilder();

try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {

String line;

while ((line = reader.readLine()) != null) {

content.append(line).append("\n");

}

} catch (IOException e) {

e.printStackTrace();

}

return content.toString();

}

private static void deleteFile(String fileName) {

File file = new File(fileName);

if (file.exists()) {

file.delete();

}

}

// Task 2 - Object serialization

private static void serializeObject(Student student, String fileName) {

try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(fileName))) {

oos.writeObject(student);

} catch (IOException e) {

e.printStackTrace();

}

}

private static Student deserializeObject(String fileName) {

Student student = null;

try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(fileName))) {

student = (Student) ois.readObject();

} catch (IOException | ClassNotFoundException e) {

e.printStackTrace();

}

return student;

}

}

class Student implements Serializable {

String name;

int age;

char grade;

public Student(String name, int age, char grade) {

this.name = name;

this.age = age;

this.grade = grade;

}

@Override

public String toString() {

return "Student{name='" + name + "', age=" + age + ", grade=" + grade + '}';

}

}

NIO Answer

import java.io.ObjectInputStream;

import java.io.ObjectOutputStream;

import java.io.Serializable;

import java.nio.file.Path;

import java.nio.file.Paths;

import java.nio.file.StandardOpenOption;

import java.nio.file.Files;

import java.io.IOException;

import java.util.List;

public class FileIOChallengeNIO {

public static void main(String[] args) {

// Task 1

Path filePath = createFile("file_nio_challenge.txt");

writeToFile(filePath, "Hello, File I/O Challenge!");

String content = readFromFile(filePath);

System.out.println("Content read from the file: " + content);

deleteFile(filePath);

// Task 2

Student student = new Student("John Doe", 20, 'A');

Path serializedFilePath = Paths.get("serialized_object.dat");

serializeObject(student, serializedFilePath);

Student deserializedStudent = deserializeObject(serializedFilePath);

System.out.println("Deserialized Object: " + deserializedStudent);

}

// Task 1 - Basic File Operations with NIO

private static Path createFile(String fileName) {

Path filePath = Paths.get(fileName);

try {

return Files.createFile(filePath);

} catch (IOException e) {

e.printStackTrace();

return null;

}

}

private static void writeToFile(Path filePath, String content) {

try {

Files.write(filePath, content.getBytes(), StandardOpenOption.WRITE);

} catch (IOException e) {

e.printStackTrace();

}

}

private static String readFromFile(Path filePath) {

try {

List<String> lines = Files.readAllLines(filePath);

return String.join("\n", lines);

} catch (IOException e) {

e.printStackTrace();

return "";

}

}

private static void deleteFile(Path filePath) {

try {

Files.deleteIfExists(filePath);

} catch (IOException e) {

e.printStackTrace();

}

}

// Task 2 - Object Serialization with NIO

private static void serializeObject(Student student, Path filePath) {

try (ObjectOutputStream oos = new ObjectOutputStream(Files.newOutputStream(filePath))) {

oos.writeObject(student);

} catch (IOException e) {

e.printStackTrace();

}

}

private static Student deserializeObject(Path filePath) {

Student student = null;

try (ObjectInputStream ois = new ObjectInputStream(Files.newInputStream(filePath))) {

student = (Student) ois.readObject();

} catch (IOException | ClassNotFoundException e) {

e.printStackTrace();

}

return student;

}

}

// Student class remains the same

class Student implements Serializable {

String name;

int age;

char grade;

public Student(String name, int age, char grade) {

this.name = name;

this.age = age;

this.grade = grade;

}

@Override

public String toString() {

return "Student{name='" + name + "', age=" + age + ", grade=" + grade + '}';

}

}

## CHAPTER 9

1.  a. concat()

2.  b. length()

3.  c. Date

4.  a. abs()

5.  b. nextInt()

6.  a. Set

7.  a. add()

8.  a. Map<String, Integer> myMap = new HashMap<>();

9.  a. ArrayList allows random access, while LinkedList is more efficient for insertions and removals

10.  c. HashSet

## CHAPTER 10

import javax.swing.*;

import java.awt.*;

import java.awt.event.ActionEvent;

import java.awt.event.ActionListener;

public class FormSubmissionApp {

public static void main(String[] args) {

// Create the main frame

JFrame frame = new JFrame("Form Submission App");

frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

frame.setSize(300, 200);

// Create and set layout manager

JPanel panel = new JPanel();

panel.setLayout(new GridLayout(3, 2));

// Create components

JLabel nameLabel = new JLabel("Name:");

JTextField nameField = new JTextField();

JLabel ageLabel = new JLabel("Age:");

JTextField ageField = new JTextField();

JButton submitButton = new JButton("Submit");

// Add components to the panel

panel.add(nameLabel);

panel.add(nameField);

panel.add(ageLabel);

panel.add(ageField);

panel.add(new JLabel()); // Empty label for spacing

panel.add(submitButton);

// Add action listener to the button

submitButton.addActionListener(new ActionListener() {

@Override

public void actionPerformed(ActionEvent e) {

// Handle the button click

String name = nameField.getText();

String age = ageField.getText();

System.out.println("Name: " + name);

System.out.println("Age: " + age);

});

// Add the panel to the frame

frame.add(panel);

// Set the frame visibility

frame.setVisible(true);

}

}

## CHAPTER 11

Before we get to the answer, here are a few instructions you might want to consider:

1\. Compile the code:

*   Save the server code in a file named ChatServer.java.

*   Save the client code in a file named ChatClient.java.

*   Save the client handler code in a file named ClientHandler.java.

*   Open a terminal and compile the server, client, and client handler classes separately using the javac command:

javac ChatServer.java

javac ChatClient.java

javac ClientHandler.java

2\. Run the Server: In the same terminal, run the server using the java command:

java ChatServer

The server will start listening on port 8080.

3\. Run the Clients: Open new terminals for each client and run the client in each terminal:

java ChatClient

Each client will connect to the server.

4\. Chat: Type messages in the client terminals, and the messages will be broadcast to all connected clients.

5\. Terminate:

*   To terminate a client, press Ctrl+C in its terminal.

*   To terminate the server, press Ctrl+C in its terminal.

ChatServer:

import java.io.*;

import java.net.ServerSocket;

import java.net.Socket;

import java.util.HashSet;

import java.util.Set;

public class ChatServer {

private static final int PORT = 8082;

static Set<PrintWriter> clientWriters = new HashSet<>();

public static void main(String[] args) {

try {

ServerSocket serverSocket = new ServerSocket(PORT);

System.out.println("Server listening on port " + PORT);

while (true) {

Socket clientSocket = serverSocket.accept();

PrintWriter writer = new PrintWriter(clientSocket.getOutputStream(), true);

clientWriters.add(writer);

Thread clientHandler = new Thread(new ClientHandler(clientSocket, writer));

clientHandler.start();

}

} catch (IOException e) {

e.printStackTrace();

}

}

public static void broadcastMessage(String message, PrintWriter sender) {

for (PrintWriter writer : clientWriters) {

if (writer != sender) {

writer.println(message);

}

}

}

}

Client Handler

import java.io.BufferedReader;

import java.io.IOException;

import java.io.InputStreamReader;

import java.io.PrintWriter;

import java.net.Socket;

public class ClientHandler implements Runnable {

private Socket clientSocket;

private PrintWriter writer;

public ClientHandler(Socket clientSocket, PrintWriter writer) {

this.clientSocket = clientSocket;

this.writer = writer;

}

@Override

public void run() {

try {

BufferedReader reader = new BufferedReader(new InputStreamReader(clientSocket.getInputStream()));

String message;

while ((message = reader.readLine()) != null) {

ChatServer.broadcastMessage(message, writer);

}

} catch (IOException e) {

// Handle client disconnection

System.out.println("Client disconnected.");

ChatServer.clientWriters.remove(writer);

}

}

}

Chat Client

import java.io.*;

import java.net.Socket;

import java.util.Scanner;

public class ChatClient {

public static void main(String[] args) {

try {

Socket socket = new Socket("localhost", 8082);

BufferedReader reader = new BufferedReader(new InputStreamReader(socket.getInputStream()));

PrintWriter writer = new PrintWriter(socket.getOutputStream(), true);

Scanner scanner = new Scanner(System.in);

Thread messageReceiver = new Thread(() -> {

try {

String message;

while ((message = reader.readLine()) != null) {

System.out.println(message);

}

} catch (IOException e) {

e.printStackTrace();

}

});

messageReceiver.start();

// Read user input and send messages to the server

while (true) {

String message = scanner.nextLine();

writer.println(message);

}

} catch (IOException e) {

e.printStackTrace();

}

}

}

## CHAPTER 12

1.  a. to halt the execution of the program at a specific point

2.  c. it aids in identifying and fixing bugs in code

3.  b. testing framework for unit tests

4.  a. to halt the execution of the program at a specific point

5.  c. to check if the actual value is equal to the expected value

6.  a. to simulate the behavior of a real object

7.  a. @BeforeEach

8.  a. to mark a test method as not to be executed

9.  c. incorrect assertions or expectations

10.  b. by using breakpoints and stepping through the code

REFERENCES

Adware. (2022, June 23). Difference between compile-time and run-time polymorphism in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/difference-between-compile-time-and-run-time-polymorphism-in-java](https://www.geeksforgeeks.org/difference-between-compile-time-and-run-time-polymorphism-in-java)

Agrawal, S. (2023, March 27). Data types in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/data-types-in-java](https://www.geeksforgeeks.org/data-types-in-java)

Akshaysobti15\. (2022, August 16). What are the roles of Java compiler and interpreter? GeeksforGeeks. [https://www.geeksforgeeks.org/what-are-the-roles-of-java-compiler-and-interpreter](https://www.geeksforgeeks.org/what-are-the-roles-of-java-compiler-and-interpreter)

Arrays. (2017). Oracle. [https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)

Badkar, A. (2023, August 31). Type casting in Java: Everything you need to know. Simplilearn. [https://www.simplilearn.com/tutorials/java-tutorial/type-casting-in-java](https://www.simplilearn.com/tutorials/java-tutorial/type-casting-in-java)

baeldung. (2019, January 22). Variable scope in Java. Baeldung. [https://www.baeldung.com/java-variable-scope](https://www.baeldung.com/java-variable-scope)

baeldung. (2020, October 10). Baeldung. Guide to the Java finally keyword. [https://www.baeldung.com/java-finally-keyword](https://www.baeldung.com/java-finally-keyword)

baeldung. (2022, October 20). Baeldung. Using an interface vs. abstract class in Java. [https://www.baeldung.com/java-interface-vs-abstract-class](https://www.baeldung.com/java-interface-vs-abstract-class)

Challa, A. (n.d.). String handling functions using Java. Educative. [https://www.educative.io/answers/string-handling-functions-using-java](https://www.educative.io/answers/string-handling-functions-using-java)

Chris, K. (2021, September 9). Java array declaration – How to initialize an array in Java with example code. FreeCodeCamp. [https://www.freecodecamp.org/news/java-array-declaration-how-to-initialize-an-array-in-java-with-example-code](https://www.freecodecamp.org/news/java-array-declaration-how-to-initialize-an-array-in-java-with-example-code)

Coursera. (2023, July 24). What is programming? And how to get started. Coursera. [https://www.coursera.org/articles/what-is-programming](https://www.coursera.org/articles/what-is-programming)

Cyubahiro, P. (2022, April 18). Object-oriented programming in Java – A beginner's guide. FreeCodeCamp. [https://www.freecodecamp.org/news/object-oriented-programming-concepts-java](https://www.freecodecamp.org/news/object-oriented-programming-concepts-java)

Defining methods. (n.d.). Oracle. [https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html)

Difference between compile time and run time polymorphism in Java. (n.d.). Unacademy. [https://unacademy.com/content/gate-cse-it/difference-between-compile-time-and-run-time-polymorphism-in-java](https://unacademy.com/content/gate-cse-it/difference-between-compile-time-and-run-time-polymorphism-in-java)

Difference between data hiding and encapsulation. (n.d.). Tutorials Point. [https://www.tutorialspoint.com/difference-between-data-hiding-and-encapsulation](https://www.tutorialspoint.com/difference-between-data-hiding-and-encapsulation)

Event handling in Java GUI. (n.d.). Studytonight. [https://www.studytonight.com/java/event-handling-in-java.php](https://www.studytonight.com/java/event-handling-in-java.php)

The finally block. (n.d.). Oracle. [https://docs.oracle.com/javase/tutorial/essential/exceptions/finally.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/finally.html)

Gaba, I. (2023, February 14). What is JUnit: An overview of the best Java testing framework. Simplilearn. [https://www.simplilearn.com/tutorials/java-tutorial/what-is-junit](https://www.simplilearn.com/tutorials/java-tutorial/what-is-junit)

GeeksforGeeks. (2023a, August 7). Exceptions in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/exceptions-in-java](https://www.geeksforgeeks.org/exceptions-in-java)

GeeksforGeeks. (2023b, August 24). ArrayList vs LinkedList in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/arraylist-vs-linkedlist-java](https://www.geeksforgeeks.org/arraylist-vs-linkedlist-java)

Great Learning Team. (2023, August 14). Method overloading in Java with examples. Great Learning. [https://www.mygreatlearning.com/blog/method-overloading-in-java](https://www.mygreatlearning.com/blog/method-overloading-in-java)

Gupta, D. K. (2020, July 16). Type conversion in Java | Type casting, example. ScientechEasy.com. [https://www.scientecheasy.com/2020/07/type-conversion-casting-java.html](https://www.scientecheasy.com/2020/07/type-conversion-casting-java.html)

Hamilton, T. (2023, October 25). How to write test cases: Sample template with examples. Guru99\. [https://www.guru99.com/test-case.html](https://www.guru99.com/test-case.html)

Harold, E. R. (2000). Java network programming. O'Reilly. [https://www.oreilly.com/library/view/java-network-programming/9781449365936/ch01.html](https://www.oreilly.com/library/view/java-network-programming/9781449365936/ch01.html)

How to debug Java errors. (2019, February 12). Rollbar. [https://rollbar.com/guides/java/how-to-debug-java-errors](https://rollbar.com/guides/java/how-to-debug-java-errors)

How to manipulate objects using lambdas in Java. (2021, November 23). Section. [https://www.section.io/engineering-education/using-lambdas-to-manipulate-a-collection-of-objects](https://www.section.io/engineering-education/using-lambdas-to-manipulate-a-collection-of-objects)

How to throw exceptions. (n.d.). Oracle. [https://docs.oracle.com/javase/tutorial/essential/exceptions/throwing.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/throwing.html)

How to throw exceptions in Java. (2019, February 12). Rollbar. [https://rollbar.com/guides/java/how-to-throw-exceptions-in-java](https://rollbar.com/guides/java/how-to-throw-exceptions-in-java)

Izydorczyk, A. (2022, October 13). Why Java is still dominating the programming landscape. Espeo Software. [https://espeo.eu/blog/java-programming-landscape](https://espeo.eu/blog/java-programming-landscape)

Janssen, T. (2021, December 17). OOP concepts for beginners: What is polymorphism. Stackify. [https://stackify.com/oop-concept-polymorphism](https://stackify.com/oop-concept-polymorphism)

Java - Basic syntax. (n.d.). Tutorials Point. [https://www.tutorialspoint.com/java/java_basic_syntax.htm](https://www.tutorialspoint.com/java/java_basic_syntax.htm)

Java - Variable types. (2020). Tutorials Point. [https://www.tutorialspoint.com/java/java_variable_types.htm](https://www.tutorialspoint.com/java/java_variable_types.htm)

Java API. (2023, July 24). Wallarm. [https://www.wallarm.com/what/what-is-java-api](https://www.wallarm.com/what/what-is-java-api)

Java arrays. (2019). Programiz. [https://www.programiz.com/java-programming/arrays](https://www.programiz.com/java-programming/arrays)

Java collections framework. (n.d.). Programiz. [https://www.programiz.com/java-programming/collections](https://www.programiz.com/java-programming/collections)

Java Hello World program. (n.d.). Programiz. [https://www.programiz.com/java-programming/hello-world](https://www.programiz.com/java-programming/hello-world)

Java keywords. (n.d.). W3Schools. [https://www.w3schools.com/java/java_ref_keywords.asp](https://www.w3schools.com/java/java_ref_keywords.asp)

Java language keywords. (n.d.). Oracle. [https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)

Java list. (n.d.). Programiz. [https://www.programiz.com/java-programming/list](https://www.programiz.com/java-programming/list)

Java method overloading (with examples). (n.d.). Programiz. [https://www.programiz.com/java-programming/method-overloading](https://www.programiz.com/java-programming/method-overloading)

Java multi-dimensional arrays. (n.d.). W3Schools. [https://www.w3schools.com/java/java_arrays_multi.asp](https://www.w3schools.com/java/java_arrays_multi.asp)

Java object and classes. (2019). Tutorials Point. [https://www.tutorialspoint.com/java/java_object_classes.htm](https://www.tutorialspoint.com/java/java_object_classes.htm)

Java OOP (Object-oriented programming). (2020). W3Schools. [https://www.w3schools.com/java/java_oop.asp](https://www.w3schools.com/java/java_oop.asp)

Java recursion. (n.d.). W3Schools. [https://www.w3schools.com/java/java_recursion.asp](https://www.w3schools.com/java/java_recursion.asp)

Java recursion: Recursive methods (with examples). (n.d.). Programiz. [https://www.programiz.com/java-programming/recursion](https://www.programiz.com/java-programming/recursion)

Java switch. (n.d.). W3Schools. [https://www.w3schools.com/java/java_switch.asp](https://www.w3schools.com/java/java_switch.asp)

Learning the Java language. (n.d.). Oracle. [https://docs.oracle.com/javase/tutorial/java/](https://docs.oracle.com/javase/tutorial/java/)

Javin, Paul. "20 Java and Programming Quotes to Motivate Yourself." Javarevisited: Blog About Java Programming Tutorials, Examples, Design Patterns, Interview Questions and Answers, FIX Protocol, Tibco RV Messaging, UNIX and Linux Commands, XML, SQL, MySQL, Oracle, JQuery, JavaScript, HTML, Multithreading, Collection, Error and Exception, Debugging, Best Practices and Practical Tips from My Experience. Last modified May 5, 2023\. [https://javarevisited.blogspot.com/2018/08/20-java-quotes-to-learn-and-motivate-yourself.html](https://javarevisited.blogspot.com/2018/08/20-java-quotes-to-learn-and-motivate-yourself.html).

Khan, A. (2023, June 1). What is encapsulation in Java? Intellipaat. [https://intellipaat.com/blog/java-encapsulation](https://intellipaat.com/blog/java-encapsulation)

Khurpaderushi143\. (2023, March 29). Introduction to Java swing. GeeksforGeeks. [https://www.geeksforgeeks.org/introduction-to-java-swing](https://www.geeksforgeeks.org/introduction-to-java-swing)

Lenka, C. (2023, April 4). Java logical operators with examples. GeeksforGeeks. [https://www.geeksforgeeks.org/java-logical-operators-with-examples](https://www.geeksforgeeks.org/java-logical-operators-with-examples)

The method declaration. (n.d.). Whitman College. [https://www.whitman.edu/mathematics/java_tutorial/java/javaOO/methoddecl.html](https://www.whitman.edu/mathematics/java_tutorial/java/javaOO/methoddecl.html)

Miglani, G. (2023, September 22). Classes and objects in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/classes-objects-java](https://www.geeksforgeeks.org/classes-objects-java)

Minh, N. H. (2019, July 18). How to read and write text file in Java. CodeJava. [https://www.codejava.net/java-se/file-io/how-to-read-and-write-text-file-in-java](https://www.codejava.net/java-se/file-io/how-to-read-and-write-text-file-in-java)

Monus, A. (2020, January). 6 Java debugging tools you should know. Raygun Blog. [https://raygun.com/blog/java-debugging-tools/](https://raygun.com/blog/java-debugging-tools/)

Nested loop in Java (with examples). (n.d.). Programiz. [https://www.programiz.com/java-programming/nested-loop](https://www.programiz.com/java-programming/nested-loop)

Nishkarshgandhi. (2023, February 28). Java networking. GeeksforGeeks. [https://www.geeksforgeeks.org/java-networking](https://www.geeksforgeeks.org/java-networking)

Nitsdheerendra. (2023, April 5). Difference between abstract class and interface in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/difference-between-abstract-class-and-interface-in-java](https://www.geeksforgeeks.org/difference-between-abstract-class-and-interface-in-java)

Overview (JavaFX 21). (n.d.). OpenJFX. [https://openjfx.io/javadoc/21](https://openjfx.io/javadoc/21)

Praneethharsha10\. (2023, September 23). Multidimensional arrays in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/multidimensional-arrays-in-java](https://www.geeksforgeeks.org/multidimensional-arrays-in-java)

raja. (2023, November 23). Importance of return type in Java. Tutorials Point. [https://www.tutorialspoint.com/importance-of-return-type-in-java](https://www.tutorialspoint.com/importance-of-return-type-in-java)

Ravikiran A. S. (2023, February 13). Collections in Java and how to implement them? Simplilearn. [https://www.simplilearn.com/tutorials/java-tutorial/java-collection](https://www.simplilearn.com/tutorials/java-tutorial/java-collection)

Research by Cambridge MBAs for tech firm Undo finds software bugs cost the industry $316 billion a year. (2013, January 25). Cambridge Judge Business School. [https://www.jbs.cam.ac.uk/2013/research-by-cambridge-mbas-for-tech-firm-undo-finds-software-bugs-cost-the-industry-316-billion-a-year](https://www.jbs.cam.ac.uk/2013/research-by-cambridge-mbas-for-tech-firm-undo-finds-software-bugs-cost-the-industry-316-billion-a-year)

Reuters. (2004, February 15). Java runs remote-controlled Mars rover. CNET. [https://www.cnet.com/tech/tech-industry/java-runs-remote-controlled-mars-rover](https://www.cnet.com/tech/tech-industry/java-runs-remote-controlled-mars-rover)

RishabhPrabhu. (2023, July 21). Object oriented programming (OOP) concept in Java. GeeksforGeeks. [https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java)

Simplilearn. (2023, February 21). An introduction to methods in Java with examples. Simplilearn. [https://www.simplilearn.com/tutorials/java-tutorial/methods-in-java](https://www.simplilearn.com/tutorials/java-tutorial/methods-in-java)

Singh, C. (2013, May 18). How to compile and run your first Java program. Beginners Book. [https://beginnersbook.com/2013/05/first-java-program](https://beginnersbook.com/2013/05/first-java-program)

Sedgewick, R. & Wayne, K. (2016). Computer science: An interdisciplinary approach (1st ed.).  Addison-Wesley Professional.

The state of developer ecosystem in 2022. (2023). JetBrains. [https://www.jetbrains.com/lp/devecosystem-2022](https://www.jetbrains.com/lp/devecosystem-2022)

Svet, O. (2023, April 25). Top industries and cases for using Java. Computools. [https://computools.com/top-industries-and-cases-for-using-java](https://computools.com/top-industries-and-cases-for-using-java)

Tyson, M. (2022, September 23). What is the JDK? Introduction to the Java development kit. InfoWorld. [https://www.infoworld.com/article/3296360/what-is-the-jdk-introduction-to-the-java-development-kit.html](https://www.infoworld.com/article/3296360/what-is-the-jdk-introduction-to-the-java-development-kit.html)

Understand parameters and return values. (2023, May 22). OpenClassrooms. [https://openclassrooms.com/en/courses/5667431-learn-programming-with-java/5929871-understand-parameters-and-return-values](https://openclassrooms.com/en/courses/5667431-learn-programming-with-java/5929871-understand-parameters-and-return-values)

Vats, R. (2021, February 5). Scope of a variable in Java [with coding example]. UpGrad Blog. [https://www.upgrad.com/blog/scope-of-a-variable-in-java](https://www.upgrad.com/blog/scope-of-a-variable-in-java)