![](Images/cover.jpg)

![cover.jpg](Images/cover.jpg)

Table of Contents[Chapter 1: Centralized Logging Is a Modern Solution for At-Scale Applications](../Text/Section0001.xhtml)[Chapter 2: Get Started Quickly With Java Logging](../Text/Section0002.xhtml)[Chapter 3: Getting Started Quickly With Log4j2 Configuration](../Text/Section0003.xhtml)[Chapter 4: Getting Started Quickly With PHP Logging](../Text/Section0004.xhtml)[Chapter 5: Getting Started Quickly With Ruby Logging](../Text/Section0005.xhtml)[Chapter 6: Getting Started Quickly With Rails Logging](../Text/Section0006.xhtml)[Chapter 7: Getting Started Quickly With Swift Logging](../Text/Section0007.xhtml)[Chapter 8: Getting Started Quickly With Scala Logging](../Text/Section0008.xhtml)[Chapter 9: Getting Started Quickly With Django Logging](../Text/Section0009.xhtml)[Chapter 10: Getting Started Quickly With Angular Logging](../Text/Section0010.xhtml)[Chapter 11: Getting Started Quickly With Meteor Logging](../Text/Section0011.xhtml)[About Scalyr](../Text/Section0012.xhtml)

## Chapter 1: Centralized Logging Is a Modern Solution for At-Scale Applications

I remember the very first website I created. This was in the late 90s. It was about military fighter jets, and I built it in pure HTML with inline CSS—no JavaScript. I also only ever ran it locally.

The most complex websites of that time were probably e-commerce websites. They had to handle content management, user accounts, and payment processing. While not a trivial task at the time, the way the web applications of the late 90s and early 2000s were constructed seems simple and straightforward today.

Things have shifted over the years. Companies used to have just one instance of an application running on a single server. Only the biggest enterprises needed to think about scaling because most websites saw a limited amount of traffic. Today, even relatively small organizations take scale into account.

Luckily, the cloud allows us to build services without needing to manage our hardware. This can significantly save cost and effort for enterprises, both small and large. Going further, microservices give us the opportunity to develop individual services that remain loosely coupled and scale more easily.

Yet we can’t just say things have become easier and simpler. In fact, microservices in a cloud environment can form a jungle of moving parts, making it hard to get an overview of their communication flow. We need something more.

We need logging.

Scale Has Increased Our Need for Logging

If you have a single application with maybe one or two dependencies to other services, logging is easy. The application can log information to the server’s disk, which you can then check to see what’s going on. You’ll get a chronological overview of all performed actions. This gives you an easy way of investigating any issues that arise.

In a scaled environment, things get a bit more complicated. Your application probably consists of multiple services, with either services offering different functionalities or different instances of the same service. The interaction of these services increases the chances of things going wrong. So the need for logging increases as well.

When you make an in-process method call, not much can break so long as you provide the correct input. However, if you’re making a call to another service, there are more opportunities for things to fail:

*   The network might be slow or down.
*   The other service might produce an error.
*   Your service could be providing the wrong input.

All this magnifies the need for logging so that you can more easily see what’s going wrong.

The Need for Centralized Logging

Having each service log to the server’s disk quickly becomes a nightmare. When one service calls another, you need to look at the other service’s logs. If that service calls a third, you have even more work to do. After investigating all logs, you need to aggregate this information to complete the picture. And if you’ve ever investigated issues that span several services, you’ve experienced the pain of logs spread out everywhere.

This is why centralized logging is becoming increasingly important, as companies move to an architecture where one application actually consists of multiple services interacting with each other. But in fact, this isn’t so different from what we used to do. In the past, we went to a central location to read the logs—specifically, the server running the single service. Now that we have multiple services, it’s still useful to be able to go to a single location.

Microservices as a Model for Massive Scale

Microservices are a great way of developing applications that need to scale. But they create challenges for logging. We need to be able to correlate log statements across different services, especially when many requests are coming in at a fast pace.

While that all might sound complicated, logging is probably still the best way to identify the root cause of problems. Monitoring provides a great overview of the health of our applications, but when something goes wrong, we often need to go back several steps to see what led to the issue. A stack trace usually isn’t enough.

Centralized logging allows us to follow the flow of a user’s request across multiple services, so it’s the way to go.

Hybrid Environments

These days, many companies take a hybrid approach to the cloud/on-premise choice. Some services run on local servers that the company manages. Some might be running on a hosted infrastructure. Yet others may run on one of the major cloud providers.

This is due in part to our world is evolving so quickly. We might start by running on Platform A but later decide to switch to Platform B for new services. The old services aren’t always ported immediately. And why should they be, if they’re running great?

Logging is often overlooked when planning these architectures. The first step is to log to the local file system. This works well on the developer’s machine. But when we’re talking about multiple services deployed across multiple platforms, this approach starts falling apart. Yet many companies keep each service logging to its own location.

Migrating all your services to a single platform would be a costly and unnecessary solution. A far simpler solution is to keep everything running where it is but send the logs to a central location. Of course, this means the central log can become massive. But with good tools, this shouldn’t be an issue.

Centralizing logging can really save a company money. Support staff will need less time to find the root cause of issues. Developers will have the information to reproduce the issue faster. This means less frustration in the organization and less chance of people leaving. But it also means less frustration for your customers, as issues can be identified and resolved sooner.

The New Serverless

Serverless, or function as a service (FaaS), is a new way of developing applications. I’ve seen it described as microservices on steroids. Each function has a very limited scope. This means an application consists of tens if not hundreds (or thousands!) of separate functions.

Because all these function interact with each other, it’s difficult to get an idea of the application’s flow by just looking at the logging of one function. In Amazon’s AWS Lambda, for example, you can use CloudWatch to check the logs of a single function. But currently, it’s still impossible to combine the logs of different functions; you’re forced to switch between multiple views or queries.

Centralized logging is even more important here. Instead of having a few microservice logs, you can now have an incredible amount of logs in different locations.

Easier, Not Simpler

Developing software has become easier thanks to the plethora of tools that help developers by eliminating difficult tasks. These tools include

*   The cloud.
*   Modern IDEs.
*   Development frameworks and libraries.
*   Automated testing, building, and deployment tools.
*   Low- or no-code platforms that allow you to build applications with little to no coding experience.

But even though things are easier, they haven’t become simpler. In fact, they’re more complex. Instead of building a single stand-alone application, we now write applications that consist of multiple smaller applications. These all interact with each other and with services that are out of our control.

All this complexity gives us great advantages, like easier scaling and improved efficiency. But they also increase the amount of places where bugs and issues can occur. Luckily, we have modern monitoring tools that can quickly notify us and even provide context and information. But logging is still the best way to see what led up to the issue.

In these complex environments, centralized logging is the number one way to gain access to all necessary information. Centralized logging makes our lives easier and allows us to fix issues faster and cheaper.

## Chapter 2: Get Started Quickly With Java Logging

For our first experiment in getting started quickly with logging, we’re going to tackle Java. In this chapter, we’ll not only provide a quick guide but also go into more detail about logging, diving particularly into the what and why of logging.

![http://blog.scalyr.com/wp-content/uploads/2018/01/Java-Logging-Icon.png](Images/Image280.png)

The Simplest Possible Java Logging That Could Possibly Work

For this demo, I’m going to use the free [community version of IntelliJ IDEA](https://www.jetbrains.com/idea/download/#section=windows). I’m also assuming that you have the [Java JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html?ssSourceSiteId=otnpt) installed on your machine.

![IntelliJ IDEA Screenshot](Images/Image287.png)

On the next screen, select Java as the type of project on the left panel. You’ll also need to point to the JDK’s path, in case you haven’t yet.

![JDK Path Screenshot](Images/Image296.png)

Third step—mark the Create project from template option and then select Command Line App:

![New Project Screenshot](Images/Image304.png)

I’ve called my project JavaLoggingDemo, as you can see from the image below.

![JavaLoggingDemo Screenshot](Images/Image311.png)

After doing the steps above, you should see the Main class that was automatically created for you. It should look like this:

![](Images/Image319.png)

Let’s get to work. Replace the // write your code here comment with the following line:

![](Images/Image328.png)

Now you have an application that displays a friendly greeting.

Next, let’s run our app. Go to Run > Run ‘Main’ or use the shortcut SHIFT+F10 (Windows and Linux) or CTRL+R on Mac.

If everything went well, you should see something like this:

![Program File Screenshot](Images/Image335.png)

Nice. But let’s say the requirements for our little app changed, as they always seem to do. Now we need our app to not only display a message but also log it somewhere. How do we go about that?

There are a lot of sophisticated options we could use, but let’s try to do the simplest thing we can. Edit the code in your main function so it looks like this:

![](Images/Image343.png)

Notice the changes. We’ve added a new variable (message) to store the greeting’s text. Then there’s the printing. And finally, there’s a new line, which is meant to save the text to a file.

We also had to add a throw declaration to our method since the last line can throw an IOException. Additionally, we’ve added some new import declarations. The whole code now looks like this:

![](Images/Image351.png)

When you run your application again, it should behave the same as before. But the last line added will create a log file for you. The log file will be located in your project folder:

![Project File Screenshot](Images/Image358.png)

That’s pretty much it. You’ve just written your first Java logger! And with that first, small step, you’re ready to try larger ones.

What Is Application Logging?

Let’s zoom out for a second and briefly define what application logging is.

According to [Wikipedia](https://en.wikipedia.org/wiki/Log_file),

In computing, a log file is a file that records either events that occur in an operating system or other software runs, or messages between different users of a communication software. Logging is the act of keeping a log.

A little bit vague, right? I tend to prefer the definition we gave at the beginning of the Scalyr’s first book on logging, [The Scalyr Guide to Getting Started Logging as Quickly as Possible](https://www.amazon.com/Getting-Started-Logging-Quickly-Possible-ebook/dp/B07H8SNT2Q):

Application logging involves recording information about your application’s runtime behavior to a more persistent medium.

With the what out of the way, let’s get to the why of logging.

What’s the Motivation for Logging?

I think the key part of the logging definition from the previous section was the word “persistent.” Why would we need to record information about the behavior of our app in a persistent medium?

Well, for the same reason we record anything to a persistent medium: so we can get back to it later. The question then becomes: “Why would you want to do that with events that happened in an application execution?”

It all boils down to the nature of software itself.

A piece of software in production is a very complicated thing, more often than not running in a totally non-controlled environment. How do you know it’s going to work? And when things go wrong, how can you know what exactly went off the rails?

You can always cross your fingers and hope, but as they say, hope is not a strategy. Logging is, though!

In a nutshell, you use logging so that you can after-the-fact debug your application. By reading the log entries, you can understand the events that happened with your application, or even retrace the steps taken by a user, in order to diagnose and fix issues.

Evolving Our Approach: What Should We Capture? And to Where?

Being able to do an after-the-fact investigation on your app sounds like a great benefit—and indeed it is. The humble logger we just created isn’t able to provide us this benefit, though, since all it can do is write some text to a file.

Our job now should be to evolve our logger, turning it into a richer source of information for its future readers. So how do we go about that?

The key point to understand is the nature of a log entry. Think of a log entry as an event. Something that is of interest to your application happened in a given moment in time. So the value of your log entry derives from the data you capture about the event.

The following list contains some examples of data that you’ll probably want to capture:

*   A timestamp. Exactly when did the event take place? (You’ll want to record times in UTC and using a standard format such as ISO-8601, in case you’re logging to a file.)
*   Context that makes it clear to a reader what the entry is about. Just recording “Hello, user!” might prove confusing weeks or months later. A better message might say, “Recorded user greeting of ‘Hello, user!’”
*   Tags or categories for each entry, to enable later search and classification.
*   Log levels, such as Error, Warning, or Info, that allow even more filtering and context.

After deciding what things you want to capture, the next step is defining where you want to log to. Even though I’ve used a file in our first example, there’s nothing stopping you from logging to other media, such as a database (relational or not), the Windows event viewer, or even the console.

Enter the Logging Framework

Time to get back to our demo. Here’s the thing: this was designed to give you a quick start on the Java logging world. But now you’re equipped to look at it in a more critical way. So let’s do just that.

As it turns out, our humble logger is inadequate in several important ways.

For one thing, the code always overwrites the log file. A log strategy that only allows you to see the last event isn’t terribly useful, is it? Since we’re talking about overwriting the file, it probably wouldn’t hurt to think about file permissions, how to deal with concurrent access, and other things of that sort.

Finally, it sounds like an awful lot of work having to write boilerplate code in each logging call to get log levels, timestamps, and all that jazz I mentioned in the previous section.

I could go on and on, but you’ve got the picture: coming up with a sound Java logging approach requires a lot of thought. I have good news, though. As it turns out, people have already solved these problems. Not only that, they provide their solutions for you, ready to use and often for free, in the form of a logging framework.

A logging framework is a package you install in your application that provides easy and configurable logging for you. With a little bit of configuration, you can make one-line calls as simple as the one in our toy example. But this time, they’ll have consistent and nicely formatted log entries, and they’ll have answers to all those questions from the previous section.

Installing a Logging Framework

The first thing we’re going to do is go back to our codebase and delete that line that writes to the file. Then we can proceed to install a logging framework called [Log4j](https://logging.apache.org/log4j/2.x/). This is only one of the options out there, and I do encourage you to try alternatives later. But since this is a quick guide, it makes sense to go with Log4j because it’s a widely used framework.

On the Project tool windows, right-click on the JavaLoggingDemo module and then on Add Framework Support...

![Add Framework Screenshot](Images/Image368.png)

Now, select Maven and click OK:

![Maven Screenshot](Images/Image375.png)

After you’ve done this, the IDE will create a pom.xml file for you and open it for editing:

![Pom XML Screenshot](Images/Image382.png)

Now, use the following XML text in your file:

![](Images/Image390.png)

The whole file should look like this by now:

![](Images/Image397.png)

After adding the dependencies to the file, you should see a small pop-up in the bottom-right corner of your screen. Click on Import Changes to finish the installation.

![Import Changes Screenshot](Images/Image405.png)

Configuring the Logger

Now it’s time to configure Log4j. What I’m going to show you is just one way of doing this; it’s not the only one, and it’s probably not even the best one, whatever “best” may mean. But it’s definitely shorter than a lot of the tutorials you see out there.

Pretty much all you have to do is create a configuration file and then write some lines of code. Don’t believe me? Well, let me just show you!

First, go to the Project tool window on IntelliJ. Expand the folders and locate the resources folder, under JavaLoggingDemo > src > main, just like in the image below:

![Java Logging Demo Screenshot](Images/Image412.png)

Now, right-click on the resources folder and then select New > File:

![New File Screenshot](Images/Image420.png)

When you’re prompted for a name, enter log4j2.xml. After the file is created, add the following text to it:

![](Images/Image429.png)

Editing the Code

First, at the top of the file, add the following two import declarations:

![](Images/Image440.png)

Then, add the following line to the top of the Main class, which declares a private field to hold the instance of the logger:

![](Images/Image455.png)Finally, add the following line of code to where you had the call to Files.write(Paths.get(“log.txt”), message.getBytes()):

![](Images/Image462.png)

The whole class should now look like this:

![](Images/Image470.png)

And we’re done! Now all you have to do is run the application.

Checking the Results

Now, if you navigate back to the application folder, you should notice a new file there called proper.log. If you open it using a text editor, you should see the following:

![](Images/Image477.png)

Let’s break this line into its components.

First, we have the timestamp, 2017-12-31 15:39:29.739 , in the ISO-8601-compliant format.

Then we have [main]. This refers to the name of the thread from which the event originated.

Next is Info, the logging level.

Then comes com.company.Main, the name of the class.

And last but not least, the message itself: Hello there!

The Power of a Logging Framework

I think you’ll agree that our logger just got a lot more useful after the update we made. Just by creating a config file and writing a few lines of code, we were able to configure a realistic example of a logger. This isn’t all there is to it, of course, but it’s already enough to be useful in a real application. What’s more, it gives you a pretty good idea of the power a logging framework can put into your hands.

The XML configuration file is one of the places this power really manifests itself. It offers you a lot of options to configure each entry that you log, such as the name of the log file or if the logger should append to it or overwrite it.

A lot of the flexibility Log4j provides is due to something called an appender. The appender is the component that effectively writes the message to some medium, and there are many of them available. This means it’s possible to direct your logs somewhere else entirely—just by adding a new appender to the XML file—without even touching your application code.

Separation of concerns at its finest, if you ask me.

What’s Next?

What we’ve seen in this chapter is just the tip of the iceberg. If this is your first time logging, make no mistake: you now have a lot of learning ahead of you. But you have the advantage of already having a live, functional, and realistic setup to work with. Start by playing with it and tweaking it. Here are some tips on what you can do:

*   Learn how to configure different loggers, one for each log level.
*   Research and try out the different appenders available.
*   Play with the options available for the “layout” entry.
*   Learn about the other ways you can configure Log4j.
*   Try some new logging frameworks, once you’re confident enough with Log4j. You have lots of options.

Learning something from the ground up can be an overwhelming task. Fortunately for you, you don’t have to do that. We’ve given you the fundamentals upon which you can build a solid and long-lasting body of knowledge.

Now it’s up to you.

This chapter was contributed by Carlos Schults. [Carlos](http://carlosschults.net/) is a software developer with experience in both desktop and web development, now trying his hand at mobile. He has a passion for writing clean and concise code, and he’s also very interested in practices that help you improve your app’s health.

## Chapter 3: Getting Started Quickly With Log4j2 Configuration

In the previous chapter, we used Log4j, a logging framework from the Apache project. Let’s go one step further with Java application logging and look at Log4j2 configuration.

Log4j’s capabilities have made it one of Java’s most popular logging frameworks. It can be configured for multiple logging destinations and a variety of log file formats. Log messages can be filtered and directed at the individual class level, giving developers and operations personnel granular control over application messages.

Let’s examine these mechanisms by configuring Log4j with a command line Java application.

![](Images/Image485.png)

Sample Application

Let’s start where we left off in the previous chapter: with an application that logs with Log4j.

![](Images/Image492.png)

We’re logging the same message at each of Log4j’s predefined logging levels: Trace, Debug, Info, Warn, Error, and Fatal.

We will be using Log4j’s YAML file format, so you’ll need to add a few additional dependencies to your pom.xml (or build.gradle).

![](Images/Image500.png)

Set this code up so you can build and run it using your favorite Java tools.

Essential Log4j2 Configuration

Next, let’s talk configuration.

Default Configuration

Let’s run our application without a Log4j configuration file. If you already have one, delete it or move it to another file name so that Log4j will ignore it.

When we run the application, we see this on the console:

![](Images/Image507.png)

Two of the six log messages, the ones specified as Error and Fatal, are sent to the console.

Note: Log4j has a default configuration. It will log to the console, showing messages classified as Error or higher.

Knowing how Log4j will behave without a configuration file is useful, but let’s look at how to set it up for our needs.

Configuration File Location

We can provide Log4j with a configuration file in a specific location via the log4j.configurationFile system property. This is the first place it will look for a configuration file.

If Log4j cannot find the system property, it looks for a file in the classpath. Since Log4j2 supports four different file formats and two different file naming conventions, the rules for locating a file are complicated. We’ll go over how to locate a file after we cover the different format and naming options.

Configuration File Formats

Log4j will load Java properties and YAML, JSON, and XML configuration files. It identifies the file format by examining the file extension.

*   For Java properties, the extension is .properties
*   For YAML, the extensions are .yaml or .yml
*   For JSON, the extensions are .json or .jsn
*   For XML, the extension is .xml

A file specified by the log4j.configurationFile system property must have one of these file extensions, but it can have any base name. Log4j will parse it based on the format indicated by the extension.

When Log4j scans the classpath for a file, it checks for each format in the order listed above and stops when it finds a match. For example, if it finds a YAML configuration, it will stop searching and load it. If there is no YAML file but it finds a JSON one, it will stop searching and use that instead.

Configuration File Names

When Log4j scans the classpath, it looks for one of two file names: log4j2-test.[extension] or log4j2.[extension]. It loads test files first, giving developers a convenient mechanism for forcing an application to log at the Debug or Trace levels without altering the standard configuration.

Scanning for Configuration

When we put the rules for file formats and names together, we can see Log4j’s algorithm for configuring itself.

If any of the following steps succeeds, Log4j will stop and load the resulting configuration file.

1.  Check for the log4j.configurationFile system property and load the specified file if found.
2.  Search for log4j2-test.properties in the classpath.
3.  Scan classpath for log4j2-test.yaml or log4j2-test.yml.
4.  Check for log4j2-test.json or log4j2-test.jsn.
5.  Search for log4j2-test.xml.
6.  Look for log4j2.properties.
7.  Search for log4j2.yaml or log4j2.yml.
8.  Scan classpath for log4j2.json or log4j2.jsn.
9.  Check for log4j2.xml.
10.  Use the default configuration.

Practice Proper Configuration File Hygiene

There are 12 potential configuration file names for Log4j. Loading the wrong one can lead to lost logging information or diminished performance. That’s because an application may log unnecessary messages in a production environment.

Before deploying code, make sure your application has one—and only one—configuration file and that you know where it is. If you insist on loading configuration from the classpath, scan for spurious files before releasing your code.

Basic Configuration

Now that we know how to supply a configuration to Log4j, let’s create one and use it to customize our application.

Log4j’s Default Configuration Revisited

We’ll start with the default configuration and modify our application’s behavior from there. Taking the hint from Log4j’s configuration rules, we’ll use YAML.

The default configuration looks like this:

![](Images/Image515.png)

Create a file name log4j2.yaml with these contents and set log4j.configurationFile to point to its location.

Next, run the application. You’ll see the same output as before.

![](Images/Image524.png)

We’ve taken control of our application’s logging configuration. Now let’s improve it.

Log File Location

The first step is to get our logs off of the console and into a file. To do this, we need to understand appenders.

Appenders put log messages where they belong. The default configuration supplies a console appender. As the name suggests, it appends messages to the console.

![](Images/Image535.png)

We want a file appender. Let’s replace our console appender.

![](Images/Image548.png)

File appenders have a name, just like console appenders. But instead of a target, they have a fileName.

Similar to console appenders, they also have a PatternLayout, which we’ll cover below.

The name is not just for show. If we want to replace the console appender with the file appender, we need to let our logger know where to put our log messages.

So change the ref value in the logger to the file appender’s name.

![](Images/Image555.png)

Now, rerun the application. Instead of logging to the console, it places the messages in a file named logfile.log in the working directory. We’ve moved our logs to a file!

Logging Levels

We still only saw two of our six log messages in our log file. Let’s talk about loggers and how they manage log messages.

Our basic configuration defines a single logger.

![](Images/Image563.png)

It has a level of Error, so it only prints messages that are Error or Fatal.

When a logger receives a log message, it passes it on or filters it based on its configured level. This table shows the relationship between logger configuration and log message level.

![](Images/Image570.png)

So if we change the level of our logger, we’ll see more messages. Set it to Debug.

![](Images/Image578.png)

Next, rerun the program. The application logs all of the messages that are Debug level or higher.

Logger Hierarchy

Log4j arranges loggers in a hierarchy. This makes specifying a different configuration for individual classes possible.

Let’s change our application and see this in action.

![](Images/Image585.png)

We’ve added an inner class that creates a logger and logs a message with it.

After Main does its logging, it calls LoggerChild.

If we run this with our current config, we see the new message and that it’s logged from a different class.

![](Images/Image593.png)

Loggers have a class hierarchy similar to Java’s. All loggers are descendants of the Root logger we’ve been working with so far. Loggers that lack any specific configuration inherit the Root configuration.

So when Main and LoggerChild create loggers using their class name, these loggers inherit Root’s configuration, which is to send Debug level and higher messages to the File_Appender.

We can override this specifying configuration for the two loggers.

![](Images/Image600.png)

Loggers are named in the logger section. Since we’re listing two, we use the YAML array syntax.

We set com.company.Main logger to Error and com.company.Main.LoggerChild to Debug.

The additivity setting controls whether or not Log4j will send messages from a logger’s ancestor to a descendant. If set to true, both loggers will process the same message. Some systems want to add the same message to two different logs. We don’t want this behavior, so we’ve overridden the default and specified false.

Now run the program again:

![](Images/Image608.png)

We only saw the error message from Main but still saw the debug message from LoggerChild!

More Than One Appender

Just like we can have more than one logger, we can have more than one appender.

Let’s make a few changes to our configuration.

Add a second file appender. To do this, create a list with the original appender and the second one with a different name and file. Your Appenders section should look like this:

![](Images/Image618.png)

Next, point the LoggerChild logger at the new appender. Your Loggers section will look like this.

![](Images/Image629.png)

Now run the application. You’ll see two different log files, each with the messages from their associated classes.

Log Message Formatting

Each of our appenders has a PatternLayout.

![](Images/Image642.png)PatternLayout is an instance of a Log4j layout class. Log4j has built-in layouts for logging messages in CSV, JSON, Syslog, and a variety of different formats.

PatternLayout has a set of operators for formatting messages that works like C’s sprintf function. By specifying a pattern, we control the format of log messages when they’re written by the appender.

Our layout string looks like this:

![](Images/Image649.png)

Each % corresponds to a field in a log message.

![](Images/Image657.png)

There are many additional operators for PatternLayout, too, which you can explore on your own.

Variable Replacement

Configuration files can become repetitive as appenders and loggers multiply. Log4j supports variable substitution to help reduce repetition and make things easier to maintain. Let’s refine our configuration with the use of Properties.

![](Images/Image664.png)

At the top of the file, we declared two Properties, one named LogDir and another DefaultPattern.

After declaring a property, it can be used in the configuration using braces and a dollar sign: ${LogDir} or ${DefaultPattern}.

LogDir is a subdirectory name we added to the names of the two log files. When we run the application, Log4j will create this directory and place the log files there.

We specified DefaultPattern as the pattern layout for our two log files, moving the definition to one place. If we want to modify our log file format, we only have to worry about changing it once now.

Log4j can also import properties from the environment. (You can read more about this [on the Apache Logging Services website.](https://logging.apache.org/log4j/2.x/manual/configuration.html#Property_Substitution)) For example, if we want to import the log file directory from a Java system property, we specify it as ${sys:LogDir} in the Log4j configuration and set a LogDir system property to the desired directory.

Automatic Reconfiguration

Log4j can reload its configuration at a periodic interval, giving us the ability to change an application’s logging configuration without restarting it.

Add the monitorInterval setting to the Configuration section of the file and Log4j will scan the file at the specified interval.

![](Images/Image672.png)

The interval is specified in seconds.

Conclusion

Log4j is a powerful logging framework that allows us to configure our applications to log in a variety of different ways, with granular control over how different components use log files. This tutorial covered the basic aspects of configuring Log4j, but there’s much more to learn. You can learn about Log4j configuration on the project’s [website](https://logging.apache.org/log4j/2.x/manual/configuration.html).

This chapter was contributed by Eric Goebelbecker. [Eric](http://ericgoebelbecker.com/) has worked in the financial markets in New York City for 25 years, developing infrastructure for market data and financial information exchange (FIX) protocol networks. He loves to talk about what makes teams effective (or not so effective!).

## Chapter 4: Getting Started Quickly With PHP Logging

In this chapter, let’s discuss logging techniques in a very popular language: PHP.

I’ll open with a quick example of manual logging in PHP. Then I’ll revisit the details discussed in chapter two of this book—details about why logging matters and what your logs should show. And lastly, I’ll show you how to set up and use the most popular PHP logging framework.

Let’s get started, then!

![](Images/Image679.png)

A (Super Simple) Example of PHP Logging

For the purpose of this tutorial, I’ll be using Linux with a clean installation of the [LAMP stack](https://www.digitalocean.com/community/tags/lamp-stack?type=tutorials). You might need to adjust the tools and the commands if you’re using Mac or Windows instead of Linux.

Navigate to the /var/www/html folder and delete a file named index.html from there:

![](Images/Image687.png)

Then create a new file index.php and open it in your favorite text editor (I’m using Emacs):

![](Images/Image694.png)

Add the following HTML code into index.php:

![](Images/Image702.png)

This HTML code will create a simple subscription form. To see the resulting page, open your browser and go to http://localhost:

![](Images/Image711.png)

Even though you can see the form in the browser, it doesn’t do anything useful right now. To make it functional, add the following PHP script at the top of the index.php file, before the HTML code:

![](Images/Image722.png)

The above code will extract the name and email parameters from the submitted request and pass them into the subscribe function, which will have the code that takes care of subscribing new users. But since this tutorial is about logging, I’ll leave the subscribe function’s body empty for now.

Now, let’s say you want a log file that keeps track of all subscription requests alongside their respective parameters. You can do that by adding just two lines right before a call to the subscribe function:

![](Images/Image736.png)

The additional two lines of code will call to PHP’s file_put_contents function that will append a new log message to the contents of server.log file.

Now if you open http://localhost in your browser, populate the input fields, and click on the subscribe button, this script will create a new file named server.log in the /var/www/html directory and write the log entry into it. I can read the contents of this file using cat command:

![](Images/Image743.png)

Congratulations! You’ve logged your first entry written in PHP.

Now, let’s back up a bit.

What Is Application Logging?

You probably already have an intuitive understanding of what logging is, but it’s still worth taking the time to go over a proper definition we can build upon. We previously defined application logging like this:

Application logging involves recording information about your application’s runtime behavior to a more persistent medium.

There are two important points to note here.

First, logging is all about the application’s runtime behavior. In other words, it involves recording the application’s events as a function of time.

Second, you always want to store logs in a more persistent medium. The exact meaning of “more persistent” will vary depending on your requirements and environment, but at the very least, you’ll want to be able to read the logs even if the application—or the entire server—crashes.

While this definition explains what logging is, it doesn’t explain why you’d want to use logging in your application. That’s an important question, and I’d like to address it in detail.

Why Log?

If we lived in an ideal world, our applications would just work exactly as we planned. However, the reality is that even well-constructed applications have bugs and will be at risk of crashing at one point or another.

When you develop on your personal computer and encounter errors, they’re usually relatively simple to resolve. After all, you know what you’ve been working on and what sequence of events led to the error. In addition, you can develop in debug mode, which gives you lots of additional information about the system.

But at some point, you need to release the application to your users. They will use it in original ways and in environments you couldn’t have imagined, and there will potentially be many of them using the application concurrently. Plus, your application will need to function for much longer periods of time. Debugging errors in this situation is impossible without additional information.

Enter logging.

Having a record of your application’s past runtime behavior allows you to investigate all kinds of undesired behavior post-factum. In other words, even if your application crashes and loses all its runtime state, you’ll still be able to understand what led to that crash using application’s logs.

But the usefulness of logs doesn’t stop there. Logs become priceless when users report bugs. They can audit your application, including regulatory audits required in specific business domains. Or they can be processed and analyzed in real time to warn you about potential performance issues. That’s just to name a few things.

In short, application logging is a must for production applications because it gives you visibility into your application’s runtime history.

What Should You Log?

The simple logging approach from the beginning of this chapter fulfills the persistence requirement because it stores the logs in a file. However, it’s not great for recording runtime behavior because it doesn’t tell you exactly when each specific event happened.

This leads to a more general question: what information should be logged?

It’s a widespread practice to include at least the following information in each log entry:

*   A timestamp that states exactly when the event described by the log entry happened. To make your life easier, use properly formatted [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date/time in UTC.
*   Event context that is descriptive. For example, it would be a bad idea to log name: testName; email: test@test.com because a month from now, you’ll probably forget what this means. Here’s some context to make the log entry more descriptive: Subscription; user: testName email: test@test.com.
*   Log severity level, such as Error, Warning, Info, etc. This information provides additional context and allows you to easily filter logs by severity.

I suggest that you treat the above list as the absolute baseline for your logging strategy and don’t log less information than that. Otherwise, you’ll have a hard time reading your logs and making sense of them.

Make Logging Easier With the Monolog Framework

In the example at the beginning of this chapter, I showed you how to do basic logging in PHP. However, my solution didn’t log timestamps and severity levels, which, as you now know, are two mandatory pieces of information that must be included in each log entry.

Sure, I can add more code and enhance my solution to accommodate more advanced needs, but that would be a waste. See, I do logging only because I need to—it’s not really part of my application’s functionality. Therefore, each minute I spend on implementing logging solutions is one less minute I have to work on the core functionality of my application.

Luckily, my logging needs are very similar to the needs of millions of other developers, so this problem has already been solved in form of logging frameworks. These are third-party libraries that I can import and use in my project without having to concern myself with exactly how they work. In other words, there’s no need for me to reinvent the wheel when it comes to logging.

The most popular logging framework for PHP is [Monolog](https://github.com/Seldaek/monolog). In the next sections, I’ll show you how you can use it in your projects.

Installing Monolog PHP Logging Framework

If you’re developing your application using a PHP framework (like Laravel, for example), chances are this framework already integrates with Monolog. Check your framework’s documentation for details.

Since I’m working with a very simple PHP project, I can show you how to install and use Monolog from scratch.

First, you’ll need to install the PHP [Composer](https://getcomposer.org/doc/00-intro.md) package manager. The following commands will achieve that:

![](Images/Image751.png)

Once you’ve got Composer on your machine, go to the root directory of your project at /var/www/html/ and execute the following command:

![](Images/Image758.png)

This command will create vendor/directory and import Monolog files there. The next step will be to make use of Monolog from within the PHP code.

Using Monolog

To use Monolog in your code, you’ll need to load it as a dependency. For this purpose, Composer conveniently generated an autoload.php file that you can access from your code.

Put the following code at the top of your PHP script in an index.php file:

![](Images/Image766.png)

And right after that, specify two specific Monolog dependencies that you’re going to use:

![](Images/Image773.png)

Logger is the object that generates logs, and [StreamHandler](https://docs.python.org/2/library/logging.handlers.html) is a special object that Logger uses internally to write logs to files. As you might guess, Monolog supports different handlers that allow you to route the logs into different mediums.

So far, you’ve loaded Monolog and imported specific dependencies. Now instantiate a new Logger and name it SimpleLogger:

![](Images/Image781.png)

Next, use StreamHandler to make sure the logger stores the logs into your existing server.log file:

![](Images/Image788.png)

The second parameter in StreamHandler’s constructor defines the lowest severity level it picks up. Since you want it to capture all log entries in this case, specify the lowest severity level, which is Debug.

After setting up the Logger object, you can replace your old logging implementation with Monolog’s logger. So, delete this line:

![](Images/Image796.png)

Now replace it with the following call:

![](Images/Image805.png)

As you can see, even though you had to do a bit of upfront setup, this process made logging much simpler. Given that in real applications you might want to log hundreds of events, this conciseness will become very handy.

All in all, your index.php file should look like this:

![](Images/Image819.png)

Reading Monolog Logs

If you go to http://localhost in your browser again, specify the same user details, and click on subscribe, a new log entry will be added to server.log file. Let’s contrast the original log entry from the first example with the one generated by Monolog.

Here’s the original log entry:

![](Images/Image833.png)

And here’s what Monolog produced:

![](Images/Image840.png)

As you see, Monolog automatically added the following information to the log entry:

*   Timestamp
*   Logger name
*   Log severity level

And the best part is that you didn’t need to write all this stuff yourself.

The only issue with this log entry is that the timestamp is not UTC. There are at least two ways to fix that:

1.  Specify UTC timezone when instantiating Logger.
2.  Specify UTC timezone for the entire PHP script.

In most cases, you’ll want your entire application to use UTC time, so I suggest adding the following method call at the top of your PHP script:

![](Images/Image848.png)

All date and time function calls following this line will use UTC timezone by default—very useful.

What Now?

In this chapter I’ve explained the basics of logging in PHP, which should be enough to get you started. Still, you might want to search for more advanced information to solidify your understanding.

If you’re going to use Monolog (as you probably should), invest some time into reading its [documentation](https://github.com/Seldaek/monolog/blob/master/doc/01-usage.md). This logging framework is extremely powerful and configurable, which allows you to support basically any logging requirements.

As your applications grow in size and as your log files become more complex, you might find it challenging to make sense of them even if you follow all best practices. That’s where [log aggregation tools](%20https://www.scalyr.com/blog/log-aggregation-help/) can be lifesavers. These tools help you aggregate, process, search, and visualize your logs, making it easier to find what you need in the vast ocean of log entries.

So go ahead and use application logging in your PHP projects! And remember: you should probably err on the side of logging more than you currently think you need.

This chapter was contributed by Vasiliy Zukanov. [Vasily](https://www.techyourchance.com/) worked in the semiconductor industry and then became a software engineer specializing in Android. After several years of 9-5 jobs, he decided to go into Android dev freelancing. Currently, he consults and creates Android video courses for developers.

## Chapter 5: Getting Started Quickly With Ruby Logging

Let’s continue to get started logging quickly, this time with Ruby.

We’ve talked about many languages so far. So, what about tipping the scale to the side of dynamically-typed interpreted languages? That’s exactly what we’re doing in this chapter by teaching you how to get up and running with logging using the Ruby programming language.

This chapter will cover:

*   How to implement a very rudimentary logger.
*   My take on the fundamentals of logging: why bother logging, what data to log, and where to log.
*   Finally, a very simple yet realistic example of proper logging, with help from the Ruby Logger class.

As in the previous chapters, we’ll create a very simple toy app in order to demonstrate how to log. And we’ll start with a very primitive—though functional—approach. We’ll then evolve it toward a more sophisticated and realistic solution.

![Ruby With Scalyr Colors](Images/Image855.png)

Some Words About Ruby and Rails

Before we jump into the logging part, I figured it’d be useful to set the scene. The Ruby language first appeared in 1995, created by Yukihiro Matsumoto, aka Matz. But it really gained popularity after 2005, largely due to the very successful Ruby On Rails web framework.

Even though many (or even most) developers get to know Ruby thanks to Rails, Ruby itself is a general-purpose language that can be used in a variety of situations, not just when building web applications. For that reason, this chapter won’t cover logging in Rails—that’s covered fully in the next chapter. But here, we’ll explore logging in the context of a simple command-line Ruby application.

With that out of the way, I think it’s time to get our hands dirty. Let’s start.

The Simplest Ruby Logging That Could Possibly Work

For our demo, I’m going to use [JetBrain](https://www.jetbrains.com/ruby/)[’](https://www.jetbrains.com/ruby/)[s RubyMine IDE](https://www.jetbrains.com/ruby/). Also, make sure you’ve got [Ruby](https://www.ruby-lang.org) installed.

Once you’re all set up and good to go, open RubyMine and click on Create New Project:

![http://blog.scalyr.com/wp-content/uploads/2018/02/Screenshot-2018-02-22-20.45.42.png](Images/Image864.png)

In the next screen, you’ll be asked to choose the project’s type:

![http://blog.scalyr.com/wp-content/uploads/2018/02/Screenshot-2018-02-22-20.52.59.png](Images/Image871.png)

As I already mentioned, we’re not creating a Rails app but rather a simple Ruby app. So choose Empty Project, which is the first option under Ruby on the left bar. The next step is to set the location/name for your project. After doing that, select the location of the Ruby SDK:

![http://blog.scalyr.com/wp-content/uploads/2018/03/Highlighted.png](Images/Image879.png)

Once you’re done, click on the Create button. We’ve successfully created a new Ruby project on RubyMine. Time to start coding.

First, let’s add a class. Go to File > New... > Ruby class:

![http://blog.scalyr.com/wp-content/uploads/2018/02/add-new-ruby-class.png](Images/Image886.png)

Name it Greeter and click on OK:

![http://blog.scalyr.com/wp-content/uploads/2018/02/Screenshot-2018-02-22-21.22.03.png](Images/Image894.png)

RubyMine will create the class and open it up for editing. Let’s add a Greet method that will receive a user’s name as input and print a friendly greeting:

![](Images/Image903.png)

Nice. Now let’s add a new file. Go to the File menu, then New..., and finally click on File. When the dialog box shows up, enter main.rb as the file name and click on OK:

![http://blog.scalyr.com/wp-content/uploads/2018/02/Screenshot-2018-02-22-21.50.45.png](Images/Image914.png)

This file will serve as the entry point for our little toy app. Insert the following code into it:

![](Images/Image927.png)

This code should be very easy to understand. On the first line, we load the greeter.rb file so we can access the Greeter class we’ve defined.

Following this, we print a request to the user to type their name. Then we read from stdin and assign the value to a new variable called name. On the next line, we create a new instance of the Greeter class and assign it to a variable of the same name. Finally, we call the Greet method on Greeter, passing the name we read from stdin as a parameter.

Time to run our app. Go to the Run menu and choose the first option, as is shown in the figure below:

![http://blog.scalyr.com/wp-content/uploads/2018/02/run-main.png](Images/Image934.png)

Alternatively, use the shortcut SHIFT+F10 on Windows and Linux or CTRL+R on Mac. If everything goes well, you should see something like this on the Run tool window:

![http://blog.scalyr.com/wp-content/uploads/2018/02/pleas-type.png](Images/Image942.png)

Type your name and press Enter, and you should see this:

![http://blog.scalyr.com/wp-content/uploads/2018/02/hi-carlos.png](Images/Image949.png)

Well, not exactly this, of course. Unless your name is also Carlos, in which case I congratulate your parents on their good taste in names.

Jokes aside, we’ve got our little toy app up and running! It successfully displays a greeting to the user. But now let’s say someone decided this isn’t enough. We also need to register the greetings somewhere, which can really come in handy in several ways. How to go about that? There’s no shortage of options, of course, but since this is meant to get you logging as quickly as possible, we don’t really want to get fancy.

Go back to the Greeter class and edit it so it looks like this:

![](Images/Image957.png)

Not a lot of changes. We’ve just added a new line of text that writes the greeting to a file. There’s also a new variable, message, that exists just to prevent duplication. So, run the app again, type your name, and the app should continue behaving the exact same way.

But now navigate to the project folder and you’ll see a new file there, accompanying the project’s source files:

![http://blog.scalyr.com/wp-content/uploads/2018/02/log-file.png](Images/Image964.png)

Open the file and you should see the greeting message. And that’s it. If this was your first attempt at logging with Ruby, congrats—you were successful!

What Is Application Logging?

As a starting point for discussion, let’s repeat the definition of application logging shared early on in this book.

Application logging involves recording information about your application’s runtime behavior to a more persistent medium.

This definition is, in my opinion, as good as it gets; it’s short, easy, and to the point. I don’t really feel the need to add more to it, which lets us get to a more interesting question: why log?

What’s the Motivation for Logging?

Why bother logging? Basically, we log for the same reasons we record any kind of information—so we can get back to it later. In the case of your application behavior, there are many ways in which this can come in handy.

It probably goes without saying, but software is a massively complicated thing. While you’re developing it, you hopefully employ techniques, tools, and principles to try to ensure its correctness.

But when the time for release comes and you set your application free into the world, you’re basically giving up control. Things can go wrong, and they often do. If you don’t have a proper strategy for monitoring your application’s behavior in production, you’re basically running blind. Without logging, you can’t know things like

*   If everything is OK.
*   What happened, exactly, when something goes wrong. You also won’t know when or how it happened.
*   Which features people use the most and which ones they don’t they use at all.
*   Which area of the application is responsible for most crashes.

As we’ve seen, application logging is essential not only to help you understand and fix errors but also to help you gather data so you understand the needs of your users.

Evolving Our Approach: What Should We Capture? And Where Should We Store It?

Being able to put on your detective hat by investigating your application’s log files can bring several benefits, as we’ve just seen. Our toy log, in its current form, isn’t quite there yet. It just writes the greeting to a file, after all.

Now it’s up to us to evolve our approach so our log files can reach their maximum usefulness. But how to proceed with that?

First, we have to understand the nature of a log entry. This is going to sound familiar if you’ve read previous chapters, but I’m going to recap here for completeness’ sake. You should think of a log entry as an event—something that’s of interest to your app that happened at some time. So the value of your entry is all about what you capture regarding the event.

Here are some examples of things that might make sense for you to capture:

*   A timestamp. When did the event take place? (You’ll probably want to follow best practices of dealing with dates and times, such as using the ISO-8601 format, for instance.)
*   Context. You need to make it as easy as possible for the future reader to understand what this entry is about.
*   Log levels. Log entries can wildly vary in their purpose. You have to have some way of distinguishing an entry whose sole purpose is to debug some execution path from another that records some event of interest to the business (customer placed an order) or from even another that writes down the details of a fatal crash for posterior investigation. Log levels are your friends here.

After deciding what type of events you want to log (Each method call? Just business events? Only fatal errors?) and what data about them you want to capture (timestamp, description, log level, logged user, or time of session?), the next step is deciding where you want to log to.

See, even though the demo app logs to a file, there’s nothing preventing you from logging to a variety of targets, such as the database, the console, or even an online service.

Enter the Logging Framework

Think about our toy app. It was designed to give you as quick a start on the Ruby logging world as humanly possible. But now you’re more knowledgeable about logging and can analyze our demo in a more critical way.

By doing that, we can come up with several questions that need answering, such as:

*   How can we prevent the log file from getting overwritten every time?
*   Since we’re talking about files, don’t we have to worry about file permissions, concurrent access, and other concerns that arise when doing IO?
*   Will we have to write a lot of code to add the timestamp, log levels, and other important information we want to capture with each event?

It didn’t take a lot of thought to conclude that our logging strategy lacks a lot of important things. Coming up with a proper logging strategy is no small feat, as you can see.

The good news is this: you don’t have to answer all of those issues on your own. People have already solved those kinds of problems before, and guess what? Many of them decided to make their solutions available to the world in the form of a logging framework.

A logging framework is a package meant to provide “free” logging for you. With a little bit of configuration, you can make one-line calls that, despite being as simple as the one in our toy example, can do a lot more. They’ll generate log entries with nice, consistent formatting, and all of the issues we discussed above will be pretty much taken care of.

As with Python, Ruby has logging built in, which can really make things easier. Let’s explore it a little bit.

Getting Started With the Ruby Logger

First of all, let’s change our existing code to make use of the Logger class. Go to the Greeter file and add the following line right at the start of the file:

![](Images/Image972.png)

Now, remove the line where we write the greeting to a file, and add the following lines:

![](Images/Image979.png)

Then, the complete Greet method should look like this:

![](Images/Image987.png)

The code should be easy enough to understand. We create a new instance of the Logger class, giving it a new file by parameter. In the next line, we log the greeting message at the Info level.

Now, let’s run the app again and see what happens.

Checking the Results

Next, navigate back to the project folder, and you’ll notice there’s a new file hanging out there called proper.log. Open it using your favorite text editor, and you should get something like the following:

![](Images/Image996.png)

Let’s break this line down:

First, we have the severity ID, I. The I stands for Info.

What follows—2018-02-23T14:41:59.538985—is the event timestamp, in ISO-8601 format.

Then we have our app’s PID, #11520, and the label for the severity, Info.

And finally, we have our message: Hi Carlos!

The Power of a Logging Framework

Just by adding three lines of code (the require line and the two new lines inside the method), we were able to implement a simple yet realistic example of a logger. Of course, a logger for a “real life” application would require a lot more thought—and work. But I do hope that after this quick example, you’re now both more knowledgeable about the principles that govern logging and also eager to explore and learn more.

What’s Next?

There’s obviously more to logging in Ruby, but I think we’ve delivered on our promise: you’re up and running with Ruby logging as quickly as possible. Your challenge from here on out is to build upon this knowledge. So why not start playing with the demo logger you now have?

There’s no shortage of things for you to try. Here are some suggestions:

*   Experiment with the different severity levels.
*   Learn about formatting options for your logger.
*   Research logging to targets other than files, such as a database.
*   Once you’re confident enough, try logging options other than the built-in class. Use GitHub and Ruby Gems to learn about those options, and try them!

Good luck on your logging journey with Ruby!

This chapter was contributed by Carlos Schults. [Carlos](http://carlosschults.net/) is a software developer with experience in both desktop and web development, now trying his hand at mobile. Carlos has a passion for writing clean and concise code, and he’s also very interested in practices that help you improve your app’s health.

## Chapter 6: Getting Started Quickly With Rails Logging

Let’s continue our our journey getting starting with loggers for different languages and platforms. In the last chapter, we covered logging with Ruby; now it’s time to take a look at the platform most often associated with that language: Rails.

We’ll start with a simple application, with scaffolding for CRUD operations on a single record. We’ll look at Rails’ default logging configuration and how to use logging in an application. Then we’ll look at how logging can be improved and why you might want to improve it.

This tutorial uses [Ruby v2.5.1](https://www.ruby-lang.org/en/downloads/) and [Rails 5.2.0](https://weblog.rubyonrails.org/2018/4/9/Rails-5-2-0-final/). You’ll need to have them installed to follow along. These instructions will use the command line to create and configure the application and will not rely on a specific IDE or editor. We’ll let Rails use SQLite for the backend database.

![](Images/Image1007.png)

Create a Rails Application

We’ll start off by creating a Rails application. Run this command first:

![](Images/Image1019.png)

After few screens of output, Rails has created the application.

Next, we’ll let Rails create a model and a controller for us so we have something interesting to log. Move into the logging_app directory and run this:

![](Images/Image1026.png)

Rails creates the scaffolding for a user record with a name and an email address.

Finally, have Rails migrate the application into SQLite.

![](Images/Image1034.png)

And we have an application! Let’s run it and confirm that’s all set up.

![](Images/Image1042.png)

Point a browser at http://localhost:3000/users, and we see our main page for managing users:

![](Images/Image1050.png)

We’re ready to get started with logging!

Rails Logger

Rails creates an instance of ActiveSupport::Logger as part of initialization and uses it for logging to standard output.

Take a look at the application output when we open the /users page:

![](Images/Image1057.png)

Logger produces this output. In addition to standard output, we can find the same input in the default log file. Let’s stop the server and take a look at the last ten lines of the log file:

![](Images/Image1064.png)

The default name of the log file is the environment name. In development, it’s named development.log; in production, it’s named production.log; and so on.

The default logger is available to application code in a globally accessible instance named logger. Let’s add an extra debug message when the application displays a user.

First, add a log message to app/user_controller.rb in the show method.

![](Images/Image1071.png)

Then start the application. Go to the /users and add a user named John Doe with an email address of [john@doe.com](mailto:john@doe.com).

Your log should have an entry similar to this:

![](Images/Image1080.png)

Rails has a reputation for making life easy for developers, and logging is an example of why it got that reputation. Let’s look at how we can customize the Rails logger.

What Is Application Logging?

Before we delve into how to improve the Rails logger, let’s go back to first principles. What are we trying to do? What is application logging? If you’ve read any of our other chapters, you’re already quite familiar with our definition:

Application logging involves recording information about your application’s runtime behavior to a more persistent medium.

So, in Rails, we’ve already seen that we have a way to record information about our application to a file and to standard output, which our DevOps team can redirect to where they wish with standard output. But we can do more.

What Is Application Logging For?

Why do we write logs? It seems like an obvious question, but it’s worth considering.

We write logs so we have a record of what’s happening.

We’ve released our code to production, and we need to get to work on something else. But at some point, something will go wrong, and we’ll be asked to diagnose the problem. Logs are often the only thing we have.

We may also be asked for information about what’s happening in production when nothing is wrong. How many pages are loaded per day? Per hour? Per minute? Where are users coming from? What features are used most often, and what features are ignored?

While some of this information is available from web analytics, logs can drill down to a higher level of detail.

Application logging is a critical tool for helping us locate and fix errors and for collecting information that can help us improve our applications.

What Information Should We Log?

The messages we’ve seen from Rails are messages about what’s happening in the application. They lack context, though. Let’s define what we want from a log message and then configure the system to give us that.

A log entry represents an event. Something happened to the application, and the developer thought it was interesting enough to save for later review.

The most obvious thing we might want to know about an event is when it happened. None of the log entries we’ve seen so far have a timestamp on them. We’ll need to add that.

It’s also useful to have some context. We added this log message to our code earlier.

![](Images/Image1089.png)

Rails logged this:

![](Images/Image1100.png)

What happened to Debug? We called the logger at Debug level, but that information wasn’t passed on. All of the log entries appear as equivalent with the default configuration, reducing their usefulness.

Let’s get started changing the Rails logger’s configuration.

Configuring Logs

Like most loggers, ActiveSupport::Logger supports different levels. Those levels are Debug, Info, Warn, Error, and Fatal.

We can log a message at any one of these levels by calling the associated method:

![](Images/Image1112.png)

This gives us a way to categorize messages, and we’ll add the level to the messages below. But let’s look at filtering messages first.

Debug messages are useful for, well, debugging. Their very name implies they’re for development or for isolating a problem. We don’t typically want to see them in production where they can reduce the signal-to-noise ratio in log files and potentially compromise performance.

We can filter which messages make it to the console or log file in Rails’ configuration.

If we add this to our configuration, only messages logged at Error or Fatal will be logged.

![](Images/Image1119.png)

Rails has a hierarchical configurations scheme. We can add logging configuration in config/application.rb or config/environment/{environment_name}.rb. The environment-specific file takes precedence.

So when we add this to config/application.rb...

![](Images/Image1119.png)

and this to config/environment/development.rb...

![](Images/Image1134.png)

...we still see Debug messages in development but only Error and Fatal in production.

We can change the name and location of log files by supplying Rail with logger instance initialized with our preferences.

![](Images/Image1142.png)

This also means we can create new subclasses of Logger if we want to change logging behavior.

But let’s change the behavior we’re most interest in right now: log message formatting.

Log Message Format

Rails’ configuration has a mechanism for supplying Rails with a log message formatter instance. The first step is creating that message formatter class.

![](Images/Image1149.png)

We extended the ActiveSupport::Logger::SimpleFormatter and overloaded its call method. We need an instance of SimpleFormatter for the configuration.

Logger passes call four parameters. They are

*   The log level (as severity).
*   The time of the message.
*   The program name.
*   The message.

We formatted the severity into a fixed width field and the time as a human-readable string. Then we put the parts together into a familiar message format.

There are a variety of ways we can add this class to our code. The use of the libs directory can be controversial with Rails, but we’ll use it for the sake of getting a formatter installed.

First, create the formatter class in logging_app/libs as message_formatter.rb.

Next, since Rails 5.x does not load classes from lib automatically, add these lines to config/application.rb in the LoggingApp class declaration:

![](Images/Image1156.png)

Finally, add the formatter to config/environment/development.rb:

![](Images/Image1164.png)

When we run the server and open a user entry, we see log messages with our custom format.

![](Images/Image1173.png)

We’ve added the logging severity and the timestamp to the message. The program name isn’t always used, but it will appear if specified in a call.

You’re Ready to Go!

In this chapter, we looked at the Rails logger and how to call it from our application code. Then we looked at how to customize the configuration and extend the log messages to make them more useful.

There’s a great deal more you can do with logging, so keep learning!

This chapter was contributed by Eric Goebelbecker. [Eric](http://ericgoebelbecker.com/) has worked in the financial markets in New York City for 25 years, developing infrastructure for market data and financial information exchange (FIX) protocol networks. He loves to talk about what makes teams effective (or not so effective!)

## Chapter 7: Getting Started Quickly With Swift Logging

In this chapter, it’s time to talk about Apple’s Swift language. Swift has slowly been gaining popularity, especially since its open-source release.

I’ll start with a quick example of manual logging in Swift. Then I’ll give you my own take on a subject frequently covered in this book: details of how and why logging matters. Finally, I’ll move on to using Apple’s Unified Logger in a Swift application and let you know how it can improve your ability to monitor applications and track down issues.

The code example will be for MacOS, but you can easily adapt it for any Apple platform.

Let’s get to work!

![](Images/Image1182.png)

The Simplest Swift Logging That Could Possibly Work

Let’s start by creating a new project in Xcode. If you don’t already have it installed, go to the App Store and install it from there.

Next, start Xcode and select Create a new Xcode Project from the first dialog window.

![getting started with swift logging](Images/Image1193.png)

We’re going to keep the code as simple as we can in this tutorial, so select MacOS and Command Line Tool and then click Next. You’ll see this.

![](Images/Image1206.png)

Now, you can give your project a name. These values are not critical, but make sure that Swift is set as the project language.

![](Images/Image1213.png)

Finally, we have a project.

![](Images/Image1221.png)

Select main.swift in the IDE, and you can see the code Xcode added for us.

![](Images/Image1228.png)

Rather than print to the console, we want to save logging information to a text file.

Swift works differently from many of the other languages we’ve worked with before. There are several ways to write a string to a file. But since the purpose here is to demonstrate the easiest way to, here it is:

![](Images/Image1236.png)

Set the file name to something that will allow you to quickly locate it. Keep in mind that the working directory for Xcode projects is buried somewhere deep in your Library directory, so you may want to set the log file location to your home directory.

When you’ve picked a place for the file, build and run the project. Then find the file and open it with any editor you wish. You’ll see your log message.

We started by declaring where our log file will be. As you’ll see below, this is important. It’s something all components have to know—unless there’s a framework that manages log locations for us.

Next, we converted that file name to a URL. All Swift strings can write themselves to a URL, so we’re taking advantage of that.

Finally, we created a string and wrote it to the URL.

While this would work for simple logging, it wouldn’t necessarily work well. What’s the cost of having every log message open a URL and write itself to it? I doubt it scales well for hundreds or thousands of log messages. What would happen when more than one message wanted to log itself at the same time? Is this mechanism threadsafe? Would it block the entire program?

Let’s look at a better way.

What Is Application Logging?

First, let’s take a look at what logging is.

You’ve probably dealt with logging before and have an idea of what it means, but it’s still worth defining it so we can evaluate a logging framework in terms of what we need. You already know that we like to define application logging like this:

Application logging involves recording information about your application’s runtime behavior to a more persistent medium.

But let me break that down.

Logging means recording runtime behavior. We’re documenting events about an application. The time factor implies in chronological order.

Second, we store logs in a more persistent medium. Application events occur quickly, and we want to be able to go back and review them. Maybe we’re trying to track down an error, or perhaps we have to maintain an audit trail. A persistent medium can be a disk, a relational database, or a search engine.

So, that’s what logging is. How can you do it more effectively in Swift? And why would you want to? These are important questions. Let’s get back to work.

Apple’s Unified Logging System

With MacOS Sierra and iOS 10, Apple introduced the new unified logging system. While they haven’t deprecated the legacy logging system yet, this new logger is the direction they’re going.

The unified logger has built-in security and performance features that make it desirable. But it does have an idiosyncrasy that many developers dislike: messages are stored in memory and a proprietary data store. There are no clear-text log files, and messages can only be read with Console.app or the command line log tool.

Let’s add the unified logger to our application and see how it works.

We’ll start by removing the code for manipulating files and just replacing it with os_log(), the unified logger. We need to import the OS package and add the call to os_log.

![](Images/Image1243.png)

Hmm. This program doesn’t build.

![getting started with swift logging](Images/Image1250.png)We can only pass static strings to os_log. So we’ll change how our string is defined.

![](Images/Image1258.png)

Build and run this version, and everything looks fine.

But where’s the log message?

Run the Console application. You can find it in Applications/Utilities or by opening Spotlight and searching for it.

Search for the text Process: Swift in the search bar as shown below.![](Images/Image1267.png)
There’s our log message.

The unified logger takes care of the log file location by storing all logs in the same system and indexing them. We don’t have to worry about where they belong, how to open them, and when to close them.

So what do we need to concern ourselves with when it comes to Swift logging?

Why Log?

Someday you’ll write that perfect application. You know which—the one that has no bugs, reacts correctly to unexpected events, and anticipates your customers’ every need. But until then, you’ll need a way to keep an eye on things. Here in the real world, even well-constructed applications have bugs and other shortcomings, and we need to monitor what’s going on inside them.

We can find and fix problems quickly when we’re developing code. We have the debugger, we can add print statements, and yes, we even use logs as we’re coding. We’re watching our application in captivity, in a sterile environment where we have control.

But our application is going to leave the tender embrace of our development environment eventually. It will be used in ways we didn’t anticipate, and it will encounter conditions we never imagined. And then, when it fails, we’ll need a way to figure out what happened.

This is where logs come in.

Isolating bugs isn’t the only use for logs, either. They’re useful for watching an application that works and finding opportunities for improvement. We can use them to detect patterns of behavior that can be improved upon. We might be able to discover a resource that should be cached in memory instead of a file or a feature that’s never used.

And of course, the usefulness of logs doesn’t stop there. Sometimes we need an extra copy of transactional data, such as credit card charges or other financial transactions.

We need visibility into our application’s runtime behavior, and we get it by logging.

How Should You Log?

We already took a quick look at Apple’s unified logging system. It fulfills the requirement for persistently storing logs in a central location. We can find these logs with a text search via the console application or a command line tool.

But it would be nice if the logs were easier to find inside the system and had a bit more context.

This leads to a more general question: what information should be logged?

Most logging systems include at least the following information in each log entry:

*   Timestamp: when the event described in the log entry happened. The unified logger takes care of this for us.
*   Event context: useful information about the event. “It worked” or “it’s broken” might be useful or entertaining during a debugging session. “Failed to connect to database at 192.9.168.3:5000” is more useful in production.
*   Severity level: logs tend to have a level that puts them in context compared to other entries. The unified logger defines Default, Info, Debug, Error, and Fault. We’ll take a closer look at logging levels below.

So the unified logger takes care of two out of three essential aspects of logging for us. But it’s up to us to manage the content of our messages effectively.

Customizing the Unified Logging System

Let’s take some time to talk about customization.

Adding a Log Level

First, we’ll cover how to make our use of the unified logger more effective. We can already log information to persistent storage with a single line of code. But what more can we do?

First, let’s add some additional context to our logs with log levels. Change the call to os_log by adding a few more arguments and the log message text.

![](Images/Image1277.png)

Build, run, and take a look at the console application.

![](Images/Image1289.png)

The logger tagged the message as an Error for us because we passed .error for the type: argument. We can also pass in .info, .debug, or .fatal. If we omit the type: argument, the message is logged as default.

To do this, we had to pass the call to os_log the log message, an instance of a logger, along with the log message type.

Let’s take a closer look at the notion of a log instance before continuing to customize our messages.

Log Instances

We’d been calling os_log with a single call to log messages up until the previous exercise. This is a convenience function. When we called it with only a message, it used a default logger instance. When we called it with an instance and a log type, we were calling a different function that manipulated the instance we passed in.

Let’s take a closer look at our log message in the console application.

![](Images/Image1302.png)

Because we used the default logger instance, the message doesn’t have subsystem or category information.

If we want to populate these fields, we need our own logger instance—one that’s initialized with information about our application. Let’s create one.

The first step is to create a plist with logging configuration information.

In Xcode, create a new file. Select the property list type.

![swift logging new plist](Images/Image1309.png)

Name it com.scalyr.SwiftLogger and save the file.

The file will open in the property editor. But life’s too short for that. Right-click on the file name in the project navigator, select open as, and then select source code.

![https://www.hitsubscribe.com/wp-content/uploads/2018/09/open-as-source-code.png](Images/Image1317.png)

Enter this text:

![](Images/Image1324.png)

This property list defines a logger system that defines how Info-level messages are handled. We’ll go over this in more detail after this example.

Copy this file over to the /Library area of your system.

You’ll need to be in the working directory of your project and have root access.

![](Images/Image1332.png)

This property list defines a logging subsystem named com.scalyr.SwiftLogger that we can refer to when we create a new instance.

So, let’s update the code.

![](Images/Image1339.png)

We’re creating a logger instance with OSLog.init. We pass it the name of our subsystem and then a logging category. A category is an arbitrary name for group log messages.

Next, we pass the logger instance to os_log.

Run the code, and you’ll find a log message set to the Default level in the console app. Click on it to see the details.

![](Images/Image1346.png)

Let’s send this message as a Fault.

![](Images/Image1354.png)

Run this version, and check the console application.

![swift logging](Images/Image1364.png)

We see the details and the Fault log level.

Log Message Storage

In the plist, you can see this section toward the middle:

![](Images/Image1373.png)

This defines the storage options for the Info log level. It tells the system to inherit the default. We only needed to establish a log system to get past the step of creating a named logger.

But it’s useful to understand the default rules for storing logs.

*   Default log messages are stored in memory buffers. The system will compress and move them to the data store as memory buffers fill.
*   Info log messages are stored in memory buffers. The system won’t move them to the data store. It purges them as memory buffers fill.
*   Debug messages are only captured in memory when Debug logging is enabled through a configuration change. The system will never write them to disk.
*   Unified logging always saves Error and Fatal messages to the data store.

Log Contents

We can set up a log with a subsystem and category, and we can control the level messages we send with it. That leaves log contents.

Even though we’re limited to passing static strings in the log message, we can still use C-style formatting with those strings.

So we can use log strings as a formatter:

![](Images/Image1384.png)

Run this from Xcode, and you’ll see the log message.

We can log scalar values too:

![](Images/Image1396.png)

But what we see from inside Xcode is not what happens in production.

Let’s change the code back to printing a string in the log message:

![](Images/Image1403.png)

Run this in Xcode, and you’ll see “The answer is a secret” in the console application.

Now, let’s build the application and run it from the command line.

Open a shell and move to the project directory. Run xcodebuild and then run the application.

![](Images/Image1412.png)

Check the log message in console.

![](Images/Image1419.png)

The unified logger redacted the string. This is the default behavior for string messages. It isn’t for scalar values.

If you do not want a string to be redacted use the {public} notation.

![](Images/Image1427.png)

If you want a scalar value redacted, use the {private} notation.

![](Images/Image1434.png)

This is a built-in security feature that helps protect critical information. As tempting as it might be to mark everything public, resist the urge.

What Now?

We’ve covered the hows and the whys of logging with Swift on an Apple platform with the unified logger. It’s a comprehensive system that makes logging easy for an application developer.

Even though we’ve talked about a lot of logging approaches in this book, there’s still more to know about logging. If you want to branch out from what you’ve learned in this chapter, you can start with the the [Apple unified logger documentation](https://developer.apple.com/documentation/os/logging#2878594?changes=_1) on the Apple Developer website. But now you know the fundamentals, and that means you can get started with logging in your Swift applications today!

This chapter was contributed by Eric Goebelbecker. [Eric](http://ericgoebelbecker.com/) has worked in the financial markets in New York City for 25 years, developing infrastructure for market data and financial information exchange (FIX) protocol networks. He loves to talk about what makes teams effective (or not so effective!).

## Chapter 8: Getting Started Quickly With Scala Logging

Now that we’ve talked about logging with a couple different languages and platforms, it’s time to show how you can get started quickly with Scala logging.

First, I’ll show you with a quick example of manual logging with Scala. I’ll use IntelliJ IDEA to create and run a Scala project, using sbt to build the code. That way, you can use the application to get started on any platform that supports Scala and Java.

Next, I’ll discuss details of how and why logging matters. You’ve already heard some other folks’ takes on this, but I’m sharing mine here.

And finally, I’ll move on to using the Scala logging wrapper in an application, and I’ll tell you about how it can improve your ability to monitor your applications and issues.

Let’s get started!

![](Images/Image1441.png)

A Simple Scala Logging Implementation

Let’s kick things off by launching Scala project. Then, we’ll show the simplest Scala logging that could possibly work.

Creating a Scala Project

We’ll use [IntelliJ IDEA](https://www.jetbrains.com/idea/download/) for this tutorial, which has a free community edition that you can download.

First, make sure you have the Scala plugin installed and activated. Once you have that set up, start IntelliJ. Before you open any projects, select Preferences from the start screen.

![scala logging start plugins](Images/Image1450.png)

Select Plugins from the configure menu.

This will open the plugins management window.

![jetbrains plugins scala logging](Images/Image1459.png)

Now, click Install JetBrains plugin... on the bottom left-hand side of the window. This will bring up a window listing the official JetBrains-supported plugins for IDEA.

![scala logging plugin](Images/Image1468.png)

Now, select the Languages category at the top and scroll down until you find the Scala option. Install the plugin if it’s not already there. You’ll be prompted to restart the IDE after the plugin is downloaded and restarted.

You’re ready to write Scala applications now!

![scala logging new project](Images/Image1479.png)

In the next window, select Scala and sbt as shown, and then click Next.

![scala logging tutorial](Images/Image1491.png)

Now give the project a name at the top. Verify that the latest JDK you have available is selected, as well as the Scala SDK and sbt version.

![scala logging last project window](Images/Image1498.png)

If Scala is not installed, no SDK will be available. Click the Create button and download the latest available version (2.12.7, as of this writing). Now, click Finish, and IDEA will create your project.

We have one more step to finish before we can start coding. Adding the Scala framework to the project will make creating Scala classes and objects easier. After the project is finished loading, right-click on the project name in the browser window.

![scala logging Add Framework support](Images/Image1506.png)

Select Add Framework Support... as shown. This brings up the Add Frameworks window. Scroll down in the left-hand pane until you find Scala. Check the box and then click OK.

![Add scala framework](Images/Image1513.png)

That’s it. Let’s write some code!

Simple Scala Logging

Let’s start with a new class. Open up the src folder in the project browser and navigate to the Scala folder.

![New Scala Class](Images/Image1521.png)

Right-click and select Scala Class.

![](Images/Image1528.png)

Change the selector from class to object, and give your new object a name. Then, click OK.

IDEA will create a file and add skeleton code to it.

![](Images/Image1535.png)

Now, modify the new class to extend the App class. That way, we can run it. Then add a single line of code:

![](Images/Image1543.png)

Let’s now have the IDE run the class. Right-click on the object name in the project browser.

![scala logging run first time](Images/Image1552.png)

Select Run in the menu as shown.

A run pane will open in the IDE, and you’ll see the program output.

![](Images/Image1561.png)

That was easy! But now the requirements for your application have changed. You need to not only log to the console but also to a file. Your operations personnel want to be able to go back and look at past log messages.

There are several options for writing to a text file in Scala, but let’s use the simplest option. Edit the code in the object, so it looks like this:

![](Images/Image1572.png)

Now, rerun the program. The output is the same, but a new file called output.log appears in the project browser.

![scala logging output.log](Images/Image1584.png)

Double-click on output.log and the IDE will display the contents.

![](Images/Image1591.png)

We have a log file.

But there are some issues with this approach. For example, PrintWriter uses the current platform’s default encoding. So log files created on a Mac will not look correct when examined on Windows and vice versa.

Let’s discuss some logging basics, and then we’ll see a better method for Scala logging.

What Is Application Logging?

What is logging? Why do we need it? When do we need it?

At this point in the book, you probably have a good idea of what logging is. And you may have already dealt with it in an application that you’ve created or maintained. But let’s revisit our definition so we can evaluate a logging framework in terms of what we need. Way back at the start of this book, we defined application logging this way:

Application logging involves recording information about your application’s runtime behavior to a more persistent medium.

Let’s take a closer look at this definition.

When we log, we record runtime behavior. We document the events that occur inside an application. While it’s not explicit in this definition, we can also assume that the events are recorded in chronological order.

Second, we store logs in a more persistent medium, like a disk, a relational database, or a search engine. Sometimes application events occur more quickly than we can follow in real time. We want to be able to review them later. Maybe we’re trying to track down an error, or perhaps we have to maintain an audit trail.

The following list contains some examples of things that you’ll probably want to capture in a log entry:

*   A timestamp. Exactly when did the event take place? (You’ll want to record times in UTC, using a standard format such as ISO-8601, in case you’re logging to a file.)
*   A context that makes it clear to a reader what the entry is about. Just recording “Hello, user!” might be difficult to decipher weeks or months later. A better message might say, “User greeting of ‘Hello, user!’”
*   Log levels, such as Error, Warning, or Info. These provide context.

Enter the Logging Framework

So, that’s what logging is. Our simple solution above only scratches the surface of what we need for effective logging. It also relies on the developer to open the file, close it, manage the log entry format, and avoid overwriting old log entries when the application is restarted. Also, the solution wouldn’t scale across multiple objects. We would have to write a library or framework for that.

I could continue, but I’m sure you understand. Creating a sound logging approach requires a lot of work and a lot of thought. But these problems have already been solved for Java and, as a result, for Scala.

Scala-logging is a library that wraps the [Simple Logging Facade for Java (SLF4J)](https://www.slf4j.org) in a Scala-friendly library. SLF4J supports many different logging frameworks, including both Log4j, which we covered earlier in the book; and [Logback](https://logback.qos.ch), a similar framework. We’re going to use Logback for this tutorial because the set will be easier.

Let’s get back to the tutorial.

Using a Framework for Scala Logging

First, we need to add SLF4J to our application dependencies. Open build.sbt in the code editor.

![scala logging build.sbt](Images/Image1599.png)

Add the dependency for scala-logging so the file contents look like this:

![](Images/Image1606.png)

Next, we need to download jar files for logback and add them to the runtime classpath.

First, create a new directory in your project folder named libs.

Then, add it to the project’s classpath. Right-click on the project name and select Open Module Settings.

![module settings](Images/Image1614.png)

Select the Dependencies tab, and then click the plus sign to add a directory.

![](Images/Image1621.png)

When you select Add jars or directories, IDEA will let you select a folder. Below is the display for IDEA on a Mac.

![](Images/Image1628.png)

Select the folder, and then click OK.

We’ve added a folder to the classpath. Now we need to add the jars. Download the latest Logback jars from its website, specifically at [https://logback.qos.ch/download.html](https://logback.qos.ch/download.html). Open the archive and copy logback-classic-XXX.jar and logback-core-XXX.jar to the libs directory, where XXX is the latest version.

We’re finally ready to write some code.

Modify your tutorial class to look like this.

![](Images/Image1636.png)

We’re importing the logger class and then creating an instance named logger. Then, we print a log message at the error logging facility.

Rerun the application.

![](Images/Image1645.png)

SLF4J passed our log messages to Logback. Then, Logback printed them to the console, which is the default behavior when no configuration is specified. You can see that each log message has a timestamp, a level that corresponds to the function we called with each message, and the name of the thread that logged. We’ve satisfied our list of requirements for log messages, and we wrote less code than in the simple example above.

Scala Logging: Mission Accomplished

We did it—we logged in Scala! But this is only the beginning. Java’s existing logging frameworks support Scala, so getting started is the easy part.

Your next mission? Spend some time developing a strategy for logging. You’ll need it.

This chapter was contributed by Eric Goebelbecker. [Eric](http://ericgoebelbecker.com/) has worked in the financial markets in New York City for 25 years, developing infrastructure for market data and financial information exchange (FIX) protocol networks. He loves to talk about what makes teams effective (or not so effective!).

## Chapter 9: Getting Started Quickly With Django Logging

Django is one of the most popular Python web application frameworks, and for good reason. Since it employs the built-in Python logging facility, logging in Django is a snap.

Still, there are a few specific Django configuration options to keep in mind. In this chapter, we’ll

*   Create a Python virtual environment.
*   Set up a small Django project to work with.
*   Write a basic logging example.
*   Configure the Django logger.
*   Explore the Django logging extensions.

If you want to skip writing code, you can find all of my code from this chapter over on GitHub ([https://github.com/caseydunham/django-logging](https://github.com/caseydunham/django-logging)).

Also, note that this chapter won’t go into details on the specifics of Python logging. If you want a primer on those, check out ”Get Started Quickly With Python Logging” from our first logging book, [The Scalyr Guide to Getting Started Logging as Quickly as Possible](https://www.amazon.com/Getting-Started-Logging-Quickly-Possible-ebook/dp/B07H8SNT2Q).

Now: ready, set, log!

![](Images/Image1654.png)

Create a Python Virtual Environment

Python virtual environments are a great way to keep your system-wide Python environment clean. They isolate your project dependencies and keep the Python system installation free of cruft and dependency issues.

Since we’ll be using Python 3 in this chapter, before creating the Python virtual environment, you should double-check to make sure you’re running a recent version:

![](Images/Image1665.png)

Next, create a directory to keep our project in:

![](Images/Image1677.png)

All right. Before we move onto the next section, let’s create and activate our new virtual environment:

![](Images/Image1684.png)

Now everything is good to go to install Django.

Install Django

Within the virtual environment, installing Django is as easy as one, two, pip install Django:

![](Images/Image1692.png)

Quickly verify the installation by checking the version of Django:

![](Images/Image1699.png)

Great! Now let’s move on to creating a simple hello world application.

Create a Simple Application

For this chapter, this project isn’t going to be anything fancy—just a simple web page handler that will be the logging test bed. Before creating our module, we’ll need a name, which will be app. (I know, that’s not very clever, but it’ll do for our purposes.)

The django-admin command will create an initial application skeleton for us:

![](Images/Image1707.png)

There won’t be any output, but in your directory you should see a new app folder:

![](Images/Image1714.png)

As a final step to make sure everything’s up and running, fire up the built-in Django web server:

![](Images/Image1721.png)

See that scary message about the 15 unapplied migrations? Just ignore that. Open up a browser and point it at http://localhost:8000. You should see the default Django web page:

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/Django__the_Web_framework_for_perfectionists_with_deadlines_-1024x594.png](Images/Image1729.png)

Add a New Django Module

Now that we’ve got all our scaffolding in place, let’s create a module named hello. Once again, Django provides another handy script, [manage.py](https://docs.djangoproject.com/en/2.1/ref/django-admin/), that takes care of a bit of scaffolding:

![](Images/Image1738.png)

This command will create a new folder named hello,  along with a few additional Python files. Replace the contents of hello/views.py with the following:

![](Images/Image1747.png)

This creates our initial view, but we still need to let Django know about it. Create a new file in hello/urls.py and add the following to it:

![](Images/Image1761.png)

This hooks up our view to the base URL path (the empty string). Now all we need to do is hook this into the app/urls.py file so Django knows how to route everything.

Open app/urls.py and replace its contents with the following:

![](Images/Image1774.png)

Next, start the web server, as we did before:

![](Images/Image1781.png)

Instead of the default Django welcome screen, we’ll see our lackluster but useful view:

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/hello_logging-1024x360.png](Images/Image1789.png)

Whew. Thanks for sticking with it. Now that we have all that out of the way, let’s look at how to utilize logging within the Django application.

First Steps With Logging

The simplest possible logging we can do is to just import the Python logging module and start logging.

Begin by updating the app/views.py file with the following code:

![](Images/Image1796.png)

Here, we’re importing the logging module and then using the getLogger method to get a logging instance we can use. In the Index method, we emit our log message using the logger.error method. Restart the web server and refresh the page to see our message in the console window:

![](Images/Image1804.png)

Configure the Logger

By default, Django uses the dictConfig format for configuring logging handlers, filters, and formatting. These settings are set through the LOGGING dictionary, which is merged with the Django default logging configuration. Let’s look at a simple logging configuration and then walk through it.

![](Images/Image1811.png)

OK, that’s a lot. Let’s break it down.

version:  The dictConfig schema doesn’t require a version, but setting it ensures backward compatibility. Currently, the only valid value here is 1.

disable_existing_loggers:  This setting disables existing loggers. The default value is False, but it doesn’t hurt to be explicit. When setting this to True, define additional loggers. Otherwise, messages may be lost.

formatters: This section defines what our log statements will look like. Let’s take a look at the console log format:

![](Images/Image1818.png)

Here’s what’s going on:

*   %(name): this is the package name that emits the log message.
*   %(levelname): the log level of the message (Error, Warning, Info, etc.).
*   %(message): this is the actual log message.

The -12s and the -8s control spacing between the different format specifications. An example message in this format will look like the following:

![](Images/Image1826.png)

You’ll notice the file formatter includes an additional specifier, the %(asctime). This adds a timestamp to each message sent through the file handler. As an example, the message from our defined debug.log will resemble this:

![](Images/Image1835.png)

handlers: This section defines how to handle log messages. We can send messages to the console, files, or even sockets! All the default handlers are in the Python docs [on their website](https://docs.python.org/3/library/logging.handlers.html). This configuration defines separate handlers: one for console messages and another for messages sent to the file. In addition, for the file handler, we specify the handler class, the file name to log to, and the log level. This handler also specifies which formatter to use.

loggers: This last section is where we tie it all together and define our loggers, including how to handle the root logger (represented by the empty string) messages. We also set the logging level to Debug and define two handlers—one to the console and one to the file.

Let’s update the configuration now and take it for a spin.

Update and Test the New Configuration

Update the app/views.py to include the above logging configuration. It should look like this:

![](Images/Image1844.png)

Running that as before and refreshing the browser, the console log message now includes the additional information from our format string:

![](Images/Image1855.png)

The log file will contain the same message and format, but with the addition of the timestamp:

![](Images/Image1867.png)

This is enough to start incorporating logging in any Django project. However, we have one more topic to cover: the logging extensions that Django provides.

Tour the Django Logging Extensions

In a web server environment, we often have routine information we need to log. Django provides a few logging extensions to cover these use cases.

django: This is a catch-all logger for messages in the django hierarchy. Messages aren’t posted using this logger name since one of the following loggers will be used.

django.request: This logger handles the logging of HTTP requests and will raise exceptions for certain status codes. All HTTP 5xx error codes will raise Error messages. Likewise, HTTP 4xx codes will appear as Warning messages.

django.server: When running the server using the runserver command (which we’ve been doing), this will log messages related to the handling of those requests, just like the django.request logger—except that all other messages are logged at the Info level. These are messages that don’t trigger an HTTP status code of 5xx or 4xx.

django.template: No matter how often I’ve worked with Django templates, I’ve never put one together without errors the first time. The django.template logger handles errors related to the rendering of templates. Missing context variables will appear in the log as Debug messages.

django.db.backends: This logger handles any messages from the interaction of the code with the database. All application-level SQL statements will appear at the Debug level. As this can get quite noisy, Debug logging needs to be enabled by changing settings.DEBUG to True.

django.security.*: Django provides handlers for security-related errors. In particular, the logger will receive any messages that result from a SuspiciousOperation error. Django defines subclasses for each kind of security error, such as DisallowedHost or InvalidSessionKey. The rest of the subclasses of SuspiciousOperation can be found [on](https://docs.djangoproject.com/en/2.1/ref/exceptions/#django.core.exceptions.SuspiciousOperation) [Django’s website, under their exceptions page in the documentation](https://docs.djangoproject.com/en/2.1/ref/exceptions/#django.core.exceptions.SuspiciousOperation). A word of caution—if the django.security logger handles a message, it won’t be sent through the django.request logger. So don’t ignore messages from the django.security.* loggers!

django.security.csrf: This logger doesn’t inherit from the SuspiciousOperation logger that the other security handlers extend. This handles any exceptions that occur due to cross-site request forgery (CSRF) attacks.

As one final example, let’s log messages from the django.request extension. This is done by adding the logger to the logging section of the configuration like so:

![](Images/Image1874.png)

This will log request messages like the following:

![](Images/Image1882.png)

Feel free to experiment, and don’t forget to log the django.security.* messages!

You’ve Got This!

That was a lot of information, so let’s recap:

*   Django uses the standard Python logging facilities.
*   Logging settings are set through the logging.dictConfig dictionary.
*   Django provides a few [logging extensions](https://docs.djangoproject.com/en/2.1/topics/logging/#django-s-logging-extensions) for handling common web server issues.

If you need to delve further, you can read up on the Python logging facility as well as the Django logging specifics, both on their respective websites. Until next time, happy logging!

This chapter was contributed by Casey Dunham. [Casey](https://www.caseydunham.com/), who recently launched his own security business, is known for his unique approaches to all areas of application security, stemming from his 10+ year career as a professional software developer. His strengths include secure SDLC development consulting; threat modeling; developer training; and auditing web, mobile, and desktop applications for security flaws.

## Chapter 10: Getting Started Quickly With Angular Logging

In this chapter, I’ll show you how to quickly get started logging in one of the most popular front-end development frameworks: Angular.

“But wait!” you might be thinking. “Do you mean Angular or AngularJS?” I mean both. After a bit of Angular history, we’ll look at logging with AngularJS, and then we’ll use the current Angular version to show you logging in action.

![](Images/Image1889.png)

A Bit of Angular History

The history of Google’s Angular development is tumultuous. Each major version made the previous one obsolete, as the codebase developed in previous Angular versions was not compatible with newer versions. If the cost of refactoring the entire codebase was too high for your company, you never made the upgrade to newer Angular versions.

Like all front-end development frameworks of the time, Angular started as a JavaScript framework. The first version of Angular was called AngularJS, and the JS in the name stands for JavaScript.

Around 2015 at the Angular Conference, the Angular team announced they were moving to TypeScript instead of JavaScript, which marked another major change in the codebase. This is when the JS was dropped from the product name and it simply became Angular.

In addition to moving away from JavaScript, newer Angular versions started embracing component- and service-centered development. While it added more complexity to getting started, this approach is the better architecture for supporting large single-page applications. Currently, Angular has a very structured and opinionated approach to front-end development.

There you have it—some background on Angular. Now, let’s get started with logging in AngularJS!

AngularJS Logging Application

Let me start with a blast from the past, when Angular was young and called AngularJS. Even though it’s an old version now, there are many current applications still using Angular 1\. In AngularJS (last version 1.7.2), things were simpler to bootstrap. Let’s revisit a simple example for logging with AngularJS.

With Windows Explorer, create a new folder called angular-logging. Place this in your development folder on your hard drive. This folder will contain our two simple files: script.js (containing our logging logic) and index.html (containing our template view).

In Visual Studio Code, open this folder by choosing File > Open Folder. Then, click File > New File (CTRL+N) and type the file name: script.js. This new file will contain our Angular 1 controller, which will perform the Angular logging logic.

![](Images/Image1897.png)

When creating an Angular controller, we pass in a name for the controller and an array of parameters that define this controller’s dependencies. In our case, we’re passing the $scope object and the $log module that we’ll use.

The last parameter is the actual function that performs our logic...logging. To keep things simple, we add two variables on the global $scope object: logger and message.

The logger variable is the actual $log library, and the message variable will be bound to the HTML template index.html.

Next, we create the HTML template—our view—that will be controlled by LogController.

![](Images/Image1904.png)

What do we have in our HTML view? Let’s take a closer look above, inside index.html.

After importing the Angular library and our controller code, start binding the HTML elements to the LogController and the message variable. In addition, add click listeners using the Angular 1 directive ng-click so that when we click the buttons, our controller’s function will be called.

Testing Our AngularJS Logging Application

In Firefox, click File > Open File and navigate to the index.html file. Once the file loads, bring up Firefox Developer Tools and then click the Console tab.

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular1-logging-view.png](Images/Image1911.png)

By clicking on the buttons, we can see the various logging levels displayed. We can also change the text being logged in the Message field since it’s bound two ways to the controller.

In AngularJS, the $log module is a simple wrapper to console.log and doesn’t provide any extra functionality.

There you have it! Logging with AngularJS in a few steps. In AngularJS, things are much simpler.

Now, let’s move on to logging in today’s version of Angular. But before we take a look at that, we need to build a simple Angular application skeleton. This will prove to be more difficult than it was with AngularJS.

Building a Simple Angular Application

Getting started with Angular is going to be different. Gone are the days when you can simply load an HTML file straight from your browser and get coding quickly. To get even a simple application bootstrapped, you must have a few things installed.

Let’s get started! First, we’ll need to [install Node.js](https://nodejs.org/). Node comes with its own package manager npm, which we’ll need in order to install Angular.

Next, we need to install the Angular command line interface (CLI). Before we can talk about logging with Angular, we’ll need to use Angular CLI to generate an application skeleton:

![](Images/Image1919.png)

The -g flag stands for global. If we don’t use -g, Angular CLI will only be installed in the current folder, and it’s not going to be accessible anywhere else.

If you’re on a Mac, you need to put sudo at the beginning of this command to execute it as an administrator. Otherwise, you’ll get permission errors.

If you’re doing this for the first time, this step might take a while. Once Angular CLI has been installed, we can create a simple application:

![](Images/Image1929.png)

Here we’re telling Angular CLI to generate a new project called hello-world and store it in a folder with the same name. It’ll be created in the folder where you’re running the Angular CLI commands, and it’ll contain all the files needed for the Angular application to run.

Now, let’s run it.

![](Images/Image1938.png)

Ugh! Now you have to wait a while (depending on your machine’s muscles) for Angular to actually compile all that TypeScript code that was generated. Look for an output like this:

![](Images/Image1949.png)

Testing Our New Angular Application

Finally! Now you can simply point your browser to localhost:4200 and see the Angular logo. As you can see, wow—this was not trivial.

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular4-hello-world-1.png](Images/Image1961.png)

Now let’s take a look at the hello-world folder and see what Angular CLI actually created for us:

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular4-hello-visual-code.png](Images/Image1968.png)

Remember that we’re still trying to get to logging with Angular. But for now, here’s a quick summary of an Angular application structure:

The top folder called e2e is for testing our application. The next one, node_modules, is for all the modules your application needs. If we expand node_modules, we’ll see that even for the simplest applications, there are a lot of modules needed. Finally, we get to the src folder that has our source code. This is where we will do our work. And down the tree, there’s index.html, which is our application’s entry point.

Generating an Angular Logging Component

Now, as promised, let’s turn our attention to logging in Angular. We’ll add a new Angular component that has several buttons, and these buttons will trigger logging at the console at different levels. In addition, we’ll add a timestamp to each logging statement.

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular-new-component.png](Images/Image1976.png)

Our first step is to generate a new Angular component for logging. We’ll do this using the Angular CLI in the same folder as our project hello-world.

![](Images/Image1983.png)

In this command, g stands for generate, while c stands for component. Logger is the name of our new component. Taking a look at the project folder (hello-world) inside the src/app folder, we see a new folder called logger.

The logger folder contains the four basic parts of an Angular component: styling (.css), view (.html), test (spec.ts), and model (.ts).

In addition, our application’s module file (app.module.ts) has been modified to automatically import the new component.

![](Images/Image1991.png)

This way, as soon as we generate a new component, we can immediately use it.

So, let’s use our brand-spanking-new Angular component.

Adding Logging Logic in Our Angular Component

To start adding logging logic, we’ll first open our application view file app.component.html. We generated this file at the very beginning when we created the hello world application.

Let’s add our new Angular component, as well as the new custom HTML tag that was just created (<app-logger></app-logger>):

![](Images/Image1998.png)

Now, let’s go inside our new Angular component model (logger.component.ts) and add some logging logic.

![](Images/Image2005.png)

Take a look at our model file. Our main method is log (level, message) method, which simply logs to the console the message passed in, according to the level passed in.

Next, we’ll take a look at our model file above (logger.component.ts). So, the method log simply logs to the console the message passed in as a parameter. Additionally, logging is done according to the logging level, which is also passed in as a parameter. We then finish formatting each log statement to include the level and a simple timestamp, in addition to the message.

Now, let’s add our controls to the HTML view in logger.component.html:

![](Images/Image2013.png)

Let’s note a few things here in our view. First, notice lines 1 and 6, which are {{title}} and {{logStatement}}. These are our model variables that were bound to our view. In Angular, they’re bound two ways, which means that if the value changes in the view, the model value is updated and vice versa. If you change the value in the model, the value in the view will also be updated.

In our particular case, the {{logStatement}} will be changed in our model as we click the various logging level buttons. The HTML view will update when the model value updates.

Let’s take a look at our Angular logging application:

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular4-logging-app.png](Images/Image2022.png)

On the right-hand side, we have our Google Chrome console, which first displays the message in the ngOnInit method. Then, as we click on the various logging buttons, we log to the console in the appropriate logging level.

Generating a New Service With Angular CLI

Logging inside an Angular component was a very quick way to log with Angular, certainly. But that’s not the proper way to create a logging utility that can be reused to log in our Angular application.

To do it properly, let’s create a logging service called LogEngine. A service is a small piece of our software that specializes in performing one specific function. Our new service specializes in logging messages to the console.

This time, since we already have our logger component, let’s create an Angular service that will contain our logging logic. We’ll also change our logger component to only have our user interface that will use the new service.

We could simply use the Angular CLI again to generate a service, just as we generated the Angular component above. To do that, in a terminal window, we’d make sure we’re inside our hello-world folder. We’d then use Angular CLI to generate a service instead of a component:

![](Images/Image2031.png)

As usual, g stands for generate, while s stands for service. We’re naming our logging service logEngine. Notice that in addition to the service name, we also include the path to this new service. And let me share a piece of advice: make sure you don’t use the word service in the name of your service when you’re creating through the CLI. Angular CLI automatically adds the word service to the class definition.

But I’ve chosen not to generate our new service using Angular CLI. Let’s discuss how to do this manually instead.

Creating a New Angular Logging Service Manually

This time, let’s create the new Angular logging service manually. It’s good to know how to do this because, many times, it’s helpful to see what happens behind the scenes when things are generated for us.

In Visual Studio Code, under src/app, we’ll create a new folder called services. Inside that, create another new folder called log-engine. This folder will hold our logEngine service. Inside this new folder, let’s create a new file called log-engine.service.ts. This is our service file.

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular-service-created-215x300.png](Images/Image2042.png)

Next, let’s take a look at our IDE. We should still see the logger component folder from above. Now we have the services folder with the log-engine subfolder inside it. It’s here that we’ll find our new log-engine.service.ts file. In this file, we’ll create our LogEngineService logic.

Now, let’s move all our logging logic from the old logger.component.ts to the new logging service, log-engine.service.ts.

We’ll also refactor our logging methods to better resemble a normal logging interface, with specific methods for each logging level.

Moving Logging Logic to the New Angular Service

At this point, we’ll simply move our existing logging logic from our logger component to our new LogEngineService. In addition, we’ll refactor the existing log method and split it into specific methods dedicated to each log level. This is a much better interface for logging, as it resembles the well-known console logging interface.

![](Images/Image2054.png)

Notice that the class name is LogEngineService. Angular CLI automatically adds the word service when creating a service. And we should do the same, even though we’re creating the file manually.

We still want to add the logging level and the timestamp in each log entry. In addition, each method in our LogEngineService returns each log entry. We want to also display the logging statement in our application via our HTML view. This will become clearer in a little bit.

Now let’s wire our LogEngineService and use it in our logger Angular component.

Wiring the New Angular Logging Service

To wire the service, we’ll open app.module.ts. Here’s where we define our application-level dependencies. We need to add our new service as one of the providers.

![](Images/Image2061.png)

Notice that we added LogEngineService in the providers list—providers: [LogEngineService].

Using Our Service Inside Our Angular Component

Next in our journey toward logging quickly with Angular, we need to add LogEngineService to our logger component inside logger.component.ts. Let’s take a look at the import statement on top of the file:

![](Images/Image2069.png)

Now our existing logger component is ready to use our new logEngine service. I’ve also refactored our existing component so it has clear button listeners, specific to each button. Our old component doesn’t have any logging logic because we’ve moved all that logic to our new service.

Let’s take a look again at the entire logger.component.ts file:

![](Images/Image2076.png)

I’m sure you quickly noticed the new button listeners. But what’s logService? Well, it’s our new LogEngineService that we just created and imported into our logger component. Notice the constructor. That’s how LogEngineService becomes logService:

![](Images/Image2084.png)

Now all our button listeners can use the logService instance to call the logging methods on our new service.

Take special note of the logStatement variable. We bind this model variable to our HTML view. Our LogEngineService updates this variable with the value of the last log entry. That’s why our LogEngineService log methods return every log entry.

Refactoring the HTML View and Retesting

The last step is to update our logger component’s HTML view (logger.component.html) to use the new button listeners that we just created:

![](Images/Image2091.png)

Here, we just added calls to each button listener with a message. We no longer have to pass the desired logging level since each button listener will send the right logging level to the LogEngineService methods.

All we have to do now is to save all files and refresh our application running at localhost:4200. Let’s take a look:

![https://www.hitsubscribe.com/wp-content/uploads/2018/11/angular-logging-final-debug-1024x463.png](Images/Image2098.png)

There you have it! Same exact functionality as we previously implemented when we were logging from inside the container itself. However, now we have an independent Angular service, specialized in logging our messages, embellished with the logging level and timestamp.

Enhance Your Logging Service!

In this chapter, we learned how to get started logging quickly with Angular and AngularJS. We also touched on installing Angular CLI and using it to create a skeleton for developing with Angular. Plus, we refactored our logging component so that it uses an Angular logging service. That equates to much better organization of our code and logic.

It’s probably obvious that logging to the console doesn’t bring much value other than during debugging. However, after exploring Angular services, you should have some ideas now about how you could enhance your logging service so that it can persist logs via REST calls or integrate with a log aggregation service. So go forth and log in Angular like a pro!

This chapter was contributed by [Vlad Georgescu](https://www.organizepictures.com/). Vlad is senior system architect and full-stack enterprise software developer with almost two decades of experience in the development lifecycle. He also has experience as a SCRUM master, agile coach, and team leader. On the communications front, Vlad is also effective: he’s created online communities and worked on social media marketing strategies.

## Chapter 11: Getting Started Quickly With Meteor Logging

We’ve covered a lot of bases in previous chapters. In addition to Java and PHP, we’ve created guides for Ruby, Swift, Django, and more. Now, we’ll discuss logging from a Meteor point of view.

Since Meteor can follow the same premise as JavaScript and Node.js, we’re going to change things up a bit. Instead of an empty app, we’re going to clone an existing sample app and add logging to it. But if this tutorial isn’t quite what you were looking for, go check out the basic JavaScript and Node.js chapters from our first logging book, [The Scalyr Guide to Getting Started Logging as Quickly as Possible](https://www.amazon.com/Getting-Started-Logging-Quickly-Possible-ebook/dp/B07H8SNT2Q). They’ll cover anything else you might need.

But don’t worry, we’ll still cover these topics:

*   Meteor overview
*   Basic logging
*   Where to log
*   What to log

Now let’s get started.

![Meteor_logging_image_with_scalyr_colors](Images/Image2106.png)

Meteor Overview

If you came to this chapter with some experience using Meteor, you might not need this section. But I’d like to make sure we’re all starting from the same point, so here’s some quick Meteor info. Don’t worry. I’ll be brief.

Meteor provides a full-stack JavaScript platform for developing web and mobile apps. It includes a number of packages from Node.js and other JavaScript libraries. And it focuses on and provides full stack reactivity so your UI acts seamlessly with your backend server. And as a bonus, it provides easy MongoDB integration right out of the box.

Basic Logging

As I mentioned above, instead of creating a bare application, we’re going to clone one of the existing sample applications that the folks over at Meteor have provided. Since we’re adding logging to an already existing app, we’ll be able to see different logs come through with minimal effort.

Setup

If you haven’t used Meteor before, no worries—basic setup is a breeze. First, you’ll need to install both Node.js and npm. If you’re on a Mac, you’ll need Xcode as well.

For step two, we’ll install Meteor using either Chocolatey or a curl command, depending on your operating system.

![](Images/Image2115.png)

All set? Great. Next, let’s clone the simple todo app from Meteor:

![](Images/Image2124.png)

Once you’ve got everything downloaded and installed, cd into the simple-todo directory and run the app using the Meteor command.

![https://library.scalyr.com/2019/02/15124602/011.png](Images/Image2135.png)

Once the application has started, go to http://localhost:3000/. You should see a simple todo app there.

![https://library.scalyr.com/2019/02/15124645/021-1024x463.png](Images/Image2147.png)

You should be able to add users, add items to the checklist, and so on. Go ahead and play around with it. I’ll be waiting at the next section for you.

Console Logging

Now that you’ve had a chance to check out the application, let’s get started. To demonstrate simple logging, we’re going to add some console logs to our application. This can be helpful for debugging issues on the client side while you’re developing. But it won’t do much for you once your application is being used by someone out in the real world—you won’t have access to their console logs.

To start, let’s add some code to the imports/api/tasks.js file. This file contains the JavaScript that’s executed when we add or remove tasks from the list. In the tasks.insert method, add the log.console line shown in this image:

![https://library.scalyr.com/2019/02/15124721/031-1024x439.png](Images/Image2154.png)

Next, after saving that file, head over to your browser window. It should have updated automatically, so you don’t have to restart the app. When you add a new task, you should see the output in your browser console.

![https://library.scalyr.com/2019/02/15124750/041-1024x280.png](Images/Image2162.png)

Looks great, right? What if we also want to add some user context? Modify the line in the tasks.insert method to also print out the userId object that this application has defined.

![](Images/Image2169.png)

After that, you should see something like this:

![https://library.scalyr.com/2019/02/15124816/051-1024x221.png](Images/Image2177.png)

Not super helpful, is it? Let’s make it a little more useful by asking Meteor to find the username associated with this ID instead.

![](Images/Image2184.png)

Yes, that looks much better!

![https://library.scalyr.com/2019/02/15124841/06-1024x243.png](Images/Image2191.png)

OK, now that we’ve done some simple console logging, we can move on to the next section. However, I have one thing I’d like you to do first.

Now that you have a Meteor application up and running, take some time to explore its various functionalities by adding your own console logging throughout the code. It really helps you understand the application by seeing data flow through the system as you use it. And though these may not be logs you want to keep around forever, they’ll help you gain a sense of what goes into a good Meteor application.

Where to Log

Let’s return to something I mentioned at the beginning of the console logging section. You won’t be able to view your customer’s console.log files. So let’s discuss what you should do instead.

Send Logs to the Server

As discussed, if your application is being used by actual customers, you won’t have access to their console logs. Sure, you could have them open their browser console and send you what’s there every time there’s an issue. But you’re assuming that people will know how to do that. And even if they do know, it doesn’t provide a great user experience for them.

So what can we do instead? Well, instead of just writing to a console, we could send logs back to the server. But then what?

Save Logs for Later Use

With Meteor, one option could be to set up a logging table in MongoDB. So instead of just inserting tasks as our example above shows, we could insert logging or error messages. However, storing logs in a database typically doesn’t make sense. You want to store them somewhere easily accessible so you can start harvesting some analytics.

Let’s consider another option. How about taking a look at some of Scalyr’s [APIs](https://www.scalyr.com/help/api)? There are a lot of goodies there. And two of them let us add events to our Scalyr logs, either one at a time or by batch. So instead of logging to the console or saving the logs to our database, we can send events that require logging right back to Scalyr.

In this situation, I would send the logs over to the server side of my Meteor application and then call the Scalyr APIs with the token tied to my account. Let’s go over this in greater detail.

First, adding simple HTTP functionality to your Meteor app requires running the following command within your Meteor directory.

![](Images/Image2199.png)

That will let you make HTTP calls to remote servers easily.

Then we can use the following syntax to send an event to Scalyr’s addEvents API.

![](Images/Image2208.png)

You may have noticed that I broke out the username from the message I sent. That’s because breaking parts of the log into separate attributes will help with searching later.

What to Log

With great logging comes great responsibility. So what should we log in our applications?

Well, that depends—not only on what your application does, but also on whether you’re logging on the client side or the server side. You also want to make sure that what you log adds value. Logging every little action is usually a bad idea.

In fact, the example above doesn’t represent something I’d want to be logged in my system. I don’t care what my customers add to their to-do lists. I care about metrics, performance, and errors. And I want specific information that can help debug issues.

So what sort of data can we log?

*   Errors: if something goes wrong, we want to know about it.
*   Usage: let’s see how often various parts of our application are used. If we have features no one uses, we can deprecate them or make them better.
*   Performance: we want to know what the customer experiences regarding latency. If the application slows down too much for them, we need to investigate.

Specifically for error logging, what information do we need?

*   Timestamps that tell exactly when an error occurred.
*   User ID or context, so we know who was affected.
*   Relevant parameters to help recreate the problem and find a solution.
*   Unique and specific error messages to help pinpoint the problem.

You’re on Your Way

You’re in a great place. You’ve got a sample Meteor app to experiment with, as well as some guidance on how to log information in it. Once you’ve logged data from your application, remember to review the logs from time to time. Iterate on what’s being logged and the format until you have a useful set of data that will help you debug and optimize your application. And now you can rest easy knowing you’ll be able to support your Meteor application in production.

This chapter was contributed by Sylvia Fronczak. [Sylvia](https://sylviafronczak.com/) is a software developer who has worked in various industries with various software methodologies. She’s currently focused on design practices that the whole team can own, understand, and evolve over time.

## About Scalyr

Scalyr is the log management and observability platform for the new stack. Purpose-built to handle the scale and complexity of modern cloud architectures, Scalyr changes the dynamics of delivering healthy applications by allowing engineers to quickly troubleshoot problems and focus on doing what they love—coding. With 96% of searches completing in under one second and thousands of active users, Scalyr has transformed logs from afterthought into advantage.

Learn more at [scalyr.com](http://scalyr.com/) and follow on Twitter (@scalyr).