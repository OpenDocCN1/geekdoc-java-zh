![](Images/cover00210.jpeg)

Java Swing Tutorials

- Herong's Tutorial Examples

![](Images/image00127.jpeg)

v4.31, 2022

Herong Yang

Copyright © 1997-2022 Herong Yang. All rights reserved.

This tutorial book is a collection of notes and sample codes written by the author while he was learning Java Swing and AWT himself. Topics include Swing and AWT (Abstract Windows Toolkit) class library; graphical components: JButton, JCheckbox, JComboBox, JFrame, JLabel, JMenu, JRadioButton, JTextField; frame layouts; menus; dialog boxes; editor pane; Unicode and Chinese. Updated in 2022 (Version v4.31) with JDK 17\. For latest updates and free sample chapters, visit https://www.herongyang.com/Swing.

Table of Contents

> [About This Book](#part0002.xhtml)
> 
> [JDK (Java Development Kit)](#part0003.xhtml)
> 
> [What Is JDK](#part0004.xhtml)
> 
> [Downloading and Installing JDK 15](#part0005.xhtml)
> 
> [Writing My First Java Program](#part0006.xhtml)
> 
> [Adding JDK "bin" Directory to Path Setting](#part0007.xhtml)
> 
> [JDK Documentation Installation](#part0008.xhtml)
> 
> [Introduction of Java Swing Package](#part0009.xhtml)
> 
> [What Is Swing](#part0010.xhtml)
> 
> [SwingHello.java - My First Swing Program](#part0011.xhtml)
> 
> [Graphics Environment of the Local System](#part0012.xhtml)
> 
> [java.awt.GraphicsEnvironment - Graphics Environment Class](#part0013.xhtml)
> 
> [java.awt.Toolkit - AWT Base Class](#part0014.xhtml)
> 
> [Testing Screen Resolution](#part0015.xhtml)
> 
> [JFrame - Main Frame Class](#part0016.xhtml)
> 
> [Creating Frames with Sizes and Locations](#part0017.xhtml)
> 
> [Closing Frame and Terminating Application](#part0018.xhtml)
> 
> [Listing and Interrupting AWT Threads](#part0019.xhtml)
> 
> ["AWT blocker activation interrupted" Error in JDK 1.6](#part0020.xhtml)
> 
> [JFrame Thread Behavior with JDK 8 to 12](#part0021.xhtml)
> 
> [Displaying Chinese Characters in Frame Title](#part0022.xhtml)
> 
> [Drawing Graphics - Using paint() on Frame](#part0023.xhtml)
> 
> [Drawing Graphics - Using paint() on Component](#part0024.xhtml)
> 
> [Drawing Graphics - Using paint() on Content Pane](#part0025.xhtml)
> 
> [Drawing Chinese Characters on Frames](#part0026.xhtml)
> 
> [JLabel - Swing Label Class](#part0027.xhtml)
> 
> [Creating Labels with javax.swing.JLabel Class](#part0028.xhtml)
> 
> [Creating Labels with Chinese Characters](#part0029.xhtml)
> 
> [JButton - Swing Button Class](#part0030.xhtml)
> 
> [Creating Buttons with javax.swing.JButton Class](#part0031.xhtml)
> 
> [Creating Image Buttons with javax.swing.JButton Class](#part0032.xhtml)
> 
> [Button Action Handler at the Component Level](#part0033.xhtml)
> 
> [Button Action Handler at the Frame Level](#part0034.xhtml)
> 
> [Mouse Click Handler at the Frame Level](#part0035.xhtml)
> 
> [JCheckBox - Swing Check Box Class](#part0036.xhtml)
> 
> [javax.swing.JCheckBox and Related Methods](#part0037.xhtml)
> 
> [ActionListener, ChangeListener and ItemListener](#part0038.xhtml)
> 
> [isSelected() - Getting State of Check Box](#part0039.xhtml)
> 
> [JRadioButton - Swing Radio Button Class](#part0040.xhtml)
> 
> [javax.swing.JRadioButton and Related Classes](#part0041.xhtml)
> 
> [ActionListener, ChangeListener and ItemListener](#part0042.xhtml)
> 
> [getSelection() - Getting Selected Button](#part0043.xhtml)
> 
> [JTextField - Swing Text Field Class](#part0044.xhtml)
> 
> [javax.swing.JTextField and Related Classes](#part0045.xhtml)
> 
> [ActionListener and DocumentListener](#part0046.xhtml)
> 
> [JComboBox - Swing Combo Box Class](#part0047.xhtml)
> 
> [javax.swing.JComboBox and Related Methods](#part0048.xhtml)
> 
> [ActionListener and ItemListener](#part0049.xhtml)
> 
> [getSelectedItem() - Selected Item of Combo Box](#part0050.xhtml)
> 
> [setEditable() - Use Combo Box as Text Field](#part0051.xhtml)
> 
> [Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)
> 
> [JMenuBar, JMenu, and JMenuItem Classes](#part0053.xhtml)
> 
> [JMenuBarTest.java - Menu Bar Test Program](#part0054.xhtml)
> 
> [JMenuTest.java - Menu Test Program](#part0055.xhtml)
> 
> [JMenuItemTest.java - Menu Item Test Program](#part0056.xhtml)
> 
> [JRadioButtonMenuItemTest.java - Radio Button Menu Item Test Program](#part0057.xhtml)
> 
> [JCheckBoxMenuItemTest.java - Check Box Menu Item Test Program](#part0058.xhtml)
> 
> [javax.swing.event.MenuListener - Menu Listener Interface](#part0059.xhtml)
> 
> [JMenuItemActionListenerTest.java - Menu Item Action Listener Test](#part0060.xhtml)
> 
> [Item Listener on Radio Button Menu Items](#part0061.xhtml)
> 
> [Item Listener on Check Box Menu Items](#part0062.xhtml)
> 
> [javax.swing.event.MenuKeyListener - Menu Key Listener Interface](#part0063.xhtml)
> 
> [setMnemonic() - Setting Keyboard Mnemonics on Menu Items](#part0064.xhtml)
> 
> [setAccelerator() - Setting Keyboard Accelerators on Menu Items](#part0065.xhtml)
> 
> [setMnemonic() - Setting Keyboard Mnemonics on Menus](#part0066.xhtml)
> 
> [Creating Internal Frames inside the Main Frame](#part0067.xhtml)
> 
> [javax.swing.JInternalFame - Internal Frame Class](#part0068.xhtml)
> 
> [JInternalFameTest.java - Internal Frame Class Test](#part0069.xhtml)
> 
> [javax.swing.InternalFrameListener - Internal Frame Listener Interface](#part0070.xhtml)
> 
> [Layout of Components in a Container](#part0071.xhtml)
> 
> [What Is Layout?](#part0072.xhtml)
> 
> [java.awt.BorderLayout - Border Layout](#part0073.xhtml)
> 
> [java.awt.FlowLayout - Flow Layout](#part0074.xhtml)
> 
> [java.awt.BoxLayout - Box Layout](#part0075.xhtml)
> 
> [java.awt.GridLayout - Grid Layout](#part0076.xhtml)
> 
> [java.awt.GridBagLayout - Grid Bag Layout](#part0077.xhtml)
> 
> [LookAndFeel and UIManager](#part0078.xhtml)
> 
> [Option Dialog Boxes](#part0079.xhtml)
> 
> [javax.swing.JOptionPane - Creating and Displaying Option Dialog Boxes](#part0080.xhtml)
> 
> [showMessageDialog() - Displaying Message Dialog Boxes](#part0081.xhtml)
> 
> [showConfirmDialog() - Displaying Confirmation Dialog Boxes](#part0082.xhtml)
> 
> [Receiving Inputs from Confirmation Dialog Boxes](#part0083.xhtml)
> 
> [showInputDialog() - Displaying Input Dialog Boxes](#part0084.xhtml)
> 
> [showOptionDialog() - Displaying Option Dialog Boxes](#part0085.xhtml)
> 
> [showInternal*Dialog() - Displaying Internal Dialog Boxes](#part0086.xhtml)
> 
> [createDialog() - Creating Dialog Boxes Directly](#part0087.xhtml)
> 
> [JEditorPane - The Editor Pane Class](#part0088.xhtml)
> 
> [Creating a Simple Plain Text Editor Pane](#part0089.xhtml)
> 
> [Saving Text from an Editor Pane](#part0090.xhtml)
> 
> [Editing HTML in an Editor Pane](#part0091.xhtml)
> 
> [Editing Unicode Characters in an Editor Pane](#part0092.xhtml)
> 
> [javax.swing.JFileChooser - File Chooser Dialog Box](#part0093.xhtml)
> 
> [SwingWorker - The Background Task Worker](#part0094.xhtml)
> 
> [What Is SwingWorker Class?](#part0095.xhtml)
> 
> [SwingWorker Example using done() Method](#part0096.xhtml)
> 
> [SwingWorker Example using publish() Method](#part0097.xhtml)
> 
> [SwingWorker Example using "progress" Property](#part0098.xhtml)
> 
> [SwingWorker Example using JProgressBar](#part0099.xhtml)
> 
> [AWT (Abstract Windows Toolkit)](#part0100.xhtml)
> 
> [What Is AWT (Abstract Windows Toolkit)](#part0101.xhtml)
> 
> [HelloAWT.java - My First AWT Program](#part0102.xhtml)
> 
> [Closing AWT Frame and Terminating Application](#part0103.xhtml)
> 
> [Drawing Graphics - Using paint() on Frame or Component](#part0104.xhtml)
> 
> [Creating Labels with java.awt.Label Class](#part0105.xhtml)
> 
> [Creating Buttons with java.awt.Button Class](#part0106.xhtml)
> 
> [AWT Button Action Handler at the Component Level](#part0107.xhtml)
> 
> [AWT Button Action Handler at the Frame Level](#part0108.xhtml)
> 
> [AWT Button Mouse Click Handler at the Frame Level](#part0109.xhtml)
> 
> [AWT TextField and ActionListener](#part0110.xhtml)
> 
> [MenuBarTest.java - AWT Menu Bar Test Program](#part0111.xhtml)
> 
> [MenuTest.java - AWT Menu Test Program](#part0112.xhtml)
> 
> [MenuItemTest.java - AWT Menu Item Test Program](#part0113.xhtml)
> 
> [MenuItemActionListenerTest.java - AWT Menu Item Action Listener](#part0114.xhtml)
> 
> [Integration with Desktop System](#part0115.xhtml)
> 
> [javax.awt.Desktop and Related Methods](#part0116.xhtml)
> 
> [browse() - Launch Default Web Browser](#part0117.xhtml)
> 
> [mail() - Launch Default Email Program](#part0118.xhtml)
> 
> [edit() - Launch Default Editor for Given File](#part0119.xhtml)
> 
> [Archived Tutorials](#part0120.xhtml)
> 
> [Archived: Downloading and Installing JDK 12](#part0121.xhtml)
> 
> [Archived: Downloading and Installing JDK 10](#part0122.xhtml)
> 
> [References](#part0123.xhtml)

**Keywords:** Swing, AWT, Java, Graphics, User Interface

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟About This Book

This section provides some detailed information about this book - Java Swing Tutorials - Herong's Tutorial Examples.

**Title:** Java Swing Tutorials - Herong's Tutorial Examples

**Author:** Herong Yang - Contact by email via herong_yang@yahoo.com.

**Category:** Java & Graphics

**Version/Edition:** v4.31, 2022

**Number of pages:** 265

**Description:** This tutorial book is a collection of notes and sample codes written by the author while he was learning Java Swing and AWT himself. Topics include Swing and AWT (Abstract Windows Toolkit) class library; graphical components: JButton, JCheckbox, JComboBox, JFrame, JLabel, JMenu, JRadioButton, JTextField; frame layouts; menus; dialog boxes; editor pane; Unicode and Chinese. Updated in 2022 (Version v4.31) with JDK 17.

**Keywords:** Swing, AWT, Java, Graphics, User Interface.

**Copyright:**

*   This book is under Copyright © 1997-2022 Herong Yang. All rights reserved.
*   Material in this book may not be published, broadcasted, rewritten or redistributed in any form.
*   The example codes is provided as-is, with no warranty of any kind.

**Revision history:**

*   Version 4.31, 2022\. Updated with JDK 17.
*   Version 4.10, 2014\. Updated with JDK 8.
*   Version 4.00, 2009\. Updated with JDK 6.
*   Version 3.00, 2002\. Updated with JDK 1.4.
*   Version 2.00, 1999\. Added Swing tutorials.
*   Version 1.00, 1997\. Started with AWT tutorials.

**Web version:** [https://www.herongyang.com/Swing](https://www.herongyang.com/Swing) - Provides free sample chapters, latest updates and readers' comments. The Web version of this book has been viewed a total of:

*   1,593,681 times as of December 2021.
*   1,504,792 times as of December 2020.
*   1,428,454 times as of December 2019.
*   1,360,716 times as of December 2018.
*   1,303,085 times as of December 2017.
*   1,237,845 times as of December 2016.
*   1,150,507 times as of December 2015.
*   1,019,129 times as of December 2014.
*   841,839 times as of December 2013.
*   679,173 times as of December 2012.
*   502,432 times as of December 2011.
*   340,928 times as of December 2010.
*   294,916 times as of December 2009.
*   170,832 times as of December 2008.
*   139,491 times as of December 2007.
*   116,463 times as of December 2006.

**PDF/EPUB version:** [https://www.herongyang.com/Swing/PDF-Full-Version.html](https://www.herongyang.com/Swing/PDF-Full-Version.html) - Provides information on how to obtain the full version of this book in PDF, EPUB, or other format.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JDK (Java Development Kit)

This chapter provides tutorial JDK (Java Development Kit). Topics include introduction of JDK; downloading and installing JDK; creating and running a simple Java program.

> [What Is JDK](#part0004.xhtml)
> 
> [Downloading and Installing JDK 15](#part0005.xhtml)
> 
> [Writing My First Java Program](#part0006.xhtml)
> 
> [Adding JDK "bin" Directory to Path Setting](#part0007.xhtml)
> 
> [JDK Documentation Installation](#part0008.xhtml)

Conclusion:

*   JDK (Java Development Kit) - a development environment for building software applications and software components using the Java programming language.
*   JDK is available for free. You can download it from Oracle Website.
*   JDK offers a JRE (Java Runtime Environment), a Java class library, and a set Java tools including a Java compiler.
*   This book provides tutorials on Java Swing and AWT library included in JDK.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK (Java Development Kit)](#part0003.xhtml)

∟What Is JDK

This section describes what is JDK (Java Development Kit) - a development environment for building software applications and software components using the Java programming language.

**What Is JDK (Java Development Kit)**? JDK is short name for Java™ Platform, Standard Edition Development Kit (JDK™), developed and distributed by Oracle. It is a development environment for building software applications and software components using the Java programming language.

JDK includes the following components:

**JRE (Java Runtime Environment)** - JRE allows you to run Java applications. The JRE uses HotSpot as the JVM (Java Virtual Machine) implementing the JVM specification.

See "JVM Tutorials - Herong's Tutorial Examples" book at [herongyang.com/JVM](https://www.herongyang.com/JVM) for more tutorials on JRE.

**JCL (Java Class Library)** - JCL is a set of dynamically loadable libraries that Java applications can call at run time. JCL is organized into Java packages. Some packages are wrappers to access native operating system APIs like java.io.*, java.net.*, java.awt, etc.

Tutorials on JCL are provided in this book.

**Java Development Tools** - Tools includes Java compiler, JAR tool, class file disassembler, debugger, JRE builder, etc.

See "Java Tools Tutorials - Herong's Tutorial Examples" book at [herongyang.com/Java-Tools](https://www.herongyang.com/Java-Tools) for more tutorials on Java tools.

JDK versions and release dates:

```
 JDK (Java SE) 17   September, 2021
JDK (Java SE) 16   March, 2021
JDK (Java SE) 15   September, 2020
JDK (Java SE) 14   March, 2020
JDK (Java SE) 13   September, 2019
JDK (Java SE) 12   March 19, 2019
JDK (Java SE) 11   September, 2018
JDK (Java SE) 10   March 20, 2018
JDK (Java SE) 9    September 21, 2017
JDK (Java SE) 8    March 18, 2014
JDK (Java SE) 7    July 28, 2011
JDK (Java SE) 6    December 2006
JDK (J2SE) 5.0     September 2004
JDK (J2SE) 1.4     February 2002
JDK (J2SE) 1.3     May 2000
JDK (J2SE) 1.2     December 1998
JDK 1.1            February 1997
JDK 1.0            January 1996
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK (Java Development Kit)](#part0003.xhtml)

∟Downloading and Installing JDK 15

This section describes how to download and install JDK 15 on a macOS computer.

JDK 15 is also called Java SE (Standard Edition) 15\. Here is what I did to download and install JDK 15 on my macOS computer.

*   Open the Java SE Download page with this URL: [https://www.oracle.com/technetwork/java/javase/downloads/](https://www.oracle.com/technetwork/java/javase/downloads/).
*   Click "JDK Download" under "Java SE 15". You will see a new page with a list of different download files of "Java SE Development Kit 15 Downloads".
*   Click the hyper link of "jdk-15_osx-x64_bin.dmg", next to "macOS Installer - 179.31 MB".
*   Accept the license agreement and finish the download. The download file jdk-15_osx-x64_bin.dmg will be saved in your ~/Downloads folder.
*   Double-click on jdk-15_osx-x64_bin.dmg to open the installation package.
*   Double-click "JDK 15.pkg" to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

The picture below shows you how the JDK 15 Installation Screen looks like:

![](Images/image00128.jpeg)

JDK 12 Installation Screen

To test the installation, open a command window to try the java command. If you are getting the following output, your installation is good:

```
 herong> java -version 

java version "15" 2020-09-15
Java(TM) SE Runtime Environment (build 15+36-1562)
Java HotSpot(TM) 64-Bit Server VM (build 15+36-1562, mixed mode, sharing)
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK (Java Development Kit)](#part0003.xhtml)

∟Writing My First Java Program

This section provides a tutorial example on how to write, compile, and execute the first Java program with JDK 1.8.0.

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
 herong> javac Hello.java
```

To execute the program, use the java command:

```
 herong> java Hello
Hello world!
```

Congratulations, you have successfully entered, compiled and executed your first Java program.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK (Java Development Kit)](#part0003.xhtml)

∟Adding JDK "bin" Directory to Path Setting

This section provides a tutorial on how to add JDK 'bin' directory to the 'path' system environment variable.

If you are using a Windows computer and want to run Java compiler and JVM by typing their program file name without the directory path name, you may need to update the "path" environment variable on your Windows computer:

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
   C:\WINDOWS\system32;C:\WINDOWS;
   ...
```

Now I should be able to run Java commands without the directory path name:

```
 herong> java -version
java version "17.0.1" 2021-10-19 LTS

herong> javac hello.java

herong> java Hello
Hello world!
```

Now I am ready to play with Java Swing functionalities included in Oracle JDK package!

![](Images/image00129.jpeg)

Adding JDK "bin" Directory to Path Setting

You can also set a new environment variable called "java_home" to avoid typing the full path name to access Java tool program files:

```
 herong> set java_home=C:\Progra~1\java\jdk-17.0.1

herong> %java_home%\bin\java -version
java version "17.0.1" 2021-10-19 LTS
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JDK (Java Development Kit)](#part0003.xhtml)

∟JDK Documentation Installation

This section describes how to install JDK Documentation on your own machine.

To learn JDK more effectively, you definitely need to have a copy of the JDK Documentation installed on your own machine. JDK Documentation provides you detailed information of all classes and methods used in JDK. Here is what I did to download and install JDK 17 Documentation on my local machine.

*   Open the Java download home page with this URL: [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/).
*   Click the "Documentation Download" button near the bottom of the page. You will see "Java SE Development Kit 17 Documentation" page showing up.
*   Click the hyper link of "jdk-17.0.1_doc-all.zip".
*   Save the download file "jdk-17.0.1_doc-all.zip" to a temporary directory.
*   Double-click on "jdk-17.0.1_doc-all.zip" to extract all files to "C:\Program Files\Java\jdk-17.0.1 directory.

To verify the installation, open the "C:\Program Files\Java\jdk-17.0.1\docs\index.html" with a Web browser. You should see the JDK 17 Documentation starting page.

Click the "java.logging" module on the JDK 17 Documentation page to see the API documentation of the java.logging module.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Introduction of Java Swing Package

This chapter provides tutorial notes and example codes on Java Swing package, javax.swing. Topics include quick introduction Java Swing package; first Swing application, SwingHello.java.

> [What Is Swing](#part0010.xhtml)
> 
> [SwingHello.java - My First Swing Program](#part0011.xhtml)

Conclusion:

*   Swing is a Java package, javax.swing, that provides components for graphical user interfaces.
*   The javax.swing.JFrame class allows you to create the main graphical frame.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Introduction of Java Swing Package](#part0009.xhtml)

∟What Is Swing

This section describes what is Java Swing - a JDK class package that implements a set of components for building graphical user interfaces (GUIs) and adding rich graphics functionality and interactivity to Java applications.

**What Is Swing?** Swing is a Java package, javax.swing, provided in J2SDK (Java 2 Software Development Kit). It provides many enhancements to the existing graphics package, AWT (Abstract Windows Toolkit) package, java.awt.

javax.swing and java.awt together offer a complete API (Application Programming Interface) for Java applications to operate graphical devices and create GUI (Graphical User Interfaces).

The JDK documentation offers another description of Swing: "The Swing classes (part of the Java Foundation Classes (JFC) software) implement a set of components for building graphical user interfaces (GUIs) and adding rich graphics functionality and interactivity to Java applications. The Swing components are implemented entirely in the Java programming language. The pluggable look and feel lets you create GUIs that can either look the same across platforms or can assume the look and feel of the current OS platform (such as Microsoft Windows, Solaris or Linux)."

The Swing package contains following subpackages:

*   javax.swing - Provides a set of "lightweight" (written in Java with no native code) components that, to the maximum degree possible, work the same on all platforms.
*   javax.swing.border - Provides classes and interfaces for drawing specialized borders around a Swing component.
*   javax.swing.colorchooser - Contains classes and interfaces used by the JColorChooser component.
*   javax.swing.event - Provides support for events fired by Swing components.
*   javax.swing.filechooser - Contains classes and interfaces used by the JFileChooser component.
*   javax.swing.plaf - Provides one interface and many abstract classes that Swing uses to provide its pluggable look and feel capabilities.
*   javax.swing.plaf.basic - Provides user interface objects built according to the Basic look and feel.
*   javax.swing.plaf.metal - Provides user interface objects built according to the Java look and feel (once codenamed Metal), which is the default look and feel.
*   javax.swing.plaf.multi - Provides user interface objects that combine two or more look and feels.
*   javax.swing.plaf.synth - Provides user interface objects for a skinnable look and feel in which all painting is delegated.
*   javax.swing.table - Provides classes and interfaces for dealing with JTable.
*   javax.swing.text - Provides classes and interfaces that deal with editable and non-editable text components.
*   javax.swing.text.html - Provides the class HTMLEditorKit and supporting classes for creating HTML text editors.
*   javax.swing.text.html.parser - Provides the default HTML parser, along with support classes.
*   javax.swing.text.rtf - Provides a class (RTFEditorKit) for creating Rich Text Format text editors.
*   javax.swing.tree - Provides classes and interfaces for dealing with JTree.
*   javax.swing.undo - Allows developers to provide support for undo/redo in applications such as text editors.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Introduction of Java Swing Package](#part0009.xhtml)

∟SwingHello.java - My First Swing Program

This section provides a tutorial example on how to a simple Java Swing program. SwingHello.java is my first Swing program that displays a blank window with 'Hello world!' in the window title bar.

Below is my first Swing program, SwingHello.java:

```
 import javax.swing.*;
public class SwingHello {
   public static void main(String[] a) {
      JFrame f = new JFrame("Hello world!");
      f.setVisible(true);
   }
}
```

If you have JDK installed on your system, you can compile and run this program in a command window:

```
 herong> javac SwingHello.java
herong> java SwingHello
```

Once the program is running, you will see a small new window showing up on your screen. If use the mouse pointer to drag its edges to make it larger, you can see the hello text in the title area as shown in this picture:

![](Images/image00130.jpeg)

First Swing (on Windows) - Hello World!

The new window will stay on your screen until you press Ctrl-C in the command window to terminate the running program.

If you are using a macOS computer, the Java Swing window will look differently:

![](Images/image00131.jpeg)

First Swing (on macOS) - Hello World!

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Graphics Environment of the Local System

This chapter provides tutorial notes and example codes on local graphics environment. Topics include java.awt.GraphicsEnvironment class description and example; java.awt.Toolkit class description and example; calculating screen resolution with the default Toolkit object.

> [java.awt.GraphicsEnvironment - Graphics Environment Class](#part0013.xhtml)
> 
> [java.awt.Toolkit - AWT Base Class](#part0014.xhtml)
> 
> [Testing Screen Resolution](#part0015.xhtml)

Conclusion:

*   java.awt.GraphicsEnvironment.getLocalGraphicsEnvironment() returns the local graphics environment object.
*   java.awt.Toolkit.getDefaultToolkit() returns the default Toolkit object.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Graphics Environment of the Local System](#part0012.xhtml)

∟java.awt.GraphicsEnvironment - Graphics Environment Class

This section describes java.awt.GraphicsEnvironment - Graphics Environment Class. You can use this class to get a lot of information about your local graphics device, which is really your computer screen.

java.awt.GraphicsEnvironment is an AWT class representing graphics environment that are accessible by the local operating system. This class also offers a static method, getLocalGraphicsEnvironment(), to return an object representing the local default graphics environment.

You can use this local graphics environment object to get a lot of information about your local system. For example, you can find out what text fonts are available, and what is maximum size of the graphical drawing area on the screen.

To show you how to use the getLocalGraphicsEnvironment() method, I wrote the following sample program:

```
 /* LocalGraphicsEnvironment.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
public class LocalGraphicsEnvironment {
   public static void main(String[] a) {
      GraphicsEnvironment e 
         = GraphicsEnvironment.getLocalGraphicsEnvironment();
      String n[] = e.getAvailableFontFamilyNames();
      System.out.println("Font families:");
      for (int i=0; i<n.length; i++) {
         System.out.println("   "+n[i]);
      }
      Point p = e.getCenterPoint();
      System.out.println("Window center point: "+p.x+", "+p.y);
      Rectangle r = e.getMaximumWindowBounds();
      System.out.println("Maximum window bounds: "+r.x+", "+r.y
         +", "+r.width+", "+r.height);
      GraphicsDevice g = e.getDefaultScreenDevice();
      System.out.println("Device ID: "+g.getIDstring());
   }
}
```

Output:

```
 herong> java LocalGraphicsEnvironment.java

Font families:
   Albertus Extra Bold
   Albertus Medium
   Antique Olive
   Arial
   Arial Black
   Arial Narrow
   ......
Window center point: 512, 296
Maximum window bounds: 0, 0, 1024, 592
Device ID: \Display0
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Graphics Environment of the Local System](#part0012.xhtml)

∟java.awt.Toolkit - AWT Base Class

This section provides a tutorial example on how to use java.awt.Toolkit class to obtain the default Toolkit object, which also can provide information about the default graphics environment, the local screen.

java.awt.Toolkit is an AWT class acting as a base class for all implementations of AWT. This class also offers a static method, getDetaulToolkit(), to return a Toolkit object representing the default implementation of AWT.

You can use this default toolkit object to get information of the default graphics device, the local screen. For example, you can find out the size and resolution of the local screen.

To show you how to use the getDefaultToolkit() method, I wrote the following sample program:

```
 /* DefaultToolkit.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
public class DefaultToolkit {
   public static void main(String[] a) {
      Toolkit t = Toolkit.getDefaultToolkit();
      Dimension d = t.getScreenSize();
      System.out.println("Screen size: "+d.width+", "+d.height);
      System.out.println("Screen resolution: "+t.getScreenResolution());
   }
}
```

Output:

```
 herong> java DefaultToolkit.java 

Screen size: 1024, 640
Screen resolution: 120
```

Comparing the output of DefaultToolkit.java with LocalGraphicsEnvironment.java, the toolkit screen size doesn't match the environment window bounds. I don't know why. I also don't know how to read the screen resolution value. Is it 120 DPI (Dots Per Inch)?

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Graphics Environment of the Local System](#part0012.xhtml)

∟Testing Screen Resolution

This section provides a tutorial example on how to test the graphics resolution of the local screen using the default Toolkit object returned by the Toolkit.getDefaultToolkit() static method.

To answer my question raised in the previous section, I wrote the following program and did some tests:

```
 /* ScreenResolution.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class ScreenResolution {
   static int dpi;
   static int width, height;
   public static void main(String[] a) {
      Toolkit t = Toolkit.getDefaultToolkit();
      dpi = t.getScreenResolution();
      width = t.getScreenSize().width;
      height = t.getScreenSize().height;
      System.out.println("Width = "+width);
      System.out.println("Height = "+height);
      System.out.println("DPI = "+dpi);
      JFrame f = new JFrame("Screen Size and Resolution");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setContentPane(new MyComponent());
      f.setExtendedState(Frame.MAXIMIZED_BOTH);
      f.setVisible(true);
   }
   static class MyComponent extends JComponent {
      public void paint(Graphics g) {
         g.drawString("100 pixel boxes",0,20);
         for (int i=0; i<width/100+1; i++) {
            g.drawRect(i*100,20,100,100);
         }
         g.drawString("One inch ("+dpi+" pixel) boxes",0,140);
         for (int i=0; i<width/dpi+1; i++) {
            g.drawRect(i*dpi,140,dpi,dpi);
         }
      }
   }
}
```

For the first test, I changed my Windows screen setting (Control Panel / Display / Settings / Screen Area) to 1024 x 786, and executed my program. It shows about 10.* 100-pixel boxes and 10.* one-inch boxes:

![](Images/image00132.jpeg)

Screen Resolution

The example program also gives me the following numbers in the console window:

```
 Width = 1024
Height = 768
DPI = 96
```

For the second test, I changed my Windows screen setting (Control Panel / Display / Settings / Screen Area) to 800 x 600, and executed my program. It shows about 8 100-pixel boxes and 8.* one-inch boxes, and gave me the following in the console window:

```
 Width = 800
Height = 600
DPI = 96
```

So the result tells me that the size of my one-inch boxes is not really one inch, if you measure them on the screen. The screen resolution I got from the default toolkit is not following the screen setting. In other words, I am not getting the real resolution of my screen. If anyone knows how to get the real resolution, please tell me.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JFrame - Main Frame Class

This chapter provides tutorial notes and example codes on JFrame class. Topics include creating frames with sizes and locations; terminating program with its frame is closed; Listing AWT threads; displaying Chinese character on frames; drawing graphics on frames.

> [Creating Frames with Sizes and Locations](#part0017.xhtml)
> 
> [Closing Frame and Terminating Application](#part0018.xhtml)
> 
> [Listing and Interrupting AWT Threads](#part0019.xhtml)
> 
> ["AWT blocker activation interrupted" Error in JDK 1.6](#part0020.xhtml)
> 
> [JFrame Thread Behavior with JDK 8 to 12](#part0021.xhtml)
> 
> [Displaying Chinese Characters in Frame Title](#part0022.xhtml)
> 
> [Drawing Graphics - Using paint() on Frame](#part0023.xhtml)
> 
> [Drawing Graphics - Using paint() on Component](#part0024.xhtml)
> 
> [Drawing Graphics - Using paint() on Content Pane](#part0025.xhtml)
> 
> [Drawing Chinese Characters on Frames](#part0026.xhtml)

Conclusion:

*   JFrame.setVisible() starts AWT threads and displays the frame on the screen.
*   JFrame.setDefaultCloseOperation() can be used to terminate the program when its frames are closed.
*   JFrame.setContentPane() can be used to replace the content pane with your own components.
*   The best way to draw graphics on a frame is to draw graphics on its content pane component.
*   JComponent.setFont() can be use to set Chinese fonts and draw Chinese characters.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Creating Frames with Sizes and Locations

This section provides a tutorial example on how to create a frame with a given size and a given location with setBounds() and setVisible() methods.

**Problem**: I want to create a frame window with a specific size and display it on the screen at a specific location.

**Solution**: You can use the JFrame.setBounds() method define the frame location and size. Then use the setVisible() method to make the frame visible on the screen. The following sample code, JFrameTest.java, shows you how to do this.

```
 import javax.swing.*;
public class JFrameTest {
   public static void main(String[] a) {
      JFrame f = new JFrame("Frame Title");
      f.setBounds(50,50,150,150);
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00133.jpeg)

JFrame Test

Note 1: The size specified in the setBounds() method includes both the content area and the title area of the frame.

Note 2: After executing the f.setVisible(true) statement, the main() method reaches the end of execution. But the execution of the entire program is not terminated. This is due the fact that the f.setVisible(true) statement actually launches new execution threads, AWT threads. Those threads are still running even after the main thread reaches the end.

Note 3: When you click the close icon, the frame will be removed from the screen. But the execution of the entire program is not terminated. Removing all frames from the screen does not force all AWT threads to end.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Closing Frame and Terminating Application

This section provides 3 solutions and sample programs on how to close the main frame and terminate the application.

**Problem**: I have a frame window displayed on the screen and I want to close the frame and terminate the application, when user invokes the close command from the window's system menu, or clicks on the close icon from the window's system icon list.

**Solution 1**: You can use the JFrame.setDefaultCloseOperation() method to change the default behavior option of JFrame responding to the window closing event. Select the EXIT_ON_CLOSE option will terminate the application immediately. Of course, when the application is terminated, all frames will be closed automatically. The following sample code, JFrameClose1.java, shows you how to do this.

```
 /* JFrameClose1.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
public class JFrameClose1 {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setTitle("Closing Frame with Default Close Operation");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setVisible(true);
   }
}
```

**Solution 2**: You can extend JFrame class to have your own frame class, so that you can override the default processWindowEvent() method to terminate the application. Of course, calling System.exit(0) is the quickest way to terminate an application. The following sample code, JFrameClose2.java, shows you how to do this.

```
 /* JFrameClose2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
public class JFrameClose2  {
   public static void main(String[] a) {
      MyJFrame f = new MyJFrame();
      f.setTitle("Closing Frame with Process Window Event");
      f.setBounds(100,50,500,300);
      f.setVisible(true);
   }
   static class MyJFrame extends JFrame {
      protected void processWindowEvent(WindowEvent e) {
         if (e.getID() == WindowEvent.WINDOW_CLOSING) {
            System.exit(0);
         }
      }
   }
}
```

**Solution 3**: You can create a new window event listener class and add an object of this listener class to the JFrame object. In the new window event listener, you can implement your owner version of windowClosing() handler method. Of course, the quickest way to create a new window event listener class is to extend the WindowAdapter class. The following sample code, JFrameClose3.java, shows you how to do this.

```
 /* JFrameClose3.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
public class JFrameClose3  {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setTitle("Closing Frame with Window Listener");
      f.setBounds(100,50,500,300);
      f.addWindowListener(new MyWindowListener());
      f.setVisible(true);
   }
   static class MyWindowListener extends WindowAdapter {
      public void windowClosing(WindowEvent e) {
         System.exit(0);
      }
   }
}
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Listing and Interrupting AWT Threads

This section provides a tutorial example on how to list AWT threads and how to interrupt AWT threads with the interrupt() method.

**Problem**: I want to know how many threads are created by the Swing package and the AWT package. And what will happen if I send the interrupt signal to all of them.

**Solution**: This is easy. Just get the list of all threads of the current thread group, and interrupt them one by one. Here is a sample program to show you how to do this:

```
 /* FrameThreads.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class FrameThreads {
   public static void main(String[] a) {
      JFrame f = new JFrame("Frame 1");
      f.setBounds(0,0,100,100);
      f.setVisible(true);
      f = new JFrame("Frame 2");
      f.setBounds(50,50,100,100);
      f.setVisible(true);
      f = new JFrame("Frame 3");
      f.setBounds(100,100,100,100);
      f.setVisible(true);
      Thread[] l = new Thread[100];
      int n = Thread.enumerate(l);
      Thread g = null;
      for (int i=0; i<n; i++) {
         System.out.println("Active thread = "+l[i].getName());
      }
      Thread t = Thread.currentThread();
      for (int i=0; i<n; i++) {
         try {
            Thread.sleep(1000*30);
         } catch (Exception e) {
            System.out.println("Interrupted.");
         }
         if (t != l[i]) {
            System.out.println("Interrupting thread = "
               +l[i].getName());
            l[i].interrupt();
         }
      }
   }
}
```

If you run this program with JDK 1.5 or older, you will see 3 frame windows showing up on the screen. After every 30 seconds, my program will send an interrupt signal to each thread. When the interrupt signal reaches the "Java2D Disposer" thread, a run-time exception occurs forcing the application to terminate. The following list shows you the output of my program:

```
 herong> \Progra~1\Java\jdk1.5.0_09\bin\java FrameThreads

Active thread = main
Active thread = AWT-Windows
Active thread = AWT-Shutdown
Active thread = AWT-EventQueue-0
Active thread = Java2D Disposer
Interrupting thread = AWT-Windows
Interrupting thread = AWT-Shutdown
Interrupting thread = AWT-EventQueue-0
Interrupting thread = Java2D Disposer
Exception while removing reference: java.lang.InterruptedException
java.lang.InterruptedException
   at java.lang.Object.wait(Native Method)
   at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:111)
   at java.lang.ref.ReferenceQueue.remove(ReferenceQueue.java:127)
   at sun.java2d.Disposer.run(Disposer.java:100)
   at java.lang.Thread.run(Thread.java:534)
AWT blocker activation interrupted:
java.lang.InterruptedException
   at java.lang.Object.wait(Native Method)
   at java.lang.Object.wait(Object.java:429)
   at sun.awt.AWTAutoShutdown.activateBlockerThread(AWTAutoShut...
   at sun.awt.AWTAutoShutdown.setToolkitBusy(AWTAutoShutdown.ja...
   at sun.awt.AWTAutoShutdown.notifyToolkitThreadBusy(AWTAutoSh...
   at sun.awt.windows.WToolkit.eventLoop(Native Method)
   at sun.awt.windows.WToolkit.run(WToolkit.java:262)
   at java.lang.Thread.run(Thread.java:534)
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟"AWT blocker activation interrupted" Error in JDK 1.6

This section provides a tutorial example on the condition for the 'AWT blocker activation interrupted' error in JDK 1.6.0.

When I ran the same test program, FrameThreads.java, listed in the previous tutorial with JDK 1.6 or JDK 1.7, I got some interesting results.

Test 1 - Run FrameThreads.java in a command window and wait:

```
 herong> \progra~1\java\jdk1.6.0_02\bin\java FrameThreads

Active thread = main
Active thread = AWT-Shutdown
Active thread = AWT-Windows
Active thread = AWT-EventQueue-0
Interrupting thread = AWT-Shutdown
Interrupting thread = AWT-Windows
Interrupting thread = AWT-EventQueue-0
```

All three AWT threads are terminated. But 3 frame windows are still displayed on the screen forever. That means the run-time exception issue is fixed now.

Noticed that the "Java2D Disposer" thread is not there anymore in JDK 1.6.0\. But if you check the parent thread group, the "system" thread group, you will see the "Java2D Disposer" thread. In other words, the "Java2D Disposer" thread is moved from the "main" thread group to its parent, the "system" thread group.

Test 2 - Run FrameThreads.java in a command window and run Internet Explorer in full screen to hide those 3 frame windows. About 3 minutes later, all 3 frame windows are terminated. The console window shows:

```
 herong> \progra~1\java\jdk1.6.0_02\bin\java FrameThreads

Active thread = main
Active thread = AWT-Shutdown
Active thread = AWT-Windows
Active thread = AWT-EventQueue-0
Interrupting thread = AWT-Shutdown
Interrupting thread = AWT-Windows
Interrupting thread = AWT-EventQueue-0
AWT blocker activation interrupted:
java.lang.InterruptedException
   at java.lang.Object.wait(Native Method)
   at java.lang.Object.wait(Object.java:485)
   at sun.awt.AWTAutoShutdown.activateBlockerThread(AWTAutoShutdow...
   at sun.awt.AWTAutoShutdown.setToolkitBusy(AWTAutoShutdown.java:...
   at sun.awt.AWTAutoShutdown.notifyToolkitThreadBusy(AWTAutoShutd...
   at sun.awt.windows.WToolkit.eventLoop(Native Method)
   at sun.awt.windows.WToolkit.run(WToolkit.java:290)
   at java.lang.Thread.run(Thread.java:619)
```

This tells me that the AWT package in JDK 1.6 is still having some issues if its threads are interrupted. So do not interrupt AWT threads.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟JFrame Thread Behavior with JDK 8 to 12

This section provides a tutorial example on JFrame Thread behavior with JDK 1.8 to JDK 12.

I also tested the same program in JDK 8 to JDK 15\. The result is different:

Test 1 - Run FrameThreads.java with JDK 15 in a command window and wait:

```
 herong> java -version 
java version "15" 2020-09-15
Java(TM) SE Runtime Environment (build 15+36-1562)
Java HotSpot(TM) 64-Bit Server VM (build 15+36-1562, mixed mode, sharing)

herong> java FrameThreads.java
Active thread = main
Active thread = AWT-EventQueue-0
Interrupting thread = AWT-EventQueue-0
```

Noticed that the "AWT-Shutdown" and "AWT-Windows" threads are not there anymore. They are probably moved to the "system" thread group now from the "main" thread group. The interruption did sent to the AWT-EventQueue-0 threat. But the 3 Swing frames were displayed on the screen forever.

Test 2 - Run FrameThreads.java in a command window, hide 3 frames behind another window and wait. I got the same results as test 1.

This tells me that AWT packages in JDK 1.8 to JDK 15 are still having some issues if its threads are interrupted. But it behaves consistently now.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Displaying Chinese Characters in Frame Title

This section provides a tutorial example on how to display Chinese characters in the title bar of a frame window with a given Chinese font.

**Problem**: I want to display Chinese characters in the title of a frame window.

**Solution 1**: If you are using JDK 9 or higher on newer computers, you can include Chinese characters in your Java source code and save it in UTF-8 encoding, which is the default behavior of most programming editors. There is no need to specify the "SimSun" font name. The system will will pick up the default font to support Chinese characters. Chinese characters can still be provided in Unicode /uxxxx ASCII format. But UTF-8 encoding is a much better option.

```
 /* JFrameChinese2.java
 * Copyright (c) 2014-2018 HerongYang.com All Rights Reserved.
*/
import java.awt.*;
import javax.swing.*;
public class JFrameChinese2 {
   public static void main(String[] a) {
      JFrame f = new JFrame();
//    f.setFont(new Font("SimSun",Font.PLAIN, 12));
//    f.setTitle("Hello world! - \u7535\u8111\u4F60\u597D\uFF01");
      f.setTitle("Hello world! - 电脑你好！");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setVisible(true);
   }
}
```

**Solution 2**: If you are still using an older version of JDK on an older computer, you may have to install Chinese fonts yourself. In my sample code listed below, I am using font SimSun, which was installed as part of the Windows multi-language support. You may also have to enter Chinese characters in Java source code in /uxxxx ASCII format.

```
 /* JFrameChinese.java
 * Copyright (c) 2014-2018 HerongYang.com All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JFrameChinese {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setFont(new Font("SimSun",Font.PLAIN, 12));
      f.setTitle("Hello world! - \u7535\u8111\u4F60\u597D\uFF01");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setVisible(true);
   }
}
```

If you run both examples, you will get the same result:

![](Images/image00134.jpeg)

Chinese Characters in Title Bar

Note 1: With JDK 1.4.1 or lower, the characters are displayed as "?". I don't any way to fix it. If you have any suggestions, please share them with me.

Note 2: To check if you have SimSun font installed or not on your Windows computer, you can look for %windir%\fonts\simsun.ttc file in your system directory tree.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Drawing Graphics - Using paint() on Frame

This section provides a tutorial example on how to override the paint() method in the javax.swing.JFrame class to draw graphics (a rectangle) on the frame window. This solution is not recommended.

**Problem**: I want to draw some graphics in a frame.

**Solution 1**: You can do this very easily by extending JFrame class to create your own frame class so that you can override the paint() method. The paint() method provides you a Graphics object, which will give you utility methods to draw various types of graphics. The following sample code, JFramePaint1.java, shows you how to do this.

```
 /* JFramePaint1.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JFramePaint1 {
   public static void main(String[] a) {
      MyJFrame f = new MyJFrame();
      f.setTitle("Drawing Graphics in Frames");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setVisible(true);
   }
   static class MyJFrame extends JFrame {
      public void paint(Graphics g) {
         g.drawRect(20,10,100,60);
      }
   }
}
```

If you run this example, you will get:

![](Images/image00135.jpeg)

Using paint() on Frame

Note 1: The paint() method is inherited by JFrame class from the Component class. It will be called whenever this component should be painted.

Note 2: If you look at the rectangle displayed on the frame, you will see that the origin of the drawing coordinates is located at the top left corner of the entire frame, including the title bar.

Note 3: By default, the paint() method provides transparent background, in JDK 1.4, 1.5 and 1.6\. This is why you see a Web page showing up in the picture.

Note 4: In JDK 7 and higher, the paint() method does not provides transparent background.

This solution is not recommended. We don't want to draw graphics in the frame bar area.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Drawing Graphics - Using paint() on Component

This section provides a tutorial example on how to override the paint() method in the javax.swing.Component class to draw graphics (a rectangle) and add the component to the content pane of the frame window.

**Problem**: I want to draw some graphics in a frame.

**Solution 2**: Obviously, solution 1 is not so ideal, because we are drawing on the UI element of the frame itself. To draw graphics only in the content area of the frame, we can create a new component with its own paint() method and add it to the content pane of the frame. The following sample code, JFramePaint2.java, shows you how to do this.

```
 /* JFramePaint2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JFramePaint2 {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setTitle("Drawing Graphics in a Frame"
         +" by Adding a Component");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.getContentPane().add(new MyComponent());
      f.setVisible(true);
   }
   static class MyComponent extends JComponent {
    b  public void paint(Graphics g) {
         g.drawRect(20,10,100,60);
      }
   }
}
```

If you run this example, you will get:

![](Images/image00136.jpeg)

Using paint() on Component

Note 1: Since no size and location is given to the new added component, it takes the entire area of the content pane, which is the entire area of the frame without the title bar area.

Note 2: Now the origin of the drawing coordinates is at the top left corner of the content pane, much better than solution 1.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Drawing Graphics - Using paint() on Content Pane

This section provides a tutorial example on how to override the paint() method in the javax.swing.Component class to draw graphics (a rectangle) and use it as the content pane of the frame window.

**Problem**: I want to draw some graphics in a frame.

**Solution 3**: Solution 2 is still not so perfect. Why do we need to add another component for the drawing? Can we draw graphics directly on the content pane? The answer is yes, we can draw directly on the content pane. The following sample code, JFramePaint3.java, shows you how to do this.

```
 /* JFramePaint3.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JFramePaint3 {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setTitle("Drawing Graphics in a Frame"
         +" by Replacing the Content Pane");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setContentPane(new MyComponent());
      f.setVisible(true);
   }
   static class MyComponent extends JComponent {
      public void paint(Graphics g) {
         g.drawRect(20,10,100,60);
      }
   }
}
```

If you run this example, you will get:

![](Images/image00137.jpeg)

Using paint() on Content Pane

Note: The content pane is replaced by a new component object we created with our own the paint() method.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JFrame - Main Frame Class](#part0016.xhtml)

∟Drawing Chinese Characters on Frames

This section provides a tutorial example on how to draw Chinese characters on frame using the drawString() method with a Chinese font selected.

**Problem**: I want to draw some Chinese characters in a frame.

**Solution**: You can do in the same way as described in the solution of the previous question. In the paint() method, first change the font of the Graphics object to a Unicode font that supports Chinese characters. Then use drawString() utility method to draw the string with Chinese characters. The following sample code, JFramePaintChinese.java, shows you how to do this.

```
 /* JFramePaintChinese.java
 * Copyright (c) 2014-2018 HerongYang.com All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JFramePaintChinese {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setTitle("Drawing Graphics in Frames");
      f.setBounds(100,50,500,300);
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setContentPane(new MyComponent());
      f.setVisible(true);
   }
   static class MyComponent extends JComponent {
      public void paint(Graphics g) {
         g.setFont(new Font("SimSun",Font.PLAIN, 12));
         g.drawString("Hello world! - \u7535\u8111\u4F60\u597D\uFF01",
            100,50);
      }
   }
}
```

If you run this example, you will get:

![](Images/image00138.jpeg)

Draw Chinese on Frame

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JLabel - Swing Label Class

This chapter provides tutorial notes and example codes on JLabel class. Topics include creating label components with the javax.swing.JLabel class; creating labels with Chinese characters.

> [Creating Labels with javax.swing.JLabel Class](#part0028.xhtml)
> 
> [Creating Labels with Chinese Characters](#part0029.xhtml)

Conclusions:

*   javax.swing.JLabel class represents a UI label.
*   A label can have Unicode characters of any language as long as there is font file to support it.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JLabel - Swing Label Class](#part0027.xhtml)

∟Creating Labels with javax.swing.JLabel Class

This section provides a tutorial example on how to create a label with the javax.swing.JLabel class.

**Problem**: I want to create a label with a text string.

**Solution**: This is easy, just instantiate an object of javax.swing.JLabel, and add it to any container. Here is a sample program to show you how to do this:

```
 /* JLabelHello.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JLabelHello {
   public static void main(String[] a) {
      JFrame f = new JFrame();
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      JLabel l = new JLabel("Hello world!");
      f.getContentPane().add(l);
      f.pack();      
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00139.jpeg)

JLabel Test

Note: The pack() method causes the window to resize to fit the preferred size and layouts of its subcomponents.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JLabel - Swing Label Class](#part0027.xhtml)

∟Creating Labels with Chinese Characters

This section provides a tutorial example on how to create a label with Chinese characters with the javax.swing.JLabel class.

**Problem**: I want to create a label with Chinese characters.

**Solution**: Not very hard to do. See the following sample program:

```
 /* JLabelChinese.java
 * Copyright (c) 2014-2018 HerongYang.com All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JLabelChinese {
   public static void main(String[] a) {
      JLabel l = new JLabel();
      l.setFont(new Font("SimSun",Font.PLAIN, 12));
      l.setText("Hello world! - \u7535\u8111\u4F60\u597D\uFF01");
      JFrame f = new JFrame();
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.getContentPane().add(l);
      f.pack();
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00140.jpeg)

JLabel Test in Chinese

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JButton - Swing Button Class

This chapter provides tutorial notes and example codes on JButton class. Topics include creating button components with the javax.swing.JButton class; creating buttons with image icons; adding button action handler at the component level and the frame level; adding mouse click handler to handle button actions.

> [Creating Buttons with javax.swing.JButton Class](#part0031.xhtml)
> 
> [Creating Image Buttons with javax.swing.JButton Class](#part0032.xhtml)
> 
> [Button Action Handler at the Component Level](#part0033.xhtml)
> 
> [Button Action Handler at the Frame Level](#part0034.xhtml)
> 
> [Mouse Click Handler at the Frame Level](#part0035.xhtml)

Conclusions:

*   javax.swing.JButton class represents a UI action button.
*   An action button can be created with a text label or an image icon.
*   ActionListener interface can be used to handle the user action on the button.
*   MouseAdapter interface can be used to handle user mouse clicks on the button.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JButton - Swing Button Class](#part0030.xhtml)

∟Creating Buttons with javax.swing.JButton Class

This section provides a tutorial example on how to create a button with the javax.swing.JButton class.

Buttons are so easy to create with the javax.swing.JButton class. Here is a sample program:

```
 /* JButtonOk.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JButtonOk {
   public static void main(String[] a) {
      JFrame f = new JFrame("My First Button");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      JButton b = new JButton("OK");
      f.getContentPane().add(b);
      f.pack();      
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00141.jpeg)

JButton Test Button

Note: Clicking the OK button will trigger no actions, because no event listeners are added to the button component.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JButton - Swing Button Class](#part0030.xhtml)

∟Creating Image Buttons with javax.swing.JButton Class

This section provides a tutorial example on how to create an image button with the JButton class and the ImageIcon class.

You can also create a button with your own image. Here is a sample program:

```
 /* JButtonIcon.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JButtonIcon {
   public static void main(String[] a) {
      JFrame f = new JFrame("My Icon Button");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      JButton b = new JButton(new ImageIcon("java.gif"));
      f.getContentPane().add(b);
      f.pack();      
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00142.jpeg)

JLabel Image Icon Button

Note: The ImageIcon class is used to create a button with an image.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JButton - Swing Button Class](#part0030.xhtml)

∟Button Action Handler at the Component Level

This section provides a tutorial example on how to create a button to handle actions by adding the ActionListener interface to the button component.

One way to handle button actions is to add an action listener to the button object. An action listener is an object of any class that implements the ActionListener interface.

The following program shows you how to extend the JButton class to implement the ActionListener class:

```
 /* JButtonAction1.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JButtonAction1 {
   public static void main(String[] a) {
      JFrame f = new JFrame("My Switch Button");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      JButton b = new MyButton();
      f.getContentPane().add(b);
      f.pack();
      f.setVisible(true);
   }
   private static class MyButton extends JButton 
      implements ActionListener {
       String text = "On";
       public MyButton() {
          super();
          setText(text);
          addActionListener(this);
       }
       public void actionPerformed(ActionEvent e) {
          if (text.equals("On")) text = "Off";
          else text = "On"; 
          setText(text);
       }
   }
}
```

If you run this example, you will get:

![](Images/image00143.jpeg)

JButton Button Action Handler at Component

The button works well. If you click the button, the button label text will change from "On" to "Off"; and from "Off" to "On", if you click it again.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JButton - Swing Button Class](#part0030.xhtml)

∟Button Action Handler at the Frame Level

This section provides a tutorial example on how to create a button to handle actions by adding the ActionListener interface to the frame that contains the button component.

In the previous section, we extended the button to handle its own action. That works fine, if the action only requires modifying the behavior of the same button.

But if the action requires modifying the behavior of other components, you need to implement the action listener as a higher level. The following program shows you how to use the action handler to modify the text of a label component:

```
 /* JButtonAction2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JButtonAction2 implements ActionListener {
   JButton myButton = null;
   JLabel myLabel = null;
   String text = null;
   public static void main(String[] a) {
      JButtonAction2 myTest = new JButtonAction2();
      myTest.createFrame();
   }
   public void createFrame() {
      JFrame f = new JFrame("My Switch Button");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container c = f.getContentPane();
      c.setLayout(new GridLayout(2,1));
      text = "On";
      myButton = new JButton(text);
      myButton.addActionListener(this);
      c.add(myButton);
      myLabel = new JLabel(text,SwingConstants.CENTER);
      c.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      if (text.equals("On")) text = "Off";
      else text = "On"; 
      myButton.setText(text);
      myLabel.setText(text);
   }
}
```

If you run this example, you will get:

![](Images/image00144.jpeg)

JButton Button Action Handler at Frame

The button works nicely. If you click the button, the button label text will change from "On" to "Off", and the text of the label component will also change.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JButton - Swing Button Class](#part0030.xhtml)

∟Mouse Click Handler at the Frame Level

This section provides a tutorial example on how to create a button to handle actions by adding the MouseAdapter interface to the frame that contains the button component.

Of course, using ActionListeners is not the only way to handle user clicks on buttons. You can also use MouseListeners to handle user clicks. Here is an example program:

```
 /* JButtonAction3.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JButtonAction3 extends MouseAdapter {
   JButton myButton = null;
   JLabel myLabel = null;
   String text = null;
   public static void main(String[] a) {
      JButtonAction3 myTest = new JButtonAction3();
      myTest.createFrame();
   }
   public void createFrame() {
      JFrame f = new JFrame("My Switch Button");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container c = f.getContentPane();
      c.setLayout(new GridLayout(2,1));
      text = "On";
      myButton = new JButton(text);
      myButton.addMouseListener(this);
      c.add(myButton);
      myLabel = new JLabel(text,SwingConstants.CENTER);
      c.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void mouseClicked(MouseEvent e) {
      if (text.equals("On")) text = "Off";
      else text = "On"; 
      myButton.setText(text);
      myLabel.setText(text);
   }
}
```

If you run this example, you will get:

![](Images/image00145.jpeg)

JButton Button with Mouse Adapter

The button works nicely. If you click the button, the button label text will change from "On" to "Off", and the text of the label component will also change.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JCheckBox - Swing Check Box Class

This chapter provides tutorial notes and example codes on JCheckBox class. Topics include description of the javax.swing.JCheckBox class and its methods; example program of creating check boxes and event listeners; example program of identify selected check boxes.

> [javax.swing.JCheckBox and Related Methods](#part0037.xhtml)
> 
> [ActionListener, ChangeListener and ItemListener](#part0038.xhtml)
> 
> [isSelected() - Getting State of Check Box](#part0039.xhtml)

Conclusions:

*   javax.swing.JCheckBox class represents a UI check box.
*   ActionListener, ChangeListener, or ItemListener interface can be used handle user actions on a check box.
*   isSelected() method can be used to detect the state of a check box.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JCheckBox - Swing Check Box Class](#part0036.xhtml)

∟javax.swing.JCheckBox and Related Methods

This section describes the javax.swing.JCheckBox class, and its commonly used methods.

javax.swing.JCheckBox - A Swing class representing a UI check box. Some interesting methods are:

*   JCheckBox(String) - Constructor to create a check box with the specified string displayed next to the check box. The check box is unchecked by default.
*   addActionListener(ActionListener) - Method to add an action listener to this check box to handle action events. A mouse click on this check box will trigger one action event.
*   addChangeListener(ChangeListener) - Method to add a change listener to this check box to handle change events. A mouse click on this check box will trigger many change events.
*   addItemListener(ItemListener) - Method to add an item listener to this check box to handle item events. A mouse click on this check box will trigger one item event.
*   setActionCommand(String) - Method to set an action command string to this check box.
*   isSelected() - Method to return the state of the check box.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JCheckBox - Swing Check Box Class](#part0036.xhtml)

∟ActionListener, ChangeListener and ItemListener

This section provides a tutorial example on how to use ActionListener, ChangeListener and ItemListener interfaces to handle different types of events generated on check boxes.

As you can see from the previous section, a check box can have 3 types of event listeners: ActionListener, ChangeListener, and ItemListener. The following sample program shows you when those listeners are called, and how many times:

```
 /* JCheckBoxTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JCheckBoxTest {
   public static void main(String[] a) {
      JFrame f = new JFrame("My Check Boxes");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

      MyCheckBox red = new MyCheckBox("Red");
      f.getContentPane().add(red,BorderLayout.NORTH);

      MyCheckBox green = new MyCheckBox("Green");
      f.getContentPane().add(green,BorderLayout.CENTER);

      MyCheckBox blue = new MyCheckBox("Blue");
      f.getContentPane().add(blue,BorderLayout.SOUTH);

      f.pack();
      f.setVisible(true);
   }
   private static class MyCheckBox extends JCheckBox 
      implements ActionListener, ChangeListener, ItemListener  {
      static int count = 0;
      String text = null;
      public MyCheckBox(String t) {
         super(t);
         text = t;
         addActionListener(this);
         addChangeListener(this);
         addItemListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         count++;
         System.out.println(count+": Action performed - "+text);
      }
      public void stateChanged(ChangeEvent e) {
         count++;
         System.out.println(count+": State changed - "+text);
      }
      public void itemStateChanged(ItemEvent e) {
         count++;
         System.out.println(count+": Item state changed - "+text);
      }
   }
}
```

This example program creates 3 check boxes. Each button has 3 listeners to handle 3 different types of events. A counter is used in the listener class to help to identify the order of events.

If you run this program, you will see 3 check boxes: "Red", "Green" and "Blue":

![](Images/image00146.jpeg)

JCheckBox Listeners

If you move your mouse to the "Red" check box, you see 1 "State changed" message. If you press the "Red" check box, you see 2 more "State changed" messages. If you release the "Red" check box, you see 5 more messages. If you move your mouse away from the "Red" check box, you see 1 more "State changed" message.

```
 1: State changed - Red

2: State changed - Red
3: State changed - Red

4: State changed on - Red
5: Item state changed - Red
6: State changed on - Red
7: Action performed - Red
8: State changed on - Red

9: State changed on - Red

10: State changed on - Green

11: State changed on - Green
12: State changed on - Green

13: State changed on - Green
14: Item state changed - Green
15: State changed on - Green
16: Action performed - Green
17: State changed on - Green

18: State changed on - Green
```

Note that:

*   Action event raised only once when you release a check box.
*   Item event (itemStateChanged method call) is raised only once when you release a check box.
*   Change event (stateChanged method call) is raised many times, when you move your mouse in to and out of a check box, press and release a check box.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JCheckBox - Swing Check Box Class](#part0036.xhtml)

∟isSelected() - Getting State of Check Box

This section provides a tutorial example on how to use the isSelected() method to know the state of a check box.

If you are using multiple check boxes, you need to keep track of them and use the isSelected() method to get the state of each of them. Here is a sample program:

```
 /* JRadioButtonAction.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JCheckBoxAction implements ActionListener {
   JCheckBox red; 
   JCheckBox green; 
   JCheckBox blue;
   JLabel myLabel = null;
   public static void main(String[] a) {
      JCheckBoxAction myTest = new JCheckBoxAction();
      myTest.createFrame();
   }
   public void createFrame() {
      JFrame f = new JFrame("My Check Boxes");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container c = f.getContentPane();
      c.setLayout(new BoxLayout(c,BoxLayout.Y_AXIS));
      JPanel p = new JPanel();
      p.setLayout(new GridLayout(3,1));

    red = new JCheckBox("Red");
      green = new JCheckBox("Green");
      blue = new JCheckBox("Blue");
      p.add(red);
      p.add(green);
      p.add(blue);

      c.add(p);
      JButton b = new JButton("Done");
      b.addActionListener(this);
      c.add(b);
      myLabel = new JLabel("Please select",SwingConstants.CENTER);
      c.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
    String t = "";
    if (red.isSelected()) t += "Red ";
    if (green.isSelected()) t += "Green ";
    if (blue.isSelected()) t += "Blue ";
    if (t.equals("")) t = "Nothing selected";
      myLabel.setText(t);
   }
}
```

If you run this program, you will see none of the check boxes is selected initially. If you click "Done", you will get the "Nothing selected" message. If you select some check boxes, then click "Done", you will get all selected items:

![](Images/image00147.jpeg)

JCheckBox Selected Items

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JRadioButton - Swing Radio Button Class

This chapter provides tutorial notes and example codes on JRadioButton class. Topics include description of the javax.swing.JRadioButton class and its methods; example program of creating radio buttons and event listeners; example program of identify the selected button in a button group.

> [javax.swing.JRadioButton and Related Classes](#part0041.xhtml)
> 
> [ActionListener, ChangeListener and ItemListener](#part0042.xhtml)
> 
> [getSelection() - Getting Selected Button](#part0043.xhtml)

Conclusions:

*   javax.swing.JRadioButton class represents a UI radio button.
*   ActionListener, ChangeListener, or ItemListener interface can be used handle user actions on a radio button.
*   getSelection() method can be used to detect the selected option in a ButtonGroup.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JRadioButton - Swing Radio Button Class](#part0040.xhtml)

∟javax.swing.JRadioButton and Related Classes

This section describes the javax.swing.JRadioButton class, the javax.swing.ButtonGroup class, and the javax.swing.JToggleButton.ToggleButtonModel class.

javax.swing.JRadioButton - A Swing class representing a UI radio button. Some interesting methods are:

*   JRadioButton(String) - Constructor to create a radio button with the specified string displayed next to the button.
*   addActionListener(ActionListener) - Method to add an action listener to this button to handle action events. A mouse click on this button will trigger one action event.
*   addChangeListener(ChangeListener) - Method to add a change listener to this button to handle change events. A mouse click on this button will trigger many change events.
*   addItemListener(ItemListener) - Method to add an item listener to this button to handle item events. A mouse click on this button will trigger one item event.
*   setActionCommand(String) - Method to set an action command string to this button.

javax.swing.ButtonGroup - A Swing class representing a group of buttons. If one radio button is selected in a group, all other buttons in the same group are un-selected.

*   add(AbstractButton) - Method to add a button to this button group.
*   getSelection() - Method to return the selected button in this button group as a ButtonModel object.

javax.swing.JToggleButton.ToggleButtonModel - A Swing class representing a default implementation of toggle button's data model. ToggleButtonModel is an inner class nested inside javax.swing.JToggleButton, which is a base class of JRadioButton.

*   getActionCommand() - Method to return the action command string of the associated button.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JRadioButton - Swing Radio Button Class](#part0040.xhtml)

∟ActionListener, ChangeListener and ItemListener

This section provides a tutorial example on how to use ActionListener, ChangeListener and ItemListener interfaces to handle different types of events generated on radio buttons.

As you can see from the previous section, a radio button can have 3 types of event listeners: ActionListener, ChangeListener, and ItemListener. The following sample program shows you when those listeners are called, and how many times:

```
 /* JRadioButtonTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JRadioButtonTest {
   public static void main(String[] a) {
      JFrame f = new JFrame("My Radio Buttons");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      ButtonGroup g = new ButtonGroup();
      MyRadioButton b1 = new MyRadioButton("On");
      g.add(b1);
      f.getContentPane().add(b1,BorderLayout.NORTH);
      MyRadioButton b2 = new MyRadioButton("Off");
      g.add(b2);
      f.getContentPane().add(b2,BorderLayout.SOUTH);
      f.pack();
      f.setVisible(true);
   }
   private static class MyRadioButton extends JRadioButton 
      implements ActionListener, ChangeListener, ItemListener  {
      static int count = 0;
      String text = null;
      public MyRadioButton(String t) {
         super(t);
         text = t;
         addActionListener(this);
         addChangeListener(this);
         addItemListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         count++;
         System.out.println(count+": Action performed - "+text);
      }
      public void stateChanged(ChangeEvent e) {
         count++;
         System.out.println(count+": State changed on - "+text);
      }
      public void itemStateChanged(ItemEvent e) {
         count++;
         System.out.println(count+": Item state changed - "+text);
      }
   }
}
```

This example program creates two radio buttons and puts them in a single button group. Each button has 3 listeners to handle 3 different types of events. A counter is used in the listener class to help to identify the order of events.

If you run this program, you will see two radio buttons: one labeled as "On" and the other labeled as "Off":

![](Images/image00148.jpeg)

JRadioButton Listeners

If you press the "On" button and hold it, you will see 2 messages showing in command window. If you release the "On" button, you will see 5 more messages. If you continue to press the "Off" button and hold it, you will see 2 more messages. If you release the "Off" button, you will see 7 more messages. Here is the list of all the messages:

```
 1: State changed on - On
2: State changed on - On     - "On" pressed
3: State changed on - On
4: Item state changed - On
5: State changed on - On
6: Action performed - On
7: State changed on - On     - "On" released
8: State changed on - Off
9: State changed on - Off    - "Off" pressed
10: State changed on - On
11: Item state changed - On
12: State changed on - Off
13: Item state changed - Off
14: State changed on - Off
15: Action performed - Off
16: State changed on - Off   - "Off" released
```

Note that:

*   Action event raised only once when you release a button.
*   Change event (stateChanged method call) is raised 2 times when you press a button; and raised 2 time again when you release a button. This tells us that a button has more than 2 states: selected and deselected.
*   Item event (itemStateChanged method call) is raised only once when you release a button.
*   In a button group, if one button is selected, other selected buttons will be deselected. Events #10 and #11 show that when "Off" is selected, "On" is deselected.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JRadioButton - Swing Radio Button Class](#part0040.xhtml)

∟getSelection() - Getting Selected Button

This section provides a tutorial example on how to use the getSelection() method to know which button is selected in a button group.

If there are many radio buttons in a button group, how do you find the one that is currently selected? One way is to use the getSelection() method of ButtonGroup class. Here is a sample program:

```
 /* JRadioButtonAction.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JRadioButtonAction implements ActionListener {
   ButtonGroup myGroup = null;
   JLabel myLabel = null;
   public static void main(String[] a) {
      JRadioButtonAction myTest = new JRadioButtonAction();
      myTest.createFrame();
   }
   public void createFrame() {
      JFrame f = new JFrame("My Radio Buttons");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container c = f.getContentPane();
      c.setLayout(new BoxLayout(c,BoxLayout.Y_AXIS));
      myGroup = new ButtonGroup();
      JPanel p = new JPanel();
      p.setLayout(new GridLayout(3,1));
      addOption(p,myGroup,"Red");
      addOption(p,myGroup,"Green");
      addOption(p,myGroup,"Blue");
      c.add(p);
      JButton b = new JButton("Select");
      b.addActionListener(this);
      c.add(b);
      myLabel = new JLabel("Please select",SwingConstants.CENTER);
      c.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void addOption(JPanel p, ButtonGroup g, String t) {
      JRadioButton b = new JRadioButton(t);
      b.setActionCommand(t);
      p.add(b);
      g.add(b);
   }
   public void actionPerformed(ActionEvent e) {
      ButtonModel b = myGroup.getSelection();
      String t = "Not selected";
      if (b!=null) t = b.getActionCommand();
      myLabel.setText(t);
   }
}
```

If you run this program, you will see none of the radio buttons is selected initially. If you click "Select", you will get the "Not selected" message. If you select any of the radio buttons, then click "Select", you will get the correct message:

![](Images/image00149.jpeg)

JRadioButton Selected Button

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JTextField - Swing Text Field Class

This chapter provides tutorial notes and example codes on JTextField class. Topics include description of the javax.swing.JTextField class and its methods; example program of creating text fields with event listeners.

> [javax.swing.JTextField and Related Classes](#part0045.xhtml)
> 
> [ActionListener and DocumentListener](#part0046.xhtml)

Conclusions:

*   javax.swing.JTextField class represents a UI text input field.
*   java.awt.event.ActionListener interface allows you to create your own handler to respond to keyboard inputs.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JTextField - Swing Text Field Class](#part0044.xhtml)

∟javax.swing.JTextField and Related Classes

This section describes the javax.swing.JTextField class, the javax.swing.text.PlainDocument class, and the javax.swing.event.DocumentListener class.

javax.swing.JTextField - A Swing class representing a UI text field. Some interesting methods are:

*   JTextField(int) - Constructor to create a text field with the specified number of columns.
*   JTextField(String) - Constructor to create a text field with the specified string as the initial text.
*   addActionListener(ActionListener) - Method to add an action listener to this text field to handle action events. Pressing the "Enter" key in this field will trigger one action event.
*   getDocuement() - Method to return the document object that is used to hold the text of this field.
*   getText() - Method to return the text of this field as a string object.

javax.swing.text.PlainDocument - A Swing class representing a plain text document. PlainDocument is used as the default document for JTextField to hold its text. Method includes:

*   addDocumentListener(DocumentListener) - Method to add a document listener to this document.

javax.swing.event.DocumentListener - A Swing interface for the implementing class to handle document events. Method includes:

*   changeUpdate(DocumentEvent) - Method to be called when any attribute of the document is changed.
*   insertUpdate(DocumentEvent) - Method to be called when text is inserted into the document.
*   removeUpdate(DocumentEvent) - Method to be called when text is removed from the document

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JTextField - Swing Text Field Class](#part0044.xhtml)

∟ActionListener and DocumentListener

This section provides a tutorial example on how to create a text field with an event handler implemented as both the ActionListener listener and the DocumentListener listener.

As you can see from the previous section, a text field can trigger action events directly. It can also trigger document events indirectly through its associated document. Here is a sample program to show you how and when those events are triggered:

```
 /* JTextFieldTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
import javax.swing.text.*;
public class JTextFieldTest {
   public static void main(String[] a) {
      JFrame f = new JFrame("Text Field Test");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      MyTextField t = new MyTextField(16);
      f.getContentPane().add(t,BorderLayout.CENTER);
      f.pack();
      f.setVisible(true);
   }
   private static class MyTextField extends JTextField 
      implements ActionListener, DocumentListener  {
      static int count = 0;
      public MyTextField(int l) {
         super(l);
         addActionListener(this);
         Document doc = this.getDocument();
         System.out.println("The document object: "+doc);
         doc.addDocumentListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         count++;
         System.out.println(count+": Action performed - "+getText());
      }
      public void insertUpdate(DocumentEvent e) {
         count++;
         System.out.println(count+": Insert update - "+getText());
      }
      public void removeUpdate(DocumentEvent e) {
         count++;
         System.out.println(count+": Remove update - "+getText());
      }
      public void changedUpdate(DocumentEvent e) {
         count++;
         System.out.println(count+": Change update - "+getText());
      }
   }
}
```

Run this program and do the following in the text field:

*   Type "h".
*   Type "i".
*   Press the backspace key to remove "i".
*   Type "e".
*   Press the enter key.

The text field should look like this:

![](Images/image00150.jpeg)

JTextField Listeners

And you should get the following output in the console window:

```
 The document object: javax.swing.text.PlainDocument@4e79f1
1: Insert update - h
2: Insert update - hi
3: Remove update - h
4: Insert update - he
5: Action performed - he
```

The output confirms that:

*   TextField class is using PlainDocument as the default document type.
*   ActionListener is called when the enter key is pressed.
*   changeUpdate() is not called.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JComboBox - Swing Combo Box Class

This chapter provides tutorial notes and example codes on JComboBox class. Topics include description of the javax.swing.JComboBox class and its methods; example programs of creating a combo box, getting selected option from a combo box, using a combo box as a text field.

> [javax.swing.JComboBox and Related Methods](#part0048.xhtml)
> 
> [ActionListener and ItemListener](#part0049.xhtml)
> 
> [getSelectedItem() - Selected Item of Combo Box](#part0050.xhtml)
> 
> [setEditable() - Use Combo Box as Text Field](#part0051.xhtml)

Conclusions:

*   javax.swing.JComboBox class represents a UI combo box.
*   ActionListener, ChangeListener, or ItemListener interface can be used handle user actions on a combo box.
*   getSelectedItem() method can be used to get the selected or entered item from a combo box.
*   setEditable() method can be used to turn on or turn off the text input part of a combo box.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JComboBox - Swing Combo Box Class](#part0047.xhtml)

∟javax.swing.JComboBox and Related Methods

This section describes the javax.swing.JComboBox class, and its commonly used methods.

javax.swing.JComboBox - A Swing class representing a UI drop-down button, also called combo box. Some interesting methods are:

*   JComboBox(String[]) - Constructor to create a check box with the specified string displayed next to the check box. The check box is unchecked by default.
*   addActionListener(ActionListener) - Method to add an action listener to this check box to handle action events. A mouse click on this check box will trigger one action event.
*   addItemListener(ItemListener) - Method to add an item listener to this check box to handle item events. A mouse click on this check box will trigger one item event.
*   setSelectedIndex(index) - Method to set the selection to the option of the given index. If index is -1, no option is selected.
*   getSelectedItem() - Method to return the first selected item from the combo box. If no option is selected, it returns null.
*   getSelectedObjects() - Method to return all selected items from the combo box.
*   setEditable() - Method to set the combo box as editable, so that users can enter text into the combobox like a text field.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JComboBox - Swing Combo Box Class](#part0047.xhtml)

∟ActionListener and ItemListener

This section provides a tutorial example on how to use ActionListener and ItemListener interfaces to handle different types of events generated on combo box.

As you can see from the previous section, a check box can have 2 types of event listeners: ActionListener and ItemListener. The following sample program shows you when those listeners are called, and how many times:

```
 /* JComboBoxTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JComboBoxTest {
   public static void main(String[] a) {
      JFrame f = new JFrame("My Combo Box");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

      JLabel color = new JLabel("Colors:");
      f.getContentPane().add(color,BorderLayout.NORTH);
      String[] options = {"Red", "Green", "Blue"};
      MyComboBox list = new MyComboBox(options);
    list.setSelectedIndex(-1);
      f.getContentPane().add(list,BorderLayout.SOUTH);

      f.pack();
      f.setVisible(true);
   }
   private static class MyComboBox extends JComboBox<String>
      implements ActionListener, ItemListener  {
      static int count = 0;
      public MyComboBox(String[] l) {
         super(l);
         addActionListener(this);
         addItemListener(this);
         this.setSelectedIndex(-1);
      }
      public void actionPerformed(ActionEvent e) {
         count++;
         System.out.println(count+": Action performed - ");
      }
      public void itemStateChanged(ItemEvent e) {
         count++;
         System.out.println(count+": Item state changed - ");
      }
   }
}
```

This example program creates a combo box with 3 options. It has 2 listeners to handle 2 different types of events. A counter is used in the listener class to help to identify the order of events.

If you run this program, you will see a combo box with 3 options: "Red", "Green" and "Blue". By default, the first option will be selected. But I called the setSelectedIndex(-1) to removed the selection.

![](Images/image00151.jpeg)

JComboBox Listeners

If you open the drop-down list, you see messages 1 and 2\. If you select the "Red" option, you see messages 3 and 4\. If you change the selection to "Green", you see messages 5, 6, and 7.

```
 1: Item state changed -
2: Action performed -

3: Item state changed -
4: Action performed -

5: Item state changed -
6: Item state changed -
7: Action performed -
```

Note that:

*   Action event raised only once when you select an option.
*   Item event (itemStateChanged method call) is raised when change is made on the combo box.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JComboBox - Swing Combo Box Class](#part0047.xhtml)

∟getSelectedItem() - Selected Item of Combo Box

This section provides a tutorial example on how to use the getSelectedItem() method to know which option is selected from a combo box.

If you are using a combo box with multiple options, you can use the getSelectedItem() method to find out which option is selected. Here is a sample program:

```
 /* JComboBoxAction.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JComboBoxAction implements ActionListener {
   JComboBox<String> combo;
   JLabel myLabel = null;
   public static void main(String[] a) {
      JComboBoxAction myTest = new JComboBoxAction();
      myTest.createFrame();
   }
   public void createFrame() {
    JFrame f = new JFrame("My Combo Box");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container c = f.getContentPane();
      c.setLayout(new BoxLayout(c,BoxLayout.Y_AXIS));

      JLabel color = new JLabel("Colors:");
      c.add(color);

      String[] options = {"Red", "Green", "Blue"};
      combo = new JComboBox<String>(options);
    combo.setSelectedIndex(-1);
      c.add(combo);

      JButton b = new JButton("Done");
      b.addActionListener(this);
      c.add(b);

      myLabel = new JLabel("Please select");
      c.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
    String t = (String) combo.getSelectedItem();
    if (t == null) t = "Nothing selected";
      myLabel.setText(t);
   }
}
```

If you run this program, you will see none of the options is selected initially. If you click "Done", you will get the "Nothing selected" message. If you select an option then click "Done", you will get the selected color:

![](Images/image00152.jpeg)

JComboBox Selected Option

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JComboBox - Swing Combo Box Class](#part0047.xhtml)

∟setEditable() - Use Combo Box as Text Field

This section provides a tutorial example on how to call the setEditable(true) method to use a combo box as a dropdown list and text field at the same time.

If you want to use a combo box as both a dropdown list and a text text field, you can call the getEditable(true) method on the combo box. Here is a sample program:

```
 /* JComboBoxAsEditable.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
public class JComboBoxAsEditable implements ActionListener {
   JComboBox<String> combo;
   JLabel myLabel = null;
   public static void main(String[] a) {
      JComboBoxAsEditable myTest = new JComboBoxAsEditable();
      myTest.createFrame();
   }
   public void createFrame() {
    JFrame f = new JFrame("My Combo Box");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container c = f.getContentPane();
      c.setLayout(new BoxLayout(c,BoxLayout.Y_AXIS));

      JLabel color = new JLabel("Colors:");
      c.add(color);

      String[] options = {"Red", "Green", "Blue"};
      combo = new JComboBox<String>(options);
    combo.setEditable(true);
    combo.setSelectedIndex(-1);
      c.add(combo);

      JButton b = new JButton("Done");
      b.addActionListener(this);
      c.add(b);

      myLabel = new JLabel("Please end/select");
      c.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
    String t = (String) combo.getSelectedItem();
    if (t == null) t = "Nothing entered/selected";
      myLabel.setText(t);
   }
}
```

If you run this program, you will see none of the options is selected initially and nothing is entered in the text field. If you click "Done", you will get the "Nothing entered/selected" message. If you select an option then click "Done", you will get the selected color. If you enter your own color, and click "Done", you will get the color you entered:

![](Images/image00153.jpeg)

JComboBox Editable as Text Field

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Menu Bar, Menus, Menu Items and Listeners

This chapter provides tutorial notes and example codes on menu bar, menus and menu items. Topics include introduction to JMenuBar, JMenu, and JMenuItem classes; test programs of menu bar, menus and menu items; using radio button and check box menu items; using menu, item, and action listeners; using mnemonics and accelerators on keyboard.

> [JMenuBar, JMenu, and JMenuItem Classes](#part0053.xhtml)
> 
> [JMenuBarTest.java - Menu Bar Test Program](#part0054.xhtml)
> 
> [JMenuTest.java - Menu Test Program](#part0055.xhtml)
> 
> [JMenuItemTest.java - Menu Item Test Program](#part0056.xhtml)
> 
> [JRadioButtonMenuItemTest.java - Radio Button Menu Item Test Program](#part0057.xhtml)
> 
> [JCheckBoxMenuItemTest.java - Check Box Menu Item Test Program](#part0058.xhtml)
> 
> [javax.swing.event.MenuListener - Menu Listener Interface](#part0059.xhtml)
> 
> [JMenuItemActionListenerTest.java - Menu Item Action Listener Test](#part0060.xhtml)
> 
> [Item Listener on Radio Button Menu Items](#part0061.xhtml)
> 
> [Item Listener on Check Box Menu Items](#part0062.xhtml)
> 
> [javax.swing.event.MenuKeyListener - Menu Key Listener Interface](#part0063.xhtml)
> 
> [setMnemonic() - Setting Keyboard Mnemonics on Menu Items](#part0064.xhtml)
> 
> [setAccelerator() - Setting Keyboard Accelerators on Menu Items](#part0065.xhtml)
> 
> [setMnemonic() - Setting Keyboard Mnemonics on Menus](#part0066.xhtml)

Conclusions:

*   javax.swing.JMenuBar class allows you to create and manage the menu bar on the main frame.
*   javax.swing.JMenu class allows you to create and manage a single menu linked to the menu bar.
*   javax.swing.JMenuItem class allows you to create and manage a standard menu item linked to a menu.
*   javax.swing.JRadioButtonMenuItem class allows you to create and manage a radio button menu item.
*   javax.swing.JCheckBoxMenuItem class allows you to create and manage a checkbox menu item.
*   javax.swing.event.MenuListener Swing interface allows you to implement your own menu event handler methods.
*   java.awt.event.ActionListener AWT interface allows you to implement your own event handler methods.
*   javax.swing.event.MenuKeyListener Swing interface allows you to implement your own handlers for keyboard inputs.

Sample programs listed in this chapter have been tested with JDK 1.6.0 to JDK 15.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JMenuBar, JMenu, and JMenuItem Classes

This section describes 3 Swing classes, JMenuBar, JMenu, and JMenuItem, to build a menu interface for a frame window. A typical menu interface has a menu bar with multiple menus or menu items. A menu can have multiple sub menus or menu items.

javax.swing.JMenuBar - A Swing class representing the menu bar on the main frame. javax.swing.JMenu objects added a JMenuBar object will be displayed horizontally. Interesting methods of JMenuBar include:

*   JMenuBar() - Constructor to create a menu bar which can be added to a frame window.
*   add(JMenu) - Method to add a new JMenu object to the end of the menu be list.
*   getMenuCount() - Method to return the number of menus in this menu bar.
*   getMenu(int) - Method to return the JMenu object of the specified position index. Of course, index 0 is the first menu.
*   getSubElements() - Method to return an array of MenuElement objects.
*   isSelected() - Method to return true if an element is currently selected in the menu bar.

javax.swing.JMenu - A Swing class representing a user interface menu. A JMenu object can be added to a JMenuBar or another JMenu object to form a menu tree structure. A JMenu object actually has two graphical components, a clickable button displayed in the parent JMenu or JMenuBar and a popup window. When its button is clicked, its pop up window will be displayed. Interesting methods of JMenu include:

*   JMenu(String) - Constructor to create a menu with the specified string as its button text.
*   add(JMenuItem) - Method to add a JMenuItem object to the end of its current menu item list.
*   addSeparator() - Method to add a menu separator to the end of its current menu item list.
*   getItemCount() - Method to return the number of its menu items.
*   getItem(int pos) - Method to return the JMenuItem object of the specified position index. Of course, index 0 is the first menu item.
*   isSelected() - Method to return true if this menu is selected.
*   isTopLevelMenu() - Method to return true if this menu is a top menu. A top menu is a menu added to the menu bar, not to another menu.
*   doClick(int) - Method to simulate a user click on this menu.

javax.swing.JMenuItem - A Swing class representing a user interface menu item. A JMenuItem object can be added to a JMenuBar or another JMenu object in a menu tree structure. A JMenuItem should be associated with a MenuKeyListener object so that tasks can be performed with the menu item is clicked. Interesting methods of JMenuItem include:

*   JMenuItem(String) - Constructor to create a menu item with the specified string as its button text.
*   addMenuKeyListener(MenuKeyListener) - Method to add a MenuKeyListener object to this menu item.
*   setEnabled(boolean) - Method to set this menu item to be enabled or disabled based on the specified Boolean value.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JMenuBarTest.java - Menu Bar Test Program

This section provides a tutorial example on how to use the javax.swing.JMenuBar class to create a menu bar in a frame window. Menus and menu items added to the menu bar will be listed horizontally.

Here is an example program I wrote to test the JMenuBar class:

```
 /* JMenuBarTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
public class JMenuBarTest {
   public static void main(String[] a) {
      JFrame f = new JFrame("JMenuBar Test");
      f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      f.setBounds(50,50,250,150);

      JMenuBar mb = new JMenuBar();      
      mb.add(new JMenu("Tools")); 
      mb.add(new JMenu("Options")); 
      mb.add(new JMenuItem("Save")); 
      mb.add(new JMenuItem("Quit")); 
      mb.add(new JButton("Stop")); 

      f.setJMenuBar(mb);
      f.getContentPane().add(new MyButton());
      f.setVisible(true);
   }
   private static class MyButton extends JButton 
      implements ActionListener {
      public MyButton() {
         super("Check");
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Check button clicked");
         JFrame myFrame = (JFrame) 
            (this.getParent().getParent()).getParent().getParent();
         JMenuBar myMenuBar = myFrame.getJMenuBar();
         System.out.println("# of elements in the menu bar: "
            +myMenuBar.getMenuCount());
         System.out.println("Is the menu bar selected: "
            +myMenuBar.isSelected());
      }
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00154.jpeg)

Menu Bar Listeners

If you click the "Check" button, click the "Options" menu in the menu bar, and click the "Check" button again, you will see text output in the console window:

```
 Check button clicked
# of elements in the menu bar: 5
Is the menu bar selected: false
Check button clicked
# of elements in the menu bar: 5
Is the menu bar selected: true
```

Interesting notes about this tutorial example:

*   JMenuItem objects can be added to the menu bar in the same way as JMenu objects.
*   Other components can also be added to the menu bar. See the "Stop" JButton object added in the example program.
*   The "Check" JButton added in the content pane is a grand grand grand child of the frame. So there are 3 layers of component in the content pane, because I have to use "this.getParent().getParent()).getParent().getParent()" to reach the frame object from the button object.
*   getMenuCount() and isSelected() methods work as expected.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JMenuTest.java - Menu Test Program

This section provides a tutorial example on how to use the javax.swing.JMenu class to create multiple menus and how to add them to the menu bar. Sub menus and menu items added to a menu will be listed vertically when the menu is selected.

Here is an example program I wrote to test the JMenu class:

```
 /* JMenuTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
public class JMenuTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JMenuTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenu mySubMenu = getOpenMenu();
      myMenu.add(mySubMenu);
      JMenuItem myItem = new JMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      JMenuItem myItem = new JMenuItem("Red");
      myMenu.add(myItem);
      myItem = new JMenuItem("Green");
      myMenu.add(myItem);
      myItem = new JMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOpenMenu() {
      JMenu myMenu = new JMenu("Open");
      JMenuItem myItem = new JMenuItem("Java");
      myMenu.add(myItem);
      myItem = new JMenuItem("HTML");
      myMenu.add(myItem);
      myItem = new JMenuItem("GIF");
      myMenu.add(myItem);
      return myMenu;
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00155.jpeg)

Menu with Two Levels

Interesting notes about this tutorial example:

*   Multiple menus can be added to a menu bar. The "File" menu and the "Color" menu are added to the menu bar in this example.
*   A menu can have a child menu included in the same way as a menu item. The "Open" menu is added as a child menu to the "File" menu in this example.
*   Calling the addSeparator() method on a JMenu object does add a separation line in the menu element list.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JMenuItemTest.java - Menu Item Test Program

This section provides a tutorial example on how to use the javax.swing.JMenuItem class to create menu items and add them to different menus, sub menus, or the menu bar. Sub menus and menu items added to a menu will be listed vertically when the menu is selected.

Here is an example program I wrote to test the JMenuItem class:

```
 /* JMenuItemTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
public class JMenuItemTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JMenuItemTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Item Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);
      JMenuItem myItem = new JMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myItem.setEnabled(false);
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      JMenuItem myItem = new JMenuItem("Red");
      myMenu.add(myItem);
      myItem = new JMenuItem("Green");
      myMenu.add(myItem);
      myItem = new JMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenu mySubMenu = getOnOffMenu("Sound");
      myMenu.add(mySubMenu);
      mySubMenu = getOnOffMenu("Auto save");
      mySubMenu.setEnabled(false);
      myMenu.add(mySubMenu);
      return myMenu;
   }
   private JMenu getOnOffMenu(String title) {
      JMenu myMenu = new JMenu(title);
      JMenuItem myItem = new JMenuItem("On");
      myMenu.add(myItem);
      myItem = new JMenuItem("Off");
      myMenu.add(myItem);
      return myMenu;
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00156.jpeg)

Menu Item Test

Interesting notes about this tutorial example:

*   A menu item can be added directly on the menu bar. The "Help" menu item is added to the menu bar in this example. But it is strongly not recommended. You will get a crash if you use the arrow key to navigate in the menu bar.
*   A menu item can be disabled by calling the set setEnabled(false) function. A disabled menu item will be listed in gray and not be clickable. The "Close" menu item is disabled in this example.
*   A menu can also be disabled by calling the set setEnabled(false) function. A disabled menu will be listed in gray and not be clickable. The "Auto save" menu item is disabled in this example.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JRadioButtonMenuItemTest.java - Radio Button Menu Item Test Program

This section provides a tutorial example on how to use the javax.swing.JRadioButtonMenuItem class to create multiple radio button menu items and added them into a button group. If one radio button menu item is selected in a group, all others will be unselected.

Other the regular menu item class, javax.swing.JMenuItem, Swing supports a special menu item class, javax.swing.JRadioButtonMenuItem, which represents radio button menu items with following special features:

*   A radio button menu item will be listed with a radio button icon.
*   The radio button icon will be displayed as checked if the radio button menu item is selected.
*   The radio button icon will be displayed as unchecked if the radio button menu item is unselected.
*   Multiple radio button menu items are added into a ButtonGroup object to form button group.
*   If one radio button menu item in a button group is selected, all other radio button menu items will be unselected.

Here is an example program I wrote to test the JRadioButtonMenuItem classes:

```
 /* JRadioButtonMenuItemTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
public class JRadioButtonMenuItemTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JRadioButtonMenuItemTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Radio Button Menu Item Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);
      JMenuItem myItem = new JMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myItem.setEnabled(false);
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      ButtonGroup myGroup = new ButtonGroup();
      JRadioButtonMenuItem myItem = new JRadioButtonMenuItem("Red");
      myItem.setSelected(true);
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new JRadioButtonMenuItem("Green");
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new JRadioButtonMenuItem("Blue");
      myGroup.add(myItem);
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenuItem myItem = new JMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new JMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00157.jpeg)

Radio Button as Menu Item (on macOS)

Interesting notes about this tutorial example:

*   A radio button menu item can be listed as selected by default, if the setSelected(true) method is called on the item. The "Red" radio button menu item selected by default in this example.

There seems to be a problem with radio button menu items on macOS computers. They are displayed without the radio button icons. If you run the same program on a Windows computer, you will see radio button icons displayed as shown below.

![](Images/image00158.jpeg)

Radio Button Menu Item Test (on Windows)

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JCheckBoxMenuItemTest.java - Check Box Menu Item Test Program

This section provides a tutorial example on how to use the javax.swing.JCheckBoxMenuItemTest class to create check box menu items. If a check box menu item is selected, its check box icon will have a check sign.

Swing also supports a special menu item class, javax.swing.JCheckBoxMenuItem, which represents check box menu items with following special features:

*   A check box menu item will be listed with a check box icon.
*   The check box icon will be displayed as checked if the check box menu item is selected.
*   The check box icon will be displayed as unchecked if the check box menu item is unselected.

Here is an example program I wrote to test the JCheckBoxMenuItemTest classes:

```
 /* JCheckBoxMenuItemTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
public class JCheckBoxMenuItemTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JCheckBoxMenuItemTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Check Box Menu Item Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);
      JMenuItem myItem = new JMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myItem.setEnabled(false);
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      JMenuItem myItem = new JMenuItem("Red");
      myMenu.add(myItem);
      myItem = new JMenuItem("Green");
      myMenu.add(myItem);
      myItem = new JMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JCheckBoxMenuItem myItem = new JCheckBoxMenuItem("Sound");
      myItem.setSelected(true);
      myMenu.add(myItem);
      myItem = new JCheckBoxMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00159.jpeg)

Check Box as Menu Item (on macOS)

Interesting notes about this tutorial example:

*   A check box menu item can be listed as selected by default, if the setSelected(true) method is called on the item. The "Sound" check box menu item selected by default in this example.

There seems to be a problem with check box menu items on macOS computers. They are displayed without the check box icons. If you run the same program on a Windows computer, you will see check box icons displayed as shown below.

![](Images/image00160.jpeg)

Check Box Menu Item Test (on Windows)

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟javax.swing.event.MenuListener - Menu Listener Interface

This section provides a tutorial example on how to use javax.swing.event.MenuListener, menu listener interface, to catch events fired by JMenu objects.

Like any other user interface components, JMenu objects fire events when users interact with them. If you want to perform a task when an event occurs on a JMenu object, you need to add an event listener to that JMenu object. To do this, you need know these Swing classes, interfaces and methods:

javax.swing.event.MenuListener - A Swing interface that allows you to implement your own menu event handler methods:

*   menuSelected(MenuEvent) - Event handler method called when the associated menu is selected. You need to implement this method to perform your own task.
*   menuDeselected(MenuEvent) - Event handler method called when the associated menu is deselected. You need to implement this method to perform your own task.
*   menuCanceled(MenuEvent) - Event handler method called when the associated menu is canceled. You need to implement this method to perform your own task.

javax.swing.event.MenuEvent - A Swing class that represents an event occurred on a menu. The most important method in this class is:

*   getSource() - Method returns the JMenu object where the event occurred.

Here is an example program I wrote to test the MenuListener interface:

```
 /* MenuListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
import javax.swing.event.*;
public class MenuListenerTest implements MenuListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new MenuListenerTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Listener Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenu.addMenuListener(this);
      myMenuBar.add(myMenu);

      myMenu = getColorMenu();
      myMenu.addMenuListener(this);
      myMenuBar.add(myMenu);

      myMenu = getOptionMenu();
      myMenu.addMenuListener(this);
      myMenuBar.add(myMenu);

      JMenuItem myItem = new JMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      JMenuItem myItem = new JMenuItem("Red");
      myMenu.add(myItem);
      myItem = new JMenuItem("Green");
      myMenu.add(myItem);
      myItem = new JMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenuItem myItem = new JMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new JMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   public void menuSelected(MenuEvent e) {
      JMenu myMenu = (JMenu) e.getSource();
      System.out.println("Menu Selected: "+myMenu.getText());
   }
   public void menuDeselected(MenuEvent e) {
      JMenu myMenu = (JMenu) e.getSource();
      System.out.println("Menu deselected: "+myMenu.getText());
   }
   public void menuCanceled(MenuEvent e) {
      JMenu myMenu = (JMenu) e.getSource();
      System.out.println("Menu canceled: "+myMenu.getText());
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00161.jpeg)

Menu Listener Test

If you click the "File" menu, move to the "Color" menu, then move to the "Option" menu, you will see some messages printed on the Java console window:

```
 Menu Selected: File
Menu deselected: File
Menu Selected: Color
Menu deselected: Color
Menu Selected: Option
```

Interesting notes about this tutorial example:

*   "public class MenuListenerTest implements MenuListener" declaration is used to make my MenuListenerTest object becoming a MenuListener object.
*   "myMenu.addMenuListener(this);" statement is used to add a MenuListener object to a JMenu object.
*   "JMenu myMenu = (JMenu) e.getSource();" statement is used to get the JMenu object where the event was fired.
*   "myMenu.getText()" expression is used to get the menu button text.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟JMenuItemActionListenerTest.java - Menu Item Action Listener Test

This section provides a tutorial example on how to use java.awt.event.ActionListener, button action listener interface, to catch events fired by JMenuItem objects.

Like any other user interface components, JMenuItem objects also fire events when users interact with them. If you want to perform a task when an event occurs on a JMenuItem object, you need to add an event listener to that JMenuItem item object. Because a JMenuItem is a sub class of AbstractButton, it shares the listener interface and event class with AbstractButton:

java.awt.event.ActionListener - An AWT interface that allows you to implement your own event handler methods:

*   actionPerformed(ActionEvent) - Event handler method called when the associated component is clicked. You need to implement this method to perform your own task.

java.awt.event.ActionEvent - An AWT class that represents an event occurred on a component. The most important method in this class is:

*   getActionCommand() - Method returns the action command string.

Here is an example program I wrote to test the ActionListener interface:

```
 /* JMenuItemActionListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
public class JMenuItemActionListenerTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JMenuItemActionListenerTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Listener Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      MyMenuItem myItem = new MyMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      MyMenuItem myItem = new MyMenuItem("Open");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new MyMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      JMenuItem myItem = new MyMenuItem("Red");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Green");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenuItem myItem = new MyMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   private class MyMenuItem extends JMenuItem 
      implements ActionListener {
      public MyMenuItem(String text) {
         super(text);
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Item clicked: "+e.getActionCommand());
      }
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00162.jpeg)

Menu Item Action Listener Test

If you click the "Help" menu item, click "Open" and "Close" in the "File" menu, then click "Red", "Green" and "Blue" in the "Color" menu, you will see some messages printed on the Java console window:

```
 Item clicked: Help
Item clicked: Open
Item clicked: Close
Item clicked: Red
Item clicked: Green
Item clicked: Blue
```

Interesting notes about this tutorial example:

*   "private class MyMenuItem extends JMenuItem implements ActionListener" declaration is used to create an inner class, MyMenuItem, which extends JMenuItem, implements ActionListener, and adds itself to handle action events.
*   "addActionListener(this);" statement is used to add my inner class, MyMenuItem, itself to handle action events.
*   "e.getActionCommand()" expression is used to get action command string, the menu item button text in this case.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟Item Listener on Radio Button Menu Items

This section provides a tutorial example on how to use java.awt.event.ItemListener, radio button and check box item listener interface, to catch state changed item vents on radio button menu item objects.

Since JRadioButtonMenuItem class is a special menu item class, it supports another event listener, ItemListener, which allows you to catch radio button state changed events:

java.awt.event.ItemListener - An AWT interface that allows you to implement your own radio button state changed event handler methods:

*   itemStateChanged(ItemEvent) - Event handler method called when the state of the associated button is changed. You need to implement this method to perform your own task.

java.awt.event.ItemEvent - An AWT class that represents an event occurred on a radio button. The most important method in this class is:

*   getStateChange() - Method returns an integer: 1 if state is changed to selected or 2 if state is changed to deselected.

Here is an example program I wrote to test the ItemListener interface:

```
 /* JRadioButtonMenuItemListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
public class JRadioButtonMenuItemListenerTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JRadioButtonMenuItemListenerTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Listener Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);

      MyMenuItem myItem = new MyMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      MyMenuItem myItem = new MyMenuItem("Open");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new MyMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      ButtonGroup myGroup = new ButtonGroup();
      MyRadioButtonMenuItem myItem 
         = new MyRadioButtonMenuItem("Red");
      myItem.setSelected(true);
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new MyRadioButtonMenuItem("Green");
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new MyRadioButtonMenuItem("Blue");
      myGroup.add(myItem);
      myMenu.add(myItem);
      return myMenu;
   }
   private class MyMenuItem extends JMenuItem 
      implements ActionListener {
      public MyMenuItem(String text) {
         super(text);
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Item clicked: "+e.getActionCommand());
      }
   }
   private class MyRadioButtonMenuItem extends JRadioButtonMenuItem
      implements ActionListener, ItemListener {
      public MyRadioButtonMenuItem(String text) {
         super(text);
         addActionListener(this);
         addItemListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Item clicked: "+e.getActionCommand());
      }
      public void itemStateChanged(ItemEvent e) {
         System.out.println("State changed: "+e.getStateChange()
            +" on "+((MyRadioButtonMenuItem) e.getItem()).getText());
      }
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00163.jpeg)

Radio Button Menu Item Listener Test

If you click the "Help" menu item and click menu items in the "Color" menu, you will see some messages printed on the Java console window:

```
 State changed: 1 on Red
Item clicked: Help
Item clicked: Red
Item clicked: Red
State changed: 2 on Red
State changed: 1 on Green
Item clicked: Green
State changed: 2 on Green
State changed: 1 on Blue
Item clicked: Blue
```

Interesting notes about this tutorial example:

*   I used inner class MyRadioButtonMenuItem to create radio button menu items with both ActionListener and ItemListener interfaces implemented in the inner class.
*   "e.getActionCommand()" expression is used to get action command string, the menu item button text in this case.
*   "e.getStateChange()" expression is used to get state changed signal
*   Clicking on a selected radio button does not trigger any item events.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟Item Listener on Check Box Menu Items

This section provides a tutorial example on how to use java.awt.event.ItemListener, radio button and check box item listener interface, to catch state changed item vents on check box menu item objects.

Like JRadioButtonMenuItem, JCheckBoxMenuItem class is a special menu item class, it supports another event listener, ItemListener, which allows you to catch radio button state changed events.

Here is an example program I wrote to test the ItemListener interface on check box menu items:

```
 /* JCheckBoxMenuItemListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
public class JCheckBoxMenuItemListenerTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JCheckBoxMenuItemListenerTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Listener Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      MyMenuItem myItem = new MyMenuItem("Help");
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      MyMenuItem myItem = new MyMenuItem("Open");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new MyMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JCheckBoxMenuItem myItem = new MyCheckBoxMenuItem("Sound");
      myItem.setSelected(true);
      myMenu.add(myItem);
      myItem = new MyCheckBoxMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   private class MyMenuItem extends JMenuItem 
      implements ActionListener {
      public MyMenuItem(String text) {
         super(text);
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Item clicked: "+e.getActionCommand());
      }
   }
   private class MyCheckBoxMenuItem extends JCheckBoxMenuItem
      implements ActionListener, ItemListener {
      public MyCheckBoxMenuItem(String text) {
         super(text);
         addActionListener(this);
         addItemListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Item clicked: "+e.getActionCommand());
      }
      public void itemStateChanged(ItemEvent e) {
         System.out.println("State changed: "+e.getStateChange()
            +" on "+((MyCheckBoxMenuItem) e.getItem()).getText());
      }
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00164.jpeg)

Check Box Menu Item Listener Test

If you click the "Help" menu item and click menu items in the "Option" menu, you will see some messages printed on the Java console window:

```
 State changed: 1 on Sound
Item clicked: Help
State changed: 1 on Auto save
Item clicked: Auto save
State changed: 2 on Sound
Item clicked: Sound
State changed: 2 on Auto save
Item clicked: Auto save
State changed: 1 on Auto save
Item clicked: Auto save
```

Interesting notes about this tutorial example:

*   I used inner class MyCheckBoxMenuItem to create check box menu items with both ActionListener and ItemListener interfaces implemented in the inner class.
*   "e.getActionCommand()" expression is used to get action command string, the menu item button text in this case.
*   "e.getStateChange()" expression is used to get state changed signal

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟javax.swing.event.MenuKeyListener - Menu Key Listener Interface

This section provides a tutorial example on how to use javax.swing.event.MenuKeyListener, menu key listener interface, to catch events fired by JMenuItem objects when a key is typed on the keyboard.

JMenuItem objects also fire events when users interact with them by typing a key on the keyboard. If you want to perform a task when an event occurs on a JMenuItem object, you need to add an event listener to that JMenuItem object. To do this, you need know these Swing classes, interfaces and methods:

javax.swing.event.MenuKeyListener - A Swing interface that allows you to implement your own menu item event handler methods:

*   menuKeyTyped(MenuKeyEvent) - Event handler method called when a key is typed on a menu item button. You need to implement this method to perform your own task.
*   menuKeyPressed(MenuKeyEvent) - Event handler method called when a key is pressed on a menu item button. You need to implement this method to perform your own task.
*   menuKeyReleased(MenuKeyEvent) - Event handler method called when a key is released on a menu item button. You need to implement this method to perform your own task.

javax.swing.event.MenuKeyEvent - A Swing class that represents an event occurred on a menu item. The most important method in this class is:

*   getSource() - Method returns the JRootPane object where the event occurred. Not very useful.
*   getKeyChar() - Method returns the character represented by the key that triggered event.
*   getKeyCode() - Method returns the code value represented by the key that triggered event.
*   getKeyText() - Method returns the text name of a given key code value.
*   getPath() - Method returns a list of menu objects representing a path in the menu tree. The last object is the JMenuItem object that fired the event.

Here is an example program I wrote to test the MenuKeyListener interface:

```
 /* MenuKeyListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
import javax.swing.event.*;
public class MenuKeyListenerTest implements MenuKeyListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new MenuKeyListenerTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Listener Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      JMenuItem myItem = new JMenuItem("Help");
      myItem.addMenuKeyListener(this);
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myItem.addMenuKeyListener(this);
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myItem.addMenuKeyListener(this);
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem.addMenuKeyListener(this);
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      ButtonGroup myGroup = new ButtonGroup();
      JRadioButtonMenuItem myItem = new JRadioButtonMenuItem("Red");
      myItem.setSelected(true);
      myItem.addMenuKeyListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new JRadioButtonMenuItem("Green");
      myItem.addMenuKeyListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new JRadioButtonMenuItem("Blue");
      myItem.addMenuKeyListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenuItem myItem = new JMenuItem("Sound");
      myItem.addMenuKeyListener(this);
      myMenu.add(myItem);
      myItem = new JMenuItem("Auto save");
      myItem.addMenuKeyListener(this);
      myMenu.add(myItem);
      return myMenu;
   }
   public void menuKeyTyped(MenuKeyEvent e) {
      MenuElement[] path = e.getPath();
      JMenuItem item = (JMenuItem) path[path.length-1];
      System.out.println("Key typed: "+e.getKeyChar()
         + ", "+e.getKeyText(e.getKeyCode())
         + " on "+item.getText());
   }
   public void menuKeyPressed(MenuKeyEvent e) {
      MenuElement[] path = e.getPath();
      JMenuItem item = (JMenuItem) path[path.length-1];
      System.out.println("Key pressed: "+e.getKeyChar()
         + ", "+e.getKeyText(e.getKeyCode())
         + " on "+item.getText());
   }
   public void menuKeyReleased(MenuKeyEvent e) {
      MenuElement[] path = e.getPath();
      JMenuItem item = (JMenuItem) path[path.length-1];
      System.out.println("Key released: "+e.getKeyChar()
         + ", "+e.getKeyText(e.getKeyCode())
         + " on "+item.getText());
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00165.jpeg)

Menu Key Listener Test

If you click the "Color" menu leaving it open, then type the "b" key and the "Shift" key on the keyboard, you will see some messages printed on the Java console window:

```
 Key pressed: b, B on Red
Key pressed: b, B on Green
Key pressed: b, B on Blue
Key pressed: b, B on Help
Key typed: b, Unknown keyCode: 0x0 on Red
Key typed: b, Unknown keyCode: 0x0 on Green
Key typed: b, Unknown keyCode: 0x0 on Blue
Key typed: b, Unknown keyCode: 0x0 on Help
Key released: b, B on Red
Key released: b, B on Green
Key released: b, B on Blue
Key released: b, B on Help
Key pressed: ?, Shift on Red
Key pressed: ?, Shift on Green
Key pressed: ?, Shift on Blue
Key pressed: ?, Shift on Help
Key released: ?, Shift on Red
Key released: ?, Shift on Green
Key released: ?, Shift on Blue
Key released: ?, Shift on Help
```

Interesting notes about this tutorial example:

*   I declared the main class with "public class MenuKeyListenerTest implements MenuKeyListener" to make the main class objects as MenuKeyListener objects.
*   "myItem.addMenuKeyListener(this);" statement is used add the MenuKeyListener to all JMenuItem objects.
*   "JMenuItem item = (JMenuItem) path[path.length-1];" statement is used to get the last object from menu object path provided by the MenuKeyEvent object.
*   When the "b" key was pressed, 4 menu key events were fired, 1 from each menu item that were active on the window at that time. "Red", "Green", and "Bleu" menu items were on the "Color" menu opened by the mouse click. "Help" menu item was listed on the menu bar.
*   When the "b" key was typed, 3 types of menu key events were fired in the order of "key pressed", "key typed" and "key released".
*   The "key typed" event fired by the "b" key can not return a value key code, This is strange.
*   When the "Shift" key is typed, no "key typed" event was fired. This is also strange.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟setMnemonic() - Setting Keyboard Mnemonics on Menu Items

This section provides a tutorial example on how to use setMnemonic() method to associate mnemonics to menu items. Mnemonics allows user to interact with menu items using keys on keyboard.

As you can see from the previous section, it is very hard to use menu key listeners to catch menu key event to support user typed keys on menu items. When one key typed triggers all active menu items to fire menu key events.

Another way to allow users interacting with menu items using keyboard keys is to set mnemonics, keyboard keys, to menu items with the setMnemonic() method. Here is how it works:

1\. Assign difference mnemonics, representing different keys on the keyboard, to different menu items.

2\. Adding an action listener to each menu item.

3\. When a menu item is displayed, the character in the menu text that matches the mnemonic will be underscored.

4\. When a key is pressed on the keyboard, only the menu item that has the mnemonic matching the pressed key will fire an action event.

Here is an example program I wrote to test the setMnemonic() method:

```
 /* JMenuItemSetMnemonicTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JMenuItemSetMnemonicTest 
   implements ActionListener, MenuKeyListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JMenuItemSetMnemonicTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Item Mnemonic Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      JMenuItem myItem = new JMenuItem("Help");
      myItem.setMnemonic(KeyEvent.VK_H);
      myItem.addActionListener(this);
      myItem.addMenuKeyListener(this);
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      ButtonGroup myGroup = new ButtonGroup();

      JRadioButtonMenuItem myItem = new JRadioButtonMenuItem("Red");
      myItem.setSelected(true);
      myItem.setMnemonic(KeyEvent.VK_R);
      myItem.addActionListener(this);
      myItem.addMenuKeyListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);

      myItem = new JRadioButtonMenuItem("Green");
      myItem.setMnemonic(KeyEvent.VK_G);
      myItem.addActionListener(this);
      myItem.addMenuKeyListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);

      myItem = new JRadioButtonMenuItem("Blue");
      myItem.setMnemonic(KeyEvent.VK_B);
      myItem.addActionListener(this);
      myItem.addMenuKeyListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);

      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenuItem myItem = new JMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new JMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      System.out.println("Item clicked: "+e.getActionCommand());
   }
   public void menuKeyTyped(MenuKeyEvent e) {
      MenuElement[] path = e.getPath();
      JMenuItem item = (JMenuItem) path[path.length-1];
      System.out.println("Key typed: "+e.getKeyChar()
         + ", "+e.getKeyText(e.getKeyCode())
         + " on "+item.getText());
   }
   public void menuKeyPressed(MenuKeyEvent e) {
      MenuElement[] path = e.getPath();
      JMenuItem item = (JMenuItem) path[path.length-1];
      System.out.println("Key pressed: "+e.getKeyChar()
         + ", "+e.getKeyText(e.getKeyCode())
         + " on "+item.getText());
   }
   public void menuKeyReleased(MenuKeyEvent e) {
      MenuElement[] path = e.getPath();
      JMenuItem item = (JMenuItem) path[path.length-1];
      System.out.println("Key released: "+e.getKeyChar()
         + ", "+e.getKeyText(e.getKeyCode())
         + " on "+item.getText());
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00166.jpeg)

Menu Item setMnemonic Test (on macOS)

If you click the "Color" menu leaving it open, then type the "b" key. Click the "Color" menu and type the "s" key again. You will see some messages printed on the Java console window:

```
 Key pressed: b, B on Red
Key pressed: b, B on Green
Key pressed: b, B on Blue
Item clicked: Blue
Key pressed: s, S on Red
Key pressed: s, S on Green
Key pressed: s, S on Blue
Key pressed: s, S on Help
Key typed: s, Unknown keyCode: 0x0 on Red
Key typed: s, Unknown keyCode: 0x0 on Green
Key typed: s, Unknown keyCode: 0x0 on Blue
Key typed: s, Unknown keyCode: 0x0 on Help
Key released: s, S on Red
Key released: s, S on Green
Key released: s, S on Blue
Key released: s, S on Help
```

Interesting notes about this tutorial example:

*   I implemented two interfaces on the main class: ActionListener and MenuKeyListener.
*   "myItem.setMnemonic(KeyEvent.VK_*);" statement is used to assign a specific mnemonic to a menu item.
*   When the "b" key was typed, 3 menu key pressed events were fired from "Red", "Green", and "Bleu" menu items. 1 action event was fired from the "Blue" menu item, because "b" matches its mnemonic.
*   When the action event was fired, it stopped key typed and key released events triggered by the "b" key.
*   When the "s" key is typed, no action event was fired, because it did not match any mnemonics defined on menu items.

There seems to be a problem with the setMnemonic() method on macOS computers. It is not adding the underscore sign to the mapped key in the menu item. If you run the same program on a Windows computer, you will see underscore signed displayed as shown below.

![](Images/image00167.jpeg)

Menu Item setMnemonic Test (on Windows)

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟setAccelerator() - Setting Keyboard Accelerators on Menu Items

This section provides a tutorial example on how to use setAccelerator() method to associate accelerators to menu items. Accelerators allows user to interact with menu items using keys on keyboard.

Keyboard mnemonics allows users to invoke a menu item with a single key. But the menu contains that menu item must be popped up first.

For users to invoke a menu item without its menu popped up, we need to assign an accelerator, key combination, to that menu item with the setAccelerator() method. Here is how it works:

1\. Assign difference accelerators, representing different key combinations, to different menu items.

2\. Adding an action listener to each menu item.

3\. When an accelerator, key combination, is pressed at any time, the menu item with the matching accelerator will fire an action event.

Here is an example program I wrote to test the setAccelerator() method:

```
 /* JMenuItemSetAcceleratorTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JMenuItemSetAcceleratorTest implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JMenuItemSetAcceleratorTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Item Accelerator Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      JMenuItem myItem = new JMenuItem("Help");
      myItem.setMnemonic(KeyEvent.VK_H);
      myItem.setAccelerator(
         KeyStroke.getKeyStroke(KeyEvent.VK_P, ActionEvent.CTRL_MASK));
      myItem.addActionListener(this);
      myMenuBar.add(myItem);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      ButtonGroup myGroup = new ButtonGroup();

      JRadioButtonMenuItem myItem = new JRadioButtonMenuItem("Red");
      myItem.setSelected(true);
      myItem.setMnemonic(KeyEvent.VK_R);
      myItem.setAccelerator(
         KeyStroke.getKeyStroke(KeyEvent.VK_D, ActionEvent.CTRL_MASK));
      myItem.addActionListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);

      myItem = new JRadioButtonMenuItem("Green");
      myItem.setMnemonic(KeyEvent.VK_G);
      myItem.setAccelerator(
         KeyStroke.getKeyStroke(KeyEvent.VK_N, ActionEvent.CTRL_MASK));
      myItem.addActionListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);

      myItem = new JRadioButtonMenuItem("Blue");
      myItem.setMnemonic(KeyEvent.VK_B);
      myItem.setAccelerator(
         KeyStroke.getKeyStroke(KeyEvent.VK_E, ActionEvent.CTRL_MASK));
      myItem.addActionListener(this);
      myGroup.add(myItem);
      myMenu.add(myItem);

      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      JMenuItem myItem = new JMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new JMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      System.out.println("Item clicked: "+e.getActionCommand());
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00168.jpeg)

Menu Item setAccelerator Test

Don't open the "Color" menu, and press <Ctrl>-d, <Ctrl>-n and <Ctrl>-e. Then repeat the test with the "Color" menu open. Also try <Ctrl>-p. You will see some messages printed on the Java console window:

```
 Item clicked: Red
Item clicked: Green
Item clicked: Blue
Item clicked: Red
Item clicked: Green
Item clicked: Blue
Item clicked: Help
```

Interesting notes about this tutorial example:

*   I implemented only one interface on the main class: ActionListener.
*   "myItem.setAccelerator( KeyStroke.getKeyStroke( KeyEvent.VK_*, ActionEvent.CTRL_MASK ) );" statement is used to assign a specific accelerator to a menu item.
*   Most GUI applications follow the convention of using <Ctrl> as the modifier key menu item accelerators.
*   When accelerator <Ctrl>-d was pressed, 1 action event was fired from the "Red" menu item, because it has the matching accelerated assigned.
*   The accelerator on the "Help" menu item listed in the menu bar also works correctly.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Menu Bar, Menus, Menu Items and Listeners](#part0052.xhtml)

∟setMnemonic() - Setting Keyboard Mnemonics on Menus

This section provides a tutorial example on how to use setMnemonic() method to associate mnemonics to menus. Mnemonics allows user to interact with menus using keys on keyboard.

Keyboard mnemonics can also be used on menus listed in the menu bar. But they behave differently than mnemonics on menu items.

1\. Assign difference mnemonics, representing different keys on the keyboard, to different menus in the menu bar.

2\. Adding a menu listener to each menu.

3\. The character in the menu text that matches the mnemonic will be underscored.

4\. When a mnemonic key is pressed together with the <Alt> key, the menu that has the mnemonic matching the pressed key will fire a menu event.

Here is an example program I wrote to test the setMnemonic() method on menus in the menu bar:

```
 /* JMenuSetMnemonicTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JMenuSetMnemonicTest implements MenuListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JMenuSetMnemonicTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Menu Mnemonic Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());

      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      myMenu = new JMenu("Help");
      myMenu.setMnemonic(KeyEvent.VK_H);
      myMenu.addMenuListener(this);
      myMenuBar.add(myMenu);

      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      myMenu.setMnemonic(KeyEvent.VK_F);
      myMenu.addMenuListener(this);

      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      ButtonGroup myGroup = new ButtonGroup();
      myMenu.setMnemonic(KeyEvent.VK_C);
      myMenu.addMenuListener(this);

      JRadioButtonMenuItem myItem = new JRadioButtonMenuItem("Red");
      myItem.setSelected(true);
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new JRadioButtonMenuItem("Green");
      myGroup.add(myItem);
      myMenu.add(myItem);
      myItem = new JRadioButtonMenuItem("Blue");
      myGroup.add(myItem);
      myMenu.add(myItem);

      return myMenu;
   }
   private JMenu getOptionMenu() {
      JMenu myMenu = new JMenu("Option");
      myMenu.setMnemonic(KeyEvent.VK_O);
      myMenu.addMenuListener(this);

      JMenuItem myItem = new JMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new JMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   public void menuSelected(MenuEvent e) {
      JMenu myMenu = (JMenu) e.getSource();
      System.out.println("Menu Selected: "+myMenu.getText());
   }
   public void menuDeselected(MenuEvent e) {
      JMenu myMenu = (JMenu) e.getSource();
      System.out.println("Menu deselected: "+myMenu.getText());
   }
   public void menuCanceled(MenuEvent e) {
      JMenu myMenu = (JMenu) e.getSource();
      System.out.println("Menu canceled: "+myMenu.getText());
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00169.jpeg)

Menu setMnemonic Test

If you press <Alt>-f, <Alt>-c, <Alt>-o and <Alt>-h, you will see some messages printed on the Java console window:

```
 Menu Selected: File
Menu deselected: File
Menu Selected: Color
Menu deselected: Color
Menu Selected: Option
Menu deselected: Option
Menu Selected: Help
Menu deselected: Help
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Creating Internal Frames inside the Main Frame

This chapter provides tutorial notes and example codes on internal frames. Topics include quick introduction of the javax.swing.JInternalFrame class and the javax.swing.JInternalFrameListener interface; examples of creating internal frames inside the main frame; examples of adding internal frame listeners.

> [javax.swing.JInternalFame - Internal Frame Class](#part0068.xhtml)
> 
> [JInternalFameTest.java - Internal Frame Class Test](#part0069.xhtml)
> 
> [javax.swing.InternalFrameListener - Internal Frame Listener Interface](#part0070.xhtml)

Conclusion:

*   An object of the javax.swing.JInternalFrame class represents an internal frame inside the main frame.
*   Creating a class to implement the javax.swing.JInternalFrameListener interface allows you to add logics to react to events generated by internal frames.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Creating Internal Frames inside the Main Frame](#part0067.xhtml)

∟javax.swing.JInternalFame - Internal Frame Class

This section describes javax.swing.JInternalFame - Internal Frame Class, representing a UI internal frame inside a regular frame.

javax.swing.JInternalFrame - A Swing class representing a UI internal frame inside a regular frame. An internal frame supports almost all the features a regular frame does. Adding an internal frame to a regular frame should be done by adding the internal frame to a desktop pane first, then using the desktop pane as the content pane of the regular frame. Interesting methods of JInternalFrame include:

*   JInternalFrame(String) - Constructor to create an internal frame with the specified string as the frame title.
*   setResizable(boolean) - Method to set this frame to be resizable or not.
*   setClosable(boolean) - Method to set this frame to be closable or not.
*   setMaximizable(boolean) - Method to set this frame to be maximizable or not.
*   setIconifiable(boolean) - Method to set this frame to be iconifiable or not.
*   setSize(int, int) - Method to set the size of this frame. If not set, an internal frame will have zero size and not visible.
*   setVisible(boolean) - Method to set this frame to be visible or not. The default setting is not visible, you must call setVisible(true) to show an internal frame.
*   addInternalFrameListener(InternalFrameListener) - Method to add internal frame listeners to this internal frame.

javax.swing.JDesktopPane - A Swing class representing a container to host internal frames.

*   getSelectedFrame() - Method to return the selected internal frame.

javax.swing.event.InternalFrameListener - A Swing interface for the implementing class to handle internal frame events. Methods include:

*   internalFrameActivated(InternalFrameEvent) - Method to be called when the internal frame is activated.
*   internalFrameClosed(InternalFrameEvent) - Method to be called when the internal frame has been closed.
*   internalFrameClosing(InternalFrameEvent) - Method to be called when the internal frame is in the process of being closed.
*   internalFrameDeactivated(InternalFrameEvent) - Method to be called when the internal frame is de-activated.
*   internalFrameDeiconified(InternalFrameEvent) - Method to be called when the internal frame is de-iconified.
*   internalFrameIconified(InternalFrameEvent) - Method to be called when the internal frame is iconified.
*   internalFrameOpened(InternalFrameEvent) - Method to be called when the internal frame is opened.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Creating Internal Frames inside the Main Frame](#part0067.xhtml)

∟JInternalFameTest.java - Internal Frame Class Test

This section provides a tutorial example on how to use javax.swing.JInternalFame class to create 2 internal frames in the main frame.

The following program shows you how to create internal frames:

```
 /* JInternalFrameTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class JInternalFrameTest {
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("Internal Frames");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,300);
      JDesktopPane myDesktop = new JDesktopPane();
      myFrame.setContentPane(myDesktop);
      JInternalFrame f = createFrame("Frame 1");
      f.setLocation(10,10);
      myDesktop.add(f);
      f = createFrame("Frame 2");
      f.setLocation(60,60);
      myDesktop.add(f);
      myFrame.setVisible(true);
   }
   private static JInternalFrame createFrame(String t) {
      JInternalFrame f = new JInternalFrame(t);
      f.setResizable(true);
      f.setClosable(true);
      f.setMaximizable(true);
      f.setIconifiable(true);
      f.setSize(200,200);
      f.setVisible(true);
      return f;
   }
}
```

Run this program and you should see two internal frames. You can resize, close, maximize, and minimize the internal frame:

![](Images/image00170.jpeg)

Internal Frame Test

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Creating Internal Frames inside the Main Frame](#part0067.xhtml)

∟javax.swing.InternalFrameListener - Internal Frame Listener Interface

This section provides a tutorial example on how to use javax.swing.JInternalFameListener interface that allows implementing classes to handle internal frame events.

The following program shows you how to create internal frame listeners:

```
 /* JInternalFrameListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JInternalFrameListenerTest 
   implements InternalFrameListener, ActionListener {
   JFrame myFrame = null;
   int count = 0;
   public static void main(String[] a) {
      (new JInternalFrameListenerTest()).test();
   }
   private void test() {
      myFrame = new JFrame("Internal Frame Listener Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,300);
      myFrame.setContentPane(new JDesktopPane());
      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = new JMenu("Frame");
      JMenuItem myMenuItem = new JMenuItem("New");
      myMenuItem.addActionListener(this);
      myMenu.add(myMenuItem);
      myMenuBar.add(myMenu);
      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      count++;
      JInternalFrame f = new JInternalFrame("Frame "+count);
      f.setResizable(true);
      f.setClosable(true);
      f.setMaximizable(true);
      f.setIconifiable(true);
      f.setSize(200,200);
      f.setLocation(count*10,count*10);
      f.addInternalFrameListener(this);
      f.setVisible(true);
      myFrame.getContentPane().add(f);
   }
   public void internalFrameActivated(InternalFrameEvent e) {
      System.out.println("Internal frame activated");
   }
   public void internalFrameClosed(InternalFrameEvent e) {
      System.out.println("Internal frame closed");
   }
   public void internalFrameClosing(InternalFrameEvent e) {
      System.out.println("Internal frame closing");
   }
   public void internalFrameDeactivated(InternalFrameEvent e) {
      System.out.println("Internal frame deactivated");
   }
   public void internalFrameDeiconified(InternalFrameEvent e) {
      System.out.println("Internal frame deiconified");
   }
   public void internalFrameIconified(InternalFrameEvent e) {
      System.out.println("Internal frame iconified");
   }
   public void internalFrameOpened(InternalFrameEvent e) {
      System.out.println("Internal frame opened");
   }
}
```

Run this program, you will see a blank frame with one menu called "Frame". If you:

*   Click "Frame" menu and "New" menu item to create first internal frame.
*   Click "Frame" menu and "New" menu item to create second internal frame.
*   Click the close icon on the first internal frame.
*   Click the maximize icon on the second internal frame.
*   Click the minimize icon on the second internal frame.
*   Click the minimized image of the second internal frame.

you will see the following messages generated from the internal frame listener methods.

```
 Action performed              - Clicked "New" menu item
Internal frame opened
Action performed              - Clicked "New" menu item
Internal frame opened
Internal frame closing        - Clicked the close icon
Internal frame closed
Internal frame activated      - Clicked the maximize icon
Internal frame deactivated    - Clicked the minimize icon
Internal frame iconified
Internal frame activated      - Clicked the minimized image
Internal frame deiconified
```

At the end of the test, the main frame will look like this:

![](Images/image00171.jpeg)

Internal Frame Listener

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Layout of Components in a Container

This chapter provides tutorial notes and example codes on component layout. Topics include introduction of component layout; tutorial examples of BorderLayout, FlowLayout, BoxLayout, GridLayout, and GridBagLayout.

> [What Is Layout?](#part0072.xhtml)
> 
> [java.awt.BorderLayout - Border Layout](#part0073.xhtml)
> 
> [java.awt.FlowLayout - Flow Layout](#part0074.xhtml)
> 
> [java.awt.BoxLayout - Box Layout](#part0075.xhtml)
> 
> [java.awt.GridLayout - Grid Layout](#part0076.xhtml)
> 
> [java.awt.GridBagLayout - Grid Bag Layout](#part0077.xhtml)

Conclusions:

*   A layout is a set of rules that defines how graphical components should be positioned in a container.
*   Java provides 5 built-in layouts: Border, Flow, Box, Grid, and Grid Bag layouts.
*   java.awt.BorderLayout class allows you to manage the Border layout, which displays 5 components in east, south, west, north, and center regions.
*   java.awt.FlowLayout class allows you to manage the Flow layout, which displays unlimited number of components in sequentially in the horizontal direction and wraps around at the right edge of the container.
*   java.awt.BoxLayout class allows you to manage the Box layout, which displays unlimited number of components in sequentially in the horizontal or vertical direction. Components are resized to fit the container width or height.
*   java.awt.GridLayout class allows you to manage the Grid layout, which displays components in cells of rows and columns with width and height. Components are resized to fit cell width and height.
*   java.awt.GridBagLayout class allows you to manage the Grid Bag layout, which displays components in cells of rows and columns. Components are not resized.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Layout of Components in a Container](#part0071.xhtml)

∟What Is Layout?

This section describes AWT layout classes that can be used to layout components in a container. Commonly used layouts are BorderLayout, FlowLayout, BoxLayout, GridLayout, and GridBagLayout.

**What Is Layout?** A layout is a set of rules that defines how graphical components should be positioned in a container.

There two ways to position a component is a container:

*   Using a predefined layout and allowing the layout to decide where to position the component. This is a soft way of positioning a component. If the container changes its size, the component's position will be adjusted. But you may not able to get precisely where you want to component to be.
*   Specifying the position of the component using the container's coordinates. This is a hard way of positioning a component. You can get precisely where you want the component to be. But if the container changes its size, the component's position will not be adjusted.

AWT offers a number of predefined layouts for you to use:

*   java.awt.BorderLayout - Divides the container into five regions: east, south, west, north, and center and assigns one component for each region.
*   java.awt.FlowLayout - Takes unlimited number of components and let them flow naturally horizontally first, then vertically.
*   java.awt.BoxLayout - Takes unlimited number of components and let them flow horizontally or vertically in one direction.
*   java.awt.GridLayout - Divides the container into rows and columns and assigns one component for each cell.
*   java.awt.GridBagLayout - Divides the container into rows and columns and assigns one component for each cell with cell sizes not equal.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Layout of Components in a Container](#part0071.xhtml)

∟java.awt.BorderLayout - Border Layout

This section provides a tutorial example on how to create a BorderLayout to layout components in a container. BorderLayout has 5 fixed sections - north, south, west, east and center.

**java.awt.BorderLayout** - A very simple layout that:

*   Divides the container into five regions: east, south, west, north, and center.
*   Takes maximum 5 components only, one per region.
*   Resizes each component to match the size of its region.
*   Acts as the default layout in a container.
*   Resizes each region when the container is resized.

Here is an example program I wrote to test the BorderLayout:

```
 /* BorderLayoutTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class BorderLayoutTest {
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("FlowLayout Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();

      myPane.setLayout(new BorderLayout());
      myPane.add(new JButton("North"), BorderLayout.NORTH);
      myPane.add(new JButton("South"), BorderLayout.SOUTH);
      myPane.add(new JButton("East"), BorderLayout.EAST);
      myPane.add(new JButton("West"), BorderLayout.WEST);
      myPane.add(new JButton(new ImageIcon("java.gif")), 
         BorderLayout.CENTER);
      myFrame.pack();
      myFrame.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00172.jpeg)

Layout - BorderLayout

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Layout of Components in a Container](#part0071.xhtml)

∟java.awt.FlowLayout - Flow Layout

This section provides a tutorial example on how to create a FlowLayout to layout components in a container. FlowLayout can have many elements arranged horizontally first, then vertically.

**java.awt.FlowLayout** - Another very simple layout that:

*   Takes unlimited number of components.
*   Uses the default size of each component.
*   Positions each component next to each other in a row. If there is not enough room in the current row, the component will be positioned at the beginning of the next row.
*   Re-arranges the flow when the container is resized.

I don't see any potential use of this layout. But I am interested to see how it re-arranges the flow when the container is resized. So I decided to use FlowLayout to layout a window of several different types of components. I wanted the window to look like this:

```
 - Details ----------------
|     Name: Text         |
|   System: Radio button |
| Language: Check box    |
|     Year: Dropdown     |
--------------------------
        OK  Cancel
```

Here is an example program I wrote to do this with FlowLayout:

```
 /* FlowLayoutTest2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class FlowLayoutTest2 {
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("FlowLayout Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new FlowLayout(FlowLayout.CENTER));
      myPane.add(getFieldPanel());
      myPane.add(getButtonPanel());
      myFrame.pack();
      myFrame.setVisible(true);
   }
   private static JPanel getFieldPanel() {
      JPanel p = new JPanel(new FlowLayout());
      p.setBorder(BorderFactory.createTitledBorder("Details"));
      p.add(new JLabel("Name:"));
      p.add(new JTextField(16));
      p.add(new JLabel("System:"));
      p.add(getSystemPanel());
      p.add(new JLabel("Language:"));
      p.add(getLanguagePanel());
      p.add(new JLabel("Year:"));
      p.add(new JComboBox<String>(
         new String[] {"2021","2022","2023"}));
      return p;
   }
   private static JPanel getButtonPanel() {
      JPanel p = new JPanel(new FlowLayout());
      p.add(new JButton("OK"));
      p.add(new JButton("Cancel"));
      return p;
   }
   private static JPanel getSystemPanel() {
      JRadioButton unixButton = new JRadioButton("Unix",true);
      JRadioButton winButton = new JRadioButton("Window",false);
      ButtonGroup systemGroup = new ButtonGroup();
      systemGroup.add(unixButton);
      systemGroup.add(winButton);
      JPanel p = new JPanel(new FlowLayout());
      p.add(unixButton);
      p.add(winButton);
      return p;
   }
   private static JPanel getLanguagePanel() {
      JPanel p = new JPanel(new FlowLayout());
      p.add(new JCheckBox("Java",true));
      p.add(new JCheckBox("C++",true));
      p.add(new JCheckBox("Perl",false));
      return p;
   }
}
```

Run it. What do you think about the result? Pretty bad, right?

![](Images/image00173.jpeg)

Layout - FlowLayout

Initially all components are positioned in a single row. If you narrow the window, "OK" and "Cancel" buttons will be wrapped to the next row. If you narrow it further, no change will happen on positions. Because the top container, the window, really contains only two components: the field panel and the button panel.

So, FlowLayout is not good for my example.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Layout of Components in a Container](#part0071.xhtml)

∟java.awt.BoxLayout - Box Layout

This section provides a tutorial example on how to create a BoxLayout to layout components in a container. BoxLayout can have many elements arranged in one direction only: horizontally or vertically.

**java.awt.BoxLayout** - A layout that:

*   Takes unlimited number of components.
*   Positions each component next to each other only in one direction, horizontal or vertical.
*   Resizes components that are resizable to fill entire container.
*   Resizes components that are resizable when the container is resized.

To test BoxLayout, I wrote another program to try to display my window with BoxLayout:

```
 /* BoxLayoutTest2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class BoxLayoutTest2 {
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("BoxLayout Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new BoxLayout(myPane,BoxLayout.Y_AXIS));
      myPane.add(getFieldPanel());
      myPane.add(getButtonPanel());
      myFrame.pack();
      myFrame.setVisible(true);
   }
   private static JPanel getFieldPanel() {
      JPanel p = new JPanel();
      p.setLayout(new BoxLayout(p,BoxLayout.X_AXIS));
      p.setBorder(BorderFactory.createTitledBorder("Details"));
      p.add(getLabelPanel());
      p.add(getValuePanel());
      return p;
   }
   private static JPanel getButtonPanel() {
      JPanel p = new JPanel();
      p.setLayout(new BoxLayout(p,BoxLayout.X_AXIS));
      p.add(new JButton("OK"));
      p.add(new JButton("Cancel"));
      return p;
   }
   private static JPanel getLabelPanel() {
      JPanel p = new JPanel();
      p.setLayout(new BoxLayout(p,BoxLayout.Y_AXIS));
      JLabel l = new JLabel("Name:");
      l.setAlignmentX(Component.RIGHT_ALIGNMENT);
      p.add(l);
      l = new JLabel("System:");
      l.setAlignmentX(Component.RIGHT_ALIGNMENT);
      p.add(l);
      l = new JLabel("Language:");
      l.setAlignmentX(Component.RIGHT_ALIGNMENT);
      p.add(l);
      l = new JLabel("Year:");
      l.setAlignmentX(Component.RIGHT_ALIGNMENT);
      p.add(l);
      return p;
   }
   private static JPanel getValuePanel() {
      JPanel p = new JPanel();
      p.setLayout(new BoxLayout(p,BoxLayout.Y_AXIS));
      JComponent c = new JTextField(16);
      c.setAlignmentX(Component.LEFT_ALIGNMENT);
      p.add(c);
      JPanel s = getSystemPanel();
      s.setAlignmentX(Component.LEFT_ALIGNMENT);
      p.add(s);
      s = getLanguagePanel();
      s.setAlignmentX(Component.LEFT_ALIGNMENT);
      p.add(s);
      JComboBox<String> b = new JComboBox<String>(
         new String[] {"2021","2022","2023"});
      b.setAlignmentX(Component.LEFT_ALIGNMENT);
      p.add(b);
      return p;
   }
   private static JPanel getSystemPanel() {
      JRadioButton unixButton = new JRadioButton("Unix",true);
      JRadioButton winButton = new JRadioButton("Window",false);
      ButtonGroup systemGroup = new ButtonGroup();
      systemGroup.add(unixButton);
      systemGroup.add(winButton);
      JPanel p = new JPanel();
      p.setLayout(new BoxLayout(p,BoxLayout.X_AXIS));
      p.add(unixButton);
      p.add(winButton);
      return p;
   }
   private static JPanel getLanguagePanel() {
      JPanel p = new JPanel();
      p.setLayout(new BoxLayout(p,BoxLayout.X_AXIS));
      p.add(new JCheckBox("Java",true));
      p.add(new JCheckBox("C++",true));
      p.add(new JCheckBox("Perl",false));
      return p;
   }
}
```

Run it. What do you think about the result? Much better, right?

![](Images/image00174.jpeg)

Layout - BoxLayout

But if you look closely, value components are not aligned to the corresponding label components. It is almost impossible to align them, because they are in two different panels.

So, BoxLayout is still not good for my example.

Another question about BoxLayout is why the constructor needs to take the container as input. Constructors of other layouts do not need containers. This makes the statement looks very strange: p.setLayout(new BoxLayout(p,...)).

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Layout of Components in a Container](#part0071.xhtml)

∟java.awt.GridLayout - Grid Layout

This section provides a tutorial example on how to create a GridLayout to layout components in a container. GridLayout can have many elements arranged in predefined rows and columns.

**java.awt.GridLayout** - A layout that:

*   Divides the container into rows and columns. The number of rows and the number of columns are configurable. Rows and columns are equally divided.
*   Places components into the specified cells.
*   Resizes each component to match the size of its cell.
*   Resizes all components when the container is resized.

Again, I wrote another program to try to display my window with GridLayout:

```
 /* GridLayoutTest2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class GridLayoutTest2 {
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("GridLayout Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new GridLayout(2,1));
      myPane.add(getFieldPanel());
      myPane.add(getButtonPanel());
      myFrame.pack();
      myFrame.setVisible(true);
   }
   private static JPanel getFieldPanel() {
      JPanel p = new JPanel(new GridLayout(4,2));
      p.setBorder(BorderFactory.createTitledBorder("Details"));
      p.add(new JLabel("Name:",SwingConstants.RIGHT));
      p.add(new JTextField(16));
      p.add(new JLabel("System:",SwingConstants.RIGHT));
      p.add(getSystemPanel());
      p.add(new JLabel("Language:",SwingConstants.RIGHT));
      p.add(getLanguagePanel());
      p.add(new JLabel("Year:",SwingConstants.RIGHT));
      p.add(new JComboBox<String>(
         new String[] {"2021","2022","2023"}));
      return p;
   }
   private static JPanel getButtonPanel() {
      JPanel p = new JPanel(new GridLayout(1,2));
      p.add(new JButton("OK"));
      p.add(new JButton("Cancel"));
      return p;
   }
   private static JPanel getSystemPanel() {
      JRadioButton unixButton = new JRadioButton("Unix",true);
      JRadioButton winButton = new JRadioButton("Window",false);
      ButtonGroup systemGroup = new ButtonGroup();
      systemGroup.add(unixButton);
      systemGroup.add(winButton);
      JPanel p = new JPanel(new GridLayout(1,2));
      p.add(unixButton);
      p.add(winButton);
      return p;
   }
   private static JPanel getLanguagePanel() {
      JPanel p = new JPanel(new GridLayout(1,3));
      p.add(new JCheckBox("Java",true));
      p.add(new JCheckBox("C++",true));
      p.add(new JCheckBox("Perl",false));
      return p;
   }
}
```

Run it. What do you think about the result? You don't like it, right?

![](Images/image00175.jpeg)

Layout - GridLayout

All components are aligned correctly in both directions now. But all components are having wrong sizes.

So, GridLayout is still not good for my example.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Layout of Components in a Container](#part0071.xhtml)

∟java.awt.GridBagLayout - Grid Bag Layout

This section provides a tutorial example on how to create a GridBagLayout to layout components in a container. GridBagLayout can have many elements arranged in predefined rows and columns with non-equal sizes.

**java.awt.GridBagLayout** - A more complex layout that:

*   Divides the container into rows and columns. The number of rows and the number of columns are unlimited. Rows and columns are not equally divided.
*   Places components into the specified cells.
*   Uses the default size of each component.
*   Keeps component sizes unchanged when the container is resized.
*   Provides individual layout constraints for each component to control its layout behavior.

Once again, I wrote another program to try to display my window with GridBagLayout:

```
 /* GridBagLayoutTest2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class GridBagLayoutTest2 {
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("GridBagLayout Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new GridBagLayout());
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.CENTER);
      myPane.add(getFieldPanel(),c);
      setMyConstraints(c,0,1,GridBagConstraints.CENTER);
      myPane.add(getButtonPanel(),c);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   private static JPanel getFieldPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.setBorder(BorderFactory.createTitledBorder("Details"));
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.EAST);
      p.add(new JLabel("Name:"),c);
      setMyConstraints(c,1,0,GridBagConstraints.WEST);
      p.add(new JTextField(16),c);
      setMyConstraints(c,0,1,GridBagConstraints.EAST);
      p.add(new JLabel("System:"),c);
      setMyConstraints(c,1,1,GridBagConstraints.WEST);
      p.add(getSystemPanel(),c);
      setMyConstraints(c,0,2,GridBagConstraints.EAST);
      p.add(new JLabel("Language:"),c);
      setMyConstraints(c,1,2,GridBagConstraints.WEST);
      p.add(getLanguagePanel(),c);
      setMyConstraints(c,0,3,GridBagConstraints.EAST);
      p.add(new JLabel("Year:"),c);
      setMyConstraints(c,1,3,GridBagConstraints.WEST);
      p.add(new JComboBox<String>(
         new String[] {"2021","2022","2023"}),c);
      return p;
   }
   private static JPanel getButtonPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.add(new JButton("OK"));
      p.add(new JButton("Cancel"));
      return p;
   }
   private static JPanel getSystemPanel() {
      JRadioButton unixButton = new JRadioButton("Unix",true);
      JRadioButton winButton = new JRadioButton("Window",false);
      ButtonGroup systemGroup = new ButtonGroup();
      systemGroup.add(unixButton);
      systemGroup.add(winButton);
      JPanel p = new JPanel(new GridBagLayout());
      p.add(unixButton);
      p.add(winButton);
      return p;
   }
   private static JPanel getLanguagePanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.add(new JCheckBox("Java",true));
      p.add(new JCheckBox("C++",true));
      p.add(new JCheckBox("Perl",false));
      return p;
   }
   private static void setMyConstraints(GridBagConstraints c, 
      int gridx, int gridy, int anchor) {
      c.gridx = gridx;
      c.gridy = gridy;
      c.anchor = anchor;
   }
}
```

Run it. What do you think about the result? Almost perfect, right?

![](Images/image00176.jpeg)

Layout - GridBagLayout

All components are aligned correctly in both directions now. And all components are properly sized.

GridBagLayout seems to be good enough for my example.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟LookAndFeel and UIManager

This chapter provides tutorial notes and example codes on UI look and feel. Topics include introduction of javax.swing.LookAndFeel and javax.swing.UIManager classes; example programs on how to manage UI look and feel.

**javax.swing.LookAndFeel** - A Swing class representing a set of rules that define how each type of graphical components should look and feel.

**javax.swing.UIManager** - A Swing class managing the current LookAndFeel.

To find out which LookAndFeel is available on your local system, and to switch from one LookAndFeel to another, I wrote the following sample program:

```
 /* LookAndFeelTest2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import javax.swing.*;
public class LookAndFeelTest2 {
   public static void main(String[] a) {
      try {
         showFrame("Default LookAndFeel", 1);
         String cn = UIManager.getSystemLookAndFeelClassName();
         UIManager.setLookAndFeel(cn);
         showFrame("System LookAndFeel", 2);
         cn = UIManager.getCrossPlatformLookAndFeelClassName();
         UIManager.setLookAndFeel(cn);
         showFrame("Cross Platform LookAndFeel", 3);
         cn = "com.sun.java.swing.plaf.motif.MotifLookAndFeel";
         UIManager.setLookAndFeel(cn);
         showFrame("Motif LookAndFeel", 4);
      } catch (Exception e) {
         System.out.println("Exception: "+e);
      }
   }
   private static void showFrame(String t, int i) {
      LookAndFeel laf = UIManager.getLookAndFeel();
      JFrame myFrame = new JFrame(i+". "+t+": "+laf.getName());
      myFrame.setBounds(50*i,50*i,0,0);
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new GridBagLayout());
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.CENTER);
      myPane.add(getFieldPanel(),c);
      setMyConstraints(c,0,1,GridBagConstraints.CENTER);
      myPane.add(getButtonPanel(),c);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   private static JPanel getFieldPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.setBorder(BorderFactory.createTitledBorder("Details"));
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.EAST);
      p.add(new JLabel("Name:"),c);
      setMyConstraints(c,1,0,GridBagConstraints.WEST);
      p.add(new JTextField(16),c);
      setMyConstraints(c,0,1,GridBagConstraints.EAST);
      p.add(new JLabel("System:"),c);
      setMyConstraints(c,1,1,GridBagConstraints.WEST);
      p.add(getSystemPanel(),c);
      setMyConstraints(c,0,2,GridBagConstraints.EAST);
      p.add(new JLabel("Language:"),c);
      setMyConstraints(c,1,2,GridBagConstraints.WEST);
      p.add(getLanguagePanel(),c);
      setMyConstraints(c,0,3,GridBagConstraints.EAST);
      p.add(new JLabel("Year:"),c);
      setMyConstraints(c,1,3,GridBagConstraints.WEST);
      p.add(new JComboBox<String>(
         new String[] {"2021","2022","2023"}),c);
      return p;
   }
   private static JPanel getButtonPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.add(new JButton("OK"));
      p.add(new JButton("Cancel"));
      return p;
   }
   private static JPanel getSystemPanel() {
      JRadioButton unixButton = new JRadioButton("Unix",true);
      JRadioButton winButton = new JRadioButton("Window",false);
      ButtonGroup systemGroup = new ButtonGroup();
      systemGroup.add(unixButton);
      systemGroup.add(winButton);
      JPanel p = new JPanel(new GridBagLayout());
      p.add(unixButton);
      p.add(winButton);
      return p;
   }
   private static JPanel getLanguagePanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.add(new JCheckBox("Java",true));
      p.add(new JCheckBox("C++",true));
      p.add(new JCheckBox("Perl",false));
      return p;
   }
   private static void setMyConstraints(GridBagConstraints c, 
      int gridx, int gridy, int anchor) {
      c.gridx = gridx;
      c.gridy = gridy;
      c.anchor = anchor;
   }
}
```

Run it. You should get 4 windows, representing the JDK default LookAndFeel, the local system default LookAndFeel, cross platform LookAndFeel, and the Motif LookAndFeel.

![](Images/image00177.jpeg)

LookAndFeel and UIManager

As you can see, the JDK default LookAndFeel is called Metal, which is also the cross platform LookAndFeel.

Sample programs listed in this tutorial have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Option Dialog Boxes

This chapter provides tutorial notes and example codes on option dialog box. Topics include creating and displaying message, confirmation, input and option dialog boxes; receiving input values from option dialog boxes; creating and display internal dialog boxes; creating option dialog box directly.

> [javax.swing.JOptionPane - Creating and Displaying Option Dialog Boxes](#part0080.xhtml)
> 
> [showMessageDialog() - Displaying Message Dialog Boxes](#part0081.xhtml)
> 
> [showConfirmDialog() - Displaying Confirmation Dialog Boxes](#part0082.xhtml)
> 
> [Receiving Inputs from Confirmation Dialog Boxes](#part0083.xhtml)
> 
> [showInputDialog() - Displaying Input Dialog Boxes](#part0084.xhtml)
> 
> [showOptionDialog() - Displaying Option Dialog Boxes](#part0085.xhtml)
> 
> [showInternal*Dialog() - Displaying Internal Dialog Boxes](#part0086.xhtml)
> 
> [createDialog() - Creating Dialog Boxes Directly](#part0087.xhtml)

Conclusions:

*   javax.swing.JOptionPane class can be used to display different types of simple dialog boxes with showMessageDialog(), showConfirmDialog(), showInputDialog(), and showOptionDialog() methods.
*   showMessageDialog() method displays a dialog box with a text message only.
*   showConfirmDialog() method displays a dialog box with a text message and prompts for a confirmation button click from the user.
*   showInputDialog() method displays a dialog box with a text message only and prompts for the user to enter a text input.
*   showOptionDialog() method displays a dialog box with a list of options for the user to select.
*   By default, dialog boxes are created as standalone windows floating outside the parent panel. If you want to create dialog boxes restricted inside the parent panel, you need to use showInternal*Dialog() methods.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟javax.swing.JOptionPane - Creating and Displaying Option Dialog Boxes

This section describes some static methods in the JOptionPane class that can be used to create and display different types of option dialog boxes.

javax.swing.JOptionPane - A Swing class that allows you to create and display option dialog boxes. Interesting methods of JOptionPane include:

*   showMessageDialog() - Method to create and display a message dialog box to present regular, warning or error messages.
*   showConfirmDialog() - Method to create and display a confirmation dialog box with yes, no and cancel buttons.
*   showInputDialog() - Method to create and display an input dialog box to prompt for some input.
*   showOptionDialog() - Method to create and display a generic dialog box to present message, take a confirmation, or take some input.
*   showInternal*Dialog() - Methods to create and display internal dialog boxes, displayed inside the main frame.

All dialog boxes created with the JOptionPane class are modal, disabling all other user interface components on other frames. Each call of show*Dialog() method blocks the execution until the dialog box is closed.

All dialog boxes must be created with parent frame.

The message type of an option dialog box controls the icon used on the left side of the message text.

The option type of an option dialog box controls what option buttons to be displayed.

The option buttons can be customized with your own option strings.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟showMessageDialog() - Displaying Message Dialog Boxes

This section provides a tutorial example on how to use the static method, showMessageDialog(), to create and display message dialog boxes for 4 different type of messages: information, warning, error, and plain.

The simplest dialog box you can create and display with the javax.swing.JOptionPane class is the message dialog box. This can be done with the static method: showMessageDialog(frame, message, title, type), where:

*   "frame" is a frame object to be used as the parent frame.
*   "message" is the message string to be display on the dialog box.
*   "title" is the title string to be used as the dialog box title.
*   "type" is an integer code representing a specific message dialog box type. Valid type codes are predefined as constants in the JOptionPane class: INFORMATION_MESSAGE, WARNING_MESSAGE, ERROR_MESSAGE and PLAIN_MESSAGE.

Here is an example program I wrote to test the showMessageDialog() method:

```
 /* JOptionPaneShowMessageDialog.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneShowMessageDialog implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JOptionPaneShowMessageDialog()).test();
   }
   private void test() {
      myFrame = new JFrame("showMessageDialog Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setBounds(50,50,250,150);
      myFrame.setContentPane(new JDesktopPane());
      JMenuBar myMenuBar = new JMenuBar();
      JMenu myMenu = getDialogMenu();
      myMenuBar.add(myMenu);
      myFrame.setJMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private JMenu getDialogMenu() {
      JMenu myMenu = new JMenu("Dialogs");
      JMenuItem myItem = new JMenuItem("Information");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      myItem = new JMenuItem("Warning");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      myItem = new JMenuItem("Error");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      myItem = new JMenuItem("Plain");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      String menuText = ((JMenuItem) e.getSource()).getText();
      int messageType = JOptionPane.INFORMATION_MESSAGE;
      if (menuText.equals("Information")) {
         messageType = JOptionPane.INFORMATION_MESSAGE;
      } else if (menuText.equals("Warning")) {
         messageType = JOptionPane.WARNING_MESSAGE;
      } else if (menuText.equals("Error")) {
         messageType = JOptionPane.ERROR_MESSAGE;
      } else if (menuText.equals("Plain")) {
         messageType = JOptionPane.PLAIN_MESSAGE;
      }

      System.out.println("Before displaying the dialog: "+menuText);
      JOptionPane.showMessageDialog(myFrame, 
         "This is message dialog box of type: "+menuText,
         menuText+" Message", messageType);
      System.out.println("After displaying the dialog: "+menuText);
   }
}
```

If you run this example, open the "Dialogs" menu, and click "Information", "Warning" or "Error" menu item, you will see a message dialog box showing up like this:

![](Images/image00178.jpeg)

Message Dialog Box

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟showConfirmDialog() - Displaying Confirmation Dialog Boxes

This section provides a tutorial example on how to use the static method, showConfirmDialog(), to create and display confirmation dialog boxes for 3 different types of options and 4 different types of messages: information, warning, error, and plain.

The second type of dialog boxes you can create and display with the javax.swing.JOptionPane class is the confirmation dialog box. This can be done with the static method: showConfirmDialog(frame, message, title, option, type), where:

*   "frame" is a frame object to be used as the parent frame.
*   "message" is the message string to be display on the dialog box.
*   "title" is the title string to be used as the dialog box title.
*   "option" is an integer code representing a specific confirmation option type. Valid type codes are predefined as constants in the JOptionPane class: YES_NO_OPTION, YES_NO_CANCEL_OPTION, and OK_CANCEL_OPTION.
*   "type" is an integer code representing a specific message dialog box type. Valid type codes are predefined as constants in the JOptionPane class: INFORMATION_MESSAGE, WARNING_MESSAGE, ERROR_MESSAGE and PLAIN_MESSAGE.

Here is an example program I wrote to test the showConfirmDialog() method:

```
 /* JOptionPaneShowConfirmDialog.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneShowConfirmDialog implements ActionListener {
   JFrame myFrame = null;
   int optionType = JOptionPane.YES_NO_OPTION;
   int messageType = JOptionPane.INFORMATION_MESSAGE;
   public static void main(String[] a) {
      (new JOptionPaneShowConfirmDialog()).test();
   }
   private void test() {
      myFrame = new JFrame("showConfirmDialog() Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new GridBagLayout());
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.CENTER);
      myPane.add(getFieldPanel(),c);
      setMyConstraints(c,0,1,GridBagConstraints.CENTER);
      myPane.add(getButtonPanel(),c);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   private JPanel getFieldPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.setBorder(BorderFactory.createTitledBorder("Settings"));
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.EAST);
      p.add(new JLabel("Option Type:"),c);
      setMyConstraints(c,1,0,GridBagConstraints.WEST);
      p.add(getOptionPanel(),c);
      setMyConstraints(c,0,1,GridBagConstraints.EAST);
      p.add(new JLabel("Message type:"),c);
      setMyConstraints(c,1,1,GridBagConstraints.WEST);
      p.add(getMessagePanel(),c);
      return p;
   }
   private JPanel getOptionPanel() {
      JPanel myPanel = new JPanel(new GridBagLayout());
      ButtonGroup myGroup = new ButtonGroup();
      JRadioButton myButton = new JRadioButton("Yes-No",true);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);

      myButton = new JRadioButton("Yes-No-Cancel",false);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);

      myButton = new JRadioButton("Ok-Cancel",false);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);
      return myPanel;
   }
   private JPanel getMessagePanel() {
      JPanel myPanel = new JPanel(new GridBagLayout());
      ButtonGroup myGroup = new ButtonGroup();
      JRadioButton myButton = new JRadioButton("Information",true);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);

      myButton = new JRadioButton("Warning",false);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);

      myButton = new JRadioButton("Error",false);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);

      myButton = new JRadioButton("Plain",false);
      myButton.addActionListener(this);
      myGroup.add(myButton);
      myPanel.add(myButton);
      return myPanel;
   }
   private JPanel getButtonPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      JButton myButton = new JButton("Show");
      myButton.addActionListener(this);
      p.add(myButton);
      return p;
   }
   public void actionPerformed(ActionEvent e) {
      String cmd = ((AbstractButton) e.getSource()).getText();
      System.out.println("Button clicked: "+cmd);
      if (cmd.equals("Information")) {
         messageType = JOptionPane.INFORMATION_MESSAGE;
      } else if (cmd.equals("Warning")) {
         messageType = JOptionPane.WARNING_MESSAGE;
      } else if (cmd.equals("Error")) {
         messageType = JOptionPane.ERROR_MESSAGE;
      } else if (cmd.equals("Plain")) {
         messageType = JOptionPane.PLAIN_MESSAGE;
      } else if (cmd.equals("Yes-No")) {
         optionType = JOptionPane.YES_NO_OPTION;
      } else if (cmd.equals("Yes-No-Cancel")) {
         optionType = JOptionPane.YES_NO_CANCEL_OPTION;
      } else if (cmd.equals("Ok-Cancel")) {
         optionType = JOptionPane.OK_CANCEL_OPTION;
      } else if (cmd.equals("Show")) {
         JOptionPane.showConfirmDialog(myFrame, 
         "Confirmation dialog box text message.", 
         "Confirmation Dialog Box", optionType, messageType);
      }
   }
   private void setMyConstraints(GridBagConstraints c, 
      int gridx, int gridy, int anchor) {
      c.gridx = gridx;
      c.gridy = gridy;
      c.anchor = anchor;
   }
}
```

If you run this example, select an option type and a message type, then click the "Show" button, you will see a confirmation dialog box showing up like this:

![](Images/image00179.jpeg)

Confirm Dialog Box

Interesting notes about this tutorial example:

*   I used several panels and layouts to organize the settings area.
*   An action listener has been added to all radio buttons and the "Show" button.
*   The actionPerformed() method in the action listener is implemented to handle all changes.
*   What is missing in this example is how to catch input on option buttons on the confirmation dialog box.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟Receiving Inputs from Confirmation Dialog Boxes

This section provides a tutorial example on how to use the static method, showConfirmDialog(), to create and display confirmation dialog boxes and receive input code to know which button was clicked by the user.

In the previous tutorial example, when users click the one of the option buttons like Ok, Yes, No or Cancel on confirmation dialog boxes, the showConfirmDialog() method will actually returns an integer code representing the clicked button. Valid type codes are predefined as constants in the JOptionPane class:

*   JOptionPane.OK_OPTION - User clicked the Ok button.
*   JOptionPane.YES_OPTION - User clicked the Yes button.
*   JOptionPane.NO_OPTION - User clicked the No button.
*   JOptionPane.CANCEL_OPTION - User clicked the Cancel button.
*   JOptionPane.CLOSED_OPTION - User closed the confirmation dialog box.

Here is an example program I wrote to test the returned integer code of showConfirmDialog():

```
 /* JOptionPaneConfirmDialogInput.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneConfirmDialogInput implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JOptionPaneConfirmDialogInput()).test();
   }
   private void test() {
      myFrame = new JFrame("showConfirmDialog() Input Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      JButton myButton = new JButton("Show");
      myButton.addActionListener(this);
      myPane.add(myButton);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      int messageType = JOptionPane.INFORMATION_MESSAGE;
      int optionType = JOptionPane.YES_NO_CANCEL_OPTION;
      int code = JOptionPane.showConfirmDialog(myFrame, 
         "Do you want to continue?", 
         "Confirmation Dialog Box", optionType, messageType);

      String answer = "Unknown";
      if (code == JOptionPane.OK_OPTION) {
         answer = "Ok";
      } else if (code == JOptionPane.YES_OPTION) {
         answer = "Yes";
      } else if (code == JOptionPane.NO_OPTION) {
         answer = "No";
      } else if (code == JOptionPane.CANCEL_OPTION) {
         answer = "Cancel";
      } else if (code == JOptionPane.CLOSED_OPTION) {
         answer = "Closed";
      }
      System.out.println("Answer: "+answer);
   }
}
```

If you run this example, and click the Show button, you will see a confirmation dialog box showing up like this:

![](Images/image00180.jpeg)

Congirmation Dialog Box Input

Click the Yes button on the confirmation dialog box. Click the Show button on the main frame window, then the No button on the confirmation dialog box again. Repeat the test with the Cancel button and the close dialog box icon. You will see some messages printed on the Java console window:

```
 Answer: Ok
Answer: No
Answer: Cancel
Answer: Closed
```

Interesting notes about this tutorial example:

*   The returned code of the Yes button is JOptionPane.OK_OPTION, not JOptionPane.YES_OPTION. I don't know why.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟showInputDialog() - Displaying Input Dialog Boxes

This section provides a tutorial example on how to use the static method, showInputDialog(), to create and display input dialog boxes to take text string input from the user.

The third type of dialog boxes you can create and display with the javax.swing.JOptionPane class is the input dialog box. This can be done with the static method: answer = showInputDialog(frame, message, title, type), where:

*   "frame" is a frame object to be used as the parent frame.
*   "message" is the message string to be display on the dialog box.
*   "title" is the title string to be used as the dialog box title.
*   "type" is an integer code representing a specific message dialog box type. Valid type codes are predefined as constants in the JOptionPane class: INFORMATION_MESSAGE, WARNING_MESSAGE, ERROR_MESSAGE and PLAIN_MESSAGE.
*   "answer" is the returned string entered by the user on the input dialog box. If no input entered, null will be returned.

Here is an example program I wrote to test the showInputDialog() method:

```
 /* JOptionPaneInputDialog.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneInputDialog implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JOptionPaneInputDialog()).test();
   }
   private void test() {
      myFrame = new JFrame("showInputDialog() Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      JButton myButton = new JButton("Show");
      myButton.addActionListener(this);
      myPane.add(myButton);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      int messageType = JOptionPane.INFORMATION_MESSAGE;
      String answer = JOptionPane.showInputDialog(myFrame, 
         "What's you name?", 
         "Input Dialog Box", messageType);
      System.out.println("Answer: "+answer);
   }
}
```

If you run this example, and click the Show button, you will see an input dialog box showing up like this:

![](Images/image00181.jpeg)

Congirmation Dialog Box Input

Enter "Herong Yang" in the input field on the input dialog box and click OK. Repeat the test with the Cancel button and the close dialog box icon. You will see some messages printed on the Java console window:

```
 Answer: Herong Yang
Answer: null
Answer: null
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟showOptionDialog() - Displaying Option Dialog Boxes

This section provides a tutorial example on how to use the static method, showInputDialog(), to create and display input dialog boxes to take text string input from the user.

The fourth type of dialog boxes you can create and display with the javax.swing.JOptionPane class is the option dialog box. This can be done with the static method: answer = showOptionDialog(frame, message, title, 0, type, icon, options, default), where:

*   "frame" is a frame object to be used as the parent frame.
*   "message" is the message string to be display on the dialog box.
*   "title" is the title string to be used as the dialog box title.
*   "0" is an place holder for an integer code representing a specific confirmation option type. Valid type codes are predefined as constants in the JOptionPane class: YES_NO_OPTION, YES_NO_CANCEL_OPTION, and OK_CANCEL_OPTION. But this parameter has no impact on the result.
*   "type" is an integer code representing a specific message dialog box type. Valid type codes are predefined as constants in the JOptionPane class: INFORMATION_MESSAGE, WARNING_MESSAGE, ERROR_MESSAGE and PLAIN_MESSAGE.
*   "icon" is an image object to be displayed as the message icon.
*   "options" is an array of strings representing different options for the user to select.
*   "default" is the default string to be pre-selected on the option dialog box.
*   "answer" is the returned integer index of the "options" array representing the option string selected by the user.

Here is an example program I wrote to test the showOptionDialog() method:

```
 /* JOptionPaneOptionDialog.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneOptionDialog implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JOptionPaneOptionDialog()).test();
   }
   private void test() {
      myFrame = new JFrame("showOptionDialog() Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      JButton myButton = new JButton("Show");
      myButton.addActionListener(this);
      myPane.add(myButton);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      int messageType = JOptionPane.QUESTION_MESSAGE;
      String[] options = {"Java", "C++", "VB", "PHP", "Perl"};
      int code = JOptionPane.showOptionDialog(myFrame, 
         "What language do you prefer?", 
         "Option Dialog Box", 0, messageType, 
         null, options, "PHP");
      System.out.println("Answer: "+code);
   }
}
```

If you run this example, and click the Show button, you will see an input dialog box showing up like this:

![](Images/image00182.jpeg)

Congirmation Dialog Box Input

Select "Perl" on the option dialog box. Repeat the test with the "Java" option button and the close dialog box icon. You will see some messages printed on the Java console window:

```
 Answer: 4
Answer: 0
Answer: -1
```

Interesting notes about this tutorial example:

*   If closes the option dialog box, showOptionDialog() returns JOptionPane.CLOSED_OPTION, which is -1.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟showInternal*Dialog() - Displaying Internal Dialog Boxes

This section provides a tutorial example on how to use the static methods, showInternal*Dialog(), to create and display internal dialog boxes inside an parent container.

Dialog boxes can also be created and displayed inside a panel. To do this, you need to call the "Internal" version of show*Dialog() methods:

*   showInternalMessageDialog() - Method to create and display an internal message dialog box to present regular, warning or error messages.
*   showInternalConfirmDialog() - Method to create and display an internal confirmation dialog box with yes, no and cancel buttons.
*   showInternalInputDialog() - Method to create and display an internal input dialog box to prompt for some input.
*   showInternalOptionDialog() - Method to create and display an internal generic dialog box to present message, take a confirmation, or take some input.

Note that you can not use a JFrame object directly as the "parent" for internal dialog boxes. If you do, you will get a runtime exception like this:

```
 Exception in thread "AWT-EventQueue-0" java.lang.RuntimeException: 
JOptionPane: parentComponent does not have a valid parent
   at javax.swing.JOptionPane.createInternalFrame(
      JOptionPane.java:1486)
   ...
```

The "parent" input parameter should be the content pane, or other containers.

Here is an example program I wrote to test the showInternalOptionDialog() method:

```
 /* JOptionPaneInternalOptionDialog.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneInternalOptionDialog 
   implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JOptionPaneInternalOptionDialog()).test();
   }
   private void test() {
      myFrame = new JFrame("showInternalOptionDialog() Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,200);      
      Container myPane = myFrame.getContentPane();
      JButton myButton = new JButton("Show");
      myButton.addActionListener(this);
      myPane.add(myButton);
      myFrame.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      int messageType = JOptionPane.QUESTION_MESSAGE;
      String[] options = {"Java", "C++", "VB", "PHP", "Perl"};
      int code = JOptionPane.showInternalOptionDialog(
         myFrame.getContentPane(), 
         "What language do you prefer?", 
         "Option Dialog Box", 0, messageType, 
         null, options, "PHP");
      System.out.println("Answer: "+code);
   }
}
```

If you run this example, and click the Show button, you will see an input dialog box showing up like this:

![](Images/image00183.jpeg)

Internal Dialog Box

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Option Dialog Boxes](#part0079.xhtml)

∟createDialog() - Creating Dialog Boxes Directly

This section provides a tutorial example on how to use the static method, showInputDialog(), to create and display input dialog boxes to take text string input from the user.

If you don't want to use show*Dialog() methods to create and display dialog boxes automatically, you can use the createDialog() method to create dialog boxes manually.

1\. Use "myPane = new JOptionPane()" to create an empty option pane object, which represents content pane of the dialog box.

2\. Use "myPane.setMessageType(type)" to set the message type on the option pane with a type code, INFORMATION_MESSAGE, WARNING_MESSAGE, ERROR_MESSAGE, PLAIN_MESSAGE, or QUESTION_MESSAGE.

3\. Use "myPane.setMessage(message)" to set the message text on the option pane with a string.

4\. Use "myPane.setOptionType(type)" to set the option type on the option pane with an option code, YES_NO_OPTION, YES_NO_CANCEL_OPTION, or OK_CANCEL_OPTION. This is not needed if you are setting your own options.

5\. Use "myPane.setOptions(options)" to set options on the option pane with a string array. This will override options created by the option type.

6\. Use "myPane.setInitialValue(default)" to set the default option on the option pane with a string.

7\. Use "myDialog = myPane.createDialog(parent, title)" to create the final dialog box with a parent frame and a title string.

8\. Use "myDialog.setVisible(true)" to set the final dialog box visible.

9\. Use "answer = myPane.getValue()" to get the answer selected/entered by the user on the dialog box. The answer could be an integer if options are provided with an option type, or an string in other cases.

Here is an example program I wrote to test the createDialog() method:

```
 /* JOptionPaneCreateDialog.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class JOptionPaneCreateDialog 
   implements ActionListener {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JOptionPaneCreateDialog()).test();
   }
   private void test() {
      myFrame = new JFrame("createDialog() Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      JButton myButton = new JButton("Create");
      myButton.addActionListener(this);
      myPane.add(myButton);
      myFrame.pack();
      myFrame.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      String[] options = {"Java", "C++", "VB", "PHP", "Perl"};
      JOptionPane myPane = new JOptionPane();
      myPane.setMessageType(JOptionPane.QUESTION_MESSAGE);
      myPane.setMessage("What language do you prefer?");
      myPane.setOptions(options);
      myPane.setInitialValue("PHP");
      JDialog myDialog = myPane.createDialog(
         myFrame, "Option Dialog Box");
      myDialog.setVisible(true);
      Object answer = myPane.getValue();
      System.out.println("Answer: "+answer);
   }
}
```

If you run this example, and click the Create button, you will see an input dialog box showing up like this:

![](Images/image00184.jpeg)

Creating Dialog Boxes Directly

Select "Perl" on the option dialog box. Repeat the test with the "Java" option button and the close dialog box icon. You will see some messages printed on the Java console window:

```
 Answer: Perl
Answer: Java
Answer: null
```

Interesting notes about this tutorial example:

*   The dialog box created in this example is identical to the one created in the showOptionDialog() method in the JOptionPanelOptionDialog.java example.
*   But showOptionDialog() method returns integer indexes of the option array. But myPane.getValue() returns string elements of the option array.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟JEditorPane - The Editor Pane Class

This chapter provides tutorial notes and example codes on the editor pane class. Topics include a simple text editor pane; saving text from the editor pane to a file; editing HTML content and Chinese characters in editor pane; using file chooser dialog boxes.

> [Creating a Simple Plain Text Editor Pane](#part0089.xhtml)
> 
> [Saving Text from an Editor Pane](#part0090.xhtml)
> 
> [Editing HTML in an Editor Pane](#part0091.xhtml)
> 
> [Editing Unicode Characters in an Editor Pane](#part0092.xhtml)
> 
> [javax.swing.JFileChooser - File Chooser Dialog Box](#part0093.xhtml)

Conclusions:

*   javax.swing.JEditorPane class can be used to create a simple text editor window.
*   setText() and getText() methods can be used to exchange the text content of a JEditorPane window.
*   setContentType() method can be used to switch the display mode of a JEditorPane window between text/html and text/plain.
*   javax.swing.JFileChooser class can be used to display a dialog box for selecting a file on the local computer.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JEditorPane - The Editor Pane Class](#part0088.xhtml)

∟Creating a Simple Plain Text Editor Pane

This section provides a tutorial example on how to create a simple plain text editor pane with a call of setText() to set initial text content.

javax.swing.JEditorPane class can be used to create a simple text editor window with two method calls:

*   setContentType("text/plain") - Setting the content type to be plain text.
*   setText(text) - Setting the initial text content.

Here is an example program I wrote to test the JEditorPane class:

```
 /* JEditorPaneTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.*;
public class JEditorPaneTest {
   JFrame myFrame = null;
   public static void main(String[] a) {
      (new JEditorPaneTest()).test();
   }
   private void test() {
      myFrame = new JFrame("JEditorPane Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,200);

      JEditorPane myPane = new JEditorPane();
      myPane.setContentType("text/plain");
      myPane.setText(
         "JEditorPane is a text component to edit various kinds of"
         +" content.\n\nThis component uses implementations of the"
         +" EditorKit to accomplish its behavior.");

      myFrame.setContentPane(myPane);
      myFrame.setVisible(true);
   }
}
```

If you run this example, you will see a text editor pane displayed with the initial text content.

You can edit initial text or add more text. You can also select a part of the text as shown in the picture below:

![](Images/image00185.jpeg)

Editor Pane Test

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JEditorPane - The Editor Pane Class](#part0088.xhtml)

∟Saving Text from an Editor Pane

This section provides a tutorial example on how to use the getText() method of the javax.swing.JEditorPane class to implement a save file function.

In the next tutorial example, I want to show you how to use the setText() method and the getText() method of the javax.swing.JEditorPane class to implement the "Open" function and the "Save" function of my text editor.

```
 /* JEditorPaneSave.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.io.*;
import java.nio.*;
import java.awt.event.*;
import javax.swing.*;
public class JEditorPaneSave implements ActionListener {
   JFrame myFrame = null;
   JEditorPane myPane = null;
   public static void main(String[] a) {
      (new JEditorPaneSave()).test();
   }
   private void test() {
      myFrame = new JFrame("JEditorPane Save Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,200);

      myPane = new JEditorPane();
      myPane.setContentType("text/plain");
      myPane.setText(
         "JEditorPane is a text component to edit various kinds of"
         +" content.\n\nThis component uses implementations of the"
         +" EditorKit to accomplish its behavior.");
      myFrame.setContentPane(myPane);

      JMenuBar myBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myBar.add(myMenu); 
      myFrame.setJMenuBar(myBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myItem.addActionListener(this);
      myMenu.add(myItem);

      myItem = new JMenuItem("Save");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      String cmd = ((AbstractButton) e.getSource()).getText();
      try {
         if (cmd.equals("Open")) {
            FileReader in = new FileReader("JEditorPane.txt");
            char[] buffer = new char[1024];
            int n = in.read(buffer);
            String text = new String(buffer, 0, n);
            myPane.setText(text);
            in.close();
         } else if (cmd.equals("Save")) {
            FileWriter out = new FileWriter("JEditorPane.txt");
            out.write(myPane.getText());
            out.close();
         }
      } catch (Exception f) {
         f.printStackTrace();
      }
   }
}
```

If you run this example, you will see a text editor pane displayed with the initial text content and a menu bar with the "File" menu.

You can edit the text in the editor pane, use the menu to save the changes, and open it again. See the picture below:

![](Images/image00186.jpeg)

Editor Pane - Save Changes

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JEditorPane - The Editor Pane Class](#part0088.xhtml)

∟Editing HTML in an Editor Pane

This section provides a tutorial example on how to use the setContentType() method of the javax.swing.JEditorPane class to set force the editor pane to display content in HTML format.

Now I want to try the "text/html" content type with the javax.swing.JEditorPane class. In this tutorial example, I want to add a new menu, "View", with two functions, "HTML" and "Plain". If you click HTML, the text in the editor pane will be displayed in HTML format. If you click Plain, the text in the editor pane will be displayed in plain text format. Of course, this is done by using the setContentType() of the JEditorPane class.

```
 /* JEditorPaneHtml.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.io.*;
import java.nio.*;
import java.awt.event.*;
import javax.swing.*;
public class JEditorPaneHtml implements ActionListener {
   JFrame myFrame = null;
   JEditorPane myPane = null;
   public static void main(String[] a) {
      (new JEditorPaneHtml()).test();
   }
   private void test() {
      myFrame = new JFrame("JEditorPane HTML Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,300);

      myPane = new JEditorPane();
      myPane.setContentType("text/html");
      myPane.setText(
         "<p><b>JEditorPane</b> is a text component to edit various"
         +" kinds of content.\n\nThis component uses implementations"
         +" of the EditorKit to accomplish its behavior.</p>");
      myFrame.setContentPane(myPane);

      JMenuBar myBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myBar.add(myMenu); 
      myMenu = getViewMenu();
      myBar.add(myMenu); 
      myFrame.setJMenuBar(myBar);
      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myItem.addActionListener(this);
      myMenu.add(myItem);

      myItem = new JMenuItem("Save");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      return myMenu;
   }
   private JMenu getViewMenu() {
      JMenu myMenu = new JMenu("View");
      ButtonGroup myGroup = new ButtonGroup();
      JMenuItem myItem = new JRadioButtonMenuItem("HTML");
      myItem.setSelected(true);
      myItem.addActionListener(this);
      myMenu.add(myItem);
      myGroup.add(myItem);

      myItem = new JRadioButtonMenuItem("Plain");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      myGroup.add(myItem);

      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      String cmd = ((AbstractButton) e.getSource()).getText();
      String text = null;
      try {
         if (cmd.equals("Open")) {
            FileReader in = new FileReader("JEditorPane.txt");
            char[] buffer = new char[1024];
            int n = in.read(buffer);
            text = new String(buffer, 0, n);
            myPane.setText(text);
            in.close();
         } else if (cmd.equals("Save")) {
            FileWriter out = new FileWriter("JEditorPane.txt");
            out.write(myPane.getText());
            out.close();
         } else if (cmd.equals("HTML")) {
            text = myPane.getText();
            myPane.setContentType("text/html");
            myPane.setText(text);
         } else if (cmd.equals("Plain")) {
            text = myPane.getText();
            myPane.setContentType("text/plain");
            myPane.setText(text);
         }
      } catch (Exception f) {
         f.printStackTrace();
      }
   }
}
```

If you run this example, you will see a text editor pane displayed with the initial text content and a menu bar with the "File" menu and the "View" menu.

Initially, the content is displayed in HTML format. the <b> tag is properly processed. You can <b>The End</b> at the end.

If you click the "Plain" command in the "View" menu, the content will be displayed in plain text, the original HTML source code as shown in the picture below:

![](Images/image00187.jpeg)

Editor Pane - HTML Documents

Interesting notes about this tutorial example:

*   setContentType() method will actually remove the current text content in the editor pane. This is why I have save the content into a variable first.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JEditorPane - The Editor Pane Class](#part0088.xhtml)

∟Editing Unicode Characters in an Editor Pane

This section provides a tutorial example on how to use ALTER TABLE statements to add, delete, modify, columns and indexes.

If you are trying to edit Chinese characters or other non-ASCII characters, you must change the write function and the read function to support Unicode characters with the UTF-8 encoding.

```
 /* JEditorPaneUnicode.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.io.*;
import java.nio.*;
import java.nio.charset.*;
import java.awt.event.*;
import javax.swing.*;
public class JEditorPaneUnicode implements ActionListener {
   JFrame myFrame = null;
   JEditorPane myPane = null;
   public static void main(String[] a) {
      (new JEditorPaneUnicode()).test();
   }
   private void test() {
      myFrame = new JFrame("JEditorPane Unicode Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,200);

      myPane = new JEditorPane();
      myPane.setContentType("text/plain");
      myPane.setText(
         "Hello computer! - \u7535\u8111\u4F60\u597D\uFF01\n"
         + "Welcome to Herong's Website!\n"
         + "\u6B22\u8FCE\u4F60\u8BBF\u95EE\u548C\u8363\u7F51\u7AD9"
         + "\uFF01\nwww.herongyang.com");
      myFrame.setContentPane(myPane);

      JMenuBar myBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myBar.add(myMenu); 
      myFrame.setJMenuBar(myBar);

      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myItem.addActionListener(this);
      myMenu.add(myItem);

      myItem = new JMenuItem("Save");
      myItem.addActionListener(this);
      myMenu.add(myItem);
      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      String cmd = ((AbstractButton) e.getSource()).getText();
      try {
         if (cmd.equals("Open")) {
            FileInputStream fis = 
               new FileInputStream("JEditorPane.txt");
            InputStreamReader in = 
               new InputStreamReader(fis, Charset.forName("UTF-8")); 
            char[] buffer = new char[1024];
            int n = in.read(buffer);
            String text = new String(buffer, 0, n);
            myPane.setText(text);
            in.close();
         } else if (cmd.equals("Save")) {
            FileOutputStream fos = 
               new FileOutputStream("JEditorPane.txt");
            OutputStreamWriter out = 
               new OutputStreamWriter(fos, Charset.forName("UTF-8")); 
            out.write(myPane.getText());
            out.close();
         }
      } catch (Exception f) {
         f.printStackTrace();
      }
   }
}
```

If you run this example, you will see a text editor pane displayed with the initial text content including some Chinese characters.

You can enter more Chinese or other language characters, click the Save link in the File menu, Chinese characters will be saved correctly, see the picture below:

![](Images/image00188.jpeg)

Editor Pane - Unicode Text

Interesting notes about this tutorial example:

*   I have to use OutputStreamWriter instead of FileWriter to save Unicode characters to a file. OutputStreamWriter allows me to use the UTF-8 encoding.
*   I have to use InputStreamReader instead of FileReader to read Unicode characters from a file. InputStreamReader allows me to use the UTF-8 encoding.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[JEditorPane - The Editor Pane Class](#part0088.xhtml)

∟javax.swing.JFileChooser - File Chooser Dialog Box

This section provides a tutorial example on how to use the javax.swing.JFileChooser class to create a file chooser dialog box for the Open command and the Save command.

If you want users to enter a file name to read or write data, you may want to use the javax.swing.JFileChooser class, the file chooser dialog box. It has some interesting methods:

*   setCurrentDirectory(File) - Method to set the current directory for the file chooser.
*   setSelectedFile(File) - Method to set the default selected file.
*   setFileFilter(FileFilter) - Method to define a file type based on file extensions as a file selection filter.
*   setFileSelectionMode(int) - Method to set the selection mode out 3 options: FILES_ONLY, DIRECTORIES_ONLY and FILES_AND_DIRECTORIES.
*   getSelectedFile() - Method to return the selected file as a File object.
*   showOpenDialog(Component) - Method to display this file chooser dialog box, wait for user input and return integer code: CANCEL_OPTION, APPROVE_OPTION, or ERROR_OPTION.

Here is an example program I wrote to test the JFileChooser class:

```
 /* JEditorPaneFileChooser.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.io.*;
import java.nio.*;
import java.nio.charset.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.filechooser.*;
public class JEditorPaneFileChooser implements ActionListener {
   JFrame myFrame = null;
   JEditorPane myPane = null;
   JMenuItem cmdOpen = null;
   JMenuItem cmdSave = null;
   String dirName = "\\herong\\swing\\";
   String fileName = "JEditorPane.txt";

   public static void main(String[] a) {
      (new JEditorPaneFileChooser()).test();
   }
   private void test() {
      myFrame = new JFrame("JEditorPane JFileChooser Test");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      myFrame.setSize(300,200);

      myPane = new JEditorPane();
      myPane.setContentType("text/plain");
      myPane.setText(
         "Hello computer! - \u7535\u8111\u4F60\u597D\uFF01\n"
         + "Welcome to Herong's Website!\n"
         + "\u6B22\u8FCE\u4F60\u8BBF\u95EE\u548C\u8363\u7F51\u7AD9"
         + "\uFF01\nwww.herongyang.com");
      myFrame.setContentPane(myPane);

      JMenuBar myBar = new JMenuBar();
      JMenu myMenu = getFileMenu();
      myBar.add(myMenu); 
      myFrame.setJMenuBar(myBar);

      myFrame.setVisible(true);
   }
   private JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      cmdOpen = new JMenuItem("Open");
      cmdOpen.addActionListener(this);
      myMenu.add(cmdOpen);

      cmdSave = new JMenuItem("Save");
      cmdSave.addActionListener(this);
      myMenu.add(cmdSave);
      return myMenu;
   }
   public void actionPerformed(ActionEvent e) {
      JFileChooser chooser = new JFileChooser();
      chooser.setCurrentDirectory(new File(dirName));
      chooser.setSelectedFile(new File(fileName));
      chooser.setFileSelectionMode(JFileChooser.FILES_ONLY);

      FileNameExtensionFilter filter = new FileNameExtensionFilter(
        ".txt and .java files", "txt", "java");
      chooser.setFileFilter(filter);

      Object cmd = e.getSource();
      try {
         if (cmd == cmdOpen) {
            int code = chooser.showOpenDialog(myPane);
            if (code == JFileChooser.APPROVE_OPTION) {
               File selectedFile = chooser.getSelectedFile();
               fileName = selectedFile.getName();
               FileInputStream fis = 
                  new FileInputStream(selectedFile);
               InputStreamReader in = 
                  new InputStreamReader(fis, Charset.forName("UTF-8")); 
               char[] buffer = new char[1024];
               int n = in.read(buffer);
               String text = new String(buffer, 0, n);
               myPane.setText(text);
               in.close();
            }
         } else if (cmd == cmdSave) {
            int code = chooser.showOpenDialog(myPane);
            if (code == JFileChooser.APPROVE_OPTION) {
               File selectedFile = chooser.getSelectedFile();
               fileName = selectedFile.getName();
               FileOutputStream fos = 
                  new FileOutputStream(selectedFile);
               OutputStreamWriter out = 
                  new OutputStreamWriter(fos, Charset.forName("UTF-8")); 
               out.write(myPane.getText());
               out.close();
            }
         }
      } catch (Exception f) {
         f.printStackTrace();
      }
   }
}
```

If you run this example, you will see a text editor pane displayed with the initial text content including some Chinese characters.

If you click the Open command in the File menu, a file chooser dialog box will be displayed. You can click the Details icon to change the list of files with detailed information. You can click the Date Modified column header to sort the list of files as shown in the picture below:

![](Images/image00189.jpeg)

Editor Pane - File Chooser

Interesting notes about this tutorial example:

*   "chooser.setCurrentDirectory(new File(dirName));" statement is used to set the default directory to \herong\swing\.
*   "chooser.setSelectedFile(new File(fileName));" statement is used to set the default file to JEditorPane.txt.
*   "chooser.setFileSelectionMode(JFileChooser.FILES_ONLY);" statement is used to set the selection mode to file only.
*   "chooser.setFileFilter(filter);" statement is used to set the file filter for .txt and .java files only.
*   Note that the constructor, FileNameExtensionFilter(description, ext1, ext2, ...), has a parameter list of variable length.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟SwingWorker - The Background Task Worker

This chapter provides tutorial notes and example codes on the java.swing.SwingWorker class. Topics include quick introduction of java.swing.SwingWorker; Example programs for catching final result, publishing intermediate values, updating progress property value, and connecting to JProgressBar components.

> [What Is SwingWorker Class?](#part0095.xhtml)
> 
> [SwingWorker Example using done() Method](#part0096.xhtml)
> 
> [SwingWorker Example using publish() Method](#part0097.xhtml)
> 
> [SwingWorker Example using "progress" Property](#part0098.xhtml)
> 
> [SwingWorker Example using JProgressBar](#part0099.xhtml)

Conclusion:

*   The java.swing.SwingWorker class is a task worker, which performs time consuming tasks in background.
*   A SwingWorker instance interacts with 3 threads: the Launching thread, the Worker thread and the Dispatch thread.
*   The Launching thread calls the execute() method to kickoff the task to background and returns immediately.
*   The Worker thread executes your own version of the doInBackground() method continuously in the background.
*   The Dispatch thread wakes up from time to time to notify you on what happened in the Worker thread.
*   When doInBackground() is ended, the Dispatch thread notifies you by call your version of the done() method.
*   To publish intermediate values, you can call the publish(V) method in doInBackground(). The Dispatch thread notifies you by calling your version of the process(List<V>) method.
*   To update the progress property, you can call the setProgress(i) method in doInBackground(). The Dispatch thread notifies you by calling your version of a PropertyChangeListener class.
*   The java.swing.JProgressbar class is a UI component designed to show the progress of a background task implemented as SwingWorker instance.

Sample programs listed in this chapter have been tested with JDK 1.3.1 to JDK 17 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[SwingWorker - The Background Task Worker](#part0094.xhtml)

∟What Is SwingWorker Class?

This section describes what is javax.swing.SwingWorker class - An abstract class introduced in JDK 1.6 as part of the Swing package, that you can extend the SwingWorker class to perform a time intensive computing task in the background to avoid holding the UI component response time for too long.

**What Is SwingWorker Class?** javax.swing.SwingWorker class is an abstract class introduced in JDK 1.6 as part of the Swing package. You can extend the SwingWorker class to perform a time intensive computing task in the background to avoid holding the UI component response time for too long.

When using the SwingWorker class to perform a background task, there are three threads involved in the execution flow:

*   Launching thread: The thread that creates a SwingWorker instance and calls the execute() on the instance.
*   Worker thread: The thread that actually performs the bask by executing the doInBackground() method.
*   Dispatch thread: The thread that is used by the Worker thread to send out information.

To extending the SwingWorker class, you need to consider the following:

*   Implementing the doInBackground() method to perform the actual task.
*   Implementing the done() method, if you want to do something when the task is done.
*   Calling the get() method on the SwingWorker instance, if you want to retrieve the result returned by the doInBackground() method. Note that you should call the get() method after the task is done. If you call it too early, it will wait for the task to finish.
*   Calling the publish() method while performing calculation inside the doInBackground() method any time when you want to publish intermediate values. Of course, you need to implement the process() method to receive those intermediate values.
*   Dividing the task in multiple equal units in the doInBackground() method and calling the setProgress() method to update the "progress" property with a percentage value after each unit is completed. Of course, you need to implement a java.beans.PropertyChangeListener class to get notified about the "progress" value changes.
*   Implementing a java.beans.PropertyChangeListener class to get notified about the "status" value changes of the SwingWorker instance, going from PENDING, STARTED, to DONE.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[SwingWorker - The Background Task Worker](#part0094.xhtml)

∟SwingWorker Example using done() Method

This section provides a tutorial example on how to use java.swing.SwingWorker class with the done() method to communicate the calculation result out into a dispatch thread.

There are several ways to use the SwingWorker class. Let's start with the simplest one first.

**Example 1: Get notified when task is done and retrieve the result** - This example shows the simplest way of using the SwingWorker class to just launch the Worker thread and catch the result in the Dispatch thread. Only 2 methods need to be implemented:

*   T doInBackground() - Instance method to be implemented to perform the task. The doInBackground() method will be executed in the Worker thread.
*   void done() - Instance method to be implemented, if you want to do something when the task is done. The done() method will be executed in the Dispatch thread.

Here is the source code of the example program, SwingWorkerUsingDone.java:

```
 /* SwingWorkerUsingDone.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.SwingWorker;
import java.util.List;
import java.util.Random;
import java.time.LocalTime;
public class SwingWorkerUsingDone 
   extends SwingWorker<Integer[], Object> {
   int total = 100;
   int wait = 10;

// Extending the SwingWorker class
   protected Integer[] doInBackground() {
      logMessage("doInBackground() started");
      int i = 0;
      Integer[] l = new Integer[total];
      Random r = new Random();
      try {
         while (i<total) {
            Thread.sleep(wait);
            Integer n = Integer.valueOf(r.nextInt());
            l[i] = n;
            i++;
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
      logMessage("doInBackground() ended");
      return l;
   }

   protected void done() {
      logMessage("done() started");
      try {
        Integer[] r = get();
        System.out.println("# of element in the result: "+r.length);
        System.out.println("First element: "+r[0]);
        System.out.println("Last element: "+r[total-1]);
      } catch (Exception e) {
         e.printStackTrace();
      }
      logMessage("done() ended");
   }

// Launching my extended SwingWorker class
   public static void main(String[] a) {
      try {
         SwingWorker<Integer[], Object> worker 
            = new SwingWorkerUsingDone();
         dumpThreads();
         worker.execute();
         while (true) {
            dumpThreads();
            Thread.sleep(200);
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
   }
   public static void dumpThreads() {
      System.out.println(LocalTime.now()+" Thread dump:");
      Thread.currentThread().getThreadGroup().list();
   }
   public static void logMessage(String s) {
      System.out.println(LocalTime.now()+" "
         +Thread.currentThread().getName()+": "+s);
   }
}
```

Notes on the sample program:

*   My class, SwingWorkerUsingDone, in this example is playing double roles acting both as an extended class of java.swing.SwingWorker and as the main class to start the application.
*   Note that SwingWorker class is a generic class that takes two type parameters <T,V>, where T is the data type of the result returned by the doInBackground() method; and V is the data type of intermediate values to be published by the doInBackground() method. In this example, I am setting T to be Integer[] to return result in an array of Integer; and setting V to be Object to publish intermediate values, which is not used anyway.
*   Integer[] doInBackground() is implemented to generate some random numbers. An Integer array is created to store all random numbers generated and returned at the end of the method. Note that "Thread.sleep()" is used to make execution last longer.
*   void done() is implemented to retrieve the Integer array returned by doInBackground().
*   void main() method is implemented so that SwingWorkerUsingDone can be used as the main class to start the application. In this example, I am just creating a new instance of SwingWorkerUsingDone and calling its execute() method. Then a simple loop is used to watch how many threads are running in the application.

If you compile and run this example with JDK 10 or higher, you should get output messages similar to these:

```
 herong> java SwingWorkerUsingDone.java 

20:24:03.750508700 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]

20:24:03.766108700 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
20:24:03.812908700 SwingWorker-pool-1-thread-1: doInBackground() started

20:24:03.968908700 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]

20:24:04.171708700 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]

20:24:04.374508700 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]

20:24:05.388508700 SwingWorker-pool-1-thread-1: doInBackground() ended
Thread[SwingWorker-pool-1-thread-1,5,main]

20:24:05.435308700 AWT-EventQueue-0: done() started
# of element in the result: 100
First element: 575978873
Last element: 498411894

20:24:05.435308700 AWT-EventQueue-0: done() ended    
...
```

If you compile and run this example with JDK 1.8, you should get output messages similar to these:

```
 herong> \progra~1\java\jdk-8.0.1\bin\java SwingWorkerUsingDone

21:59:22.601 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]

21:59:22.683 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
21:59:22.695 SwingWorker-pool-1-thread-1: doInBackground() started

21:59:22.884 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]

21:59:23.091 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]

21:59:23.299 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]

21:59:23.507 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
21:59:23.695 SwingWorker-pool-1-thread-1: doInBackground() ended

21:59:23.714 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
21:59:23.730 AWT-EventQueue-0: done() started

# of element in the result: 100
First element: 1278389322
Last element: 1363500147
21:59:23.731 AWT-EventQueue-0: done() ended

21:59:23.918 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]

21:59:24.123 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
...
```

Some interesting notes on the output:

*   The first thread dump at 21:59:22.601 shows that there was only 1 application thread running: "main", after the application started.
*   The second thread dump at 21:59:22.683 shows that there were 2 application thread running: "main" and "SwingWorker-pool-1-thread-1", right after worker.execute() was called.
*   The log message in the output: "21:59:22.695 SwingWorker-pool-1-thread-1: doInBackground() started" confirms that "SwingWorker-pool-1-thread-1" is the Worker thread created by the worker.execute() call to run the background task.
*   The third thread dump at 21:59:22.884 shows that there were 5 application thread running: "main", "SwingWorker-pool-1-thread-1", "AWT-Shutdown", "AWT-Windows", and "AWT-EventQueue-0". So "SwingWorker-pool-1-thread-1" created 3 more threads.
*   The log message in the output: "21:59:23.695 SwingWorker-pool-1-thread-1: doInBackground() ended" shows when doInBackground() was ended.
*   The log message in the output: "21:59:23.730 AWT-EventQueue-0: done() started" shows that the done() method was called in the "AWT-EventQueue-0" thread. So "AWT-EventQueue-0" is a Dispatch thread in our example.
*   "# of element in the result: 100" message in the output confirms the get() returned all 100 random numbers generated by the doInBackground method in the Worker thread.
*   The thread dump at 21:59:23.918 shows that the Worker thread "SwingWorker-pool-1-thread-1" continued to live even after the background task was fully completed. May be JDK is using thread pool to share meet all Worker thread requests as the thread name suggests?
*   The Dispatch thread "AWT-EventQueue" also stayed live. I not sure why.

The picture below gives you an idea on how the Launching thread, the Worker thread, and the Dispatch thread worked together in this example where I am only interested to interact with the done() method at the end of the background task:

![](Images/image00190.jpeg)

SwingWorker Threads using done() Method

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[SwingWorker - The Background Task Worker](#part0094.xhtml)

∟SwingWorker Example using publish() Method

This section provides a tutorial example on how to use java.swing.SwingWorker class with the publish() method to send out intermediate values from the doInBackground() method. The process() method must be implemented to catch those intermediate values in the dispatch thread.

**Example 2: Publish intermediate values and catch them** - This example shows the another way of using the SwingWorker class to just publish intermediate values while performing the background task and catch them result in the Dispatch thread. Only 2 methods need to be implemented:

*   T doInBackground() - Instance method to be implemented to perform the task. Inside doInBackground(), the publish(V...) method is called multiple times to publish intermediate values.
*   void process(List<V>) - Instance method to be implemented, if you want to catch intermediate values published by the publish() method calls inside doInBackground().

Here is the source code of the example program, SwingWorkerUsingPublish.java:

```
 /* SwingWorkerUsingPublish.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.SwingWorker;
import java.util.List;
import java.util.Random;
import java.time.LocalTime;
public class SwingWorkerUsingPublish 
   extends SwingWorker<Object, Integer> {
   int total = 100;
   int wait = 10;

// Extending the SwingWorker class
   protected Object doInBackground() {
      logMessage("doInBackground() started");
      int i = 0;
      Random r = new Random();
      try {
         while (i<total) {
            Thread.sleep(wait);
            Integer n = Integer.valueOf(r.nextInt());
            publish(n);
            i++;
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
      logMessage("doInBackground() ended");
      return null;
   }

   protected void process(List<Integer> v) {
      logMessage("process() receiving values: "+v.size());
   }

// Launching my extended SwingWorker class
   public static void main(String[] a) {
      try {
         SwingWorker<Object, Integer> worker 
            = new SwingWorkerUsingPublish();
         dumpThreads();
         worker.execute();
         while (true) {
            dumpThreads();
            Thread.sleep(200);
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
   }
   public static void dumpThreads() {
      System.out.println(LocalTime.now()+" Thread dump:");
      Thread.currentThread().getThreadGroup().list();
   }
   public static void logMessage(String s) {
      System.out.println(LocalTime.now()+" "
         +Thread.currentThread().getName()+": "+s);
   }
}
```

Notes on the sample program:

*   When extending SwingWorker<T,V>, I am setting T to be Object because I am not returning any result; and setting V to be Integer to publish intermediate values.
*   Object doInBackground() is implemented to generate some random numbers. Whenever a random number is generated, I call the publish() method to publish it the Dispatch thread.
*   void process(List<V>) is implemented to catch intermediate values published by the Worker thread. Note that this publish-catch process is an asynchronous process. One invocation of process() could catch multiple intermediate values from multiple publish() calls. This is why received intermediate values are passed in as a List<V> object.

If you compile and run this example with JDK 10 or higher, you should get output messages similar to these:

```
 herong> java SwingWorkerUsingPublish

20:38:25.885114100 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
20:38:25.900714100 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
20:38:25.947514100 SwingWorker-pool-1-thread-1: doInBackground() started
20:38:25.994314100 AWT-EventQueue-0: process() receiving values: 2
20:38:26.056714100 AWT-EventQueue-0: process() receiving values: 4
20:38:26.103514100 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]
20:38:26.119114100 AWT-EventQueue-0: process() receiving values: 4
20:38:26.181514100 AWT-EventQueue-0: process() receiving values: 4
20:38:26.243914100 AWT-EventQueue-0: process() receiving values: 4
20:38:26.306314100 Thread dump:
20:38:26.306314100 AWT-EventQueue-0: process() receiving values: 4
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]
...
```

If you compile and run this example with JDK 1.8, you should get output messages similar to these:

```
 herong> \progra~1\java\jdk-8.0.1\bin\java SwingWorkerUsingPublish

22:50:44.146 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]

22:50:44.186 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
22:50:44.196 SwingWorker-pool-1-thread-1: doInBackground() started
22:50:44.236 AWT-EventQueue-0: process() receiving values: 4
22:50:44.286 AWT-EventQueue-0: process() receiving values: 5
22:50:44.336 AWT-EventQueue-0: process() receiving values: 5

22:50:44.386 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    22:50:44.386 AWT-EventQueue-0: process() receiving values: 5
Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
22:50:44.436 AWT-EventQueue-0: process() receiving values: 5
22:50:44.486 AWT-EventQueue-0: process() receiving values: 5
22:50:44.536 AWT-EventQueue-0: process() receiving values: 5
22:50:44.586 AWT-EventQueue-0: process() receiving values: 5

22:50:44.596 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
22:50:44.636 AWT-EventQueue-0: process() receiving values: 5
22:50:44.686 AWT-EventQueue-0: process() receiving values: 5
22:50:44.736 AWT-EventQueue-0: process() receiving values: 5
22:50:44.786 AWT-EventQueue-0: process() receiving values: 5

22:50:44.796 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
22:50:44.836 AWT-EventQueue-0: process() receiving values: 5
22:50:44.886 AWT-EventQueue-0: process() receiving values: 5
22:50:44.936 AWT-EventQueue-0: process() receiving values: 5
22:50:44.986 AWT-EventQueue-0: process() receiving values: 5

22:50:44.996 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
22:50:45.036 AWT-EventQueue-0: process() receiving values: 5
22:50:45.086 AWT-EventQueue-0: process() receiving values: 5
22:50:45.136 AWT-EventQueue-0: process() receiving values: 5
22:50:45.186 AWT-EventQueue-0: process() receiving values: 5

22:50:45.196 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    22:50:45.196 SwingWorker-pool-1-thread-1: doInBackground() ended
Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
22:50:45.236 AWT-EventQueue-0: process() receiving values: 1

22:50:45.406 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]

22:50:45.606 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
```

Some interesting notes on the output:

*   The log message in the output: "22:50:44.236 AWT-EventQueue-0: process() receiving values: 4" shows that the process() method was called in the "AWT-EventQueue-0" thread. So "AWT-EventQueue-0" is a Dispatch thread in our example.
*   The log message in the output: "22:50:44.236 AWT-EventQueue-0: process() receiving values: 4" also shows that the process() method is called only once after 4 calls of publish(), because 4 intermediate values were passed in as the argument.
*   The log message in the output: "22:50:45.236 AWT-EventQueue-0: process() receiving values: 1" shows that the last call of process() occurred after doInBackground() is ended.

The picture below gives you an idea on how the Launching thread, the Worker thread, and the Dispatch thread worked together in this example where I am repeatedly publishing intermediate values inside the doInBackground() method, and using the process() method to catch them:

![](Images/image00191.jpeg)

SwingWorker Threads using publish() Method

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[SwingWorker - The Background Task Worker](#part0094.xhtml)

∟SwingWorker Example using "progress" Property

This section provides a tutorial example on how to use java.swing.SwingWorker class with the setProgress() method to update the 'progress' property value from the doInBackground() method. A PropertyChangeListener class must be implemented to catch the updated value of the 'progress' property in the dispatch thread.

**Example 3: Update "progress" property and use it to show progress** - This example shows you how to communicate the "progress" of a background task to a Dispatch thread. Only 1 method and 1 listener class need to be implemented:

*   T doInBackground() - Instance method to be implemented to perform the task. Inside doInBackground(), the setProgress(int) method is called multiple times to publish an integer to indicate the progress of the background task as a percentage number.
*   class ... implements PropertyChangeListener {} - Listener class that implements the propertyChange() method to catch the updated percentage value.

Here is the source code of the example program, SwingWorkerUsingProgress.java:

```
 /* SwingWorkerUsingProgress.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import javax.swing.SwingWorker;
import java.util.Random;
import java.time.LocalTime;
import java.beans.*;
public class SwingWorkerUsingProgress 
   extends SwingWorker<Object, Object> {
   int total = 100;
   int wait = 10;

// Extending the SwingWorker class
   protected Object doInBackground() {
      logMessage("doInBackground() started");
      int i = 0;
      Random r = new Random();
      try {
         while (i<total) {
            Thread.sleep(wait);
            Integer n = Integer.valueOf(r.nextInt());
            setProgress((100*(i+1))/total);
            i++;
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
      logMessage("doInBackground() ended");
      return null;
   }

// Launching my extended SwingWorker class
   public static void main(String[] a) {
      try {
         SwingWorker<Object, Object> worker 
            = new SwingWorkerUsingProgress();
         dumpThreads();
         worker.addPropertyChangeListener(new myListener());
         worker.execute();
         while (true) {
            dumpThreads();
            Thread.sleep(200);
         }
      } catch (Exception e) {
         e.printStackTrace();
      }
   }
   public static void dumpThreads() {
      System.out.println(LocalTime.now()+" Thread dump:");
      Thread.currentThread().getThreadGroup().list();
   }
   public static void logMessage(String s) {
      System.out.println(LocalTime.now()+" "
         +Thread.currentThread().getName()+": "+s);
   }
   static class myListener implements PropertyChangeListener {
      public void propertyChange(PropertyChangeEvent e) {
         if ("progress".equals(e.getPropertyName())) {
            logMessage("propertyChange() "+e.getNewValue()+"%");
         }
      }
   }
}
```

Notes on the sample program:

*   When extending SwingWorker<T,V>, I am setting T to be Object because I am not returning any result; and setting V to be Object because I am not publish any intermediate values.
*   Object doInBackground() is implemented to generate some random numbers. Whenever a random number is generated, I call the setProgress() method to update the property called "progress" with an integer between 0 and 100 to indicate the percentage of the task progress.
*   class myListener {} is implemented with the java.beans.PropertyChangeListener interface to be attached to my SwingWorker instance to listen to value change events on the "progress" property.
*   void propertyChange() is implemented inside myListener{} to catch the updated "progress" property value.

If you compile and run this example with JDK 10 or higher, you should get output messages similar to these:

```
 herong> java SwingWorkerUsingProgress

20:45:52.387317 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
20:45:52.402917 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
20:45:52.449717 SwingWorker-pool-1-thread-1: doInBackground() started
20:45:52.512117 AWT-EventQueue-0: propertyChange() 3%
20:45:52.574517 AWT-EventQueue-0: propertyChange() 7%
20:45:52.605717 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]
20:45:52.636917 AWT-EventQueue-0: propertyChange() 11%
20:45:52.699317 AWT-EventQueue-0: propertyChange() 15%
20:45:52.761717 AWT-EventQueue-0: propertyChange() 19%
20:45:52.808517 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-EventQueue-0,6,main]
20:45:52.824117 AWT-EventQueue-0: propertyChange() 23%
```

If you compile and run this example with JDK 1.8, you should get output messages similar to these:

```
 herong> \progra~1\java\jdk-8.0.1\bin\java SwingWorkerUsingProgress

23:02:46.481 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]

23:02:46.521 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
23:02:46.531 SwingWorker-pool-1-thread-1: doInBackground() started
23:02:46.571 AWT-EventQueue-0: propertyChange() 4%
23:02:46.621 AWT-EventQueue-0: propertyChange() 9%
23:02:46.671 AWT-EventQueue-0: propertyChange() 14%

23:02:46.721 Thread dump:
23:02:46.721 AWT-EventQueue-0: propertyChange() 19%
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
23:02:46.771 AWT-EventQueue-0: propertyChange() 24%
23:02:46.821 AWT-EventQueue-0: propertyChange() 29%
23:02:46.871 AWT-EventQueue-0: propertyChange() 34%
23:02:46.921 AWT-EventQueue-0: propertyChange() 39%

23:02:46.921 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
23:02:46.971 AWT-EventQueue-0: propertyChange() 44%
23:02:47.021 AWT-EventQueue-0: propertyChange() 49%
23:02:47.071 AWT-EventQueue-0: propertyChange() 54%
23:02:47.121 AWT-EventQueue-0: propertyChange() 59%

23:02:47.121 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
23:02:47.171 AWT-EventQueue-0: propertyChange() 64%
23:02:47.221 AWT-EventQueue-0: propertyChange() 69%
23:02:47.271 AWT-EventQueue-0: propertyChange() 74%
23:02:47.321 AWT-EventQueue-0: propertyChange() 79%

23:02:47.331 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
23:02:47.371 AWT-EventQueue-0: propertyChange() 84%
23:02:47.421 AWT-EventQueue-0: propertyChange() 89%
23:02:47.471 AWT-EventQueue-0: propertyChange() 94%
23:02:47.521 AWT-EventQueue-0: propertyChange() 99%
23:02:47.531 SwingWorker-pool-1-thread-1: doInBackground() ended

23:02:47.531 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
23:02:47.571 AWT-EventQueue-0: propertyChange() 100%

23:02:47.731 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]

23:02:47.931 Thread dump:
java.lang.ThreadGroup[name=main,maxpri=10]
    Thread[main,5,main]
    Thread[SwingWorker-pool-1-thread-1,5,main]
    Thread[AWT-Shutdown,5,main]
    Thread[AWT-Windows,6,main]
    Thread[AWT-EventQueue-0,6,main]
```

Some interesting notes on the output:

*   The log message in the output: "23:02:46.571 AWT-EventQueue-0: propertyChange() 4%" shows that the propertyChange() method was called in the "AWT-EventQueue-0" thread. So "AWT-EventQueue-0" is a Dispatch thread in our example.
*   The log message in the output: "23:02:46.571 AWT-EventQueue-0: propertyChange() 4%" also shows that the process() method is called only once after 4 calls of setProgress(), because I don't see 1%, 2% and 3% "progress" property values showing in output.

The picture below gives you an idea on how the Launching thread, the Worker thread, and the Dispatch thread worked together in this example where I am repeatedly updating "progress" property value inside the doInBackground() method, and using a PropertyChangeListener class to catch it:

![](Images/image00192.jpeg)

SwingWorker Threads using Progress Property

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[SwingWorker - The Background Task Worker](#part0094.xhtml)

∟SwingWorker Example using JProgressBar

This section provides a tutorial example on how to use java.swing.SwingWorker class the JProgressBar component on the UI. All main features of the SwingWorker class are demonstrated.

**Example 4: Put everything together** - This example shows you how to all features of the SwingWorker class together to create more real Swing GUI application to generate random numbers as a background task.

Here is the source code of the example program, SwingWorkerUsingProgress.java:

```
 /* SwingWorkerUsingProgressBar.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.beans.*;
import java.awt.*;
import java.awt.event.*;
import java.util.*;
import javax.swing.*;
public class SwingWorkerUsingProgressBar {
   static JButton myButton;
   static JProgressBar myProgressBar;
   static JLabel myUpdate;
   static JTextArea myTextArea;
   public static void main(String[] a) {
      JFrame myFrame = new JFrame("Random Number Generator");
      myFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      Container myPane = myFrame.getContentPane();
      myPane.setLayout(new GridBagLayout());
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.CENTER);
      myPane.add(getFieldPanel(),c);
      setMyConstraints(c,0,1,GridBagConstraints.CENTER);
      myPane.add(getButtonPanel(),c);

      JMenuBar myMenuBar = new JMenuBar();
      myMenuBar.add(getFileMenu());
      myMenuBar.add(getColorMenu());
      JMenuItem myItem = new JMenuItem("Help");
      myMenuBar.add(myItem);
      myFrame.setJMenuBar(myMenuBar);

      myFrame.pack();
      myFrame.setVisible(true);
   }
   private static JMenu getFileMenu() {
      JMenu myMenu = new JMenu("File");
      JMenuItem myItem = new JMenuItem("Open");
      myMenu.add(myItem);
      myItem = new JMenuItem("Close");
      myItem.setEnabled(false);
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new JMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private static JMenu getColorMenu() {
      JMenu myMenu = new JMenu("Color");
      JMenuItem myItem = new JMenuItem("Red");
      myMenu.add(myItem);
      myItem = new JMenuItem("Green");
      myMenu.add(myItem);
      myItem = new JMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private static JPanel getFieldPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      p.setBorder(BorderFactory.createTitledBorder(""));
      GridBagConstraints c = new GridBagConstraints();
      setMyConstraints(c,0,0,GridBagConstraints.EAST);
      p.add(new JLabel("Progress:"),c);
      setMyConstraints(c,1,0,GridBagConstraints.WEST);
      myProgressBar = new JProgressBar(0, 100);
      p.add(myProgressBar,c);
      setMyConstraints(c,0,1,GridBagConstraints.EAST);
      p.add(new JLabel("Last number:"),c);
      setMyConstraints(c,1,1,GridBagConstraints.WEST);
      myUpdate = new JLabel("");
      p.add(myUpdate,c);
      setMyConstraints(c,0,2,GridBagConstraints.EAST);
      p.add(new JLabel("All numbers:"),c);
      setMyConstraints(c,1,2,GridBagConstraints.WEST);
      myTextArea = new JTextArea(10,40);
      myTextArea.setLineWrap(true);
      myTextArea.setFont(new Font("Courier",Font.PLAIN, 12));
      p.add(myTextArea,c);
      return p;
   }
   private static JPanel getButtonPanel() {
      JPanel p = new JPanel(new GridBagLayout());
      myButton = new JButton("Run");
      myButton.addActionListener(new MyButtonListener());
      p.add(myButton);
      return p;
   }
   private static void setMyConstraints(GridBagConstraints c, 
      int gridx, int gridy, int anchor) {
      c.gridx = gridx;
      c.gridy = gridy;
      c.anchor = anchor;
   }

// My ActionListener class to kickoff the task
   static class MyButtonListener implements ActionListener {
      public void actionPerformed(ActionEvent e) {
         myButton.setText("Wait");
         myButton.setEnabled(false);
         myTextArea.setText("");
         MySwingWorker worker = new MySwingWorker();
         worker.addPropertyChangeListener(new MyProgressListener());
         worker.execute();
      }
   }

// My SwingWorker class to perform the task
   static class MySwingWorker 
      extends SwingWorker<Integer[], Integer> {
      int total = 100;
      int wait = 100;
      protected Integer[] doInBackground() {
         Integer[] l = new Integer[total];
         Random r = new Random();
         try {
            for (int i=0; i<total; i++) {
               Thread.sleep(wait);
               Integer n = Integer.valueOf(100+r.nextInt(899));
               l[i] = n;
               publish(n);
               setProgress((100*(i+1))/total);
            }
         } catch (Exception e) {
            e.printStackTrace();
         }
         return l;
      }
      protected void process(java.util.List<Integer> v) {
         myUpdate.setText(""+(Integer)v.get(v.size()-1));
      }
      protected void done() {
         try {
            Integer[] r = get();
            String s = "";
            for (int i=0; i<r.length; i++) {
               s += " "+r[i];
            }
            myTextArea.setText(s);
            myButton.setText("Run");
            myButton.setEnabled(true);
         } catch (Exception e) {
            e.printStackTrace();
         }
      }
   }

// My PropertyChangeListener class catch progress property changes  
   static class MyProgressListener implements PropertyChangeListener {
      public void propertyChange(PropertyChangeEvent e) {
         if ("progress".equals(e.getPropertyName())) {
            myProgressBar.setValue((Integer)e.getNewValue());
         }
      }
   }
}
```

If you compile and run this example, you will see a Swing window showing up. If you click the "Run" button to kickoff the background task, you will see the progress bar getting updated as more random numbers are generated. See the picture below:

![](Images/image00193.jpeg)

SwingWorker Threads with JProgressBar

Note that while the random number generation is going on in the background, you can still click on menu items to perform other functions. This demonstrates us the key advantage of using the SwingWorker class, i.e. to launch a time consuming task in the background and keep the UI to be responsive.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟AWT (Abstract Windows Toolkit)

This chapter provides tutorial JDK AWT (Abstract Windows Toolkit). Topics include introduction of AWT classes; creating and closing AWT frames; drawing graphics on components; creating labels and buttons; Text field and action listeners; using menu bar, menu and menu items.

> [What Is AWT (Abstract Windows Toolkit)](#part0101.xhtml)
> 
> [HelloAWT.java - My First AWT Program](#part0102.xhtml)
> 
> [Closing AWT Frame and Terminating Application](#part0103.xhtml)
> 
> [Drawing Graphics - Using paint() on Frame or Component](#part0104.xhtml)
> 
> [Creating Labels with java.awt.Label Class](#part0105.xhtml)
> 
> [Creating Buttons with java.awt.Button Class](#part0106.xhtml)
> 
> [AWT Button Action Handler at the Component Level](#part0107.xhtml)
> 
> [AWT Button Action Handler at the Frame Level](#part0108.xhtml)
> 
> [AWT Button Mouse Click Handler at the Frame Level](#part0109.xhtml)
> 
> [AWT TextField and ActionListener](#part0110.xhtml)
> 
> [MenuBarTest.java - AWT Menu Bar Test Program](#part0111.xhtml)
> 
> [MenuTest.java - AWT Menu Test Program](#part0112.xhtml)
> 
> [MenuItemTest.java - AWT Menu Item Test Program](#part0113.xhtml)
> 
> [MenuItemActionListenerTest.java - AWT Menu Item Action Listener](#part0114.xhtml)

Conclusion:

*   AWT (Abstract Windows Toolkit) is a Java package, java.awt.* that allows Java applications to operate graphical devices and create GUI (Graphical User Interfaces).
*   java.awt.Frame - Represents a top-level window with a title and a border.
*   You can override the paint() method to draw graphics on the frame or any components.
*   java.awt.Button and java.awt.Label represent standard button and label GUI components.
*   Button can generate action events, when clicked. You can add action listeners to handle action events with your own logics.
*   TextField can also generate action events, when "Enter" key is pressed.
*   java.awt.MenuBar, java.awt.Menu and java.awt.MenuItem can be used to create a menu system and added to a frame.

Sample programs listed in this chapter have been tested with JDK 1.0 to JDK 15 on Windows and macOS computers.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟What Is AWT (Abstract Windows Toolkit)

This section describes what is AWT (Abstract Windows Toolkit) - A Java package, java.awt.* that allows Java applications to operate graphical devices and create GUI (Graphical User Interfaces).

**What Is AWT (Abstract Windows Toolkit)**? AWT is a Java package, java.awt.* that allows Java applications to operate graphical devices and create GUI (Graphical User Interfaces).

The JDK documentation offers another description of AWT: "AWT contains all of the classes for creating user interfaces and for painting graphics and images. A user interface object such as a button or a scrollbar is called, in AWT terminology, a component. The Component class is the root of all AWT components. See Component for a detailed description of properties that all AWT components share."

The AWT package, java.awt.* was introduced in JDK 1.0\. Later in JDK 1.2, the Swing package, javax.swing.*, was introduced to provide a richer API and hiding AWT behind a wrapper layer.

The AWT package contains following major class:

*   java.awt.AWTEvent - The root class of all SWT event classes.
*   java.awt.Button - Represents a labeled button.
*   java.awt.Canvas - Represents a blank rectangular area of the screen onto which the application can draw or from which the application can trap input events from the user.
*   java.awt.Checkbox - Represents a graphical component with either an "on" (true) or "off" (false) state.
*   java.awt.Color - Encapsulates colors in the default sRGB color space.
*   java.awt.Component - A graphical representation that can be displayed on the screen and that can interact with the user.
*   java.awt.Container - A logical component that can hold other components as a group.
*   java.awt.Desktop - Allows the application to interact with various desktop capabilities.
*   java.awt.Dialog - Represents a top-level window with a title and a border that is typically used to take some form of input from the user.
*   java.awt.Event - Represents a labeled button.
*   java.awt.FlowLayout - Arranges components in a directional flow, much like lines of text in a paragraph.
*   java.awt.Font - Represents fonts, which are used to render text in a visible way.
*   java.awt.Frame - Represents a top-level window with a title and a border.
*   java.awt.Graphics - An abstract base class for all graphics contexts that allow an application to draw onto components that are realized on various devices, as well as onto off-screen images.
*   java.awt.GraphicsEnvironment - Describes the collection of GraphicsDevice objects and Font objects available to a Java(tm) application on a particular platform.
*   java.awt.GridBagLayout - A flexible layout manager that aligns components vertically, horizontally or along their baseline without requiring that the components be of the same size.
*   java.awt.GridLayout - A layout manager that lays out a container's components in a rectangular grid.
*   java.awt.Image - An abstract class acting as the superclass of all classes that represent graphical images.
*   java.awt.Label - A component for placing text in a container.
*   java.awt.List - A component presenting the user with a scrolling list of text items.
*   java.awt.Menu - A pull-down menu component that is deployed from a menu bar.
*   java.awt.MenuBar - Encapsulates the platform's concept of a menu bar bound to a frame.
*   java.awt.MenuItem - An item associated to the MenuBar.
*   java.awt.MouseInfo - Provides methods for getting information about the mouse, such as mouse pointer location and the number of mouse buttons.
*   java.awt.Panel - The simplest container class.
*   java.awt.Point - Represents a location in (x,y) coordinate space, specified in integer precision.
*   java.awt.Polygon - Encapsulates a description of a closed, two-dimensional region within a coordinate space.
*   java.awt.Rectangle - Specifies an area in a coordinate space that is enclosed by the Rectangle object's upper-left point (x,y) in the coordinate space, its width, and its height.
*   java.awt.Robot - Generates native system input events for the purposes of test automation, self-running demos, and other applications where control of the mouse and keyboard is needed.
*   java.awt.Scrollbar - Embodies a scroll bar, a familiar user-interface object.
*   java.awt. ScrollPane - A container class which implements automatic horizontal and/or vertical scrolling for a single child component.
*   java.awt.SystemTray - Represents the system tray for a desktop.
*   java.awt.Taskbar - Allows a Java application to interact with the system task area (taskbar, Dock, etc.).
*   java.awt.TextArea - A multi-line region that displays text.
*   java.awt.TextField - A text component that allows for the editing of a single line of text.
*   java.awt.Toolkit - The abstract superclass of all actual implementations of the Abstract Window Toolkit.
*   java.awt.TrayIcon - Represents a tray icon that can be added to the system tray.
*   java.awt.Window object - A top-level window with no borders and no menubar.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟HelloAWT.java - My First AWT Program

This section provides a tutorial example on how to write a simple Java AWT program. HelloAWT.java is my first AWT program that displays a blank window with 'Hello world!' in the window title bar.

Below is my first AWT program, HelloAWT.java:

```
 import java.awt.Frame;
public class HelloAWT {
   public static void main(String[] a) {
      Frame f = new Frame("Hello world!");
      f.setVisible(true);
   }
}
```

If you have JDK installed on your system, you can compile and run this program in a command window:

```
 herong> javac HelloAWT.java
herong> java HelloAWT
```

Once the program is running, you will see a small new window showing up on your screen. If use the mouse pointer to drag its edges to make it larger, you can see the hello text in the title area as shown in this picture:

![](Images/image00194.jpeg)

First AWT - Hello World!

The new window will stay on your screen until you press Ctrl-C in the command window to terminate the running program.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟Closing AWT Frame and Terminating Application

This section provides solutions and sample program on how to close an AWT frame and terminate the application.

**Problem**: I have a frame window displayed on the screen and I want to close the frame and terminate the application, when user invokes the close command from the window's system menu, or clicks on the close icon from the window's system icon list.

**Solution**: You can create a new window event listener class and add an object of this listener class to the Frame object. In the new window event listener, you can implement your owner version of windowClosing() handler method. Of course, the quickest way to create a new window event listener class is to extend the WindowAdapter class.

The following sample code, FrameClose.java, shows you how to do this.

```
 /* FrameClose.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;
public class FrameClose  {
   public static void main(String[] a) {
      Frame f = new Frame();
      f.setTitle("Closing Frame with Window Listener");
      f.setBounds(100,50,500,300);
      f.addWindowListener(new MyWindowListener());
      f.setVisible(true);
   }
   static class MyWindowListener extends WindowAdapter {
      public void windowClosing(WindowEvent e) {
         System.exit(0);
      }
   }
}
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟Drawing Graphics - Using paint() on Frame or Component

This section provides a tutorial example on how to override the paint() method in the javax.awt.Frame class to draw graphics (a rectangle) on the frame window, or override the paint() method in the java.awt.Component class to draw graphics and add the component to the frame window.

**Problem**: I want to draw some graphics in a frame.

**Solution 1**: You can do this very easily by extending Frame class to create your own frame class so that you can override the paint() method. The paint() method provides you a Graphics object, which will give you utility methods to draw various types of graphics. The following sample code, FramePaint1.java, shows you how to do this.

```
 /* FramePaint1.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Graphics;
public class FramePaint1 {
   public static void main(String[] a) {
      MyFrame f = new MyFrame();
      f.setTitle("Drawing Graphics in a Frame Directly");
      f.setBounds(100,50,500,300);
      f.setVisible(true);
   }
   static class MyFrame extends Frame {
      public void paint(Graphics g) {
         g.drawRect(20,10,100,60);
      }
   }
}
```

If you run this example, you will get:

![](Images/image00135.jpeg)

Using paint() on Frame

Note 1: The paint() method is inherited by Frame class from the Component class. It will be called whenever this component should be painted.

Note 2: If you look at the rectangle displayed on the frame, you will see that the origin of the drawing coordinates is located at the top left corner of the entire frame, including the title bar.

Note 3: By default, the paint() method provides transparent background, in JDK 1.4, 1.5 and 1.6\. This is why you see a Web page showing up in the picture.

Note 4: In JDK 7 and higher, the paint() method does not provides transparent background.

This solution is not recommended. We don't want to draw graphics in the frame bar area.

**Solution 2**: Obviously, solution 1 is not so ideal, because we are drawing on the UI element of the frame itself. To draw graphics only in the content area of the frame, we can create a new component with its own paint() method and add it to the frame. The following sample code, FramePaint2.java, shows you how to do this.

```
 /* FramePaint2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Graphics;
import java.awt.Component;
public class FramePaint2 {
   public static void main(String[] a) {
      Frame f = new Frame();
      f.setTitle("Drawing Graphics in a Frame"
         +" by Adding a Component");
      f.setBounds(100,50,500,300);
      f.add(new MyComponent());
      f.setVisible(true);
   }
   static class MyComponent extends Component {
      public void paint(Graphics g) {
         g.drawRect(20,10,100,60);
      }
   }
}
```

If you run this example, you will get:

![](Images/image00195.jpeg)

Using paint() on Component

Note 1: Since no size and location is given to the new added component, it takes the entire area of the content pane, which is the entire area of the frame without the title bar area.

Note 2: Now the origin of the drawing coordinates is at the top left corner of the content pane, much better than solution 1.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟Creating Labels with java.awt.Label Class

This section provides a tutorial example on how to create a label with the java.awt.Label class.

**Problem**: I want to create a label with a text string.

**Solution**: This is easy, just instantiate an object of java.awt.Label, and add it to any container. Here is a sample program to show you how to do this:

```
 /* LabelHello.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Label;
public class LabelHello {
   public static void main(String[] a) {
      Frame f = new Frame("LabelHello");
      Label l = new Label("Hello world!");
      f.add(l);
      f.pack();      
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00196.jpeg)

AWT Label Test

Note: The pack() method causes the window to resize to fit the preferred size and layouts of its subcomponents.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟Creating Buttons with java.awt.Button Class

This section provides a tutorial example on how to create a button with the java.awt.Button class.

Buttons are so easy to create with the java.awt.Button class. Here is a sample program:

```
 /* ButtonOk.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Button;
public class ButtonOk {
   public static void main(String[] a) {
      Frame f = new Frame("My OK Button");
      Button b = new Button("OK");
      f.add(b);
      f.pack();      
      f.setVisible(true);
   }
}
```

If you run this example, you will get:

![](Images/image00197.jpeg)

AWT Button Test

Note: Clicking the OK button will trigger no actions, because no event listeners are added to the button component.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟AWT Button Action Handler at the Component Level

This section provides a tutorial example on how to create an AWT button to handle actions by adding the ActionListener interface to the button component.

One way to handle button actions is to add an action listener to the button object. An action listener is an object of any class that implements the ActionListener interface.

The following program shows you how to extend the Button class to implement the ActionListener class:

```
 /* ButtonAction.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Button;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class ButtonAction1 {
   public static void main(String[] a) {
      Frame f = new Frame("My AWT Button");
      Button b = new MyButton();
      f.add(b);
      f.pack();
      f.setVisible(true);
   }
   private static class MyButton extends Button 
      implements ActionListener {
       String text = "On";
       public MyButton() {
          super();
          setLabel(text);
          addActionListener(this);
       }
       public void actionPerformed(ActionEvent e) {
          if (text.equals("On")) text = "Off";
          else text = "On"; 
          setLabel(text);
       }
   }
}
```

If you run this example, you will get:

![](Images/image00198.jpeg)

AWT Button Action Handler

The button works well. If you click the button, the button label text will change from "On" to "Off"; and from "Off" to "On", if you click it again.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟AWT Button Action Handler at the Frame Level

This section provides a tutorial example on how to create an AWT button to handle actions by adding the ActionListener interface to the frame that contains the button component.

In the previous section, we extended the button to handle its own action. That works fine, if the action only requires modifying the behavior of the same button.

But if the action requires modifying the behavior of other components, you need to implement the action listener as a higher level. The following program shows you how to use the action handler to modify the text of a label component:

```
 /* ButtonAction2.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Button;
import java.awt.Label;
import java.awt.GridLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class ButtonAction2 implements ActionListener {
   Button myButton = null;
   Label myLabel = null;
   String text = null;
   public static void main(String[] a) {
      ButtonAction2 myTest = new ButtonAction2();
      myTest.createFrame();
   }
   public void createFrame() {
      Frame f = new Frame("My Switch Button");
      f.setLayout(new GridLayout(2,1));
      text = "On";
      myButton = new Button(text);
      myButton.addActionListener(this);
      f.add(myButton);
      myLabel = new Label(text);
      f.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void actionPerformed(ActionEvent e) {
      if (text.equals("On")) text = "Off";
      else text = "On"; 
      myButton.setLabel(text);
      myLabel.setText(text);
   }
}
```

If you run this example, you will get:

![](Images/image00199.jpeg)

AWT Button Action Handler

The button works nicely. If you click the button, the button label text will change from "On" to "Off", and the text of the label component will also change.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟AWT Button Mouse Click Handler at the Frame Level

This section provides a tutorial example on how to create an AWT button to handle actions by adding the MouseAdapter interface to the frame that contains the button component.

Of course, using ActionListeners is not the only way to handle user clicks on buttons. You can also use MouseListeners to handle user clicks. Here is an example program:

```
 /* ButtonAction3.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.Button;
import java.awt.Label;
import java.awt.GridLayout;
import java.awt.event.MouseEvent;
import java.awt.event.MouseAdapter;
public class ButtonAction3 extends MouseAdapter {
   Button myButton = null;
   Label myLabel = null;
   String text = null;
   public static void main(String[] a) {
      ButtonAction3 myTest = new ButtonAction3();
      myTest.createFrame();
   }
   public void createFrame() {
      Frame f = new Frame("My Switch Button");
      f.setLayout(new GridLayout(2,1));
      text = "On";
      myButton = new Button(text);
      myButton.addMouseListener(this);
      f.add(myButton);
      myLabel = new Label(text);
      f.add(myLabel);
      f.pack();
      f.setVisible(true);
   }
   public void mouseClicked(MouseEvent e) {
      if (text.equals("On")) text = "Off";
      else text = "On"; 
      myButton.setLabel(text);
      myLabel.setText(text);
   }
}
```

If you run this example, you will get:

![](Images/image00200.jpeg)

AWT Button Mouse Adapter

The button works nicely. If you click the button, the button label text will change from "On" to "Off", and the text of the label component will also change.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟AWT TextField and ActionListener

This section provides a tutorial example on how to create an AWT text field with an event handler implemented as the ActionListener listener.

AWT TextField component can trigger ActionEvent directly. Here is a sample program to show you how TextField ActionEvent works:

```
 /* TextFieldTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.TextField;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class TextFieldTest {
   public static void main(String[] a) {
      Frame f = new Frame("Text Field Test");
      MyTextField t = new MyTextField(16);
      f.add(t);
      f.pack();
      f.setVisible(true);
   }
   private static class MyTextField extends TextField 
      implements ActionListener {
      static int count = 0;
      public MyTextField(int l) {
         super(l);
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         count++;
         System.out.println(count+": Action performed - "+getText());
      }
   }
}
```

Run this program and do the following in the text field:

*   Type "Hello".
*   Press the enter key.
*   Type " World!".
*   Press the enter key.

The text field should look like this:

![](Images/image00201.jpeg)

AWT TextField ActionListener

And you should get the following output in the console window:

```
 1: Action performed - Hello
2: Action performed - Hello World!
```

The output confirms that:

*   ActionListener is called when the enter key is pressed.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟MenuBarTest.java - AWT Menu Bar Test Program

This section provides a tutorial example on how to use the java.awt.MenuBar class to create a menu bar in a frame window.

If you want to add a menu bar to a AWT frame, you can follow this example program:

```
 /* MenuBarTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.MenuBar;
import java.awt.Menu;
import java.awt.MenuItem;
import java.awt.Button;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class MenuBarTest {
   public static void main(String[] a) {
      Frame f = new Frame("MenuBar Test");
      f.setBounds(50,50,250,150);

      MenuBar mb = new MenuBar();      
      mb.add(new Menu("Tools")); 
      mb.add(new Menu("Options")); 
      mb.add(new Menu("Save")); 
      mb.add(new Menu("Quit")); 

      f.setMenuBar(mb);
      f.add(new MyButton());
      f.setVisible(true);
   }
   private static class MyButton extends Button 
      implements ActionListener {
      public MyButton() {
         super("Check");
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Check button clicked");
         Frame myFrame = (Frame) (this.getParent());
         MenuBar myMenuBar = myFrame.getMenuBar();
         System.out.println("# of elements in the menu bar: "
            +myMenuBar.getMenuCount());
      }
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00202.jpeg)

AWT Menu Bar Test

If you click the "Check" button, you will see text output in the console window:

```
 Check button clicked
# of elements in the menu bar: 4
```

Interesting notes about this tutorial example:

*   The "Check" Button added in the frame is a grand grand child of the frame. So I have to use "this.getParent()" to reach the frame object from the button object.
*   getMenuCount() methods work as expected.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟MenuTest.java - AWT Menu Test Program

This section provides a tutorial example on how to use the java.awt.Menu class to create multiple menus and how to add them to the menu bar. Sub menus and menu items added to a menu will be listed vertically when the menu is selected.

Here is an example program I wrote to test the java.awt.Menu class:

```
 /* MenuTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame; 
import java.awt.MenuBar; 
import java.awt.Menu; 
import java.awt.MenuItem; 
public class MenuTest {
   Frame myFrame = null;
   public static void main(String[] a) {
      (new MenuTest()).test();
   }
   private void test() {
      myFrame = new Frame("Menu Test");
      myFrame.setBounds(50,50,250,150);
      MenuBar myMenuBar = new MenuBar();
      Menu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);

      myFrame.setMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private Menu getFileMenu() {
      Menu myMenu = new Menu("File");
      Menu mySubMenu = getOpenMenu();
      myMenu.add(mySubMenu);
      MenuItem myItem = new MenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new MenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private Menu getColorMenu() {
      Menu myMenu = new Menu("Color");
      MenuItem myItem = new MenuItem("Red");
      myMenu.add(myItem);
      myItem = new MenuItem("Green");
      myMenu.add(myItem);
      myItem = new MenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private Menu getOpenMenu() {
      Menu myMenu = new Menu("Open");
      MenuItem myItem = new MenuItem("Java");
      myMenu.add(myItem);
      myItem = new MenuItem("HTML");
      myMenu.add(myItem);
      myItem = new MenuItem("GIF");
      myMenu.add(myItem);
      return myMenu;
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00203.jpeg)

AWT Menu Test

Interesting notes about this tutorial example:

*   Multiple menus can be added to a menu bar. The "File" menu and the "Color" menu are added to the menu bar in this example.
*   A menu can have a child menu included in the same way as a menu item. The "Open" menu is added as a child menu to the "File" menu in this example.
*   Calling the addSeparator() method on a Menu object does add a separation line in the menu element list.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟MenuItemTest.java - AWT Menu Item Test Program

This section provides a tutorial example on how to use the java.awt.MenuItem class to create menu items and add them to different menus, sub menus, or the menu bar. Sub menus and menu items added to a menu will be listed vertically when the menu is selected.

Here is an example program I wrote to test the java.awt.MenuItem class:

```
 /* MenuItemTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.MenuBar;
import java.awt.Menu;
import java.awt.MenuItem;
public class MenuItemTest {
   Frame myFrame = null;
   public static void main(String[] a) {
      (new MenuItemTest()).test();
   }
   private void test() {
      myFrame = new Frame("Menu Item Test");
      myFrame.setBounds(50,50,250,150);

      MenuBar myMenuBar = new MenuBar();
      Menu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      myFrame.setMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private Menu getFileMenu() {
      Menu myMenu = new Menu("File");
      MenuItem myItem = new MenuItem("Open");
      myMenu.add(myItem);
      myItem = new MenuItem("Close");
      myItem.setEnabled(false);
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new MenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private Menu getColorMenu() {
      Menu myMenu = new Menu("Color");
      MenuItem myItem = new MenuItem("Red");
      myMenu.add(myItem);
      myItem = new MenuItem("Green");
      myMenu.add(myItem);
      myItem = new MenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private Menu getOptionMenu() {
      Menu myMenu = new Menu("Option");
      Menu mySubMenu = getOnOffMenu("Sound");
      myMenu.add(mySubMenu);
      mySubMenu = getOnOffMenu("Auto save");
      mySubMenu.setEnabled(false);
      myMenu.add(mySubMenu);
      return myMenu;
   }
   private Menu getOnOffMenu(String title) {
      Menu myMenu = new Menu(title);
      MenuItem myItem = new MenuItem("On");
      myMenu.add(myItem);
      myItem = new MenuItem("Off");
      myMenu.add(myItem);
      return myMenu;
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00204.jpeg)

AWT Menu Item Test

Interesting notes about this tutorial example:

*   A menu item can be disabled by calling the set setEnabled(false) function. A disabled menu item will be listed in gray and not be clickable. The "Close" menu item is disabled in this example.
*   A menu can also be disabled by calling the set setEnabled(false) function. A disabled menu will be listed in gray and not be clickable. The "Auto save" menu item is disabled in this example.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[AWT (Abstract Windows Toolkit)](#part0100.xhtml)

∟MenuItemActionListenerTest.java - AWT Menu Item Action Listener

This section provides a tutorial example on how to use java.awt.event.ActionListener, button action listener interface, to catch events fired by MenuItem objects.

Like any other user interface components, MenuItem objects also fire events when users interact with them. If you want to perform a task when an event occurs on a MenuItem object, you need to add an event listener to that MenuItem item object. Because a MenuItem is a sub class of AbstractButton, it shares the listener interface and event class with AbstractButton:

java.awt.event.ActionListener - An AWT interface that allows you to implement your own event handler methods:

*   actionPerformed(ActionEvent) - Event handler method called when the associated component is clicked. You need to implement this method to perform your own task.

java.awt.event.ActionEvent - An AWT class that represents an event occurred on a component. The most important method in this class is:

*   getActionCommand() - Method returns the action command string.

Here is an example program I wrote to test the ActionListener interface:

```
 /* MenuItemActionListenerTest.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.Frame;
import java.awt.MenuBar;
import java.awt.Menu;
import java.awt.MenuItem;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class MenuItemActionListenerTest {
   Frame myFrame = null;
   public static void main(String[] a) {
      (new MenuItemActionListenerTest()).test();
   }
   private void test() {
      myFrame = new Frame("Menu Listener Test");
      myFrame.setBounds(50,50,250,150);

      MenuBar myMenuBar = new MenuBar();
      Menu myMenu = getFileMenu();
      myMenuBar.add(myMenu);
      myMenu = getColorMenu();
      myMenuBar.add(myMenu);
      myMenu = getOptionMenu();
      myMenuBar.add(myMenu);

      myFrame.setMenuBar(myMenuBar);
      myFrame.setVisible(true);
   }
   private Menu getFileMenu() {
      Menu myMenu = new Menu("File");
      MyMenuItem myItem = new MyMenuItem("Open");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Close");
      myMenu.add(myItem);
      myMenu.addSeparator();
      myItem = new MyMenuItem("Exit");
      myMenu.add(myItem);
      return myMenu;
   }
   private Menu getColorMenu() {
      Menu myMenu = new Menu("Color");
      MenuItem myItem = new MyMenuItem("Red");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Green");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Blue");
      myMenu.add(myItem);
      return myMenu;
   }
   private Menu getOptionMenu() {
      Menu myMenu = new Menu("Option");
      MenuItem myItem = new MyMenuItem("Sound");
      myMenu.add(myItem);
      myItem = new MyMenuItem("Auto save");
      myMenu.add(myItem);
      return myMenu;
   }
   private class MyMenuItem extends MenuItem 
      implements ActionListener {
      public MyMenuItem(String text) {
         super(text);
         addActionListener(this);
      }
      public void actionPerformed(ActionEvent e) {
         System.out.println("Item clicked: "+e.getActionCommand());
      }
   }
}
```

If you run this example, you will see the frame window shows up with the menu bar like this:

![](Images/image00205.jpeg)

AWT Menu Item Action Listener Test

If you click the "Help" menu item, click "Open" and "Close" in the "File" menu, then click "Red", "Green" and "Blue" in the "Color" menu, you will see some messages printed on the Java console window:

```
 Item clicked: Help
Item clicked: Open
Item clicked: Close
Item clicked: Red
Item clicked: Green
Item clicked: Blue
```

Interesting notes about this tutorial example:

*   "private class MyMenuItem extends MenuItem implements ActionListener" declaration is used to create an inner class, MyMenuItem, which extends MenuItem, implements ActionListener, and adds itself to handle action events.
*   "addActionListener(this);" statement is used to add my inner class, MyMenuItem, itself to handle action events.
*   "e.getActionCommand()" expression is used to get action command string, the menu item button text in this case.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Integration with Desktop System

This chapter provides tutorial notes and example codes on integration with the local desktop system. Topics include description of the javax.awt.Desktop class and its methods; example programs of launch default Web browser, email program and file editors of the local desktop system.

> [javax.awt.Desktop and Related Methods](#part0116.xhtml)
> 
> [browse() - Launch Default Web Browser](#part0117.xhtml)
> 
> [mail() - Launch Default Email Program](#part0118.xhtml)
> 
> [edit() - Launch Default Editor for Given File](#part0119.xhtml)

Conclusions:

*   javax.awt.Desktop class represents the local desktop system.
*   getDesktop() method can be used to get an instance of the current local desktop system.
*   browse​(URI) method can be used to launch the default Web browser with the given URI.
*   mail​(URI) method can be used to launch the default email program with the given mailto URI.
*   edit(File) method can be used to launch the default editor with the given file.

Sample programs listed in this chapter have been tested with JDK 1.6 to JDK 12.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Integration with Desktop System](#part0115.xhtml)

∟javax.awt.Desktop and Related Methods

This section describes the javax.awt.Desktop class, and its commonly used methods.

java.awt.Desktop - An AWT class that helps to integrate Java GUI applications with desktop functionalities of the operating system. It offers the following interesting methods:

*   getDesktop() - Method to return a Desktop object representing the current desktop of the operating system.
*   browse​(URI) - Method to launch the default Web browser with the given URI.
*   mail​(URI) - Method to launch the default email program with the given mailto URI.
*   edit(File) - Method to launch the default editor with the given file.

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Integration with Desktop System](#part0115.xhtml)

∟browse() - Launch Default Web Browser

This section provides a tutorial example on how to use Desktop.browe() method to launch the default Web browser on the desktop of the operating system.

If you want to launch the default Web browser on the current desktop of the operating system, you can get the default Desktop object and call its browse() method. Here is a sample program:

```
 /* DesktopWebBrowser.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
import java.net.URI;
public class DesktopWebBrowser {
   public static void main(String[] a) {
      try {
         URI uri = new URI("https://www.herongyang.com/Swing");
         Desktop desktop = Desktop.getDesktop();
         if (desktop != null) desktop.browse(uri);
      } catch (Exception e) {
        e.printStackTrace();
      }
   }
}
```

If you run this program, you will see the default Web browser is started with the given Website displayed. On my Windows 10 computer, I am getting the Edge browser launched.

![](Images/image00206.jpeg)

Launch Web Browser on Desktop

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Integration with Desktop System](#part0115.xhtml)

∟mail() - Launch Default Email Program

This section provides a tutorial example on how to use Desktop.mail() method to launch the default email program on the desktop of the operating system.

If you want to launch the default email program on the current desktop of the operating system, you can get the default Desktop object and call its mail() method. Here is a sample program:

```
 /* DesktopSendEmail.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
import java.net.URI;
public class DesktopSendEmail {
   public static void main(String[] a) {
      try {
     String address = "herong_yang@yahoo.com";
     String subject = "Java%20Swing%20Tutorials";
     String body = "I%20like%20your%20tutorial%20book!";
         URI uri = new URI("mailto:"+address+"?subject="+subject
        +"&body="+body);
         Desktop desktop = Desktop.getDesktop();
         if (desktop != null) desktop.mail(uri);
      } catch (Exception e) {
        e.printStackTrace();
      }
   }
}
```

Note that I have encoded the email address, subject and message body in the mailto URI string.

If you run this program, you will see the default email program is started with the given email content. On my Windows 10 computer, I am getting the Outlook app launched.

![](Images/image00207.jpeg)

Launch Email Program on Desktop

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Integration with Desktop System](#part0115.xhtml)

∟edit() - Launch Default Editor for Given File

This section provides a tutorial example on how to use Desktop.edit() method to launch the default editor for the given file based on the file type.

If you have a file and want to launch its associated default editor on the current desktop of the operating system, you can get the default Desktop object and call its edit() method. Here is a sample program:

```
 /* DesktopEditFile.java
 * Copyright (c) 1997-2018 HerongYang.com. All Rights Reserved.
 */
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
import java.io.File;
public class DesktopEditFile {
   public static void main(String[] a) {
      try {
     File file = new File("Swing.jpg");
         Desktop desktop = Desktop.getDesktop();
         if (desktop != null) desktop.edit(file);
      } catch (Exception e) {
        e.printStackTrace();
      }
   }
}
```

Make sure you have image file called Swing.jpg in the working directory. Then run this program, you will see the default image editor program is started with the given image file. On my Windows 10 computer, I am getting the "Paint" app launched.

![](Images/image00208.jpeg)

Launch File Editor on Desktop

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟Archived Tutorials

This chapter contains some outdated tutorial notes and example codes from previous versions of this book.

> [Archived: Downloading and Installing JDK 12](#part0121.xhtml)
> 
> [Archived: Downloading and Installing JDK 10](#part0122.xhtml)

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0120.xhtml)

∟Archived: Downloading and Installing JDK 12

This section describes how to download and install JDK 12 on a Windows system.

The current version of JDK is JDK 12, which is also called Java SE (Standard Edition) 12 Here is what I did to download and install JDK 12 on my Windows machine.

*   Open the Java SE Download page with this URL: [https://www.oracle.com/technetwork/java/javase/downloads/](https://www.oracle.com/technetwork/java/javase/downloads/).
*   Click the download button next to "Java Platform (JDK) 12". You will see a new page with a list of different download files of JDK 12.
*   Accept the license agreement.
*   Click the hyper link of "jdk-12.0.1_windows-x64_bin.exe", next to "Windows 158.49 MB".
*   Save jdk-12.0.1_windows-x64_bin.exe to a temporary directory.
*   Double-click on jdk-12.0.1_windows-x64_bin.exe to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

The picture below shows you how the JDK 12 Installation Screen looks like:

![](Images/image00209.jpeg)

JDK 12 Installation Screen

To test the installation, open a command window to try the java command. If you are getting the following output, your installation is good:

```
 herong> \progra~1\java\jdk-12.0.1\bin\java -version

java version "12.0.1" 2019-04-16
Java(TM) SE Runtime Environment (build 12.0.1+12)
Java HotSpot(TM) 64-Bit Server VM (build 12.0.1+12, mixed mode, sharing)
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟[Archived Tutorials](#part0120.xhtml)

∟Archived: Downloading and Installing JDK 10

This section describes how to download and install JDK 10 on a Windows system.

Here is what I did to download and install JDK 10 on my Windows machine.

*   Open the Java SE Download page with this URL: [http://www.oracle.com/technetwork/java/javase/downloads/](http://www.oracle.com/technetwork/java/javase/downloads/).
*   Click the download button next to "Java Platform (JDK) 10". You will see a new page with a list of different download files of JDK 10.
*   Accept the license agreement.
*   Click the hyper link of "jdk-10.0.1_windows-x64_bin.exe", next to "Windows 390.19 MB".
*   Save jdk-10.0.1_windows-x64_bin.exe to a temporary directory.
*   Double-click on jdk-10.0.1_windows-x64_bin.exe to start the installation wizard.
*   The installation wizard will guide you to finish the installation.

To test the installation, open a command window to try the java command. If you are getting the following output, your installation was ok:

```
 herong> \progra~1\java\jdk-10.0.1\bin\java -version

java version "10.0.1" 2018-04-17
Java(TM) SE Runtime Environment 18.3 (build 10.0.1+10)
herong> java HotSpot(TM) 64-Bit Server VM 18.3 (build 10.0.1+10, mixed mode)
```

[Java Swing Tutorials - Herong's Tutorial Examples](#part0001.xhtml)

∟References

List of reference materials used in this book.

*   *The Java Tutorials Trail: Creating a GUI With JFC/Swing*, Oracle, [docs.oracle.com/javase/tutorial/uiswing/](https://docs.oracle.com/javase/tutorial/uiswing/)
*   *Java Swing tutorial*, Jan Bodnar, [zetcode.com/tutorials/javaswingtutorial/](http://zetcode.com/tutorials/javaswingtutorial/)
*   *Package javax.swing*, Oracle, [docs.oracle.com/en/java/javase/12/docs/api/java.desktop/module-summary.html](https://docs.oracle.com/en/java/javase/12/docs/api/java.desktop/module-summary.html)
*   *Java Swing Icon* (Website not available anymore), [http://www.jsrsoft.com](http://www.jsrsoft.com)

![The Front Cover](Images/cover00210.jpeg)