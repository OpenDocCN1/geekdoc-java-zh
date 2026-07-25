![](cover.jpeg)

# Python

## Learn Python Programming – Beginner Guide

Copyright 2016 by eProgramming - All rights reserved.

The contents of this book may not be reproduced, duplicated or transmitted without direct permission from the author.

# Table Of Contents

What is Python ?

History of Python

Features of Python

Getting Start with Python

The First Program

Values and Types

Variables

Key Words

Operators and Operands

Expressions and statements

Interactive mode and Script mode

Strings

Decision Making in Python

Loops

Lists

Dictionaries

Tuples

What is Python ?

Python is a best programming language for beginners. It is interpreted, high-level interactive and object-oriented ,scripting language. It is designed to be highly readable language. It is use more English keywords than any other programming language that’s way it is easy in learning and understanding.

## Python as interpreted Language:

Python is an interpreted language. It doesn’t use a compiler; the interpreter check the code line by line and creates a bytecode. Bytecode is an in-between “language” that isn’t quite machine code but it isn’t the source code. Because of this in-between state, bytecode is more transferable between operating systems than machine code; this helps Python be cross-platform. Java is another language that uses bytecodes. However, because Python uses an interpreter rather than compiler, the code processing can be slower. The bytecode still has to be “deciphered” for use by the processor, which takes additional time. But the benefit to this is that the programmer can immediately see the results of his code. He doesn’t have to wait for the compiler to decide if there is a syntax error somewhere that causes the program to crash. Because of interpretation, Python and similar languages are used for rapid application development and program prototyping. For example, a simple program can be created in just a few hours and shown to a customer in the same visit. Programmers can repeatedly modify the program and see the results quickly. This allows them to try different ideas and see which one is best without investing a lot of time on dead-ends. This also applies to creating graphical user interfaces (GUIs). Simple “sketches” can be laid out in minutes because Python not only has several different GUI libraries available but also includes a simple library (Tkinter) by default.

## Python as Object-Oriented Programming (OOP):

Python supports Object-Oriented style of programming that packs code within objects. Python is unique from other languages because in that you have two choices when developing your programs: procedural programming or object-oriented. You can mix the two in the same program.

Procedural programming is a step-by-step process of developing the program . Functions are called by  the program at time to perform some processing , then control is returned back to the main program . C and BASIC are procedural languages.

Object-oriented programming (OOP) means that programming with objects . Objects  can be created by  different units of programming logic; variables and methods are combines into objects that do a particular thing. For example if you built a model of some kind of robot and each part of its body would be separated object, capable of doing different things but still part of the overall object. OOP is also heaving used GUI development.

## Python as beginner’s Language:

Python provided  wide range of applications from simple text processing to WWW browsers to games. It is a great language for the beginner level  programmers.

History of Python

Guido van Rossum was the developer of Python Language. Its was developed in late eighties and early nineties at the National Research institute for Mathematical and Computer Science in the Natherland.He play a vital role in directing its progress.

It is a combination of many other languages including ABC, Modula-3, C , C++, Algol-68 , SmartTalk, and Unix shell and other scripting languages. It is now copyrighted and source code is nw available under the GNU General Public License( GPL)

Features of Python

Following are some features of python Programming:

## Easy to learn:

It was very easy to learn than other languages. Python has few keywords and simple structure which is easy to make and easily can understand. It has clear syntax which allows programmers to pick up the language quickly.

## Easy to read:

It is a high level language and use many keywords from English Language. That’s why it is easy to read and understanding than other languages. The code is more clearly defined and visible to the eyes. And source code easily to maintain.

## Standard Libraries:

Python has bulk of libraries which are use in programming . These libraries are portable and cross-platform compatible on UNIX, Windows and Macintosh.

## Interactive Mode:

Python allows an interactive mode which support interactive testing and debugging of snippets of code.

## Portable:

Python has the same interface on all platforms and can run on a wide variety of hardware platform. . It is portable, meaning that they can run on different kinds of computers with no modifications.

## Extendable:

It is feature of python that it can add low-level modules to the Python interpreter. These modules enable programmers to add to or customize their tools to be more efficient.

## Database:

Python provides to programmers interfaces to all major commercial databases.

## Graphical User Interface (GUI) Programming:

Python has ability to perform on GUI that can be created and ported to many systems calls, s, windows systems such as Windows MFC, Macintosh and the X windows systems of Unix  ,and libraries.

## Scalable:

Python is very vast and progressive language it can provides a better structure and support for large programs than shell scripting.

Python has many other features than above-mentioned, some of them are below:

*   It can be compiled to byte-code for building large applications.
*   It can support IT functions and structured programming methods and OOP.
*   One of the most powerful feature of programming languages is the ability to manipulate variables.
*   IT supports automatic garbage collection.
*   It has ability to  easily integrated with C, C++, CORBA, ActiveX, COM, and JAVA.
*   It provides very high-level dynamic data types and supports dynamic type checking.

Getting Start with Python

Python is considered an interpreted language because Python programs are executed by an interpreter. There are two ways to use the interpreter: interactive mode and script mode. In interactive mode, you type Python programs and the interpreter displays the result:

1+1

2

The chevron, >>>, is the prompt the interpreter uses to indicate that it is ready. If you type  ,1+1, the interpreter replies 2\. Alternatively, you can store code in a file and use the interpreter to execute the contents of the file, which is called a script. By convention, Python scripts have names that end with .py extention.

To execute the script, you have to tell the interpreter the name of the file. If you have a script named mywork.py and you are working in a UNIX command window, you type python mywork.py. In other development environments, the details of executing scripts are different. You can find instructions for your environment at the Python website [http://python.org.](http://python.org./)

Working in interactive mode is convenient for testing small pieces of code because you can type and execute them immediately. But for anything more than a few lines, you should save your code as a script so you can modify and execute it in the future.

## What is a Program ?

A program is a combination of lines of code\instructions that specifies how to perform a computation. The computation might be something mathematical , such as solving equations or finding the roots of a polynomial , but it can also be symbolic computation such as searching and replacing text in a document or compiling a program.

There are some instructions in every language :

*   Input: Getting data from user through keyboard or other input device
*   Output: Displayed data on screen or other output device.
*   Math: Perform basic mathematical operations.
*   Conditional execution: Check for certain conditions and execute the appropriate code.
*   Repetitions : Perform some action repeatedly, usually with some variation.

## What is debugging ?

Programming errors are called bugs and the process of tracking them down is called debugging.

There are three types of errors in programming:

### Syntax Error:

Python can only executes a program if the syntax error is correct; otherwise the interpreter displays an error message. Syntax are rules about structure . For example , parentheses have to come in matching pairs so (1+3) is legal, but 3) is a syntax error.

During the first few weeks of your programming , you will probably spend a lot of  time tracking down syntax error . As you gain experience , you will make fewer errors and find them faster.

### Runtime Error:

The second type of error is a runtime error ,so called because the error does not appear until after the program has started running. These errors are also called exceptions because they usually indicate that something exceptional (and bad) has happened.

### Logical Error:

The third one is logical error. If there is a logical error in your program , it will run successfully in the sense that the computer will not generate any error message, but it will not do the right thing it will do something that we are not excepting. Specifically it will do what you told to it to do. Its occur due to make wrong logic of program.

Before we start our first program in Python we must know some terminologies and their functions in a short way .It will clear the concept of beginners and be a very helpful for them.

Problem solving: The process of formulating a problem, finding a solution, and expressing the solution.

High-level language: A programming language like Python that is designed to be easy for humans to read and write.

Low-level language: A programming language that is designed to be easy for a computer to execute; also called “machine language” or “assembly language.” portability: A property of a program that can run on more than one kind of computer. interpret: To execute a program in a high-level language by translating it one line at a time.

Compile: To translate a program written in a high-level language in to a low-level language all at once, in preparation for later execution.

Source code: A program in a high-level language before being compiled.

Object code: The output of the compiler after it translates the program.

Executable: Another name for object code that is ready to be executed.

Prompt: Characters displayed by the interpreter to indicate that it is ready to take input from the user.

Script: A program stored in a file (usually one that will be interpreted).

Interactive mode: A way of using the Python interpreter by typing commands and expressions at the prompt.

Script mode: A way of using the Python interpreter to read and execute statements in a script.

Program: A set of instructions that specifies a computation.

Algorithm: A general process for solving a category of problems.

Bug: An error in a program.

Debugging: The process of finding and removing any of the three kinds of programming errors.

Syntax: The structure of a program.

Syntax error: An error in a program that makes it impossible to parse (and therefore impossible to interpret).

Exception: An error that is detected while the program is running.

Semantics (logic): The meaning of a program.

Semantic (Logical) error: An error in a program that makes it do something other than what the programmer intended.

Token: One of the basic elements of the syntactic structure of a program, analogous to a word in a natural language.

Parse: To examine a program and analyze the syntactic structure.

Print statement: An instruction that causes the Python interpreter to display a value on the screen.

Value: One of the basic units of data, like a number or string, that a program manipulates.

Type: A category of values. The types we have seen so far are integers (type int), floating point numbers (type float), and strings (type str).

Integer: A type that represents whole numbers. floating-point: A type that represents numbers with fractional parts.

String: A type that represents sequences of characters.

Variable: A name that refers to a value.

Statement: A section of code that represents a command or action. So far, the statements we have seen are assignments and print statements.

Assignment: A statement that assigns a value to a variable.

State diagram: A graphical representation of a set of variables and the values they refer to.

Keyword: A reserved word that is used by the compiler to parse a program; you cannot use keywords like if, def, and while as variable names. 

Operator: A special symbol that represents a simple computation like addition, multiplication, or string concatenation

Operand: One of the values on which an operator operates.

Floor division: The operation that divides two numbers and chops off the fraction part.

Expression: A combination of variables, operators, and values that represents a single result value.

Evaluate: To simplify an expression by performing the operations in order to yield a single value.

Rules of precedence: The set of rules governing the order in which expressions involving multiple operators and operands are evaluated.

Concatenate: To join two operands end-to-end.

Comment: Information in a program that is meant for other programmers (or anyone reading the source code) and has no effect on the execution of the program.

The First Program

In all the new languages the first program is called “Hello World” because all it dose is display the word “Hello World”.

In Python :

Print ‘Hello World’

This is a simple example of print statement , which doesn’t actually print anything or paper. It displays a value on the screen . In this case , the result is the words

Hello World

The quotation marks in the program mark the beginning and end of the text to be displayed; they don’t appear in the result.

In Python 3, the syntax for printing is slightly different:

print('Hello, World!') The parentheses indicate that print is a function.

If you are using Python 3, you will have to translate. But other than that, there are very few differences we have to worry about.

Values and Types

Letter and numbers are known as values in program.

Example: 1 , 20 , Hello etc.

These values have some different types. In above examples  ‘1’  is integer and “Hello” is string, you can identify strings because they are enclosed in quotations marks.

If you are not sure what type a value has, the interpreter can tell you.

type(‘Hello’)

<type ; ‘str’>

type(49)

<type ‘int’>

The keywords using in python for integers are int and for string is  str. We cannot use their full name. Integers are use for only  whole numbers in which no decimal point is used. Numbers with a decimal point belong to a type called float , because these are represented in a format called floating-point. Float also called real numbers.

Example:

type(8.8)

<type ‘float’>

If the numbers coded in the quotations form they also became a string….

type(‘49’)

<type ‘str’>

type(‘8.8’)

<type ‘str’)

They are strings.

Variables

A variable is a name refer to the a value. It is a place where you can put a stuff in. One of the  most powerful feature of programming languages is the ability to manipulate variables.

For creation of  new variable we use assignment operator and give them value:

result = ‘easily done’

x = 88

g = 9.8 

Above these examples we have use three variables. The first assign a string to a new variable named “result”; the second gives the integer 88 to x and the third assigns the value of gravitational acceleration “g” to 9.8.

The type of a variable is the type of the value it refers to.

type(message)

<type 'str'>

type(n)

<type 'int'>

type(pi)

<type 'float'>

## Rules for variable name:

We have some rules for creating a variable name are:

*   It is not a keyword.
*   No special character use except underscore ( _ ).
*   No space or blanks are allowed within variable name.
*   First character must b alphabet.
*   It can be alpha-numeric.
*   Never use again same name.
*   It can be uppercase, but its good idea to begin variable name with a lowercase letters.

A good programmer choose a meaningful name for their variables. Which he used in his program.

If you give an illegal name , you get a syntax error.

20level = 'Final round'

SyntaxError: invalid syntax

good@ = 1000000

SyntaxError: invalid syntax

class = 'look good'

SyntaxError: invalid syntax

20level is illegal because it does not begin with a letter. good@ is illegal because it contains an illegal character, @. But what’s wrong with class? It turns out that class is one of Python’s keywords. The interpreter uses keywords to recognize the structure of the program, and they cannot be used as variable names.

Key Words

These are the words whose meaning has already been explained in the programming language. Keywords cannot be used as variable names because if we do so we are trying to assign a new meaning to the keywords, which is not allowed by the computer.

Every keyword perform a  specific task.

Some important keywords are below in the table which are used in the python programming:

|                             And | del | from |
| Not | while | as |
| Assert | elif | global |
| Or | with | else |
| If | pass | yield |
| Break | except | import |
| Print | class | exec |
| In | raise | continue |
| Finally | is | return |
| Def | lambda | for |
| Try |  |  |

Operators and Operands

The computation work like addition and multiplication perform with operators. The values the operator is applied to are called operands. Operators are the construct which can manipulate the value of operands.

Some basic operators are :

1. Arithmetic Operators                                      

*   Comparison (Relational) Operators
*   Assignment Operators
*   Logical Operators

## Arithmetic Operators:

There are useful arithmetic operators:

| + | Additions | * | Multiplication |
| - | Subtraction | / | Division |
| ** | Exponentiation | % | Modulus |
| // | Floor Division |  |  |

As in following example:

2+3      hour-1                            hour*2+minute              minute/30              2**5              (x+2)*(y-22)

In Python , the declaration is not necessary. In other languages you must declare first then initialize and both steps done in same line of  the code. For example in C++

int a = 3;     //inline initialization of integer

float b;

b = 4.0 f ;         //sequential initialization of floating point number

In this you can see that it is essential to declare first either it is float or integer .

But in Python Its not essential , if you initialize a variable with some value its store in that type. As you can see in this example:

a = 3 #integer

b = 4.0 #floating point

As you can see, “a” and “b” are both numbers but Python can figure out what type they are without being told. In the C++ example, a float value has to be “declared” twice; first the variable is given a type (“float”) then the actual value is given to the variable. You’ll also note that comments in Python are set off with a hash/pound sign (#) and are used exactly like the “//” comments in C++ or Java. That’s about it for numbers in Python.

In Python 2, the division operator might not do what you expect:

minute = 59

minute/60

0

The value of minute is 59,and in conventional arithmetic 59 divided by 60 is 0.98333,not 0\. The reason for the discrepancy is that Python is performing floor division “//”. When both of the operands are integers, the result is also an integer; floor division chops off the fraction part, so in this example it rounds down to zero.

In Python 3, the result of this division is a float. The new operator // performs floor division. If either of the operands is a floating-point number, Python performs floating-point division, and the result is a float:

minute//60.0

0.98333333333333328

## Comparison(Relational) Operators:

These operators decide the relation among them and compare the values on either side of them.

| Operators | Description |
| == | This applied when two values are equal to each other |
| != | This applied when two values are not equal to each other. |
| > | This is used for greater than |
| < | This is used for less than |
| >= | This is used for greater than or equal to |
| <= | This is used for less than or equal to |
| <> | If two operands are not equal then it used as != |

## Assignment operators:

In Python we used some assignment operators. Their description given in the table below:

| Operators | Description |
| = | It assigns values from right side operands to left side operand. |
| +=(Add AND) | It added up the both operands and assign the value of result to left operand. |
| -=(Subtract AND) | It subtracted right operand from left and assign result to left operand. |
| *=(Multiply AND) | It multiply both operands and assign the result to left operand. |
| /=(Divide AND) | It divides right operand with left and assign the result to left operand. |
| **=(Exponent AND) | It make exponent to left operand on right and  assign the result to left operand. |
| %=(Modulus AND) | It takes modulus using two operands and assign the result to left operand. |
| //=(Floor Division AND) | Its applied floor division on operators and assign value to left operand. |

## Bitwise Operators:

They perform bit by bit operations and works on bits.

There are some Bitwise operators used in python:

| Operators | Description |
| & Binary AND | If both cases true than it exist |
| &#124;Binary OR | If either one operand true it will exist |
| ^ Binary XOR | It copies the bit if it exists in one operand but not both |
| ~ Binary ones Complement | It has the effect of ‘flipping’ bits. |
| << Binary left shift | The left operands value is moved left by the number of bits specified by the right operand. |
| >> Binary right shift | The left operands value is moved right by the number of bits specified by the right operand. |

Examples:

Let consider if a = 60; and b = 13; Now in binary format they will be as follows −

a = 0011 1100

b = 0000 1101

-----------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011

## Logical Operators:

There are following logical operators used in Python programming:

| Operators | Description |
| and | It works only when both conditions satisfied. |
| or | It works when only one condition true. |
| not | Use to reverse the result. |

## Membership Operators:

There are only two membership operators. They test the membership in a sequence such as triples, lists or strings.

| Operators | Description |
| in | Only when true when it finds a variable in a specified sequence. |
| not on | Only when true when it does not finds a variable in a specified sequence. |

## Identity Operators:

They are use for comparing the memory locations of two objects. There is only two identity operators in Python:

| Operators | Description |
| is | Evaluates to true if the variables on either side of the operator point to the same object and false otherwise. |
| is not | Evaluates to false if the variables on either side of the operator point to the same object and true otherwise. |

## Order of Operations:

When we use more than one operator in an expression, then the order of evaluation depends on the rules of priority. There is a priority order for mathematical operators on which they can execute. The priority order from top to bottom:

*   Parentheses have the highest priority and can be used to force an expression to evaluate in the order you want.

Examples: 3*(5+4) ,              (2**5)+2

              In first answer is 27 and in second 34.

*   Exponentiation has the second highest priority

So 4**2+1 is 17 not,64 and 3*1**3 is 3 not, 27.

*   After Exponential Complement, unray plus and minus (+@ and -@) have third highest priority .
*   Division, multiplication , modulus and floor division have same priority order. So 2*3-1 is 5 not, 4 and 6+4/8 is 8 not, 5.
*   Addition and subtraction have the same priority after division and multiplication.
*   <<  >> right and left bitwise shift .
*   & Bitwise ‘AND’.
*   ^ | Bitwise exclusive “OR” and regular “OR”.
*   <=  <  >   >=  Comparison Operators.
*   <>  ==  != Equality Operators.
*   =   %=   /=    //=   -=   +=   *=    **=    Assignment Operators.
*   is    is not    Identity Operators.
*   in   not in    Membership Operators.
*   not   or   and    Logical Operators.   

Operators with the same priority are evaluated from left to right.

I don’t work very hard to remember rules of precedence for other operators. If I can’t tell by looking at the expression, I use parentheses to make it obvious.

Expressions and statements

A combination of values, operator and variables are called expression. A value all by itself consider an expression, and so is a variable , so the following are all legal expressions

Example:

88

X

X+11

A statement is a unit of code that the Python interpreter can execute. We have seen two kinds of statement: print and assignment.

Technically an expression is also a statement, but it is probably simpler to think of them as different things. The important difference is that an expression has a value; a statement does not.

Interactive mode and Script mode

One of the benefits of working with an interpreted language is that you can test bits of code in interactive mode before you put them in a script. But there are differences between interactive mode and script mode that can be confusing.

For example, if you are using Python as a calculator, you might type

>>> miles = 26.2

>>> miles * 1.61 42.182

The first line assigns a value to miles, but it has no visible effect. The second line is an expression, so the interpreter evaluates it and displays the result. So we learn that a marathon is about 42 kilometers. But if you type the same code into a script and run it, you get no output at all. In script mode an expression, all by itself, has no visible effect. Python actually evaluates the expression, but it doesn’t display the value unless you tell it to:

miles = 26.2

print miles * 1.61

This behavior can be confusing at first. A script usually contains a sequence of statements. If there is more than one statement, the results appear one at a time as the statements execute.

For example, the script:

print 100

x = 55

print 11

produces the output

100

11

The assignment statement produces no output.

Strings

Strings in programming are simply text, either individual characters, words, phrases, or complete sentences. Strings are amongst the most popular type in Python. They are one of the most common elements to use when programming, at least when it comes to interacting with the user. Because they are so common, they are a native data type within Python, meaning they have many powerful capabilities built-in. Unlike other languages, you don’t have to worry about creating these capabilities yourself. This is good because the built-in ones have been tested many times over and have been optimized for performance and stability.

Strings in Python are different than most other languages. We can create a string simply by enclosing characters in quotes .First off, there are no char types, only single character strings. Strings also can’t be changed in-place; a new string object is created whenever you want to make changes to it, such as concatenation. This simply means you have to be aware that you are not manipulating the string in memory; it doesn’t get changed or deleted as you work with it. You are simply creating a new string each time. Creating a string is simple. For Example:

num1 = ‘Hello World’

num2 = ‘Basics of Python’

there is no character type  in Python. These are treated as string of length one, thus also considered a substring.

We use square brackets to access substrings with the index and indices to obtain your substring. For example:

num1 = ‘Hello World’

num2 = ‘Basics of Python’

print “num1[0]:”, num1[0]

print “num2[1:5]:” , num2[1:5]

the output will be :

num1: H

num2: asics

Here is a list of common string operations:

*   s1 = ‘ ’ : empty string
*   s2 = “knight’s” : double quotes
*   block = “““ - ””” : triple-quoted block
*   s1 + s2 : concatenate (combine)
*   s2 * 3 : repeat the string a certain number of times
*   s2[n] : index (the position of a certain character)
*   len(s2) : get the length of a string
*   “a%sparrot” %‘dead’: string formatting(deprecated in Python 3.x)
*   “a {0} parrot”.format(“dead”) : string formatting (Python 3.x)
*   for x in s2 : iteration (sequentially move through the string’s characters)
*   ‘m’ in s2 : membership (is there a given character in the string?)

In general, you can’t perform mathematical operations on strings, even if the strings look like numbers, so the following are illegal:

'2'-'1' 'eggs'/'easy' 'third'*'a charm'

The + operator works with strings, but it might not do what you expect: it performs concatenation, which means joining the strings by linking them end-to-end. For example:

first = 'Basics'

second = 'of'

third = ‘Python’

print first + second + third

The output of this program is:

BasicsofPython.

The * operator also works on strings; it performs repetition. For example,

'Spam'*3

is

'SpamSpamSpam'.

If one of the operands is a string, the other has to be an integer. This use of + and * makes sense by analogy with addition and multiplication. Just as 4*3 is equivalent to 4+4+4, we expect 'Spam'*3 to be the same as 'Spam'+'Spam'+'Spam', and it is. On the other hand, there is a significant way in which string concatenation and repetition are different from integer addition and multiplication.

There is a table for these operators:

| Operators | Description | Operators | Description |
| + | Concentration- Adds two values . | * | Repetition-create the same string |
| [] | Slice-gives the value of substring | [:] | Range Slice-gives character from given range |
| In | Membership-returns if a character exists in the given string | not in | Membership- true if character does not exist. |
| % | Format- Performs String Formatting. |  |  |

String Formatting:

It is a very good feature of python programming. Its resembles from the function from C’s printf() family. Its symbol is %. For example:

print “ My name is %s and roll no. is %d.” % (‘Omer’, 15)

This code will produce output:

My name is Omer and roll no. is 15.

There are some useful symbols which can be used along with %-

| Format symbol | Conversion | Format Symbol | Conversion |
| %c | character | %s | string conversion |
| %i, %d | signed decimal integer | %u | unsigned decimal integer |
| %o | octal integer | %x | hexadecimal integer(lowercase letters) |
| %X | hexadecimal integer(uppercase letters) | %e | exponential notations(with lower case ‘e’ ) |
| %E | exponential notations (with uppercase ‘E’) | %f | floating point real numbers |

Decision Making in Python

In our daily life we often make decision according to conditions. For example if we have $5 then we buy a cricket bat otherwise not. This example shows that if the first condition is true than we can proceed more , it not then we do some other task. As it is Python provides us this type of conditions statements in programming to make decision. Decision structure evaluates multiple expressions which produce true or false as outcome. In Python programming zero and null values assumes as false others are true.

In Python we have following types of decision making statements:

## if  Statement:

It is similar to C language. In if statement we give it some conditions which data is compared and a decision is made. If the condition is satisfy then statement print.

Syntax

if (condition)

statement

Example:

num1 = 2

if num1:

              print “Expression is true”

              print num1

num2 = 0

if num2:

              print “Expression is False ”

              print num2

print “Its Over”

The block of statements inside the if statement can be executed if Boolean expression evaluate to true. If Boolean expression evaluates to false, then the next code after the end of the if statement is executed.

if-statemnt can be coded in a single line.

Example:

num = 1

if ( num== 1 ) : print "one-line if"

## if-else statement:

  If the condition of it statement is false and then the control of execution jumped to first statement after the if statements, If we use else statement then it execute after the if statement. An else statement combined with and if statement. It is optional statement and mostly use once in the if-else statements block.

Syntax:

if (conditon):

statement

else:

statement

Example:

num1 = 0

if num1:

   print "Expression is true"

else:

    print "Expression is false"

## The elif Statement:

If we want to check multiple expressions for true and execute a block of statements  as soon as one of the conditions evaluates to true, we have elif Statement to perform this type of task.

It is optional as else statement. We mostly use just one else statement in block but there can be many number of elif statements.

Syntax:

if (condition1):

              statement

elif(condition2):

              statement

elif(condition3):

              statement

else:

              statement

it is similar to switch case statements in other languages.

Example:

num = 1

if num == 2:

 print "True Expression 1"

elif num == 3:

 print "True Expression 2"

elif num == 1:

 print "True Expression 3"

elif num == 1:

 print "True Expression 4"

else:

 print "No one match!"

If no one can match with the true expression than else statement will be printed.

Loops

When we need to repeat the execution of block of code several times then we use loops in Python.  In programming languages there are various control structures that allows for more complicated path.

A simple loop statement allows us to execute a block of code multiple times.

To handling the looping requirements Python provides following types of loops:

## While Loop:

If the given condition is true , while loop repeatedly executes a statement until it becomes false.

Sytanx:

while (condition):

statement

increment\decrement

First of all we declare a variable above the while loop. Then we give condition in the parentheses. In condition we may use relational operators. Then we write statement of the loop, if statement is true loop executes again and again until is false. Statement may be single line or a block of statements. After the statement we mention the increment or decrement in the last of the loop. If loop executes first time than second time it will executes with that increment or decrement. This process executes until the condition becomes false.

Example:

value = 0

while (value <5):

print ‘The value is:’, value

value= value +1

print “Its Over”

This block is consisting only print and increment statements, Its increase the value 1 after every cycle of loop. When value increase by 4 the condition becomes false and it stop working.

Using else statement with While Loop:

Python supports to have an else statement associated  with the While Loop statement.

If  the else statement is used with the while loop, the else statement is executed when the condition becomes false.

## For Loop:

For loop has ability to repeat over the items of any sequence, such as a list or a string. Expression list evaluated first if a sequence contain any of this. Then the first item in the sequence is assigned to the iterating variable. After this the statement block is executed. Each time in the list is assigned to iterating variable, and the statement block is executed until the entire sequence is exhausted.

Syntax:

for iterating_var in sequence:

statements

Example:

for letter in ‘Python’:

print ‘Current Letter  :’ , letter

print “Its Over”

Using else statement with for loops:

In Python we can use else  statement with for loop.

The else statement is executed when the loop has exhausted iterating the list.

## Nesting of Loops:

A loop or many loops inside a loop is called nesting of loops. Python programming allows to nesting of loops.

For Loop Sytanx:

for iterating_var in sequence:

for iterating_var in sequence:

statements

statements

While Loop Syntax:

while(conditon):

while(condition):

 statements

statements

increment\decrement

## Loop Control Statements:

To change the normal loop execution we use loop control statements. In Python we have following control statements:

### Break Statement:

It performs the same work as break statement in C. Its stop the execution and jumped out the execution from the loop block. The break statement used in both for and while loops. If you are using nested loops, the break statement stops execution of the innermost loop and start execution the next line of code after the block.

Syntax;

break

Example :

for letter in ‘ Python’ :

              If letter == ‘h’ :

              break

print ‘ Current Letter :’  , letter

print “ Its Over”

### Continue Statement:

When the continue statement used in looping its return the control to the beginning of the the loop. It cannot execute the remaining statements in the current iteration of the loop and moves the control back to the top of the loop.

It can be used in both while and for loop.

Syntax:

continue

Example :

for letter in ‘Python’:

 if  letter == ‘o’:

 continue

print ‘Current Letter :’ , letter

print “Its Over”

### Pass  Statement:

Nothing happened when it executes, it is a null operation. It is useful in places where the code will eventually go, but has not been written yet.

Syntax:

pass

Example:

for letter in ‘Python’ :

              if letter == ‘h’:

              pass

print ‘This is pass block’

print ‘Current Letter :’ , letter

print “Its Over”

Lists

Like a string, list is a sequence of values. The most basic data structure in Python is sequence. Each element in the sequence have its own position or index. The first position is always zero, second is one and so on. In strings we have only values of characters but in a list they can be any type. The values in list called elements or sometimes items.

The creating of list is so easy, we can create a list just using square brackets. Elements are enclose in it and put the comma to separated elements.

Example1:

List1 = [10, 20, 30, 40];

Example2:

List2 = [‘June’, ‘July’, ‘August’ ];

Example3:

List3 = [‘march’, 2.1 , 5 ]:

In first example we simple use integers in list. In second , strings are used and in third example we use string, float and integer.

A list contain no element is called an empty set. You can create empty list by brackets [].

## Access Values in List:

They are accessed just like strings (e.g. slicing and concatenation) so they are simple to use and they’re variable length, i.e. they grow and shrink automatically as they’re used. To access elements in list , use the square brackets. In reality, Python lists are C arrays inside the Python interpreter and act just like an array of pointers.

Example:

list1 = ['June', 'july', 404, 808];

list2 = [1, 2, 3, 4, 5, 6, 7 ];

print "list1[0]: ", list1[0]

print "list2[1:3]: ", list2[1:3]

The biggest thing to remember is that lists are a series of objects written in side square brackets, separated by commas. Dictionaries and tuples will look similar except they have different types of brackets.

The most common use of a list is to iterate over the list and perform the same action to  each object within the list, hence the use of similar data types.

## Adding Elements in List:

Adding new elements in a list is so easy. For this purpose we have append statement with which we can tell the list to add it.

Example:

mylist = [20 , 22 , 24 ];

mylist. append (26) ;

print mylist

To linked two list together, we have extend() statement. We can linked two lists together by using this statement.

Example:

list1 = ["June", "July" ,"August"];

list2 = [5 , 10 , 15 ];

list1.extend(list2);

print list1

## Remove Elements in List:

There are many ways to delete elements from a list. To delete a n element you can use either del statement and pop if you know exactly which element you are deleting or remove method if  you don’t know.

Pop modifies the list and return the element that was removed after execution.

Example:

list = ['a', 'b', 'c'];

newlist = list.pop(1);

print t

del operator can be used if you don’t remove the value.

Example:

list = ['a', 'b', 'c'];

del list[1];

print t

if you don’t know the index of that element which desired to remove but know that element, you can use remove statement.

Example:

list= ['a', 'b', 'c'];

list.remove('b');

print list

## List Operators :

Lists also perform +(concentration)  and *(repetition) operators like string, but the result is is new list not a string.

Lists performs all of the general operations we used on strings.

| Expression | Output | Description |
| [1 , 2 , 3 ]+[4, 5, 6] | [1, 2, 3, 4, 5, 6] | Concentration |
| Len([1, 2, 3]), | 3 | Length |
| 3 in [1, 2, 3] | True | Membership |
| [‘OK’]*4 | [‘OK’ ,’OK’ , ‘OK’ , ‘OK’ ] | Repetition |
| For x in [1, 2, 3]: print x, | 1 2 3 | Iteration |

Dictionaries

Dictionaries are one of  the  most useful data type in Python. A dictionary is like a list but  it has more general properties. In a list , the indices have to be integers but in dictionaries they can be almost any type. They are unordered collections of objects, matches to a keywords. List on the other hand, are ordered collections that use a numerical offset.

Python dictionaries provide  a mapping between a set of indices i.e keys and a set of values. Each key map to a value. The relation of key and a value is called a key-value pair or sometimes an item.

## Basic Properties of Dictionaries:

There are some properties of dictionaries:

*   It is not an offset and easily accessed by keyword. Its perform the same execution as associative arrays. All the items in dictionary have its own keyword; the keyword is used to call the item.
*   To provide faster lookup, the stored objects are in a random order. When created, a dictionary stores items in any order it chooses. To use the key, we get the item. There are no buit-in method in dictionaries to order the items, If you need to order do it yourself.
*   Dictionaries are variable length, can hold objects of any type ,and support deep nesting
*   They can’t be modified like lists or strings but can be mutable.
*   They are the only data type that support mapping.
*   Internally, dictionaries are implemented as a hash table.

## Basic Dictionaries Operation: 

Now we have a list of some common operations in Python dictionaries:

*   d1 = { } Empty dictionary.
*   d2 = { ‘basic’ : 2, ‘Python’ : 3} Two-item dictionary.
*   d3 = { ‘June’ : { ‘July’ :  1 , ‘August’ : 2 } } Nesting.
*   d2 [ ‘Python’ ] , d3[ ‘June’ ][ ‘July’ ] Indexing by key.
*   d2.has_key( ‘Python’), d2.keys( ) , d2.values( )  Methods: membership test, keys list, values list, etc.
*   len(d1) Length (number stored entries).
*   d2 [key] = new, del d2[key] Adding/changing, deleting.

Making of dictionaries;

You can create dictionaries and access items via a key. This is any type which cannot b changed. The values can be any type of  objects,  including other dictionaries. The format of making  a dictionary is below:

dictionary = { “key name” : value }

Any type allowed in key name and values. For example:

Dictionary = { ”Batman” : “Spiderman” , 2 : “Superman” , 3 : [ “Thor” , “Hulk” ] };

Notice that the brackets used in dictionaries are curly braces, the separator between a key word and its associated value is a colon. And the each key and its value is separated from other keys and their values is separated by a comma. This is just some of things that  can cause syntax error in your programming.

There are some important points about dictionaries:

*   In dictionaries we have mapping not sequence, therefore sequence operations don’t work. Function like concatenation and slicing don’t work because there is no order to dictionary item.
*   Keys can be created by adding new values to an existing dictionary or when you making a dictionary. The process is similar and the end result is the same.
*   Keys can be anything immutable.

There are some built-in functions in dictionaries with their description:

| Functions |               Description              |
| cmp(dict1 , dict2) | Compare elements of dict |
| str(dict) | It can produces a printable string representation of a dictionary. |
| len(dict) | It provides total length of  the dictionary and this would  be equal to the number of elements in the dictionary |
| type(variable) | It returns the type of the passed variable. If passed variable is dictionary, then it would return a dictionary type. |

There are some basic methods in Python dictionary:

| Methods | Description |
| dict.clear( ) | With using this we can remove all the items in dictionary dict. |
| dict.copy( ) | With using this we can copy the elements of dictionary dict. |
| dict.fromkeys( ) | In this method we create a new dictionary with keys from seq and values. |
| dict.has_key(key) | It will give a true if key is in the  dictionary dict, otherwise false. |
| dict.items( ) | It will return a list of dict’s tuple pairs. |
| dict.key( ) | This method is returns a list of keys in the dictionary. |

Tuples

The final built-in type in Python is tuple. A tuple is a sequence of values. Any type of value can be used in and they are indexes by integers, Therefore they are not like for list. They are work like a Python list except they are immutable mean they can’t be changed in place. They are usually written in the parentheses to distinguish them from the lists in which we use square brackets. But sometimes parentheses are not necessary. Their length is fixed. A new tuple must be created when we need to grow  or shrink a tuple.

Tuples are immutable therefore they can be used to store different data about a certain thing. The most important thing is that standard operations like slicing and iteration return new tuple objects. In Python programming there are a few times when you simply have to use a tuple because your code requires it.

There are some other  reasons to use tuples:

*   The speed  of proceeding is faster than list. You must use a tuple when you are creating a constant set of values that would not change and you need to simply iterate through them.
*   The sequences within a tuple are essentially protected from modification.
*   They can also be used as keys for dictionaries. Most of the programmers did not use tuples for this purpose.
*   They are use to holding multiple values to be inserted into a string in the string formatting.

## Basic Operation:

Here is a list of some common operations for tuples:

*   () it’s a simply an empty tuple.
*   tup1 = (0, ) A one-item tuple.
*   tup2 = (0, 1, 2, 3)
*   tup3 = 1, 2, 3, 4 it is another four-item tuple as above but is has no parentheses.
*   tup3 = ( ‘xyz’ , ( ‘ijk’ , ‘lmn’ )) ,          Nested tuples.
*   tup1[n] , tup3[n][j] ,  Index.
*   tup1[i:j] ,                                 Slice.
*   len(tup1) ,                            Length.
*   tup1 + tup2 ,                        Concatenate.
*   tup3*4 ,                                Repeat.
*   for x in tup2 ,                                  Iteration.
*   3 in tup2 ,                                    Membership.

The second entry shows hoe to create a one item tuple. Since parentheses can surround expressions, you have to show Python when a single item is actually a tuple by placing a comma after the item. The fourth entry shows a tuple without parentheses; this form can be used when a tuple is unambiguous. However, it’s easiest to just use parentheses than to figure out when they’re optional.

## Creating a Tuple:

Creating a tuple is very simple you just put the values and separate them by using comma. You can use parentheses to close the tuple but it’s optionally.

Example:

tup1 = ( ‘Sunday’ , ‘Monday’ , 1 , 2 );

tup2 = ( 11 , 12 , 13 , 14 , 15);

tup3 = “a” , “b” , “c” , “d” ;

## Access a Value:

We use square brackets for slicing along with index or indices to get the value at that index.

Example:

tup1 = ('Sunday', 'Monday', 1, 2);

tup2 = (1, 2, 3, 4, 5, 6, 7 );

print "tup1[0]: ", tup1[0]

print "tup2[1:5]: ", tup2[1:5]