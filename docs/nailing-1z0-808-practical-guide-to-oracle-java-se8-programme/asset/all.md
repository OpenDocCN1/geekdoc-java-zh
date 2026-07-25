![](cover.jpeg)

![](images/00003.jpeg)

Practical Guide
to
Oracle Java SE8 Programmer I Certification

**by Igor Soudakevitch**

**NAILING 1Z0-808:**

**Practical Guide to
Oracle Java SE8 Programmer I Certification**

by Igor Soudakevitch

All rights reserved. No part of this book may be reproduced or transmitted in any form or by any means, electronic or mechanical, including photocopying, recording or by any information storage and retrieval system, without written permission from the author, except for the inclusion of brief quotations in a review.

Copyright © 2016 by Igor Soudakevitch. First edition
[www.igor.host](http://www.igor.host) ISBN-13: 978-1540609649
ISBN-10: 1540609642

Java and the Java logo are registered trademarks of Oracle Corporation; Microsoft, Windows and Windows Server are registered trademarks of Microsoft Corporation in the United States and/or other countries. Other product and company names such as NetBeans, IntelliSense, etc. mentioned herein may be the trademarks of their respective owners. The author of this publication is not associated with any product or vendor mentioned in this book.

The example companies, organizations, products, domain names, email addresses, logos, people, places, and events mentioned herein are fictitious. No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.

This book expresses the author’s views and opinions. The information contained in this book is provided without any express, statutory, or implied warranties. Neither the author nor his resellers or distributors will be held liable for any damages caused or alleged to be caused either directly or indirectly by this book.

Interior and cover design: Igor Soudakevitch
Illustrations: Raphael Krivonogov

About the Author

**Igor Soudakevitch** never thought of writing this book; he sort of plunged into it headfirst when Providence gave him a mighty slap on his rump. And yet, however strange it may sound, *Nailing 1Z0-808* is a labor of love; for Igor cannot live without coding. He wrote his first program at the tender age of eleven, and still keeps that old, yellowish roll of perforated tape.

Igor relocated to Japan in 1990 to work as a researcher at Tokyo Institute of Technology, in the field that is known nowadays as Applied Nanotechnology and Nanoscience, but then changed lanes in order to fully embrace another passion of his life, namely translation and study of foreign languages.

After spending fourteen unforgettable years in the Land of Rising Sun and Blooming Robotics he returned to his native Moscow where he continues to live with his family, all the while rendering children's – and Nobel Prize winners' – books from English, French and Japanese into his mother tongue, tinkering with Raspi and Arduino, and writing articles on the art of what he enjoys most: coding and translating.

I am nothing without you, Tamaki.
Thank you for being in my life.

**ACKNOWLEDGEMENTS**

I have not attempted to cite in the text all the authorities and sources consulted in the preparation of this guide. To do so would require more space than is available.

There are, however, certain individuals without whom writing this book would be simply impossible. My special thanks go to Simon Roberts for his outstanding Live Lessons, Paul Anilprem and his colleagues at Enthuware for their exceptional product not to mention ever-present support, and all the good folks at the CodeRanch who helped me see the Java light and get to where I am now.

![](images/00004.jpeg)

*–Mommy? Why did you marry an idiot?*

*–How could you say that?! Our Daddy is smart! Look, he’s studying for his Java certification right now!*

*–Yes, I know… But why he laughs hysterically and screams "I’m an idiot!" every other minute?*

**AUTHOR’S NOTE**

As this is an account of personal experience, it is highly prejudiced and opinionated. If some of what follows sounds too categorical, it is based on the notes that were written *in extremis*. The author would not like to have on his conscience anything that may happen to the reader who puts blind trust into everything that the book recommends – or advises against.

**Contents**

[Acknowledgements](#part0002.html_page_3)

[Author’s Note](#part0002.html_id_342)

[Target Audience](#part0004.html_page_5)

[Abbreviations and Acronyms](#part0005.html_page_7)

[Preface](#part0006.html_page_8)

[Part I: Know Your Enemy](#part0007.html_page_12)

[Chapter I.0:      Toe Suckers and Guinea Pigs](#part0008.html_page_13)

[Chapter I.1:      Taking the Heat](#part0010.html_page_20)

[Chapter I.2:      Lock and Load](#part0011.html_page_25)

[External Resources](#part0012.html_page_36)

[Part II:      Exam Objectives, a.k.a. Pater Noster](#part0013.html_page_37)

[Chapter II.0:      Opening Remarks](#part0014.html_page_38)

[Chapter II.1:      Java Basics](#part0015_split_000.html_page_44)

[Keys & Discussion](#part0015_split_002.html_page_63)

[Chapter II.2:      Working With Java Data Types](#part0016_split_000.html_page_80)

[Keys & Discussion](#part0016_split_007.html_page_104)

[Chapter II.3:      Using Operators and Decision Constructs](#part0017_split_000.html_page_129)

[Keys & Discussion](#part0017_split_005.html_page_151)

[Chapter II.4:      Creating and Using Arrays](#part0018_split_000.html_page_169)

[Keys & Discussion](#part0018_split_002.html_page_178)

[Chapter II.5:      Using Loop Constructs](#part0019_split_000.html_page_188)

[Keys & Discussion](#part0019_split_002.html_page_203)

[Chapter II.6:      Working with Methods and Encapsulation](#part0020_split_000.html_page_217)

[Keys & Discussion](#part0020_split_006.html_page_242)

[Chapter II.7:      Working with Inheritance](#part0021_split_000.html_page_270)

[Keys & Discussion](#part0021_split_010.html_page_301)

[Chapter II.8:      Handling Exceptions](#part0022_split_000.html_page_336)

[Keys & Discussion](#part0022_split_002.html_page_350)

[Chapter II.9:      Working with Selected Classes from Java API](#part0023_split_000.html_page_370)

[Keys & Discussion](#part0023_split_008.html_page_397)

[Appendix A:      Registering for the Exam](#part0024.html_page_439)

[Appendix B:      RWJ.bat](#part0025.html_page_449)

[Appendix C:      Filter.java](#part0026.html_page_452)

[Appendix D:      Key Summary](#part0027.html_page_453)

**Target Audience**

**Given the following class definitions (disregard line numbers):**

![](images/00005.jpeg)

**What is the result when we attempt to compile and run the TargetAudience class from C:\Try_Java?**

A. 1Z0-808 is tricky!

B. Then again, maybe not...

C. Compilation fails

D. StringOutOfBoundsException is thrown at run time

See the correct answer overleaf.

**Answer to the ’Target Audience’ question:**

The correct answer is option C for the code does not compile.

The fail-safe way to solve problems on the exam is to read question first, then glance at the available choices to see if some of them can be eliminated immediately because options are syntactically invalid quite often, and only after that start analyzing code. Let me do it for you:

Prints this, prints that... hmm, a possible comperr... what? ***StringOutOfBoundsException***?! Nah, I don’t think so, **java.lang** has no such thing: it should’ve been SIOOBE → option D is out. Damn, three more to go. To the code, then.

Line numbers start with 1; full contents, then → need to verify if imports are listed *after* packages... check → all three classes live in different packages → RED ALERT! RED ALERT! some class members or constructors along the inheritance chain may be inaccessible... → aha! **TargetAudience** does extend another class! something fishy must be going on... → now to the **main()** method... right, an object... hmm, reftype differs from actype... oh, we're calling another class' constructor, aren’t we now? in a different package, no less? well, you know, that ctor better be `public`, otherwise no go... → yeap, just as I expected: it’s `protected` → LOC16 in **TargetAudience** won’t work. Done!

And here’s the actual error message produced by the compiler:

![](images/00006.jpeg)

The entire chain of reasoning takes but twenty seconds, and this is what you too will be able to pull off every single time on the exam regardless of the problem you’re facing – after you worked your way through this OCA bootcamp with all its obstacle courses, that is.

This book has one sole purpose: to hone your skills for solving exam questions both reliably and quickly; as such, it doesn’t even attempt to replace a full-fledged Java study guide. Ideally, *Nailing 1Z0-808* should become the beachhead from which you’ll be launching your final offensive to conquer the coveted ‘Oracle Certified Programmer I’ title. This entire tune-up, refueling and ammo-stocking phase won’t take more than three weeks. However, to benefit from it fully you should already know your way around Java basics so grab a solid tutorial, study online or watch^([1](#part0004.html_id_2)) video lessons and so on; *Preface* lists some reliable titles.

![](images/00007.jpeg)

I’d be very much interested in hearing how you fared on the exam. Do find a minute to tell me your score and what objectives you missed. Comments and suggestions are welcome.

[www.igor.host](http://www.igor.host)

* * *

^([1](#part0004.html_id_1)) You can find free Java online courses at MIT, UC Berkeley, etc. Stay away from YouTube, though: it has no QC.

**Abbreviations and Acronyms**

actype – actual object’s type at run time

assop – assignment operator; mostly used metonymically, in the sense of assignment statement

castype – data type specified inside the parentheses for an explicit cast

comperr – compilation error

ctor – constructor

def – definition

dim – dimension

initer – initializer

initing – initializing

op – operator

paramlist – list of formal parameters in a lambda expression

preditype – data type specified inside the angle brackets of a generified **Predicate**

reftype – reference type

refvar – reference variable

sout – any printing statement such as **System.out.println()**, etc.

stat – statement

ternop – ternary operator; often used metonymically to denote a ternary statement

var – variable

AIOOBE – `ArrayIndexOutOfBoundsException`

CCE – `ClassCastException`

ChE – checked exception

CSR – the Catch-or-Specify Requirement

DTPE – `DateTimeParseException`

E – an exception (regardless of the type)

IAE – `IllegalArgumentException`

IOE – `IOException`

IOOBE – `IndexOutOfBoundsException`

LDT – any of the new date/time classes in Java 1.8 (such as `LocalDate`, `LocalTime` or `LocalDateTime`)

LOC – line of code

NFE – `NumberFormatException`

NPE – `NullPointerException`

RTE – `RuntimeException`

SIOOBE – `StringIndexOutOfBoundsException`

TCF – `try-catch-finally` construct (not necessarily containing either `catch` or `finally`)

![](images/00008.jpeg)

This story does end happily, with data types flowing smoothly across the screen, almost nodding at me like old trusted friends. There was a moment, however, when it wasn’t at all that enjoyable; in fact, everything looked downright depressing.

This is what the author posted on the CodeRanch forum on May 20, 2016 (edited slightly for better readability):

A few days ago I failed my 1Z0-808 at 62%.

[This should] serve as a warning to those who dream about becoming Oracle-certified in a snap. Alright, here it goes:

I started preparing in the earnest six months ago. The first thing I did was quitting my job, quite literally.

After burning the proverbial bridges behind me I watched… no, that’s a wrong word; I worked painstakingly through the entire video course, a.k.a. *Live Lessons*, on 1Z0-803 by Simon Roberts. Was spending on that ten to twelve hours daily. Took me three weeks; no holidays, no weekends, no nothing… Why this long? Because I was hitting *Pause* every few seconds to write notes, think over what Simon was talking about and, most importantly, put all of it out in code. By using Notepad++. Yes, that’s right. For the first two months I wasn’t letting myself fire up an IDE.

Soon running my tiny ‘javalets’ directly from the CLI became so tedious that I hacked the Registry and wrote a minimalist launcher to run the code by right-clicking on the .java file in the Explorer window. This trick alone allowed me to write and test well over a hundred javalets a day, all the while learning new, even more mind-boggling rules from the JLS.

By my rough estimation, by the mid-January, 2016, I had thought up, tested, twisted, tortured, tormented, and otherwise tweaked with over 3,000 javalets while listening to and watching Simon. (Mind you, not because watching him makes you do all those unspeakable things, no. He did an outstanding work. The best there is. I’m going to write an extensive review about his video course, although not right now. Right now I don’t have the right. Right…)

And then I hit the books. Oh boy, did I hit ’em… Here’s the list:

–the ubiquitous *OCA: Oracle Certified Associate Java SE 8 Programmer I Study Guide. Exam 1Z0-808* by Jeanne Boyarsky & Scott Selikoff (loved it; positively loved it! granted, it’s ridden with typos but still makes a great read; in fact, THE greatest);

–*OCA Java SE 7* by Mala Gupta (liked it, especially all those tightly packed Review Notes; btw, her new book, this time on 1Z0-808, will be released very soon);

–*Head First Java* by Kathy Sierra & Bert Bates (dropped it after a couple of weeks; reason: the delivery grated on my nerves; in my eyes, it’ll make a perfect present to one’s worst enemy but that’s just me; anyhow, all my comments are highly subjective);

–*Thinking in Java* by Bruce Eckel (6th ed.) (not everything, of course; I didn’t touch collections, inner classes, threads, and other advanced topics that are not on the exam; I am awed by this book; a few pieces of code resemble poems, even; then again, it’s just me);

–few chapters from *Effective Java* by Joshua Bloch (am going to read it ten more times; pure pleasure);

–*Java 8\. Pocket Guide* by Robert & Patricia Liguori (I always keep this book within my reach and consult with it dozens of times daily);

–*Java in a Nutshell* by Benjamin Evans & David Flanagan (6th ed., which covers JSE8) (I think I did find a typo in their code but the book itself is undeniably excellent; helped me to look at certain concepts from a different angle; would love to translate it if I only had a chance…);

–*Exercices en Java* par Claude Delannoy (4e éd., couvre JSE8 aussi) (I certainly enjoyed it; would’ve gladly recommended it to any of my friends);

–*La programmation objet en Java* par Michel Divay (apparently, he teaches this very course at the Univ.of Rennes; the book itself is as dry as moon dust and bo-oring but it has one major advantage: it makes use of simple UML diags, which I find helpful when solving problems);

–and three more books in Russian, which are too obscure to talk about here.

Naturally, just reading books won’t cut it so I did exercises. As Jeanne Boyarsky loves to repeat, "Practice!" And so I practiced. It looked like this: read [Chapter 1](#part0008.html_page_13), do the exercises to that Chapter, do not check answers but read [Chapter 2](#part0014.html_page_38) instead, come back and repeat the exercises to [Chapter 1](#part0008.html_page_13), compare your own answers (to see if they are the same, otherwise it would mean that you are unsure about certain points) and finally check them against the key. Loop in the same fashion to finish the book. Cover all the books that have exercises. Then do it again and again until your score becomes at least 90% at every single pass.

Boyarsky & Selikoff’s book alone contains 345 exercises if we count in the three mock up exams; I did the whole cycle three times (and read the book itself four times, from cover to cover; now I’m reading it for the fifth time; I did quit my job, remember?). Mala Gupta’s book gives a lot of practice, as well…

I also enrolled for a four-week-long course on Java 8 that they teach at Bauman’s Technical University here, in downtown Moscow. Three hours of brain wracking practice in class, then solving all those home assignments until four o’clock in the morning. For twenty days.

Attended JPoint, a Java conference for students organized by the local JUG. Was reading all Java-related magazines I could get my hands on in all the languages I’m familiar with. Sat for hours cracking Java Interview questions that can be found on so many sites in India…

The idea was to saturate myself with Java code, until I puke blood or drop dead. Or both. Didn’t happen, though.

This epic picture will not be complete without me squinting at my screen while working through emulated exams; I had plenty of those, too:

–two 60-question-long practice exams that are bundled with *OCA SE7 Programmer I & II* by Kathy Sierra, et al.;

–over 600 questions in the Enthuware Question Bank;

–Kaplan Self-Test with its 180 questions;

–as for the testing software that comes with the B&S book, I stopped using it after seeing how many errors it contains; preferred pen and paper instead.

Kathy Sierra’s quizzes are tough. Enthuware’s even harder – and thoroughly enjoyable. The explanations alone are worth the buck; they are first rate, hands down.

As for Kaplan’s… I wish I could sue that sorry bunch. Their so-called ‘self-test’ (for which I paid over $80 and which is even advertised on the Pearson Vue^([2](#part0006.html_id_6)) site as a part of the official Oracle Certification Bundle, of all things) is the worst piece of software workmanship that I have ever seen in my entire life.

In case someone is curious why I resent them that much, here are the reasons; there are two of them… hold it! three!^([3](#part0006.html_id_4))

Firstly, the desktop version’s GUI is full of visual bugs that literally clutter the screen (seriously!) and it is only the web-based version that works as advertised. Secondly, their flash cards contain errors and ambiguities in the explanations, and finally, the questions are simply… well, too simple. I took their mock-up exam in the so-called Certification Mode and got 96%. Without breaking a sweat, with tons of time to spare, without even reviewing my answers…

Now, about Enthuware. My scores were 77% on Foundation, 74-79-75-81-74-80 on Standard Tests 1 thru 6, and 78% on the Last Day Test. The Enthuware developers have a sort of a running scoreboard on their site; it says that the average Standard Tests score from thousands of users is 74.8% while the actual exam score is 88%. My avscore was 77.2… so I thought I had this exam, this damned 1Z0-808 thingy in my pocket… Over 800 hours of reading, plus coding, plus cracking puzzles, plus almost 9000 lines of review notes that weren’t merely copied&pasted from anywhere but were indeed my own brainchildren… Notes to myself. Remember this, remember that… "Watch out for the wrappers’ constructors! they accept either underlying primitives or Strings!"… "Be on guard for trim()! StringBuilder doesn’t have it!"… "switch accepts compile-time constants only!"… Stuff like that. Even earned myself the ‘dry eye’ syndrome because of watching too many Simon Roberts videos, so now I’m dragging my sorry derrière around wiping tears from the corner of my right eye every few seconds. Like a fool. All those efforts… down the drain…

How do you call it? this strange, hollow feeling when you know, with a cold, calm, even serene and contented certainty know that you gave everything humanly possible – and yet it wasn’t enough?

Do not worry, I am about to finish. I think I know what my problem was and still is. Am going to test this hypothesis next time, around June 17\. Will report both the results and my findings.

Thanks for listening.
Signing off for now.

And then, on June 26, 2016…

This is a simple follow-up on my previous post:
I finally passed (98%); now to the 1Z0-809!

There was also one more post that I placed on [amazon.com](http://amazon.com) as a review for *OCA: Oracle Certified Associate Java SE 8 Programmer I Study Guide. Exam 1Z0-808* by Jeanne Boyarsky & Scott Selikoff:

Six weeks ago I failed my 1Z0-808 exam at 62%. Was too naïve, cocky and self-confident to the point of arrogance – and the exam creators taught me a lesson. Which I did learn because the day before yesterday I retook the exam and passed it with the 98% score. My study kit included three tools each of which, IMO, is a must for all those who need solid, certification-grade Java skills. Here’s the list:

–this study guide, which will give you every single bit of the theoretical and practical knowledge required to pass the exam with flying colors;

–a video course on preparing for the Oracle JSE exams by Simon Roberts (the very person who developed the initial concept of the questions a couple of decades ago; his video course was *the* foundation upon which I built and expanded my knowledge base further by reading this book);

–and, finally, the 1Z0-808 Test Studio by Enthuware, with its 600+ questions, which will probe, drill, grind, boil, and pig-roast you on all possible aspects and nuances. When you are done with it, you will be seeing both Java and yourself in a completely new light.

Clench your teeth, bear the pain – a lot of it is coming your way, especially if you are new to Java as I was – but stick to these three tools, and you *will* get your certification.

Unfortunately, none of these fine instruments can give you the second key to the success: they all discuss in detail purely technical matters while the way you work through and with the questions during the actual exam is equally important. At what speed should you go through the test? Since many of the questions are booby-trapped, is it advisable to second-guess yourself and attempt to re-solve the problem some other way? When you immediately see the "correct" answer, should you check every other option? Or is it better to move on to the next question right away because this way you’ll save time, and it is *time* that is the most precious resource during the exam... What about ‘cherry picking’? What about the ‘Review Later’ check-marks? Just how restrained or generous should you be with them? Is it safe to trust your gut instincts rather than do things by the book, checking and re-checking every single LOC methodically? As I found out, and at a great cost, too, some of the answers to these and many other questions are, in fact, counterintuitive and even paradoxical.

Tactics, guys, I’m talking tactics here. All those study guides, video lessons, exam simulators, and testing suits crafted by talented people are a part of your winning strategy but – sorry for sounding like Captain Obvious – it’s the execution that gets the job done. If you think this psychological cr*p is something that belongs to the 70s and that you’ll never have use for it, be my guest. Just go ahead, I wish you all the luck. You’ll need it. As for me, I had to learn this lesson the hardest way possible, for which I am actually grateful. The initial failure forced me to scrap and then rebuild my entire approach, devise a fool-proof plan of attack, invent shorthand notations for cracking loops, diagramming the objects’ lifecycle dynamics, expressing inheritance, polymorphic behavior, etc. and even to formulate dozens of concise, easy-to-remember rules all the while saturating myself with the Java code until my eyes start hurting whenever I see an erroneous snippet. No study guide that I know of, no software and no Java coders’ forum teach such skills, which I find quite puzzling because they are simply indispensable. To the extent that I am going to write a small book on the whole experience^([4](#part0006.html_id_12))…

Now, if I may, a direct advice: code. Code as much and as often as you can, immediately test all your ideas or doubts while reading, listening or simply thinking about what you’ve been learning AND DO NOT use an IDE for the first few weeks as the very minimum. Stick to your Notepad++ instead and run everything from the CLI. This will reveal your soft spots and the typical mistakes you tend to make.

Still reading? Hmm. Well, stop then and go get this study guide by Jeanne Boyarsky and Scott Selikoff, the test suite by Enthuware and the video course by Simon Roberts. Best of luck! I actually envy you: you still have your chance to score the perfect 100% :)

You know the saying, "*Practice makes perfect?*" It isn’t true. Only perfect practice makes perfect. To know syntax rules, principles of overriding and so on isn’t enough; I witnessed it firsthand. You need to learn how to apply them under stress, when everything works against you.

The pages that follow contain every single trick, approach, or technique I had been using while both preparing for and taking the actual exam. I will tell you *all of it*, down to the most boring and even embarrassing detail – because tactics *is* about details.

There is one problem, though. I did sign the NDA^([5](#part0006.html_id_10)) before taking the exam, so I can’t possibly give you a laundry list of correct answers to the real questions; often you’ll have to figure them out on your own by *inferring*: the very concept that we will meet again when working with generics and lambdas. But do not worry: I’ll be at your side all along, dropping hints now and then, and generally helping as much as humanly possible – and permissible by law.

Let me show you an example right away. Why am I reusing my old posts in this section of the book? Because this approach illustrates the principle that you will – you *will*! – encounter in one of the textual questions^([6](#part0006.html_id_8)) on the real exam. Can you name it, this principle? It is one of the benefits of polymorphism.

Hint: the preceding paragraph mentions the correct answer in the open. And here’s another hint, which is more like a reminder: the Test Studio by Enthuware has it all. *All the answers*. You just have to dig for them a little deeper.

* * *

^([2](#part0006.html_id_5)) And on Oracle University site, too…

^([3](#part0006.html_id_3)) Come to think of it, I can add one more: Kaplan SelfTest website misleads the prospective buyers into thinking that these mock-up tests mimick "the actual test environment perfectly" (I took this expression right from the Testimonials section on their landing page.) Mildly put, it isn’t true. In fact, none of the simulated 1Z0-808 prepware suits reproduce the look and feel of the *actual* test envionment – which puzzles me to no end. After all, it’s just GUI; no changes to the business logic are needed to recreate the atmosphere of the real exam…

^([4](#part0006.html_id_11)) This very book you are reading.

^([5](#part0006.html_id_9)) Non-Disclosure Agreement; we sign these whenever we are about to sit an Oracle cert exam.

^([6](#part0006.html_id_7)) Half a dozen of questions will have no code in them; they are included to test your knowledge of the most basic concepts of the object-oriented programming (OOP).

**PART I**

**Know Your Enemy**

![](images/00009.jpeg)

*–Young man! Don’t you know that the Department of Public Health warns about dangers of smoking?*

*–It’s OK. I’m a programmer, after all*.

*–?!*

*–We spit on warnings and care about errors only*.

![](images/00010.jpeg)

Once nailed, this certification is supposed to become our closest ally – if not a friend. Right now, however, it seems more like an uphill battle. This being said, let’s start by taking a closer look at the adversary’s stronghold.

As you probably remember, B&S^([7](#part0008.html_id_14)) contains a brief description of the history of OCA exams and what they are for. How about using another angle to better appreciate what’s in store for us?

This is what was published in the *Fix It* section of *Java Magazine*, July-August 2015 (pp.14-15):

([…] The purpose of this certification [1Z0-808 – *I.S*.] is to enable beginners to demonstrate their knowledge of fundamental Java concepts. The certification is designed for beginners in programming and/or those with a nonprogramming background who have basic mathematical, logical, and analytical problem-solving skills and who want to begin to learn the Java programming language; and for novice programmers and those programmers who prefer to start learning the Java programming language at an introductory level.

After successfully completing this certification, candidates can confidently utilize their knowledge on Java datatypes, operators, statements, arrays, lists, and exception-handling techniques.)

Naturally, these questions have small embedded traps that spring open if you rush through without considering exactly what the code is doing. […]

Got the picture? In my eyes, it basically says the OCAJSE8 exam – with all its "small" traps – is meant for toddlers if not toe-sucking infants.

Ready? then asks the column in a silver-haired mentor’s tone and produces this (Q3, 2nd part):

![](images/00011.jpeg)

Take a good look at the highlighted area; hopefully, you can spot the problem right away. If not, reread the quiz and its LOCs – unhurriedly and *subvocalizing*; this is how you should work through the code whenever you suspect it might be booby-trapped. What are the telltale signs that can arouse such a suspicion in you, how do you apply this technique in different scenarios – all this will be illustrated later; right now I am drawing your attention to something else entirely.

Alright, by now you should have it. Being `public`, **OnlineCart** class cannot possibly be declared in the file **Shop.java**, which makes all those options **a** through **d** simply irrelevant. In other words, while lying a bear trap for us toddlers, the quiz creator^([8](#part0008.html_id_20)) shot herself in the leg.

Now, I’m neither saying nor implying she is insufficiently qualified; there’s no doubt in my mind she is thoroughly professional: after all, her employer is Oracle Univ., and this credential alone is enough for me. But this example is as real as it gets, and by using it I mean to say that there are so many rules, nuances and subtleties to Java that even the most knowledgeable person might slip occasionally. Unfortunately for us, the exam itself is not that understanding and neither it is forgiving. Paraphrasing Forrest Gump, 1Z0-808 is like a box of chocolates: *ya never know what ya gonna get*. But twenty^([9](#part0008.html_id_18)) strikes out of seventy seven, and you are done for.

The exam is delivered from a remote server; it doesn’t live on the local machine. (I actually asked the exam administrator in my test center about this and she confirmed that it is so.) The machine was a peculiar looking flat-case desktop PC, deep-space black with no markings, it had a lockable CD/DVD-drive and no USB connectors on the front panel. The rear panel was well out of reach; I didn’t managed to get a look at it. To be honest, I didn’t even try…

The machine was connected to a small bluish box that looked like a regular Ethernet hub to me. The test room had one more computer, a twin to mine; it was also connected to the hub.

The most unusual feature of the whole setup was the monitor: it was square. Not the usual 4:3, 16:10 or 16:9 aspect ratio, no. It was 1:1. I’ve only seen such things twice in my entire life, and both times it was on the OCA exam.

Some test centers run their exams on Mac but in my case the OS was Windows-based; probably, some flavor of MS Windows Server because its flash screen had the Windows logo. According to my observations, the access to the exam is protected by a double-authentication protocol.

It seems that each exam is unique in the sense that the questions are most probably taken from a larger bank in a quasi-random order. The available answers (a.k.a. options) among which we have to choose the correct one(s) are shuffled each time the exam subset is being generated.

By ‘quasi-random’ I mean the following: it looks like^([10](#part0008.html_id_16)) that the exam is made up of three major sections:

• a Core section, which contains questions that appear always, on each exam, for every candidate regardless of the date or location; in other words, these questions aren’t randomly chosen from the question bank and will be present in every case;

• an Advanced section whose questions test our knowledge on a higher level of comprehension; close to Tough / Very Tough classification by Enthuware; these are the questions that are chosen randomly;

• a ‘Guinea Pig’ section, which is made up of the questions that Oracle tests on us. As you know after reading B&S, these questions are not graded. At all. Unfortunately, there is no way to tell if your current question is of the ungraded variety, otherwise it would mean that you can spit it in the face, kick its butt and then skip it altogether – and get away with it…

I think this general layout is more or less correct because I met core questions both times, the tough ones were different, and there were some average looking problems that I met only once. I have this feeling that the core questions make up 70 to 80% of the whole set. I can be wrong, though.

When looking up your score, you’ll see a list of the objectives that you have missed; after the second sitting my list contained a single item – "Create and overload constructors; including impact on default constructors" – and since my score was 98%, it appears that a single objective is worth 2%. On the other hand, the failed attempt (62%) gave me a list with 21 items; now you know why I think that the game is over after twenty strikes.

This math, however, does not mean much because we can answer wrongly for a completely different reason that has nothing to do with the objective that we are being tested for. ‘Spooked-by-a-shadow’ sort of thing.

An illustration. Do you remember the **TargetAudience** example? Admittedly, that was a shamelessly contrived piece of code, but still, how many objectives does it incorporate? Let’s count:

![](images/00012.jpeg)applying access modifiers such as `public` and `protected`;

![](images/00012.jpeg)applying non-access modifiers such as `final`;

![](images/00012.jpeg)applying `this` keyword;

![](images/00012.jpeg)initing^([11](#part0008.html_id_22)) of fields in constructors;

![](images/00012.jpeg)using method overloading;

![](images/00012.jpeg)working with methods defined in some of the core Java API classes.

At least six, and if we count in `package` and `import` declarations, general class design principles, rules for valid identifiers… Too many. While the code actually tests us on the proper use of constructors, it also throws a lot of dust into our eyes.

Apparently, designing test quizzes is an art in itself, and that’s precisely why Oracle has this ‘Guinea Pig’ section on the exam.

Let’s have another illustration. The same quiz block that appeared in Java Magazine (July-Aug 2015), contained one more somewhat ambiguously formulated question. Please look it up on your own; it concerns garbage collection, which is on the list of the exam objectives, too. Try to figure out what’s wrong with the wording, then refer to the **Quizzical Quiz Questions** in the *Letters to the Editor* column (p.7) in the Nov-Dec 2015 issue (External Resources).

Very well; so Oracle tests new questions on us toe suckers and guinea pigs all in one – and we don’t even get credit for this – but why do they need new questions in the first place? I suspect it’s a defensive mechanism against braindumps. No more on this subject you shall hear from me.

Now, back to the test rig. It may sound silly at first but I strongly advise you to take a long, hard look at the keyboard. See if it has a **Sleep** / **Hibernate** / **Power Off** key on it. Now imagine what happens when you accidentally hit it during the exam.

Worst case scenario: game over. Like, totally. The session with remote server has been abruptly terminated, and you’re out for good. Best case scenario: the connection can be restored, and you are able to continue right from the point of premature termination.

In fact, when I asked the exam admin about this, she replied that the best case scenario is exactly what would happen. But she wasn’t at all sure about the timer…

My keyboard did not have potentially suicidal keys on it. And neither did mouse^([12](#part0008.html_id_24)).

Good. Now, to the battlefield, that is, the screen. As I’ve told you, it was square, and most of the time the picture looked pretty much like this:

![](images/00013.jpeg)

**Legend:**

![](images/00014.jpeg) – Exam taker's name Oracle Testing ID

![](images/00015.jpeg) – Countdown timer, 02:30:00 → 0:00:00 ![](images/00012.jpeg) 'Flag for Review' checkbox

![](images/00016.jpeg) – Vertical scrollbar

![](images/00017.jpeg) – **Review** / **Previous** / **Next** buttons

![](images/00018.jpeg) – **Help** button

It wasn’t the usual, maximized window that takes up almost entire screen leaving accessible just the Taskbar; no, there was no Taskbar, not even a collapsed one – which means no Start button. As for the Ctrl+Alt+Del combo to access the Task Manager with its plethora of interesting options, I think it would have worked but I didn’t try it. Neither did I hit Win+R or other hot-key combinations to see if it would be theoretically possible to gain access to the command line, PowerShell, ports, and so on. Most probably, would not have worked; too obvious.

I also think they have disabled the Clipboard; same goes for the PrintScreen key (at least that’s how I would have gone about it if someone asked me to harden the exam environment against casual attacks.) Apart from taking the buffer out of the picture, they apparently took care of the selection event handler because the displayed text itself is not selectable.

Pearson Vue suggests that in order to familiarize themselves with the look and feel of the exam software, candidates should visit the following link: [http://www.pearsonvue.com/demo/](http://www.pearsonvue.com/demo/). To be honest, I don’t think it is terribly important in our case because the 1Z0-808 GUI is quite simple and straightforward. It’s up to you.

Do watch, however, ‘What to expect in a Pearson VUE test center’ video; it is close to what I have observed ([https://home.pearsonvue.com/test-taker/security.aspx](https://home.pearsonvue.com/test-taker/security.aspx)). One comment, though: they are checking now our watches. When I asked the administrator if it is because the modern wearable gizmos have built-in cameras and whatnots, she just smiled sweetly and said nothing. Draw your own conclusions.

Before taking the exam, you are supposed to sign some papers including the NDA and Oracle Certification Terms & Conditions; you’ll see this legal stuff again, this time right on the screen. As soon as you click ‘I accept’, the clock starts ticking.

Now, pay close attention to what I’m saying: **this trick**^([13](#part0008.html_id_26)) **alone can save you up to TEN minutes**… and oh boy, if you only knew how precious becomes time during the exam… but you’ll need to be prepared to benefit from it fully.

You see, there are TWO clocks on the exam. As I’ve just said, the first one commences its countdown when you click ‘I accept’. After that you’ll have 10 minutes to calm down, get a grip of yourself, concentrate, switch to full combat mode and/or read the Instructions (like clicking Help brings up the Help screen, clicking Next forwards to the next question while clicking Previous… I think, you got the picture.) So, you can skim all this self-explanatory stuff and then do whatever takes your fancy during those 10 minutes – which should be writing down some really important things that will help you crack the questions.

Now, what are they, these ‘really important things’? Do you remember the following little passage from B&S (page [363)?](#part0022_split_002.html_page_363)

If there’s a particular facet of the Java language that you have difficulty remembering, try memorizing it before the exam and write it down as soon as the exam starts.[…] For example, you may have trouble remembering the list of acceptable data types in `switch` statements. If so, we recommend you memorize that information before the exam and write it down as soon as the exam starts for use in various questions.

This is it – with one correction: NOT as soon as the exam starts but *before* it. I repeat, you’ll have as much as 10 minutes to do it. But do remember: you are supposed to click Start within those 10 minutes – and only then the SECOND timer will begin its 2h30m countdown…

B&S mentions the data types for `switch`. IMO, there are two more items that you might be writing down before the actual exam: the table of modifiers and an extract from the operator precedence chart. Maybe even the list of the most ‘popular’ ChEs + RTEs plus five major cases when an NPE gets thrown. Again, it’s up to you. Anyway, we’ll talk about all these in Part 2, Exam Objectives, or *Pater Noster*.

Perhaps, the only really helpful bit of info in the Instructions is the fact that you can strike out wrong answers right on the screen. Now, B&S809 says that

You can right-click questions to cross out answers. This lets you mark answers as incorrect as you go so that you have less to think about as you read. It also helps you remember what you’ve eliminated when you go back to questions.

True, true – but again, with one minor correction: to do so you’ll need to keep the Ctrl key pressed. So, Ctrl+right-clicking will eliminate a particular choice. Remember me mentioning a **Sleep** / **Hibernate** / **Power Off** button? Now you know you’ll may need to use the keyboard after all, so watch out.

Another time-saving tip: to cross out incorrect answers do NOT click on the O or ![](images/00012.jpeg) symbols in the list of the available options, it won’t work, you’ll be just wasting precious seconds; click instead right on the words / code. This particular option will immediately gray out and become stricken-through. The state is persistent, so when reviewing your answers, you’ll see those grayed out lines of text/code as you have left them.

When you finish answering the questions, a table will appear on the screen containing a list of all those questions that you have marked for Review plus, supposedly, those questions that you have forgotten to answer (or ticked off insufficient number of times, like two instead of three, etc.) I say ‘supposedly’, because I did not test this function. On the other hand, the Instructions did promise it. In any case, do whatever it takes but do not leave any question unanswered or answered incompletely. Make double sure of it, the penalty is just too harsh.

One more thing of equal importance. You will need to take all the precautions so as not let anything disrupt your concentration. Both B&S and B& S809 contain many really helpful, practical suggestions in this department, like dressing in layers, using earplugs and so on. All of it solid, all of it true. Here I’d like to share with you a few of my own observations:

![](images/00012.jpeg)If the test center permits bringing in drinks, do not use caffeinated beverages: they’ll most probably make you jumpy and even more thirsty (which did happen to me.) Bring in just plain water in a fully transparent plastic bottle with no markings (basically, just strip off the label).

![](images/00012.jpeg)Have on you a couple of glucose tablets in case of hypoglycemia because of all this nervousness, otherwise you risk becoming listless.

![](images/00012.jpeg)Watch out for uncapped markers. In all probability, you will be given a couple of felt tip pens (I’ve got one, blue, on the first sitting, and two, green and red, on the second.) Well, it turned out that because of all the excitement I forgot to cap my single pen – and its tip dried up. *Oops!* can write no more. So I dipped the pen into my coffee, and the trick worked. But I lost almost ten seconds – and got seriously distracted, it broke my concentration even more…

![](images/00012.jpeg)Count the steps between the office and the test room. Sounds mysterious but tell me, can you guess why I didn’t call the exam admin by waiving at the CCTV camera with my dried-up pen? Because I counted the time it took us to move from the office (where they checked my IDs and I signed all those legal papers and so on) to the test room: almost 50 seconds. Add here the time it would have taken the admin to understand the meaning of my wild grimaces, find a fresh pen and bring it in. Best case scenario – close to a couple of minutes, wouldn’t you say? While I solved my silly problem in ten seconds. It didn’t help pass the exam, though…

Alright, back to our little story. Well, during the first sitting I hadn’t realized that I could have benefited from extra 10 minutes, so after clicking ‘I accept’ I spent thirty or so seconds scrolling through Instructions and then, right before clicking ‘Start’, I just sighed heavily and murmured ‘Hit me’.

And so it did.

* * *

^([7](#part0008.html_id_13)) Throughout this book, B&S stands for the OCA 1Z0-808 Study Guide by Jeanne Boyarsky and Scott Selikoff. Its OCP sibling, the study guide for 1Z0-809, will be referred to as B&S809.

^([8](#part0008.html_id_19)) Sushma Jagannath of Oracle University.

^([9](#part0008.html_id_17)) Later I’ll show you how I arrived at this number. Then again, my logic can be totally bogus. You still have your own head.

^([10](#part0008.html_id_15)) The only way to ascertain this is to ask Oracle – and those guys ain’t talking.

^([11](#part0008.html_id_21)) Please refer to the Abbreviations and Acronyms section.

^([12](#part0008.html_id_23)) No, I didn’t check the mouse pad – because there was none! Otherwise… ☺

^([13](#part0008.html_id_25)) Yeah, it is a bit sneaky, I admit that much; on the other hand, they themselves say it in the open: we have prepared curved balls plus a minefield for you. So I think it’s just fitting; after all, in love and war, etc…

![](images/00019.jpeg)

Entire 1Z0-808 at a glance. What does it tell you?

![](images/00020.jpeg)

Immediately one thing became apparent – and I was utterly unprepared for it. This was of *immense* importance, but even more serious were consequences. Naturally, you may be of a completely different opinion; I am simply sharing my experience with you, that’s all.

Now, what is it, this hellishly important thing? Take a deep breath, then read slowly:

**THE CODE IS PRETTY-TYPED**

*All of it*. Every frigging LOC^([14](#part0010.html_id_30)). And what are the consequences of this momentous discovery?

Since the code is properly formatted, we can stop counting curly braces… Guys! *We can stop counting those pesky things and waste time on them*!

I dunno, maybe it’s just me but before the exam I took for granted that one of the possible traps could be a missing or misplaced brace. Besides, a string of them may get in the way obscuring the meaning, the clarity of code. "Get used to those horrible braces", warns the study guide by Kathy Sierra and Bert Bates referring, for example, to this curly brace parade on the same line: }}}}}. Or take B&S (p.33):

Identifying blocks needs to be second nature for the exam. The good news is that there are lots of code examples to practice on. You can look at any code example in this book on any topic and match up braces.

But now all the initialization blocks, all the method and constructor bodies and so on can be grasped at a glance. I suspect that the Oracle cert team simply got tired of all the complaints (in a couple of days after successfully passing the exam you’ll get an email asking you to participate in a survey) and finally gave in making all code pretty-typed.

I, however, couldn’t believe my eyes and continued, stubbornly and stupidly, match the braces just *wasting time*. A lot of it. On the second sitting it was altogether different: I simply took them all in at a glance, just making sure that all the method bodies, initers, etc. are properly enclosed. But no counting this time! That was a *major* time saver.

Alas, this is perhaps the only piece of good news about the code being pretty-typed on the exam because when you properly format your LOCs, with most of the closing braces on fresh lines, with indentations and all, the listing becomes *lo-ong*.

Combined with the fact that the font size is rather big (I think it is around 18 points), it means that many questions – not to mention answer options! – cannot fit on a single screen thus forcing you to scroll up and down incessantly and desperately. Damn! That threw me out of synch^([15](#part0010.html_id_28)) with the code, I was out of the groove – and got real nervous.

And what happens when you are nervous? Some people (me included) start second-guessing themselves. Doubt sneaks in and fogs your mind, you become tense, edgy… The vicious circle at its worst.

So I committed another hideous error: after checking off the option(s) I thought to be correct, I began to re-read the code looking for previously unnoticed traps. Each and every time.

*That* was most foolish of me. But wait, there was another deadly mistake: being full of doubts, I started marking up *too many* questions for Review…

Stop here for a sec and think what reviews are meant for. To check your answers in case you missed something, right? Like re-running calculations for nested loops, for example, just to see if you got everything correctly the first time. Or to take another look at the code for which you couldn’t decide between two options, something like that^([16](#part0010.html_id_32)). And when you mark almost every other question… What would *that* mean? It would mean that you’ll be practically taking the same exam once again. Still within the allotted time. Which is already running out because of multiple re-readings…

When I went through all the questions, I had only 15 minutes left, and the Review list contained some thirty items. And I didn’t even remember which were the most difficult ones; those that really needed my attention…

Another psychological trap I let myself in is that I was expecting nasty tricks in every single question. The thing is, many questions don’t even try to deceive you; they are straight as an arrow. Tell me, can you spot anything even remotely suspicious about this one (something to this tune *is* on the real exam):

**Given in the file** HiThere.java**:**

![](images/00021.jpeg)

**Which set of commands prints** Hi there! **in the console?**

![](images/00022.jpeg)

I didn’t see anything out of the ordinary, either. But spent on this one a few minutes instead of few seconds stubbornly resisting to trust my own eyes and instincts. All because I was wound up for devilishly clever trickery – where there was none…

We have already covered the make up of the exam questions according to their basic functions (the ‘Core’, ‘Advanced’ and ‘Guinea Pig’ types). Another possible classification is based on the inclination of the question to deceive you, to run the proverbial red herring across your path. Viewed from this angle, a question can be:

![](images/00012.jpeg)a straight arrow,

![](images/00012.jpeg)a curved ball to throw you off balance, and

![](images/00012.jpeg)a caltrop that is meant to cripple you.

The class **HiThere** is, obviously, of the first type. Let’s have a curved ball:

![](images/00023.jpeg)

Does the code compile? If it does, what is the result? If not, what is the reason for the comperr? And if the code throws an RTE, what is the reason for that?

The answer is this: the code does compile, both line 1 and line 2 print 42null each, and line3 prints 42 then throws an NPE because we attempt to unbox an **Integer** by implicitly calling **Integer.intValue()** on a `null` object.

Please don’t be alarmed; in all probability, you will not get such a question on the exam: it is more of the OCP realm. But there are at least three questions in our OCA 1Z0-808 that relate to the behavior of `null`, which includes several scenarios – and this is your curved ball: you’ll be needing to keep track of a number of things at the same time. We’ll cover these scenarios when discussing NPE.

How about meeting a simple yet nasty caltrop? Here you go:

**Given:**

![](images/00024.jpeg)

**What is the result?**

A.The code prints 1

B.The code prints 0

C.Compilation fails

D.The code throws an exception at run time

The correct answer is C: compilation fails.

The exam knows that we got used to see **insert()** rather often – and catches us off guard^([17](#part0010.html_id_34)).

And now I am going to confide to you THE mistake I made. The real one. All-embracing. The mother of all mistakes. Ready?

I didn’t read the questions. Hah! how about that? Bet you didn’t see it coming. Me neither :(

But fact is a fact is a fact. I did not read the textual part properly, that is, carefully. Was too anxious to get to the ‘meat’, the code itself. On my way home from the exam I was, naturally, thinking about the questions while writing them down from memory – and suddenly saw that a lot of times I tried to mark as correct the lines that would compile while the question must have been asking for the lines that wouldn’t, and vice versa. "Ah, so that’s why I couldn’t get the right number of options so many times! The question asked for two but I found three… And since the GUI wouldn’t allow me to checkmark so many, I relied on my blind luck and did it for only two. Both incorrect ones…"

Line from "The Rainmaker". "*You must be stupid, stupid, stupid!*"…

After failing the first sitting, after spending weeks recalling and reconstructing the exam questions, analyzing my own behavior and realizing what I have done, a set of most simple rules formed in my mind:

![](images/00012.jpeg)Don’t jump to the code. Read – the question – first. *Force yourself to read it*.

![](images/00012.jpeg)Give the problem your best shot at the very first pass.

![](images/00012.jpeg)Do it unhurriedly and never let yourself re-read what you have already read carefully.

![](images/00012.jpeg)Take the code at its face value. Not every snippet is meant to deceive you.

![](images/00012.jpeg)No cherry picking; do the questions as they come in.

![](images/00012.jpeg)Treat your Review marks as gold.

![](images/00012.jpeg)Trust your gut feelings.

![](images/00012.jpeg)Resist the temptation to redo calculations right away, leave it for the Review.

In hindsight, it all became so painfully apparent: I did not clearly think my approach through *beforehand*. Despite the fact that it is so uncomplicated… Take, for example, the ‘Review marks’ rule. If certain questions are too tough for you, if you are barely sure of what the code is doing, marking the problems for Review won’t help much – especially when you mark too many of them: you simply won’t have time to do a decent job. On the other hand, when you go through the questions like an ice-breaker, without dwelling on them too much, when you completely unleash your instincts as a coder and let them work for you… then you will have tons of time left and, therefore, stand a good chance of catching mistakes and disarming previously unnoticed traps on the Review. Not to mention gathering context clues during the initial pass…

But enough of this fountain of words, let’s have hard facts. Here’s the timeline for my second sitting:

Initial pass – 77 questions – 40 minutes. Yes, I did say forty. Not 2h15m like before. ("Wow… I’m sorta flying through all this like a Greek god or something…")

1st Review – a dozen of marked up questions (half of them loops, nested or otherwise) – 18 minutes. ("Damn, they were right, after all. It *is* kiddies stuff…") Swiftly found and corrected two silly mistakes.

1st *complete* Review – all 77 questions – 35 minutes. ("Day-dreaming on a golden cloud…") After recalling a puzzle in the Enthuware, changed one of the answers.

2nd complete Review – ditto – 22 minutes. ("Bo-oring…") No mistakes spotted this time.

Seeing that I still have a good half an hour left and no more interesting things to do, I decided to call it a day.

**My final conclusions after two sittings:**

All things considered, I must say that the most important, overarching rule that leads to success is also the simplest and most logical one:

Read the question first, then options and then code *carefully*. Subvocalize, even.

For example, take a look at this:

![](images/00025.jpeg)

Monospaced fonts are notoriously hard on eyes, particularly when the font size is unusually large – as it is on the actual exam. It is surprisingly easy to overlook a missing comma in the above LOC *especially* when you’re tired after, say, fifty or so questions and time is already pressing because:

a)you have, most probably, marked up a good dozen of questions for Review (which means you’ll need more time for them), and

b)there may be some frustratingly time-consuming loop(s) ahead…

Another important guideline: if you see more correct answers than the question asks for, and you still can’t find what is wrong with the options you’re ready to tick off, review the most ‘obvious’ choice extra carefully: it just may contain a trap.

Never assume that the exam creators made a mistake.^([18](#part0010.html_id_38))

I also noticed this: **weird looking, overly complex code**^([19](#part0010.html_id_36)) **is most likely to be booby-trapped** on a fairly *simple concept* such as (listed in the order of prevalence):

–out-of-scope vars;

–invalid syntax;

–unreachable stats.

* * *

^([14](#part0010.html_id_29)) This, however, I fully realized only near the end of the exam.

^([15](#part0010.html_id_27)) To tell the truth, I’m fairly surprised that none of the software-based mock up exams that I’m familiar with (such as Kaplan’s, Enthuware, etc.) simulate this particular feature. After all, it is harder to crack problems when you can’t see *entire* code and *all* available options…

^([16](#part0010.html_id_31)) B&S mentions some other techniques that you can use during Review like applying context clues from other questions, etc.

^([17](#part0010.html_id_33)) **insert(**int offset, String str**)** belongs to the class **StringBuilder** rather than **String**.

^([18](#part0010.html_id_37)) Unbelievable as it may sound, they do have a typo in one of their questions (which has to do with the class **LocalDate**): it lists a misspelled `DateParseExcpetion` as one of the options. I met this typo both times…

^([19](#part0010.html_id_35)) Particularly involving loops or post-decrement/post-increment notation.

![](images/00026.jpeg)

Alright, so far we’ve been talking about tactics and now it’s time to lay out the winning strategy against 1Z0-808.
Nothing can be simpler:

![](images/00012.jpeg)follow up on what you’re learning by coding as much as you can, and

![](images/00012.jpeg)solve as many practice question as possible.

From this point on our discussion is going to be fairly technical; we’re leaving behind all this psychological stuff – but I hope that you do see now just how important it is. This being said, let us move closer to the drawing board, so to speak.

You probably remember from *Preface* that using an IDE is not advisable (for at least the first few weeks.) Running programs from the command line, however, requires a lot of typing thus tempting you to abandon the whole idea and switch back to your favorite IDE. Resist the temptation. The point is, no one expects from you highly polished typing skills. It’s more about writing clean code without the help on the part of IntelliSence (in its concrete implementation, of course, such as Eclipse, NetBeans, Android Studio and so on.)

This will pay off a hundredfold when you are dealing with the questions that rely on the interaction between and among the data types located in different packages. This approach – writing code in Notepad++^([21](#part0011.html_id_40)) and then running it from the CLI – truly helps master access modifiers and imports, not to mention learning to be on alert for your most typical mistakes.

In order to save time on typing commands in the console, I invite you to try out my solution of how to teach the machine to run a **.java** file by right-clicking it in the Windows Explorer.

The solution requires two steps: 1) hacking the Windows Registry, and 2) writing a launcher, which is even easier than it sounds.

**Step 1: Hacking Registry**

Add the following key to your Registry: **HKEY_CLASSES_ROOT\*\shell\Run with Java** and then specify its command (default value): **C:\JC\RWJ.bat %1**

The easiest way to do it is to create a plain ASCII file (let’s call it **RWJ.reg**) and fill it with the following code (also downloadable from External Resources):

![](images/00027.jpeg)

Double-clicking **RWJ.reg** will import the keys into the Registry.

**Step 2: Writing a Launcher**

In the **C:\JC**^([22](#part0011.html_id_44)) folder create a text file^([23](#part0011.html_id_42)) named **RWJ.bat** and fill it with the code from **Appendix B** (or jump to External Resourcesfor a download link.) Below is the same code but with line numbers in it because we’ll be needing them for the discussion that follows.

![](images/00028.jpeg)

![](images/00029.jpeg)

![](images/00030.jpeg)

![](images/00031.jpeg)

Now let’s run a test and see how the whole idea works:

1)Create the folder **C:\Try_Java** with three more subfolders in it:

**org
tempa
tempb**

2)In the subfolder **org** create one more subfolder named **xlator**; the final result should resemble this tree:

![](images/00032.jpeg)

3)Go to **C:\Try_Java\org\xlator** and create **HelloWorld.java** there with the help of Notepad++, etc. Use the ‘ANSI as UTF-8’ encoding. If you absolutely sure that your Java classes do not output Unicode characters, you can flip rems to comment out lines 39 and 41 instead of lines 40 and 42\. This will disable the forced encoding switch of the Java compiler. By default, the forced encoding is ON because lines 39 and 41 are uncommented:

![](images/00033.jpeg)

4)Fill **HelloWorld.java** with any valid Java code you want. Just make sure of two things:

–the file starts with valid `package` declaration;

–even if the class isn’t `public`, its name and the **.java** file’s name must be the same.

It is possible to dispense with the `package` declaration altogether and compile and then run the **.java** file right from inside the folder the source file lives in. This practice is not recommended, though, because, after all, we must learn how to work with several packages at once.

By default, the package declaration is `package org.xlator;` (which reflects one of my websites' URL); naturally, you can be using something else; simply search and replace all instances of `org` and `xlator` in **RWJ.bat** with whatever you need; right now, however, I suggest you use the following code just to test the launcher and see how it works on your machine:

![](images/00034.jpeg)

5)Right-click **HelloWorld.java** in the Windows Explorer to open the context menu and select ‘Run with Java’ option.

6)**RWJ.bat** will launch `javac` and then JVM so you are going to see something close to this:

![](images/00035.jpeg)

Basically, this is it. The rest of the discussion concerns simple details like what and how should be changed to accommodate your particular needs.

First of all, let’s strip the launcher down to the most basic code possible and take a look at its beating heart. Here it is:

![](images/00036.jpeg)

Yes, it’s that simple: first we pass our **.java** file to `javac` by invoking `javac %1` and then we pass the class name to JVM. This trick, however, works **only if** the class name is exactly the same as the filename without the extension – which is removed with the help of ~n switch.^([24](#part0011.html_id_48))

Let me repeat; this is important. The above requirement – the class name must be exactly the same as the filename without the extension – **has nothing to do with** the JLS rule on naming files that contain a `public` class. It is there because of the ~n switch, that’s all^([25](#part0011.html_id_46)).

Here’s an illustration. Rename **HelloWorld.java** to **Brass.java**, then change the class name to **Brass**; you can also make it package-`private` (leave the package declaration in place, though):

![](images/00037.jpeg)

Run **Brass.java** by right-clicking it. Works fine, right? Now change class name to **Glass** and run the file. *Oops!* "Error: could not find or load main class org.xlator.Brass". Rename the class **Glass** back to **Brass**, and it will work again.

Now let’s address the execution flow. Depending on whether the package declaration is present, the flow forks on line 100 by checking the `packaged` flag declared on line 29:

![](images/00038.jpeg)

We are going to leave out the `simple_process` section (which is reserved for **.java** files without the package declaration in them; naturally, in this case you’ll also need to flip the `packaged` flag) and concentrate instead our attention on the generalized case, which is represented by the `packaged_process` section.

Once the `packaged_process` section has been entered on line 138, the code on line 146 checks if the directory specified on line 30 for the `javac -d` switch exists:

![](images/00039.jpeg)

The `javac -d` switch defines where the compiler should place the compiled classes. In all probability, your machine doesn’t have the **C:\Garbage\classes** directory, so – after asking your permission, of course (lines 147 through 157) – this directory will be created for you by running lines 159 through 172:

![](images/00040.jpeg)

If you decide against creating **C:\Garbage\classes** directory, the execution terminates by falling through into the `exiting` section on line 174:

![](images/00041.jpeg)

The real job is done in the section `get_to_it`, which starts on line 184\. The batch file first prints out supplementary info like what arguments will be passed to JVM, what is the package name of the class that contains the entry point, and so on (lines 187 through 201):

![](images/00042.jpeg)

Then we enter (line 205) the package directory from where we invoke first the compiler (line 206) followed by passing the main class to JVM on line 207\. If the program runs successfully, we’ll be given a chance to retain the compiled classes in place, otherwise they will be deleted (lines 214 – 218). The `pause` statement on line 213 is indispensable as it allows us to see compiler messages, our program’s output, a stack trace, etc. If you want to keep the compiled classes, press **^C** at this point; if not, hit **Space**.

![](images/00043.jpeg)

Right now **RWJ.bat** lets us work with three different packages: our main class lives in `org.xlator`, two more packages are **tempa** and **tempb**. This packaged structure is reflected in the **C:\Try_Java** directory’s file structure.

Why *three* packages and not four or even more? It’s because study guides and question banks rarely use four; besides, it seems that the real exam never uses more than three (at least I met only three; yes, in both sittings.)

Other switches like `Xlint` or `Xdiags` you can look up on your own^([26](#part0011.html_id_50)), and as for flags, here is a brief description:

![](images/00044.jpeg)

Alright, let’s have another example, this time with three packages and command line arguments – and then we really should move on, to the essential and much more interesting things.

1)Create three **.java** files and fill them with the following pieces of code:

![](images/00045.jpeg)

![](images/00046.jpeg)

2)Make double sure that line 28 in **RWJ.bat** contains *at least* two command line args, e.g.:

![](images/00047.jpeg)

3)Run **MyClass.java** by right-clicking it and selecting ‘Run with Java’^([28](#part0011.html_id_52)):

![](images/00048.jpeg)

As we can see, **RWJ.bat** works and, apart from the practice test software and study guides mentioned in *Preface*, this is basically all you’ll ever need to get prepped for the 1Z0-808 exam.

**Final Remarks on Dilemma ‘2IDE | !2IDE’**

We will still use an IDE occasionally in order to, say, look into the source code for the core Java classes (refer, for example, to the discussion of [Problem 1.15](#part0015_split_001.html_page_59)).

What’s more, an IDE such as NetBeans may allow to run uncompilable code by clicking the "Run Anyway" button in the error notification dialog. Let’s take a brief look at this interesting feature. What follows is a snapshot of a most simple class in the NetBeans environment:

![](images/00049.jpeg)

As we can see, the code is clearly uncompilable (BTW, there *is* a question on the exam that will test you on the mandatory initing of `final` fields) and, therefore, won’t run from inside the CLI. After asking the IDE to run it anyway, we’ll see the code producing "Hi there!" in the console… Amazing. How is it ever possible?

Whenever Java code runs, it means there’s a **.class** file for it, so let’s decompile the bytecode^([29](#part0011.html_id_54)):

![](images/00050.jpeg)

There! NetBeans simply added a no-arg constructor with a `throw` clause in it. Naturally, this is not always possible; for example, as soon as we make the var **str** `static`, the trick stops working. To make it work again, we’ll have to explicitly define a no-arg ctor:

![](images/00051.jpeg)

Only after that the IDE will be able to insert the `throw` clause to make the code compilable. The decompiled class will look exactly as the previous case except for the variable **str**: it will be declared `final static` and not just `final`.

* * *

^([20](#part0011.html_page_25)) Most people nowadays associate this immortal phrase with John Wayne whose nickname was Duke. Our exam also has a question with a Duke in it. And just as the heroes John Wayne portrayed, the question is honest and straightforward, without any traps. ^([21](#part0011.html_id_39)) Or JEdit, etc.

^([22](#part0011.html_id_43)) Naturally, the folder’s name can be entirely different; just take good care of the command line in Registry.

^([23](#part0011.html_id_41)) Preferably, in the ‘ANSI as UTF-8’ encoding (a.k.a. ‘UTF-8 without BOM’) but, strictly speaking, it is not necessary unless you are planning to use charset encodings other than plain ANSI.

^([24](#part0011.html_id_47)) So if you don’t like **RWJ.bat** – maybe it’s too limited by your standards – now you can build your own launcher.

^([25](#part0011.html_id_45)) I am saying it just in case: the switch `~n` is passed to `cmd` rather than to `java`; it is called a ‘CMD variable edit’; you can read more on this fascinating stuff in *Windows XP Under the Hood: Hardcore Windows Scripting and Command Line Power* by Brian Knittel.

^([26](#part0011.html_id_49)) For example, here: [http://docs.oracle.com/javase/7/docs/technotes/tools/solaris/javac.html#nonstandard](http://docs.oracle.com/javase/7/docs/technotes/tools/solaris/javac.html#nonstandard)

^([27](#part0011.html_foot1)) Control Panel ▶ System ▶Advanced System Settings ▶ System Properties ▶ Advanced ▶ Environment Variables

^([28](#part0011.html_id_51)) At this point I’d recommend to hit **^C** and peek into the **C:\Garbage\classes** folder to see how the compiler places compiled classes. Besides, we’ll need a **.class** file for a decompilation exercise in a few minutes.

^([29](#part0011.html_id_53)) This is a very simple case so the Class File Reader by Lee Benfield ([http://www.benf.org/other/cfr/](http://www.benf.org/other/cfr/)) will suffice.

External Resources

The two issues of *Java Magazine* that were mentioned in the text + **RWJ.bat**, **RWJ.reg**, the lambda-related **Filter.java** and all practice questions to [Chapters II.1](#part0015_split_000.html_page_44) through [II.9](#part0023_split_000.html_page_370) can be downloaded here: [www.igor.host\nailing1z0-808\Nailing_1Z0-808_Resources.zip](http://www.igor.host\nailing1z0-808\Nailing_1Z0-808_Resources.zip).

You may want to visit [www.igor.host](http://www.igor.host) to take a look at the Errata list, write a comment, etc.

**PART II**

**Exam Objectives, or *Pater Noster***

![](images/00052.jpeg)

*We gonna be rich! Daddy says he’s got entire Java inheritance practically in his pocket!*

![](images/00053.jpeg)

This part is arguably the most important section of the book – and it is also the longest – as it deals with virtually every rule from the JLS and javadocs for the core Java classes^([30](#part0014.html_id_62)) you will be applying during the exam.

These rules cover practically all questions that belong to the Core section, and that’s why this part is called *Pater Noster*: you need to know it by heart. Yes, you do; at least the Core Rules. As for the Extra Rules, they concern more advanced subjects, which are less likely to appear on the actual 1Z0-808 yet provide more insight into the Exam Objectives.

The Rules are listed according to the official **Oracle 1Z0-808 Exam Topics**^([31](#part0014.html_id_60)) (nine categories of 42 topics in total.)

Apart from the Core Rules, you should memorize (and maybe even write down within the additional 10 minutes right before the actual exam) a couple of tables:

**Table 1 Java Access Modifiers (extract)**

![](images/00054.jpeg)

[Table 1](#part0014.html_id_313) does not list all the modifiers that are available in Java; it is limited to those that are within the scope of the official Oracle 1Z0-808 Exam Topics. A checkmark means that this particular data type or class/interface member^([32](#part0014.html_id_58)) accepts this particular modifier.

To memorize the table, we can use mnemonics, visual patterns or just good old logic. Since we spare no efforts in preparation, let’s have all of it^([33](#part0014.html_id_56)):

–take a closer look at the leftmost column and you’ll see that modifiers are listed *alphabetically^([34](#part0014.html_id_66))* within their groups (pa-pri-pro-pu & a-f-s) – and the groups are also given alphabetically (A followed by O);

–now examine the title row: as classes are the root of all evil in 1Z0-808, we start with them…

–… and continue with the behavior-defining interfaces…

–… which are followed – in the order of importance from the class design point of view – by constructors who have the final say in the state of objects…

–…then we have methods who just love to be overridden and overloaded…

–…and lastly, there is an assorted bunch of mischievous – although sometimes primitive – data members, a.k.a. variables;

–the right-hand part of the title row forms something close to ‘Cl_I_C (click) Me, Data’ (not to mention CIC for ‘kick’), which, of course, is *the* way to greet our fellow Java coders who happen to be Star Trek fans;

–when tabled as pictured, the crossmarks form three distinct areas:

![](images/00012.jpeg)a Lone Star on the right, which reminds us that – if the spaghetti westerns are to be believed – neither a sheriff in Texas nor a variable in Java can be abstract; they are always painfully real;

![](images/00012.jpeg)a square island of four crosses, the burial ground for those top-level classes and interfaces who foolishly believed they were private and even protected citizens. Basically, the whole upper part of the table says that we are free to use whatever access modifier we want EXCEPT for the classes or interfaces of the upper crust; how sad: despite all their importance they can afford neither complete privacy nor protection…

![](images/00012.jpeg)and a triangle (The Ramp of Doom? as for Biblical allusions, I leave them to you) of six crosses, which rests on the bottom line of the table; the easiest way to memorize it is probably by its visual pattern.

Then again, it’s only natural that a top-level class cannot be `static` as a static entity is something that belongs to a class^([35](#part0014.html_id_64)); for example, we access static members by appending the dot operator to their data type names… Following this line of reasoning, we arrive at the conclusion that inner classes and interfaces can be `static` – and indeed they can!

Interfaces cannot be `final` because this would strip them of their ultimate *raison d’être* for what good is an interface if no one can extend or implement it?

As for the constructors, they are rather sneaky in following both static and non-static semantics (on the one hand, we can’t call them on an instance, they are neither overridable nor inheritable, which resembles static methods, while on the other hand, their bodies can contain, for example, `this`, which implies a non-static concept…)

Since constructors aren’t inherited, there is no way to implement an abstract constructor.

A constructor is always invoked in respect to an object, and since a static member *must* be accessible even in the absence of any object of this particular data type, there can be no constructors without objects, hence no static constructors may exist.

Finally, no constructor can be `final` (no pun intended) because it "…is not inherited, so there is no need to declare it `final`" (JLS, §8.8.3).

One last thing – which, unfortunately, is not apparent from the table – concerns local variables: the only modifier that is allowed inside methods, constructors or initers is `final`. You *will* have a question on the exam that tests you on this particular subject.

–If you digest information better through code than words, here’s the same table:

![](images/00055.jpeg)

The pattern on the right is probably the easiest way to memorize and quickly write down the whole table for the exam.

The second table, which concerns the priority of operators, is harder by far to master; luckily for us, we’ll be needing only a part of it for the exam:

![](images/00056.jpeg)

**Table 2.1 Priority of Operators (full form)**

![](images/00057.jpeg)

Aside from the basic arithmetic rules (*/ *vs*. +–), the most important points to remember for the exam are these:

![](images/00012.jpeg)postfix / prefix increment / decrement operators are of the top priority;

![](images/00012.jpeg)all arithmetic ops including comparison come before equality testing;

![](images/00012.jpeg)assignment, including its compound forms, is of the lowest priority.

Now let’s have only the part that is really needed for the exam (I don’t remember meeting either `instanceof` or the comparison operators or XOR but who knows what your particular set of questions will contain…):

**Table 2.2 Priority of Operators (extract to memorize for the exam)**

![](images/00058.jpeg)

As for the data types that are acceptable by `switch`, or a list of the NPE-throwing scenarios mentioned in *Preface*, they will be covered in the chapters that follow. Naturally, it’s up to you to decide which concrete tables (if any) you are going to write down before the exam.

Now let’s briefly discuss certain assumptions that, according to Oracle University^([37](#part0014.html_id_68)), you’ll need to make in order to correctly interpret the context of a question:

**Assume the following:**

![](images/00012.jpeg)Missing package and import statements: If sample code does not include `package` or `import` statements, and the question does not explicitly refer to these missing statements, then assume that all sample code is in the same package, and import statements exist to support the code. ← *This is a typical situation; happens in most of the questions that use core Java classes defined outside of the **java.lang** package such as **java.io.IOException**, **java.util.List**, **java.util.function.Predicate** and so on*.

![](images/00012.jpeg)No file or directory path names for classes: If a question does not state the file names or directory locations of classes, then assume one of the following, whichever will enable the code to compile and run: ← *Also quite common*.

![](images/00059.jpeg)All classes are in one file;

![](images/00059.jpeg)Each class is contained in a separate file, and all files are in one directory.

![](images/00012.jpeg)Unintended line breaks: Sample code may have unintended line breaks. If you see a line of code that looks like it has wrapped, and this creates a situation where the wrapping is significant (for example, a quoted string literal has wrapped), assume that the wrapping is an extension of the same line, and the line does not contain a hard carriage return that would cause a compilation failure. ← *Didn’t meet this one. At all. Just as I’ve said, the entire code was pretty-typed*.

![](images/00012.jpeg)Code fragments: A code fragment is a small section of source code that is presented without its context. Assume that all necessary supporting code exists and that the environment fully supports the correct compilation and execution of the code shown and its omitted environment. ← *A good half of the questions contain such code fragments*.

![](images/00012.jpeg)Descriptive comments: Take descriptive comments, such as "setters and getters go here," at face value. Assume that correct code exists, compiles, and runs successfully to create the described effect.

← *Met it once, in the form "setter and getter methods go here"*.

**Word of caution:**

It can be very tempting to actively use web resources to prepare for the exam. This can also lead to a dismal failure for most of those resources aren’t subject to rigorous quality control. They are just like people: can’t trust ’em all, can we?

For example, you may have come across something like this: "For convenience, the Java compiler automatically imports three entire packages for each source file: (1) the package with no name, (2) the **java.lang** package, and (3) the current package (the package for the current file)."

What’s interesting, this phrase comes directly from an official Java SE tutorial – but is badly outdated. The current JLS8 ([Chapter](#part0021_split_000.html_page_270) 7, *Packages*, preamble) clearly states that

A package consists of a number of compilation units. A compilation unit automatically has access to all types declared in its package and also automatically imports all of the public types^([38](#part0014.html_id_304)) declared in the predefined package **java.lang**",

so now it’s *two* packages, not three.

Apparently, some sites for Java students just don’t bother with keeping their pages up to date… I would recommend not to rely on Web but use instead solid study guides and tools from reputable authors / vendors.

A few suggestions on how to work through the chapters that cover exam objectives:

–keep a written record of your errors;

–start and finish your day by going through this list of failures;

–use colors, invent mnemonic formulas, draw pictures on paper and in your mind (as you know, funny ones work the best) and so on; do whatever helps commit the rules to memory^([39](#part0014.html_id_70)); you’ll be amazed what results it brings in a very short time.

And on a final note:

* * *

**Do not worry much about ‘Extra’ stuff; concentrate instead on the ‘Core Rules’ and related problems because you *will* encounter something close to them during the actual test**.

* * *

* * *

^([30](#part0014.html_id_61)) Within the scope of OCAJP8 objectives, of course, since Java 1.8 contains 4240 classes in 217 packages, and we cannot be reasonalbly expected to master them all.

^([31](#part0014.html_id_59)) [http://education.oracle.com/pls/web_prod-plq-dad/db_pages.getpage?page_id=5001&get_params=p_exam_id:1Z0-808](http://education.oracle.com/pls/web_prod-plq-dad/db_pages.getpage?page_id=5001&get_params=p_exam_id:1Z0-808)

^([32](#part0014.html_id_57)) Incidentally, constructors are *not* class members (JLS, §8.2, *Class Members*).

^([33](#part0014.html_id_55)) The stranger the association, the better the mental hooks and anchors; some parallels might sound silly but this is the whole point… You may want to experiment with your own mnemonic formulas, the ones that work best for *you*.

^([34](#part0014.html_id_65)) Or lexicographically, if you want to split hairs.

^([35](#part0014.html_id_63)) Did you notice that the compiler sometimes calls an interface a class? Declare a public interface in a wrongly named file (like `public interface I{}` in the file **File.java**) and observe this error: "class I is public, should be declared in a file named I.java".

^([36](#part0014.html_foot2)) Determines how ops of the same precedence are grouped in the absence of parentheses. Consider, for example, `int a=3-2-1;` this might produce either 0 (if evaluated from left to right) or 2 (right to left). The answer is 0.

^([37](#part0014.html_id_67)) [http://education.oracle.com/pls/web_prod-plq-dad/db_pages.getpage?page_id=5001&get_params=p_exam_id:1Z0-808](http://education.oracle.com/pls/web_prod-plq-dad/db_pages.getpage?page_id=5001&get_params=p_exam_id:1Z0-808)

^([38](#part0014.html_id_303)) **java. lang** contains `public` types only so that’s why we usually hear a shorter phrase like ‘**java.lang** is the only package that is imported implicitly’. Although a tiny bit redundant, the JLS’s wording is a good reminder that "A top level type is accessible outside the package that declares it only if the type is declared `public`" (JLS, Ch.7).

^([39](#part0014.html_id_69)) You may want to read or watch something on stage magicians’ mnemonic technique; this stuff definitely works…

![](images/00060.jpeg)

**The 1Z0-808 objectives within this group:**

| [1.1](#part0015_split_000.html_c1.1) | Define the scope of variables |
| [1.2](#part0015_split_000.html_c1.2) | Define the structure of a Java class |
| [1.3](#part0015_split_000.html_c1.3) | Create executable Java applications with a main method; run a Java program from the command line, including console output |
| [1.4](#part0015_split_000.html_c1.4) | Import other Java packages to make them accessible in your code |
| [1.5](#part0015_split_000.html_c1.5) | Compare and contrast the features and components of Java such as: platform independence, object orientation, encapsulation, etc. |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

1.1Scope of variables:

![](images/00012.jpeg)Basically, scope refers to that portion of code where a variable is visible, in other words, can be accessed.

![](images/00012.jpeg)Variables can operate on different levels and, therefore, they can have multiple scopes:

–class-level variables,

–instance variables,

–local variables (including loop vars), and

–method arguments.

![](images/00012.jpeg)Local variables are most often defined within the body of a method/constructor and in sub-blocks.

![](images/00012.jpeg)The scope of a variable is limited by the nearest pair of matching curly braces, {}. For example, the scope of a local variable is less than the scope of a method if the variable was declared within a sub-block inside the method. This sub-block can be an `if` statement, a `switch` construct, a loop, a TCF construct, or just a group of assorted stats enclosed by a matching pair of braces.

![](images/00012.jpeg)Local variables are not visible (*read*: they cannot be accessed) outside the method or sub-block in which they’re defined.

![](images/00012.jpeg)Instance variables are defined and accessible within an object, which effectively means we need a valid object to work with them. Any instance method of the same class can access these instance variables.

![](images/00012.jpeg)Class-level variables, a.k.a. `static` variables, are shared by all of the instances of the class; what’s more, they can be accessed even if there are no objects of the class.

![](images/00012.jpeg)Method arguments are used by a method that accepts parameters. Their scope is confined to the method within which they’re defined.

![](images/00012.jpeg)A method argument and a local variable cannot share the same identifier, that is, name.

![](images/00012.jpeg)Same goes for class and instance variables: they can’t be defined using the same name.

![](images/00012.jpeg)On the other hand, local and class/instance vars may be defined using the same name. If a method defines a local var that shares the same name with an class/instance variable, the local var shadows the class/instance var (in other words, makes it invisible.)

![](images/00012.jpeg)Sometimes the variables’ scopes overlap with each other; the only way to be sure if a variable is accessible is to identify the block it belongs to (by looking at braces).

![](images/00012.jpeg)Loop variables are local to the loop within which they’re defined.

![](images/00012.jpeg)All variables go into scope as soon as they get declared.

![](images/00012.jpeg)Class variables remain in scope as long as the program is running.

![](images/00012.jpeg)Instance variables go out of scope when the object is garbage collected.

![](images/00012.jpeg)Local variables go out of scope when the block they are declared in ends.

Putting out these rules in code:

![](images/00062.jpeg)

Line 2 declares `static` variables, which exist on the class level^([40](#part0015_split_002.html_id_72)). These variables are visible inside all methods and class-level blocks. Being class members, these fields do not require explicit initialization; the `static int` **y** automatically receives the value of 0.

Lines 3–5 define a static initialization block, which deals with static members only. This block fires only once, at the moment when the class is loaded. Please note that the assignment statement on line 4 executes *outside* any method.

Line 6 declares non-static, that is, instance variables (a.k.a. *instance* or *object fields*), which are known to all methods and class-level blocks UNLESS they are shadowed by other variables that happen to have the same name (which is unwise at it leads to much confusion). Instance vars also do not require explicit initialization, and **b** on line 6 automatically receives the value of 0.

Next comes the instance initialization block (lines 7–9), which fires every time an object is being created (naturally, after the very first initialization of the var at the point of its declaration); as the result, line 8 assigns the value of 11 to **b**, which used to be 0 when freshly declared. Similarly to static initers, the stats inside an instance initer execute outside any method.

Line 10 declares a method argument, `int` **b**, which is a local variable known only inside its method. Please note that this local var **b** doesn’t clash with the instance var **b**; instead, it shadows the instance var **b**. Same goes for `int` **a** declared and assigned the value of the arg **b** on line 11; this particular var is also a ‘shadow-caster’ and known only inside its method.

Local variable `int` **c** exists only inside **run()**; unlike `static` and instance vars, local vars are not automatically inited thus requiring an explicit initing BEFORE they may be used. There is at least one question on the exam that arms a bear trap based on this concept.

The sub-block on lines 13–16 attempts to declare two more vars that share names with previously declared vars: `int` **c** and `int` **x**. Line 14, however, does not compile since the scope of `int` **c**, declared two LOCs before, overlaps with that of the second `int` **c**, and Java does not allow multiple declarations of the same var. As for `int` **x** on line 15, this var is known only to its method, so there’s no problem. `int` **x** from line 15 ceases to exist after line 16.

As we can see, the scope of a var is limited by a pair of braces. There is, however, an exception to this rule, namely, `for` loops: their local vars (a.k.a. *loop vars*) are defined *before* the opening brace (refer to line 17 or to this example of a `for-each` loop: `for(int i : intArray){}`).

Line 18 foolishly attempts to re-declare already known local var `int` **a** whose scope starts on line 11 and ends after line 23\. (Just a reminder: being shadowed, the instance var `int` **a** from line 6 is still out of the picture at this point.)

The local var `int` **e** from line 19 is visible only inside the `for` loop on lines 17–22\. The exam creators are truly in love with this trap so be warned. Both **d** and **e** cease to exist after line 22.

The fourth and final attempt to re-declare `int` **a**, which is used as a param for **run()**, is met with success on line 25 because we are inside a different method whose matching braces limit this var’s scope… *Whew*! Half a thousand words to describe twenty or so simple LOCs… All in all, shadowing should be used sparingly. Mildly put.

1.2Structure of Java class:

![](images/00012.jpeg)The structure and functions of Java class are defined in a source code file (**.java** file).

![](images/00012.jpeg)The compiler creates a single Java bytecode file (**.class** file) for each compiled class, even if it is nested. As for the **.class** files themselves, they are not on the 1Z0-808 exam.

![](images/00012.jpeg)A class can define multiple components, such as:

![](images/00063.jpeg)

![](images/00012.jpeg)A single **.java** file can define multiple classes and/or interfaces.

![](images/00012.jpeg)A `public` class can be defined only in a source code file with the same name.

![](images/00012.jpeg)The structure of the source code file can have direct impact on the compilability of a Java class (something that you will be tested for), so it is important to be able to recognize misplaced statements in a class:

![](images/00059.jpeg)Java classes are kept inside packages, which group together related classes and interfaces. The packages also provide access protection and namespace management.

![](images/00059.jpeg)The `import` stat is used to import `public` classes and interfaces from other packages.

![](images/00059.jpeg)EXTRA: If a needed `import` statement is missing, classes and interfaces should be referred to by their fully qualified names (in the form of *pack.[subpack.]type_name*).

![](images/00059.jpeg)Classes can be imported by class name or wildcard. Wildcards do not make the compiler look inside subpackages (which are mapped to the local file system as subfolders).

![](images/00059.jpeg)EXTRA: In the event of a conflict, class name imports take precedence over wildcards.

![](images/00059.jpeg)`package` and `import` statements are optional. If present, they apply to all the classes and interfaces defined in the same **.java** file.

![](images/00059.jpeg)Fields and methods are also optional but, unlike the `package` and `import` stats that must precede the class declaration, they may be placed in any order within the class;

![](images/00059.jpeg)If a class defines a `package` statement, it should be the first statement in the **.java** file. It is a comperr if the `package` stat appears inside or after the class declaration;

| **Corollary**: | If a class has a `package` statement, all the `import`s should follow it. |

![](images/00059.jpeg)A class can contain exactly one `package` statement;

![](images/00059.jpeg)A class can include multiple `import` statements;

![](images/00059.jpeg)The `import` statement uses simple names of classes and interfaces from within the class.

![](images/00059.jpeg)The `import` statement cannot be applied to multiple classes or interfaces with the same simple name;

![](images/00059.jpeg)Redundant imports are allowed.

![](images/00059.jpeg)EXTRA: The `import` statement requires the dot operator.

![](images/00012.jpeg)Comments are another component of a class: they are used to annotate Java code and can appear anywhere within the source code file.

![](images/00012.jpeg)EXTRA: Comments can contain any characters from the entire Unicode charset.

![](images/00012.jpeg)There are three types of comments:

![](images/00059.jpeg)a single-line comment // (a.k.a. ‘end-of-line comment’), which hides from the compiler anything that is present to the right-hand side of it;

![](images/00059.jpeg)a multiline comment /* */, and

![](images/00059.jpeg)EXTRA: a Javadoc comment /** */, which is not on the exam.

![](images/00012.jpeg)A comment can appear in multiple places, before or after a `package` statement, before, within, or after the class definition, and before, within, or after the bodies of methods, constructors, blocks, loops and so on.

![](images/00012.jpeg)A Java class may define zero or more members such as `static` fields, instance variables, methods, or constructors^([41](#part0015_split_002.html_id_74)) whose definitions can be placed in any order within the class.

| **Corollary**: | Since the declaration order does not matter, a method may use, for example, an instance variable even before it has been declared in the file. |

Putting out these rules in code:

![](images/00064.jpeg)

Lines 1 through 4 are self-explanatory as they make use of the multiline comment syntax.

Line 7 imports all the classes (including **String**, which is the data type for the string literal "Hello" and the objects to be contained within the **ArrayList** referred to by the var **list**) from the **java.lang** package – which is already visible to the compiler, thus making this `import` statement redundant; this doesn’t throw a comperr, though. Line 8 is invalid as the `package` statement must precede `import`s and may appear only once. Lines 10 and 11 can be replaced with a single statement: `import java. util.*;` as shown on the commented-out line 9.

Line 12 throws a comperr: "a type with the same simple name is already defined by a single-type-import of Date".

Line 15 is invalid because the source code file is named wrongly (it should have been **I2.java**). It follows that a single **.java** file cannot contain more than one `public` class or `public` interface.

Line 20 uses the variable **list**, which is declared later, on line 22, but there’s no comperr since the declaration order of the class or instance vars does not matter.

Line 22 specifies the fully qualified name of the interface **List** used as the reftype of the var **list**. We could also uncomment line 9, and there would be no conflict because fully qualified names take precedence over wildcards.

EXTRA: Perhaps, the only surprise is that line 20 prints **true** instead of the half-expected **Hello**; it’s because the class **ArrayList**’s **add()** method (inherited from the interface **List**, which, in its own turn, extends the interface **Collection**) returns a `boolean` (**true** if the collection changed as a result of the call). This stuff, however, is not on the exam; in fact, even the Exam Objective 9.4, *Declare and use an ArrayList of a given type*, doesn’t go to such depth… Would make a nice little trap, though.

1.3Create executable Java applications with a main method; run a Java program from the command line, including console output:

![](images/00012.jpeg)Before any Java class can be used by the JVM, it must be compiled into bytecode:

![](images/00065.jpeg)

![](images/00012.jpeg)Java classes can be either executable or non-executable. An executable Java class runs when its class name (together with optional parameters) is handed over to the JVM:

![](images/00066.jpeg)

![](images/00012.jpeg)To be executable, the Java class must define the **main()** method, a.k.a. ‘entry point’, at which the JVM begins program execution.

![](images/00012.jpeg)The most commonly used signature of the **main()** method is:

![](images/00067.jpeg)

![](images/00012.jpeg)EXTRA: also acceptable are the varargs: `public static void main(String... args)`

![](images/00012.jpeg)To make the class executable, its **main()** method must be both `public` and `static`.

![](images/00012.jpeg)A class can define multiple methods with the name **main()**, provided that their signatures do not match the signature of the **main()** method defined as the program’s entry point.

![](images/00012.jpeg)The ‘entry-point’ **main()** accepts an array of type **String** that will contain the parameters specified on the command line after the class name. In fact, the **main()** method uses copies of these parameters as its arguments^([42](#part0015_split_002.html_id_76)).

![](images/00012.jpeg)Arguments are referenced starting with **args[0]**. An attempt to access an argument that wasn’t passed in causes an RTE, namely, AIOOBE.

![](images/00012.jpeg)EXTRA: **String**[] **args** in `public static void main()` is never `null`. If the program is run without any command line arguments, **args** points to a **String** array of zero length.

1.4Import other Java packages to make them accessible in your code:

Many rules concerning importing Java packages have been already covered in Item 1.2, *Structure of Java class*, because these objectives are closely related. Now let’s take another look at these principles while paying attention to a number of important details:

![](images/00012.jpeg)Java code is commonly organized into packages, which resemble file system folders.

![](images/00012.jpeg)To reference public classes or interfaces contained in other packages, we can use:

–either an `import` statement, or

–the fully qualified name of the class/interface.

![](images/00012.jpeg)No `import` statement can be placed before a `package` declaration.

![](images/00012.jpeg)An `import` statement can end with either simple name of the class or a wildcard symbol, that is, asterisk *.

![](images/00012.jpeg)If an `import` statement ends with the asterisk, it means that the code wants to have access to all `public` data types in that particular package.

![](images/00012.jpeg)On the other hand, the wildcard symbol does not provide access to any of the subpackages that may exist inside that one.

![](images/00012.jpeg)The **java.lang**^([43](#part0015_split_002.html_id_80)) package is the only package the compiler imports automatically.

![](images/00012.jpeg)Packages can contain multiple subpackages depending on how programmers organize their classes and interfaces.

![](images/00012.jpeg)By default, classes and interfaces in different packages and subpackages aren’t visible to each other.

![](images/00012.jpeg)On the other hand, all classes and interfaces within the same package are visible to each other.

![](images/00012.jpeg)The package and subpackage names are chained together with the dot operator.

![](images/00012.jpeg)An `import` statement is nothing but a handy way to tell the compiler where to look for a specific `public` class or interface; it does not ‘import’ anything^([44](#part0015_split_002.html_id_78)) but makes our life easier by allowing to use simple names for the `public` classes and interfaces defined in other packages.

| **Corollary**: | Instead of using an `import` stat, we can always write the fully qualified name of the `public` class or interface right in our code – but it soon becomes tedious. |

![](images/00012.jpeg)EXTRA: It also follows that `import` statements can’t be used to access multiple classes or interfaces that share the same simple name but reside in different packages. This problem can be solved, for example, by using an `import` stat for one conflicting class and the fully qualified name for its competitor. Another approach is to re-think the entire architecture of your namespace.

![](images/00012.jpeg)An `import` stat allows to gain access to either a single `public` member of the package, or to all of them (by using the abovementioned wildcard symbol).

| ![](images/00012.jpeg) | **Known trap on the exam** | If a data type isn’t `public`, it cannot be imported: |

![](images/00068.jpeg)

![](images/00012.jpeg)Unlike the asterisk used to access file system subfolders, `import` stat’s wildcard symbol does not work in a similar fashion with subpackages. In other words, * does not import subpackages.

![](images/00012.jpeg)EXTRA: If the source code file does not contain a `package` declaration, the class / interface is considered to be a member of the so-called default package.

![](images/00012.jpeg)EXTRA: The default package’s members are accessible only to the classes or interfaces defined in the same directory that contains the default package.

![](images/00012.jpeg)EXTRA: A class belonging to a default package can’t be used in any named packaged class regardless of whether it is defined within the same directory, or not.

![](images/00012.jpeg)It is possible to import an individual public *static* member of a class or all of its public static members by using an `import static` declaration.

![](images/00012.jpeg)To import a `static` method, we must use its name only, that is, without parentheses.

![](images/00012.jpeg)If the code appears clean and the LOCs are numbered, be on guard for missing imports – especially when you see:

![](images/00059.jpeg)lists (**List** and **ArrayList**)

![](images/00059.jpeg)predicative lambdas

![](images/00059.jpeg)LDT-related LOCs

![](images/00059.jpeg)**Arrays** (e.g., **Arrays.asList()**)^([45](#part0015_split_002.html_id_84))

![](images/00059.jpeg)**Collections** (e.g., **Collections.sort()**)

1.5Compare and contrast the features and components of Java such as platform independence, object orientation, encapsulation, etc.:

![](images/00012.jpeg)Java is a computer programming language that is concurrent, class-based and object-oriented^([46](#part0015_split_002.html_id_82)). The advantages of object-oriented software development:

![](images/00059.jpeg)Modular development of code, which improves its robustness;

![](images/00059.jpeg)Reusability of code;

![](images/00059.jpeg)Code is more flexible and dynamic at run time;

![](images/00059.jpeg)Better maintainability of code.

![](images/00012.jpeg)The OOP-based development is supported by a number of built-in features, such as encapsulation, inheritance, polymorphism, and abstraction.

![](images/00012.jpeg)Encapsulation allows objects to hide their internal characteristics and implementation details. Each object can provide a number of methods, which are accessible to other objects thus permitting them to read and/or change its internal state.

![](images/00012.jpeg)Encapsulation is realized through the use of access modifiers.

![](images/00012.jpeg)Some of the advantages of encapsulation:

![](images/00059.jpeg)The internal state of every object can be protected;

![](images/00059.jpeg)Encapsulation improves usability and maintainability of code because the behavior of an object can be modified independently of other data types;

![](images/00059.jpeg)Encapsulation decreases coupling, that is, interaction between and among classes thus improving modularity of the design.

![](images/00012.jpeg)Polymorphism is the ability to realize behavior depending on the underlying data type. A polymorphic data type is the type whose methods can also be applied to variables of some other related type. In other words, we can use the same variable to refer to different types and thus a method call can perform different tasks depending on the type of the actual object.

![](images/00012.jpeg)Polymorphism makes the code more dynamic at run time and also improves its flexibility and reusability.

![](images/00012.jpeg)Inheritance provides an object with the ability to acquire the fields and methods of its parent class, also called superclass or base class. Inheritance further enhances reusability of code by adding new features to an existing data type without modifying it.

![](images/00012.jpeg)Java does not support multiple inheritance. Each class is permitted to extend only one class, but can implement multiple interfaces.

![](images/00012.jpeg)EXTRA: Abstraction allows to develop data types in terms of their own functionality instead of implementation details. Java provides support for abstract classes that expose interfaces to the outside world without including the actual implementation of all methods. Basically, abstraction aims to separate the implementation details of a class from its behavior.

![](images/00012.jpeg)EXTRA: Difference between abstraction and encapsulation:

![](images/00059.jpeg)Abstraction and encapsulation are complementary concepts: while abstraction deals with the behavior of an object, encapsulation concerns the implementation details of this behavior.

![](images/00059.jpeg)Encapsulation is usually achieved by hiding information about the internal state of an object and thus can be seen as a way to realize abstraction.

![](images/00012.jpeg)Java is platform independent, meaning that it allows to develop applications that can run, without having to be rewritten or recompiled, on any platform that has Java Runtime Environment.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 1.1Given:**

![](images/00070.jpeg)

**What is the result?**

A.input: 0123, output: 0123

B.input: 2013, output: 2013

C.input: 0123, output: 2013

D.Wrong argument!

E.None of the above because compilation fails

**Problem 1.2Given the contents of three files:**

![](images/00071.jpeg)

**Which statement is true?**

A.Only A.java compiles successfully.

B.Only B.java compiles successfully.

C.Only C.java fails compilation.

D.All three files fail compilation.

**Problem 1.3Given the code from the PinkFloyd_Wall_SideB_7.java file:**

![](images/00072.jpeg)

**Which set of commands prints** `Goodbye Cruel World`**?**

A.javac PinkFloyd_Wall_SideB_7
java PinkFloyd_Wall_SideB_7 Cruel World

B.javac PinkFloyd_Wall_SideB_7.java Cruel World
java PinkFloyd_Wall_SideB_7

C.javac PinkFloyd_Wall_SideB_7.java
java PinkFloyd_Wall_SideB_7 Cruel World

D.javac PinkFloyd_Wall_SideB_7.java
java PinkFloyd_Wall_SideB_7.class Cruel World

**Problem 1.4Given the code from the Eat2GetFit.java file:**

![](images/00073.jpeg)

**And given the following set of commands:**

javac Eat2GetFit.java

java Eat2GetFit 100 100 100

**What is the result?**

A.Stay below 10000 cals per night!

B.Compilation fails on line 1

C.Compilation fails on line 2

D.Compilation fails on line 3

E.Compilation fails on line 4

**Problem 1.5Given the file WhichOne.java:**

![](images/00074.jpeg)

**and commands:**

javac WhichOne.java

java WhichOne 1234

**What is the result?**

A.1234 is an Object!

B.1234 is a Number!

C.1234 is a String!

D.1234 is an int!

E.Compilation fails

F.An ArrayIndexOutOfBoundsException is thrown at run time

**Problem 1.6Given:**

![](images/00075.jpeg)

**And given the commands:**

javac OpenSesame.java

java OpenSesame My voice is my password

**What is the result?**

A.Access denied!

B.Access granted!

C.Compilation fails on line 1

D.Compilation fails on line 2

E.An ArrayIndexOutOfBoundsException is thrown at run time

**Problem 1.7Given the contents of four files:**

![](images/00076.jpeg)

**Which LOC(s), when inserted in AngryBoss.java, shall enable the code to compile?**

A.`import office.*.*;`

B.`import office.broomcloset.*;`

C.import office;
import office.broomcloset;

D.import office.BroomCloset;
import office.broomcloset.Broom;

E.import office.*;
import office.broomcloset.*;

**Problem 1.8Which three statements describe the object-oriented features of the Java language?**

A.Objects cannot be reused.

B.A subclass can inherit from a superclass.

C.Objects can share behavior with other objects.

D.A package must contain more than one class.

E.Object is the root class of all other objects.

F.A main method must be declared in every class.

**Problem 1.9Which of the following best describes encapsulation?**

A.Encapsulation ensures that certain fields and methods of an object can be made inaccessible to other objects.

B.Encapsulation ensures that classes can have abstract fields and methods.

C.Encapsulation ensures that data types can have inheritable methods.

D.Encapsulation ensures that data types can be designed in such a way so that if a method has an argument DataTypeOne dto, any subclass of DataTypeOne can be passed to that method.

**Problem 1.10Which one is true about Java byte code?**

A.It can run on any platform.

B.It can run on any platform provided the byte code was compiled for that platform.

C.It can run on any platform that has the JRE (Java Runtime Environment).

D.It can run on any platform that has javac.exe (that is, a Java compiler).

E.It can run on any platform provided this platform has both the JRE and javac.exe.

**Problem 1.11Given the contents of two Java source files:**

![](images/00077.jpeg)

**What three modifications, made independently to the class Hackathon, will enable the code to compile and run?**

A.Replace line 5 with new hackathon.hacker.Hacker().hack();

B.Replace line 5 with new hackathon.*.Hacker().hack();

C.Add import hackathon.hacker.*; before line 1

D.Add import hackathon.hacker.*; after line 1

E.Add import hackathon.hacker.Hacker; after line 1

**Problem 1.12Given:**

![](images/00078.jpeg)

**What is the result?**

A.17

B.18

C.19

D.Compilation fails

E.An exception is thrown at run time

**Problem 1.13Given:**

![](images/00079.jpeg)

**Which line causes a compilation error?**

A.line 1

B.line 2

C.line 3

D.line 4

**Problem 1.14Given:**

![](images/00080.jpeg)

**Which two items are fields?**

A.j

B.k

C.x

D.y

E.z

**Problem 1.15**

**Which two classes compile and can be run successfully using the command:**

![](images/00081.jpeg)

**Problem 1.16**

**Given the complete contents of the file** `Jupiter.java`**:**

![](images/00082.jpeg)

**And the commands:**

javac Jupiter.java

java Juno Jupiter Juno

**What is the result?**

A.Welcome Jupiter!

B.Welcome Juno!

C.Compilation fails because a source file can contain only one main() method

D.An ArrayIndexOutOfBoundsException is thrown

E.Run-time error is thrown because we run wrong class: it should’ve been Jupiter

**Problem 1.17Given:**

![](images/00083.jpeg)

**Which package is automatically imported by the Java compiler?**

A.java.lang

B.javax.swing

C.[javax.net](http://javax.net)

D.java.*

E.The package with no name

**Problem 1.18**

**Which three are benefits of encapsulation?**

A.Encapsulation allows to change the class implementation without changing the clients.

B.Encapsulation prevents leakage of confidential data out of the objects.

C.Encapsulation prevents code from causing exceptions.

D.Encapsulation enables the class implementation to protect its invariants.

E.Encapsulation allows classes to be combined into the same package.

F.Encapsulation enables multiple instances of the same class to be created safely.

**Problem 1.19Given:**

![](images/00084.jpeg)

**What is the result?**

A.3 2 3 1

B.3 2 3 0

C.3 1 3 1

D.3 1 3 0

**Problem 1.20Given:**

![](images/00085.jpeg)

**What is the result?**

A.kk = 0, kk = 2, kk = 0,

B.kk = 0, kk = 2, kk = 2,

C.kk = 0, kk = 2, kk = 4,

D.Compilation fails.

**Problem 1.21Which three statements are true about the structure of a Java class?**

A.Only one private constructor is allowed per class.

B.A class can have overloaded static methods.

C.A field and a method can share the same name.

D.A public class must have a main method.

E.No class can be declared without methods.

F.Fields do not need explicit initialization before use.

**Problem 1.22Given:**

![](images/00086.jpeg)

**What is the output?**

A.one

B.two

C.three

D.four

**Problem 1.23Given the contents of three files:**

![](images/00087.jpeg)

**Which snippet will allow the code to compile and run successfully?**

A.Add to class **Raspi**:

`import peripherals.*;`

`import microsd.microSD;`

B.Add to class **Raspi**:

`import peripherals.Peripherals;`

`import microsd.microSD.*;`

C.In class **Raspi**:

add `import peripherals.*;`

replace line r2 with `microSD.writeImage();`

D.In class **Raspi**:

add `import static microsd.microSD.writeImage;`

replace line r1 with `new peripherals.Peripherals();`

E.Add to class **Raspi**:

`import peripherals.Peripherals;`

`import static microsd.microSD.writeImage();`

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 1.1 – C**

**Given:**

![](images/00088.jpeg)

**What is the result?**

A.input: 0123, output: 0123

B.input: 2013, output: 2013

C.input: 0123, output: 2013

D.Wrong argument!

E.None of the above because compilation fails

The var `input` declared on line p2 inside the `try` block shadows the instance field of the same name declared on line p1\. The scope of this local var, however, is limited to the `try` block only so that’s why the **println()** method on the line p3 uses the instance field’s value. In addition, since **parseMe()** is invoked with a valid parameter, the `catch` block has no chance to run.

**Problem 1.2 – A**

**Given the contents of three files:**

![](images/00089.jpeg)

**What is the result?**

A.Only A.java compiles successfully.

B.Only B.java compiles successfully.

C.Only C.java fails compilation.

D.All three files fail compilation.

The file **A.java** has two redundant `import` statements on lines X1 and X2 but this does not produce a compile-time error because redundant imports are allowed.

The class **B** says that the vocal var **p** declared on line X3 is `private` thus leading to a comperr because the only modifier allowed inside methods is `final`.

The file **C.java** has its sequence of `package` and `import` statements wrong: `import` may never precede `package`.

**Problem 1.3 – C**

**Given the code from the PinkFloyd_Wall_SideB_7.java file:**

![](images/00090.jpeg)

**Which set of commands prints** `Goodbye Cruel World`**?**

A.javac PinkFloyd_Wall_SideB_7
java PinkFloyd_Wall_SideB_7 Cruel World

B.javac PinkFloyd_Wall_SideB_7.java Cruel World
java PinkFloyd_Wall_SideB_7

C.javac PinkFloyd_Wall_SideB_7.java
java PinkFloyd_Wall_SideB_7 Cruel World

D.javac PinkFloyd_Wall_SideB_7.java
java PinkFloyd_Wall_SideB_7.class Cruel World

This is an example of a ‘straight arrow’: the question is both simple and harmless. You will meet a good dozen of them on the actual exam so don’t waste time desperately searching for traps in each and every case.

Option A omits **.java** file extension in the call to **javac.exe**; option B displaces command-line arguments for **java.exe**, and D specifies **.class** file instead of the class name.

**Problem 1.4 – E**

**Given the code from the Eat2GetFit.java file:**

![](images/00091.jpeg)

![](images/00092.jpeg)

**And given the following set of commands:**

javac Eat2GetFit.java

java Eat2GetFit 100 100 100

**What is the result?**

A.Stay below 10000 cals per night!

B.Compilation fails on line 1

C.Compilation fails on line 2

D.Compilation fails on line 3

E.Compilation fails on line 4

It’s OK if an `abstract` class has no `abstract` methods so line 1 compiles, and although `abstract` classes by definition cannot be instantiated, the code never attempts to create an object of type **Eat2GetFit** → hence the program is potentially executable.

The integer literal 0 on line 2 has an **f** appended which makes it a `float`. A `float` is perfectly assignable to a `double` so there’s no comperr.

The expression `!(args.length < 3)` on line 3 produces a `boolean`, hence line 3 compiles, too.

The real problem is on line 4, which attempts to use the vars `weight`, `height` and `age`. Since these vars are local, they must be inited before being used yet their initing is not guaranteed (specifically, if the `args` array has two slots in it or less). The compiler realizes it and throws an error.

**Problem 1.5 – C**

**Given the file WhichOne.java:**

![](images/00093.jpeg)

**and commands:**

javac WhichOne.java

java WhichOne 1234

**What is the result?**

A.1234 is an Object!

B.1234 is a Number!

C.1234 is a String!

D.1234 is an int!

E.Compilation fails

F.An ArrayIndexOutOfBoundsException is thrown at run time

The code does compile.

The class **WhichOne** declares four overloaded **main()** methods but only one of them has a valid entry point’s signature (which uses an array of type **String** as its argument).

Although the JVM is passed just a single arg, the code uses the very first slot in the array so there’s no run-time error.

**Problem 1.6 – B**

**Given:**

![](images/00094.jpeg)

**And given the commands:**

javac OpenSesame.java

java OpenSesame My voice is my password

**What is the result?**

A.Access denied!

B.Access granted!

C.Compilation fails on line 1

D.Compilation fails on line 2

E.An ArrayIndexOutOfBoundsException is thrown at run time

The code does compile.

Line 1 is valid because a vararg is acceptable as the **main()** method’s argument. In fact, the compiler translates a vararg into an array of type **String**.

Line 2 also has a valid ternop syntax thus producing no compile-time error.

When the program is run, the **args** array fills with five **String** values and the code uses the last one of them, so there’s no AIOOBE.

The ternary op on line 2 is straightforward despite its seemingly inverted logic: as **args**[4]’s value matches the string "password", the ternary operator returns `false` and the `else`-branch is therefore executed.

**Problem 1.7 – E**

**Given the contents of four files:**

![](images/00095.jpeg)

**Which LOC(s), when inserted in AngryBoss.java, shall enable the code to compile?**

`A.``import office.*.*;`

`B.``import office.broomcloset.*;`

`C.``import office;`
`import office.broomcloset;`

`D.``import office.BroomCloset;`
`import office.broomcloset.Broom`;

`E.``import office.*;`
`import office.broomcloset.*;`

Another typical example of what you should expect on the actual exam: a couple of screens filled with garbage through which you’ll have to waddle by scrolling up and down. While rather time consuming and therefore frustrating, the problem itself is quite simple and contains no serious traps.

Options A and C are syntactically invalid as only one asterisk is both *required* and *allowed* inside a generalized `import` stat.

Option B imports source files from the package **office.broomcloset** only thus leaving the classes **Janitor** and **BroomCloset** inaccessible since they live inside the package **office** rather than **office.broomcloset**.

And finally, although option D uses fully qualified names for the classes, it forgot to summon **Janitor**. Replacing **office.BroomCloset** with **office.*** fixes this error.

**Problem 1.8 – BCE**

**Which three statements describe the object-oriented features of the Java language?**

A.Objects cannot be reused.

B.A subclass inherits non-private fields and methods from a superclass.

C.Objects can share their behavior with other objects.

D.A package should contain at least two classes.

E.Object is the root class for every object in Java.

F.Every class must declare its own main method.

Option A is incorrect since reusability is one of the cornerstones of the object-oriented design.

Packages does not prescribe the number of classes they can contain, so the option D is not correct, either. And finally, classes can be totally void of members, which makes option F incorrect.

**Problem 1.9 – A**

**Which of the following best describes encapsulation?**

A.Encapsulation ensures that certain fields and methods of an object can be made inaccessible to other objects.

B.Encapsulation ensures that classes can have abstract fields and methods.

C.Encapsulation ensures that data types can have inheritable methods.

D.Encapsulation ensures that data types can be designed in such a way so that if a method accepts an argument of type DataTypeOne, any subclass of DataTypeOne can be passed to that method.

The actual exam has at least two questions related to encapsulation; one is completely textual like this Problem 1.9; the other one is code-based and contains a simple trap (or even two, depending on how you look at it). We’ll meet and disarm those nasties soon enough, in Exam Objective 6.5, *Apply encapsulation principles to a class*, which belongs to Group 6, *Working with Methods and Encapsulation*.

As for the solution to the current Problem, options B, C and D do not concern encapsulation.

**Problem 1.10 – C**

**Which one is true about Java byte code?**

A.It can run on any platform.

B.It can run on any platform provided the byte code was compiled for that platform.

C.It can run on any platform that has the JRE (Java Runtime Environment).

D.It can run on any platform that has javac.exe (that is, a Java compiler).

E.It can run on any platform provided this platform has both the JRE and javac.exe.

I met two versions of this question on the exam; both didn’t mention either byte code or **javac.exe** specifically but did talk about Java compiler and Java programs in general. Expect no traps in this one.

Option A is way too general, B doesn’t understand the meaning of byte code, option D specifies unrelated requirement, and E builds on D.

**Problem 1.11 – ADE**

**Given the contents of two Java source files:**

![](images/00096.jpeg)

**What three modifications, made independently to the class Hackathon, will enable the code to compile and run?**

A.Replace line 5 with `new hackathon.hacker.Hacker().hack();`

B.Replace line 5 with `new hackathon.*.Hacker().hack();`

C.Add `import hackathon.hacker.*;` before line 1

D.Add `import hackathon.hacker.*;` after line 1

E.Add `import hackathon.hacker.Hacker;` after line 1

This is an example of a question that uses certain assumptions; for example, both classes are `public` but we are not provided with filenames → hence we get to assume that the filenames are immaterial in this case.

Option A correctly makes the class **Hacker** accessible to the class **Hackathon** by using the fully qualified name during the creation of the object on which we then call the method **hack()**.

Option B has an asterisk before the class name and therefore violates syntactic rules.

Option C wants to place an `import` stat before `package`, which is not allowed.

As for option D, it imports entire package `hackathon` while option E imports a single class only, the very one that we actually need.

**Problem 1.12 – B**

**Given:**

![](images/00097.jpeg)

**What is the result?**

A.17

B.18

C.19

D.Compilation fails

E.An exception is thrown at run time

Remember me saying that we should take the questions at their face value? This one can be – and should be – cracked in two seconds: the printing stat is well within the scope of **a**, **m()** is `static` and accepts an `int` → done! As for those two inexplicable values of 17 and 19, they were put there simply to confuse you. Expect the same treatment from the 1Z0-808 creators.

**Problem 1.13 – B**

**Given:**

![](images/00098.jpeg)

**Which line causes a compilation error?**

A.line 1

B.line 2

C.line 3

D.line 4

Line 1 compiles because **doStuff()** is `static` and its invocation meets the method’s signature. Line 3 is valid since the class declares its `static` field **a** even though the declaration comes after the body of **doStuff()**. This does not throw a comperr because the order of class member declaration does not matter. Line 4 compiles for exactly same reason: the printing stat is within the var **a**’s scope, which makes **a** accessible.

Line 2, however, attempts to assign the not-yet-existing local var **x2**’s value to **x1**. It’s only class members^([47](#part0015_split_002.html_id_86)) that can be declared in any order; local vars do not work this way.

**Problem 1.14 – AB**

**Given:**

![](images/00099.jpeg)

![](images/00100.jpeg)

**Which two items are fields?**

A.j

B.k

C.x

D.y

E.z

Since fields are not local variables, options CDE are incorrect (**x** and **y** are regular locals, and **z** is the so-called loop var, also very much local).

**Problem 1.15 – CD**

**Which two classes compile and can be run successfully using the command:**

![](images/00101.jpeg)

All classes are compilable except the one in option A: its printing stat wants to access a slot in an array while the method’s signature doesn’t provide for array-type args. What’s more, even if the printing stat were using just the refvar rather than a slot (like option C does), the method’s signature wouldn’t make it a valid entry point: it still needs a **String** array.

Option B throws an AIOOBE at run time because the command line specifies only two arguments while the printing stat wants to access the third slot. Option D is a textbook case of the classic HelloWorld-type program, and as for option C, it produces a rather unpalatable output ([Ljava.lang.String;@2a139a55 on my machine).

This is due to the fact that arrays do not provide their own implementation of the **toString()** method, which they inherit from the root class **Object**.

To see what’s going on and what **toString()** has to do with all this, we need to dig into the source code for the core Java class **PrintStream** that lives in the **java.io** package (which is zipped and placed into the file **rt.jar** inside your JDK 1.8 dir). The easiest way to look at it is to open an IDE such as NetBeans, place the cursor on **println()** and press Ctrl-B (or use Navigate | Go to Declaration in the context menu).

The IDE should teleport you to this point inside the file **PrintStream.java**:

![](images/00102.jpeg)

Now, as we can see, the method **println()** invokes the class **String**’s `static` **valueOf()** method to make the representation of the object **x** that was passed to it; let’s jump to the point of **valueOf()** declaration in the file **String.java**:

![](images/00103.jpeg)

So, if the object is `null`, the method returns a **String** var whose value is literally "null", and if not… To see what happens in this non-trivial case, we boldly go to the declaration of **toString()** in the class **Object**:

![](images/00104.jpeg)

Now it’s clear how we got the sequence of symbols 2a139a55: it’s the hashcode of our object, namely array **args** of type **String**. As for **java.lang.String**, it’s self-explanatory, and the prepended [L means a one-dim array of reference types while [[F would have meant a two-dim array of `float`s and so on – but this stuff isn’t on the exam.

What follows, however, *IS* on the exam (you’ll have at least one Core question about it). Borrowing directly from the javadoc^([48](#part0015_split_002.html_id_88)) on **Object**:

In general, the toString method returns a string that "textually represents" this object. The result should be a concise but informative representation that is easy for a person to read. It is recommended that all subclasses override this method.

The key point to remember here is that you have to be on high alert whenever you see a user-defined data type used as a param for **println()** or **print()** invocation: unless the class defines its own implementation of the **toString()** method, the output will look like garbage.

And one more thing which you *will* be tested on. It’s about one of the NPE-throwing scenarios; a perfect trap for us exam takers. Go back a little and take another look at the body of the **valueOf()** method defined in **String**:

![](images/00105.jpeg)

Retreat again and then jump to the declaration of **print()** inside the **PrintStream** class:

![](images/00106.jpeg)

Now we see why it is perfectly safe to invoke printing stats such as **println()** or **print()** on a `null` object: these methods never throw a **NullPointerException** because of the built-in protection mechanism. And yes, I did meet a question on the exam asking me exactly this…

**Problem 1.16 – B**

**Given the complete contents of the file Jupiter.java:**

![](images/00107.jpeg)

**And the commands:**

javac Jupiter.java

java Juno Jupiter Juno

**What is the result?**

A.Welcome Jupiter!

B.Welcome Juno!

C.Compilation fails because a source file can contain only one main() method

D.An ArrayIndexOutOfBoundsException is thrown

E.Run-time error is thrown because we run wrong class: it should’ve been Jupiter

This problem does not test your knowledge of the **main**() method’s signature: it asks if you know that however many data types a source file contains, the compiler always places them into separate **.class** files → meaning that you can run any class you want as long as it has the executable **main()** method.

So this is exactly what happens here: **javac.exe** compiles both classes into separate files (**Jupiter.class** and **Juno.class**), places them into the source dir, then we nonchalantly pass the class **Juno** to the JVM – and it runs it for us because both classes have their own executable **main()** methods. **Juno**’s **main()** calls the **Jupiter**’s **main()** passing to it a valid array of the command line args. All in all, nothing surprising.

Now, let’s look at the whole setup from a different angle; please note the wording of the problem: "Given the complete contents of the file **Jupiter.java**". Indeed, the class declaration starts right on the first line; there’s no package declaration. What would’ve happened if we added a package declaration without changing anything else? The answer is, the classes would have compiled just fine but the JVM would’ve thrown a run-time error: "Could not find or load main class Juno". Interesting, wouldn’t you say? The required **Juno.class** file apparently exists but the virtual machine can’t see it…

This happens because the compiler automatically ‘expands’ the data type names during compilation to their fully qualified form (that is, with their package name prepended) – and the JVM can’t then find **Juno.class** because it is forced to look into a wrong directory.

How to fix this problem? Suppose, the source code says that the classes belong to the package named **org.xlator**:

![](images/00108.jpeg)

Let’s assume further that this package is mapped to the local file system as follows:

![](images/00109.jpeg)

This means that in the simplest case when we don’t move the compiled classes to a dedicated directory (which can be done by using the compiler’s **-d** switch), the **.class** files will be stored in the same dir, **C:\Try_Java\org\xlator**.

Now it becomes obvious that in order to run a **.class** file successfully, we simply should move into the appropriate dir within the file system’s hierarchy and do our job from there:

![](images/00110.jpeg)

**Problem 1.17 – A**

**Given:**

![](images/00111.jpeg)

**Which package is automatically imported by the Java compiler?**

A.java.lang

B.javax.swing

C.[javax.net](http://javax.net)

D.java.*

E.The package with no name

We have already mentioned that the option E is outdated so what remains is just option A. This problem can be presented in a different wording on the exam but the implied meaning is essentially the same. Expect no traps here.

**Problem 1.18 – ABD**

**Which three are benefits of encapsulation?**

A.Encapsulation allows to change the class implementation without changing the clients.

B.Encapsulation prevents leakage of confidential data out of the objects.

C.Encapsulation prevents code from causing exceptions.

D.Encapsulation enables the class implementation to protect its invariants.

E.Encapsulation allows classes to be combined into the same package.

F.Encapsulation enables multiple instances of the same class to be created safely.

If I remember correctly, there was just a couple of questions related to encapsulation: one code-based and another one textual. What I don’t remember is what the textual question was asking: about benefits or the meaning of encapsulation… Probably, both; this is why I give you a combination of these variants which should cover all possible aspects. Hopefully…

Option C is out because exceptions are irrelevant to encapsulation, and E and F also miss the point.

**Problem 1.19 – A**

**Given:**

![](images/00112.jpeg)

**What is the result?**

A.3 2 3 1

B.3 2 3 0

C.3 1 3 1

D.3 1 3 0

We can see right from the beginning that this problem contains no traps related to compilation errors, and that’s a good news as we don’t have to watch out for something non-`static` in `static` context, incompatible assignments and whatnots. A good third of the questions on the actual exam are like this, which makes our life easier.

Now, the code declares a local var (on line 1) that shadows the instance field **z** → hence line 2 outputs 3\. Then the code invokes **doStuff()** that declares another shadow-casting local var on line 5, which gets printed on line 6 and produces 2 because the second, overloaded **doStuff()** changes the instance field rather the local var's value. When we add here one of the most important rules for the exam – local vars are visible only inside the methods they are declared in – it becomes obvious that line 3 prints 3, and then line 4 prints the value of the instance field that was changed by the overloaded **doStuff(**int**)**, namely 1.

**Problem 1.20 – D**

**Given:**

![](images/00113.jpeg)

**What is the result?**

A.kk = 0, kk = 2, kk = 0,

B.kk = 0, kk = 2, kk = 2,

C.kk = 0, kk = 2, kk = 4,

D.Compilation fails.

One of the most ‘popular’ traps on 1Z0-808; fortunately for us, it’s also quite simple. All you have to remember is that local vars are visible inside the nearest^([49](#part0015_split_002.html_id_90)) matching pair of braces – and loop vars are not exempted from this rule despite the fact they are declared *before* the braces → meaning that the second printing stat throws a comperr since **kk** isn’t visible anymore on line 1.

You would have remembered this little peculiarity exhibited by loop vars if you watched Simon’s *Live Lessons*: he briefly mentions it when talking about loops. In fact, I can tell you in retrospect that when someone like Simon Roberts calls our attention to certain subtleties, we can be pretty sure to meet them on the actual exam.

**Problem 1.21 – BCF**

**Which three statements are true about the structure of a Java class?**

A.Only one private constructor is allowed per class.

B.A class can have overloaded static methods.

C.A field and a method can share the same name.

D.A public class must have a main method.

E.No class can be declared without methods.

F.Fields do not need explicit initialization before use.

The question is as straightforward as it can be. The only item worthy of spending a minute on is, perhaps, option C.

The possibility for a field (can be either a class or an instance var) and a method to share the same name is due to the fact that Java has *four* namespaces: for fields, methods, data types, and packages, hence no conflict. Other languages can have a radically different view on this; for example, Scala recognizes just two namespaces: for values (fields, methods, packages, and singleton objects), and for types (class and trait names).

Four namespaces in Java can provide endless hours of amusement for the whole family, pets included; consider, for example, the following class:

![](images/00114.jpeg)

This little bundle of mischief compiles without a hitch but the JVM then chokes on **main()**:

![](images/00115.jpeg)

The code happily prints "String!" as soon as we refine the reference to the **String** array **string** by stating the fully qualified name for the needed data type, which used to be obscured:

![](images/00116.jpeg)

**Problem 1.22 – C**

**Given:**

![](images/00117.jpeg)

**What is the output?**

A.one

B.two

C.three

D.four

This one is just a simpler variant of [Problem 1.5](#part0015_split_002.html_id_315)as the exam creators sometimes repack their questions to test related concepts from different angles. There’s no trap; all the question does is innocently asking if we know the **main()** method’s signature…

**Problem 1.23 – D**

**Given the contents of three files:**

![](images/00118.jpeg)

**Which snippet will allow the code to compile and run successfully?**

A.Add to class **Raspi**:

`import peripherals.*;`
`import microsd.microSD;`

B.Add to class **Raspi**:

`import peripherals.Peripherals;`
`import microsd.microSD.*;`

C.In class **Raspi**:

add import peripherals.*; replace line r2 with `microSD.writeImage();`

D.In class **Raspi**:

add import static microsd.microSD.writeImage; replace line r1 with `new peripherals.Peripherals();`

E.Add to class **Raspi**:

`import peripherals.Peripherals;`
`import static microsd.microSD.writeImage();`

Available options strongly hint on problems with `import`s; what’s more, the class **Raspi** lacks any of them so the nature of our task is apparent. On the other hand, the exam just loves to palm off redundant or syntactically incorrect `import`s on us, so in the questions that concern interaction among data types located in different packages, it is much safer to start with **main()** and go with the execution flow.

**Raspi**’s **main()** calls **assemble()** who references a constructor in **Peripherals** and a certain **writeImage()** method, which is not defined in **Raspi** → this is a telltale sign that **writeImage()** is `static` – provided, of course, its invocation is valid in the first place → a glance at **microSD** confirms: yeap, the method *is* `static` → we’ll only need to look for `import static`^([50](#part0015_split_002.html_id_92)) in the given options → A, B and C are instantly eliminated.

Now, option D quite correctly imports a `static` method → we can even contrast it with option E, which tries to do the same but uses () after the method’s name – and that’s not allowed → done.

At the Review stage we check the second LOC in option D → oh yes, it uses a fully qualified name so there’s no need to import anything from the package **peripherals**. Now let’s make double sure all other options are indeed incorrect.

E is wrong, we already know that. What about A? Its second LOC is valid but the invocation of **writeImage()** still needs the class name – or an object – and we have none.

Option B is out because its second `import` uses a wildcard after the class name as if it were a package.

Option C does reference the class name for **writeImage()** but the compiler still has no idea where to look for this class as its `import` is missing.

When everything is in place, the program outputs OK… OK… It works!

* * *

^([40](#part0015_split_000.html_id_71)) Some people also refer to them as *class fields* but we won’t. After all, the JLS has no notion of ‘class fields’; it mentions only ‘*super*class fields’, and from the context it becomes clear that the term means instance fields defined in the supertype.

^([41](#part0015_split_000.html_id_73)) Okay, okay, so constructors aren’t class members, I admit. Let’s pretend they are for the sake of brevity.

^([42](#part0015_split_000.html_id_75)) Parameters are values passed to a method at the point of its invocation whereas arguments are the actual values the method works with. Or think of them this way: args are defined in signatures, params are used in calls. Many people don’t see the difference; the OCA exam won’t test you on this, either; needed for OCP, though.

^([43](#part0015_split_000.html_id_79)) It provides language support by making available fundamental types, system methods, widely used classes such as **String**, **StringBuilder**, **Math** and so on, threads, and exceptions. Contains 104 data types (at least in 1.8).

^([44](#part0015_split_000.html_id_77)) Unlike the #include directive in C/C++ that makes the compiler look into the standard library and copy code from the header files into the program (thus increasing the program size, which wastes memory and the CPU time), the `import` stat makes the JVM look into the Java standard library, execute code there, and substitute the result into the program. As no code is copied and there is no waste of memory or processor’s resources, Java’s import can be considered as more efficient mechanism than #include.

^([45](#part0015_split_000.html_id_83)) BTW, I didn't meet the **Arrays.binarySearch()** method on the exam; that’s why this guide doesn’t cover it.

^([46](#part0015_split_000.html_id_81)) Alan Key – who invented the term ‘object-oriented’ – reportedly remarked once that the term is actually a misnomer: it should have been something like ‘message-oriented’…

^([47](#part0015_split_002.html_id_85)) Plus constructors plus static and instance initers, although these guys are not class members (JLS, §8.2).

^([48](#part0015_split_002.html_id_87)) It’s a matter of personal preference, of course, but for those with poor eyesight – take me, for example – I’d recommend to download the whole bunch of javadocs from Oracle and keep them on your local drive. Not just because of speed; it’ll become a lot easier on your eyes if you tweak the root-level style-defining file (lives inside <your_jdk_1.8_path>\docs\api dir; in my case it’s C:\Program Files\Java\jdk1.8.0_66\docs\api\stylesheet.css) to change typefaces, font sizes and colors for different tags, etc. It really helps to decrease the strain, believe me.

^([49](#part0015_split_002.html_id_89)) Nearest to the local var’s declaration point, that is.

^([50](#part0015_split_002.html_id_91)) Why `import static` and not just `import`? Because the call omits the class name.

![](images/00119.jpeg)

**The 1Z0-808 objectives within this group:**

| [2.1](#part0016_split_000.html_c2.1) | Declare and initialize variables (including casting of primitive data types) |
| [2.2](#part0016_split_000.html_c2.2) | Differentiate between object reference variables and primitive variables |
| [2.3](#part0016_split_002.html_c2.3) | Know how to read or write to object fields |
| [2.4](#part0016_split_003.html_c2.4) | Explain an object’s lifecycle (creation, "dereference by reassignment" and garbage collection) |
| [2.5](#part0016_split_005.html_c2.5) | Develop code that uses wrapper classes such as **Boolean**, **Double**, and **Integer** |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

As the first two objectives are closely related, we will cover them in a single block.

2.1Declare and initialize variables (including casting of primitive data types) +

2.2Differentiate between object reference variables and primitive variables:

![](images/00012.jpeg)Declaring a variable is done by stating the data type and giving the variable a valid identifier, in other words, name.

![](images/00012.jpeg)The exam uses identifiers that contain – using regex for brevity – only [a-zA-Z$_]^([51](#part0016_split_007.html_id_94)). Identifiers are not limited in their length.

![](images/00012.jpeg)Identifiers may not begin with a digit. As for the underscore _ and the dollar sign $, they are allowed in the starting place. There’s one question on the exam that has a var’s name that starts with a digit. As soon as you find it, you can forget about traps in identifiers.

![](images/00012.jpeg)Java keywords such as `switch` and so on, may not be used as identifiers.

![](images/00012.jpeg)A literal is a fixed value that doesn’t need further calculations to be assigned to any variable provided the variable is of a compatible type.

![](images/00012.jpeg)Numeric literals, which are used to represent numeric values, may contain underscores between digits and begin with 1–9, 0, 0x, 0X, 0b, or 0B (where 0 stands for zero).

![](images/00012.jpeg)When several variables share a type, they can be declared and initialized in the same statement.

![](images/00012.jpeg)***Non-final*** non-local variables do not require explicit initialization: they are inited automatically to their corresponding default value (which depends on the data type in question) during object instantiation (for instance fields) or class initialization (for `static` fields). ***final*** vars mandate explicit initing (discussed in more detail in the Exam Objective 6.3, *Create and overload constructors, including impact on default constructors*).

EXTRA: Methods in a `final` class are effectively `final` since it’s obviously impossible to override or hide them; as for fields, they aren’t implicitly `final`:

![](images/00120.jpeg)

![](images/00012.jpeg)Local variables (including loop vars) must be explicitly initialized before use.

![](images/00012.jpeg)The basic building blocks of Java types are the so-called primitive types, which are predefined by the language. Java doesn’t allow user-defined primitive types.

![](images/00012.jpeg)The language defines eight primitive data types – `byte`, `short`, `int`, `long`, `float`, `double`, `char`, and `boolean` – which can be classified as follows:

![](images/00059.jpeg)numeric:
– integral types
– floating-point types

![](images/00059.jpeg)boolean

![](images/00012.jpeg)Numeric types:

![](images/00059.jpeg)Numeric types can store either integer or floating-point values.

![](images/00059.jpeg)`byte`, `short`, `int`, and `long` can be used to store integers.

![](images/00059.jpeg)`byte`, `short`, `int`, and `long` allocate 8, 16, 32, and 64 bits, respectively, to store their values.

![](images/00059.jpeg)`float` and `double` can be used to store floating-point values.

![](images/00059.jpeg)`float` and `double` allocate 32 and 64 bits, respectively, to store their values.

![](images/00059.jpeg)The default data type for integral literals is `int`.

![](images/00059.jpeg)To designate an integer as `long`, we append L or l to the literal value.

![](images/00059.jpeg)Numeric values can be stored in binary, octal, decimal, and hexadecimal formats.

![](images/00059.jpeg)Decimal literals use digits from 0 to 9\. Octal literals use digits from 0 to 7 (a total of 8 digits). Hexadecimal literals use digits from 0 to 9 and letters from A to F. Binary literals use digits 0 and 1.

![](images/00059.jpeg)Octal literals must be prefixed with 0 (zero), hex literals start with the prefix 0x or 0X, and binary literals begin with 0b or 0B.

![](images/00059.jpeg)The default data type for floating-point values is `double`.

![](images/00059.jpeg)To designate an integral or floating-point value as `float`, we add the suffix F or f to the literal value.

![](images/00059.jpeg)The suffixes D and d can be used to mark a literal as a `double` value.

![](images/00059.jpeg)The `char` data type is stored as an unsigned positive integer.

![](images/00059.jpeg)`char` can store a single 16-bit Unicode character, from '\u0000' (or 0) to a maximum of '\uffff' (or 65,535) inclusive.

![](images/00059.jpeg)When a symbol gets assigned to a `char`, Java stores its integer equivalent value. It is therefore allowed to assign a positive integer value to a `char` instead of a symbol (for example, `char ch = 97` to store the letter ‘a’).

![](images/00059.jpeg)To assign a symbol to a `char` variable, we use single quotes: `char ch = 'a';`

![](images/00012.jpeg)The data type boolean:

![](images/00059.jpeg)`boolean` can store data with only two possible values, `true` and `false`, which are also used as literal values.

![](images/00059.jpeg)Unlike some other programming languages, Java does not recognize the numeric literals 1 and 0 as valid `boolean` values.

![](images/00012.jpeg)Casting:

![](images/00059.jpeg)Casting is the process of forcefully making a variable behave as a variable of another type. Casting applies to both primitive and reference variables, and can be implicit or explicit.

![](images/00059.jpeg)Automatic casting done by the Java compiler internally is called implicit casting. Implicit casting is performed to convert a narrower data type to a wider data type.

![](images/00059.jpeg)The casting done by the programmer is called explicit casting. Explicit casting is mandatory to convert a wider data type to a narrower data type.

![](images/00059.jpeg)Converting a narrower data type into a wider data type is called widening while converting a wider data type into a narrower type is called narrowing. Widening is safe so the Java compiler does not flag any error even if the programmer did not use the cast operator `(T)`. Narrowing is intrinsically unsafe, hence the programmer should explicitly use the cast operator in narrowing.

![](images/00012.jpeg)Reference types:

![](images/00059.jpeg)Primitive types, which represent single values, can be assembled into reference types, which represent a group of values.

![](images/00059.jpeg)Apart from this, reference types can also have methods.

![](images/00059.jpeg)Unlike primitive types, reference types can be `null`.

![](images/00012.jpeg)Default values for primitive numeric types are their corresponding ‘zeroes’ (that is, 0 or 0.0) and `false` for `boolean`.

![](images/00012.jpeg)Reference types default to `null`.

**Extra Practical Rules**:

•Both f/F and d/D can be used not only on floating-point literals, so float f = 10F is VALID.

•ANY integral literal (incl. in binary, hex or octal notation) is assignable to `long` w/o l/L.

•ATTN: `char` literals (such as ‘a’, etc.) are assignable to `long` BUT w/o l/L ONLY.

•The underscores in numerical values can appear ONLY between digits or be chained like

1____2__3 (same as 123)^([52](#part0016_split_007.html_id_96)). They can be used in the floating point literals, too:

![](images/00121.jpeg)

•`float`s with floating-point literals should have f/F appended → be attentive to the cases when they are passed to methods that expect `float`s.

Using Exponent:

The exponent is used with the floating-point literals only (e or E for decimals, or p or P for hexes):

![](images/00122.jpeg)

| Octal Notation: | A floating point number cannot be written in octal (it gets interpreted as decimal, instead): |

![](images/00123.jpeg)

| Casting to char and back: | What it boils to, `char` is unsigned whereas `byte`, `short`, etc. can be negative, so **char = short** and so on *won’t compile*. |
|  | Also, `char` can hold up to 65535 while `short` maxes out at 32767, so **short = char** *won’t compile*, either. An explicit cast to the rescue! |

•Implicit narrowing occurs only for `byte`, `char`, `short`, and `int` → it does not occur for `long`, `float`, or `double`.

So, this will not compile:

`int i = 129L;`
`char ch = 30L;` will fail, too, even though 30 is representable in `char`.

However:

`final int s = 10;`
`char c = s; //` OK as **s** is a constant (it’s final) and its value fits into a `char`.

Combat Rule:

No *VARIABLE* other than `char` can be assigned to a `char` without an explicit cast whereas a *CONSTANT* can be assigned to a `char` only if the value fits into `char`.

Converting from `int` or `long` to `float` or from `long` to `double` can lead to loss of precision.^([53](#part0016_split_007.html_id_100))

`char` behaves almost as an unsigned `short`^([54](#part0016_split_007.html_id_98)), e.g.:

`sout('a' +1)` prints 98

A floating-point literal written in **binary** or **hex** cannot use any suffix denoting the floating-point notation (**other wording**: the floating-point suffixes f, F, d, and D are applicable only to decimal notation.)

**Known trap on the exam:** Watch out for casts: they act on the nearest right-side neighbor only.

`null` can be cast to any reference type: `"Hello".equals((String)null);` is perfectly valid.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 2.1Given:**

![](images/00124.jpeg)

**What is the result?**

A.42 43
44 45 null

B.42 43
44 45 46

C.Compilation fails

D.A NullPointerException is thrown at run time

E.An ArraylndexOutOfBoundsException is thrown at run time

**Problem 2.2Given the code fragment:**

![](images/00125.jpeg)

**How many LOCs fail to compile?**

A.one

B.two

C.three

D.four

**Problem 2.3Given the following code:**

![](images/00126.jpeg)

**And the following main method inside another class in the same package:**

![](images/00127.jpeg)

**Assuming that the hash codes are correct, what is the result?**

| A. | Group: Element:
Number of electrons: | AlkaliMetals Rubidium
37 |
| B. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@2a139 a55 Rubidium
37 |
| C. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@2a139a55 periodictable.Element@15db9742
37 |
| D. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@2a139a55 periodictable.Element@15db9742
Electrons@372sf871 |
| E. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@2a139a55 Rubidium
null |

**Problem 2.4Which two code fragments are illegal?**

A.abstract int MyVar = 42;

B.private final static String str = "?!";

C.byte b1 = 1, b2, b3 = 3;

D.short s1 = 10, int i1 = 123;

E.double d1 = 0f;

**Problem 2.5Given:**

![](images/00128.jpeg)

**Which two declarations compile?**

A.On line 1

B.On line 2

C.On line 3

D.On line 4

A.On line 5

**Problem 2.6How many illegal statements are in the following code fragment?**

![](images/00129.jpeg)

A.One

B.Two

C.Three

D.Four

E.None

**Problem 2.7Which declaration correctly initializes a** boolean **variable?**

A.boolean flag1 = 1;

B.boolean flag2 = 0;

C.boolean flag3 = null;

D.boolean false = false;

E.boolean True = 1 < 2;

**Problem 2.8Which code fragment causes a compilation error?**

A.float f3 = 1000;

B.float f1 = 1000F;

C.float f2 = (float) 1_000.0;

D.double f4 = 1000.0;

E.float f5 = 1000.0;

F.float f7 = (float) f4;

**Problem 2.9Given:**

![](images/00130.jpeg)

**What is the result?**

A.0 4 8 12

B.0 2 6 10 14

C.Compilation fails

D.The program enters an endless loop

E.The program prints nothing

**Problem 2.10Given:**

![](images/00131.jpeg)

**What is the result?**

A.Result: 4

B.Result: 5

C.Result: 6

D.The program enters an endless loop

E.Compilation fails

**Problem 2.11Given:**

![](images/00132.jpeg)

**What is the result?**

A.21.0 32.0 107.0 43.0

B.21.0 32.0 a10 43.0

C.Compilation fails

D.An exception is thrown at run time

**Problem 2.12Given:**

![](images/00133.jpeg)

**What is the result?**

A.parent: class test.Object
child: class test.Child

B.parent: class test.Parent
child: class test.Child

C.parent: class test.Child
child: class test.Parent

D.parent: class test.Child
child: class test.Child

**Problem 2.13Given:**

![](images/00134.jpeg)

**What is the result?**

A.0

B.null

C.Compilation fails

D.java.lang.NullPointerException is thrown

**Problem 2.14Given:**

![](images/00135.jpeg)

**What is the result?**

A.5

B.10

C.15

D.Compilation fails

E.An exception is thrown at run time.

**Problem 2.15Given:**

![](images/00136.jpeg)

**What is the result?**

A.0 2 4 6

B.0 2 4 6 9

C.1 3 5 7

D.1 3 5 7 9

E.Compilation fails

F.An exception is thrown at run time

**Problem 2.16Given:**

![](images/00137.jpeg)

**What is the result:**

A.0

B.0.0

C.-0.0

D.Compilation fails

E.An IllegalArgumentException is thrown at run time

**Problem 2.17Given the following code fragment:**

![](images/00138.jpeg)

**What is the result?**

A.pos is printed

B.neg is printed

C.Compilation fails

D.An ArithmeticException is thrown

**Problem 2.18Given the following:**

![](images/00139.jpeg)

**What is the result?**

A.The code prints 4.0

B.Compilation fails on line 2

C.Compilation fails on line 6

D.Compilation fails on line 9

![](images/00061.jpeg) **CORE RULES:**

2.3Know how to read or write to object fields:

![](images/00012.jpeg)An object field is another name for an instance variable defined in a class.

![](images/00012.jpeg)Access modifiers^([55](#part0016_split_007.html_id_102)) determine if the object fields can be read and written to directly by using instance variables.

![](images/00012.jpeg)Accessing object fields:

![](images/00059.jpeg)Reading:

–by directly accessing the field (its access modifier permitting), or

–by using a method that returns the field’s value.

![](images/00059.jpeg)Writing:

–by directly accessing the field (its access modifier permitting), or

–by using constructors or methods that assign a value to the field.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 2.19Given:**

![](images/00140.jpeg)

**And given the code fragment:**

![](images/00141.jpeg)

**What is the result?**

A.true : true

B.true : false

C.false : true

D.false : false

**Problem 2.20Given:**

![](images/00142.jpeg)

**What is the result?**

A.Name: Alice, Passed: true

B.Name: Alice, Passed: false

C.Name: Bob, Passed: true

D.Name: Bob, Passed: false

E.Compilation fails

**Problem 2.21Given the class:**

![](images/00143.jpeg)

**What is the result if we comment out all those LOCs that do not compile?**

A.iVar=22, cVar=22

B.iVar=200, cVar=300

C.iVar=400, cVar=700

D.iVar=600, cVar=1100

**Problem 2.22Given:**

![](images/00144.jpeg)

**What is the result?**

A.null 12 null 123

B.Hi! 12 null 12

C.Hi! 12 null 123

D.Compilation fails

**Problem 2.23Given:**

![](images/00145.jpeg)

**What is the result?**

A.80 Junior

B.120 Senior

C.170 Grandpa

D.Compilation fails

**Problem 2.24Given:**

![](images/00146.jpeg)

**What is the result?**

A.: Darcula

B.null : Darcula

C.Darcula : Darcula

D.A NullPointerException is thrown at run time

**Problem 2.25Given:**

![](images/00147.jpeg)

**What is the result?**

A.a, bc, d

B.a, bd, d

C.c, bd, d

D.b, cc, d

**Problem 2.26Given the following classes:**

![](images/00148.jpeg)

**Which statement sets the field name of the object std?**

A.std.setName() = "John Smith";

B.setName("John Smith");

C.Student.setName("John Smith");

D.std.setName("John Smith");

![](images/00061.jpeg) **CORE RULES (with some Extras):**

2.4Explain an object’s lifecycle (creation, "dereference by reassignment" and garbage collection):

![](images/00012.jpeg)Object’s lifecycle:

![](images/00059.jpeg)It begins when the object is initialized and ends when the object goes out of scope or is no longer referenced;

![](images/00059.jpeg)A live object can be referenced by a var to make available its methods and fields to other objects;

![](images/00059.jpeg)Simply declaring a reference var does not imply that a new object will be created.

![](images/00059.jpeg)Out of several practical ways^([56](#part0016_split_007.html_id_106)) to create a new object in Java only two are needed for the 1Z0-808 exam:

| – by using the keyword `new` | ← universal method^([57](#part0016_split_007.html_id_104)) |
| – by using double quotes | ← this shorthand is available only for **String**. |

![](images/00059.jpeg)An object becomes eligible for garbage collection when it can no longer be accessed.

![](images/00059.jpeg)An object becomes inaccessible when no reference variable points to it any longer because:

–the reference variable was re-assigned to another object,

–the refvar was set to `null`, or

–went out of scope

![](images/00012.jpeg)The inaccessible objects are removed from memory by the so-called garbage collection mechanism. The purpose of garbage collection is to identify and remove the objects that are no longer needed by a program so that their resources can be reclaimed and reused.

![](images/00012.jpeg)EXTRA: **OutOfMemoryError** is thrown by the JVM when it’s unable to create objects on the heap and the garbage collector cannot free more memory for the JVM.

![](images/00012.jpeg)EXTRA: The programmer can attempt to call the garbage collector by calling the method **System.gc()** or **Runtime.getRuntime().gc()** but the fact is the garbage collector is invoked fully automatically and it is not guaranteed that the GC process will ever run during a program’s lifecycle. All we can be sure about is whether objects are eligible for being garbage collected.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 2.27Given:**

![](images/00149.jpeg)

**How many objects of the class ObjectsGalore are created in memory at run time?**

A.1

B.4

C.8

D.Compilations fails

**Problem 2.28Given:**

![](images/00150.jpeg)

**Which statement, when inserted at line X, correctly initializes an ExamTaker instance?**

A.ExamTaker examTaker = "Bob";

B.ExamTaker examTaker = ExamTaker.new("Bob", 100, " 1Z0-808");

C.ExamTaker examTaker = new ExamTaker();

D.ExamTaker examTaker = ExamTaker("Bob", 100, " 1Z0-808");

E.None of the above

**Problem 2.29Given:**

![](images/00151.jpeg)

**Which statement is true?**

A.After line 14, three objects are eligible for garbage collection.

B.After line 14, two objects are eligible for garbage collection.

C.After line 14, one object is eligible for garbage collection.

D.After line 14, none of the objects is eligible for garbage collection.

**Problem 2.30Given:**

![](images/00152.jpeg)

**When the object** `ab`**, created by LOC18, becomes eligible for GC?**

A.After line 22

B.After line 23

C.After line 24

D.Never in this program

![](images/00061.jpeg) **CORE RULES (with some Extras):**

2.5Develop code that uses wrapper classes such as **Boolean**, **Double**, and **Integer**:

![](images/00012.jpeg)What are wrapper classes?

Java provides specialized classes corresponding to each of the primitive data types:

![](images/00153.jpeg)

These are called wrapper classes.

![](images/00012.jpeg)Why do we need wrapper classes?

Sometimes it becomes easier to handle primitives if they were objects. For example, the wrapper classes provide many useful methods for such occasions but these methods expect objects as their arguments. Now and then it is simply required: say, being a **Collection**, an **ArrayList** is not allowed to contain primitives. In this case, Java can autobox the passed primitive parameters into the proper wrapper types – and we then can use on them handy methods from the **java.util** package such as **Collections.sort()** and so on.

![](images/00012.jpeg)What is autoboxing?

Autoboxing refers to converting primitive data types into objects (that is, instances of the corresponding wrapper classes) automatically by the compiler.

![](images/00012.jpeg)What is unboxing?

Converting an object into its underlying primitive data type is called unboxing.

**EXTRA:**

![](images/00012.jpeg)More on wrappers:

![](images/00059.jpeg)All primitive wrappers’ constructors EXCEPT **Character** (which has only one constructor: **Character**(char value)) accept a `null` treating it as a null **String** but they then throw an NFE (or NPE in case of **Float** and **Double** ) EXCEPT the **Boolean**(null) constructor, which returns `FALSE` (in contrast to the primitive `false`).

![](images/00059.jpeg)None of the primitive wrapper classes has a no-arg constructor.

![](images/00059.jpeg)ALL wrappers (except **Character**) accept a **String** and ALL (no exceptions) accept their underlying primitives;

![](images/00059.jpeg)Most popular methods:

![](images/00154.jpeg)

![](images/00059.jpeg)**Boolean**.FALSE is an **Object** (same for **Boolean**.TRUE).

![](images/00012.jpeg)**Constructors: in most cases two constructors** (except **Character** and **Float**)

![](images/00155.jpeg)

![](images/00012.jpeg)primitive == wrapper works; the right-hand side gets unboxed.

![](images/00012.jpeg)A primitive passed to a **List**<Wrapper> will autobox.

However – WATCH OUT! – the compiler will perform **only a single-step** conversion on its own! can’t add, say, a `byte` or `short` to **List**<Integer>):

![](images/00156.jpeg)

![](images/00012.jpeg)Parsers of the wrapper classes accept only **String**s (or **String**, radix).

![](images/00012.jpeg)**Boolean.valueOf(**String**)** and its overloaded **Boolean.valueOf(**boolean**)** version return a reference to either **Boolean**.TRUE or **Boolean**.FALSE wrapper obj, and do NOT create a new **Boolean** object; they simply return the `static` constants **TRUE** or **FALSE** defined in the **Boolean** class.

![](images/00012.jpeg)All wrapper classes are immutable.

![](images/00012.jpeg)Although the wrappers extend **Number**, there’s no IS-A relation between any two of the wrapper classes. So, casting an **Integer** to, say, **Long** won’t work. **Byte** == **Short**, etc. throws a comperr, too.

![](images/00012.jpeg)**Byte**, **Short**, **Integer** and **Long** use the same numerical pool (similar to **String** case) up to `byte`’s boundaries (-128 ... 127), hence == evaluates to `true` when the values are the same and do not overshoot this range. Beyond those boundaries, the operator ‘double equals’ compares just object references.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 2.31Given:**

![](images/00157.jpeg)

**Which two modifications, made independently, enable the code to print** `Gone with the Wind, new: true, price: 9.5`**?**

A.Replace line b2 with:

`b.title = "Gone with the Wind";`
`b.secondHand = false;`
`b.price = 9.5;`

B.Replace line b2 with:

`this.title = "Gone with the Wind";`
`this.secondHand = false;`
`this.price = 9.5;`

C.Replace line b1 with:

`this.title = new String("Gone with the Wind");`
`this.secondHand = new Boolean(false);`
`this.price = new Double(9.5);`

D.Replace line bl with:

`title = "Gone with the Wind";`
`secondHand = FALSE;`
`price = 9.5f;`

E.Replace line b1 with:

`this("Gone with the Wind", false, 9.5);`

**Problem 2.32Given:**

![](images/00158.jpeg)

**What is the result?**

A.true false false

B.true true false

C.false false false

D.An IllegalArgumentException is thrown at run time

E.A NullPointerException is thrown at run time

**Problem 2.33Given:**

![](images/00159.jpeg)

**What is the result?**

A.input: 0123, output: 0123

B.input: 2013, output: 0123

C.input: 2013, output: 83

D.Wrong argument!

E.None of the above

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 2.1 – A**

**Given:**

![](images/00160.jpeg)

**What is the result?**

A.42 43
44 45 null

B.42 43
44 45 46

C.Compilation fails

D.A NullPointerException is thrown at run time

E.An ArraylndexOutOfBoundsException is thrown at run time

The refvar **astr** declared on line t1 is local and needs explicit initing before use. The next example throws a comperr saying that variables **myStr** ‘may not have been initialized’:

![](images/00161.jpeg)

This restriction becomes painfully evident in case of primitives, which you have doubtlessly observed many times. In our problem, however, we are dealing with an array, which is a reference type whose value gets inited at the point of allocation (an object gets created → the refvar that points to it is assigned a value that holds this object’s address). The following compiles but throws an **ArrayIndexOutOfBoundsException** when the JVM attempts to access the first slot in the array **astr**:

![](images/00162.jpeg)

Still, the reference var **myArr** is inited even if its length is zero. But what about the values that an array’s slots hold when the array’s length isn’t zero? The JLS8, §4.12.5, says that

Each class variable, instance variable, or array component is initialized with a default value when it is created.

From here follows that since our array is of type **String**, each slot gets inited with a `null` as the same §4.12.5 stipulates that "For all reference types, the default value is `null`".

Now, the code in [Problem 2.1](#part0016_split_007.html_id_316) uses a nested `for` loop to assign some other values to the second dimension of the array **astr** but takes the *first* dimension’s length as the criterion for its conditional expression on line t2\. Since the array is jagged (its 2nd dim is longer than the 1st dim), the last slot in the 2nd dim is left out of the loop and retains its initial value, that is, `null`. Should the conditional expression on line t2 be rewritten as `j<astr[0].length`, the 2nd dim wouldn’t have contained `null`s at all.

**Problem 2.2 – C**

**Given the code fragment:**

![](images/00163.jpeg)

**How many LOCs fail to compile?**

A.one

B.two

C.three

D.four

The floating-point literals are treated as `double`s by default but line 4 works because 123.123 has the suffix **f** appended to it; otherwise it wouldn’t have compiled.

Line 5 compiles because floating-point variables accept integer constants.

Line 6 is OK, too, since the value 123 – which is an `int` by default – is automatically narrowed to `short` and 123 is within the range for a `short`.

Line 7 is just trivial and doesn’t throw a comperr, either.

On line 8 we have an automatic widening to a `long`.

Line 9, however, attempts to assign a floating-point variable to an int, so the compiler complains of ‘a possible lossy conversion from `float` to `int`’. An explicit cast to `int` would have worked here, although it can lead to a loss of precision.

The assignments on lines 11 through 12 are all valid because the right-hand sides are narrower than the left-hand sides, but the next LOC attempts to perform a lossy conversion from `double` to `float`. An explicit cast `fVar = (float)dVar` would force the LOC to compile.

And finally, line 15 wants to assign a wider `double` to a much narrower `int`, which flags a comperr. Naturally, `iVar = (int)dVar` would make the line valid.

Taking all this into consideration, we can conclude the current exercise by formulating the following rule: explicit casts between primitive numeric types always compile. By the way, [Problem 2.6](#part0016_split_007.html_id_317)addresses some interesting variations of this tune.

**Problem 2.3 – C**

**Given the following code:**

![](images/00164.jpeg)

**And the following main method inside another class in the same package:**

![](images/00165.jpeg)

**Assuming that the hash codes are correct, what is the result?**

| A. | Group: Element:
Number of electrons: | AlkaliMetals Rubidium
37 |
| B. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@<*hash_value*> Rubidium
37 |
| C. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@<*hash_value1*> periodictable.Element@<*hash_value2*>
37 |
| D. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@<*hash_value1*> periodictable.Element@<*hash_value2*>
Electrons@<*hash_value3*> |
| E. | Group: Element:
Number of electrons: | [Lperiodictable.Element;@<*hash_value*> Rubidium
null |

This problem contains a small trap that tests our knowledge of the fact that primitive and reference variables behave differently in many aspects. For example, even if a reference variable has been initialized, there’s no guarantee that its string representation is always meaningful.

In this particular case we are dealing with an array of nameless objects, and arrays do not override the method **toString()**, which they inherit from the class **Object**. Something similar goes for user data types: they all should override **toString()**. If we added, say, the following declaration to the definition of the class **Element**

![](images/00166.jpeg)

the code’s output would have been option B.

**Problem 2.4 – AD**

**Which two code fragments are illegal?**

A.abstract int myVar = 42;

B.private final static String $tr = "?!";

C.byte b1 = 1, b2, b3 = 3;

D.short s1 = 10, int i1 = 123;

E.double d1 = 0f;

Option A is correct because no variable (either of primitive or reference data type) may be declared `abstract` in Java^([58](#part0016_split_007.html_id_108)). Option D is correct, too, as multiple declaration of variables of different data types is not allowed in one statement (the comma should have been replaced with the semicolon). Potentially problematic B is out since the Problem doesn’t say **$tr** is local.

**Problem 2.5 – AD**

**Given:**

![](images/00167.jpeg)

**Which two declarations compile?**

A.On line 1

B.On line 2

C.On line 3

D.On line 4

E.On line 5

Option A is correct because we have three vars of the same data type declared within a single stat, and the fact that only one of them gets inited is irrelevant because those vars are never used.

Line 2 does nothing criminal in itself and would have compiled when placed before line 1 but the problem is these two LOCs declare the same local vars → they are mutually exclusive.

Option C fails compilation because the syntax does not allow repetition of data types within a single declaration stat (and commas make this entire LOC a single stat.)

Option D is OK, although Java Code Conventions^([59](#part0016_split_007.html_id_112)) recommends to reserve fully capitalized identifiers for constants only (and **FIELD** looks particularly odd here as the var is local). It’s not a felony, though… yet^([60](#part0016_split_007.html_id_110)).

And finally, option E is invalid as it attempts to assign an undeclared **l** to **k** and undeclared **m** to **l**. If the code declared both **l** and **m** before this line, it would have compiled:

![](images/00168.jpeg)

**Problem 2.6 – C**

How many illegal statements are in the following code fragment?

![](images/00169.jpeg)

A.One

B.Two

C.Three

D.Four

E.None

Line 1 is illegal because 128 is an `int` by default; actually, it wouldn’t be a problem thanks to implicit narrowing but the value exceeds `byte`’s range → this LOC requires an explicit narrowing cast → and this is exactly what line 2 does; note, however, that the most significant bit gets lost in the process thus giving us an interesting result at run time.

Line 3 fails compilation because casting an `int` to `short` explicitly still doesn’t address implicit lossy conversion to `byte`. What we can do here is step down one more time by adding another narrowing cast.

As for line 4, it wants to redundantly cast an `int` to `int`, which still gets assigned to a much narrower `byte` thus flagging a comperr.

Here’s how we could re-write the currently illegal LOCs to make them compile:

![](images/00170.jpeg)

**Problem 2.7 – E**

**Which declaration correctly initializes a** boolean **variable?**

A.boolean flag1 = 1;

B.boolean flag2 = 0;

C.boolean flag3 = null;

D.boolean false = false;

E.boolean True = 1 < 2;

Literals 1 and 0 are not recognized by Java as valid `boolean` values so options A and B are incorrect.

The var **flag3** is declared as `boolean`, which is a primitive data type whereas `null` can be assigned to a reference type only. If **flag3** were a **Boolean**, the LOC would have compiled.

Option D illegally uses the keyword `false` as an identifier.

Option E is valid since 1) the identifier **True** is not a keyword in Java, and 2) the expression 1<2 returns a `boolean`.

**Problem 2.8 – E**

**Which code fragment causes a compilation error?**

A.float f3 = 1000;

B.float f1 = 1000F;

C.float f2 = (float) 1_000.0;

D.double f4 = 1000.0;

E.float f5 = 1000.0;

F.float f7 = (float) f4;

Option A assigns an `int` to a `float`, which is valid.

Option B does the same, and the suffix F is actually redundant here.

Option C uses a mandatory narrowing cast and an underscore, which is placed correctly: between digits.

Option D is trivial because floating-point literals are `double` by default.

Option F explicitly downcasts (in other words, performs a narrowing conversion of) a `double` to a `float`, which is valid.

So this leaves us only option E: it doesn’t compile because 1000.0 is `double` by default. To make this LOC compile, we could either employ a narrowing cast or add the suffix F (or f).

**Problem 2.9 – E**

**Given:**

![](images/00171.jpeg)

**What is the result?**

A.0 4 8 12

B.0 2 6 10 14

C.Compilation fails

D.The program enters an endless loop

E.The program prints nothing

The var **flag** is an instance field and as such does not need explicit initing; it simply gets assigned the default value, that is, `false` → so the code never enters the `while` loop and the printing stats never fire.

**Problem 2.10 – E**

**Given:**

![](images/00172.jpeg)

**What is the result?**

A.Result: 4

B.Result: 5

C.Result: 6

D.The program enters an endless loop

E.Compilation fails

The var **bottom** is local and needs an explicit initing before the `while` loop may increment it. The printing stat also wants to use this uninited var, so the code actually contains two invalid LOCs.

**Problem 2.11 – A**

**Given:**

![](images/00173.jpeg)

**What is the result?**

A.21.0 32.0 107.0 43.0

B.21.0 32.0 a10 43.0

C.Compilation fails

D.An exception is thrown at run time

The easiest way to tame `char`s is to remember that these sneaky things behave almost as unsigned `short`s; take them at their numeric face, so to speak, by forcing yourself to see them as mere numbers.

Viewed from this angle, it should come as no surprise that, say, `char c = 'a' + 10` compiles just fine and that the array **darr** also gets valid primitives in each of its slots.

So, both eleven and 'a' (whose numeric value is 97) get promoted to corresponding `double`s, and 33.0f is just a `float` that is perfectly assignable to a `double`.

**Problem 2.12 – D**

**Given:**

![](images/00174.jpeg)

**What is the result?**

A.parent: class test.Object
child: class test.Child

B.parent: class test.Parent
child: class test.Child

C.parent: class test.Child
child: class test.Parent

D.parent: class test.Child
child: class test.Child

Both **c** and **p** are reference vars, so the assop `p = c` simply ‘dereferences’ **p** to **c**, that’s all. The **Parent** object gets lost as the result, and what’s left is just a single object of the type **Child** – plus two distinct references that point to it.

Hm-m… Alright, one more thing: it is probably worth to note here that ‘dereferencing’ does not mean setting a reference var to `null` (at least not in Java); it’s just a popular misconception. What really puzzles me is why the exam lists "dereference by reassignment" as one of its objectives while neither Java Lang Specs or JVM Specs define any dereference in the first place; they merely use the term…

**Problem 2.13 – B**

**Given:**

![](images/00175.jpeg)

**What is the result?**

A.0

B.null

C.Compilation fails

D.java.lang.NullPointerException is thrown

The var **arr** is of a reference type (arrays are **Object**s), so it’s only natural to set it to `null`. As to why the printing stat doesn’t throw an NPE when its arg is `null` and obediently outputs "null" instead, we have already covered it when discussing [Problem 1.15](#part0016_split_007.html_id_318).

**Problem 2.14 – C**

**Given:**

![](images/00176.jpeg)

**What is the result?**

A.5

B.10

C.15

D.Compilation fails

E.An exception is thrown at run time

This exercise relates to two exam objectives at once: 2.2, *Differentiate between object reference variables and primitive variables*, and 6.6, *Determine the effect upon object references and primitive values when they are passed into methods that change the values*.

This is what happens here: we pass **a** to the method **run()** → the method gets a copy of this reference var → then accesses the first slot of the array and increases it by ten.

Yes, the copy of **a** is a local var and dies when the method completes its work, but – unlike primitive vars – the changes made through a copy of an object reference get reflected in the object itself.

If you still feel confused by this difference, I suggest you look up the remote controller analogy^([61](#part0016_split_007.html_id_114)); personally, I know of no better explanation: it is concise, hits the bull’s-eye, pretty vivid and clear. Soon we’ll meet it again.

**Problem 2.15 – D**

**Given:**

![](images/00177.jpeg)

**What is the result?**

A.0 2 4 6

B.0 2 4 6 9

C.1 3 5 7

D.1 3 5 7 9

E.Compilation fails

F.An exception is thrown at run time

There’s no trap here, just a simple case of ‘dereference by reassignment’: as the code assigns **arr1** to **arr2**, the object, which **arr2** was pointing to, gets lost and forgotten.

**Problem 2.16 – D**

**Given:**

![](images/00178.jpeg)

**What is the result:**

A.0

B.0.0

C.-0.0

D.Compilation fails

E.An IllegalArgumentException is thrown at run time

Whatever the modulo op does is immaterial in our case because the invocation of **getModulo()** is faulty in the first place: floating-point literals are `double` by default. On the other hand, `getModulo((float)2.0)` would have worked and produced -0.0\. As to why the value is negative, please refer to the Core-Rules-plus-Extrassection for Exam Objective 3.1, *Use Java operators, including parentheses to override operator precedence*.

**Problem 2.17 – C**

**Given the following code fragment:**

![](images/00179.jpeg)

**What is the result?**

A.pos is printed

B.neg is printed

C.Compilation fails

D.An ArithmeticException is thrown

`char` can be as large as 65535 while `byte`’s range covers only -128 to 127 → the assignment on line 1 fails.

**Problem 2.18 – C**

**Given the following:**

![](images/00180.jpeg)

**What is the result?**

A.The code prints 4.0

B.Compilation fails on line 2

C.Compilation fails on line 6

D.Compilation fails on line 9

Line 2 is perfectly valid since Java allows redundant imports; just keep in mind that importing a `static` method is done without the parentheses (I met such a question on the second sitting).

The real problem lives on line 6 where each invocation of **parseDouble()** produces a `double`^([62](#part0016_split_007.html_id_116)) but only the first value gets cast to `float` → the returned value is actually a `double` but the method **squareIt()** is supposed to return a `float`.

**Problem 2.19 – C**

**Given:**

![](images/00181.jpeg)

**And given the code fragment:**

![](images/00182.jpeg)

**What is the result?**

A.true : true

B.true : false

C.false : true

D.false : false

The code creates two distinct but identical objects, **r1** and **r2**, then declares another reference var and sets its value to **r1**. Since the == operator compares references, **b1** gets assigned `false` because the objects are different; on the other hand, **r1** == **r3** would yield `true`.

Finally, line t2 assigns `true` to **b2** since the field **title** is of type **String** and the class **String** overrides **equals()** so that the method compares not just references but actual contents.

And yes, some of the questions on the exam are *that* simple; just as I said, we should take them at their face value.

**Problem 2.20 – C**

**Given:**

![](images/00183.jpeg)

**What is the result?**

A.Name: Alice, Passed: true

B.Name: Alice, Passed: false

C.Name: Bob, Passed: true

D.Name: Bob, Passed: false

E.Compilation fails

This problem uses comments to mislead you into believing that the code should print option D because "Bob failed the exam…" Personally, I didn’t meet such a trap on my sittings but, if forum posts are to be believed, there are people who did – so be on alert just in case.

The real problem awaits us on the following line inside the definition of the class **OCAJP8**:

![](images/00184.jpeg)

This LOC blindly follows the pattern which should be reserved for initializing primitive vars only as it makes two distinct references point to the same object. While in case of primitives different vars would simply get the same values and further operations with one of the variables would not affect the other one, our situation is more complicated as we are dealing with references.

Following the analogy mentioned in the discussion to [Problem 2.14](#part0016_split_007.html_id_319), **alice** and **bob** are two distinct remotes controllers that operate on the same TV set represented in our code by the object created with `new ExamTaker()`. At the moment of creation, the object was a nameless gadget, then line o1 slapped on it a sticker saying "Alice", then line o2 replaced it permanently with "Bob". After that the code pressed buttons on the remote controller named **bob** setting the TV to channel 62 (the var **score**’s value), then grabbed the remote controller named **alice** and changed the channel to 100. As the result, the output assures us that Bob passed the exam.

**Problem 2.21 – A**

**Given the class:**

![](images/00185.jpeg)

**What is the result if we comment out all those LOCs that do not compile?**

A.iVar=22, cVar=22

B.iVar=200, cVar=300

C.iVar=400, cVar=700

D.iVar=600, cVar=1100

Obviously, we should begin by investigating the reason(s) why the compilation fails in the first place. Scanning line after line, we find out pretty soon that the `static` method **main()** attempts to directly access the non-`static`, instance field **iVar**.

Now what? should we cross out all invalid LOCs and start adding numbers? but the exam software allows us to cross out only options and not the lines of code themselves → so most of the task must be performed mentally or at least on paper … the vars get reset occasionally… one of the fields is even static… wow, too many things to juggle and keep track of!

Fortunately, we are already armed with a handy practical rule – the ‘hairier’ the code, the simpler must be solution, – so let’s not even waste time on computations and writing everything down. Just look closer: it’s the very last statement that takes care of printing out the result; and what comes before it? A setter. Does the setter compile? Absolutely. It’s 22-22, then. Takes all but twenty two seconds.

Another hint for the exam: leaving aside inheritance- and overriding-related questions, it’s often printing stats that do something illegal or provide a key to instantly crack the problem, so pay close attention to **println()** and its cousins.

**Problem 2.22 – C**

**Given:**

![](images/00186.jpeg)

**What is the result?**

A.null 12 null 123

B.Hi! 12 null 12

C.Hi! 12 null 123

D.Compilation fails

We have already seen how fields can be read from and written to by using either direct access or setters, a.k.a. mutators, and getters, a.k.a. accessor methods. This problem addresses one more way to set fields, namely by making use of constructors.

The code itself is as simple as ever can be; containing no traps, the question is a typical ‘straight arrow’. The first nameless object has its **str** field inited in a constructor that doesn’t touch the var **a**, while the second object mirrors the situation leaving **str** unchanged. In fact, as far as this particular class is concerned, there is no need to assign "null" to **str** at all as the var gets set to `null` by default, and the **println()** would then print null all by itself → no change in the output.

The **println()** method’s invocation looks odd but since we defined it ourselves, there’s no comperr, either.

**Problem 2.23 – C**

**Given:**

![](images/00187.jpeg)

![](images/00188.jpeg)

**What is the result?**

A.80 Junior

B.120 Senior

C.170 Grandpa

D.Compilation fails

Another variation of the tune "How-to-set-fields-thru-object-reference". No surprises here; as for the empty `return` stat in the method **test2()**, it makes a weak, half-hearted attempt to throw a red herring across our path – and fails miserably as we do know how to read method signatures.

The most important thing about this code is that there’s only one object, just two distinct references to it, so `System. out.println(e1 == e2)` returns `true`. It comes from the fact that neither method creates anything new, they just affect instance fields.

Line t1 creates an object **e1** whose fields read 80 and "Junior" because that’s how they were set by the constructor **Engine()**. After that **test1()** changes them to 120 and "Senior" – and then what? What does the method assign to **e2** on line t2? a completely new object or a reference to what we already have? Think for a second.

OK, it’s a reference to the original object; for to return a new object, line t3 should have read `return new Engine()`. Apply this change and test the refvars with ‘double equals’… See? The output changes, too. All because we are dealing now with two distinct objects.

Alright, back to code; restore t3; next **test2()** – acting through **e2** – modifies our object by setting its fields to 170 and "Grandpa", which then get printed because **e1** and **e2** refer to the same… hm… entity. I’m objecting to saying ‘object’ all the time…

**Problem 2.24 – B**

**Given:**

![](images/00189.jpeg)

**What is the result?**

A.: Darcula

B.null : Darcula

C.Darcula : Darcula

D.A NullPointerException is thrown at run time

Just a straightforward example of using setters and getters to access object fields. The exam contains half a dozen of questions that use the JavaBeans convention for the accessor/mutator method syntax – and not a single question that would test you exactly on that: all of them address completely different objectives. Come to think of it, it appears that the JavaBeans convention isn’t on the exam, although many study guides and exam prepware do drill us on some basics. Then again, their authors apparently know what they are doing; after all, this book is based on my own experience, while they must have drawn feedback from the entire community of the former exam takers…

**Problem 2.25 – B**

**Given:**

![](images/00190.jpeg)

**What is the result?**

A.a, bc, d

B.a, bd, d

C.c, bd, d

D.b, cc, d

One more illustration of the difference between primitive and reference variables. While changes to **var2** don’t affect **var1** in the slightest, making two different references point to the same object allows us to mutate the object’s state through either of the refvars.

**Problem 2.26 – D**

**Given the following classes:**

![](images/00191.jpeg)

![](images/00192.jpeg)

**Which statement sets the field** `name` **of the object** `std`**?**

A.std.setName() = "John Smith";

B.setName("John Smith");

C.Student.setName("John Smith");

D.std.setName("John Smith");

Option A incorrectly uses the method **setName()**, which needs an argument of type **String**.

Option B is invalid because **setName()** is not `static` and, therefore, should be invoked on the **std** object.

And finally, option C is also incorrect because it invokes **setName()** by using the class’s name, which is allowed for `static` members only.

**Problem 2.27 – A**

**Given:**

![](images/00193.jpeg)

**How many objects of the class** `ObjectsGalore` **are created in memory at run time?**

A.1

B.4

C.8

D.Compilations fails

Although Java offers several ways to create objects, for 1Z0-808 we need to remember only two: 1) with the help of the class instantiation expression that uses the keyword `new`, and 2) with a shortcut that is available for the class **String** only, that is, by using double quotes (with some unpleasant complications related to interned strings; unpleasant for us the exam takers, that is).

Fortunately, this problem does not contain **String**s, so we can with a clear conscience ask ourselves the only question that matters here: how many `new` ops does this code contain?

Just one → hence one object, and everything else is simply chaff. Do expect a similar question on the exam.

**Problem 2.28 – C**

**Given:**

![](images/00194.jpeg)

**Which statement, when inserted at line X, correctly initializes an** `ExamTaker` **instance?**

A.ExamTaker examTaker = "Bob";

B.ExamTaker examTaker = ExamTaker.new("Bob", 100, " 1Z0-808");

C.ExamTaker examTaker = new ExamTaker();

D.ExamTaker examTaker = ExamTaker("Bob", 100, " 1Z0-808");

E.None of the above

The problem tries to mislead us by providing option E. Since options B and D are clearly invalid (as B uses `new` improperly and D omits `new` altogether) and option A can’t compile, either (as the class **ExamTaker** isn't a **String**^([63](#part0016_split_007.html_id_118))), we are left with C and E.

Now, it may be tempting to select E because it looks like option C doesn’t initialize the object – after all, it doesn’t set the fields to some meaningful values, right? – but this is just an appearance. As a matter of fact, automatic initing of fields is implied by any object’s lifecycle as Java guarantees that "each class variable, instance variable, or array component is initialized with a default value when it is created" (remember [Problem 2.1](#part0016_split_007.html_id_316)?), so even an empty constructor cannot possibly mean that fields are left uninited: the no-arg **ExamTaker()** doesn’t modify their default values, that’s all.

**Problem 2.29 – C**

**Given:**

![](images/00195.jpeg)

![](images/00196.jpeg)

**Which statement is true?**

A.After line 14, three objects are eligible for garbage collection.

B.After line 14, two objects are eligible for garbage collection.

C.After line 14, one object is eligible for garbage collection.

D.After line 14, none of the objects is eligible for garbage collection.

Three `new` keywords, hence three objects. As LOCs 12 – 14 follow a sort of a zigzag pattern:

![](images/00197.jpeg)

it might be tempting to view them simply as a single stat with chained assignments:

![](images/00198.jpeg)

Yes, this would set all three references to `null` thus making all three objects eligible for garbage collection – but our code works differently. To see the proof, replace line 15 with this:

![](images/00199.jpeg)

It’s only an attempt to access `s2.name` that throws an NPE.

So, what’s going on in [Problem 2.29](#part0016_split_007.html_id_320)? Line 12 sets **s1** to point to the object referenced by **s3** (let’s call it "Carol"), then line 13 re-assigns **s3** to point to the object referenced to by **s2** ("Bob") and lastly, **s2** is set to `null`. So it’s only **s2** that is eligible for GC.

When studying for this objective, you should check your conclusions by trying to access objects’ members after the critical point to see if you got it right as an NPE would mean that this particular object is ripe for harvest.

**Problem 2.30 – D**

**Given:**

![](images/00200.jpeg)

**When the object** `ab`**, created by LOC18, becomes eligible for GC?**

A.After line 22

B.After line 23

C.After line 24

D.Never in this program

The problem seems a bit complicated with all those field assignments and setting refvars to `null`. As it is not immediately evident who depends on who and what exactly happens when someone is taken out of the equation, it is better to put the whole story into pictures.

After a lot of experiments, I have found that the following graphical representation of an object works best for me:

![](images/00201.jpeg)

The end result resembles a crude UML diagram with some modifications, and every aspect is essential: the object is rectangular, the reference var (in other words, the object’s name) is in the lower left corner, there is an open space near the top, fields are separated by lines, and the reftype-actype combo (i.e., Rt At) is at the bottom inside the object.

This little animal works equally well with both the GC- and inheritance-related questions. In cases where it is important to keep track of a `static` field’s contents, I put the field inside an oval (although, as you probably know, the UML rules prescribe to underline `static` features).

As for representing behavioral features *inside* objects, I never needed this during the entire preparation period, so it’s up to you to work out the best way to depict methods signatures…

Alright, let’s apply all these little tricks to our problem and see how they work in practice.

LOCs 17 through 19 draw the following picture (to save time on the exam, the field names are written with their initial letters only, i.e. ‘n’ stands for **name** and ‘o’ stands for **obj**):

![](images/00202.jpeg)

LOCs 20 through 22 change it into this:

![](images/00203.jpeg)

Please observe that after LOC 22 **ab** points not to **bb** (since **bb** is just a refvar) but to *the object* **bb** is referencing.

And finally, LOCs 23-24 set both **ab** and **bb** to null, so we are left with just a chain:

![](images/00204.jpeg)

The drawing clearly shows that all three objects are alive and kicking till the very end. To see if this is indeed so, we can add the following stat on line 25 and run the code:

![](images/00205.jpeg)

I met a similar question on the first sitting although there were two objects instead of three; if I remember correctly, one of them had itself as its own field; there were some other complications so I had to draw pictures. The second sitting was much easier as the question resembled the current [Problem 2.30](#part0016_split_007.html_id_321).

**Problem 2.31 – AC**

**Given:**

![](images/00206.jpeg)

**Which two modifications, made independently, enable the code to print** `Gone with the Wind, new: true, price: 9.5`**?**

A.Replace line b2 with:

`b.title = "Gone with the Wind";`
`b.secondHand = false;`
`b.price = 9.5;`

B.Replace line b2 with:

`this.title = "Gone with the Wind";`
`this.secondHand = false;`
`this.price = 9.5;`

C.Replace line b1 with:

`this.title = new String("Gone with the Wind");`
`this.secondHand = new Boolean(false);`
`this.price = new Double(9.5);`

D.Replace line bl with:

`title = "Gone with the Wind";`
`secondHand = FALSE;`
`price = 9.5f;`

E.Replace line b1 with:

`this("Gone with the Wind", false, 9.5);`

Option B is incorrect as it places all three instance vars into a static context.

Option D won’t compile, either, since it wants to assign FALSE to a primitive `boolean` var, and FALSE isn’t a valid keyword for a `boolean` literal value. The following modification would have worked because **Boolean** unboxes:

![](images/00207.jpeg)

As for option E, it too throws a comperr because the class **Book** didn’t define a corresponding three-arg constructor.

**Problem 2.32 – B**

**Given:**

![](images/00208.jpeg)

**What is the result?**

A.true false false

B.true true false

C.false false false

D.An IllegalArgumentException is thrown at run time

E.A NullPointerException is thrown at run time

This problem tests if you know that the class **Boolean** has a case-insensitive constructor that accepts a **String** and allocates a **Boolean** object representing the value `true` if the input string reads "true" in any spelling, and a **Boolean** that represents `false` otherwise (like in case of "1", `null`, etc.) Same goes for the **parseBoolean(**String str**)** method.

What’s more, similarly to all other wrapper classes, **Boolean** has another constructor that accepts an underlying primitive, that is a `boolean`.

**Problem 2.33 – E**

**Given:**

![](images/00209.jpeg)

**What is the result?**

A.input: 0123, output: 0123

B.input: 2013, output: 0123

C.input: 2013, output: 83

D.Wrong argument!

E.None of the above

This problem wants to trick you by betting on two things: that you remember [Problem 1.1](#part0016_split_007.html_id_316)all too well and are going to follow the previous solution’s steps purely mechanically (thus arriving at option B by simply swapping the values), or that, having noticed just how mighty out of place looks 83, you may start believing that the whole point of the exercise concerns octal notation.

Unfortunately, this is not the case as octal notation isn’t even on the exam. The trap is built into the **Integer.parseInt()** method, of all things. Let’s take another look at the documentation that comes with the core Java API:

![](images/00210.jpeg)

*Decimal*. Not octal. So the leading zero gets stripped off and the code prints:

input: 2013, output: 123

Which, of course, is option E.

Admittedly, this problem is way too tricky for the OCA exam, far-fetched and even insulting. By including it into this book, I wanted to remind you that there is a non-zero probability that the exam just might attempt to take an advantage of the way we tend to operate: when two things strongly resemble each another, we start thinking along similar lines. The exam will never test you on precisely same objective more than once, so stay focused and don’t take anything for granted.

* * *

^([51](#part0016_split_000.html_id_93)) I’m saying this simply because Java recognizes almost entire Unicode charset as valid characters for identifiers; for example, £var or ¥var are OK, too; they’re just not on the exam, that’s all.

^([52](#part0016_split_000.html_id_95)) The use of underscores is better to be left to declarations only: there are cases when underscores are simply not allowed (for example, the **Integer. decode()** method does not accept underscores between digits).

^([53](#part0016_split_000.html_id_99)) [https://www.securecoding.cert.org/confluence/display/java/NUM13-J.+Avoid+loss+of+precision+when+converting+primitive+integers+to+floating-point](https://www.securecoding.cert.org/confluence/display/java/NUM13-J.+Avoid+loss+of+precision+when+converting+primitive+integers+to+floating-point)

^([54](#part0016_split_000.html_id_97)) It is not a two’s-compliment integral type, though…

^([55](#part0016_split_002.html_id_101)) The use of access modifiers is covered by Exam Objective 6.5, "Apply encapsulation principles to a class".

^([56](#part0016_split_003.html_id_105)) 1) `new`, 2) clone(), 3) Class.forName(), 4) newInstance(), 5) by deserialization, 6) thru the class **Constructor**.

^([57](#part0016_split_003.html_id_103)) Although it does look like the LDT-related classes don’t use `new()`, they simply define no `public` constructors; that’s why we need to use `static` methods to create, say, a **LocalDate** object by calling **LocalDate.of()**, which invokes **create()** who then calls `private` **LocalDate(**int year, int month, int dayOfMonth**)** constructor, and so on.

^([58](#part0016_split_007.html_id_107)) This subject has been already addressed in [Table 1](#part0014.html_id_313) ([Chapter II](#part0014.html_page_38).0, *Opening Remarks*). Nevertheless, the concept of abstract variables is theoretically solid (refer, for example, to *Deductive Verification of Object-Oriented Software* by Benjamin Weiß, p.6).

^([59](#part0016_split_007.html_id_111)) [http://www.oracle.com/technetwork/java/codeconvtoc-136057.html](http://www.oracle.com/technetwork/java/codeconvtoc-136057.html)

^([60](#part0016_split_007.html_id_109)) Feeling tired? Take a coffee break and re-motivate yourself by reading *Imprisonment for Irresponsible Coding* by Yegor Bugayenko, [http://www.yegor256.com/2015/11/24/imprisonment-for-irresponsible-coding.html](http://www.yegor256.com/2015/11/24/imprisonment-for-irresponsible-coding.html)

^([61](#part0016_split_007.html_id_113)) *Data Structures and Algorithms in Java* by Michael T. Goodrich, Roberto Tamassia and Michael H. Goldwasser, 6th ed, 2014, p.7, or *Thinking in Java* by Bruce Eckel, the chapter "Everything is an Object".

^([62](#part0016_split_007.html_id_115)) Do remember that parsing methods in all wrapper classes produce underlying primitives.

^([63](#part0016_split_007.html_id_117)) In fact, it cannot extend **String** even if it wanted to. You will – hopefully – forgive me whenever I annoy you by repeating that the class **String** is not only immutable but also `final` as remembering these things is indeed important for the exam.

![](images/00211.jpeg)

**The 1Z0-808 objectives within this group:**

| [3.1](#part0017_split_000.html_c3.1) | Use Java operators, including parentheses to override operator precedence |
| [3.2](#part0017_split_001.html_c3.2) | Test equality between **String**s and other objects using `==` and **equals()** |
| [3.3](#part0017_split_002.html_c3.3) | Create `if` and `if-else` and ternary constructs |
| [3.4](#part0017_split_003.html_c3.4) | Use a `switch` statement |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

3.1Use Java operators, including parentheses to override operator precedence:

**General Remarks:**

![](images/00012.jpeg)Naturally, all objectives are equally important since we need to pass the exam, but this one is simply indispensable because at least one of its aspects will appear in every question that contains sample code.

![](images/00012.jpeg)A large number of questions on the exam concern the misuse of a particular operator leading to a compile-time error. Quite often these errors are caused by inappropriate data types which the operator accepts as its operands.

![](images/00012.jpeg)Typical examples are control structures such as decision-making constructs, including `if-then`^([64](#part0017_split_005.html_id_120))`-(else)` and `switch` statements, as well as repetition handlers (`for`, enhanced `for`, `do-while`, and `while`). It is important to remember that, unlike most of these constructs, which evaluate `boolean` expressions, the `switch` statement is the only one that supports a variety of data types.

![](images/00012.jpeg)Nested stats can be particularly tough, especially when they are used together with labels and/or `break` and `continue`. In fact, the exam pays special attention to such cases by including separate objectives to cover nuances.

![](images/00012.jpeg)Some operators can be used only with numeric primitives, some apply only to `boolean` values, and some require objects only.

![](images/00012.jpeg)Many Java operators are unary, meaning they accept a single operand, but the number of expressions they evaluate can often be greater than one. The order of evaluation plays therefore a crucial role. Spare no efforts memorizing at least [Table 2.2](#part0014.html_id_314) (ref.to [Chapter II.0, *Opening Remarks*](#part0014.html_page_38)).

![](images/00012.jpeg)Parentheses are used to override the default order of precedence. The exam includes at least two questions that will test you on this aspect in different scenarios.

**Java Operators At a Glance:**

![](images/00012.jpeg)The 1Z0-808 exam covers assignment, arithmetic, relational, and logical operators.

![](images/00012.jpeg)Assignment operators:

![](images/00059.jpeg)The assignment operators store, or assign, a value into a variable. The left-hand operand must evaluate to an appropriate local variable, array element, or a field. The right-hand side can be any value of a type compatible with the variable.

![](images/00059.jpeg)Unlike all other binary operators, the assops are right-associative, which means that the chained assignments in `a=b=c` are performed in this fashion: `a=(b=c)`.

![](images/00059.jpeg)The compound assops such as `a`+=*smth* and so on are equivalent to `a=a+`*smth*, etc. In other words, += can be interpreted as ‘first add and then assign’.

![](images/00059.jpeg)EXTRA: The assignment is actually the *side effect* of the assignment expression evaluation^([65](#part0017_split_005.html_id_122)). Remembering this helps see that the following class does compile:

![](images/00212.jpeg)

Look at the assop this way: when a value gets assigned to a var, the process doesn’t stop at the variable; the value kind of ‘bleeds’ to the left thus becoming available to whatever sits further to the left of the var. The fact that some variable (like **boo** or **b** in the above example) gets assigned a value along the way is simply a side effect. Now it becomes clear that, as far as the ternop is concerned, **boo** = `true` is equivalent to `true`, and **b** = 10 also produces a value that can be assigned to **a**.

![](images/00012.jpeg)Arithmetic operators:

![](images/00059.jpeg)Arithmetic operators do not accept the `boolean` data type. An attempt to do so results in a comperr.

![](images/00059.jpeg)++ and -- are unary increment and decrement operators, which can be used in prefix or postfix notation.

![](images/00059.jpeg)In prefix notation, the value of the variable increments/decrements just before the variable is used.

![](images/00059.jpeg)The exam is particularly keen on testing us on postfix notation, wherein the value of the variable increments/decrements just after the variable is used.

![](images/00059.jpeg)Increment and decrement operators can be used only with variables and not with constants or expressions:

![](images/00213.jpeg)

![](images/00059.jpeg)Unary operators have a higher precedence than multiplication and addition operators.

![](images/00059.jpeg)EXTRA: There is a popular misconception that the % operator produces a reminder. Actually, what it computes is this:

![](images/00214.jpeg)

So, we get the reminder only if both operands are positive.

When it comes to %: The first operand’s sign is the sign of the result.

![](images/00059.jpeg)EXTRA: JVM generates no **Throwable** on arithmetic overflow or underflow^([66](#part0017_split_005.html_id_126)).

![](images/00012.jpeg)Relational operators:

![](images/00059.jpeg)Relational operators always produce a `boolean` value.

![](images/00059.jpeg)Relational operators are used to compare values for equality (`==`) and nonequality (`!=`). To determine whether two numeric values are greater or less than each other, we use `>`, `>=`, `<`, and `<=`.

![](images/00059.jpeg)It’s a comperr to attempt to compare incompatible types. For example, an `int`, a `char`, or a floating-point value can’t be compared with a `boolean`. On the other hand, we may compare an `int` and a `char` since `char` behaves almost as an unsigned `short`.

![](images/00059.jpeg)The operators ‘equal to’ (`==`) and ‘not equal to’ (`!=`) can be used with any compatible primitive types.

![](images/00059.jpeg)`==` returns `true` if the primitive values being compared are equal.

![](images/00059.jpeg)`!=` returns `true` if the primitive values being compared are not equal.

![](images/00012.jpeg)Logical operators:

![](images/00059.jpeg)Application of a logical operator always results in a `boolean` value.

![](images/00059.jpeg)Logical operators are used in the decision-making structures to determine whether a set of conditions is `true` or `false`.

![](images/00059.jpeg)Logical AND (`&&`) evaluates to `true` iff^([67](#part0017_split_005.html_id_124)) all operands are `true`, and `false` otherwise.

![](images/00059.jpeg)Logical OR (`||`) evaluates to `true` if any of the operands is `true`.

![](images/00059.jpeg)Logical negation (`!`) inverts the `boolean` value.

![](images/00059.jpeg)The logical operators `&&` and `||` are also called short-circuit operators. If these operators can determine the output of the expression with the evaluation of the first operand, all subsequent operands are not evaluated.

EXTRA: De Morgan’s Laws may come in handy, as well:

![](images/00215.jpeg)

![](images/00012.jpeg)Other useful rules to remember:

![](images/00059.jpeg)`null` is the only literal value that can be assigned to a reference data type, such as **String**, etc. On the other hand, `null` cannot be assigned to a primitive var.

![](images/00059.jpeg)If a **String** is `null` and then gets used with a + op, the result will be "null*smth*".

![](images/00059.jpeg)Arithmetic ops turn everything into `int`s unless an operand is `long`, `float` or `double` (or a corresponding Wrapper, which unboxes first and then this rule will be applied again). (**other wording**: All operands of type `byte`, `short` or `char` are promoted AT LEAST to `int` before performing mathematical operations. If one of the operands is larger than `int` then the other one is promoted to the same type.)

Illustration:

![](images/00216.jpeg)

![](images/00059.jpeg)There is a question on the exam that asks – among other things – if Java allows operator overloading. The correct answer is ‘No, it doesn’t’. What’s interesting, Java does use something that looks operator overloading when it comes to the + op: it is overloaded for **String**.^([68](#part0017_split_005.html_id_128))

Question: why this throws comperrs?

![](images/00217.jpeg)

Let’s apply the abovementioned rule: the + operator is overloaded for the cases where at least one of its operands is a **String**. So `null +'a'` will not compile because neither of the operands is a **String**.

On the other hand, `str += 'a'` works because it translates to `str = str + 'a'` which means one of the operands *is* a **String**.

Although the fourth LOC can indeed be re-written as `str=str+null+'a'` (which doesn’t generate a comperr), the compiler first evaluates – and chokes on – the faulty `null + 'a'`. Expanding the expression to `str = str +` *whatever* comes later.

![](images/00059.jpeg)It is important to remember that the types of the operands are determined at compile time. The third LOC in the next example won’t compile even though the run-time type of the object referred to by **sobj** is **String**:

![](images/00218.jpeg)

![](images/00059.jpeg)An empty statement, represented by the semicolon, can appear in rather unexpected places making the code seem uncompilable while, in fact, it is perfectly legit:

![](images/00219.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 3.1Given the following code fragment:**

![](images/00220.jpeg)

**What is the result?**

A.The answer to Life, the Universe and everything is 42

B.The answer to Life, the Universe and everything is 43

C.The answer to Life, the Universe and everything is 44

D.Compilation fails

**Problem 3.2Given:**

![](images/00221.jpeg)

**What is the result?**

A.1 + 2 = 34
1 + 2 = 7
1 + 2 = 7

B.1 + 2 = 7
1 + 2 = 34
1 + 2 = 7

C.3 = 34
3 = 7
3 = 7

D.1 + 2 = 34
1 + 2 = 34
1 + 2 = 7

**Problem 3.3Given the code fragment:**

![](images/00222.jpeg)

**What is the result?**

A.27!
212!

B.234!
212!

C.9!
14!

D.54!
14!

D.Compilation fails

**Problem 3.4Given the code fragment:**

![](images/00223.jpeg)

**What is the result?**

A.-1 0

B.-1 -2

C.0 1

D.1 0

**Problem 3.5Given the fragment:**

![](images/00224.jpeg)

**What is the result?**

A.40 40

B.39 40

C.38 40

D.Compilations fails

**Problem 3.6Given:**

![](images/00225.jpeg)

**What is the result?**

A.bool1:true, bool2:false

B.bool1:true, bool2:true

C.bool1:false, bool2:true

D.bool1:false, bool2:false

**Problem 3.7Given:**

![](images/00226.jpeg)

**Which one is false?**

A.The code prints true

B.The code prints false

**Problem 3.8Given:**

![](images/00227.jpeg)

**How many statements fail compilation?**

A.One

B.Two

C.Three

D.None

**Problem 3.9**

The very first exercise in *The Art of Computer Programming*, Vol.1, "Fundamental Algorithms" by Donald Knuth^([69](#part0017_split_005.html_id_130)) reminds the reader that

…the text showed how to interchange the values of variables *m* and *n*, using the replacement notation, by setting *t* ← *m*, *m* ← *n*, *n* ← *t*.

You decided to beat Knuth himself at his game by devising a way to switch any two integer variables *without* using a temporal storage, and this is what you came up with:

![](images/00228.jpeg)

**Suppose, we declare**

![](images/00229.jpeg)

**What will happen?**

A.The algorithm will continue to work correctly

B.Both a and b will flip their signs

C.Compilation will fail

D.The code will throw an ArithmeticException

3.2Test equality between **String**s and other objects using == and **equals()**:

![](images/00012.jpeg)While `==` between two comparable primitive values checks whether they are equal, the very same operator between two reference vars checks whether these references point to the same object.

![](images/00012.jpeg)The method **equals()** checks the equality of objects depending on its implementation by the particular data type it is being called on.

![](images/00012.jpeg)For example, calling `==` on **String**s checks if they point to the same object within the common pool of strings while calling **equals()** on the same objects will check whether the sequence of characters is the same.

![](images/00012.jpeg)On the other hand, since the class **StringBuilder** – unlike the class **String** – does not override **Object**’s **equals()** with its own implementation, calling **equals()** on **StringBuilder** objects is the same as using the `==` operator: it will check if they are pointing to the same object rather than peek at the values inside.

| **Corollary**: | The easiest way to compare the *contents* rather than references of two **StringBuilder** objects, is to call **equals()** on the values returned by the **toString()** method. |

![](images/00012.jpeg)The **String**s created with double quotes get interned into a common pool unlike the **String**s computed at run time or created with the keyword `new`.

Expressing the same rules in code:

![](images/00230.jpeg)

![](images/00012.jpeg)Other useful rules to remember:

![](images/00059.jpeg)Even though integral and floating-point primitives are not always assignable to each other (thus requiring explicit casts), they may be freely compared with `==`:

![](images/00231.jpeg)

![](images/00059.jpeg)`null == null` returns `true`.

| ◼ | Question: | Will `==` compile between ‘covariant’ operands? |
|  | Answer: | Yes, because there exists an IS-A relationship. An attempt to use `==` between unrelated reference types leads to a comperr: |

![](images/00232.jpeg)

| **Simple corollary:** | `==` between different Wrappers throws a comperr. It’s only **equals()** that behaves itself. |

EXTRA: It may look as if there’s a way to trick the compiler into comparing two unrelated data types with the ‘double equals’ operator; this, however, is just an appearance since both objects are of the same reftype:

![](images/00233.jpeg)

or even bolder and simpler:

![](images/00234.jpeg)

→ Reminder: the compiler always looks at reftypes and never cares about actypes.

![](images/00059.jpeg)EXTRA: It is common to compare the values of the *instance* vars when testing two objects for equality because it is the instance vars that are used to store the state of a particular object at a particular point in time.

![](images/00059.jpeg)EXTRA: **equals**(`null`) returns `false` on any object.

![](images/00059.jpeg)EXTRA: The method **equals()** defined for a user data type should not modify any of the instance vars passed to it as its arguments; failure to do so will violate the contract for the method **equals()** defined by the Java API.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 3.10Given:**

![](images/00235.jpeg)

**What is the result?**

A.Same 1

B.Same 2

C.Different

D.A NullPointerException is thrown at run time

**Problem 3.11Given:**

![](images/00236.jpeg)

**Which code fragment, when inserted at line 7, enables the code to print** `true`**?**

A.String str2 = str1;

B.String str2 = new String (str1);

C.String str2 = sb1.toString();

D.String str2 = " 1Z0-808";

**Problem 3.12Given:**

![](images/00237.jpeg)

**What is the result?**

A.Same
More of the same

B.More of the same

C.Same

D.Nothing prints

**Problem 3.13Given the code fragment:**

![](images/00238.jpeg)

**What is the proper way to check whether str1 and str2 have the same contents?**

A.if (str1 == str2) { /* some code */ }

B.if (str1.equals(str2)) { /* some code */ }

C.if (str1 = str2) { /* some code */ }

D.if (str1.toString() == str2.toString()) { /* some code */ }

**Problem 3.14Given the following main method:**

![](images/00239.jpeg)

**What is the result?**

A.Same
More of the same

B.More of the same

C.Same

D.Nothing prints

E.Compilation fails

**Problem 3.15Given:**

![](images/00240.jpeg)

**What is the result?**

A.Identical
Dissimilar

B.Dissimilar
Identical

C.Identical
Identical

D.Dissimilar
Dissimilar

**Problem 3.16Given:**

![](images/00241.jpeg)

**What is the result?**

A.Identical
Dissimilar

B.Dissimilar
Identical

C.Identical
Identical

D.Dissimilar
Dissimilar

3.3Create if and if-else and ternary constructs:

![](images/00012.jpeg)if and if-else constructs:

![](images/00059.jpeg)`if`’s logic is based on the result of a condition, which should evaluate to a `boolean` or **Boolean** value.

![](images/00059.jpeg)`if` constructs can be nested; theoretically, the depth is unlimited.

![](images/00059.jpeg)The `else` part isn’t required.

![](images/00059.jpeg)Braces {} are not mandatory → watch out! only the nearest stat forms therefore a part of the `if` construct.

![](images/00059.jpeg)`if`’s expression doesn’t accept a var declaration; it will, however, accept an assignment but only when the value is a `boolean` (or **Boolean**):

![](images/00242.jpeg)

![](images/00059.jpeg)EXTRA: `if`’s body accepts a labeled `break`:

![](images/00243.jpeg)

![](images/00059.jpeg)EXTRA: `if(false)` doesn’t flag a comperr despite the fact that the nearest stat becomes unreachable.

![](images/00059.jpeg)EXTRA: Neither `if`- nor `else`-branch accepts a variable declaration:

![](images/00244.jpeg)

![](images/00012.jpeg)Ternary constructs:

![](images/00059.jpeg)Ternary op does not require that its terms must be compile-time constant values.

![](images/00059.jpeg)When the ternop is used on the right-hand side of an assop, its (the ternop’s) terms must 1) match or be numerically ‘promotable’, and 2) be compatible with the assop.

![](images/00059.jpeg)Both terms of the ternary op should return or evaluate to something. In the following example the code compiles because **test()** returns an `int`, `--res` evaluates to a value, and `for` is provided with a `boolean`:

![](images/00245.jpeg)

| **Simple corollary**: | It’s a comperr if either term consists of a `void` method such as **System.out.println()**, etc.: |

![](images/00246.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 3.17Given:**

![](images/00247.jpeg)

**What is the result?**

A.16

B.17

C.18

D.23

E.Compilation fails

**Problem 3.18Given the following code fragment:**

As you are planning to sell your Android-based games, you need to calculate discount rates for bulk purchases using the following criteria:

–if someone buys three or four of your apps, you are willing to offer a 20% discount;

–buying five or more apps makes your clients eligible for a 50% discount;

–the miserly types who refuse to spend their ill-gotten money on more than two of your amazing games, will get no discount at all.

The following **main()** method should take care of the task:

![](images/00248.jpeg)

**Which two code fragments can be independently inserted at line X to meet the above criteria?**

![](images/00249.jpeg)

**Problem 3.19Given the following code fragment:**

![](images/00250.jpeg)

**What is the result?**

A.My plaid jackets quit.

B.My six before quit.

C.six before she quit.

D.six dozen before quit.

**Problem 3.20Given:**

![](images/00251.jpeg)

**What is the result?**

A.valid

B.not valid

C.Compilation fails

D.An IllegalArgumentException is thrown

**Problem 3.21Given:**

![](images/00252.jpeg)

**What is the result?**

A.wow!

B.zer!

C.wowzer!

D.Compilation fails

**Problem 3.22Given:**

![](images/00253.jpeg)

**What is the result?**

A.It works!

B.!

C.Compilation fails

D.An exception is thrown at run time

**Problem 3.23Given:**

![](images/00254.jpeg)

**What is the result?**

A.How many? 1

B.How many? 100

C.How many? 2

D.How many? 101

E.Compilation fails

**Problem 3.24Given the code fragment:**

![](images/00255.jpeg)

**And the following decision-making construct:**

![](images/00256.jpeg)

**What is the result?**

A.1

B.3

C.Compilation fails

D.An ArrayIndexOutOfBoundsException is thrown at run time

3.4Use a switch statement:

![](images/00012.jpeg)`switch` expression accepts all primitives and their wrappers (except `boolean`, `long`, `float`, and `double` with their corresponding wrappers) + **String** + `enum`s^([70](#part0017_split_005.html_id_306)).

![](images/00012.jpeg)Every `case` constant expression in a `switch` block must be assignable to the type of `switch` expression.

→ The `switch` expression’s type must be wide enough to hold all `case` values; the first `case` in the following example will not compile because 128 cannot be assigned to **b**, which can only hold values from -128 to 127 inclusive:

![](images/00257.jpeg)

| **Corollary**: | if `switch` was promised, say, a `byte`, it will also accept certain `char`s (such as ‘a’ since the numerical value of ‘a’ (namely, 97) is within `byte`’s range.) Same goes for a `short`. |

Look at it this way: the flow isn’t from top to bottom; just the opposite; it’s not that `byte` can fit inside 128: it’s 128 that can’t fit inside `byte`.

Imagine that `switch` is a box with an opening on top (`switch` expression); we need to take an appropriate `case` value out of the box to perform our computations – but we can’t do it if the value is larger than the opening: it simply won’t get through! (Mental pic: a trapped monkey with its paw in a jar).

![](images/00012.jpeg)No two identical `case` values are allowed in a `switch`.

→ pay attention to both literals and vars used as `case` values. Watch out for underscores in `switch`’s `case`s that use integral types such as `int`, etc.; there can be identical twins lurking.

![](images/00012.jpeg)EXTRA: The `case` value can’t be the literal value `null`.

![](images/00012.jpeg)EXTRA: The `case` value can define expressions that use literal values such as 1 + 2.

![](images/00012.jpeg)`switch` requires curly braces but its body can be empty.

Alright, what follows isn’t exactly about `switch` *per se* but we still need to review the rules that govern the use of braces anyway so let’s do it right now:

The curly braces {} are required around method bodies, `switch` blocks, TCF constructs and lambdas with `return` and/or multiple stats; not required for `if`s and loops (be careful with `do-while`, though; it will choke on more than one stat w/o braces).

What’s more, the TCF constructs are treated as a single statement, hence whatever surrounds them might not need braces, either:

![](images/00258.jpeg)

![](images/00012.jpeg)The `switch` expression does not accept declarations.

![](images/00012.jpeg)The `switch`’s `case`s require constant expressions (in other words, they must be constant at run time)^([71](#part0017_split_005.html_id_134)).

| **Corollary**: | If a **case** expression uses a var, this var must be a **final primitive** because although `switch` does accept some wrappers, its **case** expressions must generate a constant value – and **wrappers aren’t constants** (**not even final static ones**!)^([72](#part0017_split_005.html_id_132)) |

![](images/00012.jpeg)The `default` section can be placed anywhere.

![](images/00012.jpeg)Watch out for falling through due to missing `break`s.

![](images/00012.jpeg)EXTRA: Like any other block, the `switch` block can be labeled:

![](images/00259.jpeg)

![](images/00012.jpeg)EXTRA: It is possible to initialize local vars in `switch`’s `default` section if this `default` is always accessible (like in the following example where the falling-through makes `default` reachable thanks to missing `break`s):

![](images/00260.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 3.25Given the code snippet:**

![](images/00261.jpeg)

**Which option will allow the code snippet print** `True Blue`**?**

A.Remove the default section

B.Replace line 7 with `String bool = "true";` and replace line 9 with `case "true":`

C.Remove the `break;` statement at line 11

D.Replace line 7 with `boolean bool = 1;` and replace line 9 with `case 1:`

**Problem 3.26Given the code snippet:**

![](images/00262.jpeg)

**Which three statements can be independently inserted at line X to enable the code to print** `Zero`**?**

A.short a = 0;

B.Integer a = 0;

C.Double a = 0;

D.String a = "0";

E.Byte a = new Byte("0");

F.Long a = 0;

**Problem 3.27Given the code snippet:**

![](images/00263.jpeg)

**What is the result?**

A.Compilation error on line 1

B.Compilation error on line 2

C.The code prints Not divisible by 4

D.The code prints Divisible by 4

**Problem 3.28Given:**

![](images/00264.jpeg)

**What is the result?**

A.Hi Alice!

B.Hi Alice!
Hi Bob!

C.Hi Alice!
Hi Bob!
Hi Carol!

C.Hi Alice!
Hi Bob!
Hi Carol!
Hello stranger!

**Problem 3.29Given:**

![](images/00265.jpeg)

**Which two modifications, made independently, enable the code to compile and run?**

A.Adding a `break` statement after each print statement

B.Adding a default section

C.Removing the double quotes from each `case` label

D.Changing the type of the variable **day** to **String**

E.Arranging the `case` labels in ascending order

**Problem 3.30Given:**

![](images/00266.jpeg)

**What is the result?**

A.String !

B.String!

C.Compilation fails on line 1

D.Compilation fails on lines 2 and 3

**Problem 3.31Given:**

![](images/00267.jpeg)

**Which statement about this code is true?**

A.Line 1 throws a comperr

B.Line 2 throws a comperr

C.Line 3 throws a comperr

D.There is nothing wrong with the code

**Problem 3.32Given:**

![](images/00268.jpeg)

**Which two LOCs fail compilation?**

A.Line 1

B.Line 2

C.Line 3

D.Line 4

E.Line 5

F.Line 6

**Problem 3.33Given:**

![](images/00269.jpeg)

**Which statement about the code is true?**

A.The code compiles and prints Java

B.The code throws a comperr on line 1

C.The code throws a comperr on line 2

A.The code throws a RuntimeException

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 3.1 – B**

**Given the following code fragment:**

![](images/00270.jpeg)

**What is the result?**

A.The answer to Life, the Universe and everything is 42

B.The answer to Life, the Universe and everything is 43

C.The answer to Life, the Universe and everything is 44

D.Compilation fails.

Since the postfix notation means that the variable is used first and only then increments, the comparison between **a** and 42 on line 1 yields `true` and the control gets transferred to the `if`-branch rather than `else`-branch. By this moment, however, the value of **a** has been already incremented.

Mastering the postfix notation should be one of your top priorities since it is widely used on the exam. Let’s have a few more examples to see how it works.

Example 1:

![](images/00271.jpeg)

Lines 7 and 8 are easy. Line 2 mimics line 7 in its logic, and as for line 3, it uses the local var **x** twice, so the value it returns has been already incremented.

Example 2:

![](images/00272.jpeg)

What is the result?

A.-1

B.0

C.1

As I’ve got no control over what you are doing, there is no stopping you from reading any further without solving Example 2 first. If you’re dead set on ruining everything, just go ahead; after all, passive learning is also a way to pass time. It’s just not the way to pass an exam.

Alright, let’s crack the sucker together:

The expressions involving arithmetic ops are evaluated left to right → so, how many times the var **a** gets used? → twice → and since by the second time the var’s value has been already incremented, the answer is 0 - 1.

And now for the big finale: when we uncomment the last printing stat, it’ll output… what?^([73](#part0017_split_005.html_id_136))

**Problem 3.2 – D**

**Given:**

![](images/00273.jpeg)

**What is the result?**

A.1 + 2 = 34
1 + 2 = 7
1 + 2 = 7

B.1 + 2 = 7
1 + 2 = 34
1 + 2 = 7

C.3 = 34
3 = 7
3 = 7

D.1 + 2 = 34
1 + 2 = 34
1 + 2 = 7

I had two different questions to this tune on different sittings; this one combines them all.

As we already know that the + op in Java is overloaded for **String**, here are the simplest formulas to remember:

![](images/00012.jpeg)**String** with `+` (including `+=`) will take anything in any order; for example, `str += 'a'` or `str += false` or `str +=1` are all valid as well as `str = 'a' + str; str = 'b'+63+"a", str = null + str,` and so on.

![](images/00012.jpeg)If the expression contains a **String** that is followed by a +, whatever is to the right of the **String** becomes a string of **Strings**. Watch out for parentheses, though.

**Problem 3.3 – C**

**Given the code fragment:**

![](images/00274.jpeg)

**What is the result?**

A.27!
212!

B.234!
212!

C.9!
14!

D.54!
14!

D.Compilation fails

The expression on the left-hand side of the **String** is evaluated first, then the **String** "!" makes the end result a **String**, too^([74](#part0017_split_005.html_id_138)).

**Problem 3.4 – A**

**Given the code fragment:**

![](images/00275.jpeg)

**What is the result?**

A.-1 0

B.-1 -2

C.0 1

D.1 0

The whole chain is evaluated this way:

![](images/00276.jpeg)

**Problem 3.5 – A**

**Given the fragment:**

![](images/00277.jpeg)

**What is the result?**

A.40 40

B.39 40

C.38 40

D.Compilations fails

There’s nothing illegal with using arithmetic ops on Wrappers: they simply unbox as needed and then autobox again, therefore the code compiles and option D is incorrect.

Line 1 decreases 42 by one resulting in **aa** = 41. Line 2 decrements the value further, combines it with the **String** " ", then prints 40 followed by a space. Line 3 just outputs the same value of **aa**.

**Problem 3.6 – A**

**Given:**

![](images/00278.jpeg)

**What is the result?**

A.bool1:true, bool2:false

B.bool1:true, bool2:true

C.bool1:false, bool2:true

D.bool1:false, bool2:false

Line 1 uses numerical promotions: first the `double` 1.5 is explicitly cast to the `float` 1.5, then this `float` is promoted to `double` again in order to compare these two values with the ‘not equal’ op thus resulting in the boolean `false`, which means `||` doesn’t short-circuit; then the expression `bool1 = true` gets evaluated thus assigning true to **bool1** along the way.

Line 2 evaluates ++**a** == **a**++ resulting in `true` (and making **a** equal to 21 at the same time), so the short-circuiting AND still needs to evaluate !**bool1** thus resulting in `false`.

**Problem 3.7 – A**

**Given:**

![](images/00279.jpeg)

**Which one is false?**

A.The code prints true

B.The code prints false

Sometimes it is easier to apply De Morgan’s Laws than evaluate each operand in a relational expression. Since NEG(A OR B) 􀅁 ≡ NEG(A) AND NEG(B), the stat on line 1 can be rewritten as

![](images/00280.jpeg)

To simplify it even more, we can mentally apply the negation operator:

![](images/00281.jpeg)

**Problem 3.8 – A**

**Given:**

![](images/00282.jpeg)

**How many statements fail compilation?**

A.One

B.Two

C.Three

D.None

To crack this one, we need to recall that comparison ops have lower precedence than arithmetic ops. This is why line 1 is valid while line 2 fails compilation because it’s illegal to add numeric types to a `boolean`.

The first "" in line 3 turns the `boolean` into a **String**, and then the same principle is applied once again on line 4 after the evaluation of the operands of the comparison op `==`.

**Problem 3.9 – A**

The very first exercise in *The Art of Computer Programming*, Vol.1, "Fundamental Algorithms" by Donald Knuth reminds the reader that

…the text showed how to interchange the values of variables *m* and *n*, using the replacement notation, by setting *t* ← *m*, *m* ← *n*, *n* ← *t*.

You decided to beat Knuth himself at his game by devising a way to switch any two integer variables *without* using a temporal storage, and this is what you came up with:

![](images/00283.jpeg)

**Suppose, we declare**

![](images/00284.jpeg)

**What will happen?**

A.The algorithm will continue to work correctly

B.Both **a** and **b** will flip their signs

C.Compilation will fail

D.The code will throw an ArithmeticException

Java has neither overflows nor underflows. If a value overflows, it goes back to the MIN_VALUE and continues from there, whereas if it underflows, it jumps back to the MAX_VALUE and continues from there.

The documentation for the class **Math** advises that

The best practice is to choose the primitive type and algorithm to avoid overflow. In cases where the size is int or long and overflow errors need to be detected, the methods addExact, subtractExact, multiplyExact, and toIntExact throw an ArithmeticException when the results overflow.

**java.math.BigInteger** also throws **ArithmeticException** when the result is out of the supported range of -2^(Integer.MAX_VALUE) (exclusive) to +2^(Integer.MAX_VALUE) (exclusive).

**Problem 3.10 – B**

**Given:**

![](images/00285.jpeg)

**What is the result?**

A.Same 1

B.Same 2

C.Different

D.A NullPointerException is thrown at run time

**Object**’s **equals()** is defined simply as `==`, and since the class **StringBuilder** does not override this method, we get `if(false)` on line 2, thus transferring control to the `else-if` branch.

As line 3 uses the **String**’s **equals()**, we get `if(true)` because both objects contain identical character sequences.

**Problem 3.11 – A**

**Given:**

![](images/00286.jpeg)

**Which code fragment, when inserted at line 7, enables the code to print** `true`**?**

A.String str2 = str1;

B.String str2 = new String (str1);

C.String str2 = sb1.toString();

D.String str2 = "1Z0-808";

As **sb1** and **str1** are different reference types, comparing them with `==` would be illegal, that’s why we need either another **String** object or another reference of type **String**, which is exactly those four options do. Further, to make the code print true, both references must point to the same object – and option A satisfies the requirement.

This problem demonstrates another practical principle of how to work during the exam: as soon as you find the answer you’re looking for, move to the next question without even bothering with other options. You’ll check them all during the complete Review.

**Problem 3.12 – B**

**Given:**

![](images/00287.jpeg)

**What is the result?**

A.Same
More of the same

B.More of the same

C.Same

D.Nothing prints

Unlike **String** literals surrounded with double quotes, the **String** objects returned by methods or created with the keyword `new` are not interned, which means we are dealing here with two distinct objects.

**Problem 3.13 – B**

**Given the code fragment:**

![](images/00288.jpeg)

**What is the proper way to check whether str1 and str2 have the same contents?**

A.if (str1 == str2) { /* some code */ }

B.if (str1.equals(str2)) { /* some code */ }

C.if (str1 = str2) { /* some code */ }

D.if (str1.toString() == str2.toString()) { /* some code */ }

The same problem, only paraphrased. Option A evaluates to `false` regardless of the contents while option C doesn’t even compile because the assop produces a **String** and not a `boolean`. As for option D, it also evaluates to `false` regardless of the contents since the **String**s returned by methods don’t get interned, so we would be trying to compare two distinct objects.

**Problem 3.14 – D**

**Given the following main method:**

![](images/00289.jpeg)

**What is the result?**

A.Same
More of the same

B.More of the same

C.Same

D.Nothing prints

E.Compilation fails

Since the class **StringBuilder** doesn’t override **Object**’s **equals()**, the **StringBuilder** objects must be first converted to **Strings**. As **sb.toString()** returns an object that is not kept in the pool, the first printing stat never fires. After the method **append()** returns "Inequalitymatters" (without a space), the second printing stat doesn’t get executed, either.

**Problem 3.15 – D**

**Given:**

![](images/00290.jpeg)

![](images/00291.jpeg)

**What is the result?**

A.Identical
Dissimilar

B.Dissimilar
Identical

C.Identical
Identical

D.Dissimilar
Dissimilar

This is an illustration of the fact that user-defined data types should provide their own implementation of **equals()**.

**Problem 3.16 – D**

**Given:**

![](images/00292.jpeg)

**What is the result?**

A.Identical
Dissimilar

B.Dissimilar
Identical

C.Identical
Identical

D.Dissimilar
Dissimilar

This problem tests your knowledge of **equals()**’s signature: the method defined by **Twins** does not override the **Object**’s **equals()** who takes an **Object** as its argument. A more proper way to override it should have been something like this (gives option B):

![](images/00293.jpeg)

**Problem 3.17 – E**

**Given:**

![](images/00294.jpeg)

**What is the result?**

A.16

B.17

C.18

D.23

E.Compilation fails

Those assops appear overly complex, one of the vars doesn’t even get used… a red herring? And just look at the ternop! It tries to hide its intentions by dropping the parentheses → the question has all the signs of being booby-trapped on line 1.

It is, of course, perfectly possible to painstakingly work out the true meaning of this ternop by writing the whole statement down and then figuring out where the parentheses should go, but there is another way, a time-saving shortcut: since each question mark in a syntactically valid nested ternop must have a matching colon, let’s simply count them.

Three question marks and two colons → somewhere a term is missing → the code fails compilation. The following stat would have worked; the previously missing part is highlighted:

![](images/00295.jpeg)

**Problem 3.18 – AC**

**Given the following code fragment:**

As you are planning to sell your Android-based games, you need to calculate discount rates for bulk purchases using the following criteria:

–if someone buys three or four of your apps, you are willing to offer a 20% discount;

–buying five or more apps makes your clients eligible for a 50% discount;

–the miserly types who refuse to spend their ill-gotten money on more than two of your amazing games, will get no discount at all.

The following **main()** method should take care of the task:

![](images/00296.jpeg)

**Which two code fragments can be independently inserted at line X to meet the above criteria?**

![](images/00297.jpeg)

Option B got its logic wrong by insisting that buying three or more games means a 20% discount. Option D specifies a 0% discount for any quantity below 5\. And finally, option E never provides a 50% discount for any quantity over 1.

Don’t take this Problem lightly; work out exactly what’s going on in it; you’ll be glad you did.

**Problem 3.19 – B**

**Given the following code fragment:**

![](images/00298.jpeg)

![](images/00299.jpeg)

**What is the result?**

A.My plaid jackets quit.

B.My six before quit.

C.six before she quit.

D.six dozen before quit.

The first `if` construct wraps up all the others, which are not even nested, so the solution is straight-forward.

**Problem 3.20 – C**

**Given:**

![](images/00300.jpeg)

**What is the result?**

A.valid

B.not valid

C.Compilation fails

D.An IllegalArgumentException is thrown

Since `if` accepts either `boolean` or a **Boolean** only, the code does not compile.

**Problem 3.21 – C**

**Given:**

![](images/00301.jpeg)

**What is the result?**

A.wow!

B.zer!

C.wowzer!

D.Compilation fails

All three printing stats fire. The first one runs because inverting `false` makes it `true`, and the second one runs simply because it doesn't even belong to the `if` stat, although is surrounded with braces.

**Problem 3.22 – C**

**Given:**

![](images/00302.jpeg)

**What is the result?**

A.It works!

B.!

C.Compilation fails

D.An exception is thrown at run time

The method **runTest()** returns an `int`, which cannot be accepted by `if`.

**Problem 3.23 – B**

**Given:**

![](images/00303.jpeg)

**What is the result?**

A.How many? 1

B.How many? 100

C.How many? 2

D.How many? 101

E.Compilation fails

As the instance var **flag** is automatically inited to the default value, the ternary operator evaluates to 100 while the printing stat makes a feeble attempt to trip you with the postfix notation.

**Problem 3.24 – A**

**Given the code fragment:**

![](images/00304.jpeg)

**And the following decision-making construct:**

![](images/00305.jpeg)

**What is the result?**

A.1

B.3

C.Compilation fails

D.An ArrayIndexOutOfBoundsException is thrown at run time

Option D is incorrect because no index exceeds the array’s length minus one. As for the `else-if` statements, the execution flow skips them altogether since `if` expression evaluates to `true`.

**Problem 3.25 – B**

**Given the code snippet:**

![](images/00306.jpeg)

**Which option will allow the code snippet print** `True Blue`**?**

A.Remove the `default` section

B.Replace line 7 with `String bool = "true";` and replace line 9 with `case "true":`

C.Remove the `break;` statement at line 11

D.Replace line 7 with `boolean bool = 1;` and replace line 9 with `case 1:`

As `switch` can’t work with a `boolean`, all we need is make **bool** of a proper type plus tweak the `case` value so that it’s consistent with `switch`’s expression, and option B does exactly that.

**Problem 3.26 – ABE**

**Given the code snippet:**

![](images/00307.jpeg)

![](images/00308.jpeg)

**Which three statements can be independently inserted at line X to enable the code to print** `Zero`**?**

A.short a = 0;

B.Integer a = 0;

C.Double a = 0;

D.String a = "0";

E.Byte a = new Byte("0");

F.Long a = 0;

Although the Exam Objective 2.5 tests us on **Boolean**, **Integer** and **Double** only, option F has a legitimate place here as this Problem actually checks our knowledge of `switch`. Option E is correct because all wrapper classes (except **Character** with its lonely **Character(**char value**)** ctor) have a constructor that accepts a **String**. Option C is incorrect since `switch` does not work with floating-point primitives and their wrappers. Everything else is just trivial.

**Problem 3.27 – C**

**Given the code snippet:**

![](images/00309.jpeg)

**What is the result?**

A.Compilation error on line 1

B.Compilation error on line 2

C.The code prints Not divisible by 4

D.The code prints Divisible by 4

Option B is obviously incorrect because `switch` does accept a **Short**. As for line 1, it is syntactically valid since all those casts are allowed.

**Problem 3.28 – B**

**Given:**

![](images/00310.jpeg)

**What is the result?**

A.Hi Alice!

B.Hi Alice!
Hi Bob!

C.Hi Alice!
Hi Bob!
Hi Carol!

C.Hi Alice!
Hi Bob!
Hi Carol!
Hello stranger!

Option B is correct due to falling through because of a missing `break` in the `case` "Alice".

**Problem 3.29 – CD**

**Given:**

![](images/00311.jpeg)

**Which two modifications, made independently, enable the code to compile and run?**

A.Adding a break statement after each print statement

B.Adding a default section

C.Removing the double quotes from each case label

D.Changing the type of the variable day to String

E.Arranging the case labels in ascending order

The problem with this class in its unmodified form is that the local var **day**’s type is inconsistent with `case` labels.

**Problem 3.30 – B**

**Given:**

![](images/00312.jpeg)

**What is the result?**

A.String !

B.String!

C.Compilation fails on line 1

D.Compilation fails on lines 2 and 3

This problem demonstrates that `switch` expression is evaluated at run time while `case` labels must be compile-time constants. Since the compiler is perfectly able to evaluate the concatenation of **Strings**, neither line 2 nor line 3 throws a comperr.

As for the `final` modifier, it doesn’t do anything useful.

**Problem 3.31 – C**

**Given:**

![](images/00313.jpeg)

**Which statement about this code is true?**

A.Line 1 throws a comperr

B.Line 2 throws a comperr

C.Line 3 throws a comperr

D.There is nothing wrong with the code

The problem is similar to the previous one although this time the code violates the rule about `case` labels: the var **a** isn’t a constant. Declaring it `final` would have cleared the comperr.

**Problem 3.32 – BE**

**Given:**

![](images/00314.jpeg)

**Which two LOCs fail compilation?**

A.Line 1

B.Line 2

C.Line 3

D.Line 4

E.Line 5

F.Line 6

The var **a** isn’t a constant to be used as a `case` label, that’s why line 5 throws a comperr whereas line 1 doesn’t. The var **c** is `final` so line 6 is OK. Line 3 compiles since the numeric literal 1 is an `int`, and line 4 doesn’t violate any rule, either. As for line 2, it attempts to declare a var right inside the `switch` expression, which is not allowed.

**Problem 3.33 – C**

**Given:**

![](images/00315.jpeg)

**Which statement about the code is true?**

A.The code compiles and prints Java

B.The code throws a comperr on line 1

C.The code throws a comperr on line 2

D.The code throws a RuntimeException

Line 1 compiles because the var **a1** is `final` while line 2 fails compilation as wrapper classes are not considered compile-time constants – even when they are declared `final`.

* * *

^([64](#part0017_split_000.html_id_119)) Although there’s no `then` in Java, it *is* the official name of this stat (JLS, §14.9.1, *The if-then Statement*).

^([65](#part0017_split_000.html_id_121)) It is interesting to note that many Java operators are used primarily because of their side effects. For example, the `new` operator has the profound side effect of creating a new object.

^([66](#part0017_split_000.html_id_125)) With one exception that concerns the class **StrictMath**: "In cases where the size is int or long and overflow errors need to be detected, the methods addExact, subtractExact, multiplyExact, and toIntExact throw an ArithmeticException when the results overflow" (ref.to the **StrictMath** API javadocs).

^([67](#part0017_split_000.html_id_123)) ‘if and only if’; the authors of the JLS love this abbreviation.

^([68](#part0017_split_000.html_id_127)) In the **String** API javadoc parlance: "The Java language provides special support for the string concatenation operator ( + )".

^([69](#part0017_split_001.html_id_129)) page [9](#part0006.html_page_9) in the 3rd ed. (1997).

^([70](#part0017_split_003.html_id_305)) `enum` types aren’t on the exam.

^([71](#part0017_split_003.html_id_133)) Formal def: «A *constant expression* is an expression denoting a value of primitive type or a **String**» (JLS, §15.28)

^([72](#part0017_split_003.html_id_131)) Because `switch` unboxes the wrapper, and autoboxing/unboxing happens only at run time…

^([73](#part0017_split_005.html_id_135)) The value of Dirac delta function δ(x) everywhere except at x = 0… No passive learning, remember?

^([74](#part0017_split_005.html_id_137)) §5.1.11, String Conversion ([http://docs.oracle.com/javase/specs/jls/se8/html/jls-5.html#jls-5.1.11](http://docs.oracle.com/javase/specs/jls/se8/html/jls-5.html#jls-5.1.11))

![](images/00316.jpeg)

**The 1Z0-808 objectives within this group:**

| [4.1](#part0018_split_000.html_c4.1) | Declare, instantiate, initialize and use one-dimensional arrays; |
| [4.2](#part0018_split_000.html_c4.1) | Declare, instantiate, initialize and use multi-dimensional arrays. |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

As the 2nd objective is just an extension of the first one, we’ll cover them both in a single block.

4.1 & 4.2 Declare, instantiate, initialize and use one- and multi-dimensional arrays:

![](images/00012.jpeg)An array is an **Object**.

| **Corollaries**: | Arrays can access any method that is available to the class **Object**; |
|  | Unlike primitive types, changes to an array are reflected wherever the array is used. |

![](images/00012.jpeg)Arrays are used to store collections of values and are structurally immutable (in other words, once an array has been allocated, we can’t change its length and the number of its dimensions).

![](images/00012.jpeg)Java provides support for one-dimensional and multi-dimensional arrays.

![](images/00012.jpeg)A two-dimensional array refers to a collection of one-dimensional arrays, which can be of different length (**other wording**: rows may have different number of columns in them).

![](images/00012.jpeg)The creation of an array involves three steps:

![](images/00059.jpeg)declaration,

![](images/00059.jpeg)allocation, and

![](images/00059.jpeg)initialization.

![](images/00012.jpeg)The type of an array can be any including an abstract data type or interface.

![](images/00012.jpeg)As arrays are **Object**s, they are allocated by using the keyword `new`.

![](images/00012.jpeg)The number of matching square brackets specifies the number of dimensions in the array. The square brackets may follow either the data type or the variable name, or both if the array is multi-dimensional.

![](images/00012.jpeg)A standalone declaration of an array that isn’t followed by allocation creates a reference var that points to `null`.

![](images/00012.jpeg)Because declaration does not create elements, it is illegal to specify the size of the array in the declaration part.

![](images/00012.jpeg)It is permitted to declare and allocate an array without initing it:

![](images/00317.jpeg)

![](images/00012.jpeg)Once allocated, all elements receive their default values according to the declared data type:

![](images/00059.jpeg)0 for integral numerical types such as `byte`, `short`, `int` and `long`;

![](images/00059.jpeg)0.0 for floating-point numerical types (`float` and `double`);

![](images/00059.jpeg)`false` for `boolean`;

![](images/00059.jpeg)'\u0000' for `char`, and

![](images/00059.jpeg)`null` for reference types.

| **Corollaries**: | Accessing an uninited array of any reference type with a printing stat won’t throw an NPE; |
|  | A properly allocated array *will* be inited even if it’s a local var and there’s no explicit initialization. |

![](images/00012.jpeg)When all the steps are combined into a single stat, defining the length of the array is not permitted because it is calculated automatically on the basis of the number of values that are assigned to the array. For example, we cannot specify the length of the array when using an initializer block at the point of declaration:

![](images/00318.jpeg)

![](images/00012.jpeg)An initializer block without `new` is valid only in the declaration:

![](images/00319.jpeg)

![](images/00012.jpeg)The code throws an AIOOBE at run time if the requested index does not fall within the valid range of the number of elements.

![](images/00012.jpeg)The dimension expressions are evaluated first (left to right).

![](images/00012.jpeg)While counting curly braces may seem at the first glance a reliable solution to checking the consistency of dimensions, exercise extreme caution as some elements just might be arrays in themselves:

![](images/00320.jpeg)

![](images/00012.jpeg)Accessing slots in allocated arrays with undefined dimension(s) results in an NPE:

![](images/00321.jpeg)

![](images/00012.jpeg)The upper-level dimension *must* be defined in the absence of initializer block:

![](images/00322.jpeg)

![](images/00012.jpeg)EXTRA: To see if an array is assignable to another array, check the number of dimensions the slots are referring to and *not* the length of the array on the right-hand side:

![](images/00323.jpeg)

![](images/00012.jpeg)EXTRA: When accessing an array, the expression to the left of the square brackets gets evaluated before any part of the expression within the brackets. If this evaluation completes abruptly, the expression inside the brackets won’t be evaluated:

![](images/00324.jpeg)

![](images/00012.jpeg)EXTRA: A vararg passed to a method will be used as a regular array. Say, in case of a vararg-based **main()** method invocation, the compiler internally converts **String**… into a **String**[] → the JVM doesn’t have any idea about the vararg. It sees only a **String**[].

![](images/00012.jpeg)EXTRA: A trailing comma is acceptable: `new String[]{"Hi",}`. This is used to simplify changes in the order of elements particularly when they are written vertically.

![](images/00012.jpeg)EXTRA: There are no true, matrix-type multi-dimensional arrays in Java, and since they are implemented as arrays of arrays, the structural immutability concerns only the first dimension:

![](images/00325.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 4.1Given the class:**

![](images/00326.jpeg)

**Which code fragment, when inserted at line 3, lets the code print** `MU vs FCB 3 : 1`**?**

A.byte[] new arr = byte[2];

B.short[] arr;
arr = new short[2];

C.int arr = new int[2];

D.long arr[2];

**Problem 4.2Given the following main method:**

![](images/00327.jpeg)

**What is the result?**

A.53

B.55

C.Compilation fails

D.Run-time exception is thrown

**Problem 4.3Given:**

![](images/00328.jpeg)

**Which option represents the contents of the array arrStr after line 13?**

A.abcdef

B.abcfef

C.abcfeg

D.abcgeg

**Problem 4.4Given:**

![](images/00329.jpeg)

**Which option outputs all elements of the array referred to as** `arr`**?**

![](images/00330.jpeg)

**Problem 4.5Given:**

![](images/00331.jpeg)

**Which option represents the state of the** `arr` **array after successful completion of the outer loop?**

A.arr[0][0]=10
arr[1][0]=10
arr[2][0]=10

B.arr[0][0]=10
arr[0][1]=10
arr[0][2]=10

C.arr[0][0]=10
arr[0][1]=10
arr[0][2]=10
arr[0][3]=10
arr[1][0]=0
arr[1][1]=0
arr[1][2]=0
arr[1][3]=0

D.arr[0][0]=10
arr[0][1]=0
arr[0][2]=0

**Problem 4.6Given:**

![](images/00332.jpeg)

**What is the result?**

A.12 followed by null

B.2 followed by 4

C.An IllegalArgumentException is thrown at run time

D.12 followed by an ArrayIndexOutOfBoundsException

**Problem 4.7**

**Which two are valid declarations of a two-dimensional array?**

A.int[][] arr2D;

B.int[2][2] arr2D;

C.int arr2D[];

D.int[][] arr2D[];

E.int[] arr2D[];

**Problem 4.8Given:**

![](images/00333.jpeg)

**What is the result?**

A.3 false 1

B.3 true 1

C.2 false 1

D.2 true1

**Problem 4.9**

**Which two are valid declarations, instantiations and initializations of a multi-dimensional array?**

A.int[][] arr2D = { { 0, 1, 2, 3 } { 4, 5 } };

B.int[][] arr2D = new int[2][2];
arr2D[0][0] = 0;
arr2D[0][1] = 1;
arr2D[1][0] = 2;
arr2D[1][1] = 3;

C.int[][][] arr3D = { {0,1}, {2, 3}, {4, 5} };

D.int[] arr = { ( 0 ), ( 1 ), ( 2 ), ( 3 ), ( 4 ) };
int[][][] arr3D = new int[2][2][2];
arr3D[0][0] = arr3D[0][1] = arr;
arr3D[1][0] = arr3D[0][1] = arr;

E.int[][] arr2D = { 0, 1 };

**Problem 4.10**

**Which two are valid array declarations?**

A.Object arr1[];

B.boolean arr2[3];

C.char[] arr3;

D.double[2] arr4;

**Problem 4.11Given the class:**

![](images/00334.jpeg)

**Which pair of statements will set each element of the array to the sum of the element indices and then modify it by multiplying the value by 2?**

![](images/00335.jpeg)

**Problem 4.12**

**Which two statements are true for a two-dimensional array?**

A.Internally, Java stores it as an array of an array of the specified data type.

B.Each row of a two-dimensional array must be of the same size.

C.The number of elements of the array in each dimension must be specified at the moment of declaration.

D.All methods defined in the class Object may be invoked on the two-dimensional array.

**Problem 4.13Given the following method:**

![](images/00336.jpeg)

**Which two statements, when inserted independently at line X, enable the code to compile and run without throwing an exception?**

A.int[][] array = null;

B.int[][] array = new int[2];

C.int[][] array = new int[2][];

D.int[][] array = new int[][4];

E.int[][] array = new int[2][0];

F.int[][] array = new int[0][4];

**Problem 4.14Given the following class:**

![](images/00337.jpeg)

**Which statement, when inserted at line X, will print** `null`**?**

A.System.out.println(array[1]);

B.System.out.println(array[1][1]);

C.System.out.println(array[1][1][1]);

D.None of the above because the code fails compilation

**Problem 4.15Given the following graphic representation of an array:**

![](images/00338.jpeg)

**And given the code fragment that was used to fill in the array as pictured above:**

![](images/00339.jpeg)

**Which statement will make four crosses in a row?**

A.starr[3][3] = "X";

B.starr[2][3] = "X";

C.starr[2][2] = "X";

D.starr[3][2] = "X";

E.starr[2][4] = "X";

**Problem 4.16Given:**

![](images/00340.jpeg)

**What is the result?**

A.Caught E

B.Caught NPE

C.Caught AIOOBE

D.Compilation fails

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 4.1 – B**

**Given the class:**

![](images/00341.jpeg)

**Which code fragment, when inserted at line 3, lets the code print** `MU vs FCB 3 : 1`**?**

A.byte[] new arr = byte[2];

B.short[] arr;
arr = new short[2];

C.int arr = new int[2];

D.long arr[2];

Options A, C and D are syntactically invalid because A misplaces the keyword `new` and C specifies a non-array primitive in the left-hand part. As for option D, it violates syntax by specifying the number of elements right in the declaration part.

Option B correctly declares a one-dimensional array of `short`s in its first stat, then instantiates the array.

**Problem 4.2 – A**

**Given the following main method:**

![](images/00342.jpeg)

**What is the result?**

A.53

B.55

C.Compilation fails

D.Run-time exception is thrown

The length of an array is stored in the instance field **length** whereas getting the length of a **String** requires invoking the method **length()** on the **String** object.

**Problem 4.3 – C**

**Given:**

![](images/00343.jpeg)

**Which option represents the contents of the array** `arrStr` **after line 13?**

A.abcdef

B.abcfef

C.abcfeg

D.abcgeg

The answer seems obvious – even insultingly so. And while this particular problem is indeed simple, I’d like to seize the opportunity to remind you that we always should be on guard when dealing with objects.

The problem is not booby-trapped only because the class **String** is immutable, so after line 13 each element of the array still points to a different object. Now consider what happens when the objects are not immutable:

![](images/00344.jpeg)

Line 7 makes both elements point to the same object just like line 12 in [Problem 4.3](#part0018_split_002.html_id_322) did. But unlike the **String**s where a change in an object creates another object, a change in a **StringBuilder** gets reflected inside the original object, so that’s why line 10 affects **sbar**[0], too.

Reminder: Here’s the list of the immutable core Java 1.8 classes that are on the exam:

![](images/00345.jpeg)

EXTRA: all wrapper classes
EXTRA: *structurally*-immutable is any **List** created by **Arrays.asList(arr)**

I admit: it was tempting to use a user-defined mutable data type to lay a nice trap for you but the actual exam uses something similar to the way [Problem 4.3](#part0018_split_002.html_id_322) is presented, so in the end I voted for a better consistency. Do remember, however, that acting on a reference can lead to radically different results as compared to acting on a primitive data type.

**Problem 4.4 – D**

**Given:**

![](images/00346.jpeg)

**Which option outputs all elements of the array referred to as** `arr`**?**

![](images/00347.jpeg)

Indexation of arrays starts with zero so option A misses the first row entirely and the first column in the second row. Option B should have compared the loop var **idx** to **arr[index].length** while option C is simply irrelevant as the code declares neither the var **integers** nor the var **booleans**.

I met a similar question on both sittings so take all the time you need to get this Problem’s logic right.

**Problem 4.5 – B**

**Given:**

![](images/00348.jpeg)

**Which option represents the state of the array** `arr` **after successful completion of the outer loop?**

A.arr[0][0]=10
arr[1][0]=10
arr[2][0]=10

B.arr[0][0]=10
arr[0][1]=10
arr[0][2]=10

C.arr[0][0]=10
arr[0][1]=10
arr[0][2]=10
arr[0][3]=10
arr[1][0]=0
arr[1][1]=0
arr[1][2]=0
arr[1][3]=0

D.arr[0][0]=10
arr[0][1]=0
arr[0][2]=0

The instantiation part of the array declaration stat says that the array has only one row with three slots in it, so options A and C are obviously out (A needs three rows and C, two).

Option D is also incorrect because the nested `for` loop executes successfully thus setting each element to the value of ten.

**Problem 4.6 – D**

**Given:**

![](images/00349.jpeg)

**What is the result?**

A.12 followed by null

B.2 followed by 4

C.An IllegalArgumentException is thrown at run time

D.12 followed by an ArrayIndexOutOfBoundsException

The initialization part of the array declaration specifies that the array will contain a single row with five slots in it, each of which is an array in itself. While the element referred to as **arr**[4][2] does exist, the third one-dimensional array contains only three slots so the code tries to access an element well beyond the valid range.

**Problem 4.7 – AE**

**Which two are valid declarations of a two-dimensional array?**

A.int[][] arr2D;

B.int[2][2] arr2D;

C.int arr2D[];

D.int[][] arr2D[];

E.int[] arr2D[];

Options C and D are obviously incorrect as they specify a wrong number of dimensions (one and three, respectively), and option B is syntactically invalid as the declaration part may not contain the number of elements.

**Problem 4.8 – B**

**Given:**

![](images/00350.jpeg)

**What is the result?**

A.3 false 1

B.3 true 1

C.2 false 1

D.2 true1

Although the **getClass()** and **isArray()** methods are not on the exam^([75](#part0018_split_003.html_id_140)), it is probably not a bad idea to remind ourselves that a multi-dimensional array in Java is actually implemented as an array of arrays who can be of different lengths and even change the number of their slots.

**Problem 4.9 – BD**

**Which two are valid declarations, instantiations and initializations of a multi-dimensional array?**

A.int[][] arr2D = { { 0, 1, 2, 3 } { 4, 5 } };

B.int[][] arr2D = new int[2][2];
arr2D[0][0] = 0;
arr2D[0][1] = 1;
arr2D[1][0] = 2;
arr2D[1][1] = 3;

C.int[][][] arr3D = { {0, 1}, {2, 3}, {4, 5} };

D.int[] arr = { ( 0 ), ( 1 ), ( 2 ), ( 3 ), ( 4 ) };
int[][][] arr3D = new int[2][2][2];
arr3D[0][0] = arr3D[0][1] = arr;
arr3D[1][0] = arr3D[0][1] = arr;

E.int[][] arr2D = { 0, 1 };

Option A is syntactically invalid as it is missing a comma between the elements. Option B is a ‘straight arrow’: it instantiates a two-dim array then fills it with `int`s. Option C says that **arr3D** is a three-dim array while the initialization part is suitable for a two-dim array only (observe that here the trick about counting the number of leading braces works quite well). Option E is similar to C in being inconsistent about the number of dimensions, and as for option D, it is perfectly valid although looks a bit twisted. The redundant parentheses do not affect the statement’s compilability, and chained assignments of the already declared vars are also legal.

**Problem 4.10 – AC**

**Which two are valid array declarations?**

A.Object arr1[];

B.boolean arr2[3];

C.char[] arr3;

D.double[2] arr4;

While the square brackets can indeed be placed after the reftype or the var’s name, the array declaration never accepts the number of elements.

**Problem 4.11 – D**

**Given the class:**

![](images/00351.jpeg)

**Which pair of statements will set each element of the array to the sum of the element indices and then modify it by multiplying the value by 2?**

![](images/00352.jpeg)

This one illustrates that the questions contain sometimes just too much chaff: we actually don’t even need to look at the class to work out the correct answer as option D is the only one that is syntactically correct regardless of its business logic.

**Problem 4.12 – AD**

**Which two statements are true for a two-dimensional array?**

A.Internally, Java stores it as an array of an array of the specified data type.

B.Each row of a two-dimensional array must be of the same size.

C.The number of elements of the array in each dimension must be specified at the moment of declaration.

D.All methods defined in the class Object may be invoked on the two-dimensional array.

By now answering this question should present no problems whatsoever.

**Problem 4.13 – CE**

**Given the following method:**

![](images/00353.jpeg)

**Which two statements, when inserted independently at line X, enable the code to compile and run without throwing an exception?**

A.int[][] array = null;

B.int[][] array = new int[2];

C.int[][] array = new int[2][];

D.int[][] array = new int[][4];

E.int[][] array = new int[2][0];

F.int[][] array = new int[0][4];

Only options B and D are syntactically incorrect as B is inconsistent about the number of dimensions while D is missing the number of elements in the very first array.

The compiler always needs to know how many slots an upper-level array should contain. So if we have a two-dim array, the code must specify the number of elements for at least the first dimension; a three-dim array will need number of slots for at least the first two dimensions, etc.

Although option A does compile, it throws an NPE because the reference points to `null`. This is hugely important subject for the exam so let’s list all the NPE-throwing scenarios right away:

**The Magnificent Five:**

**In what cases JVM throws NullPointerException?**

ABSOLUTELY NEEDED

| 1. | Calling the instance method on a `null` object. |
| 2. | Accessing or modifying the field of a `null` object. |
| 3. | Taking the length of `null` as if it were an array. |
| 4. | Accessing or modifying the slots of `null` as if it were an array. | ← a popular trap! |
| 5. | Throwing `null` as if it were a **Throwable** value. | ← didn’t meet on the exam, though |

By choosing option A, we’ll be implementing the 4th scenario.

Although option C leaves out the number of elements in the second dimension, it’s alright since the code then starts defining the arrays that go in each slot. Option E is similar to option C as it is immaterial how many elements we declare in the very last dimension.

And finally, option F throws an AIOOBE because the array is instantiated with zero elements in its first dimension, and the code wants to work with an element that does not even exist. Since the first dimension is structurally immutable, there isn’t much we can do about fixing the problem.

**Problem 4.14 – B**

**Given the following class:**

![](images/00354.jpeg)

**Which statement, when inserted at line X, will print** `null`**?**

A.System.out.println(array[1]);

B.System.out.println(array[1][1]);

C.System.out.println(array[1][1][1]);

D.None of the above because the code fails compilation

The exam GUI doesn’t allow code editing; on the other hand, everything is pretty-typed and you will not meet such a ‘hairy’ snippet on the real exam. But practice is still practice.

It is, of course, possible to work out diligently each and every element’s address but I would like to show you a shortcut. The `null` element here simply holds a place of a one-dim array so we can mentally replace it with a pair of matching curly braces. It becomes apparent then that the first two closing braces indicate the end of the first row, the next two closing braces (the last one of them is imaginary) mark the end of the second row – and all the rest is simply irrelevant. By mentally restoring `null` to its lawful place, we finally get its address: [1][1].

All in all, the entire array contains four rows. More specifically, the uppermost array has four slots occupied by arrays: the first two of them contain two 3-element-long slots each, the third one stores just "y" in the third dimension, and the fourth array has two slots with the last one – that is, array[3][1] – of zero length:

![](images/00355.jpeg)

You probably should practice more until reading dimensions even in horrendous ‘dendritic’ arrays like this one becomes your second nature. For example – and look only at the code, not the picture – what is the address of the letter "y"? what about "Q"?^([76](#part0018_split_003.html_id_142))

**Problem 4.15 – C**

**Given the following graphic representation of an array:**

![](images/00356.jpeg)

**And given the code fragment that was used to fill in the array as pictured above:**

![](images/00357.jpeg)

**Which statement will make four crosses in a row?**

A.starr[3][3] = "X";

B.starr[2][3] = "X";

C.starr[2][2] = "X";

D.starr[3][2] = "X";

The array initialization part mimics the rows in the table, so the solution is obvious – especially when you mentally re-arrange the elements vertically. Note, however, that we don’t even need to consult the code fragment to see what element should be assigned the literal "X". Even if we somehow confuse rows with columns, it still will be the last element in a 3-by-3 grid (provided, of course, we start counting from the upper left corner and continue clockwise, which is only natural).

The question on the exam used separate statements to assign Xs to the appropriate cells so you may want to practice with that version, too.

And one more thing: I met a similar question on the second sitting^([77](#part0018_split_003.html_id_144)) only, which may mean that it is of the ‘Guinea Pigs’ variety, in other words, ungraded. Who knows…

**Problem 4.16 – A**

**Given:**

![](images/00358.jpeg)

**What is the result?**

A.Caught E

B.Caught NPE

C.Caught AIOOBE

D.Compilation fails

According to the JLS §15.10.4, *Run-Time Evaluation of Array Access Expressions*, the evaluation process starts to the left of the square brackets, then – if successful – the JVM looks at the part within the brackets. The Specification also adds that

If the array reference expression produces `null` instead of a reference to an array, then a NullPointerException is thrown at run time, but only after all parts of the array access expression have been evaluated and only if these evaluations completed normally.

In our case it means that since the evaluation of the index expression **spoil()** completes abruptly due to a thrown **Exception**, an NPE never occurs because the evaluation process doesn’t even reach the moment of truth where it must check whether value of the array reference expression is `null`.

This exercise also demonstrates that although accessing a slot of `null` as if it were an array does produce an NPE, we shouldn’t jump to the conclusion as soon as we see that the code intends to do something to a `null` reference: the chances are it won’t get to that point at all…

* * *

^([75](#part0018_split_002.html_id_139)) **getClass()** is defined in **Object** and **isArray()** is defined in the class **Class**.

^([76](#part0018_split_003.html_id_141)) [2][0][0] and [3][0][1], respectively.

^([77](#part0018_split_003.html_id_143)) On the first sitting there was no graphics at all…

![](images/00359.jpeg)

**The 1Z0-808 objectives within this group:**

| 5.1 | Create and use `while` loops |
| 5.2 | Create and use `for` loops including the enhanced `for` loop |
| 5.3 | Create and use `do-while` loops |
| 5.4 | Compare loop constructs |
| 5.5 | Use `break` and `continue` |

As loops are arguably the most widely used constructs, it becomes indispensable to fully master them for the exam. The harder the training the better the results so we’ll cover all loop-related objectives first and only then do exercises, otherwise it’ll be too obvious what each particular question is asking for thus making spotting traps easier. We will also pay a close attention to labels since they are generally go with loops.

![](images/00061.jpeg) **CORE RULES (with some Extras):**

![](images/00012.jpeg)The standard `for` loop is the most basic and versatile loop of all; it can replace any other loop construct.

![](images/00012.jpeg)`do-while` executes at least once.

![](images/00012.jpeg)The `break` statement breaks out of a loop ‘cleanly’, in other words, by fully abandoning current iteration and any other remaining iterations of the loop. Control is transferred to the first statement after the loop.

![](images/00012.jpeg)When the loop `for(i = 0; i < n; i++)` terminates, the value of **i** is **n** and not **n-1**.

![](images/00012.jpeg)Nested loops can appear intimidating but chances are the flow won’t even enter some of those damned loops.

| **Reminder:** | The weirder the loop the higher the chances the code is booby-trapped somewhere else and, what’s more, on a pretty simple aspect. |

If your analysis shows that the flow does enter a loop, write down each iteration with all its steps; cracking loops mentally at home is cool but probably not a good idea on the exam. Vertical notation works better than writing the results of each iteration in rows because it’s easier to correct values this way or start over from a particular point if you lose concentration for a sec:

![](images/00360.jpeg)

![](images/00012.jpeg)EXTRA: Any section of the `for` loop can be moved to its body; what’s more, the ForInit section accepts chained assignments (the vars must be of the same type, though):

![](images/00361.jpeg)

![](images/00012.jpeg)The compiler treats `for(;;)` as `for(;true;)`.

![](images/00012.jpeg)An endless loop makes subsequent stat unreachable → comperr.

The rule sounds pretty obvious but endless loops are tricky: the code will throw the "unreachable statement" comperr only if 1) the boolean expression can be evaluated at compile time, and 2) there’s no escape from the loop. Consider the following example:

![](images/00362.jpeg)

This code fails compilation since line 3 creates a truly endless loop and the compiler can see it → the next LOC becomes unreachable → comperr. If, however, we comment out the offending line 3, the class will compile because the other loops have an escape hatch built right in.

For example, line 4 says that we could break out of the endless `for(;;)` if such and such condition evaluates to `true` → ‘Alright, I admit it’s possible so have it your way’, shrugs the compiler.

The TCF construct on lines 5 thru 7 is even more interesting: although the `for` loop in the `try` block doesn’t have a rabbit hole and simply runs idly for eternity, the compiler trusts us when we say that there’s still a theoretical possibility for an exception and, therefore, a way to transfer control out of the loop. This trick works, however, only if `catch` specifies either an RTE or, by extension, a **Throwable** or **Exception**; for example, an IOE will trip a comperr ‘exception **IOException** is never thrown in body of corresponding `try` statement’.

Removing the `catch` block will make the compilation fail on line 8 because the TCF construct is treated as a single block → the compiler sees that this block contains an ‘escapeless’ endless loop that is followed by one more stat → which is therefore unreachable.

And if you think this stuff is too exotic, let me tell you that I did meet on the exam a `while(true)` loop wrapped up in a `try` block… Don’t worry, though: we’ll cover this scenario again in [Chapter II.8, *Handling Exceptions*](#part0022_split_000.html_page_336).

![](images/00012.jpeg)The curly braces {} are NOT required for loops → be careful: the code’s business logic can be in jeopardy.

![](images/00012.jpeg)`continue` is valid only inside loops; ANY loop will do including `for-each`, `do-while` and `while`.

![](images/00012.jpeg)Labels:

![](images/00059.jpeg)can be added to:

–a sub-block;

–any looping construct such as `for`, `for-each`, `while`, or `do-while`;

–conditional constructs such as `if` and `switch`;

–expressions and assignments;

–`return` stats;

–TCF constructs, and

–`throw` stat.

![](images/00059.jpeg)cannot be added to declarations of variables.

Although labeled `break` is commonly used with loops, it is still valid outside them (e.g., in the `if` constructs, etc.). Watch out, however, for its scope as it might lead to the ‘unreachable statement’ comperr.

Labeled `break` needs a block or an `if` with at least a single `break label;` stat in it:

![](images/00363.jpeg)

As labels bind to either loops or blocks, outside them they are out of scope → comperr.

| **Corollary:** | If there's a labeled `continue` it must always be inside the loop the label is declared for. |

![](images/00012.jpeg)The `for-each` loop is routinely used to iterate over **Collection**s such as **List**s. However, it cannot be used to:

![](images/00059.jpeg)initialize or modify the elements of an array;

![](images/00059.jpeg)delete the elements of a **Collection**;

![](images/00059.jpeg)iterate over multiple collections or arrays within the same loop.

![](images/00012.jpeg)Nested loops – Rules of Engagement:

![](images/00059.jpeg)use `break` to exit the inner loop;

![](images/00059.jpeg)use `continue` to abandon the current iteration of the inner loop;

![](images/00059.jpeg)use a labeled `break` to exit the outer loop;

![](images/00059.jpeg)use a labeled `continue` to skip the iteration of the outer loop.

![](images/00012.jpeg)EXTRA: It is not possible to break out of an `if` construct when it isn’t wrapped up in a loop or `switch` UNLESS the `break` stat is labeled (already demonstrated):

![](images/00364.jpeg)

![](images/00012.jpeg)EXTRA: `while` expression accepts assignments:

![](images/00365.jpeg)

![](images/00012.jpeg)EXTRA: `while` doesn’t accept var declarations; can use method invocation, though.

![](images/00012.jpeg)EXTRA: The ForUpdate section of the standard `for` loop allows only the following:

–an assignment expression;

–pre/post incr/decr op;

–method invocation;

–class instance creation;

![](images/00012.jpeg)EXTRA: `while` and regular `for` can’t have explicit `false` as their termination condition^([78](#part0019_split_002.html_id_148)) but `do-while` *can*.

What’s more, `while(!true)` doesn’t compile – because `!true` is a straightforward constant that can be evaluated at compile time – but `while(!(x=true))` does compile. Same goes for the standard `for`:

![](images/00366.jpeg)

Remark: `if(false)` is an exception to the rule (to make if(DEBUG) possible).

![](images/00012.jpeg)EXTRA: Can’t use an existing/predefined var in the var declaration part of the enhanced `for` loop. What’s interesting, this var (even of a primitive type!) can be `final`^([79](#part0019_split_002.html_id_146)). In fact, this is the only modifier that is allowed inside an enhanced `for` declaration:

![](images/00367.jpeg)

![](images/00012.jpeg)EXTRA: Labels are ‘recyclable’ (because they go out of scope as soon as the block or construct they bind to is over):

![](images/00368.jpeg)

![](images/00012.jpeg)EXTRA: Booby-trapped patterns:

![](images/00059.jpeg)`i = i++;` never increments.^([80](#part0019_split_002.html_id_150))

![](images/00059.jpeg)a `break-continue` fork in ANY loop makes subsequent stats inside the loop unreachable:

![](images/00369.jpeg)

![](images/00059.jpeg)`for(...;...;`*<no update>*`){`*<no update>*`}` creates a valid, endless loop.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 5.1Given the following class:**

![](images/00370.jpeg)

**Which option(s) can replace *** so that the class will compile and run successfully? (Choose all that apply)**

A.int e : arr

B.int i = 0; i < 0; i++

C.; ;

D.int i; i < 4; i++

E.boolean b = true; b; b = !b

**Problem 5.2Given the following class:**

![](images/00371.jpeg)

**Which option will enable the code to print 54321?**

A.Replace line 5 with System.out.print(--a);

B.Replace line 5 with System.out.print(a); a--;

C.Replace line 5 with --a; System.out.print(a);

D.Replace line 9 with return a > 0 ? false : true;

**Problem 5.3Given:**

![](images/00372.jpeg)

**Which option can replace *** to enable the code to print 135?**

A.int idx = 0; idx <= 4; idx++

B.int idx = 0; idx < 5; idx += 2

C.int idx = 1; idx <= 5; idx += 1

D.int idx = 1; idx < 5; idx += 2

**Problem 5.4Given the following main method:**

![](images/00373.jpeg)

**What is the result?**

A.5

B.4 2 1

C.5 4 3 2 1

D.5 4 3 2 1 0

E.Nothing is printed

**Problem 5.5Given the code fragment:**

![](images/00374.jpeg)

**Given the requirements:**

1\. Process all the elements of the array in the order of entry.

2\. Process all the elements of the array in the reverse order of entry.

3\. Process alternating elements of the array in the order of entry.

**Which two statements are true?**

A.All three Requirements can be successfully implemented by using the enhanced `for` loop.

B.Requirements 1, 2 and 3 can be implemented by using the standard `for` loop.

C.The standard `for` loop is not suitable to implement Requirements 2 and 3.

D.The enhanced `for` loop can be used to implement Requirement 1.

E.It is impossible to implement Requirement 3 by using either the enhanced `for` loop or the standard `for` loop.

**Problem 5.6Given the following main method:**

![](images/00375.jpeg)

**What is the result?**

A.20 30 40 50 60 Processed

B.20 30 40 50 Processed

C.20 Processed

D.Compilation fails

**Problem 5.7Given the code snippet:**

![](images/00376.jpeg)

**What is the result?**

A.Compilation fails

B.2; 4; 6;

C.0; 2; 4; 6;

D.0; 2; 4; 6; 8;

**Problem 5.8Given:**

![](images/00377.jpeg)

**What is the result?**

A.byte short int

B.byte short long char

C.byte short int long char

D.Compilation fails

**Problem 5.9Given the following array of ints:**

![](images/00378.jpeg)

**Which two code fragments, when used independently, print all elements in the array?**

![](images/00379.jpeg)

**Problem 5.10Given the following code snippet:**

![](images/00380.jpeg)

**What is the result?**

A.a : b : c : d : null :

B.Compilation fails.

C.NullPointerException is thrown at run time

D.An ArrayIndexOutOfBoundsException is thrown at run time.

**Problem 5.11Given:**

![](images/00381.jpeg)

**What is the result?**

A.0 found!

B.1 found!

C.2 found!

D.Compilation fails

E.An exception is thrown

**Problem 5.12Given:**

![](images/00382.jpeg)

**What is the result?**

A.Done! 2147483647

B.Done! -2147483648

C.Compilation fails on line 1.

D.Compilation fails on line 2.

E.Code throws a run-time exception.

**Problem 5.13Given the following class:**

![](images/00383.jpeg)

**Which statement, when inserted at line X, will make the code print the following table?**

![](images/00384.jpeg)

A.int x = 2, y = 3, z = 2;

B.int x = 3, y = 2, z = 4;

C.int x = 3, y = 0, z = 5;

D.int x = 4, y = 3, z = 4;

**Problem 5.14Given the following class:**

![](images/00385.jpeg)

**Which statement, when inserted at line 3, will make the code print** `a = 7`**?**

A.int i = 6;

B.int i = 7;

C.int i = 8;

D.None of the above as the code fails compilation at line 5

**Problem 5.15Given:**

![](images/00386.jpeg)

**What is the result?**

A.0

B.012

C.012012012

D.Compilation fails

**Problem 5.16Given the following class:**

![](images/00387.jpeg)

**What is the result?**

A.0

B.01

C.012

D.The program runs but produces no output

E.Compilation fails

**Problem 5.17Given:**

![](images/00388.jpeg)

**What is the result?**

A.1

B.10

C.The program enters an endless loop

D.Compilation fails

**Problem 5.18Given:**

![](images/00389.jpeg)

**How many LOCs fail compilation?**

A.None

B.One

C.Two

D.Three

E.Four

**Problem 5.19Given:**

![](images/00390.jpeg)

**What is the result?**

A.A D

B.B D

C.A C D

D.B C D

E.Compilation fails

**Problem 5.20Given:**

![](images/00391.jpeg)

**What statements should replace LOC1 and LOC2, respectively, in order to print** `12345`**?**

A.break, continue

B.break, break

C.continue, break

D.continue, continue

**Problem 5.21Given the array:**

![](images/00392.jpeg)

**Which option prints orange pomelo pompia citron ?**

![](images/00393.jpeg)

**Problem 5.22Given the following classes in the same package:**

![](images/00394.jpeg)

**What is the result?**

A.The sequence 0 1 2 3 4 is printed once

B.The sequence 0 1 2 3 4 is printed twice

C.The sequence 0 1 2 3 4 5 is printed once

D.The sequence 0 1 2 3 4 5 is printed twice

**Problem 5.23Given:**

![](images/00395.jpeg)

**What is the output?**

A.Jav8av8v8av88

B.Jav8Jav8Jav8Jav8Jav8

C.Java8

D.Compilation fails

**Problem 5.24Given:**

![](images/00396.jpeg)

**What is the result?**

A.3
23
123

B.30
230
1230

C.23
123

D.230
1230

**Problem 5.25Given:**

![](images/00397.jpeg)

**What is the result?**

A.53

B.58

C.106

D.1013

E.Compilation fails

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 5.1 – ABCE**

**Given the following class:**

![](images/00398.jpeg)

**Which option(s) can replace *** so that the class will compile and run? (Choose all that apply)**

A.int e : arr

B.int i = 0; i < 0; i++

C.; ;

D.int i; i < 4; i++

E.boolean b = true; b; b = !b

Option A is a plain vanilla `for-each` loop.

Option B is a `for` loop in its classic form; the execution flow won’t enter this loop, though, as the termination condition evaluates to `false` right from the beginning.

Since option C is treated as `for(true)`, the loop is endless and the program never terminates. Should the code have some other stats after this LOC, they would be unreachable thus throwing a comperr.

Option D is invalid as the loop var **i** is missing initialization.

As for option E, it does look just a bit out of the ordinary but is perfectly valid, nonetheless. It executes once and then the termination condition (the value of the var **b**, to be precise) gets toggled in the update section thus stopping the loop.

**Problem 5.2 – B**

**Given the following class:**

![](images/00399.jpeg)

**Which option will enable the code to print 54321?**

A.Replace line 5 with `System.out.print(--a);`

B.Replace line 5 with `System.out.print(a); a--;`

C.Replace line 5 with `--a; System.out.print(a);`

D.Replace line 9 with `return a > 0 ? false : true;`

The code in its unmodified form enters an endless `while` loop and prints 5 over and over again.

Option A is incorrect since its initial output is four and not five because the increment operator in the prefix notation changes the value of the variable first and only then the variable is used so the output will be 43210.

Option C is essentially the same as option A, and option D doesn’t help, either, because all it does is just prevents the execution flow from entering the loop.

The correct answer, option B, can be also rewritten as `System.out.print(a--);`

**Problem 5.3 – B**

**Given:**

![](images/00400.jpeg)

**Which option can replace *** to enable the code to print 135?**

A.`int idx = 0; idx <= 4; idx++`

B.`int idx = 0; idx < 5; idx += 2`

C.`int idx = 1; idx <= 5; idx += 1`

D.`int idx = 1; idx < 5; idx += 2`

Since the output should start with the first element's value, options C and D are obviously incorrect. As for option A, it uses all five elements but we need only three.

**Problem 5.4 – A**

**Given the following main method:**

![](images/00401.jpeg)

**What is the result?**

A.5

B.4 2 1

C.5 4 3 2 1

D.5 4 3 2 1 0

E.Nothing is printed

The `do-while` loop always executes at least once. As the termination condition evaluates to `false`, the loop stops running right after the first iteration.

**Problem 5.5 – BD**

**Given the code fragment:**

![](images/00402.jpeg)

**Given the requirements:**

1.Process all the elements of the array in the order of entry.

2.Process all the elements of the array in the reverse order of entry.

3.Process alternating elements of the array in the order of entry.

**Which two statements are true?**

A.All three Requirements can be successfully implemented by using the enhanced for loop.

B.Requirements 1, 2 and 3 can be implemented by using the standard for loop.

C.The standard for loop is not suitable to implement Requirements 2 and 3.

D.The enhanced for loop can be used to implement Requirement 1.

E.It is impossible to implement Requirement 3 by using either the enhanced for loop or the standard for loop.

Since the enhanced `for` loop visits each element of an array (or, say, a **Collection** such as **List**, **ArrayList** and so on) only in the order of entry, option A is incorrect.

The standard `for` loop is almighty, which makes options C and E incorrect.

**Problem 5.6 – C**

**Given the following main method:**

![](images/00403.jpeg)

**What is the result?**

A.20 30 40 50 60 Processed

B.20 30 40 50 Processed

C.20 Processed

D.Compilation fails

The code is valid because both `continue` and `break` are within a loop, so option D is incorrect.

The flow enters the loop, the first element of the array gets printed and then, as the `if` expression evaluates to `false`, the second printing stat fires and the subsequent `break` makes the flow jump out of the loop.

**Problem 5.7 – C**

**Given the code snippet:**

![](images/00404.jpeg)

**What is the result?**

A.Compilation fails

B.2; 4; 6;

C.0; 2; 4; 6;

D.0; 2; 4; 6; 8;

A straightforward loop with no traps, so option A is out. As the output begins with the very first value, which is zero, option B is also incorrect.

Finally, we should recall that with the termination condition that uses the ‘less than’ op such as **myVar** < **ceiling**, the value of **myVar** can never become equal to **ceiling** *inside the loop*. Since in our case the ‘ceiling’ is 9 - 1 = 8, we can never reach it, which eliminates option D.

**Problem 5.8 – B**

**Given:**

![](images/00405.jpeg)

**What is the result?**

A.byte short int

B.byte short long char

C.byte short int long char

D.Compilation fails

Since `continue` is within a loop (the outer one, to be exact), there’s no problem with compilation.

When the `if`’s expression evaluates to `true`, `break` will force the execution flow to abandon the inner loop, so "int" never gets printed, which makes option A and C incorrect.

**Problem 5.9 – BE**

**Given the following array of ints:**

![](images/00406.jpeg)

**Which two code fragments, when used independently, print all elements in the array?**

![](images/00407.jpeg)

Option A uses the `for-each` loop incorrectly because the variable **i** itself is a representation of an element of the array; this option prints 2 4 16 and then throws an AIOOBE.

Option C is invalid syntactically as the `for-each` loop doesn’t allow initialization of the loop var; the only thing we can do with it is declare the var `final`.

Option D prints the loop var’s values (that is, 0 1 2 3 4) rather than the array’s elements.

And finally, option F fails compilation because the var **i** is local and therefore needs explicit initing before it can be used.

**Problem 5.10 – A**

**Given the following code snippet:**

![](images/00408.jpeg)

**What is the result?**

A.a : b : c : d : null :

B.Compilation fails

C.NullPointerException is thrown at run time

D.An ArrayIndexOutOfBoundsException is thrown at run time

The `for`-each loop never looks beyond array boundaries so option D is incorrect. The code does compile since `null` as a perfectly valid value for a reference variable. As for throwing an NPE, we already know that the method **System.out.print()** takes care of this problem by checking its argument for being `null`.

**Problem 5.11 – C**

**Given:**

![](images/00409.jpeg)

**What is the result?**

A.0 found!

B.1 found!

C.2 found!

D.Compilation fails

E.An exception is thrown

This is a classic `for` loop that simply visits each element of the array and checks if it equals 2015\. If it does, the counter **count** gets incremented, otherwise the execution abandons the current iteration, and the loop looks at the next element of the array.

**Problem 5.12 – D**

**Given:**

![](images/00410.jpeg)

**What is the result?**

A.Done! 2147483647

B.Done! -2147483648

C.Compilation fails on line 1.

D.Compilation fails on line 2.

E.Code throws a run-time exception.

Compilation fails on line 2 not because this LOC is syntactically invalid; after all, **Integer.MAX_VALUE** is also an `int` and not a reference type. The problem is that line 2 is simply unreachable because the compiler interprets `for(;;)` as `for(;true;)`, which means that the execution enters an endless – and in our case escapeless! – loop.

Can you tell offhand what is the root cause for this comperr? – STOP READING! Think about it for a minute. – It’s ***^([81](#part0019_split_002.html_id_154)). If they were enclosing both statements after `for(;;)`, like this:

![](images/00411.jpeg)

the program would have compiled and obediently printed Done! -2147483648 over and over again:

**Problem 5.13 – C**

**Given the following class:**

![](images/00412.jpeg)

**Which statement, when inserted at line X, will make the code print the following table?**

![](images/00413.jpeg)

A.int x = 2, y = 3, z = 2;

B.int x = 3, y = 2, z = 4;

C.int x = 3, y = 0, z = 5;

D.int x = 4, y = 3, z = 4;

The loop looks menacing but one still can hope to crack it eventually one step at a time – thus wasting five or even more minutes, which is an impossible luxury^([82](#part0019_split_002.html_id_152)). So no, we can’t go that way; what we really need here is strategic thinking.

Please recall me saying that the weirder the code the more chances it’s booby-trapped on something simple. However, by looking at the available options we can conclude that all LOCs are clean as the program both compiles and runs successfully. Alright, what to do then? Well, it’s time to give you another useful hint: if code is both tough-looking *and* clean, there’s always a soft spot in it. *Always*. Find it, take a poke – and the sucker will pop open in no time.

Let’s see how it works.

Observe that the stat that prints a bunch of dashes isn't managed by any conditional construct, which means its execution at each iteration is *guaranteed* → the dashes are printed three times → three iterations in total → since **i** starts with 0, **x** must be 3 → options A and D are eliminated… And while we are at this point, let’s repeat one more time: in a `for` loop whose termination condition is in the form of **myVar** < **ceiling**, **myVar**’s value can *never* be equal to **ceiling** inside the loop. You’ll do extremely well by remembering this simple yet powerful rule; I myself applied it half a dozen times on the exam…

Alright, here’s another logical chain to weed out the last incorrect option: the actual numbers that get printed are the values of the var **k** → there are five of them in total → the `while` loop ramps **k** one bit at a time → **z** must be 5\. There!

**Problem 5.14 – B**

**Given the following class:**

![](images/00414.jpeg)

**Which statement, when inserted at line 3, will make the code print** `a = 7`**?**

A.int i = 6;

B.int i = 7;

C.int i = 8;

D.None of the above as the code fails compilation on line 5

Naturally, it’s just a little joke: line 5 should have been written as `for(;i-- > 0;)`. Besides, there’s nothing illegal about combining the update section with the termination condition section.

**Problem 5.15 – B**

**Given:**

![](images/00415.jpeg)

**What is the result?**

A.0

B.012

C.012012012

D.Compilation fails

No loop mandates placing curly braces (they do affect business logic, though), so the code compiles just fine.

Now, let’s see what it does. The termi… oh! wait a sec! did you get the structure right? `do` and `while` on line X belong to two different constructs; if re-written, it's

![](images/00416.jpeg)

Good; now, the termination conditions for both loops depend on the same expression → both loops will terminate at exactly same point → the printing stat fires **moons.length** times → options A and C are incorrect.

**Problem 5.16 – C**

**Given the following class:**

![](images/00417.jpeg)

**What is the result?**

A.0

B.01

C.012

D.The program runs but produces no output

E.Compilation fails

The `while` loop prints the var **a** each time it visits an element of the array → three elements → the output must contain three digits. The `break` statement is just chaff as it does nothing apart from sitting there trying to look important; we could remove it altogether.

**Problem 5.17 – D**

**Given:**

![](images/00418.jpeg)

**What is the result?**

A.1

B.10

C.The program enters an endless loop

D.Compilation fails

Any loop’s termination expression must evaluate to a `boolean`.

**Problem 5.18 – A**

**Given:**

![](images/00419.jpeg)

**How many LOCs fail compilation?**

A.None

B.One

C.Two

D.Three

E.Four

The first `while`’s termination expression generates a `boolean`, so this LOC is valid.

The second `while` evaluates at compile time to `while(true)`, which makes an endless loop – and that’s why we need `break`, otherwise the subsequent stats become unreachable.

There’s nothing special about the third `while`; the execution flow just doesn’t enter it, that’s all.

And finally, even though **Test** and **String** are incompatible data types, the method **equals()** accepts any **Object** and, therefore, is valid and will produce a `boolean`. The fact that **Test** and **String** are incompatible would have played crucial role in case of the ‘double equals’ op but this is entirely different story…

**Problem 5.19 – C**

**Given:**

![](images/00420.jpeg)

**What is the result?**

A.A D

B.B D

C.A C D

D.B C D

E.Compilation fails

The `break` stat does precisely nothing because it is the last statement in the loop; in fact, we could get rid of the second `if` as it adds not a single semantically meaningful feature to the business logic.

The only keyword that does come into play is `continue`: as soon as the first `if` sees "B", the current iteration terminates, and the loop visits another element.

**Problem 5.20 – D**

**Given:**

![](images/00421.jpeg)

**What statements should replace LOC1 and LOC2, respectively, in order to print** `12345`**?**

A.break, continue

B.break, break

C.continue, break

D.continue, continue

`break` makes the execution abandon the loop → there can be no `break` at LOC1 because the program will simply terminate as soon as it hits this keyword → options A and B are incorrect.

Now, we are charged with the task to print out all elements except the very first one → the execution shouldn’t terminate at any other element, be it 2, 3, 4 or 5 → LOC2 can’t read `break`, either, no matter what is the `if`'s expression.

**Problem 5.21 – A**

**Given the array:**

![](images/00422.jpeg)

**Which option prints** `orange pomelo pompia citron` **?**

![](images/00423.jpeg)

All we need here is prevent the flow from reaching the printing stat unless the element is exactly six letters long – and only option A answers this requirement.

**Problem 5.22 – B**

**Given the following classes in the same package:**

![](images/00424.jpeg)

**What is the result?**

A.The sequence 0 1 2 3 4 is printed once

B.The sequence 0 1 2 3 4 is printed twice

C.The sequence 0 1 2 3 4 5 is printed once

D.The sequence 0 1 2 3 4 5 is printed twice

The `for` loop iterates five times rather than six, therefore options C and D are out.

Now, since the instance variable **i** is automatically inited to the value of zero, the `while` loop executes twice → option B is the correct one.

On a final note, the loop var shadows the instance var **i**, so there’s no clash.

**Problem 5.23 – C**

**Given:**

![](images/00425.jpeg)

**What is the output?**

A.Jav8av8v8av88

B.Jav8Jav8Jav8Jav8Jav8

C.Java8

D.Compilation fails

`continue` is valid only inside loops, and here we have exactly that as the `switch` block is enclosed by a `for` loop, hence the code compiles.

What’s more, as `continue` is utterly irrelevant to `switch` and affects only loops, whenever the execution hits it, the loop immediately abandons the current iteration thus preventing the flow from falling through `switch` body → options A and B are incorrect.

**Problem 5.24 – A**

**Given:**

![](images/00426.jpeg)

**What is the result?**

A.3
23
123

B.30
230
1230

C.23
123

D.230
1230

The digit-printing stat is controlled by the `while` loop → at the very beginning, the value of the var **column** is three → C and D are out → `while` executes just once during the first iteration of the `for` loop → the first printed line must contain a single digit.

**Problem 5.25 – E**

**Given:**

![](images/00427.jpeg)

**What is the result?**

A.53

B.58

C.106

D.1013

E.Compilation fails

Yeah, this one is booby-trapped as only *labeled* `break`s are allowed outside a loop or, naturally, a `switch`. By re-writing line X as, say

![](images/00428.jpeg)

we could’ve made the code compile and print 1013.

* * *

^([78](#part0019_split_000.html_id_147)) It is not that `false` isn’t allowed in principle, no; it’s simply about unreacheable stats. E.g.: do { doStuff(); } while (false) // VALID because doStuff() is reachable

^([79](#part0019_split_000.html_id_145)) [https://docs.oracle.com/javase/specs/jls/se8/html/jls-14.html#jls-14.14.2](https://docs.oracle.com/javase/specs/jls/se8/html/jls-14.html#jls-14.14.2)

^([80](#part0019_split_000.html_id_149)) See the discussion here: [http://stackoverflow.com/questions/3831341/why-does-this-go-into-an-infinite-loop](http://stackoverflow.com/questions/3831341/why-does-this-go-into-an-infinite-loop)

^([81](#part0019_split_002.html_id_153)) missing curly braces: they are not mandatory for loops.

^([82](#part0019_split_002.html_id_151)) In retrospect, I can assure you that no question on the exam requires more than 30 seconds. If solution takes over two minutes, you overlooked a clue – or, worse, are doing something wrong.

![](images/00429.jpeg)

**The 1Z0-808 objectives within this group:**

| [6.1](#part0020_split_000.html_c6.1) | Create methods with arguments and return values, including overloaded methods; |
| [6.2](#part0020_split_002.html_c6.2) | Apply the `static` keyword to methods and fields; |
| [6.3](#part0020_split_004.html_c6.3) | Create and overload constructors, including impact on default constructors; |
| [6.4](#part0020_split_002.html_c6.4) | Apply access modifiers; |
| [6.5](#part0020_split_002.html_c6.5) | Apply encapsulation principles to a class; |
| [6.6](#part0020_split_000.html_c6.6) | Determine the effect upon object references and primitive values when they are passed into methods that change the values. |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

6.1Create methods with arguments and return values, including overloaded methods +

6.6Determine the effect upon object references and primitive values when they are passed into methods that change the values:

![](images/00012.jpeg)The structure of Java method declaration (left to right in the stated order unless noted otherwise):

![](images/00059.jpeg)an access modifier such as `public`, `protected` or `private`;

![](images/00059.jpeg)interface method modifier `default` (can be combined – redundantly – with `public` only)

![](images/00059.jpeg)an optional specifier such as `abstract`, `final` or `static` (NOTE: `final` and `static` may be combined);

![](images/00059.jpeg)optional specifier(s) may precede access modifier;

![](images/00059.jpeg)the return type such as `void` or another valid data type^([83](#part0020_split_006.html_id_156));

![](images/00059.jpeg)the method name, which is just another Java identifier, followed by a matching pair of parentheses to contain an optional list of the method arguments;

![](images/00059.jpeg)if the argument list is present, each argument must be specified by its data type (which can be a primitive or reference type) and its name;

![](images/00059.jpeg)unlike multiple variable declaration where we can state the data type just once if all the variables are of the same type, each method argument must have its own data type specified explicitly;

![](images/00059.jpeg)argument declarations are separated by commas;

![](images/00059.jpeg)after the closing parenthesis comes an optional list of exception types, which starts with the keyword `throws`;

![](images/00059.jpeg)unlike the `catch` block where a narrower exception type must appear before a wider type, the exception types thrown by the method may be declared in any order;

![](images/00059.jpeg)the body of any method must be enclosed by a pair of matching curly braces;

![](images/00059.jpeg)EXTRA: the method body can be completely empty or contain any number of the empty statements, that is, semicolons;

![](images/00012.jpeg)Only a single vararg is permitted in the list of arguments per method declaration; more than that, the vararg, when present, must be the last variable among the declared arguments.

![](images/00012.jpeg)Methods that do not return a value (`void` methods):

![](images/00059.jpeg)the body of such methods may contain an empty `return` statement, in other words, a `return` stat that is not followed immediately by a variable or literal;

![](images/00012.jpeg)Methods that return a value:

![](images/00059.jpeg)their bodies must contain a `return` stat immediately followed by an appropriate value^([84](#part0020_split_006.html_id_158))…

![](images/00059.jpeg)… which is passed back to the caller…

![](images/00059.jpeg)… who may elect to disregard it altogether or assign it to a variable. If such is the case, the var’s type must be compatible with the returned value’s type.

![](images/00012.jpeg)The `return` statement, when present, must be the last statement in the method body:

![](images/00430.jpeg)

![](images/00012.jpeg)Overloaded methods differ in their lists of arguments.

| **Corollary**: | An attempt to define multiple methods that differ only in their access modifiers, optional specifiers, return types, or thrown exceptions will cause a comperr. |

![](images/00012.jpeg)***Learn by heart***: In case of overloading, exact matches are used first, followed by wider primitives, then by autoboxing, and finally by varargs.

![](images/00012.jpeg)Since Java uses pass-by-value, calling a method creates copies of its parameters – and these copies are used then as the method’s arguments.

| **Corollaries**: | When a primitive is passed to a method, its value *never* changes for the caller. |
|  | When an object reference is passed to a method, changes in the object’s state might be reflected for the caller unless the called method assigns a new object reference to the passed-in argument *before* modifying its field(s). **Other wording**: invoking a method on a passed-in object can potentially change it. |

![](images/00012.jpeg)Known traps on the actual exam:

–the return type and method name are separated by an access modifier or optional specifier;

–more then one vararg is defined in the argument list;

–the vararg isn’t the last one in the argument list;

–the method body is missing a `return` stat although the method is declared as non-void;

–`return` is followed by some other – therefore unreachable! – stats;

–what `return` delivers is inconsistent with the method declaration (incompatible data types);

–methods differ only in their return types and, therefore, are not overloaded → comperr.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 6.1Given:**

![](images/00431.jpeg)

**Which three lines, when uncommented independently, can empty the bank account created on line 20?**

A.Line 22

B.Line 23

C.Line 24

D.Line 25

E.Line 26

F.Line 27

G.Line 28

H.Line 29

**Problem 6.2Given:**

![](images/00432.jpeg)

![](images/00433.jpeg)

**What is the result?**

A.200.0 vs 400.0

B.600.0 vs 800.0

C.1000.0 vs 400.0

D.Compilation fails

**Problem 6.3Given:**

![](images/00434.jpeg)

**What is the result?**

A.working with int: 3
working with float: 3.0

B.working with int: 3
working with double: 3.0

C.working with Integer: 3
working with double: 3.0

D.working with Integer: 3
working with float: 3.0

**Problem 6.4Given:**

![](images/00435.jpeg)

**What is the result?**

A.200 : 100

B.100 : 100

C.200 : 200

D.Compilation fails

**Problem 6.5**

**Suppose, a method is declared to take two arguments but the caller passes to it only one parameter. What is the result?**

A.Compilation fails.

B.The missing argument is given the default value for its declared type.

C.An IllegalArgumentException is thrown at run time.

D.A NoSuchMethodException is thrown at run time.

**Problem 6.6Given:**

![](images/00436.jpeg)

**What is the result?**

A.10 20 30 11 21 31 10 20 30

B.10 20 30 11 21 31 11 21 31

C.Compilation fails

D.A RuntimeException is thrown

**Problem 6.7Given:**

![](images/00437.jpeg)

**What is the result?**

A.a = 0, b = 0
a = 0, b = 0

B.a = 1, b = 2
a = 3, b = 4

C.a = 0, b = 0
a = 3, b = 4

D.a = 1, b = 2
a = 0, b = 0

**Problem 6.8Given:**

![](images/00438.jpeg)

**What is the result?**

A.double: 1.0

B.int: 1

C.String: 1.0

D.Compilation fails

**Problem 6.9**

**Which two are valid in the body of a method that does not return a value?**

A.Omission of the `return` statement

B.return `null;`

C.return `void;`

D.`return;`

**Problem 6.10**

**Which is the valid declaration of a method that takes two arguments of the type int and returns the result of their division?**

A.`divide (int a, int b) { return a/b; }`

B.`double divide (int a, b) { return a/b; }`

C.`int divide (int a, int b) { return a/b; }`

D.`double divide (int a, int b) { a/b; }`

E.`void divide (int a, int b) { return a/b; }`

F.None of the above

**Problem 6.11Given:**

![](images/00439.jpeg)

**This class fails compilation. What is the reason?**

A.There is no corresponding **setValue()** method

B.The method **getValue()** returns an incompatible data type

C.A static field cannot be declared `private`

D.The field value is uninitialized

E.The **main()** method has wrong signature

![](images/00061.jpeg) **CORE RULES (with some Extras):**

6.2Apply the static keyword to methods and fields +

6.4Apply access modifiers +

6.5Apply encapsulation principles to a class:

![](images/00012.jpeg)The `static` modifier is valid with variables, methods and initers but cannot be applied to the top-level classes and interfaces.

![](images/00012.jpeg)`static` fields are shared by all instances of a given class.

![](images/00012.jpeg)Since `static` fields and methods belong to the class, they can be accessed even without instantiating it first. When referenced from outside the class, they are called by using the class name, e. g. **java.lang.Math.PI** or **Math.random()**.

![](images/00012.jpeg)A `static` method may not call non-`static` variables or methods while the opposite is permitted. The exam tests us on at least three variants of this aspect: a `static` method accessing an instance var, a `static` method calling a non-`static` method and a non-`static` method either accessing a `static` field or invoking a `static` method.

![](images/00012.jpeg)Java allows to import `static` members by using the keywords `import static`.^([85](#part0020_split_006.html_id_160))

![](images/00012.jpeg)A method cannot be declared both `abstract` and `static`.

![](images/00012.jpeg)EXTRA: The `static` methods defined in classes are inherited in Java although they do not take part in polymorphism. The `static` methods defined in interfaces aren’t inherited.

![](images/00012.jpeg)The access modifiers control the accessibility of a given class and its members from outside the class and its package:

![](images/00059.jpeg)the `public` keyword means that the code is accessible from anywhere;

![](images/00059.jpeg)the `protected` keyword means the code is accessible by the classes or interfaces inside the same package or by the derived data types (that is, subclasses or subinterfaces);

| **Known trap on the exam**: | An attempt by a class instantiated outside its package to access its own `protected` member. |

![](images/00059.jpeg)the default (a.k.a. package-`private`) access is denoted by the absence of any access modifier and means that the code is accessible only from within the same package;

| **Known trap on the exam**: | An attempt to access a class defined using default access from outside its package. |

![](images/00059.jpeg)the `private` keyword means the code is visible only inside the same class.

| **Known trap on the exam**: | A subclass attempting to access a private member of its superclass. |

| **Combat versions**: | A non-`public` class can’t be accessed from outside its package. |
|  | `protected` members of a parent in a diff pack aren’t accessible to the child whose reftype is Parent. |

![](images/00012.jpeg)EXTRA: A `static` method invoked on a `null` object doesn’t throw an NPE (because the object isn't used in any way):

![](images/00440.jpeg)

![](images/00012.jpeg)Encapsulation prevents callers from modifying the instance variables *directly*.

![](images/00012.jpeg)Encapsulation is implemented by making instance vars `private` while providing `public` getters and/or setters.

![](images/00012.jpeg)EXTRA: Immutability refers to preventing callers from modifying the instance variables *at all* and is implemented by omitting setters or by making defensive copies:

![](images/00441.jpeg)

![](images/00012.jpeg)Properly encapsulated class exposes its state through methods.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 6.12Given:**

![](images/00442.jpeg)

**What is the result?**

A.10 20 30 40

B.30 20 30 40

C.A run-time exception is thrown

D.Compilation fails

**Problem 6.13Given two classes:**

![](images/00443.jpeg)

**How many LOCs in the class B fail compilation?**

A.None

B.One

C.Two

D.Three

E.Four

**Problem 6.14**

**What is the name of the Java concept that uses access modifiers to protect variables defined by a class?**

A.Abstraction

B.Encapsulation

C.Inheritance

D.Instantiation

E.Polymorphism

**Problem 6.15Given:**

![](images/00444.jpeg)

**What is the result?**

A.a = 20, b = 60
a = 60, b = 60
a = 40, b = 60

B.a = 20, b = 60
a = 60, b = 60
a = 0, b = 60

C.a = 20, b = 20
a = 60, b = 60
a = 40, b = 40

D.a = 20, b = 20
a = 60, b = 60
a = 0, b = 60

**Problem 6.16Given two classes:**

![](images/00445.jpeg)

**Which code block, when inserted at line X, will implement the following requirements?**

**1.The code should successfully update the water consumption bill (represented by the variable** `bill`**), which is defined as the number of cubic meters of water consumed by the customer (the variable** `m3`**) multiplied by the cost of water per cubic meter (the variable** `rate`**);**

**2.The code should also protect the variable** `bill` **from tampering such as attempting to decrease its value by an instance of the class WaterConsumer**.

![](images/00446.jpeg)

**Problem 6.17Given:**

![](images/00447.jpeg)

**What is the result?**

A.p1.count = 20, p2.count = 20

B.p1.count = 10, p2.count = 10

C.p1.count = 10, p2.count = 20

D.Compilation fails

**Problem 6.18Given:**

![](images/00448.jpeg)

**What is the result?**

A.No args! 1 1.0 "1"

B.Compilation fails on line 4

C.Compilation fails on lines 4 and 3

D.Compilation fails on lines 4, 3 and 2

E.Compilation fails on lines 4, 3, 2 and 1

**Problem 6.19Given the following class:**

![](images/00449.jpeg)

**Which two options, when used independently, will make this code compile and run?**

A.Replace line 2 with `public int a;`

B.Replace line 2 with `static int a;`

C.Replace line 4 with `static int a;`

D.Replace line 4 with `static double a;`

E.Replace line 5 with `a = 10.0d;`

F.Replace line 5 with `new A().a = 10;`

**Problem 6.20Given:**

![](images/00450.jpeg)

**Which two LOCs fail compilation?**

A.line 3

B.line 4

C.line 5

D.line 8

E.line 9

F.line 12

**Problem 6.21Given the contents of the file U.java:**

![](images/00451.jpeg)

**Which three LOCs fail compilation?**

A.line 1

B.line 2

C.line 3

D.line 4

E.line 5

F.line 6

**Problem 6.22Given:**

![](images/00452.jpeg)

**What is the result?**

A.42 42

B.40 41

C.41 40

D.43 44

**Problem 6.23Given the following two classes:**

![](images/00453.jpeg)

**What should be done to make the code compile?**

A.Make the class **A** `public`

B.Declare the **method run()** as `protected` instead of `private`

C.Make the **A()** constructor `public`

D.Make the **A()** constructor `protected`

E.Make the method **doStuff()** package-`private`

![](images/00061.jpeg) **CORE RULES (with some Extras):**

6.3Create and overload constructors, including impact on default constructors:

![](images/00012.jpeg)Unfortunately, the term "constructor" may be misleading as constructors do not ‘construct’ (read: ‘build’, ‘assemble’, ‘manufacture’, ‘fabricate’, ‘make’, or ‘create’) objects: they *initialize* them. The actual job of a constructor is to ensure that the freshly created object is in a valid state; it is usually done by setting object fields to certain initial values.

![](images/00012.jpeg)Constructors resemble methods (e.g., they accept arguments, can be overloaded and may throw exceptions that require handling in the TCF constructs) but they don’t specify a return type, not even `void`. In addition, ctors must share the same name with their class.

| **Known trap on the exam**: | As soon as a would-be constructor specifies a return type, the compiler stops treating it as a constructor even though it shares the same name with the class → whenever you think you see a constructor, double check it’s not a method. |

![](images/00012.jpeg)A default, no-arg constructor is implicitly declared in the class that doesn’t define any constructor explicitly.

| **Known traps on the exam**: | The default constructor is the one that is provided automatically by the compiler → even if an explicitly defined constructor specifies no arguments, it cannot be called the default constructor. |
|  | Whenever superclass doesn’t define a no-arg ctor in parallel to other constructors, explicit call to an appropriate parent ctor must be provided in the child’s constructors whose bodies don’t start with `this()`. |

![](images/00012.jpeg)The default constructor has the same accessibility as the class.

| **Corollary**: | Since the humanware-defined no-arg constructor isn’t the default one, the above rule doesn’t apply to it. ← ***known trap on the exam*** |
| **Combat rule**: | Different packages? Watch out! If **Parent** defines a package-`private` no-arg ctor, **Child** won’t be able to access it: |

![](images/00454.jpeg)

![](images/00012.jpeg)EXTRA: Constructors are not inherited.

![](images/00012.jpeg)Constructors accept access modifiers only.

| **Corollary**: | Unlike regular methods, constructors may not be declared `abstract`, `static` or `final`. |

![](images/00012.jpeg)A matching pair of parentheses is mandatory for a constructor.

![](images/00012.jpeg)A class can have multiple constructors. Just like regular methods, they are overloaded by using different lists of arguments.

![](images/00012.jpeg)Overloaded constructors invoke each other by using the keyword `this()`, which should be the first stat in the caller’s body.

| **Corollaries**: | A constructor may not call another constructor by using its class name. An attempt by a regular method to use `this()` will cause a comperr. |

![](images/00012.jpeg)Constructors can differentiate between their arguments and instance vars by prepending the instance var’s name with the keyword `this` followed by a dot.

![](images/00012.jpeg)EXTRA: Constructors can declare local variables (whose scope is therefore limited to the constructor), which will shadow the similarly named fields.

![](images/00012.jpeg)EXTRA: Polymorphisms extends to the constructors, too. (The subject will be discussed in more detail in the next group of Exam Objectives, *Working with Inheritance*).

![](images/00012.jpeg)EXTRA: Constructors can throw exceptions. The exception-wise rule in ctors, however, is opposite to what we have for methods: an overriding method cannot throw a new or superclass ChE, whereas a subclass ctor cannot throw subclass ChE unless the same ChE or its superclass is declared in the subclass constructor’s `throws` clause. Note that just like in the case of method overriding, this rule doesn’t involve RTEs:

![](images/00455.jpeg)

Observe that although the subclass throws an AIOOBE, which is narrower than the IOOBE thrown by the superclass, line 12 compiles just fine because we are dealing with RTEs.

On the other hand, lines 9 and 16 throw the comperr "unreported exception IOException; must be caught or declared to be thrown" – which is actually misleading. Yes, again.

You see, we can only declare but not catch this ChE, and the comperr on line 18 explains why: "call to super must be first statement in constructor". Hence, our TCF construct won’t work at all and we are left with only one option: declare the same ChE or its superclass, which is exactly what line 11 does.

![](images/00012.jpeg)Although constructors routinely function as initializers, a class can define separate initializer blocks, which can be either `static` or non-`static`.

![](images/00012.jpeg)An initializer block can declare local vars, access both `static` and instance fields or call `static` and non-`static` methods (the rule of non-`static` entities in `static` context still applies), define loops, conditional and TCF constructs.

![](images/00012.jpeg)The order of precedence when instantiating a class^([87](#part0020_split_006.html_id_162)):

![](images/00059.jpeg)`static` initers for the *entire* inheritance chain; it is done only once;

![](images/00059.jpeg)instance initers for the superclass;

![](images/00059.jpeg)superclass constructors;

![](images/00059.jpeg)instance initers for the subclass;

![](images/00059.jpeg)subclass constructors;

| **Corollaries**: | Instance initers run for every object that is being created. |
|  | Constructors run after all other initers within the same class. |

![](images/00012.jpeg)EXTRA: `static` initers of a class are not executed unless you access something that belongs to this particular class.

| **Corollary**: | Simply declaring a refvar isn’t enough for `static` initers start running. |

![](images/00012.jpeg)`final` ***non-local*** vars must be inited even if they are never used:

![](images/00456.jpeg)

Where and how this initing is done depends on whether the var is `static` or not:

![](images/00059.jpeg)`final` instance vars can be inited in THREE places:

-at the point of declaration,

-in instance initers, and

-in constructors.

![](images/00059.jpeg)`final static` vars can be inited in TWO places only:

-at the point of declaration,

-in static initers.

Pay attention: `final static` vars can’t be inited in constructors or instance initers. Which is understandable as `static` fields must be available to callers even in the absence of the instances of the class whereas instance initers and then constructors run only when an object is being created:

![](images/00457.jpeg)

By the way, in the preceding example the compiler complains of an attempt to modify a `final` var. It is interesting to note that if we comment out the `static` initer, the compiler produces yet another misleading error message: "variable **str** not initialized in default constructor". Well, you know, it can’t be inited there in the first place^([88](#part0020_split_006.html_id_164)); compare it to the following case:

![](images/00458.jpeg)

Here the error message on the line that defines the no-arg constructor quite correctly says that "variable **str** might not have been initialized".

Alright, putting this rule out in code:

![](images/00459.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 6.24Given the following code fragment:**

![](images/00460.jpeg)

**What is the result?**

A.Alice 0 Bob 62

B.Compilation fails only on line E1

C.Compilation fails only on line E2

D.Compilation fails at both line E1 and line E2

**Problem 6.25Given:**

![](images/00461.jpeg)

**What is the result?**

A.Hi!

B.Hello!

C.No output

D.Compilation fails

E.A RuntimeException is thrown

**Problem 6.26Given:**

![](images/00462.jpeg)

**Which class has a default constructor?**

A.Only A

B.Only B

C.Only C

D.A and B

E.B and C

F.A and C

G.All three of them

**Problem 6.27Given the contents of four source code files:**

![](images/00463.jpeg)

**Which class definition, when inserted at line C1, will enable the code to compile?**

A.`class C extends A { }`

B.`class C extends B { }`

C.`class C extends D { }`

D.`class C extends E { }`

E.None of the above

**Problem 6.28Given two classes:**

![](images/00464.jpeg)

**Which option, when inserted at line XXX, will enable the class Scheduler to print** `Bob in 2016: [1Z0-808, 1Z0-809]`**?**

A.private Exams(String name, int year, List exams){

B.public void Exams(String name, int year, List exams){

C.Exams(String name, int year, List exams){

D.Exams(String name, int year, ArrayList exams){

**Problem 6.29Given:**

![](images/00465.jpeg)

**Which modification will make the code compile and print** `Hello`**?**

A.Remove the **Parent()** constructor

B.Make the **Child()** constructor `public` instead of `private`

C.Add the modifier `protected` to the **Parent()** constructor

D.Remove the **Child()** constructor

E.Remove the modifier `private` from the **Child()** constructor

**Problem 6.30**

**Which statement is true about the default constructor?**

A.It can take arguments.

B.It has implicit public access modifier in its declaration.

C.It can be added by the programmer.

D.The default constructor of a subclass always invokes the no-arg constructor of its superclass.

**Problem 6.31Given:**

![](images/00466.jpeg)

**Which two LOCs can be added independently at line X?**

A.`Child() {}`

B.`Child(int a) { this.b = a; }`

C.`Child(int b) { this.a = b; }`

D.`Child(int b) { super(Math.PI > Math.E ? 3 : 2); }`

E.`Child(int c) { this(c = 1, c = 2 ); }`

**Problem 6.32Given:**

![](images/00467.jpeg)

**What is the result?**

A.i iaou iaouaoe

B.i iiaou iiaouaoe

C.i iaou iaouiaoe

D.i aiou aioue

**Problem 6.33Given:**

![](images/00468.jpeg)

**What is the result?**

A.a = 40, b = 40

B.a = 40, b = 60

C.a = 60, b = 40

D.Compilation fails

**Problem 6.34**

The ***Real World Scenario*** sidebar on page [208](#part0019_split_002.html_page_208) in the *OCA Study Guide* by Jeanne Boyarsky and Scott Selikoff discusses the so-called defensive copy^([89](#part0020_split_006.html_id_168)) and provides this example:

![](images/00469.jpeg)

Now, the Constructor Summary for the class **StringBuilder**^([90](#part0020_split_006.html_id_166)) says the class defines four constructors none of which lists a **StringBuilder** object as its argument:

![](images/00470.jpeg)

Hence the question: **Is line XXX valid?**

A.Oh yes, most definitely; after all, the authors of any study guide written to the masses should know what they are talking about…

B.Hell, no; it should’ve been `return new StringBuilder(builder.toString());`

**Problem 6.35Given:**

![](images/00471.jpeg)

**What is the result?**

A.A

B.Hello from A

C.Hello from C A

D.Hello from B C A

**Problem 6.36Given:**

![](images/00472.jpeg)

**What is the result?**

A.str=null sb=null

B.str=aaa sb=null

C.str=aaa sb=bbb

D.str=aaa sb=aaabbb

E.str=aaa sb=bbbaaabbb

F.Compilation fails

G.A NullPointerException is thrown at runtime

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 6.1 – DGH**

**Given:**

![](images/00473.jpeg)

**Which three lines, when uncommented independently, can empty the bank account created on line 20?**

A.line 22

B.line 23

C.line 24

D.line 25

E.line 26

F.line 27

G.line 28

H.line 29

Line 22 doesn’t compile because a) the method **main()** is `static` but `this` by definition refers to an instance, and b) the var **balance** is itself defined in the class **BankAccount** rather than **HighRoller**.

The problem with line 23 is somewhat similar to what we have on line 22: the var **balance** is an instance field and therefore can’t be accessed by prepending its class name.

Line 24 is also invalid since the class **BankAccount** doesn’t define a constructor that takes an `int`.

The totally outlandish line 26 attempts to assign zero to the method **getBalance()**, which itself returns an `int`.

And finally, line 27 simply adds zero to the var **balance**, thus not affecting it in the slightest.

It should be noted in passing that the class **BankAccount** is improperly encapsulated, and line 25 clearly illustrates this: instead of being able to access the var **balance** only through a `public` method like line 29 does, **HighRoller** has full direct control over **balance** because the var wasn’t declared `private`.

**Problem 6.2 – C**

**Given:**

![](images/00474.jpeg)

**What is the result?**

A.200.0 vs 400.0

B.600.0 vs 800.0

C.1000.0 vs 400.0

D.Compilation fails

The method **breakRecord()** takes in two args: one is a reftype and the other is a primitive. Since Java is always pass-by-value, whatever happens to a primitive arg isn’t reflected in the caller but in our case the method **breakRecord()** affects the instance field **speed** by accessing it through a copy of the reference that points to the object **sb** created on line b1\. As the result, the value of **speed** becomes 200.0f + 400.0f*2 = 1000.0f.

**Problem 6.3 – B**

**Given:**

![](images/00475.jpeg)

![](images/00476.jpeg)

**What is the result?**

A.working with int: 3
working with float: 3.0

B.working with int: 3
working with double: 3.0

C.working with Integer: 3
working with double: 3.0

D.working with Integer: 3
working with float: 3.0

When it comes to executing an overloaded method (or a constructor, for that matter), Java always starts looking for the exact match. Failing that, it attempts to use a wider primitive, then autoboxing and, finally, a vararg. Here, both calls to the overloaded versions of **run()** have found their exact matches.

**Problem 6.4 – A**

**Given:**

![](images/00477.jpeg)

**What is the result?**

A.200 : 100

B.100 : 100

C.200 : 200

D.Compilation fails

Changes to a primitive arg are never reflected in the caller, which immediately limits us to only two choices – options A and B – because the second printing stat must output the unmodified value of the variable **a**.

**Problem 6.5 – A**

**Suppose, a method is declared to take two arguments but the caller passes to it only one parameter. What is the result?**

A.Compilation fails.

B.The missing argument is given the default value for its declared type.

C.An IllegalArgumentException is thrown at run time.

D.A NoSuchMethodException is thrown at run time.

The answer is obvious. I included this question for one simple reason: to have an opportunity to talk a bit more about method calls. Consider it as a small print that helps to look at method invocation from another angle.

Method invocations are resolved at both compile and run time. The compiler concerns itself with overloading while the JVM deals with overriding (which we will be discussing in the next [Chapter](#part0021_split_000.html_page_270)). Resolving a method name at compile time is performed in several steps:

–first, the compiler determines which class or interface is to be looked into;

–then the type determined in the previous step is scanned for member methods by using the name of the method and the argument expressions. The compiler wants methods that are both *accessible* and *applicable*; in other words, it looks for declarations that can be correctly invoked on the list of the given arguments;

–finally, the compiler decides whether the chosen method is appropriate by checking the compatibility of an argument to a method invocation with its target type.

Unlike overloading, overriding involves also the return type and `throws` clause.

So far so good; now for the fun part. This is what the JLS8 says:

The descriptor (signature plus return type) of the most specific method is the one used at run time to perform the method dispatch^([91](#part0020_split_006.html_id_174)).

And this what can be found in the JVM8 Spec:

A method signature encodes type information about a (possibly generic) method declaration. It describes any type parameters of the method; the (possibly parameterized) types of any formal parameters; the (possibly parameterized) return type, if any; and the types of any exceptions declared in the method’s throws clause.^([92](#part0020_split_006.html_id_172))

There you have it – the Big Divide between the legislative and executive branches of the Java Republic: the language specification, which defines what Java is, says the method signature excludes the return type, while the JVM thinks otherwise. I say, it’s a wonder our programs run at all…

Although this stuff isn’t on the 1Z0-808 exam, it is still nice to know that the Java ecosystem is full of contradictions, which means it is bound to develop further – at least if Hegel is to be believed^([93](#part0020_split_006.html_id_170)).

**Problem 6.6 – B**

**Given:**

![](images/00478.jpeg)

**What is the result?**

A.10 20 30 11 21 31 10 20 30

B.10 20 30 11 21 31 11 21 31

C.Compilation fails

D.A RuntimeException is thrown

An array is an **Object** and, as such, can be changed even though the method **modify()** works with a copy of the array’s reference variable. We could even declare the array `final`, and its slots would be still modifiable.

**Problem 6.7 – C**

**Given:**

![](images/00479.jpeg)

**What is the result?**

A.a = 0, b = 0
a = 0, b = 0

B.a = 1, b = 2
a = 3, b = 4

C.a = 0, b = 0
a = 3, b = 4

D.a = 1, b = 2
a = 0, b = 0

The method **run1()** doesn’t affect the fields because it assigns the passed-in values to the local vars, which cease to exist after the method terminates.

On the contrary, the method **run2()** acts on `this`, which is a reference that points to the current object. Although `this` is `final` by definition, we still can change its fields.

**Problem 6.8 – D**

**Given:**

![](images/00480.jpeg)

**What is the result?**

A.double: 1.0

B.int: 1

C.String: 1.0

D.Compilation fails

The methods are overloaded incorrectly: they all take in a single parameter of the type `double`. This is why the compiler generates the same error message twice, "method **run(**double**)** is already defined in class **OverloadTester**".

**Problem 6.9 – AD**

**Which two are valid in the body of a method that does not return a value?**

A.Omission of the `return` statement

B.`return null;`

C.`return void;`

D.`return;`

`return null` does return a value. As for the keyword `void`, it is used in method declarations only. And lastly, an empty `return` is allowed.

**Problem 6.10 – C**

**Which is the valid declaration of a method that takes two arguments of the type int and returns the result of their division?**

A.`divide (int a, int b) { return a/b; }`

B.`double divide (int a, b) { return a/b; }`

C.`int divide (int a, int b) { return a/b; }`

D.`double divide (int a, int b) { a/b; }`

E.`void divide (int a, int b) { return a/b; }`

F.None of the above

Although returning an `int` will most likely screw up business logic, it is still valid. As for option A, it omits return type in the method’s declaration. Option B specifies its arguments incorrectly, option D has no `return` statement even though the declaration does promise that the method returns something, and option E attempts to return a value while the declaration says it won’t.

**Problem 6.11 – B**

**Given:**

![](images/00481.jpeg)

**This class fails compilation. What is the reason?**

A.There is no corresponding `setValue()` method

B.The method `getValue()` returns an incompatible data type

C.A `static` field cannot be declared `private`

D.The field’s value is uninitialized

E.The `main()` method has wrong signature

The variable **value** is of type `double`, which cannot be implicitly narrowed to `int` so the return type of the method **getValue()** clashes with the method’s declaration. To make the code work, we could explicitly cast **value** to `int` or change the return type to `double`.

**Problem 6.12 – B**

**Given:**

![](images/00482.jpeg)

![](images/00483.jpeg)

**What is the result?**

A.10 20 30 40

B.30 20 30 40

C.A run-time exception is thrown

D.Compilation fails

The array **a** is `static` and, therefore, all instances of the class share it. This is why the statement that assigns 30 to the fourth slot in **a** by acting on the refvar **t2**, also affects **a**[3] in the object **t1**.

**Problem 6.13 – D**

**Given two classes:**

![](images/00484.jpeg)

**How many LOCs in the class B fail compilation?**

A.None

B.One

C.Two

D.Three

E.Four

The `private` variable **d** is by definition accessible only inside the class that declares it. The package-`private` variable **c** is again by definition available only to the classes inside the same package.

As for the `protected` variable **b**, it cannot be accessed through **obj** because the reference type of this object is **A**. In the next [chapter](#part0021_split_000.html_page_270) we will be talking in more detail about inheritance and its subtleties so right now it should be sufficient to recall that it is the reftype that says what’s available to the object. Being `protected`, the variable **b** is by definition available to the classes inside the same package or to the data types derived from **A**. And since **A** is obviously not its own subclass, the object **obj** cannot see **b**. Had line 5 declared the object **obj** being of type **B**, line 7 would have compiled.

**Problem 6.14 – B**

**What is the name of the Java concept that uses access modifiers to protect variables defined by a class?**

A.Abstraction

B.Encapsulation

C.Inheritance

D.Instantiation

E.Polymorphism

The question may seem surprisingly simple; there exists, however, much confusion about the precise nature of relation between abstraction and encapsulation. As if to complicate things even further, the terms *encapsulation* and *information hiding* are often used interchangeably, so it is theoretically possible that on the actual exam you’ll encounter something about information hiding. I didn’t but who knows what’s going to be in your case…

*Encyclopedia of Computer Science and Technology* by Harry Henderson (2009) says that encapsulation "…both protects code from uncontrolled modification or access and hides information (details) that programmers who simply want to use functionality don’t need to know about". It becomes apparent that encapsulation is wider than just data protection or data hiding.

If you want more, here’s a good read on the subject although it was published a quarter of a century ago when Java didn’t even exist: Berard, E. V. “Abstraction, Encapsulation, and Information Hiding.” White paper, Berard Software Engineering, Inc., Baithersburg, MD, 1991.^([94](#part0020_split_006.html_id_176))

**Problem 6.15 – B**

**Given:**

![](images/00485.jpeg)

**What is the result?**

A.a = 20, b = 60
a = 60, b = 60
a = 40, b = 60

B.a = 20, b = 60
a = 60, b = 60
a = 0, b = 60

C.a = 20, b = 20
a = 60, b = 60
a = 40, b = 40

D.a = 20, b = 20
a = 60, b = 60
a = 0, b = 60

This question resembles [Problem 6.12](#part0020_split_006.html_id_323)although here we are dealing with primitives. Both variables **a** and **b** get explicitly initialized in the same constructor but the var **b** is `static` and this complicates things. In addition, the printing stats run only after all the operations that affect our three objects have been executed.

When the first object is created, both fields are assigned the same value of 20 because non-`final` non-local variables are inited implicitly and `if(0<20)` evaluates to `true`. The second time the constructor is called, the value of **b** (which equals 20) is still less than **input** (which is 60) so both vars get the same values again. Since **b** is `static`, its current value, 60, is shared by both objects.

The situation changes when the constructor initializes the third object: as 40 is less than 60, the assignments are not executed. Being `static` and, therefore, common for all instances of the class, the variable **b** remains equal to 60, while the variable **a** is left without explicit initialization thus retaining its default value of zero.

**Problem 6.16 – B**

**Given two classes:**

![](images/00486.jpeg)

**Which code block, when inserted at line X, will implement the following requirements?**

**1.The code should successfully update the water consumption bill (represented by the variable** `bill`**), which is defined as the number of cubic meters of water consumed by the customer (the variable** `m3`**) multiplied by the cost of water per cubic meter (the variable** `rate`**);**

**2.The code should also protect the variable** `bill` **from tampering such as an attempt to decrease its value by an instance of the class WaterConsumer**.

![](images/00487.jpeg)

As encapsulation is best achieved by making instance fields `private` and providing `public` getters and setters, we will solve this problem by applying these principles methodically.

Option C can be eliminated at once because the method **updateBill()** is `private` and no other class will be able to call it.

Option A does not check the method arg thus making the calculation algorithm vulnerable to an attack: the object **wcons** just might pass a negative value in an attempt to lower the water bill.

And finally, although option D does make such a check in its **updateBill()** method, it still leaves the var **bill** wide open because anyone can invoke the public method **calcBill()** with a negative argument.

**Problem 6.17 – A**

**Given:**

![](images/00488.jpeg)

**What is the result?**

A.p1.count = 20, p2.count = 20

B.p1.count = 10, p2.count = 10

C.p1.count = 10, p2.count = 20

D.Compilation fails

The question asks about the value of the same `static` variable, hence option C is immediately out. Calling the loop twice makes the answer obvious.

**Problem 6.18 – D**

**Given:**

![](images/00489.jpeg)

**What is the result?**

A.No args! 1 1.0 "1"

B.Compilation fails on line 4

C.Compilation fails on lines 4 and 3

D.Compilation fails on lines 4, 3 and 2

E.Compilation fails on lines 4, 3, 2 and 1

This question is to the tune of [Problem 6.13](#part0020_split_006.html_id_324)but concerns methods rather than fields. The situation is quite similar: we have two classes in different packages → `private` and package-`private` members are inaccessible → lines 3 and 4 fail compilation.

The `protected` method **run(int arg)** is also inaccessible because no type can be its own child.

**Problem 6.19 – BF**

**Given the following class:**

![](images/00490.jpeg)

**Which two options, when used independently, will make this code compile and run?**

A.Replace line 2 with `public int a;`

B.Replace line 2 with `static int a;`

C.Replace line 4 with `static int a;`

D.Replace line 4 with `static double a;`

E.Replace line 5 with `a = 10.0d;`

F.Replace line 5 with `new A().a = 10;`

One of the most ‘popular’ coding blunders is asking a `static` method to access something non-`static`. The exam has at least two questions on this subject: one uses instance variables (like the current Problem) and the other instance methods.

Option A does not help because the var **a** remains non-`static`. Options C and D are simply illegal as the only modifier that is accepted inside a method is `final`. As for option E, it does not address the real problem.

Option F is perfectly valid although it makes line 4 redundant.

**Problem 6.20 – BE**

**Given:**

![](images/00491.jpeg)

**Which two LOCs fail compilation?**

A.line 3

B.line 4

C.line 5

D.line 8

E.line 9

F.line 12

Here we have the second version of the exam problem that tests us on the ‘non-`static` in `static` context’ compile-time error.

Since **run3()** is an instance method, **run1()** should've invoked it on an object. As for **run2()**, it calls **run3()** as if the method were indeed `static`, in other words, by prepending its class name.

**Problem 6.21 – DEF**

**Given the contents of the file U.java:**

![](images/00492.jpeg)

**Which three LOCs fail compilation?**

A.line 1

B.line 2

C.line 3

D.line 4

E.line 5

F.line 6

Only nested classes and interfaces may be declared `private`, `protected` or `static`.

**Problem 6.22 – A**

**Given:**

![](images/00493.jpeg)

**What is the result?**

A.42 42

B.40 41

C.41 40

D.43 44

As any `static` member can be accessed through an object or by its class name, the printing stat outputs the same value twice thus immediately eliminating options B, C and D. Another approach to solving this Problem is by noticing that two increments followed by two decrements bring the value of **a** back to its starting point…

**Problem 6.23 – B**

**Given the following two classes:**

![](images/00494.jpeg)

**What should be done to make the code compile?**

A.Make the class **A** `public`

B.Declare the **method run()** as `protected` instead of `private`

C.Make the **A()** constructor `public`

D.Make the **A()** constructor `protected`

E.Make the method **doStuff()** package-`private`

Because both classes are in the same package, options A, C, D and E cannot help: they are missing the real target.

The true cause of the compilation failure is the `private` nature of **run()**, which doesn’t let the class **B** inherit this method.

**Problem 6.24 – D**

**Given the following code fragment:**

![](images/00495.jpeg)

**What is the result?**

A.Alice 0 Bob 62

B.Compilation fails only on line E1

C.Compilation fails only on line E2

D.Compilation fails at both line E1 and line E2

This is an example of an exam question that omits definitions of certain methods and uses just a placeholder instead. If I remember correctly, I met it only once, on the second sitting, which just might mean it’s ungraded…
I also can’t recall if the actual exam uses the `@Override` annotation but I placed it here anyway to remind you to pay attention to the signature of the **Object**’s **toString()** method; one of the exam questions relies on it.

Now, to the task at hand. Line E1 is invalid because the class never defines an explicit no-arg constructor. The *default* constructor isn’t available, either, since the compiler inserts it when the data type in question defines no constructors at all.

Line E2 also fails compilation because we may not call constructors by using the class name; the keywords `this()` and `super()` are to be used, instead.

And on a final note, the missing definitions of the accessors and mutators could be written like this:

`public void setName(String name){ this.name = name;}`
`public void setScore(int score){ this.score = score; }`
`public String getName(){ return this.name; }`
`public int getScore(){ return this.score; }`

**Problem 6.25 – A**

**Given:**

![](images/00496.jpeg)

**What is the result?**

A.Hi!

B.Hello!

C.No output

D.Compilation fails

E.A RuntimeException is thrown

This is just a simple illustration of an instance field initialization through a constructor. No traps or nasty tricks.

**Problem 6.26 – A**

**Given:**

![](images/00497.jpeg)

**Which class has a default constructor?**

A.Only A

B.Only B

C.Only C

D.A and B

E.B and C

F.A and C

G.All three of them

The Java Language Specification, §8.8.9, *Default Constructor*, says that

If a class contains no constructor declarations, then a default constructor is implicitly declared.

When studying constructors for the exam, I found out that many questions can be solved faster when I think of the default constructor as an invisible self-proclaimed Beauty Queen who just hates and fears competitors:

–the default constructor is invisible, ain’t it?

–and if another constructor appears on the podium, Def Con never attends that particular beauty pageant.

So, as option A defines no constructors whatsoever, Def Con reigns uncontested inside the class **A**. By the same token, since both options B and C do define constructors, Def Con thinks she is way too smashing and noble to keep them company.

**Problem 6.27 – C**

**Given the contents of four source code files:**

![](images/00498.jpeg)

**Which class definition, when inserted at line C1, will enable the code to compile?**

A.`class C extends A { }`

B.`class C extends B { }`

C.`class C extends D { }`

D.`class C extends E { }`

E.None of the above

A non-`public` class^([95](#part0020_split_006.html_id_178)) in a different package is inaccessible; this is arguably one of the most important rules for the exam. Following it, we can see that option A is incorrect.

Option B doesn’t work because the class B is `final` and cannot be extended by definition.

Now to option D; while the class E is `public` and hence accessible from outside its package, its no-arg constructor is `private` and therefore unavailable to the class C. The following class definitions would have worked, though:

![](images/00499.jpeg)

Please recall that unlike the default constructor, which shares the level of access with its class, non-default constructors are exempt from this rule; that’s why we had to add the `public` modifier to the constructor declaration on line XXX. The modifier `protected` would also help.

And finally, there’s nothing wrong with option C because it is just natural to extend an abstract class (after all, how else one could implement its abstract methods, huh?). Although the declaration `private void D()` resembles a non-arg constructor, it defines a return type and, therefore, is still a method that just happens to share the same name with its class. What’s more, because the class **D** is `public`, its default constructor is also `public` and hence accessible to the class **C**.

**Problem 6.28 – C**

**Given two classes:**

![](images/00500.jpeg)

![](images/00501.jpeg)

**Which option, when inserted at line XXX, will enable the class Scheduler to print** `Bob in 2016: [1Z0-808, 1Z0-809]`**?**

A.private Exams(String name, int year, List exams){

B.public void Exams(String name, int year, List exams){

C.Exams(String name, int year, List exams){

D.Exams(String name, int year, ArrayList exams){

Since the constructor in option A is `private`, the class **Scheduler** will not be able to access it.

Option B defines a method rather than a constructor, and option D wants an **ArrayList** while the call to the constructor provides just a **List**.

**Problem 6.29 – C**

**Given:**

![](images/00502.jpeg)

**Which modification will make the code compile and print** `Hello`**?**

A.Remove the **Parent()** constructor

B.Make the **Child()** constructor `public` instead of `private`

C.Add the modifier `protected` to the **Parent()** constructor

D.Remove the **Child()** constructor

E.Remove the modifier `private` from the **Child()** constructor

Two classes in different packages again… This means we should be on alert for potential problems with accessibility. One of the traps on the exam is build upon the rule that says that the default constructor has the same access level as its class whereas an explicitly declared no-arg constructor loses the default accessibility associated with its class, so the following won’t compile:

![](images/00503.jpeg)

![](images/00504.jpeg)

In our case, the superclass **Parent** is declared `public` but doesn’t have the default constructor (which would be also `public`). Instead, the class **Parent** explicitly defines a no-arg constructor and makes it package-`private` thus effectively preventing the class **Child** from accessing it. All we need is make the explicit no-arg constructor in **Parent** accessible → all options except C are eliminated.

Naturally, we could make the **Parent()** constructor `public` instead of `protected`; it would have worked, too.

**Problem 6.30 – D**

**Which statement is true about the default constructor?**

A.It can take arguments.

B.It has implicit public access modifier in its declaration.

C.It can be added by the programmer.

D.The default constructor of a subclass always invokes the no-arg constructor of its superclass.

The default constructor is by definition a no-arg constructor so option A is out. Since it shares the same access level with the class, option B is also incorrect. And because the default constructor is added by the compiler only, we can rid of option C, as well.

Much more interesting is the correct option D as it reminds us that there’s more in the code than meets the eye:

![](images/00505.jpeg)

The superclass for **A** is the class **Object** whose javadocs description is probably the shortest of all:

Class **Object** is the root of the class hierarchy. Every class has **Object** as a superclass. All objects, including arrays, implement the methods of this class.

**Problem 6.31 – DE**

**Given:**

![](images/00506.jpeg)

**Which two LOCs can be added independently at line X?**

![](images/00507.jpeg)

Option A illustrates the trap that you will most definitely meet on the exam: the compiler always tries to stick a no-arg call to `super()` into every available constructor it sees. By being available I mean that the constructor does not have its own call to `super()` or `this()` regardless of the number of args in it.

In our case (we are still talking about option A), since the class **Parent** doesn’t have a no-arg constructor, adding a no-arg ctor to the class **Child** throws a comperr.

Options B and C suffer from exactly same problem: although the compiler wants to insert a no-arg call to `super()`, the class **Parent** doesn’t have a matching constructor.

The only cases when the compiler won’t throw a tantrum are options D and E: their own calls to `super()` and `this()` prevent the compiler from inserting blindly a no-arg call to `super()`. After all, since a call to `super()` or `this()` must be the first statement in any constructor’s body, no constructor may have *two* such calls in it.

**Problem 6.32 – A**

**Given:**

![](images/00508.jpeg)

**What is the result?**

A.i iaou iaouaoe

B.i iiaou iiaouaoe

C.i iaou iaouiaoe

D.i aiou aioue

This problem is probably twice as hard as the actual exam’s question that deals with the order of initialization – if you ever encounter it, that is; because I met such a question only once. Anyway, to crack it, we should keep in mind four simple rules:

| Rule 1: `static` initializers start running first, and they do it only once; |
| Rule 2: they run one after another in the declared order for the entire inheritance chain; |
| Rule 3: then the instance initializers kick in for every object that is being created; |
| Rule 4: the constructors are the last to run. |

Putting it out in code:

![](images/00509.jpeg)

The code prints:

![](images/00510.jpeg)

![](images/00511.jpeg)

According to Rules 1 and 2, when the JVM begins executing the code at its entry point, which is the method **main()**, the static initers for all three classes come into play, starting with **Grandpa**, followed by **Father** and finishing with **Grandson**. It does look as if the static initers run as soon as the class is accessed but, in fact, the process is more complicated. This is what the JLS says^([96](#part0020_split_006.html_id_180)):

A class or interface type T will be initialized immediately before the first occurrence of any one of the following:

• T is a class and an instance of T is created.

• A static method declared by T is invoked.

• A static field declared by T is assigned.

• A static field declared by T is used and the field is not a constant variable.

There are a few more circumstances under which the initialization occurs but they are too advanced for our discussion. Anyway, we can see that in our case it is the second condition that causes the static initers to run: "a static method declared by T is invoked" – and **main()** is static.

The JLS adds that

When a class is initialized, its superclasses are initialized (if they have not been previously initialized)

which explains why all *three* classes in the above example run their static initers. It also becomes clear why the following code prints "Hello from Base!" only once:

![](images/00512.jpeg)

Getting back to the previous example. After the static initers finish their job, the JVM moves its attention to the contents of the method **main()**, which prints a message that the program is about to start creating objects. Rules 3 and 4 dictate that any object is initialized beginning from its superclass, and this is exactly what we have: first the instance initers for the class **Grandpa** run in the declared order, then the **Grandpa**’s constructor follows – and the process is repeated for the classes **Father** and **Grandson**. The exact same thing happens when the JVM creates the second object.

All in all, the order of initialization boils down to the following chain of events:

![](images/00513.jpeg)

Now it’s time to look at our problem again. The process starts with assigning an empty string to the static field **word** just to make it non-`null`, otherwise our printing stats would output something like ‘`null`*followed-by-other-things*’.

Then the static initer on line h3 executes adding **i** to the still empty **word**, thus making its value equal to "i". At this point we run out of static initializers, be it simple declarations or entire blocks, and so the method **main()** executes line t1 thus printing the static var **word** followed by a white space, that is, "i ".

Next comes line t2 who wants to create a **Hamlet** object by calling a single-arg constructor and passing it a parameter of type **String**. This launches a whole new chain of events, this time involving instance initers and a constructor. Since the field **word** is `static`, it retains its previous value "i" to which the instance inters add "a" (line h2) and then "o" (line h4), after which the constructor on line h1 concatenates it with "u". At this point the value of **word** becomes equal to "iaou", so the printing stat on line t3 happily outputs it and adds a trailing white space → options B and D are eliminated.

When line t4 requests creation of a new **Hamlet** object, the process is repeated; this time, however, **word**’s value is "iaou", to which the instance initers add "ao" and the constructor finishes it up by appending "e".

**Problem 6.33 – D**

**Given:**

![](images/00514.jpeg)

**What is the result?**

A.a = 40, b = 40

B.a = 40, b = 60

C.a = 60, b = 40

D.Compilation fails

Calls to `super()` or `this()` are allowed only from inside constructors while **modify()** is just a method… I met such a trap on both sittings; do be careful.

**Problem 6.34 – B**

The ***Real World Scenario*** sidebar on page [208](#part0019_split_002.html_page_208) in the *OCA Study Guide* by Jeanne Boyarsky and Scott Selikoff discusses the so-called defensive copy^([97](#part0020_split_006.html_id_184)) and provides this example:

![](images/00515.jpeg)

Now, the Constructor Summary for the class **StringBuilder**^([98](#part0020_split_006.html_id_182)) says that the class defines four constructors none of which lists a **StringBuilder** object as its argument:

![](images/00516.jpeg)

Hence the question: **Is line XXX valid?**

A.Oh yes, most definitely; after all, the authors of any study guide written to the masses should know what they are talking about…

B.Hell, no! it should’ve been `return new StringBuilder(builder.toString());`

This problem is equally appropriate for another Exam Objective, namely 9.1, *Manipulate Data Using the StringBuilder Class and Its Methods*, which belongs to the last group, *Working with Selected Classes from the Java API*. I must also add that the actual exam does not go to such depths, so please don’t be alarmed. On the other hand, looking at things from different – preferably unexpected – perspectives helps understand and memorize them quicker and better…

So far we were mostly passing primitives or objects of instantiable types to constructors except for [Problem 6.28](#part0020_split_006.html_id_325), which had to do with the interface type **List**. Here we meet an interface again; this time it is **CharSequence**.

The class **StringBuilder**^([99](#part0020_split_006.html_id_186)) implements **CharSequence**; this is why any **StringBuilder** object is also a **CharSequence**, and since one of the **StringBuilder**’s constructors does accept a **CharSequence**, the code snippet in the ***Real World Scenario*** sidebar of the B&S Study Guide is perfectly valid.

**Problem 6.35 – B**

**Given:**

![](images/00517.jpeg)

**What is the result?**

A.A

B.Hello from A

C.Hello from C A

D.Hello from B C A

We already know from the discussion to [Problem 6.32](#part0020_split_006.html_id_326)that static initers do not fire automatically when the class is accessed; they do it only under certain conditions. Here’s another one of them (JLS, §12.4.1):

A reference to a static field causes initialization of only the class or interface that actually declares it, even though it might be referred to through the name of a subclass, a subinterface, or a class that implements an interface.

This very condition is realized by the method **main()** who wants to access the var **name**, which is `static` and declared in the class **A**. On the other hand, were the var **name** an instance field and **main()**’s printing stat were accessing it through an object of type **C**, the program would have printed two more letters:

![](images/00518.jpeg)

**Problem 6.36 – E**

**Given:**

![](images/00519.jpeg)

**What is the result?**

A.str=null sb=null

B.str=aaa sb=null

C.str=aaa sb=bbb

D.str=aaa sb=aaabbb

E.str=aaa sb=bbbaaabbb

F.Compilation fails

G.A NullPointerException is thrown at runtime

As Java is always pass-by-value, setting local references to whatever values (like `null` in our case) doesn’t affect the caller. It’s the method invocation on those pesky refs that does → lines XXX and XXXX are immaterial whereas line XX indeed comes into play. As for line X, it simply leads to the creation of a new object because of the immutability of **String**.

* * *

^([83](#part0020_split_000.html_id_155)) Yes, void is also a data type. The package **java.lang** contains the class **Void**, which, according to the javadocs, is "an uninstantiable placeholder class to hold a reference to the **Class** object representing the Java keyword void". Its parent is **java. lang.Object**. Naturally. ^([84](#part0020_split_000.html_id_157)) In other words, whose type doesn’t clash with the declared return type.

^([85](#part0020_split_002.html_id_159)) Please note that it's not ‘static import’. The easienst way to remember this is by taking the keyword `import` as a direct order (that is, an imperative: "Hey you! Wake up and `import static` things such as…").

^([86](#part0020_split_004.html_foot3)) Please note that the compiler generates a somewhat misleading error message saying that the ctor One() isn’t `public` in One. Well, it doesn’t have to be `public`; being `protected` is enough.

^([87](#part0020_split_004.html_id_161)) Both `static` and instance initializer blocks are executed in the order they appear.

^([88](#part0020_split_004.html_id_163)) For *two* reasons. First, the var **str** is `static`, so any constructor is out of the question. Second, the default constructor is by definition inserted automatically and contains just a single stat: `super();` (ref.to JLS8, §8.8.9: "…the default constructor simply invokes the superclass constructor with no arguments." ). Whoever coded the error messages for `javac` would have failed the exam on this partucular aspect… Curious.

^([89](#part0020_split_005.html_id_167)) Which has been briefly mentioned a few pages earlier when we were looking at the rules related to Exam Objective 6.5, *Applying Encapsulation Principles to a Class*.

^([90](#part0020_split_005.html_id_165)) [https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html)

^([91](#part0020_split_006.html_id_173)) The Java Language Specification, Java SE8 Edition, §15.12.2, *Compile-Time Step 2: Determine Method Signature*.

^([92](#part0020_split_006.html_id_171)) The Java Virtual Machine Specification, Java SE8 Edition, §4.7.9.1, *Signatures*.

^([93](#part0020_split_006.html_id_169)) "…contradiction is the root of all movement and vitality", *Science of Logic* (1812), §956.

^([94](#part0020_split_006.html_id_175)) At the moment of writing the article was available here: [http://www.tonymarston.co.uk/php-mysql/abstraction.txt](http://www.tonymarston.co.uk/php-mysql/abstraction.txt)

^([95](#part0020_split_006.html_id_177)) However, a non-`public` *constructor* in a `public` class is accessible if it’s `protected`. Do remember this, OK?

^([96](#part0020_split_006.html_id_179)) §12.4.1, *When Initialization Occurs*.

^([97](#part0020_split_006.html_id_183)) Which was also briefly mentioned a few pages earlier when we took a look at the rules related to Exam Objective 6.5, *Applying Encapsulation Principles to a Class*.

^([98](#part0020_split_006.html_id_181)) [https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html)

^([99](#part0020_split_006.html_id_185)) along with **String** and **StringBuffer**.

![](images/00520.jpeg)

**The 1Z0-808 objectives within this group:**

| [7.1](#part0021_split_000.html_c7.1) | Describe inheritance and its benefits; |
| [7.2](#part0021_split_002.html_c7.2) | Develop code that demonstrates the use of polymorphism, including overriding and object type *versus* reference type; |
| [7.3](#part0021_split_004.html_c7.3) | Determine when casting is necessary; |
| [7.4](#part0021_split_006.html_c7.4) | Use `super` and `this` to access objects and constructors; |
| [7.5](#part0021_split_008.html_c7.5) | Use abstract classes and interfaces |

This Group of Exam Objectives is hugely important, as a good third of all exam questions is based on the aspects that have to do with inheritance and overriding. Moreover, given the fact that, starting from Java 1.8, interfaces may define three kinds of methods (`abstract`, `default` and `static`), mastering these Objectives becomes one of the most interesting – and toughest – tasks.

![](images/00061.jpeg) **CORE RULES (with some Extras):**

7.1Describe inheritance and its benefits:

![](images/00012.jpeg)A Java class may inherit a single class only, with all classes eventually extending the class **java.lang.Object**, which has no parent.

![](images/00012.jpeg)While Java does not allow true multiple inheritance, its limited form is emulated through interfaces because classes are allowed to implement multiple interfaces, each of which, in its own turn, may also extend multiple interfaces.

| **Corollary**: | An interface `extends` an interface, while a class `extends` a class or `implements` an interface. |

![](images/00012.jpeg)Inheritance enables to reuse existing code by allowing a class to inherit the properties and behavior of another class; one of the most useful aspects of inheritance is polymorphism, which makes the code more flexible and dynamic.

![](images/00012.jpeg)A `final` class cannot be extended.

![](images/00012.jpeg)EXTRA: Below are some of the `final` core Java classes that are featured on the exam:

![](images/00059.jpeg)**String**;

![](images/00059.jpeg)**StringBuilder** ^([100](#part0021_split_011.html_id_188));

![](images/00059.jpeg)All primitive wrappers (namely, **Boolean**, **Character**, **Byte**, **Short**, **Integer**, **Long**, **Float**, and **Double**);

![](images/00059.jpeg)All LDTs;

![](images/00059.jpeg)**java.lang.System** is also `final`.

![](images/00012.jpeg)A Java class that extends another class inherits all of its non-`private` members, although the package-`private` members can be accessed from inside the same package only^([101](#part0021_split_011.html_id_190)).

| **Corollary and known trap on the exam**: | `private` methods and `private` variables are not inherited. |

![](images/00012.jpeg)Be on alert for every class that defines all kinds of constructors except a no-arg one: its child will be locked out of the inheritance (we have already discussed it in more detail in Exam Objective 6.3).

![](images/00012.jpeg)EXTRA: Constructors as well as `static` and instance initers aren’t inherited.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 7.1Given:**

![](images/00521.jpeg)

**What is the result?**

A.3

B.1 2 3

C.3 2 1

D.Compilation fails on line t1 and line t2

**Problem 7.2**

**Which two are benefits of polymorphism?**

A.More dynamic code at runtime

B.Faster code at runtime

C.More efficient code at runtime

D.More flexible and reusable code

E.Code that is protected from extension by other classes

**Problem 7.3Given the following classes:**

![](images/00522.jpeg)

**Which two LOCs fail to compile when inserted at line XXX?**

A.ship.serviceLife = 50;

B.enterprise.serviceLife = 45;

C.ship.shields = 10;

D.starship.shields = 1000;

E.starship.warpSpeed = 2;

F.enterprise.warpSpeed = 12;

**Problem 7.4Given:**

![](images/00523.jpeg)

**From which data type does the Java compiler implicitly derive the class Test?**

A.Object

B.java.lang.Class

C.An anonymous abstract class

D.The interface Javable

**Problem 7.5Given:**

![](images/00524.jpeg)

**What is the result?**

A.true

B.false

![](images/00061.jpeg) **CORE RULES (with some Extras):**

7.2Develop code that demonstrates the use of polymorphism, including overriding and object type *versus* reference type:

![](images/00012.jpeg)An object may take on different forms, and its behavior will depend in part on the reference that points to the object. Unlike methods and variables that are hidden, overridden methods will be replaced by their overriding counterparts at the run time.

![](images/00012.jpeg)Only inheritable methods can be overridden → `private` methods can be only hidden.

| **Different wording**: | Parent’s `private` methods aren’t polymorphic and bind at the compile time → the actype’s version won’t fire. |

![](images/00012.jpeg)EXTRA: Abstract methods can be overridden.

![](images/00012.jpeg)Essence of polymorphism through the exam taker’s eyes:

![](images/00059.jpeg)The version to be executed is selected according to the class of the actual object;

![](images/00059.jpeg)In Java, all non-`private` and non-`final` instance method calls are virtual and potentially polymorphic;

![](images/00059.jpeg)Polymorphism in Java is realized when child’s method has the same name as in the parent class but its business logic differs from the overridden method.

![](images/00012.jpeg)Rules for method overriding:

![](images/00059.jpeg)both methods must have the same signature,

![](images/00059.jpeg)the overriding method mustn’t have a weaker access privilege,

![](images/00059.jpeg)the overriding method may not declare any new or wider ChE,

![](images/00059.jpeg)the return types must be at least covariant.

| **Corollary**: | The return type of the overriding method must match exactly the return type of the overridden method if the return type is a primitive. If the methods return objects, the return type of the overriding method may be a subclass of the return type of the overridden method. |

![](images/00012.jpeg)EXTRA: `static` over non-`static` and *vice versa **between classes*** never compiles^([102](#part0021_split_011.html_id_192)):

![](images/00525.jpeg)

![](images/00012.jpeg)Actype^([103](#part0021_split_011.html_id_196)) *vs* reftype:

![](images/00059.jpeg)Actype – the type of the actual object at run time – determines which properties exist within the object in memory.

![](images/00059.jpeg)Reftype – the type of the reference to the object – specifies which methods and variables are accessible.

| **Combat version**: | Reftype dictates what’s available while actype says what runs. |
| **On the exam**: | See a new object? Assess its reftype first: it’ll give you an idea what the object is capable of and what is out of its reach. |

![](images/00012.jpeg)Unlike methods, variables can’t be overridden – but they can be HIDDEN^([104](#part0021_split_011.html_id_194)):

![](images/00059.jpeg)Which *variable* will be used depends on the reftype (RT), that is, the left-hand side of `RT obj = new AT();` where AT is a descendant of RT;

![](images/00059.jpeg)Which *method* will run depends on the actype (AT, right-hand side):

![](images/00526.jpeg)

![](images/00012.jpeg)EXTRA: When ancestor’s var is not hidden and gets re-assigned in the descendant class, the var’s value changes in the ancestor class, too.

| **Corollary**: | Leads to a comperr if the var is `final`. |

![](images/00527.jpeg)

Were the var **s** `static`, the output would’ve been `Child Child Child Child`.

![](images/00012.jpeg)EXTRA: Polymorphism extends to constructors, as well^([105](#part0021_split_011.html_id_198)):

![](images/00528.jpeg)

In this example, the **Parent**’s no-arg constructor invokes the method **greet()**, which is virtual and, therefore, gets executed according to the overriding version. Since the **obj**’s actype is **Child**, the first call to **greet()** prints the default value of the var **str** and not the **String** " Hello! ", and only after the object has been fully initialized, the second call to the same method outputs " Hi! ".

Please also note that calling an overridable method from a constructor (like **Parent**’s ctor does) is bad coding practice as it invokes a method on an object that hasn’t been properly constructed yet.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 7.6Given two classes:**

![](images/00529.jpeg)

**What is the result?**

A.Hello Bob!
Hello Bob!

B.Hello java.lang.StringBuilder@<*hashcode*>
Hello exam.ExamTaker@<*hashcode*>

C.Hello Bob!
Hello exam.ExamTaker@<*hashcode*>

D.Compilation fails

**Problem 7.7Given:**

![](images/00530.jpeg)

**What is the reference type of** `objA` **and what is the actual type of the object this variable references?**

A.Reference type is A; object type is A.

B.Reference type is C; object type is C.

C.Reference type is A; object type is C.

D.Reference type is C; object type is A.

**Problem 7.8Given:**

![](images/00531.jpeg)

**What is the result?**

A.Green Blue Purple

B.Orange Yellow Purple

C.Blue Red Purple

D.Compilation fails

**Problem 7.9Given:**

![](images/00532.jpeg)

**What is the result?**

A.BBBAAA

B.BBBaaa

C.Compilation fails on line t1

D.Compilation fails on line t2

**Problem 7.10Given:**

![](images/00533.jpeg)

**What is the result?**

A.Tree is growing

B.Oak is growing

C.Compilation fails on line 6

D.Compilation fails on line 11

**Problem 7.11Given:**

![](images/00534.jpeg)

**The code is supposed to print**

running type = 10
type = 0

**Which LOC(s) should be uncommented to achieve the desired result?**

A.line 1

B.line 2

C.line 3

D.line 4

![](images/00061.jpeg) **CORE RULES (with some Extras):**

7.3Determine when casting is necessary:

![](images/00012.jpeg)We use casting to make reference variable behave as a variable of another type when it becomes necessary to access certain members that are not available by default:

![](images/00535.jpeg)

Let’s recall a rule from the previous section: "Reftype dictates what’s available while actype says what runs". Although the actual type of the object is **StringBuilder**, we cannot invoke on it the method **append()** because this particular method isn’t available to **Object** → we need to cast the var **obj** from **Object** to **StringBuilder**.

![](images/00012.jpeg)Rules of casting between reference types:

![](images/00059.jpeg)Widening (or upcast: subclass → superclass) doesn’t need an explicit cast.

![](images/00059.jpeg)Narrowing (or downcast: subclass ← superclass) requires an explicit cast.

**Combat version**: See no cast when reftype is narrower than actype? → comperr!

![](images/00012.jpeg)Casting to unrelated types:

Lots and lots of study guides unconditionally insist that the compiler won’t allow casts to unrelated types, period^([106](#part0021_split_011.html_id_202)). There’s, however, an exception that concerns interfaces:

![](images/00059.jpeg)A cast between unrelated class types is *always* illegal… **← important for the exam**

![](images/00536.jpeg)

![](images/00059.jpeg)EXTRA: Casting a non-`final` type^([107](#part0021_split_011.html_id_200)) to unrelated *interface* type is *always* valid:

![](images/00537.jpeg)

The class **Test1** in the preceding examples illustrates the compile-time error when we attempt to cast a **Short** to an **Integer**: although all wrapper classes extend the same parent type **Number**, they are unrelated to each other in terms of inheritance. The last statement works because **Short** is related to **Number** by being its child.

This clear and unambiguous picture cracks as soon as we cast a non-`final` type to an interface type as illustrated by the class **Test2**: despite the fact that all three data types are complete strangers to each other, both casts work. Naturally, there will be a CCE at run time, but as far as the compiler is concerned, everything is just peachy. It happens because the compiler assumes that on some sunny day either interface (or even both of them) might be implemented by a descendant of **Test2**.

Now you know what’s going to happen should we declare **Test2** `final`: since the class cannot have children, the first cast immediately becomes illegal – and the second cast won’t work without the first one…

| **Corollary**: | A cast between two unrelated interface types through a non-`final` class always compiles. |

![](images/00012.jpeg)Even after an explicit and valid cast the JVM may well throw a **CastClassException** at run time if the object being cast is not actually an instance of the target class:

![](images/00538.jpeg)

The first cast in the above example compiles but the actype of the object **o** is **String** rather than **StringBuilder** → hence the types clash and produce a CCE at run time. Same sad story with the second cast…

On the other hand, we could make the references point to the same object, and then the downcast would run successfully:

![](images/00539.jpeg)

![](images/00012.jpeg)EXTRA: Casting can be used not only to make certain fields or methods available to the refvar, but also to resolve an ambiguous reference:

![](images/00540.jpeg)

![](images/00541.jpeg)

| Reminder: | Another way to resolve an ambiguous reference is, of course, by specifying the fully qualified name (as illustrated by the first valid sout in the above example). |

![](images/00012.jpeg)EXTRA: Casting also helps to get hold of a carefully concealed member somewhere up the hierarchical chain:

![](images/00542.jpeg)

Suppose, we want to access the var **str** declared in **A**. The first printing stat in this example fails miserably because the var **str** declared in **B** hides **A**’s **str**; more than that, **B**’s **str** is itself `private`. Even if it weren’t `private`, we still wouldn’t get the desired result due to hiding… A cast to **A** to the rescue!

In short, making a data type `final` can help protect its secrets… I suggest you play more with this example to see how – and if – it works when the classes are in different packages, and so on.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 7.12Given the following method main():**

![](images/00543.jpeg)

**What is the result?**

A.Result: 500

B.Compilation fails on line m1

C.Compilation fails on line m2

D.Line m1 throws a ClassCastException

E.Line m2 throws a ClassCastException

**Problem 7.13Given:**

![](images/00544.jpeg)

**What is the result?**

A.Plant
Coffee

B.Plant
Java

C.Java
Java

D.Java
Coffee

E.A ClassCastException is thrown at run time.

**Problem 7.14Given:**

![](images/00545.jpeg)

**Which LOC, when inserted at line X, throws a ClassCastException?**

A.d = b;

B.b = d;

C.d = (Object) b;

D.d = (I) d;

E.d = (Derived)(I) b;

**Problem 7.15Given:**

![](images/00546.jpeg)

**Which three LOCs compile and output** `Make way!`**?**

A.Line 7

B.Line 8

C.Line 9

D.Line 10

E.Line 11

F.Line 12

**Problem 7.16Given:**

![](images/00547.jpeg)

**What is the result?**

A.p: Object, c: Object

B.p: Parent, c: Child

C.p: Child, c: Parent

D.p: Child, c: Child

**Problem 7.17Given:**

![](images/00548.jpeg)

**Which three statements will compile?**

A.Beverage obj = new Coffee();

B.Beverage obj = new Beverage();

C.Coffee obj = new Beverage();

D.Coffee obj = new Java();

E.Beverage obj = new Java();

F.Java obj = new Coffee();

**Problem 7.18**

**Suppose, the class Child extends the class Parent. Let’s assume further that we have the following variable declarations:**

![](images/00549.jpeg)

**Which four LOCs compile?**

A.p = (Child) new Child();

B.p = new Child();

C.c = (Child) new Parent();

D.c = new Parent();

E.c = new Child(); p = c;

F.p = new Parent(); c = p;

**Problem 7.19Given:**

![](images/00550.jpeg)

**What is the result?**

A.P P P

B.P C P

C.C C P

D.C C C

E.Compilation fails

**Problem 7.20Given:**

![](images/00551.jpeg)

**Which two statements are true?**

A.Line t1 throws a compile-time error

B.Line t2 throws a ClassCastException at run time

C.Line t3 throws a ClassCastException at run time

D.Line t2 fails compilation if the cast is removed

![](images/00061.jpeg) **CORE RULES (with some Extras):**

7.4Use super and this to access objects and constructors:

![](images/00012.jpeg)The keywords `super` and `this` are reference variables that are defined and initialized by the JVM itself for every object in its memory:

![](images/00059.jpeg)`this` always refers to the current object…

![](images/00059.jpeg)… whereas `super` denotes the object’s supertype;

| **Known trap on the exam**: | Both `this` and `super` point to an instance → an attempt to access them from a `static` context such as `static` method, `static` initer or declaration of a `static` var throws a comperr. |

![](images/00012.jpeg)EXTRA: `super` and `this` point to the same object:

![](images/00552.jpeg)

![](images/00012.jpeg)`super` and `this` can be used to access variables, methods or constructors in the parent or child class, respectively (ctors require parentheses, though).

![](images/00012.jpeg)EXTRA: `this` is `final` → e.g., `this = new Object();` throws a comperr.

![](images/00012.jpeg)To call a constructor from another constructor, the form `this()` or `super()` is used.

| **Known trap on the exam**: | `this()` or `super()` must be the first stat in a constructor’s body → two such calls back to back throw a comperr. |

![](images/00012.jpeg)To access a shadowed var **x** within the same class, we use the form `this.x`, which is a typical idiom for constructors or methods that define a local var or an arg with the same name as an instance var:

![](images/00553.jpeg)

![](images/00012.jpeg)To access a hidden var **x** in the superclass, we use `super.x`. It is also possible to invoke an overridden method by calling `super.methodName()`.

![](images/00012.jpeg)Reminders: What is the difference between shadowing and hiding? And let’s add obscuring for good measure…

JLS8, §6.4.1, *Shadowing*:

Some declarations may be shadowed in part of their scope by another declaration of the same name, in which case a simple name cannot be used to refer to the declared entity.

Please take a good note of this bashful utterance: "some declarations". Does it mean that certain declarations cannot be shadowed in principle? Yes, it does; and first and foremost, these are local vars; even placing them into sub-blocks won't help. Consider the following example:

![](images/00554.jpeg)

While the local var **str** declared on line t2 successfully shadows the instance field with the same name declared on line t1, lines t3 and t4 throw a comperr – ‘variable **str** is already defined in method **main(String[])**’ – and the JLS explains why it happens:

This restriction – a declaration of an identifier as a local variable of a method, constructor, or initializer block must not appear within the scope of a parameter or local variable of the same name – helps to detect some otherwise very obscure bugs. A similar restriction on shadowing of members by local variables was judged impractical, because the addition of a member in a superclass could cause subclasses to have to rename local variables.

The JLS continues by saying that

Shadowing is distinct from *hiding*, which applies only to members which would otherwise be inherited but are not because of a declaration in a subclass.

Now to obscuring, which differs from shadowing and hiding:

A simple name may occur in contexts where it may potentially be interpreted as the name of a variable, a type, or a package. In these situations, the rules of §6.5 specify that a variable will be chosen in preference to a type, and that a type will be chosen in preference to a package. Thus, it is may sometimes be impossible to refer to a visible type or package declaration via its simple name. We say that such a declaration is *obscured*.

A most typical case of obscuring happens when a field shares the same simple name with a package. We had a close encounter with obscuring while discussing [Problem 1.21](#part0015_split_001.html_id_327).

![](images/00012.jpeg)EXTRA: Can a grandson **C** call his grandpa **A**’s method? Is `this.super.run()` possible? No, there is no way to go more than one level up for methods because `this` refers to an instance and not to a data type.

This problem, though, doesn’t occur for instance variables because variables can never be overridden: they are hidden. So in order to access an ancestor’s hidden var, we ‘unhide’ it by using a cast, such as `((A)c).var`, which gives us the var defined in **A** even if it is hidden by **B**.

As already mentioned, `super.methodName()` is a valid way to invoke a superclass’ method from a subclass’s instance method, instance initializer, constructor, or initializer of an instance var. But it works only for classes.

To invoke a superinterface’s `default` method, we need to use the name of that interface, as well. This, however, is possible only when the interface is directly implemented – or extended – by the caller:

![](images/00555.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 7.21Given:**

![](images/00556.jpeg)

**What is the result?**

A.20 : 90

B.Compilation error on line p1

C.Compilation error on line p2

D.Compilation error on line p3

E.Lines p1, p2 and p3 fail compilation

**Problem 7.22Given:**

![](images/00557.jpeg)

**Which code fragment, when inserted at line L1, will instantiate the os object successfully?**

![](images/00558.jpeg)

**Problem 7.23Given:**

![](images/00559.jpeg)

**What is the result?**

A.Pikachu says Squeak squeak!

B.Undefined says Squeak squeak!

C.Compilation fails on line p1

D.Compilation fails on line p2

E.Compilation fails on lines p1 and p2

**Problem 7.24Given:**

![](images/00560.jpeg)

**What code fragment, when inserted into the class Hemingway, will produce the following output?**

`Fish: swims`
`Marlin: caught`
`Fish: caught`

A.Marlin marlin = new Fish("Get the sucker!");
marlin. getFish("Get the sucker!");
marlin.getFish();

B.Marlin marlin = new Marlin ("Get the sucker!");
marlin.getFish();
marlin. getFish("Get the sucker!");

C.Marlin marlin = new Marlin();
marlin.getFish();
marlin. getFish("Get the sucker!");

D.Marlin marlin = new Fish();
marlin. getFish("Get the sucker!");
marlin.getFish();

E.Fish marlin = new Marlin();
marlin.getFish();
marlin. getFish("Get the sucker!");

F.Marlin marlin = new Marlin();
marlin. getFish("Get the sucker!");
marlin.getFish();

![](images/00061.jpeg) **CORE RULES (with some Extras):**

7.5Use abstract classes and interfaces:

![](images/00012.jpeg)The keyword `abstract` is one of the non-access modifiers^([108](#part0021_split_011.html_id_204)) that change the default properties of a Java class and its members.

![](images/00012.jpeg)A class can be declared `abstract` even if it doesn’t define any abstract methods.

![](images/00012.jpeg)An abstract type cannot be instantiated and, therefore, requires a concrete subtype for the code to be used.

![](images/00012.jpeg)An abstract method doesn’t have a body but follows all the method overriding rules applicable to regular methods.

![](images/00012.jpeg)The first concrete class that extends an abstract class must implement all the inherited abstract methods.

| **Corollary**: | Abstract classes and methods cannot be declared as `private` or `final`. |

![](images/00012.jpeg)An abstract class can extend a concrete class, and vice versa.

![](images/00012.jpeg)An interface is an abstract type → can’t be instantiated; **known trap on the exam!**

![](images/00012.jpeg)In addition to abstract methods and `static final` variables (in other words, *constants*) that were allowed in interfaces prior to Java 1.8, now interfaces can also define `default` and `static` methods.

| **On the exam**: | As soon as you see a var declared in an interface, be on alert! The var is `final`! |
| Important Reminder: | `final` reftypes behave differently from `final` primitives: it’s only their references that are `final`, not the inner states. |
| **Alternative wording**: |

![](images/00561.jpeg)

![](images/00012.jpeg)All members of an interface are implicitly `public` ← **known trap on the exam!**

![](images/00012.jpeg)Any interface method that is not explicitly marked as `default` or `static` is assumed to be `abstract`.

![](images/00012.jpeg)An interface cannot extend a class but can extend multiple interfaces.

![](images/00012.jpeg)A subinterface inherits all the abstract and `default` methods declared in its superinterface(s).

![](images/00012.jpeg)A class cannot extend an interface but can implement multiple interfaces thus achieving benefits of multiple inheritance.

![](images/00012.jpeg)The `default` methods can be overridden, `abstract` method are meant to be overridden, and `static` methods cannot be overridden: they’ll become hidden.

| **On the exam**: | Overriding method can be `abstract` thus making the child class `abstract`. → It’s a potential trap! |

![](images/00012.jpeg)EXTRA: `static` interface methods are useful for providing handy tools such as sorting, null checks, etc. → no need to define utility classes anymore.

![](images/00012.jpeg)EXTRA: A `static` interface method can only be invoked by using its interface name.

This rule – invocation of `static` interface methods through the interface name only – exists due to many reasons, and one of them is security as implementing classes cannot override these methods, otherwise the JVM would’ve simply run the actype’s version as it does with classes.

![](images/00562.jpeg)

So how come we can call `static` methods declared in classes via object references and cannot do the same with interfaces? Answers Brian Goetz himself:

We consider the ability to invoke a static method through an instance to be a language design error, unfortunately one which we can’t fix retroactively for classes^([109](#part0021_split_011.html_id_308)).

![](images/00012.jpeg)EXTRA: "Classes win over interfaces" (this one is also from Brian Goetz; covered in the discussion to [Problem 7.34](#part0021_split_009.html_page_300); just read on).

![](images/00012.jpeg)EXTRA: Question: Are `static` methods inherited? Simple answer: "Yes" for classes and "No" for interfaces as per JLS8, §8.4.8, *Inheritance, Overriding, and Hiding*:

![](images/00059.jpeg)A class inherits from its direct superclass all concrete methods (both `static` and instance) of the superclass;

![](images/00059.jpeg)A class inherits from its direct superclass and direct superinterfaces all `abstract` and `default` methods;

| **Corollary**: | `default` methods may collide if not overridden: |

![](images/00563.jpeg)

![](images/00059.jpeg)A class does not inherit `static` methods from its superinterfaces.

![](images/00012.jpeg)**Reminder**: Just like classes, interfaces can also be inaccessible from outside their packages (it’s only their members that are implicitly `public`) → so watch out if the code tries to peek into different packages:

![](images/00564.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 7.25Given the following classes:**

![](images/00565.jpeg)

**Which two modifications, made independently, enable the code to compile?**

A.Make the method on line 1 public.

B.Make the method on line 2 public.

C.Make the method on line 3 public.

D.Make the method on line 4 public.

E.Make the method on line 3 protected.

**Problem 7.26Given:**

![](images/00566.jpeg)

**Which two modifications, made independently, enable the code to compile?**

A.Replace line 1 with:
`class Plane implements Flier {`

B.Insert at line 2:
`public abstract void takeOff();`

C.Replace line 3 with:
`abstract class Boeing747 extends Plane {`

D.Insert at line 4:
`public void takeOff() { }`

**Problem 7.27**

Your enterprising teenage sister asked you to develop an inventory program for her tiny online shop, and after patiently listening to her incoherent, stumbled explanations you realize that the specifications boil down to this:

•The program must contain the classes **Dress**, **ReadyToWear**, and **HauteCouture**. The **Dress** class is the superclass of the other two classes.

•The `double calculatePrice(Dress d)` method should calculate the price of a dress. The `void showDress(Dress d)` method should output the full description of a dress.

**Which definition of the class** `Dress` **can serve as a valid abstraction in the class hierarchy?**

![](images/00567.jpeg)

**Problem 7.28Given the following data type declarations:**

![](images/00568.jpeg)

**Which option(s), when inserted at line XXX, will fail compilation?**

A.ArrayList<Pilot> alumni = new ArrayList<>();
alumni.add(new D2R2());

B.ArrayList<SpaceCadet> alumni = new ArrayList<>();
alumni.add(new CyberPilot());

C.ArrayList<SpaceCadet> alumni = new ArrayList<>();
alumni.add(new D2R2());

D.ArrayList<D2R2> alumni = new ArrayList<>();
alumni.add(new CyberPilot());

E.ArrayList<Pilot> alumni = new ArrayList<>();
alumni.add(new Pilot());

**Problem 7.29Given:**

![](images/00569.jpeg)

**What is true about the class Test?**

A.It fails compilation because an abstract class cannot have instance variables.

B.It fails compilation because an abstract class cannot have private members.

C.It fails compilation because an abstract class must have at least one abstract method.

D.It fails compilation because an abstract class must have an explicit no-arg constructor.

E.It compiles without error.

**Problem 7.30**

**Which two statements are true?**

A.An abstract class can implement an interface.

B.An abstract class can be extended by an interface.

C.An interface cannot be extended by another interface.

D.An interface can be extended by an abstract class.

E.An abstract class can be extended by a concrete class.

F.An abstract class cannot be extended by an abstract class.

**Problem 7.31**

**Which one is valid?**

A.public interface Diver { protected abstract void dive(); }

B.public abstract class ScubaDiver { protected void dive(); }

C.public abstract class ScubaDiver { protected final abstract void dive(); }

D.public abstract class ScubaDiver { protected abstract void dive(); }

E.public abstract class ScubaDiver { protected abstract void dive() {} }

**Problem 7.32Given:**

![](images/00570.jpeg)

**Which two options are valid?**

A.`class B extends A implements I { public void doStuff_B() { } }`

B.`abstract class B extends A implements I { public void doStuff_B() { } }`

C.`class B extends A implements I { public void doStuff_A() { } }`

D.`abstract class B extends A implements I {}`

E.`class B extends A implements I { public void doStuff() { } }`

**Problem 7.33Given:**

![](images/00571.jpeg)

**How much money is left in this coder’s pocket?**

A.4900

B.4800

C.0

D.-100

E.-200

**Problem 7.34Given:**

![](images/00572.jpeg)

**What is the result?**

A.Inter

B.Parent

C.Compilation fails

D.Run-time error

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 7.1 – B**

**Given:**

![](images/00573.jpeg)

**What is the result?**

A.3

B.1 2 3

C.3 2 1

D.Compilation fails on line t1 and line t2

There’s nothing wrong with lines t1 and t2: they simply declare public constructors for their respective classes, so option D is incorrect.

Option A is out of the question because the superclasses’ constructors run before the object **obj** is initialized for the last time, and we have three constructors in total, which corresponds to three printing stats → we have to choose between options B and C.

Option C is incorrect since the constructors are called in the order of inheritance, starting from the base class.

**Problem 7.2 – AD**

**Which two are benefits of polymorphism?**

A.More dynamic code at runtime

B.Faster code at runtime

C.More efficient code at runtime

D.More flexible and reusable code

E.Code that is protected from extension by other classes

‘Dynamic’ here doesn’t relate to the program execution progress; it’s about the so-called dynamic binding, which occurs at run time in contrast to the static binding, which takes place at compile time. The dynamic binding is what makes polymorphism possible: the decision as to which version of a method should be executed is made according to the actual type of the object at run time.

As for option B, static dispatch is actually faster than virtual calls.

Option C is too broad, we don’t even know what it refers to because the efficiency of code can be measured in terms of, say, memory footprint or CPU utilization ratio, etc. On a side note, I didn’t meet any reference to ‘code efficiency’ on the real exam although all the study guides and prepware I know of mention it; so you are probably safe in this regard…

Option E is the exact opposite of what the OOP is all about.

**Problem 7.3 – CE**

**Given the following classes:**

![](images/00574.jpeg)

**Which two LOCs fail to compile when inserted at line XXX?**

A.ship.serviceLife = 50;

B.enterprise.serviceLife = 45;

C.ship.shields = 10;

D.starship.shields = 1000;

E.starship.warpSpeed = 2;

F.enterprise.warpSpeed = 12;

Both options that we need to tick off commit the same error: they attempt to access something that is not available to the object in question. For example, option C wants to set the value of the var **shields**, which is declared in the class **Starship** and, therefore, doesn’t even exist in the superclass **Ship**. Similar story is with option E, where the code tries to set **warpSpeed**, which is declared in the last extending class only.

**Problem 7.4 – A**

**Given:**

![](images/00575.jpeg)

**From which data type does the Java compiler implicitly derive the class** `Test`**?**

A.Object

B.java.lang.Class

C.An anonymous abstract class

D.The interface Javable

"Class **Object** is the root of the class hierarchy. Every class has **Object** as a superclass. All objects, including arrays, implement the methods of this class", says the documentation for the class **Object**.

**Problem 7.5 – A**

**Given:**

![](images/00576.jpeg)

**What is the result?**

A.true

B.false

The JLS says that `private` members aren’t inherited… Have you ever wondered what happens to `private` fields defined in the parent class? Will the child object contain them? or not? Common sense – and the OOP principles – dictate that those fields must be present inside the object even if they are ‘non-inheritable’.

Apart from running the class **Child** and knowingly smiling at the result, another way to confirm validity of our logic is to serialize the object to a file and peek inside.

**Step 1**. Fill the file **Child.java** with the following code:

![](images/00577.jpeg)

![](images/00578.jpeg)

Comments:

1.To be serializable, the class should implement the interface **Serializable**.

2.The `try` block uses something that is not on our exam, namely the `try-with-resources` construct, which exists since Java 1.7 and is used for declaring resources that must be released back to the system when no longer needed (like file handles, sockets, etc.).

3.While the whole `import` block can be easily replaced with the `import java. io.*;` stat, you’d better stick to fully qualified names until you pass the exam.

**Step 2**. Execute the program and open **child.ser**:

![](images/00579.jpeg)

Our object does contain the sacred string " 1Z0-808", which is only natural. The JLS specifies several conditions that must be met by a class member to be inheritable (§8.4.8, *Inheritance, Overriding, and Hiding*). As far as the exam is concerned, `private` members aren’t inherited, and that’s it. Think of them as being ‘incorporated and encapsulated’, if it helps…

**Problem 7.6 – C**

**Given the file ExamTaker.java:**

![](images/00580.jpeg)

**Given the file Greeting.java:**

![](images/00581.jpeg)

**What is the result?**

A.Hello Bob!
Hello Bob!

B.Hello java.lang.StringBuilder@<*hashcode*>
Hello exam.ExamTaker@<*hashcode*>

C.Hello Bob!
Hello exam.ExamTaker@<*hashcode*>

D.Compilation fails

The problem is meant to remind us that although user-defined classes inherit **Object**’s method **toString()**, they should override the method to make it truly meaningful, and the following article^([110](#part0021_split_011.html_id_206)) by Dustin Marx explains how it is to be done. The exam does contain such a question.

**Problem 7.7 – C**

**Given:**

![](images/00582.jpeg)

**What is the reference type of** `objA` **and what is the actual type of the object this variable references?**

A.Reference type is A; object type is A.

B.Reference type is C; object type is C.

C.Reference type is A; object type is C.

D.Reference type is C; object type is A.

The reftype denotes the type of the reference variable and, as dictated by Java syntax rules, is always on the left-hand side of the variable declaration.

The actype, or the actual object type, is determined by the constructor placed on the right-hand side of the declaration.

In our case, the object **objA** is none other but **objC** whose actype is **C**, which can be verified by replacing line b1 with the following stat:

![](images/00583.jpeg)

The `@Override` annotation might not appear on the exam but is considered a good programming practice.

The code compiles without explicit casts because **B** is broader than **C** and **A** is broader than **B**. There’s no **ClassCastException** at run time because the IS-A relationship between **C** and **B** as well as between **B** and **A** holds true. In contrast, the next code snippet needs an explicit cast for the last assop because **Object** is wider than **Short**, and throws a CCE since the IS-A test between and the data of **sH produces**

![](images/00584.jpeg)

And finally, the code in the current [Problem 7.7](#part0021_split_010.html_id_328) prints "Hello from C!" since the method **toString()** is non-`private` and non-`static` and, therefore, polymorphic → the class **C**’s version of the overridden **toString()** runs because it is the actype that dictates which version to call, and the actual object type is **C**.

**Problem 7.8 – A**

**Given:**

![](images/00585.jpeg)

**What is the result?**

A.Green Blue Purple

B.Orange Yellow Purple

C.Blue Red Purple

D.Compilation fails

The abstract method **m1()** is correctly overridden in **Paint2** (its access modifier is `public`) while the package-`private` **m2()** is also correctly overridden with the `protected` **m2()**. As for the `abstract` **m3()**, it is overridden in **Paint3** with a method with the same access privilege, which is valid, too. The object **p** is declared of type **Paint2** → all the methods from **m1()** through **m3()** are therefore available to the object so the code compiles successfully.

All three methods are non-`private` and non-`static`, hence polymorphic → they all are selected according to the actype, which is **Paint3** → the code prints Green Blue Purple.

If you are still confused as to what polymorphic means, look in the mirror. Or imagine that a Java object is made of flesh and blood and makes its living as a deep-cover secret agent known to ordinary citizens as humble Mr.Brown the accountant (the reftype), whereas his true self is, say, James Bond IV (the actype). If we were to ask Mr.Brown to shoot a fly in the eye while piloting an attack helicopter, he would flatly refuse saying that no accountant can be reasonable expected to know how to do such things. However, should we appeal to his true nature and order him to smite the wrongdoers in the name of Queen and Country, all hell would break loose… Same person, different social roles depending on the circumstances.

**Problem 7.9 – A**

**Given:**

![](images/00586.jpeg)

**What is the result?**

A.BBBAAA

B.BBBaaa

C.Compilation fails on line t1

D.Compilation fails on line t2

The modifier `final` does nothing useful; it sits there just to confuse you although there are plenty of cases when disregarding it can be fatal – particularly when it’s implicit as in interfaces.

The cast on line t1 is needed because the object **ab** is of type **A**, and **A** is wider than **B**.

We can formulate a simple practical rule that says when an assignment works without an explicit cast:

**LEFT-HAND SIDE CAN’T BE NARROWER THAN RIGHT-HAND SIDE**

In practice, especially when dealing with collections, it is recommended to use interface type on the left because this way it becomes much easier to switch between different implementations of the same interface:

![](images/00587.jpeg)

can be readily replaced with `List list = new LinkedList();` and so on.

A narrower type on the left-hand side mandates the use of explicit cast but can throw a CCE:

![](images/00588.jpeg)

Let’s consider the following example:

![](images/00589.jpeg)

The reftype **List** on line w1 says **l** will accept only **Whale** or its subtypes – and we feed it appropriate objects on lines w2 and w3.

`null` is added to the list on line w4 just to remind us that `null` is perfectly valid value for a reference data type.

Line w5 needs an explicit cast because **Mammal** is wider than **Whale** + it throws a **ClassCastException**; similar story with line w6\. As for line w7, it shouldn’t have asked for instantiation because **HasTail** is an interface, which is `abstract` by definition.

Coming back to [Problem 7.9](#part0021_split_010.html_id_329), we can see that line t1 won’t throw a CCE since **bb**’s reftype and actype are both **B**. The method **mB()** is declared in the class **B** and, therefore, is available to **bb**. **mA()** is declared in **A**, which means it’s available to **ab**; what’s more, this method gets overridden in **B**, and since **ab**’s actype is also **B**, line t2 outputs AAA… Are you still with me?

**Problem 7.10 – A**

**Given:**

![](images/00590.jpeg)

![](images/00591.jpeg)

**What is the result?**

A.Tree is growing

B.Oak is growing

C.Compilation fails on line 6

D.Compilation fails on line 11

Line 6 is valid because the data type **Tree** is wider than **Oak**, so no cast is needed.

Line 11 doesn’t throw a comperr, either, since the `protected` access privilege is much less restrictive than the `private` one, so the method **grow()** is overridden correctly… Right? am I right or what? hello-o?..

Hopefully, you caught me red-handed even before I started dropping hints right and left: the rules of method overriding aren’t even applicable here because the method **grow()** in **Tree** is `private`, hence not inherited → from which follows it doesn’t participate in polymorphism → the reftype’s version of **grow()** runs regardless of the actype.

**Problem 7.11 – ACD**

**Given:**

![](images/00592.jpeg)

**The code is supposed to print**

![](images/00593.jpeg)

**Which LOC(s) should be uncommented to achieve the desired result?**

A.line 1

B.line 2

C.line 3

D.line 4

The printing stats want to access the variable named **type** but all its declarations are commented out so the code doesn’t even compile → first of all, we need to declare the var properly. But where?

We have three choices: declare type in **Base** or in **Derived** or do it in both places, in which case **Derived**’s **type** will hide its namesake in **Base**. So, which one is appropriate? That’s a tough call.

Alright, now it’s probably a good idea to recall how inheritance treats variables: they are not overridden but hidden.

It’s because variables are not polymorphic. When the compiler maps virtual method calls, it doesn’t know neither cares what’s inside those methods leaving it to the JVM to sort them out, so when the JVM starts executing a method that makes use of a field, it grabs the field that exists inside the *actual* object at the execution time, which is, in our parlance, `this`.**someField**. Note, however, that access to this very field via reference that is *not* wrapped up in a virtual method is always performed regardless of the run-time type of the object.

All the **type**-related declarations in **Derived** mention values other than zero, while the last printing stat must output exactly zero → the declaration in the class **Base** must be uncommented → option A is in; this definitely makes the code compile but it prints zeroes in both cases.

Now let’s take a careful look at **Derived**. What will happen if we uncomment line 2? This line declares a local var whose scope is limited to the constructor → whatever we do with it won’t affect the output → by the same token, uncommenting line 2 and 3 together is also useless → option B is definitely out.

So far so good; what’s going to happen if we uncomment line 3? The constructor will assign 10 to it and… oh no! since the var isn’t hidden, its value will propagate to **Base** thus making the code print 10 in both cases…

Let’s uncomment line 4 instead of line 3, then. The var gets hidden, so **run()** prints the value that exists in `this` – namely, 1 – whereas the printing stat in **main()** outputs the value according to the reftype, that is zero… Damn! missed again.

Grasping at the last straw, we uncomment both line 3 *and* 4. Let’s see: the var is shadowed, the constructor inits it to ten, **run()** prints it out and… There! Feeling dizzy yet?

**Problem 7.12 – C**

**Given the following method main():**

![](images/00594.jpeg)

**What is the result?**

A.Result: 500

B.Compilation fails on line m1

C.Compilation fails on line m2

D.Line m1 throws a ClassCastException

E.Line m2 throws a ClassCastException

Line m1 unboxes a **Short** and casts it to a primitive `long`; then there’s a rule (JLS §5.6.2 ) that says that "if either operand is of type `long`, the other is converted to `long`", after which the resulting primitive is converted to **Long**. All in all, this LOC is perfectly valid.

On the other hand, line m2 performs unboxing of a **Short** and a **Long**, converts the primitive `short` to `long` and then attempts to cast the resulting `long` to **String**, which is illegal as `long` is incompatible with **String** → a comperr on line m2.

**Problem 7.13 – C**

**Given:**

![](images/00595.jpeg)

**What is the result?**

A.Plant
Coffee

B.Plant
Java

C.Java
Java

D.Java
Coffee

E.A ClassCastException is thrown at run time.

By looking at the available options, we can see immediately that the code compiles, which means the method **run()** is properly overridden and accessible in all cases. What’s left is to figure out what it prints or, possibly, throws.

The object **p1**’s reftype is **Plant**, **p3** is a **Plant**, too → the cast on line j1 is actually redundant. More than that, the LOC doesn’t throw a CCE because either object’s actype is **Java**.

Line j2 explicitly casts **p3** whose reftype is **Plant** to a narrower **Coffee**, which is valid, and after that the ‘narrowed’ object gets assigned back to a wider **Plant** → no comperr. But does it throw a CCE? The answer is "No" since **p3**’s actype is **Java** and **Java** IS-A **Plant**.

Now we apply the rule that says that polymorphic methods are selected at run time according to the actype of the object on which the method is invoked → both **p1**’s and **p4**’s actype is **Java** → the same method defined in **Java** gets called in either case.

**Problem 7.14 – E**

**Given:**

![](images/00596.jpeg)

**Which LOC, when inserted at line X, throws a ClassCastException?**

A.d = b;

B.b = d;

C.d = (Object) b;

D.d = (I) d;

E.d = (Derived)(I) b;

What follows, borders on heresy and is not endorsed by any study guide or tutorial – lest of all by the JLS – but I found out that this homebrew approach helps see if a LOC generates a CCE.

Let’s start by introducing a new notion of the so-called ‘castype’. We know what the reftype and actype mean, but what on earth is a castype? It’s the ‘casting’ data type, the one we write inside the parentheses when asking the compiler to perform a cast, e. g.:

![](images/00597.jpeg)

In the above example **Father** is the castype^([111](#part0021_split_011.html_id_208)). Now we can formulate a new combat-grade rule:

**Any explicit cast throws a CCE unless actype IS-A castype (working out R to L)**

Sounds cryptic; we need to see how it works.

Suppose, we have three classes along a single inheritance chain: the base type is **A**; **B** extends **A**, and **C** is the subtype of **B**. I suggest we write it down this way: **A** ← **B** ← **C**. Yes, the widest type goes to the left thus reflecting a generic comperr-free casting scenario.

So, **A** ← **B** ← **C** Λ Cc = new C(); ⇒ ^([112](#part0021_split_011.html_id_310))

![](images/00598.jpeg)

Once again: in the above example the actype of **a** is **C**, which IS-A castype **B** → no CCE. The rule holds.

Let’s make life more interesting by adding an interface; most likely, you won’t have a problem deciphering the following shorthand notation:

![](images/00599.jpeg)

It says that the class **A** implements the interface **I**, then class **B** extends **A** and class **C** extends **B**. The angle brackets (a.k.a. chevrons) denote an interface: this way we won’t forget that the data type **I** cannot be instantiated, while **A**, **B** and **C** can. By the way, **A**, **B** and **C** are concrete classes; for abstract classes I use the caret, e.g.:

![](images/00600.jpeg)

Fine; so <**I**> ← **A** ← **B** ← **C** Λ A a = new A(); B b = new B(); ⇒

![](images/00601.jpeg)

However, these are problematic:

![](images/00602.jpeg)

And how about the following one?

![](images/00603.jpeg)

Diligently working it out R to L (right to left), we get **B** is-a **I** is-a **A** is *per se* **B** is-a… wait a sec! no way **B** is-a **C**! → CCE at the point of casting to **C**.

After the offending cast is removed, our weirdish code runs without as much as a peep:

![](images/00604.jpeg)

![](images/00605.jpeg)

Now it should be fairly easy to solve our little [Problem 7.14](#part0021_split_010.html_id_330):

Option A assigns wider **Base** to a narrowed **Derived** → comperr.

Option B does the opposite → no comperr and no CCE since **Derived** IS-A **Base**.

Option C casts **Base** to even wider **Object** and then assigns it to the much narrower **Derived** → comperr.

Option D casts **Derived** to a completely unrelated **I** but this is allowed since the compiler assumes that some descendant of **Derived** might implement **I** in the future, so the cast is valid. However, **I** – which is now being treated as a provisional supertype and is, therefore, pretty wide, – then gets assigned to the narrower **Derived** → comperr.

And finally, since option E additionally downcasts **I** to **Derived** and then assigns the result again to **Derived**, there’s no comperr but a CCE at the point when **Base** gets converted to **I**.

**Problem 7.15 – CDF**

**Given:**

![](images/00606.jpeg)

**Which three LOCs compile and output** `Make way!`**?**

A.Line 7

B.Line 8

C.Line 9

D.Line 10

E.Line 11

F.Line 12

This problem builds on the previous one, wherein we met an interface that was completely unrelated to class types. This time, however, one of the classes does implement an interface.

Let’s start by taking a brief look at a somewhat simpler example that doesn’t employ casts:

![](images/00607.jpeg)

The operator `instanceof` isn’t on our exam but is quite helpful when studying casting and CCE-throwing scenarios. Here’s a number of more or less compact rules that govern the use of `instanceof`:

![](images/00012.jpeg)`instanceof` works with reference types only; using it with a primitive throws a comperr;

![](images/00012.jpeg)`instanceof` throws a comperr if the left-hand operand cannot be converted to the right-hand one;

![](images/00012.jpeg)unless the class is `final`, neither cast to nor `instanceof` an interface type throws a comperr;

![](images/00012.jpeg)`instanceof` always produces `false` unless the left-hand side^([113](#part0021_split_011.html_id_312)) isn’t `null` and could be cast to the right-hand side (a.k.a. ReferenceType) without raising a CCE.

Please also note the convention used to name the objects: the first letter denotes the reftype and the second one, the actype (e.g., **fe** means RT==Flier and AT==Eagle). This way it is easier to recall which is which when looking at the output.

Our example uses a ‘dendritic’ inheritance structure to which the simple shorthand notation from the previous problem cannot be applied; nothing to do but resort to drawing:

![](images/00608.jpeg)

Line t1 tests if the object **fe** is an instance of **Flyer**; our diagram shows that it is, so there’s no comperr and no CCE → this LOC prints `fe is a Flyer`.

Line t2 looks at **ee** – while we look at our diagram: yes, this object IS-A **Bird**, so we get `ee is a Bird` printed.

By continuing checking the other tests against the diagram, we arrive at the conclusion that line t3 must throw a comperr since **Insect** cannot be converted to **Bird**; as for line t4, it is not only valid as **Dragonfly** IS-A **Flyer** but also doesn’t throw a CCE for exactly same reason.

There’s no comperr on line t5 because **Insect** isn’t `final` and the compiler knows that any non-`final` class can theoretically have a descendant that will implement any interface in the future. But since casting **Insect** to **Flyer** does produce a CCE, the `if` stat evaluates to `false` and this LOC outputs nothing.

Getting back to our [Problem 7.15](#part0021_split_010.html_id_331). Line 7 attempts to invoke the method **move()** on the object **jogger** whose reftype is **Jogger** – and fails miserably because this method is available only to the class that either defines it or at least implements the interface **FitnessBuff**, in other words the class **Runner**, and **Jogger** ain’t **Runner** → option A is out.

Line 8 does have a cast, but this cast is misplaced and doesn’t help rectify the problem we encountered on line 7 thus leading to a comperr → option B is out, too.

On the contrary, option C correctly widens **jogger** to the interface type thus making **run()** available to the object, and since this cast doesn’t throw a CCE (for **jogger**’s actype is **Runner**, which does implement **FitnessBuff**), we see the LOC output "Make move!".

Line 10 is trivial: it invokes a method that is available to the reftype **Runner** on the object whose actype is also **Runner** → neither comperr nor CCE, and the LOC prints what it’s supposed to.

Option E resembles line 8 in its misguided attempt to cast to **FitnessBuff** whatever the method **move()** returns, so this LOC fails: it wouldn't be a syntactically correct statement even if the method weren’t `void` in the first place.

As for option F, it doesn’t differ much from line 10; it just casts a **Runner** object to the interface type, and then runs the same method → option F is correct.

**Problem 7.16 – D**

**Given:**

![](images/00609.jpeg)

**What is the result?**

A.p: Object, c: Object

B.p: Parent, c: Child

C.p: Child, c: Parent

D.p: Child, c: Child

After what we have been through on the previous pages, this problem can be solved in a snap. I included it here mostly to remind you that **java.lang** contains the class **Class**, which might be useful when learning inheritance with all its quirks (for example, it contains **getFields()** and **getMethods()**, which can give you all the `public` methods and variables accessible to the data type in question; there’s also **getClasses()**, which returns an array with all the interfaces and `public` classes that are members of the object represented by `this`, and so forth).

As for the answer to [Problem 7.16](#part0021_split_010.html_id_332), it is option D because both objects’ actype is **Child**.

**Problem 7.17 – ADE**

**Given:**

![](images/00610.jpeg)

**Which three statements will compile?**

A.Beverage obj = new Coffee();

B.Beverage obj = new Beverage();

C.Coffee obj = new Beverage();

D.Coffee obj = new Java();

E.Beverage obj = new Java();

F.Java obj = new Coffee();

Since we see no casts, all we have to do is apply the rule that says that a comperr-free assignment LOC should have a valid and wider left-hand side.

Now, why mention ‘wider’ while, in fact, a valid data type of the *same* width would be perfectly legal, too?

Let’s ask ourselves: what is exactly the ‘valid data type of the same width’? Since we are dealing with reference types, any attempt to assign an incompatible type throws a comperr → the only *valid* type of the *same* width is the very same type we have on the right-hand side; so why memorize rules that pedantically proclaim that something as trivial as A = A always compiles? Waste of time and mental resources…

By the way, the popular term ‘covariant types’, strictly speaking, is not applicable here because the JLS speaks only of covariant *return* types, which are "the specialization of the return type to a subtype".

Alright, alright; let’s just state for the record that the right-hand type should be assignable to the left-hand one.

Now to ‘valid’; this one seems redundant… unless we take into account our ultimate goal: passing the exam. Which means we should be always on alert for potential traps, and 1Z0-808 features at least one question that wants to instantiate an interface. It is awfully easy to miss an invalid stat inside a list of similarly structured and harmlessly-looking, even naive LOCs…

So what we have here is this:

**Beverage** is wider than **Coffee** → option A is correct;
Options B and C are out because **Beverage** is an interface and cannot be instantiated;
**Coffee** is narrower that **Beverage** → this LOC needs an explicit cast;
**Coffee** is wider than **Java** → option D is correct;
**Beverage** is wider than **Java** → option E is also correct;
**Java** is narrower than **Coffee** → an explicit cast is missing.

**Problem 7.18 – ABCE**

**Suppose, the class Child extends the class Parent. Let’s assume further that we have the following variable declarations:**

![](images/00611.jpeg)

**Which four LOCs compile?**

A.p = (Child) new Child();

B.p = new Child();

C.c = (Child) new Parent();

D.c = new Parent();

E.c = new Child(); p = c;

F.p = new Parent(); c = p;

Hm… What’s the story with those `nulls`? are they important? do they affect compilation?

Recalling the list of NPE-throwing scenarios^([114](#part0021_split_011.html_id_210)), we can see that none of The Magnificent Five is at work here – which means we need to be careful about assignments and *implicit* casts only since the question doesn’t even mention CCE. As for potential problems with instantiation, we are safe because interfaces are not involved.

Very well then; option A creates an instance of **Child**, redundantly casts it to **Child** again and then assigns the object to a wider type → the LOC compiles.

Option B does the same thing but without the cast.

Option C creates a **Parent** object and assigns it to the narrower **Child**; this is valid because of the explicit cast although there will be a CCE at RT. The ‘castless’ option D doesn't work.

Option E assigns a completely new **Child** object to **c** then re-assigns it to the wider **Parent** represented by the object **p**. There's also no CCE at RT.

The similarly constructed option F is illegal because its second stat tries to assign a wider **Parent** object to the var that is of the narrower type **Child**.

**Problem 7.19 – D**

**Given:**

![](images/00612.jpeg)

![](images/00613.jpeg)

**What is the result?**

A.P P P

B.P C P

C.C C P

D.C C C

E.Compilation fails

The method **toString()** is overridden correctly in both cases (it is `public` and returns a **String** in the class **Object**).

Line p1 is trivial. Line p2 assigns a narrower **Child** object to the wider type **Parent** → the LOC is valid.

Although **I** and **Parent** are unrelated, we already know that the compiler allows such assignments and casts to the interface types as long as the class type on the right-hand side is non-`final`.

Line p4 needs a **toString()** to output anything meaningful for **p**, and the class **Parent** obliges by providing its own version of the method but since the actype of **p** is **Child**, line p4 prints "C ".

Line p5 calls **Parent** a **Child**, which is not illegal, and because **p**’s actype is also **Child**, there’s no CCE at RT and the LOC outputs "C ", too.

And finally… Whoa! **inter** is an interface! is **toString()** available to it at all? And if so, does it make an interface a class?! what a novel idea! Very well then, let’s look into it.

Same question in disguise: Do interfaces inherit from the class **Object**?

According to the official Oracle tutorial^([115](#part0021_split_011.html_id_212)), the answer is resounding and sonorous Yes:

Reference types all inherit from **java.lang.Object**. Classes, enums, arrays, and interfaces are all reference types.

"Oh bother" said Pooh as the tripwire clicked…

On the surface it does appear as if interfaces inherit from **Object**; say, the next example compiles:

![](images/00614.jpeg)

But wait! what’s this?! the following LOCs are invalid when we insert them into **Inter**:

![](images/00615.jpeg)

The JSL8 (§9.2, *Interface Members*) explains why it is so:

If an interface has no direct superinterfaces, then **the interface implicitly declares a public abstract member method m with signature s, return type r, and throws clause t corresponding to each public instance method m with signature s, return type r, and throws clause t declared in Object**, unless a method with the same signature, same return type, and a compatible throws clause is explicitly declared by the interface.

Do you see it? ‘…corresponding to each *`public`* instance method[…] declared in **Object**’. Now it becomes clear why we can invoke neither **clone()** nor **finalize()** on the object **entity** although all three methods – **toString()**, **clone()** and **finalize()** – are defined by **Object**: the methods **clone()** and **finalize()** are `protected` rather than `public` → if a `protected` member defined in the class **T** is not available to an object, the data type represented by this object is not a subtype of **T** → interfaces do not inherit from **Object** and simply have their own abstract versions of **Object**’s `public` methods^([116](#part0021_split_011.html_id_214)).

Alright; armed with this mind-blowing wisdom, we realize that line p6 does compile; as for the actype, it remains unchanged → there’s no CCE, and the LOC cheerfully prints "C " again.

**Problem 7.20 – CD**

**Given:**

![](images/00616.jpeg)

**Which two statements are true?**

A.Line t1 throws a compile-time error

B.Line t2 throws a ClassCastException at run time

C.Line t3 throws a ClassCastException at run time

D.Line t2 fails compilation if the cast is removed

Since **B** is a subtype of **A**, line t1 is valid.

Line t2 explicitly downcasts a wider **a1** object to the refvar of a narrower type, which is OK and also makes option D correct along the way. Incidentally, since **a1** actually points back to **b**, we have here the so-called ‘circular reference’. Anyway, this line doesn’t throw a CCE as there’s no conflict between the reference and run-time types.

As for line t3, it does throw CCE because **a2** still points to the same object that **a1** used to point to (ref.to line XXX) so the array **a2**’s type is **A**, and **A** ain’t IS-A **B**.

**Problem 7.21 – E**

**Given:**

![](images/00617.jpeg)

**And given the code fragment:**

![](images/00618.jpeg)

**What is the result?**

A.20 : 90

B.Compilation error on line p1

C.Compilation error on line p2

D.Compilation error on line p3

E.Lines p1, p2 and p3 fail compilation

Smack in the middle of our code sits the problematic spot: `super()` and `this()` back to back, which is not allowed as a call to another constructor, if present, must be the first one in any constructor’s body → line p2 definitely fails compilation.

What about line p1? is it OK? No, because it tries to invoke a no-arg constructor in the supertype – and **Painter** doesn’t have it.

Now for the tough one: which option mentions both p1 and p2?

Oh! almost forgot. Asking out of sheer curiosity, why exactly line p3 fails compilation?^([117](#part0021_split_011.html_id_216))

**Problem 7.22 – B**

**Given:**

![](images/00619.jpeg)

**And given the code fragment:**

![](images/00620.jpeg)

**Which code fragment, when inserted at line L1, will instantiate the** `os` **object successfully?**

![](images/00621.jpeg)

Can we use option A? No, because its first line is not a call to another constructor, which means that the compiler will try to insert at this point a call to a no-arg **super()**, and the supertype (the class **OS**) doesn’t have it.

Same goes for option D, which also has another reason to fail compilation. Can you name it?^([118](#part0021_split_011.html_id_218))

Option C is out, as well, since it contains two constructor calls back to back.

**Problem 7.23 – D**

**Given:**

![](images/00622.jpeg)

**What is the result?**

A.Pikachu says Squeak squeak!

B.Undefined says Squeak squeak!

C.Compilation fails on line p1

D.Compilation fails on line p2

E.Compilation fails on lines p1 and p2

As always, the first thing we do is check the code for validity by testing the ‘compilation fails’ options one at a time. Line p1 seems OK because the class **Pokemon** does have a constructor that accepts a single **String** arg → options C and, therefore, E are out.

Line p2, however, is definitely illegal: it contains two constructor invocations inside the same constructor body.

**Problem 7.24 – F**

**Given:**

![](images/00623.jpeg)

**What code fragment, when inserted into the class Hemingway, will produce the following output?**

![](images/00624.jpeg)

![](images/00625.jpeg)

The good news is that the code apparently compiles so we don’t have to check all those LOCs apart from the provided options... but there are so many of them (*sigh*)… I wonder if it’s possible to… oh no! the problem doesn’t specify an interface or an abstract class, otherwise we probably could eliminate some of the choices in a snap…^([119](#part0021_split_011.html_id_222))

Alright guys, we’ll do it the old-fashioned, caveman way, pedantically cracking one skull at a time.

Option A needs a **Fish** constructor that would accept a single **String** arg → but does **Fish** have it? nope → a comperr.

Option B uses a **Marlin** single-**String** constructor → but regardless of what else happens after the code calls this constructor, it will always print Marlin: swims, which is not mentioned in the provided output.

Option C invokes the no-arg **Marlin** constructor, which calls the no-arg **Fish** constructor, which prints Fish: swims → so far so good. Now, we invoke the no-arg **marlin.getFish()**, which in its own turn calls the no-arg **super.getFish()** → Fish: caught gets printed, which is not what we need: it should’ve been Marlin: caught.

Option D fails compilation as it attempts to assign the wider **Fish** to the narrower **Marlin**.

Option E is invalid since **marlin** is now of type **Fish** and **Fish** doesn’t define the method **getFish(**String**)**.

And that’s it; what’s the point of checking if option F is correct when it is the only one that is left? So postpone it for the Review…

No sooner said than done: the no-arg **Marlin** ctor^([120](#part0021_split_011.html_id_220)) calls the no-arg **super()**, which prints Fish: swims, then the overloaded-for-**String getFish()** prints Marlin: caught, and, finally, the no-arg **getFish()** calls **super.getFish()**, which outputs Fish: caught.

Gosh, it must be hard to be a fisherman…

**Problem 7.25 – CE**

**Given the following classes:**

![](images/00626.jpeg)

**Which two modifications, made independently, enable the code to compile?**

A.Make the method on line 1 public.

B.Make the method on line 2 public.

C.Make the method on line 3 public.

D.Make the method on line 4 public.

E.Make the method on line 3 protected.

Yikes! small but nasty… Or is it?

Starting with option A. The method **code()** on line 1 is `protected` → but the overriding version must have at least the same access privilege → the default access specified on line 3 is more restrictive → options C and E are the answer since only they mention line 3.

Hm… not that nasty, after all.

**Problem 7.26 – CD**

**Given:**

![](images/00627.jpeg)

**Which two modifications, made independently, enable the code to compile?**

A.Replace line 1 with:
`class Plane implements Flier {`

B.Insert at line 2:
`public abstract void takeOff();`

C.Replace line 3 with:
`abstract class Boeing747 extends Plane {`

D.Insert at line 4:
`public void takeOff() { }`

This one should be easy. Since the class **Plane** is `abstract`, it doesn’t need to implement all the `abstract` methods inherited from the superinterface **Flier**; as for the method **land()**, it is properly overridden (same access privilege + `void` + no extra ChE) → we can forget about options A and B as they concern the class **Plane** only → done.

On the Review, however, we’ll have to confirm that it is indeed the class **Boeing747** that needs some fiddling. One option is to declare it `abstract` as the class in its current form doesn't implement the `abstract` method **takeOff()** defined in the interface **Flier**. As for option D, it eliminates the root cause of this evil problem.

**Problem 7.27 – A**

Your enterprising teenage sister asked you to develop an inventory program for her tiny online shop, and after patiently listening to her incoherent, stumbled explanations you realize that the specifications boil down to this:

•The program must contain the classes **Dress**, **ReadyToWear**, and **HauteCouture**. The **Dress** class is the superclass of the other two classes.

•The `double calculatePrice(Dress d)` method should calculate the price of a dress. The `void showDress(Dress d)` method should output the full description of a dress.

**Which definition of the class** `Dress` **can serve as a valid abstraction in the class hierarchy?**

![](images/00628.jpeg)

Option B is faulty as it defines two methods with no bodies, which means the methods must be `abstract` – but the modifier `abstract` is missing in both cases.

Option C has the same problem with the method **calculatePrice()**.

Both methods in option D are declared `abstract` and, as such, shouldn’t have bodies at all.

As for option A, it defines just a single `abstract` method while the other method is concrete, which is perfectly acceptable. In fact, an `abstract` class may be completely void of `abstract` methods.

**Problem 7.28 – DE**

**Given the following data type declarations:**

![](images/00629.jpeg)

**Which option(s), when inserted at line XXX, will fail compilation?**

A.ArrayList<Pilot> alumni = new ArrayList<>();
alumni.add(new D2R2());

B.ArrayList<SpaceCadet> alumni = new ArrayList<>();
alumni.add(new CyberPilot());

C.ArrayList<SpaceCadet> alumni = new ArrayList<>();
alumni.add(new D2R2());

D.ArrayList<D2R2> alumni = new ArrayList<>();
alumni.add(new CyberPilot());

E.ArrayList<Pilot> alumni = new ArrayList<>();
alumni.add(new Pilot());

Option A wants to add a new **D2R2** object into an **ArrayList** generified to **Pilot** → **D2R2** IS-A **CyberPilot**, which IS-A **Pilot** → **D2R2** is narrower than **Pilot** and can easily fit into the provided place → option A compiles.

Option B works with a **CyberPilot** object, which is also a **SpaceCadet** → this option does compile.

Option C is also valid because **D2R2** extends **CyberPilot**, which implements **SpaceCadet** → compiles.

Option D attempts to stick a wider **CyberPilot** object into a place suitable for the objects of the type **D2R2** only → comperr.

As for option E, it wants to instantiate an abstract class.

**Problem 7.29 – E**

**Given:**

![](images/00630.jpeg)

**What is true about the class Test?**

A.It fails compilation because an abstract class cannot have instance variables.

B.It fails compilation because an abstract class cannot have private members.

C.It fails compilation because an abstract class must have at least one abstract method.

D.It fails compilation because an abstract class must have an explicit no-arg constructor.

E.It compiles without error.

The only restriction that should concern us for the OCA exam is that an `abstract` class cannot be instantiated, so every option except E is incorrect.

**Problem 7.30 – AE**

**Which two statements are true?**

A.An abstract class can implement an interface.

B.An abstract class can be extended by an interface.

C.An interface cannot be extended by another interface.

D.An interface can be extended by an abstract class.

E.An abstract class can be extended by a concrete class.

F.An abstract class cannot be extended by an abstract class.

An interface cannot extend a class while a class cannot extend an interface → options B and D are immediately eliminated.

Classes implement interfaces, and `abstract` classes are not an exception; they don’t even have to implement `abstract` methods declared by the interface → option A is true.

Option C is incorrect as interface can extend an interface (or even several of them).

As for option F, there’s no such restriction.

**Problem 7.31 – D**

**Which one is valid?**

A.public interface Diver { protected abstract void dive(); }

B.public abstract class ScubaDiver { protected void dive(); }

C.public abstract class ScubaDiver { protected final abstract void dive(); }

D.public abstract class ScubaDiver { protected abstract void dive(); }

E.public abstract class ScubaDiver { protected abstract void dive() {} }

The access modifier `public` in option A is redundant and the same goes for the modifier `abstract` but this is allowed; what’s not allowed is the modifier `protected` because all the members of an interface are `public` by definition.

Option B violates the rule that says that an `abstract` method in a class must be explicitly declared `abstract` – and we can see that the method **dive()** is `abstract` because it doesn’t have a body.

Option C is also faulty because an `abstract` method cannot be `final` as it would be impossible to make it concrete in a subclass.

Option E is invalid as it defines a method with a body but declares it `abstract`.

**Problem 7.32 – BD**

**Given:**

![](images/00631.jpeg)

**Which two options are valid?**

A.`class B extends A implements I { public void doStuff_B() { } }`

B.`abstract class B extends A implements I { public void doStuff_B() { } }`

C.`class B extends A implements I { public void doStuff_A() { } }`

D.`abstract class B extends A implements I {}`

E.`class B extends A implements I { public void doStuff() { } }`

All the provided options implement the interface **I**, which means that if the class **B** is concrete it must at the very least implement the `abstract` method **doStuff()** → options A and C are immediately eliminated.

Option E does implement **doStuff()** but fails to override **doStuff_A()** although the concrete class **B** inherit the said method from the `abstract` class **A** → option E is out, too. And since the Problem asks for two valid options, we stop looking any further.

On the Review: **B** defines a completely new method **doStuff_B()** and does nothing to implement both **doStuff()** and **doStuff_A()** but it’s OK: **B** is `abstract`, after all. Same goes for option D as the class **B** doesn’t have to do anything whatsoever.

**Problem 7.33 – C**

**Given:**

![](images/00632.jpeg)

**How much money is left in this coder’s pocket?**

A.4900

B.4800

C.0

D.-100

E.-200

Fields are not polymorphic, so one of the most important rules that relate to inheritance, namely

The reftype says what’s available to the object while actype determines what runs

is not fully applicable here; we’ll be using only the first half of the rule; the second half concerns virtual methods.

Alright, here’s the entire logical chain: the object **m**’s reftype is **Money** → does **Money** define the variable **cash**? yes → which **cash** are we accessing through **m**: the one in **Money** or the one that is declared in **LocalCurrency** and which actually hides **Money**’s **cash**? → applying the rule: "the reftype says what’s available…" → the vars declared in an interface are `public`, `static` and `final` by definition → their values cannot be changed → done.

By the way, what should this poor Java coder do in order to finally make some money – I mean, apart from passing the OCA exam?^([121](#part0021_split_011.html_id_224))

**Problem 7.34 – B**

**Given:**

![](images/00633.jpeg)

**What is the result?**

A.Inter

B.Parent

C.Compilation fails

D.Run-time error

This one is probably too advanced for our exam and the chances of meeting something similar to it must be fairly low; nevertheless, the problem is quite interesting as it allows to peek a little deeper into interfaces.

It does appear that there’s a clash between the two versions of **run()**; well, this is what Brian Goetz wrote more than six years ago for the Open JDK Mailing List^([122](#part0021_split_011.html_id_226)):

**Rule #1: Classes win over interfaces. If a class in the superclass chain has a declaration for the method (concrete or abstract), you’re done, and defaults are irrelevant**.

The rule makes perfect sense if we recall that `default` methods serve as a backup in case when a class doesn’t provide an implementation for such methods and neither inherits them from its superclasses.

So the **Parent**’s **run()** wins over **Inter**’s version → the code prints Parent.

![](images/00007.jpeg)

As the inheritance-related questions are notoriously tough, let’s take another look at the most important rules that just might save your day on the exam.

**Rules of Inheritance Revisited***

(be especially attentive when overriding involves a `static` method)

1.A **static** method attempting to **override a non-static** one is **ALWAYS** a comperr, which includes **ALL** cases: interface-interface, class-class or interface-class **AND** throughout the entire inheritance chain (see Remark below).

2.When it comes to overriding between classes, `static` and non-`static` methods are **NEVER** compatible.

Reminder: On the other hand, a non-`static` interface method may override a superinterface’s `static` method.

3.**ANY** other override is valid **EXCEPT** the ‘`abstract static`’ combos which are illegal in the first place.

* leaving out the stuff related to return types and exceptions

Note that Rule 1 holds true even in case of an implementation via inheritance:

![](images/00634.jpeg)

**Simple Corollaries:**

![](images/00012.jpeg)A subinterface can re-declare a `default` method and also make it `abstract`.

![](images/00012.jpeg)A subinterface can re-declare a `static` method but it won’t be overriding.

![](images/00012.jpeg)A `static` method can’t override an `abstract` method between interfaces but the opposite is permitted.

When it comes to vars, `static` may hide non-`static`, and vice versa.

**AGAIN, from a different angle:**

Fields and `static` methods are not overridden, therefore access to fields and `static` methods is determined at compile time based on the type of the variable (while instance methods will run according to the actual type of the object referred to by the variable).

A class cannot inherit two interfaces that both define `default` methods with the same signature, unless the class implementing the interfaces overrides those two competing methods with an `abstract` or concrete method.

More on difference between static and default / abstract methods in interfaces:

Interfaces define behavior, and this behavior is inherited only through non-`static` methods (**shorter wording**: interface `static` methods aren’t inherited).

![](images/00635.jpeg)

static methods defined in the **Parent** class run when the reftype is **Parent**:

![](images/00636.jpeg)

**SAME STORY WITH INTERFACES:**

![](images/00637.jpeg)

**FOR THE LAST TIME**: the reftype determines which methods and fields are available to the object while actype chooses concrete version EXCEPT fields: the fields are ALWAYS of the reftype.

**Corollary:**

When a var that has been declared in an interface IS NOT HIDDEN by the implementing class, we can’t change its value (simply because it’s implicitly `final` → comperr)

Suppose:

1)class **Parent** declares `int a = 0;`

2)class **Child** declares `int a = 100;`

Then:

![](images/00638.jpeg)

Same goes for interfaces except interfaces cannot be instantiated.

* * *

^([100](#part0021_split_000.html_id_187)) Its thread-safe cousin **StringBuffer** is `final`, as well.

^([101](#part0021_split_000.html_id_189)) Official wording can be found in the JSL, §8.2, *Class Members*.

^([102](#part0021_split_002.html_id_191)) It’s about methods only; variables know no such restriction.

^([103](#part0021_split_002.html_id_195)) For the record: the JLS has no notion of actype; this homebrew term is used throughout the book for the sake of brevity as it helps to make rules shorter and more easily memorizable.

^([104](#part0021_split_002.html_id_193)) By declaring a var with the same name in a subclass.

^([105](#part0021_split_002.html_id_197)) Do appreciate the careful wording: the sentence doesn’t say that constructors are polymorphic (after all, they aren’t inherited); they do, however, let non-`private` and non-`final` instance methods exhibit their polymorphic nature.

^([106](#part0021_split_004.html_id_201)) I admit, this will work for our OCA exam – but then you gonna be in a big trouble on 1Z0-809…

^([107](#part0021_split_004.html_id_199)) In other words, non-`final` classes *plus* interfaces since interfaces are non-`final` by definition.

^([108](#part0021_split_008.html_id_203)) Two more non-access modifiers featured on the 1Z0-808 exam are `final` and `static`.

^([109](#part0021_split_008.html_id_307)) [http://stackoverflow.com/questions/34709082/illegal-static-interface-method-call](http://stackoverflow.com/questions/34709082/illegal-static-interface-method-call)

^([110](#part0021_split_010.html_id_205)) [http://www.javaworld.com/article/2073619/core-java/java-tostring---considerations.html](http://www.javaworld.com/article/2073619/core-java/java-tostring---considerations.html)

^([111](#part0021_split_010.html_id_207)) One more time and for the record: this ‘castype’ thingy does NOT exist in Java; it’s just a handy trick to solve exam questions both reliably and quickly, that’s all.

^([112](#part0021_split_010.html_id_309)) "If **A** ← **B** ← **C** *and* **C** c = new **C()**; *then*"

^([113](#part0021_split_010.html_id_311)) To be exact, its full name is *RelationalExpression* operand.

^([114](#part0021_split_011.html_id_209)) Can you name them right now? We covered this in the discussion to [Problem 4.13](#part0018_split_001.html_page_176).

^([115](#part0021_split_011.html_id_211)) [http://docs.oracle.com/javase/tutorial/reflect/class/index.html](http://docs.oracle.com/javase/tutorial/reflect/class/index.html)

^([116](#part0021_split_011.html_id_213)) To hear the JLS saying it in the open (‘[…] consider that while an interface does not have **Object** as a supertype[…]’), refer to §9.6.4.4, *@Override*, where you can also learn why the @Override annotation for, say, **toString()** works in interfaces.

^([117](#part0021_split_011.html_id_215)) For the same reason as line p1 does: since p3 has no explicit call to another constructor, the compiler tries to insert into it a call to a no-arg super() – which is not available in **Painter**. So watch out; you *will* have to dodge this trap on the exam.

^([118](#part0021_split_011.html_id_217)) The call to **super(**name**)** is not the first stat in the body of this constructor.

^([119](#part0021_split_011.html_id_221)) And yes, take it as a hint for the exam: an immediate hunt for ‘un-instantiable’ types will let you not only avoid potential pitfalls but also cross out incorrect options right away.

^([120](#part0021_split_011.html_id_219)) By the way, ctor is a truly vintage term; as to how it should be pronounced, listen to Bjarne Stroustrup himself saying it: [http://www.cpptips.com/ctor_ct](http://www.cpptips.com/ctor_ct).

^([121](#part0021_split_011.html_id_223)) He should better stick to **LocalCurrency**, i.e., `LocalCurrency m = new LocalCurrency()`. *That* would put a bewildered smile on his unshaven face along with 4,900 local currency units into his pocket.

^([122](#part0021_split_011.html_id_225)) [http://mail.openjdk.java.net/pipermail/lambda-dev/2013-March/008435.html](http://mail.openjdk.java.net/pipermail/lambda-dev/2013-March/008435.html)

![](images/00639.jpeg)

**The 1Z0-808 objectives within this group:**

| 8.1 | Differentiate among checked exceptions, unchecked exceptions, and errors |
| 8.2 | Create a `try-catch` block and determine how exceptions alter normal program flow |
| 8.3 | Describe the advantages of exception handling |
| 8.4 | Create and invoke a method that throws an exception |
| 8.5 | Recognize common exception classes (such as **NullPointerException**, **ArithmeticException**, **ArrayIndexOutOfBoundsException**, **ClassCastException**) |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

Covering everything in one common block:

![](images/00012.jpeg)Checked exceptions represent expected exceptional conditions that might affect the execution of the program → the compiler forces the coder to deal with such conditions programmatically.

| *Bottomline*: | If an API client code can reasonably be expected to recover from an exception, make it a ChE. If the client cannot do anything to recover from the exception, make it an unchecked exception. |

![](images/00012.jpeg)What must be handled in a `catch` or `finally` block or declared:

![](images/00640.jpeg)

![](images/00012.jpeg)The unchecked exception classes, which are exempted from compile-time checking:

![](images/00641.jpeg)

![](images/00012.jpeg)The exam does check for the proper use of the keywords `throw` and `throws`:

![](images/00059.jpeg)`throws` is used in method declarations to indicate that an exception *might* be thrown;

![](images/00059.jpeg)`throw` is used when the programmer wants to throw an exception; needs `new`.

![](images/00012.jpeg)Advantages of exceptions^([123](#part0022_split_002.html_id_228)):

![](images/00059.jpeg)Separating error-handling code from ‘regular’ code;

![](images/00059.jpeg)Propagating errors up the call stack;

![](images/00059.jpeg)Grouping and differentiating error types.

***Most Important for the Exam***: If a method invokes another method that might throw a checked exception, the caller must either declare this ChE in its signature OR enclose the call within a TCF construct (a.k.a. ‘Catch-or-Declare Requirement’).

| **Corollary**: | It’s OK if a method declares a ChE while not actually throwing it + it may throw any RTE without warning. |

![](images/00012.jpeg)A `try` block must be followed by either a `catch` or a `finally`, or both.

| **Corollary**: | Neither `catch` nor `finally` may precede `try` or exist without it. |

![](images/00012.jpeg)Multiple `catch` blocks are allowed, but Java runs the first one that matches.

| **Corollary**: | A wider exception may not precede its subclass in the list of `catch`es. |

![](images/00012.jpeg)At most one `catch` block can run.

| **Corollary**: | Nested ChEs thrown in `catch` or `finally` also require handling: |

![](images/00642.jpeg)

![](images/00012.jpeg)`finally` runs last and **always** UNLESS a `try` or `catch` is ‘**System.exit()**ed’.

| **Corollary:** | It runs even if `try` or `catch` has `return` (beware of unreachable stats, though! see below). |

![](images/00012.jpeg)The execution continues after the successfully completed TCF construct.

![](images/00012.jpeg)If both `catch` and `finally` throw an exception, `finally` ‘outshouts’ `catch`.

![](images/00012.jpeg)Unchecked exceptions do not affect method overriding.

![](images/00012.jpeg)Overriding method may not throw a wider or unrelated checked exception.

| ![](images/00012.jpeg) | **Combat Rule:** | Reftype governs checked exception handling: |

![](images/00643.jpeg)

Line XXX fails compilation because the compiler doesn’t even suspect that the actype can never produce a checked exception; it sees only the reftype, which does throw a ChE → the invocation must be wrapped up in a TCF construct or the caller – which in our case is **main()** itself – must declare a throw.

![](images/00012.jpeg)EXTRA: An exception is an **Object** and, as such, can be `null`.

| **Corollary**: | An NPE occurs if the `throw` stat’s expression results in a `null` pointer. |

![](images/00012.jpeg)EXTRA: Exception-wise, the method overriding rule is opposite in case of constructors (ref.to [Chapter II.6](#part0020_split_000.html_page_217), [*Working with Methods and Encapsulation*](#part0020_split_000.html_page_217), for more details).

![](images/00012.jpeg)EXTRA: `finally` executes first and only then a `catch`’s E (if any) is thrown UNLESS `finally` itself `return`s or throws an E in which case `finally`’s E/`return` suppresses the `catch`’s E/`return`.

![](images/00012.jpeg)EXTRA: *Antipattern*: If `catch` or `finally` is followed by statements, those stats will be executed UNLESS a `catch` or `finally return`s or deliberately throws an exception in which case those stats become unreachable thus leading to a comperr.

| **Corollary**: | When a stat follows `finally` or `catch` while BOTH the happy and unhappy paths^([125](#part0022_split_002.html_id_230)) have `return`s in them → the stat becomes unreachable: |

![](images/00644.jpeg)

![](images/00012.jpeg)EXTRA: If both `catch` and `finally` have a `return` stat, the `finally`’s `return` overrides the `catch`’s `return`^([126](#part0022_split_002.html_id_232)). The value returned by `catch` is formed BEFORE `finally` executes:

![](images/00645.jpeg)

![](images/00012.jpeg)EXTRA: When a class implements multiple interfaces, its overriding method must conform to the overriding rules for each overridden method^([127](#part0022_split_002.html_id_234)):

![](images/00646.jpeg)

![](images/00012.jpeg)EXTRA: It’s a comperr if a method contains some ChE catches – except for **Throwable** and **Exception** (because an RTE or **Error** might be thrown) – although `try` block doesn’t even throw a ChE (since the ChE-related `catch` becomes unreachable; RTEs and **Error**s are OK, though):

![](images/00647.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 8.1Given the following two classes:**

![](images/00648.jpeg)

**What is the result?**

A.A

B.B

C.Either A or B

D.AB

E.Line XXX fails compilation

**Problem 8.2Given:**

![](images/00649.jpeg)

**Which two modifications, made independently, will permit the code to compile?**

A.Adding `throws IOException` to the **main()** method signature

B.Adding `throws IOException` to the **doStuff()** method signature

C.Adding `throws IOException` to the **main()** method signature and to the **doStuff()** method signature

D.Adding `throws IOException` to the **doStuff()** method signature and changing the `catch` argument to **IOException**

E.Adding `throws IOException` to the **main()** method signature and changing the `catch` argument to **IOException**

**Problem 8.3Given the following class:**

![](images/00650.jpeg)

**What is the result?**

A.Caught an RTE

B.Out of memory...

C.Out of memory... Total success!

D.Compilation fails because `for(;;)` is endless, which makes `catch` unreachable

E.Compilation fails on line XXX because catching **Error**s is not allowed

**Problem 8.4Given:**

![](images/00651.jpeg)

**Which two are possible outcomes?**

A.Starting…

B.Starting… Finishing…

C.Starting… Finishing… Done!

D.Starting… and Exception in thread "main" java.lang.Exception

**Problem 8.5**

**Which three are advantages of the Java exception mechanism?**

A.Improves the program structure because the error handling code is separated from the normal program function

B.Provides a set of standard exceptions that covers all the possible errors

C.Improves the program structure because the programmer can choose where to handle exceptions

D.Improves the program structure because exceptions must be handled in the method in which they occurred

E.Allows the creation of new exceptions that are tailored to the particular program being created

**Problem 8.6Given the following two classes:**

![](images/00652.jpeg)

**Which two modifications, when used together, will make the code compile?**

A.Add `throws Exception` to the **main()** method’s signature on line 15

B.Replace line 17 with:

![](images/00653.jpeg)

C.Add `throws IOException` to the **printFile()** method’s signature on line 9

D.Replace line 10 with

`if (checkContents(file)) throw new IOException("Exception raised");`

E.Replace line 18 with

`throw new IOException(); }`

**Problem 8.7Given the following interface definition:**

![](images/00654.jpeg)

**Which three implementations are valid?**

![](images/00655.jpeg)

**Problem 8.8**

**The catch clause argument is always of type:**

A.Exception

B.Exception but NOT including RuntimeException

C.Throwable

D.RuntimeException

E.CheckedException

F.Error

**Problem 8.9**

**Suppose, the method doStuff() might throw an unchecked exception. Which of the following is true?**

A.This exception must be caught inside **doStuff()**

B.This exception must be declared by **doStuff()** in its signature

C.The call to **doStuff()** must be wrapped up in a `try-catch` block

D.No action is necessary

**Problem 8.10Given:**

![](images/00656.jpeg)

**What modification will make the code compile and run successfully?**

A.Wrap up the `throw new Exception()` statement in a `try-catch` block that catches a **Throwable**

B.Wrap up the call to **tripOverCat()** in a `try-catch` block that catches an **Exception**

C.Add `throws Exception` to the signature of **run()**

D.Add `throws Exception` to the signature of **run()** and wrap up the call to **tripOverCat()** in a `try-catch` block that catches an **Exception**

**Problem 8.11Given:**

![](images/00657.jpeg)

**What is the result?**

A.!

B.A StringIndexOutOfBoundsException is thrown at runtime

C.A NullPointException is thrown at runtime

D.An IllegalArgumentException is thrown at runtime

**Problem 8.12**

**Which three statements are true?**

A.In multicatch blocks, the subclass exception handler may be placed after the superclass exception handler.

B.A `try` block must be followed by either a `catch` or `finally` block.

C.The class **Exception** is the superclass of all errors and exceptions in Java.

D.A checked exception must be handled explicitly by either catching or declaring it.

E.A single `catch` block can handle more than one type of exception.

**Problem 8.13Given:**

![](images/00658.jpeg)

**What is the result?**

A.WHAT?! No more beer?

B.Excellent!

C.null

D.Total bliss and serenity of being

**Problem 8.14Given the following class:**

![](images/00659.jpeg)

**What is the result?**

A.Cargo loaded - Cargo unloaded

B.Compilation fails only on line c1.

C.Compilation fails only on line c2.

D.Compilation fails only on line c3.

E.Compilation fails at both line c2 and line c3.

**Problem 8.15**

**Which two statements correctly describe checked exceptions?**

A.These are exceptional conditions that a well-written application should anticipate and recover from.

B.These are exceptional conditions that are internal to the application, and that the application usually cannot anticipate or recover from.

C.Every class that is a subclass of RuntimeException and Error is categorized as checked exception.

D.Every class that is a subclass of Exception, excluding RuntimeException and its subclasses, is categorized as checked exception.

**Problem 8.16Given the following classes:**

IndexOutOfBoundsException

FileNotFoundException

StackOverflowException

IllegalFormatException

ArrayOutOfBoundsException

ClassCastException

IOException

IllegalArgumentException

**How many of them are defined in the java.lang package?**

A.One

B.Two

C.Three

D.Four

E.Five

F.Six

G.Seven

H.All of them

**Problem 8.17Given:**

![](images/00660.jpeg)

![](images/00661.jpeg)

**What is the maximum number of letters the code can print?**

A.One

B.Two

C.Three

D.Four

E.All five

F.The code prints nothing because compilation fails

**Problem 8.18Given the following two files:**

![](images/00662.jpeg)

**What is the result?**

A.Oh no…

B.Oh no… Finally!

C.I’m ordering pizza tonight!

D.I’m ordering pizza tonight! Finally!

E.Compilations fails

**Problem 8.19Given:**

![](images/00663.jpeg)

**What is the result?**

A.Lemme think…

B.Marry her?! You gotta be kidding me!

C.Compilation fails

D.NullPointerException at run time

**Problem 8.20Given:**

![](images/00664.jpeg)

**Which four are true?**

A.If lines X and XX are commented out, the code prints 42

B.If line XXX is commented out, the code prints either 1 or 666

C.If lines X and XXX are commented out, the code prints 123

D.If line XX is commented out, the code prints 123

E.If lines XX and XXX are commented out, the code prints either 1 or 123

F.If line XXXX is commented out, the code prints 42

G.If lines XXX and XXXX are commented out, the code prints either 1 or 666

**Problem 8.21Given:**

![](images/00665.jpeg)

**Which one is true?**

A.The code always prints 42

B.The code will fail compilation if either of lines t1 and t3 is commented out

C.The code compiles if both t1 and t2 are commented out

D.None of the above

**Problem 8.22Given:**

![](images/00666.jpeg)

**Which two are true?**

A.The keyword `throws` on line 4 is redundant

B.The `try-catch` statement on lines 6 through 9 is redundant

C.The code prints Caught NPE + Caught IOE

D.A **RuntimeException** is thrown at run time

E.Compilation fails

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 8.1 – B**

**Given the following two classes:**

![](images/00667.jpeg)

**What is the result?**

A.A

B.B

C.Either A or B

D.AB

E.Line XXX fails compilation

As **MyException** IS-A **RuntimeException**, either of them gets caught on line t1, so **run()** never throws an exception to the outside → the printing stat on line t2 has no chance to fire.

Option C would have been correct if before line t1 there were another handler that catches **MyException** and prints A.

**Problem 8.2 – CD**

**Given:**

![](images/00668.jpeg)

**Which two modifications, made independently, will permit the code to compile?**

A.Adding `throws IOException` to the **main()** method signature

B.Adding `throws IOException` to the **doStuff()** method signature

C.Adding `throws IOException` to the **main()** method signature and to the **doStuff()** method signature

D.Adding `throws IOException` to the **doStuff()** method signature and changing the `catch` argument to **IOException**

E.Adding `throws IOException` to the **main()** method signature and changing the `catch` argument to **IOException**

To solve this one, we need to see what’s wrong with the code in the first place.

The available options tell us that the error must be caused by an unhanded exception, and the only kind of exceptions the compiler cares about is checked exceptions.

The so-called Catch-or-Specify Requirement^([129](#part0022_split_002.html_id_236)) that governs the handling of checked exceptions says that the code that might throw a ChE must be placed inside an appropriate `try-catch` block or the caller itself must declare this exception (or its superclass).

The source of trouble, namely line c5, lives inside the method **doStuff()**, which does nothing to prevent an **IOException** from escaping. Now let’s ask ourselves how can **doStuff()** fulfill the Catch-or-Specify Requirement? The CSR offers two ways to do this but only one of them is available to us because the list of options doesn’t mention wrapping up the offending code in a TCF construct → we have no choice but modify **doStuff()**’s signature → any option that fails to do so is out → options A and E are eliminated.

What about option B? By confessing that it can’t handle the exception, **doStuff()** washes its hands of all responsibility for whatever might happen at run time and transfers it to the caller instead. Alas, the caller – the method **main()** – is armed with the butterfly net that is suitable for catching RTEs but not IOEs because there’s no IS-A relationship between **IOException** and **RuntimeException**. This means, in turn, that **main()**, too, must warn its caller, Lady Jay V. Emme, by chanting "By the pricking of my thumbs, something wicked your way comes!". The method **main()**, however, is ominously silent, its signature says nothing about the nasty surprise brewing inside **doStuff()**’s bowels → the compiler can’t and won’t let the unspeakable thing happen.

On the other hand, option C forms an appropriate chain of warnings – from **doStuff()** to **main()** and beyond – while option D equips **main()** with an upgraded net that won’t let IOEs through this time.

**Problem 8.3 – C**

**Given the following class:**

![](images/00669.jpeg)

**What is the result?**

A.Caught an RTE

B.Out of memory...

C.Out of memory... Total success!

D.Compilation fails because `for(;;)` is endless, which makes `catch` unreachable

E.Compilation fails on line XXX because catching **Error**s is not allowed

The API documentation for the class **java.lang.Error** says that

An Error is a subclass of **Throwable** that indicates serious problems that a reasonable application should not try to catch. Most such errors are abnormal conditions.

Catching errors is considered bad programming practice. A better way to react to such problems is to print a stack trace and exit → option E is incorrect since Java does not explicitly forbid catching **Error**s.

Now let’s consider option D. While it is true that an endless `for` well might bring about a comperr because of a potentially unreachable statement after the loop, wrapping it up in a `try` block^([130](#part0022_split_002.html_id_240)) provides a non-zero chance of escape → option D is out.

However, what does happen in our code? `for(;;)` is indeed endless^([131](#part0022_split_002.html_id_238)), and the **add()** method will be happily adding new elements one after another until… until… Wait a sec! just how long can be **ArrayList**?!

The documentation for **ArrayList** says that the method `size()` returns an `int`; we also know that **Integer.MAX_VALUE** is two in the power of 31 (for an `int` holds a signed 32-bit integral value, and a half of this space is used to represent negative numbers). Can we take it as an indication that after our **list** reaches this limit, something must give in throwing an exception along the way? Sounds logical but we aren’t out of hot water yet for it is still necessary to figure out what kind of exception it’s going to be: an RTE or an Error.

The description for **ArrayList**’s **size()** is tight-lipped: all it says is that the method "returns the number of elements in this list". On the other hand, **ArrayList** implements **List**, and **List**’s documentation is more accommodating:

`int size()`

Returns the number of elements in this list. If this list contains more than Integer.MAX_VALUE elements, returns Integer.MAX_VALUE.

There you have it: **ArrayList** may contain more than 2^(31) elements, it’s only its reported size that cannot exceed this limit → our initial chain of reasoning wasn’t entirely correct for the code is going to gobble up all available heap space → and only then the JVM will throw **OutOfMemoryError** → which gets caught → the execution will terminate normally (it’ll take a few seconds, though).

My gentle readers might object: we are not allowed to consult the API docs on the exam. That much is true but none of the actual questions run that deep. Consider this problem to be a sort of a bridge to the next [Chapter](#part0023_split_000.html_page_370), which deals with a number of core Java classes including **ArrayList**. Besides, it is probably not entirely a bad idea to remember that sometimes there’s more than meets the eye.

On a final note please also observe that the listing does not mention an import for either **java.util.List** or **java.util.ArrayList**. This is in line with the assumptions that we are told to make for the exam (ref.to *Missing package and import statements* in [Chapter II.0](#part0014.html_page_38), [*Opening Remarks*](#part0014.html_page_38)).

**Problem 8.4 – CD**

**Given:**

![](images/00670.jpeg)

**Which two are possible outcomes?**

A.Starting…

B.Starting… Finishing…

C.Starting… Finishing… Done!

D.Starting… and Exception in thread "main" java.lang.Exception

When line t1 doesn’t throw an exception, nothing prevents the last printing stat from firing, while the alternative case makes the uncaught exception propagate up the call stack.

**Problem 8.5 – ACE**

**Which three are advantages of the Java exception mechanism?**

A.Improves the program structure because the error handling code is separated from the normal program function

B.Provides a set of standard exceptions that covers all the possible errors

C.Improves the program structure because the programmer can choose where to handle exceptions

D.Improves the program structure because exceptions must be handled in the method in which they occurred

E.Allows the creation of new exceptions that are tailored to the particular program being created

The official Oracle tutorial lists "separation, propagation and differentiation" as the three advantages. In all probability, the actual wording will be different so you’ll be needing to think for a moment what these three concepts might imply.

A question to this tune *is* on the exam in the ‘Core’ section for I personally met it both times.

**Problem 8.6 – AC**

**Given the following two classes:**

![](images/00671.jpeg)

![](images/00672.jpeg)

**Which two modifications, when used together, will make the code compile?**

A.Add `throws Exception` to the **main()** method’s signature on line 15

B.Replace line 17 with:

![](images/00673.jpeg)

C.Add `throws IOException` to the **printFile()** method’s signature on line 9

D.Replace line 10 with

`if (checkContents(file)) throw new IOException("Exception raised");`

E.Replace line 18 with

`throw new IOException(); }`

"Catch or Declare", a.k.a. Catch-or-Specify Req: this is the rule we’ll be applying in every single case when dealing with ChEs on the exam. Let’s see what we’ve got here; the culprit lives on line 10, and the code provides no handler for it → following the CSR, we need either to put a TCF construct here or change **printFile()**’s signature → available options do not list a `try-catch` block that would successfully handle the ChE-throwing LOC → we are left with no choice but declare `throws IOException` on line 9 → option C is in.

Now that the caller, namely the method **main()**, is informed of the impending attack and must take appropriate countermeasures, it’s time to set the defensive perimeter (‘`catch`’) or, failing that, dispatch a warning to the GHQ (‘`throws`’).

Option B offers something promising, something that appears suitable for catching ChEs but a closer look reveals that this particular block of code is faulty: the clause `catch(Exception e)` makes the next `catch` unreachable because **Exception** is wider than **IOException** → option B is out.

Since the options don’t give us an appropriate TCF construct to protect **main()** from the inside, we must declare → the only choice that has anything to do with **main()**’s signature is A. And we stop here immediately without even checking if this option is indeed correct because it is better to leave the validity analysis for the Review; the first pass is about saving time…

Out of curiosity, what else can be done to the code to satisfy the CSR? Now it should be rather obvious that we might wrap up lines 10 or 17 in `try-catch` blocks whose `catch` clauses can have **IOException**, **Exception** or even **Throwable** in them; swapping the `catch` clauses in option B would also help.

**Problem 8.7 – ACD**

**Given the following interface definition:**

![](images/00674.jpeg)

**Which three implementations are valid?**

![](images/00675.jpeg)

One of the rules that govern method overriding says that the version defined in a subtype may not throw a new ChE. Fine; so what exactly would be a "new checked exception" in this particular case?

Obviously, it must be something that fails IS-A test. Let’s methodically run through the options to see what we can find.

Option A throws **IOException** → the option does not violate the rule of method overriding and, therefore, is in.

Option B throws **Exception**, which is a supertype for **IOException** → we can’t say that **Exception** IS-A **IOException**, although the opposite is true → option B is out.

As for the next two options, they are all correct for **FileNotFoundException** IS-A **IOException** because **IOException** is its parent, and option D is so timid that it does not throw any exception at all, not even an RTE.

**Problem 8.8 – C**

**The catch clause argument is always of type:**

A.Exception

B.Exception but NOT including RuntimeException

C.Throwable

D.RuntimeException

E.CheckedException

F.Error

An exception is represented by an instance of the class **Throwable** (a direct subclass of **Object**) or one of its subclasses, says the Java Lang Spec in its §11.1.1, *The Kinds of Exceptions*.

**Problem 8.9 – D**

**Suppose, the method doStuff() might throw an unchecked exception. Which of the following is true?**

A.This exception must be caught inside **doStuff()**

B.This exception must be declared by **doStuff()** in its signature

C.The call to **doStuff()** must be wrapped up in a `try-catch` block

D.No action is necessary

The unchecked exception classes, says the JLS, are the run-time exception classes and the error classes; what’s more, the unchecked exception classes are exempted from compile-time checking (ref.to §11.2, *Compile-Time Checking of Exceptions*) → options A through C are out.

**Problem 8.10 – A**

**Given:**

![](images/00676.jpeg)

**What modification will make the code compile and run successfully?**

A.Wrap up the `throw new Exception()` statement in a `try-catch` block that catches a **Throwable**

B.Wrap up the call to **tripOverCat()** in a `try-catch` block that catches an **Exception**

C.Add `throws Exception` to the signature of **run()**

D.Add `throws Exception` to the signature of **run()** and wrap up the call to **tripOverCat()** in a `try-catch` block that catches an **Exception**

"Catch or Declare" all over again. Remember: we always start from the point of origin going up the call stack.

Has **tripOverCat()** a `try-catch` handler? nope → does the list of options provide a suitable handler? yeap. Done.

**Problem 8.11 – B**

**Given:**

![](images/00677.jpeg)

**What is the result?**

A.!

B.A StringIndexOutOfBoundsException is thrown at runtime

C.A NullPointException is thrown at runtime

D.An IllegalArgumentException is thrown at runtime

Although we are going to look into the class **String** in detail in the next [Chapter, *Working with selected classes from the Java API*](#part0023_split_000.html_page_370), the method invocation on line t1 is self-explanatory: the code wants to know what character occupies the 4th slot in the string known as **str**. Besides, the Exam Objective we are discussing right now prescribes knowledge of the most ‘popular’ exceptions thrown by **String**, **StringBuilder**, **ArrayList**, and a number of other core Java classes…

Do you remember the strange-but-true example from our talk on the constructors? the one that deals with a single-arg **StringBuilder** constructor that accepts a **StringBuilder** object as its argument?^([132](#part0022_split_002.html_id_248)) simply because one of the constructors accepts a **CharSequence** object, and **StringBuilder** does implement the interface **CharSequence**?

Well, here we have a similar situation, in the sense that **String** implements **CharSequence**, too^([133](#part0022_split_002.html_id_246)). The method **charAt()** is specified by **CharSequence** and, according to the API documentation, throws an **IndexOutOfBoundsException** (removing option D along the way). We don’t have this choice in out list of options but a **StringIndexOutOfBoundsException**, which is a subtype of IOOBE, does get mentioned → this is the correct answer because, after all, SIOOBE IS-A IOOBE. What’s more, the javadocs for IOOBE says that "Applications can subclass this class to indicate similar exceptions", and this is exactly what happens in practice with the **charAt()** refined by the class **String**… *at least in its current implementation* although it is unlikely that Oracle is indeed going to change **String** some day. On the other hand, Java 9 is going to have something called Compact Strings^([134](#part0022_split_002.html_id_244)), which just might declare throwing a certain BrandNewException that is a subtype of IOOBE without breaking the documented contract.

Fortunately for us, the options do not mention **ArrayIndexOutOfBoundsException** although this exception does extend IOOBE and is SIOOBE’s sibling. Given the fact that **String** is backed by an array of characters it would be rather hard to decide between these two exceptions without consulting documentation.

And finally, I would like to call your attention to option C. Can you tell why an NPE isn’t applicable here?^([135](#part0022_split_002.html_id_242))

**Problem 8.12 – BDE**

**Which three statements are true?**

A.In multicatch blocks, the subclass exception handler may be placed after the superclass exception handler.

B.A `try` block must be followed by either a `catch` or `finally` block.

C.The class **Exception** is the superclass of all errors and exceptions in Java.

D.A checked exception must be handled explicitly by either catching or declaring it.

E.A single `catch` block can handle more than one type of exception.

Option A is obviously incorrect because a wider exception type will intercept all its subtypes thus making the next `catch` unreachable.

Option B is in line with the JLS requirements while option C is an arrogant impostor who is trying to pass itself for the class **Throwable**.

Option D is another wording for the Catch-or-Specify Requirement, and option E is correct, too, because the JLS does provide for multi-`catch` clauses^([136](#part0022_split_002.html_id_250)), like this:

![](images/00678.jpeg)

Although it seems that the multi-`catch` clauses are not on the 1Z0-808, they are interesting animals in themselves and offer a lot of opportunities to place and arm some nice traps. For instance, the exception parameter in a uni-`catch` is `final` effectively whereas in a multi-`catch` clause it is `final` implicitly, which could blow off a finger or two. Or consider the following example:

![](images/00679.jpeg)

Even though the above `catch` clause resembles a correctly coded multi-`catch` block (the narrower **IOException** comes before **Exception**, which is wider), this snippet won’t work because alternatives in a multi-`catch` clause cannot be related by inheritance. Just so you know.

**Problem 8.13 – C**

**Given:**

![](images/00680.jpeg)

**What is the result?**

A.WHAT?! No more beer?

B.Excellent!

C.null

D.Total bliss and serenity of being

Apparently, the class **TGIF** compiles so we need only to figure out what exception type the `try` block throws and what happens next. Since all three potential exceptions get thrown inside the enhanced `for` loop, let’s take a closer look at it.

Our `for-each` loop iterates over a **String** array that is referenced by a local var → from the previous chapters we know that local vars offer two popular spots to place mines: 1) the vars must be explicitly inited before being used, and 2) their scope is limited to the method / block they are declared in.

Has been **sixpack** inited? Oh yes; because it’s a reference var^([137](#part0022_split_002.html_id_252)). But what about the slots of this array? what values do they hold? The answer is, of course, the default values – which are `null` → **coldOne.contents** attempts to access a field on a `null` object → NPE.

As NPE IS-A **RuntimeException**, the second `catch` intercepts it and prints out the message that the exception object contains. Since the code didn’t specify the message for an NPE-throwing scenario, the JVM constructs a new **Throwable** with `null` as its detail message, which gets passed to **toString()**; so this is why the correct answer is option C.

If **coldOne.contents** were replaced with just **coldOne**, the result would have been option A… not to mention that filling^([138](#part0022_split_002.html_id_254)) the bottles after LOC XXX with something like

![](images/00681.jpeg)

would have yielded option B… and then – as a bonus – ;D.

**Problem 8.14 – D**

**Given the following class:**

![](images/00682.jpeg)

**What is the result?**

A.Cargo loaded - Cargo unloaded

B.Compilation fails only on line c1.

C.Compilation fails only on line c2.

D.Compilation fails only on line c3.

E.Compilation fails at both line c2 and line c3.

So many options hinting at an imminent compilation failure… → in all probability, the code doesn’t compile. Very well, let’s see if it is indeed the case.

Line c1 looks fine, it just throws a **RuntimeException**, which is not a checked exception so the compiler can’t care less if the method declares an RTE or not. Since line c1 doesn’t do anything illegal, option B is out.

As the method **load()** throws a **RuntimeException**, the caller doesn’t have to do anything → option C is also incorrect → since option E needs a comperr on line c2, it gets automatically eliminated → now we have to choose only between A and D.

Line c3 calls the method **unload()**, which throws an **Exception**, which – being unhandled – goes up the call stack meaning that the caller, namely the method **main()**, must do something about it. Since **main()** didn’t declare a thrown exception in its signature, it should have wrapped up line c3 in a `try-catch` block, which is missing → compilation does fail on line c3.

**Problem 8.15 – AD**

**Which two statements correctly describe checked exceptions?**

A.These are exceptional conditions that a well-written application should anticipate and recover from.

B.These are exceptional conditions that are internal to the application, and that the application usually cannot anticipate or recover from.

C.Every class that is a subclass of RuntimeException and Error is categorized as checked exception.

D.Every class that is a subclass of Exception, excluding RuntimeException and its subclasses, is categorized as checked exception.

The wording of this Problem comes straight from the official Oracle tutorial^([139](#part0022_split_002.html_id_256)):

The first kind of exception is the checked exception. These are exceptional conditions that a well-written application should anticipate and recover from…

The second kind of exception is the error. These are exceptional conditions that are external to the application, and that the application usually cannot anticipate or recover from…

The third kind of exception is the runtime exception. These are exceptional conditions that are internal to the application, and that the application usually cannot anticipate or recover from.

And this is what the JLS has to say on the matter (§11.1.1, *The Kinds of Exceptions*):

Exception is the superclass of all the exceptions from which ordinary programs may wish to recover.

The class RuntimeException is a direct subclass of Exception. RuntimeException is the superclass of all the exceptions which may be thrown for many reasons during expression evaluation, but from which recovery may still be possible.

The unchecked exception classes are the run-time exception classes and the error classes.

The checked exception classes are all exception classes other than the unchecked exception classes.

Options B and C are eliminated based on the above definitions.

**Problem 8.16 – C**

**Given the following classes:**

IndexOutOfBoundsException

FileNotFoundException

StackOverflowException

IllegalFormatException

ArrayOutOfBoundsException

ClassCastException

IOException

IllegalArgumentException

**How many of them are defined in the java.lang package?**

A.One

B.Two

C.Three

D.Four

E.Five

F.Six

G.Seven

H.All of them

As far as I remember, no exception-related question on the exam was missing imports because most of the **Throwable**s were from the **java.lang** package. Two notable exceptions (no pun intended) were **IOException** (defined in **java.io**) and its subclass **FileNotFoundException**.

The following exceptions, which the options mention, are defined in **java.lang**:

![](images/00683.jpeg)

So far so good. Now, can you guess which package **FileNotFoundException** is defined in? Let’s do it together: since **IOException** lives in **java.io**, it is only reasonable that FNFE would be camping there, too. And, in fact, it does. Outstanding. Our logic is impeccable.

But the architects of the core Java classes are not linear beings; or, at the very least, they seem to follow a more convoluted path to Ultimate Truth: although **IllegalArgumentException** does reside in **java.lang**, its child **IllegalFormatException** is at home in **java.util**…

As for StackOverflowException and ArrayOutOfBoundsException, these are not amongst the core Java classes, to put it mildly.

**Problem 8.17 – D**

**Given:**

![](images/00684.jpeg)

**What is the maximum number of letters the code can print?**

A.One

B.Two

C.Three

D.Four

E.All five

F.The code prints nothing because compilation fails

Let’s consider the happy path first: **main()** calls **doStuff()** → **doStuff()** calls **doMoreStuff()** → **doMoreStuff()** prints E and terminates → **doStuff()** then prints D and terminates → `try` prints A → `finally` prints C → FULL STOP → ‘EDAC’ => four letters in total. As the class contains only four printing stats and no loops, we can conclude our analysis at this point.

On the Review, however, we should also consider the unhappy path: **main()** calls **doStuff()** → **Math.random()** throws an RTE → we jump out of `try` and the exception gets caught → `catch` prints B → then `finally` prints C → ‘BC’ => two letters only.

**Problem 8.18 – E**

**Given the following two files:**

![](images/00685.jpeg)

**What is the result?**

A.Oh no…

B.Oh no… Finally!

C.I’m ordering pizza tonight!

D.I’m ordering pizza tonight! Finally!

E.Compilations fails

When `if` throws a **WeightOutOfBoundsException**, this object goes up the call stack (after all, the method **standOnScale()** doesn’t have a `try-catch` block but declares that it might throw an **Exception**, and WOOBE IS-A **Exception** → this exception gets caught because the `catch` stat is specifically tailored to WOOBE → since this particular exception class overrides **toString()**, the code outputs ‘Oh no…’ → then `finally` adds its own two cents… Right?

Wrong. Because **Exception**, which is declared by **standOnScale()**, is wider than its user-defined child; the code needs another handler, something along these lines:

![](images/00686.jpeg)

to get rid of the comperr although we would never see this particular ‘butterfly net’ engaged: the catch intercepts the *run-time* object whose type is WOOBE rather than **Exception**.

Replacing **Exception** with **WeightOutOfBoundsException** in **standOnScale()**’s signature would have yielded randomly alternating options B and D.

By the way, an attempt to arrive at the correct answer by elimination (like: since the code forks at `if`, there should be *two* possible outputs → the question uses singular case implying that only one option is valid → therefore, it must be E) is faulty because, speculating purely theoretically, both branches of a conditional construct may lead to exact same end result, that’s why we need to analyze the code itself.

**Problem 8.19 – C**

**Given:**

![](images/00687.jpeg)

**What is the result?**

A.Lemme think…

B.Marry her?! You gotta be kidding me!

C.Compilation fails

D.NullPointerException at runtime

What can be the reasons for the compilation to fail? Let’s check: interface members are implicitly `public` + **marryHeroine()** in **Prince** isn’t `static` and, therefore, can be inherited → the overriding method in the implementing class must be both `public` and non-`static` → which is exactly what **Charming** does. Good.

Another landmine: the overriding method may not throw a new ChE → well, it doesn’t → if the compilation fails, it isn’t because of invalid overriding. Hm-m…

Alright, it’s time to apply the Check-or-Declare rule: **main()** invokes **marryHeroine()** on the object **prince** and… Aha! Since the compiler cannot know what will be the actual type of the object at run time (it’s the JVM’s prerogative, after all), it just looks at the reftype → and the reftype does threaten to throw a ChE → the invocation must be either enclosed in a `try-catch` or **main()** itself must declare in its signature that it might throw an IOE…

This simple rule

Reftype Governs Exception Handling

will surely come in handy on the exam. Let’s play with it and see how it works one more time. Consider the following class definitions:

![](images/00688.jpeg)

Now the question: how can we fill in the blanks so that the code compiles?

‘Reftype governs exception handling’ → does **Parent**’s version of **doStuff()** throw a ChE? yes → neither the invocation is wrapped up in a `try-catch` nor **main()** declares → the reftype cannot be **Parent** for it would violate the CSR otherwise → the reftype must be **Child** → the only compilable combination of types is **Child – Child** because **Child – Parent** won’t work without an explicit cast, which is absent.

And since we mentioned casting, let’s add that one more way to make code compile is cast the object to a subtype that doesn’t throw an unhandled ChE, and then invoke a method on this object:

![](images/00689.jpeg)

Now we can even refine our rule:

When a reftype throws a ChE outside, the caller MUST handle it somehow UNLESS the reference is explicitly cast to a silent actype.

Or maybe it’s just too long; maybe the four-word version works better… It’s up to you.

**Problem 8.20 – CEFG**

**Given:**

![](images/00690.jpeg)

**Which four are true?**

A.If lines X and XX are commented out, the code prints 42

B.If line XXX is commented out, the code prints either 1 or 666

C.If lines X and XXX are commented out, the code prints 123

D.If line XX is commented out, the code prints 123

E.If lines XX and XXX are commented out, the code prints either 1 or 123

F.If line XXXX is commented out, the code prints 42

G.If lines XXX and XXXX are commented out, the code prints either 1 or 666

The most important thing^([140](#part0022_split_002.html_id_258)) to remember about `finally` is that it always runs unless there’s `System. exit()` somewhere in `try-catch`. Moreover, `finally`’s `return` always suppresses `return` in `catch` or `try`. And here’s another practical guideline to crack questions on the exam:

The post-exception-handling stats are unreachable if there’s an unconditional `return` in ether `finally` or in both `try` and `catch`.

Apparently, we have both scenarios, which means line XXXX must be definitely unreachable. Duly noted; now, is there other reasons to suspect an imminent compilation failure? for example, what about the exception itself? what if the code is missing some handlers?

Nope, the worst thing the `try` block can do is divide by zero, and this generates **ArithmeticException**, which is a **RuntimeException**, and the compiler doesn’t care about RTEs; besides, this exception does get caught.

We can conclude, therefore, that all that commenting out is about getting rid of the ‘unreachable statement’ comperr. Fine; now we may start analyzing our options.

If line X is removed, `catch` won’t even run but `finally` will → line XXXX remains unreachable → option A is incorrect.

If line XXX is commented out, the ‘happy’ `try` returns unconditionally whereas ‘unhappy’ `try` hands the execution flow over to `catch`, which also returns unconditionally → line XXXX is still out of reach → option B is incorrect.

When we remove lines X and XXX, `try` doesn’t throw anything → `catch` won’t run → and since `finally` is ‘returnless’, line XXXX runs freely → option C is correct.

Option D cannot work because even though `catch` is now ‘returnless’, both `try` and `finally` still return some values unconditionally → line XXXX becomes again unreachable.

Commenting out both XX and XXX lets ‘happy’ `try` output 1 while the unhappy path leads to printing 123 → option E is correct.

Since our code doesn’t have `System. exit()` in it, `finally` always runs, and uncommenting the unreachable line XXXX makes compilation succeed → option F is correct, as well.

Lastly, as soon as we comment out line XXXX, the code becomes compilable, and removing overriding `return` in `finally` gives green light to whatever `catch` has to say whenever `try` is unhappy → option G is in, too.

Let’s conclude this twisted example by stating firmly that putting `return` in `finally` is unadvisable.

**Problem 8.21 – D**

**Given:**

![](images/00691.jpeg)

**Which one is true?**

A.The code always prints 42

B.The code will fail compilation if line t1 is commented out

C.The code compiles if both t1 and t2 are commented out

D.None of the above

Removing line t1 could have led to a comperr if the exception argument in `catch` clause were of any subtype of **Exception** other than an RTE: the compiler would have objected saying that such and such exception ‘is never thrown in body of corresponding `try` statement’.

Making both t1 and t2 disappear won’t affect compilation, either, because `finally` guarantees a returning value. By the same token, commenting out line t3 is suicidal as the happy path will be left without `return`.

There’s one more side to the story. The ‘*unless-system.exited-finally-runs-always*’ rule holds true ONLY IF the code enters the `try-catch-finally`. Do not automatically assume that if there’s a ‘returning’ `finally` somewhere in the code you can instantly grab this `return` and use it; check first if the flow indeed enters the TCF block (for example, in our case there is a fifty-fifty chance that it doesn’t → strictly speaking, the rule should read: "Once the execution enters the TCF block, `finally` always runs unless there is a `System.exit()` in `try` or `catch`".

**Problem 8.22 – AE**

**Given:**

![](images/00692.jpeg)

**Which two are true?**

A.The `try-catch` statement on lines 10 through 13 is needed

B.The `try-catch` statement on lines 6 through 9 is redundant

C.The code prints Caught NPE + Caught IOE

D.A **RuntimeException** is thrown at run time

E.Compilation fails

**IOException** is a checked exception, so the code must fulfill the CSR, which it does by enclosing line 11 in a `try-catch` stat → option A is correct.

Now let’s consider option B. Line 7 throws `null`, which is the last scenario among the Magnificent Five → line 7 results in a NPE → since NPE is a **RuntimeException**, the code doesn’t have to handle it at all → it seems that the `try-catch` stat on lines 6 thru 9 is not needed… Unfortunately, this is not the case.

What will happen if we comment out the first `try-catch` on lines 6–9? Line 7 will throw an NPE – which is now unhandled – and the JVM will abort the execution so the `try` on line 10 becomes unreachable. In other words, the `try-catch` on lines 6 thru 9 is needed *not* because of exception handling requirements but because it makes the subsequent stats reachable.

What about option C? It contains two sub-outputs, which imply that both catches run with the first `catch` printing Caught NPE. Now, line 11 actually throws `null` since **ioe** is `null` (ref.to line 5) but the fact is `catch` on line 13 handles only IOE or its subtypes → this `catch` can’t even run.

So, may we conclude that option D is the correct one? that the code will first print ‘Caught NPE’ and then throw an NPE?

The answer is No. Because the compilation fails.

So far our job was somewhat easier than on the actual exam since we could make an educated guess what the problem was about; say, the questions to a loop-discussing chapter must be testing us on loops, the questions in a chapter that relates to exception handling must be about the CSR, and so on. The actual exam isn’t like that: the problems come in randomly, so we have no idea what they can be asking for… Alright, so why does the compilation fail? It’s because the exception argument declared in the `catch` clause on line 13 clashes with the variable **ioe** declared earlier on line 5… Scope of variables; yes, it’s that simple…

That’s why we have to be on our guard all the time – especially when there’s a ‘Compilation fails’ option (although it does seem to be a mere place holder in our problem).

* * *

^([123](#part0022_split_000.html_id_227)) [https://docs.oracle.com/javase/tutorial/essential/exceptions/advantages.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/advantages.html)

^([124](#part0022_split_000.html_foot4)) [https://www.youtube.com/watch?v=nGeKSiCQkPw](https://www.youtube.com/watch?v=nGeKSiCQkPw)

^([125](#part0022_split_000.html_id_229)) Visit [https://twitter.com/ronjeffries/status/586902281125232640](https://twitter.com/ronjeffries/status/586902281125232640) for other variants.

^([126](#part0022_split_000.html_id_231)) The 1Z0-803 Study Guide by Mala Gupta mentions (p.389) that "If a `catch` block returns a primitive data type, a `finally` block can’t modify the value being returned by it". The example below, however, proves otherwise.

^([127](#part0022_split_000.html_id_233)) FYI: **InterruptedException** is a ChE.

^([128](#part0022_split_000.html_foot5)) "Item 65: …An empty `catch` block defeats the purpose of exceptions" (*Effective Java* by Joshua Bloch).

^([129](#part0022_split_002.html_id_235)) [https://docs.oracle.com/javase/tutorial/essential/exceptions/catchOrDeclare.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/catchOrDeclare.html)

^([130](#part0022_split_002.html_id_239)) We discussed this scenario in [Chapter II.5, *Using Loop Constructs*](#part0019_split_000.html_page_188).

^([131](#part0022_split_002.html_id_237)) In its place we could have, for example, `while(true)` or `do-while(true)`, as well.

^([132](#part0022_split_002.html_id_247)) [Problem 6.34](#part0020_split_006.html_id_333).

^([133](#part0022_split_002.html_id_245)) There are only three more **CharSequence**-implementing classes in the core Java API – **CharBuffer**, **Segment** and **StringBuffer** – but they are not on the exam.

^([134](#part0022_split_002.html_id_243)) [https://blogs.oracle.com/java/strings-in-java-9](https://blogs.oracle.com/java/strings-in-java-9)

^([135](#part0022_split_002.html_id_241)) This is about remembering those NPE-throwing scenarios; yes, again; because it’s so important for the exam… Alright, the reason why option C is out is that none of those five scenarios can be realized in our example: the code doesn’t throw a null and as for the object itself, it has been properly inited and is not null.

^([136](#part0022_split_002.html_id_249)) A single `catch` clause that handles only one type of exceptions is called a uni-`catch`.

^([137](#part0022_split_002.html_id_251)) We covered this already when discussing [Problem 2.1](#part0016_split_001.html_id_334).

^([138](#part0022_split_002.html_id_253)) We can’t use the enhanced `for` loop here because it is a sort of ‘read-only’ operation: its equivalent form written as a regular `for` stat uses the method **next()** defined by the interface **Iterator** (JLS, §14.14.2, *The enhanced for statement*).

^([139](#part0022_split_002.html_id_255)) [https://docs.oracle.com/javase/tutorial/essential/exceptions/catchOrDeclare.html](https://docs.oracle.com/javase/tutorial/essential/exceptions/catchOrDeclare.html)

^([140](#part0022_split_002.html_id_257)) Exam-wise, that is.

![](images/00693.jpeg)

**The 1Z0-808 objectives within this group:**

| [9.1](#part0023_split_000.html_c9.1) | Manipulate data using the **StringBuilder** class and its methods |
| [9.2](#part0023_split_000.html_c9.2) | Creating and manipulating **String**s |
| [9.3](#part0023_split_002.html_c9.3) | Create and manipulate calendar data using classes from **java.time.LocalDateTime**, **java.time.LocalDate**, **java.time.LocalTime**, **java.time.format.DateTimeFormatter**, **java.time.Period** |
| [9.4](#part0023_split_004.html_c9.4) | Declare and use an **ArrayList** of a given type |
| [9.5](#part0023_split_006.html_c9.5) | Write a simple lambda expression that consumes a lambda **Predicate** expression |

![](images/00061.jpeg) **CORE RULES (with some Extras):**

9.1Manipulate data using the **StringBuilder** class and its methods +

9.2Creating and manipulating **String**s:

![](images/00012.jpeg)Both **String** and **StringBuilder** implement the interface **CharSequence** and use a `char` array to store their characters but, unlike **StringBuilder** objects, **String** objects are immutable.

| **Most important corollary**: | *None* of the methods defined in the class **String** can modify original **String** object’s value. |

| (**other wording**) | If a **String** method returns a modified **String**, this object is new. |

![](images/00012.jpeg)In practice, **String**s can be created in two ways: by forming a string literal (a sequence of characters enclosed by double quotes) or by using the keyword `new`.

![](images/00012.jpeg)In Java, a string literal is itself an object, which gets interned in a common string pool^([141](#part0023_split_009.html_id_260)) (as per JLS, §3.10.5, *String Literals*: "A string literal is a reference to an instance of class **String**. Moreover, a string literal always refers to the same instance of class **String**"). Whenever the code requests creation of a string literal, the pool is scanned and, if a **String** object with the same value already exists in the pool, the reference to this object is returned. **String** objects created using the keyword `new` are never placed in the pool of **String** objects; same goes for the **String**s that are products of methods and, therefore, computed at run time:

![](images/00694.jpeg)

![](images/00012.jpeg)Not only all string literals but the string-valued constant expressions (such as `"Hello " + "world!"`) are interned, too.

| **Corollary**: | **String**s computed by concatenation *at run time* are created anew, hence distinct: |

![](images/00695.jpeg)

![](images/00012.jpeg)EXTRA: String pool is common for all the classes from all the packages that are being used by the running application.

![](images/00012.jpeg)**String** constructors likely to appear on the exam (*italics*: didn’t meet personally):

![](images/00696.jpeg)

| EXTRA: | Although a no-arg constructor **String()** does exist, it isn’t used in practice because **String** objects are immutable in the first place. |

![](images/00012.jpeg)**StringBuilder** constructors likely to appear on the exam (*italics*: didn’t meet):

![](images/00697.jpeg)

![](images/00012.jpeg)**String** and **StringBuilder** methods likely to appear on the exam:

![](images/00698.jpeg)

| *REMARK*: | The table is not exhaustive; it only means that I personally met those methods on the exam. To be on the safe side, learn the following methods, as well: |

![](images/00699.jpeg)

![](images/00012.jpeg)**Known traps on the exam**:

–**str[sb].substring(int start, int end)**^([142](#part0023_split_009.html_id_262)) excludes the character at the `end` position:

![](images/00700.jpeg)

–although **str.replace()**, **str.trim()** and **str.substring()** seem to *modify* the value of a **String**, they actually return a completely new **String** object UNLESS there has been no change:

![](images/00701.jpeg)

–since `==` tests for ‘physical’ equality, the equality of contents should be tested with the method **equals()**;

–whereas **String** and **ArrayList** override **Object**’s **equals()**, **StringBuilder** does not → use a workaround: **sb1.toString().equals(sb2.toString())**;

![](images/00012.jpeg) Easily confused methods (**list** refers to **ArrayList**):

![](images/00702.jpeg)

![](images/00012.jpeg)**Other possible traps**:

–**str.trim()** doesn’t remove whitespace^([143](#part0023_split_009.html_id_264)) inside the string;

–**sb.substring()** returns a newly created **String** without affecting the current **sb** object whereas **sb.append()**, **sb.delete()** and **sb.insert()** do change it;

–**str[sb].substring()** throws SIOOBE if the `end` arg exceeds **str[sb].length()**:

![](images/00703.jpeg)

–chained methods are to be evaluated left to right;

–only two **StringBuilder** methods return a **String**: **substring()** and **toString()**;

–while **substring()** can be invoked in similar ways for both **StringBuilder** and **String** – the method is overloaded for (int start) and (int start, int end) in either class – calls to **replace()** lead to different results: **sb.replace()** substitutes a string between two positions and **str.replace()** substitutes *all* occurrences of a `char` or a **CharSequence**.

![](images/00012.jpeg)EXTRA: **str[sb].indexOf()** returns -1 if no match was found.

![](images/00012.jpeg)EXTRA: **sb.insert()** doesn’t throw a SIOOBE when inserting at the index i = **sb.length()**; the result simply mimics **sb.append()**.

![](images/00012.jpeg)The **+** op is overloaded for **String**, so if either operand of a + expression is a **String**, concatenation is used; otherwise, addition is used.

| **Corollary**: | **+** accepts anything when assigning to a **String**: |

![](images/00704.jpeg)

![](images/00012.jpeg)The principal operations on a **StringBuilder** object are the **append()** and **insert()** methods, which are overloaded so as to accept data of *any* type. Each effectively converts a given datum to a string.

| **Corollaries**: | **append()**ing and **insert()**ing a `null` object won't throw an NPE. |
| EXTRA: | When a `null` object (such as **String**, etc.) is passed in as a parameter to these two methods, it will be converted to the four characters ‘null’. |
| EXTRA: | However, **append(**`null`**)** and **insert(**`null`**)** won’t compile as the reference is ambiguous: `null` can refer to either `char`[] or **CharSequence** |

![](images/00012.jpeg)Useful reminders:

![](images/00059.jpeg)**charAt()**, **indexOf()**, **substring()**, and **length()** work in the same way both in **String** and **StringBuilder**.

![](images/00059.jpeg)**append()** adds only to the end of the current **StringBuilder** object whereas **insert()** allows to put in one or multiple characters at a specified position
→ **sb.insert(sb.length(),"***")** behaves as **sb.append("***")**;

![](images/00059.jpeg)**StringBuilder** uses a char array and throws a SIOOBE rather than AIOOBE.

![](images/00059.jpeg)**StringBuilder** doesn’t have **remove()**; it’s **delete()**.

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 9.1Given:**

![](images/00705.jpeg)

**What is the result?**

A.Hell Hell false false

B.Hell Hell true true

C.Hello Hell false false

D.Hello Hell true true

E.Hello Hell false true

F.Hello Hell true false

**Problem 9.2Given:**

![](images/00706.jpeg)

**What is the result?**

A.same pets, same names

B.different pets, same names

C.same pets, different names

D.different pets, different names

E.Compilation fails

**Problem 9.3Given:**

![](images/00707.jpeg)

**What is the result?**

A.1234Leeloo

B.Compilation fails

C.The code throws a run-time exception

**Problem 9.4Given the following class:**

![](images/00708.jpeg)

**What is the result:**

A._12345 (*where _ denotes an empty space*)

B.12345

C.null 12345

D.Compilation fails

E.A **NullPointerException** is thrown

**Problem 9.5**

Hoping to land a job as a junior programmer at a local bank, you came to a Java interview and were asked to complete the following class that masks 20-digit account numbers so that only the last five digits will be visible to the user while each of the first 15 digits is replaced with an asterisk:

![](images/00709.jpeg)

Specifically, your task is to finish up the method **maskAccount(**String accNum**)** so that the class **AccountMasker** will output ****************67541 when run with the following command:

![](images/00710.jpeg)

**Which two LOCs, when used independently, will achieve this requirement?**

A.`return (new StringBuilder(accNum)).substring(15, 19).toString();`

B.`return lead + accNum.substring(15, 19);`

C.`return new StringBuilder(accNum).append(lead, 15, 19).toString();`

D.`return new StringBuilder(accNum).insert(0, lead).toString();`

E.`return new StringBuilder(lead).append(accNum, 15, 19).toString();`

**Problem 9.6**

**Which statement initializes a StringBuilder to a capacity of 256?**

A.StringBuilder sb = new StringBuilder(new String(256));

B.StringBuilder sb = StringBuilder.setCapacity(256);

C.StringBuilder sb = StringBuilder.setLength(256);

D.StringBuilder sb = new StringBuilder(256);

**Problem 9.7Given the code fragment:**

![](images/00711.jpeg)

**Which two options will output the following:**

`I’ll pass 1Z0-808`

A.System.out.println(sb.append("I’ll pass " + exam + "-" + code));

B.System.out.println(sb.insert("I’ll pass ").append(exam + "-" + code));

C.System.out.println(sb.insert("I’ll pass ").insert(exam).insert("-").insert(code));

D.System.out.println(sb.append("I’ll pass ").append(exam).append("-").append(code));

**Problem 9.8Given:**

![](images/00712.jpeg)

**What is the result?**

A.B A L L

B.B L A

C.B UL L

D.B U A

E.B U A L

**Problem 9.9Given:**

![](images/00713.jpeg)

**What is the result?**

A.There is no output

B.Compilation fails

C.The code throws an **IndexOutOfBoundsException**

D.The code throws a **NullPointException**

**Problem 9.10Given:**

![](images/00714.jpeg)

**Which statement(s) will empty the contents of the bucket object?**

A.bucket.empty();

B.bucket.clear();

C.bucket.delete(0, bucket.size());

D.bucket.delete(0, bucket.length());

E.bucket.deleteAll();

F.bucket.remove(0, bucket.length());

G.bucket.removeAll();

**Problem 9.11Given:**

![](images/00715.jpeg)

**What is the result?**

A.Hi! I’m Javaline

B.Hi! I’m Javalina

C.Hi! I’m Jevaline

D.Hi! I’m Jeveline

**Problem 9.12Given the following main() method:**

![](images/00716.jpeg)

**What is the result?**

A.true true

B.true false

C.false true

D.false false

**Problem 9.13Given:**

![](images/00717.jpeg)

**How many of them print** `Hello Duke`**?**

A.None

B.One

C.Two

D.Three

**Problem 9.14Given the following code fragment:**

![](images/00718.jpeg)

**How many times the code prints** `true`**?**

A.Not a single time

B.Once

C.Twice

D.Three times

**Problem 9.15Given:**

![](images/00719.jpeg)

**What is the result?**

A.a

B.at

C.Compilations fails

D.An exception is thrown at run time

**Problem 9.16Given:**

![](images/00720.jpeg)

**What is the result?**

A.The

B.The Matrix Reloaded

C.Compilation fails

D.An exception is thrown at run time

**Problem 9.17Given the code fragment:**

![](images/00721.jpeg)

**What is the result?**

A.01

B.0 1

C.0 1

D.Compilation fails.

E.An exception is thrown at run time.

**Problem 9.18Given:**

![](images/00722.jpeg)

**What is the result?**

A.Passed

B.Failed

C.Failed Passed

D.Compilation fails

E.An exception is thrown at runtime

**Problem 9.19Given:**

![](images/00723.jpeg)

**What is the result?**

A.Passed: false

B.Passed: true

C.Failed: false

D.Failed: true

E.Compilation fails

F.The code throws IndexOutOfBoundsException

**Problem 9.20Given:**

![](images/00724.jpeg)

**What is the result?**

A.1

B.4

C.16

D.Compilations fails

E.A NullPointerException is thrown at run time

**Problem 9.21Given:**

![](images/00725.jpeg)

**What is the result?**

A.8

B.16

C.24

D.Compilations fails

E.A NullPointerException is thrown at run time

**Problem 9.22Given:**

![](images/00726.jpeg)

**How many LOCs, when inserted independently at line XXX, will make the code print** `Strings Forever!`**?**

A.None

B.One

C.Two

D.Three

**Problem 9.23Given:**

![](images/00727.jpeg)

**What is the result?**

A.1

B.No visible output at all

C.Code compiles but enters endless loop at run time

D.Compilation fails because of an unreachable statement

E.Compilation fails because str+1 attempts to create a new object but str is final

F.Compilation fails because the expression str+1 is illegal

**Problem 9.24Given:**

![](images/00728.jpeg)

**How many LOCs fail compilation?**

A.Two

B.Three

C.Four

D.Five

**Problem 9.25Given:**

![](images/00729.jpeg)

**Is it true that the code prints** `String Quartet No. 19 in C Major, K. 465`**?**

A.true

B.false

![](images/00061.jpeg) **CORE RULES (with some Extras):**

9.3Create and manipulate calendar data using classes from **java.time.LocalDateTime**, **java.time.LocalDate**, **java.time.LocalTime**, **java.time.format.DateTimeFormatter**, **java.time.Period**

![](images/00012.jpeg)*All* of the LDT-related classes are immutable.

![](images/00012.jpeg)*None* of the LDT-related classes (incl. DTF and **Period**) have `public` constructors.

| **Corollary**: | All three primary classes are instantiated with **now()** or **of()**, e.g.: |

![](images/00730.jpeg)

| **NB**: | Months can be specified in two ways (see above). Months start with 1 rather than zero (January is 01). |
| EXTRA: | The overloaded **of()** that accepts months as words rather than numbers, uses the enum **Month** defined in **java.time** together with most of the other LDT-related classes. |
| EXTRA: | The class **DateTimeFormatter** is defined in **java.time.format**. |

![](images/00012.jpeg)**LocalDate** doesn’t contain time-related fields whereas **LocalTime** doesn’t contain date-related fields.

| **Known trap on the exam**: | A missing or unexpected field → comperr or RTE |

![](images/00731.jpeg)

![](images/00012.jpeg)The methods likely to appear on the exam:

![](images/00732.jpeg)

| **Known trap on the exam**: | Since the classes are immutable, adding or subtracting time units becomes meaningless unless the code uses the values returned by these methods (similarly to the methods invoked on **String** objects). |

![](images/00733.jpeg)

![](images/00012.jpeg)**plusXXX()** or **minusXXX()** methods are used to manipulate date and time values. EXTRA: Method chaining for **minusXXX()** and **plusXXX()** works properly:

![](images/00734.jpeg)

![](images/00012.jpeg)**parse(CharSequence)** and **parse(CharSequence, DataFormatter)** methods are used to obtain a date & time object from a text string.

| **Known trap on the exam**: | **parse()** needs appropriate number of components in the text string (both date & time for **LocalDateTime**, time only for **LocalTime**, date only for **LocalDate**), otherwise a **DateTimeParseException** is thrown: |

![](images/00735.jpeg)

| **NB**: | Days, months, hours and minutes should be specified with *TWO* digits, otherwise a **DateTimeParseException** is thrown; this rule isn’t applicable to the method **of()**. |

![](images/00736.jpeg)

![](images/00012.jpeg)The class **Period** represents a number of days, months, weeks, or years, which can be added to or subtracted from a **LocalDate** or a **LocalDateTime** object:

![](images/00737.jpeg)

![](images/00012.jpeg)EXTRA: Chaining for **Period**’s **ofXXX()** methods doesn’t work properly^([144](#part0023_split_009.html_id_268)):

![](images/00738.jpeg)

→ instead of **Period.ofDays(**1**)**.**ofMonths(**2**).ofYears(**3**)** use **Period.of(**3, 2, 1**)**:

![](images/00739.jpeg)

![](images/00012.jpeg)EXTRA: **Period.parse(**"P1Y2M3D"**)** is the same as **Period.of(**1, 2, 3**)**.

![](images/00012.jpeg)**DateTimeFormatter** is used to output dates and times in the desired format.

| **Potential trap**: | All DTF formatters that are likely to appear on the exam, start with ISO, e. g.: ISO_DATE, ISO_TIME, ISO_LOCAL_DATE, ISO_LOCAL_DATE_TIME, and so on → any other form^([145](#part0023_split_009.html_id_266)) leads to a comperr: |

![](images/00740.jpeg)

| EXTRA: | Difference between ISO_**** and ISO_LOCAL_****** is the offset (e.g., ISO_DATE can output either ‘2011-12-03’ or ‘2011-12-03+01:00’ if the offset is available while ISO_LOCAL_DATE outputs only ‘2011-12-03’). |

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 9.26Given the following code fragment:**

![](images/00741.jpeg)

**What is the result?**

A.2016-06-14

B.2016-06-13

C.Compilation fails

D.An exception is thrown at run time

**Problem 9.27Given:**

![](images/00742.jpeg)

**What is the result?**

A.2016-07-13

B.2016-07-14

C.2016-07-15

D.Compilation fails

E.An exception is thrown at run time

**Problem 9.28Given:**

![](images/00743.jpeg)

**What is the result?**

A.December 13, 2016

B.June 13, 2015

C.2016-12-13

D.2016-06-13

**Problem 9.29**

**Which two LOCs fail compilation?**

A.LocalDateTime.of(2016,6,13);

B.LocalDate.of(2016, Month.JUNE, 50);

C.LocalDateTime.of(2016,06,13,14,15);

D.LocalDate ld = new LocalDate(2016,6,13);

E.LocalTime.now().format(DateTimeFormatter.ISO_DATE);

**Problem 9.30Given:**

![](images/00744.jpeg)

**What is the result if the system date is June 13, 2016?**

A.2016-06-13
2016-06-13
2016-06-13

B.Compilation fails.

C.A DateParseException is thrown at runtime.

**Problem 9.31Given the full contents of the file** `JavaBirthday.java`**:**

![](images/00745.jpeg)

**One of the LOCs fails compilation. Which two modifications, used independently, will make the code print** `Java was born on May 23, 1995`**?**

A.Replace line 2 with import java.time.*;

B.Replace line 3 with import java.time.format.*;

C.Replace Month.MAY on line 7 with Month.May

D.Replace Month.MAY on line 7 with 05

![](images/00061.jpeg) **CORE RULES (with some Extras):**

9.4Declare and use an **ArrayList** of a given type:

![](images/00012.jpeg)**ArrayList** implements **List**, which extends **Collection** and **Iterable** → that’s why:

![](images/00059.jpeg)**ArrayList** works with reference types only:

–can accept a mixture of types when used without generics;

–primitives get autoboxed and unboxed as needed;

| **Corollary**: | `for-each` with a primitive loop var throws an NPE at `null` element. |

![](images/00059.jpeg)is structurally mutable and resembles a resizable array:

–**ArrayList**s are zero-based like ordinary arrays;

–unlike arrays, initial size of an **ArrayList** cannot be specified;

–internally, the elements are stored in an **Object[]** array → throws AIOOBE

![](images/00059.jpeg)is ordered and iterable:

–allows positional (indexed) access to the elements;

–enhanced `for` loop returns the elements in the order they were added;
EXTRA: `for-each` cannot remove elements; use **Iterator** or **ListIterator**;

![](images/00059.jpeg)allows duplicates;

![](images/00059.jpeg)allows `nulls`;

![](images/00059.jpeg)can be made type-safe by using generics, for example, if **Vehicle** ← **SUV**:

![](images/00746.jpeg)

| **NB:** | Empty diamond on the left is not allowed. |
| **NB:** | **contains()** is comperr-proof even if the **List** is generified: |

![](images/00747.jpeg)

![](images/00012.jpeg)**ArrayList** constructor likely to appear on the exam:

![](images/00748.jpeg)

![](images/00012.jpeg)Methods likely to appear on the exam:

![](images/00749.jpeg)

**Possible trap on the exam:**

Easily confused methods

![](images/00750.jpeg)

![](images/00012.jpeg)One more way to create a **List** is with the method **Arrays.asList()**:

![](images/00751.jpeg)

**Remarks:**

1.The reftype *must* be **List** rather than **ArrayList**.

2.Unlike the lists created with a constructor defined in a **List**-implementing class, this particular list is structurally immutable (i.e., it cannot change its size^([146](#part0023_split_009.html_id_272))).

3.I met this idiom on both sittings but only in the question that was related to lambdas so the first two points are probably not terribly important for our exam…

![](images/00012.jpeg)EXTRA: **List** and **ArrayList** don’t have a simple **sort()** method; their **sort()** needs a comparator → to sort an **ArrayList**, use **java.util.Collections.sort(al)**^([147](#part0023_split_009.html_id_270)):

![](images/00752.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 9.32Given the following class definition:**

![](images/00753.jpeg)

**What is the result?**

A.[Ruby, Perl, Closure, Emacs Lisp]

B.[Ruby, Closure, Emacs Lisp, Emacs Lisp]

C.[Ruby, Closure, Emacs Lisp]

D.Compilation fails

**Problem 9.33Given:**

![](images/00754.jpeg)

**Which two expressions evaluate to 3?**

A.someTypes.size();

B.someTypes.capacity();

C.someTypes.length();

D.someTypes. get(2).size;

E.someTypes. get(2).length;

F.someTypes. get(2).length();

**Problem 9.34Given the following code fragment:**

![](images/00755.jpeg)

**What is the result?**

A.1

B.Compilation fails on line a1

C.Compilation fails on line a2

D.Compilation fails on line a3

E.An IndexOutOfBoundsException is thrown at run time

**Problem 9.35Given:**

![](images/00756.jpeg)

**What is the result?**

A.true

B.4

C.[0, 1, 2, 3, 4]

D.Compilation fails

**Problem 9.36Given:**

![](images/00757.jpeg)

**What is the result?**

A.[OK, OK]

B.[OK, ]

C.Compilations fails

D.A RuntimeException is thrown

**Problem 9.37Given:**

![](images/00758.jpeg)

**What is the result?**

A.[jay, finch, titmouse, kinglet]

B.[jay, finch, titmouse, true]

C.Compilation fails on line b1

D.Compilation fails on line b2

**Problem 9.38Given:**

![](images/00759.jpeg)

**What is the result?**

A.16null16

B.16null16null

C.16null16 and a NullPointerException

D.Compilation fails

![](images/00061.jpeg) **CORE RULES (with some Extras):**

9.5Write a simple lambda expression that consumes a lambda **Predicate** expression:

![](images/00012.jpeg)The abstract method **test()** declared in the interface **Predicate** returns a `boolean` and takes an argument of type **Object**.

![](images/00012.jpeg)Since there’s only one formal parameter (which corresponds to **test()**’s arg), its type and enclosing parentheses are optional.

![](images/00012.jpeg)If the method body contains a single `boolean`-returning stat, the braces can be omitted UNLESS the stat uses an explicit `return` – in which case we must apply the Semirebra ^([148](#part0023_split_009.html_id_274)) Rule.

![](images/00012.jpeg)**The Semirebra Rule:**

Semicolon, return and braces in lambda method body always go together.

| **Traps!** | –empty parameter list, or – `return` without semicolon and braces, or
– semicolon without `return` and braces, or
– the method body does not return a `boolean`. |

*Typical invalid patterns likely to appear on the exam:*

![](images/00760.jpeg)

![](images/00012.jpeg)What **Predicate** is typed to must be consistent with the parameter’s type.

Consider the following:

![](images/00761.jpeg)

The above example fails to compile because **p** isn’t generified → its type is therefore **Object** → and **Object** doesn’t have the method **isEmpty()**. On the other hand, the code would have compiled if **al.isEmpty()** were replaced, say, with **al.equals("")**. Better yet, cast the formal param to **List** or **ArrayList** (e.g., ((List)al).isEmpty()) as this wouldn’t break the logic behind the code, which happens with **equals("")**.

Let’s have another example that doesn’t compile:

![](images/00762.jpeg)

Here, **Predicate** is typed to **ArrayList** while the object it must work with is of type **List**. In other words, the method **test()** was promised that its argument is going to have everything that is typical for an **ArrayList**; instead, **test()** gets just a **List**, which is not sufficient.

Alright, let’s flip the types in the **check()** method’s signature:

![](images/00763.jpeg)

Did it help? Nope, the comperr just moved to the printing stat’s line: although **test()** is perfectly happy now because it expected a toy of type **List** while what it’s gonna get will be even more sophisticated and amusing, the actual call to **check()** provides the same unrefined, boring **List**. If the available options prevent us from touching the **check()** method’s signature, we could change **list**’s reftype:

![](images/00764.jpeg)

Another way to deal with this problem involves casting **list** to **ArrayList**:

![](images/00765.jpeg)

After all, the actual type of the object at run time is **ArrayList**, so this quick’n’dirty hack will even work…

![](images/00012.jpeg)EXTRA: Watch out for already declared vars in lambdas: while the parameter list does declare new vars to be used in the body part of the lambda expression, these variables won’t get new scope and, therefore, cannot shadow the previously declared vars:

![](images/00766.jpeg)

![](images/00069.jpeg) **EXERCISES (for Key Summary ref.to App.D):**

**Problem 9.39Given the following class definitions:**

![](images/00767.jpeg)

**Which LOC, when inserted at line r1, enables the code to print** `Passed: Alice, Doug,`**?**

A.checkScore(list, () -> e. getScore() > 65);

B.checkScore(list, Examinee e -> e. getScore() > 65);

C.checkScore(list, e -> e. getScore() > 65);

D.checkScore(list, (Examinee e) -> { e.getScore() > 65; });

**Problem 9.40**

**Let ^(sb) refer to a StringBuilder object. Which of the following fail(s) compilation?**

A.sb -> sb.toString()

B.StringBuilder sb -> sb.toString()

C.(StringBuilder sb) -> return sb.length();

D.(StringBuilder sb) -> { return sb.length(); }

**Problem 9.41Given:**

![](images/00768.jpeg)

**Which two options can make the code compile and run successfully?**

A.Replace line t3 with `check(list, myList -> list.isEmpty()));`

B.Replace line t2 with `List list = new ArrayList();` and replace line t3 with `check(list, myList -> myList.isEmpty()));`

C.Replace line t1 with `String check(List list, Predicate<ArrayList> p){` and line t3 with `check(list, myList -> myList.isEmpty()));`

D.Replace line t1 with `String check(ArrayList list, Predicate<ArrayList> p){` line t2 with `List mist = new ArrayList();` and line t3 with `check(mist, list -> list.isEmpty()));`

E.Replace line t1 with `String check(List list, Predicate<List> p){` and line t3 with `check(list, myList -> myList.isEmpty()));`

**Problem 9.42Given:**

![](images/00769.jpeg)

**Which modification will achieve the same result?**

A.Overload the method **interrogate()** with the following code fragment:

![](images/00770.jpeg)

and replace the call to **Interrogate** with the following LOC:

![](images/00771.jpeg)

B.Overload the method **interrogate()** with the following code fragment:

![](images/00772.jpeg)

and replace the call to **interrogate()** with the following LOC:

![](images/00773.jpeg)

C.Add the following interface:

![](images/00774.jpeg)

D.Add the following interface:

![](images/00775.jpeg)

**Problem 9.43**

**Which one is true?**

A.Functional interface may not contain more than one method.

B.Any interface that has a single abstract method is therefore functional.

C.Functional interface cannot have superinterfaces.

D.Functional interface cannot be extended.

E.None of the above.

![](images/00069.jpeg) **Keys & Discussion:**

**Problem 9.1 – D**

**Given:**

![](images/00776.jpeg)

**What is the result?**

A.Hell Hell false false

B.Hell Hell true true

C.Hello Hell false false

D.Hello Hell true true

E.Hello Hell false true

F.Hello Hell true false

The first thing coming to your mind whenever you see a **String** object on the exam should be something like "Ah! This animal is immutable, so I’d better be careful…" Naturally, there are also some quirky methods to watch out for but, basically, this is it.

Now please list the immutable classes that are on our exam; we mentioned them when discussing the solution to [Problem 4.3](#part0018_split_001.html_id_335)… Did you get them all^([149](#part0023_split_009.html_id_276))? Good.

Back to **String**. Since **str** is immutable, line h1 doesn’t change the original object; instead, a new object is created – and wasted because the reference to it isn’t used in any way, so line h2 prints the same old ‘Hello’. With a trailing space, of course. On the other hand, line h3 outputs ‘Hell ’ because the printing stat acts on the object that was returned by **replace()**.

As for line h4, **StringBuilder** doesn’t override **Object**’s **equals()** → hence the method simply compares two identical references and returns `true`. We should always keep in mind that methods act on objects *through a reference*, so that’s why when the second **append()** completes its job, both operands will contain the same sequence of characters, namely ‘Hello?!’. Let’s have a simple illustration of this principle, this time with a class that does override **equals()**:

![](images/00777.jpeg)

![](images/00778.jpeg)

In the above example, the object is always the same, and any change made to it through a reference gets reflected on both sides of **equals()**.

Next step (we are getting back to the current [Problem 9.1](#part0023_split_008.html_id_336), by the way); what happens when we have a mirror situation: the class **String** that, unlike **StringBuilder**, is not only immutable but also overrides **equals()**? Line h5 answers that by printing `true`, but why? Specifically, is it because **String** is immutable or for some other reason?

Alright, the first operand, namely **str.replace(**"o",""**)**, creates an identical twin to **str**, changes its contents, delivers this freshly baked object to **equals()**, who grabs it, peeks inside and sees… hmm… it sees Hell.

The second operand in its own turn takes the reference to the original and immutable **str**, which still reads "Hello", does its thing and returns another new object that again contains "Hell". So on both palms of **equals()** lie pointers to two different objects, which just happen to be made of the same hellish stuff. Compare it to the situation with the mutable **StringBuilder** where **append()** each time acts on and returns reference to the same object…

And what about an immutable object in a class that does not overrides **equals()**? Here we go:

![](images/00779.jpeg)

Our brave general became unsinkable although unpromotable!

**Problem 9.2 – D**

**Given:**

![](images/00780.jpeg)

**What is the result?**

A.same pets, same names

B.different pets, same names

C.same pets, different names

D.different pets, different names

E.Compilation fails

Since **StringBuilder** doesn’t override **equals()**, **checkNames()** is virtually identical to **checkPets()**: it simply compares references.

**Problem 9.3 – A**

**Given:**

![](images/00781.jpeg)

**What is the result?**

A.1234Leeloo

B.Compilation fails

C.The code throws a run-time exception

**StringBuilder** does have a constructor that accepts a **String**, and its **append()** is overloaded for all imaginable types.

Now, unlike the class **String**, **StringBuilder**’s **replace()** isn’t overloaded: its only version takes three args, namely (int start, int end, String replacementString). In short, the code is perfectly valid.

As with all the other methods in **String** and **StringBuilder** that accept two indices to limit a specific part of the character sequence (such as **str.substring(**int beginIndex, int endIndex**)**, **sb.append(**CharSequence s, int start, int end**)**, etc.), the first index is inclusive while the second one is exclusive → the substring on line t1 starts with the 5th element and ends with the element number 4\. Looks mighty suspicious.

The code, however, doesn’t throw a **RuntimeException** (a SIOOBE, to be exact) because – according to the **StringBuilder** API docs – the exception is generated "if `start` is negative, greater than **length()**, or greater than `end`".

And what **replace()** does, then? It

…replaces the characters in a substring of this sequence with characters in the specified String. The substring begins at the specified start and extends to the character at index end - 1 or to the end of the sequence if no such character exists. First the characters in the substring are removed and then the specified String is inserted at start. (This sequence will be lengthened to accommodate the specified String if necessary.)^([150](#part0023_split_009.html_id_278))

**Problem 9.4 – C**

**Given the following class:**

![](images/00782.jpeg)

**What is the result:**

A._12345 (*where _ denotes an empty space*)

B.12345

C.null 12345

D.Compilation fails

E.A **NullPointerException** is thrown

**String** is a reference type and, as such, can be `null`, so the assop on line t1 is valid.

What about the next LOC? Let’s run the entire logical chain:

| Step 1. | `str += e` actually means `str = str + e`; |
| Step 2. | JLS, §15.18, *Additive Operators*: "If the type of either operand of a + operator is **String**, then the operation is string concatenation". |
| Step 3. | JLS, §5.1.11, *String Conversion*: "If the reference is `null`, it is converted to the string "null" (four ASCII characters n, u, l, l)". |

→ so there’s neither a comperr nor RTE → this is why the first iteration results in ‘null1’ – and everything after that is trivial.

**Problem 9.5 – BE**

Hoping to land a job as a junior programmer at a local bank, you came to a Java interview and were asked to complete the following class that masks 20-digit account numbers so that only the last five digits will be visible to the user while each of the first 15 digits is replaced with an asterisk:

![](images/00783.jpeg)

Specifically, your task is to finish up the method **maskAccount(**String accNum**)** so that the class **AccountMasker** will output ****************67541 when run with the following command:

![](images/00784.jpeg)

**Which two LOCs, when used independently, will achieve this requirement?**

A.`return (new StringBuilder(accNum)).substring(15, 19).toString();`

B.`return lead + accNum.substring(15, 19);`

C.`return new StringBuilder(accNum).append(lead, 15, 19).toString();`

D.`return new StringBuilder(accNum).insert(0, lead).toString();`

E.`return new StringBuilder(lead).append(accNum, 15, 19).toString();`

As usual, we start our analysis by looking at the available options: what if some of them can be eliminated right away? It happens a lot on the exam, and this time is not an exception.

The output must contains asterisks (disguised as the var **lead**) → option A doesn’t even mention that var → A is immediately out.

What about B? **substring()** works in the same way for both **String** and **StringBuilder**: it returns a **String** and is overloaded for (int start) and (int start, int end) → we have the second version, which returns whatever sits between index 15 inclusive and index 20 exclusive → what does this method receive? → it receives the object returned by **replace(**" ", ""**)** → to wit, a 20-digit sequence now void of spaces because **String**’s **replace()** acts on ***each*** occurrence of the target `char` or **CharSequence** → substring contains 67541 → it gets prepended with **lead** → bingo.

Now to option C. **maskAccount()**’s arg, represented by the local var **accNum**, contains 20 digits without spaces → a new **StringBuilder** object gets created → it contains **accNum** → then **append()** attempts to add to it five characters taken from **lead** → but in doing so it goes too far, beyond the last available value since **lead** contains only 15 characters → an IOOBE.

Option D: **insert()** places **lead** at the first position in the **StringBuilder** object thus shifting to the right entire bunch of whatever the object used to contain, namely a 20-digit string → the result is way too long.

And since what’s left is just option E, we accept it without even analyzing its logic → but at the Review stage we must do it → **append()** adds to **lead** a five-digit string extracted from **accNum**’s tail → then converts the whole works to **String** and returns it → yeap, looks fine.

**Problem 9.6 – D**

**Which statement initializes a StringBuilder to a capacity of 256?**

A.StringBuilder sb = new StringBuilder(new String(256));

B.StringBuilder sb = StringBuilder.setCapacity(256);

C.StringBuilder sb = StringBuilder.setLength(256);

D.StringBuilder sb = new StringBuilder(256);

Since the answer to the problem is obvious, we can afford to spend a minute to take a look at the bigger picture.

Only two classes on our exam have something that relates – either directly or indirectly – to this particular creature called **capacity**, namely **StringBuilder** and **ArrayList**:

![](images/00785.jpeg)

Although it may sound so, capacity is not an upper limit of how much we can put into the **StringBuilder** or **ArrayList**; it’s a value defining a boundary beyond which the internal array must be reallocated to accommodate the necessary number of elements (in case of **ArrayList**) or the **CharSequence**’s length (in case of **StringBuilder**). Whereas **StringBuilder** lets both get and set its capacity, **ArrayList** does not provide a direct read access.

Back to our problem; option A doesn’t compile because **String** defines no constructor that would take an `int` as its only arg; now please list the **String** constructors that are likely to appear on the exam^([151](#part0023_split_009.html_id_280)).

As for options B and C, they are just plain wrong. First of all, **StringBuilder** doesn’t have static methods so the name of the class cannot be used in any invocation. Secondly, **setCapacity()** doesn’t even exist in **StringBuilder**; lastly, either method would have to return a **StringBuilder** object, and setters in a mutable class are usually `void` – just as **setLength()** is…

**Problem 9.7 – AD**

**Given the code fragment:**

![](images/00786.jpeg)

**Which two options will output the following:**

`I’ll pass 1Z0-808`

A.System.out.println(sb.append("I’ll pass " + exam + "-" + code));

B.System.out.println(sb.insert("I’ll pass ").append(exam + "-" + code));

C.System.out.println(sb.insert("I’ll pass ").insert(exam).insert("-").insert(code));

D.System.out.println(sb.append("I’ll pass ").append(exam).append("-").append(code));

Of all the core Java classes we are supposed to learn for the exam only **StringBuilder** defines **insert()** – which is indeed our case. However, this **insert()** in all its overloaded versions requires at least two args (we need to specify *what* is to be inserted and *where*) → options B and C are immediately eliminated.

**Problem 9.8 – C**

**Given:**

![](images/00787.jpeg)

**What is the result?**

A.B A L L

B.B L A

C.B UL L

D.B U A

E.B U A L

We are dealing with **String**, which is immutable → the LOC on line XXX is immaterial as it doesn’t assign the newly created object back to the var **a**. What is left for us is imitate the work of lines X, XX and XXXX on paper → line X results in B U → then line XX appends ‘L’ to what **a** holds → and line XXX does the same.

**Problem 9.9 – C**

**Given:**

![](images/00788.jpeg)

**What is the result?**

A.There is no output

B.Compilation fails

C.The code throws an IndexOutOfBoundsException

D.The code throws a NullPointException

**String**’s **charAt()** takes an `int`, and Java treats `char` as an integral type representing values from 0 to 65535 inclusive → there is no comperr.

As for what happens at run time, since ‘Hello’ contains only five characters, the code attempts to access something that doesn’t exist → IOOBE (or, to be more precise, a SIOOBE).

**Problem 9.10 – D**

**Given:**

![](images/00789.jpeg)

**Which statement(s) will empty the contents of the** `bucket` **object?**

A.bucket.empty();

B.bucket.clear();

C.bucket.delete(0, bucket.size());

D.bucket.delete(0, bucket.length());

E.bucket.deleteAll();

F.bucket.remove(0, bucket.length());

G.bucket.removeAll();

This problem is obviously about one of the easily confused methods. Consult this tableamong the rules that relate to Exam Objectives 9.1 & 9.2 to refresh your memory, when in doubt.

Neither **String** nor **StringBuilder** nor **ArrayList** has an **empty()** method. The method **clear()** belongs to **ArrayList**, and same goes for **remove()** and **removeAll()** → we are left to choose among the three versions of **delete()**.

**deleteAll()** is there to confuse you; there’s no such method, it simply bears a resemblance to **ArrayList**’s **removeAll()**.

Finally, as **size()** is defined in **ArrayList** while **StringBuilder** – together with **String** – uses **length()**, we arrive at the correct conclusion that the answer to our [Problem 9.10](#part0023_split_008.html_id_337) is option D.

**Problem 9.11 – B**

**Given:**

![](images/00790.jpeg)

**What is the result?**

A.Hi! I’m Javaline

B.Hi! I’m Javalina

C.Hi! I’m Jevaline

D.Hi! I’m Jeveline

The method **replace()** is defined in both **String** (where it is overloaded and takes *two* args – target followed by replacement – in both cases) and **StringBuilder** (where it is not overloaded and accepts *three* args). One of the most remarkable features of **replace()** in **String** is that it substitutes *each* occurrence of the target → every ‘e’ in Javeline gets replaced with an ‘a’.

**Problem 9.12 – D**

**Given the following main() method:**

![](images/00791.jpeg)

**What is the result?**

A.true true

B.true false

C.false true

D.false false

The **String**s created with double quotes are placed into a common string pool; everything else – such as **String**s instantiated with the `new` keyword or computed at run time – isn’t…

The above sentence is just a reminder; it’s not directly relevant to our Problem because **str.trim()** returns a completely new object (but only if there were changes, that is), which in our case doesn’t get used at all → **str** still points to the same object.

Now, it is immaterial whether or not the **String**s " " and "" live in a common pool: they are definitely distinct → and since **equals()** is overridden in **String**s, it compares different contents.

**Problem 9.13 – B**

**Given:**

![](images/00792.jpeg)

**How many of them print** `Hello Duke`**?**

A.None

B.One

C.Two

D.Three

The first printing stat appears quite natural. As for **append()**, it works with the tail only, so even its args look suspicious.

**add()** gets used so often that by now we should remember that it is a dweller of the **ArrayList** realm.

The method **set()** is a rarer bird but its logic dictates that it would simply replace the very first element with Hello – and the very first element in our **StringBuilder** is just ‘D’. Still, it would have worked if only it were invoked on a proper object because **set()** also belongs to **ArrayList**…

**Problem 9.14 – C**

**Given the following code fragment:**

![](images/00793.jpeg)

**How many times the code prints** `true`**?**

A.Not a single time

B.Once

C.Twice

D.Three times

Alright, as we start reading the code, here comes immediate realization that both objects are immutable and that **str1** is a member of a common string pool whereas **str2** isn’t. But is it important? We don’t know yet; need to analyze further.

Next step: **str2.toLowerCase()** on line 1 returns ‘null’ and **equalsIgnoreCase()** compares it with **str1**’s ‘null’.

Line 2 uses `==`, which compares references only → **str2.replace(**'L', 'l'**)** returns a completely new object on which **toLowerCase()** is then invoked resulting in yet another object. All in all, on both sides of `==` sit different objects so it’s no wonder that line 2 outputs `false`.

Line 3 resembles line 2 so damn much that it’s tempting to assume both LOCs lead to identical results, which would be a disaster. As **str1** is made up of letters in lowercase from the very beginning, **replace()** – finding not a single match – returns reference to the same object. Then **toLowerCase()** follows its steps → in the end, on either palm of == sits the same object.

When reviewing you answers, pay close attention so something like option A, which might mean that the code doesn’t compile. In our case, the only point of concern is probably the invocation of **replace()** that uses `char`s as the method’s args.

You’ll do mighty well remembering that **String** overloads **replace()** and that this method indeed can take `char`s as its args. The overloaded version accepts **CharSequence**… What about **StringBuilder**? and **ArrayList**?^([152](#part0023_split_009.html_id_282))

**Problem 9.15 – D**

**Given:**

![](images/00794.jpeg)

**What is the result?**

A.a

B.at

C.Compilations fails

D.An exception is thrown at run time

A **String**? and the reference to it doesn’t get reassigned? → same object all along.

And whoever wrote that **substring()** invocation was obviously half asleep for the method wants to grab the 6th character while **movie** still has only three.

**Problem 9.16 – C**

**Given:**

![](images/00795.jpeg)

**What is the result?**

A.The

B.The Matrix Reloaded

C.Compilation fails

D.An exception is thrown at run time

Many people prefer to read code starting from the **main()** method and then just following the program’s business logic. The questions on our exam aren’t long (with a possible exception of lambda-related problems – soon you’ll see what I mean) so it is also possible to start on the top and then work your way to the bottom. Either way, you should notice that the invocation of **insert()** is wrong: its args switched places.

Otherwise the answer would have been option B because **StringBuilder** is mutable, and we do remember that Java is pass-by-value.

**Problem 9.17 – E**

**Given the code fragment:**

![](images/00796.jpeg)

**What is the result?**

A.01

B.0 1

C.0 1

D.Compilation fails

E.An exception is thrown at run time

**str** is an array, and arrays, when allocated, always get inited with default values in their slots. In our case, the slots are of type **String**, which is a reference type, hence the default value is `null`.

Invoking a method on a `null` object is one of the most typical NPE-throwing scenarios on the exam.

**Problem 9.18 – B**

**Given:**

![](images/00797.jpeg)

**What is the result?**

A.Passed

B.Failed

C.Failed Passed

D.Compilation fails

E.An exception is thrown at runtime

The var **str** declared in the method **main()** is local and, therefore, shadows the instance var **str** on line e1, which is a good thing because **pass()** is `static` → the code doesn’t throw a comperr.

The method **concat()** is invoked correctly: it is overloaded for any data type so accepting a **String** isn’t a problem, and the object itself isn’t `null`.

If the class **String** were mutable, the method **pass()** would have returned ‘Failed Passed’ – but it isn’t, so **str.concat()** dutifully creates a new object, which is then simply wasted.

**Problem 9.19 – B**

**Given:**

![](images/00798.jpeg)

**What is the result?**

A.Passed: false

B.Passed: true

C.Failed: false

D.Failed: true

E.Compilation fails

F.The code throws IndexOutOfBoundsException

**StringBuilder**’s **replace()** is not overloaded, takes three args (int start, int end, String str) and returns the reference to the current object, so the left-hand side of `==` is valid → the object contains now ‘Failed’.

Now to the right-hand side: **StringBuilder**’s **delete()** isn’t overloaded, either, and takes two args, namely (int start, int end). A question arises: is it OK if the `end` index is way beyond the object’s boundary? won’t the code throw an IOOBE?

No, says the API documentation: "[the method] throws **StringIndexOutOfBoundsException** if `start` is negative, greater than **length()**, or greater than `end`" → the method successfully deletes the entire string → and then **insert()** – which is overloaded, by the way – slips in ‘Failed’ at the first position.

Whatever the object contains is, however, immaterial as `==` compares references and we are dealing here with a mutable data type → the last printing stat outputs true.

**Problem 9.20 – B**

**Given:**

![](images/00799.jpeg)

**What is the result?**

A.1

B.4

C.16

D.Compilations fails

E.A NullPointerException is thrown at run time

Line c1 creates a **StringBuilder** object with no characters in it and an initial capacity of 16\. As for the method **append()**, it is overloaded for all imaginable types → its operation is therefore successful.

But what exactly does it append? The mike goes to the API documentation:

**append(**Object obj**)** appends the string representation of the Object argument.

Next question: how this ‘string representation’ thingy is obtained? In a traditional way, that is, by calling **toString()** on **obj**? If so, this will surely throw an NPE… Option E, then?

Not at all; let’s listen further to the API docs for **StringBuilder**’s **append(**Object obj**)**:

The overall effect is exactly as if the argument were converted to a string by the method **String.valueOf(**Object**)**, and the characters of that string were then appended to this character sequence.

And **String.valueOf(**Object**)** pipes in with this:

If the argument is `null`, then a string equal to "null"; otherwise, the value of **obj.toString()** is returned.

In short, our **StringBuilder** contains now the string ‘null’ – which is four characters long.

**Problem 9.21 – C**

**Given:**

![](images/00800.jpeg)

**What is the result?**

A.8

B.16

C.24

D.Compilations fails

E.A NullPointerException is thrown at run time

Every LOC is valid so there’s no comperr:

–**str** is a refvar and can be assigned `null`;

–`str += str` means `str = str + str`, and the + op is overloaded for **String** resulting in ‘nullnull’;

–**StringBuilder** indeed have an overloaded constructor that accepts a **String**;

–**delete()** is invoked correctly → no RTE, and

–**StringBuilder** class does define an instance field named **capacity**.

Now we only have to choose among options A, B and C. The **StringBuilder** API documentation defines capacity in this way: "The capacity is the amount of storage available for newly inserted characters, beyond which an allocation will occur". As for length, it’s a character count.

Unfortunately, this information is not enough to arrive at the correct answer; we really need to look at the definition of the **StringBuilder** constructor that accepts a **String**:

Constructs a string builder initialized to the contents of the specified string. The initial capacity of the string builder is 16 plus the length of the string argument.

QED.

**Problem 9.22 – A**

**Given:**

![](images/00801.jpeg)

**How many LOCs, when inserted independently at line XXX, will make the code print** `Strings Forever!`**?**

A.None

B.One

C.Two

D.Three

First and foremost – please do pay attention, this one is important – **String** has neither **delete()** nor **insert()**; they belong to **StringBuilder**. The only methods that *appear* to change a **String** structurally are **concat()**, **replace()** and **trim()** → the first two LOCs are definitely out.

LOC number three, while valid, isn’t what we need: it does remove the string " Bean" but the computed result gets wasted because the hasty slogan writer forgot to assign it back to **str**.

Now, I don’t know about you, but in my eyes the last line of code looks entirely logical: it first constructs an SB by passing a **String** object to the correctly chosen constructor, them **remove()** gets rid of an extra " Bean" after which **toString()** converts the result to a **String** and assigns it to **str** which then gets printed → this one should apparently work… only it doesn’t because **StringBuilder** has no **remove()** → the last LOC is invalid.

Rather confusing, if you ask me. So, when preparing for the exam, I tried to come up with a single logical rule:

No **delete()** or **insert()** in **String** → they are defined in **StringBuilder** only → **remove()** would be totally redundant in SB because the class already has **delete()** that takes care of the task.

Or on a lighter note,

*Rules for **String** are mean ’n tough,
Learn by heart this bloody stuff:
No **delete()** and no **insert()** –
That’s the way to Java cert.
**add()** to **List** to feel no pain,
Use **remove()** – or **clear()** its brain.
And remember that **replace()** Can explode right in your face:
While in **String** it overloads,
**SB** follows other roads*.

HTH.

**Problem 9.23 – C**

**Given:**

![](images/00802.jpeg)

**What is the result?**

A.1

B.No visible output at all

C.Code compiles but enters endless loop at run time

D.Compilation fails because of an unreachable statement

E.Compilation fails because str+1 creates a new object but str is final

F.Compilation fails because the expression str+1 is illegal

Although it is a fact that something like `while(true)` may lead to a comperr if the loop is followed by other statements, which become therefore unreachable, it doesn’t happen in our case because the evaluation of **equals()** happens at run time.

The expression `str+1` is also valid since the + op is overloaded for **String**; it simply appends 1 to the already existing string at each iteration, creating another **String** object – every time anew:

![](images/00803.jpeg)

As for the `final` keyword, it is actually irrelevant since the new object never gets assigned to the original reference – unlike, for example, the following code snippet, which throws a comperr because **str** was declared `final`:

![](images/00804.jpeg)

One more word of caution: Java doesn’t require braces around loop bodies, which not only might break business logic if the coder isn’t attentive but also can create endless loops when a semicolon is placed behind, for example, `while(`*smth_that_evaluates_to_true*`)` out of habit:

![](images/00805.jpeg)

Similarly to our [Problem 9.23](#part0023_split_008.html_id_338), this code fragment also compiles and runs indefinitely although without any visible output. What a nasty, well hidden trap… Fortunately, the exam seems not to abuse semicolons but you should be on your guard just the same.

**Problem 9.24 – B**

**Given:**

![](images/00806.jpeg)

**How many LOCs fail compilation?**

A.Two

B.Three

C.Four

D.Five

The literal "a" is a full-fledged **String** object → does **String** have the method **replace()**? → yes, it does but there are only two overloaded versions, either of which takes *two* args → line 3 is definitely invalid. It would have been fine, though, if it were invoked on a **StringBuilder** object because **StringBuilder** does have **replace()** that accepts three args: two `int`s – start and end – and a **String**.

What about line 4? It looks mighty odd: the args are of different – and even incompatible types… Will it compile? To find out what’s going to happen, we need to test our knowledge of the **replace()** method in **String**. Please answer: what are the arguments for **replace()** in **String**?

By looking at our code (lines 1 and 2), it is tempting to say: "two **String**s and two `char`s". Close, very close – but no cigar… because the API actually defines **replace(**char oldChar, char newChar**)** and **replace(**CharSequence target, CharSequence replacement**)**.

**String** and **StringBuilder** both implement the interface **CharSequence** (we have already met this when discussing [Problem 6.34](#part0020_split_006.html_id_333)); this is precisely why we can use **String**s as arguments in **str.replace()** – and same goes for **StringBuilder** objects. What’s more, **StringBuilder** does define a constructor that accepts a **CharSequence** → line 4 is valid. By the same token, line 5 also compiles.

Alright, what can be said about line 6? Ah, but this one should be easy by now: **StringBuilder** has no **replace()** that would take two args → line 6 is invalid → line 7 fails compilation, as well.

As for the last LOC, it looks clean: three args of correct types in correct places…

One more thing about **replace()** that you might find useful on the exam is that the method returns a reference to the same object if there was no change:

![](images/00807.jpeg)

Boring, eh? Getting on your nerves already… Alright, let’s play with **replace()** for the very last time. Please riddle me this:

**Given:**

![](images/00808.jpeg)

**What is the result?**

Do run this code; it may brighten up your day^([153](#part0023_split_009.html_id_286))…

**Problem 9.25 – A**

**Given:**

![](images/00809.jpeg)

**Is it true that the code prints** `String Quartet No. 19 in C Major, K. 465`**?**

A.true

B.false

The question strongly hints on the most famous string quartet by Mozart so answering it should be easy. A bit harder is figuring out why the code compiles and works as intended because we get used to the idea that employing double quotes as the way to create objects is reserved for **String**s only, from which sort of follows that the reftype must be also **String** – and this is not so.

As soon as we realize that the double-quoted literal "String" is just a handy replacement^([154](#part0023_split_009.html_id_284)) for

![](images/00810.jpeg)

it becomes clear as day that there’s nothing wrong with line D1.

**Problem 9.26 – C**

**Given the following code fragment:**

![](images/00811.jpeg)

**What is the result?**

A.2016-06-14

B.2016-06-13

C.Compilation fails

D.An exception is thrown at run time

**LocalDate** contains only date → the second stat is invalid.

**Problem 9.27 – E**

**Given:**

![](images/00812.jpeg)

**What is the result?**

A.2016-07-13

B.2016-07-14

C.2016-07-15

D.Compilation fails

E.An exception is thrown at run time

Once again: **LocalDate** cannot contain time but formatter wants to extract time out of that object, so the code should apparently misbehave, that much is clear. What’s not so clear is what it’s gonna throw: a comperr or an RTE?

As a rule of thumb for the exam: improperly applied **format()** throws an RTE whereas incorrect invocations of **parse()** and **plus/minusXXX()** usually lead to a comperr.

**Problem 9.28 – D**

**Given:**

![](images/00813.jpeg)

**What is the result?**

A.December 13, 2016

B.June 13, 2015

C.2016-12-13

D.2016-06-13

Now all the LOCs are clean, and the code does output the date contained in the object **ld** – which is, of course, immutable but we already know that. The only question is what form this date will be printed in: after all, the code compiles as can be easily deduced from the list of options.

Alright, the API documentation defines the class **LocalDate** in the following way:

A date without a time-zone in the ISO-8601 calendar system, such as 2007-12-03.

This is it; by default, the date is output as YYYY-MM-DD; notice two mandatory digits for both months and days. To get something like option A or B, we’d need to call on our **LocalDate** object the method **format()** with an appropriate **DateTimeFormatter** as its argument…

I wonder what you will make out of this little gem:

![](images/00814.jpeg)

This is oh-so-praised Kaplan: the software *officially* endorsed by both Oracle and Pearson Vue. That’s how those guys propose – quoting – "to prepare you to pass the 1Z0-808 exam". Well then, be prepared…

**Problem 9.29 – AD**

**Which two LOCs fail compilation?**

A.LocalDateTime.of(2016,6,13);

B.LocalDate.of(2016, Month.JUNE, 50);

C.LocalDateTime.of(2016,06,13,14,15);

D.LocalDate ld = new LocalDate(2016,6,13);

E.LocalTime.now().format(DateTimeFormatter.ISO_DATE);

Option A needs time (no pun intended) but gets none.

Option B is fine as far as the compiler is concerned although the LOC throws

java.time.DateTimeException: Invalid value for DayOfMonth (valid values 1 - 28/31): 50

Option C is also valid because it provides both components (14 denotes hours and 15, minutes).

As for option D, it’s a trap. We are so used to calling constructors that this LOC appears totally innocent. But please do remember:

**LDTs don’t have** `public` **constructors. None of ’em has**.

The LDT objects are usually created by invoking `static` methods such as **of()**, **now()** or **parse()**.

And finally, option E. It does nothing illegal although its desire to format the **LocalTime** object with something that also concerns date will be frowned upon by the JVM:

java.time.temporal.UnsupportedTemporalTypeException: Unsupported field: Year

**Problem 9.30 – A**

**Given:**

![](images/00815.jpeg)

**What is the result if the system date is** `June 13, 2016`**?**

A.2016-06-13
2016-06-13
2016-06-13

B.Compilation fails.

C.A DateParseException is thrown at runtime.

All three LOCs correctly create their corresponding **LocalDate** objects. Yes, it is that simple. And even a simpler version of this question you are going to meet on the exam. Congrats.

**Problem 9.31 – AD**

**Given the full contents of the file** `JavaBirthday.java`**:**

![](images/00816.jpeg)

**One of the LOCs fails compilation. Which two modifications, used independently, will make the code print** `Java was born on May 23, 1995`**?**

A.Replace line 2 with import java.time.*;

B.Replace line 3 with import java.time.format.*;

C.Replace Month.MAY on line 7 with Month.May

D.Replace Month.MAY on line 7 with 05

The LDT classes often borrow things from other classes and even different packages, such as **DateTimeFormatter**, which is defined in **java.time.format**. By using fully qualified names rather than wildcards in imports, the code can create a situation when something is amiss.

That’s exactly what’s happening here: line 7 invokes the method **of()**, which takes as its second arg a constant that is defined in the `enum` **Month**, which belongs to **java.time**. Using a ‘wildcarded’ `import` stat restores the compilability of the class.

Another way to get rid of the comperr is to use a two-digit `int` for the desired month instead of the `enum` constant.

**Problem 9.32 – A**

**Given the following class definition:**

![](images/00817.jpeg)

**What is the result?**

A.[Ruby, Perl, Closure, Emacs Lisp]

B.[Ruby, Closure, Emacs Lisp, Emacs Lisp]

C.[Ruby, Closure, Emacs Lisp]

D.Compilation fails

There is no reason for the compilation to fail since all methods are invoked correctly and the object itself is also created in a valid way. Note, however, that it can contain only **String**s. And don’t forget that unlike **StringBuilder**, **ArrayList** defines **remove()** rather than **delete()**.

Another important thing to keep in mind is that **remove()** acts on the first match only (compare it to **replace()** in **String**).

This useful functionality is possible because **List** is an ordered collection. Which can also be sorted. By the way, what’s the difference between ‘ordered’ and ‘sorted’? This is what the **List** API documentation says:

public interface List<E> extends Collection<E>

An ordered collection (also known as a sequence). The user of this interface has precise control over where in the list each element is inserted. The user can access elements by their integer index (position in the list), and search for elements in the list.

In other words, ‘ordered’ means in practice ‘addressable’ while ‘sorted’ implies that the elements are physically placed in a certain order, which is imposed by the interface **Comparable** and is referred to as ‘natural ordering’. The natural ordering of elements is specific for each class that implements **Comparable**. For example, **String**s are sorted lexicographically:

![](images/00818.jpeg)

Back to our [Problem 9.32](#part0023_split_008.html_id_339); **ArrayList**’s **remove(**Object obj**)** returns `true` if the list contained the specified object → "Emacs Lisp" gets added to the list.

**Problem 9.33 – AF**

**Given:**

![](images/00819.jpeg)

**Which two expressions evaluate to 3?**

A.someTypes. size();

B.someTypes. capacity();

C.someTypes.length();

D.someTypes. get(2).size;

E.someTypes. get(2).length;

F.someTypes. get(2).length();

**ArrayList** doesn’t have the method **capacity()** (which is **StringBuilder**’s member) although it defines **ensureCapacity()**; **length()** belongs to both **String** and **StringBuilder**.

As for the method **get()**, it returns the element at the specified position, and we then invoke **length()** on it because, after all, our **ArrayList** is generified to **String**.

Let’s note in passing that option D wouldn’t have compiled even if **someTypes** were generified to **List** and contained three three-element-long **List**s because the number of elements in **someTypes** must be computed by calling a method rather than by accessing a field.

As for option E, it would have worked, for example, in the following case:

![](images/00820.jpeg)

**Problem 9.34 – E**

**Given the following code fragment:**

![](images/00821.jpeg)

**What is the result?**

A.1

B.Compilation fails on line a1

C.Compilation fails on line a2

D.Compilation fails on line a3

E.An IndexOutOfBoundsException is thrown at run time

Even though the right-hand side of the **list**-creating LOC is missing angle brackets, it’s OK because the compiler can infer our intentions.

As type safety via generics is provided at compile time, the compiler looks at the reftype only and disregards the diamond op on the right:

![](images/00822.jpeg)

On the other hand, the diamond on the left may not be empty → otherwise a comperr:

![](images/00823.jpeg)

All in all, option B is incorrect as line a1 is valid.

Line a2 is also fine as primitives get autoboxed because **List** works with reference types only. (Reminder: using something like `list.add((byte)1);` at line a2 would have thrown a comperr since the compiler would have autoboxed byte to **Byte**, and then what? **Byte** can’t be converted to **Integer** implicitly…)

Now to option D; both methods are invoked correctly but `list.get(1)` will definitely throw an RTE as it wants to look at the second element while **list** has only one.

**Problem 9.35 – B**

**Given:**

![](images/00824.jpeg)

**What is the result?**

A.true

B.4

C.[0, 1, 2, 3, 4]

D.Compilation fails

The invocation `list. add("" + i)` works correctly because our **list** is generified to **String** and the op + is overloaded for **String**s. The methods **indexOf()** and **remove()** are also called in valid ways → option D is out.

**remove()** receives an `int` whose value is 4 (since elements are enumerated starting with zero) → **remove(**int index**)** strips **list** of the element at the specified position and returns it (the element, that is) → the code prints 4.

In short, it is important to remember that **remove(**int index**)** returns what was taken out from the **List** and not, for example, a `boolean` as if to say ‘Alright boss, I successfully did what you have requested’. Because it doesn’t need to: it either removes an element or reports a failure by throwing an IOOBE, that’s all. On the contrary, the overloaded version of the method, namely **remove(**Object obj**)**, does return a `boolean`…

Please also note what kind of loop was used to populate the **list**. It may be tempting to employ an enhanced `for`, like this:

![](images/00825.jpeg)

but it won’t work: **list** is still empty, there’s no elements to iterate over → `for` won’t run, and the code will enter an endless loop because the loop var **i** has no chance to increment…

**Problem 9.36 – B**

**Given:**

![](images/00826.jpeg)

**What is the result?**

A.[OK, OK]

B.[OK, ]

C.Compilations fails

D.A RuntimeException is thrown

As **list** isn’t generified, it accepts any object. Casts ensure that the code may call methods specific for either **StringBuilder** or **String**. And finally, since **String** is immutable, invoking the method **concat()** doesn’t affect the original **String** object, which remains empty.

**Problem 9.37 – A**

**Given:**

![](images/00827.jpeg)

**What is the result?**

A.[jay, finch, titmouse, kinglet]

B.[jay, finch, titmouse, true]

C.Compilation fails on line b1

D.Compilation fails on line b2

Using an empty diamond in the right-hand side of the stat on line b1 doesn’t affect code’s compilability, so **aviary** gets successfully populated with virtual birds whose reftype is **Object** and the actype **String**. Line b2 is valid, as well; it replaces the first element with **String** "jay", and since the method **set()** returns what was replaced, **add()** appends "kinglet" to the list.

**Problem 9.38 – C**

**Given:**

![](images/00828.jpeg)

**What is the result?**

A.16null16

B.16null16null

C.16null16 and a NullPointerException

D.Compilation fails

**List** autoboxes primitive args, so line s1 actually appends an **Integer**. Adding `null` to **ages** isn’t problematic, either. What happens next, however, is: the first `for` loop behaves itself but the enhanced `for` throws an NPE. Let’s see why.

As `get(i)` returns an **Integer**, the printing stat receives what **Integer**’s **toString()** returns → the first `for` outputs 16null. The enhanced `for` successfully unboxes the first element and assigns it to a primitive, but a similar attempt with `null` fails. Replacing `int` with a compatible reference type would have cleared up the problem.

| **Conclusion**: | using a primitive loop var in an enhanced `for` can lead to an NPE when iterating over a **List** → always make sure that the loop var is suitable for the task. |

**Problem 9.39 – C**

**Given the following class definitions:**

![](images/00829.jpeg)

**Which LOC, when inserted at line r1, enables the code to print** `Passed: Alice, Doug,`**?**

A.checkScore(list, () -> e. getScore() > 65);

B.checkScore(list, Examinee e -> e. getScore() > 65);

C.checkScore(list, e -> e. getScore() > 65);

D.checkScore(list, (Examinee e) -> { e.getScore() > 65; });

The Problem looks rather demanding but, in fact, lambda-related questions are arguably among the easiest ones on the exam. As always, we start our analysis by glancing at the list of available options, and a bunch of lambda expressions immediately indicates what the question is about.

The exam requires us to work with predicative lambdas; we just need to make sure if this is the case; the **checkScore()** method’s signature confirms it.

Since the interface **Predicate**’s **test()** method takes a single arg, option A is out. Option B is also invalid because the explicit use of the parameter type requires parentheses.

Option D fails compilation because semicolon, braces and `return` should be used together^([155](#part0023_split_009.html_id_288)) – but `return` is missing.

**Problem 9.40 – BC**

**Let** `sb` **refer to a StringBuilder object. Which of the following fail(s) compilation?**

A.sb -> sb.toString()

B.StringBuilder sb -> sb.toString()

C.(StringBuilder sb) -> return sb.length();

D.(StringBuilder sb) -> { return sb.length(); }

The question hints that the list of options may contain more than one invalid LOC so we’ll be needing to check every option. All four cases indicate that the lambda method takes a single arg of type **StringBuilder** and returns either a **String** or an `int` – and this info is enough to start the analysis.

Option A: the formal parameter has no explicit data type but this is OK; the method body contains a single **String**-returning stat so braces, semicolon and `return` aren’t necessary → option A looks perfectly compilable.

What about option B? While the method body appears to be correct, the parameter list is missing parentheses, which are now mandatory because of the explicitly stated data type.

Option C is also invalid since it is omitting braces; option D, on the other hand, dutifully follows all the rules: the parentheses around the paramlist are in place, and the method body is written in its full form, with braces, `return` and semicolon → only options B and C fail compilation.

Let’s see if our conclusion is indeed correct:

![](images/00830.jpeg)

**Problem 9.41 – AE**

**Given:**

![](images/00831.jpeg)

**Which two options can make the code compile and run successfully?**

A.Replace line t3 with `check(list, myList -> list.isEmpty()));`

B.Replace line t2 with `List list = new ArrayList();` and replace line t3 with `check(list, myList -> myList.isEmpty()));`

C.Replace line t1 with `String check(List list, Predicate<ArrayList> p){` and line t3 with `check(list, myList -> myList.isEmpty()));`

D.Replace line t1 with `String check(ArrayList list, Predicate<ArrayList> p){` line t2 with `List mist = new ArrayList();` and line t3 with `check(mist, list -> list.isEmpty()));`

E.Replace line t1 with `String check(List list, Predicate<List> p){` and line t3 with `check(list, myList -> myList.isEmpty()));`

First of all, we need to see why the original code doesn’t compile. All options mention line t3; is this LOC problematic? Indeed, it is: its paramlist clashes with the already declared variable **list**. Renaming the parameter saves the day → option A (incidentally, it completely disregards the functional method's argument and accesses **list** directly, then prints Empty) is in.

What about option B? It changes the object’s reftype to a wider one but how can this help when **myList** is passed to **test()** that sees it as an **Object** only? After all, **Object** has no **isEmpty()** method…

All the other options hint that there may be something wrong with the compatibility of the data types in the signature of the **check()** method and its invocation.

Why? Because line t1 specifies ungenerified **List** and **Predicate** → they will accept any object → expect illegal implicit downcasts and CCEs at run time.

We can use the following rule of thumb:

A predicative lambda? Check its type first! Object, Predicate and the formal parameter are ideally should be of the same type; no sub/superclasses combos for Predicate and the parameter.

Let’s see how the rule works in practice; we’ll start with something simpler: will this print `true`?

![](images/00832.jpeg)

The answer is ‘No’ because the code fails compilation. Reason: **Predicate** is generified to **List** → **Predicate**’s **test()** expects **List** → but **checkList()** offers **ArrayList al** → won’t work; after all, lambda expression’s ultimate *raison d’être* is to override the functional method…

Very well; what if we change **Predicate**<List> to **Predicate**<ArrayList>? Now lambda’s body does override the method **test()** but the code still won’t compile since the invocation `p. test(list)` specifies an arg of type **List** → we have an implicit downcast from **List** to **ArrayList** on line X, which is illegal. On the other hand, an explicit cast such as `p. test(<ArrayList>list)` works, and the code prints `true`.

Recapping: **Predicate**<T> and paramlist (T param) must be of the same type T and the object must be assignable to that type (or use a cast).

Please also note that removing <> from **Predicate**<> means that we will have to remove type from the paramlist, too – and *that* automatically makes **Predicate** of **Object** – which doesn’t have **isEmpty()** method, so we’ll be needing something that returns a `boolean`; for example:

![](images/00833.jpeg)

Now we can get back to our [Problem 9.41](#part0023_split_008.html_id_340); option C makes **test()** expect an **ArrayList** but delivers a **List** → which cannot be converted to **ArrayList** implicitly → a comperr. Doing the same thing with a cast in a strategic place would have helped, though:

![](images/00834.jpeg)

Option D resolves the conflict of types between the **check()** method’s signature and the **test()** method’s invocation; however, the fact that this option also changes the object’s reftype on line t2 to **List** leads to the same problem: an illegal implicit downcast in the **check()** method’s invocation. Casting **mist** would have cleared the problem:

![](images/00835.jpeg)

Option E finally restores balance: the signature of **check()** specifies a **List** for both its args, and the object created on line t2 is of type **ArrayList**, which IS-A **List**…

**Problem 9.42 – D**

**Given:**

![](images/00836.jpeg)

![](images/00837.jpeg)

**Which modification will achieve the same result?**

A.Overload the method **interrogate()** with the following code fragment:

![](images/00838.jpeg)

B.Overload the method **interrogate()** with the following code fragment:

![](images/00839.jpeg)

C.Add the following interface:

![](images/00840.jpeg)

D.Add the following interface:

![](images/00841.jpeg)

As the available options make use of not only predicative lambdas but also lambdas in general, you will not meet such a question on the exam; practicing with fundamental principles, however, can be beneficial, so let’s do it unhurriedly and methodically.

To have a lambda, we’ll be needing a functional interface, in other words, an interface with a single abstract method. Although this handy definition isn’t entirely correct – as you’ll see in the very next [Problem 9.43](#part0023_split_008.html_id_341) – it’s good enough in practice.

What else do we need? Obviously, a properly written lambda expression (LE). An LE is made up of three basic components:

![](images/00842.jpeg)A comma-separated list of formal parameters enclosed in parentheses…

| ***Reminder***: | We can omit the LE params’ data types – and also get rid of the parentheses altogether if there is only one param. |

![](images/00843.jpeg)… the arrow token, ->

![](images/00844.jpeg)… and a body, which can consist of a single expression or a statement block.

| ***Reminder***: | Single expression doesn’t require braces REGARDLESS of whether the method is `void` or not. |

Also let’s not forget that `return` in a lambda expression can’t live without its pals Semicolon and the Braces brothers.

In short, all of the following can work if the functional method is `void`, and the last LOC is also valid for a functional method that returns a **String**:

![](images/00845.jpeg)

**Example 1:**

![](images/00846.jpeg)

In Example 1 we defined our own functional interfaces; one of them, **Lambdable**, has a `void` method → no invocation of **run1()** may mention `return` that actually returns something; the fourth, invalid invocation would have worked if **run1()** were replaced with **run2()**.

Time to play with the interface **Predicate**. Coming from the field of linguistics, I couldn’t at first get the whole notion through my skull because to me a predicate meant either a verb or a verb phrase. For example, in the sentence ‘It doesn’t compute’ the predicate is ‘doesn’t compute’, and in ‘Lambdas are weird’ the predicate is ‘are weird’. And how exactly can it help to conquer those LEs? As for the attempt to get enlightened by asking Wiki, it only made my head spin…

The real breakthrough came after I had found a short, workable definition of predicate in the *Dictionary of Logic* by Nikolay Kondakov^([156](#part0023_split_009.html_id_290)); basically it says that "…a predicate is an utterance that affirms or negates something about an object… It reflects presence or absence of a certain feature… In mathematical logic, the predicate is a logical function that is defined for a specific task and whose value can be either `true` or `false`".

And that was it. From this definition it immediately follows that 1) predicate needs an object, and 2) it returns a boolean. Exactly as it is with the method `boolean test(T t)` defined in the interface **java.util.function.Predicate**… Everything fell into place.

**Example 2 (with Predicate):**

![](images/00847.jpeg)

Getting back to our Problem. Option A suggests to overload the method **interrogate()** with:

![](images/00848.jpeg)

The code compilability analysis on the exam should start with the verification of the lambda method body followed by signature check. Yes, in this order because the exam question will most likely test you on the correctness of the lambda expression rather than the compatibility of the involved objects.

**Verifying the lambda expression**:

| *Step 1*. | Since we are overriding **test()** in **Predicate**, a single formal parameter is mandatory: |

–is it in place?

–does it have its type specified?

if ‘yes’, the paramlist must be enclosed in parentheses;
if ‘no’, parentheses are optional;

–what about the param’s name? does it clash with any of the previously declared vars that are still in scope?

| *Step 2*. | Is the lambda token in place? |
| *Step 3*. | **test()** in **Predicate** is supposed to return a `boolean`, therefore: |

–does the method body specify a single statement?

if ‘yes’, does it use `return`?

if ‘yes’, it must end with a semicolon and be enclosed in parentheses;
if ‘no’, the body must be ‘naked’ (neither braces nor semicolon);

if ‘no’, the body must be written in a full form, with braces and semicolons.

–does it indeed return a `boolean`?

| *Step 4*. | See if the same lambda expression is used in other options. For example, in our current case (Problem 9.42) it is → since the expression is valid, we don’t have to bother ourselves with validating it anymore. |

**Verifying the signature**:

| *Use this rule*: | If the object, predicate and formal parameter are of the same data type → OK If they aren’t… (*sigh*) well, expect all kinds of trouble. |

Let’s see what we’ve got:

![](images/00849.jpeg)

The signature specifies an ungenerified **Predicate** → as the result, the method **test()** sees only an **Object** instead of the promised **Suspect** → **Object** has no **getStatement()** method → a comperr.

Now to option B; it wants us to overload the method **interrogate()** with the following:

![](images/00850.jpeg)

and use the same method invocation as in option A (which we have already ascertained as being valid) → skipping the lambda expression verification → applying signature verification rule → **Predicate** is generified to **Suspect** whereas the object **perps**’ reftype is an ungenerified **List** → but the enhanced `for` will want to use **perps**’ elements as **Suspect**s rather than **Object**s → a comperr because of an implicit downcast from **Object** to **Suspect**, which is illegal.

If we only had a *carte blanche*, we still could, theoretically speaking, save the day by making the enhanced `for` to iterate over **Object**s rather than **Suspect**s and then apply a couple of casts in strategic places, like this:

![](images/00851.jpeg)

Line X gets rid of the comperr that reads ‘incompatible types: Object cannot be converted to Suspect’; the cast on line XX gives the method **test()** what it wants; and the cast on line XXX allows to invoke **getName()**. Option B, however, isn’t that flexible so we mark it as incorrect.

Now, option C. Ah, but this is fun! We get to create our own interface that should mimic **Predicate** in **java.util.function**:

![](images/00852.jpeg)

Wait a minute… How come the method **test()** in **LieDetector** is declared as `default`?! it must be `abstract`! No, this won’t do: our brand new interface isn’t functional → option C isn’t what we need, either…

During the initial pass, we stop our analysis at this point because we have arrived at the correct answer by the process of elimination. The Review stage, however, is different: we will have to verify our conclusion by checking option D, too.

Alright, so we add a new interface:

![](images/00853.jpeg)

then overload the method **interrogate()** with the following:

![](images/00854.jpeg)

and replace the call to **interrogate()** with this:

![](images/00855.jpeg)

As we saw when analyzing option A, the invocation is valid. The interface is indeed functional: it declares a single abstract method. The signature, however, looks suspicious because **LieDetector** isn’t generified… Hmm… what could that mean?.. Ah! unlike **test()** in **Predicate**, the method **analyze()** declares that it will accept only objects of type **Suspect** → this is a perfect match with **List**<Suspect> → the enhanced `for` is valid → this option is indeed correct.

Now, what’s the story with **Predicate**’s **test()** and how it differs from our **analyze()**? Compare the definitions:

![](images/00856.jpeg)

In its current form, our **LieDetector** cannot be generified because <T> is missing; that’s why the method **analyze()** was specifically tailored to **Suspect**. After making **LieDetector** generifiable, we could use the already familiar idiom with the generified **List** and **LieDetector** in the method's signature :

![](images/00857.jpeg)

**Problem 9.43 – E**

**Which one is true?**

A.Functional interface may not contain more than one method.

B.Any interface that has a single abstract method is therefore functional.

C.Functional interface cannot have superinterfaces.

D.Functional interface cannot be extended.

E.None of the above.

The following code answers the question by illustrating how available options work:

![](images/00858.jpeg)

The program has two functional interfaces, namely **Lambdable** and its child, **Omegable** → options C and D are incorrect.

Option A is obviously incorrect as **Lambdable** (and, therefore, **Omegable**) has three methods (`default` **walk()** plus `abstract` **equals()** plus inherited `abstract` **run(**StringBuilder sb**)**), yet it works as intended (just look at the `@FunctionalInterface` annotations to which the compiler doesn’t object) → options A and B are also incorrect…

We were taught that

Conceptually, a functional interface has exactly one abstract method^([157](#part0023_split_009.html_id_294))

which is a bit disconcerting as **Lambdable** has *two* abstract methods. As usual, to understand what the heck is going on, we have to turn to the JLS (§9.8, *Functional Interfaces*):

The definition of functional interface excludes methods in an interface that are also public methods in Object. This is to allow functional treatment of an interface like java.util.Comparator<T> that declares multiple abstract methods of which only one is really "new" - int compare(T,T). The other method - boolean equals(Object) - is an explicit declaration of an abstract method that would otherwise be implicitly declared, and will be automatically implemented by every class that implements the interface.

So for an interface to define an `abstract` method that has its `public` namesake in **Object** doesn't count toward being functional.

Well, basically this is it for lambdas. Since our book is also at its end, how about adding a couple of extra touches to the discussion? and then we’ll call it quits…

Consider the following program, which tests certain animal species for their ability to swim, hop or fly^([158](#part0023_split_009.html_id_292)):

![](images/00859.jpeg)

![](images/00860.jpeg)

And this is what the code outputs:

![](images/00861.jpeg)

Several approaches are being used to check the traits: the ability to hop is tested in the old-school fashion, so to speak, by explicitly creating an object that has a getter method that returns a `boolean`; then we use a lambda expression to check animals for their ability to swim; note that it can take two forms: we either write the LE directly on the LOC with the method invocation (line 54), or use the **Predicate**<Animal> var that holds the appropriate LE (the commented-out line 55). The two last checks (for the ability to fly and, after that, the ability to both fly and hop) demonstrate the use of streams and complex, multi-stage filters, which are possible thanks to the additional methods that the interface **Predicate** defines.

For example, replacing line 61 with the following:

![](images/00862.jpeg)

would have selected only those animals that can either hop or fly (i.e., fish, kangaroo, cat, dog, bird, rabbit, and ladybug), while this LOC

![](images/00863.jpeg)

would have chosen those who can hop but are unable to fly (namely, kangaroo, cat, dog, and rabbit). This is where our decision to assign the LEs to separately declared **Predicate** variables comes in handy as the code becomes less cluttered and, therefore, more readable and maintainable…

![](images/00007.jpeg)

The book is practically over, and under any other circumstances I would be saying goodbye and wishing you good luck on the exam. Instead, I’ve chosen to lay a finishing touch by quoting Mark Twain:

It ain’t what you don’t know that gets you into trouble. It’s what you know for sure that just ain’t so.

And here’s the steam hammer to drive the point home:

**Given full contents of the file** Daddy.java **located in** `C:\Try_Java\tempa` **folder:**

![](images/00864.jpeg)

**Given full contents of the file** Twin_1.java **located in** `C:\Try_Java\org\xlator` **folder:**

![](images/00865.jpeg)

**Given full contents of the file** Twin_2.java **located in** `C:\Try_Java\org\xlator` **folder:**

![](images/00866.jpeg)

**What is the result when we try to compile and run** Twin_1.java**?**

A.Daddy says "Sweet dreams!" twice and both twins get their goodnight kisses

B.Compilation fails in the class Twin_1 but not in the class Twin_2

C.Compilation fails in the class Twin_2 but not in the class Twin_1

D.Both classes fail compilation

The correct answer is option D:

![](images/00867.jpeg)

Guys, this is hilarious. The method **kiss()** is indeed `protected` but, after all, both descendants extend **Daddy**. So how come we get two errors as if neither of the child classes may access a lawfully inherited method? And if you think the failure to get a loving goodnight kiss has something to do with the fact that Daddy and his twin children live under different roofs, I can give you another, even more bizarre example that uses classes within the same package.

Look here: any class we create extends **Object**, therefore all the methods defined in **Object**^([159](#part0023_split_009.html_id_298)) are available to each and every class; this is Java’s ABC. Yet the following code throws a similar comperr, "**clone()** has protected access in **Object**":

![](images/00868.jpeg)

What happens at run time isn’t our immediate concern; right now the question is why line 5 fails compilation.

This entire brain-wracking conundrum is only possible due to an immensely popular yet hopelessly wrong view of what `protected` access means in Java. When asked about it, most people would dutifully mumble something close to the following quote from the official Oracle Java tutorial^([160](#part0023_split_009.html_id_296)):

The `protected` modifier specifies that the member can only be accessed within its own package (as with package-private) and, in addition, by a subclass of its class in another package.

So what of it? irritatingly asks my gentle reader. The definition is true, ain’t it? Oh yes, most definitely. My point is that lots of people don’t realize clearly that it contains *two* fundamental conditions rather than one that concerns *where* the classes are located. The second condition to be taken into account is *who* attempts to access the `protected` member.

You’ll get what I mean as soon as you answer this question: who wants to invoke **clone()** on the object created on line 5? is it class **A** or class **B**?

See? **clone()** is defined in **java.lang.Object** → it may be accessed outside the **java.lang** package only by **Object**’s subclasses along a direct inheritance line → **A** and **B** are on parallel but distinct inheritance lines → yet **B** wants to invoke a method that belongs to a different data type → ‘No mister, says the compiler, although **A** is your brother, he inherited his own stuff from Daddy-O, and you’ve got no right to touch something that ain’t yours. So mind your own business and keep your hands off other people’s property. Now scram!’

Or look at it this way: the compiler maintains ethical cloning standards: ‘Thou shalt not clone other people. Clone only thyself’.

The following example illustrates how **B** could use **A** as a proxy; now the code compiles because **B** actually calls its own **clone()**, the one that it inherited itself:

![](images/00869.jpeg)

Poor, poor **B**: it is still pretty much unhappy because it forgot to support the **Cloneable** interface and doesn’t know how to reproduce, but this is another story.

Anyway, what should be remembered from our brief excursion into the wiles and woes of inheritance is this (JLS, §6.6.2, *Details on protected Access*):

A `protected` member or constructor of an object may be accessed from outside the package in which it is declared only by code that is responsible for the implementation of that object.

An illustration:

![](images/00870.jpeg)

So, while `protected` on line 1 lets the class **Test** properly extend **One**, the very same modifier on line 2 kills compilation…

Now go and break a leg. Rock the test.

* * *

^([141](#part0023_split_000.html_id_259)) Do not confuse "string pool" with "constant pool", which is allocated at run time and "…contains several kinds of constants, ranging from numeric literals known at compile-time to method and field references that must be resolved at run-time" (JVM Spec, Java SE8 Ed., §2.5.5, *Run-Time Constant Pool*).

^([142](#part0023_split_000.html_id_261)) Means either **str.substring()** or **sb.substring()**.

^([143](#part0023_split_000.html_id_263)) space (0x20), horizontal tab (0x09), form feed (0x0C) and line terminators LF (0x0A), CR (0x0D) and CRLF.

^([144](#part0023_split_002.html_id_267)) Because **Period**’s **ofXXX()** methods are `static`; all they do is just return a newly created **Period** object.

^([145](#part0023_split_002.html_id_265)) Something like **ofLocalizedTime(**timeStyle**)** or RFC_1123_DATE_TIME is obviously out of scope for 1Z0-808.

^([146](#part0023_split_004.html_id_271)) Citing the **Arrays** API docs: "`static` <T> **List**<T> **asList(**T... a**)** returns a fixed-size list backed by the specified array".

^([147](#part0023_split_004.html_id_269)) Being a utility class, **Collections** is made up entirely of `static` methods; same goes for **java.util.Arrays**.

^([148](#part0023_split_006.html_id_273)) Just an acronym: ‘semi’ for ‘semicolon’, ‘re’ for ‘return’, and ‘bra’ for ‘braces’. As the Semirebra Rule is specifically tailored to **java.util.function.Predicate**, it is meant to be used on the 1Z0-808 exam only.

^([149](#part0023_split_008.html_id_275)) **String** + all **LDT**s + all Wrappers such as **Byte**, etc. + *structurally*-immutable **List** created by **Arrays.asList()**.

^([150](#part0023_split_008.html_id_277)) Quoting from the **StringBuilder** API docs.

^([151](#part0023_split_008.html_id_279)) **String(**String str**)** and **String(**StringBuilder sb**)** + **String**(), which is virtually useless because the object is immutable.

^([152](#part0023_split_008.html_id_281)) **ArrayList** has no **replace()**: it uses **set(**int index, E element**)** instead. **StringBuilder** defines **replace(**int start, int end, String str**)** and doesn’t overload it.

^([153](#part0023_split_008.html_id_285)) As there’s no **StringBuilder** constructor that would take a `char` *per se*, 'Z' gets widened to `int`, so new **StringBuilder**('Z') creates just an empty **StringBuilder** with capacity of 90\. Effectively, the **replace()** invocation reads **replace(**"","^"**)** – and "" matches boundaries of "_" because of the way the regex engine works…

^([154](#part0023_split_008.html_id_283)) Ref.to the API javadoc's preambule for the class **String**.

^([155](#part0023_split_008.html_id_287)) One more time: please keep in mind that this rule is applicable only on our exam where we are supposed to deal with predicative lambdas. The interface **Predicate**’s **test()** returns a boolean → hence return is mandatory → but when the functional method is `void`, the Semirebra rule won’t work.

^([156](#part0023_split_008.html_id_289)) Not available in English; there’s a German translation, though: *Wörterbuch der Logik* von N.I.Kondakow. The book is awesome, it helped me untold number of times…

^([157](#part0023_split_008.html_id_293)) [https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html](https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html)

^([158](#part0023_split_008.html_id_291)) You can find its listing without line numbers in Appendix C.

^([159](#part0023_split_009.html_id_297)) **java.lang.Object** doesn’t have `private` methods.

^([160](#part0023_split_009.html_id_295)) [https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)

![](images/00871.jpeg)

| **Step 1**. | If you don’t have an Oracle account, go to [https://www.oracle.com/index.html](https://www.oracle.com/index.html) to create one; you’ll need it anyway to access your exam score. It is also possible to register your Oracle account *post factum*. |
| **Step 2**. | Next go to [http://www.pearsonvue.com/](http://www.pearsonvue.com/). Select For test takes → Test taker home: |

![](images/00872.jpeg)

| **Step 3**. | Select vendor (obviously, in our case it’s Oracle): |

![](images/00873.jpeg)

| **Step 4**. | In the section **Schedule An Exam** click on and read the **Oracle Certification Program Candidate Agreement**, because the page warns that |
|  | BY SELECTING THE "START" BUTTON BELOW YOU ARE AGREEING TO THE TERMS AND CONDITIONS OF THE ORACLE CERTIFICATION PROGRAM CANDIDATE AGREEMENT |
|  | Moreover, you’ll have to sign this document on paper when you come to the test center to take the exam. |

![](images/00874.jpeg)

Please also note that Agreement contains certain restrictions that concern minors, etc.

| **Step 5**. | Click **Schedule An Exam** and create you own account with **Pearson Vue** (unless, of course, you already have one): |

![](images/00875.jpeg)

| **Step 6**. | Agree to the Pearson Vue’s **Privacy and Cookies Policy**, then fill in your personal data, contact info, etc., and finally press **Finish**: |

![](images/00876.jpeg)

| **Step 7**. | On successful creation of your web account, you’ll be taken to an exam selection page, where you click **Proctored Exams**… |

![](images/00877.jpeg)

… which offers three choices: order a bundle, a beta exam or just a regular certification exam:

![](images/00878.jpeg)

**Exam Bundles** let you buy a desired exam together with Kaplan’s practice tests for it:

![](images/00879.jpeg)

**Beta Exams** are those freshly created exams that Oracle tests on us, exam takers:

![](images/00880.jpeg)

Oracle uses betas to determine both correctness of questions and passing score threshold.

Pros:

–betas are a lot cheaper (around $50-90 depending on the exam);

–allocated time is longer;

–entire Java community benefits from your feedback.

Cons:

–as the exam is right from the oven, you probably won’t find comprehensive (or at least recently updated) study guides and practice tests for it;

–you’ll be waiting for your score for months while Oracle collects enough statistical data.

Since betas are available for a limited time only and 1Z0-808 is now in its mature state, our next chance to sit a beta OCAJSE will come after Oracle releases Java 1.9.

As for **Certification Exams**, there are so many of them it’s easier to type the desired code right into the search field; it’ll give you two options: standard 1Z0-808 and 1Z0-808-JPN, which is available only in Japan^([161](#part0024.html_id_300)):

![](images/00881.jpeg)

Clicking **Go** will take you to the exam scheduling page:

![](images/00882.jpeg)

Make sure you read **Testing Policies** before clicking the **Schedule this Exam** button.

| **Step 8**. | Click ![](images/00883.jpeg)to confirm that you indeed want to register for this particular exam (note that you can also schedule more exams to be taken on the same day) and then click **Proceed to Scheduling**: |

![](images/00884.jpeg)

| **Step 9**. | Now you have to choose a test center and indicate the date & time when you want to sit the exam there; by default, the page lists the nearest centers first (you did provide your address when creating your Pearson Vue profile, right?); if needed, click the **Display more test centers**... link. |
|  | You’ll get to select three centers to check their availability on that particular date; some of them will accept exam takers only once a week, others are more accommodating; if none of them provide what you want, click **Change Test Centers**: |

![](images/00885.jpeg)

After finding a convenient combination, select the start time:

![](images/00886.jpeg)

On having made sure that the appointment info is correct, **Proceed to Checkout**:

![](images/00887.jpeg)

![](images/00888.jpeg)

After the payment is processed, you get your confirmed order summary:

![](images/00889.jpeg)

On clicking **Return Home** you’ll see that your appointment was successfully registered with Pearson Vue:

![](images/00890.jpeg)

Also check your email box, which should already contain the official exam purchase invoice. *Voilà*! Done and done.

| **Step 10**. | Now contact your test center to see if they got notified by Pearson Vue and that they will be waiting for you on that particular day and time. Also check if they’ll accept those two IDs you’re planning to take with you. Ask if they allow bringing water to the test room. Tissue paper or handkerchiefs to wipe off your blood, sweat and tears. Ask about eye drops, too. |
|  | Apparently, Oracle firmly believes we are going to use our paper money, candy wrappers, bottle labels and whatnots to make crib notes and cheat sheets. Truly desperate souls may want to follow Michael Scofield’s example although I’ve no idea about Oracle’s policy on tattoos – including shedding all of your cloths and bending backwards to cast a glance at that last rule on method overriding. So ask. |
|  | As the last resort consider printing your own T-shirt – and not upside down if you want to look particularly enigmatic on CCTV monitors – so use your social engineering skills to figure out if those proctors can read Klingon or the Easter Island’s script… |
|  | On a more serious note you may want to ‘case the joint’, so to speak, by running a brief recon mission a couple of weeks in advance to see if the facility does provide a separate test room, which should be sufficiently quiet, and so on. |

Upon finishing the exam you’ll get a piece of paper attesting to the fact, and then – most likely, within the next two hours – your score will be made available. Follow the link in the notification email from Oracle to logon to the CertView using your Oracle account user name and password.

It really shouldn’t take more than a couple of hours to get your score processed, so if there’s no email and you have been waiting long enough, go directly to Oracle University^([162](#part0024.html_id_302)), sign in, click on **Certification** then on **CertView**…

![](images/00891.jpeg)

… and then on **Exam Results**…

![](images/00892.jpeg)

![](images/00893.jpeg)

…upon which you should see something close to this:

![](images/00894.jpeg)

If you did pass, soon a new email will arrive to take you to Acclaim site, which provides virtual badges you could use in your correspondence and CVs; also you’ll get a link to your electronic certificate:

![](images/00895.jpeg)

… with a validation code in the bottom right corner that you could use to order your free Oracle Certification T-shirt to show off:

![](images/00896.jpeg)

As for printed certificate, you’ll need to explicitly ask for one through a CertView request form or by following a link in the notification email; the delivery can take up to ten weeks.

* * *

^([161](#part0024.html_id_299)) In case you’re wondering if Japanese get preferential treatment, the answer is ‘No’: the allocated time and passing score are exactly the same, and the translation doesn’t contain hints. Yes, I did check – and since I am a professional Japanese-Russian translator with 20+ years of experience, you’d better take my word for it.

^([162](#part0024.html_id_301)) [https://education.oracle.com/pls/eval-eddap-dcd/ocp_interface.ocp_candidate_login?p_include=Y](https://education.oracle.com/pls/eval-eddap-dcd/ocp_interface.ocp_candidate_login?p_include=Y)

![](images/00897.jpeg)

![](images/00898.jpeg)

![](images/00899.jpeg)

![](images/00900.jpeg)

![](images/00901.jpeg)

![](images/00902.jpeg)

![](images/00903.jpeg)

[Problem 1.1 – C](#part0015_split_002.html_pro1.1)

[Problem 1.2 – A](#part0015_split_002.html_pro1.2)

[Problem 1.3 – C](#part0015_split_002.html_pro1.3)

[Problem 1.4 – E](#part0015_split_002.html_pro1.4)

[Problem 1.5 – C](#part0015_split_002.html_pro1.5)

[Problem 1.6 – B](#part0015_split_002.html_pro1.6)

[Problem 1.7 – E](#part0015_split_002.html_pro1.7)

[Problem 1.8 – BCE](#part0015_split_002.html_pro1.8)

[Problem 1.9 – A](#part0015_split_002.html_pro1.9)

[Problem 1.10 – C](#part0015_split_002.html_pro1.10)

[Problem 1.11 – ADE](#part0015_split_002.html_pro1.11)

[Problem 1.12 – B](#part0015_split_002.html_pro1.12)

[Problem 1.13 – B](#part0015_split_002.html_pro1.13)

[Problem 1.14 – AB](#part0015_split_002.html_pro1.14)

[Problem 1.15 – CD](#part0015_split_002.html_pro1.15)

[Problem 1.16 – B](#part0015_split_002.html_pro1.16)

[Problem 1.17 – A](#part0015_split_002.html_pro1.17)

[Problem 1.18 – ABD](#part0015_split_002.html_pro1.18)

[Problem 1.19 – A](#part0015_split_002.html_pro1.19)

[Problem 1.20 – D](#part0015_split_002.html_pro1.20)

[Problem 1.21 – BCF](#part0015_split_002.html_pro1.21)

[Problem 1.22 – C](#part0015_split_002.html_pro1.22)

[Problem 1.23 – D](#part0015_split_002.html_pro1.23)

[Problem 2.1 – A](#part0016_split_007.html_pro2.1)

[Problem 2.2 – C](#part0016_split_007.html_pro2.2)

[Problem 2.3 – C](#part0016_split_007.html_pro2.3)

[Problem 2.4 – AD](#part0016_split_007.html_pro2.4)

[Problem 2.5 – AD](#part0016_split_007.html_pro2.5)

[Problem 2.6 – C](#part0016_split_007.html_pro2.6)

[Problem 2.7 – E](#part0016_split_007.html_pro2.7)

[Problem 2.8 – E](#part0016_split_007.html_pro2.8)

[Problem 2.9 – E](#part0016_split_007.html_pro2.9)

[Problem 2.10 – E](#part0016_split_007.html_pro2.10)

[Problem 2.11 – A](#part0016_split_007.html_pro2.11)

[Problem 2.12 – D](#part0016_split_007.html_pro2.12)

[Problem 2.13 – B](#part0016_split_007.html_pro2.13)

[Problem 2.14 – C](#part0016_split_007.html_pro2.14)

[Problem 2.15 – D](#part0016_split_007.html_pro2.15)

[Problem 2.16 – D](#part0016_split_007.html_pro2.16)

[Problem 2.17 – C](#part0016_split_007.html_pro2.17)

[Problem 2.18 – C](#part0016_split_007.html_pro2.18)

[Problem 2.19 – C](#part0016_split_007.html_pro2.19)

[Problem 2.20 – C](#part0016_split_007.html_pro2.20)

[Problem 2.21 – A](#part0016_split_007.html_pro2.21)

[Problem 2.22 – C](#part0016_split_007.html_pro2.22)

[Problem 2.23 – C](#part0016_split_007.html_pro2.23)

[Problem 2.24 – B](#part0016_split_007.html_pro2.24)

[Problem 2.25 – B](#part0016_split_007.html_pro2.25)

[Problem 2.26 – D](#part0016_split_007.html_pro2.26)

[Problem 2.27 – A](#part0016_split_007.html_pro2.27)

[Problem 2.28 – C](#part0016_split_007.html_pro2.28)

[Problem 2.29 – C](#part0016_split_007.html_pro2.29)

[Problem 2.30 – D](#part0016_split_007.html_pro2.30)

[Problem 2.31 – AC](#part0016_split_007.html_pro2.31)

[Problem 2.32 – B](#part0016_split_007.html_pro2.32)

[Problem 2.33 – E](#part0016_split_007.html_pro2.33)

[Problem 3.1 – B](#part0017_split_005.html_pro3.1)

[Problem 3.2 – D](#part0017_split_005.html_pro3.2)

[Problem 3.3 – C](#part0017_split_005.html_pro3.3)

[Problem 3.4 – A](#part0017_split_005.html_pro3.4)

[Problem 3.5 – A](#part0017_split_005.html_pro3.5)

[Problem 3.6 – A](#part0017_split_005.html_pro3.6)

[Problem 3.7 – A](#part0017_split_005.html_pro3.7)

[Problem 3.8 – A](#part0017_split_005.html_pro3.8)

[Problem 3.9 – A](#part0017_split_005.html_pro3.9)

[Problem 3.10 – B](#part0017_split_005.html_pro3.10)

[Problem 3.11 – A](#part0017_split_005.html_pro3.11)

[Problem 3.12 – B](#part0017_split_005.html_pro3.12)

[Problem 3.13 – B](#part0017_split_005.html_pro3.13)

[Problem 3.14 – D](#part0017_split_005.html_pro3.14)

[Problem 3.15 – D](#part0017_split_005.html_pro3.15)

[Problem 3.16 – D](#part0017_split_005.html_pro3.16)

[Problem 3.17 – E](#part0017_split_005.html_pro3.17)

[Problem 3.18 – AC](#part0017_split_005.html_pro3.18)

[Problem 3.19 – B](#part0017_split_005.html_pro3.19)

[Problem 3.20 – C](#part0017_split_005.html_pro3.20)

[Problem 3.21 – C](#part0017_split_005.html_pro3.21)

[Problem 3.22 – C](#part0017_split_005.html_pro3.22)

[Problem 3.23 – B](#part0017_split_005.html_pro3.23)

[Problem 3.24 – A](#part0017_split_005.html_pro3.24)

[Problem 3.25 – B](#part0017_split_005.html_pro3.25)

[Problem 3.26 – ABE](#part0017_split_005.html_pro3.26)

[Problem 3.27 – C](#part0017_split_005.html_pro3.27)

[Problem 3.28 – B](#part0017_split_005.html_pro3.28)

[Problem 3.29 – CD](#part0017_split_005.html_pro3.29)

[Problem 3.30 – B](#part0017_split_005.html_pro3.30)

[Problem 3.31 – C](#part0017_split_005.html_pro3.31)

[Problem 3.32 – BE](#part0017_split_005.html_pro3.32)

[Problem 3.33 – C](#part0017_split_005.html_pro3.33)

[Problem 4.1 – B](#part0018_split_002.html_pro4.1)

[Problem 4.2 – A](#part0018_split_002.html_pro4.2)

[Problem 4.3 – C](#part0018_split_002.html_pro4.3)

[Problem 4.4 – D](#part0018_split_002.html_pro4.4)

[Problem 4.5 – B](#part0018_split_002.html_pro4.5)

[Problem 4.6 – D](#part0018_split_002.html_pro4.6)

[Problem 4.7 – AE](#part0018_split_002.html_pro4.7)

[Problem 4.8 – B](#part0018_split_002.html_pro4.8)

[Problem 4.9 – BD](#part0018_split_002.html_pro4.9)

[Problem 4.10 – AC](#part0018_split_002.html_pro4.10)

[Problem 4.11 – D](#part0018_split_002.html_pro4.11)

[Problem 4.12 – AD](#part0018_split_002.html_pro4.12)

[Problem 4.13 – CE](#part0018_split_002.html_pro4.13)

[Problem 4.14 – B](#part0018_split_003.html_pro4.14)

[Problem 4.15 – C](#part0018_split_003.html_pro4.15)

[Problem 4.16 – A](#part0018_split_003.html_pro4.16)

[Problem 5.1 – ABCE](#part0019_split_002.html_pro5.1)

[Problem 5.2 – B](#part0019_split_002.html_pro5.2)

[Problem 5.3 – B](#part0019_split_002.html_pro5.3)

[Problem 5.4 – A](#part0019_split_002.html_pro5.4)

[Problem 5.5 – BD](#part0019_split_002.html_pro5.5)

[Problem 5.6 – C](#part0019_split_002.html_pro5.6)

[Problem 5.7 – C](#part0019_split_002.html_pro5.7)

[Problem 5.8 – B](#part0019_split_002.html_pro5.8)

[Problem 5.9 – BE](#part0019_split_002.html_pro5.9)

[Problem 5.10 – A](#part0019_split_002.html_pro5.10)

[Problem 5.11 – C](#part0019_split_002.html_pro5.11)

[Problem 5.12 – D](#part0019_split_002.html_pro5.12)

[Problem 5.13 – C](#part0019_split_002.html_pro5.13)

[Problem 5.14 – B](#part0019_split_002.html_pro5.14)

[Problem 5.15 – B](#part0019_split_002.html_pro5.15)

[Problem 5.16 – C](#part0019_split_002.html_pro5.16)

[Problem 5.17 – D](#part0019_split_002.html_pro5.17)

[Problem 5.18 – A](#part0019_split_002.html_pro5.18)

[Problem 5.19 – C](#part0019_split_002.html_pro5.19)

[Problem 5.20 – D](#part0019_split_002.html_pro5.20)

[Problem 5.21 – A](#part0019_split_002.html_pro5.21)

[Problem 5.22 – B](#part0019_split_002.html_pro5.22)

[Problem 5.23 – C](#part0019_split_002.html_pro5.23)

[Problem 5.24 – A](#part0019_split_002.html_pro5.24)

[Problem 5.25 – E](#part0019_split_002.html_pro5.25)

[Problem 6.1 – DGH](#part0020_split_006.html_pro6.1)

[Problem 6.2 – C](#part0020_split_006.html_pro6.2)

[Problem 6.3 – B](#part0020_split_006.html_pro6.3)

[Problem 6.4 – A](#part0020_split_006.html_pro6.4)

[Problem 6.5 – A](#part0020_split_006.html_pro6.5)

[Problem 6.6 – B](#part0020_split_006.html_pro6.6)

[Problem 6.7 – C](#part0020_split_006.html_pro6.7)

[Problem 6.8 – D](#part0020_split_006.html_pro6.8)

[Problem 6.9 – AD](#part0020_split_006.html_pro6.9)

[Problem 6.10 – C](#part0020_split_006.html_pro6.10)

[Problem 6.11 – B](#part0020_split_006.html_pro6.11)

[Problem 6.12 – B](#part0020_split_006.html_pro6.12)

[Problem 6.13 – D](#part0020_split_006.html_pro6.13)

[Problem 6.14 – B](#part0020_split_006.html_pro6.14)

[Problem 6.15 – B](#part0020_split_006.html_pro6.15)

[Problem 6.16 – B](#part0020_split_006.html_pro6.16)

[Problem 6.17 – A](#part0020_split_006.html_pro6.17)

[Problem 6.18 – D](#part0020_split_006.html_pro6.18)

[Problem 6.19 – BF](#part0020_split_006.html_pro6.19)

[Problem 6.20 – BE](#part0020_split_006.html_pro6.20)

[Problem 6.21 – DEF](#part0020_split_006.html_pro6.21)

[Problem 6.22 – A](#part0020_split_006.html_pro6.22)

[Problem 6.23 – B](#part0020_split_006.html_pro6.23)

[Problem 6.24 – D](#part0020_split_006.html_pro6.24)

[Problem 6.25 – A](#part0020_split_006.html_pro6.25)

[Problem 6.26 – A](#part0020_split_006.html_pro6.26)

[Problem 6.27 – C](#part0020_split_006.html_pro6.27)

[Problem 6.28 – C](#part0020_split_006.html_pro6.28)

[Problem 6.29 – C](#part0020_split_006.html_pro6.29)

[Problem 6.30 – D](#part0020_split_006.html_pro6.30)

[Problem 6.31 – CE](#part0020_split_006.html_pro6.31)

[Problem 6.32 – A](#part0020_split_006.html_pro6.32)

[Problem 6.33 – D](#part0020_split_006.html_pro6.33)

[Problem 6.34 – B](#part0020_split_006.html_pro6.34)

[Problem 6.35 – B](#part0020_split_006.html_pro6.35)

[Problem 6.36 – E](#part0020_split_006.html_pro6.36)

[Problem 7.1 – B](#part0021_split_010.html_pro7.1)

[Problem 7.2 – AD](#part0021_split_010.html_pro7.2)

[Problem 7.3 – CE](#part0021_split_010.html_pro7.3)

[Problem 7.4 – A](#part0021_split_010.html_pro7.4)

[Problem 7.5 – A](#part0021_split_010.html_pro7.5)

[Problem 7.6 – C](#part0021_split_010.html_pro7.6)

[Problem 7.7 – C](#part0021_split_010.html_pro7.7)

[Problem 7.8 – A](#part0021_split_010.html_pro7.8)

[Problem 7.9 – A](#part0021_split_010.html_pro7.9)

[Problem 7.10 – A](#part0021_split_010.html_pro7.10)

[Problem 7.11 – ACD](#part0021_split_010.html_pro7.11)

[Problem 7.12 – C](#part0021_split_010.html_pro7.12)

[Problem 7.13 – C](#part0021_split_010.html_pro7.13)

[Problem 7.14 – E](#part0021_split_010.html_pro7.14)

[Problem 7.15 – CDF](#part0021_split_010.html_pro7.15)

[Problem 7.16 – D](#part0021_split_010.html_pro7.16)

[Problem 7.17 – ADE](#part0021_split_010.html_pro7.17)

[Problem 7.18 – ABCE](#part0021_split_011.html_pro7.18)

[Problem 7.19 – D](#part0021_split_011.html_pro7.19)

[Problem 7.20 – CD](#part0021_split_011.html_pro7.20)

[Problem 7.21 – E](#part0021_split_011.html_pro7.21)

[Problem 7.22 – B](#part0021_split_011.html_pro7.22)

[Problem 7.23 – D](#part0021_split_011.html_pro7.23)

[Problem 7.24 – F](#part0021_split_011.html_pro7.24)

[Problem 7.25 – CE](#part0021_split_011.html_pro7.25)

[Problem 7.26 – CD](#part0021_split_011.html_pro7.26)

[Problem 7.27 – A](#part0021_split_011.html_pro7.27)

[Problem 7.28 – DE](#part0021_split_011.html_pro7.28)

[Problem 7.29 – E](#part0021_split_011.html_pro7.29)

[Problem 7.30 – AE](#part0021_split_011.html_pro7.30)

[Problem 7.31 – D](#part0021_split_011.html_pro7.31)

[Problem 7.32 – BD](#part0021_split_011.html_pro7.32)

[Problem 7.33 – C](#part0021_split_011.html_pro7.33)

[Problem 7.34 – B](#part0021_split_011.html_pro7.34)

[Problem 8.1 – B](#part0022_split_002.html_pro8.1)

[Problem 8.2 – CD](#part0022_split_002.html_pro8.2)

[Problem 8.3 – C](#part0022_split_002.html_pro8.3)

[Problem 8.4 – CD](#part0022_split_002.html_pro8.4)

[Problem 8.5 – ACE](#part0022_split_002.html_pro8.5)

[Problem 8.6 – AC](#part0022_split_002.html_pro8.6)

[Problem 8.7 – ACD](#part0022_split_002.html_pro8.7)

[Problem 8.8 – C](#part0022_split_002.html_pro8.8)

[Problem 8.9 – D](#part0022_split_002.html_pro8.9)

[Problem 8.10 – A](#part0022_split_002.html_pro8.10)

[Problem 8.11 – C](#part0022_split_002.html_pro8.11)

[Problem 8.12 – BDE](#part0022_split_002.html_pro8.12)

[Problem 8.13 – C](#part0022_split_002.html_pro8.13)

[Problem 8.14 – D](#part0022_split_002.html_pro8.14)

[Problem 8.15 – AD](#part0022_split_002.html_pro8.15)

[Problem 8.16 – C](#part0022_split_002.html_pro8.16)

[Problem 8.17 – D](#part0022_split_002.html_pro8.17)

[Problem 8.18 – E](#part0022_split_002.html_pro8.18)

[Problem 8.19 – C](#part0022_split_002.html_pro8.19)

[Problem 8.20 – CEFG](#part0022_split_002.html_pro8.20)

[Problem 8.21 – D](#part0022_split_002.html_pro8.21)

[Problem 8.22 – AE](#part0022_split_002.html_pro8.22)

[Problem 9.1 – D](#part0023_split_008.html_pro9.1)

[Problem 9.2 – D](#part0023_split_008.html_pro9.2)

[Problem 9.3 – A](#part0023_split_008.html_pro9.3)

[Problem 9.4 – C](#part0023_split_008.html_pro9.4)

[Problem 9.5 – BE](#part0023_split_008.html_pro9.5)

[Problem 9.6 – D](#part0023_split_008.html_pro9.6)

[Problem 9.7 – AD](#part0023_split_008.html_pro9.7)

[Problem 9.8 – C](#part0023_split_008.html_pro9.8)

[Problem 9.9 – C](#part0023_split_008.html_pro9.9)

[Problem 9.10 – D](#part0023_split_008.html_pro9.10)

[Problem 9.11 – B](#part0023_split_008.html_pro9.11)

[Problem 9.12 – D](#part0023_split_008.html_pro9.12)

[Problem 9.13 – B](#part0023_split_008.html_pro9.13)

[Problem 9.14 – C](#part0023_split_008.html_pro9.14)

[Problem 9.15 – D](#part0023_split_008.html_pro9.15)

[Problem 9.16 – C](#part0023_split_008.html_pro9.16)

[Problem 9.17 – E](#part0023_split_008.html_pro9.17)

[Problem 9.18 – B](#part0023_split_008.html_pro9.18)

[Problem 9.19 – B](#part0023_split_008.html_pro9.19)

[Problem 9.20 – B](#part0023_split_008.html_pro9.20)

[Problem 9.21 – C](#part0023_split_008.html_pro9.21)

[Problem 9.22 – A](#part0023_split_008.html_pro9.22)

[Problem 9.23 – C](#part0023_split_008.html_pro9.23)

[Problem 9.24 – B](#part0023_split_008.html_pro9.24)

[Problem 9.25 – A](#part0023_split_008.html_pro9.25)

[Problem 9.26 – C](#part0023_split_008.html_pro9.26)

[Problem 9.27 – D](#part0023_split_008.html_pro9.27)

[Problem 9.28 – D](#part0023_split_008.html_pro9.28)

[Problem 9.29 – AD](#part0023_split_008.html_pro9.29)

[Problem 9.30 – A](#part0023_split_008.html_pro9.30)

[Problem 9.31 – AD](#part0023_split_008.html_pro9.31)

[Problem 9.32 – A](#part0023_split_008.html_pro9.32)

[Problem 9.33 – AF](#part0023_split_008.html_pro9.33)

[Problem 9.34 – E](#part0023_split_008.html_pro9.34)

[Problem 9.35 – B](#part0023_split_008.html_pro9.35)

[Problem 9.36 – B](#part0023_split_008.html_pro9.36)

[Problem 9.37 – A](#part0023_split_008.html_pro9.37)

[Problem 9.38 – C](#part0023_split_008.html_pro9.38)

[Problem 9.39 – C](#part0023_split_008.html_pro9.39)

[Problem 9.40 – BC](#part0023_split_008.html_pro9.40)

[Problem 9.41 – AE](#part0023_split_008.html_pro9.41)

[Problem 9.42 – D](#part0023_split_008.html_pro9.42)

[Problem 9.43 – E](#part0023_split_008.html_pro9.43)