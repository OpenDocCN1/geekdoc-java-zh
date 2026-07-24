![](Images/cover00121.jpeg)

Copyright © All rights reserved

No part of this book may be reproduced, or stored in a retrieval system, or transmitted in any form or by any means, electronic, mechanical, photocopying, recording, or otherwise, without express written permission of the publisher.

I would like to dedicate the book to the students who will be using it. I wish you future career success and hope you never stop learning.

TABLE OF CONTENT

[Functional Programming - Overview](#part0003.xhtml_id_Toc70077177)

[Functional Programming with Java – Functions](#part0004.xhtml_id_Toc70077178)

[Functional Programming with Java – Composition](#part0005.xhtml_id_Toc70077179)

[Eager vs Lazy Evaluation](#part0006.xhtml_id_Toc70077180)

[Persistent Data Structure](#part0007.xhtml_id_Toc70077181)

[Functional Programming with Java – Recursion](#part0008.xhtml_id_Toc70077182)

[Functional Programming with Java – Parallelism](#part0009.xhtml_id_Toc70077183)

[Optionals and Monads](#part0010.xhtml_id_Toc70077184)

[Functional Programming with Java – Closure](#part0011.xhtml_id_Toc70077185)

[Functional Programming with Java – Currying](#part0012.xhtml_id_Toc70077186)

[Functional Programming with Java – Reducing](#part0013.xhtml_id_Toc70077187)

[Functional Programming - Lambda Expressions](#part0014.xhtml_id_Toc70077188)

[Functional Programming - Default Methods](#part0015.xhtml_id_Toc70077189)

[Functional Programming - Functional Interfaces](#part0016.xhtml_id_Toc70077190)

[Functional Programming - Method References](#part0017.xhtml_id_Toc70077191)

[Constructor References](#part0018.xhtml_id_Toc70077192)

[Functional Programming with Java – Collections](#part0019.xhtml_id_Toc70077193)

[Functional Programming - High Order Functions](#part0020.xhtml_id_Toc70077194)

[Functional Programming - Returning a Function](#part0021.xhtml_id_Toc70077195)

[Functional Programming - First Class Function](#part0022.xhtml_id_Toc70077196)

[Functional Programming - Pure Function](#part0023.xhtml_id_Toc70077197)

[Functional Programming - Type Inference](#part0024.xhtml_id_Toc70077198)

[Exception Handling in Lambda Expressions](#part0025.xhtml_id_Toc70077199)

[Intermediate Methods](#part0026.xhtml_id_Toc70077200)

[Functional Programming - Terminal Methods](#part0027.xhtml_id_Toc70077201)

[Functional Programming - Infinite Streams](#part0028.xhtml_id_Toc70077202)

[Functional Programming - Fixed length Streams](#part0029.xhtml_id_Toc70077203)

# Functional Programming - Overview

In functional programming paradigm, an application is written mostly using pure functions. Here pure function is a function having no side effects. An example of side effect is modification of instance level variable while returning a value from the function.

Following are the key aspects of functional programming.

*   **Functions** − A function is a block of statements that performs a specific task. Functions accept data, process it, and return a result. Functions are written primarily to support the concept of re usability. Once a function is written, it can be called easily, without having to write the same code again and again.

Functional Programming revolves around first class functions, pure functions and high order functions.

*   A **First Class Function** is the one that uses first class entities like String, numbers which can be passed as arguments, can be returned or assigned to a variable.
*   A **High Order Function** is the one which can either take a function as an argument and/or can return a function.
*   A **Pure Function** is the one which has no side effect while its execution.

*   **Functional Composition** − In imperative programming, functions are used to organize an executable code and emphasis is on organization of code. But in functional programming, emphasis is on how functions are organized and combined. Often data and functions are passed together as arguments and returned. This makes programming more capable and expressive.
*   **Fluent Interfaces** − Fluent interfaces helps in composing expressions which are easy to write and understand. These interfaces helps in chaining the method call when each method return type is again reused. For example −

LocalDate futureDate =  LocalDate.now().plusYears(2).plusDays(3);

*   **Eager vs Lazy Evaluation** − Eager evaluation means expressions are evaluated as soon as they are encountered whereas lazy evaluation refers to delaying the execution till certain condition is met. For example, stream methods in Java 8 are evaluated when a terminal method is encountered.
*   Persistent Data Structures

− A persistent data structure maintains its previous version. Whenever data structure state is changed, a new copy of structure is created so data structure remains effectively immutable. Such immutable collections are thread safe.

*   **Recursion** − A repeated calculation can be done by making a loop or using recursion more elegantly. A function is called recursive function if it calls itself.
*   **Parallelism** − Functions with no side effects can be called in any order and thus are candidate of lazy evaluation. Functional programming in Java supports parallelism using streams where parallel processing is provided.
*   **Optionals** − Optional is a special class which enforces that a function should never return null. It should return value using Optional class object. This returned object has method isPresent which can be checked to get the value only if present.

# Functional Programming with Java – Functions

A function is a block of statements that performs a specific task. Functions accept data, process it, and return a result. Functions are written primarily to support the concept of re usability. Once a function is written, it can be called easily, without having to write the same code again and again.

Functional Programming revolves around first class functions, pure functions and high order functions.

*   A **First Class Function** is the one that uses first class entities like String, numbers which can be passed as arguments, can be returned or assigned to a variable.
*   A **High Order Function** is the one which can take a function as an argument and/or can return a function.
*   A **Pure Function** is the one which has no side effect while its execution.

## First Class Function

A first class function can be treated as a variable. That means it can be passed as a parameter to a function, it can be returned by a function or can be assigned to a variable as well. Java supports first class function using lambda expression. A lambda expression is analogous to an anonymous function. See the example below −

public  class  FunctionTester  {

public  static  void main(String[] args)  {

int[] array =  {1,  2,  3,  4,  5};

SquareMaker squareMaker = item -> item * item;

for(int i =  0; i < array.length; i++){

System.out.println(squareMaker.square(array[i]));

}

}

}

interface  SquareMaker  {

int square(int item);

}

### Output

1

4

9

16

25

Here we have created the implementation of square function using a lambda expression and assigned it to variable squareMaker.

## High Order Function

A high order function either takes a function as a parameter or returns a function. In Java, we can pass or return a lambda expression to achieve such functionality.

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

int[] array =  {1,  2,  3,  4,  5};

Function<Integer,  Integer> square = t -> t * t;

Function<Integer,  Integer> cube = t -> t * t * t;

for(int i =  0; i < array.length; i++){

print(square, array[i]);

}

for(int i =  0; i < array.length; i++){

print(cube, array[i]);

}

}

private  static  <T, R>  void  print(Function<T, R>  function, T t )  {

System.out.println(function.apply(t));

}

}

### Output

1

4

9

16

25

1

8

27

64

125

## Pure Function

A pure function does not modify any global variable or modify any reference passed as a parameter to it. So it has no side-effect. It always returns the same value when invoked with same parameters. Such functions are very useful and are thread safe. In example below, sum is a pure function.

public  class  FunctionTester  {

public  static  void main(String[] args)  {

int a, b;

a =  1;

b =  2;

System.out.println(sum(a, b));

}

private  static  int sum(int a,  int b){

return a + b;

}

}

### Output

3

# Functional Programming with Java – Composition

Functional composition refers to a technique where multiple functions are combined together to a single function. We can combine lambda expression together. Java provides inbuilt support using Predicate and Function classes. Following example shows how to combine two functions using predicate approach.

import java.util.function.Predicate;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Predicate<String> hasName = text -> text.contains("name");

Predicate<String> hasPassword = text -> text.contains("password");

Predicate<String> hasBothNameAndPassword = hasName.and(hasPassword);

String queryString =  "name=test;password=test";

System.out.println(hasBothNameAndPassword.test(queryString));

}

}

### Output

true

**Predicate** provides and() and or() method to combine functions. Whereas **Function** provides compose and andThen methods to combine functions. Following example shows how to combine two functions using Function approach.

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Function<Integer,  Integer> multiply = t -> t *3;

Function<Integer,  Integer>  add  = t -> t +  3;

Function<Integer,  Integer>  FirstMultiplyThenAdd  = multiply.compose(add);

Function<Integer,  Integer>  FirstAddThenMultiply  = multiply.andThen(add);

System.out.println(FirstMultiplyThenAdd.apply(3));

System.out.println(FirstAddThenMultiply.apply(3));

}

}

### Output

18

12

# Eager vs Lazy Evaluation

Eager evaluation means expression is evaluated as soon as it is encountered where as lazy evaluation refers to evaluation of an expression when needed. See the following example to under the concept.

import java.util.function.Supplier;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

String queryString =  "password=test";

System.out.println(checkInEagerWay(hasName(queryString)

, hasPassword(queryString)));

System.out.println(checkInLazyWay(()  -> hasName(queryString)

,  ()  -> hasPassword(queryString)));

}

private  static  boolean hasName(String queryString){

System.out.println("Checking name: ");

return queryString.contains("name");

}

private  static  boolean hasPassword(String queryString){

System.out.println("Checking password: ");

return queryString.contains("password");

}

private  static  String checkInEagerWay(boolean result1,  boolean result2){

return  (result1 && result2)  ?  "all conditions passed":  "failed.";

}

private  static  String checkInLazyWay(Supplier<Boolean> result1,  Supplier<Boolean> result2){

return  (result1.get()  && result2.get())  ?  "all conditions passed":  "failed.";

}

}

### Output

Checking name:

Checking password:

failed.

Checking name:

failed.

Here checkInEagerWay() function first evaluated the parameters then executes its statement. Whereas checkInLazyWay() executes its statement and evaluates the parameter on need basis. As && is a short-circuit operator, checkInLazyWay only evaluated first parameter which comes as false and does not evaluate the second parameter at all.

# Persistent Data Structure

A data structure is said to be persistent if it is capable to maintaining its previous updates as separate versions and each version can be accessed and updated accordingly. It makes the data structure immutable and thread safe. For example, String class object in Java is immutable. Whenever we make any change to string, JVM creates another string object, assigned it the new value and preserve the older value as old string object.

A persistent data structure is also called a functional data structure. Consider the following case −

## Non-Persistent way

public  static  Person updateAge(Person person,  int age){

person.setAge(age);

return person;

}

## Persistent way

public  static  Person updateAge(Person pPerson,  int age){

Person person =  new  Person();

person.setAge(age);

return person;

}

# Functional Programming with Java – Recursion

Recursion is calling a same function in a function until certain condition are met. It helps in breaking big problem into smaller ones. Recursion also makes code more readable and expressive.

## Imperative vs Recursive

Following examples shows the calculation of sum of natural numbers using both the techniques.

public  class  FunctionTester  {

public  static  void main(String[] args)  {

System.out.println("Sum using imperative way. Sum(5) : "  + sum(5));

System.out.println("Sum using recursive way. Sum(5) : "  + sumRecursive(5));

}

private  static  int sum(int n){

int result =  0;

for(int i =  1; i <= n; i++){

result = result + i;

}

return result;

}

private  static  int sumRecursive(int n){

if(n ==  1){

return  1;

}else{

return n + sumRecursive(n-1);

}

}

}

### Output

Sum using imperative way. Sum(5) : 15

Sum using recursive way. Sum(5) : 15

Using recursion, we are adding the result of sum of n-1 natural numbers with n to get the required result.

## Tail Recursion

Tail recursion says that recursive method call should be at the end. Following examples shows the printing of a number series using tail recursion.

public  class  FunctionTester  {

public  static  void main(String[] args)  {

printUsingTailRecursion(5);

}

public  static  void printUsingTailRecursion(int n){

if(n ==  0)

return;

else

System.out.println(n);

printUsingTailRecursion(n-1);

}

}

### Output

5

4

3

2

1

## Head Recursion

Head recursion says that recursive method call should be in the beginning of the code. Following examples shows the printing of a number series using head recursion.

public  class  FunctionTester  {

public  static  void main(String[] args)  {

printUsingHeadRecursion(5);

}

public  static  void printUsingHeadRecursion(int n){

if(n ==  0)

return;

else

printUsingHeadRecursion(n-1);

System.out.println(n);

}

}

### Output

1

2

3

4

5

# Functional Programming with Java – Parallelism

Parallelism is a key concept of functional programming where a big task is accomplished by breaking in smaller independent tasks and then these small tasks are completed in a parallel fashion and later combined to give the complete result. With the advent of multi-core processors, this technique helps in faster code execution. Java has Thread based programming support for parallel processing but it is quite tedious to learn and difficult to implement without bugs. Java 8 onwards, stream have parallel method and collections has parallelStream() method to complete tasks in parallel fashion. See the example below:

import java.util.ArrayList;

import java.util.Arrays;

import java.util.List;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Integer[] intArray =  {1,  2,  3,  4,  5,  6,  7,  8  };

List<Integer> listOfIntegers =  new  ArrayList<>(Arrays.asList(intArray));

System.out.println("List using Serial Stream:");

listOfIntegers

.stream()

.forEach(e ->  System.out.print(e +  " "));

System.out.println("");

System.out.println("List using Parallel Stream:");

listOfIntegers

.parallelStream()

.forEach(e ->  System.out.print(e +  " "));

System.out.println("");

System.out.println("List using Another Parallel Stream:");

listOfIntegers

.stream()

.parallel()

.forEach(e ->  System.out.print(e +  " "));

System.out.println("");

System.out.println("List using Parallel Stream but Ordered:");

listOfIntegers

.parallelStream()

.forEachOrdered(e ->  System.out.print(e +  " "));

System.out.println("");

}

}

### Output

List using Serial Stream:

1 2 3 4 5 6 7 8

List using Parallel Stream:

6 5 8 7 3 4 2 1

List using Another Parallel Stream:

6 2 1 7 4 3 8 5

List using Parallel Stream but Ordered:

1 2 3 4 5 6 7 8

# Optionals and Monads

Monad is a key concept of Functional Programming. A Monad is a design pattern which helps to represent a missing value. It allows to wrap a potential null value, allows to put transformation around it and pull actual value if present. By definition, a monad is a set of following parameters.

*   **A parametrized Type** − M<T>
*   **A unit Function** − T −> M<T>
*   **A bind operation** − M<T> bind T −> M<U> = M<U>

## Key Operations

*   **Left Identity** − If a function is bind on a monad of a particular value then its result will be same as if function is applied to the value.
*   **Right Identity** − If a monad return method is same as monad on original value.
*   **Associativity** − Functions can be applied in any order on a monad.

## Optional Class

Java 8 introduced Optional class which is a monad. It provides operational equivalent to a monad. For example **return** is a operation which takes a value and return the monad. Optional.of() takes a parameters and returns the Optional Object. On similar basis , **bind** is operation which binds a function to a monad to produce a monad. Optional.flatMap() is the method which performs an operation on Optional and return the result as Optional.

*   **A parametrized Type** − Optional<T>
*   **A unit Function** − Optional.of()
*   **A bind operation** − Optional.flatMap()

### Example − Left Identity

Following example shows how Optional class obeys Left Identity rule.

import java.util.Optional;

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Function<Integer,  Optional<Integer>> addOneToX

= x −>  Optional.of(x +  1);

System.out.println(Optional.of(5).flatMap(addOneToX)

.equals(addOneToX.apply(5)));

}

}

### Output

true

### Example − Right Identity

Following example shows how Optional class obeys Right Identity rule.

import java.util.Optional;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

System.out.println(Optional.of(5).flatMap(Optional::of)

.equals(Optional.of(5)));

}

}

### Output

true

### Example - Associativity

Following example shows how Optional class obeys Associativity rule.

import java.util.Optional;

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Function<Integer,  Optional<Integer>> addOneToX

= x −>  Optional.of(x +  1);

Function<Integer,  Optional<Integer>> addTwoToX

= x −>  Optional.of(x +  2);

Function<Integer,  Optional<Integer>> addThreeToX

= x −> addOneToX.apply(x).flatMap(addTwoToX);

Optional.of(5).flatMap(addOneToX).flatMap(addTwoToX)

.equals(Optional.of(5).flatMap(addThreeToX));

}

}

### Output

true

# Functional Programming with Java – Closure

A closure is a function which is a combination of function along with its surrounding state. A closure function generally have access to outer function's scope. In the example given below, we have created a function getWeekDay(String[] days) which returns a function which can return the text equivalent of a weekday. Here getWeekDay() is a closure which is returning a function surrounding the calling function's scope.

Following example shows how Closure works.

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

String[] weekDays =  {"Monday",  "Tuesday",  "Wednesday",  "Thursday",

"Friday",  "Saturday",  "Sunday"  };

Function<Integer,  String> getIndianWeekDay = getWeekDay(weekDays);

System.out.println(getIndianWeekDay.apply(6));

}

public  static  Function<Integer,  String> getWeekDay(String[] weekDays){

return index -> index >=  0  ? weekDays[index %  7]  :  null;

}

}

### Output

Sunday

# Functional Programming with Java – Currying

Currying is a technique where a many arguments function call is replaced with multiple method calls with lesser arguments.

See the below equation.

(1  +  2  +  3)  =  1  +  (2  +  3)  =  1  +  5  =  6

In terms of functions:

f(1,2,3)  = g(1)  + h(2  +  3)  =  1  +  5  =  6

This cascading of functions is called currying and calls to cascaded functions must gives the same result as by calling the main function.

Following example shows how Currying works.

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Function<Integer,  Function<Integer,  Function<Integer,  Integer>>>

addNumbers = u -> v -> w -> u + v + w;

int result = addNumbers.apply(2).apply(3).apply(4);

System.out.println(result);

}

}

### Output

9

# Functional Programming with Java – Reducing

In functional programming, reducing is a technique to reduce a stream of values to a single result by apply a function on all the values. Java provides reduce() function in a Stream class from Java 8 onwards. A stream has inbuilt reducing methods like sum(), average(), count() as well which works on all elements of the stream and returns the single result.

Following example shows how Reducing works.

import java.util.stream.IntStream;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

//1 * 2 * 3 * 4 = 24

int product =  IntStream.range(1,  5)

.reduce((num1, num2)  -> num1 * num2)

.orElse(-1);

//1 + 2 + 3 + 4 = 10

int sum =  IntStream.range(1,  5).sum();

System.out.println(product);

System.out.println(sum);

}

}

### Output

24

10

# Functional Programming - Lambda Expressions

Lambda expressions are introduced in Java 8 and are touted to be the biggest feature of Java 8\. Lambda expression facilitates functional programming, and simplifies the development a lot.

## Syntax

A lambda expression is characterized by the following syntax.

parameter -> expression body

Following are the important characteristics of a lambda expression.

*   **Optional type declaration** − No need to declare the type of a parameter. The compiler can inference the same from the value of the parameter.
*   **Optional parenthesis around parameter** − No need to declare a single parameter in parenthesis. For multiple parameters, parentheses are required.
*   **Optional curly braces** − No need to use curly braces in expression body if the body contains a single statement.
*   **Optional return keyword** − The compiler automatically returns the value if the body has a single expression to return the value. Curly braces are required to indicate that expression returns a value.

## Lambda Expressions Example

Create the following Java program using any editor of your choice in, say, C:\> JAVA.

### Java8Tester.java

public  class  Java8Tester  {

public  static  void main(String args[])  {

Java8Tester tester =  new  Java8Tester();

//with type declaration

MathOperation addition =  (int a,  int b)  -> a + b;

//with out type declaration

MathOperation subtraction =  (a, b)  -> a - b;

//with return statement along with curly braces

MathOperation multiplication =  (int a,  int b)  ->  {  return a * b;  };

//without return statement and without curly braces

MathOperation division =  (int a,  int b)  -> a / b;

System.out.println("10 + 5 = "  + tester.operate(10,  5, addition));

System.out.println("10 - 5 = "  + tester.operate(10,  5, subtraction));

System.out.println("10 x 5 = "  + tester.operate(10,  5, multiplication));

System.out.println("10 / 5 = "  + tester.operate(10,  5, division));

//without parenthesis

GreetingService greetService1 = message ->

System.out.println("Hello "  + message);

//with parenthesis

GreetingService greetService2 =  (message)  ->

System.out.println("Hello "  + message);

greetService1.sayMessage("Mahesh");

greetService2.sayMessage("Suresh");

}

interface  MathOperation  {

int operation(int a,  int b);

}

interface  GreetingService  {

void sayMessage(String message);

}

private  int operate(int a,  int b,  MathOperation mathOperation)  {

return mathOperation.operation(a, b);

}

}

### Verify the Result

Compile the class using **javac** compiler as follows −

C:\JAVA>javac Java8Tester.java

Now run the Java8Tester as follows −

C:\JAVA>java Java8Tester

It should produce the following output −

10 + 5 = 15

10 - 5 = 5

10 x 5 = 50

10 / 5 = 2

Hello Mahesh

Hello Suresh

Following are the important points to be considered in the above example.

*   Lambda expressions are used primarily to define inline implementation of a functional interface, i.e., an interface with a single method only. In the above example, we've used various types of lambda expressions to define the operation method of MathOperation interface. Then we have defined the implementation of sayMessage of GreetingService.
*   Lambda expression eliminates the need of anonymous class and gives a very simple yet powerful functional programming capability to Java.

## Scope

Using lambda expression, you can refer to any final variable or effectively final variable (which is assigned only once). Lambda expression throws a compilation error, if a variable is assigned a value the second time.

### Scope Example

Create the following Java program using any editor of your choice in, say, C:\> JAVA.

Java8Tester.java

public  class  Java8Tester  {

final  static  String salutation =  "Hello! ";

public  static  void main(String args[])  {

GreetingService greetService1 = message ->

System.out.println(salutation + message);

greetService1.sayMessage("Mahesh");

}

interface  GreetingService  {

void sayMessage(String message);

}

}

### Verify the Result

Compile the class using **javac** compiler as follows −

C:\JAVA>javac Java8Tester.java

Now run the Java8Tester as follows −

C:\JAVA>java Java8Tester

It should produce the following output −

Hello! Mahesh

# Functional Programming - Default Methods

Java 8 introduces a new concept of default method implementation in interfaces. This capability is added for backward compatibility so that old interfaces can be used to leverage the lambda expression capability of Java 8.

For example, 'List' or 'Collection' interfaces do not have 'forEach' method declaration. Thus, adding such method will simply break the collection framework implementations. Java 8 introduces default method so that List/Collection interface can have a default implementation of forEach method, and the class implementing these interfaces need not implement the same.

## Syntax

public interface vehicle {

default void print() {

System.out.println("I am a vehicle!");

}

}

## Multiple Defaults

With default functions in interfaces, there is a possibility that a class is implementing two interfaces with same default methods. The following code explains how this ambiguity can be resolved.

public  interface vehicle {

default  void  print()  {

System.out.println("I am a vehicle!");

}

}

public  interface fourWheeler {

default  void  print()  {

System.out.println("I am a four wheeler!");

}

}

First solution is to create an own method that overrides the default implementation.

public  class car implements vehicle, fourWheeler {

public  void  print()  {

System.out.println("I am a four wheeler car vehicle!");

}

}

Second solution is to call the default method of the specified interface using super.

public  class car implements vehicle, fourWheeler {

default  void  print()  {

vehicle.super.print();

}

}

## Static Default Methods

An interface can also have static helper methods from Java 8 onwards.

public  interface vehicle {

default  void  print()  {

System.out.println("I am a vehicle!");

}

static  void blowHorn()  {

System.out.println("Blowing horn!!!");

}

}

## Default Method Example

Create the following Java program using any editor of your choice in, say, C:\> JAVA.

### Java8Tester.java

public  class  Java8Tester  {

public  static  void main(String args[])  {

Vehicle vehicle =  new  Car();

vehicle.print();

}

}

interface  Vehicle  {

default  void  print()  {

System.out.println("I am a vehicle!");

}

static  void blowHorn()  {

System.out.println("Blowing horn!!!");

}

}

interface  FourWheeler  {

default  void  print()  {

System.out.println("I am a four wheeler!");

}

}

class  Car  implements  Vehicle,  FourWheeler  {

public  void  print()  {

Vehicle.super.print();

FourWheeler.super.print();

Vehicle.blowHorn();

System.out.println("I am a car!");

}

}

### Verify the Result

Compile the class using **javac** compiler as follows −

C:\JAVA>javac Java8Tester.java

Now run the Java8Tester as follows −

C:\JAVA>java Java8Tester

It should produce the following output −

I am a vehicle!

I am a four wheeler!

Blowing horn!!!

I am a car!

# Functional Programming - Functional Interfaces

Functional interfaces have a single functionality to exhibit. For example, a Comparable interface with a single method 'compareTo' is used for comparison purpose. Java 8 has defined a lot of functional interfaces to be used extensively in lambda expressions. Following is the list of functional interfaces defined in java.util.Function package.

Given below is the list of interfaces in Java8.

## Functional Interface Example

Predicate <T> interface is a functional interface with a method test(Object) to return a Boolean value. This interface signifies that an object is tested to be true or false.

Create the following Java program using any editor of your choice in, say, C:\> JAVA.

### Java8Tester.java

import java.util.Arrays;

import java.util.List;

import java.util.function.Predicate;

public  class  Java8Tester  {

public  static  void main(String args[])  {

List<Integer> list =  Arrays.asList(1,  2,  3,  4,  5,  6,  7,  8,  9);

// Predicate<Integer> predicate = n -> true

// n is passed as parameter to test method of Predicate interface

// test method will always return true no matter what value n has.

System.out.println("Print all numbers:");

//pass n as parameter

eval(list, n->true);

// Predicate<Integer> predicate1 = n -> n%2 == 0

// n is passed as parameter to test method of Predicate interface

// test method will return true if n%2 comes to be zero

System.out.println("Print even numbers:");

eval(list, n-> n%2  ==  0  );

// Predicate<Integer> predicate2 = n -> n > 3

// n is passed as parameter to test method of Predicate interface

// test method will return true if n is greater than 3.

System.out.println("Print numbers greater than 3:");

eval(list, n-> n >  3  );

}

public  static  void  eval(List<Integer> list,  Predicate<Integer> predicate)  {

for(Integer n: list)  {

if(predicate.test(n))  {

System.out.println(n +  " ");

}

}

}

}

Here we've passed Predicate interface, which takes a single input and returns Boolean.

### Verify the Result

Compile the class using **javac** compiler as follows −

C:\JAVA>javac Java8Tester.java

Now run the Java8Tester as follows −

C:\JAVA>java Java8Tester

It should produce the following output −

Print all numbers:

1

2

3

4

5

6

7

8

9

Print even numbers:

2

4

6

8

Print numbers greater than 3:

4

5

6

7

8

9

# Functional Programming - Method References

Method references help to point to methods by their names. A method reference is described using "::" symbol. A method reference can be used to point the following types of methods −

*   **Static methods** - static method can be reference using ClassName::Method name notation.

//Method Reference - Static way

Factory vehicle_factory_static =  VehicleFactory::prepareVehicleInStaticMode;

*   **Instance methods** - instance method can be reference using Object::Method name notation.

//Method Reference - Instance way

Factory vehicle_factory_instance =  new  VehicleFactory()::prepareVehicle;

Following example shows how Method references works in Java 8 onwards.

interface  Factory  {

Vehicle prepare(String make,  String model,  int year);

}

class  Vehicle  {

private  String make;

private  String model;

private  int year;

Vehicle(String make,  String model,  int year){

this.make = make;

this.model = model;

this.year = year;

}

public  String toString(){

return  "Vehicle["  + make +", "  + model +  ", "  + year+  "]";

}

}

class  VehicleFactory  {

static  Vehicle prepareVehicleInStaticMode(String make,  String model,  int year){

return  new  Vehicle(make, model, year);

}

Vehicle prepareVehicle(String make,  String model,  int year){

return  new  Vehicle(make, model, year);

}

}

public  class  FunctionTester  {

public  static  void main(String[] args)  {

//Method Reference - Static way

Factory vehicle_factory_static =  VehicleFactory::prepareVehicleInStaticMode;

Vehicle carHyundai = vehicle_factory_static.prepare("Hyundai",  "Verna",  2018);

System.out.println(carHyundai);

//Method Reference - Instance way

Factory vehicle_factory_instance =  new  VehicleFactory()::prepareVehicle;

Vehicle carTata = vehicle_factory_instance.prepare("Tata",  "Harrier",  2019);

System.out.println(carTata);

}

}

### Output

Vehicle[Hyundai, Verna, 2018]

Vehicle[Tata, Harrier, 2019]

# Constructor References

Constructor references help to point to Constructor method. A Constructor reference is accessed using "::new" symbol.

//Constructor reference

Factory vehicle_factory =  Vehicle::new;

Following example shows how Constructor references works in Java 8 onwards.

interface  Factory  {

Vehicle prepare(String make,  String model,  int year);

}

class  Vehicle  {

private  String make;

private  String model;

private  int year;

Vehicle(String make,  String model,  int year){

this.make = make;

this.model = model;

this.year = year;

}

public  String toString(){

return  "Vehicle["  + make +", "  + model +  ", "  + year+  "]";

}

}

public  class  FunctionTester  {

static  Vehicle factory(Factory factoryObj,  String make,  String model,  int year){

return factoryObj.prepare(make, model, year);

}

public  static  void main(String[] args)  {

//Constructor reference

Factory vehicle_factory =  Vehicle::new;

Vehicle carHonda = factory(vehicle_factory,  "Honda",  "Civic",  2017);

System.out.println(carHonda);

}

}

### Output

Vehicle[Honda, Civic, 2017]

# Functional Programming with Java – Collections

With Java 8 onwards, streams are introduced in Java and methods are added to collections to get a stream. Once a stream object is retrieved from a collection, we can apply various functional programming aspects like filtering, mapping, reducing etc. on collections. See the example below −

import java.util.Arrays;

import java.util.List;

import java.util.stream.Collectors;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

List<Integer> numbers =  Arrays.asList(3,  2,  2,  3,  7,  3,  5);

//Mapping

//get list of unique squares

List<Integer> squaresList = numbers.stream().map( i -> i*i)

.distinct().collect(Collectors.toList());

System.out.println(squaresList);

//Filering

//get list of non-empty strings

List<String>strings =  Arrays.asList("abc",  "",  "bc",  "efg",  "abcd","",  "jkl");

List<String> nonEmptyStrings = strings.stream()

.filter(string  ->  !string.isEmpty()).collect(Collectors.toList());

System.out.println(nonEmptyStrings);

//Reducing

int sum = numbers.stream().reduce((num1, num2)  -> num1 + num2).orElse(-1);

System.out.println(sum);

}

}

### Output

[9, 4, 49, 25]

[abc, bc, efg, abcd, jkl]

25

# Functional Programming - High Order Functions

A function is considered as a High Order function if it fulfils any one of the following conditions.

*   It takes one or more parameters as functions.
*   It returns a function after its execution.

Java 8 Collections.sort() method is an ideal example of a high order function. It accepts a comparing method as an argument. See the example below −

import java.util.Arrays;

import java.util.Collections;

import java.util.Comparator;

import java.util.List;

import java.util.stream.Collectors;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

List<Integer> numbers =  Arrays.asList(3,  4,  6,  7,  9);

//Passing a function as lambda expression

Collections.sort(numbers,  (a,b)  ->{  return a.compareTo(b);  });

System.out.println(numbers);

Comparator<Integer> comparator =  (a,b)  ->{  return a.compareTo(b);  };

Comparator<Integer> reverseComparator = comparator.reversed();

//Passing a function

Collections.sort(numbers, reverseComparator);

System.out.println(numbers);

}

}

### Output

[3, 4, 6, 7, 9]

[9, 7, 6, 4, 3]

# Functional Programming - Returning a Function

As a High Order function can return a function but how to implement using Java 8\. Java 8 has provided Function interface which can accept a lambda expression. A high order function can return a lamdba expression and thus this high order function can be used to create any number of functions. See the example below −

import java.util.function.Function;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Function<Integer,  Integer> addOne = adder(1);

Function<Integer,  Integer> addTwo = adder(2);

Function<Integer,  Integer> addThree = adder(3);

//result = 4 + 1 = 5

Integer result = addOne.apply(4);

System.out.println(result);

//result = 4 + 2 = 6

result = addTwo.apply(4);

System.out.println(result);

//result = 4 + 3 = 7

result = addThree.apply(4);

System.out.println(result);

}

//adder - High Order Function

//returns a function as lambda expression

static  Function<Integer,  Integer> adder(Integer x){

return y -> y + x;

}

}

### Output

5

6

7

# Functional Programming - First Class Function

A function is called a first class function if it fulfills the following requirements.

*   It can be passed as a parameter to a function.
*   It can be returned from a function.
*   It can be assigned to a variable and then can be used later.

Java 8 supports functions as first class object using lambda expressions. A lambda expression is a function definition and can be assigned to a variable, can be passed as an argument and can be returned. See the example below −

@FunctionalInterface

interface  Calculator<X, Y>  {

public X compute(X a, Y b);

}

public  class  FunctionTester  {

public  static  void main(String[] args)  {

//Assign a function to a variable

Calculator<Integer,  Integer> calculator =  (a,b)  -> a * b;

//call a function using function variable

System.out.println(calculator.compute(2,  3));

//Pass the function as a parameter

printResult(calculator,  2,  3);

//Get the function as a return result

Calculator<Integer,  Integer> calculator1 = getCalculator();

System.out.println(calculator1.compute(2,  3));

}

//Function as a parameter

static  void printResult(Calculator<Integer,  Integer> calculator,  Integer a,  Integer b){

System.out.println(calculator.compute(a, b));

}

//Function as return value

static  Calculator<Integer,  Integer> getCalculator(){

Calculator<Integer,  Integer> calculator =  (a,b)  -> a * b;

return calculator;

}

}

### Output

6

6

6

# Functional Programming - Pure Function

A function is considered as Pure Function if it fulfils the following two conditions −

*   It always returns the same result for the given inputs and its results purely depends upon the inputs passed.
*   It has no side effects means it is not modifying any state of the caller entity.

## Example- Pure Function

public  class  FunctionTester  {

public  static  void main(String[] args)  {

int result = sum(2,3);

System.out.println(result);

result = sum(2,3);

System.out.println(result);

}

static  int sum(int a,  int b){

return a + b;

}

}

### Output

5

5

Here **sum()** is a pure function as it always return 5 when passed 2 and 3 as parameters at different times and has no side effects.

## Example- Impure Function

public  class  FunctionTester  {

private  static  double valueUsed =  0.0;

public  static  void main(String[] args)  {

double result = randomSum(2.0,3.0);

System.out.println(result);

result = randomSum(2.0,3.0);

System.out.println(result);

}

static  double randomSum(double a,  double b){

valueUsed =  Math.random();

return valueUsed + a + b;

}

}

### Output

5.919716721877799

5.4830887819586795

Here **randomSum()** is an impure function as it return different results when passed 2 and 3 as parameters at different times and modifies state of instance variable as well.

# Functional Programming - Type Inference

Type inference is a technique by which a compiler automatically deduces the type of a parameter passed or of return type of a method. Java 8 onwards, Lambda expression uses type inference prominently.

See the example below for clarification on type inference.

## Example- Type Inference

public  class  FunctionTester  {

public  static  void main(String[] args)  {

Join<Integer,Integer,Integer> sum =  (a,b)  -> a + b;

System.out.println(sum.compute(10,20));

Join<String,  String,  String> concat =  (a,b)  -> a + b;

System.out.println(concat.compute("Hello ","World!"));

}

interface  Join<K,V,R>{

R compute(K k ,V v);

}

}

### Output

30

Hello World!

A lambda expression treats each parameter and its return type as Object initially and then inferred the data type accordingly. In first case, the type inferred is Integer and in second case type inferred is String.

# Exception Handling in Lambda Expressions

Lambda expressions are difficult to write when the function throws a checked expression. See the example below −

import java.net.URLEncoder;

import java.util.Arrays;

import java.util.stream.Collectors;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

String url =  "www.google.com";

System.out.println(encodedAddress(url));

}

public  static  String encodedAddress(String... address)  {

return  Arrays.stream(address)

.map(s ->  URLEncoder.encode(s,  "UTF-8"))

.collect(Collectors.joining(","));

}

}

The above code fails to compile because URLEncode.encode() throws UnsupportedEncodingException and cannot be thrown by encodeAddress() method.

One possible solution is to extract URLEncoder.encode() into a separate method and handle the exception there.

import java.io.UnsupportedEncodingException;

import java.net.URLEncoder;

import java.util.Arrays;

import java.util.stream.Collectors;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

String url =  "www.google.com";

System.out.println(encodedAddress(url));

}

public  static  String encodedString(String s)  {

try  {

URLEncoder.encode(s,  "UTF-8");

}

catch  (UnsupportedEncodingException e)  {

e.printStackTrace();

}

return s;

}

public  static  String encodedAddress(String... address)  {

return  Arrays.stream(address)

.map(s -> encodedString(s))

.collect(Collectors.joining(","));

}

}

But above approach is not good when we have multiple such methods which throws exception. See the following generalized solution using functional interface and a wrapper method.

import java.net.URLEncoder;

import java.util.Arrays;

import java.util.function.Function;

import java.util.stream.Collectors;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

String url =  "www.google.com";

System.out.println(encodedAddress(url));

}

public  static  String encodedAddress(String... address)  {

return  Arrays.stream(address)

.map(wrapper(s ->  URLEncoder.encode(s,  "UTF-8")))

.collect(Collectors.joining(","));

}

private  static  <T, R, E extends  Exception>  Function<T, R>

wrapper(FunctionWithThrows<T, R, E> fe)  {

return arg ->  {

try  {

return fe.apply(arg);

}  catch  (Exception e)  {

throw  new  RuntimeException(e);

}

};

}

}

@FunctionalInterface

interface  FunctionWithThrows<T, R, E extends  Exception>  {

R apply(T t)  throws E;

}

### Output

www.google.com

# Intermediate Methods

Stream API was introduced in Java 8 to facilitate functional programming in Java. A Stream API is targeted towards processing of collections of objects in functional way. By definition, a Stream is a Java component which can do internal iteration of its elements.

A Stream interface has terminal as well as non-terminal methods. Non-terminal methods are such operations which adds a listener to a stream. When a terminal method of stream is invoked, then internal iteration of stream elements get started and listener(s) attached to stream are getting called for each element and result is collected by the terminal method.

Such non-terminal methods are called Intermediate methods. The Intermediate method can only be invoked by called a terminal method. Following are some of the important Intermediate methods of Stream interface.

*   **filter** − Filters out non-required elements from a stream based on given criteria. This method accepts a predicate and apply it on each element. If predicate function return true, element is included in returned stream.
*   **map** − Maps each element of a stream to another item based on given criteria. This method accepts a function and apply it on each element. For example, to convert each String element in a stream to upper-case String element.
*   **flatMap** − This method can be used to maps each element of a stream to multiple items based on given criteria. This method is used when a complex object needs to be broken into simple objects. For example, to convert list of sentences to list of words.
*   **distinct** − Returns a stream of unique elements if duplicates are present.
*   **limit** − Returns a stream of limited elements where limit is specified by passing a number to limit method.

## Example - Intermediate Methods

import java.util.Arrays;

import java.util.List;

import java.util.stream.Stream;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

List<String> stringList =

Arrays.asList("One",  "Two",  "Three",  "Four",  "Five",  "One");

System.out.println("Example - Filter\n");

//Filter strings whose length are greater than 3.

Stream<String> longStrings = stringList

.stream()

.filter( s ->  {return s.length()  >  3;  });

//print strings

longStrings.forEach(System.out::println);

System.out.println("\nExample - Map\n");

//map strings to UPPER case and print

stringList

.stream()

.map( s -> s.toUpperCase())

.forEach(System.out::println);

List<String> sentenceList

=  Arrays.asList("I am Mahesh.",  "I love Java 8 Streams.");

System.out.println("\nExample - flatMap\n");

//map strings to UPPER case and print

sentenceList

.stream()

.flatMap( s ->  {  return  (Stream<String>)

Arrays.asList(s.split(" ")).stream();  })

.forEach(System.out::println);

System.out.println("\nExample - distinct\n");

//map strings to UPPER case and print

stringList

.stream()

.distinct()

.forEach(System.out::println);

System.out.println("\nExample - limit\n");

//map strings to UPPER case and print

stringList

.stream()

.limit(2)

.forEach(System.out::println);

}

}

### Output

Example - Filter

Three

Four

Five

Example - Map

ONE

TWO

THREE

FOUR

FIVE

ONE

Example - flatMap

I

am

Mahesh.

I

love

Java

8

Streams.

Example - distinct

One

Two

Three

Four

Five

Example - limit

One

Two

# Functional Programming - Terminal Methods

When a terminal method in invoked on a stream, iteration starts on stream and any other chained stream. Once the iteration is over then the result of terminal method is returned. A terminal method does not return a Stream thus once a terminal method is invoked over a stream then its chaining of non-terminal methods or intermediate methods stops/terminates.

Generally, terminal methods returns a single value and are invoked on each element of the stream. Following are some of the important terminal methods of Stream interface. Each terminal function takes a predicate function, initiates the iterations of elements, apply the predicate on each element.

*   **anyMatch** − If predicate returns true for any of the element, it returns true. If no element matches, false is returned.
*   **allMatch** − If predicate returns false for any of the element, it returns false. If all element matches, true is returned.
*   **noneMatch** − If no element matches, true is returned otherwise false is returned.
*   **collect** − each element is stored into the collection passed.
*   **count** − returns count of elements passed through intermediate methods.
*   **findAny** − returns Optional instance containing any element or empty instance is returned.
*   **findFirst** − returns first element under Optional instance. For empty stream, empty instance is returned.
*   **forEach** − apply the consumer function on each element. Used to print all elements of a stream.
*   **min** − returns the smallest element of the stream. Compares elements based on comparator predicate passed.
*   **max** − returns the largest element of the stream. Compares elements based on comparator predicate passed.
*   **reduce** − reduces all elements to a single element using the predicate passed.
*   **toArray** − returns arrays of elements of stream.

## Example - Terminal Methods

import java.util.Arrays;

import java.util.List;

import java.util.stream.Collectors;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

List<String> stringList

=  Arrays.asList("One",  "Two",  "Three",  "Four",  "Five",  "One");

System.out.println("Example - anyMatch\n");

//anyMatch - check if Two is present?

System.out.println("Two is present: "

+ stringList

.stream()

.anyMatch(s ->  {return s.contains("Two");}));

System.out.println("\nExample - allMatch\n");

//allMatch - check if length of each string is greater than 2.

System.out.println("Length > 2: "

+ stringList

.stream()

.allMatch(s ->  {return s.length()  >  2;}));

System.out.println("\nExample - noneMatch\n");

//noneMatch - check if length of each string is greater than 6.

System.out.println("Length > 6: "

+ stringList

.stream()

.noneMatch(s ->  {return s.length()  >  6;}));

System.out.println("\nExample - collect\n");

System.out.println("List: "

+ stringList

.stream()

.filter(s ->  {return s.length()  >  3;})

.collect(Collectors.toList()));

System.out.println("\nExample - count\n");

System.out.println("Count: "

+ stringList

.stream()

.filter(s ->  {return s.length()  >  3;})

.count());

System.out.println("\nExample - findAny\n");

System.out.println("findAny: "

+ stringList

.stream()

.findAny().get());

System.out.println("\nExample - findFirst\n");

System.out.println("findFirst: "

+ stringList

.stream()

.findFirst().get());

System.out.println("\nExample - forEach\n");

stringList

.stream()

.forEach(System.out::println);

System.out.println("\nExample - min\n");

System.out.println("min: "

+ stringList

.stream()

.min((s1, s2)  ->  {  return s1.compareTo(s2);}));

System.out.println("\nExample - max\n");

System.out.println("min: "

+ stringList

.stream()

.max((s1, s2)  ->  {  return s1.compareTo(s2);}));

System.out.println("\nExample - reduce\n");

System.out.println("reduced: "

+ stringList

.stream()

.reduce((s1, s2)  ->  {  return s1 +  ", "+ s2;})

.get());

}

}

### Output

Example - anyMatch

Two is present: true

Example - allMatch

Length > 2: true

Example - noneMatch

Length > 6: true

Example - collect

List: [Three, Four, Five]

Example - count

Count: 3

Example - findAny

findAny: One

Example - findFirst

findFirst: One

Example - forEach

One

Two

Three

Four

Five

One

Example - min

min: Optional[Five]

Example - max

min: Optional[Two]

Example - reduce

reduced: One, Two, Three, Four, Five, One

# Functional Programming - Infinite Streams

Collections are in-memory data structure which have all the elements present in the collection and we have external iteration to iterate through collection whereas Stream is a fixed data structure where elements are computed on demand and a Stream has inbuilt iteration to iterate through each element. Following example shows how to create a Stream from an array.

int[] numbers =  {1,  2,  3,  4};

IntStream numbersFromArray =  Arrays.stream(numbers);

Above stream is of fixed size being built from an array of four numbers and will not return element after 4th element. But we can create a Stream using Stream.iterate() or Stream.generate() method which can have lamdba expression will pass to a Stream. Using lamdba expression, we can pass a condition which once fulfilled give the required elements. Consider the case, where we need a list of numbers which are multiple of 3.

## Example - Infinite Stream

import java.util.stream.Stream;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

//create a stream of numbers which are multiple of 3

Stream<Integer> numbers =  Stream.iterate(0, n -> n +  3);

numbers

.limit(10)

.forEach(System.out::println);

}

}

### Output

0

3

6

9

12

15

18

21

24

27

In order to operate on infinite stream, we've used limit() method of Stream interface to restrict the iteration of numbers when their count become 10.

# Functional Programming - Fixed length Streams

There are multiple ways using which we can create fix length streams.

*   Using Stream.of() method
*   Using Collection.stream() method
*   Using Stream.builder() method

Following example shows all of the above ways to create a fix length stream.

## Example - Fix Length Stream

import java.util.Arrays;

import java.util.List;

import java.util.stream.Stream;

public  class  FunctionTester  {

public  static  void main(String[] args)  {

System.out.println("Stream.of():");

Stream<Integer> stream =  Stream.of(1,  2,  3,  4,  5);

stream.forEach(System.out::println);

System.out.println("Collection.stream():");

Integer[] numbers =  {1,  2,  3,  4,  5};

List<Integer> list =  Arrays.asList(numbers);

list.stream().forEach(System.out::println);

System.out.println("StreamBuilder.build():");

Stream.Builder<Integer> streamBuilder =  Stream.builder();

streamBuilder.accept(1);

streamBuilder.accept(2);

streamBuilder.accept(3);

streamBuilder.accept(4);

streamBuilder.accept(5);

streamBuilder.build().forEach(System.out::println);

}

}

### Output

Stream.of():

1

2

3

4

5

Collection.stream():

1

2

3

4

5

StreamBuilder.build():

1

2

3

4

5