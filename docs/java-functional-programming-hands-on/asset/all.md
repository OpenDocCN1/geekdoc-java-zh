![](image_rsrc11N.jpg)

Copyright
Copyright © 2023 by AK Ray
All rights reserved.

This ebook is protected by copyright law. No part of this publication may be reproduced, distributed, or transmitted in any form or by any means, including photocopying, recording, or other electronic or mechanical methods, without the prior written permission of the copyright owner, except in the case of brief quotations embodied in critical reviews and certain other noncommercial uses permitted by copyright law.

For permission requests or inquiries, please contact:
Email: akr.technolab@gmail.com

Disclaimer: The information provided in this ebook is for general informational purposes only and should not be considered as professional, legal, or financial advice. The author and publisher disclaim any liability or responsibility for any loss or damage incurred as a consequence of the use of the information presented in this ebook.

First Edition
TO

This book is dedicated to the memory of my beloved Grandfather, whose unwavering support and boundless love continue to inspire me every day. Your presence in my life was a blessing, and your memory will forever be cherished.

To my family, for your patience, encouragement, and understanding throughout this journey. Your belief in me is my greatest motivation.
To my mentor, Biplab Roy, Sr. Engineering Leader at Calibo India Pvt Ltd, whose mentorship and guidance have shaped my perspective and fueled my passion for this subject.
To my loyal readers and supporters, your enthusiasm for my work is a driving force, and I'm deeply grateful for your trust and encouragement.
And to all those who believe that knowledge has the power to transform lives, this book is dedicated to you. May it bring inspiration, insight, and positive change.
With heartfelt gratitude,  About the Author
Hello,Techies! I'm AK Ray, a seasoned software professional with a deep-rooted passion for playing with Java best practices and a keen interest in functional programming.

With over 10 Yrs of hands-on experience in the software industry especially in core product development in the R&D division and I have been certified in Software Design and Architecture from University of Alberta, I've had the privilege of working on a multitude of projects, each a testament to the power of Java. But beyond the lines of code, I've also nurtured fervor for exploring the elegance and efficiency of functional programming paradigms.

My journey into the world of programming started in early 2014\. Java, with its robustness and versatility, quickly became my language of choice. Over time, I delved into the fascinating realm of functional programming, where I discovered the beauty of lambda expressions, streams, and immutability.

I'm passionate about fostering a community of Java enthusiasts and functional programming aficionados. Let's connect and continue the conversation:

Email: akr.technolab@gmail.com
LinkedIn : https://www.linkedin.com/in/amitesh-kumar-ray-9366b7143/ Practice Code: GIT link is shared at the end of the book

I extend my heartfelt gratitude to you for choosing to explore the world of Java functional programming with me. Your support and enthusiasm fuel my commitment to sharing knowledge and empowering fellow developers with the tools they need to excel in the Java ecosystem.

Here's to a future of code that's not just functional but beautifully elegant too!
Warm regards,

1\. How to create a Stream ? 5 2\. Stream Operations 11
3\. Sorting using Streams 30
4\. GroupBy Statements 47
5\. Data Partitioning 67
6\. Function Interface 69
7\. Method Reference 86
8\. Record Class 95
9\. Lombok Library 99
10\. Sealed class/interface 103
11\. String Template 106
12\. Virtual Thread ? 111
13\. Sequenced Collection 116
14.Structured Concurrency 121

## How to create a Stream ?

### Streamis a sequence of elements that can be pipelined.

● It supports sequential as well as parallel operation.
● It was introduced in Java 8 as part of the Java Streams API under java.util.stream package ● Streams are used for processing sequences of data, such as collections (e.g., lists, sets, maps) or

other data sources, in a functional and declarative manner.
● Creating a parallel Stream will create the same number of parallel Streams as no of processors
available. It's a default behavior BUT you can change it as required.

The most common use case to create Stream is to create Stream from a Collection Object. Assume you have an Employee List of 10K records where we have to do some operations like Sorting,Filtering,Data Transformation logic, Grouping data, Partitioning data or other operations that we wanted to perform on bulk data.

![](image_rsrc11P.jpg)

Create Stream from Employee’s collection: Steps:
1\. Create List of Employee
2\. Create Stream from List of Employee

Employee.java  EmployeeUtil : we will use this class to get an Employee List for our example in this book.
![](image_rsrc11R.jpg)Create Stream from List of Employee Object:
Note :- Your Stream can be Sequential OR parallel
![](image_rsrc11S.jpg)Stream can Even be created from primitives/Strings:
![](image_rsrc11T.jpg)Create Stream using Stream Builder
![](image_rsrc11U.jpg)![](image_rsrc11V.jpg)![](image_rsrc11W.jpg)Print Stream values:
![](image_rsrc11X.jpg)![](image_rsrc11V.jpg)![](image_rsrc11Y.jpg)Let's Look into some examples of Stream operations

There are two types of operation that Stream supports.
1\. Intermediate Operation:
2\. Terminal Operation

![](image_rsrc11Z.jpg)

## Lets understand Streamoperationsusing below image:

![](image_rsrc120.jpg)![](image_rsrc121.jpg)

## Filter Stream Data

![](image_rsrc11P.jpg)Filter Employee having salary more than 160,000

## filter(Predicate p)is a method of Stream which takes an Input of type Predicate.

![](image_rsrc122.jpg)

## Predicateis a Functional Interface that takes an input of any type and given Result of type Boolean.

![](image_rsrc11P.jpg)Filter Employees where CITY is Bangalore You can even write your Predicate separately and pass it to filter(Predicate p) method. ![](image_rsrc123.jpg)![](image_rsrc11P.jpg)Print EVEN Number between 1 to 10
![](image_rsrc11V.jpg)![](image_rsrc124.jpg)

### OR

![](image_rsrc125.jpg)Note You can call multiple Predicates together as per your need OR you can simply combine the logics of Two conditions together as per your requirements.
![](image_rsrc11P.jpg)Use negate() OR change your Predicate logic to get opposite result
![](image_rsrc126.jpg)![](image_rsrc127.jpg)![](image_rsrc11V.jpg)![](image_rsrc128.jpg)

### Data Transformation using map(Function f) on Stream

![](image_rsrc129.jpg)NOTE in simple words you can say that map(function f) used to map data from input type X to any result type Y.
As per above example, you have mapped Employee Object to NAME. it accepts a function that do the transformation logic.
![](image_rsrc12A.jpg)![](image_rsrc11V.jpg)![](image_rsrc12B.jpg)![](image_rsrc11P.jpg)Get the doubled the salary of each Employee’s
![](image_rsrc12C.jpg)![](image_rsrc11V.jpg)![](image_rsrc12D.jpg)![](image_rsrc11P.jpg)List Employee’s Name where SALARY>160,000 ![](image_rsrc12E.jpg)![](image_rsrc11P.jpg)Find the distinct name from List
![](image_rsrc12F.jpg)![](image_rsrc11P.jpg)Find the distinct name from List
Here we have taken the same requirement to find the distinct employee.

## There are multiple ways to get the RESULT of unique data BUT here we will use adistinct()

method.
As we have seen , in the above example it's done just by calling distinct() method BUT if you want to do

## the same for any custom class you must have to override the behavior ofhashcode()and
equals(Object o)method.

String classes do provide the implementation for these methods so we do not need to do it explicitly. ![](image_rsrc12G.jpg)![](image_rsrc12H.jpg)![](image_rsrc11V.jpg)![](image_rsrc12J.jpg)

### NOTE- you can use Employee Record instead of Employee class THEN you no need to provide the

implementation for hashcode() and equals(Object o) method since JAVA does it by default.
![](image_rsrc12K.jpg)OR you can even use the Lobok library also to handle getter/setter ,hashcode and equals methods using annotations. https://projectlombok.org/#

## You can get the same RESULT without even usingdistinct()method , we can simply collect our

result in SET since SET does not allow duplicate SO duplicate entry will automatically be excluded. ![](image_rsrc11P.jpg)Find unique employee result without any duplicate ![](image_rsrc12M.jpg)

## Sorting using Streams

![](image_rsrc11P.jpg)Sort the Number List using Stream ![](image_rsrc12N.jpg)![](image_rsrc11V.jpg)![](image_rsrc12P.jpg)![](image_rsrc11P.jpg)Sort String elements using Stream.
![](image_rsrc12R.jpg)![](image_rsrc11V.jpg)![](image_rsrc12S.jpg)Let's look into how to sort custom class objects as we used to handle in real time.
Let's assume we have a List of 10K Employee data and you wanted to SORT them in ascending order of Employee Name.
![](image_rsrc11P.jpg)Sort Employee List in ascending order of Employee Name Input DATA:
![](image_rsrc12T.jpg)We can use this Utility class to get Employee Records for our examples.
Here we are using Record instead of class.
![](image_rsrc12U.jpg)![](image_rsrc12V.jpg)![](image_rsrc11V.jpg)![](image_rsrc12W.jpg)![](image_rsrc11P.jpg)Sort Employee List in Descending order of Employee Name
![](image_rsrc12X.jpg)Result : Example:List the Employee data in Sorted in Ascending order by Name,CITY and Design WHERE Salary>160,000
![](image_rsrc12Y.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Find Employee Names Sorted BY Name where SALARY>160,000. ![](image_rsrc12Z.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Find Employee’s salary list where Salary will be doubled if SALARY>160,000 ![](image_rsrc130.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)

## WHY do we use the peek(Consumer c)method ?

We use this method for DEBUGGING purposes where we wanted to print String elements.
![](image_rsrc131.jpg)![](image_rsrc11V.jpg)![](image_rsrc132.jpg)As you can see here , We are printing Stream elements before and after mapping data.
![](image_rsrc11P.jpg)How to limit Stream elements ? You can use the limit(long l) method to limit Stream elements.
![](image_rsrc133.jpg)![](image_rsrc11V.jpg)![](image_rsrc134.jpg)![](image_rsrc11P.jpg)Find the MAX number from the List using Stream ![](image_rsrc135.jpg)![](image_rsrc11V.jpg)![](image_rsrc136.jpg)![](image_rsrc11P.jpg)Find the MAX Salaried Employee from the Employee List.
![](image_rsrc137.jpg)Result :
![](image_rsrc11P.jpg)Find the MIN Salary of Employee from the Employee List WHERE CITY=Bangalore ![](image_rsrc138.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)WHY do we use the flatmap(Function f) method ? flatmap(function f) is similar to map(function f) and used to flatten the stream's data.
Assume that Steam contains List of List or List of Array THEN we can simply flatten it to List.
![](image_rsrc139.jpg)![](image_rsrc11V.jpg)![](image_rsrc13A.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)get the combined total Employees from different departments. ![](image_rsrc13B.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Find Average of Integers using Stream ![](image_rsrc13C.jpg)![](image_rsrc11V.jpg)![](image_rsrc13D.jpg)

## GroupBy Statements

![](image_rsrc11P.jpg)Find the List Employee’s name from List of Employee
![](image_rsrc13E.jpg)![](image_rsrc11P.jpg)GroupBy Employee list by Employee Name
![](image_rsrc13F.jpg)![](image_rsrc11V.jpg)![](image_rsrc13G.jpg)![](image_rsrc11P.jpg)GroupBy Employee’s Data By CITY then By Department
![](image_rsrc13H.jpg)![](image_rsrc11V.jpg)![](image_rsrc13J.jpg)![](image_rsrc11P.jpg)Find the Average SALARY of each CITY.
![](image_rsrc11V.jpg)![](image_rsrc13K.jpg)![](image_rsrc11P.jpg)Find the MAX salaried Employee from Each CITY. ![](image_rsrc13M.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Find the MIN Salaried EMployee from each CITY
![](image_rsrc13N.jpg)![](image_rsrc11V.jpg):
![](image_rsrc11P.jpg)Find the Employee count by Each CITY ![](image_rsrc13P.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Find SUM of Salary of Employee from Each group(CITY). ![](image_rsrc13R.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Find MIN,MAX,SUM and AVG Salary from Each CITY ![](image_rsrc13S.jpg)![](image_rsrc11V.jpg)![](image_rsrc13T.jpg)![](image_rsrc11P.jpg)GroupBy Employee’s Data and remove groupBy column from Result. As in the Below Example , We have groupBy Employee’s data by CITY, CITY is already there in result as Map KEY so we don't want to see CITY value in Map values. Default Result of groupBy:
![](image_rsrc13U.jpg)Expected Result:
![](image_rsrc13V.jpg)As you can see, the CITY value is NOT included in Map values.
We have different overloaded methods for groupBy(..) as you can see below.
We will look into it one by one. groupingBy(..) overloaded methods:
![](image_rsrc13W.jpg)

It may be possible that you wanted to perform some extra job on groupingBy data , you can use these overloaded methods to get your task done.

![](image_rsrc13X.jpg)![](image_rsrc13Y.jpg)![](image_rsrc11V.jpg)

As you can see in the above example , we are using the 2nd overloaded method of groupingBy(..) where we are passing the Collector to map groupingBy(..) results as we want.

This kind of use-cases you will get while working with real time applications.
As you can see here , we are collecting result in MAP but what if I wanted to collect final result in TreeMap or Hashtable or any other implementation of Map.
![](image_rsrc13Z.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)GroupBy Employee’s data by CITY and Designation and collect final data in TreeMap so that it will be sorted.
![](image_rsrc140.jpg)![](image_rsrc11V.jpg)![](image_rsrc141.jpg)Note what if i wanted to keep Designation data to TreeMap , means expecting the result of type

### TreeMap<String,TreeMap<String,List<EmployeeRecord>>>

![](image_rsrc11P.jpg)GroupBy Employee’s data by CITY and Designation and collect final data in TreeMap so that it will be sorted.
![](image_rsrc142.jpg)![](image_rsrc11V.jpg)![](image_rsrc143.jpg)Note: As you can see here , we have grouped Data by multiple fields and collected result data in TreeMap at different levels just to get the result data in sorted format.
You can apply a similar use-case on different types of data.
![](image_rsrc11P.jpg)

You have a List of Students where each Student has opted multiple courses and each course they have some marks. groupBy Student Data by Student Name and course so that Name and course will be in Ascending order for better readability on user-interface.

StudentRecors.java
![](image_rsrc144.jpg)StudentRecordUtil.java : get Student list , we are using Record here.
![](image_rsrc145.jpg)![](image_rsrc146.jpg)![](image_rsrc11V.jpg)![](image_rsrc147.jpg)![](image_rsrc11P.jpg)Find the Highest marks subject by each Student. ![](image_rsrc148.jpg)![](image_rsrc11V.jpg)![](image_rsrc149.jpg)![](image_rsrc11P.jpg)Find the AVG marks by each Student.
![](image_rsrc14A.jpg)![](image_rsrc11V.jpg)![](image_rsrc14B.jpg)![](image_rsrc11P.jpg)Find the Total marks scored by each Student
![](image_rsrc11V.jpg):
![](image_rsrc14C.jpg)![](image_rsrc11P.jpg)Find the Topper with Total SUM of marks obtained ![](image_rsrc14D.jpg)![](image_rsrc11V.jpg)![](image_rsrc14E.jpg)![](image_rsrc11P.jpg)

### WHY do we usegroupingByConcurrent(..)? What is the
difference between groupingBy(..) andgroupingByConcurrent(..) ?

![](image_rsrc11P.jpg)Demo: use concurrent version of groupingBy(..) ![](image_rsrc14F.jpg)![](image_rsrc11V.jpg)

## Data Partitioning

● It partitions the elements of a stream into two groups based on a boolean-valued function.
● The partitioning operation returns aMapwhere the keys are Boolean values (true andfalse)
![](image_rsrc14G.jpg)![](image_rsrc11P.jpg)Find the list of Student who are successfully scored more than 80% ![](image_rsrc14H.jpg)![](image_rsrc11V.jpg)

## FunctionInterface

![](image_rsrc14J.jpg)What is Functional Interface in Java ? How do we use it ?
![](image_rsrc14K.jpg)![](image_rsrc14M.jpg)Some most commonly used Functional Interfaces : ![](image_rsrc14N.jpg)![](image_rsrc14P.jpg)![](image_rsrc14J.jpg)

## Multiply Number by 2 , using FunctionalInterfaceFunction

![](image_rsrc14R.jpg)![](image_rsrc11V.jpg)![](image_rsrc14S.jpg)![](image_rsrc11P.jpg)Check if Number is EVEN
![](image_rsrc14T.jpg)![](image_rsrc11V.jpg)![](image_rsrc14U.jpg)![](image_rsrc11P.jpg)What is UnaryOperator ?

UnaryOperator is a FunctionalInterface that takes an input of type X and provides the output of the same type.
It's the same as a Function that returns theResult of the same type as input.

![](image_rsrc14V.jpg)![](image_rsrc11V.jpg)100
![](image_rsrc11P.jpg)What is BinaryOperator ?
Its Functional Interface that accepts 2 inputs(same type) and provides the Output of the same type.
![](image_rsrc14W.jpg)![](image_rsrc11V.jpg)33
![](image_rsrc11P.jpg)What is Consumer ?
![](image_rsrc14X.jpg)![](image_rsrc14Y.jpg)![](image_rsrc11V.jpg)You have provided: 10
![](image_rsrc11P.jpg)What is Supplier ![](image_rsrc14Z.jpg)![](image_rsrc11P.jpg)Supplier Demo
In simple words we can say that,It Supply the value without taking any input.
![](image_rsrc150.jpg)![](image_rsrc11V.jpg)![](image_rsrc151.jpg)![](image_rsrc11P.jpg)HOW to create Thread ?
![](image_rsrc152.jpg)![](image_rsrc11V.jpg)Thread is Running …
![](image_rsrc11P.jpg)What is Lambda Expression ?
![](image_rsrc153.jpg)![](image_rsrc154.jpg)![](image_rsrc155.jpg)![](image_rsrc156.jpg)![](image_rsrc157.jpg)Please follow the Below Book for Java Functional Programming.

I have scripted this Book specially for Java Function programming where I have discussed Stream, Lambda Expression , Method Reference and other features from very scratch level to expert level.

![](image_rsrc158.jpg)

https://www.amazon.in/Java-Functional-Programming-industry-practices-ebook/dp/B0CHTV3TWR/ref=tmm_kin_swatch_0?_encoding =UTF8&dib_tag=se&dib=eyJ2IjoiMSJ9.LTBpL1aLeOJTflVVRJLD_qjU1hUQlPs1TDeXVqKNqqkNTLoganQLNlsBM3R6CQ4znU4cx PIOgaHH65Q4w0A8Z7Wwz3DuDVF5dySqfYAIwxGQ2lHoWkzOgYTBkJhlsJ2tDaipRuO_Cu8-oRukNLrpJNDxfAUBr2YtJtaZPv8_3lg HlCRJSkTgx8FI2eX5w75WT0w8CS-lM_wnEa8QDnKzivV8sj3247KOswDu3-VgfjI.tMkuKJR3Un8fd6uUKoQlXQWBnPyv0tAW7O_W OtClYp0&qid=1715674856&sr=8-3

![](image_rsrc159.jpg)![](image_rsrc15A.jpg)![](image_rsrc11V.jpg)![](image_rsrc15B.jpg)![](image_rsrc15C.jpg)

## Method Reference

![](image_rsrc15D.jpg)![](image_rsrc11P.jpg)How you can refer to a method call to another method using Method Reference. ![](image_rsrc15E.jpg)![](image_rsrc11V.jpg)![](image_rsrc15F.jpg)![](image_rsrc15G.jpg)![](image_rsrc15H.jpg)![](image_rsrc15J.jpg)![](image_rsrc15K.jpg)![](image_rsrc15M.jpg)![](image_rsrc11P.jpg)What is the default method in Java ? Can we provide method implementation in Interface ?
default methods were introduced as a new feature in interfaces. Default methods allow interfaces to have methods with implementations.

## These methods are marked with thedefaultkeyword and provide a way to add

new methods to interfaces without breaking existing implementations.
Add default method in Interface
![](image_rsrc11P.jpg)Can we add private methods in Interface ? ![](image_rsrc15N.jpg)![](image_rsrc11P.jpg)Can you use a static method in Interface ?
![](image_rsrc15P.jpg)![](image_rsrc15R.jpg)![](image_rsrc11P.jpg)Calculate Average of List of Integers
![](image_rsrc15S.jpg)![](image_rsrc11V.jpg)![](image_rsrc15T.jpg)![](image_rsrc11P.jpg)Find MAX number from the list
![](image_rsrc15U.jpg)![](image_rsrc11V.jpg)![](image_rsrc15V.jpg)![](image_rsrc11P.jpg)

Given a list of integers, write a Java program to filter out the even numbers, double the remaining odd numbers, and then return the sum of all the resulting numbers.

![](image_rsrc15W.jpg)![](image_rsrc11V.jpg)![](image_rsrc15X.jpg)![](image_rsrc11P.jpg)What is “var” in java ? Why do we use it ?

## In Java 11, thevarkeyword was introduced as a new feature to enhance type

inference for local variables.
It allows you to declare local variables without explicitly specifying their types, provided that the type can be inferred from the context.

### Here's how you can use thevarkeyword in Java 11:

![](image_rsrc15Y.jpg)![](image_rsrc11V.jpg)![](image_rsrc15Z.jpg)![](image_rsrc11P.jpg)What is Record Class in Java ? Why do we use it ?
![](image_rsrc160.jpg)![](image_rsrc161.jpg)Let's have a look on how our normal POJO/Data Carrier class look like.
![](image_rsrc162.jpg)![](image_rsrc163.jpg)Note Here we have just 4 attributes in POJO but in real time it may be 10 or even more, then it will be around 200 lines of code and you may have so many similar classes in your project.
Java has introduced Record to handle such situations so that Java will take care of creating these methods on your behalf.
Let's look at how we can write the same POJO class using the Java Record class. EmployeeRecord.java
![](image_rsrc164.jpg)This EmployeeRecord will have the same behavior as the Employee class. Some facts about Record classes:
![](image_rsrc165.jpg)Example: Do we have any other alternative of Record classes in java that we can use in real time projects ?
Yes ,We do have the Lombok library that we can use with Java.
Know more about Lombok: https://projectlombok.org/
![](image_rsrc11P.jpg)

## What is Lombok Library and how can we use it with Java.

![](image_rsrc166.jpg)

You can use Lombok annotations to create setter,getter,constructors ,hashcode and equals methods.

![](image_rsrc167.jpg)

If you want to use it in your Java project THEN you can simply add maven dependency for Lombok to your conf file.

![](image_rsrc168.jpg)If you are using Springboot THEN you just need to add Lombok Starter. ![](image_rsrc169.jpg)

For more info visit : https://start.spring.io/ to create Springboot project and try Lombok. NOTE-I have Scripted Springboot Book with realtime examples in the simplest way possible, In this Book I have mostly covered the issue that we as Developers or Novice Springboot Developers used to face.

![](image_rsrc16A.jpg)

https://www.amazon.in/microservices-Springboot-Amitesh-Kumar-Ray-ebook/dp/B0CW1DR6GQ/ref=sr_1 _5?crid=2FE0NDKXDTKG5&dib=eyJ2IjoiMSJ9.kpkN0_gzitOhJxtGHFurUbIiLlo4jS9QMnNp4Hqs8Hgb10 OKXR0KizFEkiD8KHhiVzAhKCdy2bl2BTp2a_WjBz9lgfSgRFznVVVQSkB2C42lXyhLd47xn1m0e8QSZB_ PsDoiUuuTDcRuGwexBYuUTw.ywy4lZsvBybFf5UiiZAl8aCXQ5L5hpwgrxOYXQ2kE5g&dib_tag=se&keyw ords=amitesh+kumar+ray&qid=1715749771&sprefix=amitesh+kumar+ray%2Caps%2C235&sr=8-5

Employee POJO with Lombok:
![](image_rsrc16B.jpg)![](image_rsrc11P.jpg)

## What is a Sealed class/interface in Java ?

![](image_rsrc16C.jpg)![](image_rsrc16D.jpg)Let's create and sealed Interface OrgService :
![](image_rsrc16E.jpg)![](image_rsrc16F.jpg)EmployeeService Interface:
![](image_rsrc16G.jpg)

NOTE :
If the subtype is a non-sealed interface then it will be extensible by everyone.
If the subtype is a sealed interface then it will NOT be extensible by everyone.

![](image_rsrc16H.jpg)![](image_rsrc16J.jpg)As you can see here, we are overriding the behavior of 2 interfaces. ![](image_rsrc11P.jpg)

## What is String Template in java ?

![](image_rsrc16K.jpg)![](image_rsrc16M.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)Use String Template for format String
![](image_rsrc16N.jpg)![](image_rsrc11V.jpg)![](image_rsrc16P.jpg)![](image_rsrc11P.jpg)handle HTML file with String Template
![](image_rsrc11V.jpg)![](image_rsrc16R.jpg)![](image_rsrc11P.jpg)Can we generate any String format using String Template ? Yes, let's see how to create a json like String using String Template.
![](image_rsrc16S.jpg)![](image_rsrc11V.jpg)![](image_rsrc16T.jpg)![](image_rsrc11P.jpg)How to create Thread in Java ? ![](image_rsrc16U.jpg)Using Thread Class
![](image_rsrc16V.jpg)![](image_rsrc16W.jpg)![](image_rsrc11P.jpg)

## What is Virtual Thread ?

![](image_rsrc16X.jpg)![](image_rsrc11P.jpg)How to create Virtual Thread ?
![](image_rsrc16Y.jpg)![](image_rsrc16Z.jpg)![](image_rsrc11V.jpg)Hello
![](image_rsrc11P.jpg)Create 10K Normal Threads and Virtual Threads check the time taken. ![](image_rsrc170.jpg)![](image_rsrc11V.jpg)Create the 10K Virtual Thread. ![](image_rsrc171.jpg)![](image_rsrc11V.jpg)![](image_rsrc172.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)

## What is a Sequenced Collection ?

![](image_rsrc173.jpg)![](image_rsrc174.jpg)![](image_rsrc11P.jpg)Demo Sequenced Collection
![](image_rsrc175.jpg)![](image_rsrc11V.jpg)![](image_rsrc176.jpg)![](image_rsrc11P.jpg)How can we get reverse collection data from Sequenced collection?
![](image_rsrc177.jpg)![](image_rsrc11V.jpg)![](image_rsrc178.jpg)![](image_rsrc179.jpg)![](image_rsrc11V.jpg)![](image_rsrc17A.jpg)![](image_rsrc11P.jpg)Remove first/last element from Sequenced Collection
![](image_rsrc17B.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)ADD Element at last and first to Sequenced Collection ![](image_rsrc17C.jpg)![](image_rsrc11V.jpg)![](image_rsrc11P.jpg)

### What isStructured Concurrency ?

![](image_rsrc11P.jpg)Sample code to explain Structured Concurrency ![](image_rsrc17D.jpg)![](image_rsrc11V.jpg)

# Sample CODE

https://github.com/playwithjavaDOTin/Functional-Java-Practice.git

# My Author Profile

https://www.amazon.in/stores/Amitesh-Kumar-Ray/author/B0CJ5TLKFW?ref=ap_rdr&isDr amIntegrated=true&shoppingPortalEnabled=true