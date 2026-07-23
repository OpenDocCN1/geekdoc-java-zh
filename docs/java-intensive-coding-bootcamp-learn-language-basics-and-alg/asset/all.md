![](cover1.jpeg)

JAVA INTENSIVE CODING BOOTCAMP: LEARN LANGUAGE BASICS AND ALGORITHM

More than Hundred Difficult Problems with Solutions - Explained Step by Step, Designed for Absolute Beginners

Sanjib Sinha

© 2020-21 Sanjib Sinha

Chapter One: Java, a High Level Language with a Purpose

A high level language is closer to human language. It is more or less machine or computer independent. Java fits into this puzzle because it satisfies every condition of a high level language. Because of Java Virtual Machine (JVM),it is machine independent. When Java was created, the slogan had been – code once, run everywhere. A beginner might find this difficult to understand; we will talk about them later, in detail.

As you go further down in the language tree, you will find assembly language just below any high level language. On a floor below there is machine language, which is closer to the hardware.

Machine language is really different. It is only understood by the computer. It is a collection of binary digits or bits that only computer can understand. Computer can read and interpret that 0 and 1\. Therefore, every high level language should be translated to machine language so that it can finally talk to the hardware.

Being able to talk to the hardware is the final target where every high level language shoots at.

Starting with Fortran, C, Pascal, C++, we can name many more popular high level languages besides Java, such as PHP, Python, Dart, etc.

We can also compare this programming language tree with human language like English. According to John Collinson Nesfield’s “English Grammar, Past and Present; With Appendices on Prosody, Synonyms, and Other Outlying Subjects”, the language English belongs to the Aryan family of Languages. The immediate ancestor of English is Teutonic. From Teutonic, comes Low German (including English) and High German.

Now consider a human being who is neither able to speak, nor he can hear. In that case, we use sign languages to create some images. The activity of communication is done by those images. Letters are visual representation of alphabets.

A natural language starts with alphabets or letters, and words are built with letters; remember, there is a difference between letters and alphabets, although people think they are essentially same. Anyway, let us move ahead with words. With the help of words, we make sentences; and, sentences make paragraphs, essays, stories, poems, plays, etc.

Words cannot be placed randomly to make sentences. That does not make any sense. Therefore, between words and sentences, comes in grammar.

What is grammar? A set of rules that arranges words to make sentences meaningful. Without those rules we cannot make meaningful sentences. Without meaningful sentences we cannot create meaningful paragraphs, stories, poems, etc. Even we cannot communicate meaningfully with another person.

We can conclude that every natural language has a purpose, either you want to write something meaningful, or speak to somebody meaningfully.

That is true for any programming language. Every programming language has a purpose. In some cases, it is targeted to do some specific tasks, such as, at the time of its creation, PHP was meant to make a website dynamic. Now PHP is a general purpose language; with its help we not only make a small website dynamic, but also we create more robust and complex web applications.

The same is true for Java. Study the history of Java. You will find how it has evolved to be a general purpose object-oriented-programming language that runs billions of disparate devices. You will find Java in smart TV, satellite, cooking devices, artificially intelligent objects, robust and complex software, like desktop and web applications, Android mobile applications, etc; the list is endless.

Just like natural languages, without knowing the grammar or the language basics of Java, we cannot make such software or applications. Therefore, we have a purpose to learn Java. And, Java is a general purpose language that could create different types of applications.

Who Should Read this Book and What about the Next Bootcamp

This book will empower computer science and programming students to learn the language basics of Java; so that, they could build applications in Java. It is for the first time that a book with a “problems-solutions-explanations” approach using “Direct Method”; it is like an intensive coding bootcamp where participants will take active part to develop their logical and analytical thinking so that they could solve interactive problems. For that reason, we will get our head around the basics of Data Structures and Algorithm also.

We are learning the language basics of Java together to solve many types of problems first. It will help us to build applications that are discussed in the next Java bootcamp series, where we will develop applications. Here, in this first bootcamp, we will start writing code first. If you cannot take a short swim in the pool, you cannot learn swimming. Therefore, we will learn about objects and classes, primitive data types, arrays, logical if-else, switch-case, loop constructs, etc by solving problems.

Let us start with small programs, the result follows; since it is caused by some phenomenon, we will learn the theory thereafter. We will study the problem first, then we solve it and practice some more relevant problems. After that we will discuss theory.

After all, we want to build many applications with the help of Java, that is our main purpose of learning Java. Although the Abstraction stays behind the curtain, we will learn them with the help of our problems.

As we progress, by solving more than 100 problems from simple to complex, we will learn the Java language basics and its related core concepts.

High Level to Machine Language

Let us see a simple Java program that takes input from a user and gives an output, such as “Hello World”.

 1 //Problem 1
2 //code 1
3 package fun.sanjibsinha;
4
5 import java.util.*;
6 import java.util.Scanner;
7 import java.lang.String;
8 public class Main {
9
10     public static void main(String[] args) {
11     // write your code here
12         String s;
13         Scanner in = new Scanner(System.in);
14         System.out.println("Enter a string");
15         s = in.nextLine();
16         System.out.println("You entered string " + s);
17
18     }
19 }

And here is the output:

1 Enter a string
2 Hello World
3 You entered string Hello World
4
5 Process finished with exit code 0

However, the text “Hello World” looks completely different in machine language (binary). Here is the output:

1 01001000 01100101 01101100 01101100 01101111 00100000 01010111 01101111 01110010 011\
2 01100 01100100

I hope now you can understand why we need a high level language to build applicable software. It is impossible for us to write a simple “Hello World” in machine language.

In human language, the same thing happens.

It is easier to say, “Good Morning”. If you had to draw an image to convey the same message, it would be cumbersome and seemed to be an impossible task for most of the humans.

When somebody wishes “Good Morning”, our brain processes that message and actually forms an image inside our mind. In case of high level programming language, the compiler does that processing job, and converts the high level language to machine language (binary).

The following figure (Figure 1.1) gives you an idea how it goes like.

![Figure 1.1 – The Language tree comparing Humans and Machines](OEBPS/Image00000.jpg)

Figure 1.1 – The Language tree comparing Humans and Machines

We have already seen our first problem (Problem 1) of the book. If you are a beginner, the first problem really does not convey any meaningful message to you. However, we have learned one thing, specifically, how to take input from a user and give an output. We’ll dissect that problem later and learn how it works.

We have also learned another important lesson: it is very difficult to give the same output in machine language (binary). Therefore, we need high level language like Java to write code that will build an applicable software or application; web and mobile both.

Furthermore, we have also seen when we write a code in high level language, it is ultimately translated to binary code. Hardware does not understand anything but binary.

Memory allocation, heap and stack

As a beginner, you need to have an idea about what is going on behind the curtain, especially when we write a code and execute it.

So far, we have learned one important lesson: our code ultimately talks to the hardware in binary code. Whatever we write in Java is translated to 0 and 1\. But where it is stored? Here comes the idea of memory. In computing, memory refers to a device that is used to store information for immediate use. Therefore, we can say that memory is actually a primary storage.

At the same time, memory management is also very important. When we write a code and execute it, computer dynamically allocates some memory to the program and free it for reuse, when it is no longer needed.

As you progress, you’ll find that in Java programming, we will write many classes and create objects. Every class has a main() thread where the program is executed. As memory management essentially deals with space, we will find two terms quite regularly in Java programming. One is “heap” and the other is “stack”.

When we write a class, and create an object, it is created always in the heap space. However, Java uses its Stack memory to execute all the threads, such as attributes and methods; that is, this space is allocated not only for the main() method, but also all the attributes and methods we create inside any class. Consider the problem one or code one.

In our first problem, we have taken a string input from the user and given an output of that string. There was no extra class or object we have created. Now, we are going to create two extra classes and related objects and at the end, we are going to give a string output of that object. For a beginner this code looks a little bit weird and difficult. But, please stick around. we’ll explain class, object and every other primitive data types in the coming chapters with rather simple problems and solutions. Now, we have our second problem at hand, where we have this code:

 1 //Problem 2
2 //code 2
3 package fun.sanjibsinha;
4
5 import java.util.*;
6 import java.util.Scanner;
7 import java.lang.String;
8
9 class MyObject{};
10 class MyMemory{
11
12     void myMethod(MyObject myParam) {
13         String str = myParam.toString();
14         System.out.println(str);
15     }
16 };
17
18 public class Main {
19
20     public static void main(String[] args) {
21     // write your code here
22         String s;
23         Scanner in = new Scanner(System.in);
24         System.out.println("Enter a string");
25         s = in.nextLine();
26         System.out.println("You entered string " + s);
27         MyObject myObj = new MyObject();
28         MyMemory myMem = new MyMemory();
29         myMem.myMethod(myObj);
30     }
31 }

And here goes the output:

1 //output of problem 1
2
3 Enter a string
4 sanjib
5 You entered string sanjib
6 fun.sanjibsinha.MyObject@573f2bb1
7
8 Process finished with exit code 0

Let me explain the code first. We have created two classes. Inside one of the classes, we have created a method where we have passed another class object as a parameter. We have converted that object into string and given an output.

In the main() method, we have created two new objects of those classes and finally called that method through one object.

The question is, how computer allocates memory for those newly created objects and all the attributes and methods including main().

The allocation goes like this:

In the Stack memory, all the attributes, such as “String myStr”, and the method parts like “myMethod(MyObject myParam)”, and main() are stored.

On the contrary, the Heap memory has stored only the classes and newly created objects. The Heap part also manages the garbage collection, which is nothing but freeing the memory spaces.

As a beginner, you need to understand one thing very clearly. These memory allocation part is going on simultaneously. You don’t have to worry about that. However, you need to know how things happen behind the curtain.

If situation arises, we’ll discuss this in detail, in future.

In the next chapter, we will discuss what type of code editors we should use to write and to run our Java code what extra features we need. Before that, we need to know more about objects and classes. Because Java is an object-oriented-programming language, we should know how objects interact with each other.

1 Tips: In any software or any type of application written in an object-oriented-progr\
2 amming language like Java, objects communicate with each other, passing messages.

What are Objects, Why they are Important

Here we are going to see how objects contain other objects,communicate with each other. We have seen an example before, where we have created new objects, and pass objects through methods.

If you have never used object-oriented-programming language before, you need to know the basic concepts first. After that you can write your code.

In this section, we will have a quick introduction to objects and classes. In a later chapter, we will discuss them in detail. Therefore, we need to know what is an object. We have already known that Java is used to create software or web or mobile application. They are also a kind of software packages, nonetheless.

A software is basically a bundle of many states and behaviors. A software can have hundreds and thousands objects joined together in a way so that they can communicate with each other to run the software perfectly. Therefore, an object is essentially made of some states and behaviors. Suppose a Person object has states like ‘color of eyes’. We can change that state by one behavior, such as ‘Wear a contact lens’.

Software objects are often used to model the real life objects that we see around us everyday. We have seen a Person object, just now. When we see a Person object in real world do we know how many states or behaviors are hidden in that Person object? Those states and behaviors are designed and encapsulated such a way that one could not guess it from outside.

However, we must have some mechanism, where we need to define them clearly. The concept of class plays the crucial role here. A class is a blueprint or prototype from which the objects are created.

In the following program we will see how we can create objects; we will also see how classes are written as blueprints of those objects.

I hope you have probably heard the story of Socrates, one of the greatest philosopher who was sentenced to death by the wise men of Athens. Socrates died drinking the poison Hemlock. The reason was quite amazing. Socrates questioned their wisdom and said famously while dying, “an un-examined life is not worth living”. From Socrates’ statement, it is clear that he wanted to examine life by asking questions. But the wise men of Athens did not want that.

Socrates’ friend and student Plato, another great philosopher, wrote about his friends, in fact, in Plato’s many writings, Socrates appeared as one of the central character.

Here, we are going to develop a small console based application that tells us the life story Socrates. There are four objects, Socrates, Plato, Wise men of Athens and the Hemlock. To create those objects, we need to write the blueprints of them first.

Let us first define the Socrates class.

 1 // class of Socrates
2 // blueprint of Socrates object
3 package fun.sanjibsinha.object;
4
5 class Socrates {
6 public String name = "Socrates";
7 WiseMen wise;
8 Hemlock hemlock;
9
10 public void questionWiseMen(WiseMen wise){
11 this.wise = wise;
12 System.out.println(this.name + " questioned the wisdom of " + wise.name);
13 }
14
15 public void sayToWiseMen(WiseMen wise){
16 this.wise = wise;
17 System.out.println(this.name + " said to the " + wise.name + " hearing" +
18 " his death sentence, 'an unexamined life is not worth living'.");
19 }
20
21 public void dieByDrinking(Hemlock hemlock){
22 this.hemlock = hemlock;
23 System.out.println(this.name + " died drinking " + hemlock.nature);
24 }
25 }

After that we need a Plato class, similarly, with some states and methods.

 1 // class Plato
2 // blueprint of Plato object
3 package fun.sanjibsinha.object;
4
5 class Plato {
6 public String name = "Plato";
7 Socrates socrates;
8
9 public void hasARelationWith(Socrates socrates){
10 this.socrates = socrates;
11 System.out.println(this.name + " had a friendship with " + socrates.name);
12 }
13 public void writesAbout(Socrates socrates){
14 this.socrates = socrates;
15 System.out.println(this.name + " had written about his friend and teacher "
16 + socrates.name);
17 }
18 }

Next, we want the wise men of Athens, who had decided Socrates’ fate, and gave him death sentence.

 1 // class WiseMen
2 // blueprint of WiseMen object
3 package fun.sanjibsinha.object;
4
5 class WiseMen {
6 public String name = "Wise men of Athens";
7 Socrates socrates;
8
9 public void giveDeathSentenceTo(Socrates socrates){
10 this.socrates = socrates;
11 System.out.println(this.name + " had given death sentence to "
12 + socrates.name);
13 }
14 }

The Hemlock object is defined in a small class, where its state has been declared as poison.

1 // class Hemlock
2 // blueprint of Hemlock object
3 package fun.sanjibsinha.object;
4
5 class Hemlock {
6 public String nature = "Poison";
7 }

By reading the above blueprints or classes we can say that they are based on real life story. We have written each class in a way, so that they have some states and behaviors, such as Socrates has states like:

1 public String name = "Socrates";

The Socrates class also has some behaviors like this:

1 public void questionWiseMen(WiseMen wise){
2 this.wise = wise;
3 System.out.println(this.name + " questioned the wisdom of " + wise.name);
4 }

It is clearly seen that behaviors are also called functions or methods. Through any method we can pass one or more than one parameters, such as, here we have passed an ‘WiseMen’ object. We have also given it a name ‘wise’. Now, do not worry about the keywords we have used, like ‘public’, or syntax like ‘;’ that ends an expression. We will learn them later. We have probably noticed that we always follow a sets of rules to write one class from which one or more objects could be created later.

We have also noticed that a class always clearly defines the ‘state’ and ‘behavior’, so that later no disambiguation is formed. Computer does not like ambiguities. It wants clear instructions; a step-by-step instruction.

From the above code it is visible that one or more objects could be ‘state’ of another object. Look at the Socrates class:

1 public String name = "Socrates";
2 WiseMen wise;
3 Hemlock hemlock;

These are all ‘states’ that are defined in Socrates class. Of three states, two are ‘objects’, which have their own classes.

Finally, we want to run the application by creating the objects, and based on the relationship they have, we build our algorithm.

 1 // code of main() method
2 package fun.sanjibsinha.object;
3
4 public class PhilosopherDemo {
5
6 public static void main(String[] args) {
7 Socrates socrates = new Socrates();
8 WiseMen wiseMenOfAthens = new WiseMen();
9 Plato plato = new Plato();
10 Hemlock hemlock = new Hemlock();
11 socrates.questionWiseMen(wiseMenOfAthens);
12 wiseMenOfAthens.giveDeathSentenceTo(socrates);
13 socrates.sayToWiseMen(wiseMenOfAthens);
14 socrates.dieByDrinking(hemlock);
15 plato.hasARelationWith(socrates);
16 plato.writesAbout(socrates);
17 }
18 }

While we run our application, we get this output:

1 Socrates questioned the wisdom of Wise men of Athens
2 Wise men of Athens had given death sentence to Socrates
3 Socrates said to the Wise men of Athens hearing his death sentence, 'an unexamined l\
4 ife is not worth living'.
5 Socrates died drinking Poison
6 Plato had a friendship with Socrates
7 Plato had written about his friend and teacher Socrates

I hope, this example will help you to understand how objects contain other objects, communicating with each other. It is also known as ‘has-a-relationship’. When we inherit one class from another, that is called ‘is-a-relationship’.

We will discuss them later in detail.

Chapter Two: Java Standard Edition Development Kit and IDE

This chapter will be short as we will discuss only two key points here.

To write Java code and run it as well, we need two things in particular. The first one is Java Standard Edition Development kit and the second thing is a good code editor.

Java SE Development kit

Searching Java SE Development kit 11 on web will take you to the web page, https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html, where you can download and install the kit. There are four types of kits available for Linux, Windows, Solaris SPARC, and macOS. Please remember, for this book, I have used Java version 11, which is stable and it is the second long term support release after Java 8\. For your personal purpose it is free, but if you want to use it in commercial purpose, you have to pay.

Another great thing of Java 11 is its compatibility with the code editor IntelliJ IDEA 2018.2.4 Community Edition, which we are going to write and execute our code.

The following image (Figure 2.1) will show you the web page.

![Figure 2.1 – The web page from where you can download Java SE Development kit](OEBPS/Image00001.jpg)

Figure 2.1 – The web page from where you can download Java SE Development kit

According to your operating system, please download and install it so that in your code editor IntelliJ IDEA 2018.2.4 Community Edition will find the path, where you’ve saved the kit. The advantage is plenty. As you progress by solving the problems, you’ll find it. In the next section I’ll give you a few screenshots of IntelliJ IDEA 2018.2.4 Community Edition, which I’ve used for this book projects. Besides, this code editor, there are two great code editors you can always use for your Java application development. They are NetBeans and Eclipse.

IntelliJ IDEA 2018.2.4 Community Edition

Whatever your computer operating system is, you can easily install this code editor. The following image (Figure 2.2) shows you how to choose the path where you’ve installed the Java SE Development kit in your machine.

My operating system is Ubuntu 18\. If you have a different operating system, that path may differ(Figure 2.2).

![Figure 2.2 – Selecting the home directory for the Project SDK](OEBPS/Image00002.jpg)

Figure 2.2 – Selecting the home directory for the Project SDK

Usually, it automatically chooses a home directory by default. However, in most cases, it is wrong. Therefore, you click the “new” button on the right hand side and select the correct path.

The next image (Figure 2.3) will show you what type of application we’re going to make with this code editor.

![Figure 2.3 – We are going to select the Command Line App](OEBPS/Image00003.jpg)

Figure 2.3 – We are going to select the Command Line App

Because we’re going to learn how to code using Java by solving problems, the Command Line App will work fine for us.

The next image (Figure 2.4) will show you how to name the project and where it will be saved.

![Figure 2.4 – Creating the project by giving it a name](OEBPS/Image00004.jpg)

Figure 2.4 – Creating the project by giving it a name

We’ve named this project as “HundredProblemsInJava”. The IntelliJ IDEA 2018.2.4 Community Edition will create the path, where this project will be saved. So you don’t have to worry about it.

As a base package, it will ask for a domain name. Currently, I have a domain https://sanjibsinha.fun, so the base package name will be “fun.sanjibsinha”. If you have a domain booked already, you can use that.

In the next image (Figure 2.5), we see how we can write a code and execute it using IntelliJ IDEA 2018.2.4 Community Edition.

![Figure 2.5 – The main() method and the execution](OEBPS/Image00005.jpg)

Figure 2.5 – The main() method and the execution

The advantage of IntelliJ IDEA 2018.2.4 Community Edition is as a good code editor, it will give you plenty of tips at the time of coding. We will learn it together, as we progress.

Chapter Three: How Java Programming Works

In this chapter we will discuss the difference between Procedural (POP) and Object Oriented Programming (OOP). Using problems, we will also see how Java programming is written within a class. In the context of a problem, we will also learn the role of compiler and interpreter in processing Java code.

Difference between POP and OOP

Java is an object-oriented-programming. Java programming is written within a class. We will see it in a minute. Before that, we would like to know what is the key difference between procedural and object-oriented-programming.

A procedural programming (POP) is governed and executed step-by-step by a set of instruction. So it always maintains a procedure. Here data flows down from the top to the bottom and the priority is given to the functions.

On the contrary, objects are the main focus in the object-oriented-programming (OOP). Objects encapsulate all the procedures written in the class, which is the actual blueprint of the objects. OOP is more secured as there are access specifiers. It is also more readable, because we can write different classes for doing different tasks and make them loosely coupled. There are many more features like method and operator overloading or overriding that are not present in the POP. As you progress, you’ll learn more about this.

Java program is written within a class

Now we come to the problem three, code three, where we will try to understand how a Java program is written within a class.

Consider the problem three, which is a very simple program that gives an output of “Hello World”.

1 //Problem 3
2 //code 3
3 public class Main {
4     public static void main(String[] args) {
5         System.out.println("Hello World");
6     }
7 }

In the above code, we have seen that the program is written within a class “Main”. Inside that Main class we find a “public” method “main()”. This main() method is also “static” and “void”. We will discuss about the term “static” later. The meaning of “void” is it will not return any value.

Inside that main() method, we see this line:

1 System.out.println("Hello World");

When you type the word “System” on your IntelliJ code editor, it will automatically show a “c” icon on the left side. It means, “System” represents a class in Java. After “System”, if you use a DOT “.” notation it will show many hints, of which, we would pick up “out”. When you pick up “out”, the left icon will show a sign of “f”. It means “out” is a field of the class “System”. After using “out”, if we again use a “.” notation, it will again give us many hints. Out of those many hints, we will pick up “println()”. Now on IntelliJ, on the left side of “println()”, it will show an icon of “m”; it means this is a method.

Inside the “println()”, we write “Hello World”, a string value. A string is a sequence of characters. We will discuss about them in detail, very soon.

As we see so far, we have seen that our Main class is stored in the file “Main.java”. Whatever class we build for this project, from now on, the file will have the same extension “.java”. Is there something else behind the curtain?

Yes, there is. The byte code of this Java file is stored inside “Main.class”. In the following image (Figure 3.1) we will find that class. See at the left side of your IntelliJ code editor, you will find a folder called “out/production”. You will find the “Main.class” file inside it.

![Figure 3.1 – The “Main.class” file inside “out/production” folder](OEBPS/Image00006.jpg)

Figure 3.1 – The “Main.class” file inside “out/production” folder

Our problem four consists of this “Main.class” file. Let us see what is inside.

1 //problem 4
2 //code 4
3 package fun.sanjibsinha;
4
5 public class Main {
6     public Main() { /* compiled code */ }
7
8     public static void main(java.lang.String[] args) { /* compiled code */ }
9 }

This is the completion of code, which is also called Java byte code. This byte code of Java is completely platform independent. It can run on Linux, Windows, and macOS, if that computer system has Java Runtime Environment (JRE). JRE released by Oracle is a freely available software for personal use. The recent licensing agreement bars it from using for any commercial purpose.

The following image (Figure 3.2) will show you the web page from where you can download the JRE for your computer. And here is the link: https://www.java.com/en/download/

![Figure 3.2 – The Java Runtime Environment (JRE) download page](OEBPS/Image00007.jpg)

Figure 3.2 – The Java Runtime Environment (JRE) download page

This JRE contains the stand-alone Java Virtual Machine (JVM), which is a virtual machine that enables a computer to run any Java programs as well as other programs written in other languages, which are also compiled to Java Byte Code.

So we have learned many important facts about how a Java source code is compiled to a byte code (Main.class). This byte code goes to Java Virtual Machine (JVM), which is also called Interpreter. It actually interprets the Byte Code into the Native Code that can be run in any operating system.

In the following diagram (Figure 3.3) we have shown how it works.

![Figure 3.3 – How Java source code works as a platform independent Native Code](OEBPS/Image00008.jpg)

Figure 3.3 – How Java source code works as a platform independent Native Code

As the above image shows, we can conclude that Java has some specialty to convert the high level language to machine level language (MLL) . It uses compiler and interpreter, both.

Basically, any high level language either uses compiler or interpreter. A software that accepts the whole program written in high level language and converts it into its equivalent machine language is known as compiler. Each high level language requires separate compiler to convert the source code to machine language. Since a compiler uses the compilation technique as a whole, at once, it is comparatively faster than the interpreter. Although it is slightly difficult to find the errors, because it gives errors as a whole. It cannot indicate logical errors, it only finds syntax errors.

Besides, interpreter conversions are done line by line. Therefore, it is slower than compiler, but finding errors is much easier. If an error is found on any line, the execution stops.

In case of Java, the compiler converts the high level source code into an intermediate Byte Code, which is then converted to Native Code by the interpreter or Java Virtual Machine (JVM). Now, any computer, that has Java Runtime Environment or JRE, can run that Java program.

Here comes our problem five or code five. Consider the problem first and see the output.

 1 //problem 5
2 //code 5
3 package fun.sanjibsinha;
4
5 public class NewClass {
6     public static void main(String[] args){
7         byte numOne = 10;
8         byte numTwo = 12;
9         byte sumOfTwoNumbers = 0;
10         sumOfTwoNumbers = numOne + numTwo;
11         System.out.println(sumOfTwoNumbers);
12     }
13 }

In the output we have got an error, like this:

1 //output of problem 5
2 Error:(8, 34) java: incompatible types: possible lossy conversion from int to byte

We need to find, why this happens? As you know, “byte” is the smallest integer data type. You can assign a byte variable a range of integer value between (-128) to 127\. However, byte has no literals or constants like “int” or “long”. It means you cannot assign an integer constant expression to a byte variable. Another possible explanation that comes to my mind tells us that in Java, the int type is coded using 32 bits and the byte type using 8 bits. If you convert an int to a byte, there is a chance that you may loose information. Yet we can do the same operations using the reference variables. We will discuss that topic in chapter five.

In the above program, when we add two byte variables, it becomes an int literal expression. You cannot equate that with a byte variable anymore. We cannot convert int constant to byte now.

We can solve this problem by two methods. The first solution is here.

 1 //problem 6
2 //code 6
3 package fun.sanjibsinha;
4
5 public class NewClass {
6     public static void main(String[] args){
7         byte numOne = 10;
8         byte numTwo = 12;
9         byte sumOfTwoNumbers = 0;
10         sumOfTwoNumbers = (byte)(numOne + numTwo);
11         System.out.println(sumOfTwoNumbers);
12     }
13 }

And there is no error anymore.

1 //output of problem 6
2 /usr/lib/jvm/jdk12.0.1/bin/java -javaagent:/snap/intellij-idea-community/185/lib/ide\
3 a_rt.jar=37275:/snap/intellij-idea-community/185/bin -Dfile.encoding=UTF-8 -classpat\
4 h /home/ss/IdeaProjects/HundredProblemsInJava/out/production/HundredProblemsInJava f\
5 un.sanjibsinha.NewClass
6 22
7
8 Process finished with exit code 0

The addition of two numbers is not greater than 127\. So if we can convert that integer literal expression to byte by this line:

1 sumOfTwoNumbers = (byte)(numOne + numTwo);

Now the integer literal expression is byte and the value is within the range.

Furthermore, we can solve this problem with another trick, where we can declare the variable “sumOfTwoNumbers” as an integer.

Consider this code:

 1 //problem 7
2 //code 7
3 package fun.sanjibsinha;
4
5 public class NewClass {
6     public static void main(String[] args){
7         byte numOne = 10;
8         byte numTwo = 12;
9         int sumOfTwoNumbers = 0;
10         sumOfTwoNumbers = numOne + numTwo;
11         System.out.println(sumOfTwoNumbers);
12     }
13 }

Here the output is same as before.

1 //output of problem 7
2 /usr/lib/jvm/jdk12.0.1/bin/java -javaagent:/snap/intellij-idea-community/185/lib/ide\
3 a_rt.jar=34621:/snap/intellij-idea-community/185/bin -Dfile.encoding=UTF-8 -classpat\
4 h /home/ss/IdeaProjects/HundredProblemsInJava/out/production/HundredProblemsInJava f\
5 un.sanjibsinha.NewClass
6 22
7
8 Process finished with exit code 0

Here in the above solution, the trick lies in this line:

1 int sumOfTwoNumbers = 0;

As a beginner, it may seem a little bit difficult for you to understand how these data types work. So, in the next chapter, we will discuss this topic along with object-oriented-programming concepts , so that after finishing chapter four you can start writing some simple code snippets on your own.

Chapter Four: Objects and Data Types

In the first part of this chapter we will discuss object-oriented-programming concepts. In the second part we will dig deep into the concepts of primitive and non-primitive types. This discussion will not be a dry potato-fry. We will add some sauce, of course. Our source of spice and sauce is problems-solutions-explanations resources.

We have so far discussed seven different problems. Through those problems, we have tried to understand various basic concepts. From now on, we will identify each problem with an individual class committed to that problem, such as the next problem, that is “Problem eight” will be written as a class “ProblemEight”, “Problem nine” will be written as a class “ProblemNine”, and so on.

Objects Share Two Characteristics

To understand object-oriented-programming technology, we need to understand objects first. We have reproduced real world objects’ behavior and state in the programming world. Looking around us helps us find how the real world objects are moving around us. Humans, dogs, computers, cars, and many many more.

Taking a deep-down-look will give us more insights about objects. We find that real world objects share two characteristics. They all have state and behavior. Humans have state, such as name, height, anger, etc. And they have behaviors, like shouting, walking, running, etc. One thing is pretty sure that each object has its own complexities. It varies. The complexities of a human cannot be the same as a dog. A human can smile. A dog cannot. Instead, they wag their tails. The performance of their behaviors are different. In some cases, comparing the similarities, it seems they may have a parent class. Some objects may contain other objects.

However, we are not going to discuss those topics here. Because this is an introductory chapter to objects and classes, we try to keep it as simple as possible. To start with all we need to know that there is a relation between an object and a class. To create an object, we need to write its states and behaviors inside a class. You may think it as a blueprint.

The problem eight deals with one car object. To make it simple, we keep two states: gear and speed. When gear is up, the speed is increasing. Reducing of the speed is also related to gear. In that case, gear is down. Those are behaviors. The action part of the object. Since we are attributing states (latest speed or gear), we can also call them as attributes of an object. When we change that state or attribute, we need to provide some methods. So a car has a state called speed, and it also has a method called “speedUp” to change that current speed.

Therefore, in a class we need to design and write them separately. Moreover, in some cases, we need some whole numbers; in some cases, we need decimal point values. In many cases, we also need texts, which are actually a sequence of characters. That is why, after a brief introduction to object-oriented-programming, we will discuss primitive data types, such as integers, floating point values, etc.

We need to write a Car class first. After that, we will create a car object inside the main() method.

 1 //problem 8
2 //code 8
3 package fun.sanjibsinha;
4
5 /*
6 Covering objects and classes
7 */
8
9 class Car {
10
11     int speed = 0;
12     int gear = 1;
13
14     void changeGear(int newValue) {
15         gear = newValue;
16     }
17
18     void speedUp(int increment) {
19         speed = speed + increment;
20     }
21
22     void speedDown(int decrement) {
23         speed = speed - decrement;
24     }
25
26     void stateOfCar() {
27         System.out.println(" The speed of car: " + speed + " when gear is :" + gear);
28     }
29 }
30
31 public class ProblemEight {
32     public static void main(String args[]){
33         //creating one car object
34         Car car1 = new Car();
35         car1.changeGear(2);
36         car1.speedUp(10);
37         car1.stateOfCar();
38         car1.changeGear(3);
39         car1.speedUp(30);
40         car1.stateOfCar();
41         car1.changeGear(1);
42         car1.speedDown(35);
43         car1.stateOfCar();
44     }
45 }

Let us first see the output and after that we will dissect the class to understand how it works.

1 //output of problem eight
2 The speed of car: 10 when gear is :2
3 The speed of car: 40 when gear is :3
4 The speed of car: 5 when gear is :1

Reading the code will help you understand how we have declared the states in the Car class, and after that, how we have changed that state by providing some methods. We have created only one car object by using the “new” keyword.

In problem nine, we have introduced another car object and at the same time we have provided another method to stop the car.

 1 //problem 9
2 //code 9
3 package fun.sanjibsinha;
4
5 /*
6 Covering objects and classes
7 */
8
9 class AnotherCar {
10
11     int speed = 0;
12     int gear = 0;
13
14     void changeGear(int newValue) {
15         gear = newValue;
16     }
17
18     void speedUp(int increasing) {
19         speed = speed + increasing;
20     }
21
22     void speedDown(int reducing) {
23         speed = speed - reducing;
24     }
25
26     void stopCar(int noSpeed){
27         speed = speed * noSpeed;
28     }
29
30     void stateOfCar() {
31         System.out.println(" The speed of car: " + speed + " when gear is :" + gear);
32     }
33 }
34
35 public class ProblemNine {
36     public static void main(String args[]){
37         //creating two car objects
38         AnotherCar car1 = new AnotherCar();
39         AnotherCar car2 = new AnotherCar();
40         car1.changeGear(2);
41         car1.speedUp(10);
42         car1.stateOfCar();
43         car1.changeGear(3);
44         car1.speedUp(30);
45         car1.stateOfCar();
46         car1.changeGear(1);
47         car1.speedDown(35);
48         car1.stateOfCar();
49         car2.changeGear(2);
50         car2.speedUp(20);
51         car2.stateOfCar();
52         car2.changeGear(1);
53         car2.stopCar(0);
54         car2.stateOfCar();
55     }
56 }

As you see in the above code, we have created two car objects. We have also provided another method “stopCar” to change the value of the speed to 0\. Here goes the output:

1 //output of problem 9
2 The speed of car: 10 when gear is :2
3 The speed of car: 40 when gear is :3
4 The speed of car: 5 when gear is :1
5 The speed of car: 20 when gear is :2
6 The speed of car: 0 when gear is :1

We have learned a few things about an object. When we create an object, we write the code this way:

1 AnotherCar car1 = new AnotherCar();

You may have noticed that the “AnotherCar” class has no main() method. It is because it is a blueprint of a car object. It is not a complete application. We will use this blueprint or class inside the application class. The application class containing the main() method, has the responsibility to create the objects. Exactly that happens in the above code (problem 9).

We have used the ‘new’ keyword to create a new object which has a blueprint behind it. Inside that blueprint or class, we have mentioned what types of states it should have. We also have methods to change that states.

The name of the car object is eventually ‘car1’; it could have been ‘jaguar’. No matter whatever name you use, keeping contexts in your mind, the names should be meaningful and expressive so that you can read that code and understand it later. Here the name ‘car1’ is also called reference variable that is stored in ‘Stack’ memory. However, the newly created car object is stored in the ‘Heap’ section of memory. This reference variable ‘car1’ in ‘Stack’ points to that newly created object in ‘Heap’. We will discuss this topic in great detail with examples in chapter five, where we will see the difference between different types of variables and nature of data types that used to mention the ‘state’ of the object.

There are some advantages of object-oriented-programming. It is modular. Source code of an object can be written separately and maintained separately. Once created an object can be passed into the system.

The second important thing is, information hiding. The outside world is unaware of what is going inside. The internal implementation is kept hidden.

An object can have immense power. It may contain thousands of other objects inside. It means an object created by a developer can be reused by other developers. Code reuse is another advantage.

We can replace an object with another object, if the first one gives us trouble. When a door handle does not work properly, we change the handle. We don’t have to replace the door.

We will discuss those features in detail later. Before that, we need to know about the primitive and non-primitive data types that are essential for creating an object. However, we will start our next discussion with variables or fields that are used inside the classes.

Moreover, those variables actually represent the states of the objects.

Variables or Fields in Java

In Problem Nine, we have seen two fields in the class “AnotherCar”. They are “speed” and “gear”. We have also learned that they are states of the car object.

The car object stores its states in fields. In Java, the terms ‘field’ and ‘variable’ are both used. In fact, the term ‘variable’ is often more used. Since we store states of an object in variables, we need to be careful about naming them. It should be meaningful. It is also a good practice. If we want to store the state of speed of any object in a variable, the name of the variable should be ‘speed’. Writing ‘s’ instead of ‘speed’, does not convey anything.

Now, we have written the speed like this:

1 int speed = 0;

What does that mean? It is commonly understood that speed of anything should be an integer value. It should not be text string. Therefore, we have written ‘int’ before the variable name. Thereafter, we have initialized the variable with a value 0\. Is that necessary?

We will discuss them in the coming section, where we will talk about primitive data types like byte, short, int, etc,in a minute.

Before that we need to talk more about the naming conventions of variables. I am going to place two problems before you to study – problem ten and eleven, where you will find how we can name variable in different ways.

 1 //problem 10
2 //code 10
3 package fun.sanjibsinha;
4
5 /*
6 rules and conventions for naming fields in a class;
7 the terms variables and fields are both used
8 */
9
10 class Robot {
11
12     int speed = 0;
13
14     void walk(int distance, int hour) {
15         speed = distance/hour;
16     }
17     void run (int distance, int hour) {
18         speed = distance/hour;
19     }
20     void printState() {
21         if(speed <= 5) {
22             System.out.println("The speed of robot is " + speed + ". It walks.");
23         }
24         else {
25             System.out.println("The speed of robot is " + speed + " kilometers per h\
26 our. It runs.");
27         }
28
29     }
30 }
31
32 public class ProblemTen {
33     public static void main(String args[]) {
34         Robot robot1 = new Robot();
35         robot1.walk(40, 2);
36         robot1.printState();
37     }
38 }

We have used very simple if/else logic to check whether the robot walks or runs. Because the speed of the robot is more than 5 here, so the output is obvious.

1 //output of problem 10
2 The speed of robot is 20 kilometers per hour. It runs.

In the above code, we have followed the normal naming conventions. However, before the variable names, we can use ‘$’ or ‘_’ signs. Watch the next problem eleven.

 1 //problem 11
2 //code 11
3 package fun.sanjibsinha;
4
5 /*
6 rules and conventions for naming fields in a class;
7 the terms variables and fields are both used
8 */
9
10 class RobotOne {
11
12     int speed = 0;
13
14     void walk(int $distance, int _hour) {
15         speed = $distance/_hour;
16     }
17     void run(int $distance, int _hour) {
18         speed = $distance/_hour;
19     }
20     void printState() {
21         if(speed <= 5) {
22             System.out.println("The speed of robot is " + speed + ". It walks.");
23         }
24         else {
25             System.out.println("The speed of robot is " + speed + " kilometers per h\
26 our. It runs.");
27         }
28
29     }
30 }
31
32 public class ProblemEleven {
33     public static void main(String args[]) {
34         RobotOne robot1 = new RobotOne();
35         robot1.walk(10, 2);
36         robot1.printState();
37     }
38 }

The above code breaks the normal conventions of naming the variables and used the special characters like ‘$’ and ‘_’. Still the program runs fine, and gives us the following output:

1 //output of problem 11
2 The speed of robot is 5\. It walks.

The convention is you should always begin your variable name with a letter. Using ‘$’ or ‘_’ is not encouraged. As we have been told before, name of a variable should be meaningful, so using mystifying abbreviations does not make any sense. Try to be clear and very expressive while you are writing your code. Adding comments in proper places, is also a good habit. For comments, you can use both:

1 /*
2 Inside goes your long comments
3 /*
4 // use it for short comments

The naming convention of consists of two major things: we write a class like this - “NewClass”, especially when the class name has more than two words. The same is true for a variable, where only one word should begin with a lowercase letter. If there are two words, write it like this: ‘twoWords’.

We will come back to this topic once again, when we will talk more about classes and objects. You may consider this section as a short introduction to variables. There are more, and we will discuss them in the next chapter.

Primitive Data Types

So far we have seen eleven different types of problems, of which we have seen mostly integer values. We have also noticed one key thing at the time of declaring a variable. We write a variable like this: “int speed = 0;”.

It means we need to specify what type of variable it is. Stating the variable’s type and name is essential, because Java is statically-typed. It means all variables should be declared first before you can use it.

By naming and declaring a variable we actually declare the state of an object. In a Car class, when we declare a variable ‘speed’, our program knows that a field exists and that field holds a numerical data. It has also any initial value, such as 0 or 1. It explains why we need data types.

The data type of a variable tells us what type of value it is. Because it represents the state of an object, we need to know what type of value it contains. Otherwise, we cannot change that state through a method. Basically, in a method, we do some kind of operations to change that state of the object.

In total Java supports eight primitive data types.

Consider the following line:

1 int speed = 0;

Here, the primitive data type ‘int’ is predefined by the language. The name of the primitive data type ‘int’ is a reserved keyword. In the next problem twelve, we will have a look at the other primitive data types.

 1 //problem 12
2 //code 12
3 package fun.sanjibsinha;
4
5 /*
6 primitive data types and default values
7 */
8
9 import org.w3c.dom.CDATASection;
10
11 class PrimitiveDataTypes {
12     byte age = 10;
13     // byte distance = 144; // exceeding range
14     short height = 30000; // inside range
15     // short elevation = 40000; // outside range
16     int distanceBetweenTwoSatellites = 1000000000; // inside range
17     // int distanceBetweenTwoGalaxy = 10000000000; // outside range
18     long distanceBetweenTwoGalaxy = 10000000000L; // inside range
19     float rateOfInterest = 6/5f; // range is beyond the scope of discussion
20     double rateOfHike = 456/123d; // range is beyond the scope of discussion
21     char capitalA = 'A';
22     boolean isPossible = true;
23
24     void printState() {
25         System.out.println("Age :" + age + ". Height: " + height + ". Distance Betwe\
26 en Two Galaxies "
27         + distanceBetweenTwoGalaxy + ". Distance Between Two Satellites " + distance\
28 BetweenTwoSatellites +
29                 ". Rate of Interest: " + rateOfInterest + ". Rate of Hike :" + rateO\
30 fHike +
31                 ". Capital A :" + capitalA + ". Is it possible? :" + isPossible);
32     }
33 }
34
35 public class ProblemTwelve {
36     public static void main(String args[]) {
37         PrimitiveDataTypes dataObject = new PrimitiveDataTypes();
38         dataObject.printState();
39     }
40 }

A closer look at the above code snippet will help you understand that each primitive data types have a range of values. We will talk about it in a minute. Let us see the output first:

1 //output of problem 12
2 Age :10\. Height: 30000\. Distance Between Two Galaxies 10000000000\. Distance Between \
3 Two Satellites 1000000000\. Rate of Interest: 1.2\. Rate of Hike : 3.707317073170732\. \
4 Capital A : A. Is it possible? : true

We can say that eight primitive data types that Java uses are:

1 byte
2 short
3 int
4 long
5 float
6 double
7 char
8 boolean

One primitive value does not share state with other primitive values. That is another key point. In the next problem thirteen, we will take a closer look at this point.

 1 //problem 13
2 //code 13
3 package fun.sanjibsinha;
4
5 /*
6 One primitive value does not share its state with other primitive values
7 */
8
9 class StateOfAnObject {
10
11     byte age = 10;
12     short distance = 10_000;
13     int speedOfCar = 1_00_000;
14     int speedOfTrain = 2_00_000;
15
16     void printState() {
17         System.out.println("The age is : " + age + ". The distance is : " + distance\
18  +
19                 ". The speed of car is : " + speedOfCar);
20     }
21 }
22
23 public class ProblemThirteen {
24     public static void main(String args[]) {
25         StateOfAnObject state = new StateOfAnObject();
26         state.speedOfCar = state.speedOfTrain; // sharing states will not give errors
27         state.printState();
28     }
29 }

In the above problem, we want to share states of the object ‘state’ and the code runs successfully. The ‘speedOfCar’ is equal to ‘speedOfTrain’. So the ‘state’ object shares its states.

How does it happen? We have claimed earlier that one primitive data type does not share states with other primitive data type.

Let us see the output, and then we will explain how it has taken place?

1 //output of problem 13
2 The age is : 10\. The distance is : 10000\. The speed of car is : 200000

In the above problem, we share states among the same primitive data types. Look at the code closely, you will find that ‘speedOfCar’ and ‘speedOfTrain’ are both declared as ‘int’ primitive data types. That is why the speed of car changes to 200000\. It was initialized with 100000.

By the way, you have also noticed that we have declared numerical values as this:

1 int speedOfCar = 1_00_000;

Java allows this to separate a big numerical values. It gives us better understanding of a big numerical value. Just remember, you cannot use ‘_’ underscore sign in front or at the end.

When the nature of the primitive data types is same, they can share the state. When they are different, it gives us errors. However, this concept seems little bit difficult at this stage.

I also think, the statement is not very clear though. Maybe, it is trying to say that there is a difference between primitive and reference types. Two reference variables can point to the same object. Changing the state of the object can affect both reference variables at the same time. In case of primitive types, that does not happen. It is discussed in detail in problem eighteen, in chapter five. We will talk about it in the next chapter, where we will discuss more about different types of variables and the relation between primitive data types and reference data types. Let us see more problems to get the feel of primitive data types, classes and objects.

Have a look at the problem fourteen.

 1 //problem fourteen
2 //code fourteen
3 package fun.sanjibsinha;
4
5 /*
6 One primitive value does not share its state with other primitive values
7 */
8
9 class SharingStatesOfAnObject {
10
11     byte age = 10;
12     short distance = 10_000;
13     int speedOfCar = 1_00_000;
14     int speedOfTrain = 2_00_000;
15
16     void printState() {
17         System.out.println("The age is : " + age + ". The distance is : " + distance\
18  +
19                 ". The speed of car is : " + speedOfCar);
20     }
21 }
22
23 public class ProblemFourteen {
24     public static void main(String args[]) {
25         SharingStatesOfAnObject state = new SharingStatesOfAnObject();
26         state.age = state.speedOfCar; // it will give error
27         state.printState();
28     }
29 }

The ‘age’ of the ‘state’ object cannot be equal to the ‘speedOfCar’. The first one is ‘byte’ and the other one is ‘int’.

Here is the output:

1 //output of problem fourteen
2 Error:(23, 26) java: incompatible types: possible lossy conversion from int to byte

It happens because the byte data type is an 8-bit signed two’s complement integer. It can store value between -128 to 127\. But the int data type is 32-bit signed two’s complement integer. Although both represent numerical values, when you equate a byte data type to int data type it cannot convert the value properly.

Let us see problem 15, to understand this problem.

 1 //problem 15
2 //code 15
3 package fun.sanjibsinha;
4
5 class StatesOfAnObject {
6
7     byte age = 10;
8     byte length = 100;
9     int speedOfCar = 1_00_000;
10
11     void printState() {
12         System.out.println("The age is : " + age + ". The distance is : " + length +
13                 ". The speed of car is : " + speedOfCar);
14     }
15 }
16
17 public class ProblemFifteen {
18     public static void main(String[] args){
19         StatesOfAnObject state = new StatesOfAnObject();
20         state.speedOfCar = state.age + state.length;
21         state.printState();
22     }
23 }

Here, state of the speed of the car represent int data types. The other two states (age and length) represent byte data types.

Take a look at the output:

1 //output of problem 15
2 The age is : 10\. The distance is : 100\. The speed of car is : 110

The type incompatible issue does not raise here. We will see more examples. Let us see the problem 16, where we have used local variables and the same issue is raised.

Still we can solve the issue in a different way:

 1 //problem 16
2 //code 16
3 package fun.sanjibsinha;
4 /*
5 Covering problems 5 to 7
6 */
7 public class ProblemSixteen {
8     public static void main(String[] args){
9         final byte numOne = 10;
10         final byte numTwo = 12;
11         int sumOfTwoNumbers;
12         sumOfTwoNumbers = numOne + numTwo;
13         //sumOfTwoNumbers = (byte)(numOne + numTwo);
14         System.out.println("The sum of two byte values inside int data type: " + sum\
15 OfTwoNumbers);
16     }
17 }

We have made both byte data types to final. It solves the “literals” issue. We will talk more about literals in the next chapter. Let us take a look at the output:

1 //output of problem 16
2 The sum of two byte values inside int data type: 22

We could have also cast the value. As a beginner if you feel at a loss, don’t worry. We will discuss these topics in detail, in the next chapter. Before moving to the next chapter, we will see the final problem of this chapter, problem 17.

 1 //problem 17
2 //code 17
3 package fun.sanjibsinha;
4
5 import java.sql.PseudoColumnUsage;
6
7 class PrimitiveType {
8     byte age;
9     byte height;
10     void printState() {
11         System.out.println("The age of the object is: " + age + ". The height is : "\
12  + height);
13     }
14 }
15
16 class WrapperClassExample {
17     Byte numberOne;
18     Byte numberTwo;
19     void printingState() {
20         System.out.println("The number one is : " + numberOne + ". The number two is\
21  : " + numberTwo);
22     }
23 }
24
25 class AnotherClass {
26     String anotherName = "Alina";
27 }
28
29 class ReferenceType {
30     String nameOne = "John";
31     String nameTwo;
32     AnotherClass anotherClass;
33
34     void givingOutput() {
35         System.out.println("The first name is : " + nameOne + ". The second name is \
36 : " + nameTwo + ". " +
37                 "Here is another class object: " + anotherClass);
38     }
39 }
40
41 public class ProblemSeventeen {
42
43     public static void main(String[] args){
44         byte firstNumber;
45         byte secondNumber = 1;
46         firstNumber = secondNumber;
47         System.out.println("The value of first number : " + firstNumber);
48         System.out.println("The value of second number : " + secondNumber);
49         secondNumber = 2;
50         System.out.println("The value of first number : " + firstNumber);
51         System.out.println("The value of second number : " + secondNumber);
52
53         PrimitiveType objectOne = new PrimitiveType();
54         objectOne.height = objectOne.age;
55         objectOne.printState();;
56         objectOne.height = 2;
57         objectOne.printState();
58
59         WrapperClassExample objectTwo = new WrapperClassExample();
60         objectTwo.printingState();
61         objectTwo.numberOne = 1;
62         objectTwo.numberTwo = objectTwo.numberOne;
63         objectTwo.printingState();
64         objectTwo.numberOne = 2;
65         objectTwo.printingState();
66
67         ReferenceType objOne = new ReferenceType();
68         AnotherClass objThree = new AnotherClass();
69         objOne.givingOutput();
70         objOne.nameTwo = objOne.nameOne;
71         objOne.givingOutput();
72         objOne.nameOne = "SS";
73         objOne.givingOutput();
74         objThree.anotherName = objOne.nameOne;
75         System.out.println(objThree.anotherName);
76         objThree.anotherName = "AA";
77         objOne.givingOutput();
78     }
79 }

The code snippet is quite long. However, if you take a look at the output, you will understand what we wanted to show.

Let us see the output:

 1 //output of problem 17
2 The value of first number : 1
3 The value of second number : 1
4 The value of first number : 1
5 The value of second number : 2
6 The age of the object is: 0\. The height is : 0
7 The age of the object is: 0\. The height is : 2
8 The number one is : null. The number two is : null
9 The number one is : 1\. The number two is : 1
10 The number one is : 2\. The number two is : 1
11 The first name is : John. The second name is : null. Here is another class object: n\
12 ull
13 The first name is : John. The second name is : John. Here is another class object: n\
14 ull
15 The first name is : SS. The second name is : John. Here is another class object: null
16 The another name of AnotherClass : Alina
17 The another name of AnotherClass takes the value of another object : SS
18 The first name is : SS. The second name is : John. Here is another class object: null

From the above code, we have learned a key concept. Every primitive data type has a default value, such as byte, short, int data types all have default value 0.

Furthermore, the instance variables that are declared at the class level, have a default value “null”. Our output gives us the same value. On the hand, local variables that are declared within a method, do not have any default value. They should be initialized. In the above code, we have also used wrapper class, such as “Byte numberOne”. Each primitive type has a corresponding wrapper like this:

1 byte, short, int, long, float, double, boolean, char
2 Byte, Short, Integer, Long, Float, Double, Boolean,    Character

The default value of wrapper objects are null. On the other hand, primitive types can never be null, as we have seen before.

In the next chapter, we will dig deep into these topics.

Chapter Five: Variables, the Name of a Field

In this chapter, we will talk more about different type of variables and data types. It will include reference variable that acts as a handle to the newly created object. There are a few rules and conventions that we should follow when we design and write the state of an object. Besides ‘int’ or ‘boolean’, there are other data types; moreover, we should have a clear idea about assigning values to the variables. If we do not explicitly initialize them, are they assigned default values? Let us know all the technique through problems.

Difference between Variables

Let us start with the problem eighteen. This problem handles a core concept of Java. We know that local variables store their values in the ‘Stack’, whereas, the newly created objects are stored in ‘Heap’. However, the reference variable that acts as a handle to the object, is stored in ‘Stack’. It only points to the new object. Let us see the problem first, and after that we will discuss what has happened actually.

 1 //problem 18
2 //code 18
3 package fun.sanjibsinha;
4
5 class ReferenceVariable {
6     int num;
7 }
8
9 public class ProblemEighteen {
10     public static void main(String[] args) {
11         int i = 10;
12         int j = 5;
13         System.out.println(i + " " + j);
14         i = j;
15         System.out.println(i + " " + j);
16         j++;
17         System.out.println(i + " " + j);
18
19         ReferenceVariable numOne = new ReferenceVariable();
20         ReferenceVariable numTwo = new ReferenceVariable();
21         numOne = numTwo;
22         numOne.num = 10;
23         System.out.println(numOne.num + " " + numTwo.num);
24         numTwo.num++;
25         System.out.println(numOne.num + " " + numTwo.num);
26     }
27 }

As you see in the above code, there are two local variables ‘int i, and int j’. We have displayed two values first. After that we write ‘i=j’, and raises the value of ‘j’ by 1\. As a matter of fact, this increase in value should reflect on the value of ‘i’. Yet, the change in the value of ‘j’ does not affect the value of ‘i’. You will find it in the output in a minute.

In the second part of the program, we have dealt with two objects. You watch these lines in the code:

1 ReferenceVariable numOne = new ReferenceVariable();
2         ReferenceVariable numTwo = new ReferenceVariable();
3         numOne = numTwo;

In the above lines, ‘numOne’ and ‘numTwo’ are two reference variables which point to the newly created two objects that are stored in the ‘Heap’. Whereas these two reference variables are stored in ‘Stack’. Once we equate them, the first reference variable, that is ‘numOne’, now points to the second object. It no longer reflects the value of the first object.

You watch the output carefully, you will understand the difference between ‘call by value’ and ‘call by reference’.

1 //output of problem 18
2 10 5
3 5 5
4 5 6
5 10 10
6 11 11

In the first case, the variable ‘i’ does not take up the value of ‘j’. But in the second case, ‘numOne’ takes up the value of ‘numTwo’. Because in the second case, the reference variable ‘numOne’ acts as a handle to the first object, it just withdraws and points to the second object.

In the next two problems, we will see a different types of variables. How we should use local variables?

 1 //problem 19
2 //code 19
3 package fun.sanjibsinha;
4
5 public class ProblemNineteen {
6     //local variable
7     public void WeightOfFatherBear(){
8         int weight = 0;
9         weight = 180;
10         System.out.println("The weight of father bear is: " + weight);
11     }
12
13     public static void main(String[] args) {
14         ProblemNineteen fatherWeight = new ProblemNineteen();
15         fatherWeight.WeightOfFatherBear();
16     }
17 }

Here is the output of problem 19:

1 The weight of father bear is: 180

Quite simple program. But it reminds us one key factor. We must not use local variable out of scope. Watch the problem 20.

 1 //problem 20
2 //code 20
3 package fun.sanjibsinha;
4
5 public class ProblemTwenty {
6     //using local variable out of scope
7     public void WeightOfChildBear(){
8         int weight = 0;
9         weight = 80;
10     }
11
12     public static void main(String[] args) {
13         //it will give us errors
14         System.out.println("The weight of child bear is: " + weight);
15     }
16 }

It will produce errors. Watch the output below.

1 //output of problem 20
2 Error:(12, 62) java: cannot find symbol
3 symbol:   variable weight
4 location: class fun.sanjibsinha.ProblemTwenty

When local variables are declared inside a method, it should be used in that method only. We can call that method later.

In the next problem, we will find another key factor. Local variables should be initialized. Otherwise, it gives us errors.

 1 //problem 21
2 //code 21
3 package fun.sanjibsinha;
4
5 /*
6 Local variables must be initialized
7 */
8
9 public class ProblemTwentyOne {
10
11     //local variable
12     public void WeightOfMotherBear(){
13         int weight;
14         System.out.println("The weight of mother bear is: " + weight);
15     }
16
17     public static void main(String[] args) {
18         ProblemTwentyOne motherBear = new ProblemTwentyOne();
19         //you cannot initialize local variable here
20         //it will give us errors
21         motherBear.weight = 150;
22         motherBear.WeightOfMotherBear();
23     }
24
25 }

We should have initialized it earlier. Instead, we tried to assign a value through the object reference. It does not work.

1 //output of problem 21
2 Error:(19, 19) java: cannot find symbol
3 symbol:   variable weight
4 location: variable motherBear of type fun.sanjibsinha.ProblemTwentyOne

On the other hand, the class level instance variable should not be initialized. It is because the instance variable has a default value of null. Watch the next problem.

 1 //problem 22
2 //code 22
3 package fun.sanjibsinha;
4
5 import java.io.*;
6
7     //these are instance variables
8     //you need not initialize them like local variables
9 class StudentClasses {
10     int className;
11     //we could have added more states and methods to change the states
12     }
13
14 public class ProblemTwentyTwo {
15     public static void main(String args[]) {
16         //here john is the reference variable
17         //it'll act as a handle to the new object
18         //john is stored in stack, and the new object is stored in heap
19         StudentClasses john = new StudentClasses();
20         //now john can access the instance variable
21         john.className = 1;
22         System.out.println("The new student john studies at class : " + john.classNa\
23 me);
24         StudentClasses mary = new StudentClasses();
25         mary.className = 2;
26         System.out.println("The new student mary studies at class : " + mary.classNa\
27 me);
28         john.className = mary.className;
29         System.out.println("After one year john passed the exam and now he studies a\
30 t : " + john.className);
31     }
32 }

It will not produce errors as we have guessed earlier.

1 //output of problem 21
2 The new student john studies at class : 1
3 The new student mary studies at class : 2
4 After one year john passed the exam and now he studies at : 2

Reference Variables

Now, we can give a summary of a few key rules about variables. We have found three types of variables, so far. Reference variable, local variable, and instance variable. The reference variables are directly related to the object scope. We have seen some problems and studied their nature through those problems.

Local Variables

Local variables have some special characteristics. They are declared within a block, or method, or constructor (we are yet to discuss constructor in the next chapter). When the method is called, or the block is entered, these local variables are created and destroyed when we leave the block or the call is returned from the method. We cannot access these variables outside this block of code. Furthermore, we have to initialize local variables.

Therefore we need to remember a few key factors about local variables and eventually we can compare its position with the object state or field, of which we have discussed earlier.

Just like objects store their fields in instance variables,a method stores its temporary states in local variables. The syntax for declaration is the same. We don’t use any ‘local’ keyword for that. According to its location, we can assume whether the role of the variable is local or not. It is always between the opening and closing braces of a method. Moreover, it is visible only inside the method.

Instance Variables

The specialty of instance variables is directly related to the classes and objects. We can declare it outside any block, method or constructor; but inside a class. It is not mandatory that we should initialize instance variable. Its default value is 0\. Objects store their states inside the fields or variables and that value is unique to each instance or object.

Furthermore, it life cycle is totally dependent on the objects of the class. The creation and the destruction process is controlled by objects. Since they are not ‘static’ variables, only objects can access them depending on the declaration of the access modifiers. We will talk about access modifiers in great detail, later in the coming chapters. However, in this chapter, we will have an introductory note about it.

Class Variables (Static Fields)

We call a variable class variable, when its field is declared with the ‘static’ modifier. The word ‘static’ means you can access the variable directly through the class name. You don’t have to create an object to do that anymore. It also tells the compiler that there is exactly one copy of this variable in existence. It does not matter how many times you instantiate a class, how many objects you create, there is only one copy of this variable and only the class can access it. We can think of a field like human eyes. It can ideally be marked as static. Why?

Because conceptually, we can apply the same number of eyes to all instances of human beings. Additionally we can add the keyword ‘final’ to assert that the number of eyes will never change.

The next problem will show you an example.

 1 //problem 23
2 //code 23
3 package fun.sanjibsinha;
4
5
6 class StudentClassesAndNames {
7     public static int className;
8     public static String studentName;
9 }
10
11
12 public class ProblemTwentyThree {
13     public static void main(String args[]) {
14         StudentClassesAndNames.studentName = "John";
15         StudentClassesAndNames.className = 1;
16         System.out.println(StudentClassesAndNames.studentName + " studies at class "\
17  + StudentClassesAndNames.className);
18     }
19 }

In the above code, we have seen an example of class variable with static modifier. The output is quite simple:

1 John studies at class 1

We will see some more problems that will have class variables with static modifier. However, in the next problem we will have a quick introduction to the access modifiers, which will play a very important role in building applicable software. In the next problem, we have seen difference between access modifiers. Read the documentation written inside the code. That will clear many ambiguities regarding these core concepts of object-oriented-programming.

 1 //problem 24
2 //code 24
3 package fun.sanjibsinha;
4
5 /*
6 Member variables can be declared inside class, but outside any method
7 There are four types of access modifiers
8 1) public = it is available in package, subclass, and outer world
9 2) protected = it is available in package, subclass, and not in the outer world
10 3) private = it is not available in package, subclass, and outer world
11 4) default (no modifier) = it is only available in package
12 */
13 /*
14 In this program we will check the access modifiers individually
15 */
16
17 class FatherPanda {
18     public boolean isPredator;
19     protected int weight;
20     private int age;
21     public void eat() {
22         System.out.println("After each meal Father Panda gains weight : " + weight +\
23  ". And his age is : " + age);
24     }
25 }
26
27 public class ProblemTwentyFour {
28     public static void main(String args[]) {
29         FatherPanda father = new FatherPanda();
30         System.out.println("Is father panda predator ? " + father.isPredator);
31         father.weight = 5;
32         //the next line will give error
33         //we cannot modify private member variable this way
34         //father.age = 10;
35         father.eat();
36     }
37 }

In the above code, we have commented out this line:

1 //father.age = 10;

Otherwise, it produces this error:

1 //output of problem 24
2 Error:(32, 15) java: age has private access in fun.sanjibsinha.FatherPanda

In the above output it clearly shows what kind of mistake we have done. We tried to access a private field or variable. When an instance variable is ‘public’, every part of the program can access it. When it is ‘protected’ a certain section is allowed to access it. When it is ‘private’, it is unavailable unless we change that state through a public method.

The same thing happens here. When that particular line is commented out, the output changes to this:

1 //output of problem 24
2 Is father panda predator ? false
3 After each meal Father Panda gains weight : 5. And his age is : 0

We have noticed another key property of instance variable that has primitive data type ‘int’. If it is not initialized, the default value is 0\. In case of ‘boolean’, it is ‘false’.

Using ‘get’ and ‘set’ method, we can modify the state of any protected and private field. The next problem deals with this. Let’s have a look.

 1 //problem 25
2 //code 25
3 package fun.sanjibsinha;
4
5 /*
6 Understanding member variables and access modifier
7 */
8
9 class MotherPanda {
10     public boolean isPredator;
11     protected int weight;
12     private int age;
13
14     public void setWeight(int weight) {
15         this.weight = weight;
16     }
17
18     public int getWeight() {
19         return weight;
20     }
21
22     public void setAge(int age) {
23         this.age = age;
24     }
25
26     public int getAge() {
27         return age;
28     }
29
30     public void eat() {
31         System.out.println("After each meal Mother Panda gains weight : " + getWeigh\
32 t() + ". And her age is : " + getAge());
33     }
34 }
35
36 public class ProblemTwentyFive {
37     public static void main(String args[]) {
38         MotherPanda mother = new MotherPanda();
39         mother.setWeight(2);
40         mother.setAge(7);
41         mother.eat();
42         FatherPanda father = new FatherPanda();
43         //protected member variable available in package
44         father.weight = 200;
45         //public member variable available in package
46         System.out.println("Is father panda predator? " + father.isPredator);
47         //public method available in everywhere
48         father.eat();
49     }
50 }

This problem is fairly simple to understand. Here is the output.

1 //output of problem 25
2 After each meal Mother Panda gains weight : 2. And her age is : 7
3 Is father panda predator? false
4 After each meal Father Panda gains weight : 200\. And his age is : 0

In the next problem, we will recapitulate the method level scope of a local variable. As we have said earlier, a local variable is only visible inside the method of a class. You should treat it as a typical property of a method, because a method stores its temporary state in those local variables.

Watch the next problem, where we tried to access a local variable outside the method level scope.

 1 //problem 26
2 //code 26
3 package fun.sanjibsinha;
4
5 /*
6 method level scope of a local variable
7 */
8
9 class ChildPanda {
10     public void eat() {
11         int weight = 3;
12         System.out.println("After each meal child panda gains weight : " + weight);
13     }
14 }
15
16 public class ProblemTwentySix {
17     public static void main(String args[]) {
18         ChildPanda child = new ChildPanda();
19         //we cannot access the variable weight
20         //since it is declared inside method, it has a method level scope
21         //weight cannot be accessed out the method
22         //the following line will give us error
23         child.weight = 4;
24         child.eat();
25     }
26 }

The method ‘eat()’ stores its state inside the local variable ‘weight’ whose data type is ‘int’. However, the reference variable ‘child’ wants to access it directly and tries to change its state. Watch the output:

1 //output of problem 26
2 Error:(17, 14) java: cannot find symbol
3 symbol:   variable weight
4 location: variable child of type fun.sanjibsinha.ChildPanda

Once we have commented out that particular line, the program runs perfectly well.

1 //output of problem 26
2 After each meal child panda gains weight : 3

We have seen different types of variables, and in some cases, we have seen a type of variable called ‘parameters’.

Parameters, another type of Variable

We need to remember one key thing about parameters. They are not classified as fields, but classified as variables. Always. In the next two problems, we will see how parameters work. The signature for the main() method in Java also uses parameters.

 1 //problem 27
2 //code 27
3 package fun.sanjibsinha;
4
5 /*
6 there is exactly one copy of a class variable, regardless of how many times the clas\
7 s has been instantiated.
8 */
9
10 class ExerciseSchedule {
11     static int weightGain = 0;
12     static int weightLoss = 0;
13     public void eat(int weightGain){
14         ExerciseSchedule exerciseOne = new ExerciseSchedule();
15         this.weightGain = 2;
16         System.out.println("After each meal the weight gain is : " + exerciseOne.wei\
17 ghtGain);
18     }
19     public void run(int weightLoss){
20         ExerciseSchedule exerciseTwo = new ExerciseSchedule();
21         this.weightLoss = 2;
22         System.out.println("After running two miles the weight gain is: " +
23                 ( exerciseTwo.weightGain - exerciseTwo.weightLoss ));
24     }
25
26 }
27
28 public class ProblemTwentySeven {
29     public static void main(String args[]){
30         ExerciseSchedule newScheduleOne = new ExerciseSchedule();
31         newScheduleOne.eat(2);
32         newScheduleOne.run(2);
33         ExerciseSchedule newScheduleTwo = new ExerciseSchedule();
34         newScheduleTwo.eat(3);
35         newScheduleTwo.run(3);
36     }
37 }

Here is the output:

1 //output of problem 27
2 After each meal the weight gain is : 2
3 After running two miles the weight gain is: 0
4 After each meal the weight gain is : 2
5 After running two miles the weight gain is: 0

The next code snippet deals with the same problem using parameters. Along with it we have also used class variables with static modifiers.

 1 //problem 28
2 //code 28
3 package fun.sanjibsinha;
4
5
6 class NewExerciseSchedule {
7     static int weightGain = 5;
8     static int weightLoss = 4;
9     int rateOfPulse;
10
11     public int eat(int weightGain){
12         return weightGain;
13     }
14     public int run(int weightLoss){
15         return weightLoss;
16     }
17 }
18
19 public class ProblemTwentyEight {
20     public static void main(String args[]){
21         NewExerciseSchedule newScheduleOne = new NewExerciseSchedule();
22         //first reference variable
23         newScheduleOne.rateOfPulse = 50;
24         System.out.println("Total weight loss for the first object : " + (newSchedul\
25 eOne.eat(2) -
26                 newScheduleOne.run(2))+ ". And the rate of pulse is :  " + newSchedu\
27 leOne.rateOfPulse);
28         NewExerciseSchedule newScheduleTwo = new NewExerciseSchedule();
29         //second reference variable
30         newScheduleTwo.rateOfPulse = 60;
31         System.out.println("Total weight loss for the second object : " + (newSchedu\
32 leTwo.eat(3) -
33                 newScheduleTwo.run(1)) + ". And the rate of pulse is :  " + newSched\
34 uleTwo.rateOfPulse);
35         //first reference variable points to the second object value and takes the n\
36 ew value
37         newScheduleOne.rateOfPulse = newScheduleTwo.rateOfPulse;
38         System.out.println("Total weight loss for the first object : " + (newSchedul\
39 eOne.eat(10) -
40                 newScheduleOne.run(2))+ ". And the rate of pulse is :  " + newSchedu\
41 leOne.rateOfPulse);
42         //since a class variable has been declared with a static modifier
43         //we can access it with a class name
44         //we need not instantiate
45         NewExerciseSchedule.weightLoss = 1;
46         System.out.println(NewExerciseSchedule.weightGain - NewExerciseSchedule.weig\
47 htLoss);
48     }
49 }

The last line of output gives us the subtracted value of two class variables.

1 //output of problem 28
2 Total weight loss for the first object : 0. And the rate of pulse is :  50
3 Total weight loss for the second object : 2. And the rate of pulse is :  60
4 Total weight loss for the first object : 8. And the rate of pulse is :  60
5 4

In the next problem, we have examined the role of private access modifier and besides we have also seen how a reference variable accesses instance variable.

 1 //problem 29
2 //code 29
3 package fun.sanjibsinha;
4
5 public class ProblemTwentyNine {
6     private int mySecretNumber = 10;
7     public void displaySecret(){
8         mySecretNumber = 45;
9         ProblemTwentyNine secret = new ProblemTwentyNine();
10         System.out.println("Reference variable accessing instance variable : " + sec\
11 ret.mySecretNumber);
12         System.out.println("Local Variable : " + mySecretNumber);
13         secret.mySecretNumber = mySecretNumber;
14         System.out.println("Reference variable accessing instance variable that poin\
15 ts to the local variable : " + secret.mySecretNumber);
16     }
17     public static void main(String args[]){
18         ProblemTwentyNine notSoPrivate = new ProblemTwentyNine();
19         notSoPrivate.displaySecret();
20     }
21 }

The output is quite expected. We can get the local variable’s value separately. Still we can have instance variable’s value using the reference variable in the first line.

1 //output of problem 29
2 Reference variable accessing instance variable : 10
3 Local Variable : 45
4 Reference variable accessing instance variable that points to the local variable : 45

You need to be careful about the usage of local variable. The scope is always inside the curly braces. Whatever method we use, it is visible only inside that method. The next problem will give you an idea. A small but meaningful program.

 1 //problem 30
2 //code 30
3 package fun.sanjibsinha;
4
5 public class ProblemThirty {
6     public static void main(String args[]){
7         {
8             int anyNumber = 10;
9             System.out.println(anyNumber);
10         }
11         //it will give error
12         // System.out.println(anyNumber);
13     }
14 }

We have used curly braces inside the main() method to differentiate the local variable’s position. Calling it outside the curly braces will give us errors.

1 The output is: 10.

The next two problems will use looping construct, which we have not covered yet. We will discuss them in the coming chapters, in detail. However, the two problems will get your head around the core concept regarding the naming of variables.

 1 //problem 31
2 //code 31
3 package fun.sanjibsinha;
4
5 public class ProblemThirtyOne {
6     public static void main(String args[]){
7         int anyNumber = 10;
8         for (anyNumber = 0; anyNumber <=5; anyNumber++){
9             System.out.println(anyNumber);
10         }
11         System.out.println(anyNumber);
12     }
13 }

Since we have already defined the variable ‘anyNumber’ once, we cannot use declare it anymore. Although we have declared it in the outer loop section, the inner loop takes us the same value and finally after the completion of the loop, it changes the outer loop value.

1 //output of problem 31
2 0
3 1
4 2
5 3
6 4
7 5
8 6

In the last problem of this chapter, we have examined the same naming convention of variables, where the inner loop has been declared separately. Thereafter, it cannot change the value of the outer loop.

 1 //problem 32
2 //code 32
3 package fun.sanjibsinha;
4
5 public class ProblemThirtyTwo {
6     public static void main(String args[]){
7         //variable name of outer loop
8         int anyNumber = 10;
9         //we cannot define the variable twice
10         //it has already been defined as int
11         //the following is not a continuation of outer loop, it's an inner loop
12         //hence the variable name is changed
13         for (int myNumber = 0; myNumber <=5; myNumber++){
14             System.out.println("Output of inner loop : " + myNumber);
15         }
16         System.out.println("Output of outer loop : " + anyNumber);
17     }
18 }

Watch the output here. The value of the outer loop is not 6 anymore.

1 //output of problem 32
2 Output of inner loop : 0
3 Output of inner loop : 1
4 Output of inner loop : 2
5 Output of inner loop : 3
6 Output of inner loop : 4
7 Output of inner loop : 5
8 Output of outer loop : 10

The naming convention of Java is no different than other programming languages. It has its own sets of rules that you must follow. Although you can write a variable like this: ‘int $anyNumber’, or ‘int anyNumber’, it is considered to be a good practice that you don’t use ‘$’ or ‘ ’ signs before any variable name. Begin your variable name with a letter. White space is also not allowed. If you want to store a constant value:

1 static final int NUM_OF_EYES = 2;

The naming convention can be changed. These are special cases where we can use ‘_’. Otherwise it is discouraged. Variable name is case sensitive, and you cannot declare variable name twice. We have seen such problems above. Finally you cannot use keywords or reserved words as your chosen variable names.

Chapter Six: Array the Container Object

In this chapter, we will learn about Array. We have seen before that a variable is a location in memory that has a name that contains a value. This value could be any data type, such as ‘int’. An array is also another kind of variable or a container object that holds a fixed number of values of a single type. Therefore, an array could be any data type, such as ‘int’, or ‘String’. We have used array before, in our last programs, unknowingly. Watch this code snippet below:

1 public static void main(String[] args){}

In every program, this is the entry point, the main method that has parameter, which is an array of ‘String’ type.

An Array in Disarray

In many Java programs you will see tow types of main method.

1 1) public static void main(String[] args){}
2 2) public static void main(String args[]){}

In fact, in our last 32 problems, we have used the second type. From now on we will keep using the first one. Why? Any particular reason?

No. Java allows both. Java makes no difference between this two statement. However, in Array chapter we will find that declaration of an array by using the second one, is discouraged in their official documentation.

Logically, from now on we will stick around with the first one.

What is an Array

As we have seen earlier, an array is a container object or a type of variable that holds a fixed number of values.

These values should be of a same type. We should also mention the length when create an array. When the array is created, that length is established. A variable could also be container that holds one value of single type. An array is a container that holds many value. So an array is just another kind of variable.

Let us first try to have an image of an array in our mind. A variable is a box; an array is also a box with many compartments. Inside each compartment, we keep one value. Enhancing the capacity of our container has been increased drastically.

The following figure (figure 6.1) shows you how values can be stored inside an array container object.

![Figure 6.1 – An array of 5 elements with the index starting from 0](OEBPS/Image00009.gif)

Figure 6.1 – An array of 5 elements with the index starting from 0

In the above array-figure we have not mentioned any value of the elements. However, it is clear that the fifth element is related to the index 4.

As you progress, you will find that an array plays a key role in building any complex software. Understanding data structures is a key component in any programming language. Learning array is the first step towards it.

Creating many compartments inside a box, is not difficult. Nevertheless, they should be ordered. They should be indexed properly and each index should point to an element. It looks like this:

1 INDICES => index 0->index 1->index 2->index 3->...index n
2 ELEMENTS => element 1->element 2->element 3->element 4->....element n+1

Don’t get confused with the letter ‘n’. That indicates the last index and element. It could be of any numerical value. Suppose an array has ten elements or items. They are kept separately in the compartment. Now each compartment has a numerical index, through which we can access the value or element kept in those compartments. As a rule of thumb, this index begins with 0.

For that reason, if there are 10 compartments in the array container box, there will be 10 indices but it will start from 0, and ends at 9\. The index 0 points to the element 1,and it goes on like this.

We declare array many ways:

1 1.
2 int[] myNumberCollection = new int[5];
3 2.
4 int[] myNumberCollection;
5 myNumberCollection = new int[5];
6 3.
7 int[] myNumberCollection = {1, 2, 56, 57, 23};

In the first two cases, we need to add elements to the array container manually. Like this:

1     // initializing first element
2         myNumberCollection[0] = 1;
3         // initializing second element
4         myNumberCollection[1] = 2;

In the third case, we have shown above, we have added the elements while declaring the array.

Accessing those elements is also very easy.

1 System.out.println("Element at index 0 : " + myNumberCollection[0]);
2
3 It will give an output : 1.

As we have found so far, there are many characteristics in an array. We can simply have a declaration, like this: “int[] myNumbers;”. The declaration does not create an array. It just tells the compiler, ‘Get ready, this variable will hold an array of specified type. This variable box will have many compartments.’.

As you see, the declaration of an array is similar to declaration of any variables of other types. Primarily, it involves two components: the data type and the name.

We write the type as int[], or String[]. When we mention the type, we actually mention the data type of the contained elements. Why we use the brackets? Just to let the compiler know that the variable holds an array. When we declare the array, inside the brackets, we don’t mention the size or length. It is done in the later part.

The same way, we can declare and create an array of objects. It is created just like an array of primitive data types.

1 Person[] persons = new Person[3];

In the last problem (problem 53) we have discussed this topic in great detail.

Similarly we can declare arrays of other types, this way:

1 byte[] anyName;
2 short[] anyName;
3 long[] anyName;
4 float[] anyName;
5 double[] anyName;
6 boolean[] anyName;
7 char[] anyName;
8 String[] anyName;

The next problem will display you how we can declare, initialize and allocate memory for different types of variables. Read the comments written inside the problem 33.

 1 // problem33
2 //code 33
3 package fun.sanjibsinha;
4 /*
5 Introduction to array object
6 Primitive data types are not objects created from a class. They are special data typ\
7 es built into the language.
8 To build an array object we need to take help from primitive data types.
9 The only exception is String
10 What features will distinguish array from primitive data types?
11 Let us see to that problem
12 */
13
14 public class ProblemThirtyThree {
15
16     public static void main(String[] args){
17         //an example of primitive data type
18         //a variable is a container that contains a value or a primitive data types
19         int myAge = 54;
20         System.out.println("An example of primitive data type : " + myAge);
21         //in case of array we declare and allocate memory with a new keyword
22         //the following array container holds a fixed number of value of data type i\
23 nt
24         //the length of the array is established
25         //here the length is 2, this container has 2 elements
26         int[] myBasket = new int[2];
27         //each item or element has a corresponding numerical index that starts with 0
28         myBasket[0] = 2;
29         myBasket[1] = 3;
30         //each element can be accessed by its corresponding numerical index
31         System.out.println("The first element of my basket : " + myBasket[0]);
32         System.out.println("The second element of my basket : " + myBasket[1]);
33     }
34 }

The output gives us an idea about how we can treat these variables in different way.

1 //output of problem 33
2 An example of primitive data type : 54
3 The first element of my basket : 2
4 The second element of my basket : 3

Initializing and creating an array always involves mentioning the data type. While initializing an array element through the index, if we choose a wrong data type it gives us an error of incompatible type.

The next problem shows us the same situation.

 1 // problem 34
2 //code 34
3 package fun.sanjibsinha;
4 /*
5 How to declare a variable to refer to an array
6 */
7
8 public class ProblemThirtyFour {
9
10     public static void main(String[] args){
11         //to declare and create an array of integer type
12         int[] studentClasses = new int[2];
13         //to declare an array of String, a non-primitive data type
14         String[] studentNames = new String[4];
15         //the brackets after the data type indicate it's an array
16         //an array has two parts : data type and name
17         //the data type also indicates what type of elements the array will contain
18         //the next line will give an error of incompatible type
19         /*
20         studentNames[0] = 12;
21         */
22         studentNames[0] = "John"; //this is OK with the compiler
23         System.out.println("The name of the student who has come out first : " + stu\
24 dentNames[0]);
25     }
26 }

In the above code, as usual you need to follow the commented sections. A ‘String’ array cannot be initialized as ‘int’.

1 //output of problem 34
2 The name of the student who has come out first : John

As we have said earlier, the proper initialization is necessary. In the next problem we will see the same thing.

 1 // problem 35
2 //code 35
3 package fun.sanjibsinha;
4 /*
5 The proper initialization of an array
6 */
7
8 public class ProblemThirtyFive {
9
10     public static void main(String[] args){
11         //we can also create and initialize an array like this
12         int schoolSections[] = new int[4];
13         schoolSections[0] = 1;
14         schoolSections[1] = 2;
15         schoolSections[2] = 3;
16         schoolSections[3] = 4;
17         System.out.println("We want section 1 : " + schoolSections[0]);
18         /*
19         However this above type of initialization is highly discouraged
20         */
21         int[] schoolSection = new int[4]; // it is OK
22
23     }
24 }

Java allows both type of initialization. However, we will follow this one:

1 int[] schoolSection = new int[4];

The shortcut syntax to creation and initialization of any array also saves a lot of time. In cases of multidimensional arrays (we will come to that topic in a minute), we need to use the shortcut syntax or array literals.

The following problem will show you how we can do that.

 1 // problem 36
2 //code 36
3 package fun.sanjibsinha;
4 /*
5 The shortcut syntax to create and initialize an array
6 */
7
8 public class ProblemThirtySix {
9
10     public static void main(String[] args){
11
12         String[] nameCollection = {
13                 "John Smith", "Chicago", "good gunner."
14         };
15         System.out.println("He is " + nameCollection[0] + ", from " + nameCollection\
16 [1]
17                 + ". And he is a " + nameCollection[2]);
18     }
19 }

And here is the output:

1 //output of problem 36
2 He is John Smith, from Chicago. And he is a good gunner.

So far we have seen how we can declare, initialize and create an array. Furthermore, we can take advantage of Java Standard Edition that provides many utilities to manipulate the arrays. Through those manipulations arrays turn to be very powerful and useful concept in programming.

You may consider a situation where we can put arrays inside any array. It may become complex, however, accessing multidimensional array elements is not very difficult. The next problem shows us the declaration, initialization and creation of a multidimensional array.

 1 // problem 37
2 //code 37
3 package fun.sanjibsinha;
4 /*
5 In multidimensional array components are themselves arrays
6 The rows can vary in length
7 */
8 public class ProblemThirtySeven {
9
10     public static void main(String[] args){
11         //you may imagine it as columns and rows
12         String[][] nameCollections = {
13                 {"Name", "Location", "Occupation"}, //[0][0] => Name
14                 {"John Smith", "Chicago", "Gunner"}, //[1][0] => John ...
15                 {"Ernest Hemingway", "Writer"}, //[2][0] => Ernest...
16                 {"Don Juan", "Paris", "Artist"} //[3][0] => Don...
17         };
18         //the first column name represents the first index as [0][0], and moves on
19
20         System.out.println(nameCollections[0][0] + " : " + nameCollections[1][0]);
21         System.out.println(nameCollections[0][1] + " : " + nameCollections[1][1]);
22         System.out.println(nameCollections[0][2] + " : " + nameCollections[1][2]);
23         System.out.println("+++++++++++++++");
24         System.out.println(nameCollections[0][0] + " : " + nameCollections[2][0]);
25         System.out.println(nameCollections[0][2] + " : " + nameCollections[2][1]);
26         System.out.println("+++++++++++++++");
27         System.out.println(nameCollections[0][0] + " : " + nameCollections[3][0]);
28         System.out.println(nameCollections[0][2] + " : " + nameCollections[3][1]);
29         System.out.println(nameCollections[0][2] + " : " + nameCollections[3][2]);
30     }
31 }

The output of this multidimensional arrays will help you understand how it works actually. We can also manipulate the multidimensional arrays in many ways.

 1 //output of problem 37
2 Name : John Smith
3 Location : Chicago
4 Occupation : Gunner
5 +++++++++++++++
6 Name : Ernest Hemingway
7 Occupation : Writer
8 +++++++++++++++
9 Name : Don Juan
10 Occupation : Paris
11 Occupation : Artist

We can also manipulate any array with some built-in property and methods that come with Java Standard Edition classes.

Knowing the size of an array is easy. Watch the next problem.

 1 // problem 38
2 //code 38
3 package fun.sanjibsinha;
4 /*
5 The built-in length property helps us to determine the size of any array
6 */
7
8 public class ProblemThirtyEight {
9
10     public static void main(String[] args){
11
12         String[][] nameCollections = {
13                 {"Name", "Location", "Occupation"}, //[0][0] => Name
14                 {"John Smith", "Chicago", "Gunner"}, //[1][0] => John ...
15                 {"Ernest Hemingway", "Writer"}, //[2][0] => Ernest...
16                 {"Don Juan", "Paris", "Artist"} //[3][0] => Don...
17         };
18         System.out.println("The length of the first array is : " + nameCollections.l\
19 ength);
20         System.out.println("The length of the index 2 of the first array is : " + na\
21 meCollections[2].length);
22     }
23 }

Since in the above code, we have used a multidimensional array, we can verify the length of any one of them. An outer array holds another inner array inside it. The output will show us how it works.

1 //output of problem 38
2 The length of the first array is : 4
3 The length of the index 2 of the first array is : 2

In the next problem, we will see how we can copy a part of one array to another array.

 1 // problem 39
2 //code 39
3 package fun.sanjibsinha;
4 /*
5 System class has a method called 'arraycopy()' that has five parameters
6 arraycopy(Object source, int source-position, Object destination, int destination po\
7 sition, int length)
8 */
9
10 import java.util.Arrays;
11
12 public class ProblemThirtyNine {
13
14     public static void main(String[] args){
15
16         String[] notAMeaningfulSentence = {"My ", "I ", "am ", "not ", "a ", "Robot"\
17 };
18         String[] aMeaningfulSentence = new String[5];
19         System.arraycopy(notAMeaningfulSentence, 1, aMeaningfulSentence, 0, 5);
20         System.out.println(aMeaningfulSentence[0]
21         + aMeaningfulSentence[1] + aMeaningfulSentence[2] + aMeaningfulSentence[3]
22         + aMeaningfulSentence[4]);
23     }
24 }

The ‘arraycopy()’ method, belonging to the ‘System’ class can copy from a destination to a source-position.

1 //output of problem 39
2 I am not a Robot

In the above code one of the parameters is the length of the new destination array. Therefore we can solve the same problem using for loop.

 1 // problem 40
2 //code 40
3 package fun.sanjibsinha;
4
5 public class ProblemForty {
6
7     public static void main(String[] args){
8
9         String[] notAMeaningfulSentence = {"My ", "I ", "am ", "not ", "a ", "Robot"\
10 };
11         String[] aMeaningfulSentence = new String[5];
12         System.arraycopy(notAMeaningfulSentence, 1, aMeaningfulSentence, 0, 5);
13         for (int i = 0; i<=4; i++){
14             System.out.print(aMeaningfulSentence[i]);
15         }
16     }
17 }

The output is same.

1 //output of problem 40
2 I am not a Robot

Since a problem can be solved many ways, we can use the array length property to get the output. In this solution, two factors play the vital role. The source-position and the length.

 1 // problem 41
2 //code 41
3 package fun.sanjibsinha;
4
5 /*
6 We can perform some of the most common manipulations related to arrays
7 */
8
9 public class ProblemFortyOne {
10
11     public static void main(String[] args){
12
13         String[] notAMeaningfulSentence = {"My ", "I ", "am ", "not ", "a ", "Robot"\
14 };
15         String[] aMeaningfulSentence = java.util.Arrays.copyOfRange(notAMeaningfulSe\
16 ntence, 1, 6);
17         for (int i = 0; i <= (aMeaningfulSentence.length - 1); i++){
18             System.out.print(aMeaningfulSentence[i]);
19         }
20     }
21 }

You get the same output: I am not a Robot.

So far we have learned one key point about array. There are index and value relations and that are very tightly coupled together. That is an advantage or pro side. The con side is we cannot change the length of the array. In the time of declaration, initialization, and memory allocation, it is fixed.

The next problem will depend on the same principles.

 1 // problem 42
2 //code 42
3 package fun.sanjibsinha;
4
5 /*
6 How array works : index=>element
7 */
8
9 public class ProblemFortyTwo {
10     public static void main (String[] args)
11     {
12         //declaring a certain type of array, we choose data type int
13         int[] ageCollection;
14
15         //the next step deals with allocating memory for elements, we choose 5
16         ageCollection = new int[5];
17
18         //the initialization process begins with the first element
19         for (int i = 0; i <= 4; i ++){
20             int j = 18;
21             j = j + i;
22             ageCollection[i] = j;
23             System.out.println("Element at index " + i + " => " + ageCollection[i]);
24         }
25     }
26 }

We have created the elements on the fly inside the loop.

1 //output of problem 42
2 Element at index 0 => 18
3 Element at index 1 => 19
4 Element at index 2 => 20
5 Element at index 3 => 21
6 Element at index 4 => 22

We have seen how we can create multidimensional array. Now in the next problem, we will see how we can manipulate a multidimensional array using for loop.

 1 // problem 43
2 //code 43
3 /*
4 Multidimensional array using for loop
5 */
6
7 public class ProblemFortyThree {
8
9     public static void main(String[] args){
10
11         int[][] myArray = {
12                 {1, 2, 3},
13                 {4, 5, 6},
14                 {7, 8, 9}
15         };
16
17         for (int i = 0; i < 3; i++){
18             System.out.print(i + " => ");
19             for (int j = 0; j < 3; j++){
20                 System.out.print(myArray[i][j] + " ");
21             }
22             System.out.println();
23         }
24
25     }
26 }

We have used nested loop to get the output. We will discuss this topic of outer and inner loop, along with nested loop in chapter 9\. After practicing nested loop by solving a couple of problems, it will be better for you to come back and visit this code snippets again.

1 //output of problem 43
2 0 => 1 2 3
3 1 => 4 5 6
4 2 => 7 8 9

The next couple of array problems will show you how to handle array methods and how we can follow a few array rules to get the best out of it. We will use Java built-in utilities classes to use some methods that can give us output of an array quite easily.

 1 // problem 44
2 //code 44
3 package fun.sanjibsinha;
4
5 import java.util.Arrays;
6
7 /*
8 Testing a few built-in array methods
9 */
10 public class ProblemFortyFour {
11
12     public static void main(String[] args){
13         //array declaration
14         int[] myNumber = new int[5];
15         //now we need to add elements
16         myNumber[0] = 50;
17         myNumber[1] = 60;
18         myNumber[2] = 70;
19         //etc
20         int[] anotherNumber = {1, 2, 3};
21         //we can print any array value this way
22         System.out.println(Arrays.toString(myNumber));
23         System.out.println(Arrays.toString(anotherNumber));
24     }
25 }

The output is quite expected. Before taking a look at the output I would like to discuss a key point of using array here.

Watch the array ‘myNumber[]’. We have declared length as 5,but added 3 elements. Since we cannot add elements once the length has been declared, we need to keep the memory location open for further addition. That is a con side of Java array. Wasting memory is not a sign of enlightenment. When you build a software, keep planning it beforehand so that you should not waste the memory unnecessarily.

1 //output of problem 44
2 [50, 60, 70, 0, 0]
3 [1, 2, 3]

There are a few basic rules that we should remember while handling and manipulating any array. An array is a container object. Therefore, it has states and we can change the states with the help of built-in methods. Since an array is a container object it has a reference value associated with it. In the next problem, we will see how it is displayed when you give an output.

 1 // problem 45
2 //code 45
3 package fun.sanjibsinha;
4 /*
5 There are few basic rules we should remember about an array
6 */
7
8 public class ProblemFortyFive {
9
10     public static void main(String[] args){
11         //array declaration
12         int[] myNumber = new int[5];
13         //now we need to add elements
14         myNumber[0] = 50;
15         myNumber[1] = 60;
16         myNumber[2] = 70;
17         //etc
18         int[] anotherNumber = {1, 2, 3};
19         //printing the value of an array like this
20         //gives us reference value : [I@5ba23b66
21         System.out.println(myNumber);
22         //we can print out the individual value of element by index
23         System.out.println(myNumber[0] + " => " + anotherNumber[0]);
24         //we can also use for loop
25         for (int i = 0; i <= 2; i++){
26             System.out.println(myNumber[i]);
27         }
28     }
29 }

Here is the output of code 45.

1 [I@5ba23b66
2 50 => 1
3 50
4 60
5 70

As we have said earlier, Java has many built-in array methods that can help us manipulate any array according to our requirements.

 1 // problem 46
2 //code 46
3 import java.util.Arrays;
4
5 /*
6 We can check if any array has a certain value
7 */
8 public class ProblemFortySix {
9
10     public static void main(String[] args){
11         //array declaration
12         int[] myNumber = new int[3];
13         //now we need to add elements
14         myNumber[0] = 50;
15         myNumber[1] = 60;
16         myNumber[2] = 70;
17         //etc
18         int[] anotherNumber = {1, 2, 3};
19         String[] nameColection = {"John", "Bob", "Mary"};
20
21         System.out.println("Does array nameCollection contains this element? "
22                 + Arrays.asList(nameColection).contains(2));
23         System.out.println("Does array nameCollection contains this element? "
24                 + Arrays.asList(nameColection).contains("John"));
25
26     }
27 }

In the first case, we have passed a numerical value. It is quite expected, the answer will be false. Because the array was of String type. The next one is true.

1 //output of problem 46
2 Does array nameCollection contains this element? false
3 Does array nameCollection contains this element? True

A problem can be solved in many ways. Doing any arithmetic operations on any number is quite easy. However, when we want to add a range of numbers, array is easy to use. We can pass a range of value as an array and add them on the fly.

 1 // problem 47
2 //code 47
3 package fun.sanjibsinha;
4 /*
5 We can pass array as parameter and we can manipulate that feature in many ways
6 In this problem we have solved how to add a collection of numbers
7 */
8
9 import java.util.*;
10
11 import java.util.Arrays;
12
13 public class ProblemFortySeven {
14
15     public static void main(String[] args){
16
17         int[] anotherNumber = {10, 25, 300};
18         addingAColectionOfNUmbers(anotherNumber);
19     }
20     public static void addingAColectionOfNUmbers(int[] aCollectionOfNumbers){
21         int sum = 0;
22         for (int i = 0; i < aCollectionOfNumbers.length; i++){
23             sum += aCollectionOfNumbers[i];
24         }
25         System.out.println(sum);
26     }
27 }

Using the shortcut syntax, we can pass as many numbers as possible, to get the result of addition. Here we pass three numbers: 10, 25, and 300.

1 And here is the output - 335.

We can also return any array value, using a method.

 1 // problem 48
2 //code 48
3 package fun.sanjibsinha;
4 /*
5 we can return any array value using a method
6 */
7
8 public class ProblemFortyEight {
9
10     public static void main(String args[]){
11         int newArray[] = returningArrayMethod();
12
13         for (int i = 0; i < newArray.length; i++){
14             System.out.print(newArray[i] + " ");
15         }
16     }
17
18     public static int[] returningArrayMethod(){
19         //returning any array from a method
20         return new int[] {111,222,3333, 456897};
21     }
22 }

The output is quite expected.

1 //output of problem 48
2 111 222 3333 456897

We have covered a few things about Array in Java. As you have found array has its pros and cons. In standard java libraries we have found some methods that can manipulate the elements. However, there are some limitations that we can overcome with the help of some external libraries. The next section will talk about it.

Apache Commons Lang

Apache Commons Lang provides many methods for manipulation of Java Arrays. This external libraries provide these extra methods. We need to add the libraries to our project to manipulate arrays.

Apache Commons Lang provides many helper utilities that will help you, not only arrays, but also string and numerical values. In this section, we will only talk about array methods. Maybe in future, in some other books we will have a more close look about these external helper utilities.

The first step will guide you how to add these external utilities to your NetBeans IDE. The subsequent steps will guide you to add the utilities to IntelliJ IDE. Once it has been added to your IDE, we will start using ‘org.apache.commons.lang3’ package on the top of our Java file, and call the methods accordingly.

Lang 3.0 is the latest version. It uses a different package than the previous versions. You can read more at here : https://commons.apache.org/proper/commons-lang/. At the same time you can download the ‘commons-lang3-3.9.jar’ file in your machine and later you can add that ‘jar’ file to your projects.

You may ask, why we need these external libraries? In fact, for many reasons. We can remove, add, reverse any array using these utilities. We can do many more things. Before that, we need to add Apache Commons Lang to our NetBeans 11.2 IDE.

The following figure (Figure 6.2) will show you how to start a NetBeans Java ANT project.

![Figure 6.2 – Starting an Java ANT application](OEBPS/Image00010.jpg)

Figure 6.2 – Starting an Java ANT application

Before proceeding any further, we would like to discuss about ANT.

Apache ANT is a Java library and command-line tool that helps you build Java applications. The advantage of ANT is IDE, like NetBeans or Eclipse ships with ANT. Another great advantage is while creating a Java ANT application, you can mention the libraries path, where you can place the Apache Commons Lang JAR file. After that you can easily import the external Lang utilities in your projects. ANT also supplies many built-in tasks allowing you to compile, assemble, test, and run your applications. For further reading please visit this link: https://ant.apache.org/.

As just mentioned, when you create a Java ANT application, you need to select the library path separately. The following figure (Figure 6.3) shows you how you can do that.

![Figure 6.3 – Selecting a separate libraries path](OEBPS/Image00011.jpg)

Figure 6.3 – Selecting a separate libraries path

The next step will be to click the second mouse on the Libraries folder and add the Apache commons-lang3 JAR file here (Figure 6.4).

![Figure 6.4 – Adding Apache commons-lang3 utilities to NetBeans libraries](OEBPS/Image00012.jpg)

Figure 6.4 – Adding Apache commons-lang3 utilities to NetBeans libraries

Now we can click on the JAR file to see what is there inside. There are lots of utilities that we can use in many ways depending on the complexities of your projects (Figure 6.5).

![Figure 6.5 – The Apache commons-lang3 and other utilities](OEBPS/Image00013.jpg)

Figure 6.5 – The Apache commons-lang3 and other utilities

Now we can safely import the Apache commons-lang3 utilities to our projects to use different type of Array methods (Figure 6.6).

![Figure 6.6 – Importing Apache commons-lang3 utilities](OEBPS/Image00014.jpg)

Figure 6.6 – Importing Apache commons-lang3 utilities

In the next problem, we will get a feel of Apache commons-lang3 utilities, where we can manipulate our arrays in a different way.

 1 // problem 49
2 //code 49
3 package fun.sanjibsinha;
4 /*
5 In this problem we will see how we can manipulate different type of
6 Array methods using internal and external libraries
7 */
8
9 import org.apache.commons.lang3.ArrayUtils;
10
11 import java.lang.reflect.Array;
12 import java.util.Arrays;
13
14 public class ProblemFortyNine {
15
16     public static void main(String[] args){
17
18         int[] numberCollection = {1, 2};
19         //we can get a particular value through index
20         System.out.println(Array.get(numberCollection, 1));
21         //we can get the length of the array
22         System.out.println(Array.getLength(numberCollection));
23
24         /*
25         Using external libraries is required in some situations where we want to
26         manipulate array values. Please consult the related texts and associated lin\
27 ks
28         written in the book
29         */
30         //using apache commons lang3 external library
31         int[] cartOne = {1, 2, 3, 4};
32         System.out.println("The length of the first cart : " + cartOne.length);
33         int[] cartTwo = {5, 200, 36, 4, 78, 123};
34         System.out.println("The length of the second cart : " + cartTwo.length);
35         int[] addingCart = ArrayUtils.addAll(cartOne, cartTwo);
36         System.out.println("Combining two carts the length has changed : " + addingC\
37 art.length);
38         //we can also see the final output
39         System.out.println("The adding cart looks like this : " + Arrays.toString(ad\
40 dingCart));
41
42     }
43 }

This solution shows us how we can use internal and external libraries, side by side in any of our Java projects.

1 //output of problem 49
2 2
3 2
4 The length of the first cart : 4
5 The length of the second cart : 6
6 Combining two carts the length has changed : 10
7 The adding cart looks like this : [1, 2, 3, 4, 5, 200, 36, 4, 78, 123]

By using Apache commons-lang3 utilities, we can easily add two arrays and extend the array length. We will solve some more problems, before that, let us see how we can add the same external utilities to our IntelliJ IDE.

Open your IntelliJ IDE and click on the left ‘file→Project Structure’. It will show up a window like the following image (Figure 6.7).

![Figure 6.7 – Opening IntelliJ IDE Project Structure from ‘file’](OEBPS/Image00015.jpg)

Figure 6.7 – Opening IntelliJ IDE Project Structure from ‘file’

On the top left corner you will find a ‘+’ sign. Click on it and select ‘Java’. Here you can add the path to your Apache commons-lang3 JAR file. I have downloaded it inside my “Download” folder, so I get that path. You might save it elsewhere.

The next image (Figure 6.8) will show you how I have added the external utilities file to IntelliJ IDE.

![Figure 6.8 – Adding Apache commons-lang3 JAR file to the Libraries folder in IntelliJ IDE](OEBPS/Image00016.jpg)

Figure 6.8 – Adding Apache commons-lang3 JAR file to the Libraries folder in IntelliJ IDE

Just like NetBeans, once you have added external Apache commons-lang3 utilities, you can use it in your Java projects.

In the next problem we will reverse this array elements completely. In the chapter 9, where we will learn nested loop, we will solve the same problem, but that will take more lines of code. Using the Apache commons-lang3 utilities we can solve the same problem with one or two lines of code.

 1 // problem 50
2 //code 50
3 package fun.sanjibsinha;
4 /*
5 Some more Array methods using external apache commons lang3
6 */
7
8 import org.apache.commons.lang3.ArrayUtils;
9
10 public class ProblemFifty {
11
12     public static void main(String[] args){
13         //we can reverse an Array
14         char[] myName = {'s', 'a', 'n', 'j', 'i', 'b'};
15         //now we can just add this characters to get my name
16         System.out.println("My name : " + new String(myName));
17         //let us reverse thsi character to see how my name looks in the mirror
18         ArrayUtils.reverse(myName);
19         System.out.println("My name on the mirror : " + new String(myName));
20     }
21 }

The output looks a little bizarre, however, every reverse string looks the same.

1 //output of code 50
2 My name : sanjib
3 My name on the mirror : bijnas

Now comes more sophisticated technique, more manipulation that we can do using this external utilities. We are now able to remove or replace any element in the array with the help of Apache commons-lang3 Array utilities.

 1 // problem 51
2 //code 51
3 package fun.sanjibsinha;
4
5 /*
6 We can remove any element of an array using apache commons lang library
7 */
8
9 import org.apache.commons.lang3.ArrayUtils;
10
11 import java.util.Arrays;
12
13 public class ProblemFiftyOne {
14
15     public static void main(String[] args){
16         //declaring an array
17         int[] myNumber = {1, 58, 23, 45, 47, 13, 35};
18         //the length of the array and the output
19         System.out.println("The length of the array : " + myNumber.length);
20         System.out.println("The array before removing any element : " + Arrays.toStr\
21 ing(myNumber));
22         //removing an element in the array
23         int[] newArrayOfMyNumber = ArrayUtils.remove(myNumber, 2);
24         System.out.println("The length of the new array after removel of index 2 : "\
25  + newArrayOfMyNumber.length);
26         System.out.println("The array after removing element 3, index 2 : "
27                 + Arrays.toString(newArrayOfMyNumber));
28         System.out.println("The index 2 and element 3, that is number " + myNumber[2\
29 ] + " is missing in the new array.");
30     }
31 }

The length of the original array was 7\. We will see the original array first. The next step will display the removed element. And finally we will see the elements of the changed array.

This problem can be done with the help of loop. But that will definitely take more lines of code. The same solution is achieved using the Apache commons-lang3 array utilities.

1 //output of code 51
2 The length of the array : 7
3 The array before removing any element : [1, 58, 23, 45, 47, 13, 35]
4 The length of the new array after removel of index 2 : 6
5 The array after removing element 3, index 2 : [1, 58, 45, 47, 13, 35]
6 The index 2 and element 3, that is number 23 is missing in the new array.

So far we have seen many different types of arrays that were created using primitive data types. We can create an array of objects just like any array of any primitive data types. In the next problem, we will see a simple problem and its solution.

 1 // problem 52
2 //code 52
3 package fun.sanjibsinha;
4
5 class Person{
6     int age;
7 }
8
9
10 public class ProblemFiftyTwo {
11
12     public static void main(String[] args){
13
14         Person onePerson = new Person();
15         onePerson.age = 10;
16         Person twoPerson = new Person();
17         twoPerson.age = 20;
18         Person threePerson = new Person();
19         threePerson.age = 30;
20         Person[] persons = new Person[3];
21         persons[0] = onePerson;
22         persons[1] = twoPerson;
23         persons[2] = threePerson;
24         System.out.println("The age of three Persons : " + persons[0].age +
25                 ", " + persons[1].age + ", " + persons[2].age);
26
27     }
28
29 }

Here index of the array points the object elements in the array. The object element can access the corresponding states defined in the class. That reflects in the output.

1 //output of code 52
2 The age of three Persons : 10, 20, 30

The next problem shows you a little bit complex code snippets, where we have used an array of objects that use methods to change the states of the objects defined in the class.

 1 // problem 53
2 //code 53
3 package fun.sanjibsinha;
4
5 class Mobile{
6     int modelNumber;
7     String modelName;
8     public void displayModels(int model, String name){
9         this.modelName = name;
10         this.modelNumber  = model;
11         System.out.println("The model number : " + model + ". The model name :  " + \
12 name);
13     }
14
15 }
16
17 public class ProblemFiftyThree {
18
19     public static void main(String[] args) {
20         //we are creating three mobile objects in heap
21         //three reference variables from stack point to the heap
22         Mobile sam = new Mobile();
23         Mobile red = new Mobile();
24         Mobile zen = new Mobile();
25         //an array of objects can be created just like any primitive data type
26         Mobile[] mobiles = {sam, red, zen};
27         for (int i = 0; i < mobiles.length; i ++){
28             //we want model number starts from 10
29             int j = 10;
30             j += i;
31             if(i == 0){
32                 mobiles[i].displayModels(j, "Sam");
33             }
34             else if(i == 1){
35                 mobiles[i].displayModels(j, "Red");
36             }
37             else {
38                 mobiles[i].displayModels(j, "Zen");
39             }
40         }
41     }
42 }

In the output, we get different model number and names of mobiles.

1 //output of code 53
2 The model number : 10\. The model name :  Sam
3 The model number : 11\. The model name :  Red
4 The model number : 12\. The model name :  Zen

We will conclude this array chapter with a concept called ‘enhanced loop’. Java allows us to pick up the elements directly from any array. We have picked up the array element by using the corresponding index. But this time, using for loop, we can pick up the elements directly.

 1 // problem 54
2 //code 54
3 package fun.sanjibsinha;
4
5 public class ProblemFiftyFour {
6
7     public static void main(String[] args) {
8
9         int[] myNUmbers = {12, 18, 36, 6, 24};
10         //enhanced for loop
11         //it takes out the value directly from the array
12         for (int i : myNUmbers){
13             System.out.println(i);
14         }
15
16     }
17 }

The output is quite expected. It will display the elements belonging to the corresponding array.

1 //output of code 54
2 12
3 18
4 36
5 6
6 24

Although arrays in Java have some limitations, it has some usefulness. As you progress, you will find them and you will also learn those qualities of being of practical use.

To explain array we have used conditional constructs, we have seen a lot of ‘if-then-else’, ‘for loop’, etc. We should learn them as fast as possible and master them to learn core Java language and the related concepts.

In the next three chapters (7, 8, and 9), we will discuss them with the help of more problems.

My advice is, after mastering the conditional constructs, altogether, you should revisit the array chapter again, and I hope, these algorithm will look much easier than before.

Chapter Seven: Operators and Conditional Statements

We have learned a few important concepts, such as how to store an object in the fields, how to name a field, by calling them variables. We have also seen how we can use array, the container object that stores many elements or data types.

Now, question is, how to do something with them. In lots of cases, we have assigned a value or initialize the value by using an assignment operator (=). After assigning a value to two operands, we can add them by using a ‘+’ symbol. We can perform many types of operations on one or more than one operands by using such symbols. These symbols are called operators. In this chapter we will explore many such operations, using operators. We will also find how these operators differ in many respects.

Arithmetic and Unary Operators

Arithmetic operators perform addition, subtraction, multiplication, and division. In basic mathematics, we have seen them quite often. The only new one is mod, ‘%’ symbol. By using this symbol, we divide one operand by another and return the remainder as the result.

In the next problem, we will see how arithmetic and unary operators work. Read the comments in the problem. You will understand how these operators work.

 1 // problem 55
2 //code 55
3 package fun.sanjibsinha;
4
5 public class ProblemFiftyFive {
6
7     public static void main(String[] args) {
8         //assignment operator is evaluated right to left
9         //the declaration of data type allocates memory
10         //variable x stores the value 10
11         int x = 10;
12         int y = 20;
13         //arithmetic operators -> +, -, *, /, %
14         int result = x + y;
15         System.out.println(result);
16         result = result - x;
17         System.out.println(result);
18         result = x * y;
19         System.out.println(result);
20         result = y / x;
21         System.out.println(result);
22         y = y - 1;
23         //now y = 19
24         result = y % x;
25         //the remainder is 9
26         System.out.println(result);
27
28         //arithmetic operator can concatenate the strings
29         String firstName = "John";
30         String lastName = "Rambo";
31         System.out.println(firstName + " " + lastName);
32
33         //unary operators require only one operand
34         int a = +12;
35         //a is positive
36         System.out.println(a);
37         a = -a;
38         //a is negative
39         System.out.println(a);
40         a--;
41         //-12 -1 = -13
42         System.out.println(a);
43         a++;
44         //-13 + 1 = -12
45         System.out.println(a);
46     }
47 }

We have not told about assignment operator separately, as it is most commonly used. It is evaluated right to left.

Once you declare the data type, it allocates memory. Watch this line: int x = 10; what does that mean? The field of the object has a name, ‘x’. It is variable. It stores the value 10\. Here the data type is ‘int’. It’s a primitive data type.

Now run this code in your IDE, you will find this output:

 1 //output of code 55
2 30
3 20
4 200
5 2
6 9
7 John Rambo
8 12
9 -12
10 -13
11 -12

Specialty of Unary Operators

Unary operators require only one operand. It can increment or decrement the value of the operand, make a variable’s value negative, and finally, it can invert the value of a boolean. In the next problem, we have seen various operations using unary operators.

 1 // problem 56
2 //code 56
3 package fun.sanjibsinha;
4
5 public class ProblemFiftySix {
6
7     public static void main(String[] args) {
8         // unary operators may be postfix and prefix
9         //but there is a difference
10         int x = 10;
11         //postfix
12         x++;
13         //x = 11
14         System.out.println(x);
15         ++x;
16         //x = 12
17         System.out.println(x);
18         x--;
19         //x = 11
20         System.out.println(x);
21         --x;
22         //x = 10
23         System.out.println(x);
24         int a = 0;
25         a = x;
26         //a = 10
27         System.out.println(a);
28         a = x++;
29         //a = 10, not 11, postfix version (x++) evaluates to the original value, ie;\
30  10
31         // although value of x changes to 11
32         System.out.println(a);
33         // a gets the incremented value if we make a = x
34         a = x;
35         // a is 11
36         System.out.println(a);
37         a = ++x;
38         //a = 12, prefix version (++x) evaluates to the incremented value
39         System.out.println(a);
40         a = -a;
41         // a is now -12
42         System.out.println(a);
43
44         boolean isTrue = false;
45         // false
46         System.out.println(isTrue);
47         // true
48         System.out.println(!isTrue);
49
50     }
51 }

Read the comments and you will have a clear idea about the unary operators work.

 1 //output of code 56
2 11
3 12
4 11
5 10
6 10
7 10
8 11
9 12
10 -12
11 false
12 true

The specialty of unary operators vary with the increment and decrement operators. The postfix increment (a++) and the prefix increment (++a), both can increment value of the operand by 1\. In the above code watch this snippets:

 1         a = x;
2         //a = 10
3         System.out.println(a);
4         a = x++;
5         //a = 10, not 11, postfix version (x++) evaluates to the original value, ie;\
6  10
7         // although value of x changes to 11
8         System.out.println(a);
9         // a gets the incremented value if we make a = x
10         a = x;
11         // a is 11
12         System.out.println(a);

When two operands get involved, the postfix version evaluates to the original value. Whereas, if we had used the prefix version, it evaluates to the incremented value.

You have to carefully design your code when you use two operands.

Equality, and Relational Operators

The equality and the relational operators mainly deal with two operands. These operators determine if one operand is greater than, less than, equal to, or not equal to another operand. Furthermore, it checks the equality between two operands using the ‘==’ symbol, not ‘=’ symbol.

The next problem will show you how we can use these operators. Read the comments specially, because it will clear your ideas about these operators.

 1 // problem 57
2 //code 57
3 package fun.sanjibsinha;
4 /*
5 Equality, and Relational Operators
6 ==      equal to
7 !=      not equal to
8 >       greater than
9 >=      greater than or equal to
10 <       less than
11 <=      less than or equal to
12 */
13
14 public class ProblemFiftySeven {
15
16     public static void main(String[] args) {
17         //it tests whether one operand is greater than, less than, equal to, or not \
18 equal to another operand
19         int x = 10;
20         int y = 20;
21         if (x == y){
22             System.out.println("x == y");
23         }
24         //it is true, we will get the output
25         if (x != y){
26             System.out.println("x != y");
27         }
28         if (x > y){
29             System.out.println("x > y");
30         }
31         if (x >= y){
32             System.out.println("x >= y");
33         }
34         //it is true, we will get the output
35         if (x < y){
36             System.out.println("x < y");
37         }
38         //it is true, we will get the output
39         if (x <= y){
40             System.out.println("x <= y");
41         }
42     }
43 }

You need to remember one thing, the ‘if-then-else’ block maintains one rule. The ‘if’ block will only work when the condition is ‘true’. Otherwise, it will jump to the ‘else’ block. Run the code in your IDE and see the output.

1 //output of code 57
2 x != y
3 x < y
4 x <= y

In case of conditional operators the rules slightly change. We will see that in a minute.

Conditional Operators

These operators perform the operations on two boolean expressions. Conditional AND and Conditional OR are represented by these two symbols ‘&&’ and ‘||’ symbols respectively.

There are some golden rules in such operations. Because two boolean expressions are involved, they could either be ‘true’, or ‘false’. You need to remember that here the Conditional-AND represents some kind of mixing. On the other hand, the Conditional-OR represents a kind of separations.

You can also think of ‘true’ as a good guy and ‘false’ as a bad guy.

What would happen when two good guys mixed up. Something good would come up. Right? So, boolean expression ‘true’ and ‘true’ always comes out ‘true’.

On the contrary, when a good guy mixes with a bad guy, what happens? The good guy no longer remains good. Right? So, ‘true’ and ‘false’ comes out ‘false’. However, when we say, ‘true’ or ‘false’, as a rule, the good guy separates herself from the bad guy. So the result comes out ‘true’. In the next problem, we have seen such results. Read the comments. That will guide you to understand the rules.

  1 // problem 58
  2 //code 58
  3 package fun.sanjibsinha;
  4
  5 /*
  6 Conditional Operators perform Conditional-AND and Conditional-OR operations on two b\
  7 oolean expressions
  8 && -> AND
  9 || -> OR
10 */
11 /*
12 The Golden rules of the Truth table:
13 true && false -> false
14 false && true -> false
15 true && true -> true
16 false && false -> false
17 -----------------------
18 true || false -> true
19 false || true -> true
20 true || true -> true
21 false || false -> false
22 */
23
24 public class ProblemFiftyEight {
25
26     public static void main(String[] args) {
27
28         int x = 10;
29         int y = 100;
30         if (true){
31             //this block will work
32             System.out.println("true");
33         }
34         else{
35             System.out.println("false");
36         }
37         if (false){
38             //this block will not work
39             System.out.println("true");
40         }
41         else{
42             //it comes to this block
43             System.out.println("false");
44         }
45         System.out.println("**********");
46         if (true && false){
47             //this block will not work
48             System.out.println("true");
49         }
50         else{
51             System.out.println("false");
52         }
53         System.out.println("**********");
54         if (false && true){
55             //this block will not work
56             System.out.println("true");
57         }
58         else{
59             System.out.println("false");
60         }
61         System.out.println("**********");
62         if (true && true){
63             //this block will work
64             System.out.println("true");
65         }
66         else{
67             System.out.println("false");
68         }
69         System.out.println("**********");
70         if (false && false){
71             //this block will not work
72             System.out.println("true");
73         }
74         else{
75             System.out.println("false");
76         }
77         System.out.println("**********");
78         System.out.println("**********");
79         System.out.println("**********");
80         if (true || false){
81             //this block will work
82             System.out.println("true");
83         }
84         else{
85             System.out.println("false");
86         }
87         System.out.println("**********");
88         if (false || true){
89             //this block will work
90             System.out.println("true");
91         }
92         else{
93             System.out.println("false");
94         }
95         System.out.println("**********");
96         if (true || true){
97             //this block will work
98             System.out.println("true");
99         }
100         else{
101             System.out.println("false");
102         }
103         System.out.println("**********");
104         if (false || false){
105             //this block will not work
106             System.out.println("true");
107         }
108         else{
109             System.out.println("false");
110         }
111     }
112 }

We have checked many boolean expressions in the above code,and here goes the result.

 1 //output of code 58
2 true
3 false
4 **********
5 false
6 **********
7 false
8 **********
9 true
10 **********
11 false
12 **********
13 **********
14 **********
15 true
16 **********
17 true
18 **********
19 true
20 **********
21 false

We have used line separators to understand how these tests take place. What we have tested with boolean expressions, we can test with objects. However, we do it differently.

InstanceOf Operators

These operators check whether an object is an instance of a class, or a subclass. If a class implements an interface,that can also be checked. Let us see the next problem to understand how it works.

 1 // problem 59
2 //code 59
3 package fun.sanjibsinha;
4
5 /*
6 You can use the instanceof operator to test if an object is an instance of a class,
7 an instance of a subclass, or an instance of a class that implements a particular in\
8 terface
9 */
10
11 interface PlaceTheOrder{
12     public void place();
13 }
14 class ParentClass implements PlaceTheOrder{
15
16     public void place(){
17         System.out.println("Placing the order.");
18     }
19
20 }
21 class ChildClass extends ParentClass{
22
23 }
24 public class ProblemFiftyNine {
25
26     public static void main(String[] args) {
27         ParentClass parent = new ParentClass();
28         ChildClass child = new ChildClass();
29
30         /*
31         The following two questions will have answers true
32         */
33         System.out.println("Is parent isntance of ParentClass? : " + (parent instanc\
34 eof ParentClass));
35         System.out.println("Is parent isntance of interface PlaceTheOrder? : " + (pa\
36 rent instanceof PlaceTheOrder));
37         //it is false
38         System.out.println("Is parent isntance of ChildClass? : " + (parent instance\
39 of ChildClass));
40         /*
41         The floowing answers will be true, because ChidlClass is a subclass of Paren\
42 tClass
43         */
44         System.out.println("Is child isntance of ChildClass? : " + (child instanceof\
45  ChildClass));
46         System.out.println("Is child isntance of ParentClass? : " + (child instanceo\
47 f ParentClass));
48         System.out.println("Is child isntance of interface PlaceTheOrder? : " + (chi\
49 ld instanceof PlaceTheOrder));
50
51     }
52 }

As you see in the above code, there are two classes and one interface. One is parent class, and one is child class. The parent class implements an interface. Check out the output to understand how it works.

1 //output of code 59
2 Is parent isntance of ParentClass? : true
3 Is parent isntance of interface PlaceTheOrder? : true
4 Is parent isntance of ChildClass? : false
5 Is child isntance of ChildClass? : true
6 Is child isntance of ParentClass? : true
7 Is child isntance of interface PlaceTheOrder? : true

When you design a software, using object-oriented-programming, objects play the most important role. There are two things primarily. State of the objects (fields) and the action part that involves change of state (behavior or methods) . And to all types of operations we use decimal number system.

However, computer only use binary number system. It has only two digits – 0 and 1\. Why binary number system is used? Because the fundamental building block of a computer is a switch much like we use ‘on or off’ switch for an electric lamp. Binary numbers are referred as bit. Therefore, 0 is a bit and 1 is another bit. A byte contains 8 bits.

In Java programming language, we get operators that perform bitwise and bit shift operations on integral types,although they are less commonly used.

In the next problem, we will build a method that will change any decimal value to its binary equivalent.

 1 // problem 60
2 //code 60
3 package fun.sanjibsinha;
4
5 /*
6 Changing decimal value to binary
7 */
8
9 class DecimalToBinary{
10
11     public Integer Decimal2Binary(Integer myDecimalNumber) {
12
13         if (myDecimalNumber == 0) {
14             return myDecimalNumber;
15         }
16
17         StringBuilder myBinaryNumber = new StringBuilder();
18         Integer quotient = myDecimalNumber;
19
20         //we keep dividing the quotient until the quotient becomes 0
21         while (quotient > 0) {
22             int remainder = quotient % 2;
23             myBinaryNumber.append(remainder);
24             quotient /= 2;
25         }
26
27         myBinaryNumber = myBinaryNumber.reverse();
28         return Integer.valueOf(myBinaryNumber.toString());
29     }
30 }
31
32 public class ProblemSixty {
33
34     public static void main(String[] args) {
35
36         DecimalToBinary myNumber = new DecimalToBinary();
37         System.out.println(myNumber.Decimal2Binary(5));
38     }
39 }
40
41 The output is – 101.

There are four types of bitwise operators. AND - ‘&’, OR - ‘|’, XOR - ‘ ’, and Complement - ‘~’. For AND (&) operator if both bits are 1, it gives 1, else it gives 0\. For OR (|) operator if either of the bits is 1, it gives 1, else it gives 0\. For XOR ( ) operator if corresponding bits are different, it gives 1, else it gives 0\. For Complement (~) operator with all bits are inversed. It makes every 0 to 1, and every 1 to 0.

Consider the Complement operator (~), if you apply this operator to a byte value whose bit pattern is “00000000”, the Complement operator would change its pattern to “11111111”.

The next problem would show you how we can use this operators using decimal values. When we use these operators on decimal value, it checks the value bitwise.

 1 // problem 61
2 //code 61
3 package fun.sanjibsinha;
4
5 /*
6 A simple introduction to bitwise operator
7 binary of 10 is 1010,
8 binary of 11 is 1011
9 */
10
11 public class ProblemSixtyOne {
12
13     public static void main(String[] args) {
14         int x = 10; // binary 1010
15         int y = 11; // binary 1011
16         // for AND (&) operator if both bits are 1, it gives 1, else it gives 0
17         System.out.println((x & y)); // 1010, that is 10
18         // for OR (|) operator if either of the bits is 1, it gives 1, else it gives\
19  0
20         System.out.println((x | y)); // 1011, that is 11
21         // for XOR (^) operator if corresponding bits are different, it gives 1, els\
22 e it gives 0
23         System.out.println((x ^ y)); // 0001, that is 1
24         // for Complement (~) operator with all bits inversed, means it makes every \
25 0 to 1, and every 1 to 0
26         System.out.println(~x); // 0101, that is 5, 2's complement of 5 is -11
27     }
28 }

Here is the output:

1 //output of code 61
2 10
3 11
4 1
5 -11

Control Flow – Part One

The source code is usually executed from top to bottom. With the help of Control Flow Statements, we can break up the flow of execution. In this section, we will see how ‘decision making’ impact the Control Flow Statements.

The next problem will show you how we can conditionally execute blocks of code with the help of decision-making statements, like ‘if-then’, ‘if-then-else’, and ‘switch’. Thereafter, in the next chapter, we will extend this topic that will contain the discussion of looping statements and the branching statements.

 1 // problem 62
2 //code 62
3 package fun.sanjibsinha;
4
5 class HumanBehaviour{
6     boolean isTrustWorthy = false;
7     int dependenceCounter = 0;
8 }
9
10 public class ProblemSixtyTwo {
11
12     public static void main(String[] args) {
13
14         HumanBehaviour john = new HumanBehaviour();
15         john.isTrustWorthy = true;
16         if(john.isTrustWorthy == true){
17             //only if the above condition is true, this block will work
18             john.dependenceCounter++;
19             System.out.println("We could depend on John because the dependence count\
20 er is positive : "
21                     + john.dependenceCounter);
22         } else {
23             john.dependenceCounter--;
24             System.out.println("We could not depend on John because the dependence c\
25 ounter is negative : "
26                     + john.dependenceCounter);
27         }
28         HumanBehaviour hobgoblin = new HumanBehaviour();
29         if(hobgoblin.isTrustWorthy == true){
30             //only if the above condition is true, this block will work
31             System.out.println("We could depend on Hobgoblin because the dependence \
32 counter is positive : "
33                     + hobgoblin.dependenceCounter);
34         } else {
35             //since the above condition is not true, this block will work
36             hobgoblin.dependenceCounter--;
37             System.out.println("We could not depend on Hobgoblin because the depende\
38 nce counter is negative : "
39                     + hobgoblin.dependenceCounter);
40         }
41     }
42 }

You may guess the output, because the ‘if’ block only works when the boolean expression is true.

1 //output of code 62
2 We could depend on John because the dependence counter is positive : 1
3 We could not depend on Hobgoblin because the dependence counter is negative : -1

Employing the decision-making statements, such as ‘switch’ is little bit different. A switch statement tests expressions based only on a single integer, enumerated value, or String object. On the contrary, based on ranges of values or conditions, ‘if-then-else’ can test expressions.

The next problem will show you how ‘switch’ works.

 1 // problem 63
2 //code 63
3 package fun.sanjibsinha;
4
5 /*
6 Based on ranges of values or conditions, if-the-else can test expressions.
7 A switch statement tests expressions based only on a single integer, enumerated valu\
8 e, or String object
9 */
10
11 class Human{
12     int age;
13     String name;
14     public void display(int displayAge, String displayName){
15         this.age = displayAge;
16         this.name = displayName;
17         System.out.println("Age of the person : " + displayAge + ". Name of the pers\
18 on : " + displayName);
19     }
20 }
21
22 public class ProblemSixtyThree {
23
24     public static void main(String[] args){
25
26         Human personOne = new Human();
27         Human personTwo = new Human();
28         Human personThree = new Human();
29
30         Human[] persons = new Human[2];
31         persons[0] = personOne;
32         Human[] personCollection = {personOne, personTwo, personThree};
33         for (int i = 0; i < 3; i++){
34             switch (i){
35                 case(0):
36                     personCollection[i].display(10, "Sanjib");
37                     break;
38                 case(1):
39                     personCollection[i].display(20, "John");
40                     break;
41                 case(2):
42                     personCollection[i].display(30, "Robert");
43                     break;
44             }
45         }
46     }
47 }

In the above code, we have used a class that contains two states – age, and name. We change the states using a method by passing them as parameters. Inside the main() method, we initialize an array container object that contains the objects of that class. We have mentioned three elements should be there in the array object. The rest part is simple.

1 // output of code 63
2 Age of the person : 10\. Name of the person : Sanjib
3 Age of the person : 20\. Name of the person : John
4 Age of the person : 30\. Name of the person : Robert

In this chapter, we have learned how to use different type of operators, we have also seen how ‘if-then-else’ and ‘switch’ statements work.

Chapter Eight: Iterative Constructs, Entry and Exit Controlled Loops

As we have seen earlier, in many code snippets, the statements inside our source files are generally executed from top to bottom. The looping statements are no exception. In this chapter, we will try to understand how looping statements that include ‘for, while and do-while’, work. We will also learn about the branching statements, such as break, continue, return.

In loop, a statement or a set of statements are repeatedly execute till the condition is satisfied. As we just saw, there are three types of loops supported by Java programming. They are:

1 1\. for loop
2 2\. while loop
3 3\. do-while loop

We can broadly categorize these loops as Entry controlled and Exit controlled.

Entry Controlled loop: Fixed and Unfixed Iteration

In entry controlled loop, the condition is checked first. If it is not satisfied, that means the condition is not true, the process stops, it does not enter the loop body. The ‘for loop’ and the ‘while loop’, both belong to this category. However, there is a big difference between these two entry controlled looping constructs.

In case of ‘For loop’ the number of iterations is fixed. Here the loop starts with a given value of a control variable. According to the condition the value of the variable gets updated. Once the condition becomes false, it comes out from the loop.

Why it is entry controlled? After the process enters the body of loop, it first checks the condition. If it is true,only then it goes back to the starting point of the loop and gets updated. Let us learn by solving the problem, as usual.

Fixed Iteration

To understand the fixed iteration, let us read the code below.

 1 // problem64
2 //code 64
3 package fun.sanjibsinha;
4
5 public class ProblemSixtyFour {
6
7     public static void main(String[] args) {
8
9         int[] myNumbers = {10, 20, 30, 40};
10
11         //entry controlled loop
12         // fixed iteration
13         // loop starts with the given value
14         // next it checks the condition
15         // unless the given condition is false, it executes
16         for (int i = 0; i < myNumbers.length; i++){
17             System.out.println(myNumbers[i]);
18         }
19
20     }
21 }

Read the comments written inside the code snippets. We are reading the elements of an array by iteration of the index value. The condition checks the length of the array. When it reaches the end, it comes out from the loop body.

Before that it gives us all the values.

Let us see the output.

1 //output of code 64
2 10
3 20
4 30
5 40

In the above code snippet, we have seen three expressions. We can write it this way:

1 • The ‘for loop statement’ is initialized with an initialization expression. We ente\
2 r the body of loop. Next we check the condition, we can call it the termination expr\
3 ession. Once the condition is true, the loop begins.
4 • When the condition is false, the termination expression also evaluates to false, a\
5 nd the loop stops.
6 • In the whole loop expression, the third part is the increment or decrement express\
7 ion. After each iteration, it is invoked depending upon the condition or the termina\
8 tion expression given.

We can imagine this iteration as the act of hopping, jumping either forward or backward. Furthermore, this ‘hop’ or ‘iteration’ is fixed. We can control this by increment or decrement.

We can also suddenly stop the loop statement by applying ‘break’. We can skip one value midway and then starts looping again from the next value. We will see that in a minute.

Branching Statements

The next problem deals with another interesting part of code statements. It is called branching statements. By using ‘continue’ and ‘break’ keywords, we can control a movement of a loop. First see the problem.

 1 // problem 65
2 //code 65
3 package fun.sanjibsinha;
4
5 public class ProblemSixtyFive {
6
7     public static void main(String[] args) {
8         System.out.println("Continue statement: ");
9         //continue statement tells the control to skip the current statement
10         //the loop executes the remaining statement
11         for(int i = 0; i < 5; i++){
12             if(i == 2){
13                 continue;
14             }
15             System.out.println(i);
16         }
17         System.out.println("Break statement: ");
18         for(int i = 0; i < 5; i++){
19             if(i == 2){
20                 break;
21                 //loop terminates when this condition is true
22             }
23             System.out.println(i);
24         }
25     }
26 }

In the first case, the ‘continue’ keyword skips a certain value and the loop continues. In the second case, when the iteration matches the exact value, it no longer moves. The loop terminates at that particular point. Watch the output,you will understand the logic.

1 //output of code 65
2 Continue statement:
3 0
4 1
5 3
6 4
7 Break statement:
8 0
9 1

We can create an infinite loop this way:

1 // infinite loop
2 for ( ; ; ) {   
3     // some code
4 }

We can solve various types of problems using for loop. The next problem will display the sum of two positive numbers for 4 iterations. If the sum is negative, the loop ends.

 1 // problem 66
2 //code 66
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 /*
8 display the sum of two positive numbers for 4 iterations
9 if the sum is negative, the loop ends
10 */
11 public class ProblemSixtySix {
12     //we need three variables globally
13     static int numOne;
14     static int numtwo;
15     static int sumOfTwoNumbers;
16
17     public static void main(String[] args) {
18         // we will take input from the users
19         Scanner firstInput = new Scanner(System.in);
20         Scanner secondInput = new Scanner(System.in);
21
22         for(int i = 0; i < 4; i++){
23             System.out.println("Enter the first positive integer: ");
24             numOne = firstInput.nextInt();
25             System.out.println("Enter the second positive integer: ");
26             numtwo = secondInput.nextInt();
27             sumOfTwoNumbers = numOne + numtwo;
28             System.out.println("The sum of two numbers: " + sumOfTwoNumbers);
29             if(sumOfTwoNumbers > 0){
30                 continue;
31             } else {
32                 System.out.println("The sum is negative. The program terminates");
33                 break;
34             }
35         }
36     }
37 }

We have run this program in two different ways to get two different outputs.

 1 //output of code 66
2 Enter the first positive integer:
3 12
4 Enter the second positive integer:
5 12
6 The sum of two numbers: 24
7 Enter the first positive integer:
8 56
9 Enter the second positive integer:
10 45
11 The sum of two numbers: 101
12 Enter the first positive integer:
13 89
14 Enter the second positive integer:
15 12
16 The sum of two numbers: 101
17 Enter the first positive integer:
18 78
19 Enter the second positive integer:
20 45
21 The sum of two numbers: 123
22
23 ---------------------------------------
24 Enter the first positive integer:
25 56
26 Enter the second positive integer:
27 456987
28 The sum of two numbers: 457043
29 Enter the first positive integer:
30 -45
31 Enter the second positive integer:
32 3
33 The sum of two numbers: -42
34 The sum is negative. The program terminates

Unfixed Iteration

In the next problem, we will see two types of loops one after another. The first snippet examines how unfixed iteration takes place in while loop. The subsequent for loop gives us a different set of value. In case of ‘for’ loop, we know how many iterations are going to take place. In case of ‘while’ loop, we do not know the number of iterations. That is why, it always checks whether the condition is true or false. When the ‘while’ loop finds the condition is ‘true’, it goes on until the condition turns ‘false’.

 1 // problem 67
2 //code 67
3 package fun.sanjibsinha;
4
5 /*
6 unfixed iterations, where number of iterations is unknown
7 a set of statements is repeated till a given condition is true
8 two types: entry controlled and exit controlled
9 */
10
11 public class ProblemSixtySeven {
12
13     public static void main(String[] args) {
14         //entry controlled unfixed iterations
15         int i = 0;
16         while (i <= 5){
17             i++;
18             System.out.println(i);
19         }
20         System.out.println("**********");
21         //entry controlled fixed iterations
22         for(i = 0; i <=5; i++){
23             System.out.println(i);
24         }
25
26     }
27 }

Here goes the output:

 1 //output of code 67
2 1
3 2
4 3
5 4
6 5
7 6
8 **********
9 0
10 1
11 2
12 3
13 4
14 5

I hope you get the idea how these fixed and unfixed iterations work. In case of ‘for loop’ statement, once the initialization expression initializes the loop (int i = 0),it is executed once, as the loop begins. That is why the output of ‘for loop’ starts with 0, and the output of ‘while loop’ starts with 1.

In the next section we will see how exit controlled loop works.

Exit Controlled loop

In this case, there is no restriction on the control to enter the loop. The decision, whether the process will repeat or terminate, will be made at the exit point of the loop. Since the condition or termination expression evaluates at the exit point of the loop, it is known as ‘Exit Controlled loop’.

Let us check a problem, where we can test our exit controlled loop.

 1 // problem 68
2 //code 68
3 package fun.sanjibsinha;
4
5 /*
6 unfixed iterations, exit controlled
7 */
8
9 public class ProblemSixtyEight {
10
11     public static void main(String[] args) {
12         //local variable
13         int i = 0;
14         do {
15             //statements are executed before checking the condition
16             //exit controlled
17             i++;
18             System.out.println(i);
19         } while (i <= 5);
20         //the decision is made at the exit point
21     }
22 }

In the above code you have noticed that the last statement is the ‘while statement’, thereafter we have to use a semi-colon to terminate the loop. This type of statement is known as compound statement.

The output is quite expected. It will start from 1.

1 //output of code 68
2 1
3 2
4 3
5 4
6 5
7 6

For or While, it Depends

According to the situation, it depends whether we should use ‘for loop’ or ‘while loop’ statement.

In many cases ‘while’ loop is the best remedy. Suppose, we want to take integer inputs from the user and want to give the output of average value. While writing the code, we will decide how many times the user will type the value. In the following code the user is restricted to give 5 values.

Once the user reaches the range, the average will come out automatically.

 1 //code snippet to find the average of five numbers
2 package fun.sanjibsinha.understandingloops;
3
4 import java.util.Scanner;
5
6 public class WhileOne {
7
8     public static void main(String[] args) {
9
10         final int listSize = 5;
11         double valueOfSum = 0;
12         int valueProcessed = 0;
13
14         System.out.println("Please enter " + listSize + " numbers.");
15         Scanner sc = new Scanner(System.in);
16         while (valueProcessed < listSize){
17             double yourNumber;
18             yourNumber = sc.nextDouble();
19             valueOfSum += yourNumber;
20             valueProcessed++;
21         }
22         double averageOfYourNumbers = valueOfSum / valueProcessed;
23         System.out.println("The average of given numbers " + averageOfYourNumbers);
24
25
26     }
27 }

If we run the code, the user is prompted to give five values. After entering five values, the user will no longer be able to enter any more value. Our program will keep adding five values and at the end, it will give the average.

1 //output of the above code snippet
2 Please enter 5 numbers.
3 45
4 56
5 23
6 36
7 58
8 The average of given numbers 43.6

The advantage of using ‘while’ loop is, it checks the condition for exact five times; after that, the loop terminates automatically and gives us the desired result.

We could modify the above loop and make it more robust. The limitation of the above code is: the user is restricted to a certain number. Here we had restricted it to 5\. We could have made it 10 or 20; but, that does not give the user enough freedom. The user should be able to enter as many numbers as possible and get the average of the numbers.

We could instruct the user how to terminate the program, so that after a certain number, the user will stop. The code is as follows:

 1 // modifying the previous code to give user more freedom
2 // to choose the time to terminate and get the result
3 package fun.sanjibsinha.understandingloops;
4
5 import java.util.Scanner;
6
7 public class WhileTwo {
8
9     public static void main(String[] args) {
10
11         double valueOfSum = 0;
12         int valueProcessed = 0;
13
14         System.out.println("Please enter your numbers or -1 to stop : ");
15         Scanner sc = new Scanner(System.in);
16         double yourNumber;
17         yourNumber = sc.nextDouble();
18         while (yourNumber != -1){
19             valueOfSum += yourNumber;
20             System.out.println("Please enter your numbers or -1 to stop: ");
21             yourNumber = sc.nextDouble();
22             valueProcessed++;
23         }
24         double averageOfYourNumbers = valueOfSum / valueProcessed;
25         System.out.println("The average of given numbers " + averageOfYourNumbers); \
26       
27     }
28 }

As you see in the above code, until the user types ‘-1’, she can enter the value and find the average.

 1 // output of the above code
2 Please enter your numbers or -1 to stop :
3 45
4 Please enter your numbers or -1 to stop:
5 56
6 Please enter your numbers or -1 to stop:
7 36
8 Please enter your numbers or -1 to stop:
9 58
10 Please enter your numbers or -1 to stop:
11 69
12 Please enter your numbers or -1 to stop:
13 47
14 Please enter your numbers or -1 to stop:
15 4568
16 Please enter your numbers or -1 to stop:
17 879564
18 Please enter your numbers or -1 to stop:
19 -1
20 The average of given numbers 110555.375

In some cases like the previous examples, the ‘while’ loop is indispensable. The user input validation is also done by using ‘while’ loop. We can do it by applying the ‘if-else’ logic. But, that should not be as robust as the code below:

 1 package fun.sanjibsinha.understandingloops;
2 /**
3 * how to force the user to give valid input
4 */
5
6 import java.util.Scanner;
7
8 public class WhileThree {
9
10     public static void main(String[] args) {
11
12         Scanner sc = new Scanner(System.in);
13         System.out.println("Enter your age : between 0 and 150 ");
14         int age = sc.nextInt();
15         while (age < 0 || age > 150){
16             System.out.println("That is impossible; try again! ");
17             age = sc.nextInt();
18         }
19         System.out.println("Your are " + age + " years old.");
20     }
21 }

We assume that humans can live up to 150 years. Therefore, the range is set between 0 and 150\. Now, we ask user to tell her age.

If you see the output, you will understand how ‘while’ construct forces the user to give the true value.

 1 // output of the above code
2 Enter your age : between 0 and 150
3 -1
4 That is impossible; try again!
5 1456
6 That is impossible; try again!
7 258
8 That is impossible; try again!
9 -45
10 That is impossible; try again!
11 120
12 Your are 120 years old.

By this time, we have seen how judiciously we could use ‘while’ loop to solve different type of problems.

But, in some cases, ‘do-while’ construct works better than ‘while’ construct. Let us see the next code snippet, where user is prompted to calculate the total price of number of items. The user gives the price of one item, then is asked to give the quantity, so the total price is calculated.

With the help of ‘do-while’ construct, we give the user enough freedom to calculate as long as she wishes. To terminate the program, she just types ‘no’. Since Java is case sensitive, we have used the proper method to ignore the upper case or lower case.

 1 package fun.sanjibsinha.understandingloops;
2
3 /**
4 * user can calculate total price more than once
5 */
6
7 import java.util.Scanner;
8
9 public class DoWhileOne {
10
11     public static void main(String[] args) {
12         Scanner sc = new Scanner(System.in);
13         String answer = "";
14         do {
15             System.out.println("Enter the price :");
16             double price = sc.nextDouble();
17             System.out.println("Enter the quantity : ");
18             int quantity = sc.nextInt();
19             double totalPrice = price * quantity;
20             System.out.printf("The price of " + quantity + " pieces is $%.2f: ", tot\
21 alPrice);
22             System.out.println();
23             System.out.println("Do you want to calculate more price? Yes or No.");
24             answer = sc.next();
25         } while (answer.equalsIgnoreCase("Yes"));
26     }
27 }

Here is the output:

 1 // output of the above code
2 Enter the price :
3 1456.45
4 Enter the quantity :
5 23
6 The price of 23 pieces is $33498.35:
7 Do you want to calculate more price? Yes or No.
8 yes
9 Enter the price :
10 456.23
11 Enter the quantity :
12 45789
13 The price of 45789 pieces is $20890315.47:
14 Do you want to calculate more price? Yes or No.
15 no
16
17
18 Process finished with exit code 0

We have seen a few problems to have an idea how ‘while’ and ‘do-while’ constructs work. We will see more problems so that we could understand it properly.

In the next problem, we will take inputs from the users and only add the negative numbers. See the problem and run the code in your IDE.

 1 // problem 69
2 //code 69
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 /*
8 accept any 5 number and print the sum of only negative numbers
9 */
10 public class ProblemSixtyNIne {
11
12     static int num, sum = 0;
13     static int controllingNumber = 1;
14
15     public static void main(String[] args) {
16         Scanner sc = new Scanner(System.in);
17         System.out.println("Enter any 5 number: ");
18         while (controllingNumber <= 5){
19             num = sc.nextInt();
20             if(num < 0){
21                 sum += num;
22             }
23             controllingNumber++;
24         }
25         System.out.println("The sum of only negative numbers: " + sum);
26     }
27 }

As a user you can insert any decimal value positive or negative, but our algorithm will determine which one to choose.

1 //output of code 69
2 Enter any 5 number:
3 10
4 -2
5 -5
6 -3
7 45
8 The sum of only negative numbers: -10

The same way we can take inputs and print the sum of only odd numbers.

 1 // problem 70
2 //code 70
3 package fun.sanjibsinha;
4 /*
5 accept any 5 number and print the sum of only odd numbers
6 */
7 import java.util.Scanner;
8
9 public class ProblemSeventy {
10
11     static int num, sum = 0;
12     static int controllingNumber = 1;
13
14     public static void main(String[] args) {
15         Scanner sc = new Scanner(System.in);
16         System.out.println("Enter any 5 number: ");
17         while (controllingNumber <= 5){
18             num = sc.nextInt();
19             if(num % 2 != 0){
20                 sum += num;
21             }
22             controllingNumber++;
23         }
24         System.out.println("The sum of only odd numbers: " + sum);
25     }
26 }

When you divide a decimal value by 2 and has no remainder, it is an even number. If that condition is not true, it is odd.

1 //output of code 70
2 Enter any 5 number:
3 12
4 10
5 5
6 3
7 7
8 The sum of only odd numbers: 15

We can take input from the user and test whether that number is even or odd. To terminate the program the user must enter 0\. The next problem will show us a good example of how we can utilize the concept of infinite loop to solve a certain problem.

 1 // problem 71
2 //code 71
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 /*
8 Enter a number to check whether odd or even and enter 0 to terminate the program
9 */
10 public class ProblemSeventyOne {
11     static int num = 1;
12
13     public static void main(String[] args) {
14
15         Scanner sc = new Scanner(System.in);
16         System.out.println("Enter a number to check whether odd or even\n" +
17                 "and enter 0 to terminate the program");
18         while (num != 0){
19             num = sc.nextInt();
20             if(num == 0){
21                 break;
22             }
23             if(num % 2 == 0){
24                 System.out.println(num + " is an even number");
25             } else {
26                 System.out.println(num + " is an odd number");
27             }
28         }
29     }
30 }

And here goes the output.

 1 //output of code 71
2 Enter a number to check whether odd or even and enter 0 to terminate the program
3 2
4 2 is an even number
5 3
6 3 is an odd number
7 789456
8 789456 is an even number
9 533333
10 533333 is an odd number
11 0

Can we pick up only odd numerical values by using the ‘continue’ keyword? Yes, we can do that. The next problem shows us how we can do that.

 1 // problem 72
2 //code 72
3 package fun.sanjibsinha;
4 /*
5 only odd numbers between 1 to 9, using continue
6 */
7
8 public class ProblemSeventyTwo {
9
10     public static void main(String[] args) {
11         int controllingNumber = 0;
12
13         while (controllingNumber <= 9){
14             controllingNumber += 1;
15             if(controllingNumber % 2 == 0){
16                 continue;
17             }
18             System.out.println("The only odd numbers: " + controllingNumber);
19
20         }
21     }
22 }

Run the above code in your IDE, and you will have this output.

1 //output of code 72
2 The only odd numbers: 1
3 The only odd numbers: 3
4 The only odd numbers: 5
5 The only odd numbers: 7
6 The only odd numbers: 9

In the next problem we can try to examine whether the user’s input number is a special number or not. By the way,a special number is a number whose sum of the digits if added to the product of its digits, the result is equal to the original number, such as 59.

 1 // problem73
2 //code 73
3 package fun.sanjibsinha;
4 /*
5 check special number
6 */
7 import java.util.*;
8
9 public class ProblrmSeventyThree {
10
11     public static void main(String[] args) {
12
13         System.out.println("Enter any number : ");
14         Scanner scan = new Scanner(System.in);
15         int inputNumber = scan.nextInt();
16         boolean result = specialnumber(inputNumber);
17         if (result == true)
18             System.out.println(inputNumber + " is a Special number");
19         if (result == false)
20             System.out.println(inputNumber + " is NOT a Special number");
21     }
22
23     public static boolean specialnumber(int inputNumber) {
24
25         // Create a copy of the inputNumber
26
27         int temp = inputNumber;
28
29         // Initialize sumOfDigits of inputNumber
30         int sumOfDigits = 0;
31
32         /* Calculate the sum of factorial of
33
34         digits */
35
36         while (temp != 0) {
37
38             // Get the rightmost digit
39
40             int currentDigit = temp % 10;
41             sumOfDigits = sumOfDigits + factorial(currentDigit);
42             temp = temp/10;
43         }
44
45         /* If sumOfDigits is equal to inputNumber then
46         the number is Special, otherwise not */
47
48         return (sumOfDigits == inputNumber);
49     }
50
51     public static int factorial(int number) {
52         if (number == 1 || number == 0)
53             return 1;
54         else
55             return (number * factorial(number -1));
56     }
57 }

We have entered 456, and that is not a special number. If you do not understand the algorithm, the best way of understanding is – write the sequence of steps on a notebook.

1 //output of code 73
2 Enter any number :
3 456
4 456 is NOT a Special number

The same way, we can check whether a number is a palindrome or not. 121 is a palindrome, because if you come backward, you will get the same digit.

 1 // problem 74
2 //code 74
3 package fun.sanjibsinha;
4 /**
5 * Display whether the number is palindrome or not.
6 *
7 */
8 public class ProblemSeventyFour{
9
10     public static void main(String[] args) {
11         int num = 121, reversedInteger = 0, remainder, originalInteger;
12         originalInteger = num;
13         // reversed integer is stored in variable
14         while( num != 0 )
15         {
16             remainder = num % 10;
17             reversedInteger = reversedInteger * 10 + remainder;
18             num  /= 10;
19         }
20         // palindrome if originalInteger and reversedInteger are equal
21         if (originalInteger == reversedInteger)
22             System.out.println(originalInteger + " is a palindrome.");
23         else
24             System.out.println(originalInteger + " is not a palindrome.");
25     }
26 }

As we have said that we entered 121, which is a palindrome. So as an output we get – 121 is a palindrome. The next problem will find a sum of a series, where we take a value from the user, and it goes on like this: (2 / 3) – (4 / 5) + (6 / 7) – (8 / 9) + .. up to n terms. In our problem, the value of n is 7.

 1 // problem 75
2 //code 75
3 package fun.sanjibsinha;
4
5 /**
6 * Write a program to find SumOfSeries 2/3
7 *
8 */
9 public class ProblemSeventyFive
10 {
11     // Function to find sum of series
12     // up-to n terms
13     static double seriesSum(int n)
14     {
15
16        
17         int i = 1;
18
19         // variable to calculate result
20         double res = 0.0;
21         boolean sign = true;
22
23         // while loop until nth term
24         // is not reached
25         while (n > 0)
26         {
27             n--;
28
29             // boolean type variable
30             // for checking validation
31             if (sign)
32             {
33                 sign = !sign;
34                 res = res + (double)++i / ++i;
35             }
36
37             else
38             {
39                 sign = !sign;
40                 res = res - (double)++i / ++i;
41             }
42         }
43
44         return res;
45     }
46
47    
48     public static void main (String[] args) {
49
50         int n = 7;
51
52         System.out.print(seriesSum(n));
53     }
54 }
55
56 And the output is: 0.7542679542679541.

In Java interactive programming tests, or in Java interview the employer asks to find the frequency of a number in a given digit.

A brief introduction to Algorithm

We have already been introduced to Algorithm. We solve any problem by breaking it in sequence of steps. Before writing the final code we could write the sequence of steps in our natural language.

In the following part we will compute the number of molecules in a hydrocarbon.

Notice the algorithm. That is same for any other language, we can write the same program in C++, or C#, although syntactically there will be differences. So the steps of algorithm varies. Let us see the algorithm in our natural language first.

The algorithm will be like this:

1 Step 1: take input and store the mass of hydrocarbon, the number of carbon, and the \
2 number of hydrogen atoms
3     Step 2: find and store the formula weight of one mole
4     Step 3: find the number of molecules in given mass of hydrocarbon  using the abo\
5 ve formula
6     Step 4: output the stored input values and the result

Considering that the algorithm is the same, let us suppose for any other programming language other than Java, its value is 1\. However, the syntactical difference makes the second value change. If we consider that algorithm is the X axis, and the syntactical difference as Y axis, then the hypothetical value might be (1, 2) and (1, 5). Moreover, they are discrete, distinct and separated.

Let us see the Java program first.

 1 //code to find the number of molecules in a hydrocarbon
2 //Java
3     package fun.sanjibsinha.languagebasics;
4     /*
5     we will compute number of molecules in a hydrocarbon
6     a mole of any substance contains 6.02 * 10^23 molecules
7     this is called Avogadro's number
8     relationship of a mass of a substance and the number of molecules is:
9
10     molecules = mass * 1mole/FormulaWeight * (6.02 * 10^23 molecules)/i mole
11     */
12     import java.util.Scanner;
13
14     public class HydroCarbonMolecule {
15
16         static float massOfHydrocarbon = 0.00f;
17         static int numberOfCarbonAtoms = 0;
18         static int numberOfHydrogenAtoms = 0;
19
20         public static void main(String[] args) {
21
22             System.out.println("Enter mass of HydroCarbon in a floating point: ");
23             Scanner mh = new Scanner(System.in);
24             massOfHydrocarbon = mh.nextFloat();
25             System.out.println("Enter the number of carbon atoms: ");
26             Scanner nc = new Scanner(System.in);
27             numberOfCarbonAtoms = nc.nextInt();
28             System.out.println("Enter the number of hydrogen atoms: ");
29             Scanner nh = new Scanner(System.in);
30             numberOfHydrogenAtoms = nh.nextInt();
31             final int CarbonAMU = 12;
32             final int HydrogenAMU = 1;
33             long formulaWeightOfOneMole = 111111111111L;
34             formulaWeightOfOneMole = (numberOfCarbonAtoms * CarbonAMU)
35                     + (numberOfHydrogenAtoms * HydrogenAMU);
36             double AvogadroNumber = 6.02 * Math.pow(10, 23);
37             double molecules = (massOfHydrocarbon/formulaWeightOfOneMole) * Avogadro\
38 Number;
39             System.out.println(massOfHydrocarbon + " grams of hydrocarbon with " + n\
40 umberOfCarbonAtoms
41             + " carbon atoms and " + numberOfHydrogenAtoms + " hydrogen atoms contai\
42 n "
43             + molecules + " molecules.");
44
45         }
46     }

Here goes the output:

1 //output of the above code
2 Enter mass of HydroCarbon in a floating point:
3 16.00
4 Enter the number of carbon atoms:
5 1
6 Enter the number of hydrogen atoms:
7 4
8 16.0 grams of hydrocarbon with
9 1 carbon atoms and 4 hydrogen atoms contain 6.019999999999999E23 molecules.

I would like to write the Avogadro’s number using the scientific notation this way:

1 double AvogadroNumber = 6.02e23;

The output changes from 6.019999999999999E23 to 6.02E23, although it should not have mattered how you have written the Avogadro’s number. In the first case, I have used the Java pow() method. In the second case, I have used the scientific notation. However, the outputs are discrete.

In the next problem, we will have an input like 1122322, and we will try to find how many times 2 appears on this number.

 1 // problem 76
2 //code 76
3 package fun.sanjibsinha;
4
5 public class ProblemSeventySix
6 {
7    
8     static int frequencyDigits(int n, int d)
9     {
10        
11         int c = 0;
12
13        
14         while (n > 0)
15         {
16             // check for equality
17             if (n % 10 == d)
18                 c++;
19             // reduce the number
20             n = n / 10;
21         }
22         return c;
23     }
24
25    
26     public static void main(String[] args)
27     {
28
29        
30         int myNumber = 1122322;
31
32        
33         int findTheDigit = 2;
34
35         System.out.println("Frequency of digit 2 in the number " + myNumber + " is :\
36  " + frequencyDigits(myNumber, findTheDigit));
37     }
38 }
39
40 And here goes the output: Frequency of digit 2 in the number 1122322 is : 4.

The next problem is comparatively easier than before. We will raise the value of 1 by adding 3\. And this iteration will stop when the number of steps is less than 5.

 1 // problem 77
2 //code 77
3 package fun.sanjibsinha;
4 /**
5 * SumOfSeriesTen 1+4+7+10.
6 *
7 */
8 public class ProblrmSeventySeven
9 {
10     static  int sum = 0;
11     static int num = 0;
12
13     public static void main (String[] args) {
14
15         sum = 1;
16         while (num < 5)
17         {
18             num++;
19             System.out.println(sum);
20             sum += 3;
21         }
22
23     }
24 }

The loop starts from 1, as usual. After that it starts increment the value by 3.

1 //output of code 77
2 1
3 4
4 7
5 10
6 13

Let us do some weird kind of things like taking an array of values from user, and sort them in ascending order.

 1 // problem 78
2 //code 78
3 package fun.sanjibsinha;
4 /*
5 Enter any number of array elements and get them in ascending order
6 */
7
8 import java.util.Scanner;
9 public class ProblemSeventyEight
10 {
11     public static void main(String[] args)
12     {
13         int count, temp;
14
15         //User inputs the array size
16         Scanner scan = new Scanner(System.in);
17         System.out.print("Enter number of elements you want in the array: ");
18         count = scan.nextInt();
19
20         int num[] = new int[count];
21         System.out.println("Enter array elements:");
22         for (int i = 0; i < count; i++)
23         {
24             num[i] = scan.nextInt();
25         }
26         scan.close();
27         for (int i = 0; i < count; i++)
28         {
29             for (int j = i + 1; j < count; j++) {
30                 if (num[i] > num[j])
31                 {
32                     temp = num[i];
33                     num[i] = num[j];
34                     num[j] = temp;
35                 }
36             }
37         }
38         System.out.print("Array Elements in Ascending Order: ");
39         for (int i = 0; i < count - 1; i++)
40         {
41             System.out.print(num[i] + ", ");
42         }
43         System.out.print(num[count - 1]);
44     }
45 }

Run the code in your favorite IDE, and you will get the same output as the following. You can download the code repository from the GitHub. At the end of the book, I have given the link. However, my suggestion is try to read the code and write in from your memory and while doing this, follow the logical steps that we have maintained in the code.

 1 //output of code 78
2 Enter number of elements you want in the array: 12
3 Enter array elements:
4 45
5 56
6 89
7 7456
8 23564
9 897456
10 12356
11 456123
12 25
13 45
14 457896
15 321456
16 Array Elements in Ascending Order: 25, 45, 45, 56, 89, 7456, 12356, 23564, 321456, 4\
17 56123, 457896, 897456

In the next problem we will try to find the sum of prime divisors. Now, question is what does this mean? What is the sum of prime divisors?

When we have the prime factorization of any number, then to calculate the the sum of its divisors, we take each different prime factor and add together all its powers up to the one that appears in the above process of factorization. Then we multiply all these sums together.

I admit, this type of problem is a little bit tricky and seems weird. However, my opinion is try to push the barrier of learning and task yourself with something that you don’t understand at the first hand. Only then you can learn something new. Everything takes time, it will take too.

 1 // problem 79
2 //code 79
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 public class ProblemSeventyNine
8 {
9     static int myNUmber = 0;
10     //checking whether the number is prime or not
11     static boolean isPrime(int num)
12     {
13         if (num <= 1)
14             return false;
15         if (num <= 3)
16             return true;
17
18         if (num % 2 == 0 || num % 3 == 0)
19             return false;
20
21         for (int i = 5;
22             i * i <= num; i = i + 6)
23             if (num % i == 0 ||
24                     num % (i + 2) == 0)
25                 return false;
26         return true;
27     }
28
29
30     static int SumOfPrimeDivisors(int num)
31     {
32         int sum = 0;
33         for (int i = 1;
34             i <= num; i++)
35         {
36             if (num % i == 0)
37             {
38                 if (isPrime(i))
39                     sum += i;
40             }
41         }
42         return sum;
43     }
44
45     public static void main(String[] args)
46     {
47         Scanner in = new Scanner(System.in);
48         System.out.println("Enter any number: ");
49         myNUmber = in.nextInt();
50         System.out.print("Sum of prime divisors of " + myNUmber + " is " +
51                 SumOfPrimeDivisors(myNUmber) + "\n");
52     }
53 }

We have tested a prime number like 11 and the output is quite expected. But for the next time, we have entered a different value. And see the output.

 1 //output of code 79
2 Enter any number:
3 11
4 Sum of prime divisors of 11 is 11
5
6 -------------------
7
8 Enter any number:
9 456
10 Sum of prime divisors of 456 is 24

It is because 456 is divisible by prime numbers 2, 3, 19\. If you add them, you get 24.

The next problem is much easier than before. Let us take 4 numbers and more to get Sum of even and odd.

 1 // problem 80
2 //code 80
3 package fun.sanjibsinha;
4 /**
5 * input 4 numbers and more to get Sum of Even And Odd
6 */
7 import java.util.*;
8 public class ProblemEighty
9 {
10     static int num=1, sumOfEven=0, sumOOdd=0;
11     public static void main(String[] args){
12
13         Scanner in = new Scanner(System.in);
14         while(num !=0){
15             System.out.println("Enter zero to end");
16             num = in.nextInt();
17
18             if(num!=0){
19                 if(num>0 && num%2==0)
20                     sumOfEven = sumOfEven + num;
21                 if(num>0 && num%2!=0)
22                     sumOOdd = sumOOdd + num;
23             }
24
25             if(num==0)
26                 break;
27         }
28
29         System.out.println("The sum of positive even numbers  = " + sumOfEven);
30         System.out.println("The sum of positive odd numbers  = " + sumOOdd);
31     }
32 }

Here goes the output.

 1 //output of code 80
2 Enter zero to end
3 2
4 Enter zero to end
5 4
6 Enter zero to end
7 3
8 Enter zero to end
9 5
10 Enter zero to end
11 6
12 Enter zero to end
13 9
14 Enter zero to end
15 0
16 The sum of positive even numbers  = 12
17 The sum of positive odd numbers  = 17

In the next problem, we will deal with Fibonacci number. In Mathematics the Fibonacci sequence or series is defined as a series of numbers in which each number ( Fibonacci number ) is the sum of the two preceding numbers. The simplest is the series 1, 1, 2, 3, 5, 8, etc. It could be complex.

We will find the sum of first ten Fibonacci numbers.

 1 // problem 81
2 //code 81
3 package fun.sanjibsinha;
4
5 //find the sum of first ten Fibonacci numbers
6 class SumOfFirstFibonacciNumbers{
7
8     //we need a method that will return the sum
9     public int findTheSum(int n){
10         if (n <= 0)
11             return 0;
12
13         int fibo[]=new int[n+1];
14         fibo[0] = 0; fibo[1] = 1;
15
16         int sum = fibo[0] + fibo[1];
17
18         for (int i=2; i<=n; i++)
19         {
20             fibo[i] = fibo[i-1]+fibo[i-2];
21             sum += fibo[i];
22         }
23
24         return sum;
25     }
26
27 }
28
29 public class ProblemEightyOne {
30
31     static int num = 0;
32
33     public static void main(String args[])
34     {
35         num = 10;
36         SumOfFirstFibonacciNumbers fiboObject = new SumOfFirstFibonacciNumbers();
37         System.out.println("Sum of first ten Fibonacci numbers is : " + fiboObject.f\
38 indTheSum(num));
39     }
40 }

The output reflects the sum of first ten Fibonacci numbers.

1 //output of code 81
2 Sum of first ten Fibonacci numbers is : 143

The next problem will examine whether the number is ‘Duck’ or not. In Mathematics, the Duck number is defined as a number which has zeroes present in it. However, not in the beginning of the number. For example 3210, 7056 are Duck numbers. But not 0321, or 0756.

 1 // problem 82
2 //code 82
3 package fun.sanjibsinha;
4
5 //check whether a number is Duck Number or not.
6
7 import java.util.Scanner;
8
9 class DuckNumber{
10
11     public int checkingDuck(String num){
12
13         int len = num.length();
14         int countZero = 0 ;
15         char myChar;
16
17         for(int i = 1; i < len; i++)
18         {
19             myChar = num.charAt(i);
20             if(myChar == '0')
21                 countZero++;
22         }
23         return countZero ;
24     }
25 }
26
27 public class ProblemEightyTwo
28 {
29     static int num = 0;
30     static String str;
31     static char digitAtIndexZero;
32
33     public static void main(String[] args){
34         DuckNumber myDuck = new DuckNumber();
35         Scanner sc = new Scanner(System.in);
36         System.out.println("Enter a number to check whether the number is a Duck num\
37 ber or not: ");
38         num = sc.nextInt();
39         String num1 = Integer.toString(num);
40         str = Integer.toString(num);
41         digitAtIndexZero = str.charAt(0);
42         if( myDuck.checkingDuck(str) > 0 && digitAtIndexZero != '0')
43             System.out.println("It is a duck number");
44         else
45             System.out.println("It is not a duck number");
46     }
47 }

We are taking inputs from the users to examine the nature of the number.

1 //output of code 82
2 Enter a number to check whether the number is a Duck number or not:
3 123
4 It is not a duck number
5 Enter a number to check whether the number is a Duck number or not:
6 1023
7 It is a duck number

We might use the loop statement to form many types of patterns. The triangle pattern is one of them.

 1 // problem 83
2 //code 83
3 package fun.sanjibsinha;
4
5 // how to create triangle patterns
6
7 class TrianglePattern{
8
9     public void printStars(int n){
10         int i, j;
11
12         for(i=0; i < n; i++)
13         {
14
15             for(j=0; j<=i; j++)
16             {
17                 System.out.print("* ");
18             }
19             System.out.println();
20         }
21     }
22
23 }
24
25 public class ProblemEightyThree
26 {
27     static int num = 0;
28     public static void main(String args[])
29     {
30         TrianglePattern patternObject = new TrianglePattern();
31         num = 5;
32         patternObject.printStars(num);
33     }
34 }

It will form the triangle pattern, which is quite commonly used in find solutions of other problems.

1 //output of code 83
2 *
3 * *
4 * * *
5 * * * *
6 * * * * *

The next problem seems to appear in Java community quite often. Finding the Armstrong number in a given range is rather a code heavy experience. Before that we should know what that exactly mean in number theory. It is also known as a narcissistic number, because it is the sum of its own digits each raised to the power of the number of digits.

Consider the number 153\. The number of digits is 3\. Now, if each digit of that number is raised to the power of 3, the sum is equal to 153.

Keeping that logic in mind, from 0 to 9, all numbers are Armstrong or narcissistic number.

 1 // problem 84
2 //code 84
3 package fun.sanjibsinha;
4 // find Armstrong numbers based on user's input
5
6 import java.util.Scanner;
7
8 public class ProblemEightyFour
9 {
10     public static void main(String[] args) {
11         int num, lastDigit, digits, sum, i;
12         int start, end;
13
14         Scanner sc = new Scanner(System.in);
15
16         /*
17         Taking inputs of lower and upper limit from user
18         */
19         System.out.println("Enter lower limit: ");
20         start = sc.nextInt();
21         System.out.println("Enter upper limit: ");
22         end = sc.nextInt();
23
24         System.out.println("Armstrong number between " + start + " and " + end + " a\
25 re : ");
26
27         for(i=start; i<=end; i++)
28         {
29             sum = 0;
30
31             /* Copying the value of num for processing */
32             num = i;
33
34             /* Finding total digits in num */
35             digits = (int) java.lang.StrictMath.log10(num) + 1;
36
37             /* Calculating the sum of power of digits */
38             while(num > 0)
39             {
40                 /* Extracting the last digit */
41                 lastDigit = num % 10;
42
43                 // Finding sum of power of digits
44                 sum = sum + (int)java.lang.StrictMath.pow(lastDigit, digits);
45
46                 /* Removing the last digit */
47                 num = num / 10;
48             }
49
50             /* Finally checking for Armstrong number */
51             if(i == sum)
52             {
53                 System.out.println(i);
54             }
55         }
56     }
57 }

In the above code, we are taking two inputs from the user – the lower limit and the upper limit. We are trying to find all the Armstrong numbers between 0 to 10,000.

 1 //output of code 84
2 Enter lower limit:
3 0
4 Enter upper limit:
5 10000
6 Armstrong number between 0 and 10000 are :
7 0
8 1
9 2
10 3
11 4
12 5
13 6
14 7
15 8
16 9
17 153
18 370
19 371
20 407
21 1634
22 8208
23 9474

The next problem will be little bit tricky one. We will find the result of a series like this: 2 + 4 – 6 + 8 - … up to n.

Here the last number ‘n’ is determined by the user.

 1 // problem 85
2 //code 85
3 package fun.sanjibsinha;
4
5 import java.util.*;
6
7 public class ProblemEightyFive {
8
9     static int num, sum;
10
11     public static void main(String[] args){
12         System.out.println("We are going to get a sum of series like 2 -4 + 6 - 8 +.\
13 ..upto n:");
14         System.out.println("Enter the value of n here: ");
15         Scanner in = new Scanner(System.in);
16         num = in.nextInt();
17
18         for(int i = 2; i <= num; i = i + 2){
19             if(i % 4 == 0){
20                 sum = sum - i;
21             } else{
22                 sum = sum + i;
23             }
24         }
25         System.out.println("Sum of series upto " + num + " terms is : " + sum);
26     }
27 }

We have taken two values to examine how they change according to the value of n.

 1 //output of code 85
2 We are going to get a sum of series like 2 -4 + 6 - 8 +...upto n:
3 Enter the value of n here:
4 50
5 Sum of series upto 50 terms is : 26
6
7 ------------------------
8
9 We are going to get a sum of series like 2 -4 + 6 - 8 +...upto n:
10 Enter the value of n here:
11 20
12 Sum of series upto 20 terms is : -10
13
14 -------------------------------
15
16 We are going to get a sum of series like 2 -4 + 6 - 8 +...upto n:
17 Enter the value of n here:
18 13
19 Sum of series upto 13 terms is : -6

The next problem will showcase a rather weird number that is known as ‘Palindromic Prime’ or in short ‘pal prime’. A number, which is simultaneously palindrome and prime.

 1 // problem 86
2 //code 86
3 package fun.sanjibsinha;
4 /*
5 finding the PalPrime number
6 */
7 import java.util.*;
8
9 public class ProblemEightySix {
10
11     static int num, temp, last, sum = 0, origin = 0;
12
13     public static void main(String args[])
14     {
15         Scanner sc = new Scanner(System.in);
16
17         System.out.println("Enter any number : ");
18         //taking inputs from user
19         num = sc.nextInt();
20         //storing the user input in a temporary variable
21         temp = num;
22         for(int i = 1; i <= temp; i++)
23         {
24             if(temp % i == 0)
25             {
26                 origin++;
27             }
28         }
29         while(num > 0)
30         {
31             //extracting the last digit
32             last = num % 10;
33             //storing it
34             sum = (sum * 10) + last;
35             //extract all digits except the last
36             num = num / 10;
37         }
38         //comparing with the original number
39         if(temp == sum && origin == 2)
40         {
41             System.out.println("Number is PalPrime : " + temp);
42         }
43         else
44         {
45             System.out.println("Number is not PalPrime : " + temp);
46         }
47     }
48 }

We have tested more than one number to examine whether they are Palindromic Prime or not.

1 //output of code 86
2 Enter any number
3 313
4 Number is PalPrime : 313
5 -------------------------
6
7 Enter any number
8 444
9 Number is not PalPrime : 444

Another common prime number we face in the number system which is called twisted prime. When the reversed prime number is also prime, we call it twisted prime. Example is 97\. The reverse of 97 is 79, which is also prime.

 1 // problem 87
2 //code 87
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 class TwistedPrime{
8
9     static int temp, remain;
10
11     static int reverseNumber(int num){
12         while (num > 0){
13             remain = num % 10;
14             temp = temp * 10 + remain;
15             num /= 10;
16         }
17         return temp;
18     }
19     static boolean isPrime(int num){
20         if (num <= 1)
21             return false;
22         if (num <= 3)
23             return true;
24
25         if (num % 2 == 0 || num % 3 == 0)
26             return false;
27
28         for (int i = 5; i * i <= num; i = i + 6)
29             if (num % i == 0 || num % (i + 2) == 0)
30                 return false;
31
32         return true;
33     }
34
35     static boolean isTwistedPrime(int num){
36         if (isPrime(num) == false)
37             return false;
38
39         return isPrime(reverseNumber(num));
40     }
41
42 }
43
44 public class ProblemEightySeven {
45
46     static int num = 0;
47
48     public static void main(String[] args)
49     {
50         Scanner in = new Scanner(System.in);
51         System.out.println("Enter a number to check whether that is twisted prime nu\
52 mber or not: ");
53         num = in.nextInt();
54         if(TwistedPrime.isTwistedPrime(num)){
55             System.out.println("The number " + num + " is a twisted prime number.");
56         }
57         else{
58             System.out.println("The number " + num + " is not a twisted prime number\
59 .");
60         }
61     }
62 }

We have taken more then one numbers to examine whether these numbers are twisted prime or not.

1 //output of code 87
2 Enter a number to check whether that is twisted prime number or not:
3 23
4 The number 23 is not a twisted prime number.
5 --------------------------------------
6 Enter a number to check whether that is twisted prime number or not:
7 101
8 The number 101 is a twisted prime number.

Before we have seen how we can form triangle patterns with the help of loop statements. Now we can test it on string variable.

 1 // problem 88
2 //code 88
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 public class ProblemEightyEight {
8
9     static int len;
10     static String str, strUpper;
11
12     public static void main(String[] args){
13         try {
14             Scanner in = new Scanner(System.in);
15             System.out.println("Enter a string");
16             str = in.nextLine();
17             System.out.println("You entered string " + str);
18             strUpper = str.toUpperCase();
19             System.out.println("Your entered-string changes to upper case " + strUpp\
20 er);
21             len = strUpper.length();
22             for(int i = 0; i < len - 1; i++){
23
24                 for(int j = 0; j < i; j++){
25                     System.out.print(strUpper.charAt(j));
26                 }
27                 System.out.println(strUpper.charAt(i));
28             }
29         }
30         catch(Exception e)
31         {
32             System.err.println(e);
33         }
34     }
35 }

You can enter any string and the program will start reading the character from the first index. As we know that a string is a sequence of characters. So we can play around any string.

 1 //output of code 88
2 Enter a string
3 sanjib
4 You entered string sanjib
5 Your entered-string changes to upper case SANJIB
6 S
7 SA
8 SAN
9 SANJ
10 SANJI

Now you have learned to solve many types of different problems that, sometimes, are code-heavy. We will finish this long loop chapter with two more common problems, which seem to be rather easier than what you have seen before.

The problem 89 is a program that will reverse any number.

 1 // problem 89
2 //code 89
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 class ReversingNumber{
8     static int temp, remain;
9     static int reverseNumber(int num){
10         while (num > 0){
11             remain = num % 10;
12             temp = temp * 10 + remain;
13             num /= 10;
14         }
15         return temp;
16     }
17 }
18 public class ProblemEightyNine {
19     static int num;
20     public static void main(String[] args) {
21         Scanner sc = new Scanner(System.in);
22         System.out.println("Enter any number to reverse : ");
23         //taking inputs from user
24         num = sc.nextInt();
25         System.out.println("We are going to reverse the number :" + num + " The resu\
26 lt is: "
27                 + ReversingNumber.reverseNumber(num));
28     }
29 }

Here goes the output where we have taken any number from user:

1 //output of code 89
2 Enter any number to reverse :
3 123456
4 We are going to reverse the number :123456 The result is: 654321

The final problem of this chapter is probably the most common problem, finding whether the number is prime or not.

 1 // problem 90
2 //code 90
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 class FindPrime{
8
9     static boolean isPrime(int num){
10         if (num <= 1)
11             return false;
12         if (num <= 3)
13             return true;
14
15         if (num % 2 == 0 || num % 3 == 0)
16             return false;
17
18         for (int i = 5; i * i <= num; i = i + 6)
19             if (num % i == 0 || num % (i + 2) == 0)
20                 return false;
21
22         return true;
23     }
24 }
25
26 public class ProblemNinety {
27     static int num;
28     public static void main(String[] args) {
29         Scanner sc = new Scanner(System.in);
30         System.out.println("Enter any number to find it is prime or not : ");
31         //taking inputs from user
32         num = sc.nextInt();
33         if(FindPrime.isPrime(num)){
34             System.out.println("You have entered : " + num + ". It is prime.");
35         } else {
36             System.out.println("You have entered : " + num + ". It is not prime.");
37         }
38     }
39 }

Here user can enter any number to examine whether the number is prime or not. We can take more than one numbers to test it.

1 //output of code 90
2 Enter any number to find it is prime or not :
3 12
4 You have entered : 12\. It is not prime.
5 ---------------------------------------
6 Enter any number to find it is prime or not :
7 11
8 You have entered : 11\. It is prime.

If you have written all the code snippets in your favorite code editor, then it is commendable. Understanding all types of loop statements is extremely important. We are trying to learn from the problems presented here. It will take time to get your head around all the code snippets. The next chapter will give you an introduction to the mostly used package of Java, which handles the user inputs.

Chapter Nine: Basic Input and Output in Java

We have seen before how to take input from the users. How to use Scanner class is not completely new to us. However, we need to make further investigation regarding this matter for one reason.

Our goal is to create a software that is interactive. In that regard, Scanner class is the latest development that helps us to write less code. Before that, we used ‘InputStreamReader’. It reads bytes and turns them to characters. The ‘read()’ method of InputStreamReader invokes the reading of bytes from the underlying byte-input stream.

We increase the efficiency of InputStreamReader by wrapping the new InputStreamReader object within a BufferedReader object. The constructor of

InputStreamReader passes one ‘System.in’ object that reads the input from the keyboard.

Consequently the process becomes complex. To avoid that complexities Java has introduced Scanner class through which we can easily take the user’s input.

The next problem shows us that complexities.

 1 // problem 91
2 //code 91
3 package fun.sanjibsinha;
4
5 import java.io.BufferedReader;
6 import java.io.IOException;
7 import java.io.InputStreamReader;
8
9 public class ProblemNinetyOne {
10
11     static String name;
12     static int age;
13
14     public static void main(String[] args) throws IOException {
15
16         BufferedReader str = new BufferedReader(new InputStreamReader(System.in));
17         System.out.println("Enter your name ");
18         name = str.readLine();
19         System.out.println("Your name : " + name);
20         int i = 0;
21         for(i = 0; i <= name.length(); i++){
22             System.out.println(i);
23         }
24         System.out.println();
25         int j = 0;
26         while (j <= name.length()){
27             j++;
28             System.out.println(j);
29         }
30     }
31 }

In the output, we have seen how it works. To understand the underlying mechanism of reading the byte streams and the conversion of characters we have read the length of the characters also. As usual, in ‘for loop statement’ the index starts from 0, and the ‘while loop statement’ begins with 1.

 1 //output of code 91
2 Enter your name
3 John Smith
4 Your name : John Smith
5 0
6 1
7 2
8 3
9 4
10 5
11 6
12 7
13 8
14 9
15 10
16
17 1
18 2
19 3
20 4
21 5
22 6
23 7
24 8
25 9
26 10
27 11

In the above output, the white space between the name and the ‘Enter’ key at the end, takes two bytes more. In this process the InputStreamReader acts as a bridge to convert byte to characters.

On the contrary, Scanner is a class in ‘java.util’ package. We use this class to obtain input of all the primitive types like ‘int, float, double, etc’, along with strings. This is the easiest way to read user inputs from the keyboard.

The next problem shows us how Scanner class takes input and produces output. After the output, we will briefly discuss the underlying mechanism.

 1 // problem 92
2 //code 92
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 public class ProblemNinetyTwo {
8
9     /*
10     we could have declared it as static outside main() method and used inside the cl\
11 ass
12     */
13     // static Scanner userInput = new Scanner(System.in);
14
15     public static void main(String[] args)
16     {
17         Scanner sc = new Scanner(System.in);
18         System.out.print("Your favorite number: ");
19
20         if (sc.hasNextInt())
21         {
22             int numEntered = sc.nextInt();
23
24             System.out.println("You entered " + numEntered);
25
26             // you can do every basic mathematical operations
27             int addTheNumberEntered = numEntered + numEntered;
28             System.out.println("Adding together: " + addTheNumberEntered);
29             numEntered += 1;
30             System.out.println("1 increment: " + numEntered);
31             numEntered -= 2;
32             System.out.println("2 decrement: " + numEntered);
33
34             numEntered++;
35             System.out.println("One increment: " + numEntered);
36             numEntered--;
37             System.out.println("One decrement: " + numEntered);
38
39         } else {
40             System.out.println("Sorry you have not entered an integer");
41         }
42     }
43 }

Here goes the output, where we can see how we can do all the mathematical operations on the user input.

1 //output of 92
2 Your favorite number: 563
3 You entered 563
4 Adding together: 1126
5 1 increment: 564
6 2 decrement: 562
7 One increment: 563
8 One decrement: 562

As you see in the above code, we have passed the predefined object ‘System.in’ as a parameter inside the Scanner constructor. The ‘System.in’ object represents the standard input stream. You can pass any other object, such as an object of class File, if we want to read the input from the file.

If we want to read certain primitive data type like ‘int’, we use the ‘nextInt()’ method. For ‘float’ we use ‘nextFloat()’, for double we use ‘nextDouble()’, and for string we use ‘nextLine()’. As you may presume, there are others for Boolean, Byte, Long, and Short. However, not all the methods we need regularly.

As a rule of thumb, we can also check whether a user input is really an integer or not. When we build a software or any web or mobile application, user inputs play a vital role. But we cannot trust all the users. We want integer inputs but they thought they would try some weird string value instead. We need to be prepared for that.

To check whether the input is integer, we have ‘hasNextInt()’ method. It will return true if the next value entered is an integer. The same rule applies for other data types. In the above code we have similarly checked the user input.

The next problem will show you a same method where we have checked the string input to be true.

 1 // problem 93
2 //code 93
3 package fun.sanjibsinha;
4
5 import java.util.Scanner;
6
7 public class ProblemNinetyThree {
8
9     static String name = "sanjib";
10
11     public static void main(String[] args) {
12
13         System.out.println("Enter your name: ");
14         Scanner sc = new Scanner(System.in);
15         if(sc.hasNext()){
16             String yourName = sc.next();
17             if(yourName.equals(name)){
18                 System.out.println("Your name is: " + yourName);
19                 int i = 0;
20                 while (i <= yourName.length()){
21                     i++;
22                 }
23                 System.out.print("There are " + (i -1) + " characters in your name."\
24 );
25             } else {
26                 System.out.println("You have not entered proper name.");
27             }
28         } else {
29             System.out.println("Next time ...");
30         }
31
32     }
33 }

We have initialized the variable ‘name’ with a string value. Now we expect user’s input should mach the same. If it does not match, it gently reminds her to give proper value.

 1 //output of code 93
2 Enter your name:
3 sanjib
4 Your name is: sanjib
5 There are 6 characters in your name.
6
7 ---------------
8
9 Enter your name:
10 john smith
11 You have not entered proper name.

For the first case, we have entered proper value, and the next time we have entered a wrong value. To read a single character we use this method: ‘next().charAt(0)’.

In this chapter, we have learned to know the basics of scanner class; furthermore, we learned to handle user inputs in a more efficient way, having knowledge of checking user inputs.

Chapter Ten: Classes and Objects

In our previous problems we have seen a Java program creates many objects. Objects interact with other objects by changing their states (or may prefer to call it fields). When it changes its states, it actually invokes methods. These objects interactions accomplish many tasks, simple to full of complexities., such as implementation of a Graphical User Interface (GUI), an animation or something else.

We have also learned that behind an object there is a blueprint, a class. In those classes, we also set some rules so that one object can interacts with other object.

As you progress further, you will find how we can make and break those rules to create different types of design patterns. Unfortunately, that is beyond our scope at present. We will have a very basic introduction to classes and objects to give you an idea how they work.

In the next problem, we will see a parent or super ‘MobileClass’ that has some typical states and methods that a mobile usually has got. We also have a child or subclass ‘ZenyClass’ (you may think about it as a new mobile company) that extends all those states and methods.

Not only ‘ZenyClass’ extends all the features of the superclass, but it also has some of its own. At the later point we have created two ‘ZenyClass’ objects with different features.

 1 // problem 94
2 //code 94
3 // first let us have parent or superclass MobileClass
4 package fun.sanjibsinha;
5
6 public class MobileClass {
7
8     private double height = 0.0;
9     private double width = 0.0;
10     private double thickness = 0.0;
11     private double price = 0.0;
12     private String color;
13     public String name;
14
15     public double getHeight() {
16         return height;
17     }
18     public void setHeight(double height) {
19         this.height = height;
20     }
21
22     public double getWidth() {
23         return width;
24     }
25     public void setWidth(double width) {
26         this.width = width;
27     }
28
29     public double getThickness() {
30         return thickness;
31     }
32     public void setThickness(double thickness) {
33         this.thickness = thickness;
34     }
35
36     public double getPrice() {
37         return price;
38     }
39     public void setPrice(double price) {
40         this.price = price;
41     }
42
43     public String getColor() {
44         return color;
45     }
46     public void setColor(String color) {
47         this.color = color;
48     }
49
50     protected double changeHeight(double height){
51         this.height = height;
52         return height;
53     }
54
55     //generic constructor
56     public MobileClass(){}
57
58     //more complex constructor
59     public MobileClass(String name, String color, double price){
60         this.name = name;
61         this.color = color;
62         this.price = price;
63     }
64 }

Next we will see how the child or subclass ‘ZenyClass’ looks like:

 1 // here is a blueprint of ‘ZenyClass’
2 /*
3 class cannot extend multiple classes
4 so we cannot write like this: public class ZenyClass extends MobileClass, MobileFeat\
5 ures
6 */
7
8 public class ZenyClass extends MobileClass {
9
10     private double batteryStrength = 0.0;
11     private int pixel = 10;
12     private double mins = 60.0;
13     private int days = 0;
14
15     public double getBatteryStrength() {
16         return batteryStrength;
17     }
18     public void setBatteryStrength(double batteryStrength) {
19         this.batteryStrength = batteryStrength;
20     }
21
22     public double getMins() {
23         return mins;
24     }
25     public void setMins(double mins) {
26         this.mins = mins;
27     }
28
29     public double takeCharge(double mins){
30         this.mins = mins;
31         return mins;
32     }
33     public double batteryCanLast(int days){
34         this.days = days;
35         return days;
36     }
37
38     public ZenyClass(){}
39     public ZenyClass(String name, String color, double price, double mins){
40         super(name, color, price);
41         this.mins = mins;
42     }
43 }

Finally we want to create two different ‘ZenyClass’ objects in our main application so that two objects (MobileClass and its extension ZenyClass) interact with each other.

Now you may ask, you have not created the superclass objects. Then how it interacts with the subclass? First of all, we have extended all the states and methods of a superclass to a subclass. We have given permission to the subclass to use all those features that it has inherited from its superclass. Besides, a subclass can easily modify any methods of superclass if it wants to.

Furthermore, the subclass can add its own features as situation demands.

We have not repeated any feature of MobileClass in our subclass. That is code redundancy. We don’t want it. And why should we do that? We have already extended all the features of the superclass.

 1 // creating ‘ZenyClass’ objects
2 package fun.sanjibsinha;
3
4 public class ProblemNinetyFour {
5
6     public static void main(String[] args) {
7         ZenyClass zenyOne = new ZenyClass();
8         zenyOne.name = "My Zeny";
9         zenyOne.setHeight(6.12);
10         System.out.println(zenyOne.name + " has height of " + zenyOne.getHeight() + \
11 " inches.");
12         System.out.println();
13         ZenyClass zenyTwo = new ZenyClass("Zeny", "Red", 45.00, 20);
14         System.out.println(zenyTwo.name + " has color: " + zenyTwo.getColor());
15         System.out.println(zenyTwo.name + "'s price: " + zenyTwo.getPrice() + " Euro\
16 .");
17         System.out.println(zenyTwo.name + " takes charge of : "
18                 + zenyTwo.takeCharge(12.23) + " minutes.");
19         System.out.println(zenyTwo.name + " has battery lasting power of "
20                 + (int)zenyTwo.batteryCanLast(2) + " days.");
21
22     }
23 }

As you look at the output, you will find that two ZenyClass objects, (in reality, they are two different types of brand) have different features.

1 //output of code 94
2 My Zeny has height of 6.12 inches.
3
4 Zeny has color: Red
5 Zeny's price: 45.0 Euro.
6 Zeny takes charge of : 12.23 minutes.
7 Zeny has battery lasting power of 2 days.

The above code snippets represent very basic staff just to give you a very brief introduction as I have told. In the next problem, we can find some more information about these two objects.

To do that in our main application, we have used some default methods that tell us more about these objects. Are they equal? Do they have any unique identifier when they are created? Which classes do they belong to?

 1 // problem 95
2 //code 95
3 package fun.sanjibsinha;
4
5 public class ProblemNinetyFive {
6
7     public static void main(String[] args) {
8         ZenyClass zenyOne = new ZenyClass();
9         zenyOne.name = "New Zeny";
10         zenyOne.setHeight(7.12);
11         System.out.println(zenyOne.name + " has height of " + zenyOne.getHeight() + \
12 " inches.");
13         System.out.println("The New Zeny mobile object has unique identifier: " + ze\
14 nyOne.hashCode());
15         System.out.println(zenyOne.name + " represents the " + zenyOne.getClass());
16         System.out.println();
17         ZenyClass zenyTwo = new ZenyClass("ZenyModified", "Blue", 55.00, 10);
18         System.out.println(zenyTwo.name + " has color: " + zenyTwo.getColor());
19         System.out.println(zenyTwo.name + "'s price: " + zenyTwo.getPrice() + " Euro\
20 .");
21         System.out.println(zenyTwo.name + " takes charge of : "
22                 + zenyTwo.takeCharge(6.23) + " minutes.");
23         System.out.println(zenyTwo.name + " has battery lasting power of "
24                 + (int)zenyTwo.batteryCanLast(3) + " days.");
25         System.out.println("The ZenyModified mobile object has unique identifier: "
26                 + zenyTwo.hashCode());
27         System.out.println(zenyTwo.name + " represents the " + zenyTwo.getClass());
28
29         if(zenyOne.equals(zenyTwo)){
30             System.out.println(zenyOne.name + " is equal to " + zenyTwo.name);
31         } else {
32             System.out.println(zenyOne.name + " is not equal to " + zenyTwo.name);
33         }
34
35     }
36 }

If you run these code snippets in your favorite IDE, you will find all those answers.

 1 //output of code 95
2 New Zeny has height of 7.12 inches.
3 The New Zeny mobile object has unique identifier: 1020923989
4 New Zeny represents the class fun.sanjibsinha.ZenyClass
5
6 ZenyModified has color: Blue
7 ZenyModified's price: 55.0 Euro.
8 ZenyModified takes charge of : 6.23 minutes.
9 ZenyModified has battery lasting power of 3 days.
10 The ZenyModified mobile object has unique identifier: 1635546341
11 ZenyModified represents the class fun.sanjibsinha.ZenyClass
12 New Zeny is not equal to ZenyModified

We have learned to create different objects. We have also learned many untold information about objects. Now in the next problem, we will throw a quick glance at another object-oriented-programming concept, Polymorphism.

Polymorphism in Java

To explain Polymorphism in a few sentences, we can think of computer mouse.

Consider the ‘double click’ feature. It is a state changing method, of course, if you want to write a mouse class and create an object.

When we double click a Word Document, it opens up on the text editor. When we double click on an executable file, the program starts running.

Similar objects often get the same message but do different things. That is Polymorphism in a nutshell. The next problem will show you how this concept of Polymorphism is applied in our superclass and subclass. Let us see the problem first.

 1 // problem 96
2 //code 96
3 package fun.sanjibsinha;
4
5 /*
6 How Polymorphism works
7 */
8
9 public class ProblemNinetySix {
10
11     public static void main(String[] args) {
12         MobileClass mob = new MobileClass();
13         MobileClass aMobile = new ZenyClass();
14         mob.name = "Mob";
15         aMobile.name = "A Mobile";
16
17         if(aMobile.equals(mob)){
18             System.out.println(mob.name + " is equal to " + aMobile.name);
19         } else {
20             System.out.println(mob.name + " is not equal to " + aMobile.name);
21         }
22
23         System.out.println();
24         MobileClass anotherMobile
25                 = new ZenyClass("Another Zeny", "Blue", 65.00, 5);
26         System.out.println(anotherMobile.name + " has color: " + anotherMobile.getCo\
27 lor());
28         System.out.println(anotherMobile.name + "'s price: " + anotherMobile.getPric\
29 e() + " Euro.");
30
31         /*
32         System.out.println(anotherMobile.name + " takes charge of : "
33                 + anotherMobile.takeCharge(6.23) + " minutes.");
34
35                 Error:(14, 32) java: cannot find symbol
36 symbol:   method takeCharge(double)
37 location: variable anotherMobile of type fun.sanjibsinha.MobileClass
38
39         */
40
41         System.out.println("The ZenyModified mobile object has unique identifier: "
42                 + anotherMobile.hashCode());
43     }
44 }

Before taking a look at the output, let us examine this line of code in particular.

1 MobileClass anotherMobile
2                 = new ZenyClass("Another Zeny", "Blue", 65.00, 5);

Here the reference variable ‘anotherMobile’ should have pointed to the ‘MobileClass’ object, right? That would have been the usual scenario. Instead, it points to a subclass object and acts differently. If we had written it in the usual manner, creating a ‘MobileClass’ object, it would have acted in a different way.

Let us see the output and it will be clear how similar objects get the same message but do different things.

1 //output of code 96
2 Mob is not equal to A Mobile
3
4 Another Zeny has color: Blue
5 Another Zeny's price: 65.0 Euro.
6 The ZenyModified mobile object has unique identifier: 1684106402

In a very short space, we have discussed a few important object-oriented-programming concepts; although the code snippets are very basic one.

In the next chapter, we will discuss another important concept: interface and abstract methods.

Chapter Eleven: Interface and Abstraction

Using Interface in object-oriented-programming is really tricky. The concept demands more attention than it appears. We have already seen some examples of abstraction or encapsulation. A class is a good example of abstraction. It encapsulates every detail from the users.

Users do things with objects without knowing what is happening behind, how it was designed in a blueprint. Interface takes that concepts of abstraction to a higher level. Let us give a concrete example to understand how it works.

Suppose a school wants to measure the weight of every student for medical purpose. The school authority hires a contractor and gives the contract. The school authority does not care about how the work has been done. They want records and the contract is implemented. The students also don’t know why their weights are taken. Now this contract can be implemented in other spheres. A book company might want to compare the number of pages of the books they have published. They can also implement this.

Since the objects are nouns, we treat interfaces as adjectives that tells us something about the objects. In the above scenario, the student objects are comparable. The book objects are also comparable.

Another advantage of interface is we can implement multiple interfaces. Just like a noun that may have multiple adjectives. A person is good as well as honest.

A class can be extended and at the same time, it may implement multiple interfaces. The next problem is a showcase for the same example.

 1 // problem 97
2 //code 97
3 package fun.sanjibsinha;
4 /*
5 class cannot extend multiple classes
6 so we cannot write like this: public class CatyClass extends MobileClass, MobileFeat\
7 ures
8 */
9 public class CatyClass extends MobileClass implements MobileUpgradable {
10
11     private double batteryStrength = 0.0;
12     private int pixel = 10;
13     private double mins = 60.0;
14     private int days = 0;
15     public double version = 1.0;
16
17     public double getVersion() {
18         return version;
19     }
20
21     public void setVersion(double version) {
22         this.version = version;
23     }
24
25     public double getBatteryStrength() {
26         return batteryStrength;
27     }
28     public void setBatteryStrength(double batteryStrength) {
29         this.batteryStrength = batteryStrength;
30     }
31
32     public double getMins() {
33         return mins;
34     }
35     public void setMins(double mins) {
36         this.mins = mins;
37     }
38
39     public double takeCharge(double mins){
40         this.mins = mins;
41         return mins;
42     }
43     public double batteryCanLast(int days){
44         this.days = days;
45         return days;
46     }
47
48     public CatyClass(){}
49     public CatyClass(String name, String color, double price, double mins){
50         super(name, color, price);
51         this.mins = mins;
52     }
53
54 }

After the class declaration, we need an interface.

1 package fun.sanjibsinha;
2
3 interface MobileUpgradable {
4
5     double getVersion();
6     void setVersion(double version);
7 }

And finally, we need the main application.

 1 package fun.sanjibsinha;
2
3 public class ProblemNinetySeven {
4
5     public static void main(String[] args) {
6         CatyClass catyOne = new CatyClass();
7         catyOne.name = "New Caty";
8         catyOne.setHeight(8.12);
9         System.out.println(catyOne.name + " has height of " + catyOne.getHeight() + \
10 " inches.");
11         System.out.println("The New Zeny mobile object has unique identifier: " + ca\
12 tyOne.hashCode());
13         System.out.println(catyOne.name + " represents the " + catyOne.getClass());
14         System.out.println();
15         catyOne.version = 2.0;
16         System.out.println(catyOne.name + " has version " + catyOne.version);
17         catyOne.setVersion(3.0);
18         System.out.println(catyOne.name + " is upgraded to " + catyOne.getVersion());
19     }
20 }

Through the contract ‘MobileUpgradable’ now the new mobile object can implement the new version. Exactly that has been done.

Watch the output, and you will get the idea.

1 //output of code 97
2 New Caty has height of 8.12 inches.
3 The New Zeny mobile object has unique identifier: 1720435669
4 New Caty represents the class fun.sanjibsinha.CatyClass
5
6 New Caty has version 2.0
7 New Caty is upgraded to 3.0

By default the interface methods are ‘public’ and ‘abstract’. So we don’t have to mention it when we declare a method in the interface.

The next problem is the showcase of the discussion we have had earlier. I hope this example will give you more clear insights about this contract is being implemented.

First, we will see the code snippets of the interface and after that we have two classes that have implemented that contract and finally we will have the main application.

 1 // problem 98
2 //code 98
3 package fun.sanjibsinha;
4
5
6 public interface Comparable {
7
8     public boolean isGreaterThan(Comparable toOther);
9
10 }
11
12 Next, the Student class that implements the contract.
13
14 public class Student implements Comparable {
15     public int weight;
16
17     public boolean isGreaterThan(Comparable toOther) {
18         Student otherStudent = (Student) toOther;
19         if (this.weight < otherStudent.weight)
20             return false;
21         else if (this.weight > otherStudent.weight)
22             return true;
23         else
24             return false;
25     }
26 }

Next, the Book class that implements the same contract.

 1 public class Book implements Comparable {
2
3     public int pages;
4
5     public boolean isGreaterThan(Comparable toOther) {
6         Book otherBook = (Book) toOther;
7         if (this.pages < otherBook.pages)
8             return false;
9         else if (this.pages > otherBook.pages)
10             return true;
11         else
12             return false;
13     }
14 }

Finally, we have the main application body.

 1 public class ProblemNinetyEight {
2
3     public static void main(String[] args) {
4         Student st1 = new Student();
5         Student st2 = new Student();
6         st1.weight = 20;
7         st2.weight = 30;
8         System.out.println(st1.isGreaterThan(Comparable.class.cast(st2)));;
9         System.out.println();
10         Book b1 = new Book();
11         Book b2 = new Book();
12         b1.pages = 100;
13         b2.pages = 99;
14         System.out.println(b1.isGreaterThan(Comparable.class.cast(b2)));
15     }
16 }

From the above code snippet, you can guess what kind of output we might have.

1 //output of code 98
2 false
3
4 true

I wish I could write more about classes, objects and interfaces now. But this book is not meant for that, so I have to stop here.

Anyway, understanding the object-oriented-programming concepts is extremely important. Especially understanding the idea of abstraction in object-oriented-programming, is compulsory.

The next chapter will display the case of exception handling.

Chapter Twelve: Exception Handling

As the chapter headline tells you this chapter will also be very short and it is written to give you an idea about how Java handles errors.

A Brief Note on Exception Handling

As an error occurs, an exception object is created. This exception object tells us about the error that occurred. There are many types of exception objects that are created during the programming. One of them is ‘java.lang.Exception’. The Java compiler checks for these exceptions.

Exceptions can be thrown during the normal operation of the Java Virtual Machine (JVM). As programmers, it is our responsibility to catch them.

Here, in the next problem we will learn to handle one of the most common Java exceptions – the ‘ArithmeticException’. You cannot divide a number by zero.

 1 // problem 99
2 //code 99
3 package fun.sanjibsinha;
4
5 class CheckingDivision{
6
7     public int num;
8
9     public void restrictDivisionByZero(int num){
10         try{
11             this.num = num;
12             System.out.println(num/0);
13
14         }
15         catch (ArithmeticException e){
16
17             //your custom message
18             System.out.println("You can't divide by 0");
19             //java's error message
20             System.out.println(e.getMessage());
21             //the exception name and error message
22             System.out.println(e.toString());
23             //you can also print the standard error stack trace
24             e.printStackTrace();
25
26         }
27     }
28
29 }
30
31 public class ProblemNinetyNine {
32
33     public static void main(String[] args) {
34         CheckingDivision checkDivision = new CheckingDivision();
35         checkDivision.restrictDivisionByZero(10);
36     }
37
38 }

In the output, we have the custom message first. After that we get the java’s error message. The the exception name and error message are displayed after that. And finally, we get the standard error stack trace.

1 //output of code 99
2 You can't divide by 0
3 / by zero
4 java.lang.ArithmeticException: / by zero
5
6 java.lang.ArithmeticException: / by zero
7     at fun.sanjibsinha.CheckingDivision.restrictDivisionByZero(ProblemNinetyNine.jav\
8 a:10)
9     at fun.sanjibsinha.ProblemNinetyNine.main(ProblemNinetyNine.java:33)

As you will progress, you will encounter a few more common exceptions that occur in Java programming. Sometimes, we forget to pass the parameters. It gives us ‘IllegalArgumentException’. While handling with an array you may encounter this exception ‘IndexOutOfBoundsException’. These exceptions are very verbose, so you can understand what types of exceptions occur. You may call a class that does not exist, thereafter you get the ‘ClassNotFoundException’.

There are several more exceptions that we have not discussed here. However, I hope, a single problem has thrown some light on the topic.

Chapter Thirteen: Data Structure, A Brief Introduction

The last problem of the book, that is the hundredth problem knocks on the door of a very big topic – data structures and algorithm. In my opinion, it deserves a separate book that might give you a fair idea of what they actually are. Our next Java bootcamp for Intermediate Learners will start with Data Structures, Algorithm and Time Complexity. Do not forget to check that out.

It is a very big topic, in the sense, as we progress the volume of data is multiplying. We need to know how to store, sort, search and do many and varied operations using that data. This is not a easy task. That is why the term ‘Big Data’ has popped up. Learning data structures and algorithm gets more attention now.

How will we manage this collection of data? You have already seen array. However, array has many limitations, such as it holds fixed number of values of a single type. You cannot change it.

To overcome such limitations, Java introduces core collection interfaces. They encapsulate different type of collections. You have learned the role of an interface, it is actually a contract. So it allows collections to be manipulated independently. The foundation of Java Collections Framework consists of such Core Collection Interfaces.

They are ‘Set’, ‘List’, ‘Queue’, ‘Deque’, and ‘Map’. In the last problem, we have seen an example of ‘LinkedList’ class, which is a collection based on a Linked List. As the name suggests, it is a collection of container that holds data and each container has a link identifier that links it either to the next one or the previous one. The last link identifier is always ‘null’, because it points to nothing.

Now it goes on like this: A links to B, B links to C, C links to D and so on. If you want to add an object (suppose E) in between C and D, Java sets new link identifiers for everyone and the chain is not broken. It is automatically maintained as before. Only a new data structure emerges.

They are particularly good when you wan to perform many additions and deletions with a collection. You can add anywhere, delete any value anywhere.

The next problem will show you how a LinkedList works. However, I would not go any further. You will find the detail in my ‘Data Structures and Algorithm’ book.

 1 // problem 100
2 //code 100
3 package fun.sanjibsinha;
4
5 import java.util.LinkedList;
6
7 public class ProblemHundred {
8
9     public static void main(String[] args) {
10         //creating a linked list that contains strings
11         LinkedList<String> cart = new LinkedList<String>();
12         cart.add("Book");
13         cart.add("Grocery");
14         cart.add("Garments");
15         cart.add("Mobile");
16         /*
17         for(String item : cart){
18             System.out.print(item + ", ");
19         }
20
21         it will print
22         Book, Grocery, Garments, Mobile,
23         */
24         //adding last element
25         cart.addLast("TV");
26         //adding first element
27         cart.addFirst("Bottle");
28         /*
29         for(String item : cart){
30             System.out.print(item + ", ");
31         }
32
33         it will now print: Bottle, Book, Grocery, Garments, Mobile, TV,
34         */
35         cart.add(0, "Refrigerator");
36         cart.set(3, "Medicine");
37         /*
38         for(String item : cart){
39             System.out.print(item + ", ");
40         }
41
42         printing: Refrigerator, Bottle, Book, Medicine, Garments, Mobile, TV,
43         in the new list Grocery is replaced by Medicine
44         */
45         //we can create a copy or back-up of the above collection
46         LinkedList<String> backUp = new LinkedList<String>(cart);
47         /*
48         System.out.println(backUp);
49         it gives us exact copy of the cart
50         [Refrigerator, Bottle, Book, Medicine, Garments, Mobile, TV]
51         */
52         /*
53         System.out.println(cart.indexOf("Book"));
54         System.out.println(cart.get(2));
55         printing:
56         2
57         Book
58         */
59         //we can remove items either using index or value
60         /*
61         cart.remove(0);
62         cart.remove("Refrigerator");
63         cart.removeFirst();
64         cart.removeLast();
65
66         */
67         //wec can check whether the cart and the copy contains the same
68
69         if(cart.containsAll(backUp)){
70             System.out.println("It is same.");
71         } else {
72             System.out.println("Not same.");
73         }
74         //let us remove the last value from the copy
75         backUp.removeLast();
76         System.out.println(backUp);
77         //the last value TV is deleted
78         //it does not affect the original linked list
79         System.out.println(cart);
80         backUp.push("TV");
81         System.out.println(backUp);
82         //now the backup has been rearranged
83         // [TV, Refrigerator, Bottle, Book, Medicine, Garments, Mobile]
84
85     }
86
87 }

You need to read the comments to understand how the LinkedList works actually. All methods have not been shown here. We have added, deleted, moved objects; the output shows us the result.

1 //output of code 100
2 It is same.
3 [Refrigerator, Bottle, Book, Medicine, Garments, Mobile]
4 [Refrigerator, Bottle, Book, Medicine, Garments, Mobile, TV]
5 [TV, Refrigerator, Bottle, Book, Medicine, Garments, Mobile]

I hope you get an idea about data structures; although this is a very basic idea.

Through hundred problems we have tried to understand the core basic concepts of Java. We have just scratched the surface without digging it further. However, we have discussed those problems that are particularly searched for, asked in the Java interviews. I hope that helps you as a beginner.

What Next

You cannot learn anything by reading a single book, or watching a single video. It takes time and only practice makes you perfect.

In my opinion, learning is incomplete without thinking. Never copy and paste code. Read code first, understand the concepts behind it, write it down on your notebook, and then write the algorithm on your own. You may write it in a better way.

Besides keeping practice and writing code everyday, you need to think about how it works. Before using anything, you need to understand why you need to use it.

Think about data types. Can we move a user defined data type like objects from one class to other, just like any other primitive data types? Ask yourself, find the answer. Furthermore, read the Java documentation. It helps.

You will get all the source code of this book at this GitHub repository:

[https://github.com/sanjibsinha/HundredProblemsInJava](https://github.com/sanjibsinha/HundredProblemsInJava)

Happy learning, happy coding; wish you best of luck. Meet you in the next Java coding bootcamp for Intermediate learners.