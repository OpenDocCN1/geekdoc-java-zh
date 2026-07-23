![](image_rsrc27V.jpg)

Java Design                                                           

Pattern                                                                                       

In This Book You Will Learn Explanation with Diagramme and

Working Labs with Successfull Execution of Labs with Output Shown

Readymade Solution With Step By Step Explanation      

AMIT K

Contents

SQL: Beginners Guide to Learn SQL Programming Step by Step

Introduction

Chapter 1 : Introduction

Design Pattern Introduction

Chapter 2 : Creational Design Pattern

Factory Pattern                   (  Lab - 1  )

Abstract Factory Pattern  (  Lab - 2  )

Singleton Pattern                 (  Lab - 3  )

Prototype Pattern                (  Lab - 4  )

Builder Pattern                     (  Lab - 5  )

Chapter 3 : Structural Design Pattern

Adapter Pattern                   (  Lab - 6  )

Bridge Pattern                     (  Lab - 7  )

Composite Pattern              (  Lab - 8  )

Decorator Pattern               (  Lab - 9 )

Facade Pattern                    (  Lab - 10 )

Filter/Criteria Pattern         (  Lab - 11 )

Proxy Pattern                       (  Lab - 12 )

Chapter 4 : Behavioral Design Pattern

Chain Of Responsibility Pattern         (  Lab - 13 )

Command Pattern                                (  Lab - 14 )

Interpreter Pattern                              (  Lab - 15 )

Iterator Pattern                                    (  Lab - 16 )

Mediator Pattern                                 (  Lab - 17 )

Null Object Pattern                               (  Lab - 18 )

Observer Pattern                                   (  Lab - 19 )

State Pattern                                          (  Lab - 20 )

Strategy Pattern                                    (  Lab - 21 )

Template Pattern                                   (  Lab - 22 )

Visitor Pattern                                        (  Lab - 23 )

MVC Pattern                                            (  Lab - 24 )

Chapter 5 : JEE Design Pattern

Data Access Object Pattern                   (  Lab - 25 )

Introduction

Design patterns are programming language independent, it is for solving the common object-oriented design problems.

A design pattern represents an idea, not an implementation.

By using the design patterns we can make our code more flexible, reusable and maintainable.

Java itself internally follows design patterns.

In core java, there are mainly three types of design patterns, which are further divided into their sub-parts:

*   Creational Design Pattern

1\. Factory Pattern

2.  Abstract Factory Pattern

3.  Singleton Pattern

4.  Prototype Pattern

5.  Builder Pattern.

*   Structural Design Pattern

1.  Adapter Pattern

2.  Bridge Pattern

3.  Composite Pattern

4.  Decorator Pattern

5.  Facade Pattern

6.  Flyweight Pattern

7.  Proxy Pattern

*   Behavioral Design Pattern

1\. Chain Of Responsibility Pattern

2.  Command Pattern

3.  Interpreter Pattern

4.  Iterator Pattern

5.  Mediator Pattern

6.  Memento Pattern

7.  Observer Pattern

8.  State Pattern

9.  Strategy Pattern

10.  Template Pattern

11.  Visitor Pattern

Creational design patterns are used when creating objects.

Chapter 1 :

Introduction

A design pattern is a well-proved solution for solving the specific problem/task.

For example, to create a class for which only a single instance should be created and that single object can be used by all other classes, use Singleton design pattern.

Design patterns are programming language independent, it is for solving the common object-oriented design problems.

A design pattern represents an idea, not an implementation.

By using the design patterns we can make our code more flexible, reusable and maintainable.

Java itself internally follows design patterns.

In core java, there are mainly three types of design patterns, which are further divided into their sub-parts:

*   Creational Design Pattern

1\. Factory Pattern

2.  Abstract Factory Pattern

3.  Singleton Pattern

4.  Prototype Pattern

5.  Builder Pattern.

*   Structural Design Pattern

1.  Adapter Pattern

2.  Bridge Pattern

3.  Composite Pattern

4.  Decorator Pattern

5.  Facade Pattern

6.  Flyweight Pattern

7.  Proxy Pattern

*   Behavioral Design Pattern

1\. Chain Of Responsibility Pattern

2.  Command Pattern

3.  Interpreter Pattern

4.  Iterator Pattern

5.  Mediator Pattern

6.  Memento Pattern

7.  Observer Pattern

8.  State Pattern

9.  Strategy Pattern

10.  Template Pattern

11.  Visitor Pattern

12.  MVC Pattern

*   JEE Design Pattern

1\. Data Access Object Pattern

Creational design patterns are used when creating objects

What is Gang of Four (GOF)?

Elements of Reusable Object-Oriented Software.

Design patterns are based on the following principles of object orientated design.

*   Program to an interface not an implementation
*   Favor object composition over inheritance

Chapter 2 :

Creational Design Pattern

1\. Factory Pattern

2.  Abstract Factory Pattern

3.  Singleton Pattern

4.  Prototype Pattern

1.  Factory Pattern

Factory pattern is a creational pattern as this pattern provides better ways to create an object.

In Factory pattern, we create object without exposing the creation logic to the client.

Lab - 1

In the following sections we will show how to use Factory Pattern to create objects.

The objects created by the factory pattern would be shape objects, such as Circle, Rectangle.

First we design an interface to represent Shape.

The following code is for Shape.java

| public interface Shape {​   void draw();} |

Then we create concrete classes implementing the interface.

The following code is for Rectangle.java

| public class Rectangle implements Shape {@Overridepublic void draw() {System.out.println("Inside Rectangle::draw() method.");}} |

Square.java

| public class Square implements Shape {@Overridepublic void draw() {​System.out.println("Inside Square::draw() method.");}} |

Circle.java

| public class Circle implements Shape {@Overridepublic void draw() {System.out.println("Inside Circle::draw() method.");}} |

The core factory pattern is a Factory class. The following code shows how to create a Factory class for Shape objects.

The ShapeFactory class creates Shape object based on the String value passed in to the getShape() method. If the String value is CIRCLE, it will create a Circle object.

ShapeFactory.java

| public class ShapeFactory {//use getShape method to get object of type shapepublic Shape getShape(String shapeType){if(shapeType == null){​   return null;}   if(shapeType.equalsIgnoreCase("CIRCLE")){​   return new Circle();} else if(shapeType.equalsIgnoreCase("RECTANGLE")){​   return new Rectangle();} else if(shapeType.equalsIgnoreCase("SQUARE")){​   return new Square();}​   return null;}} |

The following code has main method and it uses the Factory class to get object of concrete class by passing an information such as type.

Main.java

| public class Main {public static void main(String[] args) {ShapeFactory shapeFactory = new ShapeFactory();//get an object of Circle and call its draw method.Shape shape1 = shapeFactory.getShape("CIRCLE");//call draw method of Circleshape1.draw();//get an object of Rectangle and call its draw method.Shape shape2 = shapeFactory.getShape("RECTANGLE");//call draw method of Rectangleshape2.draw();//get an object of Square and call its draw method.Shape shape3 = shapeFactory.getShape("SQUARE");//call draw method of circleshape3.draw();}} |

The code above generates the following result

Output

| ![](image_rsrc27W.jpg) |

2.  Abstract Factory Pattern

Abstract Factory pattern is another creational pattern.

Abstract Factory patterns, also called as Factory of factories, have a factory which creates other factories.

When using Abstract Factory pattern, we first use super factory to create factory, then use the created factory to create objects.

Lab - 2

The following code shows how to use abstract factory pattern.

We are going to create shapes and Printers. For shapes, we would have circle, rectangle and square. For printers we will have paper Printer, Web Printer and screen Printer.

For shape we will create Shape interface, as follows

Shape.java

| interface Shape {​              void draw();} |

Then we create concrete classes implementing the Shape interface.

| class Rectangle implements Shape {@Overridepublic void draw() {System.out.println("Inside Rectangle::draw() method.");}}class Square implements Shape {@Overridepublic void draw() {System.out.println("Inside Square::draw() method.");}}class Circle implements Shape {@Overridepublic void draw() {System.out.println("Inside Circle::draw() method.");}} |

After that we create an interface for Printers.

Printer.java

| interface Printer{​               void print();} |

Then we create concrete classes implementing the Printer interface. 

| class PaperPrinter implements Printer {@Overridepublic void print() {System.out.println("paper");}}class WebPrinter implements Printer {@Overridepublic void print() {System.out.println("web");}}class ScreenPrinter implements Printer {@Overridepublic void print() {System.out.println("screen");}} |

Finally we create an abstract class to get factories for Printer and Shape Objects.

| abstract class AbstractFactory {​abstract Printer getPrinter(String type);​abstract Shape getShape(String shape) ;} |

Finally we create Factory classes extending AbstractFactory to generate object of concrete class based on given information.   

| class ShapeFactory extends AbstractFactory {@Overridepublic Shape getShape(String shapeType){if(shapeType == null){return null;}   if(shapeType.equalsIgnoreCase("CIRCLE")){return new Circle();} else if(shapeType.equalsIgnoreCase("RECTANGLE")){return new Rectangle();} else if(shapeType.equalsIgnoreCase("SQUARE")){return new Square();}​  return null;}@OverridePrinter getPrinter(String type) {​  return null;​ }}class PrinterFactory extends AbstractFactory {@Overridepublic Shape getShape(String shapeType){​ return null;}@OverridePrinter getPrinter(String type) {if(type == null){​   return null;}   if(type.equalsIgnoreCase("paper")){​   return new PaperPrinter();} else if(type.equalsIgnoreCase("web")){​   return new WebPrinter();} else if(type.equalsIgnoreCase("Screen")){​   return new ScreenPrinter();}​ return null;}} |

Create a Factory generator/producer class to get factories by passing an information such as Shape or Printer

| class FactoryProducer {public static AbstractFactory getFactory(String choice){if(choice.equalsIgnoreCase("SHAPE")){​    return new ShapeFactory();​  } else if(choice.equalsIgnoreCase("Printer")){​    return new PrinterFactory();​  }​    return null;}} |

The following code shows how to use the abstract factory patterns.

| public class Main {public static void main(String[] args) {//get shape factoryAbstractFactory shapeFactory= FactoryProducer.getFactory("SHAPE");//get an object of Shape CircleShape shape1 = shapeFactory.getShape("CIRCLE");//call draw method of Shape Circleshape1.draw();//get an object of Shape RectangleShape shape2 = shapeFactory.getShape("RECTANGLE");//call draw method of Shape Rectangleshape2.draw();//get an object of Shape SquareShape shape3 = shapeFactory.getShape("SQUARE");//call draw method of Shape Squareshape3.draw();//get printer factoryAbstractFactory printerFactory= FactoryProducer.getFactory("printer");Printer printer1 = printerFactory.getPrinter("Paper");printer1.print();Printer printer2 = printerFactory.getPrinter("Web");printer2.print();Printer printer3 = printerFactory.getPrinter("Screen");printer3.print();}} |

The code above generates the following result.

Output

| ![](image_rsrc27X.jpg) |

3.  Singleton Pattern

Singleton pattern is a creational pattern.

This pattern involves only a single class which is responsible to creates its own object.

The class ensures that only single object get created.

This class provides a way to access its only object.

For example, when design a user interface, we may only have one main application windows. We can use the Singleton Pattern to ensure that there is only one instance of the MainApplicationWindow object.

Lab – 3

The following code is going to create a MainWindow class.

MainWindow class have its constructor as private and have a static instance of itself.

MainWindow class provides a static method to get its static instance to outside world.

Main, our demo class will use MainWindow class to get a MainWindow object.

MainWindow.java

| class MainWindow {//create an object of MainWindowprivate static MainWindow instance = new MainWindow();//make the constructor private so that this class cannot be//instantiated by other classprivate MainWindow(){}//Get the only object availablepublic static MainWindow getInstance(){return instance;}public void showMessage(){System.out.println("Hello World!");​}}public class Main {​  public static void main(String[] args) {​      //Get the only object available​      MainWindow object = MainWindow.getInstance();​      //show the message​      object.showMessage();​ }} |

Output

| ![](image_rsrc27Y.jpg) |

4.  Prototype Pattern

Prototype pattern is one of the creational patterns.

Prototype pattern helps create duplicate object with better performance.

In Prototype Pattern a clone of an existing object is returned instead of creating new one.

We use Prototype Design Pattern, if the cost of creating a new object is expensive and resource intensive.

Lab – 4

The following code shows how to use Prototype Pattern to create objects.

First it create a Shape abstract class which implements the Cloneable interface.

Shape.java

| abstract class Shape implements Cloneable {​   private String id;​   protected String type;​   abstract void draw();​   public String getType(){​      return type;​   }​   public String getId() {​      return id;​   }​   public void setId(String id) {​      this.id = id;​   }​   public Object clone() {​      Object clone = null;​      try {​         clone = super.clone();​      } catch (CloneNotSupportedException e) {​         e.printStackTrace();​      }​      return clone;​   }​} |

Then it creates three concrete classes extending the Shape class.

| class Rectangle extends Shape {public Rectangle(){type = "Rectangle";}@Overridepublic void draw() {System.out.println("Inside Rectangle::draw() method.");}}class Square extends Shape {public Square(){type = "Square";}@Overridepublic void draw() {System.out.println("Inside Square::draw() method.");}}class Circle extends Shape {public Circle(){type= "Circle";}@Overridepublic void draw() {System.out.println("Inside Circle::draw() method.");}} |

After that it creates a ShapeProtoType class to return the prototype of shapes.

| class ShapeProtoType{​private static Hashtable<String, Shape> shapeMap= new Hashtable<String, Shape>();​public static Shape getShape(String shapeId) {​      Shape cachedShape=  shapeMap.get(shapeId);​      return (Shape) cachedShape.clone();​   }​   public static void loadCache() {​      Circle circle = new Circle();​      circle.setId("1");​      shapeMap.put(circle.getId(),circle);​      Square square = new Square();​      square.setId("2");​      shapeMap.put(square.getId(),square);​      Rectangle rectangle = new Rectangle();​      rectangle.setId("3");​      shapeMap.put(rectangle.getId(),rectangle);​   }​}public  class Main{public  static  void main(String[] args) {ShapeProtoType.loadCache();Shape clonedShape = (Shape) ShapeProtoType.getShape("1");System.out.println("Shape : " + clonedShape.getType());   Shape clonedShape2 = (Shape) ShapeProtoType. getShape("2");System.out.println("Shape : " + clonedShape2.getType());   Shape clonedShape3 = (Shape) ShapeProtoType. getShape("3");System.out.println("Shape : " + clonedShape3.getType());}} |

The code above generates the following result.

Output

| ![](image_rsrc27Z.jpg) |

5.  Builder Pattern

Builder pattern is used to create a complex object using simple objects. It creates the bigger object step by step from small and simple object.

Builder pattern is another creational pattern.

For example, when creating a window as our application's main window, we need to create a menu, a toolbar and then add the menu and toolbar.

For each window we are going to create, we need to create an empty window, create a menu, create a toolbar, install the menu and toolbar to the window.

We can use the builder pattern to hide the implementation of how to create a window.

Lab – 5

MainWindow.java

| class Menu {}class ToolBar {}class MainWindow {Menu menu;ToolBar toolBar;public Menu getMenu() {return menu;}public void setMenu(Menu menu) {this.menu = menu;}public ToolBar getToolBar() {return toolBar;}public void setToolBar(ToolBar toolBar) {this.toolBar = toolBar;}}class WindowBuilder{public static MainWindow createWindow(){MainWindow window = new MainWindow();Menu menu = new Menu();ToolBar toolBar = new ToolBar();window.setMenu(menu);window.setToolBar(toolBar);return window;}}public class Main{public static void main(String[] args) {MainWindow object = WindowBuilder.createWindow();}} |

Chapter 3 :

Structural Design Pattern

1.  Adapter Pattern

2.  Bridge Pattern

3.  Composite Pattern

4.  Decorator Pattern

5.  Facade Pattern

6.  Flyweight Pattern

7.  Proxy Pattern

1.  Adapter Pattern

We use the adapter in real life a lot. For example, we use a memory card adapter to connect a memory card and a computer since the computer only support one type of memory card and our card is not compatible with the computer.

Adapter is a converter between two incompatible entities. Adapter pattern is a structural pattern.

In Java design pattern, Adapter pattern works as a bridge between two incompatible interfaces.

By using the adapter pattern we can unify the two incompatible interfaces.

Lab – 6

First we create a Player interface to play any time of media files.

MyPlayer is the adapter, it unifies the interface of playing media files.

| interface Player {​   public void play(String type, String fileName);}interface AudioPlayer {​   public void playAudio(String fileName);}interface VideoPlayer {​   public void playVideo(String fileName);}class MyAudioPlayer implements AudioPlayer {​   @Override​   public void playAudio(String fileName) {​      System.out.println("Playing. Name: "+ fileName);   ​   }}class MyVideoPlayer implements VideoPlayer {​   @Override​   public void playVideo(String fileName) {​      System.out.println("Playing. Name: "+ fileName);   ​   }}class MyPlayer implements Player {​   AudioPlayer audioPlayer = new MyAudioPlayer();​   VideoPlayer videoPlayer = new MyVideoPlayer();​   public MyPlayer(){     ​   }​   @Override​   public  void play(String audioType, String fileName) {  ​      if(audioType.equalsIgnoreCase("avi")){​         videoPlayer.playVideo(fileName);​      }else if(audioType.equalsIgnoreCase("mp3")){​         audioPlayer.playAudio(fileName);​      }​   }​}​public class Main{​   public static void main(String[] args) {​      MyPlayer myPlayer = new MyPlayer();​      myPlayer.play("mp3", "h.mp3");​      myPlayer.play("avi", "me.avi");​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc280.jpg) |

2.  Bridge Pattern

Bridge pattern decouples an definition from its implementation. It is a structural pattern.

This pattern involves an interface which acts as a bridge. The bridge makes the concrete classes independent from interface implementer classes.

Both types of classes can be altered without affecting each other.

Lab – 7

| interface Printer {​   public void print(int radius, int x, int y);}class ColorPrinter implements Printer {​   @Override​   public void print(int radius, int x, int y) {​      System.out.println("Color: " + radius +", x: "  +x+", "+ y +"]");   ​   }}class BlackPrinter implements Printer {​   @Override​   public void print(int radius, int x, int y) {​      System.out.println("Black: " + radius +", x: "+x+", "+ y +"]");​   }}​abstract class Shape {​   protected Printer print;​   protected Shape(Printer p){​      this.print = p;​   }​   public abstract void draw();​}​class Circle extends Shape {​   private int x, y, radius;​   public Circle(int  x, int  y, int  radius, Printer draw) {​      super(draw);​      this.x = x;​      this.y = y;​      this.radius = radius;​   }​   public void draw() {​      print.print(radius,x,y);​   }​}public class Main {public static void main(String[] args) {Shape redCircle = new Circle(100,100, 10, new ColorPrinter());Shape blackCircle = new Circle(100,100, 10, new BlackPrinter());​  redCircle.draw();​  blackCircle.draw();}} |

The code above generates the following result.

Output

| ![](image_rsrc281.jpg) |

3.  Composite Pattern

Composite pattern is structural pattern since it creates a tree structure of group of objects.

Composite pattern treats a group of objects as a single object.

Composite pattern uses one class to represent a tree structure.

In Composite pattern we create a class contains group of its own objects.

Lab – 8

The following code uses the Employee class to demonstrate the Composite pattern.

Employee.java

| import java.util.ArrayList;import java.util.List;class Employee {private String name;private String title;private List<Employee> subordinates;public Employee(String name,String title) {this.name = name;this.title = title;subordinates = new ArrayList<Employee>();}public void add(Employee e) {subordinates.add(e);}public void remove(Employee e) {subordinates.remove(e);}public List<Employee> getSubordinates(){return subordinates;}public String toString(){return "Employee :[ Name : "+ name+", dept : "+ title +subordinates +" ]";}  }public class Main {public static void main(String[] args) {Employee CEO = new Employee("John","CEO");Employee headSales = new Employee("Rob","Sales");Employee headMarketing = new Employee("Mike","Marketing");Employee programmer1 = new Employee("Lili","Programmer");Employee programmer2 = new Employee("Bob","Programmer");Employee tester1 = new Employee("Jack","Tester");Employee tester2 = new Employee("Tom","Tester");CEO.add(headSales);CEO.add(headMarketing);headSales.add(tester1);headSales.add(tester2);headMarketing.add(programmer1);headMarketing.add(programmer2);//print all employees of the organizationSystem.out.println(CEO);for (Employee headEmployee : CEO.getSubordinates()) {System.out.println(headEmployee);for (Employee employee : headEmployee.getSubordinates()) {System.out.println(employee);}}   }} |

The code above generates the following result.

Output

| ![](image_rsrc282.jpg) |

4.  Decorator Pattern

Decorator pattern adds new functionality an existing object without chaining its structure.

It is a structural pattern as it acts as a wrapper to existing class.

Decorator pattern creates a decorator class to wrap the original class and provides additional functionality.

Lab – 9

| interface Printer {​   void print();}class PaperPrinter implements Printer {​   @Override​   public void print() {​      System.out.println("Paper Printer");​   }​}​class PlasticPrinter implements Printer {​   @Override​   public void print() {​      System.out.println("Plastic Printer");​   }​}​abstract class PrinterDecorator implements Printer {​   protected Printer decoratedPrinter;​   public PrinterDecorator(Printer d){​      this.decoratedPrinter = d;​   }​   public void print(){​      decoratedPrinter.print();​   }​}​class Printer3D extends PrinterDecorator {​   public Printer3D(Printer decoratedShape) {​      super(decoratedShape);   ​   }​   @Override​   public void print() {​     System.out.println("3D.");​     decoratedPrinter.print();        ​   }​}​public class Main{​   public static void main(String[] args) {​      Printer plasticPrinter = new PlasticPrinter();​      Printer plastic3DPrinter = new Printer3D(new PlasticPrinter());​      Printer paper3DPrinter = new Printer3D(new PaperPrinter());​      plasticPrinter.print();​      plastic3DPrinter.print();​      paper3DPrinter.print();​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc283.jpg) |

5.  Facade Pattern

Facade pattern hides the complexities of a system.

It provides a simple interface to the client and the client uses the interface to interact with the system.

Facade pattern is a structural pattern.

Lab – 10

| class ShapeFacade {​  interface Shape {​    void draw();}class Rectangle implements Shape {​    @Override​    public void draw() {​      System.out.println("Rectangle::draw()");​    }​  }​  class Square implements Shape {​    @Override​    public void draw() {​      System.out.println("Square::draw()");​    }​  }​  class Circle implements Shape {​    @Override​    public void draw() {​      System.out.println("Circle::draw()");​    }​  }​  private Shape circle = new Circle();​  private Shape rectangle = new Rectangle();​  private Shape square = new Square();​  public ShapeFacade() {​  }​  public void drawCircle() {​    circle.draw();​  }​  public void drawRectangle() {​    rectangle.draw();​  }​  public void drawSquare() {​    square.draw();​  }​}​public class Main {​  public static void main(String[] args) {​    ShapeFacade shapeFacade = new ShapeFacade();​    shapeFacade.drawCircle();​    shapeFacade.drawRectangle();​    shapeFacade.drawSquare();​  }​} |

The code above generates the following result.

Output

| ![](image_rsrc284.jpg) |

6.  Filter/Criteria Pattern

Filter pattern filters objects using different criteria.

The criteria can be chained together through logical operations.

Filter pattern is a structural pattern.

Lab – 11

Employee.java

| import java.util.List;import java.util.ArrayList;class Employee {private String name;private String gender;private String retireStatus;public Employee(String name, String gender, String r) {this.name = name;this.gender = gender;this.retireStatus = r;}public String getName() {return name;}public String getGender() {return gender;}public String getRetireStatus() {return retireStatus;}@Overridepublic String toString() {return "Employee [name=" + name + ", gender=" + gender+ ", retireStatus=" + retireStatus + "]";}}interface Criteria {public List<Employee> meetCriteria(List<Employee> persons);}class CriteriaMale implements Criteria {@Overridepublic List<Employee> meetCriteria(List<Employee> persons) {List<Employee> malePersons = new ArrayList<Employee>();for (Employee person : persons) {if (person.getGender().equalsIgnoreCase("MALE")) {malePersons.add(person);}}return malePersons;}}class CriteriaFemale implements Criteria {@Overridepublic List<Employee> meetCriteria(List<Employee> persons) {List<Employee> femalePersons = new ArrayList<Employee>();for (Employee person : persons) {if (person.getGender().equalsIgnoreCase("FEMALE")) {femalePersons.add(person);}}return femalePersons;}}class CriteriaRetire implements Criteria {@Overridepublic List<Employee> meetCriteria(List<Employee> persons) {List<Employee> singlePersons = new   ArrayList<Employee>();for (Employee person : persons) {if (person.getRetireStatus().equalsIgnoreCase("YES")) {singlePersons.add(person);}}return singlePersons;}}class AndCriteria implements Criteria {private Criteria criteria;private Criteria otherCriteria;public AndCriteria(Criteria criteria, Criteria otherCriteria) {this.criteria = criteria;this.otherCriteria = otherCriteria;}@Overridepublic List<Employee> meetCriteria(List<Employee> persons) {List<Employee> firstCriteriaPersons = criteria.meetCriteria(persons);return  otherCriteria.meetCriteria(firstCriteriaPersons);}}class OrCriteria implements Criteria {private Criteria criteria;private Criteria otherCriteria;public OrCriteria(Criteria criteria, Criteria otherCriteria){this.criteria = criteria;this.otherCriteria = otherCriteria;}@Overridepublic List<Employee> meetCriteria(List<Employee> persons){List<Employee> firstCriteriaItems = criteria.meetCriteria(persons);List<Employee> otherCriteriaItems = otherCriteria.meetCriteria(persons);for (Employee person : otherCriteriaItems) {if (!firstCriteriaItems.contains(person)) {firstCriteriaItems.add(person);}}return firstCriteriaItems;}}public class Main {public static void main(String[] args) {List<Employee> persons = new ArrayList<Employee>();persons.add(new Employee("Tom", "Male", "YES"));persons.add(new Employee("Jack", "Male", "NO"));persons.add(new Employee("Jane", "Female", "NO"));persons.add(new Employee("Diana", "Female", "YES"));persons.add(new Employee("Mike", "Male", "NO"));persons.add(new Employee("Bob", "Male", "YES"));Criteria male = new CriteriaMale();Criteria female = new CriteriaFemale();Criteria retire = new CriteriaRetire();Criteria retireMale = new AndCriteria(retire, male);Criteria retireOrFemale = new OrCriteria(retire, female);System.out.println("Males: ");printPersons(male.meetCriteria(persons));System.out.println("Females: ");printPersons(female.meetCriteria(persons));System.out.println("Retire Males: ");printPersons(retireMale.meetCriteria(persons));System.out.println("Retire Or Females: ");printPersons(retireOrFemale.meetCriteria(persons));}public static void printPersons(List<Employee> persons) {for (Employee person : persons) {System.out.println(person);}}} |

The code above generates the following result.

Output

| ![](image_rsrc285.jpg) |

7.  Proxy Pattern

In Proxy pattern, a class represents functionality of another class.

Proxy pattern is a structural pattern.

In Proxy pattern, we create object with original interface to expose its functionality to outer world.

Lab – 12

| interface Printer {​   void print();}class ConsolePrinter implements Printer {​   private String fileName;​   public ConsolePrinter(String fileName){​      this.fileName = fileName;​   }​   @Override​   public void print() {​      System.out.println("Displaying " + fileName);​   }​}​class ProxyPrinter implements Printer{​   private ConsolePrinter consolePrinter;​   private String fileName;​   public ProxyPrinter(String fileName){​      this.fileName = fileName;​   }​   @Override​   public void print() {​      if(consolePrinter == null){​         consolePrinter = new ConsolePrinter(fileName);​      }​      consolePrinter.print();​   }​}​public class Main {​   public static void main(String[] args) {​      Printer image = new ProxyPrinter("test");​      image.print();  ​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc286.jpg) |

Chapter 4 :

Behavioral Design Pattern

1\. Chain Of Responsibility Pattern

2.  Command Pattern

3.  Interpreter Pattern

4.  Iterator Pattern

5.  Mediator Pattern

6.  Memento Pattern

7.  Observer Pattern

8.  State Pattern

9.  Strategy Pattern

10.  Template Pattern

11.  Visitor Pattern

12.  MVC Pattern

1.  Chain Of Responsibility Pattern

The chain of responsibility pattern creates a list of receiver objects for a request.

This pattern is behavioral patterns.

When using chain of responsibility pattern, normally each receiver contains reference to another receiver.

If one object cannot handle the request then it passes the same to the next receiver and so on.

Lab – 13

| abstract class Logger {​   protected Logger nextLogger;public void setNextLogger(Logger nextLogger){​      this.nextLogger = nextLogger;​   }​   public void logMessage(String message){​      log(message);​      if(nextLogger !=null){​         nextLogger.logMessage(message);​      }​   }​   abstract protected void log(String message);​}​class ConsoleLogger extends Logger {​   public ConsoleLogger(){​   }​   @Override​   protected void log(String message) {   ​      System.out.println("Console::Logger: " + message);​   }​}​class EMailLogger extends Logger {​   public EMailLogger(){​   }​   @Override​   protected void log(String message) {   ​      System.out.println("EMail::Logger: " + message);​   }​}​class FileLogger extends Logger {​   public FileLogger(){​   }​   @Override​   protected void log(String message) {   ​      System.out.println("File::Logger: " + message);​   }​}​public class Main { ​   private static Logger getChainOfLoggers(){​      Logger emailLogger = new EMailLogger();​      Logger fileLogger = new FileLogger();​      Logger consoleLogger = new ConsoleLogger();​      emailLogger.setNextLogger(fileLogger);​      fileLogger.setNextLogger(consoleLogger);​      return emailLogger;​   }​   public static void main(String[] args) {​      Logger loggerChain = getChainOfLoggers();​      loggerChain.logMessage("Null pointer");​      loggerChain.logMessage("Array Index Out of Bound");​      loggerChain.logMessage("Illegal Parameters");​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc287.jpg) |

2.  Command Pattern

Command pattern is a data driven design pattern It is one of the behavioral pattern.

A request is wrapped under a object as command and passed to invoker object.

Invoker object passes the command to the corresponding object and that object executes the command.

Lab – 14

| import java.util.ArrayList;import java.util.List;interface Command {void execute();}class MouseCursor {private int x = 10;private int y = 10;public void move() {System.out.println("Old Position:"+x +":"+y);x++;y++;System.out.println("New Position:"+x +":"+y);}public void reset() {System.out.println("reset");x = 10;y = 10;}}class MoveCursor implements Command {private MouseCursor abcStock;public MoveCursor(MouseCursor abcStock) {this.abcStock = abcStock;}public void execute() {abcStock.move();}}class ResetCursor implements Command {private MouseCursor abcStock;public ResetCursor(MouseCursor abcStock) {this.abcStock = abcStock;}public void execute() {abcStock.reset();}}class MouseCommands {private List<Command> orderList = new ArrayList<Command>();public void takeOrder(Command order) {orderList.add(order);}public void placeOrders() {for (Command order : orderList) {order.execute();}orderList.clear();}}public class Main {public static void main(String[] args) {MouseCursor cursor = new MouseCursor();MoveCursor moveCursor = new MoveCursor(cursor);ResetCursor resetCursor = new ResetCursor(cursor);MouseCommands commands= new MouseCommands();commands.takeOrder(moveCursor);commands.takeOrder(resetCursor);commands.placeOrders();}} |

The code above generates the following result.

Output

| ![](image_rsrc288.jpg) |

3.  Interpreter Pattern

We normally use Interpreter pattern to evaluate language grammar or expression.

This type of pattern is one of the behavioral patterns.

Lab – 15

| interface Expression {​  public boolean evaluate(String context);}class IsInExpression implements Expression {​  private String data;​  public IsInExpression(String data) {​    this.data = data;​  }​  @Override​  public boolean evaluate(String context) {​    if (context.contains(data)) {​      return true;​    }​    return false;​  }​}​class OrExpression implements Expression {​  private Expression expr1 = null;​  private Expression expr2 = null;​  public OrExpression(Expression expr1, Expression expr2) {​    this.expr1 = expr1;​    this.expr2 = expr2;​  }​  @Override​  public boolean evaluate(String context) {​    return expr1.evaluate(context) &#124;&#124; expr2.evaluate(context);​  }​}​class AndExpression implements Expression {​  private Expression expr1 = null;​  private Expression expr2 = null;​  public AndExpression(Expression expr1, Expression expr2) {​    this.expr1 = expr1;​    this.expr2 = expr2;​  }​  @Override​  public boolean evaluate(String context) {​    return expr1.evaluate(context) && expr2.evaluate(context);​  }​}​public class Main {​  public static void main(String[] args) {​    Expression select = new IsInExpression("Select");​    Expression from = new IsInExpression("From");​    Expression isSelectFrom = new AndExpression(select, from);​    Expression insert = new IsInExpression("Insert");​    Expression update = new IsInExpression("Update");​    Expression isInsertOrUpdate = new OrExpression(insert, update);​    System.out.println(isSelectFrom.evaluate("Select"));​    System.out.println(isInsertOrUpdate.evaluate("Insert"));​    System.out.println(isSelectFrom.evaluate("Select From"));​    System.out.println(isInsertOrUpdate.evaluate("Update"));​  }​} |

The code above generates the following result.

Output

| ![](image_rsrc289.jpg) |

4.  Iterator Pattern

Iterator pattern accesses the elements of a collection object in sequential manner without knowing its underlying representation.

Iterator pattern is one of the behavioral patterns.

Lab – 16

| interface Iterator {​   public boolean hasNext();​   public Object next();}class LetterBag {​   public String names[] = {"R" , "J" ,"A" , "L"};​   public Iterator getIterator() {​      return new NameIterator();​   }​   class NameIterator implements Iterator {​      int index;​      @Override​      public boolean hasNext() {​         if(index < names.length){​            return true;​         }​         return false;​      }​      @Override​      public Object next() {​         if(this.hasNext()){​            return names[index++];​         }​         return null;​      }   ​   }​}​public class Main {​   public static void main(String[] args) {​      LetterBag bag = new LetterBag();​      for(Iterator iter = bag.getIterator(); iter.hasNext();){​         String name = (String)iter.next();​         System.out.println("Name : " + name);​      }  ​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc28A.jpg) |

5.  Mediator Pattern

Mediator pattern reduces communication between multiple objects.

This pattern provides a mediator class which handles all the communications between different classes.

Mediator pattern falls under behavioral pattern category.

Lab – 17

| class Printer {​   public static void showMessage(Machine user, String message){​      System.out.println(new java.util.Date().toString()​         + " [" + user.getName() +"] : " + message);​   }​}class Machine {​   private String name;​   public Machine(String name){​      this.name  = name;​   }​   public String getName() {​      return name;​   }​   public void setName(String name) {​      this.name = name;​   }​   public void sendMessage(String message){​      Printer.showMessage(this,message);​   }​}​class Main {​   public static void main(String[] args) {​      Machine m1= new Machine("M1");​      Machine m2 = new Machine("M2");​      m1.sendMessage("Rebooting");​      m2.sendMessage("Computing");​   }​} |

6.  Null Object Pattern

In Null Object pattern, a business-meaningless object is created incase of   null   object.

We use the business-meaningless object to replace the null pointer check.

We call the a business-meaningless object Null Object.

Null object provides default behaviour when data is not available.

In Null Object pattern, we usually create an abstract class to specify the various operations.

Both Null Object and concreate classes will extends this abstract class.

The Null Object class just provide empty logic.

Lab – 18

| abstract class AbstractEmployee {​   protected String name;​   public abstract boolean isNull();​   public abstract String getName();​}class Programmer extends AbstractEmployee {​   public Programmer(String name) {​      this.name = name;   ​   }​   @Override​   public String getName() {​      return name;​   }​   @Override​   public boolean isNull() {​      return false;​   }​}​class NullCustomer extends AbstractEmployee {​   @Override​   public String getName() {​      return "Not Available";​   }​   @Override​   public boolean isNull() {​      return true;​   }​}​class EmployeeFactory {​  public  static  final String[] names = {"Rob", "Joe", "Jack"};​ public  static AbstractEmployee getCustomer(String name){​      for (int i = 0; i < names.length; i++) {​         if (names[i].equalsIgnoreCase(name)){​            return new Programmer(name);​         }​      }​      return new NullCustomer();​   }​}public class Main {public static void main(String[] args) {AbstractEmployee emp = EmployeeFactory.getCustomer("Rob");AbstractEmployee emp2 = EmployeeFactory.getCustomer("Bob");AbstractEmployee emp3 = EmployeeFactory.getCustomer("Jack");AbstractEmployee emp4 = EmployeeFactory.getCustomer("Tom");​      System.out.println(emp.getName());​      System.out.println(emp2.getName());​      System.out.println(emp3.getName());​      System.out.println(emp4.getName());​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc28B.jpg) |

7.  Observer Pattern

Observer pattern is used to notify its depenedent objects if one object is modified.

Observer pattern is a behavioral pattern category.

Lab – 19

| import java.util.ArrayList;import java.util.List;class MyValue {private List<Observer> observers= new ArrayList<Observer>();private int state;public int getState() {return state;}public void setState(int state) {this.state = state;notifyAllObservers();}public void attach(Observer observer){observers.add(observer);   }public void notifyAllObservers(){for (Observer observer : observers) {observer.update();}}  }abstract class Observer {protected MyValue subject;public abstract void update();}class PrinterObserver extends Observer{public PrinterObserver(MyValue subject){this.subject = subject;this.subject.attach(this);}@Overridepublic void update() {System.out.println("Printer: " + subject.getState() );}}class EmailObserver extends Observer{public EmailObserver(MyValue subject){this.subject = subject;this.subject.attach(this);}@Overridepublic void update() {System.out.println("Email: "+ subject.getState() );}}class FileObserver extends Observer{public FileObserver(MyValue subject){this.subject = subject;this.subject.attach(this);}@Overridepublic void update() {System.out.println("File: " + subject.getState());}}public class Main {public static void main(String[] args) {MyValue subject = new MyValue();new FileObserver(subject);new EmailObserver(subject);new PrinterObserver(subject);subject.setState(15);subject.setState(10);}} |

The code above generates the following result.

Output

| ![](image_rsrc28C.jpg) |

8.  State Pattern

In State pattern a class behavior is changed based on its state.

State pattern is a behavior pattern.

When using State pattern, we create various state objects and a context object whose behavior varies as its state object changes.

Lab – 20

| interface State {​  public void doAction(Context context);}class StartState implements State {​  public void doAction(Context context) {​    System.out.println("In start state");​    context.setState(this);​  }​  public String toString() {​    return "Start State";​  }​}class StopState implements State {​  public void doAction(Context context) {​    System.out.println("In stop state");​    context.setState(this);​  }​  public String toString() {​    return "Stop State";​  }​}​class PlayState implements State {​  public void doAction(Context context) {​    System.out.println("In play state");​    context.setState(this);​  }​  public String toString() {​    return "Play State";​  }​}​class Context {​  private State state;​  public Context() {​    state = null;​  }​  public void setState(State state) {​    this.state = state;​  }​  public State getState() {​    return state;​  }​}​public class Main {​  public static void main(String[] args) {​    Context context = new Context();​    StartState startState = new StartState();​    startState.doAction(context);​    System.out.println(context.getState().toString());​    PlayState playState = new PlayState();​    playState.doAction(context);​    StopState stopState = new StopState();​    stopState.doAction(context);​    System.out.println(context.getState().toString());​  }​} |

The code above generates the following result.

Output

| ![](image_rsrc28D.jpg) |

9.  Strategy Pattern

In Strategy pattern, an algorithm can be changed at run time.

Strategy pattern is a behavior pattern.

In Strategy pattern, we create objects to represent various algorithms and a context object to run the algorithm.

The strategy object changes the algorithm on the context object.

Lab – 21

| interface MathAlgorithm {​   public int calculate(int num1, int num2);​}class MathAdd implements MathAlgorithm{​   @Override​   public int calculate(int num1, int num2) {​      return num1 + num2;​   }​}class MathSubstract implements MathAlgorithm{​   @Override​   public int calculate(int num1, int num2) {​      return num1 - num2;​   }​}class MathMultiply implements MathAlgorithm{​   @Override​   public int calculate(int num1, int num2) {​      return num1 * num2;​   }​}​class MathContext {​   private MathAlgorithm algorithm;​   public MathContext(MathAlgorithm strategy){​      this.algorithm = strategy;​   }​   public int execute(int num1, int num2){​      return algorithm.calculate(num1, num2);​   }​}public class Main {public static void main(String[] args) {MathContext context = new MathContext(new MathAdd());   System.out.println("10 + 5 = " + context.execute(10, 5));context = new MathContext(new MathSubstract());   ​ System.out.println("10 - 5 = " + context.execute(10, 5));context = new MathContext(new MathMultiply());   ​ System.out.println("10 * 5 = " + context.execute(10, 5));​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc28E.jpg) |

10.  Template Pattern

In Template pattern, a parent abstract class expose several abstract methods for the subclass to implement. In the parent abstract class there is another method or several methods which uses the abstract methods to achieve business logics.

The abstract methods usually are for each step required by the parent class.

For example, in order to use a new software we need to download, install, configuration, and run. If we are going to use template pattern to code the logic we would create a parent class as follows.

| abstract class UseSoftware{​   abstract void download();​   abstract void install();​   abstract void configuration();​   abstract void run();​   public void useNewSoftware(){​     download();​     install();​     configuration();​     run();  ​   }​} |

For using different software we just need to inherit from the abstract class above and provide the detailed implementation.

Template pattern is a behavior pattern.

Lab – 22

| abstract class Software {​   abstract void initialize();​   abstract void start();​   abstract void end();public final void play(){​      //initialize​      initialize();​      //start​      start();​      //end​      end();​   }​}class Browser extends Software {​   @Override​   void end() {​      System.out.println("Browser Finished!");​   }​   @Override​   void initialize() {​      System.out.println("Browser Initialized!.");​   }​   @Override​   void start() {​      System.out.println("Browser Started.");​   }​}class Editor extends Software {​   @Override​   void end() {​      System.out.println("Editor Finished!");​   }​   @Override​   void initialize() {​      System.out.println("Editor Initialized!");​   }​   @Override​   void start() {​      System.out.println("Editor Started!");​   }​}public class Main {​   public static void main(String[] args) {​      Software s1 = new Browser();​      s1.play();​      s1 = new Editor();​      s1.play();   ​   }​} |

The code above generates the following result.

Output

| ![](image_rsrc28F.jpg) |

11.  Visitor Pattern

In visitor pattern, element object accepts the visitor object and visitor object handles the operation on the element object.

This pattern is a behavior pattern.

By this way, execution algorithm of element can be changed from different visitors.

Lab – 23

| class TreeNode {​  private String name;​  public TreeNode(String name) {​    this.name = name;​  }​  public String getName() {​    return name;​  }​  public void accept(NodeVisitor v) {​    v.visit(this);​  }​}​interface NodeVisitor {​  public void visit(TreeNode n);​}class ConsoleVisitor implements NodeVisitor {​  @Override​  public void visit(TreeNode n) {​    System.out.println("console:" + n.getName());​  }​}​class EmailVisitor implements NodeVisitor {​  @Override​  public void visit(TreeNode n) {​    System.out.println("email:" + n.getName());​  }​}​public class Main {​  public static void main(String[] args) {​    TreeNode computer = new TreeNode("abd");​    computer.accept(new ConsoleVisitor());​    computer.accept(new EmailVisitor());​  }​} |

The code above generates the following result.

Output

| ![](image_rsrc28G.jpg) |

12.  MVC Pattern

MVC Pattern stands for Model-View-Controller Pattern.

From the name we can see that the MVC pattern involves three parts:

Model - Model represents an object carrying data. It can also have logic to update controller if its data changes.

View - View represents the visualization of the data that model contains. Usually it has the UI logic.

Controller - Controller references both Model and view. It controls the data flow into model object and updates the view whenever data changes. It keeps View and Model separate.

Lab – 24

| class Employee {​  private String id;​  private String name;​  public String getId() {​    return id;​  }​  public void setId(String id) {​    this.id = id;​  }​  public String getName() {​    return name;​  }​  public void setName(String name) {​    this.name = name;​  }​}​class EmployeeView {​public  void printEmployeeDetails(String name, String no) {​    System.out.println("Employee: ");​    System.out.println("Name: " + name);​    System.out.println("ID: " + no);​  }​}​class EmployeeController {​  private Employee model;​  private EmployeeView view;​ public EmployeeController(Employee model, EmployeeView view) {​    this.model = model;​    this.view = view;​  }​  public void setEmployeeName(String name) {​    model.setName(name);​  }​  public String getEmployeeName() {​    return model.getName();​  }​  public void setEmployeeId(String rollNo) {​    model.setId(rollNo);​  }​  public String getEmployeeId() {​    return model.getId();​  }​  public void updateView() {​    view.printEmployeeDetails(model.getName(), model.getId());​  }​}​public class Main {​  public static void main(String[] args) {​    Employee model = new Employee();​    model.setName("Tom");​    model.setId("1");​    EmployeeView view = new EmployeeView();​    EmployeeController controller = newEmployeeController(model, view);​    controller.updateView();​    controller.setEmployeeName("New Name");​    controller.updateView();​  }​} |

The code above generates the following result.

Output

| ![](image_rsrc28H.jpg) |

Chapter 5 :

Data Access Object Pattern

Data Access Object Pattern or DAO pattern separates data accessing API from high level business services.

A DAO pattern usually has the following interface and classes.

*   Data Access Object Interface defines the standard operations on a model object(s).
*   Data Access Object class implements above interface. There could be more than one implementations, for example, one for database, one for file.
*   Model Object Simple POJO containing get/set methods to store data.

Lab – 25

| import java.util.ArrayList;import java.util.List;class Employee {private String name;private int id;Employee(String name, int id) {this.name = name;this.id = id;}public String getName() {return name;}public void setName(String name) {this.name = name;}public int getId() {return id;}public void setId(int id) {this.id = id;}}interface EmployeeDao {public List<Employee> getAll();public Employee get(int id);public void updateStudent(Employee student);public void delete(Employee student);}class EmployeeDaoImpl implements EmployeeDao {List<Employee> employeeList;public EmployeeDaoImpl() {employeeList = new ArrayList<Employee>();Employee emp1 = new Employee("Jack", 0);Employee emp2 = new Employee("Tom", 1);employeeList.add(emp1);employeeList.add(emp2);}@Overridepublic void delete(Employee student) {employeeList.remove(student.getId());System.out.println("Employee: No " + student.getId()+ ", deleted from database");}@Overridepublic List<Employee> getAll() {return employeeList;}@Overridepublic Employee get(int rollNo) {return employeeList.get(rollNo);}@Overridepublic void updateStudent(Employee emp) {employeeList.get(emp.getId()).setName(emp.getName());System.out.println("Emp:No " + emp.getId()+ ", updated in the database");}}public class Main {public static void main(String[] args) {EmployeeDao empDao = new EmployeeDaoImpl();for (Employee emp : empDao.getAll()) {System.out.println("Emp: [No : " + emp.getId() + ",Name : "  + emp.getName() + " ]");}Employee emp = empDao.getAll().get(0);emp.setName("Jane");empDao.updateStudent(emp);empDao.get(0);System.out.println("Emp: [No : " + emp.getId() + ",Name : " + emp.getName() + " ]");}} |

The code above generates the following result.

Output

| ![](image_rsrc28J.jpg) |