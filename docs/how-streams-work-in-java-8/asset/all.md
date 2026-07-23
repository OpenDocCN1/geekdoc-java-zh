![](cover.jpeg)

How Streams work in Java 8

VLIGHT

Table Of Contents

[Intro to Streams in Java 8](#part0000_split_002.html__Toc478926448)

[How Streams work in Java 8](#part0000_split_003.html__Toc478926449)

[How to filter a collections in Java 8](#part0000_split_004.html__Toc478926450)

# 
Intro to Streams in Java 8

□  Streams in Java 8 are completely different from InputStream or OutputStream before Java 8

□  Streams in Java 8 are Monads which is a concept in functional programming languages

□  Monads in a functional programming language is nothing but a structure which represents computations defined as Sequences of Steps

□  In a functional programming language, a type with a monad structure meanings to chain operations, or nest functions  of that type together

□  Stream in Java 8 lets you to process data declaratively and leverage multicore architecture without the need to write any specific code for it

□  There are 5 main characteristics of a Stream in Java 8 as follow:

 ‡  Sequence of elements

 ‡  Source

 ‡  Aggregate operations

 ‡  Pipelining

 ‡  Automatic iterations

# 
How Streams work in Java 8

▬You should familiar with Lambda Expressions, Functional Interfaces, and Method References if you want to fully understanding how Streams work in Java 8

▬Stream Operations are either intermediate or terminal

+ Intermediate Operations: These operations will return a stream so you can chain multiple intermediate operations without using semicolons

+ Terminal Operations: These operations are either void or return a non-stream result

▬Sample Code

List<String> nameList = Arrays.asList

("Van", "Nam","Tuan","Tien","Hoang");

 nameList.stream()

                  .filter(name -> name.startsWith("T"))

                  .map(String::toLowerCase)

                  .sorted()

                  .forEach(System.out::println);

Output

tien

tuan

►  Notes

▬In the above example

+ filter(), map(), and sorted() methods are intermediate operations

+ forEach() method is a terminal operation

▬In Java 8, a Stream can be created from various data sources especially Collections

▬List and Set in Java 8 support new methods including

+ stream(): This method is used to create a sequential stream

+ parallelStream(): This method is used to create a parallel stream which is capable of operating on multiple threads

▬Calling a method stream() on a List object will return a regular stream object but you do not need to create Collections in order to work with streams

Example

Arrays.asList("Van01", "Van02", "Van03")

           .stream()

           .findFirst()

          .ifPresent(System.out::println);

Output

Van01

▬You can use Stream.of() to create a stream from a bunch of object references

Example

Stream.of("Lan01", "Lan02", "Lan03")

             .findFirst()

             .ifPresent(System.out::println);

Output

Lan01

# 
How to filter a collections in Java 8

▬Java 8 provides new features to support filtering of elements in a Collection

▬You can filter a Collection like List, Set, or Map in Java 8 using filter() method of Stream class with following steps

+ Step 01: You need to obtain a Stream from a Collection by calling stream() method

+ Step 02: And then you can use filter() method which takes a Predicate as only argument

►  Notes

+ The filter() method does not remove elements which match the condition given in predicate, but the filter() method will select elements in an output stream

+ The filter() method is defined in the Stream class. It takes a Predicate object and then returns a stream consisting of the elements from original stream which matches the given Predicate

▬Streams in Java 8 support the map() method which takes a function as an argument to project the elements of a stream into another form