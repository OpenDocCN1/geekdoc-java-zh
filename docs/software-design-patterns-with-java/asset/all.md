![](image_rsrc3ME.jpg)

Copyright

Copyright © 2023 by AK Ray

All rights reserved.

This ebook is protected by copyright law. No part of this publication may be reproduced, distributed, or transmitted in any form or by any means, including photocopying, recording, or other electronic or mechanical methods, without the prior written permission of the copyright owner, except in the case of brief quotations embodied in critical reviews and certain other noncommercial uses permitted by copyright law.

For permission requests or inquiries, please contact:

Email: [akr.technolab@gmail.com](mailto:akr.technolab@gmail.com)

Facebook: [https://www.facebook.com/akr.technolab](https://www.facebook.com/akr.technolab)

LinkedIn : [https://www.linkedin.com/in/akr-technolab-074b5828b/](https://www.linkedin.com/in/akr-technolab-074b5828b/)

Disclaimer: The information provided in this ebook is for general informational purposes only and should not be considered as professional, legal, or financial advice. The author and publisher disclaim any liability or responsibility for any loss or damage incurred as a consequence of the use of the information presented in this book.

First Edition

About the Author

AK Ray is a distinguished software development professional with a wealth of experience spanning over a decade. His career has been marked by significant contributions to core software development within renowned product development multinational corporations. With expertise in a diverse range of technologies, AK Ray is well-versed in Java, Spring Boot, Microservices, Docker, Ethical Hacking, and Application Security.

His passion for software design and architecture has culminated in his authorship of a notable book on Software Design Patterns, demonstrating his thought leadership in the field. AK Ray's commitment to excellence is further underscored by his certification in Software Design and Architecture from the esteemed University of Alberta.

AK Ray's substantial experience, coupled with his comprehensive skill set, positions him as a highly sought-after expert in software engineering and architecture. His dedication to innovation and continuous learning continues to drive his success, making him a valuable asset to the industry.

Feel free to reach out to me :

Email: [akr.technolab@gmail.com](mailto:akr.technolab@gmail.com)

Facebook: [https://www.facebook.com/akr.technolab](https://www.facebook.com/akr.technolab)

LinkedIn : [https://www.linkedin.com/in/akr-technolab-074b5828b](https://www.linkedin.com/in/akr-technolab-074b5828b/)

I extend my heartfelt gratitude to you for choosing to explore the world of Java functional programming with me. Your support and enthusiasm fuel my commitment to sharing knowledge and empowering fellow developers with the tools they need to excel in the Java ecosystem.

Here's to a future of code that's not just functional but beautifully elegant too!

Warm regards,

# ![](image_rsrc3MF.jpg)

About this Book

Embark on a comprehensive exploration of Software Design Patterns in this book, where I meticulously dissect the intricacies of SOLID principles, unravel the subtleties of code smells and anti-patterns, and provide an in-depth understanding of design patterns and object-oriented design.

With a focus on real-time experiences and an emphasis on simplicity, this book serves as a guide for developers of all levels, offering practical insights and examples to elevate your coding proficiency.

Whether you're a seasoned developer looking to refine your skills or a novice eager to grasp the essentials, each chapter provides a clear pathway to mastering the art of crafting robust and maintainable code.

Immerse yourself in a journey through the principles that underlie successful software design, applying them directly to your projects. Gain a deeper understanding of design concepts with practical, real-world scenarios, and emerge as a skilled architect of software solutions. This book is your key to unlocking the secrets of effective software design, making complex concepts accessible and empowering you to create resilient and scalable applications.

Join me on this enlightening voyage into the heart of Software Design Patterns, where simplicity meets expertise, and innovation takes center stage. Your path to mastering Software Design Patterns begins here.

1.  [SOLID Design Principle in OOAD](#part0005.xhtml)

1.1 [Single Responsibility Principle (SRP)](#part0006.xhtml)

1.2 [Open-Closed Principle (OCP)](#part0007.xhtml)

1.3 [Liskov Substitution Principle (LSP)](#part0009.xhtml)

1.4 [Interface Segregation Principle (ISP)](#part0010.xhtml)

1.5 [Problem Without ISP](#part0010.xhtml_a3H5)

1.6 [Applying ISP in Java](#part0010.xhtml_a3H9)

1.7 [Dependency Inversion Principle (DIP)](#part0011.xhtml)

2.  [Anti-Patterns and Code Smells](#part0013.xhtml)

2.1 [Anti-Patterns](#part0013.xhtml_a3ET)

2.2 [Code Smells](#part0013.xhtml_a3GK)

2.3 [Duplicate Code](#part0014.xhtml)

2.4 [Signs of Duplicate Code](#part0014.xhtml_a3GM)

2.5 [Why Duplicate Code is a Smell](#part0014.xhtml_a3F5)

2.6 [Addressing Duplicate Code](#part0014.xhtml_a3FT)

2.7 [Benefits of Eliminating Duplicate Code](#part0014.xhtml_a3HK)

2.8 [Large Class](#part0016.xhtml)

2.9 [Signs of the Large Class code smell](#part0016.xhtml_a3HN)

2.10 [How to Fix It:](#part0016.xhtml_a3FF)

2.11 [Long Method](#part0017.xhtml)

2.12 [Feature Envy](#part0017.xhtml_a3GS)

2.13 [Inappropriate Intimacy](#part0017.xhtml_a3H7)

2.14 [Primitive Obsession](#part0017.xhtml_a3H1)

2.15 [Shotgun Surgery](#part0017.xhtml_a3F0)

2.16 [Comments Abuse](#part0017.xhtml_a3G1)

2.17 [Lazy Class](#part0017.xhtml_a3F9)

2.18 [Cyclic Dependencies](#part0017.xhtml_a3FM)

2.19 [Lava Flow](#part0017.xhtml_a3HG)

2.20 [Golden Hammer (or Silver Bullet)](#part0017.xhtml_a3HT)

2.21 [Copy and Paste Programming](#part0017.xhtml_a3G4)

3.  [Design Pattern](#part0018.xhtml)

3.1 [Type of Design Pattern](#part0019.xhtml)

3.1.1 [Creational patterns](#part0020.xhtml)

3.1.1.1 [Singleton Design Pattern](#part0020.xhtml_a3GW)

3.1.1.2 [Factory Method Pattern](#part0021.xhtml)

3.1.2 [Structural Design Pattern](#part0023.xhtml)

3.1.2.1 [Adapter Pattern](#part0024.xhtml)

3.1.2.2 [Facade Pattern](#part0026.xhtml)

3.1.2.3 [Composite Pattern](#part0027.xhtml)

3.1.2.4 [Decorator Pattern](#part0029.xhtml)

3.1.2.5 [Bridge Pattern](#part0034.xhtml)

3.1.2.6 [Flyweight Pattern](#part0037.xhtml)

3.1.2.7 [Proxy Design Pattern](#part0038.xhtml)

3.1.3 [Behavioral Design Pattern](#part0040.xhtml)

3.1.3.1 [Template Method Pattern](#part0042.xhtml)

3.1.3.2 [Chain of Responsibility Pattern](#part0046.xhtml)

3.1.3.3 [State Pattern](#part0049.xhtml)

3.1.3.4 [Command Pattern](#part0054.xhtml)

3.1.3.5 [Observer Pattern](#part0056.xhtml)

3.1.3.6 [MVC Design Pattern](#part0059.xhtml)

4.  [Object-oriented design](#part0061.xhtml)

4.1 [What do you mean by requirements ?](#part0061.xhtml_a3FE)

4.2 [Conceptual Design](#part0061.xhtml_a3F7)

4.3 [Technical Design](#part0061.xhtml_a3HV)

4.4 [Compromise in Requirements and Design](#part0061.xhtml_a3G0)

4.5 [Design for Quality Attributes](#part0061.xhtml_a3G5)

4.6 [Trade offs](#part0061.xhtml_a3HD)

4.7 [CRC Card](#part0061.xhtml_a3J1)

4.8 [Object Modeling in OOAD](#part0061.xhtml_a3GN)

4.9 [Creating Models in Design](#part0061.xhtml_a3FR)

4.10 [Design Principles](#part0062.xhtml)

4.11 [Abstraction](#part0062.xhtml_a3H0)

4.12 [Encapsulation](#part0063.xhtml)

4.13[Decomposition](#part0064.xhtml)

4.14 [Generalization](#part0064.xhtml_a3EK)

4.15 [Design Principles](#part0065.xhtml)

4.16[Coupling](#part0065.xhtml_a3GP)

4.17[High Cohesion:](#part0065.xhtml_a3GH)

4.18 [Separation of Concerns](#part0066.xhtml)

4.19 [Information Hiding](#part0066.xhtml_a3H2)

4.20 [Conceptual Integrity](#part0067.xhtml)

4.21 [Generalization Principles](#part0068.xhtml)

4.22 [Model Checking](#part0068.xhtml_a3GX)

4.23 Phases in Model checking[.](#part0069.xhtml)

# SOLID

The SOLID principles are a set of five design principles that help software developers create more maintainable, flexible, and robust object-oriented software. Each principle addresses a specific aspect of software design and, when applied together, promotes good software design practices.

# Here's an very high level overview of each of the SOLID principles

Single Responsibility Principle (SRP)

Open-Closed Principle (OCP)

Liskov Substitution Principle (LSP)

Interface Segregation Principle (ISP)

Dependency Inversion Principle (DIP)

* * *

# Single Responsibility Principle (SRP)

●         Idea: A class should have only one job or responsibility.

● Example: Think of a remote control. It has a single responsibility: to send commands to a device. If you add more responsibilities, like handling power, volume, and channels, it becomes less focused.

● Example: If you have a class for handling user authentication, it shouldn't also be responsible for sending emails. Each class should focus on doing one thing well.

# Here are the key points of the Single Responsibility Principle in OOAD

One Reason to Change: Each class should have only one responsibility or reason to change. If there is more than one reason for a class to change, it becomes more error-prone and harder to maintain.

Cohesion: The principle encourages high cohesion within classes, meaning that the class should contain members (methods and attributes) that are closely related and work together to achieve a single responsibility.

Separation of Concerns: It helps in separating different concerns or aspects of the software system into distinct classes. This separation makes the system more modular and easier to understand, modify, and maintain.

Reusability: Classes that adhere to the SRP are often more reusable, as they are specialized in a single responsibility and can be used in various contexts.

# Here's an example to illustrate the Single Responsibility Principle

Suppose you're designing a banking software system. You might have a BankAccount class. According to SRP, this class should have only one responsibility, which is managing the bank account balance.

| public class BankAccount {public double getAccountBalance(){// ADD your code to fetch Bank accountreturn Math.random();}public void createBankAccount(){//LOGIC to create bank Account}public boolean validateUser(UserData request){//Validate Userreturn Boolean.TRUE;}public void sendEmail(String emailId){//send email to User}} |

It should not be responsible for handling user authentication, sending emails, or other unrelated tasks.

So, user authentication and email sending should be handled by separate classes with their own single responsibilities. This separation allows for easier maintenance, testing, and future changes without affecting unrelated parts of the system.

In summary, the Single Responsibility Principle in OOAD promotes the idea that each class should have a clear, single, and well-defined responsibility, which contributes to more maintainable and robust software systems.

| public class EmployeeData {private int id;private String name;private double salary;public EmployeeData(int id, String name, double salary) {this.id = id;this.name = name;this.salary = salary;}// Methods for accessing and modifying employee datapublic int getId() { return id; }public String getName() { return name; }public double getSalary() { return salary; }// Method to save an employee to the databasepublic void saveToDatabase() {// Code to save the employee data to a database}} |

# In this design, the Employee class has two responsibilities

1\. Managing employee data (storing and retrieving employee attributes).

2\. Saving employee data to a database.

# Revised Design (Adhering to SRP)

To adhere to the Single Responsibility Principle, we separate the responsibilities into different classes. We create an Employee class for managing employee data and an EmployeeRepository class for database operations.

| public class EmployeeData {private int id;private String name;private double salary;public EmployeeData(int id, String name, double salary) {this.id = id;this.name = name;this.salary = salary;}// Methods for accessing and modifying employee datapublic int getId() { return id; }public String getName() { return name; }public double getSalary() { return salary; }} |

| public class EmployeeRepository {public void saveToDatabase(Employee employee) {// Code to save the employee data to a database}} |

# As you can see above

1\. The EmployeeData class is responsible for managing employee data (attributes and methods related to employee information).

2\. The EmployeeRepository class is responsible for saving and retrieving employee data from the database.

By separating these responsibilities into different classes, we adhere to the Single Responsibility Principle. This design promotes code maintainability and flexibility because changes to the way employee data is persisted (e.g., switching from a database to a file system) won't impact the core employee data management logic in the Employee class.

In any real time applications, you need to design your code in such a way that it will somehow use the SOLID principle to make it more flexible,readable and robust.

# Summary

|  
1.  Whenever you are creating any class ,ensure that class has a single responsibility.

2.  You can split your requirements in different classes based on category,type,nature and based on other applicable parameters.

3.  Name of the class should tell the functionality.

 |

# Open-Closed Principle (OCP)

* * *

Idea: Software entities(classes, modules, functions) should be open for extension but closed for modification.

Example: Instead of modifying existing code, you should be able to add new features through extensions. Think of it as adding new layers to a cake without changing the existing layers.

Example: Imagine a shape drawing application. You can add new shapes without changing how existing shapes are drawn. For instance, you can add a new "Triangle" class without modifying the existing "Circle" or "Square" classes.

* * *

The open/closed principle states that classes should be open for extension but closed to change.

A class is considered “closed” to editing once it has:

● Been tested to be functioning properly. The class should behave as expected.

●      All the attributes and behaviors are encapsulated,

● Been proven to be stable within your system. The class or any instance of the class should not stop your system from running or do it harm.

Although the principle is called “closed”, it does not mean that changes cannot be made to a class during development. Things should change during the design and analysis phase of your development cycle. A “closed” class occurs when a point has been reached in development when most of the design decisions have been finalized and once you have implemented most of your system.

During the lifecycle of your software, certain classes should be closed to further changes to avoid introducing undesirable side effects. A “closed” class should still be fixed if any bugs or unexpected behaviors occur.

If a system needs to be extended or have more features added, then the “open” side of the principle comes into play. An “open” class is one that can still be built upon. There are two different ways to extend a system with the open principle.

The first way is through the inheritance of a superclass. Inheritance can be used to simply extend a class that is considered closed when you want to add more attributes and behaviors. The subclasses will have the original functions of the superclass, but extra features can be added in the subclasses. This helps preserve the integrity of the superclass, so if the extra features of the subclasses are not needed, the original.

![](image_rsrc3MG.jpg)

* * *

# Example

Assume you have a system that calculates the areas of different shapes, and you want to extend it to support new shapes without modifying the existing code.This is how you can do it.

| // Shape class (Base class)public abstract class Shape {public abstract double calculateArea();}// Rectangle class (Extends Shape)public class Rectangle extends Shape {private double width;private double height;public Rectangle(double width, double height) {this.width = width;this.height = height;}@Overridepublic double calculateArea() {return width * height;}}// Circle class (Extends Shape)public class Circle extends Shape {private double radius;public Circle(double radius) {this.radius = radius;}@Overridepublic double calculateArea() {return Math.PI * radius * radius;}}// AreaCalculator classpublic class AreaCalculator {public double calculateArea(Shape shape) {return shape.calculateArea();}} |

Now, let's say you want to add a new shape, a Triangle, without modifying the existing code. According to the Open-Closed Principle, you should be able to extend the system without changing the existing classes.

| // Triangle class (Extends Shape)public class Triangle extends Shape {private double base;private double height;public Triangle(double base, double height) {this.base = base;this.height = height;}@Overridepublic double calculateArea() {return 0.5 * base * height;}} |

| // Updated AreaCalculator class (no modification needed)public class AreaCalculator {public double calculateArea(Shape shape) {return shape.calculateArea();}} |

# Think and apply

|  
1.  Whenever you are creating any new class,you must think about re-usability and separation of concerns.

2.  Check the most common feature and keep it in the parent class and you can create a separate class for specific needs.

 |

# The Liskov Substitution Principle (LSP)

* * *

Idea: Subtypes must be substitutable for their base types.

Subtypes must be substitutable for their base types without altering the correctness of the program.

Example: If you have a base class representing shapes, any subclass (like a specific type of shape) should be able to replace the base class without causing issues.

Example: In a zoo program, if you have a base class "Bird," you should be able to substitute it with any specific bird type like "Penguin" or "Eagle" without breaking the program.

* * *

# Explanation

It is one of the SOLID principles of object-oriented programming and software design. It was introduced by Barbara Liskov in 1987 and emphasizes the importance of inheritance and polymorphism in object-oriented systems.

# The LSP states

"Subtypes must be substitutable for their base types."

In simpler terms, the LSP implies that objects of derived classes should be able to replace objects of the base class without affecting the correctness of the program.

In other words, if a class is designed to be a subtype (a derived or child class) of another class (the base or parent class), it should conform to the contract or behavior of the base class in a way that it can be used interchangeably.

# The key ideas behind the LSP include

Behavioral Compatibility: Subtypes should not change or violate the behavioral expectations of the base type. This means that they should provide at least the same interface as the base type, and their methods should adhere to the same expectations.

Inheritance Is-a Relationship: When you create a subtype, it should genuinely represent an "is-a" relationship with the base type. In other words, a derived class should be a more specialized version of the base class.

Polymorphism: The LSP enables polymorphism, allowing objects of different classes to be treated uniformly through their common base type. This simplifies code and promotes flexibility and reuse.

Robustness: Adhering to the LSP contributes to the robustness of the software because it ensures that derived classes won't introduce unexpected behavior or errors when used in place of their base classes.

Failure to adhere to the Liskov Substitution Principle can lead to incorrect program behavior, making the software more error-prone and harder to maintain. In practice, it's crucial to carefully design and implement inheritance hierarchies to ensure that the LSP is satisfied, and derived classes are true substitutes for their base classes, providing a consistent and predictable experience when using polymorphism.

* * *

# Example

you have a base class called Shape, representing various geometric shapes. It has a method calculateArea() for calculating the area of the shape.

| public class Shape {public double calculateArea() {return 0;}} |

Now, you create two derived classes, Rectangle and Circle, which are specialized shapes. These derived classes should adhere to the Liskov Substitution Principle, meaning they should be substitutable for the base class and provide their own implementations of calculateArea() without violating the base class contract.

Here's how you can implement the Rectangle and Circle classes

| public class Rectangle extends Shape {private double width;private double height;public Rectangle(double width, double height) {this.width = width;this.height = height;}@Overridepublic double calculateArea() {return width * height;}} |

| public class Circle extends Shape {private double radius;public Circle(double radius) {this.radius = radius;}@Overridepublic double calculateArea() {return Math.PI * radius * radius;}} |

● The Rectangle and Circle classes inherit from the Shape class, indicating an "is-a" relationship, where a rectangle and a circle are specific types of shapes.

● Both derived classes override the calculateArea() method with their own implementations, which are appropriate for calculating the area of a rectangle and a circle.

● These derived classes conform to the LSP, as they can be used interchangeably with the base Shape class without causing issues or violating the expected behavior. For example, you can create an array of shapes and calculate the area of each shape without knowing the specific subclass.

Here's an example of how you can use these classes:

| Shape[] shapes = new Shape[] {new Rectangle(5, 10),new Circle(3)};for (Shape shape : shapes) {System.out.println("Area: " + shape.calculateArea());} |

This example demonstrates how the LSP allows you to create specialized subclasses that can be used seamlessly alongside the base class, enabling polymorphism and making your code more flexible and robust.

# The Interface Segregation Principle (ISP)

* * *

Idea: A class should not be forced to implement interfaces it does not use.

Example: If an interface has multiple methods and a class only needs to use a few of them, it should not be obligated to implement the unnecessary methods.

Example: Think of a machine interface. If you have a simple machine that only starts and stops, it shouldn't be forced to implement a method for maintenance. Different machines can implement different interfaces based on their capabilities.

* * *

# Explanation

It is one of the SOLID principles of object-oriented design. It emphasizes that classes should not be forced to implement interfaces that contain methods they don't need. In other words, clients (classes or modules that use interfaces) should not be dependent on methods they don't use. Instead, interfaces should be designed to be small, focused, and tailored to specific use cases.

Here's a detailed explanation of the Interface Segregation Principle in the context of Java.

# Problem Without ISP

Suppose you're designing an interface for a generic machine.

The interface includes methods like start(), stop(), and performMaintenance().

However, not all machines require maintenance. You create a class for a basic machine that doesn't need to perform maintenance.

* * *

# Example

| interface Machine {void start();void stop();void performMaintenance();}class BasicMachine implements Machine {public void start() {// Implementation for starting the machine}public void stop() {// Implementation for stopping the machine}public void performMaintenance() {// This method is not needed for BasicMachine, but it's required to implement the Machine interface.// The implementation is empty.}} |

In this example, the BasicMachine class is forced to implement the performMaintenance() method, even though it doesn't need it. This violates the ISP because the class is being forced to depend on methods it doesn't use.

# Applying ISP in Java

To adhere to the Interface Segregation Principle, you should design interfaces that are specific to their implementing classes. In this case, you can create a separate interface for machines that require maintenance:

| interface Startable {void start();void stop();}interface Maintainable {void performMaintenance();}class BasicMachine implements Startable {public void start() {// Implementation for starting the machine}public void stop() {// Implementation for stopping the machine}}class MaintenanceMachine implements Startable, Maintainable {public void start() {// Implementation for starting the machine}public void stop() {// Implementation for stopping the machine}public void performMaintenance() {// Implementation for performing maintenance}} |

# In this revised design

●         The Startable interface includes methods related to starting and stopping machines.

●         The Maintainable interface includes the performMaintenance() method, which is only relevant to machines that require maintenance.

The BasicMachine class implements the Startable interface because it only needs to start and stop, while the MaintenanceMachine class implements both the Startable and Maintainable interfaces, as it requires both functionalities.

By applying ISP, you ensure that each class or interface has a specific, well-defined purpose, and clients are only forced to depend on what they need. This promotes cleaner, more maintainable code and reduces the risk of unnecessary dependencies and empty method implementations.

* * *

OR you can make the method default so that it's NOT mandatory for clients to provide implementation.

If you are using java 9+ then you can use the default method in the interface.

| public interface Machine {void start();void stop();default void performMaintenance(){//default implementation}} |

BasicMachine Implementation where you no need to implement the performMaintenance() method since it's NOT required for you.

| public class BasicMachine implements Machine{@Overridepublic void start() {//provide implementation to start}@Overridepublic void stop() {//provide implementation to stop}} |

Add a new class AdvancedMacgine where you need to implement performMaintenance()  method.

| public class AdvancedMachine implements Machine{@Overridepublic void start() {}@Overridepublic void stop() {}@Overridepublic void performMaintenance() {//Machine.super.performMaintenance();//Add your implementation}} |

# Dependency Inversion Principle (DIP)

* * *

Idea: High-level modules should not depend on low-level modules; both should depend on abstractions.

Example: Instead of a higher-level module relying directly on a lower-level module, both should depend on an abstract interface. This promotes flexibility and makes the system less tightly coupled.

Example: Consider a light switch. It depends on electricity (low-level), but the switch and the bulb both depend on the abstraction of a "Switchable" interface. This way, you can change the bulb or the switch independently without affecting each other.

* * *

The Dependency Inversion Principle (DIP) is one of the SOLID principles of object-oriented design. It emphasizes the need for high-level modules (classes or components) to not depend on low-level modules, but rather both should depend on abstractions (interfaces or abstract classes). Additionally, it suggests that details (low-level implementation) should depend on abstractions, not the other way around.

# Example

| // Low-level moduleclass EmailService {public void sendEmail(String message) {// Logic to send an emailSystem.out.println("Email: " + message);}}// High-level module directly depends on low-level moduleclass NotificationService {private EmailService emailService = new EmailService();public void sendNotification(String message) {emailService.sendEmail(message);}}// Client codepublic class Client {public static void main(String[] args) {NotificationService notificationService = new NotificationService();notificationService.sendNotification("Hello, world!");}} |

In this example,  NotificationService directly depends on  EmailService, violating the Dependency Inversion Principle. Now, let's refactor it to adhere to DIP:

| // Abstraction for notification serviceinterface Notification {void sendNotification(String message);}// Low-level module implements the abstractionclass EmailService implements Notification {@Overridepublic void sendNotification(String message) {// Logic to send an emailSystem.out.println("Email: " + message);}}// High-level module depends on the abstractionclass NotificationService {private Notification notification;public NotificationService(Notification notification) {this.notification = notification;}public void sendNotification(String message) {notification.sendNotification(message);}}// Client codepublic class Client {public static void main(String[] args) {Notification emailService = new EmailService();NotificationService notificationService = new NotificationService(emailService);notificationService.sendNotification("Hello, world!");}} |

Now, NotificationService depends on the Notification interface rather than the concrete EmailService. This adheres to the Dependency Inversion Principle, allowing for more flexibility. If you want to introduce a new notification method (e.g., SMS), you can create a new class implementing the Notification interface without modifying the existing code.

By applying DIP, the high-level module (NotificationService) is no longer tightly coupled to the low-level module (EmailService), and both depend on abstractions, providing a more flexible and maintainable design.

* * *

In other words, the Dependency Inversion Principle encourages loose coupling between different parts of a software system. This loose coupling makes the system more flexible, maintainable, and adaptable to changes.

Software dependency, or coupling, is a common problem that needs to be addressed in system design. Coupling defines how much reliance there is between different components of your software. High coupling indicates a high degree of reliance. Low coupling indicates low dependency. Dependency determines how easily changes can be made to a system.

If parts of a system are dependent on each other, then substituting a class or resource for another is not easily done, or even impossible.

The dependency inversion principle addresses dependency, to help make systems more robust and flexible. The principle states that high-level modules should depend on high-level generalizations, and not on low-level details. This keeps client classes independent of low-level functionality.

This suggests that client classes should depend on an interface or abstract class, rather than a concrete resource. Further, concrete resources should have their behaviors generalized into an interface or abstract class. Interfaces and abstract classes are high-level resources. They define a general set of behaviors. Concrete classes are low-level resources. They provide the implementation for behaviors.

All the design patterns covered in this course are built on this dependency inversion principle.

# Low Level Dependency

In order to better understand the dependency inversion principle, let us examine low-level dependency. In a low-level dependency, the client classes name and make direct references to a concrete class. Subsystems are directly dependent on each other, so the client class will directly reference some concrete class in the enterprise subsystem, which will directly reference some concrete class in your backend.

* * *

![](image_rsrc3MH.jpg)

Let us examine this as code.

![](image_rsrc3MJ.jpg)

This has a low-level dependency. There is direct naming and referencing to the concrete class, QuickSorting, which is used in this example to sort a list sent to the system by a user. However, if a different sorting class called MergeSort were to be implemented, significant changes would need to be made to the ClientSubsystem class. The type of sorting class would have to change, as well as the sorting method call. This would require a great deal of work every time a change needed to be made to the sorting algorithm.

* * *

Here are some key points to understand the Dependency Inversion Principle (DIP) in more detail:

High-Level Modules vs. Low-Level Modules:

● High-level modules are the components or classes that provide the overall structure and logic of an application. They represent the core functionality.

● Low-level modules are the details, utilities, or components that support the high-level modules. They typically interact with hardware, databases, or other external resources.

Depend on Abstractions:

● The DIP suggests that high-level modules should depend on abstractions (abstract classes or interfaces) rather than on concrete implementations (low-level modules). This means high-level modules should not directly reference specific low-level modules.

●         Abstractions define a contract that high-level modules can rely on without worrying about the implementation details.

Inversion of Control (IoC):

● IoC is a common technique used to implement DIP. It involves inverting the control of the flow of a program. Instead of high-level modules controlling low-level modules, a higher-level component controls the overall flow, including the interaction with low-level modules.

Benefits of DIP:

● Loose coupling: DIP reduces the direct dependencies between components, making the system more flexible and easier to change. If low-level modules need to be replaced or updated, it doesn't affect high-level modules.

● Testability: DIP enables easier unit testing, as you can substitute low-level components with mock objects or stubs during testing.

● Reusability: By depending on abstractions, you promote the reuse of high-level modules in different contexts, as they are not tightly coupled to specific low-level implementations.

Examples of DIP Implementation:

● Inversion of control containers (e.g., Spring or Guice) in Java implements DIP by managing the instantiation and configuration of objects.

● Design patterns like the Factory Method and Dependency Injection are commonly used to adhere to the Dependency Inversion Principle.

●          

In practice, the Dependency Inversion Principle encourages the creation of clean and modular software, where changes to low-level components have minimal impact on the overall system. It fosters a more adaptable and maintainable codebase, making it an essential principle in modern software engineering and design.

* * *

# Anti-Patterns and Code Smells

* * *

In Object-Oriented Analysis and Design (OOAD), "anti-patterns" and "code smells" refer to common design issues and coding practices that can lead to suboptimal software solutions. They are signals that the design or code might need improvement.

Let's explore each concept:

# Anti-Patterns

* * *

Anti-patterns are recurring solutions to common problems that are ineffective and counterproductive. They represent design approaches that seem intuitive but, when applied, lead to poor or problematic outcomes.

Example: An example of an anti-pattern is the "God Object," where a single class knows or does too much. This violates the Single Responsibility Principle (SRP) and makes the system less maintainable.

# Code Smells

* * *

Code smells are specific indicators in the source code that suggest there might be a problem with the design or implementation. They are not necessarily bugs but rather areas that might benefit from refactoring for better maintainability, readability, or efficiency.

Example: A common code smell is "Long Method," where a method is excessively long and performs multiple tasks. This can make the code harder to understand and maintain.

Both anti-patterns and code smells can be addressed through refactoring, which involves restructuring the code without changing its external behavior. Recognizing and addressing these issues early in the development process can contribute to a more maintainable and scalable software system.

# Differences:

● Scale: Code smells are usually small, localized issues within the code, while anti-patterns are larger design or architectural problems that affect the entire system.

● Detection: Code smells can often be detected through automated code analysis tools, while identifying anti-patterns may require a more comprehensive understanding of the overall system design.

● Impact: Code smells may impact individual methods or classes, making them harder to maintain. Anti-patterns, on the other hand, can have a more profound impact on the overall system, leading to issues like poor scalability or maintainability.

● Resolution: Resolving code smells often involves refactoring specific parts of the code. Addressing anti-patterns may require a more holistic approach, potentially involving changes to the overall system architecture.

In summary, while code smells and anti-patterns both highlight potential issues in software development, code smells are smaller-scale and more localized, focusing on specific coding practices, whereas anti-patterns address larger design and architectural problems that can have a systemic impact on the software.

* * *

# Overview

Refactoring is the process of improving the structure of your code without changing how it behaves externally. It involves making small, gradual changes and testing frequently to ensure that the code still works as intended. Ideally, refactoring is done when adding new features, making it easier and more efficient.

Code changes are often necessary due to bad code patterns, known as anti-patterns or code smells. Martin Fowler's book "Refactoring" identifies these issues and provides ways to improve them. Code smells act like a "sniff test" for identifying problematic code.

One common example of bad code is excessive or insufficient comments. If there are no comments, it can be hard to understand the code's purpose later on. However, too many comments can become outdated and mask underlying issues. Comments serving as reminders or explaining code that should be updated indicate potential problems.

Comments can also reveal issues with the choice of programming language. In the past, developers used comments in Java to explain type casting before generics were introduced. While comments are valuable for documenting APIs or explaining design choices, their excessive use may suggest underlying problems in the code.

In summary, refactoring helps manage code changes while maintaining external behavior. Code smells, like too many comments, indicate areas for improvement. Striking a balance in commenting and addressing code smells enhances code quality.

# Duplicate Code

* * *

Duplicated code happens when you have similar blocks of code in different parts of your software. If you need to make a change, you have to update it in multiple places, which can be tricky. It's like having the same recipe written in different cookbooks—if you change the recipe, you need to update every copy.

Following the "Don't Repeat Yourself" (D.R.Y.) principle helps. It suggests writing code in a way that lets you do the same tasks with less code. This makes updates easier and reduces the chance of missing a spot.

Another issue is the "Long Method" anti-pattern, where code methods are too long. Long methods can make your code harder to understand. While some tasks naturally need more code, having overly long methods might mean there's too much going on. Context matters, though—sometimes, in certain programming languages, longer methods are okay.

In a nutshell, avoiding duplicated code and keeping methods a reasonable length make your code easier to work with and understand.

* * *

Duplicate Code is a common "code smell," indicating a potential problem in the design or structure of your code. This occurs when identical or very similar code blocks appear in different parts of your software. It's like having a recipe repeated in different sections of a cookbook.

# Signs of Duplicate Code

Identical or Similar Blocks: Look for code segments that perform the same or very similar tasks.

Copy-Pasting: If you find instances where code seems to be copied and pasted in different places.

# Why Duplicate Code is a Smell

Maintenance Challenge: If you need to make a change, you might have to update the same code in multiple locations, which can be error-prone and time-consuming.

Consistency Issues: It increases the risk of inconsistency. If you forget to update one instance, it can lead to bugs or unexpected behavior.

Readability and Understanding: Code duplication can make the codebase harder to read and understand, as developers may need to navigate through multiple locations to comprehend the logic.

# Addressing Duplicate Code

Refactoring: Identify duplicated code and refactor it by creating a shared function, method, or class that can be reused.

Abstraction: Look for opportunities to abstract common functionality into a single, central place.

Code Reviews: Regular code reviews can help catch instances of duplicate code early in the development process.

# Example

Consider a scenario where the same input validation logic appears in multiple parts of your code. Instead of duplicating the validation code, you can create a separate function or method to handle input validation, making it more modular and easier to maintain.

# Benefits of Eliminating Duplicate Code

Easier Maintenance: Changes can be made in one place, reducing the risk of overlooking updates in other locations.

Improved Readability: Code becomes more concise and readable without unnecessary redundancy.

Consistent Behavior: Ensures that the same logic is applied consistently throughout the software.

By addressing Duplicate Code, you contribute to a cleaner, more maintainable codebase, making it easier for developers to understand, modify, and enhance the software.

# Example

| // Class A with duplicated codepublic class ClassA {public int calculateSquare(int number) {return number * number;}// ... other methods and code}// Class B with duplicated codepublic class ClassB {public int calculateSquare(int number) {return number * number;}// ... other methods and code} |

In this example, both  ClassA and  ClassB have a method named  calculateSquare that performs the same task—calculating the square of a given number. This is a clear case of duplicated code.

To address this code smell, you can refactor the code by creating a shared utility class or method:

| // Shared utility class with a method for calculating the squarepublic class MathUtils {public static int calculateSquare(int number) {return number * number;}}// Class A using the shared utility methodpublic class ClassA {public int calculateSquare(int number) {return MathUtils.calculateSquare(number);}// ... other methods and code}// Class B using the shared utility methodpublic class ClassB {public int calculateSquare(int number) {return MathUtils.calculateSquare(number);}// ... other methods and code |

Now, the common logic for calculating the square is moved to the  MathUtils class, and both  ClassA and  ClassB use this shared method. This eliminates the duplicated code smell, making the code more maintainable and reducing the risk of inconsistencies if the logic ever needs to change.

* * *

# Large Class

* * *

The "Large Class" code smell is like having a super busy person who tries to do everything. In coding, it happens when a class becomes too big and tries to handle too many tasks.

This is a problem because it can make the code hard to understand and maintain.

Big classes are often called "God classes," "Blob classes," or "Black Hole classes."

These classes start off normal but keep growing because more and more responsibilities are added to them. People think it's okay to put new tasks in these classes, but over time, they just get bigger and take on too much.

When a class becomes large, it needs a lot of comments to explain where different things are in the code. But having too many comments is also a sign of bad code. It's important to notice this problem early because fixing it later can be hard and take a lot of time.

Good classes should have a clear purpose, meaning they should focus on doing one thing really well. If some job doesn't fit the main purpose of the class, it's usually better to put that task somewhere else.

This helps to keep the class organized and easy to understand.

* * *

# Signs of the Large Class code smell

Too Many Jobs: The class does too many things, like handling data, talking to databases, and sending emails.

Lots of Stuff: The class has tons of methods and fields, making it look like a big mess.

Confusing: It's hard to figure out what the class is really supposed to do.

# How to Fix It:

One Job Rule: Make sure each class does only one main thing, like handling data or sending emails.

Tidy Up: Organize methods and fields into smaller groups that make sense together.

Teamwork: Let smaller classes work together on different tasks.

# Example:

Imagine a class called BigWorker that does everything—manages data, talks to databases, sends emails, and more. To fix it, we create smaller classes like DataManager, DatabaseHandler, and EmailSender. Each does its own specific job, making the code cleaner and easier to manage.

| // Large Class handling multiple responsibilitiespublic class LargeClassDemo {private String customerName;private int customerAge;private String customerAddress;private String phoneNumber;// Constructor, getters and setterspublic void displayCustomerInfo() {// Code to display customer information}public void saveCustomerToDatabase() {// Code to save customer information to the database}public void sendEmailNotification() {// Code to send email notification to the customer}public void processOrder() {// Code to process customer orders}// ... other methods and code} |

In this example, the LargeClass is responsible for managing customer information, saving to a database, sending email notifications, and processing orders. It has multiple responsibilities, making it a candidate for the "Large Class" code smell.

# Signs of the "Large Class" code smell in this example

Numerous Methods: The class has a significant number of methods (displayCustomerInfo, saveCustomerToDatabase, sendEmailNotification, processOrder, etc.).

Many Fields: The class has multiple fields (customerName, customerAge, customerAddress, phoneNumber).

Multiple Responsibilities: The class performs tasks unrelated to its core purpose, such as displaying information, saving to a database, and processing orders.

# How to Address the "Large Class" Code Smell

Identify Responsibilities: Break down the class into smaller classes, each handling a specific responsibility (e.g., one for customer information, one for database operations, one for email notifications).

Encapsulation: Group related fields and methods together in separate classes.

Delegation: Delegate specific tasks to appropriate classes.

Collaboration: Encourage collaboration between smaller classes.

By addressing the "Large Class" code smell, you create a more modular and maintainable codebase, where each class has a clear and focused responsibility.

* * *

# Long Method

* * *

Symptom: A method is excessively long, making it hard to understand.

Impact: Reduced readability, difficulty in maintaining and testing.

Example Fix: Break down the method into smaller, more manageable methods

# Feature Envy

* * *

Feature envy is a code smell that occurs when there is a method that is more interested in the details of a class other than the one it is in. If two methods or classes are always talking to one another and seem as if they should be together, then chances are this is true.

Symptom: A class uses methods or fields of another class excessively.

Impact: Tight coupling, reduced encapsulation, potential for high dependency.

Example Fix: Move the relevant methods or fields to the class that needs them.

# Inappropriate Intimacy

* * *

Symptom: Classes are too tightly coupled, often accessing each other's internals.

Impact: Reduced flexibility, increased complexity, challenges in maintenance.

Example Fix: Encapsulate related functionality and reduce direct dependencies.

* * *

Inappropriate intimacy is like a code problem when two classes are too close to each other, talking back and forth too much.

Imagine two friends who keep talking and asking each other for help all the time. In code, this is when two classes depend on each other too much, like one class calling the other's methods and vice versa.

# How To fix

It's a good idea to make the communication more organized. Instead of both classes talking to each other in a loop, we can create another class in the middle. This way, communication becomes more one-sided, like passing a message through a friend. It helps keep things simple and easy to understand.

Sometimes, having classes talk back and forth is necessary, like friends needing to chat. But if we can make the design simpler and easier to understand, that's a good solution. It's like finding a better way for friends to communicate without getting too tangled up.

* * *

# Primitive Obsession

Symptom: Overuse of primitive types instead of creating custom objects.

Impact: Reduced code readability, potential for bugs related to data handling.

Example Fix: Create classes to represent domain-specific concepts rather than relying solely on primitive types.

Primitive obsession is like a code problem that happens when you use basic types (like ints, strings) too much in your code. While these types are necessary, they should be used mostly in the lower levels of your code. When you use them too often, it means you might be missing out on creating better, more specific classes for your code.

Imagine if everything in a system was just stored as simple strings or arrays. Back in the 1960s, this was how code looked. But as languages evolved, we learned to create our own types for better organization. If everything is stored as a string, it can hide important details, and it becomes hard to see the overall design of the system. Using too many basic types at a high level suggests that you might be missing the chance to create better, more specialized classes in your system.

Switch statements are another issue. They are like road signs scattered throughout your code, and if you change one, you have to find and update all the others. While long if/else statements are sometimes needed, having too many switch statements is a sign that things could be handled better. For example, if you find yourself checking type codes or types in your conditions, there might be a better way to organize your code using polymorphism, a technique that allows you to handle different types more efficiently.

* * *

# Shotgun Surgery

Symptom: A single change requires modifications in multiple places.

Impact: Increased risk of errors, maintenance challenges.

Example Fix: Consolidate related functionality in a single location to avoid scattered changes.

It is a code smell that occurs when a change needs to be made to one requirement, and numerous classes all over the design need to be touched to make that one change. In good design, a small change is ideally localized to one or two places (although this is not always possible).

This is a commonly occurring code smell. It can happen if you are trying to add a feature, adjust code, fix bugs, or change algorithms. If changes need to be made all over the code, then the chances of missing a change or creating an issue elsewhere increase.

Modular code is not always an option, however. Some changes require shotgun surgery no matter how well designed the code is. For example, changing a copyright statement or licensing will require changing every file in the system to update the block of copyright text.

The shotgun surgery smell is normally resolved by moving methods around. If a change requires you to make changes to many methods in different classes, then that can be an indicator that the methods may be better consolidated into one or two classes. However, you must be careful not to move so many methods into one class because it becomes a large class code smell.

If a change in one place leads to changes in other places, then this indicates that the methods are related in some way. Perhaps there is a better way to organize them. If not, then you may have to deal with it as it is.

* * *

# Comments Abuse

Symptom: Excessive or misleading comments, often used to cover up bad code.

Impact: Maintenance challenges, outdated comments, potential for misinterpretation.

Example Fix: Improve code clarity, remove unnecessary comments, and use comments sparingly for clarity.

* * *

# Lazy Class

Symptom: Classes that don't do much and have minimal impact on the system.

Impact: Code bloat, reduced clarity, unnecessary complexity.

Example Fix: Either remove the class or consolidate its functionality with other classes.

* * *

# Cyclic Dependencies

Symptom: Classes depend on each other in a circular manner.

Impact: Reduced modularity, challenges in understanding and maintaining the code.

Example Fix: Reorganize classes or use dependency injection to break cyclic dependencies.

* * *

# Lava Flow

The Lava Flow Anti-Pattern occurs when outdated or unused code is retained in the system because developers are afraid to remove it due to uncertainty about its impact. This can lead to a codebase cluttered with unnecessary and confusing artifacts.

# Golden Hammer (or Silver Bullet)

This anti-pattern involves using a specific technology, tool, or design pattern for every problem, regardless of whether it is the most suitable solution. It can lead to overcomplicated designs and missed opportunities to explore more appropriate alternatives.

# Copy and Paste Programming

This anti-pattern involves duplicating code instead of creating reusable abstractions. It can lead to maintenance issues, as changes must be made in multiple places whenever there is a need for modification.

* * *

# Points to remember

| 1.While writing code,ensure that your code does not contain any of the above code smells are anti-patterns.2\. You can use tools for code quality checks in your local system.3.you can use sonarqube and other applicable tools for coverage and code smells check. |

# Design Pattern

* * *

Design patterns are standardized solutions to common software design problems. They offer a structured and proven way to solve recurring issues in software development.

Imagine design patterns as recipes in cooking. Just like when you cook, there are certain ways people have tried and tested to create delicious dishes. Over time, they figure out the best steps to make the food taste amazing. Similarly, in coding, design patterns are like these well-known ways of doing things that have proven to be effective. They're like the go-to recipes for creating reliable and efficient software because they've been experimented with and used successfully by many developers.

![](image_rsrc3MK.jpg)

Think of making Biryani. You might know what ingredients are needed, or you can find the recipe online. But if you ask 10 people to cook it, each Biryani might taste a bit different. That's because how you cook it matters. An expert cook knows how to handle things for the best taste. In software design, it's similar. We know how to code, but to make our code flexible, reusable, easy to maintain, strong, and simple, we use design patterns. It's like having a set of expert cooking techniques for coding!

# Type of Design Pattern

* * *

# 1.    Creational patterns

# 2.    Structural patterns

# 3.    Behavioral patterns

These classifications help developers choose the right design patterns based on the specific problem they are trying to solve. Creational patterns are concerned with object creation, structural patterns with object composition, and behavioral patterns with object collaboration and communication.

Using a combination of these patterns allows developers to create more maintainable, modular, and scalable software solutions in Java.

# Creational patterns

* * *

Creational patterns tackle how you handle creating or cloning new objects. Cloning an object occurs when you are creating an object that is similar to an existing one, and instead of instantiating a new object, you clone existing objects instead of instantiating them.

These patterns are focused on the process of object creation. They provide mechanisms for creating objects in a way that is flexible, efficient, and independent of the system's architecture.

Examples : Singleton, Factory Method, Abstract Factory, Builder, and Prototype patterns.

# Singleton Design Pattern

* * *

The Singleton Design Pattern is a creational design pattern that ensures a class has only one instance and provides a global point of access to that instance. This pattern is useful when exactly one object is needed to coordinate actions across the system, such as a single database connection or a logging service

A singleton is a special way to create an object, and it's one of the easiest design patterns. It's like having only one of something. Imagine you have a favorite pen that you always use. That pen is your "singleton" pen because it's the only one you want to use, and it's easy to know where it is.

In computer programs, a singleton is useful when you want only one instance (or object) of something. For example, think about the settings in an app, the waiting list for your printer, or the software that controls a device. It's better to have just one of these things to avoid confusion.

The goal of the singleton pattern is to make sure this single thing is easily available to the whole program. To do this, we make it so that creating more than one of these special objects isn't even possible. It's like saying, "There can be only one!" This is important when many people are working on a big project or even for smaller projects because it keeps things clear and avoids problems.

* * *

# Let us examine this in code

If a class has a public constructor, an object of this class can be instantiated at any time.

Instead, if the class has a private constructor, then the constructor cannot be called from outside the class. Although this seems to prevent creating an object of the class, there are two key components for getting around this.

First, declare a class variable. In this case, it is called “unique Instance.” This class variable will refer to the one instance of your Singleton class. As the variable is private, it can only be modified within the class.

Second, create a public method in the class that will create an instance of this class, but only if an instance does not exist already. In this case, the method is called “getInstance.” It will check if the “unique Instance” variable is null. If it is null, then it will instantiate the class and set this variable to reference the object. On the other hand, if the “unique Instance” class variable currently references an object, meaning that there is already an object of this class, then the method will simply return that object. As the getInstance() method is public, it can be called globally and used to create one instance of the class. In a sense, it replaces the normal constructor.

| public class SingletonClass {private static  SingletonClass singletonClass=null;private SingletonClass() {}public static SingletonClass getInstance(){if(singletonClass==null){singletonClass=new SingletonClass();}return singletonClass;}} |

# Test Singleton class

| public class SingletonDemo {public static void main(String[] args) {System.out.println("#### Singleton Demo :: ");SingletonClass e1=SingletonClass.getInstance();SingletonClass e2=SingletonClass.getInstance();SingletonClass e3=SingletonClass.getInstance();SingletonClass e4=SingletonClass.getInstance();System.out.println("###### Instance e1 :"+e1.hashCode());System.out.println("###### Instance e2 :"+e2.hashCode());System.out.println("###### Instance e3 :"+e3.hashCode());System.out.println("###### Instance e4 :"+e4.hashCode());}} |

Result

| #### Singleton Demo ::###### Instance e1 :681842940###### Instance e2 :681842940###### Instance e3 :681842940###### Instance e4 :681842940 |

As you can see here,the hashcodes of all these 4 instances are the same so it's clear that all the instances are the same.

In the example above, the regular constructor is hidden. Other classes are forced to call the public “getInstance” method. This puts in place basic gatekeeping and ensures that only one object of this class is created. The same method can be used to globally reference a single object if it has already been created.

An advantage of this version of a Singleton class is lazy creation. Lazy creation means that the object is not created until it is truly needed. This is helpful, especially if the object is large. As the object is not created until the “getInstance” method is called, the program is more efficient.

There are trade-offs to the Singleton design principle. If there are multiple computing threads running, there could be issues caused by the threads trying to access the shared single object.

In real use, there may be variations of how Singleton is realized because design patterns are defined by purpose and not exact code. The intent of a Singleton pattern is to provide global access to a class that is restricted to one instance. In general, this is achieved by having a private constructor with a public method that instantiates the class “if” it is not already instantiated.

* * *

# Factory Method Pattern

* * *

The Factory Design Pattern is like a blueprint for creating objects in a flexible and organized way. Imagine you're building different types of cars in a factory. You have a blueprint (the design pattern) that tells you how to build each type of car. This way, you can create cars with specific features without worrying too much about the details every time.

It says define an interface or abstract class for creating an object but let the subclasses decide which class to instantiate.

Factory Method Pattern allows the sub-classes to choose the type of objects to create.

It promotes the loose-coupling by eliminating the need to bind application-specific classes into the code.

Factory design pattern will return instances of required type based on given context.

As you can see in the below example,based on need, the factory will provide different type of shape instances.

| public interface Shape {void draw();} |

| package playwithjava.in.factory;public class Circle implements Shape{@Overridepublic void draw() {System.out.println("##### Circle ::draw() called");}} |

| package playwithjava.in.factory;public class Rectangle implements Shape{@Overridepublic void draw() {System.out.println("##### Rectangle ::draw() called");}} |

| package playwithjava.in.factory;public class Square implements Shape{@Overridepublic void draw() {System.out.println("##### Squire ::draw() called");}} |

| package playwithjava.in.factory;public class ShapeUtil {public static Shape getShape(String shapeType){if (ShapeEnum.CIRCLE.name().equals(shapeType)){return new Circle();}else if (ShapeEnum.RECTANGLE.name().equals(shapeType)){return new Rectangle();}else if (ShapeEnum.SQUIRE.name().equals(shapeType)){return new Square();}else {return null;}}} |

As you can see below , instances for Circle,Square and Rectangle get created based on params passed to factory class.

| package playwithjava.in.factory;public class FactoryDemo {public static void main(String[] args) {Shape shape1=ShapeUtil.getShape(ShapeEnum.CIRCLE.name());shape1.draw();Shape shape2=ShapeUtil.getShape(ShapeEnum.RECTANGLE.name());shape2.draw();Shape shape3=ShapeUtil.getShape(ShapeEnum.SQUIRE.name());shape3.draw();}} |

# Structural Design Pattern

* * *

Structural Design Patterns describe how objects are connected to each other. These patterns relate to the design principles of decomposition and generalization.

These patterns are concerned with how classes and objects are organized to create more flexible and maintainable systems. Structural patterns emphasize the relationships between classes and objects, defining ways to compose them into larger structures.

These structural design patterns help in organizing classes and objects to create more maintainable and extensible systems.

There are many different ways that you can structure objects depending on the relationship you’d like between them. Not only do structural patterns describe how different objects have relationships, but they also describe how subclasses and  classes interact through inheritance. Structural patterns use these relationships and describe how they should work to achieve a particular design goal. Each structural pattern determines the various suitable relationships among the objects.

A good metaphor for considering structural patterns is that of pairing different kinds of foods together: flavor determines what ingredients can be mixed together to form a suitable relationship.Some relationships combine ingredients together, such as chickpeas and garlic in hummus. Some relationships still combine ingredients, but those ingredients may maintain some independence, like a salad of mixed vegetables. Some relationships allow a pairing of ingredients, without a physical combination, like wine and cheese.

# Below are list of Structural design patterns in OOAD

●     Adapter Pattern

●     Facade Pattern

●     Decorator Pattern

●     Composite Pattern

●     Bridge Pattern

●     Flyweight Pattern

●     Proxy Pattern

# Adapter Pattern

* * *

Adapter design pattern is helpful to enable two unrelated interfaces can work together.

Think of an adapter like a superhero cape for objects. It covers them up and does some fancy tricks without them knowing. Imagine you have a robot (let's call it Robot Buddy) that speaks in a secret code (like beeps), but you want it to chat with your friend who only understands English.

So, you get an adapter, which is like a magic cloak. You put this cloak around Robot Buddy. Now, whenever Robot Buddy beeps, the adapter quickly turns those beeps into English words. Your friend hears English, and Robot Buddy just keeps beeping happily, not realizing the translation magic that's happening.

In simpler terms, the adapter is a sneaky helper that makes sure two things can talk to each other without one of them knowing a different language. It's like having a universal language translator for objects!

it converts the interface of one object so that another object can understand it.

Lets understand with an example.

# Existing class with a method that gets measurements  in meters.

| class MeterMeasurement {public double getMeasurementInMeters() {return 10.0; //return sample hardcoded value in meter.}} |

Assume that you have some requirements to get measurements in feet but your existing functionality is providing results in meters then what you will do ?

| interface ImperialMeasurement {double getMeasurementInFeet();} |

Adapter class that makes MeterMeasurement compatible with ImperialMeasurement, creates a class that implements the target interface.

Here in our case,ImperialMeasurement is the target interface here.

Create a class that implements ImperialMeasurement.

![](image_rsrc3MM.jpg)

| class MeterToFeetAdapter implements ImperialMeasurement {private MeterMeasurement meterMeasurement;public MeterToFeetAdapter(MeterMeasurement meterMeasurement) {this.meterMeasurement = meterMeasurement;}@Overridepublic double getMeasurementInFeet() {// Conversion from meters to feetreturn meterMeasurement.getMeasurementInMeters() * 3.28084;}} |

# Client code that expects measurements in feet.

| class Client {public void displayMeasurementInFeet(ImperialMeasurement imperialMeasurement) {System.out.println("Measurement in Feet: " + imperialMeasurement.getMeasurementInFeet());}} |

| public class AdapterExample {public static void main(String[] args) {// Existing object with a method in metersMeterMeasurement meterMeasurement = new MeterMeasurement();// Adapter to make the existing object compatible with the target interfaceImperialMeasurement adapter = new MeterToFeetAdapter(meterMeasurement);// Client code can now work with the adapted objectClient client = new Client();client.displayMeasurementInFeet(adapter);}} |

Facade Pattern

* * *

# The facade design pattern is a means to hide the complexity of a subsystem by encapsulating it behind a unifying wrapper called a facade class.

# It  handles instantiation and redirection of tasks to the appropriate class within the subsystem, provides client classes with a simplified interface for the subsystem, acts simply as a point of entry to a subsystem and does not add more functionality to the subsystem.

# The facade design pattern is a way to provide client classes with an easier means of interacting with the parts of your system.

# Complex subsystems can be difficult to use and navigate. By providing a simpler interface through a facade, client classes will have an easier time successfully using your software.

# As of now it's clear that Facade is nothing the way to create an interface or single point from which all required functionality can be triggered simply.

# Lets understand facade with example

Let's assume that you have 2 Databases MySql and MongoDB and you have to generate reports in HTML and CSV format for both databases.

You can simplify the logic as below.

# Interface

| package playwithjava.in.facade;public interface DBHelper {public void buildExportDataHTML(String tableName); 
public void buildExportDataCSV(String tableName);

} |

| package playwithjava.in.facade;public interface MongoDbHelper extends DBHelper{} |

| package playwithjava.in.facade;public interface MySQLHelper extends DBHelper{} |

| package playwithjava.in.facade;public class MongoDbHelperImpl implements MongoDbHelper{@Overridepublic void buildExportDataHTML(String tableName) {System.out.println("######## generate HTML Report ::MongoDB");}@Overridepublic void buildExportDataCSV(String tableName) {System.out.println("######## generate CSV Report ::MongoDB");}} |

|  
package playwithjava.in.facade;

public class MySqlHelperImpl implements MySQLHelper{@Overridepublic void buildExportDataHTML(String tableName) {System.out.println("######## generate HTML Report ::MySQL");}@Overridepublic void buildExportDataCSV(String tableName) {System.out.println("######## generate CSV Report ::MySQL");}} |

| package playwithjava.in.facade;public class DBClientClass {public static void main(String[] args) {MySQLHelper mySQLHelper=new MySqlHelperImpl();MongoDbHelper mongoDbHelper=new MongoDbHelperImpl();String tableName="employee";mySQLHelper.buildExportDataHTML(tableName);mySQLHelper.buildExportDataCSV(tableName);mongoDbHelper.buildExportDataHTML(tableName);mySQLHelper.buildExportDataCSV(tableName);} 
}

 |

# Composite Pattern

* * *

Using the Composite pattern makes sense only when the core model of your app can be represented as a tree.

The Composite Design Pattern is a structural pattern that lets you compose objects into tree structures to represent part-whole hierarchies. It allows clients to treat individual objects and compositions of objects uniformly.

This design pattern is mostly applicable when we have instances of similar type and we have to deal with them all together in the same way as we do with lists of their type.

As in the example below,you can see that we have an interface Graphic which is a base interface and it has the common methods applicable for its childs.

We have 2 classes ,Ellipse and Circle which is a type of Graphic, here we have to design the system in such a way that we can deal with all these childs in a similar way and we can simply call a common method and respective method implementation will be called.

* * *

# How to implement

1. Make sure that the main structure of your app can be shown like a tree. Think of it as having basic things (like leaves on a tree) and boxes that can hold those basic things or even more boxes. These boxes should be able to hold not only basic things but also other boxes. This way, you're organizing your app in a way that makes it easy to understand, just like how a tree is made up of simple leaves and branches that hold them

2. Declare the component interface with a list of required  methods.

3. Create a leaf class to represent simple elements. Your design may have multiple leaf classes based on your need.

4. Create a container class to represent complex elements. In this class, provide an List field for storing references to sub-elements. The array must be able to store both leaves and containers, so make sure it’s declared with the component interface type.override the method in such a way that all the required login are covered for your requirements

5. Finally, define the methods for addition/removal of child elements in the container.

# Example

Graphic.java(base interface)

| import java.util.ArrayList;import java.util.List;interface Graphic {void draw();} |

Ellipse.java [1st implementation]

| class Ellipse implements Graphic {@Overridepublic void draw() {System.out.println("Ellipse");}} |

Circle.java [2nd implementation]

| class Circle implements Graphic {@Overridepublic void draw() {System.out.println("Circle");}} |

CompositeGraphic.java []

| class CompositeGraphic implements Graphic {private List<Graphic> graphics = new ArrayList<>();// Methods to add and remove graphics from the compositionvoid addGraphic(Graphic graphic) {graphics.add(graphic);}void removeGraphic(Graphic graphic) {graphics.remove(graphic);}@Overridepublic void draw() {System.out.println("Composite Graphic:");for (Graphic graphic : graphics) {graphic.draw();}}} |

| // Client code using the composite patternpublic class CompositePatternExample {public static void main(String[] args) {// Creating individual graphic objectsEllipse ellipse1 = new Ellipse();Ellipse ellipse2 = new Ellipse();Circle circle1 = new Circle();Circle circle2 = new Circle();CompositeGraphic compositeGraphic = new CompositeGraphic();compositeGraphic.addGraphic(ellipse1);compositeGraphic.addGraphic(ellipse2);compositeGraphic.addGraphic(circle1);compositeGraphic.addGraphic(circle2);// Drawing the composite graphic (which contains individual graphics)compositeGraphic.draw();}} |

# Decorator Pattern

* * *

The Decorator design pattern is a structural design pattern that allows behavior to be added to an object dynamically without affecting the behavior of other objects in the same class.

![](image_rsrc3MN.jpg)

In this visual representation, object A is a base object, because it does not contain another object, and has its own set of behaviors. Object B aggregates Object A, allowing Object B to “augment” the behaviors of Object A.

Objects can continue to be added to the stack. So, in the above diagram, Object C aggregates to Object B and augments the behaviors of Object B.

In an aggregation stack, the aggregation relationship is always one-to-one in the decorator design pattern. This allows the stack to build up, so one object is on top of another.

An overall combination of behaviors for stacked objects can be achieved if you call upon the top element, which is Object C in this example.

This would start a series of calls: Object C would call upon Object B, Object B would call upon Object A. Object A would then respond with its behavior, then Object B would add its increment of behavior, followed by Object C.

# Let's understand with an example

Component Interface - The interface or abstract class defining the methods that will be implemented. In our case Car will be the component interface.

This is the interface which contains the required set of methods that we have,based on different variations of Cars like Sports Car and Luxury car we can change the information and price without creating separate classes for each.

| package playwithjava.in.decorator;public interface Car {public double getPrice();public String getCarInfo();} |

This is basic implementation for the Decorator interface which has

| package playwithjava.in.decorator;public class BasicCar implements Car{@Overridepublic double getPrice() {return 1000;}@Overridepublic String getCarInfo() {return "This is Car";}} |

CarDecorator.java

| package playwithjava.in.decorator;import java.awt.*;import java.nio.charset.CharsetDecoder;public class CarDecorator extends BasicCar {Car car;public CarDecorator(Car car) {this.car = car;}@Overridepublic double getPrice() {return super.getPrice();}@Overridepublic String getCarInfo() {return super.getCarInfo();}} |

Implementation for LuxuryCar.

| package playwithjava.in.decorator;public class LuxuryCar extends CarDecorator{public LuxuryCar(Car c) {super(c);}@Overridepublic double getPrice() {return super.getPrice()+2000d;}@Overridepublic String getCarInfo() {return super.getCarInfo()+"With Luxury facilities ";}} |

| package playwithjava.in.decorator;public class SportsCar extends CarDecorator{public SportsCar(Car c) {super(c);}@Overridepublic double getPrice() {return super.getPrice()+3000d;}@Overridepublic String getCarInfo() {return super.getCarInfo()+"With Sports facilities ";}} |

As you can see we have implementations for Luxury Car as well as Sports Car.we have basic implementation for Car interface as BasicCar and we are just adding the additional behavior to that existing BasicCar implementation.

Decorator patterns mostly help us to decorate the object's behavior dynamically in the most simplified way.

As you can see , getCarInfo() and getPrice()  are getting implemented in BasicCar class ,SportsCar and LuxuryCar class.  We are using BasicCar implementation and just adding the additional capability without affecting the BasicCar implementation.

DecoratorDemo.java

| package playwithjava.in.decorator;public class DecoratorDemo {public static void main(String[] args) {Car basicCar=new BasicCar();Car luxuryCar=new LuxuryCar(basicCar);Car sportscar=new SportsCar(basicCar);System.out.println("############ Basic Car ###########");String carInfo1=basicCar.getCarInfo();double price1=basicCar.getPrice();System.out.println("Car Info  : "+carInfo1);System.out.println("Basic Car Price : "+price1);System.out.println("############ Luxury Car ###########");String carInfo2=luxuryCar.getCarInfo();double price2=luxuryCar.getPrice();System.out.println("Car Info  : "+carInfo2);System.out.println("Basic Car Price : "+price2);System.out.println("############ Sports Car ###########");String carInfo3=sportscar.getCarInfo();double price3=sportscar.getPrice();System.out.println("Car Info  : "+carInfo3);System.out.println("Basic Car Price : "+price3);}} |

# Bridge Pattern

* * *

Bridge is used when we need to decouple an abstraction from its implementation so that the two can vary independently and bridge structure works between them to connect with each other.

As the name suggests,the Bridge design pattern  provides an easier capability for us to extend two layers separately as these two layers become independent from each other. And the connection point is our bridge, which means our bridge class in our code base.

As you can see below,Banks or the river is isolated and connected through a Bridge ,this is what Bridge design patterns do in software.

![](image_rsrc3MP.jpg)

# Example

| package playwithjava.in.bridge;public interface FillColor {public void fillWithColor();} |

As you can see, we have FillColor and its 2 implementations for Red and Green color.This logic is separated from Shape implementation classes.

Based on object reference ,required color will be applied.

| package playwithjava.in.bridge;public class GreenColor implements FillColor{@Overridepublic void fillWithColor() {System.out.println("#########  Fill With Green Color");}} |

| package playwithjava.in.bridge;public class RedColor  implements FillColor{@Overridepublic void fillWithColor() {System.out.println("#########  Fill With Green Color");}} |

| package playwithjava.in.bridge;public abstract class Shape {protected FillColor fillColor;public Shape(FillColor fillColor) {this.fillColor = fillColor;}abstract void feedColor();} |

| package playwithjava.in.bridge;public class Circle extends Shape{public Circle(FillColor fillColor) {super(fillColor);}@Overridepublic void feedColor() {System.out.println("########  Draw Shape:: Circle");fillColor.fillWithColor();}} |

| package playwithjava.in.bridge;public class Squire extends Shape{public Squire(FillColor fillColor) {super(fillColor);}@Overridepublic void feedColor() {System.out.println("########  Draw Shape:: Circle");fillColor.fillWithColor();}} |

BridgeDemo.java

| package playwithjava.in.bridge;public class BridgeDemo {public static void main(String[] args) {FillColor fillColorGreen=new GreenColor();FillColor fillColorRed=new RedColor();Shape circleGreen=new Circle(fillColorGreen);Shape circleRed=new Circle(fillColorRed);Shape squireGreen=new Squire(fillColorGreen);Shape squireRed=new Squire(fillColorRed);circleGreen.feedColor();circleGreen.feedColor();squireGreen.feedColor();squireRed.feedColor();}} |

Result:

| ########  Draw Shape:: Circle#########  Fill With Green Color########  Draw Shape:: Circle#########  Fill With Green Color########  Draw Shape:: Circle#########  Fill With Green Color########  Draw Shape:: Circle#########  Fill With Green Color |

# Flyweight Pattern

* * *

The Flyweight Design Pattern is a structural pattern in Java that aims to minimize memory usage or computational expenses by sharing as much as possible with related objects.

It used to reduce the number of objects created and to decrease required memory and increase performance.

It helps us to avoid creating objects,in this pattern we used to have a Map where we keep our recently created objects and whenever some expects some objects we used to check whether the same object is already available in Map or not.

If it's already available then we used to get it from Map and return the same instance to call instead of creating new and returning.

| public interface Shape {void draw();} |

| public class Circle implements Shape {private String color;private int x;private int y;private int radius;public Circle(String color){this.color = color;​}public void setX(int x) {this.x = x;}public void setY(int y) {this.y = y;}public void setRadius(int radius) {this.radius = radius;}@Overridepublic void draw() {System.out.println("Circle:Draw [Color : " + color + ", x : " + x + ", y :" + y + ", radius :" + radius);}} |

| public class ShapeCreator {private static final HashMap map = new HashMap();public static Shape getCircle(String color) {Circle circle = (Circle)circleMap.get(color);if(circle == null) {circle = new Circle(color);circleMap.put(color, circle);System.out.println("Creating circle with color : " + color);}return circle;}} |

| public class FlyweightDemo {public static void main(String[] args) {Circle circle = (Circle)ShapeFactory.getCircle(“red”);circle.setX(10);circle.setY(15));circle.setRadius(11);circle.draw();}}} |

# Proxy Design Pattern

* * *

A proxy design pattern allows a proxy class to represent a real “subject” class. It is a structural design pattern. A proxy is something that acts as a simplified, or lightweight version, of the original object. A proxy object can perform the same tasks as an original object but may delegate requests to the original object to achieve them.

In this design pattern, the proxy class wraps the real subject class. This means that a reference to an instance of the real subject class is hidden in the proxy class. The real object is usually a part of the software system that contains sensitive information, or that would be resource-intensive to instantiate. As the proxy class is a wrapper, client classes interact with it instead of the real subject class.

The proxy class is like a helper that wraps around the real class. Sometimes, it helps by doing things itself, but when it needs the heavy lifting done, it asks the real class to do it. Both the helper (proxy) and the real class know how to do the same tasks because they follow the same rules, like a recipe.

We can switch between the helper and the real chef because they both understand the same recipe, making it easy to use either of them when needed. This way, the proxy and the real class can work together smoothly.

Let's assume you want to watch a movie online. Instead of directly accessing the movie file (the RealSubject), you use a streaming service (the Proxy). The streaming service checks if you have the right subscription (access control), maybe adds some subtitles or extra features (additional behavior), and only when you click "play," it fetches the actual movie from the server and enables the view for you.

| // Subject Interfaceinterface Video {void play();} |

# Lets see how we can play the video using a proxy design pattern.

| // RealSubjectclass RealVideo implements Video {private String title;public RealVideo(String title) {this.title = title;loadVideo();}private void loadVideo() {System.out.println("Loading video: " + title);}@Overridepublic void play() {System.out.println("Playing video: " + title);}} |

| // Proxyclass VideoProxy implements Video {private RealVideo realVideo;private String title;public VideoProxy(String title) {this.title = title;}@Overridepublic void play() {if (realVideo == null) {realVideo = new RealVideo(title);}realVideo.play();}} |

Lets see on how client is enabling you to access the Movie file with proxy pattern.

| // Client Codepublic class ProxyPatternExample {public static void main(String[] args) {Video video = new VideoProxy("Awesome Movie");// The real video is loaded and played only when 'play' is called on the proxyvideo.play();}} |

Behavioral Design Pattern

* * *

This module will describe certain behavioral design patterns. These are patterns that focus on ways that individual objects collaborate to achieve a common goal. This is an important aspect to consider in software design – objects are only pieces of a larger solution. For each to work effectively, it must have a set purpose. Let us examine some behavioral design patterns.

Behavioral design patterns in Java are patterns that focus on defining how objects interact and communicate with each other. They are concerned with the assignment of responsibilities between objects and encapsulating behavior in a flexible and reusable manner.

The behavioral pattern makes it essential to keep things loosely coupled with minimum hard coding and more coherence.

Behavioral patterns are like templates that identify how objects usually talk to each other and keep a record of these interactions. They also handle how tasks and responsibilities are shared among different objects.

So, imagine these patterns as guides for how objects should communicate and work together. They help in organizing the tasks and deciding who should do what in a way that makes the objects easy to work with and not too dependent on each other.

In simpler terms, behavioral patterns help objects talk to each other in a flexible and easy way. It's like having a set of rules that make sure everyone knows how to cooperate without getting too tangled up with each other. This makes the whole system more adaptable and less complicated.

# A behavioral pattern is a group of twelve design patterns, as below.

●         Chain of Responsibility

●         Command Pattern

●         Interpreter Pattern

●         Iterator Pattern

●         Mediator Pattern

●         Memento Pattern

●         Observer Pattern

●         State Pattern

●         Strategy Pattern

●         Template Pattern

●         Visitor Pattern

●         Null object Pattern.

* * *

# Template Method Pattern

The template method pattern defines an algorithm’s steps generally, by deferring the implementation of some steps to subclasses. In other words, it is concerned with the assignment of responsibilities.

Think of the template method as a handy tool when you have two classes that do almost the same things but with some differences. It's like having a magic trick to make changes in just one spot instead of two. So, instead of repeating yourself in both classes, you create a special set of instructions in a main class (the superclass) that both of them can follow.

This special set of instructions is the template method, and it's like a blueprint for how things should be done. The cool part is that the tricky parts, where the classes are a bit different, can be left blank. These blank parts are like questions that the subclasses (the specific classes) answer with their own unique details.

By doing this, you're making sure that when you change something, you only have to do it in one place, making everything simpler and less confusing. It's like having a master plan that helps you reuse things more easily. This way of organizing stuff is called inheritance, and it's like sharing the cool tricks between different classes, making your code more understandable.

Both dishes require that you boil water, cook the pasta, add the sauce, add the protein, and garnish the plate. Some of these steps have different implementations depending on which dish is being prepared – each dish has a different sauce, protein, and garnish. Other steps, however, would be the same, such as boiling the water.

This situation could be modeled with a PastaDish class that has a method that makes the recipe for each subclass, spaghetti with meatballs or penne alfredo. The method knows the general set of steps to make either dish - from boiling water to adding the garnish. Steps that are special to a dish, like the sauce to add, are implemented in the subclass. The UML diagram below illustrates this example.

* * *

Let's consider some other example:

![](image_rsrc3MR.jpg)

As you can see in the above class diagram,We have superclass Noodles with set of required common methods.suppose you went to some restaurant and order for Noodles, it may be simple Noodles, ChickenNoodles OR PaneerNoodles.

In Noodles class we have kept all the common methods that are required for any kind of noodles to be served.As we know we need to add chicken for ChickenNoodle and paneer to PaneerNoodles().

Now lets see how Template design pattern is helping to simplify the logic, As we have to prepare Noodles that may be simple Noodles,ChickenNoodles and PaneerNoodles. We have a template method prepareNoodles() , this method will call all the required methods in-order to prepare chicken.

As you can see , we have a method addProtein() in template method , we can add Chicken OR Paneer as required.

If it's ChickenNoodle we can add Chicken or we can add paneer for PaneerNoodle.

* * *

|  
package playwithjava.in.template;

public abstract class Noodles {public final void prepareNoodle(){boilWater();boilNoodles();addSalt();addMasala();addProtien();doFry();putInPlate();}public abstract void boilWater();public abstract void boilNoodles();public abstract void addSalt();public abstract void addMasala();public abstract void addProtien();public abstract void doFry();public abstract void putInPlate();} |

| package playwithjava.in.template;public class ChickenNoodles extends Noodles{@Overridepublic void boilWater() {System.out.println("## boil water");}@Overridepublic void boilNoodles() {System.out.println("## boil Noodles"); 
}

@Overridepublic void addSalt() {System.out.println("## Add salt");}@Overridepublic void addMasala() {System.out.println("## Add Chicken Masala");}@Overridepublic void addProtien() {System.out.println("## Add Chicken");}@Overridepublic void doFry() {System.out.println("## Fry for 5 minutes");}@Overridepublic void putInPlate() {System.out.println("## put in white plate");}} |

|  
package playwithjava.in.template;

public class PaneerNoodles extends Noodles{@Overridepublic void boilWater() {System.out.println("## boil water");}@Overridepublic void boilNoodles() {System.out.println("## boil Noodles");}@Overridepublic void addSalt() {System.out.println("## Add salt");}@Overridepublic void addMasala() {System.out.println("## Add Paneer Masala");}@Overridepublic void addProtien() {System.out.println("## Add Paneer");}@Overridepublic void doFry() {System.out.println("## Fry for 3 minutes");}@Override

public void putInPlate() {

System.out.println("## put in green plate");}} |

| package playwithjava.in.template;public class TemplateDemo {public static void main(String[] args) {Noodles chickenNoodles=new ChickenNoodles();Noodles pannerNoodles=new PaneerNoodles();System.out.println("#### Chicken Noodles ####");chickenNoodles.prepareNoodle();System.out.println("#### Panner Noodles ####");pannerNoodles.prepareNoodle();}} |

# Result

| #### Chicken Noodles ###### boil water## boil Noodles## Add salt## Add Chicken Masala## Add Chicken## Fry for 5 minutes## put in white plate#### Panner Noodles ###### boil water## boil Noodles## Add salt## Add Paneer Masala## Add Paneer## Fry for 3 minutes## put in green plate |

# Chain of Responsibility Pattern

* * *

The chain of responsibility design pattern is a chain of objects that are responsible for handling requests. In software design, these objects are handler objects that are linked together.

When a client object sends a request, the first handler in the chain will try to process it. If the handler can process the request, then the request ends with this handler. However, if the handler cannot handle the request, then the request is sent

to the next handler in the chain. This process will continue until a handler can process the request.

![](image_rsrc3MS.jpg)

If the entire chain is unable to handle the request, then the request is not satisfied.

The chain of responsibility is an important pattern in software. This pattern avoids coupling the sender to the receiver by giving more than one object a chance to handle the request. Whoever sends the request does not need to worry about who will handle the request, so the sender and the receiver are decoupled from each other.

The chain of responsibility also helps deal with situations in which streams of different requests need to be handled.

Each filter needs to go through the following steps:

1.     Check if the rule matches.

2.     If it matches,perform some specific operation.

3. If it doesn’t match, call the next method/job/task in the list.

You can take Exception handling as a chain of responsibility.

| // Handler interfaceinterface Handler {void handleRequest(Request request);} |

| // Concrete Handler 1class ConcreteHandler1 implements Handler {private Handler nextHandler;public void setNextHandler(Handler nextHandler) {this.nextHandler = nextHandler;}@Overridepublic void handleRequest(Request request) {if (request.getType().equals(RequestType.TYPE1)) {System.out.println("ConcreteHandler1 handling request of type TYPE1");} else if (nextHandler != null) {nextHandler.handleRequest(request);} else {System.out.println("End of the chain. Request not handled.");}}} |

| // Concrete Handler 2class ConcreteHandler2 implements Handler {private Handler nextHandler;public void setNextHandler(Handler nextHandler) {this.nextHandler = nextHandler;}@Overridepublic void handleRequest(Request request) {if (request.getType().equals(RequestType.TYPE2)) {System.out.println("ConcreteHandler2 handling request of type TYPE2");} else if (nextHandler != null) {nextHandler.handleRequest(request);} else {System.out.println("End of the chain. Request not handled.");}}} |

| // Request classclass Request {private RequestType type;public Request(RequestType type) {this.type = type;}public RequestType getType() {return type;}} |

| // Enum representing different request typesenum RequestType {TYPE1, TYPE2} |

| // Client codepublic class ChainOfResponsibilityExample {public static void main(String[] args) {// Creating handlersHandler handler1 = new ConcreteHandler1();Handler handler2 = new ConcreteHandler2();// Linking handlers in a chainhandler1.setNextHandler(handler2);// Making requestsRequest request1 = new Request(RequestType.TYPE1);Request request2 = new Request(RequestType.TYPE2);Request request3 = new Request(RequestType.TYPE3);  // Unsupported type// Handling requestshandler1.handleRequest(request1);handler1.handleRequest(request2);handler1.handleRequest(request3);}} |

# State Pattern

* * *

The State Design Pattern is a behavioral design pattern in Java that allows an object to alter its behavior when its internal state changes. The pattern represents states as separate classes and delegates the state-specific behavior to these classes

Objects in your code are aware of their current state. They can choose an appropriate behavior based on their current state. When their current state changes, this behavior can be altered - this is what the state design pattern does.

This pattern should be primarily used when you need to change the behavior of an object based upon changes to its internal state or the state it is in at run-time. This pattern can also be used to simplify methods with long conditionals that depend on the object’s state.

# Participants:

Context:

●         Represents the object whose behavior changes based on its internal state.

●         Maintains a reference to the current state.

●         Provides methods that delegate the state-specific behavior to the current state.

State:

●         Defines an interface or abstract class for encapsulating the behavior associated with a particular state of the context.

●         Declares methods representing the actions that can be performed in that state.

Concrete States:

●         Implement the State interface.

●         Provide concrete implementations for the methods declared in the State interface.

●         Each concrete state represents a specific behavior associated with the context when it is in that state.

* * *

# Key Concepts:

Encapsulation of State:

● The State Design Pattern encapsulates the behavior associated with each state in separate classes. This encapsulation makes it easy to add new states without modifying existing code.

Dynamic State Changes:

● The context can change its state dynamically during runtime. This allows the object to adapt its behavior based on changes in its internal state.

Delegated Behavior:

● The context delegates the execution of state-specific behavior to the current state object. This delegation is typically done through an interface or abstract class that defines the common methods for all states.

Flexibility and Extensibility:

● Adding new states or modifying existing ones doesn't require changes to the context class. This promotes flexibility and extensibility, making it easy to introduce new behaviors without affecting other parts of the system.

* * *

# Example Scenario:

Consider a simple vending machine as an example. The vending machine has different states such as "No Coin Inserted," "Coin Inserted," and "Product Selected." Each state has its own behavior:

●         In the "No Coin Inserted" state, inserting a coin transitions the machine to the "Coin Inserted" state.

● In the "Coin Inserted" state, selecting a product transitions the machine to the "Product Selected" state, and so on.

Let's illustrate the State Design Pattern with a real-world example: a traffic light system. In this scenario, a traffic light can be in three states: "Red," "Yellow," and "Green." The behavior of the traffic light changes based on its current state.

| // State interfaceinterface TrafficLightState {void displayState();} |

| // Concrete State: RedLightStateclass RedLightState implements TrafficLightState {@Overridepublic void displayState() {System.out.println("Traffic Light is RED. Stop!");}}// Concrete State: YellowLightStateclass YellowLightState implements TrafficLightState {@Overridepublic void displayState() {System.out.println("Traffic Light is YELLOW. Prepare to stop or go!");}}// Concrete State: GreenLightStateclass GreenLightState implements TrafficLightState {@Overridepublic void displayState() {System.out.println("Traffic Light is GREEN. Go!");}} |

| // Context class: TrafficLightclass TrafficLight {private TrafficLightState currentState;public TrafficLight() {// Initial statecurrentState = new RedLightState();}public void changeState(TrafficLightState newState) {currentState = newState;}public void displayState() {currentState.displayState();}} |

| // Client codepublic class TrafficLightExample {public static void main(String[] args) {TrafficLight trafficLight = new TrafficLight();// Initial state: RedtrafficLight.displayState();// Transition to YellowtrafficLight.changeState(new YellowLightState());trafficLight.displayState();// Transition to GreentrafficLight.changeState(new GreenLightState());trafficLight.displayState();}} |

| The State Design Pattern is commonly used in scenarios where an object's behavior is highly dependent on its internal state, and that state can change dynamically. Systems involving workflows, user interfaces, and various modes of operation can benefit from this pattern.By encapsulating state-specific behavior in separate classes, the pattern provides a clear and organized way to manage complex state transitions in a system. It also aligns well with the Open-Closed Principle, making it easier to extend the system with new states without modifying existing code. |

# Command Pattern

* * *

The Command Design Pattern is a behavioral design pattern that turns a request into a stand-alone object. This object contains all the information about the request, allowing for parameterization of clients with different requests, queuing of requests, and logging of the requests.

Participants:

Command:

●         Declares an interface for executing a particular operation.

ConcreteCommand:

●         Defines a binding between a Command object and an action.

●         Implements the execute method by invoking the corresponding operation on the Receiver.

Invoker:

●         Asks the command to execute the request.

●         Does not know how the request is carried out, only knows how to initiate the command.

Receiver:

●         Knows how to perform the operation associated with the request.

Client:

●         Creates a ConcreteCommand and sets its receiver.

The command pattern encapsulates a request as an object of its own. In general, when an object makes a request for a second object to do an action, the first object would call a method of the second object and the second object would complete the task. There is direct communication between the sender and receiver object.

![](image_rsrc3MT.jpg)

The command pattern creates a command object between the sender and receiver. This way, the sender does not have to know about the receiver and the methods to call.

![](image_rsrc3MU.jpg)

In a command pattern, a sender object can create a command object. However, an invoker is required to make the command object do what it’s supposed to do and get the specific receiver object to complete the task. An invoker is therefore an object that invokes the command objects to complete whatever task it is supposed to do. A command manager can also be used that basically keeps track of the commands, manipulates them, and invokes them.

* * *

Example Implementation:

Let's consider a simple example of a remote control system where we want to control various electronic devices using the Command Design Pattern.

# Define the Command Interface:

| // Command interfaceinterface Command {void execute();} |

| // ConcreteCommand for turning on the lightclass LightOnCommand implements Command {private Light light;public LightOnCommand(Light light) {this.light = light;}@Overridepublic void execute() {light.turnOn();}}// ConcreteCommand for turning off the lightclass LightOffCommand implements Command {private Light light;public LightOffCommand(Light light) {this.light = light;}@Overridepublic void execute() {light.turnOff();}} |

| // Receiver: The Lightclass Light {public void turnOn() {System.out.println("Light is ON");}public void turnOff() {System.out.println("Light is OFF");}} |

| // Invoker: The Remote Controlclass RemoteControl {private Command command;public void setCommand(Command command) {this.command = command;}public void pressButton() {command.execute();}} |

| // Client codepublic class CommandPatternExample {public static void main(String[] args) {// Create instances of the Receiver and ConcreteCommandLight light = new Light();Command lightOn = new LightOnCommand(light);Command lightOff = new LightOffCommand(light);// Create an instance of the InvokerRemoteControl remote = new RemoteControl();// Set the ConcreteCommand for turning on the light and press the buttonremote.setCommand(lightOn);remote.pressButton();// Set the ConcreteCommand for turning off the light and press the buttonremote.setCommand(lightOff);remote.pressButton();}} |

In this example, the RemoteControl acts as the invoker, and the LightOnCommand and LightOffCommand are concrete commands. The Light class is the receiver. This setup allows for flexibility in adding new commands without modifying the invoker, promoting the Open-Closed Principle.

# Benefits:

Decouples Sender and Receiver:

● The Command Design Pattern decouples the sender (client) from the receiver (receiver of the request), allowing for greater flexibility.

Undo/Redo Operations:

● Commands can be easily stored for undo/redo operations, as each command object contains all the information needed to reverse the operation.

Supports Queues and Logging:

●         Commands can be queued and logged, allowing for additional functionality such as transaction management.

# Real-world Applicability:

The Command Design Pattern is commonly used in applications where it is necessary to parameterize objects with operations, queue requests, or log requests. It's especially useful in scenarios where the system needs to support undo operations or where the behavior of objects needs to be customizable at runtime.

* * *

# Observer Pattern

* * *

The observer design pattern is like having a leader (we call it the "subject") who keeps a list of followers (we call them "observers"). The observers depend on the subject to tell them if something important changes.

In this pattern, we usually have a special leader class called "Subject." This leader has a list where it keeps track of all its followers, the observers. There is also a rulebook, kind of like a set of instructions, called the "Observer" interface. This rulebook has a special method that helps the followers know when there's a change in the leader's state. The leader, in turn, might have some team members who follow these rules (implement the Observer interface). This creates a connection between the leader and its team.

So, think of it like a group of friends. You have a leader who knows everyone, and there's a set of rules to follow. When something important happens, the leader tells the friends, and they can react based on the rules they know. It's a way for the leader and the friends to stay connected and updated on what's going on.

The Observer Design Pattern is used when one object, called the subject, wants to notify a group of dependent objects, called observers, about a change in its state. The observers are then updated automatically by the subject when the state changes.

# Participants:

Subject:

●         Maintains a list of observers and provides methods to add, remove, and notify observers.

●         In Java, this can be an interface or an abstract class.

ConcreteSubject:

●         Extends or implements the Subject.

●         Keeps track of its observers and notifies them of any state changes.

Observer:

● Defines an interface or an abstract class with a method (e.g., update) that the subject calls to notify observers.

ConcreteObserver:

●         Implements the Observer interface.

●         Registers itself with the subject to receive notifications.

●         Defines the specific behavior to execute when notified.

# Example Implementation:

Let's create a simple example where a weather station is the subject, and different displays are observers that want to be notified about changes in the weather.

| // Observer interfacepublic interface Observer {void update(String weather);} |

| // Subject interfacepublic interface Subject {void registerObserver(Observer observer);void removeObserver(Observer observer);void notifyObservers();} |

| // Concrete Observer: WeatherDisplaypublic class WeatherDisplay implements Observer {private String currentWeather;@Overridepublic void update(String weather) {this.currentWeather = weather;display();}public void display() {System.out.println("Weather Display: Current Weather is " + currentWeather);}} |

| // Concrete Subject: WeatherStationimport java.util.ArrayList;import java.util.List;public class WeatherStation implements Subject {private List<Observer> observers = new ArrayList<>();private String currentWeather;@Overridepublic void registerObserver(Observer observer) {observers.add(observer);}@Overridepublic void removeObserver(Observer observer) {observers.remove(observer);}@Overridepublic void notifyObservers() {for (Observer observer : observers) {observer.update(currentWeather);}}// Simulate weather changespublic void setWeather(String weather) {this.currentWeather = weather;notifyObservers();}} |

| // Client codepublic class ObserverPatternExample {public static void main(String[] args) {// Create the subjectWeatherStation weatherStation = new WeatherStation();// Create observersObserver display1 = new WeatherDisplay();Observer display2 = new WeatherDisplay();// Register observers with the subjectweatherStation.registerObserver(display1);weatherStation.registerObserver(display2);// Simulate weather changesweatherStation.setWeather("Sunny");weatherStation.setWeather("Rainy");}} |

In this example, the WeatherStation is the subject, and WeatherDisplay is an observer. The update method in WeatherDisplay is called when the weather changes, and it displays the current weather.

# Benefits:

Decoupling:

●         The Observer Pattern promotes a loose coupling between the subject and observers, allowing them to vary independently.

Flexibility:

●         It allows adding or removing observers without modifying the subject.

Reusability:

●         Observers can be reused with different subjects.

# Real-world Applicability:

The Observer Pattern is commonly used in scenarios where an object's state changes, and other objects need to react to these changes, such as in GUI systems, event handling, and distributed systems. It provides an efficient way to achieve communication between objects without making them tightly coupled.

* * *

# MVC Design Pattern

* * *

The Model-View-Controller (MVC) design pattern is a software architectural pattern widely used in developing user interfaces. It divides an application into three interconnected components to separate concerns and enhance modularity.

Model, View, Controller (MVC) pattern is a pattern that should be considered for use with user interfaces. MVC patterns divide the responsibilities of a system that offers a user interface into three parts: model, view, and controller.

Below is a diagram of a simple MVC pattern.

![](image_rsrc3MV.jpg)

The Model is going to contain the underlying data, state, and logic that users want to see and manipulate through an interface. It is the “back end”, or the underlying software. A key aspect of the MVC pattern is that the model is self-contained. It has all of the state, methods, and other data needed to exist on its own. The View gives users the way to see the model in the way they expect and allows them to interact with it or at least parts of it. It is the “front end” or the presentation layer of the software. A model could have several views that present.

So, in simpler terms, the Model keeps the data, the View shows it, and the Controller manages user input and updates.

Now, let's talk about an important part of this system: the Observer pattern. It's like a notification system. Imagine you have a friend who tells you about every cool thing they see - that friend is like an observer. In our program, the View is an observer of the Model. If something changes in the Model (like a new item being added to the order), the View gets notified and updates what it shows to the user.

In Java, to make the Model observable, you can use a package called java.util. This package has a class called Observable that you can extend. So, in our grocery store example, the StoreOrder class (which represents the order in the store) can extend Observable. This allows views to be added as observers, so they know when the order changes and can update accordingly.

This way, everyone (Model, View, and Controller) does their specific job, and they work together smoothly to make sure the user sees the right information and can interact with it.

# Components:

Model:

●         Represents the application's data and business logic.

●         Responds to requests for information, updates its state, and notifies registered observers (usually views) about changes.

●         In Java, models are often represented by classes and may implement interfaces like Observer to notify observers.

View:

●         Displays the data to the user and handles user input.

●         Observes the model and updates itself when the model changes.

●         In Java, views are often implemented using classes, such as graphical user interface (GUI) components.

Controller:

●         Handles user input and updates the model accordingly.

● Acts as an intermediary between the model and view, ensuring that changes in one do not directly affect the other.

●         In Java, controllers can be classes or components responsible for handling user interactions.

* * *

# Benefits:

Separation of Concerns:

● MVC separates data management, user interface, and user input handling, making the application more modular and easier to maintain.

Reusability:

●         Models, views, and controllers can be reused in different contexts or combined with other components.

Testability:

●         Each component can be tested independently, facilitating unit testing.

Real-world Applicability:

MVC is widely used in developing graphical user interfaces, web applications, and other systems where user interaction and data presentation are crucial. It provides a structured and organized way to design applications, promoting maintainability and scalability.

* * *

# Object-oriented design

* * *

Object-oriented modeling is like breaking down big ideas into smaller, manageable parts, thinking of them like building blocks or puzzle pieces. You know how when you play with toys or solve a puzzle, each piece has its own role? That's a bit like objects in object-oriented thinking.

Even though we often connect "object-oriented" with coding, it's more like a way of thinking. Imagine you have a tweet on Twitter or a product on an online store – those can be like special objects. Object-oriented thinking means looking at big ideas and seeing them as these special objects.

When we do object-oriented modeling, it's like turning these ideas into objects in our computer programs. Think of everyday things – like people, places, or things – as if they were special objects in our software.

Now, each of these objects has its own unique details that matter. For example, a person object could have details like a name, age, gender, and job. A place object might have a size or a name. Even a thing, like an object on your desk, might have specific features, like its dimensions or color. It's a bit like giving each object its own special characteristics that make sense for what it is.

Objects in your computer program can also do things or have jobs they are supposed to do. For instance, a person might know how to sit down or type. And think about electronic devices like a computer – they have jobs too, like turning on or off, or showing pictures.

Now, when we use objects to show things in our code, it's like keeping everything tidy, flexible, and ready to use again. It's a bit like having specific tools for specific jobs – it helps us keep our code neat and do things more easily.

Objects in code are like little containers that hold all the important details and specific jobs in one neat place. Imagine each object is a box, and inside that box, you keep everything related to it.

These objects make code flexible, so you can easily change things inside the box without messing up the rest of the code. Let's say you have a person object – if the job or details of that person change, it won't cause chaos in the rest of the code.

Using objects also helps in reusing code. It's like having a set of tools that you can use again and again, making programs simple and not too complicated.

And here's a cool thing: even objects that don't move, like a chair or a mobile phone, know things about themselves. In software, a mobile phone "knows" its specifications, and in object-oriented modeling, a chair would "know" its dimensions and where it is.

So, in this way of thinking, everything is like a special object, even if it's not alive. And these objects, whether they're a person or a chair, are kind of like having a good memory – they know about themselves.

When we make computer programs, we follow a step-by-step process. Imagine it like making a plan to solve a problem with the help of software. This plan isn't a one-time thing; it's like a loop that repeats.

Here's how it works: first, we understand the problem we want to solve. Then, we come up with ideas and drawings (like sketches) to show what our solution might look like. After that, we make detailed plans (kind of like maps) that tell us exactly how to build the solution using the computer.

Now comes the exciting part – we start building the actual software based on our plans. But wait, we're not done yet! We need to test the software to make sure it works like we want it to.

This whole process happens over and over for each part of the problem we're solving. It's like putting together a puzzle – step by step, until we have a complete and working solution.

Skipping any of these steps, especially understanding the problem and planning, can cause projects to not work well. Just starting to write code without a clear plan is like building a house without knowing what it should look like – it might not turn out the way we want. So, taking it step by step is the key!

Let's talk about the steps we take when we're getting ready to make software. It's a bit like being an architect – someone who plans out how a building should look and work.

So, first, we think about what the software needs to do. It's like making a list of what each part of the software should be able to do – this is called "requirements." Then, we put on our architect hats and start thinking about how the software will be structured and how it will behave.

By the end of this lesson, we'll see that designing the software is like making a plan for a solution. We don't just pick one way to do things; we might look at different options before deciding the best way.

So, designing is about figuring out how everything will work together. It's like sketching out a blueprint for a house before we start building it. And just like an architect, we might explore different ideas before settling on the final plan.

* * *

# What do you mean by requirements ?

Alright, let's talk about what we need to do before we start making software. First off, we gather something called "requirements." These are like a list of conditions or things that the client or user really wants in the software. It's kind of like understanding what the client dreams of.

But, we don't stop there. Getting requirements means more than just hearing what the client says. We actively ask questions to really dig into what they need. Sometimes, we even bring up things they might not have thought about. This helps us get the whole picture of what we're building before we dive into coding.

Now, here's the interesting part – we not only figure out what the software must do but also talk about any trade-offs the client might have to make. For example, they might decide to give up a fancy feature if it means the program runs faster. It's all about finding the right balance to make everyone happy.

once we have a clear list of what the client wants and the choices they're willing to make, it's like having a blueprint for building a house.

Imagine you're an architect, and the homeowner tells you they want certain rooms in their house. But that's not all – you, being the smart architect, ask more questions. You might ask about the size of the rooms, if there are any rules or limitations (like space constraints or building codes), where the rooms should be placed, or even which direction the house should face.

Just like an architect needs to understand every detail before they start building, we need to get all the info about the software we're making. It's like making sure we know exactly what rooms to build and where to put them in our "digital house" before we start coding. It's all about getting it right from the beginning!

* * *

# Conceptual Design

Once we have the first set of requirements, the next thing we do is create two important things: conceptual design and technical design. It's like drawing two types of pictures to help us understand and plan what the software will be like.

The first picture, called a "conceptual mock-up," is like a rough sketch. It helps us visualize how the software might look and work. It's not detailed yet – just a basic idea.

The second picture is a "technical diagram." This one is more detailed and focuses on how the software will be built. It's like having a map that shows all the technical details, so when we start coding, we know exactly what to do.

So, these pictures or diagrams are like our guides. One helps us see the big picture, and the other gives us detailed instructions for building the software. It's a bit like having a plan before we start creating something amazing!

When we're creating conceptual designs, we start with the first set of requirements. Think of it as the foundation. These designs help us see the main components, how they connect, and what each part is supposed to do in the software. It's like making a rough sketch of the big ideas without getting into too many technical details yet.

Conceptual designs focus on the higher-level concepts of what our final software will be like. They're not super detailed – it's more about understanding the overall structure and responsibilities of each part. We leave the nitty-gritty technical stuff for later when we get into the technical design phase. So, it's like getting the big picture first before diving into the finer details.

Conceptual designs come to life through something called "conceptual mock-ups." These are like visual drawings that give us an initial idea of how we plan to meet the requirements. When we're dealing with software that has user interfaces (like what you see on a screen), these mock-ups often take the form of wireframes.

Now, wireframes are like simple blueprints or basic visual guides for what the product will look like. Imagine it as a rough sketch of a webpage or screen layout. Whether it's hand-drawn sketches or made using computer tools, these mock-ups help us explain and discuss our design decisions with clients and users. They're a simple and clear way to show how the software will work and look. It's like giving everyone a preview before we actually build it!

Mock-ups are like pictures that show the main parts and how they connect in our software. When we create a mock-up, it helps us see if something is missing or if there's a problem with how things might work. If we spot any issues, we talk with the client and might need to do more work on the design.

Each part in our software has a job to do, and we call that its "responsibility." Mock-ups help us understand and show these responsibilities, but they don't get into the nitty-gritty technical stuff. That comes later in the process when we move on to more detailed designs. So, think of mock-ups as the early visual guides that help us get a good grasp of the big ideas before diving into the specifics.

Let's go back to our house-building metaphor. In this case, the main parts, or "components," are the lot where the house will sit, the actual house, and the rooms inside. The connections are like how the rooms are connected and accessible to each other. The house itself has a big responsibility – making sure it has enough power, water, and support for everything inside.

Now, think about the rooms in the house, like the kitchen. Each room also has its own responsibilities, such as providing space for kitchen stuff, appliances, and food supplies, plus having power and water for cooking. But, we're not getting into the specifics like wiring and plumbing in the conceptual design. Those technical details come later when we have a full grasp of the conceptual mock-ups. It's a bit like figuring out the size of the electrical panel for the whole house by adding up the power needs of each room. We start with the big picture before diving into the tiny details.

The smart way to do things is to first create a clear conceptual design before jumping into the technical details. If we have a strong and clear concept of how our software will work, it makes it much easier to create a detailed technical design. This way, there's a higher chance that the software we build will turn out just the way we want it to be. So, it's like having a solid plan in place before we get into the nitty-gritty of building the software.

* * *

# Technical Design

Technical designs take what we figured out in the conceptual design and requirements and dive into the nitty-gritty details of how the solution will actually work. In the conceptual design, we outlined the main parts, connections, and responsibilities of the software we're creating. Now, the technical design takes this info to the next level – it explains exactly how we're going to meet these responsibilities.

The technical design isn't complete until we've worked on each component enough to get into the specific details. It's like getting into the fine-tuning phase, making sure every part of our software is designed in enough detail to bring our plan to life. So, think of conceptual design as the big picture, and technical design as the detailed roadmap for building our software.

To make technical designs, we start by breaking down the main components into smaller and more specific parts. We keep breaking them down until we reach a level where we can design each part in great detail. It's like zooming in, breaking things into smaller pieces with very specific responsibilities.

By doing this, we end up with each component having its own set of detailed technical specifications. This process allows us to focus on the nitty-gritty of each part, making sure we've covered all the technical details. So, think of it as going from the big picture to detailed specifics, ensuring that every part of our software has its technical details well-defined.

To convey the technical design, we use technical diagrams. These diagrams show how to tackle specific issues for each component because conceptual mock-ups usually don't get into such detailed information. There are various types of technical diagrams that describe the structure and behavior of components, and we'll delve into them later in this specialization. Technical diagrams play a crucial role in coordinating development work.

Let's stick with our example of designing a kitchen in a house. The kitchen, as a component, needs smaller parts like flooring. The technical design might specify that the flooring should be made of an easy-to-clean material, especially if the client plans on doing a lot of cooking – which can get a bit messy! It's like having detailed plans to make sure every part of the kitchen is just right.

* * *

# Compromise in Requirements and Design

During the design phase, finding the right solution might involve making compromises. Constant communication and feedback are crucial to creating a solution that not only meets the client's needs but also fits within any constraints.

For instance, consider a client who wants an open kitchen with no obstructions, but structural support is needed in that area. A compromise would be necessary to address this situation.

If components, connections, and responsibilities outlined in the conceptual design prove unachievable in the technical design or fail to meet requirements, designs will need adjustments. Regular checks with clients ensure that conceptual mock-ups align with their desires. It's much easier to redesign in the planning stages than once coding has started.

Larger systems require more design time due to the complexity of managing numerous components, connections, and responsibilities. These large components might need to be broken down into smaller ones before detailed design can occur.

Once a feasible design is agreed upon, technical diagrams serve as the foundation for constructing the intended solution. Components at this stage may be refined into collections of functions, classes, or other components, making it more manageable for developers to implement.

Various design techniques exist to enhance the design process, and the rest of this specialization will explore these techniques.

* * *

# Design for Quality Attributes

When creating software, it's crucial to consider a holistic approach to achieve the desired requirements. This lesson explores the need to balance competing ideals, roles, perspectives, potential trade-offs, and project realities in software design. In simpler terms, it's about finding the right balance and making smart decisions when developing software to meet the project's goals.

# Trade offs

This course has emphasized the significance of requirements and design in software creation. Occasionally, design faces constraints that necessitate compromise. In addition to functionality-based software requirements, there are quality attributes that specify how effectively this functionality should operate. However, decisions may entail trade-offs in various quality attributes, such as performance, convenience, and security, and it's essential to strike a balance between these attributes.

For instance, it's crucial to assess how quality attributes may conflict in a proposed solution across various scenarios. By considering this and comparing it to the product requirements, an appropriate compromise can be identified. This juggling act is a continuous challenge in software architecture. Software architects must constantly find the optimal balance between quality attributes, often by determining which one holds more significance. Project deadlines also play a role in defining what is feasible within a given timeframe.

To illustrate, think about designing a front door for a house. Security is a crucial quality attribute, but if you add too many locks, the door might become challenging to open easily, sacrificing convenience and performance. A well-thought design should strike a balance between security, convenience, and performance.

Context plays a crucial role in deciding the balance of qualities in design. For instance, software storing public-accessible personal information may have different security requirements than software exclusively used by corporate employees. To establish context, engaging with stakeholders is essential.

Software design also needs to factor in consequences. Choices made in software design can lead to unintended outcomes. For instance, an idea effective for a small amount of data might become impractical for large datasets.

A good practice is to seek diverse perspectives on technical designs for a well-rounded implementation. This can involve getting opinions from other developers or organizing design review sessions. Thoroughly testing a system before full implementation is also wise. During the design phase, prototyping alternative ideas and running tests can help identify what works best and uncover unintended consequences. For instance, testing with both small and large datasets in the previous example could reveal system limitations.

* * *

# Quality

Qualities are attained by meeting both functional and non-functional requirements, serving as the foundation for the design process.

Functional requirements articulate what the system or application should accomplish. Achieving correctness is a crucial quality when satisfying a functional requirement. For instance, in the design of a music app, it must accurately download and play a song. The design should outline a solution that effectively fulfills this requirement.

Non-functional requirements detail how effectively the system or application performs its tasks. These requirements encompass aspects such as performance, resource utilization, and efficiency, measurable within the running software. For instance, the music app may have non-functional requirements specifying a maximum memory limit for downloading music. Additionally, software commonly addresses qualities like reusability, flexibility, and maintainability through non-functional requirements, indicating how well the code can adapt to changes and facilitate future modifications.

Requirements are typically incomplete initially and evolve through ongoing interactions with clients and end users.

Satisfying both functional and non-functional requirements is crucial, but constraints and limitations may necessitate compromises. Effective communication with stakeholders is essential to determine acceptable trade-offs. Consider the analogy of cars meeting the functional requirement of transportation, but differing in non-functional aspects like acceleration, handling, weight, and fuel economy, distinguishing between a minivan and a sports car.

Reviews and tests play a vital role in verifying that the required qualities in design and software implementation are met. End user feedback can also validate certain qualities.

* * *

# Compromise

When designing software, it's crucial to consider various perspectives and balance qualities that matter to both users and developers. The organization of software structure can impact user-perceived performance, reusability, and maintainability for developers.

# Several common trade-offs in software design include:

Performance and Maintainability: Highly performant code may sacrifice clarity and modularity, making it challenging to maintain. Additional code for backward compatibility can affect both performance and maintainability.

Performance and Security: Enhanced security measures might introduce extra overhead, potentially impacting performance.

Understanding and prioritizing these qualities is key, and designers must ask whether compromises can be made to balance one quality against another. Finding the right balance ensures that the software meets both user expectations and developer requirements.

* * *

# CRC Card

In summary, this module has covered the early stages of software development, focusing on requirements elicitation and conceptual design. During this phase, components, connections, and responsibilities for fulfilling requirements are established.

The module has also delved into the subsequent technical design process, refining components and connections while considering quality attributes to determine technical details. This refinement facilitates the implementation of components and connections.

The upcoming lesson introduces a valuable technique for articulating the conceptual design—Class, Responsibility, Collaborator (CRC) cards. CRC cards are instrumental in documenting and structuring components into classes, defining component responsibilities, and outlining how they collaborate. They play a crucial role in refining the components within your software design.

In the conceptual design phase, it's beneficial not just to identify components, responsibilities, and connections but also to visually represent them. One effective technique for this purpose is using Class, Responsibility, Collaborator (CRC) cards.

CRC cards serve as a tool to document, organize, and refine system design components. They can be likened to note cards, helping to structure talking points. CRC cards typically have three sections: the class name positioned at the top, the responsibilities of the class on the left side, and the collaborators on the right side. Imagine a physical index card, and that's about the size of a CRC card. See the example image below for a visual representation of what a CRC card might look like.

To effectively document each potential component and its associated responsibilities using a CRC card, you write the component's name in the class name section, outline its responsibilities in the responsibilities section, and depict connections in the collaborators section. Collaborators signify other classes with which the class at the top of the card interacts to fulfill its responsibilities. This process is repeated iteratively, creating new cards until all the classes, responsibilities, and collaborators are identified for a system.

In system design, CRC cards serve a crucial purpose—they compel designers to consistently break down components into smaller, more manageable classes that can be individually described on a card.

CRC cards offer a straightforward yet advantageous system. They are cost-effective, editable, and widely accessible, aiding in the organization of information into manageable pieces.

One key benefit of CRC cards is their capacity to facilitate physical reorganization of your design. Representing each component with a card allows you to rearrange related cards or position them to imply relationships. This enables you to explore the theoretical functioning of your system and identify any shortcomings in the design.

Furthermore, you can experiment with rearranging these cards in different orders and analyze the resulting consequences. This versatility allows you to prototype and simulate a system during the conceptual design phase.

When developing designs, these are sometimes referred to as CRC models. CRC cards should be organized by placing closely collaborating components together. This makes it easier to understand the relationships or connections between classes or components.

CRC cards are excellent tools to bring to software development team meetings. All the cards can be placed on the table, facilitating a discussion or a simulation with the team of how these classes work together with other classes to achieve their responsibilities. This allows you to visually explain your system and gain potential input from other parties.

CRC cards are useful tools, but they are most powerful when used for prototyping and simulation for conceptual design. Many other techniques have been developed to help you design more effectively. The rest of this specialization will focus on some of these various design techniques.

* * *

# Object Modeling in OOAD

The previous module in this course provided an introduction to the importance of design in the software development process, and ended with explaining the advantage of using CRC cards to complete a conceptual design.

This module will explore object-oriented modeling even further. It will begin by examining modeling problems and how programming languages evolved towards object orientation. Then, the four major design principles of abstraction, encapsulation, decomposition, and generalization will be discussed. These principles help in problem-solving and lead to developing software that is flexible, reusable, and maintainable. They are key principles to follow for developing a good design for your software.

This module will also explore how to express design structure in Java code and UML class diagrams using the principles of abstraction, encapsulation, and decomposition.

# Creating Models in Design

It is important when working on a software development project not to jump right into creating code to solve the problem. Instead, making the right product involves understanding the full requirements of your product and using good design.

The design step falls between understanding your requirements and building the product. It iteratively deals with both the problem space and the solution space. The design should also present and describe concepts in a way that users and developers both understand, so they may discuss using common terms.

Design is such an important step in software development, and there have been many approaches developed over time to help make this process easier. For example, some design strategies and programming languages have been created for specific kinds of problems.

One approach to help make the design process easier is the object-oriented approach. This allows for the description of concepts in the problem and solution spaces as objects —objects are a notion that can be understood by both users and developers, because object-oriented thinking applies to many fields. This shared knowledge makes it possible for users and developers to discuss elements of complex problems. Object-oriented programming with object-oriented languages is therefore a popular means for solving complex problems.

A good design does not just jump from a concept within the problem space to dealing with it in the solution space. Object-oriented design is no exception. As reviewed in Module 1, object-oriented design consists of:

Conceptual design uses object-oriented analysis to identify the key objects in the problem and breaks down the problem into manageable pieces.

Technical design uses object-oriented design to further refine the details of the objects, including their attributes and behaviors, so it is clear enough for developers to implement as working software.

# These design activities happen iteratively and continuously.

The goal during software design is to construct and refine “models” of all the objects of the software. Categories of objects involve:

●         Entity objects: Initial focus during the design is placed in the problem space.

●         Control objects: These receive events and coordinate actions as the process moves to the solution space.

●         Boundary objects: These connect outside services to your system as the process moves towards the solution space.

Software models help you understand and organize the design process for the objects. Design principles and guidelines are applied to complex problems to simplify objects in the model, break them down into smaller parts, and look for commonalities that can be handled consistently. Models should be continuously critiqued and evaluated to ensure the original problem is addressed, and qualities such as reusability, flexibility, and maintainability are satisfied. Models also serve as design documentation for your software. In fact, models are often mapped to skeletal source code, particularly for an object-oriented language like Java.

Software models are often expressed in a visual notation called Unified Modeling Language (UML). Object-oriented modeling has different kinds of models or UML diagrams that can be used to focus on different software issues. For example, a structural model might be used to describe what objects do and how they relate. This is analogous to a scale model of a building, which is used in architecture.

Now that you have an understanding of the roles models play in design and the relationship between models and coding languages, the next lesson will turn to reviewing the history of programming languages.

* * *

# Four Design Principles

* * *

As explained in the first lesson of this module, object-oriented programming enables you to create models of how objects are represented in your system. However, to build an object-oriented program, you need to consider the major design principles of such programs. Four of these major principles are: abstraction, encapsulation, decomposition, and generalization.

# Abstraction

Abstraction is one of the four major design principles explored in this lesson. It serves as a fundamental way for humans to manage complexity. Abstraction involves simplifying a concept in the problem domain by breaking it down into a streamlined description that omits unnecessary details and highlights the essentials required for understanding the concept within a specific context.

A good abstraction adheres to the rule of least astonishment. This principle suggests that essential attributes and behaviors should be captured without surprises and should not extend beyond the intended scope. This ensures that irrelevant characteristics are excluded from an abstraction, maintaining clarity and relevance for the concept's purpose.

In programming, constructs like functions, classes, enumerations, and methods embody abstraction. In the context of object-oriented modeling, abstraction is most directly related to the concept of a class. When abstraction is employed to identify the essential details for a certain concept, these details are often defined within a class. Objects created from a class possess the essential characteristics to represent instances of a concept, while also allowing for individual variations. Using the analogy of a cookie cutter shaping gingerbread men, each cut cookie belongs to the class of "gingerbread men," sharing essential features like the head, arms, and legs, even if they are decorated uniquely.

Forming an abstraction requires careful consideration of the context or a specific perspective, as it plays a crucial role in defining the essential characteristics of a concept. Context can alter the fundamental features of a concept, making it necessary to understand the purpose and context before creating an abstraction. For instance, consider the abstract concept of a person, which might seem ambiguous without a specific context or purpose. In a gaming app, the essential characteristics of a person would be framed in the context of a gamer, while in a running exercise app, the context would be that of an athlete. The designer must select the most appropriate abstraction based on the software development context.

Understanding the essential characteristics of an abstraction involves considering basic attributes and basic behaviors or responsibilities. These elements provide a clear understanding of what makes up the core of the abstraction, ensuring that it aligns with the intended purpose and context of the software.

Basic attributes are enduring characteristics that persist over time, and while their values can change, the attributes themselves remain constant. For instance, when considering the abstraction of a lion, an age attribute may be present. Although the specific age value may vary, the lion consistently possesses the attribute of age.

In addition to basic attributes, an abstraction encompasses the fundamental behaviors or responsibilities associated with a concept. Taking the example of a lion, behaviors like hunting, eating, and sleeping are essential responsibilities that the lion abstraction fulfills for its intended purpose of survival and existence. These behaviors contribute to defining the core nature of the abstraction, outlining how it functions and interacts within its context.

An abstraction, as discussed earlier, is intended to capture only the essential attributes and behaviors of a concept. The determination of what is essential is heavily influenced by the context in which the abstraction is applied. Context defines the relevance of specific details. For instance, when examining a lion in the context of hunting, details about the lion's preferred sleeping position become irrelevant. If the context shifts, the appropriate abstraction may also need to change accordingly.

The principle of abstraction offers numerous benefits. It simplifies class designs, making them more focused, concise, and comprehensible to others who may review them. Since abstractions depend heavily on context or perspective, careful consideration of relevance is essential. If the system's purpose or the problem being addressed changes, it becomes crucial to reevaluate abstractions and adjust them accordingly. This adaptability ensures that the abstraction remains effective in representing the essential aspects of the concept within the given context.

* * *

# Encapsulation

Encapsulation, the second major design principle, involves the idea of containing something within a capsule, with specific parts accessible from the outside and others not.

# Three key ideas underlie encapsulation:

Bundling: This involves grouping attribute values (data) and behaviors (functions) that manipulate those values into a self-contained object.

Exposing: Certain data and functions of an object can be made accessible from other objects, typically through an interface.

Restricting: Access to specific data and functions is limited to within the object itself.

"Bundling" naturally occurs when defining a class for a type of object. The principle of abstraction helps determine relevant attributes and behaviors about a concept in a given context. Encapsulation takes this a step further, ensuring that these characteristics are bundled together within the same class.

Encapsulation facilitates the creation of distinct objects from a specific class, each with its own data values for attributes and associated behaviors. This consolidation of data and corresponding code within the same class simplifies programming, enhancing clarity and manageability.

An object's data should exclusively consist of information relevant to that specific object. For instance, a lion object is aware of the prey it hunts, but it doesn't possess knowledge about animals on a different continent because such information is not pertinent. Therefore, a class only encapsulates data that is relevant to its attributes.

Moreover, a class defines behaviors through methods. These methods manipulate the attribute values or data within the object to execute specific behaviors. Some methods can be exposed or made accessible to objects of other classes, creating an interface for other objects to utilize the class.

One of the key ideas behind encapsulation is restricting access to specific data and functions exclusively within an object. This connection naturally ties encapsulation to data integrity and the security of sensitive information.

By limiting access to certain attributes and methods only through designated methods, data cannot be altered directly through variable assignments. This prevents assumptions or dependencies from breaking related to the data within an object.

Additionally, restricting access aids in safeguarding sensitive information, preventing its disclosure even through queries that rely on such sensitive data to generate responses. This reinforces the data integrity and security aspects of encapsulation.

The concept of encapsulation, particularly its support for changeable implementation, is closely associated with the idea of black box thinking. The computations and processes occurring within a class need not be known by any other class as long as they can access the interface. A class functions like a black box—its internal details, such as how attributes are represented or how methods compute results, remain hidden. The internal workings are inconsequential; what matters is the ability to provide inputs and obtain outputs through method calls.

Encapsulation establishes an abstraction barrier through black box thinking, where the internal workings of a class are irrelevant to the external world. This results in an abstraction that simplifies complexity for users of the class.

Moreover, encapsulation enhances reusability through black box thinking. Another class only needs to understand the appropriate method to invoke for a desired behavior, what inputs to provide, and what outputs or effects to anticipate. In essence, encapsulation maintains software modularity and facilitates ease of use. Classes are easy to manage, as their internal behavior is not pertinent to other classes, as long as they can interact through the interface.

* * *

# Decomposition

* * *

Decomposition, the third major design principle, involves breaking down a whole thing into different parts or, conversely, combining separate parts with distinct functionalities to form a complete entity. Decomposition allows problems to be divided into smaller, more manageable pieces, making them easier to comprehend and solve.

When applying the principle of decomposition, the key guideline is to analyze the distinct responsibilities of a whole entity and determine how it can be divided into parts, each with a specific responsibility. These parts, essentially separate objects, can be created from distinct classes in the design. This process aligns with abstraction, as it involves breaking down a whole into objects with essential characteristics.

Every type of part within the whole can be associated with a class, aiding in the organization and encapsulation of the individual parts. Consequently, the class for the entire object establishes connections with the classes corresponding to the constituent part objects.

# Generalization

* * *

Generalization, the final major design principle, is crucial for reducing redundancy in problem-solving and is a principle widely used beyond software development. In coding, algorithmic behaviors are often represented through methods, enabling programmers to generalize a behavior and apply it to various input data. This generality eliminates the need for redundant code throughout a program.

In object-oriented modeling, generalization is a central design principle achieved through classes and inheritance. Generalization involves identifying shared characteristics between two or more classes and consolidating them into another class. This results in two types of classes: a parent class and a child class. Child classes inherit attributes and behaviors from parent classes, with parent classes capturing general ideas applicable in a broader sense.

Multiple child classes can inherit from a single parent class, receiving common attributes and behaviors. While each child class may have additional attributes and behaviors for specialization, the shared characteristics are inherited. In standard terminology, a parent class is termed a superclass, and a child class is referred to as a subclass. Inheritance enables a superclass to provide generalization, allowing its subclasses to be more specialized.

The use of parent classes enhances efficiency, reduces errors, and promotes flexibility, maintainability, and reusability in systems, particularly when employed for multiple child classes. Without parent classes, systems may lack these essential qualities.

Generalization offers numerous advantages to object-oriented modeling. As subclasses inherit attributes and behaviors from superclasses, any modifications to the shared code between subclasses need only be implemented once in the superclass. This means that software changes are easier to apply and maintain. Another benefit is the ease with which subclasses can be added without the need to recreate all common attributes and behaviors, facilitating software expansion. Generalization contributes to the creation of more robust software solutions and promotes the development of reusable code, as the same code blocks can be applied to different classes.

# Design Principles

* * *

It is important to keep modules simple when you are programming. If your design complexity exceeds what developers can mentally handle, then bugs will occur more often. To help control this, there must be a way of evaluating your design complexity.

Design complexity applies to both classes and the methods within them. This lesson will use the term module to refer to program units containing classes and the methods within them.

A system is composed of different modules. If the system has a poor design, modules can only connect to specific others and nothing else. A good design enables any modules to connect together without much difficulty. In simpler terms, in a good design, modules are compatible with each other and can be easily connected and reused.

The metrics commonly used to assess design complexity are coupling and cohesion.

# Coupling

* * *

Coupling emphasizes the complexity between a module and other modules. Coupling can be balanced between two extremes: tight coupling and loose coupling. If a module is overly dependent on other modules, it is "tightly coupled," indicating a poor design. Conversely, if a module easily connects to other modules through well-defined interfaces, it is "loosely coupled," signifying a good design.

To evaluate the coupling of a module, metrics such as degree, ease, and flexibility are considered.

Degree is the number of connections between the module and others. Ideally, the degree should be small for effective coupling. For instance, a module should connect to others through only a few parameters or narrow interfaces. This results in a small degree, indicating loose coupling.

Ease refers to how obvious the connections between the module and others are. Connections should be easy to make without requiring an in-depth understanding of the implementations of other modules. This ease of connection contributes to effective coupling.

Flexibility gauges how interchangeable other modules are for this module. Other modules should be easily replaceable with something better in the future, enhancing flexibility for coupling purposes.

Signs that a system is tightly coupled and has a poor design include:

A module connects to other modules through a great number of parameters or interfaces:

This indicates high dependency and complexity between modules, making it challenging to understand and modify the system.

Corresponding modules to a module are difficult to find:

In a tightly coupled system, modules may lack clear interfaces, making it challenging to identify and locate the modules that interact with a particular module.

A module can only be connected to specific other modules and cannot be interchanged:

This lack of flexibility suggests that the system is rigid, making it difficult to replace or upgrade modules without affecting the entire system.

Cohesion focuses on the internal complexity of a module and reflects the clarity of its responsibilities. It operates between two extremes: high cohesion and low cohesion.

# ●         High Cohesion:

●         A module with high cohesion performs a single task or has a clear, well-defined purpose.

●         In a well-designed system, modules exhibit high cohesion, meaning that each module is focused on a specific responsibility.

# ●         Low Cohesion:

●         A module with low cohesion encapsulates more than one purpose, making it unclear and harder to maintain.

● In a poorly designed system, modules may have low cohesion, leading to confusion about the module's purpose and functionality.

To achieve a good design, it's essential to balance low coupling and high cohesion. Both are crucial for system design. However, in complex systems, the distribution of complexity can be either between modules or within modules. Achieving high cohesion might increase dependency on other modules, potentially raising coupling. Conversely, simplifying connections between modules for low coupling might lead to modules taking on more responsibilities, potentially lowering cohesion. Striking the right balance is key for a well-designed system.

* * *

# Separation of Concerns

The principle of "separation of concerns" is a fundamental concept in software design, closely related to the design principle of decomposition. It emphasizes the need to break down a complex system into distinct, manageable parts or concerns. Each part addresses a specific aspect of the overall system, and by separating these concerns, the design becomes more modular, understandable, and maintainable.

Separation of concerns aims to avoid mixing different responsibilities within a single module or component. Each module should focus on one concern or responsibility, making it easier to develop, test, and modify without affecting other parts of the system. This principle promotes clarity, reduces complexity, and enhances the reusability of individual components.

In essence, decomposition, guided by the separation of concerns, allows designers to divide a large, intricate problem into smaller, more manageable problems, making it easier to address each concern independently. This modular approach is crucial for building scalable, adaptable, and maintainable software systems.

Separation of concerns plays a crucial role in object-oriented modeling and programming. By addressing concerns separately, you create more cohesive classes that adhere to key design principles, including abstraction, encapsulation, decomposition, and generalization.

# Let's delve into how separation of concerns aligns with these design principles:

Abstraction: Abstraction involves simplifying complex concepts in the problem domain. When concerns are separated, each class or module can focus on abstracting a specific concept, making it easier to understand and manage. For instance, if you have a class responsible for handling user authentication, it abstracts the concept of authentication without being burdened by unrelated concerns.

Encapsulation: Encapsulation involves bundling data and behaviors related to a concept into a self-contained unit (class). Separation of concerns allows each class to encapsulate a specific set of related functionalities. This encapsulation makes it easier to manage data and behaviors within each class without interfering with other parts of the system.

Decomposition: Decomposition breaks down a whole system into smaller, manageable parts. Separation of concerns aligns with decomposition by ensuring that different concerns are divided into distinct sections of the software. Each section can be developed, tested, and maintained independently, contributing to a more modular and scalable system.

Generalization: Generalization involves extracting common characteristics from multiple classes to create a more abstract superclass. When concerns are separated, you can identify commonalities and apply generalization where appropriate. This results in reusable, generalized components that contribute to a more flexible and adaptable system.

In summary, separation of concerns is a foundational principle that supports the effective application of other design principles in object-oriented modeling. It leads to well-organized, modular, and maintainable software systems by addressing different concerns independently and promoting a clean separation of responsibilities.

Indeed, separation of concerns is an ongoing and integral aspect of the entire system design process. This concept aligns closely with fundamental design principles, contributing to the creation of a software system that is not only easier to maintain but also more modular and reusable.

* * *

# Here are some key points to highlight

Ease of Maintenance: By adhering to the principle of separation of concerns, each class is organized to contain only the code necessary for its specific responsibilities. This focused organization makes it easier to locate, understand, and modify code within a class. When modifications are needed, developers can work on specific classes without the risk of unintended consequences in other parts of the system.

Modularity: Separation of concerns enhances modularity by isolating different concerns within individual classes. Modularity is a key factor in building scalable and maintainable software. It allows developers to work on and test individual components independently, promoting code reuse and reducing the impact of changes on other parts of the system.

Reuse and Building Blocks: Modular design, facilitated by separation of concerns, enables the reuse of individual classes as building blocks for larger systems. When concerns are well-separated, classes become more like independent entities that can be assembled and combined to create diverse and flexible software solutions. This reusability contributes to efficiency and consistency across different parts of a system.

Boundaries and Design Decisions: Determining the boundaries of each class can be a nuanced process and often involves trade-offs. Designers must carefully consider how to abstract, encapsulate, decompose, and generalize to address the specific concerns of a problem. The effectiveness of the separation of concerns strategy relies on thoughtful design decisions that balance the need for modularity with the broader system requirements.

In summary, separation of concerns is a guiding principle that, when applied effectively, results in a well-organized, maintainable, and modular software system. It encourages developers to think critically about how to structure classes, facilitating a more scalable and adaptable approach to software design.

* * *

# Information Hiding

In a well-designed computer system, things are organized in a way that makes sense. We use certain principles to help with this organization. One important principle is called "information hiding." This means that not every part of a computer program needs to know everything about all the other parts. Each part, or module, should only know what it needs to do its job. We do this to keep things simple and well-organized.

Think of it like this: if you have a special recipe, you don't need to know the details of how every ingredient is grown or processed. You just need to know how to use those ingredients to make your dish. Similarly, computer modules only need to know what's necessary for them to work correctly. We hide unnecessary details from them to keep things neat.

Now, information hiding is often connected with keeping important or sensitive data safe. The more sensitive the information, the less access it should have. In computer programs, we also use information hiding to keep certain details hidden, like how a specific calculation is done or how data is stored. We do this because these details might change, and we want to be able to change them without affecting everything else.

On the other hand, there are things that don't change much, like basic assumptions. These assumptions are not hidden; instead, they are expressed clearly in the rules that different parts of the program follow. We often describe these rules using terms like APIs (Application Programming Interfaces) and interfaces.

So, why do we do all of this? Well, it helps programmers work on different parts of a program separately. They can focus on their specific tasks without needing to know all the nitty-gritty details of what others are doing. It's a bit like chefs working in a kitchen — each chef knows their own recipe and doesn't need to worry about how other chefs are preparing their dishes.

In simple terms, a good rule to follow is this: things that might change, like how something is done, should be hidden. Things that don't change much, like basic rules, should be clearly stated for everyone to see. This way, everyone knows what to expect, and the whole system stays well-organized.

Information hiding is like keeping a secret in computer programming. When we talk about encapsulation, it's like putting that secret in a box and only letting others interact with it through a specific interface. Encapsulation bundles together the important details, like what the box contains and how it works, and provides a clear way for others to use it.

Imagine you have a magical box (an object in programming) that can do cool things. Encapsulation helps us keep the details of how it does those things hidden. We create a set of rules, like an instruction manual, that says how others can interact with the box. This set of rules is the interface. Other parts of the program, like different objects or modules, only need to know what's in the instruction manual.

They don't need to know the magical workings inside the box.

Now, this not only helps in hiding how the magic works but also protects certain important details. For example, if there's a crucial piece inside the box, we don't want anyone messing with it directly. Encapsulation prevents others from changing this important piece without following the proper rules from the instruction manual.

So, information hiding through encapsulation is like having a well-protected secret box in our program. It allows us to change how things work inside the box without affecting how others use it. It's a way of keeping our program organized and making sure everyone plays by the rules!

In Java, access modifiers are keywords that specify the visibility or accessibility of classes, methods, and fields. They control how different parts of your code can interact with each other.

There are four main access modifiers in Java:

Public (public):

●         The class, method, or field declared as public is accessible from any other class.

●         Example: public class MyClass { ... }

Private (private):

●         The class, method, or field declared as private is accessible only within the same class.

●         Example: private int myField;

Protected (protected):

● The class, method, or field declared as protected is accessible within the same class, package, and subclasses (even if they are in a different package).

●         Example: protected void myMethod() { ... }

Default (Package-Private):

● If no modifier is specified, it's called the default or package-private. It is accessible only within the same package.

●         Example: class MyPackageClass { ... }

These access modifiers help in implementing encapsulation and information hiding principles. They control the visibility of your code elements and restrict access to certain parts of your program, ensuring better security and maintainability.

# Conceptual Integrity

* * *

Conceptual integrity is a crucial concept in software development, emphasizing the need for a consistent and cohesive design and implementation of a software system. It ensures that, despite multiple individuals contributing to the project, the end result appears as if guided by a single mind. Achieving conceptual integrity involves adhering to agreed-upon design principles and conventions throughout the development process.

It's essential to note that conceptual integrity doesn't imply disregarding the opinions of team members. On the contrary, diverse perspectives are valuable and should be openly discussed. However, these ideas should align with the established principles and conventions for maintaining a unified and coherent system.

# Several approaches contribute to achieving conceptual integrity:

Communication:

Open and effective communication among team members is vital. Discussing ideas, sharing insights, and ensuring everyone is on the same page contribute to a consistent vision.

Code Reviews:

Regular code reviews help maintain consistency by ensuring that the implemented code aligns with the established principles. Peer reviews provide an opportunity to catch deviations from the agreed-upon design.

Design Principles and Programming Constructs:

Consistently applying design principles and using standardized programming constructs helps create a uniform structure and style throughout the codebase.

Well-Defined Design or Architecture:

A clear and well-defined design or architecture serves as a foundation for the entire software system. It provides guidelines that contribute to conceptual integrity.

Unifying Concepts:

Identifying and adhering to unifying concepts or themes in the software design promotes consistency and a cohesive user experience.

Small Core Group:

Having a small core group responsible for accepting each commit to the code base ensures that changes align with the established principles, preventing divergent paths.

By embracing these strategies, development teams can foster conceptual integrity, resulting in a software system that is not only functional but also maintains a unified and coherent identity.

* * *

Effective communication plays a pivotal role in maintaining conceptual integrity within a development team. It enables team members to discuss and reach agreements on the use of specific libraries or methods to address particular issues, contributing to the creation of more consistent code. Incorporating certain best practices can foster communication and enhance conceptual integrity. Agile development practices, such as daily stand-up meetings and sprint retrospectives, are examples of effective approaches.

Daily Stand-Up Meetings:

Regular, brief stand-up meetings provide a platform for team members to communicate their progress, challenges, and plans. This facilitates awareness of ongoing activities and ensures that everyone is aligned with the project's goals.

Sprint Retrospectives:

Sprint retrospectives occur at the end of each sprint or development cycle. They offer an opportunity for the team to reflect on what worked well, what could be improved, and how to enhance collaboration. This iterative feedback loop contributes to continuous improvement and helps maintain conceptual integrity.

Collaborative Decision-Making:

Encouraging collaborative decision-making ensures that important choices related to design, architecture, and coding practices are made collectively. This fosters a shared understanding and commitment to the principles of conceptual integrity.

Documentation:

Clear and accessible documentation serves as a reference point for team members. It outlines design principles, coding conventions, and any agreed-upon standards, ensuring that everyone is on the same page and can adhere to the established practices.

Feedback Channels:

Establishing open channels for feedback encourages team members to express their thoughts and concerns. This can be achieved through regular team meetings, dedicated feedback sessions, or online collaboration tools.

Knowledge Sharing:

Facilitating knowledge-sharing sessions or workshops allows team members to exchange insights, discuss best practices, and collectively build a deeper understanding of the software architecture and design goals.

Consistent Coding Standards:

Enforcing and adhering to consistent coding standards helps create a unified coding style. This consistency contributes to conceptual integrity by ensuring that the codebase maintains a cohesive structure.

By incorporating these practices, development teams can strengthen communication channels, promote collaboration, and uphold the principles of conceptual integrity throughout the software development lifecycle.

* * *

# Generalization Principles

* * *

The previous module in this course provided an overview of the four fundamental design principles: abstraction, encapsulation, decomposition, and generalization. These principles serve as valuable guides when making design decisions in object-oriented systems.

However, among these principles, generalization and inheritance are particularly challenging topics in object-oriented programming and modeling.

Inheritance is a potent design tool that, when used correctly, contributes to the development of clean, reusable, and maintainable software systems. Nevertheless, its misuse can result in poor code quality. If design principles are applied incorrectly, they might exacerbate issues rather than solving them. Understanding how to properly utilize inheritance is crucial for effective object-oriented design.

To determine whether inheritance is being misused, it's beneficial to consider a couple of generalization principles.

One principle revolves around questioning the necessity of a subclass: "Am I using inheritance to simply share attributes or behavior without further adding anything special in my subclasses?" If the answer is "yes," then inheritance may be misused, as there might be no need for the subclasses, and the superclass alone should suffice.

For instance, considering the Employee superclass for managers, salespeople, and cashiers makes sense because each subtype performs specific functions. On the other hand, creating subclasses for different types of pizza, where no true specialization exists, would be unnecessary.

Another technique involves assessing whether the Liskov substitution principle is violated. According to this principle, a subclass should replace a superclass only if it doesn't alter the functionality of the superclass. If a subclass replaces a superclass but completely changes its behaviors, then inheritance is likely misused.

For example, if a Whale class, exhibiting swimming behavior, is substituted for an Animal class, overriding functions like running and walking, it violates the Liskov substitution principle. In Java, the Stack class inheriting from Vector is an example of bad inheritance, as it introduces behaviors not expected from a stack, such as returning an element at a specified index or inserting an element into a specific index.

In situations where inheritance is not suitable, decomposition can offer a better solution. Consider the example of a smartphone, which is more aptly handled through decomposition than inheritance. Going back to the separation of concerns example, a smartphone can encompass the distinct functions of a traditional phone and a camera. Instead of creating subclasses that inherit from a generic "Phone" class, decomposition allows for the separate representation and management of the unique functionalities of the phone and camera within the smartphone system. This approach avoids unnecessary complexities that may arise from forced inheritance and better aligns with the modular and distinct nature of smartphone features.

* * *

# Model Checking

In addition to designing a software system, it is crucial to employ techniques for verifying the system. Several verification techniques include unit testing, beta testing, simulations, and model checking. Model checking is a systematic examination of your system's state model across all possible states, uncovering errors that may not be identified by other testing methods.

During model checking, all the diverse states of the software are scrutinized to detect any errors. This is achieved by simulating various events that could alter the states and variables of the software. Model checking exposes flaws by indicating violations of the rules governing the behavior of the state model. Typically, model checks are carried out using specialized software designed for this purpose.

Various types of model checking software are available, including free options accessible to developers using different programming languages. Model checking is typically performed as part of the software testing process.

Consider software with a rule that prohibits deadlock situations, where the system cannot progress because two tasks are waiting for the same resource. Model checking would simulate different states in your system, and if a deadlock were possible, it would highlight this violation with detailed information.

The process of model checking software involves several key steps. Model checkers initiate the process by generating a state model from your code. This state model represents an abstract state machine capable of existing in various states. Subsequently, the model checker scrutinizes the state model to verify its adherence to specific behavioral properties. For instance, the model checker can meticulously inspect the state model for potential flaws such as race conditions. Throughout this process, the model checker systematically explores all possible states within your model to ensure its correctness and adherence to specified properties.

# The model checking process consists of three distinct phases.

The modelling phase marks the initiation of the process. In this phase, the model description is input using the same programming languages as the system. Additionally, any desired properties are specified, and sanity checks are performed. These sanity checks involve quick evaluations based on clear and simple logic to identify and address straightforward errors before employing model checkers. For instance, a sanity check might involve turning the system on and off.

The running phase follows the modelling phase. During this phase, the model checker is executed to assess how well the model aligns with the desired properties outlined in the modelling phase.

The analysis phase is the concluding stage. In this phase, all specified properties are examined to ensure satisfaction and identify any violations. Violations, termed counterexamples, are detailed descriptions of system irregularities provided by the model checker. This information is crucial for analyzing the occurrence of violations and subsequently revising and fixing any identified problems in the software. It is advisable to run the model checker iteratively after making fixes, repeating the process until confidence is established in the correctness of the software concerning the desired properties.

Model checking plays a pivotal role in ensuring not only the well-designed nature of software but also its alignment with desired properties and intended functionality.