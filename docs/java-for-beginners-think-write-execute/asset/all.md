![](cover.jpeg)

Copyright © 2017 by Mr Kotiyana

All rights reserved. No part of this publication may be reproduced, distributed, or transmitted in any form or by any means, including photocopying, recording, or other electronic or mechanical methods, without the prior written permission of the publisher, except in the case of brief quotations embodied in critical reviews and certain other noncommercial uses permitted by copyright law.

Table of Contents

1) Introduction Basic 4

1.1 What This Book Is About? 5

1.2 Why Read This Book? 6

1.3 Do I Need to Know Math? 8

1.4 Programming as a Form of Expression              9

2) Programming Basics 10

2.1 What is Programming? 11

2.2 What is Data? 12

2.3 Understanding Variables.14

2.4 Naming Variables. 15

2.5 Keywords 20

2.6 Tokens 21

2.6.1 Writing Java22

2.6.2 Separator Tokens24

2.6.3 Operator Tokens26

2.6.4 Literals 27

2.7 What are Functions? 28

2.7.1 Parameter Lists33

2.7.2 Side Effects34

2.7.3 Multiple Arguments36

2.8 Logic and Operators 37

2.9 Return Keyword 41

2.10 Class/Static Variables43

2.11 Arrays 44

2.12 Loops51

2.13 Classes63

2.14 Introduction to Objects65

2.14.1 Characteristics of OOP              68

2.14.2 An object has an interface              70

2.14.3 An object provides services              73

2.14.4 The hidden implementation              75

2.14.5 Reusing the implementation              77

2.14.6 Inheritance78

2.14.7 Polymorphism83

2.15 Types86

2.15.1 Value and Reference Types              87

2.15.2 Strong Typing89

2.16 Thinking in Algorithms.90

2.17 Statements and Expression.96

2.18 Learning to copy & paste code.              99

2.19 Understanding floating points.              101

2.20 The Big O Notation.102

3) Data Structures 110

3.1 Binary Search.111

3.2 Bubble Sort  118

3.3 Insertion Sort  121

3.4 Merge Sort.123

3.5 Quick Sort.  127

3.6 Selection Sort132

3.7 Linked List135

4) Network Programming  150

4.1 What is network programming  151

4.2 Socket Programming  152

4.3 URL Processing  163

5) Tips and Advice

5.1 Skills self-taught programmers commonly lack.              171
5.2 Important data structure and algorithms                175

5.3 9 ways to become Great Programmer.              178
5.4 4 Secrets of Great Programmers.                192

5.5 Difference between a programmers, a good Programmer and a great programmer. .               194

6) 4 Reasons why Your Program Crashes             195

7) Programming Quotes! 197

CHAPTER 1 | Introduction

What This Book Is About

This book was written as an answer for anyone to pick up a programming language and be productive. You will be able to start from scratch without having any previous exposure to any programming language. By the end of this book, you will have the skills to be a capable programmer, or at least know what is involved with how to read and write code. Afterward you should be armed with the knowledge required to feel confident in learning more. You should have general computer skills before you get started. After this you’ll know what it takes to at least look at code without your head spinning.

Why Read This Book?

You could go online and find videos and tutorials to learn; however, there is a distinct disadvantage when it comes to learning things in order and in one place.

Most YouTube or tutorial websites either gloss over a topic or dwell at a turtle’s pace for an hour on a particular subject. Online content is often brief and doesn’t go into much depth on any given topic. It is incomplete or still a work in progress. You’ll often find yourself waiting weeks for another video or tutorial to come out.

Most online tutorials for Java are scattered, disordered, and incohesive. It is difficult to find a good starting point and even more difficult to find a continuous list of tutorials to bring you to any clear understanding of the Java programming language. Just so you know, you should find the act of learning exciting. If not, then you’ll have a hard time continuing through to the end of this book. To learn any new skill, a lot of patience is required.

I remember asking an expert programmer how I’d learn to program. He told me to write a compiler. At that time, it seemed rather mean, but now I understand why he said that. It is like telling someone who wants to learn how to drive Formula 1 cars to go compete in a race. In both cases, the “learn” part was left out of the process of learning. It is very difficult to tell someone who wants to learn to write code where to begin.

However, it all really does start with your preparedness to learn. Your motivation must extend beyond the content of this book. You may also have some preconceived notions about what a programming is.

I can’t change that, but you should be willing to change your thoughts on the topic if you make discoveries contrary to your knowledge. Keep an open mind.

Computer artists often believe that programming is a technical subject that is incompatible with art. I find the contrary to be true. Programming is an art, much as literature and design is an art. Programming just has a lot of obscure rules that need to be understood for anything to work.

Do I Need to Know Math?

With complex rules in mind, does programming require the knowledge of complex mathematics? Actually, unless you program mathematical software, only a bit of geometry is nice to have. Most of the examples here use only a tiny bit of math to accomplish their purposes.

Mathematics and programming do overlap quite a lot in their methodology. Math taught in schools provides a single solution. Programming results tend to behave a bit like a math proof, but only the proof isn’t just another bit of math. Rather, the proof of your code means that your zombies chase after humans.

A considerable amount of math required has been done for you by the computer. It is just up to you to know what math to use, and then plug in the right variables.

Programming as a Form of Expression

There is a deeper connection between words and meaning in programming. This connection is more mechanical, but flexible at the same time. In relation to a programming language, programmers like to call this “expressiveness.” When you write words in literature, you infer most if not all of the meaning. When programming inference isn’t implied, then you’re free to define your own meanings for words and invent words freely.

One common merging of art and code appears within a video game. Anytime characters can react to each other and react to user interaction, which conveys a greater experience. An artist, an animator, or an environment designer should have some ability to convey a richer experience to the audience. A character artist can show a monster to his or her audience; but to really experience the creature, the monster should glare, grunt, and attack in reaction to the audience.

Chapter 2 | Programming Basics

What Is Programming?

It’s all about writing code. Programming is a process in which we organize data and use logic to do something with those data. The data are everything a computer can store; they can range from numbers to zombie characters in a video game.

You do this by writing text into files called source code. Source code written into text files replaces punch cards used by the computing machines half a century ago.
When data are combined with logic and then written into a single file, they’re called a class. Classes are also data, and as such can be managed with more logic.

[![https://4.bp.blogspot.com/-0LaVc78_c2U/WBNMx1x7OdI/AAAAAAAAGsQ/dlzw-uNb7PEAZFkRM5Rqx4RqLhMVFkyGQCK4B/s320/class.png](images/00001.jpeg)](http://4.bp.blogspot.com/-0LaVc78_c2U/WBNMx1x7OdI/AAAAAAAAGsQ/dlzw-uNb7PEAZFkRM5Rqx4RqLhMVFkyGQCK4B/s1600/class.png)

Classes are used to create objects in the computer’s memory and can be duplicated to have a life of their own. Classes are used to build objects. Each piece of data within the class becomes a part of that object. Different chunks of data inside of a class are called class members.
Class members can also be chunks of logic called functions or methods.

For Example, in a game with a horde of zombies, each zombie is duplicated or instanced from a zombie class. Each zombie has unique values for each attribute or data element in the class.

This means hit points, and locations are unique for each duplicate zombie object. Objects created from a class are called instances. Similar to families, objects can inherit properties from one another.

The child sometimes called a subclass inherits attributes from its parent. For instance, the child created from a zombie may inherit the parent’s hunger for brains.
To be useful, the child zombie can also add new objects and change the objects it inherited from its parent class. As a result, now the child zombie might have tentacles that the parent didn’t have. Objects talk to each other through events and messages.

Shooting at zombies can create an event, or in programmer terms, it “raises” an event. The bullet impact event tells the zombie class to then take necessary steps when hit by a bullet.
Events command the class to take actions on its data, which is where functions come in.
Functions, also known as methods, are sections of logic that act on data. They allow your class to create additional events and talk to yet more objects.
As the player presses the trigger and moves the joystick around, yet more events can be raised and messages can be sent. Events and messages allow the player to interact with your world; logic events and objects together build your game.

What is Data?

Data, in a general sense, is sort of like a noun. Like nouns, data can be a person, place, or thing. Programmers refer to these nouns as objects, and these objects are stored in memory as variables. The word variable infers something that might change, but this isn’t always the case. It’s better to think of a variable as a space in your computer’s memory to put information. When you play word games like MadLibs you might ask for someone’s name, an object, an adverb, and a place. Your result could turn out like “Garth ate a jacket, and studiously played at the laundry-mat.” In this case the name, object, adverb, and place are variable types. The data is the word you use to assign the variable with.

Programmers use the word type to denote what kind of data is going to be stored. Computers aren’t fluent in English and don’t usually know the difference between the English types noun and adjective, but they do know the difference between letters and a whole variety of numbers. There are many predefined types in java or any other language.

If you add that to the ability to create new types of data, the kinds of data we can store is practically unlimited.

The C# built-in types are sometimes called POD, or plain old data. The term POD came from the original C++ standard which finds its origin dating back to 1979\. POD types have not fundamentally changed from their original implementation.

So far we’ve used the word type several times. Programmers define the word type to describe the variety of data to be stored.

Variables are created using declarations. Declaration is defined as a formal statement or announcement.

Each set of words a programmer writes is called a statement. In English we’d use the word sentence, but programmers like to use their own vocabulary. Declaration statements for variables define both the type and the identifier for a variable.

public class Example

{

int i;

}

Programmers use a semicolon (;) rather than a period to end the statement. Therefore, if you want to sound like a programmer you can say you can “write a statement to declare a variable of type int with the identifier i.” Or if you want to be overly dramatic you can proclaim “I declare a new variable of type int to be known as i!” and so it shall be.

Variables

Variables are used to store information to be referenced and manipulated in a computer program. They also provide a way of labeling data with a descriptive name, so our programs can be understood more clearly by the reader and ourselves. It is helpful to think of variables as containers that hold information. Their sole purpose is to label and store data in memory. This data can then be used throughout your program.

A variable’s name is called an identifier. For the most part an identifier is a unique word that a programmer, or in this case you, picks to name a variable. An identifier is always something that a programmer invented to describe a variable; it’s like naming a new pet or a baby.

Identifiers:

Identifiers, which are considered symbols or tokens, are words that you invent which you then assign a meaning. Identifiers can be as simple as the letter i or as complex as @OhHAICanIHasIdentifier01\.

identifier is the word that’s used to name any function, variable, or type of data you create. When the keyword class is used it’s followed by another word called an identifier. After properly identifying a function, or other chunk of data, you can now refer to that data by its identifier. In other words, when you name some data Charles you access that data by the name Charles.

class MyNewClassImWriting

{

}

Variable Names

It’s important to know that variable identifiers and class identifiers can be pretty much anything. There are some rules to naming anything when programming. Here are some guidelines to help. Long names are more prone to typos, so keep identifiers short. A naming convention for variables should consider the following points.

The variable name should indicate what it’s used for, or at least what you’re going to do with it. This should be obvious, but a variable name shouldn’t be misleading. Or rather, if you’re using a variable named radius, you shouldn’t be using it as a character’s velocity. It’s also helpful if you can pronounce the variable’s name; otherwise you’re likely to have issues when trying to explain your code to another programmer.

int someLong_complex_hardToRememberVariableName;

There is an advantage to keeping names as short as possible but still quite clear. Your computer screen, and most computers for that matter, can only fit so many characters on a single line. You could make the font smaller, but then you run into readability issues when letters get too small. Consider the following function, which requires more than one variable to work.

SomeCleverFunction(TopLeftCorner – SomeThickness + OffsetFromSomePosition, BottomRightCorner – SomeThickness + OffsetFromSomePosition);

The code above uses many long variable names. Because of the length of each variable, the statement takes up multiple lines making a single statement harder to read. We could shorten the variable names, but it’s easy to shorten them too much.

CleverFunc(TL–Thk+Ofst,LR–Thk+Ofst);

Variable names should be descriptive, so you know what you’re going to be using them for: too short and they might lose their meaning.

int a;

While short and easy to remember, it’s hard for anyone else coming in to read your code and know what you’re using the variable a for. This becomes especially difficult when working with other programmers. Variable naming isn’t completely without rules.

int 8;

A variable name can’t be a number. This is bad; numbers have a special place in programming as much of it has other uses for them. IDE will try to help you spot problems. A squiggly red line will appear under any problems it spots. And speaking of variable names with numbers, you can use a number as part of a variable name.

int varNumber2;

The above name is perfectly valid, and can be useful, but conversely consider the following.

int 13thInt;

Variable names can’t start with any numbers. To be perfectly honest, I’m not sure why this case breaks the compiler, but it does seem to be related to why numbers alone can’t be used as variable names.

int $; int this-that; int (^_^);

Most special characters also have meanings, and are reserved for other uses. For instance, in JAVA a - is used for subtracting; in this case JAVA may think you’re trying to subtract that from this. Keywords, you should remember, are also invalid variable names as they already have a special meaning for JAVA. In IDE (integrated Development Environment), you might notice that the word this is highlighted, indicating that it’s a keyword. Spaces in the middle of a variable are also invalid.

int Spaces are bad;

Most likely, adding characters that aren’t letters will break the compiler. Only the underscore and letters can be used for identifier names. As fun as it might be to use emoticons for a variable, it would be quite difficult to read when in use with the rest of the code.

int ADifferenceInCase; int adifferenceincase;

The two variables here are actually different. Case-sensitive languages like java do pay attention to the case of a character; this goes for everything else when calling things by name. Considering this: A is different from a.

As a programmer, you need to consider what a variable should be named. It must be clear to you and anyone else with whom you’ll be sharing your work with. You’ll also be typing your variable name many times, so they should be short and easy to remember and type. The last character we discuss here is the little strange @ or at. The @ can be used only if it’s the first character in a variable’s name.

 int @home;

 int noone@home;

In the second variable declared here we’ll get an error. Some of these less regular characters are easy to spot in your code. When you have a long list of variables it’s sometimes best to make them stand out visually. Some classically trained programmers like to use an underscore to indicate a class scope variable. The underscore is omitted in variables which exist only within a function. You would find the reason for the odd rule regarding @ when you use int, which is reserved as a keyword. You’re allowed to use int @int, after which you can assign @int any integer value. However, many programmers tend to use MyInt, mInt, or _ int instead of @int based on their programming upbringing.

Good programmers will spend a great deal of time coming up with useful names for their variables and functions. Coming up with short descriptive names takes some getting used to, but here are some useful tips. Variables are often named using nouns or adjectives as they describe an attribute related to what they’re used for.

In the end once you start using the name of the variable throughout the rest of your code, it becomes harder to change it as it will need to be changed everywhere it’s used. Doing a global change is called refactoring, and this happens so often that there is software available to help you “refactor” class, variable, and function names.

NOTE:

You may also notice the pattern in which uppercase and lowercase letters are used. This is referred to as either BumpyCase or CamelCase. Sometimes, the leading letter is lowercase, in which case it will look like headlessCamelCase rather than NormalCamelCase. Many long debates arise between programmers as to which is correct, but in the end either one will do. Because Java is case sensitive, you and anyone helping you should agree whether or not to use a leading uppercase letter. These differences usually come from where a person learned how to write software or who taught that person. The use of intermixed uppercase and lowercase is a part of programming style. Style also includes how white space is used.

Keywords

Keywords are special words, or symbols, that tell the compiler to do specific things. For instance, the keyword class at the beginning of a line tells the compiler you are creating a class. A class declaration is the line of code that tells the compiler you’re about to create a new class. The order in which words appear is important. English requires sentences and grammar to properly convey our thoughts to the reader.

In code, Java or otherwise, programming requires statements and  syntax to properly convey instructions to the computer.

class className

{

}

Every class needs a name; in the above example we named our class className, although we could have easily named the class Charles. When a new class is named the name becomes a new identifier. This also holds true for every variable’s name, though scope limits how long and where the variable’s identifier exists. We’ll learn more about variables and scope soon. You can’t use keywords for anything other than what Java expects them to be used for. There are exceptions, but in general, keywords provide you with specific commands.

Altogether in Java there are roughly 80 keywords you should be aware of.

Tokens

In written English the smallest elements of the language are letters and numbers. Individually, most letters and numbers lack specific meaning. The next larger element after the letter is the word. Each word has more meaning, but complex thoughts are difficult to convey in a single word. To communicate a thought, we use sentences. The words in a sentence each have a specific use, as seen in the diagram below. To convey a concept we use a collection of sentences grouped into a paragraph. And to convey emotion we use a collection of many paragraphs organized into chapters. To tell a story we use a book, a collection of chapters.

![](images/00002.jpeg)

Programming has similar organizational mechanisms. The smallest meaningful element is a token, followed by statements, code blocks, functions, followed by classes and namespaces and eventually a program, or in our case a game. We will begin with the smallest element and work our way up to writing our own classes. However, it’s important to know the very smallest element to understand how all the parts fit together before we start writing any complex code.

Writing Java: 

Java is an English-based programming language; like any other C-like programming language it can be broken into tokens, the smallest meaningful fragment of text that the computer can understand. Tokens are made of a single character or a series of characters. For instance, in a simple statement like the following there are five tokens.

![](images/00003.jpeg)

Tokens can be categorized as a keyword, identifier, literal, operator, separator, and white space. The above statement contains five tokens with spacing provided with white space. The keyword int is followed by the identifier i. This is followed by an operator = which assigns the identifier on the left of the operator and the value of the literal 0 on the right. The last token ; is a separator which ends the statement. White spaces and comments, which we have yet to cover, are not considered tokens, although they can act as separators. It’s important  that proper formatting or style be used.

Let’s examine a sample of code:

int i = 0; int j = 1;

The code shown above is two statements, the separator keeps the computer from misreading the code as a single statement. However, there are humans involved with writing code, and thus code needs to be readable by humans, or any other life-form which might read your code. Proper code means following a specific formatting style. We’ll dive into more about proper code style later in this chapter. Each group of characters, or text, is converted by a lexical analyzer, sometimes called a lexer, in the computer and turned a symbol. This process is called tokenization, or as a computer scientist would say, a lexer tokenizes your code into symbols. Once tokenized, the symbols are parsed; this process organizes the tokens into instructions for the computer to follow. This unique vocabulary does frame programmers as a strange group of alien beings with a language all to themselves; I promise, however, conversations about lexical analyzers don’t come up very often when talking with most programmers.

This may seem like a great deal of work and we are jumping ahead into more complex computer science topics, but all of this happens behind the scenes so you don’t need to see any of this taking place.

It’s important to understand what a compiler does, and how it works so you can write code in a way that the computer can understand. This is why a simple typo will stop the lexer from building code. We’ll get to writing code to be analyzed, tokenized, and parsed soon enough.

A computer can’t interpret or guess at what it is you’re trying to do. Therefore, if you mistype int i = 0: and not int i = 0; the last token cannot be converted by the lexer into a proper symbol, and thus this statement will not be parsed at all. This code results in an error before the code is even compiled.

Separator Tokens:

The most common separator is the ;, semicolon. This mark of punctuation is used to end a code statement. Other separators come in pairs. Curly braces are used in pairs to separate groups of code statements. The opening curly brace is the { with the pointy end pointed to the outside of the group; this is paired with the } which closes the curly brace pair. Parentheses start with the ( and end with the ) while square brackets start with [ and end with ]. The different opening and closing braces, brackets, and parentheses have specific purposes and are used to help identify what they are being used for. There are angle brackets < and > as well; these are used to surround data types. And don’t forget both single quotes '' and double quotes "", which are used in pairs as well to surround symbols called strings.

NOTE:

In many word processors a beginning and an ending quote (“ and ”) are often used. The lexical analyzer doesn’t recognize these smart quotes, so the text editor for programming uses straight quote marks (") instead. These subtle changes aren’t so subtle once you realize that letters, numbers, and every other character used in programming are all parsed as American Standard Code for Information Interchange (ASCII) or unicode transformation format (UTF)-8, 16, or 32.

Both ASCII and UTF are names given to the database of characters that the computer uses to read text. Computers don’t use eyes to read. Rather, they use a database of numbers to look up each character being used. Therefore, to a computer “ looks more like 0x201C and " like 0x0022, if we were using UTF-16\. Curly braces are used in code to separate statements. Parentheses are usually used to accept data. Square brackets are often used to help identify arrays. We’ll get into arrays later, but imagine something like a spreadsheet or a graph paper till we get to their explanation.

int[] arrayNumbers = {1, (int) 3.0, 9000};

The above statement assigns three numbers to an array. The curly braces contain a pair of statements separated by a comma. The second statement in the curly braces is converting a number with a dot (.) into a number without a dot in it. This will take a bit of explanation, but it’s good to get used to seeing this sort of thing. We’ll get to what an array is soon enough, as well as a dot operator.

Often, when learning to program you’ll see many strange tokens which might not seem to have any meaning. It’s up to you to observe every token you come across and try to understand what it does.

If none of the statements makes sense that’s fine. At this point you’re not expected to know what all this means yet, but you soon will.

Operator Tokens:

Operators are like keywords but use only a few non-word characters. The colon or semi-colon is an operator; unlike keywords, operators change what they do based on where they appear, or how they are used. This behavior shifting is called operator overloading, and it’s a complex subject that we’ll get into later. It’s also important to know that you can make up your own operators when you need to. Commas in Java have a different meaning. They’re used to separate different data values like     for(int i = 0, j = 1; ; i++, j++) .

Other Operator Tokens:

Operators in general are special characters that take care of specific operations between variables. Notation or the order in which operators and variables appear is normally taught with the following notation or mathematic grammar: a + b = c. However, in  programming the following is preferred: c = a + b; the change is made because the = operator in Java works differently from its function commonly taught in math class. The left side of the = operator is the assignment side, and the right side is the operation side. This puts the emphasis on the value assigned rather than how it’s assigned. The result is more important than how the problem is solved since the computer is doing the math. In programming the above example should be read as “c is assigned a plus b.”

Literals:

Literals come in many different forms; similar to operators which appear as things like +, -, or = literals are the tokens that often go between them. Numbers are considered literals, or tokens that are used in a literal manner. Numbers can be called numeric literals. When something is put into quotes, as in “I’m a literal,” you are writing a string literal. Literals are common throughout nearly all programming languages and form the base of Java’s data types. Right now, we’re dealing with only a few different types of literals, but there are many more we will be aware of soon.

Transitive and Non-Transitive Operations:

In math class it’s sometimes taught how some operations are transitive and others not. For instance 2 + 3 + 4 and 4 + 3 + 2 result in the same values. Where each number appears between the operators doesn’t matter, so the + operator is considered transitive. This concept holds true in Java. Results change when we start to mix operators.

int a = 1 + 2 - 4 + 7;  //a = 6

int b = 7 + 4 - 2 + 1;//b = 10

This code fragment shows two different results using the same operators but with different number placement. We’ll see how to overcome these problems later on when we start using them in our game. Operator order is something to be aware of, and it’s important to test each step as we build up our calculations to make sure our results end up with values we expect. To ensure that the operations happen as you expect, either you can use parentheses to contain operands or you can do each calculation. We’ll dive further into more detail with a second look at operators later on, but this will have to wait till we have a better understanding of more of the basics of Java.

What Are Functions?

Functions, sometimes called methods, contain statements which can process data. The statements can or cannot process data. Methods can be accessed by other statements. This action is referred to as calling a function or making a function call.

Functions may look different in different programming languages, but the way they work is mostly the same. The usual pattern is taking in data and using logic to manipulate that data. Functions may also be referred to by other names, for example, methods. The major differences come from the different ways the languages use syntax. Syntax is basically the use of spaces or tabs, operators, or keywords.

In the end, all you’re doing is telling the compiler how to convert your instructions into computer-interpreted commands. Variables and functions make up the bulk of programming. Any bit of data you want to remember is stored in a variable. Variables are manipulated by your functions. In general, when you group variables and functions together in one place, you call that a class.

Example:

public void PrintNum ()

{

System.out.println (anotherNum);

}

When writing a new function, it’s good practice to fill in the entirety of the function’s layout before continuing on to another task. This puts the compiler at ease; leaving a function in the form void MyFunction and then moving on to another function leaves the compiler confused as to what you’re planning on doing. The integrated development environment, in this case MonoDevelop, is constantly reading and interpreting what you are writing, somewhat like a spell checker in a word processor. When it comes across a statement that has no conclusive form, like a variable, function, or class definition, its interpretation of the code you’re writing will raise a warning or an error. MonoDevelop might seem a bit fussy, but it’s doing its best to help.

Writing a Function:

A function consists of a declaration and a body. Some programmers like to call these methods, but semantics aside, a function is basically a container for a collection of statements.

Let’s continue with the example:

void MyFunction ()

{

}

Here is a basic function called MyFunction. We can add in additional keywords to modify the function’s visibility. One common modifier we’ll be seeing is public.

public void MyFunction ()

{

}

The public keyword needs to appear before the return type of the function. In this case, it’s void, which means that the function doesn’t return anything. but functions can act as a value in a few different ways. For reference, a function that returns an int would look like this. A return statement of some kind must always be present in a function that has a return type.

public int MyFunction ()

{

return 1;

}

The public modifier isn’t always necessary, unless you need to make this function available to other classes. If this point doesn’t make sense, it will soon. The last part of the function that is always required is the parameter list. It’s valid to leave it empty, but to get a feeling for what an arg, or argument in the parameter list, looks like, move on to the next example.

public void MyFunction (int i)

{

}

For the moment, we’ll hold off on using the parameter list, but it’s important to know what you’re looking at later on so it doesn’t come as a surprise. Parameter lists are used to pass information from outside of the function to the inside of the function. This is how classes are able to send information from one to another.

Function declaration is similar to class declaration. Functions are the meat of where logic is done to handle variables.

Function Scope:

Variables often live an ephemeral life. Some variables exist only over a few lines of code. Variables may come into existence only for the moment a function starts and then disappear when the function is done. Variables in the class scope exist for as long as the class exists. The life of the variable depends on where it’s created.

Example:

public class Classscopm{

int ClassInt;

void first()

{

int firsttint;

}

void second()

{

int secondint;

}

}

If we look at the above figure we can visualize how scope is divided. The outer box represents who can see ClassInt. Within the first () function we have a firsttint that only exists within the first () function.

The same is repeated for the secondint, found only in the second () function. This means that first () can use both ClassInt and firsttint  but not secondint. Likewise, second () can see ClassInt and secondint but not firsttint.

Parameter Lists:

When a function is called, its identifier followed by its parameter list is added to code. Parameters are like little mail slots on the front door of a house. There might be a slot for integers, floats, and arrays. Each slot on the door, or argument in the parameter list, is a type followed by an identifier.

If we look at a basic example, we’ll see how all this works.

public class Example {

int a = 0;

void SetA (int i) {

a = i;

}

}

void SetA (int i) takes in one parameter of type int. This is a simple example of a value parameter; there are other types of parameters which we’ll go into next. The value parameter declares the type and an identifier whose scope is limited to the contents of the function it’s declared with. When you run the above program and give value 3 to the parameter of the function SetA(3) you’ll see a 0 followed by a 3\. We can do this any number of times, and each time we’re allowed to change what value we set A to. Of course, it’s easier to use a = 3 in the class, but then we wouldn’t be learning anything.

Side Effects:

When a function directly sets a variable in the class the function lives in, programmers like to call this a side effect. Side effects are usually things that programmers try to avoid, but it’s not always practical. Writing functions with side effects tend to prevent the function from being useful in other classes. We’ll find other systems that allow us to avoid using side effects, but in some cases, it’s necessary.

Class MySideEffect {

int a = 0;

void SetA ()

{ 

a = 5;

}

}

The above SetA() function sets int a to 5. The SetA() function does have a clear purpose, setting A, but there’s nothing in the function that indicates where the variable it’s setting lives. If the variable lived in another class which MySideEffect inherited from, then you wouldn’t even see the variable in this class. Once the complexity in a class grows, where and when a variable gets changed or read becomes more obscure. If a function remains self-contained, testing and fixing that function becomes far easier.

Reading what a function does should not involve jumping around to find what variable it’s making changes to. This brings us back to the topic of scope. Limiting the scope or reach of a function helps limit the number of places where things can go wrong.

class MySideEffect {

 int a = 0;

void SetA ()

{ 

a = 5;

}

void SetAgain ()

{ 

a = 10;

}

}

The more functions that have a side effect, the more strange behaviors might occur. If Main () function is expecting one value but gets something else entirely, you can start to get unexpected behaviors. Worse yet, if SetAgain() is called from another class and you were expecting a to be 5, you’re going to run into more strange behaviors.

Multiple Arguments:

There aren’t any limits to the number of parameters that a function can accept. Some languages limit you to no more than 16 arguments, which seems acceptable. If your logic requires more than 16 parameters, it’s probably going to be easier to separate your function into different parts. However, if we’re going to be doing something simple, we might want to use more than one parameter anyway.

 int a = 0;

void SetA (int i, int j) {

a = i * j;

}

We can add a second parameter to SetA. A comma token tells the function to accept another variable in the parameter list. For this example, we’re using two ints to multiply against one another and assign a value to a. There isn’t anything limiting the types we’re allowed to use in the parameter list.

 int a = 0;

float b = 0;

void SetA (int i, float j) { 

a = i; 

b = j;

}

The function with multiple parameters can do more. Value parameters are helpful ways to get data into a function to accomplish some sort of simple task.

Logic and Operators

Logic allows you to control what part of a function is evaluated based on changes to variables. Using logic, you'll be able to change which statements in your code will run. Simply put, everything you write must cover each situation you plan to cover. Logic is controlled through a few simple systems, primarily the if keyword and variations of if.

Booleans:

In Java booleans, or bools for short, are either true or false. It’s easiest to think of these as switches either in on or in off position. To declare a var as a bool, you use something like the following.

public class Example

{

public bool SomeBool;

}

Equality Operators:

Equality operators create boolean conditions. There are many ways to set a boolean variable. For instance, comparisons between values are a useful means to set variables. The most basic method to determine equality is using the following operator: ==. There’s a difference between use of a single and a double equals to symbol. = is used to assign a value whereas == is used to compare values.

When you need to compare two values you can use the following concept. You’ll need to remember that these operators are called equality operators, if you need to talk to a programmer.

The syntax here may look a bit confusing at first, but there are ways around that.

void Func ()

{ 

SomeBool = (1 == 1);

}

There are other operators to be aware of. You will be introduced to the other logical operators later in the chapter. In this case, we are asking if two number values are the same.

To make this a more clear, we can break out the code into more lines. Now, we’re looking at a versus b. Clearly, they don’t look the same; they are different letters after all. However, they do contain the same integer value, and that’s what’s really being compared here.

 void Func ()

{

int a = 1;

 int b = 1;

SomeBool = (a == b);

}

Evaluations have a left and a right side. The single equal to operator (=) separates the different sides. The left side of the = is calculated and looks to the value to the right to get its assignment. Because 1 == 1, that is to say, 1 is equivalent to 1, the final result of the statement is that SomeBool is true.

Relational Operators:

Bool values can also be set by comparing values. The operators used to compare two different values are called relational operators. We use ==, the is equal symbol, to check if values are the same; we can also use !=, or not equal, to check of two variables are different.

This works similarly to the ! in the previous section. Programmers more often check if one value is greater or lesser than another value. They do this by using >, or greater than, and <, or less than. We can also use > =, greater or equal to,

and < =, less than or equal to. Let’s see a few examples of how this is used.

public  class  Test  {

 public  static  void main(String args[])  {

 int a =  10;

 int b =  20;

 System.out.println("a == b = "  +  (a == b)  );

 System.out.println("a != b = "  +  (a != b)  );

 System.out.println("a > b = "  +  (a > b)  );

 System.out.println("a < b = "  +  (a < b)  );

 System.out.println("b >= a = "  +  (b >= a)  );

 System.out.println("b <= a = "  +  (b <= a)  );

 }

}

Output:

a == b = false

a != b = true

a > b = false

a < b = true

b >= a = true

b <= a = false

Return Keyword

We need to love the return keyword. This keyword turns a function into data. There are a couple of conditions that need to be met before this will work. So far, we’ve been using the keyword void to declare the return type of a function. This looks like the following code fragment.

void MyFunction()

{

//code here...

}

In this case, using return will be pretty simple.

void MyFunction()

{

//code here ...

return;

}

This function returns void. This statement has a deeper meaning. Returning a value makes a lot more sense when a real value, something other than a void, is actually returned. Let’s take a look at a function that has more meaning. The keyword void at the beginning of the function declaration means that this function does not have a return type. If we change the declaration, we need to ensure that there is a returned value that matches the declaration. This can be as simple as the following code fragment.

int MyFunction()

{

//code here...

return 1;

//1 is an int

}

This function returns int 1\.

Declaring a function with a return value requires that the return type and the declaration match. When the function is used, it should be treated like a data type that matches the function’s return type.

Class/Static Variables

Class variables also known as static variables are declared with the static keyword in a class, but outside a method, constructor or a block.

There would only be one copy of each class variable per class, regardless of how many objects are created from it.

Static variables are rarely used other than being declared as constants. Constants are variables that are declared as public/private, final and static. Constant variables never change from their initial value.

Static variables are stored in static memory. It is rare to use static variables other than declared final and used as either public or private constants.

Static variables are created when the program starts and destroyed when the program stops.

Visibility is similar to instance variables. However, most static variables are declared public since they must be available for users of the class.  Default values are same as instance variables.

For numbers, the default value is 0; for Booleans, it is false; and for

Object references, it is null. Values can be assigned during the declaration or within the constructor. Additionally values can be assigned in special static initializer blocks.

Static variables can be accessed by calling with the class name.

ClassName.VariableName.

When declaring class variables as public static final, then variables names (constants) are all in upper case. If the static variables are not public and final the naming syntax is the same as instance and local variables.

Example:

import java.io.*; 

public class Employee{   

// salary  variable is a private static variable  

private static double salary; 

   // DEPARTMENT is a constant   

public static final String DEPARTMENT = "Development "; 

   public static void main(String args[]){      

salary = 1000;     

 System.out.println(DEPARTMENT+"average salary:"+salary);  

}

}

Output:

Development average salary: 1000

Note: If the variables are access from an outside class the constant should be accessed as Employee.DEPARTMENT

Arrays

Arrays are nicely organized lists of data. Think of a numbered list that starts at zero and extends one line every time you add something to the list. Arrays are useful for any number of situations because they’re treated as a single hunk of data. For instance, if you wanted to store a bunch of high scores, you’d want to do that with an array. Initially, you might want to have a list of 10 items. You could in theory use the following code to store each score.

int score1;

int score2;

int score3;

int score4;

int score5;

int score6;

int score7;

int score8;

int score9;

int score10;

To make matters worse, if you needed to process each value, you’d need to create a set of code that deals with each variable by name. To check if score2 is higher than score1, you’d need to write a function specifically to check those two variables before switching them. Thank goodness for arrays.

There are two types of array:

*   Single Dimensional Array
*   Multidimensional Array

Single Dimensional Array in java:

Syntax to Declare an Array in java:

dataType[] arr; (or)  

dataType []arr; (or)  

dataType arr[];  

Instantiation of an Array in java:

arrayRefVar=new datatype[size];  

Example of single dimensional java array:

Let's see the simple example of java array, where we are going to declare, instantiate, initialize and traverse an array.

class Testarray{  

public static void main(String args[]){  

int a[]=new int[5];//declaration and instantiation  

a[0]=10;//initialization  

a[1]=20;  

a[2]=70;  

a[3]=40;  

a[4]=50;  

//printing array  

for(int i=0;i<a.length;i++)//length is the property of array  

System.out.println(a[i]);  

  }}  

Output: 10

     20

             70

               40

               50

Declaration, Instantiation and Initialization of Java Array:

We can declare, instantiate and initialize the java array together by:

int a[]={33,3,4,5};//declaration, instantiation and initialization  

Let's see the simple example to print this array.

class Testarray1{  

public static void main(String args[]){  

int a[]={33,3,4,5};//declaration, instantiation and initialization  

//printing array  

for(int i=0;i<a.length;i++)//length is the property of array  

System.out.println(a[i]);  

}}  

Output: 33

              3

             4

              5

 Passing Array to method in java:

We can pass the java array to method so that we can reuse the same logic on any array.

Let's see the simple example to get minimum number of an array using method.

class Testarray2{  

static void min(int arr[]){  

int min=arr[0];  

for(int i=1;i<arr.length;i++)  

 if(min>arr[i])  

  min=arr[i];  

System.out.println(min);  

}  

public static void main(String args[]){  

int a[]={33,3,4,5};  

min(a);//passing array to method  

}}  

Output: 3

Multidimensional array in java:

In such case, data is stored in row and column based index (also known as matrix form).

Syntax to Declare Multidimensional Array in java:

dataType[][] arrayRefVar; (or)  

dataType [][]arrayRefVar; (or)  

dataType arrayRefVar[][]; (or)  

dataType []arrayRefVar[];   

Example to instantiate Multidimensional Array in java:

int[][] arr=new int[3][3];//3 row and 3 column  

Example to initialize Multidimensional Array in java

arr[0][0]=1;  

arr[0][1]=2;  

arr[0][2]=3;  

arr[1][0]=4;  

arr[1][1]=5;  

arr[1][2]=6;  

arr[2][0]=7;  

arr[2][1]=8;  

arr[2][2]=9;  

Example of Multidimensional java array:

Let's see the simple example to declare, instantiate, initialize and print the 2Dimensional array.

class Testarray3{  

public static void main(String args[]){  

//declaring and initializing 2D array  

int arr[][]={{1,2,3},{2,4,5},{4,4,5}};  

//printing 2D array  

for(int i=0;i<3;i++){  

 for(int j=0;j<3;j++){  

   System.out.print(arr[i][j]+" ");  

 }  

 System.out.println();  

}  

}}  

Output:1 2 3

       2 4 5

       4 4 5

Loop

There may be a situation when you need to execute a block of code several number of times. In general, statements are executed sequentially: The first statement in a function is executed first, followed by the second, and so on.

Programming languages provide various control structures that allow for more complicated execution paths.

A loop statement allows us to execute a statement or group of statements multiple times and following is the general form of a loop statement in most of the programming languages −

![Loop Architecture](images/00004.jpeg)

Java programming language provides the following types of loop to handle looping requirements.

While loop:

If we want to run a specific statement more than once in a loop, we need another method. To do this, java comes with another couple of keywords, while and for. The while statement is somewhat easier to use. It needs only one bool argument to determine if it should continue to execute. This statement is somewhat like the if statement, only that it returns to the top of the while statement when it’s done with its evaluations.

The syntax of a while loop is :

while(Boolean_expression) {

 // Statements

}

Here, statement(s) may be a single statement or a block of statements. The condition may be any expression, and true is any non zero value.

When executing, if the boolean_expression result is true, then the actions inside the loop will be executed. This will continue as long as the expression result is true.

When the condition becomes false, program control passes to the line immediately following the loop.

## Flow Diagram:

![Java While Loop](images/00005.gif)

Here, key point of the while loop is that the loop might not ever run. When the expression is tested and the result is false, the loop body will be skipped and the first statement after the while loop will be executed.

## Example:

public  class  Test  {

 public  static  void main(String args[])  {

 int x =  10;

 while( x <  20  )  {

 System.out.print("value of x : "  + x );

         x++;

 System.out.print("\n");

 }

 }

}

This will produce the following result:

## Output:

value of x : 10

value of x : 11

value of x : 12

value of x : 13

value of x : 14

value of x : 15

value of x : 16

value of x : 17

value of x : 18

value of x : 19

For Loop:

To gain a bit more control over the execution of a loop, we have another option. The for loop requires three different statements to operate. The first statement is called an initialization, the second is a condition, and the third is an operation.

Syntax:

for(initialization; Boolean_expression; update) {

 // Statements

}

Here is the flow of control in a for loop −

*   The initialization step is executed first, and only once. This step allows you to declare and initialize any loop control variables and this step ends with a semi colon (;).
*   Next, the Boolean expressionis evaluated. If it is true, the body of the loop is executed. If it is false, the body of the loop will not be executed and control jumps to the next statement past the for loop.
*   After the body of the for loop gets executed, the control jumps back up to the update statement. This statement allows you to update any loop control variables. This statement can be left blank with a semicolon at the end.
*   The Boolean expression is now evaluated again. If it is true, the loop executes and the process repeats (body of loop, then update step, then Boolean expression). After the Boolean expression is false, the for loop terminates.

## Flow Diagram:

![Java For Loop](images/00006.gif)

## Example:

Following is an example code of the for loop in Java.

public  class  Test  {

 public  static  void main(String args[])  {

 for(int x =  10; x <  20; x = x +  1)  {

 System.out.print("value of x : "  + x );

 System.out.print("\n");

 }

 }

}

This will produce the following result:

## Output:

value of x : 10

value of x : 11

value of x : 12

value of x : 13

value of x : 14

value of x : 15

value of x : 16

value of x : 17

value of x : 18

value of x : 19

Loop Control Statements:

Loop control statements change execution from its normal sequence. When execution leaves a scope, all automatic objects that were created in that scope are destroyed.

Java supports the following control statements.

*   Break Statement
*   Continue Statement

The break statement in Java programming language has the following two usages −

*   When the break statement is encountered inside a loop, the loop is immediately terminated and the program control resumes at the next statement following the loop.
*   It can be used to terminate a case in the switch statement (covered in the next chapter).

## Syntax

The syntax of a break is a single statement inside any loop:

break;

## Flow Diagram:

![Java Break Statement](images/00007.jpeg)

## Example:

public  class  Test  {

 public  static  void main(String args[])  {

 int  [] numbers =  {10,  20,  30,  40,  50};

 for(int x : numbers )  {

 if( x ==  30  )  {

 break;

 }

 System.out.print( x );

 System.out.print("\n");

 }

 }

}

This will produce the following result:

## Output

10

20

The continue keyword can be used in any of the loop control structures. It causes the loop to immediately jump to the next iteration of the loop.

*   In a for loop, the continue keyword causes control to immediately jump to the update statement.
*   In a while loop or do/while loop, control immediately jumps to the Boolean expression.

## Syntax

The syntax of a continue is a single statement inside any loop −

continue;

## Flow Diagram:

![Java Continue Statement](images/00008.jpeg)

## Example:

public  class  Test  {

 public  static  void main(String args[])  {

 int  [] numbers =  {10,  20,  30,  40,  50};

 for(int x : numbers )  {

 if( x ==  30  )  {

 continue;

 }

 System.out.print( x );

 System.out.print("\n");

 }

 }

}

## Output:

10

20

40

50

Classes

The most important part of any Java program is the class. Classes here are not the sort that students go to; rather, they are classes in terms of classification. Classes in Java appear in several different forms. Some are called partial classes, and some classes can even appear inside of another class; these classes are called nested classes. A class is a collection of instructions and data. The instructions can be referred to as functions or methods. The data stored in a class is called a field or property. All of the naming aside, what’s important is what classes do and how they’re used.

Classes are flexible and easily changed, but this flexibility is not without some complexity. As we’ve seen before, the class declaration can contain a lot more than the following example. However, much of the complexity comes later in this book, when needed.

When you approach a game or any sort of programming task it’s important to first collect data, and then figure out how to use the data. In most programming paradigms it’s best to start off with variables at the beginning of your new class. For instance, in this pseudo code we might want to know what day it is before going out:

Time day = today;

if (day == Friday)

{

PartyTonight = true;

}

We start off with getting a day, and then deciding what to do tonight based on the day. We should refrain from partying and then checking what the day is unless we want to show up for work late. We’ll go into more detail on this topic later on, after we’ve learned about how to use a variable in a class properly.

Introduction to Objects

Object oriented programming (OOP) was invented to associate data and logic into nicely packaged bundles of code. When you write a class in Java you’re creating blueprints and instructions for a new object. Any number of objects can then be constructed based on your blueprints. Programmers use the term instantiate when talking about creating an object from the class blueprint. Each instantiated object is an instance of the class from which it was constructed. The class is not itself one of the instances created by it. The newly created object contains all of the functions and data written into the class.

All programming languages provide abstractions. It can be argued that the complexity of the problems you’re able to solve is directly related to the kind and quality of abstraction. By “kind” I mean, “What is it that you are abstracting?” Assembly language is a small abstraction of the underlying machine. Many so-called “imperative” languages that followed (such as FORTRAN, BASIC, and C) were abstractions of assembly language. These languages are big improvements over assembly language, but their primary abstraction still requires you to think in terms of the structure of the computer rather than the structure of the problem you are trying to solve.

The programmer must establish the association between the machine model (in the “solution space,” which is the place where you’re implementing that solution, such as a computer) and the model of the problem that is actually being solved (in the “problem space,” which is the place where the problem exists, such as a business). The effort required to perform this mapping, and the fact that it is extrinsic to the programming language, produces programs that are difficult to write and expensive to maintain, and as a side effect created the entire “programming methods” industry. 

The alternative to modeling the machine is to model the problem you’re trying to solve. Early languages such as LISP and APL chose particular views of the world (“All problems are ultimately lists” or “All problems are algorithmic,” respectively). Prolog casts all problems into chains of decisions. Languages have been created for constraint-based programming and for programming exclusively by manipulating graphical symbols. (The latter proved to be too restrictive.)

Each of these approaches may be a good solution to the particular class of problem they’re designed to solve, but when you step outside of that domain they become awkward. 

The object-oriented approach goes a step further by providing tools for the programmer to represent elements in the problem space. This representation is general enough that the programmer is not constrained to any particular type of problem. We refer to the elements in the problem space and their representations in the solution space as “objects.” (You will also need other objects that don’t have problem-space analogs.)

The idea is that the program is allowed to adapt itself to the lingo of the problem by adding new types of objects, so when you read the code describing the solution, you’re reading words that also express the problem. This is a more flexible and powerful language abstraction than what we’ve had before.1 Thus, OOP allows you to describe the problem in terms of the problem, rather than in terms of the computer where the solution will run. There’s still a connection back to the computer: Each object looks quite a bit like a little computer—it has a state, and it has operations that you can ask it to perform. However, this doesn’t seem like such a bad analogy to objects in the real world—they all have characteristics and behaviors.

To simply put, OOP is the process of building objects, instancing them, and then using them. Using objects involves reading data, using logic on the data, and then carrying out tasks based on the logic.

Characteristics of object-oriented programming:

These characteristics represent a pure approach to object-oriented programming: 

1\. Everything is an object. Think of an object as a fancy variable; it stores data, but you can “make requests” to that object, asking it to perform operations on itself. In theory, you can take any conceptual component in the problem you’re trying to solve (dogs, buildings, services, etc.) and represent it as an object in your program.

2\. A program is a bunch of objects telling each other what to do by sending messages. To make a request of an object, you “send a message” to that object. More concretely, you can think of a message as a request to call a method that belongs to a particular object.

3\. Each object has its own memory made up of other objects. Put another way, you create a new kind of object by making a package containing existing objects. Thus, you can build complexity into a program while hiding it behind the simplicity of objects.

4\. Every object has a type. Using the parlance, each object is an instance of a class, in which “class” is synonymous with “type.” The most important distinguishing characteristic of a class is “What messages can you send to it?”

5\. All objects of a particular type can receive the same messages. This is actually a loaded statement, as you will see later. Because an object of type “circle” is also an object of type “shape,” a circle is guaranteed to accept shape messages.  This  means you can write code that talks to shapes and automatically handle anything that fits the description of a shape. This substitutability is one of the powerful concepts in OOP.

Even more succinct description of an object is: 

An object has state, behavior and identity. 

This means that an object can have internal data (which gives it state), methods (to produce behavior), and each object can be uniquely distinguished from every other object—to put this in a concrete sense, each object has a unique address in memory.

An object has an interface:

So, although what we really do in object-oriented programming is create new data types, virtually all object-oriented programming languages use the “class” keyword. When you see the word “type” think “class” and vice versa.

Since a class describes a set of objects that have identical characteristics (data elements) and behaviors (functionality), a class is really a data type because a floating point number, for example, also has a set of characteristics and behaviors. The difference is that a programmer defines a class to fit a problem rather than being forced to use an existing data type that was designed to represent a unit of storage in a machine. You extend the programming language by adding new data types specific to your needs. The programming system welcomes the new classes and gives them all the care and type checking that it gives to built-in types. 

The object-oriented approach is not limited to building simulations. Whether or not you agree that any program is a simulation of the system you’re designing, the use of OOP techniques can easily reduce a large set of problems to a simple solution.   

Once a class is established, you can make as many objects of that class as you like, and then manipulate those objects as if they are the elements that exist in the problem you are trying to solve. Indeed, one of the challenges of object-oriented programming is to create a one-to one mapping between the elements in the problem space and objects in the solution space. 

But how do you get an object to do useful work for you? There needs to be a way to make a request of the object so that it will do something, such as complete a transaction, draw something on the screen, or turn on a switch. And each object can satisfy only certain requests. The requests you can make of an object are defined by its interface, and the type is what determines the interface. A simple example might be a representation of a light bulb:

![](images/00009.jpeg)

Light lt = new Light();

lt.on();

The interface determines the requests that you can make for a particular object. However, there must be code somewhere to satisfy that request. This, along with the hidden data, comprises the implementation. From a procedural programming standpoint, it’s not that complicated.

A type has a method associated with each possible request, and when you make a particular request to an object, that method is called. This process is usually summarized by saying that you “send a message” (make a request) to an object, and the object figures out what to do with that message (it executes code). 

Here, the name of the type/class is Light, the name of this particular Light object is lt, and the requests that you can make of a Light object are to turn it on, turn it off, make it brighter, or make it dimmer. You create a Light object by defining a “reference” (lt) for that object and calling new to request a new object of that type. To send a message to the object, you state the name of the object and connect it to the message request with a period (dot). From the standpoint of the user of a predefined class, that’s pretty much all there is to programming with objects. 

The preceding diagram follows the format of the Unified Modeling Language (UML). Each class is represented by a box, with the type name in the top portion of the box, any data members that you care to describe in the middle portion of the box, and the methods (the functions that belong to this object, which receive any messages you send to that object) in the bottom portion of the box. Often, only the name of the class and the public methods are shown in UML design diagrams, so the middle portion is not shown, as in this case. If you’re interested only in the class name, then the bottom portion doesn’t need to be shown, either.

An object provides services:

While you’re trying to develop or understand a program design, one of the best ways to think about objects is as “service providers.” Your program itself will provide services to the user, and it will accomplish this by using the services offered by other objects. Your goal is to produce (or even better, locate in existing code libraries) a set of objects that provide the ideal services to solve your problem. 

A way to start doing this is to ask, “If I could magically pull them out of a hat, what objects would solve my problem right away?” For example, suppose you are creating a bookkeeping program. You might imagine some objects that contain pre-defined bookkeeping input screens, another set of objects that perform bookkeeping calculations, and an object that handles printing of checks and invoices on all different kinds of printers. Maybe some of these objects already exist, and for the ones that don’t, what would they look like? What services would those objects provide, and what objects would they need to fulfill their obligations? If you keep doing this, you will eventually reach a point where you can say either, “That object seems simple enough to sit down and write” or “I’m sure that object must exist already.” This is a reasonable way to decompose a problem into a set of objects. 

Thinking of an object as a service provider has an additional benefit:      It helps to improve the cohesiveness of the object. High cohesion is a fundamental quality of software design: It means that the various aspects of a software component (such as an object, although this could also apply to a method or a library of objects) “fit together” well. One problem people have when designing objects is cramming too much functionality into one object. For example, in your check printing module, you may decide you need an object that knows all about formatting and printing. You’ll probably discover that this is too much for one object, and that what you need is three or more objects. One object might be a catalog of all the possible check layouts, which can be queried for information about how to print a check. One object or set of objects can be a generic printing interface that knows all about different kinds of printers (but nothing about bookkeeping—this one is a candidate for buying rather than writing yourself). And a third object could use the services of the other two to accomplish the task. Thus, each object has a cohesive set of services it offers. In a good object-oriented design, each object does one thing well, but doesn’t try to do too much. This not only allows the discovery of objects that might be purchased (the printer interface object), but it also produces new objects that might be reused somewhere else (the catalog of check layouts). 

Treating objects as service providers is a great simplifying tool. This is useful not only during the design process, but also when someone else is trying to understand your code or reuse an object. If they can see the value of the object based on what service it provides, it makes it much easier to fit it into the design. 

The hidden implementation: 

It is helpful to break up the playing field into class creators (those who create new data types) and client programmers4 (the class consumers who use the data types in their applications). The goal of the client programmer is to collect a toolbox full of classes to use for rapid application development. The goal of the class creator is to build a class that exposes only what’s necessary to the client programmer and keeps everything else hidden. Why? Because if it’s hidden, the client programmer can’t access it, which means that the class creator can change the hidden portion at will without worrying about the impact on anyone else. The hidden portion usually represents the tender insides of an object that could easily be corrupted by a careless or uninformed client programmer, so hiding the implementation reduces program bugs. 

In any relationship it’s important to have boundaries that are respected by all parties involved. When you create a library, you establish a relationship with the client programmer, who is also a programmer, but one who is putting together an application by using your library, possibly to build a bigger library. If all the members of a class are available to everyone, then the client programmer can do anything with that class and there’s no way to enforce rules. Even though you might really prefer that the client programmer not directly

manipulate some of the members of your class, without access control there’s no way to prevent it. Everything’s naked to the world. 

So the first reason for access control is to keep client programmers’ hands off portions they shouldn’t touch—parts that are necessary for the internal operation of the data type but not part of the interface that users need in order to solve their particular problems. This is actually a service to client programmers because they can easily see what’s important to them and what they can ignore. 

The second reason for access control is to allow the library designer to change the internal workings of the class without worrying about how it will affect the client programmer. For example, you might implement a particular class in a simple fashion to ease development, and then later discover that you need to rewrite it in order to make it run faster. If the interface and implementation are clearly separated and protected, you can accomplish this easily. 

Java uses three explicit keywords to set the boundaries in a class: public, private, and protected. These access specifiers determine who can use the definitions that follow. public means the following element is available to everyone. The private keyword, on the other hand, means that no one can access that element except you, the creator of the type, inside methods of that type. private is a brick wall between you and the client programmer. Someone who tries to access a private member will get a compile-time error. The protected keyword acts like private, with the exception that an inheriting class has access to protected members, but not private members. Inheritance will be introduced shortly. 

Java also has a “default” access, which comes into play if you don’t use one of the aforementioned specifiers. This is usually called package access because classes can access the members of other classes in the same package (library component), but outside of the package those same members appear to be private. 

Reusing the implementation:

Once a class has been created and tested, it should (ideally) represent a useful unit of code. It turns out that this reusability is not nearly so easy to achieve as many would hope; it takes experience and insight to produce a reusable object design. But once you have such a design, it begs to be reused. Code reuse is one of the greatest advantages that object-oriented programming languages provide. 

The simplest way to reuse a class is to just use an object of that class directly, but you can also place an object of that class inside a new class. We call this “creating a member object.” Your new class can be made up of any number and type of other objects, in any combination that you need to achieve the functionality desired in your new class. Because you are composing a new class from existing classes, this concept is called composition (if the composition happens dynamically, it’s usually called aggregation). Composition is often referred to as a “has-a” relationship, as in “A car has an engine.” 

![](images/00010.jpeg)

(This UML diagram indicates composition with the filled diamond, which states there is one car. I will typically use a simpler form: just a line, without the diamond, to indicate an association.5) 

Composition comes with a great deal of flexibility. The member objects of your new class are typically private, making them inaccessible to the client programmers who are using the class. This allows you to change those members without disturbing existing client code. You can also change the member objects at run time, to dynamically change the behavior of your program. Inheritance, which is described next, does not have this flexibility since the compiler must place compile-time restrictions on classes created with inheritance. 

Because inheritance is so important in object-oriented programming, it is often highly emphasized, and the new programmer can get the idea that inheritance should be used everywhere. This can result in awkward and overly complicated designs. Instead, you should first look to composition when creating new classes, since it is simpler and more flexible. If you take this approach, your designs will be cleaner. Once you’ve had some experience, it will be reasonably obvious when you need inheritance. 

Inheritance:

By itself, the idea of an object is a convenient tool. It allows you to package data and functionality together by concept, so you can represent an appropriate problem-space idea rather than being forced to use the idioms of the underlying machine. These concepts are expressed as fundamental units in the programming language by using the class keyword. 

It seems a pity, however, to go to all the trouble to create a class and then be forced to create a brand new one that might have similar functionality. It’s nicer if we can take the existing class, clone it, and then make additions and modifications to the clone. This is effectively what you get with inheritance, with the exception that if the original class (called the base class or superclass or parent class) is changed, the modified “clone” (called the derived class or inherited class or subclass or child class) also reflects those changes.  

![](images/00011.jpeg)

(The arrow in this UML diagram points from the derived class to the base class. As you will see, there is commonly more than one derived class.) 

A type does more than describe the constraints on a set of objects; it also has a relationship with other types. Two types can have characteristics and behaviors in common, but one type may contain more characteristics than another and may also handle more messages (or handle them differently). Inheritance expresses this similarity between types by using the concept of base types and derived types. A base type contains all of the characteristics and behaviors that are shared among the types derived from it. You create a base type to represent the core of your ideas about some objects in your system. From the base type, you derive other types to express the different ways that this core can be realized. 

For example, a trash-recycling machine sorts pieces of trash. The base type is “trash”, and each piece of trash has a weight, a value, and so on, and can be shredded, melted, or decomposed. From this, more specific types of trash are derived that may have additional characteristics (a bottle has a color) or behaviors (an aluminum can may be crushed, a steel can is magnetic). In addition, some behaviors may be different (the value of paper depends on its type and condition). Using inheritance, you can build a type hierarchy that expresses the problem you’re trying to solve in terms of its types. 

A second example is the classic “shape” example, perhaps used in a computer-aided design system or game simulation. The base type is “shape,” and each shape has a size, a color, a position, and so on. Each shape can be drawn, erased, moved, colored, etc. From this, specific types of shapes are derived (inherited)—circle, square, triangle, and so on—each of which may have additional characteristics and behaviors. Certain shapes can be flipped, for example. Some behaviors may be different, such as when you want to calculate the area of a shape. The type hierarchy embodies both the similarities and differences between the shapes.  

![](images/00012.jpeg)

Casting the solution in the same terms as the problem is very useful because you don’t need a lot of intermediate models to get from a description of the problem to a description of the solution. With objects, the type hierarchy is the primary model, so you go directly from the description of the system in the real world to the description of the system in code. Indeed, one of the difficulties people have with object-oriented design is that it’s too simple to get from the beginning to the end. A mind trained to look for complex solutions can initially be stumped by this simplicity. 

When you inherit from an existing type, you create a new type. This new type contains not only all the members of the existing type (although the private ones are hidden away and inaccessible), but more importantly it duplicates the interface of the base class. That is, all the messages you can send to objects of the base class you can also send to objects of the derived class. Since we know the type of a class by the messages we can send to it, this means that the derived class is the same type as the base class. In the previous example, “A circle is a shape.” This type equivalence via inheritance is one of the fundamental gateways in understanding the meaning of object-oriented programming. 

Since both the base class and derived class have the same fundamental interface, there must be some implementation to go along with that interface. That is, there must be some code to execute when an object receives a particular message. If you simply inherit a class and don’t do anything else, the methods from the base-class interface come right along into the derived class. That means objects of the derived class have not only the same type, they also have the same behavior, which isn’t particularly interesting. 

You have two ways to differentiate your new derived class from the original base class. The first is quite straightforward: You simply add brand new methods to the derived class. These new methods are not part of the base-class interface. This means that the base class simply didn’t do as much as you wanted it to, so you added more methods. This simple and primitive use for inheritance is, at times, the perfect solution to your problem. However, you should look closely for the possibility that your base class might also need these additional methods. This process of discovery and iteration of your design happens regularly in object-oriented programming.  

Interchangeable objects with polymorphism:

When dealing with type hierarchies, you often want to treat an object not as the specific type that it is, but instead as its base type. This allows you to write code that doesn’t depend on specific types. In the shape example, methods manipulate generic shapes, unconcerned about whether they’re circles, squares, triangles, or some shape that hasn’t even been defined yet. All shapes can be drawn, erased, and moved, so these methods simply send a message to a shape object; they don’t worry about how the object copes with the message. 

Such code is unaffected by the addition of new types, and adding new types is the most common way to extend an object-oriented program to handle new situations. For example, you can derive a new subtype of shape called pentagon without modifying the methods that deal only with generic shapes. This ability to easily extend a design by deriving new subtypes is one of the essential ways to encapsulate change. This greatly improves designs while reducing the cost of software maintenance. 

There’s a problem, however, with attempting to treat derived-type objects as their generic base types (circles as shapes, bicycles as vehicles, cormorants as birds, etc.). If a method is going to tell a generic shape to draw itself, or a generic vehicle to steer, or a generic bird to move, the compiler cannot know at compile time precisely what piece of code will be executed. That’s the whole point—when the message is sent, the programmer doesn’t want to know what piece of code will be executed; the draw method can be applied equally to a circle, a square, or a triangle, and the object will execute the proper code depending on its specific type. 

If you don’t have to know what piece of code will be executed, then when you add a new subtype, the code it executes can be different without requiring changes to the method that calls it. Therefore, the compiler cannot know precisely what piece of code is executed, so what does it do? 

For example, in the following diagram the BirdController object just works with generic Bird objects and does not know what exact type they are. This is convenient from BirdController’s perspective because it doesn’t have to write special code to determine the exact type of Bird it’s working with or that Bird’s behavior. So how does it happen that, when move( ) is called while ignoring the specific type of Bird, the right behavior will occur (a Goose walks, flies, or swims, and a Penguin walks or swims)?

![](images/00013.jpeg)

The answer is the primary twist in object-oriented programming:        The compiler cannot make a function call in the traditional sense. The function call generated by a non-OOP compiler causes what is called early binding, a term you may not have heard before because you’ve never thought about it any other way. It means the compiler generates a call to a specific function name, and the runtime system resolves this call to the absolute address of the code to be executed. In OOP, the program cannot determine the address of the code until run time, so some other scheme is necessary when a message is sent to a generic object. 

To solve the problem, object-oriented languages use the concept of late binding. When you send a message to an object, the code being called isn’t determined until run time. The compiler does ensure that the method exists and performs type checking on the arguments and return value, but it doesn’t know the exact code to execute. 

To perform late binding, Java uses a special bit of code in lieu of the absolute call. This code calculates the address of the method body, using information stored in the object (this process is covered in great detail in the Polymorphism chapter). Thus, each object can behave differently according to the contents of that special bit of code. When you send a message to an object, the object actually does figure out what to do with that message. 

In some languages you must explicitly state that you want a method to have the flexibility of late binding properties (C++ uses the virtual keyword to do this). In these languages, by default, methods are not dynamically bound. In Java, dynamic binding is the default behavior and you don’t need to remember to add any extra keywords in order to get     polymorphism.

Types

When we assign a variable a value such as int i = 1; we’re making an interesting assumption. We assume using 1 automatically infers a value type that matches the variable type. Computers use a wide variety of different types of data for storing numbers. So far we’ve been seeing the word int being thrown around as though you know what an int is. In our everyday lives we hardly think there’s any difference between numbers 1 and 1.0 or even the word one.

As humans we can easily conceptualize numbers as units of measure and converting between them. The conversion between the word one and the number 1 isn’t so easy for a computer. The keyword int is short for integer. Integers are whole number values. The integer is a Java built-in type. Basically, this means that integers are a fundamental part of java. Other built-in types include float, double, string, bool, and object. Less commonly used built-in types are char, short, and byte. Altogether, there are 15 different built-in types.

All of these, except object and string, are value types. Every type of data you’re able to build must be based on all of these built-in types. The system which creates all of these floats, doubles, and bools is rooted in the origin of computing. Remember the punch tapes and pieces of paper with holes in them? Those were records of 1s and 0s which were fed into computers for storing in the form of mechanical switches, either on or off. The patterns represented numbers or instructions and logic.

Today, we still use the same system of 1s and 0s, or binary, only we don’t need to punch holes in paper to tell the computer what to do. The methods of creating and storing the instructions have become many times more complex, but nonetheless the principle of the 1 and 0 are the same. These are called bits; one possible origin for that name is the little bits of paper that were left over from punching all of the holes in the paper cards.

Value and Reference Types:

The int, float, double, and bool are commonly used value types. The basics of this usage pattern relate to the system that stores and organizes the computer’s memory. When you talk about computer storage you use the word megabyte or gigabyte. Value types are stored with a very specific purpose in mind: to keep track of a numeric value.

NOTE:

The word mega refers to how many millions of bytes a component in your computer can store. Giga indicates how every many billions of bytes are being stored. Have you ever thought about what a byte actually is? A byte is what is called an 8-bit unsigned integer, or a system of using 8 bits to form a number. What this means is that it’s a whole number like 0, 7, or 32,767\. The word unsigned indicates that the number cannot be negative, like −512\. A 1 or 0 in computer terms is called a bit. We won’t go into detail on how computers use bits to count, and it’s a rather fun thing to learn on your own.

However, it’s important to know that a byte has a limited range, from 0 to 255\. I’ll just leave you with the idea that you could count up to 1023 on your 10 fingers if you used binary rather than decimal. Your fingers can be used to represent a 10-bit unsigned integer. The computer’s calculation capabilities used to be far more limited than they are today. An 8-bit game console made in the 1980s had a limited number of colors, 256 to be exact.

This limitation was based on the number of bits that the processor could handle. The processor had a limited number of transistors which could be used at any one time. Shortly after, floating point coprocessors were introduced, which had a much larger numeric range allowed, by having closer to 32 bits to work with. In all of these cases, when you use a value type, that number is actually stored as 1s and 0s in your computer’s RAM. This should be considered fairly remarkable.

In the past you’d have to go through flaming hoops to store a value. Now you just type in float f = 3.1415926535; and you can measure the circumference of the universe accurately to within the width of a single atom. What all of these types have in common is that they are stored as a single element. Large values like  double  gigawatts = 1210000000.0; and double mint = 2.0; use the same amount of memory.

Your computer doesn’t assign one double or the other more space in memory. These types are referred to as primitive types. The only difference between an int and a float is the number of bits they use at a time, 8 and 32 respectively; doubles use 64 bits.

The string and object types differ a bit in how they are stored. These types are a composite of any number smaller elements. The bigger a string or object the bigger chunk of memory the computer opens up to place that object or string. These are called reference types or sometimes called nullable types because Java doesn’t look to a single element in memory to get data from it.

Strong Typing:

This has nothing to do with how hard you type on the keyboard!

Java sees a difference between numbers in how they are written. A whole number like 1 is different from 1.0, even though we can think of them as having the same value. Some of these differences can be added by adding a letter. Therefore, 1.0 and 1.0f are actually different numbers as well. Java is a strongly typed programming language. When a programming language uses strong types you’re expected to keep the different types separated.

This means that a 1 + 1.0f can create a problem. Because the two numbers are actually different types of numbers we have to convert one of them to match the other before the operation is allowed to take place. To convert from one type to another we have to tell Java that we intend to make that conversion from a 1 to a 1.0 by using what’s called a cast operator. Aside from changing how memory is used, types also limit any problems which might come about when working in a team of programmers.

Thinking in Algorithms

An algorithm is a detailed step-by-step instruction set or formula for solving a problem or completing a task. In computing, programmers write algorithms that instruct the computer how to perform a task.

When you think of an algorithm in the most general way (not just in regards to computing), algorithms are everywhere. A recipe for making food is an algorithm, the method you use to solve addition or long division problems is an algorithm, and the process of folding a shirt or a pair of pants is an algorithm. Even your morning routine could be considered an algorithm! In fact, here’s what your child’s morning might look like written out as an algorithm:

![](images/00014.jpeg)

What kinds of problems are solved by   algorithms?

Sorting is by no means the only computational problem for which algorithms have been developed. Practical applications of algorithms are ubiquitous and include the following examples:

1.  The Human Genome Project has made great progress toward the goals of identifying all the 100,000 genes in human DNA, determining the sequences of the 3 billion chemical base pairs that make up human DNA, storing this information in databases, and developing tools for data analysis. Each of these steps requires sophisticated algorithms. Although the solutions to the various problems involved are beyond the scope of this book, many methods to solve these biological problems use ideas from several of the chapters in this book, thereby enabling scientists to accomplish tasks while using resources efficiently. The savings are in time, both human and machine, and in money, as more information can be extracted from laboratory techniques.
2.  The Internet enables people all around the world to quickly access and retrieve large amounts of information. With the aid of clever algorithms, sites on the Internet are able to manage and manipulate this large volume of data. Examples of problems that make essential use of algorithms include finding good routes on which the data will travel, and using a search engine to quickly find pages on which particular information resides.
3.  Electronic commerce enables goods and services to be negotiated and exchanged electronically, and it depends on the privacy of personal information such as credit card numbers, passwords, and bank statements. The core technologies used in electronic commerce include public-key cryptography and digital signatures, which are based on numerical algorithms and number theory.
4.  Manufacturing and other commercial enterprises often need to allocate scarce resources in the most beneficial way. An oil company may wish to know where to place its wells in order to maximize its expected profit. A political candidate may want to determine where to spend money buying campaign advertising in order to maximize the chances of winning an election. An airline may wish to assign crews to flights in the least expensive way possible, making sure that each flight is covered and that government regulations regarding crew scheduling are met. An Internet service provider may wish to determine where to place additional resources in order to serve its customers more effectively. All of these are examples of problems that can be solved using linear programming.

Although some of the details of these examples are beyond the scope of this book, we do give underlying techniques that apply to these problems and problem areas.

Algorithms as a technology

Suppose computers were infinitely fast and computer memory was free. Would you have any reason to study algorithms? The answer is yes, if for no other reason than that you would still like to demonstrate that your solution method terminates and does so with the correct answer.

If computers were infinitely fast, any correct method for solving a problem would do.

You would probably want your implementation to be within the bounds of good software engineering practice (for example, your implementation should be well designed and documented), but you would most often use whichever method was the easiest to implement. Of course, computers may be fast, but they are not infinitely fast. And memory may be inexpensive, but it is not free.

Computing time is therefore a bounded resource, and so is space in memory. You should use these resources wisely, and algorithms that are efficient in terms of time or space will help you do so.

Where storage lives?

It’s useful to visualize some aspects of how things are laid out while the program is running— in particular how memory is arranged. There are five different places to store data: 

1\. Registers. This is the fastest storage because it exists in a place different from that of other storage: inside the processor. However, the number of registers is severely limited, so registers are allocated as they are needed. You don’t have direct control, nor do you see any evidence in your programs that registers even exist (C & C++, on the other hand, allow you to suggest register allocation to the compiler).  

2\. The stack. This lives in the general random-access memory (RAM) area, but has direct support from the processor via its stack pointer. The stack pointer is moved down to create new memory and moved up to release that memory. This is an extremely fast and efficient way to allocate storage, second only to registers. The Java system must know, while it is creating the program, the exact lifetime of all the items that are stored on the stack. This constraint places limits on the flexibility of your programs, so while some Java storage exists on the stack—in particular, object references—Java objects themselves are not placed on the stack.

3\. The heap. This is a general-purpose pool of memory (also in the RAM area) where all Java objects live. The nice thing about the heap is that, unlike the stack, the compiler doesn’t need to know how long that storage must stay on the heap. Thus, there’s a great deal of flexibility in using storage on the heap. Whenever you need an object, you simply write the code to create it by using new, and the storage is allocated on the heap when that code is executed. Of course there’s a price you pay for this flexibility: It may take more time to allocate and clean up heap storage than stack storage (if you even could create objects on the stack in Java, as you can in C++).

4\. Constant storage. Constant values are often placed directly in the program code, which is safe since they can never change. Sometimes constants are cordoned off by themselves so that they can be optionally placed in read-only memory (ROM), in embedded systems.2

5\. Non-RAM storage. If data lives completely outside a program, it can exist while the program is not running, outside the control of the program. The two primary examples of this are streamed objects, in which objects are turned into streams of bytes, generally to be sent to another machine, and persistent objects, in which the objects are placed on disk so they will hold their state even when the program is terminated. The trick with these types of storage is turning the objects into something that can exist on the other medium, and yet can be resurrected into a regular RAMbased object when necessary. Java provides support for lightweight persistence, and mechanisms such as JDBC and Hibernate provide more sophisticated support for storing and retrieving object information in databases.

Statements and Expressions

When reading a book or story you extract meaning from an ordered chain of words.
In a similar way, computers extract commands from a chain of ordered instructions.
In English we call this a sentence; programmers call this a statement.

A statement is considered to be any chunk of code which accomplishes some sort of task separated by a semicolon. At the center of any given task is the algorithm, not to be confused with a logarithm.
An algorithm is a systematic process that accomplishes something. In many ways you can think of it as a recipe, or rather a recipe is an algorithm for making food.
It can take just one or two statements to accomplish a task, or it could take many hundreds of statements.

![https://3.bp.blogspot.com/-qi_h4uWuaLY/WBNQIt6zNjI/AAAAAAAAGso/63MfQEDmp7IJghpMTGRN3vZTiuLiYla3wCK4B/s400/PascalScriptIfThenElse.png](images/00015.jpeg)

This all depends on the difficulty of a given task. Each individual statement is a step toward a goal. This is the difference between spending a few minutes frying an egg, orspending an hour baking a souffle. Each step is usually fairly simple; it’s thefinal result that matters.
Like sentences, statements have different forms. Statements can declare and assign values to variables. These are called declaration and assignment statements. These statements are used to set up various types of data and give them names.

Expressions:

The subjects of your statements are called identifiers. An assignment statement is used to give an identifier a value. When you read “Jack is a boy and Jill is a girl,” you’ve mentally assigned two subjects their genders.

In Java this might look more like:
gender Jack = male;

gender Jill = female;

Assignment statements often incorporate some sort of operation.
These are called expressive statements. Different from expressing an emotion, expressions in code look more like “x + y.” Expressions process data. After processing, the result of an expression can be assigned to a variable.

A collection of statements is called a code block, not like a roadblock which might stop your code, but more like a building block, anything that’s used to build.
When writing a story, we call a collection of sentences a paragraph. The statements in a block of code work with each other to accomplish a task.

How Code Is Executed:

When a class is created, all of its instructions are not carried out at the same time. As it’s been explained, each collection of parts in a class is made up of lines of text called statements. Each statement is carried out in order. Where the computer starts is usually dependent on which collection of statements it’s told to start with. You’re in charge of how the code is started.

Java provides us with a function called Main(),which we’ll go into later. However, this is the preferred place to begin our code using Java. Once Main() is called, the computer goes to the first line in Main() and begins to carry out the instructions written there. As the computer gets to each statement the computer starts on the left of the statement and works its way to the right. Basically, a computer reads code like you’re reading this sentence.

Learning To Copy & Paste

“A good artist creates, a great artist steals.” There are code examples for you to copy and paste into your project. The content of this book and all downloadable content are no different. This means that you’ll have to understand what the code is doing to interpret it to fit your needs.
Every programmer does this habitually.

 ![https://3.bp.blogspot.com/-YFiXeWOGauQ/WBNOs__W1OI/AAAAAAAAGsc/Ug6oi8Vi3A4bz9wIIepvh0w2f96G_3CswCK4B/s320/copypaste_logo.png](images/00016.jpeg)

It is important to learn how to do this since it is something that you actually need to do in many cases not only to learn but also to get any unfamiliar task done. Programming is a constant learning process. It is a language to command computers.
Anytime you learn a new language, there will be plenty of words which you’ll have to look up.
Add to this the fact that every programmer gets to make up new words, and you’ve got a language that you’ll always need a dictionary for.

When some code is shown, you’ll be expected to copy that code into your project. With your fingers ready on the keyboard, you’ll want to get in the habit of typing.

There is a reason why programmers are usually fast typists. This is also cause for programmers to be picky about what keyboard they prefer. In most cases, the projects in this book will be in some state where you can read text that is already in place.
Most of the projects are in a more complete state, where you’ll be able to run them and see an intended result. As a programmer I’ve gotten used to searching the Internet for example code.
Once I’ve discovered something that looks useful, I copy that code and paste it into a simple test case. After I’ve wrapped my head around what the code is doing, I rewrite it in a form that is more suited for my specific case.
Even if the code involves some fun trick, I’ll learn from that code.
As I learn new tricks, I grow as a programmer. The only way to learn new tricks is to find the necessity to solve a new problem for which I haven’t already figured out a solution. Finding solutions to problems is a fundamental part of being a programmer.

Understanding Floating Points

Floating point numbers have been a focus of computers for many years. Gaining floating point accuracy was the goal of many early computer scientists. Because there are an infinite possibilities of how many numbers can follow a decimal point, it’s impossible to truly represent any fraction completely using binary computing.

A common example is π, which we call pi. It’s assumed that there are an endless number of digits following 3.14\. Even today computers are set loose to calculate the hundreds of billions of digits beyond the decimal point.

Computers set aside some of the bits of a floating point number aside to represent where the decimal appears in the number, but even this is limited. The first bit is usually the sign bit, setting the negative or positive range of the number. The following 8 bits is the exponent for the number called a mantissa. The remaining bits are the rest of the number appearing around the decimal point. A float value can move the decimal 38 digits in either direction, but it’s limited to the values it’s able to store.

Without special considerations, computers are not able to handle arbitrarily large numbers. To cast a float into an int, you need to be more explicit.

That’s why Java requires you to use the cast and you need to add the (int) in

int Zint = (int)Zmove;.

The (int) is a cast operator; or rather (type) acts as a converter from the type on the right to the type needed on the left.

Big O Notation

Big O notation is the language we use for articulating how long an algorithm takes to run. It's how we compare the efficiency of different approaches to a problem.

 Imagine you have a list of 10 objects, and you want to sort them in order.  There’s a whole bunch of algorithms you can use to make that happen, but not all algorithms are built equal.  Some are quicker than others but more importantly the speed of an algorithm can vary depending on how many items it’s dealing with. Big O is a way of measuring how an algorithm scales.  Big O references how complex an algorithm is.

Big O is represented using something like O(n).  The O simply denoted we’re talking about big O and you can ignore it (at least for the purpose of the interview).  n is the thing the complexity is in relation to; for programming interview questions this is almost always the size of a collection. The complexity will increase or decrease in accordance with the size of the data store.

Below is a list of the Big O complexities in order of how well they scale relative to the dataset.

O(1)/Constant Complexity: Constant.  This means irrelevant of the size of the data set the algorithm will always take a constant time. 1 item takes 1 second, 10 items takes 1 second, 100 items takes 1 second. It always takes the same amount of time.

O(log n)/Logarithmic Complexity: Not as good as constant, but still pretty good.  The time taken increases with the size of the data set, but not proportionately so. This means the algorithm takes longer per item on smaller datasets relative to larger ones.   1 item takes 1 second, 10 items takes 2 seconds, 100 items takes 3 seconds. If your dataset has 10 items, each item causes 0.2 seconds latency. If your dataset has 100, it only takes 0.03 seconds extra per item. This makes log n algorithms very scalable.

O(n)/Linear Complexity: The larger the data set, the time taken grows proportionately.  1 item takes 1 second, 10 items takes 10 seconds, 100 items takes 100 seconds.

O(n log n): A nice combination of the previous two.  Normally there’s 2 parts to the sort, the first loop is O(n), the second is O(log n), combining to form O(n log n) 1 item takes 2 seconds, 10 items takes 12 seconds, 100 items takes 103 seconds.

O(n^2)/Quadratic Complexity: Things are getting extra slow. 1 item takes 1 second, 10 items takes 100, 100 items takes 10000\.  

O(2^n): Exponential Growth! The algorithm takes twice as long for every new element added.  1 item takes 1 second, 10 items takes 1024 seconds, 100 items takes 1267650600228229401496703205376 seconds.

Examples:

Hopefully you’re with me so far, but let’s dive into some example algorithms for sorting and searching.  The important thing is to be able to explain what complexity an algorithm is.  Interviewers love to get candidates to design algorithms and then ask what the complexity of it is.

### 1. O(1)

Irrelevant of the size, it will always return at constant speed. The javadoc for Queue states that it is  “constant time for the retrieval methods (peek, element, and size)”. It’s pretty clear why this is the case.  For peek, we are always returning the first element which we always have a reference to; it doesn’t matter how many elements follow it.  The size of the list is updated upon element addition/removal, and referencing this number is just one operation to access no matter what the size of the list is.

### 2. O(log n)

The classic example is a Binary search.  You’re a massive geek so you’ve obviously alphabetised your movie collection. To find your copy of “Back To The Future”, you first go to the middle of the list. You discover the middle film is “Meet The Fockers”, so you then head to the movie in between the start and this film.  You discover this is “Children of Men”. You repeat this again and you’ve found back to the future.

Although adding more elements will increase the amount of time it takes to search, it doesn’t do so proportionally. Therefore it is O(log n).

### 3. O(n)

As discussed in my post on collections, LinkedLists are not so good (relatively speaking) when it comes to retrieval.  It actually has a Big O of O(n) as in the worst case, to find an element T which is the last element in the list, it is necessary to navigate the entire list of n elements to find T. As the number of elements increases so does the access time in proportion.

### 4. O(n log n)

The best example of O(n log n) is a merge sort. This is a divide and conquer algorithm. Imagine you have a list of integers. We divide the list in two again and again until we are left with with a number of lists with 1 item in: each of these lists is therefore sorted.We then merge each list with it’s neighbour (comparing the first elements of each every time). We repeat this with the new composite list until we have our sorted result.

## How to figure out Big O in an interview?

This is not an exhaustive list of Big O.  Much as you can O(n2), you can also have O(n^3) (imagine throwing an extra loop into your bubble sort for no apparent reason).  What the list on this page should allow you to do is have a stab in the dark at figuring out what the big O of an algorithm is.  If someone is asking you this during an interview they probably want to see how you try and figure it out. Break down the loops and processing.

*   Does it have to go through the entire list? There will be an n in there somewhere.
*   Does the algorithms processing time increase at a slower rate than the size of the data set? Then there’s probably a log n in there.
*   Are there nested loops? You’re probably looking at n^2 or n^3.
*   Is access time constant irrelevant of the size of the dataset?? O(1)

## Sample Questions:

I have an array of the numbers 1 to 100 in a random number. One of the numbers is missing. Write an algorithm to figure out what the number is and what position is missing.

There are many variations of this question all of which are very popular.  To calculate the missing number we can simply add up all the numbers we do have, and subtract this from the expected answer of the sum of all numbers between 1 and 100\.  To do this we have to iterate the list once. Whilst doing this we can also note which spot has the gap.

public void findTheBlank(int[] theNumbers) {

int sumOfAllNumbers = 0;

int sumOfNumbersPresent = 0;

int blankSpace = 0;

for (int i = 0; i < theNumbers.length; i++) {

sumOfAllNumbers += i + 1;

sumOfNumbersPresent += theNumbers[i];

if (theNumbers[i] == 0)

blankSpace = i;

}

System.out.println("Missing number = " + (sumOfAllNumbers - sumOfNumbersPresent) + " at location " + blankSpace +" of the array");

}

new BubbleSort().findTheBlank(new int[]{7,6,0,1,3,2,4});

//Missing number = 5 at location 2 of the array

What is the big O for this algorithm?

Our algorithm iterates through our list once, so it’s simply O(n).

Big-O Complexity Chart:

![](images/00017.jpeg)

![](images/00018.jpeg)

Array Sorting Algorithms complexity:

![](images/00019.jpeg)

Chapter 3 | Data Structures & Programming Questions

Sorting and Searching

![](images/00020.jpeg)

Binary Search

Binary search is one of the fundamental algorithms in computer science. In order to explore it, we’ll first build up a theoretical backbone, then use that to implement the algorithm properly and avoid those nasty off-by-one errors everyone’s been talking about.

Finding a value in a sorted sequence
In its simplest form, binary search is used to quickly find a value in a sorted sequence (consider a sequence an ordinary array for now). We’ll call the sought value the target value for clarity. Binary search maintains a contiguous subsequence of the starting sequence where the target value is surely located. This is called the search space. The search space is initially the entire sequence. At each step, the algorithm compares the median value in the search space to the target value. Based on the comparison and because the sequence is sorted, it can then eliminate half of the search space. By doing this repeatedly, it will eventually be left with a search space consisting of a single element, the target value.

For example, consider the following sequence of integers sorted in ascending order and say we are looking for the number 55:

| 0 | 5 | 13 | 19 | 22 | 41 | 55 | 68 | 72 | 81 | 98 |

We are interested in the location of the target value in the sequence so we will represent the search space as indices into the sequence. Initially, the search space contains indices 1 through 11\. Since the search space is really an interval, it suffices to store just two numbers, the low and high indices. As described above, we now choose the median value, which is the value at index 6 (the midpoint between 1 and 11): this value is 41 and it is smaller than the target value. From this we conclude not only that the element at index 6 is not the target value, but also that no element at indices between 1 and 5 can be the target value, because all elements at these indices are smaller than 41, which is smaller than the target value. This brings the search space down to indices 7 through 11:

| 55 | 68 | 72 | 81 | 98 |

Proceeding in a similar fashion, we chop off the second half of the search space and are left with:

| 55 | 68 |

Depending on how we choose the median of an even number of elements we will either find 55 in the next step or chop off 68 to get a search space of only one element. Either way, we conclude that the index where the target value is located is 7.

If the target value was not present in the sequence, binary search would empty the search space entirely. This condition is easy to check and handle. Here is some code to go with the description:

binary_search(A, target):

   lo = 1, hi = size(A)

   while lo <= hi:

      mid = lo + (hi-lo)/2

      if A[mid] == target:

         return mid           

      else if A[mid] < target:

         lo = mid+1

      else:

         hi = mid-1

   // target was not found

Complexity:
Since each comparison binary search uses halves the search space, we can assert and easily prove that binary search will never use more than (in big-oh notation) O(log N) comparisons to find the target value.

The logarithm is an awfully slowly growing function. In case you’re not aware of just how efficient binary search is, consider looking up a name in a phone book containing a million names. Binary search lets you systematically find any given name using at most 21 comparisons. If you could manage a list containing all the people in the world sorted by name, you could find any person in less than 35 steps. 

Program: Java implementation of recursive Binary Search

class BinarySearch

{

    // Returns index of x if it is present in arr[l..r], else

    // return -1

    int binarySearch(int arr[], int l, int r, int x)

    {

        if (r>=l)

        {

            int mid = l + (r - l)/2;

            // If the element is present at the middle itself

            if (arr[mid] == x)

               return mid;

            // If element is smaller than mid, then it can only

            // be present in left subarray

            if (arr[mid] > x)

               return binarySearch(arr, l, mid-1, x);

            // Else the element can only be present in right

            // subarray

            return binarySearch(arr, mid+1, r, x);

        }

        // We reach here when element is not present in array

        return -1;

    }

    public static void main(String args[])

    {

        BinarySearch ob = new BinarySearch();

        int arr[] = {2,3,4,10,40};

        int n = arr.length;

        int x = 10;

        int result = ob.binarySearch(arr,0,n-1,x);

        if (result == -1)

            System.out.println("Element not present");

        else

            System.out.println("Element found at index "+result);

    }

}

Output:

Element is present at index 3

Program: Iterative implementation of Binary Search

class BinarySearch

{

    // Returns index of x if it is present in arr[], else

    // return -1

    int binarySearch(int arr[], int x)

    {

        int l = 0, r = arr.length - 1;

        while (l <= r)

        {

            int m = l + (r-l)/2;

            // Check if x is present at mid

            if (arr[m] == x)

                return m;

            // If x greater, ignore left half

            if (arr[m] < x)

                l = m + 1;

            // If x is smaller, ignore right half

            else

                r = m - 1;

        }

        // if we reach here, then element was not present

        return -1;

    }

    public static void main(String args[])

    {

        BinarySearch ob = new BinarySearch();

        int arr[] = {2, 3, 4, 10, 40};

        int n = arr.length;

        int x = 10;

        int result = ob.binarySearch(arr, x);

        if (result == -1)

            System.out.println("Element not present");

        else

            System.out.println("Element found at index "+result);

    }

}

Output:

Element is present at index 3

Bubble Sort

Bubble sort algorithm is known as the simplest sorting algorithm.

In bubble sort algorithm, array is traversed from first element to last element. Here, current element is compared with the next element. If current element is greater than the next element, it is swapped.

## Algorithm:

We assume list is an array of n elements. We further assume that swap function swaps the values of the given array elements.

begin  BubbleSort(list)

 for all elements of list

 if list[i]  > list[i+1]

         swap(list[i], list[i+1])

 end  if

 end  for

 return list

end  BubbleSort

Program: Bubble sort program in java

public class BubbleSortExample {  

    static void bubbleSort(int[] arr) {  

       int n = arr.length;  

        int temp = 0;  

         for(int i=0; i < n; i++){  

                 for(int j=1; j < (n-i); j++){  

                          if(arr[j-1] > arr[j]){  

                                 //swap elements  

                                 temp = arr[j-1];  

                                 arr[j-1] = arr[j];  

                                 arr[j] = temp;  

                         }  

                 }  

         }  

    }  

    public static void main(String[] args) {  

                int arr[] ={3,60,35,2,45,320,5};  

               System.out.println("Array Before Bubble Sort");  

                for(int i=0; i < arr.length; i++){  

                        System.out.print(arr[i] + " ");  

                }  

                System.out.println();  

                bubbleSort(arr);//sorting array elements using bubble sort  

                System.out.println("Array After Bubble Sort");  

                for(int i=0; i < arr.length; i++){  

                        System.out.print(arr[i] + " ");  

                }  

        }  

}  

Output:

Array Before Bubble Sort

3 60 35 2 45 320 5

Array After Bubble Sort

2 3 5 35 45 60 320

Insertion sort

Insertion sort is a simple sorting algorithm that works the way we sort playing cards in our hands.

Algorithm

Step 1 − If it is the first element, it is already sorted. return 1;

Step 2 − Pick next element

Step 3 − Compare with all elements in the sorted sub-list

Step 4 − Shift all the elements in the sorted sub-list that is greater than the

         value to be sorted

Step 5 − Insert the value

Step 6 − Repeat until list is sorted

Program: Java program for implementation of Insertion Sort

class InsertionSort

{

    /*Function to sort array using insertion sort*/

    void sort(int arr[])

    {

        int n = arr.length;

        for (int i=1; i<n; ++i)

        {

            int key = arr[i];

            int j = i-1;

            /* Move elements of arr[0..i-1], that are

               greater than key, to one position ahead

               of their current position */

while (j>=0 && arr[j] > key)

            {

                arr[j+1] = arr[j];

                j = j-1;

            }

            arr[j+1] = key;

        }

    }

    /* A utility function to print array of size n*/

    static void printArray(int arr[])

    {

        int n = arr.length;

        for (int i=0; i<n; ++i)

            System.out.print(arr[i] + " ");

        System.out.println();

    }

    public static void main(String args[])

    {       

        int arr[] = {12, 11, 13, 5, 6};

        InsertionSort ob = new InsertionSort();       

        ob.sort(arr);

        printArray(arr);

    }

}

Output:

5 6 11 12 13

Mergesort

The Mergesort algorithm can be used to sort a collection of objects. Mergesort is a so called divide and conquer algorithm. Divide and conquer algorithms divide the original data into smaller sets of data to solve the problem.

Algorithm:

Step 1 − if it is only one element in the list it is already sorted, return.

Step 2 − divide the list recursively into two halves until it can no more be divided.

Step 3 − merge the smaller lists into new list in sorted order.

Program: Java program for Merge Sort

class MergeSort

{

    // Merges two subarrays of arr[].

    // First subarray is arr[l..m]

    // Second subarray is arr[m+1..r]

    void merge(int arr[], int l, int m, int r)

    {

        // Find sizes of two subarrays to be merged

        int n1 = m - l + 1;

        int n2 = r - m;

        /* Create temp arrays */

        int L[] = new int [n1];

        int R[] = new int [n2];

        /*Copy data to temp arrays*/

        for (int i=0; i<n1; ++i)

            L[i] = arr[l + i];

        for (int j=0; j<n2; ++j)

            R[j] = arr[m + 1+ j];

        /* Merge the temp arrays */

        // Initial indexes of first and second subarrays

        int i = 0, j = 0;

        // Initial index of merged subarry array

        int k = l;

        while (i < n1 && j < n2)

        {

            if (L[i] <= R[j])

            {

                arr[k] = L[i];

                i++;

            }

            else

            {

                arr[k] = R[j];

                j++;

            }

            k++;

        }

        /* Copy remaining elements of L[] if any */

        while (i < n1)

        {

            arr[k] = L[i];

            i++;

            k++;

        }

        /* Copy remaining elements of L[] if any */

        while (j < n2)

        {

            arr[k] = R[j];

            j++;

            k++;

        }

    }

    // Main function that sorts arr[l..r] using

    // merge()

    void sort(int arr[], int l, int r)

    {

        if (l < r)

        {

            // Find the middle point

            int m = (l+r)/2;

            // Sort first and second halves

            sort(arr, l, m);

            sort(arr , m+1, r);

            // Merge the sorted halves

            merge(arr, l, m, r);

        }

    }

    /* A utility function to print array of size n */

    static void printArray(int arr[])

    {

        int n = arr.length;

        for (int i=0; i<n; ++i)

            System.out.print(arr[i] + " ");

        System.out.println();

    }

    public static void main(String args[])

    {

        int arr[] = {12, 11, 13, 5, 6, 7};

        System.out.println("Given Array");

        printArray(arr);

        MergeSort ob = new MergeSort();

        ob.sort(arr, 0, arr.length-1);

        System.out.println("\nSorted array");

        printArray(arr);

    }

}

Output:

Given array is

12 11 13 5 6 7

Sorted array is

5 6 7 11 12 13

Quicksort

Sort algorithms order the elements of an array according to a predefined order. Quicksort is a divide and conquer algorithm. In a divide and conquer sorting algorithm the original data is separated into two parts "divide" which are individually sorted and "conquered" and then combined

Algorithm:

If the array contains only one element or zero elements than the array is sorted.

If the array contains more than one element than:

*   Select an element from the array. This element is called the "pivot element". For example select the element in the middle of the array.
*   All elements which are smaller then the pivot element are placed in one array and all elements which are larger are placed in another array.
*   Sort both arrays by recursively applying Quicksort to them.
*   Combine the arrays.

Quicksort can be implemented to sort "in-place". This means that the sorting takes place in the array and that no additional array needs to be created.

Program: Java program for implementation of QuickSort

class QuickSort

{

    /* This function takes last element as pivot,

       places the pivot element at its correct

       position in sorted array, and places all

       smaller (smaller than pivot) to left of

       pivot and all greater elements to right

       of pivot */

    int partition(int arr[], int low, int high)

    {

        int pivot = arr[high];

int i = (low-1); // index of smaller element

        for (int j=low; j<=high-1; j++)

        {

            // If current element is smaller than or

            // equal to pivot

            if (arr[j] <= pivot)

            {

                i++;

                // swap arr[i] and arr[j]

                int temp = arr[i];

                arr[i] = arr[j];

                arr[j] = temp;

            }

        }

        // swap arr[i+1] and arr[high] (or pivot)

        int temp = arr[i+1];

        arr[i+1] = arr[high];

        arr[high] = temp;

        return i+1;

    }

    /* The main function that implements QuickSort()

      arr[] --> Array to be sorted,

      low  --> Starting index,

      high  --> Ending index

*/

    void sort(int arr[], int low, int high)

    {

        if (low < high)

        {

            /* pi is partitioning index, arr[pi] is

              now at right place */

            int pi = partition(arr, low, high);

            // Recursively sort elements before

            // partition and after partition

            sort(arr, low, pi-1);

            sort(arr, pi+1, high);

        }

    }

    /* A utility function to print array of size n */

    static void printArray(int arr[])

    {

        int n = arr.length;

        for (int i=0; i<n; ++i)

            System.out.print(arr[i]+" ");

        System.out.println();

    }

    public static void main(String args[])

    {

        int arr[] = {10, 7, 8, 9, 1, 5};

        int n = arr.length;

        QuickSort ob = new QuickSort();

        ob.sort(arr, 0, n-1);

        System.out.println("sorted array");

        printArray(arr);

    }

}

Output:

Sorted array:

1 5 7 8 9 10

Selection sort

Selection sort is a simple sorting algorithm. This sorting algorithm is an in-place comparison-based algorithm in which the list is divided into two parts, the sorted part at the left end and the unsorted part at the right end. Initially, the sorted part is empty and the unsorted part is the entire list.

The smallest element is selected from the unsorted array and swapped with the leftmost element, and that element becomes a part of the sorted array. This process continues moving unsorted array boundary by one element to the right.

This algorithm is not suitable for large data sets as its average and worst case complexities are of Ο(n2), where n is the number of items.

### Algorithm:

Step 1 − Set MIN to location 0

Step 2 − Search the minimum element in the list

Step 3 − Swap with value at location MIN

Step 4 − Increment MIN to point to next element

Step 5 − Repeat until list is sorted

Program: Selection Sort in Java

public class SelectionSortExample {  

    public static void selectionSort(int[] arr){  

        for (int i = 0; i < arr.length - 1; i++)  

        {  

            int index = i;  

            for (int j = i + 1; j < arr.length; j++){  

                if (arr[j] < arr[index]){  

                    index = j;//searching for lowest index  

                }  

            }  

            int smallerNumber = arr[index];   

            arr[index] = arr[i];  

            arr[i] = smallerNumber;  

        }  

    }  

    public static void main(String a[]){  

        int[] arr1 = {9,14,3,2,43,11,58,22};  

        System.out.println("Before Selection Sort");  

        for(int i:arr1){  

            System.out.print(i+" ");  

        }  

        System.out.println();  

        selectionSort(arr1);//sorting array using selection sort  

        System.out.println("After Selection Sort");  

        for(int i:arr1){  

            System.out.print(i+" ");  

        }  

    }  

}  

Output:

Before Selection Sort

9 14 3 2 43 11 58 22

After Selection Sort

2 3 9 11 14 22 43 58

Linked List

A linked list is a sequence of data structures, which are connected together via links.

Linked List is a sequence of links which contains items. Each link contains a connection to another link. Linked list is the second most-used data structure after array. Following are the important terms to understand the concept of Linked List.

*   Link − Each link of a linked list can store a data called an element.
*   Next − Each link of a linked list contains a link to the next link called Next.
*   LinkedList − A Linked List contains the connection link to the first link called First.

## Linked List Representation

Linked list can be visualized as a chain of nodes, where every node points to the next node.

![Linked List](images/00021.jpeg)

As per the above illustration, following are the important points to be considered.

*   Linked List contains a link element called first.
*   Each link carries a data field(s) and a link field called next.
*   Each link is linked with its next link using its next link.
*   Last link carries a link as null to mark the end of the list.

## Types of Linked List:

Following are the various types of linked list.

*   Simple Linked List − Item navigation is forward only.
*   Doubly Linked List − Items can be navigated forward and backward.
*   Circular Linked List − Last item contains link of the first element as next and the first element has a link to the last element as previous.

## Basic Operations:

Following are the basic operations supported by a list.

*   Insertion − Adds an element at the beginning of the list.
*   Deletion − Deletes an element at the beginning of the list.
*   Display − Displays the complete list.
*   Search − Searches an element using the given key.
*   Delete − Deletes an element using the given key.

## Insertion Operation:

Adding a new node in linked list is a more than one step activity. We shall learn this with diagrams here. First, create a node using the same structure and find the location where it has to be inserted.

![Linked List Insertion](images/00022.jpeg)

Imagine that we are inserting a node B (NewNode),

between A (LeftNode) and C (RightNode). Then point B.next to C −

NewNode.next −> RightNode;

It should look like this −

![Linked List Insertion](images/00023.jpeg)

Now, the next node at the left should point to the new node.

LeftNode.next −> NewNode;

![Linked List Insertion](images/00024.jpeg)

This will put the new node in the middle of the two. The new list should look like this −

![Linked List Insertion](images/00025.jpeg)

Similar steps should be taken if the node is being inserted at the beginning of the list. While inserting it at the end, the second last node of the list should point to the new node and the new node will point to NULL.

## Deletion Operation:

Deletion is also a more than one step process. We shall learn with pictorial representation. First, locate the target node to be removed, by using searching algorithms.

![Linked List Deletion](images/00026.jpeg)

The left (previous) node of the target node now should point to the next node of the target node –

LeftNode.next −> TargetNode.next;

![Linked List Deletion](images/00027.jpeg)

This will remove the link that was pointing to the target node. Now, using the following code, we will remove what the target node is pointing at.

TargetNode.next −> NULL;

![Linked List Deletion](images/00028.jpeg)

We need to use the deleted node. We can keep that in memory otherwise we can simply deallocate memory and wipe off the target node completely.

![Linked List Deletion](images/00029.jpeg)

## Reverse Operation:

This operation is a thorough one. We need to make the last node to be pointed by the head node and reverse the whole linked list.

![Linked List Reverse Operation](images/00030.jpeg)

First, we traverse to the end of the list. It should be pointing to NULL. Now, we shall make it point to its previous node −

![Linked List Reverse Operation](images/00031.jpeg)

We have to make sure that the last node is not the lost node. So we'll have some temp node, which looks like the head node pointing to the last node. Now, we shall make all left side nodes point to their previous nodes one by one.

![Linked List Reverse Operation](images/00032.jpeg)

Except the node (first node) pointed by the head node, all nodes should point to their predecessor, making them their new successor. The first node will point to NULL.

![Linked List Reverse Operation](images/00033.jpeg)

We'll make the head node point to the new first node by using the temp node.

![Linked List Reverse Operation](images/00034.jpeg)

The linked list is now reversed.

# Program: Given a linked list which is sorted, how will you insert in sorted way?

Algorithm: 
Let input linked list is sorted in increasing order.

1) If Linked list is empty then make the node as head and return it.

2) If value of the node to be inserted is smaller than value of head node

    then insert the node at start and make it head.

3) In a loop, find the appropriate node after which the input node (let 9) is

    to be inserted. To find the appropriate node start from head, keep moving

    until you reach a node GN (10 in the below diagram) who's value is

    greater than the input node. The node just before GN is the appropriate

    node (7).

4) Insert the node (9) after the appropriate node (7) found in step 3.

Initial Linked List
![SortedLinked List](images/00035.jpeg) 

Linked List after insertion of 9
![UpdatedSortedLinked List](images/00036.jpeg) 

class LinkedList

{

Node head; // head of list

    /* Linked list Node*/

    class Node

    {

        int data;

        Node next;

        Node(int d) {data = d; next = null; }

    }

    /* function to insert a new_node in a list. */

    void sortedInsert(Node new_node)

    {

         Node current;

         /* Special case for head node */

         if (head == null || head.data >= new_node.data)

         {

            new_node.next = head;

            head = new_node;

         }

         else {

            /* Locate the node before point of insertion. */

            current = head;

            while (current.next != null &&

                   current.next.data < new_node.data)

                  current = current.next;

            new_node.next = current.next;

            current.next = new_node;

         }

     }

                  /*Utility functions*/

    /* Function to create a node */

    Node newNode(int data)

    {

       Node x = new Node(data);

       return x;

    }

     /* Function to print linked list */

     void printList()

     {

         Node temp = head;

         while (temp != null)

         {

            System.out.print(temp.data+" ");

            temp = temp.next;

         }

     }

     /* Drier function to test above methods */

     public static void main(String args[])

     {

         LinkedList llist = new LinkedList();

         Node new_node;

         new_node = llist.newNode(5);

         llist.sortedInsert(new_node);

         new_node = llist.newNode(10);

         llist.sortedInsert(new_node);

         new_node = llist.newNode(7);

         llist.sortedInsert(new_node);

         new_node = llist.newNode(3);

         llist.sortedInsert(new_node);

         new_node = llist.newNode(1);

         llist.sortedInsert(new_node);

         new_node = llist.newNode(9);

         llist.sortedInsert(new_node);

         System.out.println("Created Linked List");

         llist.printList();

     }

}

Output:

Created Linked List

1 3 5 7 9 10

# Program: Delete a given node in Linked List under given constraints

Given a Singly Linked List, write a function to delete a given node. Your function must follow following constraints:
1) It must accept pointer to the start node as first parameter and node to be deleted as second parameter i.e., pointer to head node is not global.
2) It should not return pointer to the head node.
3) It should not accept pointer to pointer to head node.

You may assume that the Linked List never becomes empty.

Let the function name be deleteNode(). In a straightforward implementation, the function needs to modify head pointer when the node to be deleted is first node.

class LinkedList {

    static Node head;

    static class Node {

        int data;

        Node next;

       Node(int d) {

            data = d;

            next = null;

        }

    }

    void deleteNode(Node node, Node n) {

        // When node to be deleted is head node

        if (node == n) {

            if (node.next == null) {

                System.out.println("There is only one node. The list "

                                 + "can't be made empty ");

                return;

            }

            /* Copy the data of next node to head */

            node.data = node.next.data;

            // store address of next node

            n = node.next;

            // Remove the link of next node

            node.next = node.next.next;

            // free memory

            System.gc();

             return;

        }

         // When not first node, follow the normal deletion process

        // find the previous node

        Node prev = node;

        while (prev.next != null && prev.next != n) {

            prev = prev.next;

        }

        // Check if node really exists in Linked List

        if (prev.next == null) {

            System.out.println("Given node is not present in Linked List");

            return;

        }

        // Remove node from Linked List

        prev.next = prev.next.next;

        // Free memory

        System.gc();

        return;

    }

    /* Utility function to print a linked list */

    void printList(Node head) {

        while (head != null) {

            System.out.print(head.data + " ");

            head = head.next;

        }

        System.out.println("");

    }

    public static void main(String[] args) {

        LinkedList list = new LinkedList();

        list.head = new Node(12);

        list.head.next = new Node(15);

        list.head.next.next = new Node(10);

        list.head.next.next.next = new Node(11);

        list.head.next.next.next.next = new Node(5);

        list.head.next.next.next.next.next = new Node(6);

        list.head.next.next.next.next.next.next = new Node(2);

        list.head.next.next.next.next.next.next.next = new Node(3);

        System.out.println("Given Linked List :");

        list.printList(head);

        System.out.println("");     

        // Let us delete the node with value 10

        System.out.println("Deleting node :" + head.next.next.data);

        list.deleteNode(head, head.next.next);

        System.out.println("Modified Linked list :");

        list.printList(head);

        System.out.println("");

        // Lets delete the first node

        System.out.println("Deleting first Node");

        list.deleteNode(head, head);

        System.out.println("Modified Linked List");

        list.printList(head);

    }

}

Output:

Given Linked List: 12 15 10 11 5 6 2 3

Deleting node 10:

Modified Linked List: 12 15 11 5 6 2 3

Deleting first node

Modified Linked List: 15 11 5 6 2 3

Chapter 4 | Networking

What is network programming?

The term network programming refers to writing programs that execute across multiple devices (computers), in which the devices are all connected to each other using a network.

The java.net package of the J2SE APIs contains a collection of classes and interfaces that provide the low-level communication details, allowing you to write programs that focus on solving the problem at hand.

The java.net package provides support for the two common network protocols –

1.  TCP − TCP stands for Transmission Control Protocol, which allows for reliable communication between two applications. TCP is typically used over the Internet Protocol, which is referred to as TCP/IP.

2.  UDP − UDP stands for User Datagram Protocol, a connection-less protocol that allows for packets of data to be transmitted between applications.

This chapter gives a good understanding on the following two subjects−

1.  Socket Programming − This is the most widely used concept in Networking and it has been explained in very detail.
2.  URL Processing − URL stands for Uniform Resource Locator and represents a resource on the World Wide Web, such as a Web page or FTP directory

Socket Programming:

Sockets provide the communication mechanism between two computers using TCP. A client program creates a socket on its end of the communication and attempts to connect that socket to a server.

When the connection is made, the server creates a socket object on its end of the communication. The client and the server can now communicate by writing to and reading from the socket.

The java.net.Socket class represents a socket, and the java.net.ServerSocket class provides a mechanism for the server program to listen for clients and establish connections with them.

The following steps occur when establishing a TCP connection between two computers using sockets −

The server instantiates a ServerSocket object, denoting which port number communication is to occur on.

The server invokes the accept() method of the ServerSocket class. This method waits until a client connects to the server on the given port.

After the server is waiting, a client instantiates a Socket object, specifying the server name and the port number to connect to.

The constructor of the Socket class attempts to connect the client to the specified server and the port number. If communication is established, the client now has a Socket object capable of communicating with the server.

On the server side, the accept() method returns a reference to a new socket on the server that is connected to the client's socket.

After the connections are established, communication can occur using I/O streams. Each socket has both an OutputStream and an InputStream. The client's OutputStream is connected to the server's InputStream, and the client's InputStream is connected to the server's OutputStream.

TCP is a two-way communication protocol, hence data can be sent across both streams at the same time. Following are the useful classes providing complete set of methods to implement sockets.

ServerSocket Class Methods:

The java.net.ServerSocket class is used by server applications to obtain a port and listen for client requests.

The ServerSocket class has four constructors –

| Sr.No. | Method & Description |
| 1 | public ServerSocket(int port) throws IOExceptionAttempts to create a server socket bound to the specified port. An exception occurs if the port is already bound by another application. |
| 2 | public ServerSocket(int port, int backlog) throws IOExceptionSimilar to the previous constructor, the backlog parameter specifies how many incoming clients to store in a wait queue. |
| 3 | public ServerSocket(int port, int backlog, InetAddress address) throws IOExceptionSimilar to the previous constructor, the InetAddress parameter specifies the local IP address to bind to. The InetAddress is used for servers that may have multiple IP addresses, allowing the server to specify which of its IP addresses to accept client requests on. |
| 4 | public ServerSocket() throws IOExceptionCreates an unbound server socket. When using this constructor, use the bind() method when you are ready to bind the server socket. |

If the ServerSocket constructor does not throw an exception, it means that your application has successfully bound to the specified port and is ready for client requests.

Following are some of the common methods of the ServerSocket class −

| Sr.No. | Method & Description |
| 1 | public int getLocalPort()Returns the port that the server socket is listening on. This method is useful if you passed in 0 as the port number in a constructor and let the server find a port for you. |
| 2 | public Socket accept() throws IOExceptionWaits for an incoming client. This method blocks until either a client connects to the server on the specified port or the socket times out, assuming that the time-out value has been set using the setSoTimeout() method. Otherwise, this method blocks indefinitely. |
| 3 | public void setSoTimeout(int timeout)Sets the time-out value for how long the server socket waits for a client during the accept(). |
| 4 | public void bind(SocketAddress host, int backlog)Binds the socket to the specified server and port in the SocketAddress object. Use this method if you have instantiated the ServerSocket using the no-argument constructor. |

When the ServerSocket invokes accept(), the method does not return until a client connects. After a client does connect, the ServerSocket creates a new Socket on an unspecified port and returns a reference to this new Socket. A TCP connection now exists between the client and the server, and communication can begin.

Socket Class Methods:

The java.net.Socket class represents the socket that both the client and the server use to communicate with each other. The client obtains a Socket object by instantiating one, whereas the server obtains a Socket object from the return value of the accept() method.

The Socket class has five constructors that a client uses to connect to a server –

| Sr.No. | Method & Description |
| 1 | public Socket(String host, int port) throws UnknownHostException, IOException.This method attempts to connect to the specified server at the specified port. If this constructor does not throw an exception, the connection is successful and the client is connected to the server. |
| 2 | public Socket(InetAddress host, int port) throws IOExceptionThis method is identical to the previous constructor, except that the host is denoted by an InetAddress object. |
| 3 | public Socket(String host, int port, InetAddress localAddress, int localPort) throws IOException.Connects to the specified host and port, creating a socket on the local host at the specified address and port. |
| 4 | public Socket(InetAddress host, int port, InetAddress localAddress, int localPort) throws IOException.This method is identical to the previous constructor, except that the host is denoted by an InetAddress object instead of a String. |
| 5 | public Socket()Creates an unconnected socket. Use the connect() method to connect this socket to a server. |

When the Socket constructor returns, it does not simply instantiate a Socket object but it actually attempts to connect to the specified server and port.

Some methods of interest in the Socket class are listed here. Notice that both the client and the server have a Socket object, so these methods can be invoked by both the client and the server.

| Sr.No. | Method & Description |
| 1 | public void connect(SocketAddress host, int timeout) throws IOExceptionThis method connects the socket to the specified host. This method is needed only when you instantiate the Socket using the no-argument constructor. |
| 2 | public InetAddress getInetAddress()This method returns the address of the other computer that this socket is connected to. |
| 3 | public int getPort()Returns the port the socket is bound to on the remote machine. |
| 4 | public int getLocalPort()Returns the port the socket is bound to on the local machine. |
| 5 | public SocketAddress getRemoteSocketAddress()Returns the address of the remote socket. |
| 6 | public InputStream getInputStream() throws IOExceptionReturns the input stream of the socket. The input stream is connected to the output stream of the remote socket. |
| 7 | public OutputStream getOutputStream() throws IOExceptionReturns the output stream of the socket. The output stream is connected to the input stream of the remote socket. |
| 8 | public void close() throws IOExceptionCloses the socket, which makes this Socket object no longer capable of connecting again to any server. |

InetAddress Class Methods:

This class represents an Internet Protocol (IP) address. Here are following usefull methods which you would need while doing socket programming –

| Sr.No. | Method & Description |
| 1 | static InetAddress getByAddress(byte[] addr)Returns an InetAddress object given the raw IP address. |
| 2 | static InetAddress getByAddress(String host, byte[] addr)Creates an InetAddress based on the provided host name and IP address. |
| 3 | static InetAddress getByName(String host)Determines the IP address of a host, given the host's name. |
| 4 | String getHostAddress()Returns the IP address string in textual presentation. |
| 5 | String getHostName()Gets the host name for this IP address. |
| 6 | static InetAddress InetAddress getLocalHost()Returns the local host. |
| 7 | String toString()Converts this IP address to a String. |

Socket Client Example

The following GreetingClient is a client program that connects to a server by using a socket and sends a greeting, and then waits for a response.

Example

// File Name GreetingClient.java

import java.net.*;

import java.io.*;

public  class  GreetingClient  {

 public  static  void main(String  [] args)  {

 String serverName = args[0];

 int port =  Integer.parseInt(args[1]);

 try  {

 System.out.println("Connecting to "  + serverName +  " on port "  + port);

 Socket client =  new  Socket(serverName, port);

 System.out.println("Just connected to "  + client.getRemoteSocketAddress());

 OutputStream outToServer = client.getOutputStream();

 DataOutputStream  out  =  new  DataOutputStream(outToServer);

 out.writeUTF("Hello from "  + client.getLocalSocketAddress());

 InputStream inFromServer = client.getInputStream();

 DataInputStream  in  =  new  DataInputStream(inFromServer);

 System.out.println("Server says "  +  in.readUTF());

         client.close();

 }catch(IOException e)  {

         e.printStackTrace();

 }

 }

}

Socket Server Example

The following GreetingServer program is an example of a server application that uses the Socket class to listen for clients on a port number specified by a command-line argument −

Example:

// File Name GreetingServer.java

import java.net.*;

import java.io.*;

public  class  GreetingServer  extends  Thread  {

 private  ServerSocket serverSocket;

 public  GreetingServer(int port)  throws  IOException  {

serverSocket =  new  ServerSocket(port);

      serverSocket.setSoTimeout(10000);

 }

 public  void run()  {

 while(true)  {

 try  {

 System.out.println("Waiting for client on port "  +

               serverSocket.getLocalPort()  +  "...");

 Socket server = serverSocket.accept();

 System.out.println("Just connected to "  + server.getRemoteSocketAddress());

 DataInputStream  in  =  new  DataInputStream(server.getInputStream());

 System.out.println(in.readUTF());

 DataOutputStream  out  =  new  DataOutputStream(server.getOutputStream());

 out.writeUTF("Thank you for connecting to "  + server.getLocalSocketAddress()

 +  "\nGoodbye!");

            server.close();

 }catch(SocketTimeoutException s)  {

 System.out.println("Socket timed out!");

 break;

 }catch(IOException e)  {

            e.printStackTrace();

 break;

 }

 }

 }

 public  static  void main(String  [] args)  {

 int port =  Integer.parseInt(args[0]);

 try  {

 Thread t =  new  GreetingServer(port);

         t.start();

 }catch(IOException e)  {

         e.printStackTrace();

 }

 }

}

Compile the client and the server and then start the server as follows −

$ java GreetingServer 6066

Waiting for client on port 6066...

Check the client program as follows −

Output:

$ java GreetingClient localhost 6066

Connecting to localhost on port 6066

Just connected to localhost/127.0.0.1:6066

Server says Thank you for connecting to /127.0.0.1:6066

Goodbye!

# URL Processing:

URL stands for Uniform Resource Locator and represents a resource on the World Wide Web, such as a Web page or FTP directory.

This section shows you how to write Java programs that communicate with a URL. A URL can be broken down into parts, as follows –

protocol://host:port/path?query#ref

Examples of protocols include HTTP, HTTPS, FTP, and File. The path is also referred to as the filename, and the host is also called the authority.

The following is a URL to a web page whose protocol is HTTP –

[https://www.amrood.com/index.htm?language=en#j2se](https://www.amrood.com/index.htm?language=en#j2se)

Notice that this URL does not specify a port, in which case the default port for the protocol is used. With HTTP, the default port is 80.

URL Class Methods

The java.net.URL class represents a URL and has a complete set of methods to manipulate URL in Java.

The URL class has several constructors for creating URLs, including the following –

| Sr.No. | Method & Description |
| 1 | public URL(String protocol, String host, int port, String file) throws MalformedURLExceptionCreates a URL by putting together the given parts. |
| 2 | public URL(String protocol, String host, String file) throws MalformedURLExceptionIdentical to the previous constructor, except that the default port for the given protocol is used. |
| 3 | public URL(String url) throws MalformedURLExceptionCreates a URL from the given String. |
| 4 | public URL(URL context, String url) throws MalformedURLExceptionCreates a URL by parsing together the URL and String arguments. |

The URL class contains many methods for accessing the various parts of the URL being represented. Some of the methods in the URL class include the following –

| Sr.No. | Method & Description |
| 1 | public String getPath()Returns the path of the URL. |
| 2 | public String getQuery()Returns the query part of the URL. |
| 3 | public String getAuthority()Returns the authority of the URL. |
| 4 | public int getPort()Returns the port of the URL. |
| 5 | public int getDefaultPort()Returns the default port for the protocol of the URL. |
| 6 | public String getProtocol()Returns the protocol of the URL. |
| 7 | public String getHost()Returns the host of the URL. |
| 8 | public String getHost()Returns the host of the URL. |
| 9 | public String getFile()Returns the filename of the URL. |
| 10 | public String getRef()Returns the reference part of the URL. |
| 11 | public URLConnection openConnection() throws IOExceptionOpens a connection to the URL, allowing a client to communicate with the resource. |

Example:

The following URLDemo program demonstrates the various parts of a URL. A URL is entered on the command line, and the URLDemo program outputs each part of the given URL.

// File Name : URLDemo.java

import java.net.*;

import java.io.*;

public  class  URLDemo  {

 public  static  void main(String  [] args)  {

 try  {

URL url =  new URL("https://www.amrood.com/index.htm?language=en#j2se");

 System.out.println("URL is "  + url.toString());

 System.out.println("protocol is "  + url.getProtocol());

 System.out.println("authority is "  + url.getAuthority());

 System.out.println("file name is "  + url.getFile());

 System.out.println("host is "  + url.getHost());

 System.out.println("path is "  + url.getPath());

 System.out.println("port is "  + url.getPort());

 System.out.println("default port is "  + url.getDefaultPort());

 System.out.println("query is "  + url.getQuery());

 System.out.println("ref is "  + url.getRef());

 }catch(IOException e)  {

         e.printStackTrace();

 }

 }

}

Output

URL is https://www.amrood.com/index.htm?language=en#j2se

protocol is http

authority is www.amrood.com

file name is /index.htm?language=en

host is www.amrood.com

path is /index.htm

port is -1

default port is 80

query is language=en

ref is j2se

URLConnections Class Methods:

The openConnection() method returns a java.net.URLConnection, an abstract class whose subclasses represent the various types of URL connections.

For example −

If you connect to a URL whose protocol is HTTP, the openConnection() method returns an HttpURLConnection object.

If you connect to a URL that represents a JAR file, the openConnection() method returns a JarURLConnection object, etc.

The URLConnection class has many methods for setting or determining information about the connection, including the following –

| Sr.No. | Method & Description |
| 1 | Object getContent()Retrieves the contents of this URL connection. |
| 2 | Object getContent(Class[] classes)Retrieves the contents of this URL connection. |
| 3 | String getContentEncoding()Returns the value of the content-encoding header field. |
| 4 | int getContentLength()Returns the value of the content-length header field. |
| 5 | String getContentType()Returns the value of the content-type header field. |
| 6 | int getLastModified()Returns the value of the last-modified header field. |
| 7 | long getExpiration()Returns the value of the expired header field. |
| 8 | long getIfModifiedSince()Returns the value of this object's ifModifiedSince field. |
| 9 | public void setDoInput(boolean input)Passes in true to denote that the connection will be used for input. The default value is true because clients typically read from a URLConnection. |
| 10 | public void setDoOutput(boolean output)Passes in true to denote that the connection will be used for output. The default value is false because many types of URLs do not support being written to. |
| 11 | public InputStream getInputStream() throws IOExceptionReturns the input stream of the URL connection for reading from the resource. |
| 12 | public OutputStream getOutputStream() throws IOExceptionReturns the output stream of the URL connection for writing to the resource. |
| 13 | public URL getURL()Returns the URL that this URLConnection object is connected to. |

Example:

The following URLConnectionDemo program connects to a URL entered from the command line.

If the URL represents an HTTP resource, the connection is cast to HttpURLConnection, and the data in the resource is read one line at a time.

// File Name : URLConnDemo.java

import java.net.*;

import java.io.*;

public  class  URLConnDemo  {

 public  static  void main(String  [] args)  {

 try  {

URL url =  new URL("https://www.amrood.com");

 URLConnection urlConnection = url.openConnection();

 HttpURLConnection connection =  null;

 if(urlConnection instanceof  HttpURLConnection)  {

connection =  (HttpURLConnection) urlConnection;

 }else  {

 System.out.println("Please enter an HTTP URL.");

 return;

 }

 BufferedReader  in  =  new  BufferedReader(

 new  InputStreamReader(connection.getInputStream()));

 String urlString =  "";

 String current;

 while((current =  in.readLine())  !=  null)  {

urlString += current;

 }

 System.out.println(urlString);

 }catch(IOException e)  {

         e.printStackTrace();

 }

 }

}

Output:

$ java URLConnDemo

.....a complete HTML content of home page of amrood.com.....

5 SKILLS SELF-TAUGHT PROGRAMMERS COMMONLY LACK

1\. ALGORITHMS

* * *

This is classic computer science right here. Programming without knowledge of algorithms is like carpentry with just one kind of saw: you can get the job done, but it’s going to take a lot longer.

You can look at an [algorithm](https://goo.gl/E2ENP8) as “discipline”. When you learn to write them, what you’re doing is solving a problem with discipline; using structure, patterns, and logical steps.

When you don’t know how to discipline your mind, you don’t know how to write algorithms.

Not only can you not write algorithms unless you’ve studied them, you don’t know how many algorithms others have written, too.

I spent four days trying to figure out how to do a permutation. I was so proud of myself when I figured it out. Right up until I discovered that B.R. Heaps had figured it out in 1963.

2\. DESIGN PATTERNS

* * *

This comes with education and/or experience. There’s more than one way to structure your code, and there’s a right time and a wrong time for each. You either need to make mistakes along the way and learn when to use each pattern, or learn from someone else who’s already made the mistake (a teacher).

3\. PROGRAMMING PARADIGMS

* * *

 Object-Oriented Programming  is not The Way. Neither is  Functional Programming. Nor  Reactive  [ Programming.  It is  A Way](https://en.wikipedia.org/wiki/Reactive_programming).

There are different ways to program, and they each have a purpose. Not only that, some languages are naturally better-suited for one paradigm or another.

“If all you have is a hammer, everything looks like a nail.”

Take that into self-taught programming and you’ll find yourself hammering in nails, screws, staples, and thumb tacks.

I remember a self-taught .NET programmer actually telling me once, “well, it’s not programming unless it’s object-oriented. And that’s why I don’t consider JavaScript a programming language.” That’s a very, very flawed train of thought.

4\. DATA STRUCTURES

* * *

Granted, your language can give you a basic idea of what the different data structures are. But again, that’s a basic idea.

Self -taught programmers can have a tendency to only stick to data structures that work within their

Favorite language. Just because it’s not a primitive, or even a common structure in your language, that doesn’t mean it can’t exist. Of course, that also means that maybe it shouldn’t exist, either.

The world is very small if it all can fit inside of an array.

5\. TESTING

* * *

Maybe it’s just me, but there’s a lot of ways to test your code before pushing it to an environment. Learn how to do unit testing.

More importantly, learn test-driven development.

There’s a difference between testing your code, and writing testable code.

SELF-TAUGHT PROGRAMMERS I HAVE INTERVIEWED OFTEN LACKED KNOWLEDGE IN THESE AREAS:

* * *

*   FORMAL VOCABULARY. You have to know the correct names of [data structures](https://goo.gl/E2ENP8) and other things by heart to by able to have an effective conversation related to a project in software development.

*   TESTING. Most of the autodidacts lack knowledge or generally do not understand the importance of the testing process.

*   PROGRAM PARADIGMS (and corresponding language). “If you only have a hammer, every problem looks like a nail”. I’ve had many of these hammer-types. They often just do not understand why not every problem can be solved the same way/with the same methodology.

*   MACHINE RELATED MATHEMATICAL PROBLEMS. They lack numerical mathematics skills and do not understand why floating points arithmetic can fail you if you don’t watch out

WHAT ARE THE MOST IMPORTANT DATA STRUCTURE AND ALGORITHMS TO PREPARE FOR AN INTERVIEW?

Did you know that the top 10 [data structures](https://goo.gl/E2ENP8) account for 99% of all data structure use in the real world? Probably not, because I just made those numbers up — but they're in the right ballpark. Yes, on occasion we ask a problem whose optimal solution requires a [Bloom filter](http://en.wikipedia.org/wiki/Bloom_filter) or [suffix tree](http://en.wikipedia.org/wiki/Suffix_tree), but even those problems tend to have a near-optimal solution that uses a much more mundane data structure. The data structures that are going to show up most frequently are:

*   Array
*   Stack / Queue
*   Hashset / Hashmap / Hashtable / Dictionary
*   Tree / binary tree
*   Heap
*   Graph

You should know these data structures inside and out. What are the insertion/deletion/lookup characteristics? (O(log n) for a balanced binary tree, for example.) What are the common caveats? (Hashing is tricky, and usually takes O(k) time when k is the size of the object being hashed.)

What algorithms tend to go along with each data structure? ([Dijkstra's](https://secure.wikimedia.org/wikipedia/en/wiki/Dijkstra%27s_algorithm) for a graph.) But when you understand these data structures, sometimes the solution to a problem will pop into your mind as soon as you even think about using the right one.

Stick to basics. I would classify the following data structures as **must know**

* * *

1.  Linked List - Single and Doubly

2.  Stack

3.  Queues

4.  Binary Search Trees or general Binary Tree

5.  Heaps

6.  Basic Graph Traversal and Shortest Path

7.  Hashing

Following data structures may be asked. I would say that their     probability of being asked is between 50 to 75% -

* * *

1.  Tries

2.  Advance Graphs like flow and min-cut etc.

3.  Bit Manipulation

You will probably crack interviews with sufficient knowledge of above.

Following have very low probability of being asked (< 25%):

* * *

1.  Segment Trees / Binary Indexed Trees

2.  AVL Trees

3.  B+ Trees

Other hard data structures are absolutely unnecessary.

Following Algorithms / Tricks / Topics may also be important:

* * *

1.  Memory Management

2.  Basic Co-ordinate geometry - Manhattan Distance, Closest Point Pair

3.  Divide and Conquer

4.  Greedy

5.  Dynamic Programming - Extremely important

6.  Probability and basic Number Theory

7.  Sorting and Searching

Following topics is important for Knowledge / Experience based questions:

* * *

1.  OS - Threads, Processes and Locks using Mutex, Semaphores
2.  Scalability Issues, RPCs, Rate limiter, etc.
3.  OOP Concepts
4.  Databases - SQL, NoSQL, Writing simple Queries, Transactions, ACID
5.  Linux Commands - sed, grep, ps, etc.

9 WAYS TO BECOME A GREAT PROGRAMMER!

1.PRACTICE

* * *

Asides from following tutorials, you should work on your own projects.

"The most fundamental thing is that you actually go and code. I’ve heard it recommended that by the time you finish college, you should have written 100,000 lines at minimum."

— Andrei Thorp from Evernote.

But how do I get start, you may ask.

"I always tell people to find something they’re doing more than once a week and to try to automate it. Ignore if anyone else has solved the problem before, and just make a tool/utility for yourself that fixes a common issue in your life."

— Kasra Rahjerdi, Mobile Lead at Stack Overflow.

"Like any other skill, it takes practice – deliberate practice, stepping outside of your comfort zone and learning the nuance and subtleties – that set apart great from good.”

— Derick Bailey, the creator of WatchMeCode.net.

Derick is a top 0.42% StackOverflow user, and has also contributed to open source frameworks such as has MarionetteJS and BackboneJS.

It’s OK to fail. Coding is all about failing and fixing things, and about learning how to do things better. If you don’t build things and work on areas that you know you are weak on, you’ll never get better.

If you ever need to receive advice on how to improve and what you’re not doing so well on, feel free to ask an experienced developer to help your get straightened up by either reviewing your code or walking you through concepts you are having trouble understanding.

2\. BE PETEINT

* * *

No-brainer here, but it’s easy to get frustrated by your lack of progress and forget that you’re not alone.

"Becoming a good programmer takes a long, long time and a lot of tedious evenings. Before you can write good code, you have to write hundreds of thousands of lines."

— Mike Arpaia, a former Etsy dev who now builds information security software for Facebook.

Mike stresses that beginners should give up on the assumption that one can become an excellent developer quickly.

But… what if you’re not even past the tutorial stages yet? What if you’re still banging your head against the wall and wondering perhaps you’re just not cut out for programming? Before you leap to conclusions,

know that everyone has a different learning style. Author of the Ruby on Rails Tutorial, Michael Hartl, points out that beginners should try lots of different resources (books, videos, etc.) to see what ‘clicks’.

In fact, Craig Coffman, the CTO of [ Reserv](https://reserve.com/)e, has personally learned through a lot of trial-and-error and by picking projects that were personal and interesting. However, since all the interesting challenges are big ones, he suggests beginners to start with biting off reasonably-sized pieces.

That way, when you lose interest or get stuck, you still have a feeling of progress and accomplishment.

3\. STAY INTERESTED

* * *

If you’re bored by the project you’re working on, you should probably reconsider any lofty goals of learning to code. Or, maybe you’re just working on the wrong project or learning through the wrong resource. Always keep yourself motivated by working on personal projects that excites you.

Coraline Ada Ehmke, founder of LGBTech and contributor to high-profile open source projects such as [ Rails](http://rubyonrails.org/)  and  [ RSpe](http://rspec.info/)c,  started coding at a young age out of interest. However, her first class in college as a  Computer Science major made her doubt her passion.

I remember our semester-long project was to write software for an ATM. I was so bored and not challenged, I decided that if that’s what life as an engineer was like, I didn’t want any part of it, so I dropped out soon after.

However, she continued to work on projects she found interesting. By 1993 she was online and building web sites, and has been developing web apps ever since.

4\. LOVE THE ERROR

* * *

As a beginner you’ll likely be mired in bugs. If you feel intimidated by all the red, you’re not alone. Ross Chapman, a UX Engineer who coded for [ Zendesk](https://www.zendesk.com/)  and now working at [ ScienceExchang](https://www.scienceexchange.com/)e, admits to being a scared developer when he first started out.

I didn’t have the patience because I wasn’t ready to love the challenge of fixing things. But that’s pretty much where all my really bad habits come from.

With that said, Ross urges beginners to embrace errors as crucial learning moments. Since you’ll be debugging for life, you should get used to errors and learn to recognize the error messages.

"Being able to quickly parse and understand error messages will save you a lot of time and get you a long way. The fact you’ve tried will be very much appreciated by the person you’re asking for help."

— Jack Franklin, author of “Beginning jQuery”

Jack also recommends beginners to make an attempt at fixing problems on their own at first. When

hitting a wall when debugging, Lee Byron, co-contributor to React, personally attempts to understand what’s going on by making ample usage of the debugger tools.

Once I understand exactly what is happening – step by step, then I can compare that to what I expected to happen and isolate the surprising parts and see where my assumptions were wrong or how some code led to the surprising situation.

Errors aren’t limited to bugs, however. Sometimes, you make bad decisions such as using the wrong data structure. According to Mike, getting burned by those bad decisions will eventually help you learn when it’s reasonable to use certain design patterns

5\. UNDSERSTAND HOW THINGS WORK

* * *

"No matter what level you’re at I’ll say this: never ever write a line of code without knowing why it works, to the metal. Like, be obsessively curious. Be the Indiana Jones of source. Curiosity is one constant among engineers. I don’t think you could make it in this biz without looking into the monitor with wonder. Both childlike, and ruthlessly academic."

— Ross Chapman

Suffice to say, interest is not enough. You have to strive to understand how things work if you’re aiming to become a professional developer of some decency.

"You can start out understanding the tools you use by sifting through StackOverflow questions. I’ve learned a thing or two from them. [The top AngularJS questions are] really interesting to read through as Angular is such a big framework."

— Todd Motto, an AngularJS conference speaker and Developer Expert at Google

Rohan Singh, a senior infrastructure engineer at Spotify, stresses the importance of working towards understanding the layer one level of the stack beneath what you’re working on right now. “Everything we do as software engineers involves working at some level of abstraction,” Rohan says. In other words, if you use some sort of database, you can take away the internals of the database and expect it to “just work”.

Furthermore, to really understand how things work, you should be able to explain why certain  technical choices are better than others, and be able to troubleshoot problems when things don’t work the way the do. Rohan achieves this in practice by trying, a little bit at a time, to learn about and  understand the fundamentals of whatever platform or system he uses — whether that’s Python or Go or the Linux operating system. According to him, this eventually helps you generate a mental of model of how things work under the covers, and broadens your base of understanding.

Ultimately, you’ll grow as engineer, and as a bonus you’d be able to debug more efficiently by learning how to do more “lean back” debugging as opposed to “lean in” debugging. In other words, you’d lean back and think hard about how things work under the covers to figure out what the problem might be. “This can be a lot faster and involve a lot less flailing than ‘lean in’ debugging with an interactive debugger or other tools,” Rohan says.

In fact, Andrei Thorp from Evernote thinks everyone should learn basic C early on.

Because it’s minimal and doesn’t do much for you, it forces you to understand how computers really work on a lower level. For example, C makes you manage the memory you use yourself – which means that later, when you use something like Python, you actually understand what Python is doing for you. Then, when you see some strange bug, you have this toolkit in your mind to understand what the problem could be.

6\. KEEP LEARNING NEW THINGS

* * *

Nothing will kill your career/craft trajectory more than working at some shitty mundane programming job. Go somewhere where you are encouraged/forced to constantly learn new tricks,

Says Jonathan Henson, who currently works at Amazon Web Services. Jonathan also tries to learn a new programming language, paradigm, or stack every year. He then puts himself on projects where he would have the opportunity to apply those skills.

“I think the most important skill to learn is meta-learning,” says Kasra. “That’s what separates engineers and programmers to me. There’s something to be said about spending 12 weeks at a course learning one framework really well, but I really respect (and like to hire) devs that are able to learn whatever they need, on the spot, to do a task.”

So, what’s the best way to learn new skills?

Reading about what you want to do is a start. Steve Klabnik, who’s a Rust core team member and ranked #37 on the all-time Rails contributors list, seeks out any established research on the topic and also tries to figure out how people who are good at the thing he wants to do achieve their results.

The most important thing is to just do it.

1\. Try to do the thing, probably do it poorly.

2\. Figure out where I’m going wrong, and what i need to improve

3\. Work on what I’ve identified.

4\. Repeat.”

CTO of Bellhops, Adam Haney, says his favorite trick to learning new languages is to reimplement a previous project using the paradigms of that new language. For example, he would take something he wrote as object oriented code in C++ and then reimplement it in a functional language.

I feel like this kind practice has prepared me to evaluate new technologies because I understand the underlying Computer Science principles even if I don’t know the intricate details of the language or framework.

If you struggle with memorization, Andrei recommends building a memory palace. The general idea is that you use your brain’s powerful visual memory, and map that to more technical data, like numbers. He also strongly believe in techniques like The Seinfeld Calendar, which is based on Jerry Seinfeld’s idea that you don’t need to work hard every day — you only need to progress a little bit every day. “So with his calendar, you just check off whether you worked on the project today or not,” Andrei says. “There are some nice apps that will help you with this.

On Android, I use HabitBull. As your streak gets longer, you feel more motivated to keep it running

7\. LEARN HOW TO WORK WITH OTHERS

* * *

Another way you can learn new things is to work on projects with other people.

“The legend of the lone coder is a myth,” Adam says. “Almost all substantial projects require teamwork.” This means you’ll need to learn the skills of breaking a problem down into multiple parts, build good interfaces between parts of the codebase, and collaborate on architecture.

“Working with a group of like-minded engineers who challenge you will definitely put you on the fast-track,” Craig says. “Working in isolation makes it hard to catch yourself making silly choices and to learn new things.”

Everyone makes mistakes – that’s just how programming is. Beginners should strive to hang around great engineers and receive feedback. “Don’t be sensitive about your mistakes,” Jonathan stresses. “That’s how you improve. Admit your mistakes and learn from them.”

Getting your code reviewed will also force you into thinking about why you did something and understand code better. “My favorite engineers to work with are the ones who don’t let you off the hook about the code you write,” says Ross. “I remember when I first was challenged, and it freaked the shit out of me. But that night I went home and studied till I knew I could at least attempt a confident explanation of how to pass this around closures.”

So, where do you find mentors or peers who can pair up with you and help you out?

According to Jack, local meetups often have sessions where free coaching is offered to anyone who would like it. Other free resources include Twitter groups, Slack groups, and iRC channels.

8.DON’T JUST CODE – BUILD SOLUTIONS

* * *

"A lot of programming isn’t about code; it’s about understanding other disciplines or standards.

You can’t solve someone’s problem with code if you don’t understand their problem. Working  on projects exposed me to the way that small businesses, marketers, brokers and other professionals approach the world. When you understand how they currently solve problems, you can work with them to come up with new and better solutions."

—Adam Haney, CTO of Bellhops

One thing Ross wishes he had done earlier in his career was to better appreciate the discipline and history of Software Engineering itself.

These days it’s easy to dive into the vocation and only focus on the “coding.” Especially as browser coders or web app coders in a booming market working with huge dynamic programming languages (Ruby, JavaScript) and vastly quirky “computer” languages and formats (HTML, CSS), we might be tempted to spend all our time racing to master the myriad tools, frameworks and APIs so we can crush interviews or level up at the job. But building a product on a team is always a social exercise, and a particular one at that with a unique set of challenges that are mostly non-technical. Like, turns out the hardest thing in software engineering is deciding what to build, not how; though maybe this is less true in as the JavaScript mycelium rhizomes dramatically.

Ross said it took him a while to understand that most of software engineering happens in your head first. “Coding will likely become the easy part soon. But a dope engineer can draw a solution with boxes, circles, and lines—and I know that’s a learned skill because I’ve been doing it more and it I’m getting better at it.” The realization that coding was much more “chin in hand and white boarding” was actually so resonant for him, he wrote a blog post about it.

“Remember that this is about human beings and our lives, not just about the technology that you’re coding with,” says Derick. “Learn how humans think, interact and deal with each other. Then represent what you’ve learned in your software architecture and design.

9\. DON’T RE-INVENT THE WHEEL

* * *

Finally, no matter how good you get, your code will never be 100% original, as many problems have been solved in your language of choice already. “Absolutely ain’t no shame in keeping the wheel as is,” Ross assures. “However, when it’s time to commit, you better be damn sure you can defend that code to your team with Dwayne Johnson-like charm and confidence.”

“Don’t re-invent the wheel just because you don’t understand an abstraction,” Mike reminds us.

However, this isn’t to say there is absolutely no value to re-inventing the wheel. Matthew Zeiler, CEO of Clarifai, encourages people to build things that already have existing solutions if that’s what interests them. Building a tool from scratch will help you learn more about software engineering, system design, scalability, and more.

Conclusion

* * *

Frustrations abound when learning how to develop apps or projects, but hopefully the tips above made you feel more confident in your quest to become a developer.

4 secrets of great programmers!

#1.REGARDING CAREER

* * *

*   Write code that can be read, understood, and manipulated by others. This allows you to hand-off and take on new challenges.

*   If you horde your knowledge, you'll be the only care taker of it --- or in an engineering/business minded organization, a risk.

*   Stop taking pride in code or hackatons survived, means nothing in a permanent team. Execution and collaboration will serve you greater.

#2.REGARDING SOLUTIONS AND CODING

* * *

*   If you can't explain it to a non-programmer, you might be over-complicating or over-optimizing.

*   If you can't draw a architecture diagram, you also might be over-complicating it.

*   Don't show off by writing "compact code"

#3.REGARDING PERSONAL IMPROVEMENT

* * *

*   Don't be a Java or C/C++ (or other) fan-boy/girl. You'll be learning 10+ languages in a long-term career. Treat them as tools, not bandwagons.

*   There will always be a better programmer and they are hard to identify. Learn from them all.

*   You are not defined by the quality of your code. Don't judge yourself that way.

#4.REGARDING PHILOSOPHY

* * *

*   Programming is the art of enabling non-programmers to do more than what they can do alone.

*   Computer science is a catalyst to nearly every field of study or industry in the world. CS enables humanity to do more, solve more, be better.

*   Computer science != programming. If your college only taught you how to program, go ask for your money back.

DIFFERENCE BETWEEN A PROGRAMMER, A GOOD PROGRAMMER AND A GREAT PROGRAMMER.

*   Programmer: anyone who can write working programs to solve problems, given a sufficiently detailed problem statement. 

*   Good programmer: a programmer who collaborates with others to create maintainable, elegant programs suitable for use by the customer, on time and with low defect rates, with little or no interpersonal drama.

*   Great programmer: a good programmer who understands algorithms and architectures intuitively, can build self-consistent large systems with little supervision, can invent new algorithms, can refactor live systems without breaking them, can communicate effectively and cogently with non-technical staff on technical and non-technical issues, understands how to keep his or her ego in check, and can teach his or her skills to others. 

The path of becoming a great programmer is to start by being a programmer, and then develop the skills needed to be a good programmer, then practice those skills until you master them, then develop the skills needed to be a great programmer, and then practice those skills until you master them.

The amount of time this takes depends on your personal skills, personality, and training.  It also depends on the experience and opportunities that you have during your career, and how you react to them.

4 REASONS WHY YOUR PROGRAM CRASHES!

There may be 4 reasons why your program may crash:

*   Your program may depend on some element of randomness: user input, randomly generated number, time, etc.

*   If Your program is using an uninitialized variable, it could be accessing data it isn't supposed to (same with accessing something outside of an arrays indices)

*   Your program may be using an external library that crashes all the time.

*   Stack overflows!

Programming Quotes!

* * *

“Talk is cheap. Show me the code.” 
― Linus Torvalds

* * *

“Programs must be written for people to read, and only incidentally for machines to execute.” 
― Harold Abelson, Structure and Interpretation of Computer Programs

* * *

“Programming today is a race between software engineers striving to build bigger and better idiot-proof programs, and the Universe trying to produce bigger and better idiots. So far, the Universe is winning.” 
― Rick Cook, The Wizardry Compiled

* * *

“Always code as if the guy who ends up maintaining your code will be a violent psychopath who knows where you live” 
― John Woods

* * *

“That's the thing about people who think they hate computers. What they really hate is lousy programmers.” 
― Larry Niven

“The best programs are written so that computing machines can perform them quickly and so that human beings can understand them clearly. A programmer is ideally an essayist who works with traditional aesthetic and literary forms as well as mathematical concepts, to communicate the way that an algorithm works and to convince a reader that the results will be correct.” 
― Donald Ervin Knuth, Selected Papers on Computer Science

* * *

“I'm not a great programmer; I'm just a good programmer with great habits.” 
― Kent Beck

* * *

“Everyone knows that debugging is twice as hard as writing a program in the first place. So if you're as clever as you can be when you write it, how will you ever debug it?” 
― Brian W. Kernighan

* * *

“A language that doesn't affect the way you think about programming is not worth knowing.” 
― Alan J. Perlis

* * *

“The computer programmer is a creator of universes for which he alone is the lawgiver. No playwright, no stage director, no emperor, however powerful, has ever exercised such absolute authority to arrange a stage or field of battle and to command such unswervingly dutiful actors or troops.” 
― Joseph Weizenbaum

* * *

“Walking on water and developing software from a specification are easy if both are frozen.” 
― Edward Berard

* * *

“Perl – The only language that looks the same before and after RSA encryption.” 
― Keith Bostic

* * *

“The most disastrous thing that you can ever learn is your first programming language.” 
― Alan Kay

* * *

“A computer is like a violin. You can imagine a novice trying first a phonograph and then a violin. The latter, he says, sounds terrible. That is the argument we have heard from our humanists and most of our computer scientists. Computer programs are good, they say, for particular purposes, but they aren’t flexible. Neither is a violin, or a typewriter, until you learn how to use it.” 
― Marvin Minsky

“The most important property of a program is whether it accomplishes the intention of its user.” 
― C.A.R. Hoare

* * *

“Object-oriented programming offers a sustainable way to write spaghetti code. It lets you accrete programs as a series of patches.” 
― Paul Graham, Hackers & Painters: Big Ideas from the Computer Age

* * *

“At forty, I was too old to work as a programmer myself anymore; writing code is a young person’s job.” 
― Michael Crichton, Prey

* * *

“Some of the best programming is done on paper, really. Putting it into the computer is just a minor detail.” 
― Max Kanat-Alexander, Code Simplicity: The Fundamentals of Software

* * *

“Programmers are not to be measured by their ingenuity and their logic but by the completeness of their case analysis.” 
― Alan J. Perlis

* * *

“Progress is possible only if we train ourselves to think about programs without thinking of them as pieces of executable code. ” 
― Edsger W. Dijkstra

* * *

“Don't gloss over a routine or piece of code involved in the bug because you "know" it works. Prove it. Prove it in this context, with this data, with these boundary conditions.” 
― Andrew Hunt, The Pragmatic Programmer: From Journeyman to Master

* * *

“Remember that code is really the language in which we ultimately express the requirements. We may create languages that are closer to the requirements. We may create tools that help us parse and assemble those requirements into formal structures. But we will never eliminate necessary precision—so there will always be code.” 
― Robert C. Martin

* * *

“Software testing is a sport like hunting, it's bughunting.” 
― Amit Kalantri

* * *

“Programming, it turns out, is hard. The fundamental rules are typically simple and clear. But programs built on top of these rules tend to become complex enough to introduce their own rules and complexity. You’re building your own maze, in a way, and you might just get lost in it.” 
― Marijn Haverbeke

Thank You!