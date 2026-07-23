![](image_rsrcZF.jpg)

# Instantiating Success in Java: The Definitive Guide to Object Oriented Power

Arthur White

# INTRODUCTION

There are a great many things that you will not find in this book and this is the author’s deliberate choice. There are no lengthy descriptions of data structures, frameworks or algorithms, only the language-level features that they all have in common.

As a Java developer, you will find yourself interacting with many different libraries, frameworks and applications. All of them are composed of classes, interfaces, constructors and methods. Even if you count some of these features as advanced, you cannot afford to put off learning them forever. To do any serious programming in Java requires that you interact with these object oriented concepts and understand them.

It would be foolhardy to dive into complicated programs and frameworks expect to simply learn by osmosis. You may have already found that object oriented programming has a tendency to obfuscate where code comes from and what other code acts upon it. Java’s natural verbosity adds to this challenge and gives us plenty of code to read and write that, often times, makes little sense.

When in search of answers, it is most likely you will find one of two things: either a massive, sometimes expensive, encyclopedia of every single feature in the Java language and standard library, or a hodgepodge collection of online tutorials that, despite their brevity, show far more than they tell and leave you guessing as to how it all works. This book is neither.

What you will find in the pages of this book is a focused subset of Java’s features presented with plain examples and explanations. You will learn about constructors, interfaces, generics, abstract methods and how to combine them with each other so that you may understand and use them yourself.

If you are still struggling with the how and why of features that so many aspiring programmers struggle with, then this is the book for you. Wrench apart the irons of confusion and throw off the chains of ambiguity. It is finally time that you Instantiate Success in Java.

# CHAPTER 1: GETTING STARTED

Before you get started, it is important that you have a suitable development environment to follow the examples throughout this book. If you already have an integrated development environment (IDE) and a working copy of the Java Development Kit (JDK), then you may skip to the last section in this chapter and read through some of the naming conventions either as a refresher or primer for the terms and syntax we will encounter ahead.

## 1.1 Choosing an IDE

You will likely find a purpose-build Java IDE comfortable and convenient to use. The first three editors listed here are such pieces of software and each of them are cross platform and free to use. Only one of them charges for premium features, but you will not need those features in order to follow the upcoming code examples.

### Intellij

This IDE from JetBrains is one of the most popular and comes with many convenient features for Java development. The program does charge extra for certain premium plugins, but even without them this editor is still powerful and easy to use.

### Eclipse

Much like JetBrains, the Eclipse foundation makes a series of specialized code editors. The Eclipse Java IDE has plenty of options and plugins in addition to build tool integration and project management features. You will find differences between Eclipse and Intellij come to personal taste more than quality. Both are solid options.

### Netbeans

Netbeans is a part of Java history. It has been around since 1996 and comes from the famed Apache Software Foundation that brought us programs such as Maven, Tomcat, Log4j and many more. Do not let this IDE’s age fool you, it is continually updated and stands as a tried-and-true option for Java developers new and old.

### Other Options

Aside from the more popular choices, you will still have plenty to choose from. One of the most popular IDEs of our time is currently VSCode. If you are already familiar with this editor and would like to use it for Java, then you will need to install a few plugins to integrate build tools such as Maven or Gradle.

The last, and least recommended option for a Java IDE is choose a text editor instead. Programs such as Vim and Emacs support plugins that can make either of them work as a viable option to the other IDEs, but it takes enough time and effort to learn such software that you should consider it as a separate endeavor entirely.

If the options are overwhelming, simply start with Intellij and see how it fits. It is popular for a reason and more than capable for the upcoming examples.

## 1.2 The Java Development Kit

To program Java you will need a copy of the JDK. The features in this book may work with versions as old as 8, though they are written and tested in Java 17, so it is advised that you stick to version 17 or later.

There is more than one way to install your own copy of the JDK. Depending on the IDE you choose, it may simply download one for you when you begin a new project. If this is not the case, then another option is to use your operating system’s package manager to search for the latest version of the JDK available.

Depending on how comfortable you are with a package manager, you may still choose to simply download and install a JDK manually. This is as easy as navigating to the Oracle.com website and choosing the right file for your operating system. The site has both installation and troubleshooting information that you may need.

## 1.3 Naming Conventions

For the code you write to compile and function properly, it must adhere to certain syntactic and logical rules. In order for programmers to recognize each other’s code, we have an additional set of rules and conventions to follow. These conventions work both ways. Once you and know follow them, it is easier to recognize other people’s code and it will be easier for other people to recognize yours should you choose to share or contribute to other projects.

Assuming that code follows common conventions, you may discern a lot of information about it merely from its position in a file and the letter case it is written in.

### Simple Variables

Primitive variables are typically short and descriptive. When a variable’s name grows to multiple words it takes a camel case as in the example below.

int tax;  int taxRate;

There are several so called primitive types in Java such as int, char, byte and others. They take all this naming convention for variable names, though other non-primitive reference type variables also use this same naming convention.

### Methods

Methods are named in camel case like normal variables. In addition, they have a pair of parentheses to hold either arguments or parameters. They are also named after what they do and what they return such as: addReference(), getClass(), or setValue().

int numberGetter() {      return this.number;  }  //this method definition returns an integer.

Methods may also resolve to a value, so in some cases they will appear as an r-value that assigns to a field.

int myInt;  myInt = numberGetter();  //the return value assigns to the variable

### Constant Values

Constant values do not change and that means they must be both static and final. The constant nomenclature comes from the C language, which predates Java.

The convention is to name them in all-caps and with underscores to separate words.

static final float DIAMETER;  static final float CYLINDER_DIAMETER;

### Enumerators

Enums appear either as their file or nested within another class. They serve as a group of constant value choices, so each element is written in all-capital letters.

  public Enum FruitEnum {      APPLES, BANANAS, ORANGES, GRAPEFRUITS  }

When we refer to an enumerated choice, the enumerator’s name and choice connect to each other with a dot operator.

public class Main {            FruitEnum fruit;      //this will hold an enum value            FruitEnum fruit = Fruit.ORANGES;      //the enum choice is assigned as a value      void enumChooser(FruitEnum fruit) {      //this method takes an enum choice as a parameter      }            FruitEnum fruitGetter() {          return FruitEnum.BANANAS;      }      //The return value for this method is an enum  }

Enumerators appear either inside of classes or as their own files. In either case, they take the same naming scheme as classes.

### Classes

Classes and their source files must have identical names and they are case-sensitive. They are named with one or more nouns with the first letter of each word capitalized. This rule extends to other files such as enums, interfaces and abstract classes.

Classes and interfaces also appear as types, so you will also see them in front of variable names, inside method parameters and as return types.

Graphics2D g2d;  //class reference as a field.  String stringGetter() {}  // a class type as a return value  void stringSetter(String st1, String st2) {}  // a class type as two method parameters

Certain primitive values appear in so called wrapper classes. When you see classes with names such as Boolean and Integer, they are indeed classes and follow the correct naming convention.

### Constructors

Although some class constructors are inaccessible, they are all named after their classes and have parentheses. If you name your classes in Pascal case, then it will be easier to tell them apart from methods, especially when they take arguments.

Another way to tell a constructor apart from a method is to observe its return type. Constructors return a reference variable of the class’ type, whereas methods may return any kind of value.

MyClass variable =  new  MyClass();

### Packages

Finally we have packages. Package names appear as imports and in your coding environment as a series of dot-separated names in all lowercase. We will learn far more about packages in the next chapter.

com.domain.appname;

* * *

With this chapter finished, you should have an IDE and JDK ready to use. Also, we have looked at the common naming conventions and how both classes and packages are named. For us to do any kind of programming, we need to compile and load our class files, so the next chapter covers this in more detail.

* * *

# CHAPTER 2: CLASSES AND PACKAGES

Class files are no use to us until they are loaded into the Java Virtual Machine. The way you write your own code will reflect the need for Java’s class loader to locate and load class files. In this chapter, we will learn more about the class loading process, as well as packages and how they combine with classes to form fully qualified names.

## 2.1 What Exactly are Packages?

As convenient as a fully featured IDE is, you will find that it sometimes obfuscates the messier, more technical aspects of Java programming. It is convenient when an IDE compresses long file paths and adds package statements for us, but it can mystify what is actually happening.

Packages are no more than folders with Java class files in them, so long as those class files have package names and the package names match the names of those folders.

Let us assume the following class is inside of your IDE’s source folder under the following file path com/domain/app/. If you are using Windows it will look like this: com\domain\app. If you write the following class file and omit a package statement, then your IDE will likely give you some warning or add the package statement for you.

//this file has no package statement  public class MyClass {  //...  }

In order to make this file part of a package, we must add a package statement. Each folder name is separated by a system agnostic dot operator instead of a forward or backward slash.

package com.domain.app;  public class MyClass {  //...  }

This is all it takes to make a class file package. Build tools and IDEs take raw code and compile it into a set of folders that mirror our source folders. The output is typically stored in a folder marked target.

If our sourcecode is stored like this:

src\main\java\com\domain\app\MyClass.java

Then the output would look like this:

target\com\domain\app\MyClass.class

Your file, folder and package names are all preserved throughout the build and deployment process. Take any .jar file and open it with an archive manager such as Winrar or 7Zip to see folders and class files all arranged neatly as if they were still in a Target folder. The author of that .jar file had their packages and classes preserved so that they would function.

The reason that class files and packages must be kept in proper order is so that the JVM’s class loader may find and load these files. Only then may the application run.

## 2.2 Fully Qualified Names

The JVM uses a combination of three different class loaders in order to search directories and load class files. The first two are mainly out of our control and operate to load class files that are essential to the JVM itself. It is the Application class loader that you will write your class files for.

The application class loader has an environment variable named CLASSPATH and it is always blank. This is so that it may default to the directory where you invoke the virtual machine. From there, it searches for a main method to start the program, then continues to load class files as needed. The way that the application class loader identifies class files is by using their fully qualified names.

A class file’s fully qualified name is formed by a combination of the file’s name and the package that it resides in. The benefit to using fully qualified names instead of merely the class’ name, is that you may have two classes with the same name in two different packages. These names will not conflict with each other because their fully qualified names still differ.

Here is an example of what would cause a naming conflict without fully qualified names.

package com.domain.app;  public class MyClass {  //...  }

The JVM is not looking for MyClass when it searches for classfiles. Instead, it searches for com.domain.app.MyClass. By using this specific name, the JVM knows exactly what to look for and that the class differs from this next one:

package com.otherdomain.library;  public class MyClass {  //...  }

We have made two class files with the same name. This is usually discouraged, but in projects with many files and dependencies it is inevitable. Thankfully, fully qualified names save us the trouble of same-named classes and views the two class files as such:

com.domain.app.MyClass;  com.otherdomain.library.MyClass;

Packages and their namespaces also help us with our import statements. We will look at them next.

## 2.3 Import Statements

Import statements use package names to locate and import class files. Without them, we would have to refer to every class type and constructor with its fully qualified name. Here is an example of how messy your code would look without the help of import statements.

package com.domain.app;  public class MyClass {      public static void main(String[]args) {          com.otherdomain.library.MyClass Obj = new              com.otherdomain.library.MyClass();          /*Note that we can split lines and they will compile, though we must          indent the continuation.*/      }  }

Using fully qualified names like this would eventually make our code cluttered and unreadable. Thankfully import statements help keep things concise.

package com.domainname.app;

import com.otherdomain.library.MyClass;

public class MyClass {

    public static void main(String[]args) {

        MyClass obj = new MyClass();
    }
}

It could be said that when you place a source file in a package, you have effectively renamed it. As far as our class loader and build tools are concerned, this is what we are specifying.

* * *

The JVM needs access to the right classfiles so that it may compile and run our code properly. Once those classes are loaded into the JVM we can start instancing them as objects. That is what we will learn about next.

To recap this chapter:

*   Folders become packages.

*   Packages help form fully qualified names.

*   Fully qualified names prevent name conflicts.

*   The JVM class loaders use fully qualified names to find class files.

*   Even .jar files maintain the same folder structure so as not to invalidate any fully qualified names.

Now that we have some idea of how classes, packages and class loaders work, we will start writing and instancing our own class files.

* * *

# CHAPTER 3: DATATYPES AND OBJECTS

In this chapter, we will finally work with classes and their instances. You are probably somewhat familiar with these topics, but it is easy to overlook the implications of what classes are, especially when it comes to data and types.

Before going any further it is important to note that when you see the term object and class instance the two are one and the same. They both refer to the instantiation of a class into the Virtual Machine’s heap memory area.

## 3.1 How Classes Relate to Objects

We write classes as code, compile the code and load it into the Java Virtual Machine so that it will function as part of a program. Classes are commonly referred to as the blueprints or templates of objects, but not all the code that you see in a class will become an object. Furthermore, sometimes a class’ object gains code from outside the class we wrote.

Another way to think of classes is as units of code that both define and describe user defined datatypes. A class file contains code that tells us:

*   What classes it shares members and data with.
*   Which parts of the class may only exist as objects.
*   How members of a class may access each other.
*   How members of the class may be accessed from the outside.
*   A new user defined datatype.

We must consider this last point if we are to understand objects and reference variables.

### User Defined Types

Java has two broad type categories. The primitive types are simple. Any int, char, short or long is a type, and we give those types names and values when we write them in our programs. The second type category is reference types, the types that we define ourselves.

Every time you name a new class you are naming a new reference type. It is up to you to provide a combination of methods and variables that you want as a reference type, and how that new reference type fits into a larger program or framework.

Below is an example of a simple user defined type. It is a rather simple collection of methods and fields, yet far more complex than a primitive type.

 public class Coordinate {

    private int x;
    private int y;

    public int getX() {
        return x;
    }

    public int getY() {
        return y;
    }

    public void setBothCoords(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

This Coordinate class is a new type of data that can modify its own values. The only way to access those values is through a pair of instance methods, so we must instance this class to use it properly. Let us declare some instance variables for our new Coordinate class.

public class Main {            public static void main(String[]args) {          int a;          int b;          int c;          Coordinate position1;          Coordainte position2;          Coordinate position3;      }  }

For comparison, we have three integer values and three Coordinate reference variables. Just as we use names like a, b and c to differentiate between the integer values they hold, we also need reference variables like position1, position2 and position3 in order to store and access different instances of the Position class that will exist in the JVM’s memory.

## 3.2 Class Instances

You will now see how we instance classes. First, we use the class’ name to declare a type, then add the name of a variable, and finally call the class’ constructor, also named after the class.

//Main.java  public class Main {      public static void main(String[]args) {                    Coordinate position1;          //type ^          Coordainte position2;          //      variable^          Coordinate position3  = new Coordinate();             //                 constructor ^      }     }

Now let us rewrite the above code so that each instance variable takes the address of a different class instance’s memory address. We will also call some of the methods and print out the return values.

//Main.java  public class Main {      public static void main(String[]args) {                    Coordinate position1 = new Coordinate();          Coordainte position2 = new Coordinate();          Coordinate position3  = new Coordinate();                       position1.setBothCoords(3,3);          position2.setBothCoords(7,7);          position3.setBothCoords(9,9);                    System.out.println("position1 " + position1.getX());          System.out.println("position2 " + position2.getX());          System.out.println("position3 " + position3.getX());      }     }

We do not need to print the Y values to see that each of these class instances are, in fact, separate from each other. They are modifiable copies of the Coordinate class that exist in memory.

Here, our class acts quite a bit like a blueprint for something that will be constructed and exist in memory. Let us move on to class members and see how this changes.

## 3.3 Static And Instance Members

Static members or class members are not duplicated into memory as separate objects, regardless of how many reference variables we create of that class. Although these class members behave differently from instance members, they still share certain qualities such as shared access specifiers.

Below I have rewritten the Coordinate class so that the variables are now static.

  public class Coordinate {      private static int globalX = 100;         private static int globalY = 100;            public int setGlobalXY(int x, int y) {          globalX = x;          globalY = y;      }      public int getGlobalX() {          return  globalX;      }      public int getGlobalY() {          return globalY;      }  //...  }

The private access specifier makes the two static variables inaccessible from the outside.

  public class Main {            public static void main(String[]args) {                    Coordinate.globalX = 10;          Coordinate.globalY = 10;          int myInt = Coordinate.globalX;          myInt = Coordinate.globalY;          // none of these will work      }  }

From outside of the Coordinate class, we do not have access to its private fields. The setter and getter methods are publicly accessible, so they are the only way that we may access the two static variables from our main method. Let us instance the class to retrieve the variables.

public class Main {

    public static void main(String[]args) {
        Coordinate coordinate1 = new Coordinate();

        coordinate1.setXY(10, 17);

        myIntY = coordinate1.getGlobalY();
        myIntX = coordinate1.getGlobalX();

        System.out.println("global x value: " + myIntX);
        System.out.println("global y value: " + myIntY);

    }
}

This works and it does make some sense. The only methods that could access the two private class members in the Coordinate class are the public instance methods. In this scenario, the class does not act like a blueprint at all, but it is still worth instancing into memory so that we may access the private variables.

Making any additional instances of the class would be rather pointless, as the variables do not exist as duplicates in memory. The next example shows how there are only one set of X and Y values.

public class Main {

    public static void main(String[]args) {

        Coordinate coordinate1 = new Coordinate();
        Coordinate coordinate2 = new Coordinate();

        coordinate1.setGlobalXY(5,5);
        System.out.println(coordinate1.getGlobalX());
        System.out.println(coordinate1.getGlobalY());

        System.out.println(coordinate2.getGlobalX());
        System.out.println(coordinate2.getGlobalY());
        //this will print five in each instance

        coordinate1.setGlobalXY(10,10);

        System.out.println(coordinate1.getGlobalX());

        System.out.println(coordinate2.getGlobalY());
        //now they are all ten
    }
}

Regardless of which reference variable we use, they will point to the same pair of class members.

## 3.4 Static VS Instance Memory

We write code that predicts for two different runtime scenarios. In one, our class is loaded and initialized into the JVM, its static methods and variables are already accessible.

In the second scenario, the class exists as an object. From outside of the class’ instance, we use a reference variable to refer to the memory object. From inside of the instanced class, the members not marked static will exist and operate only when instanced.

The example class below shows how instance and class members from within the same class do not behave alike.

public class MemberExample {

    static int staticVar;
    int instanceVar;

    public static void staticMethod() {
        staticVar +=1;        // will work
        instanceVar +=1;      // will not work
        instanceMethod();     // will not work
    }

    public void instanceMethod() {
        staticVar += 1;          // will work
        this.instanceVar += 1;   // will work
        staticMethod();  // will work
    }
}

The MemberExample class does not contain any reference variables, but you can still see what is marked static and what is not. The two static members are accessible right away, though they cannot interact with instance members without an instance variable. An instance variable would guarantee that when we call the static method, it would act upon an instance member that already exists in memory.

The instance members are quite different, though when we write them, we are implicitly saying that we will definitely have an instance of the class at some point so that it may perform the actions we specify. That is why it is so much more flexible.

## 3.5 “this” Keyword

You may use the this keyword to differentiate between instance variables and parameters of the same name. The examples in this book use the keyword a lot, but you may choose not to and keep the names of your instance variables and method parameters different.

public class Example {

    public int value;

    static void valueSetter(int value) {
        this.value = value;
        //will not work!
    }

    void numberSet(int value) {
        this.value = value;
        //this will work
    }
}

You may even refer to the current class’ instance variable using the this keyword. It seems like an odd thing to do, but sometimes you will have class instances with an inaccessible constructor.

  public class Example {            public Example instanceGetter() {          return this;      }

Classes do not have addresses, but instances do, so the only thing that this could refer to is the instance itself. That is why the return type is the same as the class. Calling the method will return a reference address.

* * *

We have much more to learn about classes and objects. The class and instance member differences are good to know, but if you only remember one thing from this chapter, it should be that classes are user defined types.

*   Classes define custom datatypes.

*   Classes exist as files.

*   Objects exist in memory as class instances.

*   Not everything inside of a class file will become an object.

*   Static methods cannot access instance members without an instance variable.

*   Instance methods can access both class and instance members freely.

*   Things such as access specifiers apply to both instance and class members of the same class.

In the next chapter, we will take what we have learned and start working with instance variables.

* * *

# CHAPTER 4: OBJECT REFERENCES

Almost all of the code we write in Java will involve accessing, creating or storing reference variables in some way or another. When we accept a reference variable in a field or method parameter, we allow one instance of a class to interact with another. It is through this process that programming techniques such as aggregation or composition are made possible.

In this chapter, we will compose some simple objects into larger ones by storing instance references together. We will also learn how empty object references cause problems and one way we may check for them.

## 4.1 Pass by Value or Reference

Before we continue, it is worth addressing a particular concern that memory-aware programmers may have when creating multiple objects and moving their reference variables from one location to another.

It is true that Java is a pass-by-value language, but the value that we use to send, store, and receive object references is merely address data to a memory location. This is like saving a web address to a text file. It has some file size, but it is trivial compared to all of the html, CSS and images that are on the actual page. Rest assured, passing objects in Java is cheap and this is a good thing because we will do it a lot as our programs grow.

## 4.2 Getting and Setting References

Let us try making some of our own classes and combining them to make a composite object. We will start with a class that holds two x and y coordinates, then store a pair of them together to make a line.

  public class Point2D {      public float x;      public float y;  }

This Point2D class holds a pair of values. We can use them to make a simple two dimensional vector or line that consists of two x-y points.

public class Line2D {      Point2D point1;      Point2D point2;        }

Now to we have a total of four values spread across three total class instances. One line holds two points and each point takes its own pair of x and y values. Let us write a class with methods that will automate all of the instantiation and set our provided values to the two points.

## 4.3 The LineUtils Class

We have already seen that we may use static methods with reference variables, so let us write a series of static methods that create and modify instances of both the Point2D and Line2D classes via reference.

public class LineUtils {

    private static Point2D pointInit(float x, float y) {

        Point2D point = new Point2D();
        point.x = x;
        point.y = y;

        return point;
    }

    public static Line2D lineInit(float x1, float y1, float x2, float y2) {

        Point2D p1 = pointInit(x1,y1);
        Point2D p2 = pointInit(x2,y2);
        Line2D line = new Line2D();
        line.point1 = p1;
        line.point2 = p2;

        return line;
    }

    private static String pointString(Point2D p) {

        String result;
        result = "point x: " + p.x + "\n" + "point y: " + p.y;
        return result;
    }

    public static void echoLine(Line2D line) {

        String p1 = pointString(line.point1);
        String p2 = pointString(line.point2);

        System.out.println(p1+"\n"p2);

    }
}

There is a lot going on in the LineUtils class and most of it involves sending and receiving reference variables. First, we need a pair of points, so we write the pointInit method to call the Point2D constructor and set the x and y fields in the class’ instance.

The lineInit method calls the pointInit method two times and supplies enough float values for both new points. Next, the pointString method takes Point2D objects and turns them into printable strings before returning them to the calling method.

Our final method, echoLine calls the pointString method once for each point reference variable and constructs a string, then prints them both. That is the entirety of our LineUtils class. Note how some of the methods are private. This is because we do not want to call them in the wrong order and try to print the values before we have them.

 public class Main {

    public static void main(String[]args) {

        Line2D line = LineUtils.lineInit(2,8,10,5);
        LineUtils.echoLine(line);
    }
}

This is all it takes to interact with the Point2D and Line2D classes. We do not even directly call their constructors to make the objects and send them where they need to go. It is worth noting that keeping the instantiation details separate does not always make sense and we could put the static methods inside of the line and point classes themselves, but you will see a better way to instance classes in the next chapter.

## 4.4 Null References

Instancing the Line2D class and then printing it requires three object references. If we were to write the lineInit method and forget to instance one or both of the Point2D objects, then the program would not compile and we would likely see an error in our IDE regarding null references.

The null keyword in Java allows us to do a few different things with object reference variables. First, let us use null to simulate a missing object reference.

 public class Main {

    public static void main(String[]args) {

        Line2D line = LineUtils.lineInit(2,8,10,5);
        line.point1 = null;
        LineUtils.echoLine(line);
        //this code will fail   
    }
}

We used the null keyword to set one of the line object’s points to null. The code will now fail to compile because an essential component is missing. We may now use the same keyword as a test condition to safeguard against such scenarios as shown in the code below.

  public class LineUtils {  //...      public static void echoLine(Line2D line) {          if(line.point1 == null || line.point2 == null) {              System.out.println("the line is null!");          } else {              String p1 = pointString(line.point1);              String p2 = pointString(line.point2);              System.out.println(p1+"\n"p2);          }      }  }

Now when we call the method with a null object reference the program will still compile. We could even set the conditional statement to call constructors for us and fill any empty reference variables.

* * *

As we start creating and instancing classes, we must manage their memory objects through reference variables. We will do this all the time in Java and the practice allows for some very intricate programs so long as we remember to fill our reference variables as needed.

*   Object references are cheap to send, receive and store.

*   Both methods and constructors may return object references.

*   One object reference may rely on others in order to function correctly.

*   Empty reference variables are null and introduce a set of problems we must be wary of.

With this chapter finished, we will move on to constructors and how we can leverage them to automate more instantiation and prevent null references.

* * *

## CHAPTER 5: CONSTRUCTORS

When you write a new class you are also writing a new default constructor. You may instance your class with the provided default constructor, or you may write your own in order to customize instantiation itself.

In this chapter you will see a few different ways to write default constructors and how they help to automate, limit, and even prohibit class instantiation.

## 5.1 Default Initializer

Default initializers run when we instantiate classes. This variation of the default constructor is the simplest, as it is a simple expansion of the constructor with some added code between a pair of curly braces. Note how it begins to look similar to a method.

Here is our old Line2D class from the previous chapter:

public class Line2D {      Point2D point1;      Point2D point2;  }

Now the class again but with a simple default initializer.

public class Line2D {

    Point2D point1;
    Point2D point2;

    public Line2D() {
        point1 = new Point2D;
        point2 = new Point2D;

    }
}

This code is far more concise and convenient than the clunky set of static methods we used in the old LineUtils class. We will always have this pair of blank Point2D objects in all instances of Line2D, so there is now no more risk of null references in this class.

We know that we may run enough code from the constructor to instance other classes. How about running our own methods? Surprisingly, it is possible to run instance methods from the constructor itself as you will see this next example.

public class Line2D {      Point2D point1;      Point2D point2;            public Line2D() {          point1 = new Point2D();          point2 = new Point2D();          echoInstantiation();      }      public void echoInstantiation() {          System.out.println("Line2D instantiated!");      }  }

We have already saved ourselves a lot of work by using our own constructors. Let us customize our constructors further to see what else they will do for us.

## 5.2 Parameterized Constructors

You may parameterize a constructor like a method. The arguments that you supply may be used just like with a setter method, to fill instance fields during object creation. We will add a parameterized constructor to the Point2D class.

public class Point2D {      public float x;      public float y;            public Point2D(float x,float y) {          this.x = x;          this.y = y;      }  }

When the only constructor in a class is parameterized, it is mandatory that you provide arguments for those parameters. This is good for when we do not want values to go unset such as in the Point2D class where we know that every point must exist somewhere in a 2D space.

Class constructors may be overloaded like methods. As long as each constructor has different parameters, we may have as many as we want. The next example shows that we now have a number of different ways to instance the Line2D class while filling any of the new Point2D constructors.

public class Line2D {

    Point2D p1;
    Point2D p2;

    Line2D(Point2D p1, Point2D p2) {
        this.p1 = p1;
        this.p2 = p2;
    }

    Line2D(Point2D p1, float x2, float y2) {
        this.p1 = p1;
        this.p2 = new Point2D(x2, y2);
    }

    Line2D(float x1, float y1, float x2, float y2) {
        p1 = new Point2D(x1, y1);
        p2 = new Point2D(x2, y2);
    }

    void echoLine() {
        System.out.println("x1 value: " + p1.x + "\n" + "y1 value: " + p1.y);
        System.out.println("x2 value: " + p2.x + "\n" + "y2 value: " + p2.y);
    }

}

Normally we do not see so many constructors in one class, though each of them shows a different way to instance Line2D with different arguments. Before we start making instances of Line2D, let us first make a new class that holds multiple lines.

## 5.3 Plotting a Triangle

Until now we have been strict in forcing ourselves to provide parameter arguments for all of our constructors. For the new Triangle class, we will do something different.

First we add the Line2D fields and a parameterized constructor.

public class Triangle {      Line2D line1,line2,line3;      Triangle(Line2D l1, Line2D l2, Line2D l3) {          this.line1 = l1;          this.line2 = l2;          this.line3 = l3;      }  }

It is possible that we may not have all of our line objects ready at one time, so we will reintroduce the default constructor to the Triangle class. Doing so is actually quite easy. We simply restate the default class without any parameters or initialization code.

public class Triangle {

    Line2D line1,line2,line3;

    Triangle() {}

    Triangle(Line2D l1, Line2D l2, Line2D l3) {

        this.line1 = l1;
        this.line2 = l2;
        this.line3 = l3;
    }

    echoTriangle() {
        line1.echoLine();
        line2.echoLine();
        line3.echoLine();
    }

}

We may turn the default constructor into a default initializer or leave it as is, the choice is all ours. We are now ready to make an instance of the Triangle class with all of custom constructors.

## 5.4 Calling Parameterized Constructors

We now have three different classes. One is a pair of coordinates that make up a two dimensional point, the next is a line that is made of two points and the third is a triangle composed of three lines. In an actual graphical program these may look different and only rely on points to draw lines, but here we are more concerned with classes and constructors.

Here is an example of the Triangle class being instanced. Note all the different ways that we use the Line2D’s constructor.

 public class Main {

    public static void main(String[]args) {

        Line2D line1 = new Line2D(0,0,10,0);
        Line2D line2 = new Line2D(new Point2D(10,0),10,10);
        Line2D line3 = new Line2D(new Point2D(0,0),new Point2D(10,10));

        Triangle triangle = new Triangle(line1,line2,line3);

        triangle.echoTriangle();
    }
}

Now that we have used our points and lines to make a triangle, we will move on to private constructors.

## 5.5 Private Constructors and Static Methods

Sometimes constructors are made private so that they may not be accessed from any outside classes. We have other ways to make instantiation impossible, but sometimes we want to make the constructor private so that instantiation is limited or strictly controlled. The singleton design pattern is one such case.

The singleton design pattern is when we only want one instance of a class to exist. The way to write this single-instance class is to make the constructor private and use a static method from inside of the class to retrieve its address.

 public class SingleTriangle {

    Line2D line1;
    Line2D line2;
    Line2D line3;

    private static SingleTriangle SINGLETON_REFERENCE;

    private SingleTriangle() {};

    public static SingleTriangle singletonGetter() {

        if(SINGLETON_REFERENCE == null) {
            SINGLETON_REFERENCE = new SingleTriangle();
        }
    //Note that this is a good use case for the 'null' keyword.
        return SINGLETON_REFERENCE;
    }
}

Remember in chapter three where we had private variables and public methods to access them. This singleton is another example of a class that is not purely a template and makes full use of in-member access privileges.

With additional methods, we could make setters and getters for the Line2D. What matters most is that our singleton class actually gives us addresses of the same object and not duplicates of it. We can test this by assigning the reference to two variables and checking to see if their hashcodes match.

  public class Main {      public static main(String[]args) {          SingleTriangle triangle1 = Triangle.singletonGetter();          SingleTriangle triangle2 = Triangle.singletonGetter();                    System.out.println(triangle1.hashCode());          System.out.println(triangle2.hashCode());      }  }

The above code should print the same hashcode for each of the triangle1 and triangle2 variables. This shows that each variable holds a reference to the same object.

* * *

Writing our own constructors means we may decide how our classes are instanced. From running default code to demanding constructor arguments, we have far more options when we start leveraging the flexibility that custom constructors give us. They are so flexible that we may choose to make them optional by reintroducing a default constructor back into our classes.

*   Default initializers allow us to automatically run code when a class is instanced.

*   Constructors can have parameters that must be filled on instantiation

*   We may have more than one constructor per class.

*   We may have both parameterized and default constructors in the same class.

*   Constructors can be made private in order to limit instantiation

With this chapter finished, we will now learn about inheritance.

* * *

# CHAPTER 6: INHERITANCE

Inheritance in Java is both powerful and perilous. There are many things that you can do with inheritance, but certainly not as many as you should do. Many people hold opinions regarding inheritance, and some will say that we ought to avoid it entirely. Whether you plan to use inheritance or not, one thing is certain: you will eventually find yourself working with it and ought to understand it regardless.

Once again we must think of what a class file’s contents tell us. They define a data type as well as the access and behavior specifics of their class and instance members. Another thing a class may indicate is that it extends another. To extend is to inherit and inheritance adds any eligible instance members to a subclass in addition to the superclass’ type.

Because subclasses are also subtypes, they share a common identity with their superclass. Anywhere that you would normally use an instance variable of the superclass’ type, you may also use an instance variable of the subclass’ type. Even though a subtype is compatible, you may find that you have added some code or behavior that makes it a poor fit for that parent type’s role.

In this chapter, we will first learn about member and constructor inheritance, then in the next we will explore type inheritance.

## 6.1 Subclassing Rules

Java does not allow a single subclass to extend two direct superclasses. We may extend one class after another like connecting pipes from end to end, and many classes may share a single superclass. Below are some examples of the rules we must follow.

class First{}  class Second extends First{}  class Third extends Second{}  class Fourth extends Third {}  //...

Classes may keep extending each other to near infinity.

class First{}  class Second extends First{}  class Third  extends First{}  class Fourth extends First{}  class Fifth  extends First{}

Here we have many subclasses with the same superclass. Each subclass may add something different while sharing its superclass’ type and members.

Java does not allow us to extend two superclasses with one subclass.

class First{}  class Second{}  class Third extends First, Second{}  //this will not work!

The rules to using the extends keyword are pretty simple. Now let us see how subclasses inherit members from superclasses.

## 6.2 The ‘Super’ Keyword

Subclasses inherit the non-private and non-static members of their superclasses. Inherited members are not visible from within the extending class, but you may still access them either from the subclass’ reference variable or from within the subclass using the super keyword.

The benefit to keeping inherited code invisible is that our subclasses will not have the clutter of what they inherit from one or more superclasses. The drawback is that you will not always see what you are working with, and this may be especially confusing when working with code that you did not write yourself.

In this section we will extend and access some superclass members of our own.

public class OriginalGreeting {            public void greeting() {          System.out.println("hello from the original superclass");      }  }

This class has a simple greeting that tells us where it came from. Now we add a subclass.

public class SecondGenGreeting extends OriginalGreeting {      public void secondGenGreeting() {          System.out.println("hello from the 2ndGen class");      }  }

This final class we will leave blank for now.

public  class ThirdGenGreeter {}

Now to instance the ThirdGenGreeter class from main to see what it has inherited.

  public class Main {            public static void Main(String[]args) {          ThirdGenGreeter greet = new ThirdGenGreeter();          greet.greeting();          greet.sendGenGreeting();      }  }

Inheritance allows us to call superclass members as far back up the inheritance chain as we want. Let us add some more code to the ThirdGenClass to see what the super keyword will do for us.

public class ThirdGenGreeter extends {

    public void finalGreeting() {
        super.greeting();
        super.secondGenGreeting();
        System.out.print("hello from the third gen greeting!");
    }
}

Now to access all three methods we may instance and call the finalGreeting from the ThirdGenGreeter class.

public class Main {      public static void main(String[]args) {          ThirdGenGreeter thirdGreeter = new ThirdGenGreeter();          thirdGreeter.finalGreeting();      }  }

It is of particular concern that our finalGreeting method from the ThirdGenGreeter class depends on two superclasses in order to function. If you were to change or rename the FirstGenGreeter or the SecondGenGreeter classes, or their methods, then you would surely break the finalGreeting method. This example is trivial, but in larger programs you must plan so that you do not end up writing such tightly coupled code if it is subject to frequent changes.

Now let us see how inheritance and constructors work together.

## 6.3 SuperConstructors

When one class extends another class, and that superclass has a parameterized constructor, the subclass will inherit the need for constructor arguments. Of course, if the parameterized constructor is optional due to the presence of a default constructor, then those arguments are also optional for the subclass.

Let us modify the SecondGenGreeting class so that it takes some text through a parameterized constructor.

public class SecondGenGreeting extends OriginalGreeting {      String message;      SecondGenGreeting(String msg) {          message = msg;      }            public void secondGenGreeting() {          System.out.println("hello from the 2ndGen class");      }  }

Now the SecondGenGreeter requires an argument to be instanced. Consequently, The ThirdGenGreeter class also requires the same constructor argument.

public class ThirdGenGreeter extends SecondGenGreeting {      ThirdGenGreeting(String msg) {          super(msg);      //note how the 'super' keyword also refers to constructors      }            public void finalGreeting() {          super.greeting();          super.secondGenGreeting();          System.out.print("hello from the third gen greeting!");      }  }

Note how the super keyword takes a string argument like a method. The string value is stored in the message field that we inherit from the superclass. This makes sense, because if you were to call the secondGenGreeting without filling the message field, the program would fail and filling the constructor argument prevents that.

## 6.4 Protected Member Inheritance

Java has four access specifiers: public, private, protected and default. From within the same package, access is simple. Either you may access a class member or not. When your program is split between packages, however, you may only access other package members marked either public or protected. Protected classes require extension in order to access their contents. Let us see a few examples below.

Let us assume the two following classes are in different packages.

package mypackage.subpackage;  public class OriginalGreeting {      protected void originalGreeting() {}       public void greeting() {          System.out.println("hello from the original superclass");      }  }

If we try to instance this class from our main method and that class does not extend OriginalGreeting, then it will not work.

package mypackage;  public class Main {      public static void main(String[]args) {          OriginalGreeting ogGreet = new OriginalGreeting();          //this will not work      }  }

The OriginalGreeting class’ access specifier protected limits our cross-package access to the constructor. By using the SecondGenGreeting subclass, we may access the superclass’ members by inheritance.

package mypackage;  public class Main {      public static void main(String[]args) {          SecondGenGreeting greet = new SecondGenGreeting("");          greet.greeting();      }  }

When working with multiple packages, the entry points that you are meant to access are typically marked public. There may be some cases where classes are protected, and you will still be able to access them so long as you use a some inheritance.

* * *

We still have a lot to learn about inheritance. You have seen how to extend classes and access their contents. Next, you will see how to use inheritance to share and substitute types.

*   Inheritance allows us to share types, data and methods between subclasses.

*   One subclass may only have one direct superclass.

*   Inheritance hides messy code, though it may also obfuscate where that code actually is.

*   Modifying a superclass may break any subclasses that extend it. The further a class extends, the more breakable they become.

*   Inheritance is the only way to access protected members between classes.

* * *

# CHAPTER 7: ABSTRACT CLASSES & METHODS

In the last chapter we had an introduction to inheritance. We saw access specifiers, member inheritance and super constructor parameters. We will now learn of a scenario where we want to inherit a superclass’ type along with its methods, and how a new kind of class and method solves some limitations of class inheritance.

## 7.1 The Initial Classes

First, we are going to make a base Shape class that holds the surface area of various shapes. We will then subclass it and use type inheritance to treat reference variables from each class the same.

public class Shape {

    double side;
    //we will use side for both the square side and circle radius
    double area;

    Shape(double, side);

    double getArea() {
        return this.area;
    }
}

Now that we have a basic shape class, we will use it to create specific shapes. First, we will extend it with a square class.

  public class Square extends Shape {            Square(double side) {          super(side);      }      void calcArea() {          double s = super.side;          super.area = s*s;      }  }   

Next is the circle class. We will use the side length as the radius for convenience.

public class Circle extends Shape {      Circle(double radius) {          super(side);      }      void calcArea() {          double r = super.side;          this.area = 3.1415*(r*r);      }  }

We will now instance it in main to see what we have so far.

 public class Main {

    public static void main(String[]args) {

        Circle circle = new Circle(4);
        Square sq = new Square(3);

        sq.calcArea();
        circle.calcArea();
    }
}

This example code should give you a few approximate values for each shape’s value. We may find ourselves with a large number of shape objects, so we will use an array to keep them organized.

  public class Main {      public static void main(String[]args) {                    Shape[] shapes = new Shapes[2];          shapes[0] = new Circle(4);          shapes[1] = new Square(3);          shapes[0].calcArea();          shapes[1].calcArea();          //this will not compile. Why?      }  }

We have an array that holds object references of the Shape class. The Circle and Square classes became subtypes through inheritance, so you may store their reference variables in the same array. For some reason, you are not allowed to call the calcArea method from the array members, even though they certainly have this method. Why is this?

The reason that our calcArea method will not work, is due to the array’s Shape type lacking such a method of its own. We may fix this with some typecasting or other workarounds, though a more elegant solution would involve using Java’s abstract classes and methods. We will learn about them in the next section.

## 7.2 The Abstract Class and Abstract Methods

Before we rewrite our two shape classes, let us learn a little about Java’s abstract classes and methods. It is true that object oriented programming is quite abstract in nature, so you may be wondering how an abstract class differs from a normal one. In brief, an abstract class is one that:

*   Uses the abstract keyword
*   Cannot be instanced
*   May contain abstract methods

It looks like we are going to sacrifice a lot in order to gain these so called abstract methods. What is so special about them? Their implementation may vary from one class to another. Below is an example of an abstract method.

abstract  int  changesX(int x);

The abstract keyword allows us to write a method with no body. Even without a body, we are making a kind of promise that says we will provide one in every extending class. Each non-abstract subclass that we write must have a method of the same name and that method must return an int and accept one as an argument.

Here is an implementation from one subclass.

//...  int otherNumber;  @Override  int changesX(int x) {      otherNumber += x;      return otherNumber;  //...  }

Here is an implementation from another subclass. Notice how the method body is different. It is not like the other subclass’ definition for the changesX method, yet it still matches the abstract method header we wrote in the abstract class.

//...  @Override  int changesX(int x) {      int result = (x * x * x);      return result;  //...  }

You can see from these examples that abstract classes and methods allow us to declare a method once and define its specifics multiple times. Of course, the abstract reference’s type recognizes the existence of the abstract method.

Now let us return to our Shape class example and see how abstract classes and methods will solve our problem.

## 7.3 The Abstract Shape Class and Methods

We will return to the Shape class and mark it abstract in the class’ header. Next, we write an abstract method called calcArea that we will then implement in differently in each of our subclasses.

public abstract class Shape {            double side;      double area;            Shape(double side) {          this.side = side;      }      double getArea() {          return this.area;      }      abstract void calcArea();  }

That is all it takes to make a class and method abstract. Note that now that we cannot instantiate it directly.

Let us return to Square class and implement the abstract method from Shape.

  public class Square extends Shape {            Square(double, side) {          super(side);      }            @Override      double calcArea() {          double d = super.side;          super.area = (d*d);      }  }   

Next is the circle class. We will extend the Shape class and implement its abstract method.

public class Circle extends Shape {      public Circle(double radius) {          super(radius);      }            @Override      public void calcArea() {          double r = super.side;          this.area = 3.1415*(r*r);      }  }

Note the use of the @Override annotation. It is not entirely mandatory, though it helps to debug errors and remind us that the method actually originates from somewhere else. For these reasons, we should always prefer to annotate our abstract methods in this way.

Once the two classes are updated, we may store them inside of an array and call the common calcArea as needed. Our final code will look something like the following.

public class ShapeManager {            Shape[] shapes;      ShapeManager(int size) {                this.shapes = new Shape[size];      }      void reportAll() {          for(Shape shape : shapes) {              shape.calcArea();              System.out.println("shape area: "+ shape.getArea());          }      }  }

Now we may call the calcArea method through ShapeManager reference variables. They are all stored in an array of Shape reference types.

 public class Main {

    public static void main(String[]args) {

        ShapeManager sManager = new ShapeManager(5);

        sManager.shapes[0] = new Circle(4);
        sManager.shapes[1] = new Square(3);
        sManager.shapes[2] = new Square(4);
        sManager.shapes[3] = new Circle(7);
        sManager.shapes[4] = new Square(2);

        sManager.reportAll();
    }
}

The ShapeManager class and the simple loops set and print all of the values to your terminal. You could take this example even further and add some arguments that make all of the outputs relative to each other or even write an algorithm to sort them. What matters most is that inheritance gives us common types and abstract classes give us common types along with abstract methods.

* * *

In this chapter we saw how abstract classes and the abstract methods add another dimension to our object oriented code. So long as these abstract methods have the same header, we may implement them however we wish.

*   Inheritance allows us to use subtypes in place of the stated supertype.

*   Abstract classes allow us to use abstract methods.

*   Extending classes must provide an implementation for abstract methods.

*   Abstract methods may be implemented differently in each subclass.

This concludes chapter 7\. We will work with even more abstract methods in the next chapter where we will learn of interfaces.

* * *

# CHAPTER 8: INTERFACES

The abstract classes in the previous chapter allowed us to do a few useful things. First, we used inheritance to make subtypes of the Shape class, then we implemented an abstract method differently in two different subclasses. In this chapter, you will learn how to share common types and abstract methods without using inheritance at all.

What are Interfaces? They are completely abstracted classes that cannot be directly instantiated and cannot have fields of any kind. You will find three kinds of methods inside of interfaces: default, static and abstract.

Default and static methods and not unlike what you would find in a regular Java class. We have already seen abstract methods, yet their particularly flexible nature pairs nicely with interfaces. For this reason, you will see the two combined in all interface examples.

## 8.1 Type By Implementation

Classes define and describe new datatypes. What we see in a class’ header tells us a lot, especially when the extends keyword is present. We know that when a class extends another, it gains the superclass’ type and all of its inheritable members. Similarly, the implements keyword tells us that a class gains the type of one or more interfaces and provides implementations for any abstract methods in those interfaces.

Let us replace our old Shape class with an interface and an abstract method.

  public interface CalculateArea {      double calculateArea();  }

We no longer need to label the abstract method with a special keyword. So long as it appears in an interface and has no body, the method is implicitly abstract.

Just as with the abstract method in our old Shape class, you must provide an implementation for the abstract method that you gained by implementing the CalculateArea interface. We even use the same annotation.

public class Circle implements CalculateArea {

    double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double calculateArea() {
        double r = this.radius;
        double pi = 3.1415;
        return pi * (r * r);
    }

}

Here is the square class implementing our same CalculateArea interface. Once again, we provide an implementation that suits our needs.

  public class Square implements CalculateArea {            double side;            public Square(double, side) {          this.side = side;      }            @Override      public double calculateArea() {          double s = this.side;          return s*s;      }  }   

Every class that implements the CalculateArea interface has two things in common. First, it is bound to provide an implementation for all of the abstract methods in CalculateArea. Secondly, the object references of these classes may be referred to by the interface’s type.

We may store an array of object references and set the type to CalculateArea. This will allow you to treat Circle and Square class instances the same.

 public class ShapeManager{

    CalculateArea[] shapes;

    public ShapeManager(int size) {
        this.shapes = new CalculateArea[size];
    }

    public void reportAll() {
        for(CalculateArea shapes : shapes) {
            System.out.println("area: " + shapes.calculateArea());
        }
    }
}

Now all we must do is instance the ShapeManager class, add members to its array and watch how it works.

  public class Main {      public static void main(String[]args) {                    ShapeManager sManager = new ShapeManager(5);                    sManager.shapes[0] = new Circle(4);          sManager.shapes[1] = new Square(3);          sManager.shapes[2] = new Square(4);          sManager.shapes[3] = new Circle(7);          sManager.shapes[4] = new Square(2);          sManager.reportAll();          }      }

By telling the ShapeManager class to expect objects from classes that implement the CalculateShape interface, we have completely removed the need for our old Shape class.

## 8.2 Multiple Implementations

What if we were to make our two dimensional object three dimensional? There are a number of ways to do this. Inheritance is an option, but we will avoid it for now to show how flexible interfaces are.

Let us start with an interface that calculates volume.

public interface CalculateVolume {      double calculateVol();  }

Now we will make a cube class and use both interfaces to calculate the dimensions and volume. Note that we must use different math to get all six sides of our cube.

public class Cube implements CalculateArea, CalculateVolume {

    double side;

    public Cube(double side) {
        this.side = side;
    }

    @Override
    double calculateArea() {
        double s = this.side;
        return 6 * (s*s);
    }

    @Override
    double calculateVolume() {
        double s = this.side;
        return (s*s*s);
    }
}

Inheritance of state is strictly prohibited in Java because conflicting values cause technical issues. Both abstract and concrete classes may have member fields, so it makes sense that we cannot extend more than one per class. Interfaces cannot have data fields of any kind, so there is no reason to restrict them to this single inheritance rule.

One class may inherit multiple interfaces and interfaces may extend multiples of each other.

public interface Calculate3D extends CalculateArea, CalculateVolume {  }

We do not have any methods to put in this interface yet, but it will work for our example.

Now we may rewrite our Cube class’ declaration as such:

  public class Cube implements Calculate3D {  //...  }

The same implementation rules apply here. Our new Cube class must implement all of the methods from the CalculateArea and CalculateVolume interfaces, as well as any abstract methods that we add to Calculate3D.

Before we create and calculate any instances of the Cube class, let us turn our circle into a sphere. We will write this example a little differently to show how interfaces and abstract classes work.

## 8.3 Mixing Implementation and Inheritance

We will combine inheritance and implementation for our Sphere class. First, We will write an abstract Rounded3D class that implements the Calculate3D interface. Take note of how it ignores Calculate3D’s abstract methods.

  public abstract class Rounded3D implements Calculate3D {      double volume;      double totalArea;      double radius;      double circleArea;      public Rouned3D(double radius) {          this.radius = radius;      }      public void calculateCircle() {          double pi = 3.14;          double r = this.radius;          this.circleArea = pi * (r*r);      }  }

The Rounded3D abstract class shows us a useful feature that helps us write more flexible code. Remember that the benefit of abstract classes is that they may have abstract methods and not implement them. Because of this, it is up to you whether you wish to implement some, all or none of the abstract methods in Calculate3D or the interfaces it extends.

What about classes that extend Rounded3D? If an extending class is not abstract, then it must implement any abstract methods whether they originate from the superclass or interfaces that the superclass implements.

  public class Sphere extends Rounded3D {            public Sphere(double radius) {          super(radius);      }      @Override      public double calculateArea() {          double circle = super.calculateCircle();          return circle * 4;      }      @Override      public double calculateVolume() {          double r = super.radius;          double rCubed = (r*r*r);          volume = (4*pi*rCubed)/3;          return volume;      }  }

The Sphere class will now take an input and calculate the volume and area for us. The abstract Rounded3D class provides a few helper methods, but leaves the important implementations up to us. This makes the Rounded3D class useful for other shapes too.

## 8.3.1 An Optional Cylinder

This section shows how we would go about adding another rounded three dimensional shape by extending the Rounded3D class. You may choose to skip this section, as it is not as essential as the other two examples.

Our new Cylinder class extends Rounded3D and adds a new height dimension. We will combine inherited members and custom implementations to calculate the surface area and volume of this new shape.

 public class Cylinder extends Rounded3D {

    double height;

    public Rounded3D(double radius, double height) {
        super(radius);
    }

    @Override
    public double calculateArea() {
        double rh;
        double flatSide;
        flatSide = super.calculateCircle();
        rh = this.radius * this.height;
        this.area = 2*pi*rh + 2*flatSide;
        return area;
    }

    @Override
    public double calculateVolume() {
        double rSq,flatSide;
        flatSide = super.calculateCircle();
        this.volume = flatSide * height;
        return volume;
    }
}

Now we have used the Rounded3D class for two different three-dimensional shapes and they both share a common supertype. In addition, both of these classes share a common implementation with the Cube class.

All we must do now is write our ShapeManager class so that it may anticipate what kind of references we will send to it.

## 8.4 Accepting Interface References

Assume that we want our ShapeManager class to store all of the object references in one convenient array. We must set that array’s type to hold all of the different classes that we wrote and potentially some new ones. The type that best covers all of the three dimensional shapes would be the Calculate3D interface. It has all the methods that we need so it will be the array’s type.

 public class ShapeManager3D {

    Calculate3D[] shapes;

    public ShapeManager(int size) {
        this.shapes = new ShapeManager[size];
    }

    public void reportAll() {
        for(Calculate3D shapes : shapes) {
            System.out.println("shape area:  " + shapes.calculateArea());
            System.out.println("shape volume:  " + shapes.calculateVolume()+"\n");
        }
    }
}

Once more, we will instance the classes and see how they work.

public class Main {      public static void main(String[]args) {          ShapeManager3D shape3d = new ShapeManager3D(5);          shape3d.shapes[0] = new Cube(5);          shape3d.shapes[1] = new Sphere(10);          shape3d.shapes[2] = new Cylinder(5);          shape3d.shapes[3] = new Cube(7);          shape3d.shapes[4] = new Sphere(3);                    shape3d.reportAll();      }  }

All three of our new shapes share a common Calculate3D interface, so this is the type that we use for our array.

We may add even more three dimensional shapes and have them implement the Calculate3D interface. This is how we may call the calculateVolume and calculateArea methods from many different object references without class inheritance.

* * *

Our example program exposes only some of the power that interfaces give us. We could make several abstract classes that implement all, some or none of the interface’s abstract methods. We could even subclass abstract classes so that each of them implement more abstract methods than the last.

To summarize:

*   Implementation and inheritance are separate, but still allow us to share common types.

*   It is optional for abstract classes to implement abstract methods from interfaces.

*   One class may implement more than one interface.

*   Interfaces may extend each other with multiple inheritance.

With this chapter finished, we will continue working with interfaces and combine them with generics.

* * *

# CHAPTER 9: GENERICS I

When you extend one class with another, that subclass gains the type of its superclass. If either the subclass, superclass or both of them implemented one or more interfaces, then the subclass would gain that type data as well. Take the Sphere class as an example. It is a subclass of a superclass that implements multiple interfaces (through interface extension).

As far as types go, we know that the Sphere class has the following types:

*   Sphere
*   Rounded3D
*   CalculateVolume
*   CalcluateArea

We have four different types to set as method parameters or variable types.

As we add more classes and interfaces to a program, it becomes unclear as to what we expect where we declare reference types for method parameters and instance variables. Do we want a Sphere because it is round? Perhaps we simply want an object with circumference or volume.

We would benefit from a form of syntax that helps us state: accept a reference type that extends this class and implements these interfaces. Thankfully Java’s generics give us an efficient and type-safe way to do just that.

This entire chapter is about generics and how they will help us work with multiple reference types. When you are done with this rather long chapter, we will return to our 3D shapes to apply what we have learned.

## 9.1 A Growing Need for Generics

Let us say that we are adding two new 3D shape classes. Each of them implements a new interface called HasCoordinates. Now we have our old 3D shapes as well as these new movable ones, and we want to plan for the future so that we may add even more shapes and possibly other interfaces for things such as color or image data.

We will have fields and methods that require reference types of one class, or one field, or any combination of them. We could group classes together with more interfaces and inheritance, but adding more types to our program will only make things more confusing. What we will do instead, is use generics to clarify what goes where.

## 9.2 Bound Generic Types

Generic types allow us to specify specific type data within pairs of angled brackets. You may have seen the syntax before, where some uppercase letter indicates an unknown element or value. The letters are simply a naming convention where we typically use T for type, E for element and K,V for key-value, etc.

These single-letter type variables are just that, variables. They are only place holders for the name of an actual class or interface. The generic variables are exchanged for real type arguments when we refer to the class as a reference variable, such as during instantiation.

public class ShapeUtils <T> {      T shape3D;  }

This generic class has a type parameter named T. When we instantiate the class, we must provide an actual type argument to fill the generic class’ type parameter.

  public class Main {      public static void main(String[]args) {                    ShapeUtils<MovingSphere> mSphereUtils = new ShapeUtils<>();      }  }

That is all it takes to write and use a generic typed class, though this generic class is not exactly what we want.

When we set the generic variable as a single letter such as T, it is possible for us to supply any type as an argument. Sometimes we want this, but such unbound types lack specificity. To restrict what we may supply as an argument for the T variable, we may specify a type requirement or bound.

public class ShapeUtils <T extends Calculate3D> {      T shape3D;  }

Now whatever we supply as an argument to this class’ type parameter must also extend or implement the Calculate3D interface. Below is an example of the ShapeUtils class being instanced twice with two different type arguments that satisfy the type’s bound.

  public class Main {      public static void main(String[]args) {          MovingCube mCube = new MovingCube();          MovingSphere mSphere = new MovingSphere();          ShapeUtils<MovingCube> mCubeUtils = new ShapeUtils<>();          ShapeUtils<MovingSphere> mSphereUtils = new ShapeUtils<>(          mCubeUtils.shape3D = mCube;          mSphereUtils.shape3D = mSphere;      }  }

Note that the keyword extends applies to interfaces and classes in this context.

Any class or subclass that implements Calculate3D is a suitable type argument for the generic class’ type variable. This type’s bound will include any shapes that calculate three dimensional measurements.

Prior being supplied with arguments, the class’ type parameter is quite flexible, but as you will see below, our choices become far more strict once we supply a type argument.

  public class Main {      public static void main(String[]args) {          MovingCube mCube = new MovingCube();          MovingSphere mSphere = new MovingSphere();          ShapeUtils<MovingCube> mCubeUtils = new ShapeUtils<>();          ShapeUtils<MovingSphere> mSphereUtils = new ShapeUtils<>(          mCubeUtils.shape3D = mSphere;             //this will not work          mSphereUtils.shape3D = mCube;             //neither will this!      }  }

The above example shows that even though the MovingCube and MovingSphere type arguments are viable for T, they are not interchangeable with each other after we supply a type argument. The reason for this is that Java employs a kind of type erasure that removes all of the type data except for what we specify as a type argument. This will exclude even similar types.

Type erasure is quite a technical process and beyond the scope of this book. All we need to know here is that it is both type safe and efficient because it eliminates guesswork for the Java compiler.

## 9.3 Multiple Bound Generic Types

We have already written a generic type parameter with a single type bound. Now we will further restrict type arguments for T by adding another bound.

To show how multiple type binds will help us, we return to the ShapeUtils class once more and modify the generic type variable so that it is bound to multiple types. We use the ampersand (&) operator between each additional bound for the type variable.

public class ShapeUtils<T extends RoundedShape & HasCoordinates> {      T shape;            public ShapeUtils(T shape) {          this.shape = shape;      }  }

There are a few rules that we must be aware of when specifying multiple type bounds. If any of the bounds are a class’ name, then that name must appear first. Everything that follows the class’ name must be an interface, as we cannot name a type that extends two classes.

Any type that we substitute for T must implement or inherit everything in the type parameter list. Generics demand that type arguments satisfy all bounds, not just some, and this is good because we want specificity.

public class Main {      public static void main(String[]args) {          MovingCube mCube = new MovingCube();          Cube normalCube = new Cube();          MovingSphere mSphere = new MovingSphere();                    ShapeUtils<MovingCube> mCubeUtils = new ShapeUtils<>(mCube)          //this is exactly what we want          ShapeUtils<MovingSphere> mSphereUtils = new ShapeUtils<>(mSphere)          //this will work with the movable sphere too          ShapeUtils<Cube> mCubeUtils = new ShapeUtils<>(normalCube)          //this does not satisfy generic type requirements          ShapeUtils<MovingCube> mCubeUtils = new ShapeUtils<>(normalCube)          //the type parameter is right, but a normal cube will not work!      }  }

We have effectively filtered out non-moving 3D shapes by specifying that they must also implement the HasCoordinates interface.

## 9.4 Type Bound Generic Methods

Methods may also have type parameters and there are two ways to specify them. One way is to share a generic class’ variable with our methods. The other way is to have our methods declare the type variables and bounds for themselves. In either scenario, we do not supply type arguments to methods when we call them.

public class ShapeUtils<T extends Calculate3D & HasCoordinates> {            T currentShape;      void setShape(T shape3D) {          this.currentShape = shape3D;      }      T getShape() {          return this.currentShape;      }  }

Note how the method type variables are bare and not trapped between angled braces because they are defined elsewhere.

We would instance the class the same as in previous examples. Sending object references to either generic methods requires no extra steps, though we are still limited to the sending references specified by the class’ type argument.

 public class Main {

    public static void main(String[]args) {

        MovingCube mCube = new MovingCube();

        ShapeUtils<MovingCube> mCubeUtils = new ShapeUtils<>()

        mCubeUtils.setShape(mCube);

        MovingCube duplicateRef = getShape();

    }
}

Once the ShapeUtils class knows the exact type, so do our methods. This is pretty simple. Now let us try removing the class’ type variable and bounds so that the methods specify their own generic type variables.

  public class ShapeUtils {      <T1 extends HasCoordinates & CalculateArea> void echoCoordinates(T1 shape) {          //...      }      <T2 extends CalculateVolume> void echoVolume(T2 shape) {          //....      }  }

Note that now we need the angled brackets for the method type variables because the methods themselves are generic. We may use the same ampersand operator to add additional types.

 public class Main {

    public static void main(String[]args) {

        ShapeUtils sUtils = new ShapeUtils();
        MovingCube mCube = new MovingCube();

        sUtils.echoCoordinates(mCube);
        sUtils.echoVolume(mCube);
    }
}

Generic methods behave very much like normal methods because type requirements are resolved during the method’s call using Java’s built-in type deduction process.

Why are there no generic return values? Our first example used the class’ type variable to determine a desired type. The instance methods use that type, so it is clear what they must return. In the case of methods with their own generic type variables, things are more difficult.

The methods need some hint as to what they will return, otherwise we would have to use either reflection or typecasting to make this work. We must also ask if this is what we want. If a method returns a type and we are to store it, then it will be much easier to do if we know what type of return value to anticipate.

## 9.5 Generic Reference Variables as Method Parameters and Return Types

When we write methods that accept reference variables from generic classes, we must provide type arguments in the method’s parameter itself. The same can be said for any return types we specify in the method’s header. They too must provide a type argument for the reference variable they will return.

Let us assume we have a generic class that accepts one of our shapes. To accept or return instances of this class, we must write methods that account for the class’ generic type.

public class CubeHolder<T extends Cube> {      T cube;  }

The CubeHolder class requires a parameter on instantiation. The way that we would write a simple setter or getter method for this class is as follows:

public class ShapeUtils {            CubeHolder<Cube> myCube;      public void cubeSetter(CubeHolder<Cube> myCube) {          myCube = cube;      }      public CubeHolder<Cube> cubeGetter() {          return new CubeHolder<Cube>();      }

What is important to recognize that this version of the ShapeUtils class is not generic, though it sends, receives and holds object references of a generic class.

Remember that once we supply a type argument to a generic class, the type it is no longer subject to change. This is why the cubeGetter return type does not require any type casting. It is set to return a very specific instance of the CubeHolder class.

## 9.6 Multiple Type Variables

Once you are comfortable with single generic type variables, it is easy to add more. All we must do is add another generic variable name and separate it with a comma. We may observe multiple generic variables in the JDK’s Hashmap for example.

public class ShapeUtils<T1 extends HasCoordinates, T2 extends CalculateVolume> {  //...  }

Note that it is the comma that separates different type variables. We may wish to add more types to the variable’s bound, so we must simply add them with the ampersand operator.

public class ShapeUtils<T1 extends HasCoordinates & Rounded3D, T2 extends  CalculateVolume & CalculateArea> {  //...  }

To instance either of these examples, we must provide a pair of type arguments separated by commas and in the order that we declared them in the class itself.

public class Main {
    public static void main(String[]args) {

        ShapeUtils<MovingCylinder,Cube> shapeUtils = new ShapeUtils<>();
    }
}

We may add many type variables in a single class or method, though for practicality’s sake we will stick to only two for now.

## 9.6.1 Multiple Method Type Parameters

Methods with multiple type parameter variables work much like their single variable counterparts. Keep in mind that without an access specifier such as public or protected methods may look a little odd because they will start with the type syntax. Rest assured, they function quite normally.

public class ShapeUtils {      <T1 extends HasCoordinates, T2 extends CalculateArea> void      echoCoordsAndVolume(T1 shapeLocation, T2 shapeArea) {          //...      }  }

This method handles two different typed variables. Just like a single method, we do not need to provide any type arguments when we call a generic method in a class such as this.

 public class Main {

    public static void main(String[]args) {

        MovingCube cube = new MovingCube();
        MovingSphere sphere = new MovingSphere();
        ShapeUtils utils = new ShapeUtils();

        utils.echoCoordsAndvolume(cube, sphere);
    }
}

## 9.7 Erasing too Much With Raw Types

We must remember that generics erase type data. If we were to instance a generic class without providing a type argument, then we would effectively tell the Java compiler to erase all type data until we are left with the base Object type.

This costs us type safety and clarity. Below is an example of what we must avoid.

public class ShapeUtils<T extends Cube> {            T rawType;      //...        }

Now we forget to add a type argument for the generic class…

public class Main {

    public static void main(String[]args) {

        ShapeUtils cubeUtils = new ShapeUtils();
        cubeUtils.rawType = new Cube();
        //this will compile, but it is not what we want.
    }

/* This code may or may not give you a warning depending
on your IDE and compiler settings. */

}

Because we have erased all of the type data for the ShapeUtils type parameter, we cannot call any of the Cube class’ object methods from the rawType field. As far as types are concerned, the reference stored in the rawType field is just the base Object type.

Even if the generic variable in the ShapeUtils class had no bounds, then we would still gain some type safety and specificity by providing a type argument on instantiation.

When it comes to generic methods, they may declare parameterized types as raw types and we do not want this either. This is especially troublesome because we do not declare any type arguments with method calls.

public class ShapeUtils {            CubeHolder myCube;      public void cubeSetter(CubeHolder myCube) {          myCube = cube;      }      public CubeHolder cubeGetter() {          return new CubeHolder();      }

Above we have the old CubeHolder example. The class is parameterized, but when we omit the type arguments in our two methods, it becomes a raw type. That means we will know the object reference’s type, but not the type that it holds. We must avoid doing this as well.

It is important to provide type arguments in both methods and classes so as not to treat any parameterized types as raw, even in cases where the type parameter is unbound. As to why raw types are even allowed in Java, this is a measure to preserve legacy code bases that predate Java’s generic system, so it is rare if ever that we will want to use raw types in our code.

* * *

This chapter introduced a lot of concepts regarding Java’s generic types. To summarize the ideas more briefly: We assign a type variable and describe what types may replace it. Then, when declaring that generic class, we provide one or more compatible types for its parameter(s). Generic methods are the same, but the type arguments are inferred from the object reference that the method receives.

Here are some key points from this section:

*   Type bound generic parameters are both expressive and precise.

*   Type parameters appear in methods, classes, or both.

*   We can use the ampersand operator to specify additional types that satisfy the generic variable(s).

*   We fill generic parameters with class or interface names on class instantiation.

*   Methods resolve type requirements when we call them and send object references.

Now that we have seen some of what generics have to offer us, we will work through the complete example in the next chapter.

* * *

# CHAPTER 10: FULL GENERIC EXAMPLES

The previous chapter introduced a lot of new concepts to learn and use in our code. The examples in that chapter were not fully written as to keep things somewhat brief. Now that we have some idea of what generics look like and how they work, we will write the MovingSphere and MovingCube classes so that they make full use of generics.

## 10.1 The ‘HasCoordinates’ Interface & ‘ShapeCoordinates’ Class

First, we want a MovingCube and MovingSphere. These will both require a set of x and y coordinates and a few methods to get/set the values. Instead of fully implementing the HasCoordinates interface for each movable 3D object, we will use a clever trick with interfaces from the decorator design pattern.

First, we write the HasCoordinates interface.

 public interface HasCoordinates {

    void setCoordinates(int x, int y, int z);

    int getCoordinateX();
    int getCoordinateY();
    int getCoordinateZ();
}

Now that we have an interface for position and movement, we will implement it in a ShapeCoordinates class.

public class ShapeCoordinates implements HasCoordinates {

    int coordinateX;
    int coordinateY;
    int coordinateZ;

    public ShapeCoordinates(int x, int y, int z) {
        setCoordinates(x,y,z);

    }

    @Override
    public void setCoordinates(int x, int y, int z) {
        this.coordinateX = x;
        this.coordinateY = y;
        this.coordinateY = z;
    }

    @Override
    public int getCoordinateX() {
        return this.coordinateX;
    }

    @Override
    public int getCoordinateY() {
        return this.coordinateY();

    @Override
    public int getCoordinateZ() {
        return this.coordinateZ();

    }
}

We now have an implementation for the HasCoordinates interface. We will move on to the Movable classes and give each their own instance of the ShapeCoordinates class.

## 10.2 The MovingCube and MovingSphere

Now we will make two new classes, though we could make as many new shapes as we want because of how we have structured our code to be reusable. First, the new cube.

public class MovingSphere extends Sphere implements HasCoordinates {

 HasCoordinates coordinates;

  MovingSphere(double radius, int x, int y, int z) {
    super(radius);
    this.coordinates = new ShapeCoordinates(x,y,z);
  }

  @Override
  public void setCoordinates(int x, int y, int z) {
    coordinates.setCoordinates(x,y,z);
  }

  @Override
  public int getCoordinateX() {
    return coordinates.getCoordinateX();
  }

  @Override
  public int getCoordinateY() {
    return coordinates.getCoordinateY();
  }

  @Override
  public int getCoordinateZ() {
    return coordinates.getCoordinateZ();
  }
}

Note how when we implement the HasCoordinates interface, we simply refer to the reference variable stored in the position field. This saves us from rewriting the code.

The above code is all that it takes to make a new class that extends the functionality of the Cube and adds coordinate data. Let us do the same for the sphere class.

## 10.3 The ShapeUtils Class

Here we will write a simple shape utility class that is specifically tailored for three dimensional objects with coordinates. We will use some parameterized generics for the methods that calculate and store strings for a full report.

 public class ShapeUtils {

    private<T1 extends HasCoordinates> String coordsText(T1 shape) {
        String msg;
        msg = "x coordinate: " + shape.getCoordinateX();
        msg += "\n" + "y coordinate: " + shape.getCoordinateY();
        msg += "\n" + "z coordinate: " + shape.getCoordinateZ();
        return msg;
    }

    private<T2 extends CalculateVolume & CalculateArea> String measurementText(T2 shape) {
        String msg;
        msg = "surface: " + shape.calculateArea();
        msg += "\n" + "volume: " + shape.calculateVol() + "\n";
        return msg;
    }

    public<T extends Calculate3D & HasCoordinates> String fullReport(T shape, String shapeName) {
        String report = shapeName + "\n";
        report+= coordsText(shape);
        report+= measurementText(shape);
        return report;
    }

    public<M extends HasCoordinates> void moveShape(M shape,int x, int y, int z) {
        int updateX,updateY,updateZ;
        updateX = shape.getCoordinateX() + x;
        updateY = shape.getCoordinateY() + y;
        updateZ = shape.getCoordinateZ() + z;
        shape.setCoordinates(updateX, updateY, updateZ);
    }

}

This shape utility class is only the beginning of what we can do with generic typed methods and classes. We will now run it from our main method to see how it all works.

public class Main {    public static void main(String[]args) {      MovingCube mCube = new MovingCube(10, 10,30,43);      MovingSphere mSphere = new MovingSphere(7 ,50,10,65);      ShapeUtils utils = new ShapeUtils();      System.out.println(utils.fullReport(mCube,"cube"));      System.out.println(utils.fullReport(mSphere,"sphere"));      utils.moveShape(mCube,-20,2,2);      System.out.println(utils.fullReport(mCube,"movedCube"));    }  }

The utility class will now take compatible object references and print the results. It will also modify the coordinates of your classes with the moveShape method.

* * *

You may decide to continue the example and add more methods that compare and modify three dimensional objects. It is also possible to write additional objects for variety. As far as examples are concerned, we are finished with the shape classes, though are not finished with generics.

* * *

# CHAPTER 11: GENERIC TYPES II - GENERIC INTERFACES

For our final chapter we will continue with generics and finish with another example. Here is where we combine generics, interfaces and abstract methods. By using all three, we will see the full power of Java’s abstraction.

Let us begin.

## 11.1 Generic Interfaces

There are a few key differences between generic classes and interfaces. First, we already know that for each implementation of an interface its behavior may vary. Generic interfaces take this a step further by allowing us to specify a type argument each time we implement them in a class.

First, we will write a class named ItemBox with a type variable that must extend or implement Item.

public  class Item{}

We do not need to fill the class details for these examples.

public interface ItemBox<T extends Item>  {  ///...  }

When we write our ItemStorage class, we use the Interface as a type bind for T.

public class ItemStorage implements ItemBox<Item> {  }

We implement the interface and fill the type argument here instead of during instantiation. This will be easy to remember as a rule if you think of all interface requirements as the implementing class’ responsibility.

  public class Main {      public static main(String[]args) {                    ItemStorage storage = new ItemStorage();      }  }

When a class implements a generic type variable while having its own, things may look a little complicated, but once we have handled the interface’s type argument, we may then instance the generic class like we normally would.

public class ItemUtils {}

public class ItemStorage<T extends ItemUtils> implements ItemBox<Item> {

    T utils;
}

Here we must fill the interface’s type argument first, then the class’ type argument when instancing it.

public class Main {      public static main(String[]args) {                    ItemStorage<ItemUtils> storage = new ItemStorage<>();      }  }

What generic interfaces allow us to do is set their type arguments differently for each class they appear in. This makes our interfaces even more reusable than before.

For our next section, we will add some generic abstract methods to our ItemBox.

## 11.2 Generic Abstract Methods

Generic abstract methods are not so different from normal generic methods. Parameterized types either resolve type data by their interface’s type parameter, or they will do it themselves with the same type deduction process that non-abstract methods use.

Here is an example where the same type variable appears in the interface and method’s parameters. The method’s type variable takes its bind(s) from the interface.

public interface ItemBox<T extends Item>  {            void setItem(T item);      T getItem();  }

These two simple generic methods will use the type variable T to determine what object references they will accept and return. Here they are implemented in the ItemStorage class.

public class ItemStorage implements ItemBox<Item> {      Item item;      @Override      void setItem(Item item) {          this.item = item;      }      @Override      Item getItem() {          return this.item;      }  }

The methods take the Item parameter from their interface’s implementation. If we remove the interface’s type variable, we would have to specify both of the generic typebounds as in the example below.

public interface ItemBox  {

    <T extends Item> void setItem(T item);

    Item getItem();

}

I have used Item as a return type for the getItem class. Another thing we could do is either add the interface’s parameter back into the interface, or move the getItem method into another interface where the type parameter belongs to the interface and the return type will not be ambiguous.

  public interface ItemBox {      <T extends Item> void setItem(T item);  }  public interface ItemCollector<I> {      I getItem();  }

To use both methods we would simply implement both interfaces in our ItemStorage class.

public class ItemStorage implements ItemBox, ItemCollector<Item> {

    Item item;

    @Override
    public Item getItem() {
        return this.item;
    }

    @Override
    public void itemBoxSetter(ItemBox<Item> itm) {
        this.item = itm;
    }
}

Now that the ItemCollector interface and its abstract method are separate, we may set the collected type to what ever we want and use the abstract method in many different places.

## 11.3 Final Generic Example

There are countless ways that we could use interfaces and there are still rules and nuances that are too numerous to cover in this book. What we will do in this section is show how a single generic abstract method may be instanced in three different ways to either save or write simple text messages.

First, we will make an enumerator that can tell the difference between savable and printable text.

  public enum MessageTypes {            SAVE, PRINT;  }

Now we will make the TextItem class that holds either of these two states.

 public class TextItem {

    String text;
    MessageTypes type;

    public TextItem(String msg, MessageTypes type) {
        this.text = msg;
        this.type = type;
    }
}

We will need an way to call the same methods with a different body. A generic abstract method will allow us to swap out the TextItem for another compatible type later if we choose to extend the class or make another.

  public interface TextConsumer<T extends TextItem> {      void processText(T text);  }

Our first class to implement the TextConsumer interface will be simple. All it must do is take the text and print it to our terminal.

public class MessageReader implements TextConsumer<TextItem> {      @Override      public processText(TextItem item) {          System.out.println(item.text);            }  }

This does not justify using an abstract method, so let us add another class that is made to handle messages set to SAVE. It will be somewhat more complex and will require a few imports from the JDK.

  import java.io.IOException;  import java.io.FileWriter;  public class MessageWriter implements TextConsumer<TextItem> {            String path;      String text;            FileWriter write;            public MessageWriter(String path) {          this.path = path;      }      @Override      public void processText(TextItem item) {          try{              write = new FileWriter(this.path, true);              //'true' means that it will append the text              write.write(item.text);              write.close();          } catch (IOException e) {              e.printStackTrace();          }      }  }

This may look a little complex, but it is quite simple. The path string holds the name and destination of a file. Without a full path, the file writer should use the filename you supply as an argument and save the file to your project’s working directory. Optionally, you may specify a different path to somewhere else in your filesystem.

Finally we must make a class that differentiates between savable and printable message items. It too may implement the same TextConsumer interface.

  public class MessageDispatcher implements TextConsumer<TextItem> {      MessageWriter write;      MessageReader read;      public MessageDispatcher(String savePath) {          this.read = new MessageReader();          this.write = new MessageWriter(savePath);      }      @Override      public void processText(TextItem item) {                    switch(item.type) {              case PRINT: read.processText(item);              break;              case SAVE: write.processText(item);              break;          }      }  }

Now that we have all of our classes together, let us send a few messages through the system and see what happens.

public class Main {

  public static void main(String[]args) {
    String greet = "hello in final example";
    String farewell = "thank you for reading "
        + "Instantiating Success in Java. \n A book by Arthur White";

    TextItem myGreeting = new TextItem(greet, MessageTypes.PRINT);
    TextItem myFarewell = new TextItem(farewell, MessageTypes.SAVE);

    MessageDispatcher handleMessage = new MessageDispatcher("messageFile.txt");

    handleMessage.processText(myGreeting);
    handleMessage.processText(myFarewell);
  }
}

The above example should take both of the text items and either print or save them depending on their enumerated values. This concludes the final example of this book.

## Book End

The concepts in this book appear will appear throughout the major frameworks and libraries that you encounter. You will eventually be able to understand these programming concepts by their syntax alone, as well as implement them in your own code, and it is encouraged that you do so.

When it comes to practice, the old adage, the more the merrier is certainly true. There really is no better way to gain familiarity with an idea than to put it into practice as often as possible. When it comes to production or project code, however, you must also gain the skill to determine when such features add anything other than clutter. Of course, this is a topic for another time.

This concludes Instantiating Success in Java. The book has been a pleasure to write and if you have enjoyed reading it, or have at least found it helpful, then please consider giving this book a positive review and recommending it to a friend so that they too, may instantiate success.

# Instantiating Success in Java: The Definitive Guide to Object Oriented Power

[INTRODUCTION](#part0002.xhtml)

[CHAPTER 1: GETTING STARTED](#part0003.xhtml)

[1.1 Choosing an IDE](#part0003.xhtml_aTU)

[Intellij](#part0003.xhtml_aTV)

[Eclipse](#part0003.xhtml_aTW)

[Netbeans](#part0003.xhtml_aTX)

[Other Options](#part0003.xhtml_aTY)

[1.2 The Java Development Kit](#part0003.xhtml_aTZ)

[1.3 Naming Conventions](#part0003.xhtml_aU0)

[Simple Variables](#part0003.xhtml_aU1)

[Methods](#part0003.xhtml_aU2)

[Constant Values](#part0003.xhtml_aU3)

[Enumerators](#part0003.xhtml_aU4)

[Classes](#part0003.xhtml_aU5)

[Constructors](#part0003.xhtml_aU6)

[Packages](#part0003.xhtml_aU7)

[CHAPTER 2: CLASSES AND PACKAGES](#part0004.xhtml)

[2.1 What Exactly are Packages?](#part0004.xhtml_aU9)

[2.2 Fully Qualified Names](#part0004.xhtml_aUA)

[2.3 Import Statements](#part0004.xhtml_aUB)

[CHAPTER 3: DATATYPES AND OBJECTS](#part0005.xhtml)

[3.1 How Classes Relate to Objects](#part0005.xhtml_aUD)

[User Defined Types](#part0005.xhtml_aUE)

[3.2 Class Instances](#part0005.xhtml_aUF)

[3.3 Static And Instance Members](#part0005.xhtml_aUG)

[3.4 Static VS Instance Memory](#part0005.xhtml_aUH)

[3.5 “this” Keyword](#part0005.xhtml_aUJ)

[CHAPTER 4: OBJECT REFERENCES](#part0006.xhtml)

[4.1 Pass by Value or Reference](#part0006.xhtml_aUM)

[4.2 Getting and Setting References](#part0006.xhtml_aUN)

[4.3 The LineUtils Class](#part0006.xhtml_aUP)

[4.4 Null References](#part0006.xhtml_aUR)

[CHAPTER 5: CONSTRUCTORS](#part0006.xhtml_aUS)

[5.1 Default Initializer](#part0006.xhtml_aUT)

[5.2 Parameterized Constructors](#part0006.xhtml_aUU)

[5.3 Plotting a Triangle](#part0006.xhtml_aUV)

[5.4 Calling Parameterized Constructors](#part0006.xhtml_aUW)

[5.5 Private Constructors and Static Methods](#part0006.xhtml_aUX)

[CHAPTER 6: INHERITANCE](#part0007.xhtml)

[6.1 Subclassing Rules](#part0007.xhtml_aUZ)

[6.2 The ‘Super’ Keyword](#part0007.xhtml_aV0)

[6.3 SuperConstructors](#part0007.xhtml_aV1)

[6.4 Protected Member Inheritance](#part0007.xhtml_aV2)

[CHAPTER 7: ABSTRACT CLASSES & METHODS](#part0008.xhtml)

[7.1 The Initial Classes](#part0008.xhtml_aV4)

[7.2 The Abstract Class and Abstract Methods](#part0008.xhtml_aV5)

[7.3 The Abstract Shape Class and Methods](#part0008.xhtml_aV6)

[CHAPTER 8: INTERFACES](#part0009.xhtml)

[8.1 Type By Implementation](#part0009.xhtml_aV8)

[8.2 Multiple Implementations](#part0009.xhtml_aV9)

[8.3 Mixing Implementation and Inheritance](#part0009.xhtml_aVA)

[8.3.1 An Optional Cylinder](#part0009.xhtml_aVB)

[8.4 Accepting Interface References](#part0009.xhtml_aVC)

[CHAPTER 9: GENERICS I](#part0010.xhtml)

[9.1 A Growing Need for Generics](#part0010.xhtml_aVE)

[9.2 Bound Generic Types](#part0010.xhtml_aVF)

[9.3 Multiple Bound Generic Types](#part0010.xhtml_aVG)

[9.4 Type Bound Generic Methods](#part0010.xhtml_aVH)

[9.5 Generic Reference Variables as Method Parameters and Return Types](#part0010.xhtml_aVJ)

[9.6 Multiple Type Variables](#part0010.xhtml_aVK)

[9.6.1 Multiple Method Type Parameters](#part0010.xhtml_aVM)

[9.7 Erasing too Much With Raw Types](#part0010.xhtml_aVN)

[CHAPTER 10: FULL GENERIC EXAMPLES](#part0011.xhtml)

[10.1 The ‘HasCoordinates’ Interface & ‘ShapeCoordinates’ Class](#part0011.xhtml_aVR)

[10.2 The MovingCube and MovingSphere](#part0011.xhtml_aVS)

[10.3 The ShapeUtils Class](#part0011.xhtml_aVT)

[CHAPTER 11: GENERIC TYPES II - GENERIC INTERFACES](#part0012.xhtml)

[11.1 Generic Interfaces](#part0012.xhtml_aVV)

[11.2 Generic Abstract Methods](#part0012.xhtml_aVW)

[11.3 Final Generic Example](#part0012.xhtml_aVX)

[Book End](#part0012.xhtml_aVY)