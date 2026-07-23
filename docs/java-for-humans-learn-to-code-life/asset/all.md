![](cover.jpeg)

1

Java for Humans

Learn to Code Life

Let's take a journey on a path to a new life of developing the software that enables the world.

2

3

*This book is dedicated to my mom and dad for always inspiring me to be and do more.*

*Also to my first computer science professor who taught me the foundations of programming in Java. Doctor James Early has been a great professor and adviser to me since we met in that introductory CS course. I am forever grateful to him for building upon my excitement for programming and helping me develop a passion for the software development industry.*

*I am writing this book as I am — by relating Java and programming concepts to human experiences — because I learned from Doctor Early that the best way to teach a language to beginners is by learning to speak their language.*

**Dedication**

4

5

Java for Humans

Learn to Code Life

ModernNerd

Teaching coding in more

human relatable ways.

6

**Contents**

[Dedication](#part0002.html_1T140-397c330900cd4534952763229706e0c7) ………………………..………..............................………………………..………... 3

[Preface](#part0007.html_6LJU0-397c330900cd4534952763229706e0c7) ….………………………..………..............................………………………..……….... 8

About the Author ………………………..………..............................………………... 9

Motivation ………………………..………..............................………………………... 9

Audience ………………………..………..............................………………….. 9

Learning Goals ...……...................................………………………..………..... 9

Overlying Project ………………………..………..............................……….. 10

[Chapter 1: Introduction](#part0010.html_9H5K0-397c330900cd4534952763229706e0c7) ………………………..………..............................………………… 11

About Java ………………………..………..............................……………………….. 11

How to Read this Book ………………………..………..............................………..... 11

Integrated Development Environment …………..…………..………............ 11

Supporting Code ………………………..……….............................................. 12

Side Notes ..………………………..………..............................……………….. 12

Inline Code ..………………………..………..............................……………… 12

[Chapter 2: Learning to Read and Write](#part0012.html_BE6O0-397c330900cd4534952763229706e0c7) …………………………………................................ 13

Variables …………........................................................................................................... 13

Datatypes ...…….............................................................................................................. 15

Comments …….....................................................…....................................................... 17

Naming Conventions …......................................................………................................ 19

Operators …..………........................................................................................................ 22

Learning by Googling ...................................................................................................... 26

**Java for Humans**

7

[Chapter 3: Learning to Classify Data](#part0029.html_RL0A0-397c330900cd4534952763229706e0c7) …………………………………………………….. 30

Classes and Objects ………………………………………………………………... 30

Static Fields & Methods …………………………………………………………… 34

Control Flow Statements: Decisions ……………………………………………... 38

Methods …………………………………………………………...………………... 42

Dot Notation …………………………………………………………...…………... 47

Access Modifiers & Encapsulation ………………………………………………... 48

[Chapter 4: Learning to Manipulate Data](#part0052.html_1HIT80-397c330900cd4534952763229706e0c7) ………………………………………………….. 53

Generating Random Numbers ……………………………………………………... 53

Control Flow Statements: Loops …………………………………………………... 56

String Manipulation ………………………………………………………………..... 62

Input and Output (I/O) …………………………………………………………….. 68

[Chapter 5: Learning to Build](#part0072.html_24L8G0-397c330900cd4534952763229706e0c7) ……………………………………………………………….. 73

Class Inheritance ……………………………………………………………….......... 73

Abstract Classes and Interfaces …………………………………………………….. 78

[Chapter 6: Learning to Organize](#part0085.html_2H1VQ0-397c330900cd4534952763229706e0c7) …………………………………………………………... 86

Data Structures …………………………………………………………………........ 86

Arrays …………………………………………………………………........... 86

Lists …………………………………………………………………............... 92

HashMaps …………………………………………………………………..... 95

Polymorphism ………………………………………………………………….......... 99

[Chapter 7: Applying Knowledge](#part0103.html_3279U0-397c330900cd4534952763229706e0c7) ………………………………………………………….. 104

Building a Fighting Game …………………………………………………………. 104

Conclusion ………………………………………………………………….............. 106

Fun Projects ……………………………………………………………….... 107

Making Money ……………………………………………………………... 107

Final Words ………………………………………………………………..... 108

**Contents**

8

**Preface**

String author = "Lincoln W Daniel";

String bookTitle = "Java for Humans";

System.out.printf("Hello, World! My name is %s, author of %s.", author, bookTitle);

Hello, World! My name is Lincoln W Daniel, a software engineer studying computer science. My passion is in developing software to enable people. I am writing to teach aspiring programmers/coders how to learn Java, my favorite language, in a way people can easily understand and relate to.

**About the Author**

Lincoln is not a PhD and wasn't born with a knack for math. Nonetheless, in a little over a year of practicing software engineering, programming, coding, or any other term you may know it by, Lincoln managed to interview with companies like AirBnB, Pandora, Box, and LinkedIn. Further,[ ](https://medium.com/p/5d0e1cf98b0f)He has received internship offers from some of the more notable companies, including NASA JPL, IBM Watson, and A Medium Corporation among others. Lincoln learned and has reached this point in his young career by doing — building. Nonetheless, Lincoln believes there is great value in books that can effectively teach beginners how to learn something in a language they can understand.

When it comes to teaching, Lincoln looks at it this way: the more you teach others a skill, the better you become at that skill. As a tutor and teaching assistant, Lincoln helps students understand concepts by relating them to real human experiences. In Java for Humans, Lincoln employs the same method to help beginners learn how to code as students have expressed that his methods of teaching are more enjoyable and considerably more effective than others.

**Java for Humans**

9

**Motivation**

I am writing this book to teach anybody with the slightest bit of interest in computer science, software engineering, and programming/coding how to begin by learning Java, the most widely used and deployed programming language today. However, Java for Humans won't be like other coding books. My intention is to relate coding to human experiences to make it easier for beginners to learn and have a connection with Java.

**Audience**

Who is this book for? For the beginner who has never heard of Java before today, this book will get you started on the road to building your first Java application by walking you through the essential components step by step.

For those who have dipped their toes in a little bit but are feeling the coding life is a little too cold for them, too unlike what they are use to, or simply too boring to continue learning, this book is here to slowly pull you in deep. Java for Humans will help you relate coding to your life experiences so you don't feel lost. Your current knowledge will be reinforced through clearer and more thorough explanations.

*Not only can an old dog be taught new tricks,*

*an old dog can also learn how to teach old tricks.*

Finally, if you consider yourself an expert in Java or a coder of moderate skill level, Java for Humans will help you reinforce your knowledge of the basics of Java that you may be forgetting. Further, as experienced programmers, we are always learning from one another. Java for Humans will provide you inspiration for new ways of teaching your craft to others who may be beginning and those who need a refresher.

Who isn't this book for? Anybody who knows oneself to be closed to new ways of thinking, this book is not for you. If you do not fall in one of the groups in “Who is This Book For”, this book may not be for you, yet. However, do feel free to embark on this journey with me.

**Learning Goals**

By relating programming/coding to your human experiences, Java for Humans will teach you all of the concepts listed in the table of contents. Some of the more noteworthy ones include how to create a class, using encapsulation, using methods and variables, datatypes and data structures, interfaces, and the great polymorphism. You will also learn best practices, design patterns, tips and tricks for programming in Java.

Not only will you learn the above topics, I will teach you how to learn far beyond what any book can ever teach you. You will learn how to use Google & StackOverflow to learn more when

**Preface**

10

you're stuck. I will teach you how to learn through doing research, building things, breaking things, and fixing things as you go. Some call this the act of building a plane while you are in midair, but I call it the process of learning by doing. It is one of the most effective ways of learning how to do anything, especially programming.

**The Overlying Projects**

I believe in having fun while learning. Towards the end of the book, you will use all of the wonderful skills and super powers you develop to build and play a little fighting game in Java.

**[ModernNerd Video Series](https://www.youtube.com/channel/UC_zTAq-3TIfGqvoB_U6Peyg)**

Because some people may learn better by hearing the explanation rather than reading it, I am publishing a video series on Java for Humans on my Youtube channel, ModernNerd. I will publish those videos as time permits, so please [subscribe to the channel](https://www.youtube.com/channel/UC_zTAq-3TIfGqvoB_U6Peyg) to receive updates as I post new videos.

**Java for Humans**

11

**Chapter 1**

**Introduction**

**About Java**

Put simply, Java, named after coffee, runs the world. There are more than three billion devices running Java today, according to [Oracle](http://oracle.com/). This is only possible because Java is a portable language thanks to the Java Virtual Machine (JVM). The JVM allows Java developers to write code and compile it on one platform and run it on many other platforms unlike other languages. This has allowed Java to become a powerhouse in the programming world. Google caught on to this and swiftly made Java the language that runs your Android phone. Java is in everything and you've been using it since you were surfing the web in the good ole America Online dial up internet days.

Java for Humans will help you learn how to build the cool tools you use everyday. With knowledge of programming in Java, you can start building Android applications and games for phones, televisions, and tablets. Furthermore, not only will you be able to build with Java, you will be better prepared to learn more programming languages to increase the range of applications you can build from car to drone software.

If you need more motivation to learn Java, read the *Applying Knowledge* chapter to learn more about what you can do with Java, how much you stand to gain from being a Java programmer, and how Java for Humans can get you started on the path to a promising career in Java software development.

**How to Read This Book**

After this chapter, we will embark on a journey together. You will learn many new concepts that will help you become a talented Java programmer. Before we begin, this section covers some things we should settle to ensure our journey is smooth, peaceful, and stress free.

**Integrated Development Environment (IDE)**

This book will make use of Java 8, version 1.8.0_51, and you need a program to run the supporting code/programs. To learn Java, you will need to do a good deal of Googling, so let’s start now. Search Google or Youtube for how to install and use the NetBeans IDE along with Java 1.8 from Oracle. I would explain how to do it, but my explanation may not work for everyone because there are many different operating systems the readers of this book may be using. A great starting point is to visit the official website for Java resources: you can download both NetBeans and the most recent Java version from [this link](http://www.oracle.com/technetwork/articles/javase/jdk-netbeans-jsp-142931.html).

**Introduction**

12

**Supporting Code**

A great way to read this book is to also have the supporting source code for each chapter opened in your IDE. There will be increasingly large amounts of code in the remaining chapters of this book, but much of it will be omitted from the text to keep the chapters short. If a chapter appears long, it is likely that a considerable amount of it is code, not plain text, so hang in there.

Each chapter’s supporting source code can be found in its own namesake package under the source (src) folder. Download [the full project here on GitHub](http://javaforhumans.com/code) but remember to type out all of the code yourself in order to effectively learn the Java language. From the root folder, navigate to “src” and then choose the chapter you want to view.

**Side Notes**

We will cover many concepts throughout this book. While I will take my time to explain each concept clearly and in ways you can relate to, there may be times when I need to explain other concepts with more jargon or deeper explanation to help you better understand. In those cases, you will see the following formatted text:

***Note!***

This is a side note which explains an aside. An aside is used to indicate that one is shifting from one topic or tone of discussion to another.

You do not have to read side notes, but it would be in your best interest to do whatever it takes to fully understand the concepts discussed in this book. If you do that, you will be well on your way to being a well equipped Java programmer.

**Inline Code**

There will be inline code in this book that you should refer to while reading. They look this this:

String bookTitle = "Java for Humans";

If we want to print something out to the console for the user to see, we will do something like this:

System.out.println(bookTitle);

***Output***

*Java for Humans*

**Java for Humans**

13

**Chapter 2**

**Learning to Read and Write**

**Variables**

There are some concepts in Java, or any programming language for that matter, that you cannot go without understanding and using. Variables are one of those concepts, but don’t worry because it’s also one of the simplest concepts in Java. By the end of this chapter, you’ll understand all you need to know about variables to start storing all of life’s information for later use.

**Why Variables are Important and Useful**

Before we start on Java and its variables, we first need to assert why we program:

*We program to capture and manipulate information (data)*

*to produce new information for users to consume.*

That data can be how much money is in your bank account or the pass code to access it. It could be how many classes you have this week and each course could have more data that says what its title is, who the teacher is, and what its about. That data could even be a picture on Instagram, how many times its been double-tapped, and who owns the picture. Or, a more fun example is data about the release angle of your Angry Bird and where it’ll land on the tower to knock it down. All of that data has to be stored somewhere in order to be manipulated and displayed to you, the user. That’s exactly what variables are used for. We can store a single data point, or value, in a variable for later use. Let’s use the example of the bank account to understand why variables are important and what they are useful for.

**Using Variables to Store Bank Account Data**

Suppose we are making a new bank account. We need to store some information about the account and its owner for later use. The account will have a unique identification number, a balance, a status of whether or not it’s active, and a pass code (pin number). Further, the account will have information about the owner: the owner’s name, address and birthday. All in all, our bank account will have the following variables:

identifierbalancepass codeactive

**Learning to Read and Write**

14

owner's nameowner's addressowner's birth yearowner's birth month

owner's birthday

Now, from earlier, you know that we are able to store all of that information in a single variable to use it later. To do this in Java, we can use a *[String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html)* which allows us to store, or represent, character strings. Making a string in Java is simple. A string is an instance of Java’s String class which is provided to us.

**Single String Variable to Store Our Account Information**

Let’s make a String variable to hold our above bank account information to see how we can create and use variables:

String bankAccount = "identifier: 1234567828;

balance: 1301.78; passcode: 9889; active: true;

owner's name: Lincoln Daniel;

owner's address: 325 JavaPlace, UnitedJavas 19081;

owner's birthday: May 26, 1993";

System.out.println("Our bank account: " + bankAccount);

Now we have our whole bank account stored in that single variable which is a String. Notice that to create a variable, we say what type of variable it is, a String in this case, then give it a name, bankAccount, and finally use the equals operator (=) to set it equal to something. In this case, something is all of our bank account information. Finally, no two variables can have the same name and we’ll learn why later.

In that code block, we have a single String variable calledbankAccount that holds all of the information about our bank account. If we later want to check our bank account, we will print it to the system and see that our account’s identifier is 1234567828, balance is 1301.78 dollars, passcode is 9889, its true that it’s active, the owner’s name is Lincoln Daniel, the owner’s address is 325 JavaPlace, UnitedJavas, 19081, and the owner’s birthday is May 26, 1993.

But what if we leave the bank and come back and just want to know what our balance is? That single variable won’t be able to give us our account balance alone. Instead, it’ll give us all the information about our bank account. That is bad for many reasons. Imagine going to the ATM and having all of that information about you and your bank account displayed on the screen for the guy behind you to peek at. That would not be safe.

In the *Datatypes* section, we will learn about datatypes in Java and how we can use them to store each individual data point about our bank account in seperate variables so that we can later

**Java for Humans**

15

manipulate and use each one individually.

**Datatypes**

Java datatypes have a simple purpose and that is to store different types of data in appropriate variables for efficiency in later use. Look at it in the case of a dog and an apple. Your dog is an animal and your apple is a fruit. You wouldn’t try to do the same things with your dog that you would with your apple, would you? Not sure? Try to make your apple bark. Another fortune of datatypes is predictability.

**Why Datatypes are Important and Useful**

Datatypes give our data the power of predictability. If you have a dog, you know for a fact that it can bark, so it would be okay to ask it to do just that. If you have an apple, you know for a fact it is okay to eat it because that’s what apples are for. But what if someone wrapped an apple in a dog suit and gave it to you without you knowing? You would try to make that dog bark, but nothing would happen. You would try to take it for a walk and it wouldn’t move. This is the same idea with datatypes in Java.

You can’t count with a String because strings represent characters that make concepts like words and stories like the one you are reading now. On the other hand, you can count with integers. However, if you try to make a word with an integer, nobody would understand it because integers only represent numbers.

We can use this same logic towards data in Java. If you store your data in variables of appropriate datatypes, you will be able to safely use them as you wish later because you know exactly what type of data they are. Let’s see how we can use datatypes in Java to store our bank account information more efficiently.

**A Better Way to Store Our Bank Account Information**

Remember that variables are useful for storing information for later use and manipulation. We want it to be easy to get only the information we need, use it as we want, and move on. Given that, we do not want to store all of our information in a single variable. Let’s see how we can make this better.

So we have nine pieces of information about our account that we have to store in variables. It helps if we first understand what types of data we are trying to store:

identifier is a numberbalance is a number with a decimal point (floating point number)pass code is a numberactive is a true or false valueowner’s name is a character stringowner’s address is a character stringowner’s birth year is a numberowner’s birth month is a character stringowner’s birthday is a number

**Learning to Read and Write**

16

Now that we know what types of data we need to store, let’s see how Java can help us. Java has primitive data types for us to use to store our information. We can store numbers as int variables,floating point numbers as double, and true or false values asboolean.

If we wanted to store a single character in a variable, we could use the char primitive type. Along with those primitive types, Java also allows us to store character strings in String variables. There are four more primitive data types provided by Java, but they are not necessary for beginners.

**Store Each Piece of Data in its Own Variable**

Let’s make nine individual variables to store our bank account’s nine individual data points:

int id = 1234567828;

double balance = 1301.41;

int passCode = 9889;

boolean isActive = true;

String ownerName = "Lincoln W Daniel";

String ownerAddress = "325 JavaPlace, UnitedJavas 19081";

int ownerBirthYear = 1993;

String ownerBirthMonth = "May";

int ownerBirthDay = 26;

System.out.println("Our bank account's balance: " + balance);

***Output***

*Our account's balance: $1301.41*

Now we have our bank account and all of it’s data is stored in variables with their appropriate datatypes. Given our new setup, we can manipulate parts of our account more easily without having to deal with parts we don’t want to. The bank teller can find our account by looking up it’s id, which is 123456782, and ask us to verify the ownerBirthday on the account to make sure we are the owner of the account before telling us our balance. Later we can go to the ATM use our passCode to view our account’s balance. We can even change our balance by adding money to it or taking money out.

We can do all of these individual data manipulations because we have our data separated in appropriately typed variables. It’s pay day, so let’s update our account balance:

balance = balance + 600.50;

System.out.println("Our account's new balance: $" + balance);

***Output***

*Our account's new balance: $1901.91*

After adding $600.50 to our account’s balance, it went from $1301.41 to $1901.91 and is

**Java for Humans**

17

represented in our balancevariable. As we learn more awesome Java concepts, we’ll see our account balance increase considerably. It definitely pays to know how to increase your account balance.

**Comments**

If you have the best memory in the world, you might be able to remember everything you do, why you do it, how you do it, and when you do it. You may even be able to tell people about your experiences when you are near them. If that is the case, you are very much fortunate. However, what about when you’re not nearby? How will you and others remember what you did to get a line of code to work and what it’s supposed to do? Queue the computer.

**Why Comments are Important and Useful**

Computers are the best at remembering information you give it and sharing that information with others when you’re not around. The folks who designed Java put this principle to good use for the sake of efficient programming. Java allows you to make comments in your code to help you and your team remember what your code does. It is very useful for every bit of code that people may have a hard time understanding. The best part of comments is that they will not be compiled by the compiler. In other words, comments don’t affect the execution of your code. They are like thought bubbles.

Your goal as a programmer is to write clean, effective, and human understandable code. Comments will help you more easily accomplish writing human understandable code. As you get better at coding and begin building large projects with complex algorithms, you will want to make extensive use of comments to later remember what your code does and be able to easily and effectively explain it to others. This is great coding style. Let’s see what kind of comments are available for us to employ in our code.

**Single Line Comments**

Single line comments, like the one above, allow you to write quick comments to explain bits of code as you go. These comments are great for explaining your variables and their declarations.

//This is a cool single line comment

**Learning to Read and Write**

18

Single line comments must start with double forward slashes // and can only span a line of code. Let’s refer to our bank account example from the Datatypes chapter to see how we can make use of single line comments for variables:

//this is the account's unique identifier

int id = 1234567828;

//this is the account's balance

double balance = 1301.41;

//this is the pass code to access the account

int passCode = 9889;

**Multi-line Comments**

Single line comments are great for commenting little bits of code when there’s not much to explain. However, when you write larger code, it’s best to use multi-line comments. Multi-line comments allow you to write long comments that can span for multiple lines by starting with “/*” and ending with “*/”.

/*This is an even cooler comment.

It can span multiple lines*/

Imagine you are writing a program to represent an ATM and you want to let the user use the ATM as long as they don’t type “EXIT”, you’d want to clearly explain how you intend to do that in your code. Doing so will require multiple lines, but it will also allow you to get all of your thoughts across:

//Scanner to get user input from keyboard

Scanner scanner = new Scanner(System.in);

//String variable to hold the user input

String input = "";

**Java for Humans**

19

/*

While the user does not want to exit,

let them continue making transactions

on our ATM.

*/

while(!input.equalsIgnoreCase("EXIT")){

//let the user make transaction on our ATM

//then ask the user what they want to do next.

System.out.println("Enter EXIT to exit or another action");

//get user's input from scanner

input = scanner.nextLine();

}

System.out.println("Thanks for using our ATM!");

Notice how we used multiple lines to explain our while-loop which does a lot of work. This will help us and others who read our code better understand what is happening.

Don’t worry if you don’t yet understand what’s going on in that code snippet due to thewhile loop and Scanner. We’ll go over those concepts soon. For now, play around with the supporting code to see how it works.

**Naming Conventions**

Remember when you were in the first grade and you had to write your first sentence? The teacher said your sentences must include a subject and a verb. Earlier, she made sure to teach everyone what a subject is and what a verb is so that she could later use it to communicate new ideas, like sentences, with confidence that everyone would understand her. At this point, she was able to tell you how to structure your sentences:

*“All sentences must start with a capital letter and end with a punctuation.”*

She continued to explain the different types of sentences you can write along with each one’s appropriate punctuation:

*“Statements end with a period and questions end with a question mark. Sometimes, we get excited when we say things, so we can use an exclamation point to show how excited we are!”*

That is a great teacher. She taught you the conventions of speaking English so that you could effectively communicate your thoughts with your classmates, parents, and the rest of the world in

**Learning to Read and Write**

20

a way everyone who understands English can comprehend. We do the same thing in Java and every other programming language so others can understand our code.

**Why Naming Conventions are Important**

When programming, you have three goals: design and build software that work, follow the conventions of the language, Java, so others can understand your code and work with you, and document your code through comments so that you and others can understand and manipulate it later. Before moving forward, it’s important that we take some time to learn the conventions of Java. By doing this, we will be able to design and build better software with code that others can understand and collaborate. While there are a number of conventions to follow, we will focus on the ones that are most important for beginners to grasp.

**Java Naming Conventions**

**Variable Naming**

What’s allowed? Variables in Java are case sensitive and can be of unlimited sequence of letters and numbers. However, variable names must start with a letter, underscore character “_”, or a dollar sign “$”.

String author = "Lincoln W Daniel";

String bookTitle = "Java for Humans";

int yearBookPublished = 2016;

What's the convention? While you can start with a underscore or dollar sign, the convention for naming variables in Java is to always start with a lowercase letter. To help make your code self-documenting, you should use full words to name a variable instead of single letter; variables named day, month, and year, for example, are more intuitive and readable than their abbreviated versions d, m, and y respectively.

If your variable name consists of more than one word, start the first word with a lowercase, but capitalize each subsequent word. This is called camel case in reference to a camel’s back; variables use lower camel case because the first letter of the variable name is lowercase. Take the variables nameOfParent1 and nameOfParent2 which hold the names of your first parent, perhaps mom, and the name of your second parent, dad. Those variables consist of three words and a number written in lower camel case.

Another convention is to never use the dollar sign in your variable names. It’s better to stick with words and numbers. The underscore character is also discouraged in most cases of variable naming. Things get a little different for naming constant variables, though.

The previous variable naming conventions apply for variables that will likely change their values during execution of the program, your code. However, when you need a variable that holds a constant value, you should use all capital letters with underscores separating each word. This way, it is clear to you and everyone who reads your code which variables can change and which can’t. If we want to write a calendar program, we will have a couple variables that change values, the current day

**Java for Humans**

21

and month, and a couple that are constant, the number of days in a year:

static final double NUMBER_OF_DAYS_IN_YEAR = 365.25;

static final int NUMBER_OF_WEEKS_IN_YEAR = 52;

String currentDay = "Tuesday";

String currentMonth = "May";

int currentWeek = 24;

The static keyword will be explained later, but it’s important to know that the final keyword means the variable’s value cannot change after it has been set: we will always have 365.25 days in a year. Such a variable is often called a constant because its value remains unchanged throughout the life of your program.

One last convention for now is your variables cannot match and should not resemble keywords that are reserved for Java such as int, double, for, while, and others that can be viewed here. But don’t worry, Java won’t let you make that mistake.

**Class Naming**

We'll only discuss the conventions for this one because as far as we are concerned, other methods of naming classes are evil and should be avoided. We haven’t talked much about classes, but I will go over them more later. For now, just know that when naming classes, you should use whole words like in variables. However, class names should employ upper camel case: the first letter of every word in the name of a class should be capitalized. Take a class that holds information and functions of a human for example. We should name such a class *Human* because that is descriptive of what the class is for and what kind of objects can be created from it*.*Another class may hold information and functions of a game character, say a fire archer; we should name it *FireArcher:*

public class FireArcher {...}

**Method Naming**

Method names, like variables, should use lower camel case with a mix of words and numbers. Further, a method’s name should consist of verbs that say what it does.

public int add2Numbers(int firstNumber, int secondNumber) {

int sum = firstNumber + secondNumber;

return sum;

}

Anyone who knows Java will be able to tell that your method, add2Numbers, takes two integers, adds them together, and returns the sum.

That’s it for now. We will learn more conventions as we learn more about Java. Follow all of

**Learning to Read and Write**

22

these conventions and you will write code that everyone wants to work with because they will be able to understand and help you.

**Operators**

Now that we understand how to make variables, the different datatypes available to us in Java, and how to write code others can understand, let’s try to manipulate some data with Java operators.

**Why Operators are Important & Useful**

Remember that we program to capture and manipulate information, data, to create new data for users to consume. We’ve learned how to capture data and store it in variables, so this chapter will focus on manipulating our data. We manipulate our data by running operations on it by with operators. Operators allow us to assign data to variables, do math with data, connect data, and compare data.

There are an infinite number of operations you can run on your data with only a small, finite number of operators available to you. This is both good and bad. Bad because you are limited to how many ways you can operate on the data you have. Good because you only need to remember a few special symbols that let you manipulate your data. On the plus side, you can combine the few operators you have to do an infinite number of operations.

Java provides us 42 operators to work with. Twenty-seven of the operators are mere combinations of the fifteen base operation symbols. More good news is you only need to know a few of those to begin working with Java. Many experienced programmers don’t make use of all of them, so don’t worry if you don’t understand them all at first. I will equip you with the most widely used operators so you can begin building fun and useful programs. You’ve seen a good number of Java’s operators being used in this book already, but let’s take a look at the ones you need to remember.

**Java Operators**

**Assignment**

When you were learning how to create and use variables, you saw the assignment = operator used countless times. As I would say, “my name is Lincoln,” to tell people what my name is so they can use it later to refer to me, the equals symbol is used to set a variable equal to a piece of data for later use.

//use = to set a variable equal to my name

String myName = "Lincoln W Daniel";

System.out.print(myName);

***Output***

*Lincoln W Daniel*

**Java for Humans**

23

**Additive**

Additive operators enable us to do addition and subtraction much like you learned in the first or second grade of school. The only difference is you don’t have to do any of the hard work like carrying numbers because Java does it for you. You will often use the addition + operator to add numbers or connect data and the subtraction *-* operator to subtract numbers. Another use of the plus symbol is for concatenating, or connecting, data:

//use + symbol to add two numbers

int numApples = 100;//"num" means "number of"

int numOranges = 10;

int numFruits = numApples + numOranges;

/*use + symbol to connect, concatenate, strings*/

String firstName = "Lincoln";

String lastName = "Daniel";

String fullName = firstName + " " + lastName;

//use - symbol to subtract two numbers

int four = 9 - 5;

//use + to concatenate all of our data to print a statement

System.out.println(fullName + " has " + numFruits + " fruits.");

***Output***

*Lincoln Daniel has 110 fruits.*

String concatenation is useful when you want to connect multiple character strings together or connect other datatypes with strings as we see in that code snippet. When we concatenate an *int* with strings, the *int* is converted into its String representation; that is also the case for any datatype that is not a String.

**Multiplicative**

Multiplicative operators let us do multiplication and division on numbers like we learned after first grade. The computer handles all of the long division and carrying for us. You can make use of the multiplication * operator to multiply and the division / operator to divide numbers:

//use * to multiply two numbers

int oneHundred = 20 * 5;

//use / to divide two numbers

int six = 12 / 2;

**Learning to Read and Write**

24

**Equality Operators**

We often want to know if two things are equal to or not equal to one another. A classic example is checking if an apple is equal to an orange. We can evaluate equality relationships by use of Java’s equality operators: == lets us check if two things are equal while != lets us check if two things are not equal. Let’s try our apples and oranges example by using numbers to represent the two:

int apple = 1;

int orange = 2;

boolean appleEqualsOrange = apple == orange;

boolean appleEqualsApple = apple == apple;

boolean appleDoesNotEqualOrange = apple != orange;

System.out.println("Apple does not equal orange: " + appleDoesNotEqualOrange);

***Output***

*Apple does not equal orange: true*

Here, the first boolean variable, appleEqualsOrange, will be set equal to false because the comparison made by the equality operator is false — an apple represented by the number one (1), does not equal an orange, which is represented by the number two (2). However, the last two booleans will be set equal to truebecause the comparisons made by the equality operators in the last two lines are evaluated to true; an apple (1) is equal to another apple, and an apple (1) is definitely not equal to an orange (2).

**Relational Operators**

Like in math, we can use relational operators to compare, or gauge the relation between two data points in Java. We can check if one data point is greater than or less than another by using the> or < operators respectively:

int one = 1;

int two = 2;

boolean twoIsGreaterThanOne = two > one;

boolean oneIsLessThanTwo = one < two;

Both of those boolean variables will be set to true when the code is executed because the comparisons made by the relational operators are true. Further, we can check if a data point is *greater than or equal* *to*another as well as if a data point is *less than or equal* *to* another by use of the

**Java for Humans**

25

***>=*** and ***<=*** operators respectively:

int three = 3;

int twenty = 20;

boolean threeIsLessThanOrEqualToTwenty = three <= twenty;

boolean twentyIsGreaterThanorEqualToThree = twenty >= three;

boolean oneIsLessThanOrEqualToOne = 1 <= 1;

boolean twoIsLessThanOrEqualToOne = 2 <= 1;

System.out.println("Two is less than or equal to one: " + twoIsLessThanOrEqualToOne);

***Output***

*Two is less than or equal to one: false*

The first three boolean variables will be set equal to true because the comparisons made by the relational operators are true. However, the last one will be false because we all know two is not less than nor equal to one. In later chapters, we will learn how to use our equality and relational operators to make decisions and control the flow of our code.

**Combining Operators**

We can combine operators to make more powerful operators, too. With combined operators, we can clean up and optimize our code. We can increase or decrease the value of a variable by doing the following:

int count = 0;

/*Combining Additive Operators

& the Assignment Operator*/

count++; //count now equals (0 + 1) = 1

count += 6; //count now equals (1 + 6) = 7

count--; //count now equals (7 - 1) = 6

count -= 2; //count now equals (6 - 2) = 4

/*Coming Multiplicative Operators

with the Assignment Operator*/

count *= 5; //count now equals (4 * 5) = 20;

count /= 10; //count now equals (20 / 10) = 2;

**Learning to Read and Write**

26

The ++ operator says, “I see your current numerical value and raise it by one,” while the -- operator decreases the current value of a variable holding a number by one. The += operator adds the number on its right to the value of the variable on its left and saves the sum in the variable; the -=, *= and /= operators work similarly.

**Others**

There are a few others that are useful, but they require more explanation than is within the scope of this chapter. In later chapters, you will learn how to logically check conditions of data by combining relational and equality operators with logical operators in order to make decisions with control flow statements (decision-making statements and looping statements). These are powerful tools that allow our code to do some things sometimes and other things other times.

**Learning by Googling**

The beauty of the computer science, software development and engineering industry is that we enjoy sharing. We like to share knowledge, code, talent, and anything necessary to advance technological innovation in our world.

I’m a strong believer in learning by doing. Try to build some things and do some Google queries to fix whatever you break. One of the best ways to learn how to code is to dive in and build something from the ground up. Use the resources available to you to facilitate and expedite your learning process. When you get stuck, stand on the shoulders of the giants who came before you to get yourself back on the road to success. In this chapter, we will take a look at how you can take advantage of your resources to teach yourself how to code beyond what any book or tutorial can teach you.

As humans, we are limited to only accumulating and maintaining a limited amount of knowledge. It is important to realize that the world’s knowledge is infinitely large and that extends to our knowledge of programming languages and techniques. For that reason, the ability to learn is far greater than possessing all of human knowledge at any given moment in time without being able to learn more as it expands.

As you learn and go through your career as a software developer, you’ll have to continue learning. I’ve worked with incredibly smart people from my college professors to my leaders at companies like IBM and they all share two things in common: they’ve had decades of programming experience and they still Google when they get stuck. Further, they are constantly learning new skills and concepts. If they, experienced as they are, are still learning, it’s clear that we all should continue learning.

When I was learning how to program, I decided on a project to build and then took to Google to learn how. This has proven to be the best way for me and a popular method across the industry because others have asked the same questions I’ve sought answers to.

In the Java for Humans book, we will cover every necessary concept of Java to get you up and running. We will step through clearly to help you understand and relate to every concept. However, there may be times when you need more explanation for the concepts that are beyond the scope of the book. In those instances, I may suggest you do further research of a concept on Google when I

**Java for Humans**

27

cannot go deeper. Furthermore, you may find it necessary to get another person’s look at some of the concepts we cover in this book. For those cases, you will need to ask your questions in Google effectively in order to get the right answers. Let’s take a look at effective methods of getting the answers you need.

**How to Google**

Often, when you have a question, you simply visit Google and type it in the same way it popped up in your mind:

*Google: How do I take over the world?*

That query may return some good results, but the results will vary largely. If you want to make sure you get the answer you want or get close enough, you need to provide Google a bit more information. May be instead of the previous wording of your query, you can try this:

*Google: How do I build a bank?*

You wanted to know how to take over the world, but Google doesn’t know how you want to do that. If you’ve observed the world enough, you may notice that banks have a great stronghold on the world. With that prior knowledge, you’d be better off asking Google how to build a bank. Let’s try another query.

**Code Queries**

Sometimes, you forget something when you are coding. Sometimes you don’t know how to code something. Let’s say you wanted to learn more about how to make variables. You could ask Google the following query:

*Google: how do I make variables?*

Again, Google would return many results, but the large majority may not be what you are looking for. This is because Google doesn’t know you intended to learn about Java variables, not variables in other programming languages. A better query may be one that tells Google that you want results about Java along with the type of variable you want to make:

*Google: how do I make String variables in Java?*

That query will return a much better set of results for you to learn from. Still, what if you spend a whole day coding and end up performing twenty Google queries? Typing out all of those words will be more time consuming than they have to be. In coding brevity is often the key to success and this is true for Googling, too:

*Google: make String variable Java*

**Learning to Read and Write**

28

Use the minimal amount of words as you can and forget the question mark. Google is smart enough to know that you want results surrounding String variables in the Java programming language. Now, let’s take a look at the results returned.

**Code Results**

At its core, Google is a software company. They built a good deal of the code bases that we all use today, so it makes sense for them to understand that we want to get the best code search results as possible. Aside from Google’s possible bias towards good code results, so many people are programming today that many of the questions you will have will already be answered many times and discussed in depth on forums like StackOverflow. With that said, let’s digest the types of results you’ll receive and which are best in particular situations.

In the case of Java, the official documentation will come from [Oracle.com](http://docs.oracle.com/javase/8/docs/api/). Oracle maintains the Java language and has the final say on what is right or wrong. Although these guys have the ultimate say on what is right, they don’t have a good way of laying it out for beginners. It’s organized well, but as a beginner, you may be a little intimidated by its layout because it contains more jargon than you may be comfortable with. Nonetheless, if you want a definitive answer to your Java questions, Oracle’s Java documentations is your best bet. This is the case for any other language, too: the official documentations will provide you the most accurate answers. If it’s accuracy you seek, use this search result. If it is comprehension you care for, forums like StackOverflow will serve you well.

[StackOverflow.com](http://StackOverflow.com) is the most popular forum for software development related discussions. On here, users can ask questions and receive answers from other users. Those answering questions, have likely ran into the issues of the questions they answer and are experienced in the fields of the questions. Moderators maintain the forum to make sure people are asking relevant questions and receiving the best answers. Users vote on the answers provided by other users on questions and the best answer is selected by the user who posted the question. It is safe to say that at least eighty percent of the questions you, a beginner, will have are already answered on StackOverflow. Google knows this and readily serves you StackOverflow results for your queries. Sometimes, the most popular, or “accepted”, answer may not be the best answer for you, so be sure to look through the other answers and pick the one that best answers your question. This is a good first step in finding answers to most of the questions you will have as you learn a programming language.

Vloggers on [YouTube.com](http://youtube.com) are another phenomenal source of knowledge. If you are brave enough to put yourself on the air for the world to watch, there’s a good chance you know what you are talking about when it comes to coding. If you want to listen to someone explain the answer to your question and show you visually how to resolve any issue, this is a great place to go. Youtube happens to be the second largest search engine, and because Google owns Youtube, you can search your questions in there the same way you would at Google.com. Good ways to judge if a video is worth watching are to scan the comments before watching, look at the up votes to down votes ratio, and examine the amount of views it has in that order.

Some say the YouTube vlogger killed the blogger. That notion can be argued, but either way, the blogger is still thriving when it comes to code. Bloggers often have the code you need available followed by a thorough explanation of each part of the source code, so the answer to your questions

**Java for Humans**

29

can often be gathered from a blog post. However, be sure to check for any feedback the post may have received from other readers and use that to gauge whether or not the content of the blog is worth listening to. Sometimes, other people will comment praise of the blog article, and other times, people will challenge the validity of the information provided in the blog. This makes your job as a learner easier because you can use this to make sure you are getting the best answers without spending too much time reading.

Over all else, remember that, contrary to popular belief, no one ever built anything from scratch and that nobody is self-made. We all need help to get where we want to be. Together, we can all advance the knowledge of society in all that we do. Start by building something and continue by asking the right questions when you get stuck.

In the following chapters, you will learn everything you need to get started building your very own Java applications. Be sure to use what you have learned in this section to research concepts you need more explanations for. Finally, always be coding. Always be building. Always be learning. Always be teaching. Always be searching for a better way. You may be the one to lead us to the next technological revolution. Here we go!

**Learning to Read and Write**

30

**Chapter 3**

**Learning to Classify Data**

**Classes and Objects**

In your life, you’ve learned about many types of animals, people, buildings, sports, schools, and so on. In English class, we refer to these “people, places, or things” as nouns. In Java, we can refer to them as objects — you can think about objects in Java as you do about nouns in English.

Java programs revolve around objects like English sentences revolve around nouns. You can describe a noun with adjectives and you can describe an object with fields, otherwise known as attributes or instance variables. Nouns perform actions with verbs just as objects perform actions with functions, or methods.

As you know, there are three base types, or classes, of nouns — people, places, and things — and from those, you can make infinitely more classes of nouns. Java has a similar idea. There’s a single base class of objects from which we can make infinitely more classes. In this chapter, you will learn what a class is in Java and how you can make an object from a class.

**Why Classes Are Important & Useful**

Java is the most widely used object-oriented programming(OOP) language in 2016\. OOP is a programming model based on the concept of “objects” which are simply data structures that have fields, or attributes, that hold information (data) about themselves and methods they can perform. The attributes of an object are variables that hold information, or data, about the object while its methods are ways the object can manipulate its data to create new data. This is important because we can use this idea of structured data to write clean, flexible, and maintainable code.

While everything in Java is not an object, most things revolve around objects in Java like the contents of an English sentence revolve around the noun(s) of the sentence. For this reason, it is important for us to know how to create objects and make use of them. This is where classes come in.

A class in Java is simply a template for creating objects with similar attributes and behavior. A Java class can be thought of as a template that defines the attributes and behavior that objects constructed from it can exhibit. With that, we can say an object is merely an instance of a class. From a single class, we can create, or construct, many instances and each instance has the attributes and functionalities that every other instance of the has. Thus, a human is an instance of the Human class, and at the time of publication of this book, there are seven billion instances of the Human class in the world.

**Making Objects From Classes**

Making a class in Java is easy. There are three key parts of every class but only one is always necessary. A class can have fields, or attributes, methods, or behaviors, and must have at least one

**Java for Humans**

31

constructor. We can create a class that defines the attributes and behavior of humans like this:

public class Human {

//TODO: add attributes

//TODO: add constructor

//TODO: add methods

}

There, we created a simple class called Human. The *public*keyword at the start of the first line means the class can be accessed from anywhere in your program and the name of the class is in *upper camel case*. Between the opening curly brace (**{**) and the closing curly brace (**}**), we have to define attributes any object, or instance, constructed from this class can have and methods it can perform. Now, before we can create objects from this class, we will need to finish defining it.

**Class Fields: Instance Variables**

Fields are variables which hold data that describe the attributes of the class and any object constructed from it. Fields that a human would have are its name, age, and height. We add fields to a class by declaring them at the top of the class like this:

public class Human {

String name;

int age;

int height;

...

}

These fields will hold information about every instance of our Human class, but they do not yet have the information because the class is simply a template. We need to create a constructor which will allow anybody who calls it to pass in the necessary information about the instance of the Human class they are constructing. At the time of constructing an instance of the class, we will assign the given information, values to the instance variables of the instance.

**Class Constructor**

A class must have a constructor which is used to create a new object from the class each time it is called. Every object created from a class is referred to as an instance of that class. A constructor is simply a method that can be called from different parts of your program to create instances of a defined class.

Although we have not covered methods, yet, it is good to know that methods have return types that tell the caller what datatype to expect back as a result of calling the method. However, some methods don’t return anything at all. We will learn more about return types in the Methods

**Learning to Classify Data**

32

section.

The constructor has no explicit return type because it’s a factory method, which means it creates a new instance of the class and returns the new instance to the caller. The constructor of a class must have the same name as the class and is case sensitive. Finally, the constructor can accept information from the caller as parameters that will be assigned to the instance fields of the instance being created. We can create a constructor for our Human class that asks the caller to provide the name, age, and the height of the new Human instance like so:

public class Human {

...

//the constructor of this class

public Human(String name,int age, int height){

//set this object's name with the provided name

this.name = name;

//set this object's age with the provided age

this.age = age;

//set this object's height with the provided height

this.height = height;

}

}

The constructor can be thought of as the doctor who gives birth to your new object and all the doctor asks is that you fill out the birth certificate to describe your new object. The constructor’s parameters says that if anybody wants to create an instance of our Human class, they must provide a name, age, and height for the new Human instance as arguments and it will use that information to initialize the new instance’s instance variables — thename, age, and height fields. Like any other method, we can manipulate data in the constructor aside from assigning the values of our new object’s fields, but it’s good practice to keep the constructor as short as possible. Once the constructor is done creating the new object, it returns it to the caller to be saved to a variable for later use:

public static main(String[] args) {

Human newHuman = new Human("Lincoln", 22, 5);

}

The keyword *this* tells the compiler that we are referring to the current instance of the class: if we want to refer to the name field of this new Human object, we say this.nameso the compiler doesn’t confuse it with the nameparameter that is provided as an argument to the constructor method.

**Java for Humans**

33

**Instance Methods**

Remember that nouns perform actions with verbs in sentences and objects in Java programs perform actions by use of their methods. A class defines methods any object constructed from the class can perform. These methods are referred to as instance methods because they can only be performed by an instance of the class. We are all instances of the Human class, so we share functionality, or methods. We speak, run, jump, sleep, walk, wave, work, and so much more. All of these actions are predefined by our human biology and anatomy— our class.

The opening and closing curly braces define a scope: the opening starts the scope and the closing ends it. Classes and methods, among others, have scope, and the class scope is the highest level scope in a class. While we can start new method scopes in the class scope, we cannot start new method scopes in a method’s scope.

We can add methods to our classes in Java by declaring them between the opening and closing curly braces, or scope, of the class. Let’s add a few methods to our Human class to make our Human objects more functional:

public class Human {

...

//every instance of a Human can speak

public void speak(){

System.out.println("Hi! I am " + name + ".");

}

//set the age of the Human object

public void setName(String newName) {

this.name = newName;

}

//return the age of the Human object

public int getAge() {return age;}

}

We will look at methods in more detail in future chapters so don’t worry about fully understanding the details yet. All that matters right now is that methods allow objects to do things. What we did was, first, add a method that will allow instances of our Human class to speak and introduce themselves. The second method allows our Human objects to change their name when they want. This is often referred to as a setter method because it sets one of an object’s instance variables to a new value and returns nothing — void. The last method allows others to read the age field of a Human instance. This kind of method is referred to as a getter method because it gets and returns one of an object’s instance variables.

**Learning to Classify Data**

34

**Static Fields and Methods**

We’ve learned that we can create classes to create objects from. Furthermore, an object, or instance of a class, can have instance variables to hold information about itself and methods to manipulate and create more information for users. While not all concepts in Java are objects, most programs in Java revolve around objects.

We can put a good deal of functionality in our classes to organize our code and make remembering what our code does easier. When we have our classes created, we can make objects from them to store information and execute functions we need them to. It’s much like society.

Think of the world like a program. There are seven billion instances of the Human class, perhaps ten billion instances of the AppleTree class, five billion of the Car class, and so on for every object found in nature. There are some Human instances that execute medical functions to keep everyone healthy, some conduct law functions to keep us safe, and some education functions to advance our knowledge. Further, we create instances of the AppleTree class to provide us apples to eat and apple juice to drink, and we need instances of the Car class to get us where we need to go.

If we make an instance of a Car, we can choose its color and customize its speed. If we make an instance of a Human, we get to give it a name, and a unique identification number, and if we make an instance of a AppleTree, we get to choose what color the apples will be. Without instances of these classes, we couldn’t use them to their full potential and customize them as we like. Usually, we want to be able to create objects from our classes to use them in our programs, but sometimes we only need our classes to hold information and perform functions universal to the class itself. In these cases, we don’t need instances of the class to hold the information or run the functions. Such information can be held in static class fields and the functions can be static class methods.

**Why Static Fields & Methods Are Important & Useful**

The static keyword in Java can be applied to both fields and methods of a class. A field or method of a class that is static can be accessed without an instance of the class. Think of a situation where you want to store information that is the same for everyone and functions that behave the same way for everyone. A great example, again, is the Human class.

A lot of functionalities we, as instances of the Human class, perform are functionalities universal to us all. We all speak, laugh, cry, eat, and walk one step at a time. Because these functions are universal and not specific to any individual, they can be static methods. Further, our governments keep universal information about all of us in order to keep records for the future. They may record information about how many instances of humans exists in the world at any given time, how many are African, North American, Russian, European, Australian, Asian, and so forth. Other universal information may include how many of us are right handed or left handed, how many of us are male or female, and how many of us have a college degree. Such data points are universal and not specific to any one instance of the Human class, so we can store them in static fields.

**Java for Humans**

35

**Static Fields**

Because static fields can be accessed without an instance of the class, they are good means of storing information that is universal to a class, such as a count of how many instances of the class have been created. To make a static field, you simply place the static keyword before the declaration of a class’s member variable, or field:

public class Human {

public static int numHumans = 7;

...

}

Once that static field exists, you can access it from outside or inside of the class without an instance of the class. When accessing it, you can simply get or change its value as you wish. The *public* modifier means that it can be accessed from anywhere in your program that the class can be accessed from. We will learn more about access modifiers soon. Whenever we make a new instance of the Human class, we could have the *numHumans* static fieldincreased by one so that our whole program knows there’s a new human in town to work with. Because the Human class is public and so is the static field, any part of our program can access that static field by doing the following:

int numHumansInWorld = Human.numHumans;

The way we accessed the field from the class is called dot notation, and we will learn more about this in the *Dot Notation* section.

**Static Methods**

Classes have three main types of methods: the factory (constructor) method, instance methods, and static methods. A static method of a class can be called without an instance of that class. As a result, static methods don’t have any access to instance variables, or instance fields, because instance variables store information about an instance of a class. Likewise, static methods do not have access to the this keyword in Java because this refers to the current instance of a class, which is not present in the scope of a static method. Further, instance methods of a class cannot be called from static methods of that class because there is no instance of the class present in a static method. However, if an instance of the class is passed to the static method, that instance is free as usual to perform its instance methods in the scope of the static method.

Remember that we use static methods for functionality that is universal to a class. Static methods do not care about instances of the class or their state. If we have an instance of our Human class, we can call a method to make it change its name or speak its name. However, if we only want to use our Human class to run some calculations to determine the DNA of a human or to check how many humans currently exist in the world, we can make static methods to do that. Let’s try the latter:

**Learning to Classify Data**

36

public class Human {

private static int numHumans = 0;

public Human(String name){

this.name = name;

numHumans++;

}

public static int getNumHumans(){

return numHumans;

}

...

}

If we want to access the static numHumans field of the Human class from outside of the Human class this time, we must call the getNumHumans() method because we made the static field private by using the private access modifier, which means the field can only be accessed from within the class its a member of, or belongs to. This is usually a wise design pattern to ensure that your fields are only being used how we want; the numHumans field in our Human class can only be changed from within the class and accessed through the getNumHumans() static method. We can call the static method from outside or inside the Human class because it is public, and it will return to us the value of the static field holding the number of Human instances that exist in our program:

int numHumansInWorld = Human.getNumHumans();

That will return the value of the static numHumans field in the Human class and store it in the localnumHumansInWorld variable for later use.

Finally, instances of a class can call the public static methods of that class from anywhere in the program, but an instance of a class can only call its private static methods, like any other private method, from within the class. If we have a static method that simply serves to increment the static numHumans field in our Human class by one and return the new value each time it is called, it’d be best to have that declared as a private method so that it can only be called within the Human class either by instances of the Human class or from other static methods:

**Java for Humans**

37

public class Human {

private static int numHumans = 0;

private String name = name;

...

public Human(String name){

this.name = name;

incrementNumHumansAndPrint();

}

private static int incrementNumHumans(){

return numHumans = numHumans + 1;

}

private static void incrementNumHumansAndPrint(){

System.out.println("There are now " + incrementNumHumans()

+ " Human instances in society.");

}

...

}

Now when we call the constructor method of our Human class to create a new instance of it, the constructor will set the name of our instance with whatever we provide it and finish by calling the private and staticincrementNumHumansAndPrint() method of the Human class to print the new number of Human instances that exist in our program. Notice the the incrementNumHumansAndPrint() method calls on the private and static incrementNumHumans() method to do the work of increasing the number of humans by one. These functions may appear trivial and lazy now, but we’ll soon see why its smart to separate work like this.

public static main(String[] args) {

//creates a new Human instance

Human newHuman1 = new Human("Lincoln W Daniel");

//creates another Human instance

Human newHuman2 = new Human("ModernNerd");

}

***Output***

*There are now 1 Human instances in society.*

*There are now 2 Human instances in society.*

**Learning to Classify Data**

38

**Control Flow Statements: Decisions**

Decisions, decisions, decisions … Decisions are the concepts you had no control over as a baby. As you grew older, however, the world expected you to start making decisions for yourself. In school, you had to make a decision everyday to sit in the front or in the back of the room; if you sat in the back, you ran the risk of being less attentive, and if you sat in the front, you had a better chance of getting the excellent grade. When it’s raining, you have to make a decision to use an umbrella or not; if you use the umbrella, you stay dry, and if you don’t use the umbrella you get wet and sad.

**Why Decisions are Important & Useful**

In Java, your code is generally executed from top to bottom in order. Line one will be executed before line two, line three after line two, and line four before line five but definitely after line three. This is great when you are writing simple programs, but when it’s time for your programs to do more, your code will have to employ control flow statements to allow your program to do some things sometimes and other things when the time is write. One form of control flow statements are decision-making statements which allow us to tell our program to do Task Aif a condition is true or Task B if it is not true: If it is raining, use the umbrella, otherwise, leave it in the closet.

**Decision-Making Statements**

**If-Then Statements**

If this is true, then do that.

If a certain condition is satisfied, then do something. You’ve been doing this for as long as you can remember. If you are hungry, you eat. If you are tired, you sleep. If your bank account is empty, you work hard to get more money. If you get a good grade, you pass the class. If you pass “Go” in Monopoly, collect 200 dollars. This is how the if-then statement, otherwise known as if statement, works:

//previous code runs

//check a condition

if(condition) {

//body

//do something: run more code here

}

//other code runs

The condition could be a mathematical expression, a variable, or a method, but regardless of what it is, it must return, or evaluate to, a*boolean* value of *true* or *false*. If it the condition evaluates to *true*, we say that the condition is satisfied.In that code snippet, some code runs, then we use a if statement to evaluate a condition. If the condition is satisfied, evaluates to true, we can do something inside the

**Java for Humans**

39

body of the *if* statement. Let’s try to model a turn in the game of Monopoly:

Player player1 = new Player("Lucy");

//the first player rolls the dice

int movePositions = player1.rollDice();

//player moves piece on game's board

player1.moveForward(movePositions);

if(player1.passedGo()) {

player1.collect200Dollars();

}

//next player rolls dice

movePositions = player2.rollDice();

//...

Note that the rollDice() instance method of the player class always returns a perfect roll of 12 and its moveForwad() instance method increases the instance’s position on the board by the number we provide it. Finally, its passedGo() instance method returns true if the player’s position on the board is greater than 11 and falseotherwise. In the Generating Random Numbers chapter, we will learn how we can randomize the rollDice() method.

In that code snippet, the current player of the Monopoly board game rolls the dice to see how far he can move and moves his piece forward on the board accordingly. If the player passed “Go” he collects 200 dollars. After all of that, the next player gets to roll the dice, and the process repeats until the game ends.

**If-Then-Else Statements**

If-then-else statements are a little more powerful than simple if-thenstatements because they let us do things if a condition is satisfied and other things otherwise. You can think of it like so:

if this is true, then do that. Otherwise, do something else.

Let’s say we want to explore the Amazon rainforest. In planning, we check the weather forecast to see if it will be raining on the day we go. We only want to pack our umbrella in our bag if it will rain when we get there. If it’s not going to rain, we should put our umbrella back in our closet because we won’t need it. We can model our plans with if-then-else statements like so:

**Learning to Classify Data**

40

boolean itWillRain = true;

//check if it will rain

if (itWillRain) {

//pack the umbrella for the trip

System.out.println("Adding our umbrella to the bag.");

} else {

//put the umbrella back in the closet

System.out.println("Putting umbrella back in the closet.";

}

If the condition is satisfied, the body of the if statement will run, and the body of the else statement will run otherwise. Thus, ifitWillRain evaluates to true, we add our umbrella to our bag — otherwise, if itWillRain evaluates to false, we put the umbrella back in the closet.

Nesting Decisions

Java allows you to nest decision-statements to make multiple decisions before doing something. Let’s take our rain example from earlier for example. If it is raining outside we want to use the umbrella. However, we only want to use the umbrella if it is raining outside and we are outside. We don’t want to use the umbrella if we are inside. We can write this in code by using nested if statements.

The following code snippet demonstrates how we use nested if statements to make decisions in sequence. First, we check if it’s raining: if it’s not raining, that’s it, don’t use the umbrella. If it is raining, we use another if statement to check if we are outside. If we are outside, we want to use the umbrella, otherwise, don’t use the umbrella:

**Java for Humans**

41

/*some of the variables used in this snippet have been omitted.

Please see the supporting code for this chapter for working code*/

//make the first decision: check if its raining

if (itsRaining) {

/*make the second decision

because it's true that it's raining*/

//check if we are outside

if (weAreOutside) {

/*use the umbrella

because it's true that we are outside*/

useUmbrella = true;

} else {

/*otherwise, don't use the umbrella

because we are not outside*/

useUmbrella = false;

}

} else {

/*otherwise, don't use the umbrella

because it is not raining*/

useUmbrella = false;

}

We could also put if statements in the body of the else statements if we wanted to make more decisions after our initial conditions failed. For instance, if it is raining and we are not outside, we could check if we will be going outside soon before we decide to put the umbrella away or keep it nearby for when we are ready to step outside into the rain.

**If-Then-Else If-Then-Else Statements**

I may or may not have coined that hyphenated statement name, but excuse me for its complexity. Although it appears ugly, it allows us to make multiple decisions inline. You can think of it like so:

*If this condition is not true, check the others until one is true, then do something.*

Think of else as the default choice that is executed if none of the conditions before it are satisfied. When you get home from school, you try to find an activity to do. In this order, you check if you have homework, if not, you check if you have chores, if not, you check if your friends are free to play, and if not that, your default option is to watch the television if you have one. We can do this inline decision making in code, too:

**Learning to Classify Data**

42

/*some of the variables used in this snippet have been omitted.

Please see the supporting code for this chapter for working code*/

String activityToDo = "nothing yet";

if(haveHomework) {

activityToDo = "do homework";

} else if (haveChores) {

activityToDo = "wash dishes.";

} else if(friendsAreFreeToPlay) {

activityToDo = "go play with friends.";

} else {

if(haveTV) {

activityToDo = "watch favorite TV show.";

} else {

activityToDo = "do nothing";

}

}

**Others**

We have one more notable option for how we can make decisions in Java. The [switch statement](http://docs.oracle.com/javase/tutorial/java/nutsandbolts/switch.html) is powerful and can be used in special cases where you have many choices to choose from and each choice leads to a different code execution path. In some ways, the switch statement is an optimized version of what I call the if-then-else if-then-else statement. It is more of a matching statement than a decision-making statement. This is something you should research more because it can be handy in bigger projects as you become more experienced.

**Methods**

From the Classes and Objects chapter, you’ve learned that methods are used in Java to provide functionality to our classes and their instances. In this chapter, we will dive deeper into methods to learn how we create them, how we access them, and why they are important to Java programming. There’s a good deal to learn and this will be one of the longer chapters of the book, so take it slowly and calmly.

**Why Methods are Important & Useful**

Remember that in Java, everything revolves around objects. Objects are to Java programs as nouns are to English sentences. If objects are so important, they’d be really boring if all we could do is store information in them. Fields of classes are awesome for holding information about instances of our classes, but they aren’t much fun on their own. They can’t do any cool tricks. All they do is sit

**Java for Humans**

43

there and take up space in our programs. Imagine bringing home a new dog and naming it, memorizing its color, age and height, but not being able to do anything with it. Your excitement about your new dog wouldn’t last too long if that was the case. You’d want it to be able to actually do cool tricks instead of simply standing there and taking up space in your living room. That’s why Java and other programming languages decided to include the notion of methods.

With methods, not only can we manipulate the data in our fields, we can manipulate other data provided to us in order to create new information for our users to consume. Methods, although incredibly powerful, are easy to work with. We can give our classes a virtually unlimited amount of methods for their instances to perform.

**The Main Method**

Some methods, as you’ve learned about static methods, don’t even need to be called by an instance of their class. We’ve been working with one of those static methods since the first program we ran in the “Hello World” chapter. In the class that we ran the program from, we wrote our code in its main method. The main method of your program’s main class is static and the computer calls it to run our program. From there, the rest of our code runs in order from top to bottom. We can call the main class anything we want, but we must call the main method “main”. Only your main class needs to have the main method to run your program, but it must be present in at least one class in your program:

public class Main {

/**

* Your code is executed in order,

* top to bottom, starting from here.

* @param args arguments the computer

* provides to this method when it calls it.

*/

public static void main(String[] args){

System.out.println("Hello, World!");

}

}

**Method Syntax**

Remember that methods are named the same way we name variables, but they require a bit more information to make them work. When we make a method, we must provide five, most of the time its only four, main points of information in the signature of our method. It is important to remember that no two methods can have the same signature, but two methods can have the same name although this is usually not a good idea.

After the signature, we create the body of our method between a single set of opening and closing

**Learning to Classify Data**

44

curly brackets. The signature of our method and its body are the scope of our method. The scope simply defines the lifetime of variables declared in it. Every opening curly bracket starts a new scope and every closing curly bracket ends the last open scope:

{scope 1 {scope 2 {scope 3}} {scope 4 {scope 5 {scope 6}}}}

Variables declared in a scope live, are accessible, until that scope ends. Thus, a variable declared in scope one is accessible from all of the scopes within scope one, but a variable declared in scope three is only available to scope two, and a variable declared in scope six is only available to scope five and four as illustrated above. In Java, while you can put as many methods as you desire in the scope of a class, it is not legal to embed a method inside of another method’s scope.

**Method Signature**

First, we need to provide an access modifier to tell the compiler that executes our code where our method can be accessed from. Next, we need to say whether or not it’s static; by default, methods are not static, so we can simply omit the static keyword. After that, we need to tell the compiler what kind of data, or the datatype, our method returns; most of the time, this is either going to be a class type or a primitive type, and other times we can return data structures. Then, we need to give our method a lower camel case name that is usually unique — you’ll learn when it’s not unique later. Finally, we need to declare a list of theparameters that must be provided to our method as arguments when it’s called. When we provide all of that information, we can start the body of our method with a opening curly bracket { and end it with a closing closing curly bracket }:

public //access modifier

static //says if the method is static

int //return type

add //name

(int num1, int num2) //parameters

{ //start body, scope

//body: write fun code here

} //end body, scope

**Method Access Modifiers**

A public method can be accessed from anywhere in our program, butprivate methods can only be accessed from within the class it belongs to. A protected method can be accessed from any class within the same package as the class the method belongs to. Those access modifiers work the same on both instance and static methods of a class. Intuitively, a method can only be accessed from the parts of a program where the method’s class can be accessed.

**Java for Humans**

45

**Method Return Types**

A method must specify a return type in its signature. A return type tells the compiler what datatype will be returned by the method. If the method will not return anything, we can specify void as the return type. Void means that the method will do what it has to do and return nothing to the caller. Otherwise, we must specify a datatype to be returned. We can return Java primitives, datatypes provided by Java, including a String, and custom datatypes, such as classes we create. Further, we can return data structures like arrays, LinkedLists, and HashMaps. We will learn more about data structures soon, but for now, know that they are simply datatypes that hold a set of data of the same type.

**Method Parameters**

Remember that methods are powerful in that they can manipulate data available in our class or instances of our class, but sometimes we need them to do more. Sometimes they need some data from outside of our class or instances of our class to complete the job. A good example of this is when you are in gym class and the instructor asks you to jump. Some people would start jumping mindlessly, but the wise thing to do would be to ask the instructor how high he wants you to jump and for how long. Next time the instructor invokes, or calls, your jump method, he will know he has to provide you a height to jump to and the amount of time to continue jumping for. Soon, we will use that same idea to teach our new pet dog how to jump.

We can provide as many parameters as we want to our methods, and when someone calls one of our methods, they will have to pass in all of the parameters we require as arguments. Our methods can then use the parameters as variables in their body. It is often wise to check if the parameter provided to our method is not empty by checking that it’s notnull because users may misuse our methods.

A *null* object is one that has no data in it and, therefore, has no type. Such an object cannot be used. Consequently, if we try to call a method on a *null* object, our program will break. We can use an if statement to check if a parameter is null in our method’s body before we use it by comparing the parameter to *null* with the not-equal-to equality operator !=. The good news is primitives cannot be null because they have default values. However, remember that a string is an instance of the String class provided by Java, so it is not a primitive and, like other class instances, should always be checked against null.

**Modeling Our New Pet Dog**

Let’s make a dog class to model our new pet dog. We will give our dog functionality by adding methods to its class that will allow it to do cool tricks. Our class will be called CoolDog because any instance of it will be able to do cool tricks unlike our boring dog from earlier. All instances of our CoolDog class will have a name, an age, a height in inches, a Human owner, and a unique id that is final — cannot be changed after it’s set. Our CoolDog class will also have a static field to keep track of how many cool dogs have been instantiated in our program. Finally, all cool dogs will be able to bark, roll over, and jump. We will also have a Human class that we will use to define a field in our CoolDog class, but that code can only be found in the supporting code for this chapter.

**Learning to Classify Data**

46

public class CoolDog {

...

public CoolDog(String name, int age, int height) {

this.name = name;

this.age = age;

this.height = height;

id = ++numCoolDogs;

}

public String getName() { return name; }

public int getAge() { return age; }

public int getHeight() { return height; }

public Human getOwner(){ return owner; }

public void setOwner(Human owner) { this.owner = owner; }

private boolean hasOwner() {

return owner != null;

}

public void jump(int howHigh, int howLong) {

if(hasOwner()) {

System.out.println("Jumping " + howHigh

+ " inches high for " + howLong + " seconds.");

} else { bark(); }

}

public void rollOver() {

if(hasOwner()) {

System.out.println("Rolling over for " + owner.getName() + ".");

} else { bark(); }

}

**Java for Humans**

47

public void bark() {

System.out.println("Wolf! WOLF!!");

}

public static int getNumCoolDogsInWorld(){

return numCoolDogs;

}

}

***Note!***

We have once again left some of the code out of this code snippet, and that is denoted by the ellipses (…).

Notice that our CoolDog class has four instance methods that return the values of an instance’s instance fields. The return type of the getName() method is a String, the getAge()method returns data of type int, and the getHuman() method returns the owner, a type of Human. A cool dog will bark whenever the bark()method is called, but a cool dog can only roll over or jump if it has a owner who has taught it how to. In the cases where a cool dog does not have a Human owner, it will bark when asked to roll over or jump.

The numCoolDogs static field is incremented each time the constructor of our CoolDog class is invoked to maintain an accurate count of how many instances exist of the class. If at any point we want to know how many CoolDog instances exist in our program, we can call the staticgetNumCoolDogsInWorld() method to return to us an int, numCoolDogs, that represents how many instances of our CoolDog class have been constructed.

Notice that the hasOwner() instance method is private because only the dog needs to know if it has a owner. We won’t be able to call that method from outside of the CoolDog class, not even on an instance of the class. Finally, observe that many of the methods, such as rollOver(), in the CoolDog class do not have parameters. This is simply because they don’t need data from the caller to do their job; they use the data available in the instance to do what they have to.

**Dot Notation**

This section is a continuation of the *Methods* section. Notice that whenever we’ve wanted to access a field or call a method from a class or an instance of a class, we’ve had to write a dot (.) after the name of the class or its instance followed by the name of the field or method. This is called dot notation:

Human person = new Human("Lucy");

CoolDog coolDog = new CoolDog("Buddy", 4, 30);

person.setPetDog(coolDog);

**Learning to Classify Data**

48

There, we used dot notation to call the *setPetDog()* method of the Human instance and we passed that method the required argument of a CoolDog instance.

We can also employ chaining with dot notation to optimize field accesses and method calls. Imagine if we want to get the petDog field of the Human instance, person, and make that CoolDog instance jump ten inches in the air for five seconds. We can save the returned CoolDog instance to a variable and then call jump on that variable like so:

CoolDog petDog = person.getPetDog();

petDog.jump(10, 5);

Sometimes, a more efficient way to do the same thing may be to use chain dot notation. When the person returns its instance of a CoolDog to us, the caller, we can immediately make it jump as we wish without saving the returned CoolDog to a variable first:

person.getPetDog().jump(10, 10);

That method of using chain dot notation saves us from writing more code and it saves space in our computer’s memory because we aren’t allocating another variable in memory.

**Access Modifiers and Encapsulation**

As humans, we make use of the tools provided to us by companies, our parents, teachers, friends, and government. Most times, we don’t care about how the tools work behind the scenes; all we care about is that they work and get the job done when we call on them.

When you go to a vending machine and pay for cookies with a dollar bill, you don’t necessarily care how the machine knows you gave it a valid dollar instead of a piece of printer paper, but you do expect it to accept your dollar as a form of payment and for it to dispense your cookie. If the cookie only cost $0.75, you expect the machine to also give you a quarter back and you don’t care how it manages to do that. You are unaware of the amount of money the machine has in it and how it does the math to decide how much money to give back to you. With that, we can say that all of its functions are encapsulated. The English dictionary defines “encapsulate” as so:

*"To enclose (something) in or as if in a capsule."*

In computer science, we define encapsulation as such:

*"To provide an interface for (a piece of software or hardware)*

*to allow or simplify access for the user."*

Thus, encapsulation in Java and many OOP languages is the process of wrapping information and functionality in a class and providing methods of accessing them in order to provide a simple

**Java for Humans**

49

interface for users to access the information and make use of the functionality of the class.

**Why Encapsulation is Important & Useful**

Encapsulation is the reason you don’t have to calculate your own change when you go to a vending machine. You slip in your cash and out comes correct change. Behind the scenes, the machine is keeping track of how much money it has available, how much each item costs, and how much money you give it. It also has functions to dispense the right item if you provide it enough money as well as a function to calculate how much change to give you. This allows you to simply walk up, give it a dollar, select an item, get the item and your change, and go enjoy life without worrying about the complex calculations going on behind the scenes. This is why encapsulation is so great in programming.

In Java, we can use encapsulation to hide the hard work from the user of our program, or teammates who use our code, while providing them access to the functionality they need. Let’s model our vending machine situation in code to get a closer look of how awesome encapsulation is:

/*some methods have been omitted in this code snippet*/

public class VendingMachine {

private double cookieCost;

private double gumCost;

private double changeFromLastPurchase = 0;

public VendingMachine (double cookieCost, double gumCost) {

this.cookieCost = cookieCost;

this.gumCost = gumCost;

}

public double getCookieCost(){ return cookieCost; }

public double getGumCost(){ return gumCost; }

public void buyItem(String whichItem, double payment){

resetLastPurchaseChange();

if(itemExists(whichItem)) {

if(paymentIsEnough(whichItem, payment)) {

dispenseItem(whichItem);

calculateChange(whichItem, payment);

} else { alertUser(whichItem, payment); }

}

}

**Learning to Classify Data**

50

public double getChange() {

return changeFromLastPurchase;

}

private boolean paymentIsEnough(String whichItem, double payment) {

if(whichItem.equals("cookie")) {

return payment >= cookieCost;

} else if (whichItem.equals("gum")) {

return payment >= gumCost;

} else { return false; }

}

private void dispenseItem(String whichItem) {

System.out.println("Here's your " + whichItem);

}

...

}

Now, there’s a good deal of code there, so let’s break it down.

**Access Modifiers**

Encapsulation in Java would not be as effective as it is today without access modifiers. Access modifiers allow us to decide how parts of our classes can be accessed by other classes in other parts of our program. If we want a field or method to be accessible from anywhere, by any class, we can mark it as public. By default fields, method, and classes are public to all other classes in their package. If we only want a field or method in our class to be accessed from within our class, we can mark them private.Finally, if we want to explicitly constrain the access of a field or method to subclasses of their class or other classes the same package, we can mark them as protected. Nonetheless, as a beginner, your focus is on public andprivate until you begin building larger programs.

In Java, by default fields, method, and classes are package-private, which means they cannot be accessed from outside of their package. That is only the case when we do not specify an access modifier. In this book, we only focus on public, private, and protected but it would be good to know this and research it more.

Classes can also be marked with access modifiers. At the top-level, scope one, a class can only be *public* or *pack-private*. An inner class, however, can be marked the same way as fields and methods, but that, too, is beyond the scope of this book. For our purposes, all of our classes will be marked as public.

**Java for Humans**

51

**Encapsulation & Our Vending Machine**

Before we analyze our vending machine class, it’s important that you know there are a few methods missing from the snippet above. You can view the full class and the accompanying executable program in the supporting code section.

If we start at the top of our vending machine class, you’ll see that all three of its fields, cookieCost, gumCost, and changeFromLastPurchase, are private. This ensures that no outsiders can change their values because the owner of the machine wouldn’t want customers changing the prices of the items in the machine and choosing how much change customers get.

When creating an instance of the VendingMachine class, the owner must provide the cost of the items as arguments to the constructor. The only public methods are the constructor for the owner to construct a new instance of the vending machine, and the three functions users of the machine would care to use: getting the price of items, buying items, and getting their change.

When a customer walks up to an instance of our VendingMachine class, they can only call the three public methods because the rest, including the omitted ones, are private. The customer can ask to see how much a cookie or a gum is, and if they are satisfied with the prices our machine returns, they can invoke the machine’s buyItem() method to try to buy an item. Behind the scenes, our buyItem() method will call our other methods which are private to do the work.

public class StoreProgram {

public static void main(String[] args) {

System.out.println("Starting Store Program");

System.out.println("Owner creates vending machine.");

VendingMachine vendingMachine = new VendingMachine(0.75,

0.50);

System.out.println("Customer starts using machine.");

double costOfCookie = vendingMachine.getCookieCost();

System.out.println("Wow cookies cost " + costOfCookie);

System.out.println("and gum costs " + costOfGum);

System.out.println("I'm going to buy a cookie!");

vendingMachine.buyItem("cookie", 1.00);

double change = vendingMachine.getChange();

System.out.println("\nGot my change of " + change + "

cents");

}

}

**Learning to Classify Data**

52

The buyItem() method will have to call our private itemExists() instance method to check if the item the user wants to buy actually exists in our machine. Next, if the item exists, the machine will call its privatepaymentIsEnough() instance method to check if the user paid enough money for the item. If the user paid enough for the item, the machine will call its private dispenseItem() instance method to give the user the item he/she just bought. Finally, the machine will call its privatecalculateChange() instance method for the purchase and store the result in the changeFromLastPurchase instance field. Finally, the user can call the machine’s public getChange() instance method to get his/her change from the last purchase. That’s it.

We have built a vending machine interface for our users to use with ease by employing encapsulation. You will want to make extensive use of encapsulation as you grow in your programming knowledge. It will make your code clearer and safer for you and teammates and easier for users.

Well there it is! You are past the stage of not knowing how to code now. You are on to the stage of becoming a better programmer. Soon, you’ll learn about looping, data structures for storing sets of data for later use, and how to get user input, which you’ve already seen in action.

**Java for Humans**

53

**Chapter 4**

**Learning to Manipulate Data**

**Generating Random Numbers**

As a kid, you may have played many games to fill your day with some fun and excitement. In some cases, the most exciting games may have been the ones that employed some bit of randomness and unpredictability. Board games like monopoly use a dice to create randomness in the outcome of the game. The series of random numbers you roll determine how successful you are in the game. Computer games, on the other hand, don’t have access to a physical dice, so there must be another way for them to create randomness. For that reason, Java and other programming languages have random number generators we can use to create randomness in our programs.

**Why Random Numbers are Important & Useful**

Random number generators allow us to generate random numbers that we can use to create randomness in our code. Java allows us to easily generate random whole (int or long) and floating point (double) numbers. We can also generator randomboolean values. With the random numbers that we generate, we can decide when to execute some lines of code and when to execute the others.

A good example of when you may need a random number program is in deciding whether or not you should go out with friends or stay in and do your homework. You can build a program to generate a random number between zero (inclusive) and ten (exclusive). If you generate a random int between zero (inclusive) and five (exclusive), you can go out, but if it's between five (inclusive) and ten (exclusive), you must stay in.

**Generating Random Numbers**

By creating an instance of Java’s Random class in java, we can use it to generate random values:

Random randomNumberGenerator = new Random();

Whenever we call an instance method of the Random class, a new random number of the type you want is generated behind the scenes and returned to us. All of the complex math is encapsulated from us so we can get our random numbers or booleans and continue with our program.

**Learning to Manipulate Data**

54

**Generating Random Values**

Generating a random integer (int) is as simple as calling thenextInt() instance method on our instance of the Random class. We can generate other random values in similar ways:

//generate and save random int to a variable of type int

int randomInt = randomNumberGenerator.nextInt();

//generate and save random long to a variable of type long

long randomLong = randomNumberGenerator.nextLong();

//generate and save random double to a variable of type double

double randomDouble = randomNumberGenerator.nextDouble();

//generate and save random boolean to a variable of type boolean

boolean randomBoolean = randomNumberGenerator.nextBoolean();

//print out all of our random numbers

System.out.println("Random whole number as int: " + randomInt);

System.out.println("Random whole number as long: " + randomLong);

System.out.println("Random floating point number as double: " + randomDouble);

System.out.println("Random boolean: " + randomBoolean);

//generate another random int and print it inline

System.out.println("Another random whole number as int: " + randomNumberGenerator.nextInt());

***Possible Output***

*Random whole number as int: -2131209878*

*Random whole number as long: 3349792078338628742*

*Random floating point number as double: 0.59413166337279*

*Random boolean: false*

*Another random whole number as int: 78474926*

As easy as that, we have three random numbers stored and a random boolean (true or false) stored in variables. Notice that at the end, we generated another random number as an *int*, but instead of storing it in a variable, we printed it out immediately after it was returned to us.

**Java for Humans**

55

**Generating Random Numbers With Bounds**

When we generate random numbers, we can choose whether or not to do so with bounds. In our examples above, we generated random numbers without bounds because we did not provide a maximum bound argument to the instance methods we called. When we call the nextInt() instance method on a Random instance, we can expect to receive a random integer between and including zero and the maximum integer allowed in Java. The nextLong() and nextDouble() instance methods behave similarly except that nextDouble()'s range is from 0.0 (inclusive) to 1.0 (exclusive).

If we want to generate random numbers with a bound, we must provide the maximum bound argument to the instance methods we call. The maximum bound argument tells the method what the largest number in the range of random numbers that we expect should be, exclusively that is. If we only want to generate random numbers between zero (inclusive) and ten (exclusive) to decide whether or not you should go out with friends or stay in and do homework, you can do the following:

int randomIntWithBound = randomNumberGenerator.nextInt(10);

Note that the maximum bound argument must be positive. Now, to check whether or not we should go out or stay in, we can do the following:

if(randomIntWithBound >= 0 && randomIntWithBound < 5) {

//random int is between 0 (inclusive) and 5 (exclusive)

System.out.println("I'm going out!");

} else {

//random int is between 5 (inclusive) and 10 (exclusive)

System.out.println("I'm staying in.");

}

***Possible Output***

*I'm staying in.*

A simpler way to do the above would be to use a random booleanvalue instead of a range of integers:

boolean randomBoolean = randomNumberGenerator.nextBoolean();

if(randomBoolean) {

//random boolean is true

System.out.println("I'm going out!");

} else {

//random boolean is false

System.out.println("I'm staying in.");

}

**Learning to Manipulate Data**

56

***Possible Output***

*I'm going out!*

That’s it. We now know how to generate random values with or without bounds as well as random booleans. Further, we have learned how to use random values to make decisions in our code with if statements. You can now employ your new knowledge to add randomness to your programs and make them that much more interesting.

**Control Flow Statements: Loops**

We’ve come a long way from the last time we learned about control flow statements in the Decisions chapter. Great work on making it this far. This chapter will cover loops, which allow you to execute blocks of code more than once.

In the Decisions chapter, we learned that Java executes our program line by line from top to bottom. To change that, we could use if statements to only execute a block of code when a condition is true and another block of code otherwise. That is the basis of control flow in Java. With decision-making statements, we can choose to skip some lines of code during execution, but what if we want to repeat a line of code multiple times while a condition is true? That’s where loops come into play.

**Why Loops are Important & Useful**

Loops in Java allow us to repeat some of our code a fixed number of times or so long as a condition remains true. There are three basic forms of loops in Java, but we will only be focusing on two of them here because they are the most important and useful ones for beginners. We will learn about the for statement and the whilestatement. Both statements allow us to loop over blocks of code so long as a condition is true, but they do so a little differently from one another.

**For Loop**

The for statement allows us to loop over a block of code until a certain condition is satisfied. Because it loops, programmers often refer to it as the for loop. The for loop is best when you want to do something for a fixed number of times.

Say we want to loop over a range of numbers and print out each one along the way. We can do this best with a for loop. We will start from the first number, print it out, move to the next number to do the same thing, and continue until we’ve printed each number. Let’s print the numbers zero through nine:

**Java for Humans**

57

for(int count = 0; count < 10; count++) {

System.out.print(count + " | ");

}

***Output***

*0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |*

Let’s take a look at the first line of the for loop and the three parts necessary to make it work. There is an initialization expression,termination expression, and a increment expression in that order.

**The Starter: Initialization**

The initialization expression initializes the loop and is only executed once, when the loop starts. This is where you must declare and initialize a variable, usually of type int, to hold an initial number that will be used to loop until it reaches a certain value. This can be thought of as the start of the range to iterate over. In our case, we started at zero (0).

The scope of the variable declared in the initialization expression extends from its declaration to the end of the for loop — until the closing curly brace } of the for loop’s block of code. This variable will be used by the termination and increment expressions during the lifetime of the loop. It can also be used in the body of the forloop as we did to print out the current number in our range. If the variable is not needed outside of the scope of the loop, it’s best to declare it in the initialization expression. Otherwise, we could declare the variable before the for loop and initialize it in the initialization expression, like so:

int count;

for(count = 4; count < 10; count++) {

System.out.print(count + " | ");

}

System.out.print("The next number would be " + count + ".");

***Output***

*4 | 5 | 6 | 7 | 8 | 9 |*

*The next number would be 10.*

There, we printed the numbers four through nine in the loop, and we finished by printing what would have been the next number to print had we not stopped the loop at nine. Had we not declared the count variable before the for loop, we would not have been able to use it outside the scope of the for loop as we did there.

**Learning to Manipulate Data**

58

***Note!***

Although we named our initialization variable “count”, you will usually see it named “i”, “j”, or “k” as a convention.

**The Terminator: Termination Expression**

The for loop will continue looping until the terminationexpression evaluates to false. The termination expression is evaluated before each iteration of the loop and it must return a boolean to decide whether or not to continue looping. If the boolean returned is equal to true, we will run the body of our forloop again. In our case, because we want to print numbers from four through nine, we want the loop to terminate after it prints nine. It does exactly that.

**The Incrementer: Increment Expression**

This is one of those times I’m going to make up a word: theincrement expression is the incrementer of the for loop. The increment expression is executed after each iteration of the loop to increment the variable we initialized in the initialization expression by use of the ++ operator. That allows the termination expression to know how many times the loop has looped. In our case, the initialization variable, count, starts at 0 and it’s printed out, then the incrementer increments it and the next iteration of the loop runs to print the new value count— 1 — and continues that way until 9 is printed. Finally, the incrementer increments the value of count to 10, but the terminator says, “No, no, no, 10 is not less than 10, so we are done here.”

Our example may seem trivial, but the *for* loop is a useful tool for easily and dynamically executing blocks of code multiple times without writing the same code more than once. In the Arrays chapter, you will see how we can use a for loop to iterate through the indices of an array to access each element one by one and manipulate them.

**While Loop**

The *while* statement is often referred to as the while loop because it continually loops over and executes a block of code statements while a given condition, or a set of conditions, is true. It is simpler to set up than the for loop because it only needs one expression, a termination expression, to evaluate before each iteration:

while (conditionIsTrue) {

//do something

}

**Java for Humans**

59

A simple application of the while loop would be to print all numbers from zero through nine. It will look much similar to what we did with the for loop:

int number = 0;

while(number < 10) {

System.out.println("Current number = " + number);

//increment the number to move to the next

number++;

}

***Output***

*Current number = 0*

*Current number = 1*

*Current number = 2*

*Current number = 3*

*Current number = 4*

*Current number = 5*

*Current number = 6*

*Current number = 7*

*Current number = 8*

*Current number = 9*

Again, that may seem trivial, but imagine the things you could do with loops. A loop may be used to keep your television on until you push the “off” button. Think about your microwave; much like a timer, it likely uses a loop to continue heating up your food until the time you set runs out. If you play video games, you may notice that the game continues to run until you turn off your game console or your computer. That’s a while loop at work:

while(offButtonNotPushed && userStillEngaged) {

//keep the game on for the user to continue playing

}

That’s a quick example of a while loop that evaluates multiple conditions before each iteration over its body. That while loop will continue looping so long as the user did not push the off button and the user is engaged in the game.

***Note!***

The && operator performs the logical And operation by combining two boolean expressions and returning true if and only if both expressions evaluate to true.

**Break Statement**

Loops are great, but sometimes we want to end them before they end themselves. If we have a loop iterating over a block of code, it will continue to do so until a particular condition becomes false.

**Learning to Manipulate Data**

60

Another way to end a loop is to break out of it when another condition becomes true during an iteration and we no longer want to continue looping.

Say you want to continue eating cookies until your stomach is full, but there’s only so many cookies available. If we run out of cookies to eat, we shouldn’t keep trying to eat cookies even if we are still hungry. Instead, we should break out of the loop. We can simulate this situation with a *while* loop like so:

int numCookiesEaten = 0;

int cookiesNeededToBeFull = 10;

int numCookiesLeftInCookieJar = 8;

Random randomCookiesGenerator = new Random();

int numCookiesToEatThisTime;

int numCompletedIterations = 0;

while(numCookiesEaten < cookiesNeededToBeFull) {

numCookiesToEatThisTime = randomCookiesGenerator

.nextInt(numCookiesLeftInCookieJar) + 1;

/*make sure we aren't trying to eat

more cookies than exists in the cookie jar*/

if(numCookiesToEatThisTime > numCookiesLeftInCookieJar) {

numCookiesToEatThisTime = numCookiesLeftInCookieJar;

}

System.out.println("< Eating " + numCookiesToEatThisTime + "

cookies this time.");

numCookiesEaten += numCookiesToEatThisTime;

numCookiesLeftInCookieJar -= numCookiesToEatThisTime;

if(numCookiesLeftInCookieJar < 1) {

System.out.println("\n#No cookies left to eat :(");

break;

}

**Java for Humans**

61

else {

System.out.println("> " + numCookiesLeftInCookieJar + "

cookies left in jar");

}

//increment number of times we've looped

numCompletedIterations++;

}

System.out.println("Completed " + numCompletedIterations + " iterations.");

***Output***

*< Eating 4 cookies this time.*

*> 4 cookies left in jar*

*< Eating 2 cookies this time.*

*> 2 cookies left in jar*

*< Eating 2 cookies this time.*

*#No cookies left to eat :(*

*Completed 2 iterations* 

There, you can see we need to eat ten cookies before we are full, but there are only eight cookies in the cookie jar to eat. During each iteration of the loop, we eat a random number of cookies from the cookie jar. At the end of each iteration, we increment the value of thenumCompletedIterations int variable by one. At some point, we will definitely run out of cookies to eat before our stomach is full. At that point, we use the break keyword to break out of the loop.

Notice that after invoking break, we print how many full iterations we made through the whileloop. It says we only completed two iterations because on the third iteration, we broke out of the loop before increasing the value ofnumCompletedIterations a third time.

Play around with the supporting code and find other ways to use the break statement with both the while and for loops.

**Learning to Manipulate Data**

62

**String Manipulation**

Java Strings are powerful. While a String seems simple as a mere representation of character strings, they are one of the best ways to store information, data in Java. Because character strings are so vital to programming, the creators of Java decided to dedicate an entire class to them and give that class useful methods to make data manipulation easier. In this chapter, we will learn how to use some of the instance methods of the String class to compare strings, search a string for individual characters or substrings, extract substrings, and more. It is not necessary that you read this whole chapter, but it is important that you know these functions are available to you.

**Why String Manipulation is Important & Useful**

Often times in your programs, you will be presented with data which you can store as a String. When you have the data stored as a String instance, you can use the instance methods of the String class to manipulate the data. This functionality allows you to do more things with the data you have.

**Comparing Strings**

A operation you will run many times in your programs is a operation to compare two String instances to one another. If you have a Facebook account, you will be asked for your username and password when you try to log in. Behind the scenes, Facebook will compare the username and password you provide to the username and password they have stored in their database for your account. If the comparisons are successful, you can log in, but if they fail, you will have to try again.

The String class has convenient comparison instance methods for us to compare two instances. We can use equals() to compare two strings case sensitively or equalsIgnoreCase() to compare without considering the case of the strings. Both of these methods return a boolean — true if the comparisons succeed and falseotherwise. Let’s emulate a social network login process in Java:

String usernameInDatabase = "modernNerd";

String passwordInDatabase = "mN123Java";

String providedUsername = "modernnerd";

String providedPassword = "mN123Java";

**Java for Humans**

63

if(providedUsername.equalsIgnoreCase(usernameInDatabase)){

//successful username comparison

//check the provided password

//this will fail

//if("mn123java".equals(passwordInDatabase)){}

//this will pass

if(providedPassword.equals(passwordInDatabase)){

System.out.println("Success! You are logged in.");

} else {

System.out.println("Wrong password. Try again.");

}

} else {

//user provided wrong username

System.out.println("Wrong username. Try again.");

}

If the username provided by the user,providedUsername, matches the username in the database, usernameInDatabase, regardless of case, we want to check if the password provided by the user, providedPassword, matches the password in the database, passwordInDatabase, with regards to the case. If all of the string comparisons pass, we can let the user log in.

**Counting Characters in a String**

Some social networking applications, such as Twitter, allow users to post messages with a maximum length. They capture the message the user enters as a String, count the length of the message, and use its length to decide whether or not to let the user post the message. We can do that with the length() instance method:

String message = "Hello, world! My name is Lincoln";

int messageLength = message.length();

if(messageLength <= 140) {

//send the message

}

Getting Index of a Character in a String

If you want to know the index of the first occurrence of a character in a string, you can use the indexOf()instance method on a String instance. Remembering that indices in Java and other

**Learning to Manipulate Data**

64

programming languages start at zero, we can try to get the index of the letter “D” in a string containing the entire alphabet:

String alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

int indexOfLetterD = alphabet.indexOf("D");

System.out.println("Index of letter 'D' is " + indexOfLetterD);

***Output***

*Index of letter 'D' is 3*

Although “D” is the fourth letter in the English alphabet, it is at the third index in the String instance, and that’s exactly what is returned by indexOf().

**Getting Index of a Substring in a String**

Other times, you may not only want to know the index of a single character. Instead, you may want to know the index of the first occurrence of an entire substring of a String instance. Say you want to get the start of the ending characters of the alphabet. The indexOf() instance method will return where the substring begins as the index of the first character in the substring:

String alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";

int beginningOfTheEnd = alphabet.indexOf("XYZ");

System.out.println("Value of beginningOfTheEnd: " +

beginningOfTheEnd);

***Output***

*Value of beginningOfTheEnd: 22*

The letter “X” is the 24th letter in the alphabet, but it’s at the 23rd index in the String instance. The substring “XYZ” of the alphabet String instance starts with “X”, so that substring begins at the 23rd index; that is what indexOf() returns here.

Extracting a Substring From a String

There may be some times when we only want a part of a string. In such cases, we want to extract a substring from a string. One of those cases may be when we have a long string but we only want the second half of it. We can use the substring() instance method on our String instance to get the first half of it by passing in one argument which will tell the method at which index of the string to start extracting our substring. Another way to think of the method’s argument is that it tells the substring()method how many characters, from the left, it should skip. Given that, we can get the second half of our alphabet string by providing half its length as the argument of the substring()

**Java for Humans**

65

method:

String secondHalfOfAlphabet = alphabet.substring(13);

System.out.println(secondHalfOfAlphabet);

***Output***

*NOPQRSTUVWXYZ*

While that works, there is a more dynamic approach to the above that allows our code to adapt to a change in the length of the alphabet in the case its length changes from 26 to something else, say 20\. In such a case, 13 would no longer be half the length of the alphabet, so we should prepare for that by doing the following:

String secondHalfOfAlphabet = alphabet.substring(alphabet.length() / 2);

System.out.println(secondHalfOfAlphabet);

***Output***

*NOPQRSTUVWXYZ*

Now imagine your friend asks you for your street address and city, but you only have the entire string of your house address which contains the street address, city, state, zip code, and country. You may not want to send her your entire address because she only cares about your street address and city. In this case, you would need to manipulate the String containing your full address to get only the part containing your street address and city and store it in a new variable to send to her.

Knowing that the street address and the city come before the comma in your full address, you can use the substring() method along with the indexOf()method to get that part of the string containing your street address:

String fullAddress = "123 JavaStreet JavaCity, JavaState 19081 United States";

String streetAddressAndCity = fullAddress.substring(0, fullAddress.indexOf(","));

The first argument of the substring() method tells the method where to begin extracting the substring while the second tells it where to end the substring. Together, the arguments declare the range of the substring we want the method to return. The range is inclusive of the first argument and exclusive of the second; in our street address and city example, the substring will begin at index zero (0) of fullAddressand end right before the index of the comma. Here’s the result of our operation:

System.out.println(streetAddressAndCity);

**Learning to Manipulate Data**

66

***Output***

*123 JavaStreet JavaCity*

**Converting Case of Strings**

There will be times when you have a word in a case other than what you need it in, so it’s nice to know that you can convert it to either all uppercase or all lowercase characters when stored in a String instance by using its toLowerCase() andtoUpperCase() instance methods. A good use of such functionality would be to ensure consistency of the data you store in a database. Making sure all of the data you get from a user is lowercase before you store it in your database will make your database easier to search through later. This is also good for the users who do not want to worry about the case of the information they provide to your program. You can let the user enter information in any case they want and convert it to the necessary case behind the scenes for your program:

String name = "Lincoln Daniel";

String lowercaseName = name.toLowerCase();

String uppercaseName = name.toUpperCase();

System.out.println("Lowercase name: " + lowercaseName);

System.out.println("Uppercase name: " + uppercaseName);

***Output***

*Lowercase name: lincoln daniel*

*Uppercase name: LINCOLN DANIEL*

***Note!***

Bonus: Figure out how to capitalize the string; only make the first letter in a String uppercase. You may need to use the substring() instance method.

**String Replacement**

Another useful tool provided to us in the String class is a method to replace a substring in a string with another string. If you want to change your last name, you can call the the replace() instance method on the string storing your full name. The replace() method takes two arguments — the substring you want to replace and the string to replace it with — and finds all occurrences of the first argument and replace them with the replacement. Finally, it will return the new String instance to you with the replacement. Let’s change my first name:

String newName = name.replace("Lincoln", "Modern");

System.out.println(newName);

***Output***

*Modern Daniel*

**Java for Humans**

67

My name is now “Modern Daniel”. Let’s finish by changing my last name to “Nerd”:

String newName2 = newName.replace("Daniel", "Nerd");

System.out.println(newName2);

System.out.println(name);

***Output***

*Modern Nerd*

*Lincoln Daniel*

Now my name is “Modern Nerd” and that new string is saved in the newName2 String variable. However, if you want to access my original name, you can still do so because we did not change the value of our name variable. The name variable still holds my original name because the replace()method copies the string it is called on and returns the copy after modifying it. The original string is never modified because String instances are immutable. Immutable data cannot be mutated, or changed. Note that the name variable is mutable because it’s a variable, but the String instance it holds is the data that is immutable. Therefore, if we wanted to overwrite our original name in the name variable, we could do the follow:

name = newName2;

System.out.println(name);

***Output***

*Modern Nerd*

**Splitting a String into Tokens**

If you’ve ever written an essay for homework, you have likely been instructed to make sure your essay consists of exactly a certain amount of words. As you write it, you constantly check the amount of words you’ve written to check how far you are from completing the essay. Many word document editors have a tool to help you count the amount of words you’ve written so you don’t have to sit there and count your words on your own. Until now, how the editor does the word counting may have been a mystery to you. Let’s see how easy it is to split a String instance and count the amount of words in it by making use of the split() instance method.

If you want to know how many words are in an string holding an essay, knowing that words are usually separated by a single empty space, you can provide an empty string with a length of one — a space — to the split() method in order to get all the tokens in the string as an array and count the number of tokens, elements in the array. Let’s try it out:

String essay = "The ModernNerd coded everyday to build something great.";

**Learning to Manipulate Data**

68

String[] allWordsInEssay = essay.split(" ");

int numWordsInEssay = allWordsInEssay.length;

System.out.println("Word Count: " + numWordsInEssay);

***Output***

*Word Count: 8*

The split() method takes a delimiter as its single argument. The delimiter tells the method how to split the string up into tokens. Tokens are simply the parts, substrings, of the string as delimited by the provided delimiter. You can provide any string as your delimiter, and the method will return an array holding all of the tokens it could create from your string and your delimiter. If it doesn’t find your delimiter in your string, it will only return one token, the original string, in the resultant array.

***Note!***

We will learn more about Java arrays soon, but know that they simply store a collection of data of the same datatype and every array has a handylength field that holds an integer representing the amount of elements in the array.

There are more methods provided to us in the String class for the purposes of manipulating strings, but the ones we have learned in this chapter are all you need to get started.

**Input and Output (I/O)**

Remember that we program to capture and manipulate information, or data, to create new data for users to consume. Software programs would not be interesting without being able to capture information, accept input from the user and produce new information — create output for the user to consume.

As a kid, you likely played games that asked for your name and age and used that information to tailor your experience to you. To tailor the gaming experience to you, games usually refer to you by your name and use your age to determine which parts of the game would be most appropriate to show you. In some cases, games may not let you play if you provide an age that is too young. This is all an example of gathering user input and using it to create output for the user. In this chapter, we will learn how Java allows us to easily gather input and produce output in our programs.

**Scanning User Input from Keyboard**

From the very beginning of the book to now, we’ve been using Java’s Scanner class to capture input from the user. The Scanner class allows you to read input available from an input stream. An input stream simply holds data coming in to your program while an out stream holds data going out of your program. In previous chapters, our input stream has been System.in, which streams in data from the user’s keyboard.

**Java for Humans**

69

***Note!***

The “System” is the current system your program is running on. System is a class provided by Java. Notice that we didn’t need to create a new instance of System in order to access its *in* static InputStream field. This is a prime example of the utility of static fields.

The Scanner’s constructor takes a Java InputStream object as its single argument in order to create a new instance of a Scanner:

Scanner scanner = new Scanner(System.in);

With our new Scanner instance, we can read user input from the user’s keyboard because we provided it in as the InputStream. The Scanner class has many useful instance methods that allow us to check if there is input available in the provided input stream and to read available input into our program.

**Checking for Input**

Before reading input from a Scanner instance, it’s smart to check if there is actually input available to read. Like you would check if your bank account has money in it before you try to withdraw money from it, we always make sure our scanner has valid data ready for reading before trying to read from it. The hasNext() instance method returnstrue only if there is data available in the provided InputStream object to read. If there is no data ready for us to read, the hasNext() method returns false:

if(scanner.hasNextLine()) {

//new line of data is available in input stream

//read from the scanner

} else {

//no line of data available in input stream

//don't read from the scanner

}

The Scanner class also has instance methods for checking if the provided InputStream object has data of a certain type available for reading. We can check if there is an int,double, long, boolean, and other data types available for reading. Each datatype has its own hasNext method; you can check for an int by calling hasNextInt() on the scanner:

**Learning to Manipulate Data**

70

if(scanner.hasNextInt()){

//read the int from the scanner

} else {

//scanner does not have an int ready for reading

}

**Reading Input from Scanner**

Now that we know our user has typed something into their keyboard and that input is stored in the InputStream object provided to our scanner, we can read it into our program. To read data from the scanner, we can simply call thenext() instance method to get the next data token available in the scanner. Further, if we want to read the entire next line of data available in the scanner, we can call thenextLine() instance method:

if(scanner.hasNextLine()) {

String nextLineOfData = scanner.nextLine();

}

Like the hasNext() method, the next() method has special methods to read only the next token of data of a specific type; the nextInt() method will read and return the very next integer that is available in the scanner’s input stream:

int nextIntInScanner = scanner.nextInt();

**Outputting Data to the Console**

System.out.print("This string will be printed to the console through the OutputStream instance stored in System.out\n");

Java allows us to create output to the console by accessing the static out field of the System class. The out field is a PrintStream instance and also, by inheritance, an OutputStream instance, so it allows us to print data out of our program. In this case, we are printing data out to the console by calling the out field’s print() instance method. The print() method takes a single argument, the String instance to be printed, and prints it to the console inline. If we want to print data on a new line each time, we can call the println() instance method which adds a new line character (‘\n’) to the front of the string we want to print.

***Note!***

The new line character adds a new line to the output wherever it’s placed in a string and we can use it as many times as we want to separate different lines of our output.

**Java for Humans**

71

**Continuously Reading Input from Scanner**

When you play a game, it doesn’t simply ask you for your information, read it, and end. The game uses the information you give it and continues running until you decide to end it. We can do this in Java by continuously reading user input while it is available and the user has not asked to end our program. We do this by using a while loop and some logic. Let’s ask the user for her name and age and decide whether or not to let her play our game. If she is old enough, we will let her know she can play our game and then ask her if she wants to exit or play again:

String userInput = "";

while(!userInput.equals("exit")) {

String userName = "";

int userAge = 0;

System.out.println("Enter your name to begin: ");

if(scanner.hasNext()) {

//get the user's name from the scanner

userName = scanner.next();

}

System.out.println("Enter your age: ");

if(scanner.hasNextInt()) {

//get the user's name from the scanner

userAge = scanner.nextInt();

}

/*check the user's age

to make sure she's at least 13 years old*/

if(userAge >= 13) {

System.out.println("Hi " + userName );

System.out.println("You are old enough to play our game!");

//TODO: write code to play fun game here

System.out.println("Game over!");

System.out.println("Enter YES to play again or EXIT to exit.");

**Learning to Manipulate Data**

72

if(scanner.hasNext()) {

userInput = scanner.next().toLowerCase();

}

} else {

System.out.print("\n\nYou're too young to play this game.

Ending...");

break;

}

}

Notice that we take in the user’s name and age to begin the game. Before we start, we let the user know what’s expected of them and what’s going on throughout the game by creating output when necessary through System.out.

Input and output are necessary for many programs and they allow us to add more interactivity our programs. You are now equipped with all you need to know about input and output to begin making your programs more dynamic. Play around with the code to see what else you can do with input and output.

**Inheritance Primer**

Earlier in this chapter, I said that out is an OutputStream and a PrintStream instance at the same time. By that, I meant that out is an instance of the PrintStream which inherits fields and methods from its super class, the OutputStream class. We will learn more about inheritance and class extension soon, but for now, just know that a PrintStream is an Outputstream. If you had some trouble at that point, don’t worry, we’ll touch on it again soon.

**Java for Humans**

73

**Chapter 5**

**Learning to Build**

**Class Inheritance**

Inheritance is one of the most powerful concepts in all of programming. Without it, it’d be tough to do many of the cool things we do. One of my favorite games as a kid was Conquer 2.0\. The game was fun because you could be anything, and at the same time, each thing was like the others. Yes different and the same at the same time. Isn’t that wonderful? Let me explain.

In Conquer, you can be an Archer, Monk, Ninja, Warrior, or one of two types of a Taoist. The great thing about the game is that no one class is much different from another and if you want to be another class, it isn’t too hard to understand how it works. This is possible because every class is built upon a single class, and, consequently, they all share similar attributes and functionalities. There is no Human class in Conquer, but it is clear that all of the classes mentioned above are humans with distinctive super powers.

An Archer can fly and shoot fire arrows, a Ninja can run fast and attack with stars, a Warrior can wield a sword and a sword, and a Taoist can perform magical acts and heal others. While those classes appear different, they are more alike than you may think. Every class extends the capability of a Human. A Human can jump, attack, and heal itself. Further, every human has a name, health, attack power, and experience. All of that adds up to two attributes and five functions. That’s essentially all it takes to create a game like Conquer. Where it gets fun is when we create the different classes with unique attributes and functionalities while still inheriting all the attributes and functionalities universal to all humans from the Human class. This is where subclassing and inheritance come in.

**Why Inheritance is Important & Useful**

By default, all classes in Java inherit from the Object class provided by Java. Therefore, the Object class is the superclass to all other classes and it defines methods that all its subclasses share. While the Object class only defines the methods its subclasses share, superclasses can define fields their subclasses share as well. This is important because it allows us to have the vital is-a relationship between objects. Even more important is the ability to write parts of our class definition once and share it with other classes that are similar in some ways. This is great for keeping our code DRY (Don’t Repeat Yourself) and encapsulating shared functionalities of our classes in their superclasses.

In our Conquer game, if we know that all classes can jump, attack, and heal as well as have a name, health, attack power, and experience, we can put all of that in a superclass called Human. With a Human superclass, we will only need to add the unique parts of each subclass to the class itself. This will allow us to write less code as well as build a predictable interface for users of our game.

**Learning to Build**

74

**Subclassing & Inheritance**

To have a superclass is to extend, or inherit from, a class. Thus, to be a subclass is to extend a class. Every class in Java can have only one direct superclass from which it inherits some of its fields and methods. However, a class that has a superclass can also be inherited from as to create a chain of inheritance; this is known as class hierarchy.

From its superclass, a class inherits all fields and methods that are not declared as private. This creates a contract between the subclass, its superclass, and the user of the classes. With the contract, the user can expect the behavior of the superclass to be present in its subclasses. However, the contract only goes one way. Fields and methods declared in a subclass are not available in the superclass unless they are declared there, too.

Extending a class is easy in Java. All you have to do is choose a class to extend and write the keyword “extends” followed by the name of the class to extend at the end of your class declaration but before the opening closing brace:

public class Human {

//add fields and methods

}

public class Archer extends Human {

//inherits fields and methods of its Human superclass

//add more fields and methods for this class

}

In that code snippet, we have a Human class which, in theory, has fields and methods. We also have a Archer class which, also in theory, has its own fields and methods and extends our Human class to inherit its fields and methods. Let’s add some fields and methods to our Human class to see how the Archer can inherit them:

public class Human {

protected String name;

protected double health = 100.0;

protected long experience = 0;

protected int attackPower = 1;

public Human(String name) {

this.name = name;

gainExperience(1);

}

**Java for Humans**

75

public long gainExperience(long experience){

this.experience += experience;

return experience;

}

public long addAttackPower(long attackPower) {

this.attackPower += attackPower;

return attackPower;

}

public double heal(double additionalHealth) {

health += additionalHealth;

return health;

}

public void attack(Human opponent) {

opponent.decreaseHealth(attackPower);

}

private void decreaseHealth(int attackPower) {

health -= attackPower;

}

public void jump() {

System.out.println("Jumped up");

}

...

}

Now, instances of every subclass of our Human class will be able to attack other Human instances, be attacked, heal, jump, gain experience, and increase their attack power. Notice that I said that instances of every subclass of our human class will be able to attack other Human instances. I say this because every instance of a class is also an instance of the class’s superclass.

The attack() instance method of our Human class takes a Human opponent as a parameter and drains its health. This is great because we only need to write one attack method that will work on all instances of our Human class regardless of the instance being an Archer, Monk, Wizard, or any other class that extends our Human class. This ispolymorphism at work and we will learn more about it later. Simply put, polymorphism is the idea that we can group many different classes

**Learning to Build**

76

together as being one class, such as saying all archers, monks, and wizards are also humans. They all pass more than one is-a test. Without inheritance, we would have to write a different attack method for each class we may come in contact with. That would be awful.

**Method Overriding**

All classes that extend our Human class will share the same attack method. That means that every subclass of our Human class will attack the same way as the other subclasses of our Human class. This wouldn’t be such a good design because a user is expecting a Warrior to attack with a sword and an Archer to attack with a bow and arrow. Method overriding in Java allows us to accomplish such a design.

A subclass can override the methods of its superclass to implement its own behavior if it is necessary. Method overriding allows a subclass to decide how to implement behavior expected by the user through the inheritance contract. In our game, a user will expect that all classes can attack other classes, but they also expect that each class attacks in a unique way. Therefore, each subclass of our Human class should override the attack() instance method to implement its own attack behavior. This is easy in Java. All we have to do to override a method from a superclass is to add the *@Override* annotation above the method in the subclass:

public class FireArcher extends Archer {

int firePower = 1;

...

@Override

public void attack(Human opponent) {

System.out.println("Attacking " + opponent.getName() + "

with fire arrows!");

opponent.decreaseHealth(attackPower + firePower);

}

}

public class Warrior extends Human {

...

@Override

public void attack(Human opponent) {

System.out.println("Attacking " + opponent.getName() + "

with my sword!");

super.attack(opponent);

}

}

**Java for Humans**

77

public class Monk extends Human {...}

***Note!***

Notice that the FireArcher class extends the Archer class which extends the Human class. This is an example of a class hierarchy from bottom to top:

FireArcher → Archer → Human.

In that code snippet, we have a FireArcher, Warrior, and Monk class. All three classes extend the Human class and inherit its fields and methods, but only the FireArcher and the Warrior class override theattack() instance method of the Human class. The Monk class doesn’t do anything special when it attacks, so it is fine with the basic Human attack() method.

When we override methods of the superclass, we can choose to invoke the superclass’s implementation of that method by accessing the super class through the super keyword provided by Java and calling the method on it at any point in the method. We do this at the end of the overriddenattack() method in the Warrior class but not in the FireArcher class because a FireArcher deals damage to opponents differently than most other classes; with its fire, a FireArcher deals additional damage to an opponent’s health.

Finally, because an instance of a class is also an instance of its superclass, a subclass must implement at least one of the constructor methods that are declared in its superclass and/or invoke the implementation of one of its superclass’s constructors by accessing the super class through the super keyword:

public class Archer extends Human {

private int numArrows = 0;

//1\. this constructor works

public Archer(String name) {

super(name);

findArrows();

}

//2\. this constructor works

public Archer(String name, int startingArrows) {

this.name = name;

numArrows = startingArrows;

}

private void findArrows() {

System.out.println("Looking for arrows");

}

}

**Learning to Build**

78

We must call the superclass’s constructor at the start in of the subclass’s constructor in at least one of the subclass’s constructors. In the second constructor, we don’t have to call the superclass’s constructor because it is called in the first constructor. There are many other rules surrounding the constructors of a superclass and its subclasses, but this is enough to get you started. Try to see how you can break the contract and you will quickly learn the other rules. Finally, notice that we accessed and set the nameinstance field in the Archer class’s second constructor although it is not declared directly in the Archer class. This is only possible because that field, as we learned earlier, is inherited from the Human superclass.

We can now create instances of all our classes — Human, Archer, Warrior, and FireArcher — and expect them to share methods and fields while behaving distinctively:

public class Main {

public static void main(String[] args){

Human human = new Human("Lisa");

Human archer = new Archer("Samuel");

FireArcher fireArcher = new FireArcher("Emmanuel");

Warrior warrior = new Warrior("Carolyn");

human.attack(fireArcher);

archer.attack(warrior);

warrior.attack(archer);

fireArcher.attack(human);

}

}

**Abstract Classes and Interfaces**

In the *Class Inheritance* section, we learned about forming a contract between classes, superclasses, and users. By creating subclasses that share a superclass, we can share fields and methods between them to decrease the amount of code we write, create a predictable interface for users, and employ *polymorphism*. In this chapter, we will learn how to make our contracts better through abstract classes and interfaces.

**Why Abstract Classes & Interface are Important & Useful**

A regular class defines the fields, implements fully functioning methods and can be instantiated; such a class is referred to as a concrete class. That is the vast majority of classes you will write and use in your programming career. Abstract classes and interfaces cannot be instantiated, but they, too, define fields and methods — although they may not implement methods. They are best for forming a contract between a class, its subclasses, and users of its subclasses.

**Java for Humans**

79

**Abstract Class**

An abstract class is much like a regular class in that it can have fields and methods. What makes it special is its methods may or may not have bodies. That means an abstract class can have method signatures that are declared as abstract as well as full methods as usual.

An abstract method is a method that has no body and requires subclasses of the abstract class its in to implement its body. This is useful when you have a method that you want all subclasses to have but you want to leave it up to the different subclasses to implement the method how they want. Further, a subclass of an abstract class must implement all of its abstract methods.

Take the Human class’s attack() instance method from the Class Inheritance chapter for example. We want every subclass of the Human class to have a method of attacking another Human opponent, but we expect each subclass to have a different way of attacking. We should make our attack() method abstract instead of implementing it in the Human class as well as every subclass. That way, we won’t be able to forget to implement it in every subclass and we will keep our code clean by not writing expectantly useless code in our superclass. There are a couple methods of the Human class that we should make abstract, but in order to do that, we must make the Human class an abstract class. To do that, we simply add the abstract keyword to the class’s signature before the class keyword.

public abstract class Human {

//add fields, methods, and abstract methods

}

For methods that we expect to behave exactly the same across all our subclasses, we can write them out in full as usual. Methods such as getters andsetters fit this bill. Further, we can still have our shared fields in our abstract class. Let’s take a look at our new Human class as an upgrade from the *Class Inheritance* section:

public abstract class Human {

protected String name;

...

public Human(String name) {...}

public abstract void attack(Human human);

public abstract void defend();

public abstract void jump();

public abstract double heal();

public String getName() {...}

**Learning to Build**

80

public double getHealth(){...}

public long getExperience(){...}

public void setAttackPower(int attackPower) {...}

public long gainExperience(long experience){...}

public double heal(double additionalHealth) {...}

public double decreaseHealth(int opponentAttackPower) {...}

}

In that code snippet, you can see that we have our Human class and its attack(), defend(), jump(), andheal() instance methods are abstract. This is because they are all functions that should be unique to each class that implements them; Taoist instances — magical characters — won’t heal the same way as Warrior instances, so they should implement theheal() method differently. You’ve seen the rest of the class before, so those parts have been omitted.

***Note!***

At this point, it is important to note that static methods cannot be abstract because in simplest terms, abstract means that a method implements no functionality and static means there is definitely functionality available in the method or field even without an instance of the class. Thus, having a static abstract method would be would be a logical contradiction which Java does not allow.

**Interfaces**

An interface is a bit different than anything we’ve seen thus far. A Java interface is more like an abstract class than a regular class. An interface can only contain method signatures and static finalfields. An interface is merely a contract between the interface and classes that implement it. Like with abstract classes, classes that implement an interface must implement its methods’ bodies to provide functionality.

Interfaces are best for creating a contract that will ensure that all classes that implement it behave similarly by abiding by the contract. This will allow users to safely expect parts of your program to behave similarly much like you would expect all characters in a fighting game to behave similarly. In our Conquer game from the Class Inheritance chapter, we expect all characters to be able to attack other characters, defend themselves from attacks, jump, and heal themselves among other functions. These functions are functions all characters can perform, not only Human instances:

public interface Character {

Random randomGenerator = new Random();

String getName();

double getHealth();

long getExperience();

int getAttackPower();

**Java for Humans**

81

void setAttackPower(int attackPower);

void defend();

void jump();

int heal();

void attack(Character opponent);

double decreaseHealth(int opponentAttackPower);

long gainExperience(long experience);

}

In the Character *interface*, *numCharactersInGame* field is implicitly *static* and all of the methods are implicitly *public*, so there’s no need to include the*static* and *public* modifiers respectively.

***Note!***

A top-level *interface* cannot be private. Also, all methods of an *interface* are intuitively *public*, so don’t include any methods you think should be*private* or *protected*.

Say we want to allow our Human characters to have Pet characters as their companions, we would expect that Pet instances can do things like attack, defend, jump, and heal but not other things that are unique to Human instances. Further, we may have many different types of pets; a user may want to have a dog, cat, or a bird as a pet. For that, we would have a Dog class, Cat class, and a Bird class. Each of those classes would, in turn, extend the Pet class which will define shared instance fields, implement shared methods, and declare the abstract methods that all subclasses must implement.

***Note!***

From bottom to top, the hierarchy of concrete classes, abstract classes, and interface goes like so:

concrete class → abstract class → interface.

If a class extends a superclass — concrete or abstract — that implements an interface, you can declare the necessary methods from the interface in the superclass. Doing this will fulfill the subclass’s duty to abide by the contract between it and the interface because your subclass will inherit the necessary methods of the contract from its superclass. Alternatively, the class can implement the interface methods on its own.

Let’s take a look at our abstract Pet class and our concrete Archer and Dog subclasses; we will make use of the Character interface and abstract Human class from earlier:

public abstract class Human implements Character{

protected Pet pet;

...

**Learning to Build**

82

public Human(String name) {

...

numCharacters++;

}

public void setPet(Pet pet) { this.pet = pet; }

public Pet getPet() { return pet; }

public abstract void attack(Character opponent);

...

}

public abstract class Pet implements Character{

protected Human owner;

...

public Pet(String name, Human owner) {

this.name = name;

this.owner = owner;

gainExperience(1);

numCharacters++;

}

public Human getOwner() { return owner; }

public abstract void attack(Character opponent);

...

}

public class Archer extends Human {

private int numArrows = 0;

public Archer(String name) {

super(name);

findArrows();

}

private void findArrows() {

System.out.println("Looking for arrows");

}

**Java for Humans**

83

@Override

public void attack(Character opponent) {...}

@Override

public void defend() {...}

@Override

public void jump() {...}

@Override

public int heal() { return 0; }

}

public class Dog extends Pet {

public Dog(String name, Human owner) {

super(name, owner);

}

public void bark() {

System.out.println("Wolf Wolf!");

}

@Override

public void attack(Character opponent) {...}

@Override

public void defend() {...}

@Override

public void jump() {...}

@Override

public int heal() { return 0; }

}

Now we have a wonderful contract set up between subclasses, abstract superclasses, and an interface to rule them all. The Character interface defines the behavioral interface for all characters in the game. The Human abstract class implements the Character interface and defines behavior and fields for all human characters in the game. The Human class also implements some of the methods of the Character interface that are common for all Human characters. The Archer class is a concrete class that extends the Human class and is used to create archer characters in the game. Furthermore, the Archer class also implements the Character interface because its superclass, Human, does. Therefore, Archer instances are also Human instances and since Human instances are also instances of the Character interface, Archer instances are Character instances. Thus, Archer instances are archer and

**Learning to Build**

84

human characters. That gives us the following hierarchy, from bottom to top:

*Archer instance → Archer concrete class →Human abstract class → Character interface.*

The Dog concrete class and the Pet abstract class work similarly with our Character interface:

*Dog instance → Dog concrete class → Pet abstract class → Character interface.*

An Archer is a Human is a Character. A Dog is aPet is a Character. Therefore, both an Archer and a Dog are equally Character instances like all other Human and Pet instances would be if you create more classes that extend those abstract classes or implement the Character interface.

You should be proud of yourself at this point. You now know everything you need to know about classes, interfaces, and contracts to get started building fun projects that employ polymorphism. Here’s a starter program:

public class Main {

public static void main(String[] args){

Archer niceArcher = new Archer("Tom");

Human modernArcher = new Archer("Stacy");

Dog modernDog = new Dog("Hunter", modernArcher);

Pet petDog = new Dog("Buddy", niceArcher);

System.out.println("\nStart Game\n");

modernArcher.attack(niceArcher);

niceArcher.getPet().attack(modernArcher);

modernArcher.attack(niceArcher.getPet());

modernDog.attack(petDog.getOwner());

petDog.attack(modernArcher.getPet());

}

}

**Java for Humans**

85

***Output***

*Tom: Found 6 arrows ...*

*Stacy: Found 4 arrows ...*

*Stacy: I have a new pet. Hi Hunter!*

*Hunter: Wolf Wolf!*

*Tom: I have a new pet. Hi Buddy!*

*Buddy: Wolf Wolf!*

*Start Game*

*Stacy: Attacking Tom with my arrows!*

*Tom: I've been hit. My health now = 90.0*

*Buddy: Biting Stacy*

*Stacy: I've been hit. My health now = 99.0*

*Stacy: Attacking Buddy with my arrows!*

*Buddy: Wolf Wolf!*

*Buddy: Health now = 90.0*

*Hunter: Biting Tom*

*Tom: I've been hit. My health now = 89.0*

*Buddy: Biting Hunter*

*Hunter: Wolf Wolf!*

*Hunter: Health now = 99.0*

Polymorphism is the ability for objects to take on many forms. Notice that the *niceArcher* is of type Human but is instantiated as a new Archer. That means that the *niceArcher* passes more than oneis-a test because its both a Human and an Archer. Furthermore, notice that each object can attack all other objects. This is only possible because each object is also an instance of the Character interface, and the attack() instance method of Character takes another a Character instance as the single argument. With all of that, we can say that these objects are polymorphic.

Remember that if you don’t quite understand the importance of polymorphism yet, we will cover it in more depth soon. For now, take a look at the supporting code and make sure you understand it. Try to change it around and make your own contracts.

**Learning to Build**

86

**Chapter 6**

**Learning to Organize**

**Data Structures**

A data structure is exactly what it sounds like — a structure that holds data. Unlike variables, which only hold a single point of data, data structures collect one or more points of data of the same type. Although a data structure can hold many points of data, a data structure, itself, is only a single object that can be stored in a variable like any other datatype. A data structure’s type becomes the type of the data points it holds. For that reason, a data structure is sometimes referred to as a container object, or a collection. Some data structures can expand infinitely in size, but others, like arrays have a fixed size.

**Arrays**

In your phone, you have a phone book filled with names and numbers of family and friends. The good thing about your phone book is it holds many contacts, but the bad is that it is limited, although you may not know it. Your phone book can only hold a predetermined number of contacts. You can add new contacts, update contacts, and delete contacts. With that said, your phone book is a *data structure*. More specifically, it is an array. We will learn how to make a phone book with an array in this section.

**Why Arrays are Important & Useful**

In the Variables chapter, you learned how to store a single data point in a variable. Then, in the Datatypes chapter, you learned that its best to store data of a certain type in a variable with that respective type: store a character string in a String variable, store a whole number, integer in an int variable, store a floating point number in adouble variable, and so on. Now that we are becoming more advanced Java programmers, we want to store a collection of data in a single data structure for later manipulation.

**Using Arrays**

An *array* is a data structure that holds a fixed number of values (data points) of the same type. Each item, or value, in an array is called an element, and each element is accessed by its integer index. When we initialize an array, we get to choose what type of data it can hold and how many elements it can hold.

**Java for Humans**

87

***Note!***

The number of elements an array instance can hold is stored in its *final int* field called *length*. A final field cannot be changed after it is set, and therefore, a final field is often referred to as a*constant* field. This *length* property of the array is what allows it to be of a fixed size.

We initialize an array instance like we initialize an instance of any other object in Java. The difference with arrays is that next to the type of array, we add a set of empty opening and closing brackets. Further, at the end of the initialization,we put the number of elements the array can hold inside a set of opening and closing brackets. There a few other ways to initialize arrays, but this is the most popular and flexible way. Let’s initialize an array of strings to hold the names of our five friends:

String[] friends = new String[5];

In that code snippet, we created an array calledfriends to hold a maximum of five String values — the names of our friends. Now that we have our array instance, we can access each element of the array by accessing its index in the array. Because indices in Java are zero-based, the first element in an array is stored at index zero (0) and the last element is at index of one less than the length of the array. Therefore, if we want to access our first friend, we would access index 0.

At initialization, all elements in in the array are initialized to a zero value: null for arrays of objects, 0 for primitive number types, and falsefor boolean types. Let’s add our friends to the array before we try to get them out:

friends[0] = "Imani";

friends[1] = "Andres";

friends[2] = "Keith";

friends[3] = "Sasha";

friends[4] = "Tabitha";

Now that we have added our five friends to ourfriends array, let’s access the first and last one and print them out:

String firstFriend = friends[0];

System.out.println("First friend is " + firstFriend);

System.out.println("Last friend is " +

friends[friends.length - 1]);

***Output***

*First friend is Imani*

*Last friend is Tabitha*

Notice that we were able to access the last element in our friends array by doing a little math. We

**Learning to Organize**

88

used the *length* property of the array to get the total number of elements in it array and subtracted one from that number to get the index of the last element. That is the dynamic way of accessing the last element, but we could have just as easily typed friends[4] to access the fifth (last) element in our array of five friends. In the unfortunate event that we lose a friend, we should zero out the value of the element in our array that corresponds to our lost friend. If we lose our first friend and our second friend changes her name, we can reflect those updates in our array like so:

friends[0] = null;

friends[1] = "Alejandro";

System.out.println("First friend is now " + friends[0]);

System.out.println("Second friend changed name to " + friends[1]);

***Output***

*First friend is now null*

*Second friend changed name to Alejandro*

Now our first friend equals null and our second friend, Andres, changed his name to Alejandro. Let’s make another array to hold the corresponding phone numbers of all our friends as integers:

int[] friendsPhoneNumbers = new int[friends.length];

friendsPhoneNumbers[0] = 555_8000;

friendsPhoneNumbers[1] = 5554448;

friendsPhoneNumbers[2] = 555_4311;

friendsPhoneNumbers[3] = 555_7898;

friendsPhoneNumbers[4] = 555_6710;

Our friendsPhoneNumbers array is initialized with the value of the length property of our friendsarray to ensure they both have the same number of elements.

***Note!***

Notice that some of the phone numbers have underscores in them. Using underscores in long numbers, like commas on paper, make them easier to read. You can add underscores between numbers, not at the start nor end.

We can loop over, or traverse, our array of friends to print out the name of each of our friends by using a *for* loop terminated by the length of our array:

**Java for Humans**

89

for(int index = 0; index < friends.length; index++) {

System.out.printf("Friend %d: %s\n", index, friends[index]);

}

***Output***

*Friend 0: null*

*Friend 1: Alejandro*

*Friend 2: Keith*

*Friend 3: Sasha*

*Friend 4: Tabitha*

We can go even further and print out each friend’s phone number from ourfriendsPhoneNumbers array next to his/her name. However, we should only print a friend’s phone number if their name is not equal to (!=) null:

for(int index = 0; index < friends.length; index++) {

String friend = friends[index];

if(friend != null) {

System.out.printf("Friend %d: %s's phone number is %d\n",

index, friend, friendsPhoneNumbers[index]);

} else {

System.out.println("#Alert: No friend at index " + index);

}

}

***Output***

*#Alert: No friend at index 0*

*Index 1: Alejandro's phone number is 5554448*

*Index 2: Keith's phone number is 5554311*

*Index 3: Sasha's phone number is 5557898*

*Index 4: Tabitha's phone number is 5556710*

Notice that we don’t print the element at index 0 in either array because we lost our first friend earlier; the element at index 0 in the friends array is now null, so the corresponding phone number at index 0 in the friendsPhoneNumbers array is now useless to us. One more thing we can do to make our phone book more intuitive is consolidate our two arrays into one. The new array will hold Friend objects instead of String and int values.

***Note!***

Remember that, by default, all classes extend the Object class provided by Java. The *toString()*instance method of the Object class is called whenever the compiler tries to convert an object to a String.

**Learning to Organize**

90

Our Friend class will have three instance fields:name, areaCode, and phoneNumber. Our Friend class will override the toString() instance method of its Object superclass to return all of a Friend instance’s information as a single String instance:

public class Friend {

private String name;

private int phoneNumber;

private int areaCode;

...

@Override

public String toString() {

return String.format("Name: %s | Phone Number: (%d)-%d",

name, areaCode, phoneNumber);

}

}

***Note!***

In that snippet, we used the format() staticmethod of the String class to map values to placeholders in our String.

Let’s create an array of type Friend to hold all of our friends’ contact information like a phone book does:

Friend[] phoneBook = new Friend[5];

phoneBook[0] = new Friend("Imani", 215, 555_8000);

phoneBook[1] = new Friend("Andres", 484, 5554448);

phoneBook[2] = new Friend("Keith", 319, 555_4311);

phoneBook[3] = new Friend("Sasha", 212, 555_7898);

phoneBook[4] = new Friend("Tabitha", 212, 555_6710);

Our friend, Imani, from earlier decided to give us another chance, so we added her to our phone book in her original spot, index 0\. Now, we can more intuitively loop over our phone book array to print out each of our friends and their contact information:

**Java for Humans**

91

for(int index = 0; index < friends.length; index++) {

Friend friend = phoneBook[index];

if(friend != null) {

System.out.println("Friend " + index + " -> " + friend);

}

}

***Output***

*Friend 0 -> Name: Imani | Phone Number: (215)-5558000*

*Friend 1 -> Name: Andres | Phone Number: (484)-5554448*

*Friend 2 -> Name: Keith | Phone Number: (319)-5554311*

*Friend 3 -> Name: Sasha | Phone Number: (212)-5557898*

*Friend 4 -> Name: Tabitha | Phone Number: (212)-5556710*

The last thing you should know about arrays holding objects is that when you want to update an element at an index, you don’t need to update the entire element. You can simply get the element and update the field you need to update or call the method you want on the object. Let’s change our second friend’s name from Andres to Alejandro again and print it out:

Friend friend2 = phoneBook[1];

friend2.changeName("Alejandro");

System.out.println(friend2);

***Output***

*Name: Alejandro | Phone Number: (484)-5554448*

If we lose our friend, Imani, again, we can remove her from our phone book array the same way we did earlier in our friends array:

phoneBook[0] = null;

System.out.println(phoneBook[0]);

***Output***

*null*

That’s it. We now have a phone book we can add to, update the elements of when a friend changes his or her contact information, and delete elements from when we lose a friend. It is clear that arrays are useful when you want to store a collection of values — objects or primitives — of the same type in one place for later use. The only constraint is that an array must have a fixed length of elements. In the next chapter, we will learn about lists which can dynamically expand in capacity when necessary.

**Learning to Organize**

92

**Lists**

Our phone book from the Arrays chapter could only hold a fixed number of our friends’ contact information because it was made with an array. We bounded our phone book by implementing it as an array because it makes sense: your phone only has a limited amount of storage space, so we can only store a limited amount of contacts. Arrays are best when you know how many elements you will be collecting, but there are other situations where it doesn’t make sense to bound the capacity of our collection. For those situations, dynamically expanding lists are best.

Why Lists are Important & Useful

Unlike arrays, lists in Java can expand without bounds. You may use a list to accumulate and collect things you don’t know the bounds of, such as the people you meet in your life time, the places you’ve been, the skills you learn, the movies you want to watch. If you’ve ever heard of a “Bucket List”, it is the best application of a list: toss everything you want to do into the bucket and mark them as done as you accomplish them.

The Java List class is an interface from which we can implement any kind of list subclass we’d like. Java provides us two popular implementations of the List interface — LinkedList and ArrayList — but we will focus on the LinkedList in this chapter because you already know much of how an ArrayList works; an ArrayList is simply an array with convenient instance methods and a dynamically expanding capacity.

LinkedLists

A LinkedList is a special type of data structure that allows us to link elements together in a line without bounds. Elements of a LinkedList are referred to as nodes and each node has a pointerfield pointing to its left neighbor and another pointing to its right neighbor.

A node has a minimum of three instance fields: its two pointers which are int values, and its datafield which holds the actual data. The datatype of a LinkedList, or any data structure for that matter, is the datatype of its elements and all elements must be of the same type.

There are only six functions you need to know to get started working with the LinkedList class. LinkedLists have a size() instance method that returns the number of nodes in the list. You can add elements to a LinkedList by passing the object as an argument to the list’s add() instance method. If you want to check if an object is already in the list before you try to add it again, you can call the contains() instance method and provide it the object to check as an argument.

When you want to access an element of a list, you must provide its position in the list as an argument to the list’s get() instance method. A reference to the object stored in the node at that position in the list will be returned. If you want to remove an element from the list, simply pass its position as an argument to the list’s remove()instance method. Finally, you can remove all elements from the list by calling the clear()method.

When we initialize our LinkedList, we must specify the type of data that can be stored in our LinkedList. To do that, we place the type’s class name between a set of opening and closing arrows <>. Let’s see how we can use a LinkedList instance to make our bucket list of things we want to do this year:

**Java for Humans**

93

public class Thing {

...

@Override

public String toString() {

if(done) { return name + " is done.";}

else { return name + " is not done";}

}

}

LinkedList<Thing> bucketList = new LinkedList<Thing>();

Our Thing class has only two instance fields: a String name and a boolean done. We can get the name of a Thing instance by calling thegetName() instance method and we can mark a Thing as done by calling the markDone()instance method. We can check if a Thing is done by calling its isDone() instance method. Finally, our Thing class overrides the toString() instance method of its implicit superclass, Object. Let’s add some things to do to our bucket list:

bucketList.add(new Thing("Bungee Jump"));

Thing learnJava = new Thing("Learn Java");

bucketList.add(learnJava);

bucketList.add(new Thing("Build an Android Application"));

bucketList.add(new Thing("Travel to the Bermuda Triangle"));

We want to go bungee jumping, learn Java, build an Android application, and travel to the Bermuda Triangle. We are currently learning Java, so we can’t mark it as done just yet. Say we complete bungee jumping, we can mark the “Bungee Jump” Thing as done by calling the get() method on our bucketList object to get it and call its own markDone() instance method on it. Because “Bungee Jump” is the first element in the list, its position is zero (0):

Thing bungeeJump = bucketList.get(0);

bungeeJump.markDone();

To get the first or last element of the list, we could also call its getFirst() or getLast() instance methods respectively. Let’s traverse our bucket list and print out everything we have to do:

**Learning to Organize**

94

for(int position = 0; position < bucketList.size(); position++){

Thing thingToDo = bucketList.get(position);

System.out.println("Thing at position " + position

+ ": " +thingToDo);

}

***Output***

*Thing at position 0: Bungee Jump is done.*

*Thing at position 1: Learn Java is not done*

*Thing at position 2: Build an Android Application is not done*

*Thing at position 3: Travel to the Bermuda Triangle is not done*

From that code snippet, we can see that we are looping over, traversing our bucket list by using the increasing position value to retrieve elements from the list by their position in the list. The first element, “Bungee Jump”, is rightfully the only Thing in the list that is “done”. We’ve traveled to the Bermuda Triangle, so we’ll mark that as done, too. At the end of each day, we should remove everything that we have done from our list:

bucketList.getLast().markDone();

for(int position = 0; position < bucketList.size(); position++){

Thing thingToDo = bucketList.get(position);

if(thingToDo.isDone()) {

bucketList.remove(thingToDo);

}

}

System.out.println("Things left to do: " + bucketList.size());

***Output***

*Things left to do: 2*

Now we only have two things left in our bucket list. Let’s imagine we have read all the way through Java for Humans and developed an Android application. That would mean we can mark those two things as done on our list. Given that we only have those two things left, instead of removing them one at a time, we can simply empty our entire bucket list by clearing our LinkedList:

bucketList.clear();

System.out.println("Things left to do: " + bucketList.size());

***Output***

*Things left to do: 0*

**Java for Humans**

95

Now our bucket list is empty. However, we lied about having learned Java, so let’s add that back to our bucket list and make sure it was successfully added by checking if the list contains it:

System.out.println(bucketList.contains(learnJava));

bucketList.add(learnJava);

System.out.println(bucketList.contains(learnJava));

System.out.println(bucketList.contains(new Thing("Learn Java")));

***Output***

*false*

*true*

*false*

***Note!***

The contains method only returns true if the provided object is a reference to an object in the list. Although the two Thing instances with a name value of “Learn Java” appear to be the same, they are not because they don’t reference one another. This is something you should do some more research on because its beyond the scope of this book.

One final method you should be aware of is the isEmpty() instance method. It returns true if the list has no elements in it.

That’s it. We have used all of the essential instance methods of a LinkedList and those methods are all in other implementations of the List interface. Try to expand your bucket list here by adding more Java concepts you want to learn to the list.

**HashMaps**

Arrays let you collect a fixed amount of elements in one data structure, and Lists can do the same but without bounds. The only thing they both don’t allow you to do is store objects and retrieve them by a specific, unique key. This is where theHashMap comes into play. If we want to make a dictionary of all the words in the English language alongside their meanings, our best bet would be to use a HashMap.

**Why HashMaps are Important & Useful**

Maps in Java are powerful tools, and the HashMap is perhaps one of the most powerful of them all. The HashMap class, an implementation of the Map interface, takes the best ideas of the List interface, combines it with the prowess of arrays, and gives us a tool to collect key-value pairs in one place. Elements of a HashMap are stored as pairs and it insures that no two pairs can have the same key, therefore maintaining the unique property of each of element.

**Learning to Organize**

96

The HashMap class provided to us by Java allows us to collect values of the same type and store them with unique keys. In the background, a HashMap uses arrays to store its elements. However, we don’t care about how it works in the background because all of the hard work is encapsulated. The HashMap class provides us methods to put a pair in the map, replace a pair’s value by key, remove a pair by key, check for the existence of a key, and clear the map like we do with a list.

A key can be of any datatype, but its important to remember that String keys are case sensitive. To ensure that all keys in the HashMap are unique, the map has a hash() method behind the scenes to hash all keys added to it. When you call theput() instance method, the key you provide is hashed to a unique hash string value and when you call the get() or containsKey() instance methods, the key you provide is hashed the same way. The hash that results is used to find a pair in the map that has a key with a matching hash. If a pair is found, the pair will be returned if you called get(), a boolean value of true will be returned if you called containsKey(), or its value will be updated with the new value if you calledput(). Let’s try to make a dictionary of some of our favorite Java terms to help us study later:

HashMap dictionary = new HashMap();

dictionary.put("Variable", "Used to store a single value " + "for later use.");

dictionary.put("String", "A class for representing character " + "strings.");

dictionary.put("double", "A primitive datatype for " + "representing floating point numbers.");

dictionary.put("Double", "A class for wrapping a double in an " + "Object with convenient methods.");

dictionary.put(0, "The number zero. The first index in arrays " + "and the first position in lists.");

dictionary.put("zero", 0);

System.out.println("Elements in map: " + dictionary.size());

***Output***

*Elements in map: 6*

We’ve added six pairs to our dictionary HashMap instance — five String keys and one integer key. Let’s print out the value of some of the pairs by key:

System.out.println("double: " + dictionary.get("double"));

Object meaningOfDouble = dictionary.get("Double");

Object meaningOf0 = dictionary.get(0);

**Java for Humans**

97

System.out.println("Double: " + meaningOfDouble);

System.out.println("0: " + meaningOf0);

System.out.println("zero: " + dictionary.get("zero"));

***Output***

*double: A primitive datatype for representing floating point numbers.*

*Double: A class for wrapping a double in an Object with convenient methods.*

*0: The number zero. The first index in arrays and the first position in lists.*

*zero: 0*

Notice that when we retrieved the value of the elements of our dictionary, they were returned as instances of the Object class. This is because if we do not specify which type of data our keys and values can be, Java makes Object the type of the HashMap’s keys and values because every class is a subclass of the Object class; the Integer, Double, Long, and other wrapper classes are provided by Java to wrap primitive datatypes in objects because primitives are not objects. This is why we were able to have both String and int keys and values. This is okay sometimes, but we should usually specify exactly what type of data we want to store in our data structures to avoid unexpected situations that can result from ambiguity. To specify the type of our map, we do the same thing we did to initialize our LinkedList instance in the LinkedLists chapter: place the type’s class name inside of a set of opening and closing arrows <>. We could make our HashMap instance accept, String keys and Integer values, but doesn’t make much sense for our dictionary .Let’s remake our dictionary to only accept String keys and String values:

HashMap<String, String> stringDictionary = new HashMap<>();

stringDictionary.put("Class", "A template for creating objects.");

stringDictionary.put("Object", "An instance of a class.");

We now have a dictionary that stores pairs of String keys and String values and it has the definition of a Java “Class” and “Object”. The “Class” definition seems a little unhelpful, so let’s update it:

stringDictionary.replace("Class", "A template that defines the " + "attributes and behaviors that objects " + "constructed from it can exhibit.");

Instead of calling the put() method again to change the value of the “Class” key in our map, we called the replace() instance method. Calling replace()ensures that the pair will not be added to the map if the key was not already present in the map. If we had called put() instead, the pair would have been added to the map even though we only intended to update the value of the pair. For that reason, you should use replace() to update the value of a pair with a key you know exists in a HashMap and useput() if you want to update the value of a pair with a key you wouldn’t mind adding to your map if it doesn’t already exist. The best of both worlds, often the better design pattern, would be to check if the key exists in our map before we replace it:

**Learning to Organize**

98

if(stringDictionary.containsKey("Class")) {

stringDictionary.replace("Class", "A better definition.");

} else {

stringDictionary.put("Class", "A descriptive definition");

}

String meaningOfClass = stringDictionary.get("Class");

System.out.println("Class: " + meaningOfClass);

***Output***

*Class: A better definition.*

In that code snippet, we replaced the value of the pair if the key already existed in the map and we added the pair to the map otherwise by checking with containsKey(). If we want to remove a pair from our map, we don’t have to make sure it exists first. We can simply ask the map to remove the pair with a key matching the key we provide as an argument to the remove() method. If the key exists in the map, the corresponding value will be removed return, and otherwise, nothing will be removed and returned:

String valueOfRemovedPair = stringDictionary.remove("Class");

System.out.println("Value of removed 'Class': " + valueOfRemovedPair);

***Output***

*Value of removed pair with key 'Class': A better definition.*

The only thing left to do is clear our dictionary and start over. If we no longer need the pairs in our HashMap, we can remove all of them at once by calling the clear() method:

stringDictionary.clear();

System.out.println("Pairs in our string dictionary: " + stringDictionary.size());

***Output***

*Pairs in our string dictionary: 0*

Our *stringDictionary* HashMap is now empty and you are free to add new pairs to it and use it to study up on everything you have learned about Java so far.

**Java for Humans**

99

You could make a study guide by adding each concept to the HashMap along with its meaning, iterate over the map’s keys with a *for loop* or Java’s handy iterator method which you can learn about by doing some research on Google, and try to guess the corresponding value of each key before you print it to the console. I’ll get you started in the supporting code.

**Polymorphism**

In our short look at polymorphism at work in both the Class Inheritance and Abstract Classes & Interfaces chapters, we got a glimpse at how powerful polymorphism is. In both chapters, we learned that any object that can pass more than oneis-a test, that is any object that is of more than one type, is considered polymorphic. With that said, we can define polymorphism as the ability of an object to take on more than one form.

Why is Polymorphism Important & Useful

Polymorphism is one of the most important concepts in object oriented programming. It is what allows us to say that all types in Java are the type of its class as well as the type of the Object class; we’ve learned that all objects in Java are instances of the Object class because of Java’s class hierarchy.

One Functionality for All

We learned in the Class Inheritance chapter that If we can say an instance of a class can be of more than one type, we can build functionality for one class that works for any class that extends it. We created a Human class that our Warrior, Archer, and FireArcher all inherited from. That allowed us to create methods that accepted them all as parameters because we could group them all as being Human. That is polymorphism at work.

One Collection for All

Remember in the three Data Structures chapters that with any data structure, collection, we can only store elements of the same type: each element of a String array must be of type String and each element in a Human LinkedList must be of type Human. In the HashMaps chapter, we saw that if we don’t explicitly specify the type of our keys and values, Java implicitly sets the map to store keys of type Object and values also of type Object because every class in Java extends the Object class provided by Java. This is only legal because of polymorphism. Let’s revisit our Conquer game example from earlier to see how we can collect all our friends in the game in a single list.

***Note!***

The classes of the different characters in the game will be omitted from this chapter, so make sure to open the supporting source code.

Remember that we have a Character interface that every character class implements, an *abstract*Human class that all human character class extends, and an abstract Pet class that all pet classes extend. We will focus on the Human class and its subclasses because while a user can have a

**Learning to Organize**

100

pet, a user who plays our game can only be a human character. Let’s create a Human instance for ourself, currentUser, and a couple Human instances to represent other users:

//the Human character representing the current user

Human currentUser = new Archer("ModernNerd");

//other Human characters playing the game

Archer human2 = new Archer("Tom");

Human human3 = new FireArcher("Christina");

Warrior human4 = new Warrior("Tyrone");

Taoist human5 = new Taoist("Jerome");

We are the currentUser Human instance which is also an Archer instance. Notice that human3 is like our character: its of type Human but is instantiated as a FireArcher. Again, that’s the beauty of polymorphism. Let’s take a look at the Human class:

public abstract class Human implements Character {

private LinkedList<Human> friendsList = new LinkedList<>();

...

public LinkedList<Human> getFriends() {

return friendsList;

}

...

}

It has a LinkedList, friendsList, that accepts Human instances as elements. We will use this to hold our list of friends. Let’s get it and store a reference to it in a local variable and add the other characters to it because they are our friends:

/*store a reference to current user's

friend list in a local variable*/

LinkedList<Human> currentUserFriendsList = currentUser.getFriendsList();

**Java for Humans**

101

//add other user's to current user's friend list

currentUserFriendsList.add(human2);

currentUserFriendsList.add(human3);

currentUserFriendsList.add(human4);

currentUserFriendsList.add(human5);

System.out.printf("Current user has %d friends.", currentUser.getFriendsList().size());

***Output***

*Current user has 4 friends.*

Now we have four friends in our list. Remembered that each element in our list is stored as a Human instance, so if we want to retrieve a friend from the list, it will be returned as a Human. Let’s retrievehuman2, “Tom”, which is also an Archer:

Human ourFriendTomTheHuman = currentUserFriendsList.get(0);

if(ourFriendTom instanceof Archer) {

System.out.println("\nOur friend Tom is an instance of " + "the Archer clas.s");

Archer ourFriendTomTheArcher = (Archer) ourFriendTomTheHuman;

System.out.println("Tom can find more arrows for battle.");

ourFriendTomTheArcher.findArrows();

} else {

System.out.println("\nOur friend Tom is NOT an instance of " + "the Archer class");

//ourFriendTom.findArrows(); doesn't work

System.out.println("Tom cannot go find arrows because he " + "is not an Archer");

ourFriendTomTheHuman.attack(currentUser);

}

***Output***

*Our friend Tom is an instance of the Archer class.*

*Tom: Found 5 arrows!*

*Tom: I now have 8 arrows.*

**Learning to Organize**

102

There’s a couple new things happening in that code snippet, so let’s walk through it line by line. In the first line, we call the get() instance method on our LinkedList holding our friends and get the first element which is at index zero (0). This is Tom who we know was an archer before we added him to the list. However, he was returned to us as a Human, so we call him ourFriendTomTheHuman for now.

**Type Casting**

If we want to turn Tom back into an Archer, we must cast him to one. Type casting in Java is the act of casting, or converting, one type, a class or interface, into another type. As usual, we should check to make sure Tom is actually an Archer disguised as a Human before we try to cast him back to an Archer. We do the check in the next line of code by using the instanceof operator in an if-thenstatement. The instanceof operator returns true if the object on the left is an instance of the class on the right, and it returns false otherwise. In this case, it returns true because Tom is indeed an instance of the Archer class as we already knew. Now we are inside the first block of the if-then statement.

After printing that Tom is an instance of the Archer class, on the next line, we cast theourFriendTomTheHuman object to an Archer and save this new copy of Tom to a new Archer variable called ourFriendTomTheArcher. As you can see, totype cast an object, we simply put the class of type we want to cast our object to inside of a set of opening and closing parenthesis to the left of the variable holding the object.

***Note!***

You can type cast primitive values like ints and doubles, too. Do some more research on type casting because it is a handy tool.

Now that we have converted Tom from being a Human back to an Archer, we can call itsfindArrows() instance method so it can find more arrows to use in battle. If we had not converted Tom back to an Archer, he could not call the findArrows() instance method because he would not be of type Archer. However, Tom could always call the attack() instance method of Human because all Human instances have an attack method. This is where it gets a little tricky, so stick with me:

ourFriendTomTheHuman.attack(human3);

***Output***

*Tom: Attacking Christina with my arrows!*

*Christina: I've been hit. My health now = 99.0*

Because Tom was instantiated as an Archer before being added to our LinkedList of Human objects, he still has access to the abstract Human methods that were already implemented by the Archer class and made available to Tom when he was instantiated. With that said, if we make ourFriendTomTheHumanattack human3, “Christina”, he still attacks with his arrows. The only

**Java for Humans**

103

problem here is, becauseourFriendTomTheHuman would not be able to find arrows after he uses it all, his attack() method will be useless at that point. That is why we should cast him back to an Archer.

By now, I hope you understand why polymorphism is so special to object oriented programming. Moving forward, be sure to employ polymorphism in your Java programming career. Take a look at the supporting source code and change things around to practice more.

**Learning to Organize**

104

**Chapter 7**

**Applying Knowledge**

**Building a Fighting Game With a GUI**

Congratulations on making it this far. Really, you have accomplish a great feat. The final test of how far you have come is for you to build your first graphical user interface game in Java. I have developed the entire game for you, and in this chapter, I will touch on the purpose of each class. With that knowledge, you will be able to reconstruct the entire project from the ground up.

If you remember the game we discussed in the Abstract Classes & Interface chapter, you will be glad to know we are using the character classes we created then in our game. We are going to mimic the “Conquer” MMORPG game. In Conquer, each character has a name, some set of special skills, a pet, health, attack power, defense power, and the ability to speak. Also, each user can select the type of character they want to be. However, there are two types of characters and users can only choose to be a Human character. A Human character can then have a Pet character. Each character battles until there’s a winner. Our game will emulate all of this.

Because we make use of polymorphism, the model-view-controller programming pattern, and interfaces, the application is quite easy to navigate. I have documented the source code of this project in great detail by commenting virtually every line of code and providing javadocs for each method, class, and interface. With that said, I will not spend much time explaining the intricacies of the project’s code base in this chapter.

The package for this chapter’s supporting code is called “buildingAGame”. Please have it open as we walk through it to at a high level to understand what’s going on. Lets take a look at the fourteen classes and one interface of our game and walk through each class to see how we apply all of the knowledge we’ve accumulated in this book.

**Characters**

The most important part of our game are the characters because there wouldn’t be much action without them. Every player in the game is a character, so we have a Character interface. Any class that intends to create a template for constructing characters that can play in our game must implement our Character interface. To make that implementation easier, we have an abstractAbstractCharacter class which implements the most general methods of the Character interface.

The AbstarctCharacter class must be extended by any class that intends to create a template for constructing characters that can play in our game. The AbstractCharacter class implements all but two of the methods from the Character interface. That means that any class that extends our AbstractCharacter class only has to implement theattack() and train() instance methods from the Character interface. We have left those two methods for subclasses to implement because it is

**Java for Humans**

105

intuitive that different types of characters attack and train in distinct ways: an Archer attacks with arrows, a Warrior attacks with a sword, and a Taoist attacks with magic. While each character has different defensive powers, they all defend the same way — perhaps by holding up their weapon to block an oncoming attack. Furthermore, there are two base types of characters and they are vastly different. For that reason, we have two more abstract classes that extend the AbstractCharacter class.

For our human characters, the ones users can choose to be, we have the abstract Human class from which all classes that intend to create a template for constructing human characters must extend. The Human class is one of two methods that directly extend the AbstractCharacter class. Human characters can have pets and human friends. Aside from that, a human character is much like any other character. For that reason, the only fields distinct to the Human class are a Pet instance field to hold an instance’s pet and a final LinkedList of Human objects for an instance to accumulate friends. The list of friends is final because we want our Human instances to always have a list of friends; it can never be set tonull or replaced by accident. The two distinct functions of the Human class have to do with settingand getting friends and a pet. The Archer, FireArcher, Warrior, and Taoist are concrete classes that extend the Human class. Its also important to note that the FireArcher is a special type of archer that extends the Archer class. Its only distinction is its additionalfirePower instance field which adds to its attack power.

The abstract Pet class is the other class that directly extends the AbstractCharacter class. All classes that intend to create a template for constructing pet characters must extend to be a valid playing character in our game. The pet class’s only distinct field is a Human instance field for storing the owner of an instance. Its only distinct method is its cry() instance method which is an interface for all pets to make their special sound; a Dog can bark and a Lion can roar by invoking cry(). The Dog and Lion concrete classes are currently the the only classes that extend the Pet class.

**Game**

The game is simple. The user chooses a maximum number of battles for the players to engage in. Each time the user clicks “Next Battle”, the next battle starts between two characters — a random attacker and a random defender. The attacker tries to inflict damage on the defender and only succeeds if the defender has less defensive power than the attacker’s attack power. Whoever wins the battle gains experience. To gain experience for an action, a character must call the gainExperience() instance method and provide a string representing the action they’ve completed as an argument. The action will be used as a key to get the corresponding amount of experience to gain from the AbstractCharacter class’sactionExperiences static HashMap field. That way, all characters get the same amount of experience for completing the same actions.

The last man standing is the winner of the game. The game has an String array which holds the history of winners from each game. A user can only play a maximum of one hundred games each time he or she launches our application because our history arrayhas a fixed length of a one elements. This is simply to illustrate a use of an array and can be changed to a LinkedList if you want to allow users to play your game as many times as they want. Lastly, the game has a graphical user interface (GUI) which it has to set up once each time our application is launched.

**Applying Knowledge**

106

**GameGUI**

The GUI is what allows a Game instance to display real time information about the state of the game and its players to the user; our GameGUI class is used by the Game class to achieve that purpose. As noted before, each Game instance must have an instance of our GameGUI class in order to run. The GameGUI makes use of JavaFX, which allows developers to create desktop, mobile, and web applications nicer than ever before, to display information from an associated Game instance to the user in its views.

Our GameGUI is currently designed with threeTextAreas for displaying information about the game and ongoing battles in the game, one TextField for capturing user input, one ListView for displaying the standings of all the characters in the game, a Button to stat the game, and two more buttons to advance through the game. Setting all of that up is a bit more involved, but you’ll be able to understand each part as you read the documentation in the code.

**JavaFX Application**

Our application runs on JavaFX components for its GUI and a nice abstract Application class provided by JavaFX for easily launching and starting a application program. Our GUIGameApplication class extends the JavaFX Application class and is at the root of our project. Its only duty is to hold the main method of our program. Its main method has a simple duty of calling the launch() instance method from the Application class. When that method is called, it will call the abstract start() instance method from the Application class to start our application. Our GUIGameApplication must implement that start()method which gives us access to the primaryStageStage field of the application. We must provide theprimaryStage reference to our Game, which will provide its instance of our GameGUI class to display the JavaFX GUI for our game.

**Finishing Up**

And just like that, we are finished. You have learned so much about Java. In fact, you know everything you need to know to start building your own Java applications. Remember that the best way to learn is by doing and having fun while doing so. Your next steps are to play around with our game, take a look at each class in the supporting code for this chapter, read the documentation, and then try to write the entire project again. After that, try to build your own game or add to what we already have here. You are on your way. In the next chapter, we will take a look at some more fun projects we can take on to continue applying your new knowledge of Java programming.

**Conclusion**

At this point, you’ve learned everything you need to know about Java to get started on developing your own projects. Here’s a list of projects you can start with to build upon your new knowledge of Java:

**Java for Humans**

107

**Fun Projects**

**Console Applications: Easy**

Study guide application to solidify your understanding of the Java concepts you’ve learned in this book. This will require you work with loops, objects, methods, and a HashMap.A simple calculator application to do some math to work on your knowledge of operators and user input and output.

GUI Applications: Moderate

A chat bot application. Keep an array of phrases the robot can say back to you and have one displayed whenever you enter something in the console. You can use some string manipulation and parsing to decide what the robot says back to you depending on what you say to it. Create a JavaFX GUI with one TextArea to show your conversation with the robot, one TextField for you to input a message, and a button to send the message to the robot.Create a to-do list of tasks you have to complete today. You can have the same GUI as the chat bot application but with an extra button that lets you delete a task.

Android Applications: Moderate

Android applications use Java for their code. You know Java, so you know most of Android. You can do anything with this one. Think of something to build, may be one of the ideas from above, and find a tutorial online to learn how to develop Android applications. A fun starting application is one that allows a user to text a friend because it doesn’t require much code. Like Java, Android does most of the heavy lifting.

You could even find a tutorial to learn how to build a clone of popular applications like Snap Chat and Instagram. None of these are far out of your reach because they consist mostly of the concepts you’ve learned here. The only thing you don’t know yet is how to interact with a database server. You can learn that as you go.

**Making Money**

Once you have a couple projects under your belt, you can start applying for jobs. You can be a software engineer, designer, tester, or documentation specialist. The United State’s national average for software engineer salaries is $90,374 according Glassdoor in 2016\. That’s for full time engineers, but even interns make more than $7,000 per month at many technology and financial companies.

If you are not interested in working for someone, you’ve also come to the right place. Silicon Valley is flowing with people like you who aren’t afraid to dream and do whatever it takes to see their dreams through. You could start the next popular social networking application like Facebook, LinkedIn, and Airbnb. The possibilities are endless when you have knowledge of Java.

**Applying Knowledge**

108

**Final Words: The End of the Beginning**

You are on your way to new and exciting times with your programming knowledge. Now that you know Java, it will also be easier to learn more languages that allow you to do even more fun things with the computers you use everyday.

*As humans, we owe it to ourselves to not only consume the advancements of our world,*

*but to produce more innovation that extend the capabilities of humankind.*

I can’t wait to see what you do with your knowledge of Java. I would love to hear from you to know how you are applying your new knowledge.

Finally, I’d like to leave you with a reminder and update of why we program:

*We program to capture and manipulate information (data)*

*to produce new information for the world to consume.*

**Java for Humans**