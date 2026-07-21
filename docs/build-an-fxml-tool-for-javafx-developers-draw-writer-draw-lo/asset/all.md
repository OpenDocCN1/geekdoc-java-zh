![](images/00039.jpeg)

|  

&#124;  
### Offer Reusable Classes and Graphics Applications
Including Complete Source Code

 &#124;

 |

|  

&#124;  
# BUILD AN FXML TOOL
FOR JavaFX DEVELOPERS

 &#124;

 |

|  
## DRAW WRITER & DRAW LOADER
in Java 8

 |

|  

&#124;  
## Coding in JavaFX
Step by Step
Build Graphics Toolkit

 &#124;

 |
|  
### VOLUME Ⅳ

 |

|  

&#124;  
## Shufen Kuo
Bing-Chao Huang

 &#124;

 |

Copyright© 2016 Shufen Kuo & Bing-Chao Huang.

All rights reserved.

No part of this book may be reproduced or distributed in any form or by any means, or stored in a database or retrieval system, without the prior written permission from the authors (Shufen Kuo & Bing-Chao Huang), with the exception that the source codes that come with the book may be entered and executed in a computer system for learning purpose, but they may not be reproduced or modified for publication or commercial use without prior written permission from the authors.

## TABLE OF CONTENTS

*   [ABOUT THE AUTHORS](#part0003.html_2RHM0-6cbc394105fd4c6ab27dd0d32efbcd86)
*   [ACKNOWLEDGMENT](#part0004.html_3Q280-6cbc394105fd4c6ab27dd0d32efbcd86)
*   [PREFACE](#part0005_split_000.html_4OIQ0-6cbc394105fd4c6ab27dd0d32efbcd86)
    *   [How this book is organized](#part0005_split_001.html_how-this-book-organize)
    *   [Why Choose This Book](#part0005_split_002.html_why-choose-this-book)
    *   [What You Need for This Book](#part0005_split_003.html_what-you-need)
*   [**INTRODUCTION**](#part0006_split_000.html_5N3C0-6cbc394105fd4c6ab27dd0d32efbcd86)
*   VOLUME Ⅳ: DEVELOPING SKETCH SAVING AND LOADING APIS
    *   [**Chapter 1**: Enhanced Draw Tool with `Draw Writer` Capacity](#part0007_split_000.html_6LJU0-6cbc394105fd4c6ab27dd0d32efbcd86)

        Introduce `DrawWriter` class, resides in `drawtool.io` package, to generate FXML files for sketch created interactively on a drawing board, a `Pane` object. The sketch can be either a `Shape` object or an `ImageView` object. Besides FXML format, it also provides API to save the image of an `ImageView` object to an image file.

        *   [1.1 Create `DrawWriter` Class](#part0007_split_001.html_create-draw-writer)
            *   [1.1.1 `Document` and `Transformer`](#part0007_split_001.html_document-n-transformer)
            *   [1.1.2 `DOMSource` and `StreamResult`](#part0007_split_001.html_dom-source-n-stream-result)
            *   [1.1.3 Implement `writeFXML` Method](#part0007_split_001.html_implement-write-fxml)
                *   [1.1.3.1 Composing Contents of A DOM Document](#part0007_split_001.html_compose-contents)
            *   [1.1.4 Implement `writeImageView` Method](#part0007_split_001.html_implement-write-image-view)
                *   [1.1.4.1 Snapshot an Image](#part0007_split_001.html_snapshot-image)
                *   [1.1.4.2 Exploit `boundsInLocal` and `boundsInParent`](#part0007_split_001.html_exploit-bounds)
                *   [1.1.4.3 Exploit `layoutBounds`](#part0007_split_001.html_learn-layout-bounds)
                *   [1.1.4.4 Complete Source Code of `writeImageView` Method](#part0007_split_001.html_source-code-write-image-view)
        *   [1.2 Create JavaFX Nodes in a Scene Graph using FXML](#part0007_split_002.html_create-node-fxml)
            *   [1.2.1 Create `Line` specifying `strokeDashArray` in FXML](#part0007_split_002.html_create-line)
            *   [1.2.2 Create `Polyline` for a Scene Graph in FXML](#part0007_split_002.html_create-polyline)
            *   [1.2.3 Create `Polygon` Shaped like Arrow in FXML](#part0007_split_002.html_create-polygon)
            *   [1.2.4 Create `Path` Formed a Chinese Character in FXML](#part0007_split_002.html_create-path)
            *   [1.2.5 Create `SVGPath` in Terms of `M`, `H`, `Q`, `L` Instructions in FXML](#part0007_split_002.html_create-svg-path)
            *   [1.2.6 Create `Rectangle` Filled with `RadialGradient` in FXML](#part0007_split_002.html_create-rectangle)
            *   [1.2.7 Create `Circle` Filled with `LinearGradient` in FXML](#part0007_split_002.html_create-circle)
            *   [1.2.8 Create `Ellipse` with `Transform` and `Effect` in FXML](#part0007_split_002.html_create-ellipse)
            *   [1.2.9 Create `Arc` Painted like Rainbow in FXML](#part0007_split_002.html_create-arc)
            *   [1.2.10 Create `Text` with Visual Effect and Shearing Transform in FXML](#part0007_split_002.html_create-text)
            *   [1.2.11 Generate FXML Files from a Shape Builder](#part0007_split_002.html_example-fxml-file)
        *   [1.3 Complete Source Code of `DrawWriter` Class](#part0007_split_003.html_complete-source-codes-draw-writer)
        *   [1.4 Summary](#part0007_split_004.html_summary)
    *   [**Chapter 2**: Enhanced Draw Tool with `Draw Loader` Capacity](#part0008_split_000.html_7K4G0-6cbc394105fd4c6ab27dd0d32efbcd86)

        Introduce `DrawLoader` class, resides in `drawtool.io` package, to load FXML files as well as image files to a drawing board.

        *   [2.1 Create `DrawLoader` Class](#part0008_split_001.html_create-draw-loader)
            *   [2.1.1 Implement `loadFXML` Methods](#part0008_split_001.html_implement-load-fxml)
            *   [2.1.2 Implement `loadImage` Method](#part0008_split_001.html_implement-load-image)
        *   [2.2 Complete Source Code of `DrawLoader` Class](#part0008_split_002.html_complete-source-codes-draw-loader)
        *   [2.3 Summary](#part0008_split_003.html_summary)
    *   [**Chapter 3**: Enhanced `JFXDrawTools` with `Draw Writer` and `Draw Loader` Capacities](#part0009_split_000.html_8IL20-6cbc394105fd4c6ab27dd0d32efbcd86)

        Integrate sketch saving and loading capabilities into `JFXDrawTools` application.

        *   [3.1 Add `File` Menu to Menu Bar](#part0009_split_001.html_add-file-menu)
        *   [3.2 Generate FXML Files for Drawings Using `DrawWriter` Class](#part0009_split_002.html_generate-fxml)
        *   [3.3 Add `Save FXML` Submenu to `File` Menu](#part0009_split_003.html_add-save-fxml-sub-menu)
        *   [3.4 Load Drawings from FXML Files Using `DrawLoader` Class](#part0009_split_004.html_load-drawing)
            *   [3.4.1 Load FXML Files](#part0009_split_004.html_load-fxml-files)
            *   [3.4.2 Load Image Files](#part0009_split_004.html_load-image-files)
        *   [3.5 Add `Open` Submenu to `File` Menu](#part0009_split_005.html_add-open-sub-menu)
        *   [3.6 Bind Stage Title for Displaying FXML File Name](#part0009_split_006.html_bind-stage-title)
        *   [3.7 Add `Action` Menu to Menu Bar](#part0009_split_007.html_add-action-menu)
        *   [3.8 Complete Source Code of `JFXDrawTools` Class](#part0009_split_008.html_complete-source-codes-jfx-draw-tools)
        *   [3.9 Summary](#part0009_split_009.html_summary)
*   [EPILOGUE](#part0010.html_9H5K0-6cbc394105fd4c6ab27dd0d32efbcd86)

# ABOUT THE AUTHORS

### Shufen Kuo

Shufen Kuo relocated to San Francisco Bay Area in summer of 1988, and has been a software engineer ever since. She has extensive hands-on experience with various platforms, from PC DOS to numerous Unix/Linux workstations, and from PC Linux to PC Windows.

She started writing Java programs in 2001\. She has been using Abstract Windowing Toolkit (AWT) and Swing, the GUI Components of Java Foundation Classes (JFC), to design and develop object oriented graphics tools. And since 2012, she has immersed herself in JavaFX; exploring its essence inspires her to write books publicizing the strength of JavaFX.

Before developing Java applications, she had more than 12 years experience in the development of C/C++ applications on UNIX/Linux/Solaris running X Window system.

Shufen Kuo got her M.S. in Computer Science from Washington State University in 1987.

Her publications include:

*   "A Two-Step String Matching Procedure," Pattern Recognition, 24(7), 711-716, 1991.
*   "An Improved Algorithm to Find the Length of the Longest Common Subsequence of Two Strings," ACM SIGIR Forum, Spring/Summer 1989, Volume 23, Numbers 3-4, 89-99

### Bing-Chao Huang

Dr. Bing-Chao Huang received his Ph.D. in Computer Science from Washington State University in 1987\. He completed an M.S. degree in Computer Science from Stanford University in 1984.

His publications include:

*   Algorithm I in D.E. Knuth＊s book "The Art of Computer Programming," Volume 1 Fundamental Algorithms, Third Edition (1997), 176-177
*   "Fast Stable Merging and Sorting in Constant Extra Space," The Computer Journal 35(1992), 643-650
*   "Stable Set and Multiset Operations in Optimal Time and Space," Information Processing Letters 16(1991), 131-136
*   "Stable Duplicate-Key Extraction with Optimal Time and Space Bounds," Acta Informatica 26(1989), 473-484
*   "Practical In-Place Merging," CACM 31(1988), 348-352
*   "Stable Set and Multiset Operations in Optimal Time and Space," Seventh ACM SIGACT-SIGMOD-SIGART Symposium on Principles of Database Systems (1988)
*   "Practical In-Place Merging," ACM-IEEE/CS Fall Joint Computer Conference (1987)
*   "A One-Way, Stackless Quicksort Algorithm," BIT 26(1986), 127-130, with D.E. Knuth
*   "An Algorithm for Inverting A Permutation," Information Processing Letters 12(1981), 237-238

# ACKNOWLEDGMENT

| Special thanks to: Dr. Tan and his family,
my brother-in-law Dr. Jacob Chung,
my sister Dr. Shuching Chung,
my two cats Mimi & Maomao. |
| --Shufen Kuo |

#   PREFACE

## How this book is organized

This book is VOLUME Ⅳ of the book series, `Coding in JavaFX Step by Step Build Graphics Toolkit`. Since contents are abundant and unfeasible to be managed into one book, chapters are organized among volumes:

1.  VOLUME Ⅰ: DEVELOPING IMAGE VIEWING COMPONENTS
    *   **Chapter 1**: Basic Image Viewer
    *   **Chapter 2**: Enhanced Image Viewer with Browsing Buttons
    *   **Chapter 3**: Enhanced Image Viewer with Slide Show Capacity

        Figure 1. Snapshot of the Image Viewer in JavaFX 8

        ![](images/00001.jpeg "image_viewer_1.jpg")

2.  VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS
    *   **Chapter 1**: Line Drawer

        Draw lines from mouse events on a drawing board.

    *   **Chapter 2**: Polyline Drawer

        Draw polylines from mouse events on a drawing board.

    *   **Chapter 3**: Polygon Drawer

        Draw polygons from mouse events on a drawing board.

    *   **Chapter 4**: Path Drawer

        Draw paths from mouse events on a drawing board.

    *   **Chapter 5**: Quadratic Bézier Curve Drawer

        Draw paths composed of quadratic Bézier curves from mouse events on a drawing board.

    *   **Chapter 6**: Basic Draw Tool

        Create integral classes in a package named `drawtool` to facilitate developments of various shape drawers -- Rectangle Drawer, Circle Drawer and Ellipse Drawer.

    *   **Chapter 7**: Enhanced Draw Tool with Predefined Drawers

        Enhance `drawtool` package and implement a variety of drawers, reside in `drawtool.drawer` package, containing these predefined shape drawers -- LineDrawer, PolylineDrawer, PolygonDrawer, PathDrawer, BazierCurveDrawer, RectangleDrawer, CircleDrawer, EllipseDrawer, and ShapeMover -- which are subclasses of `ShapeDrawer`.

    *   **Chapter 8**: Initial `JFXDrawTools` Application

        Develop initial version of `JFXDrawTools` by integrating with all predefined shape drawers as well as utilizing enhanced shape drawing APIs.

        Figure 2. Snapshot of the JFXDrawTools V1.0 application in JavaFX 8

        ![](images/00002.jpeg "jfx_draw_tools_1_0.jpg")

3.  VOLUME Ⅲ: DEVELOPING INTERACTIVE REGULAR POLYGON DRAWING TOOLS
    *   **Chapter 1**: Enhanced Draw Tool with `Regular Polygon` Shape Capacity

        Introduce `RegularPolygon` class, which derives from `Shape` class and resides in `drawtool.shape` package.

    *   **Chapter 2**: Enhanced Draw Tool with `Regular Polygon Drawer` Capacity

        Implement `RegularPolygonDrawer`, a direct subclass of `ShapeDrawer`, resides in `drawtool.drawer` package, to draw N-sided regular polygons from mouse events on a drawing board, featuring usages of `RegularPolygon` class.

    *   **Chapter 3**: Enhanced `JFXDrawTools` with `Regular Polygon Drawer` Capacity

        Integrate N-sided regular polygon drawer into `JFXDrawTools` application.

        Figure 3. Snapshot of the JFXDrawTools V1.1 application in JavaFX 8

        ![](images/00003.jpeg "jfx_draw_tools_1_1.jpg")

4.  VOLUME Ⅳ: DEVELOPING SKETCH SAVING AND LOADING APIS
    *   **Chapter 1**: Enhanced Draw Tool with `Draw Writer` Capacity

        Introduce `DrawWriter` class, resides in `drawtool.io` package, to generate FXML files for sketch created interactively on a drawing board, a `Pane` object. A sketch can be either a `Shape` object or an `ImageView` object. Besides FXML format, it also provides API to save the image of an `ImageView` object to an image file.

    *   **Chapter 2**: Enhanced Draw Tool with `Draw Loader` Capacity

        Introduce `DrawLoader` class, which resides in `drawtool.io` package, to load FXML files as well as image files to a drawing board.

    *   **Chapter 3**: Enhanced `JFXDrawTools` with `Draw Writer` and `Draw Loader` Capacities

        Integrate sketch saving and loading capabilities into `JFXDrawTools` application.

        Figure 4. Show various JavaFX shapes created in FXML and display on a drawing board

        ![](images/00004.jpeg "arc_ellipse_text_effect.jpg")

        Figure 5. Snapshot of the JFXDrawTools V1.2 application in JavaFX 8

        ![](images/00005.jpeg "jfx_draw_tools_1_2.jpg")

5.  AND THE OTHERS...

A useful **Summary** section is available at the end of each chapter; it lists all the key aspects of JavaFX library featured in the chapter. It helps you to look up fundamental capabilities of JavaFX engaged in this book series. Here are some of essentials among others:

*   `Shape` class in `javafx.scene.shape` package for 2D geometric primitives.
*   FXML, a markup language which complies with the XML (Extensible Markup Language) format, to build GUIs.
*   Properties and binding mechanism.
*   `Image` class and `ImageView` class to load and display images.
*   Concurrency capacity in `javafx.concurrent` package.
*   `FadeTransition` and `ParallelTransition` applied onto image objects in a slide show function.
*   Build-in layout panes in `javafx.scene.layout` package.
*   And more...

### Reusable Classes with Applications and Complete Source Code

Complete source code of a set of packages with reusable classes as well as embeddable JavaFX applications are included in the book series.

The following tables list all the source code offered in the prior volumes of the book series:

Drawing Tools

| Package Name | Source Code File Name |
| --- | --- |
| drawtool | ShapeDrawer.java DrawPane.java |
| drawtool.drawer | BezierCurveDrawer.java CircleDrawer.java
EllipseDrawer.java
LineDrawer.java
PathDrawer.java
PolygonDrawer.java
PolylineDrawer.java
RectangleDrawer.java
RegularPolygonDrawer.java
RubberBander.java
ShapeMover.java |
| drawtool.shape | RegularPolygon.java |
| drawtool.io | DrawClipper.java DrawLoader.java
DrawWriter.java |

Graphics Applications

| Package Name | Source Code File Name |
| --- | --- |
| imageviewer | FileUtils.java ImageViewer.java
SlideshowService.java |
| jfxdrawtools | JFXDrawTools.java |

### Contents of VOLUME Ⅳ

Let's glance at the contents of VOLUME Ⅳ:

*   [**Chapter 1**: Enhanced Draw Tool with `Draw Writer` Capacity](#part0007_split_000.html_6LJU0-6cbc394105fd4c6ab27dd0d32efbcd86)

    Introduce `DrawWriter` class, resides in `drawtool.io` package, to generate FXML files for sketch created interactively on a drawing board. A sketch can be either a `Shape` object or an `ImageView` object. Besides FXML format, it also provides API to save the image of an `ImageView` object to an image file.

    *   [1.1 Create `DrawWriter` Class](#part0007_split_001.html_create-draw-writer)
    *   [1.2 Create JavaFX Nodes in a Scene Graph using FXML](#part0007_split_002.html_create-node-fxml)
    *   [1.3 Complete Source Code of `DrawWriter` Class](#part0007_split_003.html_complete-source-codes-draw-writer)
    *   [1.4 Summary](#part0007_split_004.html_summary)
*   [**Chapter 2**: Enhanced Draw Tool with `Draw Loader` Capacity](#part0008_split_000.html_7K4G0-6cbc394105fd4c6ab27dd0d32efbcd86)

    Introduce `DrawLoader` class, resides in `drawtool.io` package, to load FXML files as well as image files to a drawing board.

    *   [2.1 Create `DrawLoader` Class](#part0008_split_001.html_create-draw-loader)
    *   [2.2 Complete Source Code of `DrawLoader` Class](#part0008_split_002.html_complete-source-codes-draw-loader)
    *   [2.3 Summary](#part0008_split_003.html_summary)
*   [**Chapter 3**: Enhanced `JFXDrawTools` with `Draw Writer` and `Draw Loader` Capacities](#part0009_split_000.html_8IL20-6cbc394105fd4c6ab27dd0d32efbcd86)

    Integrate sketch saving and loading capabilities into `JFXDrawTools` application.

    *   [3.1 Add `File` Menu to Menu Bar](#part0009_split_001.html_add-file-menu)
    *   [3.2 Generate FXML Files for Drawings Using `DrawWriter` Class](#part0009_split_002.html_generate-fxml)
    *   [3.3 Add `Save FXML` Submenu to `File` Menu](#part0009_split_003.html_add-save-fxml-sub-menu)
    *   [3.4 Load Drawings from FXML Files Using `DrawLoader` Class](#part0009_split_004.html_load-drawing)
    *   [3.5 Add `Open` Submenu to `File` Menu](#part0009_split_005.html_add-open-sub-menu)
    *   [3.6 Bind Stage Title for Displaying FXML File Name](#part0009_split_006.html_bind-stage-title)
    *   [3.7 Add `Action` Menu to Menu Bar](#part0009_split_007.html_add-action-menu)
    *   [3.8 Complete Source Code of `JFXDrawTools` Class](#part0009_split_008.html_complete-source-codes-jfx-draw-tools)
    *   [3.9 Summary](#part0009_split_009.html_summary)

## Why Choose This Book

This book is for software developers who are interested in developing GUIs using JavaFX library for rich client applications.

Important features in JavaFX are illustrated by step-by-step development of real world Java applications.

Instructive diagrams are used to help readers capture abstract concepts instantly. And all diagrams used in each chapter are created using the graphics tools developed in this book series.

The book series is for you if you are:

*   A Java GUI programmer, novice or professional, who is new to JavaFX.
*   A Java programmer who has preliminary knowledge of JavaFX and would like to learn how to develop interactive sketch drawing tools.
*   A professional software engineer who is interested in the development of object oriented JavaFX graphics tools and practical applications, along with complete and well-documented source code.

## What You Need for This Book

If you want to compile and run applications included in this book, you need to download and install JDK. Here's the website to download JDK 8, [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

To copy the complete source code from this kindle e-Book, Here's a suggestion:

1.  Install `Calibre`, a free and open source E book Management software, to your PC.
2.  Use `Add books` function in `Calibre` to add the .mobi file of the e-Book to `Calibre` library.
3.  Open the book from `Calibre` and copy the source code to Java files.

#   INTRODUCTION

This book series is a tutorial for software developers to build GUIs of Java applications using JavaFX 8 which has become a part of Java™ SE Development Kit 8 (JDK 8).

The primary objective of the book series is to provide a comprehensive handbook, which brings forward the frequently used features and the essence of JavaFX. The usages of APIs provided in JavaFX packages are illustrated through the step-by-step development of a sophisticated graphics toolkit.

Complete source code of the graphics toolkit, a set of packages with reusable classes as well as embeddable JavaFX applications, is included in the book series. Download and install JDK 8 before you compile and run these applications. Here's the website to download the latest version of JDK, [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

## JavaFX History

Now let us glance through the timeline of JavaFX evolving history and obtain glimpses of the predecessor of JavaFX:

Chris Oliver of SeeBeyond Technology Corporation developed a script language called F3, the acronym for Form Follows Function; it allows developers accessing Swing classes and creating graphics user interfaces (GUIs) for rapid development of rich internet applications.

Sun Microsystems acquired SeeBeyond in September 2005, F3 renamed to JavaFX Script in May 2007.

In December 2008, JavaFX 1.0 released, developers had relied on JavaFX Script to develop JavaFX applications until three years later when JavaFX 2.0 released.

In January 2010, Oracle completed the acquisition of Sun Microsystems, and continued maintaining JavaFX.

In September 2010 JavaOne conference, Oracle announced JavaFX Script would be discontinued.

In October 2011, JavaFX 2.0 released, developers began to engage in standard Java language, instead of JavaFX Script, to access APIs of JavaFX library. However, JavaFX SDK and JavaFX Runtime, in addition to Java SE JDK and JRE, must be installed for developing and executing applications compiled with JavaFX 2.0.

In February 2013, JavaFX 2.2.7 released, JavaFX SDK and JavaFX Runtime are included within JDK/JRE 7\. The integration of JavaFX and JDK results in great conveniency for JavaFX developers. No additional installations are needed for JavaFX applications compiled with JDK 7 and later releases.

On March 18, 2014, JavaFX 8 released as part of Java™ SE Development Kit 8 (JDK 8), a major feature release.

As of the publishing of first volume of the book series on March, 2016, the latest JDK releases are:
JDK 8u66 on October 20, 2015, and JDK 8u72 on January 2016.

The schedule of general availability (GA) for JDK 9 is March 23rd, 2017.

## Prerequisite

JavaFX applications presented in the book series using APIs provided in JavaFX packages to build GUIs. Knowledge of Swing packages is not a must, however, readers must be familiar with the basics of Java programming language. If you are new to Java, visit this website,
[http://docs.oracle.com/javase/tutorial/index.html](http://docs.oracle.com/javase/tutorial/index.html), to obtain preliminary knowledge of Java technologies. Read Oracle Java online documentation in this order:

1.  Getting Started with Simple Java Application "Hello World!" and Installations:
    Visit [http://docs.oracle.com/javase/tutorial/getStarted/index.html](http://docs.oracle.com/javase/tutorial/getStarted/index.html)
2.  Concepts and features of the Java Programming Language:
    Visit [http://docs.oracle.com/javase/tutorial/java/index.html](http://docs.oracle.com/javase/tutorial/java/index.html)
3.  Java Collections Framework:
    Visit [http://docs.oracle.com/javase/tutorial/collections/index.html](http://docs.oracle.com/javase/tutorial/collections/index.html)
4.  Essential Java Classes:
    Visit [http://docs.oracle.com/javase/tutorial/essential/index.html](http://docs.oracle.com/javase/tutorial/essential/index.html)

## A Glimpse of JavaFX Applications

The following example is for readers who are new to JavaFX to have a quick preview of how to create a JavaFX application.

To get started, you create a class that extends `javafx.application.Application`, the entry point of JavaFX applications, and override the `start` method that is abstract must be overridden. Here's what a typical `start` method looks like:

```
 package imageviewer;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    StackPane imageArea = new StackPane();
    rootPane.getChildren().add(imageArea);

    Scene scene = new Scene(rootPane, 600, 400); 
    stage.setTitle("ImageViewer V1.0");
    stage.setScene(scene);
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

### Scene and Stage

There are two important classes, `Scene` and `Stage`, appears within the `start` method. In general, the main task is to create graphical user interfaces (GUIs) managed in hierarchical tree structure called a scene graph, associate the root node of the scene graph to a `Scene` object, then place the scene on a `Stage` object which stands for the top-level container of the FavaFX application, acting as the window of the scene graph to interact with application users.

Following snapshot gives you an initial idea of how the GUIs of a JavaFX application we are going to build looks like:

Figure 1. Snapshot of a JavaFX application.

![](images/00006.jpeg "javafx_app_guis.jpg")

### Nodes

JavaFX introduces a basic class, `javafx.scene.Node` which extends `java.lang.Object` and provides common properties and methods useful to all available user interfaces. Very often we are using the term nodes to reference GUIs.

A scene graph may contain nodes of sorts. A node is either a parent (a node with children) or a leaf (a node without children); each node can have only one parent, and the root node has no parent. All nodes in a scene graph are derived from `javafx.scene.Node` class.

For quickly catch the essential about the types of nodes in a scene graph, we'll differentiate them by the ability to add children or not.

*   You may add children to these nodes:

    The following classes are frequently employed as parent nodes: `Group`, `Pane`, and build-in layout panes (they are direct subclasses of `Pane`). Typically, you call the `getChildren()` method to obtain a list of type `ObservableList<Node>` (it is a subinterface of `java.util.List`), then you use the basic utilities, defined in `Collection` interface, which java developers are familiar with, to manipulate the content of the list.

*   You may not add children to these nodes:

    The following classes are always employed as leaf nodes: `Canvas`, `ImageView`, `MediaView`, and all direct subclasses of `Shape` such as `Rectangle`, `Circle`, `Ellipse`, etc.

## JavaFX and Swing

Now, here is an intriguing issue. For years Java developers have been building GUIs of Java applications using Swing APIs, the GUI Components of Java Foundation Classes (JFC), why do we need JavaFX in addition to Swing?

If you possess multitudes of legacy code written in Swing and would like to incorporate JavaFX features into Swing code, JDK 8 provides mechanism to do so, and vice versa, you can include Swing components in JavaFX applications.

The topic of JavaFX-Swing Interoperability is not covered in the book series. If you are interested in this topic, visit Oracle Online Documentation "JavaFX: Interoperability -- JavaFX-Swing Interoperability" at here:
[http://docs.oracle.com/javase/8/javafx/interoperability-tutorial/fx_swing.htm](http://docs.oracle.com/javase/8/javafx/interoperability-tutorial/fx_swing.htm)

JavaFX is the next generation of Java GUIs. To account for the benefits of employing JavaFX capabilities, besides the Interoperability between JavaFX and Swing, we present the significant features of JavaFX in the section below.

## Essence of JavaFX

JavaFX not only allows you to create applications with visual user interfaces rapidly, but also contains enticing and distinctive abilities. They are enumerated as follows:

### Build-in Layout Panes

JavaFX's layout panes are containers that automatically perform various types of placement on nodes. You can place any number of nodes in a layout pane, which is a node itself and thus can be nested in another layout pane as well. The major advantage of using layout panes is to avoid the tediousness of manually specifying size and location of each node. As these nodes in a scene graph are managed in a tree structure, the layout algorithm recursively computes size and location of each node based on its layout type and specified layout properties, and the re-calculation is set off dynamically as the window's resize event happens.

There are 8 types of built-in layout panes, located in `javafx.scene.layout` package:

`BorderPane`

A `BorderPane` places nodes in five locations respectively to create a classic look-and-feel of main windows, typically the top region for a menu bar or a tool bar, the bottom region for a status bar, left and right regions for navigation panels, and the center region for a working area.

`HBox`

An `HBox` places nodes in one row (horizontally).

`VBox`

A `VBox` places nodes in one column (vertically).

`GridPane`

A `GridPane` places nodes in a grid with multiple rows and columns. This is a handy user interface for displaying a series of name-value pair properties.

`StackPane`

A `StackPane` places all nodes in a stack with center as default alignment. All children overlap each other in the center of the container, with the later created node placed on the top of previous ones. But you can use static methods, `StackPane.setAlignment(Node` child`, Pos` value`)` and `StackPane.setMargin(Node` child`, Insets` value`)`, to adjust the mandatory position of each node.

`FlowPane`

You can specify orientation property of a `FlowPane`. For a horizontal `FlowPane`, nodes are placed in rows, from left to right, wrapping at the boundary of its container's width. For a vertical `FlowPane`, nodes are placed in columns, from top to bottom, wrapping at the boundary of its container's height.

`TilePane`

A `TilePane` is similar to a `FlowPane` except each cell in the grid of a `TilePane` has the same size.

`AnchorPane`

An `AnchorPane` places nodes relative to their specified anchor points, there are four of them: `topAnchor`, `rightAnchor`, `bottomAnchor` and `leftAnchor`.

#### Reference to Oracle Online Documentation "Working with Layouts in JavaFX":
[http://docs.oracle.com/javase/8/javafx/layout-tutorial/index.html](http://docs.oracle.com/javase/8/javafx/layout-tutorial/index.html)

### Customization using CSS

JavaFX allows the usage of CSS (Cascading Style Sheet) to describe the presentation styles of application's user interfaces. Defining the presentation attributes--such as color, font, margins, padding, width, height, lines, background images, etc., using CSS, separated from application source code, reveals significant conveniency in many ways:

*   Customization from software provider's side:

    Applications compiled from the same set of source code can bear a variety of presentation styles, each of them complying with different customer's requirements.

*   Customization from application user's side:

    Even after the software has been released, in case application users have preferences for the look of UIs, it is also applicable to modify the presentation attributes, defined in CSS files, at customer site.

*   Benefits for designers of presentation styles:

    The separation of application source code from definitions of presentation styles improves readability of code and simplifies the tasks for graphics designers by focusing on dealing with CSS only.

*   Benefits for software developers:

    During the course of testing, developers may frequently change style attributes defined in CSS file in order to evaluate the variety looks of GUIs. If the application has to quit and restart again for each change, it is a very tiresome task. To facilitate this evaluation process, the best strategy is to design a makeshift `Load` button, and whenever any style attribute is changed, simply click on the button to re-load the CSS, there is no need to quit the application and restart it, thus saving tremendous time spending on testing.

*   Similarity between CSS in JavaFX and CSS in HTML:

    The syntax of CSS in JavaFX is same as that of CSS in HTML, thus any designer has experience on CSS for browsers can do the styling for JavaFX application's UIs with little learning effort.

#### Reference to Oracle Online Documentation "Skinning JavaFX Applications with CSS":
[http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/css_tutorial.htm](http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/css_tutorial.htm)

### Creating User Interfaces using FXML

FXML is a markup language which complies with the XML (Extensible Markup Language) syntax, with additional rules, for creating user interfaces of JavaFX applications. Considering hand coding FXML is error prone, a feasible approach is to generate FXML code by means of GUI builders.

In this book series, we present a useful application `JFXDrawTools`, it's sort of a GUI builder specifically for creating instances of subclasses derived from `Shape`. Users can interactively create a sketch, either a `Shape` or an `ImageView`, manipulate its properties and save the editing results to files in FXML format, the files can later be loaded back to continue the editing process, or be loaded by other JavaFX applications dynamically.

It is considered a good programming practice to separate application's GUIs (the View) from its business logic (the Model). The FXML file represents the view, while controller is a java class which passes information between view and model. Constructing GUIs using FXML enables application developers to adopt the MVC (Model-View-Controller) architecture effectively.

#### Reference to Oracle Online Documentation "JavaFX: Mastering FXML":
[http://docs.oracle.com/javase/8/javafx/fxml-tutorial/index.html](http://docs.oracle.com/javase/8/javafx/fxml-tutorial/index.html)

### Appealing Capacities of Properties and Binding

The concept of Properties featured in JavaFX follows the design conventions introduced in the JavaBeans component, it usually works in connection with Binding mechanism, as a whole providing powerful yet sleek and succinct solutions to a variety of programming needs.

In the `JFXDrawTools` application presented in this book series, we demonstrate the usage of Properties and Binding considerably. In the implementation of Properties Window, suitable UI controls, such as text field, choice box, combo box, etc., are used for viewing the properties of a concerned object. Binding mechanism is employed to bi-directionally link the UI controls to their respective properties of the object, the relationship is set up as the Properties Window is about to show. When users changed data displayed in UI controls, the changes instantly reflect to the corresponding properties of the related object.

#### Reference to Oracle Online Documentation "JavaFX: Properties and Binding Tutorial":
[http://docs.oracle.com/javase/8/javafx/properties-binding-tutorial/index.html](http://docs.oracle.com/javase/8/javafx/properties-binding-tutorial/index.html)

### Sophisticated Mechanism of Transformations and Transitions

The JavaFX build-in capacity of transformations for nodes are so convenient for developing graphics packages such as graphics editors, drawing tools, image viewing applications, GUI builders, etc.

Here are the classes that have dealings with transformations: `Translate`, `Rotate`, `Scale` and `Shear`. They are all derived from `Transform` class and located in `javafx.scene.transform` package.

The JavaFX transitions provide concise approaches for creating animations. There are a host of applications in need of animation features, here are some cases: to draw attention in an alert situation, to throw objects into recycle bin during the removing operation, to indicate intermediate state during a data loading,...

In the `ImageViewer` application presented in this book series, we apply `FadeTransition` and `ParallelTransition` onto image objects in a slideshow function to fade in the new image and fade out the old image simultaneously.

Here are the classes that have dealings with transitions: `FadeTransition`, `RotateTransition`, `ScaleTransition`, `TranslateTransition`, `FillTransition`, `StrokeTransition`, `PathTransition`, `ParallelTransition`, `SequentialTransition`, `PauseTransition`. They are all derived from `Transition` class, an abstract class defines basic functionality of animations, and located in `javafx.animation` package.

#### Reference to Oracle Online Documentation "JavaFX: Transformations, Animations, and Visual Effects":
[http://docs.oracle.com/javase/8/javafx/visual-effects-tutorial/index.html](http://docs.oracle.com/javase/8/javafx/visual-effects-tutorial/index.html)

### 2D Geometric Primitives and Text Are JavaFX Nodes

JavaFX provides a `Shape` class which extends `javafx.scene.Node` class and is the superclass of basic forms of 2D geometry. The object-oriented concept imposed on the geometric primitives facilitates the development of graphics applications.

Here are classes derived from `Shape` class: `Arc`, `Circle`, `CubicCurve`, `Ellipse`, `Line`, `Path`, `Polygon`, `Polyline`, `QuadCurve`, `Rectangle`, `SVGPath`, `Text`. Except the `Text` class, all the others are located in `javafx.scene.shape` package.

Please note that `Text` class, located in `javafx.scene.text` package, considered a shape as well, powers the development of text drawing tools. All features common to JavaFX nodes can be applied to text objects. You handle it just like any geometric form. Text objects can be placed in a layout pane to utilize the automatic placement abilities, applying transformations and transitions, as well as customizing the presentation style using CSS, etc.

#### Reference to Oracle Online Documentation "Using Text in JavaFX":
[http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/text-settings.htm](http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/text-settings.htm)

### Other Prominent Capabilities That Carry Out Many Complex Issues to Shorten Development Time

*   `ImageView` Class for Loading and Displaying Images

    The `ImageView` class which extends `javafx.scene.Node` is used along with `Image` class to load and display images. JavaFX also provides APIs for performing operations over bitmap images, `PixelReader` is the interface defines methods to read pixels from an `Image` object, while `PixelWriter` defines methods to write pixels to an `Image` object. All of these are located in `javafx.scene.image` package.

    #### Reference to Oracle Online Documentation "Using the Image Ops API":
    [http://docs.oracle.com/javase/8/javafx/graphics-tutorial/image_ops.htm](http://docs.oracle.com/javase/8/javafx/graphics-tutorial/image_ops.htm)

*   `WebView` Class for Managing Web Pages

    There is a web engine component embedded in JavaFX architecture and providing a set of APIs, located in `javafx.scene.web` package, for developing applications with functionality of a web browser. To view a web page, first you create a `WebView` object which extends `javafx.scene.Parent` and inherits all the features of a node, then obtain the `WebEngine` that associates with it. The `WebEngine` provides methods relevant to manipulating a web page, such as: loading/displaying the web page, either by given a url or content of the page, accessing the Document Object Model (DOM) created by `WebEngine` for the loaded web page, handling a variety of events initiated from JavaScript, etc.

    #### Reference to Oracle Online Documentation "JavaFX: Adding HTML Content to JavaFX Applications":
    [http://docs.oracle.com/javase/8/javafx/embedded-browser-tutorial/index.html](http://docs.oracle.com/javase/8/javafx/embedded-browser-tutorial/index.html)

*   `HTMLEditor` Class for Editing HTML Pages

    The full support of HTML editing ability comes from `HTMLEditor` class, extends `javafx.scene.control.Control`, resides in `javafx.scene.web` package. To embed a HTML editor into your JavaFX application, you simply create an instance of `HTMLEditor`, add it to a scene graph, then it is ready to interact with users. The following two methods are useful to get and set the HTML content of the editor: `getHtmlText()`, `setHtmlText(java.lang.String` htmlText`)`.

    Unlike the similar control `TextArea` that handles multiple lines of plain text, the `HTMLEditor` formats text that complies with HTML syntax.

    The usage of the HTML editor are widely required in various fields of software, For example, bloggers writing articles to post (content management system), users of an Email System composing messages (messaging system), online sellers preparing product descriptions for listing (e-commence management system), etc.

    #### Reference to Oracle Online Documentation "JavaFX: Working with JavaFX UI Components -- HTML Editor":
    [http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/editor.htm](http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/editor.htm)

*   Chart Components for Rendering Data

    The following classes are located in `javafx.scene.chart` packages for drawing various types of charts:

    *   `AreaChart`, `StackedAreaChart`
    *   `BarChart`, `StackedBarChart`
    *   `BubbleChart`
    *   `LineChart`
    *   `PieChart`
    *   `ScatterChart`

    `Chart` class, the base class for all chart components, extends `javafx.scene.layout.Region` class, and thus inherits all applicable features from `javafx.scene.Node` class.

    #### Reference to Oracle Online Documentation "JavaFX: Working with JavaFX UI Components -- Working with JavaFX Charts":
    [http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/charts.htm](http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/charts.htm)

*   `MediaView` Class for Playing Media

    The `MediaView` class which extends `javafx.scene.Node` is used along with `MediaPlayer` and `Media` classes to play media in your JavaFX applications. All media related classes are resides in `javafx.scene.media` package.

    #### Reference to Oracle Online Documentation "JavaFX: Incorporating Media Assets Into JavaFX Applications":
    [http://docs.oracle.com/javase/8/javafx/media-tutorial/](http://docs.oracle.com/javase/8/javafx/media-tutorial/)

## JavaFX Fundamental UI Components

In addition to the Essence of JavaFx described above, JavaFX provides fundamental UI components, reside in `javafx.scene.control` package, and are derived from `javafx.scene.control.Control` class; they are called UI controls often.

Here are available UI controls, the ones that are not marked with asterisk (*) have their resemblant counterparts in Swing:

*   `Label`, `Button`, `RadioButton`, `ToggleButton`,
*   `CheckBox`, `ChoiceBox`,
*   `ComboBox`, `ListView`, `TableView`,
*   `TextField`, `TextArea`, `PasswordField`, `HTMLEditor`(*)
*   `ScrollBar`, `ScrollPane`, `Slider`, `ProgressBar`, `ProgressIndicator`(*), `ToolBar`,
*   `MenuBar`, `MenuButton`, `SplitMenuButton`(*),
*   `ColorPicker`, `DatePicker`(*), `Separator`, `Pagination`(*), `SplitPane`, `TabPane`, `TitledPane`(*), `Accordion`(*), `TreeView`, `TreeTableView`(*), `Hyperlink`(*).

The following UI components are usually described in the same category with the above UI controls.

*   `Tooltip`

    resides in `javafx.scene.control` package, but is derived from `javafx.scene.control.PopupControl` class.

*   `MenuItem`, `Menu`, `CheckMenuItem`, `RadioMenuItem`

    resides in `javafx.scene.control` package. The `MenuItem` which extends `java.lang.Object` is the base class of the rest three.

*   `FileChooser`

    resides in `javafx.stage` package and extends `java.lang.Object`.

#### Reference to Oracle Online Documentation "JavaFX: Working with JavaFX UI Components":
[http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/ui_controls.htm](http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/ui_controls.htm)

# Chapter 1
Enhanced Draw Tool with Draw Writer Capacity
--Developing Shape Drawing Tools V1.4 (Part 1)

## Preface

In VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS, and VOLUME Ⅲ: DEVELOPING INTERACTIVE REGULAR POLYGON DRAWING TOOLS, we have demonstrated the step-by-step development of a graphics library, `Shape Drawing Tools` from `V1.0` to `V1.3`, containing APIs to facilitate developments of interactive sketch drawing applications, within these packages:

```
 drawtool
  drawtool.drawer
  drawtool.shape
```

In this chapter, we'll introduce `DrawWriter` class, resides in `drawtool.io` package, to generate FXML files for sketch created interactively on a drawing board, a `Pane` object. The sketch can be either a `Shape` object or an `ImageView` object. Besides FXML format, it also provides API to save the image of an `ImageView` object to an image file. An `ImageView` object, rendering on a drawing board, may come from an FXML file or from a graphics editing function such as image clipping, screen snapshot, etc.

From FXML examples presented in this chapter, you will experience the essentials of FXML. And from detailed descriptions and well-documented example code excerpted from developments of `Shape Drawing Tools V1.4 (Part 1)`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0007_split_004.html_summary) section.

The complete development process of `Shape Drawing Tools V1.4 (Part 1)` is characterized by the following steps:

*   [1.1 Create `DrawWriter` Class](#part0007_split_001.html_create-draw-writer)
    *   [1.1.1 `Document` and `Transformer`](#part0007_split_001.html_document-n-transformer)
    *   [1.1.2 `DOMSource` and `StreamResult`](#part0007_split_001.html_dom-source-n-stream-result)
    *   [1.1.3 Implement `writeFXML` Method](#part0007_split_001.html_implement-write-fxml)
        *   [1.1.3.1 Composing Contents of A DOM Document](#part0007_split_001.html_compose-contents)
    *   [1.1.4 Implement `writeImageView` Method](#part0007_split_001.html_implement-write-image-view)
        *   [1.1.4.1 Snapshot an Image](#part0007_split_001.html_snapshot-image)
        *   [1.1.4.2 Exploit `boundsInLocal` and `boundsInParent`](#part0007_split_001.html_exploit-bounds)
        *   [1.1.4.3 Exploit `layoutBounds`](#part0007_split_001.html_learn-layout-bounds)
        *   [1.1.4.4 Complete Source Code of `writeImageView` Method](#part0007_split_001.html_source-code-write-image-view)
*   [1.2 Create JavaFX Nodes in a Scene Graph using FXML](#part0007_split_002.html_create-node-fxml)
    *   [1.2.1 Create `Line` specifying `strokeDashArray` in FXML](#part0007_split_002.html_create-line)
    *   [1.2.2 Create `Polyline` for a Scene Graph in FXML](#part0007_split_002.html_create-polyline)
    *   [1.2.3 Create `Polygon` Shaped like Arrow in FXML](#part0007_split_002.html_create-polygon)
    *   [1.2.4 Create `Path` Formed a Chinese Character in FXML](#part0007_split_002.html_create-path)
    *   [1.2.5 Create `SVGPath` in Terms of `M`, `H`, `Q`, `L` Instructions in FXML](#part0007_split_002.html_create-svg-path)
    *   [1.2.6 Create `Rectangle` Filled with `RadialGradient` in FXML](#part0007_split_002.html_create-rectangle)
    *   [1.2.7 Create `Circle` Filled with `LinearGradient` in FXML](#part0007_split_002.html_create-circle)
    *   [1.2.8 Create `Ellipse` with `Transform` and `Effect` in FXML](#part0007_split_002.html_create-ellipse)
    *   [1.2.9 Create `Arc` Painted like Rainbow in FXML](#part0007_split_002.html_create-arc)
    *   [1.2.10 Create `Text` with Visual Effect and Shearing Transform in FXML](#part0007_split_002.html_create-text)
    *   [1.2.11 Generate FXML Files from a Shape Builder](#part0007_split_002.html_example-fxml-file)
*   [1.3 Complete Source Code of `DrawWriter` Class](#part0007_split_003.html_complete-source-codes-draw-writer)
*   [1.4 Summary](#part0007_split_004.html_summary)

## 1.1 Create `DrawWriter` Class

FXML is a markup language which complies with the XML (Extensible Markup Language) syntax, to construct GUIs of JavaFX applications without coding in Java; for more information, refer to [Creating User Interfaces using FXML](#part0006_split_005.html_creating-ui-using-FXML) in INTRODUCTION of this book.

The `DrawWriter` class, resided in `drawtool.io` package, provides innovated APIs to write sketch, drawn dynamically on a drawing board, to files in FXML format. In general, they are higher level APIs based on utilities from these Java packages:

```
javax.xml.parsers
javax.xml.transform
javax.xml.transform.dom
javax.xml.transform.stream
org.w3c.dom 
```

In addition to FXML files, `DrawWriter` also writes images to files in png or gif format.

Initially, two utilities are provided in our `drawtool.io` package:

`writeFXML`

Write a `Pane` or a list of JavaFX `Node` objects to a file in FXML format.

`writeImageView`

Apply the `javax.imageio.ImageIO.write` method to write the image of an `ImageView` object to an image file in png or gif format, taking into account the viewing properties specified in the `ImageView` object, including the transformations applied to.

Within this section, we'll describe in detail the implementations of featured methods, defined in `DrawWriter` class:

1.  `public void writeFXML(Pane` pane`, File` file`)`
2.  `public void writeFXML(List<? extends javafx.scene.Node>` list`, File` file`)`
3.  `public void writeImageView(ImageView` iv`, File` file`)`

Before we engage in the coding process, let's have a sneak peek of an FXML file generated by `writeFXML` utility:

Listing 1-1. Contents of an FXML file generated from a program that employs `writeFXML` utility:

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?import java.lang.*?>
<?import java.util.*?>
<?import javafx.animation.*?>
<?import javafx.animation.PathTransition.*?>
<?import javafx.geometry.*?>
<?import javafx.scene.Group?>
<?import javafx.scene.control.*?>
<?import javafx.scene.effect.*?>
<?import javafx.scene.image.*?>
<?import javafx.scene.layout.*?>
<?import javafx.scene.paint.*?>
<?import javafx.scene.shape.*?>
<?import javafx.scene.text.*?>
<?import javafx.scene.transform.*?>
<?import javafx.util.*?>
<Pane xmlns:fx="http://javafx.com/fxml">
  <children>
    <Ellipse centerX="280.0" centerY="80.0" fill="#00000000" fx:id="Ellipse_349826"
      radiusX="20.0" radiusY="6.0" stroke="#006400" translateX="-73.0" translateY="-20.0"/>
    <Ellipse centerX="280.0" centerY="200.0" fill="#00000000" fx:id="Ellipse_10fd2df"
      radiusX="40.0" radiusY="12.0" stroke="#006400" translateX="-73.0" translateY="-20.0"/>
    <Path fx:id="Path_1b6f0eb" stroke="#1E90FF" translateX="-73.0" translateY="-20.0">
      <elements>
        <MoveTo x="300.0" y="80.0"/>
        <LineTo x="320.0" y="200.0"/>
        <MoveTo x="260.0" y="80.0"/>
        <LineTo x="240.0" y="200.0"/>
      </elements>
    </Path>
    <Ellipse centerX="400.0" centerY="120.0" fill="#00000000" fx:id="Ellipse_192cf37"
      radiusX="30.0" radiusY="10.0" stroke="#006400" translateX="-82.0" translateY="-15.0"/>
    <Path fx:id="Path_dcbc7b" stroke="#1E90FF" translateX="-82.0" translateY="-15.0">
      <elements>
        <MoveTo x="370.0" y="120.0"/>
        <LineTo x="403.0" y="46.0"/>
        <MoveTo x="430.0" y="120.0"/>
        <LineTo x="399.0" y="46.0"/>
      </elements>
    </Path>
    <Path fx:id="Path_1d55ef8" stroke="#1E90FF" translateX="-113.0" translateY="-41.0">
      <elements>
        <MoveTo x="204.0" y="79.0"/>
        <LineTo x="158.0" y="170.0"/>
        <LineTo x="180.0" y="170.0"/>
        <LineTo x="190.0" y="148.0"/>
        <LineTo x="212.0" y="148.0"/>
        <LineTo x="223.0" y="171.0"/>
        <LineTo x="242.0" y="171.0"/>
        <LineTo x="204.0" y="79.0"/>
        <MoveTo x="202.0" y="112.0"/>
        <LineTo x="191.0" y="135.0"/>
        <LineTo x="211.0" y="135.0"/>
        <LineTo x="202.0" y="112.0"/>
      </elements>
    </Path>
  </children>
</Pane>
```

The following snapshot shows geometry sketch created from mouse dragging on a drawing board, then saved to an FXML file; and contents of the file is revealed in Listing 1-1.

Figure 1-1. Draw geometry sketch from mouse dragging on a drawing board, then saved to an FXML file, referring to Listing 1-1.

![](images/00007.jpeg "geometry.jpg")

### 1.1.1 `Document` and `Transformer`

To generate an FXML file from a program, first we need prepare a DOM `Document`, and then use a `Transformer` to write the `Document` to a physical file.

We need create a `DocumentBuilder` to instantiate a `Document`, and a `TransformerFactory` to instantiate a `Transformer`.

The `initMyFXMLDocument` method is defined to create a `Document` and a `Transformer`:

Listing 1-2. Define `initMyFXMLDocument` method to create a `Document` and a `Transformer`:

```
package drawtool.io;

import javax.imageio.ImageIO;
import javax.xml.parsers.*;
import javax.xml.transform.*;
import javax.xml.transform.dom.*;
import javax.xml.transform.stream.*;
import org.w3c.dom.*;

public class DrawWriter {
  DocumentBuilderFactory documentBuilderFactory;
  DocumentBuilder documentBuilder;
  TransformerFactory transformerFactory;
  Transformer transformer;
  Document document;
  File fxmlFile;

  void initMyFXMLDocument(File file) {
    try {
      // only create once
      if (documentBuilderFactory == null) {
        documentBuilderFactory = DocumentBuilderFactory.newInstance();
        documentBuilder = documentBuilderFactory.newDocumentBuilder();
        transformerFactory = TransformerFactory.newInstance();
        transformer = transformerFactory.newTransformer();
        transformer.setOutputProperty(OutputKeys.METHOD, "xml");
        transformer.setOutputProperty(OutputKeys.INDENT, "yes");
        transformer.setOutputProperty(
            "{http://xml.apache.org/xslt}indent-amount", "2");
      }
      this.fxmlFile = file;
      document = documentBuilder.newDocument(); // always create new doc
    } catch (ParserConfigurationException e) {
      System.out.println(e.getMessage());
    } catch (TransformerConfigurationException e) {
      System.out.println(e.getMessage());
    } 
  }

  ...

}
```

`DocumentBuilderFactory` and `DocumentBuilder` both reside in `javax.xml.parsers` package. And a DOM `Document` object can be created using the `newDocument()` method defined in `DocumentBuilder` class. Necessary methods for accessing information inside a DOM document are defined in `org.w3c.dom.Document`, an interface that extends `org.w3c.dom.Node`. To avoid confusing Java compiler, it's important to differentiate `javafx.scene.Node` from `org.w3c.dom.Node` in your code.

Here are some methods, defined in `org.w3c.dom.Document`, utilized by our `DrawWriter` class:

`Element createElement(String` tagName`) throws DOMException`

Create an element in an XML document.

`ProcessingInstruction createProcessingInstruction(String` target`, String` data`) throws DOMException`

Create a processing instruction, such as `import` statement.

We also use the `appendChild(Node` newChild`)` method, inherited from `org.w3c.dom.Node`, to append a child node to this node.

### 1.1.2 `DOMSource` and `StreamResult`

The `DOMSource` class extends `java.lang.Object` and resides in `javax.xml.transform.dom` package. The `StreamResult` class extends `java.lang.Object` and resides in `javax.xml.transform.stream` package.

When a DOM `Document` is ready to write to a physical file, we create a `DOMSource` object by passing a DOM `Document` to its constructor, and create a `StreamResult` object by passing a `File` to its constructor. Then, use a `Transformer` to transform source, the `Document`, to destination, the `File`. Here's the source code to do these:

Listing 1-3. Define `writeMyFXMLDocument` method to write a `Document` to a `File`:

```
 void writeMyFXMLDocument() {
    try {
      DOMSource source = new DOMSource(document);
      StreamResult result = new StreamResult(fxmlFile);
      transformer.transform(source, result);
    } catch (TransformerException e) {
      System.out.println(e.getMessage());
    }
  }
```

### 1.1.3 Implement `writeFXML` Method

The `DrawWriter` Class provides two `writeFXML` methods to write JavaFX nodes to FXML files, one accepts a list of `Node`, and the other accepts a `Pane`:

1.  `public void writeFXML(Pane` pane`, File` file`)`

    Recursively write children of a pane to a file in FXML format, with `<Pane>` element as root node of a `Document`.

2.  `public void writeFXML(List<? extends javafx.scene.Node>` list`, File` file`)`

    Write a list of JavaFX `Node` to a file in FXML format, with `<Pane>` element as root node of a `Document`.

At this stage, we emphasize on nodes of these types -- `Shape`, `ImageView` -- to fulfill the shape builder, JFXDrawTools V1.2 application, to be discussed in later chapter of this book. However the structure is expandable, it allows you to incrementally add code with ease to support nodes of other types.

Here are snippets of code to define `writeFXML` methods

Listing 1-4. Define `writeFXML` method in `DrawWriter` class, passing a `Pane` and a `File` to it:

```
 public void writeFXML(Pane pane, File file) {
    // if pane has no children, 
    // still create an FXML file with <pane> node,
    // and no children nodes inside it
    initMyFXMLDocument(file);
    writeFXMLHeader();
    writeFXMLRootPane(pane, pane.getChildren());
    writeMyFXMLDocument();
  }
```

Listing 1-5. Define `writeFXML` method in `DrawWriter` class, passing a `List` and a `File` to it:

```
 public void writeFXML(List<? extends javafx.scene.Node> list, File file)  {
    // if list is null or empty,
    // still create an FXML file with <pane> node,
    // and no children nodes inside it
    initMyFXMLDocument(file);
    writeFXMLHeader();
    writeFXMLRootPane(null, list);
    writeMyFXMLDocument();
  }
```

#### 1.1.3.1 Composing Contents of A DOM Document

We have described how to create a DOM `Document`, how to write it to a physical file, and how to access information inside a DOM `Document`. Now let's explore the process of composing contents of a DOM `Document` complying with FXML format.

Before writing the root node, we need to write the processing instruction for Java `import` statements, using the `createProcessingInstruction` method.

Listing 1-6. Define `writeFXMLHeader` method to write processing instructions for Java `import` statements:

```
 void writeFXMLHeader() {    
    document.appendChild(importInstruction("java.lang.*"));
    document.appendChild(importInstruction("java.util.*"));
    document.appendChild(importInstruction("javafx.animation.*"));
    document.appendChild(importInstruction("javafx.animation.PathTransition.*"));
    document.appendChild(importInstruction("javafx.geometry.*"));
    document.appendChild(importInstruction("javafx.scene.Group"));
    document.appendChild(importInstruction("javafx.scene.control.*"));
    document.appendChild(importInstruction("javafx.scene.effect.*"));
    document.appendChild(importInstruction("javafx.scene.image.*"));
    document.appendChild(importInstruction("javafx.scene.layout.*"));
    document.appendChild(importInstruction("javafx.scene.paint.*"));
    document.appendChild(importInstruction("javafx.scene.shape.*"));
    document.appendChild(importInstruction("javafx.scene.text.*"));
    document.appendChild(importInstruction("javafx.scene.transform.*"));
    document.appendChild(importInstruction("javafx.util.*"));
  }

  ProcessingInstruction importInstruction(String data) {
    return document.createProcessingInstruction("import", data);
  }
```

The header of resulting document file will look like this:

Listing 1-7. Header of a resulting document file:

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?import java.lang.*?>
<?import java.util.*?>
<?import javafx.animation.*?>
<?import javafx.animation.PathTransition.*?>
<?import javafx.geometry.*?>
<?import javafx.scene.Group?>
<?import javafx.scene.control.*?>
<?import javafx.scene.effect.*?>
<?import javafx.scene.image.*?>
<?import javafx.scene.layout.*?>
<?import javafx.scene.paint.*?>
<?import javafx.scene.shape.*?>
<?import javafx.scene.text.*?>
<?import javafx.scene.transform.*?>
<?import javafx.util.*?>
```

Please notice that, there is one problem for Processing Instruction. In the actual file, there is no line break after each instruction, therefore, you will see all processing instructions form in one line with root node <Pane> append at the end.

After adding processing instructions for import statements, do the followings:

1.  Create an element `<Pane>`, append to document as the root node.
2.  Create an element `<children>`, append to element `<Pane>`.
3.  Create elements for children of `Pane` according to their orders in the list of `javafx.scene.Node`, append one by one to element `<children>`.

The `writeFXMLRootPane` method is defined to accomplish these tasks:

Listing 1-8. Define `writeFXMLRootPane` method to write nodes one by one, append as descendant of root node `<Pane>`:

```
 void writeFXMLRootPane(Pane root, List<? extends javafx.scene.Node> list) {
    Element rootElm = document.createElement("Pane");
    document.appendChild(rootElm);
    // Write attribute:
    //   xmlns:fx="http://javafx.com/fxml"
    rootElm.setAttribute("xmlns:fx", "http://javafx.com/fxml");
    // Write nodes in list one by one
    writeFXMLFigures(list, rootElm);
    if (root != null) {
      writeProperties(root, rootElm);
    }
  }
```

The above method, first create an element `<Pane>` as the root node of a document, then call the `writeFXMLFigures` method, a recursive function, to create elements for JavaFX nodes as descendant of element `<Pane>`.

Listing 1-9. Define `writeFXMLFigures` method to create an element `<children>`, append to element `<pane>`, root node of document, and append nodes one by one to element `<children>`:

```
 void writeFXMLFigures(List<? extends javafx.scene.Node> list,
      Element rootElm) {
    Element childrenElm = document.createElement("children");
    rootElm.appendChild(childrenElm);
    for (javafx.scene.Node figure : list) {
      if (figure instanceof Group || figure instanceof Pane) {
        // For this release (V1.4): write group and
        // all classes derived from Pane (including Pane)
        Element figureElm = 
          document.createElement(figure.getClass().getSimpleName());
        childrenElm.appendChild(figureElm);
        // set common node attributes
        setNodeAttributes(figure, figureElm);
        writeProperties(figure, figureElm);
        // Use reflection mechanism to invoke getChildren method
        writeFXMLFigures(getNodeChildren(figure), figureElm);
      } else {
        writeFigure(figure, childrenElm);
      }
    }
  }

  void writeFigure(javafx.scene.Node figure, Element childrenElm) {
    String shapeTag = getSketchShapeTag(figure);
    Element shapeElm = document.createElement(shapeTag);
    childrenElm.appendChild(shapeElm);
    // set common node attributes
    setNodeAttributes(figure, shapeElm);

    if (figure instanceof Shape) {
      // set shape attributes
      setShapeAttributes((Shape)figure, shapeElm);
    } else if (figure instanceof ImageView) {
      // set imageview attributes
      setImageAttributes((ImageView)figure, shapeElm);
    } else {
      // add code here to write attributes for other types
      System.out.format(
        "DrawWriter V1.4 does not write attributes for %s yet%n",
        figure.getClass().getSimpleName());
    }

    // write properties (a map) after write imageview attributes
    writeProperties(figure, shapeElm);    
  }

  /**
   * Caller should ensure actual figure has a getChildren method
   */
  List <javafx.scene.Node> getNodeChildren(javafx.scene.Node figure) {
    List <javafx.scene.Node> nodeList = new ArrayList<>();
    try {
      List list = (List)invokeMethod(figure, "getChildren");
      for (Object obj : list) {
        nodeList.add((javafx.scene.Node)obj);
      }
    } catch (Exception e) {
      System.out.format("exception=%s%n", e);
    }
    return nodeList;
  } 

  /**
   * Invoke a method using Java reflection mechanism
   */ 
  Object invokeMethod(Object obj, String methodName, Object... args)
    throws Exception {
    Method method = obj.getClass().getMethod(methodName);
    method.setAccessible(true);
    return method.invoke(obj, args);    
  }
```

Following is an example of resulting DOM Document, in compliance with FXML format, saved in a file:

Listing 1-10. Contents of a resulting DOM Document saved in a file:

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?import java.lang.*?>
<?import java.util.*?>
<?import javafx.animation.*?>
<?import javafx.animation.PathTransition.*?>
<?import javafx.geometry.*?>
<?import javafx.scene.Group?>
<?import javafx.scene.control.*?>
<?import javafx.scene.effect.*?>
<?import javafx.scene.image.*?>
<?import javafx.scene.layout.*?>
<?import javafx.scene.paint.*?>
<?import javafx.scene.shape.*?>
<?import javafx.scene.text.*?>
<?import javafx.scene.transform.*?>
<?import javafx.util.*?>
<Pane xmlns:fx="http://javafx.com/fxml">
  <children>
    <Path fx:id="Path_12f3276" stroke="#A0522D">
      <elements>
        <MoveTo x="98.0" y="95.0"/>
        <QuadCurveTo controlX="139.0" controlY="51.0" x="186.0" y="95.0"/>
        <MoveTo x="60.0" y="169.0"/>
        <QuadCurveTo controlX="116.0" controlY="112.0" x="160.0" y="169.0"/>
        <QuadCurveTo controlX="208.0" controlY="222.0" x="260.0" y="169.0"/>
      </elements>
    </Path>
    <Circle centerX="125.0" centerY="40.0" fill="#FFD700" fx:id="Circle_e08379" radius="8.0"
    stroke="#FF7F50" translateX="130.36429647060191" translateY="133.15421741402582"/>
  </children>
</Pane>
```

Please note that, in the actual file, all processing instructions are formed in one line. In the above listing, we manually add line break after each processing instruction of Java `import` statement, for readability purpose.

### 1.1.4 Implement `writeImageView` Method

In addition to utilities for writing JavaFX shapes to FXML files, the `DrawWriter` class provides a practical method to write an `ImageView` object to an image file in png or gif format:

```
 public void writeImageView(ImageView iv, File file)
```

An `ImageView` object, rendering on a drawing board, maybe comes from a graphics editing function, such as image clipping or screen snapshot. Or, it may originally come from an FXML file, and be transformed by rotate, scale, translate, etc. In either case, we need a utility to save the edited image.

In this edition, we only support two image types, png and gif, because of the following write utility, defined in `javax.imageio.ImageIO` class, which writes an image to a file:

```
 static boolean write(RenderedImage im, String formatName, OutputStream output)
```

Testing result is that, not all formats work in the `ImageIO.write` method, only gif and png come out as expected.

The `ImageIO.write` method accepts an image of type `RenderedImage`, an interface resides in `java.awt.image` package.

We use utility provided in `javafx.embed.swing.SwingFXUtils` class, to convert a JavaFX `Image` to a `BufferedImage`:

```
 static BufferedImage fromFXImage(Image img,
                                   BufferedImage bimg)
```

The `BufferedImage` class extends `java.awt.Image` and implements `WritableRenderedImage`, a subinterface of `RenderedImage`.

#### 1.1.4.1 Snapshot an Image

Now we'll describe how to obtain a feasible JavaFX `Image` from the `ImageView` object, and to convert and then save to a file. Instead of getting the image specified in `image` property, we apply the `snapshot` method, defined in `Node` class, to acquire a new image:

```
public WritableImage snapshot(SnapshotParameters params,
                              WritableImage image)
```

The reason why we snapshot the `ImageView` is because the image specified in its `image` property is not synchronized with transformations applied onto it; any transformation, such as rotate, scale, shear, etc., performed on the `ImageView` doesn't alter its `image` property. And taking a snapshot of the `ImageView` comes out a new image, type of `WritableImage`, which is a direct subclass of `javafx.scene.image.Image`, conforms to all the transformations.

#### 1.1.4.2 Exploit `boundsInLocal` and `boundsInParent`

Inside the `writeImageView` Method, to snapshot an `ImageView`, need specify a proper viewport in a parameter, type of `SnapshotParameters`. Here's the method to obtain a bounding rectangle of a `Node` as viewport of snapshot:

`public final Bounds getBoundsInParent()`

The returned type, `Bounds`, an abstract class resided in `javafx.geometry` package, defines utilities to manipulate a rectangular region, measuring its coordinates and dimensions: minX, minY, maxX, maxY, width, height. To exploit the bounding rectangle of a `Node`, at first we need apprehend the differences between the following two properties defined in the `Node` class:

`boundsInLocal`

A property of type `ReadOnlyObjectProperty<Bounds>` specifies a `Bounds` object for a `Node`, without taking into account any transformation applied onto it.

`boundsInParent`

A property of type `ReadOnlyObjectProperty<Bounds>` specifies a `Bounds` object for a `Node`, taking into account all transformations, such as translate, scale, rotate, etc., applied onto it.

Let's use an `ImageView` object as below to illustrate `boundsInLocal` and `boundsInParent`:

Figure 1-2. Show initial bounding rectangle of `ImageView` object.

![](images/00008.jpeg "HeronBounds.png")

Initially, the `ImageView` object is displayed at location [100, 80], with width 347 and height 411 (that is the size of the image), and without any transformation applied to it yet; therefore, the `Bounds` in `boundsInLocal` and the `Bounds` in `boundsInParent` both specify identical values:

Initial `Bounds` of `ImageView`

|  | minX | minY | maxX | maxY | width | height |
| --- | --- | --- | --- | --- | --- | --- |
| `boundsInLocal` | 100 | 80 | 447 | 491 | 347 | 411 |
| `boundsInParent` | 100 | 80 | 447 | 491 | 347 | 411 |

Now, a transformation is applying to the `ImageView`; it is scaled by half of original size with center of the initial bounding rectangle as scale origin. Figure 1-3 below shows the `ImageView` and its `Bounds` after transformation. The smaller rectangular region indicates the `boundsInParent`, and the larger rectangular region is the `boundsInLocal` which stays unchanged.

Figure 1-3. Show bounding rectangles of `ImageView` after it is scaled by half of original size.

![](images/00009.jpeg "HeronBoundsScale.png")

After scaling, the `boundsInLocal` still keeps original values, and coordinates and dimensions in `boundsInParent` are changed. Here's the table showing the differences after we scale the `ImageView` to be half of original size:

`Bounds` of `ImageView` after scale

|  | minX | minY | maxX | maxY | width | height |
| --- | --- | --- | --- | --- | --- | --- |
| `boundsInLocal` | 100 | 80 | 447 | 491 | 347 | 411 |
| `boundsInParent` | 186.8 | 182.8 | 360.3 | 388.3 | 173.5 | 205.5 |

Now, we'll apply additional transformations to the `ImageView`, which has been scaled to be half of original size in Figure 1-3. At first, rotate 90° clockwise, and then translate [-32, 66]. Let's examine the final result of bounding rectangles in Figure 1-4:

Figure 1-4. Show bounding rectangles of `ImageView` after these transformations: scale 50%, rotate 90° clockwise, translate [-32, 66].

![](images/00010.jpeg "HeronBoundsScaleRotateTranslate.png")

In Figure 1-4, the smaller rectangular region indicates the `boundsInParent` after transformations. And the `boundsInLocal`, the larger rectangular region, remains the same.

To summarize, here's a table showing all transformations applied to the `ImageView`:

Transformations applied to `ImageView`

| scaleX | scaleY | rotate | translateX | translateY |
| --- | --- | --- | --- | --- |
| 0.5 | 0.5 | 90.0 | -32 | 66 |

And here's the table showing values in `boundsInLocal` and `boundsInParent` after transformations: scale down 50%, rotate 90° clockwise, translate [-32, 66]:

`Bounds` of `ImageView` after transformations

|  | minX | minY | maxX | maxY | width | height |
| --- | --- | --- | --- | --- | --- | --- |
| `boundsInLocal` | 100 | 80 | 447 | 491 | 347 | 411 |
| `boundsInParent` | 138.8 | 264.8 | 344.3 | 438.3 | 205.5 | 173.5 |

It's obvious that, no matter how many transformations applied to a node, its `boundsInLocal` always keeps the original values. Besides, take notes that set value for `layoutX` or `layoutY` property doesn't affect the `boundsInLocal` either.

The above examples conclude that the rectangular region specified in `boundsInParent` is the proper viewport for snapshot--in case the node has been transformed.

#### 1.1.4.3 Exploit `layoutBounds`

The `layoutBounds`, a property of type `ReadOnlyObjectProperty<Bounds>` defined in `Node` class, specifying a `Bounds` object, does not take into account these properties: `effect`, `clip`, `scaleX`, `scaleY`, `rotate`, `translateX`, `translateY`, `layoutX`, `layoutY`; and it also excludes any `Transform` object applied to a `Node`.

After clarifying the differences between `boundsInLocal` and `boundsInParent`, this section features `layoutBounds`, and makes comparisons of which with `boundsInLocal` and `boundsInParent`.

Likewise, we are using an `ImageView` object to view an image, Egret_1.png, as below to illustrate differences among `layoutBounds`, `boundsInLocal` and `boundsInParent`:

Figure 1-5. Show initial bounding rectangle of `ImageView` object.

![](images/00011.jpeg "EgretBounds.png")

Initially, the `ImageView` object is displayed at location [100, 80], with width 363 and height 303 (that is the size of the image), and without any `effect`, `clip`, or transformation applied to it yet; therefore, all three respective `Bounds` specify identical values:

Initial `Bounds` of `ImageView`

|  | minX | minY | maxX | maxY | width | height |
| --- | --- | --- | --- | --- | --- | --- |
| `layoutBounds` | 100 | 80 | 463 | 383 | 363 | 303 |
| `boundsInLocal` | 100 | 80 | 463 | 383 | 363 | 303 |
| `boundsInParent` | 100 | 80 | 463 | 383 | 363 | 303 |

Here's also a time to familiarize the syntax of FXML. The following show contents of an FXML file, which creates a simple scene graph, having a `Pane` as its root node, and an `ImageView` as the only child of the `Pane`:

Listing 1-11. Create an `ImageView` node in a scene graph using FXML:

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?import javafx.scene.image.*?>
<?import javafx.scene.layout.*?>
<Pane xmlns:fx="http://javafx.com/fxml">
  <children>
    <ImageView fx:id="ImageView_173b35c" preserveRatio="true" x="100.0" y="80.0">
      <image>
        <Image preserveRatio="false" smooth="false" url="@Egret_1.png"/>
      </image>
    </ImageView>
  </children>
</Pane>
```

Now, we'll create a `Path` object rendered as below:

Figure 1-6. Show a `Path` object filled interior in green color paint, and its bounding rectangle.

![](images/00012.jpeg "EgretMaskBounds.png")

Here's the FXML file in which a `Path` object is created, rendered in Figure 1-6:

Listing 1-12. Create a `Path` node in a scene graph using FXML:

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?import javafx.scene.layout.*?>
<?import javafx.scene.shape.*?>
<Pane xmlns:fx="http://javafx.com/fxml">
  <children>
    <Path fill="#00FF00" fx:id="Path_1cf1e34" stroke="#00FF00">
      <elements>
        <MoveTo x="194.0" y="206.0"/>
        <QuadCurveTo controlX="218.0" controlY="164.0" x="222.0" y="169.0"/>
        <QuadCurveTo controlX="205.0" controlY="190.0" x="234.0" y="204.0"/>
        <QuadCurveTo controlX="252.0" controlY="215.0" x="240.0" y="205.0"/>
        <QuadCurveTo controlX="256.0" controlY="212.0" x="265.0" y="209.0"/>
        <QuadCurveTo controlX="283.0" controlY="215.0" x="269.0" y="207.0"/>
        <QuadCurveTo controlX="291.0" controlY="213.0" x="291.0" y="227.0"/>
        <QuadCurveTo controlX="223.0" controlY="223.0" x="240.0" y="239.0"/>
        <QuadCurveTo controlX="67.0" controlY="258.0" x="151.0" y="334.0"/>
        <QuadCurveTo controlX="273.0" controlY="410.0" x="351.0" y="321.0"/>
        <QuadCurveTo controlX="435.0" controlY="224.0" x="353.0" y="250.0"/>
        <QuadCurveTo controlX="407.0" controlY="226.0" x="299.0" y="226.0"/>
        <QuadCurveTo controlX="291.0" controlY="213.0" x="295.0" y="210.0"/>
        <QuadCurveTo controlX="319.0" controlY="215.0" x="309.0" y="209.0"/>
        <QuadCurveTo controlX="323.0" controlY="209.0" x="315.0" y="207.0"/>
        <QuadCurveTo controlX="336.0" controlY="209.0" x="339.0" y="207.0"/>
        <QuadCurveTo controlX="369.0" controlY="217.0" x="367.0" y="209.0"/>
        <QuadCurveTo controlX="375.0" controlY="207.0" x="349.0" y="186.0"/>
        <QuadCurveTo controlX="328.0" controlY="174.0" x="358.0" y="186.0"/>
        <QuadCurveTo controlX="318.0" controlY="167.0" x="346.0" y="175.0"/>
        <QuadCurveTo controlX="314.0" controlY="163.0" x="330.0" y="163.0"/>
        <QuadCurveTo controlX="334.0" controlY="162.0" x="316.0" y="160.0"/>
        <QuadCurveTo controlX="261.0" controlY="135.0" x="246.0" y="150.0"/>
        <QuadCurveTo controlX="257.0" controlY="142.0" x="241.0" y="145.0"/>
        <QuadCurveTo controlX="219.0" controlY="145.0" x="235.0" y="142.0"/>
        <QuadCurveTo controlX="201.0" controlY="141.0" x="204.0" y="171.0"/>
        <QuadCurveTo controlX="205.0" controlY="180.0" x="194.0" y="204.0"/>
      </elements>
    </Path>
  </children>
</Pane>
```

The `Path` node is then set to the `clip` property of the `ImageView`. The following are elements in FXML, which carry out these tasks:

Listing 1-13. Show the FXML which creates a `Pane` as the root node of a scene graph, having a `ImageView` as the only child node of the `Pane`, and a `Path` node is created as clip of the `ImageView`:

```
<?import javafx.scene.layout.*?>
<?import javafx.scene.shape.*?>
<Pane xmlns:fx="http://javafx.com/fxml">
  <children>
    <ImageView fx:id="ImageView_173b35c" preserveRatio="true" x="100.0" y="80.0">
      <image>
        <Image preserveRatio="false" smooth="false" url="@Egret_1.png"/>
      </image>
      <clip>
        <Path fill="#00FF00" fx:id="Path_1cf1e34" stroke="#00FF00">
          <elements>
            <MoveTo x="194.0" y="206.0"/>
            <QuadCurveTo controlX="218.0" controlY="164.0" x="222.0" y="169.0"/>
            <QuadCurveTo controlX="205.0" controlY="190.0" x="234.0" y="204.0"/>
            <QuadCurveTo controlX="252.0" controlY="215.0" x="240.0" y="205.0"/>
            <QuadCurveTo controlX="256.0" controlY="212.0" x="265.0" y="209.0"/>
            <QuadCurveTo controlX="283.0" controlY="215.0" x="269.0" y="207.0"/>
            <QuadCurveTo controlX="291.0" controlY="213.0" x="291.0" y="227.0"/>
            <QuadCurveTo controlX="223.0" controlY="223.0" x="240.0" y="239.0"/>
            <QuadCurveTo controlX="67.0" controlY="258.0" x="151.0" y="334.0"/>
            <QuadCurveTo controlX="273.0" controlY="410.0" x="351.0" y="321.0"/>
            <QuadCurveTo controlX="435.0" controlY="224.0" x="353.0" y="250.0"/>
            <QuadCurveTo controlX="407.0" controlY="226.0" x="299.0" y="226.0"/>
            <QuadCurveTo controlX="291.0" controlY="213.0" x="295.0" y="210.0"/>
            <QuadCurveTo controlX="319.0" controlY="215.0" x="309.0" y="209.0"/>
            <QuadCurveTo controlX="323.0" controlY="209.0" x="315.0" y="207.0"/>
            <QuadCurveTo controlX="336.0" controlY="209.0" x="339.0" y="207.0"/>
            <QuadCurveTo controlX="369.0" controlY="217.0" x="367.0" y="209.0"/>
            <QuadCurveTo controlX="375.0" controlY="207.0" x="349.0" y="186.0"/>
            <QuadCurveTo controlX="328.0" controlY="174.0" x="358.0" y="186.0"/>
            <QuadCurveTo controlX="318.0" controlY="167.0" x="346.0" y="175.0"/>
            <QuadCurveTo controlX="314.0" controlY="163.0" x="330.0" y="163.0"/>
            <QuadCurveTo controlX="334.0" controlY="162.0" x="316.0" y="160.0"/>
            <QuadCurveTo controlX="261.0" controlY="135.0" x="246.0" y="150.0"/>
            <QuadCurveTo controlX="257.0" controlY="142.0" x="241.0" y="145.0"/>
            <QuadCurveTo controlX="219.0" controlY="145.0" x="235.0" y="142.0"/>
            <QuadCurveTo controlX="201.0" controlY="141.0" x="204.0" y="171.0"/>
            <QuadCurveTo controlX="205.0" controlY="180.0" x="194.0" y="204.0"/>
          </elements>
        </Path>
      </clip>
    </ImageView>
  </children>
</Pane>
```

The following figure shows the rendering of `ImageView` with the `Path` node set as its clip:

Figure 1-7. Show the `ImageView` with the `Path` node set as its clip.

![](images/00013.jpeg "EgretSetClip.png")

Now, let's illustrates the `ImageView` and its bounding rectangles after having a node set to its `clip` property.

Figure 1-8. Show the `ImageView` and its bounding rectangles after a `Path` node is set to its `clip` property.

![](images/00014.jpeg "EgretSetClipBounds.png")

Here's the table showing values in `layoutBounds`, `boundsInLocal` and `boundsInParent` after the `ImageView` is clipped:

`Bounds` of `ImageView` after it is clipped

|  | minX | minY | maxX | maxY | width | height |
| --- | --- | --- | --- | --- | --- | --- |
| `layoutBounds` | 100 | 80 | 463 | 383 | 363 | 303 |
| `boundsInLocal` | 122.5 | 141 | 394.5 | 370 | 272 | 229 |
| `boundsInParent` | 122.5 | 141 | 394.5 | 370 | 272 | 229 |

In Figure 1-8 shows the `ImageView` with a clip and two bounding rectangles; the larger rectangular region indicates the `layoutBounds`, and the smaller rectangular region indicates both `boundsInLocal` and `boundsInParent`. Clearly, after the `ImageView` is clipped, the `layoutBounds` remains the same, whereas both `boundsInLocal` and `boundsInParent` are changed to coincide with the bounding rectangle of the `Path`, which is set to the `clip` property of the `ImageView`, referring to [Figure 1-6](#part0007_split_001.html_figure-1-6).

Let's sum up in a nutshell:

1.  `layoutBounds` is not affected by these properties : `effect`, `clip`, `scaleX`, `scaleY`, `rotate`, `translateX`, `translateY`, `layoutX`, `layoutY`.
2.  All of the above mentioned properties affect `boundsInParent`.
3.  Among the above mentioned properties, only these properties affect `boundsInLocal`: `effect`, `clip`.
4.  Any `Transform` object added to an `ObservableList` of `Transform` and applied to a `Node`, affects only `boundsInParent`; it doesn't affect `layoutBounds` and `boundsInLocal`.

#### 1.1.4.4 Complete Source Code of `writeImageView` Method

Here's the complete source code of the `writeImageView` Method:

Import Statements:

```
import javafx.embed.swing.SwingFXUtils;
import javafx.geometry.Bounds;
import javafx.geometry.Rectangle2D;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.paint.Color;
import javafx.scene.SnapshotParameters;
import javax.imageio.ImageIO;
```

Listing 1-14. Define `writeImageView` Method to write an `ImageView` to an image file:

```
 /**
   * Write the image of a ImageView to an image file
   * Instead of using image specified in image property,
   * we apply snapshot method to obtain an image,
   * this is to have image conform to transformation
   * The image specified in image property of ImageView is
   * still the original image, not synchronized with transformation applied
   * Snapshot the ImageView comes out an image conformed to transformation
   * then, call writeImage to save the image to a file in
   * supported image format
   * Important notes: this method also works fine if the ImageView comes
   * with a clip specified in its clip property
   *   
   * @param iv
   * @param file 
   */
  public void writeImageView(ImageView iv, File file) {
    Bounds bP = iv.getBoundsInParent();
    Double minX = bP.getMinX();
    Double minY = bP.getMinY();
    Double w = bP.getWidth();
    double h = bP.getHeight();
    Rectangle2D vp = new Rectangle2D(minX, minY, w, h);
    SnapshotParameters parameters = new SnapshotParameters();
    parameters.setViewport(vp);
    parameters.setFill(Color.TRANSPARENT);
    Image image = iv.snapshot(parameters, null);
    writeImage(image, file);
  }

  /**
   * This method called from writeImageView to save
   * image of ImageView to an image file
   * Apply ImageIO.write method to write an JavaFX Image to file
   * After testing, ImageIO.write only works for
   *   png and gif formats 
   * ImagIO.write does not work for these formats:
   *   jpg, jpeg, bmp
   * This method first check if the given file has
   * extension matching preferred formats (png|gif)
   * if it doesn't match, concate default format (.png)
   * @param img
   * @param file
   * @return 
   */
  public File writeImage(Image img, File file) {
    // check if the given file extension matches preferred
    // image format string : (png|gif)
    String formatName = getFormatName(file);
    if (formatName == null) {
      // the given file does not ends with preferred image format
      // use "png" as format
      formatName = "png"; // default format name
      file = getImageFile(file, formatName);
    }
    writeFXImage(img, formatName, file);
    return file;
  }

  /**
   * Apply ImageIO.write method to write an JavaFX Image to file
   * Note: ImageIO.write cannot save jpg, jpeg, bmp
   */
  void writeFXImage(Image img, String formatName, File imgFile) {
    try {
      boolean succeed = ImageIO.write(
         SwingFXUtils.fromFXImage(img, null), formatName, imgFile);
      if (!succeed)
        System.out.println("ImageIO.write failed");
    } catch (IOException e) {
      System.out.println(e.getMessage());
    }
  }

  /**
   * Note for Java 8+, test if jpg,jpeg,bmp works
   * This method checks if file has preferred extension:
   *   png or gif,
   * if extension is not a preferred image format, 
   * return null, otherwise return image format
   * @param f
   * @return 
   */
  String getFormatName(File f) {
    String formatName = null; // Initialize to null
    // supported image format in regular expression
    //String reg = "(png|gif|jpg|jpeg|bmp)";
    // It would be nice to support jpg format
    // however,
    // jpg, jpeg and bmp not supported in ImagdIO.write
    // bmp do nothing, jpg,jpeg wrong image 
    String reg = "(png|gif)";
    String s = f.getName();
    int i = s.lastIndexOf('.');

    if (i > 0 && i < s.length() - 1) {
      String ext = s.substring(i + 1).toLowerCase();
      if (ext.matches(reg)) {
        formatName = ext;
      }
    }
    return formatName;
  }

  /**
   * This method is called from writeImageView method to
   * save the image of an ImageView to image file in
   * preferred format
   * Replacing file extension with given image format
   * If given file doesn't have any extension,
   * concat "." and format name
   * @return 
   */
  File getImageFile(File file, String formatName) {
    String s = file.getName();
    int i = s.lastIndexOf('.');
    if (i > 0 && i < s.length() - 1) {
      // replace whatever extension the given file has with .png
      s = s.substring(0, i);
      File p = file.getParentFile();
      String c = s + "." + formatName;
      return new File(p, c);
    } else {
      // file extension not exist, concat one
      return new File(file.getPath() + "." + formatName);
    }
  }
```

1.  ## 1.2 Create JavaFX Nodes in a Scene Graph using FXML

    We will elaborate on the usage of APIs provided in `draw.io` package, which contains `DrawWriter` class at this stage, when we implement `File` functionality within `JFXDrawTools V1.2` application in Chapter 3 of this book.

    In VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS, we have presented examples in Java code which create JavaFX nodes, such as `Line`, `Polyline`, `Polygon`, `Path`, etc.

    In this section, we'll demonstrate how to create the same JavaFX nodes, and more, in a scene graph in FXML markup, and also give you some examples of FXML files automatically generated from a JavaFX `Shape` builder, `JFXDrawTools V1.2`.

    And, in later chapters, we'll introduce utilities to load FXML files and demonstrate step by step how to build a tool to display nodes created in FXML markup.

    ### 1.2.1 Create `Line` specifying `strokeDashArray` in FXML

    The following is FXML markup which creates a `Pane` as root node of a scene graph, and a dash line, as its child node, with start point at (120, 120) and end point at (360, 360), and stroke width set to 4.0 pixels. Comments are put inside this element:

    ```
     <!--
      Put comments inside here
      //--> 
    ```

    Listing 1-15. Create a dash line with start point at (120, 120) and end point at (360, 360), and stroke width set to 4.0 pixels:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import java.lang.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Line startX="120.0" startY="120.0" endX="360.0" endY="360.0" strokeWidth="4.0">
          <!--
          Set lengths of dash and space in pixels
          16 for dash, 8 for space, 2 for dash, 8 for dash
          then repeat the pattern
          //-->
          <strokeDashArray>
            <Double fx:value="16.0"/>
            <Double fx:value="8.0"/>
            <Double fx:value="2.0"/>
            <Double fx:value="8.0"/>
          </strokeDashArray>
        </Line>
      </children>
    </Pane>
    ```

    A `Line` from above FXML markup is rendered as below:

    Figure 1-9. Show a dash line from above FXML markup.

    ![](images/00015.jpeg "dash_line.jpg")

    ### 1.2.2 Create `Polyline` for a Scene Graph in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and a `Polyline` composed of 5 line segments, given 6 points: (50.0, 20.0), (220.0, 170.0), (50.0, 320.0), (50.0, 250.0), (140.0, 170.0), (50.0, 90.0).

    Listing 1-16. Create a `Polyline` composed of 5 line segments, given 6 points:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import java.lang.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Polyline>
          <points>
            <Double fx:value="50.0"/>
            <Double fx:value="20.0"/>
            <Double fx:value="220.0"/>
            <Double fx:value="170.0"/>
            <Double fx:value="50.0"/>
            <Double fx:value="320.0"/>
            <Double fx:value="50.0"/>
            <Double fx:value="250.0"/>
            <Double fx:value="140.0"/>
            <Double fx:value="170.0"/>
            <Double fx:value="50.0"/>
            <Double fx:value="90.0"/>
          </points>
        </Polyline>
      </children>
    </Pane>
    ```

    A `Polyline` from above FXML markup is rendered as below:

    Figure 1-10. Show a polyline from above FXML markup.

    ![](images/00016.jpeg "example_polyline.jpg")

    ### 1.2.3 Create `Polygon` Shaped like Arrow in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and a `Polygon` composed of 6 line segments, given 6 points: (50.0, 20.0), (220.0, 170.0), (50.0, 320.0), (50.0, 250.0), (140.0, 170.0), (50.0, 90.0).

    Listing 1-17. Create a `Polygon` composed of 6 line segments, given 6 points:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import java.lang.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Polygon fill="#B3E6E6" stroke="#000000">
          <points>
            <Double fx:value="50.0"/>
            <Double fx:value="20.0"/>
            <Double fx:value="220.0"/>
            <Double fx:value="170.0"/>
            <Double fx:value="50.0"/>
            <Double fx:value="320.0"/>
            <Double fx:value="50.0"/>
            <Double fx:value="250.0"/>
            <Double fx:value="140.0"/>
            <Double fx:value="170.0"/>
            <Double fx:value="50.0"/>
            <Double fx:value="90.0"/>
          </points>
        </Polygon>
      </children>
    </Pane>
    ```

    A `Polygon` from above FXML markup is rendered as below:

    Figure 1-11. Show a polygon in arrow shape from above FXML markup.

    ![](images/00017.jpeg "example_polygon.jpg")

    ### 1.2.4 Create `Path` Formed a Chinese Character in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and a `Path` composed of a `MoveTo`, a `HLineTo`, a `QuadCurveTo`, and a `LineTo`. It takes 3 strokes to draw the path, in which the end point of first stroke is the start point of second stroke, and the end point of second stroke is the start point of third stroke.

    Listing 1-18. Create a `Path` composed of 4 `PathElement`s (3 strokes in total):

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Path stroke="#A0522D" strokeLineCap="ROUND" strokeLineJoin="BEVEL"
              strokeWidth="8.0">
          <elements>
            <MoveTo x="120.0" y="87.0"/>
            <HLineTo x="195.0"/>
            <QuadCurveTo controlX="36.0" controlY="201.0" x="205.0" y="170.0"/>
            <LineTo x="209.0" y="149.0"/>
          </elements>
        </Path>
      </children>
    </Pane>
    ```

    A `Path` from above FXML markup is rendered as below:

    Figure 1-12. Show a path from above FXML markup; it's a Chinese character 乙 composed of 3 strokes.

    ![](images/00018.jpeg "example_path_2.jpg")

    Please notice that four attributes presented within the `<path>` element produce distinct visual outcome on the path:

    `stroke`

    Specify a color to paint the border of a shape. Default value is `Color.BLACK` for a path.

    `strokeWidth`

    Specify the width of stroke.

    `strokeLineCap`

    Specify end cap style of a line, with one of these valid values: `BUTT`, `ROUND`, and `SQUARE`. Default value is `SQUARE`.

    `strokeLineJoin`

    Specify join style between lines, with one of these valid values: `BEVEL`, `MITER`, and `ROUND`. Default value is `MITER`.

    The following illustrates how `strokeLineCap` and `strokeLineJoin` affect the visual rendering of lines:

    Figure 1-13. Show 3 `Path` objects with different attributes set on `strokeLineCap` and `strokeLineJoin` respectively.

    ![](images/00019.jpeg "path_3_text.jpg")

    Here's FXML markup which creates 3 `Path` objects rendered as above.

    Listing 1-19. Create a `Path` composed of 4 `PathElement`s (3 strokes in total):

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Path stroke="#A0522D" strokeLineCap="ROUND" strokeLineJoin="BEVEL"
          strokeWidth="8.0">
          <elements>
            <MoveTo x="120.0" y="87.0"/>
            <HLineTo x="195.0"/>
            <QuadCurveTo controlX="36.0" controlY="201.0" x="205.0" y="170.0"/>
            <LineTo x="209.0" y="149.0"/>
          </elements>
        </Path>
        <Path stroke="#A0522D" strokeLineCap="BUTT" strokeLineJoin="ROUND"
          strokeWidth="8.0" translateX="143.0">
          <elements>
            <MoveTo x="120.0" y="87.0"/>
            <HLineTo x="195.0"/>
            <QuadCurveTo controlX="36.0" controlY="201.0" x="205.0" y="170.0"/>
            <LineTo x="209.0" y="149.0"/>
          </elements>
        </Path>
        <Path stroke="#A0522D" strokeLineCap="SQUARE" strokeLineJoin="MITER"
          strokeWidth="8.0" translateX="286.0">
          <elements>
            <MoveTo x="120.0" y="87.0"/>
            <HLineTo x="195.0"/>
            <QuadCurveTo controlX="36.0" controlY="201.0" x="205.0" y="170.0"/>
            <LineTo x="209.0" y="149.0"/>
          </elements>
        </Path>
      </children>
    </Pane>
    ```

    ### 1.2.5 Create `SVGPath` in Terms of `M`, `H`, `Q`, `L` Instructions in FXML

    Now, we'll use the same example, presented in [Listing 1-18](#part0007_split_002.html_listing-path-chinese-char) from Section [1.2.4 Create `Path` Formed a Chinese Character in FXML](#part0007_split_002.html_create-path), to illustrate a `SVGPath`. Here's FXML markup which creates the same shape shown in [Figure 1-12](#part0007_split_002.html_figure-chinese-char) using `SVGPath`.

    Listing 1-20. Create a `SVGPath` produces the same shape shown in [Figure 1-12](#part0007_split_002.html_figure-chinese-char):

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <SVGPath content="M 120 87 H 195 Q 36 201 205 170 L 209 149"
          fill="#00000000" stroke="#A0522D"
          strokeLineCap="ROUND" strokeLineJoin="BEVEL" strokeWidth="8.0">
        </SVGPath>
      </children>
    </Pane>
    ```

    The `content` attribute inside the `<SVGPath>` element specifies path data in a `String`. In our example, the following instructions are used: `M` (`moveto`), `H` (horizontal `lineto`), `Q` (quadratic Bézier `curveto`), `L` (`lineto`). To learn details about syntax of path data, read online documentation at here: [http://www.w3.org/TR/SVG/paths.html](http://www.w3.org/TR/SVG/paths.html)

    And for specification about the features and syntax for Scalable Vector Graphics (SVG) visit here: [http://www.w3.org/TR/SVG](http://www.w3.org/TR/SVG)

    ### 1.2.6 Create `Rectangle` Filled with `RadialGradient` in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and a `Rectangle` as its child node. `arcWidth` and `arcHeight` are attributes specifies dimensions of arcs at the four corner of a rounded rectangle. And a `RadialGradient` instance is created to fill the interior of the rectangle.

    Listing 1-21. Create a rounded `Rectangle` filled with `RadialGradient`:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.RadialGradient?>
    <?import javafx.scene.paint.Stop?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Rectangle x="88.0" y="66.0" width="268.0" height="148.0" stroke="#0000ff"
           arcWidth="67" arcHeight="62" strokeWidth="1.0">
          <fill>
            <RadialGradient centerX="0.5" centerY="0.5" radius="1"
              focusDistance="0.4" focusAngle="60.0"
              proportional="true" cycleMethod="NO_CYCLE">
              <stops>
                <Stop offset="0" color="#ffff00"/>
                <Stop offset="0.45" color="#008000"/>
                <Stop offset="1" color="#0000ff"/>
              </stops>
            </RadialGradient>
          </fill>
        </Rectangle>
      </children>
    </Pane>
    ```

    A `Rectangle` from above FXML markup is rendered as below:

    Figure 1-14. Show a rounded `Rectangle`, filled with `RadialGradient`, from above FXML markup.

    ![](images/00020.jpeg "rectangle_gradient.jpg")

    ### 1.2.7 Create `Circle` Filled with `LinearGradient` in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and a `Circle` as its child node. And a `LinearGradient` instance is created to fill the interior of the circle.

    Listing 1-22. Create a `Circle` filled with `LinearGradient`:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.LinearGradient?>
    <?import javafx.scene.paint.Stop?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Circle centerX="166.0" centerY="144.0" radius="100.0"
          stroke="#e6e6d3" strokeWidth="1.0">
          <fill>
            <LinearGradient startX="0.0" startY="0.0" endX="0.0" endY="1.0"
              proportional="true" cycleMethod="NO_CYCLE">
              <stops>
                <Stop offset="0" color="#ffe4e1"/>
                <Stop offset="0.33" color="#fafad2"/>
                <Stop offset="0.66" color="#d8bfd8"/>
                <Stop offset="1" color="#ffc0cb"/>
              </stops>
            </LinearGradient>
          </fill>
        </Circle>
      </children>
    </Pane>
    ```

    A `Circle` from above FXML markup is rendered as below:

    Figure 1-15. Show a `Circle`, filled with `LinearGradient`, from above FXML markup.

    ![](images/00021.jpeg "circle_gradient.jpg")

    ### 1.2.8 Create `Ellipse` with `Transform` and `Effect` in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and an `Ellipse` as its child node. Two types of transformations, `Shear` and `Translate`, as well as a `DropShadow` effect are applied to the `Ellipse`.

    Listing 1-23. Create an `Ellipse` with `Transform` and `Effect` applied to it:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.effect.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.LinearGradient?>
    <?import javafx.scene.paint.Stop?>
    <?import javafx.scene.shape.*?>
    <?import javafx.scene.transform.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Ellipse centerX="220.0" centerY="180.0" radiusX="86.0" radiusY="120.0"
          fill="#00000000" strokeWidth="12.0">
          <transforms>
            <Shear x="-0.5"/>
            <Translate x="180.0"/>
          </transforms>
          <effect>
            <DropShadow offsetX="8" offsetY="6" color="#696969"/>
          </effect>
          <stroke>
            <LinearGradient startX="0.0" startY="0.0" endX="0.0" endY="1.0"
              proportional="true" cycleMethod="NO_CYCLE">
              <stops>
                <Stop offset="0" color="#ffe4e1"/>
                <Stop offset="0.33" color="#afeeee"/>
                <Stop offset="0.66" color="#d8bfd8"/>
                <Stop offset="1" color="#9370db"/>
              </stops>
            </LinearGradient>
          </stroke>
        </Ellipse>
      </children>
    </Pane>
    ```

    An `Ellipse` from above FXML markup is rendered as below:

    Figure 1-16. Show an `Ellipse` from above FXML markup, with `Shear` and `Translate` transformations, and `DropShadow` effect.

    ![](images/00022.jpeg "ellipse_transforms.jpg")

    For comparison, here's how the original `Ellipse` looks like, before `Shear` and `Translate` transformations, and before `DropShadow` effect are applied onto it:

    Figure 1-17. Show the `Ellipse` before applying transformations and effect to it.

    ![](images/00023.jpeg "ellipse.jpg")

    ### 1.2.9 Create `Arc` Painted like Rainbow in FXML

    Here's a demonstration of rendering a rainbow shape using an `Arc` as a mask to clip an `Ellipse`:

    1.  Create an `Ellipse` filled with `RadialGradient` that emulates the rainbow colors.
    2.  Create an `Arc` with `centerX`, `centerY`, `radiusX`, `radiusY` same as the `Ellipse`. And be aware of the significance of these attributes of `Arc` -- `stroke`, `strokeWidth`, `fill`, `startAngle`, `length`, and `type` -- which determine the size and shape of the rainbow.
    3.  Set the `Arc` as the value of `clip` property of the `Ellipse`.

    The following is FXML markup to render an `Arc` of rainbow:

    Listing 1-24. Create `Ellipse` with `Arc` as mask to clip a rainbow shape:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.RadialGradient?>
    <?import javafx.scene.paint.Stop?>
    <?import javafx.scene.shape.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Ellipse centerX="292" centerY="220" radiusX="180.0" radiusY="180.0">
          <fill>
            <RadialGradient centerX="0.5" centerY="0.5" radius="0.5"
              proportional="true" cycleMethod="NO_CYCLE">
              <stops>
                <Stop offset="0" color="#ff0000"/>
                <Stop offset="0.7" color="#ee82ee"/>
                <Stop offset="0.75" color="#8a2be2"/>
                <Stop offset="0.8" color="#87cefa"/>
                <Stop offset="0.85" color="#00ff00"/>
                <Stop offset="0.9" color="#ffff00"/>
                <Stop offset="0.95" color="#ffa500"/>
                <Stop offset="1" color="#ff0000"/>
              </stops>
            </RadialGradient>
          </fill>
          <clip>
            <Arc centerX="292" centerY="220" radiusX="180.0" radiusY="180.0"
              startAngle="0.0" length="180.0" type="OPEN"
              stroke="#000000" strokeType="INSIDE" strokeWidth="45.0" fill="#00000000">
            </Arc>
          </clip>
        </Ellipse>
      </children>
    </Pane>
    ```

    An `Arc` of rainbow from above FXML markup is rendered as below:

    Figure 1-18. Show an `Arc` of rainbow from above FXML markup.

    ![](images/00024.jpeg "arc_rainbow.jpg")

    ### 1.2.10 Create `Text` with Visual Effect and Shearing Transform in FXML

    The following listing shows FXML markup which creates a `Pane` as root node of a scene graph, and a `Text` filled with `LinearGradient` as its child node. An `InnerShadow` visual effect is applied to the `Text`.

    Listing 1-25. Create `Text`, applying `InnerShadow` visual effect, and filled with `LinearGradient`:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.effect.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.LinearGradient?>
    <?import javafx.scene.paint.Stop?>
    <?import javafx.scene.shape.*?>
    <?import javafx.scene.text.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Text stroke="000000" strokeType="OUTSIDE"
          layoutX="20.0" layoutY="82.0" pickOnBounds="true"
          text="Hello！你好！" textOrigin="TOP">
          <font>
            <Font name="MS UI Gothic" size="100.0"/>
          </font>
          <effect>
            <InnerShadow offsetX="2.5" offsetY="0.5" color="#ffff00"/>
          </effect>
          <fill>
            <LinearGradient startX="0.0" startY="0.0" endX="1.0" endY="0.0"
              proportional="true" cycleMethod="NO_CYCLE">
              <stops>
                <Stop offset="0" color="#ffd700"/>
                <Stop offset="0.2" color="#ffa500"/>
                <Stop offset="0.7" color="#ff8c00"/>
                <Stop offset="1" color="#ff0000"/>
              </stops>
            </LinearGradient>
          </fill>
        </Text>
      </children>
    </Pane>
    ```

    A `Text` from above FXML markup is rendered as below:

    Figure 1-19. Show a `Text`, applying `InnerShadow` effect, and filled with `LinearGradient`.

    ![](images/00025.jpeg "text_inner_shadow.jpg")

    The following listing shows FXML markup which creates a `Text`, applying chain effects and `Shear` transform, and filled with `LinearGradient`. Please notice that a `Reflection` set as the input of an `InnerShadow`, which then is set as the input of `DropShadow` effect, results in chain effects.

    Listing 1-26. Create `Text`, applying chain effects and `Shear` transform, and filled with `LinearGradient`:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import javafx.scene.effect.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.LinearGradient?>
    <?import javafx.scene.paint.Stop?>
    <?import javafx.scene.shape.*?>
    <?import javafx.scene.text.*?>
    <?import javafx.scene.transform.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Text strokeType="OUTSIDE" layoutX="42.0" layoutY="30.0" pickOnBounds="true"
          text="Hello！你好！" textOrigin="TOP">
          <font>
            <Font name="MS UI Gothic" size="100.0"/>
          </font>
          <transforms>
            <Shear pivotX="100.0" pivotY="10.0" x="-0.2" y="0.4"/>
          </transforms>
          <effect>
            <DropShadow offsetX="3.0" offsetY="3.0"	color="#696969" 
              blurType="TWO_PASS_BOX">
              <input>
                <InnerShadow offsetX="3.0" offsetY="0.0" color="#FFF171">
                  <input>
                    <Reflection fraction="0.9" topOpacity="0.4"/>
                  </input>
                </InnerShadow>
              </input>
            </DropShadow>
          </effect>
          <fill>
            <LinearGradient startX="0.0" startY="0.0" endX="1.0" endY="0.0"
              proportional="true" cycleMethod="NO_CYCLE">
              <stops>
                <Stop offset="0" color="#ffd700"/>
                <Stop offset="0.2" color="#ffa500"/>
                <Stop offset="0.7" color="#ff8c00"/>
                <Stop offset="1" color="#ff0000"/>
              </stops>
            </LinearGradient>
          </fill>
        </Text>
      </children>
    </Pane>
    ```

    A `Text` from above FXML markup is rendered as below:

    Figure 1-20. Show a `Text`, applying chain effects and `Shear` transform, and filled with `LinearGradient`.

    ![](images/00026.jpeg "text_chain_effects.jpg")

    ### 1.2.11 Generate FXML Files from a Shape Builder

    Here we'll illustrate some FXML files generated from a JavaFX `Shape` builder, `JFXDrawTools V1.2`.

    The first example shows a `Path` object and an `ImageView` object interactively created on the drawing board of the `JFXDrawTools V1.2` application.

    The `Path` object is constructed using `Bézier Curve Drawer` module, referring to VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS Chapter 5 Quadratic Bézier Curve Drawer, and Chapter 7 Enhanced Draw Tool with Predefined Drawers Section 7.2.5 Implement BezierCurveDrawer Class, for detailed descriptions.

    And the `ImageView` object is created by the `DrawLoader.loadImage` method, to be discussed in next chapter.

    Figure 1-21. Draw a path composed of quadratic Bézier curves, and load a ginkgo leaf image, using `JFXDrawTools V1.2` application.

    ![](images/00027.jpeg "draw_gingo_leaf.jpg")

    Here are the contents of FXML file, GingoLeaf.fxml, saved for sketch displayed in Figure 1-21 using APIs provided in our `drawtool.io` package.

    Listing 1-27. Contents of GingoLeaf.fxml file, generated from `JFXDrawTools V1.2` application, saved for sketch displayed in Figure 1-21:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import java.lang.*?>
    <?import java.util.*?>
    <?import javafx.animation.*?>
    <?import javafx.animation.PathTransition.*?>
    <?import javafx.geometry.*?>
    <?import javafx.scene.Group?>
    <?import javafx.scene.control.*?>
    <?import javafx.scene.effect.*?>
    <?import javafx.scene.image.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.*?>
    <?import javafx.scene.shape.*?>
    <?import javafx.scene.text.*?>
    <?import javafx.scene.transform.*?>
    <?import javafx.util.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Path fx:id="Path_9e7c70" stroke="#A0522D">
          <elements>
            <MoveTo x="53.0" y="53.0"/>
            <QuadCurveTo controlX="85.0" controlY="26.0" x="98.0" y="31.0"/>
            <QuadCurveTo controlX="109.0" controlY="32.0" x="110.0" y="37.0"/>
            <QuadCurveTo controlX="128.0" controlY="32.0" x="128.0" y="38.0"/>
            <QuadCurveTo controlX="148.0" controlY="36.0" x="148.0" y="41.0"/>
            <QuadCurveTo controlX="174.0" controlY="41.0" x="173.0" y="56.0"/>
            <QuadCurveTo controlX="188.0" controlY="60.0" x="186.0" y="66.0"/>
            <QuadCurveTo controlX="210.0" controlY="73.0" x="204.0" y="83.0"/>
            <QuadCurveTo controlX="225.0" controlY="97.0" x="218.0" y="105.0"/>
            <QuadCurveTo controlX="125.0" controlY="139.0" x="123.0" y="167.0"/>
            <QuadCurveTo controlX="132.0" controlY="252.0" x="143.0" y="267.0"/>
            <QuadCurveTo controlX="139.0" controlY="269.0" x="137.0" y="269.0"/>
            <QuadCurveTo controlX="119.0" controlY="167.0" x="120.0" y="165.0"/>
            <QuadCurveTo controlX="66.0" controlY="65.0" x="47.0" y="75.0"/>
            <QuadCurveTo controlX="39.0" controlY="59.0" x="53.0" y="53.0"/>
            <MoveTo x="125.0" y="42.0"/>
            <QuadCurveTo controlX="120.0" controlY="161.0" x="120.0" y="161.0"/>
            <MoveTo x="182.0" y="65.0"/>
            <QuadCurveTo controlX="120.0" controlY="163.0" x="120.0" y="163.0"/>
            <MoveTo x="68.0" y="54.0"/>
            <QuadCurveTo controlX="121.0" controlY="161.0" x="121.0" y="161.0"/>
            <MoveTo x="153.0" y="49.0"/>
            <QuadCurveTo controlX="121.0" controlY="164.0" x="121.0" y="164.0"/>
            <MoveTo x="91.0" y="35.0"/>
            <QuadCurveTo controlX="121.0" controlY="166.0" x="121.0" y="166.0"/>
            <MoveTo x="196.0" y="81.0"/>
            <QuadCurveTo controlX="121.0" controlY="158.0" x="121.0" y="158.0"/>
            <MoveTo x="208.0" y="93.0"/>
            <QuadCurveTo controlX="144.0" controlY="137.0" x="144.0" y="137.0"/>
            <MoveTo x="186.0" y="73.0"/>
            <QuadCurveTo controlX="141.0" controlY="135.0" x="141.0" y="135.0"/>
            <MoveTo x="166.0" y="52.0"/>
            <QuadCurveTo controlX="128.0" controlY="147.0" x="128.0" y="147.0"/>
            <MoveTo x="136.0" y="47.0"/>
            <QuadCurveTo controlX="121.0" controlY="155.0" x="121.0" y="155.0"/>
            <MoveTo x="105.0" y="42.0"/>
            <QuadCurveTo controlX="118.0" controlY="140.0" x="118.0" y="140.0"/>
            <MoveTo x="78.0" y="45.0"/>
            <QuadCurveTo controlX="112.0" controlY="138.0" x="112.0" y="138.0"/>
            <MoveTo x="116.0" y="42.0"/>
            <QuadCurveTo controlX="120.0" controlY="132.0" x="120.0" y="132.0"/>
            <MoveTo x="172.0" y="61.0"/>
            <QuadCurveTo controlX="136.0" controlY="134.0" x="136.0" y="134.0"/>
            <MoveTo x="145.0" y="47.0"/>
            <QuadCurveTo controlX="127.0" controlY="138.0" x="127.0" y="138.0"/>
            <MoveTo x="56.0" y="61.0"/>
            <QuadCurveTo controlX="101.0" controlY="126.0" x="101.0" y="126.0"/>
            <MoveTo x="211.0" y="101.0"/>
            <QuadCurveTo controlX="179.0" controlY="117.0" x="179.0" y="117.0"/>
            <MoveTo x="198.0" y="88.0"/>
            <QuadCurveTo controlX="166.0" controlY="115.0" x="166.0" y="115.0"/>
            <MoveTo x="157.0" y="55.0"/>
            <QuadCurveTo controlX="145.0" controlY="97.0" x="145.0" y="97.0"/>
            <MoveTo x="86.0" y="42.0"/>
            <QuadCurveTo controlX="99.0" controlY="90.0" x="99.0" y="90.0"/>
            <MoveTo x="71.0" y="49.0"/>
            <QuadCurveTo controlX="95.0" controlY="102.0" x="95.0" y="102.0"/>
            <MoveTo x="99.0" y="42.0"/>
            <QuadCurveTo controlX="111.0" controlY="112.0" x="111.0" y="112.0"/>
            <MoveTo x="64.0" y="61.0"/>
            <QuadCurveTo controlX="95.0" controlY="112.0" x="95.0" y="112.0"/>
            <MoveTo x="100.0" y="94.0"/>
            <QuadCurveTo controlX="111.0" controlY="132.0" x="111.0" y="132.0"/>
            <MoveTo x="131.0" y="45.0"/>
            <QuadCurveTo controlX="126.0" controlY="100.0" x="126.0" y="100.0"/>
            <MoveTo x="176.0" y="65.0"/>
            <QuadCurveTo controlX="152.0" controlY="108.0" x="152.0" y="108.0"/>
            <MoveTo x="111.0" y="62.0"/>
            <QuadCurveTo controlX="116.0" controlY="110.0" x="116.0" y="110.0"/>
            <MoveTo x="189.0" y="80.0"/>
            <QuadCurveTo controlX="160.0" controlY="114.0" x="160.0" y="114.0"/>
            <MoveTo x="122.0" y="164.0"/>
            <QuadCurveTo controlX="138.0" controlY="265.0" x="138.0" y="265.0"/>
          </elements>
        </Path>
        <ImageView fx:id="ImageView_452209" preserveRatio="true" translateX="8.0"
              translateY="55.0" x="211.65218353271484" y="0.5">
          <image>
            <Image preserveRatio="false" smooth="false" url="@GingoLeaf_1.png"/>
          </image>
          <properties imageURL="file:/F:/My%20Documents/DocRoot/SHUFEN_JAVA/MyBookJFX\VolumeFour/JFXDrawTools1.2/src/example1/myfxml/GingoLeaf_1.png"/>
        </ImageView>
      </children>
    </Pane>
    ```

    The next example shows a smiling face, constructed using `Bézier Curve Drawer` module and `Circle Drawer` module in `JFXDrawTools V1.2` application.

    For detailed descriptions of `Circle Drawer` module, please refer to VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS Chapter 7 Enhanced Draw Tool with Predefined Drawers Section 7.2.7 Implement CircleDrawer Class.

    Figure 1-22. Draw a smiling face using `JFXDrawTools V1.2` application.

    ![](images/00028.jpeg "draw_smile_face.jpg")

    Here are the contents of FXML file, SmileFace.fxml, saved for sketch displayed in Figure 1-22 using APIs provided in our `drawtool.io` package.

    Listing 1-28. Contents of SmileFace.fxml file, generated from `JFXDrawTools V1.2` application, saved for sketch displayed in Figure 1-22:

    ```
    <?xml version="1.0" encoding="UTF-8" standalone="no"?>
    <?import java.lang.*?>
    <?import java.util.*?>
    <?import javafx.animation.*?>
    <?import javafx.animation.PathTransition.*?>
    <?import javafx.geometry.*?>
    <?import javafx.scene.Group?>
    <?import javafx.scene.control.*?>
    <?import javafx.scene.effect.*?>
    <?import javafx.scene.image.*?>
    <?import javafx.scene.layout.*?>
    <?import javafx.scene.paint.*?>
    <?import javafx.scene.shape.*?>
    <?import javafx.scene.text.*?>
    <?import javafx.scene.transform.*?>
    <?import javafx.util.*?>
    <Pane xmlns:fx="http://javafx.com/fxml">
      <children>
        <Circle centerX="193.0" centerY="100.0" fill="#FFD700" fx:id="Circle_12f2476"
              radius="22.80350850198276" stroke="#FF7F50"/>
        <Circle centerX="182.0" centerY="95.0" fill="#FFD700" fx:id="Circle_d60f6e"
              radius="3.0" stroke="#FF7F50"/>
        <Circle centerX="204.0" centerY="95.0" fill="#FFD700" fx:id="Circle_724357"
              radius="3.0" stroke="#FF7F50"/>
        <Path fx:id="Path_119f33d" stroke="#A0522D">
          <elements>
            <MoveTo x="177.0" y="106.0"/>
            <QuadCurveTo controlX="197.0" controlY="126.0" x="211.0" y="103.0"/>
          </elements>
        </Path>
        <Circle centerX="193.0" centerY="103.0" fill="#FFD700" fx:id="Circle_19f1aa5"
              radius="1.0" stroke="#FF7F50"/>
      </children>
    </Pane>
    ```

1.  ## 1.3 Complete Source Code of `DrawWriter` Class

    Listing 1-29. Complete source code of `DrawWriter` class:

    ```
    package drawtool.io;

    import java.io.*;
    import java.lang.reflect.Method;
    import java.util.*;
    import javafx.animation.*;
    import javafx.collections.ObservableList;
    import javafx.embed.swing.SwingFXUtils;
    import javafx.geometry.Bounds;
    import javafx.geometry.Rectangle2D;
    import javafx.geometry.VPos;
    import javafx.scene.SnapshotParameters;
    import javafx.scene.Group;
    import javafx.scene.effect.*;
    import javafx.scene.image.Image;
    import javafx.scene.image.ImageView;
    import javafx.scene.layout.Pane;
    import javafx.scene.paint.*;
    import javafx.scene.shape.*;
    import javafx.scene.text.Font;
    import javafx.scene.text.FontSmoothingType;
    import javafx.scene.text.TextAlignment;
    import javafx.scene.text.TextBoundsType;
    import javafx.scene.transform.*;
    import javafx.util.Duration;
    import javax.imageio.ImageIO;
    import javax.xml.parsers.*;
    import javax.xml.transform.*;
    import javax.xml.transform.dom.*;
    import javax.xml.transform.stream.*;
    import org.w3c.dom.*;

    /**
     * File Name: DrawWriter.java
     * (in directory: DrawTool1.4/src/example1/drawtool/io)
     * DrawWriter class provides these APIs:
     *  writeFXML, writeImageView
     *
     * writeFXML method writes a Pane or a list of Node objects
     * to file in FXML format
     * writeFigure method writes properties defined in these types:
     *   Shape, ImageView
     * For the other types of nodes,
     * only properties inherited from Node class are taken care of
     * However the structure is expandable, it's easy to add code to
     * support the other types comprehensively
     *
     * writeImageView method writes an ImageView to image file
     * in png or gif format
     *
     * @author Shufen Kuo
     */

    public class DrawWriter {
      DocumentBuilderFactory documentBuilderFactory;
      DocumentBuilder documentBuilder;
      TransformerFactory transformerFactory;
      Transformer transformer;
      Document document;
      File fxmlFile;

      // This is for writing raster image of an ImageView object to file
      // The image of an ImageView object may come from snapshot, we need
      // create an image file for it.
      // In the case the FXML file name is "JFXDrawTools.fxml", we will give
      // image file names: JFXDrawTools_1.png, JFXDrawTools_2.png, ...
      static int imageFileCount; 

      /**
       * Write pane to file
       * first write children list
       * then write properties (a map) of pane
       * We assume all nodes referenced by objects in properties (a map) are
       * existing in children list of pane.
       *  For example, if a Shape object is specified in path property of a
       *  PathTransition object stored in properties map, the Shape object must
       *  be a child node of pane, otherwise later when the file is loaded back,
       *  FXML loader can not resolve the object reference 
       */
      public void writeFXML(Pane pane, File file) {
        initMyFXMLDocument(file);
        writeFXMLHeader();
        writeFXMLRootPane(pane, pane.getChildren());
        writeMyFXMLDocument();
      }

      /**
       * Write a list of node to file
       * Write <Pane> as root node to FXML file
       * All nodes hold in the given list are saved to file as
       * children of Pane 
       */
      public void writeFXML(List<? extends javafx.scene.Node> list, File file)  {
        // if list is null, create a file with empty nodes
        initMyFXMLDocument(file);
        writeFXMLHeader();
        writeFXMLRootPane(null, list);
        writeMyFXMLDocument();
      }

      /**
       * Write the image of an ImageView to an image file
       * Instead of using image specified in image property,
       * we apply snapshot method to obtain an image,
       * this is to have image conform to transformations
       * The image specified in image property of ImageView is
       * still the original image,
       * not synchronized with transformations applied
       * Snapshot the ImageView comes out an image conformed
       * to transformations, and then call writeImage
       * to save the image to a file in supported image format
       * Important notes: this method also works fine if the ImageView 
       * comes with a clip specified in its clip property
       *   
       * @param iv
       * @param file 
       */
      public void writeImageView(ImageView iv, File file) {
        Bounds bP = iv.getBoundsInParent();
        Double minX = bP.getMinX();
        Double minY = bP.getMinY();
        Double w = bP.getWidth();
        double h = bP.getHeight();
        Rectangle2D vp = new Rectangle2D(minX, minY, w, h);
        SnapshotParameters parameters = new SnapshotParameters();
        parameters.setViewport(vp);
        parameters.setFill(Color.TRANSPARENT);
        Image image = iv.snapshot(parameters, null);
        writeImage(image, file);
      }

      void initMyFXMLDocument(File file) {
        try {
          // only create once
          if (documentBuilderFactory == null) {
            documentBuilderFactory = DocumentBuilderFactory.newInstance();
            documentBuilder = documentBuilderFactory.newDocumentBuilder();
            transformerFactory = TransformerFactory.newInstance();
            transformer = transformerFactory.newTransformer();
            transformer.setOutputProperty(OutputKeys.METHOD, "xml");
            transformer.setOutputProperty(OutputKeys.INDENT, "yes");
            transformer.setOutputProperty(
                "{http://xml.apache.org/xslt}indent-amount", "2");
          }

          this.fxmlFile = file;
          this.imageFileCount = 0; // always reset to 0
          document = documentBuilder.newDocument(); // always create new doc
        } catch (ParserConfigurationException e) {
          System.out.println(e.getMessage());
        } catch (TransformerConfigurationException e) {
          System.out.println(e.getMessage());
        } 
      }

      void writeMyFXMLDocument() {
        try {
          DOMSource source = new DOMSource(document);
          StreamResult result = new StreamResult(fxmlFile);
          transformer.transform(source, result);
        } catch (TransformerException e) {
          System.out.println(e.getMessage());
        }
      }

      /**
       * Write import statements before root node <Pane>
       * Note: ProcessingInstruction has no line break
       */
      void writeFXMLHeader() {    
        document.appendChild(importInstruction("java.lang.*"));
        document.appendChild(importInstruction("java.util.*"));
        document.appendChild(importInstruction("javafx.animation.*"));
        document.appendChild(importInstruction("javafx.animation.PathTransition.*"));
        document.appendChild(importInstruction("javafx.geometry.*"));
        document.appendChild(importInstruction("javafx.scene.Group"));
        document.appendChild(importInstruction("javafx.scene.control.*"));
        document.appendChild(importInstruction("javafx.scene.effect.*"));
        document.appendChild(importInstruction("javafx.scene.image.*"));
        document.appendChild(importInstruction("javafx.scene.layout.*"));
        document.appendChild(importInstruction("javafx.scene.paint.*"));
        document.appendChild(importInstruction("javafx.scene.shape.*"));
        document.appendChild(importInstruction("javafx.scene.text.*"));
        document.appendChild(importInstruction("javafx.scene.transform.*"));
        document.appendChild(importInstruction("javafx.util.*"));
      }

      ProcessingInstruction importInstruction(String data) {
        return document.createProcessingInstruction("import", data);
      }  

      /** 
       * Create a Pane element as root of scene graph
       * Write the list of nodes as children of Pane
       * Do not call this method before document initialization is completed
       * First write list of node
       * then write properties of pane
       * JFXDrawTools use properties (a map) to store application data, such as
       *   Animation objects created dynamically
       */
      void writeFXMLRootPane(Pane root, List<? extends javafx.scene.Node> list) {
        Element rootElm = document.createElement("Pane");
        document.appendChild(rootElm);
        // Write attribute: xmlns:fx="http://javafx.com/fxml"
        rootElm.setAttribute("xmlns:fx", "http://javafx.com/fxml");
        // Write nodes in list one by one
        writeFXMLFigures(list, rootElm);
        if (root != null) {
          writeProperties(root, rootElm);
        }
      }

      /**
       * Iterate list of nodes
       */
      void writeFXMLFigures(List<? extends javafx.scene.Node> list,
          Element rootElm) {
        Element childrenElm = document.createElement("children");
        rootElm.appendChild(childrenElm);
        for (javafx.scene.Node figure : list) {
          if (figure instanceof Group || figure instanceof Pane) {
            // For this release (V1.4): write group and
            // all classes derived from Pane (including Pane)
            Element figureElm = 
              document.createElement(figure.getClass().getSimpleName());
            childrenElm.appendChild(figureElm);
            // set common node attributes
            setNodeAttributes(figure, figureElm);
            writeProperties(figure, figureElm);
            // Use reflection mechanism to invoke getChildren method
            writeFXMLFigures(getNodeChildren(figure), figureElm);
          } else {
            writeFigure(figure, childrenElm);
          }
        }
      }

      /**
       * 
       */
      void writeFigure(javafx.scene.Node figure, Element childrenElm) {
        String shapeTag = getSketchShapeTag(figure);
        Element shapeElm = document.createElement(shapeTag);
        childrenElm.appendChild(shapeElm);
        // set common node attributes
        setNodeAttributes(figure, shapeElm);

        if (figure instanceof Shape) {
          // set shape attributes
          setShapeAttributes((Shape)figure, shapeElm);
        } else if (figure instanceof ImageView) {
          // set imageview attributes
          setImageAttributes((ImageView)figure, shapeElm);
        } else {
          // add code here to write attributes for other types
          System.out.format(
            "DrawWriter V1.4 does not write attributes for %s yet%n",
            figure.getClass().getSimpleName());
        }

        // write properties (a map) after write imageview attributes
        writeProperties(figure, shapeElm);    
      }

      /**
       * Caller should ensure actual figure has a getChildren method
       */
      List <javafx.scene.Node> getNodeChildren(javafx.scene.Node figure) {
        List <javafx.scene.Node> nodeList = new ArrayList<>();
        try {
          List list = (List)invokeMethod(figure, "getChildren");
          for (Object obj : list) {
            nodeList.add((javafx.scene.Node)obj);
          }
        } catch (Exception e) {
          System.out.format("exception=%s%n", e);
        }
        return nodeList;
      } 

      /**
       * Invoke a method using Java reflection mechanism
       */ 
      Object invokeMethod(Object obj, String methodName, Object... args)
        throws Exception {
        Method method = obj.getClass().getMethod(methodName);
        method.setAccessible(true);
        return method.invoke(obj, args);    
      }

      void writeTransforms(ObservableList<Transform> list,
          Element shapeElm) {
        if (list.size() == 0) return;
        Element transformsElm = document.createElement("transforms");
        shapeElm.appendChild(transformsElm);
        for (Transform t : list) {
          if (t instanceof Scale) {
            writeScale((Scale)t, transformsElm);
          } else if (t instanceof Translate) {
            writeTranslate((Translate)t, transformsElm);       
          } else if (t instanceof Rotate) {
            writeRotate((Rotate)t, transformsElm); 
          } else if (t instanceof Shear) {
            writeShear((Shear)t, transformsElm); 
          }
        }
      }

      void writeTranslate(Translate translate, Element transformsElm) {
        // tag is "Translate"
        String tag = translate.getClass().getSimpleName();
        Element tElm = document.createElement(tag);
        transformsElm.appendChild(tElm);
        // set attributes for tElm, example:
        //<Translate x="100.0" y="120.0"/>
        setDoubleAttribute(tElm, "x", translate.getX(), 0);
        setDoubleAttribute(tElm, "y", translate.getY(), 0);    
      }

      void writeScale(Scale scale, Element transformsElm) {
        // tag is "Scale"
        String tag = scale.getClass().getSimpleName();
        Element scaleElm = document.createElement(tag);
        transformsElm.appendChild(scaleElm);
        // set attributes for scaleElm, example:
        //<Scale x="0.5" y="0.5" pivotX="197.0" pivotY="85"/>
        setDoubleAttribute(scaleElm, "x", scale.getX(), 1);
        setDoubleAttribute(scaleElm, "y", scale.getY(), 1);
        setDoubleAttribute(scaleElm, "pivotX", scale.getPivotX(), 0);
        setDoubleAttribute(scaleElm, "pivotY", scale.getPivotY(), 0);
      }

      /**
       *
       */
      void writeRotate(Rotate rotate, Element transformsElm) {
        // tag is "Rotate"
        String tag = rotate.getClass().getSimpleName();
        Element rotateElm = document.createElement(tag);
        transformsElm.appendChild(rotateElm);
        // set attributes for rotateElm, example:
        //<Rotate angle="90.0" pivotX="281.0" pivotY="231.0"/>
        setDoubleAttribute(rotateElm, "angle", rotate.getAngle());
        setDoubleAttribute(rotateElm, "pivotX", rotate.getPivotX(), 0);
        setDoubleAttribute(rotateElm, "pivotY", rotate.getPivotY(), 0);
        setDoubleAttribute(rotateElm, "pivotZ", rotate.getPivotZ(), 0);
        if (rotate.getAxis() != null) {
          Element axisElm = document.createElement("axis");
          rotateElm.appendChild(axisElm);
          // set attributes for axisElm, example:
          //    <axis>
          //      <Point3D x="0.0" y="0.0" z="1.0"/>
          //    </axis>
          Element point3DElm = document.createElement("Point3D");
          axisElm.appendChild(point3DElm);
          setDoubleAttribute(point3DElm, "x", rotate.getAxis().getX());
          setDoubleAttribute(point3DElm, "y", rotate.getAxis().getY());
          setDoubleAttribute(point3DElm, "z", rotate.getAxis().getZ());
        }
      }

      /**
       *
       */
      void writeShear(Shear shear, Element transformsElm) {
        // tag is "Shear"
        String tag = shear.getClass().getSimpleName();
        Element shearElm = document.createElement(tag);
        transformsElm.appendChild(shearElm);
        // set attributes for shearElm, example:
        //<Shear x="0.3" y="0.3" pivotX="197.0" pivotY="85"/>
        setDoubleAttribute(shearElm, "x", shear.getX(), 0);
        setDoubleAttribute(shearElm, "y", shear.getY(), 0);
        setDoubleAttribute(shearElm, "pivotX", shear.getPivotX(), 0);
        setDoubleAttribute(shearElm, "pivotY", shear.getPivotY(), 0);
      }

      /**
       * In this release (V1.4), only implement these effects:
       *   DropShadow, InnerShadow, Reflection
       */
      void writeEffect(Effect effect, Element effectElm) {
        if (effect instanceof DropShadow) {
            writeDropShadow((DropShadow)effect, effectElm);
        } else if (effect instanceof InnerShadow) {
            writeInnerShadow((InnerShadow)effect, effectElm);       
        } else if (effect instanceof Reflection) {
            writeReflection((Reflection)effect, effectElm); 
        } 
      }

      /**
       *
       */
      void writeDropShadow(DropShadow dropShadow, Element effectElm) {
        // tag is "DropShadow"
        String tag = dropShadow.getClass().getSimpleName();
        Element dropShadowElm = document.createElement(tag);
        effectElm.appendChild(dropShadowElm);
        // set attributes for dropShadowElm, example:
        // <effect>
        //   <DropShadow offsetX="3" offsetY="3" color="#696969"/>
        // </effect>
        setDoubleAttribute(dropShadowElm, "offsetX", dropShadow.getOffsetX(), 0);
        setDoubleAttribute(dropShadowElm, "offsetY", dropShadow.getOffsetY(), 0);
        if (dropShadow.getColor() != null) {
          String hexStr = getColorHexString(dropShadow.getColor());
          // default color is BLACK
          setStringAttribute(dropShadowElm, "color", hexStr, "#000000");
        }
        // default width is 21.0, range: 0 to 255
        setDoubleAttribute(dropShadowElm, "width", dropShadow.getWidth());
        // default height is 21.0, range: 0 to 255
        setDoubleAttribute(dropShadowElm, "height", dropShadow.getHeight());
        // default radius is 10.0, range: 0 to 127
        // set radius has same result as set both width and height to
        //  2 * radius + 1
        setDoubleAttribute(dropShadowElm, "radius", dropShadow.getRadius());
        // default spread is 0.0, range: 0.0 to 1.0 
        setDoubleAttribute(dropShadowElm, "spread", dropShadow.getSpread(), 0);
        setStringAttribute(dropShadowElm, "blurType",
          dropShadow.getBlurType().name(), BlurType.THREE_PASS_BOX.name());
        if (dropShadow.getInput() != null) {
          // set another Effect as input of dropShadow, creates chain effects
          // e.g. if input effect is an InnerShadow:
          // <input>
          //   <InnerShadow offsetX="2.5" offsetY="0.5" color="#ffff00"/> 
          // </input>
          Element inputElm = document.createElement("input");
          dropShadowElm.appendChild(inputElm); 
          writeEffect(dropShadow.getInput(), inputElm); 
        }
      } 

      /**
       *
       */
      void writeInnerShadow(InnerShadow innerShadow, Element effectElm) {
        // tag is "InnerShadow"
        String tag = innerShadow.getClass().getSimpleName();
        Element innerShadowElm = document.createElement(tag);
        effectElm.appendChild(innerShadowElm);
        // set attributes for innerShadowElm, example:
        // <effect>
        //   <InnerShadow offsetX="2.5" offsetY="0.5" color="#ffff00"/>
        // </effect>
        setDoubleAttribute(innerShadowElm, "offsetX", innerShadow.getOffsetX(), 0);
        setDoubleAttribute(innerShadowElm, "offsetY", innerShadow.getOffsetY(), 0);
        if (innerShadow.getColor() != null) {
          String hexStr = getColorHexString(innerShadow.getColor());
          // default color is BLACK
          setStringAttribute(innerShadowElm, "color", hexStr, "#000000");
        }
        // default width is 21.0, range: 0 to 255
        setDoubleAttribute(innerShadowElm, "width", innerShadow.getWidth());
        // default height is 21.0, range: 0 to 255
        setDoubleAttribute(innerShadowElm, "height", innerShadow.getHeight());
        // default radius is 10.0, range: 0 to 127
        // set radius has same result as set both width and height to
        //  2 * radius + 1
        setDoubleAttribute(innerShadowElm, "radius", innerShadow.getRadius());
        // default choke is 0.0, range: 0.0 to 1.0 
        setDoubleAttribute(innerShadowElm, "choke", innerShadow.getChoke(), 0);
        setStringAttribute(innerShadowElm, "blurType",
          innerShadow.getBlurType().name(), BlurType.THREE_PASS_BOX.name());
        if (innerShadow.getInput() != null) {
          // set another Effect as input of innerShadow, creates chain effects
          // e.g. if input effect is a Reflection:
          // <input>
          //   <Reflection fraction="0.9"/> 
          // </input>
          Element inputElm = document.createElement("input");
          innerShadowElm.appendChild(inputElm); 
          writeEffect(innerShadow.getInput(), inputElm); 
        }
      }

      /**
       *
       */
      void writeReflection(Reflection reflection, Element effectElm) {
        // tag is "Reflection"
        String tag = reflection.getClass().getSimpleName();
        Element reflectionElm = document.createElement(tag);
        effectElm.appendChild(reflectionElm);
        // <effect>
        //   <Reflection fraction="0.9"/>
        // </effect>
        // default fraction 0.75, range 0.0 to 1.0
        setDoubleAttribute(reflectionElm, "fraction", reflection.getFraction());
        // topOffset specify distance between bottom of input and top of reflection
        // default topOffset 0.0
        setDoubleAttribute(reflectionElm, "topOffset", reflection.getTopOffset(), 0);
        // default topOpacity 0.5, range 0.0 to 1.0
        setDoubleAttribute(reflectionElm, "topOpacity", reflection.getTopOpacity());
        // default bottomOpacity 0.0, range 0.0 to 1.0
        setDoubleAttribute(reflectionElm, "bottomOpacity", reflection.getBottomOpacity(), 0);
        if (reflection.getInput() != null) {
          // set another Effect as input of reflection, creates chain effects
          // e.g. if input effect is a DropShadow:
          // <input>
          //   <DropShadow offsetX="3" offsetY="3" blurType="TWO_PASS_BOX" color="#696969"/> 
          // </input>
          Element inputElm = document.createElement("input");
          reflectionElm.appendChild(inputElm); 
          writeEffect(reflection.getInput(), inputElm); 
        }
      } 

      /**
       * This method set common attributes defined within Node class
       * @param figure
       * @param shapeElm 
       */
      void setNodeAttributes(javafx.scene.Node figure, Element shapeElm) {
        setDoubleAttribute(shapeElm, "layoutX", figure.getLayoutX(), 0);
        setDoubleAttribute(shapeElm, "layoutY", figure.getLayoutY(), 0);
        setDoubleAttribute(shapeElm, "opacity", figure.getOpacity(), 1);
        setDoubleAttribute(shapeElm, "rotate", figure.getRotate(), 0);
        setDoubleAttribute(shapeElm, "translateX", figure.getTranslateX(), 0);
        setDoubleAttribute(shapeElm, "translateY", figure.getTranslateY(), 0);
        setDoubleAttribute(shapeElm, "scaleX", figure.getScaleX(), 1);
        setDoubleAttribute(shapeElm, "scaleY", figure.getScaleY(), 1);
        setBooleanAttribute(shapeElm, "pickOnBounds", figure.isPickOnBounds(), false); 
        setStringAttribute(shapeElm, "fx:id", getSketchShapeId(figure), "");
        // write clip element
        if (figure.getClip() != null) {
          Element clipElm = document.createElement("clip");
          shapeElm.appendChild(clipElm);
          writeFigure(figure.getClip(), clipElm);
        }
        // append transforms element to shapeElm
        writeTransforms(figure.getTransforms(), shapeElm);
        // append effect element to shapeElm
        if (figure.getEffect() != null) {
          Element effectElm = document.createElement("effect");
          shapeElm.appendChild(effectElm);
          writeEffect(figure.getEffect(), effectElm);
        }    
      }

      void setDoubleAttribute(Element shapeElm, String prop, Double val) {
        shapeElm.setAttribute(prop, Double.toString(val));
      }

      /**
       * if given value is default value, do nothing
       * @param shapeElm
       * @param prop
       * @param val
       * @param defaultVal 
       */
      void setDoubleAttribute(Element shapeElm, String prop,
          Double val, int defaultVal) {
        if (val != defaultVal)
          shapeElm.setAttribute(prop, Double.toString(val));
      }

      /**
       * if given boolean value is same as default value, do nothing
       * @param shapeElm
       * @param prop
       * @param val
       * @param defaultVal 
       */
      void setBooleanAttribute(Element shapeElm, String prop,
          boolean val, boolean defaultVal) {
        if (val != defaultVal)
          shapeElm.setAttribute(prop, Boolean.toString(val));
      }

      void setBooleanAttribute(Element shapeElm, String prop, boolean val) {    
        shapeElm.setAttribute(prop, Boolean.toString(val));
      }

      void setStringAttribute(Element shapeElm, String prop, String val,
          String defaultVal) {
        if (!val.equals(defaultVal))
          shapeElm.setAttribute(prop, val);
      }

      void setIntegerAttribute(Element shapeElm, String prop,
          int val, int defaultVal) {
        if (val != defaultVal)
          shapeElm.setAttribute(prop, Integer.toString(val));
      }

      void setColorAttribute(Element shapeElm, Color color) {
        shapeElm.setAttribute("color", getColorHexString(color));
      }

      void setShapeAttributes(Shape figure, Element shapeElm) {
          // Common shape attributes
          Paint paint = figure.getFill();
          if (paint != null)
            setPaintAttribute(shapeElm, paint, "fill");
          paint = figure.getStroke();
          if (paint != null)
            setPaintAttribute(shapeElm, paint, "stroke");

          if (figure.getStrokeWidth() != 1)
            setDoubleAttribute(shapeElm, "strokeWidth", figure.getStrokeWidth());

          if (figure.getStrokeType() != StrokeType.CENTERED)
            shapeElm.setAttribute("strokeType", figure.getStrokeType().name());

          setStringAttribute(shapeElm, "strokeLineCap",
            figure.getStrokeLineCap().name(), StrokeLineCap.SQUARE.name());
          setStringAttribute(shapeElm, "strokeLineJoin",
            figure.getStrokeLineJoin().name(), StrokeLineJoin.MITER.name());
          setDoubleAttribute(shapeElm, "strokeMiterLimit",
              figure.getStrokeMiterLimit(), 10);

          // save strokeDashArray property
          setStrokDashArrayAttribute(figure, shapeElm);

          if (figure instanceof Line)
            setLineAttributes((Line)figure, shapeElm);
          else if (figure instanceof Polyline)
            setPolylineAttributes((Polyline)figure, shapeElm); 
          else if (figure instanceof Polygon)
            setPolygonAttributes((Polygon)figure, shapeElm);
          else if (figure instanceof Path)
            setPathAttributes((Path)figure, shapeElm);
          else if (figure instanceof Rectangle)
            setRectangleAttributes((Rectangle)figure, shapeElm);
          else if (figure instanceof Circle)
            setCircleAttributes((Circle)figure, shapeElm);
          else if (figure instanceof Ellipse)
            setEllipseAttributes((Ellipse)figure, shapeElm);
          else if (figure instanceof javafx.scene.text.Text) {
            setTextAttributes((javafx.scene.text.Text)figure, shapeElm);
            writeFont(((javafx.scene.text.Text)figure).getFont(), shapeElm);
          } else if (figure instanceof Arc)
            setArcAttributes((Arc)figure, shapeElm);
          else if (figure instanceof QuadCurve)
            setQuadCurveAttributes((QuadCurve)figure, shapeElm);
          else if (figure instanceof CubicCurve)
            setCubicCurveAttributes((CubicCurve)figure, shapeElm);
          else if (figure instanceof SVGPath)
            setSVGPathAttributes((SVGPath)figure, shapeElm);
      }

      /**
       *  Write color in hex string
       *    e.g. "#FF0000" for Red color
       */ 
      String getColorHexString(Color color) {
        int a = (int)(color.getOpacity() * 255); 
        int r = (int)(color.getRed() * 255);
        int g = (int)(color.getGreen() * 255);
        int b = (int)(color.getBlue() * 255);
        return a != 255 ?
          String.format("#%02X%02X%02X%02X", r, g, b, a) :
          String.format("#%02X%02X%02X", r, g, b);
      }

      /**
       * in this release (V1.4), parameter attr is:
       *   either "fill" or "stroke"
       */
      void setPaintAttribute(Element shapeElm, Paint paint, String attr) {
        if (paint instanceof Color) {
          shapeElm.setAttribute(attr, getColorHexString((Color)paint));
        } else {
          Element attrElm = document.createElement(attr);
          shapeElm.appendChild(attrElm);
          if (paint instanceof LinearGradient) {
            setLinearGradient((LinearGradient)paint, attrElm);
          } else if (paint instanceof RadialGradient) {
            setRadialGradient((RadialGradient)paint, attrElm);
          } else if (paint instanceof ImagePattern) {
            setImagePatternPaint((ImagePattern)paint, attrElm);
          }
        }  
      }

      /**
       * in this release (V1.4), parameter attrElm is:
       *   either <fill> or <stroke>
       */
      void setLinearGradient(LinearGradient gradient, Element attrElm) {
        //  <fill>
        //    <LinearGradient startX="0.0" startY="0.0" endX="0.0" endY="1.0"
        //      proportional="true" cycleMethod="NO_CYCLE">
        //      <stops>
        //        <Stop offset="0" color="#FFFFFF"/>
        //        <Stop offset="0.55" color="#ffffcc"/>
        //        <Stop offset="1" color="#FFA500"/>
        //      </stops>
        //    </LinearGradient>
        //  </fill>
        Element gradientElm = document.createElement("LinearGradient");
        attrElm.appendChild(gradientElm);
        // write LinearGradient attributes: such as startX, startY, ...
        // default startX is 0.0
        setDoubleAttribute(gradientElm, "startX", gradient.getStartX());
        // default startY is 0.0
        setDoubleAttribute(gradientElm, "startY", gradient.getStartY());
        // default endX is 1.0
        setDoubleAttribute(gradientElm, "endX", gradient.getEndX());
        // default endY is 1.0
        setDoubleAttribute(gradientElm, "endY", gradient.getEndY());
        // default proportional is true
        setBooleanAttribute(gradientElm, "proportional",
          gradient.isProportional(), true);
        // default cycleMethod is NO_CYCLE
        setStringAttribute(gradientElm, "cycleMethod",
          gradient.getCycleMethod().name(), CycleMethod.NO_CYCLE.name());
        // default stops is empty list
        setGradientStop(gradientElm, gradient.getStops());
      }

      /**
       *
       */
      void setGradientStop(Element gradientElm, List<Stop> list) {
        if (list == null || list.size() == 0) return;
        //      <stops>
        //        <Stop offset="0" color="#FFFFFF"/>
        //        <Stop offset="0.55" color="#ffffcc"/>
        //        <Stop offset="1" color="#FFA500"/>
        //      </stops>
        Element stopsElm = document.createElement("stops");
        gradientElm.appendChild(stopsElm);
        for (Stop stop : list) {
          Element stopElm = document.createElement("Stop");
          stopsElm.appendChild(stopElm);
          setDoubleAttribute(stopElm, "offset", stop.getOffset());
          setColorAttribute(stopElm, stop.getColor());
        }
      } 

      /**
       * in this release (V1.4), parameter attrElm is:
       *   either <fill> or <stroke>
       */
      void setRadialGradient(RadialGradient gradient, Element attrElm) {
        //  <fill>
        //    <RadialGradient centerX="0.5" centerY="0.5" radius="1"
        //      focusDistance="0.4" focusAngle="60.0"
        //      proportional="true" cycleMethod="NO_CYCLE">
        //      <stops>
        //        <Stop offset="0" color="#ffff00"/>
        //        <Stop offset="0.45" color="#008000"/>
        //        <Stop offset="1" color="#0000ff"/>
        //      </stops>
        //    </RadialGradient>
        //  </fill>
        Element gradientElm = document.createElement("RadialGradient");
        attrElm.appendChild(gradientElm);
        // write RadialGradient attributes: such as centerX, centerY, ...
        // default centerX is 0.0
        setDoubleAttribute(gradientElm, "centerX", gradient.getCenterX());
        // default centerY is 0.0
        setDoubleAttribute(gradientElm, "centerY", gradient.getCenterY());
        // default radius is 1.0
        setDoubleAttribute(gradientElm, "radius", gradient.getRadius());
        // focusDistance 0 locates in the center of gradient circle
        // 1 locates on the circumference of gradient circle
        setDoubleAttribute(gradientElm, "radius", gradient.getRadius());
        // focusAngle measured in degrees from the center point to a point
        // where the first given color is painted
        setDoubleAttribute(gradientElm, "focusAngle", gradient.getFocusAngle());
        // default proportional is true
        setBooleanAttribute(gradientElm, "proportional",
          gradient.isProportional(), true);
        // default cycleMethod is NO_CYCLE
        setStringAttribute(gradientElm, "cycleMethod",
          gradient.getCycleMethod().name(), CycleMethod.NO_CYCLE.name());
        // default stops is empty list
        setGradientStop(gradientElm, gradient.getStops());
      }

      /**
       * in this release (V1.4), parameter attrElm is:
       *   either <fill> or <stroke>
       */
      void setImagePatternPaint(ImagePattern pattern, Element attrElm) {
        Element patternElm = document.createElement("ImagePattern");
        attrElm.appendChild(patternElm);
        // write ImagePattern attributes: such as x, y, ...
        // will be implemented in future release
      }

      void setStrokDashArrayAttribute(Shape figure, Element shapeElm) {
        //<Rectangle fill="#00000000" height="56.0" stroke="#656565" width="82.0" x="113.0" y="84.0">
        //  <strokeDashArray>
        //    <Double fx:value="3.0"/>
        //    <Double fx:value="4.0"/>
        //    <Double fx:value="3.0"/>
        //    <Double fx:value="4.0"/>
        //  </strokeDashArray>
        //</Rectangle>
        ObservableList<Double> list = figure.getStrokeDashArray();
        if (list == null || list.size() == 0) return;
        Element dashArrayElm = document.createElement("strokeDashArray");
        shapeElm.appendChild(dashArrayElm);
        for (double val : list) {
          Element doubleElm = document.createElement("Double");
          dashArrayElm.appendChild(doubleElm);
          setDoubleAttribute(doubleElm, "fx:value", val);
        }
      }

      void setPolylineAttributes(Polyline figure, Element shapeElm) {
        // <Polygline fill="DODGERBLUE" layoutX="146.0" layoutY="117.0" stroke="BLACK"
        //  strokeType="INSIDE">
        //      <points>
        //        <Double fx:value="-50.0" />
        //        <Double fx:value="40.0" />
        //        <Double fx:value="50.0" />
        //        <Double fx:value="40.0" />
        //        <Double fx:value="0.0" />
        //        <Double fx:value="-60.0" />
        //      </points>
        //    </Polyline>
        ObservableList<Double> list = figure.getPoints();
        Element pointsElm = document.createElement("points");
        shapeElm.appendChild(pointsElm);
        for (double val : list) {
          Element doubleElm = document.createElement("Double");
          pointsElm.appendChild(doubleElm);
          setDoubleAttribute(doubleElm, "fx:value", val);
        }
      }

      private void setPolygonAttributes(Polygon figure, Element shapeElm) {
        // <Polygon fill="DODGERBLUE" layoutX="146.0" layoutY="117.0" stroke="BLACK"
        //  strokeType="INSIDE">
        //      <points>
        //        <Double fx:value="-50.0" />
        //        <Double fx:value="40.0" />
        //        <Double fx:value="50.0" />
        //        <Double fx:value="40.0" />
        //        <Double fx:value="0.0" />
        //        <Double fx:value="-60.0" />
        //      </points>
        //    </Polygon>
        ObservableList<Double> list = figure.getPoints();
        Element pointsElm = document.createElement("points");
        shapeElm.appendChild(pointsElm);
        for (double val : list) {
          Element doubleElm = document.createElement("Double");
          pointsElm.appendChild(doubleElm);
          setDoubleAttribute(doubleElm, "fx:value", val);
        }
      }

      void setPathAttributes(Path figure, Element shapeElm) {
        // <Path stroke="#1E90FF">
        //   <elements>
        //     <MoveTo x="0.0" y="0.0"/>
        //     <LineTo x="70.0" y="0.0"/>
        //     <QuadCurveTo x="120.0" y="60.0" controlX="100.0" controlY="0.0"/>
        //   </elements>
        // </Path>
        ObservableList<PathElement> list = figure.getElements();
        Element pathElm = document.createElement("elements");
        shapeElm.appendChild(pathElm);
        for (PathElement val : list) {
          Element pathElementElm = document.createElement(val.getClass().getSimpleName());
          pathElm.appendChild(pathElementElm);
          setPathElementAttributes(val, pathElementElm);
        }
      }

      void setPathElementAttributes(PathElement figure, Element pathElementElm) {
         //<MoveTo x="0.0" y="0.0"/>
         //<LineTo x="70.0" y="0.0"/>
         //<QuadCurveTo x="120.0" y="60.0" controlX="100.0" controlY="0.0"/>
         //<HLineTo x="206.0"/>
         //<VLineTo y="206.0"/>
         //<CubicCurveTo x="120.0" y="60.0" controlX1="100.0" controlY1="0.0"
         // controlX2="100.0" controlY2="0.0"/>
         //<ArcTo x="120.0" y="60.0" radiusX="100.0" radiusY="100.0"
         // largeArcFlag="false" sweepFlag="false" xAxisRotation="0.0"/>
         if (figure instanceof MoveTo)
           setMoveToAttributes((MoveTo)figure, pathElementElm);
         else if (figure instanceof LineTo)
           setLineToAttributes((LineTo)figure, pathElementElm);
         else if (figure instanceof QuadCurveTo)
           setQuadCurveToAttributes((QuadCurveTo)figure, pathElementElm);
         else if (figure instanceof CubicCurveTo)
           setCubicCurveToAttributes((CubicCurveTo)figure, pathElementElm);
         else if (figure instanceof HLineTo)
           setHLineToAttributes((HLineTo)figure, pathElementElm);
         else if (figure instanceof VLineTo)
           setVLineToAttributes((VLineTo)figure, pathElementElm);
         else if (figure instanceof ArcTo)
           setArcToAttributes((ArcTo)figure, pathElementElm);
      }

      void setMoveToAttributes(MoveTo figure, Element shapeElm) {
        //<MoveTo x="0.0" y="0.0"/>
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
      }

      void setLineToAttributes(LineTo figure, Element shapeElm) {
        //<LineTo x="70.0" y="0.0"/>
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
      }

      void setQuadCurveToAttributes(QuadCurveTo figure, Element shapeElm) {
        //<QuadCurveTo x="120.0" y="60.0" controlX="100.0" controlY="0.0"/>
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
        setDoubleAttribute(shapeElm, "controlX", figure.getControlX(), 0);
        setDoubleAttribute(shapeElm, "controlY", figure.getControlY(), 0);
      }

      void setCubicCurveToAttributes(CubicCurveTo figure, Element shapeElm) {
        //<CubicCurveTo controlX1="118.0" controlY1="108.0" 
        // controlX2="180.0" controlY2="268.0" x="212.0" y="188.0"/>
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
        setDoubleAttribute(shapeElm, "controlX1", figure.getControlX1(), 0);
        setDoubleAttribute(shapeElm, "controlY1", figure.getControlY1(), 0);
        setDoubleAttribute(shapeElm, "controlX2", figure.getControlX2(), 0);
        setDoubleAttribute(shapeElm, "controlY2", figure.getControlY2(), 0);
      }

      void setHLineToAttributes(HLineTo figure, Element shapeElm) {
        //<HLineTo x="206.0"/>
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
      }

      void setVLineToAttributes(VLineTo figure, Element shapeElm) {
        //<VLineTo y="206.0"/>
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
      }

      void setArcToAttributes(ArcTo figure, Element shapeElm) {
        //<ArcTo x="120.0" y="60.0" radiusX="100.0" radiusY="100.0"
        // largeArcFlag="false" sweepFlag="false" xAxisRotation="0.0"/>
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
        setDoubleAttribute(shapeElm, "radiusX", figure.getRadiusX(), 0);
        setDoubleAttribute(shapeElm, "radiusY", figure.getRadiusY(), 0);
        setDoubleAttribute(shapeElm, "xAxisRotation", figure.getXAxisRotation(), 0);
        setBooleanAttribute(shapeElm, "largeArcFlag",
            figure.isLargeArcFlag(), false);
        setBooleanAttribute(shapeElm, "sweepFlag",
            figure.isSweepFlag(), false);
      }

      void setRectangleAttributes(Rectangle figure, Element shapeElm) {
        // <Rectangle arcHeight="5.0" arcWidth="5.0" fill="DODGERBLUE"
        // height="200.0" layoutX="232.0" layoutY="187.0" stroke="BLACK"
        // strokeType="INSIDE" width="200.0" />
        setDoubleAttribute(shapeElm, "arcWidth", figure.getArcWidth(), 0);
        setDoubleAttribute(shapeElm, "arcHeight", figure.getArcHeight(), 0);
        setDoubleAttribute(shapeElm, "width", figure.getWidth(), 0);
        setDoubleAttribute(shapeElm, "height", figure.getHeight(), 0);
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
      }

      void setCircleAttributes(Circle figure, Element shapeElm) {
        // <Circle fill="DODGERBLUE" layoutX="232.0"
        //   layoutY="187.0" radius="100.0" stroke="BLACK" strokeType="INSIDE" />
        setDoubleAttribute(shapeElm, "radius", figure.getRadius(), 0);
        setDoubleAttribute(shapeElm, "centerX", figure.getCenterX(), 0);
        setDoubleAttribute(shapeElm, "centerY", figure.getCenterY(), 0);
      }

      void setEllipseAttributes(Ellipse figure, Element shapeElm) {
        //<Ellipse
        //  fill="DODGERBLUE" layoutX="313.0" layoutY="107.0"
        //  radiusX="100.0" radiusY="80.0" stroke="BLACK" strokeType="INSIDE" />
        setDoubleAttribute(shapeElm, "radiusX", figure.getRadiusX(), 0);
        setDoubleAttribute(shapeElm, "radiusY", figure.getRadiusY(), 0);
        setDoubleAttribute(shapeElm, "centerX", figure.getCenterX(), 0);
        setDoubleAttribute(shapeElm, "centerY", figure.getCenterY(), 0);
      }

      void setLineAttributes(Line figure, Element shapeElm) {
        //<Line endX="100.0" layoutX="268.0" layoutY="119.0" startX="-162.0"
        //startY="124.0" stroke="#99ffda" strokeWidth="8.0" />

        setDoubleAttribute(shapeElm, "startX", figure.getStartX());
        setDoubleAttribute(shapeElm, "startY", figure.getStartY());
        setDoubleAttribute(shapeElm, "endX", figure.getEndX());
        setDoubleAttribute(shapeElm, "endY", figure.getEndY());
      }

      void setArcAttributes(Arc figure, Element shapeElm) {
        //<Arc fill="#fff500" centerX="301.0" centerY="231.0" length="270.0"
        //radiusX="100.0" radiusY="100.0" startAngle="45.0" stroke="BLACK"
        //strokeType="INSIDE" type="ROUND" />
        setDoubleAttribute(shapeElm, "centerX", figure.getCenterX()); 
        setDoubleAttribute(shapeElm, "centerY", figure.getCenterY()); 
        setDoubleAttribute(shapeElm, "length", figure.getLength());
        setDoubleAttribute(shapeElm, "radiusX", figure.getRadiusX()); 
        setDoubleAttribute(shapeElm, "radiusY", figure.getRadiusY()); 
        setDoubleAttribute(shapeElm, "startAngle", figure.getStartAngle()); 
        shapeElm.setAttribute("type", figure.getType().name());      
      }

      /**
       *
       */
      void setQuadCurveAttributes(QuadCurve figure, Element shapeElm) {
        //<QuadCurve controlX="36.0" controlY="201.0"
        // startX="195.0" startY="87.0" endX="205.0" endY="170"
        // stroke="#A0522D" strokeWidth="8.0" />
        setDoubleAttribute(shapeElm, "controlX", figure.getControlX());
        setDoubleAttribute(shapeElm, "controlY", figure.getControlY());
        setDoubleAttribute(shapeElm, "startX", figure.getStartX());
        setDoubleAttribute(shapeElm, "startY", figure.getStartY());
        setDoubleAttribute(shapeElm, "endX", figure.getEndX());
        setDoubleAttribute(shapeElm, "endY", figure.getEndY());
      }

      /**
       *
       */
      void setCubicCurveAttributes(CubicCurve figure, Element shapeElm) {
        //<CubicCurve controlX1="100" controlY1="100" controlX2="250" controlY2="100"
        // startX="100" startY="200" endX="250" endY="200"
        // stroke="#888888" strokeWidth="2.0" fill="#00000000"/>
        setDoubleAttribute(shapeElm, "controlX1", figure.getControlX1());
        setDoubleAttribute(shapeElm, "controlY1", figure.getControlY1());
        setDoubleAttribute(shapeElm, "controlX2", figure.getControlX2());
        setDoubleAttribute(shapeElm, "controlY2", figure.getControlY2());
        setDoubleAttribute(shapeElm, "startX", figure.getStartX());
        setDoubleAttribute(shapeElm, "startY", figure.getStartY());
        setDoubleAttribute(shapeElm, "endX", figure.getEndX());
        setDoubleAttribute(shapeElm, "endY", figure.getEndY());
      }

      /**
       *
       */
      void setSVGPathAttributes(SVGPath figure, Element shapeElm) {
        //<SVGPath content="M 100 100 L 300 100 L 200 300 z"
        // fillRule="EVEN_ODD"/>
        // default content is empty string
        setStringAttribute(shapeElm, "content", figure.getContent(), "");
        // default fillRule is FillRule.NON_ZERO
        setStringAttribute(shapeElm, "fillRule",
          figure.getFillRule().name(), FillRule.NON_ZERO.name());
      }

      /**
       *
       */
      void setTextAttributes(javafx.scene.text.Text figure, Element shapeElm) {
        //<Text scaleY="4.293027360988526" strokeType="OUTSIDE" strokeWidth="0.0"
        // text="Text"/>
        shapeElm.setAttribute("text", figure.getText());
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);   
        //<Text boundsType="VISUAL" layoutX="43.0" layoutY="132.0"
        // strokeLineCap="ROUND" strokeLineJoin="BEVEL" strokeType="OUTSIDE"
        // strokeWidth="0.0"
        // text="A B C D E F G"
        // textAlignment="CENTER" textOrigin="TOP" underline="true"
        // wrappingWidth="80.0">
        setDoubleAttribute(shapeElm, "wrappingWidth", figure.getWrappingWidth(), 0);
        setStringAttribute(shapeElm, "boundsType",
          figure.getBoundsType().name(), TextBoundsType.LOGICAL.name());
        setStringAttribute(shapeElm, "textAlignment",
          figure.getTextAlignment().name(), TextAlignment.LEFT.name());
        setStringAttribute(shapeElm, "textOrigin",
          figure.getTextOrigin().name(), VPos.BASELINE.name());
        setBooleanAttribute(shapeElm, "underline",
          figure.isUnderline(), false);
        setBooleanAttribute(shapeElm, "strikethrough",
          figure.isStrikethrough(), false);
        setStringAttribute(shapeElm, "fontSmoothingType",
          figure.getFontSmoothingType().name(), FontSmoothingType.GRAY.name());
      }

      void writeFont(Font font, Element shapeElm) {
        //<font>
        //  <Font name="Courier New" size="15.0" />
        //</font>
        Element fontElm = document.createElement("font");
        shapeElm.appendChild(fontElm);
        // tag is "Font"
        String tag = font.getClass().getSimpleName();
        Element tagElm = document.createElement(tag);
        fontElm.appendChild(tagElm);
        // set attributes for tagElm, example:
        //<Font name="Courier New" size="15.0" />
        setDoubleAttribute(tagElm, "size", font.getSize(), 12);
        setStringAttribute(tagElm, "name", font.getName(), "");
        //setStringAttribute(tagElm, "style", font.getStyle(), "Regular");
      }

      void setImageAttributes(ImageView figure, Element shapeElm) {
        //<ImageView id="mao-mao" fx:id="maomao" fitHeight="265.0"
        //  fitWidth="353.3333333333333" layoutX="31.0" layoutY="36.0"
        //  pickOnBounds="true" preserveRatio="true" styleClass="image-view">
        //  <image>
        //    <Image url="@ColorBaloon_1.png" preserveRatio="false" smooth="false" />
        //  </image>
        //</ImageView>
        setDoubleAttribute(shapeElm, "fitWidth", figure.getFitWidth(), 0);
        setDoubleAttribute(shapeElm, "fitHeight", figure.getFitHeight(), 0);
        setDoubleAttribute(shapeElm, "x", figure.getX(), 0);
        setDoubleAttribute(shapeElm, "y", figure.getY(), 0);
        setBooleanAttribute(shapeElm, "preserveRatio",
            figure.isPreserveRatio(), false);

        // write image element
        Element imageElm = document.createElement("image");
        shapeElm.appendChild(imageElm);
        Element theImgElm = document.createElement("Image");
        imageElm.appendChild(theImgElm);

        Image img = figure.getImage();
        setBooleanAttribute(theImgElm, "preserveRatio", img.isPreserveRatio());
        setBooleanAttribute(theImgElm, "smooth", img.isSmooth());

        String url = null;
        Object urlObj = figure.getProperties().get("imageURL");
        // urlObj might be a java.net.URL object if this imageView loaded from
        // a file with the following property in properties (a map)
        //  <properties imageURL="@junktest3_1.png"/>
        // do not use String type casting for a URL object (runtime error)
        if (urlObj != null)
          url = urlObj.toString(); 

        // Note: if image has been transformed,
        // getImage() return the original image
        // However, if you load FXML, image is rendered in screen correctly
        // because transform property is saved in FXML.
        // But, if you try to load image file, which is saved by writeFXML
        // you'll see the original image (not transformed)
        // To write an image that synchronizes with transform property of
        // ImageView, you can use writeImageView method to save image

        // If this image is opened from FileChooser
        // url is something like this:
        //  "file:/C:/Documents%20and%20Settings/Bing-Chao%20Huang/My%20Documents/
        //   My%20Pictures/Photo/Bing/Cat2/Shufen2009_11%20305.jpg"
        // If an image is not opened from a FileChooser, e.g.,
        // the image is created dynamically using DrawClipper.clipImage,
        // then, url is null
        if (url == null) {
          // Save this image to file with extension .png
          // if fxml file name is Objects.fxml, then image is saved in
          // Objects_1.png, or Objects_2.png
          File imgFile = writeImage(img); 
          //String url = imgFile.toURI().toString();
          url = "@" + imgFile.getName();
          // put url to properties (a map), later will be written to file
          figure.getProperties().put("imageURL", imgFile.toURI().toString());      
        }
        theImgElm.setAttribute("url", url);
      }

      /**
       * Write animation object inside <fx:define> element
       * At this stage, only implement PathTransition
       */
      void writeAnimation(Animation figure, Element defineElm) {
        String shapeTag = getSketchShapeTag(figure); // get class simple name
        Element shapeElm = document.createElement(shapeTag);
        defineElm.appendChild(shapeElm);
        if (figure instanceof PathTransition) {    
          setPathTransitionAttributes((PathTransition)figure, shapeElm);
        }
        // write common animation attributions
        setAnimationAttributes(figure, shapeElm);
      }

      /**
       * Write common attributes for Animation Objects, such as
       *   autoReverse, cycleCount
       * which are attributes inherited from Animation class
       */
      void setAnimationAttributes(Animation figure, Element shapeElm) {
        //<PathTransition fx:id="myPathTransition1" path="$myPath1" node="$myPencil"
        //      orientation="NONE" autoReverse="true">
        //  <cycleCount><Timeline fx:constant="INDEFINITE"/></cycleCount>
        //  <duration><Duration fx:id="myDuration" fx:value="8000ms"/></duration>
        //</PathTransition>

        // must remove dot and @
        shapeElm.setAttribute("fx:id", validateFXId(figure.toString())); 
        setBooleanAttribute(shapeElm, "autoReverse", figure.isAutoReverse(), false);
        setAnimationCycleCountAttribute(figure, shapeElm);
      }

      /**
       * Write <cycleCount> element inside an Animation (such as <PathTransition>)
       * create an instance of Timeline, if cycleCount is Timeline.INDEFINITE
       */
      void setAnimationCycleCountAttribute(Animation figure, Element shapeElm) {
        if (figure.getCycleCount() == Animation.INDEFINITE) {
          //<PathTransition fx:id="myPathTransition1" path="$myPath1" node="$myPencil"
          //      orientation="NONE" autoReverse="true">
          //  <cycleCount><Timeline fx:constant="INDEFINITE"/></cycleCount>
          //  <duration><Duration fx:id="myDuration" fx:value="8000ms"/></duration>
          //</PathTransition>
          Element cycleCountElm = document.createElement("cycleCount");
          shapeElm.appendChild(cycleCountElm);
          Element timelineElm = document.createElement("Timeline");
          cycleCountElm.appendChild(timelineElm);
          timelineElm.setAttribute("fx:constant", "INDEFINITE");
        } else {
          //<PathTransition fx:id="myPathTransition1" path="$myPath1" node="$myPencil"
          //      orientation="NONE" cycleCount="2" autoReverse="true">
          //</PathTransition>
          setIntegerAttribute(shapeElm, "cycleCount", figure.getCycleCount(), 1);
        }
      }

      /**
       *  Write PathTransition attributes:
       *    path, node, orientation, duration
       */
      void setPathTransitionAttributes(PathTransition figure, Element shapeElm) {
        //<PathTransition fx:id="myPathTransition1" path="$myPath1" node="$myPencil"
        //      orientation="NONE" autoReverse="true">
        //  <cycleCount><Timeline fx:constant="INDEFINITE"/></cycleCount>
        //  <duration><Duration fx:id="myDuration" fx:value="8000ms"/></duration>
        //</PathTransition>

        Shape path = figure.getPath();
        if (path != null) {
          String id = "$" + getSketchShapeId(path);
          shapeElm.setAttribute("path", id);
        }

        javafx.scene.Node node = figure.getNode();
        if (node != null) {
          String id = "$" + getSketchShapeId(node);
          shapeElm.setAttribute("node", id);
        }

        setStringAttribute(shapeElm, "orientation",
          figure.getOrientation().name(), PathTransition.OrientationType.NONE.name());

        // write Duration
        setPathTransitionDuration(figure, shapeElm);
      }

      /**
       *  Write <duration> inside <PathTransition>
       */
      void setPathTransitionDuration(PathTransition figure, Element shapeElm) {
        Duration durObj = figure.getDuration();
        if (durObj != Duration.INDEFINITE) {
          //  <duration><Duration fx:id="myDuration" fx:value="8000ms"/></duration>
          Element durationElm = document.createElement("duration");
          shapeElm.appendChild(durationElm);
          Element tagDurationElm = document.createElement("Duration");
          durationElm.appendChild(tagDurationElm);
          double ms = durObj.toMillis();
          String msStr = String.format("%.0fms", ms);
          tagDurationElm.setAttribute("fx:value", msStr);
        }
        // don't know how to write static field: Duration.INDEFINITE (type of Duration)         
      }

      /**
       * Write properties (a map) of node, this node maybe a Pane
       * At this stage, only two keys are defined by application JFXDrawTools:
       *   "imageURL" (for imageView only), value is type of String
       *   "animation" (for root pane), value is type of Animation
       */
      void writeProperties(javafx.scene.Node root, Element rootElm) {
        Map<Object, Object> map = root.getProperties();
        if (map.size() == 0) return;
        // write properties element, it's a Map
        // <properties imageURL="@ColorBaloon_1.png"/> for a imageView
        // <properties animation1="$myPathTransition1" animation2="$myPathTransition2">
        // We want to write <fx:define> element before <properties>
        Element defineElm = document.createElement("fx:define");
        Iterator<Map.Entry<Object, Object>> it = map.entrySet().iterator();
        boolean hasDefine = false;
        while (it.hasNext()) {
          Map.Entry<Object, Object> e = it.next();
          Object v = e.getValue();
          //System.out.format("key=%s v=%s%n", e.getKey(), e.getValue());
          if (v instanceof Animation) {
            writeAnimation((Animation)v, defineElm);
            hasDefine = true;
          }
        }
        if (hasDefine)
          rootElm.appendChild(defineElm);

        Element propertiesElm = document.createElement("properties");
        rootElm.appendChild(propertiesElm);
        it = map.entrySet().iterator();
        while (it.hasNext()) {
          Map.Entry<Object, Object> e = it.next();
          if (e.getValue() instanceof String)
            propertiesElm.setAttribute(e.getKey().toString(), e.getValue().toString());
          else {
            // is an Animation object
            // get object id from toString
            String id = "$" + validateFXId(e.getValue().toString());
            propertiesElm.setAttribute(e.getKey().toString(), id);
          }
        }
      }

      /**
       *  get node's id to be written as fx:id tag
       *  if a node doesn't have an id yet,
       *  we'll use class name concat hash code (in hex) as id
       */  
      String getSketchShapeId(javafx.scene.Node figure) {
       String id = figure.getId();
       if (id == null) {
         // class name + hashCode (in hex) as id
         id = String.format("%s_%x",
           figure.getClass().getSimpleName(), figure.hashCode());
       }
       return id;
      }

      /**
       * An animation object is not a Node object,
       * it doesn't have id property
       * therefore, we use toString() and validate it as fx:id 
       * figure.toString() maybe look like these:
       *   Path[id=myPath]
       *     a path object with fx:id loaded from FXML file
       *   Path@12f3276
       *     b4 JavaFX 8, a path object created by a draw tool,
       *     without assigning an id
       *   javafx.animation.PathTransition@1bc1cac
       *     a PathTransition loaded from FXML file,
       *     or created by a draw tool
       *  these strings contain illegal characters such as
       *    dot @ = [ ]
       */
      String validateFXId(String id) {
        // remove white space and comma    
        // replace dot @ = [ ] with character '_'
        return id.replaceAll("[ \\,]", "").replaceAll(
          "[\\.\\=\\[\\]\\@]", "_");
      }

      /**
       *
       */
      String getSketchShapeTag(java.lang.Object figure) {
        String type = figure.getClass().getSimpleName();
        // write Regular Polygon class as Polygon
        if (type.compareTo("RegularPolygon") == 0)
          return "Polygon";
        return type;
      }

      /**
       * This method called from writeImageView to save
       * image of ImageView to an image file
       * Apply ImageIO.write method to write an JavaFX Image to file
       * After testing, ImageIO.write only works for
       *   png and gif formats 
       * ImagIO.write does not work for these formats:
       *   jpg, jpeg, bmp
       * This method first check if the given file has
       * extension matching preferred formats (png|gif)
       * if it doesn't match, concate default format (.png)
       * @param img
       * @param file
       * @return 
       */
      public File writeImage(Image img, File file) {
        // check if the given file extension matches preferred
        // image format string : (png|gif)
        String formatName = getFormatName(file);
        if (formatName == null) {
          // the given file does not ends with preferred image format
          // use "png" as format
          formatName = "png"; // default format name
          file = getImageFile(file, formatName);
        }
        writeFXImage(img, formatName, file);
        return file;
      }

      /**
       * This method is called when writing an ImageView object to fxml file
       * It is called from writeFXML to save the image of an ImageView
       * object if the image does not exist in physical file yet
       * The image file name is obtained by concatenating the prefix of
       * fxml file name with image format:
       * If fxml file name is objects.fxml, 
       * resulting image file names would look like these:
       *	 objects_1.png, objects_2.png,...
       *
       * Apply ImageIO.write method to write an JavaFX Image to file
       * Note: ImageIO.write cannot save jpg, jpeg, bmp
       * @param img
       * @return 
       */
      File writeImage(Image img) {
        String formatName = "png"; // Initialize to default format name
        File imgFile = getImageFile(formatName);
        writeFXImage(img, formatName, imgFile);
        return imgFile;
      }

      /**
       * Apply ImageIO.write method to write an JavaFX Image to file
       * Note: ImageIO.write cannot save jpg, jpeg, bmp
       */
      void writeFXImage(Image img, String formatName, File imgFile) {
        try {
          boolean succeed = ImageIO.write(
             SwingFXUtils.fromFXImage(img, null), formatName, imgFile);
          System.out.format("writeFXImage to %s, result=%s%n",
                            imgFile, succeed);
          if (!succeed)
            System.out.println("ImageIO.write failed");
        } catch (IOException e) {
          System.out.println(e.getMessage());
        }
      }

      /**
       * Note for Java 8+, test if jpg,jpeg,bmp works
       * This method checks if file has preferred extension:
       *   png or gif,
       * if extension is not a preferred image format, 
       * return null, otherwise return image format
       * @param f
       * @return 
       */
      String getFormatName(File f) {
        String formatName = null; // Initialize to null
        // supported image format in regular expression
        //String reg = "(png|gif|jpg|jpeg|bmp)";
        // It would be nice to support jpg format
        // however,
        // jpg, jpeg and bmp not supported in ImagdIO.write
        // bmp do nothing, jpg,jpeg wrong image 
        String reg = "(png|gif)";
        String s = f.getName();
        int i = s.lastIndexOf('.');

        if (i > 0 && i < s.length() - 1) {
          String ext = s.substring(i + 1).toLowerCase();
          if (ext.matches(reg)) {
            formatName = ext;
          }
        }
        return formatName;
      }

      /**
       * This method is called from writeImageView method to
       * save the image of an ImageView to image file in
       * preferred format
       * Replacing file extension with given image format
       * If given file doesn't have any extension,
       * concat "." and format name
       * @return 
       */
      File getImageFile(File file, String formatName) {
        String s = file.getName();
        int i = s.lastIndexOf('.');
        if (i > 0 && i < s.length() - 1) {
          // replace whatever extension the given file has with .png
          s = s.substring(0, i);
          File p = file.getParentFile();
          String c = s + "." + formatName;
          return new File(p, c);
        } else {
          // file extension not exist, concat one
          return new File(file.getPath() + "." + formatName);
        }
      }

      /**
       * This method is called from writeFXML when saving an ImageView
       * object to an fxml file
       * Replace fxml file extension(.fxml) with image format(.png)
       * @return 
       */
      File getImageFile(String formatName) {
        // supported image format specified in regular expression
        //String reg = "(png|gif|jpeg)";
        String s = fxmlFile.getName();
        int i = s.lastIndexOf('.');
        if (i > 0 && i < s.length() - 1) {
          // replace .fxml with .png
          s = s.substring(0, i);
          File p = fxmlFile.getParentFile();
          // Make image file suffix like <name>_1.png for <name>.fxml
          // Example: 
          //  first created image file for objects.fxml is objects_1.png
          //  second created image file is objects_2.png
          // We do not check file existed or not
          String c = s + "_" + (++imageFileCount) + "." + formatName;
          return new File(p, c);
        } else {
          throw new RuntimeException("getImageFile error");
        }
      }

    }
    ```

    Compiling `drawtool` library in Command Line:

    ```
    Microsoft Windows [Version 6.3.9600]
    (c) 2013 Microsoft Corporation. All rights reserved.

    F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeFour\DrawTool1.4\src\example1>
    javac  -encoding utf-8 -Xlint:unchecked drawtool\*.java

    javac  -encoding utf-8 -Xlint:unchecked drawtool\io\*.java

    javac  -encoding utf-8 -Xlint:unchecked drawtool\shape\*.java

    javac  -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

    jar cf drawtool.jar drawtool resource
    ```

1.  ## 1.4 Summary

    This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

    *   `SwingFXUtils` class resides in `javafx.embed.swing` package, and provides methods to convert types between JavaFX Image and Swing/AWT Image:

        `static BufferedImage fromFXImage(Image` img`, BufferedImage` bimg`)`

        `static WritableImage toFXImage(BufferedImage` bimg`, WritableImage` wimg`)`

        (See section [Implement `writeImageView` Method](#part0007_split_001.html_implement-write-image-view))
    *   `Image` class extends `java.lang.Object` and resides in `javafx.scene.image` package, for loading images. An `Image` can be constructed by passing a string url or an `InputStream` to its constructor. Use an `ImageView` object to display an `Image`.
        (See section [Implement `writeImageView` Method](#part0007_split_001.html_implement-write-image-view))
    *   `WritableImage snapshot(SnapshotParameters` params`, WritableImage` image`)` method, is defined in `Node` class, for taking a snapshot on a node whether it is part of a scene or not. It returns a `WritableImage`, a direct subclass of `javafx.scene.image.Image`.
        (See section [Implement `writeImageView` Method](#part0007_split_001.html_implement-write-image-view))
    *   `ImageView` class extends `javafx.scene.Node` and resides in `javafx.scene.image` package, for displaying images. An `Image` can be constructed by passing a url of `String` type or an `Image` to its constructor.
        (See section [Implement `writeImageView` Method](#part0007_split_001.html_implement-write-image-view))
    *   `SnapshotParameters` class extends `java.lang.Object` and resides in `javafx.scene` package; it provides utilities to set parameters for taking a snapshot on a `javafx.scene.Node`, such as:

        `setFill(Paint` fill`)`

        `setViewport(Rectangle2D` viewport`)`

        (See [Complete Source Code of `writeImageView` Method](#part0007_split_001.html_write-image-view-codes))
    *   `Bounds`, an abstract class, resides in `javafx.geometry package`, and defines utilities to manipulate a rectangular region, measuring its coordinates and dimensions: minX, minY, maxX, maxY, width, height.
        (See sections: [Exploit `boundsInLocal` and `boundsInParent`](#part0007_split_001.html_exploit-bounds), [Exploit `layoutBounds`](#part0007_split_001.html_learn-layout-bounds))
    *   `boundsInLocal`, a property of type `ReadOnlyObjectProperty<Bounds>`, defined in the `Node` class, specifies a `Bounds` object which indicates a rectangular bounding region of a `Node`, without taking into account any transformation applied onto it.
        (See sections: [Exploit `boundsInLocal` and `boundsInParent`](#part0007_split_001.html_exploit-bounds), [Exploit `layoutBounds`](#part0007_split_001.html_learn-layout-bounds))
    *   `boundsInParent`, a property of type `ReadOnlyObjectProperty<Bounds>`, defined in the `Node` class, specifies a `Bounds` object which indicates a rectangular bounding region of a `Node`, taking into account all transformations, such as translate, scale, rotate, etc., applied onto it.
        (See sections: [Exploit `boundsInLocal` and `boundsInParent`](#part0007_split_001.html_exploit-bounds), [Exploit `layoutBounds`](#part0007_split_001.html_learn-layout-bounds))
    *   `layoutBounds`, a property of type `ReadOnlyObjectProperty<Bounds>` defined in `Node` class, specifying a `Bounds` object, does not take into account these properties: `effect`, `clip`, `scaleX`, `scaleY`, `rotate`, `translateX`, `translateY`, `layoutX`, `layoutY`; and it also excludes any `Transform` object applied to a `Node`.
        (See section [Exploit `layoutBounds`](#part0007_split_001.html_learn-layout-bounds))
    *   `RadialGradient` class, resided in `javafx.scene.paint` package, is a direct subclass of `Paint` class.
        (See sections: [Create `Rectangle` Filled with `RadialGradient` in FXML](#part0007_split_002.html_create-rectangle), [Create `Arc` Painted like Rainbow in FXML](#part0007_split_002.html_create-arc))
    *   `LinearGradient` class, resided in `javafx.scene.paint` package, is a direct subclass of `Paint` class.
        (See section [Create `Circle` Filled with `LinearGradient` in FXML](#part0007_split_002.html_create-circle))
    *   `CycleMethod` class, an enumerated type, resided in `javafx.scene.paint` package, is used along with `LinearGradient` and `RadialGradient` classes. It defines constants: `CycleMethod.NO_CYCLE`, `CycleMethod.REFLECT`, and `CycleMethod.REPEAT`.
        (See sections: [Create `Rectangle` Filled with `RadialGradient` in FXML](#part0007_split_002.html_create-rectangle), [Create `Arc` Painted like Rainbow in FXML](#part0007_split_002.html_create-arc), [Create `Circle` Filled with `LinearGradient` in FXML](#part0007_split_002.html_create-circle))
    *   `Stop` class, resided in `javafx.scene.paint` package, is used along with `LinearGradient` and `RadialGradient` classes. To create an instance of `Stop` requires two parameters, offset and color.
        (See sections: [Create `Rectangle` Filled with `RadialGradient` in FXML](#part0007_split_002.html_create-rectangle), [Create `Arc` Painted like Rainbow in FXML](#part0007_split_002.html_create-arc), [Create `Circle` Filled with `LinearGradient` in FXML](#part0007_split_002.html_create-circle))

# Chapter 2 Enhanced Draw Tool with Draw Loader Capacity
--Developing Shape Drawing Tools V1.4 (Part 2)

## Preface

In this chapter, we'll introduce `DrawLoader` class, resides in `drawtool.io package`, to load FXML files as well as image files to a drawing board.

From detailed descriptions and well-documented example code excerpted from developments of `Shape Drawing Tools V1.4 (Part 2)`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0008_split_003.html_summary) section.

The complete development process of `Shape Drawing Tools V1.4 (Part 2)` is characterized by the following steps:

*   [2.1 Create `DrawLoader` Class](#part0008_split_001.html_create-draw-loader)
    *   [2.1.1 Implement `loadFXML` Methods](#part0008_split_001.html_implement-load-fxml)
    *   [2.1.2 Implement `loadImage` Method](#part0008_split_001.html_implement-load-image)
*   [2.2 Complete Source Code of `DrawLoader` Class](#part0008_split_002.html_complete-source-codes-draw-loader)
*   [2.3 Summary](#part0008_split_003.html_summary)

## 2.1 Create `DrawLoader` Class

The `DrawLoader` class resides in `drawtool.io` package, and provides intuitive, higher level APIs to load FXML files as well as image files. The source is an instance of `File`. If it is an image file, an `ImageView` object is created, with the loaded image set to its `image` property. If it is an FXML file, either hand coded or previously generated by a program that employs APIs provided in `DrawWriter` class, referring to prior chapter, then descendants of the root node loaded from the file are added to the given drawing pane.

### 2.1.1 Implement `loadFXML` Methods

The `DrawLoader` class provides two `loadFXML` methods:

```
 public ObservableList<Node> loadFXML(File file, Pane pane)
  public ObservableList<Node> loadFXML(File file)
```

1.  `public ObservableList<Node> loadFXML(File` file`, Pane` pane`)`

    Load an FXML file and add descendants of the root node, or root node itself, to the children list of the specified pane. And if the root node loaded from the specified file is a `Pane` possessing a map of properties, retrievable using the `getProperties()` method defined in `Node` class, elements in entry set of the map are added to the map of properties of the given pane.

2.  `public ObservableList<Node> loadFXML(File` file`)`

    Load the given FXML file and return descendants of the root node, or root node itself, in a list.

Please notice that, we check whether the root node of a scene graph stored in an FXML file belongs to these types:

1.  `Pane`
2.  `Group`

If it is not, then the root node itself, instead of its descendants, is returned to the caller in a list.

The `FXMLLoader` class extends `java.lang.Object` and resides in `javafx.fxml` package, providing functionality to load FXML documents. Here's the static method, defined in `FXMLLoader` class, used inside our `loadFXML` methods:

```
 public static <T> T load(URL location)
                  throws IOException 
```

Here's complete source code of our `loadFXML` methods:

Import Statements:

```
 import java.io.File;
import java.io.IOException;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.*;
import javafx.collections.*;
import javafx.fxml.FXMLLoader;
import javafx.scene.Group;
import javafx.scene.Node;
import javafx.scene.layout.Pane;
```

Listing 2-1. Define `loadFXML` methods:

```
 /**
   * Load FXML file to obtain root node of a scene graph
   * If root node is a Pane or a Group,
   * add its descendants to children list of the given pane 
   * If it is not a Pane or a Group,
   * add root node itself to the children list of the given pane 
   * And if root node is a pane,
   * we add its properties (a map) to the given pane as well
   */
  public ObservableList<Node> loadFXML(File file, Pane pane) {
    try {
      // get URL from File
      URL url = file.toURI().toURL();
      Node root = FXMLLoader.load(url);

      ObservableList<Node> nodeList = getRootDescendant(root);
      pane.getChildren().addAll(nodeList);

      ObservableMap<Object, Object> map = root.getProperties();
      // add properties (a map) to pane if root is a pane
      if (root instanceof Pane) {
        Iterator<Map.Entry<Object, Object>> it = map.entrySet().iterator();
        while (it.hasNext()) {
          Map.Entry<Object, Object> e = it.next();
          pane.getProperties().put(e.getKey(), e.getValue());
        }
      }      
      return nodeList;
    } catch(MalformedURLException e) {
      System.out.println(e);
    } catch(IOException e) {
      System.out.println(e);
    }     
    // return an empty list
    return FXCollections.observableArrayList();     
  }

  /**
   * Load FXML file to obtain root node of a scene graph
   * If root node is a Pane or a Group,
   * return children list of root node
   * If root node is not a Pane or a Group 
   * return root node in a list
   */
  public ObservableList<Node> loadFXML(File file) {
    try {
      // get URL from File
      URL url = file.toURI().toURL();
      Node root = FXMLLoader.load(url);
      return getRootDescendant(root);
    } catch(MalformedURLException e) {
      System.out.println(e);
    } catch(IOException e) {
      System.out.println(e);
    }     
    // return an empty list
    return FXCollections.observableArrayList();     
  }

  ObservableList<Node> getRootDescendant(Node root) {
    if (root instanceof Pane) 
      return ((Pane)root).getChildren();
    if (root instanceof Group) 
      return ((Group)root).getChildren();

    // return a list with root node added to it
    return FXCollections.observableArrayList(root);     
  }
```

### 2.1.2 Implement `loadImage` Method

In addition to load FXML files, the `DrawLoader` class provides a `loadImage` method:

```
 public ImageView loadImage(File file, double maxWidth, double maxHeight)
```

The `loadImage` method loads an image from the specified file and returns an `ImageView` object for viewing. The maximum viewing size is specified in arguments: `maxWidth` and `maxHeight`.

Here's complete source code of the `loadImage` method:

Import Statements:

```
 import java.io.File;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
```

Listing 2-2. Define `loadImage` method to load image file and return an `ImageView` object to view the loaded image:

```
 /**
   *  Return an ImageView, url as string is put in properties of ImageView
   */
  public ImageView loadImage(File file, double maxWidth, double maxHeight) {
    String url = file.toURI().toString();
    Image image = new Image(url);
    ImageView imageView = new ImageView();
    imageView.setPreserveRatio(true);  
    // If image is larger than maxWidth/maxHeight,
    // initialize imageView to fit maxWidth/maxHeight
    if (image.getWidth() > maxWidth) {
      imageView.setFitWidth(maxWidth);
    } else if (image.getHeight() > maxHeight) {
      imageView.setFitHeight(maxHeight);
    }
    imageView.setImage(image);
    // put url in properties (a map)
    imageView.getProperties().put("imageURL", url);
    return imageView;
  }
```

## 2.2 Complete Source Code of `DrawLoader` Class

Listing 2-3. Complete source code of `DrawLoader` class:

```
 package drawtool.io;

import java.io.File;
import java.io.IOException;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.*;
import javafx.collections.*;
import javafx.fxml.FXMLLoader;
import javafx.scene.Group;
import javafx.scene.Node;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.Pane;

/**
 * File Name: DrawLoader.java
 * (in directory: DrawTool1.4/src/example1/drawtool/io)
 * This class handles FXML file loading and image file loading
 * Source is an instance of File.
 *
 * @author Shufen Kuo
 */

public class DrawLoader {

  /**
   *  Return an ImageView, url as string is put in properties of ImageView
   */
  public ImageView loadImage(File file, double maxWidth, double maxHeight) {
    String url = file.toURI().toString();
    Image image = new Image(url);
    ImageView imageView = new ImageView();
    imageView.setPreserveRatio(true);  
    // If image is larger than maxWidth/maxHeight,
    // initialize imageView to fit maxWidth/maxHeight
    if (image.getWidth() > maxWidth) {
      imageView.setFitWidth(maxWidth);
    } else if (image.getHeight() > maxHeight) {
      imageView.setFitHeight(maxHeight);
    }
    imageView.setImage(image);
    // put url in properties (a map)
    imageView.getProperties().put("imageURL", url);
    return imageView;
  }

  /**
   * Load FXML file to obtain root node of a scene graph
   * If root node is a Pane or a Group,
   * add its descendants to children list of the given pane 
   * If it is not a Pane or a Group,
   * add root node itself to the children list of the given pane 
   * And if root node is a pane,
   * we add its properties (a map) to the given pane as well
   */
  public ObservableList<Node> loadFXML(File file, Pane pane) {
    try {
      // get URL from File
      URL url = file.toURI().toURL();
      Node root = FXMLLoader.load(url);

      ObservableList<Node> nodeList = getRootDescendant(root);
      pane.getChildren().addAll(nodeList);

      ObservableMap<Object, Object> map = root.getProperties();
      // add properties (a map) to pane if root is a pane
      if (root instanceof Pane) {
        Iterator<Map.Entry<Object, Object>> it = map.entrySet().iterator();
        while (it.hasNext()) {
          Map.Entry<Object, Object> e = it.next();
          //System.out.format("%s %s%n", e.getKey().toString(), e.getValue().toString());
          pane.getProperties().put(e.getKey(), e.getValue());
        }
      }      
      return nodeList;
    } catch(MalformedURLException e) {
      System.out.println(e);
    } catch(IOException e) {
      System.out.println(e);
    }     
    // return an empty list
    return FXCollections.observableArrayList();     
  }

  /**
   * Load FXML file to obtain root node of a scene graph
   * If root node is a Pane or a Group,
   * return children list of root node
   * If root node is not a Pane or a Group 
   * return root node in a list
   */
  public ObservableList<Node> loadFXML(File file) {
    try {
      // get URL from File
      URL url = file.toURI().toURL();
      Node root = FXMLLoader.load(url);
      return getRootDescendant(root);
    } catch(MalformedURLException e) {
      System.out.println(e);
    } catch(IOException e) {
      System.out.println(e);
    }     
    // return an empty list
    return FXCollections.observableArrayList();     
  }

  ObservableList<Node> getRootDescendant(Node root) {
    if (root instanceof Pane) 
      return ((Pane)root).getChildren();
    if (root instanceof Group) 
      return ((Group)root).getChildren();

    // return a list with root node added to it
    return FXCollections.observableArrayList(root);     
  }

}
```

Compiling `drawtool` library in Command Line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeFour\DrawTool1.4\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked drawtool\io\*.java

javac -encoding utf-8 -Xlint:unchecked drawtool\shape\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool resource
```

We will elaborate on the usage of APIs defined inside `DrawLoader` class, when we implement `File` functionality within `JFXDrawTools V1.2` application in Chapter 3 of this book.

## 2.3 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `FXMLLoader` class extends `java.lang.Object` and resides in `javafx.fxml` package, providing utilities to load FXML documents.
    (See section [Implement `loadFXML` Methods](#part0008_split_001.html_implement-load-fxml))
*   `Image` class extends `java.lang.Object` and resides in `javafx.scene.image` package, for loading images. An `Image` can be constructed by passing a string url or an `InputStream` to its constructor. Use an `ImageView` object to display an `Image`.
    (See section [Implement `loadImage` Method](#part0008_split_001.html_implement-load-image))
*   `ImageView` class extends `javafx.scene.Node` and resides in `javafx.scene.image` package, for displaying images. An `Image` can be constructed by passing a url of `String` type or an `Image` to its constructor.
    (See section [Implement `loadImage` Method](#part0008_split_001.html_implement-load-image))

# Chapter 3
Enhanced JFXDrawTools with Draw Writer and Draw Loader Capacities
--Developing JFXDrawTools V1.2

## Preface

In VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS Chapter 8 Initial JFXDrawTools Application, and in VOLUME Ⅲ: DEVELOPING INTERACTIVE REGULAR POLYGON DRAWING TOOLS Chapter 3 Enhanced JFXDrawTools with Regular Polygon Drawer Capacity, we have demonstrated how to utilize APIs provided in `drawtool` package, `drawtool.drawer` package, and `drawtool.shape` package to develop a drawing application, `JFXDrawTools` , `V1.0` and `V1.1`. It has capabilities to interactively draw and move these shapes: Line, Polyline, Polygon, Path, QuadCurve (quadratic Bézier Curve), Rectangle, Circle, Ellipse and Regular Polygon. Here are snapshots for `JFXDrawTools V1.0` and `JFXDrawTools V1.1`:

Figure 3-1. Snapshot of the JFXDrawTools V1.0 application.

![](images/00029.jpeg "jfx_draw_tools_1_0.jpg")

Figure 3-2. Snapshot of the JFXDrawTools V1.1 application.

![](images/00030.jpeg "jfx_draw_tools_1_1.jpg")

In this chapter, we will integrate sketch saving and loading capabilities developed in previous chapters into `JFXDrawTools V1.1`, and upgrade the version number to V1.2.

From detailed descriptions and well-documented example code excerpted from developments of `JFXDrawTools V1.2`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0009_split_009.html_summary) section.

The complete development process of `JFXDrawTools V1.2` is characterized by the following steps:

*   [3.1 Add `File` Menu to Menu Bar](#part0009_split_001.html_add-file-menu)
*   [3.2 Generate FXML Files for Drawings Using `DrawWriter` Class](#part0009_split_002.html_generate-fxml)
*   [3.3 Add `Save FXML` Submenu to `File` Menu](#part0009_split_003.html_add-save-fxml-sub-menu)
*   [3.4 Load Drawings from FXML Files Using `DrawLoader` Class](#part0009_split_004.html_load-drawing)
    *   [3.4.1 Load FXML Files](#part0009_split_004.html_load-fxml-files)
    *   [3.4.2 Load Image Files](#part0009_split_004.html_load-image-files)
*   [3.5 Add `Open` Submenu to `File` Menu](#part0009_split_005.html_add-open-sub-menu)
*   [3.6 Bind Stage Title for Displaying FXML File Name](#part0009_split_006.html_bind-stage-title)
*   [3.7 Add `Action` Menu to Menu Bar](#part0009_split_007.html_add-action-menu)
*   [3.8 Complete Source Code of `JFXDrawTools` Class](#part0009_split_008.html_complete-source-codes-jfx-draw-tools)
*   [3.9 Summary](#part0009_split_009.html_summary)

## 3.1 Add `File` Menu to Menu Bar

In this section, we'll create a `File` menu and add to menu bar. Initially, `File` menu contains menu item `Exit`. Here's the source code to create a `File` menu:

Listing 3-1. Create `File` menu with menu item `Exit`:

```
 MenuBar createMenuBar(Stage stage) {
    MenuBar menuBar = new MenuBar();
    Menu menuFile = createMenuFile(stage);
    Menu menuTools = createMenuTools();
    Menu menuPref = createMenuPreference();
    menuBar.getMenus().addAll(menuFile, menuTools, menuPref);

    return menuBar;
  }

  Menu createMenuFile(final Stage stage) {
    Menu menuFile = new Menu("File");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().add(exit);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });
    return menuFile;
  }
```

## 3.2 Generate FXML Files for Drawings Using `DrawWriter` Class

In this section, we'll demonstrate how to use APIs defined in `DrawWriter` class, referring to [Chapter 1](#part0007_split_000.html_6LJU0-6cbc394105fd4c6ab27dd0d32efbcd86) of this book, to generate FXML files, in which drawings created interactively on a drawing board are saved. The following method will be used:

```
 public void writeFXML(Pane pane, File file)
```

Please notice that, in the following example, we create an instance of `DrawPane`, placed at the center of a `BorderPane` as our drawing board. The `DrawPane`, a direct subclass of `Pane` class, registers event handlers to handle events which are significant to draw shapes interactively on the pane itself. These events include mouse pressed, mouse dragged, mouse released, key pressed, etc. For detailed description and complete source code of `DrawPane` class, refer to VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS Chapter 6 Basic Draw Tool Section 6.2 Create `DrawPane` Class, and Chapter 7 Enhanced Draw Tool with Predefined Drawers Section 7.3 Enhance `DrawPane` Class.

The following snippets of code save sketching from a drawing board to an FXML file using `DrawWriter` class, in which the `writeFXML` method is defined:

Import Statements:

```
import java.io.File;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.MenuItem;
import javafx.scene.layout.BorderPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

import drawtool.DrawPane;
import drawtool.io.DrawWriter;
```

Listing 3-2. Write drawings from a drawing board to an FXML file using `DrawWriter` class:

```
public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane = new DrawPane();

  // Create a DrawWriter to save shapes/images 
  DrawWriter drawWriter = new DrawWriter();

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    rootPane.setCenter(drawPane);

        ...

    // Create a file chooser for saveAllAs
    final FileChooser fileChooser = new FileChooser();
    fileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("FXML", "*.fxml"),
        new FileChooser.ExtensionFilter("All Files", "*.*"));

        ...

    MenuItem saveAllAs = new MenuItem("Save All As...");

    // Add action for saveAllAs menu item
    // Open FileChooser to select a file
    saveAllAs.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        fileChooser.setTitle("Save All As FXML File");
        File file = fileChooser.showSaveDialog(stage);
        if (file != null) {
          drawWriter.writeFXML(drawPane, file);
        }
      }
    }); 

    ... 
```

## 3.3 Add `Save FXML` Submenu to `File` Menu

Here, let's explore the details of implementation of `Save FXML` submenu. First, create a `Save FXML` submenu, and add to the `File` menu of menu bar. The `Save FXML` submenu has two menu items: "Save All", and "Save All As...". The action of "Save All" saves all objects on a drawing board to the current loaded/saved FXML file. If it is the first time on action, a default FXML file named "JFXDrawTools.fxml" is used. In the action of "Save All..." pops up a Save Dialog of `FileChooser` to save all objects to a file selected from the Save Dialog.

A class field, `curFXMLFile`, is defined; it is a property of type `ObjectProperty<File>` to specify the current file. Its value is updated when an FXML file is saved or loaded.

Listing 3-3. Create `Save FXML` menu with `Save All` menu item and `Save All As...` menu item:

```
 // Specify a file either last saved or last opened
  ObjectProperty<File> curFXMLFile = new SimpleObjectProperty<>();
  ObjectProperty<File> curImageFile = new SimpleObjectProperty<>();

  Menu createMenuFile(final Stage stage) {
    Menu menuFile = new Menu("File");
    Menu saveFXMLMenu = createMenuSaveFXML(stage);
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(saveFXMLMenu, exit);

            ...

    return menuFile;
  }

  Menu createMenuSaveFXML(final Stage stage) {
    Menu menuSave = new Menu("Save FXML");
    MenuItem saveAll = new MenuItem("Save All");
    saveAll.setAccelerator(
      new KeyCharacterCombination("S", KeyCombination.CONTROL_DOWN));
    MenuItem saveAllAs = new MenuItem("Save All As...");

    menuSave.getItems().addAll(saveAll, saveAllAs);

    // Create a file chooser for saveAllAs
    final FileChooser fileChooser = new FileChooser();

    // Set "." as default dir
    fileChooser.setInitialDirectory(new File("."));

    fileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("FXML", "*.fxml"),
        new FileChooser.ExtensionFilter("All Files", "*.*"));

    // Add action for saveAll menu item
    // Save to last opened file if there is one
    // If this is the first time do Save action, no file name yet,
    // use default name
    saveAll.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Get file from curFXMLFile property
        File file = curFXMLFile.get(); // get latest open file
        if (file == null) {
          // This is first time do "Save All", no file name yet
          // using default dir and name          
          File dir = fileChooser.getInitialDirectory();
          // instead of open FileChooser dialog, use default name
          String name = "JFXDrawTools";
          file = new File(dir, name);

        }
        file = getPrefFileExtension(file, "fxml");
        curFXMLFile.set(file);
        // Clean unfinished drawing is necessary
        // before an action is taken
        cleanUnfinished();
        drawWriter.writeFXML(drawPane, file);
      }
    }); 

    // Add action for saveAllAs menu item
    // Open FileChooser to select a file
    saveAllAs.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        fileChooser.setTitle("Save All As FXML File");
        // Set last dir as default dir
        if (curFXMLFile.get() != null) {
          File lastDir = curFXMLFile.get().getParentFile();
          fileChooser.setInitialDirectory(lastDir);
        }
        File file = fileChooser.showSaveDialog(stage);
        if (file != null) {
          file = getPrefFileExtension(file, "fxml");
          curFXMLFile.set(file);
          // Clean unfinished drawing is necessary
          // before an action is taken
          cleanUnfinished();
          drawWriter.writeFXML(drawPane, file);
        }
      }
    });

    return menuSave;
  }

  /**
   * Check if the file ends with the given preferred extension, 
   * if not, return a new file with the given preferred extension
   * Note for future release: check if the new file name exists 
   * or not, and prompt warning message (Replace or Cancel)
   * if it exists
   *
   * @param f
   * @param ext
   * @return
   */
  File getPrefFileExtension(File f, String ext) {
    String s = f.getName();
    if (s.endsWith("." + ext)) {
      return f;
    }
    return new File(f.getPath() + "." + ext);
  }
```

## 3.4 Load Drawings from FXML Files Using `DrawLoader` Class

In this section, we'll demonstrate how to use APIs defined in `DrawLoader` class, referring to [Chapter 2](#part0008_split_000.html_7K4G0-6cbc394105fd4c6ab27dd0d32efbcd86) of this book, to load an FXML file, in which a scene graph is saved, or to load an image file. The following methods will be used:

```
 public ObservableList<Node> loadFXML(File file, Pane pane)
  public ImageView loadImage(File file, double maxWidth, double maxHeight)
```

### 3.4.1 Load FXML Files

The following snippets of code load drawings from an FXML file to a drawing board using the `DrawLoader` class, in which the `loadFXML` method is defined:

Import Statements:

```
import java.io.File;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.MenuItem;
import javafx.scene.layout.BorderPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

import drawtool.DrawPane;
import drawtool.io.DrawLoader;
```

Listing 3-4. Load drawings from an FXML file to a drawing board using `DrawLoader` class:

```
public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane = new DrawPane();

  // Create a DrawLoader to open files of shapes/images
  DrawLoader drawLoader = new DrawLoader();

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    rootPane.setCenter(drawPane);

        ...

    // Create a file chooser for loadFXML menuItem
    final FileChooser fxmlFileChooser = new FileChooser();

    fxmlFileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("FXML", "*.fxml"),
        new FileChooser.ExtensionFilter("All Files", "*.*"));

        ...

    MenuItem loadFXML = new MenuItem("Open FXML...");

    // Add action for loadFXML menu item
    loadFXML.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        fxmlFileChooser.setTitle("Open FXML File");
        File file = fxmlFileChooser.showOpenDialog(stage);
        if (file != null) {
          ObservableList<Node> list = 
            drawLoader.loadFXML(file, drawPane);
        }
      }
    });

    ... 
```

### 3.4.2 Load Image Files

The following example loads an image and displays it on a drawing board, using the `DrawLoader` class, in which the `loadImage` method is defined:

Import Statements:

```
import java.io.File;
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.MenuItem;
import javafx.scene.image.ImageView;
import javafx.scene.layout.BorderPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

import drawtool.DrawPane;
import drawtool.io.DrawLoader;
```

Listing 3-5. Load an image and display it on a drawing board, using `DrawLoader` class:

```
public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane = new DrawPane();

  // Create a DrawLoader to open files of shapes/images
  DrawLoader drawLoader = new DrawLoader();

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    rootPane.setCenter(drawPane);

        ...

    MenuItem loadImage = new MenuItem("Open Image...");

    // Create a file chooser for loadImage menuItem
    final FileChooser imageFileChooser = new FileChooser();

    imageFileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("All Images",
        "*.bmp", "*.gif", "*.jpeg", "*.jpg", "*.png"),
        new FileChooser.ExtensionFilter("All Files", "*.*"),
        new FileChooser.ExtensionFilter("BMP", "*.bmp"),
        new FileChooser.ExtensionFilter("GIF", "*.gif"),
        new FileChooser.ExtensionFilter("JPEG", "*.jpeg"),
        new FileChooser.ExtensionFilter("JPG", "*.jpg"),
        new FileChooser.ExtensionFilter("PNG", "*.png"));

    // Add action for loadImage menu item
    loadImage.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        imageFileChooser.setTitle("Open Image File");
        File file = imageFileChooser.showOpenDialog(stage);
        if (file != null) {
          ImageView iv = drawLoader.loadImage(file,
            Double.MAX_VALUE, Double.MAX_VALUE);
          drawPane.getChildren().add(iv);
        }
      }
    });

    ... 
```

## 3.5 Add `Open` Submenu to `File` Menu

Here, let's explore the details of implementation of `Open` submenu. First, create an `Open` submenu, added to the `File` menu of menu bar. The `Open` submenu has two menu items: "Open FXML..." and "Open Image...". In the action of "Open FXML..." loads all nodes from a selected FXML file and displays them on a drawing board. In the action of "Open Image..." loads an image from a selected file and displays it on a drawing board.

Listing 3-6. Create `Open` menu with `Open FXML...` menu item and `Open Image...` menu item:

```
 // Specify a file either last saved or last opened
  ObjectProperty<File> curFXMLFile = new SimpleObjectProperty<>();
  ObjectProperty<File> curImageFile = new SimpleObjectProperty<>();

  Menu createMenuFile(final Stage stage) {
    Menu menuFile = new Menu("File");
    Menu loadSubmenu = createMenuLoad(stage);
    Menu saveFXMLMenu = createMenuSaveFXML(stage);
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(loadSubmenu, saveFXMLMenu, exit);

        ...

    return menuFile;
  }

  Menu createMenuLoad(final Stage stage) {
    Menu menuLoad = new Menu("Open");
    MenuItem loadFXML = new MenuItem("Open FXML...");
    MenuItem loadImage = new MenuItem("Open Image...");
    menuLoad.getItems().addAll(loadFXML, loadImage);

    // Create a file chooser for loadFXML menuItem
    final FileChooser fxmlFileChooser = new FileChooser();

    // Set "." as default dir
    fxmlFileChooser.setInitialDirectory(new File("."));

    fxmlFileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("FXML", "*.fxml"),
        new FileChooser.ExtensionFilter("All Files", "*.*"));

    // Add action for loadFXML menu item
    loadFXML.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        fxmlFileChooser.setTitle("Open FXML File");
        // Set last dir as default dir
        if (curFXMLFile.get() != null) {
          File lastDir = curFXMLFile.get().getParentFile();
          fxmlFileChooser.setInitialDirectory(lastDir);
        }
        File file = fxmlFileChooser.showOpenDialog(stage);
        if (file != null) {
          ObservableList<Node> list = 
            drawLoader.loadFXML(file, drawPane);
          curFXMLFile.set(file); 
        }
      }
    });

    // Create a file chooser for loadImage menuItem
    final FileChooser imageFileChooser = new FileChooser();

    // Set "." as default dir
    imageFileChooser.setInitialDirectory(new File("."));

    imageFileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("All Images",
        "*.bmp", "*.gif", "*.jpeg", "*.jpg", "*.png"),
        new FileChooser.ExtensionFilter("All Files", "*.*"),
        new FileChooser.ExtensionFilter("BMP", "*.bmp"),
        new FileChooser.ExtensionFilter("GIF", "*.gif"),
        new FileChooser.ExtensionFilter("JPEG", "*.jpeg"),
        new FileChooser.ExtensionFilter("JPG", "*.jpg"),
        new FileChooser.ExtensionFilter("PNG", "*.png"));

    // Add action for loadImage menu item
    loadImage.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        imageFileChooser.setTitle("Open Image File");
        // Set last dir as default dir
        if (curImageFile.get() != null) {
          File lastDir = curImageFile.get().getParentFile();
          imageFileChooser.setInitialDirectory(lastDir);
        }
        File file = imageFileChooser.showOpenDialog(stage);
        if (file != null) {
          ImageView iv = drawLoader.loadImage(file,
            Double.MAX_VALUE, Double.MAX_VALUE);
          drawPane.getChildren().add(iv);
          curImageFile.set(file); 
        }
      }
    });

    return menuLoad;
  }
```

Figure 3-3. Snapshot `File` menu, when mouse hovering over `Save FXML` submenu.

![](images/00031.jpeg "save_fxml_menu.jpg")

Figure 3-4. Snapshot `File` menu, when mouse hovering over `Open` submenu.

![](images/00032.jpeg "open_menu.jpg")

## 3.6 Bind Stage Title for Displaying FXML File Name

It would be helpful to show file name of the current saved/loaded file on the title of `Stage`. A `StringBinding` object is created, and binds with the `title` property of `Stage`. Here's the source code to do these:

Listing 3-7. Define `bindStageTitle` method to display FXML file name on title of stage:

```
 // Specify a file either last saved or last opened
  ObjectProperty<File> curFXMLFile = new SimpleObjectProperty<>();

    ...

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    rootPane.setCenter(drawPane);

      ...

    rootPane.setStyle("-fx-background-color: transparent;");
    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    bindStageTitle(stage);

      ...

    stage.show();
  }

  /**
   * Display current FXML file name on title of stage
   * Obtain current FXML file name specified in curFXMLFile property
   * curFXMLFile property value is updated whenever
   * an FXML file is saved or loaded
   * @param stage 
   */
  void bindStageTitle(Stage stage) {
    StringBinding fileNameB = new StringBinding() {
      {
        super.bind(curFXMLFile);
      }

      @Override
      protected String computeValue() {
        String name = "";
        if (curFXMLFile.get() != null)
          name = " - " + curFXMLFile.get().getName(); 
        return "JFXDrawTools V1.2 Shufen Source Code" + name;
        }
    };
    stage.titleProperty().bind(fileNameB);
  }
```

Figure 3-5. Draw some shapes, save them to a file named MySketch_2.fxml, and then open it, using `JFXDrawTools V1.2` application. The file name is shown on title of `Stage`.

![](images/00033.jpeg "my_sketch_2.jpg")

Figure 3-6. Open an FXML file MySketch_2.fxml saved previously, and continue editing the sketch, using `JFXDrawTools V1.2` application. The file name is shown on title of `Stage`.

![](images/00034.jpeg "/my_sketch_heart.jpg")

## 3.7 Add `Action` Menu to Menu Bar

In this section, we add an `Action` menu to menu bar. Initially it contains only one menu item, "Clear All". In a process of sketch drawing, very often we need to clear all nodes on drawing board. In future versions, more actions will be added to the `Action` menu. Here's the source code to do these:

Listing 3-8. Create `Action` menu with `Clear All` menu item:

```
 MenuBar createMenuBar(Stage stage) {
    MenuBar menuBar = new MenuBar();
    Menu menuFile = createMenuFile(stage);
    Menu menuTools = createMenuTools();
    Menu menuAction = createMenuAction();
    Menu menuPref = createMenuPreference();
    menuBar.getMenus().addAll(menuFile, menuTools, menuAction, menuPref);

    return menuBar;
  }

  Menu createMenuAction() {
    Menu menu = new Menu("Action");
    MenuItem clearAll = new MenuItem("Clear All");
    menu.getItems().addAll(clearAll);

    // Add action for "Clear All" menu item
    clearAll.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        drawPane.getChildren().clear();
        // must also clear contents of Properties map
        // if it is not empty
        Map<Object, Object> map = drawPane.getProperties();
        if (map.size() != 0) {
          map.clear();
        }

       cleanUnfinished();
      }
    });

    return menu;
  }

  /**
   * This method is called whenever some action is taken
   *  such as: Clear All, Save FXML
   */
  void cleanUnfinished() {
    ShapeDrawer tool = drawPane.getDrawer();
    if (tool != null && tool.getShape() != null) {
      if (drawPane.isDragged()) {
        tool.onMouseDragFinished(drawPane);
      }
      tool.clean(drawPane);
      tool.setShape(null);  // complete this shape
    }
  }
```

Figure 3-7. Snapshot `Action` menu, when mouse hovering over `Clear All` menu item.

![](images/00035.jpeg "action_menu.jpg")

## 3.8 Complete Source Code of `JFXDrawTools` Class

Complete source code of `JFXDrawTools` class become these:

Listing 3-9. Complete source code of `JFXDrawTools` class:

```
package jfxdrawtools;

import java.io.File;
import java.util.Map;

import javafx.application.Application;
import javafx.application.Platform; 
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
import javafx.beans.binding.BooleanBinding;
import javafx.beans.binding.StringBinding;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.collections.ObservableList;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Insets;
import javafx.scene.Node;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.input.KeyCharacterCombination;
import javafx.scene.input.KeyCombination;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.VBox;
import javafx.scene.paint.Color;
import javafx.scene.shape.*;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.Text;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;
import drawtool.io.*;
import drawtool.shape.RegularPolygon;

/**
 * File Name: JFXDrawTools.java
 * (in directory: JFXDrawTools1.2/src/example1/jfxdrawtools/)
 * This application uses APIs in drawtool library to
 * draw a variety of shapes dynamically on a drawing board,
 * by means of mouse dragging, and writes to FXML files
 *
 * Add Regular Polygon Drawer capacity (V1.1)
 *
 * Add File menu with the following items (V1.2 example1)
 *    "Save FXML" submenu, "Open" submenu, and "Exit" menu item
 * "Open" submenu contains menu items:
 *    "Open FXML..." and "Open Image..."
 *
 * Define bindStageTitle method to display FXML file name
 * on title of stage (V1.2 example1)
 * 
 * Add "Action" menu with "Clear All" menu item (V1.2 example1)
 *
 * @author: Shufen Kuo
 */

enum DrawTools {
    LINE_DRAWER,
    POLYLINE_DRAWER,
    POLYGON_DRAWER,
    PATH_DRAWER,
    BEZIER_CURVE_DRAWER,
    RECTANGLE_DRAWER,
    CIRCLE_DRAWER,
    ELLIPSE_DRAWER,
    SHAPE_MOVER,
    REGULAR_POLYGON_DRAWER,
    NO_TOOL
} 

public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane = new DrawPane();

  // Create drawing tools
  LineDrawer lineDrawer = new LineDrawer();
  PolylineDrawer polylineDrawer = new PolylineDrawer();
  PolygonDrawer polygonDrawer = new PolygonDrawer();
  PathDrawer pathDrawer = new PathDrawer();
  BezierCurveDrawer bezierCurveDrawer = new BezierCurveDrawer();
  RectangleDrawer rectangleDrawer = new RectangleDrawer();
  CircleDrawer circleDrawer = new CircleDrawer();
  EllipseDrawer ellipseDrawer = new EllipseDrawer();
  RegularPolygonDrawer regularPolygonDrawer = new RegularPolygonDrawer();
  ShapeMover shapeMover = new ShapeMover();

  // Specify text to be shown on status bar at bottom of border pane 
  StringProperty footer = new SimpleStringProperty();
  // footer for line 2
  StringProperty footer2 = new SimpleStringProperty();

  // Specify current draw tool init to NO_TOOL
  ObjectProperty<DrawTools> drawTools =
    new SimpleObjectProperty<>(DrawTools.NO_TOOL);

  // Create StringBinding objects,
  // for applying Properties and Binding mechanism
  // to show drawing tips for these shapes:
  //  Line, Rectangle, Circle, Ellipse, Regular Polygon, and ShapeMover
  // Binding for footer2 is done dynamically inside activateDrawer method
  StringBinding lineTip = createLineTip();
  StringBinding rectangleTip = createRectangleTip();
  StringBinding circleTip = createCircleTip();
  StringBinding ellipseTip = createEllipseTip();
  StringBinding regularPolygonTip = createRegularPolygonTip();
  StringBinding shapeMoverTip = createShapeMoverTip();

  // Amount of hue in color for fill interior of polygons
  // initial value is 0
  // increase by 20 each time a different N is selected
  double hueForFill = 0; 

  // Create a DrawWriter to save shapes/images 
  DrawWriter drawWriter = new DrawWriter();
  // Create a DrawLoader to open files of shapes/images
  DrawLoader drawLoader = new DrawLoader();

  // Specify a file either last saved or last opened
  ObjectProperty<File> curFXMLFile = new SimpleObjectProperty<>();
  ObjectProperty<File> curImageFile = new SimpleObjectProperty<>();

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    rootPane.setCenter(drawPane);

    // Bind footer, to show mouse moving locations
    bindFooterForMouseMove();

    // Init preference for drawing of polygons
    RegularPolygon model = (RegularPolygon)regularPolygonDrawer.getPrefModel();
    model.setFill(Color.hsb(hueForFill, 1.0, 1.0)); // Red color
    model.setStroke(Color.hsb(0, 0, 0.36)); // lighter black

    // Init preference for drawing of Bezier curves
    bezierCurveDrawer.getPrefModel().setFill(null); // do not fill

    // Add a listener for drawTools property
    drawTools.addListener(new ChangeListener<DrawTools>() {
      @Override
      public void changed(ObservableValue<? extends DrawTools> ov,
                      DrawTools oldVal, DrawTools newVal) {
        if (newVal != null) {
          activateDrawer(newVal);
        }
      }
    });   

    // Add menu bar on top of BorderPane
    MenuBar menuBar = createMenuBar(stage);
    rootPane.setTop(menuBar);   

    // Add status bar to show footer
    VBox statusBar = createStatusBar();
    rootPane.setBottom(statusBar);

    rootPane.setStyle("-fx-background-color: transparent;");
    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    // Bind Stage title for displaying current FXML file name;
    bindStageTitle(stage);

    // set application's closed icon
    String iconName = "/resource/MyLogoIcon_1_2.png";
    Image iconImage = new Image(getClass().getResourceAsStream(
        iconName));
    stage.getIcons().add(iconImage);

    stage.show();
  }

  /**
   * Display current FXML file name on title of stage
   * Obtain current FXML file name specified in curFXMLFile property
   * curFXMLFile property value is updated whenever
   * an FXML file is saved or loaded
   * @param stage 
   */
  void bindStageTitle(Stage stage) {
    StringBinding fileNameB = new StringBinding() {
      {
        super.bind(curFXMLFile);
      }

      @Override
      protected String computeValue() {
        String name = "";
        if (curFXMLFile.get() != null)
          name = " - " + curFXMLFile.get().getName(); 
        return "JFXDrawTools V1.2 Shufen Source Code" + name;
        }
    };
    stage.titleProperty().bind(fileNameB);
  }

  /**
   * Create menu bar
   */
  MenuBar createMenuBar(Stage stage) {
    MenuBar menuBar = new MenuBar();
    Menu menuFile = createMenuFile(stage);
    Menu menuTools = createMenuTools();
    Menu menuAction = createMenuAction();
    Menu menuPref = createMenuPreference();
    menuBar.getMenus().addAll(menuFile, menuTools, menuAction, menuPref);

    return menuBar;
  }

  /**
   *
   */
  Menu createMenuFile(final Stage stage) {
    Menu menuFile = new Menu("File");
    Menu loadSubmenu = createMenuLoad(stage);
    Menu saveFXMLMenu = createMenuSaveFXML(stage);
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(loadSubmenu, saveFXMLMenu, exit);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });
    return menuFile;
  }

  /**
   *
   */
  Menu createMenuLoad(final Stage stage) {
    Menu menuLoad = new Menu("Open");
    MenuItem loadFXML = new MenuItem("Open FXML...");
    MenuItem loadImage = new MenuItem("Open Image...");
    menuLoad.getItems().addAll(loadFXML, loadImage);

    // Create a file chooser for loadFXML menuItem
    final FileChooser fxmlFileChooser = new FileChooser();

    // Set "." as default dir
    fxmlFileChooser.setInitialDirectory(new File("."));

    fxmlFileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("FXML", "*.fxml"),
        new FileChooser.ExtensionFilter("All Files", "*.*"));

    // Add action for loadFXML menu item
    loadFXML.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        fxmlFileChooser.setTitle("Open FXML File");
        // Set last dir as default dir
        if (curFXMLFile.get() != null) {
          File lastDir = curFXMLFile.get().getParentFile();
          fxmlFileChooser.setInitialDirectory(lastDir);
        }
        File file = fxmlFileChooser.showOpenDialog(stage);
        if (file != null) {
          ObservableList<Node> list = 
            drawLoader.loadFXML(file, drawPane);
          curFXMLFile.set(file); 
        }
      }
    });

    // Create a file chooser for loadImage menuItem
    final FileChooser imageFileChooser = new FileChooser();

    // Set "." as default dir
    imageFileChooser.setInitialDirectory(new File("."));

    imageFileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("All Images",
        "*.bmp", "*.gif", "*.jpeg", "*.jpg", "*.png"),
        new FileChooser.ExtensionFilter("All Files", "*.*"),
        new FileChooser.ExtensionFilter("BMP", "*.bmp"),
        new FileChooser.ExtensionFilter("GIF", "*.gif"),
        new FileChooser.ExtensionFilter("JPEG", "*.jpeg"),
        new FileChooser.ExtensionFilter("JPG", "*.jpg"),
        new FileChooser.ExtensionFilter("PNG", "*.png"));

    // Add action for loadImage menu item
    loadImage.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        imageFileChooser.setTitle("Open Image File");
        // Set last dir as default dir
        if (curImageFile.get() != null) {
          File lastDir = curImageFile.get().getParentFile();
          imageFileChooser.setInitialDirectory(lastDir);
        }
        File file = imageFileChooser.showOpenDialog(stage);
        if (file != null) {
          ImageView iv = drawLoader.loadImage(file,
            Double.MAX_VALUE, Double.MAX_VALUE);
          drawPane.getChildren().add(iv);
          curImageFile.set(file); 
        }
      }
    });

    return menuLoad;
  }

  /**
   *
   */
  Menu createMenuSaveFXML(final Stage stage) {
    Menu menuSave = new Menu("Save FXML");
    MenuItem saveAll = new MenuItem("Save All");
    saveAll.setAccelerator(
      new KeyCharacterCombination("S", KeyCombination.CONTROL_DOWN));
    MenuItem saveAllAs = new MenuItem("Save All As...");

    menuSave.getItems().addAll(saveAll, saveAllAs);

    // Create a file chooser for saveAllAs
    final FileChooser fileChooser = new FileChooser();

    // Set "." as default dir
    fileChooser.setInitialDirectory(new File("."));

    fileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("FXML", "*.fxml"),
        new FileChooser.ExtensionFilter("All Files", "*.*"));

    // Add action for saveAll menu item
    // Save to last opened file if there is one
    // If this is the first time do Save action, no file name yet,
    // use default name
    saveAll.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Get file from curFXMLFile property
        File file = curFXMLFile.get(); // get latest open file
        if (file == null) {          
          // This is first time do "Save All", no file name yet
          // using default dir and name          
          File dir = fileChooser.getInitialDirectory();
          // instead of open FileChooser dialog, use default name
          String name = "JFXDrawTools";
          file = new File(dir, name);

        }
        file = getPrefFileExtension(file, "fxml");
        curFXMLFile.set(file);
        // Clean unfinished drawing is necessary
        // before an action is taken
        cleanUnfinished();
        drawWriter.writeFXML(drawPane, file);
      }
    }); 

    // Add action for saveAllAs menu item
    // Open FileChooser to select a file
    saveAllAs.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        fileChooser.setTitle("Save All As FXML File");
        // Set last dir as default dir
        if (curFXMLFile.get() != null) {
          File lastDir = curFXMLFile.get().getParentFile();
          fileChooser.setInitialDirectory(lastDir);
        }
        File file = fileChooser.showSaveDialog(stage);
        if (file != null) {
          file = getPrefFileExtension(file, "fxml");
          curFXMLFile.set(file);
          // Clean unfinished drawing is necessary
          // before an action is taken
          cleanUnfinished();
          drawWriter.writeFXML(drawPane, file);
        }
      }
    }); 

    return menuSave;
  }

  /**
   * Check if the file ends with the given preferred extension, 
   * if not, return a new file with the given preferred extension
   * Note for future release: check if the new file name exists 
   * or not, and prompt warning message (Replace or Cancel)
   * if it exists
   *
   * @param f
   * @param ext
   * @return
   */
  File getPrefFileExtension(File f, String ext) {
    String s = f.getName();
    if (s.endsWith("." + ext)) {
      return f;
    }
    return new File(f.getPath() + "." + ext);
  }

  /**
   * Create menu tools
   */
  Menu createMenuTools() {
    // Create toggle group
    ToggleGroup groupTools = new ToggleGroup();

    // This event handler is for ActionEvent,
    // it is called from Accelerator of MenuItem
    EventHandler<ActionEvent> toolSelector =
        new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        RadioMenuItem mi = (RadioMenuItem)e.getSource();
        // When user hit the defined key combination,
        // ActionEvent is triggered,
        // we must explicitly setSelected to true
        mi.setSelected(true);
      }
    };

    // Create radio menu items
    RadioMenuItem drawLine = new RadioMenuItem("Line Drawer");
    drawLine.setId(DrawTools.LINE_DRAWER.name());
    drawLine.setAccelerator(
        new KeyCharacterCombination("L", KeyCombination.CONTROL_DOWN));
    drawLine.setOnAction(toolSelector);
    drawLine.setToggleGroup(groupTools);

    RadioMenuItem drawPolyline = new RadioMenuItem("Polyline Drawer");
    drawPolyline.setId(DrawTools.POLYLINE_DRAWER.name());
    drawPolyline.setAccelerator(
        new KeyCharacterCombination("P", KeyCombination.CONTROL_DOWN));
    drawPolyline.setOnAction(toolSelector);
    drawPolyline.setToggleGroup(groupTools);

    RadioMenuItem drawPolygon = new RadioMenuItem("Polygon Drawer");
    drawPolygon.setId(DrawTools.POLYGON_DRAWER.name());
    drawPolygon.setAccelerator(
        new KeyCharacterCombination("G", KeyCombination.CONTROL_DOWN));
    drawPolygon.setOnAction(toolSelector);
    drawPolygon.setToggleGroup(groupTools);

    RadioMenuItem drawPath = new RadioMenuItem("Path Drawer");
    drawPath.setId(DrawTools.PATH_DRAWER.name());
    drawPath.setAccelerator(
        new KeyCharacterCombination("T", KeyCombination.CONTROL_DOWN));
    drawPath.setOnAction(toolSelector);
    drawPath.setToggleGroup(groupTools);

    RadioMenuItem drawBezierCurve = new RadioMenuItem("Bezier Curve Drawer");
    drawBezierCurve.setId(DrawTools.BEZIER_CURVE_DRAWER.name());
    drawBezierCurve.setAccelerator(
        new KeyCharacterCombination("B", KeyCombination.CONTROL_DOWN));
    drawBezierCurve.setOnAction(toolSelector);
    drawBezierCurve.setToggleGroup(groupTools);

    RadioMenuItem drawRectangle = new RadioMenuItem("Rectangle Drawer");
    drawRectangle.setId(DrawTools.RECTANGLE_DRAWER.name());
    drawRectangle.setAccelerator(
        new KeyCharacterCombination("R", KeyCombination.CONTROL_DOWN));
    drawRectangle.setOnAction(toolSelector);
    drawRectangle.setToggleGroup(groupTools);

    RadioMenuItem drawCircle = new RadioMenuItem("Circle Drawer");
    drawCircle.setId(DrawTools.CIRCLE_DRAWER.name());
    drawCircle.setAccelerator(
        new KeyCharacterCombination("C", KeyCombination.CONTROL_DOWN));
    drawCircle.setOnAction(toolSelector);
    drawCircle.setToggleGroup(groupTools);

    RadioMenuItem drawEllipse = new RadioMenuItem("Ellipse Drawer");
    drawEllipse.setId(DrawTools.ELLIPSE_DRAWER.name());
    drawEllipse.setAccelerator(
        new KeyCharacterCombination("E", KeyCombination.CONTROL_DOWN));
    drawEllipse.setOnAction(toolSelector);
    drawEllipse.setToggleGroup(groupTools);

    RadioMenuItem drawRegularPolygon = new RadioMenuItem("Regular Polygon Drawer");
    drawRegularPolygon.setId(DrawTools.REGULAR_POLYGON_DRAWER.name());
    drawRegularPolygon.setAccelerator(
        new KeyCharacterCombination("U", KeyCombination.CONTROL_DOWN));
    drawRegularPolygon.setOnAction(toolSelector);
    drawRegularPolygon.setToggleGroup(groupTools);

    RadioMenuItem moveShape = new RadioMenuItem("Shape Mover");
    moveShape.setId(DrawTools.SHAPE_MOVER.name());
    moveShape.setAccelerator(
        new KeyCharacterCombination("M", KeyCombination.CONTROL_DOWN));
    moveShape.setOnAction(toolSelector);
    moveShape.setToggleGroup(groupTools);

    // Add listener for toggle group   
    groupTools.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      @Override
      public void changed(ObservableValue<? extends Toggle> ov,
                      Toggle oldVal, Toggle newVal) {
        if (newVal != null) {
          RadioMenuItem mi = (RadioMenuItem) newVal;
          drawTools.set(Enum.valueOf(DrawTools.class, mi.getId()));
        }
      }
    });   

    // Create Tools menu
    Menu menuTools = new Menu("Tools");
    menuTools.getItems().addAll(
        drawLine, drawPolyline, drawPolygon, drawPath, drawBezierCurve,
        drawRectangle, drawCircle, drawEllipse,	drawRegularPolygon,
        moveShape);

    return menuTools;
  }

  /**
   *
   */
  Menu createMenuAction() {
    Menu menu = new Menu("Action");
    MenuItem clearAll = new MenuItem("Clear All");
    menu.getItems().addAll(clearAll);

    // Add action for "Clear All" menu item
    clearAll.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        drawPane.getChildren().clear();
        // must also clear contents of properties map
        // if it is not empty
        Map<Object, Object> map = drawPane.getProperties();
        if (map.size() != 0) {
          map.clear();
        }

        cleanUnfinished();
      }
    });

    return menu;
  }

  /**
   *
   */
  Menu createMenuPreference() {
    Menu menuPref = new Menu("Preference");

    // Create nSides menu
    Menu menuNSides = createMenuNSides();    
    // explicitly set the first item (3 sides) as selected menu item
    ((RadioMenuItem)menuNSides.getItems().get(0)).setSelected(true);

    // Disable menuNSides menu if RegularPolygonDrawer is not activated
    BooleanBinding bB = new BooleanBinding() {
      {
        super.bind(drawTools);
      }

      @Override
      protected boolean computeValue() {
        return drawTools.get() != DrawTools.REGULAR_POLYGON_DRAWER;
      }
    };

    menuNSides.disableProperty().bind(bB);

    menuPref.getItems().addAll(menuNSides);
    return menuPref;
  }

  /**
   *  Create N-Sided Polygon submenu for Preference menu
   */
  Menu createMenuNSides() {
    // text for each radio menu items
    String[] titles = new String[] {
     "3 sides(Triangle)", "4 sides(Square)", "5 sides(Pentagon)",
     "6 sides(Hexagon)", "7 sides(Heptagon)", "8 sides(Octagon)",
     "9 sides(Nonagon)", "10 sides(Decagon)", "11 sides(Hendecagon)",
     "12 sides(Dodecagon)", "13 sides", "14 sides", "15 sides",
     "16 sides", "17 sides", "18 sides", "19 sides"
    };

    EventHandler<ActionEvent> nSidesSelector = new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        RadioMenuItem mi = (RadioMenuItem)e.getSource();
        // When user hit the defined key combination,
        // ActionEvent is triggered, we must explicitly set selected to true
        mi.setSelected(true);
      }
    };

    // Create a toggle group for radio menu items
    ToggleGroup toggleGroup = new ToggleGroup();
    Menu menuNSides = new Menu("N-Sided Polygon");
    for (int i = 0; i < titles.length; i++) {
      RadioMenuItem mi =  new RadioMenuItem(titles[i]);
      mi.setToggleGroup(toggleGroup);
      int n = i + 3; // start from 3 sides polygon
      mi.setId(String.valueOf(n));
      String keyChar = n < 10 ? String.valueOf(n) : String.valueOf(n - 10);
      if (n < 13) {
        // For 3-sides to 9-sides, press Ctrl-3, Ctrl-4, ..., Ctrl-9
        // For 10-sides to 12-sides, press Ctrl-0, Ctrl-1, Ctrl-2
        mi.setAccelerator(
          new KeyCharacterCombination(keyChar, KeyCombination.CONTROL_DOWN));
      } else {
        // For n >= 13, press Ctrl-Shift-3, Ctrl-Shift-4, ...
        mi.setAccelerator(
          new KeyCharacterCombination(keyChar, KeyCombination.CONTROL_DOWN,
            KeyCombination.SHIFT_DOWN));
      }
      mi.setOnAction(nSidesSelector);
      menuNSides.getItems().add(mi);
    }

    // Add listener for toggle group
    // set preference for drawing of regular polygons as number of sides is selected   
    toggleGroup.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      @Override
      public void changed(ObservableValue<? extends Toggle> ov,
                      Toggle oldVal, Toggle newVal) {
        if (newVal != null) {
          RadioMenuItem mi = (RadioMenuItem) newVal;
          RegularPolygon model = (RegularPolygon)regularPolygonDrawer.getPrefModel();
          model.setNumberOfSides(Integer.parseInt(mi.getId()));
          // Set fill color, using hsb to set different color each selection
          // Change value of hue (0 to 360), increment 20 each time
          // saturation and brightness both using 1.0
          hueForFill = (hueForFill + 20) % 360;
          model.setFill(Color.hsb(hueForFill, 1.0, 1.0));
        }
      }
    });   

    return menuNSides;
  }

  /**
   * Create status bar
   */
  VBox createStatusBar() {
    VBox statusBar = new VBox();
    Text statusText = new Text();
    Text statusText2 = new Text();
    // binding text and footer
    statusText.textProperty().bind(footer);
    statusText2.textProperty().bind(footer2);
    statusBar.getChildren().addAll(statusText, statusText2);

    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(" +
        "from 0% 0% to 100% 100%, #7080A7 55%, #F0FFFF);" + 
        "-fx-border-color: #e6e6d3;");

    statusText.setFont(Font.font("Courier New", FontWeight.BOLD, 12));
    statusText.setFill(Color.web("#F0FFFF"));
    statusText2.setFont(Font.font("Courier New", FontWeight.BOLD, 12));
    statusText2.setFill(Color.web("#F0FFFF"));

    return statusBar;
  }

  /**
   * This method is called whenever some action is taken
   *  such as: Clear All, Save FXML
   */
  void cleanUnfinished() {
    ShapeDrawer tool = drawPane.getDrawer();
    if (tool != null && tool.getShape() != null) {
      if (drawPane.isDragged()) {
        tool.onMouseDragFinished(drawPane);
      }
      tool.clean(drawPane);
      tool.setShape(null);  // complete this shape
    }
  }

  /**
   * Activate a drawer of a draw pane,
   * this method is called from changed method of
   * listener registered for selectedToggle property
   */
  void activateDrawer(DrawTools value) {
    switch (value) {
      case LINE_DRAWER:
        drawPane.setDrawer(lineDrawer);
        footer2.bind(lineTip);
        break;
      case POLYLINE_DRAWER:
        drawPane.setDrawer(polylineDrawer);
        footer2.unbind();
        footer2.set("");
        break;
      case POLYGON_DRAWER:
        drawPane.setDrawer(polygonDrawer);
        footer2.unbind();
        footer2.set("");
        break;
      case PATH_DRAWER:
        drawPane.setDrawer(pathDrawer);
        footer2.unbind();
        footer2.set("");
        break;
      case BEZIER_CURVE_DRAWER:
        drawPane.setDrawer(bezierCurveDrawer);
        footer2.unbind();
        footer2.set("");
        break;
      case RECTANGLE_DRAWER:
        drawPane.setDrawer(rectangleDrawer);
        footer2.bind(rectangleTip);
        break;
      case CIRCLE_DRAWER:
        drawPane.setDrawer(circleDrawer);
        footer2.bind(circleTip);
        break;
      case ELLIPSE_DRAWER:
        drawPane.setDrawer(ellipseDrawer);
        footer2.bind(ellipseTip);
        break;
      case REGULAR_POLYGON_DRAWER:
        drawPane.setDrawer(regularPolygonDrawer);
        footer2.bind(regularPolygonTip);
        break;
      case SHAPE_MOVER:
        drawPane.setDrawer(shapeMover);
        footer2.bind(shapeMoverTip);
        break;
      default:
    }
  }

  /**
   * Display help tips for drawing
   * Resulting text looks like this, for ellipse drawer in action:
   * "mouse at (86, 94), startX=58, startY=67, Ellipse Drawer activated"
   */
  void bindFooterForMouseMove() {
    StringBinding sB = new StringBinding() {
      {
        super.bind(drawPane.eventXProperty(),
                   drawPane.eventYProperty(),
                   drawPane.startXProperty(),
                   drawPane.startYProperty(),
                   drawTools);
      }

      @Override
      protected String computeValue() {
      return String.format(
        "Mouse at (%.0f,%.0f),startX=%.0f,startY=%.0f. %s activated.",
        drawPane.getEventX(), drawPane.getEventY(),
        drawPane.getStartX(), drawPane.getStartY(),
        drawTools.get());
      }
    };

    footer.bind(sB);
  }

  /**
   * Create a StringBinding for Line
   */
  StringBinding createLineTip() {

    final Line model = (Line)lineDrawer.getPrefModel();
    StringBinding sB = new StringBinding() {
      {
        super.bind(model.startXProperty(),
                   model.startYProperty(),
                   model.endXProperty(),
                   model.endYProperty());
      }

      @Override
      protected String computeValue() {
      return String.format(
        "startX=%.0f,startY=%.0f,endX=%.0f,endY=%.0f",
        model.getStartX(), model.getStartY(),
        model.getEndX(), model.getEndY());
      }
    };

    return sB;
  }

  /**
   * Create a StringBinding for Rectangle
   */
  StringBinding createRectangleTip() {

    final Rectangle model = (Rectangle)rectangleDrawer.getPrefModel();
    StringBinding sB = new StringBinding() {
      {
        super.bind(model.xProperty(),
                   model.yProperty(),
                   model.widthProperty(),
                   model.heightProperty());
      }

      @Override
      protected String computeValue() {
      return String.format(
        "x=%.0f,y=%.0f,width=%.0f,height=%.0f",
        model.getX(), model.getY(),
        model.getWidth(), model.getHeight());
      }
    };

    return sB;
  }

  /**
   * Create a StringBinding for Circle
   */
  StringBinding createCircleTip() {

    final Circle model = (Circle)circleDrawer.getPrefModel();
    StringBinding sB = new StringBinding() {
      {
        super.bind(model.centerXProperty(),
                   model.centerYProperty(),
                   model.radiusProperty());
      }

      @Override
      protected String computeValue() {
      return String.format(
        "centerX=%.0f,centerY=%.0f,radius=%.0f",
        model.getCenterX(), model.getCenterY(),
        model.getRadius());
      }
    };

    return sB;
  }

  /**
   * Create a StringBinding for Ellipse
   */
  StringBinding createEllipseTip() {

    final Ellipse model = (Ellipse)ellipseDrawer.getPrefModel();
    StringBinding sB = new StringBinding() {
      {
        super.bind(model.centerXProperty(),
                   model.centerYProperty(),
                   model.radiusXProperty(),
                   model.radiusYProperty());
      }

      @Override
      protected String computeValue() {
      return String.format(
        "centerX=%.0f,centerY=%.0f,radiusX=%.0f,radiusY=%.0f",
        model.getCenterX(), model.getCenterY(),
        model.getRadiusX(), model.getRadiusY());
      }
    };

    return sB;
  }

  /**
   * Create a StringBinding for RegularPolygon
   */
  StringBinding createRegularPolygonTip() {

    final RegularPolygon model = (RegularPolygon)regularPolygonDrawer.getPrefModel();
    StringBinding sB = new StringBinding() {
      {
        super.bind(model.centerXProperty(),
                   model.centerYProperty(),
                   model.circumradiusProperty());
      }

      @Override
      protected String computeValue() {
      return String.format(
        "centerX=%.0f,centerY=%.0f,circumradius=%.0f",
        model.getCenterX(), model.getCenterY(),
        model.getCircumradius());
      }
    };

    return sB;
  }

  /**
   * Create a StringBinding for ShapeMover
   */
  StringBinding createShapeMoverTip() {

    StringBinding sB = new StringBinding() {
      {
        super.bind(drawPane.dragXProperty(),
                   drawPane.dragYProperty());
      }

      @Override
      protected String computeValue() {
      return String.format(
        "dragX=%.0f,dragY=%.0f",
        drawPane.getDragX(), drawPane.getDragY());
      }
    };

    return sB;
  }

  public static void main(String[] args) {
    launch(args);
  }

}
```

We set an image, /resource/MyLogoIcon_1_2.png, as the minimized icon of application's window. The icon is also a part of window decorations. Here's a snippet of code from above listing:

Listing 3-10. Set minimized icon of application's window:

```
 String iconName = "/resource/MyLogoIcon_1_2.png";
    Image iconImage = new Image(getClass().getResourceAsStream(
        iconName));
    stage.getIcons().add(iconImage);
```

Here's the image:

Figure 3-8. The Image used as minimized icon of application's window.

![](images/00036.jpeg "MyLogoIcon_1_2.png")

If you are a developer interested in compiling this program successfully, you can either replace the icon image with the one you prefer, or extract the image file, MyLogoIcon_1_2.png, from HTML files of this e-Book to a directory named `resource`. The `resource` directory should be inside the directory where you put the `drawtool` package.

Here's a suggestion regarding converting `.mobi` format of an e-Book to HTML:

1.  Install `Calibre`, a free and open source E book Management software, to your PC.
2.  Use `Add books` function in `Calibre` to add the `.mobi` file of this e-Book to `Calibre` Library.
3.  Use `Convert books` function in `Calibre`, select `HTMLZ` as output format, click `OK` button to proceed to the conversion.
4.  When the conversion completes, you'll get an output file with extension `.htmlz`. Rename the extension to be `.zip` and unzip the file, you'll get one large HTML file with a directory named `images` containing all image files that are linked within contents of the HTML file.

    If you are using Windows 8, the `.htmlz` output file is stored in a sub directory of this directory:

    ```
    C:\Users\<User Name>\Documents\Calibre Library
    ```

Followings are snapshots of `JFXDrawTools V1.2` application which draws shapes on top of an image, and then save them to an FXML file, [MySketch.fxml](#part0009_split_008.html_my-sketch-fxml), in directory:
`JFXDrawTools1.2/src/example1/myfxml/`

Figure 3-9. Load an image as background, draw some shapes, and save all to an FXML file named MySketch.fxml, using `JFXDrawTools V1.2` application.

![](images/00037.jpeg "my_sketch.jpg")

Figure 3-10. Open an FXML file MySketch.fxml previously saved, and continue editing, using `JFXDrawTools V1.2` application.

![](images/00038.jpeg "my_sketch_house.jpg")

Here are the contents of FXML file, MySketch.fxml, saved for Figure 3-10.

Listing 3-11. Contents of MySketch.fxml file saved for Figure 3-10:

```
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<?import java.lang.*?>
<?import java.util.*?>
<?import javafx.animation.*?>
<?import javafx.animation.PathTransition.*?>
<?import javafx.scene.control.*?>
<?import javafx.scene.Group?>
<?import javafx.scene.image.*?>
<?import javafx.scene.layout.*?>
<?import javafx.scene.paint.*?>
<?import javafx.scene.shape.*?>
<?import javafx.scene.text.*?>
<?import javafx.scene.transform.*?>
<?import javafx.util.*?>
<Pane xmlns:fx="http://javafx.com/fxml">
  <children>
    <ImageView fx:id="ImageView_1133fd6" preserveRatio="true">
      <image>
        <Image preserveRatio="false" smooth="false" 
        url="file:/F:/My%20Documents/DocRoot/SHUFEN_JAVA/MyBook/JFXDrawTools1.2/src/example1/myfxml/TeaTree.jpg"/>
      </image>
      <properties imageURL="file:/F:/My%20Documents/DocRoot/SHUFEN_JAVA/MyBook/JFXDrawTools1.2/src/example1/myfxml/TeaTree.jpg"/>
    </ImageView>
    <Rectangle fill="#FFE4E1" fx:id="Rectangle_313714" height="41.0"
      stroke="#FFB6C1" width="8.0" x="185.0" y="72.0"/>
    <Polygon fill="#FF5500" fx:id="RegularPolygon_1363e54"
      stroke="#5B5B5B" translateX="15.0" translateY="45.0">
      <points>
        <Double fx:value="152.0"/>
        <Double fx:value="15.325758358215502"/>
        <Double fx:value="120.2391750736855"/>
        <Double fx:value="70.33712082089224"/>
        <Double fx:value="183.76082492631448"/>
        <Double fx:value="70.33712082089227"/>
      </points>
    </Polygon>
    <Rectangle fill="#FFE4E1" fx:id="Rectangle_767bef" height="80.0"
      stroke="#FFB6C1" translateY="2.0" width="62.0" x="136.0" y="114.0"/>
    <Circle centerX="167.0" centerY="98.0" fill="#FFD700" fx:id="Circle_1d5b1dc"
      radius="10.0" stroke="#FF7F50"/>
    <Polygon fill="#FFAA00" fx:id="RegularPolygon_156d418" stroke="#5B5B5B">
      <points>
        <Double fx:value="167.0"/>
        <Double fx:value="93.0"/>
        <Double fx:value="162.0"/>
        <Double fx:value="98.0"/>
        <Double fx:value="167.0"/>
        <Double fx:value="103.0"/>
        <Double fx:value="172.0"/>
        <Double fx:value="98.0"/>
      </points>
    </Polygon>
    <Ellipse centerX="167.0" centerY="172.0" fill="#ADFF2F" fx:id="Ellipse_20a02d"
      radiusX="19.0" radiusY="23.0" stroke="#006400"/>
    <Polygon fill="#FFFF00" fx:id="RegularPolygon_19e6baa" stroke="#5B5B5B">
      <points>
        <Double fx:value="167.0"/>
        <Double fx:value="155.0"/>
        <Double fx:value="151.78309573927754"/>
        <Double fx:value="166.05572809000083"/>
        <Double fx:value="157.59543596332043"/>
        <Double fx:value="183.94427190999915"/>
        <Double fx:value="176.40456403667957"/>
        <Double fx:value="183.94427190999917"/>
        <Double fx:value="182.21690426072246"/>
        <Double fx:value="166.05572809000085"/>
      </points>
    </Polygon>
    <Polygon fill="#AAFF00" fx:id="RegularPolygon_193dfb0" stroke="#5B5B5B">
      <points>
        <Double fx:value="167.0"/>
        <Double fx:value="96.0"/>
        <Double fx:value="165.26794919243113"/>
        <Double fx:value="97.0"/>
        <Double fx:value="165.26794919243113"/>
        <Double fx:value="99.0"/>
        <Double fx:value="167.0"/>
        <Double fx:value="100.0"/>
        <Double fx:value="168.73205080756887"/>
        <Double fx:value="99.0"/>
        <Double fx:value="168.73205080756887"/>
        <Double fx:value="97.0"/>
      </points>
    </Polygon>
    <Polygon fill="#00FF00" fx:id="RegularPolygon_7daf5b" stroke="#5B5B5B">
      <points>
        <Double fx:value="153.0"/>
        <Double fx:value="124.0"/>
        <Double fx:value="149.53589838486224"/>
        <Double fx:value="126.0"/>
        <Double fx:value="149.53589838486224"/>
        <Double fx:value="130.0"/>
        <Double fx:value="153.0"/>
        <Double fx:value="132.0"/>
        <Double fx:value="156.46410161513776"/>
        <Double fx:value="130.0"/>
        <Double fx:value="156.46410161513776"/>
        <Double fx:value="126.0"/>
      </points>
    </Polygon>
    <Polygon fill="#00FF00" fx:id="RegularPolygon_1528259" stroke="#5B5B5B" translateX="-2.0">
      <points>
        <Double fx:value="183.0"/>
        <Double fx:value="124.0"/>
        <Double fx:value="179.53589838486224"/>
        <Double fx:value="126.0"/>
        <Double fx:value="179.53589838486224"/>
        <Double fx:value="130.0"/>
        <Double fx:value="183.0"/>
        <Double fx:value="132.0"/>
        <Double fx:value="186.46410161513776"/>
        <Double fx:value="130.0"/>
        <Double fx:value="186.46410161513776"/>
        <Double fx:value="126.0"/>
      </points>
    </Polygon>
    <Polygon fill="#00FFAA" fx:id="RegularPolygon_571e96" stroke="#5B5B5B" translateY="-3.0">
      <points>
        <Double fx:value="167.0"/>
        <Double fx:value="129.0"/>
        <Double fx:value="158.0"/>
        <Double fx:value="138.0"/>
        <Double fx:value="167.0"/>
        <Double fx:value="147.0"/>
        <Double fx:value="176.0"/>
        <Double fx:value="138.0"/>
      </points>
    </Polygon>
    <ImageView fx:id="ImageView_30911c" preserveRatio="true" translateX="176.0" translateY="51.0">
      <image>
        <Image preserveRatio="false" smooth="false" 
        url="file:/F:/My%20Documents/DocRoot/SHUFEN_JAVA/MyBook/JFXDrawTools1.2/src/example1/myfxml/MyLogoIcon_1_2.png"/>
      </image>
      <properties imageURL="file:/F:/My%20Documents/DocRoot/SHUFEN_JAVA/MyBook/JFXDrawTools1.2/src/example1/myfxml/MyLogoIcon_1_2.png"/>
    </ImageView>
  </children>
</Pane>
```

Compile and run the application. Try these steps to test it:

1.  Click on `Tools` menu, select menu items one by one, do MOUSE_PRESSED-MOUSE_DRAGGED-MOUSE_RELEASED events on the drawing board to draw different type of shapes.
2.  Click on `File` menu item, then click on `Save FXML` submenu, and select "Save All" menu item to save sketch rendered on the drawing board to a default file called "JFXDrawTools.fxml".
3.  Click on `File` menu item, then click on `Save FXML` submenu, and select "Save All As..." menu item to save sketch rendered on the drawing board to a preferred file name selected from `FileChooser`.
4.  Re-start `JFXDrawTools V1.2` application from another command window.
5.  Click on `File` menu item, then click on `Open` submenu, and select "Open Image..." menu item to load an image file.
6.  Click on `File` menu item, then click on `Open` submenu, and select "Open FXML..." menu item to load nodes from the FXML file saved previously.
7.  Draw some more nodes using any draw tool, such as CIRCLE DRAWER, BEZIER CRUVE DRAWER, etc., then save all to another FXML file.
8.  Click on `Action` menu item, and select "Clear All" menu item to clear all nodes on the drawing board, then load the FXML file saved previously back to the drawing board.

Output from Compiling and Running `JFXDrawTools` Program of example1 in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeFour\DrawTool1.4\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked drawtool\io\*.java

javac -encoding utf-8 -Xlint:unchecked drawtool\shape\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool resource

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeFour\JFXDrawTools1.2\src\example1>
copy /Y "..\..\..\DrawTool1.4\src\example1\drawtool.jar"  .

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar jfxdrawtools\*.java

jar cf jfxdrawtools.jar jfxdrawtools

java -cp drawtool.jar;jfxdrawtools.jar jfxdrawtools.JFXDrawTools
```

## 3.9 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `MenuBar`, `Menu`, and `MenuItem` are among fundamental JavaFX UI components, resided in `javafx.scene.control` package, for designing compact look-and-feel graphical user interfaces using less space.
    (See sections: [Add `File` Menu to Menu Bar](#part0009_split_001.html_add-file-menu), [Add `Save FXML` Submenu to `File` Menu](#part0009_split_003.html_add-save-fxml-sub-menu), [Add `Open` Submenu to `File` Menu](#part0009_split_005.html_add-open-sub-menu), [Add `Action` Menu to Menu Bar](#part0009_split_007.html_add-action-menu))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See [here](#part0009_split_001.html_create-file-menu-codes), [here](#part0009_split_003.html_save-all-set-on-action-codes), [here](#part0009_split_005.html_load-fxml-set-on-action-codes), and [here](#part0009_split_007.html_create-menu-action-codes))
*   `void setOnAction(EventHandler<ActionEvent> value)` method, provided in `MenuItem` class, registers an `EventHandler` to be notified when `ActionEvent` occurs.
    (See [here](#part0009_split_001.html_create-file-menu-codes), [here](#part0009_split_003.html_save-all-set-on-action-codes), [here](#part0009_split_005.html_load-fxml-set-on-action-codes), and [here](#part0009_split_007.html_create-menu-action-codes))
*   `accelerator` property, defined in `MenuItem` class, specifies a `KeyCombination` to trigger an `ActionEvent` of a `MenuItem`.
    (See [here](#part0009_split_003.html_create-menu-save-fxml-codes))
*   `KeyCombination`, an abstract class resides in `javafx.scene.input` package, defines static fields of type `KeyCombination.Modifier`, such as CONTROL_DOWN, META_DOWN, SHIFT_DOWN, etc. which are useful in construction of `KeyCharacterCombination` instances.
    (See [here](#part0009_split_003.html_create-menu-save-fxml-codes))
*   `KeyCharacterCombination`, resides in `javafx.scene.input` package, a direct subclass of `javafx.scene.input.KeyCombination` for creating shortcuts to trigger an `ActionEvent`.
    (See [here](#part0009_split_003.html_create-menu-save-fxml-codes))
*   `FileChooser` class extends `java.lang.Object` and resides in `javafx.stage` package; it provides convenient methods to open/save files:

    `public java.io.File showOpenDialog(Window` ownerWindow`)` method

    Show a file open dialog for navigating the local file system to select a file to open.

    `public java.io.File showSaveDialog(Window` ownerWindow`)` method

    Show a file save dialog for navigating the local file system to select a file to save.

    `public ObservableList<FileChooser.ExtensionFilter> getExtensionFilters()`

    Get a list of `ExtensionFilter` for this `FileChooser`, and allow users to add preferred filters for file extensions, such as "*.fxml", "*.jpg", etc.

    (See sections: [Add `Save FXML` Submenu to `File` Menu](#part0009_split_003.html_add-save-fxml-sub-menu), [Add `Open` Submenu to `File` Menu](#part0009_split_005.html_add-open-sub-menu))
*   `FileChooser.ExtensionFilter` class, defined in `javafx.stage.FileChooser` class, specifies filters of file extensions for file dialogs of `FileChooser`.
    (See [here](#part0009_split_003.html_create-menu-save-fxml-codes), and [here](#part0009_split_005.html_create-menu-load-codes))
*   Classes from `javafx.beans.property` package:

    `ObjectProperty<T>`

    An abstract class, which is derived from `javafx.beans.binding.ObjectExpression<T>` class, implements `Property<T>` and `WritableObjectValue<T>`.

    `SimpleObjectProperty<T>`

    A class derived from `ObjectProperty<T>` class.

    (See sections: [Add `Save FXML` Submenu to `File` Menu](#part0009_split_003.html_add-save-fxml-sub-menu), [Bind Stage Title for Displaying FXML File Name](#part0009_split_006.html_bind-stage-title))
*   `Property<T>` interface resides in `javafx.beans.property` package, and defines methods common to all properties such as:

    `void bind(ObservableValue<? extends T>` observable`)`

    Bind this property unidirectional to the given `ObservableValue`.

    `void unbind()`

    Unbind for this property.

    (See section [Bind Stage Title for Displaying FXML File Name](#part0009_split_006.html_bind-stage-title))
*   `StringBinding`, an abstract class that extends `StringExpression` class, resides in `javafx.beans.binding` package. The abstract method, `String computeValue()`, need be implemented in order to create an instance of `StringBinding`.
    (See section [Bind Stage Title for Displaying FXML File Name](#part0009_split_006.html_bind-stage-title))

#   EPILOGUE

The authors are working on the rest of volumes of this book series, and additional favorable tools for JavaFX developers are to be released one by one soon. Let's have a sneak peek of coming features besides others revealed in the PREFACE section:

*   Color palette tools
*   Image editing tools
*   More interactive sketching tools: Free Hand Drawer, Rubber Band Drawer, Text Writer, Color Gradienter, Arc Drawer, Cursor Key Mover, etc.
*   Path transition animater
*   Dynamic context menu controller
*   Convenient shapes library
*   And more...

Wish you a happy, healthy, and prosperous year of the Monkey.