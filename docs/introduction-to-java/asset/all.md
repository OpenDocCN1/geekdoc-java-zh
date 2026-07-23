![](Images/cover00209.jpeg)

INTRODUCTION TO JAVA

Java Programming for Beginners

Table Of Content

CHAPTER 1: A SMALL HISTORY OF JAVA

CHAPTER 2: INSTALLING JAVA

CHAPTER 3: BASE JAVA LANGUAGE STRUCTURE

CHAPTER 4: JAVA INTERFACES

CHAPTER 5: ANNOTATIONS IN JAVA

CHAPTER 6: VARIABLES AND METHODS

CHAPTER 7: MODIFIERS

CHAPTER 8: IMPORT STATEMENTS AND MORE JAVA LANGUAGE CONSTRUCTS

CHAPTER 9: CHEAT SHEETS

CHAPTER 10: INTEGRATED DEVELOPMENT ENVIRONMENT

CHAPTER 11: JAVA STATEMENTS

CHAPTER 12: LOOPS IN JAVA

CHAPTER 13: ARRAYS

CHAPER 14: STRINGS

CHAPTER 15: LAMBDAS

CHAPTER 16: STREAMS

CHAPTER 17: OPTIONAL

CHAPTER 18: SYSTEM PROPERTIES

CHAPTER 19: JAVA EXERCISES

CHAPTER 1: A SMALL HISTORY OF JAVA

    In 1991, James Gosling of Sun Microsystems (SUN) created a programming language that would be today known as ‘Java’. It was not until 1995 that the first publicly available version of Java (the Java 1.0) was released. While in the year 2006, Java was made available by Sun under the GNU General Public License (GPL). This project which is also called OpenJDLK is continued to this day by Oracle.

     The Oracle Corporation which is now the steermanship for Java purchased Sun Microsystems in the year 2010\. As years went by, the improved and enhanced versions of Java have been published. The latest version being the Java 1.8, or the Java 8.

What Is Java?

     Java is a programming language that can be used to design or develop mobile, desktop or web apps, games etc. It is defined by a set if specifications, and is made up of a programming language, a runtime (Java virtual machine), core libraries, and a compiler. With the Java runtime, software developers can write program codes in languages different from the familiar Java programming language that still runs on the Java virtual machine.

   The Java core libraries and the Java virtual machine is important facets of the Java platform. With Java, the target is writing a program once and then running it on several operating systems.

    The following properties are what make up the Java language:

- Object-oriented programming language:

     All the elements that make up Java are objects, except for the primitive data types.

- Platform independent:

    The Java virtual machine is used as an abstraction by Java programs who also do not access the operating system directly. This accessibility is what makes Java programs highly portable. Any Java program that follows certain rules and complies with standard can run without being modified on supported platforms such as Linux or Windows.

- Automatic memory management:

    The memory allocation and de-allocation for the creation of new objects is managed by Java. There is no direct access to the memory by this program. Objects that do not have existing active pointers are automatically deleted by the so-called garbage collector.

- Compiled and interpreted language:

    All Java source codes are moved into the bytecode format which is not dependent on the target platform. The Java Virtual Machine (JVM) then interprets these bytecode instruction. The JVM contains a so called Hotspot-Compiler which translates performance critical bytecode instructions into native code instructions.

- Strongly-typed programming language:

    The Java programming language is a strongly-typed one. For example, conversion to other objects is relatively strict e.g. must be done most of the time by a programmer, while the types of the used variables must be pre-defined.

N.B: - The Java Syntax is a look-like of the C++.

         - Java is also case-sensitive. For instance, variables called myvalue and myValue would always be treated as different variables. 

Say Hello to the World Java Program

    To begin, the codes in the illustration below can help:

// a small Java program

public  class  HelloWorld  {

 public  static  void  main(String[] args)  {

        System.out.println("Hello World");

 }

}

The Java Virtual Machine

There is a software implementation of a computer that implements and executes problems like a real machine. That software is called the Java Virtual Machine (JVM).

There is a specific operating system that the Java Virtual Machine (JVM) is written for. For instance, a special implementation is needed for Linux, as it is also needed for Windows. Also, the Java compiler converts Java programs into bytecodes, while the Java Virtual Machine helps to interpret the converted bytecode, or to simply execute the Java program.

Java Development Kit vs Java Runtime Environment

   There are two types of a Java distribution. They are the Java Development Kit (JDK), and the Java Runtime Environment (JRE). In the Java Runtime Environment (JRE), you would find the Java class libraries and the Java Virtual Machine (JVM). They both contain the necessary functionality needed to start Java programs.

The JDK additionally contains the development tools necessary to create Java programs. The JDK therefore consists of a Java compiler, the Java virtual machine and the Java class libraries.

Development Process with Java

    Java source files are written as plain text documents. The programmer typically writes Java source code in an Integrated Development Environment (IDE) for programming. An IDE supports the programmer in the task of writing code, e.g., it provides auto-formatting of the source code, highlighting of the important keywords, etc.

    At some point the programmer (or the IDE) calls the Java compiler ( javac ). The Java compiler creates the bytecode instructions. These instructions are stored in .class files and can be executed by the Java Virtual Machine.

Garbage collector

The JVM automatically re-collects the memory which is not referred to by other objects. The Java garbage collector checks all object references and finds the objects which can be automatically released.

While the garbage collector relieves the programmer from the need to explicitly manage memory, the programmer still need to ensure that he does not keep unneeded object references, otherwise the garbage collector cannot release the associated memory. Keeping unneeded object references are typically called memory leaks.

Classpath

The classpath defines where the Java compiler and Java runtime look for .class files to load. These instructions can be used in the Java program.

For example, if you want to use an external Java library you have to add this library to your classpath to use it in your program.

CHAPTER 2: INSTALLING JAVA

Step 1: The recommended Java version

    To install Java, it is highly recommended that the latest long-term version of Java is used. At the time of writing, this is the JAVA 12.

Step 2: Check installation

    Before Java programs can be run,

- one must install the Java runtime environment

- the path environment must have the Java executables

Through the use of a console, one can also test if the JRE is installed correctly. To open a console on Windows: Win+R, enter cmd, then press Enter. Now, enter type in the command below:

[Java – version]

This command would print information about the Java installation if the JRE is installed correctly. If this happens, you can skip the Java installation description. You would also have to install Java if the command line returns the information that the program could not be found.

Step 3: Install Java

There is a native installer that can be found on the [Java website](http://java.com/) provided by Oracle for Microsoft Windows. This native installer has instructions on how to install Java for all supported platforms.

For example:

          Install Java on Ubuntu

          On Ubuntu you can install Java 11 via the following command on the command line. These commands might change over time, if they do not work anymore please Google for the installation.

            # in case you prefer the Oracle Java distribution

           # you can alternatively use the following commands

             sudo add-apt-repository ppa:linuxuprising/java

            sudo apt-get update

           sudo apt-get install oracle-java11-installer

Final step: Check for installation problems and other operating systems

If you discover problems while trying to install Java on your system, go on Google and search for ‘How to install JDK on my OS’. Remember to replace the word ‘OS’ with your current operating system like Ubuntu, Mac OS X or Windows. You are bound to find really helpful links.

CHAPTER 3: BASE JAVA LANGUAGE STRUCTURE

Class

Any template that describes the behavior and date associated with an instance of a class is called a ‘Class’.

The class keyword is used to define a class, and it must always begin with a capital letter. The body of every class is enclosed in the symbols {}.

For example:

package test;  class  MyClass  {  }

Any data associated with a class is stored in variable, while any behavior associated to an object or a class is implemented using methods.

Also, you would find every class in a text file that has the same name as the class plus the .java extension. You can also always define inner classes (classes that are defined inside another class). To do this successfully, you do not need a separate file for this class.

Object

Any instance of a class is called an object. It is the real element that can perform actions and has data. Every object is created based on the definition of a class. The blueprint of every object is the class, meaning that the class describes how every object is created.

Package

Classes are grouped into functional ‘packages’ by Java.

Classes are also typically grouped into logical units by packages. For instance, every graphical view of an application may be placed in the same package known as com.vogella.webapplication.views.

A lot of people commonly use the reverse domain name of a company as the top level package. For instance, a company which owns the domain, backdrops.com would have their Java package started with com.backdrops.

Another reason why packages are used is for the sake of avoiding name collisions of classes. For a name collision to occur, two programmers would have to give the same fully qualified name to a class. A fully qualified name of a class in Java is made up of the package name, then a dot (.), and finally the class name.

If there are no packages, a Java class called Test may be created by the programmer. The same name may be used to create a class by another programmer. Through the use of packages, one can instruct a system on which class to call. For instance, if the Test class is put into the package report by the first programmer, while the second programmer puts his class into package xmlreader, one can differentiate between these classes by making use of the fully qualified name like report.Test or xmlreader.Test.

Inheritance

You can always derive a class from another class. When this happens, the derived class is called a ‘subclass’. Another common occurrence, is that a class is extended by another class.

The class from which a subclass is gotten from is called a ‘superclass’.

When inheritance occurs, it allows a class to inherit the data definitions and the behavior of another class.

Below, you would find codes that demonstrate how a class can extend another class. Bear in mind, that in Java, a class can only extend a maximum of one class.

package com.vogella.javaintro.base;

class  MyBaseClass  {

 public  void  hello()  {

        System.out.println("Hello from MyBaseClass");

 }

}

package com.vogella.javaintro.base;

class  MyExtensionClass  extends MyBaseClass {

}

Object as superclass

In Java, each object implicitly extends the Object class. For every Java object, the following methods are defined by the class:

- equals(o1) allows checking if the current object is equal to o1

- getClass() returns the class of the object

- hashCode() returns an identifier of the current object

- toString() gives a string representation of the current object

Exception handling in Java

There is an event which indicates an error during the runtime of an application in Java. This event is known as the exception. When this occurs, the usual flow of the application’s instructions is disrupted. Generally, exceptions are thrown up in the call hierarchy until they get catched.

![C:\Users\USER\Downloads\exception_throw_callstack.png](Images/image00206.jpeg)

Checked Exceptions

Checked Exceptions are explicitly thrown by methods, which might cause the exception or re-thrown by methods in case a thrown Exception is not caught.

So when calling methods, which throw checked Exceptions the Exceptions have either to be caught or to be re-thrown.

public  void  fileNotFoundExceptionIsCaughtInside()  {

 try  {

        createFileReader();

   }  catch  (FileNotFoundException e)  {

    logger.error(e.getMessage(), e);

 }

}

public  void  fileNotFoundExceptionIsReThrown()  throws

FileNotFoundException {

     createFileReader();

}

public  void  createFileReader()  throws FileNotFoundException {

File file =  new File("/home/Documents/JavaTraining.txt");

 // creating a new FileReader can cause a FileNotFoundException

 new  FileReader(file);

}

N.B: Checked Exceptions are used when an error can be predicted under certain circumstances, e.g., a file which cannot be found.

Runtime Exceptions

Runtime Exceptions are Exceptions, which are not explicitly mentioned in the method signature and therefore also do not have to be catched explicitly.

The most famous runtime exception is the NullPointerException, which occurs during runtime, when a method is invoked on an object, which actually is null.

public  void  causeANullPointerException()  {

String thisStringIsNull = getMessage(false);

 // because the thisStringIsNull object is null

 // this will cause a NullPointerException

  thisStringIsNull.toLowerCase();

}

 public String getMessage(boolean messageIsAvailable)  {

 if(messageIsAvailable)  {

 return message;

 }

 return  null;

}

CHAPTER 4: JAVA INTERFACES

What is an interface in Java?

An interfaces is a type similar to a class and is defined via the interface keyword. Interfaces are used to define common behavior of implementing classes. If two classes implement the same interface, other code which work on the interface level, can use objects of both classes.

Like a class an interface defines methods. Classes can implement one or several interfaces. A class which implements an interface must provide an implementation for all abstract methods defined in the interface.

Abstract, default and static methods in Interfaces

An interface can have abstract methods and _default_ methods. A default method is defined via the default keyword at the beginning of the method signature. All other methods defined in an interfaces are public and abstract; explicit declaration of these modifiers is optional.

Interfaces can have constants which are always implicitly public, static and final.

The following code shows an example implementation of an interface.

package testing;

 public  interface  MyInterface  {

 // constant definition

String URL =  "https://www.vogella.com/";

 // public abstract methods

 void  test();

 void  write(String s);

 // default method

 default String reserveString(String s){

 return  new  StringBuilder(s).reverse().toString();

 }

}

Implementing Interfaces

    A class can implement an interface. In this case it must provide concrete implementations of the abstract interface methods. If you implement a method defined by an interface, you can use @Override annotation. This indicates to the Java compiler that you actually want to implement a method defined by this interface. This way the compiler can give you an error in you mis-typed the name of the method or in the number of arguments. The following class implements the MyInterface interface, it must therefore implement the abstract method and can use the default methods.

package com.vogella.javaintro.base;

public  class  MyClassImpl  implements MyInterface {

 @Override

 public  void  test()  {

 }

 @Override

 public  void  write(String s)  {

 }  public  static  void  main(String[] args)  {

MyClassImpl impl =  new MyClassImpl();

        System.out.println(impl.reserveString("Lars Vogel"));

 }

}

Evolving Interfaces with default methods

    In the past, Java 8 evolving interfaces like adding new methods to an interface was impossible without having to break existing clients. Since Java 8 made default methods available, by simply supplying a default implementation with it, one can now extend an interface without having to break existing clients. The invention of this default method is a binary and compatible change.

    Now, a default method can be overrode to supply a better behavior by a class.

Multiple inheritance of methods

     When a class implements tow interfaces, and the interfaces provide similar default methods, Java will resolve the actual method for the class, through the use of the following rules:

- Subtypes trump supertypes:

     If a method can be inherited by a class from two interfaces, and one of the interface is a subtype of the other, the method from the subtype will be inherited by the class.

- Superclass would always trump the superinterface:

     If a method can be inherited by a class from a superinterface and a superclass, the superclass method would be inherited by the class. This rule is especially true for abstract and concrete superclass methods. The rule also implies that if this method is also declared in the superclass chain, the default methods would not be used.

- In every other case, the default method would have to be implemented by the class.

The listing number 3 is demonstrated in the illustration below:

public  interface  A  {

 default  void  m()  {}

}

public  interface  B  {

 default  void  m()  {}

}

public  class  C  implements A, B {

 @Override

 public  void  m()  {}

}

   When doing your own implementation, you can always call the super method you prefer. As illustrated below:

public  class  C  implements A, B {

 @Override

 public  void  m()  {A.super.m();}

}

Functional Interfaces

Functional interfaces are all kinds of interfaces that have only one method. All functional interfaces come with one particular pro; the fact they can be used alongside lambda expressions. All functional interfaces are automatically identified by the Java compiler. It would only be required that they have only one abstract method. Although, it is very possible to capture the intent of the design with a @FunctionalInterface annotation.

    A lot of default Java interfaces are functional interfaces. For example:

- java.beans.PropertyChangeListener

- java.util.Comparator

- java.io.FileFilter

- java.util.concurrent.Callable

- java.lang.Runnable

There is also a package called the java.util.function which contains functional interfaces that are frequently used present in Java. Some of the java.util.function packages include:

- BinaryOperator<T> - a function from (T, T) to T

- UnaryOperator<T> - a function from T to T

- Supplier<T> - provides an instance of T (such as a factory)

- Function<T, R> - a function transforming a T to a R

- Consumer<T> - an action to be performed on an object

- Predicate<T> - a boolean-valued property of an object

CHAPTER 5: ANNOTATIONS IN JAVA

    All the data you need about a class which is not a member of the programming logic itself is provided by annotations. Annotations do not have a direct effect on the codes that they annotate. The information or data that annotations provide can be used by other components.

Annotations are only present at development time (RetentionPolicy.SOURCE) and can only be preserved at runtime (RetentionPolicy.RUNTIME).

The @Override annotation and override methods

    Any class that extends another class, automatically inherits the methods of that class from its superclass. To successfully change these methods, it can only override them. This means that it can only redeclare the methods. Unless in situations that the class itself is defined as abstract, this procedure is absolutely necessary.

One annotation that can be added to such a method is the @Override annotation. This is because it is used by the Java compiler to see if the annotated method actually overrides a method of an extended class or an interface.

    You can always use the same method signature in the source code of the subclass to override a method. While, you can as well, make use of the @Override annotation to signal to the reader of the source code and the Java compiler that you intend to override a method.

    For illustrations on how you can override a method from a superclass, look at the codes below:

package com.vogella.javaintro.base;

class  MyBaseClass  {

 public  void  hello()  {

         System.out.println("Hello from MyBaseClass");

 }

}

package com.vogella.javaintro.base;

class  MyExtensionClass2  extends MyBaseClass {

 @Override

 public  void  hello()  {

       System.out.println("Hello from MyExtensionClass2");

 }

}

Using the @Override annotation is always good practice. This is because it ensures that the Java compiler validates if you actually overrode all methods as intended and prevents errors.

The @Deprecated annotations

This annotation is one that can be used on a class, constructor, method, or field, and is one that indicates that an element is out of date and should not be used anymore. When you add the @Deprecated annotation to the class, it does not automatically deprecate all its methods andfields.

Type annotations

    According to Java, annotations can be placed on any type. The below is an example that assumes that annotations exist:

@NonNull String name;

List<@NonNull String> names;

class  UnmodifiableList<T>  implements  @Readonly List<@Readonly T>  {...}

email =  (@Email String) input;

new  @Information MyObject();

void  doSomething()  throws  @ImportantForMe MyException {  ...  }

CHAPTER 6: VARIABLES AND METHODS

Variable

 The Java program stores values during the runtime of the program through the help of variables.

     Variables are either ‘primitive or reference variables’. Primitive valuables contain the value, while reference variables contain a pointer (or reference) to the object. This means that when comparing two reference variables, one is actually comparing if the both of them point to the same object.

    Make use of the object1.equals (object 2) method call to identify if objects contain the same data.

Instance variable

    Instance variables are those variables that are associated with an instance of a class (or an object). Access works over these objects.

All instance variables can be marked transient or final, and can have any access control. And, the moment an instance variable is marked as final, it cannot be changed after a value has been assigned to it.

Local variable

Declarations that are local (or stack) variables are those ones that cannot access modifiers. All local variables do not have default values, so they have to be initialized before they can be made use of. In fact, the only modifier available to local variables is the final.

    This modifier defines that after the first assignment, the variable cannot be changed.

Methods

     A block of code that has a return value and parameters is called a ‘method’. A method can always be called on the object.

package com.vogella.javaintro.base;

public  class  MyMethodExample  {

 void  tester(String s)  {

        System.out.println("Hello World");

 }

}

Var-args can be used to declare methods. When this happens, the method declares a parameter which accepts everything from zero to many arguments (syntax: type … name). Only one var-args parameter can be had by a method, and this has to be the last parameter in the method.

Overwriting a superclass method:

  There is a rule that states that states that a method must be of the same arguments and the exact same return parameter. It also states that the return parameter must be the same. ]

Overload methods:

    Any method that has the same name, but different arguments is called an overloaded method. The return type can never be used to overload a method.

Main method

There is public static method with a signature that can be used to start a Java application (check for signature below). This public static method is usually referred to as the main method.

public  static  void  main(String[] args)  {

}

Constructors

    Every class contains one or two constructors that are invoked by the Java runtime to create objects based on the definition of the class. Except for the fact that they use the name of the class and come with no return type, constructor declarations look like method declarations.

    Every class can have several constructors with varying parameters. In the illustration below, the constructor of the class expects a parameter:

package com.vogella.javaintro.base;

public  class  MyConstructorExample2  {

    String s;

 public  MyConstructorExample2(String s)  {

 this.s  = s;

 }

}

At least one constructor must be defined by each class. The compiler would implicitly add a constructor if no explicit constructor is defined in the Java source file. The constructor of the super class would always be called implicitly in every case that the class is sub-classed.

    In the illustration below, the definition of the constructor without parameters (also popularly called the empty constructor) is not necessary. The compiler would always create one, if it is not specified.

package com.vogella.javaintro.base;

public  class  MyConstructorExample  {

 // unnecessary: would be created by the compiler if left out

 public  MyConstructorExample()  {

 }

}

To create a constructor, the naming convention goes like this: classname (Parameter p1, …) { }. All objects are created based on a constructor. Before anything can be done with an object, the constructor method is the first statement that would be called.

CHAPTER 7: MODIFIERS

Access modifiers

In Java, you would find three access modifiers available. They are the private, the protected, and the public. You would also find four access levels available. They are: the private, the default, the public, and the protected.

All these levels define how the corresponding element is visible to other components. An example of when something is declared public is when classes or methods are freely created or called by other Java objects. While, an example of when something is declared private is when maybe a method can only be accessed within the class in which it is declared.

The access levels default and protected are very similar. A default class can be accessed only through the same package, while a protected class can be accessed from the package and sub-classes from outside the package.

For illustration on their visibility, look at the table below:

Access Level Table

| Modifier | Class | Package | Subclass | World |
| Private | Y | N | N | N |
| No modifier | Y | Y | N | N |
| Protected | Y | Y | Y | N |
| Public | Y | Y | Y | Y |

Other modifiers

- Final methods:

These ones cannot be overwritten in a subclass

- Abstract method:

These ones have no method body

- Synchronized method:

Thread safe, can have any access control, and be final.

- Native methods:

These ones are codes that depend solely on platforms. They apply only to methods.

- Strictfp:

These ones are methods or classes.

CHAPTER 8: IMPORT STATEMENTS AND MORE JAVA LANGUAGE CONSTRUCTS

Usage of import statements

To access a Java class, you always have to use its full qualified name. Meaning, the package name plus a, followed by the class name.

Import statements can also be added to your class file. These statements would allow you to use the related classes in your code without the package qualifier.

Static imports

Public static members (whether methods or fields) of another class can only be used in Java code without a class reference when allowed by static imports.

A typesafe mechanism is provided by this feature to include constants into code. Code readability is also improved, while Java API designers are allowed to write a concise API.

MORE JAVA LANGUAGE CONSTRUCTS

Class variables and class methods

Class variables and class methods are associated with the class, and not with an instance of the class like the objects. You can use the dot (.) and the classname followed by the class variable name or class method, to refer to these elements

The static keyword is used to declare class variables and class methods. Class variables are also referred to as static fields or static variables, while class methods are also referred to as static methods.

A classic example on how to use a static field is printIn of the following statement: System.out.println("Hello World"). Were out is a static field, an object of type PrintStream and you call the printIn () method on this object.

If you define a static variable, the Java runtime environment associates one class variable for a class no matter how many instances (objects) exist. The static variable can therefore be seen as a global variable.

The following code demonstrates the usage of static fields:

package com.vogella.javaintro.base;

public  class  MyStaticExample  {

 static String PLACEHOLDER =  "TEST";

 static  void  test()  {

        System.out.println("Hello");

 }

}

package com.vogella.javaintro.base;

public  class  Tester  {

 public  static  void  main(String[] args)  {

        System.out.println(MyStaticExample.PLACEHOLDER);

        MyStaticExample.test();

 }

}

If a variable should be defined as constant, you declare it with the static and the final keyword.

The static method runs without any instance of the class, it cannot directly access non-static variables or methods.[](https://www.vogella.com/tutorials/JavaIntroduction/article.html#javadef_abstractclass)

### [Abstract class and methods](https://www.vogella.com/tutorials/JavaIntroduction/article.html#javadef_abstractclass)

A class and method can be declared as abstract. Anabstract class cannot be directly instantiated.

If a class has at least one method, which only contains the declaration of the method, but not the implementation, then this class is abstract and cannot be instantiated. Sub-classes need then to define the methods except if they are also declared as abstract.

If a class contains an abstract method, it also needs to get defined with the abstract keyword.

The following example shows an abstract class:

package com.vogella.javaintro.base;

public  abstract  class  MyAbstractClass  {

 abstract  double  returnDouble();

}

## CHAPTER 9: CHEAT SHEETS

During your Java development time, you will be asked to do certain things, like creating a local variable. The following can be used as a reference for such tasks, so that you how what you have to do.

### [Working with classes](https://www.vogella.com/tutorials/JavaIntroduction/article.html#cheatsheets_class)

While programming Java you have to create several classes, methods, instance variables. The following uses the package test.

| What to do | How to do it |
| Create a new class called MyNewClass. | package test;public  class  MyNewClass  {} |
| Create a new attribute (instance variable) called var1 of type String in the MyNewClass class | package test;public  class  MyNewClass  { private String var1;} |
| Create a Constructor for your MyNewClass class which has a String parameter and assigns the value of it to the var1 instance variable. | package test;public  class  MyNewClass  { private String var1; public  MyNewClass(String para1)  {var1 = para1; // or this.var1= para1; }} |
| Create a new method called doSomeThing in your class which does not return a value and has no parameters. | package test;public  class  MyNewClass  { private String var1; public  MyNewClass(String para1)  {var1 = para1; // or this.var1= para1; } public  void  doSomeThing()  { }} |
| Create a new method called doSomeThing2 in your class which does not return a value and has two parameters, an int and a Person | package test;public  class  MyNewClass  { private String var1; public  MyNewClass(String para1)  {var1 = para1; // or this.var1= para1; } public  void  doSomeThing()  { } public  void  doSomeThing2(int a, Person person)  { }} |
| Create a new method called doSomeThing3 in your class which returns an int value and has three parameters, two Strings and a Person. | package test;public  class  MyNewClass  { private String var1; public  MyNewClass(String para1)  {var1 = para1; // or this.var1= para1; } public  void  doSomeThing()  { } public  void  doSomeThing2(int a, Person person)  { } public  int  doSomeThing3(String a, String b, Person person)  { return  5;  // any value will do for this example }} |
| Create a class called MyOtherClass with two instance variables. One will store a String, the other will store a Dog. Create getter and setter for these variables. | package test;public  class  MyOtherClass  {    String myvalue;    Dog dog; public String getMyvalue()  { return myvalue; } public  void  setMyvalue(String myvalue)  { this.myvalue  = myvalue; } public Dog getDog()  { return dog; } public  void  setDog(Dog dog)  { this.dog  = dog; }} |

Working with local variable

One must always declare local variable in a method. Take a look at the illustration below:

| Action to take | How to go about it |
| --- | --- |
| A (local) variable of type String should be declared. | String variable1; |
| A (local) variable of type String should be declared, with a ‘Test’ assigned to it. | String variable2 =  "Test"; |
| A (local) variable of type Person should be declared. | Person person; |
| A (local) variable of type String should be declared, a new Object should be created, and a variable should be assigned to this object. | Person person =  new Person(); |
| An array of type String should be declared. | String array[]; |
| An array of type Person should be declared, while an array that can hold 5 persons should be created for this variable. | Person array[]=  new Person[5]; |
| 5 should be assigned to the int variable var1 (it should have already been declared). | var1 =  5; |
| The existing variable pers2 should be assigned to the existing variable pers1. | pers1 = pers2; |
| An Arraylist variable that can hold objects of type Person should be declared. | ArrayList<Person> persons |
| A new ArrayList with objects of type Person should be created and assigned to the existing variable persons. | persons =  new ArrayList<Person>(); |
| An ArrayList variable that can hold objects of type Person should be declared, and a new Object should be created for it. | ArrayList<Person> persons =  new ArrayList<Person>(); |

CHAPTER 10: INTEGRATED DEVELOPMENT ENVIRONMENT

    In the last chapter, we discussed the steps needed to create and compile a Java program on the command line. However, we have got even better news: You would find lots of ease of use functionality for when creating Java programs if you use a Java Integrated Development Environment (IDE).

    And, it only gets better. There are numerous other very powerful IDEs that can be used, such as, the Eclipse IDE. If you want to learn the procedures needed to use the Eclipse IDE, you can go and Google and search for the Eclipse IDE Tutorial.

    You would also find out that the last description makes use of the phrase: ‘Create a Java project called ……’ This description refers to creating a Java project in Eclipse. If you have been making use of a different IDE, always ensure that you follow the necessary steps in that IDE.

TYPE CONVERSION

    If variables of different types are made use of, Java would require an explicit conversion for certain types. In the illustrations below, you would find examples for this conversion.

Conversion to string

   To convert from other types to Strings, the following can be used:

// Convert from int to String

String s1 = String.valueOf ( 10 ); // "10"

// Convert from double to String

String s2 = String.valueOf ( Math.PI ); // "3.141592653589793"

// Convert from boolean to String

String s3 = String.valueOf ( 1 < 2 ); // "true"

// Convert from date to String

String s4 = String.valueOf ( new Date() ); // "Tue Jun 03 14:40:38 CEST 2003"\

### [Conversion from String to Number](https://www.vogella.com/tutorials/JavaIntroduction/article.html#conversion_tonumber)

// Conversion from String to int

int i = Integer.parseInt(String);

// Conversion from String to float

float f = Float.parseFloat(String);

// Conversion from String to double

double d = Double.parseDouble(String);

The local settings does not play a very significant role in the conversion from string to number. For example, the English notification for number is always used. A correct number format in this notification is ‘8.20’. An error would occur if the German number ‘8.20’ is used.

The NumberFormat class would have to be used to convert from a German number. There would be only one problem though; when the value is, for instance, 98.00, the NumberFormat class would create a Long that cannot be casted to Double. This is why the complex conversion class below should be used.

private Double convertStringToDouble(String s) {

        Locale l = new Locale("de", "DE");

        Locale.setDefault(l);

        NumberFormat nf = NumberFormat.getInstance();

        Double result = 0.0;

        try {       

                if(Class.forName("java.lang.Long").isInstance(nf.parse(s)))

{

            result =

Double.parseDouble(String.valueOf(nf.parse(s)));

            } else {

               result = (Double) nf.parse(new String(s));

            }

         } catch (ClassNotFoundException e1) {

             e1.printStackTrace();

         } catch (ParseException e1) {

             e1.printStackTrace();

         } return result;

}

### [Double to int](https://www.vogella.com/tutorials/JavaIntroduction/article.html#conversion_toint)

To convert double to int, you this:

int i = (int) double;

### [SQL Date conversions](https://www.vogella.com/tutorials/JavaIntroduction/article.html#conversion_sqldate)

### The following should be used to convert a Date to a SQL date:

package test;

import  java.text.DateFormat;

import  java.text.ParseException;

import  java.text.SimpleDateFormat;

public  class  ConvertDateToSQLDate  {

private  void  convertDateToSQL(){

SimpleDateFormat template =

 new  SimpleDateFormat("yyyy-MM-dd");

           java.util.Date enddate =

 new java.util.Date("10/31/99");

           java.sql.Date sqlDate =

             java.sql.Date.valueOf(

                               template.format(enddate));

}

 public  static  void  main(String[] args)  {

 ConvertDateToSQLDate date =  new ConvertDateToSQLDate();

 date.convertDateToSQL();

 }

}

CHAPTER 11: JAVA STATEMENTS

  Certain statements are defined with predefined meanings with the Java language. In this chapter, you would find descriptions that lists some of them.

If-then and if-then-else

The if-then statement is a control flow statement. Only when a test specified by the ‘if’ part evaluates to ‘true’, is a block of code executed. If however, the ‘if’ part evaluates to false, the optional else block would be executed.

A class with two methods is illustrated by the following example code. The usage of if-then is demonstrated in the first method, while the usage of if-then-else is demonstrated in the second method.

Switch

Several alternatives can be handled by the switch statement if they are all factored on the same constant value.

switch  (expression)  {

 case  constant1:

         command;

 break;  // will prevent that the other cases or also executed

 case  constant2:

         command;

 break;

 ...

 default:

}

// Example:

switch  (cat.getLevel())  {

 case  0:

 return  true;

 case  1:

 if  (cat.getLevel()  ==  1)  {

 if  (cat.getName().equalsIgnoreCase(req.getCategory()))  {

 return  true;

 }

 }

 case  2:

 if  (cat.getName().equalsIgnoreCase(req.getSubCategory()))  {

 return  true;

 }

}

// you can also use the same logic for different constants

 public  static  void  main(String[] args)  {

 for  (int i =  0; i <  6; i++)  {

 switch  (i)  {

 case  1:

 case  5:

               System.out.println("Hello");

 break;

 default:

               System.out.println("Default");

 break;

 }

 }

 }

}

Boolean Operations

To see if two references refer to the same object or to compare two primitives, you can use ==. You can also use the equals () method to see if two different objects are equal.

There are short circuit methods that terminate the moment the result of an evaluation is made clear. Examples are && and ||.

In illustrations, (true || …) is always true, while (false && …) is always depicted as false.

E.g.: (var ! =null && var.method1 …) makes sure that var is not null before the original check is done.

| A BOOLEAN OPERATIONS TABLE |
| --- |
| Operations | Description |
| --- | --- |
| == | This stands for ‘is equal’.When objects are involved, the system will check whether the reference variable points to the same object. The content of the objects will not be compared! |
| && | This stands for ‘And’ |
| != | This stands for ‘is not equal, similar to ==.’ |
| a.equals(b) | This is used for checking whether ‘string a equals b’ |
| a.equalsIgnoreCase(b) | This is used for checking whether ‘string a equals b while ignoring lower cases’ |
| If (value ? false : true) {} | This is a negotiation: return true if value is not true. |
|  |  |

CHAPTER 12: LOOPS IN JAVA

The ‘for loop’

There is a repetition control structure that enables you to write a block of code that can be executed a stipulated number of times. That structure is referred to as the ‘for loop’.

The syntax of the structure can be seen below:

for(initialization; expression; update_statement)

{

 //block of code to run

}

For an example of a ‘for loop’ structure, check out the illustration below:

public  class  ForTest  {

 public  static  void  main(String args[])  {

 for(int i =  1; i <  10; i = i+1)  {

        System.out.println("value of i : "  + i );

 }

 }

}

N.B: An improved ‘for loop’ is available for collections and arrays. You would find the loop covered in the array description.

The while loop

There is another repetition control structure that only allows one to write a block of code that is executed until a specific condition comes out false. That structure is referred to as the ‘while loop’. Below is the syntax of that structure:

while(expression)

{

 // block of code to run

}

For an example of a ‘while loop’, look at the example below:

public  class  WhileTest  {

 public  static  void  main(String args[])  {

 int x =  1;

 while  (x <  10)  {

            System.out.println("value of x : "  + x);

            x++;

 }

 }

}

### [The do while loop](https://www.vogella.com/tutorials/JavaIntroduction/article.html#javalang_dowhile)

The do-while loop is similar to the while loop, with the exception that the condition is checked after the execution. The syntax is the following.

do

{

 // block of code to run

}  while(expression);

The following shows an example for a do-while loop.

public  class  DoTest  {

 public  static  void  main(String args[])  {

 int x =  1;

 do  {

            System.out.println("value of x : "  + x);

            x++;

 }  while  (x <  10);

 }

}

CHAPTER 13: ARRAYS

Arrays in Java

An array is a container object that holds a fixed number of values of a single type. An item in an array is called an element. Every element can be accessed via an index. The first element in an array is addressed via the 0 index, the second via 1, etc.

package com.vogella.javaintro.array;

public  class  TestMain  {

 public  static  void  main(String[] args)  {

 // declares an array of integers

 int[] array;

 // allocates memory for 10 integers

array =  new  int[10];

 // initialize values

        array[0]  =  10;

 // initialize second element

        array[1]  =  20;

        array[2]  =  30;

        array[3]  =  40;

        array[4]  =  50;

        array[5]  =  60;

        array[6]  =  70;

        array[7]  =  80;

        array[8]  =  90;

        array[9]  =  100;

 }

}

### [](https://www.vogella.com/tutorials/JavaIntroduction/article.html#arrays_forloop)

### [Enhanced for loop for Arrays and Collections](https://www.vogella.com/tutorials/JavaIntroduction/article.html#arrays_forloop)

Arrays and collections can be processed with a simpler for loop.

for(declaration : expression)

{

 // body of code to be executed

}

The following code demonstrates its usage.

package com.vogella.javaintro.array;

public  class  TestMain  {

 public  static  void  main(String[] args)  {

 // declares an array of integers

 int[] array;

 // allocates memory for 10 integers

array =  new  int[10];

 // initialize values

        array[0]  =  10;

 // initialize second element

        array[1]  =  20;

        array[2]  =  30;

        array[3]  =  40;

        array[4]  =  50;

        array[5]  =  60;

        array[6]  =  70;

        array[7]  =  80;

        array[8]  =  90;

        array[9]  =  100;

 int idx =  0;

 for  (int i : array)  {

            System.out.println("Element at index "  + idx +  " :" + i);

            idx++;

 }

 }

}

CHAPER 14: STRINGS

Strings in Java

The String class represents character strings. All string literals, for example, "hello", are implemented as instances of this class. An instance of this class is an object. Strings are immutable, e.g., an assignment of a new value to a String object creates a new object.

To concatenate Strings use a StringBuilder.

StringBuilder sb =new StringBuilder("Hello ");

sb.append("Eclipse");

String s = sb.toString();

Avoid using StringBuffer and prefer StringBuilder. StringBuffer is synchronized and this is almost never useful, it is just slower.

String pool in Java

For memory efficiency Java uses a String pool. The string pool allows string literals to be reused. This is possible because strings in Java are immutable.

If the same string literal is used in several places in the Java code, only one copy of that string is created.

Whenever a String object is created and gets a string literal assigned the string pool is used. For example, String s = "constant". However, the new operator forces a new String copy to be allocated, for example, in String s = new String("constant");.

Compare strings in Java

The s1.equals (s2) method should be used when the string objects s1 and s2 are compared. Any string comparison that has == is not correct, this is because == checks for object reference equality.

Sometimes, since Java uses a String pool, == would give the actual result. The illustration below would work with ==. It should work as expected.

String a =  "Hello";

String b =  "Hello";

if  (a==b)  {

 // if statement is true

 // because String pool is used and

 // a and b point to the same constant

}

The illustration below however, would fail:

String a =  "Hello";

String b =  new String("Hello");

if  (a==b)  {

}  else  {

 // if statement is false

 // because String pool is used and

 // a and b point to the same constant

}

Working with strings

The most common string operations are listed in the table below:

| Command | Description |
| --- | --- |
| "Testing".equals(text1); | This implies that, if text1 is equal to ‘Testing’, return true. It is a case-sensitive check. |
| "Testing".equalsIgnoreCase(text1); | This implies that, if text1 is equal to ‘Testing’, return true. However, it is not a case-sensitive check. For instance, it would also be correct for ‘testing’. |
| StringBuilder str1 = new StringBuilder(); | This stands for ‘defining a new StringBuilder that allows ‘Strings’ to be efficiently added. |
| str.charat(1); | This stands for ‘returning the character at position 1’. (Remember: strings are arrays of chars that start with 0). |
| str.substring(1); | The first characters are removed by this command. |
| str.substring(1, 5); | The substring from the second to the fifth character are gotten by this command. |
| str.indexOf("Test") | This command looks for the String "Test" in String str, and returns the index of the first occurrence of the stipulated string. |
| str.lastIndexOf("ing") | The index of the last occurrence of a stipulated String ‘ing’ in the String ‘str’ is returned by this command. |
| str.endsWith("ing") | This command would return true, if String str ends with String ‘ing’. |
| str.startsWith("Test") | This command would return true, if String str starts with String ‘Test’. |
| str.trim() | Leading and trailing spaces are removed by this command. |
| str.replace(str1, str2) | All occurrences of str1 by str2 is replaced by this command. |
| str2.concat(str1); | This command concatenates str1 at the end of str2. |
| str.toLowerCase() / str.toUpperCase() | The string is converted to lowercase or uppercase by this command. |
| str1 + str2 | This command concatenates str1 and str2 |
| String[] array = myString.split("-"); String[] array2 = myString.split("\\."); | This command splits the character separated myString into an array of strings. Note: Since the split string is a regular expression, when using special characters that have a meaning in regular expressions, ensure that you quote them at all times. In the second instance, we use the ‘.’, so it must be quoted using two backlashes. |

CHAPTER 15: LAMBDAS

What are Lambdas?

Any block of code that has parameters is said to be a lambda expression. Lambdas enable programmers to signify a block of code that should be executed after. They are very important for programming.

As of Java 8, the Java programming language supported lambdas. The ‘functional interface’ is the type of lambda expression in Java. Whenever a method expects a functional interface as a [parameter, it becomes possible to pass in a lambda expression instead.

Uses of lambda expressions

In comparison with other Java programming constructs, the use of lambdas enables programmers to use a condensed syntax. For instance, the Collection interfaces has forEach method that accepts a lambda expression.

Check out this illustration:

List<String> list = Arrays.asList("vogella.com","google.com","heise.de"

)

list.forEach(s-> System.out.println(s));

Making use of method references

Method references can be made use of in a lambda expression. The method that should be called through CalledFrom::method is usually defined by the method reference.

CalledFrom can be * instance::instanceMethod * SomeClass::staticMethod * SomeClass::instanceMethod

Look at the illustration below:

List<String> list =  new ArrayList<>();

list.add("vogella.com");

list.add("google.com");

list.add("heise.de");

list.forEach(System.out::println);

### [Differences between a closure and a lambda expression](https://www.vogella.com/tutorials/JavaIntroduction/article.html#lambdas_closures)

###   Lambdas are supported by the Java programming language, but closures are not. Where a lambda is an anonymous function, for example, it can be defined as parameter, closures are code blocks or code fragments that can be used without being a class or a method. What this means, is that variables that are not defined in their parameters can be accessed by a closure, and that it can also be assigned to a variable.

### CHAPTER 16: STREAMS

### What are streams?

### A sequence of elements that come from a source that supports aggregate operations is referred to as, a stream from the java.util.stream package.

### IntStream

###     Intstreams enable the creation of sequences of primitive int-valued elements that support sequential and parallel aggregate operations.

### Check the illustration below:

package com.vogella.java.streams;

import  java.util.ArrayList;

import  java.util.List;

import  java.util.stream.IntStream;

public  class  IntStreamExample  {

 public  static  void  main(String[] args)  {

 // printout the numbers from 1 to 100

       IntStream.range(1,  101).forEach(s -> System.out.println(s));

 // create a list of integers for 1 to 100

       List<Integer> list =  new ArrayList<>();

 IntStream.range(1,  101).forEach(it -> list.add(it));

 System.out.println("Size "  + list.size());

 }

}

Reduction operations with lambdas and streams

    Streams and lambdas enable the creation of a stream of sequence of primitive int-valued elements that support sequential and parallel aggregate operations.

See illustrations below:

package com.vogella.java.streams;

public  class  Task  {

 private String summary;

 private  int duration;

 public  Task(String summary,  int duration)  {

 this.summary  = summary;

 this.duration  = duration;

 }

 public String getSummary()  {

 return summary;

 }

 public  void  setSummary(String summary)  {

 this.summary  = summary;

 }

 public  int  getDuration()  {

 return duration;

 }

 public  void  setDuration(int duration)  {

 this.duration  = duration;

 }

}

package com.vogella.java.streams;

import  java.util.ArrayList;

import  java.util.List;

import  java.util.Random;

import  java.util.stream.Collectors;

import  java.util.stream.IntStream;

public  class  StreamTester  {

 public  static  void  main(String[] args)  {

Random random =  new Random();

 // Generate a list of random task

        List<Task> values =  new ArrayList<>();

 IntStream.range(1,  20).forEach(i -> values.add(new Task("Task"  + random.nextInt(10), random.nextInt(10))));

 // get a list of the distinct task summary field

 List<String> resultList =

                   values.stream().filter(

t -> t.getDuration()  >  5).map(

t ->

t.getSummary()).distinct().collect(Collectors.toList());

 System.out.println(resultList);

 // get a concatenated string of Task with a duration longer than 5 hours

String collect =

 values.stream().filter(

t -> t.getDuration()  >  5).map(

t ->

t.getSummary()).distinct().collect(Collectors.joining("-"));

 System.out.println(collect);

 }

}

Example of mapping and filtering the content of a list

The illustration below explains how to filter a list through the use of streams, how to perform a mapping operation, and how to use the reduce method to create one final result string from it.

import  java.util.Arrays;

import  java.util.List;

public  class  JavaStreamExample  {

 public  static  void  main(String[] args)  {

       List<String> list = Arrays.asList("Hello",  "Streams",  "Not");

String result = list.stream().

       filter(s->s.contains("e")).

       map(s-> s.toUpperCase()  ).

       reduce("",  (a,b)-> a+  " "  + b);

       System.out.println(result +  "!");

 }

}

Examples of Lambda and streams

  The illustrations below are large examples of how streams can be used. All the codes are factored from the slides on the Goldman Sachs Collection presentation at EclipseCOn 2015\.

For better illustration, the following data model would be assumed:

package com.vogella.java.streams;

public  enum PetType {

     DOG,

     HAMSTER,

 CAT,

 BIRD

}

Example 1:

package com.vogella.java.streams;

public  class  Pet  {

 private PetType type;

 private String name;

 private  int age;

 public  Pet(PetType cat, String name,  int age)  {

 this.type  = cat;

 this.name  = name;

 this.age  = age;

 }

 public PetType getType()  {

 return type;

 }

 public String getName()  {

 return name;

 }

 public  int  getAge()  {

 return age;

 }

}

Example 2:

package com.vogella.java.streams;

import  java.util.ArrayList;

import  java.util.Collection;

import  java.util.List;

import  java.util.stream.Collectors;

public  class  Person  {

 public  Person(String firstName, String lastName)  {

 this.lastName  = lastName ;

 this.firstName  = firstName;

 }

 private String firstName;

 private String lastName;

 private List<Pet> pets =  new ArrayList<>();

 public Person addPet(PetType cat, String name,  int age)  {

 pets.add(new Pet(cat,name, age ));

 return  this;

 }

        public  boolean  hasPet(PetType petType)  {

 return pets.stream().anyMatch(p-> p.getType().equals(petType));

 }

 public  boolean  isNamed(String string)  {

 return  (firstName +  " "  + lastName).equals(string);

 }

 public List<Pet>  getPets()  {

 return pets;

 }

 public Collection<PetType>  getPetTypes()  {

 return pets.stream().map(pet->

pet.getType()).collect(Collectors.toSet());

 }

 public String getFirstName()  {

 return firstName;

 }

 public String getLastName()  {

 return lastName;

 }

}

You can use lambdas and streams to search and filter the data using this data model. The illustration can be seen below:

package com.vogella.java.streams;

import  java.util.Arrays;

import  java.util.Collections;

import  java.util.IntSummaryStatistics;

import  java.util.List;

import  java.util.Map;

import  java.util.Set;

import  java.util.stream.Collectors;

public  class  Example  {

 // examples based on

 // https://www.eclipsecon.org/europe2015/sites/default/files/slides/2015-11-05%20EclipseCon-%20EclipseCollectionsByExample_0.pdf

 private List<Person> people;

 public  static  void  main(String[] args)  {

       List<Person> persons = createData();

 // do any of the persons have a cat?

 boolean result = persons.stream().anyMatch(person ->person.hasPet(PetType.CAT));

 // how many people have cats?

 long catCount = persons.stream().filter(person ->person.hasPet(PetType.CAT)).count();

 System.out.println(catCount);

 // who has a cat?

       List<Person> peopleWithCats = persons.stream().filter(person -> person.hasPet(PetType.CAT))

 .collect(Collectors.toList());

 // who does not have a cat

       List<Person> peopleWithoutCats = persons.stream().filter(person ->  !person.hasPet(PetType.CAT))

 .collect(Collectors.toList());

 // partition people with/without cats

      Map<Boolean, List<Person>> catsAndNoCats = persons.stream()

 .collect(Collectors.partitioningBy(person ->person.hasPet(PetType.CAT)));

 // get the name of Tims cats

Person person = persons.stream().filter(each ->each.isNamed("Tim Taller")).findFirst().get();

 boolean test =  ("Dolly & Spot")  .equals(person.getPets().stream().map(Pet::getName).collect(Collectors.joining(" & ")));

      System.out.println("Tim has Dolly & Spot as cats "  + test);

 // get the set of all pet types

      Set<PetType> allPetTypes = persons.stream().flatMap(p -> p.getPetTypes().stream()).collect(Collectors.toSet());

 System.out.println(allPetTypes);

 // group people by their last name

     Map<String, List<Person>> byLastName = persons.stream().collect(Collectors.groupingBy(Person::getLastName));

      Map<String, List<Person>> byLastNameTargetBag = persons.stream()  .collect(Collectors.groupingBy(Person::getLastName)); System.out.println(byLastName);

 // get the age statistics of pets

      List<Integer> agesList = persons.stream().flatMap(p -> p.getPets().stream()).map(Pet::getAge)  .collect(Collectors.toList());

IntSummaryStatistics stats = agesList.stream().collect(Collectors.summarizingInt(i -> i));

 System.out.println("Min "  + stats.getMin()  +  " Max "  + stats.getMax()  +  " Average "  + stats.getAverage());

 // counts by pet age

      Map<Integer, Long> counts = Collections.unmodifiableMap(persons.stream().flatMap(p -> p.getPets().stream())

 .collect(Collectors.groupingBy(Pet::getAge, Collectors.counting())));

 }

 private  static List<Person>  createData()  {

 return Arrays.asList(

 new  Person("Mary",  "Smith").addPet(PetType.CAT,  "Tabby",  2),

 new  Person("Tim",  "Taller").addPet(PetType.CAT,  "Dolly",  3).addPet(PetType.DOG,  "Spot",  2),

 new  Person("Ted",  "Smith").addPet(PetType.DOG,  "Spike",  4),

 new  Person("Jake",  "Snake").addPet(PetType.DOG,  "Serpy",  1),

 new  Person("Lars",  "Vogel").addPet(PetType.BIRD,  "Twirly",  1),

 new  Person("Harry",  "Hamster").addPet(PetType.HAMSTER,  "Fuzzy",  1).addPet(PetType.HAMSTER,  "Wuzzy",  1)

 );

 }

}

CHAPTER 17: OPTIONAL

You will inevitably receive a NullPointerException (NPE) the moment you access a field, or call a method on an object that is null, or not initialized. To avoid these NPEs, there is a class that can be used. It is called the java.util.optional class.

The java.util.optional class is a tool that helps with indicating that a return value may not be present. This can be viewed directly in the method signature instead of just mentioning that null may be returned in the JavaDoc.

The filter method can be used if and when you want to call a method on an object, or if you want to simply check if there are properties that can be used. A predicate is seen as an argument by the filter method at all times. If there is a value seen in an optional object that corresponds with the predicate, the filter method sends back that value; if not, it simply returns an empty optional object.

    An optional can be created using different methods. See some of them below:

// use this if the object is not null

opt = Optional.of(o);

// creates an empty Optional, if o is null

opt = Optional.ofNullable(o);

// create an empty Optional

opt = Optional.empty();

A programmer can execute some codes on an object by using the ifpresent method, if the code is actually present. If for instance, you have a Todo object, and want to call the getId() method on it, the following codes below can be used to do this:

Todo todo =  new Todo(-1);

Optional<Todo> optTodo = Optional.of(todo);

// get the id of the todo or a default value

optTodo.ifPresent(t-> System.out.println(t.getId()));

A programmer can also transform an object if it is present by using the map method. While the programmer can filter an object for certain values by using the filter method.

Todo todo =  new Todo(-1);

Optional<Todo> optTodo = Optional.of(todo);

// get the summary (trimmed) of todo if the id is higher than 0

Optional<String> map = optTodo.filter(o -> o.getId()  >  0).map(o -> o.getSummary().trim());

// same as above but print it out

optTodo.filter(o -> o.getId()  >  0).map(o -> o.getSummary().trim()).ifPresent(System.out::println);

And finally, the get () method has to be used if a programmer wants to get the actual value of an Optional. However, in scenarios where the Optional is empty, a NoSuchElementException will be thrown. For this NoSuchElementException to be avoided, the orElse or the orElseGet can be used to provide a default in case there is an absence.

// using a String

String s =  "Hello";

Optional<String> maybeS = Optional.of(s);

// get length of the String or -1 as default

int len = maybeS.map(String::length).orElse(-1);

// orElseGet allows to construct an object / value with a Supplier

int calStringlen = maybeS.map(String::length).orElseGet(()->  "Hello".length());

CHAPTER 18: SYSTEM PROPERTIES

Access to the configuration of the current working environment can be provided by the System class. And, they can all be accessed through system.getProperty (‘property_name’), for instance System.getPropery (‘path.separator’).

     The most important properties are described by the list below:

- ‘user.home’ – User home directory = schedule tasks.

- ‘user.dir’ – User working directory.

- ‘line separator’ – Sequence used to separate lines in text files by operating system.

Programmers are allowed to schedule tasks by Java. Tasks that have been scheduled can perform once or several times.

To schedule tasks, you can make use of the java.util.Timer or the java.util.TimerTask. The Timer would then perform the TimeTask implemented by the object based on the given interval.

Check out the illustrations below:

package schedule;

import  java.util.TimerTask;

public  class  MyTask  extends TimerTask {

 private  final String string;

 private  int count =  0;

 public  MyTask(String string)  {

 this.string  = string;

 }

 @Override

 public  void  run()  {

        count++;

        System.out.println(string +  " called "  + count);

 }

}

package schedule;

import  java.util.Timer;

public  class  ScheduleTest  {

 public  static  void  main(String[] args)  {

Timer timer =  new Timer();

 // wait 2 seconds (2000 milli-secs) and then start

        timer.schedule(new MyTask("Task1"),  2000);

 for  (int i =  0; i <  100; i++)  {

 // wait 1 seconds and then again every 5 seconds

            timer.schedule(new MyTask("Task "  + i),  1000,  5000);

 }

CHAPTER 19: JAVA EXERCISES

Exercise 1: Writing, compiling and running a Java program

Test yourself with exercises

Step 1: Write Source Code

The Java program below was developed under Linux through the use of a command line and a text editor. How this can be done on other operating systems should be pretty much the same, but this illustration does not cover it.

- For your Java development, choose or create a new directory that will be used. For this illustration, we use the path \home\vogella\javastarter. For a Microsoft Windows operating system, the path c:\temp\javastarter can be used. In the following illustration, we call this path javadir.

- Open a text editor that supports plain text. For example: Notepad if you are using windows or Gedit if you are using Linux. Then, write the following source code:

// a small Java program

public  class  HelloWorld  {

public  static  void  main(String[] args)  {

System.out.println("Hello World");  }

 }

Warning: Never use a rich editor such as the LibreOffice or Microsoft Word when writing your Java code. If you are not sure, go on Google and search for ‘Plain text editor for <insert your OS>’.

![C:\Users\USER\Downloads\xfirstjava10.png.pagespeed.ic.-9onYaF0Km.png](Images/image00207.jpeg)

- Now, go to your javadir directory, and save the source code with the HelloWorld.java filename. Always remember that the name of a Java source file must always equal the class name (within the source code) and end with the .java extension. In this exercise, the filename should be HelloWorld.java, due to the fact that the class is called HelloWorld.

Step 2: Compiling and running your Java program

- For this step, first of all open a shell for command line access.

Hint: If you have no clue as to how to do this, go on Google and search for ‘How to open a shell under <insert your OS>’.

- Now switch to the javadir directory using the command cd javadir for instance, in the above example through the cd \home\vogella\javastarter command. Use the 1s command (dir under Microsoft Windows) to clarify that the source file is indeed in the directory.

- Now, using the command below, compile your Java source file into a class file:

[javac HelloWorld.java]

- After a while, list the content of the directory again using the 1s or dir command. Now, the directory contains the file HelloWorld.class. Note that you would have successfully compiled your first Java source code into bytecode when you see this file.

Hint: The compiler always puts every class file in the same directory as its source file by default. Using the –d compiler flag, you can specify a separate destination directory.

- Finally, you can now start compiling your Java program. Remember to make sure that you are still in the jardir directory before entering the command below to start your Java program:

[java HelloWorld]

- The system would write "Hello World" on the command line.

![C:\Users\USER\Downloads\xfirstjava20.png.pagespeed.ic.WJun3cLajc.png](Images/image00208.jpeg)

Step 3: Making use of the classpath

- To run the program from another place in your directory, you can always use the classpath.

- All you need to do, is switch to the command line. For example, under Windows Start Run cmd. Switch to a directory of your choice, then type:

[java HelloWorld]

- The system will show an error message if you are not in the directory where the compiled class is stored. The error message could look like this:

Exception in thread "main" java.lang.NoClassDefFoundError: test/TestClass

- Type in the command below to use the class. Substitute ‘mydirectory’ with the directory that contains the test directory. The ‘HelloWorld’ output should be seen again afterwards.

[java -classpath "mydirectory" HelloWorld]

Exercise 2: Creating Java objects and methods

Step 1:  Create a Person class and instantiate it

Create a new Java project called com.vogella.javastarter.exercises1 and a package with the same name.

Create a class called Person.

Add three instance variables to it, one for storing the first name of the person, one for storing the last name and one for storing the age of the Person.

Use the constructor of the Person object to set the values to some default value.

Add a toString method as described by the following coding and solve the TODO. This method is used to convert the object to a String representation.

See illustration below:

@Override

public String toString()  {

 // TODO replace "" with the following:

 // firstName + " " + lastName

 return  "";

}

Create a new class called Main with a public static void main (String [] args). In this method create an instance of the Person class.

Step 2: Use constructor

Add a constructor to your Person class which takes first name, last name and age as parameter. Assign the values to your instance variables.

In your main method create at least one object of type Person and use System.out.println() with the object as parameter.

Step 3: Define getter and setter methods

Define methods which allow you to read the values of the instance variables and to set them. These methods are called setter and getter.

Getters should start with get followed by the variable name whereby the first letter of the variable is capitalized.

Setter should start with set followed by the variable name whereby the first letter of the variable is capitalized.

For example, the variable called firstName would have the getFirstName() getter method and the setFirstName(String s) setter method.

Change your main method so that you create one Person object and use the setter method to change the last name.

Step 4: Create an Address object

Create a new object called Address. The Address should allow you to store the address of a person.

Add a new instance variable of this type in the Person object. Also, create a getter and setter for the Address object in the Person object.