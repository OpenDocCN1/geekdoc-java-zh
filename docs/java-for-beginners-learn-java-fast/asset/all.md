![](images/00002.jpeg)

Java For Beginners

Learn Java Fast (Free Bonus Video Course Included)

# Contents

[Chapter](#part0000_split_003.html_h.3znysh7) [1:](#part0000_split_003.html_h.3znysh7) [Basic](#part0000_split_003.html_h.3znysh7) [](#part0000_split_003.html_h.3znysh7) [Java](#part0000_split_003.html_h.3znysh7) [](#part0000_split_003.html_h.3znysh7) [Syntax](#part0000_split_003.html_h.3znysh7)

Chapter 2: [About](#part0000_split_012.html_h.emasmt3v2qbw) [](#part0000_split_012.html_h.emasmt3v2qbw) [Object](#part0000_split_012.html_h.emasmt3v2qbw) [](#part0000_split_012.html_h.emasmt3v2qbw) [Oriented](#part0000_split_012.html_h.emasmt3v2qbw) [](#part0000_split_012.html_h.emasmt3v2qbw) [Programming](#part0000_split_012.html_h.emasmt3v2qbw)

Chapter 3: [Class](#part0000_split_014.html_h.g3sfqgg30k79) [](#part0000_split_014.html_h.g3sfqgg30k79) [Fundamentals](#part0000_split_014.html_h.g3sfqgg30k79)

Chapter 4: [Conclusion](#part0000_split_016.html_h.44sinio) [](#part0000_split_016.html_h.44sinio) [+](#part0000_split_016.html_h.44sinio) [FREE](#part0000_split_016.html_h.44sinio) [](#part0000_split_016.html_h.44sinio) [BONUS](#part0000_split_016.html_h.44sinio) [](#part0000_split_016.html_h.44sinio) [VIDEO](#part0000_split_016.html_h.44sinio) [](#part0000_split_016.html_h.44sinio) [COURSE](#part0000_split_016.html_h.44sinio)

Introduction

I want to thank you and congratulate you for downloading the book, “Java for Beginners. Learn Java Fast.”.

This book will give you an overview of the main concepts of programming in the Java language.

Java is the programming language of choice for web developers and is used in Android applications, web sites, web-based gaming and web-based applications. It is one of the easiest languages to learn and I will be covering the fundamental concepts of Java programming.

Thanks again for downloading this book, I hope you enjoy it!

© Copyright 2017 George L - All rights reserved.

This document is geared towards providing exact and reliable information in regards to the topic and issue covered. The publication is sold with the idea that the publisher is not required to render accounting, officially permitted, or otherwise, qualified services. If advice is necessary, legal or professional, a practiced individual in the profession should be ordered.

- From a Declaration of Principles which was accepted and approved equally by a Committee of the American Bar Association and a Committee of Publishers and Associations.

In no way is it legal to reproduce, duplicate, or transmit any part of this document in either electronic means or in printed format. Recording of this publication is strictly prohibited and any storage of this document is not allowed unless with written permission from the publisher. All rights reserved.

The information provided herein is stated to be truthful and consistent, in that any liability, in terms of inattention or otherwise, by any usage or abuse of any policies, processes, or directions contained within is the solitary and utter responsibility of the recipient reader. Under no circumstances will any legal responsibility or blame be held against the publisher for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly.

Respective authors own all copyrights not held by the publisher.

The information herein is offered for informational purposes solely, and is universal as so. The presentation of the information is without contract or any type of guarantee assurance.

The trademarks that are used are without any consent, and the publication of the trademark is without permission or backing by the trademark owner. All trademarks and brands within this book are for clarifying purposes only and are the owned by the owners themselves, not affiliated with this document.

# Chapter 1

# Basic Java Syntax

Java is one of the most versatile of all the computer programming languages and one of the easiest to learn. In this chapter, we will be covering the basic syntax of the language, which is the first thing you must learn:

## Whitespace

Whitespace characters are what makes the java code much easier to read and consist of spaces, newlines, and tabs. Usually, a whitespace character will be ignored by the Java compiler so, even if you were to use large amounts of it in your code, the actual bytecode that is generated would be quite small and would have an impact on system memory. Do be careful of excessive use, though, because it can make the code hard to read.

## Styles

Styles is all about how the source code is formatted. A Java file is normally formatted so that it is easy to read and that is where style guidelines come into play. These are standards that are usually set by an individual or an organization; this formatting is ignored by the Java compiler and it includes the use of indentation, newlines, and spacing. You can also use comments to format the code and add in notes so that anyone else reading your code can see what is going on.

Styles must deal with the formatting of the source codes. Generally, we format a Java file so that it becomes easier to read. To format a Java file, we need to look at style guidelines. Style guidelines are mainly standards followed by company, organization or individual. Generally, when setting guidelines developers keep in mind formatting of code which is easier to read. This formatting is ignored by the compiler. Styles include the use of indentation, spacing, and newlines which format source codes as per developers. Comments are used to format code and add notes so that any other programmer reading the code gets the idea behind the code.
Example 1 – Bad Formatting

<b>// Bad Style Coding

// Not easy to read, no indents used

public class Welcome {

public static void main(String[] args){

int i = 0; // single line comment

for(int i=0;i<=10;i++){

int j = 1;

int k = j;

System.out.println("Welcome to comments");

}

} </b>

Example 2 – Good Formatting

<b>// Good Style Coding

// Very easy to read, excellent use of indents

public class Welcome {

  public static void main(String[] args){

    int i = 0; // single line comment

    for(int i=0;i<=10;i++){

      int j = 1;

      int k = j;

      System.out.println("Welcome to comments");

    }

  }

}</b>

## Comments

Comments are very important because they allow you to add notes to your source code, thus making what could be a complicated piece of code much easier to read and to debug. They are not read by the Java compiler so they will have no impact on memory.  There are a couple of types of comments:

● Single line – begins with a // and anything written between // and the end of the line is ignored

● Multi-line – begins with /* and ends with */ - anything written in between is ignored and this can cover many lines of your code.

<b>public class Welcome {

  public static void main(String[] args){

    int i = 0; // this is a single line comment

    for(int i=0;i<=10;i++){

     /* int j = 1;

        int k = j;

        System.out.println("Welcome to comments"); */

     /* multi-line comment, whole code in between will be commented out */

    }

  }

}</b>

## Identifiers

Identifiers are the collective names that are given to methods, classes and variables in Java. There are rules about the naming conventions for identifiers and these follow:

● Identifiers must start with a Unicode character, underscore or dollar sign

● Numbers can be included after the first character, along with dollar signs, underscores and Unicode characters

● Try to avoid using currency symbols, like $ if you can

● Identifier names are case sensitive

● You cannot use a reserved keyword

● Use capital letters to separate two or more words in the name

Valid Identifiers                            Invalid Identifiers              Comments

tree                                                        Tree                                                        case-sensitive

my2var                                          2myVar                                          digit as the first character

myNewVar                                          my@new@var                            invalid character - @

switching                                          switch                                                        a reserved keyword

## Reserved Keywords

There are several words in Java that are reserved for use by the language and you cannot use them for anything other than their intended purpose, especially not for naming. The reserved keywords are:

● abstract

● assert

● boolean

● break

● byte

● case

● catch

● char

● class

● const

● continue

● default

● do

● double

● else

● enum

● extends

● final

● finally

● float

● for

● goto

● if

● implements

● import

● instanceof

● int

● interface

● long

● native

● new

● package

● private

● protected

● public

● return

● short

● static

● strictfp

● super

● switch

● synchronized

● this

● throw

● throws

● transient

● try

● void

● volatile

● while

## Separators

These are used a lot in Java and each has its own use:

Separator                              Comments                                                                     

() For declaring methods/passing arguments             

{}                                          Code block                                                                                   

[]                                          Defines an array and accesses array element             

;                                          The end of a statement                                                       

,                                          Argument separation                                                             

.                                          Calling operator for methods & objects       

:                                          For each loop                                                                           

## Literals

Java uses literals to give us an idea of the data type:

Literal Types                            Example                                          Comments

Integer                                          10                                                        no distinguisher

Long                                                        100L                                                        L for Long

Null                                                        null                                                        keyword

String                                                        “Java Programs”                            double quotes for a string

Character                                          ‘a’                                                        single quotes for character

Double Floating Point              3123.5                                                        no distinguisher

Floating Point                            3.5f                                                        f for float

Boolean                                          true                                                        keyword for true or false

Other than separators Java also uses literals. Literals give us a brief idea about the data types. Let us view them in a tabular form 

## Escape Sequences

We use escape sequences in strings to escape a specific character:

Escape Sequence                                          Replaced

/t                                                                      Horizontal tab

/n                                                                      New line

/r                                                                      Carriage return

/f                                                                      Form feed

/”                                                                      Double quote

/’                                                                      Single quote

//                                                                      Backslash

# Chapter 2

# About Object Oriented Programming

Java is an object-oriented programming (OOP) language, organized around objects and data instead of actions and logic. Before you can start writing your own Java code, you need to be aware of the basics of the language:

● Abstraction – picking out common features of procedures and objects

● Class – category of objects, a definition of the properties of the objects in the class

● Encapsulation – combining elements to make something new

● Information Hiding – hiding details of functions or objects to reduce code complexity

● Inheritance – a representation of the “is a” relationship of different classes

● Interface – codes and language used by applications to communicate

● Messaging – communication form in parallel and OOP programming

● Object – self-contained, consisting of procedure and data used for data manipulation

● Polymorphism – ability to process an object per its class or data type

● Procedure – part of the program that does something specific

## The Advantages of OOP

The main advantage of OOP is that programmers can create modules that don’t need to be changed when a new object type is added. Programmers can just create a new object that will inherit their features from those that already exist, making it an easy language to modify.

# Chapter 3

# Class Fundamentals

Classes are a fundamental part of Java and are incredibly powerful. A class is used to define a new data type, which is then used to create an object of the type defined. In basic, a class is a template for the object and the object is an instance of the class. Because of that, you will see the words instance and object used interchangeably.

## The Form of a Class

To define a class, you must declare the exact nature and form of it. To do this, you must specify the data in the class and the code that will operate on the data. Most classes will contain both although some only have data or code in them.

You declare a class by using the class keyword and the following shows you the general form of a class:

             class classname {

     type instance-variable1;

     type instance-variable2;

     // ..

type instance-variableN;

type methodname1(parameter-list) {

     //body of method

}

type methodname2(parameter-list) {

     //body of method

}

     //..

type methodnameN(parameter-list) {

     // body of method

}

}

 The variables, or data, that are defined in the class are known as instance variables and the code itself is held within a method. The methods and variables that are defined in a class are called members and, in most cases, the variables will be acted on and accessed by the specific methods in the class. The methods determine how the data is used.

# Chapter 4

# Conclusion + FREE BONUS VIDEO COURSE

![Blackbird (1).jpg](images/00001.jpeg)

Finally, if you enjoyed this book, then I’d like to ask you for a favor, would you be kind enough to leave a review for this book on Amazon? It’d be greatly appreciated!

=> [Click](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [here](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [to](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [leave](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [a](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [review](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [for](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [this](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [book](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [on](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top) [Amazon](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top)[!](https://www.amazon.com/ap/signin?_encoding=UTF8&openid.assoc_handle=usflex&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.mode=checkid_setup&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&openid.pape.max_auth_age=0&openid.return_to=https%3A%2F%2Fwww.amazon.com%2Freview%2Fcreate-review%3Fie%3DUTF8%26asin%3DB06XQM477F%26channel%3Dglance-detail%26ref_%3Dcm_cr_dp_d_wr_but_top)

Thank you again for reading this book! 

I hope this book was able to help you to understand the fundamentals of Java programming. 

The next step is to take your learning further. Learning the fundamentals is only the beginning, the start of a long and fruitful journey into the world of computer programming.

I recommend you check out this [FREE](http://javavideocourse.weebly.com) [](http://javavideocourse.weebly.com) [BONUS](http://javavideocourse.weebly.com) [](http://javavideocourse.weebly.com) [VIDEO](http://javavideocourse.weebly.com) [](http://javavideocourse.weebly.com) [COURSE](http://javavideocourse.weebly.com) [](http://javavideocourse.weebly.com) for more complete information.

If the link does not work go here: [http](http://javavideocourse.weebly.com/)[://](http://javavideocourse.weebly.com/)[javavideocourse](http://javavideocourse.weebly.com/)[.](http://javavideocourse.weebly.com/)[weebly](http://javavideocourse.weebly.com/)[.](http://javavideocourse.weebly.com/)[com](http://javavideocourse.weebly.com/)

Thank you and good luck!