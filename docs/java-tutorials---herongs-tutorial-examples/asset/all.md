![](Images/cover00189.jpeg)

Java Tutorials

- Herong's Tutorial Examples

![](Images/image00177.jpeg)

v8.21, 2022

Dr. Herong Yang

Copyright © 2022 by Dr. Herong Yang. All rights reserved.

This tutorial book is a collection of notes and sample codes written by the author while he was learning Java himself. Topics covered in the book include: Java language basics; execution environment; generic classes and parameterized type; generic methods and type argument inferences; enum types and constants; lambda expressions; annotation types and invocations; Java modules; execution threads and synchronization; memory management and garbage collection. Updated in 2022 (Version v8.21) with JDK 17 tutorials. For latest updates and free sample chapters, visit https://www.herongyang.com/Java.

Table of Contents

> [About This Book](#part0002.xhtml)
> 
> [JDK - Java Development Kit](#part0003.xhtml)
> 
> [Downloading and Installing JDK on Windows](#part0004.xhtml)
> 
> [Downloading and Installing JDK on Mac](#part0005.xhtml)
> 
> [Writing My First Java Program](#part0006.xhtml)
> 
> [Adding JDK "bin" Directory to Path Setting](#part0007.xhtml)
> 
> [JDK Documentation Installation](#part0008.xhtml)
> 
> [Execution Process, Entry Point, Input and Output](#part0009.xhtml)
> 
> [Creating, Compiling and Executing Java Programs](#part0010.xhtml)
> 
> [main() Method - Java Execution Entry Point](#part0011.xhtml)
> 
> [Java Execution Console - "in", "out" and "err" Data Streams](#part0012.xhtml)
> 
> [Primitive Data Types and Literals](#part0013.xhtml)
> 
> [Data Types Supported in Java](#part0014.xhtml)
> 
> [Integer Data Types](#part0015.xhtml)
> 
> [Floating-Point Data Types](#part0016.xhtml)
> 
> [Logical (Boolean) Data Type](#part0017.xhtml)
> 
> [Literals of Primitive Types](#part0018.xhtml)
> 
> [Literal Formats for Integers](#part0019.xhtml)
> 
> [Literal Formats for Integers - Example](#part0020.xhtml)
> 
> [Literal Formats for Floating-Point](#part0021.xhtml)
> 
> [Literal Formats for Floating-Point - Example](#part0022.xhtml)
> 
> [Literal Formats for Characters](#part0023.xhtml)
> 
> [Literal Formats for Character - Example](#part0024.xhtml)
> 
> [Control Flow Statements](#part0025.xhtml)
> 
> [What Is Control Flow Statement](#part0026.xhtml)
> 
> ["if-then" Statements](#part0027.xhtml)
> 
> ["if-then-else" Statements](#part0028.xhtml)
> 
> [Nested "if-then-else" Statements](#part0029.xhtml)
> 
> ["switch" Statements](#part0030.xhtml)
> 
> [Fall-Through Behavior of "switch" Statements](#part0031.xhtml)
> 
> [Basic "for" Statements](#part0032.xhtml)
> 
> [Enhanced "for" Statements](#part0033.xhtml)
> 
> ["while" Statements](#part0034.xhtml)
> 
> ["do" Statements](#part0035.xhtml)
> 
> ["break" Statements](#part0036.xhtml)
> 
> [Labeled "break" Statements](#part0037.xhtml)
> 
> ["continue" Statements](#part0038.xhtml)
> 
> [Labeled "continue" Statements](#part0039.xhtml)
> 
> [Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)
> 
> [What Are Bits and Bytes](#part0041.xhtml)
> 
> ["byte" Data Type and Implicit Casting](#part0042.xhtml)
> 
> [Operations on "byte" Data Type Values](#part0043.xhtml)
> 
> [Bitwise Operations on "byte" Values](#part0044.xhtml)
> 
> [Bitwise Operations on "byte" Values - Example Program](#part0045.xhtml)
> 
> [Shift Operations - Left, Right or Unsigned Right](#part0046.xhtml)
> 
> [Managing Bit Strings in Byte Arrays](#part0047.xhtml)
> 
> [setBit() - Storing a Bit into a Byte Array](#part0048.xhtml)
> 
> [getBit() - Retrieving a Bit from a Byte Array](#part0049.xhtml)
> 
> [rotateLeft() - Left Rotating All Bits in a Byte Array](#part0050.xhtml)
> 
> [bitStringTest.java - Testing Program](#part0051.xhtml)
> 
> [Reference Data Types and Variables](#part0052.xhtml)
> 
> [Reference Types Supported in Java](#part0053.xhtml)
> 
> [Creating Class Type Objects](#part0054.xhtml)
> 
> [Class Type Variables Storing References](#part0055.xhtml)
> 
> [Interface Type Variables](#part0056.xhtml)
> 
> [Class and Interface Hierarchy](#part0057.xhtml)
> 
> [Supertype and Subtype](#part0058.xhtml)
> 
> [Explicit and Implicit Type Casting](#part0059.xhtml)
> 
> [Type Casting Example Program](#part0060.xhtml)
> 
> [Type Casting Compile and Runtime Error](#part0061.xhtml)
> 
> [Enum Types and Enum Constants](#part0062.xhtml)
> 
> [What Is an Enum Type](#part0063.xhtml)
> 
> [Use 'class' to Define Enumeration](#part0064.xhtml)
> 
> [Instance Variables for Enum Constants](#part0065.xhtml)
> 
> [java.lang.Enum Super Type](#part0066.xhtml)
> 
> [Enum Constant Inherited Methods](#part0067.xhtml)
> 
> [Enum Constant Implicit Methods](#part0068.xhtml)
> 
> [StringBuffer - The String Buffer Class](#part0069.xhtml)
> 
> [StringBuffer Class Properties and Methods](#part0070.xhtml)
> 
> [SimpleStringBuffer - My Implementation of String Buffer](#part0071.xhtml)
> 
> [Performance Comparison of String and StringBuffer](#part0072.xhtml)
> 
> [System Properties and Runtime Object Methods](#part0073.xhtml)
> 
> [JVM and OS System Properties](#part0074.xhtml)
> 
> [System.setProperty() - Setting Your Own Properties](#part0075.xhtml)
> 
> [Runtime.getRuntime() - Getting the Runtime Object](#part0076.xhtml)
> 
> [freeMemory() - Getting JVM Free Memory Information](#part0077.xhtml)
> 
> [Calculating Memory Usage of an Array](#part0078.xhtml)
> 
> [exec() - Executing Operating System Commands](#part0079.xhtml)
> 
> [Generic Classes and Parameterized Types](#part0080.xhtml)
> 
> [What Is a Generic Class](#part0081.xhtml)
> 
> [Using a Generic Class](#part0082.xhtml)
> 
> [Using a Generic Class - Example](#part0083.xhtml)
> 
> [Creating a Generic Class](#part0084.xhtml)
> 
> [Creating a Generic Class - Example](#part0085.xhtml)
> 
> [Bounded Type Parameters](#part0086.xhtml)
> 
> [Raw Type, Generic Type and Parameterized Type](#part0087.xhtml)
> 
> [Parameterized Type and Subtyping](#part0088.xhtml)
> 
> [Wildcard Parameterized Types](#part0089.xhtml)
> 
> [Wildcard Parameterized Type Test](#part0090.xhtml)
> 
> [Wildcard Parameterized Subtyping](#part0091.xhtml)
> 
> [Wildcard Parameterized Subtyping Example](#part0092.xhtml)
> 
> [Generic Methods and Type Inference](#part0093.xhtml)
> 
> [What Is a Generic Method](#part0094.xhtml)
> 
> [Comparing Generic Method with Non-Generic Method](#part0095.xhtml)
> 
> [Non-Generic Method Example - maxNonGeneric()](#part0096.xhtml)
> 
> [Generic Method Example - maxGeneric()](#part0097.xhtml)
> 
> [Generic Methods in java.util.Collections Class](#part0098.xhtml)
> 
> [Testing Generic Methods in Collections Class](#part0099.xhtml)
> 
> [What Is Type Argument Inference](#part0100.xhtml)
> 
> [Type Argument Inference by Parameter List](#part0101.xhtml)
> 
> [Type Argument Inference by Return Value](#part0102.xhtml)
> 
> [Generic Methods using Parameterized Types](#part0103.xhtml)
> 
> [Parameterized Type as Generic Method Return Type](#part0104.xhtml)
> 
> [Lambda Expressions and Method References](#part0105.xhtml)
> 
> [What Is Lambda Expression](#part0106.xhtml)
> 
> [LambdaCalculator.java - Lambda Expression Example](#part0107.xhtml)
> 
> [Lambda Expression Syntax Options](#part0108.xhtml)
> 
> [Lambda Expression as Method Reference](#part0109.xhtml)
> 
> [Method Reference Example - LambdaMethodRefernce.java](#part0110.xhtml)
> 
> [Lambda Expression Stream Pipeline Operations](#part0111.xhtml)
> 
> [Java Modules - Java Package Aggregation](#part0112.xhtml)
> 
> [What Is Java Module](#part0113.xhtml)
> 
> [Module Descriptor - module-info.java](#part0114.xhtml)
> 
> [Creating "Hello World!" Module](#part0115.xhtml)
> 
> ["jmod create" - Creating JMOD File](#part0116.xhtml)
> 
> ["jlink --add-modules" - Creating Custom JRE](#part0117.xhtml)
> 
> [Running ".\bin\java" Command in Custom JRE](#part0118.xhtml)
> 
> [Accessing Non-Exported Package in Module](#part0119.xhtml)
> 
> [Module Dependency and Package Accessibility](#part0120.xhtml)
> 
> [com.herongyang.base Module Implementation](#part0121.xhtml)
> 
> [com.herongyang.base Module Compilation](#part0122.xhtml)
> 
> [com.herongyang.math Module Implementation](#part0123.xhtml)
> 
> [geometryJRE and Module Deliverables](#part0124.xhtml)
> 
> [Getting com.herongyang.base Module Info](#part0125.xhtml)
> 
> [Testing Exported Package in Module](#part0126.xhtml)
> 
> [Testing Un-Exported Package in Module](#part0127.xhtml)
> 
> [Application using com.herongyang.math Module](#part0128.xhtml)
> 
> [Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)
> 
> [What Are Processes and Threads](#part0130.xhtml)
> 
> [The "Thread" Class - Creating Thread Objects With Thread Sub Classes](#part0131.xhtml)
> 
> [The "Runnable" Interface - Creating Thread Objects with Runnable Objects](#part0132.xhtml)
> 
> [CPU Execution Time Shared by Multiple Threads](#part0133.xhtml)
> 
> [CPU Execution Time Shared by Multiple Threads - Test Output](#part0134.xhtml)
> 
> [Application Data Shared by Multiple Threads](#part0135.xhtml)
> 
> [Application Data Shared by Multiple Threads - Test Results](#part0136.xhtml)
> 
> [interrupt() - Method to Terminate Thread](#part0137.xhtml)
> 
> [ThreadGroup Class and "system" ThreadGroup Tree](#part0138.xhtml)
> 
> ["ThreadGroup" Class - Container of Threads and Thread Groups](#part0139.xhtml)
> 
> [Displaying the "system" ThreadGroup Tree](#part0140.xhtml)
> 
> [Adding Threads and Thread Groups](#part0141.xhtml)
> 
> [Synchronization Technique and Synchronized Code Blocks](#part0142.xhtml)
> 
> [Why Synchronization Is Needed in Multi-Threading Applications](#part0143.xhtml)
> 
> [Synchronization Technique - Lock and Synchronized Code](#part0144.xhtml)
> 
> ["synchronized" - How Java Supports Synchronization](#part0145.xhtml)
> 
> [BankingThread.java - Synchronization Sample Program](#part0146.xhtml)
> 
> [BankingThread.java - Synchronization Sample Program Output](#part0147.xhtml)
> 
> [Deadlock Condition Example Programs](#part0148.xhtml)
> 
> [What Is Deadlock](#part0149.xhtml)
> 
> [Deadlock Example - 5 Dining Philosophers](#part0150.xhtml)
> 
> [Deadlock Example - Transferring Funds](#part0151.xhtml)
> 
> [Garbage Collection and the gc() Method](#part0152.xhtml)
> 
> [Garbage Collection and Unused Objects](#part0153.xhtml)
> 
> [The Automated Garbage Collection Process](#part0154.xhtml)
> 
> [gc() - The Garbage Collection Method](#part0155.xhtml)
> 
> [Example Program of Using the gc() Method](#part0156.xhtml)
> 
> [Assert Statements and -ea" Option](#part0157.xhtml)
> 
> ["assert" Statements](#part0158.xhtml)
> 
> [JVM "-ea" and "-da" Options](#part0159.xhtml)
> 
> [Annotation Statements and Declarations](#part0160.xhtml)
> 
> [What Is Annotation](#part0161.xhtml)
> 
> [Use "interface" as Annotation](#part0162.xhtml)
> 
> [Default Values for Annotation Elements](#part0163.xhtml)
> 
> [Single-Element Annotation Invocation](#part0164.xhtml)
> 
> [No-Element (Marker) Annotation Invocation](#part0165.xhtml)
> 
> [getAnnotations() Method - Annotation APIs](#part0166.xhtml)
> 
> [Predefined Annotation Types](#part0167.xhtml)
> 
> [Java Related Terminologies](#part0168.xhtml)
> 
> [Archived Tutorials](#part0169.xhtml)
> 
> [Archived: Downloading and Installing JDK 10](#part0170.xhtml)
> 
> [Archived: JDK 10 Documentation Installation](#part0171.xhtml)
> 
> [Archived: Downloading and Installing JDK 8](#part0172.xhtml)
> 
> [Archived: Downloading and Installing JDK 1.7](#part0173.xhtml)
> 
> [Archived: Downloading and Installing JDK 1.6](#part0174.xhtml)
> 
> [Archived: Downloading and Installing JDK 1.5](#part0175.xhtml)
> 
> [Archived: JDK 1.3 Bug - Memory Leak With Unstarted Threads](#part0176.xhtml)
> 
> [References](#part0177.xhtml)

**Keywords:** Java, Language, Tutorial

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟About This Book

This section provides some detailed information about this book - Java Tutorials - Herong's Tutorial Examples.

**Title:** Java Tutorials - Herong's Tutorial Examples

**Author:** Dr. Herong Yang - Contact by email via herong_yang@yahoo.com.

**Category:** COMPUTERS / Programming Languages / Java

**Version/Edition:** v8.21, 2022

**Number of pages in PDF format:** 341

**Description:** This tutorial book is a collection of notes and sample codes written by the author while he was learning Java himself. Topics covered in the book include: Java language basics; execution environment; generic classes and parameterized type; generic methods and type argument inferences; enum types and constants; lambda expressions; annotation types and invocations; Java modules; execution threads and synchronization; memory management and garbage collection. Updated in 2022 (Version v8.21) with Java 17 tutorials.

**Keywords:** Java, variable, type, expression, statement, method, class, package, module, thread, deadlock.

**Cost/Price:** Free in Web format

**Copyright:**

*   This book is under Copyright © 2022 by Dr. Herong Yang. All rights reserved.
*   Material in this book may not be published, broadcasted, rewritten or redistributed in any form.
*   The example codes is provided as-is, with no warranty of any kind.

**Revision history:**

*   Version 8.21, 2022\. Updated with Java 17.
*   Version 8.10, 2018\. Added Java Module tutorials.
*   Version 8.00, 2018\. Updated with Java 10.
*   Version 7.00, 2014\. Updated with Java 8.

**Web version:** [https://www.herongyang.com/Java](https://www.herongyang.com/Java) - Provides free sample chapters, latest updates and readers' comments. The Web version of this book has been viewed a total of:

*   1,714,845 times as of December 2021.
*   1,638,051 times as of December 2020.
*   1,569,354 times as of December 2019.
*   1,514,290 times as of December 2018.
*   1,455,289 times as of December 2017.
*   1,390,927 times as of December 2016.
*   1,309,223 times as of December 2015.
*   1,195,256 times as of December 2014.
*   1,058,373 times as of December 2013.
*   913,999 times as of December 2012.
*   797,813 times as of December 2011.
*   540,252 times as of December 2010.
*   309,845 times as of December 2009.
*   140,533 times as of December 2008.

**PDF/EPUB version:** [https://www.herongyang.com/Java/PDF-Full-Version.html](https://www.herongyang.com/Java/PDF-Full-Version.html) - Provides information on how to obtain the full version of this book in PDF, EPUB, or other format.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JDK - Java Development Kit

This chapter provides tutorial notes on installing JDK on your own Windows system to run Java programs. Topics include downloading and installing JDK; compiling and executing Java programs, installing JDK documentation.

> [Downloading and Installing JDK on Windows](#part0004.xhtml)
> 
> [Downloading and Installing JDK on Mac](#part0005.xhtml)
> 
> [Writing My First Java Program](#part0006.xhtml)
> 
> [Adding JDK "bin" Directory to Path Setting](#part0007.xhtml)
> 
> [JDK Documentation Installation](#part0008.xhtml)

Conclusion:

*   Downloading and installing JDK on Windows or Mac computers is easy and fast.
*   Compiling and running the first Java program requires 2 commands: "javac" and "java".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK - Java Development Kit](#part0003.xhtml)

∟Downloading and Installing JDK on Windows

This section describes how to download and install JDK on a Windows system.

To learn Java, you need to have a copy of JDK (Java Development Kit) installed on your machine. If you are a Windows computer user, you can follow this tutorial to download and install JDK 17 on your Window computer.

*   Open the Java SE Download page with this URL: [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/).
*   Click the "Windows" tab under the "Java SE Development Kit 17.0.1 downloads". You will see a new page with a list of different download files of JDK 17.
*   Click the hyper link of "https://download.oracle.com/java/17/latest/jdk-17_windows-x64_bin.exe", next to "x64 Installer 152 MB".
*   Save jdk-17_windows-x64_bin.exe to a temporary directory.
*   Double-click on jdk-17_windows-x64_bin.exe to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

The picture below shows you how the JDK 17 Installation Screen looks like:

![](Images/image00178.jpeg)

JDK 17 Installation Screen

To test the installation, open a command window to try the java command. If you are getting the following output, your installation is good:

```
 herong> \progra~1\java\jdk-17.0.1\bin\java -version

java version "17.0.1" 2021-10-19 LTS
Java(TM) SE Runtime Environment (build 17.0.1+12-LTS-39)
Java HotSpot(TM) 64-Bit Server VM 
  (build 17.0.1+12-LTS-39, mixed mode, sharing)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK - Java Development Kit](#part0003.xhtml)

∟Downloading and Installing JDK on Mac

This section describes how to download and install JDK 13 on a macOS system.

To learn Java, you need to have a copy of JDK (Java Development Kit) installed on your machine. If you are a Mac computer user, you can follow this tutorial to download and install JDK 13 on your Mac computer.

1\. Go to Oracle Java SE download website at [oracle.com/technetwork/java/javase/downloads/index.html](https://www.oracle.com/technetwork/java/javase/downloads).

2\. Click "Download" next to "Java Platform (JDK) 13".

3\. Click "jdk-13_osx-x64.bin.tar.gz" from the download list. It will be saved to your "Downloads" directory automatically.

4\. Start a Terminal window and run commands below to install it.

```
 herong$ cd ~/Downloads

herong$ gunzip jdk-13_osx-x64.bin.tar.gz

herong$ tar -xf jdk-13_osx-64.bin.tar

herong$ sudo mv jdk-13.jdk/ /Library/Java/JavaVirtualMachines/
```

To test the installation, open a command window to try the java command. If you are getting the following output, your installation is good:

```
 herong$ java -version

java version "13" 2019-09-17
Java(TM) SE Runtime Environment (build 13+33)
Java HotSpot(TM) 64-Bit Server VM (build 13+33, mixed mode, sharing)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK - Java Development Kit](#part0003.xhtml)

∟Writing My First Java Program

This section provides a tutorial example on how to write, compile, and execute the first Java program with JDK.

When JDK is installed on your machine, it provides two commands for you to compile and run Java programs.

*   "javac class_name.java" - Compiles a Java program stored a file named with the program class name.
*   "java -classpath . class_name" - Runs a compiled Java program. "-classpath ." specifies the current directory as the class path.

Let's try these commands with a very simple Java program. Use NotePad to enter the following Java program into a file called Hello.java:

```
 class Hello {
   public static void main(String[] a) {
      System.out.println("Hello world!");
   }
}
```

Then compile this program in a command window with the "javac" command:

```
 herong> \progra~1\java\jdk-17.0.1\bin\javac Hello.java
```

To execute the program, use the java command:

```
 herong> \progra~1\java\jdk-17.0.1\bin\java Hello

Hello world!
```

Congratulations, you have successfully entered, compiled and executed your first Java program.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK - Java Development Kit](#part0003.xhtml)

∟Adding JDK "bin" Directory to Path Setting

This section provides a tutorial on how to add JDK 'bin' directory to the 'path' system envirnoment variable.

In order to run Java compiler and JVM by typing their program file name without the directory path name, I updated the "path" environment variable on my Windows computer:

*   Open "Control Panel > System and Security > System".
*   Click "Advanced system settings".
*   Click "Environment Variables".
*   Select "System variables > Path" and click "Edit".
*   Add "C:\Progra~1\java\jdk-17.0.1\bin;" to the beginning of the current path list.
*   Click "OK" to save the change.

Then I ran the "echo %path%" command in a new command window to confirm the change:

```
 herong> echo %path%

C:\Progra~1\java\jdk-17.0.1\bin;
   C:\Program Files\Common Files\Oracle\Java\javapath;
   C:\ProgramData\Oracle\Java\javapath;
   ...
```

Now I should be able to run Java commands without the directory path name:

```
 herong> java -version

java version "17.0.1" 2021-10-19 LTS
...

herong> javac hello.java

herong> java Hello

Hello world!
```

Now I am ready to play with Java tools included in Oracle JDK package!

![](Images/image00179.jpeg)

Adding JDK "bin" Directory to Path Setting

You can also set a new environment variable called "java_home" to avoid typing the full path name to access Java tool program files:

```
 herong> set java_home=C:\Progra~1\java\jdk-17.0.1

herong> %java_home%\bin\java -version

java version "17.0.1" 2021-10-19 LTS
...
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK - Java Development Kit](#part0003.xhtml)

∟JDK Documentation Installation

This section describes how to install JDK Documentation on your own local machine.

To learn JDK more effectively, you definitely need to have a copy of the JDK Documentation installed on your own machine. JDK Documentation provides you detailed information of all classes and methods used in JDK. Here is what I did to download and install JDK 17 Documentation on my local machine.

*   Open the Java download home page with this URL: [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/).
*   Click the "Documentation Download" button near the bottom of the page. You will see "Java SE Development Kit 17 Documentation" page showing up.
*   Click the hyper link of "jdk-17.0.1_doc-all.zip".
*   Save the download file "jdk-17.0.1_doc-all.zip" to a temporary directory.
*   Double-click on "jdk-17.0.1_doc-all.zip" to extract all files to "C:\Program Files\Java\jdk-17.0.1 directory.

To verify the installation, open the "C:\Program Files\Java\jdk-17.0.1\docs\index.html" with a Web browser. You should see the JDK 17 Documentation starting page.

Click the "java.logging" module on the JDK 17 Documentation page to see the API documentation of the java.logging module.

If you are a Mac user, you need to extract all files from "jdk-17.0.1_doc-all.zip" to /Library/Java/JavaVirtualMachines/jdk-17.jdk directory. And open "docs/index.html" from that directory in a Web browser.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Execution Process, Entry Point, Input and Output

This chapter provides tutorial notes and tutorial examples on Java program execution process. Topics include Java program creation, compilation and execution; the main() method - execution entry point; execution console, input and output data streams.

> [Creating, Compiling and Executing Java Programs](#part0010.xhtml)
> 
> [main() Method - Java Execution Entry Point](#part0011.xhtml)
> 
> [Java Execution Console - "in", "out" and "err" Data Streams](#part0012.xhtml)

Conclusion:

*   3 steps are involved in building a Java application: creating source code, compiling source code and executing the compiled code.
*   "public static void main(String[] a)" is the execution entry point when a class is launched in the Java Virtual Machine (JVM).
*   JVM provided 3 default I/O data streams to all applications: "in", "out" and "err".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Process, Entry Point, Input and Output](#part0009.xhtml)

∟Creating, Compiling and Executing Java Programs

This section describes the process of Java program creation, compilation and execution. JDK 'javac' and 'java' commands are also described.

There are 3 steps involved in building and running a Java program:

*   **Creating Program Source Code**: Creating one text file written Java language statements to define each Java class or other program unit. The text file is called source code file, which must have a file name identical to the name of the class defined in the file, and an extension of ".java". One of the source code files should define the main class which contains the "main" method as the execution starting point. Other source code files define additional classes and other program units to support the main class.
*   **Compiling Source Code**: Converting all source code files of the program into bytecode files written in Java Virtual Machine (JVM) instructions. The bytecode file must have the same file name as the source code file, and an extension of ".class".
*   **Executing the Java Program**: Loading the bytecode file of the main class into JVM, and executing its JVM instructions starting from the "main" method.

Creating a source code file can be done by a simple text editor, notepad, or a sophisticated Java development environment tool, like Eclipse, or Visual J++.

Compiling a source code file needs a Java compiler. The JDK package contains a Java compiler, which can be invoked by the command "javac". The "javac" command takes source code file names as command line arguments. For example, entering the following command in command window will invoke the "javac" compiler to compile the "Hello.java" source code file:

```
 herong> javac Hello.java
```

The "javac" command also has several command options available:

*   -d: Specify the directory where the bytecode files generated by the compiler should be placed, if you don't want to place them in the current directory.
*   -classpath: Specify the directories where to search for classes or interfaces definitions in bytecode format, if the classes or interfaces are used in source code file.
*   -sourcepatch: Specify the directories where to search for classes or interfaces definitions in source code format, if the classes or interfaces are used in source code file.

For example, the following command:

```
 herong> javac -d .\cls -classpath .\lib;.\cls \
   -sourcepath .\src .\src\Hello.java
```

invokes the "javac" compiler, and tells it to:

*   Compile the "Hello.java" source code file in the ".\src" directory.
*   Place the bytecode file, "Hello.class", in the ".\cls" directory.
*   Search ".\lib" and ".\cls" directories for the definitions in bytecode format of classes or interfaces that are used in "Hello.java".
*   Search ".\src" directory for the definitions in source code format of classes or interfaces that are used in "Hello.java".

Executing a Java program needs a JVM. The JDK also contains a JVM, called HotSpot, which can be invoked by the command "java". The "java" command takes the name of the starting class as the command argument. For example, the following command:

```
 herong> java -classpath .\lib;.\cls;. Hello
```

invokes HotSpot to:

*   Load "Hello" class into HotSpot.
*   Execute the main() method of the "Hello" class.

The "-classpath" option specifies the class path, which contains directories where the JVM will search for the bytecode files of the starting class and other program units when needed.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Process, Entry Point, Input and Output](#part0009.xhtml)

∟main() Method - Java Execution Entry Point

This section describes the Java program entry point, the main() method of the starting class. Command line arguments are passed as an string array parameter to the main() method.

As mentioned in the previous section, a Java application program must have a main class with a special method call main() as the execution entry point. The main() method must be defined as:

```
 public static void main(String[] a) {
      // statement block
   }
```

Note that the main() method must be declared as "public static void".

The parameter of the main() method is an array of "String", which contains the additional arguments after the class name argument in the "java" command line. Let's use the following Java program to illustrate how those arguments are passed into the main() method:

```
 /* CommandLine.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class CommandLine {
   public static void main(String[] a) {
      System.out.println("Number of arguments = "+a.length);
      for (int i=0; i<a.length; i++) {
         System.out.println("  a["+i+"] = "+a[i]);
      }
   }
}
```

After compiling the class, execute it with the following command line:

```
 herong> javac CommandLine.java

herong> java -classpath . CommandLine bread milk banana apple

Number of arguments = 4
  a[0] = bread
  a[1] = milk
  a[2] = banana
  a[3] = apple
```

4 arguments are specified in the command line after the class name. The JVM put them in an array of 4 elements and pass the array as a parameter to the main() method.

Execute it again with a slightly different command line:

```
 herong> java -classpath . CommandLine "bread milk" "banana apple"

Number of arguments = 2
  a[0] = bread milk
  a[1] = banana apple
```

This time, double quotes are used to make two space delimited words as a single argument.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Process, Entry Point, Input and Output](#part0009.xhtml)

∟Java Execution Console - "in", "out" and "err" Data Streams

This section provides a tutorial example on how to use default input and output data streams: System.in, System.out and System.err.

When the JVM is executing a Java application program, it needs a console window to provides 3 predefined input and output data streams to the Java program: to:

*   System.in: Standard input stream connected to the console window.
*   System.out: Standard output stream connected to the console window.
*   System.err: Standard error stream connected to the console window.

When you use JDK package to execute a Java program, the console window is the same window where you entered the "java" command.

Note that all 3 standard streams are defined as public static variables of the "System" class. We have used the "System.out" in our first Java program, Hello.java, to print the hello message on the console window. Here is another program that uses all 3 standard streams:

```
 /* Reverser.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.io.*;
public class Reverser {
   public static void main(String[] arg) {
      InputStream in1 = System.in;
      InputStreamReader in2 = new InputStreamReader(in1);
      BufferedReader in = new BufferedReader(in2);
      PrintStream out = System.out;
      PrintStream err = System.err;
      err.println("This program reverses the character positions of ");
      err.println("each line from the standard input stream.");
      err.println("Enter '.' to end the program.");
      try {
         String s = in.readLine();
         while (s!=null) {
            char[] a = s.toCharArray();
            if (s.equals(".")) break;
            int n = a.length;
            for (int i=0; i<n/2; i++) {
               char c = a[i];
               a[i] = a[n-1-i];
               a[n-i-1] = c;
            }
            out.println(new String(a));
            s = in.readLine();
         }
      } catch (IOException e) {
         err.println(e.toString());
      }
   }
}
```

Note that:

*   The "System.in" is an "InputStream" object, which only offers methods to read in information as bytes. To be able to read as one "String" per line, I need to convert "System.in" to a "BufferedReader" object.
*   The "while" loop should end when "System.in" reaches the end of the stream. However, HotSpot for Windows gives you no way to indicate the end of the standard input stream from the key board. So I used a special pattern, one and only one character '.' in a line, to end the loop.

Compile and run the program with the following command:

```
 herong> javac Reverser.java

herong> java -classpath . Reverser
```

Then enter the following text from key board:

```
 Fish, I love you and respect you very much.
But I will kill you dead before this day ends.
.
```

I see following on the console window:

```
 This program reverses the character positions of
each line from the standard input stream.
Enter '.' to end the program.
Fish, I love you and respect you very much.
.hcum yrev uoy tcepser dna uoy evol I ,hsiF
But I will kill you dead before this day ends.
.sdne yad siht erofeb daed uoy llik lliw I tuB
.
```

Note that:

*   The first 3 lines are from the "System.err" stream.
*   The 4th, 6th, and 8th lines are copies of the text lines of the "System.in" stream, because the console window is echoing everything I typed in on the keyboard.
*   The 5th and 7th lines are from the "System.out" stream.

Windows system can also redirect the console input and output to files. First, I saved the 2 lines of text and the '.' into a file called input.txt, then run the following command:

```
 herong> java -classpath . Reverser < input.txt > output.txt
```

I only got the text from the "System.err" on the console window:

```
 This program reverses the character positions of
each line from the standard input stream.
Enter '.' to end the program.
```

The output.txt file contains:

```
 .hcum yrev uoy tcepser dna uoy evol I ,hsiF
.sdne yad siht erofeb daed uoy llik lliw I tuB
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Primitive Data Types and Literals

This chapter provides tutorial notes and example codes on primitive data types and literals. Topics include 8 primitive data types; storage size of each data type; format rules on source code literals for each data type; example Java programs on primitive types.

> [Data Types Supported in Java](#part0014.xhtml)
> 
> [Integer Data Types](#part0015.xhtml)
> 
> [Floating-Point Data Types](#part0016.xhtml)
> 
> [Logical (Boolean) Data Type](#part0017.xhtml)
> 
> [Literals of Primitive Types](#part0018.xhtml)
> 
> [Literal Formats for Integers](#part0019.xhtml)
> 
> [Literal Formats for Integers - Example](#part0020.xhtml)
> 
> [Literal Formats for Floating-Point](#part0021.xhtml)
> 
> [Literal Formats for Floating-Point - Example](#part0022.xhtml)
> 
> [Literal Formats for Characters](#part0023.xhtml)
> 
> [Literal Formats for Character - Example](#part0024.xhtml)

Conclusion:

*   Java supports 8 primitive data types: byte, short, int, long, char, float, double, boolean.
*   "byte", "short", "int" and "long" can be used to represent signed integers in different ranges.
*   Default data type is "int" for integer literals.
*   Default data type is "double" for floating-point literals.
*   Hex floating-point literals can be used to represent a particular floating-point value accurately.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Data Types Supported in Java

This section provides a list of data types supported in Java: 8 primitive data types and 5 reference data types.

What are data types supported in Java? The following table lists all data types supported in Java and shows how they related to each other:

```
 Data Types
|
|- Primitive Types
|  |
|  |- Numeric Types
|  |  |
|  |  |- Integral Types
|  |  |  |- byte
|  |  |  |- short
|  |  |  |- int
|  |  |  |- long
|  |  |  |- char
|  |  |
|  |  |- Floating Point Types
|  |     |- float
|  |     |- double
|  |
|  |- boolean
|
|- Reference Types
   |...
```

Primitive types will be discussed in this chapter. Reference types will be discussed in other chapters in this book.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Integer Data Types

This section describes value ranges and storage space sizes of integer data types: byte, short, int, long and char.

Java supports 5 integer data types: byte, short, int, long and char.

From the data value point of view, each integer data type can represent the following integer numbers:

*   byte - Supports signed integer numbers in range from -128 to 127 inclusively.
*   short - Supports signed integer numbers in range from -32768 to 32767 inclusively.
*   int - Supports signed integer numbers in range from -2147483648 to 2147483647 inclusively.
*   long - Supports signed integer numbers in range from -9223372036854775808 to 9223372036854775807 inclusively.
*   char - Supports unsigned integer numbers in range from 0 to 65535 inclusively.

From the data storage point of view, each integer data type is stored its values differently:

*   byte - Stores its value in a 8-bit (1-byte) space with the 1st bit representing the sign and the remaining 7 bits representing the integer value in a binary format.
*   short - Stores its value in a 16-bit (2-byte) space with the 1st bit representing the sign and the remaining 15 bits representing the integer value in a binary format.
*   int - Stores its value in a 32-bit (4-byte) space with the 1st bit representing the sign and the remaining 31 bits representing the integer value in a binary format.
*   long - Stores its value in a 64-bit (8-byte) space with the 1st bit representing the sign and the remaining 63 bits representing the integer value in a binary format.
*   char - Stores its value in a 16-bit (2-byte) space with all 16 bits representing the integer value in a binary format.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Floating-Point Data Types

This section describes value ranges and storage space sizes of floating-point data types: float and double.

Java supports 2 floating-point data types: byte, float and double.

From the data value point of view, each floating-point data type can represent the following real number values:

*   float - Supports signed real numbers in range from -10**38 to 10**38 approximately with a 7 significant decimal digits precision roughly.
*   double - Supports signed real numbers in range from -10**308 to 10**308 approximately with a 15 significant decimal digits precision roughly.

From the data storage point of view, each floating-point data type is stored its values differently:

*   float - Stores its value in a 32-bit (4-byte) space with: 1 bit for the sign, 8 bits for the exponent component and 23 bits for the fraction component, represented in a binary format described in the IEEE 754 standard.
*   double - Stores its value in a 64-bit (8-byte) space with: 1 bit for the sign, 11 bits for the exponent component and 52 bits for the fraction component, represented in a binary format described in the IEEE 754 standard.

For more information, read the 'IEEE 754 Standards - "float" and "double"' tutorial from my "C# Tutorials - Herong's Tutorial Examples" book at [herongyang.com/C-Sharp/Floating-Point-Data-Type-IEEE-754.html](https://www.herongyang.com/C-Sharp/Floating-Point-Data-Type-IEEE-754.html).

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Logical (Boolean) Data Type

This section describes value range and storage space size of logical data type: boolean.

Java supports 1 logical data types: boolean.

From the data value point of view, logical data type, boolean, represents two values: true and false.

I am not sure about the data storage size of a boolean value. It could be 8 bits (1 byte).

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literals of Primitive Types

This section describes how to use literals to represent primitive data values in Java source code. Examples are: 911, 0x38fL, '\n', 3.14F, 1e137, 0x1p3, true, etc.

**What is a literal?** A literal is a string representation of a data value in a Java source code.

The following list summarizes how a data value of different primitive type can be represented in literals.

*   byte literal - No supported.
*   short literal - No supported.
*   int literal - Supported in 4 formats: decimal, hex, octal and binary. Examples are: 911, 0x38f, 0177, and 0b1110001111.
*   long literal - Supported in 4 formats: decimal, hex, octal and binary. Examples are: 911L, 0x38fL, 0177L, and 0b1110001111L.
*   char literal - Supported using quoted ASCII characters or escape sequences. Examples are: 'x', '\'', '\n', '\177', and '\u03a9'.
*   float literal - Supported in 2 formats: decimal and hex. Examples are: 1e1F, 2.F, .3F, 0F, 3.14F, 0x1p3F, and 6.022137e23F
*   double literal - Supported in 2 formats: decimal and hex. Examples are: 1e1, 2., .3, 0.0, 3.14, 1e137, 0x1p3 and 1e-9D,
*   boolean literal - Supported in 2 values: true and false.

Some interesting features supported in Java on primitive type literals:

*   Underscores (_) can be used as separators to put digits into groups in integer literals and floating-point literals. Examples are: 0xffff_ffff, 0377_7777_7777, 0b1111_1111_1111_1111_1111_1111_1111_1111, and 911_911_911_911.99999_9\. This feature does help to improve the readability of literals with many digits.
*   A single leading zero (0) is used as an indicator for octal integer literals. Examples are: 0177 and 0177L. This is inconsistent with hex integer literals, which requires 2 leading characters (0x) as the indicator. This feature may cause confusion because human read 0177 as a decimal value of 177, not a, octal value of 177, by ignoring the leading 0.
*   Floating-point literals can represented in hexadecimal format. Examples are: 0x1p3 is a floating-point literal in hexadecimal format for 8.0 in "double" data type. This is very nice feature introduced in JDK 5 to allow precise and predictable specification of particular floating-point values.
*   The default data type for integer literals is "int" if no suffix is used. If integer literal needs to be treated as "long" data type, suffix "L" or "l" must be used. This feature should not be a surprise to most developers.
*   The default data type for floating-point literals is "double" if no suffix is used. If floating-point literal needs to be treated as "float" data type, suffix "F" or "f" must be used. This feature may be a surprise to many developers.

More syntax rules and examples of primitive type literals are provides in other sections of this chapter.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literal Formats for Integers

This section describes 4 literal formats for integer values: decimal, hex, octal and binary integer literals. The default integer literal data type is 'int'.

Java supports literals for 2 integer data types in 4 formats described below:

1\. Decimal Integer Literal - Basic rules on decimal integer literals:

*   A sequence of decimal digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9, with no leading 0s can be used to represent a positive integer values in "int" data type. Examples are: 911 and 1024.
*   To specify values in "long" data type, suffix L or l can be added. Examples are: 911L and 1024l.
*   To increase readability, _ can be used as group separators. Examples are: 9_11L and 1_024.

2\. Hex Integer Literal - Basic rules on hex integer literals:

*   A sequence of hex digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, a, B, b, C, c, D, d, E, e, F and f, with a prefix of 0x or 0X can be used to represent an integer values in "int" data type. Examples are: 0x38F and 0X400.
*   To specify values in "long" data type, suffix L or l can be added. Examples are: 0x38FL and 0X400l.
*   To increase readability, _ can be used as group separators. Examples are: 0xDada_Cafe and 0X400_400L.
*   If the first bit of a 32-bit "int" or the 64-bit "long" literal is set to 1, it will be evaluated as a negative integer. Examples are: 0x8000_0000 and 0x8000_0000_0000_0000L.

3\. Octal Integer Literal - Basic rules on octal integer literals:

*   A sequence of octal digits: 0, 1, 2, 3, 4, 5, 6, and 7, with a prefix of 0 can be used to represent an integer values in "int" data type. Examples are: 01617 and 02000.
*   To specify values in "long" data type, suffix L or l can be added. Examples are: 01617L and 02000l.
*   To increase readability, _ can be used as group separators. Examples are: 033_266_545_376 and 02000_2000L.
*   If the first bit of a 32-bit "int" or the 64-bit "long" literal is set to 1, it will be evaluated as a negative integer. Example is: 020000000000.

4\. Binary Integer Literal - Basic rules on binary integer literals:

*   A sequence of octal digits: 0, and 1, with a prefix of 0b or 0B can be used to represent an integer values in "int" data type. Examples are: 0b1110001111 and 0B10000000000.
*   To specify values in "long" data type, suffix L or l can be added. Examples are: 0b1110001111L and 0B10000000000l.
*   To increase readability, _ can be used as group separators. Examples are: 0b11_1000_1111L and 0B10_000_000_000.
*   If the first bit of a 32-bit "int" or the 64-bit "long" literal is set to 1, it will be evaluated as a negative integer. Example is: 0b1000_0000_0000_0000_0000_0000_0000_0000.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literal Formats for Integers - Example

This section provides a tutorial example on how to use integer literals in 4 formats: decimal, hex, octal and binary.

Now let's see a tutorial program example on integer literals in decimal, hex, octal and binary formats:

```
 /* IntegerLiteral.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */

class IntegerLiteral {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;
      o.println("Decimal Integer Literals:");
      o.println("   int value:              911  = "+911);
      o.println("   int high:        2147483647  = "+2147483647);
      o.println("   long value:      2147483648L = "+2147483648L);
      o.println("   Using _:      2_147_483_648L = "+2_147_483_648L);

      o.println();
      o.println("Hex Integer Literals:");
      o.println("   Hex format:           0x38F  = "+0x38F);
      o.println("   Leading 0:       0x0000038F  = "+0x0000038F);
      o.println("   int max value:   0x7FFFFFFF  = "+0x7FFFFFFF);
      o.println("   long value:      0x7FFFFFFFL = "+0x7FFFFFFFL);
      o.println("   int min value:   0x80000000  = "+0x80000000);
      o.println("   long value:      0x80000000L = "+0x80000000L);
      o.println("   int -1 value:    0xFFFFFFFF  = "+0xFFFFFFFF);
      o.println("   long value:      0xFFFFFFFFL = "+0xFFFFFFFFL);
      o.println("   Using _:        0xDead_Deed  = "+0xDead_Deed);
      o.println("   long value:     0xDead_DeedL = "+0xDead_DeedL);

      o.println();
      o.println("Octal Integer Literals:");
      o.println("   Octal format:         01617  = "+01617);
      o.println("   int max value: 017777777777  = "+017777777777);
      o.println("   long value:    017777777777L = "+017777777777L);
      o.println("   int min value: 020000000000  = "+020000000000);
      o.println("   long value:    020000000000L = "+020000000000L);
      o.println("   Using _:     0200_0000_0000  = "+0200_0000_0000);
      o.println("   long octal:  0200_0000_0000L = "+0200_0000_0000L);

      o.println();
      o.println("Binary Integer Literals:");
      o.println("   Octal format:  0b1110001111  = "+0b1110001111);
      o.println("   int min value:"
         +" 0b1000_0000_0000_0000_0000_0000_0000_0000  = "
         +0b1000_0000_0000_0000_0000_0000_0000_0000);
   }
}
```

Compile this example program in a command window and run it:

```
 herong> javac IntegerLiteral.java

herong> java IntegerLiteral

Decimal Integer Literals:
   int value:              911  = 911
   int high:        2147483647  = 2147483647
   long value:      2147483648L = 2147483648
   Using _:      2_147_483_648L = 2147483648

Hex Integer Literals:
   Hex format:           0x38F  = 911
   Leading 0:       0x0000038F  = 911
   int max value:   0x7FFFFFFF  = 2147483647
   long value:      0x7FFFFFFFL = 2147483647
   int min value:   0x80000000  = -2147483648
   long value:      0x80000000L = 2147483648
   int -1 value:    0xFFFFFFFF  = -1
   long value:      0xFFFFFFFFL = 4294967295
   Using _:        0xDead_Deed  = -559030547
   long value:     0xDead_DeedL = 3735936749

Octal Integer Literals:
   Octal format:         01617  = 911
   int max value: 017777777777  = 2147483647
   long value:    017777777777L = 2147483647
   int min value: 020000000000  = -2147483648
   long value:    020000000000L = 2147483648
   Using _:     0200_0000_0000  = -2147483648
   long octal:  0200_0000_0000L = 2147483648

Binary Integer Literals:
   Octal format:  0b1110001111  = 911
   int min value: 0b1000_0000_0000_0000_0000_0000_0000_0000
      = -2147483648
```

Hope you know how to use integer literals properly now.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literal Formats for Floating-Point

This section describes 2 literal formats for floating-point values: decimal and hex floating-point literals. The default floating-point literal data type is 'double'.

Java supports literals for 2 floating-point data types in 2 formats described below:

1\. Decimal Floating-Point Literal - Basic rules on decimal floating-point literals:

*   A floating-point value in "double" data type can be represented 2 parts: a base part and an optional exponent part.
*   The base part consists of an integer part, a decimal point and a fractional part. Examples are: 365.242196, 3.14159 and 0.000000001.
*   The exponent part is a sequence of decimal digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9 with a leading sign + or - and a prefix of e or E. Examples are: 3.65242196e2, 3.14159e0 and 1.0e-9.
*   To specify values in "float" data type, suffix F or f can be added. Examples are: 3.65242196e2F, 3.14159e0F and 1.0e-9F.
*   To increase readability, _ can be used as group separators. Examples are: 3.652_421_96e2F and 3.141_59e0F.

2\. Hex Floating-Point Literal - Basic rules on hex floating-point literals:

*   A floating-point value in "double" data type can be represented 2 parts: a base part and an exponent part.
*   The base part consists of an integer part, a decimal point, a fractional part and a prefix of 0x or 0X. The base part should be evaluated as a hexadecimal number: each digit in the integer part is evaluated 16 times more than the next digit on the decimal point side. each digit in the fractional part is evaluated 16 times less than the next digit on the decimal point side. For example: 0x123.456 should be evaluated as 1*16*16 + 2*16 + 3 + 4/16 + 5/16/16 + 6/16/16.
*   The exponent part is a sequence of decimal digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9 with a leading sign + or - and a prefix of p or P. The exponent part is evaluated with a base of 2, not 10\. For example: 0x1p4 should be evaluated as 1*2*2*2*2.
*   To specify values in "float" data type, suffix F or f can be added. Examples are: 0x123.456p0F and 0x1.23456p8F.
*   To increase readability, _ can be used as group separators. Examples are: 0x12_345.6p-8F and 0x1.23_456p8F.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literal Formats for Floating-Point - Example

This section provides a tutorial example on how to use floating-point literals in 2 formats: decimal and hex.

Now let's see a tutorial program example on floating-point literals in decimal and hex formats:

```
 /* FloatingPointLiteral.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */

class FloatingPointLiteral {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;
      o.println("Decimal Floating-Point Literals:");
      o.println("   Base part:     365.242196     = "+365.242196);
      o.println("   With exponent: 3.65242196e2   = "+3.65242196e2);
      o.println("   Negative exponent:    1.0e-9  = "+1.0e-9);
      o.println("   float type:           1.0e-9F = "+1.0e-9F);
      o.println("   Using _:     3.65_242_196e2   = "+3.65_242_196e2);

      o.println();
      o.println("Hex Floating-Point Literals:");
      o.println("   1:                     0x1.0p0  = "+0x1.0p0);
      o.println("   16:                   0x10.0p0  = "+0x10.0p0);
      o.println("   16*16:                0x10.0p0  = "+0x10.0p0);
      o.println("   1/16:                  0x0.1p0  = "+0x0.1p0);
      o.println("   1/16/16:               0x0.01p0 = "+0x0.01p0);
      o.println("   With exponent:     0x1.23456p8  = "+0x1.23456p8);
      o.println("   Negative exponent: 0x12345.6p-8 = "+0x12345.6p-8);
      o.println("   float type:    0x800000.0p0F = "+0x8000000.0p0F);
      o.println("   Using _:      0x80_0000.0p0F = "+0x80_00000.0p0F);
   }
}
```

Compile this example program in a command window and run it:

```
 herong> javac FloatingPointLiteral.java

herong> java FloatingPointLiteral

Decimal Floating-Point Literals:
   Base part:     365.242196     = 365.242196
   With exponent: 3.65242196e2   = 365.242196
   Negative exponent:    1.0e-9  = 1.0E-9
   float type:           1.0e-9F = 1.0E-9
   Using _:     3.65_242_196e2   = 365.242196

Hex Floating-Point Literals:
   1:                     0x1.0p0  = 1.0
   16:                   0x10.0p0  = 16.0
   16*16:                0x10.0p0  = 16.0
   1/16:                  0x0.1p0  = 0.0625
   1/16/16:               0x0.01p0 = 0.00390625
   With exponent:     0x1.23456p8  = 291.27099609375
   Negative exponent: 0x12345.6p-8 = 291.27099609375
   float type:    0x800000.0p0F = 1.34217728E8
   Using _:      0x80_0000.0p0F = 1.34217728E8
```

Hope you know how to use floating-point literals properly now.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literal Formats for Characters

This section describes literal formats for character values of char data type: single characters or escape sequences enclosed in single quotes.

Java supports literals for the character data type, char, in several formats described below

Character Literal - Basic rules on character literals:

*   A character value in "char" data type can be represented as a single character enclosed in single quotes, like 'A', '1', ' ' and '"'.
*   Special characters ' and \ must be escaped with \, like '\'' and '\\'.
*   Control characters must be entered as escape sequences, like '\t', '\n' and '\r'.
*   Double-byte Unicode characters can be entered as Unicode sequences, like '\u0041' and '\u03C9'.
*   Decimal sequences can also be used, like '\101' and '\969'.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Primitive Data Types and Literals](#part0013.xhtml)

∟Literal Formats for Character - Example

This section provides a tutorial example on how to use character literals in different formats: single characters or escape sequences enclosed in single quotes.

Now let's see a tutorial program example on character literals in different formats:

```
 /* CharacterLiteral.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */

class CharacterLiteral {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;
      o.println("Character Literals:");
      o.println("   ASCII char:     'A'       = "+'A');
      o.println("   Control char:   '\\n'      = "+'\n');
      o.println("   Special char:   '\\\\'      = "+'\\');
      o.println("   Unicode char:   '\\u0041'  = "+'\u0041');
      o.println("   Decimal code:   '\\101'    = "+'\101');
   }
}
```

Compile this example program in a command window and run it:

```
 herong> javac CharacterLiteral.java

herong> java CharacterLiteral

Character Literals:
   ASCII char:     'A'       = A
   Control char:   '\n'      =

   Special char:   '\\'      = \
   Unicode char:   '\u0041'  = A
   Decimal code:   '\101'    = A
```

Hope you know how to use character literals properly now.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Control Flow Statements

This chapter provides tutorial notes and Control Flow Statements. Topics include decision-making statements: 'if' and 'switch' statements; looping statements: 'for', 'while' and 'do' statements; branching statements: 'break', 'continue', and 'return' statements.

> [What Is Control Flow Statement](#part0026.xhtml)
> 
> ["if-then" Statements](#part0027.xhtml)
> 
> ["if-then-else" Statements](#part0028.xhtml)
> 
> [Nested "if-then-else" Statements](#part0029.xhtml)
> 
> ["switch" Statements](#part0030.xhtml)
> 
> [Fall-Through Behavior of "switch" Statements](#part0031.xhtml)
> 
> [Basic "for" Statements](#part0032.xhtml)
> 
> [Enhanced "for" Statements](#part0033.xhtml)
> 
> ["while" Statements](#part0034.xhtml)
> 
> ["do" Statements](#part0035.xhtml)
> 
> ["break" Statements](#part0036.xhtml)
> 
> [Labeled "break" Statements](#part0037.xhtml)
> 
> ["continue" Statements](#part0038.xhtml)
> 
> [Labeled "continue" Statements](#part0039.xhtml)

Conclusion:

*   A Control Flow Statement is a statement that changes the default flow of execution, which run statements one by one sequentially.
*   An "if-then" statement is a decision-making statement that executes the contained sub-statement only when the given "boolean" expression is "true".
*   An "if-then-else" statement is a decision-making statement that executes only the first contained sub-statement when the given "boolean" expression is "true". Otherwise it executes only the second contained sub-statement.
*   "if-then-else" statements can be nested as "if ... else if ... else if ... ... ... else".
*   A "switch" statement is a decision-making statement that executes a portion of the contained statement block by passing control to a sub-statement based on label matching.
*   A basic "for" statement is a looping statement that executes the contained statement repeatedly with an initial logic, a looping condition, and an update logic.
*   An enhanced "for" statement is a looping statement that executes the contained statement repeatedly for each element in a given list.
*   A "while" statement is a looping statement that executes the contained statement repeatedly while a given condition is true.
*   A "do" statement is a looping statement that executes the contained statement immediately, then repeat it while a given condition is true.
*   A non-labeled "break" statement is a branching statement that transfers the control to the end of the immediate enclosing "switch", "while", "do", or "for" statement.
*   A labeled "break" statement is a branching statement that transfers the control to the end of the labeled enclosing block statement.
*   A non-labeled "continue" statement is a branching statement that transfers the control to the end of the immediate enclosing loop block and continues the next iteration of the loop.
*   A labeled "continue" statement is a branching statement that transfers the control to the end of the labeled enclosing loop block and continues the next iteration of the labeled loop.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟What Is Control Flow Statement

This section describes Control Flow Statements, which are statements that change the default flow of execution.

**What Is Control Flow Statement?** - A Control Flow Statement is a statement that changes the default flow of execution, which run statements one by one sequentially.

Control flow statements can be grouped into 3 categories:

*   Decision-Making Statements - A control-flow statement that transfers control to one of several statements based on the result of a condition logic. "if" statements, and "switch" statements are decision-making statements.
*   Looping Statements - A control-flow statement that repeats a statement multiple times based on a condition logic to stop the looping. "for" statements, "while" statements and "do" statements are looping statements.
*   Branching Statements - A control-flow statement that transfers control to a statement different than the next statement. "break" statements, "continue" statements, and "return" statements are branching statements.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"if-then" Statements

This section describes 'if-then' statement, which is a decision-making statement that executes contained sub-statements only when the given 'boolean' expression is 'true'.

"if" statements have 2 forms: "if-then" statements and "if-then-else" statements. Let's look at "if-then" statements in this tutorial first.

**What Is "if-then" Statement?** - An "if-then" statement is a decision-making statement that executes the contained sub-statement only when the given "boolean" expression is "true".

Here is the syntax for an "if-then" statement. Note that "then" is not used a keyword used in the statement at all.

```
 if (condition_expression) contained_statement
```

The contained sub-statement can be a simple single statement, or a complex statement block. Here is a sample program that shows you how to use "if-then" statements:

```
 /* IfThenStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class IfThenStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      out.println("\"if-then\" statement containing a single statement:");
      boolean isNewYear = true;
      if (isNewYear) out.println("   Happy New Year!");

      out.println("\"if-then\" statement containing a statement block:");
      boolean hasError = true;
      if (hasError) {
         out.println("   Open the log file.");
         out.println("   Write an error message.");
         out.println("   Close the log file.");
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java IfElseStatementTest.java

"if-then" statement containing a single statement:
   Happy New Year!
"if-then" statement containing a statement block:
   Open the log file.
   Write an error message.
   Close the log file.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"if-then-else" Statements

This section describes 'if-then-else' statements, which is a decision-making statement that executes only one of two its containing block based on the given 'boolean' expression.

**What Is "if-then-else" Statement?** - An "if-then-else" statement is a decision-making statement that executes only the first contained sub-statement when the given "boolean" expression is "true". Otherwise it executes only the second contained sub-statement.

Here is the syntax for an "if-then-else" statement. Note that "then" is not used a keyword used in the statement at all.

```
 if (condition_expression) first_contained_statement
else second_contained_statement
```

The contained sub-statement can be a simple single statement, or a complex statement block. Here is a sample program that shows you how to use "if-then-else" statements:

```
 /* IfThenElseStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.time.LocalTime;
class IfThenElseStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      LocalTime now = LocalTime.now();
      int hour = now.getHour(); // from 0 to 23

      out.println("\"if-then-else\" statement with 2 statement blocks:");
      if (hour<12) {
         out.println("   Good morning!");
         out.println("   Current time is "+now);
      } else {
         out.println("   How are you?");
         out.println("   Current time is "+now);
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java IfElseStatementTest.java

"if-then-else" statement with 2 statement blocks:
   Good morning!
   Current time is 09:36:47.356223
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟Nested "if-then-else" Statements

This section describes nested 'if-then-else' statements, where an 'if-then-else' statement contains another 'if-then-else' statement.

In certain situations, the second contained sub-statement of an "if-then-else" statement needs to be another "if-then-else" statement. The result is a nested "if-then-else" statement.

Some times, you may have many "if-then-else" statements nested. Here is an example of 5 "if-then-else" statements nested together.

```
 if (...) contained_statement // 1st "if" statement
else if (...) contained_statement // 2st "if" statement
     else if (...) contained_statement // 3rd "if" statement
          else if (...) contained_statement // 4th "if" statement
               else if (...) contained_statement // 5th "if" statement
                    else contained_statement
```

Note that a nested "if-then-else" statement can be written without indentations to indicate its nesting levels. But you need to remember that it is still a statement of 5 "if-then-else" statements nested together. It is not a single "if" statement with multiple contained sub-statements, which is not supported in Java.

```
 if (...) contained_statement      // 1st "if" statement
else if (...) contained_statement // 2st "if" statement
else if (...) contained_statement // 3rd "if" statement
else if (...) contained_statement // 4th "if" statement
else if (...) contained_statement // 5th "if" statement
else contained_statement
```

The above statement is actually equivalent to the following from syntax structure point of view.

```
 if (...) contained_statement      // 1st "if" statement
else { if (...) contained_statement // 2st "if" statement
else { if (...) contained_statement // 3rd "if" statement
else { if (...) contained_statement // 4th "if" statement
else { if (...) contained_statement // 5th "if" statement
else contained_statement } } } }
```

Here is a sample program that shows you how to use nested "if-then-else" statements:

```
 /* NestedIfThenElseStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.time.LocalTime;
class NestedIfThenElseStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      LocalTime now = LocalTime.now();
      int hour = now.getHour(); // from 0 to 23

      out.println("5 \"if-then-else\" statements nested together:");
      if (hour >= 6 && hour < 12)
         out.println("   Good morning!");
      else if (hour >= 12 && hour < 18)
              out.println("   Good afternoon!");
           else if (hour >= 18 && hour < 22)
                   out.println("   Good evening!");
                else if (hour >= 22 && hour < 24)
                        out.println("   Good night!");
                     else if (hour >= 0 && hour < 6)
                             out.println("   Why are you not sleeping?");
                          else
                             out.println("   Something wrong with clock!");
      out.println("   Current time is "+now);
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java NestedIfThenElseStatementTest.java

5 "if-then-else" statements nested together:
   Good afternoon!
   Current time is 14:29:50.479207
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"switch" Statements

This section describes 'switch' statement, which is a decision-making statement that executes a portion of the contained statement block by passing control to a sub-statement based on label matching.

**What Is "switch" Statement?** - A "switch" statement is a decision-making statement that executes a portion of the contained statement block. The executed portion starts from a statement whose label matches a given expression value and ends with the last statement of the block.

Here is the syntax for a "switch" statement.

```
 switch (test_expression) {
  case label_constant:
     sub-statement
     sub-statement
     ...
  case label_constant:
     sub-statement
     sub-statement
     ...
  default:
     sub-statement
     sub-statement
     ...
}
```

When a "switch" statement is executed, the test_expression is evaluated first. The resulting value is then compared with all label_constants. When a match is found, control is passed to the matching label. when no match is found, control is passed to the "default" label (if provided).

Here is a sample program that shows you how to use nested "if-then-else" statements:

```
 /* SwitchStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.time.LocalTime;
class SwitchStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      LocalTime now = LocalTime.now();
      int hour = now.getHour(); // from 0 to 23

      out.println("\"switch\" statement:");
      int workingHours = 8;
      switch (hour) {
        case  9: workingHours--; // starts here when hour ==  9
        case 10: workingHours--; // starts here when hour == 10
        case 11: workingHours--; // starts here when hour == 11
        case 12: workingHours--; // starts here when hour == 12
        case 13: workingHours--; // starts here when hour == 13
        case 14: workingHours--; // starts here when hour == 14
        case 15: workingHours--; // starts here when hour == 15
        case 16: workingHours--; // starts here when hour == 16
      }
      out.println("   Worked "+workingHours+" full hours with no breaks!");
      out.println("   Current time is "+now);
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java SwitchStatementTest.java

"switch" statement:
   Worked 3 full hours with no breaks!
   Current time is 12:15:11.702155
```

As you can see from the output, the program executes the "switch" statement as below:

*   Evaluates the test expression "hour" to value "12".
*   Passes the control to the statement labeled with "case 12" in the contained statement block.
*   Runs all statements from "case 12" to the end of the block, that decrements "workingHours" 5 times.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟Fall-Through Behavior of "switch" Statements

This section provides a tutorial example that show the 'fall-through' behavior of 'switch' statements.

From the previous tutorial, we learned that the execution of a "switch" statements starts from the label in the contained statement block that matches the value of a given test expression. The execution continues with all remaining sub-statements in the block, including "case" or "default" labels.

This behavior is called "fall-through" execution. If you do not want the execution falling through labels, you need to use "break" statements to jump out of the block.

Here is nice example from the Java language specification that demonstrate the "fall-through" behavior:

```
 /* TooMany.java
 * From "The Java Language Specification"
 */
class TooMany {
  static void howMany(int k) {
    switch (k) {
      case 1: System.out.print("one ");
      case 2: System.out.print("too ");
      case 3: System.out.println("many");
    }
  }
  public static void main(String[] args) {
    howMany(3);
    howMany(2);
    howMany(1);
  }
}
```

The output confirms the fall-through behavior:

```
 herong> java TooMany.java

many
too many
one too many
```

Here is the version that stops the fall-through behavior with "break" statements:

```
 /* TwoMany.java
 * From "The Java Language Specification"
 */
class TwoMany {
  static void howMany(int k) {
    switch (k) {
      case 1: System.out.println("one");
        break;  // exit the switch
      case 2: System.out.println("two");
        break;  // exit the switch
      case 3: System.out.println("many");
        break;  // not needed, but good style
    }
  }
  public static void main(String[] args) {
    howMany(1);
    howMany(2);
    howMany(3);
  }
}
```

Here is the output:

```
 herong> java TwoMany.java

one
two
many
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟Basic "for" Statements

This section describes basic 'for' statement, which is a looping statement that executes the contained statement repeatedly with an initial logic, a looping condition, and an update logic.

"for" statements have 2 forms: basic "for" statements and enhanced "for" statements. Let's look at basic "for" statements in this tutorial first.

**What Is Basic "for" Statement?** - A basic "for" statement is a looping statement that executes the contained statement repeatedly with an initial logic, a looping condition, and an update logic.

Here is the syntax for a basic "for" statement.

```
 for (initial_logic; looping_condition; update_logic) contained_statement
```

When a basic "for" statement is executed, the flow of control can be described as:

Step 1\. Run "initial_logic".

Step 2\. Evaluate "looping_condition". If result is "false", end the "for" statement.

Step 3\. Run "contained_statement".

Step 4\. Run "update_logic".

Step 5\. Go back to Step 2.

The contained statement can be empty, a simple single statement, or a complex statement block. Here is a sample program that shows you how to use basic "for" statements:

```
 /* BasicForStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class BasicForStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      int max = 20;
      int sum = 0;

      out.println("\"for\" statement with no contained statement:");
      for (int i = 0; i < max; sum += ++i);
      out.println("   Sum of 1 to 20: "+sum);
      sum = 0;

      out.println("\"for\" statement with a contained statement:");
      for (int i = 0; i < max; i++) sum += i;
      out.println("   Sum of 0 to 19: "+sum);

      out.println("\"for\" statement with a contained statement block:");
      for (int i = 3; i < max; i++) {
         boolean isPrime = true;
         for (int j = 2;  j <= i/2; j++) {
            isPrime = i%j > 0;
            if (!isPrime) break;
         }
         if (isPrime) out.println("   "+i+" is a prime number.");
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java BasicForStatementTest.java

"for" statement with no contained statement:
   Sum of 1 to 20: 210

"for" statement with a contained statement:
   Sum of 0 to 19: 190

"for" statement with a contained statement block:
   3 is a prime number.
   5 is a prime number.
   7 is a prime number.
   11 is a prime number.
   13 is a prime number.
   17 is a prime number.
   19 is a prime number.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟Enhanced "for" Statements

This section describes enhanced 'for' statement, which is a looping statement that executes the contained statement repeatedly for each element in a given list.

**What Is Enhanced "for" Statement?** - An enhanced "for" statement is a looping statement that executes the contained statement repeatedly for each element in a given list.

Here is the syntax for an enhanced "for" statement.

```
 for (type e: list) contained_statement
```

When an enhanced "for" statement is executed, the flow of control can be described as:

Step 1\. Declare a local variable "e".

Step 2\. Verify if the "list" has next element.

Step 3\. Assign the next element from the "list" to "e", if next element exists.

Step 4\. End the "for" statement, if there is no next element.

Step 5\. Run "contained_statement".

Step 6\. Go back to Step 2.

Note that the "list" can be an array object, or an "Iterable" object. Here is a sample program that shows you how to use enhanced "for" statements:

```
 /* EnhancedForStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class EnhancedForStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      int max = 20;
      int sum = 0;

      out.println("Enhanced \"for\" statement on an array object:");
      Integer[] arrayList = { 1, 2, 3, 4, 5, 6, 7, 8, 9,10,
                             11,12,13,14,15,16,17,18,19,20};
      for (Integer i :  arrayList) sum += i;
      out.println("   Sum of 1 to 20: "+sum);
      sum = 0;

      out.println("Enhanced \"for\" statement on an iterable object:");
      Iterable<Integer> iterableList = Arrays.<Integer>asList(arrayList);
      for (Integer i :  iterableList) sum += i;
      out.println("   Sum of 1 to 20: "+sum);
      sum = 0;
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java EnhancedForStatementTest.java

Enhanced "for" statement on an array object:
   Sum of 1 to 20: 210

Enhanced "for" statement on an iterable object:
   Sum of 1 to 20: 210
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"while" Statements

This section describes 'while' statement, which is a looping statement that executes the contained statement repeatedly while a given condition is true.

**What Is "while" Statement?** - A "while" statement is a looping statement that executes the contained statement repeatedly while a given condition is true.

Here is the syntax for a "while" statement.

```
 while (looping_condition) contained_statement
```

When a "while" statement is executed, the flow of control can be described as:

Step 1\. Evaluate "looping_condition". If result is "false", end the "while" statement.

Step 2\. Run "contained_statement".

Step 3\. Go back to Step 1.

The contained statement can be empty, a simple single statement, or a complex statement block. Here is a sample program that shows you how to use "while" statements:

```
 /* WhileStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class WhileStatementTest {
   private static int rank = 5;
   private static int downgrade() {
      rank--;
      System.out.println("   Rank downgraded to: "+rank);
      return rank;
   }

   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      out.println("\"while\" statement with no contained statement:");
      while (downgrade() > 0);

      int max = 20;
      int sum = 0;
      int i = 0;
      out.println("\"while\" statement with a contained statement:");
      while (i < max) sum += ++i;
      out.println("   Sum of 1 to 20: "+sum);

      boolean isPrime;
      i = 3;
      out.println("\"while\" statement with a contained statement block:");
      while (i < max) {
         isPrime = true;
         int j = 2;
         while (j < i) {
            isPrime = i%j > 0;
            if (!isPrime) break;
            j++;
         }
         if (isPrime) out.println("   "+i+" is a prime number.");
         i++;
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java WhileStatementTest.java

"while" statement with no contained statement:
   Rank downgraded to: 4
   Rank downgraded to: 3
   Rank downgraded to: 2
   Rank downgraded to: 1
   Rank downgraded to: 0

"while" statement with a contained statement:
   Sum of 1 to 20: 210

"while" statement with a contained statement block:
   3 is a prime number.
   5 is a prime number.
   7 is a prime number.
   11 is a prime number.
   13 is a prime number.
   17 is a prime number.
   19 is a prime number.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"do" Statements

This section describes 'do' statement, which is a looping statement that executes the contained statement immediately, then repeat it while a given condition is true.

**What Is "do" Statement?** - A "do" statement is a looping statement that executes the contained statement immediately, then repeat it while a given condition is true.

Here is the syntax for a "do" statement.

```
 do contained_statement while (looping_condition)
```

When a "do" statement is executed, the flow of control can be described as:

Step 1\. Run "contained_statement".

Step 2\. Evaluate "looping_condition". If result is "false", end the "while" statement.

Step 3\. Run "contained_statement".

Step 4\. Go back to Step 2.

The contained statement can be empty, a simple single statement, or a complex statement block. Here is a sample program that shows you how to use "do" statements:

```
 /* DoStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class DoStatementTest {
   private static int rank = 5;
   private static int downgrade() {
      rank--;
      System.out.println("   Rank downgraded to: "+rank);
      return rank;
   }

   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      out.println("\"do\" statement with no contained statement:");
      do ; while (downgrade() > 0);

      int max = 20;
      int sum = 0;
      int i = 0;
      out.println("\"do\" statement with a contained statement:");
      do sum += ++i; while (i < max);
      out.println("   Sum of 1 to 20: "+sum);

      boolean isPrime;
      i = 3;
      out.println("\"do\" statement with a contained statement block:");
      do {
         isPrime = true;
         int j = 2;
         do {
            isPrime = i%j > 0;
            if (!isPrime) break;
            j++;
         } while (j < i);
         if (isPrime) out.println("   "+i+" is a prime number.");
         i++;
      } while (i < max);
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java DoStatementTest.java

"do" statement with no contained statement:
   Rank downgraded to: 4
   Rank downgraded to: 3
   Rank downgraded to: 2
   Rank downgraded to: 1
   Rank downgraded to: 0

"do" statement with a contained statement:
   Sum of 1 to 20: 210

"do" statement with a contained statement block:
   3 is a prime number.
   5 is a prime number.
   7 is a prime number.
   11 is a prime number.
   13 is a prime number.
   17 is a prime number.
   19 is a prime number.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"break" Statements

This section describes 'break' statement, which is a branching statement that transfers the control to the end of the immediate enclosing 'switch', 'while', 'do', or 'for' statement.

"break" statements have 2 forms: non-labeled "break" statements and labeled "break" statements. Let's look at non-labeled "break" statements in this tutorial first.

**What Is Non-Labeled "break" Statement?** - A non-labeled "break" statement is a branching statement that transfers the control to the end of the immediate enclosing "switch", "while", "do", or "for" statement.

Here is the syntax for a non-labeled "break" statement.

```
 switch|while|do|for ... {
   ...
   break
   ...
}
// break continues here
```

Note that non-labeled "break" statements can not be used in statements other than "switch", "while", "do", or "for" statements.

Here is a sample program that shows you how to use non-labeled "break" statements:

```
 /* BreakStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class BreakStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      int max = 20;

      out.println("\"break\" statement in a single-level loop:");
      int sum = 0;
      int i = 1;
      while (true) { // loop level 1
         if (i > max ) break;
         sum += i;
         i++;
      } // break continues here
      out.println("   Sum of 1 to 20: "+sum);

      boolean isPrime;
      i = 3;
      out.println("\"break\" statement in a multi-level loop:");
      while (i < max) { // loop level 1
         isPrime = true;
         int j = 2;

         while (j < i) { // loop level 2
            isPrime = i%j > 0;
            if (!isPrime) break;
            j++;
         } // break continues here

         if (isPrime) out.println("   "+i+" is a prime number.");
         i++;
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java BreakStatementTest.java

"break" statement in a single-level loop:
   Sum of 1 to 20: 210

"break" statement in a multi-level loop:
   3 is a prime number.
   5 is a prime number.
   7 is a prime number.
   11 is a prime number.
   13 is a prime number.
   17 is a prime number.
   19 is a prime number.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟Labeled "break" Statements

This section describes labeled 'break' statement, which is a branching statement that transfers the control to the end of the labeled enclosing block statement.

**What Is Labeled "break" Statement?** - A labeled "break" statement is a branching statement that transfers the control to the end of the labeled enclosing block statement.

Here is the syntax for a labeled "break" statement.

```
 block_label : ... {
   ...
   {
      ...
      break block_label
      ...
   }
   ...
}
// break continue here
```

Labeled "break" statements extend usages of non-labeled "break" statements in 2 situations:

*   Break block statements other than "switch", "while", "do", or "for" statements.
*   Break a parent block statement of the immediate enclosing block statement.

Here is a sample program that shows you how to use labeled "break" statements:

```
 /* LabeledBreakStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class LabeledBreakStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      out.println("\"break\" statement in a dummy block:");
      blockDummy : {
         out.println("   One");

         if (true) break blockDummy;
         out.println("   Two");
      }
      out.println("   Three");

      out.println("\"break\" statement in an \"if\" block:");
      blockIf : if (true) {
         out.println("   Monday");

         if (true) break blockIf;
         out.println("   Tuesday");
      }
      out.println("   Wednesday");

      out.println("\"break\" statement in a two-level block:");
      boolean isPrime;
      int i = 3;
      int operations = 1;

      blockOuter: while (true) { // block level 1
         isPrime = true;
         int j = 2;

         blockInner : while (j < i) { // block level 2
            isPrime = i%j > 0;

            if (!isPrime) break blockInner;
            j++;

            if (operations > 100) break blockOuter;
            operations++;
         }

         if (isPrime) out.println("   "+i+" is a prime number.");
         i++;
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java LabeledBreakStatementTest.java

"break" statement in a dummy block:
   One
   Three

"break" statement in an "if" block:
   Monday
   Wednesday

"break" statement in a two-level block:
   3 is a prime number.
   5 is a prime number.
   7 is a prime number.
   11 is a prime number.
   13 is a prime number.
   17 is a prime number.
   19 is a prime number.
   23 is a prime number.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟"continue" Statements

This section describes non-labeled 'continue' statement, which is a branching statement that transfers the control to the end of the immediate enclosing loop block and continues the next iteration of the loop.

"continue" statements have 2 forms: non-labeled "continue" statements and labeled "continue" statements. Let's look at non-labeled "continue" statements in this tutorial first.

**What Is Non-Labeled "continue" Statement?** - A non-labeled "continue" statement is a branching statement that transfers the control to the end of the immediate enclosing loop block and continues the next iteration of the loop.

Here is the syntax for a non-labeled "continue" statement.

```
 while|do|for ... { // "continue" continues here
   ...
   continue
   ...
}
```

Note that non-labeled "continue" statements can not be used in statements other than "while", "do", or "for" statements.

Here is a sample program that shows you how to use non-labeled "continue" statements:

```
 /* ContinueStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.io.*;
import java.nio.file.*;
import java.time.*;
class ContinueStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      out.println("\"continue\" statement in a single-level loop:");
      long bytes = 0;
      int counts = 0;
      Path dir = FileSystems.getDefault().getPath(arg[0]);
      try {
         DirectoryStream<Path> stream = Files.newDirectoryStream(dir);

         for (Path path : stream) { // "continue" continues here
            File file = path.toFile();

            if (file.isDirectory()) continue;
            bytes += file.length();
            counts++;
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
      out.println("   # of files: "+counts);
      out.println("   # of bytes: "+bytes);

      out.println("\"continue\" statement in a two-level loop:");
      LocalDate now = LocalDate.now();
      int year = now.getYear();

      for (int y = year-5; y < year; y++) {

         counts = 0;
         LocalDate d = LocalDate.of(y, 1, 1);

         for ( ; d.getYear() == y; d = d.plusDays(1) ) { // continues here

            if (d.getDayOfWeek() != DayOfWeek.SUNDAY)  continue;
            counts++;
         }
         out.println("   "+counts+" Sundays in year "+y);
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java ContinueStatementTest.java .

"continue" statement in a single-level loop:
   # of files: 13
   # of bytes: 11827

"continue" statement in a two-level loop:
   52 Sundays in year 2015
   52 Sundays in year 2016
   53 Sundays in year 2017
   52 Sundays in year 2018
   52 Sundays in year 2019
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Control Flow Statements](#part0025.xhtml)

∟Labeled "continue" Statements

This section describes labeled 'continue' statement, which is a branching statement that transfers the control to the end of the labeled enclosing loop block and continues the next iteration of the labeled loop.

**What Is Labeled "continue" Statement?** - A labeled "continue" statement is a branching statement that transfers the control to the end of the labeled enclosing loop block and continues the next iteration of the labeled loop.

Here is the syntax for a labeled "continue" statement.

```
 loop_label : while|do|for ... { // "continue" continues here
   ...
   while|do|for ... {
      ...
      continue loop_label
      ...
   }
   ...
}
```

Labeled "continue" statements extend usages of non-labeled "continue" statements in 1 situation:

*   Continue the next iteration of a parent loop of the immediate enclosing loop.

Here is a sample program that shows you how to use labeled "continue" statements:

```
 /* LabeledContinueStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.io.*;
import java.nio.file.*;
import java.time.*;
class LabeledContinueStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      out.println("Labeled \"continue\" statement for outer loop:");
      loopOuter: for (int i = 3; i < 20; i++) {
         boolean isPrime = true;
         int j = 2;
         while (j < i) {
            isPrime = i%j > 0;
            if (!isPrime) continue loopOuter;
            j++;
         }
         out.println("   "+i+" is a prime number.");
      }
   }
}
```

If you compile and run the above program, you will see:

```
 herong> java LabeledContinueStatementTest.java

Labeled "continue" statement for outer loop:
   3 is a prime number.
   5 is a prime number.
   7 is a prime number.
   11 is a prime number.
   13 is a prime number.
   17 is a prime number.
   19 is a prime number.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Bits, Bytes, Bitwise and Shift Operations

This chapter provides tutorial notes and tutorial examples on bits, bytes and bitwise operations. Topics include bits and bytes as storage units; 'byte' data type and (byte) casting; bitwise operations; shift operations.

> [What Are Bits and Bytes](#part0041.xhtml)
> 
> ["byte" Data Type and Implicit Casting](#part0042.xhtml)
> 
> [Operations on "byte" Data Type Values](#part0043.xhtml)
> 
> [Bitwise Operations on "byte" Values](#part0044.xhtml)
> 
> [Bitwise Operations on "byte" Values - Example Program](#part0045.xhtml)
> 
> [Shift Operations - Left, Right or Unsigned Right](#part0046.xhtml)

Conclusion:

*   Bit is the smallest storage unit that can only store two possible values: 0 and 1.
*   Byte is a storage unit that holds 8 bits.
*   "byte" is a primitive data type in Java. A "byte" variable can hold an integer in the range of -128 to 127.
*   To assign values to "byte" variables, you need to cast original values to "byte" data type implicitly or explicitly (using "(byte)").
*   "byte" variables can participate any arithmetic and comparison operations. But their values will be converted to "int" data type before the operation.
*   Bitwise operations are defined for "int" data type, not for "byte".
*   Shift operations are defined for "int" data type, not for "byte".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)

∟What Are Bits and Bytes

This section describes bits and bytes as data storage units and as data types.

**Bit** - The smallest storage unit in the computer world. It can only hold two possible values: 0 and 1.

**Bit** - The smallest unit of measure of digital information size.

**Bit** - A single digit of a binary number. It can only have two possible values: 0 and 1.

**Byte** - A storage unit with 8 bits. A byte can hold 256 possible values.

**Byte** - A unit of measure of digital information size. 1 byte = 8 bits. For example, a Java source code file, Hello.java, has a size of 109 bytes.

**Byte** - A data type in many programming language. It can be used to store 256 possible integer values. In Java, 'byte' is a primitive data type that can store an integer value in the range of -128 and 127.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)

∟"byte" Data Type and Implicit Casting

This section provides a tutorial example on how 'byte' variables can be assigned with 'byte' values with implicit and explicit casting from other compatible types of values.

**byte** - A primitive data type in Java that can store 256 possible integer values from -128 to 127.

There is no explicit data literals for "byte" data type. If you want to assign values to "byte" data type variables, you can:

*   Use the generic integer "int" data literals.
*   Use type cast operation "(byte)" to convert from other types of values.
*   Use expressions that result in integer (int) values.

To verify how values can be assigned to "byte" data type variables, I wrote the following sample program, ByteValues.java:

```
 /* ByteValues.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class ByteValues {
   public static void main(String[] arg) {

// Good "byte" assignments
      byte b1, b2, b3, b4, b5, b6, b7, b8;
      b1 = 127; // "int" literal and implicit casting
      b2 = 0x0000007F; // "int" literal and implicit casting
      b3 = (byte) 127; // "int" literal and explicit casting
      b4 = (byte) 0x0000007F; // literal and explicit casting
      b5 = 254/2; // "int" expression and implicit casting
      b6 = 256127%256; // "int" expression and implicit casting
      b7 = (byte) 127.14157; // "float" literal and explicit casting
      b8 = (byte) 'A'; // "char" literal and explicit casting
      System.out.println("b1: "+b1);
      System.out.println("b2: "+b2);
      System.out.println("b3: "+b3);
      System.out.println("b4: "+b4);
      System.out.println("b5: "+b5);
      System.out.println("b6: "+b6);
      System.out.println("b7: "+b7);
      System.out.println("b8: "+b8);

// Bad "byte" assignments
      byte d1, d2, d3, d4, d5, d6;
//      d1 = 128; // out of range
//      d2 = -129; // out of range
//      d3 = (byte) (1==1); // type not compatible
//      d4 = (byte) "A"; // type not compatible
//      d5 = (byte) null; // type not compatible
//      d6 = (byte) new Date(); // type not compatible
   }
}
```

After executing this program, I got the following output:

```
 b1: 127
b2: 127
b3: 127
b4: 127
b5: 127
b6: 127
b7: 127
b8: 65
```

The output shows that:

*   Assignment operator performs implicit casting to convert the specified value to the same type as the target variable.
*   Converting other data type values to "byte" can be done by the explicit casting operator "(byte)".
*   "int", "float", and "char" are compatible with (can be casted to) "byte".

"ByteValues.java" also contains some hidden bad assignment expressions. If you un-comment those statement, you will get compilation errors.

Here are compilation errors from JDK 13 compiler:

```
 ByteValues.java:28: error: incompatible types: possible lossy conversion
from int to byte
      d1 = 128; // out of range
           ^
ByteValues.java:29: error: incompatible types: possible lossy conversion
from int to byte
      d2 = -129; // out of range
           ^
ByteValues.java:30: error: incompatible types: boolean cannot be converted
 to byte
      d3 = (byte) (1==1); // type not compatible
                  ^
ByteValues.java:31: error: incompatible types: String cannot be converted
 to byte
      d4 = (byte) "A"; // type not compatible
                  ^
ByteValues.java:32: error: incompatible types: <null> cannot be
converted to byte
      d5 = (byte) null; // type not compatible
                  ^
ByteValues.java:33: error: cannot find symbol
      d6 = (byte) new Date(); // type not compatible
                      ^
  symbol:   class Date
  location: class ByteValues
6 errors
```

Here are compilation errors from JDK 8 compiler:

```
 ByteValues.java:28: error: incompatible types:
   possible lossy conversion from int to byte
      d1 = 128; // out of range
           ^
ByteValues.java:29: error: incompatible types:
   possible lossy conversion from int to byte
      d2 = -129; // out of range
           ^
ByteValues.java:30: error: incompatible types:
   boolean cannot be converted to byte
      d3 = (byte) (1==1); // type not compatible
                  ^
ByteValues.java:31: error: incompatible types:
   String cannot be converted to byte
      d4 = (byte) "A"; // type not compatible
                  ^
ByteValues.java:32: error: incompatible types:
   <null> cannot be converted to byte
      d5 = (byte) null; // type not compatible
                  ^
ByteValues.java:33: error: cannot find symbol
      d6 = (byte) new Date(); // type not compatible
                      ^
  symbol:   class Date
  location: class ByteValues
6 errors
```

Here are compilation errors from JDK 7 compiler:

```
 ByteValues.java:28: possible loss of precision
found   : int
required: byte
      d1 = 128; // out of range
           ^
ByteValues.java:29: possible loss of precision
found   : int
required: byte
      d2 = -129; // out of range
            ^
ByteValues.java:30: inconvertible types
found   : boolean
required: byte
      d3 = (byte) (1==1); // type not compatible
                  ^
ByteValues.java:31: inconvertible types
found   : java.lang.String
required: byte
      d4 = (byte) "A"; // type not compatible
                  ^
ByteValues.java:32: inconvertible types
found   : <nulltype>
required: byte
      d5 = (byte) null; // type not compatible
                  ^
ByteValues.java:33: cannot find symbol
symbol  : class Date
location: class ByteValues
      d6 = (byte) new Date(); // type not compatible
                      ^
6 errors
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)

∟Operations on "byte" Data Type Values

This section provides a tutorial example on how 'byte' values are casted to 'int' values when they are involved in arithmetic, comparison and bitwise operations.

Actually, there is no operations defined in Java that works directly on "byte" data type values.

But "byte" data type values can participate all operations defined for integer values. More precisely:

*   When a "byte" value is involved in an arithmetic operation like +, -, *, /, or %, it will be casted to an "int" value before entering the operation.
*   When a "byte" value is involved in a comparison operation like ==, !=, >, <, >=, or <=, it will be casted to an "int" value before entering the operation.
*   When a "byte" value is involved in a bitwise operation like &, |, ^, or ~, it will be casted to an "int" value before entering the operation.
*   When a "byte" value is involved in a shift operation like <<, >>, or >>>, it will be casted to an "int" value before entering the operation.

To validate those rules mentioned above, I wrote the following sample program, ByteOperations.java:

```
 /* ByteOperations.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class ByteOperations {
   public static void main(String[] arg) {
      byte b1 = 127;
      int o1 = (b1+b1-0)*5/10; // arithmetic operations

      byte b2 = 0x0000007F;
      boolean o2 = b2 > b2 || b2 != b2 || b2 == b2; // comparisons

      byte b3 = (byte) 127;
      int o3 = b3 & 0x0000000F | 0x00000070; // bitwise operations

      byte b4 = (byte) 0x0000007F;
      int o4 = b4 >> 4 << 4; // shift operations

      System.out.println("o1: "+o1);
      System.out.println("o2: "+o2);
      System.out.println("o3: "+o3);
      System.out.println("o4: "+o4);
   }
}
```

After executing this program, I got this output with no surprises:

```
 o1: 127
o2: true
o3: 127
o4: 112
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)

∟Bitwise Operations on "byte" Values

This section describes 4 types of bitwise operations, 'And', 'Or', 'Exclusive Or', and 'Complement' that applies on 'byte' values indirectly through 'int' values.

**What is a bitwise operation?** A bitwise operation is an operation that requires the operand(s) to be represented in a binary format, and applies the operation one bit at a time.

Interestingly, Java defines bitwise operations on "int" data type values, not on "byte" data type values. So a bitwise operation requires that the involved "int" values to be represented into a 32-bit binary format. And the operation will be applied 1 bit at a time repeating 32 times.

Java defines 4 bitwise operations called: "And", "Or", "Exclusive Or", and "Complement"

1\. Bitwise operation "And" - "&": The bitwise "And" operation between two "int" values can be described as:

*   Representing two operands, two "int" values, into two 32-bit long input binary strings.
*   Combining those two input binary strings into one 32-bit long output binary string, such that the value of any bit in the output binary string is 1, if and only if both corresponding bits in the input binary strings are 1.
*   Converting the output binary string to an "int" value as the operation result.

The following diagram gives an example of "&" operations in 3 formats:

```
 Decimal        Hex          Binary
   858993459     33333333     00110011 00110011 00110011 00110011
& 1431655765   & 55555555   & 01010101 01010101 01010101 01010101
------------   ----------   -------------------------------------
=  286331153   = 11111111   = 00010001 00010001 00010001 00010001
```

2\. Bitwise operation "Or" - "|": The bitwise "Or" operation between two "int" values can be described as:

*   Representing two operands, two "int" values, into two 32-bit long input binary strings.
*   Combining those two input binary strings into one 32-bit long output binary string, such that the value of any bit in the output binary string is 0, if and only if both corresponding bits in the input binary strings are 0.
*   Converting the output binary string to an "int" value as the operation result.

The following diagram gives an example of "|" operations in 3 formats:

```
 Decimal        Hex          Binary
   858993459     33333333     00110011 00110011 00110011 00110011
| 1431655765   | 55555555   | 01010101 01010101 01010101 01010101
------------   ----------   -------------------------------------
= 2004318071   = 77777777   = 01110111 01110111 01110111 01110111
```

3\. Bitwise operation "Exclusive Or" - "^": The bitwise "Exclusive Or" operation between two "int" values can be described as:

*   Representing two operands, two "int" values, into two 32-bit long input binary strings.
*   Combining those two input binary strings into one 32-bit long output binary string, such that the value of any bit in the output binary string is 1, if and only if one of the corresponding bits in the input binary strings is 1.
*   Converting the output binary string to an "int" value as the operation result.

The following diagram gives an example of "^" operations in 3 formats:

```
 Decimal        Hex          Binary
   858993459     33333333     00110011 00110011 00110011 00110011
^ 1431655765   ^ 55555555   ^ 01010101 01010101 01010101 01010101
------------   ----------   -------------------------------------
= 1717986918   = 66666666   = 01100110 01100110 01100110 01100110
```

4\. Bitwise operation "Complement" - "~": The bitwise "Complement" operation on one "int" value can be described as:

*   Representing the only operand, one "int" value, into one 32-bit long input binary string.
*   Derive from the input binary string into one 32-bit long output binary string, such that the value of any bit in the output binary string is 1, if and only if the corresponding bit in the input binary string is 0.
*   Converting the output binary string to an "int" value as the operation result.

The following diagram gives an example of "~" operations in 3 formats:

```
 Decimal        Hex          Binary
~  858993459   ~ 33333333   ~ 00110011 00110011 00110011 00110011
------------   ----------   -------------------------------------
= 3233857728   = C0C0C0C0   = 11001100 11001100 11001100 11001100
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)

∟Bitwise Operations on "byte" Values - Example Program

This section provides a tutorial example on how 4 types of bitwise operations, 'And', 'Or', 'Exclusive Or', and 'Complement' works on 'int' values.

To verify those bitwise operation rules given in the previous section, I wrote the following test program, BitwiseOperations.java:

```
 /* BitwiseOperations.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class BitwiseOperations {
   public static void main(String[] arg) {
      int a = 858993459;  // binary: 00110011001100110011001100110011
      int b = 1431655765; // binary: 01010101010101010101010101010101

      int o1 = a & b; // bitwise "And"
      int o2 = a | b; // bitwise "Or"
      int o3 = a ^ b; // bitwise "Exclusive Or"
      int o4 = ~a;    // bitwise "Complement"

      System.out.println(" a: "+getBitString(a) +" = "+a);
      System.out.println(" b: "+getBitString(b) +" = "+b);
      System.out.println("o1: "+getBitString(o1) +" = "+o1);
      System.out.println("o2: "+getBitString(o2) +" = "+o2);
      System.out.println("o3: "+getBitString(o3) +" = "+o3);
      System.out.println("o4: "+getBitString(o4) +" = "+o4);
   }
   private static String getBitString(int x) {
      StringBuffer buf = new StringBuffer();
      for (int i=1; i<=32; i++) buf.append(x>>>(32-i) & 0x00000001);
      return buf.toString();
   }
}
```

Here is the output of the test program:

```
 a: 00110011001100110011001100110011 = 858993459
 b: 01010101010101010101010101010101 = 1431655765
o1: 00010001000100010001000100010001 = 286331153
o2: 01110111011101110111011101110111 = 2004318071
o3: 01100110011001100110011001100110 = 1717986918
o4: 11001100110011001100110011001100 = -858993460
```

The resulting values in the program output do match those given in my examples in the previous section. The resulting value of the complement operation in the program output shows -858993460, which is the same as 3233857728 represented in a signed 32-bit integer format.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Bits, Bytes, Bitwise and Shift Operations](#part0040.xhtml)

∟Shift Operations - Left, Right or Unsigned Right

This section describes shift operations: 'Left Shift', 'Right Shift', and 'Unsigned Right Shift'. A tutorial example is provided to show you how shift operations work on 'int' data type values.

**What is a shift operation?** A shift operation is an operation that requires the operand to be represented in a binary format, viewed as a bit string, then shift all bit values to the left or right.

Again, Java defines shift operations on "int" data type values, not on "byte" data type values. So a shift operation requires that the involved "int" value to be represented into a bit string of 32 bits. And the operation will be applied to shift bit values to the left or right on the bit string.

Java defines 3 shift operations called: "Left Shift", "Right Shift", and "Unsigned Right Shift":

1\. Shift operation "Left Shift" - "<<": The "Left Shift" operation on an "int" value can be described as:

*   Representing the first operand, an "int" values, into a bit string of 32 bits.
*   Shift all bit values to the left and fill the empty bits on the right end with a 0 value. The number of bits to shift is given in the second operand.
*   Converting the shifted bit string to an "int" value as the operation result.

The following diagram gives an example of a "<<" operation in 2 formats:

```
 Decimal             Binary
 -858993460  << 6     11001100110011001100110011001100 << 6
-----------------   ---------------------------------------
= 858993408         = 00110011001100110011001100000000
```

2\. Shift operation "Right Shift" - ">>": The "Right Shift" operation on an "int" value can be described as:

*   Representing the first operand, an "int" values, into a bit string of 32 bits.
*   Shift all bit values to the right and fill the empty bits on the left end with the original value of the sign bit, the most left bit of the bit string. The number of bits to shift is given in the second operand.
*   Converting the shifted bit string to an "int" value as the operation result.

The following diagram gives an example of a ">>" operation in 2 formats:

```
 Decimal             Binary
 -858993460  >> 6     11001100110011001100110011001100 >> 6
-----------------   ---------------------------------------
=4281545523         = 11111111001100110011001100110011
```

3\. Shift operation "Unsigned Right Shift" - ">>>": The "Unsigned Right Shift" operation on an "int" value can be described as:

*   Representing the first operand, an "int" values, into a bit string of 32 bits.
*   Shift all bit values to the right and fill the empty bits on the left end with a 0 value. The number of bits to shift is given in the second operand.
*   Converting the shifted bit string to an "int" value as the operation result.

The following diagram gives an example of a ">>>" operation in 2 formats:

```
 Decimal             Binary
 -858993460  >>> 6     11001100110011001100110011001100 >>> 6
-----------------   ---------------------------------------
=  53687091         = 00000011001100110011001100110011
```

To verify the examples given above, I wrote the following test program, ShiftOperations.java:

```
 /* ShiftOperations.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class ShiftOperations {
   public static void main(String[] arg) {
      int a = -858993460; // binary: 11001100110011001100110011001100

      int o1 = a << 6;  // left shift
      int o2 = a >> 6;  // right shift
      int o3 = a >>> 6; // unsigned right shift

      System.out.println(" a: "+getBitString(a) +" = "+a);
      System.out.println("o1: "+getBitString(o1) +" = "+o1);
      System.out.println("o2: "+getBitString(o2) +" = "+o2);
      System.out.println("o3: "+getBitString(o3) +" = "+o3);
   }
   private static String getBitString(int x) {
      StringBuffer buf = new StringBuffer();
      for (int i=1; i<=32; i++) buf.append(x>>>(32-i) & 0x00000001);
      return buf.toString();
   }
}
```

The output of the test program matches my earlier examples:

```
 a: 11001100110011001100110011001100 = -858993460
o1: 00110011001100110011001100000000 = 858993408
o2: 11111111001100110011001100110011 = -13421773
o3: 00000011001100110011001100110011 = 53687091
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Managing Bit Strings in Byte Arrays

This chapter provides tutorial notes and tutorial examples on managing bit strings in byte arrays. Topics include setting a bit value into a byte array; getting a bit value back from a byte array; rotating all bits in a byte array.

> [setBit() - Storing a Bit into a Byte Array](#part0048.xhtml)
> 
> [getBit() - Retrieving a Bit from a Byte Array](#part0049.xhtml)
> 
> [rotateLeft() - Left Rotating All Bits in a Byte Array](#part0050.xhtml)
> 
> [bitStringTest.java - Testing Program](#part0051.xhtml)

Conclusion:

*   Java has no built-in support for bit strings.
*   Bit strings can be stored in byte arrays.
*   getBit() and setBit() are easy to implement on byte arrays.
*   rotateLeft() is easy to apply on byte arrays also.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Managing Bit Strings in Byte Arrays](#part0047.xhtml)

∟setBit() - Storing a Bit into a Byte Array

This section provides a tutorial example on how to set one bit into a byte array at a specific bit position setBit().

In many applications, information must be stored and operated as bit strings. Unfortunately, Java does not provide any built-in data types or classes to support bit strings. There are several third party BitString classes that you can use to store and manage your bit strings.

Another way to store and manage bit strings is to use byte arrays, byte[]. I have used them while implementing DES (Data Encryption Standard) encryption algorithm, see "Cryptography Tutorials - Herong's Tutorial Notes" at [www.herongyang.com/Cryptography/](https://www.herongyang.com/Cryptography/).

Storing and managing bit strings in byte arrays is not that hard as long as you define a pair of setBit() and getBit() methods. Here is my set of methods used in my cryptography tutorials. Of course, there is room for improvements in these methods. Try it yourself.

1\. setBit() - To set one bit to a bit string at the specified position with the specified bit value:

```
 private static void setBit(byte[] data, int pos, int val) {
      int posByte = pos/8;
      int posBit = pos%8;
      byte oldByte = data[posByte];
      oldByte = (byte) (((0xFF7F>>posBit) & oldByte) & 0x00FF);
      byte newByte = (byte) ((val<<(8-(posBit+1))) | oldByte);
      data[posByte] = newByte;
   }
```

Explanations:

*   The method interface expects the caller to provide the byte array that stores the bit string, the position in the bit string where bit value needs to be set, and the new bit value given as a "int" value.
*   The first statement calculates the array index, "posByte", of the affected byte that holds the bit to be set.
*   The second statement calculates the bit position, "posBit", in the affected byte where the bit value needs to be set.
*   The third statement fetches the affected byte into a temporary variable, "oldByte".
*   The fourth statement sets a 0 value to "oldByte" at the bit position of "posBit".
*   The fifth statement sets the input "val" to "oldByte" at the bit position of "posBit" and assigns to "newByte".

To understand how the fourth statement works, let's assume that posBit = 2\. Then the evaluation process of the statement can be described as:

```
 0xFF7F    : 11111111 11111111 11111111 01111111
>> 2
-----------------------------------------------
          = 11111111 11111111 11111111 11011111
& oldByte : ???????? ???????? ???????? xxxxxxxx
-----------------------------------------------
          = ???????? ???????? ???????? xx0xxxxx
& 0x00FF  : 00000000 00000000 00000000 11111111
-----------------------------------------------
          = 00000000 00000000 00000000 xx0xxxxx
```

The fifth statement can be described as:

```
 val       : 00000000 00000000 00000000 0000000y
<< 5
-----------------------------------------------
          = 00000000 00000000 00000000 00y00000
| oldByte : 00000000 00000000 00000000 xx0xxxxx
-----------------------------------------------
          = 00000000 00000000 00000000 xxyxxxxx
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Managing Bit Strings in Byte Arrays](#part0047.xhtml)

∟getBit() - Retrieving a Bit from a Byte Array

This section provides a tutorial example on how to get one bit back from a byte array at a specific bit position - getBit().

2\. getBit() - To get one bit back from a bit string stored in a byte array at the specified position:

```
 private static int getBit(byte[] data, int pos) {
      int posByte = pos/8;
      int posBit = pos%8;
      byte valByte = data[posByte];
      int valInt = valByte>>(8-(posBit+1)) & 0x0001;
      return valInt;
   }
```

Explanations:

*   The method interface expects the caller to provide the byte array that stores the bit string, the position in the bit string where bit value needs to be retrieved.
*   The first statement calculates the array index, "posByte", of the source byte that holds the bit to be retrieved.
*   The second statement calculates the bit position, "posBit", in the source byte where the bit value needs to be retrieved.
*   The third statement fetches the source byte into a temporary variable, "valByte".
*   The fourth statement gets the bit value from "valByte" at the bit position of "posBit".

To understand how the fifth statement works, let's assume that posBit = 2\. Then the evaluation process of the statement can be described as:

```
 valByte   : ???????? ???????? ???????? xxyxxxxx
>> 5
-----------------------------------------------
          = ???????? ???????? ???????? ?????xxy
& 0x0001  : 00000000 00000000 00000000 00000001
-----------------------------------------------
          = 00000000 00000000 00000000 0000000y
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Managing Bit Strings in Byte Arrays](#part0047.xhtml)

∟rotateLeft() - Left Rotating All Bits in a Byte Array

This section provides a tutorial example on how to perform a left rotation of all bits in a byte array - rotateLeft().

If you are trying to implement DES (Data Encryption Standard) encryption algorithm, you will need to rotate bit values in bit strings. With the getBit() and setBit() methods defined above, rotating a bit string stored in a byte array becomes easy to do. Here my rotateLeft() method.

```
 private static byte[] rotateLeft(byte[] in, int len, int step) {
      int numOfBytes = (len-1)/8 + 1;
      byte[] out = new byte[numOfBytes];
      for (int i=0; i<len; i++) {
         int val = getBit(in,(i+step)%len);
         setBit(out,i,val);
      }
      return out;
   }
```

Explanations:

*   The method interface expects the caller to provide the byte array that stores the input bit string, the length of the input bit string, and the number of steps to rotate.
*   The first statement calculates the number of bytes needed to store the output bit string.
*   The second statement defines a new byte array to store the output bit string.
*   The third statement loops through every bit in the output bit string.
*   The fourth statement in the loop gets the bit value by calling getBit() on the input bit string from a bit position rotated to the right of the current bit position. The number of steps to be rotated is given by the caller.
*   The fifth statement in the loop sets the bit value by calling setBit() on the output bit string at the current bit position.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Managing Bit Strings in Byte Arrays](#part0047.xhtml)

∟bitStringTest.java - Testing Program

This section provides tutorial example program to test setBit(), getBit(), and rotateLeft() to manage bit strings in byte arrays.

To test my bit string methods, I wrote the following test program, bitStringTest.java

```
 /* BitStringTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class BitStringTest {
   public static void main(String[] arg) {
      byte[] inString = new byte[5];
      inString[0] = (byte) 0x00FF; // binary: 11111111
      inString[1] = (byte) 0x0000; // binary: 00000000
      inString[2] = (byte) 0x00FF; // binary: 11111111
      inString[3] = (byte) 0x0000; // binary: 00000000
      inString[4] = (byte) 0x0000; // binary: 00000000
      int length = 5*8; // 40 bits in total

      int step = 6; // steps to rotate
      byte[] outString = rotateLeft(inString, length, step);
      printBytes(inString, " Input");
      printBytes(outString, "Output");
   }
   private static byte[] rotateLeft(byte[] in, int len, int step) {
      int numOfBytes = (len-1)/8 + 1;
      byte[] out = new byte[numOfBytes];
      for (int i=0; i<len; i++) {
         int val = getBit(in,(i+step)%len);
         setBit(out,i,val);
      }
      return out;
   }
   private static int getBit(byte[] data, int pos) {
      int posByte = pos/8;
      int posBit = pos%8;
      byte valByte = data[posByte];
      int valInt = valByte>>(8-(posBit+1)) & 0x0001;
      return valInt;
   }
   private static void setBit(byte[] data, int pos, int val) {
      int posByte = pos/8;
      int posBit = pos%8;
      byte oldByte = data[posByte];
      oldByte = (byte) (((0xFF7F>>posBit) & oldByte) & 0x00FF);
      byte newByte = (byte) ((val<<(8-(posBit+1))) | oldByte);
      data[posByte] = newByte;
   }
   private static void printBytes(byte[] data, String name) {
      System.out.println("");
      System.out.println(name+":");
      for (int i=0; i<data.length; i++) {
         System.out.print(byteToBits(data[i])+" ");
      }
      System.out.println();
   }
   private static String byteToBits(byte b) {
      StringBuffer buf = new StringBuffer();
      for (int i=0; i<8; i++)
         buf.append((int)(b>>(8-(i+1)) & 0x0001));
      return buf.toString();
   }
}
```

Here is the output of the test program:

```
 Input:
11111111 00000000 11111111 00000000 00000000

Output:
11000000 00111111 11000000 00000000 00111111
```

I think getBit(), setBit(), and rotateLeft() are working correctly. What do you think?

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Reference Data Types and Variables

This chapter provides tutorial notes and example codes on reference data types and variables. Topics include 5 reference data types; reference data type variables store references to objects; multiple variables referring to a single object; superclass-subclass relation; superinterface-subinterface relation; interface-class relation; type casting.

> [Reference Types Supported in Java](#part0053.xhtml)
> 
> [Creating Class Type Objects](#part0054.xhtml)
> 
> [Class Type Variables Storing References](#part0055.xhtml)
> 
> [Interface Type Variables](#part0056.xhtml)
> 
> [Class and Interface Hierarchy](#part0057.xhtml)
> 
> [Supertype and Subtype](#part0058.xhtml)
> 
> [Explicit and Implicit Type Casting](#part0059.xhtml)
> 
> [Type Casting Example Program](#part0060.xhtml)
> 
> [Type Casting Compile and Runtime Error](#part0061.xhtml)

Conclusion:

*   Java supports 5 reference data types: class type, interface, type variable, array type, and null;
*   A class type variable stores the reference of an object of the same class.
*   A interface type variable stores the reference of an object of a class that implements the interface.
*   java.lang.Object is a superclass of all other classes.
*   java.lang.Object is a supertype of all other class and interface types.
*   Up casting (widening reference conversion) is always allowed.
*   Down casting (narrowing reference conversion) is allowed only if the reference object is compatible with the subtype.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Reference Types Supported in Java

This section provides a list of reference types supported in Java: class type, interface type, type variable and null.

Other than primitive types, Java also supports several reference types as shown below:

```
 Data Types
|
|- Primitive Types
|  |...
|
|- Reference Types
   |
   |- Class Type
   |  |- Enum Type
   |
   |- Interface Type
   |  |- Annotation Type
   |
   |- Type Variable
   |
   |- Array Type
   |
   |- null
```

1\. Class Type - A class type is a reference type representing objects whose behaviors are defined in the corresponding class. For example, java.lang.String is a class type.

1.1\. Enum Type - A enum type is a special kind of class type that has a set of pre-defined instances representing a set of static values called enum constants.

2\. Interface Type - An interface type is a reference type representing objects whose behaviors are defined in the corresponding interface. For example, java.lang.Runnable is an interface type.

2.1\. Annotation Type - A Annotation type is a special kind of interface type that defined by a "@interface" declaration statement (also called annotation declaration statement).

3\. Type Variable - A type variable is a reference type representing objects whose type will be determined at execution time, not at the compilation time. Type variable is introduced in JDK 5 to create generic classes, generic interfaces and generic methods. For example, T is a type variable in "public class Box<T> {private T t;...}".

4\. Array Type - An array type is a reference type representing objects of arrays of a primitive type or a reference type. For example, int[], String[] are array types.

5\. null - null is a special reference type representing no object.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Creating Class Type Objects

This section describes how class type objects can be created using the 'new' operator and special methods.

There are a number of ways to create a class type object:

1\. The "new" operator - A class type object can be created using the new operator to call the class constructor. Examples are listed below:

```
 new String("Hello"); // creates a String object
   new java.util.Date(); // creates a Date object
   new java.util.ArrayList<String>(); // creates an ArrayList<String>
```

2\. Special method - A class type object can be created using special methods provided by classes. Examples are listed below:

```
 javax.net.SocketFactory.getDefault().createSocket();
      // creates a java.net.Socket object

   java.security.KeyPairGenerator.getInstance("DSA");
      // creates a java.security.KeyPairGenerator object
```

3\. String literal and String concatenation - A String type object can be created using a String literal or a String concatenation. Examples are listed below:

```
 "Hello" // creates a String object
   "Hello"+" world!" // creates a String object
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Class Type Variables Storing References

This section describes how references of class objects are stored in class variables of the same class type.

When a variable is declared as a class type, it will be used to store references of objects of the same class type. The object class type must match the variable class type. Examples are listed below:

```
 String msg = new String("Hello");
      // assigns the reference of a String object

   java.util.Date today = new java.util.Date();
      // assigns the reference of a Data object

   java.util.ArrayList<String>
      = new java.util.ArrayList<String>();
      // assigns the reference of an ArrayList<String> object
```

Since class type variables stores references of class objects, it is very common that the reference of a single object can be stored in multiple variables. Here is a tutorial example program that shows you how the reference of a single object is stored in to variables:

```
 /* ClassTypeVariable.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class ClassTypeVariable {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;

      // assigning the reference of a Date object
      Date myTime = new Date();

      // showing the object content
      o.println("myTime before = "+myTime);

      // assigning the reference to another variable
      Date hisTime = myTime;

      // modifying the object content
      hisTime.setTime(hisTime.getTime()+1000*60*60);

      // showing the object content
      o.println("myTime after = "+myTime);
      o.println("hisTime after = "+hisTime);
   }
}
```

Compile and run the example, you will get:

```
 myTime before = Sun May 04 22:14:47 PDT 2018
myTime after = Sun May 04 23:14:47 PDT 2018
hisTime after = Sun May 04 23:14:47 PDT 2018
```

The result proves that both "myTime" and "hisTime" are references of the same object. When the object value is modified, time moved to 1 hour later, through "hisTime" reference, "myTime" reference can also see the change.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Interface Type Variables

This section describes how to use an interface type variable to store references to objects of classes that implemented this interface.

Interface type variables are used in Java following these basic rules:

*   An interface type variable can store the reference of an object of a class that implemented this interface.
*   The dot operator of an interface type variable can only invoke methods declared in this interface.

Here is a tutorial example program that shows you how to use interface type variables:

```
 /* InterfaceTypeVariable.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class InterfaceTypeVariable {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;

      // assigning the reference of a LinkedList object
      LinkedList<String> bookList = new LinkedList<String>();

      // assigning the reference to an implemented interface
      // LinkedList<E> implements Queue<E>
      Queue<String> bookQueue = bookList;

      // accessing interface methods
      bookQueue.add("Java Tutorials");
      bookQueue.add("PHP Tutorials");
      String next = bookQueue.remove();

      o.println("Next book in the queue = "+next);
   }
}
```

Compile and run the example, you will get:

```
 Next book in the queue = Java Tutorials
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Class and Interface Hierarchy

This section describes Java class and interface hierarchical relationships to support object inheritance: superclass-subclass relation, superinteface-subinterface relation, and interface-class relation.

Java allows classes and interfaces to be created with hierarchical relationship to support object inheritance. The class and interface hierarchy supports 3 types of relations:

1\. Superclass-Subclass Relation - The subclass extends the superclass and inherits all behaviors of the superclass. An example is listed below:

```
 class javax.net.ssl.X509ExtendedKeyManager
   extends java.lang.Object {};
   // superclass: java.lang.Object
   // subclass: javax.net.ssl.X509ExtendedKeyManager
```

2\. Superinteface-Subinterface Relation - The subinterface extends the superinterface and inherits all behaviors of the superinterface. An example is listed below:

```
 interface javax.net.ssl.X509KeyManager
   extends javax.net.ssl.KeyManager {};
   // superinterface: javax.net.ssl.KeyManager
   // subinterface: javax.net.ssl.X509KeyManager
```

3\. Interface-Class Relation - The class implements the interface and inherits all behaviors of the interface. An example is listed below:

```
 class javax.net.ssl.X509ExtendedKeyManager
   implements javax.net.ssl.X509KeyManager {};
   // interface: javax.net.ssl.X509KeyManager
   // class: javax.net.ssl.X509ExtendedKeyManager
```

The diagram below shows you a simple class interface hierarchy example:

![](Images/image00180.jpeg)

Java Class Interface Hierarchy Example

By default, all classes extend the java.lang.Object class. In other words, all classes are subclasses of the java.lang.Object class.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Supertype and Subtype

This section describes the supertype-subtype relationships: a supertype corresponds a class or interface that is extended or implemented directly or indirectly by the class or interface of the subtype.

Based on Class and Interface hierarchical relationships, Java class and interface reference types are related to each other with supertype-subtype relationships.

*   Supertype - A class type or interface type is a supertype relative to another type, if its corresponding class or interface has been extended or implemented directly or indirectly by the class or interface of the other type.
*   Subtype - A class type or interface type is a subtype relative to another type, if its corresponding class or interface is extending or implementing directly or indirectly the class or interface of the other type.

Using the class interface hierarchy example presented in the previous section, the supertype-subtype relationship can be illustrated in the picture below:

![](Images/image00181.jpeg)

Java Class Interface Type Hierarchy

Based on the picture, we can say:

*   javax.net.ssl.X509ExtendedKeyManager is a subtype of java.lang.Object.
*   javax.net.ssl.X509ExtendedKeyManager is a subtype of javax.net.ssl.X509KeyManager.
*   javax.net.ssl.X509ExtendedKeyManager is a subtype of javax.net.ssl.KeyManager.
*   javax.net.ssl.KeyManager is a supertype of javax.net.ssl.X509ExtendedKeyManager.
*   javax.net.ssl.KeyManager is a supertype of javax.net.ssl.X509KeyManager.
*   java.lang.Object is a supertype of all other class and interface types.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Explicit and Implicit Type Casting

This section describes type casting supported in Java: up casting (widening reference conversion) and down casting (narrowing reference conversion). Cast operation can be written explicitly with the cast operator (T), or implicitly with no operator.

In Java, class and interface reference type can be converted from one type to another type using the cast operation in two ways:

1\. Widening Reference Conversion - Type S is converted to type T, where S is a subtype of T. Widening reference conversion is also called up casting, because it converts a subtype to a supertype. Up casting is always allowed, because the reference object of a subtype is always compatible with a supertype. For example:

```
 String msg = new String("Hello");

    // up casting from String to Object
    Object obj = (Object) msg;
```

2\. Narrowing Reference Conversion - Type T is converted to type S, where T is a supertype of S. Narrowing reference conversion is also called down casting, because it converts a supertype to a subtype. Down casting is always allowed only if the reference object is compatible with the subtype. If the reference object is not compatible with the subtype, a compilation error or runtime exception will be resulted. For example:

```
 Object obj = new String("Hello");

    // down casting from Object to String
    String msg = (String) obj;
```

There are 2 syntax formats to write a type casting operation:

1\. Explicit Casting - Adding (cast-to type) on the left side of the cast-from type. For example,

```
 String msg = new String("Hello");

    // explicit casting
    Object obj = (Object) msg;
```

2\. Implicit Casting - Letting compiler automatically cast the type based on expression context. For example,

```
 String msg = new String("Hello");

    // explicit casting
    Object obj = msg;
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Type Casting Example Program

This section provides a tutorial example on how to use up casting and down casting explicitly and implicitly.

Now let's see a tutorial example program that uses up casting and down casting explicitly and implicitly:

```
 /* TypeCasting.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class TypeCasting {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;

      // getting an object of reference type: Thread
      Thread alarmThread = new Thread();

      // explicit up casting to Object
      Object alarmObject = (Object) alarmThread;

      // explicit down casting to Runnable
      Runnable alarmRunnable = (Runnable) alarmObject;

      // explicit down casting to Thread
      Thread copyThread = (Thread) alarmRunnable;

      // implicit up casting to Runnable
      Runnable copyRunnable = copyThread;

      o.println("alarmThread = "+alarmThread);
      o.println("alarmObject = "+alarmObject);
      o.println("alarmRunnable = "+alarmRunnable);
      o.println("copyThread = "+copyThread);
      o.println("copyRunnable = "+copyRunnable);
   }
}
```

Compile and run the example, you will get:

```
 alarmThread = Thread[Thread-0,5,main]
alarmObject = Thread[Thread-0,5,main]
alarmRunnable = Thread[Thread-0,5,main]
copyThread = Thread[Thread-0,5,main]
copyRunnable = Thread[Thread-0,5,main]
```

As you can see, all up castings and down castings are valid, because the reference object "new Thread()" is compatible with Object, Runnable, and Thread.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Reference Data Types and Variables](#part0052.xhtml)

∟Type Casting Compile and Runtime Error

This section provides a tutorial example on compilation time casting error and runtime casting exception.

If you are trying to convert reference type to another type that is not compatible, you will get a compiler error. Here is a simple example:

```
 /* TypeCastingCompileError.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class TypeCastingCompileError {
   public static void main(String[] a) {

      // Compiler error: Casting from Integer to Long is not allowed
      Integer myInteger = new Integer(777);
      Long myLong = (Long) myInteger;
   }
}
```

Try to compile it. You will see a compilation error:

```
 TypeCastingCompileError.java:10: error: incompatible types: Integer
cannot be converted to Long
      Long myLong = (Long) myInteger;
                           ^
Note: TypeCastingCompileError.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
1 error
```

If you want, you can avoid the compiler error by casting Integer to Object, before casting it to Long. But you will get a runtime error. Here is a simple example:

```
 /* TypeCastingRuntimeError.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class TypeCastingRuntimeError {
   public static void main(String[] a) {

      try {
         // Runtime error: Casting from Integer to Long is not allowed
         Integer myInteger = Integer.valueOf(777);
         Object myObject = (Object) myInteger;
         Long myLong = (Long) myObject;
      } catch (Exception e) {
         e.printStackTrace();
      }

      try {
         // Runtime error: Casting from Integer to Long is not allowed
         Integer hisInteger = Integer.valueOf(888);
         Number hisNumber = (Number) hisInteger;
         Long hisLong = (Long) hisNumber;
      } catch (Exception e) {
         e.printStackTrace();
      }
   }
}
```

Try to compile and run it with JDK 13:

```
 java.lang.ClassCastException: java.base/java.lang.Integer cannot be cast
to java.base/java.lang.Long
        at TypeCastingRuntimeError.main(TypeCastingRuntimeError.java:11)
java.lang.ClassCastException: java.base/java.lang.Integer cannot be cast
to java.base/java.lang.Long
        at TypeCastingRuntimeError.main(TypeCastingRuntimeError.java:20)
```

Try to compile and run it with JDK 8:

```
 java.lang.ClassCastException:
   java.lang.Integer cannot be cast to java.lang.Long
        at TypeCastingRuntimeError.main(TypeCastingRuntimeError.java:11)

java.lang.ClassCastException:
   java.lang.Integer cannot be cast to java.lang.Long
        at TypeCastingRuntimeError.main(TypeCastingRuntimeError.java:20)
```

As you can see from this example, the compiler fails to detect the type casting error, because down casting "(Long) Object" or "(Long) Number" is a valid casting if the reference object is a Long object.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Enum Types and Enum Constants

This chapter describes enum types and enum constants. Topics include 'enum' declaration statement, instance variables and instance methods of enum constants, enum supertype and type hierarchy, inherited static and instance methods, compiler added implicit methods.

> [What Is an Enum Type](#part0063.xhtml)
> 
> [Use 'class' to Define Enumeration](#part0064.xhtml)
> 
> [Instance Variables for Enum Constants](#part0065.xhtml)
> 
> [java.lang.Enum Super Type](#part0066.xhtml)
> 
> [Enum Constant Inherited Methods](#part0067.xhtml)
> 
> [Enum Constant Implicit Methods](#part0068.xhtml)

Conclusion:

*   An enum type is a special kind of class type that has a set of pre-defined instances representing a set of static values called enum constants.
*   An enum type can have instance variables and instance methods like other class types.
*   All enum types have a common base type called Enum<E> which implements 3 interfaces: Serializable, Comparable<E>, and Constable.
*   The base class Comparable<E> also provides some static and instance methods like valueOf(), name(), ordinal(), compareTo(), etc.
*   Java compiler implicitly adds 2 static methods to all enum types: valueOf() and values().

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Enum Types and Enum Constants](#part0062.xhtml)

∟What Is an Enum Type

This section describes 'enum' types, which are defined by 'enum' declaration statements. An 'enum' type is actually a special kind of class type.

**What Is an Enum Type?** An enum type is a special kind of class type that has a set of pre-defined instances representing a set of static values called enum constants.

An enum type is defined by the "enum" declaration statement. A simplest enum Type can be defined with 2 components:

*   The enum type name - Specified by the declaration identifier.
*   The enum constant list - Specified as a comma-delimited identifier list in the declaration body.

Here is an example of "enum" declaration statement:

```
 /* Color.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
enum Color {
   // enum constants declaration and initialization
   RED, GREEN, BLUE;
}
```

The above "enum" declaration statement actually:

*   Defines a class called "Color".
*   Declares 3 public static variables: "RED", "GREEN", and "BLUE".
*   Creates one "Color" instance assigned to each variable listed above.
*   Overrides the toString() instance method to return its associated variable name.

We can verify the above with this test program:

```
 /* ColorTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class ColorTest {
   public static void main(String[] arg) {

      System.out.println("Converting enum constant to string:");
      System.out.println("   Color.RED = "+Color.RED);
      System.out.println("   Color.GREEN = "+Color.GREEN);
      System.out.println("   Color.BLUE = "+Color.BLUE);

      System.out.println("Getting enum constant class name:");
      String clsName = Color.RED.getClass().getName();
      System.out.println("   Color.RED.getClass().getName() = "+clsName);
   }
}
```

If you compile ColorTest.java with Color.java and run ColorTest.class, you should get:

```
 herong> javac Color.java

herong> javac ColorTest.java

herong> java ColorTest
Converting enum constant to string:
   Color.RED = RED
   Color.GREEN = GREEN
   Color.BLUE = BLUE
Getting enum constant class name:
   Color.RED.getClass().getName() = Color
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Enum Types and Enum Constants](#part0062.xhtml)

∟Use 'class' to Define Enumeration

This section provides a tutorial on how to define a set of enumeratin constants use a 'class' declaration statement.

If you don't like to use 'enum' declaration statements, you can use 'class' declaration statement to define an enumeration. Here is an example of "class" declaration statement defining as set of enumeration constants:

```
 /* Season.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class Season {
   public static Season WINTER = new Season("WINTER");
   public static Season SPRING = new Season("SPRING");
   public static Season SUMMER = new Season("SUMMER");
   public static Season FALL = new Season("FALL");
   private String label = null;
   Season(String label) { this.label = label; }
   public String toString() { return label; }
}
```

We can see how those enumeration constants behave with this test program:

```
 /* SeasonTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class SeasonTest {
   public static void main(String[] arg) {

      System.out.println("Converting enum constant to string:");
      System.out.println("   Season.WINTER = "+Season.WINTER);
      System.out.println("   Season.SPRING = "+Season.SPRING);
      System.out.println("   Season.SUMMER = "+Season.SUMMER);
      System.out.println("   Season.FALL = "+Season.FALL);

      System.out.println("Getting enum constant class name:");
      String clsName = Season.WINTER.getClass().getName();
      System.out.println("   Season.WINTER.getClass().getName() = "+clsName);
   }
}
```

If you compile SeasonTest.java with Season.java and run SeasonTest.class, you should get:

```
 herong> javac Season.java

herong> javac SeasonTest.java

herong> javac SeasonTest
Converting enum constant to string:
   Season.WINTER = WINTER
   Season.SPRING = SPRING
   Season.SUMMER = SUMMER
   Season.FALL = FALL
Getting enum constant class name:
   Season.WINTER.getClass().getName() = Season
```

Cool. We have defined a set of enumeration constants with a "class" declaration statement.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Enum Types and Enum Constants](#part0062.xhtml)

∟Instance Variables for Enum Constants

This section provides a tutorial on how to define instance variables and methods for enum constants.

Since enum types are actually class types, we can define instance variables and methods to your enum types by following these rules:

*   Declare and initialize enum constants at the beginning of the enum body.
*   Add an argument list to each enum constant for calling the constructor.
*   Declare instance and class variables in the same way as in the "class" declaration statement.
*   Declare constructors in the same way as in the "class" declaration statement.
*   Declare instance and class methods in the same way as in the "class" declaration statement.

Here is a sample program that shows you how to define instance variables and methods in an "enum" declaration statement. Notice that the "Rank" enum type is declared like an inner class inside the "EnumWithInstanceVariable" class.

```
 /* EnumWithInstanceVariable.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class EnumWithInstanceVariable {
   enum Rank {
     // enum constants declaration and initialization
      GOLD(500), SILVER(300), BRONZE(100);

      // instance variable
      public int point;

      // constructor
      Rank(int point) { this.point = point; }

      // instance method
      public int getPoint() { return point; }
   }

   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      out.println("Converting enum constant to string:");
      out.println("   Rank.GOLD = "+Rank.GOLD);
      out.println("   Rank.SILVER = "+Rank.SILVER);
      out.println("   Rank.BRONZE = "+Rank.BRONZE);

      out.println("Getting enum constant class name:");
      String clsName = Rank.GOLD.getClass().getName();
      out.println("   Rank.GOLD.getClass().getName() = "+clsName);

      out.println("Accessing enum constant instance variable:");
      out.println("   Rank.GOLD.point = "+Rank.GOLD.point);
      out.println("   Rank.SILVER.point = "+Rank.SILVER.point);
      out.println("   Rank.BRONZE.point = "+Rank.BRONZE.point);

      out.println("Accessing enum constant instance method:");
      out.println("   Rank.GOLD.getPoint() = "+Rank.GOLD.getPoint());
      out.println("   Rank.SILVER.getPoint() = "+Rank.SILVER.getPoint());
      out.println("   Rank.BRONZE.getPoint() = "+Rank.BRONZE.getPoint());
   }
}
```

If you compile and run EnumWithInstanceVariable.java, you should get:

```
 herong> java EnumWithInstanceVariable.java

Converting enum constant to string:
   Rank.GOLD = GOLD
   Rank.SILVER = SILVER
   Rank.BRONZE = BRONZE
Getting enum constant class name:
   Rank.GOLD.getClass().getName() = EnumWithInstanceVariable$Rank
Accessing enum constant instance variable:
   Rank.GOLD.point = 500
   Rank.SILVER.point = 300
   Rank.BRONZE.point = 100
Accessing enum constant instance method:
   Rank.GOLD.getPoint() = 500
   Rank.SILVER.getPoint() = 300
   Rank.BRONZE.getPoint() = 100
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Enum Types and Enum Constants](#part0062.xhtml)

∟java.lang.Enum Super Type

This section provides a tutorial on how to verify the enum type hierarchy supported by the java.lang.Enum Super Type.

From previous tutorials, we can see that the "enum" declaration statement provides a simpler way to define a set of constants than the "class" declaration statement.

Another benefit of using the "enum" declaration statement is that the resulting enum type is a subtype of java.lang.Enum<E extends Enum*lt;E>>, which implements 3 interfaces: Serializable, Comparable<E>, Constable.

So if you define an enum type E with an "enum" declaration statement, E will automatically become a subtype of Enum<Rank> and Enum<?>. E will also become Serializable, Comparable<E>, and Constable.

Here is a sample program that verifies the type hierarchy of an enum type:

```
 /* EnumTypeHierarchy.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.lang.Enum;
import java.lang.Comparable;
import java.lang.constant.Constable;
import java.io.Serializable;
class EnumTypeHierarchy {
   enum Rank {
      GOLD, SILVER, BRONZE;
   }
   enum Color {
      RED, GREEN, BLUE;
   }

   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      out.println("Converting enum constant to string:");
      out.println("   Rank.GOLD = "+Rank.GOLD);
      out.println("   Rank.SILVER = "+Rank.SILVER);
      out.println("   Rank.BRONZE = "+Rank.BRONZE);

      Rank gold = Rank.GOLD;
      out.println("Enum constant class:");
      out.println("   gold instanceof Rank = "+(gold instanceof Rank));
      out.println("   gold class name = "+gold.getClass().getName());

      out.println("Reifiable class types - Gold:");
      out.println("   is a Rank = "+(gold instanceof Rank));
      out.println("   is a Enum<?> = "+(gold instanceof Enum<?>));
      out.println("   is a Object = "+(gold instanceof Object));

      out.println("Reifiable interface types - Gold:");
      out.println("   is Serializable = "+(gold instanceof Serializable));
      out.println("   is Comparable<?> = "+(gold instanceof Comparable<?>));
      out.println("   is Constable = "+(gold instanceof Constable));

      out.println("Non-reifiable types:");
      Enum<Rank> enumRank = gold;
      out.println("   gold is an Enum<Rank> = true");
      // Enum<Color> enumColor = gold;
      out.println("   gold is not an Enum<Color> = false");
      Comparable<Rank> comparableRank = gold;
      out.println("   gold is an Comparable<Rank> = true");
      // Comparable<Color> comparableColor = gold;
      out.println("   gold is an Comparable<Color> = false");
   }
}
```

If you compile and run EnumTypeHierarchy.java, you should get:

```
 herong> java EnumTypeHierarchy.java

Converting enum constant to string:
   Rank.GOLD = GOLD
   Rank.SILVER = SILVER
   Rank.BRONZE = BRONZE
Enum constant class:
   gold instanceof Rank = true
   gold class name = EnumTypeHierarchy$Rank
Reifiable class types - Gold:
   is a Rank = true
   is a Enum<?> = true
   is a Object = true
Reifiable interface types - Gold:
   is Serializable = true
   is Comparable<?> = true
   is Constable = true
Non-reifiable types:
   gold is an Enum<Rank> = true
   gold is an Enum<Color> = false
   gold is an Comparable<Rank> = true
   gold is an Comparable<Color> = false
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Enum Types and Enum Constants](#part0062.xhtml)

∟Enum Constant Inherited Methods

This section provides a tutorial on how to invoke static and instance method inherited from the generic base class of java.lang.Enum.

From previous tutorial, we learned that all enum types have a common super type of java.lang.Enum<?> supported by the generic base class of java.lang.Enum<E extends Enum*lt;E>>. The base class implements 3 interfaces: Serializable, Comparable<E>, Constable. It also provided several interesting static and instance methods:

*   name() - Returning the name of this enum constant as specified in the declaration list.
*   ordinal() - Returning the ordinal (the position in the declaration list) of this enum constant.
*   toString() - Returning the name of this enum constant as specified in the declaration list.
*   compareTo() - Comparing this enum constant to another in the same enum type by their declaration position.
*   getDeclaringClass() - Returning the Class object of this enum constant.
*   valueOf() - Returning an enum constant of the specified enum type with the specified name.

Here is a sample program that shows you how to invoke methods listed above:

```
 /* EnumInheritedMethods.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.lang.Enum;
class EnumInheritedMethods {
   enum Rank {
      GOLD, SILVER, BRONZE;
   }

   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      Rank gold = Rank.GOLD;
      Rank silver = Rank.SILVER;

      out.println("Inherited instance methods:");
      out.println("   silver.name() = "+silver.name());
      out.println("   silver.toString() = "+silver.toString());
      out.println("   silver.ordinal() = "+silver.ordinal());
      out.println("   silver.compareTo() = "+silver.compareTo(gold));
      out.println("   silver.getClass() = "+silver.getClass());
      out.println("   silver.getDeclaringClass() = "
         +silver.getDeclaringClass());

      out.println("Base static methods:");
      out.println("   Enum.valueOf() = "+Enum.valueOf(Rank.class, "GOLD"));
   }
}
```

If you compile and run EnumInheritedMethods.java, you should get:

```
 herong> java EnumInheritedMethods.java

Inherited instance methods:
   silver.name() = SILVER
   silver.toString() = SILVER
   silver.ordinal() = 1
   silver.compareTo() = 1
   silver.getClass() = class EnumInheritedMethods$Rank
   silver.getDeclaringClass() = class EnumInheritedMethods$Rank
Base static methods:
   Enum.valueOf() = GOLD
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Enum Types and Enum Constants](#part0062.xhtml)

∟Enum Constant Implicit Methods

This section describes 2 static methods implicitly added by the Java compiler to all enum types declared by the 'enum' statement.

When you define an enum type with an "enum" declaration statement, the Java compiler implicitly adds two static method in the resulting class.

1\. "public static E valueOf(String name)" - Returning the enum constant of this enum type with the specified name. This method is equivalent to the "public static E valueOf​(Class<E> enumType, String name)" static method defined in the base class java.lang.Enum<E>.

2\. "public static E[] values() " - Returning an array of this enum type containing all enum constants declared in this enum type.

Note that those implicit methods are not mentioned in JDK API documentation. You have to read the Java language specification to find them.

Here is a sample program that shows you how to invoke methods listed above:

```
 /* EnumImplicitMethods.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.lang.Enum;
class EnumImplicitMethods {
   enum Rank { GOLD, SILVER, BRONZE; }
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;
      out.println("Enum type implicit static methods:");
      out.println("   Rank.valueOf() = "+Rank.valueOf("GOLD"));
      out.println("   Rank.values() =");
      for (Rank r : Rank.values()) out.println("      "+r);
   }
}
```

If you compile and run EnumImplicitMethods.java, you should get:

```
 herong> java EnumImplicitMethods.java

Enum type implicit static methods:
   Rank.valueOf() = GOLD
   Rank.values() =
      GOLD
      SILVER
      BRONZE
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟StringBuffer - The String Buffer Class

This chapter describes the StringBuffer class included in the java.lang package. Topics include StringBuffer properties and methods, implementing a simple string buffer class, comparing performances of String and StringBuffer classes.

> [StringBuffer Class Properties and Methods](#part0070.xhtml)
> 
> [SimpleStringBuffer - My Implementation of String Buffer](#part0071.xhtml)
> 
> [Performance Comparison of String and StringBuffer](#part0072.xhtml)

Conclusion:

*   StringBuffer class allows you to manipulate text information more efficiently that String class.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[StringBuffer - The String Buffer Class](#part0069.xhtml)

∟StringBuffer Class Properties and Methods

This section describes the StringBuffer class, it properties and methods.

**java.lang.StringBuffer** - A class represents a mutable sequence of characters stored in an internal buffer. An instance of StringBuffer has 3 important properties:

*   **Buffer**: The storage where the characters are stored.
*   **Capacity**: The size of the storage.
*   **Length**: The number of characters stored in the buffer.

The sequence of characters in the buffer can be manipulated by the following methods:

*   append(): Adding more characters to the end of the sequence.
*   insert(): Inserting more characters at a given position of the sequence.
*   delete(): Removing some characters from the sequence.
*   replace(): Replacing some characters in the sequence.
*   reverse(): Reversing the positions of all characters in the sequence.
*   setLength(): Truncating the sequence or padding the sequence with '\u0000' to make the number of characters equal to the specified value.

The capacity, size of the buffer, may be affected by the following methods:

*   append(), insert(), and replace(): May cause the capacity to be increased, if the current capacity is not large enough to hold the increased number of characters.
*   setLength(): May cause the capacity to be increased, if the current capacity is smaller than the specified value.
*   ensureCapacity(): May cause the capacity to be increased, if the current capacity is smaller than the specified value.

Is there any method that could cause the capacity to be decreased? I don't see any.

Many methods in StringBuffer class return current object. This allows us to write multiple method calls in one statement like this:

```
 s = s.append("It's ").append{10).append(" o'clock.");
```

Based on the J2SDK API Specification, an instance of StringBuffer is used by the Sun Java compiler to implement the string concatenation operations. For example, the following statement:

```
 s = "It's " + 10 + " o'clock.";
```

will be compiled as:

```
 s = new StringBuffer().append("It's ").append(10)
      .append(" o'clock.").toString();
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[StringBuffer - The String Buffer Class](#part0069.xhtml)

∟SimpleStringBuffer - My Implementation of String Buffer

This section provides a tutorial example on how to implement a simple string buffer class similar to the StringBuffer class included in the java.lang package.

In order to better understand the StringBuffer class, I wrote the following program, SimpleStringBuffer, which implements a really simple string buffer class with only one append() method:

```
 /* SimpleStringBuffer.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class SimpleStringBuffer {
   private char[] buffer;
   private int capacity;
   private int length;
   public SimpleStringBuffer() {
      this(16);
   }
   public SimpleStringBuffer(int l) {
      capacity = l;
      buffer = new char[capacity];
      length = 0;
   }
   public synchronized SimpleStringBuffer append(String str) {
      String s = str;
      if (s==null) s = "null";
      if (length+s.length()>capacity) {
         int l = Math.max(length+s.length(), 2*capacity);
         char[] b = new char[l];
         for (int i=0; i<length; i++) {
            b[i] = buffer[i];
         }
         buffer = b;
         capacity = l;
      }
      for (int i=0; i<s.length(); i++) {
         buffer[length+i] = s.charAt(i);
      }
      length += s.length();
      return this;
   }
   public String toString() {
      return new String(buffer, 0, length);
   }
```

Several notes on this class:

*   I used a character array "char[]" as the storage for the string buffer.
*   Two constructor methods are provided: one takes the default buffer capacity of 16 characters, and the other allows the caller to specify a specific capacity.
*   The main method is append(), which appends the specified string to the end of the buffer.
*   If there are not enough free spaces in the buffer to append the specified string, the buffer will be extended with a higher capacity.

See the next section for testing result of this class.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[StringBuffer - The String Buffer Class](#part0069.xhtml)

∟Performance Comparison of String and StringBuffer

This section provides a tutorial example to do a performance comparison of 3 classes: String, StringBuffer, SimpleStringBuffer.

One main reason of using the StringBuffer class instead of the String class is that StringBuffer performs much better in joining strings together. In order to confirm this, I wrote the following tutorial example to compare performances of 3 classes: String, StringBuffer, and SimpleStringBuffer:

```
 /* StringBufferTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class StringBufferTest {
   public static void main(String[] args) {
      int l = 128;
      long t1 = 0;
      long t2 = 0;
      String s = null;
      System.out.println("Initial capacity = "+l);
      for (int i=1; i<=3; i++) {
         System.out.println("Test: "+i);
         t1 = System.currentTimeMillis();
         if (i==1) s = stringTest(l);
         else if (i==2) s = stringBufferTest(l);
         else if (i==3) s = simpleStringBufferTest(l);
         t2 = System.currentTimeMillis();
         System.out.println("   Final string = "+s);
         System.out.println("   Total time = "+(t2-t1));
      }
   }
   public static String stringTest(int l) {
      String s = null;
      for (int i=0; i<100000; i++) {
         String sb = "0";
         sb = sb+"01";
         sb = sb+"012";
         sb = sb+"0123";
         sb = sb+"01234";
         sb = sb+"012345";
         sb = sb+"0123456";
         sb = sb+"01234567";
         sb = sb+"012345678";
         sb = sb+"0123456789";
         s = sb;
      }
      return s;
   }
   public static String stringBufferTest(int l) {
      String s = null;
      for (int i=0; i<100000; i++) {
         StringBuffer sb = new StringBuffer(l);
         sb = sb.append("0");
         sb = sb.append("01");
         sb = sb.append("012");
         sb = sb.append("0123");
         sb = sb.append("01234");
         sb = sb.append("012345");
         sb = sb.append("0123456");
         sb = sb.append("01234567");
         sb = sb.append("012345678");
         sb = sb.append("0123456789");
         s = sb.toString();
      }
      return s;
   }
   public static String simpleStringBufferTest(int l) {
      String s = null;
      for (int i=0; i<100000; i++) {
         SimpleStringBuffer sb = new SimpleStringBuffer(l);
         sb = sb.append("0");
         sb = sb.append("01");
         sb = sb.append("012");
         sb = sb.append("0123");
         sb = sb.append("01234");
         sb = sb.append("012345");
         sb = sb.append("0123456");
         sb = sb.append("01234567");
         sb = sb.append("012345678");
         sb = sb.append("0123456789");
         s = sb.toString();
      }
      return s;
   }
}
```

I compiled and ran the program with JDK 13\. Here is the result:

```
 Initial capacity         128

StringTest               187
StringBufferTest          47
SimpleStringBufferTest    78
```

Below is the result with JDK 8 on an older computer:

```
 Initial capacity         128

StringTest               132
StringBufferTest          49
SimpleStringBufferTest    47
```

Below is the result with JDK 1.4 on an older computer:

```
 Initial capacity           16     32     64    128

StringTest               1973   1963   1963   1963
StringBufferTest          631    571    500    551
SimpleStringBufferTest    671    611    521    630
```

The result shows that:

*   The StringBuffer class does perform much better than the String class. The StringBuffer is about 3 times faster!
*   The SimpleStringBuffer class, my implementation of a string buffer class, performs almost the same as the StringBuffer class!

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟System Properties and Runtime Object Methods

This chapter provides tutorial notes and tutorial examples on system properties and the Runtime object. Topics include listing all system properties, setting your own properties, accessing the Runtime object, checking free memory, executing OS commands.

> [JVM and OS System Properties](#part0074.xhtml)
> 
> [System.setProperty() - Setting Your Own Properties](#part0075.xhtml)
> 
> [Runtime.getRuntime() - Getting the Runtime Object](#part0076.xhtml)
> 
> [freeMemory() - Getting JVM Free Memory Information](#part0077.xhtml)
> 
> [Calculating Memory Usage of an Array](#part0078.xhtml)
> 
> [exec() - Executing Operating System Commands](#part0079.xhtml)

Conclusion:

*   Java Virtual Machine (JVM) and Operating System (OS) properties can retrieved through the System class.
*   Applications can interact with Java Virtual Machine (JVM) through the Runtime class.
*   Runtime.getMemoryInfo() allows you to retrieve application memory usage information.
*   Runtime.exec() allows you to launch a new process in the Operating System (OS).

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[System Properties and Runtime Object Methods](#part0073.xhtml)

∟JVM and OS System Properties

This section provides a tutorial example on how to list all properties from the JVM and the OS that are accessible by your Java application.

Java application programs are executed inside a Java Virtual Machine (JVM), which is in turn executed inside an Operating System (OS). From the Java application program point of view, the JVM, together with the OS, represents the computer system. The properties of the JVM and the OS are all called system properties.

A Java application program can:

*   Use System.getProperty(String propertyName) to get the value of a specific system property.
*   Use System.getProperties() to get all available system properties.

Here is an example program that displays the values of all available system properties:

```
 /* SysProperties.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
public class SysProperties {
   public static void main(String[] a) {
      Properties sysProps = System.getProperties();
      sysProps.list(System.out);
   }
}
```

Output:

```
 -- listing properties --
java.specification.version=17
sun.cpu.isalist=amd64
sun.jnu.encoding=Cp1252
java.class.path=.
java.vm.vendor=Oracle Corporation
sun.arch.data.model=64
user.variant=
java.vendor.url=https://java.oracle.com/
java.vm.specification.version=17
os.name=Windows 10
sun.java.launcher=SUN_STANDARD
user.country=US
sun.boot.library.path=C:\Progra~1\java\jdk-17.0.1\bin
sun.java.command=jdk.compiler/com.sun.tools.javac.laun...
jdk.debug=release
sun.cpu.endian=little
user.home=C:\Users\herong
user.language=en
sun.stderr.encoding=ms936
java.specification.vendor=Oracle Corporation
java.version.date=2021-10-19
java.home=C:\Progra~1\java\jdk-17.0.1
file.separator=\
java.vm.compressedOopsMode=32-bit
line.separator=

sun.stdout.encoding=ms936
java.vm.specification.vendor=Oracle Corporation
java.specification.name=Java Platform API Specification
jdk.module.main.class=com.sun.tools.javac.launcher.Main
user.script=
sun.management.compiler=HotSpot 64-Bit Tiered Compilers
java.runtime.version=17.0.1+12-LTS-39
user.name=herong

jdk.launcher.sourcefile=C:\herong\SysProperties.java
path.separator=;
os.version=10.0
java.runtime.name=Java(TM) SE Runtime Environment
file.encoding=Cp1252
java.vm.name=Java HotSpot(TM) 64-Bit Server VM
java.vendor.url.bug=https://bugreport.java.com/bugreport/
java.io.tmpdir=C:\Users\herong\AppData\Local\Temp\
java.version=17.0.1
user.dir=C:\herong
os.arch=amd64
java.vm.specification.name=Java Virtual Machine Specification
sun.os.patch.level=
native.encoding=Cp1252
java.library.path=C:\Progra~1\java\jdk-17.0.1\bin;C:\Wi...
java.vm.info=mixed mode, sharing
java.vendor=Oracle Corporation
java.vm.version=17.0.1+12-LTS-39
sun.io.unicode.encoding=UnicodeLittle
java.class.version=61.0
```

Note that:

*   The value of property "line.separator" contains a new line character '\n', which produces a blank line on the output window.
*   The Properties.list() truncates values after 37 characters while sending them to the output stream.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[System Properties and Runtime Object Methods](#part0073.xhtml)

∟System.setProperty() - Setting Your Own Properties

This section provides a tutorial example on how to modify system properties provided by the JVM, and set your own properties into the system property map.

The system properties are actually stored in a map structure, which can also be used by your application program to store your own properties. For example, the following program stores two non-system properties at the beginning, and uses them later in the program:

```
 /* PropertyTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class PropertyTest {
   public static void main(String[] a) {
      setProgramInfo();
      printMessage();
   }
   public static void setProgramInfo() {
      // Modifying a system property
      System.setProperty("java.io.tmpdir","c:\\var\\tmp");
      // Adding my own properties
      System.setProperty("program.name","Property Test");
      System.setProperty("program.version","3.01");
   }
   public static void printMessage() {
      String userName = System.getProperty("user.name");
      String programName = System.getProperty("program.name");
      String programVersion = System.getProperty("program.version");
      String ioTempDir = System.getProperty("java.io.tmpdir");
      System.out.println("Hello "+userName+",");
      System.out.println("");
      System.out.println("Welcome to \""+programName+", "
         +programVersion+"\".");
      System.out.println("Note that the Java I/O "
         +" temporary directory is located at "+ioTempDir+".");
   }
}
```

Output:

```
 Hello herong,

Welcome to "Property Test, 3.01".
Note that the Java I/O  temporary directory is located at c:\var\tmp.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[System Properties and Runtime Object Methods](#part0073.xhtml)

∟Runtime.getRuntime() - Getting the Runtime Object

This section describes the system Runtime object and the Runtime.getRuntime() method to get it from the JVM.

When a Java application program is running inside a JVM, the JVM offers an instance of the Runtime class to the program. The Java program can use this Runtime instance to interact with the JVM and the supporting operating system.

There are several interesting types of methods available on the Runtime instance:

*   Getting dynamic information about the JVM, like freeMemory().
*   Launching a separate process at the operating system level, like exec().
*   Interacting with the shutdown sequence of the JVM, like addShutdownHook().
*   Forcing an immediate garbage collection job on the JVM, like gc().

The Runtime class is a special class. It represents the run time environment of the Java application program running inside the JVM. You can not create a new instance of Runtime class in your application program. You can only get the instance created by the JVM for your application program by calling the Runtime.getRuntime() method.

So, the following code is wrong:

```
 Runtime rt = new Runtime();
   rt.gc();
```

The following code is correct:

```
 Runtime rt = Runtime.getRuntime();
   rt.gc();
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[System Properties and Runtime Object Methods](#part0073.xhtml)

∟freeMemory() - Getting JVM Free Memory Information

This section provides a tutorial example on how to use freeMemory(), totalMemory(), and maxMemory() of the Runtime class to get JVM total and free memory information.

There a couple of values used in Java related to memory management:

*   **Free Memory**: Number of bytes available for the application program.
*   **Total Memory**: Number of total bytes allocated to the application program.
*   **Maximum Memory**: Maximum number of bytes that can be allocated to the application program.

There is one method in the Runtime class that you can use to get the each of those values. Here is a program showing you how to use those methods properly:

```
 /* FreeMemory.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class FreeMemory {
   private static long[] fm = new long[5];
   private static long[] tm = new long[5];
   private static long[] mm = new long[5];
   private static long[] um = new long[5];
   public static void main(String[] a) {
      Runtime rt = Runtime.getRuntime();
      getMemoryInfo(rt,0);
      getMemoryInfo(rt,1);
      getMemoryInfo(rt,2);
      getMemoryInfo(rt,3);
      getMemoryInfo(rt,4);
      printMemoryInfo(rt,0);
      printMemoryInfo(rt,1);
      printMemoryInfo(rt,2);
      printMemoryInfo(rt,3);
      printMemoryInfo(rt,4);
      for (int i=0; i<5; i++) {
         System.out.println("Get memory info - step = "+i);
         System.out.println("   Free memory = "+fm[i]);
         System.out.println("   Total memory = "+tm[i]);
         System.out.println("   Maximum memory = "+mm[i]);
         System.out.println("   Memory used = "+um[i]);
      }
   }
   public static void getMemoryInfo(Runtime rt, int i) {
      fm[i] = rt.freeMemory();
      tm[i] = rt.totalMemory();
      mm[i] = rt.maxMemory();
      um[i] = tm[i]-fm[i];
   }
   public static void printMemoryInfo(Runtime rt, int i) {
      long fm = rt.freeMemory();
      long tm = rt.totalMemory();
      long mm = rt.maxMemory();
      System.out.println("Print memory info - step = "+i);
      System.out.println("   Free memory = "+fm);
      System.out.println("   Total memory = "+tm);
      System.out.println("   Maximum memory = "+mm);
      System.out.println("   Memory used = "+(tm-fm));
   }
}
```

This program seems to be confusing:

*   Why do I need two different methods to retrieve the memory information?
*   Why are the methods called repeatedly 5 times?
*   Why are the printing statements for the getMemoryInfo() method not following the method call statements immediately?

You need to read the output of this program to answer those questions:

```
 Print memory info - step = 0
   Free memory = 1777568
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254048
Print memory info - step = 1
   Free memory = 1774712
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 256904
Print memory info - step = 2
   Free memory = 1772496
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 259120
Print memory info - step = 3
   Free memory = 1770280
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 261336
Print memory info - step = 4
   Free memory = 1768064
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 263552
Get memory info - step = 0
   Free memory = 1777568
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254048
Get memory info - step = 1
   Free memory = 1777568
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254048
Get memory info - step = 2
   Free memory = 1777568
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254048
Get memory info - step = 3
   Free memory = 1777568
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254048
Get memory info - step = 4
   Free memory = 1777568
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254048
```

Note that:

*   The difference between the getMemoryInfo() method and printMemoryInfo() method is that the getMemoryInfo() method saves the memory usage into arrays, while printMemoryInfo() method prints the memory usage values on the console. This is to show the impact of the printing statements, System.out.println(), on the memory usage.
*   Calling the methods repeatedly is to see if there are any thread other than the application program thread running that might affect the memory usage. As you can see from the output, the memory usage was un-changed during the 5 calls to getMemoryInfo(). However, after each call to printMemoryInfo(), the free memory decreased by more than 2000 bytes. This suggests that the System.out.println() method was leaving dead objects in memory for the garbage collector to remove them.
*   Calling the getMemoryInfo() at the beginning and putting the related printing statements at the end is to avoid any impact of printing statements on the printMemoryInfo() calls.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[System Properties and Runtime Object Methods](#part0073.xhtml)

∟Calculating Memory Usage of an Array

This section provides a tutorial example on how to calculate memory usage of a large array.

The memory information provided by the JVM can be used to calculate the memory usage of data objects used in the application program. In the following program, I tried to calculate the memory usage of an array:

```
 /* MemoryUsage.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class MemoryUsage {
   private static long[] fm = new long[2];
   private static long[] tm = new long[2];
   private static long[] mm = new long[2];
   private static long[] um = new long[2];
   public static void main(String[] a) {
      Runtime rt = Runtime.getRuntime();
      getMemoryInfo(rt,0);
      long[] la = null;
      long s = allocateLongArray(la);
      getMemoryInfo(rt,1);
      System.out.println("Memory usage before array allocation:");
      System.out.println("   Free memory = "+fm[0]);
      System.out.println("   Total memory = "+tm[0]);
      System.out.println("   Maximum memory = "+mm[0]);
      System.out.println("   Memory used = "+um[0]);
      System.out.println("Memory usage after array allocation:");
      System.out.println("   Free memory = "+fm[1]);
      System.out.println("   Total memory = "+tm[1]);
      System.out.println("   Maximum memory = "+mm[1]);
      System.out.println("   Memory used = "+um[1]);
      System.out.println("Memory usage summary:");
      System.out.println("   Allocated to the array = "+s);
      System.out.println("   Memory usage increase = "+(um[1]-um[0]));
      System.out.println("   Overhead of single array = "
         +(um[1]-um[0]-s));
   }
   public static void getMemoryInfo(Runtime rt, int i) {
      fm[i] = rt.freeMemory();
      tm[i] = rt.totalMemory();
      mm[i] = rt.maxMemory();
      um[i] = tm[i]-fm[i];
   }
   public static long getMemoryInfo(Runtime rt) {
      //rt.gc();
      System.out.println("Getting JVM memory information...");
      long fm = rt.freeMemory();
      long tm = rt.totalMemory();
      long mm = rt.maxMemory();
      System.out.println("   Free memory = "+fm);
      System.out.println("   Total memory = "+tm);
      System.out.println("   Maximum memory = "+mm);
      System.out.println("   Memory used = "+(tm-fm));
      return tm-fm;
   }
   public static long allocateLongArray(long[] la) {
      int s = 2*128*1024;
      la = new long[s]; // 2 MB needed for this array
      return 8*s;
   }
}
```

Output:

```
 Memory usage before array allocation:
   Free memory = 1777248
   Total memory = 2031616
   Maximum memory = 134217728
   Memory used = 254368
Memory usage after array allocation:
   Free memory = 1897280
   Total memory = 4132864
   Maximum memory = 134217728
   Memory used = 2235584
Memory usage summary:
   Allocated to the array = 2097152
   Memory usage increase = 1981216
   Overhead of single array = -115936
```

The output was very surprising. An array for storing 2097152 bytes (2MB) of data was allocated. But the memory usage was increased by only 1981216 bytes. Somehow the JVM freed up some memory during the array allocation process.

If you look closely on the values of total memory before and after the array allocation, you can see that the JVM had requested an additional 2MB of memory from the operating system into order to have enough memory to give to the array. My guess is that the expansion of total memory triggered a garbage collection call, which removed some un-used objects in the JVM.

One way to avoid the total memory expansion is to invoke the JVM with a starting total memory of 4MB, using the following command:

```
 herong> java -Xms4m MemoryUsage
```

Output:

```
 Memory usage before array allocation:
   Free memory = 3874400
   Total memory = 4128768
   Maximum memory = 134217728
   Memory used = 254368
Memory usage after array allocation:
   Free memory = 1777232
   Total memory = 4128768
   Maximum memory = 134217728
   Memory used = 2351536
Memory usage summary:
   Allocated to the array = 2097152
   Memory usage increase = 2097168
   Overhead of single array = 16
```

This time the program worked as I expected. The memory usage increased 16 bytes more than the number of bytes needed to store the data elements of the array. So the 16 bytes is the overhead cost of memory for a one-dimension array. It is used to store the size of the array and other information about the array.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[System Properties and Runtime Object Methods](#part0073.xhtml)

∟exec() - Executing Operating System Commands

This section provides a tutorial example on how to calculate memory usage of a large array.

The Runtime instance also offers methods for the Java application program to execute an operating system command as a subprocess. The following program uses the exec() method to execute "chkdsk" command:

```
 /* CheckDisk.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.io.*;
public class CheckDisk {
   private static String cmd = "C:\\Windows\\System32\\chkdsk f:";
   public static void main(String[] a) {
      Runtime rt = Runtime.getRuntime();
      try {
         Process p = rt.exec(cmd);
         Reader in = new InputStreamReader(p.getInputStream());
         int c = in.read();
         while (c!=-1) {
            System.out.print((char)c);
            c = in.read();
         }
      } catch (IOException e) {
         System.out.println(e.toString());
      }
   }
}
```

Note that the program assumes that you have a storage device connected as drive F:.

Output:

```
 The type of the file system is FAT.
Volume UDISK 2.0 created 6/8/2018 10:10 PM
Windows is verifying files and folders...
File and folder verification is complete.
Windows has checked the file system and found no problems.

  259,756,032 bytes total disk space.
       16,384 bytes in 4 folders.
    9,371,648 bytes in 15 files.
  250,368,000 bytes available on disk.

        4,096 bytes in each allocation unit.
       63,417 total allocation units on disk.
       61,125 allocation units available on disk.
```

Note that how the output of the subprocess captured and reprinted on the JVM console.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Generic Classes and Parameterized Types

This chapter provides tutorial notes and example codes on generic classes and parameterized types. Topics include what is a generic class; what is a type parameter; using parameterized types and subtyping; using wildcard parameterized types and subtyping.

> [What Is a Generic Class](#part0081.xhtml)
> 
> [Using a Generic Class](#part0082.xhtml)
> 
> [Using a Generic Class - Example](#part0083.xhtml)
> 
> [Creating a Generic Class](#part0084.xhtml)
> 
> [Creating a Generic Class - Example](#part0085.xhtml)
> 
> [Bounded Type Parameters](#part0086.xhtml)
> 
> [Raw Type, Generic Type and Parameterized Type](#part0087.xhtml)
> 
> [Parameterized Type and Subtyping](#part0088.xhtml)
> 
> [Wildcard Parameterized Types](#part0089.xhtml)
> 
> [Wildcard Parameterized Type Test](#part0090.xhtml)
> 
> [Wildcard Parameterized Subtyping](#part0091.xhtml)
> 
> [Wildcard Parameterized Subtyping Example](#part0092.xhtml)

Conclusion:

*   A generic class is a class that supports type parameters with different behaviors when given different types on invocation.
*   A generic class has a signature of ClassName<A, B, C, ...>.
*   Type parameters can be bounded as ClassName<T extends C & I1 & I2...> to ensure strong typing to reduce runtime type mismatches.
*   A parameterized type is a reference type for generic class objects with argument types provided.
*   Subtyping of parameterized types is based on their generic class hierarchy, like class Hashtable<K,V> extends Dictionary<K,V>.
*   Raw types for generic types introduced in JDK 1.5 are supported for backward compatibility.
*   A wildcard parameterized type is a parameterized type with argument types containing wildcards for subtyping purposes.
*   There 3 categories of wildcard parameterized types: unbounded, upper bounded and lower bounded.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟What Is a Generic Class

This section describes what is a generic class, a class that supports one or more type parameters. When a specific type value is given, a generic class becomes a normal 'specific' class.

**What Is a Generic Class?** A generic class is a class that supports one or more type parameters. When invoked with a given type argument, a generic class becomes a parameterized class.

A generic class uses a type parameter to make it more generic so that it can be used as multiple variations, one variation for each specific type given to the type parameter.

For example, java.util.Stack<E> is a generic class. It supports a single type parameter E. java.util.Stack<E> can be viewed as multiple classes when used with E parameterized to different reference types. Each of them is a variation of java.util.Stack<E>:

*   java.util.Stack<Object> - A class representing a stack of Object objects.
*   java.util.Stack<String> - A class representing a stack of String objects.
*   java.util.Stack<Integer> - A class representing a stack of Integer objects.
*   java.util.Stack<Runnable> - A class representing a stack of Runnable objects.
*   java.util.Stack<double[]> - A class representing a stack of double[] objects.
*   ...

When a generic class is used with a given specific type, Behaviors of its methods will change accordingly.

For example, if java.util.Stack<Integer> is used, its method "public E push(E item)" will become "public Integer push(Integer item)".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Using a Generic Class

This section describes 4 basic areas that require attention with using a generic class: calling the constructor, declaring a reference variable, passing an argument to methods and handling the returning reference from methods.

When using a generic class, you need to pay attention to 4 basic areas:

1\. Calling the constructor of a generic class - When calling a constructor of a generic class, you need to provide a specific type to the type parameter enclosed in angle brackets after the class name. Examples are listed below:

```
 new java.util.Stack<double[]>();
   new java.util.ArrayList<String>();
   new java.util.Vector<Number>(200);
```

2\. Declaring a variable for a generic class type - When declaring a variable for a generic class type, you need to provide a specific type to the type parameter enclosed in angle brackets after the class name. Examples are listed below:

```
 java.util.Stack<double[]> stackForDoubleArray;
   java.util.ArrayList<String> arrayListForString;
   java.util.Vector<Number> vectorForNumber;
```

3\. Passing an argument to a method that uses the type parameter - When calling a method in a generic class that uses a type parameter as an argument, you need to pass a reference that is compatible with the specific type provided to the generic class. Examples are listed below for the method "boolean add(E e)" in the class "java.util.Vector<E>":

```
 java.util.Vector<Number> verctorForNumber;
   ...
   vectorForNumber.add(new Double(9.99));
      // allowed - Double is compatible with Number

   vectorForNumber.add(new String("9.99"));
      // not allowed - String is not compatible with Number
```

4\. Receiving return reference from a method that uses the type parameter - When receiving a reference from a method in a generic class that uses a type parameter as the return value, you need to handle it as the specific type provided to the generic class. Examples are listed below for the method "E firstElement()" in the class "java.util.Vector<E>":

```
 java.util.Vector<Number> verctorForNumber;
   ...
   Object firstTry = vectorForNumber.firstElement();
      // allowed - Return type Number can be up casted to Object

   Double secondTry = vectorForNumber.firstElement();
      // not allowed - Double is not compatible with Number
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Using a Generic Class - Example

This section provides a tutorial example on using a generic class in 4 areas: calling the constructor, declaring a reference variable, passing an argument to methods and handling the returning reference from methods.

Let's see a tutorial example program that uses generic classes provided as part of JDK:

```
 /* UsingGenericClass.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class UsingGenericClass {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;

      // calling constructors
      new java.util.Stack<double[]>();
      new java.util.ArrayList<String>();
      new java.util.Vector<Number>(200);

      // declaring reference variables
      java.util.Stack<double[]> stackForDoubleArray;
      java.util.ArrayList<String> arrayListForString;
      java.util.Vector<Number> vectorForNumber;

      vectorForNumber = new java.util.Vector<Number>(200);

      // passing arguments
      vectorForNumber.add(Double.valueOf(9.99));
         // allowed - Double is compatible with Number

      // vectorForNumber.add(new String("9.99"));
         // not allowed - String is not compatible with Number

      // receiving returns
      Object firstTry = vectorForNumber.firstElement();
         // allowed - Return type Number can be up casted to Object

      // Double secondTry = vectorForNumber.firstElement();
         // not allowed - Double is not compatible with Number

      o.println("First element: "+(Number) firstTry);
   }
}
```

Compile and run the example, you will get:

```
 First element: 9.99
```

The output proves that I used generic classes correctly in the example program. Now if you uncomment those 2 not allowed statements, you should see 2 compilation errors.

Compilation error messages from JDK 10:

```
 UsingGenericClass.java:25: error: incompatible types: String cannot be
  converted to Number
      vectorForNumber.add(new String("9.99"));
                          ^
UsingGenericClass.java:32: error: incompatible types: Number cannot be
  converted
      Double secondTry = vectorForNumber.firstElement();

Note: Some messages have been simplified; recompile with -Xdiags:verbose 
  to get full output                                        ^
2 errors
```

Compilation error messages from JDK 8:

```
 UsingGenericClass.java:25: error: no suitable method found for
   add(String)
      vectorForNumber.add(new String("9.99"));
                     ^
    method Collection.add(Number) is not applicable
      (argument mismatch; String cannot be converted to Number)
    method List.add(Number) is not applicable
      (argument mismatch; String cannot be converted to Number)
    method AbstractCollection.add(Number) is not applicable
      (argument mismatch; String cannot be converted to Number)
    method AbstractList.add(Number) is not applicable
      (argument mismatch; String cannot be converted to Number)
    method Vector.add(Number) is not applicable
      (argument mismatch; String cannot be converted to Number)

UsingGenericClass.java:32: error: incompatible types: Number cannot
   be converted to Double
      Double secondTry = vectorForNumber.firstElement();
                                                     ^
Note: Some messages have been simplified; recompile with
   -Xdiags:verbose to get full output
2 errors
```

The first error says that the parameterized class represented by vectorForNumber supports "add(Number)" method. But error statement tries to invoke it with "add(String)".

The second error says that the parameterized class represented by vectorForNumber supports "Number firstElement()" method. But error statement tries to cast the returning type "Number" to "Double".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Creating a Generic Class

This section describes how to create a generic class by declaring type parameters and using them as 'Type Variable' types within the scope of the class.

When creating a generic class, you need to know how to declare a type parameter and how to use it as a "Type Variable" type:

1\. Declaring type parameters - When declaring a generic class, you need to provide type parameter enclosed in angle brackets after the class name. Examples are listed below:

```
 class ObjectRegistry<T> {}
   class HashMap<K,V> {}
```

2\. Using the type parameter - When a type parameter is declared, it becomes a "Type Variable" reference type that can be used within the scope of the class. Examples are listed below:

```
 class ObjectRegistry<T> {
   public void register(T item) {}
}

class Box<T> {
    private T t;
    public void set(T t) { this.t = t; }
    public T get() { return t; }
}
```

In the example above, "T" becomes a special reference type called "Type Variable" type which is used to declare local variables like "t".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Creating a Generic Class - Example

This section provides a tutorial example on creating a generic class by declaring type parameters and using them as 'Type Variable' types within the scope of the class.

Here is an example program that creates a generic class with a single type parameter:

```
 /* ObjectRegister.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class ObjectRegister<T> {
   private HashSet<T> pool;

   // Constructor
   public ObjectRegister() {
      pool = new HashSet<T>();
   }
   // Registering T objects
   public void register(T item) {
      pool.add(item);
   }
   // Returning the size
   public long size() {
      return pool.size();
   }
   // Testing the class
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;
      ObjectRegister<String> reg = new ObjectRegister<String>();
      reg.register(new String("Java"));
      reg.register(new String("C++"));
      reg.register(new String("PHP"));
      o.println("# of objects registered: "+reg.size());
   }
}
```

Compile and run the example, you will get:

```
 # of objects registered: 3
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Bounded Type Parameters

This section provides a tutorial example on creating a generic class with a bounded type parameter so that only certain types are allowed for the type parameter.

**What Is a Bounded Type Parameter?** A bounded type parameter is type parameter that can be parameterized only with certain limited types. This limitation on type parameters allow you to create generic classes to offer special functions to those limited types.

The syntax to declare a bounded type parameters is to add the keyword "extends" with one or more base types. Examples are listed below:

```
 class Name<T extends C> {}
class Name<T extends I> {}
class Name<T extends I1 & I2...> {}
class Name<T extends C & I1 & I2...> {}
```

Here is a tutorial example that shows you how to create a generic class with a bounded type parameter:

```
 /* AddRegister.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class AddRegister<T extends Number> {
   private double sum;

   public AddRegister() {
      sum = 0.0;
   }

   public void add(T item) {
      sum += item.doubleValue();
   }

   public double getSum() {
      return sum;
   }

   public static void main(String[] a) {
      java.io.PrintStream o = System.out;
      AddRegister<Float> reg = new AddRegister<Float>();
      reg.add(Float.valueOf("99.99"));
      reg.add(Float.valueOf(" 6.50"));
      reg.add(Float.valueOf("11.99"));
      o.println("Total price: "+reg.getSum());

      // not allowed - Wrong type is given the type parameter
      // AddRegister<String> test = new AddRegister<String>();
   }
}
```

The example runs ok. See the output below:

```
 Total price: 118.4799976348877
```

If you uncomment the not allowed line in the example, you will get a compilation error:

```
 AddRegister.java:28: error: type argument String is not within bounds
   of type-variable T
      AddRegister<String> test = new AddRegister<String>();
                  ^
  where T is a type-variable:
    T extends Number declared in class AddRegister
AddRegister.java:28: error: type argument String is not within bounds
   of type-variable T
      AddRegister<String> test = new AddRegister<String>();
                                                 ^
  where T is a type-variable:
    T extends Number declared in class AddRegister
2 errors
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Raw Type, Generic Type and Parameterized Type

This section provides a tutorial example on how legacy applications can continue to use raw types instead of parameterized types. But compiler will give you 'unchecked or unsafe operations' warnings.

**What Is a Generic Type?** A generic type is a generic class or interface that uses type parameters.

**What Is a Parameterized Type?** A parameterized type is a parameterized version of a generic class or interface. For example, Vector<String> is a parameterized type.

**What Is a Raw Type?** A raw type is a parameterized type with the parameter type argument omitted. For example, Vector is raw type.

Raw types are supported in Java to keep legacy applications working. In most cases, a raw type is equivalent a parameterized type with "Object" as the type argument.

Here is a legacy example that still uses a raw type of the Vector<E> generic class.

```
 /* RawTypeTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class RawTypeTest {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;

      Vector myList = new Vector();
      myList.add(new String("Milk"));
      myList.add(Float.valueOf("3.99"));

      String name = (String) myList.get(0);
      Float price = (Float) myList.get(1);
      o.println(name+": "+price);
   }
}
```

Compile and run this example. You will get:

```
 herong> javac RawTypeTest.java

Note: RawTypeTest.java uses unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.

herong> java RawTypeTest
Milk: 3.99
```

As you can see, the compiler let you to use raw types. But it gives you the "unchecked or unsafe operations" warning. If you recompile it with the "-Xlint", you will see more details:

```
 herong> javac -Xlint RawTypeTest.java

RawTypeTest.java:9: warning: [rawtypes] found raw type: Vector
      Vector myList = new Vector();
      ^
  missing type arguments for generic class Vector<E>
  where E is a type-variable:
    E extends Object declared in class Vector
RawTypeTest.java:9: warning: [rawtypes] found raw type: Vector
      Vector myList = new Vector();
                          ^
  missing type arguments for generic class Vector<E>
  where E is a type-variable:
    E extends Object declared in class Vector
RawTypeTest.java:10: warning: [unchecked] unchecked call to add(E) as
a member of the raw type Vector
      myList.add(new String("Milk"));
                ^
  where E is a type-variable:
    E extends Object declared in class Vector
RawTypeTest.java:11: warning: [unchecked] unchecked call to add(E) as
a member of the raw type Vector
      myList.add(Float.valueOf("3.99"));
                ^
  where E is a type-variable:
    E extends Object declared in class Vector
4 warnings
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Parameterized Type and Subtyping

This section describes supertype-subtype relationships with parameterized types derived from generic classes or interfaces.

Parameterized types derived a generic type can also form supertype-subtype relations with other reference types based on following rules:

1\. If two generic classes or interfaces have a supertype-subtype relationship, their parameterized types also have supertype-subtype relationships if both are using the same argument type. For example:

```
 // Generic class declared as
   class LinkedHashSet<E> extends HashSet<E> {}

   // Valid supertype-subtype relation
   // supertype: HashSet<Integer>
   // subtype: LinkedHashSet<Integer>
```

2\. If a generic class or interface is parameterized with 2 different argument types, resulting parameterized types do not a supertype-subtype relationship, even those 2 argument types have a supertype-subtype relationship. For example:

```
 // Generic class declared as
   class ObjectRegister<E> {}

   // Invalid supertype-subtype relation
   // supertype: ObjectRegister<Number>
   // subtype: ObjectRegister<Integer>
```

The diagram below shows you some examples of supertype-subtype relationships of parameterized types:

![](Images/image00182.jpeg)

Java Parameterized Type Subtyping

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Wildcard Parameterized Types

This section describes wildcard parameterized types where a argument type contains the wildcard character '?' and represents a group of types instead of a single type.

**What Is a Wildcard Parameterized Type?** A wildcard parameterized type is a parameterized type of a generic class or interface, where the argument type represents a group of types, instead of a single type.

The objective of using a wildcard parameterized type is to create a new parameterized type that is wider than a normal parameterized type, so that you can use it a supertype of the normal parameterized type. Here is some examples of wildcard parameterized type:

```
 java.util.List<?> a;
   java.util.List<? extends Number> b;
   java.util.List<? extends Integer> c;
   java.util.List<? super Integer> d;
```

Wildcard parameterized types can be divided into 3 groups:

*   Unbounded Wildcard Parameterized Type with a syntax of <?> creates a supertype of all other parameterized types of the same generic class. For example, java.util.List<?> is a supertype of java.util.List<Number>.
*   Upper Bounded Wildcard Parameterized Type with a syntax of <? extends T> creates a supertype of parameterized types with argument types narrower than T of the same generic class. For example, java.util.List<? extends Number> is a supertype of java.util.List<Integer>.
*   Lower Bounded Wildcard Parameterized Type with a syntax of <? super T> creates a supertype of parameterized types with argument types wider than T of the same generic class. For example, java.util.List<? super Integer> is a supertype of java.util.List<Number>.

The diagram below shows you some examples of supertype-subtype relationships of wildcard parameterized types and parameterized types:

![](Images/image00183.jpeg)

Java Wildcard Parameterized Type Subtyping

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Wildcard Parameterized Type Test

This section provides a tutorial example on how to declare variables using wildcard parameterized types.

The supertype-subtype relationships between wildcard parameterized types and parameterized types are confusing. So let's try a tutorial example:

```
 /* WildcardParameterizedType.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class WildcardParameterizedType {
   public static void main(String[] a) {

      // remember class Integer extends Number {}
      // allowed - implicit casting from subtype to supertype
      Vector<?> unbounded = new Vector<String>();
      Vector<? extends Number> upperBounded = new Vector<Integer>();
      Vector<? super Integer> lowerBounded = new Vector<Number>();

      unbounded = lowerBounded;
      System.out.println("Initial capacity: "+unbounded.capacity());

      // not allowed - compilation error
      // Vector<String> paramString = unbounded;
      // Vector<Integer> paramInteger = upperBounded;
      // Vector<Number> paramNumber = lowerBounded;
   }
}
```

If you compile and run this example as is, you will not see any issues.

But if you uncomment those not allowed lines, you will see these compilation errors with JDK 8:

```
 WildcardParameterizedType.java:18: error: incompatible types:
 Vector<CAP#1> cannot be converted to Vector<String>
      Vector<String> paramString = unbounded;
                                   ^
  where CAP#1 is a fresh type-variable:
   CAP#1 extends Object from capture of ?
WildcardParameterizedType.java:19: error: incompatible types:
 Vector<CAP#1> cannot be converted to Vector<Integer>
      Vector<Integer> paramInteger = upperBounded;
                                     ^
  where CAP#1 is a fresh type-variable:
   CAP#1 extends Number from capture of ? extends Number
WildcardParameterizedType.java:20: error: incompatible types:
 Vector<CAP#1> cannot be converted to Vector<Number>
      Vector<Number> paramNumber = lowerBounded;
                                   ^
  where CAP#1 is a fresh type-variable:
   CAP#1 extends Object super: Integer from capture of ? super Integer
3 errors
```

The compiler refuses to down cast the wildcard parameterized type back to the parameterized type. But you can try to do explicit down casting like Vector<Integer> paramInteger = (Vector<Integer>) upperBounded; The compiler will still give you "unchecked or unsafe operations" warnings.

Note that if you are using JDK 7, you will get slightly different error messages:

```
 WildcardParameterizedType.java:18: error: incompatible types
      Vector<String> paramString = unbounded;
                                   ^
  required: Vector<String>
  found:    Vector<CAP#1>
  where CAP#1 is a fresh type-variable:
   CAP#1 extends Object from capture of ?
WildcardParameterizedType.java:19: error: incompatible types
      Vector<Integer> paramInteger = upperBounded;
                                     ^
  required: Vector<Integer>
  found:    Vector<CAP#1>
  where CAP#1 is a fresh type-variable:
   CAP#1 extends Number from capture of ? extends Number
WildcardParameterizedType.java:20: error: incompatible types
      Vector<Number> paramNumber = lowerBounded;
                                   ^
  required: Vector<Number>
  found:    Vector<CAP#1>
  where CAP#1 is a fresh type-variable:
   CAP#1 extends Object super: Integer from capture of ? super Integer
3 errors
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Wildcard Parameterized Subtyping

This section describes subtyping rules on wildcard parameterized types. The unbounded wildcard parameterized type is the supertype of all others.

What's more confusing about wildcard parameterized types is that Wildcard parameterized types can also form supertype-subtype relationships with each others using these rules:

*   The unbounded wildcard parameterized type is a supertype of all other wildcard parameterized types from the same generic class. For example, java.util.List<?> is a supertype of java.util.List<? extends Number>.
*   An upper bounded wildcard parameterized type is a supertype of another upper bounded wildcard parameterized type from the same generic class if its bound type is a supertype of other's bound type. For example, java.util.List<? extends Number> is a supertype of java.util.List<? extends Integer>.
*   A lower bounded wildcard parameterized type is a supertype of another lower bounded wildcard parameterized type from the same generic class if its bound type is a subtype of other's bound type. For example, java.util.List<? super Integer> is a supertype of java.util.List<? suber Number>.

The following tutorial example may help you understand better those subtyping rules on wildcard parameterized types:

```
 /* WildcardParameterizedSubtyping.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class WildcardParameterizedSubtyping {
   public static void main(String[] a) {
      // remember class Integer extends Number {}

      // allowed - up casting in the upper bounded family
      Vector<? extends Integer> upperInteger = new Vector<Integer>();
      Vector<? extends Number> upperNumber = upperInteger;
      Vector<?> upperUnbounded = upperNumber;

      // allowed - up casting in the lower bounded family
      Vector<? super Number> lowerNumber = new Vector<Number>();
      Vector<? super Integer> lowerInteger = lowerNumber;
      Vector<?> lowerUnbounded = lowerInteger;

      System.out.println("Initial capacity: "+lowerUnbounded.capacity());

      // not allowed - compilation error
      // upperInteger = upperNumber;
      // lowerNumber = lowerInteger;
   }
}
```

If you are still confused, look at the picture below, which shows an example of how parameterized types and wildcard parameterized types are related to each other in the subtyping hierarchy:

![](Images/image00184.jpeg)

Java Wildcard Parameterized Subtyping Example

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Classes and Parameterized Types](#part0080.xhtml)

∟Wildcard Parameterized Subtyping Example

This section provides a tutorial example on wildcard parameterized subtyping using the putAll() method in the java.util.Hashtable class.

Let's see how wildcard parameterized types are used on JDK generic classes. Here is good example in the generic class, java.util.HashMap, as defined in JDK 1.7:

```
 package java.util;
class Hashtable<K,V> {
   ...
   void putAll(Map<? extends K,? extends V> t) {}
   ...
}
```

My understanding on putAll() definition is:

*   Two parameter types are defined at the class level: K and V, where K is served as the type for key objects and V as the type for value objects.
*   putAll(Map<? extends K,? extends V> t) means that the parameter t requires wildcard parameterized type of Map<? extends K,? extends V>.
*   If you create a new Hashtable<K,V> object and try to call putAll() dump key-value pair objects from a Map<S,T> object, the putAll(Map<? extends K,? extends V> t) declaration helps the compiler to ensure that those key-value pair objects are compatible with K and V.

The tutorial example below has no compilation errors, because objects provided in the putAll() meet the type requirements:

```
 /* HashtablePutAll.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
import java.awt.*;
import javax.swing.*;
class HashtablePutAll {
   public static void main(String[] a) {
      // Hashtable API:
      //    Class Hashtable<K,V> {
      //       void putAll(Map<? extends K,? extends V> t) {}
      //    }

      Hashtable<Number,Container> hashNumberContainer
         = new Hashtable<Number,Container>();

      // allowed - Integer extends Number & Box extends Container
      HashMap<Integer,Box> mapIntegerBox = new HashMap<Integer,Box>();
      mapIntegerBox.put(Integer.valueOf(777), new Box(BoxLayout.X_AXIS));
      hashNumberContainer.putAll(mapIntegerBox);
      System.out.println("# of entries: "+mapIntegerBox.size());

      // not allowed - Component does not extend from Container
      // HashMap<Number,Component> mapNumberComponent
      //   = new HashMap<Number,Component>();
      // hashNumberContainer.putAll(mapNumberComponent);
   }
}
```

But if you uncomment the not allowed lines in the example, you will get compilation errors:

```
 HashtablePutAll.java:26: error: no suitable method found for
   putAll(HashMap<Number,Component>)
       hashNumberContainer.putAll(mapNumberComponent);
                          ^
    method Map.putAll(Map<? extends Number,? extends Container>) is
    not applicable
      (argument mismatch; HashMap<Number,Component> cannot be
      converted to Map<? extends Number,? extends Container>)
    method Hashtable.putAll(Map<? extends Number,? extends Container>)
    is not applicable
      (argument mismatch; HashMap<Number,Component> cannot be
      converted to Map<? extends Number,? extends Container>)
1 error
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Generic Methods and Type Inference

This chapter provides tutorial notes and example codes on generic methods and type inference. Topics include what is a generic method; declaring type parameters; specifying type arguments; compiler performing type argument inference; using type parameter in parameterized types.

> [What Is a Generic Method](#part0094.xhtml)
> 
> [Comparing Generic Method with Non-Generic Method](#part0095.xhtml)
> 
> [Non-Generic Method Example - maxNonGeneric()](#part0096.xhtml)
> 
> [Generic Method Example - maxGeneric()](#part0097.xhtml)
> 
> [Generic Methods in java.util.Collections Class](#part0098.xhtml)
> 
> [Testing Generic Methods in Collections Class](#part0099.xhtml)
> 
> [What Is Type Argument Inference](#part0100.xhtml)
> 
> [Type Argument Inference by Parameter List](#part0101.xhtml)
> 
> [Type Argument Inference by Return Value](#part0102.xhtml)
> 
> [Generic Methods using Parameterized Types](#part0103.xhtml)
> 
> [Parameterized Type as Generic Method Return Type](#part0104.xhtml)

Conclusion:

*   A generic method is a method that uses one or more type parameters (also called type variables) to make it more generic so that it can be used as multiple variations.
*   A generic method has a signature of <A, B, C, ...> SomeType someMethod(...), where <A, B, C, ...> are type parameters.
*   Type parameters can be bounded as <T extends C & I1 & I2...> to ensure strong typing to reduce runtime type mismatches.
*   Type arguments can be specified as someObject.<X,Y,...>someMethod(...) when invoking a generic method.
*   Type argument inference is the process performed by the compiler to determine type arguments if they are not specified in the generic method invocation expression.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟What Is a Generic Method

This section describes what is a generic method, how to declare type parameters, how to use type parameters in generic method definitions.

**What Is a Generic Method?** A generic method is a static method or instance method that uses one or more type parameters (also called type variables) to make it more generic so that it can be used as multiple variations, one variation for each set of specific type arguments given to type parameters.

**How To Declare Type Parameters for a Generic Method?** To declare type parameters for a generic method, you need to specify type parameters before the return type as a comma-delimited list enclosed in angle brackets. For example, "static <T> void someMethod(...){...}" is a static generic method with one type parameter "T" declared.

**What Is a Bounded Type Parameter** A bounded type parameter is a type parameter declared with a supertype bound type with the syntax of "<T extends B>". Actually, a regular unbounded type parameter can also be viewed as a bounded type parameter with the supertype bound type equal to "Object". For example, "<T>" is equivalent to "<T extends Object>".

**How Type Parameters Are Used in Method Parameter List?** Once a type parameter is declared, it can be used in the parameter list definition of a generic method to help defining the type of each parameter. For example, "static <T> void someMethod(T o){...}" uses the type parameter "T" to define the type of parameter "o".

**How Type Parameters Are Used in Method Return Type?** Once a type parameter is declared, it can also be used in the return type definition of a generic method to help defining the type of the return value. For example, "static <T> T someMethod(){...}" uses the type parameter "T" to define the type of the return value.

**How Type Parameters Are Used in Parameterized Types?** Once a type parameter is declared, it can also be used as the parameter in a parameterized type to help defining types of method parameters and/or the return value. For example, "static <T> Enumeration<T> someMethod(Collection<T> c){...}" uses the type parameter "T" in two parameterized types in the method definition.

**How To Specify Type Arguments When Calling Generic Methods?** To specify type arguments to replace type parameters when calling a generic method, you need to provide type arguments after the dot (.) operator as a comma-delimited list enclosed in angle brackets. For example, "SomeClass.<String>someMethod(...){...}" is the expression to invoke a static generic method with one type argument "String" specified.

**Why Using Generic Methods?** The main advantage of using generic methods is for developing a single method to support multiple sets of data types in the method interface without using type casting. The resulting source code is type-safer and better readability.

In the next section, we will compare a generic method with a non-generic method to see what we are gaining by using generic methods.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Comparing Generic Method with Non-Generic Method

This section provides a tutorial example of comparing a generic method and a non-generic method for the same requirement. The generic method allows the compiler to catch more type compatibility mistakes.

To see advantages of using generic methods, let's try to develop a non-generic method and a generic method for the same requirement and compare them.

Assuming that we have a requirement to develop a static method that compares two objects and returns the object that has the higher value, and this method should support multiple types of objects like String, Number, Date, Time, etc., here is the best I can write as a non-generic version of the method:

```
 public static Comparable maxNonGeneric(Comparable a, Comparable b) {}
```

This definition is very weak in terms of type requirements in the method signature. When programmers try to invoke this non-generic method, they have chances of making mistakes as listed below. The compiler will not be to catch those mistakes. The resulting bytecode will be more likely running into runtime exceptions:

```
 String max = (String) maxNonGeneric(
   new String("1234"), new String("789")); // Correct invocation

String max = (String) maxNonGeneric(
   new String("1234"), new Integer("789")); // Run-time exception

Integer max = (Integer) maxNonGeneric(
   new String("1234"), new String("789")); // Run-time exception
```

Here is my generic version of the method for the same requirement:

```
 public static <T extends Comparable<T>> T maxGeneric(T a, T b) {}
```

This definition is much stronger now in terms of type requirements in the method signature:

*   The type parameter "T" is bounded be a subtype of Comparable<T>.
*   Both parameters "a" and "b" must have the same type as the type parameter "T".
*   The return value will be the same type as the type parameter "T".

Now when programmers try to invoke this generic method, they still have chances of making those same mistakes. But the compiler will catch them because of the stronger definition of the method. The resulting bytecode will be less likely running into runtime exceptions

```
 String max = SomeClass.<String>maxGeneric(
   new String("1234"), new String("789"));
   // Correct invocation. No (String) casting needed in source code.

Integer max = SomeClass.<String>maxGeneric(
   new String("1234"), new String("789")); // Compilation error

String max = SomeClass.<String>maxGeneric(
   new String("1234"), new Integer("789")); // Compilation error
```

Note that the class name "SomeClass" is needed because the type argument <String> is required to show up after the dot (.) operator.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Non-Generic Method Example - maxNonGeneric()

This section provides a tutorial example of non-generic method, maxNonGeneric(), that shows type compatibility mistakes are not detected at the compilation time.

To support our analysis provided in the previous section, I wrote the following tutorial example to implement and test the non-generic method:

```
 /* MaxNonGenericMethod.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class MaxNonGenericMethod {
   public static Comparable maxNonGeneric(
      Comparable a, Comparable b) {
      if (a.compareTo(b)>=0) {
         return a;
      } else {
         return b;
      }
   }
   public static void main(String[] a) {
      String max = (String) maxNonGeneric(
         new String("1234"), new String("789"));
      System.out.println("Maximum: "+max);

      // Mistake 1: Runtime exception when calling compareTo()
      String max1 = (String) maxNonGeneric(
         new String("1234"), Integer.valueOf("789"));

      // Mistake 2: Runtime exception when casting return value
      Integer max2 = (Integer) maxNonGeneric(
         new String("1234"), new String("789"));
   }
}
```

If you compile and run this tutorial example, you will get:

```
 herong> javac MaxNonGenericMethod.java

Note: MaxNonGenericMethod.java uses unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.

herong> java MaxNonGenericMethod

Maximum: 789
Exception in thread "main" java.lang.ClassCastException:
   java.base/java.lang.Integer cannot be cast to java.base/java.lang.String
        at java.base/java.lang.String.compareTo(String.java:124)
        at MaxNonGenericMethod.maxNonGeneric(MaxNonGenericMethod.java:7)
        at MaxNonGenericMethod.main(MaxNonGenericMethod.java:19)
```

As you can see from the output, the compiler did not catch the first type compatible mistake in the (String max1 = (String) maxNonGeneric(new String("1234"), new Integer("789"));) call. The resulting bytecode ran into a class cast exception when compareTo() was called.

If comment out lines 19 to 20 and run the program again:

```
 herong> javac MaxNonGenericMethod.java

Note: MaxNonGenericMethod.java uses unchecked or unsafe operations.
Note: Recompile with -Xlint:unchecked for details.

herong> java MaxNonGenericMethod

Maximum: 789
Exception in thread "main" java.lang.ClassCastException:
   java.base/java.lang.String cannot be cast to java.base/java.lang.Integer
        at MaxNonGenericMethod.main(MaxNonGenericMethod.java:23)
```

As you can see from the output, the compiler did not catch the second type compatible mistake in the (Integer max2 = (Integer) maxNonGeneric(new String("1234"), new String("789"));) call. The resulting bytecode ran into another class cast exception when the return value was assigned to "max2".

Conclusion: Non-generic methods can leave type compatibility mistakes undetected at compilation time. This leads to high likelihood of runtime exceptions.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Generic Method Example - maxGeneric()

This section provides a tutorial example of generic method, maxGeneric(), that shows type compatibility mistakes are detected at the compilation time.

To finish the comparison, I wrote the following tutorial example to implement and test the generic method:

```
 /* MaxGenericMethod.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class MaxGenericMethod {
   public static <T extends Comparable<T>> T maxGeneric(T a, T b) {
      if (a.compareTo(b)>=0) {
         return a;
      } else {
         return b;
      }
   }
   public static void main(String[] a) {
      String max = MaxGenericMethod.<String>maxGeneric(
         new String("1234"), new String("789"));
      System.out.println("Maximum: "+max);

      // Mistake 1: Runtime exception when calling compareTo()
      // String max1 = MaxGenericMethod.<String>maxGeneric(
      //    new String("1234"), Integer.valueOf("789"));

      // Mistake 2: Runtime exception when casting return value
      // Integer max2 = MaxGenericMethod.<String>maxGeneric(
      //    new String("1234"), new String("789"));
   }
}
```

If you compile and run this tutorial example, you will get:

```
 herong> javac MaxGenericMethod.java

herong> java MaxGenericMethod

Maximum: 789
```

The output confirms that my generic method is working!

Now uncomment the first and second mistakes. Compile the program again, you will get:

```
 herong> javac MaxGenericMethod.java

MaxGenericMethod.java:19: error: incompatible types: Integer cannot be
   converted to String
         new String("1234"), new Integer("789"));
                             ^
MaxGenericMethod.java:22: error: incompatible types: String cannot be
   converted to Integer
      Integer max2 = MaxGenericMethod.<String>maxGeneric(
                                                        ^
Note: Some messages have been simplified; recompile with
   -Xdiags:verbose to get full output
2 errors
```

If you compile the program again with the suggested option "-Xdiags:verbose", you will get more detailed error messages:

```
 herong> javac.exe -Xdiags:verbose MaxGenericMethod.java

MaxGenericMethod.java:18: error: method maxGeneric in class
   MaxGenericMethod cannot be applied to given types;
      String max1 = MaxGenericMethod.<String>maxGeneric(
                                    ^
  required: T,T
  found: String,Integer
  reason: argument mismatch; Integer cannot be converted to String
  where T is a type-variable:
    T extends Comparable<T> declared in method <T>maxGeneric(T,T)
MaxGenericMethod.java:22: error: incompatible types: String cannot be
   converted to Integer
      Integer max2 = MaxGenericMethod.<String>maxGeneric(
                                                        ^
2 errors
```

The output confirms that the compiler did a good job to catch both type compatibility mistakes!

Note that if you are using the JDK 1.7 compiler, you will get same errors. But the error messages are different:

```
 herong> "\Program Files\java\jdk1.7.0_45\bin\javac.exe" MaxG
enericMethod.java

MaxGenericMethod.java:18: error: method maxGeneric in class
   MaxGenericMethod cannot be applied to given types;
      String max1 = MaxGenericMethod.<String>maxGeneric(
                                    ^
  required: T,T
  found: String,Integer
  reason: actual argument Integer cannot be converted to String by
     method invocation conversion
  where T is a type-variable:
    T extends Comparable<T> declared in method <T>maxGeneric(T,T)

MaxGenericMethod.java:22: error: incompatible types
      Integer max2 = MaxGenericMethod.<String>maxGeneric(
                                                        ^
  required: Integer
  found:    String
2 errors
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Generic Methods in java.util.Collections Class

This section provides my understandings of some generic methods defined in the java.util.Collections class.

From previous sections, we learned how to read generic method definitions. Now let's look at some generic methods defined in the java.util.Collections class and see if we understand their definitions.

*   <T> List<T> singletonList(T o) - Creates a List of T with an object of T. Parameterized type is used as the return type in this example.
*   <T> List<T> nCopies(int n, T o) - Creates a List of T with an object of T repeating it n times.
*   <T> Enumeration<T> enumeration(Collection<T> c) - Returns an Enumeration of T from the given Collection of T, Parameterized type is used as the method parameter this example.
*   <T> ArrayList<T> - list(Enumeration<T> e) - Converts an Enumeration of T to an ArrayList of T.
*   <T> boolean replaceAll(List<T> list, T oldVal, T newVal) - Finds and replaces an old object with a new object of T in a List of type T.
*   <T> void fill(List<? super T> list, T obj) - Fills a List of any supertype of T with an object of T. Wildcard parameterized type is used in this example.
*   <T> void copy(List<? super T> dest, List<? extends T> src) - Copies a List of any subtype of T to a List of supertype of T.
*   <T> List<T> emptyList() - Returns an empty List of T.
*   <T> int binarySearch(List<? extends Comparable<? super T>> list, T key) - Searches the "key" of type T in a List of any subtype of Comparable<? super T> and returns the index of "key". Nested wildcard parameterized type is used in this example.
*   <T extends Object & Comparable<? super T>> T max(Collection<? extends T> coll) - Returns the maximum element of the given collection, according to the natural ordering of its elements.
*   <T extends Comparable<? super T>> void sort(List<T> list) - Sorts the specified list into ascending order, according to the natural ordering of its elements.

See next section for tutorial examples on how to use those generic methods.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Testing Generic Methods in Collections Class

This section provides a tutorial example on testing generic methods provided in the java.util.Collections class.

If you want to practice how to use generic methods, you can follow the tutorial example below:

```
 /* CollectionsGenericMethods.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class CollectionsGenericMethods {
   public static void main(String[] a) {
      java.io.PrintStream o = System.out;

      // Get a List of a single String
      List<String> myList
         = Collections.<String>singletonList("Java");

      // Get it back as Enumeration of String
      Enumeration<String> myEnum
         = Collections.<String>enumeration(myList);

      // Convert it as ArrayList of String
      ArrayList<String> myArrayList
          = Collections.<String>list(myEnum);

      // Add more elements
      myArrayList.add("Bean");
      myArrayList.add("Language");
      myArrayList.add("Coffee");

      // Sort the list
      Collections.<String>sort(myArrayList);

      // Get the minimum element
      String min
         = Collections.<String>min(myArrayList);

      // Find where the minimum is located
      int loc =
         Collections.<String>binarySearch(myArrayList, min);

      // Show the location and value
      o.println("Minimum element, "+min+", is at "+loc);
   }
}
```

Compile and run the example, you should see no compilation errors and runtime exceptions. The result seems to be correct:

```
 Minimum element, Bean, is at 0
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟What Is Type Argument Inference

This section describes what is type argument inference - a process performed by the compiler to determine the actual type argument for a type parameter when invoking in a generic method.

**What Is Type Argument Inference?** Type argument inference is a process performed by the compiler to determine the actual type argument for a type parameter when invoking in a generic method.

Type argument inference also happens when the compiler tries to determine the actual type argument for a type parameter when instantiating an object from a generic class. See other parts of the book for more details.

**Why Type Argument Inference Is Needed?** Type argument inference is needed only if you do not specify type arguments explicitly when invoking a generic method.

When type arguments are specified as shown below in the type argument list, the compiler knows what the type argument is. It will not perform the type argument inference process:

```
 // No, type argument inference is not needed
   Collections.<String>sort(myArrayList);
```

When type arguments are not specified as shown below, the compiler does not know what the type argument is. It will perform the type argument inference process to determine type arguments:

```
 // Yes, type argument inference is needed
   Collections.sort(myArrayList);
```

Personally, I will always specify type arguments explicitly to avoid type argument inference, because compiler may infer to incorrect type arguments and lead to type incompatibility issues. But if you are a lazy programmer, you can take the risk and let the compiler to do the work for you using rules described below.

**How Type Argument Inference Is Done?** If you are not specifying type arguments when invoking generic methods, the compiler will perform the type argument inference process using these rules:

*   If a type parameter is used in one method parameter, the compiler will look at the type of the corresponding argument to deduce the type argument.
*   If a type parameter is used in multiple method parameters, the compiler will look at types of all corresponding arguments to deduce a single type argument. If this not possible, a compilation error is raised.
*   If a type parameter is not used in any method parameter, it will be used in the return value type. The compiler will look at the expression context where this method is invoked to deduce the type argument.
*   If the compiler failed to deduce the type argument from the context, it will use the default type argument, Object.

Next sections will show you some examples on how compiler does the type argument inference.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Type Argument Inference by Parameter List

This section provides a tutorial example on type argument inference by parameter list. The compiler will deduce the type argument by looking at actual arguments for the method parameter list if the type parameter is used there.

Type argument inference (also called type inference) on generic method invocation is something I will not recommend. But if you want to use it, you can gain some experience with the following tutorial example:

```
 /* TypeInferenceByParameter.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class TypeInferenceByParameter {
   public static <T extends Comparable<T>> T maxGeneric(T a, T b) {
      if (a.compareTo(b)>=0) {
         return a;
      } else {
         return b;
      }
   }
   public static void main(String[] a) {
      String as = "1234";
      String bs = "789";
      Integer ai = Integer.valueOf(1234);
      Long bl = Long.valueOf(789);

      /* Test 1 - Type argument specified as String */
      String ms
         = TypeInferenceByParameter.<String>maxGeneric(as, bs);
      System.out.println("Maximum: "+ms);

      /* Test 2 - Type argument inferred to String
                  by looking at parameters as and bs
      Object os = TypeInferenceByParameter.maxGeneric(as, bs);
      System.out.println("Maximum: "+os);
      */

      /* Test 3 - Type argument inference failed
                  to deduce to a single type
      Long ml = TypeInferenceByParameter.maxGeneric(ai, bl);
      System.out.println("Maximum: "+ml);
      */

      /* Test 4 - Type argument inference failed
                  to deduce to a subtype of Comparable
      Integer mi = TypeInferenceByParameter.maxGeneric(
         (Number)ai, (Number)bl);
      System.out.println("Maximum: "+mi);
      */

      /* Test 5 - Type argument inferred to Short
                  but runtime exception occurred
      Number mn = TypeInferenceByParameter.maxGeneric(
         (Short)(Number)ai, (Short)(Number)bl);
      System.out.println("Maximum: "+mn);
      */
   }
}
```

On test 1, I was not using type argument inference. So there was no compilation error and runtime exception. The execution result was correct:

```
 Maximum: 789
```

On test 2, I let the compiler to do the type inference. The compiler did a good job to deduce the type argument to be "String" and the result was correct:

```
 Maximum: 789
Maximum: 789
```

On test 3, I purposely provided inconsistent types in the argument list "ai, bl". The JDK 1.7 compiler failed on the type inference process and gives me this compilation error. The error message said that the inferred type was INT#1 and did not conform to the declared bound. But I see the root cause is that found types "Integer,Long" does not match required types "T,T" where both of types must be the same type:

```
 TypeInferenceByParameter.java:31: error: method maxGeneric in class
TypeInferenceByParameter cannot be applied to given types;
      Long ml = TypeInferenceByParameter.maxGeneric(ai, bl);
                                        ^
  required: T,T
  found: Integer,Long
  reason: inferred type does not conform to declared bound(s)
    inferred: INT#1
    bound(s): Comparable<INT#1>
  where T is a type-variable:
    T extends Comparable<T> declared in method <T>maxGeneric(T,T)
  where INT#1,INT#2 are intersection types:
    INT#1 extends Number,Comparable<? extends INT#2>
    INT#2 extends Number,Comparable<?>
```

In the JDK 1.8, the compilation error message on test 3 is better:

```
 TypeInferenceByParameter.java:31: error: method maxGeneric in class
   TypeInferenceByParameter cannot be applied to given types;
      Long ml = TypeInferenceByParameter.maxGeneric(ai, bl);
                                        ^
  required: T,T
  found: Integer,Long
  reason: inference variable T has incompatible bounds
    equality constraints: Integer,Long
    lower bounds: Long,Integer
  where T is a type-variable:
    T extends Comparable<T> declared in method <T>maxGeneric(T,T)
1 error
```

On test 4, I did provide the consistent types "Number,Number". But "Number" is not a subtype of "Comparable". So the compiler failed again with the appropriate message saying that inferred type is "Number" and does not conform to the declared bound.

```
 TypeInferenceByParameter.java:37: error: method maxGeneric in class
   TypeInferenceByParameter cannot be applied to given types;
      Integer mi = TypeInferenceByParameter.maxGeneric(
                                           ^
  required: T,T
  found: Number,Number
  reason: inferred type does not conform to upper bound(s)
    inferred: Number
    upper bound(s): Comparable<Number>
  where T is a type-variable:
    T extends Comparable<T> declared in method <T>maxGeneric(T,T)
1 error
```

On test 5, I double-casted both parameter objects to be the same type "Short". The compiler was stupid and deduced the type argument to be "Short" with no errors. But the runtime caught the type casting issue and gave a "ClassCastException".

```
 Maximum: 789
Exception in thread "main" java.lang.ClassCastException:
java.lang.Integer cannot be cast to java.lang.Short
   at TypeInferenceByParameter.main(TypeInferenceByParameter.java:44)
```

I think we have done enough testing with type argument inference with the method parameter list. We will test type argument inference with the method return value in the next section.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Type Argument Inference by Return Value

This section provides a tutorial example on type argument inference by return value. The compiler will deduce the type argument by looking at the context where the return value is used. if the type parameter is not used in the method argument list.

As described earlier, if type argument is not specified explicitly when invoking a generic method, the compiler will perform the type argument inference process. It will look at method argument list first to deduce the type argument, if the type parameter is used in there. If not, the compiler will look at the return value do the job.

Here is another tutorial example to show you how the compiler uses the return value to deduce the argument type:

```
 /* TypeInferenceByReturnValue.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class TypeInferenceByReturnValue {
   public static <T> T alias(Object o) {
      return (T) o;
   }
   public static void main(String[] a) {
      String s = "1234";

      /* Test 1 - Type argument specified as String */
      String as
         = TypeInferenceByReturnValue.<String>alias(s);
      System.out.println("Alias: "+as);

      /* Test 2 - Type argument inferred to String
                  by looking at the assignment operation
      String bs = TypeInferenceByReturnValue.alias(s);
      System.out.println("Alias: "+bs);
      */

      /* Test 3 - Type argument inferred to String
                  by looking at the invocation context
      Object ao = "Hello "+TypeInferenceByReturnValue.alias(s);
      System.out.println("Alias: "+ao);

      /* Test 4 - Type argument inferred to Long
                  but runtime exception occurred
      Long al = TypeInferenceByReturnValue.alias(s);
      System.out.println("Alias: "+al);
      */

      /* Test 5 - Type argument inferred to Short
                  but runtime exception occurred
      Number an = (Short) TypeInferenceByReturnValue.alias(s);
      System.out.println("Alias: "+an);
      */

      /* Test 6 - Type argument inferred to Object:
                  but failed to compile the entire statement
      Integer ai
         = Integer.valueOf(TypeInferenceByReturnValue.alias(s));
      System.out.println("Alias: "+ai);
      */
   }
}
```

On test 1, I was not using type argument inference. So there was no compilation issue except an "unchecked" warning at the (return (T) o;) statement. See the result below:

```
 herong> javac TypeInferenceByReturnvalue.java

Note: TypeInferenceByReturnvalue.java uses unchecked or unsafe
   operations.
Note: Recompile with -Xlint:unchecked for details.

herong> java TypeInferenceByReturnValue

Alias: 1234
```

On test 2, I let the compiler to do the type inference. The compiler did a good job to deduce the type argument to be "String" by looking at the left side of the assignment operation. See the result below:

```
 Alias: 1234
Alias: 1234
```

On test 3, the compiler also did a good job to deduce the type argument to be "String" by looking at the expected type of the string concatenation operation. See the result below:

```
 Alias: 1234
Alias: Hello 1234
```

On test 4, the compiler did an ok job and deduced the type argument to be "Long" by looking at the left side of the assignment operation. But this caused a runtime ClassCastException:

```
 Alias: 1234
Exception in thread "main" java.lang.ClassCastException:
   java.lang.String cannot be cast to java.lang.Long
at TypeInferenceByReturnValue.main(TypeInferenceByReturnvalue.java:30)
```

On test 5, the compiler did an ok job and deduced the type argument to be "Short" by looking at the cast operation on the return value. But this caused a runtime ClassCastException:

```
 Exception in thread "main" java.lang.ClassCastException:
java.lang.String cannot be cast to java.lang.Short
at TypeInferenceByReturnValue.main(TypeInferenceByReturnvalue.java:36)
```

On test 6, the compiler in JDK 1.7 failed to deduce the type argument to a type that can meet the requirement of Integer.valueOf(). It used the default type, "Object", as the type argument, leading to a compilation error on Integer.valueOf():

```
 TypeInferenceByReturnvalue.java:44: error: no suitable method found
for valueOf(Object)
         = Integer.valueOf(TypeInferenceByReturnValue.alias(s));
                  ^
    method Integer.valueOf(int) is not applicable
      (actual argument Object cannot be converted to int by method
      invocation conversion)
    method Integer.valueOf(String) is not applicable
      (actual argument Object cannot be converted to String by method
      invocation conversion)
    method Integer.valueOf(String,int) is not applicable
      (actual and formal argument lists differ in length)
```

However, the compiler in JDK 1.8 is not generating any errors on test 6\. It returns expected result of "Alias: 1234".

If you want to see more examples of using generic methods and type argument inference, see the next section.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Generic Methods using Parameterized Types

This section provides a tutorial example on generic methods that use parameterized types. Type argument inference tests are provided on the generic method, singletonList(), from the java.util.Collections class.

In this section, I want to continue to test on type argument inference on generic method that uses type parameters in parameterized types. Here is my first tutorial example on testing generic method, "<T> List<T> singletonList(T o)", defined in the Collections class.

```
 /* GenericMethodSingletonList.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class GenericMethodSingletonList {
   public static void main(String[] a) {
      testSingletonList();
   }
   public static void testSingletonList() {
      java.io.PrintStream o = System.out;
      o.println("Testing: <T> List<T> singletonList(T o)");

      String s = "777";
      List<String> ls = Collections.singletonList(s);
      String e = ls.get(0);
      o.println("   Class name of ls: "+ls.getClass().getName());
      o.println("   First element of ls: "+e);

      // Test 1\. Compilation error - inconvertible types
      // List<String> ls1 = Collections.singletonList((Object) s);

      // up casting to the wildcard parameterized type
      List<?> lw = ls;

      // up casting to a supper interface
      Collection<String> cs = ls;

      // Test 2\. Compiler error - inconvertible types
      // List<Integer> li1 = (List<Integer>) ls;
      // Collection<Integer> ci1 = (Collection<Integer>) ls;

      // Test 3\. Compiler warning - unchecked or unsafe operations
      // List<Integer> li2 = (List<Integer>) (List<?>) ls;
      // o.println("   Class name of li2: "+li2.getClass().getName());

      // Test 4\. Runtime exception - cannot be cast
      // Integer e2 = li2.get(0);
      // o.println("   First element of li2: "+e2);
   }
}
```

Compile and run the example, you will get:

```
 Testing: <T> List<T> singletonList(T o)
   Class name of ls: java.util.Collections$SingletonList
   First element of ls: 777
```

Looking at the statement where the generic method is invoked (List<String> ls = Collections.singletonList(s);), here is my guesses on how the compiler did the type argument inference to determine the actual type of the type parameter, T, and did the type checking on the statement:

*   The compiler looks at the type of the input object, s, and sees that it has a type of String.
*   The compiler determines that the actual type of the type parameter, T, should be String based on the input object.
*   The compiler determines that the return type of the method should be List<String> based on the return type definition.
*   The compiler sees a perfect match of the receiving variable; ls; and return type of the method. So no compilation error or warning.

But if you uncomment "Test 1." statements, you will get a compilation error in JDK 1.8\. This error tells me that the compiler is using the resulting type of the input argument expression to determine the actual type of the type parameter, T, not using the object type of what s is referring to.

```
 GenericMethodSingletonList.java:20: error: incompatible types:
   inference variable T has incompatible bounds
      List<String> ls1 = Collections.singletonList((Object) s);
                                                  ^
    equality constraints: String
    lower bounds: Object
  where T is a type-variable:
    T extends Object declared in method <T>singletonList(T)
1 error
```

Note that JDK 1.7 gives slightly different error message on "Test 1.":

```
 GenericMethodSingletonList.java:20: error: incompatible types
      List<String> ls1 = Collections.singletonList((Object) s);
                                                  ^
  required: List<String>
  found:    List<Object>
1 error
```

If you uncomment "Test 2." statements, you will get more compilation error in JDK 1.8, because casting from List<String> to List<Integer> or Collection<Integer> is not allowed.

```
 GenericMethodSingletonList.java:29: error: incompatible types:
   List<String> cannot be converted to List<Integer>
      List<Integer> li1 = (List<Integer>) ls;
                                          ^
GenericMethodSingletonList.java:30: error: incompatible types:
   List<String> cannot be converted to Collection<Integer>
      Collection<Integer> ci1 = (Collection<Integer>) ls;
                                                      ^
2 errors
```

Note that JDK 1.7 gives slightly different error message on "Test 2.":

```
 GenericMethodSingletonList.java:29: error: inconvertible types
      List<Integer> li1 = (List<Integer>) ls;
                                          ^
  required: List<Integer>
  found:    List<String>
GenericMethodSingletonList.java:30: error: inconvertible types
      Collection<Integer> ci1 = (Collection<Integer>) ls;
                                                      ^
  required: Collection<Integer>
  found:    List<String>
2 errors
```

If you uncomment "Test 3." statements, you will get a compilation warning, not an error, with the "-Xlint" option: This tells me that the compiler is not smart enough to stop me doing inconvertible casting with double cast operations.

```
 GenericMethodSingletonList.java:33: warning: [unchecked] unchecked
   cast
      List<Integer> li2 = (List<Integer>) (List<?>) ls;
                                          ^
  required: List<Integer>
  found:    List<CAP#1>
  where CAP#1 is a fresh type-variable:
    CAP#1 extends Object from capture of ?
1 warning
```

If you uncomment "Test 3." and "Test 4." statements, you will get a runtime exception, because li2.get(0) will return a String, even li2 is declared as a List<Integer>

```
 Testing: <T> List<T> singletonList(T o)
   Class name of ls: java.util.Collections$SingletonList
   First element of ls: 777
   Class name of li2: java.util.Collections$SingletonList
Exception in thread "main" java.lang.ClassCastException:
   java.lang.String cannot be cast to java.lang.Integer
        at GenericMethodSingletonList.testSingletonList
        (GenericMethodSingletonList.java:37)
        at GenericMethodSingletonList.main
        (GenericMethodSingletonList.java:7)
```

But why there is no runtime exception on the statement where the root cause is located: (List<Integer> li2 = (List<Integer>) (List<?>) ls;)?

The answer is that Java actually allows casting from (List<String> to (List<Integer> at runtime. Because they are really objects from the same class List<T> which is really List<Object> in the compiled bytecode. This called "Type Erasure".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Generic Methods and Type Inference](#part0093.xhtml)

∟Parameterized Type as Generic Method Return Type

This section provides a tutorial example of using a generic method, emptyList(), from the java.util.Collections class. The type parameter is used only in the return type definition, no in the method parameters definition.

In the previous tutorial, we tested the "<T> List<T> singletonList(T o)" generic method and learned how the compiler uses the input argument expression to perform type argument inference to determine the type parameter, T.

In this tutorial, we will see how the compiler determines the actual type of the type parameter, T, if it is only used in the return type. Here is a tutorial example program that uses the "<T> List<T> emptyList()" generic method.

```
 /* GenericMethodsEmptyList.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class GenericMethodsEmptyList {
   public static void main(String[] a) {
      testEmptyList();
   }
   public static void testEmptyList() {
      java.io.PrintStream o = System.out;
      o.println("Testing: <T> List<T> emptyList()");

      List<String> ls = Collections.emptyList();
      o.println("   Class name of ls: "+ls.getClass().getName());

      List<?> lw = (List<?>) Collections.emptyList();
      o.println("   Class name of lw: "+lw.getClass().getName());

      // Compiler error: inconvertible types
      // List<Number> ln = (List<Number>) Collections.emptyList();
   }
}
```

Compile and run the example, you will get:

```
 Testing: <T> List<T> emptyList()
   Class name of ls: java.util.Collections$EmptyList
   Class name of lw: java.util.Collections$EmptyList
```

Looking at the first statements where the generic method are invoked (List<String> ls = Collections.emptyList();) and (List<?> lw = (List<?>) Collections.emptyList();), here is my guesses on how the compiler determines the actual type of the type parameter, T, and did the type checking on the statement:

*   The compiler looks at the context of the expression where the return reference is used to determine what should be actual type of the type parameter, T.
*   The compiler determines that the actual type of the type parameter, T, should be String in the first case, (List<String> ls = Collections.emptyList();), because List<String> is expected.
*   The compiler determines that the actual type of the type parameter, T, should be Object, in the second case, (List<?> lw = (List<?>) Collections.emptyList();), because the casting operation can work on any type. So the compiler uses the default type, Object, for the type parameter.

The behavior of using the default type of Object as the type parameter by the compiler can be demonstrated better, if you uncomment the (List<Number> ln = (List<Number>) Collections.emptyList();) statement and try to compile it again in JDK 1.8, you see this error:

```
 GenericMethodsEmptyList.java:20: error: incompatible types:
   List<Object> cannot be converted to List<Number>
      List<Number> ln = (List<Number>) Collections.emptyList();
                                                            ^
1 error
```

If you compile it with JDK 1.7, the error message is different:

```
 GenericMethodsEmptyList.java:20: error: inconvertible types
       List<Number> ln = (List<Number>) Collections.emptyList();
                                                             ^
  required: List<Number>
  found:    List<Object>
1 error
```

The "found: List<Object>" part of the error confirms that the compiler assumes that (Collections.emptyList();) has a default type of "List<Object>".

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Lambda Expressions and Method References

This chapter provides tutorial notes on lambda expressions and method references introduced in Java 8\. Topics include lambda expression syntax; method reference syntax; single abstract method interface (functional interface); using lambda expressions in stream pipeline operations.

> [What Is Lambda Expression](#part0106.xhtml)
> 
> [LambdaCalculator.java - Lambda Expression Example](#part0107.xhtml)
> 
> [Lambda Expression Syntax Options](#part0108.xhtml)
> 
> [Lambda Expression as Method Reference](#part0109.xhtml)
> 
> [Method Reference Example - LambdaMethodRefernce.java](#part0110.xhtml)
> 
> [Lambda Expression Stream Pipeline Operations](#part0111.xhtml)

Conclusion:

*   A functional interface is a single abstract method interface.
*   A lambda expression is a shorthand form of a special anonymous class that implements a functional interface.
*   A method expression is a shorthand form of a special lambda expression that a single invocation of a static method.
*   The best places to use lambda expressions are in stream pipeline operations.
*   Lambda expressions, method references and stream pipeline operations are introduced in Java 8.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Lambda Expressions and Method References](#part0105.xhtml)

∟What Is Lambda Expression

This section describes what is a lambda expression, which is a shorthand form of an anonymous class that implements a single abstract method interface (also called functional interface).

**What Is Lambda Expression?** A Lambda Expression is a shorthand form of a special anonymous class that implements an interface with only one abstract method. Lambda Expressions were introduced in Java 8.

An interface with only one abstract method is also called a **Functional Interface**.

Here is the syntax of a lambda expression:

```
 (parameter_list) -> {method_body}
```

The above lambda expression syntax is actually a shorthand form of the following anonymous class syntax:

```
 new interface_name() {
   return_type method_name(parameter_list) {method_body}
}
```

The table below provides you a comparison of each element between the anonymous class syntax and the lambda expression syntax:

```
 Anonymous class      |  Lambda expression
                     |
new                  |
interface_name() {   |
   return_type       |
   method_name       |
   (parameter_list)  |  (parameter_list)
                     |  ->
   {method_body}     |  {method_body}
}                    |
```

Here is what I see from the above comparison:

*   The "new" operator is omitted in lambda expressions.
*   The "interface_name" is omitted in lambda expressions. It's up to the compiler to determine the base interface by looking the context where the lambda expression is used.
*   The "return_type" is omitted in lambda expressions. The compiler knows the return type by looking at the only abstract method of the base interface.
*   The "method_name" is omitted in lambda expressions. The compiler knows the method name by looking at the only abstract method of the base interface.
*   The "parameter_list" is maintained in lambda expressions. The parameter list is definitely needed as variables for implementing the only abstract method in the base interface.
*   The "->" (arrow) token is introduced in lambda expressions as identifications of lambda expressions.
*   The "method_body" is maintained in lambda expressions. The method body is definitely needed for implementing the only abstract method in the base interface.

Since a lambda expression is just a shorthand form of a special anonymous class, it acts in the same way as an anonymous class with some minor differences as summarized below:

*   Like an anonymous class, a lambda expression defines a class locally without any name. But unlike an anonymous class, a lambda expression does not produce any class bytecode at compilation time.
*   Like an anonymous class, a lambda expression creates a new object from the class defined by the lambda expression. A reference to this new object will be the evaluation result of the lambda expression.
*   Unlike an anonymous class, a lambda expression can only implement a single abstract method interface.

See the next section for a simple example of a lambda expression.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Lambda Expressions and Method References](#part0105.xhtml)

∟LambdaCalculator.java - Lambda Expression Example

This section provides a tutorial example on using an lambda expression to define a class anonymously implementing a single abstract method interface. An anonymous class and a local class are used as comparisons.

My first lambda expression program, LambdaCalculator.java, follows an example given in a Oracle Java tutorial. Here is the source code:

```
 /* LambdaCalculator.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class LambdaCalculator {
   interface Operation {
      int operate(int a, int b);
   }
   public int calculate(int a, int b, Operation o) {
      System.out.println(o.toString());
      return o.operate(a, b);
   }

   public static void main(String[] arg) {
      int x = 1;
      String s = "+";
      int y = 2;
      if (arg.length>0) x = Integer.parseInt(arg[0]);
      if (arg.length>1) s = arg[1];
      if (arg.length>2) y = Integer.parseInt(arg[2]);

      // Using a lambda expression
      Operation add = (int a, int b) -> {return a+b;};

      // Using anonymous class
      Operation subtract = new Operation() {
         public int operate(int a, int b) {return a-b;}
      };

      // Using a local class
      class Multiply implements Operation {
         public int operate(int a, int b) {return a*b;}
      }
      Operation multiply = new Multiply();

      LambdaCalculator c = new LambdaCalculator();
      if (s.equals("+"))
         System.out.println(x+s+y+" = "+c.calculate(x,y,add));
      else if (s.equals("-"))
         System.out.println(x+s+y+" = "+c.calculate(x,y,subtract));
      else if (s.equals("*"))
         System.out.println(x+s+y+" = "+c.calculate(x,y,multiply));
      else
         System.out.println(x+s+y+" = Undefined");
   }
}
```

Note that my sample program uses an lambda expression, an anonymous class and a local class to implement the same interface:

*   "Operation" is a single abstract method interface which is nested in the "LambdaCalculator" class.
*   "Operation add = (int a, int b) -> {return a+b;};" uses a lambda expression to implement an add operation. A new object is created from the implementation class and assigned to "add".
*   "Operation subtract = new Operation() { ... };" uses an anonymous class to implement a subtract operation. A new object is created from the implementation class and assigned to "subtract".
*   "Operation multiply = new Multiply();" uses a local class to implement a multiply operation. A new object is created from the implementation class and assigned to "multiply".

Now compile and run LambdaCalculator.java with JDK 1.8, you will get:

```
 herong> java LambdaCalculator
LambdaCalculator$$Lambda$1/518248@cf9800
1+2 = 3

herong> java LambdaCalculator 8 + 2
LambdaCalculator$$Lambda$1/518248@cf9800
8+2 = 10

herong> java LambdaCalculator 8 - 2
LambdaCalculator$1@cf9800
8-2 = 6

herong> java LambdaCalculator 8 "*" 2
LambdaCalculator$1Multiply@cf9800
8*2 = 16
```

Here is what I learned from the output:

*   The lambda expression "(a,b) -> {return a+b;}" does define a class named as "LambdaCalculator$$Lambda$1/518248".
*   When using * as command line argument, it needs to be quoted as "*", because * is wildcard character on Windows systems.

If we look at class files generated by the compiler, we will see only 4 of them. And there is no class file for the "LambdaCalculator$$Lambda$1/518248" class defined by the lambda expression.

```
 herong> dir LambdaCalculator*.*

1,423 LambdaCalculator.java
2,076 LambdaCalculator.class           - Main application class
  214 LambdaCalculator$Operation.class - Nested interface "Operation"
  440 LambdaCalculator$1.class         - Anonymous class for "subtract
  459 LambdaCalculator$1Multiply.class - Local class "Multiply"
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Lambda Expressions and Method References](#part0105.xhtml)

∟Lambda Expression Syntax Options

This section describes some syntax simplification options on lambda expressions. A sample program is provided to show you a very compact example of a lambda expression: (a->b->c->d->'Hello').

Java also supports several options to simply the lambda expression syntax:

*   Data types can be omitted in the parameter list. The compiler knows the data type of each parameter by looking at the only abstract method of the base interface. For example, "(int a, int b) -> {return a+b;}" can be expressed as "(a,b) -> {return a+b;}".
*   The parentheses of the parameter list can be omitted, if there is only 1 parameter. For example, "(p) -> {return p.getAge() >= 18;}" can be expressed as "p -> {return p.getAge() >= 18;}".
*   The method body can be simplified to an expression without braces, if the entire method body is a single "return" statement. For example, "p -> {return p.getAge() >= 18;}" can be expressed as "p -> p.getAge() >= 18".

Using the simplified syntax makes the source compact and easier to read in most cases. But sometimes it does the opposite. For example, take a guess on what this lambda express will do in your Java code: (a->b->c->d->"Hello")?

You can play the following sample program to find out:

```
 /* LambdaNested.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class LambdaNested {
   static void show(InterfaceA a) {
      System.out.println(a.toString());
   }
   public static void main(String[] arg) {
      show(a->b->c->d->"Hello");
   }
   interface InterfaceD {
      Object methodD(Object o);
   }
   interface InterfaceC {
      InterfaceD methodC(Object o);
   }
   interface InterfaceB {
      InterfaceC methodB(Object o);
   }
   interface InterfaceA {
      InterfaceB methodA(Object o);
   }
}
```

This program will pass the compilation and run in JDK 1.8:

```
 herong> javac LambdaNested.java

herong> java LambdaNested
LambdaNested$$Lambda$1/518248@cf9800
```

If you are having trouble reading the above program, the following version using anonymous classes may help you out:

```
 /* LambdaNestedDecoded.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class LambdaNestedDecoded {
   static void show(InterfaceA a) {
      System.out.println(a.toString());
   }
   public static void main(String[] arg) {
      // show(a->b->c->d->"Hello");

      // InterfaceD iD = d->"Hello";
      InterfaceD iD = new InterfaceD() {
         public Object methodD(Object o) {return "Hello";}
      };

      // InterfaceC iC = c->iD;
      InterfaceC iC = new InterfaceC() {
         public InterfaceD methodC(Object o) {return iD;}
      };

      // InterfaceB iB = b->iC;
      InterfaceB iB = new InterfaceB() {
         public InterfaceC methodB(Object o) {return iC;}
      };

      // InterfaceA iA = a->iB;
      InterfaceA iA = new InterfaceA() {
         public InterfaceB methodA(Object o) {return iB;}
      };

      show(iA);
   }
   interface InterfaceD {
      Object methodD(Object o);
   }
   interface InterfaceC {
      InterfaceD methodC(Object o);
   }
   interface InterfaceB {
      InterfaceC methodB(Object o);
   }
   interface InterfaceA {
      InterfaceB methodA(Object o);
   }
}
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Lambda Expressions and Method References](#part0105.xhtml)

∟Lambda Expression as Method Reference

This section describes what is a method reference, which is a shorthand form of a special lambda expression which contains only one static method invocation in the body.

**What Is Method Reference?** A method reference is a shorthand form of a special lambda expression which contains only one static method invocation in the body. Of course, static method parameter list and return should match the base interface.

Here is the syntax of a method reference:

```
 class_name :: method_name
```

The above method reference syntax is actually a shorthand form of the following lambda expression syntax:

```
 (parameter_list) -> class_name.method_name(actual_parameter_list)
```

Comparing the two syntax, I can see that:

*   The "parameter_list" is omitted in method reference. The compiler can get them by looking at the only abstract method of the base interface.
*   The "->" is omitted in method reference. Because the "::" (double colon) token is introduced in method references as identifications of method references.
*   The "class_name" and "method_name" are used method reference to identify which method to be invoked.
*   The "actual_parameter_list" is omitted in method reference. The compiler will automatically pass all parameters from the "parameter_list" to the "actual_parameter_list in the same order.

Here is an example of a method reference:

```
 ClassC :: methodM
```

The compiler will process the above method reference like the following lambda expression:

```
 (TypeA a, TypeB b) -> ClassC.methodM(a, b)
```

Of course, we are assuming that the base interface has to following abstract method:

```
 public TypeC c methodI(TypeA a, TypeB b);
```

See the next section for an example program that uses method references.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Lambda Expressions and Method References](#part0105.xhtml)

∟Method Reference Example - LambdaMethodRefernce.java

This section provides a tutorial example on how to use method references.

In order to play with method references, let's try to convert the lambda expression example program, LambdaCalculator.java, to use method references. Here is my version,

```
 /* LambdaMethodRefernce.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class LambdaMethodRefernce {
   interface Operation {
      int operate(int a, int b);
   }
   public static int add(int a, int b) {
      return a+b;
   }
   public static int subtract(int a, int b) {
      return a-b;
   }
   public static int multiply(int a, int b) {
      return a*b;
   }
   public int calculate(int a, int b, Operation o) {
      System.out.println(o.toString());
      return o.operate(a, b);
   }

   public static void main(String[] arg) {
      int x = 1;
      String s = "+";
      int y = 2;
      if (arg.length>0) x = Integer.parseInt(arg[0]);
      if (arg.length>1) s = arg[1];
      if (arg.length>2) y = Integer.parseInt(arg[2]);

      LambdaMethodRefernce c = new LambdaMethodRefernce();
      if (s.equals("+"))
         System.out.println(x+s+y+" = "
            +c.calculate(x,y,LambdaMethodRefernce::add));
      else if (s.equals("-"))
         System.out.println(x+s+y+" = "
            +c.calculate(x,y,LambdaMethodRefernce::subtract));
      else if (s.equals("*"))
         System.out.println(x+s+y+" = "
            +c.calculate(x,y,LambdaMethodRefernce::multiply));
      else
         System.out.println(x+s+y+" = Undefined");
   }
}
```

Compile and run the sample program in JDK 1.8\. You will get some results like these:

```
 herong> java LambdaMethodRefernce
LambdaMethodRefernce$$Lambda$1/518248@cf9800
1+2 = 3

herong> java LambdaMethodRefernce 8 + 2
LambdaMethodRefernce$$Lambda$1/518248@cf9800
8+2 = 10

herong> java LambdaMethodRefernce 8 - 2
LambdaMethodRefernce$$Lambda$1/518248@cf9800
8-2 = 6

herong> java LambdaMethodRefernce 8 "*" 2
LambdaMethodRefernce$$Lambda$1/518248@cf9800
8*2 = 16

herong> java LambdaMethodRefernce 8 / 2
8/2 = Undefined
```

The output confirms that method references are lambda expressions.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Lambda Expressions and Method References](#part0105.xhtml)

∟Lambda Expression Stream Pipeline Operations

This section provides a tutorial example of using lambda expressions in stream pipeline operations. LambdaStream.java uses calendar dates as a stream and filters out Friday the 13th dates with lambda expressions.

The best place to use lambda expressions is probably in stream pipeline operations. See the example program, LambdaOnStream.java, below:

```
 /* LambdaOnStream.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;;
import java.text.*;;
import java.util.stream.Stream;
class LambdaOnStream {
   public static void main(String[] arg) {
      Calendar today = new GregorianCalendar();
      Stream
         .iterate(today, d->{
            Calendar n = (Calendar)d.clone();
            n.add(Calendar.DATE,1);
            return n;
          })
         .filter(d->d.get(Calendar.DATE)==13
            && d.get(Calendar.DAY_OF_WEEK)==Calendar.FRIDAY
          )
         .limit(10)
         .map(d->d.getTime())
         .forEach(d->System.out.println(
            new SimpleDateFormat("dd-MMM-yyyy").format(d)
          ));
   }
}
```

LambdaOnStream.java uses several pipeline operations from the "Stream" interface introduced in JDK 1.8 to manipulate a stream of calendar objects:

*   The pipeline consists of 5 operations: iterate(), filter(), limit(), map() and forEach().
*   At the beginning of the pipeline, iterate() is used to create a new Stream object with a Calendar object "today" as the first element and a lambda expression to generate the next element with the previous element.
*   The lambda expression used in iterate(), "d->{ Calendar n = (Calendar)d.clone(); n.add(Calendar.DATE,1); return n; }", is returning the next day Calendar object cloned from the given Calendar object.
*   The next operation in the pipeline is filter(), which removes elements that does not meet the given criteria out of the stream.
*   The lambda expression used in filter(), "d->d.get(Calendar.DATE)==13 && d.get(Calendar.DAY_OF_WEEK)==Calendar.FRIDAY", is returning true if the given Calendar object is Friday the 13th.
*   The next operation in the pipeline is limit(), which simply ends the stream after a given number of elements.
*   The next operation in the pipeline is map(), which converts all element from one object type to another object type.
*   The lambda expression used in map(), "d->d.getTime()", is returning a Date object from the given Calendar object.
*   At the end of the pipeline, forEach() is used to apply final actions on each element.
*   The lambda expression used in forEach(), "d->System.out.println( new SimpleDateFormat("dd-MMM-yyyy").format(d) )", is printing the date in console for each given Date object.

Overall, the program is trying to find the next 10 "Friday The 13th" dates.

```
 13-Mar-2020
13-Nov-2020
13-Aug-2021
13-May-2022
13-Jan-2023
13-Oct-2023
13-Sep-2024
13-Dec-2024
13-Jun-2025
13-Feb-2026
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Java Modules - Java Package Aggregationxhtml

This chapter provides tutorial notes on Java modules. Topics include Java module descriptor; module dependency; exporting package out of module; creating module JAR/JMOD file; creating custom JRE with added modules; testing package visibilities.

> [What Is Java Module](#part0113.xhtml)
> 
> [Module Descriptor - module-info.java](#part0114.xhtml)
> 
> [Creating "Hello World!" Module](#part0115.xhtml)
> 
> ["jmod create" - Creating JMOD File](#part0116.xhtml)
> 
> ["jlink --add-modules" - Creating Custom JRE](#part0117.xhtml)
> 
> [Running ".\bin\java" Command in Custom JRE](#part0118.xhtml)
> 
> [Accessing Non-Exported Package in Module](#part0119.xhtml)
> 
> [Module Dependency and Package Accessibility](#part0120.xhtml)
> 
> [com.herongyang.base Module Implementation](#part0121.xhtml)
> 
> [com.herongyang.base Module Compilation](#part0122.xhtml)
> 
> [com.herongyang.math Module Implementation](#part0123.xhtml)
> 
> [geometryJRE and Module Deliverables](#part0124.xhtml)
> 
> [Getting com.herongyang.base Module Info](#part0125.xhtml)
> 
> [Testing Exported Package in Module](#part0126.xhtml)
> 
> [Testing Un-Exported Package in Module](#part0127.xhtml)
> 
> [Application using com.herongyang.math Module](#part0128.xhtml)

Conclusion:

*   Java modules were introduced in Java 9.
*   A Java module is a Java code and related file aggregation mechanism at a level higher than a Java Package.
*   A Java module uses a module descriptor, module-info.java, to declare its name, module dependency, and package export list.
*   A Java module uses a JMOD file to store the module class code and relate files, like legal notices.
*   "jmod" command is designed to create and manage JMOD files.
*   A Java module can also use a JAR file to store the module class code only. But a module JAR file is not able to store non-class files.
*   A Java module can be embedded in a custom JRE to help the distribution.
*   "javac" command supports "--add-modules" and "--module-path" to resolve module related type references.
*   Module JAR files or JMOD files can be used in "javac" module path.
*   "java" command supports "--add-modules" and "--module-path" to load required classes from Java modules.
*   Only module JAR files can be used in "java" module path. Module JMOD files can not be used at execution time.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟What Is Java Module

This section describes what is Java Module - a Java code and resource aggregation mechanism at a higher level than a Java Package.

**What Is Java Module**? A Java Module is a Java code and related file aggregation mechanism at a level higher than a Java Package.

A Java Module has 2 components:

*   A Java Module Code - Consists of a module descriptor file called module-info.java and a list of Java packages.
*   A Java Module Archive - Consists of the Java Module Code, and 5 other types of related resource files: native libraries, native commands, configurations, header files and legal notices.

Java modules were introduced in Java 9 with the following objectives:

*   Provide Better Code Dependency Management - Each module must explicitly declare its dependent modules.
*   Provide Stronger Code Encapsulation - Each module maintains a list of exported Java packages. Other modules can not access a package in Java module that is not exported.
*   Provide Scalable JRE (Java Runtime Environment) - Java platforms are divided into multiple small modules now. You can select only those modules required by your application to build a smaller custom JRE.
*   Provide Better Deployment Packaging - You can put all files required to run your application in a single module archive file.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Module Descriptor - module-info.java

This section describes the module descriptor file, module-info.java, which defines a new Java module with declarations of dependencies and exported packages.

The first thing you need to do to create a Java module is to create the module descriptor, module-info.java using the following template:

```
 module module_name {
   requires other_module_name;
   ...
   exports package_name;
   ...
}
```

This template allows you to:

*   Specify the module name as module_name. Java module names follow same rules as Java package names. For example, com.herongyang and org.apache.commons are good module names.
*   Declare a list of other modules as dependencies. For example, "requires java.base;" declares that this module uses packages exported from the java.base module.
*   Declare a list of packages to be exported from this module. For example, "exports com.herongyang.util;" declares that other modules can use com.herongyang.util.* classes defined in this module.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Creating "Hello World!" Module

This section provides a tutorial example on how to create a simple Java module with no information provided in the module descriptor. Module compilation and module class execution commands are also provided.

Let me start to create a simple Java module that has one class in one package:

*   Module name: com.herongyang
*   Package name: com.herongyang.greeting
*   Main class name: Hello.java

Here is how the source code directory tree looks like:

```
 herong> tree /F .\src
.\SRC
|---com.herongyang
    |   module-info.java
    |
    |---com
        |---herongyang
            |---greeting
                    Hello.java
```

Here are the 2 source files in the module:

```
 herong> more .\src\com.herongyang\module-info.java
module com.herongyang {
}

herong> more .\src\com.herongyang\com\herongyang\greeting\Hello.java
package com.herongyang.greeting;
public class Hello {
   public static void main(String[] a) {
      System.out.println("Hello world! - From Module");
   }
}
```

Here is what I did to compile the module and run the main class:

```
 herong> javac --module com.herongyang --module-source-path .\src \
   -d .\cls

herong> java --module-path .\cls \
   --module com.herongyang/com.herongyang.greeting.Hello

Hello world! - From Module
```

What I learned from this tutorial:

*   The source files should be placed under a sun-directory that matches the module name.
*   The module descriptor, module-info.java, should be placed in the root directory of the module, above all package directories.
*   No need to declare any dependencies in module-info.java, if you only use the "java.base" module.
*   No need to declare the export package list in module-info, if no other modules are using this module.
*   No special coded in the package class source code, Hello.java.
*   "javac --module ... --module-source-path ..." should be used to compile all source files in a module.
*   "java --module-path ... --module ..." can be used to launch a main class in module.
*   Class name needs to be prefixed with "module_name/" to launch class as a module class.

Note that the "java" command in JDK 10 seems to require you to specify "--module ..." option before "---module-path ..." option. Otherwise, you will get the "module ... not found" error:

```
 herong> java --module com.herongyang/com.herongyang.greeting.Hello \
   --module-path .\cls

Error occurred during initialization of boot layer
java.lang.module.FindException: Module com.herongyang not found
```

The module file directory structure is backward compatible. You can still launch any class in a module as a non-module class:

```
 herong> java -classpath .\cls\com.herongyang \
   com.herongyang.greeting.Hello

Hello world! - From Module
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟"jmod create" - Creating JMOD File

This section provides a tutorial example on how to crate a JMOD file to store all class files of a Java module and its related files using the 'jmod create' command.

After the Java module code is compiled, you can create archive all module classes and other related files into a single JMOD file using the "jmod create" command.

From the previous tutorial, I have all class files of the com.herongyang module compiled in the .\cls directory tree. Now I want to create a license file in the .\license sub directory:

```
 herong> more .\license\copyright.txt

Copyright (c) HerongYang.com, All Rights Reserved.
```

To create a JMOD file, I used the following "jmod" command:

```
 herong> jmod create --class-path .\cls\com.herongyang
   --legal-notices .\license com.herongyang.jmod

herong> jmod list com.herongyang.jmod
classes/module-info.class
classes/com/herongyang/greeting/Hello.class
legal/copyright.txt

herong> jmod describe com.herongyang.jmod
com.herongyang
requires java.base mandated
contains com.herongyang.greeting
```

The "jmod" command stores all class files in the .\classes sub-directory and legal notices in the .\legal sub-directory. If you have other types files included, other sub-directories will be created. For more information on JMOD file structure and "jmod" command, see "Java Tools Tutorials - Herong's Tutorial Examples" book at [herongyang.com/Java-Tools](https://www.herongyang.com/Java-Tools/).

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟"jlink --add-modules" - Creating Custom JRE

This section provides a tutorial example on how to create a custom JRE with your own Java module using the 'jlink --add-modules' command.

With module files packaged in a JMOD file, com.heronyang.jmod, you can create a custom JRE to this Java module only with the "jlink" command:

```
 herong> jlink --strip-debug --add-modules com.herongyang
   --module-path com.herongyang.jmod --output .\helloJRE
   --launcher hello=com.herongyang/com.herongyang.greeting.Hello

herong> .\helloJRE\bin\hello
Hello world! - From Module
```

Cool. I have written a simple Java application using Java module and created a custom JRE with launch script to run the application!

"jlink" command options used are:

*   "--strip-debug" - Turns on the flag to remove debug code in the output JRE.
*   "--add-modules com.herongyang" - Specifies which Java modules to included in the output JRE.
*   "--module-path com.herongyang.jmod" - Specifies locations where to find Java modules.
*   "--output .\helloJRE" - Specifies the sub-directory to store the output JRE.
*   "--launcher hello=com.herongyang/com.herongyang.greeting.Hello" - Specifies a new script name and which module class to launch with the script. The script file will be located in the .\bin sub-directory of output JRE.

Here is the output JRE directory tree looks like:

```
 herong> tree /F helloJRE
.\HELLOJRE
|   release
|
|---bin
|   |   hello
|   |   hello.bat
|   |   java.dll
|   |   java.exe
|   |   javaw.exe
|   |   jimage.dll
|   |   jli.dll
|   |   keytool.exe
|   |   msvcp120.dll
|   |   msvcr120.dll
|   |   net.dll
|   |   nio.dll
|   |   verify.dll
|   |   zip.dll
|   |
|   |---server
|           jvm.dll
|
|---conf
|   |   net.properties
|   |
|   |---security
|       |   java.policy
|       |   java.security
|       |
|       |---policy
|           |   README.txt
|           |
|           |---limited
|           |       default_local.policy
|           |       default_US_export.policy
|           |       exempt_local.policy
|           |
|           |---unlimited
|                   default_local.policy
|                   default_US_export.policy
|
|---include
|   |   classfile_constants.h
|   |   jni.h
|   |   jvmti.h
|   |   jvmticmlr.h
|   |
|   |---win32
|           jni_md.h
|
|---legal
|   |---com.herongyang
|   |       copyright.txt
|   |
|   |---java.base
|           aes.md
|           asm.md
|           cldr.md
|           COPYRIGHT
|           icu.md
|           LICENSE
|           public_suffix.md
|           zlib.md
|
|---lib
    |   classlist
    |   jrt-fs.jar
    |   jvm.cfg
    |   jvm.lib
    |   modules
    |   tzdb.dat
    |   tzmappings
    |
    |---security
    |       blacklist
    |       blacklisted.certs
    |       cacerts
    |       default.policy
    |       public_suffix_list.dat
    |       trusted.libraries
    |
    |---server
            Xusage.txt
```

I can no ZIP the .\helloJRE directory and distribute to it to my friend as a Java application JRE. He/she can run it directly without download any Java packages from Oracle.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Running ".\bin\java" Command in Custom JRE

This section provides a tutorial example on how to run '\bin\java' command from the custom JRE to list modules and launch Java classes.

With the application JRE created, you can use the "java --list-modules" command to verify what modules are in the JRE:

```
 herong> .\helloJRE\bin\java --list-modules
com.herongyang
java.base@10.0.1
```

Not surprised. The "java.base" module is included to provide all Java built-in packages.

You can also get module information using the "java --describe-module" command:

```
 herong> .\helloJRE\bin\java --describe-module com.herongyang
com.herongyang
requires java.base mandated
contains com.herongyang.greeting
```

You can also run the application class using the "java --module" command directly:

```
 herong> .\helloJRE\bin\java
   --module com.herongyang/com.herongyang.greeting.Hello

Hello world! - From Module
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Accessing Non-Exported Package in Module

This section provides a tutorial example showing that a non-exported package in a Java module can not be accessed outside of the module.

After created the com.herongyang module, can I write another Java program to use the Java package and class in the module?

The answer is yes. Here is a simple program that tries to use the com.herongyang.greeting package in the com.herongyang module:

```
 import com.herongyang.greeting.Hello;
public class Greeting {
   public static void main(String[] a) {
      Hello.main(a);
   }
}
```

But when I tried to compile it with the module file, com.herongyang.jmod, I got this error:

```
 herong> javac --module-path com.herongyang.jmod Greeting.java
Greeting.java:1: error: package com.herongyang.greeting is not visible
import com.herongyang.greeting.Hello;
                     ^
  (package com.herongyang.greeting is declared in module com.herongyang,
   which is not in the module graph)
1 error
```

The error message is pretty clear. The compiler found the com.herongyang.jmod file. But the com.herongyang.greeting is not visible, because it is not exported to the outside of the module. So access is denied.

However, since I have module class files in the .\cls\com.herongyang directory, I can compile and run Greeting.java with the class path instead of the module path:

```
 herong> javac -classpath .\cls\com.herongyang Greeting.java

herong> dir Greeting.*
   314 Greeting.class
   135 Greeting.java

herong> java -classpath .;.\cls\com.herongyang Greeting
Hello world! - From Module
```

This tutorial demonstrates that Java module can protect your Java packages and classes from others to use them, if they are not exported. But others can still use the class path option instead of module path to by-pass the module protection.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Module Dependency and Package Accessibility

This section provides a tutorial example showing how to design two modules with dependency and package accessibility.

In previous tutorials, we learned how to create a Java module, compile it, package it into a JMOD file, and build a custom JRE with it.

Now I will create 2 Java modules to learn how to use "requires" and "exports" statements in the module descriptor, module-info.java.

**The com.herongyang.base module** - It has the following packages to provide basic classes:

*   The com.herongyang.point package has the Point class to represent a point. It will be exported to outside of the module.
*   The com.herongyang.line package has the Line class to represent a line. It will be exported to outside of the module.
*   The com.herongyang.vector package has the Vector class to support Line objects and their operations. It will be hidden inside the module.

Here is the module-info.java of the com.herongyang.base module:

```
 herong> more .\src\com.herongyang.base\module-info.java

/* module-info.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
module com.herongyang.base {
   exports com.herongyang.point;
   exports com.herongyang.line to com.herongyang.math;
}
```

In the above module descriptor, I have used the following access controls:

*   "com.herongyang.point" package is exported to all other modules.
*   "com.herongyang.line" package is exported to "com.herongyang.math" module only.
*   "com.herongyang.vector" package is not exported at all. Other modules can not access it.

Here is the module-info.java of the com.herongyang.math module:

```
 herong> more .\src\com.herongyang.math\module-info.java

/* module-info.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
module com.herongyang.math {
   requires com.herongyang.base;
   exports com.herongyang.geometry;
}
```

In the above module descriptor, I declared that:

*   "com.herongyang.geometry" package is exported to all other modules.
*   "com.herongyang.module" module is required to run this module.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟com.herongyang.base Module Implementation

This section describes how the com.herongyang.base module is implemented with 3 classes in 3 packages: Point.java, Vector.java and Line.java.

With com.herongyang.base module designed in the previous tutorial, let me now implement its packages and classes.

The com.herongyang.point package has the Point class to represent a point in the 3 dimensional space:

```
 herong> more src\com.herongyang.base\com\herongyang\point\Point.java

/* Point.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
package com.herongyang.point;
public class Point {
   public double x = 0.0;
   public double y = 0.0;
   public double z = 0.0;
   public Point(double x, double y, double z) {
      this.x = x;
      this.y = y;
      this.z = z;
   }
   public double distance(Point t) {
      return Math.sqrt((t.x-x)*(t.x-x)+(t.y-y)*(t.y-y)+(t.z-z)*(t.z-z));
   }
   public static void main(String[] a) {
      Point p = new Point(1, 0, 0);
      Point q = new Point(0, 1, 0);
      System.out.println("Point p = ("+p.x+", "+p.y+", "+p.z+")");
      System.out.println("Point q = ("+q.x+", "+q.y+", "+q.z+")");
      System.out.println("Distance from p to q = "+p.distance(q));
   }
}
```

The com.herongyang.vector package has the Vector class to represent a vector in the 3 dimensional space:

```
 /* Vector.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
package com.herongyang.vector;
public class Vector {
   public double x = 0.0;
   public double y = 0.0;
   public double z = 1.0;
   public Vector (double x, double y, double z) {
      this.x = x;
      this.y = y;
      this.z = z;
   }
   public double length() {
      return Math.sqrt(x*x + y*y + z*z);
   }
   public Vector crossProduct(Vector v) {
      Vector w = new Vector(y*v.z-z*v.y, z*v.x-x*v.z, x*v.y-y*v.x);
      return w;
   }
   public static void main(String[] a) {
      Vector i = new Vector(1, 0, 0);
      Vector j = new Vector(0, 1, 0);
      Vector k = i.crossProduct(j);
      System.out.println("Vector i = ("+i.x+", "+i.y+", "+i.z+")");
      System.out.println("Vector j = ("+j.x+", "+j.y+", "+j.z+")");
      System.out.println("i x j = ("+k.x+", "+k.y+", "+k.z+")");
   }
}
```

The com.herongyang.line package has the Line class to represent a line in the 3 dimensional space:

```
 herong> more src\com.herongyang.base\com\herongyang\line\Line.java

/* Line.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
package com.herongyang.line;
import com.herongyang.point.Point;
import com.herongyang.vector.Vector;
public class Line {
   public Point p = new Point(0, 0, 0);
   public Vector v = new Vector(1, 0, 0);
   public Line(Point p, Vector v) {
      this.p = p;
      this.v = v;
   }
   public Line(Point p, Point q) {
      this.p = p;
      this.v = new Vector(q.x-p.x, q.y-p.y, q.z-p.z);
   }
   public double distance(Point t) {
      // distance = length(w)/length(v)
      // where w = cross_product of (pt, v) and pt = vector from p to t
      Vector pt = new Vector(t.x-p.x, t.y-p.y, t.z-p.z);
      Vector w = pt.crossProduct(v);
      return w.length()/v.length();
   }
   public static void main(String[] a) {
      Point p = new Point(0, 0, 0);
      Vector v = new Vector(1, 0, 0);
      Line l = new Line(p, v);
      System.out.println("Line point = ("+p.x+", "+p.y+", "+p.z+")");
      System.out.println("Line direction = ("+v.x+", "+v.y+", "+v.z+")");
      Point t = new Point(0, 1, 0);
      System.out.println("Point t = ("+t.x+", "+t.y+", "+t.z+")");
      System.out.println("Distance from t to line = "+l.distance(t));
   }
}
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟com.herongyang.base Module Compilation

This section provides a tutorial example on how to compile the com.herongyang.base module.

Here is what I did to compile the com.herongyang.base module and run the main() method in each class for some testing.

```
 herong> javac --module com.herongyang.base \
   --module-source-path .\src -d .\cls

herong> java --module-path .\cls \
   --module com.herongyang.base/com.herongyang.point.Point
Point p = (1.0, 0.0, 0.0)
Point q = (0.0, 1.0, 0.0)
Distance from p to q = 1.4142135623730951

herong> java --module-path .\cls \
   --module com.herongyang.base/com.herongyang.vector.Vector
Vector i = (1.0, 0.0, 0.0)
Vector j = (0.0, 1.0, 0.0)
i x j = (0.0, 0.0, 1.0)

herong> java --module-path .\cls \
   --module com.herongyang.base/com.herongyang.line.Line
Line point = (0.0, 0.0, 0.0)
Line direction = (1.0, 0.0, 0.0)
Point t = (0.0, 1.0, 0.0)
Distance from t to line = 1.0
```

The compilation and testing went ok with no issues.

Then I created a JAR file and a JMOD for this module:

```
 herong> jar --create --file com.herongyang.base.jar \
   -C .\cls\com.herongyang.base .

herong> jmod create --class-path .\cls\com.herongyang.base \
   com.herongyang.base.jmod

herong> dir com.herongyang.base.*
   4,260 com.herongyang.base.jar
   3,466 com.herongyang.base.jmod
```

Actually, you only need to put the module in a JAR file, if the module only have Java class and property files. The JMOD file is used if you have other types of files that needs to be distributed together.

Then I tested all classes again from the JAR file:

```
 herong> java --module-path com.herongyang.base.jar \
   --module com.herongyang.base/com.herongyang.point.Point
Point p = (1.0, 0.0, 0.0)
Point q = (0.0, 1.0, 0.0)
Distance from p to q = 1.4142135623730951

herong> java --module-path com.herongyang.base.jar \
   --module com.herongyang.base/com.herongyang.vector.Vector
Vector i = (1.0, 0.0, 0.0)
Vector j = (0.0, 1.0, 0.0)
i x j = (0.0, 0.0, 1.0)

herong> java --module-path com.herongyang.base.jar \
   --module com.herongyang.base/com.herongyang.line.Line
Line point = (0.0, 0.0, 0.0)
Line direction = (1.0, 0.0, 0.0)
Point t = (0.0, 1.0, 0.0)
Distance from t to line = 1.0
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟com.herongyang.math Module Implementation

This section describes how the com.herongyang.math module is implemented with 1 class in 1 package: Geometry.java.

With com.herongyang.base module fully implemented, I can now implement the com.herongyang.math module.

The com.herongyang.geometry package has the Geometry class with 2 static methods:

```
 herong> more src\com.herongyang.base\com\herongyang\point\Point.java

/* Geometry.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
package com.herongyang.geometry;
import com.herongyang.point.Point;
import com.herongyang.line.Line;
public class Geometry {
   public static double p2p(double a1, double a2, double a3,
      double b1, double b2, double b3) {
      Point a = new Point(a1,a2,a3);
      Point b = new Point(b1,b2,b3);
      return a.distance(b);
   }
   public static double p2l(double p1,double p2, double p3,
      double a1, double a2, double a3, double b1, double b2, double b3) {
      Point p = new Point(p1,p2,p3);
      Point a = new Point(a1,a2,a3);
      Point b = new Point(b1,b2,b3);
      Line l = new Line(a,b);
      return l.distance(p);
   }
   public static void main(String[] args) {
      double p2p = p2p(1,0,0, 0,1,0);
      System.out.println(
         "Point to point distance: (1,0,0) and (0,1,0) = "+p2p);
      double p2l = p2l(0,0,1, 0,0,0, 1,1,1);
      System.out.println(
         "Point to line distance: (0,0,1) and (0,0,0)-(1,1,1) = "+p2l);
   }
}
```

Compilation of com.herongyang.math requires com.herongyang.base to be accessible:

```
 herong> javac -d .\cls --module-path com.herongyang.base.jar \
   --module-source-path .\src --module com.herongyang.math
```

Running the main() method of the Geometry.java also requires com.herongyang.base to be accessible:

```
 C:\herong\>java --module-path .\cls;com.herongyang.base.jar \
   --module com.herongyang.math/com.herongyang.geometry.Geometry
Point to point distance: (1,0,0) and (0,1,0) = 1.4142135623730951
Point to line distance: (0,0,1) and (0,0,0)-(1,1,1) = 0.8164965809277261
```

Then I created a JAR file and a JMOD for this module:

```
 herong> jar --create --file com.herongyang.math.jar
   -C .\cls\com.herongyang.math .

herong> jmod create --class-path .\cls\com.herongyang.math \
   com.herongyang.math.jmod

herong> dir com.herongyang.math.*
   1,923 com.herongyang.math.jar
   1,327 com.herongyang.math.jmod
```

Then I tested all classes again from the JAR file:

```
 herong> java \
   --module-path com.herongyang.math.jar;com.herongyang.base.jar \
   --module com.herongyang.math/com.herongyang.geometry.Geometry
Point to point distance: (1,0,0) and (0,1,0) = 1.4142135623730951
Point to line distance: (0,0,1) and (0,0,0)-(1,1,1) = 0.8164965809277261
```

Everything went nicely so far without any issues!

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟geometryJRE and Module Deliverables

This section describes how the com.herongyang.math module is implemented with 1 class in 1 package: Geometry.java.

With both modules, com.herongyang.base and com.herongyang.math, ready, I can now build a custom JRE with the "jlink" command:

```
 herong> jlink --strip-debug
   --module-path com.herongyang.math.jar;com.herongyang.base.jar \
   --launcher geometry=com.herongyang.math/com.herongyang.geometry.Geometry \
   --add-modules com.herongyang.math --output geometryJRE

herong> geometryJRE\bin\geometry
Point to point distance: (1,0,0) and (0,1,0) = 1.4142135623730951
Point to line distance: (0,0,1) and (0,0,0)-(1,1,1) = 0.8164965809277261
```

Now I have completed my Java module project with the following:

*   Module source code: .\src\* - It has all Java source files for both modules. I will keep it for myself.
*   Module JAR files: com.herongyang.base.jar;com.herongyang.math.jar - It has all Java class files for both modules. I can give it to anyone who wants to create a new Java application that uses my modules. He/she can use it to compile and execute the new application.
*   Module JMOD files: com.herongyang.base.jmod;com.herongyang.math.jmod - It has all Java class files for both modules. I can give it to anyone who wants to create a new Java application that uses my modules. He/she can use it to compile the new application. To execute the new application, he/she needs to create a custom JRE from JMOD files first.
*   Module JRE: .\geometryJRE\* - It has a custom JRE with my modules embedded inside. I can give it to anyone who wants to run new applications that uses my modules.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Getting com.herongyang.base Module Info

This section describes how to get module information, list of classes, and class API from the module JAR file, JMOD file or the custom JRE environment.

With com.herongyang.base module delivered in JAR, JMOD and JRE format, there several ways to get module information and class information:

If I want to get module information, I can get it from the JAR file, the JMOD file, or the custom JRE environment:

```
 herong> jar --describe-module --file com.herongyang.base.jar

com.herongyang.base
   jar:file:///C:/herong/com.herongyang.base.jar/!module-info.class
exports com.herongyang.point
requires java.base mandated
qualified exports com.herongyang.line to com.herongyang.math
contains com.herongyang.vector

herong> jmod describe com.herongyang.base.jmod

com.herongyang.base
exports com.herongyang.point
requires java.base mandated
qualified exports com.herongyang.line to com.herongyang.math
contains com.herongyang.vector

herong> geometryJRE\bin\java --describe-module com.herongyang.base

com.herongyang.base
exports com.herongyang.point
requires java.base mandated
qualified exports com.herongyang.line to com.herongyang.math
contains com.herongyang.vector

herong> java --add-modules com.herongyang.base \
   --module-path com.herongyang.base.jar \
   --describe-module com.herongyang.base

com.herongyang.base file:///C:/herong/com.herongyang.base.jar
exports com.herongyang.point
requires java.base mandated
qualified exports com.herongyang.line to com.herongyang.math
contains com.herongyang.vector
```

If I want to see what classes are provided in the com.herongyang.point package, I can use the JMOD file or the JAR file:

```
 herong> jmod list com.herongyang.base.jmod

classes/module-info.class
classes/com/herongyang/line/Line.class
classes/com/herongyang/point/Point.class
classes/com/herongyang/vector/Vector.class

herong> jar --list --file com.herongyang.base.jar

META-INF/
META-INF/MANIFEST.MF
module-info.class
com/
com/herongyang/
com/herongyang/line/
com/herongyang/line/Line.class
com/herongyang/point/
com/herongyang/point/Point.class
com/herongyang/vector/
com/herongyang/vector/Vector.class
```

If I want to see the API of the com.herongyang.point.Point class, I can use the JAR file, or the JMOD file:

```
 herong> javap --module-path com.herongyang.base.jar \
   --module com.herongyang.base com.herongyang.point.Point

Compiled from "Point.java"
public class com.herongyang.point.Point {
  public double x;
  public double y;
  public double z;
  public com.herongyang.point.Point(double, double, double);
  public double distance(com.herongyang.point.Point);
  public static void main(java.lang.String[]);
}

herong> javap --module-path com.herongyang.base.jmod \
   --module com.herongyang.base com.herongyang.point.Point

Compiled from "Point.java"
public class com.herongyang.point.Point {
  public double x;
  public double y;
  public double z;
  public com.herongyang.point.Point(double, double, double);
  public double distance(com.herongyang.point.Point);
  public static void main(java.lang.String[]);
}
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Testing Exported Package in Module

This section provides a tutorial example on how to write, compile and run a program to test an exported package from a Java module.

I have the com.herongyang.base module in JAR, JMOD and JRE format, and I know the com.herongyang.point package is exported from the module. Now I want to write a simple Java programs to test Point class in that package.

```
 /* PointTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import com.herongyang.point.Point;
public class PointTest {
   public static void main(String[] args) {
      Point a = new Point(0,0,0);
      Point b = new Point(1,1,1);
      double distance = a.distance(b);
      System.out.println("Point a = ("+a.x+", "+a.y+", "+a.z+")");
      System.out.println("Point b = ("+b.x+", "+b.y+", "+b.z+")");
      System.out.println("Distance from a to b = "+distance);
   }
}
```

Compilation can use the JAR file or the JMOD file. But it requires me to add my module to the root module list:

```
 herong> javac --module-path com.herongyang.base.jmod PointTest.java

PointTest.java:4: error: package com.herongyang.point is not visible
import com.herongyang.point.Point;
                     ^
(package com.herongyang.point is declared in module com.herongyang.base,
which is not in the module graph)
1 error

herong> javac --module-path com.herongyang.base.jmod \
   --add-modules com.herongyang.base PointTest.java

herong> javac --module-path com.herongyang.base.jar \
   --add-modules com.herongyang.base PointTest.java
```

I can not use the JMOD file for execution. But I can use the JAR file for execution.

```
 herong> java --module-path com.herongyang.base.jmod PointTest

Error occurred during initialization of boot layer
java.lang.module.FindException: JMOD format not supported at execution
time: com.herongyang.base.jmod

herong> java --module-path com.herongyang.base.jar PointTest
Exception in thread "main" java.lang.NoClassDefFoundError:
   com/herongyang/point/Point

        at PointTest.main(PointTest.java:7)
Caused by: java.lang.ClassNotFoundException: com.herongyang.point.Point
        ... 1 more

herong> java --module-path com.herongyang.base.jar \
   --add-modules com.herongyang.base PointTest

Point a = (0.0, 0.0, 0.0)
Point b = (1.0, 1.0, 1.0)
Distance from a to b = 1.7320508075688772
```

Or I can use the customJRE environment, which already has my modules embedded inside.

```
 herong> geometryJRE\bin\java PointTest

Point a = (0.0, 0.0, 0.0)
Point b = (1.0, 1.0, 1.0)
Distance from a to b = 1.7320508075688772
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Testing Un-Exported Package in Module

This section provides a tutorial example showing compilation errors on programs trying to access un-exported packages from a Java module.

In the previous tutorial, I wrote a simple program to test the Point class in the exported package, com.herongyang.point in the com.herongyang.base module.

In this tutorial, I want to test the other two packages. One is exported to named module only, and another is not exported at all:

```
 herong> jar --describe-module --file com.herongyang.base.jar

com.herongyang.base
   jar:file:///C:/herong/com.herongyang.base.jar/!module-info.class
exports com.herongyang.point
requires java.base mandated
qualified exports com.herongyang.line to com.herongyang.math
contains com.herongyang.vector
```

Here is my test on the com.herongyang.vector package, which is not exported:

```
 herong> more VectorTest.java
/* VectorTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import com.herongyang.vector.Vector;
public class VectorTest {
   public static void main(String[] args) {
      Vector.main(args);
   }
}

herong> javac --module-path com.herongyang.base.jar VectorTest.java
VectorTest.java:4: error: package com.herongyang.vector is not visible
import com.herongyang.vector.Vector;
                     ^
(package com.herongyang.vector is declared in module com.herongyang.base,
which is not in the module graph)
1 error

herong> javac --module-path com.herongyang.base.jar \
   --add-modules com.herongyang.base VectorTest.java

VectorTest.java:4: error: package com.herongyang.vector is not visible
import com.herongyang.vector.Vector;
                     ^
(package com.herongyang.vector is declared in module com.herongyang.base,
which does not export it)
1 error
```

I can not compile my test program, VectorTest.java, because the com.herongyang.vector package is not accessible. It is designed to be used by the module itself, not others.

Here is my test on the com.herongyang.line package, which is not exported:

```
 herong> more LineTest.java

/* LineTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import com.herongyang.line.Line;
public class LineTest {
   public static void main(String[] args) {
      Line.main(args);
   }
}

herong> javac --module-path com.herongyang.base.jar LineTest.java

LineTest.java:4: error: package com.herongyang.line is not visible
import com.herongyang.line.Line;
                     ^
(package com.herongyang.line is declared in module com.herongyang.base,
which is not in the module graph)
1 error

herong> javac --module-path com.herongyang.base.jar \
  --add-modules com.herongyang.base LineTest.java

LineTest.java:4: error: package com.herongyang.line is not visible
import com.herongyang.line.Line;
                     ^
(package com.herongyang.line is declared in module com.herongyang.base,
which does not export it to the unnamed module)
1 error
```

I can not compile my test program, LineTest.java, because the com.herongyang.line package is not accessible. It is designed to be used by the com.herongyang.math module only, not others.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Java Modules - Java Package Aggregation](#part0112.xhtml)

∟Application using com.herongyang.math Module

This section provides tutorial example of a simple Java application that allows to calculate the distance from a point to a line using the com.herongyang.math Java module.

Finally, let close this chapter on Java modules with a simple geometry application that allows to calculate the distance from a point to a line using the com.herongyang.math Java module:

Here is the source code of the application, PointToLineDistance.java:

```
 /* PointToLineDistance.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import com.herongyang.geometry.Geometry;
import java.io.*;
public class PointToLineDistance {
   public static void main(String[] args) {
      BufferedReader in = new BufferedReader(
         new InputStreamReader(System.in));
      PrintStream out = System.out;
      out.println(
         "This program calculates the distance from a point to a line.");
      out.println("Enter coordinates (e.g. 0,0,1) of the point,");
      out.println("or 'no' to exit:");
      try {
         String s = in.readLine();
         while (s!=null) {
            if (s.equals("no")) break;
            try {
               String[] tokens = s.split(", *");
               double x1 = Double.parseDouble(tokens[0]);
               double x2 = Double.parseDouble(tokens[1]);
               double x3 = Double.parseDouble(tokens[2]);

               out.println(
                  "Enter first location (e.g. 0,0,0) of the line:");
               s = in.readLine();
               tokens = s.split(", *");
               double a1 = Double.parseDouble(tokens[0]);
               double a2 = Double.parseDouble(tokens[1]);
               double a3 = Double.parseDouble(tokens[2]);

               out.println(
                  "Enter second location (e.g. 1,0,0) of the line:");
               s = in.readLine();
               tokens = s.split(", *");
               double b1 = Double.parseDouble(tokens[0]);
               double b2 = Double.parseDouble(tokens[1]);
               double b3 = Double.parseDouble(tokens[2]);
               double length = Geometry.p2p(a1,a2,a3, b1,b2,b3);
               if (length<0.000001) {
                  out.println("Two locations are too close.");
               } else {
                  double distance =
                     Geometry.p2l(x1,x2,x3, a1,a2,a3, b1,b2,b3);
                  out.println("Distance from point to line: "+distance);
               }
            } catch (Exception e) {
               out.println("Input is invalid.");
            }
            out.println("Enter coordinates (e.g. 0,0,1) of the point,");
            out.println("or 'no' to exit:");
            s = in.readLine();
         }
      } catch (Exception e) {
         out.println("Something went wrong.");
      }
   }
}
```

To compile the application, I need to add com.herongyang.math as a root module, and provide the module in the module path:

```
 herong> javac --module-path com.herongyang.math.jmod \
   --add-modules com.herongyang.math PointToLineDistance.java
```

To execute the application, I can use the standard JRE and add com.herongyang.math as a root module. The "java" command will find its required module, com.herongyang.base, from the module path.

```
 herong> java --module-path com.herongyang.math.jmod \
   --add-modules com.herongyang.math PointToLineDistance

Error occurred during initialization of boot layer
java.lang.module.FindException: JMOD format not supported at execution
time: com.herongyang.math.jmod

herong> java --module-path com.herongyang.math.jar \
   --add-modules com.herongyang.math PointToLineDistance

Error occurred during initialization of boot layer
java.lang.module.FindException: Module com.herongyang.base not found,
required by com.herongyang.math

herong> java \
   --module-path com.herongyang.math.jar;com.herongyang.base.jar \
   --add-modules com.herongyang.math PointToLineDistance

This program calculates the distance from a point to a line.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
```

Or I can execute it with the custom JRE, geometryJRE, which has both modules embedded inside:

```
 herong> geometryJRE\bin\java PointToLineDistance

This program calculates the distance from a point to a line.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
0,0,1
Enter first location (e.g. 0,0,0) of the line:
0,0,0
Enter second location (e.g. 1,0,0) of the line:
1,0,0
Distance from point to line: 1.0
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
0,1,1
Enter first location (e.g. 0,0,0) of the line:
0,0,0
Enter second location (e.g. 1,0,0) of the line:
1,0,0
Distance from point to line: 1.4142135623730951
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
```

The application can detect invalid input values:

```
 herong> geometryJRE\bin\java PointToLineDistance

This program calculates the distance from a point to a line.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
junk
Input is invalid.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
0,0,1
Enter first location (e.g. 0,0,0) of the line:
junk
Input is invalid.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
0,0,1
Enter first location (e.g. 0,0,0) of the line:
0,0,0
Enter second location (e.g. 1,0,0) of the line:
1,1,1
Distance from point to line: 0.8164965809277261
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
```

The application also has logic to avoid overflow condition:

```
 herong> geometryJRE\bin\java PointToLineDistance

This program calculates the distance from a point to a line.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
0,0,1
Enter first location (e.g. 0,0,0) of the line:
0,0,0
Enter second location (e.g. 1,0,0) of the line:
0.0000001,0,0
Two locations are too close.
Enter coordinates (e.g. 0,0,1) of the point,
or 'no' to exit:
```

Okay. I think I have a good understanding of Java Modules now. What do you think?

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Execution Threads and Multi-Threading Java Programs

This chapter provides tutorial notes and tutorial examples on execution threads and multi-threading programs. Topics include creating threads with thread classes and runnable objects; thread priorities and CPU time sharing; application data sharing; terminating running threads.

> [What Are Processes and Threads](#part0130.xhtml)
> 
> [The "Thread" Class - Creating Thread Objects With Thread Sub Classes](#part0131.xhtml)
> 
> [The "Runnable" Interface - Creating Thread Objects with Runnable Objects](#part0132.xhtml)
> 
> [CPU Execution Time Shared by Multiple Threads](#part0133.xhtml)
> 
> [CPU Execution Time Shared by Multiple Threads - Test Output](#part0134.xhtml)
> 
> [Application Data Shared by Multiple Threads](#part0135.xhtml)
> 
> [Application Data Shared by Multiple Threads - Test Results](#part0136.xhtml)
> 
> [interrupt() - Method to Terminate Thread](#part0137.xhtml)

Conclusion:

*   Multi-threading means an application can execute multiple sections of codes simultaneously.
*   A thread can be created with the Thread class.
*   Multi-threading improves overall performance of an application that supports multi-user interactions.
*   Multi-threading does not really make calculation faster in an application if it has no I/O wait time.
*   Multi-threading makes it harder to keep shared data in synch.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟What Are Processes and Threads

This section describes processes of multi-tasking operating systems and threads of multi-threading applications. Java is a programming language that allows you write multi-threading applications.

What is a thread? What is a process? Answers are in the following explanations:

There are 3 levels of executions of computer instructions on a computer system:

*   **CPU Level**: There is only one flow of execution on the central processing unit (CPU), that is the operating system (OS).
*   **OS Level**: For a multi-tasking OS, multiple application programs can be managed to be executed simultaneously. Here, a flow of execution is called a **process**.
*   **Application Level**: For a well written application program, multiple sections of codes can be managed to be executed simultaneously. Here, a flow of execution is called a **thread**. A program that can manage multiple threads is called a multi-threading program.

A good example of multi-threading programs are computer games that simulate real time activities of multiple human characters and/or moving objects.

Under the Java architecture, the Java virtual machine (JVM) will provide all the help you need to create and manage multiple threads in your Java applications. Read subsequent sections for tutorial examples.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟The "Thread" Class - Creating Thread Objects With Thread Sub Classes

This section provides a tutorial example on how to create new threads with your own classes extended from the 'Thread' class. You need to override the run() method in your own classes.

The first way to create a new thread in a Java program is to:

*   Extend a new class out of the "Thread" class.
*   Define the run() method in the new class to override the run() method in the Thread class.
*   Instantiate a new object of the new class.
*   Call the start() method on the new object.

Here is a tutorial sample program showing you how to do this:

```
 /* HelloThread.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class HelloThread extends Thread {
   public static void main(String[] a) {
      HelloThread t = new HelloThread();
      t.start();
      System.out.println("Hello world! - From the main program.");
   }
   public void run() {
      System.out.println("Hello world! - From a thread.");
      try {
         sleep(1000*60*60);
      } catch (InterruptedException e) {
         System.out.println("Interrupted.");
      }
   }
}
```

Output:

```
 Hello world! - From the main program.
Hello world! - From a thread.
```

A couple of things you should know about this program:

*   This program will run (actually sleep) for about one hour, after printing those messages. So you may need to press Ctrl-C to terminate the program.
*   There will be actually two threads running in this program. The first one is the main thread executing the all the statement in the main() method. The second one is a sub-thread launched by the t.start() statement. The sub-thread executes all the statements in the run() method.
*   Notice the order of the messages printed out on the console. It tells us that the sub-thread took a little bit longer to run its first statement, after it has been launched by the main thread.
*   A multi-threading program will not terminate until all its threads has reached the end of their execution. In our example, the main thread will end after printing its message. But the sub-thread will need about one hour to execute the sleep() call statement. So the entire program will not terminate until the sub-thread ends.
*   The run() method in the Thread is empty, so if you want a thread to do some work, you need to override the run() method.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟The "Runnable" Interface - Creating Thread Objects with Runnable Objects

This section provides a tutorial example on how to create new threads with the 'Thread' class and runnable objects, which are created with classes that implements the 'Runnable' interface.

The second way to create a new thread is to:

*   Implement the "Runnable" interface in your own class.
*   Implement the run() method defined in the "Runnable" interface in your own class.
*   Instantiate a runnable object of your own class.
*   Instantiate a thread object of the "Thread" class with the runnable object specified.
*   Call the start() method on the new object.

Here is a tutorial sample program showing you how to do this:

```
 /* HelloRunnable.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class HelloRunnable implements Runnable {
   public static void main(String[] a) {
      HelloRunnable r = new HelloRunnable();
      Thread t = new Thread(r);
      t.start();
      System.out.println("Hello world! - From the main program.");
   }
   public void run() {
      System.out.println("Hello world! - From a thread.");
      try {
         Thread.sleep(1000*60*60);
      } catch (InterruptedException e) {
         System.out.println("Interrupted.");
      }
   }
}
```

Output:

```
 Hello world! - From the main program.
Hello world! - From a thread.
```

Note that:

*   The program behaves the same way as the previous program: HelloThread.
*   The Thread object t is created with the special Thread constructor, which takes a Runnable object as input. If you start a Thread object created in this way, the run() method of the Runnable object will be executed as a new thread.
*   Since our class is not extending the Thread class any more, we need to call the sleep() explicitly by prefixing the class name: Thread.

May be you are wondering why we need the second way of creating a new thread, which seems to be less straight forward than the first way? The answer is that Java classes can not be extended from two different base classes. So if you are in a situation where you want to create a new class by extending an existing class to inherit some nice features of that class, and you also want to make the new class executable as a thread, you have to use the second way to implement the "Runnable" interface in your new class.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟CPU Execution Time Shared by Multiple Threads

This section provides a tutorial example on how to measuring CPU execution time allocated to threads with different setPriorities.

Question: If there are 5 application programs running on a single CPU system, and there are 5 threads running in each of the 5 running application programs, how all the 25 threads get executed simultaneously on that one CPU?

The answer is that those 25 threads do not get executed simultaneous at any given instance of time. They get executed one at a time in turns to share the processing time of the single CPU. The following simple example illustrates how the processing time can be shared by multiple threads.

Assuming that:

*   The operating system is designed to execute the running application program one at a time in turns. For each turn, the selected application get executed for only 1 millisecond.
*   If an application program gets executed, it will execute the running threads one at a time in turns. For each turn, the selected thread gets executed for only 0.01 millisecond.
*   There are 5 threads running in each of the 5 running application programs.
*   The times spend on switch threads and application program in the CPU are ignorable.

If we let the system runs for 0.1 second, each application program will be executed 20 times for a total time of 20 milliseconds, and each thread will be executed 400 times for a total time of 4 milliseconds. So, for a fraction of a second (1/10 second), all threads in all applications programs will be executed for about 4 milliseconds. This will make you feel like all threads get executed simultaneously.

Now let's use the following program to see how each thread is getting its share of the CPU time:

```
 /* RacingThread.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class RacingThread extends Thread {
   private static final long s_maxi = 1000000; // maximum # of steps
   private static final int t_maxi = 5; // maximum # of threads
   private static long[] t_done = new long[t_maxi];
   private static int t_last = -1; // index of the last thread
   private int t_indx;
   private static int n_prime = 0;
   public static void main(String[] a) {
      System.out.println("Priority: (min, norm, max) = ("+
         Thread.MIN_PRIORITY+", "+
         Thread.NORM_PRIORITY+", "+
         Thread.MAX_PRIORITY+")");
      long start_time = new Date().getTime();
      for (int i=0; i<t_maxi; i++) {
         RacingThread t = new RacingThread();
         if (i==0) t.setPriority(Thread.MIN_PRIORITY);
         else if (i==1) t.setPriority(Thread.NORM_PRIORITY);
         else t.setPriority(Thread.MAX_PRIORITY);
         t.start();
      }
      System.out.print("Threads: ");
      for (int i=0; i<t_maxi; i++) {
         System.out.print(i+" ");
      }
      System.out.print("Time");
      while(true) {
         try {
            sleep(100);
         } catch (InterruptedException e) {
            System.out.println("Interrupted.");
         }
         System.out.print("\n  Steps: ");
         for (int i=0; i<t_maxi; i++) {
            System.out.print(t_done[i]+" ");
         }
         System.out.print((new Date()).getTime()-start_time);
      }
   }
   public RacingThread() {
      t_last++;
      t_indx = t_last;
      t_done[t_indx] = 0;
   }
   public void run() {
      for (long s=0; s<s_maxi; s++) {
         int n = 0;
         for (int i=3; i<100; i++) {// keep it busy for some time
            boolean is_prime = true;
            for (int j=2; j<i; j++) {
               is_prime = (i%j>0);
               if (!is_prime) break;
            }
            if (is_prime) n++;
         }
         n_prime = n;
         t_done[t_indx] = s;
      }
   }
}
```

Notes on the program design:

*   5 sub-threads are created to do the same piece of work at each step. Steps are repeated for 1000000 times.
*   That same piece of work is to count how many prime numbers are there under 100.
*   The first sub-thread is given the lowest priority, the second sub-thread is given the medium priority, and the rest 3 sub-threads are given the highest priority.
*   Each sub-thread is recording the number of steps it has finished so far at the end of each step.
*   The main thread is repeatedly checking the recording array to see the execution progress of each sub-threads.
*   The elapse time in milliseconds is also reported each time the main thread is checking the recording array.
*   Each sub-thread is identified by an index number given in the constructor with the help of a static variable: t_last.
*   The static variable, n_prime, is updated by all 5 sub-threads repeatedly with the same value. I don't give any statement to print out the value of n_prime to verify the accuracy, but I did check the correctness of my prime number counting algorithm in a separate program.
*   The main thread will never end by itself. You need to press Ctrl-C to terminate the program.

See the next section for execution output of this program.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟CPU Execution Time Shared by Multiple Threads - Test Output

This section provides the test output of a tutorial example on how to measuring CPU execution time allocated to threads with different setPriorities.

I executed the program presented in the previous section on my Windows system, and got the following output.

```
 Priority: (min, norm, max) = (1, 5, 10)
Threads: 0 1 2 3 4 Time
  Steps: 1527 2229 161931 31864 29386 17416
  Steps: 3193 3881 175188 44342 41757 20301
  Steps: 6499 5536 204244 74234 71608 27221
  Steps: 8164 10495 244791 114110 112329 36475
  Steps: 11491 10495 257239 142209 139702 43025
  Steps: 13157 13805 285516 154633 152887 45909
  Steps: 14820 15458 297916 167948 165368 48793
  Steps: 16484 18763 327732 197825 195242 59009
  Steps: 19817 22073 369925 239372 236753 65448
  Steps: 23150 23729 403986 273273 271592 73410
  Steps: 26482 27018 416407 286531 284058 76295
  Steps: 28127 27018 429632 298998 296468 79299
  Steps: 29794 31993 473677 343808 341381 89575
  Steps: 33118 33662 486954 371226 368753 95944
  Steps: 34780 35317 514379 397811 395301 102193
  Steps: 38109 38639 541010 410201 408616 104958
  Steps: 39770 40305 553411 423504 421101 111027
  Steps: 41433 43640 595710 465923 463501 117757
  Steps: 44763 45310 609007 478306 493386 124557
  Steps: 48096 46980 638029 508055 519042 130686
  Steps: 49759 50313 664613 533784 531442 133570
  Steps: 51424 53649 690265 560371 558010 139639
  Steps: 53090 53649 720171 589434 587953 146550
  Steps: 58088 58656 751803 620981 619626 157366
  Steps: 64759 65335 819279 688363 687045 169324
  Steps: 68092 70339 865085 734088 732079 183085
  Steps: 74763 73680 914229 783060 782025 191217
  Steps: 78097 78691 958380 827074 826209 201372
  Steps: 81431 82033 999999 871975 870174 211036
  Steps: 86439 87032 999999 924273 923406 219149
  Steps: 91446 92023 999999 999999 999999 230506
  Steps: 91446 93361 999999 999999 999999 230626
  Steps: 91446 94721 999999 999999 999999 230726
  Steps: 91446 96091 999999 999999 999999 230826
  Terminate batch job (Y/N)? y
```

Here is what I get out of the output from the program:

*   Threads with the different priority levels may get the same amount of processing time share. See the progresses of thread 0 and 1\. Thread 0 had priority 1, and thread 1 had priority 5\. But they showed about the same progress rate.
*   Thread of priority 1 was getting about 10 times less amount of the processing time share than thread of priority 10\. See the progress rates of thread 0 and thread 4.
*   The main thread was running at least 20 times slower when all 5 sub-threads were running. See the elapse time intervals, which were > 2000 milliseconds while all 5 sub-threads were running. The sleeping time was about 100 milliseconds. So the main thread was blocked for at least 1900 milliseconds.

Another interesting behavior was noticed while executing the program. While all 5 sub-threads were running, the operating system was very sluggish. I was only able to move the mouse pointer around. Clicking on windows of any other running application programs gave me no response at all until 3 sub-threads reached the end. I guess the reason for this behavior is that Windows system is not truly sharing processing time among the running application programs equally. It let my Java application program (running under Java VM) took 100% of the CPU processing time. This is not a well-designed time-sharing multi-tasking operating system. Can anyone try my program on a Unix system?

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟Application Data Shared by Multiple Threads

This section provides a tutorial example on how to share application data by multiple threads. Data sharing allows multiple threads to work together on a single large task.

Threads of the same running program not only share CPU time, they also share the same memory space that allocated to the program. This is different than multiple programs running at the operating system level, where memory space can not be shared by different running programs.

Sharing the same memory space among many threads is a very nice feature. It allows threads working on the same set of data to accomplish a big task together. But it can also be a trouble maker, because the execution speed of each thread can not be managed. There is no way to know which thread is the first one to reach the data, and which one will be the next one.

The following program shows that how multiple threads can work together to calculate how many weekdays in each year for 2000 years starting from year 2000\. In this program, an array, y_days, is declared as static, so it can be shared by all the threads to store the calculated result, the number of weekdays of a specific year.

```
 /* WeekDayCounter.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
class WeekDayCounter extends Thread {
  private static final int s_year = 2000; // starting year
  private static int y_maxi = 10000; // maximum number of years
  private static int t_maxi = 50; // maximum number of threads
  private static int t_last = -1; // index of the last thread
  private static int n_loop = 50; // repeat the work n times 
  private static int[] t_year = new int[t_maxi];
  private static boolean[] t_done = new boolean[t_maxi];
  private static int[] t_logs = new int[t_maxi]; // years calculated
  private static int[] y_days = new int[y_maxi]; // weekdays

  private int t_indx; // index of this thread

  public static void main(String[] arg) {
    if (arg.length>0) y_maxi = Integer.parseInt(arg[0]);
    if (arg.length>1) t_maxi = Integer.parseInt(arg[1]);

    for (int i=0; i<y_maxi; i++) {
      y_days[i] = 0;
    }
    for (int i=0; i<t_maxi; i++) {
      WeekDayCounter t = new WeekDayCounter();
      t.start();
    }
    System.out.print("Thread: ");
    for (int i=0; i<t_maxi; i++) {
      System.out.print(i+" ");
    }
    Date t1 = new Date();
    while(true) {
      System.out.print("\n  Year: ");
      boolean done = true;
      for (int i=0; i<t_maxi; i++) {
        System.out.print(t_year[i]+" ");
        done = done && t_done[i];
      }
      if (done) break;
      try {
        sleep(100);
      } catch (InterruptedException e) {
        System.out.println("Interrupted.");
      }
    }
    Date t2 = new Date();
    System.out.println("\nTime = "+(t2.getTime()-t1.getTime()));
    System.out.println("Thread #, Years");
    int sum = 0;
    for (int i=0; i<t_maxi; i++) {
      sum += t_logs[i];
      System.out.println(i+", "+t_logs[i]);
    }
    System.out.println("Total # of years = "+sum);
  }
  public WeekDayCounter() {
    t_last++;
    t_indx = t_last;
    t_done[t_indx] = false;
    t_year[t_indx] = 0;
    t_logs[t_indx] = 0;
  }
  public void run() {
    GregorianCalendar c = new GregorianCalendar();
    for (int y=s_year; y<s_year+y_maxi; y++) {
      t_year[t_indx] = y;
      if (y_days[y-s_year]==0) {
        y_days[y-s_year] = -1;
        int n = 0;
        for (int i=0; i<n_loop; i++) {
          c.clear();
          c.set(y,0,1); // first day of the year
          n = 0;
          while (c.get(Calendar.YEAR)<=y) {
             if (c.get(Calendar.DAY_OF_WEEK)==Calendar.MONDAY) n++;
             if (c.get(Calendar.DAY_OF_WEEK)==Calendar.TUESDAY) n++;
             if (c.get(Calendar.DAY_OF_WEEK)==Calendar.WEDNESDAY) n++;
             if (c.get(Calendar.DAY_OF_WEEK)==Calendar.THURSDAY) n++;
             if (c.get(Calendar.DAY_OF_WEEK)==Calendar.FRIDAY) n++;
             c.add(Calendar.DATE,1);
          }
        }
        y_days[y-s_year] = n;
        t_logs[t_indx] += 1;
      }
    }
    t_done[t_indx] = true;
  }
}
```

When threads are launched, they will all start to work on one year at time, beginning with the same starting year, 2000\. Without any coordination, they will all work on year 2000, then 2001\. This is not what we want. We need to tell each thread to skip the year if another thread has already finished calculation for that year. This is done by initializing y_days with 0 for all the years at the beginning of the program, and setting y_days of a given year to the calculated result of that year. If another thread is running behind and reaches this year later, it checks the value in y_days for that year. If the value is not 0, it will skip that year.

However, just setting y_days to the result of the end of the calculation is not enough. Because calculating the number of weekdays of one year will take some time, and during this period, another thread might still pick up that year and work on that year, because the y_days value is still 0\. A simple way to stop this mistake is to set y_days to -1 at the beginning of the calculation.

In order to slow down the process on fast computers, n_loop = 50 is introduced to repeat the calculation 50 times.

The program is also designed to verify if a program can have more work done with more threads.

See the next sections for test results of this program.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟Application Data Shared by Multiple Threads - Test Results

This section provides test results of a tutorial example on how to share application data by multiple threads. Data sharing allows multiple threads to work together on a single large task.

I performed several tests with the program presented in the previous section. Testing outputs are listed below.

**Test on a new computer with 8 CPUs/processors and n_loop = 50**:

Output of 4000 years and 1 thread:

```
 herong> java WeekDayCounter 4000 1

Thread: 0
  Year: 0
  Year: 2043
  Year: 2340
  ...
  Year: 5932
  Year: 5999
Time = 1413
Thread #, Years
0, 4000
Total # of years = 4000
```

Output of 4000 years and 4 thread:

```
 herong> java WeekDayCounter 4000 4

Thread: 0 1 2 3
  Year: 0 0 0 0
  Year: 0 0 0 0
  Year: 2032 2033 2031 2034
  Year: 2312 2328 2327 2331
  ...
  Year: 5919 5929 5928 5927
  Year: 5999 5999 5999 5999
Time = 746
Thread #, Years
0, 1073
1, 1014
2, 958
3, 958
Total # of years = 4003
```

Output of 4000 years and 8 thread:

```
 herong> java WeekDayCounter 4000 8

Thread: 0 1 2 3 4 5 6 7
  Year: 0 0 0 0 0 0 0 0
  Year: 2014 2039 2061 2086 2092 2097 2132 2114
  Year: 2346 2487 2640 2826 3025 3051 3269 3285
  Year: 4933 5031 5039 5270 5327 5438 5483 5649
  Year: 5999 5999 5999 5999 5999 5999 5999 5999
Time = 812
Thread #, Years
0, 489
1, 506
...
6, 513
7, 511
Total # of years = 4003
```

Output of 4000 years and 16 thread:

```
 herong> java WeekDayCounter 4000 16

Thread: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
  Year: 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
  Year: 2040 2033 2034 2029 2023 2032 2036 2022 2042 2037 2020 2041 2045 ...
  Year: 2171 2167 2176 2174 2166 2178 2172 2170 2165 2175 2169 2177 2179 ...
  Year: 2375 2482 2514 2816 3166 3647 3908 4453 4849 5115 5686 5785 5912 ...
  Year: 5999 5999 5999 5999 5999 5999 5999 5999 5999 5999 5999 5999 5999 ...
Time = 1006
Thread #, Years
0, 281
1, 286
...
14, 255
15, 200
Total # of years = 4003
```

A couple of interesting notes on the results:

*   As expected, adding more threads initially will improve the performance. But when increasing the number of threads more than the number of CPUs/processors, the performance will decrease.
*   "Total # of years = 4003" in the output indicates that some threads are sill working on the same year. Our "y_days[y-s_year] = -1;" statement is not running faster enough to prevent other threads to pick up the same year. We need to use "synchronized" statement to make it perfect.

**Test on an old computer with 1 CPU/processor and n_loop = 1**:

Output of 2000 years and 1 thread:

```
 Thread: 0
  Year: 0
  Year: 2001
  Year: 2025
  ...
  Year: 3966
  Year: 3999
Time = 6029
...
```

Output of 2000 years and 5 threads:

```
 Thread: 0 1 2 3 4
  Year: 0 0 0 0 0
  Year: 2039 2040 2043 2042 2044
  Year: 2067 2040 2048 2042 2044
  ...
  Year: 3992 3999 3999 3999 3999
  Year: 3999 3999 3999 3999 3999
Time = 6369
...
```

Output of 2000 years and 10 threads:

```
 Thread: 0 1 2 3 4 5 6 7 8 9
  Year: 2936 2948 3237 3242 3208 2954 3182 3232 3169 2963
  Year: 2936 3303 3237 3242 3208 3272 3182 3232 3169 2963
  Year: 3495 3498 3237 3480 3974 3890 3996 3999 3999 2963
  Year: 3999 3999 3999 3999 3999 3999 3999 3999 3999 3999
Time = 3925
...
```

Output of 2000 years and 10 threads - another run:

```
 Thread: 0 1 2 3 4 5 6 7 8 9
  Year: 2222 2239 2174 2275 2245 2142 2213 0 0 2248
  Year: 2531 2283 2501 2510 2245 2142 2213 2460 2521 2470
  Year: 2531 2283 2583 2624 2547 2142 2213 2460 2556 2615
  ...
  Year: 3908 3949 3890 3978 3937 3991 3625 3396 3745 3426
  Year: 3999 3999 3999 3999 3999 3999 3999 3999 3999 3999
Time = 6750
...
```

Output of 2000 years and 15 threads:

```
 Thread: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14
  Year: 2039 2046 2053 0 0 0 0 0 0 0 0 2284 2363 2425 2387
  Year: 2212 2499 2088 0 0 0 0 0 0 0 0 2284 2489 2461 2387
  Year: 2638 2655 2088 0 0 0 0 2615 2663 2645 2602 2630 2489 2461 2387
  Year: 3441 2885 2088 2921 3430 3169 3487 2903 3362 3222 3186 3499 ...
  Year: 3996 3841 3502 3836 3611 3815 3999 3501 3362 3993 3900 3885 ...
  Year: 3999 3999 3999 3999 3999 3999 3999 3999 3999 3999 3999 3999 ...
Time = 6920
...
```

A couple of interesting notes on the results:

*   As expected, the total execution time is slowly growing as more threads are added to the program. Because there is only CPU, when one thread executes, the others must wait. The small amount of extra execution time when more threads are added is the overhead of managing more threads.
*   However, there is one surprise in the output. One execution of the program with 10 threads took only 3925 milliseconds, comparing to 6750 milliseconds for another execution with the same number of threads. What happened for that execution, and why it went so fast? I don't know the answers. May be, the operating system was giving my application some extra CPU resource by blocking other applications longer.
*   The outputs also show that threads can be blocked for relatively longer period of time by other threads by the application, even they all have the same priority. One example in the output of the execution with 15 threads is that threads 4, 5, 6 and 7 were blocked at the start line until thread 1 had already checked and/or processed 638 years.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Execution Threads and Multi-Threading Java Programs](#part0129.xhtml)

∟interrupt() - Method to Terminate Thread

This section provides a tutorial example on how to terminate running threads with the interrupt() method.

There are 3 ways to terminate a thread:

*   The thread has finished the work it is designed to do, and exits the run() method naturally.
*   The thread has received an interruption signal, while doing its work. It decides to not continue with work and exits the run() method. It may also decide to ignore the signal and continue to work.
*   The thread has been marked as daemon thread. When the parent thread who created this thread terminates, this thread will be forcefully terminated by the JVM.

The following program demonstrates all the 3 ways of terminating a thread. The program is design to work at a timer. It can be set to run for a given number of minutes. Once it started, the program creates 3 sub-threads:

*   One acts as a normal clock, starting with the current time.
*   One acts as a stop watch, starting from 0.
*   One acts as a count-down timer, starting from the amount of time the timer is set to.

```
 /* TimerThread.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
import java.text.*;
class TimerThread extends Thread {
   private static final int NORMAL_CLOCK = 1;
   private static final int COUNT_DOWN = 2;
   private static final int STOP_WATCH = 3;
   private int type; // type of clock
   private int c_millisecond, c_second, c_minute, c_hour;
   private static int remaining_minutes = 5;
   private static int clock_interval = 100; // in milliseconds < 1000
   public static void main(String[] a) {
      System.out.println("Normal clock Stop watch   Count-down");
      TimerThread normal_clock = new TimerThread(NORMAL_CLOCK);
      TimerThread count_down = new TimerThread(COUNT_DOWN);
      TimerThread stop_watch = new TimerThread(STOP_WATCH);
      stop_watch.setDaemon(true);
      normal_clock.start();
      count_down.start();
      stop_watch.start();
      while (count_down.isAlive()) {
         System.out.print(normal_clock.getClock()+" "+
            stop_watch.getClock()+" "+ count_down.getClock()+"\r");
         try {
            sleep(1);
         } catch (InterruptedException e) {
            System.out.println("Interrupted.");
         }
      }
      normal_clock.interrupt();
   }
   public TimerThread(int t) {
      type = t;
      if (type==NORMAL_CLOCK) {
         GregorianCalendar c = new GregorianCalendar();
         c_hour = c.get(Calendar.HOUR_OF_DAY);
         c_minute = c.get(Calendar.MINUTE);
         c_second = c.get(Calendar.SECOND);
         c_millisecond = c.get(Calendar.MILLISECOND);
      } else if (type==COUNT_DOWN) {
         c_hour = remaining_minutes/60;
         c_minute = remaining_minutes%60;
         c_second = 0;
         c_millisecond = 0;
      } else {
         c_hour = 0;
         c_minute = 0;
         c_second = 0;
         c_millisecond = 0;
      }
   }
   public void run() {
      while (!isInterrupted()) {
         try {
            sleep(clock_interval);
         } catch (InterruptedException e) {
            break; // the main thread wants this thread to end
         }
         if (type==NORMAL_CLOCK || type==STOP_WATCH)
            c_millisecond +=clock_interval;
         else c_millisecond -= clock_interval;
         if (c_millisecond>=1000) {
            c_second += c_millisecond/1000;
            c_millisecond = c_millisecond%1000;
         }
         if (c_second>=60) {
            c_minute += c_second/60;
            c_second = c_second%60;
         }
         if (c_minute>=60) {
            c_hour += c_minute/60;
            c_minute = c_minute%60;
         }
         if (c_millisecond<0) {
            c_second--;
            c_millisecond += 1000;
         }
         if (c_second<0) {
            c_minute--;
            c_second += 60;
         }
         if (c_minute<0) {
            c_hour--;
            c_minute += 60;
         }
         if (c_hour<0) {
            c_hour = 0;
            break; // end this thread
         }
      }
   }
   private String getClock() {
      // returning the clock as a string of HH:mm:ss:SSS format
      GregorianCalendar c = new GregorianCalendar();
      c.set(Calendar.HOUR_OF_DAY,c_hour);
      c.set(Calendar.MINUTE,c_minute);
      c.set(Calendar.SECOND,c_second);
      c.set(Calendar.MILLISECOND,c_millisecond);
      SimpleDateFormat f = new SimpleDateFormat("HH:mm:ss:SSS");
      return f.format(c.getTime());
   }
}
```

Threads in this program will be terminated in the following sequence:

*   The count-down thread will be the first one to terminate, when its clock reaches the 0 value.
*   The main thread is constantly checking the status of the count-down thread by calling count_down.isAlive(). Once it detects the termination of the count-down thread, it will then send the interruption signal to the normal clock thread by calling normal_clock.interrupt().
*   The normal clock thread is constantly checking its interruption status by calling isInterrupted(). Once it received the interruption signal from the main thread, it will break the loop, terminate itself.
*   After sending the interruption signal to the normal clock signal, the main thread will also terminate itself.
*   The stop-watch thread will be forced to terminate by the JVM, after the main thread terminates, because it is created by the main thread, and marked as a daemon thread.

Please also note that:

*   The interruption signal may come to a thread, while it is in the middle of a sleep. When this happens, the sleep() call will be returned immediately with the InterruptionException. The thread should terminate itself quickly.
*   The clocks simulated in the threads are not accurate at all. The extra time spend on executing the statements other the sleep() statement is counted. You will see that the clock time from the normal clock thread is running slower than your real watch.
*   I am using the System.out.print() method with the '\r' character to keep the output text repeating at the line on the screen. This will make the output looks much more like a real clock.
*   The GregorainCalendar class is used in my program to me getting the current hour, minute, second and millisecond values, and formatting those values into a string. I have more notes on calendar classes in my other book on JDK.

Output of one execution of my program:

```
 Normal clock  Stop watch    Count-down
21:19:13:764  00:05:00:000  00:00:00:000
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟ThreadGroup Class and "system" ThreadGroup Tree

This chapter provides tutorial notes and tutorial examples on the ThreadGroup class and the 'system' ThreadGroup tree. Topics include main methods of the ThreadGroup class, displaying the 'system' ThreadGroup tree, adding threads and thread groups, testing the reported JDK 1.3 bug - memory leak of unstarted threads.

> ["ThreadGroup" Class - Container of Threads and Thread Groups](#part0139.xhtml)
> 
> [Displaying the "system" ThreadGroup Tree](#part0140.xhtml)
> 
> [Adding Threads and Thread Groups](#part0141.xhtml)

Conclusion:

*   Threads are organized into thread group trees in Java.
*   JVM starts with 1 thread group called "system", which contains a child group called "main".
*   Java application is running in the "main" thread under the "main" group.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[ThreadGroup Class and "system" ThreadGroup Tree](#part0138.xhtml)

∟"ThreadGroup" Class - Container of Threads and Thread Groups

This section describes the 'ThreadGroup' class and its main methods. A 'ThreadGroup' object is a container of threads and thread groups.

**ThreadGroup**: A class represents a collection of Thread objects and ThreadGroup objects.

Features of the ThreadGroup class:

*   All objects of ThreadGroup class are organized as a tree structure. Each ThreadGroup object must have a parent ThreadGroup object in the tree, except the root object.
*   The root object of the ThreadGroup tree is provided and managed by the Java Virtual Machine (JVM).

Main methods:

*   getParent(): Returns the parent ThreadGroup object.
*   activeCount(): Returns the number of active Thread objects in this ThreadGroup object and its sub-tree.
*   activeGroupCount(): Returns the number of active ThreadGroup objects in this ThreadGroup object and its sub-tree.
*   enumerate(Thread[] l): Copies active Thread objects in this ThreadGroup object and its sub-tree.
*   enumerate(ThreadGroup[] l): Copies active ThreadGroup objects in this ThreadGroup object and its sub-tree.
*   interrupt(): Calls Thread.interrupt() method on all Thread objects in this ThreadGroup object and its sub-tree.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[ThreadGroup Class and "system" ThreadGroup Tree](#part0138.xhtml)

∟Displaying the "system" ThreadGroup Tree

This section provides a tutorial example on how to display the 'system' ThreadGroup tree by using the enumerate() and list() methods.

As I mentioned in the previous section, there is a single tree structure managed by the JVM to organize all objects of ThreadGroup class and Thread class. Here are the rules of how this tree is maintained:

*   The root node of the tree is a ThreadGroup object named "system".
*   The "system" thread group contains a number of threads performing JVM system tasks.
*   The "system" thread group contains just one ThreadGroup object named "main".
*   The "main" thread group contains one thread named "main", which is the starting thread for the application program.
*   The "main" thread group contains no other ThreadGroup objects.
*   If a new ThreadGroup object is created without a parent ThreadGroup object specified, it will be added into the "main" thread group.
*   If a new Thread object is created without a ThreadGroup object specified, it will be added into the "main" thread group.

Here is a sample program showing how to use some of the methods in ThreadGroup class to get information out of the ThreatGroup tree:

```
 /* ThreadGroupTree.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class ThreadGroupTree {
   public static void main(String[] args) {
      Thread t = Thread.currentThread();
      ThreadGroup g = t.getThreadGroup();
      g = g.getParent();
      printInfo(g,"");
      g.list();
   }
   public static void printInfo(ThreadGroup g, String p) {
      System.out.println(p+"ThreadGroup name = "+g.getName());
      System.out.println(p+"   Has parent thread group = "
         +(g.getParent()!=null));
      int n = g.activeCount();
      System.out.println(p+"   # of active threads = "+n);
      Thread[] l = new Thread[n];
      n = g.enumerate(l, false);
      for (int i=0; i<n; i++) {
         System.out.println(p+"   Thread name = "+l[i].getName());
      }
      n = g.activeGroupCount();
      System.out.println(p+"   # of active sub thread groups = "+n);
      ThreadGroup[] s = new ThreadGroup[n];
      n = g.enumerate(s, false);
      for (int i=0; i<n; i++) {
         printInfo(s[i],"   "+p);
      }
   }
}
```

Output:

```
 ThreadGroup name = system
   Has parent thread group = false
   # of active threads = 5
   Thread name = Reference Handler
   Thread name = Finalizer
   Thread name = Signal Dispatcher
   Thread name = Attach Listener
   # of active sub thread groups = 1
   ThreadGroup name = main
      Has parent thread group = true
      # of active threads = 1
      Thread name = main
      # of active sub thread groups = 0
java.lang.ThreadGroup[name=system,maxpri=10]
    Thread[Reference Handler,10,system]
    Thread[Finalizer,8,system]
    Thread[Signal Dispatcher,9,system]
    Thread[Attach Listener,5,system]
    java.lang.ThreadGroup[name=main,maxpri=10]
        Thread[main,5,main]
```

Note that:

*   There are 5 Thread objects in the "system" thread group: 4 threads (Reference Handler, Finalizer, Signal Dispatcher, Attach Listener) and 1 group (main).
*   The "main" thread is located in the "main" group under the "system" group.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[ThreadGroup Class and "system" ThreadGroup Tree](#part0138.xhtml)

∟Adding Threads and Thread Groups

This section provides a tutorial example on how to add threads and thread groups to the 'system' ThreadGroup tree.

The next program shows how to add more threads and thread groups to the ThreadGroup tree:

```
 /* GroupingThreads.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class GroupingThreads {
   public static void main(String[] args) {
      Thread t = new AThread();
      t.setName("AThread 1");
      t = new AThread();
      t.setName("AThread 2");
      t.start();
      t.interrupt();
      t = new AThread();
      t.setName("AThread 3");
      t.start();
      ThreadGroup g = new ThreadGroup("Group X");
      t = new BThread(g, "BThread 4");
      t = new BThread(g, "BThread 5");
      t.start();
      t = new BThread(g, "BThread 6");
      t.start();
      g.interrupt();
      g = new ThreadGroup("Group Y");
      t = new BThread(g, "BThread 7");
      t.start();
      t = new BThread(g, "BThread 8");
      t.start();
      g.interrupt();
      try {Thread.sleep(1000);}
      catch (InterruptedException e) {}
      g.destroy();
      printInfo();
   }
   public static void printInfo() {
      Thread t = Thread.currentThread();
      ThreadGroup g = t.getThreadGroup();
      g = g.getParent();
      printInfo(g,"");
      g.list();
   }
   public static void printInfo(ThreadGroup g, String p) {
      System.out.println(p+"ThreadGroup name = "+g.getName());
      System.out.println(p+"   Has parent thread group = "
         +(g.getParent()!=null));
      int n = g.activeCount();
      System.out.println(p+"   # of active threads = "+n);
      Thread[] l = new Thread[n];
      n = g.enumerate(l, false);
      for (int i=0; i<n; i++) {
         System.out.println(p+"   Thread name = "+l[i].getName());
      }
      n = g.activeGroupCount();
      System.out.println(p+"   # of active sub thread groups = "+n);
      ThreadGroup[] s = new ThreadGroup[n];
      n = g.enumerate(s, false);
      for (int i=0; i<n; i++) {
         printInfo(s[i],"   "+p);
      }
   }
   static class AThread extends Thread {
      public void run() {
         System.out.println("Running "+getName());
         try {
            sleep(1000*60*60);
         } catch (InterruptedException e) {
         }
         System.out.println("Ending "+getName());
      }
   }
   static class BThread extends Thread {
      public BThread(ThreadGroup g, String n) {
         super(g,n);
      }
      public void run() {
         System.out.println("Running "+getName());
         try {
            sleep(1000*60*60);
         } catch (InterruptedException e) {
         }
         System.out.println("Ending "+getName());
      }
   }
}
```

Output:

```
 Running AThread 2
Running BThread 6
Running BThread 5
Running AThread 3
Ending BThread 5
Ending BThread 6
Running BThread 8
Running BThread 7
Ending AThread 2
Ending BThread 7
Ending BThread 8
ThreadGroup name = system
   Has parent thread group = false
   # of active threads = 6
   Thread name = Reference Handler
   Thread name = Finalizer
   Thread name = Signal Dispatcher
   Thread name = Attach Listener
   # of active sub thread groups = 2
   ThreadGroup name = main
      Has parent thread group = true
      # of active threads = 2
      Thread name = main
      Thread name = AThread 3
      # of active sub thread groups = 1
      ThreadGroup name = Group X
         Has parent thread group = true
         # of active threads = 0
         # of active sub thread groups = 0
java.lang.ThreadGroup[name=system,maxpri=10]
    Thread[Reference Handler,10,system]
    Thread[Finalizer,8,system]
    Thread[Signal Dispatcher,9,system]
    Thread[Attach Listener,5,system]
    java.lang.ThreadGroup[name=main,maxpri=10]
        Thread[main,5,main]
        Thread[AThread 3,5,main]
        java.lang.ThreadGroup[name=Group X,maxpri=10]
```

Note that:

*   As expected, new thread groups were added to the "main" thread group by default.
*   As expected, new threads are were added to the "main" thread group by default, if they were created without a thread group.
*   Thread "AThread 1" was never started. It was reported by the list() method, but not included in the enumerate() method.
*   Based on the previous note, we can calculate the number of unstarted threads in thread group by activeCount()-enumerate(Thread[] l, true).
*   Thread group "Group Y" was destroyed by the destroy() method, when it became empty.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Synchronization Technique and Synchronized Code Blocks

This chapter provides tutorial notes and tutorial examples on synchronization technique and synchronized code blocks. Topics include what is the synchronization technique; synchronized class methods, instance methods, statement blocks; synchronized banking application sample.

> [Why Synchronization Is Needed in Multi-Threading Applications](#part0143.xhtml)
> 
> [Synchronization Technique - Lock and Synchronized Code](#part0144.xhtml)
> 
> ["synchronized" - How Java Supports Synchronization](#part0145.xhtml)
> 
> [BankingThread.java - Synchronization Sample Program](#part0146.xhtml)
> 
> [BankingThread.java - Synchronization Sample Program Output](#part0147.xhtml)

Conclusion:

*   Synchronization is needed in a multi-threading application to ensure that one thread is updating a shared data other threads wait and get the updated value.
*   Synchronization uses a lock to represent the shared data to allow each thread to use the lock status to Synchronize with each other.
*   Synchronization code block is a unit of code in a thread that requires synchronization on a particular lock.
*   More synchronization locks or longer synchronization code blocks slow down application performance.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Synchronization Technique and Synchronized Code Blocks](#part0142.xhtml)

∟Why Synchronization Is Needed in Multi-Threading Applications

This section describes why synchronization is needed in multi-threading applications.

The biggest problem of allowing multiple threads sharing the same data set is that one operation in one thread could collide with another operation in another thread on the same data. When this happens, the result is un-desirable.

Let's use a bank application program as an example. Assuming that the program has multiple threads running, with each thread connecting one ATM system, and you have a saving account in the bank with $100.00, now you and your friend are going to two different ATMs at about the same time, and trying to withdraw $50.00 from your account, what do you think it will happen?

If the threads are running independently, the following could happen:

```
 Time     01:01      02:01     03:01     04:01
         +----------+---------+---------+-------
Thread 1            Get       Set
Action   You        Account   Account   You
         Withdraw   Balance   Balance   Receive
         $50.00     $100.00   $50.00    $50.00
```

```
 Time      01:02      02:02     03:02     04:02
         -+----------+---------+---------+------
Thread 2             Get       Set
Action    Friend     Account   Account   Friend
          Withdraw   Balance   Balance   Receive
          $50.00     $100.00   $50.00    $50.00
```

```
 Time     01:01      02:01     03:01     04:01
         -----------++--------++--------++------
Account  $100.00    $100.00   $50.00    $50.00
```

Both you and your friend will receive $50.00 each, and your account will still have $50.00\. The bank could lose $50.00.

The solution to this problem is synchronization.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Synchronization Technique and Synchronized Code Blocks](#part0142.xhtml)

∟Synchronization Technique - Lock and Synchronized Code

This section describes what is synchronization - a programming technique used in multi-threading applications with a synchronization lock to control execution of synchronized code.

**Synchronization** is a programming technique that involves 3 elements:

*   **Lock**: An object with two states: locked and unlocked.
*   **Synchronized Block**: A block of statements that is associated with a lock.
*   **Synchronization Rule**: When a synchronized block is encountered in a thread of execution, the associated lock will be checked. If the lock locked, the execution will be stopped until the lock is unlocked. If the lock is unlocked, the lock will be locked, and the synchronized block of statements will be executed. When the execution reaches the end of the synchronized block, the lock will be unlocked. With this rule, two synchronized blocks associated with same lock will never be executed at the same time.

Now let's see if we can use the synchronization technique in the bank application program to help the bank. Let's define a synchronization block starting from the "Get Account Balance" action to the "Set Account Balance" action in each thread, and associate the block with a lock. With this change, both you and your friend can still withdraw $50.00, but your account will have nothing left:

```
 Time     01:01      02:01     03:01      04:02
         -----------+---------++--------++-------
Lock     Unlocked   Locked    Locked     Unlocked
```

```
 Time     01:01      02:01     03:01     04:01
         +----------+---------+---------+--------
Thread 1            Get       Set
Action   You        Account   Account   You
         Withdraw   Balance   Balance   Receive
         $50.00     $100.00   $50.00    $50.00
```

```
 Time      01:02      02:02     03:02     04:02     05:02
         -+----------+---------+---------+---------+------
Thread 2             Get       Get       Set
Action    Friend     Account   Account   Account   Friend
          Withdraw   Balance   Balance   Balance   Receive
          $50.00     Stopped   $50.00    $0.00     $50.00
```

```
 Time     01:01      02:01     03:01      04:02     05:02
         -----------++--------++--------++---------+------
Account  $100.00    $100.00   $50.00     $0.00     $0.00
```

The synchronization technique did help the bank from losing money. But it also increased the total transaction time.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Synchronization Technique and Synchronized Code Blocks](#part0142.xhtml)

∟"synchronized" - How Java Supports Synchronization

This section describes the 'synchronized' keyword and how Java supports synchronization in 3 different ways - synchronized class methods, synchronized instance methods, synchronized statement blocks.

Instead of let the programmers to design their own locks, manage the synchronization blocks, and apply the synchronization rules, Java offers a synchronization monitor on each instance of the Object class, so it can be used as a synchronization lock. Since all classes are sub classes of Object, all objects in Java can be used as synchronization locks.

Java also offers three ways to define synchronized blocks.

**Synchronized Class Method**:

```
 class class_name {
   static synchronized type method_name() {
      statement block
   }
}
```

All the statements in the method become the synchronized block, and the class object is the lock.

**Synchronized Instance Method**:

```
 class class_name {
   synchronized type method_name() {
      statement block
   }
}
```

All the statements in the method become the synchronized block, and the instance object is the lock.

**Synchronized Statement**:

```
 class class_name {
   type method_name() {
      synchronized (object) {
         statement block
      }
   }
}
```

All the statements specified in the parentheses of the synchronized statement become the synchronized block, and the object specified in the statement is the lock.

Java applies the synchronization rule by assigning the ownership of the lock's monitor to the threads that are running the synchronized blocks. Here is how it works:

*   When a synchronized clock is reached in an execution thread, it will try to gain the ownership of the monitor of the lock object. If another thread owns the lock's monitor, it will wait.
*   Once the lock's monitor is free, the waiting thread will become the owner of the lock's monitor, and start to execute the synchronized block.
*   Once the synchronized block is executed to the end, the lock's monitor will be freed again.

Note that one program can have many locks and each lock can be associated with many different synchronized blocks. But the synchronization rule only applies between the synchronized block and its associated lock.

For example, the following code defines two synchronized blocks. Both are associated with the same lock, the instance object.

```
 class class_name {
   type method_name() {
      synchronized (this) {
         statement block 1
      }
   }
   synchronized type method_name() {
      statement block 2
   }
}
```

Block 1 will never be executed at the same time as block 2.

The following code defines two synchronized blocks. But they are associated with two different locks, one is the class object, and the other is the instance object. Those two synchronized blocks will never wait for each other.

```
 class class_name {
   type method_name() {
      synchronized (this) {
         statement block 1
      }
   }
   static synchronized type method_name() {
      statement block 2
   }
}
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Synchronization Technique and Synchronized Code Blocks](#part0142.xhtml)

∟BankingThread.java - Synchronization Sample Program

This section provides a tutorial example on how to solve the banking synchronization issue with Java synchronized methods.

Now, let's write a Java program to see how the synchronization technique can solve the bank problem. Two classes are designed to simulate a bank system:

*   BankingThread class: Acting as an ATM machine, taking deposit or withdraw transaction requests from customers, and asking the BankingMain class to perform the transactions.
*   BankingMain class: Acting as the control center, managing instances of the BankingThread class, and performing transactions coming from each BankingThread instance.

BankingThread class:

```
 /* BankingThread.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
public class BankingThread extends Thread {
   private long[] t_balance; // account balance
   private long t_count; // number of transactions done so far
   public BankingThread(ThreadGroup g, String n) {
      super(g,n);
      t_count = 0;
      int m = BankingMain.accountCount();
      t_balance = new long[m];
      for (int i=0; i<m; i++) t_balance[i] = 0;
   }
   public long transactionCount() {
      return t_count;
   }
   public long getBalance(int i) {
      return t_balance[i];
   }
   public void run() {
      while (!isInterrupted()) {
         t_count++;
         Random r = BankingMain.getRandom();
         long t_step = BankingMain.getStep();
         int m = BankingMain.accountCount();
         int n = r.nextInt(m); // account number
         int t = 2*r.nextInt(2)-1; // type of transaction
         long a = (long) t*r.nextInt(10000); // amount of transaction
         if (t_step==1)
            if (BankingMain.doTransaction1(n,a)) t_balance[n] += a;
         if (t_step==2)
            if (BankingMain.doTransaction2(n,a)) t_balance[n] += a;
         if (t_step==3)
            if (BankingMain.doTransaction3(n,a)) t_balance[n] += a;
         if (t_step==4)
            if (BankingMain.doTransaction4(n,a)) t_balance[n] += a;
         try {
            sleep(10); // wait for the next customer
         } catch (InterruptedException e) {
            break;
         }
      }
   }
}
```

BankingMain class:

```
 /* BankingMain.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
public class BankingMain {
   public static final int a_maxi = 10; // number of accounts
   public static long[] balance = new long[a_maxi];
   public static Random r_number;
   private static final int t_maxi = 5; // number of threads
   private static BankingThread[] t_list = new BankingThread[t_maxi];
   private static long t_step;
   private static Object o_lock;
   private static Object[] a_lock = new Object[a_maxi];
   public static void main(String[] a) {
      o_lock = new Object();
      for (int i=0; i<a_maxi; i++) a_lock[i] = new Object();
      t_step = 1; // using doTransaction1();
      System.out.println("No synchronization:");
      testATM();
      printResult();
      t_step = 2; // using doTransaction2();
      System.out.println("Synchronized method:");
      testATM();
      printResult();
      t_step = 3; // using doTransaction3();
      System.out.println("Synchronized statements:");
      testATM();
      printResult();
      t_step = 4; // using doTransaction4();
      System.out.println("Synchronized statements per account:");
      testATM();
      printResult();
   }
   private static void testATM() {
      for (int i=0; i<a_maxi; i++) balance[i] = 0;
      r_number = new Random();
      ThreadGroup g = new ThreadGroup("ATM");
      for (int i=0; i<t_maxi; i++) {
         BankingThread t = new BankingThread(g,String.valueOf(i));
         t.start();
         t_list[i] = t;
      }
      try {
         Thread.sleep(5*1000); // working period
      } catch (InterruptedException e) {
         System.out.println("Interrupted in the mainthread.");
      }
      g.interrupt();
      while (g.activeCount()>0); // wait for all threads to end
   }
   private static void printResult() {
      System.out.print("Account");
      for (int i=0; i<t_maxi; i++)
         System.out.print(", ATM "+i);
      System.out.print(", Transaction Sum, Balance");
      for (int j=0; j<a_maxi; j++) {
         System.out.print("\n"+j);
         long sum = 0;
         for (int i=0; i<t_maxi; i++) {
            sum += t_list[i].getBalance(j);
            System.out.print(", "
               +getCurrency(t_list[i].getBalance(j)));
         }
         System.out.print(", "+getCurrency(sum)+
            ", "+getCurrency(balance[j]));
      }
      System.out.print("\n# of Transactions");
      for (int i=0; i<t_maxi; i++)
         System.out.print(", "+t_list[i].transactionCount());
      System.out.print("\n");
   }
   private static String getCurrency(long d) {
      long i = d/100;
      long f = Math.abs(d)%100;
      String fs = String.valueOf(f);
      if (f<10) fs = "0"+fs;
      return String.valueOf(i)+"."+fs;
   }
   public static long getStep() {
      return t_step;
   }
   public static int accountCount() {
      return a_maxi;
   }
   public static Random getRandom() {
      return r_number;
   }
   public static long getBalance(int i) {
      return balance[i];
   }
   public static boolean doTransaction1(int i, long a) {
      boolean ok = false;
      long c = balance[i]; // get current balance
      ok = c+a>0;
      if (ok) { // stop account balance going negative
         try {
            Thread.sleep(1); // slow down the process
         } catch (InterruptedException e) {
            Thread.currentThread().interrupt(); // re-set the flag
         }
         balance[i] = c+a; // set current balance
      }
      return ok;
   }
   public synchronized static boolean doTransaction2(int i, long a) {
      boolean ok = false;
      long c = balance[i]; // get current balance
      ok = c+a>0;
      if (ok) { // stop account balance going negative
         try {
            Thread.sleep(1); // slow down the process
         } catch (InterruptedException e) {
            Thread.currentThread().interrupt(); // re-set the flag
         }
         balance[i] = c+a; // set current balance
      }
      return ok;
   }
   public static boolean doTransaction3(int i, long a) {
      boolean ok = false;
      synchronized (o_lock) {
         long c = balance[i]; // get current balance
         ok = c+a>0;
         if (ok) { // stop account balance going negative
            try {
               Thread.sleep(1); // slow down the process
            } catch (InterruptedException e) {
               Thread.currentThread().interrupt(); // re-set the flag
            }
            balance[i] = c+a; // set current balance
         }
      }
      return ok;
   }
   public static boolean doTransaction4(int i, long a) {
      boolean ok = false;
      synchronized (a_lock[i]) {
         long c = balance[i]; // get current balance
         ok = c+a>0;
         if (ok) { // stop account balance going negative
            try {
               Thread.sleep(1); // slow down the process
            } catch (InterruptedException e) {
               Thread.currentThread().interrupt(); // re-set the flag
            }
            balance[i] = c+a; // set current balance
         }
      }
      return ok;
   }
}
```

Couple of notes about this program:

*   BankingThread also keeps track of balance of each account with t_balance[]. The sum of t_balance[i] from every thread should equal to the balance in the BankingMain class, balance[i].
*   BankingTread.run() simulates a transaction from a customer by randomly generating an account number, a transaction type, and a transaction amount.
*   I use "long" to store and calculate currency related values, because it is more accurate than "double".
*   The test steps are used to control the tests of different synchronization implementations: no synchronization, synchronized method, synchronized statements, and synchronized statements per account.
*   The Thread.sleep(1) statement in doTransaction() methods is used to increase the execution time of the transaction. If the thread is signaled for interruption during this sleep, no action is taken, but re-set the interruption flag to let BankingThread class to handle it later.
*   All instances of BankingThread are created within a ThreadGroup, so I can easily send an interruption signal to all of them.
*   The "while (g.activeCount()>0);" statement in the BankingMain class is used to make sure all treads are terminated before collecting results from them.

See the next section for the execution output.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Synchronization Technique and Synchronized Code Blocks](#part0142.xhtml)

∟BankingThread.java - Synchronization Sample Program Output

This section provides a tutorial example on how to solve the banking synchronization issue with Java synchronized methods.

Here is the output of the sample program presented in the previous section:

```
 No synchronization:
Account, ATM 0, ATM 1, ATM 2, ATM 3, ATM 4, Transaction Sum, Balance
0, 506.81, 227.06, 286.89, -885.14, 330.11, 465.73, 1051.87
1, 63.98, 27.74, 413.05, 276.93, -86.81, 694.89, 529.10
2, -303.05, -283.53, 385.71, 126.36, 136.16, 61.65, 188.65
3, -62.36, 491.84, 172.51, -548.71, 63.59, 116.87, 182.85
4, 553.12, 22.86, 1027.99, 52.98, -202.90, 1454.05, 1297.92
5, 276.85, 33.59, -371.78, -36.76, 363.60, 265.50, 343.82
6, 313.82, 300.44, 64.48, -321.91, 651.41, 1008.24, 1532.09
7, -516.72, -22.58, -139.76, -7.58, 352.92, -333.72, 264.26
8, 19.66, -506.82, 469.41, 437.11, -106.23, 313.13, 243.39
9, 225.69, -64.89, -301.68, -128.40, 103.83, -165.45, 173.74
# of Transactions, 444, 443, 443, 444, 443

Synchronized method:
Account, ATM 0, ATM 1, ATM 2, ATM 3, ATM 4, Transaction Sum, Balance
0, 109.68, 206.15, 482.22, 297.49, -59.65, 1035.89, 1035.89
1, -123.26, -229.60, 369.57, 187.18, -198.98, 4.91, 4.91
2, 326.85, 247.02, -124.56, 68.14, 437.90, 955.35, 955.35
3, -83.52, 154.05, 104.15, 313.32, -216.91, 271.09, 271.09
4, 274.77, 251.13, 153.58, 147.35, 17.41, 844.24, 844.24
5, 137.12, -196.64, -17.36, 243.93, 20.02, 187.07, 187.07
6, -53.76, -19.88, -251.28, 461.91, 117.58, 254.57, 254.57
7, 69.14, -3.91, -88.01, 173.90, -94.96, 56.16, 56.16
8, 390.75, -57.51, 270.10, 146.84, -1.44, 748.74, 748.74
9, -115.88, -264.73, 152.22, 241.86, 142.41, 155.88, 155.88
# of Transactions, 169, 166, 168, 166, 167

Synchronized statements:
Account, ATM 0, ATM 1, ATM 2, ATM 3, ATM 4, Transaction Sum, Balance
0, 157.37, 164.54, 247.90, -161.94, -75.02, 332.85, 332.85
1, -4.53, -48.39, 140.97, -31.71, 245.28, 301.62, 301.62
2, 313.45, 21.60, 235.10, 121.30, 260.76, 952.21, 952.21
3, -157.13, -75.60, 343.08, 288.97, 143.18, 542.50, 542.50
4, 29.81, 284.44, -81.49, -324.18, 160.94, 69.52, 69.52
5, 512.93, 303.73, 73.00, 72.01, 172.37, 1134.04, 1134.04
6, 312.77, 26.97, 29.00, -274.98, 6.03, 99.79, 99.79
7, -67.18, 28.11, 188.62, -104.12, 36.09, 81.52, 81.52
8, 31.48, 451.04, 174.24, 5.17, 287.17, 949.10, 949.10
9, -72.96, -58.93, -80.25, -35.12, 285.98, 38.72, 38.72
# of Transactions, 172, 170, 170, 170, 167

Synchronized statements per account:
Account, ATM 0, ATM 1, ATM 2, ATM 3, ATM 4, Transaction Sum, Balance
0, -356.88, 230.09, 121.05, 17.74, 139.69, 151.69, 151.69
1, 196.23, 160.88, 435.08, -321.64, -293.67, 176.88, 176.88
2, 42.31, -83.73, 220.07, 355.22, -255.00, 278.87, 278.87
3, -50.23, 794.38, -48.61, -266.61, 411.13, 840.06, 840.06
4, -149.40, -92.54, -11.21, 561.98, -47.66, 261.17, 261.17
5, -55.14, 230.12, 103.13, -107.65, 263.93, 434.39, 434.39
6, 442.87, 115.36, 55.61, -96.76, -142.20, 374.88, 374.88
7, -90.27, -17.98, 98.67, -19.88, 224.26, 194.80, 194.80
8, 86.30, 74.51, 148.25, 464.22, 290.62, 1063.90, 1063.90
9, 652.21, 5.67, -58.23, 69.86, 250.82, 920.33, 920.33
# of Transactions, 281, 287, 281, 282, 287
```

By looking at the output, we can see that:

*   Without any synchronization, doTransaction1(), we can see that every account was corrupted. For example, the balance of account number 0 was reported as 1051.87 by the BankingMain class, but it should be 465.73, which is the sum of balances from all the threads on account number 0.
*   With the synchronized method, doTransaction2(), the balances in the BankingMain class were maintained perfectly correct, but the performance of the threads were reduced dramatically. Without synchronization, BankingThread was performing about 444 transactions in 5 seconds. But with the synchronized method, it was performing only about 169 transactions.
*   By moving the synchronization from the method level to statements level, doTransaction3(), the performance improved slightly, from 169 transactions to 172 transactions.
*   By replacing the central lock, o_lock, with individual locks per account, a_lock[i], the performance improved dramatically, from 172 transactions to 281 transactions. With the central lock, we were putting all other threads on hold while one thread was running the synchronized block. With the individual locks, we were putting only other threads on hold if they happened to work on the same account number as the thread who was running the synchronized block. The chance of this situation is only about 1 over the number of accounts. As the number of accounts increases, the BankingThread will perform better and better.

**Exercise**: Assuming the following class is used in a multiple-threaded program:

```
 public class C {
   public static synchronized void m1() {
      statement block_1
   }
   public synchronized void m2() {
      statement block_2
   }
   public synchronized void m3() {
      statement block_3
   }
   public void m4() {
      synchronized (this) {
         statement block_4
      }
   }
}
```

*   Is it possible that block_1 in one thread could be on hold because of block_1 is running another thread?
*   Is it possible that block_1 in one thread could be on hold because of block_2 is running another thread?
*   Is it possible that block_2 in one thread could be on hold because of block_1 is running another thread?
*   Is it possible that block_2 in one thread could be on hold because of block_2 is running another thread?
*   Is it possible that block_2 in one thread could be on hold because of block_3 is running another thread?
*   Is it possible that block_2 in one thread could be on hold because of block_4 is running another thread?

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Deadlock Condition Example Programs

This chapter provides tutorial notes and tutorial examples to demonstrate deadlock condition. Topics include what is deadlock condition; deadlock examples - 5 Dining Philosophers and Transferring Funds.

> [What Is Deadlock](#part0149.xhtml)
> 
> [Deadlock Example - 5 Dining Philosophers](#part0150.xhtml)
> 
> [Deadlock Example - Transferring Funds](#part0151.xhtml)

Conclusion:

*   Deadlock is a state of execution when 2 or more threads are all put on hold waiting for others to release locks.
*   Deadlock is demonstrated with the 5 dining philosophers simulation program.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Deadlock Condition Example Programs](#part0148.xhtml)

∟What Is Deadlock

This section provides a tutorial example on how to demonstrate a deadlock condition with two Java threads.

**Deadlock**: A state of execution when 2 or more threads are all put on hold, because each of them is holding a synchronization lock while waiting for another lock. The lock each thread is waiting for is held by one of the other threads. So none of threads can move forward.

By definition, deadlock can only happen when the program is running multiple threads, and multiple locks are being used by multiple threads. Therefore:

*   A single-threaded program will never have deadlocks.
*   A program with one lock will never have deadlocks.

Here is a simple program to demonstrate a deadlock with two threads and two locks:

```
 /* SimpleDeadLock.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
public class SimpleDeadLock extends Thread {
   public static Object l1 = new Object();
   public static Object l2 = new Object();
   private int index;
   public static void main(String[] a) {
      Thread t1 = new Thread1();
      Thread t2 = new Thread2();
      t1.start();
      t2.start();
   }
   private static class Thread1 extends Thread {
      public void run() {
         synchronized (l1) {
            System.out.println("Thread 1: Holding lock 1...");
            try { Thread.sleep(10); }
            catch (InterruptedException e) {}
            System.out.println("Thread 1: Waiting for lock 2...");
            synchronized (l2) {
               System.out.println("Thread 2: Holding lock 1 & 2...");
            }
         }
      }
   }
   private static class Thread2 extends Thread {
      public void run() {
         synchronized (l2) {
            System.out.println("Thread 2: Holding lock 2...");
            try { Thread.sleep(10); }
            catch (InterruptedException e) {}
            System.out.println("Thread 2: Waiting for lock 1...");
            synchronized (l1) {
               System.out.println("Thread 2: Holding lock 2 & 1...");
            }
         }
      }
   }
}
```

Output:

```
 Thread 1: Holding lock 1...
Thread 2: Holding lock 2...
Thread 1: Waiting for lock 2...
Thread 2: Waiting for lock 1...
```

As the output shows, after gaining lock 1, thread 1 was put on hold to wait for lock 2, which was held by thread 2 and it will never be released, because thread 2 was also put on hold to wait lock 1, which was held by thread1\. So none of them could move forward. You have to press Ctrl-C to stop program.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Deadlock Condition Example Programs](#part0148.xhtml)

∟Deadlock Example - 5 Dining Philosophers

This section provides a Java program that simulates the deadlock example - 5 Dining Philosophers.

The story of 5 dining philosophers is the most interesting illustration of the deadlock problem. Here is the version of the story from the "The Java Tutorial" by Sun Microsystems.

"Five philosophers are sitting at a round table. In front of each philosopher is a bowl of rice. Between each pair of philosophers is one chopstick. Before an individual philosopher can take a bite of rice, he must have two chopsticks, one taken from the left, and one taken from the right. The philosophers must find some way to share chopsticks such that they all get to eat. "

Deadlock will occur in this story, if all philosophers are taking the chopstick from the left side at the same time, and no one is willing to put down the chopstick until he gets the chopstick on the right side.

Here is a Java program to simulate the story:

```
 /* DinerThread.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
public class DinerThread extends Thread {
   public static final int numberOfThreads = 5;
   public static Object[] listOfLocks = new Object[numberOfThreads];
   public static char[] dinerTable = new char[4*numberOfThreads];
   public static char[] lockedDiner = new char[4*numberOfThreads];
   public static Random randomGenerator = new Random();
   public static int unitOfTime = 500;
   private int threadIndex;
   public static void main(String[] a) {
      for (int i=0; i<numberOfThreads; i++) listOfLocks[i] =
         new Object();
      for (int i=0; i<numberOfThreads; i++) {
         dinerTable[4*i] = '|';
         dinerTable[4*i+1] = ' ';
         dinerTable[4*i+2] = '-';
         dinerTable[4*i+3] = ' ';
         lockedDiner[4*i] = ' ';
         lockedDiner[4*i+1] = '|';
         lockedDiner[4*i+2] = '=';
         lockedDiner[4*i+3] = ' ';
      }
      for (int i=0; i<numberOfThreads; i++) {
         Thread t = new DinerThread(i);
         t.setDaemon(true);
         t.start();
      }
      String lockedString = new String(lockedDiner);
      System.out.println("The diner table:");
      long step = 0;
      while (true) {
         step++;
         System.out.println((new String(dinerTable))+"   "+step);
         if (lockedString.equals(new String(dinerTable)))
            break;
         try {
            Thread.sleep(unitOfTime);
         } catch (InterruptedException e) {
            System.out.println("Interrupted.");
         }
      }
      System.out.println("The diner is locked.");
   }
   public DinerThread(int i) {
      threadIndex = i;
   }
   public void run() {
      while (!isInterrupted()) {
         try {
            sleep(unitOfTime*randomGenerator.nextInt(6));
         } catch (InterruptedException e) {
            break;
         }
         // Try to get the chopstick on the left
         Object leftLock = listOfLocks[threadIndex];
         synchronized (leftLock) {
            int i = 4*threadIndex;
            dinerTable[i] = ' ';
            dinerTable[i+1] = '|';
            dinerTable[i+2] = '=';
            try {
               sleep(unitOfTime*1);
            } catch (InterruptedException e) {
               break;
            }
            // Try to get the chopstick on the right
            Object rightLock =
               listOfLocks[(threadIndex+1)%numberOfThreads];
            synchronized (rightLock) {
               dinerTable[i+2] = 'o';
               dinerTable[i+3] = '|';
               dinerTable[(i+4)%(4*numberOfThreads)] = ' ';
               try {
                  sleep(unitOfTime*1);
               } catch (InterruptedException e) {
                  break;
               }
               dinerTable[i] = '|';
               dinerTable[i+1] = ' ';
               dinerTable[i+2] = '-';
               dinerTable[i+3] = ' ';
               dinerTable[(i+4)%(4*numberOfThreads)] = '|';
            }
         }
      }
   }
}
```

In the program, the diner table is represented by an array of characters. '|' represents a chopstick, '-', '=' and 'o' represent a philosopher with no chopstick, one chopstick and two chopsticks respectively.

There are 5 threads representing the 5 philosophers. Each of them will pause for some time before trying to synchronize with the lock that is associated with the chopstick on the left side. Once passed the first synchronization, the thread will take the chopstick on the left side, and continue to try to synchronize with the lock that is associated with the chopstick on the right side. Once passed the second synchronization, the thread will take the chopstick on the right side, and hold both chopsticks for a moment. The threads will then put back both chopsticks and release both locks.

Execute the program several times. You will see that it behaves differently each time. But soon or later, the diner table will be locked with each thread holding a lock that is needed by the thread on the left side, and waiting for a lock that is held by the thread on the right side.

One of my executions gave the following output:

```
 The diner table:
| - | - | - | - | -    1
| -  |=  |= | - | -    2
| -  |=  |o|  - | -    3
 |= | - | -  |= | -    4
 |o|  - | -  |o|  -    5
| -  |= | - | -  |=    6
  -  |o|  -  |=  |o|   7
| - | -  |=  |o|  -    8
| -  |=  |o|  - | -    9
 |=  |o|  - | - | -    10
 |o|  - | - | - | -    11
| - | - | - | -  |=    12
 |= | - | -  |=  |=    13
 |o|  -  |=  |=  |=    14
| - | -  |=  |o|  -    15
| -  |=  |o|  -  |=    16
  -  |o|  - | -  |o|   17
| - | -  |= | - | -    18
 |= | -  |o|  - | -    19
 |o|  - | -  |= | -    20
| -  |=  |=  |o|  -    21
| -  |=  |= | -  |=    22
  -  |=  |o|  -  |o|   23
 |= | - | - | - | -    24
 |=  |= | -  |= | -    25
 |=  |o|  -  |o|  -    26
| - | - | - | - | -    27
| -  |=  |= | -  |=    28
  -  |=  |o|  -  |o|   29
| -  |o|  - | - | -    30
| - | -  |=  |= | -    31
 |=  |=  |=  |o|  -    32
 |=  |=  |o|  -  |=    33
 |=  |o|  - | -  |=    34
 |o|  -  |= | -  |=    35
  -  |=  |o|  -  |o|   36
 |=  |o|  -  |= | -    37
 |o|  - | -  |=  |=    38
  - | - | -  |=  |o|   39
 |= | -  |=  |o|  -    40
 |=  |=  |o|  - | -    41
 |=  |o|  - | - | -    42
 |o|  - | - | - | -    43
| -  |= | - | - | -    44
 |=  |=  |= | -  |=    45
 |=  |=  |=  |=  |=    46
The diner is locked.
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Deadlock Condition Example Programs](#part0148.xhtml)

∟Deadlock Example - Transferring Funds

This section provides a Java program that simulates the deadlock example - Transferring Funds.

Another illustration of the deadlock problem is the following program, which simulates multiple threads taking transactions to transfer funds among different accounts.

```
 /* FundTransfer.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.util.*;
public class FundTransfer {
   public static final int numberOfAccounts = 50; // number of accounts
   public static long[] balance = new long[numberOfAccounts];
   public static Random randomGenerator = new Random();
   private static final int numberOfThreads = 10;
   private static TransferThread[] threadList =
      new TransferThread[numberOfThreads];
   private static Object[] lockList = new Object[numberOfAccounts];
   public static void main(String[] a) {
      for (int i=0; i<numberOfAccounts; i++)
         lockList[i] = new Object();
      for (int i=0; i<numberOfAccounts; i++)
         balance[i] = 100000;
      ThreadGroup g = new ThreadGroup("The Group");
      for (int i=0; i<numberOfThreads; i++) {
         TransferThread t = new TransferThread(g,String.valueOf(i));
         t.start();
         threadList[i] = t;
      }
      System.out.print("\nNumber of transactions performed per thread:");
      long steps = 0;
      while (true) {
         steps++;
         System.out.print("\nStep="+steps+": ");
         for (int i=0; i<numberOfThreads; i++)
            System.out.print(threadList[i].counts+" ");
         try {
            Thread.sleep(200);
         } catch (InterruptedException e) {
            System.out.println("Interrupted.");
         }
      }
   }
   public static boolean doTransfer(int i, int j, long a) {
      boolean ok = false;
      synchronized (lockList[i]) {
         long c = balance[i]; // get balance of the from-account
         ok = c-a>=0;
         if (ok) { // stop account balance going negative
            try {
               Thread.sleep(0,1); // slow down the process
            } catch (InterruptedException e) {
               Thread.currentThread().interrupt(); // re-set the flag
            }
            synchronized (lockList[j]) {
               long d = balance[j]; // get balance of the to-account
               ok = d+a>=0;
               if (ok) { // stop account balance going negative
                  balance[i] = c-a; // update the from-account
                  balance[j] = d+a; // update the to-account
               }
            }
         }
      }
      return ok;
   }
   public static class TransferThread extends Thread {
      public long counts;
      public TransferThread(ThreadGroup g, String n) {
         super(g,n);
         counts = 0;
      }
      public void run() {
         while (!isInterrupted()) {
            counts++;
            Random r = randomGenerator;
            int m = numberOfAccounts;
            int i = r.nextInt(m); // from-account number
            int j = r.nextInt(m); // to-account number
            int t = 2*r.nextInt(2)-1; // type of transaction
            long a = (long) t*r.nextInt(10000);
            if (i!=j) doTransfer(i,j,a);
            try {
               sleep(r.nextInt(200)); // pause between transactions
            } catch (InterruptedException e) {
               break;
            }
         }
      }
   }
}
```

The logic of the program is simple. The main thread launches 10 sub threads at the beginning, and allows each thread to repeatedly transfer some fund from a randomly selected account to another randomly selected account. The main thread keeps checking the number of transactions each thread has performed so far.

If it happens that one thread is transferring fund from account A to B, and another thread is transferring fund from account B to A at the same time, the two threads will become deadlock to each other. Then, if another thread is trying to transfer fund from account C to A or B, it will be put on hold also, because A and B are both locked. Account C will be locked also in this case. If another thread is trying to transfer fund from A or B to D, it will also be put on hold, but account D will not be locked. Slowly, all threads will be put on hold, because of the two deadlocked threads.

Execute the program several times. You will see that it behaves differently each time. But soon or later, the all threads will be put on hold as predicted. One of my executions gave the following output:

```
 Number of transactions performed per thread:
Step=1: 0 0 0 0 0 0 1 1 1 1
Step=2: 2 2 2 4 3 3 2 2 6 2
Step=3: 5 3 4 6 4 6 3 4 10 4
Step=4: 6 5 5 8 6 11 4 6 13 6
Step=5: 8 8 8 11 8 14 5 7 14 7
Step=6: 9 10 10 13 9 16 7 10 15 8
Step=7: 11 12 12 14 12 18 10 12 18 11
Step=8: 14 14 15 17 13 20 12 14 21 12
Step=9: 15 15 17 19 17 22 14 17 23 15
Step=10: 18 16 19 20 18 23 16 21 24 18
......
Step=813: 1613 1652 1607 1605 1627 1606 1613 1623 1601 1647
Step=814: 1616 1653 1611 1606 1630 1608 1615 1624 1604 1649
Step=815: 1617 1656 1615 1608 1631 1610 1616 1626 1607 1651
Step=816: 1619 1658 1617 1613 1633 1611 1619 1627 1608 1653
Step=817: 1621 1660 1617 1614 1633 1613 1621 1629 1610 1655
                    ^1        ^2
Step=818: 1622 1660 1617 1615 1633 1614 1623 1632 1612 1656
               ^3
Step=819: 1623 1660 1617 1615 1633 1615 1625 1634 1613 1657
                         ^4
Step=820: 1624 1660 1617 1615 1633 1617 1627 1636 1615 1659
Step=821: 1624 1660 1617 1615 1633 1617 1629 1638 1617 1662
          ^5                       ^6
Step=822: 1624 1660 1617 1615 1633 1617 1630 1640 1621 1664
Step=823: 1624 1660 1617 1615 1633 1617 1631 1641 1624 1666
Step=824: 1624 1660 1617 1615 1633 1617 1632 1643 1626 1667
Step=825: 1624 1660 1617 1615 1633 1617 1632 1645 1627 1668
                                        ^7
Step=826: 1624 1660 1617 1615 1633 1617 1632 1647 1628 1668
                                                       ^8
Step=827: 1624 1660 1617 1615 1633 1617 1632 1647 1628 1668
                                             ^9   ^10
```

As you can see, threads 3 and 5 became deadlocked at step 817\. Then within 10 steps, all other 8 threads were stopped.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Garbage Collection and the gc() Method

This chapter describes the garbage collection supported provided by Java. Topics include unused objects, the JVM automatic garbage collection process, the garbage collection method gc() on the default Runtime object.

> [Garbage Collection and Unused Objects](#part0153.xhtml)
> 
> [The Automated Garbage Collection Process](#part0154.xhtml)
> 
> [gc() - The Garbage Collection Method](#part0155.xhtml)
> 
> [Example Program of Using the gc() Method](#part0156.xhtml)

Conclusion:

*   Garbage collector is an independent thread always running in the Java Virtual Machine (JVM).
*   Garbage collector automatically removes unused objects when the free space of the allocated memory is low.
*   gc() method can be called to perform garbage collection explicitly.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Garbage Collection and the gc() Method](#part0152.xhtml)

∟Garbage Collection and Unused Objects

This section describes what is garbage collection and what is an unused object.

**Garbage Collector**: An execution thread that automatically frees up the memory occupied by unused objects. The garbage collector is managed by the JVM and executed separately from the application program threads.

**Garbage Collection**: The process during which the garbage collector actively identifying unused objects, and remove them to frees up the memory.

There are two key questions involved in the garbage collection:

*   How garbage collector identifies objects as unused objects?
*   When garbage collector performs the collection process?

**Unused Object**: An object that has zero live reference pointing to it. Java does not provide us any facilities to check how many references are there for a given object. But we can read the program source code to figure this out.

For example, after executing the following section of code:

```
 String a = new String("Apple");
   a = new String("Banana);
   new String("Orange");
   String g = sub("Grape");
   String x = "Kiwi";
   String y = x;
   x = null;
   ...
   static String sub(String b) {
      String l = new String{"Peach");
      return new String("Pear");
   }
```

objects created by the code will have the following status:

*   String object of "Apple": Unused, because the only reference from "a" is gone now. "a" is pointing to another object now.
*   String object of "Banana": Used, because it is still referred by "a".
*   String object of "Orange": Unused, because it was created, but never referenced by any variables.
*   String object of "Grape": Unused, because the reference from "b" is gone now. "a" is out of scope now after the execution of the method sub().
*   String object of "Peach": Unused, because the reference from "l" is gone now. "l" is out of scope now after the execution of the method sub().
*   String object of "Pear": Used, because the reference returned from the method sub() is in "g" now.
*   String object of "Kiwi": Used, because it is still referred by "y", even the reference from "x" is gone now.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Garbage Collection and the gc() Method](#part0152.xhtml)

∟The Automated Garbage Collection Process

This section a tutorial example on how to find out when the garbage collector automatically performing the garbage collection process.

To understand when the JVM will ask the garbage collector to perform the garbage collection process, I wrote the following tutorial example to run a loop of many steps. In each step, a new 1-MB object is created and an old 1-MB object is freed up, except for the first 32 steps:

```
 /* GarbageCollection.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class GarbageCollection {
   public static void main(String[] a) {
      int steps = 10000;
      int size = 32;
      Object[] queue = new Object[size];
      Runtime rt = Runtime.getRuntime();
      System.out.println("Memory: Maximum   Total   Free   Used");
      for (int m=0; m<steps; m++) {
         for (int n=0; n<size-1; n++)
            queue[size-n-1] = queue[size-n-2];
         queue[0] = getOneMega();
         System.out.println(m+"   "+rt.maxMemory()
            +"   "+rt.totalMemory()+"   "+rt.freeMemory()
            +"   "+(rt.totalMemory()-rt.freeMemory()));
         try {
            Thread.sleep(1000/10);
         } catch (InterruptedException e) {
            System.out.println("Interreupted...");
         }
      }
   }
   private static Object getOneMega() {
      return new long[1024*128]; // 1MB
   }
}
```

Note that:

*   The method getOneMega() is used to create a 1-MB object, which is an array of "long" with 1024*128 = 131072 elements. Since size of data type "long" is 8 bytes, the total size of the array is 131072 * 8 = 1048576 bytes (1MB).
*   "queue" is an array to hold 32 object references.
*   The outer loop, "for (int m=0; m<steps; m++) {...}" controls testing steps.
*   At each step, the inner loop, "for (int n=0; n<size-1; n++) {...}" shifts all references by one position towards right.
*   At each step, the inner loop, "for (int n=0; n<size-1; n++) {...}" shifts all references in the "queue" by one position.
*   After shifting operation, the reference of a new 1-MB object is added to the beginning of the "queue".
*   For the first 32 steps, the shifting operation will remove references to any existing objects, since the "queue" is not full yet.
*   After the first 32 steps, the shifting operation will remove the reference of the oldest object from the "queue".

Running this sample program, I got the following output:

```
 Memory:
      Maximum      Total       Free       Used
 0   66650112    5177344    3948480    1228864
 1   66650112    5177344    2899888    2277456
 2   66650112    5177344    1832880    3344464
 3   66650112    6410240    2087472    4322768   //Total increased
 4   66650112    6410240    1038880    5371360
 5   66650112    9908224    3488272    6419952   //Total increased
 6   66650112    9908224    2439680    7468544
 7   66650112    9908224    1391088    8517136
 8   66650112   15347712    5778048    9569664   //Total increased
 9   66650112   15347712    4740368   10607344
10   66650112   15347712    3695672   11652040
11   66650112   15347712    2649648   12698064
12   66650112   15347712    1602736   13744976
13   66650112   15347712     555248   14792464
14   66650112   26546176   10708152   15838024   //Total increased
15   66650112   26546176    9659648   16886528
16   66650112   26546176    8611056   17935120
17   66650112   26546176    7562464   18983712
18   66650112   26546176    6513872   20032304
19   66650112   26546176    5465280   21080896
20   66650112   26546176    4416688   22129488
21   66650112   26546176    3368096   23178080
22   66650112   26546176    2319504   24226672
23   66650112   26546176    1270912   25275264
24   66650112   45334528   19010672   26323856   //Total increased
25   66650112   45334528   17962080   27372448
26   66650112   45334528   16913488   28421040
27   66650112   45334528   15864896   29469632
28   66650112   45334528   14816304   30518224
29   66650112   45334528   13767712   31566816
30   66650112   45334528   12719120   32615408
31   66650112   45334528   11670528   33664000
32   66650112   45334528   10621936   34712592
33   66650112   45334528    9573344   35761184
34   66650112   45334528    8524752   36809776
35   66650112   45334528    7476160   37858368
36   66650112   45334528    6427568   38906960
37   66650112   45334528    5378976   39955552
38   66650112   45334528    4330384   41004144
39   66650112   45334528    3281792   42052736
40   66650112   45334528    2233200   43101328
41   66650112   45334528    1184608   44149920
42   66650112   58486784   24822784   33664000   //Total increased
                                                 //Garbage collected
43   66650112   58486784   23774192   34712592
44   66650112   58486784   22725600   35761184
45   66650112   58486784   21677008   36809776
46   66650112   58486784   20628416   37858368
47   66650112   58486784   19579824   38906960
48   66650112   58486784   18531232   39955552
49   66650112   58486784   17482640   41004144
50   66650112   58486784   16434048   42052736
51   66650112   58486784   15385456   43101328
52   66650112   58486784   14336864   44149920
53   66650112   58486784   13288272   45198512
54   66650112   58486784   12239680   46247104
55   66650112   58486784   11191088   47295696
56   66650112   58486784   10142496   48344288
57   66650112   58486784    9093904   49392880
58   66650112   58486784    8045312   50441472
59   66650112   58486784    6996720   51490064
60   66650112   58486784    5948128   52538656
61   66650112   58486784    4899536   53587248
62   66650112   58486784    3850944   54635840
63   66650112   58486784   24822784   33664000   //Garbage collected
...
```

Several notes about the output:

*   Between step 0 and 31, no garbage collection happened, because there was no unused objects. JVM increased the total memory 5 times to 45334528 bytes, to have enough space for 32 new objects.
*   From step 32 to 41, unused object are available for garbage collection. But JVM decided to use its free memory for new objects.
*   At step 42, the free memory was very low, 1184608 bytes. JVM decided to increase the total memory, and call for garbage collection.
*   After step 43, JVM stopped to increase total memory. It called for garbage collection when its free memory is too low.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Garbage Collection and the gc() Method](#part0152.xhtml)

∟gc() - The Garbage Collection Method

This section provides a tutorial example on how to use the garbage collection method gc() on the default Runtime object to control the garbage collection process by yourself.

If you do not like the way JVM automatically performing the garbage collection process. you can use the gc() method of the default Runtime object to control the garbage collection process by yourself.

To test this gc() method, I modified the tutorial example presented in the previous section to explicitly perform garbage collection whenever the free memory size is below 10 MB:

```
 /* GarbageCollectionForced.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class GarbageCollectionForced {
   public static void main(String[] a) {
      int steps = 10000;
      int size = 32;
      Object[] queue = new Object[size];
      Runtime rt = Runtime.getRuntime();
      System.out.println("Memory: Maximum   Total   Free   Used");
      for (int m=0; m<steps; m++) {
         for (int n=0; n<size-1; n++)
            queue[size-n-1] = queue[size-n-2];
         queue[0] = getOneMega();

         System.out.println(m+"   "+rt.maxMemory()
            +"   "+rt.totalMemory()+"   "+rt.freeMemory()
            +"   "+(rt.totalMemory()-rt.freeMemory()));
         // Forcing a garbage collection
         if (rt.freeMemory()<10485760) {
            rt.gc();
            System.out.println(m+"   "+rt.maxMemory()
               +"   "+rt.totalMemory()+"   "+rt.freeMemory()
               +"   "+(rt.totalMemory()-rt.freeMemory())
               +"   //Garbage collected");
         }
         try {
            Thread.sleep(1000/10);
         } catch (InterruptedException e) {
            System.out.println("Interreupted...");
         }
      }
   }
   private static Object getOneMega() {
      return new long[1024*128]; // 1MB
   }
}
```

Running this modified sample program, I got the following output:

```
 Memory:
      Maximum      Total       Free       Used
 0   66650112    5177344    3948456    1228888
 0   66650112    5177344    4000416    1176928   //Garbage collected
 1   66650112    5177344    2951824    2225520
 1   66650112    5177344    2951824    2225520   //Garbage collected
 2   66650112    5177344    1903232    3274112
 2   66650112    6410240    3136128    3274112   //Garbage collected
 3   66650112    6410240    2087536    4322704
 3   66650112    8159232    3836672    4322560   //Garbage collected
 4   66650112    8159232    2788080    5371152
 4   66650112    9908224    4537072    5371152   //Garbage collected
 5   66650112    9908224    3488480    6419744
 5   66650112   11653120    5233376    6419744   //Garbage collected
 6   66650112   11653120    4184784    7468336
 6   66650112   13402112    5933776    7468336   //Garbage collected
 7   66650112   13402112    4885184    8516928
 7   66650112   15347712    6826848    8520864   //Garbage collected
 8   66650112   15347712    5778256    9569456
 8   66650112   17158144    7599600    9558544   //Garbage collected
 9   66650112   17158144    6551008   10607136
 9   66650112   19038208    8434088   10604120   //Garbage collected
10   66650112   19038208    7385496   11652712
10   66650112   20918272    9267840   11650432   //Garbage collected
11   66650112   20918272    8219248   12699024
11   66650112   22794240   10096904   12697336   //Garbage collected
12   66650112   22794240    9048312   13745928
12   66650112   24674304   10929744   13744560   //Garbage collected
13   66650112   24674304    9881152   14793152
13   66650112   26554368   11762080   14792288   //Garbage collected
14   66650112   26554368   10713488   15840880
15   66650112   26554368    9665008   16889360
15   66650112   30310400   13421040   16889360   //Garbage collected
16   66650112   30310400   12372448   17937952
17   66650112   30310400   11323856   18986544
18   66650112   30310400   10275264   20035136
18   66650112   35946496   15911360   20035136   //Garbage collected
19   66650112   35946496   14862768   21083728
20   66650112   35946496   13814176   22132320
21   66650112   35946496   12765584   23180912
22   66650112   35946496   11716992   24229504
23   66650112   35946496   10668400   25278096
24   66650112   35946496    9619808   26326688
24   66650112   47218688   20892000   26326688   //Garbage collected
25   66650112   47218688   19843408   27375280
26   66650112   47218688   18794816   28423872
27   66650112   47218688   17746224   29472464
28   66650112   47218688   16697632   30521056
29   66650112   47218688   15649040   31569648
30   66650112   47218688   14600448   32618240
31   66650112   47218688   13551856   33666832
32   66650112   47218688   12503264   34715424
33   66650112   47218688   11454672   35764016
34   66650112   47218688   10406080   36812608
34   66650112   62246912   27531488   34715424   //Garbage collected
35   66650112   62246912   26482896   35764016
36   66650112   62246912   25434304   36812608
37   66650112   62246912   24385712   37861200
38   66650112   62246912   23337120   38909792
39   66650112   62246912   22288528   39958384
40   66650112   62246912   21239936   41006976
41   66650112   62246912   20191344   42055568
42   66650112   62246912   19142752   43104160
43   66650112   62246912   18094160   44152752
44   66650112   62246912   17045568   45201344
45   66650112   62246912   15996976   46249936
46   66650112   62246912   14948384   47298528
47   66650112   62246912   13899792   48347120
48   66650112   62246912   12851200   49395712
49   66650112   62246912   11802608   50444304
50   66650112   62246912   10754016   51492896
51   66650112   62246912    9705424   52541488
51   66650112   62246912   27531488   34715424   //Garbage collected
...
```

Several interesting notes about the output:

*   Between step 0 and 13, the gc() method is called on every step because the free memory was very low. But gc() did not free up any object, because there was no unused objects in the memory.
*   The gc() method actually caused the JVM to obtain more total memory when the free memory was low. See steps 2, 3, ..., 13\. In another word, the gc() method does not only frees up unused objects, it also tries to obtain more total memory if needed.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Garbage Collection and the gc() Method](#part0152.xhtml)

∟Example Program of Using the gc() Method

This section provides a tutorial example on how to use the garbage collection method gc() on the default Runtime object to test object references and memory usages.

If you want to monitor memory usage of your data objects, you can call the freeMemory(), totalMemory(), and maxMemory() methods of the default Runtime object.

Here is a simple tutorial example to test object references and memory usages:

```
 /* ObjectReferenceAndMemory.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
public class ObjectReferenceAndMemory {
   private static long[] fm = new long[2];
   private static long[] tm = new long[2];
   private static long[] mm = new long[2];
   private static long[] um = new long[2];
   public static void main(String[] args) {
      Runtime rt = Runtime.getRuntime();
      Object h, l, t;
      getMemoryInfo(rt,0);
      h = createOne();
      getMemoryInfo(rt,1);
      printMemoryInfo("One object created:");
      getMemoryInfo(rt,0);
      h = null;
      getMemoryInfo(rt,1);
      printMemoryInfo("One object removed:");

      getMemoryInfo(rt,0);
      h = createList();
      getMemoryInfo(rt,1);
      printMemoryInfo("A linked list of objects created:");
      getMemoryInfo(rt,0);
      h = null;
      getMemoryInfo(rt,1);
      printMemoryInfo("The reference of the first object removed:");

      getMemoryInfo(rt,0);
      h = createList();
      getMemoryInfo(rt,1);
      printMemoryInfo("A linked list of objects created:");
      getMemoryInfo(rt,0);
      l = ((OneMegaArray) h).last(); // the last object of the list
      h = null;
      getMemoryInfo(rt,1);
      printMemoryInfo("The reference of the first object removed,"
         + "\nbut the reference of the last object is maintained:");

      getMemoryInfo(rt,0);
      h = createCircle();
      getMemoryInfo(rt,1);
      printMemoryInfo("A linked circle of objects created:");
      getMemoryInfo(rt,0);
      t = ((OneMegaArray) h).next;
      t = ((OneMegaArray) t).next; // the third object of the circle
      h = null;
      getMemoryInfo(rt,1);
      printMemoryInfo("The reference of the first object removed,"
         + "\nbut the reference of the third object is maintained:");
   }
   public static Object createOne() {
      return new OneMegaArray();
   }
   public static Object createList() {
      OneMegaArray o3 = new OneMegaArray();
      OneMegaArray o2 = new OneMegaArray();
      o2.next = o3;
      OneMegaArray o1 = new OneMegaArray();
      o1.next = o2;
      return o1;
   }
   public static Object createCircle() {
      OneMegaArray o3 = new OneMegaArray();
      OneMegaArray o2 = new OneMegaArray();
      o2.next = o3;
      OneMegaArray o1 = new OneMegaArray();
      o1.next = o2;
      o3.next = o1;
      return o1;
   }
   public static void printMemoryInfo(String title) {
      System.out.println("\n"+title);
      System.out.println("Free memory: "+fm[1]+" - "+fm[0]
         +" = " +(fm[1]-fm[0]));
      System.out.println("Total memory: "+tm[1]+" - "+tm[0]
         +" = " +(tm[1]-tm[0]));
      System.out.println("Maximum memory: "+mm[1]+" - "+mm[0]
         +" = " +(mm[1]-mm[0]));
      System.out.println("Memory used: "+um[1]+" - "+um[0]
         +" = " +(um[1]-um[0]));
   }
   public static void getMemoryInfo(Runtime rt, int i) {
      rt.gc();
      fm[i] = rt.freeMemory();
      tm[i] = rt.totalMemory();
      mm[i] = rt.maxMemory();
      um[i] = tm[i]-fm[i];
   }
   private static class OneMegaArray {
      private long[] data = new long[128*1024]; // 1 MB data
      public Object next = null; // a pointer
      public Object last() {
         OneMegaArray o = this;
         while (o.next!=null) o = (OneMegaArray)o.next;
         return o;
      }
   }
}
```

Running this modified sample program with JDK 1.6, I got the following output:

```
 One object created:
Free memory: 4018760 - 5067440 = -1048680
Total memory: 5177344 - 5177344 = 0
Maximum memory: 66650112 - 66650112 = 0
Memory used: 1158584 - 109904 = 1048680

One object removed:
Free memory: 5067584 - 4018760 = 1048824
Total memory: 5177344 - 5177344 = 0
Maximum memory: 66650112 - 66650112 = 0
Memory used: 109760 - 1158584 = -1048824

A linked list of objects created:
Free memory: 3154656 - 5067584 = -1912928
Total memory: 6410240 - 5177344 = 1232896
Maximum memory: 66650112 - 66650112 = 0
Memory used: 3255584 - 109760 = 3145824

The reference of the first object removed:
Free memory: 6300480 - 3154656 = 3145824
Total memory: 6410240 - 6410240 = 0
Maximum memory: 66650112 - 66650112 = 0
Memory used: 109760 - 3255584 = -3145824

A linked list of objects created:
Free memory: 3154656 - 6300480 = -3145824
Total memory: 6410240 - 6410240 = 0
Maximum memory: 66650112 - 66650112 = 0
Memory used: 3255584 - 109760 = 3145824

The reference of the first object removed,
but the reference of the last object is maintained:
Free memory: 5251872 - 3154656 = 2097216
Total memory: 6410240 - 6410240 = 0
Maximum memory: 66650112 - 66650112 = 0
Memory used: 1158368 - 3255584 = -2097216

A linked circle of objects created:
Free memory: 3855040 - 5251872 = -1396832
Total memory: 8159232 - 6410240 = 1748992
Maximum memory: 66650112 - 66650112 = 0
Memory used: 4304192 - 1158368 = 3145824

The reference of the first object removed,
but the reference of the third object is maintained:
Free memory: 3855040 - 3855040 = 0
Total memory: 8159232 - 8159232 = 0
Maximum memory: 66650112 - 66650112 = 0
Memory used: 4304192 - 4304192 = 0
```

Nothing unexpected in the output.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Assert Statements and -ea" Optionxhtml

This chapter provides tutorial examples and notes on Java assertion facility. Topics include 'assert' statements; '-ea' JVM option to enable assertion.

> ["assert" Statements](#part0158.xhtml)
> 
> [JVM "-ea" and "-da" Options](#part0159.xhtml)

Conclusion:

*   An "assert" statement allows you to make an assertion in the execution flow. "assert" statements are executed only when "-ea" JVM option is specified.
*   "-ea" JVM option allows you to enable assertion on all application classes.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Assert Statements and -ea" Option](#part0157.xhtml)

∟"assert" Statements

This section describes 'assert' statement, which allows you to make an assertion in the execution flow. 'assert' statements are executed only when -ea' JVM option is specified.

**What Is "assert" Statement?** - An "assert" statement allows you to make an assertion in the execution flow. "assert" statements are executed only when "-ea" JVM option is specified. When executed an "assert" statement will throw an exception if the given assertion condition fails.

Here is the syntax for an "assert" statement. "exception_message" is optional.

```
 assert assertion_condition
assert assertion_condition : exception_message
```

Here is a sample program that shows you how to use "assert" statements:

```
 /* AssertStatementTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class AssertStatementTest {
   public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      int hour = Integer.parseInt​(arg[0]);
      out.println("Hour specified: "+hour);
      greeting(hour);
   }

   private static void greeting(int hour) {

      // Assertion on hour must >= 0
      assert hour >= 0 : "Hour = "+hour+". It be must be >= 0.";

      // Assertion on hour must < 24
      assert hour < 24 : "Hour = "+hour+". It be must be < 24.";

      // Assuming hour value is between 0 and 23
      if (hour < 6)
         System.out.println("Why are you not sleeping?");
      else if (hour < 12)
         System.out.println("Good morning!");
      else if (hour < 18)
         System.out.println("Good afternoon!");
      else if (hour < 22)
         System.out.println("Good evening!");
      else
         System.out.println("Good night!");
   }
}
```

If you compile and run the above program with different hour values, you will see:

```
 herong> java AssertStatementTest.java 8
Hour specified: 8
Good morning!

herong> java AssertStatementTest.java 18
Hour specified: 18
Good evening!

herong> java AssertStatementTest.java 28
Hour specified: 28
Good night!

herong> java AssertStatementTest.java -8
Hour specified: -8
Why are you not sleeping?
```

As you can see, "assert" statements were not executed by default. the greeting() method prints unwanted greeting messages, when invoked as greeting(28) and greeting(-8).

See the next tutorial to turn on the JVM assert option detect the issue.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Assert Statements and -ea" Option](#part0157.xhtml)

∟JVM "-ea" and "-da" Options

This section describes '-ea' and '-da' JVM option, which are used to enable or disable assertion on application classes.

By default, "assert" statements in your are not execution to save execution time. If you are running a Java application with "assert" statements added, you can turn on the JVM assertion option to troubleshoot execution issues.

JVM ("java" command) supports a number of assertion options:

*   "-ea" - Enable assertion on all application classes.
*   "-da" - Disable assertion on all application classes.
*   "-ea:class_name" - Enable assertion on the given class.
*   "-da:class_name" - Disable assertion on the given class.
*   "-esa" - Enable assertion on all system classes.
*   "-dsa" - Disable assertion on all system classes.

Let's re-run the sample program in the previous tutorial with the "-ea" option:

```
 herong> java -ea AssertStatementTest.java 8
Hour specified: 8
Good morning!

herong> java -ea AssertStatementTest.java 18
Hour specified: 18
Good evening!

herong> java -ea AssertStatementTest.java 28
Hour specified: 28
Exception in thread "main" java.lang.AssertionError:
  Hour = 28\. It be must be < 24.
  at AssertStatementTest.greeting(AssertStatementTest.java:19)
  at AssertStatementTest.main(AssertStatementTest.java:10)

herong> java -ea AssertStatementTest.java -8
Hour specified: -8
Exception in thread "main" java.lang.AssertionError:
  Hour = -8\. It be must be >= 0.
  at AssertStatementTest.greeting(AssertStatementTest.java:16)
  at AssertStatementTest.main(AssertStatementTest.java:10)
```

As you can see, both "assert" statements were executed. AssertionError messages were corrected generated.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Annotation Statements and Declarationsxhtml

This chapter provides tutorial notes on annotation. Topics include declaring new annotation type; using 'interface' for annotations; specifying default values to annotation elements; shorthand format of annotation invocation with a single element or no element; obtaining annotation information at runtime using getAnnotations() method; predefined annotations in Java.

> [What Is Annotation](#part0161.xhtml)
> 
> [Use "interface" as Annotation](#part0162.xhtml)
> 
> [Default Values for Annotation Elements](#part0163.xhtml)
> 
> [Single-Element Annotation Invocation](#part0164.xhtml)
> 
> [No-Element (Marker) Annotation Invocation](#part0165.xhtml)
> 
> [getAnnotations() Method - Annotation APIs](#part0166.xhtml)
> 
> [Predefined Annotation Types](#part0167.xhtml)

Conclusion:

*   Annotation is a programming facility that allows you to associates additional information with a program construct like class, method, variable, etc.
*   "@interface" statements are used to declare new annotation types, which are special interface types.
*   Annotation elements are methods declared in interfaces.
*   "default" keyword is used to specify default values to annotation elements.
*   Annotation invocation with a single element named "value" can be shorthanded as @Type(value).
*   Annotation invocation with no element (called marker annotation) can be shorthanded as @Type.
*   Java provides getAnnotations() method and other APIs to help you obtain annotation information at runtime.
*   Java provides a number of predefined annotation types. Most of them are used by the compiler to prevent programming mistakes.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟What Is Annotation

This section describes the annotation programming facility that allows you to associates additional information with a program construct.

**What Is Annotation?** - Annotation is a programming facility that allows you to associates additional information with a program construct like class, method, variable, etc.

Information provided by an annotation has no impact on the behavior of the program construct. But Java compiler and other tools can make use of the annotated information.

Annotation facility is designed in Java with 4 components:

1\. Annotation Type - A special kind of interface type that defined by a "@interface" declaration statement (also called annotation declaration statement).

2\. Annotation Declaration - A "@interface" declaration statement that defines an annotation type with or without annotation elements to capture annotated information.

3\. Annotation Element - An special method with no parameters declared in an annotation type to capture a piece of annotated information.

4\. Annotation Invocation - A "@annotation_type_name(annotated_information)" statement to invoke a given annotation type with specified annotated information. Annotation invocation statements can only be placed immediately before declaration statements of targeted program constructs.

Here is an example of "enum" declaration statement:

```
 /* Header.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */

// Annotation declaration
@interface Header {
   String usage();    // Usage of the targeted construct
}
```

Now we can use this annotation type to associate information with different types of program constructs using annotation invocation statements.

```
 /* HeaderTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */

// Annotation invocation targeting a static variable
@Header(usage="Testing the @Header annotation.")
class HeaderTest {

   // Annotation invocation targeting a static variable
   @Header(usage="To whom you want to greet.")
   private static String name = "Herong";

   // Annotation invocation targeting a method
   @Header(usage="The execution entry point.")
   public static void main(String[] arg) {

      // Annotation invocation targeting a local variable
      @Header(usage="The execution entry point.")
      String message = "How are you?";

      System.out.println(name+", "+message);
   }
}
```

If you compile and run HeaderTest.java, you will get:

```
 herong> javac Header.java

herong> javac HeaderTest.java

herong> java Header
Herong, How are you?
```

As you can see, those annotation invocation statements have no impact on the compilation and execution.

So annotations are useless from the execution point of view. But they do offer you a standard way of adding structured comments to your Java program.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟Use "interface" as Annotation

This section provides a tutorial example on how to use 'interface' type to do the same job, roughly, as 'annotation' type.

Based on the Java Language Specifications, an annotation type is actually an interface type.

So I think the Java compiler is actually:

*   Converting "@interface" (annotation type) declaration statements into "interface" declaration statements.
*   Converting annotation type element declarations into interface method declarations.
*   Converting annotation invocation statements into "class" declaration statements to implement the declared interface type.
*   Converting annotated information (annotation element-value pairs) into methods with return statements overriding those in the interface type.

Let's look at the following sample program that uses the annotation type:

```
 /* HeaderAnnotation.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class HeaderAnnotation {
   // Annotation declaration
   @interface Header {
      String usage();    // Usage of the targeted construct
      int version();     // Version number of targeted construct
   }

   // Annotation invocation
   @Header(
      usage="The execution entry point.",
      version=10
   )
   public static void main(String[] arg) {
      System.out.println("Hello world!");
   }
}
```

We can rewrite the above program using interface type:

```
 /* HeaderInterface.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class HeaderInterface {
   // Annotation declaration
   interface Header {
      public String usage();    // Usage of the targeted construct
      public int version();     // Version number of targeted construct
   }

   // Annotation invocation
   class Header1 implements Header {
      public String usage() { return "The execution entry point."; }
      public int version() { return 10; }
   }
   public static void main(String[] arg) {
      System.out.println("Hello world!");
   }
}
```

If you compile and run both programs, you will get:

```
 herong> java HeaderAnnotation.java
Hello world!

herong> java HeaderInterface.java
Hello world!
```

As you can see, we managed to do the same job, roughly, using interface type instead of annotation type.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟Default Values for Annotation Elements

This section provides a tutorial example on how to declare default values for annotation elements and how to use default values in annotation invocation statements.

When you declare an annotation type, you can provide default values for annotation elements. The default value is specified at the end of the element declaration and follows the keyword "default"

When you invoke an annotation type that has an element with a default value, you can take the default value by skipping this element in the argument list.

Here is a sample program that shows you how to declare and use annotation element default values.

```
 /* DefaultValueAnnotation.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class DefaultValueAnnotation {

   // Annotation declaration
   @interface Header {
      String usage();    // Usage of the targeted construct
      int version();     // Version number of targeted construct
      String author() default "Unknown"; // Default value provided
   }

   // Annotation invocation - All values provided
   @Header(usage="Entry point", version=1, author="Herong")
   public static void main(String[] arg) {
      printMsg("Hello world!");
   }

   // Annotation invocation - Default value used
   @Header(usage="Display message", version=10)
   public static void printMsg(String msg) {
      System.out.println(msg);
   }
}
```

If you compile and run the program, you will get:

```
 herong> java DefaultValueAnnotation.java

Hello world!
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟Single-Element Annotation Invocation

This section provides a tutorial example on how to use the shorthand format for a single annotation element named as 'value' in annotation invocation statements.

If an annotation invocation statement only has a single annotation element and the element name is "value", you can specify the element value without the element name in the argument list.

So the following two statements are the same, if @Author annotation has an element called "value" and other elements have default values.

```
 @Author(value="Herong") class X {...}

// Shorthand format of the above
@Author("Herong") class X {...}
```

Here is a sample program that shows you how to use the shorthand format for a single annotation element named as "value" in annotation invocation statements.

```
 /* SingleElementAnnotation.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class SingleElementAnnotation {
   // Annotation declaration
   @interface Author {
      String value() default "Unknown";    // Special element
      String email() default "info@nowhere.com";
   }

   // Annotation invocation - All elements provided
   @Author(value="Herong", email="herong@nowhere.com")
   public static void main(String[] arg) {
      printMsg("Hello world!");
   }

   // Annotation invocation - One element provided
   @Author(value="John")
   public static void printMsg(String msg) {
      printMsgUpper(msg);
   }

   // Annotation invocation - One value only
   @Author(value="Mary")
   public static void printMsgUpper(String msg) {
      System.out.println(msg.toUpperCase());
   }
}
```

If you compile and run the program, you will get:

```
 herong> java SingleElementAnnotation.java

HELLO WORLD!
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟No-Element (Marker) Annotation Invocation

This section provides a tutorial example on how to use the marker format in annotation invocation statements, if no annotation elements are needed.

If an annotation invocation statement has no annotation elements, you can omit the empty parentheses, ().

An annotation invocation statement with no annotation elements is called "Marker Annotation", because it appears like a marker in front of the targeted program construct.

Here is a sample program that shows you how to use the marker format in annotation invocation statements, if no annotation elements are needed.

```
 /* MarkerAnnotation.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class MarkerAnnotation {

   // Annotation declarations
   @interface Herong {
      String value() default "Herong";
      String email() default "herong@nowhere.com";
   }
   @interface John {
      String value() default "John";
      String email() default "john@nowhere.com";
   }

   // Annotation invocation - Marker format
   @Herong public static void main(String[] arg) {
      printMsg("Hello world!");
   }

   // Annotation invocation - Normal format
   @John() public static void printMsg(String msg) {
      System.out.println(msg);
   }
}
```

If you compile and run the program, you will get:

```
 herong> java MarkerAnnotation.java

Hello world!
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟getAnnotations() Method - Annotation APIs

This section provides a tutorial example on how to use the getAnnotations() method and other annotation APIs to obtain annotation information at runtime.

In previous tutorials, we have learned how to declare your own annotation types and use them in annotation invocation statements.

Your own annotation types can help you adding information to your Java source code in a more structured way. But need to build your own tools to parse, validate and process annotated information.

Building an annotation process tool can be done by writing a standalone program in any programming language. But you can also use Java reflection facility obtain annotated information at runtime for processing

Here are some Java APIs that you can use to obtain annotated information at runtime.

1\. java.lang.annotation package - Contains interfaces and classes to support annotation APIs.

2\. @Retention(value=RetentionPolicy.RUNTIME) annotation - Annotates your annotation declarations so that they are retained in a runtime virtual machine.

3\. Class.getAnnotations() method - Returns all annotations associated with this class.

4\. Method.getAnnotations() method - Returns all annotations associated with this method.

5\. Field.getAnnotations() method - Returns all annotations associated with this field (static or instance variable).

Here is a sample program that shows you how to use Java annotation APIs to obtain annotated information at runtime for processing

```
 /* GetAnnotationsTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
import java.lang.annotation.*;
class GetAnnotationsTest {

   @Retention(value=RetentionPolicy.RUNTIME)
   @interface Herong {
      String value() default "Herong";
      String email() default "herong@nowhere.com";
   }

   @Retention(value=RetentionPolicy.RUNTIME)
   @interface John {
      String value() default "John";
      String email() default "john@nowhere.com";
   }

   @John public static String msg = "Hello world!";

   @Herong public static void main(String[] arg) {
      java.io.PrintStream out = System.out;

      try {
        // processing annotations on a class
        java.lang.Class cls = Dummy.class;
        Annotation[] list = cls.getAnnotations();
        out.println("Annotations on class: "+cls.getName());
        for (Annotation a: list) {
           out.println("   "+a);
        }

        // processing annotations on a method
        java.lang.reflect.Method mtd =
           GetAnnotationsTest.class.getMethod("main", String[].class);
        list = mtd.getAnnotations();
        out.println("Annotations on method: "+mtd.getName());
        for (Annotation a: list) {
           out.println("   "+a);
        }

        // processing annotations on a field (variable)
        java.lang.reflect.Field fld =
           GetAnnotationsTest.class.getField("msg");
        list = fld.getAnnotations();
        out.println("Annotations on field: "+fld.getName());
        for (Annotation a: list) {
           out.println("   "+a);
        }

      } catch (Exception e) {
        e.printStackTrace();
      }

      // normal execution
      out.println(msg);
   }

   @Herong @John public class Dummy {}
}
```

If you compile and run the program, you will get:

```
 herong> java GetAnnotationsTest.java

Annotations on class: GetAnnotationsTest$Dummy
   @GetAnnotationsTest$Herong(value="Herong", email="herong@nowhere.com")
   @GetAnnotationsTest$John(value="John", email="john@nowhere.com")
Annotations on method: main
   @GetAnnotationsTest$Herong(value="Herong", email="herong@nowhere.com")
Annotations on field: msg
   @GetAnnotationsTest$John(value="John", email="john@nowhere.com")

Hello world!
```

As you can see, I can easily obtain annotated information and generate a nice report now.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Annotation Statements and Declarations](#part0160.xhtml)

∟Predefined Annotation Types

This section describes annotation types predefined in the current Java version. A tutorial example is also provided on how to use predefined annotation @Deprecated.

In previous tutorials, we have learned how to declare your own annotation types and use them in annotation invocation statements.

Your own annotation types can help you adding information to your Java programs in a more structured way. But need to build your own tools to parse them and process them.

Before build your own annotation processing tool, you may want to look at annotation types predefined in the JDK package and processed by the "javac" compiler and other tools.

Here is a list of annotation types predefined in the current JDK version:

*   @Target - Used to annotate a new annotation declaration to limit its targeted program construct types.
*   @Retention - Used to annotate a new annotation declaration to specify how far the new annotation should be retained, in the source code, in the bytecode class, or in the runtime virtual machine.
*   @Inherited - Used to annotate a new annotation declaration to specify if it should be inherited to subclasses of the targeted class.
*   @Override - Used to annotate a method declaration to inform the compiler that the targeted method is overriding the same method in a superclass. This helps the compiler to detect override methods becoming overload methods coding mistakes.
*   @SuppressWarnings - Used to annotate any declaration to inform the compiler to stop generating some compilation warning messages on the targeted declaration.
*   @Deprecated - Used to annotate any declaration to inform the compiler to generate "deprecation" warning when the targeted declaration is used in any programs.
*   @SafeVarargs - Used to annotate a method declaration to inform the compiler to stop generating the "unchecked" warning when a variable parameter with a non-reifiable element type is used.
*   @Repeatable - Used to annotate a new annotation declaration to specify that it can be used repeatedly as an array element in other annotations.
*   @FunctionalInterface - Used to annotate an interface declaration to specify that it is a functional interface. This helps the compiler to detect declaration mistakes.

Here is a sample program that shows you how to use the predefined annotation, @Deprecated, on a class declaration:

```
 /* Dummy.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
@Deprecated class Dummy {}
```

Now if you use this "@Deprecated" in another Java program, you will get a compilation warning.

```
 /* DeprecatedDummyTest.java
 * Copyright (c) HerongYang.com. All Rights Reserved.
 */
class DeprecatedDummyTest {

   Dummy dummy = new Dummy();

   public static void main(String[] arg) {
      System.out.println("Hello world!");
   }
}
```

Compile the above program to see the warning message:

```
 herong> javac Dummy.java

herong> javac DeprecatedDummyTest.java
Note: DeprecatedDummyTest.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.

herong> javac -Xlint:deprecation DeprecatedDummyTest.java
DeprecatedDummyTest.java:6: warning: [deprecation] Dummy in unnamed package
   has been deprecated
   Dummy dummy = new Dummy();
   ^
DeprecatedDummyTest.java:6: warning: [deprecation] Dummy in unnamed package
   has been deprecated
   Dummy dummy = new Dummy();
                     ^
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Java Related Terminologies

This chapter provides a list of terminologies related to Java programming language.

Here is a list of terminologies related to Java programming language:

**Annotation** - A programming facility that allows you to associates additional information with a program construct like class, method, variable, etc. See examples given in the ["What Is Annotation"](#part0161.xhtml) tutorial.

**Annotation Declaration: @interface** - A "@interface" declaration statement that defines an annotation type with or without annotation elements to capture annotated information. See examples given in the ["What Is Annotation"](#part0161.xhtml) tutorial.

**Annotation Element** - An special method with no parameters declared in an annotation type to capture a piece of annotated information. See examples given in the ["What Is Annotation"](#part0161.xhtml) tutorial.

**Annotation Invocation** - A "@annotation_type_name(annotated_information)" statement to invoke a given annotation type with specified annotated information. Annotation invocation statements can only be placed immediately before declaration statements of targeted program constructs. See examples given in the ["What Is Annotation"](#part0161.xhtml) tutorial.

**Annotation Type** - A special kind of interface type that defined by a "@interface" declaration statement (also called annotation declaration statement). See examples given in the ["What Is Annotation"](#part0161.xhtml) tutorial.

**"assert" Statement** - A debugging statement that allows you to make an assertion in the execution flow. "assert" statements are executed only when "-ea" JVM option is specified. When executed an "assert" statement will throw an exception if the given assertion condition fails. See examples given in the ["'assert' Statements"](#part0158.xhtml) tutorial.

**Bit** - A single digit of a binary number. It can only have two possible values: 0 and 1\. See examples given in the ["What Are Bits and Bytes"](#part0041.xhtml) tutorial.

**Bitwise Operation** - An operation that requires the operand(s) to be represented in a binary format, and applies the calculation one bit at a time. See examples given in the ["Bitwise Operations on byte Values"](#part0044.xhtml) tutorial.

**Bounded Type Parameter?** A type parameter that can be parameterized only with certain limited types. This limitation on type parameters allow you to create generic classes to offer special functions to those limited types. See examples given in the ["Bounded Type Parameters"](#part0086.xhtml) tutorial.

**"break" Statement - Labeled Form** - A branching statement that transfers the control to the end of the labeled enclosing block statement. See examples given in the ["Labeled 'break' Statements"](#part0037.xhtml) tutorial.

**"break" Statement - Non-Labeled Form** - A branching statement that transfers the control to the end of the immediate enclosing "switch", "while", "do", or "for" statement. See examples given in the ["'break' Statements"](#part0036.xhtml) tutorial.

**Byte** - A unit of measure of digital information size with 8 binary digits, 1 byte = 8 bits, which can hold 256 possible values. In Java, 'byte' is a primitive data type that uses a 1-byte (8-bit) storage to store 256 possible integer values from -128 to 127. See examples given in the ["byte Data Type and Implicit Casting"](#part0042.xhtml) tutorial.

**"continue" Statement - Labeled Form** - A branching statement that transfers the control to the end of the labeled enclosing loop block and continues the next iteration of the labeled loop. See examples given in the ["Labeled 'continue' Statements"](#part0039.xhtml) tutorial.

**"continue" Statement - Non-Labeled Form** - A branching statement that transfers the control to the end of the immediate enclosing loop block and continues the next iteration of the loop. See examples given in the ["'continue' Statements"](#part0038.xhtml) tutorial.

**Control Flow Statement** - A statement that changes the default flow of execution, which run statements one by one sequentially. See examples given in the ["What Is Control Flow Statement"](#part0026.xhtml) tutorial.

**Deadlock** - A state of execution when 2 or more threads are all put on waiting, because 2 threads are holding their own synchronization lock while waiting for the lock to released by the other thread. See examples given in the ["What Is Deadlock"](#part0149.xhtml) tutorial.

**"do" Statement** - A looping statement that executes the contained statement immediately, then repeat it while a given condition is true. See examples given in the ["'do' Statements"](#part0035.xhtml) tutorial.

**Enum Type** - A special kind of class type that has a set of pre-defined instances representing a set of static values called enum constants. See examples given in the ["What Is an Enum Type"](#part0063.xhtml) tutorial.

**"for" Statement - Basic Form** - A looping statement that executes the contained statement repeatedly with an initial logic, a looping condition, and an update logic. See examples given in the ["Basic 'for' Statements"](#part0032.xhtml) tutorial.

**"for" Statement - Enhanced Form** - A looping statement that executes the contained statement repeatedly for each element in a given list. See examples given in the ["Enhanced 'for' Statements"](#part0033.xhtml) tutorial.

**Garbage Collector** - An execution thread that automatically frees up the memory occupied by unused objects. The garbage collector is managed by the JVM and executed separately from the application program threads. See examples given in the ["Garbage Collection and Unused Objects"](#part0153.xhtml) tutorial.

**Generic Class** - A class that supports one or more type parameters. When invoked with given type arguments, a generic class becomes a parameterized class. See examples given in the ["What Is a Generic Class"](#part0081.xhtml) tutorial.

**Generic Method** - A static method or instance method that uses one or more type parameters (also called type variables) to make it more generic so that it can be used as multiple variations, one variation for each set of specific type arguments given to type parameters. See examples given in the ["What Is a Generic Method"](#part0094.xhtml) tutorial.

**Generic Type** - A reference data type defined by a generic class or a generic interface that uses type parameters. See examples given in the ["Raw Type, Generic Type and Parameterized Type"](#part0087.xhtml) tutorial.

**"if-then" Statement** - A decision-making statement that executes the contained sub-statement only when the given "boolean" expression is "true". See examples given in the ["'if-then' Statements"](#part0027.xhtml) tutorial.

**"if-then-else" Statement** - A decision-making statement that executes only the first contained sub-statement when the given "boolean" expression is "true". Otherwise it executes only the second contained sub-statement. See examples given in the ["'if-then-else' Statements"](#part0028.xhtml) tutorial.

**Lambda Expression** - A shorthand form of a special anonymous class that implements an interface with only one abstract method. See examples given in the ["What Is Lambda Expression"](#part0106.xhtml) tutorial.

**Literal** - A literal is a string representation of a data value in a Java source code. See examples given in the ["Literals of Primitive Types"](#part0018.xhtml) tutorial.

**Marker Annotation** - A shorthand format, @Type, of annotation invocation statement with no argument required. See examples given in the ["No-Element (Marker) Annotation Invocation"](#part0165.xhtml) tutorial.

**Method Reference** - A shorthand form of a special lambda expression which contains only one static method invocation in the body. See examples given in the ["Lambda Expression as Method Reference"](#part0109.xhtml) tutorial.

**Module** - An aggregation mechanism to manage Java programs and related resources. See examples given in the ["What Is Java Module"](#part0113.xhtml) tutorial.

**Parameterized Type** - A reference data type defined by a parameterized version of a generic class or a generic interface that uses type parameters. See examples given in the ["Raw Type, Generic Type and Parameterized Type"](#part0087.xhtml) tutorial.

**Raw Type** - A parameterized type with the parameter type argument omitted. Raw types are supported in Java to keep legacy applications working. In most cases, a raw type is equivalent a parameterized type with "Object" as the type argument. See examples given in the ["Raw Type, Generic Type and Parameterized Type"](#part0087.xhtml) tutorial.

**Shift Operation** - A bitwise operation that requires the operand to be represented in a binary format, then shifts all bit values to the left or right. See examples given in the ["Shift Operations - Left, Right or Unsigned Right"](#part0046.xhtml) tutorial.

**"switch" Statement** - A decision-making statement that executes a portion of the contained statement block. The executed portion starts from a statement whose label matches a given expression value and ends with the last statement of the block. Otherwise it executes only the second contained sub-statement. See examples given in the ["'switch' Statements"](#part0030.xhtml) tutorial.

**Synchronization** - A programming technique that allows multiple execution threads to share resources synchronously. See examples given in the ["Synchronization Technique - Lock and Synchronized Code"](#part0144.xhtml) tutorial.

**Type Argument Inference** - A process performed by the compiler to determine the actual type argument where the required type argument is no specified. See examples given in the ["What Is Type Argument Inference"](#part0100.xhtml) tutorial.

**"while" Statement** - A looping statement that executes the contained statement repeatedly while a given condition is true. See examples given in the ["'while' Statements"](#part0034.xhtml) tutorial.

**Wildcard Parameterized Type** - A parameterized type of a generic class or interface, where the argument type represents a group of types, instead of a single type. See examples given in the tutorial.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Archived Tutorials

This chapter contains some outdated tutorial notes and example codes from previous versions of this book.

> [Archived: Downloading and Installing JDK 10](#part0170.xhtml)
> 
> [Archived: JDK 10 Documentation Installation](#part0171.xhtml)
> 
> [Archived: Downloading and Installing JDK 8](#part0172.xhtml)
> 
> [Archived: Downloading and Installing JDK 1.7](#part0173.xhtml)
> 
> [Archived: Downloading and Installing JDK 1.6](#part0174.xhtml)
> 
> [Archived: Downloading and Installing JDK 1.5](#part0175.xhtml)
> 
> [Archived: JDK 1.3 Bug - Memory Leak With Unstarted Threads](#part0176.xhtml)

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: Downloading and Installing JDK 10

This section describes how to download and install JDK 10 on a Windows system.

If you are using Windows systems, you can follow this tutorial to download and install JDK.

*   Open the Java SE Download page with this URL: [http://www.oracle.com/technetwork/java/javase/downloads/](http://www.oracle.com/technetwork/java/javase/downloads/).
*   Click the download button next to "Java Platform (JDK) 10". You will see a new page with a list of different download files of JDK 10.
*   Accept the license agreement.
*   Click the hyper link of "jdk-10.0.1_windows-x64_bin.exe", next to "Windows 390.19 MB".
*   Save jdk-10.0.1_windows-x64_bin.exe to a temporary directory.
*   Double-click on jdk-10.0.1_windows-x64_bin.exe to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

The picture below shows you how the JDK 10 Installation Screen looks like:

![](Images/image00185.jpeg)

JDK 10 Installation Screen

To test the installation, open a command window to try the java command. If you are getting the following output, your installation was ok:

```
 herong> \progra~1\java\jdk-10.0.1\bin\java -version
java version "10.0.1" 2018-04-17
Java(TM) SE Runtime Environment 18.3 (build 10.0.1+10)
Java HotSpot(TM) 64-Bit Server VM 18.3 (build 10.0.1+10, mixed mode)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: JDK 10 Documentation Installation

This section describes how to install JDK Documentation on your own machine.

To learn JDK more effectively, you definitely need to have a copy of the JDK Documentation installed on your own machine. JDK Documentation provides you detailed information of all classes and methods used in JDK. Here is what I did to download and install JDK 10 Documentation on my local machine.

*   Open the Java download home page with this URL: [http://www.oracle.com/technetwork/java/javase/downloads/](http://www.oracle.com/technetwork/java/javase/downloads/).
*   Click the "DOWNLOAD" button next to "Java SE 10 Documentation". You will see "Java SE Development Kit 10 Documentation" page showing up.
*   Check the "Accept License Agreement" radio button.
*   Click the hyper link of "jdk-10.0.1_doc-all.zip".
*   Save the download file "jdk-10.0.1_doc-all.zip" to a temporary directory.
*   Double-click on "jdk-8-apidocs.zip" to extract all files to "C:\Program Files\Java\jdk-10.0.1 directory. The installation of JDK 10 Documentation is done.

To verify the installation, open the "C:\Program Files\Java\jdk-10.0.1\docs\index.html" with a Web browser. You should see the JDK 10 Documentation starting page as shown in this picture:

![](Images/image00186.jpeg)

JDK and Java SE Documentation

Click the "java.logging" module on the JDK 10 Documentation page to see the API documentation of the java.logging module.

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: Downloading and Installing JDK 8

This section describes how to download and install Java SE 8 (JDK 7) on a Windows system.

To learn Java, you need to have a copy of JDK (Java Development Kit) installed on your machine. The current version of JDK is JDK 8, which is also called Java SE (Standard Edition) 8 Here is what I did to download and install JDK 8 on my Windows machine.

*   Open the Java SE Download page with this URL: http://www.oracle.com/technetwork/java/javase/downloads/.
*   Click the download button next to "Java Platform (JDK) 8". You will see a new page with a list of different download files of JDK 8.
*   Locate the "Java SE Development Kit 8" section.
*   Click the hyper link of "jdk-8-windows-i586.exe", next to "Windows x86 - 151.68 MB".
*   Save jdk-8-windows-i586.exe to a temporary directory.
*   Double-click on jdk-8-windows-i586.exe to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

The picture below shows you how the JDK 8 Installation Screen looks like:

![](Images/image00187.jpeg)

JDK 8 Installation Screen

To test the installation, open a command window to try the java command. If you are getting the following output, your installation was ok:

```
 herong> \progra~1\java\jdk1.8.0\bin\java -version
java version "1.8.0"
Java(TM) SE Runtime Environment (build 1.8.0-b132)
Java HotSpot(TM) Client VM (build 25.0-b70, mixed mode, sharing)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: Downloading and Installing JDK 1.7

This section describes how to download and install Java SE 7 Update 7 (JDK 7u7) on a Windows system.

To learn Java, you need to have a copy of JDK (Java Development Kit) installed on your machine. The current version of JDK is JDK 7u7, which is also called Java SE (Standard Edition) 7 Update 7\. Here is what I did to download and install JDK 7u7 on my Windows machine.

*   Open the Java download home page with this URL: http://www.oracle.com/technetwork/java/javase/downloads/.
*   Click the download button next to "Java SE 7u7 - JDK". You will see a new page with a list of different download files of JDK 7u7.
*   Locate the "Java SE Development Kit 7u7" section and click the "Accept License Agreement" radio button.
*   Click on the hyper link of "jdk-7u7-windows-i586.exe" in the "Windows x86 - 88.36 MB" line.
*   Save the download file jdk-7u7-windows-i586.exe to a temporary directory. It may take up to 10 minutes to finish the download.
*   Double-click on the downloaded file jdk-7u7-windows-i586.exe in the temporary directory to start the installation wizard.
*   Follow the installation wizard flow by clicking the "Next" button on each screen. There is no need to change any installation settings.
*   Click the "Close" button on the last screen when the installation is down.

The picture below shows you how the JDK 7 Installation Screen looks like:

![](Images/image00188.jpeg)

JDK 7 Installation Screen

To test the installation, open a command window to try the java command. If you are getting the following output, your installation was ok:

```
 herong> \progra~1\java\jdk1.7.0_07\bin\java -version
java version "1.7.0_07"
Java(TM) SE Runtime Environment (build 1.7.0_07-b11)
Java HotSpot(TM) Client VM (build 23.3-b01, mixed mode, sharing)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: Downloading and Installing JDK 1.6

This section describes how to download and install Java SE (JDK) 1.6 Update 2 on a Windows XP system.

To learn Java, you need to have a copy of JDK (Java Development Kit) installed on your machine. The current version of JDK is JDK 6u2 (Java(TM) SE Development Kit 6 Update 2), which is also called Java SE 6 (Java Standard Edition 6). Here is what I did to download and install JDK 6u2 on my local machine.

*   Open the Java SE Download page with this URL: http://java.sun.com/javase/downloads/.
*   Click the download button next to "JDK 6u2". You will see a new page with a list of different download files of JDK 6u2.
*   Locate the "Windows Platform - Java(TM) SE Development Kit 6 Update 2" section.
*   Click the hyper link of "Windows Offline Installation (build 06), Multi-language", which links to jdk-6u2-windows-i586-p.exe with size of 65.57 MB.
*   Save jdk-6u2-windows-i586-p.exe to a temporary directory.
*   Double-click on jdk-6u2-windows-i586-p.exe to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

To test the installation, open a command window to try the java command. If you are getting the following output, your installation was ok:

```
 C:\>\progra~1\java\jdk1.6.0_02\bin\java -version
java version "1.6.0_02"
Java(TM) SE Runtime Environment (build 1.6.0_02-b06)
Java HotSpot(TM) Client VM (build 1.6.0_02-b06, mixed mode,
sharing)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: Downloading and Installing JDK 1.5

This section describes how to download and install Java SE (JDK) 1.5.0 on a Windows XP system.

1\. Go to http://java.sun.com/javase/downloads/index.jsp

2\. Click the download button in "JDK 5.0 Update 9" section.

3\. Go to the "Windows Platform - J2SE(TM) Development Kit 5.0 Update 9" section, and click "Windows Offline Installation, Multi-language" to download jdk-1_5_0_09-windows-i586-p.exe to a working directory on your hard disk. This file is about 50 MB.

4\. Double click on the downloaded file: jdk-1_5_0_09-windows-i586-p.exe in the working directory in the File Explorer.

5\. Follow the instruction on the installation window to finish the installation.

6\. Open a command window to try the java command. If you are getting the following output, your installation is ok:

```
 >c:
>cd \Program Files\Java\jdk1.5.0_09\bin
>java -version
java version "1.5.0_09"
Java(TM) 2 Runtime Environment, Standard Edition (build 1.5.0_09-b03)
Java HotSpot(TM) Client VM (build 1.5.0_09-b03, mixed mode, sharing)
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0169.xhtml)

∟Archived: JDK 1.3 Bug - Memory Leak With Unstarted Threads

This section describes a reported bug for JDK 1.3 that unstarted thread objects cause memory leak.

There was a bug opened in 2001 for JDK 1.3 titled "Unstarted Thread causes memory leak" See [http://developer.java.sun.com/developer/bugParade/bugs/4410846.html](http://developer.java.sun.com/developer/bugParade/bugs/4410846.html) for details.

The bug report included the following program to show the memory leak:

```
 public class ThreadTest {
    public static void main(String args[]) {
  while (true) {
    try {
        Thread t = new Thread();
    // start thread for memory leak workaround
//        t.start();
    t = null;
        System.gc();
    Thread.sleep(500);
  } catch (InterruptedException ie) {
    ie.printStackTrace();
  }
        }
    }
}
```

I ran this program on my J2SDK 1.4.1 system. As predicted, the memory usage of the JVM went up slowly at a rate of about 4K per 15 seconds.

As I mentioned in previous sections, Thread object created without a specific thread group will be added into the "main" group. So in the ThreadTest program included in the bug report, all the threads created will be added in the "main" group, and will stay there until they are started and ended. If we keep creating new threads, the number of threads in the "main" group will grow, and memory usage will also grow.

But in my opinion, this is not really a bug. JDK is designed to organize all Thread and ThreadGroup objects in a single thread group tree. Application programs are forced to use this structure, and must follow the rules.

However, this designed feature is dangerous if not used properly, as demonstrated by the bug report. It could be a risk for any server type application, if new threads are created for new connection requests and the start() calls are not executed for some reason.

One option to solve this problem is to:

*   At the Thread object creation time, add it to the thread group with a **WeakReference**.
*   At start time (when start() is called), change the WeakReference to a regular reference.

A couple of notes on this option:

*   The weak reference for an unstarted thread will allow the garbage collector to remove the thread, if there is no more regular references to this thread in the application.
*   Replacing the weak reference by a regular reference when a thread is started will prevent the garbage collector to remove this running thread, even if there is no more regular reference to this thread in the application.
*   The implementation of this option could be two separate collections of threads in a thread group: one for unstarted threads with weak references, and the other for started threads with regular references.

Without any help from JDK, finding a simple workaround to prevent this from the application side is not easy.

However, you can put a logic in your application to watch the number of unstarted threads. If this number is growing, you know that somewhere in your application threads are created without the start() calls. Here is the code to calculate the number of unstarted threads:

```
 ThreadGroup g = Thread.currentThread().getThreadGroup();
   while (g.getParent()!=null) g = g.getParent();
   Thread[] l = new Thread[g.activeCount()]];
   int unstartedThreadCount = g.activeCount() - g.enumerate(l,true):
```

[Java Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟References

List of reference materials used in this Java tutorial book.

*   *Java Language and Virtual Machine Specifications*, Oracle, [https://docs.oracle.com/javase/specs/](https://docs.oracle.com/javase/specs/)
*   *The Java Tutorial*, Oracle, [http://docs.oracle.com/javase/tutorial/](http://docs.oracle.com/javase/tutorial/)
*   *IEEE 754 Standards - "float" and "double"*, Herong Yang, [https://www.herongyang.com/C-Sharp/Floating-Point-Data-Type-IEEE-754.html](https://www.herongyang.com/C-Sharp/Floating-Point-Data-Type-IEEE-754.html)

![The Front Cover](Images/cover00189.jpeg)