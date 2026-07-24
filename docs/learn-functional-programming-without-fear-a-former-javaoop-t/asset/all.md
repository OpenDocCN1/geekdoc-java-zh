![](cover.jpeg)

# Learn Functional Programming *Without Fear*

A former Java/OOP teacher
takes you to the cusp of using
Scalaâ€™s FP libraries, in a small book.Alvin Alexander

# Table of Contents

*   [Copyright](#index_split_002.html_filepos5654)

*   [The Goal of This Book](#index_split_005.html_filepos8544)

*   [About Me](#index_split_007.html_filepos11456)

*   [Welcome!](#index_split_008.html_filepos13354)

*   [Contents and Outline](#index_split_014.html_filepos19365)

*   [A Look at Java/OOP Code and Data Types](#index_split_017.html_filepos23176)

*   [Java/OOP Summary](#index_split_019.html_filepos30253)

*   [Is Java/OOP Code That Simple? A Statistical Look](#index_split_022.html_filepos35023)

*   [My Path to Learning Scala](#index_split_024.html_filepos37969)

*   [JIT: Immutable Things](#index_split_026.html_filepos43115)

*   [JIT: Pure Functions](#index_split_029.html_filepos48404)

*   [JIT: I Love Pure Functions, They Cannot Lie](#index_split_031.html_filepos54186)

*   [JIT: Expression-Oriented Programming (EOP)](#index_split_036.html_filepos63787)

*   [Example #1: Solving Problems with Pure Functions and EOP](#index_split_043.html_filepos75958)

*   [One More Thing: Algebraic Substitution](#index_split_059.html_filepos104505)

*   [A Quick Look at Parallel Programming](#index_split_062.html_filepos118975)

*   [Recap: Java/OOP vs Pure Functions](#index_split_066.html_filepos131427)

*   [A Change To The wc Application](#index_split_069.html_filepos135858)

*   [Functional Error Handling (FEH)](#index_split_070.html_filepos137246)

*   [FEH: Option](#index_split_073.html_filepos146094)

*   [FEH: Try](#index_split_081.html_filepos162116)

*   [FEH: Either](#index_split_086.html_filepos173208)

*   [FEH: allCatch](#index_split_092.html_filepos185240)

*   [FEH: Implementing wc with Try](#index_split_095.html_filepos188177)

*   [Recap, and Whatâ€™s Next](#index_split_100.html_filepos206298)

*   [Example #2: To-Do List (TDL)](#index_split_101.html_filepos207081)

*   [TDL: The Database Class](#index_split_105.html_filepos213190)

*   [TDL: The insert Database Function](#index_split_109.html_filepos218808)

*   [TDL: The selectAll Database Function](#index_split_113.html_filepos231168)

*   [TDL: The delete Database Function](#index_split_114.html_filepos235073)

*   [TDL UI: Prompt The User](#index_split_118.html_filepos250407)

*   [TDL UI: Read Input](#index_split_123.html_filepos257129)

*   [TDL UI: Show Help](#index_split_124.html_filepos260053)

*   [JIT: Using Option and Try in for-Expressions](#index_split_126.html_filepos263953)

*   [JIT: for Loops, Generators, and Guards](#index_split_129.html_filepos269833)

*   [JIT: Code Blocks (Closures)](#index_split_133.html_filepos274978)

*   [JIT: Recursion](#index_split_134.html_filepos278181)

*   [TDL UI: Handling User Input](#index_split_138.html_filepos289755)

*   [An InputProcessor Class](#index_split_146.html_filepos306104)

*   [TDL UI: Implementing handleUserInput](#index_split_148.html_filepos310291)

*   [TDL UI: Handling â€œQuitâ€](#index_split_151.html_filepos320216)

*   [TDL UI: Handling â€œHelpâ€](#index_split_153.html_filepos322069)

*   [TDL UI: Handling â€œViewâ€](#index_split_154.html_filepos323630)

*   [TDL UI: Handling â€œAddâ€](#index_split_155.html_filepos328350)

*   [TDL UI: Handling â€œDeleteâ€](#index_split_157.html_filepos335553)

*   [TDL UI: Handling the Catch-All Case](#index_split_161.html_filepos344440)

*   [Running the To-Do List App](#index_split_164.html_filepos349765)

*   [TDL: Lessons Learned](#index_split_165.html_filepos350944)

*   [TDL: Using Either Instead of Try](#index_split_169.html_filepos356037)

*   [How Either Relates to ZIO](#index_split_175.html_filepos367944)

*   [JIT: Whatâ€™s an IO?](#index_split_177.html_filepos373183)

*   [JIT: IO and Algebraic Substitution](#index_split_180.html_filepos377147)

*   [JIT: IO, Option, Try, Either, and for-Expressions](#index_split_185.html_filepos388234)

*   [ZIO and the Power of IOs](#index_split_188.html_filepos394455)

*   [Bonus: The Mindset of an FPer](#index_split_198.html_filepos430080)

*   [Bonus: The M Word](#index_split_200.html_filepos433292)

*   [Scala 3 Cheatsheet](#index_split_204.html_filepos439823)

*   [The Scala REPL](#index_split_221.html_filepos475863)

*   [Scala CLI (Compiling and Running Code)](#index_split_223.html_filepos480519)

*   [Classes That Use Generic Types](#index_split_228.html_filepos488313)

*   [Functions That Use Generic Types](#index_split_230.html_filepos495749)

*   [A Quick Look at Variance and Bounds](#index_split_231.html_filepos499826)

*   [File I/O with â€˜Usingâ€™](#index_split_234.html_filepos505239)

*   [â€œCall By-Nameâ€ Parameters (and Multiple Parameter Groups)](#index_split_238.html_filepos512586)

*   [Glossary](#index_split_246.html_filepos528831)

# Copyright

**Learn Functional Programming *Without Fear***

Copyright 2022 [Alvin J. Alexander](https://alvinalexander.com)

All rights reserved. No part of this book may be reproduced without prior written permission from the author.

This book is presented solely for educational purposes. While best efforts have been made to prepare this book, the author makes no representations or warranties of any kind and assumes no liabilities of any kind with respect to the accuracy or completeness of the contents, and specifically disclaims any implied warranties of merchantability or fitness of use for a particular purpose. The author shall not be held liable or responsible to any person or entity with respect to any loss or incidental or consequential damages caused, or alleged to have been caused, directly or indirectly, by the information or programs contained herein. Any use of this information is at your own risk.

Version 1.0, published November 5, 2022

Buy the book and find/report issues: [alvinalexander.com/scala/learn-functional-programming-book](https://alvinalexander.com/scala/learn-functional-programming-book)

## Other books

Other books by Alvin Alexander:

*   The [Scala Cookbook](https://amzn.to/3du1pMR) (700+ pages)
*   The best-selling and highly-rated book,
    [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book) (also 700+ pages)
*   My latest book, [Learn Scala 3 The Fast Way!](https://amzn.to/3L4YwR4)

## Gratitude

I want to express my thanks to everyone who has made Scala such a wonderful programming language. It has been a fun language to write about.

I also want to express my thanks for Sriram Natarajan, who volunteered three pages of terrific comments on an early release of this book.

I also want to thank my wife, because at the very least, without her support, this book would absolutely not be possible.

Finally, I should thank all the friends and family that keep me grounded. If it wasnâ€™t for you, I might still be meditating in the mountains of Alaska. :)

# 1\. The Goal of This Book

This book has an audacious goal: To demonstrate â€” as simply as possible â€” the benefits of:

*   Immutable variables (algebraic variables)
*   Immutable data structures
*   Pure functions
*   Expression-oriented programming
*   Functional error handling

This bookâ€™s premise is that once youâ€™re comfortable with these concepts, youâ€™ll find that youâ€™re writing functional programming (FP) code. At the end of the book I demonstrate this by showing several examples using *ZIO*, which is one of Scalaâ€™s two main FP libraries (along with *Cats Effect*).

Put more clearly: This book gets you ready to start using ZIO and Cats Effect. When you finish this book, you should be able to look at their documentation and think, â€œAh, yes, I know *what* theyâ€™re doing, and *why* theyâ€™re doing it.â€

## For OOP developers: Java, Kotlin, Python, and more

Furthermore, Iâ€™ve written the book especially for people with a background in object-oriented programming (OOP). I taught Java and OOP courses for many years, and still write mostly-OOP code for iPhone and Android apps (using Flutter/Dart and Kotlin, respectively), so Iâ€™m very familiar with OOP, and what OOP developers need to know to learn FP.

Having worked with Java, Kotlin, Swift, Python, C++, Dart, and Ruby, I believe this book will be helpful to developers who use those languages, and are interested in learning FP.

I accomplish this goal in under 250 pages by focusing on how to write a few small applications with the five main concepts just mentioned, explaining those concepts as we go along.

> This is intentionally a small, hopefully easy-to-read book about FP. If youâ€™d rather read a large, detailed book on FP, I wrote the best-selling and highly-rated [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book), which is over 720 pages long. While itâ€™s much longer, the benefit of that book is that it *does* cover a lot of background information and fine details, in the form of over 100 short lessons. (To be clear, the *Print* version of that book is 720+ pages long, but the PDF and Kindle electronic versions are over 1,000 pages long.)

# 2\. About Me

For those who donâ€™t know me, my name is Alvin Alexander, and this is my Java, OOP, Kotlin, Scala, and FP background:

*   Back in the day I taught C, Java, and OOP courses to clients like GE, UPS, Papa Johns, and many others
*   I founded a little software consulting firm that we grew to 20 employees, and we primarily wrote Java/OOP code for our clients
*   I wrote two editions of the [Scala Cookbook](https://amzn.to/3du1pMR), most recently the 2nd Edition, which was released in September, 2021 (700+ pages each)
*   I wrote the best-selling and highly-rated book, [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book) (also 700+ pages)
*   I wrote a book named â€œHello, Scala,â€ which became the basis for the â€œScala Bookâ€ on the official Scala website
*   I then co-wrote the [Scala 3 Book](https://docs.scala-lang.org/scala3/book/introduction.html) for the official Scala website
*   In 2022 I released a book named [Learn Scala 3 The Fast Way!](https://amzn.to/3L4YwR4)
*   Iâ€™ve written Android apps with Java and Kotlin, and cross-platform iOS/Android apps with Flutter and Dart
*   My website about programming, [alvinalexander.com](https://alvinalexander.com), receives millions of page-views every year

I mention the page counts for some of those books because for me, this is a short book. I intentionally made it as concise as possible, while also writing it in a simple, conversational style, as if I was working right next to you, or mentoring you in a classroom.

# 3\. Welcome!

Welcome! This is a really different book for me. My *initial plan* was to create a small booklet that I was going to title â€œThinking with Typesâ€ or â€œSolving Problems with Pure Functions.â€ The idea was to show how you can write really solid, readable, maintable code using these programming techniques:

*   Pure functions
*   Immutable variables (*algebraic* variables)
*   Immutable data types (such as `String` and `List`)
*   Expression-oriented programming (EOP)
*   Functional error-handling

But then as I started working on the outline and examples, I realized how close this code is to writing pure *functional programming* (FP) code. At that point I switched from writing a booklet to trying to write the smallest possible book I can that takes OOP developers to the precipice of using Scalaâ€™s FP libraries.

So even though this is a relatively small book, I hope it delivers a tremendous amount of value by taking you so far down the road to FP. My hope is that when you finish this book, youâ€™ll be able to go right to the ZIO and Cats Effect documentation and think, â€œOh, I know *what* theyâ€™re doing, and *why* theyâ€™re doing it.â€

## Who this book is for

I wrote this book for OOP developers, but itâ€™s really for anyone who:

*   Is interested in the programming concepts listed above
*   Is just starting to work with those concepts
*   Has gotten into FP a little, and finds it hopelessly confusing
*   Is otherwise interested in improving their code

Note that the code examples in this book are written using *Scala 3*, but I donâ€™t use any â€œScala magic tricks.â€ The code is written in a simple style, as youâ€™ll soon see.

## What I assume you know

For the purposes of this book I assume that you know a little bit about Scala, but as a practical matter, the basics of Scala are very straightforward, and I think youâ€™ll do pretty well if you know another language like Java, Kotlin, Python, Swift, Dart, C++, or other languages. As I mentioned, I donâ€™t use any fancy Scala techniques in this book.

If you donâ€™t know the basics of Scala:

*   This book includes a *Scala 3 cheat sheet* in the Appendix.
*   My book, [Learn Scala 3 The Fast Way! (Book 1: The Adventure Begins)](https://amzn.to/3L4YwR4), gets you up and running fast.
*   I wrote most of the [Scala 3 Book](https://docs.scala-lang.org/scala3/book/introduction.html) on the official Scala website, and hopefully itâ€™s a terrific, free resource.

I also wrote the initial versions of these free resources on the official Scala website:

*   [Scala for Java Developers](https://docs.scala-lang.org/scala3/book/scala-for-java-devs.html)
*   [Scala for Python Developers](https://docs.scala-lang.org/scala3/book/scala-for-python-devs.html)
*   [Scala for JavaScript Developers](https://docs.scala-lang.org/scala3/book/scala-for-javascript-devs.html)

## A word of caution

One thing Iâ€™ve learned about FP is that when you write *small applications*, the techniques can seem like overkill, and you might be tempted to dismiss it.

BUT, when you write *large applications* on teams with other developers, youâ€™ll be extremely grateful for those same techniques.

## A few terms

Before we get into the book, here are a few technical terms that Iâ€™ll use from time to time:

*   I often refer to *pure functions*, and thereâ€™s a chapter on those.
*   I use the term *Expression-Oriented Programming*, or EOP. This just means that weâ€™ll be programming with *expressions* rather than *statements*. Thereâ€™s also a chapter on EOP.
*   *Immutable variables* sounds like an oxymoron, but this just means â€œvariables in the algebraic sense.â€ Thereâ€™s a chapter on these.
*   *Java/OOP* refers to programming in an OOP style with Java.
*   *Scala/OOP* refers to programming in an OOP style with Scala.
*   *Scala/EOP* refers to programming in an EOP style with Scala.
*   *Scala/FP* refers to programming in an FP style with Scala.

## Source code and bug reports

If you find any bugs/issues in this book, please report them as an issue at this bookâ€™s Github repository:

*   [github.com/alvinj/LearnFunctionalProgrammingBook](https://github.com/alvinj/LearnFunctionalProgrammingBook)

Youâ€™ll find the bookâ€™s source code examples in that repository as well.

All reports are welcome!

# 4\. Contents and Outline

Here are a few notes about this bookâ€™s table of contents and its outline.

## Table of contents

First, I want to mention that a bookâ€™s *table of contents* is important to me. When Iâ€™m reading a tech book, thatâ€™s often where I look to find things quickly, and as a result I use some naming standards for the chapters in this book:

*   **JIT**: A chapter that starts with *JIT* means that this is a â€œjust in timeâ€ chapter. That means Iâ€™m introducing a tidbit of knowledge that is important for your understanding of a chapter that follows.
*   **FEH**: I also use the unusual (non-standard) acronym *FEH* to refer to the term, â€œfunctional error-handling.â€
*   **TDL**: A chapter that starts with *TDL* means that the chapter is related to the *To-Do List* application.

## Outline

Next, if you want to know what youâ€™re about to get into in the rest of this book, read the following outline, which is something of a map of the following territory.

Conversely, if you DONâ€™T want to know what weâ€™re about to get into and you prefer it to be a surprise, please skip the rest of this chapter.

The outline goes a little like this:

*   I start by looking at how little I used to use data types in Java/OOP
*   Then I look at how much I *do* use them in Scala/OOP and Scala/EOP

After that I show:

*   Using data types isnâ€™t a bad thing, and in fact, itâ€™s a very good thing
*   The importance of immutable things (variables and data structures)
*   The importance of pure functions: specifically that you can trust them, because they cannot lie
*   That the concepts of immutable things and pure functions naturally lead to EOP

Then I show how to write a *Word Count* application with these concepts. As we go through that application weâ€™ll discover a few other things.

After that, I do a little recap of Java/OOP code compared to the Scala/EOP code you saw in the Word Count example.

After this we jump into the next important topic, functional error-handling:

*   I explain the reasoning behind functional error-handling
*   We look at Scalaâ€™s three *error-handling data types*: `Option`, `Try`, and `Either`
*   I show how to implement the Word Count application using `Try`
*   Then we build a larger *To-Do List* application, using all of these concepts
*   This application uses a simulated database, so you see the techniques youâ€™ll use when accessing a remote database or REST API

And at the end I show just *how close you are* to using FP libraries like ZIO and Cats Effect.

And now, if youâ€™re ready, letâ€™s get started!

# 5\. A Look at Java/OOP Code and Data Types

Back in my Java programming days I rarely used generic data types, and in fact, I rarely thought about data types much at all. To demonstrate why, Iâ€™ll go back to one of my common examples, writing a point-of-sales application for a pizza store.

Two points before we move on:

*   A *generic* type in Java and Scala is typically a character like `T` or `A` thatâ€™s used in a method declaration. You use a generic type to say, â€œThe exact type used here will be filled in later.â€ For instance, a `List[A]` in Scala may later be a `List[Int]`, `List[String]`, etc. I write more about generic types as this book goes on.
*   In these examples, please note that my Java code may not be 100% correct. I havenâ€™t put this code in an IDE or tried to compile it. Because I assume that you know Java or other OOP languages, my intent is to just quickly demonstrate the Java/OOP approach I used for many years.

## Modeling a pizza store application

### Some enums

To start modeling a point-of-sales application for a pizza store, Iâ€™ll first need my usual enumerations:

`enum Topping {`
`    Cheese,`
`    Pepperoni,`
`    BlackOlives`
`}`

`enum CrustSize {`
`    Small,`
`    Medium,`
`    Large`
`}`

`enum CrustType {`
`    Regular,`
`    Thin,`
`    Thick`
`}`

### A pizza class

Given those, letâ€™s create a `Pizza` class. But before doing that, letâ€™s list the attributes and behaviors of an OOP pizza. The attributes are basically what I listed with those enums:

*   Crust size
*   Crust type
*   Types of toppings

The behaviors correspond to those attributes:

*   Add topping
*   Remove topping
*   Set crust size
*   Set crust type

If I also kept price-related information, a pizza could also calculate its own price, but since the toppings and crust attributes donâ€™t carry price information with them, thatâ€™s pretty much all of the behaviors of this `Pizza`.

Having gone through this exercise several times before, I know that I want all of the food-related items in a pizza store â€” pizza, breadsticks, soda, etc. â€” to extend a base `Product` class:

`public interface Product {}`

In the real world, a `Product` will have attributes like cost, and potentially a sales price, but for the purposes of this exercise Iâ€™ll just leave it as a marker interface like that.

Given this `Product` â€” and the attributes and behaviors of my `Pizza` â€” the initial code for a Java/OOP `Pizza` class looks like this:

`public class Pizza implements Product {`

`    private List<Topping> toppings = new ArrayList<>();`
`    private CrustSize crustSize;`
`    private CrustType crustType;`

`    public Pizza(CrustSize crustSize, CrustType crustType) {`
`        this.crustSize = crustSize;`
`        this.crustType = crustType;`
`    }`

`}`

That `Pizza` class will then include the following series of getter and setter methods, with these type signatures:

`public CrustSize getCrustSize()`
`public CrustType getCrustType()`
`public List<Topping> getToppings()`

`public void setCrustSize(CrustSize crustSize)`
`public void setCrustType(CrustType crustType)`
`public void setToppings(List<Topping> toppings)`

> The term *type signature* refers to a functionâ€™s (a) input parameters and (b) return type.

### Discussion

The thing to notice here is that this is all simple code. The getters donâ€™t take any input parameters and they return basic data types, and the setters all return `void`. I wrote Java code like this for more than 12 years.

In fact, if I wrote more code, such as for an `Order` class, youâ€™d see that the pattern is the same, all very simple code:

`public class Order {`

`    private List<Product> lineItems = new ArrayList<>();`
`    public Order() {}`

`    public void addItem(Product p)`
`    public void removeItem(Product p)`
`    public List<Product> getItems()`

`    public String getPrintableReceipt()`
`    public BigDecimal getTotalPrice()`

`}`

The closest I get to using generic types in that code are these types:

`List<Topping>`
`List<Product>`

# 6\. Java/OOP Summary

So that was a quick look at a little Java/OOP code that I used to use when teaching Java courses. Of course I didnâ€™t show much; just enough to get the basic idea across.

## Summary, Part 1

To summarize what you saw in that code:

*   My Java/OOP code was simple, with no generic types
*   A lot of methods return `void`
*   A lot of methods have no input parameters
*   I *always* use mutable data structures

*Mutable* data structures are structures like the Java `ArrayList`, which can be resized, and whose elements can be updated. We say that a structure like this can be *mutated*, which just means â€œchanged.â€

## Summary, Part 2

There are a few other things to say about that code, and bear in mind, Iâ€™m only talking about my own code.

**POINT 1:** I didnâ€™t realize it when I was writing Java/OOP code, but all of those methods that return `void` and take no input parameters tend to warp your brain. You canâ€™t tell what the methods do by looking at their type signatures, so you either (a) trust that the methods are well-named, or (b) you have to look at their source code to see what they do.

As an example of what I mean, *I trusted my own code* because I knew that all of my getters and setters were just boilerplate code. But one time when I was debugging a problem with a junior developer, I found that he wrote a setter method like this:

`public void setFoo(Foo newFoo) {`
`    openTheGarageDoor();`
`    walkTheDog();`
`    buyGroceries();`
`    solveWorldPeace();`
`    this.foo = newFoo + 1;`
`}`

It wasnâ€™t quite that exhaustive, but there was a *lot* going on in there. And bear in mind, all of that happened inside a â€œsimple setter methodâ€ with this type signature:

`public void setFoo(Foo newFoo)`

The lessons I took away from that were:

*   This developer needed some more training
*   I couldnâ€™t trust method type signatures, I had to look at their code

**POINT 2:** A second point that I donâ€™t show in my pizza example is that many Java methods can throw exceptions, and when they can, you have to think about (a) handling the â€œsuccessâ€ case, and (b) handling the â€œfailureâ€ case, which for me meant wrapping the method call with `try`/`catch`.

This gets to be ridiculously hard on the brain, so I got to the point that â€” using the Model/View/Controller (MVC) paradigm â€” I only handled exceptions with my top-level controllers. I logged exceptions at the point they occurred, but then just let them bubble up to my controllers, and handled them there.

At that time I didnâ€™t know anything about functional programming, and I couldnâ€™t think of a better way to deal with potential errors â€” invalid data, servers being down, etc. â€” so thatâ€™s how I dealt with exceptions.

For more details on my MVC approach, see my blog posts:

*   [A terrific MVC diagram](https://alvinalexander.com/uml/uml-model-view-controller-mvc-diagram/)
*   [Model/View/Controller definitions and examples](https://alvinalexander.com/uml/model-view-controller-mvc-definitions-examples/)
*   [A Java Model View Controller example](https://alvinalexander.com/ooa-ood/java-model-view-controller-mvc-example-1/)

# 7\. Is Java/OOP Code That Simple? A Statistical Look

As I write this book, I havenâ€™t actually written Java code in quite some time now, and knowing that my memory isnâ€™t always accurate, I wondered, â€œWas my code really that simple?â€

To verify everything I just shared with you, I searched three old Java codebases â€” all projects that were in production in their day. I just did a simple search for the `<.*>` pattern â€” to find any data types like `<String>`, `<String, Integer>`, etc. â€” and found these percentages of occurrences within `*.java` files in those three projects:

`USAGE %    LINES FOUND    TOTAL NUMBER OF LINES`
`-------    -----------    ---------------------`
`  0.2         118                74,200`
`  1.4         686                49,189`
`  1.2         313                27,083      `

So out of about 150,000 lines of Java/OOP code, there are 1,117 lines with a `<.*>` pattern, for a total percentage of 0.74%. (Note that those line-count numbers include blanks lines and comment lines, so the actual percentages are higher.)

I then manually looked through all of those `<.*>` lines of output, and found that these were the two most difficult lines to read:

`SortedMap<String, Integer> wordCountMap = new TreeMap();`
`public Class<?> getColumnClass(int columnIndex) {`

## Coming soon â€¦

So, without any further comment at this point, thatâ€™s a look at using data types in some Java/OOP code.

In just a few chapters weâ€™ll start looking at some Scala code â€” specifically how to solve problems with Scala and pure functions. But before we get to that, I need to introduce a wee bit of background material that will help that approach make sense.

# 8\. My Path to Learning Scala

Before we jump into some Scala code, itâ€™s important to mention how I learned Scala. My timeline looked like this:

I had taught Java and OOP classes for several years. I owned a small consulting company, and we wrote Java/OOP code for most of our clients, and provided training and mentoring services to them as well.

Out of personal curiosity, I started learning a little Python, and even more Ruby. I liked Ruby (and Ruby on Rails), and then really loved JRuby, which let me use Java libraries while writing Ruby code.

Then a friend showed me the [Learn You a Haskell for Great Good!](http://amzn.to/1POaUCv) book, but after the basic intro stuff in that book, I had no idea what the author was talking about. Things like [typeclasses](https://docs.scala-lang.org/scala3/book/types-type-classes.html) totally eluded me, and I gave up on FP as anything other than a curiosity.

In late 2010 I had sold my company and was wandering around Alaska, and discovered Scala. Not knowing any better, I started using it as a â€œbetter Javaâ€, meaning that I wrote OOP code with Scala (i.e., Scala/OOP).

I also spent a lot of time trying to use the Java collections classes in Scala, which was a *horrible* waste of time. Not because you canâ€™t use them â€” you can â€” but if you do that, youâ€™re not embracing the style and best practices that Scala brings to the table.

> Itâ€™s like the time a friend started working with Java, and having a background in Visual Basic, he tried to write VB code in Java. You do something that because youâ€™re *comfortable* with VB, but youâ€™re not embracing Java; youâ€™re just writing VB code with Javaâ€™s language constructs.

As time went on I found the book, [Programming in Scala](https://amzn.to/3eqkTzi), and learned about Martin Oderskyâ€™s idea of Scala being a *fusion of OOP and FP*. (I also learned that Mr. Odersky was considered the â€œfather of the Java generics compiler.â€)

As I tried to implement the concepts in that book, I started mixing pure functions into my OOP code. I saw that pure functions were GREAT because (a) output depended only on input, and (b) there were no side effects. They were easy to write, read, and test.

I also learned that *error-handling data types* like `Option`, `Try`, and `Either` were terrific alternatives to throwing exceptions. I no longer had to think about exceptions short-circuiting my code when an error occurred.

As Iâ€™ll discuss shortly, because I knew exactly what was going into a function and coming out of a function, I began to trust the *type signatures* of functions again: I didnâ€™t have to read every functionâ€™s code to see what it *really* did, including code from complete strangers.

I realized that Mr. Odersky and the Scala people were onto something, and that FP probably wasnâ€™t a fad. I tried to learn more about it.

And as I dug into it even more, I found that *nobody* I had ever seen who switched to FP switched back to OOP.

No one.

## How that fits in with this book

The conclusion to this little story is that I fell in love with Scala, and contacted the people at Oâ€™Reilly Media, and ended up writing the 1st and 2nd Editions of the [Scala Cookbook](https://amzn.to/3du1pMR).

I mention all of this so that you can get an idea of my experience, or at least my experience prior to writing [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book): I didnâ€™t learn FP in college; I learned it by reading books, writing code, and asking questions.

But more importantly, the last portions of my learning path had to do with immutable variables, immutable data structures (like `String` and `List`), pure functions, EOP, and functional error-handling, and those concepts are the basis of *this* book.

# 9\. JIT: Immutable Things

As a first â€œJust In Timeâ€ lesson, the first important concept I need to cover is what I call â€œimmutable thingsâ€:

*   Immutable variables (immutable *algebraic* variables)
*   Immutable data structures

## Immutable variables (algebraic variables)

The term *immutable variable* sounds like a contradiction, but it just means that weâ€™ll be creating variables in the *algebraic* sense. For instance, in algebra you write an equation like this:

`x = a + b + c`

In that equation itâ€™s assumed that all of those variables are immutable â€” they canâ€™t be changed. That is, you would NOT write algebra like this:

`x = a + b + c`

`a = 42    // error`
`x = 11    // error`

As shown, those last two lines are errors: variables in algebra are never reassigned. The Scala equivalent of this is that you create algebraic variables using the `val` keyword:

`val x = a + b + c`

When you create a variable using `val`, itâ€™s like `final` in Java; it can never be reassigned. You can see this in the Scala REPL:

`scala> val x = 1`
`val x: Int = 1`

`scala> x = 2`
`-- [E052] Type Error: --`
`1 |x = 2`
`  |^^^^^`
`  |Reassignment to val x`

Attempting to reassign `x` to a new value generates that â€œReassignmentâ€ error. So thatâ€™s how weâ€™ll create variables in this book: as algebraic variables, with the `val` keyword.

> NOTE: In Scala/OOP you *can* create mutable variables using the `var` keyword, but this book will not use those.

## Immutable data structures

This book also uses only *immutable data structures*, such as the `String`, `List`, and `Seq` classes, and the default `Map` class, which is also immutable. When you use an immutable data structure, you cannot modify it.

> TIP: Java developers know that the Java `String` is immutable. So just think of all these other data types as working the same way as `String`: you never modify a `String`; instead, you call its methods to create a new `String`. These are like the immutable collections classes that were introduced in Java 9, such as using `List.of()` in Java 9+.

Because you canâ€™t mutate Scala collections classes like `List`, `Seq`, and `Map`, once you create a sequence like this:

`val xs = Seq(1, 2, 3)`

the only way to create a new `Seq` from it is to reassign its result to a new variable:

`// create a sequence:`
`val a = Seq(1, 2, 3)`

`// create new sequences based on that initial sequence:`
`val b = a ++ Seq(4, 5)     // b: List(1, 2, 3, 4, 5)`
`val c = b.filter(_ > 2)    // c: List(3, 4, 5)`

If this seems limiting â€” fear not! â€” FPers write code like this every day. Immutability is a key concept that makes your code easier to maintain, and safe for parallel programming.

# 10\. JIT: Pure Functions

The next JIT nugget of background information we need to cover is the definition of a pure function. A *pure function* is a function:

*   Whose only parameters from the outside world are the input parameters that are defined in its function signature. (I refer to the list of input parameters as a functionâ€™s *front door*.)
*   That does not modify those input parameters.
*   That does not modify other â€œhiddenâ€ variables that might be accessed through *side doors*, such as mutable variables in its class or any other global variables.
*   That does not communicate with the outside world. It has no I/O whatsoever: no file access, no internet access, no database access, no quantum entanglement, nothing.
*   That always returns the same output when its given the same input. For example, `sum(2, 2)` is always `4`.
*   That returns output for all possible input values.
*   That does not throw exceptions.

Because of those last two attributes, FPers say that a function is *total*, meaning that it always returns a value.

Examples of pure functions include:

*   Getting the length or checksum of a string
*   Calculating the sum of a list of integers (`List[Int]`)
*   Many mathematical functions

One thing to notice about pure functions is that they *always* have input parameters, and they never return `Unit`:

`def stringLength(s: String): Int`
`                 ---------   ---`
`                   Input     Return`
`                 Parameters  Type`

`// more pure function signatures:`
`def sum(xs: List[Int]): Int`
`def add(a: Int, b: Int): Int`
`def cos(x: Double): Double`

## A pure functionâ€™s signature tells you what it does

Because pure function signatures in Scala always include the *data types* of (a) the input parameters, and (b) the function result, you can often guess what a function does just by looking at its type signature, even if the function name is meaningless. For example, what do you think this function does:

`def f(s: String): Int = ???`

Because the function takes a `String` input parameter and returns an `Int` â€” and also because you can be 100% sure that itâ€™s a *pure function* â€” the function can only do a few things:

*   Calculate the length of the string
*   Calculate some sort of checksum or hash of the string

Even without knowing the name of the function, you can get a good idea from its type signature what it can possibly do. Thatâ€™s cool.

In fact, thatâ€™s *very* cool. This is one of the great things about pure functions: when functions are pure, you can just glance at their type signatures, and have a great feel for what they do.

In my case, once I saw this, I started to wish that all functions could somehow be pure.

### It cannot be â€œString to Intâ€

Going back to that example, as I sketched its function signature, I thought for a moment that another thing the function could do is convert the `String` to an `Int` â€¦ but thatâ€™s wrong. Because the process of attempting to convert a `String` to an `Int` can potentially fail, a pure function that does that MUST have one of these signatures in Scala:

`def f(s: String): Option[Int] = ???`
`def f(s: String): Try[Int] = ???`
`def f(s: String): Either[Throwable, Int] = ???`

As youâ€™ll see in the following chapters, because attempting to convert a `String` to an `Int` can result in an error â€” such as trying to convert the string `"Hi mom"` â€” we need to return an *error-handling type* like `Option`, `Try`, or `Either` when writing this as a pure function. These types tell readers of our pure function, â€œsomething can go wrong here.â€ (I explain this in *much* more in the following chapters.)

# 11\. JIT: I Love Pure Functions, They Cannot Lie

I initially thought that pure functions were â€œnice,â€ but when I really started using them I thought, wow, this is important: input goes in front door, and output comes out the back door, as shown in this first image:

![image](images/00001.jpg)

Very importantly, there are no side doors for *side effects* (bad things) to sneak in and out:

![image](images/00002.jpg)

## Pure functions do not lie

My overwhelming thought was, â€œWhoa, I can look ONLY at the signature of a pure function to know what it does.â€ No more digging into the source code of impure methods; just look at the function signature.

This hit me so hard that I immediately wanted to write an `impure` annotation to mark all those old methods I had written as being impure:

`@impure`
`def randomInt(): Int = scala.util.Random.nextInt`

I knew this wasnâ€™t a proper solution â€” because I had no way to enforce the annotation â€” but I REALLY wanted a way to tell the *pure* from the *impure* just by looking at function signatures.

> As youâ€™ll come to see in the remainder of this book, you can easily tell that this particular function is impure because it takes no input parameters. Any time you see a function with no input parameters, itâ€™s a clear sign that a side effect is happening inside that function.

## Pure functions reduce your cognitive load

Not to gush too much, but I LOVE writing pure functions: they make things MUCH easier on my brain.

What I mean is that when I write a pure function, I donâ€™t have to think about the rest of the application. When I write a pure function, my *entire universe* â€” the only things I need to think about â€” are:

*   What input parameters do I need?
*   What is my pure functionâ€™s return type?
*   What is its algorithm?

Literally, the only thing in my mind when Iâ€™m writing a pure function looks like this:

 `                            +------------+`
`(p1: Type1, p2: Type2)  =>  |  function  |  =>  result: ResultType`
`----------------------      +------------+      -------------------`
`   Input Parameters                             The Function Result`

Thereâ€™s no need to worry about mutating the variables Iâ€™m given, or variables in the class or available globally. I just think about (a) what comes in, (b) what goes out, and (c) the functionâ€™s algorithm.

Once I realized this, even the *imposter syndrome* in me thought, â€œYou know, I donâ€™t know if I can think about an entire application today. But I can certainly write one pure function. And then I can write another. And another. And then eventually I can glue them together to solve bigger problems.â€

> As youâ€™ll see in this book, glueing pure functions together is also just like algebra. (For more information on what I mean by glueing functions together, see the term *composition* in this bookâ€™s Glossary.)

One other thing: I also found that I like *reading* the signatures of pure functions that *other people write*. Unlike OOP-style methods that can return `void` and/or take no input parameters â€” which makes their type signatures meaningless â€” when I look at the type signature of a pure function, I can tell at a glance whatâ€™s going on.

## Another pop quiz

Hereâ€™s another little quiz: Knowing that this function is pure, what can it possible do:

`def f(list: List[Int]): Int = ???`

If youâ€™re new to Scala, this code defines a function that takes a list of integers as input, and returns an integer as its result:

*   `def f` tells you that itâ€™s a function named `f`.
*   It takes an input parameter that I have named `list`, and its type is `List[Int]`, meaning that it is a sequence (list) of integers.
*   The function returns an integer (`Int`).

I encourage you to write down everything you think that pure function can possibly do.

As a second question, hereâ€™s the same function signature, but with a generic type. Again, what can it possibly do:

`def g[A](list: List[A]): A = ???`

If youâ€™re not familiar with generic types, this just means that this function can take a list of integers (`List[Int]`), a list of strings (`List[String]`), a list of people (`List[Person]`), etc. The data type inside the `List` doesnâ€™t matter to the algorithm; the algorithm must only concern itself with the fact that itâ€™s given a list.

The `A` as the return type means that the function returns a single element that is the same data type thatâ€™s contained inside the list. So if the function receives a (`List[Int]`) as input, it must return an `Int`; and if it gets a (`List[Person]`), it must return a `Person`, etc.

Again, I encourage you to write down everything you think this function can possibly do.

## Key points

As a summary, there are several key points from these last two chapters:

*   Pure functions reduce your cognitive load. When youâ€™re writing them, all you have to think about is their input, output, and algorithm.
*   You can trust pure functions, they cannot lie. Their signatures tell you exactly what they can (and cannot) do.

Also â€” Iâ€™ll repeat this many times in this book â€” but writing code using pure functions (and immutable things) feels just like writing algebra. You start by writing a few pure functions like this:

`def add(i: Int, j: Int): Int`
`def multiply(i: Int, j: Int): Int`

and then you glue them together like this:

`val x = add(1, 1)`
`val y = multiply(x, 2)`

or this:

`val z = multiply(add(1, 1), 2)`

Or, if you like architecture and engineering, this style of programming is just like creating a blueprint. Youâ€™re connecting pipes and wires together, and because pure functions canâ€™t throw exceptions, all these pipes and beams â€œjust connectâ€ to each other. (You donâ€™t have to worry about functions throwing exceptions and blowing up your design.)

# 12\. JIT: Expression-Oriented Programming (EOP)

Before we start writing some code, we need to look at one more JIT topic: *Expression-Oriented Programming*, or EOP. And to understand EOP, we need to be clear about the differences between expressions and statements in programming.

## Statements vs expressions

In programming, a *statement* is a block of code that does not return a result, and is used solely for its side effect. For instance, both of these lines of code are statements because they donâ€™t return a result:

`println(a)`

`if a == b then println(a)`

Lines of code like those are used solely for their side effects, and in those examples, their side effect is printing to STDOUT.

Conversely, a *pure expression* is a block of code that DOES return a result, and has no side effects. A terrific thing about Scala is that every line of code can be an expression. Thatâ€™s because all of these Scala constructs return a result:

*   `if`/`then`/`else`
*   `match` expressions
*   `for` expressions
*   Even `try`/`catch`/`finally` returns a value

To explain this, letâ€™s look at how to use the `if`/`then`/`else` construct as an expression.

### Aside: A quick clarification

For the purists out there, itâ€™s more accurate to say that this code doesnâ€™t return a *useful* result:

`if a == b then println(a)`

It does return something â€” a type called `Unit` â€” which is like `void` in other languages. But in cases like this we generally donâ€™t care about its return value.

> As I mentioned previously, the `Unit` *type* has only one *value* (or instance) in Scala, and that value is represented by the `()` symbol. Therefore, this type is not meaningful or informative, and we use it as a functionâ€™s return type when we have no interest in that return type.

## Using â€˜ifâ€™ as an expression

As mentioned, `if`, `match`, `for`, and `try` can all be used as expressions. In regards to `if`, this means that `if`/`then`/`else` yields a result:

`val c = if a < b then a else b`

That code can be read as, â€œIf `a` is less than `b`, assign the value of `a` to `c`. If not, assign the value of `b` to `c`.â€ Because `if`/`then`/`else` is an expression that returns a value, itâ€™s also commonly used as the body of a function:

`def min(a: Int, b: Int): Int =`
`    if a < b then a else b`

That code defines a function named `min` that returns the minimum value of the two integer parameters that are passed into it, `a` and `b`.

## Other constructs as expressions

Okay, while Iâ€™m in the neighborhood, letâ€™s look at how Scalaâ€™s other constructs can be used as expressions. This example shows how a `match` expression yields a value:

`val evenOrOdd: String = i match`
`    case 1 | 3 | 5 | 7 | 9  => "odd"`
`    case 2 | 4 | 6 | 8 | 10 => "even"`

Hereâ€™s a `for` expression that yields a value:

`val result =`
`    for`
`        i <- 1 to 10`
`        if i > 5`
`    yield`
`        i`

If youâ€™re not familiar with that syntax, when that `for` expression is run, `result` will hold this value:

`Vector(6, 7, 8, 9, 10)`

> `Vector` is a specific type of Scala sequence â€” child of `Seq` â€” that has high-performance characteristics, and is commonly used in Scala.

When you first start with Scala you may prefer to explicitly declare `result`â€™s data type, like this:

`val result: Seq[Int] =    // explicitly declare resultâ€™s type`
`    for`
`        i <- 1 to 10`
`        if i > 5`
`    yield`
`        i`

Notice that I added the type `Seq[Int]` after the `result` variable. Scala can usually figure those types out *implicitly*, but if you think the code is easier to read with the data type shown *explicitly*, by all means, add it.

Lastly, even `try`/`catch`/`finally` blocks are used to write expressions:

`def makeInt(s: String): Int =`
`    try`
`        s.toInt`
`    catch`
`        case e: Exception => 0`
`    finally`
`        // do whatever you need to do here`

Note that this is NOT a recommended way to write this function â€” returning `0` when you get an exception is wrong, and I show better ways to write it shortly â€” but this does show that `try`/`catch`/`finally` yields a value. You can use this `makeInt` function like this:

`makeInt("11")       // 11`
`makeInt("eleven")   // 0`

## What EOP code looks like

As I show in the [Scala Cookbook](https://amzn.to/3du1pMR), when you write code using EOP, your code becomes easy to write, easy to read, and easy to test. Itâ€™s just a series of expressions that use immutable variables, immutable data structures, and pure functions:

`// a series of expressions`
`val symbol = "AAPL"`
`val url    = buildUrl(symbol)`
`val html   = getUrlContent(url)    // an impure function`
`val price  = getPrice(html)`
`val volume = getVolume(html)`
`val high   = getHigh(html)`
`val low    = getLow(html)`
`val date   = getDate()             // an impure function`

`// StockInstance is a class that takes these parameters:`
`val stockInstance = StockInstance(symbol, date, price, volume, high, low)`

Even though that example uses two impure functions to communicate with the outside world, it gives you can idea of what EOP code looks like. (In regard to the `getUrlContent` function, Iâ€™ll show a better way to write it in the following chapters.)

## EOP benefits

Because expressions always return a result and generally donâ€™t have side effects, there are several benefits to EOP:

*   The code is *easier to write, read, and test*. Inputs go into a pure function, a result is returned, itâ€™s assigned to an immutable variable, and there are no side effects.
*   Combined with Scalaâ€™s syntax, EOP results in concise, *expressive* code.
*   Although itâ€™s only been hinted at in these examples, expressions can often be executed in any order. This subtle feature lets you execute expressions in parallel, which is a huge bonus when youâ€™re trying to take advantage of multicore CPUs.

If youâ€™re interested in more details, I write about all of these benefits in [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book) (and ~40% of that book is free).

## On to the code!

Given this background, itâ€™s time to start writing some code that demonstrates the benefits of pure functions, immutable things, and EOP!

# 13\. Example #1: Solving Problems with Pure Functions and EOP

Writing Scala code like this gets to be so much like algebra that you can imagine walking in on Albert Einstein writing at a chalkboard, and following his equations one at a time until he joins them all together at the end.

To demonstrate this, letâ€™s walk through the process of writing a â€œword occurrenceâ€ algorithm using only pure functions, immutable variables, immutable data structures, and EOP. I think youâ€™ll see that we can simply talk about this as we sketch out a series of pure function signatures â€” just like writing algebra on a chalkboard.

> This example was inspired by a Haskell book. Iâ€™d like to give it credit, but I havenâ€™t been able to remember which book I saw it in.

## Source code

If you want to work with this exampleâ€™s source code, you can find it here in the bookâ€™s Github repository, under the `WordCount` folder:

*   [github.com/alvinj/LearnFunctionalProgrammingBook](https://github.com/alvinj/LearnFunctionalProgrammingBook)

## Problem statement

The first thing to do in any problem-solving effort is to write a clear problem statement:

> Given a document thatâ€™s represented as a single Scala `String`, count the number of occurrences of each word in that document.

In addition to that statement, weâ€™re also shown that the output of the algorithm should look like this, with the words in the first column and the number of occurrences in the second column:

`the    543`
`an     210`
`or     99`
`(more words here ...)`

Okay, that seems good enough for now. So, how do we start?

## Getting started

The first thing we can say is that weâ€™re going to write a pure function that works like a â€œword occurrencesâ€ or â€œword countâ€ function. I donâ€™t want to keep writing the word â€œoccurrences,â€ so to keep this simple Iâ€™ll refer to it as a *word count* function, which Iâ€™ll name `wc`:

`def wc`

Next, I know from the problem statement that it will take the document as a `String` input parameter:

`def wc(document: String)`

Now if I look at the sample output, that sure looks like a `Map` to me. More specifically, a map where the key is a string, and the value is an integer:

`Map[String, Int]`

For instance, in Scala, that sample data looks like this `Map`:

`Map(`
`    "the" -> 543,`
`    "an" -> 210,`
`    "or" -> 99`
`)`

Also note that the output is printed in sorted order, so weâ€™ll want to return a `VectorMap` to indicate to others that thereâ€™s something unique about this map:

`VectorMap[String, Int]`

A `VectorMap` is a specific type of immutable `Map` that lets us return the map values in a sorted order.

Knowing this, we can finish the sketch of our main function signature like this:

`def wc(document: String): VectorMap[String, Int]`

So there we have it, thatâ€™s the signature for our main function. Now all we have to do is sketch out some more pure functions that this function will call.

## The next steps

There are several ways we *could* proceed next, but because the requirement is that we just turn a `String` into a `Map`, thereâ€™s no need to deal with that `String` as paragraphs and sentences. Instead, we can work with it as is, adjusting it slightly for our needs.

## Get rid of the newline characters

The first thing Iâ€™ll do is strip all the newline characters from the `String`. What Iâ€™m thinking is that I can replace all those newline characters with blank spaces, and then in a few moments Iâ€™ll reduce all occurrences of multiple blank spaces down to single blank spaces.

When you think of how this â€œget rid of all newline charactersâ€ function needs to work, you can imagine that it takes the existing `String` as its input parameter, so I start with this:

`def replaceNewlinesWithBlanks(s: String)`

Next, I know that I want to return a `String` with all of the newline characters replaced with blanks, so I can add `String` as the functionâ€™s return type:

`def replaceNewlinesWithBlanks(s: String): String`

So thatâ€™s a sketch of that function signature. At this point I feel comfortable that this is the first step of my `wc` function, so I add it to `wc`â€™s body:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`

`    // more code to come ...`

> Note that Iâ€™ll be wrapping my expressions inside `wc` as shown because (a) Iâ€™m intentionally using long, meaningful function names, and (b) itâ€™s hard to print wide lines in a book.

## Remove formatting characters

The next thing I need to do is to remove all formatting characters from the string â€” things like periods, exclamation points, question marks, semi-colons, colons, and em dashes. So again, this is going to be a function that takes a `String` as input and returns a `String`, so I sketch this:

`def stripFormattingCharacters(s: String): String`

I really donâ€™t want you thinking about algorithms at the moment â€” just function signatures. But if you find yourself thinking about algorithms, this function can either delete all of those formatting characters or replace them with blank spaces; either approach will work.

When I add this function to `wc`â€™s body, it now looks like this:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`

## Eliminate multiple blank spaces

At this point I canâ€™t think of any other changes I want to make to the initial string. You can imagine that we started with a multiline string that looks like this:

`Foo barâ€™s baz?`

`Buzzle; buzzy. Burf!`

and at this point that string should look like this:

`Foo barâ€™s baz  Buzzle buzzy Burf`

Weâ€™re still working with a `String`, and all of its words should be separated by one or more blank spaces, so this is a good time to create a function to convert multiple blank spaces into a single blank space. Once again we have a `String` coming in and a `String` going out, so I sketch this function like this:

`def squeezeBlankSpaces(s: String): String`

Then I add that function call to `wc` to get this:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    ...`

## From String to Seq[String]

Now our `String` should be free of punctuation characters, with each word separated by a single blank space. So the next step is to transform it into a list of words, which in Scala can be represented as a `Seq[String]`, `List[String]`, or `Vector[String]`. Once we have this list of words, we can later convert it to a `Map` of word counts.

> `Seq`, `List`, and `Vector` are all immutable lists (sequences) that are suited for slightly different purposes, but as long as weâ€™re working with a relatively small document, any of them will work.

Therefore, this function takes a `String` as input and returns a `Seq[String]`, so its signature looks like this:

`def convertStringToListOfWords(s: String): Seq[String]`

and when I add it to `wc`, its body now looks like this:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    ...`

## Convert words to the same case

Now that we have a list of words, we need to do one more thing: Either (a) convert them all to the same case â€” lowercase or uppercase â€” or (b) perform a case-insensitive comparison of them later on when we count the words. We need to do this to make sure we count words like â€œDoâ€ and â€œdoâ€ as the same word.

Being lazy, Iâ€™ll change all the words to lowercase now. And because weâ€™re now working with a `Seq[String]` â€” our list of words â€” Iâ€™ll sketch this function to take a `Seq[String]` as input, and also return a `Seq[String]`:

`def lowerCaseAllWords(listOfWords: Seq[String]): Seq[String]`

With this addition, our `wc` function looks like this:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    val lcListOfWords =`
`        lowerCaseAllWords(listOfWords)`
`    ...`

## From a Seq[String] to a Map

Now that we have a list of words, weâ€™re almost home. The next step is to create a function that converts the list of words into a `Map`, where that `Map` contains each unique word as the key, and the count of occurrences of that word as its value.

We donâ€™t have to think about that algorithm yet, we just need to sketch the function signature. We know that it should take a `Seq[String]` as input, and return a `Map[String, Int]`, so its signature looks like this:

`def convertWordListToWordCount(listOfWords: Seq[String]): Map[String, Int]`

and now `wc` looks like this:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    val lcListOfWords =`
`        lowerCaseAllWords(listOfWords)`
`    val initialMap =`
`        convertWordListToWordCount(lcListOfWords)`
`    ...`

## Sort the Map

As our last step, now we just need to sort that `Map` by its values, in descending order. For example, the `Map` may look like this right now:

`Map(`
`    "or" -> 99,`
`    "the" -> 543,`
`    "an" -> 210`
`)`

and we want it to look like this:

`Map(`
`    "the" -> 543,`
`    "an" -> 210,`
`    "or" -> 99`
`)`

So we need a function that takes a `Map[String, Int]` as input, and also returns a `Map[String, Int]`, BUT, the returned map needs to be sorted. Scalaâ€™s `VectorMap` can be used for just this purpose, so I sketch this function:

`def sortMapByHighestValue(map: Map[String, Int]): VectorMap[String, Int]`

and then I add it to `wc`:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    val lcListOfWords =`
`        lowerCaseAllWords(listOfWords)`
`    val initialMap =`
`        convertWordListToWordCount(lcListOfWords)`
`    val sortedMap =`
`        sortMapByHighestValue(initialMap)`
`    sortedMap`

Note that in this case I add the `sortedMap` variable to the end of the function, because thatâ€™s the value that our function yields.

> NOTE: In functional programming, FPers donâ€™t say â€œreturnâ€; we say that a function *yields a result*, or that it *evaluates to a result*. Again, weâ€™re writing algebra here, and thatâ€™s what algebraic equations do.

## Is that code hard to read?

Great questions at this point are:

*   Is that code hard to read?
*   Is it hard to reason about?

In both cases I suspect that youâ€™ll say that this code is actually about as simple as it gets. Because the functions are pure and the variables and data types are immutable, the code ends up being written in an EOP style, which I find to be as simple as possible.

> I donâ€™t like to use the word â€œsimpleâ€ in programming books, because everyoneâ€™s background is different. So thatâ€™s why I say, â€œas simple as possible.â€ Frankly, the code reminds me of writing BASIC code with pure functions when I was in high school.

## Discussion

So this is pretty cool. Assuming that I thought of everything, we almost completely solved this problem by (a) sketching out a series of pure function signatures, and then (b) combining those signatures like a series of algebraic equations. All thatâ€™s left to do is write the code inside those function bodies.

One thing thatâ€™s worth mentioning is that as you go through this process, it can help to jot down a sample of the input you expect a function to receive, as well as the output itâ€™s expected to return. Thatâ€™s why I showed the `String` and `Map` data in a few steps there, to make sure that my logic was sound.

## Two notes

Tow notes come to mind after writing this section of the book.

### 1) Being a mathematician or architect

The first note is to reiterare what Iâ€™ve already stated: that FPers like to think of this style of programming as math, or perhaps as creating a blueprint. So rather than being a programmer, youâ€™re like a mathematician or architect, working on equations or the blueprint. Because of this, youâ€™ll also hear FPers say things like â€œreasoning about the code,â€ because they look at function signatures like these and how they glue together.

As youâ€™ll see throughout this book, when your functions are pure and your values are immutable, you can do this.

### 2) You can do much more with Scala types

A second thing I need to mention is that with the Scala type system, you can do some things to make your code even more readable. For instance, in my code I return a `VectorMap` from a function, but if you think about that signature, it could be more meaningful, right?

What I mean is that I wrote this:

`VectorMap[String, Int]`

but with Scalaâ€™s type system I can write that return type like this instead:

`MapSortedByValueDesc[String, Int]`

Scala lets you create more meaningful type names like this, and in this case, anyone who looks at this code now knows that this is a `Map` thatâ€™s sorted by value. Thatâ€™s pretty cool.

*And then* you can also take this a step further and make that function signature look like this:

`MapSortedByValueDesc[Word, Count]`

Whoa, thatâ€™s *extremely* cool. With these new names, anyone who walks in off the street can tell exactly whatâ€™s going on with that `Map`. And this can all be done with Scala.

As I discuss in the [Scala Cookbook (2nd Edition)](https://amzn.to/3du1pMR), this sort of naming process is used in *Domain-Driven Design*, and it makes your types more meaningful.

This also makes for an interesting question: If you walked into someoneâ€™s code base, which of these options would you rather see for this particular problem, and why:

*   `Map[String, Int]`
*   `VectorMap[String, Int]`
*   `MapSortedByValueDesc[String, Int]`
*   `MapSortedByValueDesc[Word, Count]`

The answer is entirely up to you, BUT, I encourage you to form an opinion about it. You can also show it to some fellow developers and ask them what theyâ€™d rather see, and why.

## All done!

At this point weâ€™re done. Well, at least weâ€™re done sketching out the pure functions we need to solve this problem. All we have to do now is to write the algorithms for the bodies of those functions.

*Up until now* was the time to think about function signatures. *Now* is the time to think about how to implement those algorithms.

Iâ€™d say that Iâ€™ll leave that as â€œan exercise for the reader,â€ but you can find those functions implemented in this bookâ€™s Github repository.

# 14\. One More Thing: Algebraic Substitution

Before we move on from this Word Count example I need to add one very important point: Because I wrote `wc` using only pure functions and immutable values, both you and a compiler are free to reduce this code.

What this means is that at the end of the previous lesson I had this function:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    val lcListOfWords =`
`        lowerCaseAllWords(listOfWords)`
`    val initialMap =`
`        convertWordListToWordCount(lcListOfWords)`
`    val sortedMap =`
`        sortMapByHighestValue(initialMap)`
`    sortedMap`

But because `initialMap` (near the end of the function) is exactly equal to `convertWordListToWordCount(lcListOfWords)` â€” and always will be, because the values are immutable and the functions are pure â€” you can replace `initialMap` in the second-to-last line with its equivalent function call, like this:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    val lcListOfWords =`
`        lowerCaseAllWords(listOfWords)`
`    // ELIMINATED 'initialMap'`
`    val sortedMap =`
`        sortMapByHighestValue(convertWordListToWordCount(lcListOfWords))`
`    sortedMap`

By the same argument, `lcListOfWords` is exactly equal to:

> `lowerCaseAllWords(listOfWords)`

so I can eliminate that intermediate variable:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    val listOfWords =`
`        convertStringToListOfWords(stringWithSingleBlanks)`
`    // ELIMINATED 'lcListOfWords'`
`    val sortedMap =`
`        sortMapByHighestValue(`
`            convertWordListToWordCount(`
`                lowerCaseAllWords(listOfWords)`
`            )`
`        )`
`    sortedMap`

Next, `listOfWords` is exactly equal to:

> `convertStringToListOfWords(stringWithSingleBlanks)`

and always will be â€” so I can remove `listOfWords` as an intermediate value:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    val stringWithSingleBlanks =`
`        squeezeBlankSpaces(stringWithoutFormatting)`
`    // ELIMINATED 'listOfWords'`
`    val sortedMap =`
`        sortMapByHighestValue(`
`            convertWordListToWordCount(`
`                lowerCaseAllWords(`
`                    convertStringToListOfWords(stringWithSingleBlanks)`
`                )`
`            )`
`        )`
`    sortedMap`

The same is true of `stringWithSingleBlanks`, so I reduce the code again:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    val stringWithoutFormatting =`
`        stripFormattingCharacters(stringWithoutNewlines)`
`    // ELIMINATED 'stringWithSingleBlanks'`
`    val sortedMap =`
`        sortMapByHighestValue(`
`            convertWordListToWordCount(`
`                lowerCaseAllWords(`
`                    convertStringToListOfWords(`
`                        squeezeBlankSpaces(stringWithoutFormatting)`
`                    )`
`                )`
`            )`
`        )`
`    sortedMap`

and then do the same with `stringWithoutFormatting`:

`def wc(document: String): VectorMap[String, Int] =`
`    val stringWithoutNewlines =`
`        replaceNewlinesWithBlanks(document)`
`    // ELIMINATED 'stringWithoutFormatting'`
`    val sortedMap =`
`        sortMapByHighestValue(`
`            convertWordListToWordCount(`
`                lowerCaseAllWords(`
`                    convertStringToListOfWords(`
`                        squeezeBlankSpaces(`
`                            stripFormattingCharacters(stringWithoutNewlines)`
`                        )`
`                    )`
`                )`
`            )`
`        )`
`    sortedMap`

and then `stringWithoutNewlines`:

`def wc(document: String): VectorMap[String, Int] =`
`    // ELIMINATED 'stringWithoutNewlines'`
`    val sortedMap =`
`        sortMapByHighestValue(`
`            convertWordListToWordCount(`
`                lowerCaseAllWords(`
`                    convertStringToListOfWords(`
`                        squeezeBlankSpaces(`
`                            stripFormattingCharacters(`
`                                replaceNewlinesWithBlanks(document)`
`                            )`
`                        )`
`                    )`
`                )`
`            )`
`        )`
`    sortedMap`

And if you want to, you can eliminate `sortedMap`:

`def wc(document: String): VectorMap[String, Int] =`
`    // ELIMINATED 'sortedMap'`
`    sortMapByHighestValue(`
`        convertWordListToWordCount(`
`            lowerCaseAllWords(`
`                convertStringToListOfWords(`
`                    squeezeBlankSpaces(`
`                        stripFormattingCharacters(`
`                            replaceNewlinesWithBlanks(document)`
`                        )`
`                    )`
`                )`
`            )`
`        )`
`    )`

To be clear, you DO NOT have to write code like this. Iâ€™m just showing it to demonstrate a possibility of this style of programming.

## Algebraic substitution

We call this process *algebraic substitution*, and it works because:

*   The functions are pure
*   The variables are immutable
*   The data structures are immutable

When code is written like this, both you and the compiler are perfectly free to write it in any of these ways, and youâ€™re always guaranteed to get the same result.

> KEY: But if you use mutable variables, mutable data types, and impure methods, the same cannot be said.

## Technical goo: â€œReferential Transparencyâ€

If you like algebra, youâ€™ll like referential transparency. We say that an expression is *referentially transparent* (RT) if it can be replaced by its resulting value without changing the behavior of the program. This must be true regardless of where the expression is used in the program. So this is basically a way of saying, â€œAlgebraic substitution can be done here.â€

What I did in the previous example is actually the opposite of that â€” I replaced the intermediate variables with their expressions â€” but thatâ€™s the cool part: all of those intermediate variables and their pure function calls are 100% equivalent.

Finally, notice that Iâ€™m not doing any â€œfancy FPâ€ stuff in this code. Iâ€™m just writing EOP code with immutable variables, immutable data types, and pure functions.

# 15\. A Quick Look at Parallel Programming

A first reason that algebraic substitution is important is because, as I mentioned, code written like this is easier to write, read, and test. Thatâ€™s a simple sentence to write, but in practice, this is an enormous gain that makes your life simpler. (I could write several chapters about this alone.)

A second reason itâ€™s important is because you can use algebraic substitution to write your code in any of the ways I just showed. The second approach I showed, where your code looks like this:

`doE(`
`    doD(`
`        doC(`
`            doB(`
`                doA(someData)`
`            )`
`        )`
`    )`
`)`

can also be formatted to look like this:

`doE(doD(doC(doB(doA(someData)))))`

With either approach, this is interesting because itâ€™s like writing Lisp code, and you read it from the inside-out. (In small doses I like this style.)

But thereâ€™s an even more important point about EOP and algebraic substitution:

> When your expressions (equations) donâ€™t have to be evaluated in a specific order, the compiler is completely free to evaluate them in parallel, and then join them into one result some time later. I only worked with Haskell for a few weeks, but Iâ€™ve read that this is how the Haskell compiler works, and it can do that because Haskell code is guaranteed to be FP code.

## Enabling parallel programming

To demonstrate what I mean, hereâ€™s an example, where again you can assume that all functions are pure, and the variables and data types are immutable:

`val a = f1(x)`
`val b = f2(y)`
`val c = f3(z)`
`val d = f(a, b, c)`

Because the first three expressions have no dependencies on each other, a smart compiler is perfectly free to run those functions on different threads (or, more recently, *fibers*). So if they each take 20 seconds to run, you donâ€™t have to wait 60 seconds for them to run in serial; they can be run in parallel, and you get the final result in 20 seconds.

Visually, that means that rather than having this slow serial code:

`// code runs in serial, 20 seconds each, 60 seconds total`

`val a = f1(x)                                                    `
`â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€>                                                    `
`              â”‚ val b = f2(y)                                    `
`              â”‚ â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€>                                    `
`                              â”‚ val c = f3(z)                    `
`                              â”‚ â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€>                    `
`                                              â”‚                  `
`                                              â”‚ val d = f(a, b, c)`

you can have this high-performance code that runs in parallel:

`// code runs in parallel, 20 seconds total`

`val a = f1(x)                            `
`â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€> â”‚                          `

`val b = f2(y)  â”‚                          `
`â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€>                            `
`               â”‚                          `
`val c = f3(z)                            `
`â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€> â”‚                          `

`               â”‚ val d = f(a, b, c)`

When you want high-performance code â€” and who doesnâ€™t â€” this is a huge win. And all you have to do to achieve these gains are to use:

*   Immutable variables
*   Immutable data structures
*   Pure functions
*   Expressions (and not statements)

## This doesnâ€™t work with mutable things

Itâ€™s important to be clear that a compiler canâ€™t do this for you when you use mutable variables, mutable data structures, and impure functions.

Perhaps the simplest way to demonstrate this is to imagine that you have these three lines of code that consist of two statements and a function with a side effect:

`println("Whatâ€™s your name?")               // statement`
`val name = readLine()                      // side effect`
`println(s"You said your name is $name")    // statement`

They make sense when run serially, but if you try to run them in parallel, you can imagine the mess you can end up with:

`println(s"You said your name is $name")`
`val name = readLine()`
`println("Whatâ€™s your name?")`

As another example, assume that you have three functions named `g1`, `g2`, and `g3`, and they each modify some shared global state. If `g1` writes a variable in that state that `g2` reads, and `g2` writes a variable that `g3` reads, those operations really need to happen in that order â€” just like the `println`/`readLine` example.

But if `g1`, `g1`, and `g3` are run in parallel â€¦ well, thereâ€™s no guarantee about the order in which things will happen. We say that the result you get from this situation is *indeterminate*.

One time I was working with a client, and they had a problem where theyâ€™d occasionally have inconsistent customer data. They might have a userâ€™s name and street address correct, but somehow the city, state, or zip code wouldnâ€™t match up with the name and street address. We found that for some reason, one or more developers wrote this portion of code to *try* to work in parallel. Apparently 99 times out of 100 it would work properly â€” perhaps because clients donâ€™t change their addresses often â€” but when it failed, customers might find out that they lived in â€œChicago, Alaskaâ€ instead of â€œChicago, Illinois.â€

This canâ€™t happen with immutable variables, immutable data structures, and pure functions.

## Reasoning about code

Youâ€™ll sometimes hear FPers say that they like to â€œreason about their code.â€ Of course we do that in OOP as well, but when FPers say this, it means that weâ€™re looking at lines of code like algebra, and weâ€™re making sure they can be joined the way we want them to be.

If they can be run in parallel, cool, thatâ€™s awesome. But if they canâ€™t, youâ€™ll see that we *ensure* that theyâ€™re run in serial, typically with a `for` expression:

`val result =`
`    for`
`        a <- g1(x)`
`        b <- g2(y)`
`        c <- g3(z)`
`    yield`
`        // some use of a, b, and c here`
`        g4(a, b, c)`

Thatâ€™s a bit of a contrived example, but I demonstrate real uses of this technique later in this book.

# 16\. Recap: Java/OOP vs Pure Functions

When I began this section of the book, I showed that these were the two most complicated type declarations I found in over 150,000 lines of production Java code:

`SortedMap<String, Integer> wordCountMap = new TreeMap();`
`public Class<?> getColumnClass(int columnIndex) {`

Conversely, as you saw in the Word Count example, as I sketched out that application in Scala using pure functions, Iâ€™m already working with data types like these:

`Seq[String]`
`VectorMap[String, Int]   // or: MapSortedByValueDesc[Word, Count]`

This is a hint that in Scala we use *types* a lot more than developers are used to using in Java/OOP.

As someone whoâ€™s interested in helping programmers who want to learn more about Scala, itâ€™s important to acknowledge that this is a different world than Java/OOP. In the Java world you generally only work with types like this if youâ€™re a library developer, but in the Scala world, developers at all levels work with them. So I think itâ€™s important to acknowledge this difference.

That being said, Iâ€™ll ask: Did you find the Word Count example hard to follow? I suspect â€” and hope â€” it wasnâ€™t hard to follow. As you saw, I just sketched out a series of pure functions and their type signatures.

## Benefits

There are a lot of benefits to this approach of working with only pure functions, immutable variables, and immutable data structures. First, hereâ€™s some of what youâ€™ve already seen:

*   You write pure functions.
*   Writing pure functions is about as easy as it gets. You donâ€™t have to worry about the state of the entire application, all you have to think about is (a) what comes in, and (b) what goes out.
*   Because of those attributes, you can sketch solutions just like I did. Just sketch out the solution as a series of pure functions, and then fill in the function bodies.
*   You can trust the type signatures of pure functions, they cannot lie. Their signatures tell you whatâ€™s going on.
*   Because of that, you can trust pure functions that other developers write.
*   Iâ€™ve only briefly touched on this so far, but if you look at a pure functionâ€™s signature and see `Option`, `Try`, or `Either` as the return type, you immediately know, â€œSomething can go wrong here.â€ (More on this soon.)

Beyond those benefits:

*   Not only are pure functions easier to write, theyâ€™re easier to read. Just look at a pure functionâ€™s type signature and youâ€™ll get a strong idea of what that function can possibly do.
*   Youâ€™ll start to see solving problems as being like algebra, or creating a blueprint as an architect or engineer.
*   As you also saw with the Word Count example, the final solution to the problem is just a matter of combining your pure functions, like algebraic equations.
*   Following all of this logic, *testing* pure functions is also easier. All you have to do is set up whatâ€™s going in the front door, and what you expect to come out the back door. You donâ€™t have to worry about mutable state anywhere else in the application (side doors).

## Next

Before we move completely on from the Word Count example, letâ€™s add a real-world scenario to it: your boss comes to you and requests a change.

# 17\. A Change To The wc Application

So the change is that your boss comes to you and says, â€œUm, err, yeah, I was wrong about that Word Count application. You wonâ€™t be getting a `String` that represents the *document*, youâ€™ll be getting a `String` that is the *name of the file* you need to read, and it contains the document.â€

This isnâ€™t a huge change, but it does bring up some interesting concerns; what should you do if:

*   The file doesnâ€™t exist?
*   The file isnâ€™t readable?

In Java/OOP â€” and even Scala/OOP â€” you might throw exceptions and then let the callers of your code deal with those. But in Scala/EOP and Scala/FP we donâ€™t do those things. We donâ€™t throw exceptions because those would short-circuit our algebraic equations or blow up our blueprints.

Instead, we use a different technique known as *functional error handling* and *error-handling data types*. Weâ€™ll look at those next.

# 18\. Functional Error Handling (FEH)

In Scala, the correct solution to handling potential errors is to use Scalaâ€™s *error-handling data types*. In short, this means that a function that can fail should return one of the `Option`, `Try`, or `Either` types:

`def wc(f: File): Option[?]`
`def wc(f: File): Try[?]`
`def wc(f: File): Either[?]`

The basic idea is that you return an error-handling data type to account for the *possibility that an error may occur in this function*.

## These types are wrappers

Error-handling types are basically *wrappers*, and inside their wrapper they contain one of two possibilities:

*   The function succeeded, and you can access its *success value*
*   The function failed, and you can access its *error value*

So itâ€™s like youâ€™re getting a container back from a function:

`â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”`
`â”‚                                       â”‚`
`â”‚   Success Value  OR  Failure Value    â”‚`
`â”‚                  --                   â”‚`
`â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜`

As shown, when you get the container back from the function, it will contain either a Success Value *or* a Failure Value â€” but not both.

A great thing about this approach is that unlike exceptions, they donâ€™t short-circuit your code: youâ€™re just working with another data type. You treat this result as a *value*, and you continue writing your code as algebra. Youâ€™ll see what this means shortly.

The `Option`, `Try`, and `Either` error-handling data types take slightly different approaches, but thatâ€™s the essence of them.

So letâ€™s see how they work.

## The three error-handling types

As mentioned, Scalaâ€™s three error-handling types are named `Option`, `Try`, and `Either`. Thinking in OOP for a moment, each of these are parent data types, and they each have two sub-types.

For these three values, these are the parent types and their two sub-types:

*   `Option`, `Some`, and `None`
*   `Try`, `Success`, and `Failure`
*   `Either`, `Right`, and `Left`

Their class hierarchies are basic OOP, and look like this:

 `      â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”`
`      â”‚  Option  â”‚`
`      â””â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”˜`
`           â”‚          `
`     â”Œâ”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”    `
`     â”‚            â”‚    `
`â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”   â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”`
`â”‚  Some  â”‚   â”‚  None  â”‚`
`â””â”€â”€â”€â”€â”€â”€â”€â”€â”˜   â””â”€â”€â”€â”€â”€â”€â”€â”€â”˜`

this:

 `        â”Œâ”€â”€â”€â”€â”€â”`
`        â”‚ Try â”‚`
`        â””â”€â”€â”¬â”€â”€â”˜`
`           â”‚            `
`     â”Œâ”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”    `
`     â”‚            â”‚    `
`â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”€â”`
`â”‚ Success â”‚  â”‚ Failure â”‚`
`â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜`

and this:

 `       â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”`
`       â”‚  Either  â”‚`
`       â””â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”˜`
`            â”‚            `
`     â”Œâ”€â”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”    `
`     â”‚             â”‚    `
`â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”    â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”€â”`
`â”‚  Left  â”‚    â”‚  Right  â”‚`
`â””â”€â”€â”€â”€â”€â”€â”€â”€â”˜    â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜`

If your background is Java, you can think of `Option`, `Try`, and `Either` as being interfaces, and their sub-types are implementations of their interface.

In the following lessons weâ€™ll look at what this means, and how these types work.

# 19\. FEH: Option

The first functional error-handling type I like to look at is `Option`, and its companions, `Some` and `None`. I do this because (a) its similar to Javaâ€™s `Optional` type, and (b) itâ€™s a little more basic than `Try` and `Either`.

## In a world where things can go wrong â€¦

Getting back to our Word Count application, our boss just came to us and told us weâ€™re not getting a `String` that represents the document, weâ€™re getting a `String` that is the name of the file that contains the document.

As any experienced developer knows, when you write certain functions, things can go wrong. This is especially true when you start working with File I/O, Network I/O, and Database I/O. In this world, files can be unreadable, networks can be down, servers can be down, etc., and these things must be accounted for.

When you write these functions in other programming languages you might throw exceptions or return null values, but in Scala we donâ€™t do those things. As mentioned, we use *error-handling data types*.

> As I wrote [in this blog post many years ago](https://alvinalexander.com/scala/best-practice-eliminate-null-values-from-code-scala-idioms/), Tony Hoare, the inventor of the `null` reference â€” way back in 1965 â€” refers to the creation of the `null` value as his â€œbillion dollar mistake.â€

## A simpler problem: Converting a String to an Int

Iâ€™m going to put off the Word Count application just a little while longer, and instead I want to work on a slightly easier problem. Iâ€™ll show how to *safely* convert a `String` to an `Int`. This is a relatively simple problem, so we can focus on our error-handling types rather than missing files or servers that are down. (Weâ€™ll deal with those later in the book.)

So the problem with converting a `String` to an `Int` is that sometimes it works, and sometimes it doesnâ€™t. And when it doesnâ€™t, the process throws an exception. The Scala REPL shows how this process succeeds and how it fails:

`scala> "1".toInt`
`val res0: Int = 1`

`scala> "one".toInt`
`java.lang.NumberFormatException: For input string: "one"`

In the first example the string properly represents an integer â€” `"1"` â€” so the conversion process works. But when the string canâ€™t be converted to an integer in the second example, the process blows up with a `NumberFormatException`.

Code blowing up is bad. You canâ€™t write algebra when your equations can explode.

## A first attempt

If we *didnâ€™t* have error-handling types, we might first try to write a `makeInt` function like this:

`def makeInt(s: String): Int =`
`    try`
`        s.toInt`
`    catch`
`        case e: NumberFormatException => 0`

That function always returns an `Int`, but the problem is that it isnâ€™t accurate in all instances. For example, all of these function calls will return `0`, which is incorrect:

`makeInt("0")`
`makeInt("")`
`makeInt("one")`

In the first example the value returned is correct, but in the second and third examples, `0` is not the correct answer. So, what is the correct solution?

## The correct solution

This is where Scalaâ€™s error-handling data types come in. Instead of the function returning an `Int`, the correct approach is for it to return a data type that *encapsulates* the possibility of success or failure. As mentioned, I want to first work with the `Option` type, and its sub-types, `Some` and `None.`

The general solution is to (a) define your function to return an `Option` that wraps the type that your function yields when it succeeds â€” `Int`, in this case. And then in the body of the function, you return (b) a `Some` for the *success* case, and (c) a `None` for the *failure* case:

`def makeInt(s: String): Option[Int] =`
`    try`
`        Some(s.toInt)`
`    catch`
`        case e: NumberFormatException => None`

As shown, the `Some` wraps the data type that you were able to calculate successfully, and in the error case you return a `None`. (The `None` type doesnâ€™t contain anything, itâ€™s just an indicator to callers of your function that something went wrong.)

When you call the function, youâ€™ll see the `Some` and `None` types as its return value:

`// success cases`
`makeInt("1")      // Some(1)`
`makeInt("2")      // Some(2)`

`// failure cases`
`makeInt("")       // None`
`makeInt("one")    // None`

A key to this solution is that `Option` is the base type, and `Some` and `None` are its sub-types:

 `       â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”`
`       â”‚ Option â”‚`
`       â””â”€â”€â”€â”¬â”€â”€â”€â”€â”˜`
`           â”‚          `
`     â”Œâ”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”    `
`     â”‚            â”‚    `
`â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”   â”Œâ”€â”€â”€â”€â”´â”€â”€â”€â”`
`â”‚  Some  â”‚   â”‚  None  â”‚`
`â””â”€â”€â”€â”€â”€â”€â”€â”€â”˜   â””â”€â”€â”€â”€â”€â”€â”€â”€â”˜`

So you declare that the function returns the parent type: `Option`, or specifically an `Option[Int]` in this case. Then the body of the function returns its sub-types: `Some` for the success case, and `None` for the error/failure case.

When you write the function, thatâ€™s all you have to do.

## Using the function

Now that `makeInt` is written like this, the flip side of the coin is, â€œAs a caller of this function, how do I handle this type?â€

### pattern matching

One of the most common ways to handle an `Option` is with *pattern matching* in a `match` expression:

`makeInt(aString) match`
`    case Some(i) => println(s"Conversion worked! i = $i")`
`    case None    => println("The conversion failed.")`

As shown, the `match` expression lets you handle the two possible cases, `Some` and `None`. When you work with the `Some` you extract the `Int` out of it, and when you work with the `None`, itâ€™s just an indicator that something failed.

### for expressions

A second common way the function is used is inside a `for` expression, especially when you have multiple calls to your function. This code shows the result when three strings can be converted to integers:

`val maybeSum: Option[Int] =`
`    for`
`        i <- makeInt("1")`
`        j <- makeInt("2")`
`        k <- makeInt("3")`
`    yield`
`        i + j + k`

`// result:  maybeSum == Some(6)`

Some developers like to use the word â€œmaybeâ€ when receiving an error-handling type, because value â€œmay beâ€ a success type, or not. So I thought Iâ€™d show that term here. The important part is that when the `for` expression finishes, `maybeSum` has the value `Some(6)`.

Next, this *exact same code* shows what happens when one or more string values cannot be converted to integers:

`val maybeSum: Option[Int] =`
`    for`
`        i <- makeInt("1")`
`        j <- makeInt("Hi mom!")`
`        k <- makeInt("3")`
`    yield`
`        i + j + k`

`// result:  maybeSum == None`

As shown, in this situation, `maybeSum` is a `None` rather than a `Some`. However, notice that you donâ€™t care at this point if something failed, you just write the code as shown, and it handles both the success and failure cases.

Then, whenever you want to work with `maybeSum`â€™s value, you can work with in a `match` expression:

`maybeSum match`
`    case Some(i) => println(s"Conversion worked! i = $i")`
`    case None    => println("The conversion failed.")`

At some point in history, someone referred to the `Some` case as the *Happy Path*, because itâ€™s the success case. And that would make the `None` case the *Unhappy Path*, because itâ€™s the failure case.

But the keys here are:

*   Your code is still algebra because youâ€™re dealing with values, and not exceptions. (There is no short-circuiting or explosions.)
*   Your code doesnâ€™t get all uglified and hard to read with a bunch of `try`/`catch` blocks.

## Pure functions cannot lie

Before we move on, itâ€™s worth repeating this about the signatures of pure functions: *they cannot lie*.

As you saw in this example, the `makeInt` function screams loud and clear, â€œIâ€™ll give you an `Int` if everything goes well, but be warned that something can wrong hereâ€:

`def makeInt(s: String): Option[Int] = ???`
`                        -----------`

Whenever you see `Option` as the return type of a pure function, you know that something can go wrong inside that function.

## makeInt can be more concise

For those who know Scala, I want to note that yes, `makeInt` can be written more concisely. But for the purpose of these lessons, Iâ€™m using this longer form. (Iâ€™ll show the shorter form later.)

# 20\. FEH: Try

Now that youâ€™ve seen how `Option` works, letâ€™s look at `Try` as an alternative to `Option`.

`Try` is almost the same as `Option`, but it lets you return a more meaningful error value. This helps the function caller understand what went wrong inside the function.

Just as `Option` has two sub-types, `Try` has two sub-types â€” `Success` and `Failure` â€” and the two sets of data types compare like this:

`Option  <=>  Try`
`Some    <=>  Success`
`None    <=>  Failure`

So basically anywhere you used `Option` before, you can also use `Try`. And where you used `Some` you now use `Success`, and instead of `None` you use `Failure`.

But the big difference is that when things go wrong, `Failure` contains an exception â€” the exception that occured inside the function. This is your functionâ€™s way to tell callers exactly what went wrong inside the function. Because of this, `Try` is generally more useful than `Option` when working with I/O functions.

Letâ€™s see what this looks like.

## Try/Success/Failure

Hereâ€™s a new version of `makeInt` that uses `Try` instead of `Option`:

`// you must first import these types:`
`import scala.util.{Try, Success, Failure}`

`def makeInt(s: String): Try[Int] =`
`    try`
`        Success(s.toInt)`
`    catch`
`        case e: NumberFormatException => Failure(e)`

Now when you call `makeInt`, youâ€™ll see these results in the success and failure cases:

`// success case`
`makeInt("1")      // Success(1)`

`// failure case`
`makeInt("one")    // Failure(java.lang.NumberFormatException:`
`                  //         For input string: "one")`

As shown:

*   You get a `Success` back when the conversion works. `Success` is a wrapper that contains the `Int`.
*   You get a `Failure` back when the process fails. `Failure` contains the exception message.

As a consumer of the function, the `Failure` case is now much more interesting, because it tells me what went wrong inside the function.

## Handling the result

As with `Option`, you handle a `Try` with a `match` expression and `for` expressions.

### pattern matching

This is what `Try` looks like with a `match` expression:

`makeInt(aString) match`
`    case Success(i) => println(s"Success: i = $i")`
`    case Failure(e) => println(s"Failed: msg = ${e.getMessage}")`

### for expressions

And this is what `Try` looks like when used with multiple strings that *can* be converted to integers in a `for` expression:

`val maybeSum: Try[Int] =`
`    for`
`        i <- makeInt("1")`
`        j <- makeInt("2")`
`        k <- makeInt("3")`
`    yield`
`        i + j + k`

`// result:  maybeSum == Success(6)`

and this is what it looks like when they *canâ€™t* be converted:

`val maybeSum: Try[Int] =`
`    for`
`        i <- makeInt("1")`
`        j <- makeInt("Hi mom!")`
`        k <- makeInt("3")`
`    yield`
`        i + j + k`

`// result:`
`maybeSum == Failure(java.lang.NumberFormatException:`
`                    For input string: "Hi mom!")`

And again â€” just like `Option` â€” whether you get a `Success` or `Failure` back from the `for` expression, you handle its result in a `match` expression:

`maybeSum match`
`    case Success(i) => println(s"Success: i = $i")`
`    case Failure(e) => println(s"Failed: msg = ${e.getMessage}")`

As shown, `Try` and `Option` are used in the same ways.

## A shorter version of that function

Iâ€™ll show later how you can write more concise versions of `makeInt` with `Option`, `Try`, and `Either`, but `Try` is a little unique in that you can simply pass your exception-throwing algorithm into `Try`â€™s constructor:

`import scala.util.{Try, Success, Failure}`

`def makeInt(s: String): Try[Int] = Try(s.toInt)`

Because `Try` returns the exception that your code can throw, its creators realized that there was no reason to make you write a `try`/`catch` expression in the body of your function. You can just wrap your exception-throwing code inside `Try` as shown, and if that exception is thrown, it will catch it for you, and return a `Failure`.

Similarly, if your exception-throwing algorithm requires multiple lines of code, just write it like this, using curly braces around the block of code:

`import scala.util.{Try, Success, Failure}`

`def makeInt(s: String): Try[Int] = Try {`
`    // some long`
`    // algorithm here`
`    s.toInt`
`}`

Lastly, if youâ€™re familiar with Scala, youâ€™ll know that what Iâ€™m showing may be (a) `Try`â€™s constructor, or it may be (b) an `apply` method in `Try`â€™s companion object. But however itâ€™s implemented, the great thing for you â€” the end user of its API â€” is that you write your code the same way.

## Pure functions cannot lie

Before moving on, Iâ€™ll again reiterate this about the signatures of pure functions: *they cannot lie*.

As shown in this example, the `makeInt` function screams loud and clear with `Try`, â€œIâ€™ll *try* to give you an `Int` if everything goes well, but something can wrong hereâ€:

`def makeInt(s: String): Try[Int] = ???`
`                        --------`

Summary: Whenever you see `Try` (or `Option`) as the return type of a function, you know that something can go wrong inside that function.

# 21\. FEH: Either

The last error-handling data type thatâ€™s built into Scala is named `Either`. Like `Option` and `Try`, `Either` has two sub-types named `Left` and `Right`, and they match up like this:

`Option  <=>  Try      <=>  Either`
`Some    <=>  Success  <=>  Right`
`None    <=>  Failure  <=>  Left`

Thatâ€™s a slight over-simplification, because what happens with `Either` is that `Right` and `Left` can contain *anything*. By convention, `Right` holds the success value and `Left` holds the error value, but technically you can use those two values however you like.

## makeInt with Either

That being said, hereâ€™s the `makeInt` function written to use `Either`. In this case Iâ€™ll return a `String` in the `Left` position:

`// no 'import' statements are needed for this`

`/**`
` * Left is a String.`
` */`
`def makeInt(s: String): Either[String, Int] =`
`    try`
`        Right(s.toInt)`
`    catch`
`        // for this example i convert the exception to a string`
`        case e: NumberFormatException => Left(e.getMessage)`

Now when you call `makeInt` with good and bad strings, youâ€™ll see these results:

`// success case`
`makeInt("1")      // Right(1)`

`// failure case`
`makeInt("one")    // Left(For input string: "one")`

In that example I return a `String` in the `Left` position, but I can also return an exception (or any other data type):

`/**`
` * The Left type is now an Exception.`
` */`
`def makeInt(s: String): Either[Exception, Int] =`
`    try`
`        Right(s.toInt)`
`    catch`
`        case e: NumberFormatException => Left(e)`

This functionâ€™s error value looks like this:

`// failure case`
`makeInt("one")   //Left(java.lang.NumberFormatException: For input string: "a")`

## Handling the result

Common ways to work with the result of an `Either` are `match` and `for` expressions.

The second version of `makeInt` returns an exception in the `Left` position, and this is how that function works in a `match` expression:

`makeInt(aString) match`
`    case Right(i) => println(s"Success: i = $i")`
`    case Left(e)  => println(s"Failed, exception = $e")`

And this is what that function looks like when its used with multiple strings that *can* be converted to integers in a `for` expression:

`val maybeSum: Either[Exception, Int] =`
`    for`
`        i <- makeInt("1")`
`        j <- makeInt("2")`
`        k <- makeInt("3")`
`    yield`
`        i + j + k`

`// result:  maybeSum == Right(6)`

As shown in the comment, in this situation, `maybeSum` has the value `Right(6)`. And this code shows what the Unhappy Path looks like when one or more strings *canâ€™t* be converted to integers:

`val maybeSum: Either[Exception, Int] =`
`    for`
`        i <- makeInt("1")`
`        j <- makeInt("Hi mom!")`
`        k <- makeInt("3")`
`    yield`
`        i + j + k`

`// result:`
`maybeSum == Left(java.lang.NumberFormatException: For input string: "Hi mom!")`

Here, `maybeSum` is a `Left`, and it contains that `NumberFormatException`.

And just like `Option` and `Try`, whether you get a `Right` or `Left` back from the `for` expression, you can handle its result in a `match` expression:

`maybeSum match`
`    case Right(i) => println(s"Success: i = $i")`
`    case Left(e)  => println(s"Failed: msg = ${e.getMessage}")`

Notice that when you use `Either`, both `Right` and `Left` are containers that contain the success value and error value, respectively.

## Reading an Either signature

In the second version of the `makeInt` function, the return value `Either[Exception, Int]` can read as, â€œIf the computation succeeds, Iâ€™ll get an `Int` back thatâ€™s wrapped in the `Right`. If it fails, Iâ€™ll get the exception in the `Left`.â€ The declaration of the two possible return types makes `Either` more flexible than the `Option` and `Try` types.

## Two technical points

There are at least two interesting technical points to know about the [`Either` data type](https://www.scala-lang.org/api/current/scala/util/Either.html).

First, as that Scaladoc page notes, `Either` represents a value that is one of two possible types, and this is technically known as a *disjoint union*.

Second, `Either` is *right-biased*. The Scaladoc states, â€œthis means that `Right` is assumed to be the default case to operate on.â€ When you use `Either` in `match` and `for` expressions as I showed, this doesnâ€™t matter. But when you want to work directly with `maybeSum`, such as calling a `map` method on it, thatâ€™s where this is important.

The key is that when you call `map` on `maybeSum` and it is a `Left`, `map` returns the `Left` value unchanged, as shown in the REPL:

`// when maybeSum is a Left:`
`scala> maybeSum.map(_ * 10)`
`val res0: Either[Exception, Int] =`
`    Left(java.lang.NumberFormatException: For input string: "Hi mom!")`

Conversely, when `maybeSum` is a `Right`, `map` and other methods work as desired:

`// when maybeSum is a Right:`
`scala> maybeSum.map(_ * 10)`
`val res1: Either[Exception, Int] = Right(60)`

## Pure functions cannot lie

Once again Iâ€™ll reiterate this point about the type signatures of pure functions: *they cannot lie*. As shown here, the `makeInt` function screams loud and clear, â€œIâ€™ll give you an `Int` in the `Right` position if everything goes well, but if something goes wrong, youâ€™ll get an `Exception` in the `Left`â€:

`def makeInt(s: String): Either[Exception, Int]`
`                        ----------------------`

Summary: Whenever you see `Either`, `Try`, or `Option` as the return type of a function, you know that something can go wrong inside that function.

# 22\. FEH: allCatch

Before we leave these error-handling lessons and get back to the change request for our `wc` application, I want to show how you can write those `makeInt` functions more concisely.

## More concise makeInt functions

You can make most of the `makeInt` functions I showed previously more concise by using a Scala type named `allCatch`. Cutting to the chase, its solutions to make `makeInt` much shorter look like this:

`import scala.util.{Try, Success, Failure}`

`// the allCatch type is here:`
`import scala.util.control.Exception.allCatch`

`// Option`
`def makeInt(s: String): Option[Int] =`
`    allCatch.opt(s.toInt)`

`// Either`
`def makeInt(s: String): Either[Throwable, Int] =`
`    allCatch.either(s.toInt)`

`// Try (Version 1: the approach shown earlier (preferred))`
`def makeInt(s: String): Try[Int] =`
`    Try(s.toInt)`

`// Try (Version 2)`
`def makeInt(s: String): Try[Int] =`
`    allCatch.withTry(s.toInt)`

As shown in the second `import` statement, `allCatch` is defined in the `Exception` object of the `scala.util.control` package, so you need to first import it, and then you can use it as shown.

The key with `allCatch` is that it does the work that the `try`/`catch` expression did in my previous examples: it returns the success value when the conversion succeeds (the happy path), and it catches exceptions when things go wrong and returns the desired error value (in the unhappy path).

## More information

The [`scala.util.control.Exception` Scaladoc page](https://www.scala-lang.org/api/current/scala/util/control/Exception$.html) has more information and examples of `allCatch` and other related solutions, such as how to handle logging when using shortcuts like this. Please see that page for more information on those techniques.

# 23\. FEH: Implementing wc with Try

Okay, given that background on how we handle possible errors in Scala, letâ€™s get back to our Word Count application. We left off at the point where our boss said to us, â€œUm, yeah, that `wc` function needs to handle a string that represents *the filename* that contains the document, not the *document* itself.â€

## The incorrect solution

To quickly re-state what I just wrote about functional error handling, recall that this is the incorrect solution, we *do not* write code like this in Scala/EOP:

`@throws Exception`
`def wc(filename: String) ...`

Exceptions short-circuit algebraic equations and blow up blueprints, so we donâ€™t do that.

## Working with a file

Having read the previous error-handling lessons, your algebraic-oriented brain should now be thinking that we need to change our previous function signature:

`def wc(document: String): VectorMap[String, Int]`

to something like this:

`def wc(filename: String): Option[?]`
`def wc(filename: String): Try[?]`
`def wc(filename: String): Either[?, ?]`

The basic idea is that files may not exist, or they may not be readable, so we use the error-handling types to account for those possibilities.

If we focus on just `Try` for a moment:

`def wc(filename: String): Try[?]`

an excellent question at this point is, â€œWhat goes inside that `Try` declaration?â€

### Tryâ€™s type

As we saw in the previous lessons, the type that goes inside `Try[]` is the *success case* data type. In this case â€” because the original `wc` function returns a `VectorMap[String, Int]` when it succeeds â€” our new functionâ€™s return type should look like this:

`def wc(filename: String): Try[VectorMap[String, Int]]`

To make that a little easier to see, hereâ€™s the success type, underlined:

`def wc(filename: String): Try[ VectorMap[String, Int] ]`
`                               ----------------------`

### Option and Either

To be thorough with our error-handling options, `Option` is declared the same way:

`def wc(filename: String): Option[ VectorMap[String, Int] ]`
`                                  ----------------------`

And as you know, with `Either` you declare both the failure and success types. The failure type can be anything, but itâ€™s usually an exception or a string, so its signature will typically be one of these:

`def wc(filename: String): Either[ Throwable, VectorMap[String, Int] ]`
`def wc(filename: String): Either[ String,    VectorMap[String, Int] ]`

I put extra spaces around those brackets to make things more obvious, but you usually donâ€™t do that, so our new function that reads a document from a given filename will have signatures look like these:

`def wc(filename: String): Try[VectorMap[String, Int]]`
`def wc(filename: String): Option[VectorMap[String, Int]]`

`def wc(filename: String): Either[Throwable, VectorMap[String, Int]]`
`def wc(filename: String): Either[String, VectorMap[String, Int]]`

## Building the new solution

Now letâ€™s look at the body of our new file-reading function.

### The Try solution

Again, if we focus only on the `Try` solution â€” which I prefer over `Option` for I/O-related functions, because we can see the exception when needed â€” Iâ€™ll start by renaming this new top-level function to `wcFromFile`:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]]`

As you can imagine, the first thing youâ€™ll do inside this function is to call a file-reading function. So far I know that Iâ€™ll give that function the filename, which is a `String`:

`def readFile(filename: String)`
`             ----------------`

And you also know two other things:

*   I just mentioned that I prefer to use `Try` for I/O functions, so this function should return `Try`
*   The function needs to return the document that it reads from that filename, and that document is a `String`

Those two items let us complete the functionâ€™s type signature:

`def readFile(filename: String): Try[String]`
`                                -----------`

Now that we know what `readFile` looks like, we add it as the first line to our new `wcFromFile` function:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]] =`
`    val maybeDocument: Try[String] = readFile(filename)`
`    ...`

### A verbose solution

So now `maybeDocument` either contains (a) a `String` version of the document, or (b) an exception. A verbose way to handle `maybeDocument` is the approach I showed earlier in the `makeInt` error-handling lessons, using a `match` expression:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]] =`
`    val maybeDocument: Try[String] = readFile(filename)`
`    maybeDocument match`
`        case Success(docAsString) => Success(wc(docAsString))   // [1]`
`        case Failure(e)           => Failure(e)                 // [2]`

As shown in Note 1, in the `Success` case I pass the document (`docAsString`) to the old `wc` function. If you look back at that function, youâ€™ll see that it has the type signature `VectorMap[String, Int]`. As you now know, this means that `wc` cannot fail. Because `wcFromFile` needs to return a `Try` type, I wrap this map in the `Success` type.

And then in the `Failure` case (Note 2), I return a new `Failure` instance that contains the exception that occurred when trying to read the file.

While this solution works, a problem with it is that Iâ€™m getting a `Try` from `readFile`, and then I unpack it into a `Success` or `Failure`, and then I re-pack it back into those types in the `match` expression. I can do better.

### A more concise solution

The more concise solution is to use the `map` method thatâ€™s available on the `Success` and `Failure` types. The way `map` works is that if itâ€™s called on:

*   `Failure`, it returns the exception
*   `Success`, `map` lets you operate on the success value however you want to

So again, the first step of the function body stays the same:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]] =`
`    val maybeDocument: Try[String] = readFile(filename)`
`    ...`

After that, I replace the `match` expression with a `map` method call on `maybeDocument`, which is a `Try`. Inside `map` I pass the document to the `wc` function:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]] =`
`    val maybeDocument: Try[String] = readFile(filename)`
`    maybeDocument.map(doc => wc(doc))`

The result of that expression has the type `Try[VectorMap[String, Int]]`, which matches our functionâ€™s return type.

If you prefer not using intermediate variables, you can write this solution more concisely, like this:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]] =`
`    readFile(filename).map(doc => wc(doc))`

or this, using Scalaâ€™s underscore shortcut in the anonymous function:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]] =`
`    readFile(filename).map(wc(_))`

Whichever approach you prefer, the key here is that both `Success` and `Failure` implement the `map` method, and with `Success`, `map` operates on the success value â€” so it works with the `wc` call â€” and with `Failure`, `map` just returns the exception it holds.

### The Either solution

Because `Either` is also a good solution for I/O functions, letâ€™s see how it works. First, its file-reading function signature looks like this:

`def readFile(filename: String): Either[Throwable, String]`

Next, its top-level function looks like this:

`def wcFromFile(filename: String): Either[Throwable, VectorMap[String, Int]]`

And finally, the short version of its function body looks like this:

`def wcFromFile(filename: String): Either[Throwable, VectorMap[String, Int]] =`
`    readFile(filename).map(wc(_))`

Because of its flexibility, `Either` is a bit more verbose, but this signature:

`Either[Throwable, VectorMap[String, Int]]`

means that if something goes wrong, youâ€™ll get an exception:

`Either[Throwable, VectorMap[String, Int]]`
`       ---------`

but if all goes well, youâ€™ll get the sorted map that weâ€™re really after:

`Either[Throwable, VectorMap[String, Int]]`
`                  ---------------------`

## One last point about types

I showed this before, so Iâ€™ll just briefly touch on this again here. These function signatures:

`def wcFromFile(filename: String): Try[VectorMap[String, Int]]`
`def wcFromFile(filename: String): Either[Throwable, VectorMap[String, Int]]`

are probably easier to read if we use Scala 3â€™s opaque types to create more meaningful type names like these:

`def wcFromFile(filename: String):`
`    Try[MapSortedByValueDesc[Word, Count]]`

`def wcFromFile(filename: String):`
`    Either[Throwable, MapSortedByValueDesc[Word, Count]]`

And lastly, if you really want to have some fun â€” and make your code easier to read â€” you can create *type aliases* like these:

`def wc(filename: String): WordCountMapTry`
`def wc(filename: String): WordCountMapEither`

With type aliases and opaque types, solutions like these are limited only by what you think is best, and easiest to read and maintain.

# 24\. Recap, and Whatâ€™s Next

As a very quick recap, so far in this book youâ€™ve seen:

*   Immutable variables
*   Immutable data structures
*   Pure functions
*   How to solve problems just by sketching pure function signatures
*   Expression-oriented programming
*   Algebraic substitution
*   Functional error-handling

Next, weâ€™ll build another complete example that uses all of these concepts. This time â€” to show more of the details â€” Iâ€™ll show more Scala code as we go through the process.

# 25\. Example #2: To-Do List (TDL)

In most of the remaining lessons of this book weâ€™re going to build a *To-Do List* (TDL) application that you can run at your operating system command line. The purpose of this is to show more of the nitty-gritty details involved in writing a Scala/EOP application, including how to compile and run it using a tool named [Scala-CLI](https://scala-cli.virtuslab.org/).

## How the app works

TDL is a command-line application that you run with `scala-cli`. To run it, clone this bookâ€™s Github repository, move into the `ToDoList` directory, and issue this command:

`$ scala-cli run .`

Or, if you prefer, use this shorter command:

`$ scala-cli .`

Both of those mean, â€œCompile the code in this directory, find a `main` method, and run it.â€

> When there are multiple `main` methods you have to add an additional option there, but with one `main` method, this command works.

When the app starts running, you can type the letter `h` to see help. That help output shows that the app accepts these single-letter commands:

`COMMAND           DESCRIPTION`
`-------           -----------`
`a [task]          add a to-do item`
`d [task number]   delete a task by its number`
`v                 view the list of tasks`
`q                 quit`
`h                 show this help text`

Given that background, this is what a small interaction with TDL looks like, where I add two tasks with the `a` command and then delete the first one with the `d` command:

`(Commands: a "task", d 1, v, q, h)`
`Yo: a wake up`
`1\. wake up`

`(Commands: a "task", d 1, v, q, h)`
`Yo: a brush teeth`
`1\. wake up`
`2\. brush teeth`

`(Commands: a "task", d 1, v, q, h)`
`Yo: a make coffee`
`1\. wake up`
`2\. brush teeth`

`(Commands: a "task", d 1, v, q, h)`
`Yo: d 1`
`1\. brush teeth`

So thatâ€™s how the app works.

## Rules for writing the app

To write the TDL app, Iâ€™ll use the same rules I followed so far in this book. It will use:

*   Immutable variables
*   Immutable data structures
*   Pure functions
*   Expression-oriented programming
*   Functional error-handling

Iâ€™ll also add this rule:

*   Any function that interacts with the outside world must return a `Try` value

I used this technique when reading the document from the file in the Word Count example, but now this is a hard rule.

## A flat-file database

I initially started to create this app using a SQL database and a Scala database library. However, once I dug into Scala database libraries, I saw that they almost all jump right into FP concepts. And because weâ€™re still building our way up to those concepts, I decided *not* to use that approach.

Instead, this application will use a â€œflat-file database.â€ This isnâ€™t a real database, itâ€™s just a file. For the TDL app it will contain a list of â€œTo Doâ€ items on separate lines, like this:

`Wake up`
`Make the coffee`
`Brush my teeth`
`Take a shower`

However, if youâ€™re ever interested in more advanced uses of a flat-file database, a common approach is to separate fields in the file with a field delimiter, such as a symbol. When you do that, your rows will look like this:

`|Alvin|Alexander|Talkeetna`
`|Fred|Flintstone|Bedrock`
`|Mary|Bailey|Bedford Falls`

So weâ€™ll write this database code in the following chapters, and the benefit of this is that youâ€™ll see how you use `Try` at the boundaries of an application to communicate with the outside world, and how that works with the rest of your code.

# 26\. TDL: The Database Class

When I think about how TDLâ€™s `main` method starts, I think that one of the first things it needs to do is create an instance of a `Database` class:

`@main`
`def ToDoList =`
`    val db = Database("./ToDoList.dat")`
`    ...`

In that code I pass `Database` the name of the file it should use as its flat-file database. Right away, this tells me that I need a `Database` class that takes a filename input parameter:

`class Database(val dbFilename: String):`
`    // methods go here ...`
`end Database`

As youâ€™ll see in the following lessons, weâ€™ll then define these functions inside that class, to mimic the way SQL functions typically work:

*   `insert`
*   `delete`
*   `selectAll`

> NOTE: Writing this code is the same as writing OOP code, where you have a class that takes a constructor parameter (`dbFilename`), and then the methods in that class use that parameter. The only difference is that I wonâ€™t mutate that parameter, so, as shown, I define it as a `val` parameter.

## About the â€˜Tryâ€™ rule

Recall my rule that any function that reaches out to the outside world must return the `Try` error-handling type. This is overkill for a flat-file database, but it helps if you recall that real database code typically accesses another server (or cluster) that may or may not be running when you call it. This is also just like calling a REST API that may or may not be running, across a network that may or may not be available.

In these situations, robust code *must* return an error-handling type like `Try` or `Either`, and for our purposes, Iâ€™ll use `Try`.

## How this affects Database

Given this rule, I sketch the `Database` class to have methods with these type signatures:

`class Database(dbFilename: String):`

`    def insert(record: String): Try[Unit] = ???`
`    def selectAll(): Try[Seq[String]] = ???`
`    def delete(indexToDelete: Int): Try[Int] = ???`

`end Database`

Iâ€™ll explain that code in the following chapters, but briefly:

*   `insert` returns `Try[Unit]`, and its `Success` and `Failure` results tell us if it worked
*   `selectAll` returns `Try[Seq[String]]`, which is a list of strings inside a `Try`.
*   `delete` returns `Try[Int]`, and its `Int` value indicates the number of rows deleted.

In all of those cases, if our â€œdatabase serverâ€ is down, the `Try` we get back will be a `Failure`, but if the server is up and running, we should get back a `Success`.

## Methods vs functions

As a final note, this is my personal standard about using the names â€œmethodsâ€ and â€œfunctionsâ€ when talking about Scala code:

*   When you define these inside a *class*, I refer to them as *methods*.
*   Anywhere else, I refer to them as *functions*.

This isnâ€™t a standard Scala naming convention, itâ€™s my own personal convention. It always feels weird to talk about *functional programming* while constantly using the term *method*, so thatâ€™s how I came up with this personal standard. Therefore, from here on out, Iâ€™ll refer to â€œmethods in the `Database` class.â€

# 27\. TDL: The insert Database Function

As a quick reminder, in the following lessons where weâ€™ll create database-related code, all of these functions will be placed inside a `Database` class that looks like this:

`class Database(dbFilename: String):`
`    // def insert = ???`
`    // def selectAll = ???`
`    // def delete = ???`
`end Database`

## insert

The first `Database` function weâ€™ll need is an `insert` function. Because this is just a flat-file database, this function will *append* a single new record to the database file. Therefore, I know that it takes a string as input, and I start to sketch the `insert` function like this:

`def insert(record: String)`

Next â€” and mostly because Iâ€™ve been through this process before â€” I know that I want this function to use another `writeToFile` function to do the actual file-writing. I know this because the `delete` and `update` functions Iâ€™ll write in the following lessons will require me to read in the entire file and then re-write it completely. So `writeToFile` will need to be able to both (a) append to a file and (b) completely overwrite the file (and I donâ€™t want to have a boolean `append` parameter in the `insert` function).

Therefore, letâ€™s forget about the `insert` function for a moment and first work on the `writeToFile` function.

## writeToFile

`writeToFile` will be another function inside the `Database` class, and because nobody outside of `Database` will need to access it, I start by making it private:

`private def writeToFile`

Next, because I know that `delete` and `update` will require me to completely re-write the file, I define it to accept a list of strings, which in the most generic sense in Scala is a `Seq[String]`:

`private def writeToFile(lines: Seq[String])`
`                        ------------------`

I also know that I want to set a boolean `append` flag when calling this function. This lets me declare that I want to overwrite the file, or append to it:

`private def writeToFile(lines: Seq[String], append: Boolean):`
`                                            ---------------`

Now the final thing to think about is its return type. As I mentioned in our rules, any function that communicates with the outside world *must* return a `Try` value, so that gives me this:

`private def writeToFile(lines: Seq[String], append: Boolean): Try[`
`                                                              ----`

And now the only question is, â€œWhat should the success value be inside `Try`?â€

Since I donâ€™t need any data back when writing a file â€” I just need a `Success` or `Failure` to know if it worked or now â€” this type can be `Unit`. (As mentioned before, this means that Iâ€™m not interested in the return type.) So I complete the function signature like this:

`private def writeToFile(lines: Seq[String], append: Boolean): Try[Unit] =`
`                                                              ---------`

### Implementing writeToFile

Next, Iâ€™m going to do something controversial and violate two of my rules: Iâ€™m going to use a `var` field and a `null` value. However, Iâ€™m *only* doing this because:

*   I suspect that many people reading this book are familiar with languages like Java and Kotlin, and therefore writing to files with Java classes and methods.
*   The more-correct solution requires a little more Scala knowledge that I donâ€™t want to get into yet. (I share this correct solution in the â€œ`Using`â€ lesson in the Appendix.)

Therefore, because this is Java/OOP code that uses the `java.io.*` classes, I write the body of the function as shown here, with comments describing the important parts:

`import java.io.*`
`import scala.util.{Try, Success, Failure}`

`/**`
`` * Notice that `dbFilename` comes in through a side door.``
` */`
`private def writeToFile(lines: Seq[String], append: Boolean): Try[Unit] =`
`    // i create this variable before the 'try' block because i need to`
`    // access it in the 'finally' block:`
`    var bw: BufferedWriter = null`

`    try`
`        // this is basically standard Java code that you use to`
`        // create a BufferedWriter:`
`        bw = BufferedWriter(FileWriter(File(dbFilename), append))`
`        // here i loop over every String in 'lines', and write each`
`        // String (one at a time) to the file. each String is`
`        // followed by a newline character:`
`        for line <- lines do bw.write(s"$line\n")`
`        // if the previous code does not throw an exception, flow`
`        // comes here, and we will return this Success value:`
`        Success(true)`
`    catch`
`        // if the previous code DOES throw an exception, control`
`        // comes here and we will return a Failure:`
`        case e: Throwable => Failure(e)`
`    finally`
`        // the 'finally' block always executes, so this is where`
`        // we release/close resources we opened. note that you need`
`        // to check if 'bw' is null first, because the previous code`
`        // may explode before 'bw' is bound to the BufferedWriter:`
`        if bw != null then bw.close`

I added a lot of comments in there to explain how that code works. So you can read that function more easily, here it is again without those comments:

`private def writeToFile(lines: Seq[String], append: Boolean): Try[Unit] =`
`    var bw: BufferedWriter = null    `
`    try`
`        bw = BufferedWriter(FileWriter(File(dbFilename), append))`
`        for line <- lines do bw.write(s"$line\n")`
`        Success(true)`
`    catch`
`        case e: Throwable => Failure(e)`
`    finally`
`        if bw != null then bw.close`

Again, this is a very Java/OOP solution to this problem, and if youâ€™d like to see the Scala solution, see the â€œ`Using`â€ lesson in the Appendix.

## Getting back to the insert function

Now that I have the `writeToFile` function, all I have to do is finish the `insert` function. I already sketched this portion of it:

`def insert(record: String)`

and now that I know I want to call `writeToFile`, I know that `insert`â€™s body should look like this:

`def insert(record: String) ...`
`    writeToFile(List(record), true)`

In that code, I wrap the `String` thatâ€™s received in a `List`, because `writeToFile` expects to receive a `Seq[String]`. And because I know that `writeToFile` returns a `Try[Unit]`, and I also want to return a `Try` from `insert`, I use that as this functionâ€™s return type as well:

`def insert(record: String): Try[Unit] =`
`    writeToFile(List(record), true)`

That completes the `insert` function.

# 28\. TDL: The selectAll Database Function

Next, the `selectAll` function is basically a â€œread a text fileâ€ function, so itâ€™s going to work a lot like the `insert` function, except weâ€™ll be reading instead of writing. Because the code is similar to the last lesson, Iâ€™ll move through it a little more quickly.

First, we know that we want a `selectAll` function, and it needs to return a `Try`:

`def selectAll(): Try`

Because the function returns all rows from the file, this means the success value is a `Seq[String]`:

`def selectAll(): Try[Seq[String]]`
`                     -----------`

In the last lesson I created a `writeToFile` function, but in this lesson that wonâ€™t be necessary, so Iâ€™ll add the file-reading code directly to `selectAll`. Conceptually this code is identical to the previous lesson, except that weâ€™re reading instead of writing:

`/**`
`` * Notice that `dbFilename` comes in through a side door.``
` */`
`def selectAll(): Try[Seq[String]] =`
`    var bufferedSource: scala.io.BufferedSource = null`
`    try`
`        bufferedSource = Source.fromFile(dbFilename)`
`        val lines = for line <- bufferedSource.getLines yield line`
`        Success(lines.toList)`
`    catch`
`        case t: Throwable => Failure(t)`
`    finally`
`        if bufferedSource != null then bufferedSource.close`

> Again, I wrote this code in a Java/OOP style, and you can see the â€œ`Using`â€ lesson in the Appendix to see the Scala way to write this code.

I tested this function, and in the `Success` case it returns a value like this:

`Success(List("a", "b", "c", "d"))`

and in the `Failure` case it returns an exception like this:

`Failure(java.io.FileNotFoundException: example.txt (No such file or directory))`

So now we have `insert` and `selectAll` functions. I *could* start working on the UI now, but for the sake of completeness, letâ€™s write a `delete` function before we switch to the UI.

# 29\. TDL: The delete Database Function

When you think about it, a `delete` function should either take (a) a string that represents the To-Do Item the user wants to delete, or (b) an index (row number) that should be deleted. Either approach is okay, but after I worked with the UI a little bit, I decided to go with the index-based approach, so Iâ€™ll share that here.

## delete

So far we know that we want a `delete` function that takes an index, so we have this:

`def delete(indexToDelete: Int)`

We also know that because it accesses the outside world, it should return a `Try`, so I add that:

`def delete(indexToDelete: Int): Try`
`                                ---`

And finally, because SQL `delete` queries return a count of the number of rows that are deleted, Iâ€™ll do the same thing, returning that count inside the `Try`:

`def delete(indexToDelete: Int): Try[Int] =`
`                                --------`

Technically Iâ€™m only allowing the user to delete one task a time, so this information isnâ€™t terribly useful. But, if you want to change the app to let the user delete multiple tasks at once, that value will be more useful.

## Writing the function body

Having written functions like this before, I know that the function body should work something like this:

*   Read the entire flat-file database into a list of strings
*   Remove the matching string from that list (using the index value)
*   Write the remaining list back to the file (overwriting the file, rather than appending to it)

There are a few ways to do this, but one approach is to use a `for` expression. Because I havenâ€™t shown those much yet, Iâ€™ll use that approach here. In this case Iâ€™m going to share the complete solution, and then describe how it works:

`def delete(indexToDelete: Int): Try[Int] =`
`    val maybeNumRowsDeleted = for`
`        rows           <- selectAll()`
`        newRows        =  CollectionUtils.removeElementByIndex(rows, indexToDelete)`
`        numRowsDeleted =  rows.size - newRows.size`
`        _              <- writeToFile(newRows, false)`
`    yield`
`        numRowsDeleted`
`    maybeNumRowsDeleted`

If you havenâ€™t seen this type of code before â€” fear not! â€” Iâ€™ll explain how it works.

Getting rid of the function signature for the time being, the code starts with the result of a `for` expression being assigned to a variable:

`val maybeNumRowsDeleted = for`

I know that this `for` expression returns the `Try[Int]` type, so I can also explicitly declare that here:

`val maybeNumRowsDeleted: Try[Int] = for`
`                         --------`

However, Iâ€™ll leave that off the following examples.

### The body as a for-expression

As mentioned in lesson on `for` expressions, a `for` expression always starts with a *generator*, and in our case the `selectAll` function serves as that generator:

`val maybeNumRowsDeleted = for`
`    // start with a generator:`
`    rows           <- selectAll()`

Recall that `selectAll` returns a `Try[Seq[String]]`, so at this point one of two things happens:

*   That `Try` is a `Failure`, and the `for` expression stops here, and `maybeNumRowsDeleted` will have that `Failure` value.
*   The `Try` is a `Success`, and the variable `rows` is a `Seq[String]`.

Thereâ€™s nothing for us to do about the `Failure` case, itâ€™s already handled for us, so we continue to write our code assuming we received a `Success`, and we continue on down the happy path.

What I want to do next is delete the element in that `Seq[String]` according to its index value. (Recall that this function gets that index passed to us.) So now what I do inside the `for` expression is remove that element from `rows`. This process yields a new `Seq[String]`, which I name `newRows`:

`val maybeNumRowsDeleted = for`
`    rows           <- selectAll()`
`    // remove the desired row, using its index value:`
`    newRows        =  CollectionUtils.removeElementByIndex(rows, indexToDelete)`

If my requirements were different I *could* just write `newRows` back to the database file, and weâ€™d be done. But my requirements state that I need to return the number of rows that were deleted. A simple way to do that is to subtract the size of `newRows` from `rows`. In theory â€” because this function only takes one index value, `newRows` should always be one row smaller â€” but if something is wrong with that index, it is possible that the result could be `0` instead of `1`.

Going back to the `for` expression, I add an expression to count the number of rows that were actually deleted:

`val maybeNumRowsDeleted = for`
`    rows           <- selectAll()`
`    newRows        =  CollectionUtils.removeElementByIndex(rows, indexToDelete)`
`    // count the number of rows deleted:`
`    numRowsDeleted =  rows.size - newRows.size`

Finally, I can write `newRows` to the database file. Remember that `writeToFile` returns a `Try`, so in real-world code youâ€™ll want to pay attention to that result. But for the purposes of this `for` expression, I thought it would be more interesting to show what to do if you *donâ€™t care about the return value of an expression inside a `for` expression*, so I wrote this:

`    _              <- writeToFile(newRows, false)`

The underscore character on the left side of this expression is the Scala way of saying that inside a `for` expression, â€œI donâ€™t care about this resulting value, so you can just discard it.â€ Again, in the real world youâ€™ll be more interested in that `Try`, but I wanted to show this technique.

When I add this in, the `for` expression now looks like this:

`val maybeNumRowsDeleted = for`
`    rows           <- selectAll()`
`    newRows        =  CollectionUtils.removeElementByIndex(rows, indexToDelete)`
`    numRowsDeleted =  rows.size - newRows.size`
`    // ignore the resulting value:`
`    _              <- writeToFile(newRows, false)`

Finally, because our `delete` function needs to return the number of rows that were deleted, we *yield* that value from the `for` expression, and it is bound to the variable named `maybeNumRowsDeleted`:

`val maybeNumRowsDeleted = for`
`    rows           <- selectAll()`
`    newRows        =  CollectionUtils.removeElementByIndex(rows, indexToDelete)`
`    numRowsDeleted =  rows.size - newRows.size`
`    _              <- writeToFile(newRows, false)`
`   // yield the count of rows deleted:`
`yield`
`    numRowsDeleted`

Note that you can also explicitly declare `maybeNumRowsDeleted`â€™s data type like this, if you prefer:

`val maybeNumRowsDeleted: Try[Int] = for ...`
`                         --------`

Iâ€™ve found that modern IDEs show that type for you, so in your code it isnâ€™t completely necessary. But when youâ€™re reading this code in a book, it can be more helpful to see that type here.

After this â€” in the final line of the `delete` function â€” I return this count:

`maybeNumRowsDeleted`

Technically the `maybeNumRowsDeleted` variable isnâ€™t needed. If you prefer to *not* use it, you can just return the result of the `for` expression as the result of the function, like this:

`def delete(indexToDelete: Int): Try[Int] =`
`    for`
`        rows           <- selectAll()`
`        newRows        =  CollectionUtils.removeElementByIndex(`
`                              rows, indexToDelete`
`                          )`
`        numRowsDeleted =  rows.size - newRows.size`
`        _              <- writeToFile(newRows, false)`
`    yield`
`        numRowsDeleted`

I suspect that most experienced Scala developers use this approach, but I showed the other approach first because I think it might be a little easier for people who are new to Scala.

So this is our complete `delete` function.

## Note

If youâ€™d like to see how the `removeElementByIndex` function is implemented in the `CollectionUtils` object, see the â€œGenericsâ€ lesson in the Appendix.

# 30\. TDL UI: Prompt The User

Now that Iâ€™ve shown in the *inside* of the application â€” the functions that read-from and write-to the database file â€” Iâ€™ll switch gears and look at the *outside* of the function: the UI code that the user interacts with.

In this code weâ€™ll continue to follow the rule that any function that interacts with the outside world must return `Try`. With the database code it helps to think that we were working with remote servers, and the same is true here: you can imagine that weâ€™re doing something like writing a REST API, and getting input from remote sources.

> NOTE: I started to create this as a REST example, but that gets into too many things that arenâ€™t important to our primary objectives. So Iâ€™m using the following â€œcommand-line UIâ€ approach to keep things as simple as possible while we work with functions that return `Try` values.

## Our main function

As I mentioned earlier, TDLâ€™s `main` method starts like this:

`@main`
`def ToDoList() =`

and I save that code in a file named `ToDoList.scala`. After that, I add the call to my `Database` class:

`@main`
`def ToDoList() =`
`    val db = Database("./ToDoList.dat")`

Now the next thing the application needs to do is prompt the user for their input. So weâ€™ll need a `promptUser` function.

## promptUser

Because `promptUser` reaches out into the outside world, it needs to return a `Try`. But because printing a couple of strings to STDOUT canâ€™t really fail (unless thereâ€™s something seriously wrong with your computer), I wonâ€™t use the `try`/`catch`/`finally` construct.

Instead Iâ€™ll use the `Try` shortcut that I showed earlier, where you just pass your block of code into `Try`â€™s constructor. Including the necessary `import` statements, that code looks like this:

`import scala.io.StdIn`
`import scala.util.{Try, Success, Failure}`

`def promptUser(): Try[Unit] = Try {`
`    println("\n(Commands: a \"task\", d 1, u 1, h, q, v)")`
`    print("Yo: ")`
`}`

In that code:

*   The `promptUser` function requires the two `import` statements shown
*   `promptUser` doesnâ€™t require any input parameters
*   Per the rule, it needs to return a `Try`
*   Because it canâ€™t really fail, I declare that it returns `Unit` inside the `Try`
*   The opening `Try {...` code tells us the code that follows is passed into `Try`â€™s constructor
*   In that code block, I prompt the user with a `println` call, followed by a `print`
*   I use `print` in the second line because it doesnâ€™t put a newline character after the string; that leaves the userâ€™s prompt on the same line as the string

## Organizing the code

Thatâ€™s all thatâ€™s needed to prompt a user for their input. However, knowing that Iâ€™m going to need a few other I/O-related functions, I want to get this code out of my main file. Because these functions are all related to I/O, letâ€™s create a new file named `IOHelper.scala`. Then weâ€™ll create an `IOHelper` object in it, and that object will contain my functions:

`import scala.io.StdIn`
`import scala.util.{Try, Success, Failure}`

`object IOHelper:`

`    def promptUser(): Try[Unit] = Try {`
`        println("\n(Commands: a \"task\", d 1, u 1, h, q, v)")`
`        print("Yo: ")`
`    }`

`end IOHelper        `

## Back to main

Now I can go back to my `ToDoList.scala` file and put this code in it:

`import IOHelper.*`

`@main def ToDoList() =`
`    val db = Database("./ToDoList.dat")`
`    promptUser()`

At this point Iâ€™m ignoring the fact that `promptUser` returns a `Try`, but Iâ€™ll get back to that shortly. Before doing that, letâ€™s write a function to read the userâ€™s input.

# 31\. TDL UI: Read Input

To read input from a user, we use the `readLine` function thatâ€™s in the `scala.io.StdIn` data type. Again â€” imagining that weâ€™re reading input in a REST service â€” we know that we want to return a `Try`:

`def readInput(): Try`

Because `readLine` returns a `String`, the function returns a `Try[String]`, and the complete function looks like this:

`def readInput(): Try[String] = Try {`
`    StdIn.readLine()`
`}`

Now I add this function to the `IOHelper` object:

`import scala.io.StdIn`
`import scala.util.{Try, Success, Failure}`

`object IOHelper:`

`    def promptUser(): Try[Unit] = Try {`
`        println("\n(Commands: a \"task\", d 1, u 1, h, q, v)")`
`        print("Yo: ")`
`    }`

`    def readInput(): Try[String] = Try {`
`        StdIn.readLine()`
`    }`

`end IOHelper`

At this point, if all I was going to do was prompt the user one time and then read their input, I could add `readInput` to my main method, like this:

`import IOHelper.*`

`@main def ToDoList() =`
`    val db = Database("./ToDoList.dat")`
`    promptUser()`
`    val input: Try[String] = readInput()`

After that I would handle the `input` value, most likely in a `match` expression.

*However*, this is not what I want. What I really want is to keep prompting the user inside some sort of loop. But first, letâ€™s write one more I/O function while weâ€™re in this neighborhood.

# 32\. TDL UI: Show Help

The other function I want to write while weâ€™re in this neighborhood is a â€œhelpâ€ function. Itâ€™s similar to `promptUser` in that it just prints to STDOUT, so I follow that same recipe:

*   Itâ€™s a function that returns `Try[Unit]`
*   I create the function using `Try`â€™s constructor (putting the `println` inside `Try{...}`.)

Hereâ€™s the new `showHelp` function, inside the `IOHelper` object:

`import scala.io.StdIn`
`import scala.util.{Try, Success, Failure}`

`object IOHelper:`

`    def promptUser(): Try[Unit] = Try {`
`        println("\n(Commands: a \"task\", d 1, u 1, h, q, v)")`
`        print("Yo: ")`
`    }`

`    def readInput(): Try[String] = Try {`
`        StdIn.readLine()`
`    }`

`    def showHelp(): Try[Unit] = Try {`
`        val text = """`
`        |  Possible commands`
`        |  -----------------`
`        |  a <task>         - add a to-do item`
`        |  h                - show this help text`
`        |  d [task number]  - delete a task by its number`
`        |  v                - view the list of tasks`
`        |  q                - quit`
`        """.stripMargin.trim`
`        println(text)`
`    }`

`end IOHelper`

## Multiline strings

Whatâ€™s new in this function is that it uses a multiline `String`. You create a multiline string in Scala using triple-quotes, as shown. The use of triple-quotes, the character at the beginning of each line, and then the `stripMargin` and `trim` method calls on the string turns a string like this:

`val s = """`
`    |Alvin Alexander`
`    |123 Main Street`
`    |Talkeetna, AK 9967`
`""".stripMargin.trim`

into a left-aligned string that prints like this:

`Alvin Alexander`
`123 Main Street`
`Talkeetna, AK 9967`

For more information on multiline strings, see my blog post, [How to create multiline strings in Scala](https://alvinalexander.com/scala/how-to-create-multiline-strings-heredoc-in-scala-cookbook/)

# 33\. JIT: Using Option and Try in for-Expressions

Before we get into the next TDL lesson, I need to make sure youâ€™re familiar with how the `Option`, `Try`, and `Either` error-handling types work in `for` expressions.

## Option

When you have a function like this that returns an `Option`:

`import scala.util.control.Exception.allCatch`

`def makeInt(s: String): Option[Int] =`
`    allCatch.opt(s.toInt)`

You can use that function in a `for` expression to yield a result:

`val rez: Option[Int] =`
`    for`
`        a <- makeInt("1")`
`        b <- makeInt("2")`
`        c <- makeInt("3")`
`    yield`
`        a + b + c`

`// rez == Some(6)`

To make this simpler, letâ€™s get rid of `makeInt` and replace it with just `Some` values:

`val rez: Option[Int] =`
`    for`
`        a <- Some(1)`
`        b <- Some(2)`
`        c <- Some(3)`
`    yield`
`        a + b + c`

As shown in that code, I declare that `rez` has the type `Option[Int]`. When you use one or more `Option` values in a `for`/`yield` expression, the resulting value will also be an `Option`, as indicated there. So thatâ€™s the first important thing to know:

> When a `for` expression works with `Option` values and yields a result, that result is also an `Option`.

A second key to know is that *inside* the `for` expression and `yield` area, the values `a`, `b`, and `c` have the â€œsuccessâ€ type thatâ€™s inside the `Option`. Restating this second key point:

> Inside the `for` and `yield` areas, the values `a`, `b`, and `c` have the data type thatâ€™s inside the `Option`. In those two areas you work with the â€œsuccessâ€ type thatâ€™s *contained* within the `Option`.

## Try works the same way

And then a third important thing to know is that `Try` works the same as `Option`:

`import scala.util.{Try, Success, Failure}`

`val rez: Try[Int] =`
`    for`
`        a <- Success(1)`
`        b <- Success(2)`
`        c <- Success(3)`
`    yield`
`        a + b + c`

`// rez == Success(6)`

In this `for` expression the same two keys apply:

*   When a `for` expression works with `Try` values and yields a result, the result is a `Try`.
*   Inside the `for` and `yield` areas, the values `a`, `b`, and `c` have the â€œsuccessâ€ data type thatâ€™s inside the `Try`. (In those two areas you work with that success type.)

(For *many* more details, see my book, [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book).)

# 34\. JIT: for Loops, Generators, and Guards

If youâ€™re not familar with Scala, youâ€™ll need to know about `for` loops, generators, and guards before we work on the next aspect of the TDL app.

## Generators

The first key is that every `for` loop begins with a generator. A *generator* is a source of data, such as a list or stream. The simplest possible generators look like this:

`for i <- 1 to 3 do println(i)    // 1st example`

`val xs = List(1, 2, 3)           // 2nd example`
`for x <- xs do println(x)`

Those are `for` *loops*. Theyâ€™re called loops â€” and not expressions â€” because they loop over those values for some side effect, which is printing in this case.

Conversely, `for`/`yield` combinations are called *expressions* because they *yield* a value, and you typically assign that value to a variable:

`val xs = List(1, 2, 3)`
`val ys = for x <- xs yield x * 2`

You often use a `for`/`yield` expression to write a function:

`def double(xs: List[Int]): List[Int] =`
`    for x <- xs yield x * 2`

When youâ€™re new to this syntax, this style may be easier to read:

`def double(xs: List[Int]): List[Int] =`
`    for`
`        x <- xs`
`    yield`
`        x * 2`

## Multiple generators

`for` loops and expressions can have as many generators as you need for your algorithm:

`val rez =`
`    for`
`        i <- 1 to 2`
`        j <- 3 to 4`
`        k <- 5 to 6`
`    yield`
`        i + j + k`

`// rez: Vector(9, 10, 10, 11, 10, 11, 11, 12)`

As shown in the comment, the result of this `for` expression is a `Vector` that contains the list of integers shown. (`Vector` is a specific type of sequence (`Seq`) that is immutable, and generally has very good performance in many different situations.)

## Guards

*Guards* are basically `if` conditions that you add to the first part of `for` loops and expressions, and they look like this:

`val newValues =`
`    for`
`        i <- 1 to 5`
`        j <- 6 to 10`
`        if i > 3`
`        if j < 7`
`    yield`
`        i + j`

`// newValues: Vector(10, 11)`

As shown, you can add as many generators and guards as you need for your algorithm.

> As I mention in my other books, the benefit of Scalaâ€™s `for` syntax is that it separates your generators and guards (in the first section) from your business logic (which comes in the second section, after the `do` and `yield` keywords).

# 35\. JIT: Code Blocks (Closures)

Before we get into the next TDL lesson, I need to cover a Scala language feature I refer to as *code blocks*, or *blocks of code*. Iâ€™ve seen in other languages that this feature can be called a *closure* (but I think there are multiple definitions of that term).

In short, you create a block of code in Scala using curly braces, like this:

`val a = {`
`    // a block of code`
`    println("hi mom")`
`    42`
`}`

The result of a code block is its final value. In this example that value is the integer `42`, so if you want to explicitly delare `a`â€™s type, itâ€™s an `Int`:

`val a: Int = {        // <== explicitly set the type`
`    // a block of code`
`    println("hi mom")`
`    42`
`}`

Notice that any legal Scala code can be inside that code block, such as the side effect of printing to STDOUT. But from Scalaâ€™s perspective, its return type is `Int`.

You can demonstrate this for yourself in the Scala REPL by passing a code block to its `:type` command:

`scala> :type { println("hi"); 42 }`
`Int`

`scala> :type { println("hi"); "dude" }`
`String`

Again, notice that the *type* of the code block is that last value returned by it. And if that last value is something that yields `Unit`, thatâ€™s the blockâ€™s type:

`scala> :type { val a = 73; println("hi") }`
`Unit`

As we get ready for the next lesson, being aware of code blocks in Scala is one thing youâ€™ll need to know.

# 36\. JIT: Recursion

The other programming technique youâ€™ll have to have some awareness of before the next lesson is *recursion*. Recursion can be really fun, and itâ€™s an important FP technique, so I spend over 50 pages explaining it in [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book).

## Writing a recursive function

In short, a recursive function is a function that calls itself. To demonstrate this, letâ€™s create a recursive function that â€œcounts downâ€ to `0`. The idea is that you give it some integer, and it prints down to `0`, as shown in the REPL:

`scala> countdown(3)`
`3`
`2`
`1`

Right away you can see that this function takes an `Int` parameter:

`def countdown(i: Int)`

You can also see that it prints its result, and doesnâ€™t return anything, so its return type is `Unit` (which is like `void` in Java and other languages):

`def countdown(i: Int): Unit =`

Normally I implement most recursive functions using `match` expressions, but to keep this familiar for OOP developers, Iâ€™ll use an `if`/`then` expression here.

The first thing I usually do when I write a recursive function is to specify its *end* or *stop* condition. In this case, I know that I want the recursion to stop when the `Int` parameter is `0`, so I write that condition first:

`def countdown(i: Int): Unit =`
`    if i == 0 then`
`        // STOP HERE`

At this point I know two things: (a) I want the recursive calls to stop here, and (b) the function needs to return `Unit`. Therefore, I return the `Unit` *value* â€” `()` â€” here:

`def countdown(i: Int): Unit =`
`    if i == 0 then`
`        ()`

The symbol `()` is the one and only instance of the `Unit` type, and as youâ€™ll see, this is how the recursive calls stop: they hit this `if` condition, `()` is yielded, and the recursive calls unroll.

Now that I have the stop condition I want, I write the rest of the algorithm, i.e., the portion of the code that calls itself. Here I know from the functionâ€™s output that I want to do two things: (a) print the current value of `i`, and (b) make the recursive call.

An important part of the second step is that I reduce the value of `i` by `1` when making the call. If I fail to do this, the recursion will continue forever, so this is another key:

`def countdown(i: Int): Unit =`
`    if i == 0 then`
`        ()`
`    else`
`        println(i)`
`        countdown(i - 1)   // the recursive call`

I donâ€™t want to make light of it, but basically thatâ€™s all there is to recursion. Please verify that code in the REPL, and make sure youâ€™re comfortable with it.

## An example with a match expression

A fun recursive algorithm to write is a â€œsumâ€ algorithm for a `List[Int]`. A key here is to know that a Scala `List` is implemented just like a *Lisp* list, as a series of *cons* cells that end with a `Nil` value:

`1 :: 2 :: 3 :: Nil`

I believe this is the type of linked-list youâ€™re taught in college, so Iâ€™m going to assume that youâ€™ve at least seen or heard of this before, but the key is that ending `Nil` value.

Getting into the algorithm, we know that we want to write a sum function:

`def sum`

It takes a `List[Int]` parameter:

`def sum(list: List[Int])`

and it returns a sum of the ints:

`def sum(list: List[Int]): Int`

I also stated that I want to implement this with a `match` expression:

`def sum(list: List[Int]): Int = list match`

Again, I like to write the *stop* condition first, and the stop condition when you work on a `List` is always the `Nil` value:

`def sum(list: List[Int]): Int = list match`
`    case Nil =>`

### Identity value

One reason Iâ€™m sharing this example is that it also helps to know a mathematical concept called an *identity value (or element)*. In short, when youâ€™re working with (a) a set of integers and (b) a sum algorithm, the identity element is the value `0`. This means that when you sum a list of integers, the value `0` adds nothing to that sum.

Similarly, the value `1` is the identity value for (a) a list of integers along with (b) a *product* algorithm: when you multiply an integer by `1`, it doesnâ€™t modify the value. This is a key concept to know when working with recursion.

### Back to sum

Getting back to the `sum` function, the identity element for a sum algorithm tells me that the stop condition for the recursion is to yield the value `0`:

`def sum(list: List[Int]): Int = list match`
`    case Nil => 0`

Next, I need to add the recursive call. The way you do this with `match` expressions looks like this:

`def sum(list: List[Int]): Int = list match`
`    case Nil =>`
`        0`
`    case head :: tail =>`
`        head + sum(tail)`

Hereâ€™s how that works:

*   On the left side of the `case`, I break `list` into two elements, `head` and `tail`
*   Notice that those are separated by the `::` symbol
*   When working with a `List`, that means `head` is a variable that contains a single element (an `Int`), and `tail` is a variable that contains the rest of the list (an `List[Int]`)
*   After that, this last line of code can be read as, â€œAdd the `head` element to the sum of all remaining elementsâ€:

`head + sum(tail)`

Now if you paste that function into the REPL with a sample `List[Int]`, youâ€™ll see a result like this:

`scala> sum(List(1,2,3))`
`val res0: Int = 6`

## Tail recursion

As you get into recursion, youâ€™ll also want to learn about *tail recursion*, and if youâ€™re programming on the JVM, youâ€™ll want to make sure you know about stacks and frames. I cover all of this in more than 50 pages of recursion content in my book, [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book).

# 37\. TDL UI: Handling User Input

Now that youâ€™ve seen that background on *code blocks* and *recursion*, itâ€™s time to write a loop where we (a) prompt the user for their input, (b) read that input, (c) process it, and then prompt them again.

As you saw in the `delete` function I wrote in the database code, I used a `for` expression to work with `Try` values. If itâ€™s been a while since you looked at that code, I recommend looking back at it now to see how it worked, because weâ€™re about to do something similar.

## Looping; input

Right now we have almost everything we need to prompt a user and read their input. We donâ€™t have a way to *process* their input, but we can fake that for the time being. What I really want to do right now is focus on how to create a loop so we can stay in this cycle as long as the user wants:

1.  Prompt the user for input
2.  Read their input
3.  Handle that input (presumable by calling our database functions)
4.  Go back to Step 1

Because both `promptUser` and `readInput` both return `Try` values, the way we do this in Scala is to perform that loop with a `for` expression. So far, our main method starts like this:

`@main`
`def ToDoList =`
`    val datafile = "./ToDoList.dat"`
`    val db = Database(datafile)`
`    val processor = InputProcessor(db)`

So after this, Iâ€™ll define a method here that Iâ€™ll name `mainLoop`:

`def mainLoop(): Try[Unit] = for`

From past experience I know that `mainLoop` will not require any input parameters, and it will also return `Unit` wrapped in a `Try`. Iâ€™ll explain this more shortly, but letâ€™s push on for the moment.

## Prompting for input

So now our mindset is that weâ€™re writing our main loop. Therefore, the first thing we want to do is prompt the user for their input, so I add this line:

`def mainLoop(): Try[Unit] = for`
`    _ <- promptUser()`

I showed this syntax earlier, so Iâ€™ll just say that this can be read as, â€œPrompt the user for their input. Because `promptUser` returns a `Unit` value inside a `Try`, I donâ€™t care about that value, so ignore it.â€ We use the `_` character on the left side of the `<-` operator to say, â€œI donâ€™t care about this value.â€

## Reading the input

The next thing we want to do in the loop is to read the userâ€™s input, so I add that in:

`def mainLoop(): Try[Unit] = for`
`    _     <- promptUser()`
`    input <- readInput()`

This binds the userâ€™s input to the variable I named `input`. Whatever they type in before they press the [Enter] key is going to be a `String` thatâ€™s assigned to the `input` variable.

## Handling the input

Next, our application needs to process the userâ€™s input. As I showed in the introduction to this To-Do List example, a user types this to add a new task with the value `"Wake up"`:

`a Wake up`

and they type this to delete the first task:

`d 1`

and so on; they use the other commands we allow.

So now we need some sort of processor or handler to process these strings that we receive. For now Iâ€™m not going to implement this processor; Iâ€™ll just create a â€œdo nothingâ€ function that has the correct signature.

As usual, I start by sketching the signature of the desired function. Iâ€™ll call this function `handleUserInput`, and I know itâ€™s going to take a string input parameter:

`def handleUserInput(input: String)`

At this point â€” to complete the function signature â€” you have to think forward a little bit: `handleUserInput` is going to receive the user input as a string, itâ€™s going to attempt to process it, and then interact with our database. Because our database functions all return `Try`, this function should also return `Try`, so I add that:

`def handleUserInput(input: String): Try`
`                                    ---`

Next, because this function will always result in printing some output to STDOUT, it will have no return value, or at least no return value that we are interested in. Whenever this is the case, we declare that the function returns `Unit`, a `Unit` wrapped in a `Try`:

`def handleUserInput(input: String): Try[Unit]`
`                                    ---------`

And now â€” because I donâ€™t want to process that user input yet â€” Iâ€™ll just implement this function with a `println` statement:

`def handleUserInput(input: String): Try[Unit] =`
`    // todo: implement this function`
`    println("handleUserInput called")`

## Back to the main loop

At this point we *could* add that function call to our `mainLoop` function, like this:

`def mainLoop(): Try[Unit] = for`
`    _     <- promptUser()`
`    input <- readInput()`
`    _     <- handleUserInput(input)`
`    // hmm, still need to do something here ...`
`yield ()`

Note that here I do a few things. First, `handleUserInput` doesnâ€™t return anything interesting, so I use the `_` on the left side of the `<-` symbol.

Second, I added a `yield ()` to the end of the `for` expression. The `()` characters represent the one and only `Unit` value in Scala. Put another way, any time you need to return a `Unit` *value* from a function, you return `()`. (That is, `()` is an instance of `Unit`, its one and only instance.)

So, `yield ()` means that this `for` expression returns `Unit`. But, because the expression works with `Try` values, that `Unit` value is wrapped in a `Try`. Thatâ€™s why the function declaration begins like this:

`def mainLoop(): Try[Unit] = for ...`

## The problem

However, the problem we have is that if we call `mainLoop` right now, it wonâ€™t really loop; it only runs once. It prompts the user, reads their input, processes it, and then quits. We still need some way for our loop to, well, loop.

When youâ€™re working with immutable variables, the solution to this problem is almost always the same: recursion. Inside our `for` expression we just need to call `mainLoop`, so it invokes itself again. Iâ€™ll format that code so it looks like this:

`def mainLoop(): Try[Unit] = for`
`    _     <- promptUser()`
`    input <- readInput()`
`    _     <- {`
`                handleUserInput(input);`
`                mainLoop()`
`             }`
`yield ()`

You can format it in different ways, but the important thing is that this code:

`_     <- {`
`            handleUserInput(input)`
`            mainLoop()`
`         }`

can be read as, â€œEverything inside the curly braces is one block of code. Inside that block, first handle the userâ€™s input. Then, when that function returns, call `mainLoop` again.â€

So now `mainLoop` is called again, and it starts a `for` expression, and itâ€™s first step is to prompt the user again for their input.

And this is a key thing to know:

> When youâ€™re working with immutable variables and need to perform a loop, you use recursion instead.

In other â€œloopingâ€ situations you can use Scalaâ€™s collections methods instead of recursion, but for a situation like this, recursion is the answer.

## The complete â€˜mainâ€™ code

Now we can look at the complete main method. The only thing new that I add to it here is an initial call to `mainLoop` to get things running. I note this with a comment near the bottom of this code.

`@main`
`def ToDoList =`

`    val db = Database("./ToDoList.dat")`
`    val processor = InputProcessor(db)`

`    def mainLoop(): Try[Unit] =`
`        for`
`            _     <- promptUser()`
`            input <- readInput()`
`            _     <- {`
`                        handleUserInput(input)`
`                        mainLoop()`
`                      }`
`        yield`
`            ()`

`    // this starts the application running:`
`    mainLoop()`

`end ToDoList`

Notice that I define `mainLoop` inside the `ToDoList` function, which is our applicationâ€™s â€œmain method.â€ Itâ€™s not necessary to define `mainLoop` inside `ToDoList`, but I do it just to show you another thing you can do with Scala.

The way this code works is:

*   Scala sees `@main` before the `ToDoList` method, and recognizes it as a main method
*   A main method is the entry point to the application, so this function starts running
*   The first couple of lines are read
*   The `mainLoop` function definition is read
*   The `mainLoop` function is run as the last line of `ToDoList`, and this starts the process of prompting the user and reading their input

And now that we have a loop, we can go back to work on processing the userâ€™s input.

# 38\. An InputProcessor Class

Because â€œinput processingâ€ can be thought of as one thing â€” one concept â€” Iâ€™ll create an `InputProcessor` class to handle all input processing:

`class InputProcessor`

Also, because I know that this code is going to need my database functions, Iâ€™ll add that as a constructor parameter:

`class InputProcessor(db: Database)`

And because I know that the database functions return the `Try` error-handling data type, I add that `import` statement to my code:

`import scala.util.{Try, Success, Failure}`

`class InputProcessor(db: Database)`

## Handling user input

So what we need now is a `handleUserInput` function. I created that dummy one earlier that just has a `println` statement, but now Iâ€™ll show what it really needs to do, as I put it inside the `InputProcessor` class:

`class InputProcessor(db: Database):`

`    def handleUserInput(input: String): Try[Unit] = input match`
`        case "q" =>`
`            ???`
`        case "h" =>`
`            ???`
`        case "v" | "l" =>`
`            ???`
`        case add if add.startsWith("a ") =>`
`            ???`
`        case del if del.startsWith("d ") =>`
`            ???`
`        case _ =>`
`            ???`
`    end handleUserInput`

`    // more code here ...`

`end InputProcessor`

As shown, my plan is to handle the processing of the different commands the user can enter with a `match` expression. Inside that expression, each `case` handles a different command the user can enter.

(NOTE: There are other ways to handle this, but Iâ€™m trying to keep the code simple.)

So now the next task is to implement the code for each of those cases. (Or *patterns*, because `match` expressions are used in Scala to implement *pattern matching*.)

> One thing to make clear here is that because the `InputProcessor` class has the `db` constructor parameter â€” which is an instance of my `Database` class â€” all of these functions will have access to that `db` parameter. Furthermore, that instance is completely initialized in the main method before itâ€™s passed into this class.

# 39\. TDL UI: Implementing handleUserInput

Now that we know that we want a `handleUserInput` function, letâ€™s start working on it. As usual I begin with a sketch of the functionâ€™s signature, which we know from the last lesson:

`def handleUserInput(input: String): Try[Unit]`

What this function needs to do is to branch off into different directions based on the user input. As I showed in the introduction to the To-Do List app, it is written to accept these commands:

*   `q`, to quit
*   `a`, to add a new item
*   `d`, to delete an item
*   `h`, to show help
*   `v` or `l` (lowercase `L`), to list items

In other languages you might handle this situation with an `if`/`then`/`else` structure, and in Scala you *can* do that, but thereâ€™s also a different way: a `match` expression.

`match` expressions let you perform *pattern matching* on a given value, and the way it works when you use `match` as the body of a function is that you start like this:

`def handleUserInput(input: String): Try[Unit] = input match`
`                                                -----------`

This is a way of saying, â€œWeâ€™re about to perform some pattern matching on the `input` variable.â€

What you do then is start writing the *cases* that you want to match. For our function we know what strings we want to match against, so I sketch those cases like this:

`def handleUserInput(input: String): Try[Unit] = input match`
`    case "q" =>`
`        ???`
`    case "h" =>`
`        ???`
`    case "v" | "l" =>`
`        ???`
`    case add if add.startsWith("a ") =>`
`        ???`
`    case del if del.startsWith("d ") =>`
`        ???`
`    case _ =>`
`        ???`

Believe it or not, thatâ€™s actually the complete function body, except that we now need to fill in those `???` areas.

## Explaining the cases

Hereâ€™s a brief discussion of each `case`. These first two cases are the simplest, and they can be read as, â€œWhen you see this exact string, do the thing on the right side of the `=>` symbolâ€:

`case "q" =>`
`case "h" =>`

So if `input` is a `"q"`, do the first thing, but if itâ€™s an `"h"`, do the second thing.

> Just as in other programming languages, strings like `"q"` and `"h"` are called string literals.

The third case is similar to the first two, except this one can be read as, â€œIf `input` is a `"v"` *or* an `"l"`, do the thing on the right side of the `=>` symbolâ€:

`case "v" | "l" =>`

With this syntax you can string together as many alternatives as you want, so if you also want to accept an `"s"` (for â€œshowâ€), write this:

`case "v" | "l" | "s" =>`

In the next pattern, things get more interesting:

`case add if add.startsWith("a ") =>`

This isnâ€™t a perfect use-case for this syntax, but for now you can read it as, â€œCreate a variable named `add` from the variable `input`, and if the string `add` starts with the letter `a` followed by a blank space, do the thing on the right side of the `=>` symbol.â€ And then you use the variable `add` on the right side of the expression.

Where this syntax really shines is when you create an expression that makes `add` different from `input`. I donâ€™t have a need to do that here, but I wanted to show this as another technique for Scala tool belt.

And then I use the same technique for the next `case` as well:

`case del if del.startsWith("d ") =>`

The final `case` looks like this, and it means â€œmatch everything elseâ€:

`case _ =>`

So if `input` doesnâ€™t match any of the previous cases, control comes to this `case`, and whatever is on the right side of this `=>` symbol is what gets executed. Itâ€™s a â€œcatch allâ€ `case`, and in our code, when they user types anything other than the allowed commands, control comes here.

> In Scala, the `=>` used to be called the â€œrocketâ€ symbol by some people, though that never really caught on. But as I describe it in my other books, itâ€™s really a *transformer* symbol. Whenever you see it, it means that the thing on the left is being transformed into the thing on the right, so in `match` expressions we match the cases on the left, and transform them into the values on the right of the `=>`.

## Remember EOP

Itâ€™s also important to remember that every line of code in Scala is an expression. So with `match` expressions, those values on the right side of each `=>` are the values that are returned from the expression.

In this function, because I already declared that the function returns `Try[Unit]`:

`def handleUserInput(input: String): Try[Unit]`
`                                    ---------`

this means that my expectation is that every expression on the right side of those `=>` symbols will return `Try[Unit]`. Weâ€™ll see how that works as we implement each of those cases in the following lessons.

# 40\. TDL UI: Handling â€œQuitâ€

The first thing to do in `handleUserInput` is to handle the â€œquitâ€ case. Basically all we have to do is call `System.exit(0)` when we see that the user has typed the letter `"q"`. However, because `handleUserInput` returns `Try[Unit]`, we need to wrap that call in a `Try`, like this:

`def handleUserInput(input: String): Try[Unit] = input match`
`    case "q" =>`
`        Try(System.exit(0))     // <== THE NEW CODE`
`    // more cases here ...`

Because `System.exit` returns `Unit`, this works as desired.

## A Scala REPL tip

Note that you can use the Scala REPLâ€™s `:type` command to verify that `System.exit` returns `Unit`:

`scala> :type System.exit(0)`
`Unit`

So thatâ€™s all we have to do for the â€œQuitâ€ use case.

# 41\. TDL UI: Handling â€œHelpâ€

Another relatively simple `case` we can knock out is the â€œHelpâ€ use case. This is when the user types the letter `"h"` to see our help text.

Because we implemented the `showHelp` function in the `IOHelper` object earlier, and because that function returns `Try[Unit]`, all we have to do is call it in our second `case` statement:

`def handleUserInput(input: String): Try[Unit] = input match`
`    case "q" =>`
`        Try(System.exit(0))`
`    case "h" =>`
`        IOHelper.showHelp()     // <== THE NEW CODE`

That function prints our â€œhelp textâ€ to STDOUT using `println` statements â€” and because that function follows our rule that any time we reach into the outside world, we return `Try` â€” that function â€œjust worksâ€ here.

# 42\. TDL UI: Handling â€œViewâ€

Next up, the â€œViewâ€ use case is a little more complicated than the first two. Basically this code needs to attempt to read the database and then take one of two possible actions from there:

*   In the success case, it prints the list of to-do items
*   In the failure case, it prints an error message about the database being inaccessible

This is straightforward to do because we already wrote the `selectAll` database method previously, and it returns a `Try` value, so we just need to handle its `Success` and `Failure` cases in a `match` expression.

Hereâ€™s the code that does what I just described, with a few comments to make those steps clear:

`def handleView(): Try[Unit] = Try {`

`    // attempt to read all the tasks from the database.`
`    // this function returns a list of strings, wrapped inside`
`    // a Try:`
`    val res: Try[Seq[String]] = db.selectAll()`

`    // handle the Success and Failure cases:`
`    res match`
`        case Success(tasks) =>`
`            // in the Success case we get a list of tasks (strings),`
`            // so print those out in a nice format:`
`            printTasks(tasks)`
`        case Failure(t) =>`
`            // in the Failure case, where we canâ€™t access the database,`
`            // print the exception (a Throwable) we get from selectAll:`
`            System.err.println(t)`
`}`

`private def printTasks(tasks: Seq[String]): Unit =`
`    for`
`        (task, count) <- tasks.zip(Stream from 1)`
`    do`
`        println(s"${count}. $task")`

Hereâ€™s a shorter version of `handleView`, without the comments:

`def handleView(): Try[Unit] = Try {`
`    val res: Try[Seq[String]] = db.selectAll()`
`    res match`
`        case Success(tasks) =>`
`            for`
`                (task, count) <- tasks.zip(Stream from 1)`
`            do`
`                println(s"${count}. $task")`
`        case Failure(t) =>`
`            System.err.println(t)`
`}`

Note that the cases of the `match` expression print to STDOUT and STDERR, so they both have the return type `Unit`. And because the entire function body is wrapped in a `Try` constructor call:

`def handleView(): Try[Unit] = Try { // body here ... }`
`                              ------------------------`

this means that both cases of this function correctly result in returning the `Try[Unit]` type.

> Again, if any of this seems like overkill, remember to imagine that weâ€™re accessing a remote database or REST service, and in the real world, those things may be down.

# 43\. TDL UI: Handling â€œAddâ€

Next up, the â€œAddâ€ use case is a little bit more complicated. Going back to our UI, we know that when a user wants to add a new task, they type things like this with the `a` command:

`a wake up`
`a brush teeth`
`a take a long hot shower`

So the first thing we need to do is to separate that *add* command â€” the letter `a` â€” from the rest of the string. Thanks to the power of Scalaâ€™s collections methods, we do this with the `drop` method thatâ€™s available on all strings:

`"a wake up".drop(2)                   // "wake up"`
`"a brush teeth".drop(2)               // "brush teeth"`
`"a take a long hot shower".drop(2)    // "take a long hot shower"`

> The `drop` method is available because a `String` is also a list, specifically a `Seq[Char]`.

This approach seems to work well, giving us a string that we can pass to another function, so that function can add the string to our database. So, looking only at the â€œaddâ€ case, I write this:

`case add if add.startsWith("a ") =>`
`    handleAdd(add.drop(2))`

## handleAdd

So now I need to write a `handleAdd` function, and I know three things about it already:

*   Itâ€™s going to take a `String` as input
*   It needs to add/insert that task into our database
*   Because itâ€™s going to access the database, it needs to return a `Try`

Therefore, I can start to sketch its signature like this:

`def handleAdd(task: String): Try`

And because I wrote the database code earlier, I know that `handleAdd` just needs to have a reference to the database object so it can perform the insert. Recall that this function is inside the `InputProcessor` class, which I defined to take a `Database` reference, like this:

`class InputProcessor(db: Database)`

So now `handleAdd` has access to this `db` reference.

> This is one situation where itâ€™s acceptable for a function to have a *side door*: when that function is declared inside a class that has a reference like this. (However, if you donâ€™t like this, there are other ways to write this code to make sure a `Database` reference is passed in through the functionâ€™s front door (i.e., its input parameter list)).

Getting back to the `handleAdd` function, I know that (a) I want to call the `insert` function on the `db` reference, and (b) it returns a `Try[Unit]`. So now I write `handleAdd` like this:

`def handleAdd(taskName: String): Try[Unit] =`
`    db.insert(taskName)`

At this point, this `case` code in the `match` expression inside the `handleUserInput` function could be the end of the `case`:

`case add if add.startsWith("a ") =>`
`    handleAdd(add.drop(2))`

However, because I know from testing the application that I want to see what my tasks look like after I issue my add command, I know that I also need to run the â€œviewâ€ function now. Therefore, I add it after `handleAdd`:

`case add if add.startsWith("a ") =>`
`    handleAdd(add.drop(2))`
`    handleView()`

And because `handleView` returns `Try[Unit]`, the return type of this `case` matches the return type of `handleUserInput`. So now `handleUserInput` has these cases in its `match` expression:

`def handleUserInput(input: String): Try[Unit] = input match`
`    case "q" =>`
`        Try(System.exit(0))`
`    case "h" =>`
`        IOHelper.showHelp()`
`    case "v" | "l" =>`
`        handleView()`
`    case add if add.startsWith("a ") =>     // <== THE NEW CODE`
`        handleAdd(add.drop(2))`
`        handleView()`
`    // more cases here ...`

# 44\. TDL UI: Handling â€œDeleteâ€

The â€œDeleteâ€ use case is very similar to the â€œAddâ€ case, but instead of having a string after the `a` command, there will be an integer after the `d` command. To be clear, delete commands look like this:

`d 1`
`d 3`

Those commands mean, â€œDelete the first taskâ€ and â€œDelete the third task,â€ respectively.

## Handling the input

Just like the last lesson, the first thing we need to do is to separate the delete command â€” the letter `d` â€” from the rest of the string. Again we do this with the `drop` method:

`"d 1".drop(2)    // "1"`
`"d 3".drop(2)    // "3"`

and then we use this approach to pass that string to a `handleDelete` function:

`case del if del.startsWith("d ") =>`
`    handleDelete(del.drop(2))`

## handleDelete

Now I need to write a `handleDelete` function, and I already know three things about:

*   Itâ€™s going to take a `String` as input
*   It needs to attempt to delete that task from the database, using the task-id that the user sees
*   Because itâ€™s going to access the database, it probably needs to return a `Try`

Therefore, I can start to sketch its signature like this:

`def handleAdd(taskIdString: String): Try`

Because this function takes a string that represents the task-id that the user sees â€” such as `"1"` or `"3"` â€” the functionâ€™s algorithm should be:

*   Attempt to convert the given string to an integer.
*   If that fails, the function should short-circuit at that time.
*   If the conversion works, subtract `1` from that value to get the real index. This is because Scala lists are 0-based, just like arrays and lists in other programming languages. (What I mean by this is that the user sees the first task as number `1`, so they type that. And that `1` corresponds to index `0` of a sequence.)
*   This function should return the number of rows that are deleted. Because Iâ€™m only letting users delete one task, this should always be `1`.
*   As usual, because weâ€™re accessing the outside world, the function should return a `Try` that wraps that integer.

Hereâ€™s the implementation of that algorithm, with a few comments added:

`def handleDelete(taskIdString: String): Try[Int] = Try {`
`    // convert the input String to an Int. this attempt will throw`
`    // an exception if this fails, so the code will short-circuit`
`    // here, and a Failure will be returned, wrapped around the`
`    // exception:`
`    val taskId = taskIdString.toInt`
`    // the task-id we show starts with 1, so subtract 1 here,`
`    // because sequences are 0-based:`
`    val maybeCount = db.delete(taskId - 1)`
`    maybeCount.get`
`}`

And to make it easier to read, hereâ€™s that function again without all those comments:

`def handleDelete(taskIdString: String): Try[Int] = Try {`
`    val taskId: Int = taskIdString.toInt`
`    val maybeCount = db.delete(taskId - 1)`
`    maybeCount.get`
`}`

I almost never call the `get` method on a `Try` value, but I do it for two reasons here:

*   The `handleDelete` function is wrapped in a `Try`, so it will return a `Failure` if `get` throws an exception. And if it throws an exception, that means something went wrong inside `delete`.
*   I believe the code is relatively easy to read for someone whoâ€™s new to Scala

As usual, you can shorten that function, if desired:

`def handleDelete(taskIdString: String): Try[Int] = Try {`
`    val taskId: Int = taskIdString.toInt`
`    db.delete(taskId - 1).get`
`}`

## Back to the handleUserInput case

And with `handleDelete` now working, its `case` *could* be finished here:

`case del if del.startsWith("d ") =>`
`    handleDelete(del.drop(2))`

But again, I know that I want to see my list of to-do items after a delete command, so I add the `handleView` call here:

`case del if del.startsWith("d ") =>`
`    handleDelete(del.drop(2))`
`    handleView()`

And because `handleView` returns `Try[Unit]`, the return type of this `case` match the return type of `handleUserInput`. Now `handleUserInput`â€™s `match` expression has these cases:

`def handleUserInput(input: String): Try[Unit] = input match`
`    case "q" =>`
`        Try(System.exit(0))`
`    case "h" =>`
`        IOHelper.showHelp()`
`    case "v" | "l" =>`
`        handleView()`
`    case add if add.startsWith("a ") =>`
`        handleAdd(add.drop(2))`
`        handleView()`
`    case del if del.startsWith("d ") =>      // <== THE NEW CODE`
`        handleDelete(del.drop(2))`
`        handleView()`
`    // more cases here ...`

Now we just have one more `case` to handle.

# 45\. TDL UI: Handling the Catch-All Case

Lastly, we just need to handle the â€œCatch-Allâ€ case. This is the case where the user types in something other than the previous commands that we handle in our `match` expression.

There are at least two ways to handle unknown commands:

*   Show an error message
*   Show our help text

Iâ€™ll take the first option, showing an error message.

## Handling the case

First, I add a new `handleUnknown` function to this default, catch-all `case`:

`case _ =>`
`    handleUnknown()`

Because I donâ€™t care what the user typed, I wrote a `handleUnknown` function there, and pass no parameters to it. But if you want to be nicer than this, you can give this case a name â€” a variable name, actually â€” and then access that variable on the right side of the `=>` symbol:

`case whateverTheyTyped =>`
`    handleUnknown(whateverTheyTyped)`

However, Iâ€™m just going to ignore whatever they typed and show an error message.

## handleUnknown

We know that `handleUnknown` has no input parameters, so I start to sketch its signature like this:

`def handleUnknown()`

Next, because this function just prints an error message, I also know that it returns a `Try[Unit]`:

`def handleUnknown(): Try[Unit]`

Now all I just need to implement the function body. Again, itâ€™s easiest to wrap the body inside a `Try` constructor, and because Iâ€™m printing an error message I use `System.err.println` instead of just `println`:

`def handleUnknown(): Try[Unit] = Try {`
`    System.err.println("Dude, I donâ€™t know what that means.")`
`}`

So thatâ€™s the `handleUnknown` function. I can leave it as-is inside its `case`:

`case _ =>`
`    handleUnknown()`

Or I can also call `handleView` after it, if that feels like the right thing to do:

`case _ =>`
`    handleUnknown()`
`    handleView()`

Now that all these cases and the functions they call are implemented, the `handleUserInput` function is complete:

`def handleUserInput(input: String): Try[Unit] = input match`
`    case "q" =>`
`        Try(System.exit(0))`
`    case "h" =>`
`        IOHelper.showHelp()`
`    case "v" | "l" =>`
`        handleView()`
`    case add if add.startsWith("a ") =>`
`        handleAdd(add.drop(2))`
`        handleView()`
`    case del if del.startsWith("d ") =>`
`        handleDelete(del.drop(2))`
`        handleView()`
`    case _ =>`
`        handleUnknown()     // <== THE NEW CODE`
`        handleView()`

# 46\. Running the To-Do List App

If you cloned this bookâ€™s Github repository to your local computer, to run the app you just need to move into the `ToDoList` directory of that repo and run this command:

`$ scala-cli .`

Thatâ€™s the Scala CLI way of saying, â€œLook for a *main method* in the source code files in this directory. Then compile all the necessary code, and run that main method.â€

When you run that command, you should see the app prompt you like this:

`(Commands: a "task", d 1, v, q, h)`
`Yo: _`

Now you can test its commands, and modify the code as desired.

# 47\. TDL: Lessons Learned

Having gone through the process of writing the Word Count application and then the To-Do List app, letâ€™s recap what youâ€™ve seen.

When I started, I said that these were our rules for programming, that weâ€™d only use:

*   Immutable variables
*   Immutable data structures
*   Pure functions
*   Expression-oriented programming
*   Error-handling data types
*   `Try` any time we accessed the outside world

Because this example only accesses a flat-file database (that we implemented), I also asked you to use your imagination to think that we were either accessing a remote database or remote REST service, both of which could be inaccessible at any time.

> I violated a couple of those rules for the reasons I gave at that time, i.e., that I wanted to make sure that I wrote code that Scala beginners could understand. But if you want to see the correct Scala solution, see the â€œUsingâ€ lesson in the Appendix.

But other than those violations, I followed the rules to a tee, and you saw how the application came together.

## Check-in time

At this time my main thought is that when this book started, you probably werenâ€™t used to using data types very much, but now that weâ€™ve written two small applications, youâ€™re probably much more used to them. So this is a good time to ask, do you feel that there are benefits to all of the techniques shown, and if so, what they are?

## Benefits

To me, the benefits I demonstrated are:

*   You know that you can trust pure functions; their type signatures cannot lie.
*   When I look at a function signature and see `Option`, `Try`, or `Either` as its return type, I instantly think, â€œSomething can go wrong in this functionâ€.
*   When I see a function signature that (a) takes no input parameters or (b) has the `Unit` return type, I know that itâ€™s performing some sort of side effect.
*   Even if I donâ€™t know the name of a function, when I look at its signature, I can get a good idea of what it can possibly do.

Furthermore:

*   Reading EOP can be as simple as code gets: you bind the result of a pure function to an algebraic variable. The code is easy to write, read, and test.
*   Writing code like this is like writing algebra, or creating a blueprint.
*   Combining expressions together is just like combining algebraic equations.

Other things I know from experience that I havenâ€™t shown here are:

*   I know that immutable variables and immutable data structures are safe to use in parallel and concurrent programming.
*   I know that pure functions are easier to test than methods that perform side effects.

In regard to that point about testing, an impure function may do any of these things:

*   Read input, without warning callers.
*   Write output, without warning callers.
*   Mutate the parameters they are given.
*   Mutate variables inside their class, or global parameters.
*   Access other variables through side doors.

Because of those, itâ€™s much harder to set up their state in a testing environment: itâ€™s hard to know exactly what else they might be accessing.

Conversely, with a pure function â€” where you know that the only variables it accesses come in through the front door, and it has no side effects â€” you know that setting up its test environment will be much easier.

## Key point

And now a key point of all of this is that if youâ€™re still with me â€” if everything Iâ€™ve shown makes sense â€” you are *really, really close to functional programming*. Probably much closer than youâ€™re thinking.

We just need to take a few more steps, which weâ€™ll do next.

# 48\. TDL: Using Either Instead of Try

The next step on your learning path is that weâ€™ll now replace all of the `Try` instances in the TDL app with `Either` instances.

Actually, I donâ€™t think itâ€™s worth doing *all* of that. Instead, all Iâ€™m going to do is to replace them in the `Database` class, and then I think you can imagine how to use those in the rest of the application.

So, letâ€™s get started, recalling that all of the following functions are inside the `Database` class:

`class Database(dbFilename: String):`
`    // all functions are in here`
`end Database`

## The insert function

The first function we wrote was the `insert` function, and it currently looks like this:

`def insert(record: String): Try[Unit] =`
`    writeToFile(List(record), true)`

So our first task is to replace that `Try` with an `Either`. So we start by updating `insert`â€™s function signature:

`def insert(record: String): Either[Throwable, Boolean] =`
`    writeToFile(List(record), true)`

As a refresher, recall that `Either` returns a `Left` or a `Right`, and by convention the `Left` holds the error, so I write `insert`â€™s return type like this:

`Either[Throwable, Boolean]`
`       ---------  -------`
`          ^          ^`
`       Possible   Success`
`        Error      Value`
`         In         In`
`        Left       Right`

Because this function relies on `writeToFile`, I need to update it next.

## writeToFile

The `writeToFile` function signature currently looks like this:

`private def writeToFile(lines: Seq[String], append: Boolean): Try[Unit] =`

and we know that we want it to look like this:

`private def writeToFile(lines: Seq[String], append: Boolean):`
`    Either[Throwable, Boolean] =`

That updates its function signature, and now a simple way to convert the function body is to convert the `Success` to a `Right`, and the `Failure` to a `Left`:

`private def writeToFile(lines: Seq[String], append: Boolean):`
`    Either[Throwable, Boolean] =`

`    var bw: BufferedWriter = null`
`    try`
`        bw = BufferedWriter(FileWriter(File(dbFilename), append))`
`        for line <- lines do bw.write(s"$line\n")`
`        Right(true)`
`    catch`
`        case e: Throwable => Left(e)`
`    finally`
`        if bw != null then bw.close`

So thatâ€™s a quick update.

## selectAll

Similarly, `selectAll`â€™s signature currently looks like this:

`def selectAll(): Try[Seq[String]] =`

and we again replace `Try` with `Either`:

`def selectAll(): Either[Throwable, Seq[String]] =`

After that, in the function body, we again replace `Success` with `Right` and `Failure` with `Left`:

`def selectAll(): Try[Seq[String]] =`
`    var bufferedSource: scala.io.BufferedSource = null`
`    try`
`        bufferedSource = Source.fromFile(dbFilename)`
`        val lines = for line <- bufferedSource.getLines yield line`
`        Right(lines.toList)`
`    catch`
`        case t: Throwable => Left(t)`
`    finally`
`        if bufferedSource != null then bufferedSource.close`

And thatâ€™s all there is to that.

One thing to observe here is that `selectAll`â€™s signature is a bit more complicated, because it has a list of strings as the `Right` parameter, but by now I suspect that you may be getting used to seeing these types (and the value of them). Hereâ€™s a breakdown of those types:

`Either[Throwable, Seq[String]]`
`       ---------  -----------`
`          ^            ^`
`       Possible     Success`
`        Error        Value`
`         In           In`
`        Left         Right`

If you can read that, youâ€™re doing just fine.

## delete

Lastly, the `delete` function currently returns this `Try`:

`def delete(indexToDelete: Int): Try[Int] = ...`
`                                --------`

and we want to replace it with this `Either`:

`def delete(indexToDelete: Int): Either[Throwable, Int] = ...`
`                                ----------------------`

For the purpose of converting `delete` so it returns an `Either`, a simple solution is to convert `maybeNumRowsDeleted` â€” which is currently a `Try` â€” to an `Either`. You do that by calling `toEither` on `maybeNumRowsDeleted` at the end of the function:

`def delete(indexToDelete: Int): Either[Throwable, Int] =`
`    val maybeNumRowsDeleted = for`
`        rows           <- selectAll()`
`        newRows        =  CollectionUtils`
`                              .removeElementByIndex(rows, indexToDelete)`
`        numRowsDeleted =  rows.size - newRows.size`
`        _              <- writeToFile(newRows, false)`
`    yield`
`        numRowsDeleted`
`    maybeNumRowsDeleted.toEither   // <== THE CHANGE`

Fortunately `Try` types have this `toEither` method, which makes the conversion simple.

## Keys

So there you have it, we rewrote the database functions to use `Either` instead of `Try`. Because `Either` requires that you declare both types the function can return, its signatures are a little longer to read, but theyâ€™re also very explicit, and more flexible in how they work.

As a reminder of what that last point means, in all of the database functions I declared the `Left` type as an `Throwable`, but they could have returned a `String`, an `enum`, or any other data type that makes the most sense for the current problem.

And this flexibility is very important for where weâ€™re going next.

# 49\. How Either Relates to ZIO

As I mentioned, if all of this continues to make sense, youâ€™re *so close* to FP right now, you can almost taste it. The truth is this: if you can handle `Either`, you can handle FP.

## A look at ZIO

If you havenâ€™t heard of it before, [ZIO](https://zio.dev) is one of the two main FP libraries in the Scala community (along with the other, named [Cats Effect](https://typelevel.org/cats-effect)). These two libraries power some of the busiest websites on the internet, including Disney Streaming, Caesars, and many other sites and applications here in 2022.

What I mean when I say â€œyouâ€™re so close to FP that you can taste itâ€ is that if you look at the [ZIO Overview document](https://zio.dev/overview) in November, 2022 â€” and pretty much every other â€œintroduction to ZIOâ€ article on the internet â€” youâ€™ll see that all the authors start with a description like this:

> Conceptually, you can think of the `ZIO` type as being a function that takes a generic `R` data type, and returns an `Either`.

That sentence means that conceptually you can sketch a `ZIO` function signature to look like this:

`def ZIO(r: R): Either[E, A]`

While that code isnâ€™t really how `ZIO` works, the basic idea is that you can think of:

*   The `ZIO` type as taking a generic `R` type as an input parameter.
*   It returns an `Either`.
*   Inside the `Either`, you see that it has two generic types in the `Left` and `Right` positions:

`Either[E,     A]`
`       ^      ^`
`      Left  Right`

These generic types are given the names `R`, `E`, and `A` for very specific reasons:

*   `R` stands for the *environment* that is passed in. Basically if your code requires some sort of environment, like a database, input/output, or even a clock, you pass in the dependencies your code needs as the `R` parameter. (It may help to think of this parameter being named `D`, for dependencies.)
*   `E` is the usual `Either` error-handling type, i.e., the type in the `Left` position. Having seen `Either` in the previous lessons, you already know what this means. (As usual, think of it as the â€œunhappyâ€ result.)
*   Similarly, `A` is the success data type that you really want, i.e., the â€œhappy pathâ€ or â€œhappy result.â€ (If your algorithm returns an `Int` as its success value, you return it in this position.)

So this is what I mean when I say that if you understand `Either`, youâ€™re now ready to start using ZIO and Cats Effect.

> At this point, to keep things simple, Iâ€™ll just keep referring to ZIO, but unless Iâ€™m showing a ZIO-specific example, every time you see â€œZIOâ€ you can think, â€œCats Effect and ZIO.â€

Coding with ZIO just involves using types like this, and again, youâ€™re really a mathematician whoâ€™s writing algebra, or an architect writing blueprints. Your code is incredibly honest because itâ€™s all immutable variables, immutable data structures, pure functions you can trust â€” along with descriptive data types â€” expression-oriented code, and functional error handling.

# 50\. JIT: Whatâ€™s an IO?

At this point I *could* turn you over to the ZIO and Cats Effect websites and their documentation, and you might do pretty well. But instead of doing that just yet, Iâ€™d like to help you out a little more.

The first thing to say is that before youâ€™re 100% ready for a `ZIO`, it will help to look at an `IO`.

## A bit of FP history

As a wee bit of FP history, back in the early days of Haskell, some really smart people were trying to figure out how to handle I/O in a â€œpureâ€ way. Every other function in Haskell was pure â€¦ and then there was I/O.

Long story short, they invented a concept called an `IO` type. To start with, you can think of `IO` as being like `Try` or `Either`: itâ€™s a type you want to use when you communicate with the outside world, or run any other side effect. So wherever I have function signatures like this in this book:

`def readFile(f: String): Try[String]`
`def writeFile(s: String): Try[Unit]`

conceptually, you can replace those `Try` types with the `IO` type:

`def readFile(f: String): IO[String]`
`def writeFile(s: String): IO[Unit]`

This is a slight oversimplification, but not too much. For example, in [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book), I show how to write an `IO` class and use it in `for` expressions, just like weâ€™ve used `Try` in this book.

## Three keys about IO types

Fast-forward to today, and there are three important things to know about `IO` types:

1.  They were created to let you reason about your *I/O and side-effect* code using algebraic substitution.
2.  One thing I havenâ€™t mentioned yet is that you canâ€™t mix `Option`, `Try`, and `Either` values inside `for` expressions, *but*, you can use as many `IO`s as you need.
3.  To help with Item 2, `IO`s are like `Try` and `Either`, but on steroids. They are *much* more powerful than those types, with tons of built-in features. (Types like `Try` and `Either` can be written in less than a page of Scala code, but `IO` types have been developed over *years* of effort.)

So letâ€™s talk about `IO` types a little bit.

# 51\. JIT: IO and Algebraic Substitution

The first key about `IO` types â€” such as `ZIO` â€” is that they let you continue to â€œreason about your codeâ€ using the concepts of referential transparency (RT) and algebraic substitution (AS).

## Referential transparency is good

To demonstrate this, hereâ€™s a new function named `stringLength`:

`def stringLength(s: String): Int = s.length`

Technically the Scala `String` type already has that `length` method, but ignoring that for now, the important part of `stringLength` is that itâ€™s a pure function. Therefore, in this next example, `fooLength` and `stringLength("foo")` will always and forever have the exact same value (the integer `3`):

`val fooLength = stringLength("foo")`

So now anywhere in your code you can use `fooLength`, `stringLength("foo")`, and the value `3`, and they will always and forever have the same value and mean the same thing.

Now contrast that with an *impure* method like `io.StdIn.readLine()`:

`val input = io.StdIn.readLine()`

Because people can type an infinite number of things at the command line, the return value of `io.StdIn.readLine()` *will almost always be different*.

This means that `readLine` is NOT referentially transparent, and we cannot use algebraic substitution with it. In the FP world this is *bad*, because we want to write our code as algebra.

So, what can we do?

This is where the Haskell people invented the `IO` type.

## IO to the rescue

The way you use an `IO` type is similar to `Try`, looking something like these two examples in the most basic case:

`val input: IO[String] = IO(io.StdIn.readLine())`

`def printLater(s: String): IO[Unit] = IO {`
`    println(s)`
`}`

A key here is that `IO` is like a wrapper, and a *lazy* wrapper at that: the code that you pass into `IO` isnâ€™t executed *now*, it will be executed *some time later*. This is even true in the first case, where I define `input` as a `val` field.

> Because `IO` is lazy, weâ€™re still writing code as a blueprint. *Right now* we describe what we want, and then some time *later* that code is actually run.

Instead of thinking of `IO` as a wrapper, you can think of it as a box â€” and a bit of a time machine as well. Right now it doesnâ€™t contain anything, itâ€™s just like a box with a label on it that describes *what will be in it* some time later. You can imagine a label being on the box that says, â€œSome time later this box will contain either (a) a `String` or (b) an error.â€

> TIP: An `IO` is like getting a receipt from Amazon that â€œyour package will be delivered,â€ and some time later it will either (a) be delivered just fine (the `Either` *happy* case), or (b) be damaged (`Either`â€™s *unhappy* case). (It may also get lost, but that doesnâ€™t fit with my analogy.)

But right now, as mathematician or architect, you just think of it as an `IO`:

`+------+`
`|  IO  |`
`+------+`

If youâ€™re familiar with a Scala `Future`, itâ€™s similar to a `Future`, with one big difference: a `Future` begins running immediately, but `IO` is lazy, so nothing happens right now.

### Laziness

We say that code like this is *lazy*, or *lazily evaluated*. Haskell is famous for being a language where everything is evaluated lazily. You can write all the Haskell code you want, but nothing will happen until you issue the magic incantation that says, â€œRun the code *now*.â€

Conversely, all of the code I used to write in Java was *strict*, or *strictly evaluated*. For example, when you write Java code like this, it runs right now:

`String input = getInput();`

Frankly, I wrote Java code like this for almost fifteen years, and didnâ€™t even know there was another way to write code.

### Laziness helps with RT

What laziness does for us is that it lets us keep thinking of our code as algebra or a blueprint. We know that weâ€™re working with an `IO` of a specific type â€” such as an `IO[String]` â€” and then we merrily keep creating our blueprint, because nothing happens now.

For instance, we can also write a `for` expression using our lazy `IO` values, and again, nothing happens yet:

`val result = for`
`    input <- readInputLater()`
`    _     <- printLater(input)`
`yield`
`    ()`

As I mentioned, Haskell has a magic incantation that lets you say, â€œOkay, Iâ€™m ready, run the blueprint now.â€ The Cats Effect and ZIO libraries have a similar incantation, and historically that incantation has been a function named something like `runUnsafe`. This means that when youâ€™re ready to run your entire application â€” or in this example, just this `for` expression â€” you run it like this:

`runUnsafe(result)`

The actual function names vary, but the word â€œunsafeâ€ is an FP way of saying, â€œHang on everyone, weâ€™re going to execute the blueprint now, including all those unsafe side effects.â€ *Until now* everything was all equations and blueprints, and nothing happened, but *now* itâ€™s action time.

And now, to wrap up this lesson, I want to add two notes.

## Note 1: Future is not like this

First, itâ€™s important to be clear that the Scala `Future` *does not* work like this. For example, if the earlier `input` value was written like this:

`val input: Future[String] = Future(doSomeSideEffect())`

the `doSomeSideEffect` function will be run immediately. This is how `Future` works, it runs immediately.

From an FP standpoint, this is bad; itâ€™s a design flaw. The flaw is that `Future` combines the blueprint and its action in the same step. As FPers, we need to be able to layout the blueprint without it starting to run while weâ€™re still working. As a mathematician/architect, we need to be able to separate the *what* from the *when*, the description from the execution: `Future`â€™s action should only be triggered some time later, specifically when `runUnsafe` is invoked.

## Note 2: Call by-name parameters

If youâ€™re wondering how `IO` can be lazy, and youâ€™re not familiar with how *call by-name* parameters work in Scala, please see the *Call By-Name* lesson in the Appendix. It explains how this works.

# 52\. JIT: IO, Option, Try, Either, and for-Expressions

A second important thing to know at this point is that you CANNOT mix types like `Option`, `Try`, and `Either` in `for` expressions (not easily, anyway).

To demonstrate this, imagine that your code base has two functions like this, one that returns an `Option` and another that returns a `Try`:

`import scala.util.{Try, Success, Failure}`
`import scala.util.control.Exception.allCatch`
`import io.StdIn`

`def makeInt(s: String): Option[Int] =`
`    allCatch.opt(s.toInt)`

`def makeDouble(s: String): Try[Double] =`
`    Try(s.toDouble)`

and then you find yourself in a situation where you want to prompt a user to enter an `Int` and then a `Double`:

`print("Enter an Int: ")`
`val intAsString = StdIn.readLine()`

`print("Enter a Double: ")`
`val doubleAsString = StdIn.readLine()`

`val maybeInt: Option[Int] = makeInt(intAsString)`
`val maybeDouble: Try[Double] = makeDouble(doubleAsString)`

So far, so good. But now, letâ€™s say that you want to use them in sequence in a `for` expression, to add them together:

`for`
`    i <- maybeInt`
`    d <- makeDouble`
`yield`
`    i + d`

Sadly, this code wonâ€™t compile. The types `Opt[Int]` and `Try[Double]` just wonâ€™t mix.

There are ways to get around this in a small example like this, but in the more-complex real world, this is a huge problem.

> I explain *why* these donâ€™t mix in [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book).

## The solution

The solution is to use an `IO` data type whenever you communicate with the outside world. When you do that, you can use as many `IO` values in a `for` expression as you want. `IO`s are built to handle all sorts of side effects, and they will all work happily together when you sequentially compose them in `for` expressions. (Life is good with `IO`.)

Now Iâ€™ll add an oversimplification here: This is where you need to choose a library like ZIO *OR* Cats Effect. There are ways to get their `IO` types to work together, but in general you want to choose one OR the other.

As a personal statement, Iâ€™m just a teacher and a writer, so I donâ€™t want to get into suggesting *which* library you should use. Thatâ€™s beyond the scope of this book, and you can search for terms like â€œZIO vs Cats Effectâ€ to find the pros and cons of each library.

> That being said, Iâ€™ll only demonstrate ZIO in this book, because I want to avoid the confusion of switching back and forth between the two.

## Key point

Getting back to this lesson, the key point is that types like `Option`, `Try`, and `Either` donâ€™t mix well: itâ€™s hard to combine their results in `for` expressions, as well as other places.

As shown in this book, the goal of these types is to handle errors in a functional way, and we generally use them when dealing with side effects, such as communicating with the outside world. But when you canâ€™t later combine them â€” what FPers call *composing* values, or *composition* â€” this is a big problem.

Therefore, `IO` types have been created as a way to deal with I/O and other side effects. They have all the benefits of `Try` and `Either`, but:

*   Theyâ€™re lazy, so we keep the algebraic substitution model
*   They can be combined in `for` expressions
*   They have MANY more features than these error-handling types

In the previous lesson and this lesson I covered the first two bullet points, and in the next lesson weâ€™ll start looking at some of the features that industrial-strength `IO` types have in the ZIO and Cats Effect libraries.

# 53\. ZIO and the Power of IOs

Like the [Cats Effect `IO` type](https://typelevel.org/cats-effect/docs/2.x/datatypes/io), the `ZIO` type is an incredibly souped-up `IO` data type. As mentioned, in [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book), I show how to write a *simple* `IO` type in less than a page of source code, but industrial-strength `IO` types have taken *years* to create.

So, after a quick JIT note, letâ€™s start writing some Scala/FP [ZIO](https://zio.dev) code.

## JIT: Scala 2 applications

Before we get into ZIO, we need one quick JIT lesson, and it goes like this: One way to create a *Scala 2* application looks like this:

`object Hello extends App {`
`    println("Hello")`
`}`

In this code, `App` is a type thatâ€™s provided by the Scala 2 SDK, and you extend it with an `object`, as shown, to create an application. In Scala 3, the *`main` method* approach I show in this book replaces this Scala 2 approach. (Thereâ€™s another way to start Scala 2 applications, but that isnâ€™t important for this lesson.)

## ZIO applications

I mention that because ZIO takes a similar approach, and you create ZIO applications like this:

`import zio.{ZIOAppDefault, Console}`

`object Zio101 extends ZIOAppDefault:`
`    def run = Console.printLine("Hello, World!")`

All you have to do is import the ZIO types that are necessary, and then create an `object` that extends ZIOâ€™s `ZIOAppDefault` type. This type is described as [the ZIO runtime](https://zio.dev/reference/core/runtime), and it evaluates the rest of your application. As a quick recap, just:

*   Create an `object` that extends `ZIOAppDefault`
*   Define a `run` method inside that `object` to start your application running
*   And then the rest of your application is evaluated as a ZIO application, and all your equations/blueprints start executing

If you dig into the `ZIOAppDefault` source code, I suspect that somewhere in there youâ€™ll find a function named something like `runUnsafe`.

## ZIO + Scala CLI 101

In that code I created the simplest-possible ZIO â€œHello, worldâ€ application, using ZIOâ€™s `Console` type. To take this a step further, save this code in a file named `Hello1.scala` to create a complete Scala 3 + ZIO + Scala CLI application:

`//> using scala "3"`
`//> using lib "dev.zio::zio::2.0.2"`

`// run me like this:`
`//     scala-cli Hello1.scala`
`//     scala-cli Hello1.scala --watch`

`import zio.{ZIOAppDefault, Console}`

`object Zio101 extends ZIOAppDefault:`
`    def run = Console.printLine("Hello, World!")`

As shown in the comments, you run it like this at your operating system command line with `scala-cli`:

`$ scala-cli Hello1.scala`

If you havenâ€™t used ZIO before â€” congratulations! You just ran your first Scala/FP ZIO application, and if you think about where this book first started, thatâ€™s quite an accomplishment.

## ZIO + Scala CLI 102

A next logical step is to demonstrate how to add a ZIO variable to your application:

`import zio.{ZIOAppDefault, ZIO, Console}`
`import java.io.IOException`

`object Zio102 extends ZIOAppDefault:`
`    val hello: ZIO[Any, IOException, Unit] =`
`        Console.printLine("Hello, World!")`
`    val run = hello`

The first difference in this application is that I create `hello` as an instance of a `ZIO` variable:

`val hello: ZIO[Any, IOException, Unit] =`

As I mentioned before, the mental model for thinking of the `ZIO` type is that itâ€™s a description of a workflow, and you can think of it as a function, that given an `R` can produce either an `A` or an `E`:

`f(r: R): Either[E, A]`

and in that code:

*   `R` stands for the *environment* that is passed in
*   `E` is like the `Either` error-handling type
*   `A` is like the `Either` success data type that you really want (i.e., the â€œhappy pathâ€ or â€œhappy resultâ€)

Therefore, you can read this variable and data type:

`val hello: ZIO[Any, IOException, Unit] =`

like this:

*   `R` is the Scala type `Any`, which is the ZIO way of saying that the environment doesnâ€™t matter
*   `E` is an `IOException`, meaning that the code on the right side of the `=` symbol can throw that exception
*   `A` is `Unit`, because weâ€™re printing output to STDOUT, so the return type isnâ€™t important

Once again, if you can read that, youâ€™ll do just fine with ZIO: itâ€™s just like writing line after line of algebra, or blueprint code.

> NOTE: In the real world, you donâ€™t have to always show each variableâ€™s data type.

A second difference in this example is that I replaced `def run` with `val run`:

`val run = hello`
`-------`

I suppose this is one of those Scala â€œmagic tricksâ€ I was going to avoid, but let me explain it, because itâ€™s not that bad.

You can do this in Scala because `run` is *probably* defined something like this somewhere in the `ZIOAppDefault` code:

`trait SomeZioTrait:`
`    def run: ZIO[A, B, C]`

Of course itâ€™s more complicated than that, but you can think of it that way. The key is that when `run` is defined like this inside a Scala `trait`, it can be read like this:

*   Thereâ€™s a `trait` named `SomeZioTrait`, and a Scala `trait` is like an interface in Java 8+, so it can be used to define both abstract and concrete methods.
*   `run` is defined as an *abstract*, somewhat vague thing that takes no input parameters, and has the type `ZIO[A, B, C]`.
*   As I describe in the [Scala Cookbook](https://amzn.to/3du1pMR) and [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book), the magic trick is that when you define `run` as an abstract thing like this, it can later be implemented by extending classes as a `def` function OR as a `val` field. This gives people who extend your trait power in how they want to implement `run`.

The summary of those bullet points is that as a designer, you define a field in a `trait` as an abstract `def` with no input parameters. This lets programmers who later extend your trait implement that field as a `def` or as a `val`, and the key is that this is more flexible for them.

Getting back to our current application, if you run `Zio102`, youâ€™ll see that it works just like `Zio101`.

## ZIO 103: ZIO.attempt

Given that background, letâ€™s take another step. Rather than using ZIOâ€™s built-in `Console` type, letâ€™s imagine that it doesnâ€™t exist, so instead, weâ€™ll need to wrap the Scala `io.StdIn.readLine` function with â€¦ well â€¦ something.

This is where you begin to see ZIOâ€™s power and flexibility. ZIO has built-in factory methods for just these needs. In this case, if you imagine that the `readLine` function can throw an exception, you define a variable as follows to (a) prompt a user for their name, and (b) read their name in:

`val username: ZIO[Any, Throwable, String] =`
`    ZIO.attempt(StdIn.readLine("Whatâ€™s your name? "))`

A few keys about this code:

*   `readLine` is used to both (a) prompt the user for their name and (b) return whatever they type.
*   Because I said to *imagine* that the code can throw an exception, the second parameter in `ZIO[Any, Throwable, String]` is a `Throwable` (and it could also be `Exception` or `IOException`).
*   Recall that this second parameter is ZIOâ€™s `E` parameter, and itâ€™s similar to `Either`â€™s error parameter.
*   Also because of the assumption that the code can throw an exception, I wrap the `readLine` code in `ZIO.attempt`. `attempt` is a ZIO factory method that you use when you literally *attempt* to do something that may fail. Because weâ€™re imagining that `readLine` can fail, we use `attempt` here.

As youâ€™ll see shortly, in other situations, where a block of code canâ€™t really fail, weâ€™ll wrap that code with `ZIO.succeed` instead of `ZIO.attempt`. (As I mentioned, ZIO has many different factory methods for all sorts of situations.)

With this step of knowledge, our next little, complete ZIO application looks like this:

`import zio.*`
`import scala.io.StdIn`

`object Zio103 extends ZIOAppDefault:`

``     // new: wrap procedural code that can fail with `attempt` ``
`    val username: ZIO[Any, Throwable, String] =`
`        ZIO.attempt(StdIn.readLine("Whatâ€™s your name? "))`

`    val run = username`

If you run that code with Scala CLI, youâ€™ll see that we can now prompt a user for input. Now we just need to use their input.

## ZIO 104: ZIO.attempt, ZIO.succeed

If we assume that we have the userâ€™s name, we now need a way to functionally print that name. Again we imagine that the ZIO `Console` type doesnâ€™t exist, so we need to handle this ourselves. For this Iâ€™ll go back to the way of writing functions that I used in most of this book: a step-by-step function-sketching process.

First, we know that we eventually want to use the Scala `println` function to print some text. You may not have any way of knowing this yet, but because Iâ€™ve done this before, I know that I want to create a ZIO-based printing function that starts like this:

`def printName(name: String): ZIO[???] =`
`    // some use of println here`

This is a function that takes a `String` input parameter, returns some sort of `ZIO` type, and uses `println` in its body.

Next, because I already mentioned `ZIO.succeed`, Iâ€™ll jump inside the functionâ€™s body to show how to wrap `println` with it:

`def printName(name: String): ZIO[???] =`
`    ZIO.succeed(println(s"Hello, $name"))`

As mentioned, whenever a block of code *canâ€™t fail*, just wrap it in `ZIO.succeed`.

To me, the only way `println` can fail is if something is really wrong with a computer, so it meets this definition. More importantly, its function signature doesnâ€™t state that it can throw exceptions.

Now all we have to do is fill in the `ZIO` type the function returns. To do that, we know these things:

*   The function doesnâ€™t require any sort of special environment, like a database, so its type is `Any`.
*   Weâ€™re saying that the function body cannot fail â€” `println` throws no exceptions â€” so its error type parameter is `Nothing`. With ZIO, any time a function body canâ€™t fail, you use this Scala type.
*   Because `println` prints to STDOUT, it has the `Unit` return type, and because thatâ€™s the final value of the function, it becomes the functionâ€™s â€œsuccessâ€ value, and is used as the third `ZIO` parameter.

Given that thought process, hereâ€™s the complete function:

`def printName(name: String): ZIO[Any, Nothing, Unit] =`
`    ZIO.succeed(println(s"Hello, $name"))`

So now we have ways to prompt a user for input, read their input, and print their input. Now we just need a way to call those functions in sequence.

### Hello, flatMap

Excluding the necessary `import` statements, Iâ€™ll jump to the complete solution for this problem:

`object Zio104 extends ZIOAppDefault:`

`    val username: ZIO[Any, Throwable, String] =`
`        ZIO.attempt(StdIn.readLine("Whatâ€™s your name? "))`

`    def printName(name: String): ZIO[Any, Nothing, Unit] =`
`        ZIO.succeed(println(s"Hello, $name"))`

`    val run = username.flatMap { name =>`
`        printName(name)`
`    }`

The new code in this solution is this:

`val run = username.flatMap { name =>`
`    printName(name)`
`}`

Here are the keys to this code:

*   `run` is the usual `ZIOAppDefault` code. It says, â€œRun the code on the right side of the `=` symbol as my ZIO application.â€
*   `flatMap` is the new, interesting piece. In ZIO, `flatMap` is THE mechanism that is used to run functional effects in sequence.
*   A key to that last statement is that `ZIO`s are described as â€œblueprints for running concurrent workflows.â€ You can take that to mean that any `ZIO` effect â€” such as `username` and `printName` â€” can potentially be run concurrently.
*   Therefore, `flatMap` is a way to ensure that in a concurrent environment, one effect is run first, and then its output is given to the next effect, which is run second. We say that the two effects are run in *sequence*, and this is *sequential composition*.
*   In this example, the use of `flatMap` means, â€œRun `username`, and when it finishes, pass its result as the variable I have named `name` to the `printName` function, and then run that function.â€
*   A cool thing is that this statement is true whether the functions are implemented to run in serial or in parallel. You can almost think of that as a runtime detail that you donâ€™t have to concern yourself with; you just use `flatMap`.

Now when you run `Zio104` with Scala CLI and your name happens to be `Alvin`, the interaction looks like this:

`$ scala-cli Zio104.scala`
`Whatâ€™s your name? Alvin`
`Hello, Alvin`

Congratulations, again â€” youâ€™re now sequentially composing effects!

## ZIO 105: From flatMap to for-expressions

When you only have one or two effects that need to be run in sequence, you can use `flatMap` as shown. However, when you need to run more effects in sequence, that sort of code can get hard to read:

`effect1.flatMap { var1 =>`
`    // use var1 in here somewhere`
`    effect2.flatMap { var2 =>`
`        // use var2 and/or var1 in here somewhere`
`        effect3.flatMap { var3 =>`
`            // use var1, var2, and var3 as needed`
`        }`
`    }`
`}`

Frankly, nobody wants to read code like that. Fortunately this is where the Scala `for` expression comes in: the `for` expression is quite literally *syntactic sugar* for that code. This means that this `for` expression is the equivalent of that `flatMap` code:

`for`
`    var1 <- effect1`
`    var2 <- effect2(var1)`
`    var3 <- effect3(var2)`
`yield`
`    ()`

More accurately, if I had taken the time to write this `for` expression correctly â€” and if you dug into the Scala compilation process â€” youâ€™d see that the Scala compiler turns this `for` expression into a series of `flatMap` method calls (followed by a single `map` method call).

Frankly, my translation isnâ€™t 100% correct because itâ€™s not that important. The important thing is that in the `Zio105` application, you can change this `flatMap` code:

`val run = username.flatMap { name =>`
`    printName(name)`
`}`

to this `for` expression:

`val run =`
`    for`
`        name <- username`
`        _    <- printName(name)`
`    yield`
`        ()`

and I do know that this code is 100% equivalent, because I did test it. And again, when you add more functional effects in sequence, writing them inside `for` expressions makes them *much* easier to read (compared to writing a series of `flatMap`s).

> *Most importantly*, this is what ZIO *sequential composition* looks like: use `flatMap` to sequence one or two effects (if you want to), and use `for` expressions to sequence *many* effects.

So now, when I replace the previous `flatMap` code with this new `for` expression code, the next complete version of our application (without `import` statements) looks like this:

`object Zio105 extends ZIOAppDefault:`

`    val username: ZIO[Any, Throwable, String] =`
`        ZIO.attempt(StdIn.readLine("Whatâ€™s your name? "))`

`    def printName(name: String): ZIO[Any, Nothing, Unit] =`
`        ZIO.succeed(println(s"Hello, $name"))`

``    // new: replace `flatMap` with a `for` expression``
`    val run =`
`        for`
`            name <- username`
`            _    <- printName(name)`
`        yield`
`            ()`

When you run this new `Zio105` application, youâ€™ll see that it works just like `Zio104` works:

`$ scala-cli Zio105.scala`
`Whatâ€™s your name? Alvin`
`Hello, Alvin`

> For many more details on how `for` expressions translate to a series of `flatMap` and `map` methods, see my book, [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book).

## ZIO 106: ZIO aliases

And now itâ€™s time for the last thing I need to demonstrate before I turn you over to the ZIO (and Cats Effect) documentation: ZIO makes common use of Scala *type aliases* (and those common ZIO aliases [are documented here](https://zio.dev/reference/core/zio/uio)).

### JIT: Scala type aliases

A Scala *type alias* is just a way to give a new name to another type, and hopefully the alias is shorter and/or more meaningful than the original type. A very basic use of a type alias named `Money` looks like this in the Scala REPL:

`scala> type Money = Double`
`// defined alias type Money = Double`

`scala> val oneDollar: Money = 1.00`
`val oneDollar: Money = 1.0`

When youâ€™re working with a financial application, it can be more meaningful to use the type name `Money` rather than `Double`, and Scala lets you do this. (Please bear in mind that this is a very basic example that doesnâ€™t show everything you need for a real-world application.)

### Type aliases in ZIO

Per the ZIO type alias documentation, the ZIO type alias `UIO[A]` is a type alias for `ZIO[Any, Nothing, A]`.

You use this alias any time (a) the environment is not important, (b) the error type is not important, and the only type that is important is the â€œsuccess type,â€ `A`. Therefore, ZIO refers to this as *an Unexceptional effect*, so you can replace this `ZIO` return type that I used in `Zio105`:

`def printName(name: String): ZIO[Any, Nothing, Unit] =`
`                             -----------------------`

with the alias, `UIO`:

`def printName(name: String): UIO[Unit] =`
`                             ---------`

Once you get used to this approach, I believe youâ€™ll find that this is a terrific use of [Scala type aliases](https://alvinalexander.com/scala/scala-type-aliases-syntax-examples/).

So now, if you replace that `ZIO` return type in `printName`â€™s signature in the `Zio105` example with the `UIO` return type, and re-run the application, youâ€™ll see the exact same result as before. (This is `Zio106` in the bookâ€™s Github repository.)

And now, before I leave you, here are the common ZIO 2 type aliases:

`ALIAS         ORIGINAL/FULL TYPE`
`----------    ----------------------`
`IO[E, A]      ZIO[Any, E, A]`
`Task[A]       ZIO[Any, Throwable, A]`
`RIO [R, A]    ZIO[R, Throwable, A]`
`UIO [A]       ZIO[Any, Nothing, A]`
`URIO[R, A]    ZIO[R, Nothing, A]`

I like to think of types portions of code as running a task, so the `Task` alias is an interesting one to look at.

As shown, `Task[A]` is an alias for `ZIO[Any, Throwable, A]`, which means:

*   A `Task` has no requirements for its environment (`Any`),
*   it can throw an exception (`Throwable`), and
*   if it succeeds, it succeeds with a result that has the type `A`.

For more information on using these type aliases, see the [ZIO type alias documentation](https://zio.dev/reference/core/zio/uio).

## Whatâ€™s next?

I could happily write about ZIO and Cats Effect for an entire book, but alas, itâ€™s time for me to turn you over to their websites:

*   [ZIO](https://zio.dev)
*   [Cats Effect](https://typelevel.org/cats-effect)

As I stated in the beginning of this book, this bookâ€™s reason for existence is to get you to the point where you can look at the Cats Effect and ZIO documentation and think, â€œI know *what* theyâ€™re doing, and *why* theyâ€™re doing it.â€ I think â€” or at least hope â€” that Iâ€™ve accomplished this task, and when you look at their documentation, I hope youâ€™ll agree.

> And if you do agree, Iâ€™d greatly appreciate it if youâ€™d leave a review of this book wherever you bought it (i.e., on the [Gumroad website](https://alvinalexander.gumroad.com/l/learnfp), or on Amazon.)

I hope this book has been readable and helpful, and I wish you tremendous amounts of success and joy in your career!

[Alvin Alexander](https://alvinalexander.com)
Somewhere in Colorado, USA

# 54\. Bonus: The Mindset of an FPer

Oops, wait, Iâ€™m still writing. :)

I started this book by saying that it has an audacious goal: to demonstrate to OOP developers the benefits of:

1.  Immutable variables (algebraic variables)
2.  Immutable data structures
3.  Pure functions
4.  Expression-oriented programming
5.  Functional error handling

As I went along in creating the examples, you also saw the additional benefits of declaring *data types*: that they make the signatures of pure functions incredibly meaningful.

After we finished the *To-Do List* example and switched some of that code from using `Try` to using `Either`, I then showed how this gets you ready to use the â€œIOâ€ types in the ZIO and Cats Effect libraries.

## The mindset of an FPer

As you dig into ZIO and Cats Effect, remember a few things:

*   The *biggest* thing is that FPers think of ourselves as mathematicians or architects, writing algebraic code or creating blueprints.
*   Terms like *equations* and *blueprints* imply that the *description* of our code is separate from the *execution* of the code. (As I mentioned, FPers donâ€™t like `Future` because it begins running immediately.)
*   Writing FP code is all about immutable variables, immutable data structures, pure functions, with data types and functional error handling that tells readers exactly whatâ€™s going on â€” all of which youâ€™ve seen in this book.
*   *Side effects* mess up our equations and blueprints, so we donâ€™t allow them. Instead we handle them with types like `Option`, `Try`, and `Either` â€” and when we really get into FP we use the more industrial-strength `IO` and `ZIO` types.
*   I mentioned that you canâ€™t mix types like `Option`, `Try`, and `Either` inside `for` expressions, so thatâ€™s one reason a type like `ZIO` has so many capabilities: whatever your `ZIO`s do individually, you can combine them all together, as desired.

These are the ways that FPers think about their code. If you understand the reasoning and desires behind this mindset, you can understand FP.

# 55\. Bonus: The M Word

Were you expecting to see *monads* in this book? If so, you wonâ€™t be disappointed. :)

Almost all of the data types I showed in this book are monads. This includes `Option`, `Try`, `Either`, `List`, `Seq`, `Vector`, `IO`, and `ZIO`: theyâ€™re all monads, or what we call *monadic data types*.

I wonâ€™t get into mathematical theory here, but *in Scala*, a monad is primarily a data type that properly implements `map` and `flatMap` methods so that it can be used in `for` expressions. Thereâ€™s a little more to it than that, but from an implementation standpoint, thatâ€™s the big thing. As Iâ€™ve shown, you can use `flatMap` to run a few effects in sequence, and `for` expressions to run many effects in sequence.

> And as I show in [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book), `for` expressions are syntactic sugar that compile down to a series of `flatMap` calls followed by a single `map` call.

## Sequential composition

The key about monads in any language is that they allow you to guarantee that effects will occur in order (i.e., sequentially). For example, Haskell is a *lazy* (or *lazily evaluated*) programming language, and part of what that means is that whenever the Haskell compiler sees that it can run expressions in parallel, it might just do that.

However, when you prompt a user for input, like this:

`print("Your input: ")`

you *really* want to make sure that your â€œprompt the userâ€ code occurs before your â€œread their inputâ€ code:

`val input = readInput()`

To make any sense, those operations *must* occur in that order, one after the other. In Haskell, you use its `do` construct to ensure that expressions are run in sequence, and in Scala you similarly sequence them in `for` expressions, like this:

`for`
`    _     <- promptUser()`
`    input  = readInput()`
`    // more code here ...`

If you recall that the `ZIO` type is a â€œblueprint for describing a *concurrent* workflow,â€ you should think, â€œIf `promptUser` and `readInput` run concurrently, I need to use a `for` expression or `flatMap` to make sure those two functions are called in the proper order.â€

For this reason, some people refer to monads as the â€œsemi-colon in FP.â€ They let us run our effects in a guaranteed sequence, so even if our functions are meant to run in parallel, `flatMap` and `for` expressions guarantee that theyâ€™re run in sequence, just like procedural code.

## Monads in Scala

But again, the key *in Scala* is that these monadic data types properly implement the `map` and `flatMap` methods inside their classes, and this is what enables them to be used in `for` expressions. I write about this in great detail in these two resources:

*   My blog post, [How to Write a Scala Class That Can Be Used in a for-Expression](https://alvinalexander.com/scala/fp-book/how-to-write-class-used-in-for-expression/)
*   My best-selling FP book, [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book)

## Category Theory

For those who are interested in the theory behind names like monad, monoid, functor, and other FP terms with unusual names, the next thing youâ€™ll want to dig into is *category theory* (which is where the name â€œCats Effectâ€ comes from).

You can find a free version of a book named *Category Theory for Programmers* at these locations:

*   [A Github repository](https://github.com/hmemcpy/milewski-ctfp-pdf)
*   [A series of online blog posts](https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/)

As Iâ€™ve shown in this book, you donâ€™t need to understand category theory to understand FP, but when you want to know where names like â€œmapâ€ come from, category theory is what youâ€™re looking for.

# Appendix A. Scala 3 Cheatsheet

Assuming that youâ€™re not familiar with [Scala 3](https://scala-lang.org/), hereâ€™s a cheat sheet that covers many of its main features. However, if you want to see *many* more details about *Scala 3*, see:

*   The free, online [Scala 3 Book](https://docs.scala-lang.org/scala3/book/introduction.html)
*   My book, [Learn Scala 3 The Fast Way!](https://alvinalexander.gumroad.com/l/learn-scala3-fast)
*   The [Scala Cookbook (2nd Edition)](https://amzn.to/3du1pMR)

## Key Concepts

These are the main points or key concepts about the Scala 3 programming language:

*   Itâ€™s a high-level programming language (like Java, Kotlin, and others)
*   Itâ€™s *expressive*, with a concise, readable syntax (similar to Kotlin)
*   A distinguishing trait is that it promotes a *fusion* of OOP and FP
*   Itâ€™s statically-typed, but feels dynamic
*   It has a sophisticated type inference system, so you rarely need to explicitly declare variable types
*   Functions are first-class values, just like strings, integers, and other types
*   Immutable data structures are preferred, and mutable ones are also available
*   Scala 2 was very consistent, and Scala 3 is ridiculously consistent
*   It works seamlessly with other JVM libraries (Java, Kotlin, etc.)

More:

*   With the creation of Scala.js several years ago, Scala can be used as a JavaScript replacement
*   With the creation of Scala Native (and GraalVM), you can create binary executables
*   The new [Scala CLI](https://scala-cli.virtuslab.org) tool makes it easy to get started with Scala
*   The Scala 3 preference is to use significant indentation as the default, but you can also use curly braces, if you prefer

On a personal note, I expect that almost every popular programming language will support significant indentation within ten years. IMHO, it makes your code much cleaner and easier to read.

## OOP Support

Scala is a complete OOP language, with full support for:

*   Classes
*   Traits (interfaces)
*   Inheritance
*   Polymorphism
*   Every value in Scala is an instance of a class

## FP Support

Scala is a complete FP language, with full support for:

*   Functions as values
*   Higher-order functions
*   Lambdas
*   Everything is an expression that returns a value
*   Immutable (algebraic) variables
*   Immutable collections classes (data structures), with dozens of built-in functional methods

## Hello, world

The most basic Scala 3 â€œHello, worldâ€ example:

`@main def hello = println("Hello, world")`

The same thing, but with a variable:

`@main def hello =`
`    val w = "world"`
`    println(s"Hello, $w")`

If theyâ€™re in a file named `Hello.scala`, run them with Scala CLI like this:

`scala-cli Hello.scala`

## Variables

Immutable (algebraic) variables are preferred, and are created with the `val` keyword:

`// immutable variables (use as much as possible)`
`val a = 1`
`val b = 2.2`
`val c = "Hello"`
`val d = true`

Create mutable variables only when necessary, with the `var` keyword:

`// mutable variables (use rarely, if at all)`
`var a = 1`
`a = 2`

You generally donâ€™t need to *explicitly* declare data types, Scala can figure them out *implictly*:

`// type inference`
`val a = 1          // Int`
`val b = 2.2        // Double`
`val c = "Hello"    // String`
`val d = true       // Boolean`

## Strings

Create multiline strings like this:

`val s = """`
`    |Alvin Alexander`
`    |123 Main Street`
`    |Talkeetna, AK 99676`
`""".stripMargin`

Embed variables inside strings like this:

`val firstName = "Alvin"`
`val lastName = "Alexander"`
`val fullName = s"$firstName $lastName"`

## Most-Common Classes

Scala is an OOP and an FP language, so `Int`, `Double`, `String`, and `Boolean` are all implemented as classes.

Classes youâ€™ll use all the time:

*   `Int`
*   `Double`
*   `String`
*   `Boolean`

`val a = 10`
`val b = 2.2`
`val c = "Yo"`
`val d = true`

Common sequences:

*   `List`
*   `Seq`
*   `Vector`
*   `ArrayBuffer` (mutable)

Maps:

*   `Map`

Other:

*   `Tuple`
*   `Range`
*   `Set`

See below for examples of all of those.

## Language constructs

### if/then/else

Here are a few `if`/`then`/`else` examples:

`// every construct is an expression, so you can assign`
`// an if/then result to a variable:`
`val a = if x < 0 then -x else x`

`// you can also use if/then as the body of a function:`
`def compare(a: Int, b: Int): Int =`
`    if a < b then`
`        -1`
`    else if a == b then`
`        0`
`    else`
`        1`
`    end if   // this is optional`

### for loops

`for` *loops* are used for side effects, such as printing:

`// single line:`
`for i <- ints do println(i)`

`// multiline:`
`for`
`    i <- ints`
`    if i > 2`
`do`
`    println(i)`

`// optionally close the expression with 'end for':`
`for`
`    i <- ints`
`    if i > 2`
`do`
`    println(i)`
`end for`

### for expressions (for/yield)

`for` *expressions* are true expressions that yield values:

`// create a sample list:`
`val ints = List.range(1, 10)`

`// write for/yield like this:`
`val tenX = for i <- ints yield i * 10`

`// or this:`
`val tenX = for`
`    i <- ints`
`    if i > 5`
`yield`
`    i * 10`

`// or this:`
`val tenX =`
`    for`
`        i <- ints`
`        if i > 5`
`    yield`
`        i * 10`

### match expression

Scala is famous for being a pattern-matching language. As its name implies, `match` is an expression that yields a value:

`val month = i match`
`    case 1  => "January"`
`    case 2  => "February"`
`    // more months here ...`
`    case 11 => "November"`
`    case 12 => "December"`
`    case _  => "Invalid month"  // the default, catch-all`

`// used for a side effect:`
`i match`
`    case 1 | 3 | 5 | 7 | 9  => println("odd")`
`    case 2 | 4 | 6 | 8 | 10 => println("even")`

`// a function written with 'match':`
`def isTrueInPerl(a: Matchable): Boolean = a match`
`    case false | 0 | "" => false`
`    case _ => true`

Note: There are *many* more ways to use `match` expressions.

### try/catch/finally

Scalaâ€™s `try`/`catch`/`finally` expressions are similar to Java, but are also expressions that return a value:

`def readTextFile(filename: String): Option[List[String]] =`
`    try`
`        Some(Source.fromFile(filename).getLines.toList)`
`    catch`
`        case e: Exception => None`
`    finally`
`        // close any resources here`

## Functions

Scala functions and methods are created with the `def` keyword. They can be written on one line, or as many lines as needed:

`def sum(a: Int, b: Int): Int = a + b`

`def max(a: Int, b: Int): Int =`
`    // as many lines as you need here`
`    if a > b then a else b`

### Default parameter values

Function parameters can have default values:

`def getUrlData(`
`    url: String,`
`    connectionTimeout: Int = 5_000,`
`    readTimeout: Int = 5_000`
`): String =`
`    println(s"cTimeout = $connectionTimeout, rTimeout = $readTimeout")`
`    // your real code would be here`
`    "Hereâ€™s the data!"`

`getUrlData("https...")                   // cTimeout = 5000, rTimeout = 5000`
`getUrlData("https...", 2_500)            // cTimeout = 2500, rTimeout = 5000`
`getUrlData("https...", 10_000, 10_000)   // cTimeout = 10000, rTimeout = 10000`

### A function that takes a function parameter

A three-step process.

[1] Define function that takes other functions as input parameters:

`// callback is a "function input parameter" (FIP):`
`def sayHello(callback: () => Unit): Unit =`
`    callback()`

`// this defines a FIP that (a) takes no input parameters and`
`// (b) returns nothing (Unit is like void):`
`def sayHello(callback: () => Unit): Unit =`
`                       ----------`

[2] Define other functions:

`def helloAl(): Unit =`
`    println("Hello, Al")`

`def holaLorenzo(): Unit =`
`    println("Hola, Lorenzo")`

[3] Pass those to `sayHello`:

`sayHello(helloAl)        // prints "Hello, Al"`
`sayHello(holaLorenzo)    // prints "Hola, Lorenzo"`

(See [Functional Programming, Simplified](https://alvinalexander.com/scala/functional-programming-simplified-book) for many more details on how this works.)

## Functional error handling

Scala has the concepts of functional error handling and error-handling data types.

*   Functions *should not* throw exceptions
*   They *should* return functional error-handling types:
    *   `Option`
    *   `Try`
    *   `Either`

This is demonstrated in many places in the book, such as the `makeInt` function:

`def makeInt(s: String): Option[Int] =`
`    try`
`        Some(s.toInt)`
`    catch`
`        case e: NumberFormatException => None`

## Domain Modeling (MD)

When programming in an OOP style, youâ€™ll primarily use these Scala constructs:

*   Traits
*   Enums
*   Classes
*   Objects

Class examples:

`class Person`

`class Person(val name: String, val age: Int)`

`class Person(val name: String, val age: Int)`
`    override def toString = s"$name is $age years old"`

When programming in an FP style, youâ€™ll primarily use these constructs:

*   Traits
*   Enums
*   Case classes
*   Objects

### DM: Classes

An OOP-style class has parameters that are created with the `var` keyword, so they can be changed (mutated) later:

`// one-liner:`
`class Person(var firstName: String, var lastName: String)`

`// when it gets longer:`
`class Person(`
`    var firstName: String,`
`    var lastName: String`
`)`

Create a new instance, then access and mutate its parameters/fields:

`val p = Person("Reginald", "Dwight")`

`// access the fields:`
`println(p.firstName)   // prints "Reginald"`
`println(p.lastName)    // prints "Dwight"`

`// mutate them:`
`p.firstName = "Elton"`
`p.lastName = "John"`

`// print the new values:`
`println(p.firstName)   // prints "Elton"`
`println(p.lastName)    // prints "John"`

A class with some enums as well:

`enum CrustSize:`
`    case Small, Medium, Large`

`enum CrustType:`
`    case Thin, Thick, Regular`

`enum Topping:`
`    case Cheese, Pepperoni, Olives`

`class Pizza (`
`   var crustSize: CrustSize,`
`   var crustType: CrustType,`
`   val toppings: ArrayBuffer[Topping]`
`):`

`    override def toString = s"$crustSize $crustType with $toppings"`

`    // create a method to determine the pizza cost based on its attributes:`
`    def cost: Double = ???`

`    // create a method to determine the pizza price based on its attributes:`
`    def price: Double = ???`

`end Pizza`

In that example, we use `???` as the method body until weâ€™re ready to implement it.

### DM: Enums

Scala 3 has enums, or enumerations:

`enum Suit:`
`    case Clubs, Diamonds, Hearts, Spades`

`// some time later ...`
`import Suit.*`

`def printEnum(suit: Suit) = suit match`
`    case Clubs    => println("clubs")`
`    case Diamonds => println("diamonds")`
`    case Hearts   => println("hearts")`
`    case Spades   => println("spades")`

### DM: Traits

Traits can used like Java interfaces, and can also be used like Ruby mixins.

`trait Animal:`
`    def speak(): Unit`

`trait HasTail:`
`    def wagTail(): Unit`

`class Dog extends Animal, HasTail:`
`    def speak(): Unit = println("Woof")`
`    def wagTail(): Unit = println("âŽžâŽœâŽ›  âŽžâŽœâŽ›")`

`val d = Dog()`

### DM: Objects

Objects are used to create singletons. Functions in objects are like `static` methods in Java.

`object StringUtils:`

`    def truncate(s: String, length: Int): String =`
`        s.take(length)`

`    def lettersAndNumbersOnly_?(s: String): Boolean =`
`        s.matches("[a-zA-Z0-9]+")`

`    def lettersOnly_?(s: String): Boolean =`
`        s.matches("[a-zA-Z]+")`

`    def containsWhitespace(s: String): Boolean =`
`        s.matches(".*\\s.*")`

`end StringUtils`

### DM: Case classes

*Case classes* start with the `case` keyword, and are intended for FP:

`case class Person(name: String, relation: String)`

`val christina = Person("Christina", "niece")`
`christina.name            // "Christina"`
`christina.name = "Fred"   // error: reassignment to val`

`val aleka = christina.copy(name = "Aleka")`
`aleka.name                // "Aleka"`

`christina == aleka        // false`

### DM: Union types

Scala 3 has *union* types, which let your code be even more dynamic. This function takes an `Int` *or* a `String` as an input parameter:

`// Perl version of "true"`
`def isTrueInPerl(a: Int | String): Boolean = a match`
`    case 0 | "0" | "" => false`
`    case _ => true`

This one returns a union type as a function result:

`def aFunction(): Int | String =`
`    val x = scala.util.Random.nextInt(100)`
`    if (x < 50) then x else s"string: $x"`

For more information, see [my blog post](https://alvinalexander.com/scala/scala-3-union-types-cookbook-simulate-dynamic-typing/).

## Collections Classes

Some common collections classes:

`val xs = List(1, 2, 3)           // a simple linked-list`
`val xs = Vector(1, 2, 3)         // a high-performance, immutable sequence`
`val xs = ArrayBuffer(1, 2, 3)    // a high-performance, mutable sequence`

`val states = Map(`
`    "AK" -> "Alaska",`
`    "AL" -> "Alabama"`
`)`

`val s = Set(1, 2, 1, 3)    // s: Set(1, 2, 3)  (duplicates are dropped)`

## Collections Methods

Scala sequence classes have *many* methods with functional methods that take anonymous functions (lambdas) to solve problems. Hereâ€™s the `List` class and some of its methods:

`val a = List(10, 20, 30, 40, 10)      // List(10, 20, 30, 40, 10)`
`a.distinct                            // List(10, 20, 30, 40)`
`a.drop(2)                             // List(30, 40, 10)`
`a.dropRight(2)                        // List(10, 20, 30)`
`a.dropWhile(_ < 25)                   // List(30, 40, 10)`
`a.filter(_ < 25)                      // List(10, 20, 10)`
`a.filter(_ > 100)                     // List()`
`a.find(_ > 20)                        // Some(30)`
`a.slice(2,4)                          // List(30, 40)`
`a.take(3)                             // List(10, 20, 30)`
`a.takeRight(2)                        // List(40, 10)`
`a.takeWhile(_ < 30)                   // List(10, 20)`

And some more:

`val evens = List(2, 4, 6)                  // List(2, 4, 6)`
`val odds = List(1, 3, 5)                   // List(1, 3, 5)`
`val fbb = "foo bar baz"                    // String = foo bar baz`
`val firstTen = (1 to 10).toList            // List(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)`
`val empty = List[Int]()                    // List[Int] = List()`
`val letters = ('a' to 'f').toList          // List(a, b, c, d, e, f)`

`evens.contains(2)                          // true`
`firstTen.containsSlice(List(3,4,5))        // true`
`firstTen.count(_ % 2 == 0)                 // 5`
`firstTen.endsWith(List(9,10))              // true`
`firstTen.exists(_ > 10)                    // false`
`firstTen.forall(_ < 20)                    // true`
`letters.indexOf('b')                       // 1 (zero-based)`
`letters.indexOfSlice(List('c','d'))        // 2`
`firstTen.indexWhere(_ == 3)                // 2`
`letters.isDefinedAt(1)                     // true`
`letters.isDefinedAt(20)                    // false`
`letters.isEmpty                            // false`
`empty.isEmpty                              // true`

`val fbb = "foo bar baz"`
`fbb.indexOf('a')                           // 5`
`fbb.lastIndexOf('a')                       // 9`
`fbb.lastIndexOfSlice("ar")                 // 5`
`fbb.lastIndexOfSlice(List('a','r'))        // 5`
`fbb.lastIndexWhere(_ == 'a')               // 9`
`fbb.lastIndexWhere(_ == 'a', 4)            // -1`
`fbb.lastIndexWhere(_ == 'a', 5)            // 5`

`firstTen.max                               // 10`
`letters.max                                // f`
`firstTen.min                               // 1`
`letters.min                                // a`
`letters.nonEmpty                           // true`
`empty.nonEmpty                             // false`
`firstTen.product                           // 3628800`
`letters.size                               // 6`

`firstTen.startsWith(List(1,2))             // true`
`firstTen.startsWith(List(1,2), 0)          // true`
`firstTen.startsWith(List(1,2), 1)          // false`
`firstTen.sum                               // 55`

`// fold and reduce examples`
`firstTen.fold(100)(_ + _)                  // 155`
`firstTen.foldLeft(100)(_ + _)              // 155`
`firstTen.foldRight(100)(_ + _)             // 155`
`firstTen.reduce(_ + _)                     // 55`
`firstTen.reduceLeft(_ + _)                 // 55`
`firstTen.reduceRight(_ + _)                // 55`

`firstTen.fold(100)(_ - _)                  // 45`
`firstTen.foldLeft(100)(_ - _)              // 45`
`firstTen.foldRight(100)(_ - _)             // 95`
`firstTen.reduce(_ - _)                     // -53`
`firstTen.reduceLeft(_ - _)                 // -53`
`firstTen.reduceRight(_ - _)                // -5`

## Tuples

A *tuple* is a heterogeneous collection of elements, which means that a tuple can contain different types of elements:

`val t = (1, "yo")    // (Int, String)`

A tuple that contains an `Int`, `String`, `Char`, and `Double`:

`val t = (1, "1", '1', 1.1)`

Examples:

`val t = (42, "fish")`

`t(0)     // 42`
`t(1)     // "fish"`

`t.size   // 2`

## Ranges

Ranges let you create ranges of integers or characters:

`1 to 5         // will contain Range(1, 2, 3, 4, 5)`
`1 to 10 by 2   // will contain Range(1, 3, 5, 7, 9)`
`1 to 10 by 3   // will contain Range(1, 4, 7, 10)`

`for i <- 1 to 10 do println(i)`

## A Little Scala 3 Application

This is a complete little Scala 3 application with a `main` method. You can run it with `scala-cli` to make an HTTP `GET` request:

`//> using scala "3"`
`//> using lib "com.softwaremill.sttp.client3::core::3.7.2"`
`// the two previous lines are the Scala CLI way to say that`
`// you want to use (a) the latest version of Scala 3, and`
`// (b) the 'sttp' client library.`

`// run me with 'scala-cli HttpGet.scala'`

`import sttp.client3.*`

`@main def doGet =`
`    val backend = HttpURLConnectionBackend()`
`    val response = basicRequest`
`                      .get(uri"http://httpbin.org/get")`
`                      .send(backend)`
`    println(response)`

# Appendix B. The Scala REPL

With most programming languages having REPL environments â€” Javaâ€™s `jshell`, Kotlinâ€™s playground, Pythonâ€™s shell, etc. â€” Iâ€™ll just quickly cover the Scala REPL.

The acronym *REPL* stands for â€œread/evaluate/print/loop,â€ and the Scala REPL is an interactive tool that lets you experiment with Scala code. I refer to it as a *playground* or *laboratory*, because itâ€™s a place where you can run experiments on Scala code to make sure it works like you expect it to.

Start the REPL at the command line with Scala CLI like this:

`$ scala-cli repl`

Or, if you have the [Scala 3 SDK](https://www.scala-lang.org/download) installed on your system, start it like this:

`$ scala`

In either case you should see something like this:

`Welcome to Scala 3.1.1`
`Type in expressions for evaluation. Or try :help.`

`scala> _`

Now you can start experimenting with Scala code:

`scala> val x = 1`
`x: Int = 1`

`scala> val y = 2`
`y: Int = 2`

`scala> x + y`
`res0: Int = 3`

As shown in those examples:

*   You generally create new variables in Scala with the `val` keyword (but can also use `var` for mutable variables).
*   `x` and `y` are the names of two variables that I created.
*   After you press the `[Enter]` key, the REPL output shows the result of your expression, including any variable names, their data type (such as `Int`), and value.
*   If you donâ€™t assign a variable name, as in the third example, the REPL creates its own variable, beginning with the name `res0`, then `res1`, etc. You can then use these variable names just as though you had created them yourself:

`scala> res0 * 3`
`res1: Int = 9`

The REPL is a great place to experiment, and most Scala developers have a REPL session running every day.

Besides variables, you can enter any legal Scala code:

`scala> def add(i: Int, j: Int): Int = i + j`
`def add(i: Int, j: Int): Int`

`scala> add(2, 2)`
`val res2: Int = 4`

## A few tips

*   The REPL has tab completion. (Ex: type `"hi".` and then `[Tab]`).
*   Quit a REPL session with `:quit` or `[Control][d]`.
*   Thereâ€™s a more powerful Scala REPL named *Ammonite*. Start it like this:

`$ scala-cli repl --amm`

There are other alternatives:

*   [Scastie](https://scastie.scala-lang.org) is a website that works like the REPL, or a worksheet
*   VS Code and IntelliJ IDEA both have worksheets

# Appendix C. Scala CLI (Compiling and Running Code)

Until some time in the year 2021 I would have written this book using only the [Scala SDK](https://www.scala-lang.org/download) and its `scalac` and `scala` commands to compile and run your code, respectively. (These are just like `javac` in Java, `kotlinc` in Kotlin, and `java` with both of those.)

But since that time the [Scala CLI command](https://scala-cli.virtuslab.org) project has come along, and it greatly simplifies the â€œgetting started with Scalaâ€ experience, so I use it in this book. Scala CLI:

*   Is much simpler to use, especially when youâ€™re first getting started with Scala
*   Lets you easily compile and run both (a) small applications and (b) Scala scripts
*   Lets you easily include third-party libraries in apps and scripts, such as using HTTP, JSON, and HTML libraries for working on the internet, along with testing libraries (so you can include tests in your code)
*   Lets you export your project configuration details to build tools like *Sbt* or *Mill*, once it feels too large for Scala CLI.

At the time of this writing thereâ€™s also an effort to make Scala CLI the official Scala command (`scala`). I donâ€™t know if that will come to complete fruition, but if it does, youâ€™ll be in great shape.

Because I use Scala CLI in this book, I want to share a little â€œcheat sheetâ€ of how to use its basic features here.

> NOTE: At the time of this writing, Scala CLI is at version 0.1.12, so be aware that some of the following features may change over time.

## Compiling and running applications

If you have an application with an `@main` method named `hello` in a file named `Hello.scala`, and you want to run that application, this is how you run it:

`$ scala-cli Hello.scala`

That command both *compiles* and *runs* your application in one step. If instead you want to do those in separate steps, do this:

`$ scala-cli compile Hello.scala`
`$ scala-cli run hello`

You can also *continuously compile* your code with the `--watch` parameter:

`$ scala-cli compile Hello.scala --watch`

## Compiling and running scripts

Scala CLI currently makes a distinction between Scala *applications*, which are in `.scala` files, and Scala *scripts*, which are in files that end with the `.sc` extension. A main difference between the two is that a script doesnâ€™t have to have an `@main` method; it can just consist of a series of statements and expressions.

To demonstrate how to run a script, hereâ€™s a script named `MyScript.sc` that consists of just one line:

`args.foreach(println)`

In a Scala CLI script, the `args` variable is implicitly made available to you, so you can access command-line arguments. This is how you run that script:

`$ scala-cli MyScript.sc -- hello world`
`hello`
`world`

Notice that the `--` characters are required before your command-line arguments.

## â€˜usingâ€™ directives

One of the great things about Scala CLI is its concept of â€œ`using` directives.â€ These directives give you a way to control how your code will be run, including specifying what Scala version is used, and what third-party libraries your application uses.

You add these directives with this special syntax, which must be put in your script or application before any other Scala code:

`//> using scala "3"`

With this directive at the top of your file, when you run your application with `scala-cli`, it sees this line and then interprets the rest of your code using the latest version of *Scala 3* (such as Scala 3.1.1, for example).

In addition to specifying which Scala version should be used, you can also specify the dependencies your application requires. For example, I use these two directives at the beginning of some HTTP `GET` and `POST` scripts I share in my book, [Learn Scala 3 The Fast Way](https://amzn.to/3L4YwR4):

`//> using scala "3"`
`//> using lib "com.softwaremill.sttp.client3::core::3.7.2"`

`// the rest of the Scala code follows ...`

There are many more things you can do with `using` directives. See the [Scala CLI website](https://scala-cli.virtuslab.org/) for more details.

## Even more

On top of these basics thereâ€™s *much* more that Scala CLI can do for you. In addition to what Iâ€™ve shown, you can:

*   Create self-enclosed scripts
*   Include multiple dependencies
*   Declare specific Scala versions to use (such as 2.12.15 or 3.1.1)
*   Run tests
*   Create small projects
*   Integrate with your IDE
*   Package your applications
*   More!

For all those details, see the [Scala CLI website](https://scala-cli.virtuslab.org).

# Appendix D. Classes That Use Generic Types

As with other programming languages, a *generic parameter* in Scala is a placeholder for *concrete* data types that will later be supplied in the position where the generic type is declared.

This is one of those situations where itâ€™s easiest if you just jump right into the pool, so Iâ€™ll start with this example:

`class Box[A](val item: A)`

Thatâ€™s probably the simplest possible class you can create that has a generic constructor parameter. It defines a class named `Box` with a single constructor parameter named `item`, which has the generic type `A`. Notice that Scala requires you to declare generic types in brackets before the list of constructor parameters:

`class Box[A](val item: A)`
`         ---`

Then, in the parameter list, this is how you say that when an instance of `Box` is created, `item` can be any type:

`class Box[A](val item: A)`
`                       -`

Because `A` represents a generic type, when you create a `Box` instance, the actual type can be an `Int`, `String`, `Boolean`, whatever. With this declaration, youâ€™re saying that the type can be anything, basically the actual type used isnâ€™t important to you (or your algorithm).

Now you can create `Box` instances with any legal Scala type:

`val a = Box(1)       // Int`
`a.item   // 1`

`val b = Box("yo")    // String`
`b.item   // "yo"`

`val c = Box(true)    // Boolean`
`c.item   // true`

A few key points:

*   `A` is a generic type parameter
*   In Java, the standard is that generic types begin with the letter `T`, but in Scala we begin them with the letter `A` (but this is just a convention)
*   As I mention in the next lesson, an implication of using a generic parameter is that the algorithms inside your class must not care about the actual type (`Int`, `String`, whatever) that is later used when `Box` instances are created.

Youâ€™ll also see symbols like `+`, `-`, and `<:` used with generic parameters. For a few details on those, see the â€œA Quick Look at Variance and Boundsâ€ lesson that follows.

## Multiple generic parameters

When you need to define a class that has multiple constructor parameters with generic types, define it like this:

`class Pair[A, B](val a: A, val b: B):`
`    def getKey: A = a`
`    def getValue: B = b`

Notice how the generic types `A` and `B` are (1) declared in the brackets, (2) used with the constructor parameters, and (3) used with the two methods in the class.

Now you can use `Pair` like this:

`val a = Pair(1, "one")`
`a.getKey      // 1 (an Int)`
`a.getValue    // "one" (a String)`

Furthermore, because both variables are declared to have generic types, you can use *any* type in the two positions:

`Pair(1, 2)       // A and B are both Int`
`Pair(1, "1")     // A is Int, B is String`
`Pair("1", 2.2)   // A is String, B is Double`

Notice in the first example that when you use two types like `A` and `B`, youâ€™re saying, â€œThese two types *can* be different, but they donâ€™t have to be; they can both be `Int`, for example.â€

In the `Pair` class I intentionally use the method names `getKey` and `getValue` because this is a port of [this Java example](http://docs.oracle.com/javase/tutorial/java/generics/types.html), except that I created mine as a `class` rather than their Java `interface`:

`public interface Pair<K, V> {`
`    public K getKey();`
`    public V getValue();`
`}`

When youâ€™re working with a `Map` or any other type that has a key and value, the standard is also to use `K` and `V` instead of `A` and `B`, so this code is preferred over my first example:

`class Pair[K, V](val key: K, val value: V):`
`    def getKey: K = key`
`    def getValue: V = value`

# Appendix E. Functions That Use Generic Types

Defining a function or method to take a generic input parameter is similar to defining a class that takes a generic constructor parameter. For instance, without generics, I *could* define a function like this to get a random `String` from a `Seq[String]`:

`def randomName(names: Seq[String]): String =`
`    val randomNum = util.Random.nextInt(names.length)`
`    names(randomNum)`

However, because thereâ€™s nothing in the function body that depends on the type inside the `Seq` being a `String`, I can make this function generic:

`def randomElement[A](seq: Seq[A]): A =`
`    val randomNum = util.Random.nextInt(seq.length)`
`    seq(randomNum)`

Now it works with any sort of type inside a `Seq`:

`randomElement(Seq("Emily", "Hannah", "Mercedes"))`
`randomElement(Seq(1,2,3))`
`randomElement(Seq.range('a', 'z'))`

As a rule of thumb, any time your function body doesnâ€™t depend on the type of an input parameter, you can make its type generic.

Just like when you use generic types with a class, you declare the type `A` in brackets before the function definition:

`def randomElement[A](seq: Seq[A]): A =`
`                  -`

Then you use that type with one or more input parameters inside the parentheses:

`def randomElement[A](seq: Seq[A]): A =`
`                              -`

In this case I also use the generic type as the functionâ€™s return value, though this isnâ€™t always the case:

`def randomElement[A](seq: Seq[A]): A =`
`                                   -`

Also, when you have a function that uses a generic type `A` as an input parameter and returns a potentially-different generic type, declare that second one with the letter `B`, and write it like this:

`def f[A, B](x: SomeType[A]): B = ???`

And if functions need more generic type parameters, just keep adding them the same way:

`def f[A, B, C](a: A, b: B): C = ???`

# Appendix F. A Quick Look at Variance and Bounds

In this lesson I take *a very quick look* at two other generics concepts, *variance* and *bounds*.

## Variance

In the previous lesson about using generic types with class constructor parameters, I showed this class:

`class Pair[A, B](val a: A, val b: B):`
`    def getKey: A = a`
`    def getValue: B = b`

Because thatâ€™s the complete class, and both `A` and `B` are only ever used in *out* positions â€” meaning that their values only come out of methods, and are never updated by values coming into methods â€” it would have been more correct to declare the two type parameters with `+` symbols, like this:

`class Pair[+A, +B](val a: A, val b: B):`
`    def getKey: A = a`
`    def getValue: B = b`

The `+` symbol tells the compiler that you only intend to use these parameters in the *out* position inside your class, so if you ever try to accept them as a method parameter, your code wonâ€™t compile. Itâ€™s your way of saying to the compiler that these variables are immutable and read-only.

Declaring a generic parameter with the `+` symbol also has other benefits, and I detail those in my blog post, [Generic type parameters and variance explained](https://alvinalexander.com/scala/scala-3-variance-explained-generic-type-parameters/). In that post I write about the difference between parameters declared as `A`, `+A`, and `-A`.

> NOTE: Iâ€™m intentionally keeping this short, because I donâ€™t get into variance in this book.

## Bounds

The second thing youâ€™ll want to know is what I write about in my blog post, [How to define a generic method parameter that must extend a base type (bounds)](https://alvinalexander.com/scala/how-define-method-generic-parameter-must-extend-base-type). In that post I first show this function:

`def getName[A <: RequiredBaseType](a: A) = ???`
`            ---------------------`

In this example, the underlined code means, â€œThe parameter `a` has the generic type `A` *and* `A` must be a subtype of `RequiredBaseType`.â€

As a more concrete example later in the post, I create a small type hierarchy, followed by this function:

`def getName[A <: AnimalWithLegs](a: A): String = a.name`

I donâ€™t show the hierarchy here, but as you can imagine, people and dogs have legs, so these function calls are allowed, and compile properly:

`getName(Person("Fred", 20))`
`getName(Dog("Rover"))`

But because a snake does not have legs, this attempt to call the function will not compile:

`getName(Snake("Noodles"))   // error`

Iâ€™m also trying to keep this example short, but as a tad bit more information:

*   In my blog post example, `Person` and `Dog` both extend an `AnimalWithLegs` trait, but `Snake` does not.
*   The `<:` is used to create something thatâ€™s called an *upper bound* in Scala.

Please see that blog post for more details about how â€œboundsâ€ work.

# Appendix G. File I/O with â€˜Usingâ€™

In the lessons in this book that deal with reading and writing files, I violated my programming rules and used `var` fields and `null` values, because I thought that would make those functions more readable to Java, Kotlin, and other OOP developers. In this lesson Iâ€™ll show the preferred way to handle this situation in Scala.

## scala.util.Using

I donâ€™t remember the exact timeline, but historically there were several efforts outside of the Scala SDK to create control structures that would automatically close resources for developers. David Pollak wrote about one approach in *Beginning Scala*, and I document how that works in my blog post, [The `using` control structure from Beginning Scala](https://alvinalexander.com/scala/using-control-structure-beginning-scala-david-pollak/).

Then at some point in Scalaâ€™s history â€” after I wrote the first *Scala Cookbook* â€” a type named [`Using`](https://www.scala-lang.org/api/current/scala/util/Using$.html) was included in the `scala.util` package. Like these previous efforts, the purpose of this type is to automatically close any resources that you use, such as when you open file handles to perform I/O, and want to be sure that those file handles are always closed properly.

The `Using` type *guarantees* that those resources will be properly closed by making sure the resource is closed inside the `finally` section of a `try`/`catch`/`finally` block in its code. (For example, the `using` control structure I wrote about makes sure that a `close` method is called on the given resource inside `finally`.)

## Example

To demonstrate how `Using` works, this code shows how to re-write the `readFile` function I used earlier in this book to work with Scalaâ€™s `Using` type:

`import scala.io.Source`
`import scala.util.{Try, Using}`

`def readFile(filename: String): Try[String] =`
`    Using(io.Source.fromFile(filename)) { bufferedSource =>`
`        bufferedSource`
`            .getLines`
`            // need to add the "\n" character back in`
`            .map(line => s"$line\n")`
`            .mkString`
`    }`

Hereâ€™s how that code works:

*   `io.Source.fromFile` is a method that takes a `String` parameter that represents a filename, and returns a `scala.io.BufferedSource` (which is a subclass of `io.Source`).
*   That value is passed into a `Using` instance.
*   That creates a `BufferedSource` instance, which is then given the name `bufferedSource` as itâ€™s passed into the block of code that follows (inside the curly braces).
*   The `bufferedSource` instance is used to read all lines from the file with `getLines`.
*   The `map` method call adds a newline character to each line.
*   `mkString` converts those lines to a single `String`.
*   `Using` closes the `bufferedSource`, and returns that `String`, wrapped inside a `Try`.

A few more notes may help to digest that:

*   `BufferedSource` is like a `BufferedReader` in Java. Itâ€™s used to read text files.
*   `BufferedSource` is a subclass of `Source`, which has a `close` method.
*   I expect that youâ€™re probably familiar with `map` methods from other languages like Java and Kotlin, but in short, `map` is used with the function you supply to transform values, such as transforming all of the elements in a list.

So, in summary, this shows how to read a file without using `var` fields or `null` values. Additionally, [the `Using` documentation](https://www.scala-lang.org/api/current/scala/util/Using$.html) shows a few other ways it can be used.

## A shorter solution

Now that I showed the *preferred* solution, you can also solve this problem without `var`s or `null`s like this:

`import scala.util.Try`

`def readFile(filename: String): Try[String] = Try {`
`    val source = scala.io.Source.fromFile(filename)`
`    try`
`        source.getLines.map(line => s"$line\n").mkString`
`    finally`
`        source.close()`
`}`

This code is almost identical to the `Using` solution, but it relies on you calling the `close` method manually in the `finally` section. (I could have shown this solution earlier in the book, but I was trying to use constructs that are comfortable to Java and Kotlin developers.)

# Appendix H. â€œCall By-Nameâ€ Parameters (and Multiple Parameter Groups)

If youâ€™re interested in how `IO` data types work â€” or if youâ€™re like me a few years ago and wonder, *â€œHow can that possibly work?!â€* â€” one of the keys is that they take â€œCall By-Nameâ€ (CBN) input parameters. To me thatâ€™s an unusual term, so letâ€™s look at what it means before we look at three examples.

## Call By-Value

To understand CBN parameters, it helps to first know that by default, function input parameters are â€œCall By-Valueâ€ (CBV) parameters. The book, *Programming Scala* (co-written by Martin Odersky), makes this statement about â€œby-valueâ€ parameters:

> â€œTypically, parameters to functions are by-value parameters; that is, the value of the parameter is determined before it is passed to the function.â€

So if you pass in a variable named `x` and it has the value `42`, the `42` is whatâ€™s passed in.

## Call By-Name

Conversely, â€œby-nameâ€ parameters are quite different than by-value parameters. Rob Norris makes the observation that you can think about the two types of parameters like this:

*   A *by-value* parameter is like receiving a `val` field; its body is evaluated once, right before the parameter is bound to the function.
*   A *by-name* parameter is like receiving a `def` method; its body is evaluated later, whenever itâ€™s used inside the function.

He then says that those statements â€œarenâ€™t 100% accurate,â€ but I believe they are decent analogies to start with. The important part of that second statement is that a by-name parameter is like a `def` function, in that nothing happens with that parameter until you reference it inside your function. And if that parameter is inside an `if`/`else` expression or `match` expression, and its code branch is never reached, that CBN parameter will never be executed.

The book, *Scala Puzzlers*, confirms this when it states that by-name parameters are â€œevaluated only when they are referenced inside the function.â€

## Better names for by-name parameters?

According to Wikipedia, these terms date back to a language named ALGOL 60 (yes, the year 1960). I donâ€™t mean any disrespect to that language, but for me, the term â€œby-nameâ€ isnâ€™t very helpful (though Iâ€™m sure it had a solid meaning back then).

These days I find that the following terms are more accurate and meaningful:

*   Evaluate on access
*   Evaluate on use
*   Evaluate when accessed
*   Evaluate when referenced

With any of those phrases you can replace â€œEvaluateâ€ with words like â€œExecuteâ€ or â€œRun,â€ if you prefer.

But, because I canâ€™t go back in time and change this term, Iâ€™ll continue to use the acronym CBN in this lesson.

## Example 1

Perhaps the simplest-possible example of a CBN parameter is this:

`def exec(blockOfCode: => Unit): Unit =`
`    blockOfCode`

In this example, `blockOfCode` is a CBN parameter. Notice that the difference between a â€œnormalâ€ CBV input parameter and a CBN parameter is the use of the `=>` transformation symbol in the parameterâ€™s definition:

`def f(param: Int) ...      // CBV parameter`

`def f(param: => Int) ...   // CBN parameter`
`             --`

Because `=>` always means *transform* in Scala, you get the idea that `param` is *something* that is transformed into an `Int` in this example.

Now, going back to the `exec` function:

`def exec(blockOfCode: => Unit): Unit =`
`    blockOfCode`

we say that itâ€™s a function that executes the block of code thatâ€™s passed into it. The only thing thatâ€™s important about the `blockOfCode` CBN parameter is that its return type is `Unit`:

`def exec(blockOfCode: => Unit): Unit =`
`                      -------`

Therefore, you can read this input parameter as, â€œ`blockOfCode` is some piece of code that returns `Unit` when it runs.â€ Or you can say, â€œ`blockOfCode` is transformed into the `Unit` type after it runs.â€ Either of those statements is accurate.

This means that you can pass `exec` any code block that has the `Unit` return type, including a one-line block of code:

`exec(println(1))`
`     ----------`

or a multiline block of code enclosed in curly braces:

`exec {`
`    val i = 42`
`    println(s"Secret of the universe = $i")`
`}`

Because `println` has the `Unit` return type, both of those work.

As a quick recap, the two keys about CBN parameters that youâ€™ve seen so far are that you:

*   Define them with the `=>` symbol
*   Must specify their return type

## Example 2

Another great feature of CBN parameters is that you can use them *anywhere* inside your function. You can even call them multiple times inside your function, if your algorithm calls for that.

To demonstrate the *anywhere* aspect, hereâ€™s another example, where I call `codeBlock` in the second line of the function. Also notice that I define `codeBlock` to yield an `Int` instead of `Unit`:

`def exec(codeBlock: => Int): Unit =`
`    println("about to run the code")`
`    val result = codeBlock`
`    println(s"ran the code, result = $result")`

The REPL shows how `exec` works with a little block of code like `2 + 2`:

`scala> exec(2 + 2)`
`about to run the code`
`ran the code, result = 4`

Because `exec` takes *any* block of code that yields an `Int`, you can also pass functions into it, like these:

`def sum(a: Int, b: Int) = a + b`
`exec(sum(2, 3))`

`def multiply(a: Int, b: Int) = a * b`
`exec(multiply(2, 3))`

That last example looks like this in the REPL:

`scala> exec(multiply(2, 3))`
`about to run the code`
`ran the code, result = 6`

## Example 3: CBNs and multiple parameter groups

Before we get into the next example, a JIT piece of knowledge you need to know is that Scala functions can be defined to have *multiple input parameter groups*. The simplest possible example looks like this:

`def sum(a: Int)(b: Int): Int = a + b`

When a function is defined with two parameter groups like that, you just pass your parameters into it in two separate sets of parentheses when you call it, as shown in this REPL example:

`scala> sum(1)(1)`
`val res0: Int = 2`

This little feature enables us to do some cool things, such as to write our own control structures and domain-specific languages (DSLs), especially when combined with CBNs.

To demonstrate this, imagine that you want to create your own control structure named `doubleIf` that can be used like this:

`doubleIf(age > 18)(numAccidents == 0) {`
`    println("Discount!")   // some block of code here`
`}`

As shown, you pass it two test conditions in the first two parameter groups:

`doubleIf(age > 18)(numAccidents == 0) ...`
`         --------  -----------------`

and if both of those are `true`, `doubleIf` executes your block of code, which is between the curly braces, as the third parameter group.

If `doubleIf` sounds difficult to write â€” fear not! â€” itâ€™s relatively simple, as these things go. I just mentioned that `doubleIf` is a function that has three parameter groups, so you can start sketching it like this:

`def doubleIf()()()`

The first two parameter groups are test conditions, which means that they are both code blocks â€” CBN parameters â€” that yield a `Boolean` value:

`def doubleIf(test1: => Boolean)(test2: => Boolean)(???)`

Then the third parameter group is the block of code the caller wants to run if the two test conditions are `true`. In my case Iâ€™ll require that this returns `Unit`, to keep things simple:

`def doubleIf(test1: => Boolean)(test2: => Boolean)(codeBlock: => Unit)`

And finally, the body of the function says, â€œIf both test conditions are `true`, run the block of codeâ€:

`// test1 and test2 are shortened to t1 and t2 to fit the bookâ€™s page width`
`def doubleIf(t1: => Boolean)(t2: => Boolean)(codeBlock: => Unit): Unit =`
`    if t1 && t2 then codeBlock`

Now if you put this following code in the REPL, youâ€™ll see that the `"Discount!"` text is printed:

`val age = 20`
`val numAccidents = 0`

`doubleIf(age > 18)(numAccidents == 0) {`
`    println("Discount!")`
`}`

But if both of those conditions are not `true`, youâ€™ll see that `"Discount!"` is *not* printed.

As I hope this example shows, CBNs combined with multiple parameter groups give you the power to create your own control structures, and eventually your own DSLs.

## Key points

As a quick recap, these are some key points about CBNs:

*   You define them with the `=>` symbol
*   You must specify their return type
*   Theyâ€™re not executed until you call them in your function
*   They can be called anywhere in your function
*   They can be multiple times in your function
*   Combined with multiple parameter groups, they let us write our own control structures and DSLs

# Appendix I. Glossary

This glossary includes â€œsimpleâ€ descriptions of the terms used in this book, and a few other terms youâ€™ll hear in the FP world. (By *simple* I mean not too technical, or mathematical.)

algebraic substitution, substitution model

Means that you can substitute function calls with their results, just like youâ€™re writing algebra.

anonymous functions, lambda

In Scala, an anonymous function (or lambda) is the definition of a function *that isnâ€™t bound to a variable*. These are often little blocks of code that you pass into other functions, such as when calling `map` or `filter`.

compose, composition, combinator

In FP we say that we *compose* solutions by combining code like pure functions and expressions together. A key in this is that in order for us to be able to compose them, the output of one function must match the input to another function. You can think of this as being like writing a pipeline of Unix commands, such as `ps aux grep root wc -l`.

deterministic

Very similar to referential transparency (if not the same), a function is deterministic if it always produces the same output for a given input.

effect, effectful

(See below.)

expression-oriented programming (EOP)

A technique of programming with *expressions* rather than *statements*, where an *expression* is a block of code that returns a result, and has no side effects.

free variable

A free variable is what I call a variable that comes into a function through a side door. Itâ€™s not a formal function input parameter thatâ€™s declared in the functionâ€™s signature (the front door).

functor

I donâ€™t discuss functors in this book, but a functor *in Scala* is basically just a class that properly implements a `map` method. (Thereâ€™s more to it than that, but from a practical standpoint, thatâ€™s a key aspect.)

higher-order function

A function that either (a) takes a function as an input parameter, or (b) returns a function as its result.

idempotent, idempotence

Similar to the terms *deterministic* and *referential transparency*, itâ€™s said that a function is idempotent if the result of executing it multiple times for a given input is the same as executing it only once for the same input.

monad

*A monad in Scala* is basically just a class that implements a `map` and a `flatMap` method, AND, properly implemented, these two methods let you use instances of your class in a series of steps in a `for` expression. (Again, thereâ€™s bit more to it than that.) Classes like `List`, `Vector`, `Option`, `Try`, and `Either` are all monads. *In any FP language*, a monad guarantees lets you sequentially compose effects, such as with `flatMap` and in `for` expressions. (See below for a bit more.)

pure function

(See below.)

referential transparency

An expression is referentially transparent if it can be replaced by its resulting value without changing the behavior of the program.

## Effect, effectful

I donâ€™t believe thereâ€™s a standard definition of the terms *effect* and *effectful*. Some people say that a function is effectful if it has a side effect, such as dealing with I/O.

In my blog post, [What do â€œeffectâ€ and â€œeffectfulâ€ mean in functional programming?](https://alvinalexander.com/scala/what-effects-effectful-mean-in-functional-programming/), I wrote something different, which I learned from the book, [Functional and Reactive Domain Modeling](https://amzn.to/2uYGevc). Based on that book, in my blog post â€” and also from what youâ€™ve seen in this book â€” I make the following statements:

*   `Option` models the effect of *optionality* (of some result being optional)
*   `Try` and `Either` model the effect of *failure* (they manage exceptions as effects)
*   `Future` models *latency* as an effect

Another example is that if an `IO` type worked *only* with input/output, we could say that it â€œmodels I/O as an effect.â€ (However, as mentioned, modern `IO` types have much more power than this.)

From these examples we can say that an effect is *what the data type handles*: When you see `Option` as a functionâ€™s return type you immediately think the result is optional; when you see `Try`, you know that an error can happen; and so on. (Basically these types speak to you; they tell you what type of effect is happening inside a function.)

However, in addition to this, one thing thatâ€™s stressed in various ZIO documents and courses is that an effect is a *blueprint* of statements that can produce a side effect, and because itâ€™s just a blueprint, nothing happens right away. They say that the *description* of the effect must be different than its *execution*.

Similarly, the [Cats Effect documentation](https://typelevel.org/cats-effect/docs/concepts) states, â€œAn effect is a description of an action (or actions) that will be taken when evaluation happens.â€

Before Scala, my background was as an aerospace engineer, Unix admin, and then Java/OOP programmer. So when I started with Scala, one thing I didnâ€™t know is that its `Future` type does NOT fit this description, because as soon as you call its constructor, it begins running; it doesnâ€™t separate description from execution. Because of this, (a) `Future` is a good example of a type that is *not* an effect, and (b) FPers have created other types (like `IO` and `ZIO`) to use instead of `Future`.

Another important note in the Cats Effect documentation is, â€œCats Effect is all about making it possible to express effects as *values*.â€ A great example of this is in functional error handling, and how we model potential errors as effects â€” and resulting values â€” with `Option`, `Try`, and `Either`.

> This is a good time to be clear that a *type* is something like `Int` or `Option`, and a *value* is something like `1` or `Some("foo")`.

Common effects that are handled by Cats Effect and ZIO are:

*   Concurrency
*   Error handling
*   Resource safety (closing resources, such as when working with I/O)
*   Streaming
*   Tracing/troubleshooting

## Monads (example)

I wrote about monads earlier, and I mention there that `Option` is a monad. In Scala, a monad is essentially a type that properly implements `map` and `flatMap` methods so it can be used in `for` expressions. With `Option`, this specifically means that we can sequence effects in `for` expressions, where those effects are created to model the concept of optionality.

To demonstrate what I mean, hereâ€™s an example of using multiple `Option` values in sequence inside a `for` expression. First, here are three functions that return `Option` values that contain different types (`Int`, `Double`, and `String`):

`def fInt(): Option[Int] = Some(1)`
`def fDouble(): Option[Double] = Some(1.1)`
`def fString(): Option[String] = Some("alvin")`

Next, this code shows how you execute those operations in sequence in a `for` expression:

`val x = for`
`    a <- fInt()`
`    b <- fDouble()`
`    c <- fString()`
`yield`
`    (a, b, c)   // a tuple with three elements`

If you run that code in the REPL, youâ€™ll see that `x` has this type and value:

`x: Option[(Int, Double, String)] = Some((1,1.1,alvin))`
`   -----------------------------   -------------------`
`            xâ€™s type                    xâ€™s value`

As I show in the Monad lesson, you *could* write that code using a sequence of `flatMap` calls, but `for` expressions are typically easier for humans to read. But for the purpose of this glossary, my key points are (a) `Option` is a monad, because it is written to have `map` and `flatMap` methods that make is usable in `for` expressions, and (b) therefore, we can combine a series of `Option` values inside `for` expressions.

If youâ€™d like to experiment with this example, you can also simplify it like this:

`val x = for`
`    a <- Some(1)`
`    b <- Some(1.1)`
`    c <- Some("alvin")`
`yield`
`    (a, b, c)`

## Pure functions

Youâ€™ll find a surprising number of different definitions of pure functions on the internet, but to me, a *pure function* is a function:

*   Whose only parameters from the outside world are the input parameters that are defined in its function signature. (I refer to the list of input parameters as a functionâ€™s *front door*.)
*   That does not modify those input parameters.
*   That does not modify other â€œhiddenâ€ variables that might be accessed through side doors (*free* variables), such as mutable variables in its class or any other global variables.
*   That does not communicate with the outside world. It has no I/O whatsoever: no file access, no internet access, no database access, no quantum entanglement, nothing.
*   That always returns the same output when its given the same input. For example, `sum(2, 2)` is always `4`.
*   That returns output for all possible input values.
*   That does not throw exceptions.

Because of those last two attributes, FPers say that a function is *total*, meaning that it always returns a value. FPers also use terms like referential transparency, deterministic, and idempotent to describe pure functions.

![](images/00003.jpg)