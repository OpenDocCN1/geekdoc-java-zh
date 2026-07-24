![](cover.jpeg)

New Concepts in Java 8

VLIGHT

Table Of Contents

[Behavior Parameterization](#part0000_split_002.html__Toc469750618)

[Lambda Expressions](#part0000_split_003.html__Toc469750619)

[Functional Interfaces](#part0000_split_004.html__Toc469750620)

[Predicate](#part0000_split_005.html__Toc469750621)

[Customer](#part0000_split_006.html__Toc469750622)

[Streams](#part0000_split_007.html__Toc469750623)

# 
Behavior Parameterization

Behavior Parameterization is nothing but a software development pattern which lets you handle frequent requirement changes

Behavior Parameterization means taking a block of code, which can be called later by other parts of your programs, and making it available without executing it

Behavior Parameterization is the ability for a method to take multiple different behaviors as parameters and use them internally to accomplish different behaviors

For example, you could pass the block of code as an argument to another method which will execute it later so the method's behavior is parameterized based on that block of code

Behavior Parameterization is a useful pattern, which lets you encapsulate a behavior and parameterize the behavior of methods by passing and using these behaviors you create, to easily adapt to changing your customer requirements

Many methods, which are often used together with anonymous classes, in Java API can be parameterized with different behaviors including:

+ Sorting with a Comparator: This is nothing but a recurring programming task

+ Executing a block of code with Runnable: You can use the Runnable interface to represent a block of code, which will return no result, to be executed

+ Handling GUI events: A typical pattern in GUI programming is to perform an action in response to a certain event such as clicking a button or hovering over a text

# 
Lambda Expressions

Passing code with behavior parameterization, which lets you define a block of code that represents a behavior and then pass it around, is useful for coping with frequent requirement changes in your code. You can decide to run that block of code when a certain event happens or at a certain point in an algorithm

Using anonymous classes  to represent different behaviors is verbose which does not encourage programmers to use behavior parameterization in practice

Lambda Expressions in Java 8 let you represent a behavior or pass a block of code in a concise way

Lambda Expressions in Java 8 can be understood as a concise representation of an anonymous function, which does not have a name but it has a list of parameters and a body and a return type and also possibly a list of exceptions that can be thrown, can be passed around

A Lambda Expression is composed of

+ A list of parameters: This list mirrors the parameters of the compare method of a Comparator

+ An arrow: The arrow -> separates the list of parameters from the body of the Lambda Expression

+ A body of the Lambda Expression: The expression is considered the Lambda's return value

Lambda Expressions in Java 8 let you provide the implementation of the abstract method in a functional interface directly inline then treat the whole expression as an instance of a functional interface

# 
Functional Interfaces

A functional interface is nothing but an interface which specifies only 1 abstract method

There are several functional interfaces in the Java API such as Comparator and Runnable

In Java 8, an interface is still a functional interface if it has many default methods, which are methods with a body that provide some default implementation for methods in case they are not implemented by a class, as long as it has only 1 abstract method

The signature of the abstract method in a functional interface essentially describes the signature of the Lambda Expression

In Java 8, functional interfaces are annotated with @FunctionalInterface which is used to indicate that the interface is intended to be a functional interface

Functional Intefaces are useful because the signature of the abstract method in a functional interface is called a function descriptor. So if you want to use different lambda expressions  you need a set of functional interfaces which can describe common function descriptors

# 
Predicate

In Java 8, the java.util.function.Predicate<T> interface defines an abstract method named test which accepts an object of generic type T and returns a boolean

This interface is used if you need to represent a boolean expression which uses an object of type T

# 
Customer

In Java 8, the java.util.function.Consumer<T> interface defines an abstract method named accept which takes an object of generic type T and returns void

If you need to access an object of type T and perform some operations on it, you must use the Consumer interface

# 
Streams

In Java 8, a stream is nothing but a sequence of elements from a source which supports data processing operations

What is a sequence of elements?

It likes a collection, a stream provides an interface to a sequenced set of values of a specific element type. Streams are expressing computations such as filter, sorted, and map. Collections are about data but streams are about computations

What is a source?

Streams consume from a data-providing source such as collections, arrays, or I/O resources

What are data processing operations?

Streams support database-like operations and common operations from functional programming languages to manipulate data such as filter, map, reduce, find, match, sort, etc.

Streams support a filter method which is an operation takes an argument as Predicate then returns a stream including all elements that match the Predicate

Streams also support the map method which takes a function as an argument

How to build a stream?

+ Buiding a stream from values: You can create a stream with explicit values by using the static method Stream.of() which can take any number of parameters

+ Building a stream from an array: You can also create a stream  from an array using the static method named Arrays.stream() which takes an array as a parameter

+ Building a stream from a file: You can also create a stream  from a file using the method named Files.lines() which returns a stream of lines as strings from the given file

+ Building a stream from a function: You can also create a stream  from a function using 2 static methods to generate a stream named Stream.iterate() and Stream.generate()