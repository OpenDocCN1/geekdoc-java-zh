![](image_rsrcFPP.jpg)

SPRING

FRAMEWORK                                                                                     

In This Book You Will Learn Explanation with Diagram and

Working Exercises with Successful Execution of Exercise with Output

Readymade Solution with Step By Step Explanation      

AMIT K

Contents

Beginners Guide to Learn Spring Framework Step by Step

Introduction

Chapter 1 : Introduction

1  Spring ( Build Path )

Chapter 2 : Introduction

1  Lab -  1 - HelloWorld - XML

Chapter 3 :  Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab -  2 - Setter Injection - XML

2  Lab -  3 - Constructor Injection - XML

Chapter 4 : Spring Beans Inner Bean Inject

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab -  4 - Inner Bean  ref attribute – XML

2  Lab -  5 - Inner Bean  Nest Bean - XML

3  Lab -  6 - Inner Bean  Constructor – XML 

Chapter 5 : Spring Beans Bean Scope

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab -  7 - Bean Scope  Singleton Scope – XML

2  Lab -  8 - Bean Scope  Prototype Scope – XML

3  Lab -  9 - Bean Scope                  - Annotation    

Chapter 6 : Spring Beans Properties ( Collection Of Objects )

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )  

1  Lab - 10 - Beans Properties  List Properties - XML

2  Lab - 11 - Beans Properties  ListFactoryBean - XML

3  Lab - 12 - Beans Properties  Util List - XML

4  Lab - 13 - Beans Properties  Set Properties - XML

5  Lab - 14 - Beans Properties  Set Util - XML

6  Lab - 15 - Beans Properties  Map Properties - XML

7  Lab - 16 - Beans Properties  MapFactoryBean - XML

8  Lab - 17 - Beans Properties  Map Util – XML

Chapter 7 : Spring Beans Advanced

1  Lab - 19 - Beans Bean Inheritance - XML

2  Lab - 20 - Beans Override - XML

3  Lab - 21 - Beans Initialize and Destroy - XML

4  Lab - 22 - Beans Spring init Method - XML

Chapter 8 : Spring Beans Properties ( Autowire )

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab - 23 - Beans Autowire Auto Scan Not Autowired - XML

2  Lab - 24 - Beans Autowire Auto Scan Autowired - XML

3  Lab - 25 - Beans Autowire Spring Autowire - XML

4  Lab - 26 - Beans Autowire Spring Autowire Setter - XML

Chapter 9 : Spring Expression Language

1  Lab - 27 - Spring Expression Language            - XML

2  Lab - 28 - Spring Expression Language    - Annotation

Chapter 10 : Spring Aspect Oriented Programming ( AOP )

1  Lab - 29 - Spring AOP Pre AOP - XML

2  Lab - 30 - Spring AOP Around AOP - XML

Introduction

Learning Spring Framework step by step.

| ![](image_rsrcFPR.jpg) |

JPA

JAVA PERSISTENCE

FOR BEGINNERS

In This Book You Will Learn Explanation with Diagramme and

Working Exercises with Successfull Execution of Exercises with Output

Readymade Solution With Step By Step Explanation

AMIT K

Contents

Beginners Guide to Learn JPA Programming Step by Step

Introduction

Chapter 1 : JPA One to One Mapping

1  Example 1 : JPA OneToOne Mapping

2  Example 2 : JPA OneToOne Lazy Load Mapping

3  Example 3 : JPA OneToOne Join Column Mapping

4  Example 4 : JPA OneToOne Primary Key Join Column Mapping

5  Example 5 : JPA OneToOne Map Cascade Mapping

6  Example 6 : JPA OneToOne Unidirectional Mapping

7  Example 7 : JPA OneToOne Bidirectional Mapping

Chapter 2 : JPA One to Many Mapping

1  Example 8 : JPA OneToMany Mapping

2  Example 9 : JPA OneToMany Join Table Mapping

3  Example 10: JPA OneToMany Unidirectional Mapping

4  Example 11: JPA OneToMany OrderBy Mapping

5  Example 12: JPA Persist OrderedList Mapping

6  Example 13: JPA OneToMany Map Key Mapping

7  Example 14: JPA OneToMany Untyped Mapping

Chapter 3 : JPA Many to One Mapping

1  Example 15: JPA ManyToOne Mapping

2  Example 16: JPA ManyToOne Join Columns Mapping

3  Example 17: JPA ManyToOne Join Column Mapping

Chapter 4 : JPA Many to Many Mapping

1  Example 18: JPA ManyToMany Mapping

2  Example 19: JPA ManyToMany Join Table Mapping

3  Example 20: JPA ManyToMany Bidirectional Mapping

4  Example 21: JPA ManyToMany Embeddable Mapping

Introduction

Learning JPA Programming step by step.

JPA ( Java Persistence API ) is a powerful framework that can be used to quickly build robust data-driven application.

Most of the data that our applications manipulate have to be stored in data stores, retrieved, processed and analyzed. If this data store is a relational database and you use an object-oriented programming language such as Java, then you should have a look at JPA.

JPA is an Object-Relational Mapping tool that maps Java objects to relational databases and allows query operations.

In this book, you will learn Java Persistence API, its annotations for mapping entities.

JPA Integration  with spring frameworks.

| ![](image_rsrcFPS.jpg) |

JAVA

SPRING

HIBERNATE

In This Book You Will Learn Developing Java Web Application Using Spring Hibernate From Scratch

Readymade Solution With Step By Step Explanation

AMIT K

Introduction

Learning how to Develope Java Web Application Using Spring Hibernate From Scratch.

Here you will learn

When User Will Submit Request Through ( Browser )

Action will Take the Request , Proceed , Contact to Database.

Service Interface ( Having Method ) , What to Do TO Tables

CURD Operation ( Create , Update , Read , Delete ).

Implementaion of Service Interface ( Method )

Having Dependent ( Persitent Object Information ).

DAO Interface ( Methods ) , How to Communicate TO Tables

For CURD Operation ( Create , Update , Read , Delete ).

Responsible For Communicating TO Tables

POJO ( Simple Java Object )

All Request Data Comming From ( Browser )

All Result Data From ( Tables ) To ( Browser ).

MVC ( Model View Controller ) Architecture

For View ( To Display Result Data To Browser )

Result Data Comming From ( Tables )

After Contacting To Database

Front Controller Will Take the

Appropriate ( JSP Page )

And Put the Data Into ( JSP Page )

And Send Back ( JSP Page ) To Browser

Browser will Display .

Hospital System ( Working Flow )

Step 1 :

Patient   →   Required Doctor   →   Appointment

Step 2 :

Doctor → Doctor see Appointment → Treatment

Step 3 :

Patient  →  See Treatment

Step 4 :

Doctor   →  Doctor update start end Treatment

Step 5 :

Patient  →  See Treatment Status

Design Document of Hospital System

1 .  Hospital Out-Patient Referral System Features

1 .  Overall Function of the System

*   Operator of the Permissions Level, with clear classification, when the System is to be Authenticated.
*   The Patient privacy of the Individual is Responsible for the Patient's Medical Records can only be the Patient during treatment by the Doctor, other anyone, including Administrator is not authorized to access.

2 .  Patient's Role

*   To Register as a User, set to your Login Name and Password
*   The names of the Doctors a custom query.
*   Based on Results of the Query to make a Reservation, if you specify the day Doctor’s Appointment volume is full, the Reservation Failed. Result random returns to the Patient.
*   You can have an Appointment, view or undo
*   Make an Appointment, you can query the Doctor Information, Medical Information.

3 .  Doctor Role

*   You can view the Reservation the context of the Patient.
*   You can query for Patient Records.
*   You can create Patient Records.
*   The Patient's Medical Record to be Modified.

4 .  Administrator Role.

*   You can Add and Delete Doctors Account.

2 .  Design Process

From the demand analysis, separation of the entities

Major entities:

*   Doctor (doctor)
*   Patient (patient)
*   Medical Record (history)
*   Reservation records (pinqueue)
*   Administrator (administrator)
*   Doctors can be a maximum number of Appointments (appointment)
*   Doctors currently available number of Appointments (currappointment)

Home

| ![](image_rsrcFPT.jpg) |

Environment

| Technologies | Struts1 , Spring , Hibernate , Javascript , Css , Jquery |
| Database | MySQL |
| Server | Tomcat 1.6 |
| Logging Tool | Log4j |
| IDE | Eclipse |
| Design  Patterns | Front Controller ,  MVC  , Factory,  DAO  , Proxy , Singleton, Abstract factory pattern, Template pattern, SessionFactory, TransactionFactory. |

Directory Structure

| ![](image_rsrcFPU.jpg) |

Directory Structure ( Expanded )

| ![](image_rsrcFPV.jpg) |

| ![](image_rsrcFPW.jpg) |

| ![](image_rsrcFPX.jpg) |

| ![](image_rsrcFPY.jpg) |

SPRING

FRAMEWORK                                                                                     

In This Book You Will Learn Explanation with Diagram and

Working Exercises with Successful Execution of Exercise with Output

Readymade Solution with Step By Step Explanation      

AMIT K

Contents

Beginners Guide to Learn Spring Framework Step by Step

Introduction

Chapter 1 : Introduction

1  Spring ( Build Path )

Chapter 2 : Introduction

1  Lab -  1 - HelloWorld - XML

Chapter 3 :  Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab -  2 - Setter Injection - XML

2  Lab -  3 - Constructor Injection - XML

Chapter 4 : Spring Beans Inner Bean Inject

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab -  4 - Inner Bean  ref attribute – XML

2  Lab -  5 - Inner Bean  Nest Bean - XML

3  Lab -  6 - Inner Bean  Constructor – XML 

Chapter 5 : Spring Beans Bean Scope

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab -  7 - Bean Scope  Singleton Scope – XML

2  Lab -  8 - Bean Scope  Prototype Scope – XML

3  Lab -  9 - Bean Scope                  - Annotation    

Chapter 6 : Spring Beans Properties ( Collection Of Objects )

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )  

1  Lab - 10 - Beans Properties  List Properties - XML

2  Lab - 11 - Beans Properties  ListFactoryBean - XML

3  Lab - 12 - Beans Properties  Util List - XML

4  Lab - 13 - Beans Properties  Set Properties - XML

5  Lab - 14 - Beans Properties  Set Util - XML

6  Lab - 15 - Beans Properties  Map Properties - XML

7  Lab - 16 - Beans Properties  MapFactoryBean - XML

8  Lab - 17 - Beans Properties  Map Util – XML

Chapter 7 : Spring Beans Advanced

1  Lab - 19 - Beans Bean Inheritance - XML

2  Lab - 20 - Beans Override - XML

3  Lab - 21 - Beans Initialize and Destroy - XML

4  Lab - 22 - Beans Spring init Method - XML

Chapter 8 : Spring Beans Properties ( Autowire )

Injection ( Injecting Dependent Object Into

Calling Object( Parent Object ) )

1  Lab - 23 - Beans Autowire Auto Scan Not Autowired - XML

2  Lab - 24 - Beans Autowire Auto Scan Autowired - XML

3  Lab - 25 - Beans Autowire Spring Autowire - XML

4  Lab - 26 - Beans Autowire Spring Autowire Setter - XML

Chapter 9 : Spring Expression Language

1  Lab - 27 - Spring Expression Language            - XML

2  Lab - 28 - Spring Expression Language    - Annotation

Chapter 10 : Spring Aspect Oriented Programming ( AOP )

1  Lab - 29 - Spring AOP Pre AOP - XML

2  Lab - 30 - Spring AOP Around AOP - XML

Introduction

Learning Spring Framework step by step.

| ![](image_rsrcFPR.jpg) |

Chapter 1 :

Introduction

First           →      We will see some concepts

Second      →      We will see detailed explanation

Spring ( Build Path )

Step 1 :

| ![](image_rsrcFPZ.jpg) |

Step 2 :

| ![](image_rsrcFR0.jpg) |

Step 3 :

| ![](image_rsrcFR1.jpg) |

Step 4 :

| ![](image_rsrcFR2.jpg) |

Step 5 :

| ![](image_rsrcFR3.jpg) |

Step 6 :

| ![](image_rsrcFR4.jpg) |

Chapter 2 :

Introduction

Lab -  1 - HelloWorld – XML

Introduction

Spring Framework  →    Easy   Readymade Solution

→    Where ever complication occour

→    Spring provides  Readymade Objects

→    Ready to Use

→    Client will only take this

→    Readymade Objects

→    And Use It

Spring Framework  →    Spring provides Spring Container

→    Spring Container is Responsible for

→    Loading the class

→    Creating Instance of class

→    Intiallizing the Resources

→    Injecting the dependent Resource in

→    Calling ( Parent ) Object

→    Spring Container will be

→    Ready with Readymade Objects

→    Ready to Use

Client                         →    Spring Container (Readymade Objects)

Client  will take        →    Spring Container

The Objects and      →    Spring Container

Use It                         →    Spring Container

All Labs :

| ![](image_rsrcFPR.jpg) |

Lab -  1 - HelloWorld – XML

Lab -  1 - HelloWorld – XML :

| ![](image_rsrcFR5.jpg) |

HelloWorld.java

| package com.abd.spring3;public  class HelloWorld {​private String name;​public  void setName(String name) {​this.name = name;​}​public  void printHello() {​System.out.println(" Hello ! " + name);​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">​<bean  id="helloBean"  class="com.abd.spring3.HelloWorld">​<property  name="name"  value="Welcome"  />​</bean></beans> |

| ![](image_rsrcFR6.jpg) |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main(String[] args) {ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");HelloWorld obj = (HelloWorld) context.getBean("helloBean");obj.printHello();}} |

Request Flow   →   Of   Client     what will     Happen

→   What   will    Client    Do

→   What   are     the  Steps   will   Happen

→   While    Client   Processing

→   You   will   Learn

→   Detailed    Step   by   Step  Explanation

Client.java

| Step 1 :![](image_rsrcFR7.jpg) |

| Step 2 :![](image_rsrcFR8.jpg) |

| Step 3 :![](image_rsrcFR9.jpg) |

| Step 4 :![](image_rsrcFRA.jpg) |

| Step 5 :![](image_rsrcFRB.jpg) |

| Step 6 :![](image_rsrcFRC.jpg) |

| Step 7 :![](image_rsrcFRD.jpg) |

| Step 8 :![](image_rsrcFRE.jpg) |

| Step 9 :![](image_rsrcFRF.jpg) |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main(String[] args) {ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");HelloWorld obj = (HelloWorld) context.getBean("helloBean");obj.printHello();}} |

Output

| ![](image_rsrcFRG.jpg) |

Note :

1    In This     Lab -  1 - HelloWorld - XML

2    Complete  Request Flow Explained   Step by Step in Detail

3    In All Labs these Request Flow will Occur

4    So Please remember these concepts

5    Remaining Labs We will do in fast

Chapter 3 :

Injection ( Injecting Dependent Object Into Calling

Object( Parent Object ) )

Lab -  2 - Setter Injection – XML

Lab -  3 - Constructor Injection - XML

Spring  Framework Provide Loosely Coupled Architecture.

There are Two Types of Coupled Architecture.

Tightly    Coupled Architecture

You are forced to call particular dependent Object.

Loosely    Coupled Architecture

You are free to use any dependent object according to your requirement to call particular dependent Object.

Note : In comming Labs We will see how to achieve   Loosely 

Coupled Architecture

Spring Container   →    Spring Container is Responsible for

To    Do  the task for us ( Developer )   

→    Developer   is   Giving  Instruction to

Spring Container  What   to   do  

How   to   do     

→    Developer   is   Giving  Instruction to

Spring Container    Through  

( .xml )  Files

( .xml )  Files    can   be

ApplicationContext.xml      OR

SpringBeans.xml

→    In  ( .xml )  File  ,  Developer configured

Instruction ,  In what Way

Spring Container   Inject  the

Dependent Object   in  

Calling  Object ( Parent )  Through

(Setter ,Constructor  or  Any other way)   

Lab -  2 - Setter Injection – XML

Spring Container   →   Will Inject Dependent Object   Through     

Setter() Method   of  Java Class

| ![](image_rsrcFRH.jpg) |

In this Lab   ,  We will Try to  Achieve

Loosely    Coupled Architecture   Through  Interface

How to Achieve Please see

The   Request Flow   in    Detail

Printer.java

| package com.abd.spring3;public  interface Printer{​public  void print();} |

CSVPrinter.java

| package com.abd.spring3;public  class CSVPrinter implements Printer{​public  void print(){​System.out.println("Csv Output Printer");​}} |

JSONPrinter.java

| package com.abd.spring3;public  class JSONPrinter implements Printer{​public  void print(){​System.out.println("Json Output Printer");​}} |

OutputHelper.java

| package com.abd.spring3;public  class OutputHelper{​Printer outputGenerator;​public  void print(){​outputGenerator.print();​}​public  void setOutputGenerator(Printer outputGenerator){​this.outputGenerator = outputGenerator;​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://www.springframework.org/schema/beanshttp://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="outputHelper"  class="com.abd.spring3.OutputHelper"><property  name="outputGenerator"  ref="csvPrinter"  /></bean><bean  id="csvPrinter"  class="com.abd.spring3.CSVPrinter"  /><bean  id="jsonPrinter"  class="com.abd.spring3.JSONPrinter"  /></beans> |

Complete    Request   Flow    of  Client      (  Client.java  )

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {​public  static  void main(String[] args) {​ApplicationContext context = new ClassPathXmlApplicationContext(​"SpringBeans.xml");​OutputHelper output = (OutputHelper)context.getBean("outputHelper");​output.print();​}} |

| ![](image_rsrcFRJ.jpg) |

| ![](image_rsrcFRK.jpg) |

| ![](image_rsrcFRM.jpg) |

| ![](image_rsrcFRN.jpg) |

| ![](image_rsrcFRP.jpg) |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main(String[] args) {​ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");​OutputHelper output =(OutputHelper)context.getBean("outputHelper");​output.print();}} |

Output

| ![](image_rsrcFRR.jpg) |

Lab -  3 - Constructor Injection - XML

Spring Container  →     Will Inject Dependent Object   Through 

Constructor()       of  Java Class  

| ![](image_rsrcFRS.jpg) |

Printer.java

| package com.abd.spring3;public  interface Printer{​public  void print();} |

CSVPrinter.java

| package com.abd.spring3;public  class CSVPrinter implements Printer{​public  void print(){​System.out.println("Csv Output Printer");​}} |

JSONPrinter.java

| package com.abd.spring3;public  class JSONPrinter implements Printer{​public  void print(){​System.out.println("Json Output Printer");​}} |

OutputHelper.java

| package com.abd.spring3;public  class OutputHelper{​Printer outputGenerator;​public OutputHelper(){​}public OutputHelper(Printer p){​this.outputGenerator = p;​}public  void print(){​outputGenerator.print();}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://www.springframework.org/schema/beanshttp://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="outputHelper"  class="com.abd.spring3.OutputHelper"><constructor-arg>​  <bean  class="com.abd.spring3.CSVPrinter"  /></constructor-arg></bean><bean  id="csvPrinter"  class="com.abd.spring3.CSVPrinter"  /><bean  id="jsonPrinter"  class="com.abd.spring3.JSONPrinter"  /></beans> |

Complete Request Processing Flow

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main(String[] args) {ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");OutputHelper output =(OutputHelper)context.getBean("outputHelper");output.print();}} |

| ![](image_rsrcFRT.jpg) |

| ![](image_rsrcFRU.jpg) |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main(String[] args) {ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");OutputHelper output =(OutputHelper)context.getBean("outputHelper");output.print();}} |

Output

| ![](image_rsrcFRV.jpg) |

Chapter 4 :

Spring Beans Inner Bean Inject

Injection ( Injecting Dependent Object Into Calling

Object( Parent Object ) )

Lab -  4 - Inner Bean  ref attribute – XML

Lab -  5 - Inner Bean  Nest Bean - XML

Lab -  6 - Inner Bean  Constructor – XML

Lab -  4 - Inner Bean  ref attribute – XML

Customer.java( Parent Object )   ☐   Person.java ( Dependent Object )

☐   ref attribute( Means              )

☐   Through    ( Setter Injection )           

☐   After Seeing  ref attribute

☐   Understand

☐   Injection Will Happen

☐   Through    ( Setter Injection )           

We will see in detail in following Labs

| ![](image_rsrcFRW.jpg) |

Customer.java

| package com.abd.spring3;public  class Customer{​private Person person;​public Customer() {​}​public Customer(Person person) {​this.person = person;​}​public  void setPerson(Person person) {​this.person = person;​}​@Override​public String toString() {​return  "Customer [person=" + person + "]";​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private String address;​private  int  age;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​@Override​public String toString() {​return  "Person [Address=" + address + ",Age=" +age + ", Name=" + name + "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="CustomerBean"  class="com.abd.spring3.Customer">              <property  name="person"  ref="PersonBean"  /></bean><bean  id="PersonBean"  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="28"  /></bean></beans> |

Complete Client Request Processing Flow

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ){ApplicationContext context =new ClassPathXmlApplicationContext(new String[]{"SpringBeans.xml"});Customer cust(Customer)context.getBean("CustomerBean");System.out.println(cust);}} |

| ![](image_rsrcFRX.jpg) |

| ![](image_rsrcFRY.jpg) |

| ![](image_rsrcFRZ.jpg) |

| ![](image_rsrcFS0.jpg) |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ){ApplicationContext context =new ClassPathXmlApplicationContext(new String[]{"SpringBeans.xml"});Customer cust(Customer)context.getBean("CustomerBean");System.out.println(cust);}} |

Output

| ![](image_rsrcFS1.jpg) |

Lab -  5 - Inner Bean  Nest Bean – XML

| ![](image_rsrcFS2.jpg) |

Customer.java

| package com.abd.spring3;public  class Customer {​private Person person;​public Customer() {​}​public Customer(Person person) {​this.person = person;​}​public  void setPerson(Person person) {​this.person = person;​}​@Override​public String toString() {​return  "Customer [person=" + person + "]";​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private String address;​private  int  age;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​@Override​public String toString() {​return  "Person [address=" + address + ",age=" + age + ", name=" + name + "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<property  name="person">​  <bean  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="28"  /></bean>​</property></bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ){​ApplicationContext context =​  new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFS3.jpg) |

Lab -  6 - Inner Bean  Constructor – XML

| ![](image_rsrcFS4.jpg) |

Customer.java

| package com.abd.spring3;public  class Customer {​private Person person;​public Customer() {​}​public Customer(Person person) {​this.person = person;​}​public  void setPerson(Person person) {​this.person = person;​}​@Override​public String toString() {​return  "Customer [person=" + person + "]";​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private String address;​private  int  age;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​@Override​public String toString() {​return  "Person [address=" + address + ",age=" + age + ", name=" + name + "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<constructor-arg>​  <bean  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="28"  />​  </bean>​</constructor-arg></bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ){​ApplicationContext context =​  new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFS5.jpg) |

Chapter 5 :

Spring Beans Bean Scope

Injection ( Injecting Dependent Object Into Calling

Object( Parent Object ) )

Lab -  7 - Bean Scope  Singleton Scope – XML

Lab -  8 - Bean Scope  Prototype Scope – XML

Lab -  9 - Bean Scope                  - Annotation

When  A  Bean  is  Marked  as   Singleton     OR     Prototype

What  It  Means

Spring  Container   ☐   Instruction  to  Spring Container

☐   That  Special  Handling Required

☐   For This Bean

☐   We will see the concepts in Detail

Scope = “ Singleton ”  →     When  A Bean  is  Marked  as

→     Scope = “ Singleton ”  

→     Spring Container Will

→     Create only One Instance

→     At  Spring Container Startup Time

→     Each time for

→     Every  Incoming Request

→     only One Instance

→     only One Instance will be supplied

→     To  Every  Incoming Request

→     And fulfill the Request

→     Will Destroyed that Instance , When

→     Spring Container Will be Destroyed

Scope = “ Prototype”  →     When  A Bean  is  Marked  as

→     Scope = “ Prototype”  

→     Spring Container Will

→     Will NOT Create Instance of the Bean

→     At  Spring Container Startup Time

→     Each time for

→     Every  Incoming Request

→     New Instance Will be  Created

→     And  Supplied  to the  Client

→     After  Fullfilling  the  Request

→     Bean Instance  Will  be  Destroyed

→     When Client Send the Request For

→     Bean  That  Time Only

→     Bean Instance  Will  be  Created

→     And  Fullfill  the  Request

→     After  Fullfilling the

→     Incomming  Request

→     Bean Instance will be Destroyed

→     Every Time A Client Send Request

→     That Time Only

→     A New Instance Will be Created

→     And  Supplied

Complete Client Request Processing Flow

Lab -  7 - Bean Scope  Singleton Scope – XML

| ![](image_rsrcFS6.jpg) |

MyService.java

| package com.abd.spring3;public  class MyService {​String message;​public String getMessage() {​return  message;​}​public  void setMessage(String message) {​this.message = message;​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="customerService"  class="com.abd.spring3.MyService"  /></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){ApplicationContext context =new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});MyService customerA = (MyService)context.getBean("customerService");customerA.setMessage("Message by customerA");System.out.println("Message : " + customerA.getMessage());// CustomerB Retrieving That Instance Which is Already Created// Because This Bean is "Singleton"// If Any Bean , Is Not Marked As  "Singleton"  OR  "Prototype"// Spring Container Will Assume The Bean as , "Singleton"MyService customerB = (MyService)context.getBean("customerService");System.out.println("Message : " + customerB.getMessage());}} |

| ![](image_rsrcFS7.jpg) |

| ![](image_rsrcFS8.jpg) |

Lab -  8 - Bean Scope  Prototype Scope – XML

| ![](image_rsrcFS9.jpg) |

MyService.java

| package com.abd.spring3;public  class MyService {​String message;​public String getMessage() {​return  message;​}​public  void setMessage(String message) {​this.message = message;​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="customerService"  class="com.abd.spring3.MyService"scope="prototype"/></beans> |

Complete Client Processing Flow

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ){​ApplicationContext context =new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​MyService customerA = (MyService)context.getBean("customerService");​customerA.setMessage("Message by customerA");​System.out.println("Message : " + customerA.getMessage());​// Retrieving "customerService" , But Not Putting Any Message​// setMessage() Method of MyService Class​MyService custB = (MyService)context.getBean("customerService");​System.out.println("Message : " + custB.getMessage());}} |

| ![](image_rsrcFSA.jpg) |

Lab -  9 - Bean Scope                  - Annotation

| ![](image_rsrcFSB.jpg) |

MyService.java

| package com.abd.spring3;import org.springframework.context.annotation.Scope;import org.springframework.stereotype.Service;@Service@Scope("prototype")public  class MyService {​String message;​public String getMessage() {​return  message;​}​public  void setMessage(String message) {​this.message = message;​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:context="http://www.springframework.org/schema/context"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/context​http://www.springframework.org/schema/context/spring-context-2.5.xsd"><context:component-scan  base-package="com.abd.spring3"  /></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){​ApplicationContext context =new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​MyService customerA = (MyService)context.getBean("myService");​customerA.setMessage("Message by customerA");​System.out.println("Message : " + customerA.getMessage());​// Retrieving "myService" , But Not Putting Any Message​// setMessage() Method of MyService Class​MyService custB = (MyService)context.getBean("myService");​System.out.println("Message : " + custB.getMessage());}} |

Output

| ![](image_rsrcFSC.jpg) |

Chapter 6 :

Spring Beans Properties ( Collection Of Objects )

Injection ( Injecting Dependent Object Into Calling

Object( Parent Object ) )

Lab - 10 - Beans Properties  List Properties - XML

Lab - 11 - Beans Properties  ListFactoryBean - XML

Lab - 12 - Beans Properties  Util List - XML

Lab - 13 - Beans Properties  Set Properties - XML

Lab - 14 - Beans Properties  Set Util - XML

Lab - 15 - Beans Properties  Map Properties - XML

Lab - 16 - Beans Properties  MapFactoryBean - XML

Lab - 17 - Beans Properties  Map Util - XML

Lab - 18 - Beans Properties  Collection Properties - XML

Spring Beans Properties ( Collection Of Objects )

In this lesson we will learn 

How to define  Colletion Object In ( .xml )

How Spring Container will be Intiallizing the Beans to

Make in Ready State   Ready to Use.

Spring Container    ☐    While Defining the Collection Object

☐    Developer Giving Instruction to

☐    Spring Container  that

☐    This Particular Bean Registered

☐    Required Special Handling

☐    Which , Beans Contain

☐    Collection Properties as a variable

☐    Developer Giving Instruction to

☐    Spring Container Through ( .xml ) File

☐    What to Do , How to Do

☐    Instruction For Spring Container

☐    In ( .xml ) File Instruction Registered

☐    Collection Object A Way of Defining

☐    Collection Information in In ( .xml ) File

☐    That’s All

☐    While Doing the labs

☐    We learn the things

Lab - 10 - Beans Properties  List Properties – XML

| ![](image_rsrcFSD.jpg) |

Customer.java

| package com.abd.spring3;import java.util.ArrayList;import java.util.List;public  class Customer{​private List<Object> lists = new ArrayList<Object>();public String toString(){return  lists.toString();}​public List<Object> getLists() {​return  lists;​}​public  void setLists(List<Object> lists) {​this.lists = lists;​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <bean  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<!-- java.util.List -->​<property  name="lists">​<list>​<value>1</value>​<ref  bean="PersonBean"  />​<bean  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="27"  />​</bean>​</list>​</property>​</bean>​<bean  id="PersonBean"  class="com.abd.spring3.Person">​<property  name="name"  value="Bharat"  />​<property  name="address"  value="4 B Pune"  />​<property  name="age"  value="28"  />​</bean></beans > |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

| ![](image_rsrcFSE.jpg) |

Output

| ![](image_rsrcFSF.jpg) |

Lab - 11 - Beans Properties  ListFactoryBean – XML

| ![](image_rsrcFSG.jpg) |

Customer.java

| package com.abd.spring3;import java.util.ArrayList;import java.util.List;public  class Customer{​private List<Object> lists = new ArrayList<Object>();public String toString(){return  lists.toString();}​public List<Object> getLists() {​return  lists;​}​public  void setLists(List<Object> lists) {​this.lists = lists;​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<property  name="lists">​<bean  class="org.springframework.beans.factory.config.ListFactoryBean">​<property  name="targetListClass">​<value>java.util.ArrayList</value>​</property>​<property  name="sourceList">​<list>​<value>1</value>​<value>2</value>​<value>3</value>​</list>​</property>​</bean>​</property>​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFSH.jpg) |

Lab - 12 - Beans Properties  Util List - XML

| ![](image_rsrcFSJ.jpg) |

Customer.java

| package com.abd.spring3;import java.util.ArrayList;import java.util.List;public  class Customer {​private List<Object> lists = new ArrayList<Object>();public String toString(){return  lists.toString();}​public List<Object> getLists() {​return  lists;​}​public  void setLists(List<Object> lists) {​this.lists = lists;​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:util="http://www.springframework.org/schema/util"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/util​http://www.springframework.org/schema/util/spring-util-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<property  name="lists">​<util:list  list-class="java.util.ArrayList">​<value>1</value>​<value>2</value>​<value>3</value>​</util:list>​</property>​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFSK.jpg) |

Lab - 13 - Beans Properties  Set Properties – XML

| ![](image_rsrcFSM.jpg) |

Customer.java

| package com.abd.spring3;import java.util.HashSet;import java.util.Set;public  class Customer {​private Set<Object> sets = new HashSet<Object>();​public Set<Object> getSets() {​return  sets;​}​public  void setSets(Set<Object> sets) {​this.sets = sets;​}​public String toString() {​return  sets.toString();​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<!-- java.util.Set -->​<property  name="sets">​<set>​<value>1</value>​<ref  bean="PersonBean"  />​<bean  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="27"  />​</bean>​</set>​</property>​</bean>​<bean  id="PersonBean"  class="com.abd.spring3.Person">​<property  name="name"  value="Bharat"  />​<property  name="address"  value="4 B Pune"  />​<property  name="age"  value="28"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFSN.jpg) |

Lab - 14 - Beans Properties  Set Util - XML

| ![](image_rsrcFSP.jpg) |

Customer.java

| package com.abd.spring3;import java.util.HashSet;import java.util.Set;public  class Customer {​private Set<Object> sets = new HashSet<Object>();​public Set<Object> getSets() {​return  sets;​}​public  void setSets(Set<Object> sets) {​this.sets = sets;​}​public String toString() {​return  sets.toString();​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:util="http://www.springframework.org/schema/util"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/util​http://www.springframework.org/schema/util/spring-util-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<property  name="sets">​<util:set  set-class="java.util.HashSet">​<value>1</value>​<value>2</value>​<value>3</value>​</util:set>​</property>​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

| ![](image_rsrcFSR.jpg) |

Lab - 15 - Beans Properties  Map Properties – XML

| ![](image_rsrcFSS.jpg) |

Customer.java

| package com.abd.spring3;import java.util.HashMap;import java.util.Map;public  class Customer {​private Map<Object, Object> maps = new HashMap<Object, Object>();​public String toString() {​return  maps.toString();​}​public Map<Object, Object> getMaps() {​return  maps;​}​public  void setMaps(Map<Object, Object> maps) {​this.maps = maps;​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [Name=" + name + ", Age=" + age + ", Address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<!-- java.util.Map -->​<property  name="maps">​<map>​<entry  key="Key 1"  value="1"  />​<entry  key="Key 2"  value-ref="PersonBean"  />​<entry  key="Key 3">​<bean  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="27"  />​</bean>​</entry>​</map>​</property>​</bean>​<bean  id="PersonBean"  class="com.abd.spring3.Person">​<property  name="name"  value="Bharat"  />​<property  name="address"  value="4 B pune"  />​<property  name="age"  value="28"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFST.jpg) |

Lab - 16 - Beans Properties  MapFactoryBean – XML

| ![](image_rsrcFSU.jpg) |

Customer.java

| package com.abd.spring3;import java.util.HashMap;import java.util.Map;public  class Customer {​private Map<Object, Object> maps = new HashMap<Object, Object>();​public String toString() {​return  maps.toString();​}​public Map<Object, Object> getMaps() {​return  maps;​}​public  void setMaps(Map<Object, Object> maps) {​this.maps = maps;​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<property  name="maps">​<bean  class="org.springframework.beans.factory.config.MapFactoryBean">​<property  name="targetMapClass">​<value>java.util.HashMap</value>​</property>​<property  name="sourceMap">​<map>​<entry  key="Key1"  value="1"  />​<entry  key="Key2"  value="2"  />​<entry  key="Key3"  value="3"  />​</map>​</property>​</bean>​</property>​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFSV.jpg) |

Lab - 17 - Beans Properties  Map Util – XML

| ![](image_rsrcFSW.jpg) |

Customer.java

| package com.abd.spring3;import java.util.HashMap;import java.util.Map;public  class Customer {​private Map<Object, Object> maps = new HashMap<Object, Object>();​public String toString() {​return  maps.toString();​}​public Map<Object, Object> getMaps() {​return  maps;​}​public  void setMaps(Map<Object, Object> maps) {​this.maps = maps;​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:util="http://www.springframework.org/schema/util"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/util​http://www.springframework.org/schema/util/spring-util-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<property  name="maps">​<util:map  map-class="java.util.HashMap">​<entry  key="Key1"  value="1"  />​<entry  key="Key2"  value="2"  />​<entry  key="Key3"  value="3"  />​</util:map>​</property>​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFSX.jpg) |

Lab - 18 - Beans Properties  Collection Properties - XML

| ![](image_rsrcFSY.jpg) |

Customer.java

| package com.abd.spring3;import java.util.Properties;public  class Customer {​private Properties pros = new Properties();​public Properties getPros() {​return  pros;​}​public  void setPros(Properties pros) {​this.pros = pros;​}​public String toString(){​return  pros.toString();​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="CustomerBean"  class="com.abd.spring3.Customer">​<!-- java.util.Properties -->​<property  name="pros">​<props>​<prop  key="admin">User A</prop>​<prop  key="support">User B</prop>​</props>​</property>​</bean>​<bean  id="PersonBean"  class="com.abd.spring3.Person">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="28"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("CustomerBean");​System.out.println(cust);}} |

Output

| ![](image_rsrcFSZ.jpg) |

Chapter 7 :

Spring Beans Advanced

Lab - 19 - Beans Bean Inheritance – XML

Lab - 20 - Beans Override – XML

Lab - 21 - Beans Initialize and Destroy – XML

Lab - 22 - Beans Spring init Method - XML

Lab - 19 - Beans Bean Inheritance – XML

| ![](image_rsrcFT0.jpg) |

Customer.java

| package com.abd.spring3;public  class Customer {private  int  type;private String action;private String Country;public  int getType() {return  type;}public  void setType(int  type) {this.type = type;}public String getAction() {return  action;}public  void setAction(String action) {this.action = action;}public String getCountry() {return  Country;}public  void setCountry(String country) {Country = country;}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="generalCustomer"  class="com.abd.spring3.Customer">​<property  name="country"  value="USA"  />​</bean>​<bean  id="specialCustomer"  parent="generalCustomer">​<property  name="action"  value="backup"  />​<property  name="type"  value="1"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context =​new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("specialCustomer");​System.out.println(cust);}} |

Lab - 20 - Beans Override – XML

| ![](image_rsrcFT1.jpg) |

Customer.java

| package com.abd.spring3;public  class Customer {private  int  type;private String action;private String Country;public  int getType() {return  type;}public  void setType(int  type) {this.type = type;}public String getAction() {return  action;}public  void setAction(String action) {this.action = action;}public String getCountry() {return  Country;}public  void setCountry(String country) {Country = country;}​@Override​public String toString() {​return  "Customer [Type=" + type + ", Action=" + action + ", Country="​+ Country + "]";​}} |

Person.java

| package com.abd.spring3;public  class Person {​private String name;​private  int  age;​private String address;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​@Override​public String toString() {​return  "Person [name=" + name + ", age=" + age + ", address=" + address​+ "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="generalCustomer"  class="com.abd.spring3.Customer"  abstract="true">​<property  name="country"  value="USA"  />​</bean>​<bean  id="specialCustomer"  parent="generalCustomer">​    <property  name="country"  value="India"  />​<property  name="action"  value="Backup"  />​<property  name="type"  value="1"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context =​new ClassPathXmlApplicationContext("SpringBeans.xml");​Customer cust = (Customer)context.getBean("specialCustomer");​System.out.println(cust);}} |

Output

| ![](image_rsrcFT2.jpg) |

Lab - 21 - Beans Initialize and Destroy – XML

| ![](image_rsrcFT3.jpg) |

PrinterHelper.java

| package com.abd.spring3;import org.springframework.beans.factory.DisposableBean;import org.springframework.beans.factory.InitializingBean;public  class PrinterHelper implements InitializingBean, DisposableBean {​String message;​public String getMessage() {​  return  message;​}​public  void setMessage(String message) {​ this.message = message;​}​public  void afterPropertiesSet() throws Exception {​  System.out.println("Init Method After Properties are Set : " + message);​}​public  void destroy() throws Exception {​  System.out.println("Spring Container Destroyed , java Bean also Destroyed");​}​@Override​public String toString() {​return  message ;​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd"><bean  id="printerService"  class="com.abd.spring3.PrinterHelper">​<property  name="message"  value="I am Property message"  /></bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ConfigurableApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ConfigurableApplicationContext context =​new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​PrinterHelper cust = (PrinterHelper)context.getBean("printerService");​System.out.println(cust);​context.close();}} |

Output

| ![](image_rsrcFT4.jpg) |

Lab - 22 - Beans Spring init Method - XML

| ![](image_rsrcFT5.jpg) |

PrinterHelper.java

| package com.abd.spring3;public  class PrinterHelper {​String message;​public String getMessage() {​return  message;​}​public  void setMessage(String message) {​this.message = message;​}​public  void initIt() throws Exception {​System.out.println("Init Method after Properties are Set : " + message);​}​public  void cleanUp() throws Exception {​System.out.println("Spring Container Destroyed , java Bean also Destroyed");​}​@Override​public String toString() {​return  message;​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="printerService"  class="com.abd.spring3.PrinterHelper"​init-method="initIt"  destroy-method="cleanUp">​<property  name="message"  value="I am Property Message"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ConfigurableApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ConfigurableApplicationContext context =​new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​PrinterHelper cust = (PrinterHelper)context.getBean("printerService");​System.out.println(cust);​context.close();}} |

Output

| ![](image_rsrcFT6.jpg) |

Chapter 8 :

Spring Beans Properties ( Autowire )

Injection ( Injecting Dependent Object Into Calling

Object( Parent Object ) )

Lab - 23 - Beans Autowire Auto Scan Not Autowired - XML

Lab - 24 - Beans Autowire Auto Scan Autowired - XML

Lab - 25 - Beans Autowire Spring Autowire - XML

Lab - 26 - Beans Autowire Spring Autowire Setter - XML

Spring Container    → After seeing the

→< context:component-scan  Tag

→    Instruction   To  Spring Container

→    That  Special Handling Required

→    Spring Container  Understand  that

→    Annotation is Used

→    Class Information  and  Instruction For

→    Class Variable  In Java File

→    Spring Container  First Look For

→    base-package = "com.abd.spring3" />

→    Base Pakage  Name , What is the

→    Name  of  Pakage   ( com.abd.spring3  )

→    Then   Spring Container will

→    First   Go  To    (  Class path  )  And  Find

→    The  Pakage   ( com.abd.spring3  )

→    Try  to  Load  the Class

→    While   Loading  the  Class

→    Spring Container will  find @Autowired

→    @Autowired   Means

→    Variable  Marked  as  @Autowired  

→    Is  a  Class   It  Should  Be  Injected

→    In  Java Class Through setter Injection

→    Spring Container  will  Find Particular

→    Class Marked as  @Autowired  

→    Take  the  Class  and  do  the other task

→    Loading , Creating instance ,

→    Intializing the Resource

→    And  Inject the Dependent Resource

→    That’s   All

→    While  seeing  the  Labs

→    You  will  understand the things

Lab - 23 - Beans Autowire Auto Scan Not Autowired – XML

| ![](image_rsrcFT7.jpg) |

PrinterHelper.java

| package com.abd.spring3;public  class PrinterHelper {​Printer printer;​public  void setPrinter(Printer myPrinter) {​this.printer = myPrinter;​}​@Override​public String toString() {​return  "PrinterHelper [myPrinter=" + printer + "]";​}} |

Printer.java

| package com.abd.spring3;public  class Printer {} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="printerHelper"  class="com.abd.spring3.PrinterHelper">​<property  name="printer"  ref="myPrinter"  />​</bean>​<bean  id="myPrinter"  class="com.abd.spring3.Printer"  /></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {public  static  void main( String[] args ) {​ApplicationContext context =​  new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​PrinterHelper cust = (PrinterHelper)context.getBean("printerHelper");​System.out.println(cust);}} |

Lab - 24 - Beans Autowire Auto Scan Autowired – XML

| ![](image_rsrcFT8.jpg) |

PrinterHelper.java

| package com.abd.spring3;import org.springframework.beans.factory.annotation.Autowired;import org.springframework.stereotype.Component;@Componentpublic  class PrinterHelper{​@Autowired​Printer myPrinter;} |

Printer.java

| package com.abd.spring3;import org.springframework.stereotype.Component;@Componentpublic  class Printer{} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:context="http://www.springframework.org/schema/context"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/context​http://www.springframework.org/schema/context/spring-context-2.5.xsd">​<context:component-scan  base-package="com.abd.spring3"  /></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){​ApplicationContext context =​  new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​PrinterHelper cust = (PrinterHelper)context.getBean("printerHelper");​System.out.println(cust);}} |

Lab - 25 - Beans Autowire Spring Autowire – XML

| ![](image_rsrcFT9.jpg) |

Employee.java

| package com.abd.spring3;public  class Employee {private String name;private String address;private  int  age;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​@Override​public String toString() {​return  "Employee [name=" + name + ", address=" + address + ", age="​+ age + "]";​}} |

JobTitle.java

| package com.abd.spring3;public  class JobTitle {​@Override​public String toString() {​return  "JobTitle [person=" + person + ", type=" + type + ", action="​+ action + "]";​}​public Employee getPerson() {​return  person;​}​public  void setPerson(Employee person) {​this.person = person;​}​public  int getType() {​return  type;​}​public  void setType(int  type) {​this.type = type;​}​public String getAction() {​return  action;​}​public  void setAction(String action) {​this.action = action;​}​private Employee person;​private  int  type;​private String action;} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:context="http://www.springframework.org/schema/context"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/context​http://www.springframework.org/schema/context/spring-context-2.5.xsd">​<context:annotation-config  />​<bean  id="myJobTitle"  class="com.abd.spring3.JobTitle">​<property  name="action"  value="Buy"  />​<property  name="type"  value="1"  />​</bean>​<bean  id="myEmp"  class="com.abd.spring3.Employee">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A Bangalore"  />​<property  name="age"  value="28"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){​ApplicationContext context =​  new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​JobTitle cust = (JobTitle)context.getBean("myJobTitle");​System.out.println(cust);}} |

Output

| ![](image_rsrcFTA.jpg) |

Lab - 26 - Beans Autowire Spring Autowire Setter - XML

| ![](image_rsrcFTB.jpg) |

Employee.java

| package com.abd.spring3;public  class Employee{private String name;private String address;private  int  age;​public String getName() {​return  name;​}​public  void setName(String name) {​this.name = name;​}​public String getAddress() {​return  address;​}​public  void setAddress(String address) {​this.address = address;​}​public  int getAge() {​return  age;​}​public  void setAge(int  age) {​this.age = age;​}​@Override​public String toString() {​return  "Employee [name=" + name + ", address=" + address + ", age="​+ age + "]";​}} |

JobTitle.java

| package com.abd.spring3;import org.springframework.beans.factory.annotation.Autowired;public  class JobTitle{​@Override​public String toString() {​return  "JobTitle [person=" + person + ", type=" + type + ", action="​+ action + "]";​}​public Employee getPerson() {​return  person;​}​@Autowired​public  void setPerson(Employee person) {​this.person = person;​}​public  int getType() {​return  type;​}​public  void setType(int  type) {​this.type = type;​}​public String getAction() {​return  action;​}​public  void setAction(String action) {​this.action = action;​}​private Employee person;​private  int  type;​private String action;} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:context="http://www.springframework.org/schema/context"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd​http://www.springframework.org/schema/context​http://www.springframework.org/schema/context/spring-context-2.5.xsd">​<context:annotation-config  />​<bean  id="myJobTitle"  class="com.abd.spring3.JobTitle">​<property  name="action"  value="Buy"  />​<property  name="type"  value="1"  />​</bean>​<bean  id="myEmp"  class="com.abd.spring3.Employee">​<property  name="name"  value="Amar"  />​<property  name="address"  value="1 A bangalore"  />​<property  name="age"  value="28"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client{public  static  void main( String[] args ){​ApplicationContext context =​  new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});​JobTitle cust = (JobTitle)context.getBean("myJobTitle");​System.out.println(cust);}} |

Output

| ![](image_rsrcFTC.jpg) |

Chapter 9 :

Spring Expression Language

Lab - 27 - Spring Expression Language            - XML

Lab - 28 - Spring Expression Language            - Annotation

Lab - 27 - Spring Expression Language            - XML

| ![](image_rsrcFTD.jpg) |

Item.java

| package com.abd.spring3;public  class Item {​private String name;​private  int  qty;​public String getName() {​return  name;​}​@Override​public String toString() {​return  "Item [name=" + name + ", qty=" + qty + "]";​}​public  int getQty() {​return  qty;​}​public  void setQty(int  qty) {​this.qty = qty;​}​public  void setName(String name) {​this.name = name;​}} |

Server.java

| package com.abd.spring3;public  class Server {​private Item item;​private String itemName;​public Item getItem() {​return  item;​}​public  void setItem(Item item) {​this.item = item;​}​public String getItemName() {​return  itemName;​}​public  void setItemName(String itemName) {​this.itemName = itemName;​}​@Override​public String toString() {​return  "Server [Item=" + item + ", ItemName=" + itemName + "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">​<bean  id="itemBean"  class="com.abd.spring3.Item">​<property  name="name"  value="ItemA"  />​<property  name="qty"  value="10"  />​</bean>​<bean  id="myServer"  class="com.abd.spring3.Server">​<property  name="item"  value="#{itemBean}"  />​<property  name="itemName"  value="#{itemBean.name}"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {​public  static  void main(String[] args) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Server obj = (Server) context.getBean("myServer");​    System.out.println(obj);​}} |

Output

| ![](image_rsrcFTE.jpg) |

Lab - 28 - Spring Expression Language            - Annotation

| ![](image_rsrcFTF.jpg) |

Item.java

| package com.abd.spring3;import org.springframework.beans.factory.annotation.Value;import org.springframework.stereotype.Component;@Component("itemBean")public  class Item {​@Value("itemA") //inject String directly​private String name;​@Value("10") //inject interger directly​private  int  qty;​public String getName() {​return  name;​}​@Override​public String toString() {​return  "Item [name=" + name + ", qty=" + qty + "]";​}​public  int getQty() {​return  qty;​}​public  void setQty(int  qty) {​this.qty = qty;​}​public  void setName(String name) {​this.name = name;​}} |

Server.java

| package com.abd.spring3;import org.springframework.beans.factory.annotation.Value;import org.springframework.stereotype.Component;@Component("myServer")public  class Server {​@Value("#{itemBean}")​private Item item;​@Value("#{itemBean.name}")​private String itemName;​public Item getItem() {​return  item;​}​public  void setItem(Item item) {​this.item = item;​}​public String getItemName() {​return  itemName;​}​public  void setItemName(String itemName) {​this.itemName = itemName;​}​@Override​public String toString() {​return  "Server [item=" + item + ", itemName=" + itemName + "]";​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xmlns:context="http://www.springframework.org/schema/context"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-3.0.xsd​http://www.springframework.org/schema/context​http://www.springframework.org/schema/context/spring-context-3.0.xsd">​<context:component-scan  base-package="com.abd.spring3"  /></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {​public  static  void main(String[] args) {​ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");​Server obj = (Server) context.getBean("myServer");​    System.out.println(obj);​}} |

Output

| ![](image_rsrcFTG.jpg) |

Chapter 10 :

Spring Aspect Oriented Programming ( AOP )

Lab - 29 - Spring AOP Pre AOP – XML

Lab - 30 - Spring AOP Around AOP - XML

Lab - 29 - Spring AOP Pre AOP – XML

| ![](image_rsrcFTH.jpg) |

PrinterService.java

| package com.abd.spring3;public  class PrinterService {​private String name;​private String url;​public  void setName(String name) {​this.name = name;​}​public  void setUrl(String url) {​this.url = url;​}​public  void printName() {​System.out.println("Printer Name : " + this.name);​}​public  void printURL() {​System.out.println("Printer URL : " + this.url);​}​public  void printThrowException() {​throw  new IllegalArgumentException();​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beans​http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="myService"  class="com.abd.spring3.PrinterService">​<property  name="name"  value="Laser Printer"  />​<property  name="url"  value="http://www.google.com"  />​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {​public  static  void main(String[] args) {​ApplicationContext appContext = new ClassPathXmlApplicationContext(​new String[] { "SpringBeans.xml" });​PrinterService cust = (PrinterService) appContext.getBean("myService");​cust.printName();​cust.printURL();​try {​cust.printThrowException();​} catch (Exception e) {​}​}} |

Output

| ![](image_rsrcFTJ.jpg) |

Lab - 30 - Spring AOP Around AOP – XML

| ![](image_rsrcFTK.jpg) |

AOPAroundMethod.java

| package com.abd.spring3;import java.util.Arrays;import org.aopalliance.intercept.MethodInterceptor;import org.aopalliance.intercept.MethodInvocation;public  class AOPAroundMethod implements MethodInterceptor {​@Override​public Object invoke(MethodInvocation methodInvocation) throws Throwable {​System.out.println("Method name : "​+ methodInvocation.getMethod().getName());​System.out.println("Method arguments : "​+ Arrays.toString(methodInvocation.getArguments()));​System.out.println("Before method!");​try {​// proceed to original method call​Object result = methodInvocation.proceed();​// same with AfterReturningAdvice​System.out.println("after method!");​return  result;​} catch (IllegalArgumentException e) {​// same with ThrowsAdvice​System.out.println("Throw exception aop!");​throw  e;​}​}} |

CustomerService.java

| package com.abd.spring3;public  class CustomerService {​private String name;​private String url;​public  void setName(String name) {​this.name = name;​}​public  void setUrl(String url) {​this.url = url;​}​public  void printName() {​System.out.println("Customer name : " + this.name);​}​public  void printURL() {​System.out.println("Customer website : " + this.url);​}​public  void printThrowException() {​throw  new IllegalArgumentException();​}} |

SpringBeans.xml

| <beans  xmlns="http://www.springframework.org/schema/beans"​xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="http://www.springframework.org/schema/beanshttp://www.springframework.org/schema/beans/spring-beans-2.5.xsd">​<bean  id="customerService"  class="com.abd.spring3.CustomerService">​<property  name="name"  value="Laser Printer"  />​<property  name="url"  value="http://www.google.com"  />​</bean>​<bean  id="hijackAroundMethodBean"  class="com.abd.spring3.AOPAroundMethod"  />​<bean  id="customerServiceProxy"  class="org.springframework.aop.framework.ProxyFactoryBean">​<property  name="target"  ref="customerService"  />​<property  name="interceptorNames">​<list>​<value>hijackAroundMethodBean</value>​</list>​</property>​</bean></beans> |

Client.java

| package com.abd.spring3;import org.springframework.context.ApplicationContext;import org.springframework.context.support.ClassPathXmlApplicationContext;public  class Client {​public  static  void main(String[] args) {​ApplicationContext appContext = new ClassPathXmlApplicationContext(​new String[] { "SpringBeans.xml" });​CustomerService cust = (CustomerService) appContext​.getBean("customerServiceProxy");​cust.printName();​cust.printURL();​try {​cust.printThrowException();​} catch (Exception e) {​}​}} |

Output

| ![](image_rsrcFTM.jpg) |

JPA

JAVA PERSISTENCE

FOR BEGINNERS

In This Book You Will Learn Explanation with Diagramme and

Working Exercises with Successfull Execution of Exercises with Output

Readymade Solution With Step By Step Explanation

AMIT K

Contents

Beginners Guide to Learn JPA Programming Step by Step

Introduction

Chapter 1 : JPA One to One Mapping

1  Example 1 : JPA OneToOne Mapping

2  Example 2 : JPA OneToOne Lazy Load Mapping

3  Example 3 : JPA OneToOne Join Column Mapping

4  Example 4 : JPA OneToOne Primary Key Join Column Mapping

5  Example 5 : JPA OneToOne Map Cascade Mapping

6  Example 6 : JPA OneToOne Unidirectional Mapping

7  Example 7 : JPA OneToOne Bidirectional Mapping

Chapter 2 : JPA One to Many Mapping

1  Example 8 : JPA OneToMany Mapping

2  Example 9 : JPA OneToMany Join Table Mapping

3  Example 10: JPA OneToMany Unidirectional Mapping

4  Example 11: JPA OneToMany OrderBy Mapping

5  Example 12: JPA Persist OrderedList Mapping

6  Example 13: JPA OneToMany Map Key Mapping

7  Example 14: JPA OneToMany Untyped Mapping

Chapter 3 : JPA Many to One Mapping

1  Example 15: JPA ManyToOne Mapping

2  Example 16: JPA ManyToOne Join Columns Mapping

3  Example 17: JPA ManyToOne Join Column Mapping

Chapter 4 : JPA Many to Many Mapping

1  Example 18: JPA ManyToMany Mapping

2  Example 19: JPA ManyToMany Join Table Mapping

3  Example 20: JPA ManyToMany Bidirectional Mapping

4  Example 21: JPA ManyToMany Embeddable Mapping

Introduction

Learning JPA Programming step by step.

JPA ( Java Persistence API ) is a powerful framework that can be used to quickly build robust data-driven application.

Most of the data that our applications manipulate have to be stored in data stores, retrieved, processed and analyzed. If this data store is a relational database and you use an object-oriented programming language such as Java, then you should have a look at JPA.

JPA is an Object-Relational Mapping tool that maps Java objects to relational databases and allows query operations.

In this book, you will learn Java Persistence API, its annotations for mapping entities.

JPA Integration  with spring frameworks.

| ![](image_rsrcFPS.jpg) |

Chapter 1 :

JPA One to One Mapping

1   JPA OneToOne Mapping

2   JPA OneToOne Lazy Load Mapping

3   JPA OneToOne Join Column Mapping

4   JPA OneToOne Primary Key Join Column Mapping

5   JPA OneToOne Map Cascade Mapping

6   JPA OneToOne Unidirectional Mapping

7   JPA OneToOne Bidirectional Mapping

1   JPA OneToOne Mapping

| ![](image_rsrcFTN.jpg) |

Here you will learn how to do one to one map in JPA mapping.

This example assumes that one Person can only be part of one department and one department can only have one person.

In Person entity we mark the Department reference property with @OneToOne annotation.

| @Entitypublic class Person {...@OneToOneprivate Department department;... |

Here is the simple code to setup the two entities and save them to database.

| Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);em.persist(p1);em.persist(d); |

Example 1 :

In This example assumes that one Person can only be part of one department and one department can only have one person.

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;@Entitypublic class Person {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToOneprivate Department department;public Person() {}public Person(String name) {this.name = name;}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {return id;}public void setId(Long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);em.persist(p1);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1 |

2   JPA OneToOne Lazy Load Mapping

| ![](image_rsrcFTN.jpg) |

The following code shows how to do one to one mapping with lazy load setting.

| @OneToOne(fetch=LAZY)private Department department; |

Here you will learn how to do one to one mapping with lazy load setting.

Example 2 :

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;import static javax.persistence.FetchType.LAZY;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;@OneToOne(fetch=LAZY)private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);em.persist(p1);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1 |

3   JPA OneToOne Join Column Mapping

| ![](image_rsrcFTN.jpg) |

The following sections show how to set the join column for one to one map in JPA.

We use the @JoinColumn annotation to set the join column.

| @OneToOne@JoinColumn(name="DEPT_ID")private Department department; |

Here you will learn how to set the join column for one to one map in JPA.

Example 3 :

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.OneToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;@OneToOne@JoinColumn(name="DEPT_ID")private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToOne(mappedBy="department")private Person person;public Person getPerson() {return person;}public void setPerson(Person person) {this.person = person;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", person=" + person+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);d.setPerson(p1);em.persist(p1);em.persist(d);Query query = em.createQuery("SELECT e FROM Person e");List<Person> list = (List<Person>) query.getResultList();System.out.println(list.get(0).getDepartment());}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPT_ID,Column Type: BIGINT:Column Value: 1 |

4   JPA OneToOne Primary Key Join Column Mapping

| ![](image_rsrcFTN.jpg) |

Example 4 :

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;import javax.persistence.PrimaryKeyJoinColumn;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;@OneToOne@PrimaryKeyJoinColumnprivate Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToOne(mappedBy="department")private Person person;public Person getPerson() {return person;}public void setPerson(Person person) {this.person = person;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);d.setPerson(p1);em.persist(p1);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: Tom |

5   JPA OneToOne Map Cascade Mapping

| ![](image_rsrcFTN.jpg) |

The following code shows how to set cascade action for one to one mapping.

| @OneToOne(cascade=CascadeType.ALL,mappedBy="department")private Person person; |

Example 5 :

Person.java

| package com.abd.jpa;import javax.persistence.CascadeType;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.OneToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@OneToOne(cascade=CascadeType.ALL)@JoinColumn(name="DEPT_ID")  private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.CascadeType;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToOne(cascade=CascadeType.ALL,mappedBy="department")private Person person;public Person getPerson() {return person;}public void setPerson(Person person) {this.person = person;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", person=" + person+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);d.setPerson(p1);em.persist(p1);em.persist(d);Query query = em.createQuery("SELECT e FROM Person e");List<Person> list = (List<Person>) query.getResultList();System.out.println(list.get(0).getDepartment());em.remove(list.get(0));}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

6   JPA OneToOne Unidirectional Mapping

| ![](image_rsrcFTN.jpg) |

Here you will learn how to do unidirectional one to one mapping.

Example 6 :

Professor.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.OneToOne;@Entitypublic class Professor {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private String name;private long salary;@OneToOne@JoinColumn(name="PSPACE_ID")private ParkingSpace parkingSpace;public int getId() {return id;}public void setId(int id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}public long getSalary() {return salary;}public void setSalary(long salary) {this.salary = salary;}public ParkingSpace getParkingSpace() {return parkingSpace;}public void setParkingSpace(ParkingSpace parkingSpace) {this.parkingSpace = parkingSpace;}public String toString() {return "Employee id: " + getId() + " name: " + getName() +" with " + getParkingSpace();}} |

ParkingSpace.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.Table;@Entity@Table(name="PARKING_SPACE")public class ParkingSpace {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private int lot;private String location;public int getId() {return id;}public void setId(int id) {this.id = id;}public int getLot() {return lot;}public void setLot(int lot) {this.lot = lot;}public String getLocation() {return location;}public void setLocation(String deptName) {this.location = deptName;}public String toString() {return "ParkingSpace id: " + getId() + " lot: " + getLot() +", location: " + getLocation();}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test() {Professor emp = new Professor();emp.setName("name");emp.setSalary(12345);ParkingSpace ps = new ParkingSpace();ps.setLot(1);ps.setLocation("East");emp.setParkingSpace(ps);em.persist(ps);em.persist(emp);}@PersistenceContextprivate EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: PARKING_SPACERow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: LOCATION,Column Type: VARCHAR:Column Value: EastColumn Name: LOT,Column Type: INTEGER:Column Value: 1Table Name: PROFESSORRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: nameColumn Name: SALARY,Column Type: BIGINT:Column Value: 12345Column Name: PSPACE_ID,Column Type: INTEGER:Column Value: 1 |

7   JPA OneToOne Bidirectional Mapping

| ![](image_rsrcFTP.jpg) |

Here you will learn how to do bidirectional one to one mapping.

Example 7 :

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.OneToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;@OneToOne@JoinColumn(name="DEPT_ID")private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToOne;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToOne(mappedBy="department")private Person person;public Person getPerson() {return person;}public void setPerson(Person person) {this.person = person;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Person p1 = new Person("Tom");p1.setName("Tom");Department d = new Department();d.setName("Design");p1.setDepartment(d);d.setPerson(p1);em.persist(p1);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPT_ID,Column Type: BIGINT:Column Value: 1 |

Chapter 2 :

JPA One to Many Mapping

1   JPA OneToMany Mapping

2   JPA OneToMany Join Table Mapping

3   JPA OneToMany Unidirectional Mapping

4   JPA OneToMany OrderBy Mapping

5   JPA Persist OrderedList Mapping

6   JPA OneToMany Map Key Mapping

7   JPA OneToMany Untyped Mapping

1   JPA OneToMany Mapping

| ![](image_rsrcFTR.jpg) |

Here you will learn how to do one to many mapping in JPA.

A department can have one or many employees.

In Java code we can create a Java Bean to represent an employee with Employee class, and a Department class to represent a department.

When linking Employee and Department, we reference the Department class from Employee as follows.

| @Entitypublic class Person {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@ManyToOneprivate Department department; |

We mark the Department with @ManyToOne to indicate the relation between Department and Employee.

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;@ManyToOneprivate Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1 |

2   JPA OneToMany Join Table Mapping

| ![](image_rsrcFTR.jpg) |

Here you will learn how to do one-to-many mapping.

The following code shows how to use a join table to link an one-to-many mapping.

It uses @JoinTable annotation to set up the join table.

| @OneToMany@JoinTable(name = "PERSON_DEPT", joinColumns = @JoinColumn(name = "EMP_ID"), inverseJoinColumns = @JoinColumn(name = "PHONE_ID"))private Set<Person> persons = new HashSet<Person>(); |

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToOne;import javax.persistence.CascadeType;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToOne (cascade=CascadeType.ALL)private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.CascadeType;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.JoinTable;import javax.persistence.OneToMany;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToMany@JoinTable(name = "PERSON_DEPT", joinColumns = @JoinColumn(name = "EMP_ID"), inverseJoinColumns = @JoinColumn(name = "PHONE_ID"))private Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);d.getPersons().add(p1);d.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Table Name: PERSON_DEPTRow:Column Name: EMP_ID,Column Type: BIGINT:Column Value: 1Column Name: PHONE_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: EMP_ID,Column Type: BIGINT:Column Value: 1Column Name: PHONE_ID,Column Type: BIGINT:Column Value: 2 |

3   JPA OneToMany Unidirectional Mapping

Here you will learn how to do unidirectional one to many mapping.

Professor.java

| package com.abd.jpa;import java.util.ArrayList;import java.util.Collection;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.JoinTable;import javax.persistence.OneToMany;@Entitypublic class Professor {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private String name;private long salary;@OneToMany@JoinTable(name="EMP_PHONE",joinColumns=@JoinColumn(name="EMP_ID"),inverseJoinColumns=@JoinColumn(name="PHONE_ID"))private Collection<Phone> phones;public Professor() {phones = new ArrayList<Phone>();}public int getId() {return id;}public void setId(int id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}public long getSalary() {return salary;}public void setSalary(long salary) {this.salary = salary;}public void addPhone(Phone phone) {if (!getPhones().contains(phone)) {getPhones().add(phone);}}public Collection<Phone> getPhones() {return phones;}public String toString() {return "Employee id: " + getId() + " name: " + getName() +" with " + getPhones().size() + " phones";}} |

Phone.java

| package com.abd.jpa;import javax.persistence.Column;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;@Entitypublic class Phone {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;@Column(name="NUM")private String number;private String type;public int getId() {return id;}public void setId(int id) {this.id = id;}public String getNumber() {return number;}public void setNumber(String phoneNo) {this.number = phoneNo;}public String getType() {return type;}public void setType(String phoneType) {this.type = phoneType;}public String toString() {return "Phone id: " + getId() +", no: " + getNumber() +", type: " + getType();}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test() {Professor emp = new Professor();emp.setName("name");emp.setSalary(12345);Phone p = new Phone();p.setNumber("1234509876");;emp.addPhone(p);em.persist(p);em.persist(emp);}@PersistenceContextprivate EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: EMP_PHONERow:Column Name: EMP_ID,Column Type: INTEGER:Column Value: 1Column Name: PHONE_ID,Column Type: INTEGER:Column Value: 1Table Name: PHONERow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NUM,Column Type: VARCHAR:Column Value: 1234509876Column Name: TYPE,Column Type: VARCHAR:Column Value: nullTable Name: PROFESSORRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: nameColumn Name: SALARY,Column Type: BIGINT:Column Value: 12345 |

4   JPA OneToMany OrderBy Mapping

| ![](image_rsrcFTR.jpg) |

Here you will learn how to do one to many mapping.

The following code shows how to set order by property in one to many mapping.

@OrderBy("name ASC") sets to sort the person set by person name.

| @OneToMany(targetEntity=Person.class, mappedBy="department")@OrderBy("name ASC")private Set<Person> persons = new HashSet<Person>(); |

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToOne;import javax.persistence.CascadeType;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToOne (cascade=CascadeType.ALL)private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToMany;import javax.persistence.OrderBy;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToMany(targetEntity=Person.class, mappedBy="department")@OrderBy("name ASC")private Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);d.getPersons().add(p1);d.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1 |

5   JPA Persist OrderedList Mapping

Here you will learn how to do one to many mapping.

| @OneToMany(mappedBy="queue")@OrderColumn(name="PRINT_ORDER")private List<PrintJob> jobs; |

PrintJob.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.Id;import javax.persistence.ManyToOne;@Entitypublic class PrintJob {@Id private int id;@ManyToOneprivate PrintQueue queue;public int getId() {return id;}public void setId(int id) {this.id = id;}public PrintQueue getQueue() {return queue;}public void setQueue(PrintQueue queue) {this.queue = queue;}   } |

PrintQueue.java

| package com.abd.jpa;import java.util.List;import java.util.ArrayList;import javax.persistence.Entity;import javax.persistence.Id;import javax.persistence.OneToMany;import javax.persistence.OrderColumn;@Entitypublic class PrintQueue {@Id private String name;@OneToMany(mappedBy="queue")@OrderColumn(name="PRINT_ORDER")private List<PrintJob> jobs;public PrintQueue() {jobs = new ArrayList<PrintJob>();}public String getName() {return name;}public void setName(String name) {this.name = name;}public List<PrintJob> getJobs() {return jobs;}public void addJob(PrintJob job) {this.jobs.add(job);job.setQueue(this);}public String toString() {return "PrintQueue: " + name;}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test() {PrintQueue q = new PrintQueue();q.setName("q1");PrintJob j = new PrintJob();j.setId(1);j.setQueue(q);q.getJobs().add(j);em.persist(j);em.persist(q);}@PersistenceContextprivate EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: PRINTJOBRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: QUEUE_NAME,Column Type: VARCHAR:Column Value: q1Column Name: PRINT_ORDER,Column Type: INTEGER:Column Value: 0Table Name: PRINTQUEUERow:Column Name: NAME,Column Type: VARCHAR:Column Value: q1 |

6   JPA OneToMany Map Key Mapping

| ![](image_rsrcFTR.jpg) |

Here you will learn how to do one to many mapping.

The following code shows how to set the mapped key in one to many mapping.

| @OneToMany(targetEntity=Person.class, mappedBy="department")@MapKey(name="id")private Set<Person> persons = new HashSet<Person>(); |

@MapKey(name="id") sets to use the person id as the map key for person set.

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToOneprivate Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.MapKey;import javax.persistence.OneToMany;@Entitypublic class Department implements java.io.Serializable{@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToMany(targetEntity=Person.class, mappedBy="department")@MapKey(name="id")private Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);d.getPersons().add(p1);d.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1 |

7   JPA OneToMany Untyped Mapping

The following code indicates the target entity class for an untyped java.util.Map.

| @OneToMany(targetEntity=Employee.class, mappedBy="department")@MapKeyprivate Map employees; |

Employee.java

| package com.abd.jpa;import java.util.Map;import java.util.Set;import javax.persistence.CollectionTable;import javax.persistence.Column;import javax.persistence.ElementCollection;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToOne;import javax.persistence.MapKeyClass;import javax.persistence.MapKeyColumn;@Entitypublic class Employee {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private String name;private long salary;@ElementCollection(targetClass=String.class)@CollectionTable(name="EMP_PHONE")@MapKeyColumn(name="PHONE_TYPE")@MapKeyClass(String.class)@Column(name="PHONE_NUM")private Map phoneNumbers;@ManyToOneprivate Department department;public int getId() {return id;}public void setId(int id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}public long getSalary() {return salary;}public void setSalary(long salary) {this.salary = salary;}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Map getPhoneNumbers() {return phoneNumbers;}public void setPhoneNumbers(Map phoneNumbers) {this.phoneNumbers = phoneNumbers;}public String toString() {StringBuffer aBuffer = new StringBuffer("Employee ");aBuffer.append(" id: ");aBuffer.append(id);aBuffer.append(" with dept: ");if(null != department) {aBuffer.append(department.getName());}aBuffer.append(" phoneNumbers: ");for (Map.Entry e : (Set<Map.Entry>)phoneNumbers.entrySet()) {aBuffer.append(e.getKey() + "[" + e.getValue() + "] ");}       return aBuffer.toString();}} |

Department.java

| package com.abd.jpa;import java.util.HashMap;import java.util.Map;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.MapKey;import javax.persistence.OneToMany;@Entitypublic class Department {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private String name;@OneToMany(targetEntity=Employee.class, mappedBy="department")@MapKeyprivate Map employees;public Department() {employees = new HashMap();}public int getId() {return id;}public void setId(int id) {this.id = id;}public String getName() {return name;}public void setName(String deptName) {this.name = deptName;}public void addEmployee(Employee employee) {employees.put(employee.getId(), employee);if (employee.getDepartment() != null) {employee.getDepartment().getEmployees().remove(employee.getId());}employee.setDepartment(this);}public Map getEmployees() {return employees;}public String toString() {StringBuffer aBuffer = new StringBuffer("Department ");aBuffer.append(" id: ");aBuffer.append(id);aBuffer.append(" name: ");aBuffer.append(name);aBuffer.append(" employeeCount: ");if(null != employees) {          aBuffer.append(employees.size());}return aBuffer.toString();}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test() {Employee e = new Employee();e.setName("Tom");Department d = new Department();d.setName("test");d.getEmployees().put(e, e.getId());em.persist(e);   em.persist(d);}@PersistenceContextprivate EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: testTable Name: EMPLOYEERow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: SALARY,Column Type: BIGINT:Column Value: 0Column Name: DEPARTMENT_ID,Column Type: INTEGER:Column Value: nullTable Name: EMP_PHONE |

Chapter 3 :

JPA Many to One Mapping

1   JPA ManyToOne Mapping

2   JPA ManyToOne Join Columns Mapping

3   JPA ManyToOne Join Column Mapping

1   JPA ManyToOne Mapping

| ![](image_rsrcFTR.jpg) |

Here you will learn how to do many to one mapping.

The following code shows how to do many to one mapping.

It creates two entities, Person and Department. One Department can have many persons.

In the department field from Person class it marks the Department with @ManyToOne annotation.

| @Entitypublic class Person {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@ManyToOne (cascade=CascadeType.ALL)private Department department; |

Person.java

| package com.abd.jpa;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToOne;import javax.persistence.CascadeType;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToOne (cascade=CascadeType.ALL)private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.CascadeType;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToMany;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToMany(mappedBy="department",cascade=CascadeType.ALL)private Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);d.getPersons().add(p1);d.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1 |

2   JPA ManyToOne Join Columns Mapping

| ![](image_rsrcFTR.jpg) |

The following code shows how to set the join columns in the many to one mapping.

| @ManyToOne@JoinColumns({@JoinColumn(name="DEPT_NAME", referencedColumnName="Name"),@JoinColumn(name="DEPT_ID", referencedColumnName="ID")})private Department department; |

Person.java

| package com.abd.jpa;import javax.persistence.CascadeType;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.JoinColumns;import javax.persistence.ManyToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToOne@JoinColumns({@JoinColumn(name="DEPT_NAME", referencedColumnName="Name"),@JoinColumn(name="DEPT_ID", referencedColumnName="ID")})private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToMany;import javax.persistence.OrderBy;@Entitypublic class Department implements java.io.Serializable{@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToMany(targetEntity=Person.class, mappedBy="department")@OrderBy("name ASC")private Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);d.getPersons().add(p1);d.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPT_NAME,Column Type: VARCHAR:Column Value: DesignColumn Name: DEPT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPT_NAME,Column Type: VARCHAR:Column Value: DesignColumn Name: DEPT_ID,Column Type: BIGINT:Column Value: 1 |

3   JPA ManyToOne Join Column Mapping

| ![](image_rsrcFTR.jpg) |

The following code marks the join column used in many to one mapping.

| @ManyToOne (cascade=CascadeType.ALL)@JoinColumn(name="DEPT_ID")private Department department; |

Person.java

| package com.abd.jpa;import javax.persistence.CascadeType;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.ManyToOne;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToOne (cascade=CascadeType.ALL)​@JoinColumn(name="DEPT_ID")private Department department;public Person() {}​public Person(String name) {​this.name = name;​}public Department getDepartment() {return department;}public void setDepartment(Department department) {this.department = department;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.OneToMany;import javax.persistence.OrderBy;@Entitypublic class Department {@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@OneToMany(targetEntity=Person.class, mappedBy="department")@OrderBy("name ASC")private Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import java.util.List;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import javax.persistence.Query;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d = new Department();d.setName("Design");Person p1 = new Person("Tom");p1.setDepartment(d);Person p2 = new Person("Jack");p2.setDepartment(d);d.getPersons().add(p1);d.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignTable Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomColumn Name: DEPT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackColumn Name: DEPT_ID,Column Type: BIGINT:Column Value: 1 |

Chapter 4 :

JPA Many to Many Mapping

1   JPA ManyToMany Mapping

2   JPA ManyToMany Join Table Mapping

3   JPA ManyToMany Bidirectional Mapping

4   JPA ManyToMany Embeddable Mapping

1   JPA ManyToMany Mapping

| ![](image_rsrcFTS.jpg)![](image_rsrcFTT.jpg)![](image_rsrcFTU.jpg) |

Here you will learn how to do many to many mapping.

The following code shows how to create a many to many mapping.

It states a relation between person and department. One department can have many persons and one person can work for many departments.

Person.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToMany;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToManyprivate Set<Department> departments = new HashSet<Department>();public Person() {}​public Person(String name) {​this.name = name;​}public Set<Department> getDepartments() {return departments;}public void setDepartments(Set<Department> departments) {this.departments = departments;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + ", departments="+ departments + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToMany;@Entitypublic class Department implements java.io.Serializable{@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@ManyToManyprivate Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d1 = new Department();d1.setName("Design");Department d2 = new Department();d2.setName("Testing");Person p1 = new Person("Tom");p1.getDepartments().add(d1);p1.getDepartments().add(d2);Person p2 = new Person("Jack");p2.getDepartments().add(d1);p2.getDepartments().add(d2);d1.getPersons().add(p1);d1.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d1);em.persist(d2);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignRow:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: TestingTable Name: DEPARTMENT_PERSONRow:Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Column Name: PERSONS_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Column Name: PERSONS_ID,Column Type: BIGINT:Column Value: 2Table Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomRow:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackTable Name: PERSON_DEPARTMENTRow:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 1Column Name: DEPARTMENTS_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 1Column Name: DEPARTMENTS_ID,Column Type: BIGINT:Column Value: 2Row:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 2Column Name: DEPARTMENTS_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 2Column Name: DEPARTMENTS_ID,Column Type: BIGINT:Column Value: 2 |

2   JPA ManyToMany Join Table Mapping

| ![](image_rsrcFTS.jpg)![](image_rsrcFTT.jpg)![](image_rsrcFTU.jpg) |

The following code shows how to setup a join table for many to many mapping.

Person.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.JoinTable;import javax.persistence.ManyToMany;@Entitypublic class Person {​@Id​@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;​private String name;​@ManyToMany@JoinTable(name="PERSON_DEPT",joinColumns=@JoinColumn(name="PERSON_ID"),inverseJoinColumns=@JoinColumn(name="DEPT_ID"))private Set<Department> departments = new HashSet<Department>();public Person() {}​public Person(String name) {​this.name = name;​}public Set<Department> getDepartments() {return departments;}public void setDepartments(Set<Department> departments) {this.departments = departments;}public Long getId() {​return id;​}​public void setId(Long id) {​this.id = id;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}@Overridepublic String toString() {return "Person [id=" + id + ", name=" + name + ", departments="+ departments + "]";}} |

Department.java

| package com.abd.jpa;import java.util.HashSet;import java.util.Set;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToMany;@Entitypublic class Department implements java.io.Serializable{@Id@GeneratedValue(strategy=GenerationType.IDENTITY)private long id;private String name;@ManyToManyprivate Set<Person> persons = new HashSet<Person>();public Set<Person> getPersons() {return persons;}public void setPersons(Set<Person> persons) {this.persons = persons;}public long getId() {return id;}public void setId(long id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}@Overridepublic String toString() {return "Department [id=" + id + ", name=" + name + ", persons=" + persons+ "]";}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test(){Department d1 = new Department();d1.setName("Design");Department d2 = new Department();d2.setName("Testing");Person p1 = new Person("Tom");p1.getDepartments().add(d1);p1.getDepartments().add(d2);Person p2 = new Person("Jack");p2.getDepartments().add(d1);p2.getDepartments().add(d2);d1.getPersons().add(p1);d1.getPersons().add(p2);em.persist(p1);em.persist(p2);em.persist(d1);em.persist(d2);}​@PersistenceContext​private EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: DesignRow:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: TestingTable Name: DEPARTMENT_PERSONRow:Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Column Name: PERSONS_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1Column Name: PERSONS_ID,Column Type: BIGINT:Column Value: 2Table Name: PERSONRow:Column Name: ID,Column Type: BIGINT:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: TomRow:Column Name: ID,Column Type: BIGINT:Column Value: 2Column Name: NAME,Column Type: VARCHAR:Column Value: JackTable Name: PERSON_DEPTRow:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 1Column Name: DEPT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 1Column Name: DEPT_ID,Column Type: BIGINT:Column Value: 2Row:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 2Column Name: DEPT_ID,Column Type: BIGINT:Column Value: 1Row:Column Name: PERSON_ID,Column Type: BIGINT:Column Value: 2Column Name: DEPT_ID,Column Type: BIGINT:Column Value: 2 |

3   JPA ManyToMany Bidirectional Mapping

| ![](image_rsrcFTV.jpg)![](image_rsrcFTW.jpg)![](image_rsrcFTX.jpg) |

The following code shows how to create a bidirectional many to many mapping.

Professor.java

| package com.abd.jpa;import java.util.ArrayList;import java.util.Collection;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToMany;@Entitypublic class Professor {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private String name;private long salary;@ManyToManyprivate Collection<Project> projects;public Professor() {projects = new ArrayList<Project>();}public int getId() {return id;}public void setId(int id) {this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}public long getSalary() {return salary;}public void setSalary(long salary) {this.salary = salary;}public void addProject(Project project) {if (!getProjects().contains(project)) {getProjects().add(project);}if (!project.getEmployees().contains(this)) {project.getEmployees().add(this);}}public Collection<Project> getProjects() {return projects;}public String toString() {return "Employee id: " + getId() + " name: " + getName() +" with " + getProjects().size() + " projects";}} |

Project.java

| package com.abd.jpa;import java.util.ArrayList;import java.util.Collection;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToMany;@Entitypublic class Project {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)protected int id;protected String name;@ManyToMany(mappedBy="projects")private Collection<Professor> employees;public Project() {employees = new ArrayList<Professor>();}public int getId() {return id;}public void setId(int projectNo) {this.id = projectNo;}public String getName() {return name;}public void setName(String projectName) {this.name = projectName;}public Collection<Professor> getEmployees() {return employees;}public void addEmployee(Professor employee) {if (!getEmployees().contains(employee)) {getEmployees().add(employee);}if (!employee.getProjects().contains(this)) {employee.getProjects().add(this);}}public String toString() {return "Project id: " + getId() + ", name: " + getName() +" with " + getEmployees().size() + " employees";}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test() {Professor emp = new Professor();emp.setName("name");emp.setSalary(12345);Project p = new Project();p.setName("Chem");p.getEmployees().add(emp);emp.getProjects().add(p);em.persist(p);em.persist(emp);}@PersistenceContextprivate EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: PROFESSORRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: nameColumn Name: SALARY,Column Type: BIGINT:Column Value: 12345Table Name: PROFESSOR_PROJECTRow:Column Name: EMPLOYEES_ID,Column Type: INTEGER:Column Value: 1Column Name: PROJECTS_ID,Column Type: INTEGER:Column Value: 1Table Name: PROJECTRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: Chem |

4   JPA ManyToMany Embeddable Mapping

| ![](image_rsrcFTV.jpg)![](image_rsrcFTW.jpg)![](image_rsrcFTX.jpg) |

The following code uses annotation to override the default column for many to many mapping.

| @ManyToMany@JoinTable(name="DEPT_EMP",joinColumns=@JoinColumn(name="DEPT_ID"),inverseJoinColumns=@JoinColumn(name="EMP_ID"))@AttributeOverrides({@AttributeOverride(name="first_Name",column=@Column(name="EMP_FNAME")),@AttributeOverride(name="last_Name",column=@Column(name="EMP_LNAME"))})private Map<EmployeeName, Employee> employeesByName; |

Employee.java

| package com.abd.jpa;import java.util.Collection;import java.util.ArrayList;import javax.persistence.CollectionTable;import javax.persistence.Column;import javax.persistence.ElementCollection;import javax.persistence.Embedded;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.ManyToMany;@Entitypublic class Employee {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;@Embeddedprivate EmployeeName name;private long salary;@ManyToMany(mappedBy="employeesByName")private Collection<Department> departments;public Employee() {name = new EmployeeName();departments = new ArrayList<Department>();}public int getId() {return id;}public void setId(int id) {this.id = id;}public EmployeeName getName() {return name;}public void setName(EmployeeName name) {this.name = name;}public String getFirstName() {return name.getFirst_Name();}public void setFirstName(String firstName) {this.name.setFirst_Name(firstName);}public String getLastName() {return name.getLast_Name();}public void setLastName(String lastName) {this.name.setLast_Name(lastName);}public long getSalary() {return salary;}public void setSalary(long salary) {this.salary = salary;}public Collection<Department> getDepartments() {return departments;}public void setDepartments(Collection<Department> departments) {this.departments = departments;}public String toString() {StringBuffer aBuffer = new StringBuffer("Employee ");aBuffer.append(" id: ");aBuffer.append(id);aBuffer.append(" name: ");aBuffer.append(getLastName());aBuffer.append(", ");aBuffer.append(getFirstName());aBuffer.append(" with deptCount: ");if(null != departments) {aBuffer.append(departments.size());}return aBuffer.toString();}} |

EmployeeName.java

| package com.abd.jpa;import javax.persistence.Column;import javax.persistence.Embeddable;@Embeddablepublic class EmployeeName {@Column(name="F_NAME", insertable=false, updatable=false)private String first_Name;@Column(name="L_NAME", insertable=false, updatable=false)private String last_Name;public String getFirst_Name() {return first_Name;}public void setFirst_Name(String firstName) {first_Name = firstName;}public String getLast_Name() {return last_Name;}public void setLast_Name(String lastName) {last_Name = lastName;}} |

Department.java

| package com.abd.jpa;import java.util.HashMap;import java.util.Iterator;import java.util.Map;import javax.persistence.AttributeOverride;import javax.persistence.AttributeOverrides;import javax.persistence.Column;import javax.persistence.Entity;import javax.persistence.GeneratedValue;import javax.persistence.GenerationType;import javax.persistence.Id;import javax.persistence.JoinColumn;import javax.persistence.JoinTable;import javax.persistence.ManyToMany;@Entitypublic class Department {@Id @GeneratedValue(strategy=GenerationType.IDENTITY)private int id;private String name;@ManyToMany@JoinTable(name="DEPT_EMP",joinColumns=@JoinColumn(name="DEPT_ID"),inverseJoinColumns=@JoinColumn(name="EMP_ID"))@AttributeOverrides({@AttributeOverride(name="first_Name",column=@Column(name="EMP_FNAME")),@AttributeOverride(name="last_Name",column=@Column(name="EMP_LNAME"))})private Map<EmployeeName, Employee> employeesByName;public Department() {employeesByName = new HashMap<EmployeeName,Employee>();}public int getId() {return id;}public void setId(int id) {this.id = id;}public String getName() {return name;}public void setName(String deptName) {this.name = deptName;}public Map<EmployeeName, Employee> getEmployees() {return employeesByName;}public void addEmployee(Employee employee) {EmployeeName empName = employee.getName();employeesByName.put(empName, employee);}public void removeEmployee(Employee employee) {Iterator iter = employeesByName.entrySet().iterator();while (iter.hasNext()) {Employee current = ((Map.Entry<EmployeeName,Employee>) iter.next()).getValue();if (current.getId() == employee.getId()) {iter.remove();}}}public String toString() {StringBuffer aBuffer = new StringBuffer("Department ");aBuffer.append(" id: ");aBuffer.append(id);aBuffer.append(" name: ");aBuffer.append(name);aBuffer.append(" employeeCount: ");aBuffer.append(employeesByName.size());return aBuffer.toString();}} |

PersonDaoImpl.java

| package com.abd.jpa;import javax.persistence.EntityManager;import javax.persistence.PersistenceContext;import org.springframework.transaction.annotation.Transactional;@Transactionalpublic class PersonDaoImpl {public void test() {Employee e = new Employee();e.setFirstName("Tom");e.setLastName("Smith");Department d = new Department();d.setName("test");EmployeeName name = new EmployeeName();name.setFirst_Name("Tom");name.setLast_Name("Smith");e.getDepartments().add(d);d.getEmployees().put(name, e);em.persist(e);   em.persist(d);}@PersistenceContextprivate EntityManager em;} |

Helper.java

| package com.abd.jpa;import java.sql.Connection;import java.sql.DriverManager;import java.sql.ResultSet;import java.sql.ResultSetMetaData;import java.sql.Statement;public class Helper {public static void checkData()  {try{Class.forName("com.mysql.jdbc.Driver");Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");Statement st = conn.createStatement();ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });while (mrs.next()) {String tableName = mrs.getString(3);System.out.println("\n\n\n\nTable Name: "+ tableName);ResultSet rs = st.executeQuery("select * from " + tableName);ResultSetMetaData metadata = rs.getMetaData();while (rs.next()) {System.out.println(" Row:");for (int i = 0; i < metadata.getColumnCount(); i++) {System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+ ",  ");System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+ ":  ");Object value = rs.getObject(i + 1);System.out.println("    Column Value: "+value+"\n");}}}}catch(Exception e){e.printStackTrace();}}} |

persistence.xml

| <?xml version="1.0" encoding="UTF-8"?><persistence version="1.0"xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">​<persistence-unit name="jpaData" /></persistence> |

applicationContext.xml

| <?xml version="1.0" encoding="UTF-8"?><beans xmlns="http://www.springframework.org/schema/beans"​xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context"​xmlns:security="http://www.springframework.org/schema/security"​xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"​xsi:schemaLocation="​http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd​http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd​http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd​http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">​<tx:annotation-driven />​<context:annotation-config />​<bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />​<bean id="dataSource"​class="org.springframework.jdbc.datasource.DriverManagerDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/db1</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<bean id="entityManagerFactory"​class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">​<property name="dataSource" ref="dataSource" />​<property name="persistenceUnitName" value="jpaData" />​<property name="jpaVendorAdapter">​<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />​</property>​<property name="jpaProperties">​<props>​<prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>​<prop key="hibernate.show_sql">true</prop>​<prop key="hibernate.hbm2ddl.auto">update</prop>​</props>​</property>​</bean>​<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">​<property name="entityManagerFactory" ref="entityManagerFactory" />​</bean></beans> |

Client.java

| package com.abd.jpa;import org.springframework.context.support.ClassPathXmlApplicationContext;public class Client {public static void main(String[] args) {ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");dao.test();context.close();Helper.checkData();}} |

Output

| Table Name: DEPARTMENTRow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: NAME,Column Type: VARCHAR:Column Value: testTable Name: DEPT_EMPRow:Column Name: DEPT_ID,Column Type: INTEGER:Column Value: 1Column Name: EMP_ID,Column Type: INTEGER:Column Value: 1Column Name: F_NAME,Column Type: VARCHAR:Column Value: TomColumn Name: L_NAME,Column Type: VARCHAR:Column Value: SmithTable Name: EMPLOYEERow:Column Name: ID,Column Type: INTEGER:Column Value: 1Column Name: F_NAME,Column Type: VARCHAR:Column Value: nullColumn Name: L_NAME,Column Type: VARCHAR:Column Value: nullColumn Name: SALARY,Column Type: BIGINT:Column Value: 0 |

JAVA

SPRING

HIBERNATE

In This Book You Will Learn Developing Java Web Application Using Spring Hibernate From Scratch

Readymade Solution With Step By Step Explanation

AMIT K

Introduction

Learning how to Develope Java Web Application Using Spring Hibernate From Scratch.

Here you will learn

When User Will Submit Request Through ( Browser )

Action will Take the Request , Proceed , Contact to Database.

Service Interface ( Having Method ) , What to Do TO Tables

CURD Operation ( Create , Update , Read , Delete ).

Implementaion of Service Interface ( Method )

Having Dependent ( Persitent Object Information ).

DAO Interface ( Methods ) , How to Communicate TO Tables

For CURD Operation ( Create , Update , Read , Delete ).

Responsible For Communicating TO Tables

POJO ( Simple Java Object )

All Request Data Comming From ( Browser )

All Result Data From ( Tables ) To ( Browser ).

MVC ( Model View Controller ) Architecture

For View ( To Display Result Data To Browser )

Result Data Comming From ( Tables )

After Contacting To Database

Front Controller Will Take the

Appropriate ( JSP Page )

And Put the Data Into ( JSP Page )

And Send Back ( JSP Page ) To Browser

Browser will Display .

Home

| ![](image_rsrcFPT.jpg) |

Environment

| Technologies | Struts1 , Spring , Hibernate , Javascript , Css , Jquery |
| Database | MySQL |
| Server | Tomcat 1.6 |
| Logging Tool | Log4j |
| IDE | Eclipse |
| Design  Patterns | Front Controller ,  MVC  , Factory,  DAO  , Proxy , Singleton, Abstract factory pattern, Template pattern, SessionFactory, TransactionFactory. |

Directory Structure

| ![](image_rsrcFPU.jpg) |

Directory Structure ( Expanded )

| ![](image_rsrcFPV.jpg) |

| ![](image_rsrcFPW.jpg) |

| ![](image_rsrcFPX.jpg) |

| ![](image_rsrcFPY.jpg) |

Home

| ![](image_rsrcFPT.jpg) |

Admin Module I

Login

| ![](image_rsrcFTY.jpg) |

Login Success

| ![](image_rsrcFTZ.jpg) |

Add Doctor Account

| ![](image_rsrcFU0.jpg) |

Add Doctor Account Success

| ![](image_rsrcFU1.jpg) |

View Hospital Doctors Information

| ![](image_rsrcFU2.jpg) |

Remove Doctors Information

| ![](image_rsrcFU3.jpg) |

Patient Module II

Patient Registration

| ![](image_rsrcFU4.jpg) |

Patient Registration Success

| ![](image_rsrcFU5.jpg) |

View All Doctors

| ![](image_rsrcFU6.jpg) |

Find Reservation

| ![](image_rsrcFU7.jpg) |

Find Reservation List of Available Doctors

| ![](image_rsrcFU8.jpg) |

Choose Reservation For Doctor To Be Fixed

| ![](image_rsrcFU9.jpg) |

Reservation For Doctor Appointment Confirmed

| ![](image_rsrcFUA.jpg) |

Total Number Appointment of Doctor

| ![](image_rsrcFUB.jpg) |

Cancel Selected Doctor Appointment

| ![](image_rsrcFUC.jpg) |

Cancel Doctor Appointment Success

| ![](image_rsrcFUD.jpg) |

Query Doctors Records

| ![](image_rsrcFUE.jpg) |

Query Doctors Diagnosis Records

| ![](image_rsrcFUF.jpg) |

Doctors Module III

Doctor Login

| ![](image_rsrcFUG.jpg) |

Doctor Login success

| ![](image_rsrcFUH.jpg) |

Change Password

| ![](image_rsrcFUJ.jpg) |

Change Password Success

| ![](image_rsrcFUK.jpg) |

View Patient Appointment

| ![](image_rsrcFUM.jpg) |

Creating records of Patient

| ![](image_rsrcFUN.jpg) |

Creating records of Patient

| ![](image_rsrcFUP.jpg) |

Creating records of Patient Successfully

| ![](image_rsrcFUR.jpg) |

Changing Patient Records

| ![](image_rsrcFUS.jpg) |

Changing Patient Records Success

| ![](image_rsrcFUT.jpg) |

End of Treatment

| ![](image_rsrcFUU.jpg) |

End of Treatment Success

| ![](image_rsrcFUV.jpg) |

Hospital System ( Working Flow )

Step 1 :

Patient   →   Required Doctor  →   Appointment

Step 2 :

Doctor → Doctor see Appointment → Treatment

Step 3 :

Patient → See Treatment

Step 4 :

Doctor  →  Doctor update start end Treatment

Step 5 :

Patient  →  See Treatment Status

Design Document of Hospital System

1 .  Hospital Out-Patient Referral System Features

1 .  Overall Function of the System

*   Operator of the Permissions Level, with clear classification, when the System is to be Authenticated.
*   The Patient privacy of the Individual is Responsible for the Patient's Medical Records can only be the Patient during treatment by the Doctor, other anyone, including Administrator is not authorized to access.

2 .  Patient's Role

*   To Register as a User, set to your Login Name and Password
*   The names of the Doctors a custom query.
*   Based on Results of the Query to make a Reservation, if you specify the day Doctor’s Appointment volume is full, the Reservation Failed. Result random returns to the Patient.
*   You can have an Appointment, view or undo
*   Make an Appointment, you can query the Doctor Information, Medical Information.

3 .  Doctor Role

*   You can view the Reservation the context of the Patient.
*   You can query for Patient Records.
*   You can create Patient Records.
*   The Patient's Medical Record to be Modified.

4 .  Administrator Role.

*   You can Add and Delete Doctors Account.

2 .  Design Process

From the demand analysis, separation of the entities

Major entities:

*   Doctor (doctor)
*   Patient (patient)
*   Medical Record (history)
*   Reservation records (pinqueue)
*   Administrator (administrator)
*   Doctors can be a maximum number of Appointments (appointment)
*   Doctors currently available number of Appointments (currappointment)

MODULE HIERARCHY DIAGRAM

| ![](image_rsrcFUW.jpg) |

COMPONENT DIAGRAM

| ![](image_rsrcFUX.jpg) |

SEQUENCE DIAGRAM FOR REGIESTRATION ( Patient User )

| ![](image_rsrcFUY.jpg) |

ACTIVITY DIAGRAM OF ( Patient )

| ![](image_rsrcFUZ.jpg) |

ACTIVITY DIAGRAM OF ( Doctor )

| ![](image_rsrcFV0.jpg) |

ACTIVITY DIAGRAM OF ( Admin )

| ![](image_rsrcFV1.jpg) |

Creating Database ( tarena1 )

In  MySql ( Server )

| ![](image_rsrcFV2.jpg) |

Deploy Your ( hospital  Web Application )

Into Tomcat Server

Home Page will come like this

Home

| ![](image_rsrcFPT.jpg) |

Again come in to MySql ( Server )

show tables;

This time Automatic Genrated  Table will come

Due to You Already Running ( hospital  Web Application )

In Tomcat Server

| ![](image_rsrcFV3.jpg) |

Insert SQL Statement

First   →   Insert  the given SQL Statement

| /*****************************create database tarena1;use tarena1;Spring.xml========================Step1=========<prop key="hibernate.hbm2ddl.auto">create</prop>Step2=========<prop key="hibernate.hbm2ddl.auto">update</prop>Table will automatically created.*********************************/create sequence dl_admin_seq;create table dl_admin (aid number(2) primary key,username varchar2(20)  unique not null ,password varchar2(20)  not null,email varchar2(20) not null,name varchar2(12) not null,phone varchar2(15));/******************The doctor can make the maximum number of reservations tableDID Doctor Number Primary Key Foreign key dl_doctor (DID)SunA Sunday morning maximum number of reservationsSunP Sunday afternoon maximum number of reservationsMonA Monday morning maximum number of reservationsMonP Monday afternoon maximum number of reservationsTueA Tuesday morning maximum number of reservationsTueP Tuesday afternoon maximum number of reservationsWedA Wednesday morning maximum number of reservationsWedP Wednesday afternoon maximum number of reservationsThuA Thursday morning maximum number of reservationsThuP Thursday afternoon maximum number of reservationsFriA Friday morning maximum number of reservationsFriP Friday afternoon maximum number of reservationsSatA Saturday morning maximum number of reservationsSatP Saturday afternoon maximum number of reservations***********************/create table dl_appointment(did number(5) primary key references dl_doctor(did),sunA number(3) default '0',sunP number(3) default '0',monA number(3) default '0',monP number(3) default '0',tueA number(3) default '0',tueP number(3) default '0',wedA number(3) default '0',wedP number(3) default '0',thuA number(3) default '0',thuP number(3) default '0',friA number(3) default '0',friP number(3) default '0',satA number(3) default '0',satP number(3) default '0');/******************The current number of tables doctor can make an appointmentDID doctor number primary key foreign key dl doctor (DID)SunA Maximum number of available appointments on Sunday morningSunP Sunday afternoon, Maximum number of appointments availableMonA Maximum number of appointments available Monday morningMonP Monday afternoon maximum number of reservationsTueA Tuesday morning maximum number of reservationsTueP Tuesday afternoon maximum number of reservationsWedA Wednesday morning maximum number of reservationsWedP Wednesday afternoon maximum number of reservationsThuA Thursday morning maximum number of reservationsThuP Thursday afternoon maximum number of reservationsFriA Friday morning maximum number of reservationsFriP Friday afternoon maximum number of reservationsSatA Saturday morning maximum number of reservationsSatP Saturday afternoon maximum number of reservations***********************/create table dl_curappointment(did number(5) primary key references dl_doctor(did),sunA number(3,0) default '0',sunP number(3,0) default '0',monA number(3,0) default '0',monP number(3,0) default '0',tueA number(3,0) default '0',tueP number(3,0) default '0',wedA number(3,0) default '0',wedP number(3,0) default '0',thuA number(3,0) default '0',thuP number(3,0) default '0',friA number(3,0) default '0',friP number(3,0) default '0',satA number(3,0) default '0',satP number(3,0) default '0');/********************************Doctor TableDID doctor numberNamePassword PasswordAgeSex1-Male0 - femaleDoctor 's NameDepartmentsSpecialism is good at doctorsTelephone Number*******************************/create table dl_doctor (did number(5) primary key,name varchar2(12) not null,password varchar2(20) not null,age number(3) not null,sex number(1) not null,levels varchar2(12) not null,section varchar2(20) not null,specialism varchar2(20) not null,phone varchar2(15));/******************************The list of medical records is generated in the sequenceHID medical record numberDoctor Primary Doctor Number Foreign Key dl_doctor (DID)Description SymptomDiagnosePatient Number of patients Foreign key dl_patient (DID)Rx prescriptionFinished Treatment has ended0-Is1-NoFDate start time2024-01-2300:00:00SDate end time2024-01-2100:00:00Can be empty*******************************/create sequence dl_history_seq;create table dl_history (hid number(10) primary key,doctor_did number(5)   references dl_doctor(did) not null,description varchar2(64) not null,diagnose varchar2(64) not null,patient_pid number(8)   references dl_patient(pid) not null ,rx varchar2(64) not null,finished number(1)  not null ,fDate date not null,sDate date);/******************************Patient tablePID patient number sequence is generatedNameUsername The login user namePassword PasswordAgeSex1-Male0 - femaleHome AddressTelephone NumberPatient History†*****************************/create sequence dl_patient_seq;create table dl_patient (pid number(8) primary key,name varchar2(12)  not null ,username varchar2(20)  unique not null,password varchar2(20)  not null ,age number(3)  not null ,sex number(1)  not null ,address varchar2(32),phone varchar2(24));/*********************************Reservation record formThe QID record number is generated in the sequencePatient Number of patients Foreign keydl_patient (PID)Doctor Primary Doctor Number Foreign Key dl_doctor (DID)Day Schedule an appointment time0-Sunday1- Monday2- Tuesday3 - Wednesday4 - Thursday5 - Friday6 - SaturdayAP appointment time0 - am1- AfternoonDat appointment time2024-01-02100:00:00********************************/create sequence dl_pinqueue_seq;create table dl_pinqueue (qid number(10) primary key,patient_pid number(8) references dl_patient(pid) not null,doctor_did number(5)  references dl_doctor(did) not null,day number(1)  not null,ap number(1)  not null,dat date not null,constraint pinqueue_Doctor_Patient unique (doctor_did,patient_pid)); |

First   →   Insert  the given SQL Statement

| Credentials================ADMIN================user     :apassword :atable    :tarenaTotal TABLE :7 TABLEdl_patient==============user     :Amarpassword :AmarFirst Patient Will Regiestered(Auto Generated Password=123456) See in Table then you can change your Password if want.dl_doctor====================user     :Indirapassword :Indirainsert into dl_admin       (    username,     password,        email,               phone ,        name );insert into dl_admin values(1,  'a',          'a',             'a@abc.com' ,        '12345' ,      'a'  );insert into dl_admin values(2,  'Admin',      'Admin',         'admin@abc.com' ,    '21345' ,      'Admin' );2 dl_doctor===============INSERT INTO `dl_doctor`        (`DID`,     `Name`,   `Password`,      `Age`,    `Sex`,    `Level`,         `Section`,      `Specialism`,         `Phone`)INSERT INTO `dl_doctor` VALUES ('001',     'Indira',    'Indira',      28,        0,      'Professor',      'Eye',         'Short Sighted',      '82330000');INSERT INTO `dl_doctor` VALUES ('002',     'Jagan',     'Jagan',       29,        0,      'Professor',      'Head',        'Headache',           '10000823');INSERT INTO `dl_doctor` VALUES ('003',     'Chetan',    'Chetan',      40,        0,      'Suregon',        'Nose',        'Snoring',            '12340002');INSERT INTO `dl_doctor` VALUES ('004',     'Dinesh',     'Dinesh',     35,        0,      'Suregon',        'Dental',      'Teeth',              '12300100');INSERT INTO `dl_doctor` VALUES ('005',     'Pankaj',     'Pankaj',     35,        0,      'Suregon',        'Dental',      'Teeth',              '82323100');INSERT INTO `dl_doctor` VALUES ('006',     'Kamal',    'Kamal',        28,        0,      'Professor',      'Eye',         'Short Sighted',      '82332300');INSERT INTO `dl_doctor` VALUES ('007',     'Raman',     'Raman',       29,        0,      'Professor',      'Head',        'Headache',           '12340823');INSERT INTO `dl_doctor` VALUES ('008',     'Bharat',    'Bharat',      40,        0,      'Suregon',        'Nose',        'Snoring',            '83300002');INSERT INTO `dl_doctor` VALUES ('009',     'Rajeev',     'Rajeev',     40,        0,      'Professor',      'Eye',         'Short Sighted',      '45008302');INSERT INTO `dl_doctor` VALUES ('010',     'Ajay',       'Ajay',       44,        0,      'MBBS',           'Physian',     'Cold Fever',         '67300082');INSERT INTO `dl_doctor` VALUES ('011',     'Supriya',    'Supriya',    35,        1,      'Suregon',        'Dental',      'Teeth',              '68082300');INSERT INTO `dl_doctor` VALUES ('012',     'Ritu',       'Ritu',       41,        1,      'MBBS',           'Physian',     'Cold Fever',         '34303000');INSERT INTO `dl_doctor` VALUES ('013',     'Dimple',    'Dimple',      21,        1,      'Professor',      'Eye',         'Short Sighted',      '87230000');INSERT INTO `dl_doctor` VALUES ('014',     'Dipti',     'Dipti',       39,        1,      'Professor',      'Head',        'Headache',           '45000023');INSERT INTO `dl_doctor` VALUES ('015',     'Bhavna',    'Bhavna',      40,        1,      'Suregon',        'Nose',        'Snoring',            '63000230');INSERT INTO `dl_doctor` VALUES ('016',     'Tripti',       'Tripti',   34,        1,      'MBBS',           'Physian',     'Cold Fever',         '56000823');INSERT INTO `dl_doctor` VALUES ('017',     'Dipti',        'Dipti',    24,        1,      'MBBS',           'Physian',     'Cold Fever',         '47230000');INSERT INTO `dl_doctor` VALUES ('018',     'Rohan',     'Rohan',       35,        0,       'Suregon',       'Dental',      'Teeth',              '54080023');INSERT INTO `dl_doctor` VALUES ('019',     'Dinesh',    'Dinesh',      28,        0,       'Professor',     'Eye',         'Short Sighted',      '23380000');INSERT INTO `dl_doctor` VALUES ('020',     'Dipti',     'Dipti',       39,        1,       'Professor',     'Head',        'Headache',           '35400302');INSERT INTO `dl_doctor` VALUES ('021',     'Bhavna',    'Bhavna',      40,        1,       'Suregon',       'Nose',        'Snoring',            '32300230');INSERT INTO `dl_doctor` VALUES ('022',     'Ajay',       'Ajay',       44,        0,        'MBBS',         'Physian',     'Cold Fever',         '57008230');INSERT INTO `dl_doctor` VALUES ('023',     'Amar',       'Amar',       38,        0,       'MBBS',          'Physian',     'Cold Fever',          '98002308');INSERT INTO `dl_doctor` VALUES ('024',     'Kamal',       'Kamal',     28,        0,       'MBBS',          'Physian',     'Cold Fever',          '46323238');INSERT INTO `dl_doctor` VALUES ('025',     'Akshar',       'Akshar',   28,        0,       'MBBS',          'Physian',     'Cold Fever',          '46323238');INSERT INTO `dl_doctor` VALUES ('027',     'Indira1',    'Indira1',    28,        0,    'Professor',        'Eye',         'Short Sighted',       '82330000');3   dl_appointment===================INSERT INTO `dl_appointment`        (`DID`,    `SunA`,   `SunP`,    `MonA`,    `MonP`,   `TueA`,   `TueP`,    `WedA`,   `WedP`,    `ThuA`,    `ThuP`,    `FriA`,    `FriP`,    `SatA`,    `SatP`)INSERT INTO `dl_appointment` VALUES ('001',       4,        4,         4,         4,        4,        4,         4,        4,         4,         4,         4,         4,         4,          4);INSERT INTO `dl_appointment` VALUES ('002',       1,        2,         3,         4,        5,        6,         7,        8,         9,         0,         12,        3,         21,        10);4   dl_curappointment=========================INSERT INTO `dl_curappointment`       (`DID`,              `SunA`,              `SunP`,              `MonA`,              `MonP`,              `TueA`,              `TueP`,              `WedA`,              `WedP`,              `ThuA`,              `ThuP`,              `FriA`,              `FriP`,              `SatA`,              `SatP`)INSERT INTO `dl_curappointment`VALUES ('001',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('002',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('003',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('004',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('005',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('006',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('007',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('008',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('009',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('010',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('011',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('012',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('013',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('014',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('015',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('016',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('017',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('018',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('019',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('020',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('021',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);INSERT INTO `dl_curappointment`VALUES ('022',     1,      1,       1,     1,       1,      1,      1,      1,      1,       1,     1,     1,     1,      1);5   dl_patient================INSERT INTO `dl_patient`       (`PID`,    `Name`,        `Username`,       `Password`,      `Age`,      `Sex`,       `Address`,       `Phone`)INSERT INTO `dl_patient` VALUES (1001,      'Amar',         'Amar',          'Amar',         20,          0,          '1 A AMAR',      '3455234523');INSERT INTO `dl_patient` VALUES (1002,      'Bharat',       'Bharat',        'Bharat',       20,          0,         '3V KANPUR',      '9841215345');INSERT INTO `dl_patient` VALUES (1003,      'Raman',        'Raman',         'Raman',        40,          0,         '1 A DELHI',      '2312341459');INSERT INTO `dl_patient` VALUES (1004,      'Gopal',        'Gopal',         'Gopal',        45,          0,         '2 B PUNE',       '9155341234');INSERT INTO `dl_patient` VALUES (1005,      'Shyam',        'Shyam',         'Shyam',        45,          0,         '2 B PUNE',       '9155341234');6  dl_history===========================================INSERT INTO `dl_history`       (`HID`,   ​`Doctor`,              `Description`,                  `  Diagnose`,              `Patient`,                     `Rx`,                       `Finished`,              `FDate`,                                              `SDate`)INSERT INTO `dl_history` VALUES (2,​​    '001',                  'Headache',                   'Sars',                                 1001,                         'Madecine',        0,            '2024-01-23 19:02:00:0   ',       '2024-01-21 19:03:51:0 ');Data Will Come Automatically |

Entity Relationship Diagram

| ![](image_rsrcFV4.jpg) |

First Ses Some Diagram You Will Get Some Overview

| ![](image_rsrcFV5.jpg) |

| ![](image_rsrcFV6.jpg) |

| ![](image_rsrcFPV.jpg) |

src\com\abd\action

AllAction.java

| package com.abd.action;import java.util.*;import com.abd.biz.*;import com.abd.entity.*;import com.abd.util.*;import org.springframework.context.ApplicationContext;import org.springframework.web.struts.DispatchActionSupport;import org.apache.struts.action.*;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;import javax.servlet.http.HttpSession;public class AllAction extends DispatchActionSupport{​//Administrator Add Doctors​public ActionForward addDoctor(ActionMapping mapping,ActionForm form​,HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​//Obtain the proxy object​AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");​DynaActionForm daf=(DynaActionForm)form;​Integer did = new Integer(Integer.parseInt(daf.getString("did")));​String name = daf.getString("name");​int age = Integer.parseInt( (String)daf.get("age") );​int sex = Integer.parseInt( (String)daf.get("sex") );​String levels = daf.getString("level");​String spe = daf.getString("spe");​String phone = daf.getString("phone");​String section = daf.getString("section");​String spt=daf.getString("spDay");​int[] spDays=new int[14];​spDays = Util.parseSpDays(spt);​//Executed proxy method​admin.addDoctor(did, name, age, sex, levels, spe, spDays, phone, section);​request.setAttribute("addDoctor", "hao");​return mapping.findForward("addDoc");​}​//Administrators get all doctors​public ActionForward getDoctor(ActionMapping mapping,ActionForm form​,HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");​List<Doctor> set = admin.getAllDoctor();​request.getSession(true).setAttribute("doctors", set);​return mapping.findForward("allDoctor");​}​//Administrator Login​public ActionForward aLogin(ActionMapping mapping,ActionForm form​,HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");​DynaActionForm daf=(DynaActionForm)form;             ​String username =daf.getString("username");​admin.login(username, daf.getString("password"));​request.getSession(true).setAttribute("admin", username);​return mapping.findForward("aLogin");​}​//Administrator to delete the doctor if the doctor has Transcend patient medical records or have already been reserved, then the doctor will not be deleted​public ActionForward removeDoctor(ActionMapping mapping,ActionForm form​,HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");​Integer did = new Integer(Integer.parseInt(request.getParameter("did")));​admin.removeDoctor(did);​return mapping.findForward("removeDoctor");​}​//Patient registration​public ActionForward regsterPatient(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​DynaActionForm daf=(DynaActionForm)form;​String username = daf.getString("username");​String password = daf.getString("password");​String name = daf.getString("name");​int age = Integer.parseInt( (String)daf.get("age") );​int sex = Integer.parseInt( (String)daf.get("sex") );​String address = daf.getString("address");​String phone = daf.getString("phone");​Patient p=patient.regiter(name, username, password, age, sex, address, phone);​request.getSession(true).setAttribute("patient", p);​return mapping.findForward("pRegister");​}​//Login patients​public ActionForward pLogin(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​DynaActionForm daf = (DynaActionForm)form;​String username = daf.getString("username");​String password = daf.getString("password");​Patient p=patient.login(username, password);​request.getSession(true).setAttribute("patient", p);​return mapping.findForward("pLogin");​}​//Find all doctor patient information​public ActionForward allDoctorMessage(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​List<Doctor> set = patient.queryAllDoctor();​request.getSession(true).setAttribute("doctors1", set);​return mapping.findForward("getDoc");​}​//Patient doctor's appointment needed information​public ActionForward getMessage(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​List<Doctor> set = patient.queryAllDoctor();​Set l1=new HashSet();​Set l2=new HashSet();​Set l3=new HashSet();​for(Doctor d:set){​l1.add(d.getSection());​l2.add(d.getLevels());​l3.add(d.getSpe());​}​request.setAttribute("sections", l1);​request.setAttribute("levels",l2);​request.setAttribute("spes", l3);​return mapping.findForward("pqd");​}​//Patients according to their own criteria query doctor​public ActionForward patientQueryMessage(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​DynaActionForm daf=(DynaActionForm)form;​String section=daf.getString("section");​String levels=daf.getString("level");​String spe=daf.getString("spe");​int day=Integer.parseInt(daf.getString("day"));​int ap=Integer.parseInt(daf.getString("ap"));​List<Doctor> l=patient.queryDoctor(section,levels,spe,day,ap);​request.getSession(true).setAttribute("doctorss", l);​return mapping.findForward("getDocss");​}​//Patient appointment​public ActionForward patientAppointment(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​Integer did=new Integer(Integer.parseInt(request.getParameter("did")));​int day = Integer.parseInt(request.getParameter("day"));​int ap = Integer.parseInt(request.getParameter("ap"));​Patient p =(Patient)request.getSession(true).getAttribute("patient");​patient.appointment(p,did, day, ap);​return mapping.findForward("make");​}​//Patient information check a doctor's appointment​public ActionForward patientAppointmentMessage(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​DynaActionForm daf=(DynaActionForm)form;​Integer did = new Integer(Integer.parseInt(daf.getString("did")));​Curappointment cur=patient.queryByDid(did);​request.getSession(true).setAttribute("curappointment",cur);​return mapping.findForward("appoint");​}​//Patients with an appointment to see your doctor​public ActionForward patientMyAppointment(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​Integer pid=new Integer(Integer.parseInt(request.getParameter("pid")));​List<Pinqueue> list=patient.getPinqueueByPid(pid);​request.getSession(true).setAttribute("pinqueues", list);​return mapping.findForward("getApp");​}​//Patient appointments canceled​public ActionForward patientCancleAppointment(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​Integer qid = new Integer(Integer.parseInt(request.getParameter("qid")));​patient.cancleAppointemnt(qid);​return mapping.findForward("cancle");​}​//Patients get physician information​public ActionForward getDoctorMessage(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​Integer pid=new Integer(Integer.parseInt(request.getParameter("pid")));​List<Doctor> l=patient.queryDoctorByPid(pid);​request.getSession(true).setAttribute("dMessages", l);​return mapping.findForward("current");​}​//Patient medical files​public ActionForward queryHistory(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request,HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​PatientBiz patient= (PatientBiz)ctx.getBean("servicePatient");​Integer pid=new Integer(Integer.parseInt(request.getParameter("pid")));​List<History> l = patient.queryHistoryByPid(pid);​request.getSession(true).setAttribute("historys", l);​return mapping.findForward("his");​}​//Doctor Login​public ActionForward dLogin(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​DynaActionForm daf=(DynaActionForm)form;​String name = daf.getString("name");​String password = daf.getString("password");​Doctor d = doctor.login(name, password);​request.getSession(true).setAttribute("doctor", d);​return mapping.findForward("dLogin");​}​//Doctors Change Password​public ActionForward doctorUpdatePassword(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​DynaActionForm daf=(DynaActionForm)form;​String newPassword = daf.getString("password");​String name = ((Doctor)request.getSession(true).getAttribute("doctor")).getName();​doctor.updatePassword(name,newPassword);​request.setAttribute("newPassword", newPassword);​return mapping.findForward("upp");​}​//Doctors get an appointment patient information​public ActionForward getAppointmentMessage(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​Integer did = new Integer(request.getParameter("did"));​List<DoctorQueryPinqueue> l = doctor.getAllPinqueue(did);​request.getSession(true).setAttribute("pinqueues1", l);​return mapping.findForward("getPatientIn");​}​//Transcend medical doctor​public ActionForward createHistory(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​DynaActionForm daf=(DynaActionForm)form;​Doctor d=(Doctor)request.getSession(true).getAttribute("doctor");​Integer pid = new Integer(Integer.parseInt(request.getParameter("pid")));​String description = daf.getString("description");​String diagnose = daf.getString("diagnose");​String rx = daf.getString("rx");​int pd = 1;​doctor.doctorCreatePinqueue(pid,d, description, diagnose, rx, pd);​request.setAttribute("bing", pd);​return mapping.findForward("create");​}​//Doctors check patient records​public ActionForward queryPatientHistory(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​Integer did = new Integer(Integer.parseInt(request.getParameter("did")));​List<DoctorQueryHistory> dqh=doctor.getAllHistory(did);​request.getSession(true).setAttribute("dqhs", dqh);​return mapping.findForward("gph");​}​//Change doctor patient records​public ActionForward updatePatientHistory(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​Integer hid = new Integer(Integer.parseInt(request.getParameter("hid")));​String description = request.getParameter("description");​String diagnose = request.getParameter("diagnose");​String rx = request.getParameter("rx");​doctor.updateHistory(hid, description, diagnose, rx);​request.setAttribute("upda", hid);​return mapping.findForward("upok");​}​//Doctors treating patients with end​public ActionForward finishHistory(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​ApplicationContext ctx = this.getWebApplicationContext();​DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");​Integer hid = new Integer(Integer.parseInt(request.getParameter("hid")));​doctor.finish(hid);​return mapping.findForward("finishOk");​}​//Write-off​public ActionForward exit(ActionMapping mapping ,ActionForm form ,​HttpServletRequest request , HttpServletResponse response)throws Exception{​HttpSession session=request.getSession(true);​if(session.getAttribute("admin")!=null){session.setAttribute("admin", null);}​if(session.getAttribute("doctor")!=null){session.setAttribute("doctor", null);}​if(session.getAttribute("patient")!=null){session.setAttribute("patient", null);}​return mapping.findForward("default");​}} |

| ![](image_rsrcFV7.jpg) |

| ![](image_rsrcFPV.jpg) |

src\com\abd\biz

AdminBiz.java

| package com.abd.biz;import java.io.IOException;import java.sql.SQLException;import java.util.*;import com.abd.expt.SystemException;import com.abd.entity.*;public interface AdminBiz {​//Administrator Login​public void login(String username ,String password)throws IOException ,SQLException,SystemException;​//Administrator Add Doctors​public void addDoctor(Integer did,String name,int age,int sex,String levels,String spe,​int[] pPerDay,String dPhone,String section)throws IOException ,SQLException,SystemException;​//Administrator to delete the doctor​public void removeDoctor(Integer did)throws IOException,SQLException,SystemException;​//The system administrators to view all the information doctors​public List<Doctor> getAllDoctor()throws IOException ,SQLException,SystemException;} |

DoctorBiz.java

| package com.abd.biz;import com.abd.entity.*;import com.abd.expt.SystemException;import java.io.IOException;import java.sql.SQLException;import java.util.List;public interface DoctorBiz {​//Doctors Log object returns a doctor​public Doctor login(String name ,String password)throws IOException ,SQLException,SystemException;​//Doctors Change Password​public void updatePassword(String name ,String newPassword)throws IOException ,SQLException,SystemException;​//According did check all the scheduled recording, according to pid identified patient information, return a few specifically for this method of an object​public List<DoctorQueryPinqueue> getAllPinqueue(Integer did)throws IOException ,SQLException,SystemException;​//Transcend medical doctor​public void doctorCreatePinqueue(Integer pid,Doctor d,String description,String diagnose,String rx,int pd)throws IOException ,SQLException,SystemException;​//Through did check out all of his medical records and patient information patient returns a specialized object write​public List<DoctorQueryHistory> getAllHistory(Integer did)throws IOException ,SQLException,SystemException;​//Update records​public void updateHistory(Integer hid,String description,String diagnose,String rx)throws IOException ,SQLException,SystemException;​//The end of treatment, the need to write the end of time, the end state is changed to 0​public void finish(Integer hid)throws IOException ,SQLException,SystemException;} |

PatientBiz.java

| package com.abd.biz;import java.io.IOException;import java.sql.SQLException;import java.util.*;import com.abd.entity.*;import com.abd.expt.SystemException;public interface PatientBiz {​//Find all doctor patient​public List<Doctor> queryAllDoctor()throws IOException ,SQLException;​//Both methods require that I return the object to facilitate future operations​public Patient regiter(String name,String username,String password,int age,int sex,String address,String phone)throws IOException ,SQLException,SystemException;​//Login patients​public Patient login(String username , String password)throws IOException ,SQLException,SystemException;​//Query returns the current doctor's appointment can be booked several information​public Curappointment queryByDid(Integer did)throws IOException ,SQLException,SystemException;​//Reservation​public void appointment(Patient p ,Integer did ,int day ,int ap)throws IOException ,SQLException,SystemException;​//Discover what they have appointments​public List<Pinqueue> getPinqueueByPid(Integer pid)throws IOException ,SQLException,SystemException;​//Number of patients by appointment canceled appointments​public void cancleAppointemnt(Integer qid)throws IOException ,SQLException,SystemException;​//According to the doctor patient information pid inquiry​public List<Doctor> queryDoctorByPid(Integer pid)throws IOException ,SQLException,SystemException;​//Patient medical files​public List<History> queryHistoryByPid(Integer pid)throws IOException ,SQLException,SystemException;​//Doctors check patients according to their needs​public List<Doctor> queryDoctor(String section,String levels,String spe,int day,int ap) throws IOException, SQLException, SystemException;} |

src\com\abd\biz\impl

AdminBizImpl.java

| package com.abd.biz.impl;import java.io.IOException;import java.sql.SQLException;import java.util.*;import com.abd.biz.AdminBiz;import com.abd.dao.*;import com.abd.entity.*;import com.abd.expt.AppointmentException;import com.abd.expt.IdException;import com.abd.expt.PasswordException;import com.abd.expt.SystemException;import com.abd.expt.UsernameException;public class AdminBizImpl implements AdminBiz {​private AdminDao daoA=null;​private DoctorDao daoB=null;​private AppointmentDao daoC=null;​private CurappointmentDao daoD=null;​public AppointmentDao getDaoC() {​return daoC;​}​public void setDaoC(AppointmentDao daoC) {​this.daoC = daoC;​}​public CurappointmentDao getDaoD() {​return daoD;​}​public void setDaoD(CurappointmentDao daoD) {​this.daoD = daoD;​}​public AdminDao getDaoA() {​return daoA;​}​public void setDaoA(AdminDao daoA) {​this.daoA = daoA;​}​public DoctorDao getDaoB() {​return daoB;​}​public void setDaoB(DoctorDao daoB) {​this.daoB = daoB;​}​public void addDoctor(Integer did, String name, int age, int sex,​String levels, String spe, int[] perDay, String phone,​String section) throws IOException ,SQLException,SystemException{​Doctor doctor=daoB.queryBydid(did);​if(doctor!=null){​throw new IdException("did cuzai");​}else{​doctor = new Doctor();​doctor.setDid(did);​doctor.setName(name);​doctor.setAge(age);​doctor.setSex(sex);​doctor.setLevels(levels);​doctor.setSpe(spe);​doctor.setPhone(phone);​doctor.setPassword("123456");​doctor.setSection(section);​Appointment app=new Appointment(perDay[0],perDay[1],perDay[2],perDay[3],perDay[4],​perDay[5],perDay[6],perDay[7],perDay[8],perDay[9],perDay[10],perDay[11],​perDay[12],perDay[13]);​app.setDoctor(doctor);​Curappointment cuu=new Curappointment(perDay[0],perDay[1],perDay[2],perDay[3],perDay[4],​perDay[5],perDay[6],perDay[7],perDay[8],perDay[9],perDay[10],perDay[11],​perDay[12],perDay[13]);​cuu.setDoctor(doctor);​doctor.setCuu(cuu);​doctor.setApp(app);​daoB.addDoctor(doctor);​}​}​public List<Doctor> getAllDoctor() throws IOException ,SQLException,SystemException{​return daoB.getAllDoctor();​}​public void login(String username, String password) throws IOException ,SQLException,SystemException{​Admin admin=daoA.login(username);​if( admin == null ){​throw new UsernameException( "no such account" ) ;​}​if( ! admin.getPassword().equals( password)){​throw new PasswordException( "invalid password" ) ;​}​}​public void removeDoctor(Integer did) throws IOException ,SQLException,SystemException{​ Appointment app=daoC.queryApp(did);​ app.setDoctor(null);​ daoC.removeApp(app);​ Curappointment cuu=daoD.queryByDid(did);​ cuu.setDoctor(null);​ daoD.removeCur(cuu);​ Doctor doctor=daoB.queryBydid(did);​ doctor.setApp(null);​ doctor.setCuu(null);​daoB.delete(doctor);​}} |

DoctorBizImpl.java

| package com.abd.biz.impl;import java.io.IOException;import java.sql.SQLException;import java.util.ArrayList;import java.util.Date;import java.util.List;import java.util.Set;import com.abd.biz.DoctorBiz;import com.abd.dao.CurappointmentDao;import com.abd.dao.DoctorDao;import com.abd.dao.HistoryDao;import com.abd.dao.PatientDao;import com.abd.dao.PinqueueDao;import com.abd.entity.Curappointment;import com.abd.entity.Doctor;import com.abd.entity.DoctorQueryHistory;import com.abd.entity.DoctorQueryPinqueue;import com.abd.entity.History;import com.abd.entity.Patient;import com.abd.entity.Pinqueue;import com.abd.expt.PasswordException;import com.abd.expt.SystemException;import com.abd.expt.UsernameException;public class DoctorBizImpl implements DoctorBiz {​private DoctorDao daoD;​private PinqueueDao daoQ;​private PatientDao daoP;​private HistoryDao daoH;​private CurappointmentDao daoC;​public CurappointmentDao getDaoC() {​return daoC;​}​public void setDaoC(CurappointmentDao daoC) {​this.daoC = daoC;​}​public DoctorDao getDaoD() {​return daoD;​}​public void setDaoD(DoctorDao daoD) {​this.daoD = daoD;​}​public PinqueueDao getDaoQ() {​return daoQ;​}​public void setDaoQ(PinqueueDao daoQ) {​this.daoQ = daoQ;​}​public PatientDao getDaoP() {​return daoP;​}​public void setDaoP(PatientDao daoP) {​this.daoP = daoP;​}​public HistoryDao getDaoH() {​return daoH;​}​public void setDaoH(HistoryDao daoH) {​this.daoH = daoH;​}​public void doctorCreatePinqueue(Integer pid,Doctor d,String description, String diagnose, String rx, int pd)​throws IOException, SQLException, SystemException {​//Doctor and Patient joint obtained by only PIN​Patient p=daoP.queryByPid(pid);​Pinqueue pin=daoQ.queryByDoctorAndPatient(d, p);​int day=pin.getDay();​int ap=pin.getAp();​//Did get through CUU, CUU update​Curappointment cuu=d.getCuu();​switch(day){​case 0:if(ap==0){cuu.setSunA(cuu.getSunA()+1);​}else{cuu.setSunP(cuu.getSunP()+1);}​break;​case 1:if(ap==0){cuu.setMonA(cuu.getMonA()+1);​}else{cuu.setMonP(cuu.getMonP()+1);}​break;​case 2:if(ap==0){cuu.setTueA(cuu.getTueA()+1);​}else{cuu.setTueP(cuu.getTueP()+1);}​break;​case 3:if(ap==0){cuu.setWedA(cuu.getWedA()+1);​}else{cuu.setWedP(cuu.getWedP()+1);}​break;​case 4:if(ap==0){cuu.setThuA(cuu.getThuA()+1);​}else{cuu.setThuP(cuu.getThuP()+1);}​break;​case 5:if(ap==0){cuu.setFriA(cuu.getFriA()+1);​}else{cuu.setFriP(cuu.getFriP()+1);}​break;​case 6:if(ap==0){cuu.setSatA(cuu.getSatA()+1);​}else{cuu.setSatP(cuu.getSatP()+1);}​break;​}​​//Setting records property​History his = new History();​his.setDescription(description);​his.setDiagnose(diagnose);​his.setRx(rx);​his.setFinished(pd);​his.setFdate(new Date());​his.setDoctor(d);​//Update the patient's property​p.getHistory().add(his);​his.setPatient(p);​//Delete reservation information​pin.setDoctor(null);​pin.setPatient(null);​daoQ.deletePinqueue(pin);​daoH.add(his);​}​public void finish(Integer hid) throws IOException, SQLException,​SystemException {​History his = daoH.query(hid);​Date d=new Date();​his.setFinished(0);​his.setSdate(d);​daoH.update(his);​}​public List<DoctorQueryHistory> getAllHistory(Integer did)​throws IOException, SQLException, SystemException {​List<DoctorQueryHistory> l = new ArrayList<DoctorQueryHistory>();​Doctor d=daoD.queryBydid(did);​List<History> his = daoH.queryByDoctor(d);​for(History h:his){​Patient pat = daoP.queryByPid(h.getPatient().getPid());​DoctorQueryHistory hqh=new DoctorQueryHistory(​h.getHid(), pat.getName(), pat.getAge(), pat.getSex(),​pat.getAddress(),pat.getPhone(), h.getDiagnose(),​h.getDescription(),h.getRx(),h.getFdate(),h.getSdate());​l.add(hqh);​}​return l;​}​public List<DoctorQueryPinqueue> getAllPinqueue(Integer did)​throws IOException, SQLException, SystemException {​List<DoctorQueryPinqueue> l = new ArrayList<DoctorQueryPinqueue>();​Doctor d=daoD.queryBydid(did);​List<Pinqueue> pin = daoQ.queryByDoctor(d);​for(Pinqueue q:pin){​Patient pat = daoP.queryByPid(q.getPatient().getPid());​DoctorQueryPinqueue dqp=new DoctorQueryPinqueue(q.getPatient().getPid(),pat.getName(), pat.getAge(), pat.getSex(),​pat.getAddress(),pat.getPhone(),q.getQid());​l.add(dqp);​}​return l;​}​public Doctor login(String name, String password) throws IOException,​SQLException, SystemException {​Doctor d = daoD.queryName(name);​if( d == null ){​throw new UsernameException( "no such account" ) ;​}​if( ! d.getPassword().equals( password)){​throw new PasswordException( "invalid password" ) ;​}​return d;​}​public void updateHistory(Integer hid, String description, String diagnose,​String rx) throws IOException, SQLException, SystemException {​History his = daoH.query(hid);​his.setDescription(description);​his.setDiagnose(diagnose);​his.setRx(rx);​daoH.update(his);​}​public void updatePassword(String name ,String newPassword) throws IOException,​SQLException, SystemException {​Doctor d = daoD.queryName(name);​d.setPassword(newPassword);​daoD.update(d);​}} |

PatientBizImpl.java

| package com.abd.biz.impl;import java.io.IOException;import java.sql.SQLException;import java.util.ArrayList;import java.util.Date;import java.util.List;import java.util.Set;import com.abd.biz.PatientBiz;import com.abd.dao.CurappointmentDao;import com.abd.dao.DoctorDao;import com.abd.dao.HistoryDao;import com.abd.dao.PatientDao;import com.abd.dao.PinqueueDao;import com.abd.entity.Curappointment;import com.abd.entity.Doctor;import com.abd.entity.History;import com.abd.entity.Patient;import com.abd.entity.Pinqueue;import com.abd.expt.AlreadyAppointmentException;import com.abd.expt.DayAlreadyAppointmentException;import com.abd.expt.IdException;import com.abd.expt.PasswordException;import com.abd.expt.SystemException;import com.abd.expt.UsernameException;import com.abd.expt.WrongException;public class PatientBizImpl implements PatientBiz {​private DoctorDao daoD;​private CurappointmentDao daoC;​private PatientDao daoP;​private HistoryDao daoH;​private PinqueueDao daoQ;​public DoctorDao getDaoD() {​return daoD;​}​public void setDaoD(DoctorDao daoD) {​this.daoD = daoD;​}​public CurappointmentDao getDaoC() {​return daoC;​}​public void setDaoC(CurappointmentDao daoC) {​this.daoC = daoC;​}​public PatientDao getDaoP() {​return daoP;​}​public void setDaoP(PatientDao daoP) {​this.daoP = daoP;​}​public HistoryDao getDaoH() {​return daoH;​}​public void setDaoH(HistoryDao daoH) {​this.daoH = daoH;​}​public PinqueueDao getDaoQ() {​return daoQ;​}​public void setDaoQ(PinqueueDao daoQ) {​this.daoQ = daoQ;​}​public void appointment(Patient p, Integer did, int day, int ap)​throws IOException, SQLException, SystemException {​//Determine whether the doctor appointment​List<Pinqueue> list=daoQ.queryByPatient(p);​for(Pinqueue pin:list){​if( (pin.getDoctor().getDid()).intValue()==did.intValue()){​throw new AlreadyAppointmentException();​}​if(pin.getDay()==day&&pin.getAp()==ap){​throw new DayAlreadyAppointmentException();​}​}​//Set an appointment property​Doctor d=daoD.queryBydid(did);​Pinqueue q=new Pinqueue();​//Update Curappointment​Curappointment cuu=d.getCuu();​switch(day){​case 0:if(ap==0){​cuu.setSunA(cuu.getSunA()-1);​//Today, doctors can determine whether an appointment​if(cuu.getSunA()<0){​throw new WrongException();​}​}else{cuu.setSunP(cuu.getSunP()-1);​if(cuu.getSunP()<0){​throw new WrongException();​}​}​break;​case 1:if(ap==0){​cuu.setMonA(cuu.getMonA()-1);​if(cuu.getMonA()<0){​throw new WrongException();​}​}else{​cuu.setMonP(cuu.getMonP()-1);​if(cuu.getMonP()<0){​throw new WrongException();​}​}​break;​case 2:if(ap==0){​cuu.setTueA(cuu.getTueA()-1);​if(cuu.getTueA()<0){​throw new WrongException();​}​}else{​cuu.setTueP(cuu.getTueP()-1);​if(cuu.getTueP()<0){​throw new WrongException();​}​}​break;​case 3:if(ap==0){​cuu.setWedA(cuu.getWedA()-1);​if(cuu.getWedA()<0){​throw new WrongException();​}​}else{​cuu.setWedP(cuu.getWedP()-1);​if(cuu.getWedP()<0){​throw new WrongException();​}​}​break;​case 4:if(ap==0){​cuu.setThuA(cuu.getThuA()-1);​if(cuu.getThuA()<0){​throw new WrongException();​}​}else{​cuu.setThuP(cuu.getThuP()-1);​if(cuu.getThuP()<0){​throw new WrongException();​}​}​break;​case 5:if(ap==0){​cuu.setFriA(cuu.getFriA()-1);​if(cuu.getFriA()<0){​throw new WrongException();​}​}else{​cuu.setFriP(cuu.getFriP()-1);​if(cuu.getFriP()<0){​throw new WrongException();​}​}​break;​case 6:if(ap==0){​cuu.setSatA(cuu.getSatA()-1);​if(cuu.getSatA()<0){​throw new WrongException();​}​}else{​cuu.setSatP(cuu.getSatP()-1);​if(cuu.getSatP()<0){​throw new WrongException();​}​}​break;​}​q.setDay(day);​q.setDoctor(d);​q.setPatient(p);​q.setAp(ap);​q.setT_date(new Date());​d.getPin().add(q);​daoQ.addPinqueue(q);​}​public void cancleAppointemnt(Integer qid) throws IOException,​SQLException, SystemException {​//Update CUU​//QID obtained by Pin.doctor.did​Pinqueue pin=daoQ.queryByQid(qid);​int day=pin.getDay();​int ap=pin.getAp();​//Did get through CUU,Update CUU​Curappointment cuu=pin.getDoctor().getCuu();​switch(day){​case 0:if(ap==0){cuu.setSunA(cuu.getSunA()+1);​}else{cuu.setSunP(cuu.getSunP()+1);}​break;​case 1:if(ap==0){cuu.setMonA(cuu.getMonA()+1);​}else{cuu.setMonP(cuu.getMonP()+1);}​break;​case 2:if(ap==0){cuu.setTueA(cuu.getTueA()+1);​}else{cuu.setTueP(cuu.getTueP()+1);}​break;​case 3:if(ap==0){cuu.setWedA(cuu.getWedA()+1);​}else{cuu.setWedP(cuu.getWedP()+1);}​break;​case 4:if(ap==0){cuu.setThuA(cuu.getThuA()+1);​}else{cuu.setThuP(cuu.getThuP()+1);}​break;​case 5:if(ap==0){cuu.setFriA(cuu.getFriA()+1);​}else{cuu.setFriP(cuu.getFriP()+1);}​break;​case 6:if(ap==0){cuu.setSatA(cuu.getSatA()+1);​}else{cuu.setSatP(cuu.getSatP()+1);}​break;​}​​pin.setDoctor(null);​pin.setPatient(null);​//Delete PINQUEUE​daoQ.deletePinqueue(pin);​}​public List<Pinqueue> getPinqueueByPid(Integer pid) throws IOException,​SQLException, SystemException {​Patient p=daoP.queryByPid(pid);​return daoQ.queryByPatient(p);​}​public Patient login(String username, String password) throws IOException,​SQLException, SystemException {​Patient p=daoP.queryByUsername(username);​if( p == null ){​throw new IdException( "no such account" ) ;​}​if(!(p.getPassword().equals(password))){​throw new PasswordException( "invalid password" ) ;​}​return p;​}​public List<Doctor> queryAllDoctor() throws IOException, SQLException {​return daoD.getAllDoctor();​}​public Curappointment queryByDid(Integer did) throws IOException,​SQLException, SystemException {​return daoC.queryByDid(did);​}​public List<Doctor> queryDoctorByPid(Integer pid) throws IOException,​SQLException, SystemException {​Patient p=daoP.queryByPid(pid);​List<History> list = daoH.queryByPatient(p);​List<Doctor> l=new ArrayList<Doctor>();​for(History h:list){​Doctor doc=daoD.queryBydid(h.getDoctor().getDid());​l.add(doc);​}​return l;​}​public List<History> queryHistoryByPid(Integer pid) throws IOException,​SQLException, SystemException {​Patient p=daoP.queryByPid(pid);​return daoH.queryByPatient(p);​}​public Patient regiter(String name, String username, String password,​int age, int sex, String address, String phone) throws IOException,​SQLException, SystemException {​Patient p=daoP.queryByUsername(username);​if(p!=null){​throw new UsernameException("username exception");​}​p=new Patient();​p.setAddress(address);​p.setAge(age);p.setName(name);​p.setPassword(password);​p.setPhone(phone);​p.setSex(sex);​p.setUsername(username);​daoP.register(p);​return p;​}​public List<Doctor> queryDoctor(String section,String levels,String spe,int day,int ap)throws IOException,​SQLException, SystemException {​List<Doctor> l=daoD.getAllDoctor();​List<Doctor> list=new ArrayList<Doctor>();​for(Doctor doctor:l){​if(!section.equals("se")){​if(!doctor.getSection().equals(section)){​continue;​}​}​if(!levels.equals("le")){​if(!doctor.getLevels().equals(levels)){​continue;​}​}​if(!spe.equals("nn")){​if(!doctor.getSpe().equals(spe)){​continue;​}​}​list.add(doctor);​Curappointment cuu=doctor.getCuu();​  if(day!=9){​switch(day){​case 0:if(ap==0){​if(cuu.getSunA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getSunP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getSunA()==0&&cuu.getSunP()==0){​list.remove(doctor);​}​}​break;​case 1:if(ap==0){​if(cuu.getMonA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getMonP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getMonA()==0&&cuu.getMonP()==0){​list.remove(doctor);​}​    }​break;​case 2:if(ap==0){​if(cuu.getTueA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getTueP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getTueA()==0&&cuu.getTueP()==0){​list.remove(doctor);​}​}​break;​case 3:if(ap==0){​if(cuu.getWedA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getWedP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getWedA()==0&&cuu.getWedP()==0){​list.remove(doctor);​}​}​break;​case 4:if(ap==0){​if(cuu.getThuA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getThuP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getThuA()==0&&cuu.getThuP()==0){​list.remove(doctor);​}​}​break;​case 5:if(ap==0){​if(cuu.getFriA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getFriP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getFriA()==0&&cuu.getFriP()==0){​list.remove(doctor);​}​}​break;​case 6:if(ap==0){​if(cuu.getSatA()==0){​list.remove(doctor);​};​}else if(ap==1){​if(cuu.getSatP()==0){​list.remove(doctor);​};​}else if(ap==3){​if(cuu.getSatA()==0&&cuu.getSatP()==0){​list.remove(doctor);​}​}​}​  }else if(ap!=3){​  if(ap==0){​  if((cuu.getSunA()==0)&&(cuu.getMonA()==0)&&cuu.getTueA()==0&&cuu.getWedA()==0​  &&cuu.getThuA()==0&&cuu.getFriA()==0&&cuu.getSatA()==0){​  list.remove(doctor);​  }​  }else{​  if((cuu.getSunP()==0)&&(cuu.getMonP()==0)&&cuu.getTueP()==0&&cuu.getWedP()==0​  &&cuu.getThuP()==0&&cuu.getFriP()==0&&cuu.getSatP()==0){​  list.remove(doctor);​  }​  }​  }​}​return list;​}} |

First Ses Some Diagram You Will Get Some Overview

| ![](image_rsrcFV8.jpg) |

| ![](image_rsrcFPV.jpg) |

| ![](image_rsrcFV9.jpg) |

| ![](image_rsrcFVA.jpg) |

| ![](image_rsrcFVB.jpg) |

src\com\abd\dao

AdminDao.java

| package com.abd.dao;import com.abd.entity.Admin;public interface AdminDao {​public Admin login(String username);} |

AppointmentDao.java

| package com.abd.dao;import com.abd.entity.*;public interface AppointmentDao {​public void removeApp(Appointment app);​public Appointment queryApp(Integer did);} |

CurappointmentDao.java

| package com.abd.dao;import java.util.List;import com.abd.entity.Curappointment;public interface CurappointmentDao {​public void removeCur(Curappointment c);​public Curappointment queryByDid(Integer did);​public List<Curappointment> queryByDay(int dayap);} |

DoctorDao.java

| package com.abd.dao;import java.util.List;import com.abd.entity.*;public interface DoctorDao {​public Doctor queryBydid(Integer did);​public Doctor queryName(String name);​public void update(Doctor doctor);​public List<Doctor> getAllDoctor();​public void delete(Doctor doctor);​public void addDoctor(Doctor doctor);} |

HistoryDao.java

| package com.abd.dao;import java.util.List;import com.abd.entity.*;public interface HistoryDao {​public List<History> queryByPatient(Patient p);​public void add(History history);​public History query(Integer hid);​public List<History> queryByDoctor(Doctor d);​public void update(History history);} |

PatientDao.java

| package com.abd.dao;import com.abd.entity.Patient;public interface PatientDao {​public Patient queryByPid(Integer pid);​public void register(Patient patient);​public Patient queryByUsername(String username);} |

PinqueueDao.java

| package com.abd.dao;import java.util.List;import com.abd.entity.*;public interface PinqueueDao {​public Pinqueue queryByDoctorAndPatient(Doctor doctor,Patient patient);​public List<Pinqueue> queryByDoctor(Doctor d);​public List<Pinqueue> queryByPatient(Patient p);​public Pinqueue queryByQid(Integer qid);​public void addPinqueue(Pinqueue q);​public void deletePinqueue(Pinqueue q);} |

src\com\abd\dao\impl

AdminDaoImpl.java

| package com.abd.dao.impl;import java.util.List;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.AdminDao;import com.abd.entity.Admin;public class AdminDaoImpl extends HibernateDaoSupport implements AdminDao {​public Admin login(String username) {​Object args[] = {username};​List<Admin> l=getHibernateTemplate().find("from Admin a where a.username=?",args);​if(l.size() == 0){​ return null;​}else {​return l.get(0);​}​}} |

AppointmentDaoImpl.java

| package com.abd.dao.impl;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.AppointmentDao;import com.abd.entity.*;public class AppointmentDaoImpl extends HibernateDaoSupport implements AppointmentDao {​public Appointment queryApp(Integer did) {​return (Appointment)getHibernateTemplate().get(Appointment.class, did);​}​public void removeApp(Appointment app) {​getHibernateTemplate().delete(app);​}} |

CurappointmentDaoImpl.java

| package com.abd.dao.impl;import java.util.List;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.CurappointmentDao;import com.abd.entity.Curappointment;public class CurappointmentDaoImpl extends HibernateDaoSupport implements​CurappointmentDao {​public Curappointment queryByDid(Integer did) {​return (Curappointment)getHibernateTemplate().get(Curappointment.class, did);​}​public void removeCur(Curappointment c) {​getHibernateTemplate().delete(c);​}​public List<Curappointment> queryByDay(int dayap){​return null;​}} |

DoctorDaoImpl.java

| package com.abd.dao.impl;import java.util.List;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.DoctorDao;import com.abd.entity.Doctor;public class DoctorDaoImpl extends HibernateDaoSupport implements DoctorDao {​public void addDoctor(Doctor doctor) {​getHibernateTemplate().save(doctor) ;​}​public void delete(Doctor doctor) {​getHibernateTemplate().delete(doctor);​}​public List<Doctor> getAllDoctor() {​return getHibernateTemplate().find("from Doctor");​}​public Doctor queryBydid(Integer did) {​return (Doctor)getHibernateTemplate().get(Doctor.class, did);​}​public Doctor queryName(String name) {​Object[] args={name};​List<Doctor> list=getHibernateTemplate().find("from Doctor d where d.name=?", args);​if(list.size()==0){​return null;​}else{​return list.get(0);​}​}​public void update(Doctor doctor) {​getHibernateTemplate().update(doctor);​}} |

HistoryDaoImpl.java

| package com.abd.dao.impl;import java.util.List;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.HistoryDao;import com.abd.entity.*;public class HistoryDaoImpl extends HibernateDaoSupport implements HistoryDao {​public void add(History history) {​}​public History query(Integer hid) {​return (History)getHibernateTemplate().get(History.class, hid);​}​public List<History> queryByDoctor(Doctor d) {​Object[] args={d};​List<History> l=getHibernateTemplate().find("from History h where h.doctor=?", args);​return l;​}​public List<History> queryByPatient(Patient p) {​Object[] args={p};​List<History> l=getHibernateTemplate().find("from History h where h.patient=?", args);​return l;​}​public void update(History history) {​getHibernateTemplate().update(history);​}} |

PatientDaoImpl.java

| package com.abd.dao.impl;import java.util.List;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.PatientDao;import com.abd.entity.Patient;public class PatientDaoImpl extends HibernateDaoSupport implements PatientDao {​public Patient queryByPid(Integer pid) {​return (Patient)getHibernateTemplate().get(Patient.class, pid);​}​public Patient queryByUsername(String username) {​Object args[]={username};​List<Patient> list=getHibernateTemplate().find("from Patient p where p.username=?", args);​if(list.size()==0){​return null;​}else{​return list.get(0);​}​}​public void register(Patient patient) {;​this.getHibernateTemplate().save(patient);​}} |

PinqueueDaoImpl.java

| package com.abd.dao.impl;import java.util.List;import org.springframework.orm.hibernate3.support.HibernateDaoSupport;import com.abd.dao.PinqueueDao;import com.abd.entity.Doctor;import com.abd.entity.Patient;import com.abd.entity.Pinqueue;import com.abd.expt.SystemException;public class PinqueueDaoImpl extends HibernateDaoSupport implements PinqueueDao {​public void addPinqueue(Pinqueue q) {​getHibernateTemplate().save(q);​}​public List<Pinqueue> queryByDoctor(Doctor d) {​Object[] args={d};​List<Pinqueue> list=getHibernateTemplate().find("from Pinqueue q where q.doctor=?", args);​return list;​}​public List<Pinqueue> queryByPatient(Patient p) {​Object[] args={p};​List<Pinqueue> list=getHibernateTemplate().find("from Pinqueue q where q.patient=?", args);​return list;​}​public Pinqueue queryByDoctorAndPatient(Doctor doctor,Patient patient){​Object[] args={doctor};​List<Pinqueue> list=getHibernateTemplate().find("from Pinqueue q where q.doctor=?", args);​for(Pinqueue p:list){​if((p.getPatient().getPid()).intValue()==(patient.getPid()).intValue()){​return p;​}​}​return null;​}​public Pinqueue queryByQid(Integer qid) {​return (Pinqueue)getHibernateTemplate().get(Pinqueue.class, qid);​}​public void deletePinqueue(Pinqueue q) {​getHibernateTemplate().delete(q);​}} |

| ![](image_rsrcFPW.jpg) |

src\com\abd\entity

Admin.java

| package com.abd.entity;import java.io.*;public class Admin implements Serializable{​private Integer aid;​private String username;​private String password;​private String email;​private String phone;​private String name;​public Integer getAid() {​return aid;​}​public void setAid(Integer aid) {​this.aid = aid;​}​public String getUsername() {​return username;​}​public void setUsername(String username) {​this.username = username;​}​public String getPassword() {​return password;​}​public void setPassword(String password) {​this.password = password;​}​public String getEmail() {​return email;​}​public void setEmail(String email) {​this.email = email;​}​public String getPhone() {​return phone;​}​public void setPhone(String phone) {​this.phone = phone;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}} |

Appointment.java

| package com.abd.entity;import java.io.Serializable;/************Provided there are no arguments constructor parameters*/public class Appointment implements Serializable{​private Integer did;​private int sunA;​private int sunP;​private int monA;​private int monP;​private int tueA;​private int tueP;​private int wedA;​private int wedP;​private int thuA;​private int thuP;​private int friA;​private int friP;​private int satA;​private int satP;​private Doctor doctor;​public Appointment() {​super();​}​public Appointment(int sunA, int sunP, int monA, int monP, int tueA,​int tueP, int wedA, int wedP, int thuA, int thuP, int friA,​int friP, int satA, int satP) {​super();​this.sunA = sunA;​this.sunP = sunP;​this.monA = monA;​this.monP = monP;​this.tueA = tueA;​this.tueP = tueP;​this.wedA = wedA;​this.wedP = wedP;​this.thuA = thuA;​this.thuP = thuP;​this.friA = friA;​this.friP = friP;​this.satA = satA;​this.satP = satP;​}​public Doctor getDoctor() {​return doctor;​}​public void setDoctor(Doctor doctor) {​this.doctor = doctor;​}​public Integer getDid() {​return did;​}​public void setDid(Integer did) {​this.did = did;​}​public int getSunA() {​return sunA;​}​public void setSunA(int sunA) {​this.sunA = sunA;​}​public int getSunP() {​return sunP;​}​public void setSunP(int sunP) {​this.sunP = sunP;​}​public int getMonA() {​return monA;​}​public void setMonA(int monA) {​this.monA = monA;​}​public int getMonP() {​return monP;​}​public void setMonP(int monP) {​this.monP = monP;​}​public int getTueA() {​return tueA;​}​public void setTueA(int tueA) {​this.tueA = tueA;​}​public int getTueP() {​return tueP;​}​public void setTueP(int tueP) {​this.tueP = tueP;​}​public int getWedA() {​return wedA;​}​public void setWedA(int wedA) {​this.wedA = wedA;​}​public int getWedP() {​return wedP;​}​public void setWedP(int wedP) {​this.wedP = wedP;​}​public int getThuA() {​return thuA;​}​public void setThuA(int thuA) {​this.thuA = thuA;​}​public int getThuP() {​return thuP;​}​public void setThuP(int thuP) {​this.thuP = thuP;​}​public int getFriA() {​return friA;​}​public void setFriA(int friA) {​this.friA = friA;​}​public int getFriP() {​return friP;​}​public void setFriP(int friP) {​this.friP = friP;​}​public int getSatA() {​return satA;​}​public void setSatA(int satA) {​this.satA = satA;​}​public int getSatP() {​return satP;​}​public void setSatP(int satP) {​this.satP = satP;​}} |

Curappointment.java

| package com.abd.entity;import java.io.Serializable;/** Participation provides a constructor has no parameters*/public class Curappointment implements Serializable{​private Integer did;​private int sunA;​private int sunP;​private int monA;​private int monP;​private int tueA;​private int tueP;​private int wedA;​private int wedP;​private int thuA;​private int thuP;​private int friA;​private int friP;​private int satA;​private int satP;​private Doctor doctor;​public Curappointment() {​super();​// TODO Auto-generated constructor stub​}​public Curappointment(int sunA, int sunP, int monA, int monP, int tueA,​int tueP, int wedA, int wedP, int thuA, int thuP, int friA,​int friP, int satA, int satP) {​super();​this.sunA = sunA;​this.sunP = sunP;​this.monA = monA;​this.monP = monP;​this.tueA = tueA;​this.tueP = tueP;​this.wedA = wedA;​this.wedP = wedP;​this.thuA = thuA;​this.thuP = thuP;​this.friA = friA;​this.friP = friP;​this.satA = satA;​this.satP = satP;​}​public Integer getDid() {​return did;​}​public void setDid(Integer did) {​this.did = did;​}​public int getSunA() {​return sunA;​}​public void setSunA(int sunA) {​this.sunA = sunA;​}​public int getSunP() {​return sunP;​}​public void setSunP(int sunP) {​this.sunP = sunP;​}​public int getMonA() {​return monA;​}​public void setMonA(int monA) {​this.monA = monA;​}​public int getMonP() {​return monP;​}​public void setMonP(int monP) {​this.monP = monP;​}​public int getTueA() {​return tueA;​}​public void setTueA(int tueA) {​this.tueA = tueA;​}​public int getTueP() {​return tueP;​}​public void setTueP(int tueP) {​this.tueP = tueP;​}​public int getWedA() {​return wedA;​}​public void setWedA(int wedA) {​this.wedA = wedA;​}​public int getWedP() {​return wedP;​}​public void setWedP(int wedP) {​this.wedP = wedP;​}​public int getThuA() {​return thuA;​}​public void setThuA(int thuA) {​this.thuA = thuA;​}​public int getThuP() {​return thuP;​}​public void setThuP(int thuP) {​this.thuP = thuP;​}​public int getFriA() {​return friA;​}​public void setFriA(int friA) {​this.friA = friA;​}​public int getFriP() {​return friP;​}​public void setFriP(int friP) {​this.friP = friP;​}​public int getSatA() {​return satA;​}​public void setSatA(int satA) {​this.satA = satA;​}​public int getSatP() {​return satP;​}​public void setSatP(int satP) {​this.satP = satP;​}​public Doctor getDoctor() {​return doctor;​}​public void setDoctor(Doctor doctor) {​this.doctor = doctor;​}} |

Doctor.java

| package com.abd.entity;import java.io.Serializable;import java.util.*;public class Doctor implements Serializable{​private Integer did;​private String name;​private String password;​private int age;​private int sex;​private String levels;​private String section;​private String spe;​private String phone;​private Curappointment cuu;​private Appointment app;​private Set<Pinqueue> pin = new HashSet<Pinqueue>();​private Set<History> history = new HashSet<History>();​public Integer getDid() {​return did;​}​public void setDid(Integer did) {​this.did = did;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}​public String getPassword() {​return password;​}​public void setPassword(String password) {​this.password = password;​}​public int getAge() {​return age;​}​public void setAge(int age) {​this.age = age;​}​public int getSex() {​return sex;​}​public void setSex(int sex) {​this.sex = sex;​}​public String getLevels() {​return levels;​}​public void setLevels(String levels) {​this.levels = levels;​}​public String getSection() {​return section;​}​public void setSection(String section) {​this.section = section;​}​public String getSpe() {​return spe;​}​public void setSpe(String spe) {​this.spe = spe;​}​public String getPhone() {​return phone;​}​public void setPhone(String phone) {​this.phone = phone;​}​public Curappointment getCuu() {​return cuu;​}​public void setCuu(Curappointment cuu) {​this.cuu = cuu;​}​public Appointment getApp() {​return app;​}​public void setApp(Appointment app) {​this.app = app;​}​public Set<Pinqueue> getPin() {​return pin;​}​public void setPin(Set<Pinqueue> pin) {​this.pin = pin;​}​public Set<History> getHistory() {​return history;​}​public void setHistory(Set<History> history) {​this.history = history;​}} |

DoctorQueryHistory.java

| package com.abd.entity;import java.io.Serializable;import java.util.Date;public class DoctorQueryHistory implements Serializable{​private Integer hid;​private String name;​private int age;​private int sex;​private String address;​private String phone;​private String diagnose;​private String description;​private String rx;​private Date fdate;​private Date sdate;​public DoctorQueryHistory() {​super();​}​public DoctorQueryHistory(Integer hid, String name, int age, int sex,​String address, String phone, String diagnose, String description,​String rx, Date date, Date date2) {​super();​this.hid = hid;​this.name = name;​this.age = age;​this.sex = sex;​this.address = address;​this.phone = phone;​this.diagnose = diagnose;​this.description = description;​this.rx = rx;​fdate = date;​sdate = date2;​}​public Integer getHid() {​return hid;​}​public void setHid(Integer hid) {​this.hid = hid;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}​public int getAge() {​return age;​}​public void setAge(int age) {​this.age = age;​}​public int getSex() {​return sex;​}​public void setSex(int sex) {​this.sex = sex;​}​public String getAddress() {​return address;​}​public void setAddress(String address) {​this.address = address;​}​public String getPhone() {​return phone;​}​public void setPhone(String phone) {​this.phone = phone;​}​public String getDiagnose() {​return diagnose;​}​public void setDiagnose(String diagnose) {​this.diagnose = diagnose;​}​public String getDescription() {​return description;​}​public void setDescription(String description) {​this.description = description;​}​public String getRx() {​return rx;​}​public void setRx(String rx) {​this.rx = rx;​}​public Date getFdate() {​return fdate;​}​public void setFdate(Date fdate) {​this.fdate = fdate;​}​public Date getSdate() {​return sdate;​}​public void setSdate(Date sdate) {​this.sdate = sdate;​}} |

DoctorQueryPinqueue.java

| package com.abd.entity;import java.io.Serializable;/************************** Patient Information for doctor appointments inquiry**************************/public class DoctorQueryPinqueue implements Serializable{​private Integer pid;​private String name;​private int age;​private int sex;​private String address;​private String phone;​private Integer qid;​public DoctorQueryPinqueue() {​}​public DoctorQueryPinqueue(Integer pid ,String name, int age, int sex, String address,​String phone,Integer qid) {​super();​this.pid=pid;​this.name = name;​this.age = age;​this.sex = sex;​this.address = address;​this.phone = phone;​this.qid = qid;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}​public int getAge() {​return age;​}​public void setAge(int age) {​this.age = age;​}​public int getSex() {​return sex;​}​public void setSex(int sex) {​this.sex = sex;​}​public String getAddress() {​return address;​}​public void setAddress(String address) {​this.address = address;​}​public String getPhone() {​return phone;​}​public void setPhone(String phone) {​this.phone = phone;​}​public Integer getPid() {​return pid;​}​public void setPid(Integer pid) {​this.pid = pid;​}​public Integer getQid() {​return qid;​}​public void setQid(Integer qid) {​this.qid = qid;​}} |

History.java

| package com.abd.entity;import java.io.Serializable;import java.util.Date;public class History implements Serializable{​private Integer hid;​private Doctor doctor;​private String description;​private String diagnose;​private Patient patient;​private String rx;​private int finished;​private Date fdate;​private Date sdate;​public Integer getHid() {​return hid;​}​public void setHid(Integer hid) {​this.hid = hid;​}​public Doctor getDoctor() {​return doctor;​}​public void setDoctor(Doctor doctor) {​this.doctor = doctor;​}​public String getDescription() {​return description;​}​public void setDescription(String description) {​this.description = description;​}​public String getDiagnose() {​return diagnose;​}​public void setDiagnose(String diagnose) {​this.diagnose = diagnose;​}​public Patient getPatient() {​return patient;​}​public void setPatient(Patient patient) {​this.patient = patient;​}​public String getRx() {​return rx;​}​public void setRx(String rx) {​this.rx = rx;​}​public int getFinished() {​return finished;​}​public void setFinished(int finished) {​this.finished = finished;​}​public Date getFdate() {​return fdate;​}​public void setFdate(Date fdate) {​this.fdate = fdate;​}​public Date getSdate() {​return sdate;​}​public void setSdate(Date sdate) {​this.sdate = sdate;​}} |

Patient.java

| package com.abd.entity;import java.io.Serializable;import java.util.HashSet;import java.util.Set;public class Patient implements Serializable{​private Integer pid;​private String name;​private String username;​private String password;​private int age;​private int sex;​private String address;​private String phone;​private Set<History> history=new HashSet<History>();​private Set<Pinqueue> ps=new HashSet<Pinqueue>();​public Set<Pinqueue> getPs() {​return ps;​}​public void setPs(Set<Pinqueue> ps) {​this.ps = ps;​}​public Set<History> getHistory() {​return history;​}​public void setHistory(Set<History> history) {​this.history = history;​}​public Integer getPid() {​return pid;​}​public void setPid(Integer pid) {​this.pid = pid;​}​public Patient() {​super();​}​public Patient(String name, String username, String password, int age,​int sex, String address, String phone) {​super();​this.name = name;​this.username = username;​this.password = password;​this.age = age;​this.sex = sex;​this.address = address;​this.phone = phone;​}​public String getName() {​return name;​}​public void setName(String name) {​this.name = name;​}​public String getUsername() {​return username;​}​public void setUsername(String username) {​this.username = username;​}​public String getPassword() {​return password;​}​public void setPassword(String password) {​this.password = password;​}​public int getAge() {​return age;​}​public void setAge(int age) {​this.age = age;​}​public int getSex() {​return sex;​}​public void setSex(int sex) {​this.sex = sex;​}​public String getAddress() {​return address;​}​public void setAddress(String address) {​this.address = address;​}​public String getPhone() {​return phone;​}​public void setPhone(String phone) {​this.phone = phone;​}} |

Pinqueue.java

| package com.abd.entity;import java.io.Serializable;import java.util.Date;public class Pinqueue implements Serializable{​private Integer qid;​private Patient patient;​private Doctor doctor;​private int day;​private int ap;​private Date t_date;​public Integer getQid() {​return qid;​}​public void setQid(Integer qid) {​this.qid = qid;​}​public Patient getPatient() {​return patient;​}​public void setPatient(Patient patient) {​this.patient = patient;​}​public Doctor getDoctor() {​return doctor;​}​public void setDoctor(Doctor doctor) {​this.doctor = doctor;​}​public int getDay() {​return day;​}​public void setDay(int day) {​this.day = day;​}​public int getAp() {​return ap;​}​public void setAp(int ap) {​this.ap = ap;​}​public Date getT_date() {​return t_date;​}​public void setT_date(Date t_date) {​this.t_date = t_date;​}} |

hosp.hbm.xml

| <?xml version="1.0"?><!DOCTYPE hibernate-mapping PUBLIC​"-//Hibernate/Hibernate Mapping DTD 3.0//EN"​"http://hibernate.sourceforge.net/hibernate-mapping-3.0.dtd"><hibernate-mapping package="com.abd.entity">​<!-- admin -->​<class name="Admin" table="dl_admin">​<id name="aid" column="aid">​<!-- <generator class="assigned" />-->​<generator class="increment" />​</id>​<property name="username" />​<property name="password" />​<property name="email" />​<property name="phone" />​<property name="name" />​</class>​<!-- Appointment -->​<class name="Appointment" table="dl_appointment">​<id name="did" column="did" type="java.lang.Integer">​<generator class="foreign">​<param name="property">doctor</param>​</generator>​</id>​<property name="sunA"></property>​<property name="sunP"></property>​<property name="monA"></property>​<property name="monP"></property>​<property name="tueA"></property>​<property name="tueP"></property>​<property name="wedA"></property>​<property name="wedP"></property>​<property name="thuA"></property>​<property name="thuP"></property>​<property name="friA"></property>​<property name="friP"></property>​<property name="satA"></property>​<property name="satP"></property>​<!--Mapping and Doctor of-->​<one-to-one name="doctor" class="Doctor" constrained="true" cascade="save-update">​</one-to-one>​</class>​<!-- Curappointment -->​<class name="Curappointment" table="dl_curappointment">​<id name="did" type="java.lang.Integer">​<generator class="foreign">​<param name="property">doctor</param>​</generator>​</id>​<property name="sunA"></property>​<property name="sunP"></property>​<property name="monA"></property>​<property name="monP"></property>​<property name="tueA"></property>​<property name="tueP"></property>​<property name="wedA"></property>​<property name="wedP"></property>​<property name="thuA"></property>​<property name="thuP"></property>​<property name="friA"></property>​<property name="friP"></property>​<property name="satA"></property>​<property name="satP"></property>​<!--VersusDoctorMapping-->​<one-to-one name="doctor" class="Doctor" constrained="true" cascade="save-update">​</one-to-one>​</class>​<!-- Doctor -->​<class name="Doctor" table="dl_doctor" >​<id name="did" column="did">​<generator class="increment" />​</id>​<property name="name" />​<property name="password" />​<property name="age" />​<property name="sex" />​<property name="levels" />​<property name="section" />​<property name="spe" column="specialism" />​<property name="phone" />​<!--VersusappointmentMapping-->​​<one-to-one name="app" class="Appointment" cascade="save-update">​</one-to-one>​<!--VersusCurappointmentMapping-->​             ​<one-to-one name="cuu" class="Curappointment" cascade="save-update">​</one-to-one>​<!--VersusPinqueueMapping-->​<set name="pin" table="dl_pinqueue" inverse="true" cascade="save-update">​<key column="doctor_did"></key>​<one-to-many class="Pinqueue"/>​</set>​<!-- VersusHistoryMapping -->​<set name="history" table="dl_history" inverse="true" cascade="save-update">​<key column="doctor_did"></key>​<one-to-many class="History"/>​</set>​</class>​<!-- History -->​<class name="History" table="dl_history">​<id name="hid" column="hid" type="java.lang.Integer">​<generator class="increment"/>​</id>​<property name="description"></property>​<property name="diagnose"></property>​<property name="rx"></property>​<property name="finished"></property>​<property name="fdate" column="fDate" type="java.sql.Date"></property>​<property name="sdate" column="sDate" type="java.sql.Date"></property>​<!--VersusdoctorMapping-->​<many-to-one name="doctor" column="doctor_did" cascade="save-update">​</many-to-one>​<!--VersuspatientMapping-->​<many-to-one name="patient" column="patient_pid" cascade="save-update">​</many-to-one>​</class>​<!-- Patient -->​<class name="Patient" table="dl_patient">​<id name="pid" column="pid"  type="java.lang.Integer">​<generator class="increment"/>​</id>​<property name="name"></property>​<property name="username"></property>​<property name="password"></property>​<property name="age"></property>​<property name="sex"></property>​<property name="address"></property>​<property name="phone"></property>​<!--VersuspinqueueMapping-->​<set name="ps" table="dl_pinqueue" inverse="true" cascade="save-update">​​  <key column="patient_pid"></key>​  ​​<one-to-many class="Pinqueue"/>​​</set>​<!--VersushistoryMapping-->​<set name="history" table="dl_history" inverse="true" cascade="save-update">​<key column="patient_pid"></key>​<one-to-many class="History"/>​</set>​</class>​<!-- Pinqueue -->​<class name="Pinqueue" table="dl_pinqueue">​<id name="qid" column="qid"  type="java.lang.Integer">​<generator class="increment"/>​</id>​<property name="day"></property>​<property name="ap"></property>​<property name="t_date" column="dat"></property>​<!--VersusdoctorMapping-->​<many-to-one name="doctor" column="doctor_did" cascade="all">​</many-to-one>​<!--VersuspatientMapping-->​<many-to-one name="patient" column="patient_pid" cascade="all">​</many-to-one>​​</class></hibernate-mapping> |

src\com\abd\expt

AlreadyAppointmentException.java

| package com.abd.expt;public class AlreadyAppointmentException extends RuntimeException {​public AlreadyAppointmentException( ){​super();​}        ​public AlreadyAppointmentException( String msg ){​super( msg ) ;​}              ​public AlreadyAppointmentException( Throwable t ){​super( t );​}} |

AppointmentException.java

| package com.abd.expt;public class AppointmentException extends RuntimeException {​public AppointmentException( ){​super();​}        ​public AppointmentException( String msg ){​super( msg ) ;​}              ​public AppointmentException( Throwable t ){​super( t );​}} |

DayAlreadyAppointmentException.java

| package com.abd.expt;public class DayAlreadyAppointmentException extends RuntimeException {​public DayAlreadyAppointmentException( ){​super();​}        ​public DayAlreadyAppointmentException( String msg ){​super( msg ) ;​}              ​public DayAlreadyAppointmentException( Throwable t ){​super( t );​}} |

IdException.java

| package com.abd.expt;public class IdException extends RuntimeException {​public IdException( ){​super();​}        ​public IdException( String msg ){​super( msg ) ;​}              ​public IdException( Throwable t ){​super( t );​}} |

PasswordException.java

| package com.abd.expt;public class PasswordException extends RuntimeException {​public PasswordException( ){​super();​}        ​public PasswordException( String msg ){​super( msg ) ;​}              ​public PasswordException( Throwable t ){​super( t );​}} |

SystemException.java

| package com.abd.expt;public class SystemException extends RuntimeException {​public SystemException( ){​super();​}        ​public SystemException( String msg ){​super( msg ) ;​}              ​public SystemException( Throwable t ){​super( t );​}} |

UsernameException.java

| package com.abd.expt;public class UsernameException extends RuntimeException {​public UsernameException( ){​super();​}        ​public UsernameException( String msg ){​super( msg ) ;​}              ​public UsernameException( Throwable t ){​super( t );​}} |

WrongException.java

| package com.abd.expt;public class WrongException extends RuntimeException {​public WrongException( ){​super();​}        ​public WrongException( String msg ){​super( msg ) ;​}              ​public WrongException( Throwable t ){​super( t );​}} |

src\com\abd\filter

EncodingFilter.java

| package com.abd.filter;import java.io.IOException;import javax.servlet.Filter;import javax.servlet.FilterChain;import javax.servlet.FilterConfig;import javax.servlet.ServletException;import javax.servlet.ServletRequest;import javax.servlet.ServletResponse;import javax.servlet.http.HttpServletRequest;import javax.servlet.http.HttpServletResponse;public class EncodingFilter implements Filter {​@Override​public void destroy() {​// TODO Auto-generated method stub​}​@Override​public void doFilter(ServletRequest request, ServletResponse response,​FilterChain chain) throws IOException, ServletException {​// TODO Auto-generated method stub​HttpServletRequest res = (HttpServletRequest)request;​HttpServletResponse req = (HttpServletResponse)response;​res.setCharacterEncoding("UTF-8");​req.setCharacterEncoding("UTF-8");​chain.doFilter(res, req);​}​@Override​public void init(FilterConfig arg0) throws ServletException {​// TODO Auto-generated method stub​}} |

src\com\abd\util

Util.java

| package com.abd.util;import java.util.StringTokenizer;import com.abd.expt.AppointmentException;public class Util {​/**​ * Doctors reservation information string handling​ *​ * Parameters information​ * dayPattern Reservation information (14 integers, separated by commas or spaces)​ *​ * Return value - an integer array of length 14​ */​public static int[] parseSpDays(String dayPattern)​throws NumberFormatException{​int[] spDays=new int[14];​StringTokenizer token=new StringTokenizer(dayPattern.trim(),", ");​if(token.countTokens() != 14)​throw new AppointmentException();​for(int i=0;i < 14;i++)​spDays[i]=Integer.parseInt(token.nextToken());​return spDays;​}} |

src\res

AppResources.properties

| errors.password=passworderrors.system=systemerrors.username=usernameerrors.id=iderrors.sql=sqlerrors.app=appointmenterrors.io=ioerrors.exception=exceptionerrors.alreadyAppointment=alreadyAppointmenterrors.wrong=wrongerrors.DayAlreadyAppointment=DayAlreadyAppointmenterrors.header=<font color="red">errors.footer=</font> |

AppResources_zh.properties

| errors.password=Your password is incorrect!errors.system=Unknown Exception systemerrors.username=Your password is entered incorrectlyerrors.id=id already existserrors.sql=sql abnormalerrors.app=Appointment abnormalerrors.io=io abnormalerrors.exception=Unknown Exceptionerrors.alreadyAppointment=You have an appointment this Doctorerrors.wrong=Your actions are wrongerrors.DayAlreadyAppointment=Appointment conflicterrors.header=<font color="red">errors.footer=</font> |

src

log4j.properties

| ### direct log messages to stdout ###log4j.appender.stdout=org.apache.log4j.ConsoleAppenderlog4j.appender.stdout.Target=System.outlog4j.appender.stdout.layout=org.apache.log4j.PatternLayoutlog4j.appender.stdout.layout.ConversionPattern=%d{ABSOLUTE} %5p %c{1}:%L - %m%n### direct messages to file hibernate.log ####log4j.appender.file=org.apache.log4j.FileAppender#log4j.appender.file.File=hibernate.log#log4j.appender.file.layout=org.apache.log4j.PatternLayout#log4j.appender.file.layout.ConversionPattern=%d{ABSOLUTE} %5p %c{1}:%L - %m%n### set log levels - for more verbose logging change 'info' to 'debug' ###log4j.rootLogger=warn, stdout#log4j.rootLogger=warn, stdout, file#log4j.logger.org.hibernate=infolog4j.logger.org.hibernate=debug### log HQL query parser activity#log4j.logger.org.hibernate.hql.ast.AST=debug### log just the SQL#log4j.logger.org.hibernate.SQL=debug### log JDBC bind parameters ###log4j.logger.org.hibernate.type=info#log4j.logger.org.hibernate.type=debug### log schema export/update ###log4j.logger.org.hibernate.tool.hbm2ddl=debug### log HQL parse trees#log4j.logger.org.hibernate.hql=debug### log cache activity ####log4j.logger.org.hibernate.cache=debug### log transaction activity#log4j.logger.org.hibernate.transaction=debug### log JDBC resource acquisition#log4j.logger.org.hibernate.jdbc=debug### enable the following line if you want to track down connection ###### leakages when using DriverManagerConnectionProvider ####log4j.logger.org.hibernate.connection.DriverManagerConnectionProvider=trace |

| ![](image_rsrcFVC.jpg) |

| ![](image_rsrcFPX.jpg) |

WebContent\admin

addDoctor.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@ page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Add Doctors Account</title></head><body bgcolor="#FFFFFF"><table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file="../include/admin.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<c:if test="${!empty addDoctor}">​<font color="blue">Doctors successfully added</font>​</c:if>​<c:if test="${empty addDoctor}">​<form method="POST" action="/hospital/allAction.do?method=addDoctor">​<p>Serial number：<input type="text" name="did" value="0"/></p>​<p>Full name：<input type="text" name="name"/></p>​<p>Age：<input type="text" name="age" value="0"/></p>​<p>Sex：<input type="text" name="sex" size="4" maxlength="1" />（0Male，1Female）​</p>​<p>Job title：<input type="text" name="level"/></p>​<p>Specialty：<input type="text" name="spe"/></p>​<p>Phone：<input type="text" name="phone"/></p>​<p>Departments：<input type="text" name="section"/></p>​<p>Reservation information（14Integers, respectively, on Sunday morning, Sunday afternoon, Monday morning ......, separated by commas)：<br /><input type="text" name="spDay" size="50"/></p>​<p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="Add"/></p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr></table></body></html> |

getDoctor.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@ page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Hospital outpatient appointment system - administrator - Doctor Information</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file="../include/admin.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<c:if test="${!empty doctors}">​<p>Query success（Click on the name of the doctor to remove the record）</p>​</c:if>​<table width="100%">​<tr>​<th>Full name</th>​<th>Age</th>​<th>Sex</th>​<th>Job title</th>​<th>Departments</th>​<th>Specialty</th>​<th>Phone</th>​</tr>​<c:forEach var="d" items="${doctors}">​<tr align="center">​              <td><a href="/hospital/allAction.do?method=removeDoctor&did=${d.did}" onclick="return confirm('You sure you want to delete this doctor?');">​                            ${d.name}</a>​              </td>​              <td>${d.age}</td>​              <td>${d.sex}</td>​              <td>${d.levels}</td>​              <td>${d.section}</td>​              <td>${d.spe}</td>​              <td>${d.phone}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

login.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@ page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Administrator Login</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file="../include/admin.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<c:if test="${!empty admin}">​<p>Hello! ${admin}</p>​</c:if>​<c:if test="${empty admin}">​<form method="POST" action="/hospital/allAction.do?method=aLogin">​<p>Username:<input type="text" name="username"/></p>​<p>Password:<input type="password" name="password"/></p>​<p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="LogIn"/></p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

main.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Administrator</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file="../include/admin.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>Please click on the left menu and go to the corresponding page​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

removeDoctor.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@ page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Administrators Remove doctor</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file="../include/admin.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<font color="red">Deleted successfully</font>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

WebContent\Database

hospital.sql

| Already All Details ofhospital.sqlGiven in Starting |

WebContent\doctor

createHistory.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Create a Case</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<c:if test="${!empty bing}">​<p align="center">Transcend medical success</p>​</c:if>​<c:if test="${empty bing}">​   <form action="/hospital/allAction.do?method=createHistory&pid=${param.pid}" method="POST">​<p>Symptom：<input type="text" name="description"/></p>​<p>Diagnosis：<input type="text" name="diagnose"/></p>​<p>Prescription：<input type="text" name="rx"/></p>​<p><input type="submit" value="Create"/></p>​   </form>​   </c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

finishHistory.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>End of treatment</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF"><br>​Successful operation!​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

getPatientHistory.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Query patient case</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<p>Need to operate successfully</p>​<table width="100%">​<tr>​<th></th>​<th></th>​<th>Full name</th>​<th>Age</th>​<th>Sex</th>​<th>Address</th>​<th>Phone</th>​<th>Symptom</th>​<th>Diagnosis</th>​<th>Prescription</th>​<th>Start Time</th>​<th>End Time</th>​</tr>​<c:forEach var="dqh" items="${dqhs}">​<tr align="center">​              <c:if test="${empty dqh.sdate}">​              <td><a href="/hospital/doctor/updateHistory.jsp?hid=${dqh.hid}">Change</a></td>​              <td><a href="/hospital/allAction.do?method=finishHistory&hid=${dqh.hid}">End</a></td>​              </c:if>​              <c:if test="${!empty dqh.sdate}">​              <td></td>​              <td></td>​              </c:if>​              <td>${dqh.name}</td>​              <td>${dqh.age}</td>​              <td>${dqh.sex}</td>​              <td>${dqh.address}</td>​              <td>${dqh.phone}</td>​              <td>${dqh.diagnose}</td>​              <td>${dqh.description}</td>​              <td>${dqh.rx}</td>​              <td>${dqh.fdate}</td>​              <td>${dqh.sdate}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

getPatientInQueue.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Doctors get an appointment patient information</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<p align="center">Click the name of the patient medical record created</p>​<table width="100%" border="0" cellspacing="0" cellpadding="0">​<tr>​<th>Full name</th>​<th>Age</th>​<th>Sex</th>​<th>Contact Address</th>​<th>Tel</th>​<th>Reservation number</th>​</tr>​<c:forEach var="pq" items="${pinqueues1}">​<tr align="center">​<td><a href="/hospital/doctor/createHistory.jsp?pid=${pq.pid}">${pq.name}</a></td>​<td>${pq.age}</td>​<td>${pq.sex}</td>​<td>${pq.address}</td>​<td>${pq.phone}</td>​<td>${pq.qid}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

login.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Doctors Login</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<c:if test="${!empty doctor}">​<p><strong>Hello !! ${doctor.name}</strong></p>​</c:if>​<c:if test="${empty doctor}">​<form action="/hospital/allAction.do?method=dLogin" method="POST">​<p>Full name：<input type="text" name="name"/></p>​<p>Password：<input type="password" name="password"/></p>​<p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="LogIn" /></p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

main.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Doctor</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>Please click on the left menu and go to the corresponding page​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

updateHistory.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Modify patient case</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<c:if test="${!empty upda}">​<p>Update success!</p>​</c:if>​<c:if test="${empty upda}">​<form action="/hospital/allAction.do?method=updatePatientHistory&hid=${param.hid}" method="POST">​<p>Symptom：<input type="text" name="description"/></p>​<p>Diagnosis：<input type="text" name="diagnose"/></p>​<p>Prescription：<input type="text" name="rx"/></p>​<p><input type="submit" value="Confirm change"/></p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

updatePassword.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false"%><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Insert title here</title></head><body bgcolor="#ffffff">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/doctor.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<c:if test="${!empty newPassword}">​<p><strong>Password changed successfully</strong>​</p>​</c:if>​<c:if test="${empty newPassword}">​<form action="/hospital/allAction.do?method=doctorUpdatePassword" method="POST">​<p>New password：<input type="password" name="password"/></p>​<p><input type="submit" value="Change"/></p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

WebContent\include

admin.inc

| <%@ page contentType="text/html; charset=UTF-8"%>​<td width="167" height="290" valign="top" bgcolor="8FBEE8">​<div align="center">​<br>​<p><a href="/hospital/default.jsp">Back to Home</a></p>​<br>​<c:if test="${empty admin}">​<p><a href="/hospital/admin/login.jsp">Login (Admin userï¼‰</a></p>​</c:if>​<c:if test="${!empty admin}">​<p><a href="/hospital/allAction.do?method=getDoctor">View hospital doctor information</a></p>​<p><a href="/hospital/admin/addDoctor.jsp">Add Doctors Account</a></p>​<p><a href="/hospital/allAction.do?method=getDoctor">Remove doctor Account</a></p>​<p><a href="/hospital/allAction.do?method=exit">Log off</a></p>​</c:if>​<br>​<p><a href="/hospital/patient/main.jsp">Patients user</a></p>​<p><a href="/hospital/doctor/main.jsp">Doctors user</a></p>​<br>​</div>​</td> |

ccs.inc

| <style type="text/css"><!--body,td,th {​font-size: 12px;​color: #000033;}a {​font-size: 12px;}a:link {​text-decoration: none;}a:visited {​text-decoration: none;}a:hover {​text-decoration: none;}a:active {​text-decoration: none;}--></style> |

doctor.inc

| <%@ page contentType="text/html; charset=UTF-8"%><td width="167" height="290" valign="top" bgcolor="8FBEE8">​<div align="center">​<br>​<p><a href="/hospital/default.jsp">Back to Home</a></p>​<br>​<c:if test="${empty doctor}">​<p><a href="/hospital/doctor/login.jsp">Login (doctors users)</a></p>​</c:if>​<c:if test="${!empty doctor}">​<p><a href="/hospital/doctor/updatePassword.jsp">Change password</a></p>​<p><a href="/hospital/allAction.do?method=getAppointmentMessage&did=${doctor.did}">To view an appointment patient information</a></p>​<p><a href="/hospital/allAction.do?method=getAppointmentMessage&did=${doctor.did}">Creating records</a></p>​<p><a href="/hospital/allAction.do?method=queryPatientHistory&did=${doctor.did}">View patient records</a></p>​<p><a href="/hospital/allAction.do?method=queryPatientHistory&did=${doctor.did}">Changing patient records</a></p>​<p><a href="/hospital/allAction.do?method=queryPatientHistory&did=${doctor.did}">End of treatment</a></p>​<p><a href="/hospital/allAction.do?method=exit">Log off</a></p>​</c:if>​<br>​<p><a href="/hospital/patient/main.jsp">Patients user</a></p>​<p><a href="/hospital/admin/main.jsp">Administrator User</a></p>​<br>​</div></td> |

head.inc

| ​<table width="770" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<td>&nbsp;</td>​<td width="411">&nbsp;</td>​</tr>​<tr>​<td width="359"><img src="/hospital/images/LEFTBAR.GIF" width="359" height="39"></td>​<td align="right" bgcolor="336CA1">&nbsp;</td>​</tr>​<tr>​<td colspan="2"><img src="/hospital/images/TOPBAR.GIF" width="770" height="69"></td>​</tr>​<tr>​<td colspan="2">​<table width="100%" border="0" cellspacing="0" cellpadding="0" background="IMAGES/but_bg.gif">​<tr>​<td align="right">&nbsp;</td>​</tr>​</table>​</td>​</tr>​</table> |

patient.inc

| <%@ page contentType="text/html; charset=UTF-8"%>​<td width="167" height="290" valign="top" bgcolor="8FBEE8">​<div align="center">​<br>​<p><a href="/hospital/default.jsp">Back to Home</a></p>​<br>​<c:if test="${empty patient}">​<p><a href="/hospital/patient/login.jsp">Login (patient users)</a></p>​<p><a href="/hospital/patient/register.jsp">Registration</a></p>​</c:if>​<c:if test="${!empty patient}">​<p><a href="/hospital/allAction.do?method=allDoctorMessage">View all doctors</a></p>​<p><a href="/hospital/allAction.do?method=getMessage">Reservation</a></p>​<p><a href="/hospital/allAction.do?method=patientMyAppointment&pid=${patient.pid}">Check my reservation</a></p>​<p><a href="/hospital/allAction.do?method=patientMyAppointment&pid=${patient.pid}">Cancel reservation</a></p>​<p><a href="/hospital/allAction.do?method=getDoctorMessage&pid=${patient.pid}">Query doctor information</a></p>​<p><a href="/hospital/allAction.do?method=queryHistory&pid=${patient.pid}">Query records</a></p>​<p><a href="/hospital/allAction.do?method=exit">Log off</a></p>​</c:if>​<br>​<p><a href="/hospital/doctor/main.jsp">Doctors user</a></p>​<p><a href="/hospital/admin/main.jsp">Administrator User</a></p>​<br>​</div>​</td> |

WebContent\patient

cancleAppointment.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Cancel reservation</title></head><body bgcolor="#ffffff">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<p>Cancel the appointment success!</p>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

getAppointmentInfo.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Insert title here</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="100%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<p align="left"><strong>Click cancel the appointment reservation number</strong>​</p>​<table width="100%">​<tr>​<th>Reservation number</th>​<th>Doctor Number</th>​<th>0－Sunday，1－Monday，And so on​</th>​<th>0- Morning，1- Afternoon​</th>​<th>Appointment Date</th>​</tr>​<c:forEach var="pi" items="${pinqueues}">​<tr align="center">​<td><a href="/hospital/allAction.do?method=patientCancleAppointment&qid=${pi.qid}" onclick="return confirm('Really want to cancel this appointment?')">​              ${pi.qid}</a>​</td>​<td>${pi.doctor.did}</td>​<td>${pi.day}</td>​<td>${pi.ap}</td>​<td>${pi.t_date}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr></table></body></html> |

getCurrentDoctorInfo.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Query doctor information</title></head><body bgcolor="#ffffff">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<table width="100%">​<tr>​<th>Physicians Name</th>​<th>Doctor Number</th>​<th>Age</th>​<th>Sex</th>​<th>Job title</th>​<th>Departments</th>​<th>Specialty</th>​<th>Phone</th>​</tr>​<c:forEach var="m" items="${dMessages}">​<tr align="center">​              <td>${m.name}</td>​              <td>${m.did}</td>​              <td>${m.age}</td>​              <td>${m.sex}</td>​              <td>${m.levels}</td>​              <td>${m.section}</td>​              <td>${m.spe}</td>​              <td>${m.phone}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

getDoctorAppointmentInfo.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Doctors reservation information</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<p align="left">Click on "Current number can be reserved" to make an appointment​</p>​<table width="100%"  border="0" cellspacing="0" cellpadding="0">​<tr>​<td></td>​<td>SunM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>SunA&nbsp;&nbsp;&nbsp;&nbsp;</td><td>MonM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>MonA&nbsp;&nbsp;&nbsp;&nbsp;</td><td>TueM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>TueA&nbsp;&nbsp;&nbsp;&nbsp;</td><td>WedM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>WedA&nbsp;&nbsp;&nbsp;&nbsp;</td><td>ThuM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>ThuA&nbsp;&nbsp;&nbsp;&nbsp;</td><td>FriM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>FriA&nbsp;&nbsp;&nbsp;&nbsp;</td><td>SatM&nbsp;&nbsp;&nbsp;&nbsp;</td><td>SatA&nbsp;&nbsp;&nbsp;&nbsp;</td>​</tr>​<tr align="center">​<td>The current number of available appointments</td>​<td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=0&ap=0">​${curappointment.sunA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=0&ap=1">​${curappointment.sunP}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=1&ap=0">​${curappointment.monA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=1&ap=1">​${curappointment.monP}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=2&ap=0">​${curappointment.tueA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=2&ap=1">​${curappointment.tueP}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=3&ap=0">​${curappointment.wedA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=3&ap=1">​${curappointment.wedP}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=4&ap=0">​${curappointment.thuA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=4&ap=1">​${curappointment.thuP}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=5&ap=0">​${curappointment.friA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=5&ap=1">​${curappointment.friP}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=6&ap=0">​${curappointment.satA}</a></td><td>​<a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=6&ap=1">​${curappointment.satP}</a></td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr></table></body></html> |

getDoctorInfo.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Doctors get all</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<c:if test="${!empty doctors1}">​<p align="left"><strong>Click on the name of the doctor check a doctor's appointment information</strong>​</p>​</c:if>​<table width="100%" border="0" cellspacing="0" cellpadding="0">​<tr>​<th>Full name</th>​<th>Serial number</th>​<th>Age</th>​<th>Sex (0 male and 1 female)</th>​<th>Job title</th>​<th>Departments</th>​<th>Specialty</th>​<th>Phone</th>​</tr>​<c:forEach var="dd" items="${doctors1}">​<tr align="center">​              <td><a href="/hospital/allAction.do?method=patientAppointmentMessage&did=${dd.did}">​                                          ${dd.name}​                            </a>​              </td>​              <td>${dd.did}</td>​              <td>${dd.age}</td>​              <td>${dd.sex}</td>​              <td>${dd.levels}</td>​              <td>${dd.section}</td>​              <td>${dd.spe}</td>​              <td>${dd.phone}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

getDoctorInfo2.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Doctors get all</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<c:if test="${!empty doctorss}">​<p align="left"><strong>Click on the name of the doctor check a doctor's appointment information</strong>​</p>​</c:if>​<table width="100%" border="0" cellspacing="0" cellpadding="0">​<tr>​<th>Full name</th>​<th>Serial number</th>​<th>Age</th>​<th>Sex (0 male and 1 female)</th>​<th>Job title</th>​<th>Departments</th>​<th>Specialty</th>​<th>Phone</th>​</tr>​<c:forEach var="dd1" items="${doctorss}">​<tr align="center">​              <td><a href="/hospital/allAction.do?method=patientAppointmentMessage&did=${dd1.did}">​                                          ${dd1.name}​                            </a>​              </td>​              <td>${dd1.did}</td>​              <td>${dd1.age}</td>​              <td>${dd1.sex}</td>​              <td>${dd1.levels}</td>​              <td>${dd1.section}</td>​              <td>${dd1.spe}</td>​              <td>${dd1.phone}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

getHistory.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Patient records</title></head><body bgcolor="#ffffff">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<table width="100%">​<tr>​<th>Doctor No.</th>​<th>Symptom</th>​<th>Diagnosis</th>​<th>Prescription</th>​<th>Treatment has ended (Yes 0 No 1)</th>​<th>Treatment start time</th>​<th>Treatment of End Time</th>​</tr>​<c:forEach var="his" items="${historys}">​<tr align="center">​<td>${his.doctor.did}</td>​<td>${his.description}</td>​<td>${his.diagnose}</td>​<td>${his.rx}</td>​<td>${his.finished}</td>​<td>${his.fdate}</td>​<td>${his.sdate}</td>​</tr>​</c:forEach>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

login.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Patients Login</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<c:if test="${!empty patient}">​<p><strong>Hello!${patient.username}</strong>​</p>​</c:if>​<c:if test="${empty patient}">​<form action="/hospital/allAction.do?method=pLogin" method="POST">​<p>Username:<input type="text" name="username"/></p>​<p>Password:<input type="password" name="password"/></p>​<p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="LogIn"/></p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr></table></body></html> |

main.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Patients user</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                         ​<br>Please click on the left menu and go to the corresponding page​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

makeAppointment.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Reservation</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<p><strong>Congratulations! Appointment success</strong>​</p>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

patientQueryDoctor.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Query doctor</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<br>​<form action="/hospital/allAction.do?method=patientQueryMessage" method="POST">​<p>Departments<select name="section">​                                          <option value="se">Please select&nbsp;&nbsp;</option>​                                          <c:forEach var="section" items="${sections}">​                                          <option value="${section}">${section}</option>​                                          </c:forEach>​                            </select>​</p>​<p>Job title<select name="level">​                                          <option value="le">Please select&nbsp;&nbsp;</option>​                                          <c:forEach var="l" items="${levels}">​                                                        <option value="${l}">${l}</option>​                                          </c:forEach>​                 </select>​</p>​<p>Good at<select name="spe">​                                          <option value="nn">Please select&nbsp;&nbsp;</option>​                                          <c:forEach var="sp" items="${spes}">​                                                        <option value="${sp}">${sp}</option>​                                          </c:forEach>​                 </select>​</p>​<p>Time<select name="day">​                                                        <option value="9">Please select&nbsp;&nbsp;</option>​                                                        <option value="1">Monday</option>​                                                        <option value="2">Tuesday</option>​                                                        <option value="3">Wednesday</option>​                                                        <option value="4">Thursday</option>​                                                        <option value="5">Friday</option>​                                                        <option value="6">On Saturday</option>​                                                        <option value="0">On Sunday</option>​                            </select>​</p>​<p>A&nbsp;&nbsp;P<select name="ap">​                                          <option value="3">Please select&nbsp;&nbsp;</option>​                                          <option value="0">Morning</option>​                                          <option value="1">In the afternoon</option>​              </select>​</p>​<p><input type="submit" value="Confirm"/> </p>​</form>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

register.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><%@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Patient registration</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                                          <br>​<c:if test="${!empty patient}">​<p><strong>Congratulations! Register success</strong></p>​</c:if>​<c:if test="${empty patient}">​<form action="/hospital/allAction.do?method=regsterPatient" method="POST">​<p>Use&nbspFamily&nbspName：<input type="text" name="username"/>​</p>​<p>Close&nbsp&nbsp&nbsp&nbspCode：<input name="password" type="password"/>​</p>​<p>Last name&nbsp&nbsp&nbsp&nbspName：<input name="name" type="text"/>​</p>​<p>Year&nbsp&nbsp&nbsp&nbspAge：<input name="age" type="text"/>​</p>​<p>Sex&nbsp&nbsp&nbsp&nbspDo not：<input name="sex" type="text" size="4" maxlength="1" />（0Male，1Female）​</p>​<p>Contact Address：<input name="address" type="text" minlength="5"/>​</p>​<p>Tel：<input name="phone" type="text" />​</p>​<p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="Registration" />​</p>​</form>​</c:if>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html> |

| ![](image_rsrcFPY.jpg) |

WebContent\WEB-INF

springweb-servlet.xml

| <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE beans PUBLIC "-//SPRING//DTD BEAN//EN""http://www.springframework.org/dtd/spring-beans.dtd"><beans>​<!--  DataSource -->​<bean id="dataSource" class="org.apache.commons.dbcp.BasicDataSource">​<property name="driverClassName">​<value>com.mysql.jdbc.Driver</value>​</property>​<property name="url">​<value>jdbc:mysql://localhost/tarena</value>​</property>​<property name="username">​<value>root</value>​</property>​<property name="password">​<value>root</value>​</property>​</bean>​<!--  session factory -->​<bean id="sessionFactory" class="org.springframework.orm.hibernate3.LocalSessionFactoryBean">​<property name="dataSource">​<ref bean="dataSource" />​</property>​<property name="hibernateProperties">​<props>​<prop key="hibernate.dialect">​org.hibernate.dialect.MySQLDialect​</prop>​<prop key="hibernate.hbm2ddl.auto">create</prop>​<prop key="hibernate.show_sql">true</prop>​<!-- <prop key="hibernate.format_sql">false</prop>-->​</props>​</property>​<property name="mappingResources">​<list>​<value>com/kettas/entity/hosp.hbm.xml</value>​</list>​</property>​</bean>​<!-- dao  hibenate  impl extends HibernateDaoSupport-->​<bean id="adminDao" class="com.abd.dao.impl.AdminDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<bean id="appointmentDao" class="com.abd.dao.impl.AppointmentDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<bean id="curappointmentDao" class="com.abd.dao.impl.CurappointmentDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<bean id="doctorDao" class="com.abd.dao.impl.DoctorDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<bean id="historyDao" class="com.abd.dao.impl.HistoryDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<bean id="patientDao" class="com.abd.dao.impl.PatientDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<bean id="pinqueueDao" class="com.abd.dao.impl.PinqueueDaoImpl">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<!--target-->​<bean id="adminTarget" class="com.abd.biz.impl.AdminBizImpl">​<property name="daoA">​<ref bean="adminDao" />​</property>​<property name="daoB">​<ref bean="doctorDao" />​</property>​<property name="daoC">​<ref bean="appointmentDao" />​</property>​<property name="daoD">​<ref bean="curappointmentDao" />​</property>​</bean>​<bean id="patientTarget" class="com.abd.biz.impl.PatientBizImpl">​<property name="daoD">​<ref bean="doctorDao" />​</property>​<property name="daoC">​<ref bean="curappointmentDao" />​</property>​<property name="daoP">​<ref bean="patientDao" />​</property>​<property name="daoH">​<ref bean="historyDao" />​</property>​<property name="daoQ">​<ref bean="pinqueueDao" />​</property>​</bean>​<bean id="doctorTarget" class="com.abd.biz.impl.DoctorBizImpl">​<property name="daoD">​<ref bean="doctorDao" />​</property>​<property name="daoQ">​<ref bean="pinqueueDao" />​</property>​<property name="daoP">​<ref bean="patientDao" />​</property>​<property name="daoH">​<ref bean="historyDao" />​</property>​<property name="daoC">​<ref bean="curappointmentDao" />​</property>​</bean>​<!-- -->​<bean id="transactionManager" class="org.springframework.orm.hibernate3.HibernateTransactionManager">​<property name="sessionFactory">​<ref bean="sessionFactory" />​</property>​</bean>​<!--serviceProxy-->​<bean id="serviceAdmin" class="org.springframework.transaction.interceptor.TransactionProxyFactoryBean">​<property name="proxyInterfaces">​<value>com.abd.biz.AdminBiz</value>​</property>​<property name="target">​<ref bean="adminTarget" />​</property>​<property name="transactionManager">​<ref bean="transactionManager" />​</property>​<property name="transactionAttributes">​<props>​<prop key="*">PROPAGATION_REQUIRED</prop>​</props>​</property>​</bean>​<bean id="serviceDoctor" class="org.springframework.transaction.interceptor.TransactionProxyFactoryBean">​<property name="proxyInterfaces">​<value>com.abd.biz.DoctorBiz</value>​</property>​<property name="target">​<ref bean="doctorTarget" />​</property>​<property name="transactionManager">​<ref bean="transactionManager" />​</property>​<property name="transactionAttributes">​<props>​<prop key="*">PROPAGATION_REQUIRED</prop>​</props>​</property>​</bean>​<bean id="servicePatient" class="org.springframework.transaction.interceptor.TransactionProxyFactoryBean">​<property name="proxyInterfaces">​<value>com.abd.biz.PatientBiz</value>​</property>​<property name="target">​<ref bean="patientTarget" />​</property>​<property name="transactionManager">​<ref bean="transactionManager" />​</property>​<property name="transactionAttributes">​<props>​<prop key="*">PROPAGATION_REQUIRED</prop>​</props>​</property>​</bean></beans> |

struts-config.xml

| <?xml version="1.0" encoding="UTF-8" ?><!DOCTYPE struts-config PUBLIC"-//Apache Software Foundation//DTD Struts Configuration 1.2//EN""http://jakarta.apache.org/struts/dtds/struts-config_1_2.dtd"><struts-config>​<form-beans>​<form-bean name="allForm" type="org.apache.struts.action.DynaActionForm">​<form-property name="username" type="java.lang.String" />​<form-property name="password" type="java.lang.String" />​<form-property name="did" type="java.lang.String" />​<form-property name="name" type="java.lang.String" />​<form-property name="age" type="java.lang.String" />​<form-property name="sex" type="java.lang.String" />​<form-property name="level" type="java.lang.String" />​<form-property name="spe" type="java.lang.String" />​<form-property name="phone" type="java.lang.String" />​<form-property name="section" type="java.lang.String" />​<form-property name="spDay" type="java.lang.String" />​<form-property name="address" type="java.lang.String" />​<form-property name="description" type="java.lang.String" />​<form-property name="diagnose" type="java.lang.String" />​<form-property name="rx" type="java.lang.String" />​<form-property name="day" type="java.lang.String" />​<form-property name="ap" type="java.lang.String" />​</form-bean>​</form-beans>​<action-mappings>​<action parameter="method" path="/allAction" type="com.abd.action.AllAction" name="allForm">​<exception type="com.abd.expt.PasswordException" path="/error.jsp" key="errors.password" />​<exception type="com.abd.expt.SystemException" path="/error.jsp" key="errors.system" />​<exception type="com.abd.expt.UsernameException" path="/error.jsp" key="errors.username" />​<exception type="com.abd.expt.AlreadyAppointmentException" path="/error.jsp" key="errors.alreadyAppointment" />​<exception type="com.abd.expt.WrongException" path="/error.jsp" key="errors.wrong" />​<exception type="com.abd.expt.DayAlreadyAppointmentException" path="/error.jsp" key="errors.DayAlreadyAppointment" />​<exception type="java.io.IOException" path="/error.jsp" key="errors.io" />​<exception type="java.sql.SQLException" path="/error.jsp" key="errors.sql" />​<exception type="com.abd.expt.IdException" path="/error.jsp" key="errors.id" />​<exception type="com.abd.expt.AppointmentException" path="/error.jsp" key="errors.app" />​<exception type="java.lang.Exception" path="/error.jsp" key="errors.exception" />​<forward name="default" path="/default.jsp" />​<forward name="aLogin" path="/admin/login.jsp" />​<forward name="allDoctor" path="/admin/getDoctor.jsp" />​<forward name="removeDoctor" path="/admin/removeDoctor.jsp" />​<forward name="addDoc" path="/admin/addDoctor.jsp" />​<forward name="pLogin" path="/patient/login.jsp" />​<forward name="pRegister" path="/patient/register.jsp" />​<forward name="getDoc" path="/patient/getDoctorInfo.jsp" />​<forward name="getDocss" path="/patient/getDoctorInfo2.jsp" />​<forward name="appoint" path="/patient/getDoctorAppointmentInfo.jsp" />​<forward name="make" path="/patient/makeAppointment.jsp" />​<forward name="getApp" path="/patient/getAppointmentInfo.jsp" />​<forward name="cancle" path="/patient/cancleAppointment.jsp" />​<forward name="current" path="/patient/getCurrentDoctorInfo.jsp" />​<forward name="his" path="/patient/getHistory.jsp" />​<forward name="dLogin" path="/doctor/login.jsp" />​<forward name="upp" path="/doctor/updatePassword.jsp" />​<forward name="getPatientIn" path="/doctor/getPatientInQueue.jsp" />​<forward name="create" path="/doctor/createHistory.jsp" />​<forward name="gph" path="/doctor/getPatientHistory.jsp" />​<forward name="upok" path="/doctor/updateHistory.jsp" />​<forward name="finishOk" path="/doctor/finishHistory.jsp" />​<forward name="pqd" path="/patient/patientQueryDoctor.jsp" />​</action>​</action-mappings>​<message-resources parameter="res.AppResources" />​<plug-in className="org.springframework.web.struts.ContextLoaderPlugIn">​ <set-property property="contextConfigLocation"​                       value="/WEB-INF/springweb-servlet.xml"/></plug-in></struts-config> |

web.xml

| <?xml version="1.0" encoding="UTF-8"?><web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/javaee" xmlns:web="http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" id="WebApp_ID" version="2.5"><display-name>hospital</display-name><welcome-file-list><welcome-file>index.html</welcome-file><welcome-file>index.htm</welcome-file><welcome-file>index.jsp</welcome-file><welcome-file>default.html</welcome-file><welcome-file>default.htm</welcome-file><welcome-file>default.jsp</welcome-file></welcome-file-list><servlet><servlet-name>actionServlet</servlet-name>​<servlet-class>org.apache.struts.action.ActionServlet</servlet-class>​<load-on-startup>1</load-on-startup>​<init-param>​<param-name>config</param-name>​<param-value>/WEB-INF/struts-config.xml</param-value>​</init-param>​<init-param>​<param-name>debug</param-name>​<param-value>2</param-value>​</init-param>​</servlet>​<servlet-mapping>​<servlet-name>actionServlet</servlet-name>​<url-pattern>*.do</url-pattern>​</servlet-mapping>​<filter>​<filter-name>encoding</filter-name>​<filter-class>com.abd.filter.EncodingFilter</filter-class>​</filter>​<filter-mapping>​<filter-name>encoding</filter-name>​<url-pattern>/*</url-pattern>​</filter-mapping></web-app> |

WebContent

default.jsp

| <%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><%@include file="/include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>Hospital outpatient appointment system - Home</title></head><body bgcolor="#FFFFFF">​<table width="777" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF">​<table width="770" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<td>&nbsp;</td>​<td width="411">&nbsp;</td>​</tr>​<tr>​<td width="359"><img src="/hospital/images/LEFTBAR.GIF" width="359" height="39"></td>​<td align="right" bgcolor="336CA1">&nbsp;</td>​</tr>​<tr>​<td colspan="2"><img src="/hospital/images/TOPBAR.GIF" width="770" height="69"></td>​</tr>​<tr>​<td colspan="2">​<table width="100%" border="0" cellspacing="0" cellpadding="0" background="IMAGES/but_bg.gif">​<tr>​<td align="right">&nbsp;</td>​</tr>​</table>​</td>​</tr>​</table>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<td width="167" height="290" valign="top" bgcolor="8FBEE8">​<div align="center">​<br>​<p>Please select:</p>​<br>​<p><a href="/hospital/patient/main.jsp">Patients user</a>​</p>​<p><a href="/hospital/doctor/main.jsp">Doctors user</a>​</p>​<p><a href="/hospital/admin/main.jsp">Administrator User</a>​</p>​<br>​</div>​</td>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">​<div><img height="295" width="600px" src="/hospital/images/pic.jpg"/></div>​<div id="gun" style="overflow:hidden;width:600px;height:170;"><table cellpadding="0" cellspacing="0" border="0"><tr><td id="gun1" valign="top" align="center" ><table cellpadding="2" cellspacing="0" border="0" ><tr><td><a href=""><img src="/hospital/images/3.jpg" width="500" height="130" border="0" /></a></td><td><a href=""><img src="/hospital/images/4.jpg" width="500" height="130" border="0" /></a></td><td><a href=""><img src="/hospital/images/5.jpg" width="500" height="130" border="0" /></a></td><td><a href=""><img src="/hospital/images/6.jpg" width="500" height="130" border="0" /></a></td></tr></table></td><td id="gun2" valign="top"></td></tr></table></div>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html><script>var speed=30//gun2.innerHTML=gun1.innerHTMLfunction Marquee3(){if(gun2.offsetWidth-gun.scrollLeft<=0)gun.scrollLeft-=gun1.offsetWidthelse{gun.scrollLeft++}}var MyMar3 = setInterval(Marquee3,speed)gun.onmouseover=function() {clearInterval(MyMar3)}gun.onmouseout=function() {MyMar3=setInterval(Marquee3,speed)}</script> |

error.jsp

| <%@page isELIgnored="false"%><%@page contentType="text/html;charset=UTF-8" %>  <%@taglib uri="http://struts.apache.org/tags-html" prefix="html"%><h1>​<html:errors />​<br>​<a>Please return</a></h1> |