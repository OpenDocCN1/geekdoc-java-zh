![](images/cover.jpg)

Programming in Haskell

Haskell is one of the leading languages for teaching functional programming, enabling students to write simpler and cleaner code, and to learn how to structure and reason about programs.

This introduction is ideal for beginners: it requires no previous programming experience and all concepts are explained from first principles with the aid of carefully chosen examples. Each chapter includes a series of exercises, ranging from the straightforward to extended projects, along with suggestions for further reading on more advanced topics. The presentation is clear and simple, and benefits from having been refined and class-tested over several years.

Features:

•  Powerpoint slides for each chapter freely available for instructors and students from the book’s website

•  Solutions to exercises, and examination questions (with solutions) available to instructors

•  All the code in the book is fully compliant with the latest release of Haskell, and can be downloaded from the web.

•  Written by a leading Haskell researcher and instructor, well known for his teaching skills

•  Can be used with courses, or as a stand-alone text for self-learning

Graham Hutton has worked in four of the leading centres for research and teaching on functional programming. He has more than 15 years of experience in functional programming research, during which time he has published more than 30 research articles, chaired the Haskell Workshop, and edited a special issue on Haskell of the *Journal of Functional Programming*. He also has more than 10 years’ experience in teaching Haskell, and in promoting the use of functional programming in the curriculum.

**Programming in Haskell**

Graham Hutton

*University of Nottingham*

![images](images/image03_00.png)

CAMBRIDGE UNIVERSITY PRESS

Cambridge, New York, Melbourne, Madrid, Cape Town, Singapore, São Paulo, Delhi, Mexico City

Cambridge University Press

The Edinburgh Building, Cambridge CB2 8RU, UK

Published in the United States of America by Cambridge University Press, New York

[www.cambridge.org](http://www.cambridge.org)

Information on this title: [www.cambridge.org/9780521692694](http://www.cambridge.org/9780521692694)

© G. Hutton 2007

This publication is in copyright. Subject to statutory exception and to the provisions of relevant collective licensing agreements, no reproduction of any part may take place without the written permission of Cambridge University Press.

First published 2007

8th printing 2012

Printed and bound by MPG Books Group, UK

*A catalogue record for this publication is available from the British Library*

*Library of Congress Cataloguing in Publication data*

ISBN 978-0-521-87172-3 Hardback

ISBN 978-0-521-69269-4 Paperback

* * *

Cambridge University Press has no responsibility for the persistence or accuracy of URLs for external or third-party internet websites referred to in this publication, and does not guarantee that any content on such websites is, or will remain, accurate or appropriate. Information regarding prices, travel timetables and other factual information given in this work are correct at the time of first printing but Cambridge University Press does not guarantee the accuracy of such information thereafter.

* * *

*For Annette, Callum and Tom*

Contents

[Preface](#07_preface_title.html)

[**Chapter 1**  Introduction](#08_chapter_title_1.html_pg-13-1)

[1.1  Functions](#08_chapter_title_1.html_pg-13-10)

[1.2  Functional programming](#08_chapter_title_1.html_pg-14-28)

[1.3  Features of Haskell](#08_chapter_title_1.html_pg-16-21)

[1.4  Historical background](#08_chapter_title_1.html_pg-18-1)

[1.5  A taste of Haskell](#08_chapter_title_1.html_pg-18-51)

[1.6  Chapter remarks](#08_chapter_title_1.html_pg-21-29)

[1.7  Exercises](#08_chapter_title_1.html_pg-21-41)

[**Chapter 2**  First steps](#09_chapter_title_2.html_pg-22-1)

[2.1  The Hugs system](#09_chapter_title_2.html_pg-22-10)

[2.2  The standard prelude](#09_chapter_title_2.html_pg-22-27)

[2.3  Function application](#09_chapter_title_2.html_pg-24-129)

[2.4  Haskell scripts](#09_chapter_title_2.html_pg-25-131)

[2.5  Chapter remarks](#09_chapter_title_2.html_pg-28-12)

[2.6  Exercises](#09_chapter_title_2.html_pg-28-22)

[**Chapter 3**  Types and classes](#10_chapter_title_3.html_pg-29-1)

[3.1  Basic concepts](#10_chapter_title_3.html_pg-29-11)

[3.2  Basic types](#10_chapter_title_3.html_pg-30-66)

[3.3  List types](#10_chapter_title_3.html_pg-32-1)

[3.4  Tuple types](#10_chapter_title_3.html_pg-32-69)

[3.5  Function types](#10_chapter_title_3.html_pg-33-9)

[3.6  Curried functions](#10_chapter_title_3.html_pg-33-56)

[3.7  Polymorphic types](#10_chapter_title_3.html_pg-35-1)

[3.8  Overloaded types](#10_chapter_title_3.html_pg-35-93)

[3.9  Basic classes](#10_chapter_title_3.html_pg-36-70)

[3.10  Chapter remarks](#10_chapter_title_3.html_pg-40-95)

[3.11  Exercises](#10_chapter_title_3.html_pg-40-108)

[**Chapter 4**  Defining functions](#11_chapter_title_4.html_pg-42-1)

[4.1  New from old](#11_chapter_title_4.html_pg-42-10)

[4.2  Conditional expressions](#11_chapter_title_4.html_pg-43-1)

[4.3  Guarded equations](#11_chapter_title_4.html_pg-43-50)

[4.4  Pattern matching](#11_chapter_title_4.html_pg-44-3)

[4.5  Lambda expressions](#11_chapter_title_4.html_pg-46-94)

[4.6  Sections](#11_chapter_title_4.html_pg-48-1)

[4.7  Chapter remarks](#11_chapter_title_4.html_pg-48-82)

[4.8  Exercises](#11_chapter_title_4.html_pg-49-1)

[**Chapter 5**  List comprehensions](#12_chapter_title_5.html_pg-50-1)

[5.1  Generators](#12_chapter_title_5.html_pg-50-12)

[5.2  Guards](#12_chapter_title_5.html_pg-51-82)

[5.3  The *zip* function](#12_chapter_title_5.html_pg-52-113)

[5.4  String comprehensions](#12_chapter_title_5.html_pg-53-117)

[5.5  The Caesar cipher](#12_chapter_title_5.html_pg-54-71)

[5.6  Chapter remarks](#12_chapter_title_5.html_pg-58-41)

[5.7  Exercises](#12_chapter_title_5.html_pg-58-54)

[**Chapter 6**  Recursive functions](#13_chapter_title_6.html_pg-60-1)

[6.1  Basic concepts](#13_chapter_title_6.html_pg-60-10)

[6.2  Recursion on lists](#13_chapter_title_6.html_pg-61-55)

[6.3  Multiple arguments](#13_chapter_title_6.html_pg-64-17)

[6.4  Multiple recursion](#13_chapter_title_6.html_pg-65-15)

[6.5  Mutual recursion](#13_chapter_title_6.html_pg-65-62)

[6.6  Advice on recursion](#13_chapter_title_6.html_pg-67-16)

[6.7  Chapter remarks](#13_chapter_title_6.html_pg-71-15)

[6.8  Exercises](#13_chapter_title_6.html_pg-71-21)

[**Chapter 7**  Higher-order functions](#14_chapter_title_7.html_pg-73-1)

[7.1  Basic concepts](#14_chapter_title_7.html_pg-73-11)

[7.2  Processing lists](#14_chapter_title_7.html_pg-74-51)

[7.3  The *foldr* function](#14_chapter_title_7.html_pg-76-52)

[7.4  The *foldl* function](#14_chapter_title_7.html_pg-78-132)

[7.5  The composition operator](#14_chapter_title_7.html_pg-80-60)

[7.6  String transmitter](#14_chapter_title_7.html_pg-81-27)

[7.7  Chapter remarks](#14_chapter_title_7.html_pg-84-77)

[7.8  Exercises](#14_chapter_title_7.html_pg-84-88)

[**Chapter 8**  Functional parsers](#15_chapter_title_8.html_pg-86-1)

[8.1  Parsers](#15_chapter_title_8.html_pg-86-11)

[8.2  The parser type](#15_chapter_title_8.html_pg-87-1)

[8.3  Basic parsers](#15_chapter_title_8.html_pg-87-96)

[8.4  Sequencing](#15_chapter_title_8.html_pg-88-91)

[8.5  Choice](#15_chapter_title_8.html_pg-90-25)

[8.6  Derived primitives](#15_chapter_title_8.html_pg-90-79)

[8.7  Handling spacing](#15_chapter_title_8.html_pg-93-6)

[8.8  Arithmetic expressions](#15_chapter_title_8.html_pg-94-1)

[8.9  Chapter remarks](#15_chapter_title_8.html_pg-97-41)

[8.10  Exercises](#15_chapter_title_8.html_pg-97-51)

[**Chapter 9**  Interactive programs](#16_chapter_title_9.html_pg-99-1)

[9.1  Interaction](#16_chapter_title_9.html_pg-99-11)

[9.2  The input/output type](#16_chapter_title_9.html_pg-100-8)

[9.3  Basic actions](#16_chapter_title_9.html_pg-100-91)

[9.4  Sequencing](#16_chapter_title_9.html_pg-101-55)

[9.5  Derived primitives](#16_chapter_title_9.html_pg-102-21)

[9.6  Calculator](#16_chapter_title_9.html_pg-103-74)

[9.7  Game of life](#16_chapter_title_9.html_pg-106-13)

[9.8  Chapter remarks](#16_chapter_title_9.html_pg-109-23)

[9.9  Exercises](#16_chapter_title_9.html_pg-109-41)

[**Chapter 10**  Declaring types and classes](#17_chapter_title_10.html_pg-29-3)

[10.1  Type declarations](#17_chapter_title_10.html_pg-111-10)

[10.2  Data declarations](#17_chapter_title_10.html_pg-112-25)

[10.3  Recursive types](#17_chapter_title_10.html_pg-114-33)

[10.4  Tautology checker](#17_chapter_title_10.html_pg-117-5)

[10.5  Abstract machine](#17_chapter_title_10.html_pg-121-16)

[10.6  Class and instance declarations](#17_chapter_title_10.html_pg-123-14)

[10.7  Chapter remarks](#17_chapter_title_10.html_pg-126-15)

[10.8  Exercises](#17_chapter_title_10.html_pg-126-36)

[**Chapter 11**  The countdown problem](#18_chapter_title_11.html_pg-128-1)

[11.1  Introduction](#18_chapter_title_11.html_pg-128-11)

[11.2  Formalising the problem](#18_chapter_title_11.html_pg-129-32)

[11.3  Brute force solution](#18_chapter_title_11.html_pg-131-138)

[11.4  Combining generation and evaluation](#18_chapter_title_11.html_pg-132-39)

[11.5  Exploiting algebraic properties](#18_chapter_title_11.html_pg-133-63)

[11.6  Chapter remarks](#18_chapter_title_11.html_pg-135-97)

[11.7  Exercises](#18_chapter_title_11.html_pg-135-98)

[**Chapter 12**  Lazy evaluation](#19_chapter_title_12.html_pg-136-1)

[12.1  Introduction](#19_chapter_title_12.html_pg-136-11)

[12.2  Evaluation strategies](#19_chapter_title_12.html_pg-137-42)

[12.3  Termination](#19_chapter_title_12.html_pg-140-29)

[12.4  Number of reductions](#19_chapter_title_12.html_pg-141-22)

[12.5  Infinite structures](#19_chapter_title_12.html_pg-142-43)

[12.6  Modular programming](#19_chapter_title_12.html_pg-144-15)

[12.7  Strict application](#19_chapter_title_12.html_pg-146-116)

[12.8  Chapter remarks](#19_chapter_title_12.html_pg-149-1)

[12.9  Exercises](#19_chapter_title_12.html_pg-149-11)

[**Chapter 13**  Reasoning about programs](#20_chapter_title_13.html_pg-151-1)

[13.1  Equational reasoning](#20_chapter_title_13.html_pg-151-11)

[13.2  Reasoning about Haskell](#20_chapter_title_13.html_pg-152-22)

[13.3  Simple examples](#20_chapter_title_13.html_pg-153-46)

[13.4  Induction on numbers](#20_chapter_title_13.html_pg-154-31)

[13.5  Induction on lists](#20_chapter_title_13.html_pg-157-11)

[13.6  Making append vanish](#20_chapter_title_13.html_pg-158-61)

[13.7  Compiler correctness](#20_chapter_title_13.html_pg-162-9)

[13.8  Chapter remarks](#20_chapter_title_13.html_pg-166-27)

[13.9  Exercises](#20_chapter_title_13.html_pg-166-36)

[**Appendix A**  Standard prelude](#21_appendix_title.html_pg-168-3)

[A.1  Classes](#21_appendix_title.html_pg-168-9)

[A.2  Logical values](#21_appendix_title.html_pg-169-52)

[A.3  Characters and strings](#21_appendix_title.html_pg-170-1)

[A.4  Numbers](#21_appendix_title.html_pg-171-13)

[A.5  Tuples](#21_appendix_title.html_pg-172-1)

[A.6  Maybe](#21_appendix_title.html_pg-172-15)

[A.7  Lists](#21_appendix_title.html_pg-172-21)

[A.8  Functions](#21_appendix_title.html_pg-176-9)

[A.9  Input/output](#21_appendix_title.html_pg-176-44)

[**Appendix B**  Symbol table](#22_conclusion_title.html_pg-178-3)

[*Bibliography*](#23_bibliography_title.html)

[*Index*](#24_index_title.html_pg-181-1)

Preface

… there are two ways of constructing a software design: One way is to make it so simple that there are *obviously* no deficiencies and the other way is to make it so complicated that there are no *obvious* deficiencies. The first method is far more difficult.

*Tony Hoare, 1980 ACM Turing Award Lecture*

This book is about an approach to programming in which simplicity, clarity, and elegance are the key goals. More specifically, it is an introduction to the functional style of programming, using the language Haskell.

The functional style is quite different to that promoted by most current languages, such as Java, C++, C, and Visual Basic. In particular, most current languages are closely linked to the underlying hardware, in the sense that programming is based upon the idea of changing stored values. In contrast, Haskell promotes a more abstract style of programming, based upon the idea of applying functions to arguments. As we shall see, moving to this higher-level leads to considerably simpler programs, and supports a number of powerful new ways to structure and reason about programs.

The book is primarily aimed at students studying computing science at university level, but is also appropriate for a broader spectrum of readers who would like to learn about programming in Haskell. No previous programming experience is required or assumed, and all the concepts are explained from first principles, with the aid of carefully chosen examples.

The version of Haskell used in the book is Haskell 98, the standard version of the language, for which the recently published definition is the culmination of fifteen years of work by its designers. As this is an introductory text, we do not attempt to cover all aspects of Haskell and its associated libraries. Around half of the book is dedicated to introducing the main features of the language, while the other half comprises examples and case studies of programming of Haskell. Each chapter includes a series of exercises, and suggestions for further reading on more advanced and specialist topics.

The book is based upon course material that has been refined and class-tested over many years at the University of Nottingham. Most of the material from the book can be covered in twenty hours of lectures, supported by approximately forty hours of private study, practical sessions in a supervised laboratory, and take-home programming courseworks. However, additional time would be required to cover some of the later chapters in more detail, along with some of the later programming examples.

The website for the book provides a range of supporting material, including Powerpoint slides for each chapter, and Haskell code for each of the extended examples. Instructors can also obtain model answers to the exercises for each chapter, together with a large collection of exam questions and their model answers, by emailing solutions@cambridge.org.

Acknowledgements

The Foundations of Programming group at the University of Nottingham is an excellent environment in which to do research and teaching on functional programming. I am grateful to the University for providing a sabbatical to start work on this book; all the students and tutors on my Haskell courses for their feedback; and Thorsten Altenkirch, Neil Ghani, Mark Jones (now at Portland State), Conor McBride, and Henrik Nilsson in the FOP group for our many discussions about functional ideas and how to present them.

I would also like to thank David Tranah and Dawn Preston for their editorial work at Cambridge University Press; Mark Jones for the Hugs interpreter for Haskell; Ralf Hinze and Andres Löh for the lhs2TeX system for typesetting Haskell; Rik van Geldrop and Jaap van der Woude for their feedback on using drafts of the book; Kees van den Broek, Frank Heitmann, and Bill Tonkin for pointing out errors; Ian Bayley and the anonymous reviewers for useful comments; and Joel Wright for timing the countdown programs.

Graham Hutton

Nottingham, 2006

chapter 1

**Introduction**

In this chapter we set the stage for the rest of the book. We start by reviewing the notion of a function, then introduce the concept of functional programming, summarise the main features of Haskell and its history, and conclude with two small examples that give a taste of Haskell.

![](images/line.jpg)

1.1 Functions

In Haskell, a *function* is a mapping that takes one or more arguments and produces a single result, and is defined using an equation that gives a name for the function, a name for each of its arguments, and a body that specifies how the result can be calculated in terms of the arguments.

For example, a function *double* that takes a number *x* as its argument, and produces the result *x* + *x*, can be defined by the following equation:

![image](images/image15_01.jpg)

When a function is applied to actual arguments, the result is obtained by substituting these arguments into the body of the function in place of the argument names. This process may immediately produce a result that cannot be further simplified, such as a number. More commonly, however, the result will be an expression containing other function applications, which must then be processed in the same way to produce the final result.

For example, the result of the application *double* 3 of the function *double* to the number 3 can be determined by the following calculation, in which each step is explained by a short comment in curly parentheses:

![image](images/image13_00.jpg)

Similarly, the result of the nested application *double* (*double* 2) in which the function *double* is applied twice can be calculated as follows:

![image](images/image14_00.jpg)

Alternatively, the same result could also be calculated by starting with the outer application of the function *double* rather than the inner:

![image](images/image14_01.jpg)

However, this calculation requires two more steps than our original version, because the expression *double* 2 is duplicated in the first step and hence simplified twice. In general, the order in which functions are applied in a calculation does not affect the value of the final result, but it may affect the number of steps required, and may affect whether the calculation process terminates. These issues are explored in more detail in [chapter 12](#19_chapter_title_12.html).

![](images/line.jpg)

1.2 Functional programming

What is functional programming? Opinions differ, and it is difficult to give a precise definition. Generally speaking, however, functional programming can be viewed as a *style* of programming in which the basic method of computation is the application of functions to arguments. In turn, a functional programming language is one that *supports* and *encourages* the functional style.

To illustrate these ideas, let us consider the task of computing the sum of the integers (whole numbers) between one and some larger number *n*. In most current programming languages, this would normally be achieved using two variables that store values that can be changed over time, one such variable used to count up to *n*, and the other used to accumulate the total.

For example, if we use the assignment symbol := to change the value of a variable, and the keywords **repeat** and **until** to repeatedly execute a sequence of instructions until a condition is satisfied, then the following sequence of instructions computes the required sum:

![image](images/image15_00.jpg)

That is, we first initialise both the counter and the total to zero, and then repeatedly increment the counter and add this value to the total until the counter reaches *n*, at which point the computation stops.

In the above program, the basic method of computation is changing stored values, in the sense that executing the program results in a sequence of assignments. For example, the case of *n* = 5 gives the following sequence, in which the final value assigned to the variable *total* is the required sum:

![image](images/table15_01.jpg)

In general, programming languages in which the basic method of computation is changing stored values are called *imperative* languages, because programs in such languages are constructed from imperative instructions that specify precisely how the computation should proceed.

Now let us consider computing the sum of the numbers between one and *n* using Haskell. This would normally be achieved using two library functions, one called [*. .*] used to produce the list of numbers between one and *n*, and the other called *sum* used to produce the sum of this list:

![image](images/image17_00.jpg)

In this program, the basic method of computation is applying functions to arguments, in the sense that executing the program results in a sequence of applications. For example, the case of *n* = 5 gives the following sequence, in which the final result is the required sum:

![image](images/image15_02.jpg)

Most imperative languages support some form of programming with functions, so the Haskell program *sum* [1 *. .* *n*] could be translated into such languages. However, most imperative languages do not *encourage* programming in the functional style. For example, many languages discourage or prohibit functions from being stored in data structures such as lists, from constructing intermediate structures such as the list of numbers in the above example, from taking functions as arguments or producing functions as results, or from being defined in terms of themselves. In contrast, Haskell imposes no such restrictions on how functions can be used, and provides a range of features to make programming with functions both simple and powerful.

![](images/line.jpg)

1.3 Features of Haskell

For reference, the main features of Haskell are listed below, along with the particular chapters of this book that give further details.

•  **Concise programs** ([chapters 2](#09_chapter_title_2.html) and [4](#11_chapter_title_4.html))

Due to the high-level nature of the functional style, programs written in Haskell are often much more *concise* than in other languages, as illustrated by the example in the previous section. Moreover, the syntax of Haskell has been designed with concise programs in mind, in particular by having few keywords, and by allowing indentation to be used to indicate the structure of programs. Although it is difficult to make an objective comparison, Haskell programs are often between two and ten times shorter than programs written in other current languages.

•  **Powerful type system** ([chapters 3](#10_chapter_title_3.html) and [10](#17_chapter_title_10.html))

Most modern programming languages include some form of *type system* to detect incompatibility errors, such as attempting to add a number and a character. Haskell has a type system that requires little type information from the programmer, but allows a large class of incompatibility errors in programs to be automatically detected prior to their execution, using a sophisticated process called type inference. The Haskell type system is also more powerful than most current languages, by allowing functions to be “polymorphic” and “overloaded”.

•  **List comprehensions** ([chapter 5](#12_chapter_title_5.html))

One of the most common ways to structure and manipulate data in computing is using lists. To this end, Haskell provides lists as a basic concept in the language, together with a simple but powerful *comprehension* notation that constructs new lists by selecting and filtering elements from one or more existing lists. Using the comprehension notation allows many common functions on lists to be defined in a clear and concise manner, without the need for explicit recursion.

•  **Recursive functions** ([chapter 6](#13_chapter_title_6.html))

Most non-trivial programs involve some form of repetition or looping. In Haskell, the basic mechanism by which looping is achieved is by using *recursive* functions that are defined in terms of themselves. Many computations have a simple and natural definition in terms of recursive functions, particularly when “pattern matching” and “guards” are used to separate different cases into different equations.

•  **Higher-order functions** ([chapter 7](#14_chapter_title_7.html))

Haskell is a *higher-order* functional language, which means that functions can freely take functions as arguments and produce functions as results. Using higher-order functions allows common programming patterns, such as composing two functions, to be defined as functions within the language itself. More generally, higher-order functions can be used to define “domain-specific languages” within Haskell, such as for list processing, parsing, and interactive programming.

•  **Monadic effects** ([chapters 8](#15_chapter_title_8.html) and [9](#16_chapter_title_9.html))

Functions in Haskell are pure functions that take all their input as arguments and produce all their output as results. However, many programs require some form of *side effect* that would appear to be at odds with purity, such as reading input from the keyboard, or writing output to the screen, while the program is running. Haskell provides a uniform framework for handling effects without compromising the purity of functions, based upon the mathematical notion of a *monad*.

•  **Lazy evaluation** ([chapter 12](#19_chapter_title_12.html))

Haskell programs are executed using a technique called *lazy evaluation*, which is based upon the idea that no computation should be performed until its result is actually required. As well as avoiding unnecessary computation, lazy evaluation ensures that programs terminate whenever possible, encourages programming in a modular style using intermediate data structures, and even allows data structures with an infinite number of elements, such as an infinite list of numbers.

•  **Reasoning about programs** ([chapter 13](#20_chapter_title_13.html))

Because programs in Haskell are pure functions, simple *equational reasoning* can be used to execute programs, to transform programs, to prove properties of programs, and even to derive programs directly from specifications of their behaviour. Equational reasoning is particularly powerful when combined with the use of “induction” to reason about functions that are defined using recursion.

![](images/line.jpg)

1.4 Historical background

Many of the features of Haskell are not new, but were first introduced by other languages. To help place Haskell in context, some of the main historical developments related to the language are briefly summarised below:

•  In the 1930s, Alonzo Church developed the lambda calculus, a simple but powerful mathematical theory of functions.

•  In the 1950s, John McCarthy developed Lisp (“LISt Processor”), generally regarded as being the first functional programming language. Lisp had some influences from the lambda calculus, but still adopted variable assignments as a central feature of the language.

•  In the 1960s, Peter Landin developed ISWIM (“If you See What I Mean”), the first pure functional programming language, based strongly on the lambda calculus and having no variable assignments.

•  In the 1970s, John Backus developed FP (“Functional Programming”), a functional programming language that particularly emphasised the idea of higher-order functions and reasoning about programs.

•  Also in the 1970s, Robin Milner and others developed ML (“Meta-Language”), the first of the modern functional programming languages, which introduced the idea of polymorphic types and type inference.

•  In the 1970s and 1980s, David Turner developed a number of lazy functional programming languages, culminating in the commercially produced language Miranda (meaning “admirable”).

•  In 1987, an international committee of researchers initiated the development of Haskell (named after the logician Haskell Curry), a standard lazy functional programming language.

•  In 2003, the committee published the Haskell Report, which defines a longawaited stable version of Haskell, and is the culmination of fifteen years of work on the language by its designers.

It is worthy of note that three of the above researchers — McCarthy, Backus, and Milner — have each received the ACM Turing Award, which is generally regarded as being the computing equivalent of a Nobel prize.

![](images/line.jpg)

1.5 A taste of Haskell

We conclude this chapter with two small examples that give a taste of programming in Haskell. First of all, recall the function *sum* used earlier in this chapter, which produces the sum of a list of numbers. In Haskell, this function can be defined using the following two equations:

![image](images/image21_00.jpg)

The first equation states that the sum of the empty list is zero, while the second states that the sum of any non-empty list comprising a first number *x* and a remaining list of numbers *xs* is given by adding *x* and the sum of *xs*. For example, the result of *sum* [1, 2, 3] can be calculated as follows:

![image](images/image19_00.jpg)

Note that even though the function *sum* is defined in terms of itself and is hence recursive, it does not loop forever. In particular, each application of *sum* reduces the length of the argument list by one, until the list eventually becomes empty, at which point the recursion stops. Returning zero as the sum of the empty list is appropriate because zero is the *identity* for addition. That is, 0 + *x* = *x* and *x* + 0 = *x* for any number *x*.

In Haskell, every function has a *type* that specifies the nature of its arguments and results, which is automatically inferred from the definition of the function. For example, the function *sum* has the following type:

![image](images/image21_01.jpg)

This type states that for any type *a* of numbers, *sum* is a function that maps a list of such numbers to a single such number. Haskell supports many different types of numbers, including integers such as 123, and “floating-point” numbers such as 3.14159. Hence, for example, *sum* could be applied to a list of integers, as in the calculation above, or to a list of floating-point numbers.

Types provide useful information about the nature of functions, but, more importantly, their use allows many errors in programs to be automatically detected prior to executing the programs themselves. In particular, for every function application in a program, a check is made that the type of the actual arguments is compatible with the type of the function itself. For example, attempting to apply the function *sum* to a list of characters would be reported as an error, because characters are not a type of numbers.

Now let us consider a more interesting function concerning lists, which illustrates a number of other aspects of Haskell. Suppose that we define a function called *qsort* by the following two equations:

![image](images/image20_00.jpg)

In this definition, ++ is an operator that appends two lists; for example, [1, 2, 3] ++ [4, 5] = [1, 2, 3, 4, 5]. In turn, **where** is a keyword that introduces local definitions, in this case a list *smaller* that consists of all elements *a* from the list *xs* that are less than or equal to *x*, together with a list *larger* that consists of all elements *b* from *xs* that are greater than *x*. For example, if *x* = 3 and *xs* = [5, 1, 4, 2], then *smaller* = [1, 2] and *larger* = [5, 4].

What does *qsort* actually do? First of all, we show that it has no effect on lists with a single element, in the sense that *qsort* [*x*] = [*x*] for any *x* :

![image](images/image20_01.jpg)

In turn, we now work through the application of *qsort* to an example list, using the above property to simplify the calculation:

![image](images/image20_02.jpg)

In summary, *qsort* has sorted the example list into numerical order. More generally, this function produces a sorted version of any list of numbers. The first equation for *qsort* states that the empty list is already sorted, while the second states that any non-empty list can be sorted by inserting the first number between the two lists that result from sorting the remaining numbers that are *smaller* and *larger* than this number. This method of sorting is called *quicksort*, and is one of the best such methods known.

The above implementation of quicksort is an excellent example of the power of Haskell, being both clear and concise. Moreover, the function *qsort* is also more general than might be expected, being applicable not just with numbers, but with any type of ordered values. More precisely, the type

![image](images/image23_00.jpg)

states that, for any type *a* of ordered values, *qsort* is a function that maps between lists of such values. Haskell supports many different types of ordered values, including numbers, single characters such as ’a’, and strings of characters such as "abcde". Hence, for example, the function *qsort* could also be used to sort a list of characters, or a list of strings.

![](images/line.jpg)

1.6 Chapter remarks

The Haskell Report is freely available on the web from the Haskell home page, *[www.haskell.org](http://www.haskell.org)*, and has also been published as a book (25). A more detailed historical account of the development of functional programming languages is given in Hudak’s survey article (11).

![](images/line.jpg)

1.7 Exercises

**1.**  Give another possible calculation for the result of *double* (*double* 2).

**2.**  Show that *sum* [*x*] = *x* for any number *x*.

**3.**  Define a function *product* that produces the product of a list of numbers, and show using your definition that *product* [2, 3, 4] = 24.

**4.**  How should the definition of the function *qsort* be modified so that it produces a *reverse* sorted version of a list?

**5.**  What would be the effect of replacing ≤ by *<* in the definition of *qsort*? Hint: consider the example *qsort* [2, 2, 3, 1, 1].

chapter 2

**First steps**

In this chapter we take our first proper steps with Haskell. We start by introducing the Hugs system and the standard prelude, then explain the notation for function application, develop our first Haskell script, and conclude by discussing a number of syntactic conventions concerning scripts.

![](images/line.jpg)

2.1 The Hugs system

As we saw in the previous chapter, small Haskell programs can be executed by hand. In practice, however, we usually require a system that can execute programs automatically. In this book we use an interactive system called *Hugs*, which is the most widely used implementation of Haskell.

The interactive nature of Hugs makes it well suited for teaching and prototyping, and its performance is sufficient for most applications. However, if greater performance or a stand-alone executable version of a program is required, a number of compilers for Haskell are also available, of which the most widely used is the Glasgow Haskell Compiler. This compiler also has an interactive version that operates in a similar manner to Hugs, and can readily be used in its place for the purposes of this book.

![](images/line.jpg)

2.2 The standard prelude

When the Hugs system is started it first loads a library file called *Prelude*.*hs*, and then displays a > prompt to indicate that the system is waiting for the user to enter an expression to be evaluated. For example, the library file defines many familiar functions that operate on integers, including the five main arithmetic operations of addition, subtraction, multiplication, division, and exponentiation, as illustrated below:

![image](images/image25_00.jpg)

Note that the integer division operator is written as ‘*div*‘, and rounds down to the nearest integer if the result is a proper fraction.

Following normal mathematical convention, exponentiation has higher priority than multiplication and division, which in turn have higher priority than addition and subtraction. For example, 2 * 3 ↑ 4 means 2 * (3 ↑ 4), while 2 + 3 * 4 means 2 + (3 * 4). Moreover, exponentiation associates (brackets) to the right, while the other four arithmetic operators associate to the left. For example, 2 ↑ 3 ↑ 4 means 2 ↑ (3 ↑ 4), while 2 − 3 + 4 means (2 − 3) + 4\. In practice, however, it is often clearer to use explicit parentheses in such arithmetic expressions, rather than relying on the above conventions.

In addition to functions on integers, the library file also provides a range of useful functions that operate on lists. In Haskell, the elements of a list are enclosed in square parentheses, and are separated by commas. Some of the most commonly used library functions on lists are illustrated below.

•  Select the first element of a non-empty list:

![image](images/image25_01.jpg)

•  Remove the first element from a non-empty list:

![image](images/image25_02.jpg)

•  Select the *n*th element of list (counting from zero):

![image](images/image25_03.jpg)

•  Select the first *n* elements of a list:

![image](images/image25_04.jpg)

•  Remove the first *n* elements from a list:

![image](images/image25_05.jpg)

• Calculate the length of a list:

![image](images/image26_00.jpg)

•  Calculate the sum of a list of numbers:

![image](images/image26_01.jpg)

•  Calculate the product of a list of numbers:

![image](images/image26_02.jpg)

•  Append two lists:

![image](images/image26_03.jpg)

•  Reverse a list:

![image](images/image26_04.jpg)

Some of the functions in the standard prelude may produce an error for certain values of their arguments. For example, attempting to divide by zero or select the first element of an empty list will produce an error:

![image](images/image26_05.jpg)

In practice, when an error occurs the Hugs system also produces a message that provides some information about the likely cause.

For reference, [appendix A](#21_appendix_title.html) presents some of the most commonly used definitions from the standard prelude, and [appendix B](#22_conclusion_title.html) shows how special Haskell symbols, such as ↑ and ++, are typed using a normal keyboard.

![](images/line.jpg)

2.3 Function application

In mathematics, the application of a function to its arguments is usually denoted by enclosing the arguments in parentheses, while the multiplication of two values is often denoted silently, by writing the two values next to one another. For example, in mathematics the expression

![image](images/image26_06.jpg)

means apply the function *f* to two arguments *a* and *b*, and add the result to the product of *c* and *d*. Reflecting its primary status in the language, function application in Haskell is denoted silently using spacing, while the multiplication of two values is denoted explicitly using the operator *. For example, the expression above would be written in Haskell as follows:

![image](images/image27_03.jpg)

Moreover, function application has higher priority than all other operators. For example, *f a* + *b* means (*f a*) + *b*. The following table gives a few further examples to illustrate the differences between the notation for function application in mathematics and in Haskell:

![image](images/table25_00.jpg)

Note that parentheses are still required in the Haskell expression *f* (*g x*) above, because *f g x* on its own would be interpreted as the application of the function *f* to two arguments *g* and *x*, whereas the intention is that *f* is applied to one argument, namely the result of applying the function *g* to an argument *x*. A similar remark holds for the expression *f x* (*g y*).

![](images/line.jpg)

2.4 Haskell scripts

As well as the functions provided in the standard prelude, it is also possible to define new functions. New functions cannot be defined at the > prompt within Hugs, but must be defined within a *script*, a text file comprising a sequence of definitions. By convention, Haskell scripts usually have a .*hs* suffix on their filename to differentiate them from other kinds of files.

My first script

When developing a Haskell script, it is useful to keep two windows open, one running an editor for the script, and the other running Hugs. As an example, suppose that we start a text editor and type in the following two function definitions, and save the script to a file called *test*.*hs*:

![image](images/table25_01.jpg)

In turn, suppose that we leave the editor open, and in another window start up the Hugs system and instruct it to load the new script:

![image](images/image27_04.jpg)

Now both *Prelude*.*hs* and *test*.*hs* are loaded, and functions from both scripts can be freely used. For example:

![image](images/image28_03.jpg)

Now suppose that we leave Hugs open, return to the editor, add the following two function definitions to those already typed in, and then resave the file:

![image](images/table26_00.jpg)

We could equally well have defined *average ns* = *div* (*sum ns*) (*length ns*), but writing *div* between its two arguments is more natural. In general, any function with two arguments can be written between its arguments by enclosing the name of the function in single back quotes ‘ ‘.

Hugs does not automatically reload scripts when they are modified, so a reload command must be executed before the new definitions can be used:

![image](images/image27_05.jpg)

For reference, the table below summarises the meaning of some of the most commonly used Hugs commands. Note that any command can be abbreviated by its first character. For example, :*load* can be abbreviated by :*l*. The command :*type* is explained in more detail in the next chapter.

![image](images/table26_01.jpg)

Naming requirements

When defining a new function, the names of the function and its arguments must begin with a lower-case letter, but can then be followed by zero or more letters (both lower- and upper-case), digits, underscores, and forward single quotes. For example, the following are all valid names:

![image](images/image29_00.jpg)

The following list of *keywords* have a special meaning in the language, and cannot be used as the names of functions or their arguments:

![image](images/image29_01.jpg)

By convention, list arguments in Haskell usually have the suffix *s* on their name to indicate that they may contain multiple values. For example, a list of numbers might be named *ns*, a list of arbitrary values might be named *xs*, and a list of list of characters might be named *css*.

The layout rule

Within a script, each definition must begin in precisely the same column. This *layout rule* makes it possible to determine the grouping of definitions from their indentation. For example, in the script

![image](images/image27_00.jpg)

it is clear from the indentation that *b* and *c* are local definitions for use within the body of *a*. If desired, such grouping can be made explicit by enclosing a sequence of definitions in curly parentheses and separating each definition by a semi-colon. For example, the above script could also be written as:

![image](images/image27_01.jpg)

In general, however, it is usually clearer to rely on the layout rule to determine the grouping of definitions, rather than use explicit syntax.

Comments

In addition to new definitions, scripts can also contain comments that will be ignored by Hugs. Haskell provides two kinds of comments, called *ordinary* and *nested*. Ordinary comments begin with the symbol -- and extend to the end of the current line, as in the following examples:

![image](images/image27_02.jpg)

Nested comments begin and end with the symbols {- and -}, may span multiple lines, and may be nested in the sense that comments can contain other comments. Nested comments are particularly useful for temporarily removing sections of definitions from a script, as in the following example:

![image](images/image28_00.jpg)

![](images/line.jpg)

2.5 Chapter remarks

The Hugs system is freely available on the web from the Haskell home page, *[www.haskell.org](http://www.haskell.org)*, which also contains a wealth of other useful resources.

![](images/line.jpg)

2.6 Exercises

**1.**  Parenthesise the following arithmetic expressions:

![image](images/image28_01.jpg)

**2.**  Work through the examples from this chapter using Hugs.

**3.**  The script below contains three syntactic errors. Correct these errors and then check that your script works properly using Hugs.

![image](images/image28_02.jpg)

**4.**  Show how the library function *last* that selects the last element of a non-empty list could be defined in terms of the library functions introduced in this chapter. Can you think of another possible definition?

**5.**  Show how the library function *init* that removes the last element from a non-empty list could similarly be defined in two different ways.

chapter 3

**Types and classes**

In this chapter we introduce types and classes, two of the most fundamental concepts in Haskell. We start by explaining what types are and how they are used in Haskell, then present a number of basic types and ways to build larger types by combining smaller types, discuss function types in more detail, and conclude with the concepts of polymorphic types and type classes.

![](images/line.jpg)

3.1 Basic concepts

A *type* is a collection of related values. For example, the type *Bool* contains the two logical values *False* and *True*, while the type *Bool* → *Bool* contains all functions that map arguments from *Bool* to results from *Bool*, such as the logical negation function ¬. We use the notation *υ* :: *T* to mean that *υ* is a value in the type *T*, and say that *υ* “has type” *T*. For example:

![image](images/table29_00.jpg)

More generally, the symbol :: can also be used with expressions that have not yet been evaluated, in which case *e* :: *T* means that evaluation of the expression *e* will produce a value of type *T*. For example:

![image](images/table29_01.jpg)

In Haskell, every expression must have a type, which is calculated prior to evaluating the expression by a process called *type inference*. The key to this process is a typing rule for function application, which states that if *f* is a function that maps arguments of type *A* to results of type *B*, and *e* is an expression of type *A*, then the application *f e* has type *B*:

![image](images/image30_00.jpg)

For example, the typing ¬ *False* :: *Bool* can be inferred from this rule using the fact that ¬ :: *Bool* → *Bool* and *False* :: *Bool*. On the other hand, the expression ¬ 3 does not have a type under the above rule for function application, because this would require that 3 :: *Bool*, which is not valid because 3 is not a logical value. Expressions such as ¬ 3 that do not have a type are said to contain a type error, and are deemed to be invalid expressions.

Because type inference precedes evaluation, Haskell programs are *type safe*, in the sense that type errors can never occur during evaluation. In practice, type inference detects a very large class of program errors, and is one of the most useful features of Haskell. Note, however, that the use of type inference does not eliminate the possibility that other kinds of error may occur during evaluation. For example, the expression 1 ‘*div*‘ 0 is free from type errors, but produces an error when evaluated because division by zero is undefined.

The downside of type safety is that some expressions that evaluate successfully will be rejected on type grounds. For example, the conditional expression **if** *True* **then** 1 **else** *False* evaluates to the number 1, but contains a type error and is hence deemed invalid. In particular, the typing rule for a conditional expression requires that both possible results have the same type, whereas in this case the first such result, 1, is a number and the second, *False*, is a logical value. In practice, however, programmers quickly learn how to work within the limits of the type system and avoid such problems.

In Hugs, the type of any expression can be displayed by preceding the expression by the command :*type*. For example:

![image](images/image30_01.jpg)

![](images/line.jpg)

3.2 Basic types

Haskell provides a number of basic types that are built-in to the language, of which the most commonly used are described below.

*Bool* – **logical values**

This type contains the two logical values *False* and *True*.

*Char* – **single characters**

This type contains all single characters that are available from a normal keyboard, such as ’a’, ’A’, ’3’ and ’_’, as well as a number of control characters that have a special effect, such as ’\n’ (move to a new line) and ’\t’ (move to the next tab stop). As is standard in most programming languages, single characters must be enclosed in single forward quotes ’ ’.

*String* – **strings of characters**

This type contains all sequences of characters, such as "abc", "1+2=3", and the empty string "". Again, as is standard in most programming languages, strings of characters must be enclosed in double quotes " ".

*Int* – **fixed-precision integers**

This type contains integers such as −100, 0, and 999, with a fixed amount of computer memory being used for their storage. For example, the Hugs system has values of type *Int* in the range −2^(31) to 2^(31) − 1\. Going outside this range can give unexpected results. For example, evaluating 2 ↑ 31 :: *Int* using Hugs (the use of :: forces the result to an *Int* rather than some other numeric type) gives a negative number as the result, which is incorrect.

*Integer* – **arbitrary-precision integers**

This type contains all integers, with as much memory as necessary being used for their storage, thus avoiding the imposition of lower and upper limits on the range of numbers. For example, evaluating 2 ↑ 31 :: *Integer* using any Haskell system will produce the correct result.

Apart from the different memory requirements and precision for numbers of type *Int* and *Integer*, the choice between these two types is also one of performance. In particular, most computers have built-in hardware for processing fixed-precision integers, whereas arbitrary-precision integers must usually be processed using the slower medium of software, as sequences of digits.

*Float* – **single-precision floating-point numbers**

This type contains numbers with a decimal point, such as −12.34, 1.0, and 3.14159, with a fixed amount of memory being used for their storage. The term *floating-point* comes from the fact that the number of digits permitted after the decimal point depends upon the magnitude of the number. For example, evaluating *sqrt* 2 :: *Float* using Hugs gives the result 1.41421 (the library function *sqrt* calculates the square root of a number), which has five digits after the point, whereas *sqrt* 99999 :: *Float* gives 316.226, which only has three digits after the point. Programming with floating-point numbers is a specialist topic that requires a careful treatment of rounding errors, and we say little more about such numbers in this introductory text.

We conclude this section by noting a single number may have more than one numeric type. For example, 3 :: *Int*, 3 :: *Integer*, and 3 :: *Float* are all valid typings for the number 3\. This raises the interesting question of what type such numbers should be assigned during type inference, which will be answered later in this chapter when we consider type classes.

![](images/line.jpg)

3.3 List types

A *list* is a sequence of *elements* of the same type, with the elements being enclosed in square parentheses and separated by commas. We write [*T*] for the type of all lists whose elements have type *T*. For example:

![image](images/image32_00.jpg)

The number of elements in a list is called its *length*. The list [ ] of length zero is called the empty list, while lists of length one, such as such as [*False*] and [’a’], are called singleton lists. Note that [[ ]] and [ ] are different lists, the former being a singleton list comprising the empty list as its only element, and the latter being simply the empty list.

There are three further points to note about list types. First of all, the type of a list conveys no information about its length. For example, the lists [*False*, *True*] and [*False*, *True*, *False*] both have type [*Bool*], even though they have different lengths. Secondly, there are no restrictions on the type of the elements of a list. At present we are limited in the range of examples that we can give because the only non-basic type that we have introduced at this point is list types, but we can have lists of lists, such as:

![image](images/image34_02.jpg)

Finally, there is no restriction that a list must have a finite length. In particular, due to the use of lazy evaluation in Haskell, lists with an infinite length are both natural and practical, as we shall see in [chapter 12](#19_chapter_title_12.html).

![](images/line.jpg)

3.4 Tuple types

A *tuple* is a finite sequence of *components* of possibly different types, with the components being enclosed in round parentheses and separated by commas. We write (*T*[1]*, T*[2]*, . . . , T*[n]) for the type of all tuples whose *i*th components have type *T[i]* for any *i* in the range 1 to *n*. For example:

![image](images/image32_01.jpg)

The number of components in a tuple is called its *arity*. The tuple () of arity zero is called the empty tuple, tuples of arity two are called pairs, tuples of arity three are called triples, and so on. Tuples of arity one, such as (*False*), are not permitted because they would conflict with the use of parentheses to make the evaluation order explicit, such as in (1 + 2) * 3.

As with list types, there are three further points to note about tuple types. First of all, the type of a tuple conveys its arity. For example, the type (*Bool*, *Char*) contains all pairs comprising a first component of type *Bool* and a second component of type *Char*. Secondly, there are no restrictions on the types of the components of a tuple. For example, we can now have tuples of tuples, tuples of lists, and lists of tuples:

![image](images/image33_00.jpg)

Finally, note that tuples must have a finite arity, in order to ensure that tuple types can always be calculated prior to evaluation.

![](images/line.jpg)

3.5 Function types

A *function* is a mapping from arguments of one type to results of another type. We write *T1* → *T2* for the type of all functions that map arguments of type *T1* to results of type *T2*. For example:

![image](images/image33_01.jpg)

(The library function *isDigit* decides if a character is a numeric digit.) Because there are no restrictions on the types of the arguments and results of a function, the simple notion of a function with a single argument and result is already sufficient to handle multiple arguments and results, by packaging multiple values using lists or tuples. For example, we can define a function *add* that calculates the sum of a pair of integers, and a function *zeroto* that returns the list of integers from zero to a given limit, as follows:

![image](images/image33_02.jpg)

In these examples we have followed the Haskell convention of preceding function definitions by their types, which serves as useful documentation. Any such types provided manually by the user are checked for consistency with the types calculated automatically using type inference.

Note that there is no restriction that functions must be *total* on their argument type, in the sense that there may be some arguments for which the result is not defined. For example, the result of the library function *head* that selects the first element of a list is undefined if the list is empty.

![](images/line.jpg)

3.6 Curried functions

Functions with multiple arguments can also be handled in another, perhaps less obvious way, by exploiting the fact that functions are free to return functions as results. For example, consider the following definition:

![image](images/image33_03.jpg)

The type states that *add*′ is a function that takes an argument of type *Int*, and returns a result that is a function of type *Int* → *Int*. The definition itself states that *add*′ takes an integer *x* followed by an integer *y*, and returns the result *x* + *y*. More precisely, *add*′ takes an integer *x* and returns a function, which in turn takes an integer *y* and returns the result *x* + *y*.

Note that the function *add*′ produces the same final result as the function *add* from the previous section, but whereas *add* takes its two arguments at the same time packaged as a pair, *add*′ takes its two arguments one at a time, as reflected in the different types of the two functions:

![image](images/image34_00.jpg)

Functions with more than two arguments can also be handled using the same technique, by returning functions that return functions, and so on. For example, a function *mult* that takes three integers, one at a time, and returns their product, can be defined as follows:

![image](images/image34_01.jpg)

This definition states that *mult* takes an integer *x* and returns a function, which in turn takes an integer *y* and returns another function, which finally takes an integer *z* and returns the result *x* * *y* * *z*.

Functions such as *add*′ and *mult* that take their arguments one at a time are called *curried*. As well as being interesting in their own right, curried functions are also more flexible than functions on tuples, because useful functions can often be made by *partially applying* a curried function with less than its full complement of arguments. For example, a function that increments an integer is given by the partial application *add*′ 1 :: *Int* → *Int* of the curried function *add*′ with only one of its two arguments.

To avoid excess parentheses when working with curried functions, two simple conventions are adopted. First of all, the function arrow → in types is assumed to associate to the right. For example,

![image](images/image36_02.jpg)

means

![image](images/image36_03.jpg)

Consequently, function application, which is denoted silently using spacing, is assumed to associate to the left. For example,

![image](images/image36_04.jpg)

means

![image](images/image36_05.jpg)

Unless tupling is explicitly required, all functions in Haskell with multiple arguments are normally defined as curried functions, and the two conventions above are used to reduce the number of parentheses that are required.

![](images/line.jpg)

3.7 Polymorphic types

The library function *length* calculates the length of any list, irrespective of the type of the elements of the list. For example, it can be used to calculate the length of a list of integers, a list of strings, or even a list of functions:

![image](images/image37_01.jpg)

The idea that *length* can be applied to lists whose elements have any type is made precise in its type by the inclusion of a *type variable*. Type variables must begin with a lower-case letter, and are usually simply named *a*, *b*, *c*, and so on. For example, the type of *length* is as follows:

![image](images/image37_02.jpg)

That is, for any type *a*, the function *length* has type [*a*] → *Int*. A type that contains one or more type variables is called *polymorphic* (“of many forms”), as is an expression with such a type. Hence, [*a*] → *Int* is a polymorphic type and *length* is a polymorphic function. More generally, many of the functions provided in the standard prelude are polymorphic. For example:

![image](images/image35_00.jpg)

![](images/line.jpg)

3.8 Overloaded types

The arithmetic operator + calculates the sum of any two numbers of the same numeric type. For example, it can be used to calculate the sum of two integers, or the sum of two floating-point numbers:

![image](images/image37_03.jpg)

The idea that + can be applied to numbers of any numeric type is made precise in its type by the inclusion of a *class constraint*. Class constraints are written in the form *C a*, where *C* is the name of a class and *a* is a type variable. For example, the type of + is as follows:

![image](images/image38_00.jpg)

That is, for any type *a* that is a *instance* of the class *Num* of numeric types, the function (+) has type *a* → *a* → *a*. (Parenthesising an operator converts it into a curried function, and is explained in more detail in the next chapter.) A type that contains one or more class constraints is called *overloaded*, as is an expression with such a type. Hence, *Num a* ⇒ *a* → *a* → *a* is an overloaded type and (+) is an overloaded function. More generally, most of the numeric functions provided in the standard prelude are overloaded. For example:

![image](images/image36_00.jpg)

Moreover, numbers themselves are also overloaded. For example, 3 :: *Num a* ⇒ *a* means that for any numeric type *a*, the number 3 has type *a*.

![](images/line.jpg)

3.9 Basic classes

Recall that a type is a collection of related values. Building upon this notion, a *class* is a collection of types that support certain overloaded operations called *methods*. Haskell provides a number of basic classes that are built-in to the language, of which the most commonly used are described below.

*Eq* – equality types

This class contains types whose values can be compared for equality and inequality using the following two methods:

![image](images/image36_01.jpg)

All the basic types *Bool*, *Char*, *String*, *Int*, *Integer*, and *Float* are instances of the *Eq* class, as are list and tuple types, provided that their element and component types are instances of the class. For example:

![image](images/image38_01.jpg)

Note that function types are not in general instances of the *Eq* class, because it is not feasible in general to compare two functions for equality.

*Ord* – ordered types

This class contains types that are instances of the equality class *Eq*, but in addition whose values are totally (linearly) ordered, and as such can be compared and processed using the following six methods:

![image](images/image37_00.jpg)

All the basic types *Bool*, *Char*, *String*, *Int*, *Integer*, and *Float* are instances of the *Ord* class, as are list types and tuple types, provided that their element and component types are instances of the class. For example:

![image](images/image39_02.jpg)

Note that strings, lists and tuples are ordered *lexicographically*; that is, in the same way as words in a dictionary. For example, two pairs of the same type are in order if their first components are in order, in which case their second components are not considered, or if their first components are equal, in which case their second components must be in order.

*Show* – showable types

This class contains types whose values can be converted into strings of characters using the following method:

![image](images/image40_00.jpg)

All the basic types *Bool*, *Char*, *String*, *Int*, *Integer*, and *Float* are instances of the *Show* class, as are list types and tuple types, provided that their element and component types are instances of the class. For example:

![image](images/image40_01.jpg)

*Read* – readable types

This class is dual to *Show*, and contains types whose values can be converted from strings of characters using the following method:

![image](images/image40_02.jpg)

All the basic types *Bool*, *Char*, *String*, *Int*, *Integer*, and *Float* are instances of the *Read* class, as are list types and tuple types, provided that their element and component types are instances of the class. For example:

![image](images/image40_03.jpg)

The use of :: in these examples resolves the type of the result. In practice, however, the necessary type information can usually be inferred automatically from the context. For example, the expression ¬ (*read* "False") requires no explicit type information, because the application of the logical negation function ¬ implies that *read* "False" must have type *Bool*.

Note that the result of *read* is undefined if its argument is not syntactically valid. For example, the expression ¬ (*read* "hello") produces an error when evaluated, because "hello" cannot be read as a logical value.

*Num* – numeric types

This class contains types that are instances of the equality class *Eq* and showable class *Show*, but in addition whose values are numeric, and as such can be processed using the following six methods:

![image](images/image39_00.jpg)

(The method *negate* returns the negation of a number, *abs* returns the absolute value, while *signum* returns the sign.) The basic types *Int*, *Integer*, and *Float* are instances of the *Num* class. For example:

![image](images/image41_01.jpg)

Note that the *Num* class does not provide a division method, but as we shall now see, division is handled separately using two special classes, one for integral numbers and one for fractional numbers.

*Integral* – integral types

This class contains types that are instances of the numeric class *Num*, but in addition whose values are integers, and as such support the methods of integer division and integer remainder:

![image](images/image39_01.jpg)

In practice, these two methods are often written between their two arguments by enclosing their names in single back quotes. The basic types *Int* and *Integer* are instances of the *Integral* class. For example:

![image](images/image42_04.jpg)

For efficiency reasons, a number of prelude functions that involve both lists and integers (such as *length*, *take*, and *drop*) are restricted to the type *Int* of finite-precision integers, rather than being applicable to any instance of the *Integral* class. If required, however, such generic versions of these functions are provided as part of an additional library file called *List*.*hs*.

*Fractional* – fractional types

This class contains types that are instances of the numeric class *Num*, but in addition whose values are non-integral, and as such support the methods of fractional division and fractional reciprocation:

![image](images/image42_05.jpg)

The basic type *Float* is an instance of the *Fractional* class. For example:

![image](images/image42_06.jpg)

![](images/line.jpg)

3.10 Chapter remarks

The term *Bool* for the type of logical values celebrates the pioneering work of George Boole on symbolic logic, while the term *curried* for functions that take their arguments one at a time celebrates the work of Haskell Curry (after whom the language Haskell itself is named) on such functions. A more detailed account of the type system is given in Haskell Report (25), while formal descriptions for specialists can be found in (20; 6).

![](images/line.jpg)

3.11 Exercises

**1.**  What are the types of the following values?

![image](images/image43_03.jpg)

**2.**  What are the types of the following functions?

     ![image](images/image41_00.jpg)

Hint: take care to include the necessary class constraints if the functions are defined using overloaded operators.

**3.**  Check your answers to the preceding two questions using Hugs.

**4.**  Why is it not feasible in general for function types to be instances of the *Eq* class? When is it feasible? Hint: two functions of the same type are equal if they always return equal results for equal arguments.

chapter 4

**Defining functions**

In this chapter we introduce a range of mechanisms for defining functions in Haskell. We start with conditional expressions and guarded equations, then introduce the simple but powerful idea of pattern matching, and conclude with the concepts of lambda expressions and sections.

![](images/line.jpg)

4.1 New from old

Perhaps the most straightforward way to define new functions is simply by combining one or more existing functions. For example, a number of library functions that are defined in this way are shown below.

•  Decide if a character is a digit:

![image](images/image42_00.jpg)

•  Decide if an integer is even:

![image](images/image42_01.jpg)

•  Split a list at the *n*th element:

![image](images/image42_02.jpg)

•  Reciprocation:

![image](images/image42_03.jpg)

Note the use of the class constraints in the types for *even* and *recip* above, which make precise the idea that these functions can be applied to numbers of any integral and fractional types, respectively.

![](images/line.jpg)

4.2 Conditional expressions

Haskell provides a range of different ways to define functions that choose between a number of possible results. The simplest are *conditional expressions*, which use a logical expression called a *condition* to choose between two results of the same type. If the condition is *True*, then the first result is chosen, and if it is *False*, then the second result is chosen. For example, the library function *abs* that returns the absolute value of an integer can be defined as follows:

![image](images/image43_00.jpg)

Conditional expressions may be nested, in the sense that they can contain other conditional expressions. For example, the library function *signum* that returns the sign of an integer can be defined as follows:

![image](images/image43_01.jpg)

Note that unlike in some programming languages, conditional expressions in Haskell must always have an **else** branch, which avoids the well-known “dangling else” problem. For example, if **else** branches were optional, then the expression **if** *True* **then if** *False* **then** 1 **else** 2 could either return the result 2 or produce an error, depending upon whether the single **else** branch was assumed to be part of the inner or outer conditional expression.

![](images/line.jpg)

4.3 Guarded equations

As an alternative to using conditional expressions, functions can also be defined using *guarded equations*, in which a sequence of logical expressions called *guards* is used to choose between a sequence of results of the same type. If the first guard is *True*, then the first result is chosen; otherwise, if the second is *True*, then the second result is chosen, and so on. For example, the library function *abs* can also be defined as follows:

![image](images/image43_02.jpg)

The symbol | is read as “such that”, and the guard *otherwise* is defined in the standard prelude simply by *otherwise* = *True*. Ending a sequence of guards with *otherwise* is not necessary, but provides a convenient way of handling “all other cases”, as well as clearly avoiding the possibility that none of the guards in the sequence is *True*, which would result in an error.

The main benefit of guarded equations over conditional expressions is that definitions with multiple guards are easier to read. For example, the library function *signum* is easier to understand when defined as follows:

![image](images/image44_00.jpg)

![](images/line.jpg)

4.4 Pattern matching

Many functions have a particularly simple and intuitive definition using *pattern matching*, in which a sequence of syntactic expressions called *patterns* is used to choose between a sequence of results of the same type. If the first pattern is *matched*, then the first result is chosen; otherwise, if the second is matched, then the second result is chosen, and so on. For example, the library function ¬ that returns the negation of a logical value is defined as follows:

![image](images/image44_01.jpg)

Functions with more than one argument can also be defined using pattern matching, in which case the patterns for each argument are matched in order within each equation. For example, the library operator ∧ that returns the conjunction of two logical values can be defined as follows:

![image](images/image44_02.jpg)

However, this definition can be simplified by combining the last three equations into a single equation that returns *False* independent of the values of the two arguments, using the *wildcard* pattern _ that matches any value:

![image](images/image44_03.jpg)

This version also has the benefit that, under lazy evaluation as discussed in [chapter 12](#19_chapter_title_12.html), if the first argument is *False*, then the result *False* is returned without the need to evaluate the second argument. In practice, the prelude defines ∧ using equations that have this same property, but make the choice about which equation applies using the value of the first argument only:

![image](images/image44_04.jpg)

That is, if the first argument is *True*, then the result is the value of the second argument, and, if the first argument is *False*, then the result is *False*.

Note that for technical reasons the same name may not be used for more than one argument in a single equation. For example, the following definition for the operator ∧ is based upon the observation that, if the two arguments are equal, then the result is the same value, otherwise the result is *False*, but is invalid because of the above naming requirement:

![image](images/image45_00.jpg)

If desired, however, a valid version of this definition can be obtained by using a guard to decide if the two arguments are equal:

![image](images/image45_01.jpg)

So far, we have only considered basic patterns that are either values, variables, or the wildcard pattern. In the remainder of this section we introduce three useful ways to build larger patterns by combining smaller patterns.

Tuple patterns

A tuple of patterns is itself a pattern, which matches any tuple of the same arity whose components all match the corresponding patterns in order. For example, the library functions *fst* and *snd* that select the first and second components of a pair are defined as follows:

![image](images/image45_02.jpg)

List patterns

Similarly, a list of patterns is itself a pattern, which matches any list of the same length whose elements all match the corresponding patterns in order. For example, a function *test* that decides if a list contains precisely three characters beginning with ’a’ can be defined as follows:

![image](images/image45_03.jpg)

Up to this point we have viewed lists as a primitive notion in Haskell. In fact they are not primitive as such, but are actually constructed one element at a time starting from the empty list [ ] using an operator : called *cons* that *cons*tructs a new list by prepending a new element to the start of an existing list. For example, the list [1, 2, 3] can be decomposed as follows:

![image](images/image45_04.jpg)

That is, [1, 2, 3] is just an abbreviation for 1 : (2 : (3 : [ ])). To avoid excess parentheses when working with such lists, the cons operator is assumed to associate to the right. For example, 1 : 2 : 3 : [ ] means 1 : (2 : (3 : [ ])).

As well as being used to construct lists, the cons operator can also be used to construct patterns, which match any non-empty list whose first and remaining elements match the corresponding patterns in order. For example, we can now define a more general version of the function *test* that decides if a list containing any number of characters begins with ’a’:

![image](images/image46_00.jpg)

Similarly, the library functions *null*, *head* and *tail* that decide if a list is empty, select the first element of a non-empty list, and remove the first element of a non-empty list are defined as follows:

![image](images/image46_01.jpg)

Note that cons patterns must be parenthesised, because function application has higher priority than all other operators. For example, the definition *tail* _ : *xs* = *xs* without parentheses means (*tail* _) : *xs* = *xs*, which is both the incorrect meaning and an invalid definition.

Integer patterns

As a special case that is sometimes useful, Haskell also allows integer patterns of the form *n* + *k*, where *n* is an integer variable and *k* > 0 is an integer constant. For example, a function *pred* that maps zero to itself and any strictly positive integer to its predecessor can be defined as follows:

![image](images/image46_02.jpg)

There are two points to note about *n* + *k* patterns. First of all, they only match integers ≥ *k*. For example, evaluating *pred* (−1) produces an error, because neither of the two patterns in the definition for *pred* matches negative integers. Secondly, for the same reason as cons patterns, integer patterns must be parenthesised. For example, the definition *pred n* + 1 = *n* without parentheses means (*pred n*) + 1 = *n*, which is an invalid definition.

![](images/line.jpg)

4.5 Lambda expressions

As an alternative to defining functions using equations, functions can also be constructed using *lambda expressions*, which comprise a pattern for each of the arguments, a body that specifies how the result can be calculated in terms of the arguments, but do not give a name for the function itself. In other words, lambda expressions are nameless functions.

For example, a nameless function that takes a single number *x* as its argument, and produces the result *x* + *x*, can be constructed as follows:

![image](images/image49_01.jpg)

The symbol *λ* is the lower-case Greek letter “lambda”. Despite the fact that they have no names, functions constructed using lambda expressions can be used in the same way as any other functions. For example:

![image](images/image49_02.jpg)

As well as being interesting in their own right, lambda expressions have a number of practical applications. First of all, they can be used to formalise the meaning of curried function definitions. For example, the definition

![image](images/image49_03.jpg)

can be understood as meaning

![image](images/image49_04.jpg)

which makes precise that *add* is a function that takes a number *x* and returns a function, which in turn takes a number *y* and returns the result *x* + *y*.

Secondly, lambda expressions are also useful when defining functions that return functions as results by their very nature, rather than as a consequence of currying. For example, the library function *const* that returns a constant function that always produces a given value can be defined as follows:

![image](images/image47_00.jpg)

However, it is more appealing to define *const* in a way that makes explicit that it returns a function as its result, by including parentheses in the type and using a lambda expression in the definition itself:

![image](images/image47_01.jpg)

Finally, lambda expressions can be used to avoid having to name a function that is only referenced once. For example, a function *odds* that returns the first *n* odd integers can be defined as follows:

![image](images/image47_02.jpg)

(The library function *map* applies a function to all elements of a list.) However, because the locally defined function *f* is only referenced once, the definition for *odds* can be simplified by using a lambda expression:

![image](images/image49_05.jpg)

![](images/line.jpg)

4.6 Sections

Functions such as + that are written between their two arguments are called *operators*. As we have already seen, any function with two arguments can be converted into an operator by enclosing the name of the function in single back quotes, as in 7 ‘*div*‘ 2\. However, the converse is also possible. In particular, any operator can be converted into a curried function that is written before its arguments by enclosing the name of the operator in parentheses, as in (+) 1 2\. Moreover, this convention also allows one of the arguments to be included in the parentheses if desired, as in (1+) 2 and (+2) 1.

In general, if ⊕ is an operator, then expressions of the form (⊕), (*x* ⊕), and (⊕ *y*) for arguments *x* and *y* are called *sections*, whose meaning as functions can be formalised using lambda expressions as follows:

![image](images/image48_00.jpg)

Sections have three main applications. First of all, they can be used to construct a number of simple but useful functions in a particularly compact way, as shown in the following examples:

![image](images/image48_01.jpg)

Secondly, sections are necessary when stating the type of operators, because an operator itself is not a valid expression in Haskell. For example, the type of the logical conjunction operator ∧ is stated as follows:

![image](images/image50_00.jpg)

Finally, sections are also necessary when using operators as arguments to other functions. For example, the library function *and* that decides if all logical values in a list are *True* is defined by using the operator ∧ as an argument to the library function *foldr*, which is itself discussed in [chapter 7](#14_chapter_title_7.html):

![image](images/image48_02.jpg)

![](images/line.jpg)

4.7 Chapter remarks

A formal meaning for pattern matching by translation using more primitive features of the language is given in the Haskell Report (25). The Greek letter *λ* used when defining nameless functions comes from the *lambda calculus*, the mathematical theory of functions upon which Haskell is founded.

![](images/line.jpg)

4.8 Exercises

**1.**  Using library functions, define a function *halve* :: [*a*] → ([*a*], [*a*]) that splits an even-lengthed list into two halves. For example:

![image](images/image51_04.jpg)

**2.**  Consider a function *safetail* :: [*a*] → [*a*] that behaves as the library function *tail*, except that *safetail* maps the empty list to itself, whereas *tail* produces an error in this case. Define *safetail* using:

**(a)**  a conditional expression;

**(b)**  guarded equations;

**(c)**  pattern matching.

Hint: make use of the library function *null*.

**3.**  In a similar way to ∧, show how the logical disjunction operator ∨ can be defined in four different ways using pattern matching.

**4.**  Redefine the following version of the conjunction operator using conditional expressions rather than pattern matching:

![image](images/image49_00a.jpg)

**5.**  Do the same for the following version, and note the difference in the number of conditional expressions required:

![image](images/image49_00.jpg)

**6.**  Show how the curried function definition *mult x y z* = *x* * *y* * *z* can be understood in terms of lambda expressions.

chapter 5

**List comprehensions**

In this chapter we introduce list comprehensions, which allow many functions on lists to be defined in simple manner. We start by explaining generators and guards, then introduce the function *zip* and the idea of string comprehensions, and conclude by developing a program to crack the Caesar cipher.

![](images/line.jpg)

5.1 Generators

In mathematics, the *comprehension* notation can be used to construct new sets from existing sets. For example, the comprehension {*x*² | *x* ∈ {1 *. .* 5}} produces the set {1, 4, 9, 16, 25} of all numbers *x*² such that *x* is an element of the set {1 *. .* 5}. In Haskell, a similar comprehension notation can be used to construct new lists from existing lists. For example:

![image](images/image52_03.jpg)

The symbols | and ← are read as “such that” and “is drawn from” respectively, and the expression *x* ← [1 *. .* 5] is called a *generator*. A list comprehension can have more than one generator, with successive generators being separated by commas. For example, the list of all possible pairings of an element from the list [1, 2, 3] with an element from [4, 5] can be produced as follows:

![image](images/image52_04.jpg)

Changing the order of the two generators in this example produces the same set of pairs, but arranged in a different order:

![image](images/image52_05.jpg)

In particular, whereas in this case the *x* components of the pairs change more frequently than the *y* components (1,2,3,1,2,3 versus 4,4,4,5,5,5), in the previous case the *y* components change more frequently than the *x* components (4,5,4,5,4,5 versus 1,1,2,2,3,3). These behaviours can be understood by thinking of later generators as being more deeply nested, and hence changing the values of their variables more frequently than earlier generators.

Later generators can also depend upon the values of variables from earlier generators. For example, the list of all possible ordered pairings of elements from the list [1 *. .* 3] can be produced as follows:

![image](images/image53_03.jpg)

As another example of this idea, the library function *concat* that concatenates a list of lists can be defined by using one generator to select each list in turn, and another to select each element from each list:

![image](images/image51_00.jpg)

The wildcard pattern _ is sometimes useful in generators to discard certain elements from a list. For example, a function that selects all the first components from a list of pairs can be defined as follows:

![image](images/image51_01.jpg)

Similarly, the library function that calculates the *length* of a list can be defined by replacing each element by one and summing the resulting list:

![image](images/image51_02.jpg)

In this case, the generator _ ← *xs* simply serves as a counter to govern the production of the appropriate number of ones.

![](images/line.jpg)

5.2 Guards

List comprehensions can also use logical expressions called *guards* to filter the values produced by earlier generators. If a guard is *True*, then the current values are retained, and, if it is *False*, then they are discarded. For example, the comprehension [*x* | *x* ← [1 *. .* 10], *even x*] produces the list [2, 4, 6, 8, 10] of all even numbers from the list [1 *. .* 10]. Similarly, a function that maps a positive integer to its list of positive *factors* can be defined as follows:

![image](images/image51_03.jpg)

For example:

![image](images/image53_04.jpg)

Recall that an integer greater than one is *prime* if its only positive factors are one and the number itself. Hence, by using *factors*, a simple function that decides if an integer is prime can be defined as follows:

![image](images/image52_00.jpg)

For example:

![image](images/image54_01.jpg)

Note that deciding that a number such as 15 is not prime does not require the function *prime* to produce all of its factors, because under lazy evaluation the result *False* is returned as soon as any factor other than one or the number itself is produced, which for this example is given by the factor 3.

Returning to list comprehensions, using *prime* we can now define a function that produces the list of all prime numbers up to a given limit:

![image](images/image52_01.jpg)

For example:

![image](images/image54_02.jpg)

In [chapter 12](#19_chapter_title_12.html) we will present a more efficient program to generate prime numbers using the famous “sieve of Eratosthenes”, which has a particularly clear and concise implementation in Haskell.

As a final example concerning guards, suppose that we represent a lookup table by a list of pairs comprising keys and values. Then for any type of keys that is an equality type, a function *find* that returns the list of all values that are associated with a given key in a table can be defined as follows:

![image](images/image52_02.jpg)

For example:

![image](images/image54_03.jpg)

![](images/line.jpg)

5.3 The *zip* function

The library function *zip* produces a new list by pairing successive elements from two existing lists until either or both are exhausted. For example:

![image](images/image54_04.jpg)

The function *zip* is often useful when programming with list comprehensions. For example, suppose that we define a function *pairs* that returns the list of all pairs of adjacent elements from a list as follows:

![image](images/image53_00.jpg)

For example:

![image](images/image55_02.jpg)

Then using *pairs* we can now define a function that decides if a list of elements of any ordered type is *sorted* by simply checking that all pairs of adjacent elements from the list are in the correct order:

![image](images/image53_01.jpg)

For example:

![image](images/image55_03.jpg)

Similarly to the function *prime*, deciding that a list such as [1, 3, 2, 4] is not sorted may not require the function *sorted* to produce all pairs of adjacent elements, because the result *False* is returned as soon as any non-ordered pair is produced, which in this example is given by the pair (3, 2).

Using *zip* we can also define a function that returns the list of all *positions* at which a value occurs in a list, by pairing each element with its position, and selecting those positions at which the desired value occurs:

![image](images/image53_02.jpg)

For example:

![image](images/image55_04.jpg)

![](images/line.jpg)

5.4 String comprehensions

Up to this point we have viewed strings as a primitive notion in Haskell. In fact they are not primitive as such, but are actually constructed as lists of characters. For example, "abc" :: *String* is just an abbreviation for [’a’, ’b’, ’c’] :: [*Char*]. Because strings are just special kinds of lists, any polymorphic function on lists can also be used with strings. For example:

![image](images/image56_04.jpg)

For the same reason, list comprehensions can also be used to define functions on strings, such as functions that return the number of lower-case letters and particular characters that occur in a string, respectively:

![image](images/image54_00.jpg)

For example:

![image](images/image56_05.jpg)

![](images/line.jpg)

5.5 The Caesar cipher

We conclude this chapter with an extended example. Consider the problem of encoding a string in order to disguise its contents from unintended readers. A well-known encoding method is the *Caesar cipher*, named after its use by Julius Caesar. To encode a string, Caesar simply replaced each letter in the string by the letter three places further down in the alphabet, wrapping around at the end of the alphabet. For example, the string

![image](images/image56_06.jpg)

would be encoded as

![image](images/image56_07.jpg)

More generally, the shift factor of three used by Caesar can be replaced by any integer between one and twenty-five, thereby giving twenty-five different ways of encoding a string. For example, with a shift factor of ten, the original string above would be encoded as

![image](images/image57_04.jpg)

In the remainder of this section we show how Haskell can be used to implement the Caesar cipher, and how the cipher itself can easily be “cracked” by exploiting information about letter frequencies.

Encoding and decoding

For simplicity, we will only encode the lower-case letters within a string, leaving other characters such as upper-case letters and punctuation unchanged. We begin by defining a function *let2int* that converts a lower-case letter between ’a’ and ’z’ into the corresponding integer between 0 and 25, together with a function *int2let* that performs the opposite conversion:

![image](images/image55_00.jpg)

(The library functions *ord* :: *Char* → *Int* and *chr* :: *Int* → *Char* convert between characters and their Unicode representation as integers.) For example:

![image](images/image57_05.jpg)

Using these two functions, we can define a function *shift* that applies a shift factor to a lower-case letter by converting the letter into the corresponding integer, adding on the shift factor and taking the remainder when divided by twenty-six (thereby wrapping around at the end of the alphabet), and converting the resulting integer back into a lower-case letter:

![image](images/image55_01.jpg)

Note that this function accepts both positive and negative shift factors, and that only lower-case letters are changed. For example:

![image](images/image57_06.jpg)

Using *shift* within a string comprehension, it is now easy to define a function that encodes a string using a given shift factor:

![image](images/image56_00.jpg)

A separate function to decode a string is not required, because this can be achieved by simply using a negative shift factor. For example:

![image](images/image58_00.jpg)

Frequency tables

The key to cracking the Caesar cipher is the observation that some letters are used more frequently than others in English text. By analysing a large volume of text, one can derive the following table of approximate percentage frequencies of the twenty-six letters of alphabet:

![image](images/image56_01.jpg)

For example, the letter ’e’ occurs most often, with a frequency of 12.7%, while ’q’ and ’z’ occur least often, with a frequency of just 0.1%. It is also useful to produce frequency tables for individual strings. To this end, we first define a function that calculates the percentage of one integer with respect to another, returning the result as a floating-point number:

![image](images/image56_02.jpg)

(The library function *fromIntegral* :: *Int* → *Float* converts an integer into the corresponding floating-point number.) Using *percent* within a string comprehension, together with the functions *lowers* and *count* from the previous section, we can define a function that returns a frequency table for any string:

![image](images/image56_03.jpg)

For example:

![image](images/image58_01.jpg)

That is, the letter ’a’ occurs with a frequency of 6.7%, the letter ’b’ with a frequency of 13.3%, and so on. The use of the local definition *n* = *lowers xs* within *freqs* ensures that the number of lower-case letters in the argument string is calculated once, rather than each of the twenty-six times that this number is used within the string comprehension.

Cracking the cipher

A standard method for comparing a list of observed frequencies *os* with a list of expected frequencies *es* is the *chi-square* statistic, defined by the following summation in which *n* denotes the length of the two lists, and *xs*[i] denotes the *i*th element of a list *xs* counting from zero:

![image](images/image57_00.jpg)

The details of the chi-square statistic need not concern us here, only the fact that the smaller the value it produces the better the match between the two frequency lists. Using the library function *zip* and a list comprehension, it is easy to translate the above formula into a function definition:

![image](images/image57_01.jpg)

In turn, we define a function that rotates the elements of a list *n* places to the left, wrapping around at the start of the list, and assuming that *n* is between zero and the length of the list:

![image](images/image57_02.jpg)

For example:

![image](images/image59_01.jpg)

Now suppose that we are given an encoded string, but not the shift factor that was used to encode it, and wish to determine this number in order that we can decode the string. This can usually be achieved by producing the frequency table of the encoded string, calculating the chi-square statistic for each possible rotation of this table with respect to the table of expected frequencies, and using the position of the minimum chi-square value as the shift factor. For example, if *table*′ = *freqs* "kdvnhoo lv ixq", then

![image](images/image59_02.jpg)

gives the result

![image](images/image59_03.jpg)

in which the minimum value, 202.6, appears at position three in this list. Hence, we conclude that three is the most likely shift factor that was used to encode the string. Using the function *positions* from earlier in this chapter, this procedure can be implemented as follows:

![image](images/image57_03.jpg)

For example:

![image](images/image60_03.jpg)

More generally, the *crack* function can decode most strings produced using the Caesar cipher. Note, however, that it may not be successful if the string is short or has an unusual distribution of letters. For example:

![image](images/image60_04.jpg)

![](images/line.jpg)

5.6 Chapter remarks

The term *comprehension* comes from the “axiom of comprehension” in set theory, which makes precise the idea of constructing a set by selecting all values satisfying a particular property. A formal meaning for list comprehensions by translation using more primitive features of the language is given in the Haskell Report (25). A popular account of the Caesar cipher, and many other famous cryptographic methods, is given in *The Code Book* (29).

![](images/line.jpg)

5.7 Exercises

**1.**  Using a list comprehension, give an expression that calculates the sum 1² + 2² + *. . .* 100² of the first one hundred integer squares.

**2.**  In a similar way to the function *length*, show how the library function *replicate* :: *Int* → *a* → [*a*] that produces a list of identical elements can be defined using a list comprehension. For example:

![image](images/image60_5.jpg)

**3.**  A triple (*x, y, z*) of positive integers is *pythagorean* if *x*² + *y*² = *z*². Using a list comprehension, define a function *pyths* :: *Int* → [(*Int*, *Int*, *Int*)] that returns the list of all pythagorean triples whose components are at most a given limit. For example:

![image](images/image60_06.jpg)

**4.**  A positive integer is *perfect* if it equals the sum of its factors, excluding the number itself. Using a list comprehension and the function *factors*, define a function *perfects* :: *Int* → [*Int*] that returns the list of all perfect numbers up to a given limit. For example:

![image](images/image61_03.jpg)

**5.**  Show how the single comprehension [(*x*, *y*) | *x* ← [1, 2, 3], *y* ← [4, 5, 6]] with two generators can be re-expressed using two comprehensions with single generators. Hint: make use of the library function *concat* and nest one comprehension within the other.

**6.**  Redefine the function *positions* using the function *find*.

**7.**  The *scalar product* of two lists of integers *xs* and *ys* of length *n* is given by the sum of the products of corresponding integers:

     ![image](images/image59_00.jpg)

In a similar manner to the function *chisqr*, show how a list comprehension can be used to define a function *scalarproduct* :: [*Int*] → [*Int*] → *Int* that returns the scalar product of two lists. For example:

![image](images/image61_04.jpg)

**8.**  Modify the Caesar cipher program to also handle upper-case letters.

chapter 6

**Recursive functions**

In this chapter we introduce recursion, the basic mechanism for looping in Haskell. We start with recursion on integers, then extend the idea to recursion on lists, consider multiple arguments, multiple recursion, and mutual recursion, and conclude with some advice on defining recursive functions.

![](images/line.jpg)

6.1 Basic concepts

As we have seen in previous chapters, many functions can naturally be defined in terms of other functions. For example, a function that returns the *factorial* of a non-negative integer can be defined by using library functions to calculate the product of the integers between one and the number itself:

![image](images/image60_00.jpg)

In Haskell, it is also permissible to define functions in terms of themselves, in which case the functions are called *recursive*. For example, the *factorial* function can be defined in this manner as follows:

![image](images/image60_01.jpg)

The first equation states that the factorial of zero is one, and is called a *base case*. The second equation states that the factorial of any strictly positive integer is the product of that number and the factorial of its predecessor, and is called a *recursive case*. For example, the following calculation shows how the factorial of three is computed using this definition:

![image](images/image60_02.jpg)

Note that even though the *factorial* function is defined in terms of itself, it does not loop forever. In particular, each application of *factorial* reduces the integer argument by one, until it eventually reaches zero at which point the recursion stops and the multiplications are performed. Returning one as the factorial of zero is appropriate because one is the identity for multiplication. That is, 1 * *x* = *x* and *x* * 1 = *x* for any integer *x*.

For the case of the *factorial* function, the original definition using library functions is simpler than the definition using recursion. However, as we shall see in the remainder of this book, many functions have a simple and natural definition using recursion. For example, many of the library functions in Haskell are defined in this way. Moreover, as we shall see in [chapter 13](#20_chapter_title_13.html), defining functions using recursion also allows properties of those functions to be proved using the powerful technique of induction.

As another example of recursion on integers, consider the multiplication operator * used above. For efficiency reasons, this operator is provided as a primitive in Haskell. However, for non-negative integers it can also be defined using recursion on either of its two arguments, such as the second:

![image](images/image61_01.jpg)

For example:

![image](images/image61_02.jpg)

That is, the recursive definition for the * operator formalises the idea that multiplication can be reduced to repeated addition.

![](images/line.jpg)

6.2 Recursion on lists

Recursion is not restricted to functions on integers, but can also be used to define functions on lists. For example, the library function *product* used in the preceding section can be defined as follows:

![image](images/image62_00.jpg)

The first equation states that the product of the empty list is one, which is appropriate because one is the identity for multiplication. The second equation states that the product of any non-empty list is given by multiplying the first number and the product of the remaining list of numbers. For example:

![image](images/image62_01.jpg)

Recall that lists in Haskell are actually constructed one element at a time using the cons operator. Hence, [2, 3, 4] is just an abbreviation for 2 : (3 : (4 : [ ])). As another simple example of recursion on lists, the library function *length* can be defined using the same pattern of recursion as *product*:

![image](images/image62_02.jpg)

That is, the length of the empty list is zero, and the length of any non-empty list is the successor of the length of its tail. Note the use of the wildcard pattern _ in the recursive case, which reflects the fact that the length of a list does not depend upon the value of its elements.

Now let us consider the library function that reverses a list. This function can be defined using recursion as follows:

![image](images/image62_03.jpg)

That is, the reverse of the empty list is simply the empty list, and the reverse of any non-empty list is given by appending the reverse of its tail to a singleton list comprising the head of the list. For example:

![image](images/image62_04.jpg)

In turn, the append operator ++ used in the above definition of *reverse* can itself be defined using recursion on its first argument:

![image](images/image63_01.jpg)

For example:

![image](images/image63_02.jpg)

That is, the recursive definition for ++ formalises the idea that two lists can be appended by copying elements from the first list until it is exhausted, at which point the second list is joined on at the end.

We conclude this section with two examples of recursion on sorted lists. First of all, a function that inserts a new element of any ordered type into a sorted list to give another sorted list can be defined as follows:

![image](images/image63_03.jpg)

That is, inserting a new element into the empty list gives a singleton list, while for a non-empty list the result depends upon the ordering of the new element *x* and the head of the list *y*. In particular, if *x* ≤ *y*, then the new element *x* is simply prepended to the start of the list, otherwise the head *y* becomes the first element of the resulting list, and we then proceed to insert the new element into the tail of the given list. For example:

![image](images/image63_04.jpg)

Using *insert* we can now define a function that implements *insertion sort*, in which the empty list is already sorted, and any non-empty list is sorted by inserting its head into the list that results from sorting its tail:

![image](images/image64_01.jpg)

For example:

![image](images/image64_02.jpg)

![](images/line.jpg)

6.3 Multiple arguments

Functions with multiple arguments can also be defined using recursion on more than one argument at the same time. For example, the library function *zip* that takes two lists and produces a list of pairs is defined as follows:

![image](images/image64_03.jpg)

For example:

![image](images/image64_04.jpg)

Note that two base cases are required in the definition of *zip*, because either of the two argument lists may be empty. As another example of recursion on multiple arguments, the library function *drop* that removes a given number of elements from the start of a list is defined as follows:

![image](images/image65_00.jpg)

Again, two base cases are required, one for removing zero elements, and one for attempting to remove one or more elements from the empty list.

![](images/line.jpg)

6.4 Multiple recursion

Functions can also be defined using *multiple recursion*, in which a function is applied more than once in its own definition. For example, recall the Fibonacci sequence 0, 1, 1, 2, 3, 5, 8, 13*, . . .*, in which the first two numbers are 0 and 1, and each subsequent number is given by adding the preceding two numbers in the sequence. In Haskell, a function that calculates the *n*th Fibonacci number for any integer *n* ≥ 0 can be defined using double recursion as follows:

![image](images/image65_01.jpg)

As another example, in [chapter 1](#08_chapter_title_1.html) we showed how to implement another well-known method of sorting a list, called quicksort:

![image](images/image65_02.jpg)

That is, the empty list is already sorted, and any non-empty list can be sorted by placing its head between the two lists that result from sorting those elements of its tail that are *smaller* and *larger* than the head.

![](images/line.jpg)

6.5 Mutual recursion

Functions can also be defined using *mutual recursion*, in which two or more functions are all defined in terms of each other. For example, consider the library functions *even* and *odd*. For efficiency, these functions are normally defined using the remainder after dividing by two. However, for non-negative integers they can also be defined using mutual recursion:

![image](images/image66_00.jpg)

That is, zero is even but not odd, and any strictly positive integer is even if its predecessor is odd, and odd if its predecessor is even. For example:

![image](images/image66_01.jpg)

Similarly, functions that select the elements from a list at all even and odd positions (counting from zero) can be defined as follows:

![image](images/image66_02.jpg)

For example:

![image](images/image66_03.jpg)

Recall that strings in Haskell are actually constructed as lists of characters. Hence, "abcde" is just an abbreviation for [’a’, ’b’, ’c’, ’d’, ’e’].

![](images/line.jpg)

6.6 Advice on recursion

Defining recursive functions is like riding a bicycle: it looks easy when someone else is doing it, may seem impossible when you first try to do it yourself, but becomes simple and natural with practice. In this section we offer some advice for defining functions in general, and recursive functions in particular, using a five-step process that we introduce by means of examples.

Example – *product*

As a simple first example, we show how the definition given earlier in this chapter for the library function that calculates the *product* of a list of numbers can be constructed in a stepwise manner.

**Step 1: define the type**

Thinking about types is very helpful when defining functions, so it is good practice to define the type of a function prior to starting to define the function itself. In this case, we begin with the type

![image](images/image69_05.jpg)

that states that *product* takes a list of integers and produces a single integer. As in this example, it is often useful to begin with a simple type, which can be refined or generalised later on as appropriate.

**Step 2: enumerate the cases**

For most types of argument, there are a number of standard cases to consider. For lists, the standard cases are the empty list and non-empty lists, so we can write down the following skeleton definition using pattern matching:

![image](images/image67_00.jpg)

For non-negative integers, the standard cases are 0 and *n* + 1, for logical values they are *False* and *True*, and so on. As with the type, we may need to refine the cases later on, but it is useful to begin with the standard cases.

**Step 3: define the simple cases**

By definition, the product of zero integers is one, because one is the identity for multiplication. Hence it is straightforward to define the empty list case:

![image](images/image67_01.jpg)

As in this example, the simple cases often become base cases.

**Step 4: define the other cases**

How can we calculate the product of a non-empty list of integers? For this step, it is useful to first consider the ingredients that can be used, such as the function itself (*product*), the arguments (*n* and *ns*), and library functions of relevant types (+, −, *, and so on.) In this case, we simply multiply the first integer and the product of the remaining list of integers:

![image](images/image68_00.jpg)

As in this example, the other cases often become recursive cases.

**Step 5: generalise and simplify**

Once a function has been defined using the above process, it often becomes clear that it can be generalised and simplified. For example, the function *product* does not depend on the precise kind of numbers to which it is applied, so its type can be generalised from integers to any numeric type:

![image](images/image70_03.jpg)

In terms of simplification, we will see in [chapter 7](#14_chapter_title_7.html) that the pattern of recursion used in *product* is encapsulated by a library function called *foldr*, using which *product* can be redefined by a single equation:

![image](images/image70_04.jpg)

In conclusion, our final definition for *product* is as follows:

![image](images/image68_01.jpg)

This is precisely the definition from the standard prelude in appendix A, except that for efficiency reasons the use of *foldr* is replaced by the related library function *foldl*, which is also discussed in [chapter 7](#14_chapter_title_7.html).

Example – *drop*

As a more substantial example, we now show how the definition given earlier for the library function *drop* that removes a given number of elements from the start of a list can be constructed using the five-step process.

**Step 1: define the type**

Let us begin with a type that states that *drop* takes an integer and a list of values of some type *a*, and produces another list of such values:

![image](images/image70_05.jpg)

Note that we have made four decisions in defining this type: using integers rather than a more general numeric type, for simplicity; using currying rather than taking the arguments as a pair, for flexibility (see [section 3.6](#10_chapter_title_3.html_pg-33-56)); supplying the integer argument before the list argument, for readability (*drop n xs* can be read as “drop *n* elements from *xs*”); and, finally, making the function polymorphic in the type of the list elements, for generality.

**Step 2: enumerate the cases**

As there are two standard cases for the integer argument (0 and *n* + 1) and two for the list argument ([ ] and *x* : *xs*), writing down a skeleton definition using pattern matching requires four cases in total:

![image](images/image69_00.jpg)

**Step 3: define the simple cases**

By definition, removing zero elements from the start of any list gives the same list, so it is straightforward to define the first two cases:

![image](images/image69_01.jpg)

Attempting to removing one or more elements from the empty list is invalid, so the third case could be omitted, which would result in an error being produced if this situation arises. In practice, however, we choose to avoid the production of an error by returning the empty list in this case:

![image](images/image69_02.jpg)

**Step 4: define the other cases**

How can we remove one or more elements from a non-empty list? By simply removing one less element from the tail of the list:

![image](images/image69_03.jpg)

**Step 5: generalise and simplify**

Because the function *drop* does not depend on the precise kind of integers to which it is applied, its type can be generalised to any integral type, of which *Int* and *Integer* are the standard instances:

![image](images/image71_02.jpg)

For efficiency reasons, however, this generalisation is not in fact made in the standard prelude, as noted in [section 3.9](#10_chapter_title_3.html_pg-36-70). In terms of simplification, the first two equations for *drop* can be combined into a single equation that states that removing zero elements from any list gives the same list:

![image](images/image69_04.jpg)

Moreover, the variable *x* in the last equation can be replaced by the wildcard pattern _, because this variable is not used in the body of the equation:

![image](images/image70_00.jpg)

We might similarly expect *n* in the second equation to be replaced by _, but this would make the definition invalid, because patterns of the form *n* + *k* require that *n* is a variable. This constraint could be avoided by replacing the entire pattern *n* + 1 in the second equation by _, but this would change the behaviour of the function. For example, evaluating *drop* (−1) [ ] would then produce the empty list whereas it currently produces an error, because _ can match any integer whereas *n* + 1 only matches integers ≥ 1.

In conclusion, our final definition for *drop* is as follows, which is precisely the definition from the standard prelude in [appendix A](#21_appendix_title.html):

![image](images/image70_01.jpg)

Example – *init*

As a final example, let us consider how the definition for library function *init* that removes the last element from a non-empty list can be constructed.

**Step 1: define the type**

We begin with a type that states that *init* takes a list of values of some type *a*, and produces another list of such values:

![image](images/image72_00.jpg)

**Step 2: enumerate the cases**

As the empty list is not a valid argument for *init*, writing down a skeleton definition using pattern matching requires just one case:

![image](images/image72_01.jpg)

**Step 3: define the simple cases**

Whereas in the previous two examples this step was straightforward, a little more thought is required for the function *init*. By definition, however, removing the last element from a list with one element gives the empty list, so we can introduce a guard to handle this simple case:

![image](images/image70_02.jpg)

Recall that the library function *null* decides if a list is empty or not.

**Step 4: define the other cases**

How can we remove the last element from a list with at least two elements? By simply retaining the head and removing the last element from the tail:

![image](images/image71_00.jpg)

**Step 5: generalise and simplify**

The type for *init* is already as general as possible, but the definition itself can now be simplified by using pattern matching rather than guards, and by using a wildcard pattern in the first equation rather than a variable:

![image](images/image71_01.jpg)

Again, this is precisely the definition from the standard prelude.

![](images/line.jpg)

6.7 Chapter remarks

The recursive definitions presented in this chapter emphasise clarity, but many can be improved in terms of efficiency, using techniques from [chapters 12](#19_chapter_title_12.html) and [13](#20_chapter_title_13.html). The five-step process for defining functions is based upon (10).

![](images/line.jpg)

6.8 Exercises

**1.**  Define the exponentiation operator ↑ for non-negative integers using the same pattern of recursion as the multiplication operator *, and show how 2 ↑ 3 is evaluated using your definition.

**2.**  Using the definitions given in this chapter, show how *length* [1, 2, 3], *drop* 3 [1, 2, 3, 4, 5], and *init* [1, 2, 3] are evaluated.

**3.**  Without looking at the definitions from the standard prelude, define the following library functions using recursion.

**–**  Decide if all logical values in a list are *True*:

![image](images/image73_02.jpg)

**–**  Concatenate a list of lists:

![image](images/image73_03.jpg)

**–**  Produce a list with *n* identical elements:

![image](images/image73_04.jpg)

**–**  Select the *n*th element of a list:

![image](images/image73_05.jpg)

**–**  Decide if a value is an element of a list:

![image](images/image73_06.jpg)

Note: most of these functions are in fact defined in the prelude using other library functions, rather than using explicit recursion.

**4.**  Define a recursive function *merge* :: *Ord a* ⇒ [*a*] → [*a*] → [*a*] that merges two sorted lists to give a single sorted list. For example:

![image](images/image74_02.jpg)

Note: your definition should not use other functions on sorted lists such as *insert* or *isort*, but should be defined using explicit recursion.

**5.**  Using *merge*, define a recursive function *msort* :: *Ord a* ⇒ [*a*] → [*a*] that implements *merge sort*, in which the empty list and singleton lists are already sorted, and any other list is sorted by merging together the two lists that result from sorting the two halves of the list separately.

Hint: first define a function *halve* :: [*a*] → ([*a*], [*a*]) that splits a list into two halves whose lengths differ by at most one.

**6.**  Using the five-step process, define the library functions that calculate the *sum* of a list of numbers, *take* a given number of elements from the start of a list, and select the *last* element of a non-empty list.

chapter 7

**Higher-order functions**

In this chapter we introduce higher-order functions, which allow common programming patterns to be encapsulated as functions. We start by explaining what higher-order functions are and why they are useful, then introduce a number of standard higher-order functions for processing lists, consider function composition, and conclude by developing a string transmitter.

![](images/line.jpg)

7.1 Basic concepts

As we have seen in previous chapters, functions with multiple arguments are usually defined in Haskell using the notion of currying. That is, the arguments are taken one at a time by exploiting the fact that functions can return functions as results. For example, the definition

![image](images/image73_00.jpg)

means

![image](images/image75_04.jpg)

and states that *add* is a function that takes an integer *x* and returns a function, which in turn takes another integer *y* and returns their sum *x* + *y*. In Haskell, it is also permissible to define functions that take functions as arguments. For example, a function that takes a function and a value, and returns the result of applying the function twice to the value, can be defined as follows:

![image](images/image73_01.jpg)

For example:

![image](images/image76_02.jpg)

Moreover, because *twice* is a curried function, it can be partially applied with just one argument to build other useful functions. For example, a function that quadruples a number is given by *twice* (*2), and the fact that reversing a (finite) list twice has no effect is captured by the equation *twice reverse* = *id*, where *id* is the identity function defined by *id x* = *x*.

Formally speaking, a function that takes a function as an argument or returns a function as a result is called *higher-order*. In practice, however, because the term curried already exists for returning functions as results, the term higher-order is often just used for taking functions as arguments. It is this latter interpretation that is the subject of this chapter.

Using higher-order functions considerably increases the power of Haskell, by allowing common programming patterns to be encapsulated as functions within the language itself. More generally, higher-order functions can be used to define “domain-specific” languages within Haskell. For example, in this chapter we present a simple language for processing lists, and in [chapters 8](#15_chapter_title_8.html) and [9](#16_chapter_title_9.html) we do the same for building parsers and interactive programs.

![](images/line.jpg)

7.2 Processing lists

The standard prelude defines a number of useful higher-order functions for processing lists. For example, the function *map* applies a function to all elements of a list, and can be defined using a list comprehension as follows:

![image](images/image74_00.jpg)

That is, *map f xs* returns the list of all values *f x* such that *x* is an element of the list *xs*. For example, we have:

![image](images/image76_03.jpg)

There are three further points to note about *map*. First of all, it is a polymorphic function that can be applied to lists of any type, as are most higher-order functions on lists. Secondly, it can be applied to itself to process nested lists. For example, the function *map* (*map* (+1)) increments each number in a list of lists of numbers, as shown in the following calculation:

![image](images/image74_01.jpg)

And, finally, the function *map* can also be defined using recursion:

![image](images/image75_00.jpg)

That is, applying a function to all elements of the empty list gives the empty list, while for a non-empty list the function is simply applied to the head of the list, and we then proceed to apply the function to all elements of the tail. The original definition for *map* using a list comprehension is simpler, but the recursive definition is preferable for reasoning purposes (see [chapter 13](#20_chapter_title_13.html).)

Another useful library function is *filter*, which selects all elements of a list that satisfy a predicate, where a *predicate* (or property) is a function that returns a logical value. As with *map*, the function *filter* also has a simple definition using a list comprehension:

![image](images/image75_01.jpg)

That is, *filter p xs* returns the list of all values *x* such that *x* is an element of the list *xs* and the value of *p x* is *True*. For example:

![image](images/image77_03.jpg)

As with *map*, the function *filter* can be applied to lists of any type, and can be defined using recursion for the purposes of reasoning:

![image](images/image75_02.jpg)

That is, selecting all elements that satisfy a predicate from the empty list gives the empty list, while for a non-empty list the result depends upon whether the head satisfies the predicate. If it does then the head is retained and we then proceed to filter elements from the tail of the list, otherwise the head is discarded and we simply filter elements from the tail.

The functions *map* and *filter* are often used together in programs, with *filter* being used to select certain elements from a list, each of which is then transformed using *map*. For example, a function that returns the sum of the squares of the even integers from a list could be defined as follows:

![image](images/image75_03.jpg)

We conclude this section by illustrating a number of other higher-order functions for processing lists that are defined in the standard prelude.

•  Decide if all elements of a list satisfy a predicate:

![image](images/image78_03.jpg)

•  Decide if any element of a list satisfies a predicate:

![image](images/image78_04.jpg)

•  Select elements from a list while they satisfy a predicate:

![image](images/image78_05.jpg)

•  Remove elements from a list while they satisfy a predicate:

![image](images/image78_06.jpg)

![](images/line.jpg)

7.3 The *foldr* function

Many functions that take a list as their argument can be defined using the following simple pattern of recursion on lists:

![image](images/image76_00.jpg)

That is, the function maps the empty list to a value *v*, and any non-empty list to an operator ⊕ applied to the head of the list and the result of recursively processing the tail. For example, a number of familiar library functions on lists can be defined using this pattern:

![image](images/image76_01.jpg)

The higher-order library function *foldr* (abbreviating “fold right”) encapsulates this pattern of recursion for defining functions on lists, with the operator ⊕ and the value *v* as arguments. For example, using *foldr* the four definitions above can be rewritten more compactly as follows:

![image](images/image77_00.jpg)

(Recall that operators must be parenthesised when used as arguments.) These new definitions could also include explicit list arguments, as in *sum xs* = *foldr* (+) 0 *xs*, but we prefer the above definitions in which these arguments are made implicit using partial application because they are simpler.

The *foldr* function itself is defined using recursion:

![image](images/image77_01.jpg)

That is, the function *foldr f v* maps the empty list to the value *v*, and any non-empty list to the function *f* applied to the head of the list and the recursively processed tail. In practice, however, it is best to think of the behaviour of *foldr f v* in a non-recursive manner, as simply replacing each cons operator in a list by the function *f*, and the empty list at the end by the value *v*. For example, applying the function *foldr* (+) 0 to the list

![image](images/image79_05.jpg)

gives the result

![image](images/image79_06.jpg)

in which : and [ ] have been replaced by + and 0, respectively. Hence, the definition *sum* = *foldr* (+) 0 states that summing a list of numbers amounts to replacing each cons by addition and the empty list by zero.

Even though *foldr* encapsulates a simple pattern of recursion, it can be used to define many more functions than might first be expected. First of all, recall the following definition for the library function *length*:

![image](images/image77_02.jpg)

For example, applying *length* to the list

![image](images/image79_05.jpg)

gives the result

![image](images/image79_07.jpg)

That is, calculating the length of a list amounts to replacing each cons by the function that adds one to its second argument, and the empty list by zero. Hence, the definition for *length* can be rewritten using *foldr*:

![image](images/image79_08.jpg)

Now let us consider the library function that reverses a list, which can be defined using explicit recursion as follows:

![image](images/image78_00.jpg)

For example, applying *reverse* to the list

![image](images/image79_05.jpg)

gives the result

![image](images/image80_04.jpg)

It is perhaps not immediately clear from the definition, or the example, how *reverse* can be defined using *foldr*. However, if we define a function *snoc x xs* = *xs* ++ [*x*] that adds a new element at the end of a list rather than at the start (“snoc” is cons backwards), then *reverse* can be redefined as

![image](images/image78_01.jpg)

from which a definition using *foldr* is then immediate:

![image](images/image80_05.jpg)

That is, reversing a list amounts to replacing each cons by *snoc* and the empty list by itself. The append operator ++ used in the definition of *snoc* can itself be defined in a particularly compact manner using *foldr*:

![image](images/image80_06.jpg)

That is, appending *ys* to the end of a list amounts to replacing each cons in the list by itself, and the empty list at the end by *ys*.

We conclude this section by noting that the name fold *right* reflects the use of an operator that is assumed to associate to the right. For example, evaluating *foldr* (+) 0 [1, 2, 3] gives the result 1 + (2 + (3 + 0)), in which the bracketing specifies that addition here is assumed to associate to the right. More generally, the behaviour of *foldr* can be summarised as follows:

![image](images/image80_07.jpg)

![](images/line.jpg)

7.4 The *foldl* function

It is also possible to define recursive functions on lists using an operator that is assumed to associate to the left. For example, the function *sum* can be redefined in this manner by using an auxiliary function *sum*′ that takes an extra argument *v* that is used to accumulate the final result:

![image](images/image78_02.jpg)

For example:

![image](images/image79_00.jpg)

The bracketing in this calculation specifies that addition is now assumed to associate to the left. In practice, however, the order of association does not affect the value of the result in this case, because addition is *associative*. That is, *x* + (*y* + *z*) = (*x* + *y*) + *z* for any numbers *x*, *y*, and *z*.

Generalising from the *sum* example, many functions on lists can be defined using the following simple pattern of recursion:

![image](images/image79_01.jpg)

That is, the function maps the empty list to the *accumulator* value *v*, and any non-empty list to the result of recursively processing the tail using a new accumulator value obtained by applying an operator ⊕ to the current value and the head of the list. The higher-order library function *foldl* (abbreviating “fold left”) encapsulates this pattern of recursion, with the operator ⊕ and the accumulator *v* as arguments. For example, using *foldl* the above definition for *sum* can be rewritten more compactly as follows:

![image](images/image81_02.jpg)

Similarly, we have:

![image](images/image79_02.jpg)

The other *foldr* examples from the previous section can also be redefined using *foldl*, by supplying the appropriate operators:

![image](images/image79_03.jpg)

For example, with these new definitions:

![image](images/image79_04.jpg)

When a function can be defined using both *foldr* and *foldl*, as in the above examples, the choice of which definition is preferable is usually made on grounds of efficiency and requires careful consideration of the evaluation mechanism underlying Haskell, which is discussed in [chapter 12](#19_chapter_title_12.html).

The *foldl* function itself is defined using recursion:

![image](images/image80_00.jpg)

In practice, however, as with *foldr* it is best to think of the behaviour of *foldl* in a non-recursive manner, in terms of an operator ⊕ that is assumed to associate to the left, as summarised by the following equation:

![image](images/image82_02.jpg)

![](images/line.jpg)

7.5 The composition operator

The higher-order library operator ![](images/sm.jpg) returns the *composition* of two functions as a single function, and can be defined as follows:

![image](images/image80_01.jpg)

That is, *f* ![](images/sm.jpg) *g* (read as “*f* composed with *g*”) is the function that takes an argument *x*, applies the function *g* to this argument, and applies the function *f* to the result. This operator could also be defined by (*f* ![](images/sm.jpg) *g*) *x* = *f* (*g x*). However, we prefer the above definition in which the *x* argument is shunted to the body of the definition using a lambda expression, because it makes explicit the idea that composition returns a function as its result.

Composition can be used to simplify nested function applications, by reducing parentheses and avoiding the need to explicitly refer to the initial argument. For example, using composition the definitions

![image](images/image80_02.jpg)

can be rewritten more simply:

![image](images/image80_03.jpg)

The last definition exploits the fact that composition is associative. That is, *f* ![](images/sm.jpg) (*g* ![](images/sm.jpg) *h*) = (*f* ![](images/sm.jpg) *g*) ![](images/sm.jpg) *h* for any functions *f*, *g*, and *h* of the appropriate types. Hence, in a composition of three of more functions, as in *sumsqreven*, there is no need to include parentheses to indicate the order of association, because associativity ensures that this does not affect the result.

Composition also has an identity, given by the *identity function*:

![image](images/image81_00.jpg)

That is, *id* is the function that simply returns its argument unchanged, and has the property that *id* ![](images/sm.jpg) *f* = *f* and *f* ![](images/sm.jpg) *id* = *f* for any function *f*. The identity function is often useful when reasoning about programs, and also provides a suitable starting point for a sequence of compositions. For example, the composition of a list of functions can be defined as follows:

![image](images/image81_01.jpg)

![](images/line.jpg)

7.6 String transmitter

We conclude this chapter with an extended example. Consider the problem of simulating the transmission of a string using zeros and ones. More precisely, we seek to define a function that converts a string into a list of zeros and ones, together with a function that performs the opposite conversion.

Binary numbers

As a consequence of having ten fingers, people normally find it most convenient to use numbers written in base-ten or *decimal* notation. A decimal number is sequence of digits in the range zero to nine, in which the rightmost digit has a weight of one, and successive digits as we move to the left in the number increase in weight by a factor of ten. For example, the decimal number 2345 can be understood in these terms as follows:

![image](images/image83_05.jpg)

That is, 2345 represents the sum of the products of the weights 1000,100,10,1 with the digits 2,3,4,5, which evaluates to the integer 2345.

In contrast, computers normally find it more convenient to use numbers written in the more primitive base-two or *binary* notation. A binary number is a sequence of zeros and ones, called binary digits or *bits*, in which successive bits as we move to the left increase in weight by a factor of two. For example, the binary number 1101 can be understood as follows:

![image](images/image83_06.jpg)

That is, 1101 represents the sum of the products of the weights 8,4,2,1 with the bits 1,1,0,1, which evaluates to the integer 13.

To simplify the definition of certain functions, we assume for the remainder of this example that binary numbers are written in *reverse* order to normal. For example, 1101 would now be written as 1011, with successive bits as we move to the right increasing in weight by a factor of two:

![image](images/image83_07.jpg)

Base conversion

To make the types of the functions that we define more meaningful, we declare a type for bits as a synonym for the type of integers:

![image](images/image84_02.jpg)

A binary number, represented as a list of bits, can be converted into an integer by simply evaluating the required weighted sum:

![image](images/image82_00.jpg)

The higher-order library function *iterate* produces a list by applying a function an increasing number of times to a value:

![image](images/image84_03.jpg)

Hence the expression *iterate* (*2) 1 used within the definition of *bin2int* produces the list of weights [1, 2, 4, 8, · · ·]. This list is notionally infinite, but under lazy evaluation as discussed in [chapter 12](#19_chapter_title_12.html), only as many elements as required by the context in which it is used — in this case zipping with the list of bits — will actually be produced. For example:

![image](images/image84_04.jpg)

There is, however, a simpler way to define *bin2int*, which can be revealed with the aid of a little algebra. Consider an arbitrary four-bit binary number [*a*, *b*, *c*, *d*]. Applying *bin2int* to this list will produce the weighted sum

![image](images/image84_05.jpg)

which can be restructured as follows:

![image](images/image82_01.jpg)

The final result shows that converting a list of bits [*a*, *b*, *c*, *d*] into an integer amounts to replacing each cons by the function that adds its first argument to twice its second argument, and replacing the empty list by zero. More generally, we conclude that *bin2int* can be rewritten using *foldr*:

![image](images/image84_06.jpg)

Now let us consider the opposite conversion, from a non-negative integer into a binary number. This can be achieved by repeatedly dividing the integer by two and taking the remainder, until the integer becomes zero. For example, starting with the integer 13 we proceed as follows:

![image](images/image83_00.jpg)

The sequence of remainders, 1011, provides the binary representation of the integer 13\. It is easy to implement this procedure using recursion:

![image](images/image83_01.jpg)

For example:

![image](images/image85_01.jpg)

We will ensure that all our binary numbers have the same length, eight bits, by using a function *make8* that truncates or extends a binary number as appropriate to make it precisely eight bits:

![image](images/image83_02.jpg)

The library function *repeat* produces an infinite list of copies of a value, but once again lazy evaluation ensures that only as many elements as required by the context will actually be produced. For example:

![image](images/image85_02.jpg)

Transmission

We can now define a function that encodes a string of characters as a list of bits by converting each character into a Unicode number, converting each such number into an eight-bit binary number, and concatenating each of these numbers together to produce a list of bits. Using the higher-order functions *map* and composition, this conversion can be implemented as follows:

![image](images/image83_03.jpg)

For example:

![image](images/image85_03.jpg)

To decode a list of bits produced using *encode*, we first define a function *chop8* that chops such a list up into eight-bit binary numbers:

![image](images/image83_04.jpg)

It is now easy to define a function that decodes a list of bits as a string of characters by chopping the list up, and converting each resulting binary number into a Unicode number and then a character:

![image](images/image84_00.jpg)

For example:

![image](images/image86_01.jpg)

Finally, we define a function *transmit* that simulates the transmission of a string of characters as a list of bits, using a perfect communication channel that we model using the identity function:

![image](images/image84_01.jpg)

For example:

![image](images/image86_02.jpg)

![](images/line.jpg)

7.7 Chapter remarks

Further applications of higher-order functions, including the production of computer music, financial contracts, graphical images, hardware descriptions, logic programs, and pretty printers can be found in *The Fun of Programming* (7). A more in-depth tutorial on *foldr* is given in (14).

![](images/line.jpg)

7.8 Exercises

**1.**  Show how the list comprehension [*f x* | *x* ← *xs*, *p x*] can be re-expressed using the higher-order functions *map* and *filter*.

**2.**  Without looking at the definitions from the standard prelude, define the higher-order functions *all*, *any*, *takeWhile*, and *dropWhile*.

**3.**  Redefine the functions *map f* and *filter p* using *foldr*.

**4.**  Using *foldl*, define a function *dec2int* :: [*Int*] → *Int* that converts a decimal number into an integer. For example:

![image](images/image86_03.jpg)

**5.**  Explain why the following definition is invalid:

![image](images/image86_04.jpg)

**6.**  Without looking at the standard prelude, define the higher-order library function *curry* that converts a function on pairs into a curried function, and, conversely, the function *uncurry* that converts a curried function with two arguments into a function on pairs.

Hint: first write down the types of the two functions.

**7.**  A higher-order function *unfold* that encapsulates a simple pattern of recursion for producing a list can be defined as follows:

     ![image](images/image85_00.jpg)

That is, the function *unfold p h t* produces the empty list if the predicate *p* is true of the argument, and otherwise produces a non-empty list by applying the function *h* to give the head, and the function *t* to generate another argument that is recursively processed in the same way to produce the tail of the list. For example, the function *int2bin* can be rewritten more compactly using *unfold* as follows:

![image](images/image87_00.jpg)

Redefine the functions *chop8*, *map f* and *iterate f* using *unfold*.

**8.**  Modify the string transmitter program to detect simple transmission errors using parity bits. That is, each eight-bit binary number produced during encoding is extended with a parity bit, set to one if the number contains an odd number of ones, and to zero otherwise. In turn, each resulting ninebit binary number consumed during decoding is checked to ensure that its parity bit is correct, with the parity bit being discarded if this is the case, and a parity error reported otherwise.

Hint: the library function *error* :: *String* → *a* terminates evaluation and displays the given string as an error message.

**9.**  Test your new string transmitter program from the previous exercise using a faulty communication channel that forgets the first bit, which can be modelled using the *tail* function on lists of bits.

chapter 8

**Functional parsers**

In this chapter we show how Haskell can be used to program simple parsers. We start by explaining what parsers are and why they are useful, show how parsers can naturally be viewed as functions, define a number of basic parsers and higher-order functions for combining parsers in various ways, and conclude by developing a parser for arithmetic expressions.

![](images/line.jpg)

8.1 Parsers

A *parser* is a program that takes a string of characters, and produces some form of tree that makes the syntactic structure of the string explicit. For example, given the string 2 * 3 + 4, a parser for arithmetic expressions might produce a tree of the following form, in which the numbers appear at the leaves of the tree, and the operators appear at the branches:

![image](images/image86_00.jpg)

The structure of this tree makes explicit that + and * are operators with two arguments, and that * has higher priority than +.

Parsers are an important topic in computing, because most real-life programs use a parser to pre-process their input. For example, a calculator program parses numeric expressions prior to evaluating them, the Hugs system parses Haskell programs prior to executing them, and a web browser parses hypertext documents prior to displaying them. In each case, making the structure of the input explicit considerably simplifies its further processing. For example, once a numeric expression has been parsed into a tree structure such as in the example above, evaluating the expression is straightforward.

![](images/line.jpg)

8.2 The parser type

In Haskell, a parser can naturally be viewed directly as a function that takes a string and produces a tree. Hence, given a suitable type *Tree* of trees, the notion of a parser can be represented as a function of type *String* → *Tree*, which we abbreviate as *Parser* using the following declaration:

![image](images/image89_03.jpg)

In general, however, a parser might not always consume its entire argument string. For example, a parser for numbers might be applied to a string comprising a number followed by a word. For this reason, we generalise our type for parsers to also return any unconsumed part of the argument string:

![image](images/image89_04.jpg)

Similarly, a parser might not always succeed. For example, a parser for numbers might be applied to a string comprising a word. To handle this, we further generalise our type for parsers to return a list of results, with the convention that the empty list denotes failure, and a singleton list denotes success:

![image](images/image89_05.jpg)

Returning a list also opens up the possibility of returning more than one result if the argument string can be parsed in more than one way. For simplicity, however, we only consider parsers that return at most one result.

Finally, different parsers will likely return different kinds of trees, or more generally, any kind of value. For example, a parser for numbers might return an integer value. Hence, it is useful to abstract from the specific type *Tree* of result values, and make this into a parameter of the *Parser* type:

![image](images/image89_06.jpg)

In summary, this declaration states that a parser of type *a* is a function that takes an input string and produces a list of results, each of which is a pair comprising a result value of type *a* and an output string. Alternatively, the parser type can also be read as a rhyme in the style of Dr Seuss!

*A parser for things
Is a function from strings
To lists of pairs
Of things and strings*

![](images/line.jpg)

8.3 Basic parsers

We now define three basic parsers that will be used as the building blocks for all other parsers. First of all, the parser *return v* always succeeds with the result value *v*, without consuming any of the input string:

![image](images/image89_07.jpg)

This function could equally well be defined by *return v inp* = [(*v*, *inp*)]. However, we prefer the above definition in which the second argument *inp* is shunted to the body of the definition using a lambda expression, because it makes explicit that *return* is a function that takes a single argument and returns a parser, as expressed by the type *a* → *Parser a*.

Whereas *return v* always succeeds, the dual parser *failure* always fails, regardless of the contents of the input string:

![image](images/image88_00.jpg)

Our final basic parser is *item*, which fails if the input string is empty, and succeeds with the first character as the result value otherwise:

![image](images/image88_01.jpg)

The **case** mechanism of Haskell used in this definition allows pattern matching to be used in the body of a definition, in this example by matching the string *inp* against two patterns to choose between two possible results. The **case** mechanism is not used much in this book, but can sometimes be useful.

Because parsers are functions, they could be applied to a string using normal function application, but we prefer to abstract from the representation of parsers by defining our own application function:

![image](images/image88_02.jpg)

Using *parse*, we conclude this section with some examples that illustrate the behaviour of the three basic parsers defined above:

![image](images/image90_02.jpg)

![](images/line.jpg)

8.4 Sequencing

Perhaps the simplest way of combining two parsers is to apply one after the other in sequence, with the output string returned by the first parser becoming the input string to the second. But how should the result values from the two parsers be handled? One approach would be to combine the two values as a pair, using a sequencing operator for parsers with the following type:

![image](images/image91_02.jpg)

In practice, however, it turns out to be more convenient to combine the sequencing of parsers with the processing of their result values, by means of a sequencing operator >>= (read as “then”) defined as follows:

![image](images/image89_00.jpg)

That is, the parser *p* >>= *f* fails if the application of the parser *p* to the input string fails, and otherwise applies the function *f* to the result value to give a second parser, which is then applied to the output string to give the final result. In this manner, the result value produced by the first parser is made directly available for processing by the second.

A typical parser built using >>= has the following structure:

![image](images/image91_03.jpg)

That is, apply the parser *p1* and call its result value *v1*; then apply the parser *p2* and call its result value *v2*; *. . .*; then apply the parser *pn* and call its result value *vn*; and, finally, combine all the results into a single value by applying the function *f*. Haskell provides a special syntax for such parsers, allowing them to be expressed in the following, more appealing, form:

![image](images/image89_01.jpg)

As with list comprehensions, the expressions *vi* ← *pi* are called *generators*. If the result value produced by a generator *vi* ← *pi* is not required, the generator can be abbreviated simply by *pi*. Note also that the layout rule applies to the **do** notation for sequencing parsers, in the sense that each parser in the sequence must begin in precisely the same column.

For example, a parser that consumes three characters, discards the second, and returns the first and third as a pair can now be defined as follows:

![image](images/image89_02.jpg)

Note that *p* only succeeds if every parser in its defining sequence succeeds, which requires at least three characters in the input string:

![image](images/image92_02.jpg)

![](images/line.jpg)

8.5 Choice

Another natural way of combining two parsers is to apply the first parser to the input string, and if this fails to apply the second instead. Such a choice operator +++ (read as “or else”) can be defined as follows:

![image](images/image90_00.jpg)

For example:

![image](images/image92_03.jpg)

![](images/line.jpg)

8.6 Derived primitives

Using the three basic parsers together with sequencing and choice, we can now define a number of other useful parsing primitives. First of all, we define a parser *sat p* for single characters that satisfy the predicate *p*:

![image](images/image90_01.jpg)

Using *sat* and appropriate predicates from the standard prelude, we can define parsers for single digits, lower-case letters, upper-case letters, arbitrary letters, alphanumeric characters, and specific characters:

![image](images/image91_00.jpg)

For example:

![image](images/image93_03.jpg)

In turn, using *char* we can define a parser *string xs* for the string of characters *xs*, with the string itself returned as the result value:

![image](images/image91_01.jpg)

Note that *string* is defined using recursion, and only succeeds if the entire target string is consumed. The base case states that the empty string can always be parsed. The recursive case states that a non-empty string can be parsed by parsing the first character, parsing the remaining characters, and returning the entire string as the result value. For example:

![image](images/image93_04.jpg)

Our next two parsers, *many p* and *many1 p*, apply a parser *p* as many times as possible until it fails, with the result values from each successful application of *p* being combined as a list. The difference between these two repetition primitives is that *many* permits zero or more applications of *p*, whereas *many1* requires at least one successful application:

![image](images/image92_00.jpg)

Note that *many* and *many1* are defined using mutual recursion. In particular, the definition for *many p* states that *p* can either be applied at least once or not at all, while the definition for *many1 p* states that *p* can be applied once and then zero or more times. For example:

![image](images/image94_03.jpg)

Using *many* and *many1*, we can define parsers for *identifiers* (variable names) comprising a lower-case letter followed by zero or more alphanumeric characters, natural numbers comprising one or more digits, and spacing comprising zero or more space, tab, and newline characters:

![image](images/image92_01.jpg)

For example:

![image](images/image94_04.jpg)

Note that *space* returns the empty tuple () as a dummy result value, reflecting the fact that the details of spacing are not usually important.

![](images/line.jpg)

8.7 Handling spacing

Most real-life parsers allow spacing to be freely used around the basic *tokens* in their input string. For example, the strings 1+2 and 1 + 2 are both parsed in the same way by Hugs. To handle such spacing, we define a new primitive that ignores any space before and after applying a parser for a token:

![image](images/image93_00.jpg)

Using *token*, it is now easy to define parsers that ignore spacing around identifiers, natural numbers, and special symbols:

![image](images/image93_01.jpg)

For example, a parser for a non-empty list of natural numbers that ignores spacing around tokens can be defined as follows:

![image](images/image93_02.jpg)

This definition states that such a list begins with an opening square bracket and a natural number, followed by zero or more commas and natural numbers, and concludes with a closing square bracket. Note that *p* only succeeds if a complete list in precisely this format is consumed:

![image](images/image95_04.jpg)

![](images/line.jpg)

8.8 Arithmetic expressions

We conclude this chapter with an extended example. Consider a simple form of arithmetic expressions built up from natural numbers using addition, multiplication, and parentheses. We assume that addition and multiplication associate to the right, and that multiplication has higher priority than addition. For example, 2 + 3 + 4 means 2 + (3 + 4), while 2 * 3 + 4 means (2 * 3) + 4.

The syntactic structure of a language can be formalised using the mathematical notion of a *grammar*, which is a set of rules that describes how strings of the language can be constructed. For example, a grammar for our language of arithmetic expressions can be defined by the following two rules:

![image](images/image94_00.jpg)

The first rule states that an expression is either the addition or multiplication of two expressions, a parenthesised expression, or a natural number. In turn, the second rule states that a natural number is either zero, one, two, etc. For example, using this grammar the construction of the expression 2 * 3 + 4 can be represented by the following *parse tree*, in which the tokens in the expression appear at the leaves, and the grammatical rules applied to construct the expression give rise to the branching structure:

![image](images/image94_01.jpg)

The structure of this tree makes explicit that 2 * 3 + 4 can be constructed from the addition of two expressions, the first given by the multiplication of two further expressions which are in turn given by the numbers two and three, and the second expression given by the number four. However, the grammar also permits another possible parse tree for this example, which corresponds to the erroneous interpretation of the expression as 2 * (3 + 4):

![image](images/image94_02.jpg)

The problem is that our grammar for expressions does not take account of the fact that multiplication has higher priority than addition. However, this can easily be fixed by modifying the grammar to have a separate rule for each level of priority, with addition at the lowest level of priority, multiplication at the middle level, and parentheses and numbers at the highest level:

![image](images/image95_00.jpg)

Using this new grammar, 2 * 3 + 4 indeed has a single parse tree, which corresponds to the correct interpretation of the expression as (2 * 3) + 4:

![image](images/image95_01.jpg)

We have now dealt with the issue of priority, but our grammar does not yet take account of the fact that addition and multiplication associate to the right. For example, the expression 2 + 3 + 4 currently has two possible parse trees, corresponding to (2 + 3) + 4 and 2 + (3 + 4). However, this can also easily be fixed by modifying the grammatical rules for addition and multiplication to be recursive in their right argument only, rather than both arguments:

![image](images/image95_02.jpg)

Using these new rules, 2 + 3 + 4 now has a single parse tree, which corresponds to the correct interpretation of the expression as 2 + (3 + 4):

![image](images/image95_03.jpg)

In fact, our grammar for expressions is now unambiguous, in the sense that every well-formed expression has precisely one parse tree.

Our final modification to the grammar is one of simplification. For example, consider the rule *expr* ::= *term* + *expr* | *term*, which states that an expression is either the addition of a term and an expression, or is a term. In other words, an expression always begins with a term, which can then be followed by the addition of an expression or by nothing. Hence, the rule for expressions can be simplified to *expr* ::= *term* (+ *expr* | ![](images/e.jpg)), in which the symbol ![](images/e.jpg) denotes the empty string. Simplifying the rule for terms in a similar manner gives our final grammar for arithmetic expressions:

![image](images/image96_00.jpg)

It is now straightforward to translate this grammar into a parser for expressions, by simply rewriting the rules using our parsing primitives. In fact, we choose to have the parser itself evaluate the expression being parsed to its integer value, rather than returning some form of tree:

![image](images/image96_01.jpg)

For example, the parser *expr* first parses a term with value *t*, then parses a plus symbol followed by an expression with value *e* and returns the value *t* + *e*, or else parses nothing further and simply returns the value *t*. The parsers *term* and *factor* can be read in a similar manner.

Finally, using *expr* we define a function *eval* :: *String* → *Int* that evaluates an arithmetic expression to its integer value. To handle the cases of unconsumed and invalid input, we use the library function *error* :: *String* → *a* that displays an error message and then terminates the program:

![image](images/image97_00.jpg)

For example:

![image](images/image99_00.jpg)

![](images/line.jpg)

8.9 Chapter remarks

A library file comprising the parsing primitives from this chapter is available from the book’s website. For technical reasons concerning the monadic nature of parsers, a number of the basic definitions in this library are slightly different to those given here. Further details are available in (16; 17), upon which this chapter is based. More information concerning grammars can be found in (27), and more advanced approaches to building parsers in Haskell are given in (22; 9). The reading of the parser type as a rhyme is due to Fritz Ruehr.

![](images/line.jpg)

8.10 Exercises

**1.**  The library file also defines a parser *int* :: *Parser Int* for an integer. Without looking at this definition, define *int*. Hint: an integer is either a minus symbol followed by a natural number, or a natural number.

**2.**  Define a parser *comment* :: *Parser* () for ordinary Haskell comments that begin with the symbol -- and extend to the end of the current line, which is represented by the control character ’\n’.

**3.**  Using our second grammar for arithmetic expressions, draw the two possible parse trees for the expression 2 + 3 + 4.

**4.**  Using our third grammar for arithmetic expressions, draw the parse trees for the expressions 2 + 3, 2 * 3 * 4 and (2 + 3) + 4.

**5.**  Explain why the final simplification of the grammar for arithmetic expressions has a dramatic effect on the efficiency of the resulting parser. Hint: begin by considering how an expression comprising a single number would be parsed if this step had not been made.

**6.** Extend the parser for arithmetic expressions to support subtraction and division, based upon the following extensions to the grammar:

      ![image](images/image98_00.jpg)

**7.**  Further extend the grammar and parser for arithmetic expressions to support exponentiation, which is assumed to associate to the right and have higher priority than multiplication and division, but lower priority than parentheses and numbers. For example, 2 ↑ 3 * 4 means (2 ↑ 3) * 4\. Hint: the new level of priority requires a new rule in the grammar.

**8.**  Consider expressions built up from natural numbers using a subtraction operator that is assumed to associate to the left.

**(a)**  Define a natural grammar for such expressions.

**(b)**  Translate this grammar into a parser *expr* :: *Parser Int*.

**(c)**  What is the problem with this parser?

**(d)**  Show how it can be fixed. Hint: rewrite the parser using the repetition primitive *many* and the library function *foldl*.

chapter 9

**Interactive programs**

In this chapter we show how Haskell can be used to write interactive programs. We start by explaining what interactive programs are, show how such programs can naturally be viewed as functions, define a number of basic interactive programs and higher-order functions for combining interactive programs, and conclude by developing a calculator and the game of life.

![](images/line.jpg)

9.1 Interaction

A *batch* program is one that does not interact with the user while it is running. In the early days of computing, most programs were batch programs, run in isolation from their users in order to maximise the amount of time that the computer was performing useful work. For example, a route-planning program may take start and finish points as its input, silently perform a large number of calculations, and then produce a recommended route as its output.

Up to this point in the book we have considered how Haskell can be used to write batch programs. In Haskell such programs, and more generally all programs, are modelled as *pure* functions that take all their input as explicit arguments, and produce all their output as explicit results. For example, a route planner may be modelled as a function of type (*Point*, *Point*) → *Route* that takes a pair of points and produces a route between them.

In contrast, an *interactive* program is one that may take additional input from the user, and produce additional output for the user, while the program is running. In the modern era of computing, most programs are interactive programs, run as a dialogue with their users in order to provide increased flexibility. For example, a calculator program may allow the user to enter numeric expressions interactively using the keyboard, and immediately display the value of such expressions on the screen.

At first sight, modelling interactive programs as pure functions may seem infeasible, because such programs by their very nature require the *side effects* of taking additional input and producing additional output while the program is running. For example, how can the calculator program described above be viewed as a pure function from arguments to results?

Over the years there have been many proposed solutions to the problem of combining the notion of pure functions with that of side effects. In the remainder of this chapter we present the solution that is adopted in Haskell, which is based upon the use of a new type in conjunction with a small number of primitives. As we shall see, this approach shares much in common with the approach to parsers presented in the previous chapter.

![](images/line.jpg)

9.2 The input/output type

In Haskell, an interactive program is viewed as a pure function that takes the current “state of the world” as its argument, and produces a modified world as its result, in which the modified world reflects any side effects performed by the program. Hence, given a suitable type *World* whose values represent the current state of the world, the notion of an interactive program can be represented by a function of type *World* → *World*, which we abbreviate as *IO* (short for “input/output”) as follows:

![image](images/image102_04.jpg)

In general, however, an interactive program may return a result value in addition to performing side effects. For example, a program for reading a character from the keyboard may return the character that was read. For this reason, we generalise our type for interactive programs to also return a result value, with the type of such values being a parameter of the *IO* type:

![image](images/image102_05.jpg)

Expressions of type *IO a* are called *actions*. For example, *IO Char* is the type of actions that return a character, while *IO* () is the type of actions that return the empty tuple () as a dummy result value. Actions of the latter type can be thought of as purely side-effecting actions that return no result value, and are frequently used when writing interactive programs.

In addition to returning a result value, interactive programs may also require argument values. However, there is no need to generalise the type of actions to take account of this, because this behaviour can already be achieved by exploiting currying. For example, an interactive program that takes a character and returns an integer would have type *Char* → *IO Int*, which abbreviates the curried function type *Char* → *World* → (*Int*, *World*).

At this point the reader may, quite understandably, be concerned about the feasibility of passing around the entire state of the world when programming with actions. In reality, Haskell systems such as Hugs implement actions in a more efficient manner than described above, but, for the purposes of understanding the behaviour of actions, this abstract view will suffice.

![](images/line.jpg)

9.3 Basic actions

We now introduce three basic actions for building interactive programs. First of all, the action *getChar* reads a character from the keyboard, echoes it to the screen, and returns the character as its result value:

![image](images/image101_00.jpg)

The actual definition for *getChar* is built-in to the Hugs system, and cannot be defined within Haskell itself. If there are no characters waiting to be read from the keyboard, *getChar* waits until one is typed.

The dual action, *putChar c*, writes the character *c* to the screen, and returns no result value, represented by the empty tuple:

![image](images/image101_01.jpg)

Our final basic action is *return v*, which simply returns the result value *v* without performing any interaction:

![image](images/image101_02.jpg)

The function *return* provides a bridge from the setting of pure expressions without side effects to that of impure actions with side effects. Crucially, however, there is no bridge back — once we are impure we are impure for ever, with no possibility for redemption! As a result, we may suspect that impurity quickly permeates entire programs, but in practice this is usually not the case. For most Haskell programs, the vast majority of functions do not involve interaction, with this being handled by a relatively small number of interactive functions at the outermost level.

We conclude this section by noting that evaluating an action using Hugs performs its side effects, and discards the resulting value. For example, evaluating *putChar* ’a’ writes the character ’a’ to the screen, discards the result value from this action, and then terminates:

![image](images/image103_04.jpg)

![](images/line.jpg)

9.4 Sequencing

As with parsers, the natural way of combining two actions is to perform one after the other in sequence, with the modified world returned by the first action becoming the current world for the second, by means of a sequencing operator >>= (read as “then”) defined as follows:

![image](images/image101_03.jpg)

That is, we apply the action *f* to the current world, then apply the function *g* to the result value to give a second action, which is then applied to the modified world to give the final result. In practice, however, as with parsers in the previous chapter, the **do** notation is normally used to express actions defined using >>= in a more appealing form.

For example, using the **do** notation the primitive *getChar* could be decomposed into the actions of reading a character from the keyboard, echoing it to the screen, and returning the character as the result:

![image](images/image102_00.jpg)

The action *getCh* that reads a character without echoing is not part of the standard prelude, but is provided as an extension by Hugs and can be made available in any script by including the following special line:

![image](images/image104_03.jpg)

![](images/line.jpg)

9.5 Derived primitives

Using the three basic actions together with sequencing, we can now define a number of other useful action primitives. First of all, we define an action *getLine* that reads a string of characters from the keyboard:

![image](images/image102_01.jpg)

(The symbol ’\n’ represents a newline character.) Dually, we define actions *putStr* and *putStrLn* that write a string to the screen, with the latter action also moving on to a new line afterwards:

![image](images/image102_02.jpg)

For example, using these primitives we can now define an action that prompts for a string to be entered from the keyboard, and then displays its length:

![image](images/image102_03.jpg)

For example:

![image](images/image105_06.jpg)

In addition to the library primitives defined above, for the purposes of examples in the remainder of this chapter it is also useful to define a number of other primitives. First of all, we define actions that sound a beep and clear the screen, by displaying the appropriate control characters:

![image](images/image103_00.jpg)

By convention, the position of each character on the screen is given by a pair (*x*, *y*) of positive integers, with (1, 1) being the top-left corner. The notion of such a position can be represented by the following type:

![image](images/image105_07.jpg)

Using the appropriate control characters, we can now define a function that moves the cursor to a given position, where the cursor is a marker that indicates where the next character displayed will appear:

![image](images/image103_01.jpg)

In turn, we define a function that displays a string at a given position:

![image](images/image103_02.jpg)

Finally, we define a function *seqn* that performs a list of actions in sequence, discarding their result values and returning no result:

![image](images/image103_03.jpg)

For example, using *seqn* and a list comprehension, the above definition for *putStr* can be rewritten more compactly as follows:

![image](images/image105_08.jpg)

![](images/line.jpg)

9.6 Calculator

At the end of the previous chapter we developed a parser for arithmetic expressions. We now extend this example to produce a simple calculator, which allows the user to enter arithmetic expressions interactively using the keyboard, and displays the value of such expressions on the screen.

Our calculator will handle expressions built up from integers using addition, subtraction, multiplication, division, and parentheses. As the subject of this chapter is interactive programs, we do not concern ourselves with the details of parsing and evaluating expressions, assuming that we are given a suitable parser *expr* :: *Parser Int* for this purpose. Such a parser can be obtained by solving some of the exercises from the previous chapter.

We begin by considering the user interface of the calculator. First of all, we define the box of the calculator as a list of strings:

![image](images/image104_00.jpg)

The first four buttons on the calculator, q, c, d, and =, allow the user to quit, clear the display, delete a character, and evaluate an expression, while the remaining sixteen buttons allow the user to enter expressions.

We also define the buttons on the calculator as a list of characters, comprising both the twenty standard buttons that appear on the box itself, together with a number of extra characters that will be allowed for flexibility, namely Q, C, D, space, escape, backspace, delete, and newline:

![image](images/image104_01.jpg)

Using a list comprehension, we can define an action that displays the calculator box in the top-left corner of the screen:

![image](images/image104_02.jpg)

The last part of the user interface is to define a function that shows a string in the display of the calculator, by first clearing the display and then showing the last thirteen characters of the string. In this manner, if the user deletes characters from the string, they will automatically be removed from the display, and if the user types more than thirteen characters, the display will appear to scroll to the left as additional characters are typed.

![image](images/image105_00.jpg)

The calculator itself is controlled by a function *calc* that displays the current string, and then reads a character from the keyboard without echoing it. If this character is a valid button, then it is processed, otherwise we sound a beep to indicate an error and continue with the same string:

![image](images/image105_01.jpg)

The function *process* takes a valid character and the current string, and performs the appropriate action depending upon the character:

![image](images/image105_02.jpg)

We now consider each of the five possible actions in turn.

•  Quitting moves the cursor below the calculator box and terminates:

![image](images/image105_03.jpg)

•  Deleting has no effect if the current string is empty, and otherwise removes the last character from this string:

![image](images/image105_04.jpg)

•  Evaluation displays the result of parsing and evaluating the current string, sounding a beep if this process is unsuccessful:

![image](images/image105_05.jpg)

•  Clearing the display resets the current string to empty:

![image](images/image106_00.jpg)

•  Any other character is appended to the end of the current string:

![image](images/image106_01.jpg)

Finally, we define a function that runs the calculator, by clearing the screen, displaying the box, and starting with an empty display:

![image](images/image106_02.jpg)

![](images/line.jpg)

9.7 Game of life

We conclude this chapter with a second extended example, concerning the *game of life*. The game models a simple evolutionary system, and is played on a two-dimentional board. Each square on the board is either empty, or contains a single living cell, as shown in the following example:

![image](images/image106_03.jpg)

Each internal square on the board has eight immediate neighbours:

![image](images/image106_04.jpg)

For uniformity, each square on the edge of the board is also viewed as having eight neighbours, by assuming that the board wraps around from top-to-bottom and from left-to-right. That is, we can think of the board as really being a torus, which can be viewed as the surface of a three-dimensional doughnut shaped object.

Given an initial configuration of the board, the next *generation* is given by simultaneously applying the following rules to all squares:

•  a living cell survives if it has precisely two or three neighbouring squares that contain living cells, and dies (becomes empty) otherwise;

•  an empty square gives birth to a living cell if it has precisely three neighbours that contain living cells, and remains empty otherwise.

For example, applying these rules to the above board gives:

![image](images/image107_01.jpg)

By repeating this procedure with the new board, an infinite sequence of generations can be produced. By careful design of the initial configuration, many interesting patterns of behaviour can be observed in this sequence. For example, the above arrangement of cells is called a glider, and over successive generations will move diagonally down the board.

Despite its simplicity, the game of life is in fact computationally complete, in the sense that any computational process can be simulated within it by means of a suitable encoding. In the remainder of this section we show how the game of life can be implemented in Haskell.

To allow the size of the board to be easily modified, we define two integer values that determine the width and height of the board in squares:

![image](images/image107_00.jpg)

We represent a board as a list of the (*x*, *y*) positions at which there is a living cell, using the same coordinate convention as the screen:

![image](images/image109_02.jpg)

For example, the initial example board above would be represented by:

![image](images/image107_02.jpg)

Using this representation of a board, it is easy to display the living cells on the screen, and to decide if a given position is alive or empty:

![image](images/image107_03.jpg)

Next, we define a function that returns the neighbours of a position:

![image](images/image107_04.jpg)

The auxiliary function *wrap* takes account of the wrapping around at the edges of the board, by subtracting one from each component of the given position, taking the remainder when divided by the width and height of the board, and then adding one to each component again:

![image](images/image108_00.jpg)

Using function composition, we can now define a function that calculates the number of live neighbours for a given position by producing the list of its neighbours, retaining those that are alive, and counting their number:

![image](images/image108_01.jpg)

Using this function, it is then straightforward to produce the list of living positions in a board that have precisely two or three living neighbours, and hence survive to the next generation:

![image](images/image108_02.jpg)

In turn, the list of empty positions in a board that have precisely three living neighbours, and hence give birth to a new cell, can be produced as follows:

![image](images/image108_03.jpg)

However, this definition considers every possible position on the board. A more refined approach, which may be more efficient for larger boards, is to only consider the neighbours of living cells on the board, because only such positions can potentially give rise to new births. Using this approach, the function *births* can be rewritten as follows:

![image](images/image108_04.jpg)

The auxiliary function *rmdups* removes duplicates from a list, and is used above to ensure that each potential new cell is only considered once:

![image](images/image108_05.jpg)

The next generation of a board can now be produced simply by appending the list of survivors and the list of new births:

![image](images/image108_06.jpg)

Finally, we define a function *life* that implements the game of life itself, by clearing the screen, showing the living cells in the current board, waiting for a moment, and then continuing with the next generation:

![image](images/image109_00.jpg)

The function *wait* is used to slow down the game to a reasonable speed, and can be implemented by performing a given number of dummy actions:

![image](images/image109_01.jpg)

For fun, you may like to try out the *life* function with the *glider* example, and experiment with some patterns of your own.

![](images/line.jpg)

9.8 Chapter remarks

The use of the *IO* type to perform other forms of side effects, including reading and writing from files, and handling exceptional events, is discussed in the Haskell Report (25). A formal meaning for input/output and other forms of side effects is given in (24). A variety of libraries for performing graphical interaction are available from the Haskell home page, *[www.haskell.org](http://www.haskell.org)*. The game of life was invented by John Conway, and popularised by Martin Gardner in the October 1970 edition of Scientific American.

![](images/line.jpg)

9.9 Exercises

**1.**  Define an action *readLine* :: *IO String* that behaves in the same way as *getLine*, except that it also permits the delete key to be used to remove characters. Hint: the delete character is ’\DEL’, and the control string for moving the cursor back one character is "\ESC[1D".

**2.**  Modify the calculator program to indicate the approximate position of an error rather than just sounding a beep, by using the fact that the parser returns the unconsumed part of the input string.

**3.**  On some systems the game of life may flicker, due to the entire screen being cleared each generation. Modify the game to avoid such flicker by only redisplaying positions whose status changes.

**4.**  Produce an editor that allows the user to interactively create and modify the content of the board in the game of life.

**5.**  Produce graphical versions of the calculator and game of life programs, using one of the graphics libraries available from *[www.haskell.org](http://www.haskell.org)*.

**6.**  Nim is a game that is played on a board comprising five numbered rows of stars, which is initially set up as follows:

     ![image](images/image110_00.jpg)

Two players take it in turn to remove one or more stars from the end of a single row. The winner is the player who removes the last star or stars from the board. Implement the game of nim in Haskell. Hint: represent the board as a list comprising the number of stars remaining on each row, with the initial board being [5, 4, 3, 2, 1].

chapter 10

**Declaring types and classes**

In this chapter we introduce mechanisms for declaring new types and classes in Haskell. We start with two approaches to declaring types, then consider recursive types, develop a tautology checker and an abstract machine, and conclude by showing how to declare classes and their instances.

![](images/line.jpg)

10.1 Type declarations

The simplest way of declaring a new type is to introduce a new name for an existing type, using the **type** mechanism of Haskell. For example, the following declaration from the standard library states that the type *String* is just a synonym for the type [*Char*] of lists of characters:

![image](images/image113_02.jpg)

As in this example, the name of a new type must begin with a capital letter. Type declarations can be nested, in the sense that one such type can be declared in terms of another. For example, in the previous chapter a type for boards was declared in terms of a type for positions:

![image](images/image111_00.jpg)

For technical reasons, however, type declarations cannot be recursive. For example, consider the following erroneous declaration:

![image](images/image113_03.jpg)

That is, a tree is a pair comprising an integer and a list of subtrees. While this declaration is perfectly reasonable, with the empty list of subtrees forming the base case for the recursion, it is not permitted in Haskell because it is recursive. If required, recursive types can be declared using the more powerful **data** mechanism, which will be introduced shortly.

Type declarations can also be parameterised by other types. For example, in the previous two chapters we declared the following types for parsers and interactive programs in terms of a type parameter:

![image](images/image112_00.jpg)

Declarations with more than one type parameter are also permitted. For example, a type of lookup tables that associate keys of one type to values of another type can be declared as a list of (key, value) pairs:

![image](images/image114_03.jpg)

Using this type, a function that returns the first value that is associated with a given key in a table can then be defined as follows:

![image](images/image112_01.jpg)

![](images/line.jpg)

10.2 Data declarations

A completely new type, as opposed to a synonym for an existing type, can be declared by specifying its values using the **data** mechanism of Haskell. For example, the following declaration from the standard library states that the type *Bool* comprises two new values, named *False* and *True*:

![image](images/image114_04.jpg)

In such declarations, the symbol | is read as “or”, and the new values of the type are called *constructors*. As with new types themselves, the names of new constructors must begin with a capital letter. Moreover, the same constructor name cannot be used in more than one type.

Note that the names given to new types and constructors have no inherent meaning to the Hugs system. For example, the above declaration could equally well be written as **data** *A* = *B* | *C*, because the precise details of the names are not relevant, other than the fact that they have not been used before. The meaning of names such as *Bool*, *False*, and *True* is assigned by the programmer, via the functions that they define on new types.

Values of new types can be used in precisely the same way as those of built-in types. In particular, they can freely be passed as arguments to functions, returned as results from functions, stored in data structures such as lists, and used in patterns. For example, given the declaration

![image](images/image114_05.jpg)

functions that apply a move to a position (recalling that positions are relative to the top-left corner of the screen), apply a list of moves to a position, and flip the direction of a move, can be defined as follows:

![image](images/image113_00.jpg)

The constructors in a data declaration can also have arguments. For example, a type of shapes that comprise circles with a given radius, and rectangles with given dimensions can be declared by:

![image](images/image115_05.jpg)

That is, the type *Shape* has values of the form *Circle r*, where *r* is a floating-point number, and *Rect x y*, where *x* and *y* are floating-point numbers. These constructors can then be used to define functions on shapes, such as to produce a square of a given size, and to calculate the area of a shape:

![image](images/image113_01.jpg)

Because of their use of arguments, the constructors *Circle* and *Rect* are actually constructor functions, which produce results of type *Shape* from arguments of type *Float*, as can be demonstrated using Hugs:

![image](images/image115_06.jpg)

The difference between normal functions and constructor functions is that the latter have no defining equations, and exist solely for the purpose of building pieces of data. For example, whereas the expression *negate* 1.0 can be evaluated to −1.0 by applying the definition of *negate*, the expression *Circle* 1.0 is already fully evaluated, and hence cannot be further simplified, because there are no defining equations for *Circle*. Rather, the expression *Circle* 1.0 is just a piece of data, in the same way that 1.0 itself is just data.

Not surprisingly, data declarations themselves can also be parameterised. For example, the standard library declares the following type:

![image](images/image115_07.jpg)

That is, a value of type *Maybe a* is either *Nothing*, or of the form *Just x* for some value *x* of type *a*. We can think of values of type *Maybe a* as being values of type *a* that may fail, with *Nothing* representing failure, and *Just* representing success. For example, using this type we can define safe versions of the library functions *div* and *head*, which return *Nothing* in the case of invalid arguments, rather than producing an error:

![image](images/image114_00.jpg)

![](images/line.jpg)

10.3 Recursive types

Types declared using the data mechanism can also be recursive. By way of a simple first example, consider the following recursive type:

![image](images/image116_05.jpg)

That is, a value of type *Nat* is either *Zero*, or of the form *Succ n* for some value *n* of type *Nat*. Hence, this declaration gives rise to an infinite sequence of values, starting with the value *Zero*, and continuing by applying the constructor function *Succ* to the previous value in the sequence:

![image](images/image114_01.jpg)

As suggested by the choice of names, values of type *Nat* can be thought of as natural numbers (non-negative integers), with *Zero* representing the natural number 0 and *Succ* representing the successor function 1+ on such numbers. For example, *Succ* (*Succ* (*Succ Zero*)) represents 1 + (1 + (1 + 0)) = 3\. More formally, we can define the following conversion functions:

![image](images/image114_02.jpg)

For example, using these functions, two natural numbers can be added together by first converting them into integers, adding these integers, and then converting the result back into a natural number:

![image](images/image115_00.jpg)

However, using recursion the function *add* can be redefined without the need for such conversions, and hence more efficiently:

![image](images/image115_01.jpg)

This definition formalises the idea that two natural numbers can be added by copying *Succ* constructors from the first number until they are exhausted, at which point the *Zero* at the end is replaced by the second number. For example, showing that 2 + 1 = 3 proceeds as follows:

![image](images/image115_02.jpg)

As another example, the data mechanism can be used to declare our own version of the built-in type of lists, parameterised by an arbitrary type:

![image](images/image117_03.jpg)

That is, a value of type *List a* is either *Nil*, representing the empty list, or of the form *Cons x xs* for some values *x* :: *a* and *xs* :: *List a*, representing a non-empty list. Using this type, we can then also define our own versions of library functions on lists, such as to calculate the length of a list:

![image](images/image115_03.jpg)

While lists are perhaps the most commonly used data structure in computing, it is often useful to store data in a two-way branching structure, or *binary tree*, as depicted in the following example:

![image](images/image115_04.jpg)

In this example, the numbers 1, 4, 6, 9 appear at the external *leaves* of the tree, and the numbers 5, 3, 7 appear at the internal *nodes*. Using recursion, a suitable type for representing such trees can be declared by:

![image](images/image117_04.jpg)

For simplicity, we have fixed the type of the values to integers, but this could easily be generalised by parameterising the declaration. Using this type, the tree pictured above can be represented as follows:

![image](images/image116_00.jpg)

We now consider a number of functions on such trees. First of all, we define a function that decides if a given integer occurs in a tree:

![image](images/image116_01.jpg)

That is, an integer occurs in a leaf if it matches the value at the leaf, and occurs in a node if it either matches the value at the node, occurs in the left subtree, or occurs in the right subtree. Note that under lazy evaluation, if either of the first two conditions in the node case is *True*, then the result *True* is returned without the need to evaluate the remaining conditions.

In the worst case, however, the function *occurs* may still traverse the entire tree, in particular when the given integer does not occur in the tree. Now consider a function that flattens a tree to a list:

![image](images/image116_02.jpg)

If applying this function results in a sorted list, then the tree itself is called a *search tree*. For instance, our example tree is a search tree, because:

![image](images/image118_03.jpg)

Search trees have the important property that, when trying to decide if a given integer occurs in a tree, which of the two subtrees of a node it may occur in can always be determined. In particular, if the integer is less than the value at the node, then it can only occur in the left subtree, and if it is greater than this value, it can only occur in the right subtree. Hence, for search trees the *occurs* function can be rewritten as follows:

![image](images/image116_03.jpg)

This definition is more efficient than the previous version, because it only traverses one path down the tree, rather than potentially the entire tree.

We conclude this section by noting that, as in nature, trees in computing come in many different forms. For example, we can declare types for trees that have data only in their leaves, data only in their nodes, data in both their leaves and nodes (as above), or have a list of subtrees:

![image](images/image116_04.jpg)

Which form of tree is most appropriate depends upon the situation. Note that in the last example, there is no constructor for leaves, because a node with an empty list of subtrees can play the role of a leaf.

![](images/line.jpg)

10.4 Tautology checker

In practice, tree types often occur as a representation of some kind of language. In this section we present an extended example concerning such a type, by developing a function that decides if simple logical propositions are always true. Such propositions are called *tautologies*.

Consider a language of propositions built up from basic values (*False*,*True*) and variables (*A, B,* · · · *, Z*) using negation (¬), conjunction (∧), implication (⇒), and parentheses. For example, the following are all propositions:

![image](images/image117_00.jpg)

The meaning of the logical operators can be defined using *truth tables*, which give the resulting value for each combination of argument values:

![image](images/image117_01.jpg)

For example, the truth table for conjunction states that *A* ∧ *B* returns *True* if both *A* and *B* are *True*, and *False* otherwise. (To save space in such tables, we abbreviate the basic values by *F* and *T*.) Using these definitions, the truth table for any proposition can then be constructed. In the case of our four example propositions, the resulting tables are as follows:

![image](images/image117_02.jpg)

These tables show that the second and fourth propositions are tautologies, because their result value is always *True*, while the first and third are not tautologies, because their result is *False* in at least one case.

The first step towards defining a function that decides if a proposition is a tautology is to declare a type for propositions, with one constructor for each of the five possible forms that a proposition can have:

![image](images/image118_00.jpg)

Note that an explicit constructor for parentheses is not required, as parentheses within Haskell itself can be used to indicate grouping. For example, the four propositions above can be represented as follows:

![image](images/image118_01.jpg)

In order to evaluate a proposition to a logical value, we need to know the value of each of its variables. For this purpose, we declare a *substitution* as a lookup table that associates variable names to logical values, using the *Assoc* type that was introduced at the start of this chapter:

![image](images/image120_05.jpg)

For example, the substitution [(’A’, *False*), (’B’, *True*)] assigns the variable *A* to *False*, and *B* to *True*. A function that evaluates a proposition given a substitution for its variables can now be defined by pattern matching on the five possible forms that the proposition can have:

![image](images/image118_02.jpg)

For example, the value of a constant proposition is simply the constant itself, the value of a variable is obtained by looking up its value in the substitution, and the value of a conjunction is given by taking the conjunction of the values of the two argument propositions. Note that logical implication ⇒ is implemented by the ≤ operator on logical values.

To decide if a proposition is a tautology, we will consider all possible substitutions for the variables that it contains. First of all, we define a function that returns the variables in a proposition:

![image](images/image119_00.jpg)

For example, *vars p2* = [’A’, ’B’, ’A’]. Note that this function does not remove duplicates, which will be done separately later on.

The key to generating substitutions is generating lists of logical values of a given length. To this end, we seek to define a function *bools* :: *Int* → [[*Bool*]] which, for example, will return all eight lists of three logical values:

![image](images/image119_01.jpg)

The order in which the lists are produced is not important. One way to achieve this behaviour is to observe that each list corresponds to a binary number, by interpreting *False* and *True* as the binary digits 0 and 1\. For example, the list [*True*, *False*, *True*] corresponds to the binary number 101. Given this interpretation, we can think of the function *bools* as simply counting in binary, starting from zero and proceeding upwards to the appropriate limit.

This idea leads to the following definition for *bools*, in terms of the function *int2bin* :: *Int* → [*Bit*] from [chapter 7](#14_chapter_title_7.html), which converts a non-negative integer into a binary number represented as a list of bits:

![image](images/image119_02.jpg)

There is, however, a simpler way to define *bools*, which can be revealed by thinking about the structure of the resulting lists. For example, we can observe that *bools* 3 contains two copies of *bools* 2, the first preceded by *False* in each case, and the second preceded by *True* in each case:

![image](images/image120_00.jpg)

This observation naturally leads to a recursive definition for *bools*. In the base case, *bools* 0, we return all lists of zero logical values, of which the empty list is the only one. In the recursive case, *bools* (*n* + 1), we take two copies of the lists produced by *bools n*, place *False* in front of each list in the first copy, *True* in front of each list in the second, and append the results:

![image](images/image120_01.jpg)

Using *bools*, it is now straightforward to define a function that generates all substitutions for a proposition by extracting its variables, removing duplicates from this list (using the function *rmdups* from [chapter 9](#16_chapter_title_9.html)), generating all possible lists of logical values for this many variables, and then zipping the list of variables with each of the resulting lists:

![image](images/image120_02.jpg)

For example:

![image](images/image120_03.jpg)

Finally, we define a function that decides if a proposition is a tautology, by checking if it evaluates to *True* for all possible substitutions:

![image](images/image120_04.jpg)

For example:

![image](images/image122_04.jpg)

![](images/line.jpg)

10.5 Abstract machine

As a second extended example, consider a type of simple arithmetic expressions built up from integers using an addition operator, together with a function that evaluates such an expression to an integer value:

![image](images/image121_00.jpg)

For example, the expression (2 + 3) + 4 is evaluated as follows:

![image](images/image121_01.jpg)

Note that the definition of the *value* function does not specify that the left argument of an addition should be evaluated before the right, or, more generally, what the next step of evaluation should be at any point. Rather, the order of evaluation is determined by Haskell. If desired, however, such control information can be made explicit by defining an *abstract machine* for expressions, which specifies the step-by-step process of their evaluation.

To this end, we first declare a type of *control stacks* for the abstract machine, which comprise a list of operations to be performed by the machine after the current evaluation has been completed:

![image](images/image121_02.jpg)

The meaning of the two operations will be explained shortly. We now define a function that evaluates an expression in the context of a control stack:

![image](images/image122_00.jpg)

That is, if the expression is an integer, it is already fully evaluated, and we begin executing the control stack. If the expression is an addition, we evaluate the first argument, *x*, placing the operation *EVAL y* on top of the control stack to indicate that the second argument, *y*, should be evaluated once that of the first argument is completed. In turn, we define the function that executes a control stack in the context of an integer argument:

![image](images/image122_01.jpg)

That is, if the stack is empty, we return the integer argument as the result of the execution. If the top of the stack is an operation *EVAL y*, we evaluate the expression *y*, placing the instruction *ADD n* on top of the remaining stack to indicate that the current integer argument, *n*, should be added together with the result of evaluating *y* once this is completed. And, finally, if the top of the stack is an operation *ADD n*, evaluation of the two arguments of an addition is now complete, and we execute the remaining control stack in the context of the sum of the two resulting integer values.

Finally, we define a function that evaluates an expression to an integer, by invoking *eval* with the given expression and the empty control stack:

![image](images/image122_02.jpg)

The fact that our abstract machine uses two mutually recursive functions, *eval* and *exec*, reflects the fact that it has two states, depending upon whether it is being driven by the structure of the expression or the control stack. To illustrate the machine, here is how it evaluates (2 + 3) + 4:

![image](images/image123_00.jpg)

Note how *eval* proceeds downwards to the leftmost integer in the expression, maintaining a trail of the pending right-hand expressions on the control stack. In turn, *exec* then proceeds upwards through the trail, transferring control back to *eval* and performing additions as appropriate.

![](images/line.jpg)

10.6 Class and instance declarations

We now turn our attention from types to classes. In Haskell, a new class can be declared using the **class** mechanism. For example, the class *Eq* of equality types is declared in the standard library as follows:

![image](images/image123_01.jpg)

This declaration states that for a type *a* to be an instance of the class *Eq*, it must support equality and inequality operators of the specified types. In fact, because a *default definition* has already been included for ≠, declaring an instance of this class only requires a definition for ==. For example, the type *Bool* can be made into an equality type as follows:

![image](images/image123_02.jpg)

For technical reasons, only types declared using the **data** mechanism can be made into instances of classes. Note also that default definitions can be overridden in instance declarations if desired. For example, for some equality types there may be a more efficient or appropriate way to decide if two values are different than simply checking if they are not equal.

Classes can also be extended to form new classes. For example, the class *Ord* of types whose values are totally ordered is declared in the standard library as an extension of the class *Eq* as follows:

![image](images/image124_00.jpg)

That is, for a type to be an instance of *Ord* it must be an instance of *Eq*, and support six additional operators. Because default definitions have already been included for *min* and *max*, declaring an equality type (such as *Bool*) as an ordered type only requires defining the four comparison operators:

![image](images/image124_01.jpg)

Derived instances

When new types are declared, it is usually appropriate to make them into instances of a number of built-in classes. Haskell provides a simple facility for automatically making new types into instances of the classes *Eq*, *Ord*, *Show*, and *Read*, in the form of the **deriving** mechanism. For example, the type *Bool* is actually declared in the standard library as follows:

![image](images/image124_02.jpg)

As a result, all the member functions from the four derived classes can then be used with logical values. For example:

![image](images/image126_03.jpg)

The use of :: in the last example is required to resolve the type of the result, which in this case cannot be inferred from the context. Note that for the purposes of deriving instances of the class *Ord* of ordered types, the ordering on the constructors of a type is determined by their position in its declaration. Hence, the above declaration for the type *Bool*, in which *False* appears before *True*, results in the ordering *False* *<* *True*.

In the case of constructors with arguments, the types of these arguments must also be instances of any derived classes. For example, recall the following declarations from earlier in this chapter:

![image](images/image125_00.jpg)

To derive *Shape* as an equality type requires that the type *Float* is also an equality type, which is indeed the case. Similarly, to derive *Maybe a* as an equality type requires that the type *a* is also such a type, which then becomes a class constraint on this parameter. In the same manner as lists and tuples, values built using constructors with arguments are ordered lexicographically. For example, if *Shape* is derived as an ordered type, then we have:

![image](images/image127_00.jpg)

Monadic types

We conclude this chapter by returning once again to parsers and interactive programs, the subjects of the previous two chapters. As the reader may recall, the functions *return* and >>= were defined for both parsers,

![image](images/image125_01.jpg)

and interactive programs:

![image](images/image125_02.jpg)

The use of the same function names and analagous types is not coincidental. In particular, generalising from the specific cases of *Parser* and *IO* to an arbitrary parameterised type gives the notion of a *monad*, which in Haskell is captured by the following class declaration:

![image](images/image125_03.jpg)

That is, a monad is a parameterised type *m* that supports *return* and >>= functions of the specified types. The fact that *m* must be a parameterised type, rather than just a type, is inferred from its use in the types for the two functions. Using this declaration, parsers and interactive programs can then be made into instances of the class of monadic types, by defining the two member functions in the appropriate manner:

![image](images/image126_00.jpg)

It is because of these declarations that the **do** notation can be used to sequence parsers and interactive programs. More generally, Haskell supports the use of this notation with any monadic type, allowing expressions of the form

![image](images/image126_01.jpg)

to be written as:

![image](images/image126_02.jpg)

![](images/line.jpg)

10.7 Chapter remarks

The abstract machine example is derived from (19), and the type of control stacks used in this example is a special case of the zipper data structure for traversing values of recursive types (12). The term *monad* comes from a branch of mathematics known as category theory (23). For further details on the theory and application of monads in functional programming, see (31; 24). As well as the basic mechanisms for declaring new types and classes introduced in this chapter, the Hugs system also supports a number of more advanced and experimental typing features; see *[www.haskell.org/hugs](http://www.haskell.org/hugs)*.

![](images/line.jpg)

10.8 Exercises

**1.**  Using recursion and the function *add*, define a multiplication function *mult* :: *Nat* → *Nat* → *Nat* for natural numbers.

**2.**  Although not included in appendix A, the standard library defines

![image](images/image128_01.jpg)

together with a function

![image](images/image128_02.jpg)

that decides if one value in an ordered type is less than (*LT*), equal to (*EQ*), or greater than (*GT*) another such value. Using this function, redefine the function *occurs* :: *Int* → *Tree* → *Bool* for search trees. Why is this new definition more efficient than the original version?

**3.**  Consider the following type of binary trees:

![image](images/image129_01.jpg)

Let us say that such a tree is *balanced* if the number of leaves in the left and right subtree of every node differs by at most one, with leaves themselves being trivially balanced. Define a function *balanced* :: *Tree* → *Bool* that decides if a tree is balanced or not. Hint: first define a function that returns the number of leaves in a tree.

**4.**  Define a function *balance* :: [*Int*] → *Tree* that converts a non-empty list of integers into a balanced tree. Hint: first define a function that splits a list into two halves whose length differs by at most one.

**5.**  Extend the tautology checker to support the use of logical disjunction (∨) and equivalence (⇔) in propositions.

**6.**  Using the function *isTaut* together with the parsing and interaction libraries from the previous two chapters, define an interactive tautology checker that allows propositions to be entered from the keyboard in a user-friendly syntax. Hint: build a parser for propositions by modifying the parser for arithmetic expressions given in [chapter 8](#15_chapter_title_8.html).

**7.**  Extend the abstract machine to support the use of multiplication.

**8.**  Complete the following instance declarations:

![image](images/image129_02.jpg)

In this context, [ ] denotes the list type [*a*] without its parameter. Hint: first write down the types of *return* and >>= for each instance.

chapter 11

**The countdown problem**

In this chapter we show how Haskell can be used to solve the countdown problem, a numbers game in which the aim is to construct numeric expressions satisfying certain constraints. We start by formalising the rules of the problem in Haskell, and then present a simple but inefficient program that solves the problem, whose efficiency is then improved in two stages.

![](images/line.jpg)

11.1 Introduction

Countdown is a popular quiz programme that has been running on British television since 1982, and includes a numbers game that we shall refer to as the *countdown problem*. The essence of the problem is as follows:

Given a sequence of numbers and a target number, attempt to construct an expression whose value is the target, by combining one or more numbers from the sequence using addition, subtraction, multiplication, division and parentheses.

Each number in the sequence can only be used at most once in the expression, and all of the numbers involved, including intermediate values, must be positive natural numbers (1, 2, 3*, . . .*). In particular, the use of negative numbers, zero, and proper fractions such as 2 ÷ 3, is not permitted.

For example, suppose that we are given the sequence 1, 3, 7, 10, 25, 50, and the target 765\. Then one possible solution is given by the expression (1 + 50) * (25 − 10), as shown by the following simple calculation:

![image](images/image128_00.jpg)

In fact, for this example it can be shown that there are 780 different solutions. On the other hand, keeping the same sequence but changing the target to 831 gives an example that can be shown to have no solutions.

In the television version of the countdown problem, a number of additional rules are adopted to make the problem suitable for human players on a quiz programme. In particular, there are always six numbers selected from the sequence 1 *. . .* 10, 1 *. . .* 10, 25, 50, 75, 100, the target is always in the range 100 *. . .* 999, and there is a time limit of 30 seconds. It is natural to abstract from such constraints when developing a computer player, so none of the programs that we develop in this chapter enforces or depends upon these extra rules. Note, however, that we do not abstract from the positive naturals to a richer numeric domain such as the integers or rationals, as this would fundamentally change the computational complexity of the problem.

![](images/line.jpg)

11.2 Formalising the problem

We start by defining a type for the four numeric operators:

![image](images/image131_03.jpg)

Using this type, we define a function *valid* that decides if the application of an operator to two positive naturals gives another positive natural, and a function *apply* that actually performs such a valid application:

![image](images/image129_00.jpg)

For example, the application *Sub* 2 3 is invalid because 2 − 3 is negative, while *Div* 2 3 is invalid because 2 ÷ 3 is rational. In turn, we define a type for numeric expressions, which can either be an integer value or the application of an operator to two argument expressions:

![image](images/image131_04.jpg)

Using this type, we define a function that returns the list of *values* in an expression, and a function *eval* that returns the overall value of an expression, provided that this value is a positive natural number:

![image](images/image130_00.jpg)

Note that the possibility of failure within *eval* is handled by returning a list of results, with the convention that a singleton list denotes success, and the empty list denotes failure. For example, for 2 + 3 and 2 − 3, we have:

![image](images/image132_03.jpg)

Failure within *eval* could also be handled by using the *Maybe* type, but we prefer to use the list type in this case because the comprehension notation then provides a convenient way to define the *eval* function.

We now define a number of useful combinatorial functions that return all possible lists satisfying certain properties. The function *subs* returns all subsequences of a list, which are given by all possible combinations of excluding or including each element, *interleave* returns all possible ways of inserting a new element into a list, and *perms* returns all permutations of a list, which are given by all possible reorderings of the elements:

![image](images/image130_01.jpg)

For example:

![image](images/image132_04.jpg)

In turn, a function that returns all *choices* from a list, which are given by all possible ways of selecting zero or more elements in any order, can then be defined simply by considering all permutations of all subsequences:

![image](images/image131_00.jpg)

For example:

![image](images/image133_03.jpg)

Finally, we can now define a function *solution* that formalises what it means to solve an instance of the countdown problem:

![image](images/image131_01.jpg)

That is, an expression is a solution for a given list of numbers and a target if the list of values in the expression is chosen from the list of numbers, and the expression successfully evaluates to give the target. For example, if *e* :: *Expr* represents the expression (1 + 50) * (25 − 10), then we have:

![image](images/image133_04.jpg)

The efficiency of *solution* could be improved by using a function *isChoice* that decides directly if one list is chosen from another, rather than doing so indirectly using the function *choices* that returns all possible choices from a list. However, efficiency is not important at this stage, and *choices* itself is used to define a number of other functions in this chapter.

![](images/line.jpg)

11.3 Brute force solution

Our first approach to solving the countdown problem is by brute force, using the idea of generating all possible expressions over the given list of numbers. We start by defining a function *split* that returns all possible ways of splitting a list into two non-empty lists that append to give the original list:

![image](images/image131_02.jpg)

For example:

![image](images/image133_05.jpg)

Using *split* we can then define the key function, *exprs*, which returns all possible expressions whose list of values is precisely a given list:

![image](images/image132_00.jpg)

That is, for the empty list of numbers there are no possible expressions, while for a single number there is a single expression comprising that number. Otherwise, for a list of two or more numbers we first produce all splittings of the list, then recursively calculate all possible expressions for each of these lists, and, finally, combine each pair of expressions using each of the four numeric operators, using an auxiliary function defined as follows:

![image](images/image132_01.jpg)

Finally, we can now define a function *solutions* that returns all possible expressions that solve an instance of the countdown problem, by first generating all expressions over each choice from the given list of numbers, and then selecting those expressions that successfully evaluate to give the target:

![image](images/image132_02.jpg)

For the purposes of testing our programs in this chapter, the performance of Hugs is somewhat limited, so instead we use the Glasgow Haskell Compiler. For example, using GHC version 6.4.1 on a 1.2GHz Pentium M laptop, *solutions* [1, 3, 7, 10, 25, 50] 765 returns the first solution in 0.36 seconds, and all 780 solutions in 43.98 seconds, while if the target is changed to 831, then the empty list of solutions is returned in 44.42 seconds.

![](images/line.jpg)

11.4 Combining generation and evaluation

The function *solutions* generates all possible expressions over the given numbers, but in practice many of these expressions will fail to evaluate, due to the fact that subtraction and division are not always valid for positive naturals. For example, it can be shown that there are 33, 665, 406 possible expressions over the numbers 1, 3, 7, 10, 25, 50, but only 4, 672, 540 of these expressions evaluate successfully, which is just under 14%.

Based upon this observation, our second approach to solving the countdown problem is to improve our brute force program by combining the generation of expressions with their evaluation, such that both tasks are performed simultaneously. In this way, expressions that fail to evaluate are rejected at an earlier stage, and, more importantly, are not used to generate further such expressions. We start by declaring a type *Result* of expressions that evaluate successfully paired with their overall values:

![image](images/image135_00.jpg)

Using this type, we then define a function *results* that returns all possible results comprising expressions whose list of values is precisely a given list:

![image](images/image133_00.jpg)

That is, for the empty list there are no possible results, while for a single number there is a single result formed from that number, provided that the number itself is a positive natural. Otherwise, for two or more numbers we first produce all splittings of the list, then recursively calculate all possible results for each of these lists, and, finally, combine each pair of results using each of the four numeric operators that are valid:

![image](images/image133_01.jpg)

Using *results* we can now define a new function *solutions*′ that returns all possible expressions that solve an instance of the countdown problem, by first generating all results over each choice from the given numbers, and then selecting those expressions whose value is the target:

![image](images/image133_02.jpg)

In terms of performance, *solutions*′ [1, 3, 7, 10, 25, 50] 765 returns the first solution in 0.04 seconds (9 times faster than *solutions*) and all solutions in 3.47 seconds (12 times faster), while if the target is changed to 831, the empty list is returned in 3.28 seconds (13 times faster).

![](images/line.jpg)

11.5 Exploiting algebraic properties

The function *solutions*′ generates all possible expressions over the given numbers whose evaluation is successful, but in practice many of these expressions will be essentially the same, due to the fact that the numeric operators have algebraic properties. For example, the expressions 2 + 3 and 3 + 2 are essentially the same because the result of an addition does not depend upon the order of the two arguments, while 2 ÷ 1 and 2 are essentially the same because dividing any number by one has no effect on that number.

Based upon this observation, our final approach to solving the countdown problem is to improve our second program by exploiting such properties to reduce the number of generated expressions. In particular, we exploit the following five commutativity and identity properties:

![image](images/image134_00.jpg)

We start by recalling the function *valid* that decides if the application of an operator to two positive naturals gives another such:

![image](images/image134_01.jpg)

This definition can be modified to exploit the commutativity of addition and multiplication simply by requiring that their arguments are in numeric order (*x* ≤ *y*), and the identity properties of multiplication and division simply by requiring that the appropriate arguments are non-unitary (≠ 1):

![image](images/image134_02.jpg)

For example, using this new definition, *Add* 3 2 is now invalid because it is essentially the same as *Add* 2 3 using the commutativity of addition, while *Div* 2 1 is now invalid because it is essentially the same as the number 2 on its own using the identity property for division.

Using the new version of *valid* gives a new version of our function *solutions*′ that solves the countdown problem, which we write as *solutions*″. Using this new function can considerably reduce the number of generated expressions and the number of solutions. For example, *solutions*″ [1, 3, 7, 10, 25, 50] 765 only generates 245, 644 expressions, of which just 49 are solutions, which is just over 5% and 6% respectively of the numbers using *solutions*′.

As regards performance, *solutions*″ [1, 3, 7, 10, 25, 50] 765 now returns the first solution in 0.02 seconds (twice as fast as *solutions*′) and all solutions in 0.44 seconds (7 times faster), while for the target number 831 the empty list is also returned in 0.44 seconds (7 times faster). More generally, given any numbers from the television version of the countdown problem, our final program *solutions*″ typically returns all solutions in under one second.

![](images/line.jpg)

11.6 Chapter remarks

Countdown is based upon an original version on French television called “Des Chiffres et des Lettres”, while the countdown problem itself is related to the childrens arithmetic games called “krypto” and “four fours”. This chapter is based upon (15), which also includes proofs of correctness of the three programs produced. A number of more advanced approaches to solving the countdown problem are explored by Bird and Mu (2). The definitions for the functions *subs*, *interleave*, and *perms* are due to Bird and Wadler (3).

![](images/line.jpg)

11.7 Exercises

**1.**  Redefine the combinatorial function *choices* using a list comprehension rather than the library functions *concat* and *map*.

**2.**  Define a recursive function *isChoice* :: *Eq a* ⇒ [*a*] → [*a*] → *Bool* that decides if one list is chosen from another, without using the combinatorial functions *perms* and *subs*. Hint: start by defining a function that removes the first occurrence of a value from a list.

**3.**  What effect would generalising the function *split* to also return pairs containing the empty list have on the behaviour of *solutions*?

**4.**  Using *choices*, *exprs*, and *eval*, verify that there are 33, 665, 406 possible expressions over the numbers 1, 3, 7, 10, 25, 50, and that only 4, 672, 540 of these expressions evaluate successfully.

**5.**  Similarly, verify that the number of expressions that evaluate successfully increases to 10, 839, 369 if the numeric domain is generalised to arbitrary integers. Hint: modify the definition of *valid*.

**6.**  Modify the final program to:

**(a)**  allow the use of exponentiation in expressions;

**(b)**  produce the nearest solutions if no exact solution is possible;

**(c)**  order the solutions using a suitable measure of simplicity.

chapter 12

**Lazy evaluation**

In this chapter we introduce lazy evaluation, the mechanism used to evaluate expressions in Haskell. We start by reviewing the notion of evaluation, then consider evaluation strategies and their properties, discuss infinite structures and modular programming, and conclude with a special form of function application that can improve the space performance of programs.

![](images/line.jpg)

12.1 Introduction

As we have seen throughout this book, the basic method of computation in Haskell is the application of functions to arguments. For example, suppose that we define a function that increments an integer:

![image](images/image136_00.jpg)

Then the expression *inc* (2 * 3) can be evaluated as follows:

![image](images/image136_01.jpg)

Alternatively, the same result can also be obtained by performing the first two function applications in the opposite order:

![image](images/image136_02.jpg)

The fact that changing the order in which functions are applied does not affect the final result is not specific to such simple examples, but is an important general property of function application in Haskell. More formally, in Haskell any two different ways of evaluating the same expression will always produce the same final value, provided that they both terminate. We will return to the issue of termination later on in this chapter.

Note that the above property does not hold for most imperative programming languages, in which the basic method of computation is changing stored values. For example, consider the imperative expression *n* + (*n* := 1) that adds the current value of the variable *n* to the result of changing its value to one, assuming that *n* initially has the value zero. This expression can be evaluated by first performing the left-hand side of the addition

![image](images/image137_00.jpg)

or alternatively, by first performing the right-hand side:

![image](images/image137_01.jpg)

The final value is different in each case. The general problem illustrated by this example is that the precise time at which an assignment is performed in an imperative language may affect the value that results from a computation. In contrast, the time at which a function is applied to an argument in Haskell never affects the value that results from a computation. Nonetheless, as we shall see in the remainder of this chapter, there are important practical issues concerning the order and nature of evaluation.

![](images/line.jpg)

12.2 Evaluation strategies

An expression that has the form of a function applied to one or more arguments that can be “reduced” by performing the application is called a reducible expression, or *redex* for short. As indicated by the use of quotations marks in the preceding sentence, such reductions do not necessarily decrease the size of an expression, although in practice this is often the case.

By way of example, suppose that we define a function *mult* that takes a pair of integers and returns their product:

![image](images/image138_00.jpg)

Now consider the expression *mult* (1 + 2, 2 + 3). This expression contains three redexes, namely the sub-expressions 1 + 2 and 2 + 3, which have the form of the function + applied to two arguments, and the entire expression *mult* (1 + 2, 2 + 3) itself, which has the form of the function *mult* applied to a pair of arguments. Performing the corresponding reductions gives the expressions *mult* (3, 2 + 3), *mult* (1 + 2, 5), and (1 + 2) * (2 + 3).

When evaluating an expression, in what order should reductions be performed? One common strategy, called *innermost* evaluation, is to always choose a redex that is innermost, in the sense that it contains no other redex. If there is more than one innermost redex, by convention we choose that which begins at the leftmost position in the expression.

For example, both 1 + 2 and 2 + 3 contain no other redexes and are hence innermost within the expression *mult* (1 + 2, 2 + 3), with the redex 1 + 2 beginning at the leftmost position. More generally, our example expression is evaluated using innermost evaluation as follows:

![image](images/image138_01.jpg)

Innermost evaluation can also be characterised in terms of how arguments are passed to functions. In particular, using this strategy ensures that the argument of a function is always fully evaluated before the function itself is applied. That is, arguments are passed *by value*. For example, as shown above, evaluating *mult* (1 + 2, 2 + 3) using innermost evaluation proceeds by first evaluating the argument expressions 1 + 2 and 2 + 3, and then applying the function *mult*. The fact that we always choose the leftmost innermost redex ensures that the first argument is evaluated before the second.

Another common strategy for evaluating an expression, dual to innermost evaluation, is to always choose a redex that is outermost, in the sense that it is contained in no other redex. If there is more than one such redex then as previously we choose that which begins at the leftmost position. Not surprisingly, this evaluation strategy is called *outermost* evaluation.

For example, the expression *mult* (1 + 2, 2 + 3) is contained in no other redex and is hence outermost within itself. More generally, evaluating this expression using outermost evaluation proceeds as follows:

![image](images/image138_02.jpg)

In terms of how arguments are passed to functions, using outermost evaluation allows functions to be applied before their arguments are evaluated. For this reason, we say that arguments are passed *by name*. For example, as shown above, evaluating *mult* (1 + 2, 2 + 3) using outermost evaluation proceeds by first applying the function *mult* to the two unevaluated arguments 1 + 2 and 2 + 3, and then evaluating these two expressions in turn.

Note, however, that many built-in functions require their arguments to be evaluated before being applied, even when using outermost evaluation. For example, as illustrated in the calculation above, built-in arithmetic operators such as * and + cannot be applied until their two arguments have been evaluated to numbers. Functions with this property are called strict, and will be discussed in further detail at the end of this chapter.

Lambda expressions

Let us now define a curried version of *mult* that takes its arguments one at a time, using a lambda expression to make the use of currying explicit:

![image](images/image139_01.jpg)

Then using innermost evaluation, for example, we have:

![image](images/image139_02.jpg)

That is, the two arguments are now substituted into the body of the function *mult* one at a time, as we would expect using currying, rather than at the same time as in the previous section. This behaviour arises because *mult* 3 is the leftmost innermost redex in the expression *mult* 3 (2 + 3), as opposed to 2 + 3 in the expression *mult* (3, 2 + 3). Performing a reduction on *mult* 3 in the second step of the calculation above gives the lambda expression (*λy* → 3 * *y*), which awaits the result of evaluating the second argument.

Note that in Haskell, the selection of redexes within lambda expressions is prohibited. The rational for not “reducing under lambdas” is that functions are viewed as black boxes that we are not permitted to look inside. More formally, the only operation that can be performed on a function is that of applying it to an argument. As such, reduction within the body of a function is only permitted once the function has been applied. For example, the lambda expression *λx* → 1 + 2 is deemed to be fully evaluated, even though its body contains the redex 1 + 2, but once this function has been applied to an argument, evaluation of this redex can then proceed:

![image](images/image140_00.jpg)

Using innermost and outermost evaluation, but not under lambdas, is normally referred to as *call-by-value* and *call-by-name* evaluation, respectively. In the next two sections we explore how these two evaluation strategies compare in terms of two important properties, namely their termination behaviour and the number of reduction steps that they require.

![](images/line.jpg)

12.3 Termination

Consider the following recursive definition:

![image](images/image140_01.jpg)

That is, the integer *inf* (abbreviating “infinity”) is defined as the successor of itself. Evaluating *inf* produces a larger and larger expression, regardless of the evaluation strategy, and hence does not terminate:

![image](images/image140_02.jpg)

In practice, evaluating *inf* using Hugs will quickly exhaust the available memory and produce an error message. Now consider the expression *fst* (0, *inf*), where *fst* is the library function that selects the first component of a pair, defined by *fst* (*x*, *y*) = *x*. Using call-by-value evaluation with this expression also results in non-termination in a similar manner:

![image](images/image140_03.jpg)

In contrast, using call-by-name evaluation results in termination in just one step, by immediately applying the definition of *fst* and hence avoiding the evaluation of the non-terminating expression *inf* :

![image](images/image141_01.jpg)

This simple example shows that call-by-name evaluation may produce a result when call-by-value evaluation fails to terminate. More generally, we have the following important property: if there exists any evaluation sequence that terminates for a given expression, then call-by-name evaluation will also terminate for this expression, and produce the same final result.

In summary, call-by-name evaluation is preferable to call-by-value for the purpose of ensuring that evaluation terminates as often as possible.

![](images/line.jpg)

12.4 Number of reductions

Now consider the following definition:

![image](images/image141_02.jpg)

For example, using call-by-value evaluation, we have:

![image](images/image141_03.jpg)

In contrast, using call-by-name evaluation with the same expression requires one extra reduction step, due to the fact that 1 + 2 is duplicated when the function *square* is applied, and hence must be evaluated twice:

![image](images/image141_04.jpg)

This example shows that call-by-name evaluation may require more steps than call-by-value evaluation, in particular when an argument is used more than once in the body of a function. More generally, we have the following property: arguments are evaluated precisely once using call-by-value evaluation, but may be evaluated many times using call-by-name.

Fortunately, the above efficiency problem with call-by-name evaluation can easily be solved, by using pointers to indicate sharing of expressions during evaluation. Rather than physically copying an argument if it is used many times in the body of a function, we simply keep one copy of the argument and make many pointers to it. In this manner, any reductions that are performed on the argument are automatically shared between each of the pointers to that argument. For example, using this strategy we have:

![image](images/image142_01.jpg)

That is, when applying the definition *square n* = *n* * *n* in the first step, we keep a single copy of the argument expression 1 + 2, and make two pointers to it. In this manner, when the expression 1 + 2 is reduced in the second step, both pointers in the expression share the result.

The use of call-by-name evaluation in conjunction with sharing is called *lazy evaluation*. This is the evaluation strategy that is used in Haskell, as a result of which Haskell is called a lazy programming language. Being based upon call-by-name evaluation, lazy evaluation has the property that it ensures that evaluation terminates as often as possible. Moreover, using sharing ensures that lazy evaluation never requires more steps than call-by-value evaluation. The use of the term “lazy” will be explained shortly.

![](images/line.jpg)

12.5 Infinite structures

An additional property of call-by-name evaluation, and hence lazy evaluation, is that it allows what at first sight may seem impossible: programming with infinite structures. We have already seen a simple example of this idea earlier in this chapter, in the form of the evaluation of *fst* (0, *inf*) avoiding the production of the infinite structure 1 + (1 + (1 + · · ·)) defined by *inf*.

More interesting forms of behaviour occur when we consider infinite lists. For example, consider the following recursive definition:

![image](images/image143_00.jpg)

That is, the list *ones* is defined as a single one followed by itself. As with *inf*, evaluating *ones* does not terminate, regardless of the strategy used:

![image](images/image143_01.jpg)

In practice, evaluating *ones* using Hugs will produce a never-ending list of ones, until the user eventually decides to terminate this process:

![image](images/image145_02.jpg)

Now consider the expression *head ones*, which attempts to select the first element of this infinite list of ones. Using call-by-value evaluation with this expression also results in non-termination:

![image](images/image143_02.jpg)

In contrast, using lazy evaluation (or call-by-name evaluation, as sharing is not required in this example) results in termination in two steps:

![image](images/image143_03.jpg)

This behaviour arises because lazy evaluation proceeds in a lazy manner as its name suggests, only evaluating arguments as and when strictly necessary to produce results. For example, when selecting the first element of a list, the remainder of the list is not required, and hence in *head* (1 : *ones*) the further evaluation of the infinite list *ones* is avoided. More generally, we have the following property: using lazy evaluation, expressions are only evaluated as much as required by the context in which they are used.

Using this idea, we now see that under lazy evaluation *ones* is not an infinite list as such, but rather a potentially infinite list, which is only evaluated as much as required by the context. This idea is not restricted to lists, but applies equally to any form of data structure in Haskell. For example, the last exercise for this chapter involves potentially infinite trees.

![](images/line.jpg)

12.6 Modular programming

Lazy evaluation also allows us to separate control from data in our computations. For example, a list of three ones can be produced by selecting the first three elements (control) of the infinite list of ones (data):

![image](images/image146_01.jpg)

Using the definition of *take* from the standard prelude

![image](images/image144_00.jpg)

this behaviour arises using lazy evaluation as follows:

![image](images/image144_01.jpg)

That is, the data is only evaluated as much as required by the control, and these two parts take it in turn to perform reductions. Without lazy evaluation, the control and data parts would need to be combined in the form of a single function that produces a list of *n* identical elements, such as:

![image](images/image145_00.jpg)

Being able to modularise programs by separating them into logically distinct parts is an important goal in programming, and being able to separate control from data is one of the most important benefits of lazy evaluation.

Note that care is still required when programming with infinite lists, to avoid non-termination. For example, the expression

![image](images/image147_04.jpg)

(where [*n* . .] produces the infinite list of integers beginning with *n*) will produce the integers 1, 2, 3, 4, 5 and then loop forever, because the function *filter* (≤ 5) keeps testing elements of the infinite list in a vain attempt to find another that is less than or equal to five. In contrast, the expression

![image](images/image147_05.jpg)

will produce the same integers and then terminate, because *takeWhile* (≤ 5) stops as soon as it finds an element of the list that is greater than five.

We conclude this section with an example concerning prime numbers. In [chapter 5](#12_chapter_title_5.html) we wrote a function to generate prime numbers up to a given limit. Here is a simple procedure for generating the infinite sequence of all prime numbers, as opposed to some finite prefix of this sequence:

•  write down the infinite sequence 2, 3, 4, 5, 6, · · ·;

•  mark the first number, *p*, in the sequence as prime;

•  delete all multiples of *p* from the sequence;

•  return to the second step.

Note that the first and third steps require an infinite amount of work, and hence in practice the steps must be interleaved. The first few iterations of this procedure can be illustrated as follows:

![image](images/image145_01.jpg)

Each row corresponds to one iteration, with the first row being the initial sequence (step one), the first number in each row being written in bold to indicate its primality (step two), and all multiples of this number being underlined to indicate their deletion (step three) prior to the next iteration. In this manner, we can imagine the initial sequence of numbers falling downwards, with certain numbers being sieved out at each stage by the underlining, and the bold numbers forming the infinite sequence of primes:

![image](images/image148_03.jpg)

The above procedure for generating prime numbers is known as the *sieve of Eratosthenes*, after the Greek mathematician who first described it. This procedure can be translated directly into Haskell:

![image](images/image146_00.jpg)

That is, starting with the infinite list [2 *. .*] (step one), we apply the function *sieve* that retains the first number *p* as being prime (step two), and then calls itself recursively with a new list obtained by filtering all multiples of *p* from this list (steps three and four). Lazy evaluation ensures that this program does indeed produce the infinite list of all prime numbers:

![image](images/image148_04.jpg)

By freeing the generation of prime numbers from the constraint of finiteness, we have obtained a modular program on which different control parts can be used in different situations. For example, the first ten prime numbers, and the prime numbers less than ten, can be produced as follows:

![image](images/image148_05.jpg)

![](images/line.jpg)

12.7 Strict application

Haskell uses lazy evaluation by default, but also provides a special *strict* version of function application, written as $!, which can sometimes be useful. Informally, an expression of the form *f* $! *x* behaves in the same way as the normal application *f x*, except that the top-level of evaluation of the argument expression *x* is forced before the function *f* is applied.

For example, if the argument has a basic type, such as *Int* or *Bool*, then top-level evaluation is simply complete evaluation. On the other hand, for a pair type such as (*Int*, *Bool*), evaluation is performed until a pair of expressions is obtained, but no further. Similarly, for a list type, evaluation is performed until the empty list or the cons of two expressions is obtained.

More formally, an expression of the form *f* $! *x* is only a redex once evaluation of the argument *x*, using lazy evaluation as normal, has reached the point where it is known that the result is not an undefined value, at which point the expression can be reduced to the normal application *f x*. For example, using the definition *square n* = *n* * *n*, evaluation of *square* $! (1 + 2) proceeds in a call-by-value manner, by first evaluating the argument expression 1 + 2 to give the value 3, and then applying the function *square*:

![image](images/image147_00.jpg)

When used with a curried function with multiple arguments, strict application can be used to force top-level evaluation of any combination of arguments. For example, if *f* is a curried function with two arguments, an application of the form *f x y* can be modified to have three different behaviours:

![image](images/image147_01.jpg)

In Haskell, strict application is mainly used to improve the space performance of programs. For example, consider a function *sumwith* that calculates the sum of a list of integers using an accumulator value:

![image](images/image147_02.jpg)

Then using lazy evaluation, we have:

![image](images/image147_03.jpg)

Note that the entire summation ((0 + 1) + 2) + 3 is constructed before any additions are actually performed. More generally, *sumwith* will construct a summation whose size is proportional to the number of integers in the original list. For example, evaluating *sumwith* 0 [1 *. .* 10000] using Hugs will quickly exhaust the available memory and produce an error message. In practice, it would be preferable to perform each addition as soon as it is introduced, in order to avoid running out of memory in this way.

This behaviour can be achieved by redefining *sumwith* using strict application, to force evaluation of its accumulator value:

![image](images/image148_00.jpg)

For example, we now have:

![image](images/image148_01.jpg)

This evaluation requires more steps than previously, due to the additional overhead of using strict application, but now performs each addition as soon as it is introduced, rather than constructing a large summation. For example, evaluating *sumwith* 0 [1 *. .* 10000] using Hugs now gives the correct result, as opposed to producing an error as previously.

Generalising from the above example, one may wish to define a strict version of the higher-order library function *foldl* that forces evaluation of its accumulator prior to processing the tail of the list:

![image](images/image148_02.jpg)

For example, we can now define *sumwith* = *foldl*′ (+). It is important to note, however, that strict application is not a silver bullet that automatically improves the space behaviour of Haskell programs. Even for relatively simple examples, the use of strict application is a specialist topic that requires careful consideration of the behaviour of lazy evaluation.

![](images/line.jpg)

12.8 Chapter remarks

Further details about evaluation orders and their properties can be found in (28), and further examples of the use of lazy evaluation for modular programming in the classic *Why Functional Programming Matters* (13). A formal meaning for lazy evaluation is given in (21), and a comprehensive tutorial on the efficient implementation of lazy evaluation in (26).

![](images/line.jpg)

12.9 Exercises

**1.**  Identify the redexes in the following expressions, and determine whether each redex is innermost, outermost, neither, or both:

![image](images/image149_00.jpg)

**2.**  Show why outermost evaluation is preferable to innermost for the purposes of evaluating the expression *fst* (1 + 2, 2 + 3).

**3.**  Given the definition *mult* = *λx* *λy* → *x* * *y*), show how the evaluation of *mult* 3 4 can be broken down into four separate steps.

**4.**  Using a list comprehension, define an expression *fibs* :: [*Integer*] that generates the infinite sequence of Fibonacci numbers

![image](images/image151_02.jpg)

using the following simple procedure:

**–**  the first two numbers are 0 and 1;

**–**  the next is the sum of the previous two;

**–**  return to the second step.

Hint: make use of the library functions *zip* and *tail*. Note that numbers in the Fibonacci sequence quickly become large, hence the use of the type *Integer* of arbitrary-precision integers above.

**5.**  Using *fibs*, define a function *fib* :: *Int* → *Integer* that returns the *n*th Fibonnaci number (counting from zero), and an expression that calculates the first Fibonacci number greater than one thousand.

**6.**  Define appropriate versions of the library functions

![image](images/image150_00.jpg)

for the following type of binary trees:

![image](images/image152_02.jpg)

chapter 13

**Reasoning about programs**

In this final chapter we introduce the idea of reasoning about Haskell programs. We start by reviewing the notion of equational reasoning, then consider how it can be applied in Haskell, introduce the important technique of induction, show how induction can be used to eliminate uses of the append operator, and conclude by proving the correctness of a simple compiler.

![](images/line.jpg)

13.1 Equational reasoning

At school we learn basic algebraic properties of numbers, such as the fact that multiplication is commutative, addition is associative, and multiplication distributes over addition on both the left- and right-hand sides:

![image](images/image151_00.jpg)

For example, using these properties we can show that a product of the form (*x* + *a*) (*x* + *b*) can be expanded to a summation *x*² + (*a* + *b*) *x* + *a b*:

![image](images/image151_01.jpg)

Note that in this calculation we follow the common practice of implicitly exploiting associativity properties, in this case the associativity of addition by omitting parentheses when more than one addition is used in sequence.

As well as being interesting in their their own right, algebraic properties can also have a computational significance. For example, the expression *x* (*y* + *z*) requires two operations (one multiplication and one addition), whereas the equivalent expression *x y* + *x z* requires three (two multiplications and one addition). Hence even though these two expressions are algebraically equal, in terms of efficiency the former is preferable to the latter.

![](images/line.jpg)

13.2 Reasoning about Haskell

The same style of equational reasoning can also be used in Haskell. For example, in this context the equation *x* * *y* = *y* * *x* means that for any expressions *x* and *y* of the same numeric types, evaluation of *x* * *y* and *y* * *x* will always produce the same numeric value. Note that the equality operator == provided within Haskell itself is not used when stating such properties, as in *x* * *y* == *y* * *x*, because we are aiming to use mathematics as a language to reason about Haskell, rather than using Haskell as a language to reason about itself, which would be somewhat circular.

When reasoning about Haskell, we do not just use properties of built-in operations of the language such as addition and multiplication, but also use the equations from which user-defined functions are constructed. For example, consider the following function that doubles an integer:

![image](images/image152_00.jpg)

As well as being viewed as the definition of a function, this equation can also be viewed as a property that can be used when reasoning about this function. In particular, as a logical property the above equation states that for any integer expression *x*, the expression *double x* can freely be replaced by *x* + *x*, and, conversely, that the expression *x* + *x* can freely be replaced by *double x*. In this manner, when reasoning about programs, function definitions can be both applied from left-to-right and unapplied from right-to-left.

However, some care is required when reasoning about functions that are defined using multiple equations. For example, consider a function that decides if an integer is zero, defined using two equations:

![image](images/image152_01.jpg)

The first equation, *isZero* 0 = *True*, can freely be viewed as a logical property that can be applied in both directions. However, this is not the case for the second equation, *isZero n* = *False*. In particular, because the order in which the equations are written is significant, an expression of the form *isZero n* can only be replaced by *False* provided that *n* ≠ 0, as in the case when *n* = 0 the first equation applies. Dually, it is only valid to unapply the equation *isZero n* = *False* and replace *False* by an expression of the form *isZero n* in the case when *n* ≠ 0, for the same reason.

More generally, when a function is defined using multiple equations, the equations cannot be viewed as logical properties in isolation from one another, but need to be interpreted in light of the order in which patterns are matched within the equations. For this reason, it is preferable to define functions in a manner that does not rely on the order in which their equations are written. For example, if we rewrite the above definition using a guard

![image](images/image153_00.jpg)

then it is now explicitly clear that *isZero n* can only be replaced by *False*, and conversely that *False* can only be replaced by *isZero n*, when the guard *n* ≠ 0 is satisfied. Patterns that do not rely on the order in which they are matched are called *disjoint* or *non-overlapping*. In order to simplify the process of reasoning about programs, it is good practice to use non-overlapping patterns whenever possible. For example, most of the functions in the standard library given in appendix A are defined in this manner.

![](images/line.jpg)

13.3 Simple examples

As a simple example of equational reasoning in Haskell, recall the following definition of the library function that reverses a list:

![image](images/image153_01.jpg)

Using this definition, we can show that *reverse* has no effect on singleton lists, in the sense that *reverse* [*x*] = [*x*] for any element *x* :

![image](images/image153_02.jpg)

Hence any expression of the form *reverse* [*x*] in a program can freely be replaced by [*x*] without change in meaning, but with a change in efficiency by avoiding the need to apply the *reverse* function.

Equational reasoning is often combined with some form of case analysis. For example, consider the logical negation function:

![image](images/image153_03.jpg)

Because this function is defined by pattern matching, properties of ¬ are normally proved by case analysis on its argument. For example, the fact that ¬ is its own inverse, ¬ (¬ *b*) = *b* for all logical values *b*, can be shown by case analysis on the two possible values for *b*. For example, the case when *b* = *False* is verified below, and *b* = *True* follows similarly:

![image](images/image154_00.jpg)

![](images/line.jpg)

13.4 Induction on numbers

Most interesting functional programs involve some form of recursion. Reasoning about such programs normally proceeds using the simple but powerful technique of *induction*. Let us begin by recalling the simplest example of a recursive type, namely the type of natural numbers:

![image](images/image156_03.jpg)

This declaration states that *Zero* is a value of type *Nat* (the base case), and that if *n* is a value of type *Nat*, then so is *Succ n* (the recursive case). Implicit in the declaration is the fact that *Zero* and *Succ* are the only constructors for the type *Nat*. Hence, the values of *Nat* can be enumerated as follows:

![image](images/image154_01.jpg)

For simplicity, we only consider the finite natural numbers, obtained by starting with *Zero* and applying *Succ* a finite number of times. In particular, we do not consider infinity, defined by *inf* = *Succ inf*. A similar comment applies to all the other recursive types that we consider in this chapter.

Now suppose we want to prove that some property, *p* say, holds for all (finite) natural numbers. Then the principle of induction states that it is sufficient to show that *p* holds for *Zero*, called the *base case*, and that *p* is preserved by *Succ*, called the *inductive case*. More precisely, in the inductive case one is required to show that if the property *p* holds for any natural number *n*, called the *induction hypothesis*, then it also holds for *Succ n*.

Why is induction sufficient to show that *p* holds for all natural numbers? For example, how does it then follow that *p* holds for *Succ* (*Succ Zero*). Starting from the base case that *p* holds for *Zero*, we can apply the inductive case once to conclude that *p* holds for *Succ Zero*, by taking *n* = *Zero*, and then apply the inductive case a second time to conclude that *p* holds for *Succ* (*Succ Zero*), by taking *n* = *Succ Zero*. In a similar manner, it can be established that *p* holds for any natural number.

It is useful to draw an analogy with the “domino effect”. Suppose there is a line of dominoes standing on end and you know that the first domino will fall, and that whenever a domino falls then its next neighbour will also fall. Then it is clear that all the dominoes will fall, by applying the first fact to get the process started, and repeatedly applying the second to keep it going. The same pattern of reasoning occurs with induction: we first verify the required property for *Zero* (the first domino falls), then that the property is preserved by *Succ* (if any domino falls, then so will its neighbour), and conclude that the property holds for all natural numbers (all dominoes fall).

As a concrete example, consider the definition of a recursive function that takes two natural numbers and adds them together:

![image](images/image155_00.jpg)

From the first equation it is immediate that *add Zero m* = *m* holds for any natural number *m*. Now let us show that the dual property, *add n Zero* = *n*, which we abbreviate by *p*, also holds for all natural numbers *n*. We proceed by induction on *n*. The base case, showing that *p Zero* holds, amounts to showing that *add Zero Zero* = *Zero*, which is immediate:

![image](images/image155_01.jpg)

For the inductive case, we must show that if *p* holds for any natural number *n*, then *p* (*Succ n*) also holds. That is, using the induction hypothesis *add n Zero* = *n* as an assumption, we must show that *add* (*Succ n*) *Zero* = *Succ n*, which can be verified by the following calculation:

![image](images/image155_02.jpg)

![image](images/image155_03.jpg)

Because proofs by induction normally involve more than one calculation, it is useful to explicitly indicate the end of the proof. For this purpose, we use a square box ![image](images/image155_03.jpg) in the right-hand margin, as illustrated above.

As another example, let us now show that addition of natural numbers is associative. That is, *add x* (*add y z*) = *add* (*add x y*) *z* for all natural numbers *x*, *y* and *z*. There are three arguments to choose from, so which should induction be performed over? Note that the *add* function is defined by pattern matching on its first argument, so it is natural to try induction on *x*, which appears twice as the first argument to *add* in the associativity equation, whereas *y* only appears once as such and *z* never. Using induction on *x*, the proof of the associativity of *add* proceeds as follows.

Base case:

![image](images/image156_00.jpg)

Inductive case:

![image](images/image156_01.jpg)

![image](images/image155_03.jpg)

Note that both cases start by applying definitions, and conclude by unapplying definitions. This pattern is typical in proofs by induction, but the latter part may seem somewhat mysterious at first. In particular, knowing which definitions to unapply seems to require a degree of foresight. In practice, however, if one becomes stuck at a certain point during such a calculation, progress can often be made by focusing on the desired end result and trying to work backwards to the point where one became stuck.

For example, after applying the induction hypothesis in the inductive case above to obtain *Succ* (*add* (*add x y*) *z*), it may not be clear how to proceed, as there are no more definitions that can be applied. However, if we then focus on the expression that we are aiming towards, *add* (*add* (*Succ x*) *y*) *z*, we can simply apply the inner *add* and then the outer *add* to produce the expression at which we became stuck, which process can then be reversed (turning applying into unapplying) to complete the calculation.

Although we have introduced induction using the recursive type *Nat*, the same principle can also be used with the integers that are built-in to Haskell. In particular, to prove that some property *p* holds for all integers *n* ≥ 0, it is sufficient to show that *p* holds for 0, the base case, and that if *p* holds for any *n* ≥ 0, then it also holds for *n* + 1, the inductive case.

For example, consider the following definition for the library function *replicate* that produces a list with *n* identical elements:

![image](images/image156_02.jpg)

Then it is easy to show that this function does indeed produce a list with *n* elements, that is *length* (*replicate n x*) = *n*, by induction on *n* ≥ 0.

Base case:

![image](images/image157_00.jpg)

Inductive case:

![image](images/image157_01.jpg)

![image](images/image155_03.jpg)

![](images/line.jpg)

13.5 Induction on lists

Induction is not restricted to natural numbers, but can also be used to reason about other recursive types, such as the type of lists. Just as natural numbers are built up recursively from zero by applying the successor function, so lists are built up from the empty list by applying the cons operator.

Suppose we want to prove that some property *p* holds for all lists. Then the induction principle for lists states that it is sufficient to show that *p* holds for the empty list [ ], the base case, and that if *p* holds for any list *xs*, then it also holds for *x* : *xs* for any element *x*, the inductive case. Of course, both the element *x* and the list *xs* must be of the appropriate types.

As an example, let us show that the function *reverse* defined earlier in this chapter is its own inverse, *reverse* (*reverse xs*) = *xs*, by induction on *xs*. The base case is verified simply by applying the definition of *reverse*:

![image](images/image157_02.jpg)

For the inductive case, using the assumption *reverse* (*reverse xs*) = *xs*, we show that *reverse* (*reverse* (*x* : *xs*)) = *x* : *xs*, as follows:

![image](images/image159_03.jpg)

![image](images/image155_03.jpg)

This calculation uses two auxiliary properties of the function *reverse*, namely our earlier result that *reverse* preserves singleton lists, *reverse* [*x*] = [*x*], together with a new result that *reverse* distributes over append, except that the order of the two argument lists is then swapped:

![image](images/image160_04.jpg)

Technically, we say that the distribution is contravariant. Because the append operator ++ is defined by pattern matching on its first argument, it is natural to attempt to verify this property by induction on *xs*.

Base case:

![image](images/image158_01.jpg)

Inductive case:

![image](images/image158_02.jpg)

![image](images/image155_03.jpg)

This calculation in turn uses the fact that ++ is associative, which can be verified by induction in a similar manner to our earlier result that *add* is associative (see exercise 5 for this chapter.)

![](images/line.jpg)

13.6 Making append vanish

Many recursive functions are naturally defined using the append operator ++ on lists, but this operator carries a considerable efficiency cost when used recursively. In this section, we show how induction can be used to eliminate such uses of append, and hence make functions more efficient. As a first example, consider again the following definition:

![image](images/image159_00.jpg)

How efficient is *reverse*? First of all, it is easy to show that the number of reduction steps required to evaluate *xs* ++ *ys* is one greater than the length of *xs*, assuming for simplicity that both *xs* and *ys* are already fully evaluated. As a result, we say that ++ takes linear time in the length of its first argument. In turn, the number of steps required by *reverse xs* for a list of length *n* can be shown to be the sum of the integers from 1 to *n* + 1, which is (*n* + 1)(*n* + 2)*/*2. Multiplying out the brackets using the equation verified at the start of this chapter gives (*n*² + 3*n* + 2)*/*2, as a result of which we say that *reverse* takes quadratic time in the length of its argument.

Quadratic time is bad. For example, reversing a list with ten thousand elements will take approximately fifty million reduction steps. Fortunately, however, through the use of induction it is easy to eliminate the use of append in the definition of *reverse*, and hence improve its efficiency.

The trick is to attempt to define a more general function, which combines the behaviours of *reverse* and ++. In particular, we seek to define a recursive function *reverse*′ that satisfies the following equation:

![image](images/image161_04.jpg)

That is, applying *reverse*′ to two lists should give the result of reversing the first list, appended together with the second list. If we can define such a function, then *reverse* itself can be redefined by *reverse xs* = *reverse*′ *xs* [ ], using the fact that the empty list is the identity for append.

Rather the giving the definition for *reverse*′, and then showing that it satisfies the above equation, we can in fact use this equation as the driving force for constructing the definition itself. In particular, we simply attempt to verify this equation by induction on *xs*. The base case results in an equation that gives the definition for *reverse*′ [ ] *ys*, while the inductive case results in an equation that gives the definition for *reverse*′ (*x* : *xs*) *ys*.

Base case:

![image](images/image159_01.jpg)

Inductive case:

![image](images/image159_02.jpg)

![image](images/image155_03.jpg)

We conclude from this proof that the definition

![image](images/image160_01.jpg)

suffices to show that *reverse*′ *xs ys* = *reverse xs* ++ *ys* by induction. Note that the definition for *reverse*′ does not refer to the original *reverse* function, or append. Hence, *reverse* itself can now be redefined as follows:

![image](images/image160_02.jpg)

For example, we have:

![image](images/image160_03.jpg)

That is, the list is reversed by using an extra argument to accumulate the final result. The new definition for *reverse* is perhaps less clear than the original version, but it is much more efficient. In particular, the number of reduction steps required to evaluate *reverse xs* for a list of length *n* using the new definition is simply *n* + 2, and hence *reverse* now takes linear time in the length of its argument. For example, reversing a list with ten thousand elements will now take approximately ten thousand steps, in contrast to some fifty million with the original definition — quite an improvement!

Note that we have already seen the use of accumulation to improve the efficiency of functions, in the context of the higher-order library function *foldl* in [chapters 7](#14_chapter_title_7.html) and [12](#19_chapter_title_12.html). For example, the accumulator version of *reverse* can also be obtained simply by defining *reverse* = *foldl* (*λxs x* → *x* : *xs*) [ ]. However, it is instructive to see how the same kind of behaviour can be obtained using induction.

As another example of the elimination of append, which also illustrates the use of induction on trees-like types, consider the following type of binary trees, together with a function that flattens such trees to a list:

![image](images/image161_00.jpg)

Because of the use of append, the function *flatten* is inefficient. Let us now construct a more efficient version, by using the same trick as for *reverse*. That is, we seek to define a more general function, *flatten*′, that combines the behaviours of the functions *flatten* and ++:

![image](images/image163_02.jpg)

In order to prove that some property holds for all trees, the induction principle for the type *Tree* states that it is sufficient to show that it holds for all trees of the form *Leaf n*, and that if the property holds for any trees *l* and *r*, then it also holds for *Node l r*. Using this principle, we construct a definition for *flatten*′ that satisfies the above equation as follows.

Base case:

![image](images/image161_01.jpg)

Inductive case:

![image](images/image161_02.jpg)

![image](images/image155_03.jpg)

We conclude that the definition

![image](images/image161_03.jpg)

satisfies the specification for *flatten*′, and hence that the original function *flatten* can now be redefined as follows:

![image](images/image162_00.jpg)

Once again, the new definition for *flatten* is perhaps less clear than the original version, but is much more efficient, by using an extra argument to accumulate the final result, rather than using append.

![](images/line.jpg)

13.7 Compiler correctness

We conclude this chapter with an extended example. Recall that in [chapter 10](#17_chapter_title_10.html) we defined a type of arithmetic expressions built up from integers using an addition operator, together with a function (here called *eval*) that evaluates an expression directly to an integer value:

![image](images/image162_01.jpg)

Such expressions can also be evaluated indirectly, by means of code that executes using a stack. In this context, a stack is simply a list of integers, and code comprises a list of push and add operations on the stack:

![image](images/image162_02.jpg)

The meaning of such code is given by defining a function that executes a piece of code using an initial stack to give a final stack:

![image](images/image162_03.jpg)

That is, the push operation places a new integer on the top of the stack, while add replaces the top two integers by their sum. Using these operations, it is now straightforward to define a function that compiles an expression into code. An integer value is compiled by simply pushing that value, while an addition is compiled by first compiling the two argument expressions *x* and *y*, and then adding the resulting two integers on the stack:

![image](images/image162_04.jpg)

Note that when an add operation is performed, the value of expression *y* will be the top of the stack, and the value of *x* will be the second top, hence the swapping of these two values in the definition of *exec*.

To illustrate the behaviour of the three functions defined above, if *e* :: *Expr* represents the expression (2 + 3) + 4, then we have:

![image](images/image165_03.jpg)

Generalising from this example, the correctness of our compiler for expressions can be expressed by the following equation:

![image](images/image165_04.jpg)

That is, compiling an expression and then executing the resulting code using an empty initial stack gives the same final stack as evaluating the expression and then converting the resulting integer into a singleton stack. For the purposes of proving this result, however, we will see that it is necessary to generalise from the empty initial stack to an arbitrary initial stack:

![image](images/image165_05.jpg)

Using induction for the type *Expr*, which is the same as induction for the type *Tree* in the previous section except that the names of the constructors are different, the compiler correctness equation can be verified as follows.

Base case:

![image](images/image163_00.jpg)

Inductive case:

![image](images/image166_03.jpg)

![image](images/image155_03.jpg)

Note that without having generalised the result to an arbitrary stack, the second induction hypothesis step would not be applicable, because the stack becomes non-empty at this point. The distributivity property used in the inductive case states that executing two pieces of code appended together gives the same result as executing the two pieces of code in sequence:

![image](images/image166_04.jpg)

The proof of this property proceeds by induction on the code *c*, with the inductive case being split into two separate cases, depending upon whether the first operation in the code is a push or an addition.

Base case:

![image](images/image164_01.jpg)

Inductive case:

![image](images/image164_02.jpg)

Inductive case:

![image](images/image164_03.jpg)

![image](images/image155_03.jpg)

The stack not having the assumed form in the second inductive case corresponds to a stack underflow error. In practice, this will never arise, because the structure of the compiler ensures that the stack will always contain at least two integers when an add operation is performed.

In fact, however, both the distributivity property and its consequent underflow issue can be avoided altogether by applying the technique of the previous section to eliminate the use of append. In particular, we seek to define a generalised function *comp*′ with the following property:

![image](images/image167_02.jpg)

By induction on *e*, we can construct the definition

![image](images/image165_00.jpg)

from which it follows that we can recover our original definition by *comp e*= *comp*′ *e* [ ]. In turn, the correctness of the new version of the compiler with respect to our semantics can now be stated as follows:

![image](images/image167_03.jpg)

That is, compiling an expression and then executing the resulting code together with arbitrary additional code gives the same result as executing the additional code with the value of the expression on top of the original stack. The proof of this result is by induction on the expression *e*.

Base case:

![image](images/image165_01.jpg)

Inductive case:

![image](images/image165_02.jpg)

![image](images/image155_03.jpg)

Note that with *s* = *c* = [ ], this new result simplifies to *exec* (*comp e*) [ ] = [*eval e*], our original statement of correctness. In addition to avoiding the problem of stack underflow in the correctness proof, the accumulator version of the compiler has two further benefits. First of all, it avoids the use of ++, and is hence more efficient. And, secondly, the new proof is less than half the combined length of our previous two proofs. As is often the case in formal reasoning, generalising a result in the appropriate manner can considerably simplify its proof. Mathematics is an excellent tool for guiding the development of efficient programs with simple proofs!

![](images/line.jpg)

13.8 Chapter remarks

Reasoning about functional programs is a subject for a book in its own right, and we have only touched the surface here. Topics for further reading include reasoning about partial and infinite structures (5; 8), relational and point-free approaches (1), automated testing of properties (4), reasoning about effects (24), and techniques that avoid induction (14). The compiler example is adapted from (18), and the phrase “making append vanish” is inspired by (30).

![](images/line.jpg)

13.9 Exercises

**1.**  Give an example of a function from the standard library in appendix A that is defined using overlapping patterns.

**2.**  Show that *add n* (*Succ m*) = *Succ* (*add n m*), by induction on *n*.

**3.**  Using this property, together with *add n Zero* = *n*, show that addition is commutative, *add n m* = *add m n*, by induction on *n*.

**4.**  Using the following definition for the library function that decides if *all* elements of a list satisfy a predicate

![image](images/image166_00.jpg)

complete the proof of the correctness of *replicate* by showing that it produces a list with identical elements, *all* (== *x*) (*replicate n x*), by induction on *n* ≥ 0\. Hint: show that the property is always *True*.

**5.**  Using the definition

![image](images/image166_01.jpg)

verify the following two properties, by induction on *xs*:

![image](images/image166_02.jpg)

Hint: the proofs are similar to those for the *add* function.

**6.**  The equation *reverse* (*reverse xs*) = *xs* can also be proved using a single auxiliary result, *reverse* (*xs* ++ [*x*]) = *x* : *reverse xs*, which can itself be verified by induction on *xs*. Why might the proof using three auxiliary results as in this chapter be viewed as preferable?

**7.**  Using the definitions

![image](images/image167_00.jpg)

show that *map f* (*map g xs*) = *map* (*f* ![](images/sm.jpg) *g*) *xs*, by induction on *xs*.

**8.**  Using the definition for ++ given above, together with

![image](images/image167_01.jpg)

show that *take n xs* ++ *drop n xs* = *xs*, by simultaneous induction on the integer *n* ≥ 0 and the list *xs*. Hint: there are three cases, one for each pattern of arguments in the definitions of *take* and *drop*.

**9.**  Given the type declaration

![image](images/image169_08.jpg)

show that the number of leaves in a such a tree is always one greater than the number of nodes, by induction on trees. Hint: start by defining functions that count the number of leaves and nodes in a tree.

**10.**  Given the equation *comp*′ *e c* = *comp e* ++ *c*, show how to construct the recursive definition for *comp*′, by induction on *e*.

Appendix A

**Standard prelude**

In this appendix we present some of the most commonly used definitions from the standard prelude. For clarity, a number of the definitions have been simplified or modified from those given in the Haskell Report (25).

![](images/line.jpg)

A.1 Classes

Equality types:

![image](images/image170_10.jpg)

Ordered types:

![image](images/image170_11.jpg)

Showable types:

![image](images/image170_12.jpg)

Readable types:

![image](images/image170_13.jpg)

Numeric types:

![image](images/image171_07.jpg)

Integral types:

![image](images/image171_08.jpg)

Fractional types:

![image](images/image171_09.jpg)

Monadic types:

![image](images/image171_10.jpg)

![](images/line.jpg)

A.2 Logical values

Type declaration:

![image](images/image169_03.jpg)

Logical conjunction:

![image](images/image169_04.jpg)

Logical disjunction:

![image](images/image169_05.jpg)

Logical negation:

![image](images/image169_06.jpg)

Guard that always succeeds:

![image](images/image169_07.jpg)

![](images/line.jpg)

A.3 Characters and strings

Type declarations:

![image](images/image170_00.jpg)

Decide if a character is a lower-case letter:

![image](images/image170_01.jpg)

Decide if a character is an upper-case letter:

![image](images/image170_02.jpg)

Decide if a character is alphabetic:

![image](images/image170_03.jpg)

Decide if a character is a digit:

![image](images/image170_04.jpg)

Decide if a character is alpha-numeric:

![image](images/image170_05.jpg)

Decide if a character is spacing:

![image](images/image170_06.jpg)

Convert a character to a Unicode number:

![image](images/image170_07.jpg)

Convert a Unicode number to a character:

![image](images/image170_08.jpg)

Convert a digit to an integer:

![image](images/image170_09.jpg)

Convert an integer to a digit:

![image](images/image171_00.jpg)

Convert a letter to lower-case:

![image](images/image171_01.jpg)

Convert a letter to upper-case:

![image](images/image171_02.jpg)

![](images/line.jpg)

A.4 Numbers

Type declarations:

![image](images/image171_03.jpg)

Decide if an integer is even:

![image](images/image171_04.jpg)

Decide if an integer is odd:

![image](images/image171_05.jpg)

Exponentiation:

![image](images/image171_06.jpg)

![](images/line.jpg)

A.5 Tuples

Type declarations:

![image](images/image172_00.jpg)

Select the first component of a pair:

![image](images/image172_01.jpg)

Select the second component of a pair:

![image](images/image172_02.jpg)

![](images/line.jpg)

A.6 Maybe

Type declaration:

![image](images/image172_03.jpg)

![](images/line.jpg)

A.7 Lists

Type declaration:

![image](images/image172_04.jpg)

Decide if a list is empty:

![image](images/image172_05.jpg)

Decide if a value is an element of a list:

![image](images/image172_06.jpg)

Decide if all logical values in a list are *True*:

![image](images/image172_07.jpg) ![image](images/image173_00.jpg)

Decide if any logical value in a list is *True*:

![image](images/image173_01.jpg)

Decide if all elements of a list satisfy a predicate:

![image](images/image173_02.jpg)

Decide if any element of a list satisfies a predicate:

![image](images/image173_03.jpg)

Select the first element of a non-empty list:

![image](images/image173_04.jpg)

Select the last element of a non-empty list:

![image](images/image173_05.jpg)

Select the *n*th element of a non-empty list:

![image](images/image173_06.jpg)

Select the first *n* elements of a list:

![image](images/image173_07.jpg)

Select all elements of a list that satisfy a predicate:

![image](images/image173_08.jpg)

Select elements of a list while they satisfy a predicate:

![image](images/image173_09.jpg)

Remove the first element from a non-empty list:

![image](images/image176_08.jpg)

Remove the last element from a non-empty list:

![image](images/image174_00.jpg)

Remove the first *n* elements from a list:

![image](images/image174_01.jpg)

Remove elements from a list while they satisfy a predicate:

![image](images/image174_02.jpg)

Split a list at the *n*th element:

![image](images/image174_03.jpg)

Split a list using a predicate:

![image](images/image174_04.jpg)

Process a list using an operator that associates to the right:

![image](images/image174_05.jpg)

Process a non-empty list using an operator that associates to the right:

![image](images/image174_06.jpg)

Process a list using an operator that associates to the left:

![image](images/image174_07.jpg)

Process a non-empty list using an operator that associates to the left:

![image](images/image174_08.jpg)

Produce an infinite list of identical elements:

![image](images/image175_00.jpg)

Produce a list with *n* identical elements:

![image](images/image175_01.jpg)

Produce an infinite list by iterating a function over a value:

![image](images/image175_02.jpg)

Produce a list of pairs from a pair of lists:

![image](images/image175_03.jpg)

Calculate the length of a list:

![image](images/image175_04.jpg)

Calculate the sum of a list of numbers:

![image](images/image175_05.jpg)

Calculate the product of a list of numbers:

![image](images/image175_06.jpg)

Calculate the minimum of a non-empty list:

![image](images/image175_07.jpg)

Calculate the maximum of a non-empty list:

![image](images/image175_08.jpg)

Append two lists:

![image](images/image175_09.jpg)

Concatenate a list of lists:

![image](images/image175_10.jpg)

Reverse a list:

![image](images/image176_00.jpg)

Apply a function to all elements of a list:

![image](images/image176_01.jpg)

![](images/line.jpg)

A.8 Functions

Type declaration:

![image](images/image178_01.jpg)

Identity function:

![image](images/image176_02.jpg)

Function composition:

![image](images/image176_03.jpg)

Constant functions:

![image](images/image176_04.jpg)

Strict application:

![image](images/image176_05.jpg)

Convert a function on pairs to a curried function:

![image](images/image176_06.jpg)

Convert a curried function to a function on pairs:

![image](images/image176_07.jpg)

![](images/line.jpg)

A.9 Input/output

Type declaration:

![image](images/image178_02.jpg)

Read a character from the keyboard:

![image](images/image177_00.jpg)

Read a string from the keyboard:

![image](images/image177_01.jpg)

Read a value from the keyboard:

![image](images/image177_02.jpg)

Write a character to the screen:

![image](images/image177_03.jpg)

Write a string to the screen:

![image](images/image177_04.jpg)

Write a string to the screen and move to a new line:

![image](images/image177_05.jpg)

Write a value to the screen:

![image](images/image177_06.jpg)

Display an error message and terminate the program:

![image](images/image177_07.jpg)

Appendix B

**Symbol table**

In this appendix we present a table that summarises the meaning of each of the special Haskell symbols that are used in this book, and shows how each of the symbols is typed using a normal keyboard.

![image](images/table178_00.jpg)

Bibliography

1.  Richard Bird and Oege de Moor. *Algebra of Programming*. Prentice Hall, 1997.

2.  Richard Bird and Shin-Cheng Mu. Countdown: A Case Study in Origami Programming. University of Oxford, 2005.

3.  Richard Bird and Philip Wadler. *An Introduction to Functional Programming*. Prentice Hall, 1988.

4.  Koen Claessen and John Hughes. QuickCheck: A Lightweight Tool for Random Testing of Haskell Programs. In *Proceedings of the Fifth ACM SIGPLAN International Conference on Functional Programming*, Montreal, Canada, September 2000.

5.  Nils Anders Danielsson and Patrik Jansson. Chasing Bottoms: A Case Study in Program Verification in the Presense of Partial and Infinite Values. In *Proceedings of the 7th International Conference on Mathematics of Program Construction*, volume 3125 of *Lecture Notes in Computer Science*, Stirling, Scotland, Springer, 2004.

6.  Karl-Filip Faxén. A Static Semantics for Haskell. In Graham Hutton, editor, *Journal of Functional Programming, Special Double Issue on Haskell*, **12**(4&5). Cambridge University Press, 2002.

7.  Jeremy Gibbons and Oege de Moor, eds. *The Fun of Programming*. Palgrave, 2003.

8.  Jeremy Gibbons and Graham Hutton. Proof Methods for Corecursive Programs. *Fundamenta Informaticae: Special Issue on Program Transformation*, **66**(4): 353–366, 2005.

9.  Andy Gill and Simon Marlow. Happy: A Parser Generator for Haskell. Available on the web from: [www.haskell.org/happy](http://www.haskell.org/happy)

10.  Hugh Glaser, Pieter Hartel, and Paul Garratt. Programming by Numbers: A Programming Method for Novices. *The Computer Journal*, **43**(4), 2000.

11.  Paul Hudak. Conception, Evolution and Application of Functional Programming Languages. *Communications of the ACM*, **21**(3): 359–411, 1989.

12.  Gerard Huet. The Zipper. *Journal of Functional Programming*, **7**(5): 549–554, September 1997.

13.  John Hughes. Why Functional Programming Matters. *The Computer Journal*, **32**(2): 98–107, 1989.

14.  Graham Hutton. A Tutorial on the Universality and Expressiveness of Fold. *Journal of Functional Programming*, **9**(4): 355–372, 1999.

15.  Graham Hutton. The Countdown Problem. *Journal of Functional Programming*, **12**(6): 609–616, 2002.

16.  Graham Hutton and Erik Meijer. Monadic Parser Combinators. Technical Report NOTTCS-TR-96-4, Department of Computer Science, University of Nottingham, 1996.

17.  Graham Hutton and Erik Meijer. Monadic Parsing in Haskell. *Journal of Functional Programming*, **8**(4): 437–444, 1998.

18.  Graham Hutton and Joel Wright. Compiling Exceptions Correctly. In *Proceedings of the 7th International Conference on Mathematics of Program Construction*, vol. 3125 of *Lecture Notes in Computer Science*, Stirling, Scotland. Springer, 2004.

19.  Graham Hutton and Joel Wright. Calculating an Exceptional Machine. In Hans-Wolfgang Loidl, ed., *Trends in Functional Programming, vol. 5*: Intellect, February 2006\. Selected papers from the Fifth Symposium on Trends in Functional Programming, Munich, November 2004.

20.  Mark P. Jones. Typing Haskell in Haskell. In *Proceedings of the 1999 Haskell Workshop*, Paris, France, 1999.

21.  John Launchbury. A Natural Semantics for Lazy Evaluation. In *Proceedings of the 20th ACM SIGPLAN-SIGACT Symposium on Principles of Programming Languages*, pages 144–154, Charleston, South Carolina, January 1993.

22.  Daan Leijen. Parsec: A Parsing Library for Haskell. Available on the web from: [www.haskell.org/parsec](http://www.haskell.org/parsec)

23.  Saunders MacLane. *Categories for the Working Mathematician*. Number 5 in *Graduate Texts in Mathematics*. Springer-Verlag, 1971.

24.  Simon Peyton Jones. Tackling the Awkward Squad: Monadic Input/Output, Concurrency, Exceptions, and Foreign-Language Calls in Haskell. In Tony Hoare, Manfred Broy, and Ralf Steinbruggen, eds., *Engineering Theories of Software Construction*, pages 47–96\. IOS Press, 2001. Presented at the 2000 Marktoberdorf Summer School.

25.  Simon Peyton Jones. *Haskell 98 Language and Libraries: The Revised Report*. Cambridge University Press, 2003\. Also available on the web from [www.haskell.org/definition](http://www.haskell.org/definition)

26.  Simon Peyton Jones and David Lester. *Implementing Functional Languages: A Tutorial*. Prentice Hall, 1992.

27.  V.J. Rayward-Smith. *A First Course in Formal Language Theory*, vol. 234 of *Pitman Research Notes in Math*. Blackwell Scientific Publications, 1983.

28.  John C. Reynolds. *Theories of Programming Languages*. Cambridge University Press, 1998.

29.  Simon Singh. *The Code Book: The Secret History of Codes and Code Breaking*. Fourth Estate, 1999.

30.  Philip Wadler. The Concatenate Vanishes. University of Glasgow, 1989.

31.  Philip Wadler. Monads for Functional Programming. In Manfred Broy, ed., *Proceedings of the Marktoberdorf Summer School on Program Design Calculi*. Springer–Verlag, 1992.

Index

(), [20](#10_chapter_title_3.html_pl-32-20), [81](#15_chapter_title_8.html_pl-93-81), [88](#16_chapter_title_9.html_pl-100-88), [160](#21_appendix_title.html_pl-172-160)

[ ], [20](#10_chapter_title_3.html_pl-32-20), [75](#15_chapter_title_8.html_pl-87-75), [118](#18_chapter_title_11.html_pl-130-118), [160](#21_appendix_title.html_pl-172-160)

$!, [134](#19_chapter_title_12.html_pl-146-134), [164](#21_appendix_title.html_pl-176-164)

⇒, [23](#10_chapter_title_3.html_pl-35-23), [166](#22_conclusion_title.html_pl-178-166)

_, [32](#11_chapter_title_4.html_pl-44-32), [39](#12_chapter_title_5.html_pl-51-39), [50](#13_chapter_title_6.html_pl-62-50), [57](#13_chapter_title_6.html_pl-69-57), [59](#13_chapter_title_6.html_pl-71-59)

>>=, [77](#15_chapter_title_8.html_pl-89-77), [89](#16_chapter_title_9.html_pl-101-89), [113](#17_chapter_title_10.html_pl-125-113), [157](#21_appendix_title.html_pl-169-157), [166](#22_conclusion_title.html_pl-178-166)

≥, [25](#10_chapter_title_3.html_pl-37-25), [156](#21_appendix_title.html_pl-168-156), [166](#22_conclusion_title.html_pl-178-166)

*λ*, [35](#11_chapter_title_4.html_pl-47-35), [68](#14_chapter_title_7.html_pl-80-68), [76](#15_chapter_title_8.html_pl-88-76), [127](#19_chapter_title_12.html_pl-139-127), [166](#22_conclusion_title.html_pl-178-166)

←, [38](#12_chapter_title_5.html_pl-50-38), [77](#15_chapter_title_8.html_pl-89-77), [90](#16_chapter_title_9.html_pl-102-90), [166](#22_conclusion_title.html_pl-178-166)

≤, [25](#10_chapter_title_3.html_pl-37-25), [156](#21_appendix_title.html_pl-168-156), [166](#22_conclusion_title.html_pl-178-166)

*, [10](#09_chapter_title_2.html_pl-22-10), [27](#10_chapter_title_3.html_pl-39-27), [157](#21_appendix_title.html_pl-169-157)

+, [10](#09_chapter_title_2.html_pl-22-10), [27](#10_chapter_title_3.html_pl-39-27), [157](#21_appendix_title.html_pl-169-157)

−, [10](#09_chapter_title_2.html_pl-22-10), [27](#10_chapter_title_3.html_pl-39-27), [157](#21_appendix_title.html_pl-169-157)

*/*, [28](#10_chapter_title_3.html_pl-40-28), [44](#12_chapter_title_5.html_pl-56-44), [157](#21_appendix_title.html_pl-169-157)

::, [17](#10_chapter_title_3.html_pl-29-17)

:, [33](#11_chapter_title_4.html_pl-45-33), [160](#21_appendix_title.html_pl-172-160)

*<*, [25](#10_chapter_title_3.html_pl-37-25), [156](#21_appendix_title.html_pl-168-156)

>, [25](#10_chapter_title_3.html_pl-37-25), [156](#21_appendix_title.html_pl-168-156)

◦, [68](#14_chapter_title_7.html_pl-80-68), [164](#21_appendix_title.html_pl-176-164), [166](#22_conclusion_title.html_pl-178-166)

↑, [10](#09_chapter_title_2.html_pl-22-10), [159](#21_appendix_title.html_pl-171-159), [166](#22_conclusion_title.html_pl-178-166)

==, [24](#10_chapter_title_3.html_pl-36-24), [156](#21_appendix_title.html_pl-168-156)

∨, [157](#21_appendix_title.html_pl-169-157), [166](#22_conclusion_title.html_pl-178-166)

∧, [32](#11_chapter_title_4.html_pl-44-32), [157](#21_appendix_title.html_pl-169-157), [166](#22_conclusion_title.html_pl-178-166)

|, [31](#11_chapter_title_4.html_pl-43-31), [38](#12_chapter_title_5.html_pl-50-38), [100](#17_chapter_title_10.html_pl-112-100)

¬, [32](#11_chapter_title_4.html_pl-44-32), [157](#21_appendix_title.html_pl-169-157), [166](#22_conclusion_title.html_pl-178-166)

≠, [24](#10_chapter_title_3.html_pl-36-24), [156](#21_appendix_title.html_pl-168-156), [166](#22_conclusion_title.html_pl-178-166)

++, [12](#09_chapter_title_2.html_pl-24-12), [51](#13_chapter_title_6.html_pl-63-51), [66](#14_chapter_title_7.html_pl-78-66), [67](#14_chapter_title_7.html_pl-79-67), [163](#21_appendix_title.html_pl-175-163), [166](#22_conclusion_title.html_pl-178-166)

!!, [11](#09_chapter_title_2.html_pl-23-11), [161](#21_appendix_title.html_pl-173-161)

→, [21](#10_chapter_title_3.html_pl-33-21), [164](#21_appendix_title.html_pl-176-164), [166](#22_conclusion_title.html_pl-178-166)

*abs*, [27](#10_chapter_title_3.html_pl-39-27), [31](#11_chapter_title_4.html_pl-43-31), [157](#21_appendix_title.html_pl-169-157)

absolute value, *see* [*abs*](#24_index_title.html_ind1)

accumulation, [2](#08_chapter_title_1.html_pl-14-2), [66](#14_chapter_title_7.html_pl-78-66), [135](#19_chapter_title_12.html_pl-147-135), [148](#20_chapter_title_13.html_pl-160-148)

actions, [88](#16_chapter_title_9.html_pl-100-88)

addition, *see* [+](#24_index_title.html_ind2), [*sum*](#24_index_title.html_ind3)

*all*, [64](#14_chapter_title_7.html_pl-76-64), [161](#21_appendix_title.html_pl-173-161)

*and*, [64](#14_chapter_title_7.html_pl-76-64), [67](#14_chapter_title_7.html_pl-79-67), [160](#21_appendix_title.html_pl-172-160)

*any*, [64](#14_chapter_title_7.html_pl-76-64), [161](#21_appendix_title.html_pl-173-161)

append, *see* [++](#24_index_title.html_ind4)

application, [1](#08_chapter_title_1.html_pl-13-1), [12](#09_chapter_title_2.html_pl-24-12), [17](#10_chapter_title_3.html_pl-29-17), [22](#10_chapter_title_3.html_pl-34-22), [134](#19_chapter_title_12.html_pl-146-134)

> partial, [22](#10_chapter_title_3.html_pl-34-22), [62](#14_chapter_title_7.html_pl-74-62), [65](#14_chapter_title_7.html_pl-77-65)
> 
> strict, *see* [$!](#24_index_title.html_ind5)

assignment, [3](#08_chapter_title_1.html_pl-15-3), [125](#19_chapter_title_12.html_pl-137-125)

associativity, [11](#09_chapter_title_2.html_pl-23-11), [66](#14_chapter_title_7.html_pl-78-66), [140](#20_chapter_title_13.html_pl-152-140)

> for addition, [67](#14_chapter_title_7.html_pl-79-67), [82](#15_chapter_title_8.html_pl-94-82), [139](#20_chapter_title_13.html_pl-151-139), [143](#20_chapter_title_13.html_pl-155-143)
> 
> for append, [146](#20_chapter_title_13.html_pl-158-146)
> 
> for application, [22](#10_chapter_title_3.html_pl-34-22)
> 
> for composition, [68](#14_chapter_title_7.html_pl-80-68)
> 
> for cons, [33](#11_chapter_title_4.html_pl-45-33)
> 
> for function types, [22](#10_chapter_title_3.html_pl-34-22)
> 
> for multiplication, [82](#15_chapter_title_8.html_pl-94-82)

binary trees, [103](#17_chapter_title_10.html_pl-115-103)

*Bool*, [17](#10_chapter_title_3.html_pl-29-17), [18](#10_chapter_title_3.html_pl-30-18), [157](#21_appendix_title.html_pl-169-157)

**case**, [76](#15_chapter_title_8.html_pl-88-76)

category theory, [114](#17_chapter_title_10.html_pl-126-114)

*Char*, [18](#10_chapter_title_3.html_pl-30-18), [158](#21_appendix_title.html_pl-170-158)

characters, *see* [*Char*](#24_index_title.html_ind6)

*chr*, [43](#12_chapter_title_5.html_pl-55-43), [158](#21_appendix_title.html_pl-170-158)

**class**, [111](#17_chapter_title_10.html_pl-123-111)

classes, [24](#10_chapter_title_3.html_pl-36-24), [111](#17_chapter_title_10.html_pl-123-111), [156](#21_appendix_title.html_pl-168-156)

> constraints, [23](#10_chapter_title_3.html_pl-35-23), [111](#17_chapter_title_10.html_pl-123-111)
> 
> default definitions, [111](#17_chapter_title_10.html_pl-123-111)
> 
> derived instances, [112](#17_chapter_title_10.html_pl-124-112)
> 
> instances, [24](#10_chapter_title_3.html_pl-36-24), [111](#17_chapter_title_10.html_pl-123-111)
> 
> methods, [24](#10_chapter_title_3.html_pl-36-24)

clearing the screen, [91](#16_chapter_title_9.html_pl-103-91)

comments, [15](#09_chapter_title_2.html_pl-27-15)

commutativity, [122](#18_chapter_title_11.html_pl-134-122)

> for addition, [122](#18_chapter_title_11.html_pl-134-122), [154](#20_chapter_title_13.html_pl-166-154)
> 
> for multiplication, [122](#18_chapter_title_11.html_pl-134-122), [139](#20_chapter_title_13.html_pl-151-139)

composition, *see* [◦](#24_index_title.html_ind10)

comprehensions

> list, [4](#08_chapter_title_1.html_pl-16-4), [38](#12_chapter_title_5.html_pl-50-38)
> 
> set, [38](#12_chapter_title_5.html_pl-50-38), [46](#12_chapter_title_5.html_pl-58-46)
> 
> string, [42](#12_chapter_title_5.html_pl-54-42)

*concat*, [39](#12_chapter_title_5.html_pl-51-39), [163](#21_appendix_title.html_pl-175-163)

concatenation, *see* [*concat*](#24_index_title.html_ind7)

conditions, [31](#11_chapter_title_4.html_pl-43-31)

conjunction, *see* [∧](#24_index_title.html_ind8), [*and*](#24_index_title.html_ind9)

cons, *see* [:](#24_index_title.html_ind11)

*const*, [35](#11_chapter_title_4.html_pl-47-35), [164](#21_appendix_title.html_pl-176-164)

control characters, [19](#10_chapter_title_3.html_pl-31-19), [91](#16_chapter_title_9.html_pl-103-91)

*curry*, [164](#21_appendix_title.html_pl-176-164)

cursor, [91](#16_chapter_title_9.html_pl-103-91)

dangling else, [31](#11_chapter_title_4.html_pl-43-31)

**data**, [100](#17_chapter_title_10.html_pl-112-100)

**deriving**, [112](#17_chapter_title_10.html_pl-124-112)

*digitToInt*, [158](#21_appendix_title.html_pl-170-158)

disjunction, *see* [∨](#24_index_title.html_ind12), [*or*](#24_index_title.html_ind13)

distributivity, [139](#20_chapter_title_13.html_pl-151-139), [146](#20_chapter_title_13.html_pl-158-146), [152](#20_chapter_title_13.html_pl-164-152)

*div*, [10](#09_chapter_title_2.html_pl-22-10), [14](#09_chapter_title_2.html_pl-26-14), [27](#10_chapter_title_3.html_pl-39-27), [71](#14_chapter_title_7.html_pl-83-71), [157](#21_appendix_title.html_pl-169-157)

division, *see* [*div*](#24_index_title.html_ind14), [*/*](#24_index_title.html_ind15)

**do**, [77](#15_chapter_title_8.html_pl-89-77), [89](#16_chapter_title_9.html_pl-101-89), [114](#17_chapter_title_10.html_pl-126-114)

domain-specific languages, [5](#08_chapter_title_1.html_pl-17-5), [62](#14_chapter_title_7.html_pl-74-62)

domino effect, [143](#20_chapter_title_13.html_pl-155-143)

Dr Seuss, [75](#15_chapter_title_8.html_pl-87-75)

*drop*, [11](#09_chapter_title_2.html_pl-23-11), [53](#13_chapter_title_6.html_pl-65-53), [56](#13_chapter_title_6.html_pl-68-56), [162](#21_appendix_title.html_pl-174-162)

*dropWhile*, [64](#14_chapter_title_7.html_pl-76-64), [162](#21_appendix_title.html_pl-174-162)

*elem*, [160](#21_appendix_title.html_pl-172-160)

*Eq*, [24](#10_chapter_title_3.html_pl-36-24), [40](#12_chapter_title_5.html_pl-52-40), [156](#21_appendix_title.html_pl-168-156)

equality, *see* [==](#24_index_title.html_ind16)

equational reasoning, [5](#08_chapter_title_1.html_pl-17-5), [139](#20_chapter_title_13.html_pl-151-139)

*error*, [84](#15_chapter_title_8.html_pl-96-84), [165](#21_appendix_title.html_pl-177-165)

error messages, [12](#09_chapter_title_2.html_pl-24-12), *see* [*error*](#24_index_title.html_ind17)

evaluation, [10](#09_chapter_title_2.html_pl-22-10), [17](#10_chapter_title_3.html_pl-29-17), [84](#15_chapter_title_8.html_pl-96-84), [117](#18_chapter_title_11.html_pl-129-117), [124](#19_chapter_title_12.html_pl-136-124)

> call-by-name, [127](#19_chapter_title_12.html_pl-139-127), [128](#19_chapter_title_12.html_pl-140-128)
> 
> call-by-value, [126](#19_chapter_title_12.html_pl-138-126), [128](#19_chapter_title_12.html_pl-140-128)
> 
> innermost, [126](#19_chapter_title_12.html_pl-138-126)
> 
> lazy, [5](#08_chapter_title_1.html_pl-17-5), [20](#10_chapter_title_3.html_pl-32-20), [32](#11_chapter_title_4.html_pl-44-32), [40](#12_chapter_title_5.html_pl-52-40), [70](#14_chapter_title_7.html_pl-82-70), [130](#19_chapter_title_12.html_pl-142-130)
> 
> outermost, [126](#19_chapter_title_12.html_pl-138-126)
> 
> top-level, [134](#19_chapter_title_12.html_pl-146-134)

*even*, [30](#11_chapter_title_4.html_pl-42-30), [53](#13_chapter_title_6.html_pl-65-53), [159](#21_appendix_title.html_pl-171-159)

examples

> abstract machine, [109](#17_chapter_title_10.html_pl-121-109)
> 
> base conversion, [70](#14_chapter_title_7.html_pl-82-70)
> 
> Caesar cipher, [42](#12_chapter_title_5.html_pl-54-42)
> 
> calculator, [91](#16_chapter_title_9.html_pl-103-91)
> 
> chi-square, [45](#12_chapter_title_5.html_pl-57-45)
> 
> compiler, [150](#20_chapter_title_13.html_pl-162-150)
> 
> countdown, [116](#18_chapter_title_11.html_pl-128-116)
> 
> expression parser, [82](#15_chapter_title_8.html_pl-94-82)
> 
> factorial, [14](#09_chapter_title_2.html_pl-26-14), [48](#13_chapter_title_6.html_pl-60-48)
> 
> fast reverse, [147](#20_chapter_title_13.html_pl-159-147)
> 
> Fibonacci sequence, [53](#13_chapter_title_6.html_pl-65-53), [137](#19_chapter_title_12.html_pl-149-137)
> 
> game of life, [94](#16_chapter_title_9.html_pl-106-94)
> 
> insertion sort, [52](#13_chapter_title_6.html_pl-64-52)
> 
> permutations, [118](#18_chapter_title_11.html_pl-130-118)
> 
> prime numbers, [40](#12_chapter_title_5.html_pl-52-40), [133](#19_chapter_title_12.html_pl-145-133)
> 
> quicksort, [7](#08_chapter_title_1.html_pl-19-7), [53](#13_chapter_title_6.html_pl-65-53)
> 
> sieve of Eratosthenes, [134](#19_chapter_title_12.html_pl-146-134)
> 
> string transmitter, [69](#14_chapter_title_7.html_pl-81-69)
> 
> subsequences, [118](#18_chapter_title_11.html_pl-130-118)
> 
> tautology checker, [105](#17_chapter_title_10.html_pl-117-105)

exception handling, [97](#16_chapter_title_9.html_pl-109-97)

exponentiation, *see* [↑](#24_index_title.html_ind18)

expressions, [1](#08_chapter_title_1.html_pl-13-1)

> arithmetic, [82](#15_chapter_title_8.html_pl-94-82), [109](#17_chapter_title_10.html_pl-121-109), [116](#18_chapter_title_11.html_pl-128-116), [150](#20_chapter_title_13.html_pl-162-150)
> 
> conditional, *see* [**if**](#24_index_title.html_ind19)
> 
> impure, [89](#16_chapter_title_9.html_pl-101-89)
> 
> lambda, *see* [*λ*](#24_index_title.html_ind20)
> 
> logical, [105](#17_chapter_title_10.html_pl-117-105)
> 
> pure, [89](#16_chapter_title_9.html_pl-101-89)
> 
> reducible, [125](#19_chapter_title_12.html_pl-137-125)

*False*, [17](#10_chapter_title_3.html_pl-29-17), [18](#10_chapter_title_3.html_pl-30-18)

file handling, [97](#16_chapter_title_9.html_pl-109-97)

*filter*, [63](#14_chapter_title_7.html_pl-75-63), [161](#21_appendix_title.html_pl-173-161)

*Float*, [19](#10_chapter_title_3.html_pl-31-19), [44](#12_chapter_title_5.html_pl-56-44), [159](#21_appendix_title.html_pl-171-159)

*foldl*, [56](#13_chapter_title_6.html_pl-68-56), [67](#14_chapter_title_7.html_pl-79-67), [136](#19_chapter_title_12.html_pl-148-136), [162](#21_appendix_title.html_pl-174-162)

*foldl1*, [162](#21_appendix_title.html_pl-174-162)

*foldr*, [56](#13_chapter_title_6.html_pl-68-56), [64](#14_chapter_title_7.html_pl-76-64), [72](#14_chapter_title_7.html_pl-84-72), [162](#21_appendix_title.html_pl-174-162)

*foldr1*, [162](#21_appendix_title.html_pl-174-162)

FP, [6](#08_chapter_title_1.html_pl-18-6)

*Fractional*, [28](#10_chapter_title_3.html_pl-40-28), [157](#21_appendix_title.html_pl-169-157)

*fromInt*, [44](#12_chapter_title_5.html_pl-56-44)

*fst*, [33](#11_chapter_title_4.html_pl-45-33), [160](#21_appendix_title.html_pl-172-160)

functions, [1](#08_chapter_title_1.html_pl-13-1), [12](#09_chapter_title_2.html_pl-24-12), [21](#10_chapter_title_3.html_pl-33-21), [164](#21_appendix_title.html_pl-176-164)

> combinatorial, [118](#18_chapter_title_11.html_pl-130-118)
> 
> composite, *see* [◦](#24_index_title.html_ind10)
> 
> constant, *see* [*const*](#24_index_title.html_ind21)
> 
> constructor, [101](#17_chapter_title_10.html_pl-113-101)
> 
> curried, [22](#10_chapter_title_3.html_pl-34-22), [35](#11_chapter_title_4.html_pl-47-35), [61](#14_chapter_title_7.html_pl-73-61), [127](#19_chapter_title_12.html_pl-139-127), [135](#19_chapter_title_12.html_pl-147-135)
> 
> higher-order, [5](#08_chapter_title_1.html_pl-17-5), [62](#14_chapter_title_7.html_pl-74-62)
> 
> identity, *see* [*id*](#24_index_title.html_ind22)
> 
> nameless, *see* [*λ*](#24_index_title.html_ind20)
> 
> overloaded, [4](#08_chapter_title_1.html_pl-16-4), [24](#10_chapter_title_3.html_pl-36-24)
> 
> polymorphic, [4](#08_chapter_title_1.html_pl-16-4), [23](#10_chapter_title_3.html_pl-35-23), [42](#12_chapter_title_5.html_pl-54-42), [62](#14_chapter_title_7.html_pl-74-62)
> 
> recursive, [7](#08_chapter_title_1.html_pl-19-7), [48](#13_chapter_title_6.html_pl-60-48)
> 
> strict, [127](#19_chapter_title_12.html_pl-139-127), [134](#19_chapter_title_12.html_pl-146-134)
> 
> total, [21](#10_chapter_title_3.html_pl-33-21)

generators, *see* [←](#24_index_title.html_ind23)

*getCh*, [90](#16_chapter_title_9.html_pl-102-90)

*getChar*, [88](#16_chapter_title_9.html_pl-100-88), [90](#16_chapter_title_9.html_pl-102-90), [165](#21_appendix_title.html_pl-177-165)

*getLine*, [90](#16_chapter_title_9.html_pl-102-90), [165](#21_appendix_title.html_pl-177-165)

GHC, [10](#09_chapter_title_2.html_pl-22-10), [120](#18_chapter_title_11.html_pl-132-120)

grammars, [82](#15_chapter_title_8.html_pl-94-82)

> ambiguous, [84](#15_chapter_title_8.html_pl-96-84)

guards, [5](#08_chapter_title_1.html_pl-17-5), [31](#11_chapter_title_4.html_pl-43-31), [39](#12_chapter_title_5.html_pl-51-39), [58](#13_chapter_title_6.html_pl-70-58)

*head*, [11](#09_chapter_title_2.html_pl-23-11), [34](#11_chapter_title_4.html_pl-46-34), [161](#21_appendix_title.html_pl-173-161)

Hugs, [10](#09_chapter_title_2.html_pl-22-10), [13](#09_chapter_title_2.html_pl-25-13)

> commands, [14](#09_chapter_title_2.html_pl-26-14)

*id*, [69](#14_chapter_title_7.html_pl-81-69), [164](#21_appendix_title.html_pl-176-164)

identifiers, [14](#09_chapter_title_2.html_pl-26-14), [80](#15_chapter_title_8.html_pl-92-80)

identities, [122](#18_chapter_title_11.html_pl-134-122)

> for addition, [7](#08_chapter_title_1.html_pl-19-7)
> 
> for append, [147](#20_chapter_title_13.html_pl-159-147)
> 
> for composition, [68](#14_chapter_title_7.html_pl-80-68)
> 
> for division, [122](#18_chapter_title_11.html_pl-134-122)
> 
> for multiplication, [49](#13_chapter_title_6.html_pl-61-49), [55](#13_chapter_title_6.html_pl-67-55), [122](#18_chapter_title_11.html_pl-134-122)

**if**, [18](#10_chapter_title_3.html_pl-30-18), [31](#11_chapter_title_4.html_pl-43-31)

indentation, [4](#08_chapter_title_1.html_pl-16-4), *see* [layout rule](#24_index_title.html_ind24)

induction, [5](#08_chapter_title_1.html_pl-17-5), [142](#20_chapter_title_13.html_pl-154-142)

> hypothesis, [142](#20_chapter_title_13.html_pl-154-142)
> 
> on expressions, [151](#20_chapter_title_13.html_pl-163-151)
> 
> on lists, [145](#20_chapter_title_13.html_pl-157-145)
> 
> on numbers, [142](#20_chapter_title_13.html_pl-154-142), [144](#20_chapter_title_13.html_pl-156-144)
> 
> on trees, [149](#20_chapter_title_13.html_pl-161-149)

inequality, *see* [≠](#24_index_title.html_ind25)

infinity, [128](#19_chapter_title_12.html_pl-140-128), [142](#20_chapter_title_13.html_pl-154-142)

infix notation, [14](#09_chapter_title_2.html_pl-26-14)

*init*, [58](#13_chapter_title_6.html_pl-70-58), [162](#21_appendix_title.html_pl-174-162)

input/output, *see* [*IO*](#24_index_title.html_ind26)

**instance**, [111](#17_chapter_title_10.html_pl-123-111)

*Int*, [19](#10_chapter_title_3.html_pl-31-19), [159](#21_appendix_title.html_pl-171-159)

*Integer*, [19](#10_chapter_title_3.html_pl-31-19), [137](#19_chapter_title_12.html_pl-149-137), [159](#21_appendix_title.html_pl-171-159)

*Integral*, [27](#10_chapter_title_3.html_pl-39-27), [57](#13_chapter_title_6.html_pl-69-57), [157](#21_appendix_title.html_pl-169-157)

*intToDigit*, [159](#21_appendix_title.html_pl-171-159)

*IO*, [88](#16_chapter_title_9.html_pl-100-88), [164](#21_appendix_title.html_pl-176-164)

*isAlpha*, [78](#15_chapter_title_8.html_pl-90-78), [158](#21_appendix_title.html_pl-170-158)

*isAlphaNum*, [78](#15_chapter_title_8.html_pl-90-78), [158](#21_appendix_title.html_pl-170-158)

*isDigit*, [30](#11_chapter_title_4.html_pl-42-30), [78](#15_chapter_title_8.html_pl-90-78), [158](#21_appendix_title.html_pl-170-158)

*isLower*, [78](#15_chapter_title_8.html_pl-90-78), [158](#21_appendix_title.html_pl-170-158)

*isSpace*, [80](#15_chapter_title_8.html_pl-92-80), [158](#21_appendix_title.html_pl-170-158)

*isUpper*, [78](#15_chapter_title_8.html_pl-90-78), [158](#21_appendix_title.html_pl-170-158)

ISWIM, [6](#08_chapter_title_1.html_pl-18-6)

*iterate*, [70](#14_chapter_title_7.html_pl-82-70), [163](#21_appendix_title.html_pl-175-163)

keywords, [4](#08_chapter_title_1.html_pl-16-4), [15](#09_chapter_title_2.html_pl-27-15)

lambda calculus, [6](#08_chapter_title_1.html_pl-18-6), [36](#11_chapter_title_4.html_pl-48-36)

layout rule, [15](#09_chapter_title_2.html_pl-27-15), [77](#15_chapter_title_8.html_pl-89-77)

*length*, [12](#09_chapter_title_2.html_pl-24-12), [39](#12_chapter_title_5.html_pl-51-39), [50](#13_chapter_title_6.html_pl-62-50), [65](#14_chapter_title_7.html_pl-77-65), [67](#14_chapter_title_7.html_pl-79-67), [163](#21_appendix_title.html_pl-175-163)

lexicographic ordering, [25](#10_chapter_title_3.html_pl-37-25)

Lisp, [6](#08_chapter_title_1.html_pl-18-6)

lists, [4](#08_chapter_title_1.html_pl-16-4), [6](#08_chapter_title_1.html_pl-18-6), [11](#09_chapter_title_2.html_pl-23-11), [20](#10_chapter_title_3.html_pl-32-20), [38](#12_chapter_title_5.html_pl-50-38), [160](#21_appendix_title.html_pl-172-160)

> elements, [20](#10_chapter_title_3.html_pl-32-20), [33](#11_chapter_title_4.html_pl-45-33)
> 
> empty, *see* [[ ]](#24_index_title.html_ind27)
> 
> indexing, *see* [!!](#24_index_title.html_ind28)
> 
> infinite, [5](#08_chapter_title_1.html_pl-17-5), [20](#10_chapter_title_3.html_pl-32-20), [70](#14_chapter_title_7.html_pl-82-70), [131](#19_chapter_title_12.html_pl-143-131)
> 
> length, [20](#10_chapter_title_3.html_pl-32-20)
> 
> singleton, [20](#10_chapter_title_3.html_pl-32-20), [75](#15_chapter_title_8.html_pl-87-75), [118](#18_chapter_title_11.html_pl-130-118)
> 
> sorted, [7](#08_chapter_title_1.html_pl-19-7), [41](#12_chapter_title_5.html_pl-53-41), [51](#13_chapter_title_6.html_pl-63-51), [53](#13_chapter_title_6.html_pl-65-53), [60](#13_chapter_title_6.html_pl-72-60)

logical

> operators, *see* [∧](#24_index_title.html_ind8), [∨](#24_index_title.html_ind12), [¬](#24_index_title.html_ind29)
> 
> propositions, [105](#17_chapter_title_10.html_pl-117-105)
> 
> tautologies, [105](#17_chapter_title_10.html_pl-117-105)
> 
> values, *see* [*Bool*](#24_index_title.html_ind30)

lookup tables, [40](#12_chapter_title_5.html_pl-52-40), [100](#17_chapter_title_10.html_pl-112-100)

*map*, [62](#14_chapter_title_7.html_pl-74-62), [164](#21_appendix_title.html_pl-176-164)

*max*, [25](#10_chapter_title_3.html_pl-37-25), [156](#21_appendix_title.html_pl-168-156)

*maximum*, [163](#21_appendix_title.html_pl-175-163)

*Maybe*, [101](#17_chapter_title_10.html_pl-113-101), [160](#21_appendix_title.html_pl-172-160)

*min*, [25](#10_chapter_title_3.html_pl-37-25), [156](#21_appendix_title.html_pl-168-156)

*minimum*, [163](#21_appendix_title.html_pl-175-163)

Miranda, [6](#08_chapter_title_1.html_pl-18-6)

ML, [6](#08_chapter_title_1.html_pl-18-6)

*mod*, [27](#10_chapter_title_3.html_pl-39-27), [39](#12_chapter_title_5.html_pl-51-39), [43](#12_chapter_title_5.html_pl-55-43), [71](#14_chapter_title_7.html_pl-83-71), [134](#19_chapter_title_12.html_pl-146-134), [157](#21_appendix_title.html_pl-169-157)

*Monad*, [113](#17_chapter_title_10.html_pl-125-113), [157](#21_appendix_title.html_pl-169-157)

monads, [5](#08_chapter_title_1.html_pl-17-5), *see* [*Monad*](#24_index_title.html_ind31)

moving the cursor, [91](#16_chapter_title_9.html_pl-103-91)

multiplication, *see* [*](#24_index_title.html_ind32), [*product*](#24_index_title.html_ind33)

naming requirements, [14](#09_chapter_title_2.html_pl-26-14), [99](#17_chapter_title_10.html_pl-111-99), [100](#17_chapter_title_10.html_pl-112-100)

*negate*, [27](#10_chapter_title_3.html_pl-39-27), [157](#21_appendix_title.html_pl-169-157)

negation, *see* [¬](#24_index_title.html_ind29), [*negate*](#24_index_title.html_ind34)

*null*, [34](#11_chapter_title_4.html_pl-46-34), [58](#13_chapter_title_6.html_pl-70-58), [160](#21_appendix_title.html_pl-172-160)

*Num*, [7](#08_chapter_title_1.html_pl-19-7), [24](#10_chapter_title_3.html_pl-36-24), [27](#10_chapter_title_3.html_pl-39-27), [56](#13_chapter_title_6.html_pl-68-56), [157](#21_appendix_title.html_pl-169-157)

numbers, [159](#21_appendix_title.html_pl-171-159)

> binary, [69](#14_chapter_title_7.html_pl-81-69)
> 
> decimal, [69](#14_chapter_title_7.html_pl-81-69)
> 
> floating-point, *see* [*Float*](#24_index_title.html_ind35)
> 
> integer, *see* [*Int*](#24_index_title.html_ind36), [*Integer*](#24_index_title.html_ind37)
> 
> natural, [80](#15_chapter_title_8.html_pl-92-80), [82](#15_chapter_title_8.html_pl-94-82), [102](#17_chapter_title_10.html_pl-114-102), [142](#20_chapter_title_13.html_pl-154-142)
> 
> perfect, [46](#12_chapter_title_5.html_pl-58-46)
> 
> prime, [40](#12_chapter_title_5.html_pl-52-40), [133](#19_chapter_title_12.html_pl-145-133)
> 
> Unicode, [43](#12_chapter_title_5.html_pl-55-43), [71](#14_chapter_title_7.html_pl-83-71), [158](#21_appendix_title.html_pl-170-158)

*odd*, [53](#13_chapter_title_6.html_pl-65-53), [68](#14_chapter_title_7.html_pl-80-68), [159](#21_appendix_title.html_pl-171-159)

operators, [10](#09_chapter_title_2.html_pl-22-10), [36](#11_chapter_title_4.html_pl-48-36), [64](#14_chapter_title_7.html_pl-76-64), [66](#14_chapter_title_7.html_pl-78-66), [117](#18_chapter_title_11.html_pl-129-117)

*or*, [64](#14_chapter_title_7.html_pl-76-64), [67](#14_chapter_title_7.html_pl-79-67), [161](#21_appendix_title.html_pl-173-161)

*Ord*, [9](#08_chapter_title_1.html_pl-21-9), [25](#10_chapter_title_3.html_pl-37-25), [41](#12_chapter_title_5.html_pl-53-41), [51](#13_chapter_title_6.html_pl-63-51), [156](#21_appendix_title.html_pl-168-156)

*ord*, [43](#12_chapter_title_5.html_pl-55-43), [158](#21_appendix_title.html_pl-170-158)

*otherwise*, [31](#11_chapter_title_4.html_pl-43-31), [157](#21_appendix_title.html_pl-169-157)

overloading, [24](#10_chapter_title_3.html_pl-36-24)

parse trees, [82](#15_chapter_title_8.html_pl-94-82)

parsers, [74](#15_chapter_title_8.html_pl-86-74)

pattern matching, [5](#08_chapter_title_1.html_pl-17-5), [32](#11_chapter_title_4.html_pl-44-32), [55](#13_chapter_title_6.html_pl-67-55), [141](#20_chapter_title_13.html_pl-153-141)

patterns, [32](#11_chapter_title_4.html_pl-44-32)

> disjoint, [141](#20_chapter_title_13.html_pl-153-141)
> 
> integer, *see* *n* + *k*
> 
> list, [33](#11_chapter_title_4.html_pl-45-33), [49](#13_chapter_title_6.html_pl-61-49)
> 
> *n* + *k*, [34](#11_chapter_title_4.html_pl-46-34), [48](#13_chapter_title_6.html_pl-60-48), [58](#13_chapter_title_6.html_pl-70-58)
> 
> tuple, [33](#11_chapter_title_4.html_pl-45-33)
> 
> wildcard, *see* [_](#24_index_title.html_ind38)

polymorphism, [23](#10_chapter_title_3.html_pl-35-23)

predecessor, [34](#11_chapter_title_4.html_pl-46-34), [48](#13_chapter_title_6.html_pl-60-48), [54](#13_chapter_title_6.html_pl-66-54)

predicates, [63](#14_chapter_title_7.html_pl-75-63), [78](#15_chapter_title_8.html_pl-90-78)

*print*, [165](#21_appendix_title.html_pl-177-165)

priorities, [11](#09_chapter_title_2.html_pl-23-11), [13](#09_chapter_title_2.html_pl-25-13), [82](#15_chapter_title_8.html_pl-94-82)

*product*, [12](#09_chapter_title_2.html_pl-24-12), [49](#13_chapter_title_6.html_pl-61-49), [55](#13_chapter_title_6.html_pl-67-55), [64](#14_chapter_title_7.html_pl-76-64), [67](#14_chapter_title_7.html_pl-79-67), [163](#21_appendix_title.html_pl-175-163)

programming

> batch, [87](#16_chapter_title_9.html_pl-99-87)
> 
> functional, [2](#08_chapter_title_1.html_pl-14-2)
> 
> imperative, [3](#08_chapter_title_1.html_pl-15-3), [125](#19_chapter_title_12.html_pl-137-125)
> 
> interactive, [10](#09_chapter_title_2.html_pl-22-10), [87](#16_chapter_title_9.html_pl-99-87)
> 
> modular, [5](#08_chapter_title_1.html_pl-17-5), [133](#19_chapter_title_12.html_pl-145-133)

*putChar*, [89](#16_chapter_title_9.html_pl-101-89), [165](#21_appendix_title.html_pl-177-165)

*putStr*, [90](#16_chapter_title_9.html_pl-102-90), [165](#21_appendix_title.html_pl-177-165)

*putStrLn*, [90](#16_chapter_title_9.html_pl-102-90), [165](#21_appendix_title.html_pl-177-165)

*Read*, [26](#10_chapter_title_3.html_pl-38-26), [156](#21_appendix_title.html_pl-168-156)

*read*, [26](#10_chapter_title_3.html_pl-38-26), [156](#21_appendix_title.html_pl-168-156)

*readLn*, [165](#21_appendix_title.html_pl-177-165)

*recip*, [28](#10_chapter_title_3.html_pl-40-28), [30](#11_chapter_title_4.html_pl-42-30), [157](#21_appendix_title.html_pl-169-157)

reciprocation, [36](#11_chapter_title_4.html_pl-48-36), *see* [*recip*](#24_index_title.html_ind39)

recursion, [5](#08_chapter_title_1.html_pl-17-5), [48](#13_chapter_title_6.html_pl-60-48)

> multiple, [53](#13_chapter_title_6.html_pl-65-53)
> 
> mutual, [53](#13_chapter_title_6.html_pl-65-53), [80](#15_chapter_title_8.html_pl-92-80), [110](#17_chapter_title_10.html_pl-122-110)

redex, [125](#19_chapter_title_12.html_pl-137-125)

reduction, [125](#19_chapter_title_12.html_pl-137-125)

> under lambdas, [127](#19_chapter_title_12.html_pl-139-127)

remainder, *see* [*mod*](#24_index_title.html_ind40)

*repeat*, [71](#14_chapter_title_7.html_pl-83-71), [163](#21_appendix_title.html_pl-175-163)

*replicate*, [144](#20_chapter_title_13.html_pl-156-144), [163](#21_appendix_title.html_pl-175-163)

reserved words, [15](#09_chapter_title_2.html_pl-27-15)

*return*, [75](#15_chapter_title_8.html_pl-87-75), [89](#16_chapter_title_9.html_pl-101-89), [113](#17_chapter_title_10.html_pl-125-113), [157](#21_appendix_title.html_pl-169-157)

*reverse*, [12](#09_chapter_title_2.html_pl-24-12), [50](#13_chapter_title_6.html_pl-62-50), [65](#14_chapter_title_7.html_pl-77-65), [67](#14_chapter_title_7.html_pl-79-67), [145](#20_chapter_title_13.html_pl-157-145), [147](#20_chapter_title_13.html_pl-159-147), [164](#21_appendix_title.html_pl-176-164)

rounding errors, [19](#10_chapter_title_3.html_pl-31-19)

scalar product, [47](#12_chapter_title_5.html_pl-59-47)

scripts, [13](#09_chapter_title_2.html_pl-25-13)

sections, [36](#11_chapter_title_4.html_pl-48-36), [65](#14_chapter_title_7.html_pl-77-65)

sequencing, *see* [>>=](#24_index_title.html_ind41)

sharing, [130](#19_chapter_title_12.html_pl-142-130)

*Show*, [26](#10_chapter_title_3.html_pl-38-26), [156](#21_appendix_title.html_pl-168-156)

*show*, [26](#10_chapter_title_3.html_pl-38-26), [156](#21_appendix_title.html_pl-168-156)

side effects, [5](#08_chapter_title_1.html_pl-17-5), [87](#16_chapter_title_9.html_pl-99-87)

sign, *see* [*signum*](#24_index_title.html_ind42)

*signum*, [27](#10_chapter_title_3.html_pl-39-27), [31](#11_chapter_title_4.html_pl-43-31), [157](#21_appendix_title.html_pl-169-157)

*snd*, [33](#11_chapter_title_4.html_pl-45-33), [160](#21_appendix_title.html_pl-172-160)

sorting

> insertion sort, [52](#13_chapter_title_6.html_pl-64-52)
> 
> merge sort, [60](#13_chapter_title_6.html_pl-72-60)
> 
> quicksort, [7](#08_chapter_title_1.html_pl-19-7), [53](#13_chapter_title_6.html_pl-65-53)

sounding a beep, [91](#16_chapter_title_9.html_pl-103-91)

spacing, [81](#15_chapter_title_8.html_pl-93-81)

*span*, [162](#21_appendix_title.html_pl-174-162)

*splitAt*, [30](#11_chapter_title_4.html_pl-42-30), [162](#21_appendix_title.html_pl-174-162)

stacks, [150](#20_chapter_title_13.html_pl-162-150)

> control, [109](#17_chapter_title_10.html_pl-121-109)
> 
> underflow, [153](#20_chapter_title_13.html_pl-165-153)

standard prelude, [10](#09_chapter_title_2.html_pl-22-10), [156](#21_appendix_title.html_pl-168-156)

state of the world, [88](#16_chapter_title_9.html_pl-100-88)

*String*, [19](#10_chapter_title_3.html_pl-31-19), [158](#21_appendix_title.html_pl-170-158)

strings, *see* [*String*](#24_index_title.html_ind43)

subtraction, *see* [−](#24_index_title.html_ind44)

successor, [36](#11_chapter_title_4.html_pl-48-36), [102](#17_chapter_title_10.html_pl-114-102), [128](#19_chapter_title_12.html_pl-140-128)

*sum*, [6](#08_chapter_title_1.html_pl-18-6), [12](#09_chapter_title_2.html_pl-24-12), [64](#14_chapter_title_7.html_pl-76-64), [66](#14_chapter_title_7.html_pl-78-66), [67](#14_chapter_title_7.html_pl-79-67), [163](#21_appendix_title.html_pl-175-163)

symbol table, [166](#22_conclusion_title.html_pl-178-166)

*tail*, [11](#09_chapter_title_2.html_pl-23-11), [34](#11_chapter_title_4.html_pl-46-34), [161](#21_appendix_title.html_pl-173-161)

*take*, [11](#09_chapter_title_2.html_pl-23-11), [132](#19_chapter_title_12.html_pl-144-132), [161](#21_appendix_title.html_pl-173-161)

*takeWhile*, [64](#14_chapter_title_7.html_pl-76-64), [161](#21_appendix_title.html_pl-173-161)

termination, [2](#08_chapter_title_1.html_pl-14-2), [5](#08_chapter_title_1.html_pl-17-5), [128](#19_chapter_title_12.html_pl-140-128), [131](#19_chapter_title_12.html_pl-143-131)

tokens, [81](#15_chapter_title_8.html_pl-93-81)

*toLower*, [159](#21_appendix_title.html_pl-171-159)

*toUpper*, [159](#21_appendix_title.html_pl-171-159)

*True*, [17](#10_chapter_title_3.html_pl-29-17), [18](#10_chapter_title_3.html_pl-30-18)

truth tables, [105](#17_chapter_title_10.html_pl-117-105)

tuples, [20](#10_chapter_title_3.html_pl-32-20), [160](#21_appendix_title.html_pl-172-160)

> arity, [20](#10_chapter_title_3.html_pl-32-20), [33](#11_chapter_title_4.html_pl-45-33)
> 
> components, [20](#10_chapter_title_3.html_pl-32-20), [33](#11_chapter_title_4.html_pl-45-33)
> 
> empty, *see* [()](#24_index_title.html_ind45)
> 
> pairs, [20](#10_chapter_title_3.html_pl-32-20), [38](#12_chapter_title_5.html_pl-50-38), [41](#12_chapter_title_5.html_pl-53-41), [160](#21_appendix_title.html_pl-172-160)
> 
> triples, [20](#10_chapter_title_3.html_pl-32-20), [160](#21_appendix_title.html_pl-172-160)

type

> constructors, [100](#17_chapter_title_10.html_pl-112-100)
> 
> declarations, [99](#17_chapter_title_10.html_pl-111-99), [100](#17_chapter_title_10.html_pl-112-100)
> 
> errors, [18](#10_chapter_title_3.html_pl-30-18)
> 
> inference, [4](#08_chapter_title_1.html_pl-16-4), [7](#08_chapter_title_1.html_pl-19-7), [17](#10_chapter_title_3.html_pl-29-17)
> 
> parameters, [100](#17_chapter_title_10.html_pl-112-100), [101](#17_chapter_title_10.html_pl-113-101)
> 
> safety, [18](#10_chapter_title_3.html_pl-30-18)
> 
> variables, [23](#10_chapter_title_3.html_pl-35-23)

**type**, [99](#17_chapter_title_10.html_pl-111-99)

types, [4](#08_chapter_title_1.html_pl-16-4), [7](#08_chapter_title_1.html_pl-19-7), [17](#10_chapter_title_3.html_pl-29-17)

> basic, [18](#10_chapter_title_3.html_pl-30-18)
> 
> equality, *see* [*Eq*](#24_index_title.html_ind46)
> 
> fractional, *see* [*Fractional*](#24_index_title.html_ind47)
> 
> function, [21](#10_chapter_title_3.html_pl-33-21)
> 
> integral, *see* [*Integral*](#24_index_title.html_ind48)
> 
> list, [20](#10_chapter_title_3.html_pl-32-20), [103](#17_chapter_title_10.html_pl-115-103), [160](#21_appendix_title.html_pl-172-160)
> 
> maybe, *see* [*Maybe*](#24_index_title.html_ind49)
> 
> monadic, *see* [*Monad*](#24_index_title.html_ind31)
> 
> numeric, *see* [*Num*](#24_index_title.html_ind50)
> 
> ordered, *see* [*Ord*](#24_index_title.html_ind51)
> 
> overloaded, [24](#10_chapter_title_3.html_pl-36-24)
> 
> parameterised, [100](#17_chapter_title_10.html_pl-112-100), [101](#17_chapter_title_10.html_pl-113-101)
> 
> polymorphic, [23](#10_chapter_title_3.html_pl-35-23)
> 
> readable, *see* [*Read*](#24_index_title.html_ind52)
> 
> recursive, [102](#17_chapter_title_10.html_pl-114-102)
> 
> showable, *see* [*Show*](#24_index_title.html_ind53)
> 
> tree, [103](#17_chapter_title_10.html_pl-115-103), [138](#19_chapter_title_12.html_pl-150-138), [149](#20_chapter_title_13.html_pl-161-149)
> 
> tuple, [20](#10_chapter_title_3.html_pl-32-20)

*uncurry*, [164](#21_appendix_title.html_pl-176-164)

*unfold*, [73](#14_chapter_title_7.html_pl-85-73)

**where**, [15](#09_chapter_title_2.html_pl-27-15)

*zip*, [40](#12_chapter_title_5.html_pl-52-40), [52](#13_chapter_title_6.html_pl-64-52), [163](#21_appendix_title.html_pl-175-163)

zipper, [114](#17_chapter_title_10.html_pl-126-114)