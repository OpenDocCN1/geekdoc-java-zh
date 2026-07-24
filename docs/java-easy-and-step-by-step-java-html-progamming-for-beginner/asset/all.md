![](Images/cover00063.jpeg)

Java Html Programming For Beginners

 Copyright 2014 by S.J. Cole - All rights reserved.

This document is geared towards providing exact and reliable information in regards to the topic and issue covered. The publication is sold with the idea that the publisher is not required to render accounting, officially permitted, or otherwise, qualified services. If advice is necessary, legal or professional, a practiced individual in the profession should be ordered.

- From a Declaration of Principles which was accepted and approved equally by a Committee of the American Bar Association and a Committee of Publishers and Associations.

In no way is it legal to reproduce, duplicate, or transmit any part of this document in either electronic means or in printed format. Recording of this publication is strictly prohibited and any storage of this document is not allowed unless with written permission from the publisher. All rights reserved.

The information provided herein is stated to be truthful and consistent, in that any liability, in terms of inattention or otherwise, by any usage or abuse of any policies, processes, or directions contained within is the solitary and utter responsibility of the recipient reader. Under no circumstances will any legal responsibility or blame be held against the publisher for any reparation, damages, or monetary loss due to the information herein, either directly or indirectly.

Respective authors own all copyrights not held by the publisher.

The information herein is offered for informational purposes solely, and is universal as so. The presentation of the information is without contract or any type of guarantee assurance.

The trademarks that are used are without any consent, and the publication of the trademark is without permission or backing by the trademark owner. All trademarks and brands within this book are for clarifying purposes only and are the owned by the owners themselves, not affiliated with this document.

Table of Contents

[Introduction](#part0000.xhtml__Toc404012743)

[Java For The Complete Beginner Or Novice](#part0000.xhtml__Toc404012744)

[The inner workings of Java](#part0000.xhtml__Toc404012745)

[Understanding the NetBeans Software](#part0000.xhtml__Toc404012746)

[Understanding Java Comments](#part0000.xhtml__Toc404012747)

[The Structure Of Java Code And How To Run Programs](#part0000.xhtml__Toc404012748)

[How to run Java programs](#part0000.xhtml__Toc404012749)

[Everything About The Output Window](#part0000.xhtml__Toc404012750)

[How To Share Your Java Programs](#part0000.xhtml__Toc404012751)

[Understanding java variables](#part0000.xhtml__Toc404012752)

[Final Advice](#part0000.xhtml__Toc404012753)

Introduction

Computer programming is complicated stuff, especially for the complete beginner. There is one thing though; with a little enthusiasm and a lot of desire to learn, you can learn any computer programming language. Java Html is the most popular programming language, even more popular than C++ or other computer languages. This makes it a must learn for any budding programmer.

Java as a language has gotten a lot of press coverage in recent times. Part of this extensive coverage is the fact that the media touts Java as a complete change in the normal or traditional way of programming. How so? The media holds the view that the language has intentions firmly in being a vehicle for OOP (object-oriented programming) which the media also touts as a serious change to the standards of programming. While the statement may hold some truth, Codes and data structures in OOP have different arrangement, and the OOP environment does indeed have the potential to produce safe, clear, and modular programs. You should not be so quick to buy into the media hype; after all, programming is programming, and the same frame of mind required to create programs is similar across the board regardless of the language used. In fact, anyone who has been in the coding world will tell you that every now and then, there are imaginary illusions of programs that will “have a ripple paradigm shift effect” only for them to fall short of the expectations of the computer that designed them. Nevertheless, this is not to mean that Java is short of exceptional.

While learning any new language may be a challenge, nothing is impossible if you have the correct approach. This is something we shall look at in a chapter of this book. Rather than dedicating an entire chapter on the importance of Java, which I am sure you already know otherwise you would not be here, I will simply state some of the characteristics of Java that make it such a powerful language.

*While it may not exactly be OOP, it is the closest you will get. This makes it a “cleaner” language than C++ or any other computer programming language for that matter. It also makes it easy to make modular programs and reusable code.

*Java as a language is not platform dependent. This means you can write a program the same manner regardless of whether you are running OSX, UNIX, or Windows.

*The language is distributed making it easy to do distributed computing thanks to its networking capability, which is integrated into the language.

*Java is also very secure with the interpreter, compiler, language and run time environment developed with security in mind.

*Early error detection in Java is quite easy since java compilers can detect problems long before the problem even gets to the execution time.

*Java is also multithreaded, which means that you can do several tasks simultaneously unlike in other programs where you need to have some program specific procedures for multithreading to work.

# Java For The Complete Beginner Or Novice

While Java is an exciting language, it is easy to get lost in the maze. This is because to create programs using the language, you need to install a few computer peripherals and programs. This is before you can write a single code. The tool (software) also Interface development interface (IDE) we need to write our code is NETBEANS, which is the most popular IDE for writing programs in Java. Here is the kicker; while it is easy to navigate to the NETBEANS URL and download the program, things are never that easy. For NETBEANS to operate (load up) on your system, you need to install some necessary Java files and components. First, you need the Java Virtual Machine.

Java Virtual Machine

We have already stated that Java is independent from any platform and will run on any modern operating system; this component is the reason why Java does not care what OS you are running. Java Virtual Machine is the program that interprets/processes your code correctly. The program is one of the mandatory programs you must install before you can create any Java code or program. You can download the program from the relevant website.

P.s. Across the web, there are many sources of Java related programs. I suggest you only download all your files from the official Sun Microsystems website, Java’s parent company.

Once you are on the website, you can proceed to download the Java Virtual machine also known as JRE (Java Runtime Environment). Additionally, while on the website, you can check whether your computer is running a version of JRE by clicking on the relevant “do I have Java?” link. The resulting search result will tell you the version of JRE running on your computer, if any.

If you do not have the program installed, install it and restart your computer.

Next is the Java Software development Kit

Java Software Development Kit

After installing the JRE, we are not yet ready to write our first code. At this point, all we have done is installing the support software needed to run Java programs on your computer. You need a tool to write and test code, the Software Development kit, which you can also download from the [Sun Microsystems official](http://www.oracle.com/technetwork/indexes/downloads/index.html?ssSourceSiteId=ocomen) website. I suggest that you download the Java SE (standard edition) and additionally, the JDK 6 that you will find on the Java SE page. When you navigate to the JDK 6 page, you might get confused because there are many options. Depending on the IDE you are using, you can select the relevant option. In our case, we are using NETBEANS so you should locate the following JDK 6 Update X with NetBeans 6.x.

Click on download and head over to the next page to select a download file relevant to your operating system. Download and install the file. It is important to note that the file is a compressed file of over 130 bytes so you should ensure your internet connection is working while you perform the download, otherwise the file might corrupt halfway through the download. So far, we have done everything right. We have downloaded and installed the necessary environments and software needed to write your first code. However, before we launch the applications we have installed, we need to understand the inner working of the world of Java.

## The inner workings of Java

In Java, you write your code on a text editor. However, in NetBeans, there is a special area designated for writing your code. The code you write at this point is “the source code” and you save it with the file extension .java. After you create the source code, you have to turn it into Java Byte Code by running it through the JaVac program; we call this process “compiling”. The JaVac program then creates a .class extension file if there are no errors in the computing process. This (.class) file is the file you run in the Java Virtual Machine. Here is the above explanation in steps

1.  Create a .java extension  source code
2.  Compile a .class extension file by using the JaVac program
3.  Run the complied .class file on the Virtual machine

NetBeans offers you the advantage of creating and compiling for you, behind the scenes. It takes your source code and creates a Java file, then it runs JaVac to compile the .class file. In addition, NetBeans can also run the program within its own software, which saves you the trouble of using a terminal window to type long strings of commands.

This is the inner working of the Java environment/ world. Because you now have a clearer understanding, you can now proceed to launch the NetBeans software and proceed to the next step of our learning process.

# Understanding the NetBeans Software

Now that we have seen the working of Java, installed all the required software, it is time we pick up from where we left in the previous chapter i.e. launching the NetBeans software.

Like every other program, if you learn what to expect when NetBeans launches, you will not stare at your screen blankly wondering what to do next. Here is what to expect. 

The first time you load NetBeans, the system may be a bit slow as it starts all the resources required to run it. Be patient. When the program does start, you need to navigate to start new project which is on File>New Project part of the NetBeans menu at the top. This should be similar to the Image below.

![](Images/image00034.jpeg)

Figure 1

If you look at the above figure, you will notice that the dialog box on the far right hand side has options of the kind of projects you want to create. You can create projects in all the forms available there. In our instance, we are creating a Java application. Therefore, we need to select the Java category and Java application in the project tab and click on next to move on to step two.

When you click on the next button, the program will give you the option of choosing a name for your project. As you type the name of your project, you will notice that the name at the bottom will change to match the name of your project i.e. in “Create Main Class.” We shall aptly name our project “FirstProject”

![](Images/image00035.jpeg)

Figure 2

In the above figure, the “Create Main Class” name is firstproject.Main. We cannot leave it like that otherwise; the class will contain the name “Main”. We need to change it to FirstProject as shown in the figure below.

![](Images/image00036.jpeg)

Figure 3

After renaming, the class created will bear the name “FirstProject”. Notice that the project class name has a capital “F” at the start and a capital “P”. Additionally, the package name has the name “firstproject’ with a lower case “f” and “p”.

The Project Location text box will appear and offer you the option of changing the default save location. If you would prefer to save the file on any other location other than the default area, you can do it here. Additionally, the NetBeans program will also create default folder containing your project name in the same default location you opt for. Clicking on the finish button will prompt NetBeans to work in the background and create the necessary files for use. When it is through, the system will return you to the IDE where you can see and locate all your projects. If by any chance the project area found in the top left corner is not visible, you should navigate to the  window>project tab on the menu bar

![](Images/image00037.jpeg)

Figure 4

You can expand your project by pressing the +symbol, after which, your project will look something similar to the figure below.

![](Images/image00038.jpeg)

Figure 5

You should then click the + on the source package to expand it and peek at your project name. We are doing this to see our Java file source code. This is shown in the figure below.

![](Images/image00039.jpeg)

Figure 6

The source code (the same source code) should appear on the right in the text area and will bear the name FirstProject.java. Sometimes, the code window will not display. This is not something to be overly concerned about, simply click and press enter on the FirstProject.java available in your project window to call up the code window; after this, you can start working on your code. Here is a sample image of the coding window. The @author you part is where your name as an author will appear.

![](Images/image00040.jpeg)

Figure 7

You should note that the class bears the name FirstProject.

public class FirstProject {

How so you wonder. After all, this is actually the same name as that of your java source file available on your project window, FirstProject.java. There is a simple explanation for this. The complier demands of it. Once you run a program, the class name and the source file must match for the compiler to work. What does this mean? It means that if your .java file bears the name firstproject while the class bears the name FirstProject, you will receive a compile error simply because the letter class do not match, i.e. the first one is lower class while the second one is upper class.

Remember that our whole project bears the name first project as a working experiment; you can name your package any other name such as anyprogram the name package does not necessarily have to bear the same name as the java source file or the class found in the source file. The only two that must match are the name of the class and the java source file.

We have now looked at the basics of creating a java source code within the Java environment. Let us move on swiftly.

# Understanding Java Comments

After we have created a new project in the NetBeans program, you may notice that some of the code is grey and contains many asterisks and slashes like in the figure below.

![](Images/image00041.jpeg)

Figure 8

When this occurs, we call the grey’s comments. In the running stages of the program, the grey’s (comments) are moot. This is to mean that you can use the comment feature to state or explain what the code you are creating wants to achieve. You can achieve this by typing two slashes and then the comment. Here is a sample.

//Place your single line comment here

You can have more than one comment line by doing either of the following:

//We are going to

//spread the comments into two

Or

/*
This comment spreads over two lines

*/

If you look at the comment above, you will notice that it starts with /* but ends with */

Additionally, if you look at the previous image (figure 8) you will notice that there are comments that begin with a single forward slash and two asterisks (/**) but end with one asterisks and one forwards slash; this is called a Javadoc comment. For example

/**
*Here is an example of a Javadoc comment

*/

This type of code is for code documentation. You can then turn the documented code into a HTML page that you can share with others if you think it will be helpful to them. You can access the Javadoc comments by clicking run on the NetBeans menu; from the run menu, you should select Generate Javadoc. This will be useful as your coding prowess manifests. However, there is not much to see right now because we have not done much as of yet. You can also choose to delete the Javadoc comments. Here is how our code would look without the comments

![](Images/image00042.jpeg)

Figure 9

Next, we learn how to run programs and the structure of our code.

# The Structure Of Java Code And How To Run Programs

As we were winding up the previous chapter, we cleaned up our code (refer to figure 9). In the figure, you should notice the package name comes first. Additionally, you should note that a semicolon is what ends the line. The semicolon is important and if you omit it, the program will not compile.

package firstproject;

Next is the class name

public class FirstProject {

}

Ideally, you should think of the class as a code segment. However, Java dictates that you tell it where the code segments start and end. You can achieve this by using curly brackets. You can use the left curly bracket at the start of a code, and use the right curly bracket to end the code {this is an example of a curly code segment} you should however note that anything that goes inside the left and right curly is part of the said code segment. Additionally, anything inside both the left and right curly for the class is in fact, a code segment. Here is what I mean:

public static void main( String[ ] args ) {

}

More important than anything else is the word “main”. Why? Because each time any Java program boots up, it first looks for the method bearing the name ‘main’. Simply put, a method is a piece of code. The program then executes codes within the curly as part of the main. There are possibilities that you will get an error message within the Java program if your code does not have a main method. However, since this is the main entry point for your program, there is little chance you will omit it.

The public part of the code (the blue part) simply means that the method is viewable outside that class. On the other hand, static means that the creation of a new object is not necessary while void means that, there is not returnable value and the command gets on with it.

Command line arguments are the parts between the round brackets of the main. Except for the technical bits, you should not concern yourself with this. You should only strive to remember that our class is FirstProject, which contains the method main and that both the class and the main use their own set of curly brackets. You should also remember that a huge part of your code is part of the class FirstProject.

## How to run Java programs

Any program you run on NetBeans will run on the output window that you can find at the bottom of your screen directly underneath your code. This design is logical because, with the output window readily available, you do not have to call up the console window or the terminal because in NetBeans, the output window plays the role of the console.

In NetBeans, you can run a program in a number of ways with the easiest being, pressing the F6 key on your keyword. You can also use the menus found at the top of NetBeans to run the program. In the menus, locate the menu Run and execute the run main project option. Check out the figure below.

![](Images/image00043.jpeg)

Figure 10

In the NetBeans tool bar, you will notice a “green play” arrow; you can use this to run a program.

![](Images/image00044.jpeg)

Figure 11

You can also run a program by navigating to your projects window. This is especially effective in ensuring that the correct source code is running. To do this, you need to click on your java source file contained in the project window and then right click for options. Execute the run command. See figure below.

![](Images/image00045.jpeg)

Figure 12

If you use any of the program execution methods above on our code so far, you should get something similar to figure13 below on the output window

![](Images/image00046.jpeg)

Figure 13

In figure 13 above, you can see that the first line is the run command. The second is our code “My First Project.” If there is something you are not sure of and would like to run the code again, you can simply press the “two almost fast-forward green arrows” visible on figure 13 above.

# Everything About The Output Window

So far, we can create a code and turn it into a program. If we use the example of the code we have made so far, we can successfully turn it into a program even though it will not do much. For our next learning step, we are going to add a code to our project to gauge how it works. We will begin by outputting text to the console frame, and then we are going to add the line below to our main method.

public static void main( String[ ] args ) {

System.out.println( "My First Project" );

}

P.s. After typing the full stop after the “System”, NetBeans will display a list of options that you can choose from, similar to figure 14 below.

![](Images/image00047.jpeg)

Figure 14

If you double click out, it will become part of your code, after which, you can type another full stop. After this full stop, another list of options will pop up. See figure 15 below.

![](Images/image00048.jpeg)

Figure 15

When this list pops up, select println ( ). This prints a line to the output window. However, there has to be text between the round brackets of printIn “()” the text goes between the par of double quote as elaborated in figure 16 below

![](Images/image00049.jpeg)

Figure 16

Once the double quotes are in place, type your text between then (like when writing present spoken word) as illustrated in figure 17 below.

![](Images/image00050.jpeg)

Figure 17

If you look at figure 17 above, you will notice that the line ends in a semicolon. This is synonymous with every complete line of code in Java; a missing semicolon will make the program return errors and fail to compile.

We need to save our work before we test it out; click on the save option or the save all option on the NetBeans tool bar.

Always remember to test your work each time you add any new code to the source code. This is to make sure that your work does not have any error and to make sure that you do not write several codes with many errors.

How To Share Your Java Programs

Every programmer will tell you that the best way to test out your programs is to send it to colleagues for testing. To share, you need to create a JAR file (Java archive file). Luckily, NetBeans can compile the files for you straight from the menu. You need to navigate to the run menu and select “clean and build main project.”

Once you do this, NetBeans saves your complete work inclusive all necessary files in the local directory in a “dist” folder. See figure18 below.

![](Images/image00051.jpeg)

Figure 18

If you double click the dist folder, this is what you will get

![](Images/image00052.jpeg)

Figure 19

In figure 19 above, the files in the dist file is what you send to your “programmer friends”. In the text file, there are instructions on how to run the program on a console and or a terminal window. Send the file to your friends and wait for them to marvel at your programing prowess.

## Understanding java variables

As a programmer fresh out of the minting press, you will want to practice to develop your programming skills. Java programs work by manipulating data stored in memory. In the same manner a database would have variable data, the data in these memories is also variable, which means that the data can be in form of objects, texts, numbers or pointers to other memory areas plus many more. Each of this data has an assigned name that makes it easier for the data to be re-called when needed. The name and value assigned to this data is a “variable.” Let us start by looking at the number values.

There are many options for storing numbers in Java. For storage of whole numbers, e.g. 8-10-12, you use the integer (int) variable. To store 8-4-10-5-12-8 etc. you use the double variable. Storage is done with an equals sign (=). Using our first source code, let us look at some examples

To set up an integer (whole number) you need to add the code below to the main method of your “my first project” project.

public static void main(String[ ] args) {

int first_number;

System.out.println("My First Project");

}

For Java to recognize that you are storing a whole number, you need to first type the word int with a space to follow. Next, you need to coin a name for your integer variable. While you can give the integer variables any name you want, there are some rules you must put into consideration while you are naming.

*A variable name cannot start with a number. This means that using first_number as your variable is ok but using 1st_number is not. This is not to mean that you cannot use numbers as part of your variable name anywhere else; it just cannot be the beginning.

*A variable’s name cannot be the same as a java keyword. These are many and NetBeans will turn them blue like in the example of int above.

*Your variable name cannot contain spaces. If we were to use int first number in the variable declaration, we will get an error and thus the use of the underscore. Additionally, it is not unheard of to have a first word that starts with a low case character while the other words that follow are in upper case e.g. firstNumber, or myFirstNumber

*The name of a variable is case sensitive. This means that there is a difference between firstNumber and FirstNumber

When you need to store something in the variable called first_number you need to type an equals sign followed by the value you intend to store. Follow the code below.

![](Images/image00053.jpeg)

In the above code, we are telling Java we want to store a value of 10 in the integer variable we have so aptly called first_number. You can also do the above in one line if you prefer.

![](Images/image00054.jpeg)

In order to see how this works, you need to tweak the printIn method to this:

System.out.println( "First number = " + first_number );

We now have direct text between the round brackets of the printIn in enclose of double quotes.

("First number = "

Additionally, we have the name of our variable following a +sign

+ first_number );

The + sign simply means join together. This means we are joining the name of our variable to the direct text. This joining process is what we call concatenation.

The figure below, figure20 illustrates how your coding window will appear. You should note the number of times each line ends with a semicolon

![](Images/image00055.jpeg)

Figure 20

If you run the program, here is what should display at the bottom of the output window

![](Images/image00056.jpeg)

Figure 21

The variable number we stored in the variable we gave the name first_number is in the first output directly after the = sign

What if we were to make some additions? Let us add two more int variables. One will store a second number and the other one will store an answer.

![](Images/image00057.jpeg)

In java, we can three variable names on the same line as we have above, but only if the variables are the same (type) which in our instance is the int. additionally, you will notice that each of the variable names separates from the other by a comma.

Here is how our new variable would look like:

![](Images/image00058.jpeg)

For the answer variable, we need to add the first and second number (first+second). In most programming we use the (+) symbol to add. This prompts java to add up the values in the first_number and second_number. Additionally, when it adds up the values, it stores the data total in the variable on the left of the equal sign. This means that instead of assigning 10 or 20 to the variables name, it will automatically add them up and automatically assign. The figure below figure22 describes what we just looked at.

![](Images/image00059.jpeg)

Figure 22

The above figure can also equate to this:

answer = 10 + 20;

However, java is already aware of the values inside the two variable, first_number and second_number, which means you can simply use the names.

To get the output, we need to tweak our printIn method again, to this:

![](Images/image00060.jpeg)

You should also note that we are combining direct text that is surrounded by double quotes. Here is a figure of how your code window should now appear

![](Images/image00061.jpeg)

Figure 23

Again, when you run the program, the figure below is what should display on your output window

![](Images/image00062.jpeg)

Figure 24

Here is a list of what our program has accomplished

1-Stored one number

2-Stored second number

3-Added the two numbers together

4-Stored the addition result in a third variable

5-Printed out all these results

Additionally, we can use numbers directly. To do this, you need to change the answer line to the following

answer = first_number + second_number + 12;

Now run your program and notice what prints out. Notice how little changes in the code affect the overall output.

The maximum value for int value is 2147483647, which means that the numbers you can store are large. If you need to have a minus number, the lowest value is -2147483648\. Values larger than this require the double variable type.

# Final Advice

Here is the thing; programming with Java Html in the initial stages of learning will demand a lot of patience. Remember that it is very easy to lose hope when things are not going as smoothly as you would want. Persevere and you will reap the wonderful and tasty fruits of using java for programming. Programming is all about making mistakes, learning from them, and making better codes as you go along. While learning a new language (programming or otherwise) may be a bit of a task, it is well worth the pain (especially java language).

As a programmer, you cannot overlook the importance of Java in the computer-liberated world we are living in. If you are to have any success, you have to understand this very important language. Additionally, most of the systems in development today are using java more, and more, and abandoning other languages when creating databases and applications. The fact that the operating environment required for working with java are free also helps catapult it to the top of the list of all-time best programming language. As a programmer, I have found that learning java makes it extremely easy to learn all the other programming languages because it prepares you mentally and code wise.

Learning means you have to dedicate some time to learning. It means you have to be prepared to put in the hours of trying, failing, but still trying again. I will leave you with something that sound very shallow but is entire true; practice makes perfect.