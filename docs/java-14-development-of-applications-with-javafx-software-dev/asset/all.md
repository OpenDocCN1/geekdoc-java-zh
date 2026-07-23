### Poul Klausen

# Java 14: Development of applications with JavaFX

Software Development

Java 14: Development of applications with JavaFX: Software Development

1st edition

© 2018 Poul Klausen & [bookboon.com](http://bookboon.com)

ISBN 978-87-403-2188-3

Peer review by Ove Thomsen, EA Dania

# Foreword

This book is the fourteenth in a series of books on software development and deals with JavaFX. The book introduces JavaFX as an alternative to Swing and Java2D, thus treating how to work with 2D graphics in JavaFX, as well as the main components and layout. The goal is that you will quickly be able to write programs with a graphical user interface using JavaFX. There are many topics, especially JavaFX properties, which the book does not include, but these topics are dealt with in the following book. JavaFX is intended as an alternative to Swing, and it is especially for better graphics and other media used in the user interface. With JavaFX, it is easier to develop applications with a modern user interface and with all the possibilities that users expect and get used to from web applications. The book does not require the reader to know Swing and Java2D in detail, but assumes that the reader has an introductory knowledge of developing programs with a graphical user interface.

As the title says this series of books deals with software development, and the goal is to teach the reader how to develop applications in Java. It can be learned by reading about the subject and by studying complete sample programs, but most importantly by yourself to do it and write your own programs from scratch. Therefore, an important part of the books is exercises and problems, where the reader has to write programs that correspond to the substance being treated in the books. All books in the series is built around the same skeleton and will consist of text and examples and exercises and problems that are placed in the text where they naturally belongs. The difference between exercises and problems is that the exercises largely deals with repetitions of the substance that is presented in the text, and furthermore it is relatively accurately described what to do. Problems are in turn more loosely described, and are typically a little bigger and there is rarely any clear best solution. These are books to be read from start to finish, but the many code examples, including exercises and problems plays a central role, and it is important that the reader predict in detail studying the code to the many examples and also solves the exercises and problems or possibly just studying the recommended solutions.

All books ends with one or two larger sample programs, which focus primarily is on process and an explanation of how the program is written. On the other hand appears the code only to a limited extent - if at all - and the reader should instead study the finished program code perhaps while testing the program. In addition to show the development of programs that are larger than the examples, which otherwise is presented, the aim of the concluding examples also is to show program examples from varying fields of application.

Most books also ends with an appendix dealing with a subject that would not be treated in the books. It may be issues on the installation of software or other topics in computer technology, which are not about software development, but where it is necessary to have an introductory knowledge. If the reader already is familiar with the subject, the current appendix can be skipped.

The programming language is, as mentioned Java, and besides the books use the following products:

1.  NetBeans as IDE for application development
2.  MySQL to the extent there is a need for a database server (from the book Java 6 onwards)
3.  GlassFish as a web server and application server (from the book Java 11 onwards)

It is products that are free of charge and free to install, and there is even talk about products, where the installation is progressing all by itself and without major efforts and challenges. In addition, there are on the web detailed installation instructions for all the three products. The products are available on Windows and Linux, and it therefore plays no special role if you use Linux or Windows.

All sample programs are developed and tested on machines running Linux. In fact, it plays no major role, as both Java and other products work in exactly the same way whether the platform is one or the other. Some places will be in the books where you could see that the platform is Linux, and this applies primarily commands that concerning the file system. Otherwise it has no meaning to the reader that the programs are developed on a Linux machine, and they can immediately also run under Windows unless a program refers to the file system where it may be necessary to change the name of a file.

Finally a little about what the books are not. It is not "how to write" or for that matter reference manuals in Java, but it is as the title says books on software development. It is my hope that the reader when reading the books and through the many examples can find inspiration for how to write good programs, but also can be used as a source collection with a number of examples of solutions to concrete everyday programming problems that you regularly face as a software developer.

# 1 Introduction

In the books Java 2, Java 9 and primarily Java 10, I have dealt with how to write a standalone Java application with a graphical user interface. All of it has been based on Swing, which is an API that makes the necessary available through a comprehensive class library. There is nothing wrong with Swing, and it will be there many years to come, among other things because there are a lot of programs based on Swing. However, there are alternatives and one of them is called *JavaFX*, as the new API for developing Java applications with a graphical user interface.

JavaFX is intended as an alternative to Swing, and it is especially for better graphics and other media used in the user interface. With JavaFX, it is easier to develop applications with a modern user interface and with all the possibilities that users expect and get used to from web applications. However, it is important to emphasize that you can still use Swing components, so that all known facilities from Swing are still available.

JavaFX is an alternative to Swing, but the idea actually originates from World Wide Web, where you can build the user interfaces using markup, and to a large extent you can design the applications user interface using styles. The goal of this book is to show how to use JavaFX, and I will alone look at the development of standalone applications, but the goal of JavaFX is also the development of the client side of web application, which means that a JavaFX application can be opened as

1.  a standalone desktop application
2.  with the *Java Web Start* tecnology
3.  as a part of a web page

For the time being, I will only look at the first option.

## 1.1 HelloFX

As a start, I will show a very simple application that opens a window with a few buttons and a little more, but a program that uses JavaFX instead of Swing. I start with a new project in Netbeans, but it must be a *JavaFX Application* project. I have called the project *HelloFX*, and after the project has been created, NetBeans has created a single class (where I have removed all comments):

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_8.jpg)

In fact, it is a fully finished program, and starting the program opens the following window:

![](image/Image1760.jpg)

and clicking on the button it prints a message on the console. If you consider the code, first notice that the class inherits *Application*, which means that it is a *JavaFX* application. The class has a usual *main()* method as other Java applications, and it starts by calling a static method *launch()* (in the class *Application*). It basically performs the following:

1.  instantiates an object of the class (here the class *HelloFX*)
2.  performs a method *init()*, which in *Application* is an empty method
3.  performs a method *start()*, which in *Application* is an empty method
4.  waiting until the program terminates, where method *stop()*, as in *Application* is an empty method, is performed

If you want an application to open a window, it usually happens to override the method *start()* from the class *Application*, as is the case in the above example.

A JavaFX program basically consists of a *Stage* object that contains a *Scene* object, which again contains *Node* objects arranged in a tree. A *Stage* object represents a window and the primary *Stage* object is created by the runtime system and is sent as a parameter to the method *start()*, and in the above example it has the name *primaryStage*. A *Scene* object contains all of the window’s objects organized into a tree called a *scene graph*. The tree’s elements are *Node* objects, and a node can be an *branch node* (which has children) or a *leaf node* (which no children have). A node is a component in the window and may, for example, be a button or an entry field.

In the example above, the method *start()* begins by creating a button, which is a node. The object is called *btn*, and besides attaching a text to the button, an action is also associated, which is an object with a single method, which simply performs a *System.out.println()*. You should note that it looks like a usual event handling as it is known from Swing, but it is not the case, and other types are used, although they have the same names as some of the known types from Swing.

As a next step, a *root* object of the type *StackPane* is created, and it is the root of the scene graph and the button is inserted as a child to *root*. This program thus has a very simple scene graph consisting of a root and a single leaf node. The root object is then added to a *Sceen* object, which represents the window’s content, while defining the window size. This *Scene* object must be attached to the *Stage* object, which is also assigned a title, and finally, the method *show()* is performed on the object *primaryStage*, which displays the window on the screen.

It is thus easy to follow what happens in the above program, but it is more difficult to spot the benefits. They come later, but I can immediately point out that one of the advantages is that the technology used to draw the window with all its content is extremely effective.

Before I leave this example, I will change the code a bit (for now, the code appears as NetBeans has created it). I have changed the code to the following:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_10.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_11.jpg)

If you run the program, it first writes the following lines on the console:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_111.jpg)

after which you get the following window

![](image/Image1767.jpg)

If you enter the text *Frode Fredegod* and click *Hello*, the window will be updated to:

![](image/Image1776.jpg)

and clicking *Exit* terminates the program after writing the following text on the console:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_13.jpg)

This time, the method *start()* creates a scene graph with a *root* that has 5 leaf nodes. Note that the type of *root* is *VBox*. There is no particular justification in addition to showing that there are more options, and the type is relevant to how the graph’s nodes are laid out in the window. The 5 nodes have the types *Label*, *TextField*, *Label*, *Button* and *Button*, where the first and the last are created when they are added to *root* (the last created of the method *createButton()*), while the other three are created explicitly.

Note that the method *start()* starts by printing a text (on the console). I have also overwritten the two methods *init()* and *stop()* so they both print a text and finally I have added a default constructor. They show that the constructor is first executed, then *init()* and finally *start()*. Finally, they show that the method *stop()* is executed when the program terminates. Here you should note that the constructor, *start()* and *stop()* are executed in the same thread (called the *JavaFX Application Thread* ), while *init()* is performed in its own thread (called the *JavaFX Launcher*).

If you look at the directory *dist*, you can see that a jar file named *HelloFX.jar* has been created in the usual way, and the program can therefore be executed from the command line as (if current directory is the folder *dist*):

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_131.jpg)

The directory *dist* also contains other files:

![](image/Image1784.jpg)

These files I do not want to mention in this place, but they all have to do with the execution of the program as a web application.

## 1.2 HelloLines

As another example of a JavaFX program, I will show an example that opens the following window:

![](image/Image1791.jpg)

The project is called *HelloLines*, and the window contains a scene graph, consisting of a root with 4 child nodes: a *Text* object and three *Line* objects. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_14.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_15.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_16.jpg)

When you see the code, it is easy enough to understand and looks like the first example. The class defines an array of *Line* elements (a *Line* object represents a straight line), and the array is created in the constructor so that it contains three *Line* objects. A *Line* object is created using the method *createLine()*, in which you should especially note how an object is initialized and what types are used. There is also a method *createText()*, which creates and returns a *Text* object. If you consider the types used to create *Line* and *Text* objects, it is not the same types that you know from *Java2D*, but they have the same names and basically have the same characteristics. The scene graph is created in the same way as in the previous example in the method *start()*, but this time the type of the *root* element is *Group*, which is the basic type for a branch node. You should especially note how with *getChildren()* to get a list with all child nodes.

The example is simple, but you should note how geometric objects and text elements are included in the scene graph as nodes in the same way as other nodes such like *Button*, *Label*, and more.

# 2 Architecture of JavaFX

JavaFX is a full API for creating GUI applications and consists of classes distributed on the following packages:

1.  *javafx.animation*
2.  *javafx.application*
3.  *javafx.css*
4.  *javafx.event*
5.  *javafx.geometry*
6.  *javafx.stage*
7.  *javafx.scene*

where the latter has more sub packages. A JavaFX program consists as mentioned of a scene graph, which is a tree containing nodes that may be

*   geometrical objects, that can be 2D and 3D objects, as *Circle*’s, *Sphere*’s and so on
*   UI controls, such as *Label*, *Button* and so on
*   Containers, as *StackPane*, *VBox*, *Group* and more
*   Media elements, for images, audio and video

Each node in a scene graph has a unique parent, except the root, which has no parent, and all nodes that do not have child nodes are called as mentioned for leaf nodes, while all other nodes are called branch nodes. The same node can only occur in the tree once, and each node may have defined effects, opacity, transforms, and event handlers.

To render the graphics JavaFX uses *openGL* (on Linux systems) and, as far as possible, use the graphics card’s hardware accelerator with the result that JavaFX is highly effective in rendering graphics.

As mentioned above, a JavaFX application is represented by a *Stage* object that contains all of the application’s objects, and the *Stage* object is created by the actual platform. A *Stage* object has a width and a height in addition to the content (the scene graph), and there are decorations as a *title line* and a *frame*. There are the following kind of *Stage* objects:

*   *Decorated*
*   *Undecorated*
*   *Transparent*
*   *Unified*
*   *Utility*

and the individual objects are discussed continuously in connection with the examples.

The *Stage* object’s content is represented by a *Scene* object, which defines the width and height as well as the scene graph. The individual nodes are discussed in connection with the examples, and there are many with each there purpose. Among other things, there are different branch nodes, where the simplest is a *Group* node, which is primarily a collection of child nodes. Other examples are *Pane* nodes with several specific derivative classes, which play the same role as layout managers in Swing. All the specific nodes are part of a hierarchy of class’s and are derived from one of the following classes:

![](image/Image1799.jpg)

## Exersice 1

You must write a JavaFX application that opens the following window, where there are two entry fields at the top and at the bottom of a list box:

![](image/Image1808.jpg)

If you click the *Add* button, (and something has been entered in both fields), a line must be inserted in the list box where the name and title are separated by comma. If you click on the other button, the content of the list box must be deleted. It is a requirement that the size of the two input fields as well as the size of the list box follows the size of the window and that the buttons follow the edge of the window.

Below is the window after 6 people have entered. Note that it is a part of the task to find out which controls are to be used and how to place them in the window:

![](image/Image1815.jpg)

# 3 2D Shapes

In this chapter I will review how to draw geometric shapes in a window, and as may be seen in the last example of chapter 1, it is almost the same as in Java2D, only other classes are used. A geometric shape is an object of the type *Shape2D*, and thus an object that is a node and can be included in a scene graph. Generally, there are the following predefined shapes (nodes):

*   *Line*
*   *Rectangle*
*   *Circle*
*   *Ellipse*
*   *Polygon*
*   *Polyline*
*   *CubicCurve*
*   *QuadCurve*
*   *Arc*

In addition, you can define general curves as *Path* objects consisting of segments of the types:

*   *Line*
*   *CubicCurve*
*   *QuadCurve*
*   *Arc*

and finally you can define a shape like a *SVG Path*.

The aim of this chapter is to show how to create and apply the above geometric shapes, but instead of reviewing the syntax (which is a lot about what you know from Java2D), I will instead formulate a series of exercises where the challenge is primarily to find out of what the types are called JavaFX.

## Exercise 2

Write a JavaFX application that opens the following window:

![](image/Image1823.jpg)

The blue line has the endpoints (20, 20) and (320, 20) and width 21, while the red line has the endpoints (20, 40) and (320, 40) and width 1\. Finally, the green line has the endpoints (20, 60) and (320, 60) and width 21.

## Exercise 3

Write a JavaFX program that opens the following window:

![](image/Image1831.jpg)

which shows three rectangles, each of which has a size of 300 × 50\. The left upper corner of the three rectangles are (20, 20), (20, 90) and (20, 160) respectively. The top has a blue frame with a width of 21, but an empty inner. The middle has no frame, while the latter has a black frame with the width 1.

## Exercise 4

Write a program that shows a window with three rectangles with rounded corners:

![](image/Image1838.jpg)

Note that JavaFX does not have a type for rectangles with rounded corners, and the shapes are of the type *Rectangle*.

## Exercise 5

Write a JavaFX program that opens the following window:

![](image/Image1848.jpg)

when the type of the shapes must be *Circle*.

## Exercise 6

Write a program that opens the following window:

![](image/Image1855.jpg)

where the type of the three shapes are *Ellipse*.

## Exercise 7

A polygon is a closed shape bounded by straight lines, and you defines a polygon by specifying the coordinates of the corners. Write a JavaFX program that opens the following window, which shows three polygons:

![](image/Image1862.jpg)

## Exercise 8

A polyline is defined as a polygon and consists of straight lines. The shape is defined in the same way as a sequence of corners, but there is no need to be a coherent shape. Generally, a polyline is not a filled shape, but if you define a fill color, the shape is filled as a polygon. In this exercise, you must write a program that opens the following window with 4 polyline shapes:

![](image/Image1870.jpg)

## Exercise 9

You must write a program that shows two *quad curves*. If you do not remember the definition of a *quad curve*, you might want to read about the curve in the book Java 10\. The program must open the following window:

![](image/Image1877.jpg)

## Exercise 10

You must write a program that shows two *cubic curves*. If you do not remember the definition of a *cubic curve*, you might want to read about the curve in the book Java 10\. The program must open the following window:

![](image/Image1885.jpg)

## Exercise 11

Write a program that opens the window below, showing 6 circle/ellipse slices. All slices start at 0 and span over an angle of 60 degrees. The top three are circle sections from a circle with radius 100, while the three bottom are slices of an ellipse with radiuses 200 and 100:

![](image/Image1892.jpg)

## 3.1 SVG

SVG stands for *Scalable Vector Graphics*, and in relation to JavaFX, you define a shape in the form of a path as a string containing commands. There are the following commands where the cursor denotes the drawing tool:

1.  *M* or *m*, which means *move to*. As a result, the cursor is moved to the following coordinate. Is the command *M*, the coordinates designate an absolute position, and is the command *m*, the coordinates denote a relative position. If you indicate more coordinates, they are perceived as multiple subsequent move to operations.
2.  *Z* or *z*, which means *close* and closes the path with a straight line from the current position of the cursor to the start of the curve.
3.  *L* or *1*, which means *line to*. As a result, the cursor draws a straight line from the current point to the subsequent coordinate. If the command is *L*, the coordinates denote an absolute position and is the command *l*, the coordinates denote a relative position. If you indicate more coordinates, they are perceived as several subsequent line to operations.
4.  *H* or *h*, which means *horizontal to*. As a result, the cursor draws a horizontal line from the current point to the following x-coordinate. Is the command *H*, the coordinates designate an absolute position and is the command *h*, the coordinates denote a relative position. If you specify multiple x coordinates, they are perceived as multiple subsequent horizontal to operations.
5.  *V* or *v*, which means *vertical to*. As a result, the cursor draws a vertical line from the current point to the following y coordinate. If the command is *V*, the coordinates denote an absolute position and is the command *v*, the coordinate denotes a relative position. If you specify more y coordinates, they are perceived as multiple subsequent vertical to operations.
6.  *C* or *c*, which means *cubic to*. As a result, the cursor draws a cubic curve from the current point to the last of the following three coordinate pairs. The first two are control points. Is the command *C*, the coordinates designate an absolute position, and is command *c*, the coordinates denote a relative position. If you specify more coordinate sets, they are perceived as several subsequent curve to operations.
7.  *Q* or *q*, which means *quad to*. As a result, the cursor draws a quad curve from the current point to the last of the following two coordinate pairs. The first is the control point. Is the command *Q*, the coordinates designate an absolute position and is the command *q*, the coordinates denote a relative position. If you specify more coordinate sets, they are perceived as several subsequent quad to operations.
8.  *A* or *a*, which means *arc to*. The result is that the cursor draws an arc starting in the current point to (x, y). The parameters are (*rx row rotation large sweep x y*), where *rx* and *row* are radii in an ellipse and rotation is the ellipse rotation about the x-axis. The two parameters *large* and *sweep* indicate which of the two arcs to be selected, and the center of the ellipse is calculated automatically from the parameters. Is the command *A*, the coordinates designate an absolute position and is the command *a*, the coordinates denote a relative position. If you specify more parameter sets, they are perceived as several subsequent arc to operations.

As an example, below is shown an application that opens the following window:

![](image/Image1900.jpg)

which shows two shapes, both of which have the type *SVGPath*. Both shapes are drawn with two *line to* commands and an *arc to* command. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_30.jpg)

Here is the interesting of course the two SVG commands. You must note the syntax and how the commands are simply defined as a list separated by spaces. The only thing that is not obvious is command *A*, which defines an arc. In this case, it is (in the first case) a curve from (120, 120) to (20, 120) in a circle of radius 100 and it offers two options:

![](image/Image1909.jpg)

Which one chooses is determined by the two parameters *large* and *sweep* (whose values are 0 or 1).

## Exercise 12

Write a program that opens the following window, which shows two *SVGPath* shapes where the blue curve consists of a *move to*, two *line to* and an *arc to* operation, while the red consists of one *quad to*, two *line to*, one *cubic to* and a *close* operation:

![](image/Image1920.jpg)

## 3.2 A Path

Instead of drawing a path as shown above, where you defines the drawing operations as a string, you can add drawing objects to a *Path* object that represents a collection of drawing objects. The advantage is primarily that the compiler can check the syntax and that any errors are thus detected before runtime. There are the following drawing objects:

*   *MoveTo*
*   *LineTo*
*   *HLineTo*
*   *VLineTo*
*   *ArcTo*
*   *QuadCurveTo*
*   *CubicCurveTo*

For example, the following program draws the same window as shown in the previous example:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_33.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_34.jpg)![](image/Image1935.jpg)

In fact, there is not much to explain, but you should notice how to create a *Path* object and how to add drawing objects. Also note how to create each drawing object, and that the objects are used in the order as they are added to the *Path* object.

## Exercise 13

You must write a program that opens the same window as in exercise 12, but this time the type of the two shapes must be a *Path*.

## Exercise 14

Write a program that opens the following window when the shape should be a *Path* object:

![](image/Image1942.jpg)

## 3.3 Shape properties

The above has primarily concerned the shape of figures like straight lines, rectangles, circles, and more, but there are also some other properties attached to shapes, including how they are filled and how the perimeter is drawn. This section will discuss the most important of these features.

The perimeter – which is a line / curve – can be drawn in three ways:

1.  *StrokeType.CENTERED*, which is default and means the perimeter is drawn so that the edge of the shape is exactly the center of the perimeter line.
2.  *StrokeType.INSIDE*, where the perimeter is drawn as it falls within the shape.
3.  *StrokeType.OUTSIDE*, where the perimeter is drawn outside the shape.

The program *StrokeProgram* opens the following window, which illustrates the three ways to draw the perimeter and where the first is the default:

![](image/Image1950.jpg)

The code is the following, where I have only shown the method *start()*:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_36.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_37.jpg)

Another thing is the endpoints of the line and here especially for shapes composed of straight lines, such as polygons. There are three options (as you also know from Java2D):

1.  *StrokeLineJoin.MITTER* which is default
2.  *StrokeLineJoin.BEVEL*
3.  *StrokeLineJoin.ROUND*

You can find the exact explanation of how these endpoints are calculated in the book about Java2D. The application *JoinProgram* opens the following window, which shows the effect of each of the three options:

![](image/Image1957.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_371.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_38.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_39.jpg)

There are similar options for specifying endpoints of lines (please check the book Java 10 for an explanation):

1.  *StrokeLineCap.BUTT*
2.  *StrokeLineCap.SQUARE*
3.  *StrokeLineCap.ROUND*

## Exercise 15

Write a program that you can call *LineCaps*. The program must open the following window, which shows 6 *Line* objects (each of which has a length of 200), and each endpoint (of the blue lines) is *BUTT*, *SQUARE* and *ROUND* respectively:

![](image/Image1965.jpg)

## 3.4 Shape operations

In general, if you add two *Shape* objects to a *Group* and the two shapes overlap, then the shape added last will cover the part of the first shape that overlaps. The *Shape* class has three static methods

*   *union()*
*   *intersect()*
*   *subtract()*

which all as parameters have two *Shape* objects and the methods combine these two objects into a single *Shape* object. The *OperationProgram* shows how to apply this operation and opens the following window:

![](image/Image1972.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_41.jpg)

# 4 Text

Text can be represented by a *Text* object, and the important thing is that *Text* inherits *Shape* and thus can be used as any other *Shape* object and enter the scene graph as a node. In reality, there is not much to explain, but the application *TextProgram* opens the following window:

![](image/Image1980.jpg)

It works almost the same way you know from Java2D, but other classes are used. The completed code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_43.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_44.jpg)

The top text is created by the method *text1()* as a *Text* object. Here you should note that the constructor as parameters has the coordinates of the text and that the coordinates indicate the left end of the baseline (the line on which the text is “on”). Otherwise, you should especially note how to create a font. This happens with a static method *font()* in the class *Font* as well as two enumerations *FontWeight* and *FontPosture*.

The method *line()* has a *Shape* object as parameter, and the method creates a *Line* object that corresponds to the baseline of the text created in *text1()*. Here you should especially note the method *getBoundsInLocal()*, which returns a *Bounds* object (defined in the package *javafx.geometry*) that contains the *Shape* object width and height as well as its location, and thus the circumscribing rectangle. Regarding the latter, it is not a (x, y) value, but instead the smallest and largest x and y value that may occur, respectively.

The method *getBoundsInLocal()* returns the circumscribing rectangle before any transformation. There is also a method *getBoundsInParent()* that returns the circumscribing rectangle after a transformation. In this case, *Bounds* uses alone the object to determine the length of the line to be drawn.

The method *text2()* creates a *Text* object for the lower text. Since a *Text* object is also a *Shape* object, you can indicate both fill and stroke just like other shape objects. In this case, the location of the object is not defined by the constructor, but it is only to show that there are other options. In particular, note how to indicate that the text needs to be underlined.

Finally, there is method *rect()* that returns the circumscribing rectangle for the last text, and here you should primarily note how the rectangle is defined using a *Bound* object.

# 5 Effects

A JavaFX program, as mentioned, represents the content of the user interface as nodes in a scene graph. It is possible to change how the individual nodes are displayed using so-called effects, where an effect is an object that is used to modify how a node is to be drawn. It is primarily interesting for nodes, which represent graphic objects like images and geometric figures. This chapter is a brief introduction to these effects. Basically, the following effects are represented as classes in the package *javafx.scene.effect* :

*   *ColorAdjust*, which can be used to modify the color of an image where you can adjust the hue, saturation, brightness and contrast.
*   *ColorInput*, which corresponds to drawing a rectangle, filled with a color.
*   *ImageInput* used to fill a rectangular area with an image.
*   *Blend*, which is used to combine pixels from two inputs.
*   *Bloom*, which is used to provide a portion of a node more hue.
*   *Glow*, which is used to increase the hue of a node.
*   *BoxBlur*, used to perform a blur operation on a node with a box filter.
*   *GausienBlur*, also used to perform a blur of a node, but instead using a kernel.
*   *MotionBlur*, which is a gaussien blur, where there is also an angle.
*   *Reflection* that performs a reflection of a node.
*   *SepiaTone*, which tones a node with a brownish color.
*   *Shadow*, resulting in a shadow effect by a blur of edges.
*   *DropShadow*, where the shadow effect is created behind the node.
*   *InnerShadow*, where the shadow effect is created within the edge of the node.
*   *Lighting*, which is used to simulate a light effect, where you can indicate a light source such as point, distance or sport.
*   *Light.Distant*, which is a variant of Lighting.
*   *Light.Spot*, which is a variation of Lighting.
*   *Point.Spot*, which is a variation of Lighting.

As an example I show a program that adjusts the colors of an image. The program is named *ColorAdjustProgram* and opens the following window:

![](image/Image1987.jpg)

where the left image is the original, while the right is the adjusted image. The program should show only the syntax for using a *ColorAdjust*, but in this case does not result in any improvement of the image. The program also shows how to load a picture from the local disk into a JavaFX program. The program code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_47.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_48.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_49.jpg)

The image is loaded in the method *start()* and is usually done by defining a path to the image, which is a *jpg* image. In this case, the image is placed in a directory *data* under my home directory, but the image is also part of the book’s zip file with examples. The only difference with regard to the file name is that it starts with the name of the protocol as the image is located in the local file system. In other cases, it would be the *http* protocol. The image is loaded by creating an *Image* object.

An image is inserted into the program’s scene graph as an *ImageView* object, and the method *image1()* creates an *ImageView* object for the original image and specifies the coordinates of the image’s upper left corner. In addition, you specify the width of the image, and that its propositions can not be changed.

The method *image2()* correspondingly creates another *ImageView* object for the same image, but this time with other coordinates. In addition, a *ColorAdjust* object is created that has methods for adjusting lightness, contrast, saturation and tint. The parameters have values between -1 and 1, where a negative value means reducing the property while a positive value means increasing the property.

## Problem 1

![](image/Image1995.jpg)

Write a program that opens the window above. The goal is that you can experiment with the four properties: Light, contrast, hue and saturation. The picture is called *stone.jpg* and is contained in the book’s zip file. You must be able to adjust the four properties using the *Slider* controls at the top of the window. This means that you should handle the event that is firing when moving the slider. This happens with a *ChangedListener*, which is defined in the *javafx.beans.value* package.

## 5.1 Colors

In the above examples (and also the exercises from the previous chapters) I have used colors and shown how to fill a shape with a color and draw the perimeter. Generally there are four options:

1.  a uniform color and then objects of the class *Color*
2.  a linear gradiant paint and then objects of the class *LinearGradian*
3.  a radial gradiant paint and then objects of the class *RadialGradiant*
4.  an image and then objects of the class *ImagePattern*

The program *ColorProgram* opens the following window:

![](image/Image2004.jpg)

The program’s scene graph has 8 nodes, which are 4 *Text* nodes and 4 *Circle* nodes, respectively. A text node is created using the following method:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_51.jpg)

The parameters are the text, the coordinates of the shape’s position and the colors to fill the figure and draw the perimeter respectively. You should note that a color may be one of the above four options, each of which has the type *Paint* as the base type.

A circle is created using the following method:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_52.jpg)

Here the parameters means the same as for a text node.

The window shows four figures, each character consisting of a *Text* node and a *Circle* node. The first is drawn using uniform colors, where there is nothing to say in relation to what has already been said about colors. The next figure uses a linear gradient paint, which is defined as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_53.jpg)

A linear gradient paint is defined by two or more colors, which are defined as objects of the type *Stop*. Each stop indicates a color and a position that can either be relative or absolute. The first color stop is in this case blue and the position is 0, which means that the color is the start color. The other color is red and the position is 1, which means that the last color value must be red. All colors between these two extremes are blends of blue and red.

The *LinearGradient* parameters are the starting position (here (0.0)) and the final position (here (1.0)), and the next parameter indicates that the coordinates must be interpreted relative (*true*) or absolute. In this case, the coordinates indicate that they must be mixed along the x axis from the left edge of the shape to the right edge of the shape. The next last parameter indicates whether the pattern should be repeated if the coordinates do not define the entire shape, and finally the last parameter is the color stops.

A radial gradient paint is defined in almost the same way:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_531.jpg)

Again, two or more color stops must be defined, and in this case three are defined. They say that starting with a white color, and after 20% the color should be red for the last to be blue. Parameters for a *RadialGradient* begins by defining a starting point, which is the focus point and is the first stop. The first parameter is the angle of this focus point, while the next is the distance to the focus point. The next two parameters are the coordinates of the focus point, while the next is the radius of a circle that defines the area that the *Paint* object is about. The last three parameters means the same as for a *LinearGradient*.

Finally, there is an *ImagePattern*, which is a *Paint* object that draws an image. In the program’s *start()* method an image (*Bean.png*) is loaded as an *Image* object. This image can then be used to create an *ImagePattern* object:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_54.jpg)

In addition to the image, the parameters are the starting coordinate of the figure (upper left corner), the width and height of the figure (the figure is scaled to this size), and whether the coordinates should be interpreted relative or absolute.

## 5.2 Images

In the previous examples, I have already shown how to load an image and display it in a window. Actually, pictures do not have much to do with effects, but some are pictures used in the example above, and there are a few more remarks to add, so therefore a few additional examples.

An image is displayed in a scene graph as an *ImageView* node, and the image itself is represented in the program as an *Image* object and can be loaded from the machine’s hard disk by specifying the path of the image as a parameter to the constructor. The following program is called *ImageViewProgram* and it opens the following window:

![](image/Image2015.jpg)

It is the same image shown three times, and the example should primarily show how to scale an image. The first image (the big one) is unscaled while the two others are scaled. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_55.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_56.jpg)

The image is loaded in the class’ constructor and can then be referred to with the instance variable *image*. The method *createView()* creates an *ImageView* for the image, and it has five parameters, the first two being the coordinates of the *ImageView* object’s upper left corner, while the two next indicate the width and height. The last indicates whether the image’s propositions are to be retained. The statements of the method are easy to interpret, perhaps apart from the meaning of *setEffect()*, but the result is that a frame is drawn outside the image. If no *width* or *height* is specified, these attributes are not set, and the result is that the physical dimensions of the image are applied.

Examining the method *start()* shows that there is no size for the first image. The image size therefore becomes the physical size, which is 400 × 400\. For the next image, the size is set to 100 × 200, and it will be scaled within this frame, but as it is said that the propositions are to be saved, the result is an image that is scaled to 1/4 in both directions and you gets a picture that is 100 × 100\. For the last image, the same size is specified, but the propositions are not preserved, and the image is therefore scaled in both directions, so it will fill 100 × 200.

As the last example concerning images, I will show a program called *PixelProgram*. The program should show how to manipulate the individual pixels in an image. The starting point is the same picture as shown above. Here is a portion of the image’s pixels white (the background), and the program should change the background to black. That is, all white pixels must be changed to black. In general, it is simple, but as it is a jpg image, pixels close to the figure will not be completely white, and it is therefore necessary to allow an uncertainty as to when a pixel is white. Performing the program gives you the result:

![](image/Image2028.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_58.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_59.jpg)

Most importantly, of course, is the method *createImage()*, which returns an *ImageView* with the modified image. First, the width and height of the image are determined, and a memory representation of a picture of the same size is created. The type is *WritableImage* and I have called it *buffer*. Next, a *PixelReader* is defined for the original image, which means that you can refer to the individual pixels in the image. In addition, a *PixelWriter* is created for *buffer* that allows you to modify the buffer’s pixels. Next, the program iterates using the reader over the pixels of the original image (line by line), and for each pixel, the corresponding pixel is updated in *buffer* – either modified or unchanged. Here you should note the method *isWhite()* which tests whether a pixel can be considered white.

## 5.3 Light

In the introduction to this chapter on effects, I have listed the different effects that you can apply, and I have far from illustrating them all (and will not), but I want to conclude this chapter with a little about the effect light. The principle is that a light source shines on a figure, and the color of the figure is determined by the nature of the light source and its position in relation to the figure.

Generally, you can associate a lighting effect to a figure with a *Lighting* object, and if you do not indicate a light source, a default light source is used, which corresponds to the light falling directly into the figure, resulting in a weak 3D effect towards the edge. You can also explicitly indicate a light source, where there are three options:

1.  *Light.Distant*
2.  *Light.Point*
3.  *Ligth.Spot*

The first corresponds to the light source located at a distance, thus sending light that extends in one direction from a remote light source:

![](image/Image2035.jpg)

You can set as a parameter two values (both of the type *double*):

1.  *azimuth*, which indicates the angle of the light source’s rotation about the z axis
2.  *elevation*, which indicates the angle of the light source’s rotation about the x axis

In addition, you can indicate the color of the light source.

The second option is a light source where the light is sent from a certain point, as indicated by 3 coordinates. The light spreads in all directions, and in the same way as a *Distant* light source, you can indicate the color of the light source.

![](image/Image2043.jpg)

The light intensity depends on the distance of the source to the figure. Finally, there is the third option that is similar to the above, but with the difference that you can specify a *specular* that controls the focus of the light source.

If you run the application *LightingProgram*, it opens the following window:

![](image/Image2050.jpg)

The example looks like *ColorProgram*, but instead of illustrating the effect of colors, the program shows the effect of light. The figures in the top row show the effect of a standard and a distant light source, respectively, while the two figures in the bottom row show the effect of a spot and a point light source, respectively. The code of the program is:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_62.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_63.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_64.jpg)

The two methods *text()* and *circle()* are similar to the corresponding methods from earlier. You should primarily consider the method *start()* and here how to create light sources as *Light* objects used as parameters for a *Lighting* object that is an effect. Note that the specific *Light* classes are defined as inner classes in the class *Light*.

## Problem 2

To experiment a little with light sources, write an application that opens the following window:

![](image/Image2058.jpg)

The four circles mentioned from the left are using the light sources:

1.  default
2.  distant
3.  spot
4.  point

The setting options are made with *Slider* controls and *ComboBox* controls, and the names should explain the meaning. A setting option does not necessarily have effect for all light sources, but changes a setting, the change must be reflected in the relevant shapes. As for *ComboBox* controls, they must be initialized with colors and I have enclosed a color in the following wrapper class:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_65.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_66.jpg)

You can initialize the two *ComboBox* controls with an appropriate number of standard colors (static objects in the class *Color*), but you can actually decide all of them using the following method:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_67.jpg)

# 6 Transformations

JavaFX also supports transformations of nodes in the scene graph, and it happens largely in the same way that you know it from Java2D. Generally, there are 4 transfomations

1.  Translater
2.  Scaling
3.  Rotation
4.  Shearing

and the meaning is the same as in Java2D. As a simple example, the following program performs a translation of a rectangle:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_68.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_69.jpg)

The method *createRect()* creates a *Rectangle* with a fixed position and size, as well as a parameter that is the color. Finally, there is a parameter that can indicate a transformation and thus a shift of the rectangle to another position. That is, the program creates two rectangles of the same size and position, but one (the red) translated 50 pxels in both directions:

![](image/Image2065.jpg)

## Exercise 16

Write a program that opens the following window:

![](image/Image2073.jpg)

The blue rectangle has the top corner in (20, 20) while the size is 200 × 100\. The red rectangle is a scaling of the blue where it is scaled to 50% in both directions and from the point (20, 20). The green rectangle is a corresponding scale, but followed by a translation. Note that in the case of compound transformations, the order means something.

## Exercise 17

Write an application that opens the window below. Here the blue rectangle has the upper left corner in (180, 180) while the size is 200 × 100\. The red rectangle is a rotation of 45 degrees of the blue rectangle about the point (180, 180). The green rectangle is a rotation about the same point, but with the angle -45 degrees, and the rotation is followed by a  translation.

![](image/Image2080.jpg)

## Exercise 18

Write a program that opens a window similar to the following when the red rectangle is to be a shearing of the blue rectangle:

![](image/Image2088.jpg)

## 6.1 Animations

In this section I introduce animations, which you also can perceive as a form of transformations of a node. An animation basically means changing one or the properties of a node, and if you do it many times and do it at short intervals, it will seem to the user as if something is “alive” with that node. As described in Java 10, a node needs to be redrawn at short intervals, and such that the value of an option has been changed for each redraw. In JavaFX, this logic is encapsulated in a number of classes, where each class defines an animation for a particular value or property. The base class is called a *Transition*, but there are the following specific transitions:

*   *FadeTransition*
*   *FillTransition*
*   *RotateTransition*
*   *ScaleTransition*
*   *StrokeTransition*
*   *TranslateTransition*
*   *PathTransition*
*   *SequentialTransition*
*   *PauseTransition*
*   *ParallelTransition*

and the names tells a little about what it is for properties that the class in question is an animation for. As an example, I will show you how to use a *FadeTransition*. A visual node has an *opacity* property that indicates the extent to which that node should be displayed transparent. If you perform an animation of this property, you can see that the figure appears fully drawn, after which it appears more transparent until it completely disappears. It is the task of a *FadeTransition*. If you run the program *FadeAnimation*, the following window shows a red circle:

![](image/Image2098.jpg)

The circle becomes weaker and weaker and finally disappears completely. Then it grows again until it is shown as it original was. This cycle is repeated 5 times. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_73.jpg)

The method *createCircle()* is trivial, while it is the method *createTransition()* that creates the transition. In this case, it is a *FadeTransition*, and the constructor tells that the animation should take 2 seconds, and what it is for a node that the animation should work on. Otherwise, the animation must change the value from from 1 (not transparent) to 0 (total transparent). The next statement tells the animation to be repeated 10 times and finally, after the animation is complete, the next one must go backwards. In *start()*, a *Transition* object is created and the statement

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_74.jpg)

starts the animation.

The other animation classes are used in the same way, but instead of showing examples, I have formulated a series of exercises that will illustrate applications of the most important classes. You can immediately start from the above program, but for some of the exercises it is necessary to read the documentation to find out what to write – which values should be initialized.

## Exercise 19

Write an application that opens a window with a blue circle:

![](image/Image2109.jpg)

Then the program should with a *FillTransition* change color to red. The animation must take 5 seconds and then start again with a blue circle. The animation must be repeated 50 times. Note that a *FillTransition* can not be applied to a general node, but it must be a *Shape*.

## Exercise 20

Write a program that you can call *ScaleAnimation*, which opens a window with a red circle:

![](image/Image2122.jpg)

The program must, with an animation, change the size of the circle, so it will shrink and grow.

## Exercise 21

Write a program that you can call *TranslateAnimation*. The program must open a window, as shown below, where a red circle with an animation is moved from the upper left corner to the bottom right corner. You can use a *TranslateTransition*. The animation period must be 2 seconds and the animation must be repeated 50 times. You must also set *AutoReverse* to true.

![](image/Image2129.jpg)

## Exercise 22

You must write a program called *RotateAnimation*, which shows a rectangle. The rectangle should rotate from 0 to 360 degrees, and simultaneously the color must change from red to blue – and back again in the next rotation:

![](image/Image2137.jpg)

Note that this time you will need to use two transitions.

## Exercise 23

Write a program *PathAnimation*, where a red circle moves along a *CubicCurve* (see below). The curve must be defined as a *Path* object, and as a transition object you can use a *PathTransition*. An animation of the circle must run for two seconds, and you must set *AutoReverse* to *true*.

![](image/Image2144.jpg)

## Exercise 24

As the last example of an animation, write a program *SequentialAnimation* similar to the above, where a red circle moves along a *CubicCurve*, but the animation is only repeated once. When the circle reaches the end of the curve (the animation stops), the circle should with an animation change color to blue and back to red again. The program must therefore use two animations that are performed sequentially.

# 7 Components

Looking at the foregoing, I have primarily focused on how you in JavaFX works with geometric objects, but I have only overall mentioned components that the user can interact with. Viewed from practical programs it is of course the most interesting and is the subject of this and the following chapters. It is about which components are available and how they are laid out in a window. In addition, there is event management.

## 7.1 Layout

The program’s scene graph consists of components, and these components can be placed absolutely as I have used in conjunction with geometric objects, but typically, nodes are placed in the scene graph using layout panes where a layout pane is an branch node. Viewed from the programmer, a layout pane has the same characteristics (and purposes) as a layout manager in Swing, and the theory resembles what you know from Swing. All layout panes have a common basic class *Pane*, and there are the following specific panes:

*   *HBox*
*   *VBox*
*   *BorderPane*
*   *StackPane*
*   *Flow Pane*
*   *TextFlow*
*   *AnchorPane*
*   *TitlePane*
*   *Grid Pane*

In this section I show how the layout panes are used to layout components, and of course they can be nested in the same way you know it from Swing. The following examples are similar to each other and briefly show the application of the different panes, but you should examine the online documentation and what properties are available.

I want to start with a *HBox* (the *HBoxProgram* application) which places components horizontally in a window, and here with three buttons:

![](image/Image2152.jpg)

As you can see, the size of the buttons (width) changes according to the available space, and below I have shown the same window after the size has changed:

![](image/Image2159.jpg)

As you can see, the components are as default left-aligned, but it can be changed with a property. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_80.jpg)

You may notice that the last method *createButton()* assigns the button a preferred size, and in JavaFX, basically, the same applies to a component’s size, as you know from Swing. As for the method *start()*, there is not much to explain, but you should note how to define a gap between the components. A *HBox* is a very simple layout pane and can only be used to arrange components on a line relative to their preferred size.

There is a layout pane, called *VBox*, which is parallel to *HBox*, the difference being that it places the components on a vertical line. The *VBoxProgram* program shows the application of this layout pane:

![](image/Image2167.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_81.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_82.jpg)

There is not much new to explain, but you should note how to indicate that the components should be displayed centered in the window. You are encouraged to investigate what options the type of *Pos* otherwise defines.

A *BorderPane* looks like a *BorderLayout* and divides the window into 5 areas, called *center*, *top*, *right*, *bottom* and *left* and usually referenced in this order. As with a *BorderLayout*, the center will fill what has not been used by the other areas. The program *BorderProgram* opens the window shown below. In addition to show a *BorderPane*, the program should also show the use of nested panes. The window has 9 components:

1.  *center* : a *TextArea*
2.  *top*: a *BorderPane* with a *TextField* and a *Button*
3.  *right*: a *BorderPane* with a *Button* and a *TextArea*
4.  *bottom*: a *BorderPane* with a *TextField* and a *Button*
5.  *left* : a *BorderPane* with a *Button* and a *TextArea*

You should notice the spacing between the components and how they are defined in the code.

![](image/Image2174.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_821.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_83.jpg)

The individual 5 areas are created with three helper methods named *createField()*. The first is used for the center and creates a *BorderPane* with a *TextArea* component. You should notice how to set a spacing of 10 to the remaining 4 areas with *setPadding()*. Also note that the *BorderPane* constructor specifies a single parameter, which is the component to be shown at the center. The second *createField()* is used to create a *BorderPane* to be placed at top and bottom respectively. Here you specify 5 parameters for the constructor in *BorderPane*, which is interpreted as *center*, *top*, *right*, *bottom* and *left*. In particular, note how to define that the button should have a left margin in the container:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_84.jpg)

Here, *setMargin()* is a static method in the *BorderPane* class, which defines the margin of the first parameter in the current layout pane. The last *createField()* method is used to create a *BorderPane* for the contents of the right and left area and, in principle, it works as the previous method. You should note that a bottom margin is defined for both components.

Finally, there is the *start()* method, where the *root* element this time is a *BorderPane* (which is a branch node). Here you should note how to create *root*, and to set a margin of 20.

A *StackPane* is a layout pane that arranges the components on top of each other in the order they are added. The program *StackProgram* shows three buttons placed on top of each other:

![](image/Image2182.jpg)

The application is probably limited, but primarily for *Shape* objects, the possibility can be useful. It’s quite simple to use a StackPane:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_85.jpg)

A *FlowPane* is a layout pane that essentially behaves like a *FlowLayout* in Swing:

![](image/Image2191.jpg)

If you increase the width of the window, all components will appear on the same line. Regarding the code, you should first notice how to define the gap between the components:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_86.jpg)

There is also a layout pane, which is called *TextFlow*, and behaving in the same way as a *FlowPane*, but only for *Text* nodes. The program *TextflowProgram* shows how to use this pane. It’s probably not the most commonly used layout pane, but it may be useful if you need to write a custom component that supports text wrapping – something that is actually relatively complicated in Swing.

![](image/Image2202.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_861.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_87.jpg)

An AnchorPane places a component relative to the container’s edge:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_871.jpg)![](image/Image2216.jpg)

In this case, *root* has a margin of 30, and the component is positioned so that it sits 30 from the right edge (relative to the margin) and 50 above the bottom (relative to the margin). If the window’s size changes, the component will follow the bottom and right edges.

Then there is a *TilePane*, which places components into cells of the same size. The size of the cells is determined by the largest preferred size (in this case the last button). Is there no room for all components on the line, the line wraps, so the last component appears on the next line.

![](image/Image2223.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_88.jpg)

In this case, the components are set horizontally, which is default, but with a property, it is possible to specify that the components should be laid out vertically.

Finally, there is a *GridPane*, which is a very useful layout pane. Compared with Swing, you can achieve a bit of the same as with a *GridBagLayout*, but it is far easier to use. Basically, it’s a grid. but the cells do not necessarily have the same size. The program *GridProgram* opens the following window:

![](image/Image2231.jpg)

that has 5 components:

*   2 *Label* components
*   2 *TextField* components
*   1 *Button* component

If you change the window size, the components will stay at their positions and with the same size – at least as long as the window is large enough. It is therefore a typical dialog box. The code is quite simple:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_89.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_90.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_91.jpg)

In the method *start()*, a *GridPane* is created as root. Note that you do not say anything about the number of rows and columns. There is a margin of 20, and there must be a gap of 20 between the individual rows. Then I add a *Label* with the width 80, and I define that it should be in cell (0, 0), which is the cell in the upper left corner. The next component is a *TextField* with the width 300, which should be in cell (1, 0), which can be translated into column 1 and row 0\. Similarly, the two next components are placed solely with the difference that they should be placed in row 1\. Finally, place the button in cell (1, 2) and thus column 1 row 2\. Note that nothing is placed in cell (0, 2). It is not necessary – a cell may be empty. In particular, you should note that a *GridPane* has a static method that you can use to specify aligment for a component within the component’s cell:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_911.jpg)

## 7.2 Events

JavaFX has its own event types, and the base type is called *Event*. Examples of specific event types include:

*   *MouseEvent*
*   *KeyEvent*
*   *DragEvent*
*   *WindowEvent*
*   *ActionEvent*

An event is characterized by

1.  a target, which is the node where an event occurs and may for example be a window, a scene or a node
2.  a source, which is the one that has generated an event and can, for example, be the mouse
3.  an event type, such as mouse pressed, mouse released and so on

When an event occurs, one talks about an *event dispatch chain*, which is the route from the stage to that node. Is it a *Circle* node, for example, it could be

*Stage* – *Scene* – *Group* – *Circle*

When an event occurs, it is sent to all nodes in its *dispatch chain* from top to bottom. If there is a node that has registered a *filter* for that event, this will be done, after which the event will be sent to its target node where it will be processed if there is an event handler. This phase is called the *Event Capturing Phase*. After that, the event will follow the way back, and for each node it will be processed if there is a *handler* assigned. This phase is called the *Event Bubbling Phase*. An event can thus result in that multiple event handlers are performed and event handlers during the capturing phase are called *filters* while event handlers during the bubbling phase are called *handlers*.

When an event follows the dispatch chain, it can at any time be stopped by the method *consume()*, which means that the event will not be forwarded in the chain. As an example, I will show a program *EventPhaseProgram* that creates the following scene graph:

![](image/Image2238.jpg)

where under *VBox* there are 14 nodes. If you opens the program you get the window:

![](image/Image2246.jpg)

For example, if you click a location in the green area, the following is written on standard output:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_94.jpg)

Here you can see how the event of mouse clicks has been processed all the way through the dispatch chain and back again. The meaning with the checkboxes of the window is that you check where the processing of an event should be interrupted. For example, checking *Filter Scene* and clicking the green rectangle again gives you the result:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_941.jpg)

You are encouraged to test the program and what happens when you click the mouse on the different nodes depending on which checkboxes are selected.

Then there is the code:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_942.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_95.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_96.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_97.jpg)

First, 12 *CheckBox* components are created, where the 6 first are to be used for the filters (capturing phase), while the 6 next are to be used for the handlers (bubbling phase). If you consider the method *start(),* this time, both a filter and a handler are assigned to the *Stage* node – the node is the top of the scene graph. A filter associated with the method *addEventFilter()*, while a handler is associated with the method *addEventHandler()*. In either case, an event handler is associated for mouse clicked, such as:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_98.jpg)

where the first parameter indicates which event to be listened to while the other is the event handler, there is an object that (in this case) implements the interface *EventHandler<MouseEvent>*. Such an object is defined by the class *Handler*, which is an inner class where the constructor has the text to be printed on the screen as a parameter, and a reference to the *CheckBox* to be tested. The class should implement the method:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_981.jpg)

In this case, the method performs a *System.out.println()*, and then tests whether the appropriate *CheckBox* is selected and, if necessary, sets the event as *consumed*, which means that it will not be forwarded in the dispatch chain. You should note how the scene graph is built by calling the methods that create the individual nodes.

These methods are all simple and all built in the same way, and you should primarily notice how to assign filters and handlers to the individual nodes in the same way as described above. You should note *createButton()*, where no filter or handler is attached. If you run the program and click on the button, you will find that no event handlers are performed in the dispatch chain, and the reason is that the button instead with *setOnAction()* is associated with an event handler of the type *EventHandler<ActionEvent>*. This means that with the mouse click, the button will take care of the event action and not fire a regular mouse event, but instead an *ActionEvent*. Also note that the event handler of the button’s *ActionEvent* opens a simple message box, including the syntax for how to do it in JavaFX.

The next example is called *KeyEventProgram* and opens the following window:

![](image/Image2253.jpg)

If you are in the entry field and enter the key *Enter*, the green square will rotate and clicking on the square it will stop the rotation. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_100.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_101.jpg)

The class defines a variable for a transition, which is the animation that rotates the square. It is created by the method *createRotate()*, which does not contain anything new in terms of animations. The actual *Transition* object is created in the method *start()*. Here you should also notice how to set the background color for the window. The square is created in the method *createRect()*. Here, the method *setOnMouseClicked()* is used to attach an event handler for mouse clicks to the square, and you should note how the event handler is defined using a lambda expression.

Then there is the method *createField()* that creates the entry field. It is a *TextField*, and the most important is the association of the event handler. It is a filter and the handler is associated for a *KeyEvent* of the type *KEY_TYPED*. The handler uses the method *getCharacter()* to test what has been entered and has the first character the code 13, it is the *Enter* key that is pressed, and if so, the animation will start. For any event, the event is marked as cosumed so that it is not passed on in the chain, and the effect is that the character for the key pressed is never displayed in the input field.

The example thus shows how to catch events for mouse and keyboard. In the example, it happens in two different ways, where in *createField()* it takes place at low level with *addEventFilter()* while in *createRect()* it occurs using a *convenience* method. Many of the JavaFX classes defines event handlers as properties, and you can then register an event handler using a set method for that *convenience* method. The goal is to make it easier to associate event handlers what the following program *HandlerProgram* should illustrate:

![](image/Image2261.jpg)

Clicking the Start button starts an animation where the circle moves along the curve and the animation runs until you click the stop button. If you click on the circle, it changes color.

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_103.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_104.jpg)

As how to create the animation and the curve there is nothing new and happens in the two methods *createTrans()* and *createRect()*. If you consider the method *createCircle()* that creates the circle, it associates an event handler for mouse clicks using a convenience method called *setOnMouseClicked()*. You should note that the event handler is the parameter and is a lambda expression.

The method *createButton()* is used to create a button. It has three parameters, which is the text of the button, the x-coordinate of the location in the window and the button’s event handler. The latter has the type *EventHandler<ActionEvent>* and is associated with the method *setOnActionEvent()*.

## 7.3 Components

Then there are the components (or controls) where JavaFX has many, but the most important are the following:

| Label | MenuButton | Slider | ColorPicker |
| Button | MenuItem | ScrollPane | DatePicker |
| TextField | Menu | ScrollBar | ProgressIndicator |
| PassWordField | ContextMenu | TabPane | ProgressBar |
| TextArea | Separator | SplitPane | FileChooser |
| RadioButton | ChoieBox | TitlePane | HTMLEditor |
| Hyperlink | ComboBox | Accordion | TableView |
| CheckBox | ListView | Pagination | TreeView |
| ToggleButton | WebView | Tooltip | TreeTableView |

Some of these components have already been used in the previous examples and the rest of this section consists of exercises and problems where you should try using the above components (but not the last three in the last column postponed to the next book). Most of the components are easy to use and take a good part of the way, as you know it from Swing. Others are more complex, and on the whole, the following exercises require that you use the documentation and, if necessary, also find examples and help on the Internet.

## Exercise 25

You must write a program that opens the following window:

![](image/Image3333.jpg)

where there are 4 controls: 1 *Label* and 3 *Button* controls. If you click *New*, the text must be changed to

*Creatring a new document…*

and clicking *Save* should change the text to

*Saving…*

If you click the *Cancel* button, the text must be changed to the original text. It is required that the window must not be resizable, and that there must be shortcuts for all three buttons.

With regard to the green frame, it can be defined with a style. This is the subject of the next chapter, but you can try and see how far you can come.

## Exercise 26

You must write an application that opens the following window:

![](image/Image3341.jpg)

In the top line there are three *Hyperlink* controls on the left. A *Hyperlink* is the same as a *Button*, but it is drawn in another way. In this case, the three links must refer to a web page (you decide which ones). On the right side there is a *MenuButton*, which is a button with a dropdown, where you can click on a *MenuItem* control. In this case, there must be three items, each of which refers to a web page (which you decide).

Center, there must be a *WebView* control, which is a control that can open and display a web page.

At the bottom there are three *ToggleButton* controls in a group and a *Label*. When you click a button, the *Label* control must be updated with the button’s text, if it is clicked and otherwise the text *None*.

Note that the commands at the top and the commands at the bottom have nothing to do with each other, and the goal is only to illustrate typical controls.

## Exercise 27

Write a program that uses a *ChoiceBox* control:

![](image/Image3350.jpg)

You must be able to select a person from the dropdown list when a person is represented by an object of the type *Person*. It must be a simple model class that represents a person by a name and a job title. It is a requirement that the *Person* class must not have any *toString()* method, and instead, a converter must be associated with the *ChoiceBox* control. After selecting a person, the name and the job title must be displayed with a *Label*:

![](image/Image3364.jpg)

When you click the *Clear* button, this label must be blanked and no person in the *ChoiceBox* control must be selected.

## Exercise 28

You must write the same program as in the previous exercise, but with one difference: Instead of using a *ChoiceBox*, you use a *ComboBox*.

Once you have written the program, try to investigate what the difference is between a *ChoiceBox* and a *ComboBox*.

## Problem 3

From Swing you know the component *JList*, which is a list box and is one of the widely used components. In JavaFX, it is replaced by a *ListView*, which is a much more advanced component with many new options, which uses multiple help classes. You must write an application that opens the following window, where the window shows four *ListView* controls (actually 5), each *ListView* showing 10 *Person* objects where *Person* is the class from exercise 27.

![](image/Image3378.jpg)

1.  The *ListView* control in the upper left corner should show how to select items. You can select an item with the mouse and select an item using the top 5 buttons. Each time you select an item, the blank *ListView* must show which items are selected.
2.  The *ListView* control in the upper right corner should show how to edit a *Person* object. If you double-click on a person, the list box must open a field so you can edit the content (it is built into the component). Under the control there is a *TextField* that will be used to add a new *Person* object to the list.
3.  The *ListView* control at the bottom left should show items where each element is a *ChoiceBox*, from which you can update the item by selecting another *Person* object (it is also built into the component).
4.  Finally, the last *ListView* shows the items as *CheckBox* controls (it is also incorporated into the *ListView* component). If you click on the button, the program must open a message box that displays the objects that are selected (by the checkboxes).

The task requires you to examine the documentation to find out what to write, and maybe you can also can find help online.

## Exercise 29

JavaFX has a component called *ColorPicker*, which is a relatively complicated component for selecting a color. On the other hand, the component is both flexible and easy to use. You must write a program that opens a window where you can choose a color used to color a rectangle:

![](image/Image3385.jpg)

## Exercise 30

JavaFX has a good *DatePicker* control that can be used to select a date. You must write a program that opens the following window, where November 15, 2017 was selected:

![](image/Image3393.jpg)

After the date is selected, the bottom *Label* must be uploaded.

## Exercise 31

JavaFX has a progress bar like Swing, but there is also a *ProgressIndicator*, and the difference is how the two components are drawn. The *ProgressIndicator* control is bass class for *ProgressBar*. A progress component is updated in the same way as in Swing using a thread represented by a *Task* object contained in the *javafx.concurrent* package. You must write a program that shows a *ProgressIndicator* and a *ProgressBar*, both of which can be started (and stopped) by clicking a button:

![](image/Image3400.jpg)

and below is the window after clicking on both buttons:

![](image/Image3409.jpg)

and below the window after the two progress components are completed:

![](image/Image3416.jpg)

## Exercise 33

You must write a program that opens the following window, that has a *Label*, a *TextField* and two *Button* controls:

![](image/Image3424.jpg)

The buttons do not need an action, but the input field and the buttons must have a Tooltip. Here it is interesting that you can attach a style to a tooltip, where styles is the subject of the next chapter.

## Exercise 34

Write a program that has a window with two *TextArea* controls located in a *SplitPane*:

![](image/Image3431.jpg)

## Problem 4

In this task you should work with menus in JavaFX. You must write an application that opens the following window:

![](image/Image3439.jpg)

The window has a menubar with two menus, and the window itself (center) has a *Canvas* object. The first menu must have the following functions:

![](image/Image3448.jpg)

If you click on one of the three top menu items, a dark green shape with a black border in the window should appear, for example:

![](image/Image3459.jpg)

The fourth menu item must clear the window, while the last one should close the program. The *Options* menu has a menu item as well as a *Slider* :

![](image/Image3472.jpg)

The first menu item must indicate if the circumference of the shape is to be drawn while the slider indicates the size of the perimeter. If you move the slider, the perimeter of any shape should be updated.

If you right click on the canvas object you should get a context menu:

![](image/Image3479.jpg)

and clicking on one of the two menu items, a *ColorPicker* object should appear at the bottom of the window, so you can choose one of the two colors:

![](image/Image3487.jpg)

As a last requirement, shortcut keys must be available for all menu items, and accelerator keys must be defined for the three shapes.

## Exercise 35

You must write an application that opens the following window:

![](image/Image3494.jpg)

and thus a program that uses tabs (two tabs). On the first one, you must enter a name and a registration date, while on the other you can enter the address and an email address. If you click on the button, you must get a message box that shows the data entered:

![](image/Image3502.jpg)

## Exercise 36

JavaFX has a control called *HTMLEditor*, which is a complete HTML editor. You must write an application that opens the following window where you can edit a HTML document:

![](image/Image3509.jpg)

The program must have buttons so you can load and save an HTML document in a local file.

## 7.4 Dialogs

You can also use dialog boxes, and there are dialogs as in Swing there are ready to use classes that can be used immediately and, and on the other hand, there are dialog boxes that are custom. The simplest is an *Alert* that corresponds to a *MessageDialog* in Swing. The *AlertProgram* application opens the following window:

![](image/Image3517.jpg)

If you click on the *Info* button, you get the message box below that shows a simple message and clicking on the *Save* button, you may receive a corresponding message box (but with an error message) and finally the last button will result in a message box with a warning, where you will be asked if you want to delete the entry field:

![](image/Image3524.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_118.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_119.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_120.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_121.jpg)

The buttons are created in the method *createCommands()*, and here are the interesting the *ActionEvent* listeners, which are defined as classes at the end of the program. The *InfoListener* class creates an event object for the *Info* button, and in the handler is created an *Alert* object of the type *AlertType.INFORMATION* and the result is the dialog box shown above. You must note how the dialog box is otherwise initialized and how the individual messages appear in the message box. The dialog opens with the method *show()*. The method is not blocking and the program is not waiting for a return value.

The *SaveListener* class defines a listener to the *Save* button and simulates that the entered text is saved. It tests the text length and is the length less than 5, an alert similar to the above opens. The difference is the type as here is *AlertType.ERROR* corresponding to an error message, and then the dialog opens but instead with the method *showAndWait()*. This means that the message box is blocking and the following statement

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1211.jpg)

will only be executed after the dialog box is closed.

The last listener class is similar to the others, but this time is the type *AlertType.CONFIRMATION* that opens a dialog box with two buttons, where the user must select *YES* or *NO*. It also opens with *showAndWait()* and you should note that this time there is a return value and how this value is tested.

There also is a *ChoiceDialog*, where the user can choose a value between several options. The program *ChoiceProgram* opens a window with a button and clicking on the button gives you the following dialog box:

![](image/Image3532.jpg)

where in a dropdown you can choose a text (in this case the name of a Danish king). If you click OK, the selected name will be returned to the application where it appears in the window. The code is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_122.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_123.jpg)

Initially, a list named *dialogData*, which contains the names of 5 Danish kings, is defined. The method *start()* is simply and build a scene graph containing a button and a *Text* control. The button’s event handler calls the method *showDialog()*, which creates a dialog of the type *ChoiceDialog*. The parameters of the constructor are the data to be displayed in the dropdown field and which one should be selected by default. Otherwise, you should notice how to get the return value and test it.

As the last of the standard dialog boxes, you have a *TextInputDialog* that is used to enter a text. The program *InputProgram* opens just like the previous program a window with a button and clicking on the button gives you a dialog box where you can enter a text:

![](image/Image3541.jpg)

The program is basically identical to the previous one, so I would like only to show the method called from the event handler for the button, and compared to the previous example, there is not much to explain, the fact that the type of the dialog box is now *TextInputDialog*:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_124.jpg)

As the last example in this section, the following application opens two custom dialogs. The program is called *DialogProgram*, and if you run the program, you get the following window:

![](image/Image3552.jpg)

If you click on the button at the top, you will get a dialog box where you should enter the name and job title of a person and choose a date (which can be interpreted as birthday, appointment date or something else):

![](image/Image3565.jpg)

If you click the bottom button, the program opens another dialog box that shows the persons entered in the first dialog box (here it is after two persons are entered):

![](image/Image3572.jpg)

The program looks like a program that I’ve seen before in connection with Swing (the book Java 2). A person is defined by a simple model class:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_125.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_126.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_127.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_128.jpg)

At the start of the program, a list is defined for *Person* objects, which are the persons created in the input dialog. The method *start()* is trivial and the only thing to note is which event handlers are associated with the two buttons. The first calls the method *enterDialog()*, which creates an object of the type *Dialog* to *Person* objects. The parameter type *Person* specifies which object is returned if the dialog box ends by clicking *OK*. Next, the contents of the dialog box must be defined, and that happens by a *GridPane*, which laid out the dialog box components, and this *Pane* is assigned the dialog box as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1281.jpg)

The next step defines which buttons the dialog should have, and then is defined how to click on *OK* to create a *Person* object, which must be the return value of the dialog box.

The other dialog box is basically built in exactly the same way, but this time with a *BorderPane*. The main difference is that there is no return value this time. You should note that this dialog box has a header text, while the first one did not, and what a header text means for the result.

# 8 Styling

From web applications you know cascading style sheets, and you can also use it in JavaFX. The idea is the same as for web application, namely to separate the definition of windows and their content from the presentation so that you can change the look and feel of a program without changing the code. On the other hand, the syntax is a little different, and as for web applications, the biggest challenge is to learn how styles can be written and what they are called. The subject appears best with an example, and the program *StyleProgram* opens the following window:

![](image/Image3580.jpg)

where the window contains two *Label* controls, two *TextField* controls and two *Button* controls. For all 6 components there is a style attached. For the *TextField* and *Button* controls, it happens in a style sheet, which is a file named *styles.css*:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_130.jpg)

Here are three styles defined. In the same way as for web pages, a style is defined with a selector that starts with a point followed by the type on the node in the scene graph, which should have that style – but with the class name written in lowercase. The first, therefore, defines a style for *Button* nodes. Here, two style attributes are defined, and the difficulty is of course to know which attributes can be specified, but in general, you can associate a style value with any of the class’s properties. Here is the syntax that if there is a property called *backgroundColor*, the style attribute is named *-fx-background-color*. That is, if the name of an attribute consists of two words, the last one starting with a capital letter, it is all written in lowercase letters and with a hyphen is inserted between the words. The same syntax is used for a selector, and a selector for the class *TextField* is written as:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1301.jpg)

You can also have a custom selector, what the last style is an example of. It defines a style for the gray frame in the window, and when you see the individual attributes, it is easy enough to understand the meaning. In practice, of course, it is more difficult to find out what to write, and it is important to note that NetBeans knows JavaFX style sheets and which attributes are available.

With respect to the syntax, the following applies to values of the individual attributes:

*inherit*, where the value is inherited from the parent’s node, for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1311.jpg)

*boolean*, where the value can be *true* or *false*, for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1312.jpg)

*string*, where you enter the value in quotation marks, for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1313.jpg)

*number*, where you enter the value as a decimal number, for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1314.jpg)

You can also specify a unit such as *px* (pixels), *mm* (millimeters), *cm* (centimeters), *in* (inches), *pt* (points), *pc* (picas) or *em*. You can also specify a percent value. Examples could be:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1315.jpg)

*angle*, which is specified by a number and a unit that must be *deg* (degrees) or *rad* (radians) for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1316.jpg)

*point*, which is specified using x and y coordinates as two numbers separated by whitespaces, for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1317.jpg)

There are several other values that you can specify for properties, and you should examine the documentation for a complete overview, for example

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1318.jpg)

Above is shown a style sheet with three styles and it must be somewhere. The project *StyleProgram* consists of the following files:

![](image/Image3587.jpg)

and the style sheet in question is thus located in the folder *css* under *resources* (that again is located under the *src* directory). It is not a requirement, but can be recommended as the file becomes part of the project’s jar file. Then there is the code for the above program:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_132.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_133.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_134.jpg)

It’s a simple program where the components are laid out using a *GridPane*. A style sheet can be assigned to a scene graph or a branch node. In this case, it is assigned to the scene graph:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1341.jpg)

Here is used a relative path to the style sheet, but you can of course also specify an absolute path. As a result, all of the program’s *TextField* and *Button* nodes (unless stated otherwise) will apply the styles defined in the style sheet. The statement

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1342.jpg)

says that the *GridPane* node should apply a style with the selector *border*, and the result is that the gray frame appears.

Styles can also be defined inline, as is the case with the two *Label* controls. It certainly has its uses, but it is generally advisable to define styles in a style sheet, as inline styles can only be changed in the code.

If you in an application considers an attribute, its value can be determined in several places, and the following list indicates which value has the highest priority:

1.  inline (the highest priority)
2.  parent node
3.  scene graph
4.  values assigned in the code (Java properties)
5.  default style sheet

Here you should especially note that styles have higher priority than values assigned in the usual way in the Java code. Also note the last option with the lowest priority. If you do not specify something, the value of a property is determined by a default style sheet.

## Exercise 37

You must write an application that opens the following login window:

![](image/Image3595.jpg)

where there are 2 *Label* controls, 1 *TextField* control, 1 *PasswordField* control and 2 *Button* controls. For these controls, the following properties must be set:

1.  *Label*: Must have a bold *Arial* font on 18 points
2.  *TextField*: Must have a bold *Arial* font on 14 points and the text should be dark blue
3.  *PasswordField*: Must have a gray background and a blue frame
4.  *Button*: Must have a blue background and a white text with a bold *Arial* font on 14 points

These values must all be assigned using styles defined in a style sheet.

# 9 FXML

*FXML* is an XML language that can be used to define the user interface in a JavaFX program and thus it is an alternative to writing the code in Java. With FXML you can define the entire scene graph or just a part of it. If in NetBeans you select *JavaFX* and *JavaFX FXML Application* for *New Project*

![](image/Image3602.jpg)

and when you click *Next*, you must enter a project name where I have typed *HelloFXML*, and when you click *Finish*, NetBeans creates a project with three files:

![](image/Image3610.jpg)

and again it is a fully finished program that can be translated and executed:

![](image/Image3617.jpg)

If you click on the button, you get a window where a label is updated:

![](image/Image3625.jpg)

Then there is the code and I want to start with HelloFXML.java:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_137.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_138.jpg)

Immediately, it is a usual JavaFX application with a method *start()*, and there is only one difference, which is the statement

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1381.jpg)

which loads the file *FXMLDocument.fxml*. It is the XML document that defines the user interface and hence the program’s sceen graph. When you see the content, it’s almost a common XML document:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1382.jpg)

The document starts with some import directives, which you can easily interpret. Otherwise, the document consists of elements that corresponds to classes for nodes in the scene graph, and even the same names apply. For the individual elements, you can define attributes that match the properties of the corresponding node classes, and here the same names apply. The only exception is the attribute *fx:id*, which refers to a variable defined in the controller class. In addition, note the value of the attribute *onAction* for the *Button* item, which refers to a method (an event handler) in the controller class. The class is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_139.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_140.jpg)

The class defines a variable and two methods. The first is a reference to the control defined in the XML section, and here you should note the annotation *@FXML.* It means that an *FXMLLoader* can create an object defined in FXML by injection. The same notation is used for the event handler for the button, which means it can be referenced from the FXML section. You should note that the class implements the interface *Initializable*, which defines a single method that can be used to initialize the controller.

The above is what NetBeans has automatically created, and I will now have to make changes to *FXMLDocument.fxml* and *FXMLDocumentController.java*. The class *HelloFXML.java* will be unchanged. *FXMLDocument.fxml* has been changed to:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1401.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_141.jpg)

Two new import directives have been added, and the *AnchorPane* element has been replaced by a *VBox* element. Then a style element and a *TextField* element are added, and many attributes are also changed. When you see the code, it is easy enough to understand – at least if you know JavaFX. As a result, the window changes to the following:

![](image/Image3634.jpg)

where the text *Carlo* is entered in the entry field and then clicked on the button. In the controller, nothing else has been added than an additional variable has been added and the event handler has been changed:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1411.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_142.jpg)

## 9.1 Create objects

As illustrated in the previous example, FXML is used to define a program’s scene graph or part of the graph, but FXML may more generally be used to define an object graph. In this section, I will show a program called *ObjectsFXML*, which will show you how to create objects using FXML. The *ObjectsFXML.java* program class does not contain anything new and will not be shown here. The file *FXMLDocument.fxml* has the following content:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1421.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_143.jpg)

For example, if you look at the item

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1431.jpg)

this means that an object of the type *VBox* is being instantiated. First of all, it requires an import directive for the package containing the class *VBox*, and that the class has a default constructor, as the syntax does not contain any immediate way to transfer values to the constructor. Similarly, the element

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1432.jpg)

means that a *Text* object is created and that it is referred to in the controller of the variable *header*. Here, the object is also assigned a value that I return to below. The next thing that happens is to create a *ComboBox* called *lstKings* (the name that the corresponding object is called in the controller). In particular, note how the *ComboBox* is initialized. This happens with an *ObservableList*, and here the syntax means that the list is created using a factory method, explained below. The individual items in the list are of the type *String* and the item

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_144.jpg)

creates a *String* object by performing a static method *valueOf()* initialized with the current value. It requires that the class of which to instantiate an object has such a method and it has the class *String*. The result of all is that a *ComboBox* is created with 5 *String* objects.

As a next step, a button is created where there is nothing new to explain, and then an empty *ComboBox* called *lstPersons* and finally another button. Finally, a *Label* is created, and here you will notice how this *Label* is initialized with a *String* object. If you run the program, you get the following window:

![](image/Image3645.jpg)

where a name is selected in the top combobox and then clicked on the top button. The other *ComboBox* is also initialized, and it is done using a factory, as shown below. The *ComboBox* is initialized with Objects of the type:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1441.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_145.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_146.jpg)

which is a simple model class that I have previously shown. Note that the class has no default constructor, and if you want to instantiate an object, it is necessary to transfer parameters to the constructor. Because you not can do that in FXML, a builder class is used, that is a class that implements an interface:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1461.jpg)

and a class that implements this interface how to instantiate objects of the type *T*. The class is used by a factory class that implements another interface:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1462.jpg)

The *FXMLLoader* class uses a *BuilderFactory* if it can not create an object otherwise, and it happens bt calling the method *getBuilder()* with the type as argument. If this method returns a *Builder* object, a *FXMLLoader* uses this object to initialize the required properties of the object to be instantiated and eventually called the method *build()* that returns the object. The builder class must have get and set methods for all the constructor’s parameters. In this case, you must define a *Builder* for the class *Person* as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1463.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_147.jpg)

A *Builder* is thus a class that solve the problem that you can not construct an object of a class (here *Person*) without transferring parameters to the constructor.

In addition to a *Builder*, you must have a *BuilderFactory*, and in this case it can be written as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1471.jpg)

The method *getBuilder()* has a type as parameter, and if this type is *Person*, a *PersonBuilder* is returned. Otherwise, a default builder will be returned for that type.

For the project *ObjectsFXML*, I have created a directory *resources / fxml*, and I have added a file named *Persons.fxml* whose content are:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_148.jpg)

That is, a XML document that defines 5 *Person* objects, but in order to instantiate these objects, a *Builder* is required. It happens in the controller:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_149.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_150.jpg)

Note that at the start of the controller, variables are defined corresponding to elements defined in the FXML document. Next, there are the events of the two buttons that do not require any particular explanation. In the method *initialize()*, the object *header* is initialized by the loader, and the same applies to *lstPersons*, which is the bottom *ComboBox*. This is done by calling the method *loadPersons()*, as with a *FXMLLoader* loads the XML document with the definitions of *Person* objects, using a *BuilderFactory*, that here is a *PersonFactory*.

## 9.2 DialogFXML

I will write a program similar to the program *DialogProgram* from chapter 7, when the difference is that the user interface is written in FXML. I start with a *JavaFX FXML Application* project, which I have called *DialogFXML*. The main program is unchanged, but *FXMLDocument* is changed to the following:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1501.jpg)

which defines a window with two buttons:

![](image/Image3659.jpg)

I have then added the class *Person* from the project *DialogProgram*. The window’s controller can then be written as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_151.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_152.jpg)

First, note that a list has been defined for *Person* objects, but otherwise the class consists primarily of the event handlers for the two buttons. In principle, the two methods work in the same way as they starts to load the XML that defines the user interface, and then the list of *Person* objects must be transferred to the controller for the dialog box. Here you should especially note how to refer to the controller. To create a dialog box, I add an Empty FMXL:

![](image/Image3666.jpg)

After clicking *Next*, I have to enter the name (for example, *ShowDocument*), and in the next window you can choose whether to create a controller:

![](image/Image3674.jpg)

Finally, there is a window where you can specify whether there should be a stylesheet, and then NetBeans has added two new files. If it is the dialog box for entering a person, they are called *EnterDocument.fxml* and *EnterDocumentController.java*. Below is the FXML code that defines a *GridPane*  :

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_153.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_154.jpg)

Here is not much new compared to what has previously been shown, but you should note that a *DataPicker* has been added, which is a node in the same way as other nodes. The controller is as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_155.jpg)

Also, here is not much new, but you should note that a method has been added as *setList()*, so there is access to the list of *Person* objects in the event handler for the *OK* button. You should also note how to close the window by obtaining a reference to the *Stage* object that represents the window. If you run the program and click on the top button, you get the following window:

![](image/Image3681.jpg)

The XML code of the other dialog box is:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_156.jpg)

and is basically a *BorderPane*. Note that the center is a *ListView*, which is not initialized here, but is instead done it in the controller, which is trivial:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1561.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_157.jpg)

Opening the dialog the result is (where two persons are entered):

![](image/Image3689.jpg)

## 9.3 About FXML

This chapter has provided a brief introduction to FXML, and although there is more to explain, the above should be sufficient to use FXML in practice. The question is then what is gained from using FXML and there are two purposes:

1.  to separate the design/definition of the user interface from the Java code
2.  to make it easier to develop complex user interfaces

The first follows immediately from the separation of the code for a window in an XML part and a controller with the Java code. In principle, it is good, but it requires learning FXML, and although NetBeans provides good support, there is still a lot to learn, and in my opinion, it’s at least as easy to write the user interface in Java as in FXML. The separation of the code can easily be achieved by moving the code to event handlers in their own classes in a controller layer. The conclusion is that I do not find the big gains in using FXML, and in fact, I feel that the forces are better used by learning JavaFX in detail than using the power to get good at FXML. It’s my opinion and it’s not necessarily true and I know that others look different. Therefore, there is only to say, to try and gain your own experiences.

According to what I’ve mentioned above, FXML does not make it easier to write user interfaces, but it is when using a tool. There is a program called *Scene Builder* that you can use to design the user interface. Instead of writing the code itself, you pull components from a toolbox and place them in the window where you think they should be. The tool will then form the FXML code for the user interface, and it is in this context that FXML comes into its own. The product *Scene Builder* can be downloaded from

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_159.jpg)

and it is quite simple to install. Of course, you should learn to use the product, but also it is relatively easy, and if you often need to write complex user interfaces, it is worth knowing the product as it can generate significant progress in development projects.

# 10 A final example

As the final example, I will use the same program as in the previous book, but with the difference that the program this time should be a desktop application. This means that I can reuse the class library *FunctionsLib*, which implements the mathematical functions, as well as the classes for parsing and evaluating an expression can also be reused. Therefore, I only have to implement the user interface. The aim of the program is, of course, to show an example of a JavaFX program, which is slightly larger than the examples that are otherwise shown in this book.

The program must have the same features as in the previous book and should be basically used in the same way where the user enters a mathematical expression that the program can then evaluates. Unlike the previous program, the program should have buttons for the mathematical functions where a button should do nothing but insert the function name in the input field of the expression. In the previous program you can save a value in a variable and the value can be inserted later in an expression. In the new version of the program you must be able to save an arbitrary expression so that you can insert an expression into an expression, and it should also be possible to save the program’s variables in a file.

## 10.1 Development

The development of the program has been implemented as a form of prototyping, and in the following I will briefly describe how the development has been completed. From the start, I have planned the following iterations:

1.  First prototype
2.  Enhanced prototype
3.  Implements the square root and square function
4.  Implements Store and Recall
5.  Implements the other functions
6.  Implements Set Precision
7.  Implements the menu item Expressions
8.  Implements the File menu
9.  Implements missing features
10.  Styling the program
11.  Refactoring

and the goal is that after completing the last iteration, you will have a finished program. The iterations are small, but after each iteration you have a version of the program that can be tested and used with the functions that have been implemented.

#### First prototype

The goal is to write an early version of the program, which should alone be a sketch of the user interface. The program must therefore not have calculating functions.

![](image/Image3696.jpg)

Apart from the buttons, the program looks like the application from the previous book. The window must be resizable, and the two text fields must follow the size of the window, but the bottom must have a fixed height. The buttons should follow the right edge and bottom of the window. The *File* menu must have functions for saving and loading the variables, while the *Functions* menu must have a function to change the precision as well as a function that shows an overview and the variables that have been created.

#### Enhanced prototype

The result of the next iteration is still a prototype for the user interface, but with some changes with regard to buttons and with appropriate spacing and padding of the components.

![](image/Image3704.jpg)

To the right of the buttons is a list box that displays the program’s variables and the size must be that part of the window that is not used for buttons. Additionally, a progress bar has been added because some the calculations may take a long time.

#### Implements the square root and square function

I have added a reference to the jar file *FunctionsLib.jar* from the final project in the previous book. Then I have created a package *bigcalc.models* and copied the files *Tokens.java* and *Expression.java* from the project *FunctionsEJB* to this package. After that, the entire math should be in place and the required calculation functions should be available.

I have then created a package *bigcalc.ctrls* and here a class *MainController*:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_163.jpg)

In the class *BigCalc*, event handlers are assigned to the following buttons:

*   Sqr
*   Sqrt
*   Clear Result, which deletes the content of the upper field for the result
*   Clear Editor, which deletes the content og the enter field
*   Enter

It is all simple event handlers. Then you can perform arithmetic and evaluate expressions, and the calculator is in principle complete. In particular, you can paste text into the editor by clicking the buttons *Sqr* and *Sqrt*.

#### Implements Store and Recall

If you click the *STO* button, you should get the following dialog box:

![](image/Image3711.jpg)

where to enter the name of the variable. If you click *OK*, the last result that is calculated is saved. If, on the other hand, you have checked the *Store Expression* check box, it is the expression that is entered in the editor field that is saved. After clicking *OK* and the desired value is assigned to the variable, the list box is updated (the list box to the left of the buttons).

In order to keep track of the variables, the following model class has been added:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_164.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_165.jpg)

If you click on a variable in the list box, the corresponding value is inserted in the editor field (at the cursor’s position). The same syntax is used as in the previous program, that is *@A1*, and the difference is that the value can be a value or an expression. This means that the controller must be updated so that values for variables are substituted before the expression is sent to the parser.

If you click the *RCL* button, you get the following window where two variables were created:

![](image/Image3719.jpg)

If you click on the name of a variable, the window closes and the value of the variable is inserted in the editor field at the cursor’s position. If you check one or more checkboxes and click the button *Remove*, these variables will be deleted.

Center in the window is a *ListView* that is created as follows:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_166.jpg)

Here you should note that a *ListView* can contain anything, and especially a layout pane with components. It is thus an extremely flexible component, and the list box on the main window is initially initialized in the same way.

In principle, this dialog box contains the same information as the list box to the left of the buttons, but the dialog is included partly to delete variables and partly to give a better overview.

#### Implements the other functions

This iteration is simple as the remaining buttons must do the same as for *Sqr* and *Sqrt*, where only a text must be inserted into the editor field at the cursor’s position. The only challenge is that it is the right text.

However, the impact of the progress bar must be implemented. I have changed the component to a *ProgressIndicator*, which is constantly running, but from the start is invisible. When a calculation is started (clicked *Enter*), the component is made visible and it becomes invisible again when the calculation is completed and the user interface is updated. The only challenge is get the the user interface (the *ProgressIndicator*) updated, and the calculation must be performed in its own thread:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_167.jpg)

After this iteration, the machine is in principle completed, but with a fixed precision of 200.

#### Implements Set Precision

This function opens a simple dialog box where you can enter the desired precision:

![](image/Image3728.jpg)

If you click *OK*, both the controller and the status bar in the main window must be updated. The function has been moved from the menu to a button above the *Enter* key. The menu has been changed so that under *Functions* there is a menu item for each of the program’s buttons. The reason is partly to have a better description of the individual functions and to define key combinations for all functions and commands.

#### Implements the menu item Expressions

This iteration is empty, as the function corresponds to a click on *RCL*, and the function is already implemented. Since *RCL* also has a menu item, the function already exists in the  menu.

#### Implements the File menu

Five functions must be implemented, all located under the File menu:

1.  *Save*, which saves all variables in an existing file
2.  *Save as*, which saves all variables in a new file
3.  *Open*, which opens a file with variables, that ealier are saved
4.  *New*, which deletes all existing variables
5.  *Exit*, which terminates the program

Variables must be saved with simple object serialization. Therefore, the class *Memory* is partly defined *Serializable*, and in addition, there are added two static methods:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_169.jpg)

Then it’s simple to implement the 5 event handlers using a *FileChooser* component.

#### Implements missing features

There is not much that are missing, but the following should be added:

1.  There should be warnings if you try to overwrite existing variables by loading variables from a file or closing the program and the variables are not been saved.
2.  Similarly, there should be a warning if you delete the content of the result field, and accordingly if you delete variables in the dialog that shows the list of variables (the command RCL). The same applies to the dialog boxes for entering the name of a variable and the dialog for change the precision if you enter an illegal value.
3.  If you use many significant digits (heigh precision), a calculation can take a long time and therefore a timeout should be defined so that the program giving up after the timeout.

The first point is simple to solve and is primarily about include a *boolean* variable that keeps track of changes in the program’s variables. The problem is thus limited to ensuring that this variable is set at the correct places and then test the variable in the event handlers for the *File* menu. Additionally, you can override the *stop()* method and test the variable there so that you do not close the program without a warning if there are non-saved variables.

The second point is similarly simple and refers to displaying a confirmation box in the event handler that deletes the content of the result field, as well as a test in the three dialog boxes.

The last problem, on the other hand, is not quite simple to solve. First I have in the controller class (*MainController*) included a property *timeout*, which indicates the number of seconds for the timeout value. It is as default 15\. Next, I have expanded the program with the following dialog box:

![](image/Image3739.jpg)

where you can enter the timeout value. There is no button for the dialog, but it is opened from the menu or with a shortcut key.

When you click the *Enter* button in the main window, the following events are performed:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_171.jpg)![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_172.jpg)

It looks a bit complex. The calculation is performed by a method in an *Expression* object in the controller and is the method that takes time, and if executed directly, it will block the main window, which will mean that the progress indicator does not run. The calculation must therefore be performed in its own thread, which is the thread *calculator*. In Java, you can not directly interrupt a running thread, which must happen in the case of a timeout. The problem can be solved with an *Executor* and a *Future* object (possibly see Java 8). The thread *calculator* therefore starts with disabling the button *Enter*, and then an *Executor* object is created that is used to start a task of the type *Calculator*:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1721.jpg)

It is then its *call()* method that performs the calculation. After this task has been created (in the thread *calculator*) the thread is set to wait for the task to be performed or a timeout occurs. In the case of the last the result is defined as the text *Timeout*, after which is executed an

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_1722.jpg)

This causes that threats performed by the task to terminate, and even if it is still running due to a timeout. Hereafter the following method is called which updates the result:

![](image/Java_14_–_Development_of_applications_with_JavaFX_9-4-18_173.jpg)

and the button will be enabled agian. After the thread *calculator* is defined, it is started and the result is that the calculation is performed in a thread (of a task object) that is started by the thread *calculator* that starts when clicking the *Enter* button.

#### Styling the program

After the above iterations, all windows and nodes are shown on basis of the default styles in JavaFX, and often, by a program of the current kind, it will be quite good, but if you want to put your own touch on how the components appear or for some reason want to change the specific components look and feel, you can add a style sheet. It is preferable not to directly assign values to properties in the code, as a style sheet makes it much easier to maintain the code.

There are several strategies, but you can proceed as follows. The program (the main window) has the following groups of components:

*   1 *TextArea* for the display (the result)
*   1 *TextField* to the editor field
*   1 *ListView* to variables
*   1 *Button* to the *Enter* button
*   5 *Button* controls to commands (*Clr Result*, *Clr Editor*, *Precision*, *RCL*, *STO*)
*   2 *Button* controls to consts (*Pi*, *e*)
*   36 *Button* controls to functions
*   7 *Menu* controls
*   41 *MenuItem* controls
*   1 *ProgressIndicator*
*   1 *Label* to the text in the status line
*   1 *Label* to precision
*   1 *Label* to the filename
*   1 *Label* to the variable name in the list box
*   1 *Label* to the variable valie in the list box

You can then in a style sheet define a class (an empty class) for each of these groups (15 classes in total) and then associate these classes with the individual components. You can then write the styles you want to use and the advantage is that you can change the presentation of controls without changing the Java code, and as the most important thing, you can delegate the work to developers with special skills in styling.

In this case, I have added a style sheet named *mainstyles.css* and written a few styles – and maybe even most for the example’s sake.

You can then repeat it for all the application’s windows and dialogs, and maybe use the same style sheet for all or most dialogs. That way, you only have to write styles somewhere, and all of the application’s dialog boxes have the same look and feel. In this case, I have added a style sheet named *dlgstyles.css*, which is used by all dialogs. In many examples, you may want to use a single style sheet, which is used by all windows, and of course (at least for small programs) it may be appropriate.

#### Refactoring

Now the program is in principle complete and consists of the following files:

![](image/Image3752.jpg)

I have previously argued that in this place you should conduct a code review, inspecting the code, adding comments, removing disabilities, and more. This code review often has character of a refactoring, which may result in code being moved to new classes or reorganizing the code in another way. Especially if the program is developed through many small iterations with the character of prototyping as in this case, there is a great risk that it may go beyond the architecture, and in particular there is a risk that the class of the main window swells up and becomes inappropriately design. For the sake of future maintenance, therefore, refactoring is important, and you should focus on the following:

*   If there are *import* statements that are no longer necessary (NetBeans shows which ones), they should be removed.
*   If there are variables that are no longer used, they should also be deleted.
*   If there is code (such as methods) that are not used, it should be removed.
*   Has instance variables and methods appropriate names. If not, consider changing the names so that they better reflect the use.
*   Consider visibility, so only what it’s going to be *public* is *public* while the rest is *private* and possibly *protected*.
*   Are variables and properties located in the right place (in the right classes) and here you must have the MVC pattern in mind. Often the user interface will contain variables that should be moved to the controller or model.
*   Pay special attention to code repetition where the same code is written in several places. Such a code should typically be moved to its own method, and the code repetitions can then be replaced by the call of this method.
*   Pay attention to the size of classes. If classes are very large, such as many hundred of lines or more, you might want to consider splitting up the class into several classes. Not that you must necessarily, but a class on a thousand lines or more is hard to overlook.
*   Be aware of event handlers, as they tend to contain code related to business logic, and if necessary, this code should be moved to controller classes (possibly to the model). In general, event handlers should be as simple as possible and contain only code that directly concerns the user interface. It’s a tough balance, since delegation of the code to the controller and model layers can also lead to code that is difficult to read and that the user interface needs to be observer for the controller and model. However, it should be noted that the user interface should contain only what is necessary to update the components.

And so: Refactoring is an important activity for future maintenance, but make sure that the process does not introduce new errors in the program. The program must then be tested again after the activity is completed.

And then there are the comments, which are also part of the refactoring process or rather the maintenance of the comments. I have previously argued the importance of comments and especially the process of writing the comments. These views are still valid, but if you see my program examples (what the readers hopefully do), I have to admit that there is a long line between the comments. Should the truth come true, I must also admit that I am a bit ambivalent with regard to comments: I know it’s right to comment on the code, but I do not do that often, so some remarks about this problem.

It’s a big job to write comments – at least if you have to make it complete, and then the comments also has to tell you something. You must therefore necessarily refer to whether it is worth the work. Comments documents the code and it is certainly important, but I find that good program architecture and good names for variables and methods are far more important – it is also a form of comments. The goal of all is to make the code easier to read and understand, and here I find that the things I have mentioned above regarding refactoring, exceeds the value of comments. Comments have definitely their applications, but with good names and a good architecture, there is a tendency for comments to commenting on self-esteem and comments make comments for their own sake, and if so, it’s not worth the effort – then there is hardly anyone who will pay for the assignment.

Now it’s probably not either, but to explain a little about my wings, I will mention that when I have to read and understand foreign code, one of the first things I do is to delete all comments. They simply seem disturbing to me – at least if it’s a nice code. Is that the way it matters, of course, it does not make much sense of writing comments. Of course, it also has something to do with which code it is, where comments of the code in the user interface are rarely valuable, where comments of complex algorithms in control and model days may be required.

I know that not everyone will agree with these views, but at least they explain why my code often lacks comments, which also reflects that much of what I should write as comments is a part of the text in the books.