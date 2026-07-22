![](images/calibre_cover.jpg)

Eclipse 4.5 Hello Course for Java Developers

An eight-twelve hour continuing education class

John R. Hines, Software Consulting Engineer, Inc., 1125 Country Club Rd, Lucas, TX 75002 ([JRHInLucas@Gmail.com](mailto:JRHInLucas@Gmail.com))

Copyright © Software Consulting Engineer, Inc.  All rights reserved.  2014-2016

“Plagiarism is when the author steals from one source; scholarship is when the author steals from many sources.”  -- Anonymous

"Facts are stubborn things; and whatever may be our wishes, our inclinations, or the dictates of our passions, they cannot alter the state of facts and evidence." --John Adams

Oholiab's First Law: The Suits' need for computing power expands until all the Geeks' servers are 100% utilized running database queries and printing reports during business hours.

Corollary to Oholiab's First Law: Development can only access the servers purchased for development when nobody else wants them.

Warning:  If you’re not smart enough to sort the cow pies from the pearls in these notes, you do not have permission to read them!

ISBN:  None

Version 1.00   201603112300

Contents

[Getting Started](#index_split_002.html_filepos27821)

> [Chapter 0:  Getting Started](#index_split_003.html_filepos27964)

> [Prerequisites](#index_split_003.html_filepos28060)

> [Terminology](#index_split_003.html_filepos28540)

> [Typefaces](#index_split_003.html_filepos30053)

> [What Eclipse version is used in this book?](#index_split_003.html_filepos32223)

> [What Windows version is used in this book?](#index_split_003.html_filepos32452)

> [Where did the exercises in these notes come from?](#index_split_003.html_filepos32835)

> [Where did these notes come from?](#index_split_003.html_filepos33547)

> [Why isn't this eBook copy protected?](#index_split_003.html_filepos34067)

> [Chapter 1: Why Eclipse 4.5?](#index_split_004.html_filepos34567)

> [What books should I read?](#index_split_004.html_filepos34662)

> [Why use the Eclipse IDE?](#index_split_004.html_filepos36349)

> [Why use Eclipse 4.5?](#index_split_004.html_filepos36875)

> [Chapter 2: Getting Started with Eclipse](#index_split_005.html_filepos37457)

> [How is the Eclipse project managed?](#index_split_005.html_filepos37565)

> [What are the 4.x versions of Eclipse?](#index_split_005.html_filepos37895)

> [What is a wizard?](#index_split_005.html_filepos39661)

> [What is Eclipse?](#index_split_005.html_filepos39899)

> [What is the Eclipse "Big Picture"?](#index_split_005.html_filepos40308)

> [What is Eclipsepedia?](#index_split_005.html_filepos40784)

> [What is open source?](#index_split_005.html_filepos41114)

> [What is the difference between Eclipse 3 and Eclipse 4?](#index_split_005.html_filepos41519)

> [What is the Eclipse architecture?](#index_split_005.html_filepos41960)

> [What is the Eclipse platform?](#index_split_005.html_filepos42192)

> [What is the Eclipse workbench?](#index_split_005.html_filepos42468)

> [What is Wiki?](#index_split_005.html_filepos42836)

> [When did Eclipse integrate Java 7?](#index_split_005.html_filepos43143)

> [When did Eclipse integrate Java 8?](#index_split_005.html_filepos43320)

> [Chapter 3:  Installing Eclipse 4 Java](#index_split_006.html_filepos43641)

> [Do I have a JAVA_HOME environment variable?](#index_split_006.html_filepos43783)

> [What version of Java do I have?](#index_split_006.html_filepos44512)

> [What’s a command line interface?](#index_split_006.html_filepos45106)

> [What's a release (version)?](#index_split_006.html_filepos45521)

> [What’s a visual IDE?](#index_split_006.html_filepos45783)

> [What’s a WIMP interface?](#index_split_006.html_filepos46012)

> [What’s a workspace?](#index_split_006.html_filepos46493)

> [What’s an IDE?](#index_split_006.html_filepos47258)

> [What should I know before I start installing?](#index_split_006.html_filepos47492)

> [Installation](#index_split_006.html_filepos49693)

> [Where do I find on-line help for mars?](#index_split_006.html_filepos58673)

> [Where do I find the meaning of Eclipse icons for mars?](#index_split_006.html_filepos58996)

> [Chapter 4:  Eclipse 4 terms](#index_split_007.html_filepos59570)

> [What’s a build (noun)?](#index_split_007.html_filepos59666)

> [What’s a bundle?](#index_split_007.html_filepos61137)

> [What’s a facet?](#index_split_007.html_filepos61552)

> [What's a feature?](#index_split_007.html_filepos61830)

> [What’s a file?](#index_split_007.html_filepos62037)

> [What’s a folder?](#index_split_007.html_filepos62284)

> [What's a perspective?](#index_split_007.html_filepos62589)

> [What’s a plug-in (plugin)?](#index_split_007.html_filepos63063)

> [What’s a project?](#index_split_007.html_filepos63309)

> [What's a resource?](#index_split_007.html_filepos63522)

> [What's a tag?](#index_split_007.html_filepos63781)

> [What's a task list?](#index_split_007.html_filepos64077)

> [What's a task view (task tab) (tag view)?](#index_split_007.html_filepos64268)

> [What’s a view?](#index_split_007.html_filepos64500)

> [What’s an editor?](#index_split_007.html_filepos64796)

> [What's "baked-in"?](#index_split_007.html_filepos65414)

> [What's JDT (Java Development Tools)?](#index_split_007.html_filepos65629)

> [What's the build path?](#index_split_007.html_filepos65978)

> [Chapter 5:  Eclipse 4 file system](#index_split_008.html_filepos66470)

> [How does the Eclipse platform organize information?  How does the Eclipse workbench organize information?](#index_split_008.html_filepos66608)

> [What's in a workspace directory?](#index_split_008.html_filepos67127)

> [What's in a project directory?](#index_split_008.html_filepos68248)

> [What's in the .metadata folder in the workspace?](#index_split_008.html_filepos70071)

> [Chapter 6:  Eclipse 4 IDE](#index_split_009.html_filepos70480)

> [Does the Java EE IDE look different from the Java IDE?](#index_split_009.html_filepos70703)

> [What are the three regions in the IDE?](#index_split_009.html_filepos71428)

> [What's in the "Menus and tool bar region"?](#index_split_009.html_filepos72263)

> [What's the difference between the Project Explorer view and the Package Explorer view?](#index_split_009.html_filepos75463)

> [What's the outline view?](#index_split_009.html_filepos76039)

> [What's the problem view (problem tab)?](#index_split_009.html_filepos76364)

> [Where can I find information about the icons used in the IDE?](#index_split_009.html_filepos76759)

> [Where do I find eclipse error logs?](#index_split_009.html_filepos77844)

[Creating basic Java apps using Eclipse](#index_split_010.html_filepos78077)

> [Chapter 7:  Create, build and run HelloWorld using the Eclipse IDE](#index_split_011.html_filepos78246)

> [Starting Eclipse](#index_split_011.html_filepos78417)

> [What does the error icon look like?](#index_split_011.html_filepos78840)

> [What does the warning icon look like?](#index_split_011.html_filepos79325)

> [What's a folding editor?](#index_split_011.html_filepos79819)

> [What is a warning?](#index_split_011.html_filepos80133)

> [What is an error?](#index_split_011.html_filepos80512)

> [What is an execution environment JRE?](#index_split_011.html_filepos81005)

> [What is code folding?](#index_split_011.html_filepos82054)

> [What is "drill down"?](#index_split_011.html_filepos82346)

> [What is Javadoc (JavaDoc)?](#index_split_011.html_filepos82950)

> [What is scope?](#index_split_011.html_filepos83872)

> [What is the difference between a closed project, an open project and an open expanded project?](#index_split_011.html_filepos84211)

> [What's the difference between the Project Explorer and the Package Explorer?](#index_split_011.html_filepos85582)

> [Exercise 7-1:  Create a Hello1 project](#index_split_011.html_filepos85874)

> [Exercise 7-2:  Create a Hello project with a main and comments](#index_split_011.html_filepos90316)

> [Exercise 7-3:  Compare HelloWorld.java and Hello1World.java](#index_split_011.html_filepos90910)

> [Exercise 7-4:  Close Hello and Hello1](#index_split_011.html_filepos92701)

> [Exercise 7-5:  Delete the Hello1 project](#index_split_011.html_filepos93136)

> [Exercise 7-6:  Add a method call inside Hello project's HelloWorld's main method](#index_split_011.html_filepos93784)

> [Exercise 7-7:  Run Hello project](#index_split_011.html_filepos95344)

> [Exercise 7-8:  Why a Hello project warning?](#index_split_011.html_filepos95888)

> [Exercise 7-9: Close Hello project](#index_split_011.html_filepos96806)

> [Questions](#index_split_011.html_filepos97133)

> [Chapter 8: Create a new project from the Hello project](#index_split_012.html_filepos98249)

> [What is a fully qualified name?](#index_split_012.html_filepos98665)

> [What is refactoring?](#index_split_012.html_filepos98889)

> [What is the launcher pattern (design pattern)?](#index_split_012.html_filepos99184)

> [What's a launcher?](#index_split_012.html_filepos99530)

> [Exercise 8-1:  Make a copy of the Hello project and name it HelloArgs](#index_split_012.html_filepos99762)

> [Exercise 8-2:  Make a copy of the Hello project into HelloLauncher](#index_split_012.html_filepos103027)

> [Questions](#index_split_012.html_filepos108760)

> [Chapter 9:  Debugging HelloLauncher](#index_split_013.html_filepos109431)

> [What is debugging](#index_split_013.html_filepos109571)

> [What is a breakpoint (break point)?](#index_split_013.html_filepos109812)

> [What does "Toggle breakpoint" mean?](#index_split_013.html_filepos110163)

> [Exercise 9 -1:  Debug HelloLauncher project](#index_split_013.html_filepos110466)

> [Questions](#index_split_013.html_filepos112562)

> [Chapter 10:  Reduce coupling with separation of responsibility (more but smaller classes)](#index_split_014.html_filepos113011)

> [What is @Override](#index_split_014.html_filepos113395)

> [What is coupling?](#index_split_014.html_filepos113843)

> [What is a provider?](#index_split_014.html_filepos114360)

> [What is a renderer?](#index_split_014.html_filepos114700)

> [What is SoR (Separation of Responsibilities)?](#index_split_014.html_filepos114978)

> [What is an annotation?](#index_split_014.html_filepos115461)

> [Exercise 10-1:  Improve Hello separation (Reducing Hello coupling) (Decoupling Hello)](#index_split_014.html_filepos116145)

> [Exercise 10-2:  Improving Hello separation with interfaces](#index_split_014.html_filepos120872)

> [Questions](#index_split_014.html_filepos122531)

> [Chapter 11:  Add a factory to improve Hello separation](#index_split_015.html_filepos123229)

> [What can be assigned to a class reference?](#index_split_015.html_filepos123388)

> [What can be assigned to an interface reference?](#index_split_015.html_filepos123793)

> [What's a child class?](#index_split_015.html_filepos124348)

> [What's a factory (factory class)?](#index_split_015.html_filepos124524)

> [What's a parent class?](#index_split_015.html_filepos124776)

> [What's a reference?](#index_split_015.html_filepos124955)

> [What's a class reference?](#index_split_015.html_filepos125306)

> [What's an interface reference?](#index_split_015.html_filepos126144)

> [Why do I care about class references and interface references?](#index_split_015.html_filepos126414)

> [Exercise 11-1:  Improving Hello separation by adding a factory](#index_split_015.html_filepos126650)

> [Exercise 11-2:  Improving Hello separation by adding a factory Part 2](#index_split_015.html_filepos134432)

> [Chapter 12:  Reduce coupling even more with a smarter factory](#index_split_016.html_filepos136269)

> [What is Spring?](#index_split_016.html_filepos136435)

> [What's a user library?](#index_split_016.html_filepos136998)

> [What's an appender?](#index_split_016.html_filepos137217)

> [What's an external jar?](#index_split_016.html_filepos137415)

> [Exercise 12-1:  Improving Hello separation by using a factory from Spring Framework](#index_split_016.html_filepos137682)

> [Exercise 12-2:  Improving Hello separation clean up](#index_split_016.html_filepos149711)

> [Questions](#index_split_016.html_filepos150484)

> [Chapter 13:  Reduce coupling even more with DI (dependency injection)](#index_split_017.html_filepos150889)

> [What is deprecated?](#index_split_017.html_filepos151485)

> [What is DI (Dependency injection)?](#index_split_017.html_filepos151836)

> [Exercise 13-1:  Improving Hello separation by using Spring and DI](#index_split_017.html_filepos152503)

> [Exercise 13-2:  Improving Hello separation by using Spring, DI and more Xml](#index_split_017.html_filepos158167)

> [Questions](#index_split_017.html_filepos161339)

> [Chapter 14:  Export an existing project, import an existing project](#index_split_018.html_filepos161789)

> [What does export mean in Eclipse?](#index_split_018.html_filepos161961)

> [What does export mean in Java?](#index_split_018.html_filepos162319)

> [What does import mean in Eclipse?](#index_split_018.html_filepos162663)

> [What does import mean in Java?](#index_split_018.html_filepos163005)

> [What is EAR file format?](#index_split_018.html_filepos163371)

> [What is JAR file format?](#index_split_018.html_filepos163819)

> [What is WAR file format?](#index_split_018.html_filepos164352)

> [What's a Jar (Java ARchive)?](#index_split_018.html_filepos164677)

> [What's an executable jar file?](#index_split_018.html_filepos165563)

> [What's an EAR (Ear file) (EAR file) (Enterprise ARchive file)?](#index_split_018.html_filepos165879)

> [What's extract required libraries?](#index_split_018.html_filepos166294)

> [What's package required libraries](#index_split_018.html_filepos166505)

> [Questions](#index_split_018.html_filepos166774)

[Appendices](#index_split_019.html_filepos167076)

> [Appendix I:  Answers to questions](#index_split_019.html_filepos167183)

> [Chapter 7](#index_split_019.html_filepos167285)

> [Chapter 8](#index_split_019.html_filepos169683)

> [Chapter 10](#index_split_019.html_filepos170194)

> [Chapter 12](#index_split_019.html_filepos170693)

[Author's Biography](#index_split_019.html_filepos171340)

Getting Started

Chapter 0:  Getting Started

Prerequisites

Students must:

•      Have some experience with Java.  (If you can't write the HelloWorld.java program, compile it and run it, you don't have the background to succeed in this class.)

•      Have a memory stick (4GB or bigger) and bring it to every class. 

Terminology

|  Terminology  |  Description  |
|  Click   |   Left click on a screen object.  Unless right is in front of the word click, always a left click. |
|  Highlight  |   Drag mouse from left to right to highlight.  Sometimes, just clicking anywhere on the selection is enough to highlight it. |
|  Mouse over  |   Move the mouse on top of a tool icon and pause.  A hint should pop up. |
|  Right click (Right-click)  |   Right click on a screen object.  |

Typefaces

The following terminology is used when describing Java syntax.

|  Typefaces  |  Description  |
|  Courier plain text  |  required  |
|  Courier bold text  |  default  |
|  Courier italics  |  user-defined  |
|  a&#124;b  |  a or b  |
|  [ ]  |  optional choice  |
|  { }  |  required choice  |
|  …  |  list of items  |
|  +  |  can repeat  |

What Eclipse version is used in this book?

The screen shots and key clicks are from Eclipse 4.5.1 EE.

What Windows version is used in this book?

The screen shots and key clicks are from Windows 10 Pro.  Windows 7 and Windows 8.1 will look (and click) slightly differently.  If you're running Windows 8 (not 8.1) you may have problems (everyone else did).

Where did the exercises in these notes come from?

I first saw a collection of more and more complex Hello programs that eventually emphasized Spring Framework in a PDF attributed to Rebecca Ong.  Since, I have seen similar collections of Hello programs associated with other developers.  The last exercise came from Oz Brown at Collin County Community College Continuing Ed. 

Most of my examples are slightly different since my goal is to teach Eclipse creation and editing, not to teach object-oriented programming.  But, thanks to Rebecca and Oz.

Where did these notes come from?

These notes are the result of thirty years of programming and twenty years of web searches.  Which means that some sections are not the latest and greatest. However, they describe ways of getting things done.

(What can you expect from someone who started programming in GW Basic and wrote his first book in Windows Write 1.0?)

Why isn't this eBook copy protected?

You will want to cut and paste from the book.  I recommend you use Calibre to convert this book to DOCX.  You can expand the images so you can see them better.

BTW:  If you want an Eclipse course taught at your company, send me an email at JRHInLucas@Yahoo.com.

Chapter 1: Why Eclipse 4.5?

What books should I read?

A good short book is Lars Vogel's Eclipse IDE ([http://www.amazon.com/Eclipse-IDE-vogella-Lars-Vogel-ebook/dp/B006O1J39S/ref=sr_1_3?s=books&ie=UTF8&qid=1457579814&sr=1-3&keywords=lars+vogel](http://www.amazon.com/Eclipse-IDE-vogella-Lars-Vogel-ebook/dp/B006O1J39S/ref=sr_1_3?s=books&ie=UTF8&qid=1457579814&sr=1-3&keywords=lars+vogel)). 

A good but very pricey book is Ram Kulkarni's Java EE Development with Eclipse ([http://www.amazon.com/Java-Development-Eclipse-Ram-Kulkarni-ebook/dp/B014HFNB40/ref=sr_1_13?s=books&ie=UTF8&qid=1457579962&sr=1-13&keywords=eclipse+computer](http://www.amazon.com/Java-Development-Eclipse-Ram-Kulkarni-ebook/dp/B014HFNB40/ref=sr_1_13?s=books&ie=UTF8&qid=1457579962&sr=1-13&keywords=eclipse+computer)).

A useful but complex book in the almost useless dead tree format is Kate Thompson's Zero Bugs and Program Faster ([http://www.amazon.com/Zero-Bugs-Program-Faster-Thompson/dp/0996193308/ref=sr_1_38?s=books&ie=UTF8&qid=1457580123&sr=1-38&keywords=eclipse+computer](http://www.amazon.com/Zero-Bugs-Program-Faster-Thompson/dp/0996193308/ref=sr_1_38?s=books&ie=UTF8&qid=1457580123&sr=1-38&keywords=eclipse+computer)).  Only recommended for experienced programmers with good eyes.

Why use the Eclipse IDE?

In 2014 (last year data was available), Eclipse (free) has 48% of the IDE market, IntelliJ (big bucks) has 33%, NetBeans (free) has 10%, and Spring (free, based on Eclipse) has 4%.  Unless you want to develop both Java and Android applications using the same (well, similar) IntelliJ IDE, Eclipse is the tool of choice, especially at frugal companies.  (Eclipse is free.)

Why use Eclipse 4.5?

It's the second version on Eclipse based on Java 8.  It's solid and reliable.

Chapter 2: Getting Started with Eclipse

How is the Eclipse project managed?

All work at Eclipse is done in sub-projects and components organized under top-level projects. Top-level projects are managed by PMCs (project management committees).

What are the 4.x versions of Eclipse?

|  4.2  |  Juno  |  First Eclipse 4   |
|  4.3  |  Kepler  |  Maven integration  |
|  4.4  |  Luna  |  Java 8 integration  |
|  4.5  |  Mars  |  Support for Java lambda expressions  |
|  4.6  |  Neon  |  To be released in June, 2016.   Prerelease versions available now. |

What is a wizard?

A fill-in-the-boxes windows that simplifies creating something.  Eclipse is big on wizards.

What is Eclipse?

An open source community of software developers who are focused on building an open development platform with extensible frameworks, tools and runtimes that will build, deploy and manage software across the software lifecycle. Alternate:  The Eclipse platform. 

What is the Eclipse "Big Picture"?

![](images/00001.jpg)

An alternate look at the big picture is shown below:

![](images/00011.jpg)

What is Eclipsepedia?

Eclipsepedia ([http://wiki.eclipse.org/Main_Page](http://wiki.eclipse.org/Main_Page)) is a Wiki that contains much Eclipse knowledge.

What is open source?

The term open source describes applications that make source code available for others to view and modify.   Open source applications are not necessarily public domain; they are often licensed.  Eclipse is distributed with the Eclipse Public License. 

What is the difference between Eclipse 3 and Eclipse 4?

Eclipse 3 is Java 6 (except 3.7.1 or 3.7.2).  Eclipse 4 is Java 7 (or Java 8).  Also, Eclipse 4 supports "modeled UI, dependency injection and service-based programming model, CSS-based styling."  Note:  Eclipse 4 also has an Eclipse 3 simulation mode.

What is the Eclipse architecture?

![](images/00010.jpg)

What is the Eclipse platform?

The extensible IDE developed by the Eclipse project to host its projects.  Alternative:  Tool for creating projects.

What is the Eclipse workbench?

The Eclipse platform.  "Workbench is the term used for the generic Eclipse UI. Originally … called the desktop but because Eclipse was a platform primarily for tools … workbench was deemed more suitable."

What is Wiki?

A website that that uses the Wiki engine.  Site visitors can add, remove, and otherwise edit and change content, typically without being registered at the web site.

When did Eclipse integrate Java 7?

Eclipse 3.7.1.

When did Eclipse integrate Java 8?

Eclipse 4.4.  However, Eclipse 4.5.1 will run under Java 7 with some minor issues.

Chapter 3:  Installing Eclipse 4 Java

Do I have a JAVA_HOME environment variable?

Right-click on "Start->System".  When the System window appears, click on "Advanced system settings".  When the "System Properties" popup appears, click on "Environment Variables".  When the "Environment Variables" pops up, scroll down the "System Variables".  If you don't see JAVA_HOME, click on "New…" and fill in the "New System Variable" form.  The variable value should be the location of your jdk.  Click on all the "OK" buttons to save and return to the System" window.  Click on the x in the upper right hand corner to close the window.

What version of Java do I have?

Right-click on the Start icon and select Command Prompt (Admin).  When the cmd window pops up, type "java -version [ENTER]".  It should show some version of build 1.8 and some version of SE Runtime Environment.  (If not, download the jdk from [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).) 

What’s a command line interface?

Non-graphical user interface where the command line echoes typed characters on the monitor.  It is usually identified by a flashing cursor following a "$", ">", or a drive name and a backslash (the prompt) and whatever text the user has entered. 

What's a release (version)?

Significantly different version of Eclipse.  (Different enough that you'd better read the documentation.)

What’s a visual IDE?

Allows developers to program by pointing, clicking and dragging-and-dropping.

What’s a WIMP interface?

Acronym for Windows-Icon-Mouse-Pulldown Menus interface that lets users create, edit, debug and deploy classes, components, applets and applications without leaving the environment.  Command line interface developers think WIMP interface users are wimps.  WIMP interface users think command line users have low productivity.

What’s a workspace?

Manages a group of Eclipse resources regardless of where they are located. The workspace contains Eclipse projects.  The Eclipse Platform typically has a single workspace.  However, newer versions of Eclipse tend to overwrite information need by older versions so you may want to have a workspace for ach version of Eclipse you use.

How do I start eclipse using some predetermined workspace?

Create a batch file with the single line like "C:\eclipse\Mars 4.5.1 EE \eclipse.exe" -data C:\MyCode\workspace-mars-hello.

What’s an IDE?

Acronym for Integrated Development Environment, a development tool with a WIMP interface.

What should I know before I start installing?

Where to install eclipse, what version of eclipse, which type of eclipse IDE, 32- or 64-bit Windows, directory that will contain workspaces.  Warning:  Don't use spaces in directory of file names.  It may not matter.  But, it might.  Don't do it!

|  Option  |  Suggestion  |
|  Where should I install Eclipse?  |   Under a root directory named Eclipse.  You can install multiple versions of Eclipse in this directory. |
|  What version of Eclipse should I install?  |  Mars EE (Eclipse 4.5.1)  |
|  Do I have 32- or 64-bit Windows?  |  You'll have to find out by running "System Information".  |
|  What directory will contain workspaces?  |  To avoid privileges issues, create a root (C:\)  directory named MyCode (no spaces).  |
|  Should you avoid spaces in names?  |   Absolutely.  It may not hurt.  But, it might. |

Installation

Warning:  The fundamental rule for all installations is don't change anything you are not absolutely sure you understand.

Step 1:  What release (version) to install?

Either install the current version of Eclipse (Eclipse 4.5.1, Mars in January, 2016) or whatever version your company uses.  Warning:  Never install a new version (of any kind of software) until two or three months after its release. ("Never use version x.0.")  Eclipse does releases in June so install the previous version in June and July.

If you install version 4.3 or newer, you will be using Java 8 by default.  If you install version 4.2 or 3.7, you will be using Java 7 by default.

Before you go to Step 2, you should know the version of eclipse you want to install.

Step 2:  What type to install (classic ide, standard ide, Java ide or Java EE ide)?

If you install the "classic" ide version of eclipse (3.7, 4.2), you will have to manually install a build system, desktop development tools, Java development tools, a version control system, and XML tools. (Not recommended.)

If you install the "standard" version of eclipse (4.3), you will have to manually install a build system and XML tools.  (Not recommended.)

If you install the Java ide version of eclipse (4.3 or newer), you will not have to manually install any of the above.  (Not recommended if you plan on doing databases or web development.)

If you install the Java EE ide version of eclipse, you also get data tools and a bundle of web development tools.  The ide is a little more complex but you don’t have to learn a slightly different ide if you have to move to EE.

Before you go to Step 3, you should know the version and type (Classic ide, Standard ide, Java ide, or Java EE ide).

Step 3:  32- or 64-bit Windows?

If you are running Windows, you need to know if you are running 32-bit or 64-bit Windows.  Click on the Start icon, click on "All apps->Windows Administrative Tools->System information".  Look for "System Type".

Before you go to Step 4, you should know what version of Windows you have.

Step 4:  Go to the eclipse website

Go to [https://www.eclipse.org/ide/](https://www.eclipse.org/ide/)

![](images/00007.jpg)

Select Java IDE or Java EE (recommended).  Select the release you want.

![](images/00021.jpg)

Select OS.

![](images/00014.jpg)

Download Eclipse.  Warning:  You may get "gifts" if you download from one of the Members.  To avoid complications, click on the left side download button.

Note:  The end of the name of the file (win32-x86_64.zip) tells you that you are going to download the 64-bit version of the file.  Wait patiently!  (BTW:  The donation is optional.) 

![](images/00009.jpg)

Step 5:  Unzip and deploy Eclipse.

In File Manager, go to the download directory, right click on the zip file and select "extract all" and select the default destination.  You may find it's helpful to put the eclipse file system inside a directory named Eclipse.  When eclipse releases a new version, you can install the new version next to the current version.  

Step 6:  Decide where you are going to save your source files

Drill down to find eclipse.exe.  Double click on it.  Wait!  When the "Select a workspace" popup appears, enter the directory where you want your source saved.  If you select the default, 64-bit Windows may require privilege tweaking to see the contents of the default directory under Users.  (I recommend creating a root directory named MyCode then a subdirectory named "workspace-mars-hello".)  Note:  Many new versions of Eclipse "upgrade" a workspace which prevents older versions of Eclipse from using it.  So, giving each a name like "workspace-mars" that indicates the release using it is helpful:  each version will have its own unique workspace. 

![](images/00013.jpg)

Step 7:  View the Welcome screen

After you’ve selected the workspace, the eclipse start screen appears while it loads.  Eventually, the Welcome screen appears.  Look through the links on the page.  Once you’re done, close the Welcome window by clicking on the x to the left of Welcome (you will no longer see this page when you start Eclipse) or click on the "workbench" icon in the pane's upper right corner.

![](images/00003.jpg)

Step 8:  Look at help

When the workbench pops up, click on "Help".  Look through the help.  Note:  You can get back to the Welcome screen through the Help dropdown menu.  Start the "Cheat sheets" popup from the Help dropdown menu.  Start the "About" popup from the Help dropdown menu. 

If you’ve installed the Java IDE, it should look something like this.

![](images/00022.jpg)

If you installed the Java EE IDE, it should look something like this.

![](images/00023.jpg)

Step 9:  Look at your workspace

(This may require privilege tweeking.)  Use File Manager to look at your workspace.  The .metadata folder indicates you're in a workspace.  You may also see a directory called RemoteSystemsTempFiles.  (It's a free gift from eclipse that's created by the remote systems explorer.  Ignore it.  Or, google it and note how many users want to make it go away but have difficulty doing so.)

Step 10:  Set helpful defaults

Click on "Windows->Preferences".  Scroll through the top-level preferences.  You will spend most of your time in the Java top-level preferences in this class, the rest in the General preferences.  Ignore the others for now.

Go to "General->Startup and Shutdown->Workspaces" and select your workspace for the Hello projects and click on "Apply".  Shrink the General sub-preferences.  Do NOT click on "OK" unless you want to return to the eclipse windows.

Go to "Java->Build Path->Installed JREs->Execution Environment".  Click on "JavaSE-1.8" (compatible with jdk 1.8 and higher) then click on the checkbox next to a jre currently installed in your environment.

Click on "OK" to close the Preferences window.

Step 11:  Look through all the dropdowns and mouse over all the icons 

You may need to click on a blank space on the tool bar to close a dropdown or a tool popup (no program is perfect.  ").  Grayed out dropdowns and buttons are currently disabled.

Step 12:  Done

You’ve successfully installed eclipse.  Congratulations.

Where do I find on-line help for mars?

Go to [http://help.eclipse.org/mars/index.jsp](http://help.eclipse.org/mars/index.jsp).

Where do I find the meaning of Eclipse icons for mars?

Look in [http://help.eclipse.org/mars/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Freference%2Fref-icons.htm](http://help.eclipse.org/mars/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Freference%2Fref-icons.htm).

Chapter 4:  Eclipse 4 terms

What’s a build (noun)?

A build project resource created by a builder from other resources of that project.  Build (verb) is what a builder does.

What’s a builder?

A tool that converts one or more resources in a project into another resource (called a build) in the project.  All eclipse builders are incremental - after full build (sometimes called a "build all"), the builder only builds what has changed since the last build (sometimes called a "rebuild").  A builder is always associated with a project.

What’s a full build?

A build where all resources in the project are built.

What’s an autobuild?

An incremental build triggered automatically because (1) a resource has changed and (2) the autobuild feature is on.  Note:  unless you are doing something unusual, autobuild should be on!

What’s an incremental build?

A partial build that starts with the results of a previous build and only modifies what's been changed.  Faster!

What’s a bundle?

A mechanism for grouping, delivering, and managing content.  Think of bundles as the implementation of components in Eclipse.  There is no distinction in Eclipse between bundles and plug-ins. Note:  Every bundle has its own classloader and its own manifest.mf file.

What’s a facet?

A facet is a unit of functionality that can be added to a project.  Java is a facet.  (And a feature.  And several other things.)

What's a feature?

Group of related plug-ins.  (JDT is a feature, for example.)

What’s a file?

A virtual (or actual) file associated with a project or a folder in a project in an Eclipse workspace.

What’s a folder?

A virtual (or actual) directory associated with a project in an Eclipse workspace.  Folders are useful tools for storing project resources hierarchically. 

What's a perspective?

Collection of editors and views that share some common purpose.

What's the current perspective?

The perspective highlighted in the far right of the toolbar.  The current perspective controls the appearance of the main Window.

What’s a plug-in (plugin)?

Fundamental building block of the Eclipse platform.  JDT is a collection of plug-ins. 

What’s a project?

A container that groups resources into buildable, reusable units.

What's a resource?

Either a project, a folder, or a file.  Projects can contain folders and/or files.  Folders can contain files.

What's a tag?

Marker (special text) placed in code to indicate work to be done later at the location of the tag.  Eclipse tags can found with the Task tab (Task view).

What's a task list?

List of tasks associated with bug trackers.

What's a task view (task tab) (tag view)?

List of tags in source files that need to be replaced by code.

What’s a view?

A window with a graphical display of an Eclipse resource.   Eclipse makes no distinction between a view and the perspective in which it is displayed.

What’s an editor?

An editable view of a resource.  It provides customized behavior for manipulating the data represented by the resource.  Different editors are associated with different types of files. When you open a file for editing by double-clicking it in one of the navigation views, the Workbench opens the associated editor in the Workbench. If there is no associated editor for a resource, the Workbench attempts to launch an appropriate external editor outside the Workbench.

What's "baked-in"?

Euphemism for built-in (developed by eclipse, not by a third-party).

What's JDT (Java Development Tools)?

The JDT is what makes the Eclipse Java IDE different from the Eclipse C/C++ IDE or ….    BTW:  JDT is a feature, not a plug-in.  Many developers misuse the term feature, though.

What's the build path?

Specifies all dependencies required to complete a project.  Code and other resources (in source folders), associated jars and classes folder(s), and classes and libraries referenced by (needed by) the project.

Chapter 5:  Eclipse 4 file system

How does the Eclipse platform organize information?  How does the Eclipse workbench organize information?

The workbench organizes information by workspace then by project in that workspace.  When the Eclipse workbench starts, it asks the user to select a workspace if the user has not selected a default workspace.  Eclipse loads all the projects in that workspace into Project Explorer.

What's in a workspace directory?

|  .metadata  |  Look for error logs here!  |
|  .recommenders  |  JSON files.  |
|  RemoteSystemsTempFiles  |   Created by eclipse's remote system explorer.  Ignore this. |
|  Various project directories  |  Your projects.  |

What's in a project directory?

|  .settings directory  |  Project-unique settings  |
|  bin  |  Binary files created by eclipse.  |
|  src directory  |  Project-unique resources  |
|  target directory  |  Files created from resources  |
|  .classpath file  |  Optional xml file created by maven  |
|  .project file  |  Optional xml file created by maven  |
|  pom file  |  Optional xml file created by maven  |

What's in the .metadata folder in the workspace?

Plugins store information in the folder.  Also, the eclipse error .log file is stored in the folder.

Chapter 6:  Eclipse 4 IDE

Warning:  The images are from my Windows 10 development box.

Does the Java EE IDE look different from the Java IDE?

Yes.  When you first start the IDE, the title bar of the Java EE IDE says "Java EE Eclipse" while the Java IDE says "Java IDE".  The tab below the menu bar on the Java EE IDE says "Project Explorer" while the Java IDE says "Package Explorer".  The Perspective panel to the far left of the toolbar in Java EE IDE says "Java EE" while the Java IDE says "Java".  And, the panel at the bottom of the IDE shows different choices. Warning:  This is the last reference I’ll make to the Java IDE.  Everything below relates to the Java EE IDE.

What are the three  regions in the IDE?

Both the Java and Java EE IDEs have the same three regions: (1) "Menus and the toolbar region" at the top of the IDE, (2)"Main region" ("Big picture region" on the left below the menus and toolbar and "Detail region" on right below the menus and toolbars) and (3) "Current status region" at the bottom.  Most of your work is in the Main region; some of it is done in the Menus and toolbar region; almost none of it is in the Current status region.

![](images/00019.jpg)

What's in the "Menus and tool bar region"?

Mostly self-explanatory to a developer who's used other Windows IDEs:   just run the mouse over them.  (Warning:   you may have to click on a tool and wait a few seconds before the hints are visible.  You may also have to click on a nearby empty space to close a menu or a tooltip.)  However, the area to the right of the last dashed vertical line has some unusual things. 

What does "Open perspective" (the grid box to the right of the last dotted vertical bar) on the tool bar do?

Pops up the "Open Perspective" window so you can add a perspective (and its tools) to the current project.  For example, adding the Java perspective adds new options to the Project Explorer.  (It will also add the Package Explorer" to the "big picture" region.

What does "Quick Access" box (the text box to the right of the last dotted vertical bar) on tool bar do?

You can directly run searches from the box.  (The box is near the far right on the tool bar.)

What's in the "Main region" (everything between the tool bar region and the current status region)?

The big picture view and the detail view.

What's the "Big-picture region" (Big-picture view) (Big-picture pane) (Big-picture window)?

After installation (can be moved), the smaller window on the left side of the "Main region" below the buttons and above the bottom margin.  The project and package explore appear as tabs in this view.

What's the "Detail region" (Detail view) (Detail pane) (Detail view)?

After installation (can be moved), the large window on the right side of the main pane below the buttons and above the bottom margin.

What are the three regions (views) (windows) (panes) in the detail region?

The editor views, the outline views sit on top the output view (can be moved).  Warning:  There are many tabs and each perspective has its own input and output views.  You can move them around.  However, until you know what is what, it’s better to leave everything in its default position.

These is just startup views.  And, you can move them around.  However, until you know what is what, it’s better to leave everything in its default position.

![](images/00005.jpg)

What's the difference between the Project Explorer view and the Package Explorer view?

The Project Explorer is a hierarchical view of the artifacts in the Workbench (customized by the specific configuration of your Workbench).  It can be used for many languages and project types.  Additional plugins contribute "extra information" to the Project Explorer view making it much more "sophisticated".  For example, when the JDT (Java developer tools) plugin is installed in the Project Explorer, many of the features in the Package Explorer (part of JDT) appear in the Project Explorer when it is used for java projects.

What's the outline view?

In the Java and Java EE perspectives, the outline tab in the outlines and tasks regions shows of the currently selected class.  It is always visible in these perspectives.

What's the problem view (problem tab)?

In the Java and Java EE perspectives, the problem tab in the output region showing errors and warnings.   You normally have to bring up the problem view by clicking on "Window->Show View->Other->General->Problems".

Where can I find information about the icons used in the IDE?

For Mars, look in [http://help.eclipse.org/mars/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Freference%2Fref-icons.htm](http://help.eclipse.org/mars/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Freference%2Fref-icons.htm) .  For Luna, look in [http://help.eclipse.org/luna/index.jsp?topic=/org.eclipse.jdt.doc.user/reference/ref-icons.htm](http://help.eclipse.org/luna/index.jsp?topic=/org.eclipse.jdt.doc.user/reference/ref-icons.htm) .

Where do I find on-line help for Eclipse?

Try [http://help.eclipse.org/mars/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Freference%2Fref-icons.htm](http://help.eclipse.org/mars/index.jsp?topic=%2Forg.eclipse.jdt.doc.user%2Freference%2Fref-icons.htm) .

Where do I find eclipse error logs?

Look in the .metadata folder.

Creating basic Java apps using Eclipse 

Chapter 7:  Create, build and run HelloWorld using the Eclipse IDE

Starting Eclipse

When you start Eclipse, the Welcome tab should not appear.  (You closed it during installation.)  If it does, close it.  Click on "File".  When the dropdown menu appears, click on "Switch Workspace" and select your Hello workspace (I'm using C:\MyCode\workspace-mars-hello).

What does the error icon look like?

Circle with a red triangle containing an "!" in the left hand side of the Java editor view.  The triangle is in the lower right corner. ![](images/00016.jpg) (quick fixable error) or ![](images/00015.jpg) (more complex error).

What does the warning icon look like?

Circle with a yellow triangle containing an "!" in the left hand side of the Java editor view.  The triangle is in the lower right corner. ![](images/00020.jpg) (quick fixable warning) or ![](images/00002.jpg) (more complex warning).

What's a folding editor?

Allows user to hide and reveal blocks of text—usually named. Typically done to allow the user to better picture the overall structure of a document or program.

What is a warning?

Message sent to the user during build that warns of some unusually (usually abnormal) condition that isn't serious enough to throw an exception and terminate execution.  The app will run but probably won't give the desired results.

What is an error?

Message sent to the user during build warns of some error condition that is serious enough to throw an exception and terminate execution, possibly serious enough to prevent execution.  Alternative:  Run-time environment internal error or resource problem that prevents the application from continuing.  Must be fixed before the program can run.

What is an execution environment JRE?

Oldest allowable JRE runtime on the target (destination) computer.  The JRE used to build an app can be a newer version than the runtime version as long as the build knows what the oldest allowable JRE is.

What is a CDC-1 execution environment?  What is a JRE1-1 execution environment?  What is an OSGi/Minimum execution environment?

Java 1.0, 1.1 or (sometimes) 1.2 compatible target.  Curiosity value only.

What is a J2SE-1.x environment?

J2SE 1.1, …, or 1.5 compatible target.  Mostly curiosity value.

What is a JavaSE-1.x environment?

J2SE 1.6, 1.7 or 1.8 execution environment.

What is code folding?

Editor’s ability to compress and expand code, markup language, and comment blocks.  Code folding simplifies navigating through large files.

What is "drill down"?

In inverted tree structures (like a file system), clicking on a series of nodes to get to some special place in the structures.  For example, open File Manager, click on the C: drive to see the root directories, then click on Windows to see the windows directories, then clicking on System32 to see the windows system software, then ….

What is Javadoc (JavaDoc)?

Tool that parses the declarations and documentation comments in a set of source *.java files and produces a set of HTML pages describing the classes, inner classes, interfaces, constructors, methods, and fields.

How do I recognize a Javadoc comment?

Begins with /**, may have multiple lines, and ends with */.  (Not the same as a C comment which begins with /* and ends with */).

How do I see a Javadoc?

Open the Javadoc view.  (Click on Window.  When the dropdown appears, click on "Show View-> Java->Javadoc".  A Javadoc tab will appear in the output region.)

What is scope?

Characteristic of a type or data item that describes the region where the type or data item name can be safely used without conflict or confusion.  See class scope, local scope and module scope.

What is the difference between a closed project, an open project and an open expanded project?

In Project Explorer, a closed project is a single line with a closed folder icon and the project name; an open project is a single line with a ">" icon, an open file icon, and the project name; an open expanded project is on multiple lines, a down pointing arrow icon, an open file icon (the project name on the first line and then a list of resources directly under the project).

How do I change a closed project into an open project?

Double click on the closed folder icon.

How do I change an open project to an open expanded project?

Double click on the open folder icon.  Or, just click on the ">" icon.  BTW:  In general, clicking on the ">" means "Show the next layer down".

How do I change an open or open expanded project into a closed project?

Right click on the project name.  When the dropdown appears, click on "Close Project".

What's the difference between the Project Explorer and the Package Explorer?

The Project Explorer shows all projects.  The Package Explorer shows a single project.

Exercise 7-1:  Create a Hello1 project

You create projects in the Project Explorer tab in the "big picture" region. 

> Possible misstep 7-1

> Right click on the tab at the top of Project Explorer main window.  A dropdown with the entry "close" pops up.  Click on "close".  What happens?   BTW:  You can get back to the default IDE regions and formats by right clicking on the "Java EE" icon at the far right then selecting "reset".

![](images/00006.jpg)Right click on the Project Explorer main window (not on tab at the top).  When the dropdown appears, click on "New->Project".  When the "Select a wizard" popup appears, select "Java->Java Project" then click on "Next".  When the "Create a Java Project" wizard appears, enter the project name (Hello1)click on the checkbox next to "Use default location", and click on "Finish". 

When the "Open Associated Perspective?" popup appears, click on "Yes".  (Don't click on "Remember my decision".  Never change a default until you understand the implication of changing it!)  Notice you now have two perspectives, Java EE and Java.  (What is the current perspective?  Which one is highlighted?) 

> Possible misstep 7-2

> What happened to the toolbars when "Java" became the current perspective?  What happened in the "Big picture region" when Java became the current perspective?  Click on the "Java EE" icon to make Java EE the current perspective.  Same questions.  If you're not seeing what you expect in the toolbars or in the big picture region, you may be in the wrong current perspective.  BTW:  What buttons appear in the "Java" perspective toolbars that are missing in the "Java EE" perspective toolbars?

> Possible misstep 7-3

> What happened in the "big picture" region?   Bring back the Project Explorer tab in the "big picture" region by clicking on "Window->Show View->Project Explorer".   You should see both a Package Explorer tab and a Project Explorer tab in the "big picture" region.

Using File Manager, go look in your workspace directory for the Hello1 project (it should be there).  In File Manager, expand the Hello1 directory if it's not open expanded.  What folder and files do you see under the project name?  Source folders named .settings, bin (maybe), and src as well as the .classpath and .project files.  

> Possible misstep 7-4

> Why do you see strange icons instead of the file and directory names?  These are "dot" files (they don't have a name in front of the dot).  "dot" files and folders are usually treated as invisible.  BTW:  In File Manager, go back to workspace directory.  Double click on the "dot" file with the paper icon.  Notepad or some other editor will bring up the .log file!  You can see what errors eclipse has been writing to ".log" since you installed it.

In Project Explorer, click on the ">" next to Hello project. Right click on "src" then, when the popup menu appears, click on "New->Class".  When the dropdown menu appears, click on "New->Class".  When the "Java Class" window appears, enter the name "Hello1World" then click the "Finish" button.

Still in Project Explorer, where is the Hello1Word.java file located?  What package is it in?  (Eclipse created a default package since you didn't enter one and placed the java file in that package.)

![](images/00012.jpg)Exercise 7-2:  Create a Hello project with a main and comments

Repeat Exercise 7-1 except use the project name "Hello".  Don't forget to create java file "HelloWorld".  (Same name, different project!  Sounds like scope, doesn't it.)  When the "Java Class" window appears, check the checkboxes next to "public static void main…" and "Generate comments".

Exercise 7-3:  Compare HelloWorld.java and Hello1World.java

In the Project Explorer, both Hello1 and Hello should open projects. Make both projects open and expanded by clicking on the ">" icon.  Drill down to the HelloWorld classes.  Double click on HelloWorld.java and it appears in the "Editors" pane of the detail region.  Double click on Hello1World.java and it appears in a second tab of the "Editors" pane.  To see both at the same, click and hold the mouse on Hello1World.java's tab, drag it to the left until a smaller pane appears, then release the mouse button.  What differences do you see?  HelloWorld.java has shells for Javadocs and a main method so the class can run stand-alone.  HelloWorld1.java does not. 

![](images/00004.jpg)Possible Misstep 7-5

> On the left (not the far, far left) of the Hello project's HelloWorld.java in the Java editor you'll see dark circles with a + in the circle and/or light circles with a - in the circle next to the beginning of Javadoc comments and blocks (usually methods).   The dark circles with +s indicate code folding, the light circles with - indicate no code folding.  Click on the light circle at the top of the file (the beginning of the class Javadoc).  The circle becomes dark and only one line of the comment or the block.  Do NOT think anything is lost.  Click on a dark circle and it becomes a light circle and the entire comment or block appears.

Exercise 7-4:  Close Hello and Hello1

In the Project Explorer, both Hello and Hello1 should be open.  (If not, open the one that is closed.)  Right click on Hello.  When the dropdown appears, click on "Close Project".  Repeat for Hello1.

Exercise 7-5:  Delete the Hello1 project

In the Project Explorer, right click on the Hello1 project.   When the dropdown menu appears, click on "Delete".  When the Delete Resources popup appears, look at the project location to be sure this is the project you want to delete.  If so, click on checkbox next to "Delete project" then click on "OK".    In both the workspace and the IDE, the project is gone!  Forever.  Can't be recovered (easily).

Exercise 7-6:  Add a method call inside Hello project's HelloWorld's main method

In Project Explorer, make the Hello project an open expanded project.  Load HelloWorld.java into the Java editor.  Notice the TODO comment inside main.  Now, look in the Outlines pane in the "Outlines and tasks" region.  You don't have to search the editor to find TODOs:  they're listed for you in the Outlines pane. 

Find and highlight the '"//TODO" in main( …)" then type "System." (You need the dot!)  Eclipse' help system popups up the System class document.  Find and highlight "out", press ENTER (or double click) and "out" is postpended to "System.".  Type another dot (.) immediately after "System.out".  Eclipse pops up the PrintStream class document.  Find and highlight "println", and press ENTER.  Now you see "`System.out.println();`".  Type "Hello from HelloWorld and Eclipse" inside the parentheses ("`System.out.println("Hello from HelloWorld and Eclipse");`").  Now there are no error indicators.  (If you see an icon with paper and a blue pen, click on it to see the message.)

Right click on the main pane of the HellowWorld.java editor.  When the dropdown menu appears, click on "save".  Close the HelloWorld.java editor tab.

Exercise 7-7:  Run Hello project

In Project Explorer, right click on the Hello project.  When the dropdown menu appears, click on "Run as -> Java application.  Note that a console opens in the "output" region and the string "Hello World from Java and Eclipse" appears in Console.  Click on the "Problems" tab and note that no errors are listed.

Exercise 7-8: Why a Hello project warning?

In Project Explorer, if the Hello project is open, you may see a project warning icon (folder with a yellow triangle with an exclamation mark) between the ">" and the project name.  Drill down to the "HelloWorld.java file then double click on it to open it in the Java editor.  If you don't see a "Problems" tab in the output region, click on "Window->Show View->Other…->General->Problems".  Now you see a "problems" tab in the output region.  Click on the word "Problems" and read the warning description.  If  the message is "…no JREs … strictly compatible", ignore the project warning.

Exercise 7-9: Close Hello project

In Project Explorer, right click on the Hello project.  When the dropdown menu appears, click on "Close Project".  The icon for the project is now a closed folder.

Questions

All these questions assume the project is an open expanded project.

What are two additional ways to create a new project?  Hint:  Click on File.  Look at the dropdown then mouse over the toolbar icons.

What are two ways to open HelloWorld.java in the Java editor?

What additional way is there to close the Java editor?

What additional ways are there to save the changed HelloWorld.java file?

What additional ways are there to run the Hello project?

What additional ways are there to close the Hello project?

When you see a menu dropdown entry with three dots, what does it mean?

Where did Eclipse get the text for the @author tag?

Chapter 8: Create a new project from the Hello project

Creating a new project from scratch requires a lot of points and clicks.  If you have a similar project, it is often easier to copy that project than to create a new one.  Eclipse has a refactoring tool that simplifies modifying a copy of an existing program.

What is a fully qualified name?

The name of an object with its path (relative to the workspace).

What is refactoring?

The ongoing redesign of software to improve its responsiveness to change.  Also describes a software tool in an IDE which simplifies redesign. 

What is the launcher pattern (design pattern)?

Design pattern that uses a class with a main to start an application.  Usually the other classes in the application do not have mains, preventing them from being misused.

What's a launcher?

Class with a main method and little else.  All it does is launch the application. 

Exercise 8-1:  Make a copy of the Hello project and name it HelloArgs

Possible Misstep 8-1

> Close the Hello project then right click on the project.  When the dropdown menu appears, click on "Copy".  Right click on a blank part of the Project Explorer.  When the dropdown menu appears, click on "Paste".  Oops.  Error about "can't copy the clipboard …".  What went wrong?  When a project is closed, all copy does is copy the fully qualified name of the project (in this case, "/Hello").  To copy the project (the object), it must be open.

If Hello is closed, right click on it in the Project Explorer main window.  When the dropdown appears, click on "Open Project" (or, double click on Hello).  Right click on the Hello project in the Project Explorer main window.  When the dropdown menu appears, click on "Copy".  Right click on a blank region below the project.  When the dropdown appears, click on "Paste".  When the "Copy Project" popup appears, enter the project name "HelloArgs" then click on "Finish".

Possible Misstep 8-2

> If you are working in a project that is similar to another open project, it is easy to accidently make changes to the wrong project.  Avoid this problem by right clicking on the project you want to work on.  When the dropdown appears, click on "Close Unrelated Projects".  When the "Close Unrelated Projects" popup appears, click on "OK".

Click on the ">" icon in front of HelloArgs to expand the project.  Drill down to HelloWorld.java, then right click on it.  When the dropdown appears, click on "Refactor->Rename".  When the "Rename Compilation Unit" popup appears, enter the new name "HelloWorldArgs", click on the check box next to "Update textual …" then click on the "Finish" button.   (If the "Rename Compilation Unit" wizard popups up and warns you that the class has a main method, ignore the warning and click on "Finish" again.)  The name of file and the class is changed and appropriate changes have been made inside the file.  Double click on HelloWorldArgs.java to show it in the Java editor.  Replace the text "Hello from …" with args[0], then save the file. 

How do you add command line arguments?  Right click on project.  When the dropdown appears, click on "Run As …->Run Configurations …".   When the "Create, manage, and run configurations" wizard pops up, double click on "Java Application".  When the right windows changes, enter the Main class name "HelloWorldArgs", click on the "Arguments" tab.  When the tab is highlighted, enter "Hello from HelloArgs and Eclipse" in the "Program arguments" window and click on the "Run" button.  The "Create …" wizard runs and the message "Hello from HelloArgs and Eclipse" appears in the "Console" tab in the output window. 

Exercise 8-2:  Make a copy of the Hello project into HelloLauncher

Close the project HelloArgs if it's still open.  Open and copy the Hello project, paste it into the Project Explorer main pane, and name it HelloLauncher.  Right click on HelloLauncher.  When the dropdown appears, click on "Close Unrelated Projects".  (This only appears if you have two or more projects in Project Explorer.)  Make HelloLauncher an expanded project and drill down the resource folder src until you find "default package".  Right click on "default package".  When the dropdown appears, click on "New->Class".  When the "New Java Class" wizard appears, enter the name "HelloLauncher".  Don't forget to click next to the labels "…main…" and "Generate …".  Click on "Finish".  When HelloLauncher.java" appears in a Java editor, replace the TODO comment with the statement

> `HelloWorld h = new HelloWorld ("Hello from HelloLauncher and Eclipse");`

An error icon (to be exact, a quick fixable error message) appears to the far left of the statement.  When you click on the error icon, Quick Fix advice pops up.  BTW:  The thin red line in the scrollbar to the right of the statement is also an error message.  In large files, clicking on the thin red line will take you directly to the error statement.  Also, you can estimate the number of errors in the file by counting the number of thin red lines.  However, clicking the thin red line does not popup Quick Fix. 

In this case, the Quick Fix is only partially helpful.  The problem is that HelloWorld doesn't have a constructor that takes a string as an argument so you will have to modify HelloWorld.java.  Save HelloLauncher.java. 

Open the HelloWorld.java editor window. 

Add the data member

`private String message;`

inside the class and above the Javadoc comment for "main".  BTW:  Notice what just happened in the Outline tab in the detail and task region.   If the statement is not formatted correctly, right click on the line.  When the dropdown appears, click on "Source->Format element".  Note the change. 

Right click on the line below the data member.  When the dropdown appears, click on "Source->Generate Getters and Setters".  When the "Generate getters and setters" wizard appears, click on the checkboxes for "message" and "Generate method comments", then click on the "OK" button.  Note the changes in the source and in the Outline tab. 

Right click on the line above the Javadoc comment for "main".  When the dropdown appears, click on "Source->Generate constructor using fields".  Note the constructor created.

Last, highlight the body of main and delete it. 

Save HelloWorld.java then reopen the HelloLauncher.java editor.  If you still the red error, you may need to refresh the editor by saving the file again.  Now, you should not see an error.  But you do have a quick fixable warning icon (the yellow triangle with an "!" inside) on the far left of the edit window.  Mouse over it to see the message.  Oh, yeah, h is created but never used.  Insert this statement just below the statement creating h: 

`System.out.println ( h.getMessage() );`

The warning icon goes away because h is now used in the println method!  (If you still see the warning, save the file and the warning will go away.)  Select the entire main method, right click on it.  When the dropdown appears, format the method. 

Right click on the project.  When the dropdown appears, click on "Run as->Java Application".  The "Select Java Application" popup appears because you have two classes in the project with main methods.  BTW:  If you haven't saved your changes to HelloWorld.java, the "Save and Launch" popup appears.  Click on the "OK" button.  Highlight the HelloLauncher class and click on "OK".  You should see the hello message in the Console. If you don't see any error or warning indicators, you've been successful. 

Possible misstep 8-4

> You have two classes with main methods.  If you right click on the project and use "Run as->Java Application", which class will be run?  In this case, it's easy to tell:  HelloWorld has no body for main so nothing will appear in the Console tab if it runs; HelloWorld has a body for main so "Hello …" should appear in the Console tab if it runs.  Try it anyway.  Eclipse will protect you:  "Select Java Application" pops up with the two classes that have mains.  You have to select one before running the app.

> To avoid this problem, remove the Javadoc shell for main and the method main from HelloWorld then run "Run As->Java App" again.  The "Save and Run" wizard pops up, saves the now mainless HelloWorld.java then starts HelloLauncher.java.  Exactly what we hoped for.

Questions

All these questions assume the project is an open expanded project.

What other ways are there to open a closed project?

Why doesn't "File->Close" close an open project?

Chapter 9:  Debugging HelloLauncher

What is debugging

Process of identifying errors in a program, locating the cause of errors and fixing the errors.

What is a breakpoint (break point)?

Location and/or conditions at a location in source where the debugger temporarily halts program execution so the developer can examine variable values before continuing program execution.

What does "Toggle breakpoint" mean?

Turn on a breakpoint at the location of the mouse cursor if there is no breakpoint.  Disable the breakpoint if one is there and turned on.

Exercise 9 -1:  Debug HelloLauncher project

In the Project Explorer, expand "HelloLauncher" and open HelloLauncher.java in the editor.  Right click on the bar at the far left of the editor across from the "System…." statement of the main method.  When the dropdown appears, click on "Toggle breakpoint" and a dark circle with a very small arrow across the top (indicating an active breakpoint) appears on the bar.  Right click in the same place.  When the dropdown appears, click on "Toggle breakpoint" and the breakpoint disappears.  Set the breakpoint, right click on it.  When the dropdown appears, select "Disable breakpoint" and a light circle appears on the bar.  For the third time, click on "Enable breakpoint" and the ball with again be a dark again. 

In the Project Explorer, right clicking on HelloLauncher project.  When the dropdown appears, select "Debug as ->Java Application".  When "Confirm Perspective Switch" popup appears, click on "Yes".  (Do not click on the checkbox next to "Remember my decision".)  A third perspective "Debug" is added to the perspective grouping and it becomes the current perspective.  Then, the Project Explorer "main" region is swapped for the Debug "main" region. 

An image is shown below.  Study the new information you have available.  Mouse over all seven debugging buttons.  Mouse over the icons at the far right of the "Console" tab.

![](images/00008.jpg)

Click the "Terminate debugging" button.  You are still in the "Debug" perspective.  To remove clutter, right click on the "Debug" perspective.  When the dropdown appears, click on "Close", then click on "Java EE" perspective icon.  In the Project Explorer", close the project and take a break.

Questions

All these questions assume the project is an open expanded project.

Chapter 10:  Reduce coupling with separation of responsibility (more but smaller classes)

Warning:  The game has changed:  If you've been shown how to do something, you'll have to find out where and how.  I'll only show you how to do new things.

What is @Override      

Informs the compiler that you intend to override a method in the superclass.  If the compiler does not detect the method in one of the superclasses, it will generate an error.  Note:  Quickly identify typos or API changes.

What is coupling?

The relative complexity of the interfaces between code elements (the relative independence of code elements).  The phrase "loose coupling" describe simple or minimum coupling (little complexity) (good design) while "tight coupling" describes complex or maximum coupling (much complexity) (bad design).  It describes the relative independence of modules (a good thing).

What is a provider?

Class or method that provides something other classes need, usually information.  Alternative:  A factory of swappable factories (implements the abstract factory pattern.  Reduces coupling.

What is a renderer?

Class or method that encodes and decodes information in a format that other classes or methods can understand.  Reduces coupling.

What is SoR (Separation of Responsibilities)?

A class should be (1) responsibility over a single part of the software functionality and (2) that responsibility should be entirely encapsulated by the class. All its services should be narrowly aligned with that responsibility.  Alternative:  Each class should do a very few things and do them completely.

What is an annotation?

Form of metadata that provides information about a program that is not part of the program itself (has no direct effect on the operation of the code it annotates.  (1) information for the compiler (it can use them to detect errors or suppress warnings), (2) compile-time and deployment-time processing (software tools can process annotation information to generate code, XML files, and so forth), and (3) runtime processing (it can be examined at runtime).  Note:  Java and Android annotations begin with an "at" character (@). 

Exercise 10-1:  Improve Hello separation (Reducing Hello coupling) (Decoupling Hello)

Copy HelloLauncher to HelloSeparation.  (Did you make HelloSeparation an open expanded project?  Did you close HelloLauncher?)  Add empty classes HelloMessageProvider and HelloMessageRenderer to the project.  (Did you put them in the default package?  Did you add Javadoc comments?)  (Are both classes open in the Java editor?  If not, open them.)  Add to HelloMessageProvider a blank line and the following method:

> `public String getMessage() {`

> `  return "Hello from HelloSeparation and Eclipse!";`

> `}`

In Project Explorer, highlight HelloMessageProvider.java then right click on it.  When the dropdown appears, click on "Source->Format".  When Eclipse finishes formatting it, save and close it.

Add to HelloMessageRenderer the following statements:

> `private HelloMessageProvider messageProvider = null;`

> `public void render () {`

> `  if (messageProvider == null) {`

> `    throw new RuntimeException ("Set the property messageProvider of class:"`

> `                               + HelloMessageRenderer.class.getName());`

> `  }`

> `  System.out.println(messageProvider.getMessage());`

> `}`

Generate setters and getters for HelloMessageRenderer. 

In Project Explorer, highlight HelloMessageRenderer then right click on it.  When the dropdown appears, click on "Source->Format".  When Eclipse finishes formatting HelloMessageRenderer.java, save and close it.

Replace the body of HelloLauncher.java's main() with

> `HelloMessageRenderer hmr =new HelloMessageRenderer ();`

> `HelloMessageProvider hmp =new HelloMessageProvider ();`

> `hmr. setMessageProvider(hmp);`

> `hmr.render();`

In Project Explorer, highlight HelloLauncher then right click on it.  When the dropdown appears, click on "Source->Format".  When Eclipse finishes formatting HelloLauncher.java, save and close it.

Run HelloSeparation.  It runs.  However, HelloMessageRender and HelloMessageProvider are hard coded in the project (in HelloLauncher).  Changing the text of the message would be difficult.

> Possible misstep 10-1

> Does HelloWorld.java get used in the project HelloSeparation?  No, it's been replaced by HelloLauncher, HelloMessageProvider and HelloMessageRender.

Delete HelloWorld.java from project.  Run HelloSeparation.  It runs.  Somewhat cleaner. 

Exercise 10-2:  Improving Hello separation with interfaces

Copy HelloSeparation to HelloSeparationWithInterfaces.  (Did you close HelloSeparation?  Did you make HelloSeparationWithInterfaces an open expanded project?)  We are going to (eventually) be able to change the message by making HelloMessageProvider and HelloMessageRender implement interfaces.  But, that's in the future.

In the HelloSeparationWithInterfaces project, right click on HelloMessageProvider.java.  When the dropdown appears, click on "Refactor-> Extract Interface".  When the "Extract Interface" popup appears, enter the name "MessageProvider", click on the checkbox next to getMessage ( ) then click on "OK".  BTW:  Note the icon for an interface is a piece of paper with a large J and a small I inside a ball at the right top of the paper.  Open "MessageProvider.java" and "HelloMessageProvider.java" in side-by-side Java editors.  Nothing to do here except change the message to "Hello from HelloSeparationWithInterfaces and Eclipse" in HelloMessageProvider.java and save the file.

Repeat by extracting the interface from HelloMessageRenderer.java.  Open "MessageRenderer.java" and "HelloMessageRenderer.java" in side-by-side Java editors.   Ignore the annotations (the lines beginning with @)). 

Run HelloSeparationWithInterfaces.  It runs and displays an appropriate message.

Questions

All these questions assume the project is an open expanded project.

How can I add Javadoc comments to new methods I add?

Enter /** [ENTER] then enter */[ENTER]

Why doesn't "Source->Generate Element Comment" add a comment to a method?

It should work but doesn't. 

Chapter 11:  Add a factory to improve Hello separation

What can be assigned to a class reference?

Null or an object of the class or an object of some child class of that class.  No object of a parent class can be assigned to the reference.  Warning:  The only thing the reference can do is call methods in the original interface.

What can be assigned to an interface reference?

Null or an object of some (already defined) class that implements the interface or an object of some child class of that class or an object of some class that implements a child of the interface.  No object of a class that implements a parent interface can be assigned to the reference.  Warning:  The only thing the reference can do is call methods in the original interface.

What's a child class?

Another name for subclass.

What's a factory (factory class)?

Class or object that creates other classes or objects, either by composition or extension.

What's a parent class?

Another name for superclass.

What's a reference?

Data element that has a type and whose value is an address (on the heap) of an object of that type or of a child type.  Former C programmers might think of a reference as a pointer with self-control. 

What's a class reference?

Reference to an object that only knows about the characteristics and behaviors of the object's (already existing) class or of some parent class.

What's a child reference (child class reference)?

Reference to an object of some (already defined) child class.

What' a parent reference (parent class reference)?

Reference to a parent class (superclass).  A parent class reference can be assigned to child class object but it can only the parts of the object inherited from its parent class.

What's an interface reference?

Reference to an object that only knows about the behaviors of some interface implemented by the object's class.

Why do I care about class references and interface references?

They can reduce coupling and simplify coding.

Exercise 11-1:  Improving Hello separation by adding a factory

Copy HelloSeparationWithInterfaces to HelloSeparationWithInterfacesAndFactory.

In the HelloSeparationWithInterfacesAndFactory project, right click on "(default package").  When the dropdown appears, click on "New->Class".  Use the name MessageSupportFactory.  (Did you click on the checkbox next to "Generate comments"?)  Insert the code below into the body of MessageSupportFactory.

> `private static MessageSupportFactory instance = null;`

> `private Properties props = null;`

> `private MessageRenderer renderer = null;`

> `private MessageProvider provider = null;`

> `private MessageSupportFactory() {`

> `props = new Properties();`

> `try {`

> `props.load(new FileInputStream("msf.properties"));`

> `// get the implementation classes`

> `String rendererClass = props.getProperty("renderer.class");`

> `String providerClass = props.getProperty("provider.class");`

> `renderer = (MessageRenderer) Class.forName(rendererClass).newInstance();`

> `provider = (MessageProvider) Class.forName(providerClass).newInstance();`

> `} catch (Exception ex) {`

> `ex.printStackTrace();`

> `}`

> `}`

> `static {`

> `  instance = new MessageSupportFactory ();`

> `}`

Lots of errors.  Click on the ball with the red x to the right of the first use of Properties.  When help pops up, double click on "import 'Properties' (java.util)".  Most of the errors go away when "import java.util.Properties" is inserted just below the comment at the top of the editor window.  Repeat at the ball with the red x to the right of the first use of FileInputStream.  Double click on import 'FileInputStream' (java.io).  No more errors!  Right click on the text "MessageSupportFactory" to the right of public class and reformat the class. 

Note the class assumes we will create an msf.properties file to be read.

Right click on "MessageSupportFactory".  When the dropdown appears, click on "Source->Generate Getters and Setters".  Select instance, provider, renderer then click on "OK".  We're not going to use the setters so remove them.

Save and close MessageSupportFactory.java.  Double click on HelloLauncher.java.  Replace the body of main with the following code.

> `MessageRenderer mr = MessageSupportFactory.getInstance().getRenderer();`

> `MessageProvider mp = MessageSupportFactory.getInstance().getProvider();`

> `mr.setMessageProvider(mp);`

> `mr.render();`

Save the changed file and close it.

What does this code do?  MessageSupportFactory can make objects using HelloMessageProvider and HelloMessasgeRenderer if that's what it finds in msf.properties and the code works as before.  But, it can also make any other classes that implement MessageProvider and MessageRenderer if that's what is finds in in msf.properties and the code may work different. 

Double click on HelloMessageProvider.java.  Change the return message to "Hello from HelloSeparationWithInterfacesAndFactory and Eclipse.".  Save it and close it.

Now create msf.properties file.  Right click on the HelloSeparationWithInterfacesAndFactory.  When the dropdown appears, click on "New->File".  Enter the file name "msf.properties" then click on "Finish".  Enter the text below into the file.  Save and close the file.  BTW:  Where is the file in the project structure?

> `# msf.properties`

> `renderer.class=HelloMessageRenderer`

> `provider.class=HelloMessageProvider`

Last, edit the message in HelloMessageProvider.java so it says "Hello From HelloSeparationWithInterfacesAndFactory". 

Run HelloSeparationWithInterfacesAndFactory.  It runs and displays an appropriate message.

Exercise 11-2:  Improving Hello separation by adding a factory Part 2

Copy HelloSeparationWithInterfacesAndFactory to HelloSeparationWithInterfacesAndFactory2

In the HelloSeparationWithInterfacesAndFactory2 project, right click on HelloMessageProvider.java, when the dropdown appears, click on "Copy".  Right click on "default package" and when the dropdown appears, select "Paste".  Use the name "GoodbyeMessageProvider.java for the new class.  Double click on it to bring it up in the editor window.  Change the string to "Goodbye from HelloSeparationWithInterfacesFactory2 and Eclipse."  Save and close it.  Double click on "msf.properties" to bring it up in the editor window.  Change the line that begins with provider so it says

`provider.class=GoodbyeMessageProvider`

Save and close it.

Run HelloSeparationWithInterfacesAndFactory2.  It runs and gives a different message.  So it is possible to change the behavior of an application with simple changes in a text file.  No compiling is required!

Questions

All these questions assume the project is an open expanded project.

Chapter 12:  Reduce coupling even more with a smarter factory

What is Spring?

The owner of the Spring family of frameworks, including lightweight open source application server that simplifies developing Java enterprise applications.  Formerly known as SpringSource [(http://www.springsource.org](file:///C:%5CUsers%5CJohnR_000%5CDocuments%5CMy%20Documents%5CMy%20Programming%20Notes%5CEclipse%5Cword%20eclipse%204%5C(http:%5Cwww.springsource.org)).

What's a user library?

Collection of useful external jars that have some common purpose. 

What's an appender?

In Log4j, an output destination for log file data.

What's an external jar?

Jar file that is not built by a project in the workspace, typically an API Jar file provided by some external site.

Exercise 12-1:  Improving Hello separation by using a factory from Spring Framework

To access Spring Framework, you'll need to download Spring Framework 3.2.16 (zip) ALL Binary from [http://olex.openlogic.com/packages/spring/3.2.16](http://olex.openlogic.com/packages/spring/3.2.16).  Use "Extract all" or some zip program to unzip the Spring jars to c:\MyCode (or some such place-it doesn't matter where as long as you don't forget where). 

Copy HelloSeparationWithInterfacesAndFactory to HelloSeparationWithInterfacesAndSpring. 

Right click on the HelloSeparationWithInterfacesAndSpring project.  When the dropdown appears, click on "Build Path -> Configure Build Path".  When the "Java Build Path" wizard pops up, click on the "Add Library…" button.  When the "Add Library" wizard pops up, double click on "User Library".  When the "User Library" wizard pops up, click on the "User Libraries…" button.  When the "User Libraries" wizard pops up, click on the "New…" button.  When the "New User Library" wizard pops up, enter the name "Spring 3.2.16" then click on "OK".  Back in the "User Libraries" wizard, the "Spring 3.2.16" user library should be highlighted.  Click on the "Add External JARs…" button.  When the Jar Selection wizard pops up, go to the location where you unzipped the Spring Framework jars.  Double click on "libs" folder.  In the folder, highlight "spring-beans.3.2.16.RELEASE", "spring-beans.3.2.16.RELEASE-javadocs", "spring-core-3.2.16.RELEASE" and "spring-core-3.2.16.RELEASE-javadocs" jars and click on "Open".  Back in "User Libraries", look at the results then click on "OK".  Back in "User Library", click on "Finish".  Back in "Java Build Path", click on "Apply" then on "OK".  Note the change in the HelloSeparationWithInterfacesAndSpring project.  BTW:  If you get any Oomph popups, just click on "OK".  You shouldn't but ….

Open HelloLauncher.java in the editor window. Replace the code inside main with the code below:

`BeanFactory factory = getBeanFactory();`

`MessageRenderer mr = (MessageRenderer) factory.getBean("renderer");`

`MessageProvider mp = (MessageProvider) factory.getBean("provider");`

`mr.setMessageProvider(mp);`

`mr.render();`

Click on the small folder with red x icon to the far right of "BeanFactory with a red squiggle underneath".  When the on-help pops up, double click on the highlighted "import 'BeanFactory' …" line. Note the import statement added to the top of  HelloLauncher.java.  Yes, there's still a problem with getBeanFactory() - it doesn't exist yet.  Paste the method below into HelloLauncher.java  below main().

> `private static BeanFactory getBeanFactory() throws Exception {`

> `  // get the bean factory`

> `  DefaultListableBeanFactory factory = new DefaultListableBeanFactory();`

> `  // create a definition reader`

> `  PropertiesBeanDefinitionReader rdr`

> `= new PropertiesBeanDefinitionReader(factory);`

> `  // load the configuration options`

> `  Properties props = new Properties();`

> `  props.load(new FileInputStream("beans.properties"));`

> `  rdr.registerBeanDefinitions(props);`

> `  return factory;`

> `}`

Add the missing import statements that remove the errors the editor shows you. 

You still have problems with getBeanFactory().  Again, click on the small folder with the red x icon.  Oh, it's just an unhandled exception.  Notice the help offers to options.  Add "throws Exception" error message to main()  or  surround with try/catch.  Since main starts the application, you don't have a choice:  you have to use the try/catch so double click on that choice.  Unfortunately, you now have the problem that factory may not be initialized.  A sleazy but quick solution is to initialize factory to null:

`BeanFactory factory = null ;`

You have no compile errors so you can run the app.  However, you do indeed get a file io error because there is no file beans.properties.  That's easy to fix.  Right click on the project.  When the dropdown appears, select "New->File".  When the File wizard appears, enter the file name "beans.properties" then click on "Finish".

You have no errors so you can run the app.  Now you have a puzzling error:  the LogFactory not found.  This is puzzling unless you waste a lot of time read Spring docs.  Spring uses the Apache Log4j and

You'll need to download log4j-1.2.17.zip from [http://logging.apache.org/log4j/1.2/download.html](http://logging.apache.org/log4j/1.2/download.html) and commons-logging-1.2-bin.zip from [http://commons.apache.org/proper/commons-logging/download_logging.cgi](http://commons.apache.org/proper/commons-logging/download_logging.cgi).  Use "Extract all" or some zip program to unzip the Apache jars to c:\MyCode (or some such place-it doesn't matter where as long as you don't forget where).  Go back to "Build Path->Configure Build Path", create a User Library Named Apache, add log4j and commons-logging to the library.

You have no errors so you can run the app.  But you have a puzzling error:  no bean named renderer.  Then you remember there is nothing in "beans.properties" yet.  Place the following code in "beans.properties":

> `#Message renderer`

> `renderer.(class)=HelloMessageRenderer`

> `# Ask Spring to assign provider bean to the MessageProvider property`

> `# of the Message renderer bean`

> `renderer.messageProvider(ref)=provider`

> `#Message provider`

> `provider.(class)=HelloMessageProvider`

Again, no errors so you can run the app.  This time, you have puzzling warnings like "log4j:WARN No appenders could be found for logger (org.springframework.core.env.StandardEnvironment)".  An experienced Log4j user will recognize you need to add a Log4j.properties file and supply you with an example like this:

> `log4j.rootLogger = ERROR, myConsole`

> `log4j.logger.com.springclass = DEBUG, myFile, myConsole`

> `log4j.additivity.com.springclass = false`

> `log4j.appender.myConsole = org.apache.log4j.ConsoleAppender`

> `log4j.appender.myFile = org.apache.log4j.FileAppender`

> `log4j.appender.myFile.file = myFile.log`

> `log4j.appender.myConsole.layout = org.apache.log4j.SimpleLayout`

> `log4j.appender.myFile.layout = org.apache.log4j.PatternLayout`

> `#log4j.appender.myFile.layout.ConversionPattern=%r %p %c %x - %m%n`

> `log4j.appender.myFile.layout.ConversionPattern=%-5p : %m %d{dd-MM-yy HH:mm:ss}%n`

Right click on "(default package)".  When the dropdown appears, click on "New->Other."  When the "Select a wizard" popup appears, click on "General->File" then click on the "Next" button.  When the "File" popup appears, enter "Log4j.properties" then click on "Finish".  When Log4j.properties appears in the text editor view, paste the above lines into the file.  If you don’t see any errors, save and close.  BTW:  This file may or may not save the information you want in Log4j's myFile.  But, you can test and see what gets logged!

Again, no errors so you can run the app.  You notice the wrong message in the "Console", "…Factory…".  Open "HelloMessageProvider" in the Java edit and replace "…Factory…" with "…Spring…".

Again, no errors so you can run the app.  Everything appears to work.

Exercise 12-2:  Improving Hello separation clean up

Copy HelloSeparationWithInterfacesAndSpring to HelloSeparationWithInterfacesAndSpring2.

Remove msf.properties and MessageSupportFactory.java. 

No errors so run the app.  Everything appears to work but you get the message " Hello from HelloSeparationWithInterfacesAndSpring and Eclipse!" instead of  "…Spring2…".  Edit the message string in HelloMessageProvider.java. 

No errors so run the app.  Everything appears to work.

Questions

All these questions assume the project is an open expanded project.

Chapter 13:  Reduce coupling even more with DI (dependency injection)

A programmer might argue that he still has to create and add a new class for every different message before he compiles his code.  True for the simple factory class used in HelloSeparationWithInterfacesAndFactory2.  But, with a smarter factory (like one supplied by Spring Framework) XML, messages can be without recompiling by editing a text file. 

What is deprecated?

Obsolete, not recommended (but, possibly, still supported).  BTW:  If you use deprecated classes or methods, people will curse you on the day when the deprecated class or method is no longer supported.

What is DI (Dependency injection)?

Design pattern that implements inversion of control for software libraries.  A caller delegates to an external framework the control flow of discovering and importing a service or software module specified or "injected" by the caller.  There are three common forms of dependency injection: setter-, interface- and constructor-based injection, where the responsibility of injecting the dependency lies upon the client, the service or the constructor method respectively.  Spring uses DI extensively. 

Exercise 13-1:  Improving Hello separation by using Spring and DI

Copy HelloSeparationWithInterfacesAndSpring2 to HelloSeparationWithInterfacesSpringAndDI.  Edit the message string in HelloMessageProvider.java.  No errors so run the app.  If everything appears to work, continue.  Otherwise, fix problems.

Create an empty "beans.xml" at the same level as "src" and the libraries.  Insert the lines

> `<?xml version="1.0" encoding="UTF-8"?>`

> `<!DOCTYPE beans PUBLIC "-//SPRING//DTD BEAN//EN" "http://www.springframework.org/dtd/spring-beans.dtd">`

> `<beans>`

> `<bean id="renderer" class="HelloMessageRenderer">`

> `<property name="messageProvider">`

> `<ref local="provider"/>`

> `</property>`

> `</bean>`

> `<bean id="provider" class="HelloMessageProvider"/>`

> `</beans>`

Possible misstep 13-1

When you pasted the xml into beans.xml, the formatting went away.  Did you fix it by manually editing the xml?  If you did, you wasted some time.  You were in the xml editor so it knows how to format xml.  Highlight the lines then right clicking on the highlight.  When the mouse pops up, click on "Source->Format".  The xml formatting reappears.

(Why did this work?  Dot xml files are edited by an Xml editor, not the Java editor.  Of course it knows how to format Xml.)  Save and close "beans.xml".

Open "HelloLauncher.java" in the Java editor.  Replace the code in main () with the following statements:

`BeanFactory factory = getBeanFactory() ;`

`MessageRenderer mr = (MessageRenderer) factory.getBean("renderer");`

`mr.render();`

Replace getBeanFactory with the following method:

> `private static BeanFactory getBeanFactory() throws Exception {`

> > > `// get the bean factory`

> > > `BeanFactory factory`

> > > `= new XmlBeanFactory(new FileSystemResource("beans.xml")`

> > > `);`

> > > `return factory;`

> `}`

The reference to the class XmlBeanFactory generates an error.  Eclipse doesn't hint as to what jar file we need to import for XmlBeanFactory.  However, google suggests using org.springframework.beans.factory.xml.  Insert

> `import org.springframework.beans.factory.xml.XmlBeanFactory;`

at the bottom of the list of imports and the error goes away.  But, why is XmlBeanFactory dashed through?  Eclipse is warning you that XmlBeanFactory is deprecated.  But, still supported.  Also, the error at FileSystemResource can be resolved by right click on FileSystemResource.  Select the entry "import 'org.springframework.core.io.FileSystemResource'.  The error goes away. 

You do see any errors but you do see warnings ("factory can only be null" or some such).  Run it.  Everything seems to work. 

Exercise 13-2:  Improving Hello separation by using Spring, DI and more Xml

Copy HelloSeparationWithInterfacesSpringDIAndXml to HelloSeparationWithInterfacesSpringDIandMoreXml. 

Replace the contents of HelloMessageProvider with

> `private String message = "Hello from HelloSeparationWithInterfacesSpringDIAndMoreXml and Eclipse!";`

> `/* (non-Javadoc)`

> `* @see MessageProvider#getMessage()`

> `*/`

> `@Override`

> `public String getMessage() {`

> `return message ;`

> `}`

> `public HelloMessageProvider ( String message ){`

> `this.message = message;`

> `}`

Add Javadoc comments for the data member message and the constructor.

Open beans.xml.  Replace the bean provider with the following:

> `    <bean id="provider" class="HelloMessageProvider">`

> `        <constructor-arg>`

> `            <value>This is a configurable message</value>`

> `        </constructor-arg>`

> `    </bean>`

Save and close.  If there are no errors, continue.  Otherwise, fix the errors. 

Run the app.  Note the message in the console.  The text file beans.xml controls the message!

Questions

All these questions assume the project is an open expanded project.

What could you do instead of clicking on the small folder with red x to get help?

Chapter 14:  Export an existing project, import an existing project

What does export mean in Eclipse?

Converting an existing file or file system in an Eclipse format to a non-Eclipse format (or, some other Eclipse format).  Warning:  You must distinguish between Java exports and Eclipse exports.

What does export mean in Java?

Converting an existing uncompressed file or file system to a Java compressed format (typically an EAR, a JAR, or a RAR).  You must distinguish between Java exports and Eclipse exports.

What does import mean in Eclipse?

Converting an existing Eclipse file or file system or non-Eclipse file system into some format (usually a project).  You must distinguish between Java imports and Eclipse imports.

What does import mean in Java?

Converting an existing file in some compressed Java file format into an (1) uncompressed format or (2) some other compressed Java file format.  You must distinguish between Java imports and Eclipse imports.

What is EAR file format?

Compressed compiled encapsulated platform-independent file format that contains all the class files and other resources an enterprise application needs to run.  Often used as a synonym for enterprise application or J2EE enterprise application.  Ear files are deployed on an application server.

What is JAR file format?

Compressed compiled encapsulated platform-independent file format that aggregates many files into one.  Multiple Java classes and their requisite components (.class files, images, sounds and other resource files) can be bundled in a JAR file and subsequently downloaded to a client in a single HTTP transaction.  The format also supports file compression and digital signatures.

What is WAR file format?

Compressed compiled encapsulated platform-independent web application that contains a directory structure.  The war file is deployed to a web server.  A type of jar file.

What's a Jar (Java ARchive)?

Cross-platform file format that groups, and possibly compresses, multiple class files and other files such as graphics and sound files into one file.  A single HTTP transaction downloads the entire JAR file.  An EJB Jar is a special form of a JAR that contains an EJB.

What's a JAR file (.jar file)?

File that aggregating many files into one using a compressed format (JAR file format) based on PKZIP format.  Java reads JAR files without decompressing them.  Can have (usually have) relative directory structure.  Can be viewed (but not created by) ZIP viewers.  Can be created by more powerful ZIP tools like WinZip or 7UP.

What's an executable jar file?

Jar file that contains a manifest file that lists a main class.  Entering the name of the file at the command line starts the main method of the main class.

What's an EAR (Ear file) (EAR file) (Enterprise ARchive file)?

Contains all the class files and other resources an enterprise application needs to run.  Often used as a synonym for enterprise application or J2EE enterprise application.  Ear files are deployed on an application server.

What's extract required libraries?

Copy required classes into an executable jar. 

What's package required libraries

Copy entire library jars into an executable jar. 

Questions

All these questions assume the project is an open expanded project.

Appendices

Appendix I:  Answers to questions

Chapter 7

What are two additional ways to create a new project?  Hint:  Click on File.  Look at the dropdown then mouse over the toolbar icons.

Click on "File->New".  Click on the "New" icon (blue and white rectangle with a yellow plus sign) on the far left of the tool bar then click on "New".

What are two additional ways to open HelloWorld.java in the Java editor?

Double click on HelloWorld.java in the Project Explorer tab.  Right click on HelloWorld.java.  When the dropdown appears, click on "Open".  BTW:  What happens when you click on "Open With"?

What additional way is there to close the Java editor?

Click on the "X" to the editor tab.

What additional ways are there to save the changed HelloWorld.java file?

Click on the "X" on the editor tab and answer the popups..

What additional ways are there to run the Hello project?

Click on "Run" (or, "Run As") under the Run menu.  Click on the "Run" icon (green ball with a white right pointing triangle).  BTW:  What happens when you click on the dropdown to the left of the launcher icon (green ball with a white right pointing triangle with a toolbox under it)?

What additional ways are there to close the Hello project?

Highlight the project, click on the Project menu, then select "Close Project". 

When you see a menu dropdown entry with three dots, what does it mean?

Another menu is going to appear if you click on the entry.

Where did Eclipse get the text for the @author tag?

Open File Manager and look at the names under "Users". 

Chapter 8

What other ways are there to open a closed project?

Select the project in "Project Explorer"  Click on "Project->Open Project". 

Why doesn't "File-> Close" close an open project?

Closes edit windows.

Chapter 10

How can I add Javadoc comments to new methods I add?

Type /**[ENTER] the */[ENTER}

Why doesn't "Source->Generate Element Comment" add a comment to a method?

I'm not sure.  It seems broken. 

Chapter 12

What could you do instead of clicking on the small folder with red x to get help?

Click on the Help menu.

Author's Biography

John R Hines has degrees from two party schools (the University of Colorado and Arizona State University).  He has been a semiconductor engineer, a programmer, a writer and a teacher.  He is now retired in Lucas, Texas. 

In the 1980s, the US Patent and Trademark Office granted him six patents and he began writing about using computers to solve problems.  He wrote a book about circuit simulation and taught SPICE (Simulation Program with Integrated Circuit Emphasis) classes at Fortune 500 companies. 

In the 1990s, he had computer-related columns in popular trade magazines like Electronic Test and Design Automation and scholarly magazines like IEEE Spectrum and taught C, C++, Delphi and Java. 

In the 2000s, he was a Java developer for America’s best telephone company. 

In 2014, he retired.  He writes eBooks and is looking for a part-time Android programming job.  Google him under JR Hines, John Hines and John R Hines. 

Eclipse 4.5 Hello Course is his thirteenth self-published book. 

He has previously published two large and one small eDictionaries (Mostly Java – a Dictionary of Distributed Computing, Dictionary of 17th – 19th Century Terms for Readers of Romance Novels and Naval Fiction, and CCNA R&S Dictionary), two small eBooks about eBooking (Creating EPUB Documents with Tables and Communicating with Text on Screen), a short note about the calendar (Gregorian Calendar Tiny Notes), a Calibre Course.  (He thinks he is smarter now so the previous books will be rewritten and reissued.) 

He has learned to write iPhone and iPad code and written two small eBooks about iOS 8 programming "Notes on the OS X Yosemite File System: A Windows Programmer's Guide to the OS X File System (A Windows programmer programming a Mac is like a tone-deaf American speaking Chinese Book 1)" and "Xcode 6 iOS Picture Book (A Windows programmer programming a Mac is like a tone-deaf American speaking Chinese 2)."  He does not like Apple programming very much.

His next book will be a text for a short course in Maven and Eclipse, "Maven and Eclipse 4.6 for Java Developers."

Table of Contents

[Getting Started](#index_split_002.html_filepos27821)

> [Chapter 0: Getting Started](#index_split_003.html_filepos27964)

> > > [Prerequisites](#index_split_003.html_filepos28060)

> > > [Terminology](#index_split_003.html_filepos28540)

> > > [Typefaces](#index_split_003.html_filepos30053)

> > > [What Eclipse version is used in this book?](#index_split_003.html_filepos32223)

> > > [What Windows version is used in this book?](#index_split_003.html_filepos32452)

> > > [Where did the exercises in these notes come from?](#index_split_003.html_filepos32835)

> > > [Where did these notes come from?](#index_split_003.html_filepos33547)

> > > [Why isn't this eBook copy protected?](#index_split_003.html_filepos34067)

> [Chapter 1: Why Eclipse 4.5?](#index_split_004.html_filepos34567)

> > > [What books should I read?](#index_split_004.html_filepos34662)

> > > [Why use the Eclipse IDE?](#index_split_004.html_filepos36349)

> > > [Why use Eclipse 4.5?](#index_split_004.html_filepos36875)

> [Chapter 2: Getting Started with Eclipse](#index_split_005.html_filepos37457)

> > > [How is the Eclipse project managed?](#index_split_005.html_filepos37565)

> > > [What are the 4.x versions of Eclipse?](#index_split_005.html_filepos37895)

> > > [What is a wizard?](#index_split_005.html_filepos39661)

> > > [What is Eclipse?](#index_split_005.html_filepos39899)

> > > [What is the Eclipse "Big Picture"?](#index_split_005.html_filepos40308)

> > > [What is Eclipsepedia?](#index_split_005.html_filepos40784)

> > > [What is open source?](#index_split_005.html_filepos41114)

> > > [What is the difference between Eclipse 3 and Eclipse 4?](#index_split_005.html_filepos41519)

> > > [What is the Eclipse architecture?](#index_split_005.html_filepos41960)

> > > [What is the Eclipse platform?](#index_split_005.html_filepos42192)

> > > [What is the Eclipse workbench?](#index_split_005.html_filepos42468)

> > > [What is Wiki?](#index_split_005.html_filepos42836)

> > > [When did Eclipse integrate Java 7?](#index_split_005.html_filepos43143)

> > > [When did Eclipse integrate Java 8?](#index_split_005.html_filepos43320)

> [Chapter 3: Installing Eclipse 4 Java](#index_split_006.html_filepos43641)

> > > [Do I have a JAVA_HOME environment variable?](#index_split_006.html_filepos43783)

> > > [What version of Java do I have?](#index_split_006.html_filepos44512)

> > > [What’s a command line interface?](#index_split_006.html_filepos45106)

> > > [What's a release (version)?](#index_split_006.html_filepos45521)

> > > [What’s a visual IDE?](#index_split_006.html_filepos45783)

> > > [What’s a WIMP interface?](#index_split_006.html_filepos46012)

> > > [What’s a workspace?](#index_split_006.html_filepos46493)

> > > [What’s an IDE?](#index_split_006.html_filepos47258)

> > > [What should I know before I start installing?](#index_split_006.html_filepos47492)

> > > [Installation](#index_split_006.html_filepos49693)

> > > [Where do I find on-line help for mars?](#index_split_006.html_filepos58673)

> > > [Where do I find the meaning of Eclipse icons for mars?](#index_split_006.html_filepos58996)

> [Chapter 4: Eclipse 4 terms](#index_split_007.html_filepos59570)

> > > [What’s a build (noun)?](#index_split_007.html_filepos59666)

> > > [What’s a bundle?](#index_split_007.html_filepos61137)

> > > [What’s a facet?](#index_split_007.html_filepos61552)

> > > [What's a feature?](#index_split_007.html_filepos61830)

> > > [What’s a file?](#index_split_007.html_filepos62037)

> > > [What’s a folder?](#index_split_007.html_filepos62284)

> > > [What's a perspective?](#index_split_007.html_filepos62589)

> > > [What’s a plug-in (plugin)?](#index_split_007.html_filepos63063)

> > > [What’s a project?](#index_split_007.html_filepos63309)

> > > [What's a resource?](#index_split_007.html_filepos63522)

> > > [What's a tag?](#index_split_007.html_filepos63781)

> > > [What's a task list?](#index_split_007.html_filepos64077)

> > > [What's a task view (task tab) (tag view)?](#index_split_007.html_filepos64268)

> > > [What’s a view?](#index_split_007.html_filepos64500)

> > > [What’s an editor?](#index_split_007.html_filepos64796)

> > > [What's "baked-in"?](#index_split_007.html_filepos65414)

> > > [What's JDT (Java Development Tools)?](#index_split_007.html_filepos65629)

> > > [What's the build path?](#index_split_007.html_filepos65978)

> [Chapter 5: Eclipse 4 file system](#index_split_008.html_filepos66470)

> > > [How does the Eclipse platform organize information? How does the Eclipse workbench organize information?](#index_split_008.html_filepos66608)

> > > [What's in a workspace directory?](#index_split_008.html_filepos67127)

> > > [What's in a project directory?](#index_split_008.html_filepos68248)

> > > [What's in the .metadata folder in the workspace?](#index_split_008.html_filepos70071)

> [Chapter 6: Eclipse 4 IDE](#index_split_009.html_filepos70480)

> > > [Does the Java EE IDE look different from the Java IDE?](#index_split_009.html_filepos70703)

> > > [What are the three regions in the IDE?](#index_split_009.html_filepos71428)

> > > [What's in the "Menus and tool bar region"?](#index_split_009.html_filepos72263)

> > > [What's the difference between the Project Explorer view and the Package Explorer view?](#index_split_009.html_filepos75463)

> > > [What's the outline view?](#index_split_009.html_filepos76039)

> > > [What's the problem view (problem tab)?](#index_split_009.html_filepos76364)

> > > [Where can I find information about the icons used in the IDE?](#index_split_009.html_filepos76759)

> > > [Where do I find eclipse error logs?](#index_split_009.html_filepos77844)

[Creating basic Java apps using Eclipse](#index_split_010.html_filepos78077)

> [Chapter 7: Create, build and run HelloWorld using the Eclipse IDE](#index_split_011.html_filepos78246)

> > > [Starting Eclipse](#index_split_011.html_filepos78417)

> > > [What does the error icon look like?](#index_split_011.html_filepos78840)

> > > [What does the warning icon look like?](#index_split_011.html_filepos79325)

> > > [What's a folding editor?](#index_split_011.html_filepos79819)

> > > [What is a warning?](#index_split_011.html_filepos80133)

> > > [What is an error?](#index_split_011.html_filepos80512)

> > > [What is an execution environment JRE?](#index_split_011.html_filepos81005)

> > > [What is code folding?](#index_split_011.html_filepos82054)

> > > [What is "drill down"?](#index_split_011.html_filepos82346)

> > > [What is Javadoc (JavaDoc)?](#index_split_011.html_filepos82950)

> > > [What is scope?](#index_split_011.html_filepos83872)

> > > [What is the difference between a closed project, an open project and an open expanded project?](#index_split_011.html_filepos84211)

> > > [What's the difference between the Project Explorer and the Package Explorer?](#index_split_011.html_filepos85582)

> > > [Exercise 7-1: Create a Hello1 project](#index_split_011.html_filepos85874)

> > > [Exercise 7-2: Create a Hello project with a main and comments](#index_split_011.html_filepos90316)

> > > [Exercise 7-3: Compare HelloWorld.java and Hello1World.java](#index_split_011.html_filepos90910)

> > > [Exercise 7-4: Close Hello and Hello1](#index_split_011.html_filepos92701)

> > > [Exercise 7-5: Delete the Hello1 project](#index_split_011.html_filepos93136)

> > > [Exercise 7-6: Add a method call inside Hello project's HelloWorld's main method](#index_split_011.html_filepos93784)

> > > [Exercise 7-7: Run Hello project](#index_split_011.html_filepos95344)

> > > [Exercise 7-8: Why a Hello project warning?](#index_split_011.html_filepos95888)

> > > [Exercise 7-9: Close Hello project](#index_split_011.html_filepos96806)

> > > [Questions](#index_split_011.html_filepos97133)

> [Chapter 8: Create a new project from the Hello project](#index_split_012.html_filepos98249)

> > > [What is a fully qualified name?](#index_split_012.html_filepos98665)

> > > [What is refactoring?](#index_split_012.html_filepos98889)

> > > [What is the launcher pattern (design pattern)?](#index_split_012.html_filepos99184)

> > > [What's a launcher?](#index_split_012.html_filepos99530)

> > > [Exercise 8-1: Make a copy of the Hello project and name it HelloArgs](#index_split_012.html_filepos99762)

> > > [Exercise 8-2: Make a copy of the Hello project into HelloLauncher](#index_split_012.html_filepos103027)

> > > [Questions](#index_split_012.html_filepos108760)

> [Chapter 9: Debugging HelloLauncher](#index_split_013.html_filepos109431)

> > > [What is debugging](#index_split_013.html_filepos109571)

> > > [What is a breakpoint (break point)?](#index_split_013.html_filepos109812)

> > > [What does "Toggle breakpoint" mean?](#index_split_013.html_filepos110163)

> > > [Exercise 9 -1: Debug HelloLauncher project](#index_split_013.html_filepos110466)

> > > [Questions](#index_split_013.html_filepos112562)

> [Chapter 10: Reduce coupling with separation of responsibility (more but smaller classes)](#index_split_014.html_filepos113011)

> > > [What is @Override](#index_split_014.html_filepos113395)

> > > [What is coupling?](#index_split_014.html_filepos113843)

> > > [What is a provider?](#index_split_014.html_filepos114360)

> > > [What is a renderer?](#index_split_014.html_filepos114700)

> > > [What is SoR (Separation of Responsibilities)?](#index_split_014.html_filepos114978)

> > > [What is an annotation?](#index_split_014.html_filepos115461)

> > > [Exercise 10-1: Improve Hello separation (Reducing Hello coupling) (Decoupling Hello)](#index_split_014.html_filepos116145)

> > > [Exercise 10-2: Improving Hello separation with interfaces](#index_split_014.html_filepos120872)

> > > [Questions](#index_split_014.html_filepos122531)

> [Chapter 11: Add a factory to improve Hello separation](#index_split_015.html_filepos123229)

> > > [What can be assigned to a class reference?](#index_split_015.html_filepos123388)

> > > [What can be assigned to an interface reference?](#index_split_015.html_filepos123793)

> > > [What's a child class?](#index_split_015.html_filepos124348)

> > > [What's a factory (factory class)?](#index_split_015.html_filepos124524)

> > > [What's a parent class?](#index_split_015.html_filepos124776)

> > > [What's a reference?](#index_split_015.html_filepos124955)

> > > [What's a class reference?](#index_split_015.html_filepos125306)

> > > [What's an interface reference?](#index_split_015.html_filepos126144)

> > > [Why do I care about class references and interface references?](#index_split_015.html_filepos126414)

> > > [Exercise 11-1: Improving Hello separation by adding a factory](#index_split_015.html_filepos126650)

> > > [Exercise 11-2: Improving Hello separation by adding a factory Part 2](#index_split_015.html_filepos134432)

> [Chapter 12: Reduce coupling even more with a smarter factory](#index_split_016.html_filepos136269)

> > > [What is Spring?](#index_split_016.html_filepos136435)

> > > [What's a user library?](#index_split_016.html_filepos136998)

> > > [What's an appender?](#index_split_016.html_filepos137217)

> > > [What's an external jar?](#index_split_016.html_filepos137415)

> > > [Exercise 12-1: Improving Hello separation by using a factory from Spring Framework](#index_split_016.html_filepos137682)

> > > [Exercise 12-2: Improving Hello separation clean up](#index_split_016.html_filepos149711)

> > > [Questions](#index_split_016.html_filepos150484)

> [Chapter 13: Reduce coupling even more with DI (dependency injection)](#index_split_017.html_filepos150889)

> > > [What is deprecated?](#index_split_017.html_filepos151485)

> > > [What is DI (Dependency injection)?](#index_split_017.html_filepos151836)

> > > [Exercise 13-1: Improving Hello separation by using Spring and DI](#index_split_017.html_filepos152503)

> > > [Exercise 13-2: Improving Hello separation by using Spring, DI and more Xml](#index_split_017.html_filepos158167)

> > > [Questions](#index_split_017.html_filepos161339)

> [Chapter 14: Export an existing project, import an existing project](#index_split_018.html_filepos161789)

> > > [What does export mean in Eclipse?](#index_split_018.html_filepos161961)

> > > [What does export mean in Java?](#index_split_018.html_filepos162319)

> > > [What does import mean in Eclipse?](#index_split_018.html_filepos162663)

> > > [What does import mean in Java?](#index_split_018.html_filepos163005)

> > > [What is EAR file format?](#index_split_018.html_filepos163371)

> > > [What is JAR file format?](#index_split_018.html_filepos163819)

> > > [What is WAR file format?](#index_split_018.html_filepos164352)

> > > [What's a Jar (Java ARchive)?](#index_split_018.html_filepos164677)

> > > [What's an executable jar file?](#index_split_018.html_filepos165563)

> > > [What's an EAR (Ear file) (EAR file) (Enterprise ARchive file)?](#index_split_018.html_filepos165879)

> > > [What's extract required libraries?](#index_split_018.html_filepos166294)

> > > [What's package required libraries](#index_split_018.html_filepos166505)

> > > [Questions](#index_split_018.html_filepos166774)

[Appendices](#index_split_019.html_filepos167076)

> [Appendix I: Answers to questions](#index_split_019.html_filepos167183)

> > > [Chapter 7](#index_split_019.html_filepos167285)

> > > [Chapter 8](#index_split_019.html_filepos169683)

> > > [Chapter 10](#index_split_019.html_filepos170194)

> > > [Chapter 12](#index_split_019.html_filepos170693)

[Author's Biography](#index_split_019.html_filepos171340)