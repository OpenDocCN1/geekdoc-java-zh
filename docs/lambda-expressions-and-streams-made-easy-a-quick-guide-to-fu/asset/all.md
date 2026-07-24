![](cover.jpeg)

Copyright © 2018

All rights reserved. No part of this publication may be reproduced, distributed, or transmitted in any form or by any means, including photocopying, recording, or other electronic or mechanical methods, without the prior written permission of the publisher, except in the case of brief quotations embodied in critical reviews and certain other noncommercial uses permitted by copyright law.

Table of Contents

[1.Introduction](#part0000_split_002.html__Toc518902959)

[1.1.Lambda syntax](#part0000_split_003.html__Toc518902960)

[1.1.1.General syntax](#part0000_split_003.html__Toc518902961)

[1.1.2.Abbreviations](#part0000_split_003.html__Toc518902962)

[1.2A Lambda is an implementation of a functional interface](#part0000_split_004.html__Toc518902963)

[1.3 @Functional interface](#part0000_split_005.html__Toc518902964)

[2.Java standard library and lambda’s](#part0000_split_006.html__Toc518902965)

[3.Stream and forEach](#part0000_split_007.html__Toc518902966)

[3.1.1.foreach](#part0000_split_008.html__Toc518902967)

[3.2 Date sources of a stream](#part0000_split_009.html__Toc518902968)

[3.2.1List](#part0000_split_009.html__Toc518902969)

[3.2.2 Set](#part0000_split_009.html__Toc518902970)

[3.2.3 Map](#part0000_split_009.html__Toc518902971)

[3.3String](#part0000_split_010.html__Toc518902972)

[3.4 Files](#part0000_split_011.html__Toc518902973)

[3.5 Directory](#part0000_split_012.html__Toc518902974)

[3.6Infinite sequence of values](#part0000_split_013.html__Toc518902975)

[3.7Sequence of numbers](#part0000_split_014.html__Toc518902976)

[4.Filter](#part0000_split_015.html__Toc518902977)

[5.Sort](#part0000_split_016.html__Toc518902978)

[6.Combining operations](#part0000_split_017.html__Toc518902979)

[7.Unique values](#part0000_split_018.html__Toc518902980)

[8.Transform](#part0000_split_019.html__Toc518902981)

[9.Check if one or all values match with a given predicate](#part0000_split_020.html__Toc518902982)

[9.1AllMatch](#part0000_split_020.html__Toc518902983)

[9.2Anymatch](#part0000_split_021.html__Toc518902984)

[10.Collect Stream values](#part0000_split_022.html__Toc518902985)

[10.1 Array](#part0000_split_023.html__Toc518902986)

[10.2List](#part0000_split_024.html__Toc518902987)

[10.3 Set](#part0000_split_025.html__Toc518902988)

[10.4Map](#part0000_split_026.html__Toc518902989)

[10.5Stats](#part0000_split_027.html__Toc518902990)

[10.5.1Count](#part0000_split_027.html__Toc518902991)

[10.5.2Sum](#part0000_split_027.html__Toc518902992)

[10.5.3 Min, max, average](#part0000_split_027.html__Toc518902993)

[10.6Stats on long values](#part0000_split_028.html__Toc518902994)

[10.7Stats on double values](#part0000_split_029.html__Toc518902995)

[10.8 Min and max of other valus](#part0000_split_030.html__Toc518902996)

[11.Reduce](#part0000_split_031.html__Toc518902997)

[11.1 Stream.reduce() with Accumulator](#part0000_split_032.html__Toc518902998)

[11.2 Stream.reduce() with Identity and Accumulator](#part0000_split_033.html__Toc518902999)

[12Conclusion](#part0000_split_034.html__Toc518903000)

# 1. Introduction

Lambda’s exist in many coding languages. A Lambda is an anonymous function (function without a name) and is used to implement a function defined by a functional interface.

Java8 introduces Lambda’s into Java. Lambda’s are Java’s first steps into functional programming. A Java Lambda expression is a function which can be created without belonging to any class. A Java Lambda expression can be passed around as if it was an object and executed on demand (which allows us to pass logic in a more compact way.)

λ is the symbol that represents a Lambda.

## 1.1. Lambda syntax

### 1.1.1. General syntax

Lambda expressions introduce the arrow parameter into Java. It divides the lambda expression in two parts. The left side specifies the parameters required by the expression which could also be empty if no parameters are required. The right side is the lambda body which specifies the actions of the lambda expression:
(parameter1, parameter2) -> {code of the function}

The example below is a Lambda with 2 parameters that prints those parameters to the console:
(int number, char character) -> {System.out.println(number); System.out.println(character);}

### 1.1.2. Abbreviations 

*   Parameters are optional in a Lambda
    (number, character) -> {System.out.println(number); System.out.println(character);}

*   A Lambda that has 1 parameter => the parentheses are optional
    number -> {System.out.println(number);}

*   A Lambda that hasn’t any parameters => the parentheses are obliged
    () -> {System.out.println(“Hello World”);}

*   A Lambda that has only one instruction => the curly brackets are optional
    number -> System.out.println(number);

*   A Lambda that has only one instruction that is a return-instruction => the keyword return is optional
    number -> number * number;

## 1.2A Lambda is an implementation of a functional interface

A functional interface is an interface that contains one and only one abstract method. The Java standard [Runnable interface](https://docs.oracle.com/javase/7/docs/api/java/lang/Runnable.html) is such a functional interface. It defines one method: run().

Aside from the built-in functional interfaces, we can create our own functional interfaces. The example below is such a single method interface:

public  interface EvenNumber {

boolean isEven(int  number);

}

In Java7 you would have to use an anonymous interface implementation like this:

public  class  Main {

public  static  void main(String[] args) {

EvenNumber myEvenNumber = new EvenNumber() {

public  boolean isEven(int  number) {

return  number % 2 == 0;

}};

System.out.println(myEvenNumber.isEven(7));

}}

In Java8 you can use a Lambda expression that implements the functional interface:

public  class Main {

public  static  void main(String[] args) {

EvenNumber myEvenNumber =

 number -> number % 2 == 0;

 System.out.println(myEvenNumber.isEven(7)); 

 } }

## 1.3 @Functional interface

All functional interfaces are recommended to have an informative  @FunctionalInterface  annotation. This not only clearly communicates the purpose of this interface, but also allows a compiler to generate an error if the annotated interface does not satisfy the conditions. An interface that has more than 1 abstract method is no longer a functional interface and cannot be  implemented with a Lambda. When the interface is annotated with the  @FunctionalInterface annotation and the function has more than 1 abstract method, the compiler will generate an error.

@FunctionalInterface

public  interface EvenNumber {

boolean isEven(int  number);

}

# 2. Java standard library and lambda’s

The interface comparator is a functional interface. It has 1 abstract method:

int compare(T object1, T object2);

you don’t need to write a class to implement this interface, you can write a short lambda as implementation of the interface.

class Main {

public  static  void main(String[] args) {

String[] fruits = { "apple", "cherries", "banana", "avocado" };

Arrays.sort(fruits, (fruit1, fruit2) -> -fruit1.compareTo(fruit2));

System.out.println(Arrays.toString(fruits));

}}

 You could also use the length of each word to sort the fruits. You just need to change the lambda expression to:                           

fruit1.length() - fruit2.length()

# 3. Stream and forEach

The interface Stream is new in Java8\. A stream represents a sequence of elements and supports different kinds of operations to perform computations upon those elements. Streams can be created from various data sources like an array, a list, a set,…

This guide teaches you how to work with Java 8 streams and how to use the different kinds of available stream operations like filter, map, reduce,…

The methods in the Stream interface accept a Lambda as parameter, which makes the code very short and readable.

## 3.1.1. foreach

forEach iterates over a collection and performs the given action for each element of the collection until all elements have been processed or the action throws an exception. The example below will print each fruit to the console:

class Main {

public  static  void main(String[] args) {

String[] fruits = { "apple", "cherries", "banana", "avocado" };

Stream<String> stream = Arrays.stream(fruits);

stream.forEach(fruit -> System.out.println(fruit));

}}

It is possible to combine the last two instructions into one:

class Main {

public  static  void main(String[] args) {

String[] fruits = { "apple", "cherries", "banana", "avocado" };

Arrays.stream(fruits)

.forEach(fruit -> System.out.println(fruit));

}}

## 3.2 Date sources of a stream

### 3.2.1List

A list can be a date source of a stream

class Main {

public  static  void main(String[] args) {

List<String> fruits = Arrays.asList("apple", "cherries", "banana", "avocado");

fruits.stream()

.forEach(fruit -> System.out.println(fruit));

}}

### 3.2.2 Set

A Set can be a date source of a stream

class Main {

public  static  void main(String[] args) {

Set<Integer> numbers = new LinkedHashSet<>();

numbers.add(1);

numbers.add(3);

numbers.add(4);

numbers.add(7);

numbers.stream().forEach(getal -> System.out.println(getal));

}}

### 3.2.3 Map

The keySet, the values or the entrySet can be a date source of a stream. In the example below we use an entrySet.

class Main {

public  static  void main(String[] args) {

Map<String, String> languages = new LinkedHashMap<>();

languages.put("ENG", "English"); 

languages.put("FRE", "French");  

languages.entrySet().stream()

.forEach(entry -> System.out.println(entry.getKey() + ':' + entry.getValue()));   }

}

## 3.3String

A String can be a date source of a stream. The values in the stream are the characters of the String.

class Main {

public  static  void main(String[] args) {

 "Lambdafun".chars()

    .forEach(unicode->System.out.println((char) unicode)); } }

## 3.4 Files

A file can be a date source of a stream.  The values in the stream are Strings that represent the lines in the file.

class Main {

private  final  static Path LANGUAGES_PATH = Paths.get("/data/languages.txt");

public  static  void main(String[] args) {

try (Stream<String> stream = Files.lines(LANGUAGES_PATH)) {

stream.forEach(line -> System.out.println(line));

} catch (IOException ex) {

ex.printStackTrace();

}}}

## 3.5 Directory

A directory can be a date source of a stream.  The values in the stream are the paths of the files and the subdirectories in the directory.

class Main {

private  final  static Path DATA_PATH = Paths.get("/data");

public  static  void main(String[] args) {

try (Stream<Path> stream = Files.list(DATA_PATH)) {

stream.forEach(entry -> System.out.println(entry.getFileName()));

} catch (Exception ex) {

ex.printStackTrace();

}}}

## 3.6Infinite sequence of values

An infinite sequence of values can be a date source of a stream.

class Main {

public  static  void main(String[] args) { 

Stream.iterate(1, previousNumber -> previousNumber + 2)

.forEach(oddNumber->System.out.println(oddNumber));   }

}

Use the method limit() if you want to limit the sequence:

class Main {

public  static  void main(String[] args) { 

Stream.iterate(1, previousNumber -> previousNumber + 2)

.limit(10)

.forEach(oddNumber->System.out.println(oddNumber));   }

}

## 3.7Sequence of numbers

class Main {

public  static  void main(String[] args) {

IntStream.rangeClosed(1, 10).forEach(number -> System.out.println(number));

IntStream.range(1, 10).forEach(number -> System.out.println(number));

# 4. Filter

Sometimes you might want to work with only a subset of the elements. To do so, you can use the filter method.

For example if you want to create a subset of the list with fruits, which contains only those strings whose length is more than 6 characters, you use a filter:

class Main {

public  static  void main(String[] args) {

Stream.of("apple", "cherries", "banana", "avocado")

.filter(fruit -> fruit.length()>6)

.forEach(fruit -> System.out.println(fruit));

}}

# 5. Sort

You can sort the values in a stream with the stream-method sorted()

class Main {

public  static  void main(String[] args) {

Stream.of("apple", "cherries", "banana", "avocado")

.sorted()

.forEach(fruit -> System.out.println(fruit));

}}

This method sorts the stream with natural ordering.

Ordering provided by Comparator is possible as well. This Comparator can be instantiated using a Lambda expression. In the example below we will order by length of each string:

class Main {

public  static  void main(String[] args) {

Stream.of("apple", "cherries", "banana", "avocado")

.sorted((fruit1, fruit2)-> fruit1.length() - fruit2.length())

.forEach(fruit -> System.out.println(fruit));

}}

# 6. Combining operations

In the example below we combine the filter, sorted and forEach operations:

class Main {

public  static  void main(String[] args) {

Stream.of("apple", "cherries", "banana", "avocado")

.filter(fruit -> fruit.length()>5)

.sorted()

.forEach(fruit -> System.out.println(fruit));

}}

# 7. Unique values

The Stream method distinct() returns the unique values

class Main {

public  static  void main(String[] args) {

Stream.of("apple", "cherries", "apple", "banana", "avocado", "apple")

.distinct()

.sorted()

.forEach(fruit -> System.out.println(fruit));

}}

# 8. Transform

Assume we now have a filtered data that we can use for the real operations, say transforming the objects. The map operations allows us to apply a function that takes in a parameter of one type, and returns something else.

In the example below we will transform the list of strings to a list of numbers (the lengths of the strings)

class Main {

public  static  void main(String[] args) {

Stream.of("apple", "cherries", "banana", "avocado")

.map(fruit -> fruit.length())

.forEach(fruit -> System.out.println(fruit));

}}

We can also use this map method if we want to transform a list of objects to a list of methods of that object. In the example below we get the surfaces of the rectangles in the stream.

class Rectangle {

private  final  int  length;

private  final  int  width; 

Rectangle(int  length, int  width) {

this.length = length;   

this.width = width; 

} 

int getSurface() {

return  length * width; 

}

}

class Main {

public  static  void main(String[] args) { 

Stream.of(new Rectangle(6, 2), new Rectangle(3, 1), new Rectangle(5, 4))

.map(rectangle -> rectangle.getSurface())

.forEach(surface -> System.out.println(surface));} }

# 9. Check if one or all values match with a given predicate

## 9.1AllMatch

This method returns true if all the values of a stream match with the given predicate. We pass the predicate as an argument to the allmatch() method.

class Main {

public  static  void main(String[] args) {

System.out.println(

Stream.of("apple", "cherries", "banana", "avocado")

.allMatch(fruit -> fruit.length() == 6));

}}

## 9.2Anymatch

This method returns true if one of the values matches with the given predicate

class Main {

public  static  void main(String[] args) {

System.out.println(

Stream.of("apple", "cherries", "banana", "avocado")

.anyMatch(fruit -> fruit.length() == 6));

}}

# 10.  Collect Stream values

It is possible to collect all the values of a stream in an array, list, set,…

## 10.1 Array

To convert a stream to an array we use the toArray() method from stream objects. This method returns an array containing the elements of the stream.

class Main {

public  static  void main(String[] args) {

Stream<String> stream = Stream.of("apple", "cherries", "banana", "avocado");

String[] arr = stream.toArray(size -> new String[size]);

System.out.println(Arrays.toString(arr));

}}

## 10.2List

To convert a stream to a List we use the collect() method from stream objects. The toList() collector can be used for collecting all Stream elements into a List instance.

class Main {

public  static  void main(String[] args) {

System.out.println(

Stream.of("apple", "cherries", "banana", "avocado")

.sorted()

.collect(Collectors.toList()));  }}

## 10.3 Set

To convert a stream to a Set we use the collect() method from stream objects. The toSet() collector can be used for collecting all Stream elements into a Set instance.

class Main {

public  static  void main(String[] args) {

System.out.println(

Stream.of("apple", "cherries", "banana", "avocado")

.sorted()

.collect(Collectors.toSet()));

}}

## 10.4Map

In a map there is a key and a value. In the example below we will use the length of the strings as key and group all the fruits by length of their names.

class Main {

public  static  void main(String[] args) {

Map<Integer, List<String>> fruitByLength =

Stream.of("apple", "mango", "lemon", "avocado", "cherries")

.collect(Collectors.groupingBy(fruit -> fruit.length()));

fruitByLength.entrySet().stream()

.forEach(entry -> {System.out.println(entry.getKey()); entry.getValue().stream()

.forEach(fruit -> System.out.print(fruit + " "));

System.out.println();});

}}

## 10.5Stats

### 10.5.1Count

Returns the number of values in a stream

class Main {

public  static  void main(String[] args) {

System.out.println(

Stream.of("apple", "mango", "lemon", "avocado", "cherries").count());

}}

### 10.5.2Sum

Returns the sum of an IntStream

class Main {

public  static  void main(String[] args) {

IntStream stream = IntStream.of(1, 3, 4, 7);

System.out.println(stream.sum());

}}

### 10.5.3 Min, max, average

Returns the min, max or average of an IntStream

class Main {

public  static  void main(String[] args) {

IntStream stream = IntStream.of(1, 3, 4, 7);

stream.min().ifPresent(smallest -> System.out.println(smallest));

}}

## 10.6Stats on long values

The interface LongStream is a stream for long values. The methods are the same as with the IntStream. It is possible to convert an IntStream to a LongStream with the method mapToLong()

## 10.7Stats on double values

The interface DoubleStream is a stream for double values. The methods are the same as with the IntStream. It is possible to convert an IntStream to a DoubleStream with the method mapToDouble()

## 10.8 Min and max of other valus

It is possible to give in a Lambda in the min and max methods to determine which are the min and max values. The lambda will implement the functional interface Comparator

class Main {

public  static  void main(String[] args) {

    Stream.of(BigDecimal.valueOf(1.1), BigDecimal.valueOf(0.9), BigDecimal.valueOf(0.5))  

    .min((number1, number2) -> number1.compareTo(number2))

    .ifPresent(smallest -> System.out.println(smallest));

    } }

# 11. Reduce

The methods min, sum, max,… all reduce the values of a stream to one single value. The method reduce() does the same thing, but this method is able to reduce any value to one single value (not only int, double, long values). It is a general-purpose reduction method.

There are 2 versions of the reduce method :

## 11.1 Stream.reduce() with Accumulator

It performs a reduction on the elements of the given stream, using given accumulation function.

class Main {

public  static  void main(String[] args) {

System.out.println(Stream.of(BigDecimal.valueOf(1.1), BigDecimal.valueOf(0.9), BigDecimal.valueOf(0.5))

.reduce(BigDecimal.ZERO, (previousSum, number) -> previousSum.add(number)));

}}

## 11.2 Stream.reduce() with Identity and Accumulator

It performs a reduction on the elements of the given stream, using given identity value, an accumulation function and combining functions. The identity value must be an identity for the combiner function. Combiner is a function which aggregates results of the accumulator. Combiner is called only in a parallel mode to reduce results of accumulators from different threads.

class Main {

public  static  void main(String[] args) {

Stream.of(BigDecimal.valueOf(1.1), BigDecimal.valueOf(0.9), BigDecimal.valueOf(0.5))

.reduce((previousSum, number) -> previousSum.add(number))

.ifPresent(sum -> System.out.println(sum));

}}

# 12Conclusion

Thank you for reading this short introduction to Lambda’s and streams in Java. This guide contains all the information you need to start using Lambda’s yourself. Hopefully you learned a lot and feel ready to start integrating Lamdba’s into your code. If you have any questions you can contact me at [programming_made_easy@outlook.be](mailto:programming_made_easy@outlook.be)

Good luck and have fun!