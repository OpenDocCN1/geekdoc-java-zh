![](CoverDesign.jpg)

![Cover](CoverDesign.jpg)

Java 8 New Features: Practical Heads-Up Guide

[Smashwords Edition]

Richard Reese

![](image001.jpg)

* * * * *

Published in 2014 by P8tech, an imprint of Play Technologies (England) Limited

Copyright © Play Technologies (England) Limited

Richard Reese asserted their rights under the Copyright, Designs and Patents Act, 1988 to be identified as the author of this book.

ISBN: 978-0-9929105-4-9

All Rights Reserved. No part of this publication may be reproduced, stored in a retrieval system, or transmitted in any form or by any means, electronic, mechanical, photocopying, recording or otherwise, without the prior permission of the publisher.

This book is sold subject to the condition that it shall not, by way of trade or otherwise, be lent, re-sold, hired out or otherwise circulated without the publisher’s prior consent in any form of binding or cover other than that it which it is published and without a similar condition including this condition being imposed on the subsequent purchaser.

P8tech has endeavoured to provide trademark information about all the companies and products mentioned in this book by the appropriate use of capitals. However, P8tech cannot guarantee the accuracy of this information.

Published by P8tech Limited
6 Woodside
Churnet View Road
Oakamoor
ST10 3AE
United Kingdom

[www.p8tech.com](http://www.p8tech.com)

Cover image ©Shutterstock/Maks Narodenko

* * * * *

Table of Contents

[Title Page](#section-0001.html_auto_bookmark_1)

[About The Author](#section-0003.html_auto_bookmark_1)

[Code Examples – Read Me](#section-0004.html_auto_bookmark_1)

[Errata](#section-0005.html_auto_bookmark_1)

[Chapter 1 – Java 8 and Interface Enhancements](#section-0006.html_auto_bookmark_1)

[Introduction to Java 8](#section-0006.html_auto_bookmark_2)

[Default Methods and Functional Interfaces](#section-0006.html_auto_bookmark_3)

[Creating Default Methods](#section-0006.html_auto_bookmark_4)

[Understanding the Importance of Default Methods](#section-0006.html_auto_bookmark_5)

[Defining a Default Method](#section-0006.html_auto_bookmark_6)

[Overriding Default Methods](#section-0006.html_auto_bookmark_7)

[Using Inheritance with Default Methods](#section-0006.html_auto_bookmark_8)

[Working with Single Inheritance](#section-0006.html_auto_bookmark_9)

[Working with Multiple Inheritance](#section-0006.html_auto_bookmark_10)

[Understanding how Diamond Inheritance Works](#section-0006.html_auto_bookmark_11)

[Resolving Overridden Default Methods](#section-0006.html_auto_bookmark_12)

[Using Default Methods](#section-0006.html_auto_bookmark_13)

[Extending Existing Interfaces](#section-0006.html_auto_bookmark_14)

[Using Default Methods to Supplement Adapter Classes](#section-0006.html_auto_bookmark_15)

[Using Default Methods in Core Java Classes](#section-0006.html_auto_bookmark_16)

[Using a Class to Support Default Methods](#section-0006.html_auto_bookmark_17)

[Understanding the Difference between an Abstract Class and Interfaces](#section-0006.html_auto_bookmark_18)

[Using Static Interface Methods](#section-0006.html_auto_bookmark_19)

[Functional Interfaces](#section-0006.html_auto_bookmark_20)

[Creating a Functional Interface](#section-0006.html_auto_bookmark_21)

[Using  the @FunctionalInterface Annotation](#section-0006.html_auto_bookmark_22)

[Overriding Object Class Methods in a Functional Interface](#section-0006.html_auto_bookmark_23)

[Using Functional Interfaces in the Core Libraries](#section-0006.html_auto_bookmark_24)

[Conclusion](#section-0006.html_auto_bookmark_25)

[Chapter 2 – Lambda Expressions](#section-0007.html_auto_bookmark_1)

[Understanding Lambda Expressions](#section-0007.html_auto_bookmark_2)

[Inferring the Type of the Target](#section-0007.html_auto_bookmark_3)

[Creating Lambda Expressions](#section-0007.html_auto_bookmark_4)

[Lambda Expression Syntax Rules](#section-0007.html_auto_bookmark_5)

[Declaring Parameter Types](#section-0007.html_auto_bookmark_6)

[Mixing Parameter Declarations](#section-0007.html_auto_bookmark_7)

[Omitting Parentheses](#section-0007.html_auto_bookmark_8)

[Eliminating the Block Statement](#section-0007.html_auto_bookmark_9)

[Using Multiple Statements in a Lambda Expression Body](#section-0007.html_auto_bookmark_10)

[Using a Return Value](#section-0007.html_auto_bookmark_11)

[Writing Succinct Lambda Expressions](#section-0007.html_auto_bookmark_12)

[Capturing Variables in a Lambda Expression](#section-0007.html_auto_bookmark_13)

[Differentiating between a Lambda Expression and a Closure](#section-0007.html_auto_bookmark_14)

[Method and Constructor References](#section-0007.html_auto_bookmark_15)

[Using Static Method References](#section-0007.html_auto_bookmark_16)

[Using Instance Method References](#section-0007.html_auto_bookmark_17)

[Using Constructor References](#section-0007.html_auto_bookmark_18)

[Working with Lambda Expressions](#section-0007.html_auto_bookmark_19)

[Using Lambda Expressions with Variable Declarations](#section-0007.html_auto_bookmark_20)

[Using Lambda Expressions as a Return Value](#section-0007.html_auto_bookmark_21)

[Using Exceptions with a Lambda Expression](#section-0007.html_auto_bookmark_22)

[Using Lambda Expressions with the Tertiary Operator](#section-0007.html_auto_bookmark_23)

[Casting Lambda Expressions](#section-0007.html_auto_bookmark_24)

[Using Lambda Expressions to Initialize an Array](#section-0007.html_auto_bookmark_25)

[Writing Recursive Lambda Expressions](#section-0007.html_auto_bookmark_26)

[Using the java.util.function Functional Interfaces](#section-0007.html_auto_bookmark_27)

[Using the Predicate Interface](#section-0007.html_auto_bookmark_28)

[Using the Function Interface](#section-0007.html_auto_bookmark_29)

[Using the BiFunction Interface](#section-0007.html_auto_bookmark_30)

[Using the Consumer Interface](#section-0007.html_auto_bookmark_31)

[Using the Supplier Interface](#section-0007.html_auto_bookmark_32)

[Using Operator Type Interfaces](#section-0007.html_auto_bookmark_33)

[Using the UnaryOperator Interface](#section-0007.html_auto_bookmark_34)

[Using the BinaryOperator Interface](#section-0007.html_auto_bookmark_35)

[Conclusion](#section-0007.html_auto_bookmark_36)

[Chapter 3 – Streams](#section-0008.html_auto_bookmark_1)

[Streams](#section-0008.html_auto_bookmark_2)

[Stream Characteristics](#section-0008.html_auto_bookmark_3)

[Streams Do Not Store Elements](#section-0008.html_auto_bookmark_4)

[Streams Can Be Unbounded](#section-0008.html_auto_bookmark_5)

[Streams Do Not Modify the Original Source](#section-0008.html_auto_bookmark_6)

[A Stream May Be Ordered](#section-0008.html_auto_bookmark_7)

[Automatic Parallelization](#section-0008.html_auto_bookmark_8)

[An Overview of Stream Methods](#section-0008.html_auto_bookmark_9)

[Creating a Stream](#section-0008.html_auto_bookmark_10)

[Using the Stream Interface’s of Method](#section-0008.html_auto_bookmark_11)

[Using the Collection Class’ stream Method](#section-0008.html_auto_bookmark_12)

[Using a Stream.Builder Interface](#section-0008.html_auto_bookmark_13)

[Using the builder method](#section-0008.html_auto_bookmark_14)

[Generating Infinite Streams](#section-0008.html_auto_bookmark_15)

[Using the iterate Method](#section-0008.html_auto_bookmark_16)

[Concatenating Streams](#section-0008.html_auto_bookmark_17)

[Generating an Empty Stream](#section-0008.html_auto_bookmark_18)

[Using Stream Methods](#section-0008.html_auto_bookmark_19)

[The Part Example Class](#section-0008.html_auto_bookmark_20)

[Using the forEach Method](#section-0008.html_auto_bookmark_21)

[Using the forEachOrdered Method](#section-0008.html_auto_bookmark_22)

[Using the map Method](#section-0008.html_auto_bookmark_23)

[Using Other Map Methods](#section-0008.html_auto_bookmark_24)

[Using the flatmap Method](#section-0008.html_auto_bookmark_25)

[Using the filter Method](#section-0008.html_auto_bookmark_26)

[Using the Match Type Methods](#section-0008.html_auto_bookmark_27)

[Using the findFirst Method](#section-0008.html_auto_bookmark_28)

[Using the findAny Method](#section-0008.html_auto_bookmark_29)

[Using the Optional Class](#section-0008.html_auto_bookmark_30)

[Using the reduce Method](#section-0008.html_auto_bookmark_31)

[Using the Collector Interface and the collect Method](#section-0008.html_auto_bookmark_32)

[Using the Collects Class](#section-0008.html_auto_bookmark_33)

[Using the iterator Method](#section-0008.html_auto_bookmark_34)

[Using the sorted Method](#section-0008.html_auto_bookmark_35)

[Using the distinct Method](#section-0008.html_auto_bookmark_36)

[Using the limit Method](#section-0008.html_auto_bookmark_37)

[Using the skip Method](#section-0008.html_auto_bookmark_38)

[Using the max, min, and count Methods](#section-0008.html_auto_bookmark_39)

[Streams for Primitive Types](#section-0008.html_auto_bookmark_40)

[Using the IntStream Interface](#section-0008.html_auto_bookmark_41)

[Understanding Lazy and Eager Evaluation](#section-0008.html_auto_bookmark_42)

[Using Short-Circuit Methods](#section-0008.html_auto_bookmark_43)

[Using Parallel Stream Operations](#section-0008.html_auto_bookmark_44)

[Conclusion](#section-0008.html_auto_bookmark_45)

[Chapter 4 – Date and Time](#section-0009.html_auto_bookmark_1)

[Introduction](#section-0009.html_auto_bookmark_2)

[Why a New API?](#section-0009.html_auto_bookmark_3)

[A Simple Example](#section-0009.html_auto_bookmark_4)

[The ISO-8601 String Format](#section-0009.html_auto_bookmark_5)

[Design Considerations](#section-0009.html_auto_bookmark_6)

[Understanding the Standard Method Names](#section-0009.html_auto_bookmark_7)

[Understanding the of Type Methods](#section-0009.html_auto_bookmark_8)

[Understanding the from Method](#section-0009.html_auto_bookmark_9)

[Understanding the parse Method](#section-0009.html_auto_bookmark_10)

[Understanding the format Method](#section-0009.html_auto_bookmark_11)

[Understanding the get Type Method](#section-0009.html_auto_bookmark_12)

[Understanding the is Type Methods](#section-0009.html_auto_bookmark_13)

[Understanding the with Type Methods](#section-0009.html_auto_bookmark_14)

[Understanding the plus Type Methods](#section-0009.html_auto_bookmark_15)

[Understanding minus Type Methods](#section-0009.html_auto_bookmark_16)

[Understanding the to Type Methods](#section-0009.html_auto_bookmark_17)

[Understanding the at Type Methods](#section-0009.html_auto_bookmark_18)

[Overview of the Date and Time Packages](#section-0009.html_auto_bookmark_19)

[Getting the Current Time](#section-0009.html_auto_bookmark_20)

[Working with the Instant Class](#section-0009.html_auto_bookmark_21)

[Creating an Instant](#section-0009.html_auto_bookmark_22)

[Creating an Instant Based on the Epoch](#section-0009.html_auto_bookmark_23)

[Creating an Instant Based on Parsing a UTC String](#section-0009.html_auto_bookmark_24)

[Creating an Instant by Adding or Subtracting a Time from an Instant](#section-0009.html_auto_bookmark_25)

[Using the Instant Class’ get Type Methods](#section-0009.html_auto_bookmark_26)

[Working with Time Intervals](#section-0009.html_auto_bookmark_27)

[Creating Offsets Using the of Type Methods](#section-0009.html_auto_bookmark_28)

[Creating Offsets Using the with Type Methods](#section-0009.html_auto_bookmark_29)

[Creating a Duration Using the parse Method](#section-0009.html_auto_bookmark_30)

[Creating a Duration by Adding or Subtracting a Unit](#section-0009.html_auto_bookmark_31)

[Using the Duration Class](#section-0009.html_auto_bookmark_32)

[Using the Period Class](#section-0009.html_auto_bookmark_33)

[Using Date and Time Classes](#section-0009.html_auto_bookmark_34)

[Creating Date and Time Classes](#section-0009.html_auto_bookmark_35)

[Date and Time get Type Methods](#section-0009.html_auto_bookmark_36)

[Adjusting a Date or Time](#section-0009.html_auto_bookmark_37)

[Using the YearMonth, MonthDay, and Year Classes](#section-0009.html_auto_bookmark_38)

[Comparing MonthDay Instances](#section-0009.html_auto_bookmark_39)

[Using the Enumerations DayOfWeek and Month](#section-0009.html_auto_bookmark_40)

[Using the DayOfWeek Enumeration](#section-0009.html_auto_bookmark_41)

[Using the Month Enumeration](#section-0009.html_auto_bookmark_42)

[Working with the Time Zone and Offset Classes](#section-0009.html_auto_bookmark_43)

[Obtaining Available Zone IDs](#section-0009.html_auto_bookmark_44)

[Working with ZoneOffsets](#section-0009.html_auto_bookmark_45)

[Working with Zone Rules](#section-0009.html_auto_bookmark_46)

[Formatting, Queries, and Value-Based Classes](#section-0009.html_auto_bookmark_47)

[Formatting Dates and Times](#section-0009.html_auto_bookmark_48)

[Using Temporal Queries](#section-0009.html_auto_bookmark_49)

[Understanding Value-Based Classes](#section-0009.html_auto_bookmark_50)

[Conclusion](#section-0009.html_auto_bookmark_51)

[Chapter 5 – Odds and Ends](#section-0010.html_auto_bookmark_1)

[Introduction](#section-0010.html_auto_bookmark_2)

[Using the Nashorn JavaScript Engine](#section-0010.html_auto_bookmark_3)

[Accessing the Nashorn Engine](#section-0010.html_auto_bookmark_4)

[Executing JavaScript Code](#section-0010.html_auto_bookmark_5)

[Executing Java Code from JavaScript](#section-0010.html_auto_bookmark_6)

[Implementing a Java Interface](#section-0010.html_auto_bookmark_7)

[File IO Enhancements](#section-0010.html_auto_bookmark_8)

[Using the FileFilter Interface](#section-0010.html_auto_bookmark_9)

[Using the PathMatcher Interface](#section-0010.html_auto_bookmark_10)

[Using the Files Class’ list Method](#section-0010.html_auto_bookmark_11)

[Using the Files Class’ walk Method](#section-0010.html_auto_bookmark_12)

[Using the Path Class’ lines Method](#section-0010.html_auto_bookmark_13)

[Concurrency Enhancements](#section-0010.html_auto_bookmark_14)

[Using the Arrays Class’ parallelSort Method](#section-0010.html_auto_bookmark_15)

[Using the Arrays Class’ parallelSetAll Method](#section-0010.html_auto_bookmark_16)

[Using the Arrays Class’ parallelPrefix Method](#section-0010.html_auto_bookmark_17)

[Collections Enhancements](#section-0010.html_auto_bookmark_18)

[Using the forEachRemaining Method](#section-0010.html_auto_bookmark_19)

[Using the replace Type Methods](#section-0010.html_auto_bookmark_20)

[Using the compute Type Methods](#section-0010.html_auto_bookmark_21)

[Project Jigsaw and Compact Profiles](#section-0010.html_auto_bookmark_22)

[The Compact Profiles](#section-0010.html_auto_bookmark_23)

[Using Compact Profiles](#section-0010.html_auto_bookmark_24)

[Other Enhancements](#section-0010.html_auto_bookmark_25)

[Javadoc Enhancements](#section-0010.html_auto_bookmark_26)

[Security Enhancements](#section-0010.html_auto_bookmark_27)

[VM Related Enhancements](#section-0010.html_auto_bookmark_28)

[Core Java Enhancements](#section-0010.html_auto_bookmark_29)

[Conclusion](#section-0010.html_auto_bookmark_30)

[Appendix - Date and Time Classes](#section-0011.html_auto_bookmark_1)

[Of Type Methods](#section-0011.html_auto_bookmark_2)

[The from Method](#section-0011.html_auto_bookmark_3)

[The parse Method](#section-0011.html_auto_bookmark_4)

[Get Type Methods](#section-0011.html_auto_bookmark_5)

[Is Type Methods](#section-0011.html_auto_bookmark_6)

[With Type Methods](#section-0011.html_auto_bookmark_7)

[Plus Type Methods](#section-0011.html_auto_bookmark_8)

[Minus Type Methods](#section-0011.html_auto_bookmark_9)

[To Type Methods](#section-0011.html_auto_bookmark_10)

[At Type Methods](#section-0011.html_auto_bookmark_11)

[Other Books from P8tech](#section-0012.html_auto_bookmark_1)

About The Author

Richard Reese is an acclaimed author who has written several Java and C books, bringing a focused and easy-to-follow approach to learning. He currently teaches at Tarleton State University.

Richard is currently working on a JMonkeyEngine title.

* * * * *

Code Examples – Read Me

You are reading an electronic version of this book. Some eReaders (and different screen widths) can do some quite funky reformatting to text, including stripping out indentations. As such, the code examples in this ebook are offered as text and image files, to (hopefully) better illuminate the content at hand.

**To get your hands on the code as .txt**, it is available as a freely downloadable file.

Download the file from the publisher page at: *[www.P8tech.com/java701](http://www.P8tech.com/java701)*

* * * * *

Errata

Despite best efforts, mistakes can sometimes creep into books. If you spot a mistake, please feel free to email us at errata@p8tech.com (with the book title in the subject line). The errata page for the book is hosted at *[www.P8tech.com/java702](http://www.P8tech.com/java702)*

* * * * *

Chapter 1 – Java 8 and Interface Enhancements

Introduction to Java 8

-Default Methods and Functional Interfaces

-Creating Default Methods

-Understanding the Importance of Default Methods

-Defining a Default Method

--Overriding Default Methods

-Using Inheritance with Default Methods

--Working with Single Inheritance

--Working with Multiple Inheritance

--Understanding how Diamond Inheritance Works

-Resolving Overridden Default Methods

-Using Default Methods

--Extending Existing Interfaces

--Using Default Methods to Supplement Adapter Classes

--Using Default Methods in Core Java Classes

--Using a Class to Support Default Methods

-Understanding the Difference between an Abstract Class and Interfaces

-Using Static Interface Methods

-Functional Interfaces

--Creating a Functional Interface

--Using  the @FunctionalInterface Annotation

--Overriding Object Class Methods in a Functional Interface

--Using Functional Interfaces in the Core Libraries

-Conclusion

Introduction to Java 8

For Java to remain competitive it has to evolve. The enhancements to version 8 of Java introduce a number of new language features and packages. In this book we will examine most of these additions starting with an explanation of default methods and function interfaces. These new features, whilst useful in themselves, support other Java 8 features such as lambda expressions and stream. Interfaces are the focus of the first chapter.

One of the goals for Java 8 was to support and encourage the use of a functional style of programming. While this has not been completely achieved, the addition of **lambda expressions** certainly encourages this style. Lambda expressions are essentially anonymous functions. With Java 8 come a number of new function-like libraries designed to work with lambda expressions. Chapter 2 explores how to create and use these expressions.

Another goal of Java 8 is to provide better support for concurrent processing. Earlier techniques, while workable, can be error prone and hard to implement. The introduction of **Streams** to Java 8 moves some of the conceptual difficulties of concurrent programming away from the programmer and embeds them in streams. A stream can be thought of as a collection of elements to be processed either sequentially or concurrently. The programmer can specify what needs to be done and not worry about how it is done. In addition, there is support for internal iteration within the collection framework with the addition of the **forEach** method. We will see many applications of streams in Chapter 3.

Handling date and time has never been as clean as it could be in Java. This is rectified in Java 8 with the introduction of the java.time package and new classes to support time related tasks. The improvements introduced help make the execution of these tasks more readable and reliable. The formatting of time has also been improved. These enhancements are presented in Chapter 4.

There have been numerous other additions to Java. These will be discussed in Chapter 5\. They range from virtual machine enhancements, which are not always readily visible to the typical programmer, to enhancements in how Java applications are annotated and documented. In addition, there are a few concurrency and character encoding updates. Also, the Nashorn JavaScript engine has been incorporated into Java which enables execution of JavaScript code from within a Java application.

Default Methods and Functional Interfaces

This chapter focuses on the various changes that have been made to interfaces and how they can be defined and used. It starts out with a discussion of default methods. These types of methods are an important aspect of Java 8 as they lay the groundwork for other enhancements such as lambda expressions and streams. We cover how default expressions are created and used both in old applications and in new ones.

Default methods are methods of an interface that have implementations. This means that classes that implement these types of interfaces do not have to implement default methods. Default methods have been added to existing interfaces such as those found in many collection classes. Since classes that implement such interfaces do not need to override those methods, existing code that uses these interfaces will still work properly.

As with earlier versions of Java, inheritance between interfaces is supported. However, default methods add a new dimension to inheritance and offer opportunities for overriding methods in both single and multiple inheritance situations.

**Functional interfaces** are interfaces that possess one, and only one, abstract method. These types of interfaces are also called Single Abstract Methods (SAM). While an interface can possess default methods, it can have only one abstract method. As demonstrated in Chapter 2, this type of interface provides the foundation for lambda expressions.

Creating Default Methods

Default methods are interface methods that have an implementation. They are declared using the default keyword. An example of a default method follows with a Drawable interface definition consisting of one default method and one abstract method:

interface Drawable {

public default void draw() {

System.out.println(

"The Drawable interface's draw method");

}

public abstract boolean hasBeenDrawn();

}

![](image1.jpg)

To illustrate the use of this interface we will use a Person class as defined below. The draw method does not need to be implemented but the hasBeenDrawn method does since it is abstract:

class Person implements Drawable {

public boolean hasBeenDrawn() {

return true;

}

}

![](image2.jpg)

From a main method we create an instance of the Person class and execute the draw method:

public static void main(String[] args) {

Person person = new Person();

person.draw();

}

![](image3.jpg)

When executed we get an output as follows:

The Drawable interface's draw method

The implementing class did not have to implement the default method in order to use it.

A default method can be added to an existing interface. These methods are sometimes called virtual extension methods. This term arises from the idea of extending an existing interface so that it can acquire new methods without breaking existing code. The interface is said to have been extended. Virtual extension methods are also called **defender methods**.

Note: I will use the term, default methods, since we use the keyword **default** for default methods (in a similar way to how we use the **static** keyword for static methods). It can be argued that the addition of default methods to an interface corrupts the contract implied by the interface concept. In some sense, interfaces are no longer “pure”. Whether this change is for the better can be debated. Regardless, the use of default methods provides an additional technique that is available to developers.

Understanding the Importance of Default Methods

Default methods were introduced for several reasons:

- Existing code does not have to be updated to implement a new method. This allows for interfaces to grow or be extended.

- To provide additional flexibility in the design of an inheritance hierarchy such as:

-- Providing additional options in the placement of functionality within an interface hierarchy

-- Supporting interfaces that mimic adapter class type functionality

- To support lambda expressions

Private variables are still not permitted in an interface. In the previous example, the abstract method, hasBeenDrawn, implies the potential use of a state-like variable. However, any support for state information will have to be provided by the implementer of the interface.

Defining a Default Method

Let’s examine the details of creating and using a default method. The default keyword is always used to declare a default method. Technically, the keyword would not seem to be necessary. After all, it is clear from the existence of the method’s body that it is not abstract. The main reason it is required is to make it obvious that the method is implemented.

This is analogous to the use of the abstract keyword to declare abstract methods and classes. While an abstract method is obvious from its lack of a body, and an abstract class is obvious from the presence of abstract methods, the use of these keywords clarifies the intent. For example, the abstract keyword is not required to declare an abstract method in an interface. We could have declared the previous abstract method as follows:

public interface Drawable {

…

public boolean hasBeenDrawn();

}

![](image4.jpg)

However, we will use the abstract keyword, explicitly, to state our intent clearly.

The keyword default can be used in two places in the method’s declaration. Place the keyword either before, or after, any scope modifier. A scope modifier, while normally desirable, is not required. Possible placements of the keyword default are illustrated below:

public default void draw(){…}

default public void draw(){…}

default void draw(){…}

![](image5.jpg)

The term, default method, should not be confused with the idea that it is executed by default if no other methods are provided. In fact, an interface can have multiple default methods as shown below:

interface Drawable {

default void draw() {

System.out.println(

"The Drawable interface's draw method");

}

default void drawInQuotes() {

System.out.println(

"\"The Drawable interface's drawInQuotes method\"");

}

public abstract boolean hasBeenDrawn();

}

![](image6.jpg)

Both of these methods can be used from an implementing class as shown below:

Person person = new Person();

person.draw();

person.drawInQuotes();

![](image7.jpg)

The output is as follows:

The Drawable interface's draw method

"The Drawable interface's drawInQuotes method"

Overriding Default Methods

While a class must override abstract methods to avoid becoming abstract, default methods do not have to be overridden. They can be overridden as needed to provide an alternative implementation. In the following implementation of the Person class, an overridden draw method is provided:

interface Drawable {

public default void draw() {

System.out.println(

"The Drawable interface's draw method");

}

}

class Person implements Drawable {

@Override

public void draw() {

System.out.println("The Person's draw method");

}

}

![](image8.jpg)

While the @Overrride annotation is not required, it is a good programming practice to include it. When the draw method is now invoked, the Person class’ implementation is executed as shown below:

Person person = new Person();

person.draw();

![](image9.jpg)

The output follows:

The Person's draw method

If we want to use the default method’s implementation, from the class that implements the interface, we use the name of the interface followed by the keyword super and then the method name - all separated with periods. For the draw method, this is done as illustrated below:

class Person implements Drawable {

@Override

public void draw() {

Drawable.super.draw();

System.out.println("The Person's draw method");

}

}

![](image10.jpg)

The output shown below is based on the previous invocation of the draw method against the Person instance:

The Drawable interface's draw method

The Person's draw method

When overriding a default method in the implementing class, the keyword default cannot be used. For example, the following will not compile cleanly:

class Person implements Drawable {

@Override

public default void draw() {

System.out.println("The Person's draw method");

}

}

![](image11.jpg)

An error message similar to the following will be generated:

modifier default not allowed here

Using Inheritance with Default Methods

Interfaces can inherit from each other. Extensive hierarchies are possible including those that use multiple inheritance. As a result, default methods can be overridden in several places in a hierarchy. In this section, we will illustrate various inheritance alternatives and explain how the run-time system determines which overridden method to use.

Working with Single Inheritance

As with earlier versions of Java, interfaces can be derived from another interface. This is illustrated, below, where the Displayable interface derives from the Drawable interface. In this initial version, no methods have been added to the Displayable interface.

interface Drawable {

public default void draw() {

System.out.println(

"The Drawable interface's draw method");

}

}

public interface Displayable extends Drawable {

}

![](image12.jpg)

The Person class implements the Displayable interface as shown below:

public class Person implements Displayable {

}

![](image13.jpg)

These relationships are shown in Figure 1: Inheritance and Implementation Hierarchy Example. The solid line represents inheritance while the dashed line shows the Person class implementing the Displayable interface.

![](image14.jpg)

Figure 1: Inheritance and Implementation Hierarchy Example

When the draw method is executed against a Person instance, which does not override the draw method, the Drawable’s draw method is executed as shown below:

Person person = new Person();

person.draw();

![](image15.jpg)

The output is shown here:

The Drawable interface's draw method

We can override the draw method in the Displayable interface as shown below. Notice the use of the default keyword. It is required when we override a default method in interfaces.

interface Displayable extends Drawable {

public default void draw() {

System.out.println(

"The Displayable interface's draw method");

}

}

![](image16.jpg)

If the default keyword is left out, we get the following error message:

interface abstract methods cannot have body

The output of the draw method now reflects the overridden method as shown below:

The Displayable interface's draw method

It is possible to make a default method abstract in a hierarchy chain. Consider a third interface called MoreDisplayable as declared below. The draw method is overridden as an abstract method.

interface MoreDisplayable extends Displayable {

@Override

public abstract void draw();

}

![](image17.jpg)

When the Person class implements the MoreDisplayable interface it must implement the draw method. If it doesn’t, then the class must be declared as abstract.

public class Person implements MoreDisplayable {

}

![](image18.jpg)

The following error message will be generated if the class is not declared as abstract:

Person is not abstract and does not override abstract method draw() in MoreDisplayable

Working with Multiple Inheritance

The multiple inheritance of interfaces has always been possible in Java. This type of inheritance is one of behavior. However, Java still does not support multiple inheritance between classes. That type of inheritance is often referred to as inheritance of state.

Interfaces can inherit from more than one interface. However, if two or more of the base interfaces have the same default method, then ambiguity is introduced which needs to be addressed. To demonstrate how this is handled, we will explore an inheritance hierarchy where a MoreDisplayable interface is derived from both a Displayable and a Colorable interface as illustrated in Figure 2: Multiple Inheritance between Interfaces.

![](image19.jpg)

Figure 2: Multiple Inheritance between Interfaces

The first two interfaces are shown below:

public interface Displayable extends Drawable {

@Override

default void draw(){

System.out.println(

"The Displayable interface's draw method");

}

}

public interface Colorable {

public default void draw(){

System.out.println(

"The Colorable interface's draw method");

}   

}

![](image20.jpg)

A definition of the MoreDisplayable interface that extends both the Displayable and the Colorable interface is shown below. However, no implementation is provided for the draw method.

public interface MoreDisplayable extends Displayable,

Colorable {

}

![](image21.jpg)

This creates an ambiguous situation because the compiler is unable to determine which of the two base interfaces’ draw methods to use. This results in the following error message:

interface MoreDisplayable inherits unrelated defaults for draw() from types Displayable and Colorable

There are several ways of resolving this problem. One way is by providing an abstract declaration for the draw method as follows. This forces the implementing class to implement the abstract method.

public interface MoreDisplayable extends Displayable,

Colorable {

@Override

public abstract void draw();

}

![](image22.jpg)

Another approach is to use a concrete draw method:

public interface MoreDisplayable extends Displayable,

Colorable {

@Override

public default void draw() {

System.out.println(

"The MoreDisplayable interface's draw method");

}

}

![](image23.jpg)

If we want to use one of the base class’s draw methods we can explicitly call it as shown below:

public interface MoreDisplayable extends Displayable,

Colorable {

@Override

public default void draw() {

Displayable.super.draw();

}

}

![](image24.jpg)

Actually, both methods can be called if needed:

public interface MoreDisplayable extends Displayable,

Colorable {

@Override

public default void draw() {

Displayable.super.draw();

Colorable.super.draw();

}

}

![](image25.jpg)

The best solution is dependent on the needs of the application.

Understanding how Diamond Inheritance Works

Diamond inheritance occurs when one interface is the base interface for two other interfaces and a fourth interface is then derived from these two interfaces. Figure 3: Diamond Inheritance illustrates this situation where the Drawable interface serves as the base interface for the Displayable and the Colorable interfaces and the MoreDisplayable interface is derived from both the Displayable and the Colorable interfaces.

![](image26.jpg)

Figure 3: Diamond Inheritance

There are several places where the draw method can be declared. In the following set of declarations it is declared only in the Drawable interface:

public interface Drawable {

default void draw(){

System.out.println(

"The Drawable interface's draw method");

}

}

public interface Displayable extends Drawable { }

public interface Colorable extends Drawable { }

public interface MoreDisplayable extends Displayable,

Colorable { }

![](image27.jpg)

This will compile without errors. A similar situation occurs if a class implements both the Displayable and Colorable interfaces:

public class Busy implements Displayable, Colorable {

}

![](image28.jpg)

When an instance of Busy is created and the draw method is executed against this instance, the Drawable's draw method will be executed since it is the only one available. If the Displayable interface also implements the draw method, then its method will be used by the Busy class.

public interface Displayable extends Drawable {

@Override

default void draw(){

System.out.println(

"The Displayable interface's draw method");

}

}

![](image29.jpg)

If both the Displayable and Colorable interfaces implement the draw method, then we have the same ambiguous situation we had in the previous section. The compiler is unable to determine which draw method should be used. The Busy class will typically solve the problem by providing a draw implementation. One possible implementation is shown below:

public interface Colorable extends Drawable {

public default void draw(){

System.out.println(

"The Colorable interface's draw method");

}   

}

public class Busy implements Displayable, Colorable {

@Override

public void draw() {

Displayable.super.draw();

Colorable.super.draw();

}

}

![](image30.jpg)

If only the Drawable and the Displayable interfaces implement the draw method, the use of the draw method against the Busy class may not work as expected. In the following example a Busy instance is assigned to a Colorable interface reference variable:

Colorable colorable = new Busy();

colorable.draw();

![](image31.jpg)

It might be expected that the Drawable’s draw method would be called. However, the output shown below indicates otherwise:

The Displayable interface's draw method

The object referenced by the colorable variable is a Busy object and since the Busy class’ most immediate implementation of the draw method comes from the Displayable interface, that implementation is used.

Resolving Overridden Default Methods

When a default method is overridden in multiple places in a hierarchy, the run-time system needs to determine which method to use. A set of rules are used to resolve which method to use. To illustrate these rules we will use Figure 4: Resolving Overridden Default Methods that demonstrates single and multiple inheritance between interfaces and single inheritance between classes:

![](image32.jpg)

Figure 4: Resolving Overridden Default Methods

A class hierarchy is represented by the hierarchy of the classes Object, Entity, and Person. The Person class implements the MoreDisplayable interface which inherits from both the Displayable and the Colorable interfaces. The Displayable and Colorable interfaces both inherit from the Drawable interface.

When the run-time system tries to determine which method to execute, it will choose the method in the following order:

- The immediate class’ method

- Methods of the base classes (including those of the **Object** class)

- The most immediate default method of a possible hierarchy of interfaces

To illustrate these rules we will show various places where the display method could be implemented (and the effect the implementation has) when used against an instance of the Person class. This is based on the draw method being executed against an instance of Person as shown below:

Person p = new Person();

p.draw();

![](image33.jpg)

Table 1: Resolution Rules Example illustrates which draw method is used depending on where it is implemented:

***Table 1: Resolution Rules Example***

**If draw is implemented in |** And is not implemented in **| It will use the method in**

**Person** | Not applicable | **Person**

**Entity** | Person class | **Entity**

**Object** | Not possible | **Not** **possible**

**MoreDisplayable** | Person or Entity classes | **MoreDisplayable**

**Displayable** | Any class and not MoreDisplayable or Colorable | **Displayable**

**Colorable** | Any class and not MoreDisplayable or Displayable | **Colorable**

**Drawable** | Any other class or interface | **Drawable**

![](image34.jpg)

If the method is implemented in the Person class, then that implementation will always be used. If the method is not implemented there, then it will look to its base classes to find it. It will use the one in the Entity class if present. Since the Object class does not implement the draw method it will not find an implementation there.

If the method is not available in the class hierarchy, then it searches through the interface hierarchy. It will use the first implementation it finds, starting with the most derived interface first. In this case it will check to see if the MoreDisplayable interface has implemented it. If not then it will use either implementation found in the Displayable or Colorable interfaces. If both of these classes possess an implementation, then a compile error will result if the MoreDisplayable interface does not specify which one to use. This situation was discussed in the previous section. If only the Drawable interface implements the draw method, then this implementation will be used.

As demonstrated earlier, multiple implementations of the draw method can be used if an overridden method calls its immediate class or interface implementation.

This selection process can be summarized as:

- Classes take precedence over interfaces, and

- More specific interfaces (most derived) take precedence over less specific interfaces.

Using Default Methods

Default methods can be used in many situations. This section identifies and illustrates many of these possible uses. These include extending existing interfaces and supplementing adapter classes.

Extending Existing Interfaces

When adding a new abstract method to an existing interface, classes that have already implemented the interface will break since they no longer implement the new method. However, adding a default method will allow new methods to be added without breaking previous implementations. Traditionally, when an interface is defined it is treated as a contract and is not expected to change.

However, should the interface need to change, then the availability of default methods means that the interface can change and that change will not affect existing code. This permits existing interfaces to continue to be useable when new default methods are added. Older, existing usage of the interfaces does not break.

Consider the following interface that has a single abstract method draw:

interface Drawable {

public void draw();

}

![](image35.jpg)

When a class such as Person implements that interface it only needs to implement the draw method:

class Person implements Drawable {

public void draw() {

System.out.println("The Person's draw method");

}

}

![](image36.jpg)

However, if we add another abstract method to the Drawable interface, such as a drawWithQuotes method as shown below, we will introduce errors into the Person class:

interface Drawable {

public void draw();

public void drawWithQuotes();

}

![](image37.jpg)

The error message will be:

Person is not abstract and does not override abstract method drawWithQuotes() in Drawable

We are not able to easily add new methods without breaking old code written prior to Java 8\. If, instead, we use a default method in the Drawable interface as follows, the error goes away. Our code will compile and execute correctly.

interface Drawable {

public void draw();

public default void drawWithQuotes() { }

}

![](image38.jpg)

Using Default Methods to Supplement Adapter Classes

While classes such as the MouseMotionAdapter class have not been replaced with default method interface implementations, it is possible to provide similar functionality using default methods. As an example, consider a MouseMotionAdapter interface equivalent. A simplified version of the MouseMotionAdapter source code, as found in Java 8, is shown below:

public abstract class MouseMotionAdapter implements MouseMotionListener {

public void mouseDragged(MouseEvent e) {};

public void mouseMoved(MouseEvent e) {};

}

![](image39.jpg)

An “equivalent” interface could appear as follows:

public interface MouseMotionAdapterInterface extends MouseMotionListener {

public default void mouseDragged(MouseEvent e) { };

public default void mouseMoved(MouseEvent e) { };

}

![](image40.jpg)

As example of using the MouseMotionAdapter follows. This code will print the current x coordinate of the mouse as the mouse moves across the window.

public static void main(String[] args) {

JFrame frame = new JFrame();

frame.addMouseMotionListener(new MouseMotionAdapter() {

public void mouseMoved(MouseEvent e) {

System.out.println(e.getX());

}

});

frame.setBounds(100, 100, 500, 300);

frame.setVisible(true);

}

![](image41.jpg)

To demonstrate the use of the MouseMotionAdapterInterface we will use the following code. The code is equivalent to the previous example except that an instance of the MouseMotionAdapterInterface interface is used instead of MouseMotionAdapter. Otherwise, the code behaves in the same way.

public static void main(String[] args) {

JFrame frame = new JFrame();

frame.addMouseMotionListener(

new MouseMotionAdapterInterface() {

public void mouseMoved(MouseEvent e) {

System.out.println(e.getX());

}

});

frame.setBounds(100, 100, 500, 300);

frame.setVisible(true);   

}

![](image42.jpg)

The major difference is found in any implementation provided by the default method. If needed, we can add default behavior to default methods such as code to support logging.

Using Default Methods in Core Java Classes

The addition of lambda expressions is a major change to Java 8\. For the developer to take advantage of this feature and yet still use interfaces, such as those of the collection libraries, it is desirable to use default methods to extend the interfaces.

As an example, the default forEach method has been added to the java.lang.Iterable interface as shown below. This method accepts an object that implements the Consumer functional interface. The forEach method will iterate through each element of the list and apply the Consumer instance’s accept method against each element. The Objects class’ requireNonNull method, added with Java 7, validates that the action object is not null.

public interface Iterable<T> {

Iterator<T>iterator();

default void forEach(Consumer<? super T> action) {

Objects.requireNonNull(action);

for (T t : this) {

action.accept(t);

}

}

…

}

![](image43.jpg)

We can now use the accept method with new code without breaking existing code. In the following example the Person class has been modified with the addition of a name field and supporting methods:

public class Person {

String name;

int age;

public Person(String name, int age) {

this.name = name;

this.age = age;

}

@Override

public String toString() {

return "Person{" + "name=" + name +

", age=" + age + '}';

}

}

![](image44.jpg)

An ArrayList, which implements the Iterable interface, can use the forEach method to iterate through the list as shown below. A list of persons is created. The forEach method is then executed against the list. This example uses a lambda expression for the argument of the forEach method. While the lambda expression is not explained here, the effect is that each person in the list will be displayed by calling its toString method.

ArrayList<Person> roster = new ArrayList();

roster.add(new Person("Ralph", 45));

roster.add(new Person("Tom", 22));

roster.add(new Person("Mary", 31));

roster.forEach(person -> System.out.println(person));

![](image45.jpg)

The output of this sequence follows:

Person{name=Ralph, age=45}

Person{name=Tom, age=22}

Person{name=Mary, age=31}

This is easier than using the for each statement.

The Collection interface’s parallelStream method is another example of a default method, as shown below. The concept of Streams will be discussed in detail in Chapter 3.

public interface Collection<E> extends Iterable<E> {

...

default Stream<E>parallelStream() {

returnStreamSupport.stream(spliterator(), true);

}

}

![](image46.jpg)

Programmers can take advantage of these default method additions without the need to modify existing code. In the case of streams, it has the potential advantage of enhanced performance on multi-core machines.

Using a Class to Support Default Methods

Here we will illustrate how a class and interface can work together to support a state. This version of the Drawable interface uses two abstract and two default methods: draw and isNotDrawable. The default methods are dependent on the implementation of the abstract methods of the implementing class. The getString method should return the string used by the draw method. The isDrawable and isNotDrawable methods are intended to determine if the subject is, in fact, drawable.

interface Drawable {

public abstract String getString();

default void draw() {

System.out.println(getString());

}

abstract boolean isDrawable();

default boolean isNotDrawable() {

return !isDrawable();

}

}

![](image47.jpg)

The following illustrates an implementation of the Person class where two abstract methods have been implemented:

class Person implements Drawable {

public String getString() {

return "Person";

}

public boolean isDrawable() {

return true;

}

}

![](image48.jpg)

To test this implementation we use the following:

Person person = new Person();

person.draw();

System.out.println(person.isNotDrawable());

![](image49.jpg)

The output follows:

Person

false

Understanding the Difference between an Abstract Class and Interfaces

Abstract classes and interfaces with default methods may appear to be the same but there are several differences between them. These are summarized in Table 2: Abstract Class versus Interface. A class can only extend one class while multiple inheritance is supported between interfaces. State information is contained in instance variables. These are not allowed in interfaces. While we haven’t discussed lambda expressions in detail, yet, an instance of a functional interface can be used with lambda expressions. This is not possible with abstract classes.

The decision to use an abstract class versus an interface is dependent on the needs of your application.

***Table 2: Abstract Class versus Interface***

**Characteristic** | Abstract Class | **Interface**

**Supports multiple inheritance** | No | **Yes**

**Can have a constructor** | Yes | **No**

**Can have a state** | Yes | **No**

**Can be used with lambda expressions** | No | **Yes**

![](image50.jpg)

Using Static Interface Methods

Static methods can be added to interfaces in Java 8\. The following illustrates the use of a static method in the Drawable interface. In this example, the getStandardUnit method is intended to return the standard unit of measure.

enum Unit {pixel, inch, millimeter};

interface Drawable {

public default void draw(){

System.out.println(

"The Drawable interface's draw method");

}

public static Unit getStandardUnit() {

return Unit.pixel;

}

}

![](image51.jpg)

The following illustrates the use of this interface where the Shape class implements the Drawable interface:

class Shape implements Drawable {}

public class TestExample {   

public TestExample() {

Shape shape = new Shape();

shape.draw();

System.out.println(Drawable.getStandardUnit());

}

}

![](image52.jpg)

The output follows:

The Drawable interface's draw method

Pixel

Though the Shape class implements the Drawable interface, it does not possess the static method getStandardUnit. The following illustrates an attempt to use it:

System.out.println(Shape.getStandardUnit());

![](image53.jpg)

This will result in the following syntax error message:

cannot find symbol

symbol:   method getStandardUnit()

location: class Shape

The addition of static methods to interfaces eliminates the need to create a helper class whose sole purpose is to provide static methods. They can now be integrated into the interface. The following illustrates the creation of the Drawable interface and a helper class that would be needed if default methods were not used:

enum Unit {pixel, inch, millimeter};

public interface Drawable {

... 

}

class DrawableHelper {

public static Unit getStandardUnit() {

return Unit.pixel;

}

}

![](image54.jpg)

We can then use the class as follows:

Shape shape = new Shape();

shape.draw();

System.out.println(DrawableHelper.getStandardUnit());

![](image55.jpg)

While it takes the same number of statements to use the static method, we had to create an additional class with this approach.

Functional Interfaces

Functional interfaces are interfaces that have one, and only one, abstract method. However, these interfaces can have any number of default methods. Since there is only one abstract method, the compiler knows that that method will be the one used in certain situations. The existence of a single abstract method enables them to be used in interesting and powerful ways as exemplified by lambda expressions. As we will see, since a functional interface has only one abstract method, a lambda expression that matches the abstract method, can be used easily. This abstract method is referred to as the functional method.

In this section, we will learn more about functional expressions including the use of the @FunctionalInterface notation and how they have been incorporated into the Java core libraries. Detailed discussion of lambda expressions is postponed until Chapter 2.

Technically, a functional interface has one and only one non-Object method. As discussed in the Overriding Object Class Methods in a Functional Interface section, it is possible to override an Object method as abstract thus introducing more than one abstract method in a functional interface.

Creating a Functional Interface

The following illustrates a simple functional interface. It consists of a single abstract method.

public interface Drawable {

public abstract void draw();   

}

![](image56.jpg)

A functional interface can remain a functional interface and yet have one or more non-abstract methods as illustrated below:

public interface Drawable {

public abstract void draw();

public default boolean hasBeenDrawn() {

return true;

}

}

![](image57.jpg)

The abstract method of a functional interface is called the functional method. In the previous example, the draw method is the functional method.

A function descriptor is the method type of the functional method. It consists of the parameter types, return type, and any exceptions thrown by that functional method. In the previous example, its method type consists of a method with no parameters, no return type, and it does not throw an exception. It is about as simple as things get. As we will see in Chapter 2, a function descriptor is represented by a lambda expression. The lambda expression is then matched against a functional method.

Using  the @FunctionalInterface Annotation

The @FunctionalInterface annotation is available to inform the compiler that the interface should contain a single abstract function. The following illustrates its use:

@FunctionalInterface

public interface Drawable {

public abstract  void draw();

}

![](image58.jpg)

The next three Drawable interface declarations illustrate invalid functional interfaces. In the first two declarations, the interfaces do not possess an abstract method:

@FunctionalInterface

interface Drawable {

public default void draw() {

System.out.println(

"The Drawable interface's draw method");

}

}

@FunctionalInterface

public interface Drawable {

}

![](image59.jpg)

The error message generated for both of these examples is the same:

Unexpected @FunctionalInterface annotation

Drawable is not a functional interface

no abstract method found in interface Drawable

In this declaration, the interface has more than one abstract method:

@FunctionalInterface

interface Drawable {

public abstract String getValue();

public abstract booleanhasBeenDrawn ();

}

![](image60.jpg)

The error message generated is shown below:

Unexpected @FunctionalInterface annotation

Drawable is not a functional interface

multiple non-overriding abstract methods found in interface Drawable

The @FunctionalInterface annotation is not required. If it is not used with an interface that is a functional interface, the compiler will still treat it as a functional interface.

Overriding Object Class Methods in a Functional Interface

All interfaces implicitly declare abstract methods of Object class methods. It is also possible to explicitly declare an abstract method from the Object class in an interface. These methods do not count toward the number of abstract methods in an interface.

For example, although the java.util package’s Comparator interface is a functional interface, it has two abstract methods: a compare and an equals abstract method. The equals method effectively overrides the Object class’ equals method.

The following illustrates how the equals method is used to add a second abstract method to the Drawable interface:

@FunctionalInterface

public interface Drawable {

public abstract boolean hasBeenDrawn();

@Override

public abstract boolean equals(Object obj);

}

![](image61.jpg)

An interface cannot declare, as a default method, any of the methods of the Object class. This includes the commonly used equals, hashCode, and toString methods. In general, overriding a method of the Object class is not always a good idea nor is necessary.

Using Functional Interfaces in the Core Libraries

Functional interfaces have always been part of Java but have not been explicitly called functional interfaces. For example, interfaces such as ActionListener and Runnable, shown below, are functional interfaces:

public interface ActionListener extends EventListener {

public void actionPerformed(ActionEvent e);

}

public interface Runnable {

public abstract void run();

}

![](image62.jpg)

In Java 8 many new functional interfaces have been added. Several have been added to the new java.util.function package to address common programmer needs. For example, the Predicate interface is used to support test cases that evaluate to true or false. Its functional method is test. It has a single generic argument and returns a boolean value.

boolean test(T t);

![](image63.jpg)

A more detailed discussion of these functional interfaces is found in Chapter 2.

Conclusion

In this chapter, we have focused on the use of default methods and functional interfaces. Default methods are methods of an interface that have an implementation. This feature has been added to allow interfaces to grow over time without breaking existing uses of the interface. The keyword default is used to declare such a method.

With the addition of default methods, we have to consider how overridden default methods are handled in single and multiple inheritance situations. Class implementations take precedence over interface implementations. The most derived method’s default method takes precedence over base interface default method implementations.

Functional interfaces are interfaces that have one, and only one, abstract method. These are used to support lambda expressions. The abstract method of a functional interface is called the functional method. This method has a function description associated with it that provides a target signature used with lambda expression.

The @FunctionalInterface annotation has been added to Java 8 to indicate that an interface is intended to be a functional interface. However, a functional interface does not require this annotation.

In the next chapter we examine the use of functional interfaces and their use with lambda expressions. We will also explore the new java.util.function package that introduces a number of functional interfaces.

* * * * *

Chapter 2 – Lambda Expressions

-Understanding Lambda Expressions

--Inferring the Type of the Target

-Creating Lambda Expressions

--Lambda Expression Syntax Rules

---Declaring Parameter Types

---Mixing Parameter Declarations

---Omitting Parentheses

---Eliminating the Block Statement

---Using Multiple Statements in a Lambda Expression Body

---Using a Return Value

--Writing Succinct Lambda Expressions

--Capturing Variables in a Lambda Expression

--Differentiating between a Lambda Expression and a Closure

--Method and Constructor References

---Using Static Method References

---Using Instance Method References

---Using Constructor References

-Working with Lambda Expressions

--Using Lambda Expressions with Variable Declarations

--Using Lambda Expressions as a Return Value

--Using Exceptions with a Lambda Expression

--Using Lambda Expressions with the Tertiary Operator

--Casting Lambda Expressions

--Using Lambda Expressions to Initialize an Array

--Writing Recursive Lambda Expressions

-Using the java.util.function Functional Interfaces

--Using the Predicate Interface

--Using the Function Interface

--Using the BiFunction Interface

--Using the Consumer Interface

--Using the Supplier Interface

--Using Operator Type Interfaces

--Using the UnaryOperator Interface

--Using the BinaryOperator Interface

-Conclusion

The addition of lambda expressions to Java 8 is a step toward - encouraging the use of function programming techniques in Java applications. A functional style programming orientation places emphasis on using simple functions in various contexts. The use of function programming can result in better and less error prone code in many situations. This style of programming has been integrated with the object oriented nature of Java. It is also reflected in how core libraries are organized.

Lambda constructs are found in a number of other programming languages. It was felt that Java could also benefit by adding a functional programming aspect to the language which enables the use of concise and elegant expressions. Lambda expressions also allow a function to be used as a method argument. This treats code as data.

Lambda expressions eliminate the need to use anonymous inner classes in many situations. There is a lot of boiler plate code used with anonymous inner classes. After a while they all seem to look a lot alike, and, typically, they have a single method that is being overridden. Using lambda expressions means that more compact code can be used. In addition, their use also avoids the confusion that can occur when using the this keyword and the problems of accessing non-final variables.

The use of lambda expressions helps distinguish between *what* should be done versus *how* it is done. The *what* is expressed in the expression proper. The *how* is determined in the implementation. This is typified by the use of lambda expressions with streams, which can be used to implement the functionality in a sequential or concurrent manner.  Streams are discussed in Chapter 3.

Multiple core systems are supported by allowing elements of a collection to be processed by functions without the developer needing to worry about how to explicitly implement concurrent behavior. The Stream interface along with the use of the forEach method, in conjunction with lambda expressions, can take advantage of multiple cores.

When lambda expressions are compiled, they use the invokedynamic JVM instruction added to Java 7\. As a result, the compiler is able to generate shorter byte code sequences. This translates to better performance than equivalent code which did not use lambda expressions.

In this chapter, we will show how lambda expressions can be created and used in a variety of contexts. Lambda expression syntax variations are fully explored so that one can fully understand how they can be written. The concept of closure and its relationship to lambda expressions will be discussed. We will also see how method and constructor references can be used as lambda expressions.

The last section of the chapter explores the java.util.function package. This package contains a number of useful functional interfaces that are used with lambda expressions. Understanding these interfaces is especially important when they are used with the Stream interface.

Note: The mathematician Alonzo Church developed the concept of lambda expressions as part of a model of computation. He used the Greek letter lambda to represent this abstraction. The name has stuck.

Understanding Lambda Expressions

A lambda expression can be thought of as an anonymous function. When we think of a function, a common image of a square root function might come to mind. We pass it a number and it returns a number.

A guiding force behind lambda expressions is to make these expressions as simple to use as possible. What is the simplest form of a function? Well, one version of a simple square function follows:

int square(int num) {

return num*num;

}

![](image64.jpg)

If we ignore the data types and leave off the name, we can conceivably write it as:

num {return num*num;}

![](image65.jpg)

Since we know the function will return a value, there is no need for the return keyword, at least with this function. Also there is no need for a block statement since there is only one statement being used. We still need to separate the parameter from the function’s body. This can be done using the lambda operator (->), sometimes called the arrow token, as shown below:

num -> num*num

![](image66.jpg)

This is our lambda expression. It represents a simple way of writing a function. Here is another simple lambda expression. This one is passed a single value to be displayed and nothing is returned.

x -> System.out.println(x)

![](image67.jpg)

Where do we use a lambda expression? You can use a lambda expression anywhere a functional interface is expected. A functional interface is an interface that has one and only one abstract method. This method is called the functional method. These concepts were discussed in Chapter 1.

To illustrate, we will use a lambda expression as the argument of the forEach method. This method expects an instance of the java.util.function.Consumer functional interface. Its abstract method is the accept method which accepts an object and returns void.

The forEach method has been added to a number of interfaces in Java 8 including the Iterable interface.  Any sub-interfaces or implementing classes of the Iterable interface will possess this method. This includes quite a few interfaces and classes including: List, HashSet, and Linkedlist.

In the following example, a List is created based on a series of numbers:

List<Integer> list = Arrays.asList(5,3,4);

![](image68.jpg)

The lambda expression is used below to display each element of the list:

 list.forEach((Integer element)->System.out.println(element));

![](image69.jpg)

The output of this code sequence follows:

5

3

4

What is happening here? When the compiler examines the statement it expects an instance of an Iterable. However, what it finds is the lambda expression. It then tries to convert the lambda expression into the needed object. It decides it can do this since only a single argument is passed and nothing is returned. It matches the signature of the accept method. Since list is a set of integers, it decides the parameter type should be Integer. This process is called target typing and is discussed in depth in the next section.

You can envision the compiler generating an anonymous inner class implementation for the previous example similar to the following:

list.forEach(new Consumer() {

@Override

public void accept(Object element) {

System.out.println(element);

}

});

![](image70.jpg)

However, a more concise and ultimately more efficient approach uses a lambda expression as follows:

list.forEach((element)->System.out.println(element));

![](image71.jpg)

This implies an object is created. Whether or not this actually happens is an implementation issue. It is more useful to think of lambda expressions as anonymous functions.

While functions and methods are similar, a function is not tied to a class.  Lambda expressions are conceptually a simple concept. However, their syntax can be cryptic until fully understood. They represent a powerful new tool to develop Java applications.

Inferring the Type of the Target

Target typing is the process of inferring the type of an object based on the context in which it is being used. We saw this occur in the previous example. Type referencing occurs when the system determines the type of the lambda expression. The type is inferred from the expression. This is possible because Java knows the expected parameter type for the functional interface’s abstract method.

A lambda expression does not contain information about which functional interface it is implementing. The context of the lambda expression determines which functional interface it represents. For example, the following lambda expression accepts a single value and returns its square:

x -> x * x

![](image72.jpg)

The following functional interface definitions both have a single abstract method that accepts a single value and returns a value:

interface IntegerSquare {

int square(int x);

}

interface DoubleSquare {

double square(double x);

}

![](image73.jpg)

However, either of the next two assignments will work. We are assigning a lambda expression to a functional interface variable, which matches both of the abstract method’s signature.

IntegerSquare intSquare = x -> x * x;

DoubleSquare doubleSquare = x -> x * x;       

![](image74.jpg)

Here is a complete example:

public class LambdaExpressionExamples {

public static void main(String[] args) {

IntegerSquare intSquare = x -> x * x;

DoubleSquare doubleSquare = x -> x * x;

System.out.println(intSquare.square(5));

System.out.println(doubleSquare.square(5));

}   

}

![](image75.jpg)

The output of this sequence follows:

25

25.0   

Let’s reexamine the following statement:

IntegerSquare intSquare = x -> x * x;

![](image76.jpg)

The left-hand side of this expression is an IntegerSquare and is referred to as the lambda expression’s target type. The target type is the data type expected in a given context. The target type for a lambda expression must be:

- A functional interface

- Have compatible parameter types as the interface’s function descriptor

- Have a return type compatible with the return type of the interface’s function descriptor

- Throw only those exceptions permitted by the function descriptor

As a reminder, a function descriptor is the method type of the functional method. It consists of the parameter types, return type, and any exceptions thrown by the method.

We can also use generic definitions of functional interfaces. To illustrate this we will use the ComputableType interface as shown here:

interface ComputableType<T> {

T compute(T x);

}

![](image77.jpg)

In the next example, we declare two variables based on this interface. The first is of type Integer while the second is of type Double. The examples illustrate assigning lambda expressions to each variable using both implicit and explicit parameter declarations.

ComputableType<Integer> computableInteger;

computableInteger = (Integer x) -> x * x;

computableInteger = (x) -> x * x;

ComputableType<Double> computableDouble;

computableDouble = (Double x) -> x * x;

computableDouble = (x) -> x * x;

![](image78.jpg)

The last statement in each group is identical except for the variable the expression is being assigned to. In these cases the compiler is able to determine the type to use. The expression is being assigned to two different targets. This is another example of target typing.

While lambda expressions can be considered objects, they do not necessarily assign a unique identifier. This is a design decision which will provide Java architects with flexibility in how lambda expressions may evolve in future versions of Java. As a result, the use of the equality operator and the equals method (inherited from Object) will not always perform as expected. Consider the following declaration:

ComputableType<Integer> ci1;

![](image79.jpg)

Both of the following comparisons will generate syntax errors:

if(ci1 == (x) -> x * x) { }

if(ci1 == ((x) -> x * x)) { }

![](image80.jpg)

The message generated follows:

lambda expression not expected here

bad operand types for binary operator '=='

first type:  ComputableType<Integer>

second type: <none>

We can eliminate this syntax error by casting the lambda expression using ComputableType<Integer> as shown below. In this example, we also perform comparisons between two ComputableType variables to determine how they behave.

ComputableType<Integer> ci1;

ComputableType<Integer> ci2;

ci1 = (x) -> x * x;

ci2 = (x) -> x * x;

System.out.println(ci1 ==

(ComputableType<Integer>)(x) -> x * x);

System.out.println(ci1.equals(

(ComputableType<Integer>)(x) -> x * x));

System.out.println(ci1 == ci2);

System.out.println(ci1.equals(ci2));

ci2 = ci1;

System.out.println(ci1 == ci2);

System.out.println(ci1.equals(ci2));

![](image81.jpg)

The output follows:

false

false

false

false

true

true

Comparison of lambda expressions will not always work as one might expect.

Creating Lambda Expressions

In this section, we will see how lambda expressions are created and examine lambda expression syntax issues. The basic syntax of a lambda expression follows:

(parameter) -> expression

(parameters) -> { statements;}

![](image82.jpg)

A lambda expression consists of the following element sequence:

- Parameter list

- The lambda operator (->)

- A body which is either a single statement or a statement block

The parameter list is typically a comma-delineated list of formal parameters enclosed in parentheses. The parameter list does not necessarily require:

- A data type, or

- A set of parentheses

The parameter type may be declared explicitly or may be inferred from its context. Lambda expression can take on several forms. Table 1: Lambda Expression Forms illustrate various combinations of input and return values.

*Table 1: Lambda Expression Forms*

**Number of Parameters** | Number of Return Values | **Example**

**0** | 0 | **() -> System.out.println("")**

**0** | 1 | **() -> 45**

**1** | 0 | **(x) -> System.out.println(x)**

**1** | 1 | **(x) -> x * x**

**Multiple** | 0 | **(x, y) -> System.out.println(x + y)**

**Multiple** | 1 | **(x, y) -> x + y**

![](image83.jpg)

Lambda Expression Syntax Rules

The following rules summarize how lambda expressions can be written:

- Parameter types may be explicitly or implicitly declared

- Parentheses may be omitted when a single implicitly declared parameter is used

-- However, they cannot be mixed in the same expression

- A single value does not have to be enclosed in a block statement

- Multiple statements in a lambda expression must be enclosed in a block statement

- A block body may return a value or nothing

- The rules for using the return keyword are the same as for a method

We will examine the details of these rules and illustrate their numerous variations.

Declaring Parameter Types

In the first expression, the parameter x, is declared explicitly. In the second expression, its type is implied.

(Integer x) -> System.out.println(x)

(x) -> System.out.println(x)

![](image84.jpg)

In the case of the implicitly declared variable, target typing comes into play.

Mixing Parameter Declarations

Let’s start with a functional interface definition:

interface IntegerMathType<T> {

T compute(T x, T y);

}

![](image85.jpg)

The next two expressions illustrate the use of explicit parameter declarations. The first expression uses two declared parameters and is legal. The second expression is illegal because one parameter is declared explicitly while the second is declared implicitly.

IntegerMathType<Integer> addition =

 (Integer a, Integer b) -> {return a + b;};

IntegerMathType<Integer> addition =

 (Integer a, b) -> {return a + b;}; // Illegal

![](image86.jpg)

The error message generated for the second expression is as follows:

<identifier> expected

incompatible types: incompatible parameter types in lambda expression

Omitting Parentheses

Parentheses can be omitted in some situations. Consider the following declaration of the functional interface ComputableType:

interface ComputableType<T> {

T compute(T x);

}

![](image87.jpg)

Consider the following declaration:

ComputableType<Integer> computable;

![](image88.jpg)

We can assign a simple lambda expression with an explicit parameter as follows. The parameter also uses parentheses.

computable = (Integer x) -> x * x;

![](image89.jpg)

We can simplify the assignment as follows. The data type and parentheses are left out.

computable = x -> x * x;

![](image90.jpg)

If the lambda expression has a single parameter, then the parentheses can be omitted. The type can also be omitted as Java will infer its type. However, you cannot leave off parentheses and keep the data type as illustrated below:

computable = (Integer x) -> x * x;

computable = Integer x -> x * x;    // Invalid

![](image91.jpg)

The error message generated is as follows:

';' expected

not a statement

In the next example, multiple parameters are declared explicitly and implicitly in the first two lambda expressions. However, the third expression explicitly declares the parameter but does not use parentheses and is thus illegal.

(int x, int y) -> x*y

(x, y) -> x*y

int x, int y -> x*y // illegal

![](image92.jpg)

The error message generated is as follows:

';' expected

not a statement

Eliminating the Block Statement

A block statement is not always necessary. In the following example the first lambda expression uses a single input parameter and returns a single value, the square of the argument. In the second lambda expression the sum of the two parameters is returned. Neither expression uses a block statement.

(x) -> x * x

(x, y) -> x + y

![](image93.jpg)

Also, a single line lambda expression that returns void does not have to be enclosed in a block statement.

Using Multiple Statements in a Lambda Expression Body

Multiple statements can be used in the body of a lambda expression. To illustrate how this is done, we will use the ComputableType interface we declared earlier:

computable = (x) -> {

int y = x * x;

y += x + x;

return y;

};

![](image94.jpg)

Using a Return Value

A block body may return a value or nothing. When a value is returned, the return keyword does not necessarily need to be used. In most contexts it is implied. The following lambda expression returns nothing so the return keyword cannot be used:

(x) -> System.out.println(x)

![](image95.jpg)

This next lambda expression returns a single value. The return keyword must be used when a value is returned and a block statement is present.

computable = (x) -> {return x * x;};

![](image96.jpg)

In this example the return keyword is left out:

addition = (a, b) -> {a + b;};

![](image97.jpg)

It will generate the following error message:

not a statement

incompatible types: bad return type in lambda expression

missing return value

Writing Succinct Lambda Expressions

Creating short easy-to-write lambda expressions is a desirable goal as long as it doesn’t become too cryptic. The following are some guidelines as to how to write succinct expressions:

- When a single parameter is used, do not use parentheses

- Do not use parameter types if possible

- Avoid using a block statement

A valid but verbose expression is shown below:

(Integer x) -> {System.out.println(x);}

![](image98.jpg)

An equivalent but simpler expression follows:

x -> System.out.println(x)

![](image99.jpg)

By removing the parameter type and the parentheses, we simplify the first part of the lambda expression. The block statement is not required so it was also removed.

However, some IDEs may suggest that a block be used with a lambda body or to use explicit parameters if the interface is generic. For example, let’s start with the definition of a ComputableType interface as follows:

interface ComputableType<T> {

T compute(T x);

}

![](image100.jpg)

A variable of this type is declared below and then assigned a lambda expression:

ComputableType<Integer> computableType ;

computableType = (x) -> x * x;

![](image101.jpg)

An IDE may offer suggestions to make this more readable. The equivalent declaration using a body and then explicit parameters to satisfy an IDE suggestion are shown below:

ComputableType<Integer> computable;

// Using a block as a lambda body

computable = (x) -> {

return x * x;

};

// Using explicit parameters

computable = (Integer x) -> x * x;

![](image102.jpg)

If we had used the non-generic Computable interface as declared below, we would not have been presented with these suggestions.

interface Computable {

int compute(int x);

}

Computable computable;

computable = (x) -> x * x;

![](image103.jpg)

However, it is illegal to use parameters with this lambda expression since the interface is not generic. The following illustrates an attempt to use an Integer type:

computable = (Integer x) -> x * x;  // illegal

![](image104.jpg)

An error message similar to the following will be generated:

incompatible types: incompatible parameter types in lambda expression

computable = (Integer x) -> x * x;  // illegal

Capturing Variables in a Lambda Expression

In this section, we will examine the techniques that are used to access variables within a lambda expression. Using variables in the defining context is called variable capture. A lambda expression can only access final or effectively final variables in its defining context. Effectively final means that declaring the variable as final would not cause an error if the code is compiled.

Lambda expressions can refer to local variables that are not declared as final but are never modified. However, they cannot redefine them. This addresses a limitation of anonymous inner classes that requires local variables it uses to be declared as final. Also, the use of the this and super keywords are permitted.

To summarize the rules, lambda expressions can:

- Use final variables

- Use effectively final variables

- Cannot modify local or parameters variables

- Cannot redefine local or parameter variables

- Can use this and the super keywords

We will use the following class to demonstrate how variables can be captured in a lambda expression. The IntegerMath functional interface is defined and then used in the test method. The test method creates and returns a lambda expression that uses a series of variables to calculate a sum. The lambda expression is later executed in a separate thread.

interface IntegerMath {

int operation(int a, int b);

}

public class VariableCapture implements Runnable {

private int instanceVariable = 5;

static IntegerMath le;

public static void main(String args[]) {

VariableCapture vc = new VariableCapture();

le = vc.test(15);

Thread thread = new Thread(vc);

thread.start();

}

public IntegerMath test(int parameter) {

int localVariable = 10;

final int finalVariable = 30;

IntegerMath testExpression = (x, y) -> {

return x + y

+ instanceVariable

+ parameter

+ localVariable

+ finalVariable;

};

return testExpression;

}

@Override

public void run() {

System.out.println(le.operation(25, 5));

}

}

![](image105.jpg)

The output of this program will be 90.

The lambda expression is able to access the variables in its context. However, if the localVariable or parameter variables are modified they are no longer effectively final and a syntax error is generated. The error message generated for both of these modifications follows:

local variables referenced from a lambda expression must be final or effectively final

It doesn’t matter where the variables are modified. They simply cannot be changed. The instanceVariable can be modified if needed.

We could have used the this keyword in the lambda expression as follows. There are no restrictions on its use.

+ this.instanceVariable

![](image106.jpg)

The super keyword can also be used to access base class members.

An attempt to redefine localVariable or parameter within the lambda expression will result in an error message:

variable index is already defined in method testCapture ()

Using effectively final variables eliminates certain types of multithreading errors which involve local variables. Since a lambda expression may be defined in one context, but executed in a different context (thread), using effectively final variables eliminates problems that can occur with mutable variables shared between threads.

If a mutable variable was used, and if the computation were distributed across multiple threads, such as with the forEach method, these variables would need to be synchronized with its associated overhead. The intent of restricting access to effectively final variables is to force the programmer to focus on easily parallelizable and thread-safe techniques.

Differentiating between a Lambda Expression and a Closure

A closure and a lambda expression are essentially the same thing in Java. A lambda expression is an anonymous function. A closure is a function that closes over its environment. Closing over its environment means that it is able to access variables which are not in its parameter list. A closure consists of code bound to a set of variables. In Java, lambda expressions are implemented using closure which implies we can treat the two terms interchangeably.

When a lambda expression is evaluated, it uses the context in which it was defined, not where it is being used. If a lambda expression is defined in the context of a specific stack, it will be executed in the context of that stack even if it is being used within another stack. Passing a closure between execution contexts (threads) permits the evaluation of the expression in the environment it was defined in.

While an object is an instance of a class, a closure is an implementation of a lambda expression. When a lambda expression is compiled, an object representing that lambda expression type is created at run-time. While lambda expressions can be viewed as objects, they are better thought of as functions.

Method and Constructor References

There are times when it is useful to treat a class method as a lambda expression. If the functionality needed is already implemented by a method, why not use the method instead of creating a new lambda expression? Method references provide a compact way of identifying and using existing methods of a class.  In other words, a method reference is a technique to identify and reference lambda expressions that happen to have a name.

A method reference consists of a class name followed by two colons and then by the name of a method or the keyword **new** for constructor references. Table 2: Examples of Method/Constructor References illustrates simple examples of method references. The last example is a constructor reference.

***Table 2: Examples of Method/Constructor References***

**Method Reference** | Equivalent Lambda Expression

**System.out::println** | (s) -> System.out.println(s)

**Person::toString** | s->s.toString()

**String::indexOf** | x->String.indexOf(x)

**Math::sin** | x->Math.sin(x)

**ArrayList::new** | () -> new ArrayList<>()

![](image107.jpg)

Using the println method as a method reference can save the effort required to create a lambda expression as shown below. This example will display each element of the list one number per line.

List<Integer> list = Arrays.asList(-5, -3, 4);

list.forEach(System.out::println);

![](image108.jpg)

This is equivalent to the following:

list.forEach(s -> System.out.println(s));

![](image109.jpg)

There are four basic types of method references:

- Static method references

- Instance method references (specific object)

- Instance method references (arbitrary object of a specific type)

- Constructor references

When using method references, as with lambda expressions, the function must match the signature of the functional method. The type of the reference is dependent on its context.

Let’s examine the following method reference:

Math::sin              // Equivalent to  x->Math.sin(x)

![](image110.jpg)

While the Math class does not constitute a functional interface, the sin method can be used where a lambda expression accepts a double and returns a double. The sin method can be applied against such a functional interface instance. The method itself is treated as a function.

Using Static Method References

One characteristic of static reference methods is that they cannot capture instance variables for the same reason a static method cannot access an instance variable. To demonstrate the use of a static reference we will create a static display method that applies an operation against each element and then displays the result of this operation. A static square method is used for the method reference.

interface Computable {

int compute(int x);

}

public class MethodReferenceExample {

public static void main(String[] args) {

List<Integer> list = Arrays.asList(-5, -3, 4);      

display(list, MethodReferenceExample::square);

}

public static int square(int num) {

return num*num;

}

private static void display(List<Integer> list,

Computable operation) {

for(Integer element : list) {

System.out.println(operation.compute(element));

}

}

}

![](image111.jpg)

The output will appear as follows:

25

9

16

In this example, we are using a reference to the static method square. We could, as easily, use the following statement which uses the Math class’ static method abs:

display(list, Math::abs);

![](image112.jpg)

The output follows:

5

3

4

Using Instance Method References

Instance method references can use either a method of a specific instance or one from an arbitrary class object. Let’s examine a specific instance first. The following is the definition of a functional interface called StringConversion. It uses a convert method to perform some type of conversion on a string.

interface StringConversion {

String convert(String input);

}

![](image113.jpg)

The following is the definition of the MethodReferenceExample class where we will demonstrate the use of a method reference. The main method creates an instance of the MethodReferenceExample class where the toUpperCase method is assigned to the conversion variable using the method reference notation. The convert method is then used to transform a sample string to upper case. The toUpperCase method is defined at the end of the class.

public class MethodReferenceExample {

public static void main(String[] args) {

MethodReferenceExample mre = new

MethodReferenceExample();

StringConversion conversion;

conversion = mre::toUpperCase;

System.out.println(conversion.convert(

"sample string"));

}

public String toUpperCase(String input) {

return input.toUpperCase();

}

}

![](image114.jpg)

The output is as follows:

SAMPLE STRING

The next sequence illustrates how to use a method reference using the class name. A list of string is created and then sorted using the Collections class’ sort method. A second use of a method reference is used as the argument to the forEach method.

List<String> names =

Arrays.asList("Sam","Betty","Sue","Bob");

Collections.sort(names, String::compareTo);

names.forEach(System.out::println);

![](image115.jpg)

The sorted output is shown below:

Betty

Bob

Sam

Sue

Using Constructor References

Constructor references provide a convenient way of creating objects. The target type of a constructor reference will always be a functional interface. The syntax of a constructor reference consists of the class name followed by double colons and then the keyword new.

A simple use of a constructor reference is shown below where we create an ArrayList object. The Supplier is a functional interface found in the java.util.function package. Its functional method is passed void and returns an object. We are able to assign the constructor reference to the names variable because it is expecting a lambda expression. The names’ data type is a functional interface.

Supplier<List<String>> names = ArrayList::new;

![](image116.jpg)

The following is not legal. This is because a lambda expression is not expected in this context. It is looking for an object. The roster’s data type is a class.

ArrayList<Employee> roster = ArrayList<Employee>::new;

![](image117.jpg)

More sophisticated uses of constructor references are possible. To demonstrate one such use, we will start with a simple functional interface as shown below:

interface SimpleConstructorInterface<T> {

T create();

}

![](image118.jpg)

We will use this interface with the following class:

class SomeClass {

private String message;

public SomeClass() {

this.message = "Default Constructor";

System.out.println(

"+++SomeClass Default Constructor");

}

public String getMessage() {

return message;

}

}

![](image119.jpg)

Let’s start with two variable declarations for the interface and the class:

SomeClass sc;

SimpleConstructorInterface<SomeClass> sci;

![](image120.jpg)

We can use a constructor reference to create an instance of the SimpleConstructorInterface as follows. This is an instance that implements the create method.

sci = SomeClass::new;

![](image121.jpg)

When the instance is created, it will use the SomeClass default constructor in support of the create method. The default constructor’s signature matches that of the create method. That is, it is passed nothing and returns an object. Remember that constructors do return a value, an object.

We can use the create method to create an instance of SomeClass.

sc = sci.create();

System.out.println(sc.getMessage());

![](image122.jpg)

This code sequence produces the following output. The constructor has been called and the message has been set as anticipated.

+++SomeClass Default Constructor

Default Constructor

We can also use constructors other than the default constructor. The following interface will match a constructor that returns an object of type T, and takes some object U as a parameter:

interface ConstructorArgumentInterface<T, U> {

T create(U arg);

}

![](image123.jpg)

If we add a new constructor to SomeClass as shown below, we will be able to use this interface:

class SomeClass {

private String message;

…

public SomeClass(String message) {

this.message = message;       

System.out.println("+++SomeClass String Constructor");

}

…

}

![](image124.jpg)

The following illustrates its use. The constructor reference creates an instance of the ConstructorArgumentInterface. The create method is then used to create an instance of SomeClass.

ConstructorArgumentInterface<SomeClass, String> cai;

cai = SomeClass::new;

sc = cai.create("ConstructorArgumentInterface");

System.out.println(sc.getMessage());

![](image125.jpg)

The output of this sequence follows:

+++SomeClass String Constructor

ConstructorArgumentInterface

A more sophisticated example using a List is based on the following interface:

interface ConstructorListArgumentInterface<T, U> {

T create(List<U> arg);

}

![](image126.jpg)

A new instance variable and constructor are added to the SomeClass to support this interface:

class SomeClass {

private String message;

private List<String> list;

…

public SomeClass(List<String> list) {

this.list = list;

System.out.println("+++SomeClass List Constructor");

}

…

}

![](image127.jpg)

The use of these additions is shown below. The new constructor is used in support of the ConstructorListArgumentInterface’s method create. Once a SomeClass object is created, a list is returned and a string is added to it.

ConstructorListArgumentInterface<SomeClass, String> clai;

clai = SomeClass::<String>new; 

sc = clai.create(new ArrayList<String>());       

List<String> list;

list = sc.getList();

System.out.println(list.size());

list.add("First String");

System.out.println(list.size());

![](image128.jpg)

The output follows:

+++SomeClass List Constructor

0

1

Working with Lambda Expressions

Lambda expression can be used in a variety of contexts including:

- Assigning a lambda expression to a variable

- Passing a lambda expression as a parameter to a method or constructor

- Returning a lambda expression from a method

- Using lambda expressions with the tertiary operator

- Initializing an array with lambda expressions

- Throwing exceptions from a lambda expression

- Casting lambda expressions

- Implementing recursion with lambda expressions

We have already seen lambda expressions used in some of these situations. In this section, we will focus on special usage such as their use with the tertiary operator and explain how they can throw exceptions.

Using Lambda Expressions with Variable Declarations

We can assign a lambda expression to a variable if the variable is declared as a type compatible with the lambda expression. In the following example, a lambda expression is assigned to a java.util.Comparator type variable. The lambda expression is assigned to the comparator variable.

List<Integer> list = Arrays.asList(-5, -3, 4);

Comparator<Integer> comparator =

(x, y) -> (x < y) ? -1 : ((x > y) ? 1 : 0);

list.sort(comparator);

list.forEach(e->System.out.println(e));

![](image129.jpg)

When the code is executed we get the following output:

-5

-3

4

The Comparator is a functional interface whose function descriptor accepts two values and then returns a negative integer, zero, or a positive integer depending on the result of the comparison. Using a variable is useful to clarify the expression and to allow the lambda expression to be used in more than one context in the same program. Using a lambda expression with a variable declaration can also make the lambda expression easier to read when we separate the declaration from its use.

Using Lambda Expressions as a Return Value

Sometimes it is convenient to return a lambda expression that can be used in other situations. The getTest method shown below is passed a string representing a region of a country. A lambda expression matching the Predicate functional method is returned. The intent of this Predicate is to determine if a weight exceeds the limit for that region. The Predicate functional interface is discussed in the Using the Predicate Interface section.

public static Predicate<Integer> getTest(String area) {

switch (area) {

case "north":

return (Integer weight)->weight<200;

case "south":

return (Integer weight)->weight<150;

case "east":

return (Integer weight)->weight<100;

case "west":

return (Integer weight)->weight<250;

default:

return (Integer weight)->weight<200;

}

}

![](image130.jpg)

The next statement uses the lambda expression with a weight of 320:

System.out.println(getTest("east").test(320));

![](image131.jpg)

The test should return false.

Using Exceptions with a Lambda Expression

A lambda expression must not throw exceptions except for those specified in the functional interface’s method. In the following example, a TimeService interface is defined, followed by a class that uses a lambda expression to implement the interface.

interface TimeService {

String getTime();

}

public class ExceptionExamples {

public static void main(String arg[]) {

TimeService ts = ()-> {

if(*someCondition*) {

throw new Exception();

}

return "Time";

};

System.out.println(ts.getTime());

}

}

![](image132.jpg)

However, the lambda expression throws an exception that is not declared in the getTime method. As a result, the following error message will be generated at compile time:

unreported exception Exception; must be caught or declared to be thrown

This can be fixed by adding a throws clause to the getTime method as shown below:

interface TimeService {

String getTime() throws Exception;

}

![](image133.jpg)

Since the getTime method now throws an unhandled exception we get the following error message:

unreported exception Exception; must be caught or declared to be thrown

We can resolve this problem by either enclosing the statement in a try-catch block or having the main method throw an exception.

Using Lambda Expressions with the Tertiary Operator

To demonstrate the use of a lambda expression within the tertiary operator, we will use the IntBinaryOperator functional interface found in the java.util.function package. There are several functional interfaces that have been introduced with this package. The IntBinaryOperator’s function descriptor is the applyAsInt method which accepts two integer arguments and returns an integer result. We use a lambda expression consisting of a tertiary operator below to select between two different integer operations:

String operation = "add";

IntBinaryOperator operationExpression =

("sub".equals(operation))? (x,y)->x-y : (x,y)->x+y;

System.out.println(operationExpression.applyAsInt(5, 4));

![](image134.jpg)

The output will be a 9.

Casting Lambda Expressions

Casting a lambda expression is necessary in some situations. Consider the following functional interface definitions. They both declare abstract methods that accept a string and return void.

interface RectangleShape {

void draw(String s);

}

interface CircleShape {

void display(String s);

}

![](image135.jpg)

In the following class the doSomething method is overloaded. In the main method, the doSomething method is passed a lambda expression. However, this is an ambiguous situation because the lambda expression matches the abstract method of both interfaces.

public class CastingExample {

public static void main(String ars[]) {

CastingExample ce = new CastingExample();

ce.doSomething((String s)->System.out.println(s));

}

public void doSomething(RectangleShape shape) {       

}

public void doSomething(CircleShape shape) {       

}

}

![](image136.jpg)

The following error message is generated:

reference to doSomething is ambiguous

both method doSomething(RectangleShape) in CastingExample and method doSomething(CircleShape) in CastingExample match

This can be resolved using the cast operator as follows:

ce.doSomething(

(RectangleShape)(String s)->System.out.println(s));

![](image137.jpg)

Using Lambda Expressions to Initialize an Array

Lambda expressions can be used as elements of an array. In the following we create an array of Predicates. Each element is then initialized to a lambda expression expressing a specific weight range.

Predicate<Integer>[] tests;

tests = new Predicate[3];

tests[0] =  weight->weight>=0 && weight<100;

tests[1] =  weight->weight>=100 && weight<200;

tests[2] =  weight->weight>=200 && weight<300;

System.out.println(tests[1].test(125));

![](image138.jpg)

When the code executes, the output will be true.

Writing Recursive Lambda Expressions

A recursive lambda expression can be created. However, the lambda expression variable must be declared as either an instance or static variable. It cannot be a local variable. In the following program, a recursive fibonacci lambda expression is defined using the UnaryOperator functional interface. This interface is found in the java.util.function package. Its functional method is the apply method that accepts a single argument and returns a value.

public class RecursionExamples {

private static UnaryOperator<Integer>  fibonacci;

public static void main(String args[]) {       

fibonacci = (Integer n) -> {

if(n==0  || n==1) {

return 1;

} else {

return fibonacci.apply(n-1) +

                                                                                                                  fibonacci.apply(n-2);

}

};

System.out.println(fibonacci.apply(5));

}

}

![](image139.jpg)

The output is an 8.

Using the java.util.function Functional Interfaces

To facilitate the use of a lambda expression, the java.util.function package was added. It contains a number of functional interfaces designed to address common computing operations. Using these functional interfaces relieves programmers from having to declare their own equivalent interfaces. In addition, it helps standardize terminology. In this section, we will examine several of these interfaces and their uses.

Functional interfaces frequently represent abstract actions. Table 3: Function Types summarizes the function interfaces in the java.util.function package and how they are intended to be used. Many of these interfaces have default methods that add additional capability above and beyond the functional method. For example, we will see the andThen method used in the Using the Consumer Interface section.

Several of the examples in this section use an Employee class. This class possesses three instance variables: name, age, and payGrade. The first variable is a String and the last two are integers. The class has set and get methods for each of these variables and appropriate constructors. To save space, only the class’s toString method is listed as shown below:

public class Employee {

                 ...

public String toString() {

return "Name: " + this.name +

"  Age: " + this.age +

"  Pay grade: " + this.payGrade;

}

}

![](image140.jpg)

***Table 3: Function Types***

**Functional Interface Type** | Purpose

**Predicate** | These interfaces perform a test and returns a boolean value

**Function** | These types of interfaces perform some sort of transformation on their argument. No results are returned from the functional method

**Consumer** | These interfaces accept an input but do not return anything. As the name implies, it consumes its parameter.

**Supplier** | The supplier type interfaces are passed void and returns a value

**Operator** | Generally used for reduction type operations

![](image141.jpg)

Using the Predicate Interface

This interface is used in testing type situations where some function is evaluated and returns a true or false result. Its function descriptor is the test method. A single argument is passed to the test function and a boolean value is returned.

boolean  test(T t)

![](image142.jpg)

Table 4: Predicate Type Functional Interfaces list the Predicate type functional interfaces and their functional methods.

***Table 4: Predicate Type Functional Interfaces***

**Functional Interface** | Functional Method

**Predicate<T>** | boolean test(T t)

**BiPredicate<T,U>** | boolean test(T t, U u)

**DoublePredicate** | boolean test(double value)

**IntPredicate** | boolean test(int value)

**LongPredicate** | boolean test(long value)

![](image143.jpg)

There are many situations where a simple test is needed. For example, we may want to determine whether a person is eligible for some activity based on their age. We can write such a test as shown below:

public boolean evaluate(int age) {

if(age>18) {

return true;

} else {

return false;

}

}

![](image144.jpg)

We can determine if an individual is eligible by calling the evaluate method as follows:

System.out.println("Person is eligible: " + evaluate(19));

![](image145.jpg)

The output will be as follows:

Person is eligible: true

If we need to change the condition, we would need to rewrite the evaluate function. There may also be different sets of criteria needed for different situations. For example, we might want to test to see if a person is eligible for military service based on their age and weight. In another situation we might want to test to see if someone is eligible for social benefits. These examples imply that two or more evaluate like methods are needed. We can simplify the process by using the Predicate functional interface.

In the following code sequence, a Predicate is declared and assigned a lambda expression that performs the same age test as performed in the evaluate method. The test method is then executed against this Predicate lambda expression.

Predicate<Integer> tester = age->age>18;

System.out.println("Person is eligible: " +

tester.test(19));

![](image146.jpg)

The results will be the same as the previous example. An equivalent version is shown below that does not explicitly create a Predicate variable:

System.out.println("Person is eligible: " +

((Predicate<Integer>)age->age>18).test(19));

![](image147.jpg)

We can now use the Predicate for different selection criteria as shown below. Here we test to see if the individual is between the ages of 21 and 35 inclusive.

tester = age -> age>= 21 && age <=35;

System.out.println("Person is eligible: " +

tester.test(19));

![](image148.jpg)

We can also use a Predicate against a list of Employees. In the following example, a list is created and initialized with Employee instances. A for each loop is then used to select those employees that fall into a specified age range.

List<Employee> list = Arrays.asList(

new Employee("Mary", 23, 12),

new Employee("Tom", 32, 12),

new Employee("Sam", 19, 5),

new Employee("Sue", 43, 2));

tester = age -> age>= 21 && age <=35;

for(Employee element : list) {

if(tester.test(element.getAge())){

System.out.println(element.getName() +

" is eligible");

}

}

![](image149.jpg)

The output of this sequence follows:

Mary is eligible

Tom is eligible

The following example illustrates how to use the Predicate as an argument to a function. This function computes the sum of the elements in a list that meets the selection criteria.

public int sumOfElements(

List<Employee> numList,

Predicate<Integer> predicate) {

int sum = 0;

for (Employee number : numList) {

if (predicate.test(number.getAge())) {

sum += number.getAge();

}

}

return sum;

}

![](image150.jpg)

We can test the method using the following statement:

System.out.println(sumOfElements(list,age -> age >= 21 ));

![](image151.jpg)

The answer will be 98.

Building on this pattern, we can easily use different lambda expressions for other tests. The following illustrates how we can display a list of employees based on different selection criteria. The displayList method accepts a List and a Predicate to be used for employee selection. Only those employees that pass the test are displayed.

public void displayList(List<Employee> list,

Predicate<Employee> function) {

for (Employee employee : list) {

if (function.test(employee)) {

System.out.println(employee);

}

}

}

![](image152.jpg)

This code sequence illustrates the use of this method:

Predicate<Employee> condition =

(Employee e) -> e.getAge() >= 21;

displayList(list, condition);

![](image153.jpg)

The output of this sequence follows:

Name: Mary  Age: 23  Pay grade: 12

Name: Tom  Age: 32  Pay grade: 12

Name: Sue  Age: 43  Pay grade: 2

We can easily display different lists by using different selection criteria:

displayList(list, (Employee e) ->

e.getPayGrade() < 13 && e.getAge() >= 30);

displayList(list, (Employee e) ->

e.getName().contains("Sue"));

![](image154.jpg)

The Collection interface has added a method in Java 8\. This method will remove all elements of a collection which satisfy its Predicate argument. It returns true if any elements were removed, otherwise it returns false. If the collection’s iterator is unable to remove the element, an UnsupportedOperationException exception is thrown.

In the following example, a List is created and then the removeIf method is applied to it. It will remove any employee whose age is greater than 30.

List<Employee> list = new ArrayList();

list.add(new Employee("Mary", 23, 12));

list.add(new Employee("Tom", 32, 12));

list.add(new Employee("Sam", 19, 5));

lis.add(new Employee("Sue", 43, 2));

list.removeIf((e)->e.getAge()>30);

list.forEach((e)->System.out.println(e));

![](image155.jpg)

The output is shown below:

Name: Mary  Age: 23  Pay grade: 12

Name: Sam  Age: 19  Pay grade: 5

The Predicate interface is limited to a single parameter. If we want to perform a test using two arguments we can use the BiPredicate functional interface.

Using the Function Interface

The Function interface uses a generic T as an input value and returns an R. This is essentially a function that performs some sort of transformation. Its functional method is the apply method:

R apply(T t)

![](image156.jpg)

Table 5: Function Type Functional Interfaces list the Function type functional interfaces and their functional methods.

***Table 5: Function Type Functional Interfaces***

**Functional Interface** | Functional Method

**Function<T,R>** | R apply(T t)

**BiFunction<T,U,R>** | R apply(T t, U u)

**DoubleFunction<R>** | R apply(double value)

**DoubleToIntFunction** | int applyAsInt(double value)

**DoubleToLongFunction** | long applyAsLong(double value)

**IntFunction<R>** | R apply(int value)

**IntToDoubleFunction** | double applyAsDouble(int value)

**IntToLongFunction** | long applyAsLong(int value)

**LongFunction<R>** | R apply(long value)

**LongToDoubleFunction** | double applyAsDouble(long value)

**LongToIntFunction** | int applyAsInt(long value)

**ToDoubleBiFunction<T,U>** | double applyAsDouble(T t, U u)

**ToDoubleFunction<T>** | double applyAsDouble(T value)

**ToIntBiFunction<T,U>** | int applyAsInt(T t, U u)

**ToIntFunction<T>** | int applyAsInt(T value)

**ToLongBiFunction<T,U>** | long applyAsLong(T t, U u)

**ToLongFunction<T>** | long applyAsLong(T value)

![](image157.jpg)

The following illustrates how to use this interface to double the size of a number. A variable of type Function, doubleValue, is declared such that the expression accepts an integer and returns an integer. The apply method is then executed using a 4.

Function<Integer, Integer> doubleValue = x -> 2 * x;

System.out.println(doubleValue.apply(4));

![](image158.jpg)

The following example transforms an integer into a boolean value. If the number is greater than 100, true is returned otherwise false is returned. In this case true is returned.

Function<Integer, Boolean> booleanValue = x -> x > 100;

System.out.println(booleanValue.apply(150));

![](image159.jpg)

A more sophisticated example takes a list of Employees and returns a list of their ages plus one year. The getAgeList method uses a List of Employees and a Function expression that does the actual conversion.

public List<Integer> getAgeList(

List<Employee> list,

Function<Employee, Integer> function) {

List<Integer> ageList = new ArrayList<>();

for (Employee employee : list) {

ageList.add(function.apply(employee));

}

return ageList;

}

![](image160.jpg)

A list is created using the following code sequence:

List<Employee> list = Arrays.asList(

new Employee("Mary", 23, 12),

new Employee("Tom", 32, 12),

new Employee("Sam", 19, 5),

new Employee("Sue", 43, 2));       

![](image161.jpg)

The getAgeList method is then executed using a simple lambda expression where one is added to the employee’s age:

List<Integer> ageList =

getAgeList(list, e -> e.getAge() + 1);

ageList.forEach(x -> System.out.println(x));

![](image162.jpg)

The output follows:

24

33

20

44

To make the function more flexible, the following version uses generics:

public <T, U> List<U> getAgeListType(List<T> list,

Function<T, U> function) {

List<U> newList = new ArrayList<>();

for (T element : list) {

newList.add(function.apply(element));

}

return newList;

}

![](image163.jpg)

The function is then executed with the same set of parameters and gets the same result as shown below:

ageList = getAgeListType(list, e -> e.getAge() + 1);

ageList.forEach(x -> System.out.println(x));

![](image164.jpg)

The following function computes and returns the sum of the integers in a list:

public <T> int getSum(List<T> list ,

Function<T, Integer> function) {

int sum = 0;

for (T element : list) {

sum += function.apply(element);

}

return sum;      

}

![](image165.jpg)

It can be invoked as follows:

System.out.println("Sum: " +

getSum(list, Employee::getAge));

![](image166.jpg)

This example will output the following:

Sum: 117

The function would work for other lambda expressions such as the following:

System.out.println("Sum: " +

getSum(list2, Students::getGrade));

![](image167.jpg)

Using the BiFunction Interface

This interface uses two values as an input value and returns a third value. It is similar to the Function interface except that the apply method accepts two arguments:

R  apply(T t, U u)

![](image168.jpg)

The following illustrates two doubles being added together to produce a third double:

BiFunction<Double,Double,Double> product = (x,y) -> x * y;

System.out.println(product.apply(2.5, 34.6));

![](image169.jpg)

The output will be 86.5.

The next example uses two doubles and returns their product as an integer:

BiFunction<Double,Double,Integer> product2 = (x,y) -> {

double prod = x * y;

int result = (int) prod;

return result;

};

System.out.println(product2.apply(2.5, 34.6));

![](image170.jpg)

The output will be 86.

This example illustrates how the BiFunction can be used to transpose two strings:

BiFunction<String,String,String> transpose =

(s1,s2) -> s2+s1;

System.out.println(transpose.apply("cat","dog"));

![](image171.jpg)

The output will be “catdog”.

Using the Consumer Interface

The function acts on an argument and modifies it. It has no return value. The signature of the functional method follows:

void accept(T t)

![](image172.jpg)

Table 6: Consumer Type Functional Interfaces list the Consumer type functional interfaces and their functional methods.

***Table 6: Consumer Type Functional Interfaces***

**Functional Interface** | Functional Method

**Consumer<T>** | void  accept(T t)

**BiConsumer<T,U>** | void accept(T t, U u)

**DoubleConsumer** | void accept(double value)

**IntConsumer** | void accept(int value)

**LongConsumer**, | void accept(long value)

**ObjDoubleConsumer<T>** | void accept(T t, double value)

**ObjIntConsumer<T>** | void accept(T t, int value)

![](image173.jpg)

The forEach method uses a Consumer as its argument. This makes it easy to iterate over a collection and modify each element as appropriate.

List<Employee> list = Arrays.asList(

new Employee("Mary", 23, 12),

new Employee("Tom", 32, 12),

new Employee("Sam", 19, 5),

new Employee("Sue", 43, 2));                                  

list.forEach(e -> e.setPayGrade(e.getPayGrade() + 1));

list.forEach(System.out::println);

![](image174.jpg)

The output of this sequence follows:

Name: Mary  Age: 23  Pay grade: 13

Name: Tom  Age: 32  Pay grade: 13

Name: Sam  Age: 19  Pay grade: 6

Name: Sue  Age: 43  Pay grade: 3

The Consumer interface also has an andThen method. This allows the programmer to combine multiple actions together. Its syntax follows:

Default Consumer<T> andThen(Consumer<? Super T> after)

![](image175.jpg)

For example we can duplicate the raise and print operations used in the previous example with a single forEach as shown below. The andThen method adds the print operation to the following raise operation.

Consumer<Employee> raise =

e -> e.setPayGrade(e.getPayGrade() + 1);

Consumer<Employee> combined =

raise.andThen(System.out::println);

list.forEach(combined);

![](image176.jpg)

The output will be identical to the previous output.

The forEach method can also be executed against an instance of an ArrayList. The following example illustrates this.

ArrayList<Employee> employeeList =

new ArrayList<Employee>();

employeeList.add(new Employee("Mary", 23, 12));

employeeList.add(new Employee("Tom", 32, 12));

employeeList.add(new Employee("Sam", 19, 5));

employeeList.add(new Employee("Sue", 43, 2));

employeeList.forEach((e) -> System.out.println(e));

![](image177.jpg)

The output follows:

Name: Mary  Age: 23  Pay grade: 12

Name: Tom  Age: 32  Pay grade: 12

Name: Sam  Age: 19  Pay grade: 5

Name: Sue  Age: 43  Pay grade: 2

A forEachRemaining method has been added to the Iterator interface in Java 8\. Its argument is a Consumer and the method will apply that Consumer to the remaining elements of the collection. The method is demonstrated below where the first two employees are displayed in their entirety. However, once an employee’s age exceeds 30, then only their age is displayed.

Iterator<Employee> iterator = employeeList.iterator();

while(iterator.hasNext()) {

Employee employee = iterator.next();

System.out.println(employee);

if(employee.getAge()>30) {

iterator.forEachRemaining(

 (e)->System.out.println(e.getAge()));

}

}

![](image178.jpg)

The output follows:

Name: Mary  Age: 23  Pay grade: 12

Name: Tom  Age: 32  Pay grade: 12

19

43

Using the Supplier Interface

The interface is useful in situations where objects need to be produced and lambda expressions are useful to support the creation. The function returns a new or existing object. The interface’s functional method is the get method.

T get()

![](image179.jpg)

Table 7: Function Type Functional Interfaces list the Supplier type functional interfaces and their functional methods.

***Table 7: Function Type Functional Interfaces***

**Functional Interface** | Functional Method

**Supplier<T>** | T get()

**BooleanSupplier** | boolean getAsBoolean()

**DoubleSupplier** | double getAsDouble()

**IntSupplier<R>** | R apply(int value)

**LongSupplier** | long getAsLong()

![](image180.jpg)

In its simplest form we can define a Supplier that can return a new Employee as shown below. The first assignment statement uses a lambda expression while the second uses a constructor reference.

Supplier<Employee> employeeSupplier;

employeeSupplier = () -> new Employee();

employeeSupplier = Employee::new;

![](image181.jpg)

An Employee object is not created, only an instance of the Supplier functional interface. To create an Employee object we need to use the get method as shown below:

Employee employee = employeeSupplier.get();

![](image182.jpg)

A more sophisticated example is shown below which will create a random set of Employee objects based on a list of Employees. An instance of the Random class is created that is used to randomly select employees from the list. The lambda expression uses the nextInt method to select a random employee from the list.

Random r = new Random();

List<Employee> employeeList = Arrays.asList(

new Employee("Mary", 23, 12),

new Employee("Tom", 32, 12),

new Employee("Sam", 19, 5),

new Employee("Sue", 43, 2));

Supplier<Employee> randomEmployee;

randomEmployee = () -> {

int index = r.nextInt(employeeList.size());

return employeeList.get(index);

};

for(int i=0; i<5; i++) {

System.out.println(randomEmployee.get());

}

![](image183.jpg)

One possible output follows:

Name: Mary  Age: 23  Pay grade: 12

Name: Mary  Age: 23  Pay grade: 12

Name: Sam  Age: 19  Pay grade: 5

Name: Mary  Age: 23  Pay grade: 12

Name: Sam  Age: 19  Pay grade: 5

The lambda expression could have as easily generated Employee objects randomly, which can be useful for testing purposes. When testing is complete, a real supplier can be substituted in its place.

Here is an example of passing a Supplier object to a method. Its purpose is to generate a random employee and increment his pay grade by one. A Consumer functional interface is used to perform the actual conversion. The lambda expression for this operation is shown below:

Consumer<Employee> consumer = (Employee e) -> {

e.setPayGrade(e.getPayGrade() + 1);

};

![](image184.jpg)

A convert method is used to link the supplier and consumer together:

public static Employee convert(

Consumer<Employee> consumer,

Supplier<Employee> supplier) {

Employee e = supplier.get();

consumer.accept(e);

return e;

}

![](image185.jpg)

The following statement illustrates the use of the method:

System.out.println(convert(consumer,randomEmployee));

![](image186.jpg)

One possible output follows:

Name: Tom  Age: 32  Pay grade: 13

Using Operator Type Interfaces

Operator type interfaces are concerned with applying operations against one or two operands. For binary operators it is a reduction type of operation. There is not a specific operator interface, but rather a series of functional interfaces that act on objects. Table 8: Operator Type Functional Interfaces lists the Operator type functional interfaces and their functional methods.

***Table 8: Operator Type Functional Interfaces***

**Functional Interface** | Functional Method

**BinaryOperator<T>** | R apply(T t1, T t2) (Inherited from BiFunction)

**DoubleBinaryOperator** | double applyAsDouble(double left, double right)

**DoubleUnaryOperator** | double applyAsDouble(double operand)

**IntBinaryOperator** | int applyAsInt(int left, int right)

**IntUnaryOperator** | int applyAsInt(int operand)

**LongBinaryOperator** | long applyAsLong(long left, long right)

**LongUnaryOperator** | long applyAsLong(long operand)

**UnaryOperator<T>** | R apply(T t) (Inherited from Function)

![](image187.jpg)

In this section, we will illustrate several of these types of interfaces.

Using the UnaryOperator Interface

The UnaryOperator interface extends the Function interface and inherits the apply functional method. In the following example, a lambda expression is created for the interface that accepts a string and returns a formatted string indicating the number of characters present in the string:

UnaryOperator<String> stringCount = (String x) ->

"\"" + x + "\" has " + x.length() + " characters";

System.out.println(stringCount.apply("Simple String"));

![](image188.jpg)

The output follows:

"Simple String" has 13 characters

A replaceAll method has been added to the List interface in Java 8\. It will modify each element of a List by applying a UnaryOperator against each element. To demonstrate this method, let’s start with the following declarations:

List<Employee> list = new ArrayList();

list.add(new Employee("   Mary", 23, 12));

list.add(new Employee("Tom   ", 32, 12));

list.add(new Employee("   Sam   ", 19, 5));

list.add(new Employee("  Sue", 43, 2));

UnaryOperator<Employee> trimNames = (Employee e) -> {

Employee emp = new Employee(e);

emp.setName(e.getName().trim());

return emp;

};

![](image189.jpg)

Previously, it was necessary to use an iterator to replace elements of the list similar to the following:

final ListIterator<Employee> listIterator =

list.listIterator();

while (listIterator.hasNext()) {

listIterator.set(trimNames.apply(listIterator.next()));

}

list.forEach((e) -> System.out.println(e));

![](image190.jpg)

The output of this sequence is shown below:

Name: Mary  Age: 23  Pay grade: 12

Name: Tom  Age: 32  Pay grade: 12

Name: Sam  Age: 19  Pay grade: 5

Name: Sue  Age: 43  Pay grade: 2

We can now perform the same operation more succinctly using the replaceAll method as illustrated below:

list.replaceAll(trimNames);

list.forEach((e) -> System.out.println(e));

![](image191.jpg)

The output will be the same as with the previous implementation.

Using the BinaryOperator Interface

This functional interface is essentially the same as BiFunction except all of the arguments are of the same type. It is derived from BiFunction. It accepts two Ts and returns a single T, as shown below. It is useful for reduction type operations.

R apply(T t, U u)

![](image192.jpg)

The following sequence creates two lambda expressions for a BinaryOperator. The first lambda expression is for addition and the second one is for subtraction.

BinaryOperator<Integer> addition = (a, b) -> a + b;

BinaryOperator<Integer> subtraction = (a, b) -> a - b;

![](image193.jpg)

The operateBinary is passed the lambda expression and acts on the arguments:

public int operateBinary(int a, int b,

BinaryOperator<Integer> op) {

return op.apply(a, b);

}

![](image194.jpg)

The function is then executed using each lambda expression as shown below:

System.out.println("40 + 2 = "

+ operateBinary(40, 2, addition));

System.out.println("20 - 10 = "

+ operateBinary(20, 10, subtraction));

![](image195.jpg)

The output will be as follows:

40 + 2 = 42

20 - 10 = 10

Conclusion

In this chapter, we have seen how lambda expressions can be used to support a functional programming style in Java. Lambda expressions are essentially anonymous functions which are used in conjunction with functional interfaces.

Lambda expressions can be used in a number of different contexts. They can be passed and returned from methods. They can be assigned to a variable or an array so as to allow them to be reused. Lambda expressions can also be written to support recursive algorithms.

In Java 8, a new package, java.util.function, has been added. This package contains a large number of functional interfaces that support common operations such as transformations and predicate type operations. We will see further examples of the use of lambda expression in subsequent chapters.

* * * * *

Chapter 3 – Streams

-Streams

--Stream Characteristics

---Streams Do Not Store Elements

---Streams Can Be Unbounded

---Streams Do Not Modify the Original Source

---A Stream May Be Ordered

---Automatic Parallelization

--An Overview of Stream Methods

-Creating a Stream

--Using the Stream Interface’s of Method

--Using the Collection Class’ stream Method

--Using a Stream.Builder Interface

---Using the builder method

--Generating Infinite Streams

---Using the iterate Method

--Concatenating Streams

--Generating an Empty Stream

-Using Stream Methods

--The Part Example Class

--Using the forEach Method

---Using the forEachOrdered Method

--Using the map Method

---Using Other Map Methods

--Using the flatmap Method

--Using the filter Method

--Using the Match Type Methods

--Using the findFirst Method

---Using the findAny Method

---Using the Optional Class

--Using the reduce Method

--Using the Collector Interface and the collect Method

---Using the Collects Class

--Using the iterator Method

--Using the sorted Method

--Using the distinct Method

--Using the limit Method

--Using the skip Method

--Using the max, min, and count Methods

-Streams for Primitive Types

--Using the IntStream Interface

-Understanding Lazy and Eager Evaluation

--Using Short-Circuit Methods

-Using Parallel Stream Operations

-Conclusion

Streams

A stream can be thought of as a sequence of elements that can be processed on an element by element basis. The elements of a stream can be any data type. Streams are different from an array or collection in that they are not a data structure. They do not occupy permanent memory and are transient in nature.

The processing of the elements in a stream occurs by executing methods against the elements of a stream. A stream chains these method calls together. The output of one stream method is fed, or chained, to another method. This is sometimes referred to as *fluent chaining*. These methods will perform some operation on the stream such as removing some elements from the stream or converting one element type to another element type. A stream is essentially a wrapper around a collection of objects. Many stream operations use lambda expressions as covered in Chapter 2.

Do not confuse the concept of streams with that of input and output streams found in the java.io package. These are different concepts. An IO stream is generally considered to be a sequence of bytes.

The java.util.stream package has been added to Java 8\. This package consists primarily of interfaces. The Stream interface and the objects implementing this interface provide the support for the implementation of streams.

There are two primary benefits to using streams:

- They are more succinct than an equivalent collection implementation

- They have the potential to improve performance by taking advantage of multiple processors

The code used by streams is more succinct than those using older techniques such as the iterator approach. The following shows two ways of listing only those parts whose price exceeds 0.15\. The first approach uses an iterator and the second approach uses a stream. The stream approach is shorter and easier to follow. The filter method will remove those elements which do not meet the criteria specified by the predicate. Predicates were discussed in Chapter 2\. The forEach method will apply the println method against each element.

// Iterator approach

List<Part> partsList = ...

Iterator<Part> partsIterator = partsList.iterator();

while(partsIterator.hasNext()) {

Part part = partsIterator.next();

if(part.getPrice() >= 0.15f) {

System.out.println(part);

}

}

// Stream approach

Stream<Part> partsStream = partsList.stream();

Predicate<Part> pricePredicate = p -> p.getPrice() > 0.15f;

partsStream.filter(pricePredicate).

forEach(System.out::println);

![](image196.jpg)

Using a stream instead of a collection means:

- No need for an explicit declaration of intermediate variables or storage

- Potential for lazy evaluation

- More flexibility in design using a more natural style (pipeline)

- Potential for automatic parallelization

In the previous example, the iterator approach required declaring temporary variables to hold intermediate values. This is not the case for the stream implementation. Lazy evaluation will be covered in more depth in Understanding Lazy and Eager Evaluation, but it essentially means that a stream is not necessarily forced to perform an operation against an element until it needs to.

In future examples we will see how multiple methods can be applied to the same stream in an easy to follow chain of invocations. This approach conforms more closely to how solutions to many problems are conceptualized. These types of solutions involve a series of operations applied successively to elements of a collection.

Performance gains are achieved using a parallel stream. This stream will split the problem into multiple instances based on the problem and the number of processors available. The old iterator approach and sequential streams give about the same performance. Parallel streams are normally much faster.

However, a parallel stream should not be used for small lists as the overhead of parallelism will negate any performance gains. Also, it is not always possible to simply switch from a sequential stream to a parallel stream. Often factors, such as the order the elements are processed in, or whether state information is maintained between operations, need to be considered.

A stream does not support the storage of data. It is a pipeline type of operation where data is passed from one operation to the next. They flow as a stream. However, it is easy to create arrays or lists from a stream.

Once a stream processed, it cannot be used again. The stream is said to be consumed. Since a stream is not an actual data structure, when we have processed it there is nothing left. Any temporary memory that may have been used by a stream is gone.

Stream Characteristics

There are several aspects of streams that need to be kept in mind during their use. These include:

- Streams do not store elements

- Streams can be unbounded

- Streams do not modify the original source

- Streams may be ordered

- Automatic parallelization is possible

Streams Do Not Store Elements

Streams do not store elements. Since streams are not data structures there is no need to store data. This is in contrast to collections which do store data. The elements of a stream are obtained from some source and are processed. When the processing is complete, the stream goes away. Its elements will go away unless moved to an array or collection separate from the stream.

When the stream has been processed, its elements are no longer available through the stream. The stream cannot be reused. However, it can be regenerated in most cases.

Streams Can Be Unbounded

Collections are of finite size, streams are unbounded. A stream can contain zero to an infinite number of elements. As we will see in Generating Infinite Streams, an infinite stream can be generated using several techniques. Though not truly infinite, a stream can run for a very long time if needed.

A stream works on a sequence of values. A generator can create these values which are fed into the stream and processed. The stream can be of any length and is considered to be unbounded.

Streams Do Not Modify the Original Source

The source of the elements for a stream frequently originates from a data structure such as a list or array. As such, the operations against the stream and its elements are not performed against the elements in the original data structure. Also, streams do not modify the original source.

A Stream May Be Ordered

A stream may be ordered or unordered. When a stream is created from an array, List, or some generator function, the stream is an ordered stream. In contrast, streams that are produced from a Set are unordered. This does not imply that a stream is ordered by some criteria such as being alphabetical. Rather, it is like a queue where elements that enter first are served first.

With ordered streams, most operations will preserve the original order. The sorted method does not preserve the original order but imposes a new order instead. The unordered method also removes order from a stream. An unordered stream is desirable for performance reasons when used with some parallel operations.

Automatic Parallelization

Streams have two modes: sequential and parallel. When specified to be parallel, the processing of the stream is automatically executed concurrently based on the number of processors available. The programmer does not need to explicitly setup multiple threads. This is discussed in Using Parallel Stream Operations.

An Overview of Stream Methods

The methods of a stream can be classified as either intermediary or terminal. With intermediary methods, the output of the method is fed to another method. That is, they return another stream. With terminal methods, the stream ends and a result is produced. It represents the end of a pipeline. A pipeline consists of a source, zero or more intermediate operations, and a terminal operation. Once a pipeline is terminated, it cannot be used again. Intermediary methods are typically evaluated lazily. This concept is further explored in Understanding Lazy and Eager Evaluation.

Intermediate methods can further be classified as either stateless or stateful. A stateless method will simply forward its result to the next element in the pipeline. A stateful method will capture some data and possibly wait for more data before proceeding.

**Table 1 - Summary of Selected Stream Methods** lists a set of Stream interface methods. These will be discussed in the subsections that follow.

***Table 1 - Summary of Selected Stream Methods***

*Intermediate*:

Method | **Purpose** | Return Value

filter | **Return stream containing elements matching a Predicate** | Stream<T>

map | **Applies an operation against each element in the stream, possibly transforming it** | Stream<U>

flatMap | **Flattens out a stream** | Stream<R>

sorted | **Sorts the elements of a stream** | Stream<T>

distinct | **Returns a stream which contains no duplicate elements** | Stream<T>

limit | **Restricts the number of element in the returned stream** | Stream<T>

skip | **Skips over a specific number of elements in a stream** | Stream<T>

*Terminal*:

**Method** | Purpose | **Return Value**

**forEach** | Performs some operation on each element of the stream and terminates the stream | **void**

**reduce** | Combines stream elements together using a BinaryOperator | **T**

**collect** | Puts the stream’s elements into a container such as a Collection | **R**

**min** | Finds the smallest element as determined by a Comparator | **Optional<T>**

**max** | Finds the largest element as determined by a Comparator | **Optional<T>**

**count** | Determines the number of elements in a stream | **long**

**anyMatch** | Determines whether at least one element of the stream matches a Predicate | **boolean**

**allMatch** | Determines whether every element of the stream matches a Predicate | **boolean**

**noneMatch** | Determines whether there are no elements of the stream matches a Predicate | **boolean**

**findFirst** | Returns the first element of a stream | **T**

**findAny** | Returns any element of a stream | **T**

**iterator** | Returns an Iterator for the stream | **Iterator**

**toArray** | Creates an array based on the elements of the stream | **A[]**

![](image197.jpg)

Creating a Stream

Before a stream can be used, it must be created. There are several ways of creating a stream including from data structures such as a list or an array. Many of the Stream interface’s methods return Stream objects. This is an important capability and permits the “chaining” of Stream methods. Here, we are more concerned with how a stream can be created from an ultimate “source” such as a list.

Using the Stream Interface’s of Method

The Stream interface’s static of method provides a convenient technique for creating streams from a list. In the following example, a stream of strings is created. The forEach method will display the elements of the stream.

Stream<String> stringStream =

Stream.of("alpha", "beta", "gamma", "delta");

stringStream.forEach((s)->System.out.print(s + " "));

![](image198.jpg)

The output of this sequence follows:

alpha beta gamma delta

Creating a stream of strings from a string literal can be accomplished using the String class’ split method as shown below:

stringStream

= Stream.of("drop the sword here".split(" "));

stringStream.forEach((s) -> System.out.println(s));

![](image199.jpg)

The following is printed:

drop

the

sword

here

We can easily create a stream of Parts using this method as follows. The Part class will be discussed in The Part Example Class.

Stream<Part> partStream = Stream.of(

new Part("Pencil", 100, 5, 0.15f, 500),

new Part("Eraser", 200, 3, 0.25f, 250),

new Part("Paper", 2000, 1, 0.03f, 1200));

partStream.forEach((p) -> System.out.println(p));

![](image200.jpg)

The output follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.15 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25 Quantity:   250

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03 Quantity:  1200

We can also use the of method with an array as illustrated below:

Part[] parts = {

new Part("Pencil", 100, 5, 0.15f, 500),

new Part("Eraser", 200, 3, 0.25f, 250),

new Part("Paper", 2000, 1, 0.03f, 1200));

};

partStream = Stream.of(parts);

partStream.forEach((p) -> System.out.println(p));

![](image201.jpg)

The output is the same as the previous example.

Using the Collection Class’ stream Method

The stream method can be applied to those classes that implement the Collection interface including the List class. In the following example, a list of numbers is created and the stream method is then applied to it. The contents of the stream are then displayed.

List list = Arrays.asList(1, 2, 3, 4, 5);

Stream stream = list.stream();

stream.forEach(x -> System.out.print(x + " "));

![](image202.jpg)

The output of this sequence follows:

1 2 3 4 5

In the next example, a list of Parts is created. The stream method is then applied against this list and the resulting stream is then displayed.

List<Part> partsList = Arrays.asList(

new Part("Pencil", 100, 5, 0.15f, 500),

new Part("Eraser", 200, 3, 0.25f, 250),

new Part("Paper", 2000, 1, 0.03f, 1200)

);

Stream<Part> partsStream = partsList.stream();

partsStream.forEach(p -> System.out.println(p));

![](image203.jpg)

The output follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.15

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03

The stream method can also be applied against the Arrays class as shown below:

int[] nums = {2, 4, 6, 8};

IntStream intStream = Arrays.stream(nums);

intStream.forEach(x -> System.out.print(x));

![](image204.jpg)

The output of this sequence follows:

2 4 6 8

Using a Stream.Builder Interface

A stream can also be created using an instance of the Stream.Builder interface. This interface uses an accept method to add an element to a stream. The build method returns the stream.

In the following example, the class SampleStreamBuilder is declared that implements the Stream.Builder interface. The class uses a list to maintain a collection of items to be added to the stream. The accept method adds new elements to the list. The build method uses the Collection interface’s stream method to create the actual stream.

class SampleStreamBuilder implements Stream.Builder<String> {

List<String> list = new ArrayList<String>();

@Override

public void accept(String t) {

list.add(t);

}

@Override

public Stream<String> build() {

return list.stream();

}

}

![](image205.jpg)

The following code sequence creates an instance of SampleStreamBuilder and uses the accept method to add strings to the internal list. The build method is then invoked to return the stream. The forEach method is used to display the contents of the stream.

SampleStreamBuilder streamBuilder =

new SampleStreamBuilder();

streamBuilder.accept("Bob");

streamBuilder.accept("Sue");

streamBuilder.accept("Mary");

Stream<String> stream = streamBuilder.build();

stream.forEach((s)->System.out.println(s));

![](image206.jpg)

The output follows:

Bob

Sue

Mary

Using the builder method

The Stream interface also has a static method, builder, that returns an instance of a Stream.Builder. This convenience method is used below to duplicate the previous example:

Stream.Builder streamBuilder = Stream.builder();

streamBuilder.accept("Bob");

streamBuilder.accept("Sue");

streamBuilder.accept("Mary");

Stream<String> stream = streamBuilder.build();

stream.forEach((s) -> System.out.println(s));

![](image207.jpg)

The output of this sequence when executed will be the same as for the previous example.

Generating Infinite Streams

An infinite stream is one that, in theory at least, will produce an unlimited number of elements. One way of generating an infinite stream is to base the input off of the keyboard as shown below. This approach uses the Stream interface’s generate method. This method uses a Supplier functional interface implementation as an argument. Each word in a line of input is displayed separated by a backslash.

Scanner scanner = new Scanner(System.in);

Supplier<String> cliSupplier = () -> {

return scanner.next();

};

Stream.generate(cliSupplier).

forEach((c) -> System.out.print(c+"\\")

![](image208.jpg)

The supplier is the source of input. In this case it is the keyboard. The user will enter data line by line. One possible input/output sequence follows:

Once upon a time

Once\upon\a\time\

There was a giant tree

There\was\a\giant\tree\

Using the iterate Method

The Stream interface’s static iterate method can be used to generate an infinite stream. The method uses two arguments: an initial seed, and a UnaryOperator function to generate the next element. The following example displays the lower and upper case letters of the alphabet. In this example, the seed is a char and the operator increases it by one. The map method, discussed in Using the map Method, converts the char to a string containing the lower and upper case letters. The limit method restricts the output to 26 elements.

Stream.iterate('a', c -> c++).

map(c -> c.toString() + " " + c.toString().

toUpperCase()).

limit(26).

forEach(c -> System.out.print(c + " "));

![](image209.jpg)

The  output of this code sequence follows:

a A b B c C d D e E f F g G h H i I j J k K l L m M n N o O p P q Q r R s S t T u U v V w W x X y Y z Z

Concatenating Streams

The source of a stream can be from combining two or more other streams. Streams can be concatenated using the static concat method. This method is illustrated below where two integer streams are created. The first stream consists of the first 10 even numbers and the second stream consists of the first 10 odd numbers. The limit method restricts the output of the iterate methods to 10 elements. The concat method takes two streams and returns a third.

Stream<Integer> evenStream =

Stream.iterate(2, n -> n+2).limit(10);

Stream<Integer> oddStream =

Stream.iterate(1, n -> n+2).limit(10);

Stream<Integer> numbers =

Stream.concat(evenStream,oddStream);

numbers.forEach(n -> System.out.print(n + " "));

![](image210.jpg)

The output will be as follows:

2 4 6 8 10 12 14 16 18 20 1 3 5 7 9 11 13 15 17 19

Generating an Empty Stream

An empty stream is one that does not contain any elements. It may be returned by some methods or can be created using the empty method as shown below:

Stream<Integer> empty = Stream.empty();

![](image211.jpg)

If the Stream interface’s count method returns 0, then the stream is empty.

Using Stream Methods

There are numerous methods that can be applied to a stream. These are typically used for such activities as listing elements of a stream, creating new streams after transforming existing elements, or filtering out certain elements.

The examples used for the Stream interface methods will, at times, use methods not yet covered. This is sometimes necessary to demonstrate the utility of a technique. When this occurs, a brief introduction to the method will be presented. A more complete coverage can be found in the corresponding method’s section. In this section we will examine most of the Stream interface’s methods.

The Part Example Class

For the examples in this chapter we will be using a Stream based on a Part class. The class is shown below. It possesses a number of getter/setter methods along with an overridden toString and equals method. A comparator method is provided to compare two parts.

public class Part {

private String name;

private int partNumber;

private int weight;

private float price;

private int quantity;

public Part(String name, int partNumber, int weight, float price, int quantity) {

this.name = name;

this.partNumber = partNumber;

this.weight = weight;

this.price = price;

this.quantity = quantity;

}

public Part(Part part) {

this(part.name, part.partNumber, part.weight,

part.price, part.quantity);

}

public Part() {

this("Default",12345,10,10.0f,0);

}

public String getName() {

return name;

}

public void setName(String name) {

this.name = name;

}

public int getPartNumber() {

return partNumber;

}

public void setPartNumber(int partNumber) {

this.partNumber = partNumber;

}

public int getWeight() {

return weight;

}

public void setWeight(int weight) {

this.weight = weight;

}

public float getPrice() {

return price;

}

public void setPrice(float price) {

this.price = price;

}

public int getQuantity() {

return quantity;

}

public void setQuantity(int quantity) {

this.quantity = quantity;

}

public boolean equals(Part part) {

return this.name.equals(part.name);

}

public int comparator(Part part) {

return this.name.compareTo(part.name);

}

public String toString() {

return String.format(

"Name: %-8s Weight: %3d  Part Number: %5d Price: %.2f Quantity: %5d",

this.name, this.weight, this.partNumber, this.price, this.quantity);

}

}

![](image212.jpg)

![](image213.jpg)

![](image214.jpg)

We will also create a List of parts defined below:

List<Part> partsList = Arrays.asList(

new Part("Pencil", 100, 5, 0.15f, 500),

new Part("Eraser", 200, 3, 0.25f, 250),

new Part("Paper", 2000, 1, 0.03f, 1200)

);

![](image215.jpg)

This partsList will be used as the basis for a number of the examples in this chapter. In some examples, more elements are added when these three parts are not sufficient to demonstrate a technique.

Using the forEach Method

This method is useful for processing each element of a stream. Its parameter must be compatible with the Consumer interface’s accept method. The following code sequence illustrates how each element of the stream can be displayed:

Stream<Part> partsStream = partsList.stream();

partsStream.forEach(System.out::println);

![](image216.jpg)

The output of this sequence follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.15 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25 Quantity:   250

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03 Quantity:  1200

Alternatively we can increase the price for each part by 5% using the following lambda expression:

partsStream.forEach(x -> x.setPrice(x.getPrice()*1.05f));

![](image217.jpg)

However, this does not modify the original list as demonstrated below:

Stream<Part> partsStream = partsList.stream();

partsStream.forEach(x -> x.setPrice(x.getPrice()*1.05f));

for (Part part : partsList) {

System.out.println(part);

}

![](image218.jpg)

The contents of the partsList follows. It has not been changed.

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.16 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.26 Quantity:   250

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03 Quantity:  1200

However, we can use the map method to create a new stream by creating copies of the elements of the original stream.  This is illustrated in Using the map Method.

One of the drawbacks with the forEach method is that you cannot break out of the loop as you can with a forEach statement. As with all streams, the stream can only be used once.

Using the forEachOrdered  Method

When a forEach statement is used against a stream, it can be executed concurrently. However, the stream must be a parallel stream. One way of creating a parallel stream is with the parallelStream method as shown below:

partsList.parallelStream().

forEach(x ->System.out.println(x));

![](image219.jpg)

The order that the elements of a stream are processed in,  by the forEach method, is nondeterministic. That is, it cannot be predicted in advance. This is more apparent for parallel streams where the stream is broken into sub-streams, processed individually, and then combined.

The purpose of the forEachOrdered method is to guarantee that the order will be observed. Otherwise, the use of these two methods is identical. The following sequence illustrates the use of this method:

partsStream = partsList.stream();

partsStream.forEachOrdered(System.out::println);

![](image220.jpg)

The output follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.16 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.26 Quantity:   250

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03 Quantity:  1200

Using the map Method

The map method accepts a Function interface argument. This interface converts one element of a stream into a new element. To demonstrate the map method, we first declare a Function interface variable called mapper. The definition uses a lambda expression that creates a new Part based on an existing part, raises the price of each part by 5% and then returns the new part.

Function<Part, Part> mapper = (Part part) -> {

Part newPart = new Part(part);

newPart.setPrice(part.getPrice() * 1.05f);

return newPart;

};

![](image221.jpg)

The mapper reference variable is then used as the argument of the map method as shown below. The content of the newStream is then displayed.

Stream<Part> newStream = partsStream.map(mapper);

newStream.forEach(System.out::println);

![](image222.jpg)

The output of this sequence follows. The price of paper does not appear to increase due to the rounding of the output.

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.16 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.26 Quantity:   250

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03 Quantity:  1200

The previous two statements can be combined as follows:

partsStream.map(mapper).forEach(System.out::println);

![](image223.jpg)

The map function can be used to extract the part numbers from a stream. The next example uses the toArray method to generate an array Integers that holds the part numbers:

Integer[] partNumbers =

partsStream.map(Part::getPartNumber).

toArray(Integer[]::new);

for(Integer partNumber : partNumbers) {

System.out.println(partNumber);

}

![](image224.jpg)

The output follows:

100

200

2000

Using Other Map Methods

There are several other mapping methods available. These methods are summarized in **Table 2 - Map Method Summary**. Each of the argument functions uses an applyAsDataType function method. For example, the ToIntFunction interface uses an applyAsInt method.

***Table 2 - Map Method Summary***

**Return Type** | Method | **Argument**

**DoubleStream** | mapToDouble | **ToDoubleFunction**

**IntStream** | mapToInt | **ToIntFunction**

**LongStream** | mapToLong | **ToLongFunction**

![](image225.jpg)

The DoubleStream, IntStream, and LongStream interfaces represent streams of the corresponding data type.

The following example declares an array of doubles and then uses the Arrays class’ stream method to create a DoubleStream. The mapToInt method is then applied to each element. Its effect is to double the element’s value and return the result as an integer.

double numbers[] = {1.2, 34.3, 6.045, 45.32};

DoubleStream doubleStream = Arrays.stream(numbers);

doubleStream.

mapToInt(d -> ((int) d * 2)).

forEach(n -> System.out.print(n + " "));

![](image226.jpg)

The output follows:

2 68 12 90

The following uses the previously created partsStream. It computes the value of each part (the product of its price and quantity fields) and displays the total value as an integer. The sum method is a terminal method that, as its name implies, will total the elements of a stream.

int total = partsStream.

mapToInt(p -> (int)(p.getPrice()*p.getQuantity())).

sum();

System.out.println("Total value: " + total);

![](image227.jpg)

Total value: 173

Using the flatmap Method

The flatMap method is similar to the map method. The map method uses a function passed to it, applies that function to each element, and then returns a stream of the new elements. Sometimes the returned stream consists of sub-streams. The flatMap method performs similarly to the map method except it will “flatten” the sub-streams into a single stream.

The flatMap method will accept a function that is applied to each element generating a sub-stream. It will then combine these sub-streams into a single stream.

Consider the following code sequence. A list of parts, partsList, is created. A new list, mappedParts is created that consists of a list of a list of floats. This list will consist of sub-lists each listing the prices of a Part that is 10% less than a base price, the base price, and 10% more than a base price. This list is created using the asList method.

To create the mappedParts list, a stream is created from partsList. A map function is applied to the stream where a list is created using the asList method, and then the Collector’s toList method returns the list of lists. The Collector interface is discussed in Using the Collector Interface and the collect Method.

List<Float> partsList = Arrays.asList(

new Part("Pencil", 100, 5, 0.15f, 500).getPrice(),

new Part("Eraser", 200, 3, 0.25f, 250).getPrice(),

new Part("Paper", 2000, 1, 0.03f, 1200).getPrice()

);

List<List<Float>> mappedParts =

partsList.stream().

map(p -> Arrays.asList(p-=p*0.10f, p, p+=p*0.10f)).

collect(Collectors.toList());

System.out.println(mappedParts);

![](image228.jpg)

The output of this sequence follows:

[[0.135, 0.135, 0.14850001], [0.225, 0.225, 0.24749999], [0.026999999, 0.026999999, 0.029699998]]

The flatMap method is used in the following code sequence in place of the map method. In addition, the stream method is applied to the list produced by the asList method. This allows the flatMap method to flatten out the sub-streams into a single stream.

List<Float> flatParts = partsList.stream().

flatMap(p -> Arrays.asList(p-=p*0.10f, p, p+=p*0.10f).

stream()).

collect(Collectors.toList());

System.out.println(flatParts);

![](image229.jpg)

The output follows:

[0.135, 0.135, 0.14850001, 0.225, 0.225, 0.24749999, 0.026999999, 0.026999999, 0.029699998]

It differs from the previous technique in that it uses a different return type, it uses the flatMap method instead of the map method, and the stream method is used instead of the asList method.

Using the filter Method

The filter method, as its name implies, filters out or removes elements of a stream based on some set of criteria. The method’s argument is a predicate lambda expression. In this example, a predicate is defined to determine if the weight of a part is greater than or equal to three. The forEach method is then used to display the selected elements.

Predicate<Part> weightPredicate = p -> p.getWeight() >= 3; 

partsStream.filter(weightPredicate).

forEach(System.out::println);

![](image230.jpg)

The output of this sequence is shown below:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.15 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25 Quantity:   250

A further enhancement of this approach is to filter out those elements whose price is greater than or equal to 0.15 after the parts have been given a 5% increase. This is expressed succinctly as follows. The mapper variable was previously declared in Using the map Method.

Predicate<Part> pricePredicate = p -> p.getPrice() > 0.15f;

partsStream.map(mapper).filter(pricePredicate).

forEach(System.out::println);

 ![](image231.jpg)

Multiple filters can be used together as shown below. Here only those parts whose price is greater than or equal to 0.15 and whose weight exceeds 2 will be selected.

partsStream.map(mapper).

filter(pricePredicate).

filter(weightPredicate).

forEach(System.out::println);

![](image232.jpg)

The output follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.16 Quantity:   500

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.26 Quantity:   250

Using the Match Type Methods

There are three match type methods that will effectively act as a filter operation against a stream. Each of these methods accepts a predicate that is applied against each element of the stream and returns a boolean value reflecting the success of the predicate. These include:

- allMatch – Returns true if all of the elements satisfy the predicate or if the stream is empty. Otherwise it returns false.

- anyMatch – Returns true if any element of the stream matches the predicate. Returns false if the stream is empty or no elements are found that match the predicate.

- noneMatch – Returns a boolean value indicating whether any elements of the stream match the predicate.

Below, a stream is created based on the partsList and is used with a combination of predicate lambda expressions. While the example seems to execute these methods one after another, remember that a stream cannot be reused. To make this example work, the stream has to be recreated before each execution of a match method.

Stream<Part> partsStream = partsList.stream();

System.out.println(partsStream.

allMatch(p -> p.getQuantity()<50));

System.out.println(partsStream.

anyMatch(p -> p.getQuantity()<50));

System.out.println(partsStream.

noneMatch(p -> p.getQuantity()<50));

System.out.println(partsStream.

allMatch(p -> p.getWeight()>50));

System.out.println(partsStream.

anyMatch(p -> p.getQuantity()>1000));

System.out.println(partsStream.

noneMatch(p -> p.getPrice()>.35f));

![](image233.jpg)

The output of this sequence follows:

false

false

true

false

true

true

Using the findFirst Method

The findFirst method will return the first element of a Stream. However, the stream may be empty. To handle this situation, the findFirst method returns an Optional object. This object may or may not contain a null value. The isPresent method is used to determine if it contains a value or not. The Optional’s get method returns the value or null if none are present.

In the following sequence, the first part in the stream that is greater than or equal to 0.15 will be returned and then displayed.

Stream<Part> partsStream = partsList.stream();

Predicate<Part> pricePredicate = p -> p.getPrice() > 0.15f;

Part firstPart =

partsStream.filter(pricePredicate).

findFirst().

get();

System.out.println(firstPart);

![](image234.jpg)

The output follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.16 Quantity:   500

Using the findAny Method

The findAny method also returns an Optional value. This value may be empty or it may contain any element of the stream. The element selected is nondeterministic; meaning the element selected cannot be predicted.

The following example uses the previously defined partsList and pricePredicate. A stream is created and the predicate and findAny method is executed against it.

partsStream = partsList.stream();

Part anyPart =

partsStream.

filter(pricePredicate).

findAny().

get();

System.out.println(anyPart);

![](image235.jpg)

The output may appear as follows:

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25 Quantity:   250

Using the Optional Class

The previous example assumes that a Part will be returned. A more robust technique to handle null values follows using the Optional class’ isPresent method:

Optional<Part> firstPart = partsStream.map(mapper).

filter(pricePredicate).

findFirst();

if (firstPart.isPresent()) {

System.out.println(firstPart.get());

} else {

System.out.println(

"No part meets the criteria specified");

}

![](image236.jpg)

This will duplicate the output of the earlier example.

The Optional class has several methods. One of its methods, orElse, will return a specific object if the value is null. In this example, the pricePredicate criteria is changed to filter out parts whose price is less than or equal to 0.3\. For the partsStream, this eliminates all of the parts. The orElse method will return an object specified by its argument. Since firstPart will be empty, a new substitute part is created.

pricePredicate = p -> p.getPrice() > 0.3f;

firstPart = partsStream.

map(mapper).

filter(pricePredicate).findFirst();

Part part = firstPart.

orElse(new Part("Substitute", 99999, 10, 1.5f, 50));

System.out.println(part);

![](image237.jpg)

The output will be the substitute part:

Name: Substitute Weight:  10  Part Number: 99999 Price: 1.50 Quantity:    50

The Optional class also has an orElseGet method that returns an object if the Optional value is null. The argument of the method is a Supplier implementation. The next example uses a random number to select one of the partsList elements to return.

pricePredicate = p -> p.getPrice() > 0.3f;

Supplier<Part> supplier = () -> {

Random random = new Random();

return partsList.get(random.nextInt(partsList.size()));

};

Part part = firstPart.orElseGet(supplier);

System.out.println(part);

![](image238.jpg)

One possible output follows:

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.16 Quantity:   500

Another potentially useful Optional class method is the orElseThrow method. As the name implies, it will throw an exception if the Optional value is null. The argument of the method should be the exception to throw.

The following illustrates this method where a PartException is thrown. The nextInt’s argument has been set to 200 to increase the likelihood that an exception will be thrown. The exception is thrown when the index into partsList is too large.

class PartException extends Exception {

}

Supplier<Part> supplier = () -> {

Random random = new Random();

return partsList.get(random.nextInt(200));

};

try {

Part part = firstPart.orElseThrow(PartException::new);

System.out.println(part);

} catch (PartException ex) {

ex.printStackTrace();

}

![](image239.jpg)

If the get method’s argument exceeds the size of the partsList, the PartException will be thrown.

Using the reduce Method

The reduce method, as its name implies, will reduce a stream to a single value and returns it as Optional. There are three overloaded reduce methods. We will demonstrate two of these methods here.

The following example uses a BinaryOperator to perform the reduction. A stream is created from a list of integers. The reduce method reduces two arguments to their sum. This operation is applied consecutively to each element of the stream. The return value is an Optional. Its get method is used to return the effective sum of the elements of the stream.

List<Integer> list = Arrays.asList(1, 2, 3, 4);

Optional<Integer> result = list.stream().

reduce((n1, n2) -> n1 + n2);

System.out.println(result.get());

![](image240.jpg)

The output of this sequence will be a 10.

The next example illustrates the same technique applied to strings. The effect is to concatenate the elements together separated by a dash.

List<String> nameList =

Arrays.asList("Bob", "Carol", "Ted", "Alice");

Optional<String> name = nameList.stream().

reduce((n1, n2) -> n1 + "-" + n2);

System.out.println(name.get());

![](image241.jpg)

The output of this example follows:

Bob-Carol-Ted-Alice

The following reduce method performs a similar summation operation but is based on an initial accumulator value as the first argument of the method. The second argument is a BinaryOperator that is applied to the elements of the stream. The effect of this example is to compute the product of the elements.

List<Integer> productList = Arrays.asList(1, 2, 3, 4);

Integer productResult = productList.

stream().

reduce(1, (n1, n2) -> n1 * n2);

System.out.println(productResult);

![](image242.jpg)

Its output will be 24.

Using the Collector Interface and the collect Method

The Collector interface is an abstract version of a reduce type operation. The reduction operation results in a mutable result. This can be performed in either a sequential or parallel manner.  However, creating a Collector can be difficult. This task is made easier by the java.util.stream.Collectors class. It is a utility class whose methods return Collector objects and supports a number of reduction type operations.

The Stream interface’s collect method is useful when the elements of a stream need to be placed into a Collection, Map, or String. It frequently uses an instance of the Collector interface to gather elements of a stream.

There are two overloaded collect methods available. The first accepts a Collector and the second accepts three arguments: a Supplier and two BiConsumer objects. Let’s examine the use of a Collector first.

In this example, a stream of Parts is created. The map method is used to obtain the name of each part. This is followed by the use of the Collectors utility class’ toList method to create the actual list. The list is then assigned to the partList variable.

List<Part> partsList = Arrays.asList(

new Part("Pencil", 100, 5, 0.15f, 500),

new Part("Eraser", 200, 3, 0.25f, 250),

new Part("Pen", 500, 3, 0.35f, 350),

new Part("Paper", 2000, 1, 0.03f, 1200)

);

Stream<Part> partsStream = partsList.stream();

List<String> partList =

partsStream.

map(Part::getName).

collect(Collectors.toList());

for (String element : partList) {

System.out.println(element);

}

![](image243.jpg)

The output of this sequence will appear as shown below:

Pencil

Eraser

Pen

Paper

Another use of the Collectors class is to generate a set of values. In the following example a TreeSet of strings are created based on the name of the part.

partsStream = partsList.stream();

TreeSet<String> partTree =

partsStream.

map(Part::getName).

collect(Collectors.toCollection(TreeSet::new));

partTree.stream().forEach(p -> System.out.println(p));

![](image244.jpg)

The output of this sequence follows:

Eraser

Paper

Pen

Pencil

The creation and use of a Map is shown below. A map of a list of parts grouped by their weights is created. The contains method is used to determine if a grouping, where the weight is 3, exists. This list is then displayed.

partsStream = partsList.stream();

Map<Integer,List<Part>> partMap =

partsStream.

collect(Collectors.groupingBy(Part::getWeight));

if(partMap.containsKey(3)) {

partMap.get(3).forEach(p->System.out.println(p));

}

![](image245.jpg)

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25 Quantity:   250

Name: Pen      Weight:   3  Part Number:   500 Price: 0.35 Quantity:   350

Using the Collects Class

The Collects class possesses a number of useful methods for creating Collector objects from a stream. The types of operations available include:

- Averaging primitives

- Counting the number of elements in a stream

- Grouping by some value

- Joining elements into a string

- Mapping the element of a stream

- Producing a maximal or minimal element

- Partitioning a stream into a map

- Reducing elements of a stream

- Summing the elements of a stream or producing summary statistics for the stream

- Producing a Collector that contains a List, Map, or Set

While not demonstrated here, we will demonstrate some of these methods in later sections.

Using the iterator Method

The Iterator method is found in the Stream interface’s base interface BaseStream. Its intent is to provide a way of obtaining an Iterator object that can be used to iterate through the stream. This should not normally be needed as the Stream interface’s methods provide better support than the older approach.

The following example illustrates how the method can be used with a stream of integers. The first part shows the use of the iterator method and uses it to display the elements of the list in a while loop. The last two statements demonstrate how much easier it is to use the forEach method to achieve the same result.

List<Integer> numbers = Arrays.asList(10,20,30,40);

Stream<Integer> numberStream = numbers.stream();

Iterator iterator = numberStream.iterator();

while(iterator.hasNext()) {

System.out.println(iterator.next());

}

numberStream = numbers.stream();

numberStream.forEach(n -> System.out.print(n + " "));

![](image246.jpg)

The output of both techniques is identical and is shown below:

10 20 30 40

Using the sorted Method

The sorted method will return a stream that is sorted. There are two overloaded sort methods. If the stream executed against the element type supports a natural order, the sort method with no arguments can be used. For example, as shown below, a list of numbers is created, sorted, and then displayed:

List<Integer> numberList =

Arrays.asList(23, 54, 12, 5, 24);

numberList.stream().

sorted().

forEach(n -> System.out.print(n + " "));  

![](image247.jpg)

The output is as follows:

5 12 23 24 54

If, however, the element does not have a natural order, or a different comparison technique is desired, then the second overloaded sort method can be used as shown below. This method takes a Comparator as its argument. In this example the parts are sorted by name in ascending order.

Stream<Part> partsStream = partsList.stream();

Comparator<Part> partComparator =

 (p1, p2) -> p1.getName().compareTo(p2.getName());

 partsStream.sorted(partComparator).

 forEach(System.out::println);

![](image248.jpg)

The output of this sequence follows:

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25 Quantity:   250

Name: Paper    Weight:   1  Part Number:  2000 Price: 0.03 Quantity:  1200

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.15 Quantity:   500

Using the distinct Method

The distinct method is used to return a stream where any duplicate elements of the original stream are removed. Duplicate elements are determined by applying the equals method to the elements. The following code sequence using this method:

List<Integer> numbers =

Arrays.asList(19, 12, 23, 31, 12, 4, 23, 31);

numbers.stream().

distinct().

forEach(n -> System.out.print(n + " "));

![](image249.jpg)

The output is shown below:

19 12 23 31 4

Using the limit Method

Sometimes it is desirable to limit the number of elements processed in a stream. The limit method is used for this purpose. Its long argument determines how many elements will be returned.

The following example restricts output to the top 5 numbers in a list. A lambda expression is used to sort the numbers from high to low and then the top five numbers are displayed.

List<Integer> numberList =

Arrays.asList(23, 54, 12, 5, 24, 32, 89, 21, 83);

numberList.stream().

sorted((n1, n2) -> (n1>n2)?-1:1).

limit(5).

forEach(n -> System.out.print(n + " "));

![](image250.jpg)

The output follows:

89 83 54 32 24

The following example will return a list of numbers where the three largest and the three smallest numbers have been removed. This list will be in descending order. The stream, tmpStream, is created - first sorting the numbers in ascending order and then removing the last three elements using the limit method. The tmpStream is then used to create a stream in descending order and once again the limit method will cut off the last three elements of the stream.

List<Integer> numberList =

Arrays.asList(23, 54, 12, 5, 24, 32, 89, 21, 83);

Stream<Integer> tmpStream= numberList.stream().

sorted((n1, n2) -> (n1>n2)?1:-1).

limit(numberList.size() - 3);

tmpStream.

sorted((n1, n2) -> (n1>n2)?-1:1).

limit(numberList.size() - 6).

forEach(n -> System.out.print(n + " "));

![](image251.jpg)

The output will be as follows:

32 24 23

Using the skip Method

The skip method will skip over the elements at the beginning of a stream. The number of elements skipped is specified by its long argument.

The following example will duplicate the previous example but it uses the skip method instead. It will return a list of numbers where the three largest and the three smallest numbers have been removed. This list will be in descending order. The stream, tmpStream, is created first sorting the numbers in ascending order and then removing the first three elements using the skip method. The tmpStream is then used to create a stream in descending order and once again the skip method will remove the first three elements of the stream.

List<Integer> numberList =

Arrays.asList(23, 54, 12, 5, 24, 32, 89, 21, 83);

Stream<Integer> tmpStream = numberList.stream().

sorted((n1, n2) -> (n1>n2)?1:-1).

skip(3);

tmpStream.

sorted((n1, n2) -> (n1>n2)?-1:1).

skip(3).

forEach(n -> System.out.print(n + " "));

![](image252.jpg)

The output will be as follows:

32 24 23

Using the max, min, and count Methods

The max and min methods will return the largest and smallest elements, respectfully, from a stream as determined by their Comparator argument. These methods are easy to demonstrate using a list of integers as shown below. Lambda expressions are used for the Comparator to determine the relative ranking of the integers. These methods return an Optional, so the get method is used to return the integer value.

List<Integer> numberList =

Arrays.asList(23, 54, 12, 5, 24, 32, 89, 21, 83);

System.out.println(numberList.stream().

max((n1, n2) -> (n1>n2)?1:-1).get());

System.out.println(numberList.stream().

min((n1, n2) -> (n1>n2)?1:-1).get());

![](image253.jpg)

The first println statement will return 89 while the second returns 5.

The count method will return a long value reflecting the number of elements in the stream. A simple example follows:

List<Integer> numberList =

Arrays.asList(23, 54, 12, 5, 24, 32, 89, 21, 83);

System.out.println(numberList.stream().count());

![](image254.jpg)

A 9 will be displayed.

Streams for Primitive Types

The Stream interface is a generic type of interface and is useful for many types of problems. When a stream needs to be used with a primitive, a lot of boxing and unboxing is required. As a result, when a large amount of data needs to be processed, using the Stream interface may not be the best solution.

To address this problem, several stream interfaces designed to work with primitive data have been provided. These include: IntStream, LongStream and DoubleStream. These are often returned when mapping from a generic class to a primitive data type. Several functional interfaces have been added to support this type of conversion including ToIntFunction, IntConsumer, and IntSupplier. Other primitive stream interfaces, such as for boolean and short, were not added. It was felt that the three primitive streams were adequate and other primitives could be addressed using other techniques.

Primitive stream interfaces possess a number of common operations including, among others:

- count

- sum

- min

- max

- mean

There is also the IntSummaryStatistics class that provides summary statistics on a stream of integers. In addition, there are corresponding DoubleSummaryStatistics and LongSummaryStatistics classes.

Using the IntStream Interface

The IntStream interface supports operations using integers and possesses a number of useful methods. The following illustrates an implicit use of the IntStream interface. A stream of parts is created and the mapToInt method is applied against this. This will return an IntStream object. The sum method is then applied to the new primitive stream and returns the sum of the weights of all of the parts in the stream.

Stream<Part> partsStream = partsList.stream();

int sumOfWeights = partsStream.mapToInt(

(Part p) -> p.getWeight()).sum();

System.out.println("Sum: " + sumOfWeights);

![](image255.jpg)

The output will be as follows:

Sum: 9

The following explicitly uses an IntStream to achieve the same results:

IntStream tmpStream = partsStream.mapToInt(

(Part p) -> p.getWeight());

System.out.println("Sum: " + tmpStream.sum());

![](image256.jpg)

Understanding Lazy and Eager Evaluation

Streams are evaluated in a lazy fashion. This means that most operations against streams are deferred until results are actually needed. Without lazy evaluation, streams could not be infinite.

For example, consider the earlier findFirst example duplicated below. The map and filter operations process only one element at a time until the first match occurs. The entire stream is not processed. Intermediate methods are not executed until some terminal method is called.

Optional<Part> firstPart = partsStream.map(mapper).

filter(pricePredicate).findFirst();

![](image257.jpg)

An eager evaluation occurs when operations are performed on every element in a stream. Sometimes this is needed. For example, the forEach method processes every element in a stream.

There are times when it is better to process a stream in a lazy fashion and times when it needs to be processed eagerly. By moving looping operations inside streams and certain collections, the system is able to optimize these operations applying eagerness or laziness as appropriate.

Using Short-Circuit Methods

The evaluation of a stream is done in a short-circuit manner. An entire stream may not be processed but will terminate early when it can. Short-circuit methods include:

- anyMatch

- allMatch

- noneMatch

- findFirst

- findAny

- limit

- substream

Using Parallel Stream Operations

One of the benefits of using streams is their potential support of the concurrent execution of stream operations. Traditional collection methods are not always thread-safe. Often explicit thread synchronization mechanisms must be used to address the potential corruption of data. The use of synchronization can introduce thread contention issues. Parallel stream operations can avoid these issues if the collection being acted on is not modified.

Bear in mind that the concurrent execution of stream operations does not necessarily mean that an application will run faster. For small collections, the overhead involved in supporting parallel execution may be larger than the time required to perform the same set of operations in a sequential manner.

When a stream is parallelized, the run-time environment will split the stream into multiple parts, execute each part on a separate processor, and then combine the results. Operations on a stream are performed sequentially by default. To affect parallel execution either the Collection interface’s parallelStream method or the BaseStream interface’s parallel method needs to be used.

Let’s start with the following declarations of a list and stream:

List<Part> partsList = Arrays.asList(

new Part("Pencil", 100, 5, 0.15f),

new Part("Eraser", 200, 3, 0.25f),

new Part("Paper", 2000, 1, 0.03f),

new Part("Pen", 200, 3, 0.25f),

new Part("Staple", 3000, 1, 0.01f)

);

Stream<Part> partsStream = partsList.stream();

![](image258.jpg)

A sequential stream that filters out those parts whose weight is less than 3 is shown below:

partsStream.filter(

 (p)->p.getWeight()>=3).

forEach(p -> System.out.println(p));

![](image259.jpg)

The same operation performed, using a parallel stream, uses the parallel method as seen here:

partsStream.parallel().

filter((p)->p.getWeight()>=3).

forEach(p -> System.out.println(p));

![](image260.jpg)

The output of both of these sequences follows and is identical for each example:

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25

Name: Pencil   Weight:   5  Part Number:   100 Price: 0.15

However, converting a sequential stream to a parallel stream is not always this simple. Reduction type operations need to be handled more carefully. In the following example a Map is created whose key is an integer weight. The groupingBy method will return a list whose members have the same weight. These lists are then assigned to the map.

Map<Integer, List<Part>> groupByWeight =

partsStream.collect(

Collectors.groupingBy(Part::getWeight));

for(Part part : groupByWeight.get(3)) {

System.out.println(part);

}

![](image261.jpg)

The output follows:

Name: Eraser   Weight:   3  Part Number:   200 Price: 0.25

Name: Pen      Weight:   3  Part Number:   200 Price: 0.25

To achieve the same results using a parallel stream requires a couple of modifications as shown below. To improve the performance of the operation, a ConcurrentMap is needed and the groupingByConcurrent method should be used.

ConcurrentMap<Integer, List<Part>> groupByWeight =

partsStream.parallel().collect(

Collectors.groupingByConcurrent(Part::getWeight));

for (Part part : groupByWeight.get(3)) {

System.out.println(part);

}

![](image262.jpg)

To affect concurrent reduction, the following rules need to be considered:

- The stream is a parallel stream

- The collector used has the characteristic: CONCURRENT

- The stream should be unordered

For a stream to take advantage of multiple processors, a parallel stream needs to be used. However, when using a parallel stream:

- Be aware of adverse side effects

- Avoid stateful lambda expressions

A side effect can occur in a stream when one of its operations modifies the state of the application. Operations such as the println method and mutable reductions have side effects. Most side effects are handled within a stream. However, problems can occur when a stream operation modifies the source of the stream. This is called interference.

In the following example, an attempt is made to modify the original partsList, using the add method as part of the predicate operation:

partsList.stream().

filter((p)->{

partsList.add(p);

return p.getWeight()>=3;}).

forEach(p -> System.out.println(p));

![](image263.jpg)

This will generate a java.lang.UnsupportedOperationException exception when the statement is executed. Modifying a different list will not result in an exception.

A stateful lambda expression is one where the results are dependent on a state that might change during the execution of the lambda expressions. For example, the value returned by the following filter operation depends on some external condition:

boolean someCondition = …;

partsStream.parallel().

filter(p -> {

if (someCondition) {

return true;

} else {

return false;

}

}).

forEach(p -> System.out.println(p));

![](image264.jpg)

Conclusion

A stream is a collection of elements. The elements of a stream can be of any type. Operations are performed on its elements in a pipeline fashion. This can result in a more natural and concise solution to a problem. In addition, when executed as a parallel stream it will execute faster.

A stream must first be created. A stream can be created from multiple sources including arrays and lists. The length of a stream can be unbounded but once a stream has been processed it cannot be reused.

There are numerous operations that can be applied against the elements of a stream. These include operations such as transforming an element, filtering elements, reducing elements, or limiting the size of the stream. Operations can be chained together to create a pipeline. In addition, lambda expressions are frequently used with streams to improve the flexibility and expressiveness of streams.

When a stream is parallelized, care must be taken to ensure that it will function as intended. Any collectors used must be concurrent and the stream should be unordered. In the next chapter we will examine the improvements to how date and time are handled.

* * * * *

Chapter 4 – Date and Time

-Introduction

--Why a New API?

--A Simple Example

--The ISO-8601 String Format

--Design Considerations

--Understanding the Standard Method Names

---Understanding the of Type Methods

---Understanding the from Method

---Understanding the parse Method

---Understanding the format Method

---Understanding the get Type Method

---Understanding the is Type Methods

---Understanding the with Type Methods

---Understanding the plus Type Methods

---Understanding minus Type Methods

---Understanding the to Type Methods

---Understanding the at Type Methods

--Overview of the Date and Time Packages

-Getting the Current Time

--Working with the Instant Class

---Creating an Instant

---Creating an Instant Based on the Epoch

---Creating an Instant Based on Parsing a UTC String

---Creating an Instant by Adding or Subtracting a Time from an Instant

---Using the Instant Class’ get Type Methods

--Working with Time Intervals

---Creating Offsets Using the of Type Methods

---Creating Offsets Using the with Type Methods

---Creating a Duration Using the parse Method

---Creating a Duration by Adding or Subtracting a Unit

---Using the Duration Class

--Using the Period Class

-Using Date and Time Classes

--Creating Date and Time Classes

---Date and Time get Type Methods

---Adjusting a Date or Time

--Using the YearMonth, MonthDay, and Year Classes

---Comparing MonthDay Instances

--Using the Enumerations DayOfWeek and Month

---Using the DayOfWeek Enumeration

---Using the Month Enumeration

-Working with the Time Zone and Offset Classes

--Obtaining Available Zone Ids

--Working with ZoneOffsets

--Working with Zone Rules

-Formatting, Queries, and Value-Based Classes

--Formatting Dates and Times

--Using Temporal Queries

--Understanding Value-Based Classes

-Conclusion

Introduction

A significant addition to Java 8 is the introduction of the new date and time API intended to replace the existing java.util.Date and java.util.Calendar classes.  It is based on the Joda (http://joda-time.sourceforge.net/) effort and is a large and rich API. Complete documentation of the API can be found at http://download.java.net/jdk8/docs/api/.

The date and time API is based on the ISO-8601 standard ([http://www.iso.org/iso/home/standards/iso8601.htm](http://www.iso.org/iso/home/standards/iso8601.htm)) which uses the Gregorian calendar, the de facto date standard used throughout the world. The standard provides a way of expressing dates and handles leap years as well. However, it is not appropriate to use it to represent historical dates. Other calendar systems are supported in the java.time.chrono package.

Coordinate Universal Time (UTC) is the primary time standard in use today. It incorporates time zones and uses a time offset from UTC which is found along zero degrees longitude. The term, temporal-based, refers to classes such as LocalDate and ZonedDateTime which reflect different ways of expressing time.

There are several ways of organizing a discussion of the API. Time can be understood from a human perspective using measurements such as months and seconds. It can also be understood from the perspective of a computer. This measurement typically measures time from the epoch (January 1, 1970) in units such as milliseconds or nanoseconds. Both of these two perspectives are supported by the API giving the developer the option of using the most appropriate approach based on the context of the problem. These two types can be referred to as human time and machine time.

Human time is generally preferred when working with days as found in a calendar. Machine time is often preferred when dealing with durations of time such as the number of milliseconds between two events. However, it could also be expressed in human time such as the difference between two days.

An instant is an instantaneous point along a timeline. You can use this to represent events or at least the point in time the event occurs. It can be thought of as an event timestamp.

We also talk about time in terms of how long an activity occurs. Java 8 uses a Duration class to designate intervals measured in units like minutes or seconds. Duration can be used for a range such as the time it takes to open a valve or the length of an animation cycle. There is also the Period class that deals with intervals measured in days and months.

Many of the examples used in this chapter are dependent on the current date and time. As a result, the output of these examples may not reflect today’s date or time. However, they should reflect the current date and time when executed.

Why a New API?

The date and time classes available before Java 8 had a number of problems. For example, they were mutable which made them difficult to work with across threads. They were often not type safe and the internal numbers used to represent units such as months made them difficult to work with. It has also been difficult to support internationalization with the older Java date and time classes.

A Simple Example

Let’s start with an example that determines whether an individual is currently working. The worker is located in La Paz Bolivia, starts work at 8:00 in the morning and works for 6 hours. We want to call the individual from some other location, but before we call we want to make sure that they are scheduled to work.

First we need to determine the current time. We could use the DateTime class but this class does not include time zone information. So we use the ZonedDateTime class. It possesses a now method that returns an instance of the class representing the current date and time at our location. The following code sequence illustrates how this is done and then displays this date and time:

ZonedDateTime present = ZonedDateTime.now();

System.out.println(present);

![](image265.jpg)

The output that follows uses the ISO 8601 date and time representation scheme:

2014-03-05T19:50:14.613-06:00[America/Chicago]

The output string starts with date: March 3, 2014\. The 'T' demarks the beginning of the time expression. In this case it represents a time of 7:50 PM plus 14 minutes and 0.613 seconds. The next sequence, -06:00, shows the offset from UTC. The last part of the expression lists the time zone enclosed in brackets.

We need to represent the start time and duration of the worker in La Paz. To get this representation we start by creating a ZoneId object that represents the time zone. This is followed by the start time using a LocalTime object, and the length of the employee’s shift using a Duration object. These objects are created as follows:

ZoneId timeZone = ZoneId.of("America/La_Paz");

LocalTime startWorkDay = LocalTime.of(8,0);

Duration dailyTime = Duration.ofHours(6);

![](image266.jpg)

To determine if the employee is working, we need a start time and an end time that is based on his time zone. There are several ways of creating these two times. In the following code sequence, we first create a LocalDate called employeeDate, used to represent a day, month, and year value. It is then used with the startWorkDay and timeZone variables to create a start time of type ZonedDateTime. This date and time is then displayed using the DateFormatter class. The ofLocalizedDateTime method is passed a format style of LONG. This class controls how the date and time is displayed.

LocalDate employeeDate =

LocalDate.of(LocalDate.now().getDayOfYear(),

LocalDate.now().getMonth(),

LocalDate.now().getDayOfMonth());

ZonedDateTime startTime = ZonedDateTime.of(

employeeDate,

startWorkDay, timeZone);

System.out.println("Start: " +

startTime.format(

DateTimeFormatter.

ofLocalizedDateTime(FormatStyle.LONG)));

![](image267.jpg)

The output is shown below. The 0064 field is the number of days from the start of the year.

Start: March 5, 0064 8:00:00 AM BOT

The end time is calculated by adding the dailyTime duration to the start time as follows.

ZonedDateTime endTime = startTime.plusHours(

dailyTime.toHours());

System.out.println("End: " +

endTime.format(

DateTimeFormatter.ofLocalizedDateTime(

FormatStyle.LONG)));

![](image268.jpg)

The end time is shown below:

End: March 5, 0064 2:00:00 PM BOT

The last step is to use the compareTo method with the start, end, and present times to determine if the employee is working. This method returns a negative value if the time specified by its argument follows either the start or end times. It returns a positive value if it follows the target time. The following expression will return false based upon these sets of dates and times:

System.out.println(

(startTime.compareTo(present) <= 0) &&

(endTime.compareTo(present) >= 0));

![](image269.jpg)

The ISO-8601 String Format

This format is used with several methods of the API. Its format is shown below:

PnDTnHnMn.nS

The letters correspond to the following units: Period, Days, Hours, Minutes, and Seconds. The ‘n’ represents the number of units and precedes the corresponding unit symbol. The ‘T’ must be present before the use of an hour, minute, or second field. The letters are case-insensitive. Fields can be left out but must appear in the order listed above. The period separating the seconds from the first part of the string, may use 0 to 9 digits. An optional plus or minus can be used to affect an addition or subtraction. Days are exactly 24 hours in length. Table 1 - Period Format Examples provides several examples of how they can be used.

***Table 1 - Period Format Examples***

**Formatted String |** Meaning

**"P3DT13H5M"** | 3 days, 13 hours and 5 minutes

**"PT8H"** | 8 hours

**"P24D"** | 24 days

**"PT15.012S"** | 15 seconds and 12000000 nanoseconds

**"-P-3H+42M"** | +3 hours and -42 minutes

![](image270.jpg)

Design Considerations

The date and time API is based on four design considerations:

1\. Methods should be easy to understand

2\. A fluent style of programming should be supported

3\. Objects should be immutable

4\. The API should be extendable

The methods of the API are written to be easily understood and clear to a user. They should be as consistent between classes as possible. These names themselves have been standardized as much as possible and are shown in Table 2 - Method Naming Convention Summary.

A fluent style of programming is supported to make it easier to use. Fluency is supported by chaining easy-to-understand methods together making them easy to learn.

Most of the objects created using the classes of the API are immutable. The chief advantage of this design decision is that they are thread-safe. Constructors often are not available which means static factory type methods are frequently used. Immutable objects are easy to construct and are good for hash keys.

Most of the API classes possess methods that appear to modify a date or time object. However, these methods use the object they are executing against, perform any adjustment to this date or time, and then return a new object. The original object, being immutable, is not modified.

The API provides the developer with the ability to extend and create unique calendar systems when needed. This allows extension of the API to address unique needs as they arise.

Understanding the Standard Method Names

The purpose of this section is to provide a high level overview of the methods used by the API. Understanding the intent of these names will make them easier to use. It will become more obvious which methods should be used in a given situation.

The API classes and interfaces possess a number of methods with similar, if not identical, names. This is done to promote their readability and ease of use. Table 2 - Method Naming Convention Summary summarizes these methods.

The of, from, and parse type methods are static factory methods and provide the primary tool for the creation of date and time objects. The other methods are instance methods and provide techniques to format, get fields, return modified objects, or otherwise transform one object into a different type.

Many of these methods are overloaded or use the same prefix. To assist you in putting these methods into perspective, various tables are found in Appendix A which have organized these methods by type.

***Table 2 - Method Naming Convention Summary***

Type | **Prefix** | Use

Creation | **of**  | Creates an instance based on its parameters

Creation | **from**  | Creates an instance where some information may be lost

Creation | **parse**  | Creates an instance by parsing an input string

Formatting | **format**  | Returns a formatted string

State Information | **get**  | Returns a state of the target object

State Information | **is**  | Returns a boolean value relating to the state of the object

Modification | **with**  | Returns a new object that differs by one element

Modification | **plus**  | Returns a new object with a time unit added

Modification | **minus**  | Returns a new object with a time unit subtracted

Modification | **to**  | Converts the target object to a different type

Modification | **at**  | Combine the object with another to produce a new object

![](image271.jpg)

Understanding the of  Type Methods

The of type methods are similar in usage. They differ in their arguments and return types. They are all static and return an instance of that class. The of Type Methods section in Appendix A provides a list of type methods that are available. The following code sequence illustrates how an instance of the LocalDate class can be created using this method. The integer arguments correspond to year, month, and day.

LocalDate localDate = LocalDate.of(2014, 3, 6);

![](image272.jpg)

Understanding the from Method

The from method is very consistent in its signature from class to class with the exception of the Duration class. Each from method is a static method that returns an instance of the class it executes against. Each from method accepts a TemporalAccessor object as an argument with the exception of the Duration class which uses a TemporalAmount object. The from Method section in Appendix A provides a list from type methods that are available.

The following sequence creates a LocalDate from a LocalDateTime:

LocalDateTime ldt = LocalDateTime.now();

LocalDate localDate = LocalDate.from(ldt);

![](image273.jpg)

Understanding the parse Method

The static parse method is fairly consistent between those implementing classes. It uses either one or two arguments. The first argument is always a CharSequence. When the second argument is present, it is a DateTimeFormatter instance. The parse Method section in Appendix A provides a list of parse methods that are available.

In this example, the parse method is executed against an Instant to create a date at midnight January 1, 2010.

Instant instant = Instant.parse(

"2010-01-01T00:00:00.000Z");

![](image274.jpg)

Understanding the format Method

The format method is used by classes which support human readable dates and time. It uses a DateTimeFormatter instance which controls how the date is formatted. In the following example, the ISO_DATE format is used:

LocalDate localDate = LocalDate.of(2014, 3, 6);

System.out.println(

localDate.format(DateTimeFormatter.ISO_DATE));

![](image275.jpg)

The output appears as follows:

2014-03-06

The following classes possess this method: LocalDate, LocalDateTime, LocalTime, MonthDay., OffsetDateTime, OffsetTime, Year, YearMonth, ZonedDateTime.

Understanding the get Type Method

The get type methods return information about an object. The methods supported depend on the needs of the class. The get Type Methods section in Appendix A provide a list of get type methods that are available.

In the following example, the day of the year is returned based on a LocalDate object:

LocalDate localDate = LocalDate.of(2014, 3, 6);

int dayOfYear = localDate.getDayOfYear();

System.out.println(dayOfYear);

![](image276.jpg)

The output will be 65. Specific get methods are discussed in their respective class discussions.

Understanding the is Type Methods

The is type methods all return a boolean value. The actual method supported by a class is dependent on the requirements of the class. The is Type Methods section in Appendix A provides a list of is type methods that are available.

To demonstrate the isAfter method, we create an Instant that represents the current date and time as shown below. This is then compared to the epoch.

Instant now = Instant.now();

System.out.println(now.isAfter(Instant.EPOCH));

![](image277.jpg)

The output will be true.

Understanding the with Type Methods

These methods always return an instance of the class they execute against. The methods supported vary by class. In general, they return a modified version of the original class. The with Type Methods section in Appendix A provides a list of with type methods that are available.

In the following code sequence, the last day of the month is determined using a TemporalAdjusters. This class provides a number of interesting methods to adjust a date to a different value.

LocalDate localDate = LocalDate.of(2014, 3, 6);

LocalDate endOfMonth =

localDate.with(

TemporalAdjusters.lastDayOfMonth());

System.out.println(endOfMonth.toString());

![](image278.jpg)

The output will be:

2014-03-31

Understanding the plus Type Methods

These methods return a new object after adding a time unit to an existing object. The object returned is of the same type as the object the method was executed against. The methods supported depend on the class. The plus Type Methods section in Appendix A provides a list of plus type methods that are available.

In this example, one day is added to the localDate:

LocalDate localDate = LocalDate.of(2014, 3, 6);

LocalDate nextDay = localDate.plusDays(1);

![](image279.jpg)

Specific examples will be provided in the respective class sections.

Understanding minus Type Methods

The minus type methods all return the same type of class that they execute against. The object returned is a new object that is based on the original object where a unit of time has been subtracted. The methods supported are dependent on the class. The minus Type Methods section in Appendix A provides a list of minus type methods that are available.

In this example, one day is subtracted from localDate:

LocalDate localDate = LocalDate.of(2014, 3, 6);

LocalDate previousDay = localDate.minusDays(1);

![](image280.jpg)

Understanding the  to Type Methods

These types of methods are transformational in nature. They return different types depending on their purpose. The to Type Methods section in Appendix A provides a list of to type methods that are available.

In this example, the number of days from the epoch is calculated based on the localDate:

LocalDate localDate = LocalDate.of(2014, 3, 6);

System.out.println(localDate.toEpochDay());

![](image281.jpg)

The output will be 16135. This means that the date occurs 16135 days after the epoch.

Understanding the at Type Methods

The at type methods perform a transformation of one type to another using the provided arguments. The methods are specific to the class. The at Type Methods section in Appendix A provides a list of at type methods that are available.

In the following code sequence the start of the day is calculated and returned:

LocalDate localDate = LocalDate.of(2014, 3, 6);

System.out.println(localDate.atStartOfDay());

![](image282.jpg)

The output shown below indicates a time of midnight (“T00:00”):

2014-03-06T00:00

Overview of the Date and Time Packages

Table 3 - Date and Time Packages Overview summarizes the date and time packages introduced to Java 8\. The classes of the API are summarized in Table 4 - Date and Time Class Overview. They are organized by their type to provide an overview of what is available and how instances of the class can be used.

***Table 3 - Date and Time Packages Overview***

**Package |** Description

**java.time |** Many of the commonly used classes for date and time are found here. They are all immutable.

**java.time.chrono |** This package supports non-Gregorian and user-designed calendar systems

**java.time.format |** This package support the formatting and parsing of date and time information

**java.time.temporal |** Intended to be used by framework and library writers

**java.time.zone |** Deals with time zones

![](image283.jpg)

***Table 4 - Date and Time Class Overview***

**Category |** Class **| Use**

**General |** Clock **| Provides access to the current date, time, and time zone**

**General |** Instant **| A point in time in terms of milliseconds**

**Dates and Time |** LocalDate **| Provides access to a date without time**

**Dates and Time |** LocalDateTime **| Provides access to a date and time**

**Dates and Time |** LocalTime **| Provides access to a time without a date**

**Dates and Time |** OffsetDateTime **| Offsets using date and time units**

**Dates and Time |** OffsetTime **| Offset using time units**

**Dates and Time |** Year **| Represents a year**

**Dates and Time |** YearMonth **| Represents a year and month**

**Duration and Periods |** Duration **| Measurement of a period of time in nanoseconds**

**Duration and Periods |** Period **| Measurement of a period of time in easier to use units**

**Time Zone Related |** ZonedDateTime **| Date and time with a time zone**

**Time Zone Related |** ZoneId **| Represents a time zone**

**Time Zone Related |** ZoneOffset **| Represents a time zone as an offset from UTC**

**Enumerations |** Month **| Represents the months of the year: January through December**

**Enumerations |** DayOfWeek **| Represents the 7 days of the week: Monday through Sunday**

![](image284.jpg)

Getting the Current Time

The current time is represented by an instance of the Clock class. This class is used to create a time or date based on a time zone. It is an abstract class that allows alternative clocks to be used instead of the system clock. Many date and time classes possess a now method that uses the system clock along with the current time zone to create an instant.

This class can be used to get a date or time in the future. This can be useful when testing an application. An application can be tested with a specific date to better determine how the application will behave when time sensitive changes are applied.

The Clock class’ static systemDefaultZone method will return an instance of a Clock based on the current system clock. It will use a date and time based on the default time zone. In the following example an instance of  Clock is created:

Clock clock = Clock.systemDefaultZone();

System.out.println(clock);

![](image285.jpg)

This sequence will output the following indicating that it is a system clock and the current time zone:

SystemClock[America/Chicago]

The next example uses the millis method to return the number of milliseconds that has elapsed from the epoch as specified by the date and time. This number by itself is normally not of immediate use. The example also uses the instant method that returns an Instant object representing the clock time. The Instant class is discussed in the Working with the Instant Class section.

System.out.println(clock.millis());

System.out.println(clock.instant());

![](image286.jpg)

The output of this sequence follows:

1393774319282

2014-03-02T15:31:59.282Z

If we want to specify a time zone, we use the static system method with a ZoneID object. The ZoneId class is covered in more depth in the Obtaining Available Zone IDs section. In the following example, the ZoneId class’ of method is supplied a human readable string representing a time zone.

clock = Clock.system(ZoneId.of("Asia/Jakarta"));

System.out.println(clock);

System.out.println(clock.getZone());

System.out.println(clock.instant());

![](image287.jpg)

The output of this sequence follows:

SystemClock[Asia/Jakarta]

Asia/Jakarta

2014-03-02T16:15:45.830Z

An alternative technique uses the withZone method. In the following code sequence, this method is applied using the same time zone. The withZone method creates a new object based on the object it is applied against. The same date and time are used but are adjusted to the new time zone.

Clock clock = Clock.systemDefaultZone();

clock = clock.withZone(ZoneId.of("Asia/Jakarta"));

System.out.println(clock);

System.out.println(clock.getZone());

System.out.println(clock.instant());

![](image288.jpg)

Its output will be identical to the previous example.

We can also create an instant based on whole minutes or seconds. The following example illustrates creating an instant using the tickMinutes method where the time is expressed in whole minutes:

clock = clock.tickMinutes(ZoneId.of("Asia/Jakarta"));

System.out.println(clock);

System.out.println(clock.instant());

![](image289.jpg)

The output follows showing whole minutes with zeroes for seconds:

TickClock[SystemClock[Asia/Jakarta],PT1M]

2014-03-02T16:15:00Z

Working with the Instant Class

An instant is a point in time measured in the number of nanoseconds that have elapsed since the epoch. Negative values represent instants before the epoch and positive values represent time after the epoch. The Instant class supports this concept and provides a way of creating a time event using the machine timeline.

There are three Instant constants as listed in Table 5 - Instant Constants.

**Table 5 -** ***Instant Constants***

**Constant |** Meaning

**EPOCH |** An Instant representing the epoch (1970-01-01T00:00:00Z)

**MAX |** An Instant representing the largest possible instant in the future(1000000000-12-31T23:59:59.999999999Z)

**MIN |** An Instant representing the smallest possible instant in the past (-1000000000-01-01T00:00Z)

![](image290.jpg)

Creating an Instant

There are numerous methods for creating an Instant. Many of these are static methods found in the Instant class. The time represented by an instant has nanosecond precision and is supported internally with two long values.

We can use the Clock’s instant method to create an Instant object:

Clock clock = Clock.systemDefaultZone();

System.out.println(clock.instant());

![](image291.jpg)

The output follows:

2014-03-10T17:48:38.307Z

We can also use the Instant class’ static now method to create an instant based on the current UTC time zone as determined by the system clock. This is illustrated below:

Instant now = Instant.now();

System.out.println(now);

![](image292.jpg)

The output of this sequence may appear as follows:

2014-03-02T16:00:14.929Z

Creating an Instant Based on the Epoch

We may need to create an Instant from the epoch to mark an event along the machine timeline. There are three methods that produce an Instant based on the time elapsed from the epoch. They differ in their arguments and the resulting accuracy of the Instant object produced.

***Table 6 – An Instant based on the Epoch***

Method | **Arguments** | Meaning of Argument

ofEpochSecond | **long epochSecond** | Number of seconds from epoch

ofEpochSecond | **long epochSecond, long nanoAdjustment** | Number of seconds from epoch with a nanosecond adjustment

ofEpochMilli | **long** **epochMilli** | Number of milliseconds from epoch

![](image293.jpg)

The following illustrates creating an instant that is 500,000,000 milliseconds after the epoch

Instant instant = Instant.ofEpochMilli(500000000);

System.out.println(instant);

![](image294.jpg)

The output follows:

1970-01-06T18:53:20Z

Creating an Instant Based on Parsing a UTC String

There is also a parse method which takes a UTC string argument representing a point in time. An exception is thrown if the string is not valid (DateTimeParseException). This convenience method is human friendly.

The following illustrates how this method is used to create an instant based on the date and time of January 1, 2010:

instant = Instant.parse("2010-01-01T00:00:00.000Z");

System.out.println(instant);

![](image295.jpg)

The output will be:

2010-01-01T00:00:00Z

Creating an Instant by Adding or Subtracting a Time from an Instant

There are a series of plus and minus type methods that execute against an Instant object. These either add or subtract an increment using the Instant and then return a new Instant object reflecting this time. The unit added or subtracted can be a second, millisecond, nanosecond or a TemporalAmount. A TemporalAmount, as its name implies, is the number of time units such as seconds.

The following code sequence illustrates adding 3600 seconds (1 hour) and then subtracting 500 milliseconds from that time. The example also shows how fluent programming is supported. The chained methods are easy to read and understand.

instant = Instant.now()

.plusSeconds(3600)

.minusMillis(500);

System.out.println(instant);

![](image296.jpg)

The output follows:

2014-03-02T17:57:57.758Z

Using the Instant Class’ get Type Methods

The Instant class has several getter methods. These methods return various types of information such as the number of seconds relative to the epoch or whether an instant occurs before or after the epoch. These methods are summarized in Table 7 - Instant Getter Methods.

The following illustrates these methods:

Instant now = Instant.now();

System.out.println(now.getEpochSecond());

System.out.println(now.getNano());

System.out.println(now.isAfter(Instant.EPOCH));

System.out.println(now.isBefore(Instant.EPOCH));

![](image297.jpg)

One possible output follows. The value returned by the getNano method returns the number of nanoseconds from the last second and not from the epoch.

1393776014

929000000

true

false

Table 7 - Instant Getter Methods

**Return Type |** Method **| Meaning**

**long |** getEpochSecond() **| The number of seconds, positive or negative, relative to the epoch**

**int |** getNano() **| The number of nanoseconds since the last second.**

**boolean |** isAfter(Instant otherInstant) **| Returns true if the Instant it is applied against comes after other Instant**

**boolean |** isBefore(Instant otherInstant) **| Returns true if the Instant it is applied against comes before other Instant**

![](image298.jpg)

Working with Time Intervals

The Duration class represents an amount of time in terms of days, hours, minutes, seconds and nanoseconds. It possesses static methods to return a Duration object specified in days and hours. However, days are always considered to be exactly 24 hours in length. This may not be adequate when dealing with durations where daylight savings time is important. In this case, the Period class is a better choice.

The Period class provides a more human oriented way of expressing a time interval. The Period class represents time in terms of years, months, and days. This class takes into account daylight savings time when performing operations.

Creating Offsets Using the of Type Methods

A series of overloaded of type methods provides a convenient way of creating durations. They use different units of time as listed in Table 8 - Duration of Methods Summary. The Duration class has one constant, ZERO. It represents a duration of zero.

***Table 8 - Duration of Methods Summary***
**Method |** Arguments **| Units**

**of |** long amount, TemporalUnit unit **| The specified unit**

**ofDays |** long days **| Days**

**ofHours |** long hours **| Hours**

**ofMillis |** long millis **| Milliseconds**

**ofMinutes |** long minutes **| Minutes**

**ofNanos  |** long nanos **| Nanoseconds**

**ofSeconds |** long seconds **| Seconds**

**ofSeconds |** long seconds, long nanoAdjustment **| Seconds adjustment with nanoseconds**

![](image299.jpg)

The following illustrates the creation of several different Duration objects using these methods:

duration = Duration.ofSeconds(120);

System.out.println(duration);

duration = Duration.ofMinutes(30);

System.out.println(duration);

duration = Duration.ofHours(5);

System.out.println(duration);

![](image300.jpg)

The output is shown below and uses the ISO-8601 formatted string representation of the duration as discussed in The ISO-8601 String Format section. The letters correspond to Period, Time, Minutes, and Hours.

PT2M

PT30M

PT5H

Creating Offsets Using the with Type Methods

A duration can also be created using either of two with type methods: withNanos and withSeconds. The following illustrates the creation of a duration of 35 seconds:

duration = Duration.ofMinutes(30).withSeconds(35);

System.out.println(duration);

![](image301.jpg)

The resulting duration is as follows:

PT35S

Creating a Duration Using the parse Method

The parse method is passed an ISO-8601 formatted string. The following illustrates the method using a duration of 3 days, 13 hours and 5 minutes:

duration = Duration.parse("P3DT13H5M");

System.out.println(duration);

System.out.println(duration.getSeconds());

![](image302.jpg)

The output shown below echoes the parse string and uses the getSeconds method to return the duration in seconds:

PT85H5M

306300

Creating a Duration by Adding or Subtracting a Unit

There are a series of methods that add or subtract a unit from a duration. Since the Duration object is immutable, the return value is a new Duration object. Table 9 - Duration minus Method Summary and Table 10 - Duration add Method Summary summarizes these methods.

***Table 9 - Duration minus Method Summary***

**Method |** Argument

**minus |** Duration duration

**minus |** long amountToSubtract, TemporalUnit unit

**minusDays |** long daysToSubtract

**minusHours |** long hoursToSubtract

**minusMillis |** long millisToSubtract

**minusMinutes |** long minutesToSubtract

**minusNanos |** long nanosToSubtract

**minusSeconds |** long secondsToSubtract

**subtractFrom |** Temporal temporal

![](image303.jpg)

***Table 10 - Duration add Method Summary***
**Method |** Argument

**plus |** Duration duration

**plus |** long amountToAdd, TemporalUnit unit

**plusDays |** long daysToAdd

**plusHours |** long hoursToAdd

**plusMillis |** long millisToAdd

**plusMinutes |** long minutesToAdd

**plusNanos |** long nanosToAdd

**plusSeconds |** long secondsToAdd

**addTo |** Temporal temporal

![](image304.jpg)

A duration is created, below, based on an initial duration of 30 minutes. Ten seconds is then added to it and then 500 milliseconds is subtracted from it.

Duration duration = Duration.ofMinutes(30).

plus(Duration.ofSeconds(10)).

minus(Duration.ofMillis(500));

System.out.println(duration);

![](image305.jpg)

The resulting duration is shown below:

PT30M9.5S

Using the Duration Class

The Duration class supports getter methods as listed in Table 11 - Duration Class get Type Methods.

***Table 11 - Duration Class get Type Methods***

Return Type | **Method** | Meaning

int | **getNano()** | The number of nanoseconds since the last second

long | **getSeconds()** | The length of the Duration in seconds

boolean | **isNegative()** | Returns true if the Duration is negative

boolean | **isZero()** | Returns true if the Duration’s length is zero

![](image306.jpg)

In addition, it supports a number of methods that manipulate a Duration instance. The following demonstrates calculating 2/3 of the time between two dates. The between method returns the initial duration. The multipliedBy and dividedBy methods compute the fractional part of this duration.

LocalTime time1 = LocalTime.of(10, 30);

LocalTime time2 = LocalTime.of(11, 45);

duration = Duration.between(time1, time2).

multipliedBy(2).

dividedBy(3);

System.out.println(duration);

![](image307.jpg)

The result is shown below:

PT50M

Using the Period Class

The Period class is concerned with representing an interval of time in terms of years, months, and days. The class takes into account daylight savings time when performing operations. It is very similar to the Duration class except in terms of the fields that it supports.

The following example shows how to create a Period object based on the number of days or months:

Period period = Period.ofDays(21);

System.out.println(period);

period = Period.ofMonths(3);

System.out.println(period);

![](image308.jpg)

The output follows:

P21D

P3M

We can also use the parse method to create a Period. In this sequence a string representing 3 years, 2 months, and 16 days is created:

period = Period.parse("P3Y2M16D");       

System.out.println(period);

System.out.println("Years: " + period.getYears() +

"  Months: " + period.getMonths() +

"  Days: " + period.getDays());

![](image309.jpg)

The output is shown below:

P3Y2M16D

Years: 3  Months: 2  Days: 16

The between method will return the Period between two dates as illustrated below:

period = Period.between(LocalDate.now(),

LocalDate.now()

.minusMonths(3)

.plusDays(60));

System.out.println(period);

![](image310.jpg)

It will produce the following output:

P-1M-2D

Using Date and Time Classes

The date and time classes do not use time zone information. Time zone classes are discussed in the Working with the Time Zone and Offset Classes section. Date and time classes are summarized in Table 12 - Date and Time Class Summary. These classes are immutable and their names give a good idea of what they represent. In addition to these classes; there are several enumerations which work nicely with these classes.

***Table 12 - Date and Time Class Summary***

**Class** | Date | **Time** | Usage

**LocalDate** | Yes | **No** | Represents a date. The primary fields are year, month, and day. Other fields can be accessed such as day-of-week and day-of-year.

**LocalTime** | No | **Yes** | Represents time and typically viewed as a combination of an hour, minute and second. A nanosecond component is also supported.

**LocalDateTime** | Yes | **Yes** | Represents a date and time. The class possesses methods to return individual parts of the date and time such as the day or hour.

**YearMonth** | Yes | **No** | Supports only a month and a year field

**MonthDay** | Yes | **No** | Supports only a month and a day

**Year** | Yes | **No** | Supports only years

![](image311.jpg)

Date and time information is often locale specific. To address this concern, the Date and Time API transparently uses the Unicode Common Locale Data Repository (CLDR) (http://cldr.unicode.org/). This repository consists of data used to format information such as dates. It provides country specific information.

In the next sections we will illustrate how the LocalDate, LocalTime, and LocalDateTime classes can be instantiated and used. Following this section we will examine the YearMonth, MonthDay, and Year classes.

Databases often have specific types for date and time entities. The following shows how the new date and time classes map:

- LocalDate is used with the SQL DATE type

- LocalTime is used with the SQL TIME type

- LocalDateTime is used with the SQL TIMESTAMP type.

Creating Date and Time Classes

There are three common ways of creating instances of these classes:

- Using the now method

- Using an of type method

- Using the from method

These methods, with the exception of the from method, are overloaded. The use of these methods is consistent with their use in other classes. The following code sequence illustrates these methods:

LocalDateTime ldt = LocalDateTime.now();

System.out.println(ldt);

ldt = LocalDateTime.of(1980, 2, 12, 17, 30);

System.out.println(ldt);

LocalDate localDate = LocalDate.now();

System.out.println(localDate);

localDate = LocalDate.now(ZoneId.of("Brazil/West"));

System.out.println(localDate);

localDate = LocalDate.of(2011, Month.MARCH, 12);

System.out.println(localDate);

localDate = LocalDate.from(ldt);

System.out.println(localDate);

LocalTime localTime = LocalTime.now();

System.out.println(localTime);

localTime = LocalTime.of(17, 30, 15);

System.out.println(localTime);

![](image312.jpg)

The output is shown below:

2014-03-10T14:35:42.638

1980-02-12T17:30

2014-03-10

2014-03-10

2011-03-12

1980-02-12

14:35:42.769

17:30:15

Date and Time get Type Methods

These classes provide several get type methods to retrieve information about the date or time. The following sequence illustrates how we can use these methods with instances of the LocalDate and LocalTime classes. Similar methods are available for the LocalDateTime class.

localDate = LocalDate.of(2011, Month.MARCH, 12);

System.out.println(localDate);

System.out.println("Year: " + localDate.getYear() +

"  Month: " + localDate.getMonth() +

"  Day: " + localDate.getDayOfMonth() +

"  Day of the week: " +

localDate.getDayOfWeek());

localTime = LocalTime.of(17, 30, 15);       

System.out.println(localTime);

System.out.println("Hour: " + localTime.getHour() +

"  Minute: " + localTime.getMinute() +

"  Second: " + localTime.getSecond() +

"  Nanosecond: " + localTime.getNano());

![](image313.jpg)

The output is shown below:

2011-03-12

Year: 2011  Month: MARCH  Day: 12  Day of the week: SATURDAY

17:30:15

Hour: 17  Minute: 30  Second: 15  Nanosecond: 0

There are several is type methods available, such as the isLeapYear and isBefore illustrated below:

localDate = LocalDate.of(2011, Month.MARCH, 12);

System.out.println(localDate.isLeapYear());

localTime = LocalTime.of(17, 30, 15); 

System.out.println(localTime.isBefore(

LocalTime.of(15, 0, 15)));

![](image314.jpg)

Both of these methods will return false.

Adjusting a Date or Time

The with method, along with the TemporalAdjusters class, provides a useful technique for finding other related dates. For example, the firstDayOfMonth method will return the first day of the month based on a given date as shown below. Also illustrated is the next method that uses a specific day of the week.

localDate = LocalDate.of(2011, Month.MARCH, 12);

LocalDate firstDayOfTheMonth =

localDate.with(

TemporalAdjusters

.firstDayOfMonth());

System.out.println(firstDayOfTheMonth);

LocalDate nextFriday =

localDate.with(

TemporalAdjusters.next(DayOfWeek.FRIDAY));

System.out.println(nextFriday);

![](image315.jpg)

The output follows:

2011-03-01

2011-03-18

The LocalTime class has with type methods that return a new time where only one unit of the time is changed. In the following sequence the hour and then the minute is changed:

localTime = LocalTime.of(17, 30, 15);

System.out.println(localTime.withHour(8));

System.out.println(localTime.withMinute(20));

![](image316.jpg)

The output is shown below:

08:30:15

17:20:15

Using the YearMonth, MonthDay, and Year Classes

These classes support limited date information as their names imply. Since they have similar methods we will focus on the MonthDay class. 

The MonthDay class represents a month and day combination such as August 4\. It is immutable and possesses a number of methods to compare or otherwise use instances of this class. It does not contain information regarding the year or time zone.

This class is useful when we only need information about a month and day of the month. There are several static methods used to create instances of MonthDay. They include overloaded versions of now, of, and parse. Several of these are illustrated below. With the exception of the first declaration using the now method, these will all create a MonthDay object that represents August 4.

MonthDay monthDay = MonthDay.now();

monthDay = MonthDay.of(8, 4);

monthDay = MonthDay.of(Month.AUGUST, 4);

monthDay = MonthDay.parse("--08-04");

![](image317.jpg)

The parse method requires a string formatted as “--MM-dd”. If not, it will throw a java.time.format.DateTimeParseException exception.

A MonthDay object can also be created using with type methods as illustrated below. This will create a new MonthDay object that is the copy of the first one but the month has been changed to April. The withMonth version has the same effect.

monthDay = MonthDay.now();

monthDay = monthDay.with(Month.APRIL);

monthDay = monthDay.withMonth(4);

![](image318.jpg)

The day can be altered using the withDayOfMonth method in a similar fashion.

We can create a LocalDate from a MonthDay instance using the atYear method as shown below:

LocalDate date = monthDay.atYear(2014);

![](image319.jpg)

Be careful when using MonthDay objects. A MonthDay of February 29 is considered to be valid. Whether it is actually valid is dependent on the year. However, a date of February 30 is invalid. A minimum check of possible date ranges is checked when specifying the month.

The isValidYear method can be used to determine if a MonthDay instance is valid for a specific year. In the next example, a MonthDay object is created for February 29\. It is then tested against the years 2012 and 2014.

monthDay = MonthDay.of(2, 29);

System.out.println(monthDay.isValidYear(2012));

System.out.println(monthDay.isValidYear(2014));

![](image320.jpg)

The results will be true for 2012 but false for 2014.

Comparing MonthDay Instances

The compareTo method returns an integer indicating the relationship between two MonthDay instances. A negative value is returned if the date the method is executing against precedes its date argument, a zero if they are equal, and a positive number if its argument follows the first date.

The following will return a -1 indicating that the first instance precedes the second instance:

MonthDay today = MonthDay.now();

MonthDay nextMonth =

today.with(today.getMonth().plus(1));

System.out.println(today.compareTo(nextMonth));

![](image321.jpg)

We can also use the isAfter and isBefore methods which compares two MonthDay instances.

System.out.println(today.isBefore(nextMonth));

System.out.println(nextMonth.isAfter(today));

![](image322.jpg)

Both statements will display true.

Using the Enumerations DayOfWeek and Month

These two enumeration classes are used to specify the days of the week and months of the year from a human perspective. They are typically used in conjunction with other classes.

Using the DayOfWeek Enumeration

This enumeration is a convenient way of representing the days of the week. For example, the expression, DayOfWeek.FRIDAY, represents Friday. The values method returns an array of these enumerations as shown below. It also possesses a getValue method that returns the numeric representation for that enumeration.

DayOfWeek days[] = DayOfWeek.values();

for (DayOfWeek day : days) {

System.out.println(day.getValue() + " - " + day);

}

![](image323.jpg)

The output of this sequence follows:

1 - MONDAY

2 - TUESDAY

3 - WEDNESDAY

4 - THURSDAY

5 - FRIDAY

6 - SATURDAY

7 – SUNDAY

We can create a DayOfWeek value using either the valueOf or of methods. The valueOf method returns an instance of the enumeration. Its string argument must be all uppercase to be recognized properly.

DayOfWeek day = DayOfWeek.valueOf("TUESDAY");

![](image324.jpg)

The of method accepts an integer and returns the corresponding enumeration as shown below:

DayOfWeek day = DayOfWeek.of(2);

System.out.println(day);

![](image325.jpg)

The following will be displayed:

TUESDAY

This enumeration can be used with other classes such as the LocalDate class. In the following example, the current day is obtained using the now method. The with method is then applied to it. The result will be a LocalDate for the Tuesday of that week.

LocalDate localDate = LocalDate.now();

System.out.println(localDate.with(DayOfWeek.TUESDAY));

![](image326.jpg)

Assuming that today is March 6, 2014, the output of this sequence will be as follows:

2014-03-06

Using the Month Enumeration

The Month enumeration supports the 12 months of the year. Like the DayOfWeek enumeration, it has a values and a getValues method that we can use to display this enumeration:

Month months[] = Month.values();

for (Month month : months) {

System.out.println(month.getValue() +

" - " + month);

}

![](image327.jpg)

The output follows:

1 - JANUARY

2 - FEBRUARY

3 - MARCH

4 - APRIL

5 - MAY

6 - JUNE

7 - JULY

8 - AUGUST

9 - SEPTEMBER

10 - OCTOBER

11 - NOVEMBER

12 – DECEMBER

A specific month can be created using the of method which takes an integer value corresponding to the month:

Month month = Month.of(3);

![](image328.jpg)

In addition, several methods exist that return that month’s number of days from the first of the year, the first month of the current quarter, and the maximum number of days in the month. These methods are demonstrated below using the previous month declaration. The argument to the firstDayOfYear method is set to true if the year is to be considered a leap year.

System.out.println(month.firstDayOfYear(false));

System.out.println(month.firstMonthOfQuarter());

System.out.println(month.maxLength());

![](image329.jpg)

The output of this sequence follows:

60

JANUARY

31

Working with the Time Zone and Offset Classes

A time zone is a region where the time is the same within that area. It can be described as using one of several formats. For example, we can specify CST (Central Standard Time) using a time zone identifier. This identifier consists of a region followed by a forward slash and then a city such as "America/Chicago".

A time zone can also be represented as an offset from Greenwich/UTC time such as -06:00 for Chicago. It will be -05:00 if daylight savings time is in effect. If we are interested in using a time zone identifier in code we use the ZoneId class. If we need to use an offset, the ZoneOffset class should be used.

Temporal based classes that include the time zone include ZonedDateTime, OffsetDateTime, and OffsetTime. Table 13 - Time Zone Classes indicates what information is handled by each class.

***Table 13 - Time Zone Classes***
**Class |** Date **| Time |** Time Zone ID **| Offset**

**ZonedDateTime |** Yes **| Yes |** Yes **| Yes**

**OffsetDateTime |** Yes **| Yes |** No **| Yes**

**OffsetTime |** No **| Yes |** No **| Yes**

![](image330.jpg)

In addition to these classes, there is also the ZoneRules class that specifies a set of rules for defining when zone-offset changes occur. This is useful when working with daylight savings times.

Time zones are also an important part of most calendar systems. To support time zones, the Date and Time API transparently uses the Time-Zone Database (TZDB) (http://www.iana.org/time-zones). This database contains information about time zones and changes to time zones since 1970\. To correctly determine the time, the current time zone in often needed.

Obtaining Available Zone IDs

The zone ids available can be obtained using the ZoneId class’ getAvailableZoneIds method which returns a Set. This can be useful if this set, or a subset, needs to be displayed to the user, possibly in the form of a drop down combo box.

The following code sequence uses the method to create a set. The contents of the set are then displayed.

Set<String> zoneIds = ZoneId.getAvailableZoneIds();

for(String zoneId : zoneIds) {

System.out.println(zoneId);

}

![](image331.jpg)

A subset of this list is shown below:

Asia/Aden

America/Cuiaba

Etc/GMT+9

Etc/GMT+8

Africa/Nairobi

America/Marigot

Asia/Aqtau

Pacific/Kwajalein

…

If we are interested in obtaining the current ZoneId, we should use the ZoneId class’ systemDefault method as shown below:

System.out.println(ZoneId.systemDefault());

![](image332.jpg)

One possible output follows:

America/Chicago

To create a ZoneID for a specific time zone, we should use the time zone identifier as the argument of the of method:

ZoneId zoneId = ZoneId.of("Europe/Vienna");

![](image333.jpg)

Working with ZoneOffsets

The ZoneOffset, OffsetDateTime and OffsetTime classes provide a means of specifying an offset from the UTC. The ZoneOffset class represents an offset specified in hours, minutes, or seconds. It does not incorporate a date or time element as do the other two classes. The following illustrates, using the ZoneOffset class, to specify a difference of one hour:

ZoneOffset zoneOffSet = ZoneOffset.ofHours(1);

System.out.println(zoneOffSet);

![](image334.jpg)

The output below shows that only the hour and minutes are used:

+01:00

The OffsetDateTime class is illustrated here using the current date and time obtained using the now method:

OffsetDateTime offsetDateTime = OffsetDateTime.now();

System.out.println(offsetDateTime);

![](image335.jpg)

As the output below indicates, the date, time, and offset are used. The last value, -5:00, represents the offset from UTC.

2014-03-10T16:02:56.751-05:00

The next sequence illustrates using the now method with zoneOffSet and ZoneId objects:

offsetDateTime = OffsetDateTime.now(zoneOffSet);

System.out.println(offsetDateTime);

offsetDateTime =

OffsetDateTime.now(ZoneId.of("+03:30"));

System.out.println(offsetDateTime);

offsetDateTime =

OffsetDateTime.now(ZoneId.of("-06:30"));

System.out.println(offsetDateTime);

![](image336.jpg)

The output shows how the time differs by time zone:

2014-03-10T22:02:56.784+01:00

2014-03-11T00:32:56.785+03:30

2014-03-10T14:32:56.785-06:30

The OffsetTime class uses only time as illustrated below. The plusHours method is one of several methods used to adjust the offset.

OffsetTime offsetTime = OffsetTime.now();

System.out.println(offsetTime);

offsetTime = offsetTime.plusHours(2);

System.out.println(offsetTime);

![](image337.jpg)

The output follows:

16:02:56.785-05:00

18:02:56.785-05:00

Using the fluent style we can create a date in the future as follows. This illustrates several other at type methods that are available.

OffsetDateTime futureDate = Year.of(2016)

.atMonth(Month.MARCH).atDay(12)

.atTime(12, 30)

.atOffset(ZoneOffset.of("-10:00"));

System.out.println(futureDate);

![](image338.jpg)

The date is shown below:

2016-03-12T12:30-10:00

Working with Zone Rules

The rules used when working with time zones can be complex. We often use ZoneRules with daylight savings time. The following uses two different time zones with a displaySettings method:

zoneId = ZoneId.of("America/Phoenix");

displaySettings(zoneId);

zoneId = ZoneId.of("America/Chicago");

displaySettings(zoneId);

![](image339.jpg)

The displaySettings method is listed below. This method uses the isDaylightSavings and getDaylightSavings methods on the time zone passed to it based on the current date and a date 8 months later. These methods indicate whether daylight savings time is in effect and the length of the daylight savings respectively.

public static void displaySettings(ZoneId zoneId) {

ZoneRules rules = zoneId.getRules();

System.out.println("Today");

System.out.println(zoneId + ": " +

rules.isDaylightSavings(Instant.now()));

System.out.println(zoneId + ": " +

rules.getDaylightSavings(Instant.now()));

System.out.println("In Eight Months");

System.out.println(zoneId + ": " +

rules.isDaylightSavings(

Instant.now().plus(8 * 30, ChronoUnit.DAYS)));

System.out.println(zoneId + ": " +

rules.getDaylightSavings(

Instant.now().plus(8 * 30, ChronoUnit.DAYS)));

}

![](image340.jpg)

The output follows. Phoenix does not use daylight savings time so the isDaylightSavings returns false in both instances and the length of the time savings is 0\. Chicago does use daylight savings time. At the time the code was executed it was in effect with a length of 1 hour.

Today

America/Phoenix: false

America/Phoenix: PT0S

In Eight Months

America/Phoenix: false

America/Phoenix: PT0S

Today

America/Chicago: true

America/Chicago: PT1H

In Eight Months

America/Chicago: false

America/Chicago: PT0S

Formatting, Queries, and Value-Based Classes

This section addresses a few topics to round out our discussion of the API. When a date or time needs to be displayed there are many formats to choose from. These options are presented in the first section.

Temporal queries provide an interesting way of obtaining information about a date or time. This is addressed in the second section. While not unique to the date and time API, understanding value-based classes is important. The last section examines these types of classes.

Formatting Dates and Times

Two classes support the formatting of dates and time:

- DateTimeFormatter - Is used frequently when formatting dates and times. It is used with either predefined formats or custom formats.

- DateTimeFormatterBuilder - Uses a builder pattern to support the creation of custom patterns

The DateTimeFormatter class is illustrated below where several of the predefined formats are used:

LocalDateTime today = LocalDateTime.now();     

System.out.println(today.format(

DateTimeFormatter.BASIC_ISO_DATE));

System.out.println(today.format(

DateTimeFormatter.ISO_LOCAL_DATE_TIME));

System.out.println(today.format(

DateTimeFormatter.ISO_LOCAL_DATE));

System.out.println(today.format(

DateTimeFormatter.ISO_WEEK_DATE));

System.out.println(today.format(DateTimeFormatter

.ofLocalizedDate(FormatStyle.SHORT)));

![](image341.jpg)

The varied types of output are shown below:

20140310

2014-03-10T16:32:03.561

2014-03-10

2014-W11-1

3/10/14

The ofPattern method allows the developer to customize the appearance of the output as illustrated below. There are a large variety of field specifiers available and can be found in the DateTimeFormatter documentation.

DateTimeFormatter dateFormat =

DateTimeFormatter.ofPattern(

"MMM d, yyyy  (hh:mm:ss a)");

System.out.println(today.format(dateFormat));

![](image342.jpg)

The date is formatted as shown below:

Mar 10, 2014  (04:32:03 PM)

All date formatters are based on the DateTimeFormatterBuilder class. The class uses a series of append methods to create a pattern. In the following code sequence, a DateTimeFormatterBuilder object is created using the ISO_LOCAL_DATE format plus two literals for the current date:

ZonedDateTime zdt = ZonedDateTime.now();

DateTimeFormatterBuilder formatterBuilder =

new DateTimeFormatterBuilder();

formatterBuilder

.appendLiteral(

"The current date for Time Zone \"")

.appendZoneOrOffsetId()

.appendLiteral("\" is ")

.append(DateTimeFormatter.ISO_LOCAL_DATE);

DateTimeFormatter formatter =

formatterBuilder.toFormatter();

System.out.println(formatter.format(zdt));

![](image343.jpg)

The resulting output appears below:

The current date for Time Zone "America/Chicago" is 2014-03-10

Using Temporal Queries

A TemporalQuery is used in conjunction with a temporal-based object to obtain information about that object. Predefined queries are available and custom queries can be created.

The following reworks the example found in the A Simple Example section. That example demonstrated how to determine whether an employee was currently working even though the employee may be in a different time zone.

An Employee class is defined that possesses various date and time classes to represent time related aspects of an employee. The immediate relevant parts of the class are listed below. The class implements the TemporalQuery interface which requires that we provide a queryFrom method. We will implement this method later in this discussion.

public class Employee implements TemporalQuery<Boolean> {

private String name;

private LocalDate birthdate;

private LocalDate hireDate;

private LocalTime startWorkDay;

private Duration dailyTime;

private ZoneId timeZone;

public Employee(String name, LocalDate birthdate,

LocalDate hireDate, LocalTime startWorkDay,

Duration dailyTime, ZoneId timeZone) {

this.name = name;

this.birthdate = birthdate;

this.hireDate = hireDate;

this.startWorkDay = startWorkDay;

this.dailyTime = dailyTime;

this.timeZone = timeZone;

}

...

}

![](image344.jpg)

An employee is created as shown below. The fourth argument of the constructor specifies that she starts work at 8 in the morning. The fifth argument indicates that her shift is 6 hours in length. The last argument shows that she is located in La Paz.

Employee employee1 = new Employee("Mary",

LocalDate.of(1985, Month.MAY, 5),

LocalDate.of(2010, Month.JUNE, 13),

LocalTime.of(8, 0),

Duration.ofHours(6),

ZoneId.of("America/La_Paz"));

![](image345.jpg)

The present time is calculated using the ZonedDateTime class’ now method. This time will represent the current time in the current time zone. The Employee class’ isWorkingNow method will return true if the employee is currently working or false otherwise.

ZonedDateTime present = ZonedDateTime.now();

System.out.println(employee1.isWorkingNow(present));

![](image346.jpg)

The isWorkingNow method’s implementation follows. A LocalDate is created first and is used to create a start and end time based on the worker’s time zone. A ZonedDateTime presenting the present is created using the TemporalAccessor passed to the method. The method then uses these values with the compareTo method to determine if the worker is present.

public Boolean isWorkingNow(TemporalAccessor temporal) {

LocalDate employeeDate =

LocalDate.of(LocalDate.now().getDayOfYear(),

LocalDate.now().getMonth(),

LocalDate.now().getDayOfMonth());

ZonedDateTime startTime = ZonedDateTime.of(

employeeDate,

this.startWorkDay,

this.getTimeZone());

ZonedDateTime present = (ZonedDateTime) temporal;

ZonedDateTime endTime = startTime.plusHours(

this.getDailyTime().toHours());

return (startTime.compareTo(present) <= 0) &&

 (endTime.compareTo(present) >= 0);

}

![](image347.jpg)

Using a specific method such as the isWorkingNow method allows other methods to be added to the class to support similar query operations. Alternatively, we could have used the queryFrom method from a standard query as follows:

System.out.println(employee1.queryFrom(present));

![](image348.jpg)

The queryFrom method duplicates the isWorkingNow method:

@Override

public Boolean queryFrom(TemporalAccessor temporal) {

LocalDate employeeDate =

LocalDate.of(

LocalDate.now().getDayOfYear(),

LocalDate.now().getMonth(),

LocalDate.now().getDayOfMonth());

ZonedDateTime start = ZonedDateTime.of(employeeDate,

this.startWorkDay, this.getTimeZone());

ZonedDateTime present = (ZonedDateTime) temporal;

ZonedDateTime endTime =

start.plusHours(this.getDailyTime().toHours());

return (start.compareTo(present) <= 0) &&

(endTime.compareTo(present) >= 0);

}

![](image349.jpg)

We could have also called the isWorkingNow method from the queryFrom method to achieve the same results.

Understanding Value-Based Classes

Many classes in Java 8 are value-based. The LocalDateTime and MonthDay are examples of such classes. These types of classes possess a number of characteristics including:

- They are final

- They are immutable

- They have no public constructors

- Factory methods are needed to create instances of these classes

- Their equals, hashCode and toString methods do not use information from other sources when executed

- We should use the equals method instead of the == operator when performing comparisons

- Interchanging two equivalent objects should not result in any difference in behavior

Identity-sensitive operations on value-based objects should be avoided. Any such operations may result in unpredictable behavior. This is illustrated below where the equality operator and equals methods are used to compare two identical objects:

MonthDay date1 = MonthDay.of(2, 2);

MonthDay date2 = MonthDay.of(2, 2);

System.out.println(date1 == date2);

System.out.println(date1.equals(date2));

![](image350.jpg)

The equality operator will return false while the equals method returns true;

Conclusion

The new Java 8 date and time API is large and complex. It uses a variety of classes to support local dates and times along with time zone based needs. The API uses a consistent and easy to understand method naming scheme. This supports a fluent style of programming which improves productivity and the code’s readability.

The API supports a machine timeline through the Clock class. Human timelines are supported through classes like LocalDate and ZonedTimeDate. In addition, time intervals are created using the Duration class for hours, minutes, and seconds and the Period class for units such as months and days.

There are several classes that include time zone related information. The developer can work with zone offsets and zone rules as needed. Dates and time can be created through several methods including parsing strings. Dates and times can be displayed using a variety of formatting techniques.

* * * * *

Chapter 5 – Odds and Ends

-Introduction

-Using the Nashorn JavaScript Engine

--Accessing the Nashorn Engine

--Executing JavaScript Code

--Executing Java Code from JavaScript

--Implementing a Java Interface

-File IO Enhancements

--Using the FileFilter Interface

--Using the PathMatcher Interface

--Using the Files Class’ list Method

--Using the Files Class’ walk Method

--Using the Path Class’ lines Method

-Concurrency Enhancements

--Using the Arrays Class’ parallelSort Method

--Using the Arrays Class’ parallelSetAll Method

--Using the Arrays Class’ parallelPrefix Method

-Collections Enhancements

--Using the forEachRemaining Method

--Using the replace Type Methods

--Using the compute Type Methods

-Project Jigsaw and Compact Profiles

--The Compact Profiles

--Using Compact Profiles

-Other Enhancements

--Javadoc Enhancements

--Security Enhancements

--VM Related Enhancements

--Core Java Enhancements

-Conclusion

Introduction

This chapter addresses additional features of Java 8 that do not necessarily warrant a separate chapter. For example, the Nashorn JavaScript engine has been incorporated and allows for the execution of JavaScript code from a Java application. Several file IO classes and methods have been improved to support lambda expressions. In turn, there have been several methods added to the Collections framework which deserve further discussion. Concurrency enhancements and other features are also discussed here.

Using the Nashorn JavaScript Engine

A JavaScript engine is software that interprets JavaScript code. The Nashorn JavaScript engine is written in Java and allows JavaScript code to be embedded into Java applications. It is the successor to the Rhino JavaScript engine and has better memory utilization and performance.

Many operations are supported by the engine including:

- Evaluating isolated scripts or complete JavaScript files

- Invoking script functions

- Executing Java code from JavaScript

- Implementing a Java interface with script

The Nashorn engine is a complex API. Here we will only be providing an overview of its capabilities. More detail about the engine can be found at [http://download.java.net/jdk8/docs/technotes/guides/scripting/nashorn/toc.html](http://download.java.net/jdk8/docs/technotes/guides/scripting/nashorn/toc.html).

Accessing the Nashorn Engine

In order to use the engine, an instance of the JavaScript engine needs to be created. This is accomplished using two classes: ScriptEngineManager and ScriptEngine. The ScriptEngineManager class is used to manage the script engines available to the Java JVM. An instance of the ScriptEngine class represents the JavaScript engine.

In the following sequence an instance of the JavaScript engine is created. The getEngineByName method returns an instance of the engine and the eval method will execute an arbitrary JavaScript code. In this example, it determines the length of a string. The eval method is enclosed in a try block because a ScriptException exception must be handled.

ScriptEngineManager manager = new ScriptEngineManager();

ScriptEngine engine = manager.getEngineByName("nashorn");

try {

Object result = engine.eval(

"'Nashorn JavaScript Engine'.length");

System.out.println(result);

} catch (ScriptException ex) {…);

![](image351.jpg)

The output of this example will be 25.

Executing JavaScript Code

There are several ways of executing JavaScript code in addition to using the eval method with a simple string argument. The following defines a JavaScript function, sumOfSquares, that returns the sum of the squares of two numbers. We then execute the function using the eval method.

engine.eval("function sumOfSquares(a, b) {

return a*a + b*b;}");

System.out.println(engine.eval(

"sumOfSquares(1, 2);"));

![](image352.jpg)

The output will be 5.0.

Another approach uses the javax.script.Invocable interface. The engine variable can be cast to this interface which allows us to use the interface's invokeFunction method to execute script code as shown below. It produces the same output as the previous example.

Invocable invocable = (Invocable) engine;

System.out.println(

invocable.invokeFunction(

"sumOfSquares", 1, 2));

![](image353.jpg)

We can also evaluate script code found in a file. The following is the contents of a file named maximum.js. The function returns the largest number passed to it.

function max() {

var largest = arguments[0];

for(var index = 1; index < arguments.length; index++)

if (arguments[index] > largest) {

largest = arguments[index];

}

return largest;

}

![](image354.jpg)

A FileReader object is created using this file and then the invokeFunction is executed using the max function and a list of parameters passed to the function:

engine.eval(new FileReader("maximum.js"));

System.out.println(invocable.invokeFunction(

"max", 23, 21, 43, -36, 2, 51));

![](image355.jpg)

The output will be 51.

Executing Java Code from JavaScript

Embedding Java code within JavaScript is supported through the use of classes and interfaces. All references to Java types must normally be fully qualified. In the following JavaScript sequence, an instance of the LocalDateTime class is used to get and display the current date and time.

var today = java.time.LocalDateTime.now();

print(today);

![](image356.jpg)

We can demonstrate this by placing this code sequence into a file called UsingJava.js and then invoking it from Java using the following statement:

engine.eval(new FileReader("UsingJava.js"));

![](image357.jpg)

One possible output follows:

2014-03-15T14:14:38.410

Nashorn provides an object called Java that possesses to and from methods. This object is used to support conversions between Java and JavaScript. Since the object returned by the toArray method is a Java array and not a JavaScript array, it *cannot* be displayed properly until it is converted to the correct JavaScript object. This is done using the from method.

In the following sequence a list is created. A Stream object is created from the list and the filter, sort, and toArray methods are applied to it in a fluent fashion. The filternumber function is used as an argument to the filter method to eliminate numbers greater than 10 from being processed further. The Java array is converted to a JavaScript array using the from method.

function filterNumber (n) { return n>10};

var list = java.util.Arrays.asList(2, 43, 23, 87, 29);

var result =

list.stream().filter(filterNumber).sorted().toArray();

var array = Java.from(result);

print(array);

![](image358.jpg)

The output of the code sequence follows:

23,29,43,87

Nashorn does not automatically import the Java packages because there would be a conflict between the Object and String classes found in both languages. However, the javaImporter can be used in conjunction with the with statement to simplify class references. In the following example, the functionality of the previous example is duplicated by creating a variable called ImportedClasses using JavaImporter. It is then used in the with statement. This avoids having to provide explicit package names for all of the classes.

var ImportedClasses = new JavaImporter(

java.time,

java.util);

with (ImportedClasses) {

var today = LocalDateTime.now();

print(today);

var list = Arrays.asList(2, 43, 23, 87, 29);

}

var result =

list.stream().filter(filterNumber).sorted().toArray();

var array = Java.from(result);

print(array);

![](image359.jpg)

The output will be identical to the previous implementations.

Implementing a Java Interface

A Java interface can be implemented in JavaScript. We can also extend Java classes if necessary. Here we will demonstrate the basic approach using the List interface.

In the example that follows, a JavaScript variable is declared and assigned an implementation of the List interface. The implementation starts by using the new keyword with the fully-qualified interface name. This is followed by the body of the implementation contained in a block statement. In this implementation, two variables and two methods are supported.

var list = new java.util.List() {

list: "",

count: 0,

add: function(item) {

this.list += item + " ";

this.count++;

},

size: function() {

print(this.count);

}

};

![](image360.jpg)

This implementation is tested with the following code sequence:

list.size();

list.add("cat");

list.size();

![](image361.jpg)

The output follows:

0

1

No methods, other than those defined by the interface, can be added to the implementation.

File IO Enhancements

The introduction of lambda expressions and specific enhancements to the IO capabilities in Java 8 makes working with files a bit easier. We will investigate the use of lambda expressions with the FileFilter interface first and then follow up with the use of several other methods. Lambda expressions are discussed in Chapter 2.

To illustrate many of these techniques, we will use two helper methods: getFileName and getExtension. The getFileName method is passed a Path object and returns the name of the file. The getExtension returns the extension of the file name passed to it as a string.

public static String getFileName(Path path) {

return path.getName(

path.getNameCount() - 1).toString();

}

public static String getExtension(String fileName) {

String extension = null;

int index = fileName.lastIndexOf('.');

if (index > 0 && index < fileName.length() - 1) {

extension = fileName.substring(index + 1);

}

return extension;

}

![](image362.jpg)

Using the FileFilter Interface

The FileFilter interface has been part of Java since 1.2 and is used to determine which files in a directory should be returned. It has a single abstract method, accept, that is passed a File and returns a boolean value indicating whether the file should be returned. This meets the definition of a functional interface and can be used with lambda expressions. This is an example of an interface that has always been a functional interface but has not been explicitly called one.

The following illustrates how we can use a lambda expression with the interface. First we define a fileFilter variable using a lambda expression which tests to see if the file ends with a “java” extension and has a size greater than 1024 bytes. A file is then created and is tested using the fileFilter variable.

FileFilter fileFilter = file -> {

String fileName = file.getName();

String extension = getExtension(fileName);

if ("java".equalsIgnoreCase(extension)

&& file.length() > 1024) {

return true;

} else {

return false;

}

};

File file = new File("C:/SomeDirectory/SomeFile.java");

System.out.println(

file + " is a " +

getExtension(file.getName()) +

" file whose size is at least 1024 bytes: " +

fileFilter.accept(file));

![](image363.jpg)

One possible output follows:

C:\SomeDirectory\SomeFile.java is a java file whose size is at least 1024 bytes: false

Using the PathMatcher Interface

The PathMatcher interface is another interface that lends itself to lambda expressions. The interfaces have a single abstract method, matches, which takes a Path object and returns a boolean value. In the following example, the Path object is tested to see if its name ends with “java”. If so, it returns true.

PathMatcher matcher = p -> {

return p.toString().endsWith(".java");

};

Path filename = FileSystems.getDefault().getPath(

"C:/SomeDirectory/SomeFile.java");

System.out.println("We have a match: " +

matcher.matches(filename));

}

![](image364.jpg)

The result of executing this sequence follows:

We have a match: true

Using the Files Class’ list Method

The list method returns a Stream object which we can use to filter or perform similar operations. The method encapsulates a DirectoryStream<Path> stream. We will demonstrate the method with a series of examples all of which may throw an IOException exception. The first example displays directories and files using the current directory.

Files.list(new File(".").toPath())

.forEach(System.out::println);

![](image365.jpg)

The output is shown below but your actual results will depend on your current directory:

.\build

.\build.xml

.\manifest.mf

.\nbproject

.\src

.\test

The next example uses the filter method to list only XML files:

Files.list(new File(".").toPath())

.filter(p -> "xml".equalsIgnoreCase(

getExtension(getFileName(p))))

.forEach(p -> System.out.println(getFileName(p)));

![](image366.jpg)

One possible output is:

build.xml

We can use the newDirectoryStream method, as shown, below to achieve the same results:

Path files = new File(".").toPath();

try (DirectoryStream<Path> directories =

Files.newDirectoryStream(files);) {

directories.forEach(System.out::println);

}

![](image367.jpg)

Using the Files Class’ walk Method

The walk method allows us to process the files in a directory and its sub-directories. In this example we list only the XML files found in the current directory or its sub-directories:

Files.walk(new File(".").toPath())

.filter(p -> "xml".equalsIgnoreCase(

getExtension(getFileName(p))))

.forEach(System.out::println);

![](image368.jpg)

One possible output is as follows:

.\build.xml

.\nbproject\build-impl.xml

.\nbproject\private\private.xml

.\nbproject\project.xml

Using the Path Class’ lines Method

The Path class’ static lines method will return a stream of strings based on the contents of a file. Each line of the file is returned as a single string and is added to the stream. Let’s start with a file called data.txt containing the following data:

The old stream flowed

from the mountain maintaining

its ever meandering course

The following code sequence illustrates using the lines method with this file. A Path object is created that represents the file. The line method uses this path and returns a stream of input lines. The lines are then displayed.

try {

Path path = 

FileSystems.getDefault().getPath("data.txt");

Stream<String> input = Files.lines(path);

input.forEach(System.out::println);

} catch (IOException ex) {

ex.printStackTrace();

}

![](image369.jpg)

The output will be as follows:

The old stream flowed

from the mountain maintaining

its ever meandering course

Concurrency Enhancements

Several concurrency enhancements were introduced in Java 8\. The most significant one is supported using parallel streams as discussed in Chapter 3\. In addition to streams, other enhancements have been made to the java.util.Arrays class. The new methods support parallel sorting and other operations against each element of an array in a concurrent manner.

Using the Arrays Class’ parallelSort Method

The overloaded parallelSort method will sort the elements of an array concurrently. Methods exist for all of the primitive data types and for generic objects using a Comparator interface.

The methods may not actually perform the sort operation concurrently if the array does not meet a certain size threshold. In that case it will revert back to a sequential sort. Sometimes a sequential sort will execute faster when the overhead of the parallel sort outweighs the speedup achieved using multiple processors.

The parallel sort will divide the array into sub-arrays and then sort the sub-array on a dedicated processor. The sorted sub-arrays will then be recombined. The sub-division may occur multiple times depending on the size of the array.

In the following example a large array of integers is initialized with random numbers and then the paralleSort method is used to sort it. Each number assigned to the array is between 0 (inclusive) and 1000 (exclusive).

int[] largeArray = new int[10000];

Random random = new Random();

for (int i = 0; i < 10000; i++) {

largeArray[i] = random.nextInt(1000);

}

Arrays.parallelSort(largeArray);

for (int i = 0; i < 10; i++) {

System.out.println(largeArray[i]);

}

![](image370.jpg)

Assuming at least 10 zeroes were generated, the output of the code sequence should be the first 10 zeros.

Using the Arrays Class’ parallelSetAll Method

There are several static parallelSetAll methods that apply an operation against each element of the array. **Table 1 - parallelSetAll Methods** lists these methods.

***Table 1 - parallelSetAll Methods***

parallelSetAll Methods

void parallelSetAll(double[] array IntToDoubleFunction generator)

void parallelSetAll(int[] array IntUnaryOperator generator)

void parallelSetAll(long[] array IntToLongFunction generator)

<T> void parallelSetAll(T[] array IntFunction<? extends T> generator)

![](image371.jpg)

In the following example every element of the array is set to 1\. The first argument is the array. The second argument is a lambda expression that implements the IntUnaryOperator interface. The value returned is assigned to that element of the array.

int[] numbers = new int[25000];

Arrays.parallelSetAll(numbers, p -> 1);

![](image372.jpg)

In this example, each element is set to the double of its index:

Arrays.parallelSetAll(numbers, p -> 2 * p);

![](image373.jpg)

Using the Arrays Class’ parallelPrefix Method

The static overloaded parallelPrefix method processes each element by applying a binary operator to the element performing a cumulative operation. The methods are listed in Table 2 - parallelPrefix Methods.

***Table 2 - parallelPrefix Methods***

parallelPrefix Methods

void parallelPrefix(double[] array DoubleBinaryOperator op)

void parallelPrefix(double[] array int fromIndex int toIndex DoubleBinaryOperator op)

void parallelPrefix(int[] array IntBinaryOperator op)

void parallelPrefix(int[] array int fromIndex int toIndex IntBinaryOperator op)

void parallelPrefix(long[] array int fromIndex int toIndex LongBinaryOperator op)

void parallelPrefix(long[] array LongBinaryOperator op)

<T> void parallelPrefix(T[] array BinaryOperator<T> op)

<T> void parallelPrefix(T[] array int fromIndex int toIndex BinaryOperator<T> op)

![](image374.jpg)

The method uses two arguments: the array and a binary operator. In this case, the binary operator uses two values which serve as indexes into the array. The first index applies to one element and the second index is applied to the element following the first one. The elements at these indexes are applied as specified by the binary operation to the array element specified by the second index.

In the following example, each element of the numbers array is assigned a 2. The binary operator will add adjacent elements together.

int[] numbers = new int[25];

Arrays.parallelSetAll(numbers, p -> 2);

Arrays.parallelPrefix(numbers, (n, m) -> n + m);

for (int i = 0; i < 25; i++) {

System.out.println(numbers[i]);

}

![](image375.jpg)

This will output the sequence 2 through 50 in steps of 2\. Each element is the sum of the previous element and the current element. The following invocation will compute the powers of 2:

Arrays.parallelPrefix(numbers, (n, m) -> n * m);

![](image376.jpg)

Collections Enhancements

The Collections framework has added a number of new methods. A partial list of these additions is listed in**Table 3 - Collections Framework Addition**. A more complete list of changes and deletions of the java.util package can be found at [http://cr.openjdk.java.net/~mr/se/8/java-se-8-pr-spec/apidiffs/java/util/package-summary-stat.html](http://cr.openjdk.java.net/~mr/se/8/java-se-8-pr-spec/apidiffs/java/util/package-summary-stat.html). Some of these, such as the stream and forEach methods, have been discussed in previous chapters. In this section we will explore a few of the other methods.

In Java 7 an alternative String hash function was added. Java 8 has removed this along with the jdk.map.althashing.threshold system property. A balanced tree is used instead of a linked list. Each node of the tree will contain bins to hold collisions. This change applies only to HashMap, LinkedHashMap, and ConcurrentHashMap.

***Table 3 - Collections Framework Addition***

**Interface |** Method

**Iterable |** forEach(Consumer)

**Iterable |** forEachRemaining(Consumer)

**Iterator |** forEachRemaining(Consumer)

**Collection |** removeIf(Predicate)

**Collection |** spliterator()

**Collection |** stream()

**Collection |** parallelStream()

**List |** sort(Comparator)

**List |** replaceAll(UnaryOperator)

**Map |** forEach(BiConsumer)

**Map |** replaceAll(BiFunction)

**Map |** putIfAbsent(K, V)

**Map |** remove(Object, Object)

**Map |** replace(K, V, V)

**Map |** replace(K, V)

**Map |** computeIfAbsent(K, Function)

**Map |** computeIfPresent(K, BiFunction)

**Map |** compute(K, BiFunction)

**Map |** merge(K, V, BiFunction)

**Map |** getOrDefault(Object, V)

![](image377.jpg)

Using the forEachRemaining Method

The forEachRemaining method has been added to the Iterator and Iterable interfaces. As its name implies, it will act on the remaining elements of the iteration using a Consumer object. The traditional approach to iterating through a list using the Iterator interface is shown below. A list is created and the hasNext and next methods are used to print the elements of the list.

List<Integer> list = Arrays.asList(4, 54, 72, 68, 3);

Iterator<Integer> iterator = list.iterator();

while (iterator.hasNext()) {

System.out.print(iterator.next() + " ");

};

System.out.println();

![](image378.jpg)

The output follows:

4 54 72 68 3

To demonstrate, a new Iterator instance is created in the following sequence. The first two integers are skipped over using the next method. The forEachRemaining method is then used to print the remaining integers in the list.

iterator = list.iterator();

iterator.next();

iterator.next();

iterator.forEachRemaining(n -> System.out.print(n + " "));

System.out.println();

![](image379.jpg)

The output that follows displays only the last three elements:

72 68 3

Using the replace Type Methods

Two replace type methods have been added. The first is a replaceAll method and the second is an overloaded replace method. The replace methods are found in the Map interface and will replace specific elements in a map.

The replaceAll method has been added to the List and Map interfaces. The List interface uses a UnaryOperator to change each element of a list while the Map interface uses a BiFunction.

In the following example a lambda expression is used with the replaceAll method to double each number in the list. The forEach method is used to display the new values.

List<Integer> list = Arrays.asList(4, 54, 72, 68, 3);

list.replaceAll(n -> 2*n);

list.forEach(n -> System.out.print(n + " "));

![](image380.jpg)

The new elements are shown below:

8 108 144 136 6

There are two overloaded replace methods. The first overloaded replace method is passed a key and a value:

replace(K key, V value)

![](image381.jpg)

The mapped element will only be replaced if it already exists. The second form is passed a key along with an old value and a new value:

boolean replace(K key, V oldValue, V newValue)

![](image382.jpg)

This will only replace the mapped element if it already exists and is mapped to the old value. The method will return true if the value is replaced. The following illustrates how the first version works. A HashMap is created and three entries are added. The first one misspells the word: *transportation*. The replace method is then used to correct the spelling and the map is displayed.

HashMap<String, String> dictionary = new HashMap();

dictionary.put("ship", "A form of transporation");

dictionary.put("interesting", "Something of interest");

dictionary.put("disappear", "Cannot be found");

dictionary.replace("ship", "A form of transportation");

dictionary.keySet()

.forEach(k -> System.out.println(

k + " - " + dictionary.get(k)));

![](image383.jpg)

The output follows:

interesting - Something of interest

ship - A form of transportation

disappear - Cannot be found

Using the compute Type Methods

There are two compute type methods of the Map interface: computeIfPresent and computeIfAbsent. They both use two arguments: a key as an argument and a function which acts on the element specified by the key. The computeIfPresent method takes a BiFunction, and the computeIfAbsent method takes a Function. Both methods will replace the value specified by the key, assuming it is present or absent, depending on the method. The computeIfPresent method requires the value to be non-null.

The following sequence illustrates the computeIfPresent method using the dictionary HashMap defined in the Using the replace Type Methods section. It uses the “ship” key’s value for the element and replaces the original value with the original value appended with the number of words in the value.

dictionary.computeIfPresent("ship", (k, e) -> {

return e + " - " + e.split(" ").length;

});

dictionary.keySet().forEach(k -> System.out.println(

k + " - " + dictionary.get(k)));

System.out.println();

![](image384.jpg)

The output follows:

interesting - Something of interest

ship - A form of transportation - 4

disappear - Cannot be found

Project Jigsaw and Compact Profiles

Project Jigsaw ([http://openjdk.java.net/projects/jigsaw/](http://openjdk.java.net/projects/jigsaw/)) is slated for Java 9 and will provide a framework for modular Java application construction. In Java 8, an effort was made to prepare for the transition to modules. This effort includes:

- Addressing class-loading assumptions that impede modularization

- Using java.util.ServiceLoader instead of specific provider's implementations

- Deprecating certain change listeners and APIs that impede modularization

- Adding a class analyzer tool to detail application dependencies (jdeps)

- Removing references to files in $JAVA_HOME to facilitate future changes in location

Java 8 introduces the concept of a Compact Profile. The intent is to use only parts of the Java platform so as to allow Java to be utilized on platforms with minimal resources. For example, some platforms do not require GUI APIs and eliminating them will save space.

The Compact Profiles

There are three compact profiles: compact1, compact2, and compact3. Each of these compacts consists of a set of classes. Compact1 is the smallest. Compact2 consists of all of the packages of compact1 plus additional packages. Compact3 consists of all of the classes of compact1 and compact2 plus an additional set of packages. The packages included in each compact are listed in **Table 4 - Compact Profile Listing**. The entire JDK is not considered to be a compact.

Javadoc includes the names of the compact a class belongs to, if any. For example, The Clock class is found in all of the compacts. This is reflected in the documentation found at [http://download.java.net/jdk8/docs/api/](http://download.java.net/jdk8/docs/api/). The first part of the documentation is  shown below:

compact1, compact2, compact3

java.time

Class Clock

java.lang.Object

java.time.Clock

…

***Table 4 - Compact Profile Listing***

**compact1 |** compact2 **| compact3**

**java.io |** java.rmi **| java.lang.instrument**

**java.lang |** java.rmi.activation **| java.lang.management**

**java.lang.annotation |** java.rmi.dgc **| java.security.acl**

**java.lang.invoke |** java.rmi.registry **| java.util.prefs**

**java.lang.ref |** java.rmi.server **| javax.annotation.processing**

**java.lang.reflect |** java.sql **| javax.lang.model**

**java.math |** javax.rmi.ssl **| javax.lang.model.element**

**java.net |** javax.sql **| javax.lang.model.type**

**java.nio |** javax.transaction **| javax.lang.model.util**

**java.nio.channels |** javax.transaction.xa **| javax.management**

**java.nio.channels.spi |** javax.xml **| javax.management.loading**

**java.nio.charset |** javax.xml.datatype **| javax.management.modelmbean**

**java.nio.charset.spi |** javax.xml.namespace **| javax.management.monitor**

**java.nio.file |** javax.xml.parsers **| javax.management.openmbean**

**java.nio.file.attribute |** javax.xml.stream **| javax.management.relation**

**java.nio.file.spi |** javax.xml.stream.events **| javax.management.remote**

**java.security |** javax.xml.stream.util **| javax.management.remote.rmi**

**java.security.cert |** javax.xml.transform **| javax.management.timer**

**java.security.interfaces |** javax.xml.transform.dom **| javax.naming**

**java.security.spec |** javax.xml.transform.sax **| javax.naming.directory**

**java.text |** javax.xml.transform.stax **| javax.naming.event**

**java.text.spi |** javax.xml.transform.stream **| javax.naming.ldap**

**java.time |** javax.xml.validation **| javax.naming.spi**

**java.time.chrono |** javax.xml.xpath **| javax.security.auth.kerberos**

**java.time.format |** org.w3c.dom **| javax.security.sasl**

**java.time.temporal |** org.w3c.dom.bootstrap **| javax.sql.rowset**

**java.time.zone |** org.w3c.dom.events **| javax.sql.rowset.serial**

**java.util |** org.w3c.dom.ls **| javax.sql.rowset.spi**

**java.util.concurrent |** org.xml.sax **| javax.tools**

**java.util.concurrent.atomic |** org.xml.sax.ext **| javax.xml.crypto**

**java.util.concurrent.locks |** org.xml.sax.helpers **| javax.xml.crypto.dom**

**java.util.function |   | javax.xml.crypto.dsig**

**java.util.jar |   | javax.xml.crypto.dsig.dom**

**java.util.logging |   | javax.xml.crypto.dsig.keyinfo**

**java.util.regex |   | javax.xml.crypto.dsig.spec**

**java.util.spi |   | org.ietf.jgss**

**java.util.stream |   | **

**java.util.zip  |  |**

**javax.crypto |  |**

**javax.crypto.interfaces |  |**

**javax.crypto.spec |  |**

**javax.net |  |**

**javax.net.ssl |  |**

**javax.script |  |**

**javax.security.auth |  |**

**javax.security.auth.callback |  |**

**javax.security.auth.login |  |**

**javax.security.auth.spi |  |**

**javax.security.auth.x500 |  |**

**javax.security.cert |  |**

Using Compact Profiles

You can use the javac compiler command with the -profile command line option to determine if an application uses an element not present in a profile. This command is documented at [http://download.java.net/jdk8/docs/technotes/tools/windows/javac.html](http://download.java.net/jdk8/docs/technotes/tools/windows/javac.html).  For example, the Java program that follows includes an import statement and a declaration for a ResultSet variable:

import java.sql.ResultSet;

public class CompactProfiles {

public static void main(String[] args) {

ResultSet rs;

}

}

![](image385.jpg)

If we compile the program using the following command, we will get errors:

javac -profile compact1 CompactProfiles.java

Since the java.sql package is not part of compact1, we get two errors as shown below:

CompactProfiles.java:3: error: ResultSet is not available in profile 'compact1'

import java.sql.ResultSet;

^

CompactProfiles.java:8: error: ResultSet is not available in profile 'compact1'

ResultSet rs;

^

2 errors

The jdeps command will list an application's package or class dependencies. The input to the command can be a jar file, class file, or a directory. The command has numerous options to control the detail of the dependencies. The jdeps command documentation is located at [http://download.java.net/jdk8/docs/technotes/tools/windows/jdeps.html](http://download.java.net/jdk8/docs/technotes/tools/windows/jdeps.html).

To demonstrate the use of this command we will use the Selection Demo project that can be downloaded from [http://docs.oracle.com/javase/tutorial/uiswing/examples/painting/index.html#SwingPaintDemo1](http://docs.oracle.com/javase/tutorial/uiswing/examples/painting/index.html#SwingPaintDemo1). Compile the project and use a command window to navigate to the dist directory where the application’s jar file is saved. Enter the following command:

jdeps SelectionDemo.jar

![](image386.jpg)

A list of the packages used by the application is displayed as shown below:

SelectionDemo.jar -> C:\Program Files\Java\jdk1.8.0\jre\lib\rt.jar

painting (SelectionDemo.jar)

-> java.awt

-> java.awt.event

-> java.io

-> java.lang

-> java.net

-> javax.swing

-> javax.swing.event

If you need a list of all the classes, use the -verbose command line option.

Other Enhancements

This section highlights many of the other enhancements made to Java 8 that do not warrant larger sections.

Javadoc Enhancements

The most visible immediate change is to the Javadoc generated HTML files. These now support a method summary section where tabs have been added to select between types of methods: static, instance, abstract, concrete, or deprecated. The existence of these tabs depends on the methods in the class or interface.

A new DocTree API ([http://download.java.net/jdk8/docs/jdk/api/javac/tree/com/sun/source/doctree/package-summary.html](http://download.java.net/jdk8/docs/jdk/api/javac/tree/com/sun/source/doctree/package-summary.html)) has been added. The API extends the Compiler Tree API and allows for better access to Javadoc contents.

The Javadoc Access API ([http://download.java.net/jdk8/docs/api/javax/tools/package-summary.html](http://download.java.net/jdk8/docs/api/javax/tools/package-summary.html)) provides access to the Javadoc tools from a Java application. In addition, the javadoc tool now checks for invalid HTML code. This check can be turned off using the –Xdoclint option.

Security Enhancements

Various security enhancements have been made to Java 8\. Many of these are not visible to the developer. These include:

- Using x86 AES instructions when possible to improve the out-of-box AES Crypto performance

- Improving the Kerberos 5 implementation by adding the MS-SFU extensions

- Adding support for the TLS Server Name Indication (SNI) Extension

- Adding support for the AEAD/GCM cipher suites

- Improving how caller-sensitive methods are handled

A caller-sensitive method varies its behavior according to the class of its immediate caller. It discovers its caller’s class by invoking the sun.reflect.Reflection.getCallerClass method. Caller-sensitive methods may be invoked using reflection. When this happens a pattern matching technique is used against a manually maintained list of caller-sensitive methods. Instead, all caller-sensitive methods will be marked with the @sun.reflect.CallerSensitive annotation. This will help ensure that the method is invoked against the actual caller class.

In addition, various algorithm implementations were added: NSA Suite B cryptographic algorithms, SHA-224 message-digest algorithm, and SunPKCS11 provider for 64-bit Windows.

Improvements were made to the implementation of the Password-Based-Encryption (PBE) algorithm, the certificate revocation-checking API, and various aspects of the KeyStore API. Also, configuration constraints have been added when generating secure random-numbers.

VM Related Enhancements

There are several VM related improvements most of which are transparent to the typical user. These are listed below to give the reader a feel for what has been done:

- Reduced cache contention when fields of an object are accessed between cores

- Removed the permanent generation to eliminate the need to tune the size of the permanent generation

- Removed three garbage collector combinations that are rarely used

- Provided additional information about verification errors

- Reduced class metadata footprints

- Reduced HotSpot’s class metadata memory footprint to improve performance

- Supported the creation of a small VM

- Added three memory-ordering intrinsics to the sun.misc.Unsafe class

Core Java Enhancements

A number of other changes have been made. These include enhancements to the javac compiler to improve its performance and to improve dynamic memory usage by core-library classes. The Charset class and java.text.DecimalFormat.format method implementations have been improved.

Parts of the API have been upgraded. The platform now supports version 6.2 of the Unicode Standard. Also, JAXP has been upgraded to version 1.5\. A standard API for Base64 encoding and decoding has been added which is found in the java.util.Base64 class.

Annotation improvements have been made to allow multiple annotations of the same type to be applied to a single program element. The Annotation Processing Tool (APT), API, and documentation were removed. It is not possible to model many of the language features added after Java 5 using this tool. The removal was done to transit to JSR 269 (Pluggable Annotation Processing API). This API permits using custom annotation processors with javac.

Core reflection has been improved in several ways. Access to parameter names has been made easier and more reliable. The javax.lang.model.* API uses core reflection instead of using javac.

Conclusion

This chapter examined many new features of Java 8\. We started with an examination of the Nashorn JavaScript engine. This feature allows for the execution of JavaScript code from a Java application. In addition, Java code can be accessed from JavaScript. We saw how several file IO classes and methods can easily support lambda expressions. Methods have been added to the Collections framework including the forEachRemaining and several replace type methods. These expand the capabilities of the Collections Framework. We also looked at additional concurrency enhancements available in Java 8.

* * * * *

Appendix - Date and Time Classes

The purpose of this appendix is to provide an easy way of determining whether a class supports a certain type of method. For example, suppose you want to know if the LocalDateTime class supports conversion to a LocalDate. A to type method may be available for this operation. By examining Table 9 - To Type Method we can see that it does, using the toLocalDate method.

These tables have been adapted from the Java 8 documentation.

-Of Type Methods

-The from Method

-The parse Method

-Get Type Methods

-Is Type Methods

-With Type Methods

-Plus Type Methods

-Minus Type Methods

-To Type Methods

-At Type Methods

Of Type Methods

The static of type methods returns an instance of the class they are executing against. The state of the object is based on the arguments of the method. The unit of measure used by the argument varies from nanoseconds to years. In addition, some methods use other classes and strings as arguments. Table 1 - Of Type Methods lists the classes that support of type methods.

***Table 1 - Of Type Methods***

Class      Methods

Duration of(long amount, TemporalUnit unit)

ofDays(long days)

ofHours(long hours)

ofMillis(long millis)

ofMinutes(long minutes)

ofNanos(long nanos)

ofSeconds(long seconds)

ofSeconds(long seconds, long nanoAdjustment)

Instant ofEpochMilli(long epochMilli)

ofEpochSecond(long epochSecond)

ofEpochSecond(long epochSecond, long nanoAdjustment)

LocalDate of(int year, int month, int dayOfMonth)

of(int year, Month month, int dayOfMonth)

ofEpochDay(long epochDay)

ofYearDay(int year, int dayOfYear)

LocalDateTime

of(int year, int month, int dayOfMonth, int hour, int minute)

of(int year, int month, int dayOfMonth, int hour, int minute, int second)

of(int year, int month, int dayOfMonth, int hour, int minute, int second, int nanoOfSecond)

of(int year, Month month, int dayOfMonth, int hour, int minute)

of(int year, Month month, int dayOfMonth, int hour, int minute, int second)

of(int year, Month month, int dayOfMonth, int hour, int minute, int second, int nanoOfSecond)

of(LocalDate date, LocalTime time)

ofEpochSecond(long epochSecond, int nanoOfSecond, ZoneOffset offset)

ofInstant(Instant instant, ZoneId zone)

LocalTime of(int hour, int minute)

of(int hour, int minute, int second)

of(int hour, int minute, int second, int nanoOfSecond)

ofNanoOfDay(long nanoOfDay)

ofSecondOfDay(long secondOfDay)

MonthDay of(int month, int dayOfMonth)

of(Month month, int dayOfMonth)

OffsetDateTime  of(int year, int month, int dayOfMonth, int hour, int minute, int second, int nanoOfSecond, ZoneOffset offset)

of(LocalDate date, LocalTime time, ZoneOffset offset)

of(LocalDateTime dateTime, ZoneOffset offset)

ofInstant(Instant instant, ZoneId zone)

OffsetTime of(LocalTime time, ZoneOffset offset)

ofInstant(Instant instant, ZoneId zone)

Period of(int years, int months, int days)

ofDays(int days)

ofMonths(int months)

ofWeeks(int weeks)

ofYears(int years)

Year of(int isoYear)

YearMonth

of(int year, int month)

of(int year, Month month)

ZonedDateTime of(int year, int month, int dayOfMonth, int hour, int minute, int second, int nanoOfSecond, ZoneId zone)

of(LocalDate date, LocalTime time, ZoneId zone)

of(LocalDateTime localDateTime, ZoneId zone)

ofInstant(Instant instant, ZoneId zone)

ofInstant(LocalDateTime localDateTime, ZoneOffset offset, ZoneId zone)

ofLocal(LocalDateTime localDateTime, ZoneId zone, ZoneOffset preferredOffset)

ofStrict(LocalDateTime localDateTime, ZoneOffset offset, ZoneId zone)

ZoneId  of(String zoneId)

of(String zoneId, Map<String,String> aliasMap)

ofOffset(String prefix, ZoneOffset offset)

ZoneOffset of(String offsetId)

ofHours(int hours)

ofHoursMinutes(int hours, int minutes)

ofHoursMinutesSeconds(int hours, int minutes, int seconds)

ofTotalSeconds(int totalSeconds)

The from Method

The static from method is very consistent in its signature from class to class with the exception of the Duration class. The method returns an instance of the class it executes against. Each from method accepts a TemporalAccessor object as an argument with the exception of the Duration class which uses a TemporalAmount object. Table 2 lists the classes that support the from method.

***Table 2 - From Methods***

**Class  ** Method

**Duration** from(TemporalAmount amount)

**Instant** from(TemporalAccessor temporal)

**LocalDate ** from(TemporalAccessor temporal)

**LocalDateTime** from(TemporalAccessor temporal)

**LocalTime** from(TemporalAccessor temporal)

**MonthDay** from(TemporalAccessor temporal)

**OffsetDateTime** from(TemporalAccessor temporal)

**OffsetTime** from(TemporalAccessor temporal)

**Period** from(TemporalAmount amount)

**Year** from(TemporalAccessor temporal)

**YearMonth** from(TemporalAccessor temporal)

**ZonedDateTime** from(TemporalAccessor temporal)

**ZoneId** from(TemporalAccessor temporal)

**ZoneOffset** from(TemporalAccessor temporal)

The parse Method

The static parse method is consistent between those classes that implement it. The method returns an instance of the class it executes against. The overloaded method uses either one or two arguments. The first argument is always a CharSequence. When the second argument is present, it is a DateTimeFormatter instance. Table 3 - Parse Methods lists the classes that support the parse method.

Class

Methods Supported

Duration

Instant

LocalDate

LocalDateTime

LocalTime

MonthDay

Period

parse(CharSequence text)

OffsetDateTime

OffsetDateTime

OffsetTime

OffsetTime

Year

Year

YearMonth

YearMonth

ZonedDateTime

ZonedDateTime

parse(CharSequence text)

parse(CharSequence text, DateTimeFormatter formatter)

***Table 3 - Parse Methods***

**Class  ** Methods Supported

**Duration  | Instant | LocalDate | LocalDateTime | LocalTime | MonthDay | Period      ** parse(CharSequence text)

**OffsetDateTime | OffsetTime | Year | YearMonth | ZonedDateTime      ** parse(CharSequence text) **|** parse(CharSequence text, DateTimeFormatter formatter)

Get Type Methods

The get method returns information about an object. The information is usually of type integer but a class or enumeration may also be returned. The methods supported by a class depend on the needs of the class. Table 4 - Get Type Methods lists the classes that support get type methods.

***Table 4 - Get Type Methods***

**Class  ** Method

**Clock  ZoneId** getZone()

**Duration** long  get(TemporalUnit unit)

int  getNano()

long  getSeconds()

List<TemporalUnit>  getUnits()

**Instant** int  get(TemporalField field)

long  getEpochSecond()

long  getLong(TemporalField field)

int  getNano()

**LocalDate** int  get(TemporalField field)

IsoChronology  getChronology()

int  getDayOfMonth()

DayOfWeek  getDayOfWeek()

int  getDayOfYear()

Era  getEra()

long  getLong(TemporalField field)

Month  getMonth()

int  getMonthValue()

int  getYear()

**LocalDateTime** int  get(TemporalField field)

int  getDayOfMonth()

DayOfWeek  getDayOfWeek()

int  getDayOfYear()

int  getHour()

long  getLong(TemporalField field)

int  getMinute()

Month  getMonth()

int  getMonthValue()

int  getNano()

int  getSecond()

int  getYear()

**LocalTime** int  get(TemporalField field)

int  getHour()

long  getLong(TemporalField field)

int  getMinute()

int  getNano()

int  getSecond()

**MonthDay** int  get(TemporalField field)

int  getDayOfMonth()

long  getLong(TemporalField field)

Month  getMonth()

int  getMonthValue()

**OffsetDateTime** int  get(TemporalField field)

int  getDayOfMonth()

DayOfWeek  getDayOfWeek()

int  getDayOfYear()

int  getHour()

long  getLong(TemporalField field)

int  getMinute()

Month  getMonth()

int  getMonthValue()

int  getNano()

ZoneOffset  getOffset()

int  getSecond()

int  getYear()

**OffsetTime** int  get(TemporalField field)

int  getHour()

long  getLong(TemporalField field)

int  getMinute()

int  getNano()

ZoneOffset  getOffset()

int  getSecond()

**Period long** get(TemporalUnit unit)

IsoChronology  getChronology()

int  getDays()

int  getMonths()

List<TemporalUnit>  getUnits()

int  getYears()

**Year** int  get(TemporalField field)

long  getLong(TemporalField field)

int  getValue() Gets the year value.

**YearMonth** int  get(TemporalField field)

long  getLong(TemporalField field)

Month  getMonth()

int  getMonthValue()

int  getYear()

**ZonedDateTime** int  get(TemporalField field)

int  getDayOfMonth()

DayOfWeek  getDayOfWeek()

int  getDayOfYear()

int  getHour()

long  getLong(TemporalField field)

int  getMinute()

Month  getMonth()

int  getMonthValue()

int  getNano()

ZoneOffset  getOffset()

int  getSecond()

int  getYear()

ZoneId  getZone()

**ZoneId** static Set<String>  getAvailableZoneIds()

String  getDisplayName(TextStyle style, Locale locale)

abstract String  getId()

abstract ZoneRules  getRules()

**ZoneOffset** int  get(TemporalField field)

String  getId()

Long getLong(TemporalField field)

ZoneRules getRules()

int  getTotalSeconds()

Is Type Methods

The is type methods all return a boolean value. The actual method supported by a class is dependent on the requirements of the class. Table 5 - Is Type Methods lists the classes that support is type methods.

***Table 5 - Is Type Methods***

**Class  ** Methods

**Duration** boolean  isNegative

boolean  isZero()

**Instant** boolean  isAfter(Instant otherInstant)

boolean  isBefore(Instant otherInstant)

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**LocalDate** boolean  isAfter(ChronoLocalDate other)

boolean  isBefore(ChronoLocalDate other)

boolean  isEqual(ChronoLocalDate other)

boolean  isLeapYear()

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**LocalDateTime** boolean  isAfter(ChronoLocalDateTime<?> other)

boolean  isBefore(ChronoLocalDateTime<?> other)

boolean  isEqual(ChronoLocalDateTime<?> other)

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**LocalTime** boolean  isAfter(LocalTime other)

boolean  isBefore(LocalTime other)

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**MonthDay** boolean  isAfter(MonthDay other)

boolean  isBefore(MonthDay other)

boolean  isSupported(TemporalField field)

boolean  isValidYear(int year)

**OffsetDateTime** boolean  isAfter(OffsetDateTime other)

boolean  isBefore(OffsetDateTime other)

boolean  isEqual(OffsetDateTime other)

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**OffsetTime** boolean  isAfter(OffsetTime other)

boolean  isBefore(OffsetTime other)

boolean  isEqual(OffsetTime other)

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**Period boolean** isNegative()

boolean  isZero()

**Year** boolean  isAfter(Year other)

boolean  isBefore(Year other)

boolean  isLeap()

static boolean  isLeap(long year)

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

boolean  isValidMonthDay(MonthDay monthDay)

**YearMonth** boolean  isAfter(YearMonth other)

boolean  isBefore(YearMonth other)

boolean  isLeapYear()

boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

boolean  isValidDay(int dayOfMonth)

**ZonedDateTime** boolean  isSupported(TemporalField field)

boolean  isSupported(TemporalUnit unit)

**ZoneOffset** boolean  isSupported(TemporalField field)

With Type Methods

These methods always return an instance of the class they execute against. The methods supported vary by class. In general, they return a modified version of the original class. Table 6 - With Type Methods lists the classes that support with type methods.

***Table 6 - With Type Methods***

**Class** Method

**Clock ** Clock  withZone(ZoneId zone)

**Duration** Duration  withNanos(int nanoOfSecond)

Duration  withSeconds(long seconds)

**Instant** Instant  with(TemporalAdjuster adjuster)

Instant  with(TemporalField field, long newValue)

**LocalDate** LocalDate  with(TemporalAdjuster adjuster)

LocalDate  with(TemporalField field, long newValue)

LocalDate  withDayOfMonth(int dayOfMonth)

LocalDate  withDayOfYear(int dayOfYear)

LocalDate  withMonth(int month)

LocalDate  withYear(int year)

**LocalDateTime** LocalDateTime  with(TemporalAdjuster adjuster)

LocalDateTime  with(TemporalField field, long newValue)

LocalDateTime  withDayOfMonth(int dayOfMonth)

LocalDateTime  withDayOfYear(int dayOfYear)

LocalDateTime  withHour(int hour)

LocalDateTime  withMinute(int minute)

LocalDateTime  withMonth(int month)

LocalDateTime  withNano(int nanoOfSecond)

LocalDateTime  withSecond(int second)

LocalDateTime  withYear(int year)

**LocalTime** LocalTime  with(TemporalAdjuster adjuster)

LocalTime  with(TemporalField field, long newValue)

LocalTime  withHour(int hour)

LocalTime  withMinute(int minute)

LocalTime  withNano(int nanoOfSecond)

LocalTime  withSecond(int second)

**MonthDay** MonthDay  with(Month month)

MonthDay  withDayOfMonth(int dayOfMonth)

MonthDay  withMonth(int month)

**OffsetDateTime** LocalDateTime  with(TemporalAdjuster adjuster)

LocalDateTime  with(TemporalField field, long newValue)

LocalDateTime  withDayOfMonth(int dayOfMonth)

LocalDateTime  withDayOfYear(int dayOfYear)

LocalDateTime  withHour(int hour)

LocalDateTime  withMinute(int minute)

LocalDateTime  withMonth(int month)

LocalDateTime  withNano(int nanoOfSecond)

LocalDateTime  withSecond(int second)

LocalDateTime  withYear(int year)

**OffsetTime** OffsetTime  with(TemporalAdjuster adjuster)

OffsetTime  with(TemporalField field, long newValue)

OffsetTime  withHour(int hour)

OffsetTime  withMinute(int minute)

OffsetTime  withNano(int nanoOfSecond)

OffsetTime  withOffsetSameInstant(ZoneOffset offset)

OffsetTime  withOffsetSameLocal(ZoneOffset offset)

OffsetTime  withSecond(int second)

**Period** Period  withDays(int days)

Period  withMonths(int months)

Period  withYears(int years)

**Year** Year  with(TemporalAdjuster adjuster)

Year  with(TemporalField field, long newValue)

**YearMonth** YearMonth  with(TemporalAdjuster adjuster)

YearMonth  with(TemporalField field, long newValue)

YearMonth  withMonth(int month)

YearMonth  withYear(int year)

**ZonedDateTime** ZonedDateTime  with(TemporalAdjuster adjuster)

ZonedDateTime  with(TemporalField field, long newValue)

ZonedDateTime  withDayOfMonth(int dayOfMonth)

ZonedDateTime  withDayOfYear(int dayOfYear)

ZonedDateTime  withEarlierOffsetAtOverlap()

ZonedDateTime  withFixedOffsetZone()

ZonedDateTime  withHour(int hour)

ZonedDateTime  withLaterOffsetAtOverlap()

ZonedDateTime  withMinute(int minute)

ZonedDateTime  withMonth(int month)

ZonedDateTime  withNano(int nanoOfSecond)

ZonedDateTime  withSecond(int second)

ZonedDateTime  withYear(int year)

ZonedDateTime  withZoneSameInstant(ZoneId zone)

ZonedDateTime  withZoneSameLocal(ZoneId zone)

Plus Type Methods

These methods return a new object after adding a time unit to an existing object. The object returned is of the same type as the object the method was executed against. The methods supported depend on the class, but all classes support the following method:

plus(long amountToAdd, TemporalUnit unit)

![](image387.jpg)

**Table 7 - Plus Type Methods lists the classes that support plus type methods.**

***Table 7 - Plus Type Methods***

**Class  ** Methods

**Duration** Duration  plus(long amountToAdd, TemporalUnit unit)

Duration  plusDays(long daysToAdd)

Duration  plusHours(long hoursToAdd)

Duration  plusMillis(long millisToAdd)

Duration  plusMinutes(long minutesToAdd)

Duration  plusNanos(long nanosToAdd)

Duration  plusSeconds(long secondsToAdd)

**Instant** Instant  plus(long amountToAdd, TemporalUnit unit)

Instant  plus(TemporalAmount amountToAdd)

Instant  plusMillis(long millisToAdd)

Instant  plusNanos(long nanosToAdd)

Instant  plusSeconds(long secondsToAdd)

**LocalDate** LocalDate  plus(long amountToAdd, TemporalUnit unit)

LocalDate  plus(TemporalAmount amountToAdd)

LocalDate  plusDays(long daysToAdd)

LocalDate  plusMonths(long monthsToAdd)

LocalDate  plusWeeks(long weeksToAdd)

LocalDate  plusYears(long yearsToAdd)

**LocalDateTime** LocalDateTime  plus(long amountToAdd, TemporalUnit unit)

LocalDateTime  plus(TemporalAmount amountToAdd)

LocalDateTime  plusDays(long days)

LocalDateTime  plusHours(long hours)

LocalDateTime  plusMinutes(long minutes)

LocalDateTime  plusMonths(long months)

LocalDateTime  plusNanos(long nanos)

LocalDateTime  plusSeconds(long seconds)

LocalDateTime  plusWeeks(long weeks)

LocalDateTime  plusYears(long years)

**LocalTime** LocalTime  plus(long amountToAdd, TemporalUnit unit)

LocalTime  plus(TemporalAmount amountToAdd)

LocalTime  plusHours(long hoursToAdd)

LocalTime  plusMinutes(long minutesToAdd)

LocalTime  plusNanos(long nanosToAdd)

LocalTime  plusSeconds(long secondstoAdd)

**OffsetDateTime** OffsetDateTime  plus(long amountToAdd, TemporalUnit unit)

OffsetDateTime  plus(TemporalAmount amountToAdd)

OffsetDateTime  plusDays(long days)

OffsetDateTime  plusHours(long hours)

OffsetDateTime  plusMinutes(long minutes)

OffsetDateTime  plusMonths(long months)

OffsetDateTime  plusNanos(long nanos)

OffsetDateTime  plusSeconds(long seconds)

OffsetDateTime  plusWeeks(long weeks)

OffsetDateTime  plusYears(long years)

**OffsetTime** OffsetTime  plus(long amountToAdd, TemporalUnit unit)

OffsetTime  plus(TemporalAmount amountToAdd)

OffsetTime  plusHours(long hours)

OffsetTime  plusMinutes(long minutes)

OffsetTime  plusNanos(long nanos)

OffsetTime  plusSeconds(long seconds)

**Period** Period  plus(TemporalAmount amountToAdd)

Period  plusDays(long daysToAdd)

Period  plusMonths(long monthsToAdd)

Period  plusYears(long yearsToAdd)

**Year** Year  plus(long amountToAdd, TemporalUnit unit)

Year  plus(TemporalAmount amountToAdd)

Year  plusYears(long yearsToAdd)

**YearMonth** YearMonth  plus(long amountToAdd, TemporalUnit unit)

YearMonth  plus(TemporalAmount amountToAdd)

YearMonth  plusMonths(long monthsToAdd)

YearMonth  plusYears(long yearsToAdd)

**ZonedDateTime** ZonedDateTime  plus(long amountToAdd, TemporalUnit unit)

ZonedDateTime  plus(TemporalAmount amountToAdd)

ZonedDateTime  plusDays(long days)

ZonedDateTime  plusHours(long hours)

ZonedDateTime  plusMinutes(long minutes)

ZonedDateTime  plusMonths(long months)

ZonedDateTime  plusNanos(long nanos)

ZonedDateTime  plusSeconds(long seconds)

ZonedDateTime  plusWeeks(long weeks)

ZonedDateTime  plusYears(long years)

Minus Type Methods

The minus type methods all return the same type of class that they execute against. The object returned is a new object that is based on the original object where a unit of time has been subtracted. The methods supported are dependent on the class. However, with the exception of the Duration class, they all support the following method:

minus(TemporalAmount amountToSubtract)

![](image388.jpg)

Table 8 - Minus Type Methods lists the classes that support minus type methods.

**Table 8 - Minus Type Methods**

**Class  ** Method

**Duration** minus(Duration duration)

minus(long amountToSubtract, TemporalUnit unit)

minusDays(long daysToSubtract)

minusHours(long hoursToSubtract)

minusMillis(long millisToSubtract)

minusMinutes(long minutesToSubtract)

minusNanos(long nanosToSubtract)

minusSeconds(long secondsToSubtract)

**Instant** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusMillis(long millisToSubtract)

minusNanos(long nanosToSubtract)

minusSeconds(long secondsToSubtract)

**LocalDate** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusDays(long daysToSubtract)

minusMonths(long monthsToSubtract)

minusWeeks(long weeksToSubtract)

minusYears(long yearsToSubtract)

**LocalDateTime** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusDays(long days)

minusHours(long hours)

minusMinutes(long minutes)

minusMonths(long months)

minusNanos(long nanos)

minusSeconds(long seconds)

minusWeeks(long weeks)

minusYears(long years)

**LocalTime** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusHours(long hoursToSubtract)

minusMinutes(long minutesToSubtract)

minusNanos(long nanosToSubtract)

minusSeconds(long secondsToSubtract)

**OffsetDateTime** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusDays(long days)

minusHours(long hours)

minusMinutes(long minutes)

minusMonths(long months)

minusNanos(long nanos)

minusSeconds(long seconds)

minusWeeks(long weeks)

minusYears(long years)

**OffsetTime** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusHours(long hours)

minusMinutes(long minutes)

minusNanos(long nanos)

minusSeconds(long seconds)

**Period** minus(TemporalAmount amountToSubtract)

minusDays(long daysToSubtract)

minusMonths(long monthsToSubtract)

minusYears(long yearsToSubtract)

**Year** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusYears(long yearsToSubtract)

**YearMonth** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusMonths(long monthsToSubtract)

minusYears(long yearsToSubtract)

**ZonedDateTime** minus(long amountToSubtract, TemporalUnit unit)

minus(TemporalAmount amountToSubtract)

minusDays(long days)

minusHours(long hours)

minusMinutes(long minutes)

minusMonths(long months)

minusNanos(long nanos)

minusSeconds(long seconds)

minusWeeks(long weeks)

minusYears(long years)

To Type Methods

These types of methods usually transform an object into a different type of data. Often it is an integer. It may also return a string or temporal object. They return different types depending on their purpose. Table 9 - To Type Methods lists the classes that support to type methods.

***Table 9 - To Type Methods***

**Class  ** Method

**Duration** long  toDays()

long  toHours()

long  toMillis()

long  toMinutes()

long  toNanos()

String  toString()

**Instant** long  toEpochMilli()

String  toString()

**LocalDate** long  toEpochDay()

String  toString()

**LocalDateTime** LocalDate  toLocalDate()

LocalTime  toLocalTime()

String  toString()

**LocalTime** long  toNanoOfDay()

int  toSecondOfDay()

String  toString()

**MonthDay** String  toString()

**OffsetDateTime** long  toEpochSecond()

Instant  toInstant()

LocalDate  toLocalDate()

LocalDateTime  toLocalDateTime()

LocalTime  toLocalTime()

OffsetTime  toOffsetTime()

String  toString()

ZonedDateTime  toZonedDateTime()

**OffsetTime** LocalTime  toLocalTime()

String  toString()

**Period** String  toString()

long  toTotalMonths()

**Year** String  toString()

**YearMonth   ** String  toString()

**ZonedDateTime** LocalDate  toLocalDate()

LocalDateTime  toLocalDateTime()

LocalTime  toLocalTime()

OffsetDateTime  toOffsetDateTime()

String  toString()

**ZoneId** String  toString()

**ZoneOffset** String  toString()

At Type Methods

The static at type methods return a new object based on a temporal unit such as time zone, local date, hours, or minutes. Table 10 - At Type Methods lists the classes that support of type methods.

***Table 10 - At Type Methods***

**Class  ** Method

**Instant** OffsetDateTime  atOffset(ZoneOffset offset)

ZonedDateTime  atZone(ZoneId zone)

**LocalDate** LocalDateTime  atStartOfDay()

ZonedDateTime  atStartOfDay(ZoneId zone)

LocalDateTime  atTime(int hour, int minute)

LocalDateTime  atTime(int hour, int minute, int second)

LocalDateTime  atTime(int hour, int minute, int second, int nanoOfSecond)

LocalDateTime  atTime(LocalTime time)

OffsetDateTime  atTime(OffsetTime time)

**LocalDateTime** OffsetDateTime  atOffset(ZoneOffset offset)

ZonedDateTime  atZone(ZoneId zone)

**LocalTime     ** LocalDateTime  atDate(LocalDate date)

OffsetTime  atOffset(ZoneOffset offset)

**MonthDay     ** LocalDate  atYear(int year)

**OffsetDateTime** ZonedDateTime  atZoneSameInstant(ZoneId zone)

ZonedDateTime  atZoneSimilarLocal(ZoneId zone)

**OffsetTime** OffsetDateTime  atDate(LocalDate date)

**Year   ** LocalDate  atDay(int dayOfYear)

YearMonth  atMonth(int month)

YearMonth  atMonth(Month month)

LocalDate  atMonthDay(MonthDay monthDay)

**YearMonth   ** LocalDate  atDay(int dayOfMonth)

LocalDate  atEndOfMonth()

* * * * *

Other Books from P8tech

![](image389.jpg)

Java Masterclass: Java Exceptions, Assertions and Logging by Sam Alapati

Is your Java system setup to handle programming errors, or exceptions, gracefully and with minimal impact on the user experience? Do you know how to setup assertions to check your code? Do you know how to log events so that issues can be assessed and debugged painlessly and easily? Help is at hand! Welcome to your ‘Java Masterclass: Java Exceptions, Assertions and Logging’ - a concise, focused book designed to get you up-and-running in this critical world of Java development and administration.

Written by leading Java Expert, Sam Alapati, and aimed at newcomers to the world of exceptions, assertions and logging, this book cuts-to-the-chase in a logical and easy-to-understand manner. Get under the hood and find out about declaring, throwing and catching exceptions; what checked and unchecked exceptions mean; how to define custom exception classes; why (and how) you should use assertions; the value and power of logging; and much more!

![](image390.jpg)

Getting Started with Elastix by David Duffett

Elastix is class leading unified communications server software - fully Open Source - and is used by a huge number of people and organizations across the world.

Aimed at newcomers to Elastix this concise and highly focused ‘Getting Started’ book aims to have your VOIP system up-and-running fast. From installation to implementing your first extension, from trunks to custom dial plans and queues – this succinct book cuts-to-the-chase in a practical, focused, and easy-to-understand manner.

* * * * *