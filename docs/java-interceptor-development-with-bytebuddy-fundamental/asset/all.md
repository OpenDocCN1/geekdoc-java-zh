![](Image00058.jpg)

1

![](Image00000.gif)![](Image00001.jpg)

2

![](Image00000.gif)

Java Interceptor Development with ByteBuddy: Fundamental

Copyright © 2020, by MillionStrengthKnowledge.com, All rights reserved.

The publication of the book and source code are protected by copyright, and permission must be obtained from the MillionStrengthKnowledge. com prior to any prohibited reproduction, storage in a retrieval system, or transmission in any form or by any means, electronic, mechanical, photocopying, recording, or likewise.

Every effort has been made in the preparation of this book and source code to ensure the accuracy of the information presented. However, the information contained in this book and source code are sold without warranty and guarantee, either express or implied, as to the accuracy or completeness of or results to be obtained from using the book and source code. Neither the MillionStrengthKnowledge.com, author, nor its dealers and distributors will be held liable for any damages caused or alleged to be caused directly or indirectly by this book and source code. Under no circumstances shall MillionStrengthKnowledge.com, author, its dealers and distributors be liable for any indirect, incidental, special, punitive, consequential or similar damages that result from the use of or inability to use the book and source code, even if any of them has been advised of the possibility of such damages. This limitation of liability shall apply to any claim or cause whatsoever whether such claim or cause arises in contract, tort or otherwise.

First published: October 2020

https://millionstrengthknowledge.com

Unique Number: 18790-01-63329-3

3

![](Image00000.gif)

Author

My name is Eric Fong. I started my career as a software developer since 2001. I am experience in developing web application using Java, JavaEE and SpringFramework. I received a Master Degree in Management Information System from Coventry University. I am a Oracle Certified Java Programmer, EC-Council Certified Application Security Engineer in Java, and Arcitura Certified Microservice Architect.

I am the founder of MillionStrengthKnowledge.com. I created the GWT 2.8.1 Declarative User Interface Web Application Development Self Pace Training in year 2017, and ebook in year 2018. In year 2018, I also published another ebook titled GWT Responsive Web Application: Problem Solution Approach. I am very interested in Java and web application development, I enjoy doing research and development in Java during my spare time.

Acknowledgement

I would like to acknowledge the ByteBuddy project contributors that have put their great effort to make the ByteBuddy a successful open source library. ByteBuddy is an open source Java based library for Java bytecode generation and manipulation. ByteBuddy is licensed under Apache License Version 2.0, and is freely available on Github. Appreciate the open source community’s contribution, and the project constributor, Rafael Winterhalter, who has very actively participant in the github and stackoverflow forum to answer the technical question for the ByteBuddy.

4

![](Image00000.gif)

The learner of this book

The learner of this book should have knowledge in Java programming. This book is created for the learner who wants to learn on how to develop interceptor and Java code generation using ByteBuddy, and those who have knowledge in aspect oriented programming and wants to explore how ByteBuddy can develop the interceptor that has the result of aspect oriented code.

Source code

Source code can be downloaded using different methods. The method depends on which bookstore website learner purchases the ebook. If learner purchases the ebook from gumroad, then learner can download the source code from gumroad directly. If learner purchases the ebook from other websites, then please refer to this webpage for information about how to download the source code:

https://millionstrengthknowledge.com/#path- r=sourcecodeguideline.html

For general guideline, if the bookstore website is not gumroad, then learner is required to email the source code request to:

sourcecode@millionstrengthknowledge.com

The email must include either the receipt, invoice, order, or license number of the book purchased. After that, learner will receive an email reply that contains the source code zip file: javainterceptor.7z. The zip file is password protected. The password to unzip the zip file is the learner’s email address. Please refer to the URL stated above to learn about how to create the email of the source code request.

5

![](Image00002.gif)

Contents

[Author 3](#text00002.html__idContainer006)

[Acknowledgement 3](#text00002.html__idContainer006)

[The learner of this book 4](#text00003.html__idContainer009)

[Source code 4](#text00003.html__idContainer009)

[Chapter 1: Introduction 12](#text00011.html__idContainer033)

[Separating Functional Code and Non-Functional Code 13](#text00012.html__idContainer036)

[What is not covered in this book 16](#text00015.html__idContainer046)

[Java Decompiler 16](#text00015.html__idContainer046)

[Development Environment 17](#text00016.html__idContainer049)

[Conclusion 18](#text00017.html__idContainer052)

[Chapter 2: OnMethodEnter Advice 19](#text00018.html__idContainer055)

[Executing the project 21](#text00020.html__idContainer062)

[Maven Build Process 22](#text00021.html__idContainer066)

[Maven pom.xml error 29](#text00028.html__idContainer087)

[Difference between Java programming and Java Bytecode programming 29](#text00028.html__idContainer087)

[Chapter 3: OnMethodExit Advice 31](#text00030.html__idContainer093)

[Conclusion 33](#text00032.html__idContainer100)

[Chapter 4: Advice Method Parameter 34](#text00033.html__idContainer103)

[Conclusion 40](#text00039.html__idContainer121)

[Chapter 5: Intercepting Method Parameter, Method Return, and Instance Variable 42](#text00041.html__idContainer127)

[Intercepting method parameter value 45](#text00044.html__idContainer136)

[Intercepting instance and class variable 46](#text00045.html__idContainer139)

6

![](Image00002.gif)

[Intercepting method return value 47](#text00046.html__idContainer142)

[Conclusion 48](#text00047.html__idContainer145)

[Chapter 6: Intercepting Exception using @ OnMethodExit advice 49](#text00048.html__idContainer148)

[Data Type for @Thrown Annotated Parameter 53](#text00052.html__idContainer160)

[Data Type for onThrowable Attribute 54](#text00053.html__idContainer163)

[Throw New Exception from Advice Method 54](#text00053.html__idContainer163)

[Chapter 7: Passing Data from On Method Enter Advice to Exit Advice 57](#text00056.html__idContainer172)

[Conclusion 59](#text00058.html__idContainer178)

[Chapter 8: Around Advice 60](#text00059.html__idContainer181)

[Around Advice for create Method 62](#text00061.html__idContainer188)

[Around Advice for createData Method 66](#text00065.html__idContainer200)

[Execute the project 69](#text00068.html__idContainer209)

[@Origin annotation 70](#text00069.html__idContainer212)

[MethodDelegation and Advice 70](#text00069.html__idContainer212)

[Conclusion 71](#text00070.html__idContainer215)

[Chapter 9: Around Advice Method Parameter 72](#text00071.html__idContainer218)

[Conclusion 76](#text00075.html__idContainer230)

[Chapter 10: Generate Instance Variable 77](#text00076.html__idContainer233)

[Cloning instance variable with define method 78](#text00077.html__idContainer237)

[Generate new instance variable with defineField method 80](#text00079.html__idContainer243)

[The value Method 83](#text00082.html__idContainer252)

[Conclusion 83](#text00082.html__idContainer252)

7

![](Image00002.gif)

[Chapter 11: Generate Java Method 84](#text00083.html__idContainer255)

[InterceptorPlugin 87](#text00086.html__idContainer264)

[Generate method with MethodDelegation 92](#text00091.html__idContainer279)

[Generate method with Advice 94](#text00093.html__idContainer285)

[Generate method with local variable 96](#text00095.html__idContainer291)

[Generate method with nested visit 98](#text00097.html__idContainer297)

[Use array instead of HashMap 103](#text00102.html__idContainer312)

[Generate method with chain of MethodCall 103](#text00102.html__idContainer312)

[Configuring two plugin programs in maven pom.xml 109](#text00108.html__idContainer330)

[Conclusion 111](#text00110.html__idContainer336)

[Chapter 12: Generate Constructor 112](#text00111.html__idContainer339)

[Cloning the constructor with define method 114](#text00113.html__idContainer345)

[Generate constructor with defineConstructor method 115](#text00114.html__idContainer348)

[Generate constructor with visit method 120](#text00119.html__idContainer363)

[Conclusion 123](#text00122.html__idContainer372)

[Chapter 13: Generate Generic Constructor, Method, and Instance Variable 124](#text00123.html__idContainer375)

[Generic Class 126](#text00125.html__idContainer381)

[Generic Instance Variable 126](#text00125.html__idContainer381)

[Generic Method and Constructor 133](#text00132.html__idContainer402)

[Developing interceptor with generic type 139](#text00138.html__idContainer420)

[Conclusion 141](#text00140.html__idContainer426)

[Chapter 14: Add and Remove Java Annotation 142](#text00141.html__idContainer430)

[Add Java interface to Java class 145](#text00144.html__idContainer439)

[Add annotation to the Java class 146](#text00145.html__idContainer442)

[Remove annotation from the Java class 147](#text00146.html__idContainer445)

[Add annotation to Java method 150](#text00149.html__idContainer455)

8

![](Image00002.gif)

[Add nested annotation to Java method 152](#text00151.html__idContainer461)

[Remove annotation from Java method 155](#text00154.html__idContainer470)

[Add annotation to method parameter 157](#text00156.html__idContainer476)

[Remove annotation from method parameter 160](#text00159.html__idContainer485)

[Add annotation to the instance variable 163](#text00162.html__idContainer494)

[Remove annotation from the instance variable 164](#text00163.html__idContainer497)

[Add annotation on the constructor 165](#text00164.html__idContainer500)

[Remove annotation from the constructor 167](#text00166.html__idContainer506)

[Conclusion 167](#text00166.html__idContainer506)

[Chapter 15: Remove Constructor, Method, and Instance Variable 168](#text00167.html__idContainer509)

[Remove Constructor 170](#text00169.html__idContainer515)

[Remove method 171](#text00170.html__idContainer518)

[Remove instance variable 171](#text00170.html__idContainer518)

[Conclusion 171](#text00170.html__idContainer518)

[Chapter 16: Search and Replace 172](#text00171.html__idContainer521)

[Search and replace method in Java method 173](#text00172.html__idContainer524)

[Search and replace instance variable in Java method 174](#text00173.html__idContainer527)

[Conclusion 176](#text00175.html__idContainer533)

[Chapter 17: ElementMatchers 177](#text00176.html__idContainer537)

[InterceptorUtilPlugin 178](#text00177.html__idContainer540)

[ElementMatchers.isSetter 179](#text00178.html__idContainer543)

[ElementMatcherUtil 180](#text00179.html__idContainer546)

[ElementMatchers.isGetter 181](#text00180.html__idContainer549)

[ElementMatchers.isAnnotatedWith 182](#text00181.html__idContainer552)

[ElementMatchers.isConstructor 182](#text00181.html__idContainer552)

[ElementMatchers.returns, ElementMatchers. takesGenericArgument 184](#text00183.html__idContainer558)

9

![](Image00002.gif)

[ElementMatchers.canThrow, ElementMatchers.or 185](#text00184.html__idContainer561)

[InterceptorRepositoryPlugin 186](#text00185.html__idContainer564)

[ElementMatchers.nameStartsWith 188](#text00187.html__idContainer570)

[ElementMatchers.nameContainIgnoreCase 188](#text00187.html__idContainer570)

[ElementMatchers.not 189](#text00188.html__idContainer573)

[ElementMatchers.isVarArgs 190](#text00189.html__idContainer576)

[ElementMatchers.isOverriddenFrom 190](#text00189.html__idContainer576)

[InterceptorQueryPlugin 191](#text00190.html__idContainer579)

[FilterableList 192](#text00191.html__idContainer582)

[ElementMatchers.genericFieldType 196](#text00195.html__idContainer594)

[ElementMatchers.erasure 196](#text00195.html__idContainer594)

[ElementMatchers.isAnnotatedWith 197](#text00196.html__idContainer597)

[ElementMatchers.isDeclaredBy 198](#text00197.html__idContainer600)

[ElementMatchers.hasParameter and ElementMatcher 199](#text00198.html__idContainer603)

[Import static for ElementMatchers 201](#text00200.html__idContainer609)

[Conclusion 202](#text00201.html__idContainer612)

[Chapter 18: Generate Inner Class 203](#text00202.html__idContainer615)

[Generate first level inner class 212](#text00211.html__idContainer642)

[Generate method to inner class 214](#text00213.html__idContainer648)

[Generate second level inner class 214](#text00213.html__idContainer648)

[Adding second level inner class to first level inner class 218](#text00217.html__idContainer660)

[Adding first level inner class to outer class 218](#text00217.html__idContainer660)

[RepositoryPlugin 219](#text00218.html__idContainer663)

[Generate new method in inner class and anonymous class 220](#text00219.html__idContainer666)

[RepositoryPlugin does not instrument the inner class of DataReader. class 222](#text00221.html__idContainer672)

[Conclusion 223](#text00222.html__idContainer675)

10

![](Image00002.gif)

[Chapter 19: Generate Java Interface, Enum, Annotation, Subclass, and Abstract Class 224](#text00223.html__idContainer678)

[Generate new Java interface 224](#text00223.html__idContainer678)

[Generate new Java enum 227](#text00226.html__idContainer687)

[Generate new Java annotation 228](#text00227.html__idContainer690)

[Generate new Java class 233](#text00232.html__idContainer705)

[Generate lambda expression 234](#text00233.html__idContainer708)

[Generate new Java abstract class 236](#text00235.html__idContainer714)

[Instrumenting the User.class 237](#text00236.html__idContainer717)

[Rebase the Java class 240](#text00239.html__idContainer726)

[Conclusion 244](#text00243.html__idContainer738)

[Chapter 20: Instrumenting JDK Core Class 245](#text00244.html__idContainer741)

[InterceptorAgent 247](#text00246.html__idContainer747)

[Premain-Class attribute in MANIFEST.MF 250](#text00249.html__idContainer756)

[Maven pom.xml 250](#text00249.html__idContainer756)

[Execute the program in Eclipse 252](#text00251.html__idContainer762)

[Conclusion 255](#text00254.html__idContainer774)

11

![](Image00002.gif)

12

![](Image00000.gif)

Chapter 1: Introduction

ByteBuddy is an open source Java based library for Java bytecode generation and manipulation. ByteBuddy is licensed under Apache License Version 2.0, and is freely available on Github. This book uses the term instrumentation to describe the bytecode generation, manipulation, and interception. This book provides example codes that applies ByteBuddy capability to intercept, add, modify and delete existing functionality of one or more Java classes by modifying their bytecode.

With ByteBuddy, the instrumentation process can occur during maven build time, or application runtime.

Modern applications tend to be complex in nature because the application needs to fulfill different type of requirements, for example, functional requirement and non-functional requirement. These applications contains multiple modules with each of them has their own functional code. Because of the non-functional requirements, the functional code is surrounded by non-functional code, for example, security processing, logging, performance monitoring, resource usage tracing for pay-per-use billing, DevOps related processing, and others.

public double calculatePrice(){

double discount = getDiscount();

return this.price + this.deliveryCharge -

discount;

}

calculatePrice method without non-functional code

13

![](Image00000.gif)

@Secure(authority=”normalUser, premiumUser”)

public double calculatePrice(){

long startTime=System.currentMilliseconds();

logger.info(“Calculate price start”);

double discount = getDiscount();

double price =

this.price + this.deliveryCharge - discount

logger.info(“Method end”);

perfLogger.info(

“Calculate price execution time:”+

(System.currentMillioseconds()-

startTime));

return price;

}

calculatePrice method with non-functional code

The complexity increases when the non-functional code spans across multiple methods in the application, which causes tight coupling between functional code and non-functional code. The repeatedly use of non-functional code across methods of different classes impose copy-paste coding, which causes the code maintenance burden.

Separating Functional Code and Non- Functional Code

To remove the complexity, the application development team can separate the non-functional code from the application code, returns the method to its original form with pure functional code only. All the non-functional code will be re-factored into advice code .

The application development team then utilizes the bytecode instrumentation capability of ByteBuddy to produce the instrumented code .

14

![](Image00000.gif)

ByteBuddy adds the advice code to the functional code during maven build time or application runtime, and produces the instrumented code that contains the functional and non-functional code. The development team can configure the instrumentation programmatically using ByteBuddy.

ByteBuddy only changes the Java bytecode (Java class file), not the Java source code.

The benefits of using ByteBuddy:

ByteBuddy automates the coding via bytecode instrumentation.

ByteBuddy increases code reusability because all the non-functional code can be created in one advice code Java file, and then reuses many times in different method of different Java classes.

Modify bytecode without re-compilation of entire application

Modify bytecode without the need of restart of application server.

ByteBuddy uses these strategies to intercept the Java bytecode:

On Method Enter

On Method Exit

Around Advice

In this book, all the example codes is integrated into maven build process, therefore the interception and code generation are created during maven build time, not during the application runtime. There is only one chapter that will show on how to create interceptor during application runtime. However, the instrumentation used in maven

![](Image00007.jpg)

15

![](Image00000.gif)

build time are also applicable to instrumentation at application runtime.

ByteBuddy supports instrumentation that can inspect and modify existing Java bytecode. These techniques will be explained in this book:

Add new constructor, method and instance variable

Remove existing constructor, method and instance variable

Modify the value of instance variable.

Modify the value of method parameter.

Inspect the existing Java class structure, constructor signature, method signature, and instance variable.

Generate new generic Java class, constructor, method, and instance variable (upper bound, lower bound, multiple bound, wildcard, parameterized type, method type argument)

Search and replace code in the method.

Add and remove annotation that is annotated on Java class, constructor, method, instance variable, and parameter

Add and modify Java inner class (add first and second level inner class, intercepting inner class and anonymous class).

Generate new Java class, Java interface, enum, annotation, and abstract class.

Generate simple method and lambda expression.

Sharing data between advice codes.

Introduction to Java agent development with Java Instrumentation API and ByteBuddy, which can intercept JDK core class. (one chapter only)

This book provides example Java code for implementing the advice code and ByteBuddy plugin for bytecode instrumentation. Most of the example code in each chapter uses maven build process to create the instrumented code. There is one chapter that uses ByteBuddy with Java instrumentation API to create the instrumented code at

16

![](Image00000.gif)

application runtime.

What is not covered in this book

ByteBuddy is an open source library that contains many functionalities. However, this book does not cover these topics:

How to instrument Record component

How to instrument Java native method

How to instrument lambda expression

How to generate anonymous class

How to instrument Java bytecode using bytecode instruction, for example, stack manipulation, and ByteCodeAppender

Java Decompiler

Java decompiler is required to inspect the instrumented code that is in Java class format. Java decompiler can convert the class file into Java source code. This is important for verifying the generated bytecode. This is the list of Java decompiler that is free to use:

Online tools:

https://jdec.app

Offline tools:

JDecompiler

17

![](Image00000.gif)

Development Environment

IDE: SpringToolSuite4 version 4.8, any Java IDE is also applicable.

JDK: OpenJDK-11+28

ByteBuddy: version 1.10.16

Maven dependencies:

<dependency>

<groupId>net.bytebuddy</groupId>

<artifactId>byte-buddy</artifactId>

<version>1.10.16</version>

</dependency>

<dependency>

<groupId>net.bytebuddy</groupId>

<artifactId>byte-buddy-agent</artifactId>

<version>1.10.16</version>

</dependency>

<dependency>

<groupId>net.bytebuddy</groupId>

<artifactId>byte-buddy-maven-plugin

</artifactId>

<version>1.10.16</version>

</dependency>

18

![](Image00000.gif)

Conclusion

This chapter explains:

What is ByteBuddy

Definition of advice code, functional code, and instrumented code

How ByteBuddy helps in software design and coding

The knowledge and technique that will be learn in this book

Development environment used in this book

19

![](Image00000.gif)

Chapter 2: OnMethodEnter Advice

This chapter explains on how to implement the on method enter advice. This chapter also explains on how to build and execute the instrumentation process. This process will be repeated in every chapters of this book. The source code for this chapter is included in ChapterVisitOnMethodEnterAdvice Eclipse project. This is the project structure:

There are three packages: interceptor, plugin, and program.

Interceptor package contains the advice code, LogInterceptor.java .

![](Image00008.jpg)

20

![](Image00000.gif)

Plugin package contains the plugin program that provides the interception logic. In this example, InterceptorPlugin.java is the plugin program. Maven build process uses the plugin program to produce the instrumented code.

Program package contains the functional code, DataProducer.java , and one Java program, InterceptorProgram.java , which is used to execute the instrumented code, which can be used to test and view the result of the instrumentation.

target folder stores the result of maven build process, including Java class file, instrumented code, and jar file.

sourceCodeView folder stores the instrumented code in Java file format.

In this project, the create method of DataProducer.java is the method that provides the functional code. The method prints a status “create data” on screen.

The project adds advice code to create method of DataProducer.class . The advice code applies the On Method Enter advice. This type of advice will add the advice code at the start of the execution of Java method:

public void create(){

System.out.println(“create data”);

}

Functional code

public void create(){

LogInterceptor.logger.log(

Info.LEVEL, “Method start”);

System.out.println(“create data”);

}

Instrumented code

The plugin program will transform the Java bytecode (Java class file), no the Java source code. Therefore, after the instrumentation process, the Java source code remains unchanged, but the content of

21

![](Image00000.gif)

Java class file will change: the class file contains both advice code and functional code. The explanation above uses Java source code to show the instrumented code for easy-to-understand purpose. The project will also store this Java source code in the sourceCodeView folder.

Executing the project

The project uses maven buld process to produce the instrumented code. To start the maven build, executes the project using maven clean package -X command.

Follows these steps to execute clean package -X in Eclipse:

1. Right click on project root node ChapterVisitOnMethodEnter .

2. Select Run as -> Maven build. Eclipse will show the Edit Configuration window.

3. Enter clean package -X in Goals textbox.

4. Click Run button to start the maven build process.

![](Image00012.jpg)

22

![](Image00000.gif)

Once the maven build process completed, execute the InterceptorProgram.java :

1. Rigth click on InterceptorProgram.java , which is in the package explorer or project explorer of the Eclipse.

2. Select Run as -> Java application

The Eclipse will execute InterceptorProgram.java , and this is the result on Eclipse console:

Aug 1, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.program. DataProducer create INFO: Method start

create data

Maven Build Process

The maven build process consists of these processes:

1. Maven cleans the project target folder.

2. Maven compiles all the java source codes available in the project, and stores the Java class file in project target folder.

3. Maven executes the ByteBuddy instrumentation process by invoking the InterceptorPlugin.java.

4. The plugin program scans all the Java class file one by one in the project target folder.

5. For each Java class file, the plugin program invokes matches method to find the functional code for interception.

6. If found, then the matches method return true, and the plugin program continue to the apply method. If not found, then plugin program repeats the process starts from step 5.

7. In apply method, InterceptorPlugin.java applys the advice code to the functional code.

8. InterceptorPlugin.java creates the instrumented code in bytecode

23

![](Image00000.gif)

(Java class file) format and stores the code in the project target folder.

9. Maven repeats step 4 to step 8 until InterceptorPlugin.java checks all the class files in the project.

10. Maven creates a jar file that package all the Java class file, including the instrumented code.

This is the ByteBuddy configuration in the pom.xml:

<plugin>

<groupId>net.bytebuddy</groupId>

<artifactId>byte-buddy-maven-plugin

</artifactId>

<version>${bytebuddy.version}</version>

<executions>

<execution>

<goals>

<goal>transform</goal>

</goals>

</execution>

</executions>

<configuration>

<transformations>

<transformation>

<plugin>com.millionstrengthknowledge. interceptorprj.plugin.InterceptorPlugin</plugin>

</transformation>

</transformations>

</configuration>

</plugin>

The plugin requires the byte-buddy-maven-plugin . To enable the instrumentation process, the <goal> tag must have a value of transform . Therefore, another name for ByteBuddfy instrumentation process is transformation .

The <transformation> tag must have the fully qualified class name of the plugin program. The project uses com.millionstrengthknowledge. interceptorprj.plugin.InterceptorPlugin . The project can have one or more plugin programs .

24

![](Image00000.gif)

InterceptorPlugin

InterceptorPlugin.java is the plugin program that performs the matching logic and interception logic. The InterceptorPlugin.java implements the Java interface of net.bytebuddy.build.Plugin , and three methods are derived from the interface: matches, apply, close :

public class InterceptorPlugin

implements Plugin {

@Override

public boolean matches(

TypeDescription target) {

//code is omitted

}

@Override

public Builder<?> apply( Builder<?> builder,

TypeDescription typeDescription,

ClassFileLocator classFileLocator) {

/*code is omitted*/

}

@Override

public void close() throws IOException{

/*code is omitted*/

}

}

The plugin program will check all the Java class files in the project target folder. The plugin program invokes matches method to execute the first level matching logic. This is the matching logic implemented in the InterceptorPlugin.java :

public boolean matches(

TypeDescription target

) {

System.out.println(“Inspecting “+

target.getName());

25

![](Image00000.gif)

if(target.getName()

.equals(

DataProducer.class.getName())){

System.out.println(

“Found target code: “+

target.getName());

return true;

}

else {

System.out.println(“Inspected code “+

target.getName()+

” is not the target code”);

}

}

In line 7 to 9, the matching logic wants to find the DataProducer. class file. The logic compares the current Java class’s name with the DataProducer’s class name. The method returns true when the class name matches, otherwise the method prints a “Inspected code is not the target code” message and return false. The program will continue to apply method only when matches method return true.

The apply method provides the interception logic. The interception logic is the code that adds the advice code to functional code based on the state of second level matching logic. The second level matching logic further filters the Java class file found in matches method. The second level matching is based on the method name, field name, annotation, and other Java element of the found Java class file.

In ByteBuddy, most of the matching logic is created using net. bytebuddy.matcher.ElementMatchers . Chapter 17 will explain more example on the usage of ElementMatchers .

26

![](Image00000.gif)

This is the implementation of apply method of InterceptorPlugin.java :

public Builder<?> apply(

Builder<?> builder,

TypeDescription typeDescription,

ClassFileLocator classFileLocator

) {

return builder

.visit(

Advice.to(LogInterceptor.class)

.on(ElementMatchers

.named(“create”))

);

}

The first parameter, builder , is type of net.bytebuddy.dynamic. DynamicType.Builder . The method uses visit method of builder to add the advice code. Visit method will create the advice code that is in Java bytecode format, and then inlines the bytecode to the bytecode of the functional code.

Within visit method parenthesis, construct the advice configuration using Advice.to method. In this example, the Advice.to method specify the parameter value with “ LogInterceptor.class ”. LogInterceptor. java is the Java class that provides the advice code.

After that, specify the second level matching logic using on method.

The on method uses the ElementMatchers to specify the matching criteria. The criteria uses named method to match “ create ” method in DataProducer.class . ByteBuddy will only inline the advice code when the second level matching criteria returns true.

The named method finds the match based on exact name of Java element. Java element can be either method, field, generic type, and others. In this example, the named method is used to find the method with “ create ” name in DataProducer.class .

The plugin program does not use close method, which is one of the derived method of Plugin interface. The close method will be invoked only once after all the Java class files in the project target folder has been checked for the instrumentation. Therefore, the close

27

![](Image00000.gif)

method is suitable used to close any resources created in matches and apply method. This is the implementation of close method of InterceptorPlugin.java :

public void close() throws IOException {

System.out.println(“InterceptorPlugin close method”);

}

The method simply prints a message “InterceptorPlugin close method” on screen. All the trace generated from the plugin program can be viewed via Eclipse console.

Advice Code

This chapter uses on method enter advice. This is the implementation of advice code in LogInterceptor.java :

public class LogInterceptor {

public static Logger logger=

Logger.getLogger(LogInterceptor.class. getName());

@OnMethodEnter

public static void start() {

logger.log(Level.INFO, “Method start”);

}

}

In LogInterceptor.java, the start method is the method that provides the advice logic. The start method is very simple, the method simply creates a log message states that the instrumented method is started.

@OnMethodEnter annotation must be annotated on this method so that ByteBuddy knows the code segment that provides the advice logic. Besides that, the advice method must be static. Otherwise the instrumentation process will fail.

Therefore, ByteBuddy transforms the functional code into

28

![](Image00000.gif)

instrumented code via this process:

(1) Finds the static method with @OnMethodEnter annotation:

@OnMethodEnter

public static void start() {

logger.log(Level.INFO, “Method start”);

}

(2) Convert the method content into bytecode that is valid for Java execution. In this case, this will be:

From

logger.log(Level.INFO, “Method start”)

To

LogInterceptor.logger.log(Level.INFO, “Method start”) .

(3) After that, ByteBuddy adds the generated bytecode into DataProducer.class : So, the result of instrumented code contains the non-functional code and functional code:

public void create() {

LogInterceptor.logger.log(Level.INFO,

“Method start”);

System.out.println(“create data”);

}

Please be noticed that ByteBuddy only processes the Java bytecode in Java class format. This means the DataProducer.java remains unchanged, but the DataProducer.class will change. The explanation above uses Java source code to explain for easy-to-understand purpose.

29

![](Image00000.gif)

Maven pom.xml error

In Spring Tool Suite, the Eclipse project will show this error message: “Plugin execution not covered by lifecycle configuration bytebuddy maven plugin” in pom.xml. The error does not affect the instrumentation process. Therefore, just ignore the error. To ignore the error, in Spring Tool Suite, goto windows menu->Preferences- >Maven->Errors/warning, disable the error by “ignore”.

Difference between Java programming and Java Bytecode programming

Java programing is different from Java bytecode programming because Java bytecode programming programs according to Java class syntax, while Java programming uses Java language syntax. For example, Java programming permits this type of initialization of value of instance variable:

public class DataProducer{

private String data=”<noData>”;

}

However, in Java bytecode, this is no effective. JVM will not raise runtime exception for this, but the code is simply not effective, that means the data instance variable will remain null value. To properly initialize the value of instance variable in Java bytecode, the initialization must be done via constructor:

public class DataProducer{

private String data;

public DataProducer(){ data=”<noData>”; }

}

Therefore, whenever learner develops code for interceptor or code generation in ByteBuddy, the learner must develop the Java code according to Java bytecode syntax. Java Virtual Machine Specification is the document that provides more information on Java bytecode, and the document is available for download from the Internet.

30

![](Image00000.gif)

Nevertheless, most of the Java programming syntax are still applicable because ByteBuddy will translate it accordingly. There are some exception cases that must be aware of. This book will explain about this type of exception when the example code has this type of situation.

Conclusion

This chapter explains:

How to execute ByteBuddy instrumentation process in Eclipse

The instrumentation process via Maven build process.

How to execute generated bytecode via InterceptorProgram.java, and view its result on console

The configuration of plugin in pom.xml

How to create plugin program

How to create On Method Enter advice

How to inline bytecode of advice code into bytecode of functional code by using the visit method of net.bytebuddy.dynamic. DynamicType.Builder

31

![](Image00000.gif)

Chapter 3: OnMethodExit Advice

The source code for this chapter is included in ChapterVisitOnMethodExit Eclipse project. This is the project structure:

The project structure has the same structure with the project structure in Chapter 2 . All the code have the same implementation with the code in Chapter 2 . The only difference is that the LogInterceptor.java uses @OnMethodExit annotation in this chapter.

![](Image00013.jpg)

32

![](Image00000.gif)

This chapter applies On Method Exit advice. On Method Exit advice adds the advice code at the end of the method execution.

public void create(){

System.out.println(“create data”);

}

Functional code

public void create(){

System.out.println(“create data”);

LogInterceptor.logger.log(

Info.LEVEL, “Method end”);

}

Instrumented code

This is the advice code for this chapter:

public class LogInterceptor {

public static Logger logger=

Logger.getLogger(LogInterceptor.class

.getName());

@OnMethodExit

public static void methodEnd() {

logger.log(Level.INFO, “Method end”);

}

}

Advice code

To implement On Method Exit advice, the advice code annotates the methodEnd static method with the @OnMethodExit annotation. ByteBuddy then inlines the bytecode of the advice code to the create method, and produces the instrumented code stated above.

To view the result of the instrumented code, executes the maven build process, and then the InterceptorProgram.java , according to the steps stated in Chapter 2.

33

![](Image00000.gif)

The result of execution of the instrumented code should be similar to this, which is available in Eclipse console:

create data

Oct 1, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.program. DataProducer create

INFO: Method end

Conclusion

This chapte explains on how to create On Method Exit advice

34

![](Image00000.gif)

Chapter 4: Advice Method Parameter

Advice code can declare both On Method Enter and On Method Exit advice in the same advice code Java file. The static method of the advice code can also have parameter. For example, the implementation of the LogInterceptor.java (in ChapterAdviceMethodParameter Eclipse project) has used several parameters in the advice method:

public class LogInterceptor {

public static Logger logger=

Logger.getLogger(

LogInterceptor.class.getName());

@Advice.OnMethodEnter

public static void methodStart(

int param1,

String param2,

@Advice.Origin String mtd,

@Advice.Origin(“#t”) String mtdDeclrType,

@Advice.Origin(“#m”) String mtdName,

@Advice.Origin(“#d”) String mtdDescr,

@Advice.Origin(“#s”) String mtdParamType,

@Advice.Origin(“#r”) String mtdReturn,

@Advice.Argument(0) int id,

@Advice.Argument(1) String data,

@Advice.AllArguments Object[] params,

@Advice.This Object thiz,

@Advice.FieldValue(“recordId”) int data1,

@Advice.FieldValue(“descr”) String data2,

@Advice.Unused String unusedParam

) {

//code is omitted

}

35

![](Image00000.gif)

@Advice.OnMethodExit

public static void methodEnd(

@Advice.Return(typing=Assigner.Typing

.DYNAMIC) Object returnObject

) {

//code is omitted

}

}

Observed that various types of annotation have been applied to the parameters of methodStart method. The first and second parameter do not use any annotation. When no annotation is used, this means the parameter are implicitly mapped to the parameter of functional method. In this example, DataProducer.java is the functional code , and create method is the functional method .:

public class DataProducer {

public int recordId=1;

private String descr=”privateData”;

public void create(int id, String data) {

System.out.println(“create data”);

}

}

Therefore, the param1 and param2 of methodStart are mapped to all the parameters of create method. Developer must ensure that they have the same data type. The param1 and param2 contains the value of the id and data parameter of create method. For example, executes this InterceptorProgram.java after instrumentation process. InterceptorProgram.java contains this line of code:

new DataProducer.create(10000, “privateValue”);

The value of first and second parameter are 10000 and “ privateValue ” respectively. These values are copies to the param1 and param2 parameter of methodStart method of LogInterceptor.java during the instrumentation process.

36

![](Image00000.gif)

The remaining parameters in methodStart that starts from third parameter onwards, are the advice mapping parameter. Advice mapping parameter must use advice annotation.

@Origin annotation provides the method signature of functional method of functional code. For example,

Parameter: @Advice.Origin String mtd

System.out.println(mtd);

prints this string value on the screen:

public void com.millionstrengthknowledge.

interceptorprj.program.DataProducer.create(int,

java.lang.String)

@Origin(“#t”) annotation provides the class name of the functional code, which declares the create method. For example:

Parameter: @Advice.Origin(“#t”) String mtdDeclrType

System.out.println(mtdDeclrType);

prints this string value on the screen:

com.millionstrengthknowledge.interceptorprj.

program.DataProducer

@Origin(“#m”) annotation provides the method name of the functional method. For example:

Parameter: @Advice.Origin(“#m”) String mtdName

System.out.println(mtdName);

prints this string value on the screen:

create

37

![](Image00000.gif)

@Origin(“#d”) annotation provides the method descriptor of the create method. For example,

Parameter: @Advice.Origin(“#d”) String mtdDescr

System.out.println(mtdDescr);

prints this string value on the screen:

(ILjava/lang/String;)V

@Origin(“#s”) annotation provides a string that lists the data type of all the parameters of the create method. For example,

Parameter: @Advice.Origin(“#s”) String mtdParamType

System.out.println(mtdParamType);

prints this string value on the screen because the parameter of the create method uses int and String:

(int,java.lang.String)

@Origin(“#r”) annotation provides the data type of return of functional method. For example,

Parameter: @Advice.Origin(“#r”) String mtdReturn

System.out.println(mtdReturn);

prints this string value on the screen because the create method returns void:

void

@Argument annotation provides the value of parameter of create method. This annotation accepts one integer parameter that represents the index number of method parameter. For example, InterceptorProgram.java invokes:

new DataProducer.create(10000, ”testValue”);

38

![](Image00000.gif)

Parameter:

@Advice.Argument(0) int id

@Advice.Argument(1) String value

System.out.println(id+” “+value);

prints this string value on the screen:

10000 testValue

Index 0 means first parameter, index 1 means second parameter, and so on.

@AllArguments annotation provides the value of all the parameters of create method in object array format. For example, InterceptorProgram.java invokes:

new DataProducer.create(10000, ”testValue”);

Parameter:

@Advice.AllArguments Object[] params

System.out.println(params[0]+” “+params[1]);

prints this string value on the screen:

10000 testValue

@This annotation provides the Java object of the functional code. For example:

Parameter: @Advice.This Object thiz

System.out.println(thiz.getClass()

.getName());

prints this string value on the screen:

com.millionstrengthknowledge.interceptorprj

.program.DataProducer

39

![](Image00000.gif)

@FieldValue annotation provides the value of the instance variable of the functional code. This annotation accepts one parameter that represents the name of the instance variable. For example, DataProducer.java declares these two instance variables:

public int recordId=1;

private String descr=”privateData”;

Parameter:

@Advice.FieldValue(“recordId“) int data1

@Advice.FieldValue(“descr“) String data2

System.out.println(data1+” “+data2);

prints this string value on screen:

1 privateData

@Unused annotation indicates that the parameter is used for internal usage only for methodStart method of LogInterceptor.java . The parameter does not have mapping capability to functional code. It is just a marker annotation indicates that the parameter does not map to any of the parameter of functional method. For example,

Parameter:

@Advice.Unused String unusedParam

If there is parameter of methodStart method without any annotation and the parameter index does not match with the index of parameter of the functional method, the instrumentation process will fail during maven build process.

40

![](Image00000.gif)

@Return annotation is applicable only on advice method that is annotated with @OnMethodExit annotation. @Return provides the value of return of create method. For example:

Parameter: @Advice.Return(typing=Assigner.Typing. DYNAMIC) Object returnObject

System.out.println(returnObject);

prints this string value on the screen:

null

Observed that the value return null. This is because the create method return void. The returnObject should have value when the method returns object reference. In later chapter, there is example code that shows how to manage the method that returns the object reference. For now, please note that when the method return void, the parameter value of returnObject is always null. The @Return annotation must specify value for typing attribute for void return, and its value must be Assigner.Typing.DYNAMIC. The DYNAMIC is required for void return.

Conclusion

This chapter explains on how to create parameter in advice method. Various type of annotation are explained:

@Advice.Origin

@Advice.Origin(“#t”)

@Advice.Origin(“#m”)

@Advice.Origin(“#d”)

@Advice.Origin(“#s”)

@Advice.Origin(“#r”)

@Advice.Argument

@Advice.AllArgument

41

![](Image00000.gif)

@Advice.This

@Advice.FieldValue

@Advice.Unused

@Advice.Return

42

![](Image00000.gif)

Chapter 5: Intercepting Method Parameter, Method Return, and Instance Variable

This chapter explains on how to alter the value of method parameter, method return, and instance variable of functional code via advice code. The source code for this chapter is included in ChapterAdviceParameterIntercept Eclipse project.

This is the code for DataProducer.java , which is the functional code:

public class DataProducer {

public static String CLASSNAME=

”DataProducer”;

public int recordId=1;

private String descr=”someData”;

public int create(int id, String data) {

System.out.println(

“Parameter data: “+id+”, “+data);

System.out.println(

“Instance variable data: “+

recordId+”, “+descr+”, “+CLASSNAME);

if(data!=null)

return 1;

else

return -1;

}

}

43

![](Image00000.gif)

DataProducer.java declares one functional method named create , which takes two parameters. The create method prints its parameter value, and the value of instance variables of recordId , descr , and CLASSNAME on the screen. After that, the method return an integer value of either 1 or -1, based on the value of data parameter.

When these lines of program statement (which is in InterceptorProgram.java ) is executed without advice code:

int dataReceived=

new DataProducer().create(10000,”test”);

System.out.println(

“ Data returned from create() : “+ dataReceived);

The program produces this result on the screen:

Parameter data: 10000, test

Instance variable data: 1, someData, DataProducer

Data returned from create(): 1

Now execute the maven build process, and then InterceptorProgram. java , the program produces this result on the screen:

Parameter data: 20000, test2

Instance variable data: 2, new data, DataProducer1

Data returned from create(): -2

Observed that the data returned on the screen has been changed even though the same program InterceptorProgram.java is executed:

Parameter data: “ 10000, test” changed to “ 20000, test2”

Instance variable: “ 1, someData, DataProducer ” changed to “ 2, new data, DataProducer1 ”

Data returned from create(): “ 1 ” changed to “ -2 ”

44

![](Image00000.gif)

The data changes occurs because the advice code intercepts the value during instrumentation process.

This is the code for the DataInterceptor.java , which is the advice code in this chapter:

public class DataInterceptor {

@Advice.OnMethodEnter

public static void methodStart(

@Advice.Argument(value=0, readOnly=false)

int param1,

@Advice.Argument(value=1, readOnly=false,

typing=Assigner.Typing.DYNAMIC)

Object param2,

@Advice.FieldValue(value=”recordId”,

readOnly=false) int data1,

@Advice.FieldValue(value=”descr”,

readOnly=false,

typing=Assigner.Typing.DYNAMIC)

Object data2,

@Advice.FieldValue(value=”CLASSNAME”,

readOnly=false,

typing=Assigner.Typing.DYNAMIC)

Object data3

) {

param1=20000;

param2=”test2”;

data1=2;

data2=”new data”;

data3=”DataProducer1”;

}

@Advice.OnMethodExit

public static void methodEnd(

@Advice.Return(readOnly=false)

int returnObject

) {

45

![](Image00000.gif)

returnObject = -2;

}}

To intercept the value of parameter, instance variable, and return object, the instrumentation process must implement the on method enter advice, on method exit advice, and the plugin program. This chapter will focus on explaining the implementation of advice code because the plugin program is similar to the previous chapter.

Intercepting method parameter value

To alter the value of id parameter of create method of DataProducer. java , DataInterceptor.java uses @Argument annotation on param1 parameter:

@Advice.Argument(value=0, readOnly=false) int param1

The value attribute uses value of 0, which means this parameter is mapped to the first parameter of the create method. The annotation specifies false value for readOnly attribute, this means the advice method wants to alter the value of the first parameter of the create method. The default value for readOnly attribute is true, which prevent the advice code from altering the parameter value. Therefore, the advice method can alter the value from 10000 to 20000 (line 21):

param1=20000;

Next, this annotation is configured to alter the value of second parameter of create method:

@Advice.Argument(value=1, readOnly=false,

typing=Assigner.Typing.DYNAMIC) Object param2

The value attribute of 1 means the param2 is mapped to data parameter of create method. The readOnly attribute of false means the value of data parameter is alterable, and param2 parameter maps

46

![](Image00000.gif)

to the data parameter. The third attribute, typing , has the value of Assigner.Typing.DYNAMIC . The data parameter is a java.lang.String, and the advice method attempts to use java.lang.Object to map the param2 parameter. In order for param2 to have other data type than java.lang.String, the typing attribute must have value of DYNAMIC . Otherwise, the maven build process will fail.

The typing attribute of advice annotation is defaulted to STATIC. When typing is STATIC, the param2 must have the exact same data type with its mapping parameter. Because of the param2 wants to use java.lang. Object, so the DYNAMIC typing is the right attribute value.

Therefore, with these configurations in the @Argument annotation, the advice code can alter the value of param2 from “test” to “test2” (line 22):

param2=“test2”;

Intercepting instance and class variable

The advice method also alters the value of instance variable and class variable of DataProducer.java . There is one class variable named CLASSNAME , and two instance variables named recordId and descr .

To alter the value of instance or class variable, @FieldValue annotation is used instead of @Argument . This annotation is configured to alter the value of the recordId :

@Advice.FieldValue(value=”recordId”,

readOnly=false) int data1

To map the data1 parameter to recordId instance variable, the value attribute specifies the name of the instance variable, “ recordId ”. The readOnly attribute has false value, which means the value of recordId variable is alterable in the advice method. Therefore, the line 24 changes the value of recordId variable from 1 to 2 :

data1=2;

This annotation is configured to alter the value of descr instance

47

![](Image00000.gif)

variable in DataProducer.java :

@Advice.FieldValue(value=”descr”,

readOnly=false,

typing=Assigner.Typing.DYNAMIC) Object data2

This annotation wants to use java.lang.Object data type to map the data type of descr instance variable, which is java.langString. Therefore, the typing attribute must use the value of Assigner.Typing.DYNAMIC . With these configurations, the line 25 changes the value of descr variable from “ some data ” to “ new data ”:

data2=”new data”;

The @FieldValue can also alter the class variable of functional code. This annotation is configured for this purpose:

@Advice.FieldValue(value=”CLASSNAME”,

readOnly=false,

typing=Assigner.Typing.DYNAMIC) Object data3

With these configuration, the line 26 changes the value of CLASSNAME variable from “ DataProducer ” to “ DataProducer1 ”:

data3=”DataProducer1”;

Intercepting method return value

Besides of altering value of method parameter and instance variable, the advice code also can alter the value of return of the create method. For this purpose, @Return annotation must be used on the parameter of the on method exit advice method:

29. @Advice.OnMethodExit

30. public static void methodEnd(

31. @Advice.Return(readOnly=false)

32. int returnObject

33\. ) {

34. returnObject = -2;

35. }

48

![](Image00000.gif)

With @Return annotation, the value changes on the returnObject variable in methodEnd method will be reflected in the return value of create method. With the configuration, the line 34 alters the return value from 1 to -2 :

returnObject = -2;

Conclusion

This chapter explains:

How to alter the value of method parameter of functional method

How to alter the value of instance variable of functional code

How to alter the value of return of functional method

49

![](Image00000.gif)

Chapter 6: Intercepting Exception using @ OnMethodExit advice

Advice code can intercept the exception thrown from the functional code. Advice code can also suppress the exception to null, or throw a new exception to replace the exception thrown. This chapter explains about the advice code that can intercept the exception. The source code for this chapter is included in ChapterAdviceExceptionIntercept Eclipse project.

This is the functional code used in this chapter:

public class DataProducer {

public void create(String data) {

if(data==null)

throw new IllegalArgumentException(

“Data cannot be null”);

System.out.println(“create data: “+data);

}

}

The functional code has a create method that takes one java.lang.String argument. The method throws IllegalArgumentException when the data parameter is null, otherwise the method prints a status with the value of data parameter on the screen.

50

![](Image00000.gif)

This is the advice code used in this chapter:

public class ExceptionInterceptor {

public static Logger logger=

Logger.getLogger(

ExceptionInterceptor.class.getName());

@Advice.OnMethodExit(

onThrowable=Throwable.class)

public static void methodEnd(

@Advice.Thrown(readOnly=false)

Throwable excp

) {

if(excp==null) {

logger.log(

Level.INFO,

“Method end with no exception”);

}

else {

logger.log(

Level.INFO,

“Method end with exception: \n”+

“========================== \n”+

“Exception type: “+

excp.getClass()

.getName()+”\n”+

“Exception message: “+

excp.getMessage()

);

}

excp=null;

}

}

51

![](Image00000.gif)

The InterceptorProgram.java is used to test the instrumentation result:

public class InterceptorProgram {

public static void main(String args[]) {

new DataProducer().create(null);

}

}

InterceptorProgram.java is a executable Java program. It instantiates an instace of DataProducer.java , and then invokes the create method with null parameter. Execute the InterceptorProgram.java without the maven build process, the program throws the IllegalArgumentException because data parameter is null:

Exception in thread “main”

java.lang.IllegalArgumentException: data cannot be null

at com.millionstrengthknowledge.interceptorprj.program. DataProducer.create(DataProducer.java:15)

at com.millionstrengthknowledge.interceptorprj.program. InterceptorProgram.main(InterceptorProgram.java:14)

After that, starts the maven build process, and then execute the InterceptorProgram.java in the Eclipse project, the program will create this result on the screen:

Aug 01, 2020 1:00:00 PM com.millionstrengthknowledge

.interceptorprj.program.DataProducer create

INFO: Method end with exception:

==========================

Exception type: java.lang.IllegalArgumentException

Exception message: Data cannot be null

After the instrumentation process, the instrumented code prints the exception information on the screen instead. However, there is no exception stack trace showed on the screen, this is because the advice code suppresses the exception to null.

Advice code can only intercept the exception in the method that is annotated with @OnMethodExit annotation. @OnMethodExit annotation must specify the Java exception class name in the

52

![](Image00000.gif)

onThrowable attribute:

@Advice.OnMethodExit(onThrowable=Throwable. class)

public static void methodEnd(

@Advice.Thrown(readOnly=false) Throwable excp

)

By default, the advice method will be skipped if create method thows exception. To enable the instrumented code continues its method exection to advice code, the onThrowable attribute must be used. The instrumented method execution will continue to advice method if the exception thrown from the instrumented code is equivalent to the class or derived class of the exception defined in the onThrowable attribute.

Observed that the parameter of methodEnd , named excp , is annotated with the @Thrown annotation. This parameter captures the exception thrown from the instrumented method. For example, if the instrumented method throws IllegalArgumentException, then the value of the excp parameter will be the instance of IllegalArgumentException that is thrown from the instrumented method.

To alter the exception thrown from the instrumented method, the readOnly attribute of the @Thrown annotation must be set to false.

In this example, the advice method captures the exception and prints the exception class and its exception message on the screen. The instrumented code does not throw the exception because the advice code suppresses the exception at the line 30:

excp = null;

53

![](Image00000.gif)

If line 30 is omitted from the advice code, then the instrumented method will throw exception:

Aug 01, 2020 1:00:00 PM com.millionstrengthknowledge

.interceptorprj.program.DataProducer create

INFO: Method end with exception:

==========================

Exception type: java.lang.IllegalArgumentException

Exception message: Data cannot be null

Exception in thread “main” java.lang. IllegalArgumentException: data cannot be null

at com.millionstrengthknowledge.interceptorprj.program. DataProducer.create(DataProducer.java:5)

at com.millionstrengthknowledge.interceptorprj.program. InterceptorProgram.main(InterceptorProgram.java:14)

If the InterceptorProgram.java changes to this line of code:

new DataProducer().createData(“create”);

Then the instrumented code will produce this result on the screen:

create data: test

Oct 1, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.program. DataProducer create

INFO: Method end with no exception

Data Type for @Thrown Annotated Parameter

The data type for excp parameter must be either same class or the derived class of the exception class thrown from the instrumented code. Otherwise, the instrumented code will throw runtime exception - java.lang.ClassCastException. For example:

public static void methodEnd(

@Advice.Thrown(readOnly=false) Error excp)

Observed that excp parameter has data type of java.lang.Error, this will

54

![](Image00000.gif)

cause ClassCastException during application runtime because Java cannot cast java.lang.IllegalArgumentException to java.lang.Error.

Data Type for onThrowable Attribute

Advice code can only have one On Method Exit advice. Therefore, to manage all the exception type in the advice method, the onThrowable attribute should use the Throwable.class , which enables advice method to capture java.lang.Exception and java.lang.Error, and the exceptions that are the derived class of java.lang.Exception and java.lang.Error.

If the exception thrown from the instrumented code does not match with the class specified in onThrowable attribute, the advice method will be skipped. For example, with this configuration

@Advice.OnMethodExit(onThrowable=Exception.class)

If instrumented code throws java.lang.Error, then the advice method will be skipped.

Throw New Exception from Advice Method

Advice method can throw new exception, which alters the original exception thrown from the instrumented code. If the line 30 of ExceptionInterceptor.java is replaced with this line:

throw new RuntimeException(“Runtime exception”);

Then instrumented code will throw the RuntimeException instead.

What if the advice method throws checked exception instead of RuntimeException, and methodEnd adds the valid throws clause?

55

![](Image00000.gif)

@Advice.OnMethodExit(onThrowable=Throwable. class)

public static void methodEnd(

@Advice.Thrown(readOnly=false) Throwable excp

) throws Exception{

.

.

.

throw new Exception(“checked exception”);

}

The instrumented code will throw the checked exception also, similar to the the result of throwing RuntimeException in advice method.

However, please be aware that the functional method has no throws clause in the create method of DataProducer.java :

public class DataProducer {

public void create(String data) {

if(data==null)

throw new IllegalArgumentException(

“Data cannot be null”);

System.out.println(“create data: “+data);

}

}

According to Java compilation process, the create method must declare the throws clause when the method throws checked exception. Otherwise, the program will receive compilation error. However, in Java bytecode format, the throw clause is optional when the program throws checked exception. Therefore the generated code executes without runtime error.

This is the important difference between Java programming and Java bytecode programming. Java programming deals with the Java file, and Java bytecode programing deals with the Java class file. They have different syntax, the exception management is one of the example.

Conclusion

This chapter explains:

56

![](Image00000.gif)

How to use onThrowable attribute of @OnMethodExit annotation to manage exception

How to map exception thrown from instrumented code to advice method via @Thrown annotated parameter

How to suppress exception

57

![](Image00000.gif)

Chapter 7: Passing Data from On Method Enter Advice to Exit Advice

This chapter provides an example on how to pass data from On Method Enter advice to On Method Exit advice. The source code is included in ChapterPassingDataBetweenAdvice Eclipse project.

This is the functional code for this chapter:

public class DataProducer {

public void create() {

System.out.println(“create data”);

}

}

The logic of the functional code is very simple: prints a status “create data” on the screen. This is the advice code used for this chapter:

public class LogInterceptor {

public static Logger logger=

Logger.getLogger(LogInterceptor.class

.getName());

@Advice.OnMethodEnter

public static String methodStart() {

String sharedDataVar=”user01 record”;

logger.log(

Level.INFO, “Method start: “+sharedDataVar);

return sharedDataVar;

}

58

![](Image00000.gif)

@Advice.OnMethodExit

public static void methodEnd(

@Advice.Enter String data

) {

logger.log(Level.INFO, “Method end: “+ data);

}

}

The advice code uses both on method enter and on method exit advice, which is implemented in methodStart and methodEnd method respectively. There is a local variable sharedDataVar in the methodStart method. The methodStart method wants to shared the data stored in sharedDataVar variable with the methodEnd method.

In order to achieve the data sharing between advice methods, methodEnd method must annotate the @Enter annotation on one of its parameter. In this example, this parameter is the data parameter. Apart from that, the methodStart method must return the sharedDataVar . With these implementations, then ByteBuddy can pass the value stored in sharedDataVar to the data parameter.

To see the effect of data sharing capability, executes the maven build process, and then executes the InterceptorProgram.java . The program will produce this result on the screen:

Aug 01, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.program. DataProducer create

INFO: Method start: user01 record

create data

Aug 01, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.program. DataProducer create

INFO: Method end: user01 record

Observed that methodEnd method can print the value of “user01 record”, which is passed from the methodStart method.

59

![](Image00000.gif)

Conclusion

This chapter explain:

How to pass data from on method enter advice method to on method exit advice method

60

![](Image00000.gif)

Chapter 8: Around Advice

Apart from on method enter and on method exit advice, ByteBuddy supports around advice . Around advice adds the advice code to the start and end of the functional method, via method delegation.

The source code for this chapter is included in ChapterAroundAdvice Eclipse project, and this is the structure for the project:

![](Image00022.jpg)

61

![](Image00000.gif)

This chapter uses two advice codes: PerfObjectReturnInterceptor. java , and PerfVoidReturnInterceptor.java . PerfObjectReturnInterceptor.java is used to intercept functional method that has return object, and PerfVoidReturnInterceptor.java is used to intercept functional method that has void return.

This is the functional code for this chapter:

public class DataProducer {

public void create() {

System.out.println(“create data”);

}

public String createData() {

String uniqueId=UUID.randomUUID().toString();

return new String(

Base64.getEncoder().encode(

uniqueId.getBytes()),

Charset.forName(“UTF-8”)

);

}

}

The create method prints a status string “create data” on the screen. The createData method returns a base64 encoded UUID.

This is the implementation of apply method in InterceptorPlugin.java :

public Builder<?> apply(

Builder<?> builder, TypeDescription td,

ClassFileLocator cfl

) {

return builder

.method(ElementMatchers.named(“create”))

.intercept(

MethodDelegation.to(

PerfVoidReturnInterceptor.class)

)

62

![](Image00000.gif)

.method(ElementMatchers.named(“createData”))

.intercept(

MethodDelegation.to(

PerfObjectReturnInterceptor.class));

}

Around Advice for create Method

In the apply method, the method method of builder is invoked. The method method uses ElementMatchers.named to build the matching logic. The named method uses “create” for its parameter value:

builder

.method(ElementMatchers.named(“create”))

So, the create method of DataProducer.java is selected for instrumentation. After that, the plugin program invokes the builder’s intercept method. The parameter of intercept method specifies “ MethodDelegation .to(PerfVoidReturnInterceptor.class) ”:

return builder

.method(ElementMatchers.named(“create”))

.intercept(

MethodDelegation.to(

PerfVoidReturnInterceptor.class)

)

These methods are totally different from the on method enter/exit advice. First, the builder invokes intercept method to perform the instrumentation, but not the visit method. The instrumentation then uses MethodDelegation.to instead of Advice.to method. The matching logic is implemented via method method, but not the on method in the method chain of Advice.to method.

63

![](Image00000.gif)

This is the code for PerfVoidReturnInterceptor.java :

public class PerfVoidReturnInterceptor {

public static Logger logger=

Logger.getLogger(

PerfVoidReturnInterceptor.class.getName());

public static void aroundVoid(

@SuperCall Runnable targetCode,

@Origin Method method){

long startTime=

System.currentTimeMillis();

logger.log(

Level.INFO,“Method start”);

targetCode.run();

logger.log(

Level.INFO, “Method end: “+

method.getName()+” execution time: “+

(System.currentTimeMillis()-

startTime));

}

}

These are the requirements for implementing around advice that supports void return:

The advice method is a static method. (line 6)

The advice method returns void. (line 6)

The advice method has one java.lang.Runnable parameter, and it is annotated with @SuperCall annotation. (line 7)

In this example, aroundVoid method is the advice method. ByteBuddy will produce the instrumented code based on the method content of aroundVoid method. Because of MethodDelegation , and @SuperCall annotation, ByteBuddy creates a proxy class to implement the instrumented code.

64

![](Image00000.gif)

The purpose of the advice code is to measure the runtime performance of the functional code. The targetCode parameter represents the functional code: create method of DataProducer.java . The line 9 to 20 means the instrumented code will execute these instructions:

Stores the method start time to the startTime variable

Log a message that indicates the method execution is started

Executes the functional code, which prints a status “create data” on the screen.

Log a message that indicates the method execution is ended, and also the method execution time in milliseconds.

Start the maven build process and execute InterceptorProgram.java , This is the result that the instrumented code produces on the screen:

Aug 01, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.interceptor

.PerfVoidReturnInterceptor aroundVoid

INFO: Method start

create data

Aug 01, 2020 1:00:00 PM com. millionstrengthknowledge.interceptorprj.interceptor

.PerfVoidReturnInterceptor aroundVoid

INFO: Method end: create execution time: 250

Method delegation generates bytecode that is different from the visit method. To gain more understanding about the difference, let’s looks into the Java source code view of the generated bytecode:

public class DataProducer{

public DataProducer(){ }

public void create(){

class auxiliary.mxySvqOW

implements Runnable, Callable{

public void run(){

argument0

.createOriginal();

}

65

![](Image00000.gif)

public Object call(){

argument0

.createOriginal();

return null;

}

private DataProducer argument0;

auxiliary.mxySvqOW(){

argument0 = DataProducer.this;

}

}

PerfVoidReturnInterceptor.

aroundVoid(

new auxiliary.mxySvqOW(), mtd);

}

private void createOriginal(){

System.out.println(“create data”);

}

private static final Method mtd =

DataProducer.class.getMethod(“create”);

//other code is omitted

}

In the generated bytecode, ByteBuddy creates a new private method named createOriginal , and copies the method content of original create method to that method (line 32 - 34).

ByteBuddy then modifies the create method. ByteBuddy declares a inner class named auxiliary.mxySvqOW insides the create method. This inner class is the proxy class. The proxy class contains a reference to the functional code: DataProducer.java . The proxy class uses the argument0 to store this reference (line 19), which is passed

66

![](Image00000.gif)

via the proxy class’s constructor. The proxy class implements two Java interfaces: java.lang.Runnable, and java.util.concurrent.Callable. Their derived method call and run invokes the createOriginal method via the argument0 instance variable. ByteBuddy then uses PerfVoidReturnInterceptor.java to invoke the aroundVoid method (line 27 - 30), at the end of create method. In aroundVoid method of PerfVoidReturnInterceptor.java, the method invokes the targetCode. run , in which the run method is the implementation of java.lang. Runnable in auxiliary.mxySvqOW .

Even though PerfVoidReturnInterceptor.java specifies only the Runnable for the SuperCall parameter, however, ByteBuddy implements both Runnable and Callabled interface implicitly in its generated bytecde (line 6). Nevertheless, if the functional method return void, then the @SuperCall annotated parameter should uses java.lang.Runnable in advice code.

Before this section ends, please be noticed that ByteBuddy can generate different bytecode for the around advice. For example, ByteBuddy can generate the inner class that is not included in the method, and additional accessor method to access the create method. Nevertheless, the generated code will apply proxy class to implement the around advice.

Around Advice for createData Method

Similarly, to intercept createData method of DataProducer.java , this is the code segment of InterceptorPlugin.java for that purpose:

.method(ElementMatchers.named(“createData”))

.intercept(

MethodDelegation.to(

PerfObjectReturnInterceptor.class)

)

The createData method is a method that returns java.lang.String object. The PerfObjectReturnInterceptor.java is the advice code for createData method:

public class PerfObjectReturnInterceptor {

67

![](Image00000.gif)

public static Logger logger=

Logger.getLogger(

PerfObjectReturnInterceptor.class

.getName());

@RuntimeType

public static Object aroundReturn(

@SuperCall Callable<Object> targetCode,

@Origin Method method

)throws Throwable {

long startTime=

System.currentTimeMillis();

logger.log(Level.INFO, “Method start”);

Object result=targetCode.call();

logger.log(Level.INFO, “Method end: “+

method.getName()+ “ execution time: “+

(System.currentTimeMillis()-startTime));

return result;

}

}

These are the requirements for implementing around advice that supports return object of the functional method:

The advice method is a static method. (line 8)

The advice method returns Object instance, or the type that follows the return type of functional method . (line 8)

The advice method has one java.util.concurrent.Callable parameter, and it is annotated with @SuperCall annotation. (line 9)

The advice method is annotated with the @RuntimeType annotation. (line 7)

68

![](Image00000.gif)

Even though the advice code uses Callable interface instead of Runnable , ByteBuddy will generate the similar bytecode that is generated for create method. The only difference is that the createData method of DataProducer.java will invoke the aroundReturn method of PerfObjectReturnInterceptor.java (line 20 -22, at the end of createData method), and its first parameter uses the instance of proxy class of auxiliary.xMxeqXab (line 20):

public void createData(){

class auxiliary.xMxeqXab

implements Runnable, Callable{

public void run(){

argument0.createDataOriginal();

}

public Object call(){

return argument0

.createDataOriginal();;

}

private DataProducer argument0;

auxiliary.xMxeqXab(){

argument0 = DataProducer.this;

}

}

return (String)PerfObjectReturnInterceptor.

aroundReturn(

new auxiliary.xMxeqXab(), mtd2);

}

private static final Method mtd2 =

DataProducer.class.

getMethod(“createData”);

69

![](Image00000.gif)

The aroundReturn method can alter the return value of functional code. If aroundReturn method adds this line of code before the aroundReturn method returns:

result =”test”;

Then the return value will be changed to “test”, which replaces the base64 encoded UUID.

@RuntimeType annotation is required if the advice method wants to return value.

Execute the project

In order to see the result of the instrumentation process, execute the maven build process, and then executes the InterceptorProgram.java . The InterceptorProgram.java will produce this result on the screen:

Oct 01, 2020 1:00:00 AM com. millionstrengthknowledge.interceptorprj.interceptor. PerfVoidReturnInterceptor aroundVoid

INFO: Method start

create data

Oct 01, 2020 1:00:00 AM com. millionstrengthknowledge.interceptorprj.interceptor. PerfVoidReturnInterceptor aroundVoid

INFO: Method end: create execution time: 348

Oct 01, 2020 1:00:00 AM com. millionstrengthknowledge.interceptorprj. interceptor.PerfObjectReturnIn terceptor aroundReturn

INFO: Method start

Oct 01, 2020 1:00:01 AM com. millionstrengthknowledge.interceptorprj.interceptor. PerfObjectReturnInterceptor aroundReturn

INFO: Method end: createData execution time: 400

The result shows that the execution time of create method is 348 milliseconds, and createData method is 400 milliseconds.

70

![](Image00000.gif)

@Origin annotation

Observed that the advice method has a second parameter, which is annotated with @Origin annotation. Please be aware that this annotation is the net.bytebuddy.implementation.bind.annotation. Origin , not the net.bytebuddy.asm.Advice.Origin , which is used for on method enter or exit advice. Advice.Origin returns a String value that contains the name of the functional method. While Origin of around advice returns an instance of java.lang.reflect.Method that represents the functional method. For example:

public static void aroundVoid(

@SuperCall Runnable targetCode,

@Origin Method method){

System.out.println(method.getName());

}

The getName method returns “ create ”, which is the name of functional method.

MethodDelegation and Advice

The difference between MethodDelegation and Advice:

MethodDelegation is used by the intercept method of the DynamicType.Builder.

Advice is used by the visit method of the DynamicType.Builder.

When using intercept method, ByteBuddy does not inline the advice code , but generates a delegated method and invokes the delegated method to execute the functional code. In this chapter, the createOriginal and createDataOriginal method are the example of delegated method.

When using visit method, ByteBuddy generates the code that does inline the advice code into the functional code.

Both MethodDelegation and Advice can apply on method enter or exit advice, but Advice cannot apply the around advice.

71

![](Image00000.gif)

Conclusion

This chapter explains:

How to create around advice for functional method that returns void

How to create around advice for functional method that returns object reference

72

![](Image00000.gif)

Chapter 9: Around Advice Method Parameter

The advice method of around advice can use binding annotation to annotate its parameter. These annotations are used to access the Java element of the functional code when around advice is used. This chapter provides the example code that explains on how to use these annotations. The source code for this chapter is included in ChapterAroundMethod Eclipse project. This is the code for PerfReturnInterceptor.java, which uses the binding parameter:

public class PerfReturnInterceptor{

public static Logger logger=

Logger.getLogger(

PerfReturnInterceptor.class.getName());

@RuntimeType

public static Object aroundReturn(

@Super Object zuper,

@SuperCall Callable<Object>

instrumentedMethod,

@SuperMethod Method superMethod,

@This Object target,

@Origin Method method,

@AllArguments Object[] args,

@Argument(0) int p1,

@Argument(1) String p2,

@FieldValue(“objectId”) int data1,

@FieldValue(“data”) String data2

)throws Throwable {

long startTime=

System.currentTimeMillis();

logger.log(

Level.INFO, “Method start: \n”+

“ @Super: “+zuper.getClass()

.getName()+”\n”+

73

![](Image00000.gif)

“ @SuperMethod: “+

superMethod.getName()+”\n”+

“ @This: “+target.getClass()

.getName()+”\n”+

“ @AllArguments length: “+

args.length+”\n”+

“ @AllArguments [0]: “+((int)args[0])+”\n”+

“ @AllArguments [1]: “+

((String)args[1])+”\n”+

“ @Argument(0): “+p1+”\n”+

“ @Argument(1): “+p2+”\n”+

“ @FieldValue(‘objectId’): “+data1+”\n”+

“ @FieldValue(‘data’): “+data2+”\n”

);

Object result=instrumentedMethod.call();

logger.log(Level.INFO, “Method end: “+

method.getName()+” execution time: “+

(System.currentTimeMillis()-startTime));

return result;

}

}

The aroundReturn method is a around advice that can return an object. The method uses these annotation, which is included in net. bytebuddy.implementation.bind.annotation package:

@Super

@SuperMethod

@This

@AllArguments

@Argument

@FieldValue

74

![](Image00000.gif)

@Super annotation provides the instance of proxy class that is generated by ByteBuddy.

Parameter: @Super Object zuper

System.out.println(zuper.getClass().

getName());

prints this string value on the screen:

com.millionstrengthknowledge.interceptorprj

.program.DataProducer$auxiliary.mxySvqOW

@SuperMethod annotation provides the instance of java.lang.reflect. Method that representes the delegated method:

Parameter: @SuperMethod Method superMethod

System.out.println(superMethod.getName());

prints this string value on the screen:

createDataOriginal

The example here provides a simple method name. ByteBuddy can actually create the method name with random character, for example, createData$original$AOgPLhp9$accessor$sMMz5BQl

@This annotation provides the instance of the functional code. For example:

Parameter: @This Object target

System.out.println(target.getClass()

.getName());

prints this string value on the screen:

com.millionstrengthknowledge.interceptorprj

.program.DataProducer

75

![](Image00000.gif)

@AllArguments annotation provides the value of all the parameters of createData method in object array format. For example, InterceptorProgram.java invokes:

new DataProducer.create(1, ”base64”);

Parameter:

@AllArguments Object[] args

System.out.println(args[0]+” “+args[1]);

prints this string value on the screen:

1 base64

@Argument annotation provides the value of parameter of createData method. This annotation accepts one integer parameter that represents the index number of method parameter. For example, InterceptorProgram.java invokes:

new DataProducer.create(1, ”base64”);

Parameter:

@Argument(0) int p1

@Argument(1) String p2

System.out.println(p1+” “+p2);

prints this string value on the screen:

1 base64

Index 0 means first parameter, index 1 means second parameter, and so on. Around advice cannot alter the value of the parameter of functional method.

@FieldValue annotation provides the value of the instance variable of the functional code. This annotation accepts one parameter that represents the name of the instance variable. For example, DataProducer.java declares these two instance variables:

76

![](Image00000.gif)

public int objectId=-1;

private String data=”producer data”;

Parameter:

@FieldValue(“objectId“) int data1

@FieldValue(“data“) String data2

System.out.println(data1+” “+data2);

prints this string value on screen:

-1 producer data

Different from the @FieldValue used in on method enter/exit advice, the @FieldValue annotation for around advice cannot alter the value of instance variable of functional code.

Conclusion

This chapter explains about how to use parameter on advice method of around advice, with these annotations:

@Super

@SuperMethod

@This

@AllArguments

@Argument

@FieldValue

77

![](Image00000.gif)

Chapter 10: Generate Instance Variable

This chapter explains on how to use ByteBuddy to generate instance variable for the Java class dynamically. The source code for this chapter is included in ChapterDefineInstanceVariable Eclipse project. The project does not have the interceptor package, instead, there is a prototype package.

In this chapter, DataProducer.java is the functional code:

public class DataProducer {

private int data=-1;

}

The DataProducer.java is very simple, the class contains one instance

![](Image00033.jpg)

78

![](Image00000.gif)

variable named data , and has no method. All the code generation logic is implemented in the InterceptorPlugin.java . The plugin program adds multiple new instance variables into the DataProducer.class . After the instrumentation process, this is the bytecode generated by the ByteBuddy for DataProducer.class (the bytecode uses Java source code view for easy-to-understand purpose, this file is available in sourceCodeView folder ):

public class DataProducer{

private int data = -1;

public static final String FINAL_DATA =

“test1”;

private int number;

private long longData;

public static final long SERIALNUMBER = 12345L;

private long number1;

protected long number2;

volatile long number3;

private transient long number4;

long number5;

public static final long number6;

private volatile transient long number7;

}

Cloning instance variable with define method

The apply method of InterceptorPlugin.java is responsible to generate the instance variables. The first generated instance variable is the FINAL_DATA , and these are the code statements for this purpose:

Field f1=InstanceVariablePrototype.class

.getDeclaredField(“FINAL_DATA”);

builder.define(f1).value(“test1”);

ByteBuddy clones the field declaration of FINAL_DATA from InstanceVariablePrototype.class into DataProducer.class . This is the declaration of FINAL_DATA variable in InstanceVariablePrototype.

79

![](Image00000.gif)

java:

public final static String FINAL_DATA=

”example final data”;

The apply method firstly declares f1 local variable that is type of java.lang.reflect.Field , and uses the Field capability to access the declaration information of the FINAL_DATA variable. The apply method then declare the test1 variable by using define method of builder, and provides the default value “ test1 ”, using the value method:

builder.define(f1).value(“test1”)

Therefore, this is the code generated for FINAL_DATA in DataProducer. class:

public static final String FINAL_DATA=“test1”;

Next, the apply method clones the number variable from InstanceVariablePrototype.java into DataProducer.class . These are the code statements for this purpose:

Field f2=InstanceVariablePrototype.class

.getDeclaredField(“number”);

builder.define(f2);

In InstanceVariablePrototype.java, the number variable has a @ Deprecated annotation:

@Deprecated private int number=10000;

However, the instrumentation process will not clone the annotation of the source variable, and its value. Therefore, this is the instrumentation result for number variable in DataProducer.class :

private int number;

Observed that the modifier of the number is private, this is because the modifier of the number variable in InstanceVariablePrototype.

80

![](Image00000.gif)

java is private. The define method clones the modifier.

These are the code statements that clones the longData variable from InstanceVariablePrototype.java:

Field f3=InstanceVariablePrototype.class

.getDeclaredField(“longData”);

builder.define(f3);

Therefore, this is the instrumentation result for longData variable in DataProducer.class :

private long longData;

Generate new instance variable with defineField method

ByteBuddy also can declare new instance variable without cloning. ByteBuddy uses defineField method for this purpose. This is the code for declaring SERIALNUMBER variable in the DataProducer.class :

builder.defineField(

“SERIALNUMBER”,

long.class,

Visibility.PUBLIC,

FieldManifestation.FINAL,

Ownership.STATIC)

.value(12345L)

The first parameter of defineField method specifies the name of the instance variable. The second parameter specifies the data type. The third parameter is a variable length argument, it is used to specify the modifier of the instance variable. In this example, these modifier classes are used:

net.bytebuddy.description.modifier.Visibility

net.bytebuddy.description.modifier.FieldManifestation

net.bytebuddy.description.modifier.Ownership

81

![](Image00000.gif)

The Visibility is used to specifies the visibility: public, private, protected, package access . The FieldManifestation is used to specifies final or volatile keyword for the instance variable. The Ownership is used when the program wants to declare static .

Therefore, the instrumentation process generates this declaration for the SERIALNUMBER variable:

public final static long SERIALNUMBER=12345L;

Next, the plugin program declares a private instance variable named number1 :

builder.defineField(“number1”, long.class, Visibility.PRIVATE);

This declaration uses Visibility.PRIVATE , and this is the result of instrumentation:

private long number1;

To declare protected variable, uses Visibility.PROTECTED :

.defineField(“number2”, long.class,

Visibility.PROTECTED)

The result of the instrumentation:

protected long number2;

To declare package_private volatile variable:

.defineField(“number3”, long.class, Visibility. PACKAGE_PRIVATE, FieldManifestation.VOLATILE)

The result of the instrumentation:

volatile long number3;

82

![](Image00000.gif)

To declare private transient variable:

.defineField(“number4”, long.class, Visibility. PRIVATE, FieldPersistence.TRANSIENT)

The result of the instrumentation:

private transient long number4;

To declare variable without specifying the visibility modifier:

.defineField(“number5”, long.class)

If modifier is not specified, then the variable is defaulted to package access:

long number5;

net.bytebuddy.jar.asm.Opcodes is another method to specify the modifier for the instance variable. For example, this line declares public final static variable:

builder.defineField(“number6”, long.class, Opcodes.ACC_PUBLIC | Opcodes.ACC_FINAL | Opcodes.ACC_STATIC);

The result of the instrumentation:

public final static long number6;

Opcodes can combine several modifiers in one line, with each modifier is separated by a “|” character. Another example that uses Opcodes :

builder.defineField(“number7”, long.class, Opcodes.ACC_PRIVATE | Opcodes.ACC_VOLATILE | Opcodes.ACC_TRANSIENT);

The result of the instrumentation:

private volatile transient number7;

83

![](Image00000.gif)

The value Method

The value method only works for static variable. For example, the SERIALNUMBER is a static variable:

builder.defineField(“SERIALNUMBER”, long.class, Visibility.PUBLIC, FieldManifestation.FINAL, Ownership.STATIC).value(12345L);

With this configuration, the SERIALNUMBER instance variable will have long value of 12345. If the value method is used on non-static instance variable, for example:

builder.defineField(“number1”, long.class,

Visibility.PRIVATE).value(1000L);

The long value of 1000 will not be set to number1 instance variable. To set value to instance variable, the value must be set via the constructor. This is because the Java bytecode specification requires the constructor to set the value for instance variable. The Chapter 12 will explain on how to set value to instance variable in the constructor.

Conclusion

This chapter explains on how to declare instance variable dynamically.

84

![](Image00000.gif)

Chapter 11: Generate Java Method

This chapter explains on how to generate Java method dynamically into the functional code. DataProducer.java is the functional code for this chapter:

public abstract class DataProducer {

private String data;

}

After instrumentation process, the DataProducer.class should include these Java methods:

public abstract class DataProducer {

private String data;

private int numberData;

public void setNumberData(int var1) {

this.numberData = var1;

}

public int getNumberData() {

return this.numberData;

}

protected String getData() {

return this.data;

}

protected void setData(String var1) {

this.data = var1;

}

85

![](Image00000.gif)

public static int calculate(int p1,int p2) {

return -1;

}

private long getInstantTime() {

return -1L;

}

public abstract void process1();

public static final void process2(

final String strParam) {

}

private static final boolean process3() {

return false;

}

private synchronized String process4() {

return null;

}

private strictfp String process5() {

return null;

}

private String process6(int p1, String p2) {

return null;

}

private BigInteger process7(String var1)

throws NoSuchMethodException,

SecurityException, InstantiationException,

IllegalAccessException,

IllegalArgumentException,

InvocationTargetException {

return BigIntegerProducer.create(var1);

}

86

![](Image00000.gif)

private String process8(String var1,

int... var2) {

//code is omitted

}

public int process9(long var1) {

//code is omitted

}

public int process10(long var1, Map var3) {

//code is omitted

}

public int[] process11(long p1, int[] p2) {

//code is omitted

}

}

The source code for this chapter is included in ChapterDefineMethod Eclipse project. ByteBuddy provides these APIs for declaring new method dynamically, which is available in net.bytebuddy.dynamic. DynamicType.Builder :

define

defineProperty

defineMethod

Different from instance variable, Java method has method body. So, after the method is declared, the plugin program needs to define the method body. There are two plugin programs used in this chapter: InterceptorPlugin.java , InterfacePlugin.java ,

87

![](Image00000.gif)

InterceptorPlugin

The chapter firstly explains the InterceptorPlugin.java . The first method that the plugin program creates is the calculate method. This is the plugin program code for this purpose:

Method m1=MethodPrototype.class

.getDeclaredMethod(“calculate”,

int.class, int.class);

builder.define(m1).intercept(FixedValue.value(-1));

After instrumentation process, this is the instrumented code:

public static int calculate(int var0, int var1) {

return -1;

}

ByteBuddy clones the method declaration of calculate from MethodPrototype.class into DataProducer.class . This is the declaration of calculate method in MethodPrototype.java:

public static int calculate(int a, int b) {

return a+b;

}

The define method clones the modifier, method name, return data type, and parameter, but the method does not clone the method body. The apply method uses net.bytebuddy.implementation.FixedValue to create the method body for calculate method. FixedValue.value(-1) creates one line of bytecode that return -1 value.

FixedValue is a utility class provided by ByteBuddy. The FixedValue provides many convenience methods to create one line method body for the generated Java method. For example, FixedValue.nullValue() method creates a method body that returns null value.

After that, the plugin program clones the getInstantTime method from MethodPrototype.class into DataProducer.class . These are the codes for this purpose:

Method m2=MethodPrototype.class

.getDeclaredMethod(“getInstantTime”);

88

![](Image00000.gif)

builder.define(m2).intercept(FixedValue.value(-1L));

produces this instrumented code:

private long getInstantTime() {

return -1L;

}

The original getInstantTime method has one @Deprecated annotation. However, the annotation is not cloned via define method. The defineProperty , and defineMethod also have the same behavior.

The defineProperty method is used to create public setter and getter method. For example, this code:

builder.defineProperty(“numberData”, int.class);

generates these lines of code in DataProducer.class :

private int numberData;

public void setNumberData(int var1){

numberData= var1;}

public int getNumberData(){ return numberData; }

However, defineProperty can only declare setter and getter method that have public visibility. To declare setter and getter method that have other visibility than public, uses defineMethod for this purpose. For Example:

builder

.defineMethod( “getData”, String.class,

Visibility.PROTECTED )

.intercept( FieldAccessor.ofField( “data” ))

.defineMethod( “setData”, void.class,

Visibility.PROTECTED )

.withParameter(String.class)

.intercept( FieldAccessor.ofField( “data” ));

produces this instrumented code:

protected String getData(){ return data; }

89

![](Image00000.gif)

protected void setData(String var1){ data=var1;}

defineMethod method accepts three parameters. The first parameter is the method name, second method is the return data type, and third parameter is the method visibility. To create the method body of the getter method, the FieldAccessor is used. Because the getData wants to return the value of data instance variable, FieldAccessor. ofField(“data”) produces the bytecode for this purpose.

The setter requires one parameter of String. To configure the parameter for the method, withParameter method is used. The withParameter is suitable for method that has only one parameter. Because of data instance variable is a String, specifies String.class for the argument of withParameter so that the method will create a String parameter. Similar to getter method, uses FieldAccessor.ofField(“data”) to generate the setter method body.

FieldAccessor.ofField method is another useful utility class provided by ByteBuddy. The same method can be applied to both setter and getter method and it can generate the necessary code intelligently.

The withoutCode method is used to generate the abstract method. For example:

builder.define(“process1”, void.class,

Visibility.PUBLIC).withoutCode()

will generate this line of bytecode:

public abstract void process1();

Next, this is the code used to declare public final static method:

builder.defineMethod(“process2”,

void.class, Visibility.PUBLIC,

MethodManifestation.FINAL, Ownership.STATIC)

.withParameter(

String.class, “strParam”,

ParameterManifestation.FINAL)

90

![](Image00000.gif)

.intercept(StubMethod.INSTANCE)

produces this instrumented code:

public final static void process2(

final String strParam){ }

The code has used several new classes from ByteBuddy to generate the code:

net.bytebyddy.description.modifier.MethodManifestation

net.bytebyddy.description.modifier.ParameterManifestation

net.bytebyddy.description.modifier.Ownership

net.bytebuddy.implementation.StubMethod

The MethodManifestation , and Ownership are used to specify the modifier for the Java element. The StubMethod is a special Java class used to return default value of the method. The process2 is the method that has void return, therefore the use of StubMethod generates empty code for void return. To obtain the instance of the StubMethod, invokes its INSTANCE method. StubMethod is an intelligent component because it can generate the return statement based on the return data type of the method.

The process2 has one parameter, which is final . To configure final parameter, the withParameter method is used. The withParameter can accept three parameters. The first parameter specifies the data type of the parameter, the second parameter is the name of the parameter, and third parameter specifies its modifier. The declaration uses ParameterManifestation.FINAL to specify the final parameter

Next example generates a method that return boolean value, the same code StubMethod.INSTANCE is used, but it can generate “return false” for the method:

builder.defineMethod(“process3”, boolean.class,

Opcodes.ACC_PUBLIC | Opcodes.ACC_FINAL |

Opcodes.ACC_STATIC)

.intercept(StubMethod.INSTANCE)

91

![](Image00000.gif)

produce this instrumented code:

public final static boolean process3() {

return false;

}

net.bytebuddy.jar.asm.Opcodes is another Java class that can be used to specify the modifier of the Java element. The code above produces a public final static method. The benefit of using Opcodes is that it can specify the several modifiers in one line, with each modifier separated by using a “|” character.

This line of code declares a synchronized method:

builder.defineMethod(“process4”, String.class,

Visibility.PRIVATE,

SynchronizationState.SYNCHRONIZED)

.intercept(FixedValue.nullValue())

produces this instrumented code:

private synchronized String process4(){

return null; }

To specify the synchronized keyword on the method, the SynchronizationState.SYNCHRONIZED is used. This method uses nullValue method of FixedValue to generate bytecode that return null value.

This line of code declares a strictfp method:

builder.defineMethod(“process5”, String.class,

Visibility.PRIVATE, MethodStrictness.STRICT )

.intercept(FixedValue.nullValue())

produces this instrumented code:

private strictfp String process5(){

return null; }

92

![](Image00000.gif)

To specify the strictfp keyword on the method, the MethodStrictness. STRICT is used.

This line of code declares a method with multiple parameters:

builder.defineMethod(“process6”, String.class, Visibility.PRIVATE)

.withParameters(int.class, String.class)

.intercept(FixedValue.nullValue())

produces this instrumented code:

private String process6(int var0, String var1){

return null; }

To declare multiple parameters in one line, withParameters method is used. Each of the argument of withParameters method is mapped to the individual parameter of the generated method.

Generate method with MethodDelegation

ByteBuddy can generate method body using net.bytebuddy. implementation.MethodDelegation and net.bytebuddy. asm.Advice . This line of code shows an example that applies MethodDeletgation :

builder.defineMethod(“process7”,

BigInteger.class,

Visibility.PRIVATE)

.withParameter(String.class)

.throwing(

NoSuchMethodException.class,

SecurityException.class,

InstantiationException.class,

IllegalAccessException.class,

IllegalArgumentException.class,

InvocationTargetException.class

93

![](Image00000.gif)

)

.intercept(MethodDelegation.to(

BigIntegerProducer.class))

produces this instrumented code:

private BigInteger process7(String var0)

throws NoSuchMethodException, SecurityException,

InstantiationException, IllegalAccessException,

IllegalArgumentException,

InvocationTargetException{

return BigIntegerProducer.create(var0);

}

The plugin program invokes the intercept method, and uses the MethodDelegation.to(BigIntegerProducer.class) for its parameter. The code also declares the throws clause for the method by using the throwing method. The throws clause is required because the advice method of BigIntegerProducer.class has the throws clause. This is the source code of BigIntegerProducer.java:

public class BigIntegerProducer {

@OnMethodExit

public static BigInteger create(String param)

throws NoSuchMethodException,

SecurityException, InstantiationException,

IllegalAccessException,

IllegalArgumentException,

InvocationTargetException {

Constructor c=BigInteger.class

.getDeclaredConstructor(String.class);

return (BigInteger) c.newInstance(param);

}

}

Therefore, the process7 method must have the same throws clause with the advice code, and the throwing method is used to map the exception. The advice code purposely uses Java reflection technique to instantiate the instance of BigInteger because the example wants

94

![](Image00000.gif)

to demonstrate on how to map the exception. MethodDelegation does not inline the advice code into process7 method. Instead, ByteBuddy generates bytecode that invokes the create static method of BigIntegerProducer.class in the method body of process7 method.

Generate method with Advice

The next example shows on how to generate method body using the Advice. The plugin program firstly uses the defineMethod to declare the method, uses FixedValue to create the method body, and then uses visit method to modify the method body:

builder=builder.defineMethod(

“process8”, String.class,

Opcodes.ACC_PRIVATE | Opcodes.ACC_VARARGS

)

.withParameter(String.class)

.withParameter(int[].class)

.intercept(FixedValue.nullValue());

builder=builder

.visit(Advice.to(UuidGeneratorForInline.class)

.on(ElementMatchers.named(“process8”)));

This is the code for UuidGeneratorForInline.java :

public class UuidGeneratorForInline {

@OnMethodExit

public static void generate(

@Return(readOnly=false) String data,

@Argument(0) String param

) {

String uuid=UUID.randomUUID().toString();

if(param.equals(“base64”))

data= Base64.getEncoder()

.encodeToString(uuid.getBytes(

95

![](Image00000.gif)

Charset.forName(“UTF-8”)));

else

data= uuid;

}

}

The intercept method generates the method body that returns null value. The visit method overwrites the method body of the process8 method by using the advice code. The visit method clones the method body of exit advice method from UuidGeneratorForInline.class , and inlines the code into the process8 method of DataProducer.class . This is the process8 method after instrumentation process:

private String process8(

String var1, int... paramInt) {

String var2 = null;

String var3 = UUID.randomUUID().toString();

if (var1.equals(“base64”)) {

var2 = Base64.getEncoder().encodeToString(

var3.getBytes(

Charset.forName(“UTF-8”)));

} else {

var2 = var3;

}

return var2;

}

Observed that the second parameter is a variable length parameter. In order to create this type parameter, creates the last parameter of the method with an array type, then uses Opcodes.ACC_VARARGS modifiers at the third parameter of the defineMethod method.

96

![](Image00000.gif)

Generate method with local variable

The next example shows on how to generate method body and declares a local variable in the method body. The plugin program uses defineMethod to declare the method, uses FixedValue to create the method body, and then uses visit method to modify the method body:

builder.defineMethod(

“process9”, int.class, Visibility.PUBLIC

)

.withParameter(long.class)

.intercept(FixedValue.value(0));

builder=builder

.visit(Advice.to(PriceProcessorAdvice.class)

.on(ElementMatchers.named(“process9”)));

The visit method applies the PriceProcessorAdvice.class :

public class PriceProcessorAdvice {

@Advice.OnMethodEnter

public static void start(

long id,

@Local(“total”) int totalParam

) {

int price=new PriceQuery().query(id);

int discount=

new DiscountQuery().query(id);

totalParam=price-discount;

}

@Advice.OnMethodExit

public static void end(

@Local(“total”) int totalParam,

@Return(readOnly=false) int returnTotal

) {

returnTotal=totalParam;

}}

97

![](Image00000.gif)

The advice code declares both on method enter and exit advices. The advice code uses one new annotation named @Local . The @Local annotation is included in net.bytebuddy.asm.Advice package. The @Local annotation is used to declare the local variable in the method body. In advice code, this variable is a parameter. After instrumentation process, the parameter will be changed into local variable in the method body of the instrumented code.

The @Local annotation must be declared in the method with @ OnMethodEnter annotation. To use the local variable in exit advice, annotate one of the parameter in exist advice with the @Local annotation, and the annotation must have the same value with the @ Local annotation in enter advice if they are referring to the same local variable. In this example, the local variable has a name of “ total ”.

The advice code performs the price calculation. The result of the calculation is stored into the totalParam , which is the parameter annotated with @Local annotation. The calculation is performed in the on method enter advice method, named “ start ”. The start method uses the PriceQuery.java and DiscountQuery.java to query the price and discount. These two Java classes returns the price and discount in int format. For demonstration purpose, the value of price and discount is hard-coded in the PriceQuery.java and DiscountQuery.java . So, they returns the value of 280 and 10 respectively, via the query method.

The on method exit advice method, named “ end ”, reuses the totalParam , and passed the value of totalParam to returnTotal . The returnTotal is the parameter declared in the end method, and it uses @ Return annotation. Therefore, the returnTotal will be available in the instrumented code, and it can be returned via the return statement of the instrumented method.

98

![](Image00000.gif)

This is the result of the instrumented code for process9 method:

public int process9(long paramLong){

int p = 0;

int j = new PriceQuery().query(paramLong);

int m = new DiscountQuery().query(paramLong);

p = j - m;

long var1 = paramLong;

int k = 0;

k = p;

return k;

}

Observed that the generated bytecode uses different variable name, p , for the totalParam even though the @Local annotation declares the name “ total ”. There are some unexpected variables generated also, for example,var1. Please be noticed that ByteBuddy can generate different code whenever the build process is re-executed. However, ByteBuddy generates the instrumented code that can perform the correct calculation.

Generate method with nested visit

Next, the plugin program declares the process10 method:

builder=builder.defineMethod(

“process10”, int.class, Visibility.PUBLIC

)

.withParameter(long.class)

.withParameter(Map.class)

.intercept(FixedValue.value(0));

builder=builder

.visit(Advice.to(LocalVariableAdvice.class)

.on(ElementMatchers.named(“process10”)))

.visit(Advice.to(PriceQueryAdvice.class)

.on(ElementMatchers.named(“process10”)))

.visit(Advice.to(DiscountQueryAdvice.class)

.on(ElementMatchers.named(“process10”)));

99

![](Image00000.gif)

The plugin program uses defineMethod to declare the process10 method. The process10 method is a public method that returns a int value. The withParameter is used to declare two parameters: one long parameter, and one java.util.Map parameter. Then intercept method is used to generate a method body that returns one zero value.

The plugin program then modifies the process10 method by using multiple visit methods. Three advices are used: LocalVariableAdvice. class , PriceQueryAdvice.class , DiscountQueryAdvice.class.

Please be noticed that the sequence of the advice code is important. The purpose of the process10 method is to perform price calculation, which is similar to process9 method:

total = price - discount

However, the process10 method is different from the process9 method because the PriceQuery.java and DiscountQuery.java are encapsulated in the PriceQueryAdvice.java and DiscountQueryAdvice. java respectively. While process9 method encapsulates the PriceQuery. java and DiscountQuery.java in one method of the advice code.

Therefore, the @Local annotation is not applicable, and the PriceQueryAdvice.java and DiscountQueryAdvice.java wants to access to the same total variable to perform the price calculation. This example utilizes the parameter of the method of functional code to create a local variable that is visible to both PriceQueryAdvice.java and DiscountQueryAdvice.java . The example utilizes the second parameter of process10 method, which is in data type of java.util.Map . Because all the advice code instruments the same method: process10 method, so all the advice codes should be able to access the data that is stored in the second parameter of process10 method.

The instrumentation wants to prevent the program that invokes the process10 method to pass data into second parameter. Therefore the LocalVariableAdvice.java is used for this purpose.

100

![](Image00000.gif)

This is the code for LocalVariableAdvice.java :

public class LocalVariableAdvice {

@Advice.OnMethodEnter

public static void enter(

@Argument(value=1,readOnly=false)

Map<String,Object> data

) {

data=new HashMap<>();

}

@Advice.OnMethodExit

public static void end(

@Argument(value=1,readOnly=false)

Map<String,Object> data,

@Return(readOnly=false) int total

) {

total = (Integer)data.get(“total”);

}

//other code is omitted

}

The LocalVariableAdvice.java implements both on method enter and exit advice, their name are “ enter ” and “ end ” respectively. Observed that the LocalVariableAdvice.class is used in the first visit method. So the ByteBuddy will generate a nested structure for the instrumented code in this sequence:

(1) LocalVariableAdvice enter

(2) PriceQueryAdvice

(3) DiscountQueryAdvice

(4) LocalVariableAdvice end

101

![](Image00000.gif)

To prevent second parameter contains malicious data passed from outside of the process10 method, the enter method resets the second parameter every time the process10 method is invoked:

data=new HashMap<>();

The enter method instantiate a new HashMap. The new HashMap is passed to the second parameter, which is represented by data variable. The data variable is the parameter of enter method with @Argument annotation, and it is mapped to second parameter of process10 method because its value attribute is 1 , and the readOnly attribute is false .

Then the PriceQueryAdvice.java and DiscountQueryAdvice.java utilizes the HashMap to store the result of the calculation. The result of calculation is stored into HashMap with the key “ total ”.

Therefore, the total element of the HashMap contains the result of the price calculation. To ensure the instrumented code get the correct total value, the end method of LocalVariableAdvice.java , which implements the on method exit advice, is responsible to retrieve the value of total element from HashMap, and then passes it to the returnTotal parameter:

@Advice.OnMethodExit

public static void end(

@Argument(value=1,readOnly=false) Map data,

@Return(readOnly=false) int returnTotal)

{

returnTotal = (Integer)data.get(“total”);

}

The returnTotal is the parameter with @Return annotation, which represents the return data of the process10 method. So, the process10 method should be able to receive the result of the price calculation and uses it in the return statement.

The benefit of using LocalVariableAdvice.java is that the advice can constantly ensure the HashMap is reset to new HashMap before the price calculation starts. The exit advice then consistently returns the correct total to the instrumented code. At the time of this writing, which uses ByteBuddy 1.10.16, if the HashMap is replaced with the

102

![](Image00000.gif)

object reference (java.lang.String, java.lang.Integer) or primitive (int, long), the price calculation will fail because ByteBuddy will generate different object or primitive variable to store the price calculation. Even though the HashMap is used, the ByteBuddy will also generate different copy of HashMap to store the data. However, the HashMap stores the data consistently because the HashMap uses the same key to store the data . In future, when the generated bytecode does not have copy of the variable, then the HashMap parameter should be changed to object reference or primitive for efficient usage of resource.

This is the source code view of the instrumented code for process10 method:

public int process10(long paramLong, Map p){

p = new HashMap();

DataProducer var1 = this;

long var2 = paramLong;

Map varMap = p;

int var3 = new PriceQuery().query(var2);

varMap.put(“total”, Integer.valueOf(var3));

var3 = ((Integer)varMap.get(“total”))

.intValue();

var3 -= new DiscountQuery().query(var2);

varMap.put(“total”, Integer.valueOf(var3));

int var4 = 0;

var4 = ((Integer)p.get(“total”)).intValue();

return var4;

}

103

![](Image00000.gif)

In the generated bytecode, ByteBuddy creates a copy of HashMap ( varMap ) instead of using the Map in the second parameter directly. However, the method does perform the calculation correctly, and the data is stored in the consistent manner throughout the method. The generated bytecode also does not use the data in the second parameter that is possibly set by other program that invokes the method. Therefore, the developed advice code has met its objective, and the price calculation is correct.

Use array instead of HashMap

The HashMap in process10 method can be replaced with an int array . The use of int array can be more efficient in term of data retrieval and storage because array can use array index to store and retrieve data. The use of array index can also ensure the data consistency. HashMap has its own benefit because it can store different type of data and the storage size is flexible.

Generate method with chain of MethodCall

The plugin program is going to generate process11 method. Similar to process10 , this method will calculate the total price (total=price- discount). The differences are:

process11 uses multiple MethodCall and stores the total price into int array.

process11 uses utility class to invoke the query method of PriceQuery.java and DiscountQuery.java . All the method of utility class are static methods.

net.bytebuddy.implementation.MethodCall is the ByteBuddy component that can produce the bytecode to invoke either Java constructor or method. This is the code that generates the process11 method:

builder=builder.defineMethod(

“process11”, int[].class, Visibility.PUBLIC)

.withParameters(long.class, int[].class)

104

![](Image00000.gif)

.intercept(

MethodCall.invoke(LocalVariableAdvice.class

.getDeclaredMethod(“execute”,int[].class))

.withArgument(1)

.andThen(

MethodCall.invoke(

PriceUtil.class.getDeclaredMethod(

“execute”,long.class, int[].class))

.withArgument(0,1)

)

.andThen(

MethodCall.invoke(DiscountUtil.class

.getDeclaredMethod(“execute”,

long.class, int[].class))

.withArgument(0,1)

)

.andThen(FixedValue.argument(1)));

The process11 method is a public method that returns the int array. This method has two parameters: Java primitive long, and int array.

builder.defineMethod(

“process11”, int[].class, Visibility.PUBLIC)

.withParameters(long.class, int[].class)

The long parameter contains the value of id that will be used by the query method of PriceQuery.java and DiscountQuery.java . The int array is similar to the HashMap used in the process10 method: they are used to store the result of total price. The process11 method will use int array for the same purpose.

The intercept method is used to generate the method body. The intercept method uses MethodCall , and this MethodCall is chained to multiple MethodCall via the andThen method. This is the first MethodCall of the chained method:

MethodCall.invoke(LocalVariableAdvice.class

.getDeclaredMethod(“execute”,int[].class))

.withArgument(1)

105

![](Image00000.gif)

The withArgument(1) method passes the second parameter of process11 method to the execute method of LocalVariableAdvice.java . The execute method of LocalVariableAdvice.java resets the int array and its first element to zero. The execute method is a static method:

public static void execute(int[] total) {

total=new int[1];

}

Then the MethodCall is chainged to second MethodCall via andThen method:

.andThen(

MethodCall.invoke(PriceUtil.class

.getDeclaredMethod(“execute”,long.class,

int[].class))

.withArgument(0,1))

The second MethodCall invokes the execute method of PriceUtil.java . The second MethodCall invokes withArgument(0,1) , which passes the first and second parameter of process11 method to the execute method of PriceUtil.java . This is the implementation of execute method of PriceUtil.java:

public static void execute(long id, int[] total) {

total[0]+=new PriceQuery().query(id);

}

The execute method uses the id to perform the price query, adds the price and stores the result into the first element of the total array.

After that, the third MethodCall is chained via another andThen method:

.andThen(

MethodCall.invoke(DiscountUtil.class

.getDeclaredMethod(“execute”,long.class,

int[].class))

.withArgument(0,1)

106

![](Image00000.gif)

)

The third MethodCall invokes the execute method of DiscountUtil. java . The third MethodCall invokes withArgument(0,1) , which passes the first and second parameter of process11 method to the execute method of DiscountUtil.java. This is the implementation of the execute method in DiscountUtil.java :

public static void execute(long id, int[] total) {

total[0]-=new DiscountQuery().query(id);

}

The execute method uses the id to perform the discount query, then minus the total price stored in first element of the total array, and stores the latest result into the first element of the total array.

After that, the calculation is completed, and the first element of total array contains the latest total price. The last andThen method is invoked and chained to FixedValue.argument(1) . The FixedValue. argument(1) generates code that returns the second parameter of the processs11 method. Since all the MethodCall uses the second parameter to stores the total price and it is an int array, so the int array should contain the latest total price. Therefore, the process11 method can use the second parameter to create the return statement.

This is the source code view of the instrumented code for process11 method:

public int[] process11(long p1, int[] p2){

LocalVariableAdvice.execute(p2);

PriceUtil.execute(p1, p2);

DiscountUtil.execute(p1, p2);

return p2;

}

The generated code is compact, no unexpected variable created by the ByteBuddy because the int array is managed by the static method of the utility class. Therefore the process11 method can perform the calculation correctly.

ByteBuddy has some limitation in code generation. Some of the code

107

![](Image00000.gif)

cannot be generated directly. For example, the code for the price calculation can be implemented using this code:

public int calculatePrice(long id){

int total=new PriceQuery().query(id);

total-=new DiscountQuery().query(id);

return total;

}

There is no direct API, for example, MethodCall, to generate these lines of code:

new PriceQuery().query(id);

Access the total local variable and uses it in DiscountQuery.

Access the total local variable and uses it in return statement.

The net.bytebuddy.implementation.bytecode.StacManipulation can be the solution for this problem, but it is out of scope of this book. The use of StackManipulation requires knowledge of Java bytecode programming, and it can potentially implement more verbose code to achieve the same result code. The process9 method has the closest code that is similar to the code mentioned above. The process9 method uses @Local annotation in on method enter and exit advice to implement the instrumentation.

The price calculation can use instance variable to store the result of calculation, compared to the use of local variable. When the program wants to use instance variable to store the calculation result, then the implementation should use the advice code with @FieldValue annotation. The advice code can uses either on method enter advice, on method exist advice, or both of them.

At this stage, the chapter has completely explains about the InterceptorPlugin.java .

108

![](Image00000.gif)

InterfacePlugin

The InterfacePlugin.java is a plugin program that instruments all the Java interface found in the com.millionstrengthknowledge. interceptorprj.program package. This matching logic is specified in the matches method of InterfacePlugin.java :

public boolean matches(TypeDescription target){

if(target.getName().startsWith(

“com.millionstrengthknowledge.interceptorprj

.program”)&&target.isInterface())

return true;

else

return false;

}

The matching logic uses one new method: isInterface , to check whether the target is a Java interface. The Producer.java is the only one Java interface in this chapter. Therefore, the Producer.java will continue the instrumentation process to apply method.

The apply method declares three methods for the matched Java interface:

builder

.defineMethod(“getUniqueId”, String.class,

Visibility.PUBLIC)

.intercept(FixedValue.value(

UUID.randomUUID().toString()))

.defineMethod(“createData”, String.class,

Opcodes.ACC_PUBLIC|Opcodes.ACC_STATIC)

.intercept(StubMethod.INSTANCE)

.defineMethod(“verify”, void.class,

Visibility.PUBLIC)

.withoutCode();

The getUniqueId is a default method. To declare default method, simply creates the method body for the method, and ByteBuddy will generate the method intelligently. This is the generated getUniqueId

109

![](Image00000.gif)

method:

public default String getUniqueId(){

return “d33c6ab0-f12a-4d3e-8fdd-1de7aac47b90”;

}

The ByteBuddy automatically create the default method when ByteBuddy detects that the method body has the implementation code, the method is not static, and it is declared in the Java interface. The code uses FixedValue.value(UUID.fromUUID().toString()) to creates a random ID. The FixedValue.value method is another convenience method that can be used for generating constant value during build time or runtime.

The Java interface can have static method. this is the generated createData static method:

public static String createData(){

return null;

}

To create an abstract method in Java interface, use withoutCode method. This is the generated verify method:

public void verify();

Configuring two plugin programs in maven pom.xml

This chapter uses two plugin programs: InterceptorPlugin.java , InterfacePlugin.java . The section explains about how to add two plugin programs in pom.xml:

<plugin>

<groupId>net.bytebuddy</groupId>

<artifactId>byte-buddy-maven-plugin

</artifactId>

<version>${bytebuddy.version}</version>

<executions>

110

![](Image00000.gif)

<execution>

<goals>

<goal>transform</goal>

</goals>

</execution>

</executions>

<configuration>

<transformations>

<transformation>

<plugin>com.millionstrengthknowledge. interceptorprj.plugin.InterceptorPlugin</plugin>

</transformation>

<transformation>

<plugin>com.millionstrengthknowledge. interceptorprj.plugin.InterfacePlugin</plugin>

</transformation>

</transformations>

</configuration>

</plugin>

The pom.xml adds the second transformation tag for the second plugin program. The maven build process uses two loops: the first loop iterates the Java class files. The Java class file is the Java class that is compiled during maven build process.

The second loops iterates the plugin programs, invokes the matches method, and invokes apply method when matches methods return trues. The pseudo code explains the process:

for each Java class file {

for each plugin program {

invoke matches method

if matches method return ture, then invokes

apply method

}

}

111

![](Image00000.gif)

Conclusion

This chapter explains:

How to generate Java method

How to generate setter and getter method

How to generate method body using FixedValue

How to generate method body using StubMethod

How to generate method body using MethodDelegation

How to generate method body using Advice

How to generate method body using MethodCall

How to enable two plugin programs for the maven build process

112

![](Image00000.gif)

Chapter 12: Generate Constructor

This chapter explains on how to generate constructor dynamically. The source code for this chapter is included in ChapterDefineConstructor Eclipse project.

There are two functional codes for this chapter, super class Producer. java , and its derived class DataProducer.java:

Producer.java:

public class Producer {

private long producerId;

private String record;

public Producer() { }

public Producer(long pid, String d) {

producerId=pid;

record=d;

}

public long getProducerId() {

return producerId;

}

public void setProducerId(

long producerId) {

this.producerId = producerId;

}

public String getRecord() {

return record;

}

113

![](Image00000.gif)

public void setRecord(String data) {

this.record = data;

}

}

DataProducer.java:

public class DataProducer extends Producer{

private int dataProducerId;

private String data;

private BigInteger int01;

public int getDataProducerId() {

return dataProducerId;

}

public void setDataProducerId(

int dataProducerId) {

this.dataProducerId = dataProducerId;

}

public String getData() {

return data;

}

public void setData(String data) {

this.data = data;

}

}

Observed that DataProducer.java does not have the constructor. The instrumentation process will add seven constructors to the DataProducer.class .

114

![](Image00000.gif)

Cloning the constructor with define method

This is the first constructor that is created by the plugin program:

public DataProducer(int p1, String p2,

String p3){ }

This is the code that creates the constructor, which is implemented in apply method of InterceptorPlugin.java :

Constructor c1=ConstructorPrototype.class

.getDeclaredConstructor(int.class,

String.class, String.class);

builder.define(c1)

.intercept(MethodCall.invoke(

Producer.class.getConstructor()));

ConstructorPrototype.java:

public class ConstructorPrototype {

private int data1;

private String data2;

private String data3;

public ConstructorPrototype(int a, String b,

String c) {

data1=a;

data2=b;

data3=c;

}

}

The define method clones the constructor of ConstructorPrototype .java that contains three parameters: int.class, String.class, String.class. In order for define method to clones the constructor, the program must pass an instance of java.lang.reflect.Constructor to the parameter of define method. However, define method never clones the method

115

![](Image00000.gif)

body, and the annotation that are declared on prototype constructor.

Similar to Java method, the newly declared constructor requires the constructor body. The intercept method uses MethodCall to generate the constructor body.

.intercept(MethodCall.invoke(

Producer.class.getConstructor()));

In this constructor, the MethodCall is used to invoke super class default constructor: Producer() , which produces this bytecode:

public DataProducer(int p1,String p2,String p3){

super();

}

Generate constructor with defineConstructor method

Next, the plugin program creates this constructor:

private DataProducer(long p1){ }

This is the code used to generate the constructor:

builder.defineConstructor(Visibility.PRIVATE)

.withParameter(long.class)

.intercept(MethodCall

.invoke(Producer.class.getConstructor()))

The code uses defineConstructor method. The defineConstructor method takes one Visibility parameter that specifies the modifier for the constructor. In this example, the parameter specifies private visibility. Then, the method chains to withParameter method, which declares the java long primitive parameter. After that, the intercept method creates the constructor body by using the MethodCall .

Next, the plugin program creates this constructor:

116

![](Image00000.gif)

public DataProducer(in p1, int p2){ }

This is the code used to generate the constructor:

builder.

.defineConstructor(Opcodes.ACC_PUBLIC)

.withParameters(int.class, int.class)

.intercept(

MethodCall.invoke(

Producer.class.getConstructor()));

The code uses defineConstructor to declare the public constructor. Opscode is the alternative to Visibility for specifying the modifier. Then, the method chains to withParameters method that takes two parameter: int.class, int.class. Different from withParameter method, withParameters method can create multiple parameters. Then the intercept method creates the constructor body.

The apply method further creates the next constructor:

public DataProducer(int p1, int p2, String p3,

String p4){

super(p1, p3);

dataProducerId=p2;

data=p4;

}

This is the code that implements the constructor:

builder

.defineConstructor(Visibility.PUBLIC)

.withParameters(int.class, int.class,

String.class, String.class)

.intercept(

MethodCall.invoke(

Producer.class.getDeclaredConstructor(

long.class, String.class))

.withArgument(0, 2)

117

![](Image00000.gif)

.andThen( FieldAccessor.ofField(

“dataProducerId”).setsArgumentAt(1)))

.andThen( FieldAccessor.ofField(

“data”).setsArgumentAt(3)));

The declaration of the constructor and its parameter use the similar method that is already explained in previous constructor. However, the constructor body is different from the previous constructor. the constructor invokes super constructor with two parameters:

super(p1, p3);

The bytecode for this line of code is created via this advice code:

MethodCall.invoke(

Producer.class.getDeclaredConstructor(

long.class, String.class))

.withArgument(0, 2)

The MethodCall invokes another super constructor that takes two parameters: long.class and String.class. Then withArgument method is used to pass the p1 and p3 parameter to superclass constructor. The p1 and p3 parameter are used because the withArgument method specifies parameter index of 0 and 2. That means the first and third parameter of the constructor of DataProducer.class are passed to its super constructor.

After that, the constructor body assigns the p1 and p4 to dataProducerId and data instance variable:

dataProducerId=p2;

data=p4;

In order to generate bytecode for these lines of code, the advice code chains the method to andThen method

andThen(FieldAccessor.ofField(“dataProducerId”)

.setsArgumentAt(1))

The net.bytebuddy.implementation.FieldAccessor is used to access

118

![](Image00000.gif)

the instance variable programmatically. The usage of FieldAccessor here is to set the p2 parameter to dataProducerId instance variable. The ofField method configures the dataProducerId instance variable, and the setsArgumentAt method configures the p2 parameter. The value of 1 in setsArgumentAt method specifies the parameter index of the constructor. Therefore, the p2 parameter is selected. Similarly, to generate bytecode for this line code:

data=p4;

FieldAccessor is used to achieve the purpose:

andThen(FieldAccessor.ofField(“data”)

.setsArgumentAt(3))

Next, the plugin program creates this constructor:

public DataProducer(long p1, String p2)

throws ClassNotFoundException, SQLException{

super(p1,p2);

}

This is the code that generates the constructor:

builder.

.defineConstructor(Visibility.PUBLIC)

.withParameters(long.class, String.class)

.throwing(ClassNotFoundException.class,

SQLException.class)

.intercept(

MethodCall.invoke(

Producer.class.getDeclaredConstructor(

long.class, String.class))

.withAllArguments())

Similar to last constructor, the constructor body invokes the super constructor that takes two parameters. However, the advice code uses withAllArguments instead of withArgument method. The withAllArguments passed all the parameters value from the

119

![](Image00000.gif)

constructor to super constructor.

This constructor declares the throws clause . The throws clause throws ClassNotFoundException and SQLException . These exceptions are declared via throwing method.

Next, the plugin program instruments the default constructor. This is the default constructor after the instrumentation process:

public DataProducer(){

this.dataProducerId=120;

this.record=”<noData>”;

}

This is the code that instruments the default constructor, observed that the code does not declare the default constructor using defineConstructor method, instead, the code uses constructor method tomatch the default constructor in DataProducer.class :

builder.constructor(

ElementMatchers.isDefaultConstructor())

.intercept(

MethodCall.invoke(

Producer.class.getDeclaredConstructor()

)

.andThen(FieldAccessor

.ofField(“dataProducerId”)

.setsValue(120))

.andThen(FieldAccessor

.ofField(“data”)

.setsValue(“<noData>”)))

);

The code invokes constructor method and applies ElementMatchers. isDefaultConstructor method to match the default constructor. After the default constructor is selected, the builder invokes intercept method to generate code that invokes the super constructor using MethodCall . Then, the code uses FieldAccessor to set the value of instance variable of dataProducerId to 120 , and data instance variable

120

![](Image00000.gif)

to a string value of “ <noData> ”. The setsValue method is the right method to use compared to value method introduced in Chapter 10: Declare Instance Variable Dynamically . When programming for Java bytecode, the program must use constructor to set the initial value of the instance variable.

Why DataProducer.java contains the default constructor even though the plugin program does not declare it? ByteBuddy will create the default constructor implicitly when one of these methods is invoked: define, defineConstructor . The define method can be used to declare instance variable and Java method also. If define method is used to declare constructor, then ByteBuddy will create the default constructor automatically. Therefore, the default constructor is already created when the DataProducer(int,String,String) constructor is created.

Generate constructor with visit method

Finally, the plugin program declares this constructor:

public DataProducer(

int p1, String p2, String p3, String p4){

super(p1, p3);

if(p1 % 2==0)

dataProducerId=p1+10000;

else

dataProducerId=p2+20000;

data=p2;

int01=new BigInteger(data);

}

This is the code that generates the constructor:

builder=builder

.defineConstructor(Visibility.PUBLIC)

.withParameters(int.class, String.class,

String.class, String.class)

121

![](Image00000.gif)

.intercept(

MethodCall.invoke(

Producer.class

.getDeclaredConstructor(long.class,

String.class))

.withArgument(0, 2));

builder

.visit(Advice.to(ValueSetter.class)

.on(

ElementMatchers.isConstructor()

.and(ElementMatchers.takesArgument(

0,int.class))

.and(ElementMatchers.takesArgument(

1,String.class))

.and(ElementMatchers.takesArgument(

2,String.class))

.and(ElementMatchers.takesArgument(

3,String.class))));

The intercept method only generates the bytecode that invokes the super constructor:

super(p1, p3);

The remaining code is generated by the visit method. In visit method, to match the constructor, ElementMatchers.isConstructor and ElementMatchers.takesArgument(0, int.class) method are used.

The isConstructor method limits the matching scope to only constructor only.

The takesArgument method accepts two parameters: int, and java. lang.Class. The int parameter specifies the index of the parameter. The second parameter specifies its data type. This method matches only one parameter. So, to match the constructor that has four parameters, takesArgument is executed for four times. With this configuration, the constructor public DataProducer(int, String, String, String) should be selected to apply the advice code.

122

![](Image00000.gif)

ValueSetter.java:

public class ValueSetter {

@OnMethodExit

public static void set(

int param0, String param1,

@FieldValue(value=”dataProducerId”,

readOnly=false) int var1,

@FieldValue(value=”data”,

readOnly=false) String var2,

@FieldValue(value=”int01”,

readOnly=false) BigInteger biginteger

) {

if(param0%2==0)

var1=param0+10000;

else

var1=param0+20000;

var2=param1;

biginteger = new BigInteger(var2);

}

}

After that, the constructor body will contain the advice code provided in the ValueSetter.java .

Observed that the advice code instantiates an instance variable named “ int01 ”, which is an instance of BigInteger. Whenever the constructor wants to instantiate object using new operator, for example, new BigInteger(java.lang.String), the advice code should be implemented for the purpose. The intercept method supposes can generate this code via the use of MethodCall :

.intercept(

MethodCall.construct(BigInteger.class.

getDeclaredConstructor(String.class))

.withArgument(2)

.setsField(

Field.class.getDeclaredField(“int01”)));

123

![](Image00000.gif)

However, at the time of this writing, the use of MethodCall causes a java.lang.IllegalStateException during the instrumentation process. Therefore, uses the advice code when the constructor requires to instantiate new object.

Conclusion

This chapter explains:

How to declare constructor dynamically

How to declare constructor body using MethodCall

How to pass parameter to super constructor

How to use setsValue method of FieldAccessor.ofField to set the initial value of the instance variable

124

![](Image00000.gif)

Chapter 13: Generate Generic Constructor, Method, and Instance Variable

This chapter explains on how to generate generic constructor, method, and instance variable dynamically. The source code for this chapter is included in ChapterGeneric Eeclipse project. DataProducer.java is the functional code in this chapter:

public class DataProducer { }

DataProducer.java , in this chapter, does not have any method and instance variable. After the instrumentation process, this is the Java source code view of the DataProducer.class :

public class DataProducer<A, B>{

private A test1;

private List<?> test2;

private List<? super A> test3;

private List<? extends B> test4;

private List<? extends List<A>> test5;

private List<String> test6;

private List<List<String>> test7;

private List<? extends String> test8;

private List<? extends List<String>> test9;

public DataProducer() {}

public <R> DataProducer(A paramA, B paramB,

R paramR){ }

public List<String> testMtd1(List<String> p){

return null;

}

125

![](Image00000.gif)

public List<? extends String> testMtd2(

List<? extends String> paramList){

return null;

}

public <R> String testMtd3(R paramR){

return null;

}

public <R extends Long> String testMtd4(

R paramR, List<R> paramList){

return null;

}

public <R extends List<String>> String

testMtd5(R paramR){

return null;

}

public A testMtd6(A paramA, B paramB,

BiFunction<? super A, ? extends A,

? extends B> paramBiFunction){

return null;

}

public <P, Q> A testMtd7(P paramP, Q paramQ){

return null;

}

public <P extends Long, extends Serializable>

String testMtd8(P paramP){

return null;

}

}

126

![](Image00000.gif)

InterceptorPlugin.java is the plugin program that generates the generic code. The net.bytebuddy.description.type.TypeDescription. Generic is the fundamental Java class for declaring generic method and instance variable in ByteBuddy. Generic programming in Java requires the program to create parameterized type, type argument, and type variable.

Generic Class

The DataProducer.class does not have any type variable. This code adds A and B type variable to DataProducer.class :

builder.typeVariable(“A”)

.typeVariable(“B”);

The typeVariable method is responsible to define the type variable. To create A type variable, pass “A” character to the parameter of typeVariable method. Same method used for “B” type variable. With the code above, the DataProducer.class changes to this declaration:

public class DataProducer<A, B>{ }

Generic Instance Variable

The test1 instance variable uses type variable A :

private A test1;

This is the code that generates the declaration:

builder.defineField(“test1”, A_type,

Visibility.PRIVATE);

The code uses defineField method, which is the usual method used for generating instance variable. However, observed that the data type specifies A_type . This is the new concept for declaring the data type of instance variable. The A_type is an instance of net.bytebuddy. description.type.TypeDescription.Generic class:

127

![](Image00000.gif)

Generic A_type =

TypeDescription.Generic.Builder

.typeVariable(“A”).build();

In order to create the Generic instance, uses the generic builder of net.bytebuddy.description.type.TypeDescription . The builder can be accessed via TypeDescription.Generic.Builder . Then, chains the builder to typeVariable method, and then invokes the build method. After that, A_type instance is created and it represents the “A” type variable. The defineField method uses A_type to define the data type for test1 instance variable.

In order to declare parameterized type, use the net.bytebuddy. description.type.TypeDescription.Generic.Builder also. However, instead of using typeVariable method, the parameterizedType method is used. For example, test2 is an instance variable of List<?>:

private List<?> test2;

This is the code that generates the declaration:

builder.defineField(“test2”, lt_w,

Visibility.PRIVATE);

The lt_w is an instance of net.bytebuddy.description.type. TypeDescription.Generic class:

Generic wildCard =

TypeDescription.Generic.Builder

.unboundWildcard();

Generic lt_w =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType.of(

List.class), wildCard).build();

128

![](Image00000.gif)

The List<?> is a parameterized type, and its type argument is an unbound wild card, <?>. Therefore, the declaration requires to create a wild card instance. For this purpose, TypeDescription.Generic. Builder.unboundWildcard method is used, and the wild card instance is stored in the wildCard variable.

The wildCard variable is then used in the parameterizedType method. To define the parameterized type: List<?> , passes the TypeDescription.ForLoadedType.of(List.class) and wildCard variable to the first and second parameter of parameterizedType method. Then, invokes build method at the last of method chain. This should generate the bytecode of the declaration of test2 instance variable.

Next, the plugin program declares test3 instance variable:

private List<? super A> test3;

This is the code that generates the declaration:

builder.defineField(

“test3”, lt_w_lbA, Visibility.PRIVATE)

This is the declaration of lt_w_lbA :

Generic A_lb =

TypeDescription.Generic.Builder

.typeVariable(“A”)

.asWildcardLowerBound();

Generic lt_w_lbA =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType.of(

List.class), A_lb

).build();

The List<? super A> uses type argument of lower bound wildcard of A type variable. In order to create the parameterized type, two

129

![](Image00000.gif)

variables are required: lt_w_lbA , and A_lb .

The asWildCardLowerBound method is used to declare the wild card lower bound type variable. Therefore, A_lb variable stores the value of “ ? super A ”.

To declare the parameterized type List<? super A>, passes the TypeDescription.ForLoadedType.of(List.class) and A_lb variable to the parameter of parameterizedType method, and then invokes build method. The code should create lt_w_lbA variable that stores the declaration of “ List<? super A> ”, and defineField method can use the variable to define the data type for test3 instance variable.

TypeDescription.ForLoadedType.of(List.class) is responsible to create the variable of TypeDescription of java.lang.List. TypeDescription represents the Java class loaded in the JVM. In this example, that Java class is the java.lang.List. The TypeDescription.ForLoadedType.of method is the common method used in the ByteBuddy programming.

Next, the plugin program declares test4 instance variable:

private List<? extends B> test4;

The test4 instance variable is a parameterized type, and its type argument is an upper bound wildcard of B type variable. In order to create this instance variable, first creates the variable, B_ub , which represents ? extends B :

Generic B_ub =

TypeDescription.Generic.Builder

.typeVariable(“B”).asWildcardUpperBound();

The asWildCardUpperBound method is used to create the instance of upper bound wildcard. Then, creates the lt_w_ubB variable that represents the parameterized type List<? extends B> :

130

![](Image00000.gif)

Generic lt_w_ubB =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType.of(

List.class), B_ub

).build();

After that, uses the lt_w_ubB variable to define test4 instance variable:

builder.defineField(“test4”, lt_w_ubB,

Visibility.PRIVATE);

Next, the plugin program declares test5 instance variable:

private List<? extends List<A>> test5;

The test5 instance variable is a parameterized type, and its type argument is an upper bound wildcard of List<A> parameterized type. This is different type of generic, in which the parameterized type contains another parameterized type. In order to create the instance variable, first creates the A_List_ub variable, which represents the ? extends List<A> :

Generic A_List_ub =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType

.of(List.class), A_type)

.asWildcardUpperBound();

131

![](Image00000.gif)

Then, create the parameterized type List<? extends List<A>> and stores it into lt_lt_ubA variable:

Generic lt_lt_ubA =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType.of(List.class),

A_List_ub).build();

After that, uses the lt_lt_ubA variable to define the test5 instance variable:

builder.defineField(“test5”, lt_lt_ubA,

Visibility.PRIVATE);

So far the chapter explains the declaration of instance variable of parameterized type that uses type variable. In generic programming, the parameterized type can use reference type also. The test6 instance variable is the example that uses reference type of java.lang.String:

private List<String> test6;

In order to create the parameterized type List<String> , the code requires to create the parameterized type only, no type variable is required:

Generic lt_string =

TypeDescription.Generic.Builder

.parameterizedType(List.class, String.class)

.build();

132

![](Image00000.gif)

Then, the lt_string variable can be used to define the test6 variable:

builder.defineField(“test6”, lt_string,

Visibility.PRIVATE);

Next, the plugin program declares test7 instance variable:

private List<List<String>> test7;

The test7 instance variable is a parameterized type, and its type argument uses the List<String> parameterized type. Since the List<String> is already created in lt_string variable, so this declaration is going to reuse the lt_string variable. Then, creates the parameterized type that represents List<List<String>> :

Generic lt_lt_String =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType.of(List.class),

lt_string).build();

After that, uses the lt_lt_string variable to define the test7 instance variable:

builder.defineField(“test7”, lt_lt_string,

Visibility.PRIVATE);

The remaining instance variables, test8 and test9 , uses similar declaration pattern for test4 and test5 instance variable.

private List<? extends B> test4;

private List<? extends List<A>> test5;

private List<? extends String> test8;

private List<? extends List<String>> test9;

However, test8 and test9 uses reference type for its type argument, and test4 and test5 uses type variable for its type argument.

133

![](Image00000.gif)

Generic Method and Constructor

This section explains on how to declare generic method and constructor. testMtd1 is the first generic method declared in this chapter:

public List<String> testMtd1(List<String> p){

return null;

}

The testMtd1 method contains one List<String> parameter and return type of List<String> . Because the List<String> parameterized type is already created in lt_string variable, the code will reuse the lt_string variable to define the method. This is the code that defines the testMtd1 method:

builder.defineMethod(“testMtd1”, lt_string,

Visibility.PUBLIC)

.withParameter(lt_string)

.intercept(FixedValue.nullValue());

Observed that the declaration uses the defineMethod method to declare the method. The second parameter of defineMethod method and the parameter of withParameter method, both are passed with the lt_string variable in order to create the generic parameter and return type.

Next, the plugin program declares the testMtd2 method:

public List<? extends String> testMtd2(

List<? extends String> paramList){

return null;

}

The testMtd2 method uses List<? extends String> for its method parameter and return type. The declaration reuses the lt_w_ubString variable to define the method. The lt_w_ubString variable is the variable that is used for declaration of test8 variable:

134

![](Image00000.gif)

builder.defineMethod(

“testMtd2”, lt_w_ubString, Visibility.PUBLIC

).withParameter(lt_w_ubString)

.intercept(FixedValue.nullValue())

Next, the plugin program declares the testMtd3 method:

public <R> String testMtd3(R paramR){

return null;

}

The testMtd3 method contains R type argument that is scoped to the testMtd3 method only. The name for this type argument is method type argument . The method parameter is typed to R. In order to define this method, first creates an instance of Generic class. In this example, R_type is the instance of Generic class for this purpose:

Generic R_type =

TypeDescription.Generic.Builder

.typeVariable(“R”).build();

Then, define the testMtd3 method:

builder.defineMethod(

“testMtd3”, String.class, Visibility.PUBLIC)

.withParameter(R_type)

.typeVariable(“R”)

.intercept(FixedValue.nullValue())

The definition passes the R_type for the parameter of withParameter method. Then, uses the typeVariable method to declare the R, the method type argument. This code should generate the testMtd3 method accordingly.

Next, the plugin program declares the testMtd4 method:

public <R extends Long> String testMtd4(

R paramR, List<R> paramList){

return null; }

135

![](Image00000.gif)

The testMtd4 method contains R type variable with upper bounded to java.lang.Long. The method has two parameters with these data type: R and List<R> . The method requires the R type variable, and this variable is already created in R_type variable. So the code reuses the R_type variable. The method requires another parameterized type, which is List<R>. In order to create this parameterized type, the code creates the R_list variable:

Generic R_list = TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType.of(

List.class), R_type).build();

At this stage, the plugin program has R_type and R_list variables, which can be used in defineMethod method to declare the parameter of testMtd4 method. To complete the testMtd4 declaration, the method requires the <R extends Long> method type argument. However, the argument does not require explicit variable creation, instead, uses the typeVariable method to declare the method type argument. Therefore, this line of code should define the testMtd4 method:

builder.defineMethod(

“testMtd4”, String.class, Visibility.PUBLIC)

.withParameters(R_type, R_list)

.typeVariable(“R”, Long.class)

.intercept(FixedValue.nullValue())

The typeVariable method is used declare the type argument of the method. Observed that the typeVariable method is passed with the “ R ” and Long.class for its parameter value. With these two parameters, the code should create the <R extends Long> type argument for the method.

Next, the plugin program declares the testMtd5 method:

public <R extends List<String>> String

testMtd5(R paramR){

return null; }

136

![](Image00000.gif)

The testMtd5 method contains R type variable with upper bounded to List<String> . The code reuses the lt_string variable. So this is the code for the defineMethod method:

builder.defineMethod(

“testMtd5”, String.class, Visibility.PUBLIC)

.withParameter(R_type)

.typeVariable(“R”, lt_string)

.intercept(FixedValue.nullValue())

The withParameter method is used to declare the only one parameter, by passing the R_type variable. Then, uses typeVariable method to declare the type argument of the method, by passing the R and lt_string for its parameter value. With these two parameters, the code should create the <R extends List<String> type argument of the method. Therefore, the code should create the testMtd5 method accordingly.

Next, the plugin program declares the testMtd6 method:

public A testMtd6(A paramA, B paramB,

BiFunction<? super A, ? extends A, ? extends B> paramBiFunction){

return null;

}

The testMtd6 is the most complex generic method created in this chapter. The method contains three parameters. The first and second parameter are typed to A and B respectively. The third parameter is a java.util.function.BiFunction that can accept three type arguments. Since the program has already defined the A_type and B_type for A and B type variables, so this explanation is going to focus on the declaration of BiFunction . This is the code that declares the BiFunction :

137

![](Image00000.gif)

Generic gen_BiFn =

TypeDescription.Generic.Builder

.parameterizedType(

TypeDescription.ForLoadedType

.of(BiFunction.class),

A_lb, A_ub, B_ub).build();

The gen_BiFn is the variable that represents the BiFunction parameterized type. Observed that the code uses the parameterizedType method of TypeDescription.Generic.Builder . The BiFunction requires three type arguments. Therefore, the parameterizedType method above takes three arguments: A_lb , A_ ub , and B_ub , with each represents “ ? super A ”, “ ? extends A” , and “ ? extends B ”. This is the code that generates the testMtd6 method:

builder.defineMethod(

“testMtd6”, A_type, Visibility.PUBLIC)

.withParameters(A_type, B_type, gen_BiFn)

.intercept(FixedValue.nullValue())

Next, the plugin program creates the testMtd7 method:

public <P, Q> A testMtd7(P paramP, Q paramQ){

return null;

}

The testMtd7 method is different from all the previous methods declared because the method has two method type arguments, P and Q . However, the code used to declare this method is simple though. To declare two method type arguments, invokes the typeVariable method twice, for P and Q respectively:

builder.defineMethod(

“testMtd7”, A_type, Visibility.PUBLIC)

.withParameters(p_type, q_type)

.typeVariable(“P”)

.typeVariable(“Q”)

.intercept(FixedValue.nullValue());

138

![](Image00000.gif)

Therefore, the code should create the testMtd7 method accordingly.

Next, the plugin program creates testMtd8 method:

public <P extends Long & Serializable> String testMtd8(P param){

return null;

}

This is the code that generates the testMtd8 method:

builder.defineMethod(

“testMtd8”, String.class, Visibility.PUBLIC)

.withParameters(p_type)

.typeVariable(“P”, Long.class,

Serializable.class)

.intercept(FixedValue.nullValue());

The method type argument of testMtd8 is a multiple bound generic type . This is the equivalent Java source code for the code above:

public <P extends Long & Serializable> String testMtd8(P param){

return null;

}

To declare multiple bound generic type argument, the typeVariable method is used. Because the multiple bound type argument contains java.lang.Long and java.io.Serializable , so the typeVariable method specifies Long.class and Serializable.class in the second parameter since the second parameter is a variable length argument. Please be noticed that when this code is compiled into Java class, this will be the bytecode for testMtd8 method:

public <P extends Long, extends Serializable>

String testMtd8(P paramP){

return null;

}

139

![](Image00000.gif)

Finally, the plugin program creates a constructor for DataProducer<A,B>. java , which takes three parameters:

public <R> DataProducer(A paramA, B paramB,

R paramR){ }

The code pattern used to create the generic constructor is very similar to the generic method. So this chapter will create only one constructor for the example. The constructor has one type argument R. The R type argument is used in the third parameter of the constructor. The first and second parameter uses A and B , the type argument of the DataProducer.java . So this code should generates the constructor:

builder.defineConstructor(Visibility.PUBLIC)

.withParameters(A_type, B_type, R_type)

.typeVariable(“R”)

.intercept(MethodCall.invoke(

Object.class.getDeclaredConstructor()));

Developing interceptor with generic type

Java applies type erasure for generic type. When developing the interceptor, the advice code is required to manage the object differently because the type erasure will change the data type that is implemented before compilation. For example, the DataProcessor.java has type argument of P , and Q extends Number

public class DataProcessor<P,Q extends Number> {

public void process(P p, Q q) {

System.out.println(“Paramerer1: “+p);

System.out.println(“Paramerer2: “+q);

}

}

140

![](Image00000.gif)

If the advice code wants to intercept the parameter of process method, the advice code needs to use java.lang.Object and java.lang.Number to map the first and second parameter. The DataProcessorInterceptor. java is the advice code developed for DataProcessor.class :

public class DataProcessorInterceptor {

@Advice.OnMethodEnter

public static void start(

@Argument(

value=0,readOnly=false,

typing=Assigner.Typing.DYNAMIC

) Object param1,

@Argument(

value=1,readOnly=false,

typing=Assigner.Typing.DYNAMIC

) Number param2) {

if(param1 instanceof String) {

param1 = param1+”randomdata”;

}

if(param2 instanceof Integer){

param2=((Integer)param2)+1;

}

}

}

The advice code implements the on method enter advice. The param1 parameter is mapped to the first parameter of process method. The first parameter of the process method is typed to P . When mapping this type of parameter in advice code, the java.lang.Object is used because the type parameter is changed to java.lang.Object after compilation.

The param2 parameter is mapped to the second parameter of the process method. The second parameter of the process method is typed to Q , which has upper bound of java.lang.Number. So the java. lang.Number can be used to map to the second parameter.

When the advice code processes the parameter, the advice code needs to check the data type of the parameter. In this example, the advice code uses instanceof to check the data type of param1 . If the param1

141

![](Image00000.gif)

is a java.lang.String, then appends a “ ramdomdata ” to the param1 . If the param2 is a java.lang.Integer , then adds one to the integer.

Therefore, the advice code must aware of the type erasure when programming for the generic type.

Conclusion

This chapter explains on how to generate the generic instance variable, generic method and generic constructor.

142

![](Image00000.gif)

Chapter 14: Add and Remove Java Annotation

This chapter explains on how to add and remove Java annotation that is annotated on constructor, Java method, and instance variable, dynamically. The source code for this chapter is included in ChapterAnnotation Eclipse project.

This chapter is considered complex. This overview can help to increase the understanding of the explanation for this chapter:

Use net.bytebuddy.dynamic.DynamicType.Builder to add annotation to the Java class

Use net.bytebuddy.asm.MemberAttributeExtension. ForMethod to add annotation to Java method and constructor

Use net.bytebuddy.asm.MemberAttributeExtension.ForField to add annotation to instance variable

Use net.bytebuddy.asm.jar.ClassVisitor to remove annotation from the Java class

Use net.bytebuddy.asm.AsmVisitorWrapper. ForDeclaredMethods.MethodVisitorWrapper to remove annotation from Java method and constructor

Use net.bytebuddy.asm.AsmVisitorWrapper. ForDeclaredFields.FieldVisitorWrapper to remove annotation from instance variable

143

![](Image00000.gif)

The structure:

DynamicType (public class)

|-Builder (public static inner interface)

MemberAttributeExtension (public class)

|-ForMethod (public static inner class)

|

|-ForField (public static inner class)

ClassVisitor (public class)

AsmVisitorWrapper (public class)

|-ForDeclaredMethods (public static inner class)

| |-MethodVisitorWrapper (public static inner

| interface)

|

|-ForDeclaredFields (public static inner class)

| |-FieldVisitorWrapper (public static inner

interface)

DataProducer.java is the functional code of this chapter:

@Deprecated

public class DataProducer {

private int recordId=-3;

@Deprecated

public DataProducer(int p1, int p2,

@Other int p3) { }

@Deprecated

private String data;

@Deprecated

public void createData() { }

public void create() { }

144

![](Image00000.gif)

public void createRecord() {}

public void createFile(

int param0, String param1,

@Other long param2, @Other double param3

) {

}

}

The DataProducer.java uses one JDK annotation: @Deprecated , and two customized annotation: @MyAnnotation , @Other . After the instrumentation process, this is the Java source code view of the DataProducer.class :

/**

* @deprecated

*/

@MyAnnotation

public class DataProducer

implements Producer, Serializable{

/**

* @deprecated

*/

@MyAnnotation

private String data;

/**

* @deprecated

*/

@MyAnnotation

public DataProducer(@MyAnnotation int p1,

int p2, int p3){

}

/**@deprecated*/

public void createData() {}

145

![](Image00000.gif)

@Deprecated(since=””, forRemoval=false)

public void create() {}

@RecordAnnotation({@com. millionstrengthknowledge.interceptorprj. annotation.ColumnAnnotation(name=”username”, value=”user01”),

@com.millionstrengthknowledge.interceptorprj. annotation.ColumnAnnotation(name=”age”,

value=”25”)})

public void createRecord() {}

@Deprecated(since=”jdk5”, forRemoval=false)

@MyAnnotation

public void createFile(@MyAnnotation int p0,

@Deprecated(since=”jdk5”, forRemoval=false)

@MyAnnotation String param1, long param2,

@Other double param3) {}

}

Besides the annotation, the instrumentation process also adds two new Java marker interfaces to the DataProducer.class . All the code generation in this chapter are implemented in InterceptorPlugin. java , and ClassAnnotationRemoval.java .

Add Java interface to Java class

Firstly, the chapter explains on how to add Java interface to the Java class. Before instrumentation, the DataProducer.java has no Java interface. The plugin program will add java.io.Serializable and com.millionstrengthknowledge.interceptorprj.program. Producer Java interface to the DataProducer.class . In order to add the Java interface to Java class, uses the implement method of the net. bytebuddy.dynamic.DynamicType.Builder :

builder.implement(Producer.class,

Serializable.class);

146

![](Image00000.gif)

The implement method accepts variable length argument of java.lang. Class, in which the type of class is the Java interface. Any java.lang. Class of Java interface passed to the parameter of implement method will cause the ByteBuddy to add the Java interface to the target class.

Therefore, ByteBuddy generates this code for the DataProducer.class :

/**

* @deprecated

*/

@MyAnnotation

public class DataProducer implements Producer, Serializable{ }

Add annotation to the Java class

After instrumentation process, DataProducer.class is added with the implements clause. Observed that the class level annotation of DataProducer.class changes also. The @Deprecated annotation is marked in comment block, and new annotation @MyAnnotation is added to the DataProducer.class . The changes occur because the plugin program invokes these lines of code:

builder.annotateType(myAnnotation)

.visit(new ClassAnnotationRemoval(

Deprecated.class));

The annotateType method is the method that adds annotation to the Java class. Its method parameter accepts an instance of net. bytebuddy.description.annotation.AnnotationDescription . To add the annotation to the Java class, passes the instance of AnnotationDescription of the desired Java annotation to this parameter. Because the program wants to add @MyAnnotation , so the method is passed with the myAnnotation variable. This is the code that declares the myAnnotation variable:

AnnotationDescription myAnnotation =

AnnotationDescription.Builder

.ofType(MyAnnotation.class).build();

147

![](Image00000.gif)

The net.bytebuddy.description.annotation. AnnotationDescription is the fundamental Java class used in annotation programming in ByteBuddy. The AnnotationDescription is used to create the variable that represents the Java annotation. In this example, this Java annotation is the @MyAnnotation . So the declaration passes the MyAnnotation.class to AnnotationDescription.Builder. ofType method, and invokes the build method. After that, the myAnnotation variable is created and can be used in the annotateType method. The annotateType method adds the @MyAnnotation to the DataProducer.class at class level.

Remove annotation from the Java class

Then, the plugin program removes the @Deprecated annotation from the DataProducer.class . To remove the class level annotation, develops a derived class that extends net.bytebuddy.asm. AsmVisitorWrapper.AbstractBase . In this example, this derived class is the ClassAnnotationRemoval.java , and it is used to remove the @Deprecated annotation:

The derived class is required to implement the superclass wrap method. The wrap method has eight parameters.

![](Image00046.jpg)

148

![](Image00000.gif)

public ClassVisitor wrap(

TypeDescription instrumentedType,

ClassVisitor classVisitor,

Implementation.Context context,

TypePool typePool,

FieldList<FieldDescription.InDefinedShape> fs,

MethodList<?> methods,

int writerFlags,

int readerFlags

)

The implementation is going to use the only one parameter from that eight parameters: ClassVisitor , the second parameter of the wrap method. The ByteBuddy will provide the instance of ClassVisitor for this parameter during build time, this instance contains the necessary service for plugin program to generate the bytecode. However, the instance cannot remove the annotation. Therefore, the ClassAnnotationRemoval.java uses this instance to instantiate another instance of ClassVisitor, and implements the visitAnnotation method so that it can remove the annotation. This is the implementation of the wrap method:

return new ClassVisitor(

Opcodes.ASM7, classVisitor) {

public AnnotationVisitor visitAnnotation(

java.lang.String desc, boolean visible

) {

if (Type.getDescriptor(

targetAnnotationClass).equals(desc)) {

return null;

}

return super.visitAnnotation(desc, visible);

}

};

The implementation instantiates a new instance of ClassVisitor, which is an anonymous class. The constructor takes two parameters:

149

![](Image00000.gif)

Opcodes.ASM7 , and classVisitor (the second parameter from wrap method). The Opcodes.ASM7 configures the ClassVisitor to generate Java bytecode based on Java11. Because the implementation wants to enhance the classVisitor so that it can be used to remove the annotation, the classVisitor is passed to the second parameter of the constructor of ClassVisitor.

The anonymous class implements the visitAnnotation method. The visitAnnotation method is used to access and process the annotation of the Java class. The visitAnnotation method will be invoked implicitly during the instrumentation process. When the method is invoked, it accesses the annotation of the Java class one by one. If the Java class has one annotation, then this method will be invoked once. If the Java class has two annotations, then this method will be invoked twice, and so on. The first parameter of visitAnnotation method, desc , is an instance of java.lang.String, which contains the value of annotation descriptor. For example, “ Ljava/lang/Deprecated ” is the annotation descriptor for @Deprecated annotation. Therefore, the desc parameter is used to match the target annotation that is for the removal:

if(Type.getDescriptor(targetAnnotationClass)

.equals(desc)) {

return null;

}

The targetAnnotationClass instance variable contains an instance of java.lang.Class that represents the @Deprecated . The Type. getDescriptor method converts targetAnnotationClass instance variable from java.lang.Class into annotation descriptor, so that it can be used to compare with the desc variable. So, when the annotation matches, return a null value. The null value will cause the instrumentation process to mark the @Deprecated annotation in comment block. This should remove the @Deprecated annotation from DataProducer.class . To end the visitAnnotation method, invokes the superclass’s visitAnnotation method:

return super.visitAnnotation(desc, visible);

150

![](Image00000.gif)

The targetAnnotationClass is the instance variable declared in the ClassAnnotationRemoval.java . It is instantiated in the constructor:

private Class targetAnnotationClass;

public ClassAnnotationRemoval(Class c){

targetAnnotationClass = c;

}

The plugin program instantiates the instance of ClassAnnotationRemoval.java in the parameter of visit method. The plugin program passes the instance of java.lang.Class of Deprecated to the first parameter of the constructor of ClassAnnotationRemoval. class :

builder.annotateType(myAnnotation)

.visit(new ClassAnnotationRemoval(

Deprecated.class));

Therefore, the code above should add the @MyAnnotation to the DataProducer.class , and remove the @Deprecated from the DataProducer.class .

Add annotation to Java method

Next, the plugin program adds the @Deprecated annotation to the create method of DataProducer.class . This is the code that adds the @ Deprecated annotation:

builder

.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(defDeprecated)

.on(ElementMatchers.named(“create”))

);

The code uses visit method to perform the instrumentation. The instrumentation requires an instance of net.bytebuddy.asm.

151

![](Image00000.gif)

MemberAttributeExtension.ForMethod . The plugin program will use these two methods of ForMethod for annotation programming:

annotateMethod : add annotation at method level

annotateParameter : add annotation at method parameter level

The annotateMethod method is used to add the @Deprecated annotation. The annotateMethod method uses the defDeprecated variable for its parameter. This is the code that declares the defDeprecated variable:

AnnotationDescription defDeprecated =

AnnotationDescription.Builder.ofType(

Deprecated.class).build();

defDeprecated is the instance of AnnotationDescription that represents @Deprecated annotation. The ofType method of AnnotationDescription.Builder instantiates the builder with the java.lang.Class of Deprecated. Then, the build method completes the instantiation and stores the instance to the defDeprecated variable .

builder

.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(defDeprecated)

.on(ElementMatchers.named(“create”))

);

The plugin program just completes the annotateMethod method for the visit method above. The plugin program needs to specify the target functional method. The on method is invoked to match the target method for adding the annotation. In this example, the target method is the create method. Therefore, after this code is executed, the instrumentation process should add the @Deprecated annotation to the create method:

@Deprecated(since=””, forRemoval=false)

public void create() { }

152

![](Image00000.gif)

Observed that the attribute of @Deprecated : since , forRemoval , are included in the annotation, and they are provided with the default value. Even though the advice code does not include the attribute, the instrumentation process will add the attribute implicitly because this is the default behavior of the ByteBuddy.

Add nested annotation to Java method

Next, the plugin program adds the annotation container to the createRecord method. Annotation container is the annotation that contains nested annotation. For example,

@RecordAnnotation({

@ColumnAnnotation(name=”username”,

value=”user01”),

@ColumnAnnotation(name=”age”, value=”25”)})

public void createRecord() {}

@RecordAnnotation is the annotation container because it contains @ColumnAnnotation . Before the plugin program can add the @ RecordAnnotation to the createRecord method, the plugin program must declare the instance of AnnotationDescription that represents @RecordAnnotation , and its nested annotation @ColumnAnnotation . This is the code for ColumnAnnotation.java :

@Repeatable(RecordAnnotation.class)

@Retention(RetentionPolicy.RUNTIME)

@Target({

ElementType.METHOD, ElementType.FIELD})

public @interface ColumnAnnotation {

String name();

String value(); }

153

![](Image00000.gif)

This is the code that declares the instance of AnnotationDescription for @ColumnAnnotation with username attribute:

AnnotationDescription c1 =

AnnotationDescription.Builder.ofType(

ColumnAnnotation.class)

.define(“name”, “username”)

.define(“value”, “user01”).build();

When the program wants to define attribute value for the annotation, the define method is used. Here, the define method defines name attribute to have value of username ., and value attribute to have value of user01 . After that, invokes build method to create the instance of AnnotationDescription, and stores it into c1 variable. Similarly, this is the code that declares the @ColumnAnnotation with age value in name attribute, and the c2 is the variable that stores the instance of the AnnotationDescription:

AnnotationDescription c2 =

AnnotationDescription.Builder.ofType(

ColumnAnnotation.class)

.define(“name”, “age”)

.define(“value”, “25”).build();

After the instance of AnnotationDescription of nested annotation is created, creates the instance of AnnotationDescription for @ RecordAnnotation :

AnnotationDescription nestedAnnotation =

AnnotationDescription.Builder.ofType(

RecordAnnotation.class)

.defineAnnotationArray(

“value”,

new TypeDescription.ForLoadedType(

ColumnAnnotation.class), c1, c2

).build();

This is the code for RecordAnnotation.java :

154

![](Image00000.gif)

@Retention(RetentionPolicy.RUNTIME)

@Target({

ElementType.METHOD, ElementType.FIELD

})

public @interface RecordAnnotation {

ColumnAnnotation[] value();

}

The RecordAnnotation.java has one value attribute with data type of ColumnAnnotation array. To add multiple @ColumnAnnotation to the @RecordAnnotation , the defineAnnotationArray method is used.

The defineAnnotationArray method requires three parameters: String, TypeDescription, AnnotationDescription . The first parameter is used to specified the attribute name of @RecordAnnotation that contains the array of nested annotation. The @RecordAnnotation uses “ value ” attribute to contain the nested annotation (please refer to RecordAnnotation.java ), so the value of first parameter is “ value ”.

The second parameter is used to specify that the data type of the value attribute of the RecordAnnotation.java . The data type is ColumnAnnotation.java . So the program instantiates an instance of TypeDescription via TypeDescripton. ForLoadedType(ColumnAnnotation.class) in second parameter.

The third parameter is a variable length argument, and it is used to specify the content of value attribute for the RecordAnnotation.java . So pass the c1 and c2 variable to this parameter. After that, invokes build method to end the method chain. The build method creates the instance of AnnotationDescription that represents the RecordAnnotation , and this instance is stored in the nestedAnnotation variable.

After that, the nestedAnnotation variable is now ready to be used for adding the @RecordAnnotation on createRecord method. So the plugin program invokes the visit method:

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(nestedAnnotation)

.on(ElementMatchers.named(“createRecord”)))

155

![](Image00000.gif)

The instance of ForMethod is created, and the nestedAnnotation variable is passed to its annotateMethod method. The on method is invoked to match the createRecord method in DataProducer. class . Therefore, this code should add the @RecordAnnotaion to the createRecord method:

@RecordAnnotation({

@ColumnAnnotation(name=”username”,

value=”user01”),

@ColumnAnnotation(name=”age”, value=”25”)})

public void createRecord() {}

Remove annotation from Java method

Next, the plugin program removes the @Deprecated annotation from the createData method. For this purpose, the plugin program is required to implement a customized derived class of net. bytebuddy.asm.AsmVisitorWrapper.ForDeclaredMethods. MethodVisitorWrapper . The plugin program will create this derived class in anonymous class format, and it is created in methodDeprecatedRemover method of the plugin program:

private MethodVisitorWrapper

methodDeprecatedRemover() {

return new MethodVisitorWrapper() {

@Override

public MethodVisitor wrap(

TypeDescription type,

MethodDescription mtdDesc,

MethodVisitor methodVisitor,

Context ctx,

TypePool pool, int writeFlag, int readFlag

) {

return new MethodVisitor(

Opcodes.ASM7, methodVisitor) {

@Override

public AnnotationVisitor

visitAnnotation(String desc, boolean

visible) {

156

![](Image00000.gif)

if (Type.getDescriptor(

Deprecated.class).equals(desc)) {

return null;

}

return super.visitAnnotation(desc,

visible);

}

};

}};

}

The derived class of MethodVisitorWrapper requires to implement the wrap method. In this implementation, the wrap method returns an instance of net.bytebuddy.jar.asm.MethodVisitor. The implementation of wrap method creates the instance of MethodVisitor in anonymous class format, and this anonymous class implements the visitAnnotation method. Similar to ClassVisitor, the instrumentation process will invoke the visitAnnotation method when the process encounters an annotation in the method. The annotation descriptor of the currently inspecting annotation is available via the desc parameter. So the program uses desc parameter to match the target annotation that the program wants to remove:

if (Type.getDescriptor(Deprecated.class). equals(desc)) {

return null;

}

If the annotation descriptor of Deprecated.class is found, then return null. The null value causes the instrumentation process to mark the @Deprecated in comment block. To end the visitAnnotation method, invokes the superclass’s visitAnnotation method at the end of the method.

Now the implementation of methodDeprecatedRemover method is completed. The plugin program will use this method in the visit method:

157

![](Image00000.gif)

builder.visit(

new AsmVisitorWrapper.ForDeclaredMethods()

.method(

ElementMatchers.named(“createData”),

methodDeprecatedRemover()

)

);

The program instantiates an instance of ForDeclaredMethods . Then, invokes the method method of ForDeclaredMethods . The method method requires two parameters. The first parameter requires the ElementMatchers . In this example, the matcher attempts to match the createData method, so the ElementMatchers.named method is used. The second parameter takes an instance of MethodVisitorWrapper . The methodDeprecatedRemover method is invoked in this parameter. After this, the instance of ForDeclaredMethods has the necessary matcher and MethodVisitorWrapper instance, the instrumentation process should remove the @Deprecated annotation from the createData method. This is the createData method after instrumentation process:

/* @deprecated */

public void createData() {}

Add annotation to method parameter

Next, the plugin program adds some annotations to the createFile method of the DataProducer.class . This is the original createFile method before instrumentation process:

public void createFile(

int param0, String param1,

@Other long param2, @Other double param3) { }

After the instrumentation process, this is the instrumented createFile

158

![](Image00000.gif)

method:

@Deprecated(since=”jdk5”, forRemoval=false)

@MyAnnotation

public void createFile(

@MyAnnotation int param0,

@MyAnnotation @Deprecated(since=”jdk5”,

forRemoval=false) String param1,

long param2, @Other double param3

) { }

This example is complex:

The instrumentation process adds @Deprecated and @ MyAnnotation to the createFile method. The @Deprecated annotation has the since attribute with “jdk5” value.

The first parameter is added one @MyAnnotation.

The second parameter is added with @MyAnnotation and @ Deprecated annotation.

The @Other annotation is removed from the third parameter.

There is no change in the fourth parameter.

This is the code for this purpose:

1 builder.visit(new MemberAttributeExtension. ForMethod()

2 .annotateMethod(jdk5Deprecated)

3 .annotateMethod(myAnnotation)

4 .annotateParameter(0, myAnnotation)

5 .annotateParameter(1, jdk5Deprecated)

6 .annotateParameter(1, myAnnotation)

7 .on(ElementMatchers.named(“createFile”))

8 )

9 .visit(

10 new AsmVisitorWrapper.ForDeclaredMethods()

11 .method(ElementMatchers.named(“createFile”),

159

![](Image00000.gif)

12 parameterOtherRemover()

13 )

14 );

So, this example is going to explain about these new concepts:

How to add annotation to the method parameter

How to remove annotation from the method parameter

Observed that the code has two visit methods. The first visit method adds the related annotation to the method and parameter. The second visit method removes the annotation from the method parameter.

In first visit method, the MemberAttributeExtension is used to add the annotation. The line 2 and 3 invokes the annotateMethod method to add the annotation. There is a jdk5Deprecated variable, which is an instance of AnnotationDescription:

AnnotationDescription jdk5Deprecated =

AnnotationDescription.Builder.ofType(

Deprecated.class)

.define(“since”, “jdk5”)

.build();

The jdk5Deprecated variable represents the @Deprecated annotation with a “jdk5” value for its since attribute. So, the jdk5Deprecated variable is created and can be used in line 2.

The code continues, the line 4, 5, and 6 invokes the annotateParameter method to add the annotations to parameter. The annotateParameter method has two parameters: int and AnnotationDescription . The int parameter is used to specify the index number of the parameter.

.annotateParameter(0, myAnnotation)

This code add @MyAnnotation to the first parameter of createFile method.

.annotateParameter(1, jdk5Deprecated)

.annotateParameter(1, myAnnotation)

160

![](Image00000.gif)

These two lines of code add @Deprecated(since=”jdk5”, forRemoval=false) and @MyAnnotation to second parameter of createFile method.

Remove annotation from method parameter

After that, the plugin program removes the @Other parameter from the third parameter:

builder.visit(

new AsmVisitorWrapper.ForDeclaredMethods()

.method(

ElementMatchers.named(“createFile”),

parameterOtherRemover()

)

);

The visit method is used to perform the instrumentation process. The instrumentation process requires an instance of ForDeclaredMethods . The method method of ForDeclaredMethod requires one ElementMatcher , and an instance of MethodVisitorWrapper .

The parameterOtherRemover method is the method that can returned an instance of MethodVisitorWrapper. This is the implementation of parameterOtherRemover method:

private MethodVisitorWrapper

parameterOtherRemover() {

return new MethodVisitorWrapper() {

@Override

public MethodVisitor wrap(

TypeDescription td,

MethodDescription desc,

MethodVisitor methodVisitor, Context ctx,

TypePool pool, int writeFlag, int readFlag

) {

161

![](Image00000.gif)

return new MethodVisitor(Opcodes.ASM7,

methodVisitor) {

@Override

public AnnotationVisitor

visitParameterAnnotation(

int param, java.lang.String desc,

boolean visible

){

if(param==2&&Type.getDescriptor(

Other.class).equals(desc)) {

return null;

}

return super.visitParameterAnnotation(

param, desc, visible);

}

};

}

};

}

The wrap method is implemented. The wrap method returns an instance of MethodVisitor in inner anonymous class format, and it implements the visitParameterAnnotation method.

The visitParameterAnnotation method has three parameters: int, String, boolean . The int parameter is used to specify the index number of parameter. The String parameter is the annotation descriptor of the currently inspecting annotation. The boolean parameter is not used in this example. So, the instrumentation process wants to remove the @Other from the third parameter, this is the logic for this purpose:

162

![](Image00000.gif)

If(param==2&&Type.getDescriptor(Other.class). equals(desc)){

return null;

}

To match for the index number of third parameter, the param==2 is used. Then the Type.getDescriptor method converts Other.class into annotation descriptor and compares it with the desc variable. When the @Other annotation is detected, returns null value, and the null value will cause the instrumentation process to remove the annotation. To end the visitParameterAnnotation method, the return statement invokes the superclass’s visitParameterAnnotation method.

Now the parameterOtherRemover method is ready to be used. It is used in the second visit method, and it is invoked in the second parameter of method method:

9\. .visit(

10\. new AsmVisitorWrapper.ForDeclaredMethods()

11\. .method(

ElementMatchers.named(“createFile”),

12\. parameterOtherRemover()

13\. )

14\. );

With this code, the @Other annotation parameter is removed from the third parameter of the createFile method.

163

![](Image00000.gif)

Add annotation to the instance variable

At this stage, the chapter has explained about annotation processing on method and Java class. Next, the chapter will explain on how to add and remove annotation that is annotated on the instance variable. The plugin program will add @MyAnnotation to the data instance variable of DataProducer.class . This is the data instance variable before instrumentation process:

@Deprecated

private String data;

After the instrumentation process, the @Deprecated annotation is removed, and @MyAnnotation is added:

/**

*@Deprecated

*/

@MyAnnotation

private String data;

This is the code that adds and removes the annotation that is annotated on data instance variable:

1\. builder.visit(new MemberAttributeExtension

.ForField()

2\. .annotate(myAnnotation)

3\. .on(ElementMatchers.named(“data”))

4\. )

5\. .visit(new AsmVisitorWrapper

.ForDeclaredFields()

6\. .field(

7\. ElementMatchers.named(“data”),

8\. fieldDeprecatedRemover()

9\. )

10\. );

164

![](Image00000.gif)

The MemberAttributeExtension.ForField is used to add the annotation to the instance variable. The code from line 1 to 4 is the code segment for the purpose.

Invoke annotate method to add @MyAnnotation to the data instance variable, and uses on method to configure the ElementMatchers.

Remove annotation from the instance variable

Then the second visit method removes the @Deprecated annotation from the data instance variable. The program requires the instance of ForDeclaredFields and FieldVisitorWrapper for this purpose. This is the implementation of fieldDeprecatedRemover method that returns the instance of FieldVisitorWrapper :

private FieldVisitorWrapper

fieldDeprecatedRemover() {

return new FieldVisitorWrapper() {

@Override

public FieldVisitor wrap(

TypeDescription td, InDefinedShape sh,

FieldVisitor fieldVisitor

) {

return new FieldVisitor(Opcodes.ASM7,

fieldVisitor) {

@Override

public AnnotationVisitor

visitAnnotation(String desc,

boolean visible) {

if (Type.getDescriptor(

Deprecated.class).equals(desc)) {

return null;

}

return super.visitAnnotation(desc,

visible);

}};

165

![](Image00000.gif)

}};

}

Very similar to MethodVisitor , the visitAnnotation method of FieldVisitor is implemented to match the @Deprecated annotation, and return null value to signify to instrumentation process to remove the @Deprecated annotation. After the fieldDeprecatedRemover method is implemented, invokes the fieldDeprecatedRemover method in the code from line 5 to 9. Thereafter, the @Deprecated annotation of data instance variable should be removed.

Add annotation on the constructor

After all, the chapter will show one last example that adds and removes annotation that is annotated on the constructor. Annotation processing on constructor works very similar to the annotation processing on Java method. The chapter will use only one constructor to show how the annotation instrumentation works. This is the constructor before instrumentation process:

@Deprecated

public DataProducer(int p1, int p2,

@Other int p3) {

}

This is the constructor after instrumentation process:

/**

* @Deprecated

*/

@MyAnnotation

public DataProducer(@MyAnnotation int p1,

int p2, int p3) {

}

166

![](Image00000.gif)

After instrumentation process, the @Deprecated annotation is removed from the constructor. The first parameter is added one @ MyAnnotation annotation, and the @Other annotation is removed from third parameter. Most of the code that add and remove annotation is similar to the one that is used for Java method. This is the code that provides the annotation instrumentation:

builder.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(myAnnotation)

.annotateParameter(0, myAnnotation)

.on(ElementMatchers.isConstructor())

)

.visit(

new AsmVisitorWrapper.ForDeclaredMethods()

.constructor(ElementMatchers.isConstructor(),

methodDeprecatedRemover())

)

.visit(

new AsmVisitorWrapper.ForDeclaredMethods()

.constructor(ElementMatchers.isConstructor(),

parameterOtherRemover())

);

There are three visit method to achieve the instrumentation. The first visit method adds the @MyAnnotation to the constructor and its first parameter. The first visit method uses MemberAttributeExtension and its inner class ForMethod to add the annotation. Although the Java element is a constructor, however, the ForMethod can be applied to constructor also. So, this line adds @MyAnnotation to the constructor:

.annotateMethod(myAnnotation)

This line adds @MyAnnotation to the first parameter of constructor:

.annotateParameter(0, myAnnotation)

There is different matching criteria used in the ElementMatchers . The ElementMatchers uses isConstructor method, this causes the advice

167

![](Image00000.gif)

code applies to all the constructors in the DataProducer.class .

Remove annotation from the constructor

The second visit method removes the @Deprecated annotation from the constructor. The second visit method uses AsmVisitorWrapper and its inner class ForDeclaredMethod . Then, invokes the constructor method by passing the ElementMatchers.isConstructor to its first parameter, and an instance of MethodVisitorWrapper to its second parameter. The methodDeprecatedRemover method is the method that creates the instance of MethodVisitorWrapper . The methodDeprecatedRemover is reusable for the constructor.

The third visit method removes the @Other annotation from the third parameter. The third visit method uses AsmVisitorWrapper and its inner class ForDeclaredMethod . The parameterOtherRemover is reusable for the constructor parameter also.

Conclusion

This chapter explains:

How to add annotation to Java class

How to add implement clause to Java class

How to add annotation to method, instance variable and constructor using MemberAttributeExtension

How to remove annotation using the AsmVisitorWrapper, custom ClassVisitor, MethodVisitor, and FieldVisitor

168

![](Image00000.gif)

Chapter 15: Remove Constructor, Method, and Instance Variable

This chapter explains on how to use net.bytebuddy.asm. MemberRemoval to remove constructor, method and instance variable from the functional code. The source code for this chapter is included in ChapterRemoval Eclipse project.

This is the implementation of the functional code for this chapter, DataProducer.java :

public class DataProducer {

private int data;

private long data2;

public DataProducer() { }

public DataProducer(int d) {

data=d;

}

public DataProducer(long d) {

data2=d;

}

public String getUuid() {

return UUID.randomUUID().toString();

}

@Deprecated

public void test(int value, String data) {

System.out.println(“Integer: “+value);

System.out.println(“String: “+data);

}

169

![](Image00000.gif)

public void create() {

System.out.println(“create data”);

}

}

After the instrumentation process, this will be the source code view of the DataProducer.class :

public class DataProducer {

private int data;

public DataProducer(int d) {

data=d;

}

public String getUuid() {

return UUID.randomUUID().toString();

}

}

After the instrumentation process completed, the data instance variable, getUuid method, and constructor with single int parameter remains in the DataProducer.class , and all other constructors, methods, and instance variable are removed.

This is the implementation of apply method of plugin program, InterceptorPlugin.java , which removes the Java elements from the functional code:

builder

.visit(

new MemberRemoval().stripConstructors(

ElementMatchers.isDefaultConstructor()))

.visit(

new MemberRemoval().stripConstructors(

ElementMatchers.takesArgument(0,long.class)

)

)

170

![](Image00000.gif)

.visit(

new MemberRemoval().stripMethods(

ElementMatchers.named(“test”)))

.visit(

new MemberRemoval().stripFields(

ElementMatchers.named(“data2”)

)

);

Remove Constructor

The stripConstructors method is the method that removes the constructor. This line of code removes the default constructor:

builder

.visit(

new MemberRemoval().stripConstructors(

ElementMatchers.isDefaultConstructor()));

To remove the default constructor, creates an instance of MemberRemoval , and then invokes its stripConstuctors method. Then, specifies the matching logic using ElementMatchers. isDefaultConstructor method. The isDefaultConstructor method matches the default constructor in the target class. With this configuration, ByteBuddy removes the default constructor from DataProducer.class .

Next, the apply method removes another constructor that has one parameter with long data type:

builder.visit(

new MemberRemoval().stripConstructors(

ElementMatchers.takesArgument(0,long.class)));

To match the constructor, ElementMatchers.takesArgument(0, long.class) is used. The takesArgument method accepts two parameters: int, and Java.lang.Class. The int parameter specifies the index of the parameter. The second parameter specifies the Class type for the parameter according to index that is specified in first parameter. So ElementMatchers.takesArgument(0,long.class) matches with the

171

![](Image00000.gif)

constructor public DataProducer(long d) because the parameter at index 0 is the long.class. Therefore, the constructor is removed from DataProducer.class .

Remove method

After that, the apply method removes the test method from DataProducer.class . This line of code removes the test method:

builder.visit(

new MemberRemoval().stripMethods(

ElementMatchers.named(“test”)))

The stripMethods method is the method that removes the Java method. The ElementMatchers matches the test method based on the method name. Therefore, after instrumentation process, the test method is removed from DataProducer.class .

Remove instance variable

Finally, the apply method removes the data2 instance variable from DataProducer.class . This line of code removes the instance variable:

builder.visit(new MemberRemoval().stripFields(

ElementMatchers.named(“data2”)));

The stripFields method is the method that removes the Java instance variable. The ElementMatchers matches the data2 instance variable based on the variable name. Therefore, after the instrumentation process, the data2 instance variable is removed from the DataProducer. class .

Conclusion

This chapter explains on how to remove constructor, method and instance variable from the Java class.

172

![](Image00000.gif)

Chapter 16: Search and Replace

This chapter explains on how to use ByteBuddy to perform search and replace the code in the functional code. The source code for this chapter is included in ChapterSubstitute Eclipse project.

The net.bytebuddy.asm.MemberSubstitution is the Java class that can perform the search and replace functionality. The DataProducer. java is the functional code:

public class DataProducer {

public int data1, data2;

public DataProducer() { }

public DataProducer(int d) {

data2=d;

}

public String create(int value, String d) {

data2=0;

String newData=d.substring(2);

System.out.println(newData);

return d.toLowerCase();

}

}

After the instrumentation process, the DataProducer(int) constructor and create method are changed:

public DataProducer(int d) {

this.data1 = d;

}

173

![](Image00000.gif)

public String create(int value, String d) {

this.data1 = 0;

String newData = d.repeat(2);

return d.toUpperCase();

}

Search and replace method in Java method

The chapter will explain about the create method first. Observed that the create method has some changes of the code in the method body. The data2 instance variable has been changed to data1 instance variable. The substring method is changed to repeat method. The toLowerCase method is changed to toUpperCase method.

This is the code that searches the toLowerCase method and replaces it with the toUpperCase method:

builder.visit(

MemberSubstitution.strict()

.method(ElementMatchers.named(

“toLowerCase”))

.replaceWithMethod(

ElementMatchers.named(“toUpperCase”).and

(ElementMatchers.takesNoArguments()

)

);

The visit method is used. The visit method create an instance of MemberSubstitute by invoking the static method MemberSubstitute. strict() . The strict() means the instance will throw exception if the search logic is not resolved during the instrumentation process. The instance is then chained to method method. The method specifies ElementMatchers.named(“toLowerCase”) , which means search the method with the name of “toLowerCase” in the create method. If found, then replace it with the toUpperCase function. The changes to “toUpperCase” is specified via replaceWithMethod method:

.replaceWithMethod(

174

![](Image00000.gif)

ElementMatchers.named(“toUpperCase”).and(

ElementMatchers.takesNoArguments()))

The replaceWithMethod method requires another set of ElementMatchers. This matching logic is used for finding the replacement function. The name should be the function name from the java.lang.String because the target function toLowerCase is the function of the java.lang.String, so the replacement function should be the function from the java.lang.String also. In this example, the “toUpperCase” is the replacement function. However, there are two versions of toUpperCase function in java.lang.String:

toUpperCase()

toUpperCase(Locale locale)

Therefore, the matching logic specifies that the function should have the name “toUpperCase” and the function does not have any argument. So, the first version of toUpperCase is selected to replace the toLowerCase function.

The code then searches the substring function and replace it with repeat function

.method(ElementMatchers.named(“substring”))

.replaceWithMethod(

ElementMatchers.named(“repeat”))

Since there is only one version of repeat function in java.lang.String. So the replacement matching logic is much simpler. The matching logic uses ElementMatchers.named method to find the substring function in the create method, and then replaces it with repeat function.

Search and replace instance variable in Java method

Next, the plugin program searches and replaces the instance variable used in the create method. The data2 instance variable is replaced with the data1 instance variable, and this is the code for this purpose:

175

![](Image00000.gif)

.field(ElementMatchers.named(“data2”))

.replaceWithField(

ElementMatchers.named(“data1”))

To search and replace the instance variable, the field method is used to specify the target instance variable. Then uses replaceWithField method to specify the replacement instance variable. Therefore, the program should replace the instance variable from data2 to data1 .

So far the code only specifies the search matching logic using method , and field method, and replacement matching logic using replaceWithMethod and replaceWithField method. How to specify that the search and replace is performed on the create method? The on method is the method for this purpose:

.on(ElementMatchers.named(“create”)

With the on method, the search and replace is scoped to the create method only. Therefore, in the search and replace instrumentation, one visit method is corresponding to one functional method.

When programming for search and replace in ByteBuddy, there are three type of matching logic per visit method:

After that, there is another visit method, which is used to perform search and replace in DataProducer(int) constructor. The code searches the data2 instance variable and replaces it with the data1 instance variable:

builder.visit(MemberSubstitution.strict()

.field(ElementMatchers.named(“data2”))

.replaceWithField(

ElementMatchers.named(“data1”)

)

.on(ElementMatchers.isConstructor()

.and(ElementMatchers.takesArgument(

0, int.class)))

);

176

![](Image00000.gif)

The search and replace instrumentation on constructor is similar with the instrumentation on method. However, there are two constructor in the DataProducer.class . Therefore the functional code matching logic specifies to match the constructor only and that constructor has one int parameter. The DataProducer(int) constructor is selected for the instrumentation.

Conclusion

This chapter explains on how to use MemberSubstitution to search and replace the Java code.

![](Image00048.jpg)

177

![](Image00000.gif)

Chapter 17: ElementMatchers

This chapter provides examples on how to use net.bytebuddy. matcher.ElementMatchers to construct the matching logic. In previous chapters, this book has demonstrated some example usage of ElementMatchers:

named

takesArgument

takesNoArgument

isConstructor

isDefaultConstructor

This chapter will provide more example usage of ElementMatchers . This chapter will use three plugin programs: InterceptorUtilPlugin.java , InterceptorRepositoryPlugin.java , and InterceptorQueryPlugin. java . The plugin programs are going to instrument the Java classes from these packages:

com.millionstrengthknowledge.interceptorprj.repository

AuthenticationQuery.class

DataQuery.class

GeneralRepository.class

UserQuery.class

UserRepository.class

com.millionstrengthknowledge.interceptorprj.util

DataProducerUtil.class

178

![](Image00000.gif)

The source code for this chapter is included in ChapterElementMatcher Eclipse project. There are five Java classes in repository package one Java class in util package. To demonstrate the usage of ElementMatchers, the plugin program will add one @ElementMatched annotation to the Java element when the ElementMatchers matching criteria returns true. The Java elements can be either the Java class, constructor, method, or instance variable.

InterceptorUtilPlugin

So far all of the chapters only uses the getName method of the net.bytebuddy.description.type.TypeDescription . The TypeDescription is the fundamental Java class used in ByteBuddy programming. The TypeDescripton provides a set of API that allows developer to inspect the Java class. It is similar to Java Reflection API, but provides more functionality. In InterceptorUtilPlugin.java , the matches method uses the isGenerified method of TypeDescription , this the code of the implementation:

if(target.getName().startsWith(

“com.millionstrengthknowledge

.interceptorprj.util”)&&

target.isGenerified()) {

System.out.println(

“InterceptorUtilPlugin found target: “+

target.getName());

return true;

}

else

return false;

The target variable is a parameter from the matches method, and it is an instance of TypeDescription . The matching logic returns true when the the Java class represented in target variable is packaged in “ com.millionstrengthknowledge.interceptorprj.util ” package, and the target is a generic class. The isGenerified method return

179

![](Image00000.gif)

true when the target Java class uses type argument at class level. The DataProducerUtil.java is the generic Java class the uses one type argument “A” at class level:

public class DataProducerUtil<A> {

//code is omitted

}

Therefore, the DataProducerUtil.java matches the condition provided in the matching logic, and it is going to continue to apply method of InterceptorUtilPlugin.java for further instrumentation process.

ElementMatchers.isSetter

There are eight visit methods in apply method. This is the implementation of the first visit method:

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(

ElementMatcherUtil.create(

“isSetter(uniqueId)”))

.on(ElementMatchers.isSetter(“uniqueId”)));

The visit method uses MemberAttributeExtension.ForMethod to instrument the Java class. The instrumentation add the @ ElementMatched(“isSetter(uniqueId)”) to the setter method that uses uniqueId instance variable. After instrumentation process, the setUniqueId method of DataProducerUtil.class is added the annotation:

@ElementMatched(“isSetter(uniqueId)”)

public void setUniqueId(long id){ uniqueId=id; }

The main focus here is how the program applies the ElementMatchers to match the target Java element to add the annotation. In this example, ElementMatchers.isSetter method is used. The isSetter method is the matcher that matches the setter method with the name of instance

180

![](Image00000.gif)

variable specified in the parameter. This example uses “ uniqueId ” for its parameter. Therefore, setUniqueId method is selected to add the annotation.

ElementMatcherUtil

ElementMatcherUtil.java is a utility Java class:

public class ElementMatcherUtil {

public static AnnotationDescription create(

String type

) {

AnnotationDescription a =

AnnotationDescription.Builder.ofType(

ElementMatched.class)

.define(“value”, type)

.build();

return a;

}

}

The ElementMatcherUtil.java has one method named create . The method accepts one java.lang.String parameter. The method creates an instance of AnnotationDescription that represents ElementMatched. class . ElementMatched.java is a customized Java annotation used in this chapter:

@Retention(RetentionPolicy.RUNTIME)

@Target({

ElementType.TYPE,

ElementType.CONSTRUCTOR,

ElementType.METHOD,

ElementType.FIELD

})

public @interface ElementMatched {

String value();

}

181

![](Image00000.gif)

The annotation has one value attribute. The data passed from the parameter of create method of ElementMatcherUtil.java will be stored into the value attribute. For example, when the program invokes ElementMatcherUtil.create(“isSetter(uniqueId)”) , this program will annotate an annotation @ ElementMatched(“isSetter(uniqueId)”) via the annotateMethod method of MemberAttributeExtension.ForMethod.java.

So that is how the ElementMatcherUtil.java adds the @ElementMatched annotation to the functional code. This utility Java class will be reused in all of the examples in this chapter.

ElementMatchers.isGetter

The second visit method adds the @ElementMatched annotation to the getter method for uniqueId instance variable:

builder.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(

ElementMatcherUtil.create(

“isGetter(uniqueId)”))

.on(ElementMatchers.isGetter(“uniqueId”)))

For this purpose, the ElementMatchers.isGetter method is used to match the getter method. After instrumentation process, the @ ElementMatched(“isGetter(uniqueId)”) is added to getUniqueId method of DataProducerUtil.class :

@ElementMatcher(“isGetter(uniqueId)”)

public long getUniqueId() { return uniqueId; }

182

![](Image00000.gif)

ElementMatchers.isAnnotatedWith

Next, the visit method uses ElementMatchers.isAnnotatedWith method:

builder.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(ElementMatcherUtil

.create(“isAnnotatedWith(Deprecated.class)”))

.on(ElementMatchers.isAnnotatedWith(

Deprecated.class)));

The isAnnotatedWith method returns true when the method is annotated with the annotation that is specified in the parameter. In this example, this annotation is the @Deprecated annotation. Therefore, the test method of DataProducerUtil.class is selected to add the annotation because the test method is annotated with @Deprecated :

@ElementMatched(

“isAnnotatedWith(Deprecated.class)”)

@Deprecated

public void test(){ }

ElementMatchers.isConstructor

Next, the visit method uses ElementMatchers.isConstructor method:

builder.visit(new MemberAttributeExtension. ForMethod()

.annotateMethod(ElementMatcherUtil

.create(“isConstructor”))

.on(ElementMatchers.isConstructor())

);

183

![](Image00000.gif)

The isConstructor method returns true when the constructor is detected in Java class. There are two constructors in DataProducerUtil. class Therefore, these two constructors are added the annotation:

@ElementMatched(“isConstructor”)

public DataProducerUtil(){ }

@ElementMatched(“isConstructor”)

public DataProducerUtil(long id){ }

The ElementMatchers has the ability to match all the Java elements that fulfills the matching criteria, for example, the isConstructor matches all the constructor in the Java class. Sometime the program wants to match only the specify Java element. If this is the case, then the program requires to provide more ElementMatchers to form the combination of matchers to find the specific match. This can be done with the and , or , not , and other method provided by the ElementMatchers.

There is some other technique that can help in programming the specific match. For example, ElementMatchers.isFinal method return true for all the Java element that are final, including method and instance/class variable. However, the MemberAttributeExtension. ForMethod is used to limit the matching to Java method only and MemberAttributeExtension.ForField is used to limit the matching to instance/class variable only. So, two visit methods are required to annotate the method and instance variable respectively in the next example:

builder.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(

ElementMatcherUtil.create(

“isFinal-method”))

.on(ElementMatchers.isFinal()))

.visit(

new MemberAttributeExtension.ForField()

.annotate(

ElementMatcherUtil.create(“isFinal-field”))

.on(ElementMatchers.isFinal()));

184

![](Image00000.gif)

With these two visit methods, this is the result of instrumentation process on DataProducerUtil.class :

@ElementMatched(“isFinal-field”)

private final String record=””;

@ElementMatched(“isFinal-method”)

private final void process(){ }

The record instance variable and process method are selected to add the @ElementMatched annotation because there are final Java elements. Another technique to limit the isFinal matcher to method and instance variable only when ForMethod and ForField are not used:

ElementMatchers.isFinal()

.and(ElementMatchers.isMethod());

ElementMatchers.isFinal()

.and(ElementMatchers.isField());

The and method and isMethod method are used to limit the matching scope to method only. Same concept applies to the instance variable.

ElementMatchers.returns, ElementMatchers.takesGenericArgument

The next example introduces two new matcher methods: ElementMatchers.returns and ElementMatchers. takesGenericArgument :

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(ElementMatcherUtil

.create(

“returns(long) and takesGenericArgument(A)”))

.on(

ElementMatchers.returns(long.class).and(

185

![](Image00000.gif)

ElementMatchers.takesGenericArgument(

1, TypeDescription.Generic.Builder

.typeVariable(“A”).build())

))

);

The matching criteria attempts to match the method that returns long value, and its second parameter is a generic type variable “A”. The returns method is used to match the method that return long value. The takesGenericArgument method is used to match the second parameter. The first parameter of takesGenericArgument method specifies the index number of the parameter. Because the matcher wants to match second parameter, so the value of “ 1 ” is used. Then, the program creates the type variable instance for “ A ”, and passes it in second parameter of takesGenericArgument method. Therefore, the program should annotate the execute method of DataProducerUtil. class because it matches the matching criteria:

@ElementMatched(

“returns(long) and takesGenericArgument(A)”)

public long execute(int p1, A p2) { return -1; }

ElementMatchers.canThrow, ElementMatchers.or

Next, the example uses ElementMatchers.returns ElementMatchers. canThrow , and ElementMatchers.or method to form the combination of matchers:

builder.visit(

new MemberAttributeExtension.ForMethod()

.annotateMethod(ElementMatcherUtil.create(

“returns(long) and (throw SQLException or

ClassNotFoundException”))

.on(

ElementMatchers.returns(long.class).and(

ElementMatchers.canThrow(

SQLException.class).or(

ElementMatchers.canThrow(

ClassNotFoundException.class))))

186

![](Image00000.gif)

);

The matching attempts to match the method that returns long value, and the method declares either SQLException or ClassNotFoundException in the throws clause. The example uses the similar returns method explained in previous example. Then, the matching criteria uses and method to chain to another matcher combination, which uses canThrow method. The canThrow method returns true when the throw clause matches with the exception specified in the parameter. The or method is used because the matching wants to match either SQLException or ClassNotFoundException. Therefore, the processRecord and processData method of DataProducerUtil.class are selected because they fulfill the matching criteria:

@ElementMatched(“returns(long) and (throw

SQLException or ClassNotFoundException”)

public long processData() throws SQLException{

return -1;

}

@ElementMatched(“returns(long) and (throw

SQLException or ClassNotFoundException”)

public long processRecord() throws SQLException, ScriptException{

return -1; }

InterceptorRepositoryPlugin

At this stage, the chapter has completed the explanation for the InterceptorUtilPlugin.java . There are two more plugin programs: InterceptorRepositoryPlugin.java and InterceptorQueryPlugin.java . This section provides the explanation for the InterceptorRepositoryPlugin.java . The matches method of InterceptorRepositoryPlugin.java uses another method of TypeDescription to implement the matching logic. The matching logic uses isAssignableTo method:

if(target.getName().startsWith(“com.

millionstrengthknowledge.interceptorprj

.repository”)&&

187

![](Image00000.gif)

target.isAssignableTo(Serializable.class)) {

System.out.println(

“InterceptorRepositoryPlugin found target: “+

target.getName());

return true;

}

else

return false;

The isAssignableTo method is a very useful method. It return true when the instance of TypeDescription represents a Java class that can be assigned to the instance of Java class that is specified in its parameter. For example:

Integer figure=Integer.valueOf(1000);

Number n=figure;

The figure variable is assignable to n . If this is expressed in Java code using isAssignableTo method, then the code should be:

target.isAssignableto(Number.class)

In which the target variable is an instance of TypeDescription, and it represents the java.lang.Integer.

Therefore, the matching logic specified in the matches method is matching the Java class that is in com.millionstrengthknowledge. interceptorprj.repository package, and the class is assignable to java.lang.Serializable. Based on this matching criteria, only the UserRepository.class fulfills the matching criteria because this class implements the java.io.Serializale interface.

188

![](Image00000.gif)

ElementMatchers.nameStartsWith

So the UserRepository.class continues to apply method of InterceptorRepositoryPlugin.java . The apply method has five visit method. The first visit method uses ElementMatcer.nameStartsWith method:

builder

.visit(new MemberAttributeExtension.ForMethod()

.annotateMethod(ElementMatcherUtil

.create(“nameStartsWith(‘create’)”))

.on(ElementMatchers.nameStartsWith(“create”)))

The nameStartsWith method is similar to the startsWith method of java. lang.String. The method is case sensitive. Therefore, the createUser and createAddress method of UserRepostotry.class are selected to add the annotation:

@ElementMatched(“nameStartsWith(‘create’)”)

public void createUser() { }

@ElementMatched(“nameStartsWith(‘create’)”)

public void createAddress() { }

ElementMatchers. nameContainIgnoreCase

The next example uses ElementMatchers.nameContainsIgnoreCase method:

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(

ElementMatcherUtil.create(

“nameContainsIgnoreCase(‘test’)”))

.on(ElementMatchers

.nameContainsIgnoreCase(“test”)));

189

![](Image00000.gif)

The nameContainsIgnoreCase method is not case sensitive and it matches all the methods that contain the required text in the method name. Therefore, the databaseTestUrl and testMtd1 method of UserRepository.class are selected to add the annotation:

@ElementMatched(“nameContainsIgnoreCase(‘test’)”)

public void databaseTestUrl() { }

@ElementMatched(“nameContainsIgnoreCase(‘test’)”)

public void testMtd1(Double p) { }

ElementMatchers.not

The next example uses the ElementMatchers.not method:

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(ElementMatcherUtil.create(

“method return non-void”))

.on((ElementMatchers.not(ElementMatchers

.returns(void.class))));

The not method can be used to invert the matching logic. This example matches the method that return anything except void.class. So, the queryUser method of UserRepository.class is selected because this is the only method that return object reference in UserRepository.class :

@ElementMatched(“method return non-void”)

public List<Object> queryUser(){ return null; }

190

![](Image00000.gif)

ElementMatchers.isVarArgs

Next, the visit method uses ElementMatchers.isVarArgs method:

builder.visit(new MemberAttributeExtension.

ForMethod()

.annotateMethod(

ElementMatcherUtil.create(

“method use varargs”))

.on(ElementMatchers.isVarArgs()));

The isVarArgs method returns true when the method uses variable- length argument. Therefore, multipleParam1 and multipleParam2 method of UserRepository.class are selected in this example:

@ElementMatched(“method use varargs”)

public void multipleParam1(int... test) { }

@ElementMatched(“method use varargs”)

public void multipleParam1(String data, int... test) { }

ElementMatchers.isOverriddenFrom

Next, the visit method uses ElementMatchers.isOverriddenFrom method:

builder.visit(new MemberAttributeExtension. ForMethod()

.annotateMethod(

ElementMatcherUtil.create(“Override from

GeneralRepository.java”))

.on(ElementMatchers.isOverriddenFrom(

GeneralRepository.class))

);

191

![](Image00000.gif)

The isOverriddenFrom method returns true when the method overrides the method of its superclass. The superclass of UserRepository. java is GeneralRepository.java , which contains the process method. UserRepository.java overrides this method in its implementation, therefore the process method of UserRepository.class is selected to add the annotation:

@ElementMatched(“Override from

GeneralRepository.java”)

publc void process(){ }

InterceptorQueryPlugin

At this stage, the chapter has completed the explanation for the InterceptorRepositoryPlugin.java . The last plugin program is the InterceptorQueryPlugin.java . This is the matching logic implemented in the matches method of InterceptorQueryPlugin.java :

if(target.getName().startsWith(

“com.millionstrengthknowledge.interceptorprj. repository”)){

int annotationFound=

target.getDeclaredAnnotations().filter(

ElementMatchers.anyOf(

AnnotationDescription.Builder

.ofType(QueryType.class).build(),

AnnotationDescription.Builder

.ofType(GenericQueryType.class)

.build()

)

).size();

int methodFound=target

.getDeclaredMethods().filter(

ElementMatchers.named(“toString”)

).size();

if(methodFound>0 && annotationFound>0) {

System.out.println(

192

![](Image00000.gif)

“InterceptorQueryPlugin found target: “+

target.getName()

);

return true;

}

else {

return false;

}

}

else

return false;

The matching logic implemented these three conditions:

The target Java class is from the com.millionstrenthknowledge. interceptorprj.repository package.

The target Java class must have either @GenericQueryType or @ QueryType annotation at the class level.

The target Java class must implement the toString method.

FilterableList

The first condition is implemented using getName method of TypeDescription . The second and third condition is implemented using filter method of net.bytebuddy.matcher.FilterableList . The filter is the new concept in this chapter, and it is one of the techniques userd to implement the matching logic. To get the instance of FilterableLIst , invokes the getDeclaredAnnotations method of TypeDescription . The getDeclaredAnnotations returns an instance of FilterableList , which contains the list of annotation that the Java class uses at class level. The FilterableList has a filter method that can apply ElementMatchers. In this example, the filter uses ElementMatchers. anyOf method:

193

![](Image00000.gif)

int annotationFound=

target.getDeclaredAnnotations().filter(

ElementMatchers.anyOf(

AnnotationDescription.Builder.ofType(

QueryType.class).build(),

AnnotationDescription.Builder.ofType(

GenericQueryType.class)

.build()

)

).size();

In this example, the filter selects the Java class that uses either @ QueryType or @GenericQueryType . The anyOf method returns true when any one of its parameter fulfills the matching criteria.

Then the size method returns the number of items in the filtered list. The size method returns zero if the list is empty, that means no object in the list fulfill the matching criteria. Otherwise, there will be at least one object in the list and the size method should return an integer value that is greater than zero. The size of the filter is stored into the annotationFound int variable.

The matches method then continues to filter the target class. This time the matches method filter the method of the target class:

int methodFound=target.getDeclaredMethods()

.filter(ElementMatchers.named(“toString”))

.size();

To filter the methods, first retrieves the full list of method using the getDeclaredMethods method of TypeDescription . Then, invokes filter method and applies the ElementMatchers . The program wants to match the toString method, so the named method is suitable for this case. After that, the size method is invoked to get the number of filtered item in the full list, and this number is stored into methodFound int variable.

After all, the matches method return true only if both annotationFound and methodFound variable has value greater than zero. Based on the matching criteria, only the DataQuery.class and UserQuery.class are

194

![](Image00000.gif)

selected for further instrumentation process.

The InterceptorQueryPlugin.java plugin program continues to apply method for DataQuery.class and UserQuery.class . In apply method, there is another filter applied:

int queryMethodCount=target

.getDeclaredMethods().filter(

ElementMatchers.named(“query”)).size();

The target is the variable from the second parameter of apply method, and it is an instance of TypeDescription. The target variable represents the same Java class that is presented in TypeDescription parameter of matches method. In apply method, the target variable is further filtered to match the Java method with named “ query ”. Therefore, the filter method uses ElementMatchers.named method for this purpose. The result of the filter is stored into queryMethodCount int variable. The queryMethodCount variable is used for this conditional checking:

if(queryMethodCount==0) {

builder=builder.annotateType(

ElementMatcherUtil.create(“QueryType does not implement query method”));

}

If the queryMethodCount equals to zero, then that means the Java class does not implement the query method because the filter fails to find the query method in that Java class. If the method is not found, then the instrumentation process add the @ElementMatched annotation to the class level of that Java class. In this example, this Java class is the DataQuery.class . Therefore, the @ElementMatched is added to DataQuery.class :

@GenericQueryType

@ElementMatched(“QueryType does not implement query method”)

public class DataQuery<A, B extends Long> {

195

![](Image00000.gif)

After that, the method continues to other interception logic. There are six visit methods. The first visit method attempts to match the int instance variable in the Java class:

builder.visit(

new MemberAttributeExtension.ForField()

.annotate(ElementMatcherUtil.create(

“int field”))

.on(ElementMatchers.fieldType(

ElementMatchers.is(TypeDescription

.ForLoadedType.of(int.class)))

)

);

The matching logic uses ElementMatchers.fieldType and ElementMatchers.is method.

The is method is similar to “equal”. When the matching criteria is equal to the parameter specified, then the is method returns true. Because the matching logic attempts to match int instance variable, the parameter of is method is passed with the TypeDescription.ForLoadedType. of(int.class) , which returns the instance of TypeDescription that represents the int.class. The result of is method is passed to the ElementMatchers.fieldType method, so that the matching logic can check the instance variable, and return true if the instance variable is equals to type of int.class. Therefore, the program should have found that DataQuery.class and UserQuery.class fulfills the matching criteria. In DataQuery.class , there is one int instance variable:

@ElementMatched(“int field”)

private int data1;

The UserQuery.class also has one int instance variable:

@ElementMatched(“int field”)

private int number;

196

![](Image00000.gif)

ElementMatchers.genericFieldType

The next visit method matches the instance variable with type variable A. Similarly, the ElementMatchers.is method is used. Instead of ElementMatchers.fieldType method, the ElementMatchers. genericFieldType method is used in this example because the instance variable is a generic field:

builder.visit(new MemberAttributeExtension

.ForField()

.annotate(ElementMatcherUtil.create(“A field”))

.on(

ElementMatchers.genericFieldType(

ElementMatchers.is(

TypeDescription.Generic.Builder

.typeVariable(“A”).build()))));

Therefore, the data4 instance variable of DataQuery.class fulfills the matching criteria:

@ElementMatched(“A field”)

private A data4;

ElementMatchers.erasure

Next, the plugin program matches the generic instance variable that has type erasure of java.lang.Long. To find the generic instance variable, the ElementMatchers.genericFieldType method is used. However, the ElementMatchers.is method is not applicable. Instead, the ElementMatchers.erasure method is used:

builder.visit(new MemberAttributeExtension

.ForField()

.annotate(ElementMatcherUtil.create(

“Long erasure field”))

.on(

ElementMatchers.genericFieldType(

ElementMatchers.erasure(Long.class))));

197

![](Image00000.gif)

Therefore, the program should have found the instance variable with type erasure of java.lang.Long in DataQuery.class . DataQuery.class has one type argument “B”, which is upper bounded to java.lang.Long:

public class DataQuery<A, B extends Long>

The data5 instance variable is typed to B, so this instance variable matches with the matching criteria, and it is selected to add the @ ElementMatched annotation:

@ElementMatched(“Long erasure field”)

private B data5;

ElementMatchers.isAnnotatedWith

The next visit method matches the instance variable with @ Deprecated annotation. For this purpose, the ElementMatchers. isAnnotatedWith method is used:

builder.visit(new MemberAttributeExtension

.ForField()

.annotate(ElementMatcherUtil.create(

“Deprecated field”))

.on(

ElementMatchers.isAnnotatedWith(

Deprecated.class)));

The isAnnotatedWith method accepts the parameter of java.lang. Class, in which the class should be the class of Java annotation. The isAnnoatedWith method returns true when the class of annotation of the instance variable matches with the class in the parameter. In DataQuery.class , the data6 instance variable matches with the matching criteria because it has one @Deprecated annotation:

@ElementMatched(“Deprecated field”)

@Deprecated

private String data6;

198

![](Image00000.gif)

ElementMatchers.isDeclaredBy

Next, the plugin program matches the method that is declared by the DataQuery.java , and the method does not override the method of the java.lang.Object super class. For this purpose, the ElementMatchers. isDeclaredBy and ElementMatchers.isOverriddenFrom method are used:

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(ElementMatcherUtil.create(

“Method declared by DataQuery”))

.on(

ElementMatchers.isDeclaredBy(

DataQuery.class).and(

ElementMatchers.not(

ElementMatchers.isOverriddenFrom(

Object.class)))));

The isDeclaredBy method returns true when the method is owned by the Java class specified in the parameter. In order to match the method that does not override the java.lang.Object super class, the not method is used with the isOverriddenFrom method. Therefore, in DataQuery. class , the test method matches with the criteria:

@ElementMatched(“Method declared by DataQuery”)

public void test(){ }

199

![](Image00000.gif)

ElementMatchers.hasParameter and ElementMatcher

Next, the plugin program matches the method with java.lang.Double parameter, and that parameter is annotated with a @Deprecated annotation. For this purpose, the visit method uses ElementMatchers. hasParameters method:

builder.visit(new MemberAttributeExtension

.ForMethod()

.annotateMethod(ElementMatcherUtil

.create(“Double.class parameter”))

.on(

ElementMatchers.hasParameters(paramMatcher))

);

The hasParameters return true when the method parameter matches with the parameter matcher specified in the parameter. Observed that the hasParameters is passed with a paramMatcher variable. This is the declaration of the paramMatcher variable:

ElementMatcher<Iterable<? extends

ParameterDescription>> paramMatcher =

(paramDescrList)->{

for (ParameterDescription param :

paramDescrList) {

int deprecatedCount=

param.getDeclaredAnnotations().filter(

ElementMatchers.annotationType(

Deprecated.class)).size();

if (deprecatedCount>0&&param.getType()

.equals(TypeDescription.ForLoadedType

.of(Double.class)))

return true;

}

return false; };

200

![](Image00000.gif)

The paramMatcher is an instance of net.bytebuddy.matcher. ElementMatcher. The ElementMatcher is a functional interface with one method named matches . The parameter of matches method is an instance of java.lang.Iterable.

In this example, the name of this parameter is paramDescrList , and it represents all the parameters of the Java method. The element of paramDescrList is the type of net.bytebuddy.description.method. ParameterDescription . The ParameterDescription contains the meta information about each of the parameter in the Java method.

To check the data type and annotation used by the parameter, the for loop is used to iterate the list. Each loop returns an instance of ParameterDescription and it is stored into param variable. In each loop, the program uses the param variable to access the meta information of each parameter.

In each loop, invokes paramDescrList.getDeclaredAnnotation method, which returns the list of annotation used by each parameter. Then, chains the method to filter method. The filter uses ElementMatchers.annotationType method to match the @ Deprecated annotation on that parameter. The result of filter is stored into deprecatedCount variable. If one @Deprecated annotation is found on the parameter, then the value of deprecatedCount is one.

Then the deprecatedCount variable is used in next conditional check:

if (deprecatedCount>0&&param.getType().equals(

TypeDescription.ForLoadedType

.of(Double.class)))

return true;

The conditional check verifies that the deprecatedCount is more than zero, and the param variable is type of java.lang.Double. The getType method of ParameterDescription is used to check the type of the parameter. Therefore, with this conditional check, the program can decide whether the parameter has one @Deprecated annotation and it is type of java.lang.Double. The method return true if the condition check is valid, otherwise false.

The boolean value is then used by the hasParameters method in the visit method. Therefore, the program should have matched the target code according to the matching requirement. In this example, the

201

![](Image00000.gif)

queryOther method of UserQuery.class fulfills the matching criteria, and it is added the @ElementMatched annotation:

@ElementMatch(“Double.class parameter”)

public void queryOther(int p1,

@Deprecated Double p2, String p3, Double p4) { }

Import static for ElementMatchers

All of the method of ElementMatchers are static. To reduce coding, uses import static to import the static method of ElementMatchers. For example:

import static net.bytebuddy.matcher.

ElementMatchers.isDeclaredBy;

import static net.bytebuddy.matcher.

ElementMatchers.not;

import static net.bytebuddy.matcher.

ElementMatchers.isOverriddenFrom;

With these declaration of import, this code segment:

.on(ElementMatchers.isDeclaredBy(

DataQuery.class).and(

ElementMatchers.not(

ElementMatchers.isOverriddenFrom(

Object.class)))));

can be changed to:

.on(isDeclaredBy(DataQuery.class).and(

not(isOverriddenFrom(Object.class)))));

202

![](Image00000.gif)

Conclusion

The chapter explains on how to use ElementMatchers to develop matching logic to match the target Java element for instrumentation process.

203

![](Image00000.gif)

Chapter 18: Generate Inner Class

This chapter explains on how to generate inner class, and intercept inner class and anonymous class using ByteBuddy. The source code of this chapter is included in ChapterDefineInnerClass Eclipse project.

There are two plugin programs in this chapter: DataReaderPlugin. java and RepositoryPlugin.java . The DataReaderPlugin.java is responsible to create two new inner classes in the DataReader.java . Before instrumentation, DataReader.java is an empty class:

public class DataReader{ }

After instrumentation, this is the java source code view of DataReader. class and its inner class:

DataReader.java:

public class DataReader{

}

DataReader$Storage.java:

public class DataReader$Storage {

public String createUuid() {

String var1 = null;

var1 = UUID.randomUUID().toString();

return var1;

}

}

204

![](Image00000.gif)

DataReader$Storage$Util.java:

public class DataReader$Storage$Util extends AbstractUtil implements UtilIntf {

public String getData() {

return “data value”;

}

}

The instrumentation process adds one inner class named Storage.java to the DataReader.java . Then the instrumentation adds another inner class , Util.java , to Storage.java . So, after instrumentation process, two inner class files are created.

The RepositoryPlugin.java is responsible to add a new method named “ innerTest ” method to all the inner class and anonymous class found in the DataProducer.java. This is the source code of DataProducer. java before instrumentation:

public class DataProducer {

public class User {

private String name;

public User(String n) {

this.name = n;

}

public String getName() {

Runnable r=new Runnable(){

public void run() {

System.out.println(

“getName anonymous class”);

}

};

r.run();

return this.name;

}

205

![](Image00000.gif)

public class UserEntityUtil{

public String nameToUppercase() {

Runnable r=new Runnable(){

public void run() {

System.out.println(

“nameToUppercase anonymous class”);

}

};

r.run();

return name.toUpperCase();

}

}

}

private class Address {

private String address;

public Address(String addr) {

this.address = addr;

}

public String get() {

return this.address;

}

}

}

After instrumentation, the instrumentation process adds one method named innerTest to all the inner class and anonymous class. Besides that, the instrumentation process also adds one enter advice code to all the methods of inner class and anonymous class, excepts the innerTest method. This is the source code view of the DataProducer. class, and its inner class and anonymous class after the instrumentation process:

206

![](Image00000.gif)

DataProducer.java:

public class DataProducer { }

DataProducer$Address.java:

class DataProducer$Address {

private String address;

// $FF: synthetic field

final DataProducer this$0;

public DataProducer$Address(DataProducer var1, String addr) {

this.this$0 = var1;

this.address = addr;

}

public String get() {

System.out.println(“OnMethodEnter Advice: “ + “com.millionstrengthknowledge.interceptorprj. repository.DataProducer$Address” + “ “ + “get”);

return this.address;

}

public String innerTest() {

return “com.millionstrengthknowledge. interceptorprj.repository.DataProducer$Address”;

}

}

207

![](Image00000.gif)

DataProducer$User.java:

public class DataProducer$User {

private String name;

// $FF: synthetic field

final DataProducer this$0;

public DataProducer$User(DataProducer this$0, String n) {

this.this$0 = this$0;

this.name = n;

}

public String getName() {

System.out.println(“OnMethodEnter Advice: “ + “com.millionstrengthknowledge. interceptorprj.repository.DataProducer$User” + “ “ + “getName”);

1 var1 = new 1(this);

var1.run();

return this.name;

}

public String innerTest() {

return “com.millionstrengthknowledge. interceptorprj.repository.DataProducer$User”;

}

}

DataProducer$User$1.java:

class DataProducer$User$1 implements Runnable {

// $FF: synthetic field

final User this$1;

DataProducer$User$1(User this$1) {

this.this$1 = this$1;

}

208

![](Image00000.gif)

public void run() {

System.out.println(“OnMethodEnter Advice: “ + “com.millionstrengthknowledge. interceptorprj.repository.DataProducer$User$1” + “ “ + “run”);

System.out.println(“getName anonymous class”);

}

public String innerTest() {

return “com.millionstrengthknowledge. interceptorprj.repository.DataProducer$User$1”;

}

}

DataProducer$User$UserEntityUtil.java:

public class DataProducer$User$UserEntityUtil {

// $FF: synthetic field

final User this$1;

public DataProducer$User$UserEntityUtil(User this$1) {

this.this$1 = this$1;

}

public String nameToUppercase() {

System.out.println(“OnMethodEnter Advice: “ + “com.millionstrengthknowledge.interceptorprj. repository.DataProducer$User$UserEntityUtil” + “ “ + “nameToUppercase”);

1 var1 = new 1(this);

var1.run();

return this.this$1.name.toUpperCase();

}

209

![](Image00000.gif)

public String innerTest() {

return “com.millionstrengthknowledge. interceptorprj.repository. DataProducer$User$UserEntityUtil”;

}

}

DataProducer$User$UserEntityUtil$1.java:

class DataProducer$User$UserEntityUtil$1

implements Runnable {

// $FF: synthetic field

final UserEntityUtil this$2;

DataProducer$User$UserEntityUtil$1(

UserEntityUtil this$2) {

this.this$2 = this$2;

}

public void run() {

System.out.println(“OnMethodEnter Advice: “+

“com.millionstrengthknowledge.interceptorprj.

repository.DataProducer$User$UserEntityUtil$1”

+ “ “ + “run”);

System.out.println(“nameToUppercase anonymous

class”);

}

public String innerTest() {

return “com.millionstrengthknowledge.

interceptorprj.repository.

DataProducer$User$UserEntityUtil$1”;

}

}

The highlighted code is the code generated based on advice code provided in InnerClassAdvice.java.

210

![](Image00000.gif)

DataReaderPlugin

In DataReaderPlugin .java, the first level matching logic is implemented in matches method. The matching logic uses getName method to match the DataProducer.java . Once the class is matched, the method returns true and continue to apply method.

The apply method will create two new inner classes: Storage.java and Util.java . The net.bytebuddy.description.type.TypeDescription. Latent is the fundamental Java class used to create inner class in ByteBuddy. The apply method uses TypeDescription.Latent to create firstInnerTd and secondInnerTd instance, which represents the Storage.java and Util.java respectively:

TypeDescription firstInnerTd =

new TypeDescription.Latent(

“com.millionstrengthknowledge.interceptorprj

.repository.DataReader$Storage”,

Opcodes.ACC_PUBLIC,

TypeDescription.Generic.OBJECT) {

@Override

public String getSimpleName() {

return “Storage”;

}

@Override

public boolean isAnonymousType() {

return false;

}

@Override

public boolean isMemberType() {

return true;

}

};

211

![](Image00000.gif)

The constructor of TypeDescription.Latent has four parameters:

Latent(String name, int modifiers,

TypeDescription.Generic superClass,

TypeDescription.Generic... anInterface)

The first parameter is used to specify the name of the inner class, the name must be in fully qualified class name format. In this example, the inner class name is “ com.millionstrengthknowledge. interceptorprj.repository.DataReader$Storage ”

The second parameter is used to specify the modifier of the inner class. The Storage.java is a public inner class, so the second parameter specifies Opcodes.ACC_PUBLIC .

The third parameter is used to specify the superclass of the inner class. In Java, every class is the derived class of java.lang.Object. Since the inner class does not have any other superclass than java.lang.Object, so specify the java.lang.Object for its superclass. In ByteBuddy, the program can use TypeDescription.Generic.Object to represent the java.lang.Object.

The forth parameter is not applicable in this chapter, and it is optional. So the plugin program omits this parameter.

After that, there are three methods that are required to implement for the TypeDescription.Latent : getSimpleName , isAnonymousType , and isMemberType method.

To implement the getSimpleName method:

public String getSimpleName() {

return “Storage”;

}

The purpose of getSimpleName is to return the name of the inner class. Therefore, the method simply return a string value of “Storage”, for the Storage.java inner class.

The purpose of isAnonymousType method is to provide the status of anonymous class type in boolean value. The Storage.java is not an anonymous class. So the method should return false.

212

![](Image00000.gif)

public boolean isAnonymousType(){

return false;

}

The isMemberType method provide the status of member class type in boolean value. The Storage.java is an inner class and it is declared in DataReader.java . So the method should return true because the Storage.java is the member class of DataReader.java :

public boolean isMemberType(){

return true;

}

Generate first level inner class

The firstInnerTd is an instance of TypeDescription.Latent. The inner class is in TypeDescription format at this stage, and not yet in Java class format. To convert TypeDescription to Java class format, the plugin program needs to use net.bytebuddy.ByteBuddy for this purpose:

DynamicType.Builder<?> firstInnerBuilder=

new ByteBuddy()

.subclass(Object.class)

.name(firstInnerTd.getName())

.innerTypeOf(td).asMemberType()

.defineMethod(“createUuid”, String.class,

Visibility.PUBLIC)

.intercept(FixedValue.nullValue());

(1) Instantiate an instance of ByteBuddy

new ByteBuddy()

The instance of ByteBuddy is the entry point to the instrumentation process. The instance is used to configure the instrumentation behavior. All the previous chapters does not require to instantiate the instance of ByteBuddy because the plugin program will create one implicitly during the maven build time. The new instance is required

213

![](Image00000.gif)

here because the plugin program wants to use subclass method to create new Java inner class. The subclass method is not available via the DynamicType.Builder .

(2) Configure the instrumentation process to create a new Java class that extends the java.lang.Object:

.subclass(Object.class)

The subclass method instructs the instrumentation process to use inheritance in Object oriented programming of Java. That mean the generated Java class is a derived class of java.lang.Object. This looks redundant because the firstInnerTd has already specifies the superclass in the constructor of TypeDescription.Latent . However, this configuration is used for the generation of Java class, the Latent is used for constructing the TypeDescription.

(3) Configure the name for the inner class

.name(firstInnerTd.getName())

The name method provides the fully qualified class name of the generated Java class. So the method invokes the getName method of the firstInnerTd to get the fully qualified class name of the Storage. java .

(4) Configure the top outer class of the inner class

.innerTypeOf(td).asMemberType()

The innerTypeOf method specifies the top outer class for the inner class. The td is the instance of TypeDescription, which is obtained from the second parameter of apply method. The td represents the instance of DataReader.class , which is the top outer class of Storage. java . Therefore, the parameter of innerTypeOf method specifies td . The asMemberType method specifies that the inner class is type of

214

![](Image00000.gif)

member class.

Generate method to inner class

At this stage, the configuration of the instrumentation process should be able to create the Java class for Storage.java . However, the inner class is an empty class. The plugin program can continue the configuration by declaring the constructor, method, instance variable and other Java element for the inner class. In this example, the subsequent configuration declares a method named “ createUuid ”:

.defineMethod(“createUuid”, String.class,

Visibility.PUBLIC)

.intercept(FixedValue.nullValue());

The createUuid method is a public method that returns a java.lang. String. The method returns null value at the declaration time. Then the plugin program further uses visit method to modify the implementation of the method body of the createUuid method:

firstInnerBuilder=firstInnerBuilder.visit(

Advice.to(UuidGenerator.class)

.on(ElementMatchers.named(“createUuid”)));

The visit method adds the UuidGenerator.class advice code to the createUuid method. After that, the configuration of Storage.java is almost completed. The Storage.java has an inner class also, named Util.java . Therefore, the plugin program continue to generate Util.java inner class.

Generate second level inner class

To declare the Util.java inner class for Storage.java, the plugin program needs to declare a new instance of TypeDescription.Latent. This instance is the secondInnerTd :

TypeDescription secondInnerTd =

new TypeDescription.Latent(

“com.millionstrengthknowledge

215

![](Image00000.gif)

.interceptorprj.repository

.DataReader$Storage$Util”,

Opcodes.ACC_PUBLIC | Opcodes.ACC_STATIC,

TypeDescription.Generic.OBJECT) {

@Override

public String getSimpleName() {

return “Util”;

}

@Override

public boolean isAnonymousType() {

return false;

}

@Override

public boolean isMemberType() {

return true;

}

};

Since the Util.java is the public static inner class of Storage.class , so its name is “ com.millionstrengthknowledge.interceptorprj. repository.DataReader$Storage$Util ”, and the modifier configuration is Opcodes.ACC_PUBLIC | Opcodes.ACC_STATIC . The remaining implementation should be similar with the firstInnerTd .

After that, create another instance of ByteBuddy to configure the transformation process for Util.java :

new ByteBuddy()

.subclass(AbstractUtil.class)

.name(secondInnerTd.getName())

.innerTypeOf(td).asMemberType()

.implement(UtilIntf.class)

.defineMethod(“getData”, String.class,

Visibility.PUBLIC)

.intercept(FixedValue.value(“data value”))

.make()

.saveIn(dir);

216

![](Image00000.gif)

The configuration of new ByteBuddy instance should follow these steps:

(1) Create an instance of ByteBuddy

new ByteBuddy()

(2) Configure the instrumentation process to extend AbstractUtil. java

.subclass(AbstractUtil.class)

(3) Configure the name for the inner class

.name(secondInnerTd.getName())

(4) Configure the top outer class of the inner class

.innerTypeOf(td).asMemberType()

Please be noticed that the DataReader.java is the top outer class, not the Storage.java . Therefore the plugin program passes the td variable to the innerTypeOf method.

(5) Optionally, configure the super interface for the inner class

.implement(UtilIntf.class)

The implement method is used to specify that the inner class wants to implements the UtilIntf.java interface.

(6) Optionally, declares the method for the inner class

.defineMethod(“getData”, String.class,

Visibility.PUBLIC)

.intercept(FixedValue.value(“data value”))

The configuration declares a method named “ getData ” for the Util.

217

![](Image00000.gif)

java .

(7) Complete the configuration, generate the Java class, and stores it into an instance of Dynamic.Unloaded

.make()

Invoke make method to generate the Java class of the Util.java. Then, the make method will create an instance of net.bytebuddy.dynamic. Dynamic.Unloded , and stores the Java class of Util.java into this instance. At this stage, the util.class is not yet loaded into the JVM.

(8) Save the Java class into disk

.saveIn(dir)

Invokes saveIn method to save the Util.class into disk.

All the previous chapters does not require to save the Java class file explicitly because the maven process will save the file. However, for inner class, the plugin program needs to save the file explicitly because it is created by a new instance of ByteBuddy, which is not in the control of maven build process. Please change the directory of the dir variable because it is pointing to the “ C:/Users/user01/workspace/ interceptor/ChapterDefineInnerClass/target/classes/ ” in the plugin program. Change the directory name to the directory that stores the Java class file for the Eclipse project.

218

![](Image00000.gif)

Adding second level inner class to first level inner class

After saving the Util.class into disk, the plugin program can now complete the configuration for Storage.class :

firstInnerBuilder.declaredTypes(secondInnerTd)

.make()

.saveIn(dir);

Invoke the declaredTypes method of firstInnerBuilder instance. The declaredTypes method is similar to defineMethod method, which is used for declaring the method, while the declaredTypes method is used for declaring the inner class. The parameter of declaredTypes method accepts an instance of TypeDescription , so the program should pass the secondInnerTd to the method to create the Util.java inner class in Storage.java .

After that, invokes the make and saveIn method for Storage.java to save the Storage.class into disk.

Adding first level inner class to outer class

Finally, the plugin program needs to declare the Storage.java for the DataReader.java because Storage.java is the inner class of DataReader. java :

builder.declaredTypes(firstInnerTd);

After all, the DataReaderPlugin.java plugin program should completely generate the Storage.java and Util.java inner class in the DataReader. java.

219

![](Image00000.gif)

RepositoryPlugin

This chapter uses two plugin programs. This section explains the second plugin for this chapter: RepositoryPlugin.java . The RepositoryPlugin.java is used for instrumenting the inner class and anonymous class found in the com.millionstrengthknowledge. interceptorprj.repository package. This is the matching logic implemented in matches method of RepositoryPlugin.java :

if(target.getName().startsWith(

“com.millionstrengthknowledge.interceptorprj

.repository”) && (target.isInnerClass()||

target.isAnonymousType())

)

return true;

else

return false;

The if statement checks the name of the package name of the target variable, and uses isInnerClass method to check whether the target is an inner class, and uses isAnonymousType method to check whether the target is an anonymous class. Therefore, the if statement returns true when the target is either the inner class or anonymous class created in com.millionstrengthknowledge.interceptorprj. repository package. In this chapter, there are two outer classes in the com.millionstrengthknowledge.interceptorprj.repository package: DataReader.java and DataProducer.java .

DataReader.java does not have inner class and anonymous class before the instrumentation. After instrumentation process of DataReaderPlugin.java , DataReader.java contains two inner classes: Storage.java and Util.java .

DataProducer.java has three inner classes before the instrumentation: User.java , UserEntityUtil.java , and Address. java , and two anonymous class: DataProducer$User$1. java , DataProducer$User$UserEntityUtil$1.java . Therefore, DataProducer.java will continue to the instrumentation process of the RepositoryPlugin.java.

220

![](Image00000.gif)

Generate new method in inner class and anonymous class

In apply method, this is the implementation of the instrumentation process:

builder

.defineMethod(“innerTest”, String.class, Visibility.PUBLIC)

.intercept(FixedValue.value(td.getName()))

In apply method of RepositoryPlugin.java , the instrumentation adds one new method named “ innerTest ” to all the inner classes and anonymous classes. After instrumentation process, this is the source code view of the innerTest method of DataProducer$User.class :

public class DataProducer$User{

public String innerTest() {

return “com.millionstrengthknowledge.

interceptorprj.repository.DataProducer$User”;

}

//Other code is omitted

}

This is the source code view of the innerTest method of DataProducer$User$1.class :

class DataProducer$User$1 implements Runnable{

public String innerTest() {

return “com.millionstrengthknowledge.

interceptorprj.repository.DataProducer$User$1”;

}

//Other code is omitted

}

The innerTest method are also added to the UserEntityUtil. java , and Address.java , and the another anonymous class: DataProducer$User$UserEntityUtil$1.java.

221

![](Image00000.gif)

Intercepting method of inner class and anonymous class

After that, the plugin program uses visit method to intercept the InnerClassAdvice.class advice code to all the method of inner class and anonymous class, excepts the innerTest method:

builder.visit(

Advice.to(InnerClassAdvice.class)

.on(

ElementMatchers.isMethod().and(

ElementMatchers.not(

ElementMatchers.named(“innerTest”)

)

)

)

);

This is the source code of InnerClassAdvice.class :

public class InnerClassAdvice {

@OnMethodEnter

public static void start(

@Advice.Origin(“#t”) String mtdDeclrType,

@Advice.Origin(“#m”) String mtdName

) {

System.out.println(

“OnMethodEnter Advice: “+

mtdDeclrType+” “+

mtdName

);

}

}

The InnerClassAdvice.java implements one on method enter advice. The advice code prints the name of the Java class and the method of the functional code.

222

![](Image00000.gif)

After the instrumentation process, this is the source code view of the getName of DataProducer$User.class (the highlighted code is the generated code based on the advice code):

public String getName() {

System.out.println(“OnMethodEnter Advice: “ + “com.millionstrengthknowledge.interceptorprj.

repository.DataProducer$User” + “ “ +“getName”);

1 var1 = new 1(this);

var1.run();

return this.name;

}

This is the source code view of the run method of DataProducer$User$1. class (the highlighted code is the generated code based on the advice code):

public void run() {

System.out.println(“OnMethodEnter Advice: “+ “com.millionstrengthknowledge.interceptorprj. repository.DataProducer$User$1” + “ “ + “run”);

System.out.println(“getName anonymous class”);

}

RepositoryPlugin does not instrument the inner class of DataReader.class

Observed that the instrumentation process does not add the innerTest method to Storage.java and Util.java inner class of DataReader.java . This is because Storage.java and Util.java are the inner classes that are generated after the plugin program starts. Therefore, the plugin program does not include the newly generated inner class to the instrumentation process.

223

![](Image00000.gif)

Conclusion

This chapter explains about how to add inner class to the existing Java class, and how to intercept the inner class and anonymous class of the existing Java class.

224

![](Image00000.gif)

Chapter 19: Generate Java Interface, Enum, Annotation, Subclass, and Abstract Class

This chapter explains on how to generate Java Interface, enum, annotation, and subclass dynamically. The source code of this chapter is included in ChapterDefineInterface Eclipse project.

The InterceptorPlugin.java is the main plugin program for this chapter. The plugin program implements all the logic of code generation. The plugin program matches the User.java in com. millionstrengthknowledge.interceptorprj.entity package for the instrumentation process.

The apply method firstly declares a java.io.File variable dir to contain the reference to the directory that stores the compiled Java class.

File dir = new File(“C:\\Users\\user01\\

workspace\\interceptor\\ChapterDefineInterface\\ target\\classes”);

Please change the directory accordingly for the program to execute properly.

Generate new Java interface

The apply method instantiates an instance of net.bytebuddy. ByteBuddy . The instance is used to create the Java interface and configures the instrumentation process:

new ByteBuddy()

.makeInterface(Serializable.class)

.name(“com.millionstrengthknowledge

.interceptorprj.entity.EntityIntf”)

.defineMethod(“verify”, void.class,

225

![](Image00000.gif)

Visibility.PUBLIC)

.withoutCode()

.make()

.saveIn(dir);

(1) Instantiate an instance of ByteBuddy:

new ByteBuddy()

(2) Create the Java interface that extends the java.io.Serializable

.makeInterface(Serializable.class)

The makeInterface method configures the instance of ByteBuddy to generate a Java interface. In this example, the Java interface wants to extends the java.io.Serializable . For this purpose, the plugin program passes the Java class of java.io.Serializable to the parameter of makeInterface method. Please be noticed that the parameter is optional only. If the Java interface does not require to extend the other Java interface, then just leaves the parameter empty.

(3) Configure the name for the Java interface

.name(“com.millionstrengthknowledge

.interceptorprj.entity.EntityIntf”)

The name method is used to create the name of the Java interface. This parameter must be the fully qualified class name.

(4) Configure the method for the Java interface

.defineMethod(“verify”, void.class,

Visibility.PUBLIC)

.withoutCode()

This step is optional. The Java interface can have no method defined.

226

![](Image00000.gif)

However, the plugin program declares one method named verify for the EntityIntf .

(5) Complete the configuration and generates the Java class of Java interface:

.make()

The make method completes the configuration and then creates the Java interface in Java class format. ByteBuddy creates an instance of net.bytebuddy.dynamic.Dynamic.Unloaded and stores the Java class into this instance. At this stage, the Java class is not loaded into the JVM.

(6) Save the generated Java class into disk

.saveIn(dir);

The maven build process will not save the newly generated Java class. Therefore, the plugin program must explicitly invoke the saveIn method to persist the class file of Java interface into disk.

Therefore, the code above should generate this Java interface:

public interface EntityIntf

extends Serializable{

public void verify(){ }

}

227

![](Image00000.gif)

Generate new Java enum

Next, the plugin program generates a Java enum named “ DataEnum ”:

new ByteBuddy()

.makeEnumeration(“inst1”, “inst2”)

.name(“com.millionstrengthknowledge

.interceptorprj.entity.DataEnum”)

.implement(GeneralIntf.class)

.defineMethod(“execute”, void.class,

Visibility.PUBLIC)

.intercept(StubMethod.INSTANCE)

.make()

.saveIn(dir);

(1) Instantiate an instance of ByteBuddy:

new ByteBuddy()

(2) Create the enum

.makeEnumeration(“inst1”, “inst2”)

The makeEnumeration method configures the instance of ByteBuddy to generate the Java enum. Its parameter accepts a variable length argument of java.lang.String. Each of the string value is going to be the name of the instance of enum. This enum declares two instances: inst1 , inst2 .

(3) Create a name for the enum

.name(“com.millionstrengthknowledge

.interceptorprj.entity.DataEnum”)

(4) Optionally implements the Java interface for the enum

.implement(GeneralIntf.class)

The enum can optionally implement Java interface but not extends.

228

![](Image00000.gif)

(5) Optionally declares the method

.defineMethod(“execute”, void.class,

Visibility.PUBLIC)

.intercept(StubMethod.INSTANCE)

(6) Complete the configuration and generates the Java class of Java enum:

.make()

(7) Save the Java class into disk

.saveIn(dir)

After that, the code above should completely create the Java enum DataEnum :

public enum DataEnum implements GeneralIntf{

inst1, inst2;

public void execute(){ }

}

Generate new Java annotation

Next, the plugin program generate a Java annotation named EntityAnnotation . The annotation is created in the private method named createAnnotation of InterceptorPlugin.java :

AnnotationDescription entityAnnotationVar =

createAnnotation(dir);

In the createAnnotation method, there is a code segment that declares an instance of ByteBuddy. The instance is used to create the annotation:

new ByteBuddy()

.makeAnnotation()

.name(“com.millionstrengthknowledge

.interceptorprj.entity.EntityAnnotation”)

229

![](Image00000.gif)

.annotateType(retentionVar)

.annotateType(targetVar)

.defineMethod(“name”, String.class,

Visibility.PUBLIC)

.withoutCode()

.defineMethod(“description”, String.class,

Visibility.PUBLIC)

.withoutCode()

.make()

.saveIn(dir);

(1) Instantiate an instance of ByteBuddy

new ByteBuddy()

(2) Create the annotation

.makeAnnotation()

The makeAnnotation method configures the instance of ByteBuddy to generate the Java annotation.

(3) Configure the name for the new annotation

.name(“com.millionstrengthknowledge

.interceptorprj.entity.EntityAnnotation”)

The name for this new annotation is EntityAnnotation . At this stage, the annotation should have this structure:

public @interface EntityAnnotation{ }

The new annotation requires more settings, for example, retention policy, enumeration type, which will be configured in the subsequent steps.

230

![](Image00000.gif)

(4) Configure the @Retention annotation for the new annotation

.annotateType(retentionVar)

The annotateType method is used to add the annotation to the Java element. This method adds the @Retention annotation to the EntityAnnotation . For this purpose, the annotateType method requires an instance of AnnotationDescription that represents the @Retention annotation. The retentionVar is the variable for this purpose:

AnnotationDescription retentionVar =

AnnotationDescription.Builder

.ofType(Retention.class)

.define(“value”, RetentionPolicy.RUNTIME)

.build();

With the use of the retentionVar variable, the annotateType(retentionVar) method should add the @Retention to the EntityAnnotation.class :

@Retention(RetentionPolicy.RUNTIME)

public @interface EntityAnnotation{ }

(5) Configure the @Target annotation for the new annotation

.annotateType(targetVar)

The plugin program further configures the new annotation to have the @Target annotation. The targetVar is the variable that represents the @Target annotation:

AnnotationDescription targetVar =

AnnotationDescription.Builder.ofType(

Target.class)

.defineEnumerationArray(

“value”,

ElementType.class,

ElementType.TYPE,

231

![](Image00000.gif)

ElementType.CONSTRUCTOR,

ElementType.METHOD

)

.build();

With the use of the targetVar variable, the annotateType(targetVar) should add the @Target to the EntityAnnotation.class :

@Retention(RetentionPolicy.RUNTIME)

@Target({java.lang.annotation.ElementType.TYPE,

java.lang.annotation.ElementType.CONSTRUCTOR,

java.lang.annotation.ElementType.METHOD})

public @interface EntityAnnotation{ }

(6) Configure the attribute for the new annotation

.defineMethod(“name”, String.class,

Visibility.PUBLIC)

.withoutCode()

.defineMethod(“description”, String.class,

Visibility.PUBLIC)

.withoutCode()

The attribute of the Java annotation is in Java method format. Therefore, the plugin program uses defineMethod method to create name and description attribute for EntityAnnotation.class . With this declaration, the EntityAnnotation.class should have this structure at this stage:

@Retention(RetentionPolicy.RUNTIME)

@Target({java.lang.annotation.ElementType.TYPE,

java.lang.annotation.ElementType.CONSTRUCTOR,

java.lang.annotation.ElementType.METHOD})

public @interface EntityAnnotation{

String name();

String description();

}

232

![](Image00000.gif)

(7) Complete the configuration and generates the Java class of the Java annotation:

.make()

(8) Save the Java class of new annotation into disk

.saveIn(dir)

After all, the createAnnotation method has created the EntityAnnotation completely. Before the createAnnotation method exits, the method wants to return an instance of AnnotationDescription of EntityAnnotation because the plugin program wants to use this instance to add @ EntityAnnotation to the User.class . Therefore, this line of code loads the java.lang.Class of EntityAnnotation into entityVar variable:

Class entityVar=

Class.forName(

“com.millionstrengthknowledge.interceptorprj

.entity.EntityAnnotation”);

Before the createAnnotation method returns, it instantiates an instance of AnnotationDescription that represents the @EntityAnnotation . For this purpose, the parameter of ofType method is passed with the entityVar variable:

return AnnotationDescription.Builder

.ofType(entityVar)

.define(“name”, “User”)

.define(“description”, “User table for storing

user record”).build();

The instance defines “ User “ value for name attribute, and defines “ User table for storing user record ” for “ description ” attribute. The build method completes the declaration of the instance of AnnotationDescription, and this instance is returned from the method.

233

![](Image00000.gif)

After the createAnnotation method returns, the instance of the AnnotationDescription is stored into entityAnnotationVar variable:

AnnotationDescription entityAnnotationVar =

createAnnotation(dir);

The entityAnnotationVar will be used in the instrumentation of User. class . However, before the plugin program instruments the User.class , the plugin program will generate another new Java class, EntityUtil .

Generate new Java class

Next, the plugin program generates a new Java class named EntityUtil :

new ByteBuddy()

.subclass(Object.class)

.modifiers(Opcodes.ACC_PUBLIC |Opcodes.ACC_FINAL)

.name(“com.millionstrengthknowledge

.interceptorprj.entity.EntityUtil”)

.defineMethod(“getUniqueNumber”,

String.class,

Visibility.PUBLIC

)

.throwing(Exception.class)

.intercept(FixedValue.value(“12345”))

.defineMethod(“getWordLengthFunction”,

Function.class,

Visibility.PUBLIC

)

.intercept(

InvokeDynamic.lambda(

StringService.class

.getDeclaredMethod(“wordLength”,

Object.class),

Function.class

)

)

.make()

234

![](Image00000.gif)

.saveIn(dir);

The subclass method configures the instance of ByteBuddy to generate a new Java class. Very similar to the Java interface and enum explained in last sections, the plugin program instantiates the ByteBuddy instance, creates the name, defines method, declares the throws clause, generates the Java class, and saves the Java class to disk. After all, the code above should create this new Java class:

public final class EntityUtil {

public String getUniqueNumber(){

return “12345”;

}

}

There are two new concepts introduced in this example. First, observed that the code uses modifier method: modifier(Opcodes. ACC_PUBLIC | Opcodes.ACC_FINAL) . The modifier method is used to add the modifier to the Java class. In this example, the modifier method changes the Java class to be public final class.

Generate lambda expression

Second, the new Java class declares a method named getWordLengthFunction , and generates the method body using the InvokeDynamic.lambda :

.defineMethod(“getWordLengthFunction”,

Function.class,

Visibility.PUBLIC

)

.intercept(

InvokeDynamic.lambda(

StringService.class

.getDeclaredMethod(“wordLength”,

Object.class),

Function.class )

The plugin program generates the method body using lambda

235

![](Image00000.gif)

expression. To use lambda expression, the defined method must return the functional interface . In this example, this functional Interface is the java.util.function.Function . Then the intercept method is used to instrument the defined method. The instrumentation generates the lambda expression using the lambda method.

The InvokeDynamic is a Java component provided by ByteBuddy in net.bytebuddy.implementation package. The lambda method is one of the method of InvokeDynamic . The lambda method accepts two parameter: java.lang.reflect.Method, java.lang.Class .

In this example, the first parameter obtains an instance of Method via StringService.class.getDeclaredMethod(“wordLength”, Object. class) . This is the source code of StringService.java :

public class StringService {

public static Integer wordLength(Object data){

return ((String)data).length();

}

}

The instance of the Method is used to provide the implementation of the lambda expression. Observed that the wordLength method accepts one parameter of java.lang.Object and returns an java.lang. Integer . In this example, the functional interface is the Function.java, which has this method signature:

public interface Function<T,R>{

public R apply (T param);

}

Therefore the functional interface requires one parameter and return, and wordLength method must have the same number of parameter and return also. The parameter of the wordLength method is java. lang.Object . This is required because the Function.java requires one parameter. This parameter must be in java.lang.Object , otherwise it will cause compilation error in maven build process. Besides that, the wordLength method is required to be a static method.

So, that is how the program should implement the first parameter for the lambda method of InvokeDynamic . Then the second parameter

236

![](Image00000.gif)

of lambda method should uses the Java class of java.util.function. Function because the getWordLengthFunction method wants to return an instance of Function.class. After all, the code should generate a lambda expression, in method reference format, for the getWordLengthFunction method:

public Function getWordLengthFunction(){

return StringService::wordLength;

}

Generate new Java abstract class

The plugin program generates a new abstract Java class named AbstractEntity.java :

new ByteBuddy()

.subclass(Object.class)

.modifiers(

Opcodes.ACC_PUBLIC | Opcodes.ACC_ABSTRACT)

.name(“com.millionstrengthknowledge

.interceptorprj.entity.AbstractEntity”)

.defineMethod(“process”, void.class,

Visibility.PUBLIC)

.withoutCode()

.make()

.saveIn(dir);

The generation of abstract class requires the use of modifiers method. The modifiers method is used to add the public abstract Java class modifier to the Java class. With the code above, the instrumentation process should create the AbstractEntity.class completely:

public abstract class AbstractEntity{

public abstract void process();

}

237

![](Image00000.gif)

Instrumenting the User.class

At this stage, the plugin program has created one Java interface, EntityIntf.class, one Java enum DataEnum.class , one Java annotation EntityAnnotation , one Java class EntityUtil.class , and one abstract Java class AbstractEntity.class. The plugin program is going to instrument the User.class. This is the code for this purpose:

builder=builder

.annotateType(entityAnnotationVar)

.defineMethod(“getEntityUtil”, utilVar,

Visibility.PUBLIC)

.intercept(StubMethod.INSTANCE);

The code uses annotateType method to add @EntityAnnotation to the User.class at class level. For this purpose, the parameter of annotateType method is passed with the entityAnnotationVar variable. Therefore this is the result of the instrumentation:

@EntityAnnotation(name=”User”,

description=”User table for storing user record”)

public class User{

//code is omitted

}

After that, the plugin program is going to use the newly created Java class EntityUtil.class to declare a new method for User.java . Before the plugin program can use the Java class of EntityUtil.class , this class is required to be loaded into JVM so that the plugin program can use the Java class. Currently, the EntityUtil.class is saved into disk.

Therefore, the plugin program loads the EntityUtil.lcass into JVM by using Class.forName method:

Class utilVar=

Class.forName(“com.millionstrengthknowledge

.interceptorprj.entity.EntityUtil”);

After that, the utilVar variable should contains the reference to the EntityUtil.class . The plugin program uses the utilVar variable to

238

![](Image00000.gif)

declare the getEntityUtil method in User.class :

Therefore, with this configuration, the getEntityUtil method can return an instance of EntityUtil.class .

However, at this stage, the getEntityUtil method returns null value only. The plugin program further enhances the method to return a concrete instance of EntityUtil.java using the visit method:

builder=builder.visit(

Advice.to(UtilInterceptor.class)

.on(ElementMatchers.named(“getEntityUtil”))

);

The visit method applies the advice code of UtilInterceptor.class :

public class UtilInterceptor {

@OnMethodExit

public static void methodEnd(

@Return(

typing=Assigner.Typing.DYNAMIC,

readOnly=false) Object returnData

) throws Exception{

Class p=

Class.forName(“com.millionstrengthknowledge

.interceptorprj.entity.EntityUtil”);

returnData=

p.getConstructor().newInstance();

}}

The UtilInterceptor.java uses Java reflection to instantiate the instance of EntityUtil.class , and passes the instance to the returnData parameter. The returnData represents the return value of the getEntityUtil method.

After all, the plugin program should completely instrument the User. java . This is the Java source code view of User.class after instrumentation process:

239

![](Image00000.gif)

@EntityAnnotation(name=”User”,

description=”User table for storing user

record”)

public class User{

public EntityUtil getEntityUtil()

throws Exception{

Object localObject = this;

localObject = null;

Class localClass = Class.forName(“

com.millionstrengthknowledge

.interceptorprj.entity.EntityUtil”);

localObject = (EntityUtil)localClass

.getConstructor(new Class[0])

.newInstance(new Object[0]);

return (EntityUtil)localObject;

}

}

The source code view is created based on the Java bytecode generated by the ByteBuddy. Observed that the generated code is different from the advice code. For example, there is localObject variable, getConstructor method is passed with one parameter. Although the generated code has some differences, the generated code works accordingly.

240

![](Image00000.gif)

Rebase the Java class

This chapter has introduced several methods that can create new Java element:

makeInterface

makeEnumeration

makeAnnotation

subclass

There is another method named rebase , which is the method of net. bytebuddy.ByteBuddy . The rebase method is used to modify the existing Java element. The rebase method is the default method used in the plugin program of the maven build process. That means whenever the instrumentation use ByteBuddy maven plugin to instrument the class, the maven build process uses the rebase method. It is similar to this line of code that instantiate the instance of ByteBuddy:

new ByteBuddy().rebase(typeDescription)

However, this line of code is encapsulated in the plugin program. The developer can configure the rebase via net.bytebuddy.build. EntryPoint.

In ChapterDefineInterface Eclipse project, there is Java class named PluginConfig.java in com.millionstrengthknowledge. interceptorprj.plugin package. The PluginConfig.java implements the net.bytebuddy.build.EntryPoint . The EntryPoint program starts before the maven build process. It can be used to configure the instrumentation process of the plugin program. This is the source code of the PluginConfig.java :

241

![](Image00000.gif)

public class PluginConfig implements EntryPoint {

@Override

public ByteBuddy byteBuddy(

ClassFileVersion c

) {

System.out.println(“PluginConfig EntryPoint

start”);

return new ByteBuddy().with(

ClassFileVersion.JAVA_V11);

}

@Override

public Builder<?> transform(

TypeDescription typeDescription,

ByteBuddy byteBuddy,

ClassFileLocator cf,

MethodNameTransformer mtd)

{

return byteBuddy

.rebase(typeDescription, cf, mtd);

}

}

In this chapter, the PluginConfig.java is implemented to demonstrate how the plugin program configures the ByteBuddy before the maven build process starts. EntryPoint derived class must implement these two methods: byteBuddy , and transform . The byteBuddy method is the method used to instantiate the instance of net.bytebuddy. ByteBuddy :

public ByteBuddy byteBuddy(ClassFileVersion c){

System.out.println(“PluginConfig EntryPoint

start”);

return new ByteBuddy().with(

ClassFileVersion.JAVA_V11);

}

242

![](Image00000.gif)

(1) Instantiate the instance of ByteBuddy

new ByteBuddy()

(2) Configure the instance of ByteBuddy

.with(ClassFileVersion.JAVA_V11)

The with method is used to configure the instance of ByteBuddy. In this example, the with parameter configures ByteBuddy to generate the Java class in Java 11 format. However, this is optional because the plugin always generate the Java class based on the version of JDK used by the maven build process.

This is the source code for the transform method:

@Override

public Builder<?> transform(

TypeDescription typeDescription,

ByteBuddy byteBuddy,

ClassFileLocator cf,

MethodNameTransformer mtd)

{

return byteBuddy

.rebase(typeDescription, cf, mtd);

}

The transform method is the place where the plugin program chooses the strategy for the instrumentation. In this example, the rebase method is used. However, please be noticed that even the plugin program does not implement the EntryPoint, the plugin program is defaulted to rebase method..

To apply the PluginConfig.java to the maven build process, adds the <entryPoint> element in the pom.xml :

<plugin>

<groupId>net.bytebuddy</groupId>

<artifactId>byte-buddy-maven-plugin

243

![](Image00000.gif)

</artifactId>

<version>${bytebuddy.version}</version>

<executions>

<execution>

<goals>

<goal>transform</goal>

</goals>

</execution>

</executions>

<configuration>

<initialization>

<entryPoint>com.millionstrengthknowledge. interceptorprj.plugin.PluginConfig</entryPoint>

</initialization>

<transformations>

<transformation>

<plugin>com.millionstrengthknowledge

.interceptorprj.plugin

.InterceptorPlugin

</plugin>

</transformation>

</transformations>

</configuration>

</plugin>

244

![](Image00000.gif)

Conclusion

This chapter explains:

How to create new Java Interface

How to create new Java enum

How to create new Java annotation

How to create new Java class

How to create new abstract Java class

How to instrument existing Java class using the newly generated Java element

The plugin uses the rebase method

245

![](Image00000.gif)

Chapter 20: Instrumenting JDK Core Class

This chapter explains on how to instrument the JDK (Java Development Kit) core class. This chapter is also an introduction to Java Instrumentation API with ByteBuddy. The source code of this chapter is included in the ChapterJdkInstrumentation Eclipse project.

This chapter uses Java Instrumentation API and ByteBuddy to instrument java.lang.String class. Different from all previous chapters, Java Instrumentation API does not requires ByteBuddy maven plugin . Instead, Java Instrumentation API uses agent .

Java uses classloader to load the Java class from disk to JVM (Java Virtual Machine). With Java instrumentation API implementation, the agent intercepts the Java class before the Java class is loaded into JVM. When the agent completes the interception, then the instrumented Java class is loaded into JVM.

The instrumentation agent intercepts the Java class during application runtime. The Java instrumentation API is suitable for these situations:

The instrumented Java class file cannot be saved : This is true for new JDK since version 9 because all the JDK core class are compressed into a special file format (not a jar file), which is not available for the build process to repackage the core library.

The application wants to generate code based on the condition that cannot be determined during compile time and build time, but only during runtime.

Therefore, the ByteBuddy maven plugin is not applicable. Instead, the application will use agent to instrument the JDK core class during application runtime. The agent is the Java component that has instrumentation capability, and the capability is implemented in a transformer . So the agent can have multiple transformer. Example of agent are monitoring agent, profiler agent, program tracing agent. The agent must implement the premain method.

246

![](Image00000.gif)

When the JVM starts, the JVM will invokes the premain method of the agent, and then JVM invokes the main method of the application to start the application. When there are multiple agents, the premain method of each agent is invoked in sequence order, and then the main method of the application.

During the application runtime, the classloader will keep on loading new Java class into JVM. Whenever the classloader loads the new class into JVM, the agent will intercept the new class. The agent then invokes each of its transformer to instrument the new class. After the instrumentation process completes, then the new class with advice code will be loaded into JVM.

The InterceptorAgent.java in this chapter is the agent Java class:

public class InterceptorAgent {

public static void premain(String arguments,

Instrumentation inst) {

ByteBuddyAgent.install();

new AgentBuilder.Default()

.with(AgentBuilder.RedefinitionStrategy

.REDEFINITION)

.with(AgentBuilder.Listener

.StreamWriting.toSystemOut())

.ignore(ElementMatchers.none())

.type(ElementMatchers.named(

“java.lang.String”))

.transform(

(builder, typeDescription,

classLoader, module) -> {

return builder.visit(

Advice.to(LogInterceptor.class)

.on(

ElementMatchers.named(

“toUpperCase”).and(

ElementMatchers.isMethod()).and(

ElementMatchers.takesNoArguments()

)));}).installOnByteBuddyAgent();

}}

247

![](Image00000.gif)

InterceptorAgent

This is the method signature of the premain method:

public static void premain(

String arguments, Instrumentation inst)

The method takes two parameters:

The String parameter is the placeholder parameter that allows developer to pass miscellaneous data to the agent.

The second parameter is type of java.lang.instrument. Instrumentation . The JVM provides the instance of instrumentation during application runtime. This parameter provides services needed to instrument the Java class file. The agent can add transformer via addTransformer method of this instance.

The first line of the method body is:

ByteBuddyAgent.install();

The ByteBuddyAgent is the Java class from net.bytebuddy. agent package, which is available from byte-buddy-agent maven dependency. The install method installs the ByteBuddy built-in agent in the JVM. The agent is required for instrumenting the loaded Java class in the JVM.

Next, the program instantiates an instance of AgentBuilder . The AgentBuilder is a public static class in net.bytebuddy.agent.builder package. The AgentBuilder.Default is used to instantiate a new instance of the AgentBuilder with default configuration. Default configuration uses rebase strategy, and the agent will not instrument the JDK core class. The program uses with method to configure the AgentBuilder. RedefinitionStrategy.REDEFINITION strategy:

.with(AgentBuilder.RedefinitionStrategy

.REDEFINITION)

With redefinition strategy, the agent can instrument the Java class that is already loaded, and not yet loaded into JVM. For Java class that is already loaded into JVM, the agent will instrument the class when the premain method is invoked. For Java class that is not yet loaded

248

![](Image00000.gif)

into JVM, the agent will instrument the class when the classloader is loading the class.

Next, the program configures agent to enable the agent process logging:

.with(AgentBuilder.Listener.StreamWriting

.toSystemOut())

This line enables the logging of the ByteBuddy instrumentation process to console.

Next, the program configures new transformer to instrument the JDK core class:

.ignore(ElementMatchers.none())

Without this configuration, the new transformer will ignore the JDK core class for instrumentation because the instance of AgentBuilder that is instantiated via AgentBuilder.Default method disable it by default. That means the JDK core class will be skipped for instrumentation process. Since the agent wants to instrument java.lang.String , so the new transformer should not ignore the JDK core class. The ignore method is used to configure this behavior, and the ElementMatchers. none method informs the new transformer that none of the JDK core class should be ignored.

Next, the program specifies the matching logic for the target class:

.type(ElementMatchers.named(“java.lang.String”))

This is similar to the matches method in the plugin program. The AgentBuilder uses type method to configure the matching logic for the new transformer. In this example, the ElementMatchers.named method is used to match java.lang.String .

249

![](Image00000.gif)

After that, the program invokes transform method:

.transform(

builder, typeDescription, classLoader, module)

-> {

return builder.visit(

Advice.to(LogInterceptor.class)

.on(

ElementMatchers.named(“toUpperCase”).and(

ElementMatchers.isMethod()).and(

ElementMatchers.takesNoArguments()

)

));

})

The transform method of AgentBuilder is used to add the instrumentation capability to the new transformer. It is similar to the apply method in the plugin program. The transform method accepts one parameter, which is type of net.bytebuddy.agent.builder. AgentBuilder.Transformer .

In this example, the program implements the transformer using the lambda expression. The AgentBuilder.Transformer has one method, which has this method signature:

DynamicType.Builder<?> transform(

DynamicType.Builder<?> builder,

TypeDescription typeDescription,

ClassLoader classLoader, JavaModule module)

This transform method of AgentBuilder.Transformer is the method that will be invoked by agent to instrument the Java class file in premain method, and before the Java class file is loaded into JVM.

250

![](Image00000.gif)

The program will use the first parameter, builder , to configure the advice code:

builder.visit(

Advice.to(LogInterceptor.class)

.on(

ElementMatchers.named(“toUpperCase”).and(

ElementMatchers.isMethod()).and(

ElementMatchers.takesNoArguments()

)));

The builder uses visit method to configure the Advice. The transformer will apply the advice code of LogInterceptor.class when the application invokes toUpperCase method of java.lang.String .

After all, the program chains the method to installOnByteBuddyAgent method. This method installs the transformer in the ByteBuddyAgent.

.installOnByteBuddyAgent();

Premain-Class attribute in MANIFEST.MF

In order to activate the agent, the application must create a jar file that package the agent Java class file, and one MANIFEST.MF. The manifest file must have one Premain-Class attribute. The value of this attribute is the fully qualified class name of the agent. Therefore, the application creates the MANIFEST.MF file in resources folder of ChapterJdkInstrumentation Eclipse project, and this is the content of the file:

Premain-Class: com.millionstrengthknowledge

.interceptorprj.interceptor.InterceptorAgent

Maven pom.xml

The plugin program is not applicable when the program uses Java Instrumentation API. The program will use the maven to create the agent jar file. Instead of using byte-buddy-maven-plugin, the pom.xml configures the maven-jar-plugin:

251

![](Image00000.gif)

<plugin>

<groupId>org.apache.maven.plugins</groupId>

<artifactId>maven-jar-plugin</artifactId>

<version>3.2.0</version>

<executions>

<execution>

<id>agent</id>

<goals>

<goal>jar</goal>

</goals>

<configuration>

<classifier>agent</classifier>

<includes>

<include>**/interceptor/**</include>

</includes>

<archive>

<manifestFile>src/main/resources/

META-INF/MANIFEST.MF</manifestFile>

</archive>

</configuration>

</execution>

</executions>

</plugin>

By default, maven-jar-plugin will create a jar file that includes all the Java class files in the Eclipse project. The application needs to package another jar file just for agent related Java class file only. Therefore, in this chapter, the pom.xml creates a new <execution> tag for the agent jar file. The configuration has the <id> tag of value of agent . Because the jar file is created for agent only, so the jar will only package the Java class file from com.millionstrengthknowledge.interceptorprj. interceptor package, which is specified via the <include> tag. Besides that, the plugin needs to specify the file location of MANIFEST.MF so that the build process will package the manifest file that contains the Premain-Class attribute. The pom.xml uses <manifestFile> tag for this purpose.

252

![](Image00000.gif)

Execute the program in Eclipse

To view the result of the instrumentation process, first executes the maven build process:

(1) Right click on pom.xml in the project/package explorer in Eclipse.

(2) Select Run As -> Maven build

(3) Eclipse should show the “ Edit configuration ”, enters clean package -X in the Goals textbox:

(4) Click the Run button. After this, the maven build process will start.

After the maven build process completes, executes the InterceptorProgram.java :

(1) Right click on InterceptorProgram.java in project/package explorer in Eclipse.

(2) Select Run as -> Java Application

(3) Eclipse will show “Run configurations”.

![](Image00054.jpg)

253

![](Image00000.gif)

(4) Select the Arguments tab, in the VM arguments textbox, enters this value: --add-reads java.base=java.logging -javaagent:C:/Users/ user001/workspace/Interceptor/ChapterJdkInstrumentation/ target/ChapterJdkInstrumentation-1.0-agent.jar . There are two VM arguments:

-add-reads java.base=java.logging

This is required because java.base and java.logging are in different module and the LogInterceptor.java requires the java.logging module, so this parameter is configured for this purpose.

-javaagent:C:/Users/user01/workspace/ Interceptor/ChapterJdkInstrumentation/target/ ChapterJdkInstrumentation-1.0-agent.jar

-javaagent parameter specifies the file location of the agent jar. This jar file is generated by the maven build process configured in Maven pom.xml file section of this chapter. Changes the file path so that it points to the right agent jar.

(4) After that, press the Run button to executes the program. This is the source code of InterceptoProgram.java :

![](Image00055.jpg)

254

![](Image00000.gif)

public static void main(String args[]){

String data=new String(“testTEST”);

data.toUpperCase();

}

The program creates a data String variable, and then invokes the toUpperCase method on that variable. The program output is expected to have the advice code prints the log from the on method enter and exit advice of toUpperCase method. The Eclipse console should show this result:

ByteBuddyAgent generates the trace of the instrumentation process. The trace is enabled by this configuration in the InterceptorAgent. java :

.with(AgentBuilder.Listener.StreamWriting.

toSystemOut())

![](Image00056.jpg)

255

![](Image00000.gif)

Checks the trace, the trace should include the log created by the advice code in the toUpperCase method of the java.lang.String, which is in red color:

Jan 01, 2020 1:00:00PM java.lang.String toUpperCase INFO: Method Enter: public java. lang.String java.lang.String.toUpperCase()

Jan 01, 2020 1:00:00PM java.lang.String toUpperCase INFO: Method Exit: public java.lang. String java.lang.String.toUpperCase() return: ‘TESTTEST’

This means the InterceptorAgent.java has successfully instrument the java.lang.String.

However, please be noticed that the JVM does not allow agent to add or delete method, constructor and instance variable to the JDK core class. Therefore, executing the defineMethod , defineField and defineConstructor method on JDK core class has no effect during the instrumentation process.

Conclusion

This chapter explains on how to add on method enter and exit advice to the JDK core class.

256

![](Image00000.gif)![](Image00057.jpg)