![](Images/cover00191.jpeg)

![1](Images/image00075.jpeg)

![2](Images/image00076.jpeg)

This edition published in 2020 by Concepts Books Publication (India) Pvt. Ltd.

[www.researchitout.blogspot.com](http://www.researchitout.blogspot.com)

All rights reserved. No part of the publication may be

reproduced, stored in a retrieval system, or transmitted in

any form or by any means, Electronic, Mechanical, Photocopying,

Recording or otherwise, without the prior written permission

of the publisher and copyright holders.

Title: A Study of Java Refactoring Tool as Per OOP.

ISBN: 978-8-19-433581-8

Author: Dr. Ashad Ullah Qureshi& Er. Vivek Soni

Cover: Aman Kashyap

Production at NIT Kurukshetra

![](Images/image00077.jpeg)

ABSTRACT

Object Oriented Programming(OOP) is a contemporary favorite method of programming. OOP provides better flexibility, source codes are more organized and systematized, and it enables a group of developers to easily work with each other. Nevertheless, a poorly designed system will not only defeat the intention of coding with OOP, but also will make the software extremely difficult to maintain. Refactoring is a powerful way to improve existing code. It only changes the structure of the source code without changing its functionality. Manually refactoring larger systems not only consumes large amounts of time and money, but it also happens to be incredibly inaccurate. As a result, quick and easy refactoring with partial automation is extensively discussed in the software realm.

This thesis presents algorithms for implementing nine refactorings that work on the fly for JAVA source code. The refactorings algorithms are implemented in a stepwise manner by initially selecting the source code portion for refactoring, and by choosing the correct refactoring method, and then programmatically changing the selected source code to achieve refactoring.

CONTENTS

Chapter  1.INTRODUCTION                               1 - 4

1.1 Product Perspective

1.2 Motivation

1.3 Objective

1.4 Organization of Dissertation

Chapter  2.REFACTORINGS                               5 - 8

2.1 Introduction

2.2\. Scope of Work

Chapter   3.LITERATURE SURVEY 9 - 13

Chapter4. SIMPLIFYING CONDITIONAL EXPRESSIONS 14 - 26

4.1 Consolidate Conditional Expression

4.2 Structure

4.3 Refactoring Steps

4.4 Consolidate Duplicate Conditional Fragments

4.5 Structure

4.6 Refactoring Steps

4.7 Replace Nested Conditional with Guard Clauses

4.8 Structure

4.9 Refactoring Steps

Chapter  5.DEALING WITH GENERALIZATION 27 – 41

5.1 Pull Up Method

5.2 Structure

5.3 Refactoring Steps

5.4 Pull Up Field

5.6 Refactoring Steps

5.7 Push Down Method

5.8 Structure

5.9 Refactoring Steps

5.10 Push Down Field

5.11 Structure

5.12 Refactoring Steps

Chapter  6. QUICK JAVA REFACTORING TOOL  42 – 54

6.1 User Interaction

6.2 Automatic Refactoring - Data Collection

6.3 Automatic Refactoring – Overview

Chapter 7.RESULTS 55 - 130

7.1\. Sample Input and Validation of Consolidate Conditional Expression

7.2\. Sample Input and Validation of Consolidate Duplicate Conditional Fragments

7.3 Sample Input and Validation of Replace Nested Conditional with guard Clauses

7.4\. Sample Input and Validation of Pull Up Field

7.5\. Sample Input and Validation of Push Down Field

7.6\. Sample Input and Validation of Pull Up Method

7.7\. Sample Input and Validation of Push Down Method

7.8\. Sample Input and Validation of Reverse Conditional

7.9 Sample Input and Validation of Reverse Conditional Advance

Chapter 8CONCLUSION AND FUTURE ENHANCEMENTS 131 - 132

References

CHAPTER 1

![](Images/image00078.jpeg)INTRODUCTION

1.1. Product Perspective

Software maintenance is statistically proven to be expensive and difficult. There  is also a sense that software maintenance is inevit able due to the fact that new  technologies, such as new hardware are constantly being introduced; changes in law and regulations happen regularly business entities are re-organized frequently; and lastly,  customers’ requirements are constantly changing and evolving. According to Martin Fowler [1], “Refactoring is the process of changing a software system in such a way that it does not alter the external behavior of the code yet improves its internal structure.” Additionally, in an article titled “Refactoring-Way for  Software Maintenance”, Arora et al. said that through the practice of refactoring, one can accomplish re-modularization of the software, and make the software system easier to read, to understand, to extend, and to maintain [2]. Many of the refactorings described are common sense programming techniques, such as move field; some refactorings are common software design practice, such as encapsulate field; some refactorings improve readability and maintainability, such as  reverse conditional. As a result, refactoring is all about improving sof tware design and structure.

A poorly designed or engineered software system will cause problems for others. Source code decays over time; particularly, in the year 2000, the infamous Y2K bug drew  worldwide fear and attention for software maintenance.

This thesis describes nine algorithms which implement nine refactorings. A prototype tool named Quick Java Refactoring Tool (QJRT) was created to validate the algorithms.

1.2. Motivation

Software is difficult and costly to change. Large software projects face challenges such as larger development teams, greater scope of software functionality, and competition-driven schedules. These issues often lead to decreased cohesion and increased coupling between classes. The source code grows more difficult to maintain, and the addition of new features becomes increasingly complex. Delegation of programming tasks among programmers is made more difficult by the large number of classes and dependencies between them.

Programming tasks performed by more than one person are also more likely to suffer from inconsistencies in coding style, information-hiding methodology, and naming, which compromises the conceptual integrity of the software product. The intrinsic difficulty of good object-oriented design in complex systems is emphasized by the growing popularity of design patterns, which can impart experience and design knowledge to software designers.

Opdyke proposes that refactoring existing class hierarchies can improve their maintainability and reusability [Opdyke 92, Opdyke & Johnson 90]. A refactoring activity changes the organization of an object oriented program without changing its behavior. It includes changes such as encapsulating public references to member data in a new method or creating abstract superclasses from shared behavior in similar classes. Refactorings can be performed proactively by a programmer to ease upcoming changes or they can

be performed as part of a comprehensive reengineering effort. Opdyke’s automated refactoring tool allows a programmer to guide the automatic refactoring of specific portions of a class hierarchy.

A key problem in refactoring an object-oriented program is first identifying the structural problems with the current design and then exploring the possible solutions. For example, consider a class that consists primarily of public data members. As the application evolves and becomes increasingly complex, a better design for such a class might be to make the member data private and encapsulate the computations on its data members in methods of that class. To get a sense of what the methods of the class should be, a software designer needs to view all the references to the data members and categorize them according to how they are manipulated. However, the uses of the data members are widely distributed throughout the program and interspersed with computations that are unrelated to the class in question, thereby complicating the analysis.

Opdyke’s refactoring tool provides a mechanism for performing automatic meaning-preserving restructurings, but it does not help the programmer decide which restructurings to perform to improve the design.

Categorization of references with a text editor is difficult because each reference is shown only in the context of its use, rather than with the other references to the class. A typical solution to this problem is to use a searching tool like Unix grep, which extracts only those program lines that match a specified pattern.

Although successful in removing unrelated code, it is not capable of matching data references by type, only by name. Also, it does not perform any further categorization of the matched references or suggest which computations on the references belong inside the class and which should remain outside. A design visualization like a class hierarchy diagram or a graphical object model can reveal the high-level aspects of the system’s current design, but it is not possible to use such a view to examine the source code’s latent structure to suggest an appropriate redesign. Finally, in planning a complex redesign, it is desirable to have support for recording the designer’s many discoveries, thoughts, and refactoring plans.

1.3. Objective

As object-oriented software is modified its structure tends to degrade. The potentially large number of classes and the large number of dependencies between them can complicate the analysis and planning needed to maintain a program written in an object-oriented language.

Restructuring software to improve its design can lower the cost of future changes. To ease the task of software restructuring, we describe the application of the star diagram concept to Java programs. The star diagram visualization affords programmers a cross-cutting view of the project source code that can simplify software maintenance tasks by allowing the programmer to rapidly assess complicated class hierarchies and complex class interrelationships. The recording of detailed refactoring tasks to be performed, accompanied by relevant portions of star diagrams for the source code undergoing modification, provides the programmer with a visualization of the work that assists in recall and execution of the software restructuring.

1.4. Organization of Dissertation

Chapter 1 represents & discusses the introduction of the research and the overall research.

Chapter 2 states the refactoring tool & it’s important in Quick Java Refactoring tool.

Chapter 3 represents the literature survey & its extracted related content.

Chapter 4 states the simplifying conditional expression of QJRT.

Chapter 5 represents the dealing with generalization.

Chapter 6 states QJRT in detail.

Chapter 7 discusses the results and conclusion of the research.

![](Images/image00079.jpeg)CHAPTER 2

REFACTORINGS

2.1 Introduction

Refactoring is an important step in software maintenance. The first reason to refactor is that large software usually is developed by many people. Thus, different people usually have different thoughts on how to write the source code even if the project starts with a perfect UML (Unified Modeling Language) class diagram as its blueprint. In addition, software does age, and needs to be taken care of. As Pippin says in an online post, “I get the sense that tells me it is some of the best code I’ve written. It’s better than the code I wrote yesterday, and it’s better than the code I wrote a year ago” [3].

The classic approach to software development is the waterfall model. Let us assume the waterfall model worked great on some projects. However, after a period of time, new technology has been introduced, and the system must keep up in order to use the new technology (e.g., to enhance security). Refactoring comes in handy under such situations. “[It] is the process of changing a software system in such a way that it doesn’t alter the external behavior of the code yet improves its internal structure. [1]”

Refactoring is divided into four procedures: detect a problem, analyze the problem, find a solution, and change the source code accordingly [4]. To detect a problem, Fowler [1] used Bad Smells to refer to source code that can be improved. In order to analyze a problem, a series of questions must be asked, such as: Why is it necessary to change something? What are the benefits? Are there any risks To find a solution to the problem, the goal is eliminating potential bugs; yet, the outcome stays the same. Lastly, the source code must be modified to archive the goal.

Fowler discussed a total 72 refactorings in his book, and later provided a few more on his website [5]. The 72 refactorings are catalogued into seven areas: (1) composing methods; (2) moving features between objects; (3) organizing data; (4) simplifying conditional expressions; (5) making method calls simpler; (6) dealing with generalization; (7) big refactorings [1].

2.2\. Scope of Work

The scope of this thesis is limited to describing nine algorithms for implementing nine refactorings and developing a tool (QJRT) in the process. Those nine refactorings are categorized under three areas as follows:

1\. Simplifying Conditional Expressions: Consolidate Conditional Expression (CCE) refactoring combines a sequence of conditional tests into a single conditional expression and extract it. Consolidate Duplicate Conditional Fragments (CDCF) refactoring moves the same fragment of code outside of the expression. Replace Nested Conditional with Guard Clauses (RNCGC) refactoring uses guard clauses for special cases and make clear the normal path of execution.

2\. Dealing with Generalization: Pull Up Method (PUM) refactoring moves the specific methods with identical results from subclasses to the superclass. Pull Up Field (PUF) refactoring moves the specific identical field from subclasses to the superclass. Push Down Method (PDM) refactoring moves a specific method from the superclass to the only subclass in which the method makes sense. Push Down Field (PDF) refactoring moves a specific field from superclass to a subclass, in which the field is only used.

3\. Others / Miscellaneous: Reverse Conditional (RC) refactoring makes negative conditional positive. Reverse Conditional Advance (RCA) refactoring changes the conditional to the opposite meaning. All of them are described by Fowler [1], and later on Bill Murphy [5] and others’ works were added to Fowler’s refactoring website [1, 5]. Every refactoring is defined, and is followed by a sample of how the refactoring should be done in a manual fashion. QJRT provides quick and easy refactoring with knowledge of programming, which includes finding a bad smell, analyzing the problem, and then choosing the correct refactoring. The QJRT changes the source code for the developer on the spot, and the developer can verify the outcome of the finished code right away.

![](Images/image00080.jpeg)CHAPTER 3

LITERATURE SURVEY

[1] Emal Nasseri ;  Steve Counsell “An Empirical Study of Java System Evolution at the Method Level”. IEEE 2010 Proceedings.

Exploring the evolution of systems can provide valuable insights into the traits of developers and inform our understanding of system dynamics. While we usually expect an object-oriented system to grow (in classes) as it ages, what are not so obvious are patterns in the evolution of specific class features. In this paper, we explore empirical traits of four Java open-source systems using data extracted by two tools and informed by a previous study of inheritance depth evolution. We analyse evolution at a lower level of granularity given by the ‘methods’ of a class on an incremental (change per version) basis rather than absolute class size per version. Evolution at a finer-grain can identify trends not possible on a class-wide basis; the approach thus represents a ‘white-box’ view of the investigation of evolutionary forces. Our analysis also allowed direct comparison with a set of low-level refactorings extracted by an automated tool in a previous study. Scrutiny of trends in methods was further motivated by the fact that the vast majority of refactorings apply not at the class level but at the method level.

[2] Kozo Okano ;  Satoshi Harauchi ;  Toshifusa Sekizawa ;  Shinpei Ogata ;  Shin Nakashima "Equivalence Checking of Java Methods: Toward Ensuring IoT Dependability”. IEEE 2017 Proceedings.

IoT devices are software-rich and Java is sometimes chosen as the developing programming language. Although Java is highly productive in constructing large advanced programs, application or user-defined Java classes must be responsible for safety and security issues. In particular, two fundamental methods hashCode and equals play key roles in safety and security assurance. Some existing studies for ensuring the correctness of these two methods rely on static analysis, which are limited to loop-free programs only. This paper proposes a new solution to this important problem, based on equivalence checking of methods or functions. The proposed approach makes use of software analysis workbench (SAW), an open source tool. The approach is also useful in reducing the cost of regression testing when program refactoring is conducted.

[3] Gleison Brito ;  Andre Hora ;  Marco Tulio Valente ;  Romain Robbes "Do Developers Deprecate APIs with Replacement Messages? A Large-Scale Analysis on Java Systems”. IEEE 2016 Proceedings.

As any other software system, frameworks and libraries evolve over time, and so their APIs. Consequently, client systems should be updated to benefit from improved APIs. To facilitate this task and preserve backward compatibility, API elements should always be deprecated with clear replacement messages. However, in practice, there are evidences that API elements are usually deprecated without such messages. In this paper, we study a set of questions regarding the adoption of deprecation messages. Our goal is twofold: to measure the usage of deprecation messages and to investigate whether a tool is needed to recommend such messages.

[4] Jiachen Yang ;  Keisuke Hotta ;  Yoshiki Higo ;  Shinji Kusumoto"Towards purity-guided refactoring in Java”. IEEE 2015 Proceedings.

Refactoring source code requires preserving a certain level of semantic behaviors, which are difficult to be checked by IDEs. Therefore, IDEs generally check syntactic pre-conditions instead before applying refactoring, which are often too restrictive than checking semantic behaviors. On the other hand, there are pure functions in the source code that do not have observable side-effects, of which semantic behaviors are more easily to be checked. In this research, we propose purity-guided refactoring, which applies high-level refactoring such as memoization on pure functions that can be detected statically.

[5] Hitesh Sajnani ;  Vaibhav Saini ;  Cristina V. Lopes"A Comparative Study of Bug Patterns in Java Cloned and Non-cloned Code”. IEEE 2014 Proceedings.

Code cloning via copy-and-paste is a common practice in software engineering. Traditionally, this practice has been considered harmful, and a symptom that some important design abstraction is being ignored. As such, many previous studies suggest approaches to facilitate the discovery, removal, and refactoring of clones. However, not many studies exist that empirically investigate the relationship of code clones with code quality. In this paper, we conduct an empirical study of 31 open source Java projects (1.7 MSLOC) to explore the relationship between code clones and a set of bug patterns reported by Find Bugs. We found that: (i) the defect density in cloned code is 3.7 times less than that of the rest of the code, (ii) 66% of the bug patterns associated with code clones are related to issues in coding style and practice, the two least problematic of the Find Bugs' categories, while that number is 49% for non-cloned code, and (iii) 75% of the bug patterns in cloned code are duplicated without any changes, while 25% are only present in one of the clones. These results show that, when using Find Bugs to detect bug patterns, there is a positive differentiation of cloned code with respect to the rest of the code: the cloned code has considerably less, and less problematic, bug patterns.

![](Images/image00081.jpeg)CHAPTER 4

SIMPLIFYING CONDITIONAL EXPRESSIONS

This section describes the algorithm for applying refactorings that simplify conditional expressions. The refactorings included in this section are Consolidate Conditional Expression (CCE), Consolidate Duplicate Conditional Fragments (CDCF), and Replace Nested Conditional with Guard Clauses (RNCGC).

As Martin Fowler[1] pointed out in his book, the conditional expressions have their own ways of getting logically tricky. The goal is to change the conditional expressions for better readability, while not changing the meaning of the expressions, after all, that is what refactoring is for.

CCE would be used when running multiple different if-statements’ tests, no matter what the tests are, the results from the different if-statements would return the same. CDCF is applied to remove any duplicated codes within if-statement’s body. RNCGC is used while an if-statement has nested conditionals, usually more than three nested level, where the codes are hard to read. Based on developer’s preference, one or more of these three techniques can be applied to make the code more readable and tricky logic more understandable.

4.1   Consolidate Conditional Expression

The CCE basically involves combining all of the conditional expressions into one conditional expression. It results in less coding and better understanding. In addition, this step of refactoring makes the code highly cohesive.

4.2    Structure

![FIG 1.PNG](Images/image00082.jpeg)

FIGURE 1\. Consolidate Conditional Expression [1].

4.3    Refactoring Steps

1\. Developer opens the file from the File menu; the file’s entire source code will be loaded in the left panel of the QJRT, and highlights the portion of the code s/he wants to refactor.

2\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

3\. Developer chooses the Consolidate Conditional Expression refactoring from the drop-down menu bar under Refactoring menu.

4\. Upon choosing the refactoring method, QJRT displays CCE refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare CCE refactoring. And lastly, it sets the Refactoring button visible for user to click on.

5\. User clicks Refactoring button, and this is where all the wonderful mechanics happen. QJRT takes the selected source code from the bottom panel, uses Abstract Syntax Tree (AST) to parse it. In detail, AST checks if the selected source codes are multiple if-statements. If all of them are valid if-statements, then AST checks individual if-statement, and CCE compares then- and else- Statement. If all then Statements are same; meanwhile, all else Statements are same; CCE will retrieve all expressions and constructs a new if-statement.

6\. After the above step is completed in the background, the new and improved source code shows on the right panel of QJRT. The original source code is replaced with the refactored source code in the color red with highlights in yellow to show the difference. The unchanged source codes are still in black color. The left side panel with the original source codes remains the same.

7\. Now, the developer has the option of saving the refactored source code. S/he simply clicks File menu, chooses the option “save as …” to save to a new file or to overwrite the old one. Nonetheless, if there are doubts, the developer can simply cancel or exit the whole process. An example of this refactoring is presented in Chapter 8 under heading “Sample Input and Validating of Consolidate Conditional Expression.

4.4  Consolidate Duplicate Conditional Fragments

CCE refactoring improves the source code for better readability and makes it more straightforward by combining the conditional expressions. Moreover, according to Folwer, CCE is important for two reasons. “First, it makes the check clearer by showing that you are really making a single check that’s or’ing the other checks together. The sequence has the same effect, but it communicates carrying out a sequence of separate checks that just happen to be done together. The second reason [...] is that it often sets you up for Extract Method” [1]. Similarly, the CDCF refactoring method eliminates the same fragment code showing all over inside the body of the if-statement. In other words, CDCF extracts the same fragments of code out for individual standing. This improves source code for better readability, and clarifies logically what changes and what does not.

4.5   Structure

![FIG 2.PNG](Images/image00083.jpeg)

FIGURE 2\. Consolidate Duplicate Conditional Fragments [1].

4.6     Refactoring Steps

1\. As usual developer opens the file from the File menu, and highlights the portion of the code s/he wants to refactor from the chosen file.

2\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

3\. Developer chooses the Consolidate Duplicate Conditional Fragments refactoring from the drop-down menu bar under Refactoring menu.

4\. Upon choosing the refactoring method, QJRT displays CDCF refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare CDCF refactoring. And lastly, it sets the Refactoring button visible for user to click on.

5\. Developer clicks Refactoring button, and QJRT takes the selected source code from the bottom panel and uses AST to parse it. AST verifies the selected code is valid if-statement, and also verifies there are any identical fragment in the thenStatement and elseStatement. Next step is QJRT determines the identical fragments’ position. If the position matches, for example, both of them are at the beginning of the statement block; or at the end of the statement block. Then, CDCF extracts the identical fragment out, and put it either in front or at the end of the if-statement according to the position of the fragment.

6\. After the refactorings are completed in the background, the new and improved source code shows on the right panel of QJRT. The original source code is replaced with the refactored source code in the color red with highlights in yellow to show the difference. The unchanged source codes are still in black color. The left side panel with the original source codes remains the same.

7\. Developer now has the option to save the refactored source code to a new file, or to overwrite the old one. S/he simply clicks File menu and from the drop-down menu, choose option “save as …” to save the file or file the old one to replace. Nonetheless, if there are doubts, developer can simply cancel or exit the whole process before the step to overwrite the original file. An example of this refactoring is presented in Chapter 8 under the heading “Sample Input and Validation of Consolidate Duplicate Conditional Fragments.”

4.7    Replace Nested Conditional with Guard Clauses

RNCGC is used to re-arrange one normal condition per if-statement to the readers while eliminating the nested conditional. This action will make the codes look clean, as well as make the code logic easy to understand. Many software developers, including myself, intend to use many nested if-statements when deciding an outcome of a result. The way of using the nest if-statements is not illegal, but it certainly can be treated as insufficient, or in other words, very poorly designed. “If the method is clearer with one exit point, use one exit point; otherwise don’t.” [1]

4.8    Structure

![FIG 3.PNG](Images/image00084.jpeg)

FIGURE 3\. Replace Nested Conditional with Guard  Clauses [1].

4.9    Refactoring Steps

1\. Developer opens the file from the File menu, and highlights the portion of the code s/he wants to refactor from the chosen file.

2\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

3\. Developer chooses Replace Nested Conditional with Guard Clauses refactoring from the drop-down menu bar under Refactoring menu.

4\. Upon choosing the refactoring method, QJRT displays RNCGC refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare RNCGC refactoring. And lastly, it sets the Refactoring button visible for user to click on.

5\. Developer clicks Refactoring button, QJRT takes the selected source code from the bottom panel, uses AST to parse it. In detail, AST checks if the selected source code is valid if-statement. Then from the top level if-statement down to inner level ifstatement, RNCGC spins off a new if-statement constructed with expression and then Statement.

6\. After the refactorings are completed in the background, the new and improved source code shows on the right panel of QJRT. The original source code is replaced with the refactored source code in the color red with highlights in yellow to show the difference. The other unchanged source codes are still in black color. The left side panel with the original source codes remains the same.

7\. Developer now has the option to save the improved source code to a new file, or to overwrite the old one. S/he simply clicks File, and from the drop-down menu, choose option “save as …” to save the file or file the old one to replace. However, if there are doubts, developer can simply cancel or exit the whole process before the step to overwrite the original file. An example of this refactoring is presented in Chapter 8 under heading “Sample Input and Validation of Replace Nested Conditional with Guard Clause.”

![](Images/image00085.jpeg)CHAPTER 5

DEALING WITH GENERALIZATION

This section includes refactorings that work around a hierarchy of inheritance, moving fields or methods up and down between classes.

5\. 1\. Pull Up Method

The definition of Pull Up Method is to move the same function source code from two subclasses to the superclass. Similar to Pull Up Field, the motivation of this refactoring method is to eliminate duplicate source code in all subclasses. Furthermore, the benefit of this refactoring method is that developer can reduce the risk of changing only one method while not changing the others. It is easy to miss the duplicate method at subclass level, especially when the subclasses are developed by different people. The refactoring method is generally used when a method needs to be used by multiple implemented subclasses.

5.2\. Structure

![](Images/image00086.jpeg)

FIGURE 4\. Pull Up Method [1]

5.3\. Refactoring Steps

1\. Developer chooses a subclass from the File menu, and highlights the complete method source code s/he wants to pull up to the superclass.

2\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

3\. Developer chooses Pull Up Method refactoring from the drop-down menu bar under Refactoring menu.

4\. Upon choosing the refactoring method, QJRT displays PUM refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare PUM refactoring. And lastly, it sets the Refactoring button visible for user to click on.

5\. Developer clicks Refactoring button, and QJRT takes the selected source code from the bottom panel and uses ASTParser to parse it. The first step is to check if the selected methods’ class has a superclass, which is done through analysis of the AST. Then, PUM verifies if the selected code is a valid method, which should have basic method signature, includes following key elements: modifiers, return type, method name, parameter list in parenthesis, an exception list, and method body. PUM extracts value of those elements from AST, and temporarily save in memory. Then, QJRT finds the root of the chosen file (based on current file location); following the root path, QJRT discovers all Java files under root, and saves file name and location into an Array List. Next, QJRT parses each file by AST Parser to locate current file’s superclass, and all related subclasses. The final step is to add the selected method to the superclass, while removing the same methods from all the subclasses.

6\. After refactoring is complete, QJRT pops up a question window that gives the developer the option to view the modified files and the original files with the default notepad program.

7\. In addition, on the right panel of the QJRT, it reflects the changes that have been made to the current class. The bottom panel shows all the location of the affected super- and subclasses. An example of this refactoring is presented in chapter 8 under heading “Sample Input and Validation of Pull Up Method.”

5.4\. Pull Up Field

The definition of PUF is to move a field from any subclasses to the superclass. Mostly, the pull up field refactoring won’t be applied when the source code was written by an individual, but as Fowler[1] mentioned, pull up field is used when the subclasses are built separately by different developers, or the subclasses are combined through refactoring. From combining the classes to a package, subclasses mostly do have duplicate features, and having identical fields is just one of the duplicate features.

The benefit of PUF eliminates the duplicate data declaration; moreover, while this action moves the field behavior from subclasses to superclass, similar to pull up method, it reduces the risk of changing only one field while not changing the others.

5.5. Structure

![](Images/image00087.jpeg)

FIGURE 5\. Pull Up Field [1].

5.6\. Refactoring Steps

1\. Developer chooses a subclass that contains the field s/he wants to move to the super class from the File menu, and then highlights the individual field.

2\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

3\. Developer chooses Pull Up Field method from the drop-down menu bar under Refactoring menu.

4\. Upon choosing the refactoring method, QJRT displays PUF refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare PUF refactoring. And lastly, it sets the Refactoring button visible for user to click on.

5\. Developer then clicks Refactoring button, and QJRT takes the selected field from the bottom panel and uses ASTParser to parse it. The first step is to check if the selected field’s class has a superclass, which is done through analysis of the AST. Then, PUF verifies if the selected code is a valid field, which should have basic field signature, includes following key elements: modifiers, type, field name, expression. PUF extracts value of those elements from AST, and temporarily save in memory. The following step is to construct a new field with these key elements, one extra step PUF will do is to change “private” to “protected” in modifier: this new field will be saved temporarily and be extracted to superclass. Then, QJRT finds the root of the chosen file (based on current file location); following the root path, QJRT discovers all Java files under root, and saves file name and location into an ArrayList. Next, QJRT parses each file by ASTParser to locate current file’s superclass, and all related subclasses. The final step is to add the new constructed field to the superclass, while removing the same field from all the subclasses.

6\. After refactoring is complete, QJRT pops up a question window that gives the developer the option to view the modified and original files with the default notepad program.

7\. In addition, on the right panel of the QJRT, it reflects the changes that have been made to the current class. The bottom panel shows the locations of the original and modified files. An example of this refactoring is presented in Chapter 8 under heading “Sample Input and Validation of Pull Up Field.”

5.7\. Push Down Method

PDM is the opposite of PUM. The definition is to move the same function source code from a superclass to a specific subclass. Similar to Push Down Field, the motivation is to eliminate source code in a superclass, since only one subclass implements it; in other words, the method only makes sense in the specific subclass, yet it is declared in the superclass. Furthermore, the Push Down Method makes the subclass highly cohesive, and in general makes the entire software more well designed.

5.8. Structure

![](Images/image00088.jpeg)

FIGURE 6\. Push Down Method [1].

5.9\. Refactoring Steps

1\. Developer chooses a class from the File menu, and highlights the complete method source code s/he wants to push down to the subclass.

2\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

3\. Developer chooses Push Down Method from the drop-down menu bar under Refactoring menu.

4\. Upon choosing the refactoring method, QJRT displays PDM refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare PDM refactoring. And lastly, it sets the Refactoring button visible for user to click on.

5\. Developer clicks Refactoring button, and QJRT takes the selected source code from the bottom panel and uses ASTParser to parse it. The first step is PDM verifies if the selected code is a valid method, which should have basic method signature, includes following key elements: modifiers, return type, method name, parameter list in parenthesis, an exception list, and method body. PDM extracts value of those elements from AST, and temporarily save in memory. Then, QJRT finds the root of the chosen file (based on current file location); following the root path, QJRT discovers all Java files under root, and saves file name and location into an ArrayList. Next, QJRT parses each file by ASTParser to locate current file’s all subclasses. The final step is to add the selected method to the subclasses, while removing the same methods from superclass.

6\. After refactoring is complete, QJRT pops up a question window that gives the developer the option to view the modified and the original files with the default notepad program.

7\. In addition, on QJRT’s right side panel, it presents the changes that have been made to the current class. The bottom panel clears the selected method, and updates the location of affected super- and subclasses. An example of Push Down Refactoring is presented in Chapter 8 under heading “Sample Input and Validation of Push Down Method.”

8\. PDM requires user intervention: User is required to review and manually delete the unwanted method in subclasses.

5.10\. Push Down Field

PDF is the opposite of PUF. The definition of PDF is to move a field from a superclass to a subclass. Similar to Push Down Method, the motivation is the field in the superclass does not make sense in some subclasses at all; in other words, the specific field makes sense only in one of the subclasses. Thus, there is no reason to keep the field in the superclass. The benefit is less coding on superclass, and a highly cohesive method of design on subclass.

5.11. Structure

![](Images/image00089.jpeg)

FIGURE 7\. Push Down Field [1].

5.12\. Refactoring Steps

1\. User clicks Select button, and QJRT extracts the selected code to the bottom panel for individual analysis.

2\. Developer chooses Push Down Field refactoring from the drop-down menu bar under Refactoring menu.

3\. Upon choosing the refactoring method, QJRT displays PDF refactoring on a message label to present and confirm which refactoring is being executed. It also passes the parameter to QJRT to prepare PDF refactoring. And lastly, it sets the Refactoring button visible for user to click on.

4\. Developer then clicks Refactoring button, and QJRT takes the selected field from the bottom panel and uses ASTParser to parse it. The first step is PDF verifies if the selected code is a valid field, which should have basic field signature, includes following key elements: modifiers, type, field name, expression. PDF extracts value of thoseelements from AST, and temporarily save in memory. The following step is to  construct a new field with these key elements: this new field will be saved temporarily and be extracted to subclasses. Then, QJRT finds the root of the chosen file (based on current file location); following the root path, QJRT discovers all Java files under root, and saves file name and location into an ArrayList. Next, QJRT parses each file by ASTParser to locate current file’s all subclasses. The final step is to add the new constructed field to the all subclasses, while removing the same field from the superclass.

5\. After refactoring is complete. QJRT pops up a question window giving the developer the option to view the modified and the original files with the default notepad program.

6\. In addition, on the right panel of the QJRT, it reflects the changes that have been made to the current selected class. The bottom panel now shows the locations of the original and the modified affected class fields. An example of Push Down Field refactoring is presented in Chapter 8 under the heading “Sample Input and Validation of Push Down Field.”

7\. PDF requires user intervention: user is required to review and manually delete the unwanted field in subclasses.

![](Images/image00090.jpeg)CHAPTER 6

QUICK JAVA REFACTORING TOOL

Quick Java Refactoring Tool (QJRT) is a portable program performed on individual refactoring. Each refactoring section is divided into two parts. First is user interactions, and the other is refactoring.

The user interaction section includes opening the file, selecting the code, and choosing the refactoring method. The refactoring section includes two modules, one is parsing and data collection, and the other is re-constructing and generating new code. The first module is parsing the selected code, collecting related data and saving the information to memory; this module also handles all the errors. Second module is to reconstruct the source code. This section runs automatically at the background once it’s been kicked off, and it will save new code to memory or a new file.

6.1\. User Interaction

QJRT is designed with minimal user input to refactor Java code. The GUI (graphical user interface) includes a menu bar, a tool bar, and three blank text areas: two text areas are on the top side by side and another area on the bottom alone. The tool bar resides between the top and bottom text areas. A message label is also included within the tool bar for showing which refactoring is in selected, and it is only visible while the refactoring is in process.

![](Images/image00091.jpeg)

FIGURE 10\. Initial screen of QJRT.

Initial screen of QJRT contains of a menu bar and a tool bar. The menu bar contains two menu items, one is File and another is Refactoring Method. Tool bar has select, cancel, refactoring, and exit buttons. The Refactoring button is disabled initially, and it will be available upon a refactoring method is chosen by user.

![](Images/image00092.jpeg)

FIGURE 11\. Refactoring Method menu options in QJRT.

The Figure 11 shows the refactoring methods implemented in QJRT. Upon user selecting a refactoring method from this menu, it passes the parameters to QJRT to prepare the current refactoring.

![](Images/image00093.jpeg)

FIGURE 12\. Initial text area for original code viewer in QJRT.

QJRT uses window’s open file dialogue box to let developer choose Java file to open. The upper left text area is used for displaying Java code contained in the file (shown in figure 12). The code is taken in by QJRT as string in local memory. Developer then highlights the targeted code. Upon clicking Select button, the highlighted code is copied to the bottom text area (shown in figure 13). After choosing the correct refactoring method, the refactoring button is enabled (shown in figure 11) and user then clicks this button to initialize refactoring process. At this point, the user interaction is finished.

![](Images/image00094.jpeg)

FIGURE 13\. Highlighting and selecting targeted code to bottom text area.

6.2\. Automatic Refactoring - Data Collection

The first module is for parsing the selected code. QJRT uses eclipse’s AST (Abstract Syntax Tree) [5] as a library plugin, and uses AST to parse the code. The ASTParser is used for every refactoring. In detail, if the selected source code is a method or a field, K_COMPILATION_UNIT is used to parse; if the selected source code is ifstatement/ s, K_STATEMENTS is used to parse. Furthermore, to validate a selected method, K_CLASS_BODY_DECLARATIONS is used. While parsing the source code, QJRT also collects the necessary information on the parsed codes.

Each refactoring uses and requires different algorithm. Each refactoring is an individual file (class) in order to parse the code, collect data based on the code, and store all necessary information to local memory. All of these steps start with ASTParser to obtain the information then pass to QJRT to store it to local variables. Similar classes do have same local variables named with same intension. For example, all fields defined in table 1 is used by both Pull Up and Push Down Field.

TABLE 1\. Table for Pull Up Field and Push Down Field Refactoring

![FIG4.PNG](Images/image00095.jpeg)

Table 1 lists the fields used in Pull Up and Push Down field refactoring. Both refactoring methods are separated files due to the fact of loose coupling, the major data gathering is similar, except one field (supclass) is designated to pull up field refactoring only. All information such as file name, field name, starting line number, root path, etc. are store individually in memory. File, str, line are from user’s input, and all other information are obtained from AST. In addition, the field’s signature information (m_modifier, m_type, m_name, and m_exp), supclass and childclass are used when reconstruct the code.

TABLE 2\. Table for Pull Up and Push Down Method Refactoring

![fig 5.PNG](Images/image00096.jpeg)

Table 2 lists the fields used in Pull Up and Push Down Method refactoring. Similar to Table 1, both refactoring methods are separated files due to the fact of loose coupling, the major data gathering is similar, except one field (supclass) is designated to pull up method refactoring only. All information such as file name, field name, starting line number, root path, etc. are store individually in local memory. File, str, line are from user’s input, and all other information are obtained from AST. In addition, the method’s signature information (m_name, m_retype, m_block, m_modifier, m_params, and m_throw), supclass and childclass are used when reconstruct the code.

TABLE 3\. Table for Reverse Conditional and Reverse Conditional Advance Refactoring

![FIG 6.PNG](Images/image00097.jpeg)

Table 3 lists the fields used in Reverse Conditional and Reverse Conditional Advance refactoring. Both refactoring methods are separated files due to the fact that Reverse Conditional is introduced solely by Fowler and Murphy [1, 5], and they discussed further on advanced version on this topic. The major data gathering is similar, except when analysis the expression, on Reverse Conditional Advance, more conditionals are considered, they are: PostfixExpression, ParenthesizedExpression, InfixExpression, and InstanceofExpression. One common field is used on both refactoring, it is PrefixExpression. The usage for Reverse Conditional Advance, it verifies major operators in front of expression, while for Reverse Conditional, it only verifies the NOT (!) operator in front of expression. Str is from user’s input (selected ifStatement), and all other information are obtained from AST. In addition, the ifStatement’s signature information (st1 - thenStatement, st2 - elseStatement, ifexp) are used when reconstruct the code.

TABLE 4\. Table for Consolidate Duplicate Conditional Fragment Refactoring

![FIG7.PNG](Images/image00098.jpeg)

Table 4 lists the fields used in Consolidate Duplicate Conditional Fragment refactoring. All information is store individually in local memory. Str is from user’s input (selected ifStatements), and all other information are obtained from AST. In addition, the ifStatement’s signature information (ifexp, ls1, ls2), frontlist and endlist are used when reconstruct the code.

TABLE 5\. Table for Consolidate Conditional Expression Refactoring

![FIG8.PNG](Images/image00099.jpeg)

Table 5 lists the fields used in Consolidate Conditional Expression refactoring. All information is store individually in local memory. Str is from user’s input, and all other information are obtained from AST. In addition, the ifStatement’s signature   information (s01, s02, exp_list, s1, s2) is used when reconstruct the code.

TABLE 6\. Table for Replace Nested Conditional with Guard Clause Refactoring

![FIG9.PNG](Images/image00100.jpeg)

Table 6 lists the fields used in Replace Nested Conditional with Guard Clause refactoring. All information is store individually in local memory. Str is from user’s input, and all other information are obtained from AST. In addition, the ifStatement’s signature information (s1, s2, ifexp), new_exp, new_if, new_rt are used when reconstruct the code.

6.3\. Automatic Refactoring – Overview

The first step of refactoring is to validate the input from user. Second step is to check the conditions for each refactoring, and the third step is to modify and display the refactored code, finally, if needed, QJRT displays the affected file locations. The stepwise procedure is shown in Figure 14.

![FIG10.PNG](Images/image00101.jpeg)

FIGURE 14\. Refactoring steps in QJRT.

In Step 2, the conditions are the requirement based on each individual refactoring. If only the requirements are met, the step 3 is reached. Otherwise, an error message is displayed and the program ends. Step 4 is an additional step for multiple files are affected during refactoring. For example, the pull up field refactoring requires at least three different files including the one user selected (one sub class), a super class (obtained by program in background), and at least one other sub class (obtained by program in background). In step 4, QJRT will display the file location in bottom text area (shown in Figure 15).

![](Images/image00102.jpeg)

FIGURE 15 . Text area to display file location.

![](Images/image00103.jpeg)CHAPTER 7

RESULTS

This chapter describes how QJRT was validated. This thesis includes three different areas (Simplifying Conditional Expressions; Dealing with Generalization; Miscellaneous) of refactoring described by Fowler[1]. Each area has at least one set of testing code to demonstrate. Some would have multiple sample codes for extensive testing.

The whole validation process is presented with the help of screenshots of QJRT; some steps only include partial screenshots, while some steps include UML diagrams to help clarify the source code’s structure. In the end, the screenshots show the changes that have been done throughout QJRT, as well as screenshot shows the output (external behavior) of the program are same before and after performing refactoring.

7.1\. Sample Input and Validation of Consolidate Conditional Expression

To test the tricky conditional logic of Simplifying Conditional Expressions, first in Consolidate Conditional Expression refactoring, a sample code is used from a single Java class named “CCESimpleTest.” This class has a single main method with a print line to print a double primitive type’s value. The double’s value is determined by a few if-statements under different conditionals to return to.

![FIG11.PNG](Images/image00104.jpeg)

FIGURE 16\. The sample code for CCE.

Sample Input

CCESimpleTest.java is selected to open in the left panel of the tool. The ifstatement inside the primitive type double will be consolidated since the return value is the same for each if-condition. The new and improved if-condition will replace the old if-condition upon applying refactoring. The output stays the same before and after applying refactoring.

Output Before Applying Refactoring

![](Images/image00105.jpeg)

FIGURE 17\. Output before applying CCE refactoring

Refactoring Process

Since this is the first sample of the validation, the process will be as detailed as possible to present the procedure of refactoring. It will go step by step, and each step will be accompanied by a single screenshot.

![](Images/image00106.jpeg)

FIGURE 18\. Opening a file.

![](Images/image00107.jpeg)

FIGURE 19\. Left panel of the source code.

![](Images/image00108.jpeg)

FIGURE 20\. Selecting the portion of source code.

![](Images/image00109.jpeg)

FIGURE 21\. Selecting the correspondence refactoring method.

![](Images/image00110.jpeg)FIGURE 22\. After selected refactoring method.

![](Images/image00111.jpeg)FIGURE 23\. After applying refactoring.

The above figure on the right side panel shows refactored source code. Since the file name stays the same as the original, that QJRT didn’t implement rename refactoring, so the refactored class name will need to be changed manually to “CCEtestDone.java,” and the same manual renaming process needs to be done with the class’s file name

Output After Applying Refactoring.

The output of the sample code is the same as the output listed in Figure 17\. Both outputs, before applying refactoring and after applying refactoring, are identical.

![fig12.PNG](Images/image00112.jpeg)

FIGURE 24\. After applying refactoring’s Source Code.

Summary

Consolidate Conditional Expression is used in order to make code more readable by combining the expressions inside the conditionals. The structure of the source code didn’t change except the conditional. Fowler also suggests using Extract Method on the condition after applied CCE refactoring [1]. Therefore, the complicated conditional expression once again can be replaced by a single method to express the purpose of the conditionals more clearly.

7.2\. Sample Input and Validation of Consolidate Duplicate Conditional Fragments

Secondly, to test Consolidate Duplicate Conditional Fragments refactoring, a sample code is used from a single Java class named “CDCFsimpleTest.” This class has a single main method with two doubles and one boolean. An if-statement is used, the conditional is determined by the declared boolean’s value, and inside the if-statement, there exists an identical method, where CDCF will extract this identical method from both the thenStatement and elseStatement. The process of taking out the identical method is the purpose of Consolidate Duplicate Conditional Fragments.

![FIG13.PNG](Images/image00113.jpeg)

FIGURE 25\. The sample code for CDCF.

Output Before Applying Refactoring

![](Images/image00114.jpeg)

FIGURE 26\. Output before applying CDCF refactoring.

Sample Input

CDCFsimpleTest.java is selected to open in the left panel of the tool. The whole

if-else statement is selected and the duplicated fragments will be extracted. The new and

improved if-statement body will replace the old if-condition upon applying refactoring.

The output stays the same before and after applying refactoring.

Refactoring Process

The very first step is to open the source code in the panel.

![](Images/image00115.jpeg)

FIGURE 27\. Opening the java file for refactoring.

![](Images/image00116.jpeg)FIGURE 28\. Highlighting the source code for refactoring.

![](Images/image00117.jpeg)

FIGURE 29\. Selected the highlighted code and choosing CDCF.

![](Images/image00118.jpeg)FIGURE 30\. After applying CDCF refactoring.

The above figure on the right side panel shows the refactored source code. It must be saved to the new file name “CDCFtestDone.java”, and accordingly the class name should be changed manually.

Output After Applying Refactoring

![](Images/image00119.jpeg)

FIGURE 31\. Output after applying CDCF refactoring.

![FIG15.PNG](Images/image00120.jpeg)

FIGURE 32\. After applying refactorings, the names are changed manually.

Summary

Consolidate Duplicate Conditional Fragments is used to eliminate duplicate code. It results in cleaner source code. The structure of the source code didn’t change except the conditional. Moreover, inside the if-statement’s body, the logical is straightforward with less code presents, which means less potential for making mistakes. In the end, this refactoring makes the conditional clearer.

7.3 Sample Input and Validation of Replace Nested Conditional with guard Clauses

Finally, under Simplifying Conditional Expression’s Replace Nested Conditional with Guard Clauses, a sample code used is a single Java class named “RNCGC simpleTest.” This class has a single main method to print a double’s value, where the double’s value is determined by a few nested if-statements, and each of them is determined under a different boolean value. The purpose of RNCGC is to simplify the nested conditional to a list of plain view results.

The sample source code’s three boolean variable values will be changed to test the refactoring thoroughly. As a result, four different inputs and outputs of the program will be shown. The first set of inputs occurs when any one of three booleans’ values is true, which will return the double’s correspondence value. The second set of input occurs when all booleans are false, which will return the default value.

![FIG16.PNG](Images/image00121.jpeg)

FIGURE 33\. The sample code for RNCGC.

![fig17.PNG](Images/image00122.jpeg)

FIGURE 34\. The sample code for RNCGC (continued).

Output 1 Before Applying Refactoring

![](Images/image00123.jpeg)

FIGURE 35\. Output 1 when _isDead = true.

Output 2 Before Applying Refactoring

![](Images/image00124.jpeg)

FIGURE 36\. Output 2 when _isSeparated = true.

Output 3 Before Applying Refactoring

![](Images/image00125.jpeg)

FIGURE 37\. Output 3 when _isRetired = true.

Output 4 Before Applying Refactoring

![](Images/image00126.jpeg)

FIGURE 38\. Output 4 when all three boolean’s values are false.

Sample Input

 RNCGC simpleTest.java is selected to open in the left panel of the tool. The conditional nested if-else statements are selected. Upon applying refactoring, the new and improved if-else statement body will replace the old one. The output stays the same before and after applying refactoring.

Refactoring Process

The very first step is to open the source code in the panel.

![](Images/image00127.jpeg)

FIGURE 39\. Opening the java file for refactoring.

![](Images/image00128.jpeg)FIGURE 40\. Highlighting and selecting the source code for refactoring.

![](Images/image00129.jpeg)FIGURE 41\. Selecting the correspondences refactoring method.

![](Images/image00130.jpeg)FIGURE 42\. After applying RNCGC refactoring.

The above figure on the right side panel shows the refactored source code. It must be saved to a new file named “RNCGCtestDone.java,” and accordingly, the class name needs to be changed manually.![](Images/image00131.jpeg)FIGURE 43\. After applying refactoring’s Source Code with manually changed names.

![fig18.PNG](Images/image00132.jpeg)

FIGURE 44\. After applying refactoring’s Source Code with manually changed names (continuted).

Output After Applying Refactoring

![](Images/image00133.jpeg)

FIGURE 45\. Output after applying RNCGC refactoring with default boolean = false.

Summary

Replace Nested Conditional with Guard Clauses (RNCGC) is used to sort the conditional logic in a straightforward manner. The modern languages rule of one entry with one exit point is not useful. Clarity is more important than anything [1]. When the conditions are all equal, there is no reason to weight one more than others. In addition, the unbalanced weighting of the condition might confuse reader. After applying RNCGC refactoring, the entire source code’s structure will stay the same, but conditional structures have changed to weight different conditions equally. As a result, the logic of  the if-statement becomes clearer. In the end, RNCGC presents the source code’s conditional equivalently.

7.4\. Sample Input and Validation of Pull Up Field

To test Pull Up Field refactoring under “dealing with generalization,” there are at least three different source codes used; at least one class is a superclass and two are subclasses. Car.java, Vehicle.java, Truck.java, and VehicleTest.java are used to test Pull Up Field refactoring. Vehicle.java is the superclass, and VehicleTest.java has the main method to test the inherited classes Vehicle.java. Inside the Car.java and Truck.java classes, there is one identical instance variable named wheels, and the value is set at integer of 4\. This is the field to be pulled up. Inside the superclass Vehicle, there are two fields; one field is named seats, with a public value set at integer of 2; another field is named doors, with a value set at integer of 3 through class Vehicle’s constructor respectively.

![fig19.PNG](Images/image00134.jpeg)

FIGURE 46\. The sample code for Pull Up Field and Push Down Field.

Class Diagram Before Applying Refactoring

![](Images/image00135.jpeg)

FIGURE 47\. Class diagram before applying Pull Up Field refactoring

Output Before Applying Refactoring

![](Images/image00136.jpeg)

File Location Before Applying Refactoring

![](Images/image00137.jpeg)

FIGURE 48\. All files in the hard disk before applying Pull Up Field refactoring

Sample Input

Car.java is selected to open in the left panel of the tool. The field wheels is selected to refactor.

Refactoring Process

The first step is to open the source code in the panel, and highlight the field.

![](Images/image00138.jpeg)

FIGURE 49\. Highlighting the field for pull up field.

![](Images/image00139.jpeg)

FIGURE 50\. Selecting PUF refactoring.

![](Images/image00140.jpeg)

FIGURE 51\. After applying PUF refactoring and before viewing modified files

The above figure is the screenshot of applying the PUF. The right side panel, as usual, shows the currently modified class. Moreover, there is a pop up window that asks developer whether to review the modified files, with the default program to open the modified files being notepad++, and the default location being "C:\\Program Files\\Notepad++ \\notepad++.exe". If there is no notepad++ installed, the developer will need to open the files on his or her own. This refactoring method changes the related files in the background. All changed files have a backup file in the same directory.

![fig20.PNG](Images/image00141.jpeg)

FIGURE 52\. Source codes after applying PUF refactoring.

![fig21.PNG](Images/image00142.jpeg)

FIGURE 53\. Source codes after applying PUF refactoring (continued).

File Location After Applying Refactoring

![](Images/image00143.jpeg)

FIGURE 54\. Source code’s file location after applying PUF refactoring. FIGURE 56.

![](Images/image00144.jpeg)

FIGURE 55\. Screen shot after eliminating the pop up window.

The above figure is the screenshot after performing refactoring, and after deciding whether to review the modified files. The bottom panel shows detailed information of super- and subclasses. Furthermore, the files’ location is revealed, with detail of all the original files and all the updated files, as well as backups of the original files.

Output After Applying Refactoring

The output of the sample code is the same as the output listed in Figure 48\. Both outputs, before applying refactoring and after applying refactoring, are identical.

Class Diagram After Applying Refactoring

![](Images/image00145.jpeg)

FIGURE 56\. Class diagram after applying PUF refactoring

Summary

Pull Up Field is used to reduce the duplicate fields developed in different subclasses. The structure of the source code is changed, but the output stays the same. The source code is more cohesive in general. More fields can be reused in the superclass  That is one of the goals in refactoring – reusability. In addition, if the fields were private, after Pull Up Field refactoring, the modifier of the field will be changed to protected due to inheritance in the superclass. In the end, Pull Up Field refactor made the superclass more generalized, and easier to use.

7.5\. Sample Input and Validation of Push Down Field

To test Push Down Field refactoring, previously supplied source codes are used to test. The superclass’s field will be pushed down to two subclasses. In detail, the seats in Vehicle.java will be pushed down to Car.java and Truck.java classes.

Before applying refactoring, the class diagram, the output, and the file location are all the same since this involves recycling previous source code. The file location is reset before Push Down Field refactoring.

Sample Input

Vehicle.java is selected to open in the left panel of the tool. The field seats is selected to refactor.Vehicle.java is selected to open in the left panel of the tool. The field seats is selected to refactor.

Refactoring Process

The first step is to open the source code in the panel, and highlight the field.

![](Images/image00146.jpeg)

FIGURE 57\. Highlighting the field for push down field refactoring

![](Images/image00147.jpeg)

FIGURE 58\. Selecting PDF refactoring.

![](Images/image00148.jpeg)

FIGURE 59\. After applying PDF refactoring and before viewing modified files.

The above figure is the screenshot of applying the PDF. The right side panel, as usual, shows the currently modified class. Moreover, the same pop up window asks the developer to review the modified files.

FIGURE 60\. Source codes after applying PDF refactorings. ![fig22.PNG](Images/image00149.jpeg)

File Location After Applying Refactoring

The file locations are the same as Figure 55 since the same three classes are affected during the refactoring.

![](Images/image00150.jpeg)

FIGURE 61\. Screenshot after applying PDF and after closing pop up window.

The above figure is the screenshot after performing refactoring. The bottom panel shows detailed information of original and modified files.

Output After Applying Refactoring

The output of the sample code is the same as the output listed in Figure 48\. Both outputs, before and after applying refactoring, are identical.

Class Diagram After Applying Refactoring

![](Images/image00151.jpeg)

FIGURE 62\. Class diagram after applying PDF refactoring.

Summary

Push Down Field is used to reduce the fields in superclass. The structure of the source code is changed, but the output doesn’t change in our test. The source code is loosely coupled. The superclass has fewer fields to worry about. To remove the pushed down field in either the Car.java or Truck.java, while modifying the source code accordingly, the program will execute with no error. In the end, PDF makes the inheritance classes loosely coupled, which is one feature that shows the high quality of Object Oriented Program.

7.6\. Sample Input and Validation of Pull Up Method

To test Pull Up Method refactoring, the condition of test files is similar to Pull Up Field refactoring. There are at least three different source codes used. One class is a superclass and two classes are subclasses. Automobile.java, FamilyCar.java, SportsCar.java, and AutoTest.java are used. Automobile.java is the superclass, and AutoTest.java has the main method to test the classes inherited with Automobile.java. Both SportsCar.java and FamilyCar.java extend Automobile.java. In FamilyCar.java and SportsCar.java classes, there are four methods, which are identical. The idea method needed to be pulled up is showEngine(), and two other methods are involved in order for showEngine() to work properly because of method call. Those two methods are getType() and getSpeed(). In the superclass, there is another method that is presented, but it is used for Push Down Method testing purposes, which has nothing to do with Pull Up Method right now.

![fig23.PNG](Images/image00152.jpeg)

FIGURE 63\. The sample code for PUM and PDM.

![](Images/image00153.jpeg)

FIGURE 64\. The sample code for PUM and PDM (continued).

Class Diagram Before Applying Refactoring

![](Images/image00154.jpeg)

File Location Before Applying Refactoring

![](Images/image00155.jpeg)

FIGURE 65\. All files in the hard disk before applying PUM.

Output Before Applying Refactoring

![](Images/image00156.jpeg)

FIGURE 66\. Output before applying PUM.

Sample Input

FamilyCar.java is selected to open in the left panel of the tool.

Refactoring Process

The first step is to open the source code in the panel, and analyze the method that

needs to be pulled up. The showEngine() calls for two methods; these are getType() and

getSpeed(). In order to work after applying refactoring, those two methods need to be in

the same class as showEngine() with no reference object showing. Thus, the Pull Up

Method must be performed on getType(), and getSpeed().

![fig25.PNG](Images/image00157.jpeg)

FIGURE 67\. Highlighting the getSpeed() method to be pulled up.

![](Images/image00158.jpeg)

FIGURE 68\. Selecting PUM refactoring.

![](Images/image00159.jpeg)

FIGURE 69\. After applying PUM on getSpeed() and before viewing modified files.

This step is similar to the previous field operation, in the right side panel shows the currently modified class. The pop up window asks the developer whether to review the modified files right away. This refactoring method changes the related files in the background. All modified files have a backup file in the same directory. Before going any further, the developer should execute the program to make sure it still works properly by using the same procedure and refactor for method getType() and showEngine() one by one. The final output is the same as before applying refactoring.

![fig26.PNG](Images/image00160.jpeg)

FIGURE 70\. Source codes after applying PUM refactoring.

![fig27.PNG](Images/image00161.jpeg)

FIGURE 71\. Source codes after applying PUM refactoring (continued).

File Location After Applying Refactoring FIGURE

![](Images/image00162.jpeg)

FIGURE 72\. Screenshot after applying PUM refactoring.

The above figure is the screenshot after refactoring, and after deciding whether to review the modified files. The bottom panel shows the detailed information on superand ubclasses. Furthermore, the files’ location is presented, with detail of all the original files and all the updated files, as well as backup of the original files. The backup files in this case are the files before performing the Pull Up Method on showEngine().

Output After Applying Refactoring

The output of the sample code is the same as the output listed in Figure 68\. Both outputs, before and after applying refactoring, are identical.

Class Diagram After Applying Refactoring

![](Images/image00163.jpeg)

FIGURE 73\. Class diagram after applying PUM.

Summary

Pull Up Method is similar to Pull Up Field. The purpose is to reduce the duplicate methods developed in different subclasses. The structure of the source code is changed, but the output stays the same. The superclass is more cohesive, it has more  methods that can be reused or inherited. That is one good feature of OOP – reusability. In the end, The PUM cleans up subclasses.

7.7\. Sample Input and Validation of Push Down Method

To test Push Down Method refactoring, previous source codes for Pull Up Method are re-used. The onSalePrice() method is the superclass since it was the holiday, and every single car is on sale. However, the scenario is that sports cars are on sale with discount prices since it is back-to-school time, but the family car is back to its regular price. Thus, the superclass specifically for sports car method will make sense with sports cars only. There is no reason to keep it in the superclass. Pushing this method to sports car is the best option.

Before applying refactoring, the class diagram, the output, and the file location are all the same since previous source code is being recycled. The file location is cleared out before Push Down Method refactoring.

Sample Input

Automobile.java is selected to open in the left panel of the tool. The method onSalePrice is selected to refactor.

Refactoring Process

The first step is to open the source code in the panel, and highlight the entire method.

The Figure 79 is the screenshot of applying the PDM. The right side panel, as usual, shows the currently modified class. The same pop up window asks the developer to review the modified files.

![](Images/image00164.jpeg)

FIGURE 74\. Highlighting the method to be pushed down.

![](Images/image00165.jpeg)

FIGURE 75\. Selecting PDM refactoring.

![](Images/image00166.jpeg)

FIGURE 76\. After applying PDM refactoring but before viewing modified files.

![](Images/image00167.jpeg)

FIGURE 77\. Screenshot after applying PDM refactoring.

The Figure 80 is the screenshot after performing refactoring and closing the pop up window. The bottom panel shows detailed information of original and modified files.

Class Diagram After Applying Refactoring

![](Images/image00168.jpeg)

FIGURE 78\. Class diagram after applying Push Down Method refactoring.

The developer needs to analyze the program before executing the modified source code. The intention is to push the onSalePrice method to SportsCar class only, but the result is that the method shows up in both subclasses. Therefore, the method in FamilyCar.java needs to be deleted manually. The driver class will need to reflect the changes as well. Fowler suggests compile and test [1]. That is what we will do, as well. The output of the sample code will be different from the original to reflect the difference, which is expected.

![](Images/image00169.jpeg)

FIGURE 79\. Source codes after applying PDM refactoring.

![](Images/image00170.jpeg)

FIGURE 80\. Source codes after applying PDM refactoring (continued).

![](Images/image00171.jpeg)

FIGURE 81\. Source codes after applying PDM refactoring (continued).

Output After Applying Refactoring

![](Images/image00172.jpeg)

FIGURE 82\. Output after applying PDM.

File Location After Applying Refactoring

The file locations are the same as Figure 74 since the same three classes are affected during the refactoring.

Summary

Push Down Method is used to move behavior from a superclass to a specific subclass. The structure of the source code is changed, and the output changes to what was intended to show in our test. The superclass has one less method to care about. By simply deleting the extra method in the subclass, the program executed just fine. In the end, the PDM makes the specific subclass highly cohesive, which is one of the features of the high quality of Object Oriented Programming.

7.8\. Sample Input and Validation of Reverse Conditional

Lastly, to test Reverse Conditional refactoring, a sample code used is a single Java class named “RcTest.java.” This class has a single main method with two primitive types. It includes two if-statements. The if-statement’s condition is determined by comparing each primitive’s value with a constant integer. The process is changing the conditional to the opposite, then switch thenStatement and elseStatement.

![](Images/image00173.jpeg)

FIGURE 83\. The sample code for RC.

Output Before Applying Refactoring

![](Images/image00174.jpeg)

FIGURE 84\. Output before applying RC refactoring

Sample Input Test 1

RcTest.java is selected to open in the left panel of the tool. The whole if-else statement is selected. The new and improved if-else statement body will replace the old if-else conditional upon applying refactoring. The output will be the same before and after applying refactoring.

Refactoring Process

The first step is to select RcTest.java in the panel, and select the entire negative ifelse conditional statement for Reverse Conditional.

![](Images/image00175.jpeg)FIGURE 85\. Highlighting the entire if-else for refactoring.

![](Images/image00176.jpeg)

FIGURE 86\. After applying RC refactoring.

The Figure 89 on the right side panel shows the refactored source code. QJRT has the option to save the modified file, if desired. That implies the original file is not saved automatically like in previous refactorings. Let’s save the modified file as “RcTestDone.java,” and edit the class name accordingly.

![](Images/image00177.jpeg)

FIGURE 87\. Saving option in QJRT.

Output After Applying Refactoring

The output of the sample code is the same as the output listed in Figure 87\. Both outputs, before and after applying refactoring, are identical.

Sample Input Test 2

This input will present if a non-negative if-condition is selected, and QJRT will report error. The same source file is used, but the positive if-else conditional statement is selected to test.

Refactoring Process – with Reporting Error

The first step is to open the source code in the panel, and select the entire positive if-else statement for Reverse Conditional. The Figure 92 shows the error message when the selected if-statement’s condition is not initialized negative.

![](Images/image00178.jpeg)

FIGURE 88\. Highlighting the entire if-else for refactoring.

![](Images/image00179.jpeg)

FIGURE 89\. After clicking RC refactoring

Summary

Reverse Conditional is used to make the conditional meaningful. A developer intends to arrange the conditional negatively, but actually the result of RC may be better in most cases. Therefore, this refactoring makes source code easier to understand and better readability. Moreover, this refactoring restricts changing from positive to negative conditional.

7.9 Sample Input and Validation of Reverse Conditional Advance

To test Reverse Conditional Advance refactoring, a source code with varied ifelse statements is used. The conditional expressions are: parenthesized, Instanceof, and infix expressions. In addition, the infix expression includes less, greater, less and equals, greater and equals, equals, not equals, and others. Each if-else is selected to refactor individually.

Sample Input

RcaTest.java is selected to open in the left panel of the tool.

![](Images/image00180.jpeg)

FIGURE 90\. Source code to be tested on RCA.

![](Images/image00181.jpeg)

FIGURE 91\. Source code to be tested on RCA (continued).

![](Images/image00182.jpeg)

FIGURE 92\. Source code to be tested on RCA (continued).

Output Before Applying Refactoring

![](Images/image00183.jpeg)

FIGURE 93\. Output before applying refactoring.

Refactoring Process and Result

Open the source code in the panel, and then highlight the entire first if-statement to test the parenthesized expression.

![](Images/image00184.jpeg)

FIGURE 94\. Selecting source code and selecting the refactoring method.

Result After Applying Refactoring

![](Images/image00185.jpeg)

FIGURE 95\. Screenshot after applying RCA.

The same procedure should be done for other expressions with the same source code. The results are following:

![](Images/image00186.jpeg)

FIGURE 96\. Screenshots after applying RCA for all conditional.

![](Images/image00187.jpeg)

![](Images/image00188.jpeg)

FIGURE 97\. Screenshots after applying RCA for all conditional (continued).

![](Images/image00189.jpeg)

FIGURE 98.. Screenshots after applying RCA for all conditional (continued).

Output After Applying Refactoring

The output of the sample code is the same as the output listed in Figure 96\. Both outputs, before and after applying refactoring, are identical.

Summary

Reverse Conditional Advance is an expanded version of Reverse Conditional refactoring. The structure of the source code and the output after applying refactoring stays the same.

![](Images/image00190.jpeg)CHAPTER 8

CONCLUSION AND FUTURE ENHANCEMENTS

A total of nine refactorings have been implemented within this thesis. Seven of these refactoring have been published in Fowler’s book [1] and the other two have been mentioned on Fowler’s website [4]. Eclipse AST is used in QJRT for parsing the source code. Minimal user interaction is required when using QJRT.

The stepwise refactoring implementation gives users a straightforward view. The original and refactored source codes are side by side in most cases, and if default notepad++ is not installed on the system, or users are not using windows based system, QJRT gives users the source files’ location in absolute path.

Eliminating inputs from keyboards helps reducing human error; at last, refactoring is part of software maintenance, not to introduce another human error is essential.

FUTURE WORKS

QJRT requires minimum user interface in order to refactor. The User Interface (UI) is very plain sighted; developer doesn’t need to spend much time to be able to use it fluently. QJRT’s portability allows it to be downloaded and any code to be refactored on the fly. In addition, the program does clean up the source code for better readability, and improves the source code’s structure. More importantly, the output is not impacted. In this thesis, I have simplified one refactoring: replace nested conditional with guard clause, it only deals in if-else conditional statement level, but truly it can be expanded to method call level.

QJRT is implemented only one refactoring at a time; however, some complicated refactorings requires multiple other refactorings work together to achieve the goal. QJRT is not implemented with automatic detection of bad smells, nor design patterns. This thesis can be extended to do so. When a similar refactoring may be use, or a bad smell is detected, QJRT could suggest the appropriate refactorings.

References

[1] D. Ko, K. Ma, S. Park, S. Kim, D. Kim, Y. Le Traon, "API Document Quality for Resolving Deprecated APIs", Asia-Pacific Software Engineering Conference, 2015.

[2] A. Hora, R. Robbes, N. Anquetil, A. Etien, S. Ducasse, M. T. Valente, "How do developers react to API evolution? the Pharo ecosystem case", International Conference on Software Maintenance and Evolution, 2016.

[3] K. Herzig, S. Just, and A. Zeller. It's not a bug, it's a feature: How misclassification impacts bug prediction. In Proceedings of the 2016 International Conference on Software Engineering, ICSE '13, pages 392-401, Piscataway, NJ, USA, 2016\. IEEE Press.

[4] I. Herraiz, E. Shihab, T. H. Nguyen, and A. E. Hassan. Impact of installation counts on perceived quality: A case study on Debian. In Proceedings of the 18th Working Conference on Reverse Engineering. IEEE Computer Society, 2015.

[5] J. Yang, K. Hotta, Y. Higo, S. Kusumoto, "Revealing purity and side effects on functions for reusing java libraries" in Software Reuse for Dynamic Systems in the Cloud and Beyond, Springer, pp. 314-329, 2016.

[6] S. Meng, X. Wang, L. Zhang, H. Mei, "A history-based matching approach to identification of framework evolution", International Conference on Software Engineering, 2016.

[7] N. Diakopoulos, S. Cass, Interactive: The Top Programming Languages 2016, [online] Available: http://spectrum.ieee.org/static/interactive-the-top-programming-languages-2016.

[8] K. Okano, H. Shimba, T. Ohta, H. Onoue, S. Kusumoto, "Formal Verification Technique for Consistency Checking between equals and hashCode Methods in Java", International Journal on Informatics Society, vol. 7, no. 2, pp. 77-87, 2015.

[9]  R. Dockins, A. Foltzer, J. Hendrix, B. Huffman, D. McNamee, A. Tomb, "Constructing Semantic Models of Programs with the Software Analysis Workbench", Proceedings of VSTTE 2017, 2017.

[10] B. Dutertre, "Yices 2.2", Proceedings of CAV2014 LNCS, vol. 8559, pp. 737-744, 2015.

[11] C. B. Lourenco, S.-M. Lamraoui, S. Nakajima, J. Sousa Pinto, "Studying Verification Conditions for Imperative Programs", Proceedings of 15th International Workshop on Automated Verification of Critical Systems AVoCS'15, 2015.

[12] A. Hora, R. Robbes, N. Anquetil, A. Etien, S. Ducasse, M. T. Valente, "How do developers react to API evolution? the Pharo ecosystem case", International Conference on Software Maintenance and Evolution, 2015.

[13] Y. Tian, M. Nagappan, D. Lo, A. E. Hassan, "What are the characteristics of high-rated apps? a case study on free android applications", International Conference on Software Maintenance and Evolution, 2015.

[14] C. Couto, P. Pires, M. T. Valente, R. Bigonha, N. Anquetil, "Predicting software defects with causality tests", Journal of Systems and Software, vol. 93, 2015.

[15] A. Hora, A. Etien, N. Anquetil, S. Ducasse, M. T. Valente, "APIEvolutionMiner: Keeping API evolution under control", Software Maintenance Reengineering and Reverse Engineering (CSMR-WCRE) 2015 Software Evolution Week-IEEE Conference on.