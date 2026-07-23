![](cover.jpeg)

**A Software Engineer Learns Java 8 – The Fundamentals**

**By Dane Cameron**

**© 2014 Dane Cameron**

All rights reserved. No part of this publication may be reproduced, distributed, or transmitted in any form or by any means, including photocopying, recording, or other electronic or mechanical methods, without the prior written permission of the publisher, except in the case of brief quotations embodied in critical reviews and certain other non-commercial uses permitted by copyright law.

Original and modified cover design by Karuanka Rayker and CoverDesignStudio.com

Cisdal Publishing
[dane@cisdal.com](mailto:dane@cisdal.com)

www.cisdal.com

# Table of Contents

[Introduction](#part0000_split_003.html__Introduction)

[About this book](#part0000_split_009.html__About_this_book)

[Lambda Expressions](#part0000_split_018.html__Lambda_Expressions)

[Streams API](#part0000_split_023.html__Streams_API)

[Interfaces](#part0000_split_029.html__Interfaces)

[Java Date and Time API](#part0000_split_032.html__Java_Time)

[Nashorn](#part0000_split_038.html__Nashorn)

[Minor Changes](#part0000_split_045.html__Minor_Changes)

[Conclusion](#part0000_split_051.html__Conclusion)

[Appendix A: JavaScript](#part0000_split_052.html__Appendix_A:_JavaScript)

# Introduction

I first learned Java in the late-1990s using Java 1.1\. Back then there was a great sense of excitement about Java. Not only did it support a Write-Once Run-Anywhere philosophy, it embraced the Internet, and provided native support for networking, threading, and the much hyped Applet technology. In fact, it is worth reiterating the five primary goals of the Java language:

• It should be "simple, object-oriented and familiar"

• It should be "robust and secure"

• It should be "architecture-neutral and portable"

• It should execute with "high performance"

• It should be "interpreted, threaded, and dynamic"

A lot has changed since I first learned Java. Computers have become vastly more powerful, and data sets have become orders of magnitude larger. Java has kept pace with many of these changes very well, and still remains perhaps the most widely used programming language in commercial environments, particularly for server-side development. It has also maintained a dynamic and wide-ranging presence in the open source world, and has been incorporated into other technologies from Android to Salesforce.

Despite this, aspects of Java have begun to feel dated when compared to many newer (or newly rediscovered) languages. There have been few major enhancements to the Java language since Generics were introduced in Java 5 (way back in 2004). A common refrain in recent years is “Java is the new Cobol” – widely used but not widely loved. I don’t personally buy into this mantra: Java supports a set of frameworks, libraries and tools second-to-none, particularly for server-side computing - but Java does lack the expressiveness found in many other languages.

Java 8 is the biggest change to Java in at least the last 10 years, and possibly since its inception. It incorporates a number of features that have been consistently requested for years (most notably lambda expressions), and is an effort to maintain Java’s relevance in a world of multi-cored machines by adding additional support for parallelism: in fact parallel computing is the driving force behind most of the changes in Java 8 (at least from Oracle’s point of view).

The sections below guide you through the core themes of Java 8\. Later chapters will then introduce the features added to Java 8 in relation to these themes.

## Functional Programming

Functional programming is a programming paradigm where algorithms are implemented via functions that accept values and return values in return. It is a style of programming that avoids state, and avoids mutation of data – the result of a function depends entirely on its inputs. To put this another way, the same inputs always produces the same results.

I didn’t fully appreciate what Java was missing until I learned JavaScript (properly) in the last few years, as documented in my book “A Software Engineer Learns HTML5, JavaScript and jQuery“. Before learning JavaScript I had a reasonably low opinion of the language, largely based on experiences of trying to shoehorn its syntax into Java style programs.

Learning JavaScript properly showed me how powerful functional programming concepts can be even in a language embracing imperative and object-orientated programming paradigms. I was not completely unfamiliar with functional programming, but had not used functional programming techniques in my commercial work since leaving University.

I wasn’t the only one who noticed the value of functional programming techniques of course. For many years there has been a concerted push behind the idea of adding functional programming features (lambda expressions or closures) to the Java language, and this has even led to the creation of several new languages on the JVM, most notably Scala.

Java 8 provides a significant new feature called “lambda expressions”. These are essentially anonymous methods that can be constructed on the fly, assigned to variables, and passed to other methods as parameters. These have been embedded into the language, with many existing APIs being extended to provide support for lambda expressions.

Java 8 is not suddenly trying to become the equivalent of pure functional languages such as Haskell or LISP: it is attempting to add a new paradigm alongside its object-orientated paradigm. The introduction of lambda expressions are non-intrusive in the sense you can choose to ignore them if you want to, but I hope after working through the examples in this book you appreciate their place in the language, and the elegance of code utilizing them.

## Parallelism

Another major change that has occurred in computing since I began with Java is the requirement to process larger and larger datasets, and to do so in a multi-threaded manner. Google has probably done more than most to popularize approaches to processing large datasets, notably with the MapReduce algorithm (which has already been implemented in Java in the form of Hadoop).

Java 8 sees the addition of several features, most notably the Streams API, designed to simplify the process of dealing with large data sets, and to allow programmers to request parallelism rather than explicitly implement it themselves.

The principles behind these features are good, however they cannot entirely hide the complexities of parallelism, and failing to understand the new features can lead to significant issues. This book will work through the Streams API in depth, and assess where parallel processing can, and cannot be used effectively.

## Making up for old mistakes

The Java Date API has been consistently criticized for many years. Just a short look through the list of deprecated methods on java.util.Date leaves you in no doubt mistakes were made.

One of the great things about Java is that when the official language makes mistakes, the open source community fixes them through libraries. In the case of date and time, the Joda time library has filled the gap. As often happens (especially in the Java EE world), Java has been more than happy to learn from the success of others, and has incorporated a new Date/Time API based on Joda in Java 8.

The existing Date and Calendar API remains unchanged, and you can continue to use that if you wish, or use it in conjunction with the new Date/Time API.

## Dynamic Languages

Java added explicit support for dynamic languages in Java 7 with the InvokeDynamic instruction. As a result, the Java runtime now supports a wide array of dynamic languages. Implementing a language on the Java platform brings great benefits for the language (since it gets access to all the libraries and frameworks in the Java ecosystem), but also brings great benefits to the Java as well.

Java 8 has added native support for a JavaScript engine called Nashorn. Nashorn has been written from the ground up to work with the dynamic language support in Java, and replaces the Rhino JavaScript engine that has been available for a number of years.

In case you had not noticed, JavaScript has moved outside the browser in the last few years and is now widely used as a server-side language – most notably via node.js. The addition of Nashorn on the Java platform could bring interesting developments in the near future, especially for server-side computing.

## A few surprises

Sun made a conscious decision to exclude multiple inheritance from Java when it was originally specified. Multiple inheritance allows a single class to inherit functionality from two or more classes. In its place Java used interfaces (which could not provide implementations), and allowed a class to implement multiple interfaces.

Multiple inheritance was omitted from Java for a number of reasons, not least because of the famous ”diamond problem”, which is a problem that can arise when a class inherits different implementations of the same method from its parent classes.

Java 8 has partially removed its restriction on multiple inheritance with the introduction of default methods (aka defender methods) on interfaces. The main reason this feature has been added is because Java has been unable to extend any of the core-language interfaces, since this would break existing code for third parties who implement these interfaces. This change has meant many existing interfaces (such as List and Set) now have additional methods.

# About this book

## Who is this book for?

This book is intended for anyone familiar with Java who wants to learn about Java 8\. If you are not already familiar with Java this is not the book for you: you need to have a reasonable grasp of the language before jumping into these features.

Additionally, this book is intended for programmers and software engineers who use Java to write applications. Java 8 also includes changes to the Java Runtime and changes to the byte code generated from compiled Java: these features will not impact programmers on a daily basis, and therefore have been ignored. For instance, many of the features in Java 8 are designed to improve the performance of the Java platform in one-way or another. For the most part, these features are unlikely to change the way you write code.

The goal has been to produce a book that can be read in a couple of afternoons, and that provides enough code examples to allow you to understand the fundamentals of each new feature. Once you understand these fundamentals, expanding your knowledge will be relatively trivial.

As a result, this book will not try to act as a reference book, and will not contain details of every new method, class or interface added in Java 8\. Once you understand the fundamentals it is relatively simple to use the Java Doc or other online help to expand this knowledge, and find approaches for specific requirements.

I have made this book exactly the length I think it needs to be to cover the material in appropriate detail. One of the major benefits of eBooks is that it is possible to write shorter books where appropriate, and charge a price matching the length.

## What do I need?

Since Java 8 is new, this section will change on a regular basis. The book’s website will therefore contain the most up to date version of this section:

[http://www.cisdal.com/java8.html](http://www.cisdal.com/java8.html)

In order to follow the examples you need Java 8\. The JDK can be downloaded from here:

[https://jdk8.java.net/download.html](https://jdk8.java.net/download.html)

You are also going to need an IDE that supports Java 8\. IDEs need to rollout specific support for Java 8, therefore it is possible your favorite IDE will not support Java 8 at this point.

I have used NetBeans for the examples in this book, largely because it has a Java 8 compatible installer for OSX and other platforms. The following page provides links for a Java 8 compatible version of NetBeans:

[https://netbeans.org/kb/docs/java/javase-jdk8.html](https://netbeans.org/kb/docs/java/javase-jdk8.html)

Eclipse support is available, but it currently requires slightly more effort to install a version of Eclipse with Java 8 support. The following page contains instructions:

[https://wiki.eclipse.org/JDT_Core/Java8](https://wiki.eclipse.org/JDT_Core/Java8)

## Why I wrote this book

I wrote this book because I use Java on a daily basis. Over the years I have tried to keep track of the changes that have occurred to the language when each new version of Java was released.

Describing the process I went through to learn Java 8 is an excellent way for me to consolidate my knowledge of these features, and hopefully a good opportunity to pass on what I learnt to others.

## Blatant Plug

With Java officially embracing JavaScript, I figured there was no better time to promote my book “A Software Engineer Learns HTML5, JavaScript and jQuery” to the Java community. This book takes you through my process of learning to write standards-based web applications with HTML5 and JavaScript after a career using Java.

As a bonus I have added a chapter on JavaScript from that book to encourage you to learn JavaScript, and gain an understanding of what has become a surprisingly elegant and mature language.

## Caveat

Java casts a very large net. Hundreds of thousands of programmers use the Java platform, and use it in wildly different ways, and from multitude points of view. As a result there are divergent opinions on many Java features, and that extends to Java 8.

Although I am enthusiastic about the changes in Java 8, and intend to use them in my professional work, this book is not intended as a cheerleading exercise. The book sets out to teach you the new features, and how they can be used. It is up to you to decide whether you feel these features add value – if they don’t there is no reason you need to change the way you are programming now.

Many people also have strong opinions on how these features should have been implemented in the language. For instance, there has been years of debate around how lambda expressions should be implemented. I am taking the view that that ship has sailed: I will present the features as they have been implemented and not waste time talking about how they could have been implemented.

## Conventions

Code in this book will utilize the following font:

This is code

Unfortunately some eBook readers cannot use custom fonts. If you have any issues with code readability, please contact me at dane@cisdal.com.

## Code Examples

Most of the examples in this book are very simple, and can be coded by hand. If you would like a version that can be copied and pasted, all the examples can be found here, broken down by chapter:

[www.cisdal.com/java8.html](http://www.cisdal.com/java8.html)

## Feedback

I would love to hear your feedback (positive and negative) on this book. Please email me at [dane@cisdal.com](mailto:dane@cisdal.com).   

# Lambda Expressions

The best place to start our look at Java 8 is with its most widely anticipated feature: lambda expressions (JSR 335 https://jcp.org/en/jsr/detail?id=335). These are also a dependency for several of the other features added to Java 8, so these other features cannot be understood without a grasp of lambda expressions.

Lambda expressions had originally been slated for inclusion in Java 7, and had been requested widely for many years before that. Lambda expressions (commonly known as closures or anonymous methods) allow you to encapsulate a block of code in an anonymous method (i.e. a method without a name or enclosing class), and pass it to another method which will invoke it at the appropriate time. This may sound like a simple technique (and it is) but it brings tremendous benefits, especially when used in conjunction with another Java 8 feature: the Streams API.

The closest Java has had to lambda expressions in the past were anonymous and local classes. These were classes defined and instantiated inside a method, and often passed to another method to perform an operation. In the case of anonymous classes it was not necessary to name the class.

Anonymous classes are widely used as callbacks, and have been commonly used to implement interfaces such as Runnable and ActionListener.

Lambda expressions are the next step along a continuum from anonymous classes, so we will begin with an example of an anonymous class to see why many people felt lambda expressions were necessary.

Consider a piece of code that filters all even numbers out of a list of integers, producing a new list of odd numbers. Naturally this could be achieved through iteration and imperative programming techniques, but another way to write this is to define a method that accepts each element in the list, and returns true or false to indicate whether the element should be retained in the list – and to define a generic library for iterating the list and invoking the method on each element.

The advantage of this approach is that we can reuse the generic filtering algorithm, and just replace the method that makes the filtering decision.

To start, we can define an Interface for classes that will make filtering decisions:

package localclasses;

public interface Filter<T> {

 boolean filter(T t);

}

Next, we can write a static helper class that performs generic filtering. We will call this Collections2 since it is enhancing the methods Java makes available on the Collections class. This will create a new empty List, iterate through the items in the original list, and invoke the filter method on the instance of Filter passed to it - those that return true will be added to the new list:

package localclasses;

import java.util.ArrayList;

import java.util.List;

public class Collections2 {

 public static <T> List<T> filter(

 List<T> input, Filter<T> filter) {

 List<T> result = new ArrayList<T>();

 for (T t : input) {

 if (filter.filter(t)) {

 result.add(t);

 }

 }

 return result;

 }

}

Now that we have a generic filtering API in place, we can use this functionality to filter a list. The code below will declare an anonymous class that implements Filter, and provide an implementation that returns true for odd numbers:

package localclasses;

import java.util.List;

import java.util.Arrays;

public class Main {

 public static void main(String[] args) {

 List<Integer> numbers = Arrays.asList(1,5,4,2,7,9,6,4,2,6,5,8);

 System.out.println(

Collections2.filter(numbers, new Filter<Integer>() {

  @Override

  public boolean filter(Integer t) {

  return t%2 == 1;

  }                

  })

);

 }

}

That wasn’t so hard was it?

By way of comparison, the same code in JavaScript looks like this:

[1,5,4,2,7,9,6,4,2,6,5,8]

.filter(function(v) {return v%2 == 1;})

The JavaScript implementation passes an anonymous function to the filter method natively supported by arrays.

The key to comparing these two approaches is comparing the Java implementation of an anonymous class:

Collections2.filter(numbers, new Filter<Integer>() {

 @Override

 public boolean filter(Integer t) {

 return t%2 == 1;

 }                

})

to the JavaScript implementation of an anonymous function:

function(v) {return v%2 == 1;}

When you compare the two you can get a feeling why people have accused Java of feeling overly verbose. Admittedly, the JavaScript version does not bring the benefits of type safety, but otherwise the two examples are functionally equivalent. JavaScript is not an isolated example either; many languages now support equally concise syntaxes.

The key feature in JavaScript that allows this line of code to work is that functions can be assigned to variables and passed to other functions as parameters. To be specific: functions are first-class citizens in the language.

Up until the release of Java 8, all Java methods had to be defined inside a class – therefore methods were not first-class citizens in the language. As a result, methods could not be passed to other methods as parameters or assigned to variables.

A lambda expression is essentially an anonymous method that lives outside the scope of a class. As we will see, this is an illusion to some degree, lambda expressions are still objects, and they do have types, but the syntax for creating them removes the overhead of defining a class.

The basic format of a lambda expression is as follows:

(String s) -> { System.out.println(s); };

The first part of the expression (String s) denotes the arguments that will be passed to the lambda expression when it is invoked – in this case it will be passed a single String parameter. If no parameters are required by the lambda expression this can simply be defined as (). As we will see, this structure can be simplified significantly in some situations, and the types derived by the compiler based on context.

The right hand side of the expression { System.out.println(s); }; contains the code block that will be executed when the lambda expression is invoked – naturally this can access the parameters passed to the expression, and can use any other Java language features required – it is just a regular code block. This block also has access to variables in scope when the lambda expression was constructed, although with certain caveats (as we will see below).

If the code-block consists of a single statement the {} brackets can be omitted, and the return type of the statement implicitly becomes the return type of the lambda expression. Where {} brackets are used, the lambda expression can use the return keyword to return a value, otherwise, as in this case, it returns void.

The two parts of the expression are glued together by the “->” construct.

There will be plenty of examples of this construct below, so don’t worry about understanding the details of lambda expressions too much at this point.

## Functional Interfaces

As mentioned above, many languages supporting lambda expressions make functions first-class citizens in the language. Java does not go that far - lambda expressions are still objects. In addition, even with the addition of lambda expressions, Java remains a statically typed language; therefore it needs to know the type of any parameter (including lambda expressions) passed to a method at compile time. This leads to the obvious question: what type are lambda expressions?

The answer to this lies in a new Java 8 feature called “functional interfaces”. You have probably come across interfaces with no methods (e.g. Serializable, Cloneable). These are known as marker or tagging interfaces, since they are simply used to denote something about a class without requiring it to implement anything.

Java now supports a second special class of interface that contain a single method: these can be designated as ”functional interfaces”. Many existing Java interfaces have been designated as functional interfaces including Comparable, Runnable and ActionListener. These interfaces are also called Single Abstract Method interfaces (SAM Interfaces) – particularly in the Scala world.

Prior to Java 8 there was nothing special about SAM interfaces: in Java 8 they can now act as the type for lambda expressions when tagged with the annotation @FunctionalInterface, for example:

@FunctionalInterface

public interface Example {

 void doSomething(Object obj);

}

One obvious use for lambda expressions is for callbacks. Callbacks encapsulate a block of code that should be executed by another block of code when a specified event occurs. The event may be the user pressing a button on the screen, or the result being received for a long running transaction.

The example below creates a functional interface to represent the printing of an object. Instances of this interface will then be passed as a callback to other methods, allowing them to print the results of an operation in the manner required by the initial invoker:

package printing;

@FunctionalInterface

public interface Printer {

 void print(Object obj);

}

Adding the @FunctionalInterface annotation ensures that the compiler will check that the interface meets the requirements for being a Functional Interface: if the interface contained anything other than one method definition the code would not compile.

Once a Functional Interface has been defined we can declare a lambda expressions of that type:

Printer printer = (Object o) -> { System.out.println(">>>" + o); };

This line of code will not execute the lambda expression: it is simply assigning it to a variable so that it can be used at a later point in the code.

If you think about the line of code above, it is actually very unusual from a Java point of view. The compiler is determining the type of an object via the type it is assigned to. This is the other way round from how Java normally works: typically an expression has a type, and the compiler determines whether that is compatible with the type it is being assigned to.

If you wanted to, you could then invoke this as follows:

printer.print("Hello World");

Generally, however we want to pass the lambda expression to another method. The following is a contrived example, but shows the basic technique:

package lambda;

import printing.Printer;

public class Adder {

 public static void main(String[] args) {

 int num1 = 10;

 int num2 = 20;

 Printer printer = (Object o) -> {

System.out.printf("The result of %d and %d is %d\n"

, num1, num2, o);

 };

 add(num1, num2, printer);

 }

 public static void add(int num1, int num2, Printer printer) {

 int result = num1 + num2;

 printer.print(result);

 }

}

This prints the following to standard output:

The result of 10 and 20 is 30

This is a contrived example because there is no reason for the add method not to return the result of the addition for the main method to print itself, but it gets us started with lambda expressions.

Notice that this lambda expression uses local variables from the main method, even though it is eventually executed in the add method: we will return to this subject shortly when we investigate the scope that lambda expressions operate in.

As it happens, most of the time we do not need to define our own functional interfaces because Java provides a set for us. We can see this by moving to a realistic example.

A common use-case for lambda expressions is to have a method pass each element of a list to a lambda expression (just like our filter example at the start of the chapter). Java 8 provides a new method on List called forEach that accepts a lambda expression and implicitly passes each element in the list to it: the lambda expression it accepts must conform to the Consumer functional interface (java.util.function.Consumer). This defines the following method:

void accept([T](http://download.java.net/jdk8/docs/api/java/util/function/Consumer.html "type parameter in Consumer") t)

The following shows a basic example:

package lambda;

import java.util.Arrays;

import java.util.List;

import java.util.function.Consumer;

public class Main {

 public static void main(String[] args) {

 Consumer c = (Object o) -> { System.out.println(">>>" + o); };

 List l = Arrays.asList("Hello", "World", "Print", "My", "List");

 l.forEach(c);

 }

}

This will produce the following output:

>>>Hello

>>>World

>>>Print

>>>My

>>>List

This is the first example of many in this book that uses “implicit” rather than “explicit” iteration. Methods such as forEach remove the need for the programmer to describe the iteration process to the compiler – they implicitly perform it. This may sound like a minor convenience, but it will turn out to have powerful implications later in the book.

We can of course combine the declaration and use of the lambda expression into a single step:

package lambda;

import java.util.Arrays;

import java.util.List;

public class Main {

 public static void main(String[] args) {

 List l = Arrays.asList("Hello", "World", "Print", "My", "List");

 l.forEach((Object o) -> { System.out.println(">>>" + o); });

 }

}

Notice that we don’t even need to import the Consumer interface now – the compiler knows to check that the lambda expression conforms to the Consumer interface, since that is the interface accepted by the forEach method.

We can even take this one step further by removing the type definition from the lambda expression’s parameter, and remove the {} brackets from the lambda expression’s code block:

package lambda;

import java.util.Arrays;

import java.util.List;

public class Main {

 public static void main(String[] args) {

 List<String> l = Arrays.asList("Hello", "World",

 "Print", "My", "List");

 l.forEach(str -> System.out.println(">>>" + str));

 }

}

We have used generics to declare that the list contains elements of type String; therefore the compiler knows that every element in the array is a String. This also means that the compiler can safely assume that every element passed to the lambda expression will be a String. This in turn allows us to omit the type of the str parameter, and simply use the expression:

str -> System.out.println(">>>" + str)

We can now turn our attention back to the filtering example outlined earlier in this chapter. Java 8 refers to a filter as a “predicate” and provides a functional interface called Predicate. This defines the following method:

boolean test([T](http://download.java.net/jdk8/docs/api/java/util/function/Predicate.html "type parameter in Predicate") t)

The fundamental aspect of a predicate is that it accepts an element and returns true or false. The List interface also supports a new method called removeIf. This method passes every element in the list to the predicate, and removes it if the predicate evaluates to true:

package lambda;

import java.util.Arrays;

import java.util.LinkedList;

import java.util.List;

public class Main2 {

 public static void main(String[] args) {

 List<Integer> l = new LinkedList

 (Arrays.asList(4,5,88,76,55,23,7,20,45));

       l.removeIf(i -> i%2 == 0);

 System.out.println(l);

 }

}

The expression “i -> i%2 == 0” conforms to the Predicate interface since it accepts a single parameter and returns a Boolean result – as mentioned above, lambda expressions implicitly return a type if they consist of a single statement without {} brackets.

This could alternatively have been written as a code block:

l.removeIf(i -> {return i%2 == 0;});

I far prefer the first form for readability, and this is the form that is most commonly used.

I should probably mention at this point that the removeIf method is a very poor example of functional programming due to the fact that it mutates (or changes) the original list. Functional programming emphasizes immutability, and therefore the preferred approach would be to create a new list of odd numbers and leave the original list untouched. As we will see in the next chapter, it is possible to achieve this relatively simply with Java 8 using the Streams API.

In case you were wondering, the fact that this method mutates the List meant I could not simply use:

Arrays.asList(4,5,88,76,55,23,7,20,45)

Since this method returns a fixed-length List mapped to the array, and therefore it is not possible to remove elements.

## Auto-generated Interfaces

One issue with the lambda expressions we have looked at so far is that they do not lead to very good code reuse. The examples above have all created lambda expressions on the fly and passed them as parameters to other methods. If two different classes needed lambda expressions performing the same task, they would each need to construct their own lambda expression (thereby duplicating the code).

The lambda expression API in Java 8 provides a mechanism to use any method on any object (or static method on a class) as a lambda expression (subject to its access modifiers), as long as it conforms to the required functional interface. This feature is called auto-generated interfaces, and is facilitated by a new operator called the “double colon”.

Let’s take the very simplest example we can. Suppose we want to pass each element in a list to the System.out.println method. The println method meets the requirements of the Consumer functional interface (it accepts a single parameter and returns void); therefore it can be used as an instance of Consumer:

package lambda;

import java.util.Arrays;

import java.util.List;

public class Main3 {

 public static void main(String[] args) {

 List<String> l = Arrays.asList("Hello", "World",

"Print", "My", "List");

 l.forEach(System.out::println);

 }

}

The key here is the statement “System.out::println”. Essentially this is saying that there is a method called “println” on the object represented by the variable “out”, and this should be used as the lambda expression accepted by the forEach method. Since forEach accepts a Consumer, the println method is implicitly converted to be an object of type Consumer as part of the process.

If we go back to the example of removing even number elements from the list: suppose we already had the following utility class:

package lambda;

public class Detector {

 public boolean isEven(int i) {

 return i%2 == 0;

 }

 public boolean isOdd(int i) {

 return !isEven(i);

 }

}

This is a simple utility that detects odd and even numbers: it has nothing to do with lambda expressions, and could have pre-dated Java 8. We could rewrite the filtering example as follows:

package lambda;

import java.util.Arrays;

import java.util.LinkedList;

import java.util.List;

public class Main4 {

 public static void main(String[] args) {

 Detector d = new Detector();

 List<Integer> l = new LinkedList

(Arrays.asList(4,5,88,76,55,23,7,20,45));

 l.removeIf(d::isEven);

 System.out.println(l);

 }

}

Or, if we made isEven a static method, we could execute the following:

l.removeIf(Detector::isEven);

This is a very useful technique, since it means existing code can be re-purposed to adapt to an interface it does not explicitly implement. This means, for instance, any zero arguments method can be repurposed to implement the Runnable interface and executed by a Thread.

Sorting lists is a very common operation, and is supported by the Comparator and Comparable interfaces. I have always been annoyed by the fact that the sort method was a static helper on the Collections class, rather than a method on the List class. This was presumably because List was an Interface rather than a class, and therefore the sort method would have needed to be implemented on each implementation of List.

As we will see later, this is no longer a constraint for Java, and therefore Java has rectified this situation in Java 8 via a sort method on List (despite the fact it is an interface), and made Comparator a functional interface in the process.

To demonstrate this we will create a very simple Person class:

package lambda;

public class Person {

 String firstName,lastName;

 public Person(String firstName, String lastName) {

 this.firstName = firstName;

 this.lastName = lastName;

  }

 public String getFirstName() {

 return firstName;

 }

 public String getLastName() {

 return lastName;

 }

 @Override

 public String toString() {

 return firstName + " " + lastName;

 }

}

We can now create a list of Person instances, and sort it based on firstName as follows:

package lambda;

import java.util.Arrays;

import java.util.List;

public class Main5 {

 public static void main(String[] args) {

 List<Person> l = Arrays.asList(

    new Person("Albert", "Smith"),

 new Person("Jim", "James"),

 new Person("John", "Brown"),

 new Person("William", "Hughes"),

 new Person("Simon", "Fleming")

 );

 l.sort((p1, p2) -> p1.getFirstName().compareTo(p2.getFirstName()));

 System.out.println(l);

 }

}

The statement:

(p1, p2) -> p1.getFirstName().compareTo(p2.getFirstName())

is implicitly constructed into an Object of type Comparator as part of this process.

Notice here that the sort operation is mutating: it changes the original list rather than returning a new list with the elements sorted.

I would take a lot of convincing that the equivalent code with anonymous classes (while functionally equivalent) is as readable:

l.sort(new Comparator<Person>() {

 @Override

 public int compare(Person p1, Person p2) {

 return p1.getFirstName().compareTo(p2.getFirstName());

 }         

});

## Scope

As we have seen above, lambda expressions can use variables that were in scope when they were created. There is a caveat however – they can use those variables as long as they do not change their values after they are declared.

As an example, consider the following functional interface:

package lambda;

@FunctionalInterface

public interface NumberAdder {

 int add(int x);

}

This has a method called add that accepts an integer, and returns an integer.

We will now create a method that returns a NumberAdder as follows:

public static NumberAdder getNumberAdder() {

 int startingNumber = 10;

 return x -> x + startingNumber;

}

This method declares a local variable called startingNumber, and then returns an instance of NumberAdder that will (when invoked) add startingNumber to the number that is passed to the lambda expression.

Under normal circumstances the startingNumber variable would be implicitly destroyed when the method completes (remember, local variable references exist on the stack, and are popped off the stack when the method completes). In the case of lambda expressions however, the variable survives when the method completes. Here is the complete class including the invoking method:

package lambda;

public class Main6 {

 public static void main(String[] args) {

 NumberAdder na = getNumberAdder();

 System.out.print(na.add(20));

 }

 public static NumberAdder getNumberAdder() {

 int startingNumber = 10;

 return x -> x + startingNumber;

 }

}

When this runs it will print out 30\. Lambda expressions that use variables in this manner are said to be “capturing lambdas”, since they capture copies of the variables that were in scope when they were constructed.

In order for this little bit of magic to work, the variable startingNumber must be final or “effectively final”. Even the following code is invalid and won’t compile:

public static NumberAdder getNumberAdder() {

 int startingNumber = 10;

 startingNumber++;

 return x -> x + startingNumber;

 }

The term “effectively final” is new. Essentially it means that the variable must behave as though it was final, even though it doesn’t need to be marked as final. Basically, if the variable would not be valid with the final modifier added, it is not valid for use by a lambda expression.

This constraint is controversial and was added to reduce concurrency issues that could arise from mutating variables. Up until Java 8 you could never have threading issues with local variables: simply put it was impossible for two threads to be sharing the same instance of a local variable since they are created inside a method, and two threads invoking the same method would receive their own independent copies of the variables.

If lambda expressions could change a local variable, and two methods invoked the lambda expression from two separate threads at the same time, a whole new set of concurrency issues would have been introduced to the language.

It is of course possible to work around this constraint (just as it is possible to work around the constraints on final variables) by encapsulating the integer as a field inside an object. It would then be possible to change the value of this field even after the lambda expression was created. This could be achieved by creating the following class:

package lambda;

public class IntegerHolder {

 public int number = 10;

}

And changing the main class as follows:

package lambda;

public class Main7 {

 public static void main(String[] args) {

 NumberAdder na = getNumberAdder();

 System.out.print(na.add(20));

 }

 public static NumberAdder getNumberAdder() {

 IntegerHolder ih = new IntegerHolder();

 ih.number = 10;

 NumberAdder na = x -> x + ih.number;

 ih.number = 20;

 return na;

 }

}

In this case, the ih variable is effectively final, since we do not change the object referenced after the variable is initialized. We do however change the number held by the object after creating the lambda expression.

In this case the result of the operation is 40, since when the lambda expression is invoked, the value of the number field had been changed to 20.

This approach does naturally open the code up to the concurrency issues that the specification was trying to avoid through the use of final variables, and therefore should not be seen as a feature.

## Conclusion

As you have seen, lambda expressions provide a mechanism for constructing anonymous methods and passing them as parameters to other methods.

The debate around lambda expressions in the Java community has seemed endless. Not only was their release delayed from Java 7 to Java 8, there has been a huge amount of debate and criticism of them.

Even now that they have been included there is an argument in some circles that lambda expressions are “syntactic sugar” – they are simply an alternative way of implementing an interface, and therefore are no different from pre-Java 8 anonymous and local classes.

You can make an argument about any programming language or programming language construct that it is just syntactic sugar on top of some other construct (such as assembler, and ultimately machine code), since there is nothing that can be achieved in a high level language such as Java that could not be achieved in assembler or machine code. The point is, languages such as Java provide a more convenient mechanism for a human to describe a set of tasks to a computer. In the same way, lambda expressions will make it a lot easier for a lot of Java programmers to describe tasks to the Java compiler.

Although lambda expressions do not allow you to do anything you could not have done without them, they have the ability to change the way you think about solving problems in Java. This theme will be carried through to the next chapter on the Streams API: since this is where lambda expressions shine brightest.

# Streams API

Java 8 introduces a new API called the Streams API as part of the lambda expressions JSR. These should not be confused with input and output streams; they are a mechanism for processing a sequence of elements (such as the elements in a Collection). Java 8 formally defines streams as “a sequence of elements supporting sequential and parallel aggregate operations.”

As we will see later in the chapter, the Streams API is part of a push to simplify the way parallel algorithms can be implemented in Java by allowing programmers to request parallel processing rather than implementing it. Streams are a lot more than that however, they provide an alternative to iteration, and provide support for a variety of operations, all of which can utilize lambda expressions.

We will begin with some very basic Streams examples, returning to my favorite of excluding even numbers from a List. This can be accomplished as follows:

package streams;

import java.util.Arrays;

import java.util.List;

public class EvenOnly {

 public static void main(String[] args) {

 List<Integer> l = Arrays.asList(5,4,88,76,55,23,7,20,45);

    l.stream().filter(p -> p%2==1)

.forEach(i -> System.out.print(i+" "));

 }

}

After creating the list we first access its stream with the stream() method. This returns an object of type java.util.stream.Stream<Integer>. We will look at what streams are in more detail soon, but for now just think of them as a way of conveying elements from a source of data (i.e. the List) to a function (i.e. filter).

This code “internally iterates” over every element in the list (as seen in the previous chapter with forEach), and passes each element in turn to the filter method. This is opposed to “external iteration” with for loops and iterators, since the programmer does not need to declare the fact they wish to process each element in the loop, and they do not need to control the iteration.

External iteration may not seem like a huge inconvenience that needs to be alleviated – especially since the introduction of the Collection-based for loops. Internal iteration can bring unseen benefits, however, since it may implement different strategies to iterate different collections, therefore allowing behavior to be added implicitly (such as parallel processing).

The filter method is referred to as an intermediate operation. As each element is processed, those that pass the filter are then passed to the forEach method, which is a terminal operation.

The type returned by the filter() method is itself a Stream, and therefore it is possible to chain a whole set of intermediate operations together into a “pipeline”. Pipelines are facilitated by the fact that the output of one operation becomes the input of another operation.

Pipelines are widely used in computing: for instance the Unix/Linux command line supports pipelines where the output of one program is passed as the input to another program via the “|” operator. For instance, this finds any processes running for the user that contain “java” in their name:

ps | grep 'java'

The convention in Unix that allows this is that programs produce ASCII text to standard output, and other programs read ASCII text from standard input. The pipe operation therefore pipes the standard output of one program to the standard input of another.

As we will see throughout this chapter, pipelines provide a mechanism for describing a complex set of functionality in easy to understand chunks.

Terminal operators (as their name suggests) represent the end of a pipeline, and they are responsible for terminating the stream in some manner. forEach is not the most obvious example of a terminal operation, but it provides a manner of accessing all the elements after they have been processed by the pipeline, and performing some operation on them (printing them out in this case). You will notice that the forEach method returns void, therefore the pipeline cannot continue after this method has been invoked.

Unlike the removeIf method seen earlier, this pipeline does not alter the original Collection in any way: it simply provides a mechanism for processing its elements.

With the example above, the first element in the List (5) is passed to the lambda expression of the filter method, and is evaluated to true (it is odd). As a result, this element is passed to the lambda expression of the forEach method, which causes the number to be printed.

Once the element has been all the way through the pipeline, the next number (4) is processed. Since the filter lambda expression will return false for this number it will never be passed to the forEach lambda expression, and so on.

Even this is not strictly speaking a true representation of the processing: intermediate operations are lazy. The intermediate operations are not executed until the terminal operation is invoked – so it is the execution of the forEach method with the first number (5) that causes the filter method to be invoked.

This approach means that the entire pipeline can be processed in a single iteration of the collection, and can result in dramatic performance improvement for large sets of data. It also means that the stream does not need to hold all the elements in the list as it performs its processing.

This last point is important. An alternative implementation of Streams would have been to invoke the filter operation on all elements and capture these in a Collection – once these had been captured they could be passed to the forEach method. I think it is fairly obvious that this implementation would not be as efficient either in terms of memory utilization or processor utilization.

In order to see this in action, we will re-write the main method as follows:

public static void main(String[] args) {

 List<Integer> l = Arrays.asList(5,4,88,76,55,23,7,20,45);

 Stream<Integer> s = l.stream().filter(p -> {

 System.out.println("Filter called on "+ p);

 return p%2==1;

 });

 System.out.println( "The pipeline is created - calling terminal operation");

 s.forEach(i -> System.out.println(">>>" + i));

}

This produces the following result:

The pipeline is created - calling terminal operation

Filter called on 5

>>>5

Filter called on 4

Filter called on 88

Filter called on 76

Filter called on 55

>>>55

Filter called on 23

>>>23

Filter called on 7

>>>7

Filter called on 20

Filter called on 45

>>>45

Notice the first line that is output: although this was printed after the filter method appears to have been invoked, it is actually the first print statement to be displayed, proving this line was executed first. This shows that even with our code structured across multiple statements, the Collection is still processed with a single pass by the Stream.

There is another major benefit with the lazy invocation approach. Suppose we just wanted to find the first odd number in this list. This can be achieved with an alternative terminal operation called findFirst:

public static void main(String[] args) {

 List<Integer> l = Arrays.asList(5,4,88,76,55,23,7,20,45);

 Stream<Integer> s = l.stream().filter(p -> {

 System.out.println("Filter called on "+ p);

 return p%2==1;

 });

 Optional<Integer> result = s.findFirst();

 System.out.println(result.get());

}

This example prints the following result:

Filter called on 5

5

Since the first element in the list was odd, this was the only element that needed to be processed.

There is one other interesting aspect to this example. Rather than returning an Integer, the findFirst method returned an Optional<Integer>. You will find references to the Optional class throughout the Streams API: it provides a container for a value that may be null. This class supports a method called isPresent to determine whether the container holds a non-null value.

The Optional class also supports methods such as map and filter that allow the value to be modified via lambda expressions if required. There is also nothing to stop you returning Option instances from your own code, and it may prove a useful mechanism for extending the value of your APIs.

There are a couple more points to make about Streams before continuing. Firstly, once a stream has processed its elements it cannot be reused. For instance, in the example above we could not have invoked an alternative terminal operation on the Stream returned by filter after the forEach operation had been executed. Technically streams can be closed, but there is no reason to explicitly close them.

 Secondly, Streams must be non-interfering: they cannot change the source of the Stream (the list in the example above).

We will now turn to a slightly more complicated example, and demonstrate how a pipeline can include multiple intermediate steps. Suppose we want to do the following:

• Filter the even numbers out of the list

• Multiply each remaining number by itself

• Sum the numbers together

In this case, the first two steps will be the intermediate operations, while the sum operation will be the terminal operation. This can be achieved as follows:

double result = l.stream()

.filter(p -> p%2==1)

.mapToInt(p -> p * p)

.sum()

The filter method above should look familiar, and since it returns a Stream<Integer> we can obviously execute other intermediate operations on the result.

The next intermediate operation that is executed is mapToInt. This is slightly different from the filter operation: it provides a way of transforming data. The lambda expression passed to mapToInt accepts any type of object as input, and returns an integer as a result. In this case the input parameter is also a integer, but that is not required: we could have passed a Person object as the parameter, and returned the salary field (if that was a integer).

The lambda expression passed to mapToInt is simply multiplying the input parameter by itself and implicitly returning the result.

The other interesting thing about mapToInt is that instead of returning an object of type Stream<Integer>, it actually returns an instance of IntegerStream. The difference may sound small, but IntegerStream provides a set of specialized terminal operations designed to work with integer values, including min, max, average, and the method we are using here: sum.

The Streams API also supports DoubleStreams (via mapToDouble) and LongStreams (via mapToLong). These have the same set of aggregate operations seen on IntegerStream.

Streams also support a general-purpose map operation for transforming objects of any type to any other type, but this method simply returns a Stream<T> where T is the return type of the map operation.

The sum method is a type of terminal operation known as a reducing operation: it takes a set of values and reduces them to an aggregate value. We could have implemented the reduce method ourselves if we chose:

l.stream()

.filter(p -> p%2==1)

.mapToInt(p -> p * p)

.reduce((a, b) -> a + b)

The reduce algorithm starts by passing the first two elements in the list to the lambda expression provided. The result of this operation is then passed to the lambda expression along with the third element, and so on until the elements have all been processed. The following is a print out of the values passed to the reduce lambda expression:

a = 25, b = 3025

a = 3050, b = 529

a = 3579, b = 49

a = 3628, b = 2025

(There are 5 odd numbers, so the expression is invoked 4 times).

The reduce method returns an instance of OptionalInt, since the filter method could have potentially removed all elements from the Stream.

The reduce operation accepts a lambda expression conforming to the BinaryOperator functional interface. This interface has a method that accepts two parameters and returns a single parameter of the same type:

[R](http://download.java.net/jdk8/docs/api/java/util/function/BiFunction.html "type parameter in BiFunction") apply([T](http://download.java.net/jdk8/docs/api/java/util/function/BiFunction.html "type parameter in BiFunction") t, [U](http://download.java.net/jdk8/docs/api/java/util/function/BiFunction.html "type parameter in BiFunction") u)

We could therefore have reused one of the new static helper methods added to Integer (and the other number wrapper types) in Java 8:

public static int sum(int a, int b)

As follows:

l.stream()

.filter(p -> p%2==1)

.mapToInt(p -> p * p)

.reduce(Integer::sum)

Notice that the sum method is static, therefore we don’t need an instance of Integer to invoke the sum method.

The reduce operation can also accept an optional first parameter representing the initial value of the aggregation:

l.stream()

.filter(p -> p%2==1)

.mapToInt(p -> p * p)

.reduce(100, (a, b) -> a + b)

This example will return 100 more than the previous example.

If omitted, this uses the default value for the data-type returned, e.g. 0 for numbers.

## Collecting

Another useful terminal operation is collecting. Collecting provides a mechanism for accumulating or summarizing elements based on a set of criteria.

As an example, consider a list of the Person class from earlier in the book. We may want to group all the Person instances together where the firstName is equal – this could be achieved as follows:

package streams;

import java.util.Arrays;

import java.util.List;

import java.util.Map;

import java.util.stream.Collectors;

public class Collecting {

 public static void main(String[] args) {

 List<Person> people = Arrays.asList(

 new Person("Albert", "Smith"),

 new Person("John", "James"),

 new Person("John", "Brown"),

 new Person("William", "Hughes"),

 new Person("William", "Fleming")

 );

 Map<String, List<Person>> groupedMap = people.stream()

 .collect(Collectors.groupingBy(Person::getFirstName));

 System.out.println(groupedMap.get("William"));

 }

}

This groupingBy operation returns a Map where the keys are the distinct values for first name (William, John, Albert), and the values are Lists of the Person classes matching that key.

Since the final line accesses the List held against the William key, this will print out:

[William Hughes, William Fleming]

The collect method accepts a Collector. These can be generated via a set of static helpers on the Collectors class - in this case we are using the groupingBy Collector, and specifying the method that should be used for comparison. The appropriate Collector instance will then be generated for us.

Once elements have been grouped it is common to run an aggregation operation on each group (for instance, count how many elements are in each group). The groupingBy methods therefore accept a second parameter for performing aggregate operations. As an example we will process all the time zones available in Java (we will see these again later in the book when we look at the new Date and Time API): these can be obtained as an array from TimeZone.getAvailableIDs(). These exist in the form:

Africa/Asmara

Europe/London

Where the optional first portion (Europe, Africa) represents a grouping mechanism, and the portion after the forward slash represents a specific value.

We will write a program that performs the following:

• Filters out any zones that don’t have a forward slash in them

• Groups the zones by their group (e.g. Europe, Africa)

• Counts how many zones are in each group

This can be performed in a single line as follows:

package streams;

import java.util.Arrays;

import java.util.Map;

import java.util.TimeZone;

import java.util.stream.Collectors;

public class Collecting5 {

 public static void main(String[] args) {

 Map<String, Long> result =

 Arrays.asList(TimeZone.getAvailableIDs())

 .stream()

 .filter(s -> s.indexOf("/") > 0)

 .collect(Collectors.groupingBy((String s) -> s.substring(0, s.indexOf("/")),

 Collectors.counting()));

 System.out.println(result);

 }

}

Notice the use of Collectors.counting() as the second parameter to the groupingBy method. This itself is a Collector, and processes the result of the group by. The counting method (unlike the groupingBy method) does not need any other information in order to generate a Collector – since it operates on a data-structure in the format returned by the groupingBy method (a Map with Lists as its values).

This outputs the following:

{Europe=59, Africa=54, SystemV=13, Canada=9, Pacific=42, Etc=35, Asia=91, America=164, Brazil=4, Mexico=3, Indian=11, Antarctica=11, Chile=2, Australia=23, Arctic=1, Atlantic=12, US=13}

Partitioning is another form of Collector that is similar to groupingBy. As discussed earlier, filter operations return true or false for all elements in the stream. Partitioning provides a mechanism to collect all the values that are true into one List, and all the values that are false into another List. In this example we will create two lists: one for the time zones that have a “/” in their name (e.g. America/Cancun), and one for the zones that don’t (e.g. Greenwich)

package streams;

import java.util.Arrays;

import java.util.List;

import java.util.Map;

import java.util.TimeZone;

import java.util.stream.Collectors;

public class Collecting4 {

 public static void main(String[] args) {

 List<String> zones = Arrays.asList(TimeZone.getAvailableIDs());

 Map<Boolean, List<String>> zonesCompare =

 zones.stream()

 .collect(Collectors.partitioningBy(s -> s.indexOf("/") > 0));

 System.out.println(zonesCompare);

 }

}

Another good example of Collecting is adding a comma between every word in a List. I have previously used Apache Common's StringUtils.join method for this, since it is tedious to code yourself. The trick to joining is that the comma (or other delimiter) should not occur after the last element, therefore it is hard to achieve with simple iteration.

Joining can easily be achieved with Streams as follows:

package streams;

import java.util.Arrays;

import java.util.List;

import java.util.stream.Collectors;

public class Collecting {

 public static void main(String[] args) {

 List<String> strings = Arrays.asList("This", "is", "a", "list");

 String s = strings.stream()

 .collect(Collectors.joining(", "));

 System.out.println(s);

 }

}

This takes advantage of the join Collector, which accepts the parameter that should be placed between each element. This prints out:

This, is, a, list

Notice that this does not contain a comma after the last element.

Collectors can also be used for collecting the results of a pipeline into a new Collection such as a List or a Set. This can be achieved as follows:

package streams;

import java.util.Arrays;

import java.util.List;

import java.util.Map;

import java.util.stream.Collectors;

public class Collecting {

 public static void main(String[] args) {

 List<Person> people = Arrays.asList(

  new Person("Albert", "Smith"),

 new Person("John", "James"),

 new Person("John", "Brown"),

 new Person("William", "Hughes"),

 new Person("William", "Fleming")

 );

 List<Person> filteredList = people.stream()

 .filter(p -> p.getFirstName().equals("William"))

 .collect(Collectors.toList());

 System.out.println(filteredList);

 }

}

This filters out all the Person instances where the first name is “William”, and adds the result to a new list.

## Other operators

The Streams API is a large API, and will take some time to learn in its entirety. The following are potentially the most useful intermediate operations provided by the Streams API that have not been introduced up until now:

**• distinct**: removes any duplicate elements (based on the equals implementation) from the stream

**• limit**: limit the elements in the stream to a specific number. This could be useful for processing search results if only a maximum of 100 results were to be shown. It can also result in performance improvements since it allows you to reduce the elements in the stream mid-way through the pipeline.

**• map**: this is a generic version of the mapToInt method seen above. It takes each element in turn and returns a value (potentially of a different type) based on some transformation.

**• sorted**: this provides a mechanism for sorting the elements, either based on natural order or a Comparator. This can be called anywhere in the pipeline prior to the terminal operation, so it is useful when a map operation may have resulted in an unordered stream.

The following are the most useful terminal operators available on Stream not discussed in the sections above (as discussed above, specialized streams such as DoubleStream contain additional terminal operators):

**• allMatch**: this accepts a Predicate and returns true if all elements return true from the predicate

**• anyMatch**: this accepts a Predicate and returns true if any elements return true from the predicate

**• noneMatch**: this accepts a Predicate and returns true if none of the elements return true from the predicate

**• count**: counts the number of elements in the stream

## Creating Streams

So far we have focused on how Streams can be created from Collections. There are in fact several ways to create Streams; since they are just a stream of elements, they can be produced by a variety of sources.

The Streams API contains a concept called a range. A range allows a Stream to be constructed as a sequence of numbers, for instance:

IntStream.range(0, 10).forEach(n -> System.out.println(n));

This generates an IntStream with the numbers 0 through 9\. The alternative rangeClosed method can be used if you want the range to be inclusive of the final number (e.g. 0 to 10).

Once the Stream has been created it can be processed just like any other Stream, therefore ranges provide a Streams based alternative to for-loops.

An alternative mechanism for creating Streams is via builders. The following is an example of a builder that adds three Strings to a Stream, and then invokes the forEach terminal operation:

Stream.builder().add("Hello").add("World").add("!").build()

.forEach(s -> System.out.print(s));

The builder is obtained via a static method on Stream. Once all elements have been added the build() method is invoked to return a Stream of the elements.

Naturally IntStream, LongStream and DoubleStream support corresponding builders for generating Streams of integers, longs and doubles respectively.

Another way to construct Streams is to concatenate two Streams together:

Stream s1 = Stream.builder().add( "Hello").add("World").add("!").build();

Stream s2 = Stream.builder().add( "Another").add("Stream").build();      

Stream.concat(s1, s2).forEach(s -> System.out.print(s));

The stream created in the final line above will process 5 elements.

Streams can also be generated via static helpers on the Random class. Random.ints(), Random.longs() and Random.doubles() provide mechanisms for returning an unlimited stream of pseudorandom integers , longs and doubles respectively (although the quantity of values can be bound by an optional parameter). It is also possible to define a range for the numbers; for instance we could request a Stream of 100 random ints between 0 and 100,000 as follows:

Random.ints(100, 0, 100000)

Naturally these return Streams appropriate for the type of number, so the example above returns an IntStream.

Possibly the most useful source of Streams outside of Collections however is Streams created from Files.

Java 7 introduced a Files class with a set of static helpers. This has been enhanced in Java 8 to include methods that return Streams. In order to see this in action, start by creating a text file on your file system, and add a few lines to it.

The following example shows how that file can be read as a Stream, and processed with all the operations we have seen above:

package streams;

import java.io.IOException;

import java.nio.file.*;

import java.util.logging.*;

public class FileReading {

 public static void main(String[] args) {

 Path path = Paths.get("/tmp/test.txt");

 try {

 Files.lines(path).distinct()

.forEach(s -> System.out.println(s));

 } catch (IOException ex) {

 Logger.getLogger(FileReading.class.getName())

.log(Level.SEVERE, "IO Error", ex);

 }

 }

}

This program looks for a file called /tmp/test.txt and converts it into a Stream via the Files.lines() method (this assumes a default character encoding of UTF-8, but it can be overridden with an optional parameter). The intermediary operation distinct is then used to remove duplicate lines, and the results are printed out with the terminal forEach operator.

Notice that this never needs to read the whole file into memory: it can simply Stream one line at a time through the pipeline, and then move onto the next line.

Finally, it is possible to generate a Stream from an array using a static helper on Arrays. The following is a very simple example that prints out the sum of the numbers in an array. Due to the fact that the array is of type int, the Stream returned is an IntegerStream, and therefore the sum aggregate operation can be used:

package streams;

import java.util.Arrays;

public class ArraysStream {

 public static void main(String[] args) {

 int[] intArray = {4,2,5,7,66,4,3};

 int result = Arrays.stream(intArray).sum();

 System.out.print(result);

 }

}

## Parallel Programming

I mentioned at the start of this chapter that the Streams API was intended to revolutionize the way Java programmers thought about, and wrote code using parallel processing. Up until this point we have not seen any evidence of this: the Streams examples above are not any different from iterators from a threading point of view.

Before looking at parallelism it is best to start with a recap of the reasons parallel processing is useful. Due to the fact that all modern computers (and even smart phones) contain multiple cores, any program that is not performing parallel computing (processing on multiple Threads) is by definition not exploiting the full potential of the hardware for CPU bound operations.

On the whole, server-side Java frameworks (such as EJB or Servlets) do allow programmers to perform parallel computing with minimal effort, since the application server manages threads. The programmer does not need to ask the application server to run concurrent Servlet requests in multiple threads (and therefore potentially on multiple cores), it happens automatically. Outside the application server, however, the programmer is still responsible for instructing the computer how to parallelize algorithms across multiple threads.

### MapReduce

Before discussing the implementation the Streams API uses for parallelism, it is worth taking a step back and looking at an algorithm called MapReduce that heavily influenced this coding style. The MapReduce algorithm was popularized by Google researchers via a paper written in 2004, ([http://research.google.com/archive/mapreduce.html](http://research.google.com/archive/mapreduce.html)) but the operations of map and reduce have been around far longer. Google’s insight was to realize how these operations could be used to process massive quantities of data on thousands of computers simultaneously (called a cluster).

MapReduce consists of two primary operations:

• During the map step (which can be run in parallel across many machines) each element in the list is filtered, transformed or sorted as required. This obviously relates to the intermediate operations we have already seen on the Stream API such as map and filter.

• Once the map step is complete the results are passed to the reduce step (which may or may not be run in parallel). The reduce step is responsible for aggregating the data in some manner. This step is obviously related to the terminal operations we have seen on the Stream API.

Many MapReduce implementations have sprung up since Google published their paper, including Hadoop, which is an open source Java implementation. Typically these implementations designate one computer to be the controller: this farms out work to other nodes, which operate independently of one another, and collects the results. For instance, a 20GB file may be split into 10MB chunks, and each chunk sent to a different computer to be processed.

The benefits of implementations like Hadoop is that the programmer does not need to focus on the implementation of the multi-threaded code: they simply need to provide a set of operations and the framework takes care of the farming out the algorithm to potentially thousands of cores.

### Fork/Join API

As the previous section demonstrated, the key to processing large data sets in a parallel manner is derived from splitting the data up (a process also known as forking), and processing sub-sets of the data in parallel. Once this data has been processed, it is joined back together (a process known as joining) and aggregated in some manner. Fork and join are therefore akin to the terms map and reduce.

It has been possible to write code in this manner since the very first release of Java using Threads, and other threading concepts such as the synchronized keyword. Writing multi-threaded code is difficult for many programmers however, and error prone even for experienced programmers. Concurrency issues and race conditions meant many programmers would rather avoid multi-threaded code if possible.

In order to alleviate some of the inherent problems with multi-threaded code, Java introduced a Fork/Join framework in Java 7 (JSR-166). The key to this framework was the ForkJoinPool class. Using the fork/join framework was a major advance: it essentially provided a pool of worker threads who all competed to accept jobs – the programmer could simply create jobs and have them processed in an efficient manner. It also provided a set of management methods to monitor the behavior of the pool.

Even with the Fork/Join framework however, the programmer was still in control of the threading process to some degree, and had to write algorithms in the manner dictated by the Fork/Join API.

### Parallelism with Streams

The Streams API head in a different direction from the Fork/Join API (and all the other concurrency APIs that have been added to Java since Java 5). The Streams API takes the position that parallelism should be explicit – but non-intrusive. You have to ask for parallelism but you do not actually have to do anything in terms of implementing it.

Requiring the programmer to ask for parallelism is important, since the same program may behave differently when processed in parallel – particularly when ordering is important. Once it has been asked for however, the Java platform takes care of optimizing the algorithm across the available hardware.

In order to see how simple it can be to change a Stream from serial to parallel processing, the following line:

l.stream().filter(p -> p%2==1).mapToInt(p -> p * p).sum()

could be written:

l.parallelStream().filter(p -> p%2==1).mapToInt(p -> p * p).sum()

Naturally, on a small list we are unlikely to see any benefits from parallel processing, so let's try it out on a more intensive example. The following program sets up a Stream of all the positive integers, and then finds the average of the even numbers. The first version uses a parallel implementation (the Stream returned from the range method is turned into a parallel stream by invoking the parallel method). The second version is serial.

package streams;

import java.util.OptionalDouble;

import java.util.stream.IntStream;

public class LargeRange {

  public static void main(String[] args) {

 long start = System.currentTimeMillis();

 OptionalDouble result = IntStream.range(0, Integer.MAX_VALUE)

.parallel()

.filter(i -> i % 2 == 0)

.average();

 System.out.printf("Parallel version took %d\n",

 System.currentTimeMillis()-start);

 start = System.currentTimeMillis();

 OptionalDouble result2 = IntStream.range(0, Integer.MAX_VALUE)

.filter(i -> i % 2 == 0)

.average();

 System.out.printf("Serial version took %d\n",

 System.currentTimeMillis()-start);

 }

}

When I ran this on a reasonably old MacBook Air I got the following results:

Parallel version took 4800

Serial version took 9629

Unsurprisingly, when I looked at CPU usage, the parallel version was using twice as much CPU. Naturally, results may vary from machine to machine, so try this out for yourself and take a look at the results.

The great thing about this example is that I have doubled performance by invoking a single method.

Although parallel processing is simply an option, it can highlight issues that are not apparent in the same code when processed serially. A prime candidate of this is where any of the lambda expressions passed to operations in the pipeline have side effects: i.e. they mutate state that is used by other lambda expressions.

As discussed above, mutating the state of an object in lambda expressions is discouraged – but allowed. For instance, there is nothing to stop code in the pipeline adding elements to a common Collection – this is likely to cause problems when parallel processing is used however, since Collections are not thread-safe.

Before considering parallelization, therefore, it is worth asking the following questions:

**Will parallel processing improve performance?**

Parallel processing will not necessarily improve performance. Some operations, such as sorting and collecting, are not always quicker in parallel. It is therefore always wise to benchmark algorithms in serial and parallel mode to confirm that parallelism is actually providing benefits.

If you consider the groupingBy examples above, these added all related elements to a common List. Java Lists are not thread-safe, therefore the groupingBy method will need to synchronize access to the List, and this could easily negate the benefits of parallel processing.

Likewise with sorting, it is possible to perform parallel sorts: each thread can use an algorithm such as quicksort to process a subset of the elements, and then these sets of sorted elements can be sorted using merge sort: depending on the quantity of data, this will not necessarily be quicker that performing a serial sort.

Finally, the distinct operation is another example of an operation that is hard to perform with parallel processing – particularly in an unsorted set of data. Each thread can easily determine the distinct elements amongst the data it has been asked to process – but naturally these distinct sets from each thread would need to be joined back together to get a definitive list of distinct elements.

**Can the algorithm be parallelized?**

Not all algorithms can be parallelized without resulting in bugs. This is particularly common for reduce operations - specifically, reduce operations need to be associative in order to be parallelizable.

As an example, summing a list of numbers is always associative. This is because it does not matter which order we process the numbers in. If we have the numbers 8, 6 and 3 we can sum these as (8 + 6) + 3 or 8 + (6 + 3). No matter how we add these three numbers the result will be 17.

Other reduce operations are not associative. Subtraction, for instance, depends on the order of the elements (8 – 6) – 3 = -1 whereas (3 – 8) – 6 = -11.

To see this in action, consider the following program:

package streams;

import java.util.OptionalInt;

import java.util.stream.IntStream;

public class Associative {

 public static void main(String[] args) {

 OptionalInt result = IntStream.range(1, 1000)

 .parallel()

 .reduce((a, b) -> a-b);

 System.out.println(result.getAsInt());

 result = IntStream.range(1, 1000)

 .reduce((a, b) -> a-b);

 System.out.println(result.getAsInt());

 }

}

In both cases the Stream contains identical elements, and the reduce operation contains an identical implementation, but the first reduce occurs in the context of parallel processing. If I run this I get the following output.

-124

-499498

If however I change this reduce operation to perform a sum:

IntStream.range(1, 1000).reduce((a, b) -> a+b);

Both examples produce identical results:

499500

499500

This is dangerous: the compiler is not able to detect that we are performing a non-associative operation; therefore we have introduced a bug that is not easy to spot.

The point to learn from this is that you should not introduce parallelism for the sake of it: you should decide what you are trying to achieve with parallelism, and you should check that your algorithm functions correctly as a parallel operation.

Another important consideration for parallel streams is sorting. The two lines below may look like they would print out the same results:

package streams;

import java.util.stream.IntStream;

public class Associative2 {

 public static void main(String[] args) {

 System.out.println("Running in parallel");

 IntStream.range(1, 1000)

 .parallel()

 .filter(a -> a %2 == 1)

 .limit(10)

 .sorted()

 .forEach(a -> System.out.println(a));

 System.out.println("Running in serial");

 IntStream.range(1, 1000)

  .filter(a -> a %2 == 1)

 .limit(10)

 .forEach(a -> System.out.println(a));

 }

}

In fact, they do print out the same numbers, but the order the numbers are printed is not sequential in the first case. Even though the numbers are sorted before being passed to forEach, they are not printed in the sorted order. There is a way around this – if the parallel version is changed to use forEachOrdered it will print the numbers in sorted order:

 IntStream.range(1, 1000).parallel()

.filter(a -> a %2 == 1)

.limit(10)

.forEachOrdered(a -> System.out.println(a));

The reason why this works is because the forEach operation is actually being run in serial mode: which brings us back to the first point – check that parallelism is actually bringing benefits.

One final consideration to bear in mind with parallelism has to do with the way parallelism is implemented. Under the hood, all parallel streams use a common instance of ForkJoinPool containing as many threads as you have processors:

Runtime.getRuntime().availableProcessors()

This means that if you perform a long running operation with this pool you may starve other code in the application trying to run parallel algorithms.

It is useful to complete this discussion by comparing parallel streams to MapReduce frameworks such as Hadoop. Essentially parallel streams provide similar capabilities as Hadoop – but on a far smaller scale. Where Hadoop farms out and coordinates processing with many computers, parallel streams farm out and coordinates processing with many processors on the same machine.

## Conclusion

From my point of view the Streams API is one of the most important advances I have seen in Java since I began using it. Everywhere I look in the Streams API I find better ways of writing code I have written hundreds of times. Prior to Java 8 it was still possible to perform aggregate operations on data, but the code was far more verbose and far more prone to bugs.

The Streams API therefore has the ability to change the way I think about implementing algorithms in Java.

# Interfaces

Java 8 has made significant changes to the way interfaces are defined. We have already seen the changes that have been added to support FunctionalInterfaces, but another important change has been added called default methods: these allow implementation details to be included in interfaces.

It may sound a strange decision to allow Interfaces to contain implementation details, since it largely goes against the whole ethos of interfaces: to provide contracts that classes could choose to implement.

Default methods are also commonly referred to as defender methods and virtual extension methods.

Default methods have mainly been added to support some of the other changes in Java 8\. If you consider the Collections API, many fundamental types (such as List and Set) are interfaces. Java 8 wanted to add new methods to these interfaces to support Streams, but adding new methods would suddenly break all code for anyone who had implemented these Interfaces. Interfaces have historically been very difficult to modify if third parties have implemented them, since the changes will never be backwards compatible with their code.

Java 8 now allows methods to be added to Interfaces along with default implementations. This means that new methods can be added to interfaces, along with default implementations. Any existing implementations of the interface will automatically pick up the default implementation, while new classes implementing the interface can either choose to provide their own implementation or use the default implementation.

Since Java classes can implement multiple interfaces, this change essentially brings a form of multiple inheritance to the Java language. Before jumping in to take a look at the changes, it is therefore perhaps worth taking a step back and looking at one of the primary reasons Java did not previously support multiple inheritance: the diamond problem.

We will start with a very simple interface:

package diamond;

public interface A {

 void doSomething();

}

We will next implement this interface in two separate classes:

package diamond;

public class B implements A {

 @Override

 public void doSomething() {

 System.out.println("Doing something the B way");

 }

}

and

package diamond;

public class C implements A {

 @Override

 public void doSomething() {

 System.out.println("Doing something the C way");

 }

}

Now, if we were to write a class that extended both B and C (let’s call it “D”), which implementation of doSomething should it use? This is called the diamond problem because a class diagram of this structure looks like a diamond:

![](images/00001.jpeg)

Before looking at how the diamond problem is resolved, let's jump in and write an interface with a default method:

package defaultmethods;

public interface A {

 public default void doSomething() {

 System.out.println("I am A");

 }

}

Notice the use of the “default” keyword. Previously this keyword has only had meaning inside switch statements and annotation declarations; it now takes on meaning inside interfaces.

Although this interface contains an implementation for its only method, it still is not possible to directly instantiate an instance of this interface: a class still must implement it in order for it to be used.

We can now implement this interface as follows:

package defaultmethods;

public class B implements A {

}

Notice that we do not have to implement the doSomething method if we don’t want to.

We can now instantiate B, and invoke the doSomething method:

package defaultmethods;

public class DefaultMethods {

 public static void main(String[] args) {

 B b = new B();

 b.doSomething();

 }

}

This will print “I am A”.

We will now create a second interface with the same doSomething method signature:

package defaultmethods;

public interface A2 {

 public default void doSomething() {

 System.out.println("I am A2");

 }

}

And change class B to implement both interfaces:

package defaultmethods;

public class B implements A, A2 {

}

This will result in a compilation error, since the compiler cannot know which version of the doSomething method B wants to use.

We now have three choices:

• Change B to only implement either A or A2

• Provide an implementation of doSomething on B

• Explicitly tell the compiler to use the implementation in A or A2

The first two options are fairly self-explanatory; the third option can be achieved as follows:

package defaultmethods;

public class B implements A, A2 {

 @Override

 public void doSomething() {

 A2.super.doSomething();

 }

}

This tells the compiler to utilize the implementation on A2.

One important thing to note with default methods is that they cannot provide default methods for any of the methods defined on Object. For instance, they cannot provide implementations of toString or equals. The primary reason for this is that all objects already have default implementations for these methods; therefore a decision was made to disallow interfaces from providing an alternative default implementation.

Although default methods provide a form of multiple inheritance, they do have limitations. The default methods do not have access to the state of the object that has implemented them, and they cannot store state of their own – therefore they only provide behavioral inheritance.

Interfaces may also now provide static methods – previously they could only define static fields. A static method on an interface looks identical to a static method on a class:

package defaultmethods;

public interface A {

 public default void doSomething() {

 System.out.println("I am A");

 }

 public static void staticMethod() {

 System.out.println("I am a static method");

 }

}

Adding static methods to interfaces is less controversial than default methods, since there is no concept of inheritance with static methods. In fact they work particularly well in cases where an Interface only contains static methods, since it is clear that it should not be instantiated - previously it was common to use abstract classes for this purpose.

## Conclusion

It is difficult to know how widely default methods will be used. Clearly they offer a tremendous benefit in allowing you to augment legacy interfaces without breaking backwards compatibility, but should they be widely used in new code? In particular, when should you use abstract classes and when should you use default methods?

This is a difficult question to answer, but probably the easiest way to answer it is to think about the functionality you need to implement: if it relies on the state of the object then you have to use abstract classes, if it is behavioral, and receives all relevant data from its parameters it is possible to use either abstract classes or interfaces.

If default methods are an option, the next way to think about this question is to consider the times you have implemented interfaces and been forced to implement methods either not directly related to your task at hand, or with obvious default implementations. If you detect cases like this you should consider providing default methods in your interfaces.

An alternative way to think about this is to consider the cases where you have created abstract classes that cannot easily be used by other classes due to the single-inheritance restrictions. This often happens when a class in question is a utility class, and the code using it may therefore not want to directly extend it (since it is already extending another class).

This brings us to the subject of mixins. A mixin is a class that contains a combination of methods from other classes. They can be particularly useful where you want to provide a lot of optional methods – or where you want a method to be available in many classes. Mixins get their names because they mix together functionality from different classes into a single class.

As an example of a mixin, consider an situation where we have a class called Car, and another class called Person. We could create a mixin called CarDriver that brings together both those implementations, and provides an implementation representing a Person driving a Car. This would make available any methods defined on Person (e.g. getName) with methods on Car (such as getMake), while also allowing other functionality to be added (e.g. getOwningPeriod).

Mixins are still somewhat limited in Java 8 since they cannot access state, but if the relevant functionality is behavioral they can be created. Consider a case where you had many different classes for processing files of different types (XML files, CSV files, text files), and each was defined in a separate interface, using distinct method signatures. If these used default methods it would be possible to mix them into a single class that could perform processing of any file type.

# Java Date/Time API

Dates and times seem like a simple subject. People use dates and times on a daily basis, and it is not until you begin using them in software that you really have to start thinking about how complex they really are.

I’m going to assume you have worked with Java enough to understand the complexities that can occur when dealing with dates, especially when concepts like leap years, daylight savings time and time zones are taken into account.

To make matters worse, the core class for representing dates and times in Java (java.util.Date) is not the greatest achievement of the language. The class goes all the way back to JDK 1.0, and it has barely improved since (although the Y2K bugs were fixed). Just reading through the first few lines of the Java doc leaves you asking why, why why?

• A year y is represented by the integer y - 1900\. (the year 2014 is represented as 114 - why not  2014?)

• A month is represented by an integer from 0 to 11; 0 is January, 1 is February, and so forth; thus 11 is December. (why not 1-12?, and why not introduce an enumerated type?)

• A date (day of month) is represented by an integer from 1 to 31 in the usual manner. (why not following the same 0 based counting as months?)

Java introduced the concept of Calendars in JDK 1.1 to alleviate some of the problems with the Date class, and simultaneously deprecated a whole lot of functionality in Date. Despite this, the whole handling of date and time has always been slightly awkward in Java. Date manipulation is particularly painful in Java, with the need to constantly swap back and forward between Dates and Calendars.

Due to the deficiencies (perceived or otherwise) with the Java language itself, the Joda open source library has continued to grow in popularity over the years by offering an alternative implementation of dates and times.

Java has ultimately decided to provide a Joda-like API alongside the Date/Calendar API: this is called the Date and Time API (JSR 310).

If you are happy with the existing Date/Calendar API, you can continue to use it. If you are happy with Joda as a standalone library, you can continue to use it. If you want to use the new Date and Time API you can use it. The choice is yours.

If this chapter were to provide an overview of the entire Date and Time API it would become very boring very quickly, and contain an enormous amount of duplication. This chapter will therefore attempt to set out the core principles of the API: once these are understood it is straightforward to extend this knowledge to other tasks with the API.

The Date and Time API is designed to take into account two distinct ways of representing date and time:

• In human terms: this uses the familiar concepts of months, days, hours and durations.

• In machine terms: this measures the amount of time that has passed (in nano-seconds) from an epoch.

When dealing with the Date and Time API you can decide the date and time implementation that best suits your needs from the following options:

**• LocalDate**: this represents the year, month and day portion of a date independent of any time zone. This is useful for representing dates such as holidays, since 25 December is a holiday regardless of whether you are in the US, Australia or the United Kingdom.

**• LocalTime**: this is essentially the same as LocalDate, but it only represents a time, e.g. 12:55:21 (times are always captured to nano-second precision).

**• LocalDateTime**: this is the same as LocalDate, but contains time information as well as date information.

**• ZonedDateTime**: this is the same as LocalDateTime, except it contains a time zone offset from UTC time (e.g. -05:00) and a zone ID (e.g. America/Detroit).

**• OffsetDateTime**: this is identical to ZoneDateTime but does not contain a zone id, it only contains an offset.

**• OffsetTime**: this is similar to OffsetDateTime, but only contains the time portion of the date, e.g. 13:00:21+12:00

**• Year**: this simply contains the year portion of a date

**• Month**: this is an enumerated type representing the 12 months of the year

**• MonthDay**: this represents a day and month, and can therefore be used to represent a day of the year in a year-agnostic manner.

**• YearMonth**: as expected, this contains a year and a month.

**• DayOfWeek**: this is an enumerated type representing the 7 days of the week

**• Instant**: an instant represents the number of nanoseconds that have occurred between 1/1/1970 and an instance in time. Due to the fact this is a number larger than can be accommodated by a long, the seconds since 1/1/1970 are stored in a long, and the nanoseconds offset are stored in an int.

**• Duration**: a duration is an amount of time that has elapsed between two Instants. Like Instant, the duration is recorded in terms of seconds and nano-seconds.

**• Period**: a period is a date based amount of time. This records a duration in terms of years, months and days.

Now that the basic types have been introduced it is worth jumping in and looking at some examples. Although the classes are quite different in the way they represent date and time, they tend to support a standard set of methods; these methods will be introduced below. The first example will deal with the LocalDateTime class and examine some of the ways it can be constructed and manipulated:

package datetime;

import java.time.LocalDateTime;

import java.time.ZoneOffset;

public class DateTime {

 public static void main(String[] args) {

 LocalDateTime dt = LocalDateTime.now();

 System.out.println(dt);

 System.out.println(dt.getMonth());

 System.out.println(dt.getDayOfWeek());

 dt = dt.plusDays(2);

    System.out.println(dt.getDayOfWeek());

 dt = dt.plusHours(5).plusMinutes(10);

 System.out.println(dt);

 System.out.println(dt.atOffset(ZoneOffset.ofHours(-11)));

 dt = dt.minusWeeks(20);

 System.out.println(dt);

   dt = dt.withDayOfMonth(4) .withYear(2009);

 System.out.println(dt);

 }

}

This produced the following result:

2014-03-06T19:38:34.933

MARCH

THURSDAY

SATURDAY

2014-03-09T00:48:34.933

2014-03-09T00:48:34.933-11:00

2013-10-20T00:48:34.933

2009-10-04T00:48:34.933

This short example demonstrates a number of useful methods. For a start, there is a now() method for creating a LocalDateTime representing the current date and time:

LocalDateTime dt = LocalDateTime.now();

There are also a variety of methods for accessing a specific portion of the date or time (such as the year or month). You may recall that these methods were deprecated from java.util.Date, but are available in a similar form on java.util.Calendar:

dt.getMonth()

dt.getDayOfWeek()

Next, there are a wide array of methods for adding or subtracting units of time (e.g. weeks, years, hours) from a LocalDateTime. Since LocalDateTime is immutable, these always return a new instance of LocalDateTime. These are somewhat similar to the methods on java.util.Calendar, but cover a wider array of options, and, unlike Calendar, do not mutate the date object:

dt.plusDays(2)

dt.plusHours(5).plusMinutes(10)

An alternative way of manipulating a LocalDateTime is with the methods prefixed “with”, e.g. withMonth, withYear. These methods also return a new LocalDateTime, manipulated to have the appropriate unit set to the value specified in the request:

dt.withDayOfMonth(4).withYear(2009)

Finally, there are ways to convert this type of date object into other types of date, the example shows atOffset, but atZone is also supported:

dt.atOffset(ZoneOffset.ofHours(-11))

In addition to creating a LocalDateTime with the static now() method, the static of() method can be used. For example:

LocalDateTime dt = LocalDateTime.of(2014, Month.MARCH, 3, 12, 24, 33);

This method is overloaded, so you can choose how precise you want the value to be by optionally providing seconds and nanoseconds.

LocalDateTime instances can also be parsed from a textual String (this will be examined in more detail later):

LocalDateTime.parse("2014-03-20T20:12:33", DateTimeFormatter.ISO_DATE_TIME);

Finally, they can be generated from a different type of date/time object:

LocalDateTime.from(Instant.now());

Now that we have briefly introduced some of the methods that can be used for creating and manipulating Date and Time objects, it is worth focusing on a couple of principles used by the API:

**Chaining methods**

Most of the classes in the time package support chaining. Chaining is a technique whereby the output of one method call becomes the input for another method call. We have already seen examples of this earlier in the book with the intermediate operations on the Streams API. Chaining works on the principle that the return type of a method is the type the original method was invoked on (either “this” or a new instance of the type the method was invoked on).

The following are examples of chaining:

dt.withDayOfMonth(4).withYear(2009)

dt.plusHours(5).plusMinutes(10)

**Immutable objects**

The classes defined in the Dane and Time API are immutable. This means that once their value is set it can never be changed. Even when their value appears to change Java is actually creating a new instance of the object.

There has been a move towards immutable classes in Java since they tend to be easier to use in multi-threaded environments, and also lead to better practices in general, since the state of a variable will not be modified without the knowledge of one of its references. For instance, consider the following code from the Calendar API:

Calendar c = new GregorianCalendar();

Calendar c2 = c;

c.add(Calendar.DATE, 1);

The value in the Calendar referenced by c2 is changed without its knowledge. This situation can never occur with the Date and Time API.

## Year and MonthDay

Let's now look at a different set of examples with the Year and MonthDay classes (remember, these only deal with a subset of the fields needed to fully represent a date):

package datetime;

import java.time.Month;

import java.time.MonthDay;

import java.time.Year;

public class YearMonth {

 public static void main(String[] args) {

 Year y = Year.now();

 System.out.println(y.isLeap());

 System.out.println(y.isBefore(Year.of(2013)));

 System.out.println(y.isAfter(Year.parse("2013")));

 MonthDay md = MonthDay.of(Month.FEBRUARY, 29);

 System.out.println(md.atYear(2011));

 System.out.println(md.isValidYear(2012));

 System.out.println(md.isValidYear(2013));

 }

}

This produces the following result:

false

false

true

2011-02-28

true

false

As you can see, different classes in the Date and Time API sometimes support additional methods. The Year class supports an isLeap() method that indicates if the year specified is a leap year, while the MonthDay class supports an isValidYear method to indicate if the day and month represent a valid date in a particular year.

All date/time classes also support isBefore and isAfter methods for comparing two instances of the same type.

## Instant

As mentioned above, an Instant represents a point in time, and is stored as a long and int pair, representing the number of nanoseconds that have passed since 1 January 1970 (midnight UTC).

As it happens, timekeeping in nanoseconds is surprisingly complex. Seconds are defined via atomic clocks: such seconds are referred to as SI seconds. There are very close to 86400 SI seconds in a day (24 x 60 x 60).

Unfortunately the devil is in the detail – very close is not the same as exactly. To make matters worse, not all days are exactly the same length, and the length of a day is not predictable. Although the variants are tiny, they do add up after time, therefore UTC incorporates a concept called leap-seconds. These allow a day to have 86399 SI seconds or 86401 SI seconds, rather than the 86400 SI seconds expected.

Due to these complexities, the designers of the Date and Time API decided to create their own time-scale called the Java Time-scale. This time-scale always has 86400 seconds in a day – but each second may not be the same length as an SI second. This allows Java to reflect the tiny changes in the length of each day without moving away from the simplicity of 86400 seconds in a day.

How this works is largely up to the Java implementation. According to the documentation: “Implementations of the Java time-scale using the JSR-310 API are not required to provide any clock that is sub-second accurate, or that progresses monotonically or smoothly. “

If you are using Java in environments where extreme precision is required you probably want to investigate the implications of this statement in relation to your chosen JVM.

Now that the details have been addressed, the following is a code example using Instants:

package datetime;

import java.time.Instant;

import java.time.temporal.ChronoUnit;

public class InstantExample {

 public static void main(String[] args) {

 Instant now = Instant.now();

 System.out.println("Epoch seconds = "+ now.getEpochSecond());

 System.out.println("Offset nanoseconds = "+ now.getNano());

 System.out.println(now.toString());

 now = now.minusSeconds(86400 );

 System.out.println(now.toString());

 System.out.println(now.until(Instant.now(), ChronoUnit.HOURS));

 }

}

This uses the familiar now() method to construct an Instant, and then prints its seconds and nanoseconds.

As the example shows, it is possible to add or subtract seconds from an Instant to create a new Instant reflecting that offset.

It is also possible to use the until method to determine how far apart two Instants are in the required unit – hours in this example.

## Duration and Period

The final classes we will examine are Duration and Period, which are both mechanisms for recording the passing of time. As mentioned above, durations are used to track a period of time in seconds and nanoseconds, while a period is used to track a period of time in years, months and days.

The following is an example program that constructs a Duration as the difference between two Instants roughly 1050 milliseconds apart:

package datetime;

import java.time.Duration;

import java.time.Instant;

public class Durations {

 public static void main(String[] args) {

 Instant i1 = Instant.now();

 try {

 Thread.sleep(1050L);

 } catch (InterruptedException ex) {

 }

 Instant i2 = Instant.now();

 Duration d = Duration.between(i1, i2);

 System.out.printf("%d seconds and %d nanoseconds elapsed\n",

 d.getSeconds(), d.getNano());

 }

}

Once a Duration has been created, it can be used conveniently with other types of Date or Time:

LocalDateTime ldt = LocalDateTime.now();

ldt = ldt.plus(d);

This code adds the duration to an instance of LocalDateTime.

Periods are used to find the number of years, months and days between two dates. The following code constructs a period representing the difference between two LocalDate instances:

package datetime;

import java.time.LocalDate;

import java.time.Month;

import java.time.Period;

public class Periods {

 public static void main(String[] args) {

 LocalDate ldt1 = LocalDate.of(2008, Month.JANUARY, 22);

 LocalDate ldt2 = LocalDate.of(2014, Month.MARCH, 12);

 Period p = Period.between(ldt1, ldt2);

 System.out.printf("%d years, %d months, %d days\n",

p.getYears(), p.getMonths(), p.getDays());   

 }

}

This prints:

6 years, 1 months, 18 days

It is also possible to construct Periods from their static constructor methods:

Period p2 = Period.ofDays(2000);

If we were to print the years and months of this Period it would print 0 – in fact the printf statement above would produce the following:

0 years, 0 months, 2000 days

This is because we have not specified the period in relation to any fixed date, therefore it is not possible to know how many months and years it is. For instance, 366 days could be 1 year and 1 day or 1 year and 0 days depending on the context, i.e. does it include the 29th February.

## Formatting and Parsing

The existing Date and Calendar API uses the SimpleDateFormat class to convert Dates to and from Strings. This is one of the most dangerous classes in Java.

SimpleDateFormat looks like a simple utility class, where its parse and format methods would fulfill the goals of functional programming: the same inputs will always produce the same output. In fact they don’t, because SimpleDateFormat stores object level state as it performs its processing, and therefore is not thread-safe.

Although this is mentioned in the Java Doc,

“Date formats are not synchronized. It is recommended to create separate format instances for each thread. If multiple threads access a format concurrently, it must be synchronized externally.”

I found this out the hard way: I assigned SimpleDateFormat to a static variable in a multi-threaded environment, and found it would randomly produce outputs that did not match its inputs.

I still regularly find other programmers falling into this trap.

The Date and Time API provides its own parsing and formatting functionality, and this is thread-safe (this is unsurprising considering dates and time objects are immutable).

We have already briefly seen an example of parsing dates using the following code:

LocalDateTime.parse("2014-03-20T20:12:33", DateTimeFormatter.ISO_DATE_TIME);

In this case, the expression DateTimeFormatter.ISO_DATE_TIME is an instance of the DateTimeFormatter class. This defines a date and time format as follows:

'2011-12-03T10:15:30+01:00[Europe/Paris]'

Since we are using a LocalDateTime the time zone and offset are irrelevant, therefore we have omitted them.

DateTimeFormatter provides a whole set of predefined date and time formats, such as;

• ISO_DATE

• ISO_TIME

The definitions for these can be found on the DateTimeFormatter Javadoc.

 If the existing patterns do not meet your needs, you can of course define your own patterns. The pattern language for DateTimeFormatter is the same as for SimpleDateFormat:

DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MMM dd yyyy");

LocalDate ldt = LocalDate.parse("Jan 22 2014", formatter);

The pattern above can be used for parsing a textual date into an object that only contains date information; for instance, the following code is perfectly legal and constructs a year with the value 2014:

DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MMM dd yyyy");

Year year = Year.parse("Jan 22 2014", formatter);

This code is not valid however:

DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MMM dd yyyy");

LocalDateTime ldt = LocalDateTime.parse("Jan 22 2014", formatter);

This produces a java.time.format.DateTimeParseException, since the format does not contain time information, and therefore is insufficient for populating all the fields on a LocalDateTime instance.

Formatting is the reserves of parsing. The main constraint of formatting is that the pattern can only contain elements that are relevant for the given object. Therefore, the following code is valid:

LocalDate ld = LocalDate.now();

ld.format(DateTimeFormatter.ofPattern("yyyy MM"));

but the following code will result in a java.time.temporal.UnsupportedTemporalTypeException:

LocalDate ld = LocalDate.now();

ld.format(DateTimeFormatter.ofPattern("yyyy MM dd hh"));

In this particular case we are attempting to format the hour of a LocalDate – which is not possible.

It is also possible to format dates based on the defaults of the user’s locale. For instance, the following will print the date in a locale specific manner:

LocalDate ld = LocalDate.now();

ld.format(DateTimeFormatter.ofLocalizedDate(FormatStyle.SHORT));

## Conclusion

I am personally glad to see the inclusion of the Date and Time API into the language. While the Joda library performed admirably, there are benefits to incorporating it into the core language, since it is likely that other libraries and frameworks that use dates and times will be more likely to provide support for them.

For instance, I typically use the Hibernate library to persist Java objects to a relational database. Hibernate naturally needs to provide mappings for Java Dates to database Dates. Although Joda support has been added through a separate project, the Hibernate team’s effort naturally focused on the native java.util.Date object. It is likely that in the future, similar projects would focus on the objects in the Date and Time API.

# Nashorn

It has been possible to run JavaScript on the JVM for some time via the Rhino JavaScript engine. Nashorn (pronounced Naz-horn) attempts to provide a higher performance JavaScript engine, with more seamless integration between Java and JavaScript, and makes JavaScript a first class language on the JVM.

The groundwork for Nashorn was actually laid down in Java 7 with the “InvokeDynamic” feature as a new bytecode instruction. This feature made it simpler to write dynamically typed languages in Java (which itself is a statically typed language).

Nashorn supports the JavaScript specification ECMA 5.1.

## Why would you want to use JavaScript on the JVM?

First off, you may not want to, in which case you can ignore this feature. I am a big fan of JavaScript, and even I have not decided if I will use JavaScript on the JVM. Interestingly, many of the other developments in Java 8 make me less likely to want to use JavaScript, since they provide many of the language features I found missing in Java.

There are however several situations where a case could be made for using a dynamic language:

**• Scripting**: there are many times where you want to perform a fairly straightforward operation such as parsing and transforming a file. It is typically a lot faster to write code such as this in a scripting language than a language such as Java – at least it was before Java 8 was released.

**• Prototyping**: it is often quicker to perform prototyping with a dynamic language since it is not necessary to construct an entire type system before implementing the details. It is also generally easier to change code in a language like JavaScript – although with the lack of type safety this sometimes comes at a cost.

**• Preference**: you may simply prefer the syntax of JavaScript to Java. Some people are probably rolling their eyes at this statement, but if you work through the bonus chapter in Appendix A you may be surprised just how elegant code written in JavaScript can be.

**• Test JavaScript code**. Testing JavaScript code inside the browser is not straightforward. Although there have been advances, particularly with Selenium WebDriver, there are many cases where it would be good to be able to test JavaScript code in a stand-alone environment using JUnit.

**• Frameworks**: You may wish to use a server-side JavaScript framework such as a JVM based version of Node.js. This is probably the most likely reason I would run JavaScript on the JVM.

**• Reuse**: You want to utilize existing JavaScript code, but run it on a common platform with Java code.

## Getting Started

It is possible to find out the scripting engines (and their languages) supported by your version of Java with the following code:

package javascript;

import javax.script.ScriptEngineFactory;

import javax.script.ScriptEngineManager;

public class JavaScript {

 public static void main(String[] args) {

 ScriptEngineManager m = new ScriptEngineManager();

 for (ScriptEngineFactory factory : m.getEngineFactories()) {

 System.out.println(factory.getEngineName());

 System.out.println(factory.getLanguageName());

 System.out.println("--------------------");

 }

 }

}  

For me, this printed the following:

Oracle Nashorn

ECMAScript

--------------------

AppleScriptEngine

AppleScript

--------------------

Ignore the AppleScriptEngine, this is supported due to the fact I am running on OSX, it is the Nashorn engine that we are interested in here.

And here is the simplest program we can write with the Nashorn engine:

package javascript;

import java.util.logging.Level;

import java.util.logging.Logger;

import javax.script.ScriptEngine;

import javax.script.ScriptEngineManager;

import javax.script.ScriptException;

public class JavaScript {

 public static void main(String[] args) {

 try {

 ScriptEngineManager m = new ScriptEngineManager();

 ScriptEngine e = m.getEngineByName("nashorn");

 e.eval("print('Hello World!')");

    } catch (ScriptException ex) {

 Logger.getLogger(JavaScript.class.getName()).log(Level.SEVERE, null, ex);

 }

 }

}

Notice the line for obtaining a reference to the ScriptEngine:

ScriptEngine e = m.getEngineByName("nashorn");

This uses the short name of the engine, so it differs from the name seen above. We then use the engine to evaluate a JavaScript statement:

print('Hello World!')

This statement uses the JavaScript engines print function to print Hello World! to standard output.

The example above does not provide any interaction between Java and JavaScript. The following is a slightly more complex example. It creates a JavaScript function called sum, and then invokes this by providing two Java variables, and then stores the result in another Java variable.

package javascript;

import javax.script.Invocable;

import javax.script.ScriptEngine;

import javax.script.ScriptEngineManager;

public class JavaScript2 {

 public static void main(String[] args) throws Throwable {

 ScriptEngineManager e = new ScriptEngineManager();

 ScriptEngine nashorn = e.getEngineByName("nashorn");

 nashorn.eval("function sum(a, b) { return a+b; }");

 Invocable invocable = (Invocable) nashorn;

 Integer result = (Integer)invocable.invokeFunction("sum", 20, 23);

 System.out.println(result);

 }

}

Note that in order to run this example we need to specify that the Nashorn ScriptEngine is an instance of Invokable – since this is not a general requirement of ScriptEngines.

It is also possible to define a JavaScript function as an instance of a specific interface. This allows the code to be run without the invokeFunction method. For instance, consider the following case that declares a JavaScript function is an implementation of the Runnable interface, and then passes it to a Thread:

package javascript;

import javax.script.*;

public class JSInterfaces {

 public static void main(String[] args) throws Exception {

 ScriptEngineManager e = new ScriptEngineManager();

 ScriptEngine nashorn = e.getEngineByName("nashorn");

 String script = "function run() {print('This is running in a thread!'); }";

 nashorn.eval(script);

 Invocable invocable = (Invocable) nashorn;

 Runnable runnable = invocable.getInterface(Runnable.class);

  Thread thread = new Thread(runnable);

 thread.start();

 }

}

Notice that the JavaScript function called run adheres to the Runnable interface – therefore it can be used to implement Runnable.

## Executing a Script

The code examples in the previous section are not necessarily examples you want to follow – writing code through String concatenation is error prone. Generally you will create a script containing JavaScript code, and execute this script from Java, potentially also passing in variables to be used in the script.

I have created a file called helpers.js in the same package as my source code. I have provided three simple utility methods in this, and a statement that invokes one of these methods:

function sum(a, b) {

 return a + b;

}

function multiply(a, b) {

 return a * b;

}

function max(a, b) {

 return Math.max(a, b);

}

print(sum(100, 15));

The functions are all global functions, so can be invoked from any code when loaded. The statement at the end calls the sum function and prints the results – and will execute as soon as the script loads.

Before continuing – it is worth noting that the print function is not supported by browser based JavaScript engines, or where it is it does something completely different (sending the current page to the printer).

The following code can be used for invoking this script:

package javascript;

import java.util.Arrays;

import java.util.List;

import java.util.logging.Level;

import java.util.logging.Logger;

import javax.script.Invocable;

import javax.script.ScriptEngine;

import javax.script.ScriptEngineManager;

public class JavaScript {

 public static void main(String[] args) {

 try {

 ScriptEngineManager m = new ScriptEngineManager();

 ScriptEngine e = m.getEngineByName("nashorn");

 e.eval(new java.io.FileReader("src/javascript/helpers.js"));

 Invocable invocable = (Invocable) e;

 Integer result = (Integer)invocable.invokeFunction("sum", 20, 30);

 System.out.println(result);

 } catch (Exception ex) {

 Logger.getLogger(JavaScript.class.getName()).log(Level.SEVERE, null, ex);

 }

 }

}

This should print the number 115 when the script loads, and then 50 when the invokeFunction code is executed.

It is important that you get the path correct. The following assumes that your project’s code is stored in a folder called “src”, and the helpers.js file is in the “javascript” package.

## Using Java in JavaScript

The interplay between Java and JavaScript can be quite complex. Any JavaScript code can instantiate Java objects, and then treat them as though they were JavaScript objects. JavaScript objects are not completely dissimilar to Java objects – as you will see in Appendix A - they support fields and methods, just like Java objects, and use the variable “this” in similar ways.

Add the following JavaScript function to the helpers.js file created earlier:

function useJava() {

 var list = new java.util.ArrayList();

 list.add(8);

 list.add(20);

 list.add(88);

 list.add(21);

 return list.stream().mapToInt(function(i) {return i*i}).sum();

}

If you look at this you will see that it constructs a Java List within a JavaScript function. It has to use the fully qualified class name because it has not performed an import. It is possible to perform imports where required using the importPackage and importClass functions.

importPackage(java.util);

importClass(java.util.List);

It is also wise to point out at this stage that the classes in java.lang are not automatically imported into scripts, since the JavaScript has many identically named objects (e.g. Boolean, Object)

Once the ArrayList is instantiated, its methods can be invoked just like any other JavaScript object – in this case we call the add method 4 times to add numbers.

It is the final line of the method that is really interesting however. We invoke the Java Streams mapToInt method, but instead of providing a lambda expression, we provide a JavaScript anonymous function.

You can then invoke this function from Java as follows:

Integer result = (Integer)invocable.invokeFunction("useJava");

## Command Line

It is also possible to access Nashorn from the command line, making it a possible choice for writing command line scripts. A utility has been provided in the bin folder of Java, and can be invoked by opening a command prompt and invoking the jjs program:

This can be provided a script, but is also a standalone JavaScript interpreter. In order to prove this, simply type the following at the command prompt:

1 + 1

This should produce the result 2.

We can actually execute any JavaScript here, for instance:

[1,2,3,4,5,6,7,8].filter(function(i) {return i%2==1})

Any input will be immediately evaluated and the result returned.

This is more than a JavaScript interpreter however – it is a JavaScript interpreter on the Java platform, therefore we can also invoke the following:

list = new java.util.ArrayList();

list.add(1);

list.add(2);

list.add(3);

result = list.stream().mapToInt(function(i) {return i*i}).sum()

print(result)

Notice how we are combining JavaScript and Java in some of these statements. The command line therefore is great as a scratch pad for trying out code before including it in a script.

If you continue on to learn JavaScript by reading the sample chapter in Appendix A, you can choose to use jjs as the interpreter for the examples.

To exit the command line use the quit() function.

jjs is actually even more powerful that the examples above suggest. It can be started in a special scripting mode as follows:

jjs –scripting

When in this mode jjs can perform the tasks of traditional shells, such as executing commands:

$EXEC("ls -l")

Execute commands with input:

$EXEC("cat", "Hello World")

Or access the environment:

$ENV.USER

In fact, you can write scripts using the following header and execute them like any other shell script:

#!/usr/bin/jjs

The use of scripting features will naturally be dependent on your underlying operating system; therefore this feature will not be discussed in any detail.

## Conclusion

This chapter has only scratched the service of what Nashorn is capable of. The main aspect to understand is that JavaScript code can use Java code, and Java code can invoke JavaScript code. The Nashorn JavaScript engine is not just another JavaScript engine therefore, since it has access to all the libraries and APIs supported by the Java platform.

# Minor Changes

This chapter will provide a roundup of some of the minor changes that have happened in Java 8\. None of these features deserve their own chapter, but each is interesting enough that you should be aware of it.

## Parallel sort on Arrays

It is now possible to perform parallel sorts on arrays. As with parallel streams this is using the common ForkJoinPool under the hood, and may lead to performance gains.

Parallel sort can be invoked by using the Arrays.parallelSort method, as opposed to the Arrays.sort methods. As with parallel streams, it may not always be worth using parallel sorts, particularly if the size of the array is small (less than 10,000 elements). The larger the array, and the more processors available, the more likely it is that parallel sort will lead to performance gains.

If you would like to benchmark this yourself, here is an example program that adds 10,000,000 random doubles to an array and then sorts them using parallelSort

package arrays;

import java.util.Arrays;

public class ArraySort {

 public static void main(String[] args) {

 double[] nums = new double[10000000];

 for (int i = 0; i < 10000000; i++) {

 nums[i] = Math.random();

 }

 long start = System.currentTimeMillis();

    Arrays.parallelSort(nums);

 //Arrays.sort(nums);

 System.out.println(System.currentTimeMillis()-start);

 }   

}

Once you have timings for parallel sorting, try changing the implementation to use serial sort by changing the following lines:

//Arrays.parallelSort(nums);

Arrays.sort(nums);

On a large array like this I do notice a significant improvement with parallelSort, but with smaller arrays the difference was insignificant.

## Annotation Changes (JSR 308)

Prior to Java 8, annotations could be used on the declarations of classes, methods, fields, packages, local variables and on method parameters.

It is now possible to apply annotations anywhere a type declaration occurs. This may be used in the future to allow even stronger type checking than is currently available. For instance, if types are used to define local variables they can be given annotations:

public void method() {

@NotNull String str1 = “Hello”

}

They can also be used when constructing objects with the new keyword:

ObjectA objecta = new   @Readonly ObjectA();

Or in generic declarations:

List<@CreditCard String> creditCards = new ArrayList<>();

Or when throwing exceptions:

throw new @HighPriority IOException();

Essentially anywhere types are used they can be accompanied by annotations.

The main reason these changes will not be discussed in this book is because by themselves these change do not bring any immediate benefits – it is up to framework developers to use this feature in meaningful ways.

All of the examples above represent possibilities only – none of these annotations actually exist. This change does have the potential to bring significant improvements to Java in the future however, just as the original inclusion of annotation brought enormous benefits.

## Reflection Changes

Java 8 provides a minor enhancement to the Java Reflection API. It is now possible to extract method parameter names: previously it was only possible to extract their types – something I found annoying on a number of occasions.

Class<String> clz = String.class;

for (Method m : clz.getDeclaredMethods()) {

 System.out.println(m.getName());

 for (Parameter p : m.getParameters()) {

 System.out.println(p.getName());

 }

}

In order to use this feature, the source code needs to be compiled with the javac command line option “–parameter”. This ensures that appropriate information is added to the class file.

## Math Changes

We have already seen that the primitive wrappers (e.g. Integer, Long) have had new static methods added that previously were only available as static helpers on Math:

• Min

• Max

This is a more natural location for these methods, but naturally they are still available on the Math class for backwards compatibility.

The Math class itself also now contains a number of new static methods. The bulk of these are variants of existing methods, but throw an ArithmeticException if they overflow (exceed the capacity of the data-type). This is typically more useful, since overflowing is seldom a desired feature.

• [Math.addExact(int, int)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#addExact(int,%20int))

• [Math.addExact(long, long)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#addExact(long,%20long))

• [Math.subtractExact(int, int)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#subtractExact(int,%20int))

• [Math.subtractExact(long, long)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#subtractExact(long,%20long))

• [Math.multiplyExact(int, int)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#multiplyExact(int,%20int))

• [Math.multiplyExact(long, long)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#multiplyExact(long,%20long))

• [Math.negateExact(int)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#negateExact(int))

• [Math.negateExact(long)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#negateExact(long))

• [Math.decrementExact(int)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#decrementExact(int))

• [Math.decrementExact(long)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#decrementExact(long))

• [Math.incrementExact(int)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#incrementExact(int))

• [Math.incrementExact(long)](http://download.java.net/jdk8/docs/api/java/lang/Math.html#incrementExact(long))

BigInteger and BigDecimal also provide corresponding methods for converting values back to primitives:

• [longValueExact()](http://download.java.net/jdk8/docs/api/java/math/BigInteger.html#longValueExact())

• [intValueExact()](http://download.java.net/jdk8/docs/api/java/math/BigInteger.html#intValueExact())

• [shortValueExact()](http://download.java.net/jdk8/docs/api/java/math/BigInteger.html#shortValueExact())

• [byteValueExact()](http://download.java.net/jdk8/docs/api/java/math/BigInteger.html#byteValueExact())

This is a useful way of knowing overflow errors have occurred, so these variants should be favored over their non-exact siblings.

## String changes

Java 8 **finally** adds a join method for adding delimiters between Strings:

String.join(", ", "Hello", "World", "Again");

This will produce:

Hello, World, Again

The first parameter acts as the delimiter, while the remaining parameters are the Strings that are joined to the parameter.

This can optionally accept a List:

List<String> list = Arrays.asList("Hello", "World", "Again");

System.out.println(String.join(", ", list));

As we saw earlier in the book, the same basic functionality can be implemented using Streams and a join collector.

Similar functionality is also available in a new class called StringJoiner, which also allows a prefix and suffix String to be provided:

StringJoiner sj = new StringJoiner(",", "{", "}");

sj.add("Test1").add("Test2").add("Test3");

String s = sj.toString();

This produces the following:

{Test1,Test2,Test3}

# Conclusion

I hope this book, although short, has convinced you that Java 8 is more than just another Java release, and could impact (for the better) the way programmers think about expressing algorithms. Lambda expressions were a long time coming to the Java language, and although not everyone agrees with the specifics of their implementation, most people agree that the version included in Java 8 is significantly better than not having lambda expressions at all.

Java 8 also has the potential to greatly enhance the multi-threading capabilities of many applications, although, as seen, there are still risks involved in implementing parallel processing if you do not have a full understanding of how it works.

As mentioned earlier, the next section contains a bonus chapter on JavaScript from my book “A Software Engineer Learns HTML5, JavaScript and jQuery”. If you enjoy this chapter and would like to learn more, it is available from Amazon and other online retailers:

[http://www.amazon.com/Software-Engineer-Learns-JavaScript-jQuery-ebook/dp/B00GAMTRI8/ref=sr_1_2?s=digital-text&ie=UTF8&qid=1394932033&sr=1-2](http://www.amazon.com/Software-Engineer-Learns-JavaScript-jQuery-ebook/dp/B00GAMTRI8/ref=sr_1_2?s=digital-text&ie=UTF8&qid=1394932033&sr=1-2)

JavaScript made me look at Java in a new light. It also provides an interesting take on lambda expressions, and therefore learning how these work in another language will help you understand the concepts in a broader context.

# Appendix A: JavaScript

This section will provide an in-depth overview of JavaScript, including its strengths and weaknesses. The intention of this chapter is to provide you a strong understanding of JavaScript fundamentals, and to focus on how the language should be used, rather than how it can be used.

JavaScript is a particularly flexible language, and does not enforce much discipline or structure on its users. In addition, JavaScript contains a number of features than can only truly be regarded as bugs. These remain in the language principally due to backwards compatibility concerns.

In order to write large-scale web applications it is necessary to harness the strengths of JavaScript, while at the same time avoiding the pitfalls that can easily confront software engineers and programmers who do not understand the language fundamentals, and do not structure their applications in a manner compatible with the growth of the code base.

In order to follow the examples in this book, simply open the Chrome or Firefox console, and enter the commands directly - I recommend Chrome.

In order to access the Chrome interpreter, simply open Chrome, and type:

• Command+Option+i on OSX

• F12 or Ctrl+Shift+I on Windows

Alternatively, you can right click anywhere on any web page and choose “Inspect Element”:

![](images/00002.jpeg)

Once the Developer Tools are open, click the “Console” tab.

In order to prove that this is a genuine JavaScript interpreter, simply type 1+1 at the command prompt:

![](images/00003.jpeg)

One aspect of browsers that have advanced tremendously over the last few years are the tools offered to developers. Browser vendors have realized that there is a direct benefit to them when developers use their browsers, and therefore actively woo developers with the tools they offer. This book will introduce you to many of the features offered by the Chrome developer tools, but it is worth investigating the various capabilities on your own.

This section will provide an in-depth overview of JavaScript, including its strengths and weaknesses. The intention of this chapter is to provide you a strong understanding of JavaScript fundamentals, and to focus on how the language *should* be used, rather than how it *can* be used.

JavaScript is a particularly flexible language, and does not enforce much discipline or structure on its users. In addition, JavaScript contains a number of features than can only truly be regarded as bugs. These remain in the language principally due to backwards compatibility concerns.

In order to write large-scale web applications it is necessary to harness the strengths of JavaScript, while at the same time avoiding the pitfalls that can easily confront software engineers and programmers who do not understand the language fundamentals, and do not structure their applications in a manner compatible with the growth of the code base.

## Types

Any understanding of JavaScript begins with an understanding of its data types, and how these types are used.

JavaScript has the following data types:

• String

• Number

• Boolean

• Null

• Undefined

• Object

Each of these will be outlined in the sections below.

### Strings

Strings are series of characters enclosed in either single or double quotes:

> "hello world"

"hello world"

> 'hello world'

"hello world"

The examples above are referred to as string literals. We can also assign a string to a variable:

> s = 'Hello world'

"Hello world"

//

When using the console, variables will not be declared with the **var** keyword. As you will see below, it is critical that this is used in most situations when writing actual JavaScript code.

We can then inspect the type of this variable using the **typeof** operator:

> typeof s

"string”

Although strings are their own data type, it is possible to invoke methods on them just as we will see it is possible to invoke methods on objects below.

> s.charAt(1)

"e"

> s.substr(6)

"world"

> s.toUpperCase()

"HELLO WORLD"

In addition, strings have properties that can be accessed, just as we will see on objects in the examples below:

> s.length

11

JavaScript strings are largely equivalent to strings in Java. One consequence of this is that strings are immutable.

//

An immutable object is an object that cannot be changed after it is first created. Even when these appear to change, as in the examples below, in reality a new object is being created.

In order to see immutability in action, declare a new variable called **t**, and assign it the value of **s**:

> t = s

"Hello world"

We can now print out the value of **t**, and also confirm that **t** and **s** are equal:

> t

"Hello world"

> s == t

true

What should happen if we now modify the string held against the variable **s**? We can append to the string value using the **+=** operator:

> s += 'test'

"Hello worldtest"

If you now print out the value of **s** you will see that the string’s value appears to have changed:

> s

"Hello worldtest"

Despite this, if you print out the value of **t** it has retained its old value:

> t

"Hello world"

When we appended “test” to the string held against the variable **s**, the underlying string was not modified; instead a new string was created and assigned to the variable **s**. Since **t** still refers to the original string, it is not impacted by the modification.

### Numbers

The number type is used to represent both integer and floating-point values; in fact all numbers are 64 bit floating-point numbers in JavaScript:

> n = 6.827

6.827

> typeof n

"number"

> n2 = 6

6

> typeof n2

"number"

Due to the fact that all numbers are floating-point, operations between two integers can return floating-point results (unlike in Java).

> 1/3

0.3333333333333333

In addition to real numbers, JavaScript also supports a number of special values.

“Not a number” is used in cases where an arithmetic operation produces a result that is not a number. Confusingly, this type is still a **number**.

> a = 9/undefined

NaN

> typeof a

"number"

It would have potentially been more useful for JavaScript to generate an error in this scenario.

Negative and positive infinity are also supported, and are most often generated when dividing by 0:

> b = 6/0

Infinity

> b == Number.POSITIVE_INFINITY

true

> c = -6/0

-Infinity

> c == Number.NEGATIVE_INFINITY

true

Again, most programming languages would generate errors if an integer was divided by 0, but since these are floating point numbers they follow the IEEE convention of returning infinity.

JavaScript also natively supports a Math library modelled almost identically on the Java equivalent. Most common maths functions are available in this library.

> Math.pow(3, 2)

9

> Math.round(3.22)

3

### Booleans

JavaScript supports a boolean type that contains the literal values **true** and **false**:

> t = true

true

> typeof t

"boolean"

> f = false

false

Equality operators in JavaScript (>, <, ==, !=, >=, <=) also return booleans as their result:

> f != t

true

### Null

Null is a data type that has a single value: **null**.

> n = null

null

Confusingly, **null** is considered to be of type object:

> typeof n

"object"

This is another bug in the JavaScript language that has been maintained for backwards compatibility. Despite this, **null** is genuinely a unique data type in JavaScript.

It is possible to set a variable to **null** after it has been assigned a value, therefore removing the reference to its current value (and changing its data type):

> q = 2

2

> typeof q

"number"

> q = null

null

> typeof q

"object"

### Undefined

The **undefined** data type is returned when you access a property on an object that does not exist, or use a variable before it is declared, or before it is assigned a value.

> typeof g

"undefined"

### Objects

Other than the types outlined above, all data types in JavaScript are objects: this includes arrays, functions, dates and user defined objects. Objects will be discussed at length in the sections below.

### Truthy and Falsey Values

Now that you have an understanding of the JavaScript data types, the next thing to understand is that some values for these types evaluate to **true**, and some evaluate to **false**. For instance, the following are all considered false in JavaScript:

• false

• 0 (zero)

• "" (empty string)

• null

• undefined

• NaN

In order to see this in action, simply ask if they are equal to **false** in the console:

> 0 == false

true

All other values represent **true** values.

As a consequence of this, it is possible to utilize a shortcut when evaluating the value of variables in conditional statements. Instead of writing the following:

> if (a == undefined || a == null) {

 a = 1;

}

It is possible to simply write:

> if (!a) {

 a = 10

}

Likewise, if you only want to use a variable if it has a value you can write the following:

> if (s) {

 console.log(s)

}

This shortcut is enormously useful, and extensively used in JavaScript code.

The final thing that should be understood is which values are equal to one another; the following may come as a surprise:

> null == undefined

true

> 5 == "5"

true

> "true" == true

false

> "1" == true

true

> "2" == true

false

There are numerous inconsistencies in the examples above, and again, these are often bugs rather than features. **Null** should not be considered equal to **undefined**, despite the fact they are both falsey values they represent very different data-types and meanings.

Fortunately, JavaScript contains an alternative pair of equality operators:

===

!==

These compare variables based on both their value and their data type, and therefore provide more expected results:

> null === undefined

false

> 5 === "5"

false

> "true" === true

false

> "1" === true

false

It is best practice to always use these equality operators unless you consciously want to compare two values you know have different data types.

 //

If you want to know whether any value is true or false in a Boolean sense, you can print it out by prepending !! to it. A single ! will negate a Boolean value, while !! provides a double negative, and therefore prints out the Boolean value of any value:

!!""

false

!!"hello"

true

### Dynamic Typing

Finally, it is worth reiterating that JavaScript is a dynamically typed language.

Languages such as Java and C++ are statically typed languages. In statically typed languages, all variables are assigned a type at compile time, and this type cannot be changed.

//

The terms strong and weak typing are sometimes used to refer to statically typed and dynamically typed languages respectively.

In a statically typed language, the compiler can perform type checking: if a variable is defined to store an integer, the compiler can check that it is not assigned a string. This catches many causes of bugs before they can become an issue at run-time.

As we have seen, JavaScript variables derive their types based on the values they are assigned at run-time, and variables can change their type if they are assigned a new value. As a result it is not possible to perform static type checking in JavaScript, e.g. to ensure a string is not provided where a number is expected.

Consider the following function that adds two numbers together:

function add(v1, v2) {

 return v1+v2;

}

If you invoke this function with two numbers, the result is as expected:

> add(1,1)

2

If you accidentally pass a string as one of the parameters however, the result is very different:

> add(1,"1")

"11"

Instead of adding the numbers, JavaScript has performed string concatenation between the number and the string. It is unlikely that this is the result expected. This is one reason why the **typeof** operator is so important in JavaScript, it allows the function above to be rewritten as follows:

function add(v1, v2) {

 if (typeof v1 === "number"

&& typeof v2 === "number") {

 return v1+v2;

 } else {

 throw "both arguments must be numbers";

 }

}

This at least ensures data type issues will be identified at run-time, even if it does not highlight these issues to the programmer who wrote the code allowing the function to be called incorrectly.

//

Using the “+” operator on different data types produces a variety of random results in JavaScript:

{} + [] = 0

[] + {} = Object

Even using the “+” operator on the same data types can produce meaningless results:

[] + [] = empty string

{} + {} = NaN

It is hard to make sense of any of these results.

In addition, the “-“ operator should only be used on numbers:

“a” + 1 = “a1”

“a” – 1 = NaN

There are many arguments for and against dynamically typed languages. This book will not address these arguments, but it is safe to conclude that dynamic typing has advantages, but those come at the risks of run-time bugs.

## Objects

JavaScript also supports objects; in fact, most values in JavaScript applications will be objects. JavaScript also supports syntax for defining classes that objects can be instantiated from. This may lead you to think JavaScript is a conventional object orientated language – this would be a mistake.

In classical object orientated languages such as Java and C#, classes must be defined before objects can be instantiated from them. It is never possible to have an object that is not a type of a specific class.

Classes are static templates that contain definitions of the properties and methods that objects will contains. During program execution, instances of these classes are created: these are called objects. All objects instantiated from the same class have the same properties and methods, although the values assigned to properties will differ from instance to instance.

When designing applications with a classical object orientated language you may find cases where you would like some objects to contain additional properties or methods, even though they are similar in other respects those created by an existing class. For instance you may have started with a class called “Vehicle” which contained the following properties:

1\. Registration number

2\. Initial year of registration

3\. Make of vehicle

4\. Model of vehicle

Objects can be instantiated from this class, and will contain four properties to which values can be assigned.

//

This book will use the term “property” to refer to the state of an object. Other languages may call these fields or attributes.

You may subsequently decide that you would like to capture more information about trucks, for instance:

1\. Number of axles

2\. Towing capacity

You cannot simply add these new properties to objects that have been created from the Vehicle class; you must first create a new class (called Truck), and extend the Vehicle class. Only when the class structure is in place can you begin creating instances of Trucks.

A further feature of classes is that they must be defined when the application is compiled; they cannot be defined on the fly at run-time. It is not possible to decide midway through program execution that you would like to start capturing an additional property on some objects.

JavaScript has a far more flexible attitude to classes and objects, in fact classes are not essential to JavaScript programming at all.

The simplest way you can create a new object in JavaScript is as follows:

> obj = {}

The **typeof** operator confirms that the **obj** variable is indeed an object:

> typeof obj

"object"

If you are familiar with classical object orientated languages you may wonder what *type* **obj** is? This object is not of any type; it is just an object.

It may sound difficult to write code without knowing the type. For instance, if a function is passed an object without knowing its type, how does it know what to do with it?

JavaScript uses an approach colloquially known as “duck typing”. There is an old saying, “if it walks like a duck, and swims like a duck, and quacks like a duck, it probably is a duck”. Likewise, in JavaScript we might say “If it has a registration number property, and has a year of registration property, it probably is a vehicle”.

An empty object with no properties or methods is not very useful. With JavaScript however, it is possible to dynamically add properties and methods:

> obj.firstName = 'John';

> obj.lastName = 'Smith';

> obj.age = 32;

> obj.increaseAge = function() {

 this.age++;

}

 //

Functions inside objects are referred to as methods. They are exactly the same as functions, except in the way they treat an important variable called **this**. You may have also noticed the use of **this** in the method above: this will be explained in full below.

If you now look at the object in the JavaScript console you will see that it has a set of properties with values assigned:

> obj

Object {firstName: "John", lastName: "Smith", age: 32, increaseAge: function}

The reason this is possible is because objects in JavaScript are really just associative arrays (also known as hash maps in other languages). Associative arrays are supported natively in most programming languages, and comprise a collection of name/value pairs.

In order to access a property on a JavaScript object, simply use the following notation:

> obj.firstName

"John"

JavaScript supports an alternative syntax for accessing and setting properties that is even more evocative of associative arrays in other languages.

> obj['firstName']

"John"

//

These two approaches are not exactly equivalent. The second approach will work when property names are not valid variables names. The dot notation on the other hand will not work if:

• The property starts with a number.

• The property contains a space or other special character except the underscore or $ sign.

• The property name is one of the language keywords.

If you are writing code that needs to handle any property name, including ones you had no say in defining, the square brackets notation should be preferred.

In addition to properties, the example above provides an example of a method being added to an object. The method **increaseAge** increments the age property by 1: it can be invoked as follows:

> obj.increaseAge()

> obj.age

33

I alluded to the use of the **this** variable inside the method:

obj.increaseAge = function() {

 **this**.age++;

}

This is the only thing that separates a function from a method: in a method the special variable **this** refers to the object itself, and therefore:

this.age

is a way of accessing the **age** property on the object. As we will see in future sections, **this** takes on several different meanings depending on context. Understanding the meaning of **this** in these different contexts is one of the keys to understanding JavaScript.

Although it is possible to construct objects without any reliance on classes, it is probably obvious that we are also missing out on the benefits that classes bring.

If you want to create a new object to refer to a different person, you need to add these properties and methods all over again. This is not a major problem for the properties of an object, since you would need to provide values for those properties anyway, but it is a major inconvenience for methods. For instance, you would need to write the following:

> obj2 = {}

> obj2.firstName = 'Albert'

> obj2.lastName = 'Jones'

> obj2.age = 28

> obj2.increaseAge = function() {

 this.age++;

}

 //

An alternative approach is to include the properties and methods inside the **{}** separating properties/methods with commas, and properties/methods from their values with colons:

obj2 = {

 firstName: 'Albert',

 lastName: 'Jones',

 age: 28,

 increaseAge: function() {

     this.age++;

 }

}

This is going to become a major inconvenience, especially if you have a large number of methods on your object.

There is a solution to this problem that does not rely on reverting to classes: you could simply clone an existing object, and change its properties as required. The object being cloned can be referred to as a prototype for other objects.

We will see in later chapters that jQuery contains a helper for cloning objects, but for now we will write our own clone implementation. This function will perform a deep clone on an object: if a property on an object contains a value that is an object, that object will also be cloned.

function clone(obj) {

 if (obj == null || typeof obj != 'object') {

 return obj;

 }

 var newObj = {}

 for (var key in obj) {

 newObj[key] = clone(obj[key]);

}

 return newObj;

}

This function uses the **for (var key in obj)** loop to iterate through all the properties on an object. This is a special kind of JavaScript loop specifically provided to iterate through properties in an object. If the value of the property is an object, it is recursively passed to the **clone** function. If it is a simple type (such as a number or string) it is returned immediately so it can be set directly on the new instance of the object. You will remember from earlier sections that strings and numbers are immutable; therefore they do not need to be cloned.

This implementation should reinforce to you how simple JavaScript objects are.

//

There are potential problems with this implementation that have been ignored for simplicity. This implementation should not be used in real applications: use versions provided in the jQuery or Underscore libraries.

You can now use this function to construct a new object for storing information about people:

> obj3 = clone(obj2)

> obj3.firstName = 'Jim'

"Jim"

> obj3.firstName = 'Duffey'

"Duffey"

> obj3.age = 42

> obj3.increaseAge()

43

As you can see we have retained the method already defined on its prototype.

This section is not intended to imply classes have no value in JavaScript, instead it is intended to demonstrate what objects truly are in JavaScript, and to suggest that there are viable ways of writing JavaScript that does not utilize classes.

There are potential pitfalls in this implementation. For instance, if you forget to set a property on the newly cloned object, it will retain the value from the object it was cloned from: this may or may not be correct, and could become a source of bugs.

Although we will examine more advanced approaches to object creation below, the approach to objects examined in this section has a lot to recommend it.

## JavaScript Object Notation

The previous section demonstrated how simple JavaScript objects are. At heart, JavaScript objects are simple associative arrays. Each property in the object can have a value that is a simple type (such as a number or a string), a function, an array, or another type of object.

When writing web-based applications it is often necessary to send data from the client to the server, or the server to the client. In order to transfer data across a network it must be encoded in a data format agreed by both the sender and the receiver.

There are many data formats that can be used to send and receive data; of these XML is probably the most common. An example XML document for representing people might look as follows:

<person>

 <firstName>John</firstName>

 <lastName>Smith</lastName>

 <age>32</age>

 <address>

     <city>Los Angeles</city>

     <postCode>90245</postCode>

 </address>

</person>

XML is a widely used data format, particularly in enterprise applications. It has many benefits, including a wide array of libraries that support it and widespread acceptance in IT departments. XML is a particularly verbose data format however, in the example above far more than 75% of the text is made up of tags rather than content.

Before gaining an understanding of JSON, first consider what a JavaScript object may look like that contained this same data:

> person = {};

> person.firstName = 'John';

> person.lastName = 'Smith';

> person.age = 32;

> person.address = {};

> person.address.city = 'Los Angeles';

> person.address.postCode = 90245;

The example above consists of two objects. The first object is a person; this then contains a second object that captures the address information.

It would not be difficult to create an object from the XML structure. There is however a data format that is far more closely aligned with JavaScript called the JavaScript Object Notation (JSON) that makes this process trivial.

You can transform this object into a JSON encoded string as follows:

> JSON.stringify(person)

"{"firstName":"John","lastName":"Smith","age":32,"address":{"city":"Los Angeles","postCode":90245}}"

The output of this function call is a string, and could be assigned to a variable:

> s = JSON.stringify(person)

A string can then be transformed back into an object as follows:

> person2 = JSON.parse(s)

The process of converting between a string and an object is called serializing and de-serializing: the string is a serialized form of the object.

//

This process is only applicable for properties: methods are not retained when an object is serialized.

JSON is a remarkably simple data format. The entire data format is contained in a couple of paragraphs at the following web site:

[http://www.json.org/](http://www.json.org/)

There are 3 types of value in JSON:

1\. **Objects**, denoted with the now familiar curly brackets

2\. **Arrays**, which are denoted by [] brackets, and contain comma separated values just like JavaScript arrays.

3\. **Literal values** (strings, numbers, Booleans)

An object or an array can in turn contain any of these 3 types. For instance, an array may contain an object, an object may contain an array, an object may contain another object, etc.

JavaScript makes it possible to convert from a *stringified* version to an *object* representation purely because the language does not rely on classes. The stringified version of the object does not contain information on what type it is: it is simply a set of properties formatted according to the JSON specification. Likewise though, JavaScript does not need to know what type of object needs to be created when de-serializing: it can simply add the appropriate properties to an otherwise empty object.

JSON has become a widely used data format even for applications that do not use JavaScript. For instance, Java contains libraries for converting to and from JSON. The only difference in languages such as Java is that you must tell the library what type of class the textual string represents.

//

Java can in fact de-serialize a string into an object without knowing the type, but it needs to use hash maps rather than programmer defined types.

One reason for the widespread adoption of JSON (beyond its simplicity) is the fact it is far less verbose than XML – the example above is roughly half the size of the XML version. Although the size is far smaller, it is still easy for a human to read and understand a JSON encoded message (which was a traditional strength XML had over other data formats, particularly binary data formats).

As we go through the book we will explore several cases where this ability to convert simply and easily from an object to a textual string is enormously useful.

## Prototypes

We will return now to our discussion of objects in JavaScript.

The **clone** function that we wrote above was our first attempt at code reuse. It allowed us to reuse or extend an object that we had already written. One problem discussed with the **clone** function was that it took all the properties from the object it was cloning, including properties that were specific to the cloned instance, such as **firstName** and **lastName**.

JavaScript provides a more elegant mechanism for extending objects called prototypes. In fact, JavaScript itself is considered a prototype-based language.

If you declare an empty object, you may think that it contains no properties at all:

> obj = {}

You can however execute the following method on the object:

> obj.toString()

"[object Object]"

Where did the **toString** method come from?

All JavaScript objects have a prototype object (this can be **null** in rare instances, but this scenario can largely be ignored). A prototype object is an object in its own right, and can encapsulate properties and methods. If we access a property or method on an object, JavaScript will first try to access that property or method on the object itself. If the object has no property or method with that name it will look for it on the prototype object.

In fact, there can be a whole chain of objects due to the fact that the object that is our prototype may itself have a prototype. If no objects in the prototype chain have a property matching the name specified then JavaScript returns a special type called **undefined**.

The prototype of our empty object was provided by **Object.prototype**. This is the only object that does not have a prototype of its own, and therefore is the end of the chain.

In order to see the prototype chain in action, we can define our own **toString** implementation on the empty object.

> obj.toString = function() {

 return "I am an object"

 };

If we now execute **toString** on this object, the newly defined version will be used:

> obj.toString()

"I am an object"

In this case you have not modified the implementation of **toString** on the prototype; it has been overridden on this specific instance. In order to prove this, you can create a new empty object, and execute the **toString** method on it:

> obj2 = {}

> obj2.toString()

"[object Object]"

The properties on a prototype are immutable, just like strings are immutable. Although all objects with the same prototype share the properties on the prototype, they cannot change the prototype; they simply override these properties on themselves.

The specific prototype assigned to objects created with the object literal notation is the **Object.prototype**. Different objects can however have different prototypes. For instance, if we create an array using the array literal notation, the variable is still an object:

> a = [1,2,3,4,5];

> typeof a

"object"

Because this is an object, it will contain the Object prototype somewhere in its hierarchy, and therefore we can invoke the **toString** method. You will notice that the **toString** implementation has been specially tailored for arrays:

> a.toString()

"1,2,3,4,5"

The array instance also has access to a whole set of other properties that were not available to our object created with the object literal notation:

> a.reverse()

[5, 4, 3, 2, 1]

> a.pop()

1

> a.push(6)

5

These methods are derived from the prototype object for arrays called **Array.prototype** (which in turn has Object.prototype as its prototype).

Due to the fact that all arrays are based on the same prototype, if we add methods to this prototype, they immediately become available to all arrays. Remember, prototypes are just objects themselves; therefore they can be modified just like any other object.

For instance, arrays do not have a “contains” method. It might be useful to implement a method that accepts a single parameter, and then returns true if the array contains that value. This can be written as follows:

> Array.prototype.contains = function (val) {

 for (var i = 0; i < this.length; i++) {

     if (this[i] === val) {

         return true;

     }

 }

 return false;

}

We can now execute the following:

> [1,2,3,4,5].contains(3)

true

> a.contains(6)

false

Adding functionality to prototypes is a very effective code reuse pattern. As soon as the functionality is added to that prototype, it is immediately available to all objects that contain that prototype in their prototype chain: even if they were created before the functionality was added to the prototype.

 //

If you are wondering how objects can be given a specific prototype, this will be explained in more detail below.

Prototypes provide a mechanism to tidy up the code reuse pattern that we used earlier. The new implementation of **clone** (which we will rename to **extends**) still accepts an object, but now returns a new empty object with that object set as its prototype.

We will first write the object that will act as the prototype. This is going to contain two methods, the increase age method we saw earlier, and a new method that returns the full name of the person as the concatenation of the first and last name. In addition, this implementation is going to combine object creation, and the addition of methods to the object, into a single step:

> person = {

 getFullName: function() {

 return this.firstName+" "+this.lastName;

 },

 increaseAge: function() {

 this.age++;

 }

}

Notice that this object is referring to properties that are **undefined**. It does not include **lastName**, **firstName** or **age** properties, therefore calling these methods will not produce very useful results:

> person.getFullName()

"undefined undefined"

We will now write an **extends** function that accepts this object as a parameter, and returns a new object with this object set as its prototype:

function extend(obj) {

 function E(){};

 E.prototype = obj;

 return new E();

}

This code may look unfamiliar or mysterious. That is because this function is taking advantage of a special type of function we have not seen before called a constructor function.

The first line of this function declares a function called **E**:

function E(){};

By convention constructor functions always start with a capital letter. This is because there is nothing different between a regular function, a method, and a constructor function except (you guessed it) the meaning of the special **this** variable, and the fact that a constructor function implicitly returns a new object.

On the next line, we set the prototype for the **E** constructor function:

E.prototype = obj;

This means that anytime we use the **E** constructor function to create a new object, it will implicitly set the passed in object to be its prototype, and therefore it will have access to all the functionality defined in that prototype.

Constructor functions are the closest JavaScript has to classes. They must be called with the **new** keyword, and as a result will construct an object that is implicitly returned when the constructor finishes. Before finishing our look at the **extends** function, it is worth learning a little more about constructor functions.

Within a constructor function you can use the special **this** variable to set properties on the implicitly created object. For instance, if we had written the following constructor function:

> function Person(firstName, lastName) {

 this.firstName = firstName;

 this.lastName = lastName;

}

you could then construct a person as follows:

> p = new Person('John', 'Smith');

The constructor implicitly returns the newly created object even though it has no return statement. This **p** variable will therefore contain a reference to an object with the appropriate name properties set.

If you omit the **new** keyword when calling a constructor function, it will act like any other function. This is why constructor functions start with a capital letter by default: to remind you to add the **new** keyword.

Omitting the **new** keyword is actually far worse than it may look. Inside the constructor function you have access to a **this** variable that refers to the newly constructed object. If you omit the **new** keyword **this** will refer to what it does in normal functions: the **window** object.

//

The **window** object is a global object within the browser that contains information about the document. When JavaScript is used outside the browser an alternative global object is provided in place of **window**.

This is a huge source of bugs because the code appears to work, but all instances of the class will overwrite the same variables in the global namespace.

> p = Person('John', 'Smith');

The value of **p** is now **undefined**, since the function does not have a return value, but the **window** object has had two new properties added to it:

> window.firstName

John

> window.lastName

Smith

This is one of the reasons I recommend against constructor functions except in controlled environments such as the **extends** function.

//

Programmers who have experience with other object orientated languages are always initially drawn to constructor functions. They provide a certain familiarity, and appear to provide a class based typing system. Programmers are then invariably annoyed when these classes do not provide the same features they are used to with classes in other languages.

Finally, we can look at the final line of the **extends** function:

return new E();

This is simply returning a new object created by the **E** constructor. Since we only need to write the **extends** function once however, we will not forget the **new** keyword.

You can now use the **extends** function to create some objects:

> p1 = extend(person)

> p1.firstName = 'John'

> p1.lastName = 'Smith'

> p1.age = 34

 //

As the examples above illustrate, semi colons are actually optional in JavaScript. It is highly recommended that all statements are terminated with semi-colons however, since JavaScript will automatically add them when they are missing, and in some cases they will not be added where they are expected. This is another common source of hard to find bugs, for instance, the following function returns **undefined**:

function a() {

 return

 {a:1};

}

Once the instance is populated with the appropriate properties, you can use the methods defined on the prototype:

> p1.getFullName()

"John Smith"

Notice that the references to **this** inside the prototype now refer to the object itself and the full name of the person is returned.

JavaScript is a type of object orientated language called a “prototype-based language”. Prototype languages use existing objects as the basis for new objects, which are then modified to meet their specific needs. The fact that JavaScript also supports syntax for creating Class-like structures sometimes obscures this fact.

Prototype-based languages look unfamiliar to most people who have used other classical object orientated languages such as C++ or Java. The approach is very powerful however, and the examples in this book will favour prototypes to classes as the basic approach to code reuse.

Prototype-based object orientated languages are relatively rare, which is why they are so unfamiliar. Other than languages based on JavaScript, it is unlikely most software engineers will ever encounter another prototype-based language. In order to succeed with JavaScript it is important to be aware of its fundamental nature however, and embrace it rather than fight it.

## Functional Programming

Understanding JavaScript begins with the realisation that it is a prototype-based object orientated language. The next phase in understanding JavaScript comes from realising that it is also a functional-orientated programming language.

//

There is no standard definition for what makes a programming language a “functional programming language”. This section will highlight the aspects of JavaScript that make it a functional programming language without addressing arguments against considering it a functional language.

JavaScript has first class functions. This means variables can contain references to functions, and functions can be passed as arguments to other functions.

 The following is an example of assigning a function to a variable:

> f = function() {

 console.log('Hello World');

 }

The variable **f** now contains a reference to a function. If we execute:

> typeof f

The result will be

“function”

Strictly speaking this is incorrect: functions are objects, and have methods just like other objects. As we saw earlier, functions are not considered a distinct data type.

//

Following this precedence, you may expect that the **typeof** an array would be **array**: it is not, it will return **object**.

Once you have a reference to a function, you can execute it by appending **()** to its name:

> f()

Hello World

First class functions are a powerful concept. As another example, consider this as a stand-alone function assigned to a variable:

> f2 = function(i) {

     return i % 2 == 0;

    }

This function accepts a number, and returns true if the number is even, and false if it is odd:

> f2(9)

false

> f2(10)

true

Now, create an array of all the numbers between 1 and 10, and assign that to variable **a**:

a = [1,2,3,4,5,6,7,8,9,10]

As mentioned earlier, JavaScript arrays are objects, and therefore they contain methods. One of the methods supported by arrays is **filter**. This method accepts a function as a parameter; the **filter** method will then pass each member of the array in turn to the function provided, and at the end return a new array containing each value that evaluated to true in that function. This means we can create a new array with all the even numbers as follows:

> a.filter(f2)

[2, 4, 6, 8, 10]

//

The **filter**, **map** and **reduce** methods referred to in these examples were only added to JavaScript in ECMAScript version 5\. As such they are not natively supported in older browsers, including IE8\. They can however easily be added as polyfills.

Of course, we did not need to declare the function first, we could have written the same functionality as follows:

> a.filter(function(i) {return i % 2 == 0})

[2, 4, 6, 8, 10]

The function passed to the **filter** method in this case is an anonymous function (i.e. a function without a name). This function only exists for the duration of the filter call, and cannot be reused.

Let’s now imagine a more complex example. Suppose we want to take an array, multiply each element by itself, and then return the result if it is even.

JavaScript arrays also have a method called **map**. Like **filter**, **map** passes each member of the array to a function, and then returns a new array with the result of these function calls.

 //

It is important to note that these methods are not altering the original array; they are creating a new array with the appropriate entries. This is an important paradigm, since it means the method call will not impact any other code that has a reference to the original array.

In order to multiply each member by itself, we could execute:

> a.map(function(i) {return i*i})

[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

In order to return the even numbers amongst these, we could therefore perform the **filter** method on the array returned by the **map** call:

a.map(function(i) {return i*i}).filter(function(i) {return i % 2 == 0})

[4, 16, 36, 64, 100]

Finally, let’s imagine that we want to sum the values in the final array. **Arrays.prototype** supports a **reduce** method for this. This method is slightly more complex than **map** and **filter**, since the method must keep track of the current count. This method will pass the following to our function for each member in the array:

1\. The current result.

2\. The value of the current member of the array.

3\. The index that member has in the array (starting at 0).

4\. The array itself.

 //

The methods **filter**, **map** and **reduce** are not unique to JavaScript. These are important operators for dealing with data sets in many languages, and were popularised by Google’s map/reduce algorithm for indexing web pages.

[http://static.googleusercontent.com/external_content/untrusted_dlcp/research.google.com/en//archive/mapreduce-osdi04.pdf](http://static.googleusercontent.com/external_content/untrusted_dlcp/research.google.com/en/archive/mapreduce-osdi04.pdf)

In order to see this working, execute the following:

[1,2,3,4,5].reduce(function(total, currentValue, index, array) {

console.log('Current value is ' + currentValue);

console.log('Total is ' + total);

return total += currentValue;

});

This will print the following:

Current value is 2

Total is 1

Current value is 3

Total is 3

Current value is 4

Total is 6

Current value is 5

Total is 10

15

The total value is initially set to the value of the first element in the array. Each member is then passed to the function, and we add this to the total. At the end, the total is 15, which is returned from the **reduce** method.

We can now write our final version of the code with **map**, **filter** and **reduce** chained together, each using the result of its predecessor as its input:

> a.map(function(i) {return i*i})

 .filter(function(i) {return i % 2 == 0})

 .reduce(function(total, currentValue, index, array) { return total += currentValue; })

220

Functions that accept other functions allow software engineers to write extremely concise code. In many strongly typed Object Orientated languages, such as Java, functions are not first class language constructs. In order to write a function (or method), you first must construct a class to contain it, and then an object from that class. Although Java allows anonymous classes, the syntax for performing the examples above would be nowhere near as concise.

## Function Arguments

JavaScript does not check that the arguments passed to a function match the signature of the function. For instance:

• You can pass more arguments to a function than it expects; in this case the extra arguments will be ignored.

• You can pass fewer arguments to a function than it expects; in this case the arguments are assigned the value of **undefined**.

 //

A side effect of this is that it is not possible to overload functions or methods in JavaScript. In many languages it is possible to define multiple versions of the same function, but with different parameter lists (or signatures). The compiler then determines the correct version to invoke based on the parameters provided.

In order to achieve this in JavaScript the functions must be given different names, otherwise JavaScript cannot determine the correct version to invoke.

There are legitimate reasons to pass fewer arguments to a function than it expects. You may be happy for these arguments to be **undefined**.

There are also legitimate reasons to pass more arguments to a function than its signature specifies. For instance, consider a function that accepts an arbitrary number of arguments, and adds them all together.

Any time a function is invoked a variable called **arguments** is available inside the function. This is an array containing all the variables passed to the function. This means we can defined an **add** function as a function that accepts no parameters, but instead uses the **arguments** array:

> function add() {

 var result = 0;

 for (var i = 0; i < arguments.length; i++) {

 result += arguments[i];

 }

 return result;

}

This function uses a standard for-loop to iterate through all the arguments, and simply adds them to a **result** variable that is returned at the end.

This can then be invoked as follows:

> add(6,2,9,20)

37

Naturally, it is especially important to add comments to functions that accept variable numbers of parameters; otherwise it can be difficult to work out how to invoke them.

## Closures

Closures are another of the most important features of JavaScript. When we continue the development of the sample web application we will make extensive use of closures.

Closures can be a difficult concept to explain, so it is useful to learn about them through examples.

Consider the following code:

> function f() {

 var i = 0;

 return ++i;

}

//

This example uses ++i rather than i++. This means that the value is incremented (has 1 added to it with the ++ operator) before it is returned. If this had used i++, the value would be returned and then incremented by 1 – which is not the same thing.

This code defines a function **f**. Inside this function a private variable is declared and initialised to 0\. This variable is then incremented by 1 and returned.

If we perform repeated calls to this function, it is not surprising that it will always return 1:

> f()

1

> f()

1

> f()

1

Each time this function is executed it declares a new variable, which is scoped to the function. The keyword **var** is used to indicate that the variable is function scoped rather than global scoped. The newly created variable has 1 added to it, and the value is returned. When the function ends the variable is destroyed.

If we try to access the variable **i** outside the function an error will be generated:

> i

ReferenceError: i is not defined

The error is not because the variable is being accessed outside the function; it is because it does not exist anymore. Function variables are placed on a stack when the function begins execution, and when the function completes they are popped off the stack and destroyed.

Programming languages use this approach for good reason. This ensures the space allocated to variables inside functions is automatically reclaimed when the function completes. This ensures against out of memory errors.

On the face of it this all seems to make sense. There are however good reasons why we may wish to access function scoped variables even after functions complete. We do not however want to make these variables global variables (as we could do by omitting the **var** keyword on the variable declaration). This can be achieved via closures.

Consider the following code:

> function f2() {

 var i = 0;

 return function() {

 return ++i;

 };

}

This function does the following:

1\. Declares a function scoped variable called **i** initialised to the value 0.

2\. Returns a function that will increment this variable when invoked.

We can therefore call this function and assign the result (which is a function) to a variable:

> incrementer = f2()

Based on our explanation of the function scoped variables above, you would expect that the variable declared inside **f2** would be destroyed when the function call **f2** completed. Therefore, when we invoke the function that was returned from **f2**, there would be no **i** variable for it to access (since it has been destroyed). This is not the case:

> incrementer()

1

> incrementer()

2

> incrementer()

3

When the anonymous function was defined inside function **f2** it “closed” over its environment as it existed at that point of time, and kept a copy of that environment. Since the variable **i** was accessible when the function was declared, it is still available when the function is invoked. JavaScript has realised that the anonymous function refers to the variable **i**, and that this function has not been destroyed, and therefore it has not destroyed the **i** variable it depends on.

If we construct another function using the same mechanism:

> incrementer2 = f2()

This will also have access to a variable called **i** as it existed when the function was created, but it will be a new version of that variable:

> incrementer2()

1

> incrementer2()

2

> incrementer2()

3

This may look like a simple quirk of the language, but it is an incredibly powerful feature.

JavaScript by default is not very good at hiding data. It is not possible to declare properties as private inside an object. For instance, consider the following object that provides the same basic “incrementer” functionality:

> obj1 = {i: 0,

 increment: function() {

 return ++this.i;

 }

}

This appears to work correctly:

> obj1.increment()

1

> obj1.increment()

2

> obj1.increment()

3

There is a potential problem here though. Anyone with a reference to this object can change the current value of **i**:

> obj1.i = 20

Once this is done, the next call to increment the number will jump to 21:

> obj1.increment()

21

This may be a big problem; it may be an even bigger problem if the following occurs:

> obj1.i = "hello world"

Now the next call will return the following:

> obj1.increment()

NaN

The closure-based implementation solves this problem. There is no way to modify the value of **i**, or impact the value returned by the function. If a call to the function returns 5, the next call to the function is guaranteed to return 6.

Data hiding (or encapsulation) is an enormously important concept when writing large applications. It allows us to write code modules with well-defined public interfaces (or APIs), while hiding (or encapsulating) the internal logic and state from the caller. This reduces bugs, since code cannot accidentally corrupt the state of the module.

The approach used to implement the closure-based incrementer is a representation of a design pattern. A design pattern is a commonly used, reusable approach to solving a common problem. This approach is referred to as the **module** design pattern.

The module design pattern is also commonly implemented by returning an object rather than a function. This allows the object to use private variables for its private properties and functions, while still exposing a series of public properties and methods. The functionality above can be rewritten as follows:

> function createIncrementer() {

 var i = 0;

 return {

 increment: function() {

 return ++i;

 }

 };      

 }

We can now create an incremeter object:

> obj2 = createIncrementer();

Once created, we now call the increment method, and consistently receive a value incremented by 1:

> obj2.increment()

1

> obj2.increment()

2

> obj2.increment()

3

We can attempt to change the internal state of the object by calling the following:

> obj2.i = 10

but all this will do is create a new property on the object:

> obj2.i

10

This is not the same property that is being used as the incrementing state of the object:

> obj2.increment()

4

> obj2.increment()

5

> obj2.increment()

6

## Scope and “this”

In order to fully understand a language, you must understand its approach to scoping variables. Understanding scope tells us when various variables are available within the program, and which variable is used if there are multiple variables available with the same name.

Let’s start with a simple example:

> function getNumber() {

     num = 10;

     return num;

 }

This is a function that always returns the same number: 10.

> getNumber()

10

> getNumber()

10

When this function finishes execution, it may seem that the variable **num** would no longer be available based on our discussion of function scoped variables earlier in this chapter. This is not the case:

> num

10

This is because we forgot to use **var** when declaring the variable. If we had done the following, the variable would not have existed after the function completed:

> function getNumber() {

     **var** num = 10;

   return num;

 }

Due to the fact **var** was omitted; the **num** variable was added as a property to the object represented by a special variable called **this**. Within a function, **this** refers to a special object called **window**. You can see this by typing **this** in the console:

> this

Window {top: Window, window: Window, location: Location, external: Object, chrome: Object…}

 //

Strictly speaking this is not true: it is only true of functions executed in a browser environment. JavaScript written in server side applications will use a different object than **window** for the global scope.

In fact, this function could have been written as follows:

> function getNumber() {

     this.num = 10;

   return this.num;

 }

The **window** object is a global object that contains information about the browser environment, but is also the object that properties are added to by default within functions. The **window** object is available to any code in the web page (including external libraries), and therefore it is referred to as global scope.

Adding properties to the **window** object is dangerous in any moderately sized application. Since the global properties can be read and written by any piece of code, there is a significant possibility that other code will accidentally overwrite your variables.

//

If you do need to create global variables (and the sample application will create a couple), it is often a good idea to create a single object in the **window** to hold all the variables for your application:

> window.THEAPP = {};

> window.THEAPP.myproperty = 'myvalue ';

As mentioned earlier, the **this** variable takes on a different meaning inside an object’s method:

> obj = { num: 10,

 add: function(num2) {

 this.num += num2;

 return this.num;

 }

 }

This is a very simple object that contains a **num** property initialized to 10\. It also exposes an **add** method that adds the parameter passed in to this property and returns the result:

> obj.add(10)

20

> obj.add(10)

30

You will notice that **this** inside an object method refers not to the global **window** object, but to the object itself.

Let’s take this one step further:

> obj = { num: 10,

 add: function(num2) {

 helper = function(num2) {

 this.num += num2;

 return this.num;

 }

 return helper(num2);

 }

}

In this example we are declaring a function inside the object’s method. Although this is a contrived example, the approach used here is common (especially for event listeners).

Intuitively it looks like this code should work: the helper function is using **this.num** to access the **num** property on the object. Unfortunately this code does not work as expected:

> obj.add(20)

NaN

The problem can be seen if we add some logging to the code:

> obj = { nums: 10,

 add: function(num2) {

 console.log('Outer this ' + this)

 helper = function(num2) {

 console.log('Inner this ' + this)

 this.num += num2;

 return this.num;

 }

 return helper(num2);

 }

}

If you execute this now, you will see the following output:

> obj.add(20)

Outer this [object Object]

Inner this [object Window]

NaN

Surprisingly the **this** inside the inner function has reverted from being the object to being the **window**. This is considered by most as a bug in the language, but it is a bug that will not be rectified since it would break legacy code.

The common way to avoid this issue is as follows:

> obj = { num: 10,

 add: function(num2) {

 **var that = this;**

 helper = function(num2) {

 **that**.num += num2;

 return **that**.num;

 }

 return helper(num2);

 }

}

Before entering the inner function we declare a variable called **that**, and set it to refer to the **this** object (the object itself). Inside the inner function we then access the **that** variable rather than the **this** variable.

So far we have seen two different definitions of the **this** variable. In both these cases **this** was implicitly defined by the programming environment. It is also possible to explicitly specify the object that should be used to represent **this**. In order to see this in action we will define a new object that adds two properties together:

> adder = {

 num1: 10,

 num2: 20,

 add: function() {

 return this.num1+this.num2;

 }

}

If we call the **add** method, the two properties will be added together and returned:

> adder.add()

30

As mentioned earlier, functions and methods are actually objects in JavaScript, and therefore they support their own methods. These are defined on **Function.prototype**, (so naturally you can also add your own methods to functions). One of the methods **Function.prototype** supports is **apply**, which allows an alternative environment to be provided for the **this** variable:

> adder.add.apply({num1:30,num2:40})

70

The parameter passed to **apply** is an object containing the appropriate properties required by the function. This approach can be used to replace the value of **this** in standalone functions and object methods.

Another method provided to **Function.prototype** is **bind**. Rather than executing the function using the object passed in as the environment, **bind** returns a new function that permanently binds the object passed in as the **this** variable for the function:

> add2 = adder.add.bind({num1:30,num2:40})

It is now possible to execute the function as follows:

> add2()

70

We can use this method to solve the problem we encountered with inner functions in this example:

> obj = { nums: 10,

  add: function(num2) {

    console.log('Outer this ' + this)

  helper = function(num2) {

 console.log('Inner this ' + this)

 this.num += num2;

  return this.num;

 }

 return helper(num2);

 }

}

This can be rewritten as follows:

> obj = { num: 10,

 add: function(num2) {

 console.log('Outer this ' + this)

 helper = function(num2) {

 console.log('Inner this ' + this)

 this.num += num2;

 return this.num;

 }**.bind(this);**

 return helper(num2);

 }

}

Executing this now provides the correct result:

> obj.add(20)

Outer this [object Object]

Inner this [object Object]

30

Earlier in this book I mentioned a forth way **this** could be defined: inside constructor functions. Within a constructor function **this** refers to the implicitly created object, provided the function was invoked with the **new** modifier. Without the **new** modifier, **this** becomes the global object again.

It is worth mentioning one more limitation of JavaScript before completing this section. JavaScript does not support block level scope. This can be seen in the following example:

function test() {

 var a = [1,2,3,4];

 for (var i = 0; i < a.length; i++) {

 var a = i;

 console.log(a);

 } 

 console.log(a);

}

The inner block here uses the same variable name **a** as is used in the outer block. In most programing languages the two variables named **a** would be different, because they are defined in different blocks of code. JavaScript does not support block level scoping: it only supports function level scoping, therefore the line:

var a = i;

overwrites the variable defined here:

var a = [1,2,3,4];

In addition to being limited to functional scoping, JavaScript employs another technique for all the variables defined within a function called “hoisting”. Before explain “hoisting”, try to work out why only one of these two functions produces an error when executed:

> function testLocal() {

 console.log(j);

 var j = 10;

}

> function testGlobal() {

 console.log(j);

 j = 10;

}

Intuitively it looks like both of these functions will fail because they are attempting to access a variable before it is declared. In fact, when JavaScript functions are executed they first look for all function scoped variables that will be declared anywhere in the function. These are then “hoisted” to the top of the function.

These function variables remain undefined until explicitly assigned a value, but they do exist as undefined variables. Globally defined variables are not hoisted, and therefore the two functions produce different results:

> testLocal()

undefined

> testGlobal()

ReferenceError: j is not defined

For this reason it is always best practice to declare function scoped variables at the top of the function, since this is what the language will automatically do anyway.

## Exception Handling

We will discuss approaches to implementing application wide exception handling later in this book. For now, it is worth emphasising that JavaScript does support “Java-style” exception handling, but without the benefits provided by static typing.

Any code can throw an exception without declaring that it will throw that exception. Any data type can be thrown as an exception, although it is common practice to throw an object with a code and a message. This function throws an exception if it is passed an even number:

> function dontLikeEven(num) {

 if (num % 2 == 0) {

 throw {code: 'even_number',

 message: 'This function cannot be called with even numbers'

     };

 }

 }

It is also possible to catch an exception, and provide logic to handle the failure scenario:

> function passNumber(num) {

 try {

 dontLikeEven(num);

 } catch(e) {

 console.log(e.code+':'+e.message);

 console.log('Retying with ' + (num+1));

 dontLikeEven(num+1);

 }

}

In order to catch exceptions, a **try** block must be declared in the code. Only errors that occur in this block will be caught. A **catch** block must be provided at the end of the **try** block, and this will be passed any exception that occurs in the block.

The function above produces the following output if it is invoked with an even number:

> passNumber(2)

even_number:This function cannot be called with even numbers

Retying with 3

Unlike Java, only a single **catch** block can be provided, and this block must then determine the cause of the exception. If required the **catch** block can throw another exception.

Try/catch blocks should be provided to catch application logic exceptions, not to hide coding bugs. We will explore this topic further later in the book.

## Threading

Unlike most languages, JavaScript does not offer programmers an approach for utilizing multiple threads.

Within the browser environment, all JavaScript code executes on a single thread, and this is also the thread that the browser utilizes to update the window. This means that if you make changes to the DOM, and then continue to utilize the thread to perform any computation, your DOM changes will not be applied until you finish this processing.

Browsers do allow documents in different tabs to utilize different threads: this is possible because the tabs do not interact with one another.

The browser manages the single thread with an event queue. Each time an event occurs, be it a browser initiated event such as resizing the window, a user initiated even such as clicking a button, or a JavaScript initiated event such as a timer executing a function, the event is added to a queue. The browser then processes these events sequentially and does not begin processing a new event until all the events ahead of it have finished processing.

This threading model can cause issues, since it does not prioritize the processing of events based on their source. In real-world applications it is often more important to respond to user based events quickly, even if that means temporarily interrupting a computational process currently executing.

HTML5 has addressed this issue to a degree with an API called Web Workers. These will be introduced later in the book, but they are not a general purpose solution to threading issues, since they contain numerous limitations.

JavaScript does provide a mechanism to alleviate some of the issues inherent in the single thread model with the **setTimeout** function defined in the language. The **setTimeout** function allows code to execute at a delayed interval.

In order to see **setTimeout** in action, we will first define a function that we wish to execute at a delayed interval:

> writer = function() {

 for (var i = 0; i < 10; i++) {

 console.log('Row '+i);

 }

}

Next we will ask the browser thread to execute this with a delay of 5000 milliseconds:

> setTimeout(writer, 5000)

If you execute this you should see the execution begin after approximately 5 seconds. JavaScript executes this by encapsulated the function call in an event and adding that event to the event queue after 5 seconds. It will only execute when it gets to the front of the event queue.

Before performing a long running calculation, it is sometimes useful to yield control back to the browser to ensure any other events that are waiting can be processed (particularly user driven events) first, and therefore stops the application from appearing to “lock-up”.

Your processing can be encapsulated in a call to **setTimeout** with a very small delay (10 milliseconds for instance). This will guarantee that you go to the back of the event queue (and any pending events will occur), but still will not result in any unnecessary delay if there are no other events waiting to run.

The **setTimeout** function can also be used to yield control back to the browser during a long running task. If you were to perform a computation that took 10 seconds, by default you would not be interrupted during this period, so all other events would queue up behind you. Instead, if there is a way of breaking the computation up, you can choose a point where you wish to yield, and ask the next portion of the algorithm to run by calling **setTimeout** with a delay of 10 milliseconds.

If this was done every 100 milliseconds, it is unlikely the user would notice that there was a long running computational process executing on the same thread.

The main challenge in achieving this is pausing and resuming the computation. It will typically be necessary to store the current state of the algorithm, and pass this to the function that will continue the processing.

**setTimeout** has a companion function called **setInterval**. Unlike **setTimeout** which causes a function to be executed once, **setInterval** causes a function to be executed indefinitely with a given delay between executions. The following is a simple example:

> setInterval(function() {

 console.log('hello world');

 }, 1000)

This will cause “hello world” to be printed to the console every second indefinitely. setInterval is very useful for implementing background jobs that need to perform operations periodically.

As with **setTimeout**, **setInterval** generates events that are placed on the event queue. Therefore they can only run once they get to the front of the event queue.

Although **setTimeout** and **setInterval** are rudimentary compared to the threading libraries common in most programming languages, it is important to have a strong grasp of what they do, and when you should use them. They do allow many of the issues associated with the single thread model (particularly unresponsive GUIs, and slow reactions to user events) to be alleviated.

## Conclusion

JavaScript is best described as a multi-paradigm language: it supports the following programming paradigms:

• Functional programming

• Imperative programming

• Classical object orientated programming

• Prototype-based programming

Due to its multi-paradigm nature, JavaScript is enormously flexible. The danger with JavaScript’s multi-paradigm nature is that it allows programmers to see in it what they want, without taking into account which of these paradigms are JavaScript’s true strengths.

This chapter has presented the case that JavaScript should be best thought of as a prototype-based, functional programming language.

JavaScript’s approach to functions is a particular strength. First class functions are a powerful concept, and allow for concise, reusable code.

JavaScript’s approach to prototyping is perhaps its least understood feature, and while unusual as a design choice in the language, is another key strength of the language.

Finally, JavaScript has more than its fair share of quirks and design bugs. The key to circumventing these is to understand they exist. These quirks can be easily worked around by those who understand them, but can cause annoying bugs for those who don’t.