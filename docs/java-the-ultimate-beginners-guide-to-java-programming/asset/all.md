![](cover.jpeg)

Java

The Ultimate Beginner’s Guide to Java Programming

 Copyright 2016 by Steve Tale All rights reserved.

This document is geared towards providing exact and reliable information in regards to the topic and issue covered. The publication is sold with the idea that the publisher is not required to render accounting, officially permitted, or otherwise, qualified services. If advice is necessary, legal or professional, a practiced individual in the profession should be ordered.

- From a Declaration of Principles which was accepted and approved equally by a Committee of the American Bar Association and a Committee of Publishers and Associations.

In no way is it legal to reproduce, duplicate, or transmit any part of this document in either electronic means or in printed format. Recording of this publication is strictly prohibited and any storage of this document is not allowed unless with written permission from the publisher. All rights reserved.

The information provided herein is stated to be truthful and consistent, in that any liability, in terms of inattention or otherwise, by any usage or abuse of any policies, processes, or directions contained within is the solitary and utter responsibility of the recipient reader. Under no circumstances will any legal responsibility or blame be held against the publisher for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly.

Respective authors own all copyrights not held by the publisher.

The information herein is offered for informational purposes solely, and is universal as so. The presentation of the information is without contract or any type of guarantee assurance.

The trademarks that are used are without any consent, and the publication of the trademark is without permission or backing by the trademark owner. All trademarks and brands within this book are for clarifying purposes only and are the owned by the owners themselves, not affiliated with this document.

# Table of Contents

[Chapter 1 an Introduction to Java](#part0000_split_004.html__Toc464500244)

[History](#part0000_split_005.html__Toc464500245)

[Runtime and Performance](#part0000_split_006.html__Toc464500246)

[Syntax](#part0000_split_007.html__Toc464500247)

[Memory](#part0000_split_008.html__Toc464500248)

[Chapter 2 The Eight Primitive Types in Java](#part0000_split_009.html__Toc464500249)

[Characters](#part0000_split_010.html__Toc464500250)

[Boolean Expressions and Logic](#part0000_split_011.html__Toc464500251)

[Integers and Floating Point Numbers](#part0000_split_012.html__Toc464500252)

[Variables](#part0000_split_013.html__Toc464500253)

[Operators](#part0000_split_014.html__Toc464500254)

[Loops](#part0000_split_015.html__Toc464500255)

[Switch Case](#part0000_split_016.html__Toc464500256)

[Chapter 3: Arrays and Strings](#part0000_split_017.html__Toc464500257)

[Arrays](#part0000_split_018.html__Toc464500258)

[Strings](#part0000_split_019.html__Toc464500259)

[How to Format Java Strings](#part0000_split_020.html__Toc464500260)

[Chapter 4: Primitive VS Reference Types](#part0000_split_021.html__Toc464500261)

[User Datagram Protocol](#part0000_split_021.html__Toc464500262)

[Transmission Control Protocol](#part0000_split_021.html__Toc464500263)

[Internet Control Message Protocol](#part0000_split_021.html__Toc464500264)

[Address Resolution Protocol](#part0000_split_021.html__Toc464500265)

[Internet Protocol](#part0000_split_021.html__Toc464500266)

[Chapter 5: Object Oriented Programming](#part0000_split_022.html__Toc464500267)

[Chapter 6: How to make your own classes](#part0000_split_023.html__Toc464500268)

[Framework for Java Classes](#part0000_split_024.html__Toc464500269)

[Turning Classes into Pages](#part0000_split_025.html__Toc464500270)

[The Headings](#part0000_split_026.html__Toc464500271)

[Paragraphs](#part0000_split_027.html__Toc464500272)

[Images](#part0000_split_028.html__Toc464500273)

[Links](#part0000_split_029.html__Toc464500274)

[Elements](#part0000_split_030.html__Toc464500275)

[How to Quote Properly](#part0000_split_031.html__Toc464500276)

[Long Quote](#part0000_split_032.html__Toc464500277)

[Short Quote](#part0000_split_033.html__Toc464500278)

[Contact Information Quote](#part0000_split_034.html__Toc464500279)

[Java Plus CSS](#part0000_split_035.html__Toc464500280)

[Important Elements](#part0000_split_036.html__Toc464500281)

[Internal Styling (Internal CSS)](#part0000_split_037.html__Toc464500282)

[Inline Styling (Inline CSS)](#part0000_split_038.html__Toc464500283)

[External Styling (External CSS)](#part0000_split_039.html__Toc464500284)

[CSS Fonts](#part0000_split_040.html__Toc464500285)

[Chapter 7: Fields, Methods, and Constructors](#part0000_split_041.html__Toc464500286)

[Fields](#part0000_split_042.html__Toc464500287)

[Methods](#part0000_split_043.html__Toc464500288)

[Constructors](#part0000_split_044.html__Toc464500289)

[Destructors](#part0000_split_044.html__Toc464500290)

[Getting Peer Information](#part0000_split_044.html__Toc464500291)

[Network I/O Methods](#part0000_split_044.html__Toc464500292)

[Encapsulation](#part0000_split_046.html__Toc464500293)

[Abstraction Layers](#part0000_split_046.html__Toc464500294)

[Inheritance](#part0000_split_047.html__Toc464500295)

[Internet Model](#part0000_split_047.html__Toc464500296)

[Patterns](#part0000_split_047.html__Toc464500297)

[Stream Class](#part0000_split_047.html__Toc464500298)

[Polymorphism](#part0000_split_048.html__Toc464500299)

[Adding Directives](#part0000_split_049.html__Toc464500300)

[Adding Controllers](#part0000_split_050.html__Toc464500301)

[File Polymorphism and Controllers](#part0000_split_051.html__Toc464500302)

[Loading the Library](#part0000_split_052.html__Toc464500303)

[Chapter 9 Abstract Classes and Interfaces](#part0000_split_053.html__Toc464500304)

[Filters](#part0000_split_054.html__Toc464500305)

[Expression Filters](#part0000_split_055.html__Toc464500306)

[Currency Filters](#part0000_split_056.html__Toc464500307)

[Directive Filters](#part0000_split_057.html__Toc464500308)

[Filter Filter](#part0000_split_058.html__Toc464500309)

[More about Interface](#part0000_split_059.html__Toc464500310)

[JSON Object](#part0000_split_060.html__Toc464500311)

[Services](#part0000_split_061.html__Toc464500312)

[Chapter 10 Conditional and Control Flow Statements](#part0000_split_062.html__Toc464500313)

[Conditional Statements](#part0000_split_063.html__Toc464500314)

[Java Forms](#part0000_split_064.html__Toc464500315)

[Control Flow Statements](#part0000_split_065.html__Toc464500316)

[Chapter 11 Dealing with Errors and Exceptions](#part0000_split_066.html__Toc464500317)

[Understanding Acceptor Classes](#part0000_split_067.html__Toc464500318)

[Correcting Statements and Arguments](#part0000_split_068.html__Toc464500319)

[Debugging and Exception Handling](#part0000_split_069.html__Toc464500320)

[Conclusion](#part0000_split_070.html__Toc464500321)

[Bonus: Preview Of ‘SQL The Ultimate Beginners Guide Learn SQL Today](#part0000_split_071.html__Toc464500322)

[Thank you again for downloading this book!](#part0000_split_072.html__Toc464500323)

# Introduction

Known as one of the most useful, general purpose, object-oriented languages around, Java is one of the best programming languages that you could learn about—and even master, even if you're just a beginner!

With the help of this book, you would be introduced to what Java is about, its primitive types, data types, how object oriented programming actually works—and more!

Start reading this book now and you'll learn more about Java in no time!

Once again, thank you, and enjoy!

# Chapter 1 an Introduction to Java

More than anything, what you have to understand about Java is that it is a general purpose, object-oriented programming language—which means that it is easier to understand than other programming languages. It was designed primarily so that software developers could just code their programs once, and allow those programs run anywhere, or at least, in most platforms, as long as those platforms allow Java code to run in them.

Java primarily uses some of the same elements that C+ and C++ use, but transforms them into much simple, easy to understand versions that could also be modified depending on the developer’s preferences.

Java has also been created to run with enough runtime support, both for hardware and software, by means of representing each bytecode in a clear, and concise manner. For example, shih tzus, border collies, and terriers are all dogs—therefore, they could all be classified as dogs, and thus, not a lot of space would be taken up in the system, and the system would be able to work in a fast manner. This is also the reason why Java is one of the world’s most powerful, and most used programming languages of all time!

## History

The history of Java dates back to 1991 when programmers Patrick Haughton, Mike Sheridan, and James Gosling thought of a programming language that could best be used for the development of Digital TV. However, it was deemed to be way ahead of its own time, and thus, they redeveloped it based on the C+ and C++ platforms to make it easier and more economical to use.

With the redevelopment also came the core principles of Java, which are:

1.  It has to be portable—or that it should work on as many platforms as possible, without any of them not working as well as the other;
2.  It should be safe and secure to use—and definitely well encrypted;
3.  People should feel connected to it in as little time as possible, which means that they should be working with words that are somehow familiar to them, and even though it looks complex at first, sooner or later, they have to realize that it actually works;
4.  It should be dynamic, should work in threads, and could be modified when needed, and;
5.  It should perform with precision.

As you can see, these core principles give you the feeling that the programmers real made Java for the people—so they can enjoy using more programs without having to buy too many devices.

In 1995, Sun Microsystems finally released Java 1.0—the first public inception of Java, which had amazing security, no-cost runtimes, and file access restrictions across all networks. Over the years, 7 more Java releases had been made, and ever since 2006, Java started to be available through GNU, or General Public License—meaning it is now a free, open-source programming language. This stemmed from the public outcry that happened once when some of its contents were made private and only available for a fee, which definitely does not resonate with its core principles.

## Runtime and Performance

At first, Java did not run as fast as it should have, mostly because of the fact that the first couple of programs created from it required a bit more memory than those made from C+. However, over the years, its speed improved, and actually has gained better reputation in the industry than its peers.

Being a virtual machine in itself, Java now works with the so-called “just in time compilation” which makes it fairly easy to work with. Added support has also been given, so now, you can start making use of inner classes, arrays, assertions, string builders, and the like, alongside better optimization, too.

## Syntax

Of course, you would be learning more about this later but what you have to realize now is that in Java Programming, classes encapsulate all of the codes—so they coup be coherent with one another, and would be able to co-exist, and all of which would be considered as their own data items. However, primitive data types, such as characters, Boolean values, integers, etc.—which you'll be learning about in the next chapter—are excluded in this as they know how to stand on their own.

You'd also notice the following signs to be mostly used in the syntax: double slash(//), commenting style, or asterisks and slashes (/**) (*/), and multiple line style, or (/*)(*/).

When creating a program in Java, you should save the file as .java, with child pages saved as .class. If you want to keep a certain child page, or class, private, all you have to do is save it in the same Java folder, and not in its own class folder so others won't have access to it.

A sample few lines of Java syntax are as follows:

Program HiWorld (

Public static.void (

System out PrintIn.HiWorld

)

))

You have to take note, though, that making the class public gives the program the capacity to be used in other platforms. So, unless the program is still in its development stages, and you do not want it to be accessed yet, it's best to make sure that you make it public just so you could test it out, too. After all, by using the keywords “void” and “static”, you'd get to male sure that others won’t be able to edit or modify the app.

## Memory

Another reason why Java works fast is because it makes use of Automatic Memory Management, which means that runtime won't be affected by what the programmer chooses to add or subtract from what he's trying to create.

Now, what happens is that when there are no more references to a certain object, it would no longer be considered as part of the program, and won't be using a lot of memory, too—making the program easier to manage altogether.

It's now time to learn more about Java—read the next chapters, and understand how this works!

# Chapter 2 The Eight Primitive Types in Java

As mentioned earlier, there are eight primitive, or original data types in Java programming. Here they are, and what you should know about them.

## Characters

Characters compose the first primitive types of Java. Basically, these are the words that you should be using while creating your program. These also encompass a lot of things, and these are…

1.  If. This executes block codes, and includes (else and elif)
2.  While. This is used for true conditions, and also executes block codes.
3.  For. This is used for attached blocks.
4.  Try. This is handled by except and allows raised exceptions for code blocks.
5.  With. This makes use of block managers, and helps open and close files.
6.  Def. This means that a method or function is defined.
7.  Class. This executes block codes and is used for object-oriented programming.
8.  Print/ Print(). This is used for printing.
9.  Import. This is used to import modules from other functions.
10.  Yield. This is used to generate function values and is also used as an operator.
11.  Assert. This is used to check statements that are meant to be applied.
12.  Pass. This is used to create empty code blocks.

Take note that these keywords cannot be used as variables!

Indentation and Lines

The number of spaces and words used would determine whether what you have programmed is right, or if it would generate errors:

Take a look at the two examples below. The first one is right, while the other generates an error because of the un-indented print command at the last line.

Example 1:

 if True:

    print "True"

else:

  print "False"

Example 2:

if True:

    print "Answer"

    print "True"

else:

    print "Answer"

  print "False"

Quotations

To create quotations in this program, take note that you could use single (‘), double, (“) or triple (“” “”) notes to indicate strings and literal strings.

For example:

word = 'word'

sentence = "This is a sentence."

paragraph = """This is a paragraph. It is

made up of multiple lines and sentences."""

Multiple Line Statements

Automatically, the end of commands determine the start of new lines, but if you want to continue your own lines, you can use back-slash (\) to do so, except for when you’re using brackets.

Example 1:

total = item_one + \

        item_two + \

        item_three

Example 2:

days = ['Monday', 'Tuesday', 'Wednesday',

        'Thursday', 'Friday']

Comments

To create comments, just use hashtag (#)—this really sounds like it’s social-media friendly, huh? For example:

Example 1:

#!/usr/bin/java

# First comment

print "Hello, Java!" # second comment

Example 2:

# This is a comment.

# This is a comment, too.

# This is a comment, too.

# I said that already.

Waiting for the User

At time when you want to create prompts that would tell the user you’re waiting for his command, you can try:

#!/usr/bin/java

raw_input("\n\nPress the enter key to exit.")

Individual Statement Groups

Groups of Individual Statements are called Suites in Java Language. Basically, you have to begin with keywords and end them with colons (:), so, for example:

if expression :

   suite

elif expression :

   suite

else :

   suite

The above command will then give you suites!

## Boolean Expressions and Logic

Next up is Boolean Logic. In this, values are reduced to either true or false and are made use of in the Binary Numbering System. In short, they help make the program make its own decisions. For example:

>>> front_sensor_on = True

>>> front_sensor_on

True

What you have to keep in mind is that Boolean Logic determines an exact outcome—something specific that you’d want to see. Whereas there is the Square of Opposition for Philosophical Logic, there is also the Boolean Logical Square. An example of which is below:

| a | b | a== b | a!= b | A and b | A or b | not b |
| --- | --- | --- | --- | --- | --- | --- |
| False | False | True | False | False | False | True |
| False | True | False | True | False | True | True |
| True | False | False | True | False | True | False |
| True | True | True | False | True | True | False |

An explanation of the chart is below.

Logical “And”

As you can see, there is an expression above that says a and b. Remember that this’ll only happen if a and b both have the same true value, which means derivative could be true—and false, in every other case.

Here’s an example:

a and False == False

False and a == False

B and a == a and b

A and True == a

True and a== a

A and a == a

Logical Equivalence

Logical Equivalence or a==b happens when a and b both have same true value, and could either be true or false; otherwise, they have different values and not the same core.

Logical “or”

Next, you see a table that says a or b. This tests whether both are true, or only one variable is true. When both a and b are true, the value also returns as true—and nothing else.

For example:

a or False == a

False or a == a

B or a== a or b

a or True == True

True or a == True

a or a  == x

Logical Negation

Basically, Logical Negation means two variables have the ability to cancel each other. For example:

not (not a) == a

Conditional Execution

There’s also such a thing as conditional execution, or the means to change behavior and check conditions that affect the program’s behavior. This makes use of the If Statement. Here’s a good example:

if x % 2 == 0:

    print(x, " is even.")

    print("Did you know that 2 is the only even number that is prime?")

else:

    print(x, " is odd.")

    print("Did you know that multiplying two odd numbers " +

                                         "always gives an odd result?")

This’ll give you this result:

f BOOLEAN EXPRESSION:

    STATEMENTS_1        # Executed if condition evaluates to True

else:

    STATEMENTS_2        # Executed if condition evaluates to False

Chained Conditionals

Else If/ If Else are important in this conditional. Here’s an example:

if choice == "a":

    function_one()

elif choice == "b":

    function_two()

elif choice == "c":

    function_three()

else:

    print("Invalid choice.")

Nested Conditionals

There are also Nested Conditionals which basically mean that conditionals could stay on top of the other. For example:

if x < y:

    STATEMENTS_A

else:

 if x > y:

        STATEMENTS_B

 else:

        STATEMENTS_C

You can also simplify this by doing the following:

if 0 < x:            # Assume x is an int here

 if x < 10:

        print("x is a positive single digit.")

Remember that print can only be used once it passes both of the conditionals, which means:

if 0 < x and x < 10:

    print("x is a positive single digit.")

Omitting Else Clause

The Else Clause could also be omitted if a condition is evaluated as true. For example:

if x < 0:

    print("The negative number ",  x, " is not valid here.")

    x = 42

    print("I've decided to use the number 42 instead.")

print("The square root of ", x, "is", math.sqrt(x))

The Return Statement

You also have the return statement, which gives you back a value whether the operation is void or not.

def print_square_root(x):

 if x <= 0:

        print("Positive numbers only, please.")

 return

    result = x**0.5

    print("The square root of", x, "is", result)

## Integers and Floating Point Numbers

Of course, you can expect that integers and floating point numers are used to store numerical values, and this is why they are also grouped together. Assign your preferred numbers to the variables. For example:

var1 = 1

var2 = 10

You can also make use of the following numerical types:

1.  Int (signed integers)
2.  Complex (complex numbers)
3.  Float (floating real point values)
4.  Long (long integers; could be hexadecimal and octal)

To give you a better idea, here is a sample of those numerical values:

| int | long | float | complex |
| 100 | -0x19323L | 15.20 | 45.j |
| 080 | 0xDEFABCECBDAECBFBAEl | 32.3+e18 | .876j |
| 10 | 51924361L | 0.0 | 3.14j |
| -0x260 | -052318172735L | -32.54e100 | 3e+26J |
| 0x69 | -4721885298529L | 70.2-E12 | 4.53e-7j |
| -0490 | 535633629843L | -90. | -.6545+0J |
| -786 | 0122L | -21.9 | 9.322e-36j |

Also, make sure that you use an uppercase L so that the program would not think if lowercase l as the number 1\.

You can also use commas to assign single values in a synchronized manner. For example:

a = b = c = 1

## Variables

Next, it’s time for you to learn Java Variables.

Before you go and wonder what Variables are, what you have to know is that they’re basically means to store memory values—which means you’re using the program to determine where to keep what you have. Here, you’ll be using a lot of decimals, integers, and various kinds of characters, too!

Before learning the commands, here is a crash course on Data Type Conversion first.

Data Type Conversion

1.  Int (x [,base]). If x is a string, it becomes the base; also converts x to an integer.
2.  Float (x). Converts integers into floating numbers.
3.  Long (x [,base]). Converts x to long integers.
4.  Str (x). converts x to string representation.
5.  Complex (real [,imag]). This gives you a complex number.
6.  Eval (str). This evaluates a string and gives you an object in return.
7.  Repr (x). Converts x to repression string.
8.  Set (s). Converts x to set.
9.  List (L). Converts x to list.
10.  Tuple (t). Converts x to tuple.
11.  Frozen set (s). Converts x to frozen set.
12.  Dict (d). This gives you a dictionary.
13.  Oct (x). Converts x to octal string.
14.  Hex (x). Converts x to hexadecimal string.
15.  Ord (x).This gives a single character its integer value.
16.  Unichr (x). And finally, with this command, you’ll get a Unicode character.

Value Assignation

The equal sign (=) is important here because. You do not need to make explicit declarations here but you have to make sure that you place the variable before the equal sign, and on the right, put what you want to happen to the variable. For example:

#!/usr/bin/java

counter = 100          # An integer assignment

miles   = 1000.0       # A floating point

name    = "John"       # A string

print counter

print miles

print name

This would then give you the result of:

100

1000.0

John

## Operators

Then, you also have Java Operators. These manipulate operand values, and could be categorized as:

1.  Arithmetic
2.  Assignment
3.  Identity
4.  Membership
5.  Bitwise
6.  Logical
7.  Comparison/ Relational

Arithmetic Operators

Here are the arithmetic operators that you can use:

1.  + Addition. Of course, this adds values on your operators ( a + b = 15)
2.  –Subtraction. This subtracts the operand on the right from the one on the left. (a – b = -10)
3.  /Division. This divides operand on the left with what’s on the right. (b/a = 2)
4.  *Multiplication. Multiples whatever you have. (a * b = 200)
5.  // Floor Division. With this, you’d get quotient results, especially when decimal points are removed. (9//2 = 4) (9.0//2.0 = 4.0)
6.  **Exponent. This helps you derive exponential notation. (a**b = 5 to the power of 10)
7.  % Modulus. Divides operand on the left by the right and provides remainder. (b% a = 0)

Assignment Operators

1.  =. Gives value to what’s on the right side back to the left operand. (c = a + b assigns value of a + b into c)
2.  -=Subtract AND. This subtracts the operand on the right from the left operand and assigns results to what’s on the left. (c -= a is equivalent to c = c – a)
3.  +=Add AND. This adds the operand on the right to the left and gives left operand result. (c += a is equivalent to c = c + a)
4.  /=Divide AND. Divides left with right operand and assigns value to the left. (c /= a is equivalent to c = c / ac /= a is equivalent to c = c / a)
5.  *=Multiply AND. Multiplies right operand with left operand and assigns result to left operand. (c *= a is equivalent to c = c * a)
6.  **=Exponent AND. Derives exponential notation. (c **= a is equivalent to c = c ** a)
7.  %=Modulus AND. Takes modulus of two operands. (c %= a is equivalent to c = c % a)
8.  // Floor Division AND. With this, you’d get quotient results, especially when decimal points are removed. (c //= a is equivalent to c = c // a)

Identity Operators

These compare memory of two locations of two different objects.

1.  Is. Determines whether variables on either side are true; if not, operator points to the same subject. (x is y, here is results in 1 if id(x) equals id(y).)
2.  Is not. If variables on either side are false, operator points to the subjects and says true-wise. (x is not y, here is not results in 1 if id(x) is not equal to id(y).)

Membership Operators

These check whether there is membership or coherence in a certain sequence.

1.  Is. Checks whether variables on each side are true. (x is y, here is results in 1 if id(x) equals id(y).)
2.  Not in. Checks if a variable is not in a specified sequence and evaluates to either true or false. (x not in y, here not in results in a 1 if x is not a member of sequence y.)

Bitwise Operators

These perform bit by bit operation. For example:

a = 0011 1100

b = 0000 1101

-----------------

a&b = 0000 1100

a|b = 0011 1101

a^b = 0011 0001

~a  = 1100 0011

Logical Operators

Logical Operators are basically items that hold 10 to 20 variables in between them.

Comparison Operators

1.  ==. Condition equates to true if the operands are equal. ((a==b) is not true)
2.  <>. If values are not equal, condition becomes true. ((a<>b) is true)
3.  !=. Condition becomes true if values of two operands are not equal.
4.  <=. Condition becomes true if left operand value is less than the right operand. (a <=b) is true)
5.  >=. Condition becomes true if value of left operand is greater than right operand. (a>=b) is not true)
6.  <. If left operand value is less than right operand, condition is true. (a < b) is true)
7.  >. If value of left operand is greater than right, condition is true. ((a>b is not true)

## Loops

Loops are statements that provide various actions that could be used in your program. These include:

1.  For Loop. This helps you execute statements a number of times and also abbreviates codes that are used in the variable.
2.  While Loop. This repeats statements or groups of statements that you want to use again in your program.
3.  Nested Loop. This means that you’re using one or more loops in your program.
4.  Do…While Loop. This is equivalent to a statement but is seen by the program as a condition.
5.  Goto Statement. This gives control to the statement that has already been labeled.
6.  Continue Statement. This helps the loop skip the remainder of the body—so it wouldn’t be around when it’s unnecessary.
7.  Break Statement. This terminates the switch and loop statements and helps execute the other statements in the program after you have made one of the loops.

## Switch Case

And of course, if you want to test variables, you have to make use of switch cases—also known as switch statements. There are certain rules that you have to follow, though, and these are:

1.  Switch statements could also be default cases. Therefore, they have to appear at the end of the switch and could be used to determine false statements in the program. In this case, you wouldn’t have to use a break anymore.
2.  You don’t need a break for every case. In case no break appears, all you have to do is wait for something to fall through.
3.  When you have reached the break statement, go ahead and change the terminates that you have been using so that you could then jump to the next line.
4.  Constant Expression should be used. This means you have to use the same data types in your program.
5.  Every switch contains a number of case statements that could be separated with colons.
6.  You could use enumerated or integral types of switches so that class conversion could easily be done.

For this, you have to remember that:

ExpressionCase 1 Code Block 1

 Case 2 Code Block 2

 Case 3 Code Block 3

And so on. In short, you could take note of the example below:

#include <mylistofgrades>

int main () {

   /* local variable definition */

   char grade = 'D';

   switch(grade) {

      case 'E' :

         printf("Amazing!/n" );

         break;

      case 'E' :

      case 'D' :

         printf("Great Job!\n" );

         break;

      case 'D' :

         printf("You did well!\n" );

         break;

      case 'F' :

         printf("Try again next time\n" );

         break;

      default :

         printf("Invalid grade\n" );

   }

   printf("Your grade is  %c\n", grade );

   return 0;

}

# Chapter 3: Arrays and Strings

In Java, arrays and strings help make sure that whatever will appear onscreen—or on the finished program are certainly what the programmer, or you, in this case, want to express .

In coding the Java language, you of course have to make use of expressions. These are written in double braces {{}}, but could also be contained within a directive, just like this one below:

Ng-bind= “expression”

The expression will then be resolved by Java itself, and have results returned when they are ready. They pretty much mirror JavaScript expressions, so if you know something about that, this language would not be too hard for you.

This also means that Java Expressions are:

1\. Java Expressions could contain filters—but JavaScript expressions do not have them.

2\. They do not support exceptions, loops, and coordinates.

3\. The expressions could be written inside HTML.

4\. Java Expressions could also be variables, operators, and literals.

For example:

{{ 10 + 5 }} or {{ name + " " + nickname }}

This means that a basic Java expression code would look like the following:

<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>

<div ng-app="">
  <p>Supergirl Versus Bizarro: {{ Supergirl +Bizzaro }}</p>
</div>

</body>
</html>

By taking away the ng directive, HTML would not be able to solve the expression, but just show it as it is, which would just basically look the same as this:

<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>

<div ng-app="">
  <p>Supergirl Versus Bizarro: {{ Supergirl +Bizzaro }}</p>
</div>

</body>
</html>

Another example would be if you want to change certain colors and styles in CSS. For example, if you want to change the color of a box as pink, you could try the following:

<div ng-app="" ng-init="myCol='pink'">

<input style="background-color:{{myCol}}" ng-model="myCol" value="{{myCol}}">

</div>

## Arrays

This works like JavaScript Arrays. If you’re going to use ng-bind, it would look something like this one below:

<div ng-app="" ng-init="points=[2,4,6,8]">

<p>The third result is <span ng-bind="points[2]"></span></p>

</div>

But, if you’re going to take away ng-bind, it would look something like this one:

<div ng-app="" ng-init="points=[2,4,6,8]">

<p>The third result is {{ points[2] }}</p>

</div>

## Strings

Strings connect things together, even in programming. Java Strings also work like JavaScript. It could go two ways—just take a look at the examples below:

<div ng-app="" ng-init="firstName='Mark';lastName='Ruffalo'">

<p>The name is <span ng-bind="firstName + ' ' + lastName"></span></p>

</div>

Or:

<div ng-app="" ng-init="firstName='Mark';lastName='Ruffalo'">

<p>The name is {{ firstName + " " + lastName }}</p>

</div>

## How to Format Java Strings

Some people think that Java Strings are utterly complex to work with. However, you don't really have to be afraid  of them. When it comes to formatting Java Strings, here's what you have to know…

Working Strings

The first thing you have to realize is that there are certain elements known as Java Working strings.

Java Working Strings are basically quote-enclosed characters. With these, single quotes are considered the same as double quotes, so you can expect that:

var1 = 'Hello World!'

var2 = "Java Programming"

Accessing Values

Remember that character types are not accepted as Java Language. You have to use square brackets [] to access substrings. For example:

#!/usr/bin/java

var1 = 'Hello World!'

var2 = "Java Programming"

print "var1[0]: ", var1[0]

print "var2[1:5]: ", var2[1:5]

When you input those commands, you’d get a result of:

var1[0]:  H

var2[1:5]:  ytho

You could also update strings by doing the following:

#!/usr/bin/java

var1 = 'Hello World!'

print "Updated String :- ", var1[:6] + 'Java'

That will then give the following result:

Updated String :-  Hello Java

Unicode Strings

There are also Unicode strings or 8-bit ASCII that you can keep as 16-bit Unicode. For example:

#!/usr/bin/java

print u'Hello, world!'

Basically, this’ll give you:

Hello, world!

Triple Quotes

You can also make use of triple quotes which could cover multiple lines, tabs, and even new lines. For example:

#!/usr/bin/java

para_str = """this is a long string that is made up of

several lines and non-printable characters such as

TAB ( \t ) and they will show up that way when displayed.

NEWLINEs within the string, whether explicitly given like

this within the brackets [ \n ], or just a NEWLINE within

the variable assignment will also show up.

"""

print para_str

This’ll be the result that you’d get when you input the syntax above:

this is a long string that is made up of

several lines and non-printable characters such as

TAB (    ) and they will show up that way when displayed.

NEWLINEs within the string, whether explicitly given like

this within the brackets [

], or just a NEWLINE within

the variable assignment will also show up.

Special Codes and Characters

In order to program those, you have to make use of special characters and codes. These are:

Built-in String Method

1.  Center (width, fillchar). Along with the original string, this’ll give you a space-padded string consuming the total width of the columns.
2.  Capitalize(). This basically capitalizes the first letter of the string.
3.  Encode (suffix, beg=0, end=len(string)). This runs an encoded version of each string.
4.  Decode (encoding UTF-8, errors=strict). The codec registered for encoding will be used for this method, and you’d get a default string.
5.  Count (str, beg=0, end=len(string)). This counts the number of times a string appears and begins indexing.
6.  Find (str, beg=0, end=len(string)). This checks whether str is on string or on subsequent string.
7.  Expandtabs (tabsize = 8). Strings and tabs are then placed in multiple spaces.
8.  Isdecimal(). If Unicode string contains decimal characters, value returns as true; false otherwise.
9.  Zfill (width). Left-pads original string with zeros.
10.  Upper (). Turns lowercase letters into uppercase.
11.  Translate (table, deletechars=””) Turns string into translation table.
12.  Title (). Turns string into titlecard version, which means uppercase becomes lowercase and vice-versa.
13.  Swapcase (). All letters in the string will be inverted.
14.  Strip ([chars]). Performs rstrip() and Istrip() on each string.
15.  Startswith (str, beg=0, end=len (string)). Checks whether string is string itself or subset of string.
16.  Splitlines (num=string.count(‘\n’)). Returns each of the line with new strings.
17.  Split (str=””, num=string.count (str)). Splits the strings into delimeters.
18.  Rjust (width, [,fillchar]). This gives you space-padded strings.
19.  Rindex (str, beg=0, end=len(string)). This is just like index but with backward string.
20.  Replace (old, new [max]). This replaces current string with max occurrences.
21.  Max (str). This returns max character alphabetical string.
22.  Join (seq). This merges representations of the strings.

Format Symbols and their Functions

%X              hexadecimal integer (UPPERcase letters)

%x              hexadecimal integer (lowercase letters)

%u              unsigned decimal integer

%s              string conversion via str() prior to formatting

%o              octal integer

%i              signed decimal integer

%g              the shorter of %f and %e

%G              the shorter of %f and %E

%f              floating point real number

%E              exponential notation (with UPPERcase 'E')

%e              exponential notation (with lowercase 'e')

%d              signed decimal integer

%c              character

Other Important Symbols

1.  m.n.              m is the minimum total width and n is the number of digits to display after the decimal point (if appl.)
2.  0.              pad from left with zeros (instead of spaces)
3.  <sp>.              leave a blank space before a positive number
4.  +.              display the sign
5.  *.              argument specifies width or precision
6.  (var).              mapping variable (dictionary arguments)
7.  %.              '%%' leaves you with a single literal '%'
8.  #.              add the octal leading zero ( '0' ) or hexadecimal leading '0x' or '0X', depending on whether 'x' or 'X' were used.
9.  -. left justification

Using the right keywords

You also have to remember that formatting strings becomes easier when you simply make use of the right keywords, and these are…

1\. Auto. This is used to define storage class variables. For example:

auto int var1;

2\. Char. This is used to indicate the value of the variable; sometimes called type character.

Char variable09

3\. Switch, case and default. This is a group of statements that denote the variable’s expression and could also be used as a default value. For example:

switch(switch in this area){

    case 'A':

    //some statements to execute when A

    break;

    case 'B':

    //some statements to execute when B

    break;

    default:

    //some statements to execute when default;

}

4\. Break and continue. This is used for enclosing loops so you could jump out of them and so you could continue with the next statement easily. This is also used to skip some elements in the same loop.

for (i=1;i<=1;++i){

    if (i==2)

       continue;

    if (i==8)

       break;

    printf("%d ",i);

}

5\. Const. This means constant, which means that there is a constant value in the program. For example:

const int a=10;

6\. Double and Float. This is used to indicate float type variables and are used for respective data. For example:

Float thisvariable

Double thisvariable

7\. Do and While. This is used for looping the C Program. Here’s an example:

i=7;

while (i<7) {

    print("%d ",i)

    i++;

}

That will then give you the following output: 0 2 4 6 7 9

8\. Extern. This denotes that external variables are around and is accessed and declared through different functions. For example:

#include <myfavoriteprogram>

extern i=8;

void print1(){

    printf ("%d ",i);

}

int main() {

    printf("%d ",i);

}

return 0;

}

9\. Enum. As the name suggests, this is used to enumerate certain parts of the program. This consists of constant integers. For example:

enum enum_var{

   var4;

   var5;

   var6;

};

10\. If and Else. These two go together and is usually used for decision-making purposes. For example:

if (i==2)

printf("i is 2.")

else

prinf("i is not 2.")

11\. Goto. This is used for labeled statements for unconditional jumps. For example:

for(i=1;i<6;++i){

if (i==10)

    goto error;

}

printf("i is not 9");

error:

   printf("Error, count can't be 9");

12\. For. This is used for C Loops. Here’s an example:

for (i=0;i<1;++i){

     printf("%c ",i);

}

13\. Short, long, unsigned. These are mostly used for integers, and for this, you have to take note of the following ranges:

Short int (-32768 to 32767)

Unsigned int ( 0 to 655355)

Signed int (-32768 to 32767)

Long int (-32768 to 32767)

14\. Sizeof. This is used to determine the size of something on your program. Here’s an example:

#include <stdio.h>

int main(){

    printf("%u bytes.",sizeof(char));

}

15\. Return. This terminates the current function’s execution and gives some value back to the function itself. For example:

int func(){

int b=10;

return c;

}

16\. Static. This is used to indicate the storage class’ value and could be used until you reach the end of the program. For example:

Static int var;

17\. Register. This is something that differentiates normal variables from fast ones. For example:

Register int var1;

18\. Typedef. This helps you differentiate simple numbers from integers. For example:

Typedef float ab;

Ab butterfly, wings

19\. Struct. This is used to create structures so they could easily be managed. For example:

struct contestant{

char name[1116];

float marks;

int age;

}s2,s3;

20\. Void. This means that a part of your program has no value. For example:

void no_return(int a){

.....

}

21\. Union. Union is about handling the variables. This is what you have to do:

union student {

char name[100];

float marks;

int age;

}

22\. Volatile. This means that you have an erroneous function in your program. This is what you have to do:

const volatile number

There are also special characters that you can use, and these are:

, <> . _ () ; $ : % []# ? ‘ & {} “ ^ ! * /|-\~+

As for digits, you can use the following:

0 1 2 3 4 5 6 7 8 9

You can also use uppercase or lowercase alphabet letters, as well.

# Chapter 4: Primitive VS Reference Types

Earlier, you learned about the primitive or independent data types in Java. You also have to know, though, that there are also things called reference types, and just like primitive ones, these are also in different categories and could do a lot of things—but have to be supported by primitive data.

Are primitive data types better than those in the reference category? Not entirely. While Primitive types could stand on their own, there are certain things that reference data types can do that can make the program that you are trying to make a whole lot better.

What exactly are these types?

User Datagram Protocol

This is an important member of the Internet Protocol Suite. It provides connectionless transmissions in such a way that they could actually be reliable, and that they would not ruin the protocol of the network in any way. They are perfect for time-sensitive applications that easily drop pockets. User Diagram Protocols are also:

1\. It is capable of providing datagrams to the network;

2\. It is transaction-oriented and work for both Network Time Protocols and Domain Name Systems;

3\. It works with unidirectional communication, which is suitable for service discoveries and broadcast information;

4\. It works for real-time applications (such as Twitter, Snapchat, Periscope, etc.) because it makes way of transmission delays. It also works for VOIP applications (such as Skype), and works for some games, as well;

5\. It is suitable for a large number of clients, and is stateless. It also works for streaming applications, and;

6\. It’s perfect for bootstrapping because it is simple and stateless.

It also works for Octets 0 to 4, and even 20 to 160 in some cases.

Transmission Control Protocol

This provides error-checked, orderly, and reliable stream of octets between the IP Network and the various networks that it contains. This is used for email, and most of the World Wide Web, as well. This is also a latent, connectionless protocol, and works by processing data that has already been transmitted. It works from octets 0 to 160, containing source and destination ports. It also contains sequence numbers, and acknowledgment numbers.

Data Offset is also reserved, together with window size, checksum, and urgent pointers, as well.

Basically, what you can keep in mind is:

1\. 16 bits identify the source port;

2\. 16 bits also identify the receiving port;

3\. 4 bits specify the data header in 32-bit words;

4\. 32 bits identify the acknowledgment numbers;

5\. 9-bits contain the 9-bit flags;

6\. 3 bits define data that is reserved for future use.

Other bits define options that you could create for your app or website using this programming language.

Internet Control Message Protocol

Another important protocol of JAVA, this one could send requested services and messages to the router, and also has its own protocol number. The difference is that it starts in the IPv4 Header, and is mostly just known as ‘1’. It also works between octets 0 to 4, where:

1\. Code = Control Messages | ICMP Subtype

2\. Type = Control Messages | ICMP Subtype

3\. Rest of Header = Contents | ICMP Subtype

4\. Checksum = Error Checking Data | ICMP Header and Data

Data then derives a section in IPv4 where error-checking is done. Implementations are also accessible through APIs and various kinds of sockets, together with Network Discovery Protocols and microcontroller firmware.

Address Resolution Protocol

As the name suggests, this is a telecommunications protocol that makes it easy for communication apps and websites to work. It is used to map network addresses, making messaging—and even video calls—possible, and has also been used for important technologies, such as Xerox PARC Universal Packet, DEC Net, ChaosNet, and IPv4, amongst others. For this, you could keep in mind the following:

1\. 0 – Hardware Type (HTYPE)

2\. 2 – Protocol Type (PTYPE)

3\. 4 – Hardware Address (HLEN) | Protocol Address (PLEN)

4\. 6 – Operation (OPER)

5\. 8 – Sender Hardware Address (SHA)

6\. 10 - Next 2 succeeding bytes

7\. 12 – Last 2 succeeding bytes

8\. 14 – Sender Address Protocol (SAP)

9\. 16 – last 2 succeeding bytes

10\. 18 – Target Hardware Address (THA)

11\. 20 – next 2 succeeding bytes

12\. 22 – last 2 succeeding bytes

13\. 24 – Target Protocol Address (TPA)

14\. 26 – last 2 succeeding bytes

Internet Protocol

And finally—and also the one that’s closely related to JAVA, Internet Protocol is all about providing boundaries in the network, as well as relaying datagrams that allow internet-networking to happen.

The construction involves a header and a payload where the header is known to be the main IP Address, and with interfaces that are connected with the help of certain parameters. Routing prefixes and network designation are also involved, together with internal or external gateway protocols, too. Reliability also depends on end-to-end protocols, but mostly, you could expect the framework to be this way:

Data Application

UDP Header | UDP DATA Transport

IP Header | IP Data Internet

Frame Header | Frame Data | Frame Footer Link

# Chapter 5: Object Oriented Programming

If you may recall, it's been said early on that Java is a type of programming language that’s object-oriented, which means that it deals with the creation, and use of data types, strings, arrays, lists, numbers, and all these things that could make a program better—and it's not just the usual letters or numbers that you wouldn't understand.

Since Java is an object-oriented language, you can expect that it will work because—and for—the following reasons:

One Source of Truth

Otherwise known as the “Single Source of Truth”, this means that the whole app is stored in a tree’s object that is then placed in a single store. With this, creating apps becomes easy, and debugging, together with introspection, also becomes easy. Certain functions—such as undo/redo—becomes trivial. It uses the following codes:

console.log(store.getState())

  visibilityFilter: 'SHOW_ALL',

  todos: [

      text: 'Keep all state in a single tree',

      text: 'Consider using Java',

      completed: true,

      completed: false

/* Prints

    }

  ]

}

*/

Read-Only State

Another thing that Java does is that it makes sure that the app has this “read-only” state. With this, action gets to be emitted, which means that mutation begins to happen, which also means that all mutations would be centralized, and that you’d just have to watch out for certain race conditions as they happen in a strict order. This state is also important for testing purposes.

This uses the following codes:

store.dispatch({

  type: 'SET_VISIBILITY_FILTER',

  type: 'COMPLETE_TODO',

store.dispatch({

  index: 1

  filter: 'SHOW_COMPLETED'

})

})

Pure Functions are used to Make Changes

In order to make sure that actions transform the object tree by making use of reducers, which are pure functions that take the previous type of actions and states, and could then return the next kind of state that’s listed.

Basically, you could work with one reducer first, and watch the number grow as you make various changes for your app. For this, the following codes have to be used:

function visibilityFilter(state = 'SHOW_ALL', action) {

          text: action.text,

  switch (action.type) {

  switch (action.type) {

        return todo

      return state.map((todo, index) => {

      return state

      return state

          return Object.assign({}, todo, {

      return action.filter

      return [

        if (index === action.index) {

function todos(state = [], action) {

    default:

    default:

            completed: true

          completed: false

    case 'SET_VISIBILITY_FILTER':

    case 'COMPLETE_TODO':

    case 'ADD_TODO':

          })

      })

        ...state,

let store = createStore(reducer)

let reducer = combineReducers({ visibilityFilter, todos })

import { combineReducers, createStore } from 'Java'

# Chapter 6: How to make your own classes

In Java, classes are important because they determine what happens to your program, in general. Thus, it is no surprise that there are a lot of elements that come into play in making Java classes, and making sure that they would actually work. Basically, it all starts with the framework.

## Framework for Java Classes

The framework of a Java class is made up of the following:

1\. The program type is described with the UNICODE declaration.

2\. Program information is provided in the text between <HEAD> and </HEAD>.

3\. An Java Program is described in the text between <Java> and </Java>.

4\. The program’s title is provided in the text between <TITLE> and </TITLE>.

5\. The text between <H1> and </H1> are known as headings. It could also go for H2, H3, H4, and so on.

6\. The content of the program—or what you’d read onscreen—goes on the text between <BODY> and </BODY>.

7\. And, a paragraph could then be created in the text between <p> and </p>

Tags Cheat Sheet

Now, when it comes to tags, you have to keep in mind that they usually come in pairs, as you have seen in the framework above. What’s on the left side is the beginning of the tag (also known as start tag), and the end tag looks almost the same—but only with a slash (/) in the beginning.

Here are the tags that you’re mostly going to use:

<UNICODE…>

NAME – this pertains to a section on the page

HREF – this is used for hyperlinking, or for adding the name of the URL that you are referring to

onCLICK – this is the script that runs so that the user will be able to click on the anchor (i.e., for things such as [google.com](http://google.com), this script has to run so that the user would really be directed to a link after clicking)

<A> Anchor

TITLE – this is the title of the program that is being opened

onMOUSEOUT – this is the script used to determine that the mouse is no longer on the anchor text

TARGET – This shows the window where the program has to go into. Variations include: “parent” | “black” | “top” | “shelf” | window name

onMOUSEOVER – this shows that the mouse is right over the anchor text

<ADDRESS>

<App…>

CODEBASE – this is the path that would take you to the applet class

CODE – this determines the app that is currently running

HEIGHT – the height of the applet

WIDTH – this determines the applet’s width

ALIGN – this would determine how the surrounding text would show up onscreen

<APPLET…>

HSPACE – this is the horizontal space between the surrounding text and the applet

VSPACE – this is the vertical space between the surrounding text and the applet

NAME – this is the name given to an applet and is also the name used by other applets that are referencing it

BORDER – this is the empty space that surrounds the applet

ARCHIVE – this is a collection of the components of the applet that have been compressed into one

HREF – this determines the URL that you are linking to

MAYSCRIPT – This shows whether Java can use JavaScript or not

ALT – this is the alternate text used for when the image has not been properly displayed

SHAPE – this determines the shape of the area that’s shown onscreen. It could either be one of the following: POLY | RECT | CIRCLE | DEFAULT

COORDS – these determine the coordinates for the shapes in the link area

<AREA…>

TARGET – this determines the frame that you have to go to

TITLE – this is a short description of the area being used

onCLICK – this script should run while the user is hovering on the anchor text

NOHREF – this means that there are no links contained in a certain area

<b> BOLD

<BASE> Base Address

<Base Front>

              TARGET - This shows the window where the program has to go into. Variations include: “parent” | “black” | “top” | “shelf” | window name

              SRC – this determines audio or sound URL

              FACE – the typeface or font of the project

              COLOR – this is the color of the typeface

              SIZE – font size that is being used

<BG Sound>

              LOOP              - this determines the number of times audio or video is being played

<FORM>

              ENCTYPE – this is the type of form being used on the page

              onRESET – this is the script that should run if the form is being reset

              SRC – this is the type of file that has to be added to the frame

              onSUBMIT – this should run while the form is being submitted

              SCROLLING – this determines whether the form should use a scrollbar or not (answerable with YES or NO)

              MARGINWIDTH – this determines the width of the form’s margins

              MARGINHEIGHT – this determines the height of the form’s margins

              ROWS – the number of rows in the frame

              COLS – the number of columns in the frame

<HEADERS: H1, H2, H3, H4, H5, H6>             

 NOSHADE – this means that the shadow effect should not be used

              COLOR – the color of the line

<iFrame> inline frame

ALT – this would show up onscreen in the event that the image doesn’t

LONGDESC – this is a long description of the image that is being used

SUPPRESS – this means that the image’s icons won’t show up until it’s downloaded

MEDIA – this determines the type of media that is being linked to. It could be one of the following: PRINT | PROJECTION | SCREEN | ALL | BRAILLE | AURAL

TYPE –  this is the kind of link resource that’s being used

BEHAVIOR – the type of scrolling used

GUTTER – this determines the space between the columns

<OL> Ordered List

              VALUE – this determines the value of the option that the user is choosing

              START – this shows you where you have to start counting

              ALIGN – this means that you want to align the paragraph whether to the left or the right

              LANGUAGE – this is the scripting language used (Java, CSS, etc)

              BG – the background color used

              BACKGROUND – the picture you want to use as the background of the page

              BORDERCOLOR – the color of the border on the page

TYPE – the type of bullets used. This could be one of the following: SQUARE | CIRCLE | DISC

## Turning Classes into Pages

Now it’s time to start creating a full basic Java page just to see how it looks like. Again, remember that every Java page or program should start with <!UNICODE Java>. This means that it has to look something like this:

<!UNICODE Java>
<Java>
<body>

<h1>Welcome to the Web</h1>

<p>My first page</p>

</body>
</Java>

Take note that declarations would differ depending on the Java type that you’re using. This means that you have to do the following:

1\. XJava 1.0:  <!UNICODE Java PUBLIC "-//W3C//DTD XJava 1.0 Transitional//EN" "http://www.w3.org/TR/xJava1/DTD/xJava1-transitional.dtd">

2\. Java 4.01:  <!UNICODE Java PUBLIC "-//W3C//DTD Java 4.01 Transitional//EN" "http://www.w3.org/TR/Java4/loose.dtd">

3. Java 5:  <!UNICODE Java>

## The Headings

Of course, your pages need headings. These work like subheadings in books or articles so you’d know exactly what goes on in a page—what it’s about, in other words.

Headings range from <H1> to <H6>. Here’s a good example:

<h1>Look at my heading</h1>
<h2>Look at my heading</h2>
<h3>Look at my heading</h3>

<h4>Look at my heading</h4>
<h5>Look at my heading</h5>
<h6>Look at my heading</h6>

## Paragraphs

Paragraphs are also used in webpages as well as in articles and novels. You’ll know that a paragraph is around when the <p> tag is in. This also makes it easier for you to read what’s on the page.

Without the use of paragraphs, everything would be cramped in one space along—making them extremely hard to read. For this, you could try the following:

<p>Read this paragraph.</p>
<p>Read one more paragraph.</p>

## Images

Images could also be used to spruce up your website. It makes people want to read the website more because images always makes things easy on the eyes. This means you’d have to use the <img> tag for this.

The attributes of this are as follows:

1\. alt (alternate text)

2\. src (image source)

3\. size (width and height)

For example:

<img src="chanel1.jpg" alt="chanel2" width="104" height="142">

## Links

And of course, the use of links is also encouraged. These are defined with the <a> tag. It makes things easy on the eyes so that everything wouldn’t be on one page alone, and readers could be taken to different pages on your website.

Here’s a good example:

<a href="http://thechanels.com">See this link</a>

## Elements

Various elements are also used in an Java page. If you could remember, pairs of tags are always used in a webpage that’s been coded with Java.

It should look something like this:

<tagname>tagname</tagname>

For example:

<h1> Read this heading </h1>

<p> Have you seen the light? </p>

<b><p>What is feminism?</b></p>

So basically, the whole program is depicted through various <Java> tags, and that’s why start <> and end </> tags have to be used. Without them, words on the page would all come together—making them hard to read. The <body> tag then defines what the page contains. It also contains headings, paragraphs, and other attributes.

For example:

<Java>
<body>

<h1>My Sunday</h1>
<p>Last Sunday was the best Sunday because we went to the park and flew kites.</p>

</body>
</Java>

With the help of start and end tags, you get to understand what’s being shown onscreen. They give a page a lot of meaning—instead of it being just mumbo-jumbo.

Other important elements are the headings <h1>, and paragraphs </p> so that headings could also be defined. A sample of headings are as follows:

<h1> See how awesome this is </h1>

<h2> Have you seen where she went? </h2>

<h3> Where will you go next? </h3>

<h4> what will you watch? </h4>

<h5> what are you listening to? </h5>

<h6> what are you going to eat? </h6>

In between those headings, you could write what you have in mind—which then would give the webpage a better, more believable look! For example:

<h1> See how awesome this is </h1>

<p> I see how awesome this is and I like it </p>

<h2> Have you seen where she went? </h2>

<p> No, I have no idea where she went </p>

<h3> Where will you go next? </h3>

<p> I’m planning to go to Chicago, then maybe do a side trip to New York to catch a show on Broadway </p>

<h4> what will you watch? </h4>

<p> Lion King or Cats </p>

<h5> what are you listening to? </h5>

<p> I’m listening to the new Selena Gomez record. So far, so good </p>

<h6> what are you going to eat? </h6>

<p> I’m going to eat some omelet and buttered vegetables </p>

See how much of a difference that makes?

You should also keep in mind that there are such things as empty Java elements. This basically pertains to the br tag <br> which also depicts a line break. It’s pretty much like a space, if you’re goiung to think of articles or books.

For example:

<h1> See how awesome this is </h1>

<br></br>

<p> I see how awesome this is and I like it </p>

<h2> Have you seen where she went? </h2>

<br></br>

<p> No, I have no idea where she went </p>

<h3> Where will you go next? </h3>

<br></br>

<p> I’m planning to go to Chicago, then maybe do a side trip to New York to catch a show on Broadway </p>

<h4> what will you watch? </h4>

<br></br>

<p> Lion King or Cats </p>

<h5> what are you listening to? </h5>

<br></br>

<p> I’m listening to the new Selena Gomez record. So far, so good </p>

<h6> what are you going to eat? </h6>

<br></br>

<p> I’m going to eat some omelet and buttered vegetables </p>

Also, you have to remember that while tags are not case-sensitive, it’s still better to use lowercase tags especially in Java 4 and 5—which are commonly used these days. This way, you’d avoid problems from happening to your page.

## How to Quote Properly

There are times when you do have to quote certain things on your page. For example, if you have something to attribute to another website, it’s best to not twist their words so that your readers would get a really valuable read, and know that you know how to link to the right sources.

For this, you have to remember the following:

1. <q>. This means that there’s a short, inline quotation.

2\. <cite>. This is attributed to the title of a topic on the page.

3\. <blockquote>. This means that you have quoted something from outside sources.

4\. <bdo>. This states for text dictation.

5. <address>. This is the contact information quote.

6. <abbr>. acronym or abbreviation

## Long Quote

For example, you have created a new website for fostering and taking care of animals, and you are affiliated to the WWF (World Wildlife Fund). This means you may have to quote from their website. How would you do this?

Well, you can use the Long Quote Style. This is depicted by <blockquote>, which would then indent the passage. So, if you have quoted this way:

<p>Here is a quote from WWF's website:</p>
<blockquote cite="http://www.worldwildlife.org/who/index.Java">
For 50 years, WWF has been protecting the future of nature. The leading conservation organization in the world,
WWF works in over 100 countries and is supported by all
1.2 million members in the US and
close to 5 million globally.
</blockquote>

What you’d see onscreen is something like this:

Here is a quote from WWF's website:

For 50 years, WWF has been protecting the future of nature. The world's leading conservation organization, WWF works in 100 countries and is supported by 1.2 million members in the United States and close to 5 million globally.

## Short Quote

For short quotes, you could try using <q>. For example:

<p>ABC123’s Goal is to: <q>Build a future where people know how to code without problems, and create the websites they want.</q></p>

## Contact Information Quote

If you’re observant, you’d know that a lot of websites make use of the Contact tab where you get to see contact information of the owner of the website. For this, you could use the Java <address> code. This is usually seen in italic with line breaks.

For example:

<address>
Written by Blair Waldorf </br> 
Visit us at:<br>
blaircornelia.com<br>
New York, New York<br>
USA
</ be easy to get information from search engines, translation systems, and other browsers. For this, you could try the example below:

<p>The <abbr title="World Wide Web">WWW</abbr> was founded in 1989.</p>

## Java Plus CSS

And of course, if you want to make sure that your classes would look more appealing to the eyes, then you have to know how to make use of CSS Styles, top. Basically, here's what you have to do…

There are 3 important CSS elements and they are:

1\. Internal. This means that you’re using an element of <style> and you could find this in the Java <head> section.

2\. Inline. This depicts Java style attributes.

3\. External. This means that you’re using external CSS Files.

## Important Elements

1\. Style. Internal Styling

2\. CSS Margin. Space outside the border

3\. CSS Padding. Space inside the border

4\. CSS Font-Size. This determines text sizes

5\. CSS Font-Family. This determines where the font came from

6\. CSS Color. This determines the color of font being used

7\. <head>. This refers to elements of <link> and <style>

8\. <link>. A link to external CSS files

9\. <style>. The style of internal CSS

## Internal Styling (Internal CSS)

This means that you’re trying to define the style of a single page in your website. You can see this in the <head> of your page. It encapsulates the element of <style>.

For example:

<!UNICODE Java>
<Java>
<head>
<style>
body {background-color:white;}
h1   {color:pink;}
p    {color:violet;}
</style>
</head>
<body>

<h1>Read this heading</h1>
<p>Read this paragraph </p>

</body>
</Java>

## Inline Styling (Inline CSS)

Inline styling then means that you have to apply unique styles to single elements in your page. This also falls under the Java Style Attribute. For example, if you want to change the color of <h1> heading to pink, you could try:

<h1 style="color:pink;">This is a Pink Heading</h1>

## External Styling (External CSS)

External CSS is mostly about defining style for a couple of pages in your website—not just one page alone. With the help of just one file, you could already change the entire look of your website—which really makes things easy for you.

Then, you could just add a link to the External CSS sheet in the <head> part of your page. For this, you could try the example below:

<!UNICODE Java>
<Java>
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<h1>Read this heading </h1>
<p>Read this paragraph.</p>

</body>
</Java>

## CSS Fonts

Finally, in order to easily change fonts, make sure that you know how to differentiate elements. Color determines the Java text color in the page, font-size is all about the size of font used, and font-family defines which family the font came from (i.e., serif, sans serif, etc.)

<!UNICODE Java>
<Java>
<head>
<style>
h1 {
    color: blue;
    font-family: serif;
    font-size: 100%;
}
p  {
    color: red;
    font-family: courier;
    font-size: 120%;
}
</style>
</head>
<body>

<h1>Read this heading</h1>
<p>Read this paragraph.</p>

</body>
</Java>

Now that you know the basics, you could finally create your own website!

# Chapter 7: Fields, Methods, and Constructors

Next, it's time for you to learn about certain elements that could strengthen the program that you are trying to develop, and these are fields, methods, and constructors.

## Fields

Fields basically are just the scopes that Java encompass.  With these fields come terms that would help you understand what they're really about. By knowing these terms, it would be easy for you to know what you’re dealing with—and coding wouldn’t ever be a problem.

For this, you could take note of the following terms:

Ng-bind. This means that DOM element texts are being set. This means that the value of the name would be seen inside the span element. Any changes made to the name would directly reflect on other elements of the DOM. For example:

<span ng-bind="name"></span>

Ng-app. This derives the Java ’s root element so that behavior and directives would be defined, as well.

Ng-model-options. This allows updates for the model to be done by means of fine tuning.

Ng-model. This is almost the same as Ng-bind so that there’d be a bond between the scope and the view.

Ng-controller. This means that HTML expressions are evaluated with the help of the JavaScript controller class.

Ng-class. These are dynamically-loaded class attributes.

Ng-show and Ng-hide. This shows or hides the elements conditionally, which always depends on the Boolean expression formula. This could be achieved by using CSS styles.

Ng-repeat. This instantiates elements for a collection at least once.

Ng-view. This is responsible for handling ON routes for the base directives which are also specified by certain controllers.

Ng-switch. This helps you choose from a set of templates depending on the values of the expressions.

Ng-animate. This helps provide enough support for CSS3 Keyframe, CSS3 Transition, and JavaScript. This also provides enough custom and core directives, together with animation keyhooks, too.

Ng-aria. This one creates common ARIA attributes, and also serves as a module of accessibility and support.

Arguments = Scopes

In Java Programming, Scopes are equivalent to arguments. This happens because scopes bind JavaScript and HTML Element, which means that at some point, there would be some form of conflict, too.

Scopes have available methods and abilities, and are available for both controller and the view. The view depicts HTML, while controller is JavaScript—which is the one responsible for controlling, editing, or deleting data.

Scopes are also models with both properties and methods available for the user to use. It means that when changes are made, both controller and view will be affected—and updated.

Here are some examples:             

<div ng-app="TheHungerGames" ng-controller="myCtrl">

<h1>{{TheHungerGames}}</h1>

</div>

<script>

var app = Java .module('myApp', []);

app.controller('movies', function(Rscope) {
    Rscope.thehungergames= "TheHungerGames";
});

</script>

              <div ng-app="TheHungerGames" ng-controller="myCtrl">

<input ng-model="thehungergames">

<h1>Movie is {{thehungergames}}</h1>

</div>

<script>

var app = Java .module('myApp', []);

app.movies('myCtrl', function(Rscope) {
    Rscope.name = "thehungergames";
});

</script>

Rooting Mechanisms

There’s also such a thing as Rooting Mechanism (also known as $rootscope). This uses the ng-app directive and is available for the whole application—so you can say that it’s a really important part of the tutorial. This also uses the scope that’s currently used.

For example:

<body ng-app="TheFirstApp">
<p>The rootScope's favorite color:</p>
<h1>{{pink}}</h1>
<div ng-controller="myCtrl">
    <p>The scope of the controller's favorite color:</p>
    <h1>{{purple}}</h1>
</div>
<p>The rootScope's favorite color is still:</p>
<h1>{{pink}}</h1>
<script>

var app = Java .module('TheFirstApp', []);
app.run(function($rootScope) {
    $rootScope.color = 'pink';
});
app.controller('myCtrl', function(Rscope) {
    Rscope.color = "purple";
});

</script>
</body>

Limiting Areas

You also should understand where the scopes begin, and when they end. This will make your program more coherent, and help you understand what needs to be done. It’s like knowing what’s going on around you so you could easily deal with them. This is not usually an issue unless you’re dealing with large DOM Applications. The ng-repeat directive is essential for this one.

For this, you could follow the code below:

<div ng-app="TheFirstApp" ng-controller="myCtrl">

<ul>
    <li ng-repeat="x in thefirstapp">{{x}}</li>
</ul>

</div>

<script>

var app = Java .module('TheFirstApp', []);

app.controller('myCtrl', function(Rscope) {
    Rscope.names = ["the", "first", "app"];
});

</script>

## Methods

Meanwhile, and as the name suggests  methods are about the actions you should take in filling up those fields, and making sure that your program would be as coherent and as well out, as possible.

Methods, in Java, are known as information payloads that are responsible for sending data from the application to its own store, which could then be sent with the syntax store.dispatch () and are known to be plain JavaScript objects, and that is why the type property has to be used, and that types should then be considered as string constants. If you have an app that’s already large enough, it can then be moved to a separate module.

However, you have to keep in mind that methods don’t have to be depicted in separate files. In fact, you might not even have to define them at all, but you do have to declare their codebases, and understand the right type of syntax to be used.

For example:

const ADD_TODO = 'ADD_TODO'

  type: SET_VISIBILITY_FILTER,

  type: ADD_TODO,

  text: ‘Welcome to My First App’

  filter: SHOW_COMPLETED

}

}

Action Creators

True to the name, Action Creators are the kind of functions that are able to create methods, or have methods returned to the user. They create valuable dispatches when invoked, and promote bound methods.

Dispatches or dispatch () is something that you could directly access from the store, and provide connection between Java and the reader, also known as Java-reader collect. These action creators could also have certain side effects, which are also known as methods of synchronicity and AJAX Responses.

Here’s a sample proper code:

function addTodo(text) {

    type: ADD_TODO,

    type: ADD_TODO,

    text

    text

  return {

function addTodoWithDispatch(text) {

dispatch(completeTodo(index))

dispatch(addTodo(text))

  dispatch(action)

const boundCompleteTodo = (index) => dispatch(completeTodo(index))

const boundAddTodo = (text) => dispatch(addTodo(text))

  const action = {

boundCompleteTodo(index)

boundAddTodo(text)

  }

}

Source Code

To code this properly, do make use of the following source code:

/*

* action types

*/

  SHOW_COMPLETED: 'SHOW_COMPLETED',

  SHOW_ALL: 'SHOW_ALL',

  SHOW_ACTIVE: 'SHOW_ACTIVE'

  return { type: TOGGLE_TODO, index }

  return { type: SET_VISIBILITY_FILTER, filter }

  return { type: ADD_TODO, text }

export function toggleTodo(index) {

export function setVisibilityFilter(filter) {

export function addTodo(text) {

export const VisibilityFilters = {

export const TOGGLE_TODO = 'TOGGLE_TODO'

export const SET_VISIBILITY_FILTER = 'SET_VISIBILITY_FILTER'

export const ADD_TODO = 'ADD_TODO'

}

* other constants

* action creators

## Constructors

And of course, there are also constructors that help connect everything, bind them together, and make your program work effectively even with different elements involved.

Constructors allow the connect() method to happen and to be prevalent in the program. This contains the names of the IP, together with the hosts and is usually returned to the sender, or caller. To code, just follow what you see below:

#include <netinet/in.h>

#include "Javastream.h"

class FirstJavaConnector

{

  public

    JavaStream* connect(int port, const char* server);

  private:

    int resolveHost(const char* host, struct in_addr* addr);

};

You also have to take note that connected to the descriptor of the socket that allow peer Java Ports and peer IP Addresses to show up onscreen. Take note that this does not use other languages, except for C++, unlike its contemporaries in Java.

For this, you have to use the following syntax:

JavaStream::getPeerIP()

JavaStream::getPeerPort()

To code, just follow what you see below:

#include <arpa/inet.h>

#include "newJavastream.h"

JavaStream::JavaStream(int sd, struct sockaddr_in* address) : msd(sd) {

    char ip[50];

    inet_ntop(PF_INET, (struct in_addr*)&(address->sin_addr.s_addr),

              ip, sizeof(ip)-1);

    m_peerIP = ip;

    m_peerPort = ntohs(address->sin_port);

}

Destructors

Destructors are then able to close any connections that you have made. For example, if you want to log out of one of your social networking accounts, you’re able to do it because destructors are around. To code, just follow what you see below:

JavaStream::~JavaStream()

{

    close(m_sd);

}

Getting Peer Information

In order to get peer information, you have to make sure that you return both Java and IP information. This way, you could be sure that both server and client are connected to the network. You could also use the getpeername() socket so that when information is available, it could easily be captured and saved.

To accept information, let the socket JavaAcceptor::accept() be prevalent in the network. This way, you could differentiate actions coming from the server and the client.

Network I/O Methods

For this, you have to use the syntax JavaStream::send() or JavaStream::receive(). This way, you could easily know the number of bytes that are being sent and received and you could expect that buffering wouldn’t happen—and would not be a problem.

Chapter 8 Encapsulation, Inheritance, and Polymorphism

There are also Java elements that help determine how your program could be edited, and how it would appear when seen by others. These also encompass the depth of the program—or its heart, in other words. You can learn more about these below:

## Encapsulation

First up is encapsulation, which makes use of a coupe of principles to be executed well. These Principles are:

1\. Robustness Principle. This means that protocols have to be implemented but sending behavior has to be conservative, while receiving behavior should definitely be liberal. This means that you have to be careful in sending/receiving datagrams. It means that even if some software has deficiencies, it’s still important to make sure that you do not exploit its obscure protocols.

2\. End-to-end Principle. This is one of those principles that continuously evolves. Overall intelligence and state are important for maintaining this expression, and it’s also essential for network address translators, firewalls, and in managing content caches, as well.

Now, in order to provide Java with its much-needed abstraction layers, Encapsulation is done. It is aligned with the protocol suite’s functional division so that each level would be properly encapsulated and dealt with.

Take a look at the diagram below for you to understand how the process works:

First HostRouter Router  Second Host

Application –Process to Process—Application

Transport – Host to Host – Transport

Internet – Internet – Internet – Internet

Link – Link – Link – Link

Ethernet – Fiber Satellite – Ethernet

Take note that whatever is on top of the layer are those that are closely used in the user applications themselves. However, there is no single architectural model that has to be followed, especially when you have less-defined models such as the OSI model. This is its main difference from other internet protocols, especially the earlier ones. Encapsulation then covers the 4 Abstraction Layers which are as follows:

Abstraction Layers

First, take a look at the data below:

Data Application

UDP Header | UDP DATA Transport

IP Header | IP Data Internet

Frame Header | Frame Data | Frame Footer Link

What this means is that:

Application Layer

The Application Layer encapsulates the protocols used by services that provide exchanging applications. This also includes host configuration protocols, routing services and network support services. Examples include File Transfer Protocol (FTP), Hypertext Transfer Protocol (HTTP), and Dynamic Host Configuration Protocol (DHCP). This way, you would be able to lower data transfer based on the protocols you are using.

Application layer also treats the Transport Layer as a stable network with black boxes that allow communication to happen all throughout the application, while making sure that key qualities of each part of the application still work as strong as they can. Whatever happens to the Application Layer does not concern the Transport and Internet layers because traffic does not usually examine the said layer. However, sometimes, it is essential for the NAT, or Network Address Translator, to consider the payload of the application—and make sure that things are running smoothly.

Transport Layer

The Transport Layer contains the channels of data that are involved in Java, which also establishes process-to-process connectivity and end-to-end message transfers that provide the right information and logistics for any specific purpose in the network. This could either be implemented, connectionless, or object-oriented.

The port is then established with the help of the transport layer where logical constructs are around. It basically means that:

1\. Data should be correct—and could only have minimal error;

2\. Data should arrive in order;

3\. Data should include traffic congestion control;

4\. Packets that are discarded or lost have to be resent, and;

5\. Duplicate data has to be discarded.

When that happens, you could expect even the newest version of the Stream Control Protocol to work properly in your network. You don’t have to rely on connectionless datagrams, though, because as the name suggests, they don’t offer the right connections—and are quite unreliable.

Internet Layer

Basically, the Internet Layer works in such a way that it holds responsibility over sending the right packets, and making sure that they could move across several networks. Its main functions are:

1. Packet Routing. This is all about sending packets of data from the destination’s source, all the way to where it needs to be used. Unique Protocol Numbers identify these.

2\. Host Identification and Addressing. With the help of a hierarchical IP System, this one is achieved.

Link Layer

The networking methods are defined within the link layer. The scope is the intervening routers, together with the host network, including the protocols that are being used to describe the topology of the network, and datagrams are also evident with various goals and assumptions together with strict layering. This means that you can implement Java above any hardware network technology.

With the help of the link layer, packets could easily be moved and could receive driver card packets, and it also means that the layer corresponds to the OSI model.

## Inheritance

Then, there's also inheritance that describes what each class would inherit or how they would relate to their parent pages.

What you have to understand about Java is that it is an Open System Interconnect (OSI) Internet Model which means that it works in inheritance (). In order to establish connections, you need to make use of listening inheritance so that the host could make calls—or in other words, connections.

By inputting listen (), the user will be able to accept () blocks on the program. This binds () the program together and makes it whole. For this, you could keep the following in mind:

Client: socket()connectwrite()read() close()

Establish connections: connect accept()

Send Request: write() read()

Receive Reply: write() read()

Close Connection: close() read()

Server: socket()bind()listen()accept()read()write() read()

As you can see, you’re able to connect one with the other because you have established the proper inheritance—also known as roles—in your program.

Internet Model

Now, to make things clearer, you have to understand the basic model of the internet.

The Internet Model combines session, presentation, and application of layers and the ports of the Java, making way of bind() to happen. Now, you also have to wait from the response from both the sender and the receiver. This makes it easy for the exchange of requests and messages to be done until the connection is closed. When done properly, the sender and receiver won’t have to worry about messages getting unsent, or communications getting cut.

Connections could then be contained in just one thread so that it would not be too complicated for the network to understand. This way, the right Protocol Stacks could be created, too. Therefore, it would have to be this way:

OSI Model: ApplicationPresentationSessionTransportNetworkDatalink Physical

Internet Model: ApplicationTransportNetwork Network Link

Internet Protocols: HTTPS, HTTPS, DNS, SSH, POP3, FTP, NNTP, TelNet, IMAPJava, UDPIP, ICMP, ARP, DHCP Ethernet, ADSL, PPP

Patterns

Now, you also have to keep the following patterns in mind:

1\. Java Stream. This is responsible for providing I/O mechanisms to the network and also provides peer addresses, as well.

2. Java Acceptor. This allows passive acceptance of the Java mechanisms from a factory class all the way to the client. It establishes connections to the client.

3\. Java Connector. This allows mechanisms to connect to the socket so there’d be a good relationship between the servers.

Stream Class

To start programming, you could begin with the Stream Class. This provides the right data to be sent and received by various methods involved in Java, and also contains proper socket descriptors and grants privileges to others in the program. Some may even be deemed private, to make the experience better for the users.

To code, you could follow what’s written below:

#include <sys/types.h>

#include <sys/socket.h>

#include <unistd.h>

#include <string>

using namespace std

class JavaStream

{

    int     m_sd;

    string  m_peerIP;

    int     m_peerPort;

  public:

first class JavaAcceptor;

first class JavaConnector;

    ~JavaStream();

    ssize_t send(char* buffer, size_t len);

    ssize_t receive(char* buffer, size_t len);

    string getPeerIP();

    int getPeerPort();

  private:

    JavaStream(int sd, struct sockaddr_in* address);

    JavaStream();

    JavaStream(const JavaStream& stream);

};

## Polymorphism

Basically, Java Polymorphism are the ones that define applications, and serve as containers for different parts of the application. They also serve as containers for various application controllers, and they always belong to Polymorphism.

In order to create a module, you have to make use of the Java.mobile function. What’s inside the parenthesis would then determine the element where the application would run in, so that you could add filters, directives, and controllers to the application. An example is shown below:

<div ng-app="FavoriteApp">...</div>
<script>
var app = Java.module("FavoriteApp", []); 

</script>

## Adding Directives

Now, you could add directives to improve the functionality of the app you are trying to create. Directives are pretty much the terminologies given in Chapter 2, but could also be any of the following:

1\. Validation Properties, such as: $error, $invalid, and $dirty.

2\. Java.isDate. Returns value if date is the reference.

3\. Java.isArray. Pertains to array values.

4. Java.isNumber. Pertains to numerical values.

5\. Java.isFunction. Pertains to functional values.

6\. Java.isElement. Pertains to DOM Elements.

7\. Java.isDefined. Pertains to references that are defined.

8\. Java.equals. Pertains to equal values on the program.

9\. Java.isUndefined. Pertains to undefined reference values.

10\. Java.isObject. Pertains to object references.

11. Java.forEach(). This helps elements execute various functions whether in arrays, or objects.

12. Java.Copy(). This gives you deep copies of arrays or objects.

13\. Java.uppercase(). This changes values to uppercase letters

14. Java.lowercase(). This changes values to lowercase letters

15\. <textarea>. Modifies the text area’s behaviors.

16. <select>. Helps you create selections on the program.

17\. <script>. This modifies the behavior’s script.

18\. <input>. This helps you input different functions to the program.

19\. <form>. This helps you create forms in the program.

20\. <a>. This one helps input various variables in the program.

21\. Java.module(). This helps you create, retrieve, or register Polymorphism.

22\. Java.element(). This makes use of JQuery Elements to wrap the HTML Element with.

23\. Java.bootstrap(). This manually starts Java JS.

You could also use your own directives, which means the code would look something like the one below:

<div ng-app="FavoriteApp" w3-test-directive></div>
<script>

var app = Java.module("FavoriteApp", []);

app.directive("w3TestDirective", function() {
    return {
        template : "I was made in a directive constructor!"
    };
});

</script>

## Adding Controllers

Of course, you could also add controllers to your codes by using the ng-controller directive. Basically, it would show up like this:

<div ng-app="FavoriteApp" ng-controller="myCtrl">
{{ AppFirstName + " " + ApplastName }}
</div>
<script>

var app = Java.module("FavoriteApp", []);

app.controller("myCtrl", function($scope) {
    $scope.firstName = "Harry";
    $scope.lastName = "Styles";
});

</script>

## File Polymorphism and Controllers

Then, you could create Polymorphism and controllers inside the files so that your applications would even be more defined. For this one, you could copy what’s shown below:

<!DOCTYPE html>
<html>
<script src="http://ajax.googleapis.com/ajax/libs/Javajs/1.4.8/Java.min.js"></script>
<body>
<div ng-app="FavoriteApp" ng-controller="myCtrl">
{{ firstName + " " + lastName }}
</div>
<script src="FavoriteApp.js"></script>
<script src="myCtrl.js"></script>
</body>
</html>

## Loading the Library

To load the Java Library, you have to load it before the <head> and before the <body> tag.

For this, you have to use the Java.module directive and you’d get something like the one below:

<!DOCTYPE html>
<html>
<body>
<script src="http://ajax.googleapis.com/ajax/libs/Javajs/1.4.8/Java.min.js"></script>

<div ng-app="FavoriteApp" ng-controller="myCtrl">
{{ AppfirstName + " " + ApplastName }}
</div>

<script>
var app = Java.module("FavoriteApp", []);
app.controller("myCtrl", function($scope) {
    $scope.firstName = "Harry";
    $scope.lastName = "Styles";
});
</script>

</body>
</html>

# Chapter 9 Abstract Classes and Interfaces

Meanwhile, there are also abstract classes and interfaces that are more complicated, bit more detailed versions of classes. What they do is they help make your program just tad bi more secure. After all , if all classes and programs were the same, then it would be hard to protect it from hacking or phishing of any kind.

When it comes to classes and interfaces, here's what you've got to understand…

## Filters

No, this has nothing to do with adding filters to your photos to spruce them up. Filters give your applications more life—give them some form of body and soul—and could allow you to code what you want to happen to the app. This means you have to use the following variables:

1. uppercase. This helps you format a string to uppercase letters.

2\. orderBy. This arranges the array based on the expressions used.

3. number. This helps format numbers into strings.

4\. lowercase. This then formats the string into lowercase letters.

5\. limitTo. This one limits strings or arrays into characters or elements that have been specified for them.

6\. json. This helps format objects into JSON Strings.

7. filter. This helps you select subsets from arrays.

8\. date. This helps format dates into formats that you have specified for them.

9\. currency. This then helps you format currency numbers.

## Expression Filters

The pipe character (|) is used to add expressions inside filters. For this, you could try the examples below:

<div ng-app="myFavoriteApp" ng-controller="personCtrl">

<p>The name is {{ firstName | uppercase }}</p>

</div>

<div ng-app="myFavoriteApp" ng-controller="personCtrl">

<p>The name is {{ lastName | lowercase }}</p>

</div>

## Currency Filters

Now, you could try transforming a number into currency by making use of currency filters, such as the one you see below:

<div ng-app="myFavoriteApp" ng-controller="costCtrl">

<h1>How Much: {{ price | currency }}</h1>

</div>

## Directive Filters

Of course, you could also tweak your directives by making use of directive filters. The ng-repeat directive is essential here, as well as the pipe (|).

For example, if you want your variables to be in order, you should use orderBy, and code like this:

<div ng-app="myFavoriteApp" ng-controller="namesCtrl">

<ul>
  <li ng-repeat="x in names | orderBy:'hogwartshouses'">
    {{ x.name + ', ' + x.hogwartshouse }}
  </li>
</ul>

</div>

## Filter Filter

Wait, what?

Well, this is actually a thing! What happens here is that you’re allowed to choose a subset from a certain array, but you have to take note that you can only use what you have chosen for the same array. For example:

<div ng-app="myFavoriteApp" ng-controller="namesCtrl">

<ul>
  <li ng-repeat="x in names | filter : 'i'">
    {{ x }}
  </li>
</ul>

</div>

## More about Interface

Java Interface, also known as $java, is essential because it helps you get and read data from remote servers. Not only that, it also allows responses to be sent to you—making the process a two-way, understandable experience.

You also have to make use of certain methods which are as follows:

1\. .put()

2\. .post()

3\. .patch()

4\. .jsonp()

5\. .head()

6\. .get()

7\. .delete()

In order to make a simple request to the server, you could try this could below:

<div ng-app="myFavoriteApp" ng-controller="myCtrl"> 

<p>Welcome to my Blog:</p>
<h1>{{Welcome to my Blog}}</h1>

</div>

<script>

var app = Java.module('myApp', []);
app.controller('myCtrl', function($scope, $java) {
    $java.get("welcome.htm")
    .then(function(response) {
        $scope.myWelcome = response.data;
    });
});

</script>

To use the given methods above, you could code something that looks like the one below:

var app = Java.module('myApp', []);
app.controller('myCtrl', function($scope, $java) {
    $java({
        method : "GET",
        url : "welcome.htm"
    }).then(function mySucces(response) {
        $scope.myWelcome = response.data;
    }, function myError(response) {
        $scope.myWelcome = response.statusText;
    });
});

There are also certain properties that have to be observed if you want to code HTTP or services. These are the ones listed below:

1\. .statusText. This is a string that defines the HTTP Status.

2\. .status. This is a number that defines the HTTP Status.

3\. .headers. This function is used to get information regarding the function.

4\. .data. This is an object or string that carries server responses.

5\. .config. This is used to generate requests from the objects you have onscreen.

To understand this better, you could check out the examples below:

var app = Java.module('myFavoriteApp', []);
app.controller('myCtrl', function($scope, $java) {
    $java.get("welcometomyblog.htm")
    .then(function(response) {
        $scope.content = response.data;
        $scope.statuscode = response.status;
        $scope.statustext = response.statustext; 
    });
});

var app = Java.module('myFavoriteApp', []);
app.controller('myCtrl', function($scope, $java) {
    $java.get("wrongfilename.htm")
    .then(function(response) {
        //First function handles success
        $scope.content = response.data;
    }, function(response) {
        //Second function handles error
        $scope.content = "Something is wrong";
    });
});

## JSON Object

Meanwhile, the JSON Object is all about how you could transport data from JavaScript to Java, and vice-versa. The ng-repeat directive should be looped for this function. For example, you want to import data from a Blogspot blog to a WordPress one, it means that you are making use of a JSON Object.

You should also take note that $java.get() is all about reading the JSON Data, while $java() is mostly about the XMLHttpRequestObject. Here’s a good example:

<div ng-app="myFavoriteApp" ng-controller="studentsCtrl"> 

<ul>
  <li ng-repeat="x in myData">
    {{ x.Name + ', ' + x.house }}
  </li>
</ul>

</div>

<script>

var app = Java.module('myApp', []);
app.controller('studentsCtrl', function($scope, $java) {
    $java.get("students.php").then(function(response) {
        $scope.myData = response.data.records;
    });
});

</script>

## Services

It’s also important to use services because they allow certain functions to be limited only for your application so other people would not go ahead and copy them, and have you dealing with copyright claims.

There are a lot of services that Java offers, but the most important one is $location. This allows you to save certain objects to the cloud and keep them safe, so that even if your computer or external drives break down, you know your data would still be around—which is important especially if you’re dealing with programs and applications. Here are some examples:

var app = Java.module('myFavoriteApp', []);
app.controller('studentsCtrl', function($scope, $location) {
    myUrl = $location.absUrl();
});

You could also use the $timeout service or window.setTimeout to help you create countdowns—these are mostly used for events, shows, and the like. For example:

var app = Java.module('myFavoriteApp', []);
app.controller('myCtrl', function($scope, $timeout) {
    $scope.myHeader = "Hi People!";
    $timeout(function () {
        $scope.myHeader = "How are you doing today?";
    }, 2016);
});

Meanwhile, the $java service could be used to obtain data coming from the server. Here’s a good example:

var app = Java.module('myFavoriteApp', []);
app.controller('myCtrl', function($scope, $java) {
    $java.get("welcometomyblog.htm").then(function (response) {
        $scope.myWelcome = response.data;
    });
});

You could also try customizing your services by doing the following:

var app = Java.module('myFavoriteapp', []);
app.controller('myCtrl', function($scope, $timeout) {
    $scope.myHeader = "Hi everyone!";
    $timeout(function () {
        $scope.myHeader = "How are you doing today?";
    }, 2000);
});

var app = Java.module('myFavoriteapp', []);
app.controller('myCtrl', function($scope, $interval) {
    $scope.theTime = new Date().toLocaleTimeString();
    $interval(function () {
        $scope.theTime = new Date().toLocaleTimeString();
    }, 1010);
});

app.controller('myCtrl', function($scope, hexafy) {

    $scope.hex = hexafy.myFunc(255);

});

app.service('hexafy', function() {
    this.myFunc = function (x) {
        return x.toString(16);
    }
});

app.filter('myFormat',['hexify', function(hexify) {
    return function(x) {
        return hexify.myFunc(x);
    };
}]);

app.controller('myCtrl', function($scope, hexafy) {
    $scope.hex = hexafy.myFunc(259);
});

# Chapter 10 Conditional and Control Flow Statements

## Conditional Statements

You know how sometimes, you tend to want to edit you program and give it a more personal touch? Well, Conditional Statements certainly help out with that.

The thing about conditional statements is that somehow, they give you the capacity to truly make the program your own, and for that matter, here are some of those things that you can do to make the program work the way you want it to.

## Java Forms

Of course, there are also times when you need to add forms to your website or application so you could get information from your subscribers, just to make sure that they are not spambots. For this, the following input elements are used:

1\. text area elements

2\. button elements

3\. select elements

4\. input elements

You should also take note of the following:

1\. Ng-click is used to invoke the reset () method directly but only when the user clicks the button.

2\. The reset () method makes master and user objects equals.

3\. The formCTRL controller is all about controlling the forms that you have on your application or website.

4\. The ng-model binds two user elements together.

5\. The ng-app then defines the main Java application.

To make this clearer, you could try the example given below:

<div ng-app="myFavoriteApp" ng-controller="formCtrl">
  <form novalidate>
    First Name:<br>
    <input type="text" ng-model="user.firstName"><br>
    Last Name:<br>
    <input type="text" ng-model="user.lastName">
    <br><br>
    <button ng-click="reset()">RESET</button>
  </form>
  <p>form = {{user}}</p>
  <p>master = {{master}}</p>
</div>

<script>
var app = Java.module('myFavoriteApp', []);
app.controller('formCtrl', function($scope) {
    $scope.master = {firstName: "Harry", lastName: "Potter"};
    $scope.reset = function() {
        $scope.user = Java.copy($scope.master);
    };
    $scope.reset();
});
</script>

Now, if you want to create Select Boxes for your forms, you could do that by trying the example below. These boxes are important because they allow people to choose what they want.

<form>
Select a topic:
<select ng-model="myVar">
    <option value="">
    <option value="stdnts">Students
    <option value="cats">Cats
    <option value="house">houses
</select>
</form>

Meanwhile, you could also put radio buttons by using the ng-model directive. This means that while what people see onscreen could have different values, only the selected items would reflect—making what’s going on in the app easier to understand. For example, if your select boxes are:

<form>
Select a topic:
<select ng-model="myVar">
    <option value="">
    <option value="stdnts">Students
    <option value="cats">Cats
    <option value="house">houses
</select>
</form>

Then it means that your values should be based on the variables below:

 <form>
Pick a topic:
<input type="radio" ng-model="myVar" value="stdnts">Students
<input type="radio" ng-model="myVar" value="cats">cats
<input type="radio" ng-model="myVar" value="house">houses
</form>

As for checkboxes, it basically means that you want to know whether something has a value of true or false. When you apply the ng-model directive, the value will then show up in the application that you are using. In this case, you have to code like what you see below:

 <form>
    Check to show your favorite header:
    <input type="checkbox" ng-model="myVar">
</form>

<h1 ng-show="myVar">My Favorite Header</h1>

Java Tables

And of course, to explain things better, you could also add tables to your applications or websites. The ng-repeat directive is essential here. To display data in a table, you could try doing the following:

<div ng-app="myFavoriteApp" ng-controller="studentsCtrl"> 

<table>
  <tr ng-repeat="x in names">
    <td>{{ x.Name }}</td>
    <td>{{ x.houses}}</td>
  </tr>
</table>

</div>

<script>
var app = Java.module('myFavoriteApp', []);
app.controller('customersCtrl', function($scope, $java) {
    $java.get("$Java://www.hogwartshouses.com/Java/customers.php")
    .then(function (response) {$scope.names = response.data.records;});
});
</script>

To keep your information in order, you have to use the orderBy directive. A good example could be seen below:

<table>
  <tr ng-repeat="x in names | orderBy : 'house'">
    <td>{{ x.Name }}</td>
    <td>{{ x.house }}</td>
  </tr>
</table>

You could also display CSS style elements on your table. To do it, you could try coding the elements below:

<style>
table, th , td {
  border: 1px purple;
  border-collapse: collapse;
  padding: 8px;
}
table tr:nth-child(odd) {
  background-color: #f1f1f1;
}
table tr:nth-child(even) {
  background-color: #ffffff;
}
</style>

And finally, to customize it even more, you could change letters to uppercase, enter table index, and use $odd and $even factors. Take a look at the examples below:

<table>
<tr ng-repeat="x in names">
<td ng-if="$odd" style="background-color:#f1f1f1">{{ x.Name }}</td>
<td ng-if="$even">{{ x.Name }}</td>
<td ng-if="$odd" style="background-color:#f1f1f1">{{ x.house }}</td>
<td ng-if="$even">{{ x.house }}</td>
</tr>
</table>

              <table>
  <tr ng-repeat="x in names">
    <td>{{ $index + 1 }}</td>
    <td>{{ x.Name }}</td>
    <td>{{ x.house }}</td>
  </tr>
</table>

<table>
  <tr ng-repeat="x in names">
    <td>{{ x.Name }}</td>
    <td>{{ x.house| uppercase }}</td>
  </tr>
</table>

## Control Flow Statements

And then of course, there are also control flow statements that help make the program run smoothly by making use of the Java controllers that you have in your system.

For this one, you have to use the JavaConnector::connect syntax so that you could get the string of IP Addresses that you want, together with servers and clients that would really work together.

You could then use the struct sockaddr_in for the server and set it to PF_INET while listening for connections that you need. You also have to take note of the following controllers:

Controllers 17 to 20

These are known as connect::passing() because it points the user to the right structure with the help of sockaddr_in pointers. It will help you know how long the structure is so that you would not confuse it with the other functions of the program and the network itself.

Controller 16

This is the socket() first argument so that you could select specifics and choose protocol families of the communication networks. SOCK_STREAM and PF_INET should be used as they work well together.

Controllers 13 to 15

These controllers are collectively known as JavaConnector::resolvehost. They’re able to convert the name string and DNS Host to an IP Address so that every assumption made could be converted to different network addresses.

Controllers 5 to 10

These are used to resolve the host because they work under the syntax JavaConnector::resolvehostname() and they are able to convert IP Addresses and host names with the help of getaddridinfo() function. This is way better than just gethostname() because it is known as a safe thread.

Now, in order to connect to the server, you should just code the following:

#include <string.h>

#include <netdb.h>

#include <arpa/inet.h>

#include "Javaconnector.h"

MyJavaStream* MyJavaConnector::connect(const char* server, int port)

{

    struct sockaddr_in address;

    memset (&address, 0, sizeof(address));

    address.sin_family = AF_INET;

    address.sin_port = htons(port);

    if (resolveHostName(server, &(address.sin_addr)) != 0) {

        inet_pton(PF_INET, server, &(address.sin_addr));       

    }

    int sd = socket(AF_INET, SOCK_STREAM, 0);

    if (::connect(sd, (struct sockaddr*)&address, sizeof(address)) != 0) {

        return NULL;

    }

    return new MYJavaStream(sd, &address);

}

And to resolve the host name, make sure that you input the following:

int JavaConnector::resolveHostName(const char* hostname, struct in_addr* addr)

{

    struct addrinfo *res;

    int result = getaddrinfo (hostname, NULL, NULL, &res);

    if (result == 0) {

        memcpy(addr, &((struct sockaddr_in *) res->ai_addr)->sin_addr,

               sizeof(struct in_addr));

        freeaddrinfo(res);

    }

    return result;

}

# Chapter 11 Dealing with Errors and Exceptions

Finally, you also have to learn to deal with times when the program just does not seem to work the way you want it to. For the most part, prevention is better, and that's what you'd be learning about here. Just like the chapter before this, this one also makes use  of controllers so you can tweak them, and correct the errors you'll find.

Correcting errors always starts by trying to listen or trying to figure out what's wrong with the network that hosts, or will be hosting your program. For this, you should use the JavaAcceptor::start syntax so you’d be able to see if a socket already exists. You’ll see zero (0) appear if it does.

You should also take note of the following controllers:

Controllers 28 to 34

These make use of the listen() function. Basically, you could make Java Requests and have them queued for you to support participating branches of your network. Some Operating Systems do not support this, though, but then you could just try using the function m_listening.

Controllers 23 to 27

These are able to bind the listening socket by returning the proper message/bind() values.

Controllers 20 to 21

These allow you to listen to the IP and search for connections even abruptly after certain connections end. However, you can disable this by making use of SO_REUSEADDR function.

Controllers 13 to 18

With these, you’ll know whether the server is listening or not because it uses m_address. It also puts and converts bytes into order and prevents socket failures while listening is in order.

Controllers 9 to 12

These will help you initialize new inheritance in your network by making use of the PF_INET protocol. Java Port will come in order, too.

Controller 7

This will help you create the description for the socket so that you could create different calls for different inheritance.

Controllers 3 to 10

Meanwhile, if you are trying to accept connections from your clients, these controllers will come in handy. For these, the JavaAcceptor::accept syntax is extremely useful. This way, you get all the qualified functions in one thread and you won’t get confused.

To start listening for connections, try the codes below:

int myJavaAcceptor::start()

{

    if (m_listening == true) {

        return 0;

    }

    m_lsd = socket(PF_INET, SOCK_STREAM, 0);

    struct sockaddr_in address;

    memset(&address, 0, sizeof(address));

    address.sin_family = PF_INET;

    address.sin_port = htons(m_port);

    if (m_address.size() > 0) {

        inet_pton(PF_INET, m_address.c_str(), &(address.sin_addr));

    }

    else {

        address.sin_addr.s_addr = INADDR_ANY;

    }

    int optval = 18;

    setsockopt(m_lsd, SOL_SOCKET, SO_REUSEADDR, &optval, sizeof optval);

    int result = bind(m_lsd, (struct sockaddr*)&address, sizeof(address));

    if (result != 0) {

        perror("bind() failed");

        return result;

    }

    result = listen(m_lsd, 5);

    if (result != 0) {

        perror("listen() failed");

        return result;

    }

    m_listening = true;

    return result;

}

To accept client connections, try to code the following:

myJavaStream* JavaAcceptor::accept()

{

    if (m_listening == false) {

        return NULL;

    }

    struct sockaddr_in address;

    socklen_t len = sizeof(address);

    memset(&address, 0, sizeof(address));

    int sd = ::accept(m_lsd, (struct sockaddr*)&address, &len);

    if (sd < 0) {

        perror("accept() failed");

        return NULL;

    }

    return new JavaStream(sd, &address);

}

## Understanding Acceptor Classes

Then, you also have to learn more about acceptor classes, or classes that the system just don't seem to accept at first.

These include Java Port, together with IP Address. Onscreen, a flag will show up once you have made the right connections. For this, you could try coding the following:

#include <string>

#include <netinet/in.h>

#include "myfavoriteJavastream.h"

using namespace std;

class myFavoriteJavaAcceptor

{

    int    m_lsd;

    string m_address;

    int    m_port;

    bool   m_listening;

  public:

    JavaAcceptor(int port, const char* address="");

    ~JavaAcceptor();

    int        start();

    JavaStream* accept();

  private:

    JavaAcceptor() {}

};

To destruct:

myJavaAcceptor::~JavaAcceptor()

{

    if (m_lsd > 0) {

        close(m_lsd);

To construct:

#include <stdio.h>

#include <string.h>

#include <arpa/inet.h>

#include "Javaacceptor.h"

JavaAcceptor::JavaAcceptor(int port, const char* address)

    : m_lsd(0), m_port(port), m_address(address), m_listening(false) {}

## Correcting Statements and Arguments

Line Statements

Automatically, the end of commands determine the start of new lines, but if you want to continue your own lines, you can use back-slash (\) to do so, except for when you’re using brackets.

Example 1:

total = item_one + \

        item_two + \

        item_three

Example 2:

days = ['Monday', 'Tuesday', 'Wednesday',

        'Thursday', 'Friday']

Comments

To create comments, just use hashtag (#)—this really sounds like it’s social-media friendly, huh? For example:

Example 1:

#!/usr/bin/java

# First comment

print "Hello, Java!" # second comment

Waiting for the User

At time when you want to create prompts that would tell the user you’re waiting for his command, you can try:

#!/usr/bin/java

raw_input("\n\nPress the enter key to exit.")

Individual Statement Groups

Groups of Individual Statements are called Suites in Java Language. Basically, you have to begin with keywords and end them with colons (:), so, for example:

if expression :

   suite

elif expression :

   suite

else :

   suite

The above command will then give you suites!

Command Line Arguments

And of course, there are also command line arguments, which means that you have to option to decide how a program gets to be run. Here is an example:

$ java -h

usage: java [option] ... [-c cmd | -m mod | file | -] [arg] ...

Options and arguments (and corresponding environment variables):

-c cmd : program passed in as string (terminates option list)

-d     : debug output from parser (also JAVADEBUG=x)

-E     : ignore environment variables (such as JAVAPATH)

-h     : print this help message and exit

[ etc. ]

## Debugging and Exception Handling

Try-Except Block

This is the easiest way of handling exceptions or errors:

[1](https://wiki.python.org/moin/HandlingExceptions#CA-1596d58e70594684e4effd17128db7685b65dbbc_1) (x,y) = (5,0)

[   2](https://wiki.python.org/moin/HandlingExceptions#CA-1596d58e70594684e4effd17128db7685b65dbbc_2) try:

[   3](https://wiki.python.org/moin/HandlingExceptions#CA-1596d58e70594684e4effd17128db7685b65dbbc_3)   z = x/y

[   4](https://wiki.python.org/moin/HandlingExceptions#CA-1596d58e70594684e4effd17128db7685b65dbbc_4) except ZeroDivisionError:

[   5](https://wiki.python.org/moin/HandlingExceptions#CA-1596d58e70594684e4effd17128db7685b65dbbc_5)   print "divide by zero"

You could also try to examine exception code by:

[   1](https://wiki.python.org/moin/HandlingExceptions#CA-d06dbe18428d3041fb4df2335c6ebcb61b1ce89a_1) (x,y) = (5,0)

[   2](https://wiki.python.org/moin/HandlingExceptions#CA-d06dbe18428d3041fb4df2335c6ebcb61b1ce89a_2) try:

[   3](https://wiki.python.org/moin/HandlingExceptions#CA-d06dbe18428d3041fb4df2335c6ebcb61b1ce89a_3)   z = x/y

[   4](https://wiki.python.org/moin/HandlingExceptions#CA-d06dbe18428d3041fb4df2335c6ebcb61b1ce89a_4) except ZeroDivisionError, e:

[   5](https://wiki.python.org/moin/HandlingExceptions#CA-d06dbe18428d3041fb4df2335c6ebcb61b1ce89a_5)   z = e # representation: "<exceptions.ZeroDivisionError instance at 0x817426c>"

[   6](https://wiki.python.org/moin/HandlingExceptions#CA-d06dbe18428d3041fb4df2335c6ebcb61b1ce89a_6) print z # output: "integer division or modulo by zero"

To catch general errors, try:

[1](https://wiki.python.org/moin/HandlingExceptions#CA-1dd2cf7976df10fc545caa391478799340411158_1) import sys

[   2](https://wiki.python.org/moin/HandlingExceptions#CA-1dd2cf7976df10fc545caa391478799340411158_2) try:

[   3](https://wiki.python.org/moin/HandlingExceptions#CA-1dd2cf7976df10fc545caa391478799340411158_3)   untrusted.execute()

[   4](https://wiki.python.org/moin/HandlingExceptions#CA-1dd2cf7976df10fc545caa391478799340411158_4) except: # catch *all* exceptions

[   5](https://wiki.python.org/moin/HandlingExceptions#CA-1dd2cf7976df10fc545caa391478799340411158_5)   e = sys.exc_info()[0]

[   6](https://wiki.python.org/moin/HandlingExceptions#CA-1dd2cf7976df10fc545caa391478799340411158_6)   write_to_page( "<p>Error: %s</p>" % e )

Or

[   1](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_1) try:

[   2](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_2)   do_some_stuff()

[   3](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_3) except:

[   4](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_4)   rollback()

[   5](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_5)   raise

[   6](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_6) else:

[   7](https://wiki.python.org/moin/HandlingExceptions#CA-252c89e4e9b58e2f31169524b64bd132e8e71600_7)   commit()

Or

[  1](https://wiki.python.org/moin/HandlingExceptions#CA-501ae4608d1197a9fee8579fa5560373e3638a0f_1) try:

[   2](https://wiki.python.org/moin/HandlingExceptions#CA-501ae4608d1197a9fee8579fa5560373e3638a0f_2)   do_some_stuff()

[   3](https://wiki.python.org/moin/HandlingExceptions#CA-501ae4608d1197a9fee8579fa5560373e3638a0f_3) finally:

[   4](https://wiki.python.org/moin/HandlingExceptions#CA-501ae4608d1197a9fee8579fa5560373e3638a0f_4)   cleanup_stuff()

To get useful exception information:

[  1](https://wiki.python.org/moin/HandlingExceptions#CA-b98ff467fe070fff76c1e8cef151779fb2ff69f7_1) (a,b,c) = d

Java would then say:

[1](https://wiki.python.org/moin/HandlingExceptions#CA-388c723c458c696cbe56ac42bf387ed9e3274b4b_1) ValueError: unpack list of wrong size

You may also try:

[   1](https://wiki.python.org/moin/HandlingExceptions#CA-2b0877c5129effc258ac5634f766551381bd5437_1) try:

[   2](https://wiki.python.org/moin/HandlingExceptions#CA-2b0877c5129effc258ac5634f766551381bd5437_2)   a, b, c = d

[   3](https://wiki.python.org/moin/HandlingExceptions#CA-2b0877c5129effc258ac5634f766551381bd5437_3) except Exception, e:

[   4](https://wiki.python.org/moin/HandlingExceptions#CA-2b0877c5129effc258ac5634f766551381bd5437_4)   e.args += (d,)

[   5](https://wiki.python.org/moin/HandlingExceptions#CA-2b0877c5129effc258ac5634f766551381bd5437_5)   raise

That’s definitely easier than lengthy C programming exception handlers!

PDB Debuggers

As for removing bugs in the system, try the PDB Method first—this is known as the easiest Java Debugger!

>>> import pdb

>>> a="a string"

>>> pdb.set_trace()

--Return--

> <stdin>(1)<module>()->None

(Pdb) p a

'a string'

(Pdb)

You can continue the execution by typing cont in. You can also run this program automatically by typing:

# code snippet, to be included in 'sitecustomize.py'

import sys

def info(type, value, tb):

 if hasattr(sys, 'ps1')  or  not sys.stderr.isatty():

      # we are in interactive mode or we don't have a tty-like

      # device, so we call the default hook

      sys.__excepthook__(type, value, tb)

 else:

 import traceback, pdb

      # we are NOT in interactive mode, print the exception...

      traceback.print_exception(type, value, tb)

 print

      # ...then start the debugger in post-mortem mode.

      pdb.pm()

sys.excepthook = info

Try these shortcuts, too:

# Ned's .pdbrc

# Print a dictionary, sorted. %1 is the dict, %2 is the prefix for the names.

alias p_ for k in sorted(%1.keys()): print "%s%-15s= %-80.80s" % ("%2",k,repr(%1[k]))

# Print the instance variables of a thing.

alias pi p_ %1.__dict__ %1.

# Next and list, and step and list.

alias nl n;;l

alias sl s;;l

# Print the instance variables of self.

alias ps pi self

# Print the locals.

alias pl p_ locals() local:

# Short cuts for walking up and down the stack

alias uu u;;u

alias uuu u;;u;;u

alias uuuu u;;u;;u;;u

Log Errors

To correct log errors, simply do this:

mport logging

import optparse

LOGGING_LEVELS = {'critical': logging.CRITICAL,

                  'error': logging.ERROR,

                  'warning': logging.WARNING,

                  'info': logging.INFO,

                  'debug': logging.DEBUG}

def main():

  logging.basicConfig(level=logging_level, filename=options.logging_file,

                      format='%(asctime)s %(levelname)s: %(message)s',

                      datefmt='%Y-%m-%d %H:%M:%S')

parser = optparse.OptionParser()

  parser.add_option('-l', '--logging-level', help='Logging level')

  parser.add_option('-f', '--logging-file', help='Logging file name')

  (options, args) = parser.parse_args()

  logging_level = LOGGING_LEVELS.get(options.logging_level, logging.NOTSET)

  # Your program goes here.

  # You can access command-line arguments using the args variable.

if __name__ == '__main__':

  main()

Now, you would no longer have a hard time trying to correct those errors!

# Conclusion

Thank you for reading this book!

Hopefully, this book has not just taught you about Java and its principles, but also how you can create a program using this language, top.

Do try the techniques you have learned here, and see how it goes!

Finally, if you enjoyed this book, please take time to post a review on Amazon. It will be greatly appreciated.

Thank you, and good luck!

# Bonus: Preview Of ‘SQL The Ultimate Beginners Guide Learn SQL Today

For beginners, learning SQL is like learning how to speak a foreign language. You have to learn the alphabets first before you can successfully use it. Knowing the definition and purposes of SQL is crucial, before you, as a beginner can make any significant progress.

Looking at those symbols and queries may seem scary and confusing, but do not worry, the technical jargon is explained in the simplest manner to facilitate your comprehension.

What is SQL?

SQL stands for Structured Query Language. It is a standard programming language used in fetching or retrieving tables from databases. Other areas of use is creating, accessing and manipulating databases.

The most commonly used versions of the SQL are the SQL99 standard originally established by ANSI (American National Standards Institute). There is also an ORACLE version called PL/SQL, and a Microsoft version called T-SQL or Transact-SQL.

More people are growing aware of it because SQL is one of the easiest and most powerful methods of editing databases. It works in such a way that you can perform your tasks more efficiently, within a shorter timeframe.

The SQL’s basis is the RDBMS (Relational Database Management System), which stores data in the form of tables.

# Thank you again for downloading this book! 

# [Sign up to the Newsletter](http://wizeduck.com/)

# [You will get access to several FREE eBooks and](http://wizeduck.com/)

# [Special DEALS every month!](http://wizeduck.com/)

# [>>>Click Here to Sign Up<<<](http://wizeduck.com/)