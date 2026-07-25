![](cover.jpeg)

Swift Programming Guide

Create a Fully Functioning App in a Day

2nd Edition

by Os Swift

© Copyright 2015 by Os Swift - All rights reserved.

In no way is it legal to reproduce, duplicate, or transmit any part of this document in either electronic means or in printed format. Recording of this publication is strictly prohibited and any storage of this document is not allowed unless with written permission from the publisher. All rights reserved.

The information provided herein is stated to be truthful and consistent, in that any liability, in terms of inattention or otherwise, by any usage or abuse of any policies, processes, or directions contained within is the solitary and utter responsibility of the recipient reader. Under no circumstances will any legal responsibility or blame be held against the publisher for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly.

Respective authors own all copyrights not held by the publisher.

Legal Notice:

This book is copyright protected. This is only for personal use. You cannot amend, distribute, sell, use, quote or paraphrase any part or the content within this book without the consent of the author or copyright owner. Legal action will be pursued if this is breached.

Disclaimer Notice:

Please note the information contained within this document is for educational and entertainment purposes only. Every attempt has been made to provide accurate, up to date and reliable complete information. No warranties of any kind are expressed or implied. Readers acknowledge that the author is not engaging in the rendering of legal, financial, medical or professional advice.

By reading this document, the reader agrees that under no circumstances are we responsible for any losses, direct or indirect, which are incurred as a result of the use of information contained within this document, including, but not limited to, —errors, omissions, or inaccuracies.

Contents

Introduction

Chapter 1: A Basic Comparison of Swift and Objective C

Code Comments

Declaring Constants and Variables

Variable Names and Unicode

Integer Bounds

Type Inference

String Comparison

String Upper or Lower Case

Declaring Arrays

Working with Arrays

Declaring Dictionaries

Working with Dictionaries

For Loops

Conditional Statements

Switch Statement

Functions

Chapter 2: Functions

Defining and Calling Functions

Function Parameters and Return Values

Functions with Multiple Parameters

Chapter 3:  Introduction to Playgrounds

Variables vs. Constants

Explicit vs. Inferred Typing

Basic Types and Control Flow in Swift

Floats and Doubles

Bools

Strings

If Statements and String Interpolation

Part 2: Using the XCode Editing Tools

Chapter 4:  Classes and Methods

Chapter 5: Arrays and For Loops

Dictionaries

Chapter 6: Type Casting

Checking Type

Downcasting

AnyObject

Any

Nested Types

Referring to Nested Types

Function Types as Parameter Types

Function Types as Return Types

Nested Functions

Chapter 7: Creating Your First iOS App

Getting Started

Creating Your Model

Chapter 8:  Introduction to Storyboards and Interface Builder

Creating your Views

A View Controller Tour

Connecting your View Controller to your Views

Connecting Actions to your View Controller

Connecting Your View Controller to your Model

Chapter 9: Writing an iOS App with Swift – Advanced

What You Need

Getting Started

Learning by Example

AppDelegate.swift

MasterViewController.swift

DetailViewController.swift

Coming Up Next

Your First Feature

Setting up The Storyboard

Creating the AddTaskViewController

Cancelling Task Creation

Saving Your Task

Creating the Task struct

Managing our TaskStore

Finishing Your First Feature

How it Should Look Now

Finishing off Save

Using What You Have

Opening the Detail Screen

No more AnyObject

Changing the Data Source and Delegate

Back to the Data Source

Finishing the Basics with the Delegate

One More Method for TaskStore

Tidying Things Up a Bit

Altering the Storyboard

Updating Your MasterViewController

Redesigning the Detail View

Displaying Your Notes

Chapter 10: What’s New in Swift 2

Error Handling

Binding

Protocol Extensions

Grab Bag

Chapter 11: Creating Applications in Swift

Simple Calculator

Minesweeper game

Conclusion

# Introduction

In 2014, Apple changed their programming language, introducing Swift to build on the very best features of C and Objective-C without all the constraints of C Compatibility. Swift has been in the making for many years and brings new safe patterns of programming to the table, along with modern features that make it easy to program, far more flexible than ever before and a lot more fun to use.

Swift will probably look and feel very familiar to old hands at Objective-C. That’s because it takes on the readability of named parameters and the power of the object model within Objective –C. And it brings a lot of new features the computer programming for iOS and OS X operating systems.

Swift is incredibly user-friendly and is perfect for new programmers to learn. Included is support for playgrounds, which is an innovative new feature that lets you experiment with your code, see it running and see the results before you go to all the expense of building your app and running it.

It combines modern language with wisdom garnered from the wide culture of Apple engineering. The compiler is fully performance optimized and the language is development optimized without any compromises. It is designed to go from the simple “Hello, World!” app right through to building a complete operating system and this is what makes it the language to learn, the best investment you could ever make for the future.

Just like everything else they produce, Apple will ensure that Swift is kept fully updated with the latest features and the best capabilities. The idea of this book is to give you an overview of what Swift does now and help you to create your very first iOS/OS X app in the form of a Tips Calculator.

If you are ready to start learning the computer language of the future, head on to the very first chapter and let’s see what you can do. Please be sure that you have the very latest version of XCode before you begin – you can get it from the Mac OS X store – as we are going to delve straight into programming.

# Chapter 1: A Basic Comparison of Swift and Objective C

Many of you are probably very familiar with Objective C programming language and may be wondering what, if any, differences there are between that and Swift. Sift is a recent and modern programming language that has all the power for Objective C but doesn’t have all the baggage that the older language comes with. So, before we get stuck into learning how to use Swift, I wanted to just give you a basic comparison of the two languages. This is NOT designed to be a “them and us” between Microsoft and Apple – there are many programmers who use C on a daily basis and I want to show you what Swift can offer compared to C. So, let the code start talking.

## Code Comments

Both Swift and C support the same comments syntax – the all too familiar C comment:

*   // code comment
*   /* multi line
*   code comment */

## Declaring Constants and Variables

Like C, Swift is a very type safe language. Swift also support type inference so, when you are declaring the variables, you do not need to specify the type as the computer will detect, or infer, the type. It does this by evaluating the variable assignment. C is a little more on the verbose side when it comes to declaring constants but both C and Swift are as elegant as one anther when it comes to using type inference to declare variables:

*   // Declare Constant
*   // C#
*   const int legalAge = 18;
*   // Swift
*   let legalAge = 18
*   // Declare Variable
*   // C#
*   var legalAge = 18;
*   // Swift
*   var legalAge = 18

Type inference is all very nice but if you do not need to assign a value to a variable straightaway, you might have to explicitly specify the variable type:

*   // Type Annotation
*   //C#
*   string firstName;
*   // Swift
*   var firstName: String

Did you notice that Swift does not use a semi-colon? While Swift is very close to Objective C syntax, it does it all without the use of a semi-colon, unless you want to insert multiple code statements on a single line, in which case the semi-colon is supported and, indeed, in that case, required.

## Variable Names and Unicode

Both Swift and Objective C supports Unicode characters in variable names. In short, you could use anything you wanted, including non-ASCII characters and emoticons in your variable names – if you really wanted to.

## Integer Bounds

Both Objective C and Swift use static constants for when you want to access the maximum and minimum bounds for different types of integer.

*   // Integer Bounds
*   // C#
*   var a = Int32.MinValue;
*   var b = Int32.MaxValue;
*   // Swift
*   var a = Int32.min
*   var b = Int32.max

## Type Inference

Swift and Objective C both support type inference, as we mentioned earlier, in circumstances where the compiler can infer the declared variable type from its immediate assignment.

*   // Type Inference
*   // C#
*   var a = 3; // integer
*   var b = 0.14 // double
*   var c = a + b; // double
*   // Swift
*   var a = 3 // integer
*   var b = 0.14 // double
*   var c = a + b // double

Also note, in the example of type inference above that, when you declare a variable and then assign a value immediately - a value that is the result of two more variables - the type will still be inferred.

## String Comparison

Both Swift and Objective C compare strings in similar ways

*   // String Comparison
*   // C#
*   var a = "One";
*   var b = "One";
*   if (a == b) {
*   // both variables are considered equal
*   }
*   // Swift
*   var a = "One"
*   var b = "One"
*   if a == b {
*   // both variables are considered equal
*   }

They also both use similar method to detect if the start or the end of a string matches with another specified string

*   // C#
*   var s = "Some Value";
*   if (s.StartsWith("Some")) {
*   // the string starts with the value
*   }
*   if (s.EndsWith("Value")) {
*   // the string ends with the value
*   }
*   // Swift
*   var s = "Some Value"
*   if s.hasPrefix("Some") {
*   // the string starts with the value
*   }
*   if s.hasSuffix("Value") {
*   // the string ends with the value
*   }

Have another look at the above example. Did you spot that, when you use an IF statement in Swift, you don’t need to use parentheses?

## String Upper or Lower Case

Both Swift and Objective C support methods that are similar of converting a string between lower and upper case

*   // String Upper and Lower Case
*   // C#
*   var s = "some Value";
*   var upperS = s.ToUpper();
*   var lowerS = s.ToLower();
*   // Swift
*   var s = "some Value"
*   var upperS = s.uppercaseString
*   var lowerS = s.lowercaseString

## Declaring Arrays

Both Swift and Objective C support the use of a single line of code to declare and assign an Array

*   // Declare Arrays on single line
*   // String Array
*   // C#
*   var arr = new string[] { "One", "Two" };
*   // Swift
*   var arr = ["One", "Two"]
*   // Integer Array
*   // C#
*   var arr = new int[] { 1, 2 };
*   // Swift
*   var arr = [1, 2];

## Working with Arrays

There is a little difference between Swift and Objective C when it comes to working with Arrays

*   // Iterating Over Array
*   // C#
*   for each (var item in arr) {
*   // do something
*   }
*   // Swift
*   for item in arr {
*   // do something
*   }
*   // Get Item at Index
*   // C#
*   var item = arr[0];
*   // Swift
*   var item = arr[0]
*   // Set Item at Index
*   // C#
*   arr[0] = "Value";
*   // Swift
*   arr[0] = "Value"
*   // Is Array Empty?
*   // C#
*   if (arr.Length == 0) {
*   // array is empty
*   }
*   // Swift
*   if arr.isEmpty {
*   // array is empty
*   }
*   // Add Item to Array
*   // C#
*   Array.Resize(ref arr, arr.Length + 1);
*   arr[arr.Length - 1] = "Three";
*   // Swift
*   arr.append("Three")
*   // or
*   arr += "Three"
*   // Remove Item at Index
*   // C#
*   var list = arr.ToList();
*   list.RemoveAt(0);
*   var newArr = list.ToArray();
*   // Swift
*   var newArr = arr.removeAtIndex(0)

## Declaring Dictionaries

Both Swift and Objective C use similar methods when it comes to declaring Dictionaries

*   // Declaring Dictionaries
*   // C#
*   var dict = new Dictionary<string, string>();
*   var dict2 = new Dictionary<string, string>
*   {
*   { "TYO", "Tokyo" },
*   { "DUB", "Dublin" }
*   };
*   // Swift
*   var dict = Dictionary<String, String>()
*   var dict2 = ["TYO": "Tokyo", "DUB": "Dublin"]

## Working with Dictionaries

There is a slight difference between the was Swift and Objective C work with Dictionaries

*   // Iterate over Dictionary
*   // C#
*   foreach(var item in dict) {
*   var key = item.Key;
*   var value = item.Value;
*   }
*   // Swift
*   for (key, value) in dict {
*   // key variable contains key of item
*   // value variable contains value of item
*   }
*   // Get Item in Dictionary by Key
*   // C#
*   var item = dict["TYO"];
*   // Swift
*   var item = dict["TYO"]
*   // Set Item in Dictionary by key
*   // or add if key doesn't exist
*   // C#
*   dict["LHR"] = "London";
*   // Swift
*   dict["LHR"] = "London"
*   // Remove Item in Dictionary by key
*   // C#
*   dict.Remove("LHR");
*   // Swift
*   dict.removeValueForKey("DUB")

## For Loops

In the examples above for Dictionaries and Arrays, you have already seen the For-In loop, used to iterate through items in specific collections. The following shows you more methods of iteration sing that For Loop

*   // Iterate from 1 through 5
*   // C#
*   // using increment
*   for(var i = 1; i <= 5; i++) {
*   // do something with i
*   }
*   // Swift
*   // using range
*   for i in 1...5 {
*   // do something with i
*   }
*   // using increment
*   for var i = 0; i <= 5; ++i {
*   // do something with i
*   }

Notice that Swift uses a method of shorthand for the definition in the range

## Conditional Statements

Both Swift and Objective C support the If…Then conditional statement. Swift is slightly different in that parentheses are not required to be inserted around match conditions

*   // If Then Else Conditional Statement
*   // C#
*   if (i > 6) {
*   // do something
*   } else if (i > 3 && i <= 6) {
*   // do something
*   } else {
*   // do something
*   }
*   // Swift
*   if i > 6 {
*   // do something
*   } else if i > 3 && i <= 6 {
*   // do something
*   } else {
*   // do something
*   }

## Switch Statement

Both Swift and Objective C support Switch statements

*   // Switch statement
*   // C#
*   var word = "A";
*   switch(word) {
*   case "A":
*   // do something
*   break;
*   case "B":
*   // do something
*   break;
*   default:
*   // do something
*   break;
*   }
*   // Swift
*   var word = "A"
*   switch word {
*   case "A":
*   // do something
*   case "B":
*   // do something
*   default:
*   // do something
*   }

Switch statements are similar in both Swift and Objective C with the exception of case statements – in Swift, these do not pass automatically to the next as they do in Objective C. As a result of this, C needs break keywords to exit the statement unless you are intending to fall through to the next case. In Swift, you have to use the fallthrough keyword to let it know that you want to pass to the next case statement.

Another feature that is supported in Swift with Switch statements is the ranges in the Case statements, something that is not supported in Objective C

*   // Switch Case Ranges
*   // C#
*   switch (i) {
*   case 1:
*   case 2:
*   case 3:
*   // do something
*   break;
*   case 4:
*   // do something
*   break;
*   default:
*   // do something
*   break;
*   }
*   // Swift
*   switch i {
*   case 1...3:
*   // do something
*   case 4:
*   // do something
*   default:
*   // do something
*   }

## Functions

Functions are quite a big subject on their own when it comes to being compared with Objective C so, for now have a look at this fairly basic example

*   // Function with Parameter and Return Value
*   // C#
*   string sayHello(string name) {
*   // do something
*   }
*   // Swift
*   func sayHello(name: String) -> String {
*   // do something
*   }

That is a basic comparison of Objective C and Swift programming languages. You can see that both share many similarities in a lot of places but one of the single biggest differences is in how they handle arrays. Swift arrays are similar to the List<>class in Objective C, something that most developers are using nowadays instead of using arrays, unless performance dictates that they need to be used. In the next chapter, we’ll discuss about functions in detail.

# Chapter 2: Functions

In general, functions can be defined as self-contained pieces of code which are capable of performing a specific task. By assigning the function name, which identifies the task it does, you can call the function for performing the task it is supposed to do.

The unified function syntax of Swift is flexible enough for expressing simple C style functions that have no parameter names and objective C style methods, which have local parameter names and external parameter names that are complex. Default values will be provided by the parameters for simplifying the function calls. These can be given as in out parameters and after the execution of the function they modify the passed variable.

In Swift, every function has a type. Every function consists of a parameter type along with the return type, which can be used like any other parameter type in swift. With this, it is possible to pass a function as a parameter to another function and you can also return functions from other functions. Swift allows you to write functions inside other functions. With this, encapsulation is possible and useful functionalities can be nested within other functions.

### Defining and Calling Functions

Whenever you define a function, you can also define one or more optional typed, named values that can be given as the input for that function. These are known as parameters. You can also define an optional value type that the function passes back as the output after the work is done. This is called as the return type.

Every function will be given a function name and this function name will describe the task which it performs. We call the function for using that function and for calling; we will use its name and pass input values to it. These input values are known as arguments. Arguments match the function parameter type. The function parameter list and the arguments of the function must be provided with the same order, always.

Here is an example where the function called sayHello(_:) is used. It is called so because of the task it performs, which is to take the name of the person as its input and to return a greeting to him. An input parameter called the personName, of the string value should be defined for accomplishing this. The return type of this function is also a string and it contains the greeting which will be returned back to him:

*   func sayHello(personName: String) -> String {
*   let greeting = "Hello, " + personName + "!"
*   return greeting
*   }

The function definition will be prefixed with the keyword func and the information will be rolled up to the definition of the function. The return type of function will be indicated using the return arrow ->. This will be followed by the return type name.

The definition of the function will define the task of the function, the input of the function and the return type of the function when its task is done. You can unambiguously call the function from any place from your code using the definition:

print(sayHello("Chad"))

// prints "Hello, Chad!"

print(sayHello("Bruce"))

// prints "Hello, Bruce!"

You can call the function sayHello(_:), by passing a string argument inside the parentheses, like sayHello("Chad"). As the return type of the function is a string value, for printing the string, the function can be wrapped inside the call to the function print(_:separator:terminator:) for checking the return value.

A string constant called greeting will be defined and a greeting message will be addressed to the personName, for starting the body of the function sayHello(_:). The return keyword will be used for passing back the greeting out of the function. After calling the return greeting, the function will complete its execution and it will return the greeting’s current value.

The function sayHello(_:) can be call multiple times using different input values. In the example given above, we can see what happens if the function sayHello(_:) is called using “Chad” has its input value and “Bruce” as it's input value. In each case, the function will be returning a tailored greeting.

You can simplify the functions body by combining the message creation and return statement in a single line:

*   func sayHelloAgain(personName: String) -> String {
*   return "Hello again, " + personName + "!"
*   }
*   print(sayHelloAgain("Chad"))
*   // prints "Hello again, Chad!"

### Function Parameters and Return Values

In Swift, the return values and function parameters are extremely flexible. You are allowed to define simple utility functions consisting of single unnamed parameter and a complex functions consisting different parameter options with expressive parameter names.

Functions Without Parameters

For defining input parameters, functions are not required. Here is an example function that has no input parameters. Whenever this function is called, it will return the same message.

func sayHelloWorld() -> String {

  return "hello, world"

}

print(sayHelloWorld())

// prints "hello, world"

You should still add parenthesis after the name of the function in the function definition, even when it doesn't take parameters. An empty parenthesis pair will follow the function name whenever it is called.

## Functions with Multiple Parameters

Multiple input parameters can be given to a function. These parameters will be included inside the parenthesis of the function and commas are used for separating them.

*   func sayHello(personName: String, alreadyGreeted: Bool) -> String {
*   if alreadyGreeted {
*   return sayHelloAgain(personName)
*   } else {
*   return sayHello(personName)
*   }
*   }
*   print(sayHello("Popeye", alreadyGreeted: true))
*   // prints "Hello again, Popeye!"

By Passing the string argument value along with the Boolargument value, you can call the function sayHello(_:alreadyGreeted:). The Boolargument value will be labelled alreadyGreeted inside the parenthesis. These will be separated using commas.

Whenever you call a function using multiple parameters, any argument given after the first one will be labeled basing on the corresponding parameter name.

Functions without Return Values

A return type need not be defined for functions. Here is an example function sayHello(_:), and it's version sayGoodbye(_:), which will print the string value of its own instead of returning it:

*   func sayGoodbye(personName: String) {
*   print("Goodbye, \(personName)!")
*   }
*   sayGoodbye("Lee")
*   // prints "Goodbye, Lee!"

As this function doesn't need to return anything, the definition of the function need not have the return type or the return arrow ->.  

Note: In cases where the return value is not defined, the sayGoodbye(_:) function can be used for returning a value. If there is no return type defined, a Void type will be returned by the function. The Void is nothing but a special value that has no elements inside it. Is an empty tuple and can be written as ().

When the Void is called, the return value of the functions can be ignored.

*   func printAndCount(stringToPrint: String) -> Int {
*   print(stringToPrint)
*   return stringToPrint.characters.count
*   }
*   func printWithoutCounting(stringToPrint: String) {
*   printAndCount(stringToPrint)
*   }
*   printAndCount("hello, world")
*   // prints "hello, world" and returns a value of 12
*   printWithoutCounting("hello, world")
*   // prints "hello, world" but does not return a value

The function printAndCount(_:), which is the first function, will print a string and it will return the character count as Int. The function printWithoutCounting, which is the second function, will call the first function but it will ignore the return value of the first function. The first function will print the message after calling the second function. In this case, the return value will not be used.

Note: When a function says that it doesn't return a value, the values return can be ignored. But if a function says that it will return a value, it must return a value. A compile time error will be displayed when a function which has a return type define doesn't allow the control to go to the bottom without returning the value.

Functions with Multiple Return Values

For a function, you can give the return type by using a tuple type for returning multiple values, as they don't return a value for part of a single compound return value.

The below example will define a minMax(_:) function. This function will find the Int values that are smallest and largest in the given array:

*   func minMax(array: [Int]) -> (min: Int, max: Int) {
*   var currentMin = array[0]
*   var currentMax = array[0]
*   for value in array[1..<array.count] {
*   if value < currentMin {
*   currentMin = value
*   } else if value > currentMax {
*   currentMax = value
*   }
*   }
*   return (currentMin, currentMax)
*   }

A tuple consisting of two Int values will be returned by the function minMax(_:). The returned values are named as min and max. When querying the return value of the function, these can be accessed by using their name.

By setting working variables called the currentMin and currentMax, the body of the function minMax(_:) will start. The currentMin and currentMax variables are used for setting the array's first integer.  The function will iterate the remaining values from the array and compares them if they are smaller or larger than currentMin and currentMax values respectively. Finally, the minimum and maximum values will be obtained and they will be returned as a tuple with two Int values.

The tuple members can be accessed using the dot syntax, as they have named as a part of the return type of the function. They are accessed for retrieving the maximum and minimum values found:

let bounds = minMax([8, -6, 2, 109, 3, 71])

print("min is \(bounds.min) and max is \(bounds.max)")

// prints "min is -6 and max is 109"

# Chapter 3:  Introduction to Playgrounds

Without any further ado, I want you to start up XCode. We are going to dive straight into setting up for your first program and we do this in Playground. Playground is a new feature, a way of being able to test out your code and see if it all works how you want it to, before you go ahead and do it for real. So, let’s get started:

1.  Start XCode up and then open File\New\File
2.  Choose iOS\Source\Playground
3.  Click Next
4.  You need to name your file so call it Swifttutorial.playground
5.  Now click on Create and save the file where you will remember it
6.  Make sure the file is empty – you want to start with a completely clean slate.
7.  Now open up your file and type the following into your program. As you do, the result of each line will show up in the sidebar so you can see exactly what is going on:

*   let tutorialTeam = 60
*   let editorialTeam = 17
*   let totalTeam = tutorialTeam + editorialTeam

Playgrounds are a fantastic way of learning how Swift works and for experimenting. For the remainder of the first part of this tutorial you are going to stay working in this playground.

Before you go any further, drag your new playground file to your OS X dock. This will make it easier for you to use it as a kind of notepad to test out new code quickly.

### Variables vs. Constants

Open up your Playground file again and try to add this line to the bottom of it:

*   totalTeam += 1

The first thing you will notice is that you get an error when you put this line in. The reason for this is that totalTeam is what is known as a constant and its value cannot change. Constants must be declared with the word let, which we didn’t do with this example. Instead of being a constant, you want totalTeam to be a variable – with a value that changes – so it must be declared in a different way – with the keyword var.

Go back to your playground file, scrub out the line you just typed and retype this:

*   var totalTeam = tutorialTeam + editorialTeam

Now you could ask yourself why we can’t just declare everything with the var keyword. The reason for declaring most things with let is that the compiler can work to perform optimizations that it couldn’t do with var.

## Explicit vs. Inferred Typing

We haven’t yet set types for either the constants or the variables simply because the compiler can do it automatically if it has sufficient information. Back at the beginning, you set tutorialTeam to 56 and the compiler knows that 56 is an Int so it can automatically set it for you. This is known as Inferred typing. You can, of course explicitly set the type. Go to the line in your code where you set the type of tutorialTeam and replace it with:

*   let tutorialTeam: Int = 60

Where possible, you should let the compiler infer the types for you – that is one of the biggest advantages to Swift, a concise easy code. For that reason, switch back to inferred typing by putting this line back in:

*   let tutorialTeam = 60

### Basic Types and Control Flow in Swift

So, you have now seen Int working, the Swift type for integer values. But there are many more than that. Keeping your playground file open, try these lines out for size to see what they do:

### Floats and Doubles

*   let priceInferred = 19.99
*   let priceExplicit: Double = 19.99

Both Float and Double are decimal point values. Double is more precise and in the default selection for inferred decimal values.

### Bools

*   let onSaleInferred = true
*   let onSaleExplicit: Bool = false

Those of you familiar with Objective-C will know that, for declaring Boolean values you use Yes or No. In Swift, we use True or False

### Strings

*   let nameInferred = "Whoopie Cushion"
*   let nameExplicit: String = "Whoopie Cushion"

Strings are what you would expect them to be – a sequence of characters. In Swift you don’t use the @ sign like you do in Objective-C so, if you have come from the old program, it might take you a while to get your head around that one!

### If Statements and String Interpolation

*   if onSaleInferred {
*   println("\(nameInferred) on sale for \(priceInferred)!")
*   } else {
*   println("\(nameInferred) at regular price: \(priceInferred)!")
*   }

This is an if statement and it is similar to all other computer programing languages. You don’t have to use the parentheses if you don’t want to but you do have to use braces, even if it is only a one line statement.

This also shows you a brand new technique that is called string interpolation. Whenever you want to make a substitute in Swift, you must use this syntax:

*   \ (yourexpression)

Look at the sidebar in the playground and you should see the result of this – it may be a little difficult to read because there isn’t a lot of space. Hover your mouse over the line and click on the eyeball that shows up.

# Part 2: Using the XCode Editing Tools

In this chapter, we will cover four elements of using the XCode:

1.  XCode editing tools
2.  Code completion features
3.  Code correction with Fix‐It
4.  Working with code snippets

As you can see in that chapter, a great deal of your Swift XCode development involves the graphical user interface of XCode. A lot of the work — particularly at the beginning of a project — is graphical or involves checkboxes.

In Chapter 4, I show you how to write and test code — particularly small snippets of code — in a playground. This helps you learn Swift syntax and allows you to test out code fragments before you type them (or copy‐and‐paste them) into your project files.

Now, in this chapter, I introduce XCode’s editing tools. Here, you’ll write code in the way you may have written it in your beginning programming class in school (that is, typing in code rather than drawing the interface and using XCode checkboxes and other graphical elements to construct your app visually). The focus in this chapter is on the XCode tools that assist you with writing code. Much of what XCode does for you in regard to typing and editing text is made possible by the fact that it observes every keystroke and keeps track of the syntax of the terms you type (or copy‐and‐paste).

With the tools and techniques you find in these first three chapters, you can create your first Swift app — the Locatapp example app used throughout this book. (In case you haven’t seen it yet, you can look at Figures 1‐1 through 1‐5 in Chapter 1 to see where you’re headed.)

# Chapter 4:  Classes and Methods

When you start working in Swift, you will be creating classes and methods on a regular basis so let’s take a look at what they are and how they work. First clear out everything that is in your playground file – we need a clean sheet to work on again. Now, this is where you get to start creating your very first app – a Tip Calculator. You will build this app one piece of code at a time and I will explain each piece as we go along. Ready?  Type the following into your playground file:

*   // 1
*   class TipCalculator {
*   }

The first thing you are doing is creating a class and to do this you simply type class and follow it with the name, in this case, TipCalculator. Follow this with curly braces.

Inside the curly braces, type in this code:

*   // 2
*   let total: Double
*   let taxPct: Double
*   let subtotal: Double

You will see some errors appear when you type this in but don’t worry about them, they will be fixed soon enough. What you have done here is create properties on the class, pretty much the same as you create constants or variables. You have created three properties – the total of the bill before after tax is added, the tax percentage added and the amount of the bill before tax is added.

The reason you are getting errors at this stage is because you must declare properties with an initial value and we didn’t do that for this.

Following on from the code you just typed, add in these lines, staying inside the curly braces:

*   // 3
*   init(total: Double, taxPct: Double) {
*   self.total = total
*   self.taxPct = taxPct
*   subtotal = total / (taxPct + 1)
*   }

This creates the initializer for the class and these are always named as init in Swift. This initializer takes two parameters and, because they both have the same name, they are distinguished by the addition of the self prefix.

Staying inside those curly braces, add this to your code:

*   // 4
*   func calcTipWithTipPct(tipPct: Double) -> Double {
*   return subtotal * tipPct
*   }

Here you have used the func keyword to declare a method followed by the parameters – here you must be explicit with types and you follow it up with the return type. This is a simple function that multiplies the subtotal of the bill by the tip percentage. Continuing on from that, add this code:

*   // 5
*   func printPossibleTips() {
*   println("15%: \(calcTipWithTipPct(0.15))")
*   println("18%: \(calcTipWithTipPct(0.18))")
*   println("20%: \(calcTipWithTipPct(0.20))")

You have created a new method that will print out 3 possible tip values. Note that when a method is called on an instance of a class, the initial parameter doesn’t need naming but the rest do. Now, add this code in, this time, after the curly braces:

*   // 6
*   let tipCalc = TipCalculator(total: 33.25, taxPct: 0.06)
*   tipCalc.printPossibleTips()

In the final step, you have created an instance of the tip calculator and you have called the method to show the possible tip values.

This is what your code should look like now:

*   // 1
*   class TipCalculator {
*   // 2
*   let total: Double
*   let taxPct: Double
*   let subtotal: Double
*   // 3
*   init(total: Double, taxPct: Double) {
*   self.total = total
*   self.taxPct = taxPct
*   subtotal = total / (taxPct + 1)
*   }
*   // 4
*   func calcTipWithTipPct(tipPct: Double) -> Double {
*   return subtotal * tipPct
*   }
*   // 5
*   func printPossibleTips() {
*   println("15%: \(calcTipWithTipPct(0.15))")
*   println("18%: \(calcTipWithTipPct(0.18))")
*   println("20%: \(calcTipWithTipPct(0.20))")
*   }
*   }
*   // 6
*   let tipCalc = TipCalculator(total: 33.25, taxPct: 0.06)
*   tipCalc.printPossibleTips()

# Chapter 5: Arrays and For Loops

You’ve probably noticed quite a bit of duplication in the above code. This is because you have called the method calcTipWithTotal a number of times, showing different percentages. This is where arrays come in and allow you to cut down on the duplication.

Go to where you have typed printPossibleTips and replace the contents:

*   let possibleTipsInferred = [0.15, 0.18, 0.20]
*   let possibleTipsExplicit:[Double] = [0.15, 0.18, 0.20]
*   You have created an array of doubles, using both inferred and explicit typing. Now add the following lines underneath that:
*   for possibleTip in possibleTipsInferred {
*   println("\(possibleTip*100)%: \(calcTipWithTipPct(possibleTip))")
*   }

## Dictionaries

We are going to make one last change to your code – rather than just showing your tips printed out, you can instead create a dictionary that contains all the results.

Got to where you have typed printPossibleTips and delete the method. Replace it with:

*   // 1
*   func returnPossibleTips() -> [Int: Double] {
*   let possibleTipsInferred = [0.15, 0.18, 0.20]
*   let possibleTipsExplicit:[Double] = [0.15, 0.18, 0.20]
*   // 2
*   var retval = [Int: Double]()
*   for possibleTip in possibleTipsInferred {
*   let intPct = Int(possibleTip*100)
*   // 3
*   retval[intPct] = calcTipWithTipPct(possibleTip)
*   }
*   return retval
*   }

Once again, you will see an error but we will fix this now. You need to modify the final line in your file to read:

*   tipCalc.returnPossibleTips()

Congratulations! You have created your very first class in Swift!

# Chapter 6: Type Casting

Type casting is a can be defined as a way of checking the instance type, or something which treats that as a different subclass or superclass from a different place in its hierarchy.

In Swift, we implement typecasting by using the is and as operators. These operators provide users with expressive and simple ways to check the value type or for casting a value into a different type.

Typecasting can also be used for checking if a type conforms to a given protocol, as described in the protocol conformance checking.

Defining a Class Hierarchy for Type Casting

Typecasting can be used with a hierarchy of subclasses and classes for checking the type of a given class instance and for casting that instance into a different class but with the same hierarchy. An example is given below where three code snippets are given and they define the hierarchy of an array and classes containing their class instances.

A new base class is defined in the first snippet. This base class is called MediaItem. This class can provide the basic functionality for any item which appears in the digital media library.

*   class MediaItem {
*   var name: String
*   init(name: String) {
*   self.name = name
*   }
*   }

In the next snippet, to subclasses of the MediaItem are defined. Movie is the first subclass and it encapsulates additional information on the film or movie. A director property will be added on top of the class MediaItem, which is the best class. This property will be added with an initializer responding to the base class.

Song is the second subclass and this adds a property and artist with an initialiser on the base class.

*   class Movie: MediaItem {
*   var director: String
*   init(name: String, director: String) {
*   self.director = director
*   super.init(name: name)
*   }
*   }

*   class Song: MediaItem {
*   var artist: String
*   init(name: String, artist: String) {
*   self.artist = artist
*   super.init(name: name)
*   }
*   }

A constant array named library will be created by the final snippet. This contains two Movie instances along with three Song instances. By initialising the library array with the contents from an array literal, it can be inferred. The type checker of Swift is capable of did you sing the song and movie having MediaItem as the common superclass.

*   let library = [
*   Movie(name: "Avatar", director: "James Cameroon"),
*   Song(name: "They Don’t Care About Us", artist: "Michael Jackson"),
*   Movie(name: "The Lord of the Rings", director: "Peter Jackson"),
*   Song(name: "Bohemian Rhapsody", artist: "Freddie Mercury"),
*   Song(name: "summer of 69", artist: "Brian Adams")
*   ]
*   // the type of "library" is inferred to be [MediaItem]

The movie and song instances are the items that are stored inside the library behind the scenes. If the contents of the array are iterated, the items, which you get receive will not be of the type movie or song but as MediaItem. You should check their type for you to work with them in their actual type or you can downcast them to a required type, as given below.

## Checking Type

You can check if an instant belongs to a certain subclass type by using the type check operator (is). If the instance belongs to that subclass type, the type check operator will return a true and if it is not, it will return a false.

Two variables movieCount and songCount are defined in the example below and they count the total number of song and movie instances present in the library array:

*   var movieCount = 0
*   var songCount = 0

*   for item in library {
*   if item is Movie {
*   ++movieCount
*   } else if item is Song {
*   ++songCount
*   }
*   }

*   print("Media library contains \(movieCount) movies and \(songCount) songs")
*   // prints "Media library contains 2 movies and 3 songs"

All the library array items will be integrated in this example. The item constant will be sent to the next MediaItem for every pass by the for in loop.

The operator will return a true in case where the current mediaItem is of the movie instance and it will return the false otherwise. Similarly, item is song will return a true value if the mediaItem belongs to the song instance and if not, it will return a false. When the for in loop ends, movieCount and songCount will contain the count of all the mediaItem instances found in each of those types.

## Downcasting

Behind the scenes, a variable or a constant of a particular class may refer a subclass instance. If you believe that this is the case, you can perform downcasting on the subclass type using the type cast operator (as? or as!).

Downcasting cannot always be successful and there are two different forms for the type cast operator. An optional value will be returned by the conditional form, as? and this optional value will be of the type that you are trying to downcast. The second form is the forced form as!. The results will be force unwrapped as a single compound action and the downcast will be attempted.

If you're not sure on the success of the downcast, you can use the type cast operator (as?), which is its conditional form. An optional value will always be returned by this form of operator and in cases where the downcast fails, the value will be nil. With this, you can check if a downcast successful.

If you're sure about the success of the downcast, you can use the type cast operator (as!), which is the forced form. A runtime error will be triggered by the operator if you downcast a class type which is incorrect.

The below example will iterate every MediaItem from the library and then prints the description appropriate for each item. For doing this it will have to access every item not just as MediaItem but as a true Song or Movie. For it to access the artist or director property off the Song or Movie for using it in the description, this is necessary.

In the following example, each item present in the array might be a Song or it might be a Movie. We cannot know the actual class in advance, for using it with each item. In such situations, using the type cast operator (as?) conditional form for checking the downcast every time in the loop is appropriate.

*   for item in library {
*   if let movie = item as? Movie {
*   print("Movie: '\(movie.name)', dir. \(movie.director)")
*   } else if let song = item as? Song {
*   print("Song: '\(song.name)', by \(song.artist)")
*   }
*   }

*   // Movie: Avatar, dir. James Cameroon
*   // Song: 'They Don’t Care About Us', by Michael Jackson
*   // Movie: 'The Lord of the Rings', dir. Peter Jackson
*   // Song: 'Bohemian Rhapsody', by Freddie Mercury
*   // Song: 'summer of 69', by Bryan Adams

The example above starts by attempting to downcast the item as a Movie. The Movie might possibly be a MediaItem instance and similarly the Song can be too, and it is equally possible. Due to this uncertainty, an optional value will be returned by the typecast operator’s as? form when it tries to downcast to a subclass type. The resultant of the as? Movie item will be of the Movie? type or optional movie.

The downcast of the Movie will fail when it is applied to the instances of the song in the library array. The above example makes use of an optional binding for checking whether the value is actually contained in the Movie, for coping with this. This is basically to find if the downcast is a success. In writing, the optional binding will look like “if let movie = item as? Movie” and it can be read as:

“Try accessing the item as Movie. If it succeeds, temporary constant will be set, called movie, and this value will be stored in the optional Movie returned.”

If downcasting is a success, the movie properties will be used for printing the description of the Movie instance, which includes the director's name. A principle similar to this is used for checking the Song instances, for painting the appropriate description every time after finding the Song in the library.

Note: The instances will not be modified or the values will not be changed by typecasting. The instance underlying will be the same. For instance is simply accessed and treated like the instance type that is to be casted.

Type Casting for Any and AnyObject

Swift provides two special type aliases for working with non-specific types:

AnyObject can represent an instance of any class type.

Any can represent an instance of any type at all, including function types.

Note: Use Any and AnyObject only when you explicitly need the behavior and capabilities they provide. It is always better to be specific about the types you expect to work with in your code.

### AnyObject

When working on the Cocoa APIs, it is only normal to receive the [AnyObject] type array, or “an array of values of any object type”. The reason for this is that there are no explicitly typed arrays in Objective-C. But, if you are confident about the object type present in an array like that, from the API information that the array provided, you can use the as! typecast operator, a forced version, for downcasting every item in the array to a class type more specific than the AnyObject, without optional unwrapping.

A [AnyObject] type array will be defined by the below example and three instances of the class Movie will be added.

*   let someObjects: [AnyObject] = [
*   Movie(name: "2001: A Space Odyssey", director: "Stanley Kubrick"),
*   Movie(name: "Moon", director: "Duncan Jones"),
*   Movie(name: "Alien", director: "Ridley Scott")
*   ]

As this array only contains Movie instances, it can be directly downcasted and unwrapped into a non-optional Movie using the as! typecast operator (forced version).

*   for object in someObjects {
*   let movie = object as! Movie
*   print("Movie: '\(movie.name)', dir. \(movie.director)")
*   }
*   // Movie: '2001: A Space Odyssey', dir. Stanley Kubrick
*   // Movie: 'Moon', dir. Duncan Jones
*   // Movie: 'Alien', dir. Ridley Scott

Instead of downcasting each item separately, the array someObjects can be downcasted to the [Movie] type, for short forms of the loop:

*   for movie in someObjects as! [Movie] {
*   print("Movie: '\(movie.name)', dir. \(movie.director)")
*   }
*   // Movie: '2001: A Space Odyssey', dir. Stanley Kubrick
*   // Movie: 'Moon', dir. Duncan Jones
*   // Movie: 'Alien', dir. Ridley Scott

## Any

In this example, we will use Any to work along with a combination of different types, which include non-class types and function types. An array called things will be created in this example and it can store the type Any values.

*   var things = [Any]()

*   things.append(0)
*   things.append(0.0)
*   things.append(42)
*   things.append(3.14159)
*   things.append("hello")
*   things.append((3.0, 5.0))
*   things.append(Movie(name: "Ghostbusters", director: "Ivan Reitman"))
*   things.append({ (name: String) -> String in "Hello, \(name)" })
*   Two Int values, a String value, two Double values, the movie “Ghostbusters”, a tuple of type (Double, Double), and a closure expression which takes and returns a String value are contained in the things array.

The is and as operators can be used with the cases in the switch statement for discovering a specific type of variable or a constant, which is only to be of AnyObject type or Any type. The below example iterates over the things array items and it will then query each item type with the switch statement. Several cases of the switch statement bind a constant of a specific type with their matched value, for enabling the value to be printed:

*   for thing in things {
*   switch thing {
*   case 0 as Int:
*   print("zero as an Int")
*   case 0 as Double:
*   print("zero as a Double")
*   case let someInt as Int:
*   print("an integer value of \(someInt)")
*   case let someDouble as Double where someDouble > 0:
*   print("a positive double value of \(someDouble)")
*   case is Double:
*   print("some other double value that I don't want to print")
*   case let someString as String:
*   print("a string value of \"\(someString)\"")
*   case let (x, y) as (Double, Double):
*   print("an (x, y) point at \(x), \(y)")
*   case let movie as Movie:
*   print("a movie called '\(movie.name)', dir. \(movie.director)")
*   case let stringConverter as String -> String:
*   print(stringConverter("Michael"))
*   default:
*   print("something else")
*   }
*   }

*   // zero as an Int
*   // zero as a Double
*   // an integer value of 42
*   // a positive double value of 3.14159
*   // a string value of "hello"
*   // an (x, y) point at 3.0, 5.0
*   // a movie called 'Ghostbusters', dir. Ivan Reitman
*   // Hello, Michael

### Nested Types

Enumerations are usually created by supporting the functionality of a specific class or a structure. Similarly, we can define the utility structures and classes for our convenience and they will be purely used within a more complex type context. For accomplishing this, you can define nested  types in swift. Here, you can nest to the supporting structures, classes and enumerations inside the definition of the type, which they support.

By writing the definition of the type inside the outer braces of the time, which it supports, you can nest a type inside another. There is no limit for nesting types and it can be taken to as many levels as required.

Nested Types in Action

In the example given below, a structure called BlackjackCard is defined. This structure models a playing card just like the one used in the blackjack game. Suit and Rank are they to nested enumeration types contained in the blackjack structure.

The ace cards in blackjack can have the value of 1 or 11\. A structure call Values is used for representing this feature and this is nested inside the Rank enumeration:

*   struct BlackjackCard {

*   // nested Suit enumeration
*   enum Suit: Character {
*   case Spades = "♠", Hearts = "♡", Diamonds = "♢", Clubs = "♣"
*   }

*   // nested Rank enumeration
*   enum Rank: Int {
*   case Two = 2, Three, Four, Five, Six, Seven, Eight, Nine, Ten
*   case Jack, Queen, King, Ace
*   struct Values {
*   let first: Int, second: Int?
*   }
*   var values: Values {
*   switch self {
*   case .Ace:
    *   return Values(first: 1, second: 11)
*   case .Jack, .Queen, .King:
    *   return Values(first: 10, second: nil)
*   default:
    *   return Values(first: self.rawValue, second: nil)
*   }
*   }
*   }

  // BlackjackCard properties and methods

*   let rank: Rank, suit: Suit
*   var description: String {
*   var output = "suit is \(suit.rawValue),"
*   output += " value is \(rank.values.first)"
*   if let second = rank.values.second {
*   output += " or \(second)"
*   }
*   return output
*   }
*   }

The enumeration Suit is used for describing the four playing card suits along with the Character value which represents their symbol.

All possible card ranks are described by the Rank enumeration along with a raw Int value, which is used for representing their face value excluding the Ace, Jack, King and Queen and Jack cards.

A nested structure called Values is nested within the Rank enumeration as mentioned above. Almost all of the cards except the Ace, which has two values, have a single value and this structure encapsulates this fact. The two properties are defined by the Values structure for representing this:

first, of type Int

second, of type Int?, or “optional Int”

A computed property, Values, is a defined in the Rank and this returns the Values structure’s instance. The rank of the card will be considered by this computed property and basing on the rank, a new instance of Values will be initialized with appropriate values. Special values will be used for the Ace, King, Queen and Jack cards. It will use the raw Int value of rank for all the other numeric cards.

Suit and Rank are the two properties of the structure BlackjackCard. A computed property, description is also defined in it. This uses the store the values from the Rank and Suit for building a description of the value and name of the card. An optional binding will be used by the description properly for checking if there is a 2nd value to be displayed. If there are any, it will insert additional description detail for it.

As there are no custom initialisers for the BlackjackCard structure, there is an implicit memberwise initializer for it and it is described in the structure type memberwise initializer. this initializer can be used for initializing a new constant called AceOfSpades.

*   let theAceOfSpades = BlackjackCard(rank: .Ace, suit: .Spades)
*   print("theAceOfSpades: \(theAceOfSpades.description)")
*   // prints "theAceOfSpades: suit is♠, value is 1 or 11"

As you can see, Suit and Rank are nested inside BlackjackCard. From the context, we can infer their type. The enumeration cases can be referred by the initialisation of the instance. The reference will be through their case names. From the examples given above, description property reports that the value of 1 of 11

## Referring to Nested Types

For using a nested type out of the context definition, the name of the type should be prefixed with its name.

let heartsSymbol = BlackjackCard.Suit.Hearts.rawValue

// heartsSymbol is "♡"

For the above example, the names of Rank, Suit, and Values are kept short deliberately, and this is because those names are qualified naturally by the content where they are defined.

## Function Types as Parameter Types

In swift, you are allowed to use the function types like (Int, Int) -> Int as another function’s parameter type. With this, you can leave some of the function implementation aspects for the caller of the function whenever the function is called.

Given below is an example which will print the results from the above math functions.

*   func printMathResult(mathFunction: (Int, Int) -> Int, _ a: Int, _ b: Int) {
*   print("Result: \(mathFunction(a, b))")
*   }
*   printMathResult(addTwoInts, 3, 5)
*   // prints "Result: 8"

In this example, a function called printMathResult(_:_:_:) is defined and this function has three parameters. The first parameter of the function is mathFunction. The type of the first parameter is (Int, Int) -> Int. Functions of the same type can be passed as the arguments for the mathFunction parameter. a and b are the second and the third parameters. The second and the third parameters are of the Int type. For the math function provided, these parameters will be used as the input values.

When we call the printMathResult(_:_:_:) function, the function addTwoInts(_:_:) will be passed with 3 and 5 as integer values. This will now call the function provided with 3 and 5 as values and this will print 8 as the result.

Printing the result is the role of the function printMathResult(_:_:_:). This will print the math function call of an appropriate type. The implementation of the function doesn't matter here. The only thing that matters here is the type of the function, which needs to be correct. With this, the function printMathResult(_:_:_:) will hand some of the functionality to the one which calls the function. This will happen in type-safe way.

## Function Types as Return Types

The function type of a given can be used as the return type for another function. This can be accomplished by giving the complete functional type right after -> of the returning function.

Two simple functions stepForward(_:) and stepBackward(_:) are defined in the next example. The function stepForward(_:) returns a value one more than the input value and the function stepBackward(_:) returns one less value than the input value. The type of both the functions is of (Int) -> Int:

*   func stepForward(input: Int) -> Int {
*   return input + 1
*   }
*   func stepBackward(input: Int) -> Int {
*   return input - 1
*   }

Here there is a function chooseStepFunction(_:) which has the return type “a function of type (Int) -> Int”. The function ``stepForward(_:) or the function stepBackward(_:) will be returned by the function ThechooseStepFunction(_:), basing on the Boolean parameter.

*   func chooseStepFunction(backwards: Bool) -> (Int) -> Int {
*   return backwards ? stepBackward : stepForward
*   }

Now you can use the chooseStepFunction(_:) for obtaining a function which steps in a direction or in other direction.

*   var currentValue = 3
*   let moveNearerToZero = chooseStepFunction(currentValue > 0)
*   // moveNearerToZero now refers to the stepBackward() function

The above example determines if a positive step or a negative step is needed for moving the variable currentValue closer to 0, progressively.

The initial value of the currentValue is 3 and it means that the currentValue > 0 is true in this case. This will make the chooseStepFunction(_:) return the function stepBackward(_:). We use a constant moveNearerToZero for storing the returned function reference.

The moveNearerToZero now refers the right function and hence it can be used for counting to 0:

*   print("Counting to zero:")
*   // Counting to zero:
*   while currentValue != 0 {
*   print("\(currentValue)... ")
*   currentValue = moveNearerToZero(currentValue)
*   }
*   print("zero!")
*   // 3...
*   // 2...
*   // 1...
*   // zero!

## Nested Functions

All the functions that you have seen so far are examples of global functions. Global functions will be defined at a global scope. You are also allowed to define functions within other functions. These functions are called nested functions.

By default, all the nested functions will be hidden from others. Though they are hidden, the nested functions can be used and called by using their enclosing function. The enclosing function can return any one of the nested functions of its own and allow the nested functions to be available in another scope.

*   The chooseStepFunction(_:) example can be rewritten for using and returning the nested functions:
*   func chooseStepFunction(backwards: Bool) -> (Int) -> Int {
*   func stepForward(input: Int) -> Int { return input + 1 }
*   func stepBackward(input: Int) -> Int { return input - 1 }
*   return backwards ? stepBackward : stepForward
*   }
*   var currentValue = -4
*   let moveNearerToZero = chooseStepFunction(currentValue > 0)
*   // moveNearerToZero now refers to the nested stepForward() function
*   while currentValue != 0 {
*   print("\(currentValue)... ")
*   currentValue = moveNearerToZero(currentValue)
*   }
*   print("zero!")
*   // -4...
*   // -3...
*   // -2...
*   // -1...
*   // zero!

# Chapter 7: Creating Your First iOS App

Now that you have learned the basics of Swift programming, and have learned how to create a Tip Calculator class, it’s time to learn how to make your very first iOS app. We are going to use the Tip Calculator class that you developed and create a user interface for it.

## Getting Started

*   Gt XCode started up and open
*   File\New\Project
*   Choose iOS\Application\Single View Application
*   Click Next
*   Where it asks for the product nam, enter TipCalculator
*   Set the language as Swift
*   Set Devices to iPhone
*   Check that the box next to Use Core Data is not ticked
*   Click on Next
*   Choose the directory where you want to save your new project and click on Create

Now lets take a look at what XCode has done for you.  In the top left corner of XCode, click on iPhone 6 Simulator and then click Play. You should see a splash screen saying Tip Calculator and then a blank screen will appear. The next step is to fill that blank page up!

## Creating Your Model

Before we get on to creating the user interface, we need to create a model for the app. The model is a set of classes that are representative of the data in your app and of the operations that your app is going to perform on the data. 

For the purposes of this tutorial, your model is going to be the TipCalculator class that you created in the playground but you are going to rename it TipCalculatorModel.

To add this class, open

*   File\New\File
*   Select iOS\Source\Swift File
*   Call it TipCalculatorModel.swift,
*   Click on Create

What you are going to do is move your playground file to a swift file because you cannot call up code that is in a playground file – these are just for testing purposes.

Open TipCalculator.swift

Copy the class from your playground file (not the testing lines at the bottom) into the Swift file and make these changes

Rename the class to TipCalculatorModel

You need to change total and taxPct to variables

You will need to change subtotal to a computed property and you do this by replacing the subtotal property with the following code:

*   var subtotal: Double {
*   get {
*   return total / (taxPct + 1)
*   }
*   }

Computed properties don’t store values, they are computed on other values. Here you are going to be calculating the subtotal whenever it is accessed, going on the values of total and taxPct

Next, you need to delete the entire line that sets subtotal in init and get rid of any comments in the file.

When you are finished, your file should look like:

*   //
*   //  TipCalculatorModel.swift
*   //  TipCalculator
*   //
*   //  Created by Main Account on 12/18/14.
*   //  Copyright (c) 2014 Razeware LLC. All rights reserved.
*   //
*   import Foundation
*   class TipCalculatorModel {
*   var total: Double
*   var taxPct: Double
*   var subtotal: Double {
*   get {
*   return total / (taxPct + 1)
*   }
*   }
*   init(total: Double, taxPct: Double) {
*   self.total = total
*   self.taxPct = taxPct
*   }
*   func calcTipWithTipPct(tipPct: Double) -> Double {
*   return subtotal * tipPct
*   }
*   func returnPossibleTips() -> [Int: Double] {
*   let possibleTipsInferred = [0.15, 0.18, 0.20]
*   let possibleTipsExplicit:[Double] = [0.15, 0.18, 0.20]
*   var retval = [Int: Double]()
*   for possibleTip in possibleTipsInferred {
*   let intPct = Int(possibleTip*100)
*   retval[intPct] = calcTipWithTipPct(possibleTip)
*   }
*   return retval
*   }
*   }

Now that your app model is ready, it’s time to look at views!

# Chapter 8:  Introduction to Storyboards and Interface Builder

Your user interface is going to be created in something called Storyboard and XCode includes Interface Builder, a neat tool that lets you easily edit Storyboards. Interface Builder lets you lay out everything – buttons, labels, text fields and all the other controls that are in your app by dragging and dropping. These are called Views. Look on the left hand side of XCode and click on Main.storyboard. This will bring up the Interface Builder. This is quite detailed so we will cover one part of the screen at once:

On the left is Project Navigator – where your project files show up

On the left of Interface Builder is Document Outline – your views can be seen at a glance for each screen of your app – make sure you click on the down arrows beside the items to see the entire document.

At the moment, your app has just one view controller but we are going to be adding stuff into this very soon.

Look to the left of your view controller, there is an arrow. This shows that this is the Initial View Controller – this is the first page displayed when your app opens. This can be changed by dragging the arrow to another view controller.

Now look at the bottom of the Interface Builder – you will see the words “w Any” and “h Any”. This shows that your app is being edited to work on any size interface.

At the top of the View Controller, there are three small icons – these represent the controller, First Responder and Exit. You don’t need to worry about these for the purpose of this tutorial.

Look at the bottom right hand side of Interface Builder and you will see four icons that are related to Auto Layout – again, you will not be using those in this tutorial.

At the top right hand side of Interface Builder there are Inspectors – these are for whatever has been selected in the Document Outline. See that there are several tabs – you will be making a good use of these in this tutorial.

Last but not least, bottom right of the Interface Builder are the Libraries. These list the different types of view controllers that you can add into your app.

## Creating your Views

If you remember, your TipCalculatorModel class has a pair of inputs – a tax percentage and a total. What would be good for users of your app is if they could type the total in using the numeric keyboard on their iPhone – that’s where a text field comes in handy. Because the tax percentage is generally restricted to a smaller value range, you will use a slider for that.

As well as the text field and the slider, you will need a label for each one, a button that performs the calculation, a navigation bar showing the name of the app and a text field that displays the results. 

If you are ready, let’s begin to build the user interface for your app, one piece at a time:

1.  Navigation Bar – instead of directly adding this, go to the document outline and select the view controller. Now go to Editor\Embed In\Navigation Controller. This sets a navigation bar in your view controller – double click on it and input the text as Tip Calculator.
2.  Labels – Go into the Object Library and drag a label in to the view controller. Double click the label and put the text as Bill Total (Post-Tax):.. Now select that label and go to the fifth tab on the Inspectors section – this is the size inspector. Set it as X=33 and Y=81\. Do the same for another label but set the text as Tax Percentage (0%):, X=20, and Y=120.
3.  Text Field – go to the Object Library and drag a text field to the view controller. Click on the Attribute Inspector and set Keyboard Type=Decimal Pad. Go to the Size Inspector and set X=192, Y=77, and Width=392.
4.  Slider – Go to the Object Factory and drag a slider in and then go to the Attribute Inspector and set Minimum Value=0, Maximum Value=10, and Current Value=6\. Then go to the Size Inspector and set X=190, Y=116, and Width=396
5.  Button – Back to the Object Library and drag a button in. Double click on it and put the text to Calculate then set the Size Inspector to X=268 and Y=154
6.  Text View – Drag a Text View from the Objects Library and then double click on it and delete the text that is there. Go to the Attributes Inspector and ensure that Editable and Selectable have not been checked. Go to the Size Inspector and set X=16, Y=192, Width=568, and Height=400.
7.  Tap Gesture Recognizer - Back to the Object Library and drag in a Tap to Gesture Recognizer to the main view. This is going to tell when a user taps on the view to shut the keyboard down.
8.  Auto-Layout – Interface Builder is great for building a good auto-layout constraint automatically. To do this, go to the Document Outline and click on Main View. Then click the third button in bottom right of the Interface Builder and select Add Missing constraints.

Now you can build the app and run it on the iPhone 6 Simulator and you will see a working basic user interface!

## A View Controller Tour

Ok, you have new created an app model and the app views so now it’s time to look at the view controller.

Open ViewController.swift. This will show you the code for your view controller, or screen, in the app. This is the part that is responsible for managing communication between the model and the views. Look at the class and you will see the following code:

*   // 1
*   import UIKit
*   // 2
*   class ViewController: UIViewController {
*   // 3
*   override func viewDidLoad() {
*   super.viewDidLoad()
*   // Do any additional setup after loading the view, typically from a nib.
*   }
*   // 4
*   override func didReceiveMemoryWarning() {
*   super.didReceiveMemoryWarning()
*   // Dispose of any resources that can be recreated.
*   }
*   }

Now, you will see a few elements of code here that you are not yet familiar with so let’s look at them one at a time:

iOS is split into multiple frameworks and each one contains different code. Before you can use code from a framework, you must import it. The framework that contains the base class for the view controllers is called UIKit and it also contains the text fields, buttons and more besides. This is the first time in this tutorial you have seen an example of subclasses and you are declaring a new class called ViewController – a subclass of UIViewController. To see how that works, replace the class declaration with:

*   class UIViewController {
*   }

You can see that UIKit.UIViewController is referring to UIViewController class in the namespace for UIKit.

The Override method is called with a root view of the view controller when first accessed. If you override a method, you must use the override keyword so that you don’t end up overriding a method in error.

The Memory Function method is called when the iPhone is low on memory.

## Connecting your View Controller to your Views

Now you have some understanding of the view controller class, it’s time to add in properties for the sub views and get them in to the Interface Builder. To do this, go to your ViewController class, locate viewDidLoad and insert the following code just before that:

*   @IBOutlet var totalTextField : UITextField!
*   @IBOutlet var taxPctSlider : UISlider!
*   @IBOutlet var taxPctLabel : UILabel!
*   @IBOutlet var resultsTextView : UITextView!

You are declaring four different variables:

*   UITextField
*   UISlider
*   UILabel
*   UITextView

There are two differences between this and the way you did it with the playground file:

The prefix on these variables is @IBoutLet. Interface Builder goes through your code looking for these and this is what allows you to connect the variables to the views.

Each Variable is marked with an ! to indicate that these are optional values but have been implicitly unwrapped. This is a posh way of saying that your code is written as if set and that, if it isn’t set your app will just crash.

Let’s have a go at connecting these to the elements in the user interface:

*   Open Main.storyboard
*   Select the view controller n Document Outline
*   Open  Connections Inspector – tab number 6

Here you will see the properties you created previously, listed under Outlets.

Look to the right of resultsTextView - you will see a little circle. Press on CTRL and drag from the button to the Text View, which is under the Calculate button. Let go and the property will be connected to the view.

Do this for all of the other properties, making sure each one connects to the correct element.

## Connecting Actions to your View Controller

Now we are going to connect actions to methods so:

Open up ViewController.swift

Add in the following code anywhere within the class:

*   @IBAction func calculateTapped(sender : AnyObject) {
*   }
*   @IBAction func taxPercentageChanged(sender : AnyObject) {
*   }
*   @IBAction func viewTapped(sender : AnyObject) {
*   }

This signature has to be present whenever you declare a callback for actions form views. The signature is basically a function that has no return value, it takes one parameter of type AnyObject and this represents a class of any type.

To make sure that Interface Builder has spotted the new methods you inserted, these have to be marked with the keyword @IBAction.

Now go back to Main.storyboard and check that your view controller has been selected in Document Outline. Check that the 6th tab – Connections Inspector - is open and look in the Received Actions section – your new methods will be listed in there.

Look to the side of calculateTapped: and locate the circle; drag from that circle up to the button labelled calculate. A popup screen will appear, choose Touch Up Inside. By doing this, you are saying that “when the user releases their finger from the screen when over the button, call my method calculateTapped:“.

Repeat for the remaining new methods and make sure they go to the right places:

taxPercentageChanged must be dragged to the slider and connected to value Changed – this section is called when a user touches the slider in the app

viewTapped must be dragged to Tap Gesture Recognizer, which is in Document Outline. You will not need to select a gesture for this one.

## Connecting Your View Controller to your Model

You have almost finished building your very first iOS app. All that’s left is to hook the view controller to your model.

Open ViewController.swift

Add the following code to your class and a way of refreshing the interface:

*   let tipCalc = TipCalculatorModel(total: 33.25, taxPct: 0.06)
*   func refreshUI() {
*   // 1
*   totalTextField.text = String(format: "%0.2f", tipCalc.total)
*   // 2
*   taxPctSlider.value = Float(tipCalc.taxPct) * 100.0
*   // 3
*   taxPctLabel.text = "Tax Percentage (\(Int(taxPctSlider.value))%)"
*   // 4
*   resultsTextView.text = ""
*   }

Add a call to refreshUI, underneath viewDidLoad

*   refreshUI()
*   Implement viewTapp and taxPercentageChanged with the following code:
*   @IBAction func taxPercentageChanged(sender : AnyObject) {
*   tipCalc.taxPct = Double(taxPctSlider.value) / 100.0
*   refreshUI()
*   }
*   @IBAction func viewTapped(sender : AnyObject) {
*   totalTextField.resignFirstResponder()
*   }

And finally implement calculateTapped with this code:

*   @IBAction func calculateTapped(sender : AnyObject) {
*   // 1
*   tipCalc.total = Double((totalTextField.text as NSString).doubleValue)
*   // 2
*   let possibleTips = tipCalc.returnPossibleTips()
*   var results = ""
*   // 3
*   for (tipPct, tipValue) in possibleTips {
*   // 4
*   results += "\(tipPct)%: \(tipValue)\n"
*   }
*   // 5
*   resultsTextView.text = results

That’s it, your app has been successfully completed, simply build it, run it and revel in the fact that you made it!

# Chapter 9: Writing an iOS App with Swift – Advanced

The app you wrote in the last chapter was a basic tip calculator, just to give you an idea of how to get around Swift. This time, we are going to try something a little more complex and involved. Follow every step as outlined below and you will successfully write a full iOS app in Swift.

## What You Need

*   A Mac computer with Mavericks or Yosemite installed
*   XCode 6
*   A basic understanding of Swift, which you should have gained through the rest of this book

## Getting Started

Earlier in the book, I showed you how to install XCode so, follow those instructions once again. As soon as it is all installed and set up, open XCodeand create a brand new project–press cmd+shift+N.

Got to the Template Selector and check that iOS→Application has been selected

Then choose the template called Master-Detail Application

This template is an excellent starting point because it already has the storyboard set up with just about everything you will need. It also has a controller for the Detail controller and the Master controller. The reason we are using this template is because you are going to create a task list app.

When you have chosen the Master Detail Application template, click on Next to go on to the next part of the set up.

On the next screen, you will see the project set up wizard and here you will need to complete a few details and choose some options.

Start off by naming your app. Type the name into the product name field. You can call it whatever you like so long as you remember it but, for the purposes of this tutorial, I am calling it TaskMe.

The next step is to complete the Organization Name field correctly and then go to the Organization Identifier field. Here you will use a reverse domain name notation for the identifier.

The Organization Identifier is going to help you to create the Bundle Identifier, which is what will give your application a name that is unique and this is for Apple and all of your iOS devices.

Select and click on Language and, from the drop down menu, check to see that Swift has been selected, not Objective C. By doing this, most of the code that XCode generates will be generated as Swift files and not files for Objective C.

The last step is to click on Devices and from the drop down menu choose iPhone. Check that the option for Core Datais NOT checked. While Core Data is great to learn, we don’t need it for this tutorial.

## Learning by Example

Before we jump straight int writing some custom code, I want to just go over what you can learn from the code that was generated through XCode, after you chose the Master Detail Application template. This is already a working application so you do need to build and run it to see what it can do already–cmd+R.

When you play around with it, you will see that you land on a List screen with a + and an edit button showing on the navigation bar. Click on +to add a new row into the list. The list will show the date and time that the row was added. If you tap or click on that row you will see a details screen with the data and time in the middle. On the list screen you can delete rows in two ways–swipe on them and tapping Delete or by tapping on Edit and deleting them through there.

So, moving on, let’s take a look at the code already generated by XCode.

## AppDelegate.swift

The starting point of your application is a file called AppDelegate.swiftso let’s have a look at the code it contains. Ignore the comments that you see at the top of the file and go to the first piece of code. It should read

*   Import UIKit

This piece of code is going to allow you to access all that is available in UIKit. If you have done any programming with Objective C then you will find this very familiar but unlike Objective C, you will be importing an entire module instead of header files for a particular framework or class. You will do this in virtually every file in an application, whether it is for UIKit or for the simpler Foundation files.

On to the next line of code, it looks a little strange:

*   @UIApplicationMain

In Swift, you will find that there is not a mail file like there is in most other computer programming languages. Instead, when you are programming an iOS application, you will need to point XCode to the specific file that you want to be classed as the main file. You do this by adding the above attribute to a Swift class. It is highly unlikely that you will even move this from where XCode locates it but it is a good idea to know exactly what this strange little piece of code does.

Now we have a class definition for the AppDelegate file. If you look at it, you will see that it inherits from UIResponder and from the UIApplicationDelegate protocol. If you came from programming Objective C, you will see that this syntax is a massive improvement over the way we used to do it.

*   class AppDelegate: UIResponder, UIApplicationDelegate {

Have a look at the way the AppDelegate class has been implemented and you should notice that there is actually very little going on here. What you have is a window variable and a number of functions that are either empty or have very little in them.

In fact, the only function that contains code that is executable is

*   application:didFinishingLaunchingWithOptions:

But all that is doing is returning true

*   func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {
*   // Override point for customization after application launch.
*   return true
*   }

What is going on and the reason why this application is still working, is all down to some behind the scenes magic. If you take a look at the settings for your project, you will see that the launching point has been set as Main.storyboard and this s responsible for setting up the window and the controllers when your application launches.

The only other piece of code that is worth a mention at this stage is the variable definition for the window:

*   var window: UIWindow?

This is going to be responsible for creating a variable property in AppDelegate and with a UIWindow, which is optional, as its type. This is expressed, as you can see from the example above, as UIWindow?  –take note of the question mark that ends the code.

If you haven’t yet learnt anything about optionals, the idea behind them is that they are the only types that can contain something or nothing, i.e. be nil. You don’t need to know a whole lot about them for this tutorial but, if you intend to work with the Cocoa Touch Framework.

There is one important thing you must keep in mind about optionals and that is the way they are used in parameter types. You will see that some types in Swift end with an exclamation point. This known as an implicitly unwrapped optional

*   @IBOutlet weak var detailDescriptionLabel: UILabel!

The difference between an ordinary optional and an implicitly unwrapped optional is that, if you try to use the latter when it doesn’t have a value, you will get a runtime error, just like you were to try to unwrap a normal optional and use it with no value. This is why these optionals are only used in places where it is highly unlikely that there would not be a value. If there were no value, it would cause a serious error.

You may also have noticed that the second parameter contains two names

*   application:didFinishLaunchingWithOptions:

The first name is didFinishLaunchingWith0ptions and, when the function is called, this acts as the public name. The second name is launch0ptions and this plays the part of the name of the constant when it is used inside the scope of that particular function.

*   func application(application: UIApplication, didFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool {

## MasterViewController.swift

If you open up this file, you will see that there is quite a lot going on in it. You have already seen import in AppDelegate and you may already have figured out that MasterViewController class inherits from UITableViewController. I won’t be going over each and very little piece of code in this, only those that are interesting in that they provide substantial improvements on when you compare how it would have been done in Objective C.

So, taking a brief look at this code, there is one more thing that stands out – the keyword override and how it has been used before virtually all functions:

*   override func awakeFromNib() {
*   override func viewDidLoad() {
*   override func didReceiveMemoryWarning() {

Most of these functions have already been defined in the MasterViewController super class, or somewhere along the ancestry chain and, as such, you must explicitly tell the compiler that you are definite that you want to override or extend the functions that already exist in the ancestor functions. This helps to cut down on the risk of errors if you use a function name by accident, which has already been used elsewhere. If you managed to do this, everything would break.

So, looking at the MasterViewController, you can see the first part is the objects variable property definition, which has been initialized using the empty NSMutableArray()

*   var objects = NSMutableArray()

When the view for your controller has completed loading, the viewDidLoadmethod will be called. This function will begin by calling the superclass method–you will begin to see that this is done with virtually all functions like this.

The superclass call is followed by the right and left bar button items being set up. What is interesting to note here is the use of addButton, which is a constant. This is suggested for all similar items that will not change after they have been created. The other interesting part is UIBarButtonItem being initialized:

*   UIBarButtonItem(barButtonSystemItem: .Add, target: self, action: "insertNewObject:")

Instead of the somewhat verbose syntax used in Objective C, where you would call alloc followed by initWithWhatever, Swift does away with that and uses named arguments in the initializer instead.

You should also note that the way we tell it the type of UIBarButtonSystemItem we want to use is much nicer. Instead of typing UIBarButtonSystemAdd, instead you can just use. Add. You can do this because of Swift’s ability to infer type–it will simply pick up on what you are doing and infer the correct type automatically.

Take a look at insertNewObject: and you will see that there is an interesting type for the sender parameter, AnyObject

*   func insertNewObject(sender: AnyObject) {

You don’t need to do anything with that inside this function so let’s have a look at tableView:cellForRowAtIndexPath: which will have an impact on you

*   override func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell {
*   let cell = tableView.dequeueReusableCellWithIdentifier("Cell", forIndexPath: indexPath) as UITableViewCell
*   let object = objects[indexPath.row] as NSDate
*   cell.textLabel?.text = object.description
*   return cell
*   }

Notice on the first line of the function tableView:cellForRowAtIndexPath we have called dequeueeusableCellWithIdentifier:forIndexPath on the table view. For this method, the return type is AnyObject.

Any class could be returned from this particular function call so you will need to type cast it by using the as UITableViewCell that you can see at the end of the line. Later on, you will change this to be the custom cell class of taskCell, which you will be creating later on.

When you are working with Cocoa frameworks, this is common, because there is a need for compatibility with the old style used in Objective C, where id would be the return type, meaning a pointer to any object. Bear in mind that Swift avoids the use pointers wherever it can and this is why solutions such as this have been created, keeping your code much safer.

The last part that is interesting is the syntax used for mark comments, which work to help split and let you jump through the files:

*   // MARK: - Table View

When you use this syntax for a comment, you can split a file up, which makes it far easier to jump through it. This also helps readers to see exactly what a set of functions are related to in the file.

## DetailViewController.swift

There is one more file we need to look at – the DetailViewController. This is a small file compared to the MasterViewController but it does have a number of very good examples of how Swift works to help you write much better code.

To start with, we have the @IBOutlet attribute, which is for the variable detailDescriptionLabel. In a similar way to how it was in the header files in Objective C, this particular variable attribute tells Interface Builder about this particular property on your DetailViewController:

*   @IBOutlet weak var detailDescriptionLabel: UILabel!

You may also have spotted that this variable has been defined as weak because you do not want DetailViewController to own the view.

Next, there is a variable property definition that looks interesting. This has a bit of extra code attached to it to define the behavior of a property that is right beside its definition:

*   var detailItem: AnyObject? {
*   didSet {
*   // Update the view.
*   self.configureView()
*   }
*   }

There is also an optional AnyObject? Type but the most interesting bit is didSet code block.

Properties are able to contain blocks of code that will execute as a callback to a specific event. The best part about this is that, rather than defining a specific setter that will do this, you can actually have a much clearer definition of what the code is doing there.

This piece of code now states, very clearly, that once detailItem has been set, at any time from now on configureView has to be called. This is because something that pertains to the view has changed. These callbacks are something of a large leap for iOS applications, in terms of the expressive nature of the code.

Ow, earlier on, we talked briefly about optionals because they are used quite a lot in iOS coding for applications so here is another example for you on how these optionals are used.

*   func configureView() {

*   // Update the user interface for the detail item.
*   if let detail: AnyObject = self.detailItem {
*   if let label = self.detailDescriptionLabel {
*   label.text = detail.description
*   }
*   }
*   }

Notice that optional binding is used in an IF statement. This means that if the assignment expression on the right has a value, it will be assigned to the left through the duration of the IF body. If that expression does not have a value, the IF statement body will be ignored. This is similar to the way we checked for nil in Objective C but is a much safer and more expressive way of doing it.

## Coming Up Next

So, in this part of this tutorial, you never actually write any code. Instead, you did something that was more important. You looked at how Swift has an effect on the way we work with the Cocoa Touch classes and API’s/ Without this, you would find yourself fighting against Swift as you try to write applications the way you would have done previously.

What you have done is learn about how to make developing you application much safer, without running the expressive nature of the Swift programming language. You can clearly see that Apple has put great consideration into integration with their existing frameworks and have made sure that they have not missed out even one small detail.

With this part of the tutorial out of the way, it’s time to start looking at building your application. So, going back to the TaskMe application that you generated at the beginning, using XCode 6, we now need to start adding in some true functionality

Using the“TaskMe”application that you generated in XCode 6, it is time to start adding some real functionality.

## Your First Feature

The first feature that you are going to add in is the ability to add a new task to your list. Once this feature has been created, all you will need to do is tap the + button, type the name of the title of the task and a few notes if you like, and, as soon as you ta Save you will automatically go back to your list of tasks.

## Setting up The Storyboard

We want to make things nice and simple for your users so it would be good if all they had to do was tap on the + button to have a new controller automatically pop up. So, to start on this, open up Main.storyboard.

You are going to use two controllers to do this:

*   UINavigationController
*   UIViewController 

The latter will be embedded in the new UINavigationController (you will not be reusing the one that is already on your screen as that is for the main workflow. So, go to the bottom right hands side of the XCode screen and drag out the UINavigationController and the UIViewController from the object library int the editor area.

Now delete the table view controller that UINavigationController created, hold down CTRL and click the UINavigationController. Drag it across to the UIViewControllerthat was created. A popup will appear–click on root view controller in the Relationship Segue section. The UIViewController will now be embedded in the UINavigationController, ensuring that you will be able to add in Cancel and Save buttons later on.

Now it’s time to set up a segue so that you can navigate to UINavigationController and UIViewController. Before you do, open the MasterViewController.swift file and delete these two lines from  viewDidLoad:

*   let addButton = UIBarButtonItem(barButtonSystemItem: .Add, target: self, action: "insertNewObject:")
*   self.navigationItem.rightBarButtonItem = addButton

Now that they have been deleted, you can also delete InsertNewObject: method.

Go back to your Main. Storyboard file and go to the object library. Drag a Bar Button Item from the library to the right hand side of the navigation bar in MasterViewController.  Now go into Attributes Inspector and change the identifier to Add.

Now it’s time to set up the segue from MasterViewController to UINavigationController. Press CTRL and drag from the new Bar Button Item that you created to the new UINavigationController. In the popup, go to the Action Segue section and choose Present Modally

The new segue will look like a rectangle inside a circle and will be part of the arrow that goes between MasterViewController and UINavigationController. Use the Attributes Inspector to set the Identifier to showAddTask

The final thing to do is set up your screen. Go to the Object Library and drag out two text fields, putting them into UINavigationController. Position them however you want to. Press on CTRL and drag the text fields and the containing view around to set the Auto Layout constraints.

Select the first Text Field; it’s now time to do a bit of editing to some of the settings inside the Attributes Inspector. First, select the empty placeholder and edit it to say Task Title. Change the size of the font to 24 points through the font editor, which you can access by clicking the T icon that is next to the font.

Now you want to be able to play around with the height, as well as the width, so change the Border style–select the second from the right. You can now have a play around with the height, perhaps make your text 60 points tall and set the alignment to centered.

Now go to the second Text Field and do something similar. Maybe make the text smaller, perhaps 16 points, make the height smaller and perhaps change the placeholder text to read something like Notes. Set the alignment to the left, rather than center this time.

Go to the UINavigationController and click on the navigation bar. Go into the Attributes Inspector and change the title to read Add Task. With all of that, you should have two fields and two controllers. The next step is to create the subclass for the UIViewController for the new Add Task screen.

Before you do that, try to run the application and you should see that you can open the new screen although, at this stage, you will not be able to navigate back.

## Creating the AddTaskViewController

Open the File menu, choose New, and then File. A shortcut for this is Cmd+N on the keyboard. This will allow you to start creating the new AddTaskController file. Ensure that you are in iOS→ Source, go into Options and select Cocoa Touch Class. Click on Next. You will see a field that says Subclass of: - type in UIViewController. Go to the Class: field and, at the front of the name in there, add in AddTask.

Make sure that the option for Also Create XIB file is left unchecked and that Swift is selected as the language. Click on Next. You will now see a file dialog popup screen. Select the location where the file is going to go – most likely the default selection will be the one you want it to go to – and then click on Create.

Before you begin to edit the file that appears, you must remember that you need to set this as the class for UIViewController that was created in the Storyboard. Open up Main. Storyboardand choose UIViewController–the one you created earlier. Go into the Identity Inspector and set the class to AddTaskViewController. You will find the Identity Inspector on the panel that is at the top left–it looks like a square and lines.

Now, your focus is on AddTaskViewController in the Interface Builder. Open the Assistant Editor (the icon in the toolbar looks something like a tuxedo) and now you can set the outlets that go between your code and the Storyboard.

Hold down CTRL and drag from each Tet Field in turn to the top of the class definition for AddTaskViewController. Each one should be named, respectively, titleField and notesField. You should end up with something that looks like this

*   class AddTaskViewController: UIViewController {
*   @IBOutlet weak var titleField: UITextField!
*   @IBOutlet weak var notesField: UITextField!
*   override func viewDidLoad() {

If you have ever used Objective C to do any iOS work, you will notice that this looks similar to what was in the header files.

@IBOutletis a declaration of that connection between your code and the Storyboard. It uses an implicitly unwrapped optional so that the set is not needed to initialize the view controller. These can be set up as soon as the views are ready; in most cases, it won’t even affect you because they will already be set by then, especially in viewDidLoad and viewWillAppear:animated.

The declaration for the variable is weak and this is to make sure that there are no references that are not necessary. Without this, the two UITextFields will be owned by AddTaskViewController and that means that the view will not be allowed to release when it wants to because the controller will be holding on to the subviews.

## Cancelling Task Creation

Next, you need to set up the Cancel button so that your task is not saved when you tap it. Instead of saving, it will hide the task creation screen. Open the Main. Storyboard file again and drag a Bar Button Item from the Object Library. Put it on the left part of the navigation bar in the AddTaskViewController screen. Now select that Bar Button Item, open the Attributes Inspector and change the Identifier to read Cancel.

You must use the standard versions of the UI elements for two reasons: accessibility and future proofing. You could have just set the title to Cancel but, let’s say that at some time in the future, Apple changes cancel to read X for example, your application will be ready for it.

Standard elements have also got accessibility already baked into them and have been well tested by the very best that Apple employs. Now, we need to hook up the Cancel button so you will need to create a new segue for Dismiss. 

To do this, open File and click on New to create a new file. In the dialog box that appears, choose iOS→Source→Cocoa Touch Class. Click on Next and then set Subclass of: to UIStoryboardSegue. The class must be set to DismissSegue. In the Language dropdown menu, make sure that Swift is selected and not Objective C.

There is one more thing you must do before this class can be used in your Storyboard. At the moment, it will currently allow a Dismiss segue to show up in Interface builder but, when it comes to runtime, it will fail. This is because there is some strange stuff going on behind the scenes in Swift. It can be fixed by explicitly defining the Objective C class name. Once that is done, Storyboard will be able to find the right class. So, change the class definition so it looks like:

*   @objc(DismissSegue) class DismissSegue: UIStoryboardSegue {

The declaration that is at the beginning - @objc(DismissSegue)– allows the class to be accessible to Storyboard. As Swift evolves, this may all change but, for now, this is the only way to do it to stop your application from crashing.

Now you need to create a perform method for the custom segue to dismiss the controller:

*   override func perform() {
*   if let controller = sourceViewController.presentingViewController? {
*   controller.dismissViewControllerAnimated(true, completion: nil)
*   }
*   }

After all of that, it’s time to run the application and see all your hard work in action.

## Saving Your Task

Now it is time to get some real value out of this–save a task. To do this you need a Save button. Back to the Main.storyboard file, drag a Bar Button Item from the objects library and put it on the right side of the navigation bar in AddTaskViewController. Ensure it is selected and the open Attributes Inspector and change the Identifier to Save.

While you are in this file, it’s a good time to clean up something else. The people who are going to use your application don’t really care that the list screen is a Master screen. As far as they are concerned, it is a Task screen so double click on Master and change it to read Tasks. Now include a Dismiss Segue between Save and MasterViewController, in the same way you did earlier with Cancel.

If you were to run your application now, you should be able to use either button to dismiss the modal–this is what you were looking to achieve. However, it would be useful to be able to add a task to the task list and to have Table View refresh to show that new task.

You need to put those tasks in a central place and you will also need a good definition of what a task is so, for now, hold off on the Save feature and move on to the next bit.

It is important that you model the core business objects separately from the interface. It will make them more flexible and more portable, important if you ever want to make your application suitable to work on all platforms. You don’t need to do much here, just create a Task struct and a TaskStore class.

## Creating the Task struct

Open File and create a new file or just press Cmd+N. This time though, you are not going to create a Cocoa Touch Class; instead, we just want a plain Swift file. Call the file Task – it will be automatically appended with .swift. Now it’s time to create a Task struct in the file:

*   struct Task {
*   let title: String
*   let notes: String
*   init(title: String, notes: String) {
*   self.title = title
*   self.notes = notes
*   }
*   }

You might be thinking at this stage that there isn’t any way of editing the file and you would be right. Instead of making it Mutable, you are going to go the way that Swift wants you to go and create an immutable value object.

When you want to make any changes to a task, all you will do is delete the old one and put a new one in its place. Your application users will just see it as an edit but, from your point of view, your life as a programmer is much easier.

## Managing our TaskStore

Now you need to create another Swift file for the TaskStore. This will be set up as a singleton, allowing you to access the one instance whenever you want. This means you will be able to add tasks or edit existing tasks as much as you want.

So, create your Swift file, like you did earlier but this time, call it TaskStore

*   class TaskStore {
*   class var sharedInstance: TaskStore {
*   struct Static {
*   static let instance = TaskStore()
*   }
*   return Static.instance
*   }
*   var tasks: [Task] = []
*   func add(task: Task) {
*   tasks.append(task)
*   }
*   func replace(task: Task, atIndex index: Int) {
*   tasks[index] = task
*   }
*   func get(index: Int) -> Task {
*   return tasks[index]
*   }
*   }

The first few lines of this code are creating a way for you to use a singleton by giving you access with TaskStore.sharedInstance. There are then a few basic functions, for get, add and replace tasks from the list.

Later on down the line you could, if you wanted, replace all of this with a more suitable TaskStore class version, one that will store all tasks across launches but this way will suffice for this tutorial.

## Finishing Your First Feature

So, now I have a small challenge for you. Finish off the Save feature that you started earlier. You do not need to worry about displaying the task list, as I will talk more about that shortly. All you need to do is try to get the tasks saved to the TaskStore–I will show the answer to this later!

A hint to help you–the trick is giving the segue that comes from the Save button a name and using the prepareForSegue:sender method.

## How it Should Look Now

So, how did you get on with that challenge? As I promised, this is the code that you should have used to get it working:

*   if segue.identifier == "dismissAndSave" {
*   let task = Task(title: titleField.text, notes: notesField.text)
*   TaskStore.sharedInstance.add(task)
*   }

You should also ensure that you have the right identifier set for every segue in the Storyboard.

Let’s just step back a second and have a bit of a refresher on what you have done to now. If you have been following this tutorial carefully, you should now have learnt quite a bit about the difference that Swift is making to the Apple frameworks and about how much cleaner it is making your code. You have also started your first feature–adding a task–which we have nearly completed. So let’s move on and complete this application.

## Finishing off Save

It’s now time to finish off so open the Main.storyboard file again and ensure that the two segues that run between AddTaskViewController and MasterViewController have got good names. Something like dismissAndCancel and dismissAndSave perhaps. This will ensure that you can easily identify them for the next step.

Open AddTaskViewController.swift and set up the prepareForSegue:sender method:

*   override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject!) {
*   if segue.identifier == "dismissAndSave" {
*   let task = Task(title: titleField.text, notes: notesField.text)
*   TaskStore.sharedInstance.add(task)
*   }
*   }

First, check that the segue you are preparing is actually the Save segues–the Cancel segue will already do exactly what you want it to do, which is precisely nothing. It is a good practice, with every segue, even if it is the only one you ae setting up, to be explicit about the segue you are running the code for. That way, if or when things change later one, the developer will know what is going on and how every little bit connects together.

It’s now time to assign a new task to a constant, using the two text fields to fill out the task. You can then use taskStore to keep the task safe by adding it into the sharedInstance.

If you run the application now, everything will work up until the point where you get to the list. There should not be any cashed and everything should be running pretty smoothly at this point.

There really isn’t any point in saving the task if you can’t see it so now it is time to start on the second feature.

There is no point in saving a task if you can’t actually see it, though, so time to start getting into your second feature.

Listing Tasks

Before you attempt to start listing tasks, I think it is important for you to realize that, at this stage, there is no data being stored in between launches. Once you have finished this tutorial, go off and learn about CoreData. Or you could look into Realm that is set to be a very easy replacement for CoreData.

## Using What You Have

Before you customize things too much let’s see how far you can get with what you already have. At the beginning, when you first generated this project, you got a MasterViewController that contained all the basic data source and delegate methods already set up for you, including Deletion. You also have a basic DetailViewController.

So let’s move on. Open up MasterViewController.swift so we can make some changes. The first thing we want to do is get rid of the objects property on the MasterViewController, because we don’t need t. Delete the line that looks like this, at the top of the controller:

*   var objects = NSMutableArray()

You do not need that in their anymore but, by deleting it, you are going to make code very angry. You see, that property is used in a number of different places so now you can work your way through, fixing errors. Start from the top and replace the old code with the new code that uses the TaskStore.

## Opening the Detail Screen

The first place you are going to see an error is in prepareForSegue:sender method that is in the MasterViewController. The changes are needed here, to the final two lines that are inside the IF statement

*   override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
*   if segue.identifier == "showDetail" {
*   if let indexPath = self.tableView.indexPathForSelectedRow() {
*   let task = TaskStore.sharedInstance.get(indexPath.row)
*   (segue.destinationViewController as DetailViewController).detailItem = task
*   }
*   }
*   }

On the second line in the IF statement, you need to change the name of the constant from object to task. To get the task that you need, you should use the get method that is on the sharedInstance of the TaskStore. There is no need for casting because you know that you are getting a Task back from the Get method.

On the third line in the IF statement, the change is quite boring really–all you need to do is set the detailItem of the DetailViewController to task instead of object. You must do this because you changed the constant name earlier.

Now you need to move on and fix a problem that has shown up elsewhere, namely in the DetailViewController so open the DetailViewControlle.swift file and make a minor change

## No more AnyObject

DetailViewController is expecting there to be an AnyObject? And that means a struct just isn’t going to fit in. That is going to be easy enough to fix though, simply by changing the property type of the detailItem to Task?

*   var detailItem: Task? {
*   didSet {
*   // Update the view.
*   self.configureView()
*   }
*   }

While you are in there, you could just fix the rest of the controller. There isn’t much more to do, all you have to change is the configureView method.

Look at where the detailItem optional is unwrapped. At the moment, you are saying that it is AnyObjecttype, which is now not true because you just changed it. So it’s time to fix it. As Task does not have a description property, you need to change t to title

*   func configureView() {
*   // Update the user interface for the detail item.
*   if let detail: Task = self.detailItem {
*   if let label = self.detailDescriptionLabel {
*   label.text = detail.title
*   }
*   }
*   }

That is all you need to change in the DetailViewController, at least until there are some more design changes. Time to go back to MasterViewController.swift and finish off in there.

## Changing the Data Source and Delegate

The next error that needs to be fixed is the UITableViewDataSource protocol method TableView:numberOfRowsInSection

Right now, you are purely calling count on what was an object array. Instead, you want to call count on the sharedInstance of the TaskStore

*   override func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
*   return TaskStore.sharedInstance.count
*   }

You may be wondering how to do that because you don’t have a count property at the moment. So let’s create one. Open taskStore.swift and, under the property declaration for Tasks, add in this:

*   var count: Int {
*   get {
*   return tasks.count
*   }
*   }

You could, if you had wanted, have created it as a method, like this:

*   func count() -> Int {
*   return tasks.count
*   }

However, while that would have been a shorter way to do it, it is lacking a bit of style. In making Count into a computed property, you are maintaining a consistent API with Array. Do not try forcing what is, in essence, a property into a method–it won’t go.

What you may not be aware of is that you can go even more concise than a method definition. When you create a computed property, it does not have a setter so you can remove lines two and four and put this in instead:

*   var count: Int {
*   return tasks.count
*   }

That is so much better and so much more expressive. It is clearly a property and it is clear that it is a computed one as well; it is also obvious what it is computing. Welcome to Swift!

## Back to the Data Source

So let’s move on from all the little niceties that are evident in Swift and finish off the data source. The tableView:numberOfRowsInSection:  method is absolutely fine now so let’s move on to tableView:cellForRowAtIndexPath method

The change here is somewhat similar to the change that you made to prepareForSegue:Sender method in the MasterViewController–all you are doing is changing how to get the task and the property that you are using it from

*   override func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell {

*   let cell = tableView.dequeueReusableCellWithIdentifier("Cell", forIndexPath: indexPath) as UITableViewCell
*   let task = TaskStore.sharedInstance.get(indexPath.row)
*   cell.textLabel?.text = task.title
*   return cell
*   }

The lines that were changed were the two that are just before the return statement. You are now going to use the get method from the TaskStore, instead of the objects array and its subscript operator. You are assigning the result from an object constant to a task constant.

On the final line, before the return statement, you have made a change to what you set the text property of the textLabel as - change it to the title of the task you got with the get method.

Only one thing left to change - a delegate method

## Finishing the Basics with the Delegate

So, you’ve probably already spotted that you have one method left to change.  In the UITableViewDelegate method tableView:commitEditingStyle:forRowAtIndexPath: you are going to make one simple change by adding in something to the TaskStore

*   override func tableView(tableView: UITableView, commitEditingStyle editingStyle: UITableViewCellEditingStyle, forRowAtIndexPath indexPath: NSIndexPath) {

*   if editingStyle == .Delete {
*   TaskStore.sharedInstance.removeTaskAtIndex(indexPath.row)
*   tableView.deleteRowsAtIndexPaths([indexPath], withRowAnimation: .Fade)
*   } else if editingStyle == .Insert {
*   // Create a new instance of the appropriate class, insert it into the array, and add a new row to the table view.
*   }
*   }

## One More Method for TaskStore

Go to the TaskStore class and add in the removeTaskAtIndex: method

*   func removeTaskAtIndex(index: Int) {
*   tasks.removeAtIndex(index)
*   }

The reason I have asked you to do this, instead of directly accessing the tasks array and calling the removeAtIndex method is because it now allows you to define a specific API for the users of your TaskStore class. Later, you will be able to make changes to the internals of the TaskStore class without affecting any other code.

## Tidying Things Up a Bit

There are a couple of minor design changes that you can make now that will enhance your application, one of which is quite a clear design flaw – how do you view the notes?

## Altering the Storyboard

In the Main.storyboard file, select the prototype table view cell and change from the default UITableViewStyle, with just the one Text label to the subtitle style. This will let you see a preview of the notes. To do this, go into the Attributes Inspector and click on Style. From the dropdown menu, click on Subtitle and you will see that the prototype cell changes and now includes a second label.

## Updating Your MasterViewController

Let’s take advantage of that second label and make a few changes to MasterViewController. Open up the MasterViewController.swift file and locate the tableView:cellForRowAtIndexPath method. This is what you are going to change

*   override func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell {
*   let cell = tableView.dequeueReusableCellWithIdentifier("Cell", forIndexPath: indexPath) as UITableViewCell
*   let task = TaskStore.sharedInstance.get(indexPath.row)
*   cell.textLabel?.text = task.title
*   cell.detailTextLabel?.text = task.notes
*   return cell
*   }

The only real change here is that you are setting the text property of the detailTextLabel. This will be set in between the text property of textLabel and the line where the cell is returned from the method.

Run the application and try to add a task–do make sure that you fill the notes section out. You should see a preview of those notes when the task list reappears. Don’t put too much in the notes–if it is too long to fit on the detailTextLabel, it will just be cut off and that leads us onto the next thing to fix.

## Redesigning the Detail View

That small label in the center really isn’t going to be enough so open up Mail.storyboard.swift and get ready to make some changes to DetailViewController. To be honest, it really doesn’t matter what you do to this to change the way it looks so long as you have the right two views. The fits is already evident in DetailViewController and all you ae going to do is move the label up and make it a little bit bigger, not forgetting to update the constraints.

The next thing to do is drag a Tet View out of the Objects Library to the DetailViewController. Once the layout is sorted out, you can go into the Attributes Inspector and make some changes.

The font can be enlarge to 18 points, through the font picker, which, if you remember, is accessed through the T icon next to the font. Make sure you uncheck the box next to Editable–you will find it just under the font field. Something else that would be nice is if you could open phone numbers and links directly from the notes field so, when you go into the Detection section in Attributes Inspector, make sure you check the boxes for Links and Phone Numbers.

Lastly, you should link the Text View and the DetailedViewController. Open the Assistant Editor (remember, it’s the icon that looks like a tuxedo) and hold down CTRL. Drag from Text View to just beneath where you have defined the @IBOutlet  for the detailTextLabel. Call the new outlet notesView.

## Displaying Your Notes

Now that the outlet has been created, all that is left is one simple job–putting the content in. Open DetailViewController.swift and locate configureView method. Make these changes:

*   func configureView() {
*   // Update the user interface for the detail item.
*   if let detail: Task = self.detailItem {
*   if let label = self.detailDescriptionLabel {
*   label.text = detail.title
*   }
*   }
*   }

The changes are inside the IF statement which is inside the wrapping IF statement. You have also removed the completely pointless use of self that was in front of all of the properties.

So, first you need to unwrap the optional UITextView, even though it has already been implicitly unwrapped. Then, it needs to be assigned to the constant called notes, allowing you set the text n notesView as the notes property of the detail item, which is a Task.

Now, when you run the application you will see a basic task management application that you can happily play around with to your hearts content.

Congratulations! You have successfully built a new iOS application using Swift. While it isn’t likely to be the next big thing, it is a fantastic point for you to start learning from, to start understanding what it’s like to use Swift and XCode to build an app. If you were to build the same app using Objective C you would see a whole lot more code than you have in this application and, perhaps more importantly, a lot of far less expressive code.

In the final chapter, I am going to introduce you to Swift 2, the latest update to Apple’s brand new computer programming language.

# Chapter 10: What’s New in Swift 2

Hot on the heels of Apple’s new computer programming language Swift, already proving mighty popular, comes Swift 2\. Introduced at WWDC 2015, Swift 2 promises to be bigger and better than its predecessor is. And, perhaps the most astonishing piece of news is that Apple has promised to make Swift open source, later on in 2015.

This means that the source code or the programming language will be made available to everyone. As a developer or programmer, you will be able to inspect that code, modify it to suit you, and use it pretty much wherever you want. This is huge news because it means that developers can use Swift on operating systems that are not tied to Apple. It is expected that this will lead to Swift being used on Linux deployments as well as Windows and the Raspberry Pi.

Does that Mean Swift Will Work on Android Smartphones?

While you will be able to use this code on other devices, please don’t get drawn into the belief that you will be able to run iOS or OS X software on another operating system. It will be easier to port software from one to another but Apple are not likely to relinquish control of the SDK (software development kit). I can’t tell you at this stage which bits of Swift will go open source and it’s not likely that they will release the source code for XCode – you will still need your mac to develop the software for iOS and OS X.

What is New in Swift 2?

While we wait for Swift 2 to become available to all, later on in 2015 when XCode 7 is released, let’s have a brief look at some of the main new features.

## Error Handling

Error handling has been given a makeover in Swift 2; instead of getting double pointers and NSError objects, you will s a new system that is reminiscent of exception handling. You might be familiar with code that has been written like this:

*   if drinkWithError(nil) {
*   print("Could not drink beer! :[")
*   return
*   }

In Cocoa, as a rule you would include an inout parameter or a reference to an NSError object and then let the method assign the variable if there is a problem. The biggest problems are that you can pass nil and completely ignore that error or you can pass in the NSError but not check it.

Swift 2 includes extra safety measures to help with error checking and you will now use the throws keyword as a way of specifying the methods and functions, which may throw an error. You can then use other keywords – do, try and catch – for times when you are calling something that has the potential to throw:

*   // 1
*   enemy DrinkError: ErrorType {
*   case NoBeerRemainingError
*   }
*   // 2
*   func drinkWithError() throws {
*   if beer.isAvailable() {
*   // party!
*   } else {
*   // 3
*   throw DrinkError.NoBeerRemainingError
*   }
*   }

*   func tryToDrink() {
*   // 4
*   do {
*   try drinkWithError()
*   } catch {
*   print("Could not drink beer! :[")
*   return
*   }
*   }

## Binding

In Swift 1.2 we gained the ability to be able to test binding multiple optionals on the same line:

*   if let pants = pants, frog = frog {
*   // good stuff here!
*   }

That works well but some people don’t like the fact that the “Preferred” code path is indented and this is where the optionals have value. That means you have to keep looking inside the indents for the main part of the code while, in the meantime, the errors are outside the indents.

Swift 2 makes it possible to check for values in optionals with its new guard statement.

*   guard let pants = pants, frog = frog else {
*   // sorry, no frog pants here :[
*   return
*   }

The use of guard means that optional binding can be performed and will give you a code block in the else that you can run in the event of condition failure. You can then continue.

This should make your code clearer because guard allows you to specify what state you are expecting rather than going through an error check.

## Protocol Extensions

Swift 2 allows you to extend protocol and add in implementations for methods and properties. While you can already do this with structs and classes, being able to add to the protocols extends your reach.

*   extension CustomStringConvertible {
*   var shoutyDescription: String {
*   return "\(self.description.uppercaseString)!!!"
*   }
*   }
*   let greetings = ["Hello", "Hi", "Yo yo yo"]
*   // prints ["Hello", "Hi", "Yo yo yo"]
*   print("\(greetings.description)")
*   // prints [HELLO, HI, YO YO YO]!!!
*   print("\(greetings.shoutyDescription)")

You can see the Printable has been changed to CustomStringConvertible and most Foundation objects conform to this. With the protocol extensions, you can extend large parts of the system using custom functionality.

And, instead of adding in bits of custom code to enums, structs and classes, you can simply write one implementation that will apply across a number of types.

## Grab Bag

There are loads of new things on the way so, rather than go through it all now, I just want to go through a couple of them:

*   Objective C Generics – Apple has begun annotating all of the Objective C code so that all Swift types get the right optionality. That is now being done with Objective C generics, giving developers better type hinting.
*   Renamed Syntax – PrintIn has gone, after just one year so it’s back to plain Print, which has been given a default second argument – this is set to true on whether or not to print a newline. The do keyword is focused on error handling scope and do-while loops have changed to repeat-while.

These are just a few of what is to come in the near future and there will likely be a lot more revealed as time goes on. At this stage, it is a case of wait and see but, in the meantime, I would suggest that you spend your time wisely, getting fully to grips with Swift before we get the update.

# Chapter 11: Creating Applications in Swift

## Simple Calculator

Now we will have a look at the required steps for creating a simple calculator program.

*   Open XCode
*   Create a single view application
*   Fill out the product name, organization name and of the organization identifier.
*   We will name the product as iOS8SwiftCalculatorTutorial.
*   Select swift in the language tab.
*   Select the device from the device tab. Here, we will select iPhone as our device.

Make the width compact from the storyboard for changing the view to portrait mode, for suiting an iPhone.

On the top of the main view, add a label. Select the “Right Alignment” from the property inspector. Give “0” as the label title. Now select an assistant editor. Now open the file ViewController.swift. Press Ctrl and from the bottom, drag to the class section. This will create the output as shown below.

To the view, Add a button and give “1” as the title for the button. Press Ctrl and from the bottom to the IBoutlet, Drag. The following action will be created.

Copy this button to the storyboard and then press create for creating other digits. Remember that this will copy the IBAction connection as well. After copying, the storyboard was somewhat look like this.

Now click on a new button and a drag it to the view.  Give the minus sign to the button. From the plus-bottom, Ctrl+Click and Drag to the file ViewController.swift, present below the action numberTapped for creating the action.

Now, copy the plus-button and beneath it, paste a new button. Give a plus sign to the new button.

Below the “0” button, now create a new button. Give the new button a “=” sign. From this button, Ctrl and Drag till the file ViewController.swift below calculationTapped for creating an action.

Now that we have a design for our calculator, we will add code inside the file ViewController.swift. We will first define some properties after the line "class ViewController: UIViewController {".

var isTypingNumber = false
var firstNumber = 0
var secondNumber = 0
var operation = ""

The function isTypingNumber is of the Boolean type and we use it for checking whether the user is pressing an operation or typing a number.

Implement the method numberTapped after this:

*   @IBAction func numberTapped(sender: AnyObject) {
*   var number = sender.currentTitle
*   if isTypingNumber
*   {
*   calculatorDisplay.text = calculatorDisplay.text + number
*   }
*   else
*   {
*   calculatorDisplay.text = number
*   isTypingNumber = true
*   }
*   }

To the calculatorDisplay label’s text, we will append the digit pressed. If the digit is the first, that digit will be assigned to the label. The method calculationTapped will be implemented next.

*   @IBAction func calculationTapped(sender: AnyObject)
*   {
*   isTypingNumber = false
*   firstNumber = calculatorDisplay.text.toInt()!
*   operation = sender.currentTitle
*   }

Using the toInt method, the calculatorDisplay text will be converted into the integers from strings.

Note:

A string can sometimes be empty and in such cases, an optional integer will be returned. But in our case, the string will always have a value and for unwrapping the value, we will add an exclamation mark. Implement the method equalsTapped.

*   @IBAction func equalsTapped(sender: AnyObject)
*   {
*   isTypingNumber = false
*   var result = 0
*   secondNumber = calculatorDisplay.text.toInt()!
*   if operation == "+" {
*   result = firstNumber + secondNumber
*   }
*   else if operation == "-"
*   {
*   result = firstNumber – secondNumber
*   }
*   calculatorDisplay.text = "\(result)"
*   }

Basing on the property value of the operation, calculation will be performed and the result will be displayed by the calculatorDisplay label.

As the final step, Build and Run the project. Now you can make some calculations.

## Minesweeper game

Here, we will design the minesweeper game using swift. This tutorial will show you how the minesweeper game is built from start to finish.

Minesweeper: An Intro Tutorial to Swift iOS Development

We will build the minesweeper game using swift and the storyboard Interface builder of XCode. For this you need to have the latest version of XCode and the latest version of the swift language. You can download it using the link from the swift resources page or you can easily download it from the App Store.

This tutorial will help you create the swift powered iOS app. However, for the sake of brevity, some aspects of the swift are not explained in this tutorial.

I'm sure most of the people are familiar with the minesweeper game. If not, have a quick look of it online.

Open the latest version of XCode. Create a new project by following the given steps.

Give a product name for the application. We will simply name it minesweeper.

Give the organization name and organization identifiers.

Select the language as Swift

Select the device for which you are designing this application. If you want your application to work on all the iOS devices, select “Universal” from the list.

On the very first screen, go to the deployment info section from the general settings and uncheck the landscape right and landscaper left orientations. This will make the application run in portrait.

We will start designing the application by laying the user interface. We will do it with the help of the storyboard interface builder. First, open the main.storyboard and then select the ViewController present on the screen. For this you may have to select the top interface bar rather than clicking on the view for selecting the ViewController. On the right you should make sure that the utilities panel is open. In case if it is not open, you should open it by clicking on the top right button present on the XCode window. Now that you have selected the ViewController, go to the file inspector tab present in that panel and uncheck the option “Use Auto Layout”. If any pop-up shows up, select the iPhone and disable size classes. Though this app can be used on any iOS device, we will mainly design it for using it on an iPhone. We can make this application compatible to the iPad by making a few modifications. We will not be using all of the functionalities of the auto layout and for this reason we will disable it so that things can be simpler.

Select the View component from the bottom right panel of the object library and drag it onto the view controller. With this view, our minesweeper board grid will be held. Change the color of the background from the attributes inspector to Group Table View Background Color. It is a gentle grey color.

Set the values of X, Y, Width and Height to 20, 29, 280 and 280 respectively. You should make sure that the auto resizing masks are enabled, so that this can be resized for using it on an iPad.

Onto the view controller, drag the new label components. Now, align them below the board view such that one is up against the right edge and the second one is on the left. On the left label, set the text to “Moves: 0” and on the right label, set the “Time: 0”. Now, on each label, change the auto resizing mask. On the left bottom of the SuperView, the left label should be aligned and similarly, the right label should be aligned to the bottom right. With this, they will look nice on an iPhone and on iPad as well. Now we don't want the text to trail off the edges of the label. For that, we will align the text on the right label to the right side. With this, even if the length of the text increases, they won't trial off the edge.

Place the navigation bar component on the top by dragging it. Now, rename the title to “Minesweeper”. We will only use this like a static bar for displaying the application's name. In a multi-page application, this can also be used for navigation.

Drag the toolbar component by clicking on it, to the bottom. Now, rename the item to “New Game”.

With this, we have completed the basic interface of the application. Now we will add code into it. First, open the ViewController.swift. Hooking the user interface that we have created is the next thing to do. With this, the object can be accessed and the New Game will call a method.

To the class slope, add IBOutlets. The properties which connect the components from the storyboard are given below.

*   @IBOutlet weak var boardView: UIView!
*   @IBOutlet weak var movesLabel: UILabel!
*   @IBOutlet weak var timeLabel: UILabel!

Now we will add the method IBAction which gets called whenever the new game button is pressed.

*   @IBAction func newGamePressed()
*   {
*   println("new game");
*   }

Open assistant editor from the Main.storyboard. With this, you can have a look at the file ViewController.swift at the same time. On the left margin of every line, you will see an empty circle with an IBOutlet or IBAction. Drag them to their corresponding components by clicking on them and make connections.

You can now run the project and it should correctly compile and a show the view controller containing the user interface, which we have designed using storyboard. If you click the new game button, a print statement from the console will be displayed. In case where you have chosen a different device simulator, it will correctly scale between the resolutions of iPad and iPhone.

Now, we will start coding. The paradigm we follow will be the Model-View-Controller. In iOS development, this is frequently used for separating the front end user interface code from the model code of the back end.

The backend model of our application will consist of two new classes 1\. Board.swift class and 2\. Square.swift class. We will start our back-end coding by creating a Square.swift. For this, select new file from the file menu and swift file from that. Name the file as “Square.swift”.

Implement this class after defining it, which is a simple thing to do. You will just have to initialize the class and after that you should store the state in a cell inside the grid of the board.

*   class Square
*   {
*   let row:Int
*   let col:Int
*   // give these default values that we will re-assign later with each
*   new game
*   var numNeighboringMines = 0
*   var isMineLocation = false
*   var isRevealed = false
*   init(row:Int, col:Int)     
*   //store the row and column of the square in the grid
*   self.row = row
*   self.col = col
*   }
*   }

Did you notice that there are different ways in declaring variables, assigning the parameters to their properties and the method signature format. You can also notice that we don't have to call super.init and we are not sub classing.

We have now implemented the class Square and we can now implement the class board. The class board is used for representing a set of squares and it will also provide the methods required for determining the total number of mines neighboring the given Square.

Now create a new file called board.Swift by selecting the new file option from the file menu. From the new file option, select the swift file and name the file as “Board.Swift”.

Compared to the square, board is more compacted. We will first define the class, properties and method init.

*   class Board
*   {
*   let size:Int
*   var squares:[[Square]] = [] // a 2d array of square cells, indexed by [row][column]
*   init(size:Int)
*   {
*   self.size = size
*   }
*   }

To the init method, join a double for loop for setting up the square object grid:

*   for row in 0 ..< size
*   {
*   var squareRow:[Square] = []
*   for col in 0 ..< size {
*   let square = Square(row: row, col: col)
*   squareRow.append(square)
*   }
*   squares.append(squareRow)
*   }

If you notice day for loop syntax, you can see that the upper bound is not included when “<” is used. This will create a grid containing squares and now we should assign the properties isMineLocation, isRevealed and numNeighborMines. We will have to repeat this multiple times and they have to be reset whenever the user starts a new game. For this, we can create a method and call it every time a new game is started.

*   func resetBoard()
*   {
    // assign mines to squares
*   for row in 0 ..< size
*   {
*   for col in 0 ..< size
*   {
    squares[row][col].isRevealed = false
*   self.calculateIsMineLocationForSquare(squares[row][col])
*   }
*   }
    // count number of neighboring squares
*   for row in 0 ..< size
*   {
*   for col in 0 ..< size
*   {
*   self.calculateNumNeighborMinesForSquare(squares[row][col])
*   }
*   }
*   }

This will go through the squares and it will set the isRevealed property to false. It will then call a method which calculates the isMineLocation property. After assigning the locations for all the mines, we will iterate the squares for counting the total number of neighboring mines they each have. Whenever a new game is started, the resetBoard method will be called from the class ViewController.

Now we will implement the method calculateIsMineLocationForSquare. Though it is only a simple line of code, by separating it into a method of its own, it will be easier for us to modify later and it to change how the mines are assigned to squares. Currently it will only randomly give a mine to a square with a probability of 10%.

*   func calculateIsMineLocationForSquare(square: Square)
*   {
*   square.isMineLocation = ((arc4random()%10) == 0)

// 1-in-10 chance that each location contains a mine

*   }

This process was simple but the calculateNumNeighborMinesForSquare it pretty complicated. For this, we will have the loop every square and check the property isMineLocation of the neighboring squares. It gets tricky as the number of squares neighboring a particular Square is not the same. For instance, there will be eight neighboring squares for the square in the middle but there will only be three in case of a square present on the corner. For keeping things simple and clean, we will break the method into several methods.

*   func calculateNumNeighborMinesForSquare(square : Square) {
    // first get a list of adjacent squares
*   let neighbors = getNeighboringSquares(square)
*   var numNeighboringMines = 0
    // for each neighbor with a mine, add 1 to this square's count
*   for neighborSquare in neighbors {
*   if neighborSquare.isMineLocation {
*   numNeighboringMines++
*   }
*   }
*   square.numNeighboringMines = numNeighboringMines
*   }

For providing the adjacent square list, this method will rely on another method. After getting the list, iterating through the list is simple and we can check the number of mines.

*   func getNeighboringSquares(square : Square) -> [Square] {
*   var neighbors:[Square] = []
    // an array of tuples containing the relative position of each neighbor to the square
    let adjacentOffsets =
           [(-1,-1),(0,-1),(1,-1),
           (-1,0),(1,0),
           (-1,1),(0,1),(1,1)]

*   for (rowOffset,colOffset) in adjacentOffsets {

// getTileAtLocation might return a Square, or it might return nil, so use the optional datatype "?"

*   let optionalNeighbor:Square? = getTileAtLocation(square.row+rowOffset, col: square.col+colOffset)
           // only evaluates true if the optional tile isn't nil
*   if let neighbor = optionalNeighbor {
*   neighbors.append(neighbor)
*   }
*   }
*   return neighbors
*   }

We have made use of the optional data types and this feature is a unique one in swift. Nil values cannot be given to the variables by default. If you want a variable to have a nil value, you should add “?” after the data type. You can check if the value is nil or not why are sending it to an optional variable. If it is successful, it is not a nil value.

Now we will finally implement the method getTileAtLocation for getting the tiles that are in the bounds of board.

*   func getTileAtLocation(row : Int, col : Int) -> Square?
*   {
*   if row >= 0 && row < self.size && col >= 0 && col < self.size
*   {
*   return squares[row][col]
*   }
*   else
*   {
*   return nil
*   }
*   }

With this, the squares will count the number of mines correctly and their value ranges from 0 to 8\. With this we have completed coding our model. Now we will have to complete the view and for that we should create the buttons corresponding to each square present on the board. We will create a new file named “SquareButton.swift” for this.

This new class will extend the class UIButton so that it can be displayed on the screen and you can tap it for calling methods. For this, you should import the framework called UIKit.

class SquareButton : UIButton {
}

Now by defining some properties, we will implement the class and after that we will add a custom init method, which sets the position and size of the button depending on the square model associated with it. Inside the class SquareButton, add the following:

*   let squareSize:CGFloat
*   let squareMargin:CGFloat
*   var square:Square
*   init(squareModel:Square, squareSize:CGFloat,
*   squareMargin:CGFloat) {
*   self.square = squareModel
*   self.squareSize = squareSize
*   self.squareMargin = squareMargin
*   let x = CGFloat(self.square.col) * (squareSize + squareMargin)
*   let y = CGFloat(self.square.row) * (squareSize + squareMargin)
*   let squareFrame = CGRectMake(x, y, squareSize, squareSize)
*   super.init(frame: squareFrame)
*   }
*   required init(coder aDecoder: NSCoder)
*   {
*   fatalError("init(coder:) has not been implemented")
*   }

For setting up the UIButton, the method super.init(frame: CGRect) should be called, so that it can properly displayed on the screen. Basing on the square size, small margin between and the row and column, it will calculate the positions x and y.

For now, that is all we need and later another method will be added which will change the state of the button after clicking. We will create a button grid from the ViewController.swift. These buttons will be added to the screen with the help of code.

The central controller for application is the ViewController and it communicates information from the View of the Model.

For representing the total number of rows and columns present on our board, we should now define a new constant. This constant should be at class level. By changing the values of this constant, the gameplay will be adjusted. We will start by giving the board size as 10\. Now we will add a property to the board:

let BOARD_SIZE:Int = 10
var board:Board

Now, we should implement a custom init method, which gets called automatically whenever ViewController is loaded from storyboard. This custom init method will be named as init(coder aDecoder: NSCoder!). This should be added to the class.

*   required init(coder aDecoder: NSCoder)
*   {
*   self.board = Board(size: BOARD_SIZE)
*   super.init(coder: aDecoder)
*   }

Because there is no value given to the board property, we will need that. It cannot have the value as nil, as it is an optional value and before the init method finishes, it will need a value.

One more property, SquareButton objects array should be defined. There is the 2d array on our Board class it contains Square model objects. Later, we need to iterate all the buttons when a new game is started so that their appearances will be reset. We should find a way where the buttons iterate themselves. The class scope, the 1d array SquareButtons should be added.

var squareButtons:[SquareButton] = []

With this, we now have everything for initializing a new board and for adding buttons to the screen. We will now implement the method initializeBoard for iterating the 2d array of Squares and for adding button on the screen every time:

*   func initializeBoard()
*   {
*   for row in 0 ..< board.size
*   {
*   for col in 0 ..< board.size
*   {
*   let square = board.squares[row][col]
*   let squareSize:CGFloat = self.boardView.frame.width / CGFloat(BOARD_SIZE)\
*   let squareButton = SquareButton(squareModel: square, squareSize: squareSize);
*   squareButton.setTitleColor(UIColor.darkGrayColor(), forState: .Normal)
*   squareButton.addTarget(self, action: "squareButtonPressed:", forControlEvents: .TouchUpInside)
*   self.boardView.addSubview(squareButton)
*   self.squareButtons.append(squareButton)
*   }
*   }
*   }

The line to trigger the squareButtonPressed method when any of the buttons are tapped is the  “squareButton.addTarget(self, action: “squareButtonPressed:", forControlEvents: .TouchUpInside)”. For testing the game, we will add a temporary implementation to the method. To ViewController.swift, add this function:

func squareButtonPressed(sender: SquareButton)

{
   println("Pressed row:\(sender.square.row), col:\(sender.square.col)”)
sender.setTitle("", forState: .Normal)
}

The row and column of the button you tapped on will be printed to the console. Whenever we start a new game, the board should be reset with new mine locations and the text present on the back of the buttons should go back to their default values. For this, we should add the method resetBoard. This method will be called every time we start a new game. This method should be added:

*   func resetBoard() {
       // resets the board with new mine locations & sets isRevealed to
*   false for each square
*   self.board.resetBoard()

 // iterates through each button and resets the text to the default value

*   for squareButton in self.squareButtons
*   {
*   squareButton.setTitle("[x]", forState: .Normal)
*   }
*   }

We will add a method called startNewGame, which calls the resetBoard (Later for this method, we will add some more code):

*   func startNewGame() {
       //start new game
       self.resetBoard()
    }

At the end of the method, add the default method viewDidLoad in the class ViewController:

*   self.initializeBoard()
*   self.startNewGame()

We will Build and Run the game. We will do this by pressing Cmd+R. You should now see a grid of 10x10 buttons. The buttons should be labelled “[x]”. When you tap on them, the “[x]” on the buttons will be cleared and their position will be printed to the console.

This is great but it is not the complete minesweeper game yet. We can actually make it close it to complete the game by making the buttons display some other text when you tap on them, depending on the properties numNeighboringMines and isMineLocation. The body of the method squareButtonPressed and they replaced by using the following:

*   if(!sender.square.isRevealed)
*   {   
*   sender.square.isRevealed = true
*   sender.setTitle("\(sender.getLabelText())", forState: .Normal)
*   }

With this the contents of the square will be revealed by tapping on them if you haven't previously taped on them. A method on the squareButton will be called, asking for the new text that is to be displayed on the squareButton. We have not yet implemented this, so we will now open the file SquareButton.swift and add getLabelText:

*   func getLabelText() -> String {
       // check the numNeighboringMines and isMineLocation properties for determining the text to be displayed
*   if !self.square.isMineLocation
*   {
*   if self.square.numNeighboringMines == 0
*   {
    // case 1: there's no mine and no neighboring mines
*   return ""
*   }
*   else
*   {
    // case 2: there's no mine but there are neighboring mines
*   return "\(self.square.numNeighboringMines)"
*   }
*   }
*   // case 3: there's a mine
*   return "M"
*   }

We will now Build and Run the application again. Now if you tap on the buttons, the text on them will change your number in case if there are any neighboring mines. Nothing will be displayed if there are no neighboring mines. If there is a mine, “M” will be displayed.

We can make the new game button end the current game and start a new one. If there is no current game, it will directly start a new game. This is one quick feature that we can add. In the method newGamePressed that we have already defined, call the startNewGame. It will now look like:

*   @IBAction func newGamePressed()
*   {   
*   println("new game")
*   self.startNewGame()
*   }

If we test the application, tapping on the buttons will randomize the mine locations and it will also reset the square buttons.

The game should end when we tap on the button having a mine. We can add an alert to pop up whenever the mine is tapped. The alert will also have a button which resets the game. At the bottom of squareButtonPressed, add this conditional.

if sender.square.isMineLocation {
   self.minePressed()
}

For showing an alert we should implement minePressedb.

*   func minePressed()
*   {
    // show an alert when you tap on a mine
*   var alertView = UIAlertView()
*   alertView.addButtonWithTitle("New Game")
*   alertView.title = "BOOM!"
*   alertView.message = "You tapped on a mine."
*   alertView.show()
*   }

![Description: Modal with new game prompt](images/00001.jpeg) ![](images/00002.jpeg)

The AlertView will be dismissed if the new game button is tapped. Actually, it won't start a new game. You can make the button start a new game by adding the following method:

*   func alertView(View: UIAlertView!, clickedButtonAtIndex
*   buttonIndex: Int) {
    //start new game when the alert is dismissed
*   self.startNewGame()
*   }

We have not yet specified that the class ViewController is going to handle the dismissing interaction. For this, the interaction should be passed to the ViewController from the alertView. This can be done by setting the alertView’s delegate property. This will be added at the bottom of the method minePressed:

*   alertView.delegate = self

Now when the New Game is tapped in the alertView, the board will be reset so that you can try again.

Most of the core gameplay is completed and now we should add the properties for the total number of moves made, and the time in seconds, since the game began. These properties will be added to the class scope ViewController. The didSet methods will also be included with this:

*   var moves:Int = 0
*   {   
*   didSet
*   {       
*   self.movesLabel.text = "Moves: \(moves)"       
*   self.movesLabel.sizeToFit()   
*   }
*   }
*   var timeTaken:Int = 0  
*   {   
*   didSet
*   {
*   self.timeLabel.text = "Time: \(timeTaken)"
*   self.timeLabel.sizeToFit()
*   }
*   }

Every time the property’s value changes, the method didSet will be triggered. They will be used for updating the corresponding labels display automatically. The size of the label will be adjusted by the sizeToFit, so that the text will fit inside the label when the length of the text increases. Add this method startNewGame at the bottom resetting the variables whenever a new game starts.

*   func startNewGame() {
    //start new game
*   self.resetBoard()
*   self.timeTaken = 0
*   self.moves = 0
*   }

These variables should be updated as game progresses and we need a way to do it. The property Moves is easy, whenever a new button is clicked, it should be increased by 1\. There should be added inside the conditional (!sender.square.isRevealed) present in the method squareButtonPressed:

self.moves++

It is a bit complicated to deal with the time as a timer object should be created for triggering the method for every one second passed. This new property will be defined on the class:

var oneSecondTimer:NSTimer?

We will make it into an optional NSTimer object. By making it an optional object, a nil value can be given to it when the game ends and before a new game begins. At the end of startNewGame, add the line given below, for creating a new timer:

self.oneSecondTimer = NSTimer.scheduledTimerWithTimeInterval(1.0, target: self, selector: Selector("oneSecond"), userInfo: nil, repeats: true)

For every 1.0 seconds, the method named “oneSecond” will be called. Now, we will define the same method to increase 1 second of time, every time it is called.

*   func oneSecond()
*   {
*   self.timeTaken++
*   }

The Moves and the Time labels will be updated appropriately if you play now. But there will be one problem. Even after losing the game, the timer will continue to go up. When you start a new game, the new timer will start without invalidating the old timer and with this, the time goes faster and faster with every game you play. Now we should add a new method which will be triggered whenever the game ends; by tapping the new game button or a mine.

*   func endCurrentGame()
*   {
*   self.oneSecondTimer!.invalidate()
*   self.oneSecondTimer = nil
*   }

If you notice, you will find that the oneSecondTimer is optional and if you wish to access its properties, you should put “!” after is the name. The “!” will tell that the object is not empty at the current time and it is fine to access the object as non optional.

Add to the top of the minePressed method:

self.endCurrentGame()

And add to the top of the newGamePressed method:

self.endCurrentGame()

If you execute the application now, in the new games, it will properly handle the timer. We have finally built the minesweeper application using the storyboard Interface builder of XCode and swift programming language.

The positions of the square buttons will be based on the boardView size and it will scale to fill the width of the screen. With the built in cross compatibility between the iPad and the iPhone, our application can be used on any of those devices.

The iPhone version and the iPad versions are given below.

If you want some extra challenge with the application, there are many features which you can add it to the application and few of those ideas are given below.

1.  For changing the difficulty, you can add new components to the user interface where you can adjust the method calculateIsMineLocationForSquare in the board.Swift. With this, the difficulty of the game will be increased.
2.  You can implement an algorithm which will clear multiple boxes with a single click, on the box which has no neighboring mines. In the traditional minesweeper game, when there are no neighboring mines, they will be cleared continuously.
3.  You can let the user know when he won the game. This will happen when they haven't touched the mines after revealing the non-mines.

# Conclusion

That concludes my basic tutorial on how to create a class in the Swift Playground and then transfer that class over to Swift and build an app from scratch. Swift really is not a difficult language to learn and is one of the more fun ones.

Really and truthfully, we have only just scratched the surface of what this versatile computer programming langue can do and there is so much more to learn. But, you have made it this far, you have built an app and from there the world is your oyster.

You May Enjoy Oswald’s Other Books!

[PYTHON: Programming Guide For Beginners: LEARN IN A DAY!](http://hyperurl.co/python)

hyperurl.co/python

[C ++ Programming : Programming Language For Beginners: LEARN IN A DAY!](http://smarturl.it/cplusplus)

Smarturl.it/cplusplus

[JAVA: Java Programming, JavaScript, Coding: Programming Guide: LEARN IN A DAY!](http://hyperurl.co/javaos)

hyperurl.co/javaos

[SQL: Programming Guide: Javascript and Coding: LEARN IN A DAY!](http://smarturl.it/sql)

hyperurl.co/sql

Programming HTML Programming Guide: Computer Programming: LEARN IN A DAY!

[hyperurl.co/html](http://hyperurl.co/html)