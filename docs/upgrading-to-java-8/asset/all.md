![](Images/cover.jpg)

**Upgrading to Java 8**

Budi Kurniawan

Upgrading to Java 8

First Edition: February 2015

All rights reserved. No part of this book may be reproduced or transmitted in any form or by any means, electronic or mechanical, including photocopying, recording, or by any information storage and retrieval system, without written permission from the publisher, except for the inclusion of brief quotations in a review.

ISBN: 9780992133085

Indexer: Chris Mayle

**Trademarks**

Oracle and Java are registered trademarks of Oracle and/or it's affiliates
UNIX is a registered trademark of the Open Group
Apache is a trademark of The Apache Software Foundation.
Firefox is a registered trademark of the Mozilla Foundation.
Google is a trademark of Google, Inc.

Throughout this book the printing of trademarked names without the trademark symbol is for editorial purpose only. We have no intention of infringement of the trademark.

Warning and Disclaimer
Every effort has been made to make this book as accurate as possible. The author and the publisher shall have neither liability nor responsibility to any person or entity with respect to any loss or damages arising from the information in this book.

About the Author

Budi Kurniawan is known for his clear writing style. A consultant at Brainy Software Corp., he has written software licensed by Fortune 100 companies and architected and developed large scale applications for various organizations around the world. He has also published more than 100 articles in prestigious publications. His other books include the popular "How Tomcat Works" and "Servlet and JSP: A Tutorial."

Table of Contents

[Introduction](#ch00.xhtml)

[Who This Book is For](#ch00.xhtml_toc1)

[About This Book](#ch00.xhtml_toc2)

[Downloading Sample Applications](#ch00.xhtml_toc3)

[Chapter 1: Lambda Expressions](#ch01.xhtml)

[Why Lambda Expressions?](#ch01.xhtml_toc1)

[Changes to the Interface](#ch01.xhtml_toc2)

[Functional Interfaces](#ch01.xhtml_toc3)

[Lambda Expression Syntax](#ch01.xhtml_toc4)

[Predefined Functional Interfaces](#ch01.xhtml_toc5)

[Summary](#ch01.xhtml_toc6)

[Chapter 2: Method References](#ch02.xhtml)

[Overview](#ch02.xhtml_toc1)

[Reference to A Static Method](#ch02.xhtml_toc2)

[Reference to An Instance Method where An Object Reference Is Available](#ch02.xhtml_toc3)

[Reference to An Instance Method where No Object Reference Is Available](#ch02.xhtml_toc4)

[Reference to A Constructor](#ch02.xhtml_toc5)

[Summary](#ch02.xhtml_toc6)

[Chapter 3: Optional and Similar Classes](#ch03.xhtml)

[Overview](#ch03.xhtml_toc1)

[OptionalInt, OptionalLong and OptionalDouble](#ch03.xhtml_toc2)

[Summary](#ch03.xhtml_toc3)

[Chapter 4: The Stream API](#ch04.xhtml)

[Overview](#ch04.xhtml_toc1)

[Creating and Obtaining a Stream](#ch04.xhtml_toc2)

[Concatenating Streams](#ch04.xhtml_toc3)

[Filtering](#ch04.xhtml_toc4)

[Mapping](#ch04.xhtml_toc5)

[Reduction](#ch04.xhtml_toc6)

[Mutable Reductions](#ch04.xhtml_toc7)

[Parallel Streams](#ch04.xhtml_toc8)

[Summary](#ch04.xhtml_toc9)

[Chapter 5: The Date-Time API](#ch05.xhtml)

[Overview](#ch05.xhtml_toc1)

[The Instant Class](#ch05.xhtml_toc2)

[LocalDate](#ch05.xhtml_toc3)

[Period](#ch05.xhtml_toc4)

[LocalDateTime](#ch05.xhtml_toc5)

[Time Zones](#ch05.xhtml_toc6)

[ZonedDateTime](#ch05.xhtml_toc7)

[Duration](#ch05.xhtml_toc8)

[Formatting A Date-Time](#ch05.xhtml_toc9)

[Parsing A Date-Time](#ch05.xhtml_toc10)

[Summary](#ch05.xhtml_toc11)

[Chapter 6: JavaFX 8](#ch06.xhtml)

[Overview](#ch06.xhtml_toc1)

[Setting up](#ch06.xhtml_toc2)

[Your First JavaFX Application](#ch06.xhtml_toc3)

[Application, Stage, and Scene](#ch06.xhtml_toc4)

[UI Components](#ch06.xhtml_toc5)

[Controls](#ch06.xhtml_toc6)

[Regions](#ch06.xhtml_toc7)

[Event Handling](#ch06.xhtml_toc8)

[Styling with CSS](#ch06.xhtml_toc9)

[Using DatePicker](#ch06.xhtml_toc10)

[Summary](#ch06.xhtml_toc11)

[Chapter 7: JavaFX with FXML](#ch07.xhtml)

[Overview](#ch07.xhtml_toc1)

[A Simple FXML-Based Application](#ch07.xhtml_toc2)

[Event Handling with FXML](#ch07.xhtml_toc3)

[Summary](#ch07.xhtml_toc4)

[Chapter 8: Nashorn](#ch08.xhtml)

[Overview](#ch08.xhtml_toc1)

[Using the jjs Command](#ch08.xhtml_toc2)

[Using Nashorn from Java Code](#ch08.xhtml_toc3)

[Invoking Java from JavaScript](#ch08.xhtml_toc4)

[Running JavaFX with Nashorn](#ch08.xhtml_toc5)

[Using Nashorn As Shell Script Replacement](#ch08.xhtml_toc6)

[Summary](#ch08.xhtml_toc7)

Introduction

Released in March 2014, Java 8 ships with many important features and enhancements. This book covers the most important features for developers, including:

*   Lambda expressions and method references.
*   A Stream API to support functional-style operations on streams of elements.
*   The revamped java.util package that adds support for streams.
*   The introduction of the Optional class and similar classes to help handle null pointer exceptions.
*   A major change to the Java language that allows static and default methods in interfaces.
*   A new theme and components for JavaFX 8.
*   Nashorn, a new JavaScript engine with more capabilities than simply parsing JavaScript code.

The complete list of the new features and enhancement can be found here:

```
 http://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html
```

Who This Book is For

This book is for experienced Java developers who want to learn Java 8 fast. If you are not familiar with Java, consider reading my other book, Java: A Beginner’s Tutorial, Fourth Edition (ISBN 9780992133047), which is fully revised for Java 8.

About This Book

The following presents the overview of each chapter.

Chapter 1, “Lambda Expressions” covers lambda expressions, a powerful feature added in Java 8\. It explains the concept and provides useful examples.

Chapter 2, “Method References” explains method references, a feature to make lambda expressions even shorter.

Chapter 3, “Optional and Similar Classes” talks about the new Optional class and similar classes for wrapping objects that can be potentially null. These classes can help handle null pointer exceptions.

Chapter 4, “The Stream API” discusses the new Stream API to support streams.

Chapter 5, “The Date-Time API” explains how you can work with the new Date-Time API in Java 8.

Chapter 6, “JavaFX 8” is an introduction to JavaFX and provides several examples.

Chapter 7, “JavaFX with FXML” discusses FXML, a markup language that can be used to separate the presentation layer and the business logic in JavaFX applications.

Chapter 8, “Nashorn” discusses the new JavaScript engine in Java 8 for running JavaScript from Java as well as performing other tasks such as scripting JavaFX and manipulating shell script output.

Downloading Sample Applications

Sample applications accompanying this book can be downloaded from the publisher’s website at

```
 http://books.brainysoftware.com
```

Chapter 1

Lambda Expressions

The lambda expression is the most important new feature in Java SE 8\. Long considered a missing feature in Java, it has made the Java language complete. At least for now. In this chapter you will learn what lambda expressions are and why they are a nice addition to the language. You will also be introduced to new technical terms such as single abstract method (SAM) and functional interface.

Why Lambda Expressions?

Also known as closures, lambda expressions can make certain constructs shorter and more readable, especially when you are dealing with inner classes.

Consider the following code snippet that defines an anonymous inner class out of the java.lang.Runnable interface and instantiates the class.

```
 Runnable runnable = new Runnable() {
    @Override
    public void run() {
        System.out.println("Running...");
    }
}
```

The code can be replaced with a lambda expression as short as this:

```
 Runnable runnable = () -> System.out.println("Running...")
```

In other words, if you need to pass a Runnable to a java.util.concurrent.Executor like so

```
 executor.execute(new Runnable() {
    @Override
    public void run() {
        System.out.println("Running...");
    }
});
```

you can use a lambda expression to produce code with the same effect:

```
 executor.execute(() -> System.out.println("Running..."));
```

Short and sweet. And clearer and more expressive too.

Changes to the Interface

Before I delve deeper into lambda expressions, I have to mention that starting Java 8 you can have default and static methods in an interface. This section explains what default and static methods are and why this major overhaul of the Java language was needed to enable lambda expressions to blend into the Java core libraries.

Default Methods

Extending an interface is a safe way of adding functionality to the interface. However, you end up with two interfaces with similar functionality. This is acceptable if you only need to extend one or two interfaces. If you need to add new features to hundreds of interfaces, this has certainly become a serious issue.

This is exactly what the Java language designers faced when they were trying to add lambda expressions to Java 8 and add support for lambda in dozens of interfaces in the Collection Framework. The interfaces needed new methods to support lambda expressions, but extending all the interfaces would double the number of interfaces and some would probably end up with ugly names such as List2 or ExtendedSet.

Instead, they resolved this by adding the default method to the language. A default method in an interface is a method with implementation. A class implementing the interface does not have to implement the default method, which means you can add new methods to an interface without breaking backward compatibility.

To make a method in an interface a default method, add the keyword default in front of the method signature. Additionally, instead of terminating the signature with a semicolon, add a pair of brackets and write code in the brackets. Here is an example.

```
 default java.lang.String getDescription() {
    return "This is a default method";
}
```

As you will learn later, a lot of Java interfaces in JDK 1.8 now have default methods.

When extending an interface with default methods, you have these options.

*   Ignore the default methods, in effect inheriting them,
*   Re-declare the default methods, which makes them abstract,
*   Override the default methods.

Remember that the main reason Java now support default methods is for backward compatibility. By no means should you start writing programs without classes.

Static Methods

A static method in a class is shared by all instances of the class. In Java 8 and later you can have static methods in an interface so that all static methods associated with an interface can be written in the interface, rather than in a helper class.

The signature of a static method is similar to that of a default method. Instead of the keyword default, however, you use the keyword static. Static methods in an interface are public by default.

Static methods in an interface are rare. Of the close to 30 interfaces in the java.util package, only two contain static methods.

Functional Interfaces

In addition to the default and static methods, there is another prerequisite for learning the lambda expression: the functional interface. A functional interface is an interface that has exactly one abstract method that does not override a java.lang.Object method. A functional interface is also called a single abstract method (SAM) interface. For example, java.lang.Runnable is a functional interface because it has only one abstract method, run. A functional interface may have any number of default and static methods and methods that override public methods in java.lang.Object and still qualifies as a functional interface. For example, the Calculator interface in Listing 1.1 is a functional interface with a single abstract method called calculate. It is a functional interface even though it has two default methods and another abstract method overriding the toString method from java.lang.Object.

Listing 1.1: A functional interface

```
 package app01;
public interface Calculator {

    double calculate(int a, int b);

    public default int subtract(int a, int b) {
        return a - b;
    }

    public default int add(int a, int b) {
        return a * b;
    }

    @Override
    public String toString();
}
```

Examples of functional interfaces in the core Java library include java.lang.Runnable, java.lang.AutoCloseable, java.lang.Comparable and java.util.Comparator. In addition, the new package java.util.function contains dozens of functional interfaces and is discussed in the section “Predefined Functional Interfaces” later in this chapter. Optionally, a functional interface can be annotated with @FunctionalInterface.

Why is the functional interface important? Because you can use a lambda expression to create the equivalent of an anonymous inner class from a functional interface. You cannot use an interface that is not a functional interface for this purpose.

Lambda Expression Syntax

The Calculator interface in Listing 1.1 has a calculate method that can be the basis of a lambda expression. The method allows you to define any mathematical operation that takes two integers and returns a double. For instance, here are two lambda expressions based on Calculator.

```
 Calculator addition = (int a, int b) -> (a + b);
System.out.println(addition.calculate(5, 20)); // prints 25.0

Calculator division  = (int a, int b) -> (double) a / b;
System.out.println(division.calculate(5, 2)); // prints 2.5
```

The lambda expression is such an elegant design. How many more lines of code would you need to implement the same program without lambda expressions?

Now that you have acquainted yourself with the lambda expression, I will show you its formal syntax.

```
 (parameter list) -> expression
```

or

```
 (parameter list) -> { 
    statements
}
```

The parameter list is the same as the list of parameters of the abstract method in the underlying functional interface. However, the type for each parameter is optional. In other words, both of these expressions are valid.

```
 Calculator addition = (int a, int b) -> (a + b);
Calculator addition = (a, b) -> (a + b);
```

To summarize, a lambda expression is a shortcut to defining an implementation of a functional interface. A lambda expression is equivalent to an instance of a functional interface implementation. Since it is possible to pass objects as parameters to a method, it is too possible to pass lambda expressions as parameters to a method.

Predefined Functional Interfaces

The java.util.function package is a new package in JDK 8\. It contains more than forty predefined functional interfaces that can make it easier for you to write lambda expressions. Some of the predefined functional interfaces are shown in Table 1.1.

| Functional Interface | Description |
| Function | Models a function that can take one parameter and return a result. The result can be of a different type than the parameter. |
| BiFunction | Models a function that can take two parameters and return a result. The result can be of a different type than any of the parameters. |
| UnaryOperator | Represents an operation on a single operand that returns a result whose type is the same as the type of the operand. A UnaryOperator can be thought of as a Function whose return value is of the same type as the parameter. In fact, UnaryOperator is a subinterface of Function. |
| BiOperator | Represents an operation on two operands. The result and the operands must be of the same type. |
| Predicate | A Function that takes a parameter and returns true or false based on the value of the parameter. |
| Supplier | Represents a supplier of results. |
| Consumer | An operation that takes a parameter and returns no result. |

Table 1.1: Core functional interfaces

Function, BiFunction and Other Variants

The Function interface is used to create a one-argument function that returns a result. It is a parameterized type and here is its definition.

```
 public interface Function<T, R>
```

Here, T represents the type of the argument and R the type of the result.

Function has one abstract method, apply, whose signature is as follows.

```
 R apply(T argument)
```

This is the method you need to override when using Function. For example, the class in Listing 1.2 defines a Function for converting miles to kilometers. The Function takes an Integer as an argument and returns a Double.

Listing 1.2: The FunctionDemo1 class

```
 package app01.function;
import java.util.function.Function;

public class FunctionDemo1 {
    public static void main(String[] args) {
        Function<Integer, Double> milesToKms = 
                (input) -> 1.6 * input;
        int miles = 3;
        double kms = milesToKms.apply(miles);
        System.out.printf("%d miles = %3.2f kilometers\n", 
                miles, kms);
    }
}
```

If you run the FunctionDemo1 class, you will see this on your console.

```
 3 miles = 4.80 kilometers
```

A variant of Function, BiFunction takes two arguments and returns a result. Listing 1.3 shows an example of BiFunction. It uses BiFunction to create a function that calculates an area given a width and a length. Invoking the function is done by calling its apply method.

Listing 1.3: The BiFunctionDemo1 class

```
 package app01.function;
import java.util.function.BiFunction;

public class BiFunctionDemo1 {
    public static void main(String[] args) {
        BiFunction<Float, Float, Float> area =
                (width, length) -> width * length;
        float width = 7.0F;
        float length = 10.0F;
        float result = area.apply(width, length);
        System.out.println(result);
    }
}
```

Running the BiFunctionDemo1 class prints this on the console.

```
 70.0
```

In addition to BiFunction, there are also variants that are specializations of Function. For example, the IntFunction interface always takes an Integer and requires only one parameterized type for the result type. Its apply method returns an int.

```
 R apply(int input)
```

The LongFunction and DoubleFunction interfaces are similar to IntFunction, except they take a long and a double as an argument, respectively.

Then, there are variants that do not require parameterized arguments at all, because they have been designed for a specific argument type and a specific return type. For instance, the IntToDoubleFunction interface can be used to create a function that accepts an int and returns a double. Instead of apply, the interface offers an applyAsDouble method. An example of IntToDoubleFunction interface is given in Listing 1.4\. It is a function that converts a temperature on the Celcius scale to Fahrenheit.

Listing 1.4: The IntToDoubleFunctionDemo1 class

```
 package app01.function;
import java.util.function.IntToDoubleFunction;

public class IntToDoubleFunctionDemo1 {
    public static void main(String[] args) {
        IntToDoubleFunction celciusToFahrenheit = 
                (input) -> 1.8 * input + 32;
        int celcius = 100;
        double fahrenheit = 
                celciusToFahrenheit.applyAsDouble(celcius);
        System.out.println(celcius + "\u2103" + " = " 
                + fahrenheit + "\u2109\n");
    }
}
```

This is the output of IntToDoubleFunctionDemo1.

```
 100? = 212.0?
```

Similar to IntToDoubleFunction are LongToDoubleFunction and LongToIntFunction. I am sure you can guess what they do from their names.

The UnaryOperator interface is another specialization of Function whose operand type is the same as the return type. Its declaration is as follows.

```
 public interfaceUnaryOperator<T> extends Function<T,T>
```

BinaryOperator is a specialization of BiFunction. BinaryOperator represents an operation with two operands of the same type and returns a result that has the same type as the operands.

Predicate

A Predicate is a function that takes a parameter and returns true or false based on the value of the parameter. It has a single abstract method called test.

For example, the PredicateDemo1 class in Listing 1.5 defines a Predicate that evaluates a string input and returns true if every character in the string is a number.

Listing 1.5: The PredicateDemo1 class

```
 package app01.function;
import java.util.function.Predicate;

public class PredicateDemo1 {
    public static void main(String[] args) {
        Predicate<String> numbersOnly = (input) -> {
            for (int i = 0; i < input.length(); i++) {
                char c = input.charAt(i);
                if ("0123456789".indexOf(c) == -1) {
                    return false;
                }
            }
            return true;
        };

        System.out.println(numbersOnly.test("12345"));// true
        System.out.println(numbersOnly.test("100a")); // false
    }
}
```

Supplier

A Supplier takes no parameter and returns a value. Implementations must override its get abstract method and returns an instance of the interface’s type parameter.

Listing 1.6 shows an example of Supplier. It defines a Supplier that returns a one-digit random number and uses a for loop to print five random numbers.

Listing 1.6: The SupplierDemo1 class

```
 package app01.function;
import java.util.Random;
import java.util.function.Supplier;

public class SupplierDemo1 {
    public static void main(String[] args) {
        Supplier<Integer> oneDigitRandom = () -> {
            Random random = new Random();
            return random.nextInt(10);
        };
        for (int i = 0; i < 5; i++) {
            System.out.println(
                    oneDigitRandom.get());
        }
    }
}
```

There are also specialized variants of Supplier, such as DoubleSupplier (returns a Double), IntSupplier and LongSupplier.

Consumer

A Consumer is an operation that returns no result. It has one abstract method called accept.

Listing 1.7 shows an example of Consumer that takes a string and print it center-justified.

Listing 1.7: Consumer example

```
 package app01.function;
import java.util.function.Consumer;
import java.util.function.Function;

public class ConsumerDemo1 {
    public static void main(String[] args) {
        Function<Integer, String> spacer = (count) -> {
            StringBuilder sb = new StringBuilder(count);
            for (int i = 0; i < count; i++) {
                sb.append(" ");
            }
            return sb.toString();
        };

        int lineLength = 60; // characters
        Consumer<String> printCentered = 
                (input) -> {
                    int length = input.length();
                    String spaces = spacer.apply(
                            (lineLength - length) / 2);
                    System.out.println(spaces + input);
                };

        printCentered.accept("A lambda expression a day");
        printCentered.accept("makes you");
        printCentered.accept("look smarter");
    }
}
```

The example in Listing 1.7 features a Consumer that takes a String and prints it after prefixing it with a certain number of spaces. The maximum number of characters in each line is 60 and the spaces are obtained by calling a Function named spacer. The implementation of the Consumer’s accept method is given by this Lambda expression.

```
 (input) -> {
                    int length = input.length();
                    String spaces = spacer.apply(
                            (lineLength - length) / 2);
                    System.out.println(spaces + input);
                }
```

The function spacer returns the specified number of spaces and is defined as

```
 Function<Integer, String> spacer = (count) -> {
            StringBuilder sb = new StringBuilder(count);
            for (int i = 0; i < count; i++) {
                sb.append(" ");
            }
            return sb.toString();
        };
```

The function employs a for loop that appends a space to a StringBuilder  count number of times, where count is the parameter to the function. When the loop exits, it returns the String representation of the StringBuilder.

If you run the ConsumerDemo1 class, you will see this on your console.

```
 A lambda expression a day
                         makes you
                        look smarter
```

Summary

A new feature in Java 8, lambda expressions can make certain constructs shorter and more readable, especially when you are dealing with inner classes. This chapter discussed lambda expressions, functional interfaces, the pre-defined functional interfaces and method references.

Chapter 2

Method References

In Chapter 1 you learned about the lambda expression. This chapter discusses the method reference, a subfeature of the lambda expression that can make writing lambda expressions even easier.

Overview

A lot of Java methods take a functional interface as an argument. For instance, one of the sort methods in java.util.Arrays accepts an instance of Comparator, which is a functional interface. The signature of the sort method is as follows.

```
 public static T[] sort(T[] array, Comparator<? super T> comparator)
```

Instead of passing an implementation of Comparator to the sort method, you can pass a lambda expression. You have seen how to do this in the previous chapter.

Now, you can go one step further by passing a method reference in lieu of a lambda expression. A method reference is simply a class name or an object reference followed by the double colon operator (::) and a method name.

Why would you want to use a method reference? There are two reasons for this.

1\. A method reference has shorter syntax than a lambda expression because a method reference does not contain a definition like a lambda expression. The method body is defined somewhere else.

2\. You can use an existing method, thus promoting code reuse.

You can use a reference to a static method, an instance method or even a constructor. You use the double colon (::), a new operator in Java 8, to separate the class name/object reference and the method/constructor name. The class that encapsulates the referenced method does not have to implement the functional interface.

The syntax for method references is one of the following.

```
 ClassName::staticMethodName
ContainingType::instanceMethod
objectReference::methodName
ClassName::new
```

Each of the kinds of method references are discussed in the following sections.

Reference to A Static Method

A reference to a static method can be passed as an argument to a method that expects a functional interface if the method has a compatible return type and compatible argument types with the functional interface’s abstract method.

As the first example in this topic, consider the NoMethodRef class in Listing 2.1, which illustrates the use of a functional interface without method references. The class defines a functional interface called StringListFormatter that takes a List of Strings and formats the strings. The format method, the abstract method of the interface, takes a delimiter and a List of Strings. There is also a formatAndPrint static method that takes an instance of StringListFormatter, a delimiter and a List of Strings. This method in turn calls the format method on the StringListFormatter and prints the formatted list.

Listing 2.1: The NoMethodRef class

```
 package app02.methodref;
import java.util.Arrays;
import java.util.List;

public class NoMethodRef {

    @FunctionalInterface
    interface StringListFormatter {
        String format(String delimiter, List<String> list);
    }

    public static void formatAndPrint(StringListFormatter formatter, 
            String delimiter, List<String> list) {
        String formatted = formatter.format(delimiter, list);
        System.out.println(formatted);
    }

    public static void main(String[] args) {
        List<String> names = Arrays.asList("Don", "King", "Kong");

        StringListFormatter formatter =
                (delimiter, list) -> {
                    StringBuilder sb = new StringBuilder(100);
                    int size = list.size();
                    for (int i = 0; i < size; i++) {
                        sb.append(list.get(i));
                        if (i < size - 1) {
                            sb.append(delimiter);
                        }
                    }
                    return sb.toString();
                };
        formatAndPrint(formatter, ", ", names);
    }
}
```

The main method in NoMethodRef constructs a string list with three elements and creates an implementation of StringListFormatter with this lambda expression.

```
 StringListFormatter formatter =
                (delimiter, list) -> {
                    StringBuilder sb = new StringBuilder(100);
                    int size = list.size();
                    for (int i = 0; i < size; i++) {
                        sb.append(list.get(i));
                        if (i < size - 1) {
                            sb.append(delimiter);
                        }
                    }
                    return sb.toString();
                };
```

Basically, it iterates over the List and adds a delimiter between two elements. No delimiter is appended after the last element.

The main method then calls the formatAndPrint method passing the lambda expression , a delimiter and the string list. If you run NoMethodRef, you will see the formatted list:

```
 Don, King, Kong
```

After spending twenty minutes writing the code, you realized that the lambda expression does the same job as the join method of the String class. This is a static method added to String in JDK 1.8\. One of its overrides has the following signature.

```
 public static String join(CharSequence delimiter,
        Iterable<? extends CharSequence> elements)
```

Compare it with the format method in the functional interface in Listing 2.1.

```
 public String format(java.langString delimiter, 
        java.util.List<String> list);
```

Since List extends Iterable and String implements CharSequence, join is compatible with format.

A method reference allows you to reuse an existing implementation such as String.join(). As such, you can rewrite the NoMethodRef class to use a reference to String.join(). This is illustrated in the MethodReferenceDemo1 class in Listing 2.2.

Listing 2.2: The MethodReferenceDemo1 class

```
 package app02.methodref;
import java.util.Arrays;
import java.util.List;

public class MethodReferenceDemo1 {

    @FunctionalInterface
    interface StringListFormatter {
        String format(String delimiter, List<String> list);
    }

    public static void formatAndPrint(StringListFormatter formatter, 
            String delimiter, List<String> list) {
        String formatted = formatter.format(delimiter, list);
        System.out.println(formatted);
    }

    public static void main(String[] args) {
        List<String> names = Arrays.asList("Don", "King", "Kong");
        formatAndPrint(String::join, ", ", names);
    }
}
```

You still have the same StringListFormatter interface and the same formatAndPrint method. However, the main method no longer contains a lambda expression implementing StringListFormatter. Instead, you use String.join as an implementation of StringListFormatter.

```
 formatAndPrint(String::join, ", ", names);
```

As a side note, note that the abstract method in StringListFormatter takes two parameters and returns a value. This is a good candidate for a BiFunction. The WithBiFunction class in Listing 2.3 is a rewrite of the MethodReferenceDemo1 class that eliminates the StringListFormatter interface entirely. The formatAndPrint method has also been modified to accept a BiFunction as its first parameter.

Listing 2.3: The WithBiFunction class

```
 package app02.methodref;
import java.util.Arrays;
import java.util.List;
import java.util.function.BiFunction;

public class WithBiFunction {

    public static void formatAndPrint(
            BiFunction<String, List<String>, String> formatter, 
            String delimiter, List<String> list) {
        String formatted = formatter.apply(delimiter, list);
        System.out.println(formatted);
    }

    public static void main(String[] args) {
        List<String> names = Arrays.asList("Don", "King", "Kong");
        formatAndPrint(String::join, ", ", names);
    }
}
```

Reference to An Instance Method where An Object Reference Is Available

The compatibility rule for this kind of method reference is the same as the method reference to a static method. The referenced method must have a compatible return value and compatible arguments as the abstract method of the functional interface the method replaces.

For example, in JDK 1.8 the java.lang.Iterable interface has a default method named forEach that accepts a Consumer:

```
 default void forEach(java.util.function.Consumer<? super T> action)
```

forEach performs the given action for each element of the Iterable. Thanks to inheritance, this method is inherited by its subinterface List, which I will use in the example in Listing 2.4.

Listing 2.4: Referencing an instance method in an object

```
 package app02.methodref;
import java.util.Arrays;
import java.util.List;

public class MethodReferenceDemo2 {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana");
        // with lambda expression
        fruits.forEach((name) -> System.out.println(name));

        // with method reference
        fruits.forEach(System.out::println);
    }
}
```

The MethodReferencDemo2 class has a list of fruits that needs to be printed. You can do this by calling the forEach method, passing a Consumer in the form of a lambda expression like so:

```
 fruits.forEach((name) -> System.out.println(name));
```

Alternatively, since System.out is an existing object that the system has created for you, you can use a method reference to the println method on System.out.

```
 fruits.forEach(System.out::println);
```

Reference to An Instance Method where No Object Reference Is Available

Hold on tight. This one is a bit tricky and requires your full concentration.

You can pass a reference to an instance method as a method argument to replace a functional interface. In this case, you do not have to explicitly create an instance of the containing class. The syntax for this kind of method reference is different from that of the first and second kinds of method references. With the first two kinds, the number of arguments must be the same as the number of arguments expected by the functional interface’s abstract method. When using an instance method without an object reference, the referenced method must have one fewer argument than the number of arguments expected by the functional interface’s abstract method. Therefore, if the functional interface’s abstract method takes four arguments, the referenced instance method must take only three arguments, which must be compatible with the second, third and fourth arguments of the abstract method. In addition, the first argument of the abstract method must be of a type that is compatible as the class containing the instance method.

The compatibility rule for this kind of method reference is depicted below. The first line is a pseudo-signature of the functional interface’s abstract method and the second line a pseudo-signature of the referenced instance method.

```
 returnType abstractMethod(type-1, type-2, type-3, type-4)
returnType instanceMethod(type-2, type-3, type-4)
```

Here, type-1 must be compatible with the class containing the instance method because the class will be instantiated and the instance passed as the first argument to the abstract method, along with the other arguments.

This will become clear after you have seen the example for this kind of method reference.

Listing 2.5: The MethodReferenceDemo3 class

```
 package app02.methodref;
import java.util.Arrays;

public class MethodReferenceDemo3 {

    public static void main(String[] args) {
        String[] names = {"Alexis", "anna", "Kyleen"};

        Arrays.sort(names, String::compareToIgnoreCase);
        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

The example in Listing 2.5 shows how to pass an instance method reference to Arrays.sort in lieu of a Comparator. The MethodReferenceDemo3 class contains a string array with three names where case-sensitivity is not strictly adhered to. If you use an override of Arrays.sort that only takes one argument to sort this array, the names will be sorted as

```
 Alexis, Kyleen, anna
```

This is not what you really want. So, you need to use Arrays.sort that also takes a Comparator:

```
 public static <T> void sort(T[] array, Comparator<? super T> c)
```

The example shows how you can use an instance method reference String.compareIgnoreCase to replace a Comparator (Recall that Comparator is a functional interface). Here is the signature of String.compareToIgnoreCase.

```
 public int compareToIgnoreCase(String str)
```

It has one less argument than the signature of Comparator.compare.

```
 int compare(String str1, String str2)
```

This is perfect for the second kind of method reference.

If you run the code, you will see that the names are sorted correctly. Here is the result.

```
 Alexis
anna
Kyleen
```

Reference to A Constructor

The fourth kind of method reference uses a constructor. The syntax for a constructor reference is as follows.

```
 ClassName::new
```

Suppose you need a method to convert an Integer array to a Collection and you need to be able to determine whether the resulting collection is a List or a Set. To this end, you can create the arrayToCollection method in Listing 2.6.

Listing 2.6: The MethodReferenceDemo4 class

```
 package app02.methodref;
import java.util.ArrayList;
import java.util.Collection;
import java.util.HashSet;
import java.util.function.Supplier;

public class MethodReferenceDemo4 {

    public static Collection<Integer> arrayToCollection(
            Supplier<Collection<Integer>> supplier, Integer[] 
                numbers) {
        Collection<Integer> collection = supplier.get();
        for (int i : numbers) {
            collection.add(i);
        }
        return collection;
    }

    public static void main(String[] args) {
        Integer[] array = {1, 8, 5};
        Collection<Integer> col1 
                = arrayToCollection(ArrayList<Integer>::new, array);
        System.out.println("Natural order");
        col1.forEach(System.out::println);
        System.out.println("=======================");
        System.out.println("Ascending order");
        Collection<Integer> col2 
                = arrayToCollection(HashSet<Integer>::new, array);
        col2.forEach(System.out::println);
    }
}
```

Instead of passing this lambda expression as the first argument to the method.

```
 () -> new ArrayList<Integer>()
```

You can simply pass this reference to the ArrayList constructor.

```
 ArrayList<Integer>::new
```

And, instead of this

```
 () -> new HashSet<Integer>()
```

you can write

```
 HashSet<Integer>::new
```

If you run the example, you will see this on the console.

```
 Natural order
1
8
5
=======================
Ascending order
1
5
8
```

More examples of constructor references can be found in Chapter 4, “The Stream API.”

Summary

A new feature in Java 8, lambda expressions can make certain constructs shorter and more readable, especially when you are dealing with inner classes. This chapter discussed the method reference a subfeature that can make writing lambda expressions easier.

Chapter 3

Optional and Similar Classes

Java programmers have been dealing with null pointer exceptions for years. In Java 8 there is a new way of handling them, by wrapping an object that can potentially be null in a class called Optional.

This chapter covers Optional and similar classes.

Overview

Java 8 adds the Optional, OptionalInt, OptionalLong and OptionalDouble classes to deal with NullPointerExceptions. Part of the java.util package, these classes are excellent examples of classes that heavily use lambda expressions and method references.

These four classes are similar and Optional is the most important of them as it can be used with any type whereas the other classes are only suitable for integers, longs or doubles, respectively. Consequently, Optional is the main focus of this chapter.

Optional is a container for a value that can potentially be null. As you should know by now, trying to call a method or a field on a null reference variable throws a NullPointerException. Handling null is not hard, but it can be tedious. Consider the code in Listing 3.1 that shows a Company class that can have an Office, which in turn can have an Address. To make things simple, here an Address only contains two fields, street and city. All these properties can be null. A Company may not have an Office and an Address may not have full data about the street and city.

Listing 3.1: Tedious way of checking for nullity

```
 package app03.optional1;

class Company {
    private String name;
    private Office office;
    public Company(String name, Office office) {
        this.name = name;
        this.office = office;
    }

    public String getName() {
        return name;
    }

    public Office getOffice() {
        return office;
    }
}

class Office {
    private String id;
    private Address address;

    public Office(String id, Address address) {
        this.id = id;
        this.address = address;
    }

    public String getId() {
        return id;
    }

    public Address getAddress() {
        return address;
    }
}

class Address {
    private String street;
    private String city;

    public Address(String street, String city) {
        this.street = street;
        this.city = city;
    }

    public String getStreet() {
        return street;
    }

    public String getCity() {
        return city;
    }
}

public class OptionalDemo1 {

    public static void main(String[] args) {
        Address address1 = new Address(null, "New York");
        Office office1 = new Office("OF1", address1);
        Company company1 = new Company("Door Never Closed",
            office1);

        // What is the street address of company1?
        // In which city company1 is located?
        String streetAddress = null;
        String city = null;
        if (company1 != null) {
            Office office = company1.getOffice();
            if (office != null) {
                Address address = office.getAddress();
                if (address != null) {
                    streetAddress = address.getStreet();
                    city = address.getCity();
                }
            } 
        }
        System.out.println("Street Name:" + streetAddress);
        System.out.println("City:" + city);
    }
}
```

The OptionalDemo1 class in Listing 3.1 creates a Company for testing and tries to get the street address of the company. Realizing that any of the fields can be null, the programmer made a conscious attempt to test each single instance for nullity before calling a method on it, resulting in this code:

```
 if (company1 != null) {
            Office office = company1.getOffice();

            if (office != null) {
                Address address = office.getAddress();
                if (address != null) {
                    streetAddress = address.getStreet();
                    city = address.getCity();
                }
            } 
        }
```

This is kind of tedious and readability suffers.

The Optional class can help. If you decide to use it, you wrap every field that can potentially be null in an Optional. For example, the office field in Company should now be:

```
 private Optional<Office> office;
```

And the city field in Address should be

```
 private Optional<String> city;
```

Before you learn how to rewrite the example in Listing 3.1 using Optional, look at the methods of Optional in Table 3.1.

| Method | Description |
| empty | Returns an empty Optional |
| filter | If a value is present and matches the given predicate, return an Optional describing the value. Otherwise, returns an empty Optional. |
| flatMap | If a value is preset, apply the specified mapping function on the value and return and Optional describing the mapping result. If a value is not present, return an empty Optional. |
| get | If a value is present, returns the value. Otherwise, throw a NoSuchElementException. |
| ifPresent | If a value is present, invoked the given Consumer with the value. |
| isPresent | Returns true if a value is present. Otherwise, returns false. |
| map | If a value is present, apply the given mapping function to it. If the result is not null, return an Optional describing the result. |
| of | Returns an Optional describing the given non-null value. |
| ofNullable | If the given value is non-null, returns an Optional describing the value. If the value is null, returns an empty Optional. |
| orElse | If a value is present, returns the value. Otherwise, returns the specified value. |

Table 3.1: More important methods of Optional

The methods are easy to use. To wrap a value in an Optional, call its static of or ofNullable method. You use of if you are certain the value you are wrapping is not null. If the value is potentially null, use ofNullable instead. Alternatively, the empty method is also static and returns an empty Optional, i.e. an Optional without a value.

The rest of the methods are for handling an Optional. If you simply want to retrieve the value in an Optional, you would first check if a value is present. You can do this by using isPresent followed by get:

```
 if (optional.isPresent()) {
    value = optional.get();
}
```

However, this is similar to checking for nullity when not using Optional. There are better ways, though.

The ifPresent method accepts a Consumer that will be called if a value is present. So if you simply want to print the value, you can do this.

```
 optional.ifPresent(System.out::println);
```

If no value is present, nothing will happen. So this is getting better, isn’t it?

However, wait until you get to use flatMap. This method applies a mapping function and returns an Optional describing the value. Better still, it can be cascaded, like this to replace the series of null check in Listing 3.14:

```
 company1.flatMap(Company::getOffice)
        .flatMap(Office::getAddress)
        .flatMap(Address::getCity)
        .ifPresent(System.out::println);
```

Now look at Listing 3.2 that contains a rewrite of the code in Listing 3.1\. All fields that can potentially be null have been wrapped in Optionals.

Listing 3.2: Using Optional

```
 package app03.optional2;
import java.util.Optional;

class Company {
    private String name;
    private Optional<Office> office;

    public Company(String name, Optional<Office> office) {
        this.name = name;
        this.office = office;
    }

    public String getName() {
        return name;
    }

    public Optional<Office> getOffice() {
        return office;
    }
}

class Office {
    private String id;
    private Optional<Address> address;

    public Office(String id, Optional<Address> address) {
        this.id = id;
        this.address = address;
    }

    public String getId() {
        return id;
    }

    public Optional<Address> getAddress() {
        return address;
    }
}

class Address {
    private Optional<String> street;
    private Optional<String> city;

    public Address(Optional<String> street, Optional<String> city) {
        this.street = street;
        this.city = city;
    }

    public Optional<String> getStreet() {
        return street;
    }

    public Optional<String> getCity() {
        return city;
    }
}

public class OptionalDemo2 {
    public static void main(String[] args) {
        Optional<Address> address1 = Optional.of(
                new Address(Optional.ofNullable(null), 
                        Optional.of("New York")));
        Optional<Office> office1 = Optional.of(
                new Office("OF1", address1));

        Optional<Company> company1 = Optional.of(
                new Company("Door Never Closed", office1));

        // What is the street address of company1?
        // In which city company1 is located?
        Optional<Office> maybeOffice = 
                company1.flatMap(Company::getOffice);
        Optional<Address> maybeAddress = 
                maybeOffice.flatMap(Office::getAddress);
        Optional<String> maybeStreet = 
                maybeAddress.flatMap(Address::getStreet);
        maybeStreet.ifPresent(System.out::println);
        if (maybeStreet.isPresent()) {
            System.out.println(maybeStreet.get());
        } else {
            System.out.println("Street not found");
        }

        // shorter way
        String city = company1.flatMap(Company::getOffice)
            .flatMap(Office::getAddress)
            .flatMap(Address::getCity)
            .orElse("City not found");
        System.out.println("City: " + city);

        // only print if city is not null
        company1.flatMap(Company::getOffice)
                .flatMap(Office::getAddress)
                .flatMap(Address::getCity)
                .ifPresent(System.out::println);
    }
}
```

The OptionalDemo2 class shows how to get the street and city of a company, first by assigning the return value of each flatMap invocation to a variable and then by cascading it.

OptionalInt, OptionalLong and OptionalDouble

The OptionalInt, OptionalLong and OptionalDouble classes have a subset of the methods offered by Optional. For example, they have these methods: empty, ifPresent, isPresent, and of. of takes a primitive and since a primitive cannot be null, there is no ofNullable method. There is no get method either. Instead, OptionalInt has a getAsInt method, OptionalLong a getAsLong method and OptionalDouble a getAsDouble method. There are no filter, flatMap and map methods either.

Summary

Java programmers have to deal with null pointer exceptions every where in his or her code. Java 8 introduces Optional and similar classes as a new powerful way of tackling null pointer exceptions. You have learned how to use Optional in this chapter.

Chapter 4

The Stream API

In this chapter you will learn about the Stream API, a new feature of JDK 8\. To understand the topics in this chapter, you need to know how to use Lambda expressions and the predefined functional interfaces in java.util.function, both discussed in Chapter 1, “Lambda Expressions.”

Overview

A stream is like a pipe, but instead of transporting water or oil, a stream transfers data from a source to a destination. Depending on the mode of transfer, a stream can be either sequential or parallel. A parallel stream is especially useful if the computer the program is running on has a multicore CPU.

At first glance, a stream may look like a collection. However, a stream is not a data structure for storing objects, it only moves them. As such, you cannot add an element to a stream as you would to a collection.

The main reason for using a stream is for its supports for sequential and parallel aggregate operations. For example, you can easily filter, sort or map the elements in a stream.

The Stream API consists of the types in the java.util.stream package. The Stream interface is the most frequently used stream type. A Stream can be used to transfer any type of objects. There are also specializations of Stream: IntStream, LongStream and DoubleStream. All the four stream types are derived from BaseStream.

Table 4.1 shows some of the methods defined in the Stream interface.

| Method | Description |
| concat | Lazily concatenates or links together two streams. It returns a new stream whose elements are all the elements of the first stream followed by all the elements of the second stream. |
| count | Returns the number of elements of the stream. |
| empty | Creates and returns an empty stream. |
| filter | Returns a new stream whose elements are all the elements of this stream that match the given predicate. |
| forEach | Performs an action on each element of the stream. |
| limit | Returns a new stream having the specified maximum number of elements from the current stream. |
| map | Returns a stream consisting of the results of applying the given function to the elements of this stream. |
| max | Returns the maximum element of this stream according to the given comparator. |
| min | Returns the minimum element of this stream according to the given comparator. |
| of | Returns a stream whose source is the given values. |
| reduce | Performs a reduction on this stream’s elements using an identity and an accumulator. |
| sorted | Returns a new stream containing the elements of this stream in natural order |
| toArray | Returns an array containing the elements of this stream. |

Table 4.1: More important methods of Stream

Some of the Stream methods perform intermediate operations and some perform terminal operations. An intermediate operation transforms a stream into another stream. Methods such as filter, map and sorted are examples of methods that perform intermediate operations. A terminal operation produces a result or side-effect. Methods such as count and forEach perform terminal operations.

It is worth noting that streams are lazy. Computation on the source is only performed when a terminal operation is started.

Stream’s methods will be explained in detail in the sections to come.

Creating and Obtaining a Stream

You can use the of static method in Stream to create a sequential stream. For example, the following code snippet creates a Stream of Integers with three elements.

```
 Stream<Integer> stream = Stream.of(100, 200, 300);
```

Or, you can pass an array to the of method:

```
 String[] names = {"Bart", "Lisa", "Maggie"};
Stream<String> stream = Stream.of(names);
```

The java.util.Arrays utility class now has a stream method for converting an array to a sequential stream. For instance, you can rewrite the code above using Arrays to create a Stream from an array.

```
 String[] names = {"Bart", "Lisa", "Maggie"};
Stream<String> stream = Arrays.stream(names);
```

In addition, the java.util.Collection interface also has default methods named stream and parallelStream that return a sequential or a parallel stream, respectively, with the collection as its source. Their signatures are as follows.

```
 default java.util.stream.Stream<E> stream()
default java.util.stream.Stream<E> parallelStream()
```

Thanks to these methods in Collection, getting a Stream from a List or a Set is a breeze.

On top of that, the java.nio.file.Files class offers two methods that return a Stream<Path>, list and walk. list returns a Stream of Paths that point to the entries in the given path. On the other hand, walk walks through the entries in the given path and return them as a stream.

Files also contains a lines method that returns all lines in a text file as a Stream<String>.

For example, the ObtainStreamDemo class in Listing 4.1 shows how to obtain a stream from the Files class.

Listing 4.1: The ObtainStreamDemo class

```
 package app04;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.stream.Stream;

public class ObtainStreamDemo {

    public static void main(String[] args) {
        Path path = Paths.get(".");
        try {
            Stream<Path> list = Files.list(path);
            list.forEach(System.out::println);
        } catch (IOException ex) {
            ex.printStackTrace();
        }
    }
}
```

The code in Listing 4.1 constructs a Path that references the current directory (i.e. the directory from which the Java program was run) and passes it to Files.list. The method returns a Stream of Paths. The code then calls the forEach method on the Stream passing a Consumer that prints each entry. If you run the code, you will see all entries in the current path printed on the console.

Concatenating Streams

The Stream interface provides a concat method for lazily concatenating or linking two streams together. This method returns a new stream whose elements are all the elements of the first stream followed by all the elements of the second stream.

The code in Listing 4.2 shows how to concatenate two Streams of Strings and sort them.

Listing 4.2: Joining streams

```
 package app04;
import java.util.stream.Stream;

public class StreamConcatDemo {
    public static void main(String[] args) {
        Stream<String> stream1 = 
                Stream.of("January", "Christie");
        Stream<String> stream2 = 
                Stream.of("Okanagan", "Sydney", "Alpha");
        Stream.concat(stream1, stream2).sorted().
                forEach(System.out::println);
    }
}
```

If you run the StreamConcatDemo class in Listing 4.2, you will see the following printed on the console.

```
 Alpha
Christie
January
Okanagan
Sydney
```

Filtering

When you filter a stream you select the elements of the stream based on certain criteria and return a new Stream for the selected elements. You filter a stream by calling the filter method on a Stream object, passing a Predicate. The Predicate determines whether or not an element will be included in the new stream.

Here is the signature of the filter method.

```
 Stream<T> filter(java.util.function.Predicate<? super T> predicate)
```

As an example, the code in Listing 4.3 reads the example.txt file in Listing 4.4 and let pass only lines that are not empty and not a comment. A comment line starts with a hash (#) after removing all trailing spaces.

Listing 4.3: The StreamFilterDemo1 class

```
 package app04;
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.function.Predicate;
import java.util.stream.Stream;

public class StreamFilterDemo1 {
    public static void main(String[] args) {
        Predicate<String> notCommentOrEmptyLine
                = (line) -> line.trim().length() > 0
                && !line.trim().startsWith("#");
        try (FileReader fr = new FileReader("example.txt");
                BufferedReader br = new BufferedReader(fr)) {
            Stream<String> lines = br.lines();
            lines.filter(notCommentOrEmptyLine)
                    .forEach(System.out::println);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

Listing 4.4: The example.txt file

```
 # Set path so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"

fi
```

If you run the class in Listing 4.3, you will see these lines on the console. It prints three of five lines in the text file.

```
 if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

As a second example, the class in Listing 4.5 shows how you can use a stream to do a file search on your computer. To be more precise, the code displays all java files located in a given directory and any of its subdirectories.

Listing 4.5: The StreamFilterDemo2 class

```
 package app04;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.stream.Stream;

public class StreamFilterDemo2 {
    public static void main(String[] args) {
        // find all java files in the parent directory and
        // all its subdirectories
        Path parent = Paths.get("..");
        try {
            Stream<Path> list = Files.walk(parent);
            list.filter((Path p) -> p.toString().endsWith(".java"))
                    .forEach(System.out::println);
        } catch (IOException ex) {
            ex.printStackTrace();
        }
    }
}
```

The StreamFilterDemo2 class starts by constructing a Path that points to the parent of the current directory. It then passes the Path to Files.walk to obtain a Stream of Paths and assign the result to a local variable named list. Next, it filters the stream with a Predicate that will include all Paths whose name ends with .java and calls the forEach method to print the path.

Mapping

The Stream interface’s map method maps each element of a stream with the result of passing the element to a function. Here is the signature of map.

```
 <R> Stream<R> map(java.util.function.Function<? super T,
        ? extends R> mapper)
```

As you can see from the signature, the map method returns a new Stream of elements whose type may be different from the type of the elements of the current stream.

Consider the code in Listing 4.6 that shows a more useful and realistic example of a Stream to calculate the average age of all employees in a company. It does this in two steps. First, it calls the map method to convert a Stream of Employee objects to a Stream of Period objects. Each Period element of the new stream contains the period between today and each employee’s birthday. In other words, each Period element contains the age of an employee. In the second step, the code calls the mapToLong method to calculate the average age of all the employees.

Listing 4.6: The StreamMapDemo class

```
 package app04;
import java.time.LocalDate;
import java.time.Month;
import java.time.Period;
import java.util.stream.Stream;

public class StreamMapDemo {
    class Employee {
        public String name;
        public LocalDate birthday;
        public Employee(String name, LocalDate birthday) {
            this.name = name;
            this.birthday = birthday;
        }
    }

    public Employee[] getEmployees() {
        Employee[] employees = { 
            new Employee("Will Biteman", 
                    LocalDate.of(1984, Month.JANUARY, 1)), 
            new Employee("Sue Everyman", 
                    LocalDate.of(1980, Month.DECEMBER, 25)),
            new Employee("Ann Wangi",
                    LocalDate.of(1976, Month.JULY, 4)),
            new Employee("Wong Kaching",
                    LocalDate.of(1980, Month.SEPTEMBER, 1))
        };
        return employees;
    }

    public double calculateAverageAge(Employee[] employees) {
        LocalDate today = LocalDate.now();
        Stream<Employee> stream = Stream.of(employees);
        Stream<Period> periods = stream.map(
                (employee)-> Period.between(
                        employee.birthday, today));
        double avgAge = periods.mapToLong(
                (period)->period.toTotalMonths())
                .average().getAsDouble() / 12;
        return avgAge;
    }

    public static void main(String[] args) {
        StreamMapDemo demo = new StreamMapDemo();
        Employee[] employees = demo.getEmployees();
        double avgAge = demo.calculateAverageAge(employees);
        System.out.printf("Average employee age : %2.2f\n",
                avgAge);
    }
}
```

If you run the StreamMapDemo class, you will see the average age of the employees. Of course, the result will depend on when you run the program. When I ran it on my computer at the time of writing this book, I got the following result.

```
 Average employee age : 34.13
```

Reduction

One of the more useful methods in Stream is reduce, which can perform reduction operations. There are two overloads of this method:

```
 java.util.Optional<T> reduce(java.util.function.BinaryOperator<T> 
        accumulator)
T reduce(T identity,
        java.util.function.BinaryOperator<T> accumulator)
```

Looking at the two signatures, you probably notice that the reduce method reduces a Stream of type T to a single instance of type T, with the help of the specified BinaryOperator. Even though the description in the Java documentation is not that intuitive, in reality this method is not that hard to understand.

Figure 4.1 shows what happens behind the scene when a sequential stream of four elements is being reduced.

![](Images/0401.png)

Figure 4.1: Reducing a stream

First, element-1 and element-2 are used as operands to the specified binary operator. The result of this operation is an object of the same type as the elements, which I call result-a. Next, result-a and element-3 are passed to the binary operator, resulting result-b, which again has the same type as the elements. Finally, result-b and element-4 are passed to the binary operator, returning result-c. Since there is no more element in the stream, result-c is returned as the result of the reduction.

For a parallel stream, operations can be done in parallel. This means, the operation on element-1 and element-2 may take place at the same time as the operation on element-3 and element-4, and then the results of the first operation and the second operation are passed to the binary operator and its result returned.

Okay. Let’s now look at an example.

The StreamReductionDemo1 class in Listing 4.7 shows a Stream of four Order objects that is reduced to a single Order object, which is the Order placed most recently and having the largest value.

Listing 4.7: StreamReductionDemo1 class

```
 package app04;
import java.time.LocalDate;
import java.time.Month;
import java.util.Optional;
import java.util.stream.Stream;

public class StreamReductionDemo1 {
    class Order {
        public int orderId;
        public double value;
        public LocalDate orderDate;
        public Order(int orderId, double value, 
                LocalDate orderDate) {
            this.orderId = orderId;
            this.value = value;
            this.orderDate = orderDate;
        }
    }

    public Order[] getOrders() {
        Order[] orders = {
            new Order(1, 100.49,  
                    LocalDate.of(2014, Month.DECEMBER, 11)), 
            new Order(1, 88.09,  
                    LocalDate.of(2014, Month.DECEMBER, 29)), 
            new Order(1, 10.29,  
                    LocalDate.of(2014, Month.DECEMBER, 30)), 
            new Order(1, 100.49,
                    LocalDate.of(2014, Month.NOVEMBER, 22)) 
        };
        return orders;
    }

    public Optional<Order> getLatestLargestOrder(Order[] orders) {
        Stream<Order> stream = Stream.of(orders);
        Optional<Order> theOrder = stream.reduce((a, b) -> {
                if (a.value > b.value) {
                    return a;
                } else if (a.value < b.value) {
                    return b;
                } else {
                    if (a.orderDate.isAfter(b.orderDate)) {
                        return a;
                    } else {
                        return b;
                    }
                }
            });
        return theOrder;
    }

    public static void main(String[] args) {
        StreamReductionDemo1 demo = new StreamReductionDemo1();
        Order[] orders = demo.getOrders();
        Optional<Order> latestLargest = demo.getLatestLargestOrder(
                orders);
        if (latestLargest.isPresent()) {
            Order order = latestLargest.get();
            System.out.printf("Latest largest order value: $%2.2f,",
                    order.value);
            System.out.println(" date : " + order.orderDate);
        } else {
            System.out.println("No order found");
        }

    }
}
```

First, look at the Order class. The Order class models an order and has three fields, orderId, value and orderDate. The method main instantiates the StreamReductionDemo1 class and calls its getOrders method, which returns an Order array containing four orders. main then calls the getLatestLargestOrder method, passing the Order array.

The getLatestLargestOrder method is of interest here. It first creates a Stream<Order> using Stream’s of static method.

```
 Stream<Order> stream = Stream.of(orders);
```

It then calls the reduce method on the Stream passing a binary operator.

```
 Optional<Order> theOrder = stream.reduce((a, b) -> {
                if (a.value > b.value) {
                    return a;
                } else if (a.value < b.value) {
                    return b;
                } else {
                    if (a.orderDate.isAfter(b.orderDate)) {
                        return a;
                    } else {
                        return b;
                    }
                }
            });
```

The binary operator compares the values of the two Order operands and returns the one with the larger value. If both values are equal, the order with the latest order date is returned.

main then checks if the returned Optional has an Order. If so, the Order is unwrapped and its value and date are printed. If not, an error message will be displayed.

If you run the class you will see this on the console.

```
 Latest largest order value: $100.49, date : 2014-12-11
```

If the stream is empty, the reduce method will not throw an exception. It simply returns an empty Optional.

As a second example, consider the code in Listing 4.8\. The demo class uses a Stream to calculate the total order value in a given month.

Listing 4.8: StreamReductionDemo2 class

```
 package app04;
import java.time.LocalDate;
import java.time.Month;
import java.time.YearMonth;
import java.util.function.Predicate;
import java.util.stream.Stream;

public class StreamReductionDemo2 {
    class Order {
        public int orderId;
        public double value;
        public LocalDate orderDate;
        public Order(int orderId, double value, 
                LocalDate orderDate) {
            this.orderId = orderId;
            this.value = value;
            this.orderDate = orderDate;
        }
    }

    public Order[] getOrders() {
        Order[] orders = { 
            new Order(1, 100.49,  
                    LocalDate.of(2014, Month.DECEMBER, 11)), 
            new Order(1, 88.09,  
                    LocalDate.of(2014, Month.DECEMBER, 29)), 
            new Order(1, 10.29,  
                    LocalDate.of(2014, Month.DECEMBER, 30)), 
            new Order(1, 100.49,
                    LocalDate.of(2014, Month.NOVEMBER, 22)) 
        };
        return orders;
    }

    public double calculateSalesTotal(Order[] orders, 
            YearMonth yearMonth) {
        Predicate<Order> orderInGivenMonth
                = (order) -> order.orderDate.getMonth() 
                        == yearMonth.getMonth()
                && order.orderDate.getYear() 
                        == yearMonth.getYear();

        Stream<Order> stream = Stream.of(orders);
        return stream.filter(orderInGivenMonth)
                .mapToDouble((order) -> order.value)
                .reduce(0, (a, b) -> a+b);
    }

    public static void main(String[] args) {
        StreamReductionDemo2 demo = new StreamReductionDemo2();
        Order[] orders = demo.getOrders();
        double totalSalesForMonth = demo.calculateSalesTotal(
                orders, YearMonth.of(2014, Month.NOVEMBER));
        System.out.printf("Sales for Nov 2014 : $%2.2f\n",
                totalSalesForMonth);

        totalSalesForMonth = demo.calculateSalesTotal(
                orders, YearMonth.of(2014, Month.DECEMBER));
        System.out.printf("Sales for Dec 2014 : $%2.2f\n",
                totalSalesForMonth);
    }
}
```

The StreamReduceDemo2 class employs the same Order objects as those in StreamReduceDemo1. The calculateSalesTotal method creates a Stream from the Order array, filters the Orders to those having a given year/month and maps the elements to doubles before finally reducing them to a double.

If you run this demo class, you will see this on your console.

```
 Sales for Nov 2014 : $100.49
Sales for Dec 2014 : $198.87
```

Mutable Reductions

A mutable reduction operation accumulates a Stream’s elements into a container and returns the container. The container is mutable, hence the term mutable.

You use the Stream interface’s collect method to perform a mutable reduction operation. Its signature is as follows.

```
 <R> R collect(java.util.function.Supplier<R> supplier,
        java.util.function.BiConsumer<R, ? super T> accumulator,
        java.util.function.BiConsumer<R, R> combiner);
```

The collect method does its job in three steps, each step processing one of the arguments to the method.

In the first step, the method handles its first argument, which is a Supplier that returns a container such as a Collection or a StringBuilder. In a sequential stream, the Supplier is only called once and there will only be one container. In a parallel stream, however, the Supplier may be called multiple times and there may be multiple containers.

In the second step, the method tackles the second argument, which is a BiConsumer that performs the collection. Recall that a BiConsumer accepts two arguments of different types and do not return any value. Practically, the BiConsumer adds each stream element to the container or containers that the Supplier produced. In the case of a sequential stream, all elements are added to the same container because there is only one container. In a parallel stream, each element is added to a different container.

In the last step, the method processes the third argument, which is also a BiConsumer. In a sequential stream, no processing takes place and the argument has no effect as it is never called. Nevertheless, you cannot pass a null as the third argument. In a parallel stream, the collectors are merged using the operation specified by the BiConsumer.

The first example of this kind of operation is given in Listing 4.9\. It demonstrates how you can collect an array of strings into a StringBuilder. There are two streams involved, both doing the same thing. The first stream uses lambda expressions and the second uses method references.

Listing 4.9: StreamCollectDemo1 class

```
 package app04;
import java.util.stream.Stream;

public class StreamCollectDemo1 {
    public static void main(String[] args) {
        String[] strings = { "a", "b", "c", "d" };
        Stream<String> stream1 = Stream.of(strings);
        StringBuilder sb1 = stream1.collect(
                () -> new StringBuilder(), 
                (a1, b1) -> a1.append(b1),
                (a2, b2) -> a2.append(b2));
        System.out.println(sb1.toString());

        Stream<String> stream2 = Stream.of(strings);
        StringBuilder sb2 = stream2.collect(
                StringBuilder::new, 
                StringBuilder::append,
                StringBuilder::append);
        System.out.println(sb2.toString());
    }
}
```

For each stream, the collect method starts by creating a StringBuilder. Since a sequential stream is involved, there is only one StringBuilder. Next, the method appends each stream element to the StringBuilder. Since there are four elements in the stream, the append method of the StringBuilder is called four times.

Since this is a sequential stream, the third argument is not processed. The collect method simply returns the StringBuilder that now contains “abcd”.

Listing 4.10 shows a second example for the mutable reduction operation. This time I use a List as the container, in a sequential stream setting. Again, there are two streams involved, one using lambda expression one using a method reference. The collect method here returns a List that contains four elements.

Listing 4.10: StreamCollectDemo2 class

```
 package app04;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Stream;

public class StreamCollectDemo2 {
    public static void main(String[] args) {
        String[] strings = { "a", "b", "c", "d" };
        Stream<String> stream1 = Stream.of(strings);
        List<String> list1 = stream1.collect(
                () -> new ArrayList<>(),
                (a1, b1) -> a1.add(b1),
                (a2, b2) -> a2.addAll(b2));
        for (String s: list1) {
            System.out.println(s);
        }

        Stream<String> stream2 = Stream.of(strings);
        List<String> list2 = stream2.collect(
                ArrayList::new,
                ArrayList::add,
                ArrayList::addAll);
        for (String s: list2) {
            System.out.println(s);
        }
    }
}
```

The last example in this category, the StreamCollectDemo3 class in Listing 4.11, is a rewrite of StreamCollectDemo1. However, a parallel stream is used to show you how collection really works. The parallel stream is created by calling the parallel method on the initial stream. To show the exact moment each argument is processed, I have also created a custom Supplier by extending ArrayList and overriding its add and addAll methods. The new methods print a message and call a super method.

Listing 4.11: StreamCollectDemo3 class

```
 package app04;
import java.util.ArrayList;
import java.util.Collection;
import java.util.List;
import java.util.concurrent.atomic.AtomicInteger;
import java.util.function.Supplier;
import java.util.stream.Stream;

public class StreamCollectDemo3 {

    public static void main(String[] args) {
        AtomicInteger counter = new AtomicInteger();
        Supplier<List<String>> supplier = () -> {
            System.out.println("supplier called");
            return new ArrayList<String>() {
                int id = counter.getAndIncrement();
                @Override
                public boolean add(String e) {
                    System.out.println(
                            "\"add\" called for " + e
                            + " on ArrayList " + id);
                    return super.add(e);
                }

                @Override
                public boolean addAll(
                        Collection<? extends String> c) {
                    System.out.println("\"addAll\" called"
                        + " on ArrayList " + id);
                    return super.addAll(c);
                }
            };
        };
        String[] strings = { "a", "b", "c", "d" };
        Stream<String> stream1 = Stream.of(strings).parallel();
        List<String> list1 = stream1.collect(
                supplier,
                (a1, b1) -> a1.add(b1),
                (a2, b2) -> a2.addAll(b2));
        for (String s: list1) {
            System.out.println(s);
        }
    }
}
```

If you run this example in a multi-core computer, you will see something similar to this on your console.

```
 supplier called
supplier called
supplier called
supplier called
"add" called for d on ArrayList 0
"add" called for c on ArrayList 2
"add" called for a on ArrayList 1
"add" called for b on ArrayList 3
"addAll" called on ArrayList 2
"addAll" called on ArrayList 1
"addAll" called on ArrayList 1
a
b
c
d
```

You see that the Supplier was called four times since there were four elements in the stream, resulting in four brand new ArrayLists. Then, the add method on each ArrayList was called once for each element. Finally, the content of the four ArrayLists were merged into a single ArrayList and the ArrayList was returned.

Parallel Streams

Most computers today have a multi-core processor. This means, multiple threads can run concurrently in different cores, which makes using parallel streams make sense. However, a parallel stream is more expensive to construct than a sequential stream, which means using a parallel stream does not always make your program run faster.

The ParallelStreamDemo class in Listing 4.12 maps six integers with their fibonacci numbers. The objective of this example is to show how a parallel stream can run much faster in a multi-core processor machine.

Listing 4.12: The ParallelStreamDemo class

```
 package app04;
import java.time.Duration;
import java.time.Instant;
import java.util.Arrays;
import java.util.List;

public class ParallelStreamDemo {

    public static long fibonacci(long i) {
        if (i == 1 || i == 2) {
            return 1;
        }
        return fibonacci(i - 1) + fibonacci(i - 2);
    }

    public static void main(String[] args) {
        List<Integer> numbers = 
                Arrays.asList(10, 20, 30, 40, 41, 42);

        Instant start = Instant.now();
        numbers.parallelStream()
                .map((input) -> fibonacci(input))
                .forEach(System.out::println);
        Instant end = Instant.now();
        System.out.printf(
                "Processing time with parallel stream : %dms\n",
                Duration.between(start, end).toMillis());

        start = Instant.now();
        numbers.stream()
                .map((input) -> fibonacci(input))
                .forEach(System.out::println);
        end = Instant.now();
        System.out.printf(
                "Processing time with sequential stream : %dms\n",
                Duration.between(start, end).toMillis());
    }
}
```

If you run the code, you will see this on your console.

```
 55
6765
832040
102334155
165580141
267914296
Processing time with parallel stream : 953ms
55
6765
832040
102334155
165580141
267914296
Processing time with sequential stream : 1764ms
```

As you can see, you can benefit from a parallel stream. However, for not so resource-intensive tasks, the advantage gets less and less and there is a point where the cost of setting up a parallel stream outweighs the cost of setting up a sequential stream plus the speed-up. For instance, if I replace the numbers with

```
 List<Integer> numbers = 
                Arrays.asList(1, 2, 3, 4, 5, 6);
```

On my machine, the parallel stream actually takes more time to complete this.

So, before you decide to use a parallel stream, do some testing to see if a parallel stream is faster than a sequential stream for a particular task.

Summary

JDK 1.8 introduces a new Stream API that lets you work with streams. A stream is like a pipe. However, instead of transporting oil or water, a stream transfers data from a source to a destination. The main reason for using a stream is for its supports for sequential and parallel aggregate operations. You can easily filter, sort or map the elements of a stream.

Chapter 5

The Date-Time API

Support for dates and times has been available since Java version 1.0, mainly through the java.util.Date class. However, Date was poorly designed. For examples, months in Date start at 1 but days start at 0\. A lot of its methods were deprecated in JDK 1.1 at the same time the java.util.Calendar was brought in to take over some of the functionality in Date. The duo were the main classes for dealing with dates and times, right up to JDK 1.7, even though they had been considered inadequate and not easy to work with, causing many to resort to third party alternatives such as Joda Time (http://joda.org). The new Date and Time API in JDK 1.8 resolves many of the issues in the old API and is similar to the Joda Time API.

This chapter explains the JDK 1.8 Date-Time API.

Overview

The new Date and Time API makes it extremely easy to work with dates and times. The java.time package contains the core classes in the API. In addition, there are four other packages whose members are used less often: java.time.chrono, java.time.format, java.time.temporal and java.time.zone.

Within the java.time package, the Instant class represents a point on the time-line and is often used to time an operation. The LocalDate class models a date without the time component and time zone, suitable, for example, to represent a birthday.

If you need a date as well as a time, then LocalDateTime is for you. For instance, an order shipping date probably requires a time in addition to a date to make the order easier to track. If you need a time but do not care about the date, then you can use LocalTime.

On top of that, if a time zone is important, the Date and Time API provides the ZonedDateTime class. As the name implies, this class models a date-time with a time zone. For instance, you can use this class to calculate the flight time between two airports located in different time zones.

Then there are two classes for measuring an amount of time, Duration and Period. These two are similar except that Duration is time-based and Period is date-based. Duration provides a quantity of time to nanosecond precision. This class is good, for example, to model a flight time as it is often given in the number of hours and minutes. On the other hand, Period is suitable when you are only concerned with the number of days, months or years, such as when calculating your father’s age.

The java.time package also comes with two enums, DayOfWeek and Month. DayOfWeek represents the day of the week, from MONDAY to SUNDAY. The Month enum represents the twelve months of the year, from JANUARY to DECEMBER.

Working with dates and times frequently involves parsing and formatting. The Date and Time API addresses these two issues by providing parse and format methods in all its major classes. In addition, the java.time.format contains a DateTimeFormatter class for formatting dates and times.

The Instant Class

An Instant object represents a point on the time-line. The reference point is the standard Java epoch, which is 1970-01-01T00:00:00Z (January 1, 1970 00:00 GMT). The EPOCH field of the Instant class returns an Instant representing the Java epoch. Instants after the epoch have positive values and instants prior to that have negative values.

The static method now of Instant returns an Instant object that represents the current time:

```
 Instant now = Instant.now();
```

The getEpochSecond method returns the number of seconds that have elapsed since the epoch. The getNano method returns the number of nanoseconds since the beginning of the last second.

A popular use of the Instant class is to time an operation, as demonstrated in Listing 5.1.

Listing 5.1: Using Instant to time an operation

```
 package app05;
import java.time.Duration;
import java.time.Instant;

public class InstantDemo1 {
    public static void main(String[] args) {
        Instant start = Instant.now();
        // do something here
        Instant end = Instant.now();
        System.out.println(Duration.between(start, end).toMillis());
    }
}
```

As shown in Listing 5.1, the Duration class is used to return the difference between two Instants. You will learn more about Duration later in this chapter.

LocalDate

The LocalDate class models a date without a time component. It also has no time zone. Table 5.1 shows some of the more important methods in LocalDate.

| Method | Description |
| now | A static method that returns today’s date. |
| of | A static method that creates a LocalDate from the specified year, month and date. |
| getDayOfMonth, getMonthValue, getYear | Returns the day, month or year part of this LocalDate as an int. |
| getMonth | Returns the month of this LocalDate as a Month enum constant. |
| plusDays, minusDays | Adds or subtracts the given number of days to or from this LocalDate. |
| plusWeeks, minusWeeks | Adds or subtracts the given number of weeks to or from this LocalDate. |
| plusMonths, minusMonths | Adds or subtracts the given number of months to or from this LocalDate. |
| plusYears, minusYears | Adds or subtracts the given number of years to or from this LocalDate. |
| isLeapYear | Checks if the year specified by this LocalDate is a leap year. |
| isAfter, isBefore | Checks if this LocalDate is after or before the given date. |
| lengthOfMonth | Returns the number of days in the month in this LocalDate. |
| withDayOfMonth | Returns a copy of this LocalDate with the day of month set to the given value. |
| withMonth | Returns a copy of this LocalDate with the month set to the given value. |
| withYear | Returns a copy of this LocalDate with the year set to the given value. |

Table 5.1: More important methods of LocalDate

LocalDate offers various methods to create a date. For example, to create a LocalDate that represents today’s date, use the static method now.

```
 LocalDate today = LocalDate.now();
```

To create a LocalDate that represents a specific year, month and day, use its of method, which is also static. For instance, the following snippet creates a LocalDate that represents December 31, 2015.

```
 LocalDate endOfYear = LocalDate.of(2015, 12, 31);
```

The method of has another override that accepts a constant of the java.time.Month enum as the second argument. For example, here is the code to construct the same date using the second method override.

```
 LocalDate endOfYear = LocalDate.of(2015, Month.DECEMBER, 31);
```

There are also methods for obtaining the day, month or year of a LocalDate, such as getDayOfMonth, getMonth, getMonthValue and getYear. They all do not take any argument and either return an int or a Month enum constant. In addition, there is a get method that takes a TemporalField and returns a part of this LocalDate. For example, passing ChronoField.YEAR to get returns the year component of a LocalDate.

```
 int year = localDate.get(ChronoField.YEAR));
```

ChronoField is an enum that implements the TemporalField interface, therefore you can pass a ChronoField constant to get. Both TemporalField and ChronoField are part of the java.time.temporal package. However, not all constants in ChronoField can be passed to get as not all of them are supported. For example, passing ChronoField.SECOND_OF_DAY to get throws an exception. As such, instead of get, it is better to use getMonth, getYear or a similar method to obtain a component of a LocalDate.

In addition, there are methods for copying a LocalDate, such as plusDays, plusYears, minusMonths, and so on. For example, to get a LocalDate that represents tomorrow, you can create a LocalDate that represents today and then calls its plusDays method.

```
 LocalDate tomorrow = LocalDate.now().plusDays(1);
```

To get a LocalDate that represents yesterday, you can use the minusDays method.

```
 LocalDate yesterday = LocalDate.now().minusDays(1);
```

In addition, there are plus and minus methods to get a copy of a LocalDate in a more generic way. Both accept an int and a TemporalUnit. The signatures of these methods are as follows.

```
 public LocalDate plus(long amountToAdd, 
        java.time.temporal.TemporalUnit unit)
public LocalDate minus(long amountToSubtract, 
        java.time.temporal.TemporalUnit unit)
```

As an example, to get a LocalDate that represents a past date exactly two decades ago from today, you can use this code.

```
 LocalDate pastDate = LocalDate.now().minus(2, ChronoUnit.DECADES);
```

ChronoUnit is an enum that implements TemporalUnit, so you can pass a ChronoUnit constant to the plus or minus method.

A LocalDate is immutable and therefore cannot be changed. Any method that returns a LocalDate returns a new instance of LocalDate.

Listing 5.2 shows an example of LocalDate.

Listing 5.2: LocalDate example

```
 package app05;
import java.time.LocalDate;
import java.time.temporal.ChronoField;
import java.time.temporal.ChronoUnit;

public class LocalDateDemo1 {
    public static void main(String[] args) {
        LocalDate today = LocalDate.now();
        LocalDate tomorrow = today.plusDays(1);
        LocalDate oneDecadeAgo = today.minus(1, 
                ChronoUnit.DECADES);
        System.out.println("Day of month: " 
                + today.getDayOfMonth());
        System.out.println("Today is " + today);
        System.out.println("Tomorrow is " + tomorrow);
        System.out.println("A decade ago was " + oneDecadeAgo);
        System.out.println("Year : " 
                + today.get(ChronoField.YEAR));
        System.out.println("Day of year:" + today.getDayOfYear());    
    }
}
```

Period

The Period class models a date-based amount of time, such as five days, a week or three years. Some of its more important methods are presented in Table 5.2.

| Method | Description |
| between | Creates a Period between two LocalDates. |
| ofDays, ofWeeks, ofMonths, ofYears | Creates a Period representing the given number of days/weeks/months/years. |
| of | Creates a Period from the given numbers of years, months and days. |
| getDays, getMonths, getYears | Returns the number of days/months/years of this period as an int. |
| isNegative | Returns true if any of the three components of this Period is negative. Returns false otherwise. |
| isZero | Returns true if all of the three components of this Period are zero. Otherwise, returns false. |
| plusDays, minusDays | Adds or subtracts the given number of days to or from this Period. |
| plusMonths, minusMonths | Adds or subtracts the given number of months to or from this Period. |
| plusYears, minusYears | Adds or subtracts the given number of years to or from this Period. |
| withDays | Returns a copy of this Period with the specified number of days. |
| withMonths | Returns a copy of this Period with the specified number of months. |
| withYears | Returns a copy of this Period with the specified number of years. |

Table 5.2 More important methods of Period

Creating a Period is easy, thanks to the static factory methods between, of, and ofDays/ofWeeks/ofMonths/ofYears. For example, here is how you create a Period representing two weeks.

```
 Period twoWeeks = Period.ofWeeks(2);
```

To create a Period representing one year, two months and three days, use the of method.

```
 Period p = Period.of(1, 2, 3);
```

To obtain the year/month/day component of a Period, call its getYears/getMonths/getDays method. For instance, the howManyDays variable in the following code snippet will have a value of 14.

```
 Period twoWeeks = Period.ofWeeks(2);
int howManyDays = twoWeeks.getDays();
```

Finally, you can create a copy of a Period using the plusXXX or minusXXX methods as well as one of the withXXX methods. A Period is immutable so these methods return new Period instances.

As an example, the code in Listing 5.3 shows an age calculator that calculates a person’s age. It creates a Period from two LocalDates and calls its getDays, getMonths, and getYears methods.

Listing 5.3: Using Period

```
 package app05;
import java.time.LocalDate;
import java.time.Period;

public class PeriodDemo1 {
    public static void main(String[] args) {
        LocalDate dateA = LocalDate.of(1978, 8, 26);
        LocalDate dateB = LocalDate.of(1988, 9, 28);
        Period period = Period.between(dateA, dateB);
        System.out.printf("Between %s and %s"
                + " there are %d years, %d months"
                + " and %d days%n", dateA, dateB, 
                period.getYears(), 
                period.getMonths(),
                period.getDays());
    }
}
```

When run, the PeriodDemo1 class in Listing 5.3 will print this string.

```
 Between 1978-08-26 and 1988-09-28 there are 10 years, 1 months and 2 
days
```

LocalDateTime

The LocalDateTime class models a date-time without a time zone. Table 5.3 shows some of the more important methods in LocalDateTime. The methods are similar to those of LocalDate plus some other methods for modifying the time component, such as plusHours, plusMinutes and plusSeconds, that are not available in LocalDate.

| Method | Description |
| now | A static method that returns the current date and time. |
| of | A static method that creates a LocalDateTime from the specified year, month, date, hour, minute, second and millisecond. |
| getYear, getMonthValue, getDayOfMonth, getHour, getMinute, getSecond | Returns the year, month, day, hour, minute or second part of this LocalDateTime as an int. |
| plusDays, minusDays | Adds or subtracts the given number of days to or from the current LocalDateTime. |
| plusWeeks, minusWeeks | Adds or subtracts the given number of weeks to or from the current LocalDateTime. |
| plusMonths, minusMonths | Adds or subtracts the given number of months to or from the current LocalDateTime. |
| plusYears, minusYears | Adds or subtracts the given number of years to or from the current LocalDateTime. |
| plusHours, minusHours | Adds or subtracts the given number of hours to or from the current LocalDateTime. |
| plusMinutes, minusMinutes | Adds or subtracts the given number of minutes to or from the current LocalDateTime. |
| plusSeconds, minusSeconds | Add or subtracts the given number of seconds to or from the current LocalDateTime. |
| IsAfter, isBefore | Checks if this LocalDateTime is after or before the given date-time. |
| withDayOfMonth | Returns a copy of this LocalDateTime with the day of month set to the given value. |
| withMonth, withYear | Returns a copy of this LocalDateTime with the month or year set to the given value. |
| withHour, withMinute, withSecond | Returns a copy of this LocalDateTime with the hour/minute/second set to the given value. |

Table 5.3: More important methods of LocalDateTime

LocalDateTime offers various static methods to create a date-time. The method now comes with three overrides and return the current date-time. The no-argument override is the easiest to use:

```
 LocalDateTime now = LocalDateTime.now();
```

To create a LocalDateTime with a specific date and time, use the of method. This method has a number of overrides and allows you to pass the individual component of a date-time or a LocalDate and a LocalTime. Here are the signatures of some of the of methods.

```
 public static LocalDateTime of(int year, int month, int dayOfMonth, 
        int hour, int minute)
public static LocalDateTime of(int year, int month, int dayOfMonth,
        int hour, int minute)
public static LocalDateTime of(int year, Month month, 
        int dayOfMonth, int hour, int minute)
public static LocalDateTime of(int year, Month month, 
        int dayOfMonth, int hour, int minute)
public static LocalDateTime of(LocalDate date, LocalTime time)
```

For instance, the following snippet creates a LocalDateTime that represents December 31, 2015 at eight o’clock in the morning.

```
 LocalDateTime endOfYear = LocalDateTime.of(2015, 12, 31, 8, 0);
```

You can create a copy of a LocalDateTime using the plusXXX or minusXXX method. For example, this code creates a LocalDateTime that represents the same time tomorrow.

```
 LocalDateTime now = LocalDateTime.now();
LocalDateTime sameTimeTomorrow = now.plusHours(24);
```

Time Zones

The Internet Assigned Numbers Authority (IANA) maintains a database of time zones that you can download from this web page:

```
 http://www.iana.org/time-zones
```

For easy viewing, however, you can just visit this Wikipedia page:

```
 http://en.wikipedia.org/wiki/List_of_tz_database_time_zones
```

The Java Date and Time API caters for time zones too. The abstract class ZoneId (in the java.time package) represents a zone identifier. It has a static method called getAvailableZoneIds that returns all zone identifiers. Listing 5.4 shows how you can print a sorted list of all time zones using this method.

Listing 5.4: Listing all zone identifiers

```
 package app05;
import java.time.ZoneId;
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Set;

public class TimeZoneDemo1 {
    public static void main(String[] args) {
        Set<String> allZoneIds = ZoneId.getAvailableZoneIds();
        List<String> zoneList = new ArrayList<>(allZoneIds);

        Collections.sort(zoneList);       
        for (String zoneId : zoneList) {
            System.out.println(zoneId);
        }
        // alternatively, you can use this line of code to 
        // print a sorted list of zone ids
        // ZoneId.getAvailableZoneIds().stream().sorted().
        //        forEach(System.out::println);
    }
}
```

getAvailableZoneIds returns a Set of Strings. You can sort the Set using Collections.sort() or more elegantly by calling its stream method. You could have written this code to sort the zone identifiers.

```
 ZoneId.getAvailableZoneIds().stream().sorted()
        .forEach(System.out::println);
```

getAvailableZoneIds returns a Set of 586 zone identifiers. Here are some of the zone identifiers from the code above.

```
 Africa/Cairo
Africa/Johannesburg
America/Chicago
America/Los_Angeles
America/Mexico_City
America/New_York
America/Toronto
Antarctica/South_Pole
Asia/Hong_Kong
Asia/Shanghai
Asia/Tokyo
Australia/Melbourne
Australia/Sydney
Canada/Atlantic
Europe/Amsterdam
Europe/London
Europe/Paris
US/Central
US/Eastern
US/Pacific
```

ZonedDateTime

The ZonedDateTime class models a date-time with a time zone. For example, the following is a zoned date-time:

```
 2015-12-31T10:59:59+01:00 Europe/Paris
```

A ZonedDateTime is always immutable and the time component is stored to nanosecond precision.

Table 5.4 shows the more important methods in ZonedDateTIme.

| Method | Description |
| now | A static method that returns the current date and time of the system’s default zone. |
| of | A static method that creates a ZonedDateTime from the specified date-time and zone identifier. |
| getYear, getMonthValue, getDayOfMonth, getHour, getMinute, getSecond, getNano | Returns the year, month, day, hour, minute, second or nanosecond part of this ZoneDateTime as an int. |
| plusDays, minusDays | Adds or subtracts the given number of days to or from the current ZonedDateTime. |
| plusWeeks, minusWeeks | Adds or subtracts the given number of weeks to or from the current ZonedDateTime. |
| plusMonths, minusMonths | Adds or subtracts the given number of months to or from the current ZonedDateTime. |
| plusYears, minusYears | Adds or subtracts the given number of years to or from the current ZonedDateTime. |
| plusHours, minusHours | Adds or subtracts the given number of hours to or from the current ZonedDateTime. |
| plusMinutes, minusMinutes | Adds or subtracts the given number of minutes to or from the current ZonedDateTime. |
| plusSeconds, minusSeconds | Add or subtracts the given number of seconds to or from the current ZonedDateTime. |
| IsAfter, isBefore | Checks if this ZonedDateTime is after or before the given zoned date-time. |
| getZone | Returns the zone ID of this ZonedDateTime. |
| withYear, withMonth, withDayOfMonth | Returns a copy of this ZonedDateTime with the year/month/day of month set to the given value. |
| withHour, withMinute, withSecond | Returns a copy of this ZonedDateTime with the hour/minute/second set to the given value. |
| withNano | Returns a copy of this ZonedDateTime with the nanosecond set to the given value. |

Table 5.4: More important methods of ZonedDateTime

Like LocalDateTime, the ZonedDateTime class offers the static methods now and of to construct a ZonedDateTime. now creates a ZonedDateTime representing the date and time of execution. The no-argument override of now creates a ZonedDateTime with the computer’s default time zone.

```
 ZonedDateTime now = ZonedDateTime.now();
```

Another override of now lets you pass a zone identifier:

```
 ZonedDateTime parisTime =
        ZonedDateTime.now(ZoneId.of("Europe/Paris"));
```

The method of also comes with several overrides. In all cases, you need to pass a zone identifier. The first override allows you to pass each component of a zoned date-time, from the year to the nanosecond.

```
 public static ZonedDateTime of(int year, int month, int dayOfMonth, 
        int hour, int minute, int second, int nanosecond, 
        ZoneId zone)
```

The second override of of takes a LocalDate, a LocalTime and a ZoneId:

```
 public static ZonedDateTime of(LocalDate date, LocalTime time,
        ZoneId zone)
```

The last override of of takes a LocalDateTime and a ZoneId.

```
 public static ZonedDateTime of(LocalDateTime datetime, ZoneId zone)
```

Like LocalDate and LocalDateTime, ZonedDateTime offers methods to create a copy of an instance using the plusXXX, minusXXX and withXXX methods.

For instance, these lines of code creates a ZonedDateTime with the default time zone and calls its minusDays method to create the same ZonedDateTime three days earlier.

```
 ZonedDateTime now = ZonedDateTime.now();
ZonedDateTime threeDaysEarlier = now.minusDays(3);
```

Duration

The Duration class models a time-based duration. It is similar to Period except that a Duration has a time component to nanosecond precision and takes into account the time zones between ZonedDateTimes. Table 5.5 shows the more important methods in Duration.

| Method | Description |
| between | Creates a Duration between two temporal objects, such as between two LocalDateTimes or two LocalZonedDateTimes. |
| ofYears, ofMonths, ofWeeks, ofDays, ofHours, ofMinutes, ofSeconds, ofNano | Creates a Duration representing the given number of years/months/weeks/days/hours/minutes/seconds/nanoseconds. |
| of | Creates a Duration from the given number of temporal units. |
| toDays, toHours, toMinutes | Returns the number of days/hours/minutes of this Duration as an int. |
| isNegative | Returns true if this Duration is negative. Returns false otherwise. |
| isZero | Returns true if this Duration is zero length. Otherwise, returns false. |
| plusDays, minusDays | Adds or subtracts the given number of days to or from this Duration. |
| plusMonths, minusMonths | Adds or subtracts the given number of months to or from this Duration. |
| plusYears, minusYears | Adds or subtracts the given number of years to or from this Duration. |
| withSeconds | Returns a copy of this Duration with the specified number of seconds. |

Table 5.5: More important methods in Duration

You can create a Duration by calling its between or of static method. The code in Listing 5.5 creates a Duration between two LocalDateTimes, between January 26, 2015 11:10 and January 26, 2015 12:40.

Listing 5.5: Creating a Duration between two LocalDateTimes

```
 package app05;
import java.time.Duration;
import java.time.LocalDateTime;

public class DurationDemo1 {

    public static void main(String[] args) {
        LocalDateTime dateTimeA = LocalDateTime
                .of(2015, 1, 26, 8, 10, 0, 0);
        LocalDateTime dateTimeB = LocalDateTime
                .of(2015, 1, 26, 11, 40, 0, 0);
        Duration duration = Duration.between(
                dateTimeA, dateTimeB);
        System.out.printf("There are %d hours and %d minutes.%n",
                duration.toHours(), 
                duration.toMinutes() % 60);
    }
}
```

The result of running the DurationDemo1 class is this.

```
 There are 3 hours and 30 minutes.
```

The code in Listing 5.6 creates a Duration between two ZoneDateTimes, with the same date-time but different timezones.

Listing 5.6: Creating a Duration between two ZonedDateTimes

```
 package app05;
import java.time.Duration;
import java.time.LocalDateTime;
import java.time.Month;
import java.time.ZoneId;
import java.time.ZonedDateTime;

public class DurationDemo2 {

    public static void main(String[] args) {
        ZonedDateTime zdt1 = ZonedDateTime.of(
                LocalDateTime.of(2015, Month.JANUARY, 1, 
                        8, 0),
                ZoneId.of("America/Denver"));
        ZonedDateTime zdt2 = ZonedDateTime.of(
                LocalDateTime.of(2015, Month.JANUARY, 1, 
                        8, 0), 
                ZoneId.of("America/Toronto"));
        Duration duration = Duration.between(zdt1, zdt2);
        System.out.printf("There are %d hours and %d minutes.%n",
                duration.toHours(), 
                duration.toMinutes() % 60);
    }
}
```

Running the DurationDemo2 class prints this on the console.

```
 There are -2 hours and 0 minutes.
```

This is expected, because there are two hours difference between the time zones America/Denver and America/Toronto.

As a more complex example, the code in Listing 5.7 shows a bus travel time calculator. It has one method, calculateTravelTime, which takes a departure ZonedDateTime and an arrival ZonedDateTime. The code calls the calculateTravelTime method twice. Both times the bus departs from Denver, Colorado at 8 in the morning Denver time and arrives in Toronto at 8 in the next morning Toronto time. The first time the bus leaves on March 8, 2014 and the second time it leaves on March 18, 2014.

What are the travel time in both occasions?

Listing 5.7: Travel time calculator

```
 package app05;
import java.time.Duration;
import java.time.LocalDateTime;
import java.time.Month;
import java.time.ZoneId;
import java.time.ZonedDateTime;

public class TravelTimeCalculator {

    public Duration calculateTravelTime(
            ZonedDateTime departure, ZonedDateTime arrival) {
        return Duration.between(departure, arrival);
    }

    public static void main(String[] args) {
        TravelTimeCalculator calculator = 
                new TravelTimeCalculator();
        ZonedDateTime departure1 = ZonedDateTime.of(
                LocalDateTime.of(2014, Month.MARCH, 8, 
                        8, 0), 
                ZoneId.of("America/Denver"));
        ZonedDateTime arrival1 = ZonedDateTime.of(
                LocalDateTime.of(2014, Month.MARCH, 9, 
                        8, 0), 
                ZoneId.of("America/Toronto"));
        Duration travelTime1 = calculator
                .calculateTravelTime(departure1, arrival1);
        System.out.println("Travel time 1: " 
                + travelTime1.toHours() + " hours");

        ZonedDateTime departure2 = ZonedDateTime.of(
                LocalDateTime.of(2014, Month.MARCH, 18, 
                        8, 0), 
                ZoneId.of("America/Denver"));
        ZonedDateTime arrival2 = ZonedDateTime.of(
                LocalDateTime.of(2014, Month.MARCH, 19, 
                        8, 0), 
                ZoneId.of("America/Toronto"));
        Duration travelTime2 = calculator
                .calculateTravelTime(departure2, arrival2);
        System.out.println("Travel time 2: " 
                + travelTime2.toHours() + " hours");
    }
}
```

The result is this.

```
 Travel time 1: 21 hours
Travel time 2: 22 hours
```

Why the difference? Because in 2014 daylight saving time began on Sunday, March 9 at 2AM. As such, you ‘lost’ one hour between March 8, 2014 and March 9, 2014.

Formatting A Date-Time

You use a java.time.format.DateTimeFormatter to format a local or zoned date-time. The LocalDate, LocalDateTime, LocalTime and ZoneDateTime classes offer a format method that has the following signature.

```
 public java.lang.String format(java.time.format.DateTimeFormatter 
        formatter)
```

It is clear that to format a date or time, you must first create an instance of DateTimeFormatter.

The code in Listing 5.8 formats the current date using two formatters.

Listing 5.8: Formatting dates

```
 package app05;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.time.format.FormatStyle;

public class DateTimeFormatterDemo1 {
    public static void main(String[] args) {
        DateTimeFormatter formatter1 = DateTimeFormatter
                .ofLocalizedDateTime(FormatStyle.MEDIUM);
        LocalDateTime example = LocalDateTime.of(
                2000, 3, 19, 10, 56, 59);
        System.out.println("Format 1: " + example
                .format(formatter1));        
        DateTimeFormatter formatter2 = DateTimeFormatter
                .ofPattern("MMMM dd, yyyy HH:mm:ss");
        System.out.println("Format 2: " + 
                example.format(formatter2));
    }
}
```

The results are as follows (the first result depends on your locale).

```
 Format 1: 19-Mar-2000 10:56:59 AM
Format 2: March 19, 2000 10:56:59
```

Parsing A Date-Time

There are two parse methods in many of the classes in the Java Date and Time API. The first requires a formatter, the second does not. The one that does not will parse the date-time based on the default pattern. To use your own pattern, use a DateTimeFormatter. The parse methods will throw a DateTimeParseException if the string passed cannot be parsed.

Listing 5.9 contains an age calculator to demonstrate date parsing.

Listing 5.9: An age calculator

```
 package app05;
import java.time.LocalDate;
import java.time.Period;
import java.time.format.DateTimeFormatter;
import java.time.format.DateTimeParseException;
import java.util.Scanner;

public class AgeCalculator {
    DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-M-d");
    public Period calculateAge(LocalDate birthday) {
        LocalDate today = LocalDate.now();
        return Period.between(birthday, today);
    }

    public LocalDate getBirthday() {
        Scanner scanner = new Scanner(System.in);
        LocalDate birthday;
        while (true) {
            System.out.println("Please enter your birthday "
                    + "in yyyy-MM-dd format (e.g. 1980-9-28): ");
            String input = scanner.nextLine();
            try {
                birthday = LocalDate.parse(input, formatter);
                return birthday;
            } catch(DateTimeParseException e) {
                System.out.println("Error! Please try again");
            }
        }
    }

    public static void main(String[] args) {
        AgeCalculator ageCalculator = new AgeCalculator();
        LocalDate birthday = ageCalculator.getBirthday();
        Period age = ageCalculator.calculateAge(birthday);
        System.out.printf("Today you are %d years, %d months"
                + " and %d days old%n",
                age.getYears(), age.getMonths(), age.getDays());
    }
}
```

The AgeCalculator class has two methods, getBirthday and calculateAge. The getBirthday method employs a Scanner to read user input and parses the input into a LocalDate using the class level DateTimeFormatter. The getBirthday method keeps begging for a date until the user types in a date in the correct format, in which case the method returns. The calculateAge method takes a birthday and creates a Period between the birthday and today.

If you run this example, you will see this on your console.

```
 Please enter your birthday in yyyy-MM-dd format (e.g. 1980-9-28):
```

If you enter a date in the correct format, the program will print the calculated age, such as the following.

```
 Today you are 79 years, 0 months and 15 days old
```

Summary

Java 8 brings with it a new Date-Time API to replace the old API that centered around the java.util.Date class. In this chapter you have learned to use the core classes in the new API, such as Instant, LocalDate, LocalDateTime, ZonedDateTime, Period and Duration, as well as learned to format and parse a date-time.

Chapter 6

JavaFX 8

JavaFX is a technology for creating rich client applications that can run on the desktop and in the browser. It is similar to Swing but with a better and simpler object model and will replace Swing and AWT.

This chapter provides an introduction to JavaFX and Chapter 7, “JavaFX with FXML” explains how to separate the presentation layer and business logic using a special markup language called FXML.

Overview

JavaFX is a technology for building rich applications that can be deployed as desktop applications as well as run in the browser as applets. JavaFX will eventually replace Swing, and to ease transition from Swing to JavaFX, there is support for interoperability between the two. You can easily use Swing components from within your JavaFX application.

As a desktop technology, JavaFX is an excellent choice for any Java developer or anyone aspiring to be a GUI developer, thanks to its features and ease of use. In addition, JavaFX enjoys the full support from Oracle and the Java community at large, so getting help is easy.

As a technology for building in-browser applications, JavaFX must compete with other technologies, notably HTML 5, Flash, and Microsoft Silverlight. HTML 5 has the advantage of being natively supported by modern browsers, which means everything built in HTML 5 is guaranteed to work seamlessly in those browsers, despite the fact that HTML 5 is not as feature-rich as JavaFX, Flash or Silverlight. JavaFX, Flash and Silverlight applications require plug-ins to run in a browser and browsers do not necessarily ship with these plug-ins so JavaFX applet users, for example, may have to install a Java browser plug-in before being able to run a JavaFX applet. Installing a plug-in may or may not discourage people from liking JavaFX applets. You can judge yourself whether it is easy enough to install the plug-in by reading the instructions on this web page.

```
 http://java.com/en/download/help/enable_browser.xml 
```

Setting up

JavaFX started as an independent technology that had to be downloaded separately from the JDK. Starting from JDK 1.7 update 6 (JDK7u6), however, the JDK ships with the latest version of JavaFX. JDK 1.7 includes JavaFX 2.2 and Java 8 comes with JavaFX 8, the release after version 2.2.

At the time of writing, the easiest way to develop JavaFX applications is by using NetBeans 8 or later. Simply click File → New Project → JavaFX to create a new JavaFX project.

If you are not using NetBeans, you need to include the jfxrt.jar file in your class path when compiling and running your application. In JDK 1.8, the file is located in $JAVA_HOME/jre/lib/ext/ where $JAVA_HOME is the installation directory of your JDK. In JDK 1.7 update 6 and later, the file can be found in $JAVA_HOME/jre/lib/.

If you’re using Eclipse, right-click the project icon and click on Properties. On the left hand side of the window that appears, click Java Build Path, then select the Libraries tab on the right. Next, click the Add External JARs button and navigate to the location of the jar file and select it.

There is an Eclipse plug-in called e(fx)clipse that you can add to Eclipse 4.4 and later to help you develop JavaFX applications. The instruction can be found here.

```
 http://www.eclipse.org/efxclipse/install.html
```

You can also compile and run a JavaFX application from outside an IDE. To compile a JavaFX class named MyFXApp in package mypackage using the javac program on the command line, go to the source directory of your project and type

```
 javac -cp ${JAVA_HOME}/jre/lib/ext/jfxrt.jar mypackage/MyFXApp.java
```

replacing ${JAVA_HOME} with the path to Java installation. For example, if your Java installation is in /opt/jdk1.8.0_25, use this command.

```
 javac -cp /opt/jdk1.8.0_25/jre/lib/ext/jfxrt.jar mypackage/MyFXApp.java
```

To run the application (on Linux and Mac OS X), include the current directory in the class path:

```
 java -cp /opt/jdk1.8.0_25/jre/lib/ext/jfxrt.jar:. mypackage.MyFXApp 
```

On Windows, replace the colon with a semicolon.

```
 java -cp /opt/jdk1.8.0_25/jre/lib/ext/jfxrt.jar;. mypackage.MyFXApp
```

Your First JavaFX Application

This section shows how easy it is to develop a JavaFX application. The example consists of only one class, which is called FirstApp and shown in Listing 6.1.

Listing 6.1: The FirstApp class

```
 package app06; 
import javafx.application.Application; 
import javafx.scene.Scene; 
import javafx.scene.control.Label; 
import javafx.scene.layout.StackPane;
import javafx.stage.Stage; 

public class FirstApp extends Application { 

    @Override 
    public void start(Stage stage) { 
        Label label = new Label("Welcome"); 
        StackPane root = new StackPane(); 
        root.getChildren().add(label); 

        Scene scene = new Scene(root, 400, 100);

        stage.setTitle("First FX"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
}
```

Run it just as you would any Java application and you’ll see a window like the one in Figure 6.1.

![](Images/0601.png)

Figure 6.1: A simple JavaFX application (on Ubuntu)

The JavaFX API is explained in the next section.

Application, Stage, and Scene

The JavaFX API takes the form of the types in the javafx package and its subpackages. One of its most important types is the javafx.application.Application class, which represents a JavaFX application. A JavaFX application consists of one or more windows and other resources.

In JavaFX a window is represented by the javafx.stage.Window class, which has two subclasses, Stage and PopupWindow. A Stage (an instance of javafx.stage.Stage) is a top-level container to which you add a second-level container called Scene, which in turn contains the UI components for that window. The primary Stage is created for you by the JavaFX runtime, but you can create additional Stages and PopupWindows if needed.

The javafx.scene.Scene class is a container for UI components. In JavaFX a UI component is called a graph scene node (or a node, for short). To create a Scene you must pass a parent node (an instance of javafx.scene.Parent) responsible for laying out child UI components.

Now let’s take a look at the three main classes, Application, Stage and Scene. Details on other JavaFX types can be viewed here.

```
 http://docs.oracle.com/javase/8/javafx/api/toc.htm
```

The Application Class

You extend the Application class to create a JavaFX application. To run it as a stand-alone program, you call one of its launch methods.

```
 public static void launch(java.lang.String... args)
public static void launch(java.lang.Class<? extends Application> 
        appClass, java.lang.String... args)
```

Any parameter you pass to the launch methods can be retrieved from inside an Application using the getParameters method.

```
 public final Application.Parameters getParameters() 
```

The Application class has the following life-cycle methods that will be called when an instance is launched.

```
 public void init() throws java.lang.Exception 
```

This method is called after the application is constructed. It should be overriden if the application needs to perform initialization.

```
 public abstract void start(Stage stage) throws 
        java.lang.Exception 
```

This method is called after init() returns and you should construct your UI in this method implementation. The JavaFX runtime creates a Stage object that is passed as a method argument.

```
 public void stop() throws java.lang.Exception
```

This method is called when the application should stop. You should release any held resources here.

Of the life-cycle methods, only start must be overriden.

The Stage Class

The Stage class represents a top-level container for your UI components. An instance is created and passed to you when the application’s start method is called. The Stage that the application created is the primary window of the application. You can create your own Stage if necessary.

A Stage, just like any other UI window, can have a title that you can populate using the Stage class’s title property. On top of that, you can add a Scene to a Stage by calling the setScene method on the Stage. Then, to show a Stage you call its show method.

The Scene Class

A Scene is a container that can be added to a Stage. A Scene must contain a parent node that is the root of all components added to the Scene. A parent node is represented by the javafx.scene.Parent class. The simplest constructor in Scene takes one argument, an instance of Parent.

```
 public Scene(Parent root)
```

There are other constructors that let you specify the dimension of the Scene as well as its fill.

```
 public Scene(Parent root, double width, double height)
public Scene(Parent root, javafx.scene.paint.Paint fill)
public Scene(Parent root, double width, double height, 
        javafx.scene.paint.Paint fill)
```

UI Components

Built-in UI components make writing JavaFX applications so easy and fun. A UI component is called a scene graph node (or simply a node) in the parlance of JavaFX developers. The javafx.scene.Node class is the base class for all nodes. It has five subclasses that distinguish the types of nodes in JavaFX:

*   Canvas. A rectangular area you can draw on.
*   Parent. A container to which you can add other UI components.
*   Shape. Represents a shape, such as a rectangle, a circle, or an arc.
*   ImageView. A view area for showing an image.
*   MediaView. Provides a view of media being played by a MediaPlayer.

Canvas, ImageView, and MediaView do not have subclasses. Parent and Shape do.

The Parent class has the following subclasses.

*   Control. This class is a base class for all UI controls, from simple controls like Button and Label to more complex ones such as ProgressBar, TreeView, and TableView.
*   Region. Represents a screen area that can contain other nodes and be styled using CSS. Subclasses include Chart and various Panes, including BorderPane, StackPane, FlowPane, GridPane, HBox, VBox, AnchorPane, etc.
*   Group. An area that contains an ObservableList of children and is the best Parent for working with Shape objects.
*   WebView. A WebView is used to manage a WebEngine and display its content. As the name implies, a WebEngine can load web pages, create document models, and run JavaScript on pages.

The Control and Region classes are discussed further in the next sections.

The javafx.scene.shape.Shape class is a base class for various geometric shapes, including Arc, Circle, Ellipse, Line, Path, and Rectangle.

Controls

UI controls are nodes that the user can interact with. The javafx.scene.control.Control class is the base class for all UI controls. Figure 6.2 shows direct and indirect subclasses of Control.

![](Images/0602.png)

Figure 6.2: Control implementations

Figure 6.3 shows a Scene that contains some JavaFX controls and Listing 6.2 presents the code that produces the Scene.

![](Images/0603.png)

Figure 6.3: JavaFX UI Controls

Listing 6.2: The ControlsDemo class

```
 package app06;
import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.Button; 
import javafx.scene.control.CheckBox; 
import javafx.scene.control.ChoiceBox; 
import javafx.scene.control.ColorPicker; 
import javafx.scene.control.ComboBox; 
import javafx.scene.control.Hyperlink; 
import javafx.scene.control.Label; 
import javafx.scene.control.ListView; 
import javafx.scene.control.MenuButton; 
import javafx.scene.control.MenuItem; 
import javafx.scene.control.PasswordField; 
import javafx.scene.control.RadioButton; 
import javafx.scene.control.ScrollBar; 
import javafx.scene.control.Separator; 
import javafx.scene.control.Slider; 
import javafx.scene.control.TextArea; 
import javafx.scene.control.TextField; 
import javafx.scene.control.ToggleGroup; 
import javafx.scene.layout.ColumnConstraints; 
import javafx.scene.layout.GridPane; 
import javafx.scene.paint.Color; 
import javafx.stage.Stage; 

public class ControlsDemo extends Application { 

    @Override 
    public void start(Stage stage) { 
        GridPane grid = new GridPane(); 
        grid.setHgap(15); 
        grid.setVgap(25); 
        ColumnConstraints constraint = new ColumnConstraints(); 
        constraint.setPercentWidth(25); 
        grid.getColumnConstraints().addAll(constraint, 
                constraint, constraint, constraint); 
        grid.setPadding(new Insets(10)); 

        grid.add(new Label("Label"), 0, 0); 
        grid.add(new Button("Button"), 1, 0); 
        grid.add(new CheckBox("CheckBox"), 2, 0); 

        ChoiceBox<String> choiceBox = new ChoiceBox<String>(); 

        choiceBox.getItems().addAll("ChoiceBox 1", "ChoiceBox 2"); 
        choiceBox.setValue("ChoiceBox 1"); 
        grid.add(choiceBox, 3, 0); 

        grid.add(new ColorPicker(Color.GREEN), 0, 1); 

        ComboBox<String> comboBox = new ComboBox<String>(); 
        comboBox.getItems().addAll("Combo 1", "Combo 2"); 
        comboBox.setValue("Combo 1"); 
        grid.add(comboBox, 1, 1); 

        grid.add(new Hyperlink("Hyperlink"), 2, 1); 

        ListView<String> listView = new ListView<String>(); 
        listView.getItems().addAll("List Item 1", 
                "List Item 2", "List Item 3"); 
        grid.add(listView, 3, 1); 

        MenuButton menuButton = new MenuButton("Menu"); 
        menuButton.getItems().addAll(new MenuItem("Menu 1"), 
                new MenuItem("Menu 1")); 
        grid.add(menuButton, 0, 2); 

        grid.add(new TextField("TextField"), 1, 2); 

        PasswordField passwordField = new PasswordField(); 
        passwordField.setText("Password"); 
        grid.add(passwordField, 2, 2); 

        grid.add(new ScrollBar(), 3, 2); 

        ToggleGroup group = new ToggleGroup(); 
        RadioButton radioButton1 = new RadioButton("Radio 1"); 
        radioButton1.setToggleGroup(group); 
        radioButton1.setSelected(true); 
        RadioButton radioButton2 = new RadioButton("Radio 2"); 
        radioButton2.setToggleGroup(group); 
        grid.add(radioButton1, 0, 3); 
        grid.add(radioButton2, 1, 3); 

        TextArea textArea = new TextArea("TextArea"); 
        textArea.setMinHeight(60.00); 
        grid.add(textArea, 2, 3); 

        grid.add(new Separator(), 3, 3); 

        Slider slider2 = new Slider(0, 100, 30); 
        slider2.setShowTickMarks(true); 
        slider2.setShowTickLabels(true); 
        grid.add(slider2, 0, 4, 4, 1); 

        Scene scene = new Scene(grid, 600, 320); 
        scene.setFill(Color.BEIGE); 

        stage.setTitle("JavaFX Controls"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
}
```

Regions

A Region is a screen area that can contain other nodes and be styled using CSS. All Regions are subclasses of the javafx.scene.layout.Region class. There are three direct descendents of Region: Axis, Chart, and Pane. An Axis is used to render an axis on a chart area and a Chart models a chart. A Pane is a region that is normally used for laying out UI controls.

This section only discusses Pane.

Subclasses of Pane include BorderPane, StackPane, GridPane, FlowPane, AnchorPane, HBox, and VBox.

BorderPane divides a Parent into five areas, top, bottom, left, right, and center. The diagram in Figure 6.4 shows the different areas in a BorderPane.

![](Images/0604.png)

Figure 6.4: The five areas of BorderPane

HBox lays out its children in a single horizontal row and VBox does it in a single vertical row. GridPane, on the other hand, arranges children in a grid and is often used to layout the controls of a form.

The BorderPaneDemo class Listing 6.3 uses BorderPane to lay out controls. Only the top, left and center areas are used. The top section contains an HBox with two buttons and the left section contains a Label and a ColorPicker. The center section has an ImageView with an Image.

Listing 6.3: The BorderPaneDemo class

```
 package app06;
import javafx.application.Application; 
import javafx.geometry.Insets; 
import javafx.scene.Scene; 
import javafx.scene.control.Button; 
import javafx.scene.control.ColorPicker; 
import javafx.scene.control.Label; 
import javafx.scene.image.ImageView; 
import javafx.scene.layout.BorderPane; 
import javafx.scene.layout.HBox; 
import javafx.scene.layout.VBox; 
import javafx.stage.Stage; 

public class BorderPaneDemo extends Application { 

    @Override 
    public void start(Stage stage) { 
        Button okButton = new Button("OK"); 
        okButton.setDefaultButton(true); 

        Button cancelButton = new Button("Cancel"); 
        HBox hBox = new HBox(); 
        hBox.setPadding(new Insets(15, 12, 15, 12)); 
        hBox.setSpacing(10); 
        hBox.setStyle("-fx-background-color: #886699;"); 
        hBox.getChildren().addAll(okButton, cancelButton); 
        BorderPane root = new BorderPane(); 
        root.setTop(hBox); 

        ImageView imageView = new ImageView("image/1.jpg"); 
        root.setCenter(imageView); 

        VBox vBox = new VBox(); 
        vBox.setStyle("-fx-background-color: " + 
        		"#ddeeff;-fx-padding:10px"); 
        vBox.getChildren().addAll( 
                new Label("Select Color:"), 
                new ColorPicker()); 
        root.setLeft(vBox); 

        root.setStyle("-fx-background-color: #6680e6;"); 
        Scene scene = new Scene(root, 740, 530); 

        stage.setTitle("HBox, VBox, BorderPane Demo"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
} 
```

Figure 6.5 shows the BorderPaneDemo application on Windows.

![](Images/0605.png)

Figure 6.5: BorderPane demo

Event Handling

JavaFX is event-driven. A UI component can raise events and you can write code to handle the events. This event-driven-ness enables user interactivity in JavaFX applications.

There are many types of events, all derive from the javafx.event.Event class. Subclasses of Event include ActionEvent, InputMethodEvent, MouseEvent, MouseDragEvent, ScrollEvent, SwipeEvent, and so on.

Different components may raise different events. For example, clicking a button raises an ActionEvent and changing the text in a TextField triggers an InputMethodEvent. You can write and register an event handler that will be called when the corresponding event occurs. For instance, you can write a handler for the InputMethodEvent of a TextField to change entered text to upper case. Or, you can write a handler that will open another Stage if a button is clicked.

The easiest way to write and register an event handler in JavaFX is by using one of the convenience methods provided by the Node class. The method names have the pattern setOnXXX and the methods are inherited by all descendents of Node. Examples of the convenience methods are setOnDragEntered, setOnDragExited, setOnInputMethodTextChanged, setOnKeyTyped, setOnMouseClicked, and many, many others. Subclasses of Node may add more convenience methods to accommodate events specific to them.

These convenience methods take an EventHandler object as an argument. javafx.event.EventHandler is a parameterized interface with a method, handle. Here is the definition of EventHandler.

```
 package javafx.event;
public interface EventHandler<T extends Event> extends 
        java.util.EventListener {

    void handle(T event)

}
```

When constructing an EventHandler, you must pass an appropriate event type. For example, the following code construct an EventHandler for the ActionEvent.

```
 EventHandler handler = new EventHandler<ActionEvent>() { 

    @Override 
    public void handle(ActionEvent event) { 
        // do something
    } 
};
```

The RotateDemo class in Listing 6.4 shows JavaFX event processing. The class has a Rectangle and a Button and captures the ActionEvent of the Button. Whenever the button is clicked, the Rectangle is rotated 10 degrees clock-wise.

Listing 6.4: The RotateDemo class

```
 package app06;

import javafx.application.Application; 
import javafx.collections.ObservableList; 
import javafx.event.ActionEvent; 
import javafx.event.EventHandler; 
import javafx.scene.Node; 
import javafx.scene.Scene; 
import javafx.scene.control.Button; 
import javafx.scene.layout.VBox; 
import javafx.scene.paint.Color; 
import javafx.scene.shape.Rectangle; 
import javafx.stage.Stage; 

public class RotateDemo extends Application { 

    @Override 
    public void start(Stage stage) { 
        VBox root = new VBox(40); 
        ObservableList<Node> children = root.getChildren(); 
        final Rectangle rect = new Rectangle(80, 50); 
        rect.setFill(Color.AQUAMARINE); 
        children.add(rect); 

        Button button = new Button("Rotate"); 
        button.setOnAction(new EventHandler<ActionEvent>() { 
            @Override 
            public void handle(ActionEvent event) { 
                rect.setRotate(rect.getRotate() + 10); 
            } 
        }); 
        children.add(button); 

        Scene scene = new Scene(root, 120, 130); 
        scene.setFill(Color.BEIGE); 

        stage.setTitle("Rotate Demo"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
}
```

In the start method of the application, a Button is created and its setOnAction method called.

```
 Button button = new Button("Rotate"); 
        button.setOnAction(new EventHandler<ActionEvent>() { 
            @Override 
            public void handle(ActionEvent event) { 
                rect.setRotate(rect.getRotate() + 10); 
            } 
        }); 
```

Note how the EventHandler was created and passed to the button’s setOnAction convenience method.

Figure 6.6 shows the application. Try clicking the button and watch the effect.

![](Images/0606.png)

Figure 6.6: Event handling in JavaFX

Styling with CSS

Some of the controls offer methods to change their look and feel. For example, the setFont method of the Label class allows you to set the font to display the label text. While these methods are easy to use, they have to be called from within the code and this implies tight-coupling between the presentation layer and the business logic. A better way is to style the UI components using CSS (Cascading Style Sheet). JavaFX CSS is not exactly the same as that used in web design. In this chapter CSS refers to the CSS used in JavaFX applications.

A CSS file contains styles that can be referred to by id or by class. Each of the JavaFX controls is already assigned a default CSS class that is similar to the Java class name of the control. For example, the default style for Button is button and the default style for Label is label. This means, to provide a style that affects all buttons, you simply need a style named button in your CSS file. For example,

```
 .button {
    -fx-border-width: 3px; 
    -fx-background-color:#dd8818; 
} 
```

The default style for a control with a multiword name is the combination of the words separated by a hyphen. For instance, the default style for CheckBox is check-box and the default style for ProgressBar is progress-bar.

Non-control nodes do not have a default style. If you want to style a VBox, for example, you first need to add a CSS class to the instance. For example, the following code adds a style named vbox to a Vbox.

```
 VBox vBox = new VBox(); 
vBox.getStyleClass().add("vbox"); 
```

The VBox will then react to a vbox style in any CSS file referred to by the application.

In addition to using style classes, you can also create a style that will be referred by the component identifier. You do this if you want a style that will only affect a certain instance of a type, and not all instances of that particular type. For example, the .button style affects all Button controls in an application. If you want a style to affect a certain Button and not all Buttons, you can either add a new class to the Button or add an identifier to it. Here is an example of a Button that is assigned the id nextBtn.

```
 Button nextButton = new Button("Next"); 
nextButton.setId("nextBtn"); 
```

You can then create this style in your CSS file that will only affect that Button.

```
 #nextBtn { 
    -fx-font-weight: bold; 
}
```

Note that each node has a setStyle method that you can call to assign a CSS style. However, this practice is not recommended as you are mixing presentation and business logic. Here is an example of how you can use setStyle.

```
 Button button = new Button();
button.setStyle("-fx-background-color:green");
```

It’s better to write all your styles in a CSS file. Once your CSS file is ready, you can load it from the application’s start method, like this.

```
 @Override 
public void start(Stage stage) { 
    ...
    Scene scene = ...; 
    scene.getStylesheets().add("style.css");
    ...
} 
```

Here, style.css is the CSS file located in the same location as the class file.

The following are some of the styles used in this chapter.

*   -fx-fill
*   -fx-font-family
*   -fx-font-size
*   -fx-font-style
*   -fx-font-weight
*   -fx-background-color
*   -fx-text-fill

As an example, consider the CSSDemo class in Listing 6.5 that uses the style.css file in Listing 6.6.

Listing 6.5: The CSSDemo class

```
 package app06;
import javafx.application.Application; 
import javafx.scene.Scene; 
import javafx.scene.control.Button; 
import javafx.scene.control.Label; 
import javafx.scene.layout.BorderPane; 
import javafx.scene.layout.HBox; 
import javafx.stage.Stage; 

public class CSSDemo extends Application { 

    @Override 
    public void start(Stage stage) { 
        BorderPane root = new BorderPane(); 

        root.setCenter(new Label("Welcome")); 

        HBox hBox = new HBox(); 
        hBox.getStyleClass().add("hbox"); 

        Button backButton = new Button("Back"); 
        hBox.getChildren().add(backButton); 
        Button nextButton = new Button("Next"); 
        nextButton.setId("nextBtn"); 
        hBox.getChildren().add(nextButton); 
        root.setBottom(hBox); 

        Scene scene = new Scene(root, 400, 300); 
        scene.getStylesheets().add("style.css");

        stage.setTitle("CSS Demo"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
} 
```

Listing 6.6: The style.css file

```
 .label { 
    -fx-background-color: #778855; 
    -fx-font-family: helvetica; 
    -fx-font-size: 450%; 
    -fx-text-fill: yellow;
} 
.hbox { 
    -fx-background-color: #2f4f4f; 
    -fx-padding: 15; 
    -fx-spacing: 10; 
    -fx-alignment: center-right; 
} 

.button { 
    -fx-border-width: 2px; 
    -fx-background-color:#ff8800;
    -fx-cursor: hand;
} 

#nextBtn { 
    -fx-font-weight: bold; 
}
```

If you run the application, you’ll see a Stage just like that in Figure 6.7.

![](Images/0607.png)

Figure 6.7: CSS Demo

As a side note, the jfxrt.jar file, the JavaFX runtime file, includes a modena.css file. This is the default style sheet for the root node and UI controls. I recommend that you look at the content of this file to learn all the styles defined. To view this file, go to the directory the jar file is located and run this command.

```
 jar xf jfxrt.jar com/sun/javafx/scene/control/skin/modena/modena.css
```

Using DatePicker

A new component in JavaFX 8, DatePicker allows the user to select a date or enter it as text. You can then retrieve the selected date as a LocalDate. You can also respond to date selection by writing an EventHandler and passing to the DatePicker’s setOnAction method.

Listing 6.7 shows a JavaFX application that uses a DatePicker to select a birthday. If the user selects a future date, an error message will be displayed next to the DatePicker.

Listing 6.7: The DatePickerDemo class

```
 package app06;
import java.time.LocalDate;
import java.time.Period;
import javafx.application.Application;
import javafx.event.Event;
import javafx.event.EventHandler;
import javafx.geometry.HPos;
import javafx.scene.Scene;
import javafx.scene.control.DatePicker;
import javafx.scene.control.Label;
import javafx.scene.layout.GridPane;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;

public class DatePickerDemo extends Application {

    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage stage) {
        stage.setTitle("DatePicker Demo");
        VBox vbox = new VBox(20);
        vbox.setStyle("-fx-padding: 15;");
        Scene scene = new Scene(vbox, 550, 340);
        stage.setScene(scene);

        GridPane gridPane = new GridPane();
        gridPane.setHgap(10);
        gridPane.setVgap(10);

        Label label = new Label("Birthday:");
        gridPane.add(label, 0, 0);
        GridPane.setHalignment(label, HPos.LEFT);

        DatePicker birthdayPicker = new DatePicker();
        gridPane.add(birthdayPicker, 0, 1);

        Label error = new Label();
        gridPane.add(error, 1, 1);

        birthdayPicker.setOnAction(new EventHandler() {
            public void handle(Event t) {
                LocalDate selectedDate = birthdayPicker.getValue();
                System.out.println("Selected date: " + selectedDate);
                LocalDate today = LocalDate.now();
                if (Period.between(selectedDate, today).isNegative()) {
                    error.setText(
                            "Your birthday cannot be later than today");
                } else {
                    error.setText("");
                }
            }
        });

        vbox.getChildren().add(gridPane);
        stage.show();
    }
}
```

Figure 6.8 shows the application.

![](Images/0608.png)

Figure 6.8: Steps to program

Summary

JavaFX is a Java technology for creating desktop and in-browser applications. It is a better solution than both AWT and Swing and is therefore destined to replace its predecessors.

This chapter introduced JavaFX and provided a couple of examples. The next chapter, “JavaFX with FXML” explains how to separate the presentation layer and the business logic using a special markup language called FXML.

Chapter 7

JavaFX with FXML

FXML is an XML-based markup language for constructing JavaFX user interface (UI). Using FXML in JavaFX applications is a great way of separating the presentation layer and the application logic. This chapter discusses FXML and shows how to use it in JavaFX application development.

Overview

A new feature of JavaFX 2, FXML greatly reduces the complexity of your JavaFX classes by moving user interface component construction to an XML-based document. In addition, FXML visualizes the UI component hierarchy much better than Java classes. The root of an FXML document represents a javafx.scene.Parent that can be loaded to JavaFX using a special loader called FXMLLoader. Here is the start method of an Application subclass that uses FXML.

```
 @Override 
public void start(Stage stage) throws Exception { 
    stage.setTitle("FXML Example"); 
    Parent root = (Parent) FXMLLoader.load(
            getClass().getResource("example1.fxml")); 
    Scene scene = new Scene(root, 740, 530); 
    stage.setScene(scene); 
    stage.show(); 
} 
```

The code above calls the load method of FXMLLoader to read an FXML file and convert its content to a Parent object. The Parent object is then used to construct a Scene.

Writing an FXML file is easy. You start by creating a text file and saving it in the same directory as your class file. You can store it somewhere else, but it is easiest to load it if it is in the same directory as the class that will load it.

As an FXML file is an XML document, all FXML documents start with this declaration.

```
 <?xml version="1.0" encoding="UTF-8"?> 
```

Next come the import directives to import types you will reference in the FXML file. You can import a package or a type.

```
 <?import javafx.scene.*?> 
<?import javafx.scene.control.*?> 
<?import javafx.scene.layout.*?> 
<?import javafx.geometry.Insets?> 
```

The root element comes next. It can be any subclass of Parent. Here is an example.

```
 <GridPane xmlns:fx="http://javafx.com/fxml" 
        hgap="5" vgap="12" layoutY="30">

</GridPane>
```

The fx prefix is a special prefix in FXML. You will learn its use later in this chapter.

To set a property in an object, use a nested element or an attribute. For example, the hgap attribute in the GridPane element above populates the GridPane’s hgap property.

Inside the root element, construct your UI. Listing 7.1 shows an example FXML file.

Listing 7.1: An example FXML file

```
 <?xml version="1.0" encoding="UTF-8"?> 
<?import javafx.scene.*?> 
<?import javafx.scene.control.*?> 
<?import javafx.scene.layout.*?> 
<?import javafx.geometry.Insets?> 
<?import javafx.scene.image.Image?> 
<?import javafx.scene.image.ImageView?> 

<BorderPane> 
    <top> 
        <HBox spacing="10.0" style="-fx-background-color:#886699;"> 
            <padding> 
                <Insets top="15" bottom="15" left="12" right="12"/>
            </padding> 
            <Button id="okButton" text="OK" defaultButton="true"/> 
            <Button text="Cancel"/> 
        </HBox> 
    </top> 
</BorderPane> 
```

An element may contain a class to be instantiated or a property to be populated. The FXML file in Listing 7.1 contains a root of type BorderPane. The BorderPane has its top property populated with an HBox. The HBox in turn contains two Buttons and has its padding property populated with an Insets.

More details on FXML can be found here.

```
 http://docs.oracle.com/javafx/2/api/javafx/fxml/doc-files/
introduction_to_fxml.html
```

Note

It is recommended that you use an IDE that supports JavaFX when writing an FXML and take advantage of its code completion feature to make writing FXML easier. NetBeans and IntelliJ support JavaFX, and Eclipse supports JavaFX through a plug-in.

The next sections present examples of using FXML in JavaFX applications.

A Simple FXML-Based Application

This example is a rewrite of the BorderPaneDemo application created in the previous chapter. This time an FXML document is used to construct and organize the UI components. For your reading convenience, the BorderPaneDemo class is reprinted here.

```
 package app07;
import javafx.application.Application; 
import javafx.geometry.Insets; 
import javafx.scene.Scene; 
import javafx.scene.control.Button; 
import javafx.scene.control.ColorPicker; 
import javafx.scene.control.Label; 
import javafx.scene.image.ImageView; 
import javafx.scene.layout.BorderPane; 
import javafx.scene.layout.HBox; 
import javafx.scene.layout.VBox; 
import javafx.stage.Stage; 

public class BorderPaneDemo extends Application { 

    @Override 
    public void start(Stage stage) { 
        Button okButton = new Button("OK"); 
        okButton.setDefaultButton(true); 

        Button cancelButton = new Button("Cancel"); 
        HBox hBox = new HBox(); 
        hBox.setPadding(new Insets(15, 12, 15, 12)); 
        hBox.setSpacing(10); 
        hBox.setStyle("-fx-background-color: #886699;"); 
        hBox.getChildren().addAll(okButton, cancelButton); 
        BorderPane root = new BorderPane(); 
        root.setTop(hBox); 

        ImageView imageView = new ImageView("image/1.jpg"); 
        root.setCenter(imageView); 

        VBox vBox = new VBox(); 
        vBox.setStyle("-fx-background-color: " + 
        		"#ddeeff;-fx-padding:10px"); 
        vBox.getChildren().addAll( 
                new Label("Select Color:"), 
                new ColorPicker()); 
        root.setLeft(vBox); 

        root.setStyle("-fx-background-color: #6680e6;"); 
        Scene scene = new Scene(root, 740, 530); 

        stage.setTitle("HBox, VBox, BorderPane Demo"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
}
```

The UI construction part of the BorderPaneDemo class can be replaced with the markup in the example1.fxml file shown in Listing 7.2.

Listing 7.2: The example1.fxml file

```
 <?xml version="1.0" encoding="UTF-8"?> 
<?import javafx.scene.*?> 
<?import javafx.scene.control.*?> 
<?import javafx.scene.layout.*?> 
<?import javafx.geometry.Insets?> 
<?import javafx.scene.image.Image?> 
<?import javafx.scene.image.ImageView?> 

<BorderPane> 
    <top> 
        <HBox spacing="10.0" style="-fx-background-color:#886699;"> 
            <padding> 
                <Insets top="15" bottom="15" left="12" right="12"/>     
            </padding> 
            <Button id="okButton" text="OK" defaultButton="true"/> 
            <Button text="Cancel"/> 
        </HBox> 
    </top> 
    <left> 
        <VBox style="-fx-background-color:#ddeeff;-fx-padding:10px"> 
            <Label text="Select Color:"/> 
            <ColorPicker /> 
        </VBox> 
    </left> 
    <center> 
        <ImageView> 
            <Image url="/image/1.jpg"></Image> 
        </ImageView> 
    </center> 
</BorderPane> 
```

The main Java class, called Example1, is given in Listing 7.3\. It extends Application and provides an implementation of the start method.

Listing 7.3: The Example1 class

```
 package app07;
import javafx.application.Application; 
import javafx.fxml.FXMLLoader; 
import javafx.scene.Parent; 
import javafx.scene.Scene; 
import javafx.stage.Stage; 

public class Example1 extends Application { 

    @Override 
    public void start(Stage stage) throws Exception {
        // Example1.fxml must be located in the same directory
        // as Example1.class
        Parent root = FXMLLoader.load(
                getClass().getResource("example1.fxml")); 
        root.setStyle("-fx-background-color: #6680e6;"); 
        Scene scene = new Scene(root, 740, 530); 
        stage.setTitle("JavaFX with FXML (Example 1)"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
}
```

The start method uses FXMLLoader to load the FXML document and return a Parent object that contains the components declared in the document. The method then creates a Scene and passes the Scene to the Stage before calling the show method on the Stage.

Figure 7.1 shows the result of running the application.

![](Images/0701.png)

Figure 7.1: Using FXML

Event Handling with FXML

FXML is a powerful language. Among its features is the ability to bind a UI component with an event-processing method (event handler) in a controller, so that the method will be called when the event occurs. A controller is a Java class that implements javafx.fxml.Initializable. To take advantage of this feature, you must use the fx:controller attribute in your root element, like this.

```
 <Group fx:controller="app7.Example2Controller" 
```

Recall that fx is a special prefix in FXML.

To bind a component to an event handler, use the relevant onXXX attribute of the element. For example, to bind the ActionEvent with a method called handleAction in the controller, write this.

```
 onAction="#handleAction"
```

For example, consider the following application that features a Login form that takes a user name and password. The primary stage of the application is shown in Figure 7.2.

![](Images/0702.png)

Figure 7.2: The Login form in Example 2

The user may enter a user name and password. Clicking Reset clears the User Name and Password fields. Clicking Login authenticates the user. The authentication result will be written on the Label above the fields.

The application consists of an FXML document (example2.fxml in Listing 7.4), a controller class (Example2Controller in Listing 7.5), and the main class (Example2 in Listing 7.6).

Listing 7.4: The example2.fxml file

```
 <?xml version="1.0" encoding="UTF-8"?> 

<?import javafx.scene.*?> 
<?import javafx.scene.control.*?> 
<?import javafx.scene.layout.*?> 
<?import javafx.geometry.Insets?> 

<GridPane xmlns:fx="http://javafx.com/fxml" 
        fx:controller="app07.Example2Controller" 
        hgap="5" vgap="12" layoutY="30"  > 
    <columnConstraints> 
        <ColumnConstraints percentWidth="15"/> 
        <ColumnConstraints percentWidth="35" 
                halignment="RIGHT"/> 
        <ColumnConstraints percentWidth="35"/> 
        <ColumnConstraints percentWidth="10"/> 
    </columnConstraints> 

    <children> 
        <Label fx:id="statusLabel" > 
            <GridPane.columnIndex>1</GridPane.columnIndex> 
            <GridPane.rowIndex>0</GridPane.rowIndex> 
            <GridPane.columnSpan>2</GridPane.columnSpan> 
        </Label> 

        <Label text="User Name:"> 
            <GridPane.columnIndex>1</GridPane.columnIndex> 
            <GridPane.rowIndex>1</GridPane.rowIndex> 
        </Label> 
        <TextField fx:id="userNameField"> 
            <GridPane.columnIndex>2</GridPane.columnIndex> 
            <GridPane.rowIndex>1</GridPane.rowIndex> 
        </TextField> 

        <Label text="Password:"> 
            <GridPane.columnIndex>1</GridPane.columnIndex> 
            <GridPane.rowIndex>2</GridPane.rowIndex> 
        </Label> 
        <PasswordField fx:id="passwordField"> 
            <GridPane.columnIndex>2</GridPane.columnIndex> 
            <GridPane.rowIndex>2</GridPane.rowIndex> 
        </PasswordField> 
        <Button fx:id="resetButton" text="Reset" 
                onAction="#handleReset"> 
            <GridPane.columnIndex>1</GridPane.columnIndex> 
            <GridPane.rowIndex>3</GridPane.rowIndex> 
        </Button> 
        <Button fx:id="loginButton" text="Login" 
                defaultButton="true" onAction="#handleLogin"> 
            <GridPane.columnIndex>2</GridPane.columnIndex> 
            <GridPane.rowIndex>3</GridPane.rowIndex> 
        </Button> 
    </children> 
</GridPane>
```

The FXML document in Listing 7.2 uses a GridPane as the root element. The markup also populates the columnConstraints and children properties of the GridPane. The columnContraints contains ColumnConstraints elements that specify the width for each of its columns. The children property specifies the UI components to be rendered inside the GridPane.

Pay special attention to the onAction attributes of the Button elements. They are used to bind the ActionEvent with the handleLogin and handleReset methods, respectively.

Listing 7.5: The Example2Controller class

```
 package app07;
import java.net.URL; 
import java.util.ResourceBundle; 
import javafx.event.ActionEvent; 
import javafx.fxml.FXML; 
import javafx.fxml.Initializable; 
import javafx.scene.control.Label; 
import javafx.scene.control.PasswordField; 
import javafx.scene.control.TextField; 

public class Example2Controller implements Initializable { 

    @FXML 
    private TextField userNameField; 
    @FXML 
    private PasswordField passwordField; 
    @FXML 
    private Label statusLabel; 

    @FXML 
    private void handleReset(ActionEvent event) { 
        userNameField.setText(""); 
        passwordField.setText(""); 
        statusLabel.setText(""); 
    } 

    @FXML 
    private void handleLogin(ActionEvent event) { 
        String userName = userNameField.getText(); 
        String password = passwordField.getText(); 
        if ("john".equals(userName) 
                && "secret".equals(password)) { 
            statusLabel.setText("Login successul"); 
        } else { 
            statusLabel.setText("Login failed"); 
        } 
    } 

    @Override 
    public void initialize(URL url, ResourceBundle rb) { 
    }    
} 
```

A controller provides event-handlers for the FXML document it is bound with. An event-handler must be annotated with @FXML. In addition, to allow access to a UI component, you can annotate a field with @FXML. The annotated field must have the same name as the fx:id attribute of the component it is bound to.

In the controller class in Listing 7.5, three fields are declared and annotated with @FXML: userNameField, passwordField, and statusLabel.

Listing 7.6: The Example2 class

```
 package app07;
import javafx.application.Application; 
import javafx.fxml.FXMLLoader; 
import javafx.scene.Parent; 
import javafx.scene.Scene; 
import javafx.stage.Stage; 

public class Example2 extends Application { 

    @Override 
    public void start(Stage stage) throws Exception { 
        Parent root = FXMLLoader.load( 
                getClass().getResource("example2.fxml")); 
        Scene scene = new Scene(root, 300, 200); 
        stage.setTitle("Login Form"); 
        stage.setScene(scene); 
        stage.show(); 
    } 

    public static void main(String[] args) { 
        launch(args); 
    } 
}
```

Finally, the Example2 class in Listing 7.6 loads the FXML document and creates and shows the primary stage.

Summary

FXML is a markup language for constructing the UI component graph of a JavaFX application. Using FXML makes writing the UI easier. In this chapter you learned the basics of FXML and how to use it.

Chapter 8

Nashorn

Nashorn is a JavaScript engine in Java 8\. It replaces Mozilla Rhino, an older JavaScript engine that comes with JDK 7 and JDK 6\. The new engine is fast and lets you mix Java with JavaScript. With Nashorn you can run JavaScript from Java or run Java code quickly from a command prompt. In addition, you can use Nashorn to run JavaFX applications and execute shell scripts on UNIX or Linux machines.

This chapter introduces Nashorn.

Overview

The API for Java scripting actually has been available since JDK 1.6 and takes the form of the javax.script package. JDK 1.6 and JDK 1.7 use Mozilla Rhino and the engine is still available in Java 8\. However, for new projects you should use Nashorn, which is faster than its predecessor and provides better compliance with ECMAScript.

The name Nashorn is a German word meaning rhinoceros. The Nashorn engine is based on JSR 292, “Supporting Dynamically Typed Languages on the Java Platform.” This JSR allows dynamic languages targeting the JVM to run faster by taking advantage of invokedynamic, a new Java bytecode. The specification can be downloaded from this web page:

```
 https://jcp.org/en/jsr/detail?id=292
```

Using the jjs Command

jjs is a tool that comes with the JRE 1.8 and the JDK 1.8\. It is located under the JAVA_HOME/bin directory, where JAVA_HOME is the installation directory of the JRE or the JDK.

The easiest way to test the power of Nashorn is by using the jjs command tool that ships with Java 8\. The syntax is as follows.

```
 jjs [options] [script-files] [-- arguments]
```

Used without a script file, jjs will launch as a read-eval-print loop (REPL), an environment to which you can type in commands or expressions.

You can try this at home:

```
 $ jjs
```

The interface for jjs is a prompt like this:

```
 jjs>
```

You can now start typing. For example:

```
 jjs> "Hello World"
Hello World
```

Here is another example:

```
 jjs> var name = 'Charlie'
jjs> print('Hello ' + name)
Hello Charlie
```

And, here is a JavaScript function:

```
 jjs> function triple(n) { return 3 * n }
function triple(n) { return 3 * n }
```

Calling the function triple and passing 5 returns 15:

```
 jjs> triple(5)
15
```

Of course, you can put your script in a file and pass it to jjs. Suppose you have a script file named test1.js as printed in Listing 8.1.

Listing 8.1: The test1.js file

```
 function add(a, b) {
    return a + b;
}
var c = add(10, 20)
print(c)
```

Now, call jjs and pass test1.js:

```
 $ jjs test1.js
30
```

As mentioned earlier, jjs can be used with options. Table 8.1 lists some of the options.

| Option | Description |
| -ccs=size or--class-cache-size=size | Specifies the class cache size in bytes. The letter k or K indicates kilobytes, m or M megabytes and g or G gigabytes. The default class cache size is 50. |
| -co or --compile-only | Compiles the script without running it. |
| -cp or -classpath | Specifies the class path. This option can be repeated to specify multiple class paths. |
| -Dname=value | Passes a system property key and value. |
| -d=path or--dump-debug-dir=path | Specifies the path to a directory to dump class files to. |
| --debug-lines=true&#124;false | Indicates whether a line number table should be generated in the class file. By default, this option is on. |
| --debug-locals | Generates a local variable table in the class file. |
| -doe or--dump-on-error | Provides a full stack trace when an error occurs. By default, only a brief error message is printed. |
| --early-lvalue-error | Reports invalid lvalue expressions as early errors. |
| --empty-statements | Preserves empty statements in the Java abstract syntax tree. |
| -fv or -fullversion | Prints the full version of Nashorn. |
| --function-statement-error | Prints an error message when a function declaration is used as a statement. |
| --function-statement-warning | Prints a warning message when a function declaration is used as a statement. |
| -fx | Launches the script as a JavaFX application. |
| -h or -help | Prints the list of options and their descriptions. |
| -Joption | Passes a Java option to the JVM. |
| -lazy-compilation | Enables lazy code generation. |
| --loader-per-compile | Creates a new class loader per compile. |
| --log=subsystem:level | Logs at the specified level. |
| --package=name | Specifies the package for generated classes. |
| --parse-only | Parses the code without compiling. |
| --print-ast | Prints the abstract syntax tree of the code. |
| --print-code | Prints the bytecode. |
| --print-lower-ast | Prints the lowered AST. |
| --print-lower-parse | Prints the lowered parse tree. |
| --scripting | Enabled shell scripting. |
| --stderr=filename&#124;stream&#124;tty | Redirects the standard error stream to the specified file, stream or text terminal. |
| --stdout=filename&#124;stream&#124;tty | Redirects the standard output stream to the specified file, stream or text terminal. |
| -v or -version | Prints the Nashorn version. |
| -xhelp | Prints extended help for command-line options. |

Table 8.1: jjs options

You can list all available options using the -help option:

```
 $ jjs -help
```

Or even a more complete list of options using -xhelp:

```
 $ jjs -xhelp
```

If you are curious about how the underlying compiler works, try the --print-ast and --print-code options.

```
 $ jjs --print-ast myscript.js
$ jjs --print-code myscript.js
```

In addition to jjs, there is also another tool, jrunscript, that invokes any script engine compliant with JSR 223, “Scripting for the Java Platform.” With Java 8 installed and without any options, jrunscript will invoke Nashorn.

```
 $ jrunscript
nashorn>
```

Try it yourself.

```
 $ jrunscript
nashorn> print(300 + 700)
1000
```

Using Nashorn from Java Code

You can run JavaScript from your Java code. But, why would you do that? One scenario: You have complex JavaScript functions that you don’t want to rewrite in Java.

To call Nashorn from Java, use the javax.script package. The ScriptEngine interface’s eval methods evaluate a JavaScript script and returns the result as a java.lang.Object. The multiple overloads of eval allow you to pass a String or a Reader.

```
 public java.lang.Object eval(java.lang.String script) 
        throws ScriptException
public java.lang.Object eval(java.io.Reader scriptFile)
        throws ScriptException
```

You can obtain a ScriptEngine implementation using the ScriptEngineManager’s getEngineByName method:

```
 ScriptEngineManager factory = new ScriptEngineManager();
ScriptEngine engine = factory.getEngineByName("nashorn");
```

For example, the ScriptEngineDemo1 class in Listing 8.2 obtains a ScriptEngine and runs a small JavaScript script.

Listing 8.2: The ScriptEngineDemo1 class

```
 package nashorn.fromjava;
import javax.script.ScriptEngine;
import javax.script.ScriptEngineManager;
import javax.script.ScriptException;

public class ScriptEngineDemo1 {
    public static void main(String[] args) {
        ScriptEngineManager factory = new ScriptEngineManager();
        ScriptEngine engine = factory.getEngineByName("nashorn");

        // evaluate JavaScript statement
        try {
            engine.eval("print('A taste of Nashorn');");
        } catch (ScriptException e) {
        	e.printStackTrace();
        }
    }
}
```

Running the ScriptEngineDemo1 class prints “A taste of Nashorn” on the console.

Of course, most of the time it is more convenient to write JavaScript code in a file rather than as a Java String. Listing 8.3 shows how to load a JavaScript file and execute it with Nashorn.

Listing 8.3: Evaluating a JavaScript file

```
 package nashorn.fromjava;
import java.io.FileNotFoundException;
import java.io.FileReader;
import javax.script.ScriptEngine;
import javax.script.ScriptEngineManager;
import javax.script.ScriptException;

public class ScriptEngineDemo2 {
    public static void main(String[] args) {
        ScriptEngineManager factory = new ScriptEngineManager();
        ScriptEngine engine = factory.getEngineByName("nashorn");
        // evaluate JavaScript file
        try {
            engine.eval(new FileReader("jjstest/test1.js"));
        } catch (FileNotFoundException | ScriptException e) {
        	e.printStackTrace(); 
        }
    }
}
```

Invoking Java from JavaScript

You can use your Java skills to perform certain tasks with Nashorn. Neither a Java project nor compilation is necessary. Assuming you are using a computer with Java 8 installed, you can, for example, read a text file and process the content or use the java.lang.Math class to perform complex arithmetic operations.

You can also tell Nashorn to handle Java 8 new features. Even though Nashorn cannot parse Java lambda expressions, don’t despair. You can replace a lambda expression with an anonymous JavaScript function. For example, this lambda expression

```
 (a) -> 3 * a
```

can be replaced with

```
 function(a) {
    return 3 * a;
}
```

The code in Listing 8.4 opens and reads the content of the sales.txt file and calculates the sales figures there.

Listing 8.4: Using Java from JavaScript

```
 var path = java.nio.file.Paths.get("sales.txt");
var lines = java.nio.file.Files.lines(path);
print("Total: " + lines.mapToDouble(function(s) {return parseFloat(s)})
        .sum());

// lines stream has been closed, so we need to re-open it
lines = java.nio.file.Files.lines(path);
print("Average: " + lines.mapToDouble(function(s) {return parseFloat(s)})
        .average().getAsDouble());
```

To give you a better perspective, the equivalent Java code is given in Listing 8.5.

Listing 8.5: The equivalent Java code

```
 Path path = java.nio.file.Paths.get("sales.txt");
Stream<String> lines = java.nio.file.Files.lines(path);
DoubleStream ds = lines.mapToDouble(a -> Double.parseDouble(a));
System.out.println("Total: " + ds.sum());

lines = java.nio.file.Files.lines(path);
ds = lines.mapToDouble(a -> Double.parseDouble(a));
System.out.println("Average: " + ds.average().getAsDouble());
```

To run the script in Listing 8.4, change directory to where the sales.txt file is located and issue this command:

```
 $ jjs test1.js
```

The result will be printed on the console:

```
 30
```

Running JavaFX with Nashorn

Another intriguing feature of Nashorn is its ability to script JavaFX. All you need is a start function in a JavaScript file. The start function must accept an argument that will be passed the primary Stage for the application.

Consider the code in Listing 8.6.

Listing 8.6: A JavaFX script (test1.js)

```
 function start(stage) {
    stage.title = "Scripting JavaFX";
    var button = new javafx.scene.control.Button();
    button.text = "Click Me!";
    button.onAction = function() {
    	print("Thank you!");
    }
    var root = new javafx.scene.layout.StackPane();
    root.children.add(button);
    stage.scene = new javafx.scene.Scene(root, 400, 200);
    stage.show();
}
```

To execute a JavaFX script, you must invoke jjs with the -fx option:

```
 jjs -fx test1.js
```

Figure 8.1 shows the JavaFX application that gets created when you run the test1.js script.

![](Images/0801.png)

Figure 8.1: Scripting JavaFX

Using Nashorn As Shell Script Replacement

Linux die-hards are usually good with the Linux commands. If your Linux skills are limited to the most basic commands such whoami and ls, however, you can take advantage of Nashorn. Nashorn allows you to invoke Linux commands and process the results.

To execute a Linux command in Nashorn, invoke jjs and enclose the command with backtick characters (`). On the keyboard, the character key is normally located to the left of the 1\. For example, to list the contents of the current directory, use this.

```
 jjs> `ls -al`
```

The advantage of using Nashorn to invoke a Linux command is that you can process the output. For instance, the following invokes the cat command to print a Demo.java file and append line numbers.

```
 jjs> var lines = `cat Demo.java`.split('\n');
jjs> var i = 1;
jjs> for each (line in lines) { print(i++ + '\t' + line) };
```

Here is the result.

```
 1	package nashorn.scripting;
2	
3	public class Demo {
4		public static void main(String[] args) {
5			System.out.println("This is a demo");
6		}
7	}
8 
```

As another example, the following script can be used to display a long document one line at a time. This will eliminate scrolling back to the beginning of the document as you would normally have to do when printing a long manual.

```
 jjs> var System = java.lang.System
jjs> var lines = `man pwd`.split('\n')
jjs> for each (line in lines) {System.out.print(line); System.in.read()}
```

Type Enter to show the next line of text.

Summary

Nashorn is a new JavaScript engine in Java 8\. Not only does it allow you to execute JavaScript from Java code, it also comes with advanced features to script JavaFX applications and process the output of a Linux command.