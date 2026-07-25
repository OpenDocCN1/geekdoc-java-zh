![](images/00029.jpeg)

## Power Java

#### Mark Watson

This book is for sale at [http://leanpub.com/powerjava](http://leanpub.com/powerjava)

This version was published on 2015-11-29

![publisher's logo](images/00001.jpeg)

*   *   *   *   *

This is a [Leanpub](http://leanpub.com) book. Leanpub empowers authors and publishers with the Lean Publishing process. [Lean Publishing](http://leanpub.com/manifesto) is the act of publishing an in-progress ebook using lightweight tools and many iterations to get reader feedback, pivot until you have the right book and build traction once you do.

*   *   *   *   *

© 2015 Mark Watson

## Table of Contents

## Guide

1.  [Begin Reading](#part0002.html_1T140-258cf8ee95f94c5dab2217695d18f654)

## Preface

I have been programming since high school and since the early 1980s I have worked on artificial intelligence, neural networks, machine learning, and general web engineering projects. Most of my professional work is reflected in the examples in this book. These examples programs were also chosen based on their technological importance, i.e. the rapidly changing technical scene of big data, the use of machine learning in systems that touch most parts of our lives, and networked devices. I then narrowed the list of topics based on a public survey I announced on [my blog](https://blog.markwatson.com). Many thanks to the people who took the time to take this survey. It is my hope that the Java example programs in this book will be useful in your projects. Hopefully you will also have a lot of fun working through these examples!

Java is a flexible language that has a huge collection of open source libraries and utilities. Java gets some criticism for being a verbose programming language. I have my own coding style that is concise but may break some of the things you have learned about “proper” use of the language. The Java language has seen many upgrades since its introduction over 20 years ago. This book requires and uses the features of Java 8 so please update to the latest JDK if you have not already done so. You will also need to have maven installed on your system. I also provide project files for the free Community Version of the IntelliJ IDE.

Everything you learn in this book can be used with some effort in the alternative JVM languages Clojure, JRuby, and Scala. In addition to Java I frequently use Clojure, Haskell, and Ruby in my work.

### Book Outline

This book consists of eight chapters that I believe show the power of the Java language to good effect:

*   Network programming techniques for the Internet of Things (IoT)
*   Natural Language Processing using OpenNLP including using existing models and creating your own models
*   Machine learning using the Spark mllib library
*   Anomaly Detection Machine Learning
*   Deep Learning using Deeplearning4j
*   Web Scraping
*   Using rich semantic and linked data sources on the web to enrich the data models you use in your applications
*   Java Strategies for Knowledge Management-Lite using Cloud Data Resources

The first chapter on IoT is a tutorial on network programming techniques for IoT development. I have also used these same techniques for multiplayer game development and distributed virtual reality systems, and also in the design and implementation of a world-wide nuclear test monitoring system. This chapter stands on its own and is not connected to any other material in this book.

The second chapter shows you how to use the OpenNLP library to train your own classifiers, tag parts of speech, and generally process English language text. Both this chapter and the next chapter on machine learning using the Spark mllib library use machine learning techniques.

The fourth chapter provides an example of anomaly detection using the University of Wisconsin cancer database. The fifth chapter is a short introduction to pulling plain text and semi-structured data from web sites.

The last two chapters are for information architects or developers who would like to develop information design and knowledge management skills. These chapters cover linked data (semantic web) and knowledge management techniques.

The source code for the examples can be found at https://github.com/mark-watson/power-java and are all released under the Apache 2 license. I have tried to use only existing libraries in the examples that are either Apache 2 or MIT style licensed. In general I prefer Free Software licenses like GPL, LGPL, and AGPL but for examples in a book where I expect readers to sometimes reuse entire example programs or at least small snippets of code, a license that allows use in commercial products makes more sense.

There is a subdirectory in this github repository for each chapter, each with its own maven pom.xml file to build and run the examples.

The five chapters are independent of each other so please feel free to skip around when reading and experimenting with the sample programs.

This book is available for purchase at https://leanpub.com/powerjava.

You might be interested in other books that I have self-published via leanpub:

*   [Practical Artificial Intelligence Programming With Java](https://leanpub.com/javaai)
*   [Loving Common Lisp, or the Savvy Programmer’s Secret Weapon](https://leanpub.com/lovinglisp)
*   [Build Intelligent Systems with JavaScript](https://leanpub.com/aijavascript)

My older books published by Springer-Verlag, McGraw-Hill, Morgan Kaufman, APress, Sybex, M&T Press, and J. Wiley are listed on the [books page of my web site](http://markwatson.com/books/).

One of the major themes of this book is machine learning. In addition to [my general technical blog](https://blog.markwatson.com) I have a separate blog that contains information on using machine learning and cognition technology: [blog.cognition.tech](http://blog.cognition.tech/?view=classic) and an [associated website supporting cognition technology](http://cognition.tech/).

### If You Did Not Buy This Book

I frequently find copies of my books on the web. If you have a copy of this book and did not buy it please consider paying the minimum purchase price of $4 at [leanpub.com/powerjava](https://leanpub.com/powerjava/).

## Network Programming Techniques for the Internet of Things

This chapter will show you techniques of network programming relevant to developing Internet of Things (IoT) projects and products using local TCP/IP and UDP networking. We will not cover the design of hardware or designing IoT user experiences. Specifically, we will look at techniques for using local directory services to publish and look up available services and techniques for efficiently communicating using UDP, multicast and broadcast.

This chapter is a tutorial on network programming techniques that I believe you will find useful for developing IoT applications. The material on User Data Protocol (UDP) and multicast is also useful for network game development.

I am not covering some important material: the design of user experience and devices, and IoT devices that use local low power radios to connect cooperating devices. That said, it is worth thinking about what motivates the development of IoT devices and we will do this in the next section.

There are emerging standards for communication between IoT devices and open source projects like TinyOS and Contiki that are C language based, not Java based, so I won’t discuss them. Oracle supports the Java ME Embedded profile that is used in some IoT products but in this chapter I want to concentrate network programming techniques and example programs that run on stock Java (including Android devices).

### Motivation for IoT

We are used to the physical constraints of using computing devices. When I was in high school in the mid 1960s and took a programming class at a local college I had to make a pilgrimage to the computer center, wait for my turn to use a keypunch machine, walk over to submit my punch cards, and stand around and wait and eventually get a printout and my punch cards returned to me. Later, interactive terminals allowed me to work in a more comfortable physical environment. Jumping ahead almost fifty years I can now use my smartphone to SSH into my servers, watch movies, and even use a Java IDE. As I write this book, perhaps 70% of Internet use is done on mobile devices.

IoT devices complete this process of integrating computing devices more into our life with fewer physical constraints on us. Our future will include clothing, small personal items like pens, cars, furniture, etc., all linked in a private and secure data fabric. Unless you are creating content (e.g., writing software, editing pictures and video, or performing a knowledge engineering task) it is likely that you won’t think too much about the devices that you interact with and in general will prefer mobile devices. This is a similar experience to driving a car where tasks like braking, steering, etc. are “automatic” and don’t require much conscious thought.

We are physical creatures. Many of us gesture with our hands while talking, move things around on our desk while we are thinking, and generally use our physical environment. Amazing products will combine physical objects and computing and information management.

Before diving into techniques for communication between IoT devices, we will digress briefly in the next section to see how to run the sample programs for this chapter.

### Running the example programs

If you want to try running the example programs let’s set that up before going through the network programming techniques and code later in this chapter. Assuming that you have cloned the github repository for the examples in this book, go to the subdirectory internet_of_things, open two shell windows and use the following commands to run the examples in the same order that they are presented (these commands are in the README.md file so you can copy and paste them). These commands have been split to multiple lines to fit the page width of this book:

#### Build

```
1     mvn clean compile package assembly:single
```

#### Run service discovery

```
1     java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
2 	     com.markwatson.iot.CreateTestService
3     java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar /
4 	     com.markwatson.iot.LookForTestService
```

#### Run UDP experiments:

```
 1     java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
 2 	     com.markwatson.iot.UDPServer
 3     java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
 4 	     com.markwatson.iot.UDPClient
 5 
 6     # Multicast experiments:
 7     java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
 8 	     com.markwatson.iot.MulticastServer
 9     java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
10 	     com.markwatson.iot.MulticastClient
```

Line 2 compiles and builds the examples. For each of the example programs you will run two programs on the command line. For example for the service discovery example on lines 5 and 6 (which would be entered on one line in a terminal window) we start a test service and lines 7 and 8 run the service test client. Similarly, lines 10 through 20 show how to run the services and test clients for the UDP experiments and the multicast experiments. I repeat these instructions with each example as we look at the code but I thought that you might enjoy running all three examples before we look at the implementations of the examples later in this chapter.

In each example, run the two example programs in different shell windows. For more fun, run the examples using different laptops or any device that can run Java code.

The following figure shows the project for this chapter in the Community Edition of IntelliJ:

![IntelliJ project view for the examples in this chapter](images/00002.jpeg)

IntelliJ project view for the examples in this chapter

This chapter starts with a design pattern that you might use for writing IoT applications. Then the following three major sections show you how to use directory lookups, use User Data Protocol (UDP) instead of TCP/IP, and then multi-cast/broadcast.

The material in this chapter is fairly elementary but it seems like many developers don’t have experience with lower level network programming techniques. My hope is that you will understand when you might want to use a lower level protocol like UDP instead of TCP and when you might find directory lookups useful in your applcations.

### Design Pattern

The pattern that the examples in the following sections support is simple (in principle): small devices register services that they offer and look for services offered in other devices. Devices will use User Data Protocol (UDP) and multi-cast to communicate for using and providing services. Once a consumer has discovered a service privider (host, IP address, port, and service types) a consumer can also open a direct TCP/IP socket connection to a provider to use a newly discovered service.

The following diagram shows several IoT use cases:

*   A consumer uses the JmDNS library to broadcast on the local network a request for services provided.
*   The JmDNS library on the provider side hears a service description request and broadcasts available services.
*   The JmDNS library on the consumer side listens for the broadcast from the provider.
*   Using a service description, the consumer makes a direct socket connection to the provider for a service.
*   The provider periodically broadcasts updated data for its service.
*   The consumer listens for broadcasts of updated data and uses new data as it is available.

![Consumer and Provider Use Cases](images/00003.gif)

Consumer and Provider Use Cases

This figure shows a few use cases. You can use these interaction patterns of interactions between IoT devices using application specific software you write.

### Directory Lookups

In the next two sub-sections we will be using the [Java JmDNS library](http://jmdns.sourceforge.net/) that supports a local multi-cast Domain Name Service (DNS) and supports service discovery. JmDNS is compatible with Apple’s Bonjour discovery service that is also available for installation on Microsoft Windows.

JmDNS has been successfully used in Android apps if you change the defaults on your phone to accept multi-cast (since Android version 4.1 [Network Service Discovery (NDS)](https://developer.android.com/training/connect-devices-wirelessly/nsd.html)). Android development is outside the scope of this chapter and I refer you to the NDS documentation and example programs if you are interested. I tried the example Android NsdChat application on my Galaxy S III (Android 4.4.2) and Note 4 (Android 5.0.1) and this example app would be a good place for you to start if you are interested in using Android apps to experiment with IoT development.

#### Create and Register a Service

The example program in this section registers a service using the JmsDNS Java library that listens on port 1234\. In the next section we look at another example program that connects to this service.

```
 1 package com.markwatson.iot;
 2 
 3 import javax.jmdns.*;
 4 import java.io.IOException;
 5 
 6 public class CreateTestService {
 7   static public void main(String[] args) throws IOException {
 8     JmDNS jmdns = JmDNS.create();
 9     jmdns.registerService(
10         ServiceInfo.create("_http._tcp.local.", "FOO123.", 1234,
11             0, 0, "any data for FOO123")
12     );
13     // listener for service FOO123:
14     jmdns.addServiceListener("_http._tcp.local.", new Foo123Listener());
15   }
16 
17   static class Foo123Listener implements ServiceListener {
18 
19     public void serviceAdded(ServiceEvent serviceEvent) {
20       System.out.println("FOO123 SERVICE ADDED in class CreateTestService");
21     }
22 
23     public void serviceRemoved(ServiceEvent serviceEvent) {
24       System.out.println("FOO123 SERVICE REMOVED in class CreateTestService");
25     }
26 
27     public void serviceResolved(ServiceEvent serviceEvent) {
28       System.out.println("FOO123 SERVICE RESOLVED in class CreateTestService");
29     }
30   }
31 }
```

The service is created in lines 10 and 11 defining the service name (notice that a period is added to the end of the service name FOO123), the port that the server listens on (1234 in this case), and the last argument is any string data that you also want to pass to clients looking up information on service FOO123\. When you run the client in the next section you will see that the client receives this information for the local DNS lookup.

Running this example produces the following output (edited to fit the page width):

```
> java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
       com.markwatson.iot.CreateTestService
FOO123 SERVICE ADDED in class CreateTestService
```

#### Lookup a Service by Name

If you have the service created by the example program in the last section running then the following example program will lookup the service.

```
 1 package com.markwatson.iot;
 2 
 3 import javax.jmdns.*;
 4 import java.io.IOException;
 5 
 6 // reference: https://github.com/openhab/jmdns
 7 
 8 public class LookForTestService {
 9 
10   static public void main(String[] args) throws IOException {
11     System.out.println("APPLICATION entered registerService");
12     JmDNS jmdns = JmDNS.create();
13     // try to find a service named "FOO123":
14     ServiceInfo si = jmdns.getServiceInfo("_http._tcp.local.", "FOO123");
15     System.out.println("APPLICATION si: " + si);
16     System.out.println("APPLICATION APP: " + si.getApplication());
17     System.out.println("APPLICATION DOMAIN: " + si.getDomain());
18     System.out.println("APPLICATION NAME: " + si.getName());
19     System.out.println("APPLICATION PORT: " + si.getPort());
20     System.out.println("APPLICATION getQualifiedName: " + si.getQualifiedName());
21     System.out.println("APPLICATION getNiceTextString: " + si.getNiceTextString(\
22 ));
23   }
24 }
```

We use the JmsDNS library in lines 12 and 14 to find a service by name. In line 14 the first argument “_http._tcp.local.” indicates that we are searching the local network (for example, your home network created by a router from your local ISP).

Running this example produces the following output (edited to fit the page width):

```
> java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
       com.markwatson.iot.LookForTestService
APPLICATION entered registerService
APPLICATION si: [ServiceInfoImpl@1595428806
                  name: 'FOO123._http._tcp.local.' address: '/192.168.0.14:1234'
                  status: 'DNS: Marks-MacBook-Air-local.local.
                  state: probing 1 task: null', has data empty]
APPLICATION APP: http
APPLICATION DOMAIN: local
APPLICATION NAME: FOO123
APPLICATION PORT: 1234
APPLICATION getQualifiedName: FOO123._http._tcp.local.
APPLICATION getNiceTextString: any data for FOO123
```

**Do** **you** **want** **to** **find** **all** **local** **services?** Then you can also create a listener that will notify you of all local HTTP services. There is an example program in the JmsDNS distribution on the path src/sample/java/samples/DiscoverServices.java written by Werner Randelshofer. I changed the package name to com.markwatson.iot and added it to the git repository for this book. You can try it using the following commands:

```
mvn clean compile package assembly:single
java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
         com.markwatson.iot.CreateTestService
java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
         com.markwatson.iot.DiscoverServices
```

While it is often useful to find all local services, I expect that for your own projects you will be writing both service and client applications that cooperate on your local network. In this case you know the service names and can simply look them up as in the example in this section.

### User Data Protocol Network Programming

You are most likely familiar with using TPC/IP in network programming. TCP/IP provides some guarantees that the sender is notified on failure to deliver data to a receiving program. User Data Protocol (UDP) makes no such guarantees for notification of message delivery and is very much more efficient than TCP/IP. On local area networks data delivery is more robust to failure compared to the Internet and since we are programming for devices on a local network it makes some sense to use a lower level and more efficient protocol.

#### Example UDP Server

The example program in this section implements a simple service that listens on port 9005 for UDP packets that are client requests. The UDP packets received from clients are assumed to be text and this example slightly modifies the text and returns it to the client.

```
 1 package com.markwatson.iot;
 2 
 3 import java.io.IOException;
 4 import java.net.*;
 5 
 6 public class UDPServer {
 7   final static int PACKETSIZE = 256;
 8   final static int PORT = 9005;
 9 
10   public static void main(String args[]) throws IOException {
11     DatagramSocket socket = new DatagramSocket(PORT);
12     while (true) {
13       DatagramPacket packet =
14          new DatagramPacket(new byte[PACKETSIZE], PACKETSIZE);
15       socket.receive(packet);
16       System.out.println("message from client: address: " + packet.getAddress() +
17           " port: " + packet.getPort() + " data: " +
18           new String(packet.getData()));
19       // change message content before sending it back to the client:
20       packet.setData(("from server - " + new String(packet.getData())).getBytes(\
21 ));
22       socket.send(packet);
23     }
24   }
25 }
```

In line 11 we create a new DatagramSocket listener on port 9005\. On lines 13 and 14 we create a new empty DatagramPacket that is used in line 16 to hold data from a client. The example code prints out packet data, changes the text from the client, and returns the modified text to the client.

Running this example produces the following output (edited to fit the page width):

```
1 > java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
2         com.markwatson.iot.UDPServer
3 message from client: address: /127.0.0.1 port: 63300
4                      data: Hello Server1431540275433
```

Note that you must also run the example program from the next section to get the output in lines 4 and 5\. This is why I listed the commands at the beginning of the chapter for running all of the examples: I thought that if you ran all of the examples according to these earlier directions, the example programs would be easier to understand.

#### Example UDP Client

The example program in this section implements a simple client for the UDP server in the last section. A sample text string is sent to the server and the response is printed.

```
 1 package com.markwatson.iot;
 2 
 3 import java.io.IOException;
 4 import java.net.*;
 5 
 6 public class UDPClient {
 7 
 8   static String INET_ADDR = "localhost";
 9   static int PORT = 9005;
10   static int PACKETSIZE = 256;
11 
12   public static void main(String args[]) throws IOException {
13     InetAddress host = InetAddress.getByName(INET_ADDR);
14     DatagramSocket socket = new DatagramSocket();
15     byte[] data = ("Hello Server" + System.currentTimeMillis()).getBytes();
16     DatagramPacket packet = new DatagramPacket(data, data.length, host, PORT);
17     socket.send(packet);
18     socket.setSoTimeout(1000); // 1000 milliseconds
19     packet.setData(new byte[PACKETSIZE]);
20     socket.receive(packet);
21     System.out.println(new String(packet.getData()));
22     socket.close();
23   }
24 }
```

Running this example produces the following output (edited to fit the page width):

```
> java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
         com.markwatson.iot.UDPClient
from server - Hello Server1431540275433
```

I have used UDP network programming in many projects and I will mention two of them here. In the 1980s I was an architect and developer on the NMRD project that used 38 seismic research stations around the world to collect data that we used to determine if any country was conducting nuclear explosive tests. We used a guaranteed messaging system for meta control data but used low level UDP for much of the raw data transfer. The other application was communcations library for networked racecar and hovercraft games that ran on a local network. UDP is very good for local network game development because it is efficient and the chance of losing data packets is very low and even if packets are lost game play is usually not affected. Remember that when using UDP you are not guaranteed delivery of data and not guaranteed notification of failure!

### Multicast/Broadcast Network Programming

The examples in the next two sections are similar to the examples in the last two sections with one main difference: a server periodically broadcasts data using UDP. The server does not care if any client is listening or not, it simply broadcasts data. If any clients are listening they will probably receive the data. I say that they will probably receive the data because UDP provides no delivery guarantees.

There are specific INET addresses that can be used for local multicast in the range of addresses between 224.0.0.0 and 224.0.0.255. We will use 224.0.0.5 in the two example programs. These are local addresses that are invisible to the the Internet.

#### Multicast Broadcast Server

The following example is very similar to that seen two sections ago (Java class UDPServer) except we do not wait for a client request.

```
 1 package com.markwatson.iot;
 2 
 3 import java.io.IOException;
 4 import java.net.*;
 5 
 6 public class MulticastServer {
 7 
 8   final static String INET_ADDR = "224.0.0.5";
 9   final static int PORT = 9002;
10 
11   public static void main(String[] args)
12       throws IOException, InterruptedException {
13     InetAddress addr = InetAddress.getByName(INET_ADDR);
14     DatagramSocket serverSocket = new DatagramSocket();
15     for (int i = 0; i < 10; i++) {
16       String message = "message " + i;
17 
18       DatagramPacket messagePacket =
19           new DatagramPacket(message.getBytes(),
20               message.getBytes().length, addr, PORT);
21       serverSocket.send(messagePacket);
22 
23       System.out.println("broadcast message sent: " + message);
24       Thread.sleep(500);
25     }
26   }
27 }
```

In line 13 we create an INET address for “224.0.0.5” and in line 14 create a DatagramSocket that is reused for broadcasting 10 messages with a time delay of 1/2 a second between messages. The broadcast messages are defined in line 16 and the code in lines 18 to 21 creates a new DatagramPacket with the message text data and gets broadcast to the local network in line 21.

Running this example produces the following output (output edited for brevity):

```
> java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar com.markwatson.iot.\
MulticastServer
broadcast message sent: message 0
broadcast message sent: message 1
 ...
broadcast message sent: message 8
broadcast message sent: message 9
```

Unlike the UDPServer example two sections ago, you will get this output regardless of whether you are running the listing client in the next section.

#### Multicast Broadcast Listener

The example in this section listens for broadcasts by the server example in the last section. The broadcast server and clients need to agree on the INET address and a port number (9002 in these examples).

```
 1 package com.markwatson.iot;
 2 
 3 import java.io.IOException;
 4 import java.net.DatagramPacket;
 5 import java.net.InetAddress;
 6 import java.net.MulticastSocket;
 7 import java.net.UnknownHostException;
 8 
 9 public class MulticastClient {
10 
11   final static String INET_ADDR = "224.0.0.5";
12   final static int PORT = 9002;
13 
14   public static void main(String[] args) throws IOException {
15     InetAddress address = InetAddress.getByName(INET_ADDR);
16     byte[] buf = new byte[512]; // more than enough for any UDP style packet
17     MulticastSocket clientSocket = new MulticastSocket(PORT);
18     // listen for broadcast messages:
19     clientSocket.joinGroup(address);
20 
21     while (true) {
22       DatagramPacket messagePacket = new DatagramPacket(buf, buf.length);
23       clientSocket.receive(messagePacket);
24 
25       String message = new String(buf, 0, buf.length);
26       System.out.println("received broadcast message: " + message);
27     }
28   }
29 }
```

The client creates an InetAddress in line 15 and allocates storage for the received text messages in line 16\. We create a MulticastSocket on port 9002 in line 17 and in line 19 join the broadcast server’s group. In lines 21 through 27 we loop forever listening for broadcast messages and printing them out.

Running this example produces the following output (output edited for brevity):

```
> java -cp target/iot-1.0-SNAPSHOT-jar-with-dependencies.jar \
          com.markwatson.iot.MulticastClient
received broadcast message: message 0
received broadcast message: message 1
 ...
received broadcast message: message 8
received broadcast message: message 9
```

### Wrap Up on IoT

Even though I personally have some concerns about security and privacy for IoT applications and products, I am enthusiastic about the possibilities of making our lives simpler and more productive with small networked devices. When we work and play we want as much as possible to not think about our computing devices so that we can concentrate on our activities.

I have barely scratched the surface on useful IoT technologies in this chapter but I hope that I have shown you network programming techniques that you can use in your projects (IoT and also networked game programming). As I write this book there are companies supplying IoT hardware development kits and deciding on one kit and software framework and creating your own projects is a good way to proceed.

## Natural Language Processing Using OpenNLP

I have worked in the field of Natural Language Processing (NLP) since the early 1980s. Many more people are interested in the field of NLP and the techniques have changed drastically. NLP has usually been considered part of the field of artificial intelligence (AI) and in the 1980s and 1990s there was more interest in symbolic AI, that is the manipulation of high level symbols that are meaningful to people because of our knowledge of the real world. As an example, the symbol **car** means something to us but to AI software this symbol in itself has no meaning except for possible semantic relationships to other symbols like **driver** and **road**.

There is still much work in NLP that deals with words as symbols: syntactic and semantic parsers being two examples. What has changed is a strong reliance on statistical and machine learning techniques. In this chapter we will use the open source (Apache 2 license) OpenNLP project that uses machine learning to create models of language. Currently, OpenNLP has support for Danish, German, English, Spanish, Portuguese, and Swedish. I include in the github repository some trained models for English that are used in the examples in this chapter. You can download models for other languages at the [web page for OpenNLP 1.5 models](http://opennlp.sourceforge.net/models-1.5/) (we are using version 1..6.0 of OpenNLP in this book which uses the version 1.5 models).

I use OpenNLP for some of the NLP projects that I do for my consulting customers. I have also written my own NLP toolkit [KBSPortal.com](http://kbsportal.com) that is a commercial product. For customers who can use the GPL license I sometimes use the [Stanford NLP libraries](http://nlp.stanford.edu/) that, like OpenNLP, are written in Java.

The following figure shows the project for this chapter in the Community Edition of IntelliJ:

![IntelliJ project view for the examples in this chapter](images/00004.jpeg)

IntelliJ project view for the examples in this chapter

We will use pre-trained models for tokenizing text, recognizing the names of organizations, people, locations, and parts of speech for words in input text. We will also train a new model (the file opennlp/models/en-newscat.bin in the github repository) for recognizing the category of input text. The section on training new maximum entropy classification models using your own training data is probably the material in this chapter that you will use the most in your own projects. We will train one model to recognize the categories of **COMPUTERS**, **ECONOMY**, **HEALTH**, and **POLITICS**. You should then have the knowledge for training your own models using your own training texts for the categories that you need for your applications. We will also use both some pre-trained models that are included with the OpenNLP distribution and the classification mode that we will soon create in the next chapter when we learn how to perform scalable machine learning algorithms using the Apache Spark platform where we look at techniques for processing very large collections of text to discover information.

After building a classification model we finish up this chapter with an interesting topic: statistically parsing sentences to discover the most probable linguistic structure of each sentence in input text. We will not use parsing in the rest of this book so you may skip the last section of this chapter if you are not currently interested in parsing sentences into linguistic components like noun and verp phrases, proper nouns, nouns, adjectives, etc.

### Using OpenNLP Pre-Trained Models

Assuming that you have cloned the github repository for this book, you can fetch the maven dependencies, compile the code, and run the unit tests using the command:

```
1     mvn clean build test
```

The model files, including the categorization model you will learn to build later in this chapter, are found in the subdirectory **models**. The unit tests in src/test/java/com/markwatson/opennlp/NLPTest.java provide examples for using the code we develop in this chapter. The Java example code for tokenization (splitting text into individual words), splitting sentences, and recognizing organizations, locations, and people in text is all in the Java class **NLP**. You can look at the source code in the repository for this book. Here I will just show a few snippets of the code to make clear how to load and use pre-trained models.

I use static class initialization to load the model files:

```
 1   static public Tokenizer tokenizer = null;
 2   static public SentenceDetectorME sentenceSplitter = null;
 3   static POSTaggerME tagger = null;
 4   static NameFinderME organizationFinder = null;
 5   static NameFinderME locationFinder = null;
 6   static NameFinderME personNameFinder = null;
 7 
 8   static {
 9 
10     try {
11       InputStream organizationInputStream =
12 	    new FileInputStream("models/en-ner-organization.bin");
13       TokenNameFinderModel model =
14 	    new TokenNameFinderModel(organizationInputStream);
15       organizationFinder = new NameFinderME(model);
16       organizationInputStream.close();
17 
18       InputStream locationInputStream =
19 	    new FileInputStream("models/en-ner-location.bin");
20       model = new TokenNameFinderModel(locationInputStream);
21       locationFinder = new NameFinderME(model);
22       locationInputStream.close();
23 
24       InputStream personNameInputStream =
25 	    new FileInputStream("models/en-ner-person.bin");
26       model = new TokenNameFinderModel(personNameInputStream);
27       personNameFinder = new NameFinderME(model);
28       personNameInputStream.close();
29 
30       InputStream tokienizerInputStream =
31 	    new FileInputStream("models/en-token.bin");
32       TokenizerModel modelTokenizer = new TokenizerModel(tokienizerInputStream);
33       tokenizer = new TokenizerME(modelTokenizer);
34       tokienizerInputStream.close();
35 
36       InputStream sentenceInputStream =
37 	    new FileInputStream("models/en-sent.bin");
38       SentenceModel sentenceTokenizer = new SentenceModel(sentenceInputStream);
39       sentenceSplitter = new SentenceDetectorME(sentenceTokenizer);
40       tokienizerInputStream.close();
41 
42       organizationInputStream = new FileInputStream("models/en-pos-maxent.bin");
43       POSModel posModel = new POSModel(organizationInputStream);
44       tagger = new POSTaggerME(posModel);
45 
46     } catch (IOException e) {
47       e.printStackTrace();
48     }
49   }
```

The first operation that you will usually start with for processing natural language text is breaking input text into individual words and sentences. Here is the code for using the tokenizing code that separates text stored as a Java String into individual words:

```
1   public static String[] tokenize(String s) {
2     return tokenizer.tokenize(s);
3   }
```

Here is the similar code for breaking text into individual sentences:

```
1   public static String[] sentenceSplitter(String s) {
2     return sentenceSplitter.sentDetect(s);
3   }
```

Here is some sample code to use **sentenceSplitter**:

```
1     String sentence =
2       "Apple Computer, Microsoft, and Google are in the " +
3       " tech sector. Each is very profitable.";
4     String [] sentences = NLP.sentenceSplitter(sentence);
5     System.out.println("Sentences found:\n" + Arrays.toString(sentences));
```

In line 4 the static method **NLP.sentenceSplitter** returns an array of strings. In line 5 I use a common Java idiom for printing arrays by using the static method **Arrays.toString** to convert the array of strings into a **List<String>** object. The trick is that the **List** class has a **toString** method that formats list nicely for printing.

Here is the output of this code snippet (edited for page width and clarity):

```
1 Sentences found:
2   ["Apple Computer, Microsoft, and Google are in the tech sector.",
3    "Each is very profitable."]
```

The code for finding organizations, locations, and people’s names is almost identical so I will only show the code in the next listing for recognizing locations. Please look at the methods **companyNames** and **personNames** in the class **com.markwatson.opennlp.NLP** to see the implementations for finding the names of companies and people.

```
 1   public static Set<String> locationNames(String text) {
 2     return locationNames(tokenizer.tokenize(text));
 3   }
 4 
 5   public static Set<String> locationNames(String tokens[]) {
 6     Set<String> ret = new HashSet<String>();
 7     Span[] nameSpans = locationFinder.find(tokens);
 8     if (nameSpans.length == 0) return ret;
 9     for (int i = 0; i < nameSpans.length; i++) {
10       Span span = nameSpans[i];
11       StringBuilder sb = new StringBuilder();
12       for (int j = span.getStart(); j < span.getEnd(); j++)
13         sb.append(tokens[j] + " ");
14       ret.add(sb.toString().trim().replaceAll(" ,", ","));
15     }
16     return ret;
17   }
```

The public methods in the class **com.markwatson.opennlp.NLP** are overriden to take either a single string value which gets tokenized inside of the method and also a method that takes as input text that has already been tokenized into a **String tokens[]** object. In the last example the method starting on line 1 accepts an input string and the overriden method starting on line 5 accepts an array of strings. Often you will want to tokenize text stored in a single input string into tokens and reuse the tokens for calling several of the public methods in **com.markwatson.opennlp.NLP** that can take input that is already tokenized. In line 2 we simply tokenize the input text and call the method that accepts tokenized input text.

In line 6 we create a **HashSet<String>** object that will hold the return value of a set of location names. The **NameFinderME** object **locationFinder** returns an array of **Span** objects. The **SPan class is used to represnt a sequence of adjacent words. The **Span** class has a public static attribute **length** and instance methods **getstart** and **getEnd** that return the indices of the beginning and ending (plus one) index of a span in the origianl input text.

Here is some sample code to use **locationNames** along with the output (edited for page width and clarity):

```
1    String sentence =
2      "Apple Computer is located in Cupertino, California and Microsoft " +
3      "is located in Seattle, Washington. He went to Oregon";
4    Set<String> names = NLP.locationNames(sentence);
5    System.out.println("Location names found: " + names);
6 
7 Location names found: [Oregon, Cupertino, Seattle, California, Washington]
```

Note that the pre-trained model does not recognize when city and state names are associated.

### Training a New Categorization Model for OpenNLP

The OpenNLP class **DoccatTrainer** can process specially formatted input text files and produce categorization models using maximum entropy which is a technique that handles data with many features. Features that are automatically extracted from text and used in a model are things like words in a document and word adjacency. Maximum entropy models can recognize multiple classes. In testing a model on new text data the probablilities of all possible classes add up to the value 1 (this is often refered to as “softmax”). For example we will be training a classifier on four categories and the probablilities of these categories for some test input text add up to the value of one:

```
[[COMPUTERS, 0.1578880260493374], [ECONOMY, 0.2163099374638936],
 [HEALTH, 0.35546925520388845], [POLITICS, 0.27033278128288035]]
```

The format of the input file for training a maximum entropy classifier is simple but has to be correct: each line starts with a category name, followed by sample text for each category which must be **all** **on** **one** **line**. Please note that I have already trained the model producing the model file **models/en-newscat.bin** so you don’t need to run the example in this section unless you want to regenerate this model file.

The file sample_category_training_text.txt contains four lines, defining four categories. Here are two lines from this file (I edited the following to look better on the printed page, but these are just two lines in the file):

```
COMPUTERS Computers are often used to access the Internet and meet basic busines\
s functions.
ECONOMY The Austrian School (also known as the Vienna School or the Psychologica\
l School ) is a Schools of economic thought|school of economic thought that emph\
asizes the spontaneous organizing power of the price mechanism.
```

Here is one training example each for the categories COMPUTERS and ECONOMY.

You must format the training file perfectly. As an example, if you have empty (or blank) lines in your input training file then you will get an error like:

```
Computing event counts...  java.io.IOException: Empty lines, or lines with
                           only a category string are not allowed!
```

The OpenNLP documentation has examples for writing custom Java code to build models but I usually just use the command line tool; for example:

```
bin/opennlp DoccatTrainer -model models/en-newscat.bin -lang en \
                          -data sample_category_training_text.txt \
                          -encoding UTF-8
```

The model is written to the relative file path models/en-newscat.bin. The training file I am using is tiny so the model is trained in a few seconds. For serious applications, the more training text the better! By default the **DoccatTrainer** tool uses the default text feature generator which uses word frequencies in documents but ignores word ordering. As I mention in the next section, I sometimes like to mix word frequency feature generation with 2gram (that is, frequencies of two adjacent words). In this case you cannot simply use the **DoccatTrainer** command line tool. You need to write a little Java code yourself that you can plug another feature generator into using the alternative API:

```
public static DoccatModel train(String languageCode,
                                ObjectStream<DocumentSample> samples,
                                int cutoff, int iterations,
                                FeatureGenerator... featureGenerators)
```

As I also mention in the next section, the last argument would look like:

```
public DocumentCategorizerME(DoccatModel model,
           new FeatureGenerator[]{new BagOfWordsFeatureGenerator(),
                                  new NGramFeatureGenerator()});
```

For most purposes the default word frequency (or bag of words) feature generator is probably OK so using the command line tool is a good place to start. Here is the output from running the **DoccatTrainer** command line tool:

```
> bin/opennlp DoccatTrainer -model models/en-newscat.bin -lang en \
                            -data sample_category_training_text.txt \
                            -encoding UTF-8
Indexing events using cutoff of 5

	Computing event counts...  done. 4 events
	Indexing...  done.
Sorting and merging events... done. Reduced 4 events to 4.
Done indexing.
Incorporating indexed data for training...  
done.
	Number of Event Tokens: 4
	    Number of Outcomes: 4
	  Number of Predicates: 153
...done.
Computing model parameters ...
Performing 100 iterations.
  1:  ... loglikelihood=-5.545177444479562	0.25
  2:  ... loglikelihood=-4.730232204542369	0.5
  3:  ... loglikelihood=-4.232192673282495	0.75
   ...
 98:  ... loglikelihood=-0.23411803835475453	1.0
 99:  ... loglikelihood=-0.23150121909902377	1.0
100:  ... loglikelihood=-0.22894028845170055	1.0
Writing document categorizer model ... done (0.041s)

Wrote document categorizer model to
path: /Users/mark/power-java/opennlp/models/en-newscat.bin
```

We will use our new trained model file **en-newscat.bin** in the next section.

**Please** **note** that in this simple example I used very little data, just a few hundred words for each training category. I have used the OpenNLP maximum entropy library on various projects, mostly to good effect, but I used many thousands of words for each category. The more data, the better.

### Using Our New Trained Classification Model

The code that uses the model we trained in the last section is short enough to list in its entirety:

```
 1 package com.markwatson.opennlp;
 2 
 3 import opennlp.tools.doccat.DoccatModel;
 4 import opennlp.tools.doccat.DocumentCategorizerME;
 5 
 6 import java.io.*;
 7 import java.util.*;
 8 
 9 /**
10  * This program uses the maximum entropy model we trained
11  * using the instructions in the chapter on OpenNLP in the book.
12  */
13 
14 public class NewsClassifier {
15 
16   public static List<Pair<String,Double>> allRankedCategories(String text) {
17     DocumentCategorizerME aCategorizer = new DocumentCategorizerME(docCatModel);
18     double[] outcomes = aCategorizer.categorize(text);
19     List<Pair<String,Double>> results = new ArrayList<Pair<String, Double>>();
20     for (int i=0; i<outcomes.length; i++) {
21       results.add(new Pair<String, Double>(aCategorizer.getCategory(i), outcomes\
22 [i]));
23     }
24     return results;
25   }
26 
27   public static String bestCategory(String text) {
28     DocumentCategorizerME aCategorizer = new DocumentCategorizerME(docCatModel);
29     double[] outcomes = aCategorizer.categorize(text);
30     return aCategorizer.getBestCategory(outcomes);
31   }
32 
33   public static Pair<String,Float> classifyWithScore(String text) {
34     DocumentCategorizerME classifier = new DocumentCategorizerME(docCatModel);
35     double [] scores = classifier.categorize(text);
36     int num_categories = classifier.getNumberOfCategories();
37     if (num_categories > 0) {
38       String bestString =  classifier.getBestCategory(scores);
39       for (int i=0; i<num_categories; i++) {
40         if (classifier.getCategory(i).equals(bestString)) {
41           return new Pair<String,Float>(bestString, (float)scores[i]);
42         }
43       }
44     }
45     return new Pair<String,Float>("<no category>", 0f);
46   }
47   
48   static DoccatModel docCatModel = null;
49 
50   static {
51 
52     try {
53       InputStream modelIn = new FileInputStream("models/en-newscat.bin");
54       docCatModel = new DoccatModel(modelIn);
55     } catch (IOException e) {
56       e.printStackTrace();
57     }
58   }
59 }
```

In lines 33 through 42 we initialize the static data for an instance of the class **DoccatModel** that loads the model file created in the last section.

A new instance of the class **DocumentCategorizerME** is created in line 28 each time we want to classify input text. I called the one argument constructor for this class that uses the default feature detector. An alternative constructor is:

```
1 public DocumentCategorizerME(DoccatModel model,
2                              FeatureGenerator... featureGenerators)
```

The default feature generator is **BagOfWordsFeatureGenerator** which just uses word frequencies for classification. This is reasonable for smaller training sets as we used in the last section but when I have a large amount of training data available I prefer to combine **BagOfWordsFeatureGenerator** with **NGramFeatureGenerator**. You would use the constructor call:

```
1 public DocumentCategorizerME(DoccatModel model,
2            new FeatureGenerator[]{new BagOfWordsFeatureGenerator(),
3                                   new NGramFeatureGenerator()});
```

The following listings show interspersed both example code snippets for for using the **NewsClassifier** class followed by the output printed by each code snippet:

```
 String sentence = "Apple Computer, Microsoft, and Google are in the tech sec\
tor. Each is very profitable.";
    System.out.println("\nNew test sentence:\n\n" + sentence + "\n");
    String [] sentences = NLP.sentenceSplitter(sentence);
    System.out.println("Sentences found: " + Arrays.toString(sentences));

New test sentence:

Apple Computer, Microsoft, and Google are in the tech sector.
Each is very profitable.

Sentences found: [Apple Computer, Microsoft, and Google are in the tech sector.,
                  Each is very profitable.]
```

```
 sentence = "Apple Computer, Microsoft, and Google are in the tech sector.";
    Set<String> names = NLP.companyNames(sentence);
    System.out.println("Company names found: " + names);

Company names found: [Apple Computer, Microsoft]

    sentence = "Apple Computer is located in Cupertino, California and Microsoft\
 is located in Seattle, Washington. He went to Oregon";
    System.out.println("\nNew test sentence:\n\n" + sentence + "\n");
    Set<String> names1 = NLP.locationNames(sentence);
    System.out.println("Location names found: " + names1);

New test sentence:

Apple Computer is located in Cupertino, California and Microsoft is located in S\
eattle, Washington. He went to Oregon

Location names found: [Oregon, Cupertino, Seattle, California, Washington]
```

```
 sentence = "President Bill Clinton left office.";
    System.out.println("\nNew test sentence:\n\n" + sentence + "\n");
    Set<String> names2 = NLP.personNames(sentence);
    System.out.println("Person names found: " + names2);

New test sentence:

President Bill Clinton left office.

Person names found: [Bill Clinton]

    sentence = "The White House is often mentioned in the news about U.S. foreig\
n policy. Members of Congress and the President are worried about the next elect\
ion and may pander to voters by promising tax breaks. Diplomacy with Iran, Iraq,\
 and North Korea is non existent in spite of a worry about nuclear weapons. A un\
i-polar world refers to the hegemony of one country, often a militaristic empire\
. War started with a single military strike. The voting public wants peace not w\
ar. Democrats and Republicans argue about policy.";
    System.out.println("\nNew test sentence:\n\n" + sentence + "\n");
    List<Pair<String, Double>> results = NewsClassifier.allRankedCategories(sent\
ence);
    System.out.println("All ranked categories found: " + results);

New test sentence:

The White House is often mentioned in the news about  U.S. foreign policy. Membe\
rs of Congress and the President are worried about the next election and may pan\
der to voters by promising tax breaks. Diplomacy with Iran, Iraq, and North Kore\
a is non existent in spite of a worry about nuclear weapons. A uni-polar world r\
efers to the hegemony of one country, often a militaristic empire. War started w\
ith a single military strike. The voting public wants peace not war. Democrats a\
nd Republicans argue about policy.

All ranked categories found: [[COMPUTERS, 0.07257665117660535], [ECONOMY, 0.2355\
9821969425127], [HEALTH, 0.29907267186308945], [POLITICS, 0.39275245726605396]]
```

```
 sentence = "The food affects colon cancer and ulcerative colitis. There is s\
ome evidence that sex helps keep us healthy. Eating antioxidant rich foods may p\
revent desease. Smoking may raise estrogen levels in men and lead to heart failu\
re.";
    System.out.println("\nNew test sentence:\n\n" + sentence + "\n");
    String results2 = NewsClassifier.bestCategory(sentence);
    System.out.println("Best category found found (HEALTH): " + results2);
    List<Pair<String, Double>> results3 = NewsClassifier.allRankedCategories(sen\
tence);
    System.out.println("All ranked categories found (HEALTH): " + results3);
    System.out.println("Best category with score: " + NewsClassifier.classifyWit\
hScore(sentence));

New test sentence:

The food affects colon cancer and ulcerative colitis. There is some evidence tha\
t sex helps keep us healthy. Eating antioxidant rich foods may prevent desease. \
Smoking may raise estrogen levels in men and lead to heart failure.

Best category found found (HEALTH): HEALTH
All ranked categories found (HEALTH): [[COMPUTERS, 0.1578880260493374], [ECONOMY\
, 0.2163099374638936], [HEALTH, 0.35546925520388845], [POLITICS, 0.2703327812828\
8035]]
Best category with score: [HEALTH, 0.35546926]
```

### Using the OpenNLP Parsing Model

We will use the parsing model that is included in the OpenNLP distribution to parse English language input text. You are unlikely to use a statistical parsing model in your work but I think you will enjoy the material in the section. If you are more interested in practical techniques then skip to the next chapter that covers more machine learning techniques.

The following example code listing is long (68 lines) but I will explain the interesting parts after the listing:

```
 1 package com.markwatson.opennlp;
 2 
 3 import opennlp.tools.cmdline.parser.ParserTool;
 4 import opennlp.tools.parser.Parse;
 5 import opennlp.tools.parser.ParserModel;
 6 import opennlp.tools.parser.chunking.Parser;
 7 
 8 import java.io.FileInputStream;
 9 import java.io.IOException;
10 import java.io.InputStream;
11 
12 /**
13  * Experiments with the chunking parser model
14  */
15 public class ChunkingParserDemo {
16   public Parse[] parse(String text) {
17     Parser parser = new Parser(parserModel);
18     return ParserTool.parseLine(text, parser, 5);
19   }
20 
21   public void prettyPrint(Parse p) {
22     StringBuffer sb = new StringBuffer();
23     p.show(sb);
24     String s = sb.toString() + " ";
25     int depth = 0;
26     for (int i = 0, size = s.length() - 1; i < size; i++) {
27       if (s.charAt(i) == ' ' && s.charAt(i + 1) == '(') {
28         System.out.print("\n");
29         for (int j = 0; j < depth; j++) System.out.print("  ");
30       } else if (s.charAt(i) == '(') System.out.print(s.charAt(i));
31       else if (s.charAt(i) != ')' || s.charAt(i + 1) == ')')
32         System.out.print(s.charAt(i));
33       else {
34         System.out.print(s.charAt(i));
35         for (int j = 0; j < depth; j++) System.out.print("  ");
36       }
37       if (s.charAt(i) == '(') depth++;
38       if (s.charAt(i) == ')') depth--;
39     }
40     System.out.println();
41   }
42 
43   static ParserModel parserModel = null;
44 
45   static {
46 
47     try {
48       InputStream modelIn = new FileInputStream("models/en-parser-chunking.bin");
49       parserModel = new ParserModel(modelIn);
50     } catch (IOException e) {
51       e.printStackTrace();
52     }
53   }
54 
55   public static void main(String[] args) {
56     ChunkingParserDemo cpd = new ChunkingParserDemo();
57     Parse[] possibleParses =
58       cpd.parse("John Smith went to the store on his way home from work ");
59     for (Parse p : possibleParses) {
60       System.out.println("parse:\n");
61       p.show();
62       //p.showCodeTree();
63       System.out.println("\npretty printed parse:\n");
64       cpd.prettyPrint(p);
65       System.out.println("\n");
66     }
67   }
68 }
```

The OpenNLP parsing model is read from a file in lines 45 through 53. The static variable **parserModel** (instance of class **ParserModel**) if created in line 49 and used in lines 17 and 18 to parse input text. It is instructive to look at the intermediate calculation results. The value for variable parser defined in line 17 has a value of:

![Data in the parser model as seen in IntelliJ](images/00005.jpeg)

Data in the parser model as seen in IntelliJ

Note that the parser returned 5 results because we specified this number in line 18\. For a long sentence the parser generates a very large number of possible parses for the sentence and returns, in order of probability of being correct, the number of resutls we requested.

The OpenNLP chunking parser code prints out results in a flat list, one result on a line. This is difficult to read which is why I wrote the method **prettyPrint** (lines 21 through 41) to print the parse results indented. Here is the output from the last code example (the first parse shown is all on one line but line wraps in the following listing):

```
 1 parse:
 2 
 3 (TOP (S (NP (NNP John) (NNP Smith)) (VP (VBD went) (PP (TO to) (NP (DT the) (NN \
 4 store))) (PP (IN on) (NP (NP (NP (PRP$ his) (NN way)) (ADVP (NN home))) (PP (IN \
 5 from) (NP (NN work))))))))
 6 
 7 pretty printed parse:
 8 
 9 (TOP
10   (S
11     (NP
12       (NNP John)        
13       (NNP Smith))      
14     (VP
15       (VBD went)        
16       (PP
17         (TO to)          
18         (NP
19           (DT the)            
20           (NN store)))        
21       (PP
22         (IN on)          
23         (NP
24           (NP
25             (NP
26               (PRP$ his)                
27               (NN way))              
28             (ADVP
29               (NN home)))            
30           (PP
31             (IN from)              
32             (NP
33               (NN work))))))))
```

In the 1980s I spent much time on syntax level parsing. While the example in this section is a statistical parsing model I don’t find these models very relevant to my own work but I wanted to include a probalistic parsing example for completeness in this chapter.

OpenNLP is a great resource for Java programmers and its Apache 2 license is “business friendly.” If you can use software with a GPL license then please also look at the Stanford NLP libraries.

## Machine Learning Using Apache Spark

I have used Java for Machine Learning (ML) for nearly twenty years using my own code and also great open source projects like Wika, Mahout, and Mallet. For the material in this chapter I will use a relatively new open source machine learning library MLlib that is included in the Apache Spark project. Spark is similar to Hadoop in providing functionality for using multiple servers for processing massively large data sets. Spark preferentially deals with data in memory and can provide near real time analysis of large data sets.

We saw a specific use case of machine learning in the previous chapter on OpenNLP: building maximum entropy classification models. This chapter will introduce another good ML library. Machine learning is part of the fields of data science and artificial intelligence.

There are several steps involved in building applications with ML:

*   Understand what problems your organization has and what data is available to solve these problems. In other words, figure out where you should you spend your effort. You should also understand early in the process how it is that you will evaluate the usefulness and quality of the results.
*   Collecting data. This step might involve collecting numeric time series data from instruments; for example, to train regression models or collecting text for natural language processing ML projects as we saw in the last chapter.
*   Cleaning data. This might involve detecting and removing errors in data from faulty sensors or incomplete collection of text data from the web. In some cases data might be annotated (or labelled) in this step.
*   Integrating data from different sources and organizing it for experiments. Data that has been collected and cleaned might end up being used for multiple projects so it makes sense to organize it for ease of use. This might involve storing data on disk or cloud storage like S3 with meta data stored in a database. Meta data could include date of collection, data source, steps taken to clean the data, and references to models already build using this data.
*   **The** **main** **topic** **of** **this** **chapter:** analysing data and creating models with machine learning (ML). This will often be experimental with many different machine learning algorithms used for quick and dirty experiments. These fast experiments should inform you on which approach works best for this data set. Once you decide which ML algorithm to use you can spend the time to refine features in data used by learning algorithms and to tune model parameters. It is usually best, however, to first quickly try a few approaches before settling on one approach and then investing a lot of time in building a model.
*   Interpreting and using the results of models. Often models will be used to process other data sets to automatically label data (as we do in this chapter with text data from Wikipedia) or making predictions from new sources of time series numerical data.
*   Deploy training models as embedded parts of a larger system. This is an optional step - sometimes it is sufficient to use a model to understand a problem well enough to know how to solve it. Usually, however, a model will be used repeatadly, often automatically, as part of normal data processing and decision workflows. I will take some care in this chapter to indicate how to reuse models embedded in your Java applications.

In the examples in this book I have supplied test data with the example programs. Please keep in mind that although I have listed these steps for data mining and ML model building as a sequence of steps, in practice this is a very iterative process. Data collection and cleaning might be reworked after seeing preliminary results of building models using different algorithms. We might iteratively tune model parameters and also improve models by adding or removing the features in data that are used to build models.

What do I mean by “features” of data? For text data features can be: words in text, collections of adjacent words in text (ngrams), structure of text (e.g., taking advantage of HTML or other markup), punctuation, etc. For numeric data features might be minimum and maximum of data points in a sequence, features in frequency space (calculated by Fast Forier Transfroms (FFTs), sometimes as Power Spectral Density (PSD) which is a FFT with phase information in the data discarded), etc. Cleaning data means different things for different types of data. In cleaning text data we might segment text into sentences, perform word stemming (i.e., map words like “banking” or “banks” to their stem of root “bank”), sometimes we might want to convert all text to lower case, etc. For numerical data we might have to scale data attributes to a specific numeric range - we will do this later in this chapter when using the University of Wisconsin cancer data sets.

The previous seven steps that I outline are my view of the process of discovering information sources, processing the data, and producing actionable knowledge from data. Other acronyms that you are likely to run across is Knowledge Discovery in Data (KDD) and the CCC Big Data Pipeline which both use steps similar to those that I have just outlined.

There are, broadly speaking, four types of ML models:

*   Regression - predicts a numerical value. Inputs are numeric values.
*   Classification - predicts yes or no. Inputs are numeric values.
*   Clustering - partition a set of data items into disjoint sets. Data items might be text documents, numerical data sets from sensor readings, sets of structured data that might include text and numbers. Inputs must be converted to numeric values.
*   Recommendation - decision to recommend an object based on a user’s previous actions and/or by matching a user to other similar users to use other users’ actions.

You will see later when dealing with text that we need to convert words to numbers (each word is assigned a unique numeric ID). A document is represented by a sparse vector that has a non-empty element for each unique word index. Further, we can divide machine learning problems into two general types:

*   Supervised learning - input features used for training are labeled with the desired prediction. The example of supervised learning we will look at is building a regresion model using cancer symptom data to predict the malignancy vs. benign given a new input feature set.
*   Unsupervised learning - input features are not labeled. Examples of unsupervised learning that we will look at are: K-Means similar Wikipedia document clustering and using word2vec to find related words in documents.

My goal in this chapter is to introduce you to practical techniques using Spark and machine learning algorithms. After you have worked through the material I recommend reading through the Spark documentation to see a wider variety of available models to use. Also consider taking Andrew Ng’s excellent [Machine Learning class](https://www.coursera.org/learn/machine-learning).

**Scaling** **Machine** **Learning**

While the ability to scale data mining and ML operations for very large data sets is sometimes important, for development and for working through the examples in this chapter you do not need to set up a cluster of servers to run Spark. We will use Spark in developer mode and you can run the examples on your laptop. It would be best if your laptop has at least 2 gigabytes of RAM to run the ML examples. The important thing to remember is that the techniques that you learn in this chapter can be scaled to very large data sets as needed without modifying your application source code.

The Apache Spark project originated at the University of California at Berkeley. Spark has client support for Java, Scala, and Python. The examples in this chapter will all be in Java. If you are a Scala developer, after working through through the examples you might want to take a look at the Scala Spark documentation since Spark is written in Scala and Scala has the best client support. The Python Spark and MLlib APIs are also very nice to use so if you are a Python developer you should check out this Python support.

Spark is an evolutionary step forward from using map reduce systems like Hadoop or Google’s Map Reduce. In following through the examples in this chapter you will likely think that you could accomplish the same effect with less code and runtime overhead. For dealing with small amounts of data that is certainly true but, just like using Hadoop, a little more verbosity in the code gives you the ability to scale your applications over large data sets. We put up with extra complexity for scalability. Spark has utility classes for reading and transforming data that make the example programs simpler than writing code yourself for importing data.

I suggest that you download the source code for the Spark 1.5.0 distribution from the [Apache Spark download page](https://spark.apache.org/downloads.html) since there are many example programs that you can use for ideas and for reference. The Java client examples in the Spark machine learning library MLlib can be found in the directory:

```
spark-1.5.0/examples/src/main/java/org/apache/spark/examples/MLlib/
```

Where the directory **spark-1.5.0** was created when you downloaded Spark version 1.5.0.

These examples use provided data files that provide numerical data, each line specifies a local Spark vector data type. The first K-Means clustering example in this chapter is derived from a MLlib example included with the Spark distribution. The second K-Means example that clusters Wikipedia articles is quite a bit different because we need to write new code to convert text into numeric feature vectors. I provide sample text that I manually selected from Wikipedia articles.

We will start this chapter by showing you how to set up Spark and MLlib on your laptop and then look at a simple “Hello World” introductory type program for generating word counts from input text. We will then implement logistic regression and also take a brief look at the JavaKMeans example program from the Spark MLlib examples and use it to understand the requirement for reducing data to a set of numeric feature vectors. We will then develop examples using Wikipedia data and this will require writing custom converters for plain text to numeric feature vectors.

### Setting Up Spark On Your Laptop

Assuming that you have cloned the github project for this book, the Spark examples are in the sub-directory machine_learning_spark. The maven pom.xml file contains the Spark dependencies. You can install these dependencies using:

```
mvn clean install
```

There are four examples in this chapter. If you want to skip ahead and run the code before reading the rest of the chapter, run each maven test separately:

```
mvn test -Dtest=HelloTest
mvn test -Dtest=KMeansTest
mvn test -Dtest=WikipediaKMeansTest
mvn test -Dtest=LogisticRegressionTest
mvn test -Dtest=SvmClassifierTest
```

Spark has all of Hadoop as a dependency because Spark is able to interact with Hadoop and Hadoop file systems. It will take a short while to download all of these dependencies but that only needs to be done one time. To augment the material in this chapter you can refer to the [Spark Programming Guide](https://spark.apache.org/docs/latest/programming-guide.html). We will also be using material in the [Spark Machine Learning Library (MLlib) Guide](https://spark.apache.org/docs/1.5.0/mllib-guide.html).

The following figure shows the project for this chapter in the Community Edition of IntelliJ:

![IntelliJ project view for the examples in this chapter](images/00006.jpeg)

IntelliJ project view for the examples in this chapter

### Hello Spark - a Word Count Example

The word count example is frequently used to introduce map reduce and I will also use it here for a “hello world” type simple Spark example. In the following listing, lines 3 through 6 import the required classes. In lines 3 and 4 “RDD” stands for Resilient Distributed Datasets (RDD). Spark was written in Scala so we will sometimes see Java wrapper classes that are recognizable with the prefix “Java.” Each RDD is a collection of objects of some type that can be distributed across multiple servers in a Spark cluster. RDDs are fault tolerant and there is sufficient information in a Spark cluster to recreate any lost data due to a server or software failure.

```
 1 package com.markwatson.machine_learning;
 2 
 3 import org.apache.spark.api.java.JavaPairRDD;
 4 import org.apache.spark.api.java.JavaRDD;
 5 import org.apache.spark.api.java.JavaSparkContext;
 6 import scala.Tuple2;
 7 
 8 import java.util.Arrays;
 9 import java.util.List;
10 import java.util.Map;
11 
12 public class HelloSpark {
13 
14   static private List<String> tokenize(String s) {
15     return Arrays.asList(s.replaceAll("\\.", " \\. ").replaceAll(",", " , ")
16         .replaceAll(";", " ; ").split(" "));
17   }
18 
19   static public void main(String[] args) {
20     JavaSparkContext sc = new JavaSparkContext("local", "Hello Spark");
21 
22     JavaRDD<String> lines = sc.textFile("data/test1.txt");
23     JavaRDD<String> tokens = lines.flatMap(line -> tokenize(line));
24     JavaPairRDD<String, Integer> counts =
25         tokens.mapToPair(token ->
26 			 new Tuple2<String, Integer>(token.toLowerCase(), 1))
27               .reduceByKey((count1, count2) -> count1 + count2);
28     Map countMap = counts.collectAsMap();
29     System.out.println(countMap);
30     List<Tuple2<String, Integer>> collection = counts.collect();
31     System.out.println(collection);
32   }
33 }
```

Lines 14 through 17 define the simple **tokenizer** method that takes English text and maps it to a list of strings. I broke this out into a separate method as a reminder that punctuation needs to be handled and breaking it in to a separate method makes it easier for you to experiment with custom tokenization that might be needed for your particular text input files. One possibility is using the OpenNLP tokenizer model that we used in the last chapter. For example, we would want the string “tree.” to be tokenized as [“tree”, “.”] and not [“tree.”]. This method is used in line 23 and is called for each line in the input text file.

In this example in line 22 we are reading a local text file “data/test1.txt” but in general the argument to JavaSparkContext.textFile() can be a URI specifying a file on a local Hadoop file system (HDFS), an Amazon S3 object, of a Cassandra file system. Pay some attention to the type of the variable **lines** defined in line 22: the type JavaRDD<string> specifies an RDD collection where the distributed objects are strings.</string>

The code in lines 29 through 32 is really not very complicated if we parse it out a bit at a time. The type of **counts** is a RDD distributed collection where each object in the collection is a pair of string and integer values. The code in lines 25 through 27 takes each token in the original text file and produces a pair (or Tuple2) values consisting of the token string and the integer 1\. As an example, an array of three tokens like:

```
1     ["the", "dog", "ran"]
```

would be converted to an array of three pairs like:

```
1     [["the", 1], ["dog", 1], ["ran", 1]]
```

The statement in line 28 is uses the method **reduceByKey** which partitions the array of pairs by unique key value (the key being the first element in each pair) and sums the values for each matching key. The rest of this example shows two ways to extract data from an distributed RDD collection back to a Java process as local data. In line 29 we are pulling the collection of word counts into a Java **Map<String,Integer>** collection and in line 31 we are doing the same thing but pulling data into a list of Scala tuples. Here is what the output of the program looks like:

```
1     {dog=2, most=1, of=1, down=1, rabbit=1, slept=1, .=2, the=5, street=1,
2      chased=1, day=1}
3     [(most,1), (down,1), (.,2), (street,1), (day,1), (chased,1), (dog,2),
4      (rabbit,1), (of,1), (slept,1), (the,5)]
```

### Introducing the Spark MLlib Machine Learning Library

As I write this Chapter in the fall of 2015, the Spark MLlib library is at version 1.5 and under development. When you experiment with the examples first try using version 1.5\. I will update the git repository for this book periodically and I will try to keep the code examples compatible with the current stable versions of Spark and MLlib.

The examples in the following sections show how to apply the MLlib library to problems of logistic regression, using the K-Means algoirthm to cluster similar documents, and using the word2vec algorithm to find strong associations between words in documents.

### MLlib Logistic Regression Example Using University of Wisconsin Cancer Database

We will use supervised learning in this section to build a regresion model that maps a numeric feature vector of symptoms to a numeric value where larger values close to one indicate malignancy and smaller values closer to zero indicate benign.

MLlib supports three types of linear models: Support Vector Machine (SVM), logistic regression (models for membership in one or more classes or categories), and linear regression (models that model outputs for a class as a floating point number in the range [0..1]). The Spark MLlib documentation (http://spark.apache.org/docs/latest/mllib-linear-methods.html) on these three linear models is very good and their sample programs are similar so it is easy enough to switch the type of linear model that you use.

We will use logistic regression for the example in this section. Andrew Ng, in his excellent [Machine Learning class](https://www.coursera.org/learn/machine-learning) said that the first model he tries when starting a new problem is a linear model. We will repeat this example in the next section using SVM instead of logistic regression.

If you read my book [Build Intelligent Systems with Javascript](https://leanpub.com/aijavascript) the training and test dataset used in this section will look familiar: [University of Wisconsin breast cancer data set](http://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29).

From the University of Wisconsin web page, here are the attributes with their allowed ranges in this data set:

```
- 0 Sample code number            integer
- 1 Clump Thickness               1 - 10
- 2 Uniformity of Cell Size       1 - 10
- 3 Uniformity of Cell Shape      1 - 10
- 4 Marginal Adhesion             1 - 10
- 5 Single Epithelial Cell Size   1 - 10
- 6 Bare Nuclei                   1 - 10
- 7 Bland Chromatin               1 - 10
- 8 Normal Nucleoli               1 - 10
- 9 Mitoses                       1 - 10
- 10 Class (2 for benign, 4 for malignant)
```

The file data/university_of_wisconson_data_.txt contains raw data. We will use this sample data set with two changes: we clean it by removing the sample code column and the next 9 values are scaled to the range [0..1] and the class is mapped to 0 (benign) or 1 (malignant). So, our input features are scaled (values between [0 and 1] numerical values indicating clump thickness, uniformity of cell size, etc. The label that specifies what the desired prediction is the class (2 for for benign, 4 for malignant which we scale to 0 or 1)). In the following listing data is read from the training file and scaled in lines 27 through 44\. Here I am using some utility methods provided by MLlib. In line 28 I am using the method **JavaSparkContext.textFile** to read the text file into what is effectively a list of strings (one string per input line). Lines 29 through 44 is creating a list of instances of the class **LabeledPoint** which contains a training label with associated numeric feature data. The container class **JavaRDD** acts as a list of elements that can be automatically managed across a Spark server cluster. When in development mode with a local **JavaSparkContext** everything is running in a single JVM so an instance of class **JavaRDD** behaves a lot like a simple in-memory list.

```
 1 package com.markwatson.machine_learning;
 2 
 3 import org.apache.spark.api.java.JavaDoubleRDD;
 4 import org.apache.spark.api.java.JavaRDD;
 5 import org.apache.spark.api.java.JavaSparkContext;
 6 import org.apache.spark.api.java.function.Function;
 7 import org.apache.spark.mllib.linalg.Vectors;
 8 import org.apache.spark.mllib.regression.LabeledPoint;
 9 import org.apache.spark.mllib.regression.LinearRegressionModel;
10 import org.apache.spark.mllib.regression.LinearRegressionWithSGD;
11 import scala.Tuple2;
12 
13 public class LogisticRegression {
14 
15   public static double testModel(LinearRegressionModel model,
16                                  double [] features) {
17     org.apache.spark.mllib.linalg.Vector inputs = Vectors.dense(features);
18     return model.predict(inputs);
19   }
20 
21   public static void main(String[] args) {
22     JavaSparkContext sc =
23 	  new JavaSparkContext("local",
24 	                       "University of Wisconson Cancer Data");
25 
26     // Load and parse the data
27     String path = "data/university_of_wisconson_data_.txt";
28     JavaRDD<String> data = sc.textFile(path);
29     JavaRDD<LabeledPoint> parsedData = data.map(
30         new Function<String, LabeledPoint>() {
31           public LabeledPoint call(String line) {
32             String[] features = line.split(",");
33             double label = 0;
34             double[] v = new double[features.length - 2];
35             for (int i = 0; i < features.length - 2; i++)
36               v[i] = Double.parseDouble(features[i + 1]) * 0.09;
37             if (features[10].equals("2"))
38               label = 0; // benign
39             else
40               label = 1; // malignant
41             return new LabeledPoint(label, Vectors.dense(v));
42           }
43         }
44     );
45     // Split initial RDD into two data sets with 70% training data
46     // and 30% testing data (13L is a random seed):
47     JavaRDD<LabeledPoint>[] splits =
48 	  parsedData.randomSplit(new double[]{0.7, 0.3}, 13L);
49     JavaRDD<LabeledPoint> training = splits[0].cache();
50     JavaRDD<LabeledPoint> testing = splits[1];
51     training.cache();
52 
53     // Building the model
54     int numIterations = 100;
55     final LinearRegressionModel model =
56         LinearRegressionWithSGD.train(JavaRDD.toRDD(training),
57 		                              numIterations);
58 
59     // Evaluate model on training examples and compute training error
60     JavaRDD<Tuple2<Double, Double>> valuesAndPreds = testing.map(
61         new Function<LabeledPoint, Tuple2<Double, Double>>() {
62           public Tuple2<Double, Double> call(LabeledPoint point) {
63             double prediction = model.predict(point.features());
64             return new Tuple2<Double, Double>(prediction, point.label());
65           }
66         }
67     );
68     double MSE = new JavaDoubleRDD(valuesAndPreds.map(
69         new Function<Tuple2<Double, Double>, Object>() {
70           public Object call(Tuple2<Double, Double> pair) {
71             return Math.pow(pair._1() - pair._2(), 2.0);
72           }
73         }
74     ).rdd()).mean();
75     System.out.println("training Mean Squared Error = " + MSE);
76 
77     // Save and load model and test:
78     model.save(sc.sc(), "generated_models");
79     LinearRegressionModel loaded_model =
80 	  LinearRegressionModel.load(sc.sc(), "generated_models");
81     double[] malignant_test_data_1 =
82 	  {0.81, 0.6, 0.92, 0.8, 0.55, 0.83, 0.88, 0.71, 0.81};
83     System.err.println("Should be malignant: " + 
84 	                    testModel(loaded_model, malignant_test_data_1));
85     double[] benign_test_data_1 =
86 	  {0.55, 0.25, 0.34, 0.31, 0.29, 0.016, 0.51, 0.01, 0.05};
87     System.err.println("Should be benign (close to 0.0): " +
88                        testModel(loaded_model, benign_test_data_1));
89   }
90 }
```

Once the data is read and converted to numeric features the next thing we do is to randomly split the data in the input data file into two separate sets: one for training and one for testing our model after training. This data splitting is done in lines 47 and 48\. Line 49 copies the training data and requests to the current Spark context to try to keep this data cached in memory. In line 50 we copy the testing data but don’t specify that the test data needs to be cached in memory.

There are two sections of code left to discuss. In lines 53 through 75 I am training the model, saving the model to disk, and testing the model while it is still in memory. In lines 77 through 89 I am reloading the saved model from disk and showing how to use it with two new numeric test vectors. This last bit of code is meant as a demonstration of embedding a model in Java code and using it.

The following three lines of code are the output of this example program. The first line of output indicates that the error for training the model is low. The last two lines show the output from reloading the model from disk and using it to evaluate two new numeric feature vectors:

```
Test Data Mean Squared Error = 0.050140726106582885
Should be malignant (close to 1.0): 1.1093117757012294
Should be benign (close to 0.0): 0.29575663511929096
```

This example shows a common pattern: reading training data from disk, scaling it, and building a model that is saved to disk for later use. This program can almost be reused as-is for new types of training data. You should just have to modify lines 27 through 44.

### MLlib SVM Classification Example Using University of Wisconsin Cancer Database

The example in this section is very similar to that in the last section. The only differences are using the MLlib class **SvmClassifier** instead of the class **LogisticRegression** that we used in the last section and setting the number of training iterations to 500\. We are using the same University of Wisconsin cancer data set in this section - refer to the previous section for a discusion of this data set.

Since the code for this section is very similar to the last example I will not list it. Please refer to the source file **SvmClassifier.java** and the test file **SvmClassifier.java** in the github repository for this book. In the repository subdirectory **machine_learning_spark** you will need to remove the model files generated when running the example in the previous section before running this example:

```
rm -r -f generated_models/*
mvn test -Dtest=SvmClassifierTest
```

The output for this example will look like:

```
Test Data Mean Squared Error = 0.22950819672131167
Should be malignant (close to 1.0): 1.0
Should be benign (close to 0.0): 0.0
```

Note that the test data mean square error is larger than the value of 0.050140726106582885 that we obtained using logistic regression in the last section.

### MLlib K-Means Example Program

We will use unsupervised learning in this section, specifically the K-Means clustering algorithm. This clustering process partitions inputs into groups that share common features. Later in this chapter we will look at an example where our input will be some randomly chosen Wikipedia articles.

K-Means analysis is useful for many types of data where you might want to cluster members of some set into different sub-groups. As an example, you might be a biologist studying fish. For each species of fish you might have attributes like length, weight, location, fresh/salt water, etc. You can use K-Means to divide fish specifies into similar sub-groups.

If your job deals with marketing to people on social media, you might want to cluster people (based on what attributes you have for users of social media) into sub-groups. If you have sparse data on some users, you might be able to infer missing data on other users.

The simple example in this section uses numeric feature vectors. Keep in mind, however our goal of processing Wikipedia text in a later section. In the next section we will see how to convert text to feature vectors, and finally, in the section after that we will cluster Wikipedia articles.

Implementing K-Means is simple but using the MLlib implementation has the advantage of being able to process very large data sets. The first step in calculating K-Means is choosing the number of desired clusters NC. The calculate NC cluster centers randomly. We then perform an inner loop until either cluster centers stop changing or a specified number of iteractions is done:

*   For each data point, assign it to the cluster center closest to it.
*   for each cluster center, move the center to the average location of the data points in that cluster

In practice you will repeat this clustering process many times and use the cluster centers with the minimum distortion. The distortion is the sum of the squares of the distances from each data point in a cluster to the final cluster center.

So before we look at the Wikipedia example (clustering Wikipedia articles) later in this chapter, I want to first review the **JavaKMeans.java** example from the Spark MLlib examples directory to see how to perform K-Means clustering on sample data:

```
spark-1.5.0/examples/src/main/java/org/apache/spark/examples/mllib/
```

This is a very simple example that already uses numeric data. I copied the **JavaKMeans.java** file (changing the package name) to the github repository for his book.

The most important thing in this section that you need to learn is the required types of input data: vectors of double size floating point numbers. Each sample of data needs to be converted to a numeric feature vector. For some applications this is easy. As a hypothetical example, you might have a set of features that measure weather in your town: low temperature, high temperature, average temperature, percentage of sunshine during the day, and wind speed. All of these features are numeric and can be used as a feature vector as-is. You might have 365 samples for a given year and would like to cluster the data to see which days are similar to each other.

What if in this hypothetical example one of the features was a string representing the month? One obvious way to convert the data would be to map “January” to 1, “February” to 2, etc. We will see in the next section when we cluster Wikipedia articles that converting data to a numeric feature vector is not always so easy.

We will use the tiny sample data set provided with the MLlib KMeans example:

```
0.0 0.0 0.0
0.1 0.1 0.1
0.2 0.2 0.2
9.0 9.0 9.0
9.1 9.1 9.1
9.2 9.2 9.2
```

Here we have 6 samples and each sample has 3 features. From inspection, it looks like there are two clusters of data: the first three rows are in one cluster and the last three rows are in a second cluster. The order that feature vectors are processed in is not important; the samples in this file are organized so you can easily see the two clusters. When we run this sample program asking for two clusters we get:

```
Cluster centers:
 [9.1,9.1,9.1]
 [0.1,0.1,0.1]
```

We will go through the code in the sample program since it is the same general pattern we use throughout the rest of this chapter. Here is a slightly modified version of **JavaKMeans.java** with a few small changes from the version in the MLLib examples directory:

```
 1 public final class JavaKMeans {
 2 
 3   private static class ParsePoint implements Function<String, Vector> {
 4     private static final Pattern SPACE = Pattern.compile(" ");
 5 
 6     @Override
 7     public Vector call(String line) {
 8       String[] tok = SPACE.split(line);
 9       double[] point = new double[tok.length];
10       for (int i = 0; i < tok.length; ++i) {
11         point[i] = Double.parseDouble(tok[i]);
12       }
13       return Vectors.dense(point);
14     }
15   }
16 
17   public static void main(String[] args) {
18 
19     String inputFile = "data/kmeans_data.txt";
20     int k = 2; // two clusters
21     int iterations = 10;
22     int runs = 1;
23 
24     JavaSparkContext sc = new JavaSparkContext("local", "JavaKMeans");
25     JavaRDD<String> lines = sc.textFile(inputFile);
26 
27     JavaRDD<Vector> points = lines.map(new ParsePoint());
28 
29     KMeansModel model = KMeans.train(points.rdd(), k, iterations, runs,
30 	                                 KMeans.K_MEANS_PARALLEL());
31 
32     System.out.println("Cluster centers:");
33     for (Vector center : model.clusterCenters()) {
34       System.out.println(" " + center);
35     }
36     double cost = model.computeCost(points.rdd());
37     System.out.println("Cost: " + cost);
38 
39     sc.stop();
40   }
41 }
```

The inner class **ParsePoint** is used to generate a single numeric feature vector given input data. In this simple case the input data is a string like “9.1 9.1 9.1” that needs to be tokenized and each token converted to a double floating point number. This inner class in the Wikipedia example will be much more complex.

In line 24 we are creating a Spark execution context. In all of the examples in this chapter we use a “local” context which means that Spark will run inside the same JVM as our example code. In production the Spark context could access a Spark cluster utilizing multiple servers.

Lines 25 and 27 introduce the use of the class **JavaRDD** which is the Java version of the Scala Ricj Data Definition class used internally to implement Spark. This data class can live inside a single JVM when we use a local Spark context or be spread over many servers when using a Spark server cluster. In line 25 we are reading the input strings and in line 27 we are using the inner class **ParsePoint** to convert the input text lines to numeric feature vectors.

Lines 29 and 30 use the static method **KMeans.train** to create a trained clustering model. Lines 33 through 35 print out the clusers (listing of the output was shown earlier in this section).

This simple example along with the “Hello Spark” example in the last section has shown you how to run Spark on your laptop in developers mode. In the next section we will see how to convert input text into a numeric feature vector.

### Converting Text to Numeric Feature Vectors

In this section I develop a utility class **TextToSparseVector** that converts a set of text documents into sparse numeric feature vectors. Spark provides dense vector classes (like an array) and sparse vector classes that contain index and value pairs. For text feature vectors, In this example we will have a unique feature ID for each unique word stem (or word root) in all of the combined input documents.

We start by reading in all of the input text and forming a Map where the keys are word stems and the values are unique IDs. Any given index document will be represented with a psarse vector. For each word, the word’s stem is represented by a unique ID. The vector element at the integer ID value is set. A short document with 100 unique words would have 100 elements of the sparse vector set.

Listing of the class **TextToSparseVector**:

```
 1 package com.markwatson.machine_learning;
  2 
  3 import java.nio.file.Files;
  4 import java.nio.file.Paths;
  5 import java.util.*;
  6 import java.util.stream.Stream;
  7 import org.apache.spark.mllib.linalg.Vector;
  8 import org.apache.spark.mllib.linalg.Vectors;
  9 
 10 /**
 11  * Copyright Mark Watson 2015\. Apache 2 license.
 12  */
 13 public class TextToSparseVector {
 14 
 15   // The following value might have to be increased
 16   // for large input texts:
 17   static private int MAX_WORDS = 60000;
 18 
 19   static private Set<String> noiseWords = new HashSet<>();
 20   static {
 21     try {
 22       Stream<String> lines =
 23 	    Files.lines(Paths.get("data", "stopwords.txt"));
 24       lines.forEach(s ->
 25           noiseWords.add(s)
 26       );
 27       lines.close();
 28     } catch (Exception e) { System.err.println(e); }
 29   }
 30 
 31   private Map<String,Integer> wordMap = new HashMap<>();
 32   private int startingWordIndex = 0;
 33   private Map<Integer,String> reverseMap = null;
 34 
 35   public Vector tokensToSparseVector(String[] tokens) {
 36     List<Integer> indices = new ArrayList();
 37     for (String token : tokens) {
 38       String stem = Stemmer.stemWord(token);
 39       if(! noiseWords.contains(stem) && validWord((stem))) {
 40         if (! wordMap.containsKey(stem)) {
 41           wordMap.put(stem, startingWordIndex++);
 42         }
 43         indices.add(wordMap.get(stem));
 44       }
 45     }
 46     int[] ind = new int[MAX_WORDS];
 47 
 48     double [] vals = new double[MAX_WORDS];
 49     for (int i=0, len=indices.size(); i<len; i++) {
 50       int index = indices.get(i);
 51       ind[i] = index;
 52       vals[i] = 1d;
 53     }
 54     Vector ret = Vectors.sparse(MAX_WORDS, ind, vals);
 55     return ret;
 56   }
 57 
 58   public boolean validWord(String token) {
 59     if (token.length() < 3)  return false;
 60     char[] chars = token.toCharArray();
 61     for (char c : chars) {
 62       if(!Character.isLetter(c)) return false;
 63     }
 64     return true;
 65   }
 66 
 67   private static int NUM_BEST_WORDS = 20;
 68 
 69   public String [] bestWords(double [] cluster) {
 70     int [] best = maxKIndex(cluster, NUM_BEST_WORDS);
 71     String [] ret = new String[NUM_BEST_WORDS];
 72     if (null == reverseMap) {
 73       reverseMap = new HashMap<>();
 74       for(Map.Entry<String,Integer> entry : wordMap.entrySet()){
 75         reverseMap.put(entry.getValue(), entry.getKey());
 76       }
 77     }
 78     for (int i=0; i<NUM_BEST_WORDS; i++)
 79 	  ret[i] = reverseMap.get(best[i]);
 80     return ret;
 81   }
 82   // following method found on Stack Overflow
 83   // and was written by user3879337\. Thanks!
 84   private  int[] maxKIndex(double[] array, int top_k) {
 85     double[] max = new double[top_k];
 86     int[] maxIndex = new int[top_k];
 87     Arrays.fill(max, Double.NEGATIVE_INFINITY);
 88     Arrays.fill(maxIndex, -1);
 89 
 90     top: for(int i = 0; i < array.length; i++) {
 91       for(int j = 0; j < top_k; j++) {
 92         if(array[i] > max[j]) {
 93           for(int x = top_k - 1; x > j; x--) {
 94             maxIndex[x] = maxIndex[x-1]; max[x] = max[x-1];
 95           }
 96           maxIndex[j] = i; max[j] = array[i];
 97           continue top;
 98         }
 99       }
100     }
101     return maxIndex;
102   }
103 }
```

The public method **String [] bestWords(double [] cluster)** is used for display purposes: it will be interesting to see the words in a document which provided the most evidence for its inclusion in a cluster. This Java class will be used in the next section to cluster similar Wikipedia articles.

### Using K-Means to Cluster Wikipedia Articles

The Wikipedia article training files contain one article per line with the article title appearing at the beginning of the line. I have already performed some data cleaning: capturing HTML, stripping HTML tags, yielding plain text for the articles and then organizing the data one article per line in the input text file. I am providing two input files: one containing 41 articles and one containing 2001 articles.

One challenge we face is converting the text of an article into a numeric feature vector. This was easy to do in an earlier section using cancer data already in numeric form; I just had to discard one data attribute and scale the remaining data atrributes.

In addition to converting input data into numeric feature vectors we also need to decide how many clusters we want the K-Means algorithm to partitian our data into.

Given the class **TextToSparseVector** developed in the last section, the code to cluster Wikipedia articles is fairly straightforward. In the following listing of the class **WikipediaKMeans**

```
 1 // This example is derived from the Spark MLlib examples
 2 
 3 package com.markwatson.machine_learning;
 4 
 5 import java.io.IOException;
 6 import java.nio.file.Files;
 7 import java.nio.file.Paths;
 8 import java.util.Arrays;
 9 import java.util.regex.Pattern;
10 import java.util.stream.Stream;
11 
12 import org.apache.spark.SparkConf;
13 import org.apache.spark.api.java.JavaRDD;
14 import org.apache.spark.api.java.JavaSparkContext;
15 import org.apache.spark.api.java.function.Function;
16 
17 import org.apache.spark.mllib.clustering.KMeans;
18 import org.apache.spark.mllib.clustering.KMeansModel;
19 import org.apache.spark.mllib.linalg.Vector;
20 import org.apache.spark.mllib.linalg.Vectors;
21 
22 public class WikipediaKMeans {
23 
24   // there are two example files in ./data/: one with
25   // 41 articles and one with 2001
26   //private final static String input_file = "wikipedia_41_lines.txt";
27   private final static String input_file = "wikipedia_2001_lines.txt";
28 
29   private static TextToSparseVector sparseVectorGenerator =
30    new TextToSparseVector();
31   private static final Pattern SPACE = Pattern.compile(" ");
32 
33   private static class ParsePoint implements Function<String, Vector> {
34 
35     @Override
36     public Vector call(String line) {
37       String[] tok = SPACE.split(line.toLowerCase());
38       return sparseVectorGenerator.tokensToSparseVector(tok);
39     }
40   }
41 
42   public static void main(String[] args) throws IOException {
43 
44     int number_of_clusters = 8;
45     int iterations = 100;
46     int runs = 1;
47 
48     JavaSparkContext sc = new JavaSparkContext("local", "WikipediaKMeans");
49     JavaRDD<String> lines = sc.textFile("data/" + input_file);
50     JavaRDD<Vector> points = lines.map(new ParsePoint());
51     KMeansModel model = KMeans.train(points.rdd(), number_of_clusters,
52 	                                 iterations, runs,
53                                      KMeans.K_MEANS_PARALLEL());
54 
55     System.out.println("Cluster centers:");
56     for (Vector center : model.clusterCenters()) {
57       System.out.println("\n " + center);
58       String [] bestWords = sparseVectorGenerator.bestWords(center.toArray());
59       System.out.println(" bestWords: " + Arrays.asList(bestWords));
60     }
61     double cost = model.computeCost(points.rdd());
62     System.out.println("Cost: " + cost);
63 
64     // re-read each "document* (single line in input file
65     // and predict which cluster it belongs to:
66     Stream<String> lines2 = Files.lines(Paths.get("data", input_file));
67     lines2.forEach(s ->
68         {
69           String[] parts = s.split("\t");
70           String[] tok = SPACE.split(parts[1].toLowerCase());
71           Vector v = sparseVectorGenerator.tokensToSparseVector(tok);
72           int cluster_index = model.predict(v);
73           System.out.println("Title: " + parts[0] + ", cluster index: " +
74 		                     cluster_index);
75         }
76     );
77     lines2.close();
78 
79     sc.stop();
80   }
81 }
```

The class **WikipediaKMeans** is fairly simple because most of the work is done converting text to feature vectors using class **TextToSparseVector** that we saw in the last seciton. The Spark setup code is also similar to that seen in our tiny **HelloSpark** example.

The parsepoint method defined in lines 33 to 40 uses the method **tokensToSparseVector** (defined in class **TextToSparseVector**) to convert the text in one line of the input file (remember that each line contains text for an entire Wikipedia article) to a sparse feature vector. There are two important parameters that you will want to experiment with. These parameters are defined on lines 44 and 45 and set the desired number of clusters and the number of iterations you want to run to form clusters. I suggest leaving **iterations** set initially to 100 as it is in the code and then vary **number_of_clusters**. If you are using this code in one of your own projects with a different data set then you might also want to experiment with running more iterations. If you cluster a very large number of text documents then you may have to increase the constant value **MAX_WORDS** set in line 9 in the class **TextToSparseVector**.

In line 48 we are creating a new Spark context that is local and will run in the same JVM as your application code. Lines 49 and 50 read in the text data from Wikipedia and create a JavaRDD of vectors pass to the K-Means clustering code that is called in lines 51 to 53.

Here are a few cluster indices for the 2001 input Wikipedia articles that are printed out by cluster index. When you run the sample program this list of documents assigned to eight different clusters is a lot of output. In the following I am listing just a small bit of the output for the first four clusters. If you look carefully at the generated clusters you will notice that Cluster seems not to be so useful since there are really two or three topics represented in the cluster. This might indicate re-running the clustering with a larger number of requested clusters (i.e., increasing the value of **number_of_clusters**). On the other hand, Cluster 1 seems very good, almost all articles are dealing with sports.

```
DOCUMENTS IN CLUSTER INDEX 0

   Article title: Academy Award for Best Art Direction
   Article title: Agricultural science
   Article title: Alien
   Article title: Astronomer
   Article title: Apollo
   Article title: Anatomy
   Article title: Demographics of Angola
   Article title: Transport in Angola
   Article title: Angolan Armed Forces
   Article title: Arctic Circle
   Article title: List of anthropologists
   Article title: Asociaci贸n Alumni
   Article title: Aramaic alphabet
   Article title: Applied ethics
   Article title: August
   Article title: Politics of Antigua and Barbuda
   Article title: Royal Antigua and Barbuda Defence Force
   Article title: Demographics of Armenia
   Article title: Geography of American Samoa
   Article title: America's National Game
   Article title: Augustin-Jean Fresnel
   Article title: Ashmore and Cartier Islands
   Article title: Extreme poverty
   Article title: Geography of Antarctica
   Article title: Transport in Antarctica
   Article title: Algernon Swinburne
   Article title: Alfred Lawson

DOCUMENTS IN CLUSTER INDEX 1

   Article title: Albert Spalding
   Article title: Arizona Cardinals
   Article title: Atlanta Falcons
   Article title: Arizona Diamondbacks
   Article title: Atlanta Braves
   Article title: Arsenal F.C.
   Article title: AZ (football club)
   Article title: American Football League
   Article title: Board game
   Article title: Baseball statistics
   Article title: Base on balls
   Article title: Hit by pitch
   Article title: Stolen base
   Article title: Baseball
   Article title: History of baseball in the United States
   Article title: Major League Baseball Most Valuable Player Award
   Article title: Major League Baseball Rookie of the Year Award
   Article title: National League Championship Series
   Article title: American League Championship Series
   Article title: National League Division Series
   Article title: 2001 World Series
   Article title: 1903 World Series
   Article title: Basketball
   Article title: National Baseball Hall of Fame and Museum
   Article title: Bill Walsh (American football coach)
   Article title: Babe Ruth
   Article title: Baltimore Ravens
   Article title: Buffalo Bills
   Article title: Backgammon
   Article title: Boston Red Sox
   Article title: Baltimore Orioles
   Article title: Barry Bonds
   Article title: Bob Costas

DOCUMENTS IN CLUSTER INDEX 2

   Article title: International Atomic Time
   Article title: Altruism
   Article title: ASCII
   Article title: Arithmetic mean
   Article title: Algae
   Article title: Analysis of variance
   Article title: Assistive technology
   Article title: Acid
   Article title: American National Standards Institute
   Article title: Atomic number
   Article title: Algorithm
   Article title: Axiom of choice
   Article title: Algorithms for calculating variance
   Article title: Analysis
   Article title: Amplitude modulation
   Article title: Automorphism
   Article title: Artificial intelligence
   Article title: Astrometry
   Article title: Alloy
   Article title: Angle
   Article title: Acoustics
   Article title: Atomic physics
   Article title: Atomic orbital
   Article title: Amino acid
   Article title: Area
   Article title: Astronomical unit
   Article title: Kolmogorov complexity
   Article title: An Enquiry Concerning Human Understanding
   Article title: Adenosine triphosphate
   Article title: Antibacterial

DOCUMENTS IN CLUSTER INDEX 3

   Article title: Academy Award
   Article title: Animation
   Article title: Andrei Tarkovsky
   Article title: Alfred Hitchcock
   Article title: American Film Institute
   Article title: Akira Kurosawa
   Article title: ABBA
   Article title: Afro Celt Sound System
   Article title: The Alan Parsons Project
   Article title: Dutch hip hop
   Article title: Anyone Can Whistle
   Article title: A Funny Thing Happened on the Way to the Forum
   Article title: Albert Brooks
   Article title: Arlo Guthrie
   Article title: The Birth of a Nation
   Article title: Blade Runner
   Article title: Blazing Saddles
   Article title: Brigitte Bardot
   Article title: Blue Velvet (film)
   Article title: Bing Crosby
```

This example program can be reused in your applications with few changes. You will probably want to manually assign meaningful labels to each cluster index and store the label with each document. For example, the cluster at index 1 would probably be labeled as “sports.”

### Using word2vec To Find Similar Words In Documents

Google released their open source **word2vec** library as Apache 2 licensed open source. The [Deeplearning4j](http://deeplearning4j.org) project and Spark’s MLlib both contain implementations. As I write this chapter the Deeplearning4j version has more flexibility but we will use the MLlib version here. We cover Deeplearning4j in a later chapter. We will use the sample data file from the Deeplearning4j project in this section.

The **word2vec** library can identify which other words in text are strongly related to any other word in the text. If you run **word2vec** on a large sample of English language text you will find the the word woman is closely associated with the word man, the word child to the word mother, the word road to the word car, etc.

The following listing shows the class **Word2VecRelatedWords** that is fairly simple because all we need to do is tokenize text, discard noise (or stop) words, and convert the input text to the correct Spark data types for processing by the MLlib class *Word2VecModel**.

```
 1 package com.markwatson.machine_learning;
 2 
 3 import org.apache.spark.api.java.JavaRDD;
 4 import org.apache.spark.api.java.JavaSparkContext;
 5 import org.apache.spark.mllib.feature.Word2Vec;
 6 import org.apache.spark.mllib.feature.Word2VecModel;
 7 
 8 import java.io.IOException;
 9 import java.nio.file.Files;
10 import java.nio.file.Paths;
11 import java.util.*;
12 import java.util.stream.Collectors;
13 import java.util.stream.Stream;
14 
15 import scala.Tuple2;
16 
17 public class Word2VecRelatedWords {
18   // Use the example data file form the deeplearning4j.org word2vec example:
19   private final static String input_file = "data/raw_sentences.txt";
20 
21   static private List<String> tokenizeAndRemoveNoiseWords(String s) {
22     return Arrays.asList(s.toLowerCase().replaceAll("\\.", " \\. ")
23         .replaceAll(",", " , ").replaceAll("\\?", " ? ")
24         .replaceAll("\n", " ").replaceAll(";", " ; ").split(" "))
25         .stream().filter((w) ->
26 		     ! noiseWords.contains(w)).collect(Collectors.toList());
27   }
28 
29   public static void main(String[] args) throws IOException {
30     JavaSparkContext sc = new JavaSparkContext("local", "WikipediaKMeans");
31 
32     String sentence = new String(Files.readAllBytes(Paths.get(input_file)));
33     List<String> words = tokenizeAndRemoveNoiseWords(sentence);
34     List<List<String>> localWords = Arrays.asList(words, words);
35     Word2Vec word2vec = new Word2Vec().setVectorSize(10).setSeed(113L);
36     JavaRDD<List<String>> rdd_word_list = sc.parallelize(localWords);
37     Word2VecModel model = word2vec.fit(rdd_word_list);
38     
39     Tuple2<String, Object>[] synonyms = model.findSynonyms("day", 15);
40     for (Object obj : synonyms)
41 	  System.err.println("-- words associated with day: " + obj);
42 
43     synonyms = model.findSynonyms("children", 15);
44     for (Object obj : synonyms)
45 	  System.err.println("-- words associated with children: " + obj);
46 
47     synonyms = model.findSynonyms("people", 15);
48     for (Object obj : synonyms)
49 	  System.err.println("-- words associated with people: " + obj);
50 
51     synonyms = model.findSynonyms("three", 15);
52     for (Object obj : synonyms)
53 	  System.err.println("-- words associated with three: " + obj);
54 
55     synonyms = model.findSynonyms("man", 15);
56     for (Object obj : synonyms)
57 	  System.err.println("-- words associated with man: " + obj);
58 
59     synonyms = model.findSynonyms("women", 15);
60     for (Object obj : synonyms)
61 	  System.err.println("-- words associated with women: " + obj);
62 
63     sc.stop();
64   }
65 
66   static private Set<String> noiseWords = new HashSet<>();
67   static {
68     try {
69       Stream<String> lines = Files.lines(Paths.get("data", "stopwords.txt"));
70       lines.forEach(s -> noiseWords.add(s));
71       lines.close();
72     } catch (Exception e) { System.err.println(e); }
73   }
74 }
```

The output from this example program is:

```
words associated with 'day': (season,0.952233990962071)
words associated with 'day': (night,0.9511060013892698)
words associated with 'day': (big,0.8728547447056546)
words associated with 'day': (good,0.8576788222594224)
words associated with 'day': (today,0.8396659969645013)
words associated with 'day': (end,0.8293329248658234)
words associated with 'day': (life,0.8249991404480943)
words associated with 'day': (game,0.80432033480323)
words associated with 'day': (program,0.792725056069907)
words associated with 'day': (business,0.7913084744641095)
words associated with 'day': (political,0.7818051986127171)
words associated with 'day': (market,0.7764758770314986)
words associated with 'day': (second,0.7737555854409787)
words associated with 'day': (year,0.7429513803623038)
words associated with 'day': (set,0.7294508559210614)
words associated with 'children': (million,1.0903815875201748)
words associated with 'children': (women,1.059845154178747)
words associated with 'children': (days,0.9776504379129254)
words associated with 'children': (two,0.9646151248422365)
words associated with 'children': (years,0.936748689685324)
words associated with 'children': (members,0.9017954013921553)
words associated with 'children': (house,0.8657203835921035)
words associated with 'children': (old,0.8631901736913122)
words associated with 'children': (left,0.86281306293074)
words associated with 'children': (four,0.8613461580704683)
words associated with 'children': (three,0.858547609404486)
words associated with 'children': (week,0.8522042667181716)
words associated with 'children': (five,0.8179405841924944)
words associated with 'children': (home,0.8095612388770681)
words associated with 'children': (case,0.7461659839438249)
words associated with 'people': (know,0.7792464691200726)
words associated with 'people': (want,0.734389563281012)
words associated with 'people': (work,0.6829544862339761)
words associated with 'people': (make,0.6645301218487332)
words associated with 'people': (say,0.6153710744965498)
words associated with 'people': (public,0.6054330328462636)
words associated with 'people': (ms,0.5842404516570064)
words associated with 'people': (just,0.5791629468565187)
words associated with 'people': (white,0.5636639753271303)
words associated with 'people': (home,0.5586558330551199)
words associated with 'people': (little,0.5401336635483608)
words associated with 'people': (think,0.5176197541759774)
words associated with 'people': (american,0.5098579866944077)
words associated with 'people': (women,0.5046623970160208)
words associated with 'people': (?,0.47238591701531557)
words associated with 'three': (two,2.0172783800362466)
words associated with 'three': (five,1.9963427800055753)
words associated with 'three': (four,1.9890870749494771)
words associated with 'three': (years,1.836102840486217)
words associated with 'three': (million,1.7966031095487769)
words associated with 'three': (days,1.7456308099866056)
words associated with 'three': (ago,1.7438148167574663)
words associated with 'three': (old,1.6704126685943632)
words associated with 'three': (week,1.6393314973787558)
words associated with 'three': (times,1.6236709983968334)
words associated with 'three': (children,1.4605285096333689)
words associated with 'three': (left,1.3927866198115773)
words associated with 'three': (members,1.2757167489324481)
words associated with 'three': (companies,1.106585238117151)
words associated with 'three': (year,1.0806081055554506)
words associated with 'man': (john,0.6841310695193488)
words associated with 'man': (case,0.6795045575483528)
words associated with 'man': (program,0.6652340138422144)
words associated with 'man': (dr,0.659963781737535)
words associated with 'man': (market,0.6552229884848991)
words associated with 'man': (ms,0.6488172627464075)
words associated with 'man': (yesterday,0.640285291527994)
words associated with 'man': (director,0.6400444581814078)
words associated with 'man': (street,0.6395737967168845)
words associated with 'man': (mr,0.6181822944209798)
words associated with 'man': (court,0.6113708937966306)
words associated with 'man': (political,0.5994838292027088)
words associated with 'man': (life,0.5873452829470825)
words associated with 'man': (office,0.5714323032795753)
words associated with 'women': (children,0.7336026558437857)
words associated with 'women': (home,0.6950468303126367)
words associated with 'women': (war,0.65634414969338)
words associated with 'women': (money,0.6548505665001131)
words associated with 'women': (say,0.6490701416147411)
words associated with 'women': (like,0.6322006183913979)
words associated with 'women': (public,0.6058074917094844)
words associated with 'women': (court,0.6057305040658708)
words associated with 'women': (want,0.5977223947592321)
words associated with 'women': (music,0.5939362450235905)
words associated with 'women': (street,0.5876902247693967)
words associated with 'women': (house,0.5866848059316422)
words associated with 'women': (country,0.5724038019422217)
words associated with 'women': (case,0.57149905752473)
words associated with 'women': (family,0.5609861524585015)
```

While **word2vec** results are just the result of statistical processing and the code does not understand the semantic of the English language, the results are still impressive.

### Chapter Wrap Up

In the previous chapter we used machine learning for natural language processing using the OpenNLP project. In the examples in this chapter we used the Spark MLlib library for for logistic regression, document clustering, and determining which words are closely associated with each other.

You can go far using OpenNLP and Spark MLlib in your projects. There are a few things to keep in mind, however. One of the most difficult aspects of machine learning is finding and preparing training data. This process will be very dependant on what kind of project you are working on and what sources of data you have.

One of the most powerful machine learning techniques is artificial neural networks. I have a long history of using neural networks (I was on a DARPA neural network advisory panel and wrote the first version of the commercial ANSim neural network product in the late 1980s). I decided not to cover simple neural network models in this book because I have already written about neural networks in one chapter of my book [Practical Artificial Intelligence Programming in Java](https://leanpub.com/javaai). “Deep learning” neural networks are also very effective (if difficult to use) for some types of machine learning problems (e.g., image recognition and speech recognition) and we will use the [Deeplearning4j](http://deeplearning4j.org) project in a later chapter.

In the next chapter we cover another type of machine learning: anomaly detection.

## Anomaly Detection Machine Learning Example

Anomaly detection models are used in one very specific class of use cases: when you have many negative (non-anomaly) examples and relatively few positive (anomaly) examples. For training we will ignore positive examples, create a model of “how things should be”, and hopefully be able to detect anomalies different from the original negative examples.

If you have a large training set of both negative and positive examples then do not use anomaly detection models.

### Motivation for Anomaly Detection

There are two other examples in this book using the University of Wisconsin cancer data. These other examples are supervised learning. Anomaly detection as we do it in this chapter is, more or less, unsupervised learning.

When should we use anomaly detection? You should use supervised learning algorithms like neural networks and logistic classification when there are roughly equal number of available negative and positive examples in the training data. The University of Wisconsin cancer data set is fairly evenly split between negative and positive examples.

Anomaly detection should be used when you have many negative (“normal”) examples and relatively few positive (“anomaly”) examples. For the example in this chapter we will simulate scarcity of positive (“anomaly”) results by preparing the data using the Wisconsin cancer data as follows:

*   We will split the data into training (60%), cross validation (20%) and testing (20%).
*   For the training data, we will discard all but two positive (“anomaly”) examples. We do this to simulate the real world test case where some positive examples are likely to end up in the training data in spite of the fact that we would prefer the training data to only contain negative (“normal”) examples.
*   We will use the cross validation data to find a good value for the epsilon meta parameter.
*   After we find a good epsilon value, we will calculate the F1 measurement for the model.

### Math Primer for Anomaly Detection

We are trying to model “normal” behavior and we do this by taking each feature and fitting a Gaussian (bell curve) distribution to each feature. The learned parameters for a Gaussian distribution are the mean of the data (where the bell shaped curve is centered) and the variance. You might be more familiar with the term standard deviation, ![\sigma](images/00007.gif). Variance is defined as ![ \sigma ^2](images/00008.gif).

We will need to calculate ![P(x : \mu, \sigma ^2)](images/00009.gif) where ![\mu](images/00010.gif) is the mean and ![ \sigma ^2](images/00011.gif) is the squared variance:

![P(x : \mu, \sigma ^2) = \frac{1}{{\sigma \sqrt {2\pi } }}e^{{{ - \left( {x - \mu } \right)^2 } \mathord{\left/ {\vphantom {{ - \left( {x - \mu } \right)^2 } {2\sigma ^2 }}} \right. \kern-\nulldelimiterspace} {2\sigma ^2 }}}](images/00012.gif)

where ![x_i](images/00013.gif) are the samples and we can calculate the squared variance as:

![\sigma^2 = \frac{\displaystyle\sum_{i=1}^{m}(x_i - \mu)^2} {m}](images/00014.gif)

We calculate the parameters of ![\mu](images/00015.gif) and ![ \sigma ^2](images/00016.gif) for each feature. A bell shaped distribution in two dimensions is easy to visualize as is an inverted bowl shape in three dimentions. What if we have many features? Well, the math works and don’t worry about not being able to picture it in your mind.

### AnomalyDetection Utility Class

The class **AnomalyDetection** developed in this section is fairly general purpose. It processes a set of training examples and for each feature calculates ![\mu](images/00017.gif) and ![ \sigma ^2](images/00018.gif). We are also training for a third parameter: an epsilon “cutoff” value: if for a given input vector if ![P(x : \mu, \sigma ^2)](images/00019.gif) evaluates to a value greater than epsilon then the input vector is “normal, less than epsilon implies that the input vector is an “anomaly.” The math for calulating these three features from training data is fairly easy but the code is not: we need to organize the training data and search for a value of epsilon that minimizes the error for a cross validaton data set.

To be clear: we separate the input examples into three separate sets of training, cross validation, and testing data. We use the training data to set the model parameters, use the cross validation data to learn an epsilon value, and finally use the testing data to get precision, recall, and F1 scores that indicate how well the model detects anomalies in data not used for training and cross validation.

I present the example program as one long listing, with more code explanation after the listing. Please note the long loop over each input training example starting at line 28 and ending on line 74\. The code in lines 25 through 44 processes the input training data sample into three disjoint sets of training, cross validation, and testing data. Then the code in lines 45 through 63 copies these three sets of data to Java arrays.

The code in lines 65 through 73 calculates, for a training example, the value of ![\mu](images/00020.gif) (the varible **mu** in the code).

Please note in the code example that I prepend class variables used in methods with “this.” even when it is not required. I do this for legibility and is a personal style.

```
 1 package com.markwatson.anomaly_detection;
  2 
  3 import java.util.ArrayList;
  4 import java.util.List;
  5 
  6 /**
  7  * Created by markw on 10/7/15.
  8  */
  9 public class AnomalyDetection {
 10 
 11   public AnomalyDetection() { }
 12 
 13   /**
 14    * AnomalyDetection is a general purpose class for building anomaly detection
 15    * models. You should use this type of mdel when you have mostly negative
 16    * training examples with relatively few positive examples and you need a model
 17    * that detects postive (anomaly) inputs.
 18    *
 19    * @param num_features
 20    * @param num_training_examples
 21    * @param training_examples [num_training_examples][num_features]
 22    */
 23   public AnomalyDetection(int num_features, int num_training_examples,
 24                           double [][] training_examples) {
 25     List<double[]> training = new ArrayList<>();
 26     List<double []> cross_validation = new ArrayList<>();
 27     List<double []> testing = new ArrayList<>();
 28     int outcome_index = num_features - 1; // index of target outcome
 29     for (int i=0; i<num_training_examples; i++) {
 30       if (Math.random() < 0.6) { // 60% training
 31         // Only keep normal (negative) examples in training, except
 32         // remember the reason for using this algorithm is that it
 33         // works with many more negative examples than positive
 34         // examples, and that the algorithm works even with some positive
 35         // examples mixed into the training set. The random test is to
 36         // allow about 10% positive examples to get into the training set:
 37         if (training_examples[i][outcome_index] < 0.5 || Math.random() < 0.1)
 38           training.add(training_examples[i]);
 39       } else if (Math.random() < 0.7) {
 40           cross_validation.add(training_examples[i]);
 41       } else {
 42         testing.add(training_examples[i]);
 43       }
 44     }
 45     this.num_training_examples = training.size();
 46     this.num_cross_validation_examples = cross_validation.size();
 47     this.num_testing_examples = testing.size();
 48 
 49     this.training_examples = new double[this.num_training_examples][];
 50     for (int k=0; k<this.num_training_examples; k++) {
 51       this.training_examples[k] = training.get(k);
 52     }
 53 
 54     this.cross_validation_examples = new double[num_cross_validation_examples][];
 55     for (int k=0; k<num_cross_validation_examples; k++) {
 56       this.cross_validation_examples[k] = cross_validation.get(k);
 57     }
 58 
 59     this.testing_examples = new double[num_testing_examples][];
 60     for (int k=0; k<num_testing_examples; k++) {
 61       // dimensions of [num_training_examples][num_features]:
 62       this.testing_examples[k] = testing.get(k);
 63     }
 64 
 65     this.mu = new double[num_features];
 66     this.sigma_squared = new double[num_features];
 67     this.num_features = num_features;
 68     for (int nf = 0; nf < this.num_features; nf++) { //
 69       double sum = 0;
 70       for (int nt = 0; nt < this.num_training_examples; nt++)
 71         sum += training_examples[nt][nf];
 72       this.mu[nf] = sum / this.num_training_examples;
 73     }
 74   }
 75 
 76   public double [] muValues()     { return mu; }
 77   public double [] sigmaSquared() { return sigma_squared; }
 78   public double bestEpsilon()     { return best_epsilon; }
 79 
 80   /**
 81    *
 82    * Train the model using a range of epsilon values. Epsilon is a
 83    * hyper parameter that we want to find a value that
 84    * minimizes the error count.
 85    */
 86   public void train() {
 87     double best_error_count = 1e10;
 88     for (int epsilon_loop=0; epsilon_loop<40; epsilon_loop++) {
 89       double epsilon = 0.05 + 0.01 * epsilon_loop;
 90       double error_count = train(epsilon);
 91       if (error_count < best_error_count) {
 92         best_error_count = error_count;
 93         best_epsilon = epsilon;
 94       }
 95     }
 96     System.out.println("\n**** Best epsilon value = " + best_epsilon );
 97 
 98     // retrain for the best epsilon setting the maximum likelyhood parameters
 99     // which are now in epsilon, mu[] and sigma_squared[]:
100     train_helper(best_epsilon);
101 
102     // finally, we are ready to see how the model performs with test data:
103     test(best_epsilon);
104   }
105 
106   /**
107    * calculate probability p(x; mu, sigma_squared)
108    *
109    * @param x - example vector
110    * @return
111    */
112   private double p(double [] x) {
113     double sum = 0;
114     // use (num_features - 1) to skip target output:
115     for (int nf=0; nf<num_features - 1; nf++) {
116       sum += (1.0 / (SQRT_2_PI * sigma_squared[nf])) *
117              Math.exp(- (x[nf] - mu[nf]) * (x[nf] - mu[nf]));
118     }
119     return sum / num_features;
120   }
121 
122   /**
123    * returns 1 if input vector is an anoomaly
124    *
125    * @param x - example vector
126    * @return
127    */
128   public boolean isAnamoly(double [] x) {
129     double sum = 0;
130     // use (num_features - 1) to skip target output:
131     for (int nf=0; nf<num_features - 1; nf++) {
132       sum += (1.0 / (SQRT_2_PI * sigma_squared[nf])) *
133              Math.exp(- (x[nf] - mu[nf]) * (x[nf] - mu[nf]));
134     }
135     return (sum / num_features) < best_epsilon;
136   }
137 
138   private double train_helper_(double epsilon) {
139     // use (num_features - 1) to skip target output:
140     for (int nf = 0; nf < this.num_features - 1; nf++) {
141       double sum = 0;
142       for (int nt=0; nt<this.num_training_examples; nt++) {
143         sum += (this.training_examples[nt][nf] - mu[nf]) *
144                (this.training_examples[nt][nf] - mu[nf]);
145       }
146       sigma_squared[nf] = (1.0 / num_features) * sum;
147     }
148     double cross_validation_error_count = 0;
149     for (int nt=0; nt<this.num_cross_validation_examples; nt++) {
150       double[] x = this.cross_validation_examples[nt];
151       double calculated_value = p(x);
152       if (x[9] > 0.5) { // target training output is ANOMALY
153         // if the calculated value is greater than epsilon
154         // then this x vector is not an anomaly (e.g., it
155         // is a normal sample):
156         if (calculated_value > epsilon) cross_validation_error_count += 1;
157       } else { // target training output is NORMAL
158         if (calculated_value < epsilon) cross_validation_error_count += 1;
159       }
160     }
161     System.out.println("   cross_validation_error_count = " +
162                        cross_validation_error_count +
163                        " for epsilon = " + epsilon);
164     return cross_validation_error_count;
165   }
166 
167   private double test(double epsilon) {
168     double num_false_positives = 0, num_false_negatives = 0;
169     double num_true_positives = 0, num_true_negatives = 0;
170     for (int nt=0; nt<this.num_testing_examples; nt++) {
171       double[] x = this.testing_examples[nt];
172       double calculated_value = p(x);
173       if (x[9] > 0.5) { // target training output is ANOMALY
174         if (calculated_value > epsilon) num_false_negatives++;
175         else                            num_true_positives++;
176       } else { // target training output is NORMAL
177         if (calculated_value < epsilon) num_false_positives++;
178         else                            num_true_negatives++;
179       }
180     }
181     double precision = num_true_positives /
182                        (num_true_positives + num_false_positives);
183     double recall = num_true_positives /
184                     (num_true_positives + num_false_negatives);
185     double F1 = 2 * precision * recall / (precision + recall);
186 
187     System.out.println("\n\n -- best epsilon = " + this.best_epsilon);
188     System.out.println(" -- number of test examples = " +
189                        this.num_testing_examples);
190     System.out.println(" -- number of false positives = " + num_false_positives);
191     System.out.println(" -- number of true positives = " + num_true_positives);
192     System.out.println(" -- number of false negatives = " + num_false_negatives);
193     System.out.println(" -- number of true negatives = " + num_true_negatives);
194     System.out.println(" -- precision = " + precision);
195     System.out.println(" -- recall = " + recall);
196     System.out.println(" -- F1 = " + F1);
197     return F1;
198   }
199 
200   double best_epsilon = 0.02;
201   private double [] mu;  // [num_features]
202   private double [] sigma_squared; // [num_features]
203   private int num_features;
204   private static double SQRT_2_PI = 2.50662827463;
205 
206 
207   private double[][] training_examples; // [num_features][num_training_examples]
208   // [num_features][num_training_examples]:
209   private double[][] cross_validation_examples; 
210   private double[][] testing_examples; // [num_features][num_training_examples]
211   private int num_training_examples;
212   private int num_cross_validation_examples;
213   private int num_testing_examples;
214 
215 }
```

Once the training data and the values of ![\mu](images/00021.gif) (the varible **mu** in the code) are defined for each feature we can define the method **train** in lines 86 through 104 that calculated the best **epsilon** “cutoff” value for the training data set using the method **train_helper** defined in lines 138 through 165\. We use the “best” **epsilon** value by testing with the separate cross validation data set; we do this by calling the method **test** that is defined in lines 167 through 198.

### Example Using the University of Wisconsin Cancer Data

The example in this section loads the University of Wisconsin data and uses the class **AnomalyDetection** developed in the last section to find anomalies, which for this example will be input vectors that represented malignancy in the original data.

```
 1 package com.markwatson.anomaly_detection;
 2 
 3 import java.io.*;
 4 import org.apache.commons.io.FileUtils;
 5 
 6 /**
 7  * Train a deep belief network on the University of Wisconsin Cancer Data Set.
 8  */
 9 public class WisconsinAnomalyDetection {
10 
11   private static boolean PRINT_HISTOGRAMS = true;
12 
13   public static void main(String[] args) throws Exception {
14 
15     String [] lines =
16       FileUtils.readFileToString(
17          new File("data/cleaned_wisconsin_cancer_data.csv")).split("\n");
18     double [][] training_data = new double[lines.length][];
19     int line_count = 0;
20     for (String line : lines) {
21       String [] sarr = line.split(",");
22       double [] xs = new double[10];
23       for (int i=0; i<10; i++) xs[i] = Double.parseDouble(sarr[i]);
24       for (int i=0; i<9; i++) xs[i] *= 0.1;
25       xs[9] = (xs[9] - 2) * 0.5; // make target output be [0,1] instead of [2,4]
26       training_data[line_count++] = xs;
27     }
28 
29     if (PRINT_HISTOGRAMS) {
30       PrintHistogram.historam("Clump Thickness", training_data, 0, 0.0, 1.0, 10);
31       PrintHistogram.historam("Uniformity of Cell Size", training_data,
32                               1, 0.0, 1.0, 10);
33       PrintHistogram.historam("Uniformity of Cell Shape", training_data,
34                               2, 0.0, 1.0, 10);
35       PrintHistogram.historam("Marginal Adhesion", training_data,
36                               3, 0.0, 1.0, 10);
37       PrintHistogram.historam("Single Epithelial Cell Size", training_data,
38                               4, 0.0, 1.0, 10);
39       PrintHistogram.historam("Bare Nuclei", training_data, 5, 0.0, 1.0, 10);
40       PrintHistogram.historam("Bland Chromatin", training_data, 6, 0.0, 1.0, 10);
41       PrintHistogram.historam("Normal Nucleoli", training_data, 7, 0.0, 1.0, 10);
42       PrintHistogram.historam("Mitoses", training_data, 8, 0.0, 1.0, 10);
43     }
44     
45     AnomalyDetection detector = new AnomalyDetection(10, line_count - 1,
46                                                      training_data);
47 
48     // the train method will print training results like
49     // precision, recall, and F1:
50     detector.train();
51 
52     // get best model parameters:
53     double best_epsilon = detector.bestEpsilon();
54     double [] mean_values = detector.muValues();
55     double [] sigma_squared = detector.sigmaSquared();
56 
57     // to use this model, us the method AnomalyDetection.isAnamoly(double []):
58 
59     double [] test_malignant = new double[] {0.5,1,1,0.8,0.5,0.5,0.7,1,0.1};
60     double [] test_benign = new double[] {0.5,0.4,0.5,0.1,0.8,0.1,0.3,0.6,0.1};
61     boolean malignant_result = detector.isAnamoly(test_malignant);
62     boolean benign_result = detector.isAnamoly(test_benign);
63     System.out.println("\n\nUsing the trained model:");
64     System.out.println("malignant result = " + malignant_result +
65                        ", benign result = " + benign_result);
66   }
67 }
```

Data used by an anomaly detecton model should have (roughly) a Gaussian (bell curve shape) distribution. What form does the cancer data have? Unfortunately, each of the data features seems to either have a greater density at the lower range of feature values or large density at the extremes of the data feature ranges. This will cause our model to not perform as well as we would like. Here are the inputs displayed as five-bin histograms:

```
Clump Thickness
0	177
1	174
2	154
3	63
4	80

Uniformity of Cell Size
0	393
1	86
2	54
3	43
4	72

Uniformity of Cell Shape
0	380
1	92
2	58
3	54
4	64

Marginal Adhesion
0	427
1	85
2	42
3	37
4	57

Single Epithelial Cell Size
0	394
1	117
2	76
3	28
4	33

Bare Nuclei
0	409
1	44
2	33
3	27
4	135

Bland Chromatin
0	298
1	182
2	41
3	97
4	30

Normal Nucleoli
0	442
1	56
2	39
3	37
4	74

Mitoses
0	567
1	42
2	8
3	17
4	14
```

I won’t do it in this example, but the feature “Bare Nuclei” should be removed because it is not even close to being a bell-shaped distribution. Another thing that you can do (recommended by Andrew Ng in his Coursera Machine Learning class) is to take the log of data and otherwise transform it to something that looks more like a Gaussian distribution. In the class WisconsinAnomalyDetection, you could for example, transform the data using something like:

```
1   // make the data look more like a Gaussian (bell curve shaped) distribution:
2   double min = 1.e6, max = -1.e6;
3   for (int i=0; i<9; i++) {
4     xs[i] = Math.log(xs[i] + 1.2);
5     if (xs[i] < min) min = xs[i];
6     if (xs[i] > max) max = xs[i];
7   }
8   for (int i=0; i<9; i++) xs[i] = (xs[i] - min) / (max - min);
```

The constant 1.2 in line 4 is a tuning parameter that I got by trial and error by iterating on adjusting the factor and looking at the data histograms.

In a real application you would drop features that you can not transform to something like a Gaussian distribution.

Here are the results of running the code as it is in the github repository for this book:

```
 -- best epsilon = 0.28
 -- number of test examples = 63
 -- number of false positives = 0.0
 -- number of true positives = 11.0
 -- number of false negatives = 8.0
 -- number of true negatives = 44.0
 -- precision = 1.0
 -- recall = 0.5789473684210527
 -- F1 = 0.7333333333333334

Using the trained model:
malignant result = true, benign result = false
```

How do we evaluate these results? The precision value of 1.0 means that there were no false positives. False positives are predictions of a true result when it should have been false. The value 0.578 for recall means that of all the samples that should have been classified as positive, we only predicted about 57.8% of them. The F1 score is calculated as two times the product of precision and recall, divided by the sum of precision plus recall.

## Deep Learning Using Deeplearning4j

The [Deeplearning4j.org](http://deeplearning4j.org/) Java library supports several neural network algorithms including support for Deep Learning (DL). We will look at an example of DL implementing Deep-Belief networks using the same University of Wisconsin cancer database that we used in the chapters on machine learning with Spark and on anomaly detection. Deep learning refers to neural networks with many layers, possibly with weights connecting neurons in non-adjacent layers which makes it possible to model temporal and spacial patterns in data.

I am going to assume that you have some knowledge of simple backpropagation neural networks. If you are unfamiliar with neural networks you might want to pause and do a web search for “neural networks backpropagation tutorial” or read the neural network chapter in my book [Practical Artificial Intelligence Programming With Java, 4th edition](https://leanpub.com/javaai).

The difficulty in training many layer networks with backpropagation is that the delta errors in the layers near the input layer (and far from the output layer) get very small and training can take a very long time even on modern processors and GPUs. Geoffrey Hinton and his colleagues created a new technique for pretraining weights. In 2012 I took a Coursera course taught by Hinton and some colleagues titled [‘Neural Networks for Machine Learning’](https://www.coursera.org/course/neuralnets) and the material may still be available online when you read this book.

For Java developers, Deeplearning4j is a great starting point for experimenting with deep learning. If you also use Python then there are good tutorials and other learning assets at [deeplearning.net](http://deeplearning.net/).

### Deep Belief Networks

Deep Belief Networks (DBN) are a type of deep neural network containing multiple hidden neuron layers where there are no connections between neurons inside any specific hidden layer. Each hidden layer learns features based on training data an the values of weights from the previous hidden layer. By previous layer I refer to the connected layer that is closer to the input layer. A DBN can learn more abstract features, with more abstraction in the hidden layers “further” from the input layer.

DBNs are first trained a layer at a time. Initially a set of training inputs is used to train the weights between the input and the first hidden layer of neurons. Technically, as we preliminarily train each succeeding pair of layers we are training a restricted Boltzmann machine (RBM) to learn a new set of features. It is enough for you to know at this point that RBMs are two layers, input and output, that are completely connected (all neurons in the first layer have a weighted connection to each neuron in the next layer) and there are no inner-layer connections.

As we progressively train a DBN, the output layer for one RBM becomes the input layer for the next neuron layer pair for preliminary training.

Once the hidden layers are all preliminarily trained then backpropagation learning is used to retrain the entire network but now delta errors are calculated by comparing the forward pass outputs with the training outputs and back-propagating errors to update weights in layers proceeding back towards the first hidden layer.

The important thing to understand is that backpropagation tends to not work well for networks with many hidden layers because the back propagated errors get smaller as we process backwards towards the input neurons - this would cause network training to be very slow. By precomputing weights using RBM pairs, we are closer to a set of weights to minimize errors over the training set (and the test set).

### Deep Belief Example

The following screen show shows an IntelliJ project (you can use the free community orprofessional version for the examples in this book) for the example in this chapter:

![IntelliJ project view for the examples in this chapter](images/00022.jpeg)

IntelliJ project view for the examples in this chapter

The Deeplearning4j library uses user-written Java classes to import training and testing data into a form that the Deeplearning4j library can use. The following listing shows the implementation of the class **WisconsinDataSetIterator** that iterates through the University of Wisconsin cancer data set:

```
 1 package com.markwatson.deeplearning;
 2 
 3 import org.deeplearning4j.datasets.iterator.BaseDatasetIterator;
 4 
 5 import java.io.FileNotFoundException;
 6 
 7 
 8 public class WisconsinDataSetIterator extends BaseDatasetIterator {
 9   private static final long serialVersionUID = -2023454995728682368L;
10 
11   public WisconsinDataSetIterator(int batch, int numExamples)
12          throws FileNotFoundException {
13     super(batch, numExamples, new WisconsinDataFetcher());
14   }
15 }
```

The **WisconsinDataSetIterator** constructor calls its super class with an instance of the class **WisconsinDataFetcher** (defined in the next listing) to read the Comma Separated Values (CSV) spreadsheet data from the file data/cleaned_wisconsin_cancer_data.csv:

```
 1 package com.markwatson.deeplearning;
 2 
 3 import org.deeplearning4j.datasets.fetchers.CSVDataFetcher;
 4 
 5 import java.io.FileInputStream;
 6 import java.io.FileNotFoundException;
 7 
 8 /**
 9  * Created by markw on 10/5/15.
10  */
11 public class WisconsinDataFetcher extends CSVDataFetcher {
12 
13   public WisconsinDataFetcher() throws FileNotFoundException {
14     super(new FileInputStream("data/cleaned_wisconsin_cancer_data.csv"), 9);
15   }
16   @Override
17   public void fetch(int i) {
18     super.fetch(i);
19   }
20 
21 }
```

In line 14, the last argument 9 defines which column in the input CSV file contains the label data. This value is zero indexed so if you look at the input file data/cleaned_wisconsin_cancer_date.csv this will be the last column. Values of 4 in the last column idicate malignant and values of 2 indicate not malignant.

The following listing shows the definition of the class **DeepBeliefNetworkWisconsinData** that reads the University of Wisconsin cancer data set using the code in the last two listings, randmly selects part of it to use for training and for testing, creates a DBN, and tests it. The value of the variable **numHidden** set in line 51 refers to the number of neurons in each hidden layer. Setting **numberOfLayers** to 3 in line 52 indicates that we will just use a single hidden layer since this value (3) also counts the input and output layers.

The network is configured and constructed in lines 83 through 104\. If we increased the number of hidden units (something that you might do for more complex problems) then you would repeat lines 88 through 97 to add a new hidden layer, and you would change the layer indices (first argument) as appropriate in calls to the chained method **.layer()**.

```
 1 package com.markwatson.deeplearning;
  2 
  3 import org.deeplearning4j.datasets.iterator.DataSetIterator;
  4 import org.deeplearning4j.eval.Evaluation;
  5 import org.deeplearning4j.nn.conf.MultiLayerConfiguration;
  6 import org.deeplearning4j.nn.conf.NeuralNetConfiguration;
  7 import org.deeplearning4j.nn.conf.layers.OutputLayer;
  8 import org.deeplearning4j.nn.conf.layers.RBM;
  9 import org.deeplearning4j.nn.multilayer.MultiLayerNetwork;
 10 import org.deeplearning4j.nn.weights.WeightInit;
 11 import org.nd4j.linalg.api.ndarray.INDArray;
 12 import org.nd4j.linalg.dataset.DataSet;
 13 import org.nd4j.linalg.dataset.SplitTestAndTrain;
 14 import org.nd4j.linalg.factory.Nd4j;
 15 import org.nd4j.linalg.lossfunctions.LossFunctions;
 16 import org.slf4j.Logger;
 17 import org.slf4j.LoggerFactory;
 18 
 19 import java.io.*;
 20 import java.nio.file.Files;
 21 import java.nio.file.Paths;
 22 import java.util.Random;
 23 
 24 import org.apache.commons.io.FileUtils;
 25 
 26 /**
 27  * Train a deep belief network on the University of Wisconsin Cancer Data Set.
 28  */
 29 public class DeepBeliefNetworkWisconsinData {
 30 
 31   private static Logger log =
 32     LoggerFactory.getLogger(DeepBeliefNetworkWisconsinData.class);
 33 
 34   public static void main(String[] args) throws Exception {
 35 
 36     final int numInput = 9;
 37     int outputNum = 2;
 38     /**
 39      * F1 scores as a function of the number of hidden layer
 40      * units hyper-parameter:
 41      *
 42      *    numHidden   F1
 43      *    ---------   --
 44      *            2   0.50734
 45      *            3   0.87283 (value to use - best result / smallest network)
 46      *           13   0.87283
 47      *          100   0.55987 (over fitting)
 48      *
 49      *   Other hyper parameters held constant: batchSize = 648
 50      */
 51     int numHidden = 3;
 52     int numberOfLayers = 3; // input, hidden, output
 53     int numSamples = 648;
 54 
 55     /**
 56      * F1 scores as a function of the number of batch size:
 57      *
 58      *    batchSize   F1
 59      *    ---------   --
 60      *           30   0.50000
 61      *           64   0.78787
 62      *          323   0.67123
 63      *          648   0.87283 (best to process all training vectors in one batch)
 64      *
 65      *   Other hyper parameters held constant: numHidden = 3
 66      */
 67     int batchSize = 648; // equal to number of samples
 68 
 69     int iterations = 100;
 70     int fractionOfDataForTraining = (int) (batchSize * 0.7);
 71     int seed = 33117;
 72 
 73     DataSetIterator iter = new WisconsinDataSetIterator(batchSize, numSamples);
 74     DataSet next = iter.next();
 75     next.normalizeZeroMeanZeroUnitVariance();
 76 
 77     SplitTestAndTrain splitDataSets =
 78 	  next.splitTestAndTrain(fractionOfDataForTraining, new Random(seed));
 79     DataSet train = splitDataSets.getTrain();
 80     DataSet test = splitDataSets.getTest();
 81 
 82     MultiLayerConfiguration conf = new NeuralNetConfiguration.Builder()
 83         .seed(seed) //use the same random seed
 84         .iterations(iterations)
 85         .l1(1e-1).regularization(true).l2(2e-4)
 86         .list(numberOfLayers - 1) // don't count the input layer
 87         .layer(0,
 88             new RBM.Builder(RBM.HiddenUnit.RECTIFIED, RBM.VisibleUnit.GAUSSIAN)
 89                 .nIn(numInput)
 90                 .nOut(numHidden)
 91                 // set variance of random initial weights based on
 92                 // input and output layer size:
 93                 .weightInit(WeightInit.XAVIER)
 94                 .dropOut(0.25)
 95                 .build()
 96         )
 97         .layer(1, new OutputLayer.Builder(LossFunctions.LossFunction.MCXENT)
 98             .nIn(numHidden)
 99             .nOut(outputNum)
100             .activation("softmax")
101             .build()
102         )
103         .build();
104     MultiLayerNetwork model = new MultiLayerNetwork(conf);
105     model.init();
106     model.fit(train);
107 
108     log.info("\nEvaluating model:\n");
109     Evaluation eval = new Evaluation(outputNum);
110     INDArray output = model.output(test.getFeatureMatrix());
111 
112     for (int i = 0; i < output.rows(); i++) {
113       String target = test.getLabels().getRow(i).toString();
114       String predicted = output.getRow(i).toString();
115       log.info("target: " + target + " predicted: " + predicted);
116     }
117 
118     eval.eval(test.getLabels(), output);
119     log.info(eval.stats());
120 
121     /**
122      * Save the model for reuse:
123      */
124     OutputStream fos = Files.newOutputStream(Paths.get("saved-model.bin"));
125     DataOutputStream dos = new DataOutputStream(fos);
126     Nd4j.write(model.params(), dos);
127     dos.flush();
128     dos.close();
129     FileUtils.writeStringToFile(
130        new File("conf.json"),
131                 model.getLayerWiseConfigurations().toJson());
132 
133     /**
134      * Load saved model and test again:
135      */
136     log.info("\nLoad saved model from disk:\n");
137     MultiLayerConfiguration confFromJson =
138 	  MultiLayerConfiguration.fromJson(
139                      FileUtils.readFileToString(new File("conf.json")));
140     DataInputStream dis = new DataInputStream(
141                                 new FileInputStream("saved-model.bin"));
142     INDArray newParams = Nd4j.read(dis);
143     dis.close();
144     MultiLayerNetwork savedModel = new MultiLayerNetwork(confFromJson);
145     savedModel.init();
146     savedModel.setParameters(newParams);
147 
148     log.info("\nEvaluating model loaded from disk:\n");
149     Evaluation eval2 = new Evaluation(outputNum);
150     INDArray output2 = savedModel.output(test.getFeatureMatrix());
151 
152     for (int i = 0; i < output2.rows(); i++) {
153       String target = test.getLabels().getRow(i).toString();
154       String predicted = output.getRow(i).toString();
155       log.info("target: " + target + " predicted: " + predicted);
156     }
157 
158     eval2.eval(test.getLabels(), output2);
159     log.info(eval2.stats());
160   }
161 }
```

In line 71 we set **fractionOfDataForTraining** to 0.7 which means that we will use 70% of the available data for training and 30% for testing. It is very important to not use training data for testing because performance on recognizing training data should always be good assuming that you have enough memory capacity in a network (i.e., enough hidden units and enough neurons in each hidden layer). In lines 78 through 81 we divide our data into training and testing disjoint sets.

In line 86 we are setting three meta learning parameters: learning rate for the first set of weights between the input and hidden layer to be 1e-1, setting the model to use regularization, and setting the learning rate for the hidden to output weights to be 2e-4.

In line 95 we are setting the dropout factor, here saying that we will randomly not use 25% of the neurons for any given training example. Along with regularization, using dropout helps prevent overfitting. Overfitting occurs when a neural netowrk fails to generalize and learns noise in training data. The goal is to learn important features that affect the utility of a trained model for processing new data. We don’t want to learn random noise in the data as important features. Another way to prevent overfitting is to use the smallest possible number of neurons in hidden labels and still perform well on the independent test data.

After training the model in lines 105 through 107, we test the model (lines 110 through 120) on the separate test data. The program output when I ran the model is:

```
Evaluating model:

14:59:46.872 [main] INFO  c.m.d.DeepBeliefNetworkWisconsinData -
                                  target: [ 1.00, 0.00] predicted: [ 0.76, 0.24]
14:59:46.873 [main] INFO  c.m.d.DeepBeliefNetworkWisconsinData -
                                  target: [ 1.00, 0.00] predicted: [ 0.65, 0.35]

Actual Class 0 was predicted with Predicted 0 with count 151 times

Actual Class 1 was predicted with Predicted 0 with count 44 times

==========================Scores========================================
 Accuracy:  0.7744
 Precision: 0.7744
 Recall:    1
 F1 Score:  0.8728323699421966
===========================================================================
```

The F1 score is calculated as twice precision times recall, all divided by precision + recall. We would like F1 to be as close to 1.0 as possible and it is common to spend a fair amount of time experimenting with meta learning paramters to increase F1.

It is also fairly common to try to learn good values of meta learning paramters also. We won’t do this here but the process involves splitting the data into three disjoint sets: training, validation, and testing. The meta parameters are varied, training is performed, and using the validation data the best set of meta parameters is selected. Finally, we test the netowrk as defined my meta parameters and learned weights for those meta parameters with the separate test data to see what the effective F1 score is.

### Deep Learning Wrapup

I first used complex neural network topologies in the late 1980s for phoneme (speech) recognition, specifically using time delay neural networks and I gave a talk about it at [IEEE First Annual International Conference on Neural Networks San Diego, California June 21-24, 1987](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?reload=true&arnumber=4307059). Back then, neural networks were not really considered to be a great technology for this application but in the present time Google, Microsoft, and other companies are using deep (many layered) neural networks for speech and image recognition. Exciting work is also being done in the field of natural language processing. I just provided a small example in this chapter that you can experiment with easily. I wanted to introduce you to [Deeplearning4j](http://deeplearning4j.org/) because I think it is probably the easiest way for Java developers to get started working with many layered neural networks and I refer you to [the project documentation](http://deeplearning4j.org/documentation.html).

## Web Scraping Examples

Except for the first chapter on network programming techniques, this chapter, and the final chapter on what I call Knowledge Management-Lite, this book is primarily about machine learning in one form or another. As a practical matter, much of the data that many people use for machine learning either comes from the web or from internal data sources. This short chapter provides some guidance and examples for getting text data from the web.

In my work I usually use the Ruby scripting language for web scraping and information gathering (as I wrote about in my APress book [Scripting Intelligence Web 3.0 Information Gathering and Processing](http://www.apress.com/9781430223511)) but there is also good support for using Java for web scraping and since this is a book on modern Java development, we will use Java in this chapter.

Before we start a technical discusion about “web scraping” I want to point out to you that much of the information on the web is copyright and the first thing that you should do is to read the terms of service for web sites to insure that your use of “scraped” or “spidered” data conforms with the wishes of the persons or organizations who own the content and pay to run scraped web sites.

### Motivation for Web Scraping

As we will see in the next chapter on linked data there is a huge amount of structured data available on the web via web services, semantic web/linked data markup, and APIs. That said, you will frequently find data that is useful to pull raw text from web sites but this text is usually fairly unstructured and in a messy (and frequently changing) format as web pages meant for human consumption and not meant to be ingested by software agents. In this chapter we will cover useful “web scraping” techniques. You will see that there is often a fair amount of work in dealing with different web design styles and layouts. To make things even more inconvenient you might find that your software information gathering agents will often break because of changes in web sites.

I tend to use one of three general techniques for scraping web sites. Only the first two will be covered in this chapter:

*   Use an HTML parsing library that strips all HTML markup and Javascript from a page and returns a “pure text” block of text. Here the text in navigation menus, headers, etc. will be interspersed with what we might usually think of a “content” from a web site.
*   Exploit HTML DOM (Document Omject MOdel) formatting information on web sites to pick out headers, page titles, navigation menues, and large blocks of content text.
*   Use a tool like (Selenium)[http://docs.seleniumhq.org/] to programatically control a web browser so your software agents can login to site and otherwise perform navigation. In other words your software agents can simulate a human using a web browser.

I seldom need to use tools like Selenium but as the saying goes “when you need them, you need them.” For simple sites I favor extracting all text as a single block and use DOM processing as needed.

I am not going to cover the use of Selenium and the Java Selenium Web-Driver APIs in this chapter because, as I mentioned, I tend to not use it frequently and I think that you are unlikely to need to do so either. I refer you to the Selenium documentation if the first two approaches in the last list do not work for your application. Selenium is primarily intended for building automating testing of complex web applications, so my occasional use in web spidering is not the common use case.

I assume that you have some experience with HTML and DOM. For reference, the following figure shows a small part of the DOM for a page on one of my web sites:

![Using the Chrome Developer Tools](images/00023.jpeg)

Using the Chrome Developer Tools

This screen shot shows the Chrome web browser developer tools, specifically viewing the page’s DOM. Since a DOM is a tree data structure it is useful to be able to collapse or to expand sub-trees in the DOM. In this figure, the HTML BODY element contains two top level DIV elements. The first DIV that contains the navigation menu for my site is collapes. The second DIV contains an H2 heading and various nested DIV and P (paragraph) elements. I show this fragment of my web pagenot as an example of clean HTML coding but rather as an example of how messy and nested web page elements can be.

### Using the jsoup Library

We will use the MIT licensed library [jsoup](http://jsoup.org/). One reason I selected jsoup for the examples in this chapter out of many fine libraries that provide similar functionality is the particularly nice documentation, especially [The jsoup Cookbook](http://jsoup.org/cookbook/) which I urge you to bookmark as a general reference. In this chapter I will concentrate on just the most frequent web scraping use cases that I use in my own work.

The following bit of code uses jsoup to get the text inside all P (paragraph) elements that are direct children of any DIV element. On line 14 we use the jsoup library to fetch my home web page:

```
 1 package com.markwatson.web_scraping;
 2 
 3 import org.jsoup.*;
 4 import org.jsoup.nodes.Document;
 5 import org.jsoup.nodes.Element;
 6 import org.jsoup.select.Elements;
 7 
 8 /**
 9  * Examples of using jsoup
10  */
11 public class MySitesExamples {
12 
13   public static void main(String[] args) throws Exception {
14     Document doc = Jsoup.connect("http://www.markwatson.com").get();
15     Elements newsHeadlines = doc.select("div p");
16     for (Element element : newsHeadlines) {
17       System.out.println(" next element text: " + element.text());
18     }
19   }
20 }
```

In line 15 I am selecting the pattern that returns all P elements that are direct children of any DIV element and in lines 16 to 18 print the text inside these P elements.

For training data for machine learning it is useful to just grab all text on a web page and assume that common phrases dealing with web navigaion, etc. will be dropped from learned models because they occur in many different training examples for different classifications. The following code snippet shows how to fetch the plain text from an entire web page:

```
 Document doc = Jsoup.connect("http://www.markwatson.com").get();
    String all_page_text = doc.text();
    System.out.println("All text on web page:\n" + all_page_text);
```

```
All text on web page:
Mark Watson: Consultant specializing in machine learning and artificial intellig\
ence Toggle navigation Mark Watson Home page Consulting Free mentoring Blog Book\
s Open Source Fun Consultant specializing in machine learning, artificial intell\
igence, cognitive computing, and web engineering...
```

The 2gram (i.e., two words in sequence) “Toggle navigation” in the last listing has nothing to do with the real content in my site and is an artifact of using the Bootstrap CSS and Javascript tools. Often “noise” like this is simply ignored by machine learning models if it appears on many different sites but beware that this might be a problem and you might need to precisiely fetch text from specific DOM elements. Similarly, notice that this last listing picks up the plain text from the navigation menus.

The following code snippet finds HTML anchor elements and prints the data associated with these elements:

```
 Document doc = Jsoup.connect("http://www.markwatson.com").get();
    Elements anchors = doc.select("a[href]");
    for (Element anchor : anchors) {
      String uri = anchor.attr("href");
      System.out.println(" next anchor uri: " + uri);
      System.out.println(" next anchor text: " + anchor.text());
    }
```

```
 1  next anchor uri: #
 2  next anchor text: Mark Watson
 3  next anchor uri: /
 4  next anchor text: Home page
 5  next anchor uri: /consulting/
 6  next anchor text: Consulting
 7  next anchor uri: /mentoring/
 8  next anchor text: Free mentoring
 9  next anchor uri: http://blog.markwatson.com
10  next anchor text: Blog
11  next anchor uri: /books/
12  next anchor text: Books
13  next anchor uri: /opensource/
14  next anchor text: Open Source
15  next anchor uri: /fun/
16  next anchor text: Fun
17  next anchor uri: http://www.cognition.tech
18  next anchor text: www.cognition.tech
19  next anchor uri: https://github.com/mark-watson
20  next anchor text: GitHub
21  next anchor uri: https://plus.google.com/117612439870300277560
22  next anchor text: Google+
23  next anchor uri: https://twitter.com/mark_l_watson
24  next anchor text: Twitter
25  next anchor uri: http://www.freebase.com/m/0b6_g82
26  next anchor text: Freebase
27  next anchor uri: https://www.wikidata.org/wiki/Q18670263
28  next anchor text: WikiData
29  next anchor uri: https://leanpub.com/aijavascript
30  next anchor text: Build Intelligent Systems with JavaScript
31  next anchor uri: https://leanpub.com/lovinglisp
32  next anchor text: Loving Common Lisp, or the Savvy Programmer's Secret Weapon
33  next anchor uri: https://leanpub.com/javaai
34  next anchor text: Practical Artificial Intelligence Programming With Java
35  next anchor uri: http://markwatson.com/index.rdf
36  next anchor text: XML RDF
37  next anchor uri: http://markwatson.com/index.ttl
38  next anchor text: Turtle RDF
39  next anchor uri: https://www.wikidata.org/wiki/Q18670263
40  next anchor text: WikiData
```

Notice that there are diffent types of URIs like #, relative, and absolute. Any characters following a # character do not affect the routing of which web page is shown (or which API is called) but the characters after the # character are available for use in specifying anchor positions on a web page or extra parameters for API calls. Relative APIs like /consulting/ (as seen in line 5) are understood to be relative to the base URI of the web site.

I often require that URIs be absolute URIs (i.e., starts with a protocol like “http:” or “https:”) and the following code snippet selects just absolute URI anchors:

```
1     Elements absolute_uri_anchors = doc.select("a[href]");
2     for (Element anchor : absolute_uri_anchors) {
3       String uri = anchor.attr("abs:href");
4       System.out.println(" next anchor absolute uri: " + uri);
5       System.out.println(" next anchor absolute text: " + anchor.text());
6     }
```

In line 3 I am specifying the attribute as “abs:href” to be more selective:

```
 next anchor absolute text: Mark Watson
 next anchor absolute uri: http://www.markwatson.com/
 next anchor absolute text: Home page
 next anchor absolute uri: http://www.markwatson.com/consulting/
 next anchor absolute text: Consulting
 next anchor absolute uri: http://www.markwatson.com/mentoring/
 next anchor absolute text: Free mentoring
 next anchor absolute uri: http://blog.markwatson.com
 next anchor absolute text: Blog
 ...
```

### Wrap Up

I just showed you quick reference to the most common use cases for my work. What I didn’t show you was an example for organizing spidered information for reuse.

I sometimes collect training data for machine learning by using web searches with query keywords tailored to find information in specific categories. I am not covering automating web search in this book but I would like to refer you to an open source wrapper that I wrote for [Microsoft’s Bing Search APIs](https://github.com/mark-watson/bing_search_java) on github. As an example, just to give you an idea for experimentation, if you wanted to train a model to categorize text containing car descriptions into two classes: “US domestic cars” “foreign made cars” thsn you might use search queries like “cars Ford Chevy” and “cars Volvo Volkswagen Peugeot” to get example text for these two categories.

If you use the Bing Search APIs for collecting training data, then you can for the top ranked search results use the techniques covered in this chapter to retreive the text from the original web pages. Then use one or more of the machine learning techniques covered in this book to build classification models. This is a good technique and some people might even consider it a super power.

For machine learning, I sometimes collect text in file names that indicate the classification of the text in each file. I often also collect data in a NOSQL datastore like MongoDB or CouchDB, or use a relational database like Postgres to store training data for future reuse.

## Linked Data

This chapter introduces you to techniques for information architecture and development using linked data and semantic web technologies. This chapter is paired with the next chapter on knowledge management so please read these two chapters in order.

**Note:** I published “Practical Semantic Web and Linked Data Applications: Java, JRuby, Scala, and Clojure Edition” and you can get a [free PDF of this book here](http://www.markwatson.com/opencontent_data/book_java.pdf). While the technical details of that book are still relevant, I am now more opinionated about which linked data and semantic web technologies are most useful so this chapter is more focused. With some improvements, I use the Java client code for DBPedia search and SPARQL queries from my previous book. I also include new versions that return query results as JSON. I am going to assume that you have fetched a free copy of my book “Practical Semantic Web and Linked Data Applications” and use chapters 6 and 7 for an introduction to the Resource Definition Language (RDF and RDFS) and chapter 8 for a tutorial on the SPARQL query language. It is okay to read this background material later if you want to dive right into the examples in this chapter. I do provide a quick introduction to SPARQL and RDF i the next section, but please do also get a free copy of my semantic web book for a longer treatment. We use the standard query language SPARQL to retrieve information from RDF data sources in much the same way that we use SQL to retrieve information from relational databases.

In this chapter we will look at consuming linked data using SPARQL queries against public RDF data stores and searching DBPedia. Using the code from the earlier chapter “Natural Language Processing Using OpenNLP” we will also develop an example application that annotates text by tagging entities with unique DBPedia URIs for the entities (we will use this example also in the next chapter in a code example for knowledge Management).

**Why** **use** **linked** **data?**

Before we jump into technical details I want to give you some motivation for why you might use linked data and semantic web technologies to organize and access information. Suppose that your company sells products to customers and your task is to augment the relational databases used for ordering, shipping, and customer data with a new system that needs to capture relationships between products, customers, and information sources on the web that might help both your customers and customer support staff increase the utility of your products to your customers.

Customers, products, and information sources are entities that will sometimes be linked with properties or relationships with other entities. This new data will be unstructured and you do not know ahead of time all of the relationships and what new types of entities that the new system will use. If you come from a relational database background using an sort of graph database might be uncomfortable at first. As motivation consider that Google uses its Knowledge Graph (I customized the Knowledge Graph when I worked at Google) for internal applications, to add value to search results, and to power Google Now. Facebook uses its Open Graph to store information about uses, user posts, and relationships between users and posted material. These graph data stores are key assets for Google and Facebook. Just because you don’t deal with huge amounts of data does not mean that the flexibility of graph data is not useful for your projects! We will use the DBPedia graph database in this chapter for the example programs. DBPedia (which Google used as core knowledge when developing their Knowledge Graph) is a rich information source for typed data for products, people, companies, places, etc. Connecting internal data in your organization to external data sources like DBPedia increases the utility of yor private data. You can make this data sharing relationship symmetrical by selectively publishing some of your internal data externally as linked data for the benefit of your customers and business partners.

The key idea is to design the shape of your information (what entities do you deal with and what types of properties or relationships exist between different types of entities), ingest data into a graph database with a plan for keeping everything up to date, and then provide APIs or a query language so application programmers can access this linked data when developing new applications. In this chapter we will use semantic web standards with the SPARQL query language to access data but these ideas should apply to using other graph databases like Neo4J or non-relational data stores like MongoDB or CouchDB.

### Example Code

The examples for this chapter are set up to run either from the command line or using IntelliJ.

There are three examples in this chapter. If you want to try running the code before reading the rest of the chapter, run each maven test separately:

```
1     mvn test -Dtest=AnnotationTest
2     mvn test -Dtest=DBPediaTest
3     mvn test -Dtest=SparqlTest
```

The following figure shows the project for this chapter in the Community Edition of IntelliJ:

![IntelliJ project view for the examples in this chapter](images/00024.jpeg)

IntelliJ project view for the examples in this chapter

### Overview of RDF and SPARQL

The Resource Description Framework (RDF) is used to store information as subject/predicate/object triple values. RDF data was originally encoded as XML and intended for automated processing. In this chapter we will use two simple to read formats called “N-Triples” and “N3.” RDF data consists of a set of triple values:

*   subject
*   predicate
*   object

As an example, suppose our application involved news stories and we wanted a way to store and query meta data. We might do this by extracting semantic information from the text, and storing it in RDF. I will use this application domain for the examples in this chapter. We might use triples like:

*   subject: a URL (or URI) of a news article
*   predicate: a relation like “containsPerson”
*   object: a value like “Bill Clinton”

As previously mentioned, we will use either URIs or string literals as values for subjects and objects. We will always use URIs for the values of predicates. In any case URIs are usually preferred to string literals because they are unique. We will see an example of this preferred use but first we need to learn the N-Triple and N3 RDF formats.

Any part of a triple (subject, predicate, or object) is either a URI or a string literal. URIs encode namespaces. For example, the containsPerson predicate in the last example could properly be written as:

```
1 http://knowledgebooks.com/ontology/#containsPerson
```

The first part of this URI is considered to be the namespace for (what we will use as a predicate) “containsPerson.” When different RDF triples use this same predicate, this is some assurance to us that all users of this predicate subscribe to the same meaning. Furthermore, we will see in [Section on RDFS](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) that we can use RDFS to state equivalency between this predicate (in the namespace http://knowledgebooks.com/ontology/) with predicates represented by different URIs used in other data sources. In an “artificial intelligence” sense, software that we write does not understand a predicate like “containsPerson” in the way that a human reader can by combining understood common meanings for the words “contains” and “person” but for many interesting and useful types of applications that is fine as long as the predicate is used consistently. We will see shortly that we can define abbreviation prefixes for namespaces which makes RDF and RDFS files shorter and easier to read.

A statement in N-Triple format consists of three URIs (or string literals – any combination) followed by a period to end the statement. While statements are often written one per line in a source file they can be broken across lines; it is the ending period which marks the end of a statement. The standard file extension for N-Triple format files is *.nt and the standard format for N3 format files is *.n3.

My preference is to use N-Triple format files as output from programs that I write to save data as RDF. I often use Sesame to convert N-Triple files to N3 if I will be reading them or even hand editing them. You will see why I prefer the N3 format when we look at an example:

```
1 @prefix kb:  <http://knowledgebooks.com/ontology#> .
2 <http://news.com/201234 /> kb:containsCountry "China"  .
```

Here we see the use of an abbreviation prefix “kb:” for the namespace for my company KnowledgeBooks.com ontologies. The first term in the RDF statement (the subject) is the URI of a news article. The second term (the predicate) is “containsCountry” in the “kb:” namespace. The last item in the statement (the object) is a string literal “China.” I would describe this RDF statement in English as, “The news article at URI http://news.com/201234 mentions the country China.”

This was a very simple N3 example which we will expand to show additional features of the N3 notation. As another example, suppose that this news article also mentions the USA. Instead of adding a whole new statement like this:

```
1     @prefix kb:  <http://knowledgebooks.com/ontology#> .
2     <http://news.com/201234 /> kb:containsCountry "China"  .
3     <http://news.com/201234 /> kb:containsCountry "USA"  .
```

we can combine them using N3 notation. N3 allows us to collapse multiple RDF statements that share the same subject and optionally the same predicate:

```
1     @prefix kb:  <http://knowledgebooks.com/ontology#> .
2     <http://news.com/201234 /> kb:containsCountry "China" ,
3                                                   "USA" .
```

We can also add in additional predicates that use the same subject:

```
 1     @prefix kb:  <http://knowledgebooks.com/ontology#> .
 2 
 3     <http://news.com/201234 /> kb:containsCountry "China" ,
 4                                                   "USA" .
 5         kb:containsOrganization "United Nations" ;
 6         kb:containsPerson "Ban Ki-moon" , "Gordon Brown" ,
 7                           "Hu Jintao" , "George W. Bush" ,
 8                           "Pervez Musharraf" ,
 9                           "Vladimir Putin" , 
10                           "Mahmoud Ahmadinejad" .
```

This single N3 statement represents ten individual RDF triples. Each section defining triples with the same subject and predicate have objects separated by commas and ending with a period. Please note that whatever RDF storage system we use (we will be using Sesame) it makes no difference if we load RDF as XML, N-Triple, of N3 format files: internally subject, predicate, and object triples are stored in the same way and are used in the same way.

I promised you that the data in RDF data stores was easy to extend. As an example, let us assume that we have written software that is able to read online news articles and create RDF data that captures some of the semantics in the articles. If we extend our program to also recognize dates when the articles are published, we can simply reprocess articles and for each article add a triple to our RDF data store using a form like:

```
1     <http://news.com/201234 /> kb:datePublished
2                                "2008-05-11" .
```

Furthermore, if we do not have dates for all news articles that is often acceptable depending on the application.

SPARQL is a query language used to query RDF data stores. While SPARQL may initially look like SQL, there are some important differences like support for RDFS and OWL inferencing. We will cover the basics of SPARQL in this section.

We will use the following sample RDF data for the discusion in this section:

```
 1     @prefix kb:  <http://knowledgebooks.com/ontology#> .
 2     @prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .
 3 
 4     kb:containsCity rdfs:subPropertyOf kb:containsPlace .
 5 
 6     kb:containsCountry rdfs:subPropertyOf kb:containsPlace .
 7 
 8     kb:containsState rdfs:subPropertyOf kb:containsPlace .
 9 
10     <http://yahoo.com/20080616/usa_flooding_dc_16 />
11         kb:containsCity "Burlington" , "Denver" ,
12                         "St. Paul" ," Chicago" ,
13                         "Quincy" , "CHICAGO" ,
14                         "Iowa City" ;
15         kb:containsRegion "U.S. Midwest" , "Midwest" ;
16         kb:containsCountry "United States" , "Japan" ;
17         kb:containsState "Minnesota" , "Illinois" , 
18                          "Mississippi" , "Iowa" ;
19         kb:containsOrganization "National Guard" ,
20                          "U.S. Department of Agriculture" ,
21                          "White House" ,
22                          "Chicago Board of Trade" ,
23                          "Department of Transportation" ;
24         kb:containsPerson "Dena Gray-Fisher" ,
25                           "Donald Miller" ,
26                           "Glenn Hollander" ,
27                           "Rich Feltes" ,
28                           "George W. Bush" ;
29         kb:containsIndustryTerm "food inflation" , "food" ,
30                                 "finance ministers" ,
31                                 "oil" .
32 
33     <http://yahoo.com/78325/ts_nm/usa_politics_dc_2 />
34         kb:containsCity "Washington" , "Baghdad" ,
35                         "Arlington" , "Flint" ;
36         kb:containsCountry "United States" ,
37                            "Afghanistan" ,
38                            "Iraq" ;
39         kb:containsState "Illinois" , "Virginia" ,
40                          "Arizona" , "Michigan" ;
41         kb:containsOrganization "White House" ,
42                                 "Obama administration" ,
43                                 "Iraqi government" ;
44         kb:containsPerson "David Petraeus" ,
45                           "John McCain" ,
46                           "Hoshiyar Zebari" ,
47                           "Barack Obama" ,
48                           "George W. Bush" ,
49                           "Carly Fiorina" ;
50         kb:containsIndustryTerm "oil prices" .
51 
52     <http://yahoo.com/10944/ts_nm/worldleaders_dc_1 />
53         kb:containsCity "WASHINGTON" ;
54         kb:containsCountry "United States" , "Pakistan" ,
55                            "Islamic Republic of Iran" ;
56         kb:containsState "Maryland" ;
57         kb:containsOrganization "University of Maryland" ,
58                                 "United Nations" ;
59         kb:containsPerson "Ban Ki-moon" , "Gordon Brown" ,
60                           "Hu Jintao" , "George W. Bush" ,
61                           "Pervez Musharraf" ,
62                           "Vladimir Putin" ,
63                           "Steven Kull" ,
64                           "Mahmoud Ahmadinejad" .
65 
66     <http://yahoo.com/10622/global_economy_dc_4 />
67         kb:containsCity "Sao Paulo" , "Kuala Lumpur" ;
68         kb:containsRegion "Midwest" ;
69         kb:containsCountry "United States" , "Britain" ,
70                            "Saudi Arabia" , "Spain" ,
71                            "Italy" , India" , 
72                            ""France" , "Canada" ,
73                            "Russia" , "Germany" , "China" ,
74                            "Japan" , "South Korea" ;
75         kb:containsOrganization "Federal Reserve Bank" ,
76                                 "European Union" ,
77                                 "European Central Bank" ,
78                                 "European Commission" ;
79         kb:containsPerson "Lee Myung-bak" , "Rajat Nag" ,
80                           "Luiz Inacio Lula da Silva" ,
81                           "Jeffrey Lacker" ;
82         kb:containsCompany "Development Bank Managing" ,
83                            "Reuters" ,
84                            "Richmond Federal Reserve Bank" ;
85         kb:containsIndustryTerm "central bank" , "food" ,
86                                 "energy costs" ,
87                                 "finance ministers" ,
88                                 "crude oil prices" ,
89                                 "oil prices" ,
90                                 "oil shock" ,
91                                 "food prices" ,
92                                 "Finance ministers" ,
93                                 "Oil prices" , "oil" .
```

In the following examples, we will look at queries but not the results. We will start with a simple SPARQL query for subjects (news article URLs) and objects (matching countries) with the value for the predicate equal to $containsCountry$:

```
1     SELECT ?subject ?object
2       WHERE {
3         ?subject
4         http://knowledgebooks.com/ontology#containsCountry>
5         ?object .
6       }
```

Variables in queries start with a question mark character and can have any names. We can make this query easier and reduce the chance of misspelling errors by using a namespace prefix:

```
1     PREFIX kb:  <http://knowledgebooks.com/ontology#>
2     SELECT ?subject ?object
3       WHERE {
4           ?subject kb:containsCountry ?object .
5       }
```

We could have filtered on any other predicate, for instance $containsPlace$. Here is another example using a match against a string literal to find all articles exactly matching the text “Maryland.” The following queries were copied from Java source files and were embedded as string literals so you will see quotation marks backslash escaped in these examples. If you were entering these queries into a query form you would not escape the quotation marks.

```
1     PREFIX kb: <http://knowledgebooks.com/ontology#>
2        SELECT ?subject
3        WHERE { ?subject kb:containsState \"Maryland\" . }
```

We can also match partial string literals against regular expressions:

```
1     PREFIX kb:  
2     SELECT ?subject ?object
3        WHERE {
4          ?subject
5          kb:containsOrganization
6          ?object FILTER regex(?object, \"University\") .
7        }
```

Prior to this last example query we only requested that the query return values for subject and predicate for triples that matched the query. However, we might want to return all triples whose subject (in this case a news article URI) is in one of the matched triples. Note that there are two matching triples, each terminated with a period:

```
 1     PREFIX kb: <http://knowledgebooks.com/ontology#>
 2     SELECT ?subject ?a_predicate ?an_object
 3        WHERE {
 4         ?subject
 5         kb:containsOrganization
 6         ?object FILTER regex(?object, \"University\") .
 7 
 8         ?subject ?a_predicate ?an_object .
 9        }
10        DISTINCT
11        ORDER BY ?a_predicate  ?an_object
12        LIMIT 10
13        OFFSET 5
```

When WHERE clauses contain more than one triple pattern to match, this is equivalent to a Boolean “and” operation. The DISTINCT clause removes duplicate results. The ORDER BY clause sorts the output in alphabetical order: in this case first by predicate (containsCity, containsCountry, etc.) and then by object. The LIMIT modifier limits the number of results returned and the OFFSET modifier sets the number of matching results to skip.

We are finished with our quick tutorial on using the SELECT query form. There are three other query forms that I am not covering in this chapter:

*   CONSTRUCT – returns a new RDF graph of query results
*   ASK – returns Boolean true or false indicating if a query matches any triples
*   DESCRIBE – returns a new RDF graph containing matched resources

### SPARQL Query Client

There are many available public RDF data sources. Some examples of publicly available SPARQL endpoints are:

*   [DBPedia](http://dbpedia.org/sparql) which encodes the structured information in Wikipedia info boxes as RDF data. The DBPedia data is also available as a free download for hosting on your own SPARQL endpoint.
*   [LinkDb](http://www.genome.jp/linkdb/linkdb_rdf.html) Which contains human genome data
*   [Library of Congress](http://id.loc.gov/techcenter/searching.html) There is currently no SPARQL endpoint provided but subject matter Sparql data is available for download for use on your own SPARQL endpoint and there is a search faclity that can return RDF data results.
*   [BBC Programs and Music](http://lod.openlinksw.com/sparql/)
*   [FactForge](http://factforge.net/sparql) Combines RDF data from a many sources including DBPedia, Geonames, Wordnet, and Freebase. The SPARQL query page has many great examples to get you started. For example, look at the SPARQL for the query and results for “Show the distance from London of airports located at most 50 miles away from it.”

There are many public SPARQL endpoints on the web but I need to warn you that they are not always available. The raw RDF data for most public endpoints is usually available so if you are building a system relying on a public data set you should consider hosting a copy of the data on one of your own servers. I usually use one of the following RDF repositories and SPARQL query interfaces: [Star Dog](http://stardog.com/), [Virtuoso](http://virtuoso.openlinksw.com/), and [Sesame](http://rdf4j.org/). That said, there are many other fine RDF repository server options, both commercial and open source. After reading this chapter, you may want to read a fairly recent [blog article](http://blog.markwatson.com/2014/07/using-opencyc-rdfowl-data-in-stardog.html) I wrote for importing and using the OpenCYC world knowledge base in to a local repository.

In the next two sections you will learn how to make SPARQL queries against RDF data stores on the web, getting results both as JSON and parsed out to Java data values. A major theme in the next chapter is combining data in the “cloud” with local data.

#### JSON Client

```
 1 package com.markwatson.linkeddata;
 2 
 3 import org.apache.http.HttpResponse;
 4 import org.apache.http.client.methods.HttpGet;
 5 import org.apache.http.impl.client.DefaultHttpClient;
 6 
 7 import java.io.BufferedReader;
 8 import java.io.InputStreamReader;
 9 import java.net.URLEncoder;
10 
11 public class SparqlClientJson {
12   public static String query(String endpoint_URL, String sparql)
13                        throws Exception {
14     StringBuffer sb = new StringBuffer();
15     try {
16       org.apache.http.client.HttpClient httpClient =
17 	    new DefaultHttpClient();
18       String req = URLEncoder.encode(sparql, "utf-8");
19       HttpGet getRequest =
20           new HttpGet(endpoint_URL + "?query=" + req);
21       getRequest.addHeader("accept", "application/json");
22       HttpResponse response = httpClient.execute(getRequest);
23       if (response.getStatusLine().getStatusCode() != 200)
24 	     return "Server error";
25 
26       BufferedReader br =
27           new BufferedReader(
28               new InputStreamReader(
29 				   (response.getEntity().getContent())));
30       String line;
31       while ((line = br.readLine()) != null) {
32         sb.append(line);
33       }
34       httpClient.getConnectionManager().shutdown();
35     } catch (Exception e) {
36       e.printStackTrace();
37     }
38     return sb.toString();
39   }
40 }
```

We will be using the SPARQL query for finding people who were born in Arizona:

```
1 PREFIX foaf: <http://xmlns.com/foaf/0.1/>
2         PREFIX dbpedia2: <http://dbpedia.org/property/>
3         PREFIX dbpedia: <http://dbpedia.org/>
4         SELECT ?name ?person WHERE {
5              ?person dbpedia2:birthPlace <http://dbpedia.org/resource/Arizona> .
6              ?person foaf:name ?name .
7         }
8         LIMIT 10
```

You can run the unit tests for the DBPedia lookups and SPARQL queries using:

```
1 mvn test -Dtest=DBPediaTest
```

Here is a small bit of the output produced when running the unit test for this class with this example SPARQL query:

```
{
  "head": {
    "link": [],
    "vars": [
      "name",
      "person"
    ]
  },
  "results": {
    "distinct": false,
    "ordered": true,
    "bindings": [
      {
        "name": {
          "type": "literal",
          "xml:lang": "en",
          "value": "Ryan David Jahn"
        },
        "person": {
          "type": "uri",
          "value": "http://dbpedia.org/resource/Ryan_David_Jahn"
        }
      },
      ...
	]
	...
  },
 }
```

This example uses the DBPedia SPARQL endpoint. There is another public DBPedia service for looking up names and we will look at it in the next section.

### DBPedia Entity Lookup

Later in this chapter I will show you what the raw DBPedia data looks like. For this section we will access DBPdedia through a public search API. The following two sub-sections show example code for getting the DBPedia lookup results as Java data and as JSON data.

#### Java Data Client

In the DBPedia Lookup service that we use in this section I only list a bit of the example program for this section. This example is fairly long and I refer you to the source code.

```
 1 public class DBpediaLookupClient extends DefaultHandler {
 2   public DBpediaLookupClient(String query) throws Exception {
 3     this.query = query;
 4     HttpClient client = new HttpClient();
 5 
 6     String query2 = query.replaceAll(" ", "+");
 7     HttpMethod method =
 8         new GetMethod(
 9           "http://lookup.dbpedia.org/api/search.asmx/KeywordSearch?QueryString="\
10  +
11           query2);
12     try {
13       client.executeMethod(method);
14       InputStream ins = method.getResponseBodyAsStream();
15       SAXParserFactory factory = SAXParserFactory.newInstance();
16       SAXParser sax = factory.newSAXParser();
17       sax.parse(ins, this);
18     } catch (HttpException he) {
19       System.err.println("Http error connecting to lookup.dbpedia.org");
20     } catch (IOException ioe) {
21       System.err.println("Unable to connect to lookup.dbpedia.org");
22     }
23     method.releaseConnection();
24   }
25 
26   public void printResults(List<Map<String, String>> results) {
27     for (Map<String, String> result : results) {
28       System.out.println("\nNext result:\n");
29       for (String key : result.keySet()) {
30         System.out.println("  " + key + "\t:\t" + result.get(key));
31       }
32     }
33   }
34 
35   //  ... XML parsing code not shown ...
36   
37   public List<Map<String, String>> variableBindings() {
38     return variableBindings;
39   }
40 }
```

The DBPedia Lookup service returns XML response data by default. The **DBpediaLookupClient** class is fairly simple. It encodes a query string, calls the web service, and parses the XML payload that is returned from the service.

You can run the unit tests for the DBPedia lookups and SPARQL queries using:

```
1 mvn test -Dtest=DBPediaTest
```

Sample output for looking up “London” showing values for map key “Description”, “Label”, and “URI” in the fetched data looks like:

```
1   Description	:	The City of London was a United Kingdom Parliamentary constituen\
2 cy. It was a constituency of the House of Commons of the Parliament of England t\
3 hen of the Parliament of Great Britain from 1707 to 1800 and of the Parliament o\
4 f the United Kingdom from 1801 to 1950\. The City of London was a United Kingdom \
5 Parliamentary constituency. It was a constituency of the House of Commons of the\
6  Parliament of England then of the Parliament of Great Britain from 1707 to 1800\
7  and of the Parliament of the United Kingdom from 1801 to 1950.
8   Label	:	United Kingdom Parliamentary constituencies established in 1298
9   URI	:	http://dbpedia.org/resource/City_of_London_(UK_Parliament_constituency)
```

If you run this example program you will see that the description text prints all on one line; it line wraps in the about example.

This example returns a list of maps as a result where each list item is a map which each key is a variable name and each map value is the value for the key. In the next section we will look at similar code that instead returns JSON data.

#### JSON Client

The example in the section is simpler than the one in the last section because we just need to return the payload from the lookup web service as-is (i.e., as JSON data encoded in a string).

```
 1 package com.markwatson.linkeddata;
 2 
 3 import org.apache.http.HttpResponse;
 4 import org.apache.http.client.HttpClient;
 5 import org.apache.http.client.methods.HttpGet;
 6 import org.apache.http.impl.client.DefaultHttpClient;
 7 
 8 import java.io.BufferedReader;
 9 import java.io.InputStreamReader;
10 
11 /**
12  * Copyright 2015 Mark Watson.  Apache 2 license.
13  */
14 public class DBpediaLookupClientJson {
15   public static String lookup(String query) {
16     StringBuffer sb = new StringBuffer();
17     try {
18       HttpClient httpClient = new DefaultHttpClient();
19       String query2 = query.replaceAll(" ", "+");
20       HttpGet getRequest =
21           new HttpGet(
22 		    "http://lookup.dbpedia.org/api/search.asmx/KeywordSearch?QueryString="
23               + query2);
24       getRequest.addHeader("accept", "application/json");
25       HttpResponse response = httpClient.execute(getRequest);
26 	  
27       if (response.getStatusLine().getStatusCode() != 200) return "Server error";
28 
29       BufferedReader br =
30           new BufferedReader(
31               new InputStreamReader((response.getEntity().getContent())));
32       String line;
33       while ((line = br.readLine()) != null) {
34         sb.append(line);
35       }
36       httpClient.getConnectionManager().shutdown();
37     } catch (Exception e) {
38       e.printStackTrace();
39     }
40     return sb.toString();
41   }
42 }
```

You can run the unit tests for the DBPedia lookups and SPARQL queries using:

```
1 mvn test -Dtest=DBPediaTest
```

The following example for the lookup for “Bill Clinton” shows sample JSON (as a string) content that I “pretty printed” using IntelliJ for readability:

```
{
  "results": [
    {
      "uri": "http://dbpedia.org/resource/Bill_Clinton",
      "label": "Bill Clinton",
      "description": "William Jefferson \"Bill\" Clinton (born William Jefferson\
 Blythe III; August 19, 1946) is an American politician who served as the 42nd P\
resident of the United States from 1993 to 2001\. Inaugurated at age 46, he was t\
he third-youngest president. He took office at the end of the Cold War, and was \
the first president of the baby boomer generation. Clinton has been described as\
 a New Democrat. Many of his policies have been attributed to a centrist Third W\
ay philosophy of governance.",
      "refCount": 7034,
      "classes": [
        {
          "uri": "http://dbpedia.org/ontology/OfficeHolder",
          "label": "office holder"
        },
        {
          "uri": "http://dbpedia.org/ontology/Person",
          "label": "person"
        },
        ...
      ],
      "categories": [
        {
          "uri": "http://dbpedia.org/resource/Category:Governors_of_Arkansas",
          "label": "Governors of Arkansas"
        },
        {
          "uri": "http://dbpedia.org/resource/Category:American_memoirists",
          "label": "American memoirists"
        },
        {
          "uri": "http://dbpedia.org/resource/Category:Spouses_of_United_States_\
Cabinet_members",
          "label": "Spouses of United States Cabinet members"
        },
		...
      ],
      "templates": [],
      "redirects": []
    },
```

### Annotate Text with DBPedia Entity URIs

I have used DBPdedia, the semantic web/linked data version of Wikipedia, in several projects. One useful use case is using DBPedia URIs as a unique identifier of a unique real world entity. For example, there are many people named Bill Clinton but usually this name refers to a President of the USA. It is useful to annotate people’s names, company names, etc. in text with the DBPedia URI for that entity. We will do this in a quick and dirty way (but hopefully still useful!) in this section and then solve the same problem in a different way in the next section.

In this section we simply look for exact matches in text for the descriptions for DBPedia URIs. In the next section we tokenize the descriptions and also tokenize the text to match entity names with URIs. I will also show you some samples of the raw DBPedia RDF data in the next section.

For one of my own projects I created mappings of entity names to DBPedia URIs for nine entity classes. For the example in this section I use three of my entity class mappings: people, countries, and companies. The data for these entity classes is stored in text files in the subdirectory dbpedia_entities. Later in this chapter I will show you what the raw DBPedia dump data looks like.

The example program in this section modified input text adding DBPedia URIs after entities recognized in the text.

The annotation code in the following example is simple but not very efficient. See the source code for comments discussing this that I left out of the following listing (edited to fit the page width):

```
 1 package com.markwatson.linkeddata;
 2 
 3 import java.io.BufferedReader;
 4 import java.io.FileInputStream;
 5 import java.io.InputStream;
 6 import java.io.InputStreamReader;
 7 import java.nio.charset.Charset;
 8 import java.util.HashMap;
 9 import java.util.Map;
10 
11 public class AnnotateEntities {
12 
13   /**
14    * @param text - input text to annotate with DBPedia URIs for entities
15    * @return original text with embedded annotations
16    */
17   static public String annotate(String text) {
18     String s = text.replaceAll("\\.", " !! ").replaceAll(",", " ,").
19 	                replaceAll(";", " ;").replaceAll("  ", " ");
20     for (String entity : companyMap.keySet())
21       if (s.indexOf(entity) > -1) s = s.replaceAll(entity, entity +
22 		   " (" + companyMap.get(entity) + ")");
23     for (String entity : countryMap.keySet())
24       if (s.indexOf(entity) > -1) s = s.replaceAll(entity, entity +
25 		   " (" + countryMap.get(entity) + ")");
26     for (String entity : peopleMap.keySet())
27       if (s.indexOf(entity) > -1) s = s.replaceAll(entity, entity +
28 		   " (" + peopleMap.get(entity) + ")");
29     return s.replaceAll(" !!", ".");
30   }
31 
32   static private Map<String, String> companyMap = new HashMap<>();
33   static private Map<String, String> countryMap = new HashMap<>();
34   static private Map<String, String> peopleMap = new HashMap<>();
35   static private void loadMap(Map<String, String> map, String entityFilePath) {
36     try {
37       InputStream fis = new FileInputStream(entityFilePath);
38       InputStreamReader isr =
39         new InputStreamReader(fis, Charset.forName("UTF-8"));
40       BufferedReader br = new BufferedReader(isr);
41       String line = null;
42       while ((line = br.readLine()) != null) {
43         int index = line.indexOf('\t');
44         if (index > -1) {
45           String name = line.substring(0, index);
46           String uri = line.substring((index + 1));
47           map.put(name, uri);
48         }
49       }
50     } catch (Exception ex) {
51       ex.printStackTrace();
52     }
53   }
54   static {
55     loadMap(companyMap, "dbpedia_entities/CompanyNamesDbPedia.txt");
56     loadMap(countryMap, "dbpedia_entities/CountryNamesDbPedia.txt");
57     loadMap(peopleMap, "dbpedia_entities/PeopleDbPedia.txt");
58   }
59 }
```

If you run the unit tests for this code the output looks like:

```
 1 > mvn test -Dtest=AnnotationTest
 2 [INFO] Compiling 5 source files to /Users/markw/BITBUCKET/power-java/linked_data\
 3 /target/classes
 4 
 5 -------------------------------------------------------
 6  T E S T S
 7 -------------------------------------------------------
 8 Running com.markwatson.linkeddata.AnnotationTest
 9 
10 Annotated string: Bill Clinton (<http://dbpedia.org/resource/Bill_Clinton>) went\
11  to a charity event in Thailand (<http://dbpedia.org/resource/Thailand>). 
12 
13 Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.251 sec
14 
15 Results :
16 
17 Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
```

### Resolving Named Entities in Text to Wikipedia URIs

We will solve the same problem in this section as we looked at in the last section: resolving named entities with DBPedia (Wikipedia) URIs but we will use an alternative approach.

I some of my work I find it useful to resolve named entities (e.g., people, organizations, products, locations, etc.) in text to unique DBPedia URIs. The DBPedia semantic web data, which we will also discuss in the next chapter, is derived from the “info boxes” in Wikipedia articles. I find DBPedia to be an incredibly useful knowledge source. When I worked at Google with the Knowledge Graph we were using a core of knowledge from Wikipedia/DBPedia and Freebase with a lot of other information sources. DBPedia is already (reasonably) clean data and is ready to be used as-is in your applications.

The idea behind the example in this chapter is simple: the RDF data dumps from DBPedia can be processed to capture an entity name and the corresponding DBPedia entity URI.

The raw DPBedia files can be downloaded from [Resolving Named Entities](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) (latest version when I wrote this chapter) and as an example, the SKOS categories dataset looks like (reformatted to be a litle easier to read):

```
 1 <http://dbpedia.org/resource/Category:World_War_II>
 2     <http://www.w3.org/2004/02/skos/core#broader>
 3     <http://dbpedia.org/resource/Category:Conflicts_in_1945> .
 4 	
 5 <http://dbpedia.org/resource/Category:World_War_II>
 6     <http://www.w3.org/2004/02/skos/core#broader>
 7 	<http://dbpedia.org/resource/Category:Global_conflicts> .
 8 	
 9 <http://dbpedia.org/resource/Category:World_War_II>
10     <http://www.w3.org/2004/02/skos/core#broader>
11 	<http://dbpedia.org/resource/Category:Modern_Europe> .
12 	
13 <http://dbpedia.org/resource/Category:World_War_II>
14     <http://www.w3.org/2004/02/skos/core#broader>
15 	<http://dbpedia.org/resource/Category:The_World_Wars> .
```

[SKOS (Simple Knowledge Organization System)](http://www.w3.org/2004/02/skos/) defines hierarchies of categories that are useful for categorizing real world entities, actions, etc. Cateorgies are then used for RDF versions of Wikipedia article titles, abstracts, geographic data, etc. Here is a small sample of RDF that maps subject URIs to text labels:

```
 1 <http://dbpedia.org/resource/Abraham_Lincoln>
 2     <http://www.w3.org/2000/01/rdf-schema#label>
 3 	"Abraham Lincoln"@en .
 4 
 5 <http://dbpedia.org/resource/Alexander_the_Great>
 6     <http://www.w3.org/2000/01/rdf-schema#label>
 7 	"Alexander the Great"@en .
 8 
 9 <http://dbpedia.org/resource/Ballroom_dancing>
10     <http://www.w3.org/2000/01/rdf-schema#label>
11 	"Ballroom dancing"@en .
```

As a final example of what the raw DBPedia RDF dump data looks like, here are some RDF statements that define abstracts for articles (text descriptions are shortened in the following listing to fit on one line):

```
1 <http://dbpedia.org/resource/An_American_in_Paris>
2    <http://www.w3.org/2000/01/rdf-schema#comment>
3    "An American in Paris is a jazz-influenced symphonic poem by ...."@en .
4 
5 <http://dbpedia.org/resource/Alberta>
6     <http://www.w3.org/2000/01/rdf-schema#comment>
7 	"Alberta (is a western province of Canada. With a population of 3,645,257 ...."\
8 @en .
```

I have already pulled entity names and URIs for nine classes of entities and this data is available in the github repo for this book in the directory inked_data/dbpedia_entities.

#### Java Named Entity Recognition Library

We already saw the use of Named Entity Resolution (NER) in the chapter using OpenNLP. Here we do something different. For my own projects I have data that I have processed that maps entity names to DBPedia URIs and Clojure code to use this data. For the purposes of this book, I am releasing my data under the Apache 2 license so you can use it in your projects and I converted my Clojure NER library to Java.

The following figure shows the project for this chapter in IntelliJ:

![IntelliJ project view for the examples in this chapter](images/00025.jpeg)

IntelliJ project view for the examples in this chapter

The following code example uses my data for mapping nine classes of entities to DBPedia URIs:

```
 1 package com.markwatson.ner_dbpedia;
 2 
 3 import java.io.IOException;
 4 import java.nio.file.Files;
 5 import java.nio.file.Paths;
 6 import java.util.HashMap;
 7 import java.util.Map;
 8 import java.util.stream.Stream;
 9 
10 /**
11  * Created by markw on 10/12/15.
12  */
13 public class NerMaps {
14   private static Map<String, String> textFileToMap(String nerFileName) {
15     Map<String, String> ret = new HashMap<String, String>();
16     try {
17       Stream<String> lines =
18           Files.lines(Paths.get("dbpedia_as_text", nerFileName));
19       lines.forEach(line -> {
20         String[] tokens = line.split("\t");
21         if (tokens.length > 1) {
22           ret.put(tokens[0], tokens[1]);
23         }
24       });
25       lines.close();
26     } catch (Exception ex) {
27       ex.printStackTrace();
28     }
29     return ret;
30   }
31 
32   static public final Map<String, String> broadcastNetworks =
33     textFileToMap("BroadcastNetworkNamesDbPedia.txt");
34   static public final Map<String, String> cityNames =
35     textFileToMap("CityNamesDbpedia.txt");
36   static public final Map<String, String> companyames =
37     textFileToMap("CompanyNamesDbPedia.txt");
38   static public final Map<String, String> countryNames =
39     textFileToMap("CountryNamesDbpedia.txt");
40   static public final Map<String, String> musicGroupNames =
41     textFileToMap("MusicGroupNamesDbPedia.txt");
42   static public final Map<String, String> personNames =
43     textFileToMap("PeopleDbPedia.txt");
44   static public final Map<String, String> politicalPartyNames =
45     textFileToMap("PoliticalPartyNamesDbPedia.txt");
46   static public final Map<String, String> tradeUnionNames =
47     textFileToMap("TradeUnionNamesDbPedia.txt");
48   static public final Map<String, String> universityNames =
49     textFileToMap("UniversityNamesDbPedia.txt");
50 
51   public static void main(String[] args) throws IOException {
52     new NerMaps().textFileToMap("CityNamesDbpedia.txt");
53   }
54 }
```

The class **TextToDbpediaUris** uses the nine NER types defined in class **NerMaps**. In the following listing the code for all by the NER class Broadcast News Networks is not shown for brevity:

```
 1 package com.markwatson.ner_dbpedia;
 2 
 3 public class TextToDbpediaUris {
 4   private TextToDbpediaUris() {
 5   }
 6 
 7   public TextToDbpediaUris(String text) {
 8     String[] tokens = tokenize(text + " . . .");
 9     String s = "";
10     for (int i = 0, size = tokens.length - 2; i < size; i++) {
11       String n2gram = tokens[i] + " " + tokens[i + 1];
12       String n3gram = n2gram + " " + tokens[i + 2];
13       // check for 3grams:
14       if ((s = NerMaps.broadcastNetworks.get(n3gram)) != null) {
15         log("broadcastNetwork", i, i + 2, n3gram, s);
16         i += 2;
17         continue;
18       }
19 
20       // check for 2grams:
21       if ((s = NerMaps.broadcastNetworks.get(n2gram)) != null) {
22         log("broadCastNetwork", i, i + 1, n2gram, s);
23         i += 1;
24         continue;
25       }
26 
27       // check for 1grams:
28       if ((s = NerMaps.broadcastNetworks.get(tokens[i])) != null) {
29         log("broadCastNetwork", i, i + 1, tokens[i], s);
30         continue;
31       }
32     }
33   }
34 
35   /** In your applications you will want to subclass TextToDbpediaUris
36    * and override <strong>log</strong> to do something with the
37    * DBPedia entities that you have identified.
38    * @param nerType
39    * @param index1
40    * @param index2
41    * @param ngram
42    * @param uri
43    */
44   void log(String nerType, int index1, int index2, String ngram, String uri) {
45     System.out.println(nerType + "\t" + index1 + "\t" + index2 + "\t" + ngram + \
46 "\t" + uri);
47   }
48 
49   private String[] tokenize(String s) {
50     return s.replaceAll("\\.", " \\. ").replaceAll(",", " , ")
51         .replaceAll("\\?", " ? ").replaceAll("\n", " ").replaceAll(";", " ; ").s\
52 plit(" ");
53   }
54 }
```

Here is an example showing how to use this code and the output:

```
 String s = "PTL Satellite Network covered President Bill Clinton going to Gu\
atemala and visiting the Cocoa Cola Company.";
    TextToDbpediaUris test = new TextToDbpediaUris(s);
```

```
broadcastNetwork 0 2 PTL Satellite Network	<http://dbpedia.org/resource/PTL_Sate\
llite_Network>
person   5  6 Bill Clinton <http://dbpedia.org/resource/Bill_Clinton>
country  9 10 Guatemala    <http://dbpedia.org/resource/Guatemala>
company 13 14 Coca Cola    <http://dbpedia.org/resource/Coca-Cola>
```

The second and third values are word indices (first word in sequence and last word in sequence from the input tokenized text).

There are many types of applications that can benefit from using “real world” information from sources like DBPedia.

### Combining Data from Public and Private Sources

A powerful idea is combining public and private linked data; for example, combining the vast real world knowledge stored in DBPedia with an RDF data store containing private data specific to your company. There are two ways to do this:

*   Use SPARQL queries to join data from multiple SPARQL endpoints
*   Assuming you have an RDF repository of private data, import external sources like DBPedia into your local data store

It is beyond the scope of my coverage of SPARQL but data can be joined from multiple endpoints using the **SERVICE** keyword in a SPARQL **WHERE** clause. In a similar way, public sources like DBPedia can be imported into your local RDF repository: this both makes queries more efficient and makes your system more robust in the face of failures of third party services.

One other data source that can be very useful to integrate into your applications is **web** **search**. I decided not to cover Java examples for calling public web search APIs in this book but I will refer you to my project on github that [wraps the Microsoft Bing Search API](https://github.com/mark-watson/bing_search_java). I mention this as an example pattern of using local data (notes and stored PDF documents) with public data APIs.

We will talk more about combining different data sources in the next chapter.

### Wrap Up for Linked Data

The semantic web and linked data are large topics and my goal in this chapter was to provide an easy to follow introduction to hopefully interest you in the subject and motivate you for further study. If you have not seen graph data before then RDF likely seems a little strange to you. There are more general graph databases like the commercial Neo4j commercial product (a free community edition is available) which provides an alternative to RDF data stores. If you would like to experiment with running your own RDF data store and SPARQL endpoint there are many fine open source and commercial products to choose from. If you read my web blog you have seen my experiments using the free edition of the Stardog RDF data store.

## Java Strategies for Working with Cloud Data: Knowledge Management-Lite

Knowledge Management (KM) is the collection, organization and maintenance of knowledge. The last chapter introduced you to techniques for information architecture and development using linked data and semantic web technologies and is paired with this chapter so please read these two chapters in order.

KM is a vast subject but I am interested in exploring one particular idea in this chapter: strategies for combining information stored in local data sources (relational and NoSQL data stores) with cloud data sources (e.g., Google Drive, Microsoft OneDrive, and Dropbox) to produce fused information that in turn may provide actionable knowledge. Think about your workflow: do you use Google Docs and Calendars? Microsoft Office 365 documents in the Azure cloud? I use both companies cloud services in my work. Sometimes cloud data just exists to backup local data on my laptops but usually I use cloud data for storing:

*   very large data sets
*   data that needs to be available for a wide range of devices
*   data that is valuable and needs to be replicated

I have been following the field of KM for many years but in the last few years I have been more taken with the idea of fusing together public information sources with private data. The flexibility of hybrid private data storage in the cloud and locally stored is a powerful pattern:

![Data fusion in KM systems](images/00026.jpeg)

Data fusion in KM systems

In this chapter we use data sources of documents in the cloud and local relational databases.

When I first planned on writing this chapter the example program that I wanted to write would access a user’s data in real time from either Google’s or Microsoft’s cloud services. I decided that the complexity of implementing OAuth2 to access Google and Microsoft services was too much for a book example because of the need for a custom web app to support an example application authenticating with these services.

What I decided to do was export (using Google Takeout) a small set of test data from my Google account for my calendar, Google Drive, and GMail and use a sanitized version of these data for examples programs in this chapter. Google Drive documents export as Microsoft document formats (Microsoft Word docx files, Excel xlsx spreadsheet files) and in standard calendar **ics** **format** files and email in the standard **mbox** **format**. In other words, this example could also be applicable for data stored in Microsoft Office 365\. While using canned data does not make a totally satisfactory demo it does allow me to concentrate on techniques for accessing the content of popular document types while ignoring the complexities of authenticating users to access their data on Google and Microsoft cloud services.

If you want to experiment with the example programs in this chapter with your own data you can use [www.google.com/settings/takeout/](https://www.google.com/settings/takeout/) to download your own data and replace my sanitized Google Takeout data - doing this will make the example programs more interesting and hopefully motivate you to experiment further with them.

A real system using the techniques that we will cover could be implemented as a web app running on either Google Cloud Services or Microsoft Azure that would authenticate a user with their Google or Microsoft accounts, and have live access to the user’s cloud data.

We will be using open source Java libraires to access the data in Microsoft Excel and Office formats (note that Google exports Google docs in these formats as does Microsoft’s Office 365).

One excellant tool for building KM systems that I am not covering is **web** **search**. Automatically accessing a web-wide search index to provide system users with more information to make decisions is something to consider when designong KM and decision support systems. I decided not to cover Java examples for calling public web search APIs in this book but you can use my project on github that [wraps the Microsoft Bing Search API](https://github.com/mark-watson/bing_search_java). I once wrote a service using search APIs to annotate notes and stored documents. Using DBPedia (as we did in the last chapter) and Bing search was easy and allowed me to annotate text (with hyperlinks to web information sources) in near real time.

### Motivation for Knowledge Management

Knowledge workers are different than previous kinds of workers who were trained to do a specific job repetitively. Knowledge workers tend to combine information from different sources to make decisions.

When workers leave, if their knowledge is not codified then the organization loses value. This situation will get worse in the future as baby boomers retire in larger numbers. So, the broad goals of KM are to capture employee knowledge, to facilitate sharing knowledge and information between workers company wide, and provide tools to increase workers’ velocity in making good decisions that are based on solid information and previous organizational knowledge.

For the purposes of this chapter we will discuss KM from the viewpoint of making maximum use of all available data sources, including shared cloud-based sources of information. We will do this through the implementation of Java code examples for accessing common document formats.

Since KM is a hugely broad topic I am going to concentrate on a few relatively simple examples that will give you ideas for both capturing and using knowledge and in some cases also provide useful code from the examples in this book that you can use:

*   Capture your email in a relational database and assign categories using some of the techniques we learned in the NLP and machine learning chapters.
*   Store web page URIs and content snippets for future use.
*   Java clients to process data in Google Drive, specifically reading Microsoft file formats that Google uses for exporting Google docs.
*   Annotate text in a document store by resolving entity names to unique DBPedia URIs.
*   Use Postgres as a local database to store discovered data that is discovered by the example software in this chapter.

Microsoft Office 365, which I use, also has APIs for integrating your own programs into an Office 365 work flow. I decided to use Google Drive in this chapter because it is free to use but I also encourage you to experiment with the Office 365 APIs. You can take free Office 365 API classes offered online [edX.org](http://edx.org). We will use Google Drive as a data source for the example code developed in this chapter.

As I mentioned earlier in this chapter in order to build a real system based on the ideas and example code in this chapter you will need to write a web applicaton that can authenticate users of your system to access data in Google Drive and/or in Microsoft OneDrive. In addition to real time access to shared data in the cloud, another important part of organizational KM systems that we are not discussing in this chapter is providing user and access roles. In the examples in this chapter we will ignore these organizational requirements and concentrate on the process of automatic discovery of useful metadata that helps to organize shared data.

There are many KM products that cater to organizations or individuals. Depending on your requirements you might want to mix custom software with off the shelf software tools. Another important aspect of KM is the concept of **master** **data** which is creating a uniform data model and storage strategy for diverse (and often legacy) databases. This is partly what I worked on at Google. Even for the three simple examples we will develop in this chapter there are interesting issues involving master data that I will return to later.

Most KM systems deal with internal data that is stored on local servers. While I do provide some very simple examples of using the Postgres relational database later in this chapter, I wanted to get you thinking about using multiple data sources and concentrating on data stored in commercial cloud services makes sense.

### Using Google Drive Cloud Takeout Service

As I mentioned in the introduction to this chapter, while it is fairly easy to write a web app for Microsoft Azure that uses the Office 365 APIs an a web app for AppEngine (or Google Cloud) that uses the Google Drive data access APIs, building a web app with the auth2 support required to use these APIs is outside of the scope for an example program. So, I am cheating a little. Google has a “Google Takeout” service that everyone who uses Google services should periodically use to save all of their data from Google services.

In this section and contained sub-sections we will use a “Google Takeout” dump as the data used by the example programs. The following subsections contain utilities for reading and parsing:

*   Microsoft Excel which is what Google Takeout exports Google Drive spreadsheets as.
*   Microsoft Word docx files which is the format that Google Takeout uses to export Google Drive word processing documents.
*   iCal calendar files which is a standard format that Google Calendar data is exported as.
*   Email mbox files which is the format that GMail is exported as.

These are all widely used file formats so I hope the utilities developed in the next four sub-sections will be generally useful to you. The following figure shows a screen grab of the IntelliJ Community Edition project browser showing just the data files that I exported using Google Takeout. I “sanitized” these files by changing names, email addresses, etc. to use for the example programs in this chapter.

![Sample Google Takeout files for this chapter](images/00027.jpeg)

Sample Google Takeout files for this chapter

We will be using the Apache Tika and iCal4j libraires to implement the code in the next three sub-sections. The following figure shows the IntelliJ source and test files used in this chapter:

![Java source and test files for this chapter](images/00028.jpeg)

Java source and test files for this chapter

#### Processing Microsoft Excel Spreadsheet xlsx and Microsoft Word docx Files

We will be using the Tika library that parses all sheets (i.e., separate pages) in Excel spreadsheet files. The output is a nicely formatted text file that is new line and tab character delimited. The following utility class parses this text output for more convenient use by parsing the plain text representation into Java data:

```
 1 package com.markwatson.km;
 2 
 3 import java.util.*;
 4 import java.util.regex.Pattern;
 5 
 6 public class ExcelData {
 7   public List<List<List<String>>> sheetsAndRows = new ArrayList<>();
 8   private List<List<String>> currentSheet = null;
 9 
10   public ExcelData(String contents) {
11     Pattern.compile("\n")
12         .splitAsStream(contents)
13         .forEach((String line) -> handleContentsStream(line));
14     if (currentSheet != null) sheetsAndRows.add(currentSheet); 
15   }
16 
17   private void handleContentsStream(String nextLine) {
18     if (nextLine.startsWith("Sheet")) {
19       if (currentSheet != null) sheetsAndRows.add(currentSheet);
20       currentSheet = new ArrayList<>();
21     } else {
22       String[] columns = nextLine.substring(1).split("\t");
23       currentSheet.add(Arrays.asList(columns));
24     }
25   }
26 
27   public String toString() {
28     StringBuilder sb = new StringBuilder("<ExcelData # sheets: " +
29               sheetsAndRows.size() + "\n");
30     for (List<List<String>> sheet : sheetsAndRows) {
31       sb.append("  <Sheet\n");
32       for (List<String> row : sheet) {
33         sb.append("    <row " + row + ">\n");
34       }
35       sb.append("  >\n>\n");
36     }
37     return sb.toString();
38   }
39 }
```

When a new instance of the class **ExcelData** is created you can access the individual sheets and the rows in each sheet from the public data in **sheetsAndRows**.

The first index of **sheetsAndRows** provides access to individual sheets, the second index provided access to the rows in a selected sheet, and the third (inner) index provides access to the individual columns in a selected row. The public utility method **toString** provides an example for accessing this data. The class **ExcellData** is used in the example code in the next listing.

The following utility class **PoiMicrosoftFileReader** has methods for processing Excel and Word files:

```
 1 package com.markwatson.km;
 2 
 3 import java.io.*;
 4 import org.apache.poi.openxml4j.exceptions.InvalidFormatException;
 5 import org.apache.tika.Tika;
 6 import org.apache.tika.exception.TikaException;
 7 import org.apache.tika.metadata.Metadata;
 8 import org.apache.tika.parser.ParseContext;
 9 import org.apache.tika.parser.microsoft.ooxml.OOXMLParser;
10 import org.apache.tika.sax.BodyContentHandler;
11 import org.apache.xmlbeans.XmlException;
12 import org.xml.sax.SAXException;
13 
14 public class PoiMicrosoftFileReader {
15 
16   static private boolean DEBUG_PRINT_META_DATA = false;
17 
18   public static String DocxToText(String docxFilePath)
19       throws IOException, InvalidFormatException, XmlException,
20              TikaException {
21     String ret = "";
22     FileInputStream fis = new FileInputStream(docxFilePath);
23     Tika tika = new Tika();
24     ret = tika.parseToString(fis);
25     fis.close();
26     return ret;
27   }
28 
29   public static ExcelData readXlsx(String xlsxFilePath)
30       throws IOException, InvalidFormatException, XmlException,
31              TikaException, SAXException {
32     BodyContentHandler bcHandler = new BodyContentHandler();
33     Metadata metadata = new Metadata();
34     FileInputStream inputStream = new FileInputStream(new File(xlsxFilePath));
35     ParseContext pcontext = new ParseContext();
36     OOXMLParser parser = new OOXMLParser();
37     parser.parse(inputStream, bcHandler, metadata, pcontext);
38     if (DEBUG_PRINT_META_DATA) {
39       System.err.println("Metadata:");
40       for (String name : metadata.names())
41         System.out.println(name + "\t:\t" + metadata.get(name));
42     }
43     ExcelData spreedsheet = new ExcelData(bcHandler.toString());
44     return spreedsheet;
45   }
46 }
```

The static public method **DocxToText** transforms a file path specifying a Microsoft Word docx file to the plain text in that file. The public static method **readXlsx** transforms a file path to an Excel xlsx file to an instance of the class **ExcelData** that we looked at earlier.

The following output was generated from running the test programs **GoogleDriveTest.testDocxToText** and **GoogleDriveTest.testExcelReader**. I am using jUnit tests as a convenient way to provide examples of calling APIs in the example code. Here is the test code and its output:

```
 1   String contents =
 2     PoiMicrosoftFileReader.DocxToText(
 3 	      "GoogleTakeout/Drive/booktest/Test document 1.docx");
 4   System.err.println("Contents of test Word docx file:\n\n" +
 5                      contents + "\n");
 6 
 7   ExcelData spreadsheet =
 8     PoiMicrosoftFileReader.readXlsx(
 9 		"GoogleTakeout/Drive/booktest/Test spreadsheet 1.xlsx");
10   System.err.println("Contents of test spreadsheet:\n\n" +
11                      spreadsheet);
```

```
 1 Contents of test Word docx file:
 2 
 3 This is a test document for Power Java book.
 4 
 5 
 6 Contents of test spreadsheet:
 7 
 8 <ExcelData # sheets: 1
 9   <Sheet
10     <row [Name, Age]>
11     <row [Brady, 12]>
12     <row [Calvin, 17]>
13   >
14 >
```

#### Processing iCal Calendar Files

The iCal format is the standard way that Google, Apple, Microsoft, and other vendors export calendar data. The following code uses the **net.fortuna.ical4j** library that provides a rich API for dealing with iCal formatted files. In the follow example we are using a small part of this API.

```
 1 package com.markwatson.km;
 2 
 3 // refenerence: https://github.com/ical4j/ical4j
 4 
 5 import net.fortuna.ical4j.data.CalendarBuilder;
 6 import net.fortuna.ical4j.data.ParserException;
 7 import net.fortuna.ical4j.model.Component;
 8 import net.fortuna.ical4j.model.Property;
 9 
10 import java.io.FileInputStream;
11 import java.io.IOException;
12 import java.util.*;
13 
14 public class ReadCalendarFiles {
15 
16   public ReadCalendarFiles(String filePath)
17              throws IOException, ParserException {
18     Map<String, String> calendarEntry = null;
19     FileInputStream fin = new FileInputStream(filePath);
20     CalendarBuilder builder = new CalendarBuilder();
21     net.fortuna.ical4j.model.Calendar calendar = builder.build(fin);
22     for (Iterator i = calendar.getComponents().iterator();
23          i.hasNext(); ) {
24       Component component = (Component) i.next();
25       if (component.getName().equalsIgnoreCase("VEVENT")) {
26         calendarEntry = new HashMap<>();
27         for (Iterator j = component.getProperties().iterator();
28              j.hasNext(); ) {
29           net.fortuna.ical4j.model.Property property =
30              (Property) j.next();
31           calendarEntry.put(property.getName(),
32                             property.getValue());
33         }
34         calendarEntries.add(calendarEntry);
35       }
36     }
37   }
38 
39   public int size() { return calendarEntries.size(); }
40   public Map<String, String> getCalendarEntry(int index) {
41     return calendarEntries.get(index);
42   }
43 
44   /**
45    * List of calendar entries where each entry
46    *  is a Map<String, String>
47    *
48    */
49   private List<Map<String, String>> calendarEntries =
50        new ArrayList<>();
51 }
```

The following output was generated from running the test program **GoogleDriveTest.testCalendarFileReader**. Here is the test code and its output:

```
 1   ReadCalendarFiles calendar =
 2     new ReadCalendarFiles("GoogleTakeout/Calendar/Mark Watson.ics");
 3   System.err.println("\n\nTest iCal calendar file has " +
 4                      calendar.size() + " calendar entries.");
 5   for (int i=0, size=calendar.size(); i<size; i++) {
 6     Map<String,String> entry = calendar.getCalendarEntry(i);
 7     System.err.println("\n\tNext calendar entry:");
 8     System.err.println("\n\t\tDTSAMP:\t" + entry.getOrDefault("DTSTAMP", ""));
 9     System.err.println("\n\t\tSUMMARY:\t" + entry.getOrDefault("SUMMARY", ""));
10     System.err.println("\n\t\tDESCRIPTION:\t" +
11                        entry.getOrDefault("DESCRIPTION", ""));
12   }
```

```
 1 Test iCal calendar file has 11 calendar entries.
 2 
 3 	Next calendar entry:
 4 
 5 		DTSAMP: 20150917T234033Z
 6 
 7 		SUMMARY: Free Foobar Test  Meeting
 8 
 9 		DESCRIPTION: Bob Smith has invited you to join a meeting
10 
11  ... ...
```

The utility method **toString** for the class **ReadCalendarFiles** prints for each entry three attributes: a date stamp, a summary, and a description.

#### Processing Email mbox Files

In this section we use the Apace Tika library for parsing email mbox formatted files. There is a commented out printout on line 36 and you might want to uncomment this and look at the full message text to see all available meta data for each email as it is processed. You might want to use more of the meta data in your applications than I am using in the example code.

```
 1 package com.markwatson.km;
  2 
  3 // reference: https://tika.apache.org/
  4 
  5 import org.apache.poi.openxml4j.exceptions.InvalidFormatException;
  6 import org.apache.tika.exception.TikaException;
  7 import org.apache.tika.metadata.Metadata;
  8 import org.apache.tika.parser.ParseContext;
  9 import org.apache.tika.parser.Parser;
 10 import org.apache.tika.parser.mbox.MboxParser;
 11 import org.apache.tika.parser.microsoft.ooxml.OOXMLParser;
 12 import org.apache.tika.sax.BodyContentHandler;
 13 import org.apache.xmlbeans.XmlException;
 14 import org.xml.sax.SAXException;
 15 
 16 import java.io.*;
 17 import java.nio.charset.StandardCharsets;
 18 import java.util.ArrayList;
 19 import java.util.List;
 20 
 21 /**
 22  * Created by markw on 9/17/15.
 23  */
 24 public class ReadMbox {
 25 
 26   static private boolean DEBUG_PRINT_META_DATA = true;
 27 
 28   private String getTextContents(InputStream stream) {
 29     BufferedReader br = new BufferedReader(new InputStreamReader(stream));
 30     StringBuffer sb = new StringBuffer();
 31     String subject = "";
 32     String from = "";
 33     String to = "";
 34     try {
 35       String line = null;
 36       boolean inText = false;
 37       while ((line = br.readLine()) != null) {
 38         //System.err.println("-- line: " + line);
 39         if (!inText) {
 40           if (line.startsWith("Subject:")) subject = line.substring(9);
 41           if (line.startsWith("To:"))      to = line.substring(4);
 42           if (line.startsWith("From:"))    from = line.substring(6);
 43         }
 44         if (line.startsWith("Content-Type: text/plain;")) {
 45           inText = true;
 46           br.readLine();
 47         } else if (inText) {
 48           if (line.startsWith("-----")) break;
 49           if (line.startsWith("--_---")) break;
 50           if (line.startsWith("Content-Type: text/html;")) break;
 51           sb.append(line + "\n");
 52         }
 53       }
 54     } catch (Exception ex) {
 55       System.err.println("ERROR: " + ex);
 56     }
 57     return "To: " + to + "\nFrom: " + from + "\nSubject: " +
 58            subject + "\n" + sb.toString();
 59   }
 60 
 61   public ReadMbox(String filePath)
 62       throws IOException, InvalidFormatException, XmlException,
 63              TikaException, SAXException {
 64 
 65     FileInputStream inputStream = new FileInputStream(new File(filePath));
 66 
 67     BufferedReader br = new BufferedReader(new InputStreamReader(inputStream));
 68 
 69     String line = null;
 70     StringBuffer sb = new StringBuffer();
 71     try {
 72       // the outer loop splits each email to a separate string that we will use \
 73 Tika to parse:
 74       while ((line = br.readLine()) != null) {
 75         if (line.startsWith("From ")) {
 76           if (sb.length() > 0) { // process all but the last email
 77             String content = sb.toString();
 78             InputStream stream =
 79               new ByteArrayInputStream(content.getBytes(StandardCharsets.UTF_8));
 80             emails.add(getTextContents(stream));
 81             sb = new StringBuffer();
 82           }
 83         }
 84         sb.append(line + "\n");
 85       }
 86       if (sb.length() > 0) { // process the last email
 87         String content = sb.toString();
 88         InputStream stream =
 89           new ByteArrayInputStream(content.getBytes(StandardCharsets.UTF_8));
 90         emails.add(getTextContents(stream));
 91       }
 92 
 93       br.close();
 94     } catch (Exception ex) {
 95       System.err.println("ERROR: " + ex);
 96     }
 97   }
 98 
 99   public int size() {
100     return emails.size();
101   }
102 
103   public String getEmail(int index) {
104     return emails.get(index);
105   }
106 
107   public List<String> emails = new ArrayList<>();
108 }
```

The following output was generated from running the test program **GoogleDriveTest.testMboxFileReader**. Here is the test code and its output (edited for brevity and clarity):

```
1   ReadMbox mbox = new ReadMbox("GoogleTakeout/Mail/bookexample.mbox");
2   System.err.println("\nMBOX size = " + mbox.size());
3   for (int i=0, size=mbox.size(); i<size; i++) {
4     System.err.println("\n* * next email:\n\n" + mbox.getEmail(i) + "\n");
5   }
```

```
 1 MBOX size = 3
 2 
 3 * * next email:
 4 
 5 To: <mark@markwatson.com>
 6 From: Ruby Weekly= <rw@peterc.org>
 7 Subject: This week's Ruby news issue
 8 
 9 This week's Ruby and Rails news
10 
11 Ruby Weekly - A Weekly Ruby Newsletter
12 Issue 264 - September 17=2C 2015
13 
14  ...  ...
```

You now can parse and use information from exported Microsoft Office documents. As I mentioned before, when you export Google documents this process also generates documents in the Microsoft formats.

### Using Postgres as a Local Document Store with Text Search

We will now develop a simple set of utiltity classes for easily string structured data and “less structured” JSON data in a Postgres database. We will also provide support for text search in database table columns containing text data.

I use many different data stores in my work: Amazon S3 and DynamoDB, Google Big Table, Hadoop File System, MongoDB, CouchDB, Cassandra, etc. Lots of good options for different types of projects!

That said, Postgres is my “Swiss Army knife” data store offering a rock solid relational database, full text indexing, and native support for schema less native JSON documents. I this short section I am going to cover JDBC access to Postgres and cover the common use cases that you might need if you also want to use Postgres as your “Swiss Army knife” data store.

The following listing shows these utilities, encapsulated in the Java class **PostgresUtilities**. In line 16 we set the server name, Postgres account anme, and password for connecting to a database. Here the server name is “localhost” since I am running both the example program and the postgres server on my laptop. I pass the connection parameters in the connection URI on line 14 but the commented out lines 25 and 26 show you how to set connection properties in your code if you prefer that.

```
 1 package com.markwatson.km;
  2 
  3 import java.sql.*;
  4 import java.util.ArrayList;
  5 import java.util.HashMap;
  6 import java.util.List;
  7 import java.util.Properties;
  8 
  9 /**
 10  * Created by Mark on 6/5/2015.
 11  */
 12 public class PostgresUtilities {
 13   private static String defaultConnectionURL =
 14        "jdbc:postgresql://localhost:5432/kmdexample?user=markw&password=";
 15   private Connection conn = null;
 16 
 17   public PostgresUtilities() throws ClassNotFoundException, SQLException {
 18     this(defaultConnectionURL);
 19   }
 20 
 21   public PostgresUtilities(String connectionURL)
 22          throws ClassNotFoundException, SQLException {
 23     Class.forName("org.postgresql.Driver");
 24     Properties props = new Properties();
 25     //props.setProperty("user","a username could go here");
 26     //props.setProperty("password","a passwordc could go here");
 27     conn = DriverManager.getConnection(connectionURL, props);
 28   }
 29 
 30   /**
 31    * doQuery - performs an SQL update
 32    * @param sql the update string
 33    * @return List<HashMap<String,Object>> Each row is a map where columns are
 34    *         fetched by (lower case) column name
 35    * @throws SQLException
 36    */
 37   public int doUpdate(String sql) throws SQLException {
 38     Statement st = conn.createStatement();
 39     int rows_affected = st.executeUpdate(sql);
 40     return rows_affected;
 41   }
 42 
 43   /**
 44    * doQuery - performs an SQL query
 45    * @param sql the query string
 46    * @return List<HashMap<String,Object>> Each row is a map where columns are
 47              fetched by (lower case) column name
 48    * @throws SQLException
 49    */
 50   public List<HashMap<String,Object>> doQuery(String sql) throws SQLException {
 51     Statement st = conn.createStatement();
 52     ResultSet rs = st.executeQuery(sql);
 53     List<HashMap<String,Object>> ret = convertResultSetToList(rs);
 54     rs.close();
 55     st.close();
 56     return ret;
 57   }
 58 
 59   /**
 60    * textSearch - search for a space separated query string in a specific column
 61    *              in a specific table.
 62    *
 63    * Please note that this utility method handles a very general case. I usually
 64    * start out with a general purpose method like <strong>textSearch</strong>
 65    * and then as needed add additional methods that are very application
 66    * specific (e.g., selecting on different columns, etc.)
 67    *
 68    * @param tableName
 69    * @param coloumnToSearch
 70    * @param query
 71    * @return List<HashMap<String,Object>> Each row is a map where columns are
 72    *                                      fetched by (lower case) column name
 73    * @throws SQLException
 74    */
 75   public List<HashMap<String,Object>> textSearch(String tableName,
 76                                                  String coloumnToSearch,
 77                                                  String query)
 78          throws SQLException {
 79     // we need to separate query words with the & character:
 80     String modifiedQuery = query.replaceAll(" ", " & ");
 81     String qString = "select * from " + tableName + " where to_tsvector(" +
 82                      coloumnToSearch + ") @@ to_tsquery('" +
 83                      modifiedQuery +  "')";
 84     Statement st = conn.createStatement();
 85     ResultSet rs = st.executeQuery(qString);
 86     List<HashMap<String,Object>> ret = convertResultSetToList(rs);
 87     rs.close();
 88     st.close();
 89     return ret;
 90   }
 91 
 92   /**
 93    * convertResultSetToList
 94    *
 95    * The following method is derived from an example on stack overflow.
 96    * Thanks to stack overflow users RHT and Brad M!
 97    *
 98    * Please note that I lower-cased the column names so the column data for each
 99    * row can uniformly be accessed by using the column name in the query as
100    * lower-case.
101    *
102    * @param rs is a JDBC ResultSet
103    * @return List<HashMap<String,Object>> Each row is a map where columns are
104    *         fetched by (lower case) column name
105    * @throws SQLException
106    */
107   private List<HashMap<String,Object>> convertResultSetToList(ResultSet rs)
108           throws SQLException {
109     ResultSetMetaData md = rs.getMetaData();
110     int columns = md.getColumnCount();
111     List<HashMap<String,Object>> list = new ArrayList<HashMap<String,Object>>();
112     while (rs.next()) {
113       HashMap<String,Object> row = new HashMap<String, Object>(columns);
114       for(int i=1; i<=columns; ++i) {
115         row.put(md.getColumnName(i).toLowerCase(),rs.getObject(i));
116       }
117       list.add(row);
118     }
119     return list;
120   }
121 }
```

I use the private method **convertResultSetToList** (lines 107 through 102) to convert a result set object (class java.sql.ResultSet) to pure Java data. This method returns a list. Each element in the returned list contains a map representing a row. the keys of the map are table column names and the values are the row value for the column.

Besides rhe constructor, this class contains three public methods: **doUpdate**, **doQuery** and **textSearch**. Both take as an argument a string containign an SQL statement. I assume that you know the SQL language, and if not the following test code for the class **PostgresUtilities** provides a few simple SQL statement examples for creating tables, adding and updating rows in a table, querying to find specific rows, and performing full text search.

The test program **PostgresTest** contains examples for using this utility class. In the following snippets I will alternate code from PostgresTest with the outputs from the snippets:

```
 PostgresUtilities pcon = new PostgresUtilities();
    int num_rows = pcon.doUpdate(
      "create table test (id int, name varchar(40), description varchar(100))");
    System.out.println("num_rows = " + num_rows);
```

The **doUpdate** method returns the number of modified rows in the database. From the output you see that creating a table changes no rows in the database:

```
num_rows = 0
```

```
 PostgresUtilities pcon = new PostgresUtilities();
    int num_rows = pcon.doUpdate(
      "create table test (id int, name varchar(40), description varchar(100))");
    System.out.println("num_rows = " + num_rows);
```

The output is:

```
num_rows = 0
```

```
 num_rows = pcon.doUpdate(
      "CREATE INDEX description_search_ix ON test USING gin(to_tsvector('english\
', description))");
    System.out.println("num_rows = " + num_rows);
    num_rows = pcon.doUpdate(
	  "insert into test values (1, 'Ron', 'brother who lives in San Diego')");
    System.out.println("num_rows = " + num_rows);
    System.out.println("num_rows = " + num_rows);
```

The output is:

```
num_rows = 0

num_rows = 1
```

```
 num_rows = pcon.doUpdate(
	  "insert into test values (1, 'Ron', 'brother who lives in San Diego')");
    System.out.println("num_rows = " + num_rows);
    num_rows = pcon.doUpdate("insert into test values (1, 'Anita', 'sister inlaw\
 who lives in San Diego')");
    System.out.println("num_rows = " + num_rows);
```

The output is:

```
num_rows = 1
```

```
 List<HashMap<String,Object>> results = pcon.doQuery("select * from test");
    System.out.println("results = " + results);
```

The output is:

```
results = [{name=Ron, description=brother who lives in San Diego, id=1},
           {name=Anita, description=sister inlaw who lives in San Diego, id=1}]
```

```
 String name = "Ron";
    String search_string = "sister";
    results = pcon.doQuery(
        "select * from test where name = '"  +name +
        "' and to_tsvector(description) @@ to_tsquery('" + search_string + "')");
    System.out.println("results = " + results);
```

The output is:

```
results = []
```

```
 results = pcon.doQuery(
        "select * from test where to_tsvector(description) @@ to_tsquery('" +
        search_string + "')");
    System.out.println("results = " + results);
```

The output is:

```
results = [{name=Anita, description=sister inlaw who lives in San Diego, id=1}]
```

```
 num_rows = pcon.doUpdate("drop table test");
    System.out.println("num_rows = " + num_rows);
```

The output is:

```
num_rows = 0
```

There is a lot of hype concerning NoSQL data stores and some of this hype is well deserved: when you have a massive amount of data to handle then splitting it accross many servers with systems like the Hadoop File System or Cassandra allows you to process large data sets using many lower cost servers. That said, for many applications, you don’t have very large data sets so general purpose database systems like Postgres make more sense. Ideally you will wrap data access in your own code to minimize future code changes if you switch data stores.

### Wrap Up

Much of my career has involved building systems to store and provide access to information to support automated and user in the loop systems. Knowledge Management is the branch of computer science that helps turn data into data into information and information into knowledge. I titled this chapter “Knowledge Management-Lite” because I am just providing you with ideas for your own KM projects and hopefully changed for the better how you look at the storage and use of data.

## Book Wrap Up

This book has provided you with my personal views on how to process information using machine learning, natural language processing, and various data store technologies. My hope is that at least some of my ideas for building software systems has been of use to you and given you ideas that you can use when you design and build your applications.

My philosophy in general for building systems that solve real problems in the world includes the following system:

*   Learn new technologies as a background exercise to “keep a full toolbelt.” This is especially important now that technology is changing rapidly and often new technologies make it easier to implement new functionality. A major reason that I wrote this book is to introduce you to some of the technology that I have found to be most useful.
*   Make sure you solve the right problems. Build systems that have an impact on your company or organization, and on the world in general by building things that you think will have the greatest positive impact.

```
Best regards,
Mark Watson  November 10, 2015
```