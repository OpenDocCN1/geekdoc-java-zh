![](Images/cover00163.jpeg)

|  

&#124;  
### Offers Reusable Classes and Graphics Applications
Including Complete Source Codes

 &#124;

 |
|  

&#124;  
# Coding in JavaFX
Step by Step
Build Graphics Toolkit

 &#124;

 |
|  
### VOLUME Ⅰ
IMAGE VIEWER
in Java 8 (JDK 8u66)

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

*   [ABOUT THE AUTHORS](#part0003.xhtml)
*   [ACKNOWLEDGMENT](#part0004.xhtml)
*   [PREFACE](#part0005.xhtml)
    *   [How this book is organized](#part0005.xhtml_how-this-book-organize)
    *   [Why Choose This Book](#part0005.xhtml_why-choose-this-book)
    *   [What You Need for This Book](#part0005.xhtml_what-you-need)
*   [**INTRODUCTION**](#part0006.xhtml)
*   VOLUME Ⅰ: DEVELOPING IMAGE VIEWING COMPONENTS
    *   [**Chapter 1**: Basic Image Viewer](#part0007.xhtml)
        *   [1.1 Create `ImageViewer` Class as Subclass of `Application`](#part0007.xhtml_create-image-viewer)
            *   [1.1.1 JavaFX Application Thread vs. Java Launcher Thread](#part0007.xhtml_thread)
            *   [1.1.2 Catch Resize Event of Image Rendering Area](#part0007.xhtml_image-area-resize)
        *   [1.2 Create Menu Bar](#part0007.xhtml_add-menu-bar)
            *   [1.2.1 Add File Menu to Menu Bar](#part0007.xhtml_add-file-menu)
            *   [1.2.2 Select Image File from File Open Dialog and Display Image on `StackPane`](#part0007.xhtml_file-chooser)
        *   [1.3 Create Option Menu and View Submenu](#part0007.xhtml_add-option-menu)
            *   [1.3.1 Create Toggle Group, Radio Menu Items and Add Listener for `selectedToggle` Property](#part0007.xhtml_toggle-group)
        *   [1.4 Implement Fit Width, Fit Height and Original Size Viewing Options](#part0007.xhtml_view-option)
            *   [1.4.1 Approach One: Bind `ImageView`'s `fitWidth`/`fitHeight` Properties to `Scene`'s `width`/`height` Properties Respectively](#part0007.xhtml_bind-unbind)
                *   [1.4.1.1 Implement Fit Width Viewing Option](#part0007.xhtml_bind-fit-width)
                *   [1.4.1.2 Implement Fit Height Viewing Option](#part0007.xhtml_bind-fit-height)
                *   [1.4.1.3 Implement Original Size Viewing Option](#part0007.xhtml_bind-original-size)
                *   [1.4.1.4 Complete Source Codes of `ImageViewer` Class](#part0007.xhtml_complete-source-codes-1)
            *   [1.4.2 Approach Two: Change Values for `fitWidth` Property and `fitHeight` property](#part0007.xhtml_set-fit-w-h-value)
                *   [1.4.2.1 Catch Resize Event of Scene to Adjust Viewing Size of Image](#part0007.xhtml_scene-resize)
                *   [1.4.2.2 Complete Source Codes of `ImageViewer` Class](#part0007.xhtml_complete-source-codes-2)
        *   [1.5 Summary](#part0007.xhtml_summary)
    *   [**Chapter 2**: Enhanced Image Viewer with Browsing Buttons](#part0008.xhtml)
        *   [2.1 Add `Next` Button](#part0008.xhtml_add_next)
            *   [2.1.1 Use `Group` as Parent Container](#part0008.xhtml_group-as-container)
            *   [2.1.2 Use `Shape` Class for Rendering 2D Geometric Primitives](#part0008.xhtml_shape-class)
            *   [2.1.3 Use `Rectangle` Shape as Bounding Box of Custom-Made Button](#part0008.xhtml_rectangle-as-bounding-box)
            *   [2.1.4 Paint Background and Border of `Shape`](#part0008.xhtml_paint-shape)
            *   [2.1.5 Set Value of `arcHeight` and `arcWidth` Properties to Render Rounded Rectangle](#part0008.xhtml_arc-height-arc-width)
            *   [2.1.6 Use `Polygon` Shape as Visual Sign of `Next` Icon](#part0008.xhtml_polygon-as-icon)
            *   [2.1.7 Set Value of `Cursor` Property for `Node`](#part0008.xhtml_mouse-cursor)
            *   [2.1.8 Use Convenience Methods to Register Event Handlers to Handle Mouse Events](#part0008.xhtml_event-handler)
            *   [2.1.9 Complete Source Codes of `createNextButton()` Method](#part0008.xhtml_create-next-button-codes)
            *   [2.1.10 Install `Tooltip` for `Node`](#part0008.xhtml_tooltip)
        *   [2.2 Adjust `Next` Button's Default Position in `StackPane`](#part0008.xhtml_adjust_next)
        *   [2.3 Add `Previous` Button and Adjust Its Position in `StackPane`](#part0008.xhtml_add_previous)
        *   [2.4 Implement On Mouse Clicked Event Handlers](#part0008.xhtml_button_clicked)
            *   [2.4.1 Configure `FileChooser`](#part0008.xhtml_configure-file-chooser)
            *   [2.4.2 Create List Iterator to Iterate Existing Files in the Current Directory](#part0008.xhtml_file-iterator)
            *   [2.4.3 Define Properties in `ImageViewer` Class](#part0008.xhtml_properties)
        *   [2.5 Complete Source Codes of `Image Viewer V1.1`](#part0008.xhtml_complete-source-codes)
            *   [2.5.1 Complete Source Codes of `FileUtils` Class](#part0008.xhtml_complete-source-codes-file-utils)
            *   [2.5.2 Complete Source Codes of `ImageViewer` Class](#part0008.xhtml_complete-source-codes-image-viewer)
        *   [2.6 Summary](#part0008.xhtml_summary)
    *   [**Chapter 3**: Enhanced Image Viewer with Slide Show Capacity](#part0009.xhtml)
        *   [3.1 Add Status Bar at the Bottom of `BorderPane`](#part0009.xhtml_add-footer)
            *   [3.1.1 Create `HBox` Pane as Status Bar and `Text` Node to Show Image Name](#part0009.xhtml_create-hbox-text)
            *   [3.1.2 Set Value of `imageName` Property](#part0009.xhtml_set-value-image-name)
        *   [3.2 Improve Button's Reaction Aspect](#part0009.xhtml_improve-button)
            *   [3.2.1 Disable Button to Indicate No More Image to Open](#part0009.xhtml_disable-button)
            *   [3.2.2 Change Button Appearance When Mouse Is Pressed](#part0009.xhtml_pressed-button)
        *   [3.3 Add Slide Show Capabilities](#part0009.xhtml_add-slideshow)
            *   [3.3.1 Add `Start Slideshow` and `Stop Slideshow` Menu Items](#part0009.xhtml_add-slideshow-menu-item)
                *   [3.3.1.2 Bind Disable Property of Menu Item](#part0009.xhtml_slideshow-disable-bind)
            *   [3.3.2 Execute Slide Show on Another Thread](#part0009.xhtml_slideshow-thread)
                *   [3.3.2.1 Create `SlideshowService` Class that Extends `Service` Class](#part0009.xhtml_slideshow-service)
                *   [3.3.2.2 Configure Slide Show Service Object](#part0009.xhtml_configure-slideshow)
                *   [3.3.2.3 Implement Event Handlers of Action Events for `Start Slideshow` and `Stop Slideshow` Menu Items](#part0009.xhtml_slideshow-action)
            *   [3.3.3 The Complete `start(Stage` stage`)` Method of `ImageViewer` Application](#part0009.xhtml_complete-start)
            *   [3.3.4 Coordinate with Event Handlers of `Load` Menu Item and `Previous` Button](#part0009.xhtml_coordinate)
        *   [3.4 Add Fade Transition between Slides](#part0009.xhtml_fade-transition)
            *   [3.4.1 Complete Source Codes of `SlideshowService` Class](#part0009.xhtml_complete-slide-show-service)
        *   [3.5 Complete Source Codes of `Image Viewer V1.2`](#part0009.xhtml_complete-source-codes)
        *   [3.6 Summary](#part0009.xhtml_summary)
*   [EPILOGUE](#part0010.xhtml)

# ABOUT THE AUTHORS

### Shufen Kuo

Shufen Kuo relocated to San Francisco Bay Area in summer of 1988, and has been a software engineer ever since. She has extensive hands-on experience with various platforms, from PC DOS to numerous Unix/Linux workstations, and from PC Linux to PC Windows.

She started writing Java programs in 2001\. She has been using Abstract Windowing Toolkit (AWT) and Swing, the GUI Components of Java Foundation Classes (JFC), to develop GUIs for her Java projects for years. And since 2012, she has immersed herself in JavaFX; exploring its essence inspires her to write books publicizing the strength of JavaFX.

Before developing Java applications, she had more than 12 years experience in the development of C/C++ applications on UNIX/Linux/Solaris running X Window system.

Shufen Kuo got her M.S. in Computer Science from Washington State University in 1987.

Currently, she is developing Java applications with rich GUIs using JavaFX, as well as writing tutorials about coding in JavaFX, utilizing her expertise on designing and developing object oriented graphics tools.

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

This book is VOLUME Ⅰ of the book series, `Coding in JavaFX Step by Step Build Graphics Toolkit`. Since contents are abundant and unfeasible to be managed into one book, chapters are organized among volumes:

1.  VOLUME Ⅰ: DEVELOPING IMAGE VIEWING COMPONENTS
    *   **Chapter 1**: Basic Image Viewer
    *   **Chapter 2**: Enhanced Image Viewer with Browsing Buttons
    *   **Chapter 3**: Enhanced Image Viewer with Slide Show Capacity
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

3.  VOLUME Ⅲ: DEVELOPING INTERACTIVE REGULAR POLYGON DRAWING TOOLS
    *   **Chapter 1**: Enhanced Draw Tool with `Regular Polygon` Shape Capacity

        Introduce `RegularPolygon` class, derived from `Shape` class and resides in `drawtool.shape` package.

    *   **Chapter 2**: Enhanced Draw Tool with `Regular Polygon Drawer` Capacity

        Implement `RegularPolygonDrawer`, a direct subclass of `ShapeDrawer`, resides in `drawtool.drawer` package, to draw N-sided regular polygons from mouse events on a drawing board, featuring usages of `RegularPolygon` shape.

    *   **Chapter 3**: Enhanced `JFXDrawTools` with `Regular Polygon Drawer` Capacity

        Integrate N-sided regular polygon drawer into `JFXDrawTools` application.

4.  VOLUME Ⅳ: DEVELOPING SKETCH SAVING AND LOADING APIS
    *   **Chapter 1**: Enhanced Draw Tool with `Draw Writer` Capacity

        Introduce `DrawWriter` class, resides in `drawtool.io` package, to save sketches that are interactively drawn on a drawing board, a `Pane` object, to files in JavaFXML format. A sketch can be either a `Shape` object or an `ImageView` object. Besides JavaFXML format, it also provides API to save the image of an `ImageView` object to an image file.

    *   **Chapter 2**: Enhanced Draw Tool with `Draw Loader` Capacity

        Introduce `DrawLoader` class, which resides in `drawtool.io` package, to load FXML files as well as image files to a drawing board.

    *   **Chapter 3**: Enhanced `JFXDrawTools` with `Draw Writer` and `Draw Loader` Capacities

        Integrate sketch saving and loading capabilities into `JFXDrawTools` application.

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

### Reusable Classes with Applications and Complete Source Codes

Complete source codes of a set of packages with reusable classes as well as embeddable JavaFX applications are included in the book series.

The following tables list all the source codes offered in the prior four volumes of the book series:

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
| imageviewer | FileUtils.java ImageViewer.java
SlideshowService.java |
| jfxdrawtools | JFXDrawTools.java |

### Contents of VOLUME Ⅰ

Let's glance at the contents of VOLUME Ⅰ:

*   [**Chapter 1**](#part0007.xhtml): Basic Image Viewer
    *   [1.1 Create `ImageViewer` Class as Subclass of `Application`](#part0007.xhtml_create-image-viewer)
    *   [1.2 Create Menu Bar](#part0007.xhtml_add-menu-bar)
    *   [1.3 Create Option Menu and View Submenu](#part0007.xhtml_add-option-menu)
    *   [1.4 Implement Fit Width, Fit Height and Original Size Viewing Options](#part0007.xhtml_view-option)
    *   [1.5 Summary](#part0007.xhtml_summary)
*   [**Chapter 2**](#part0008.xhtml): Enhanced Image Viewer with Browsing Buttons
    *   [2.1 Add `Next` Button](#part0008.xhtml_add_next)
    *   [2.2 Adjust `Next` Button's Default Position in `StackPane`](#part0008.xhtml_adjust_next)
    *   [2.3 Add `Previous` Button and Adjust Its Position in `StackPane`](#part0008.xhtml_add_previous)
    *   [2.4 Implement On Mouse Clicked Event Handlers](#part0008.xhtml_button_clicked)
    *   [2.5 Complete Source Codes of `Image Viewer V1.1`](#part0008.xhtml_complete-source-codes)
    *   [2.6 Summary](#part0008.xhtml_summary)
*   [**Chapter 3**](#part0009.xhtml): Enhanced Image Viewer with Slide Show Capacity
    *   [3.1 Add Status Bar at the Bottom of `BorderPane`](#part0009.xhtml_add-footer)
    *   [3.2 Improve Button's Reaction Aspect](#part0009.xhtml_improve-button)
    *   [3.3 Add Slide Show Capabilities](#part0009.xhtml_add-slideshow)
    *   [3.4 Add Fade Transition between Slides](#part0009.xhtml_fade-transition)
    *   [3.5 Complete Source Codes of `Image Viewer V1.2`](#part0009.xhtml_complete-source-codes)
    *   [3.6 Summary](#part0009.xhtml_summary)

Figure 1. Snapshot of The Image Viewer in JavaFX 8.

![](Images/image00122.jpeg "image_viewer_1.jpg")

## Why Choose This Book

This book is for software developers who are interested in developing GUIs using JavaFX library for rich client applications.

Important features in JavaFX are illustrated by step-by-step development of real world Java applications.

Instructive diagrams are used to help readers capture abstract concepts instantly. And all diagrams used in each chapter are created using the graphics tools developed in this book series.

This book is for you if you are:

*   A Java GUI programmer, novice or professional, who is new to JavaFX.
*   A Java programmer who has preliminary knowledge of JavaFX and would like to learn how to develop interactive sketch drawing tools.
*   A professional software engineer who is interested in the development of object oriented JavaFX graphics tools and practical applications, along with complete and well-documented source codes.

## What You Need for This Book

If you want to compile and run applications included in this book, you need to download and install JDK. Here's the website to download JDK 8, [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

To copy the complete source codes from this kindle e-Book, Here's a suggestion:

1.  Install `Calibre`, a free and open source E book Management software, to your PC.
2.  Use `Add books` function in `Calibre` to add the .mobi file of the e-Book to `Calibre` library.
3.  Open the book from `Calibre` and copy the source codes to Java files.

#   INTRODUCTION

This book series is a tutorial for software developers to build GUIs of Java applications using JavaFX 8 which has become a part of Java™ SE Development Kit 8 (JDK 8).

The primary objective of this book series is to provide a comprehensive handbook, which brings forward the frequently used features and the essence of JavaFX. The usages of APIs provided in JavaFX packages are illustrated through the step-by-step development of a sophisticated graphics toolkit.

Complete source codes of the graphics toolkit, a set of packages with reusable classes as well as embeddable JavaFX applications, are included in the book series. Download and install JDK 8 before you compile and run these applications. Here's the website to download the latest version of JDK, [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

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

As of the publishing of this book on March, 2016, the latest JDK releases are:
JDK 8u66 on October 20, 2015, and JDK 8u72 on January 2016.

The schedule of general availability (GA) for JDK 9 is March 23rd, 2017.

## Prerequisite

JavaFX applications presented in this book using APIs provided in JavaFX packages to build GUIs. Knowledge of Swing packages is not a must, however, readers must be familiar with the basics of Java programming language. If you are new to Java, visit this website,
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

![](Images/image00123.jpeg "javafx_app_guis.jpg")

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

If you possess multitudes of legacy codes written in Swing and would like to incorporate JavaFX features into Swing codes, JDK 8 provides mechanism to do so, and vice versa, you can include Swing components in JavaFX applications.

The topic of JavaFX-Swing Interoperability is not covered in this book. If you are interested in this topic, visit Oracle Online Documentation "JavaFX: Interoperability -- JavaFX-Swing Interoperability" at here:
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

JavaFX allows the usage of CSS (Cascading Style Sheet) to describe the presentation styles of application's user interfaces. Defining the presentation attributes--such as color, font, margins, padding, width, height, lines, background images, etc., using CSS, separated from application codes, reveals significant conveniency in many ways:

*   Customization from software provider's side:

    Applications compiled from the same set of codes can bear a variety of presentation styles, each of them complying with different customer's requirements.

*   Customization from application user's side:

    Even after the software has been released, in case application users have preferences for the look of UIs, it is also applicable to modify the presentation attributes, defined in CSS files, at customer site.

*   Benefits for designers of presentation styles:

    The separation of application codes from definitions of presentation styles improves readability of codes and simplifies the tasks for graphics designers by focusing on dealing with CSS only.

*   Benefits for software developers:

    During the course of testing, developers may frequently change style attributes defined in CSS file in order to evaluate the variety looks of GUIs. If the application has to quit and restart again for each change, it is a very tiresome task. To facilitate this evaluation process, the best strategy is to design a makeshift `Load` button, and whenever any style attribute is changed, simply click on the button to re-load the CSS, there is no need to quit the application and restart it, thus saving tremendous time spending on testing.

*   Similarity between CSS in JavaFX and CSS in HTML:

    The syntax of CSS in JavaFX is same as that of CSS in HTML, thus any designer has experience on CSS for browsers can do the styling for JavaFX application's UIs with little learning effort.

#### Reference to Oracle Online Documentation "Skinning JavaFX Applications with CSS":
[http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/css_tutorial.htm](http://docs.oracle.com/javase/8/javafx/user-interface-tutorial/css_tutorial.htm)

### Creating User Interfaces using FXML

FXML is a markup language which complies with the XML (Extensible Markup Language) format, with additional rules, for creating user interfaces of JavaFX applications. Considering hand coding FXML is error prone, a feasible approach is to generate FXML codes by means of GUI builders.

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

    There is a web engine component embedded in JavaFX architecture and providing a set of APIs, located in `javafx.scene.web` package, for developing applications with functionality of a web browser. To view a web page, first you create a `WebView` object which extends `javafx.scene.Parent` and inherits all the features of a node, then obtain the `WebEngine` that associates with it. The `WebEngine` provides methods relevant to manipulating a web page, such as: loading/displaying the web page, either by given a url or content of the page, accessing the Document Object Model (DOM) created by `WebEngine` for the loaded web page, handling a variety of events initiated from JavaScript,...etc.

    #### Reference to Oracle Online Documentation "JavaFX: Adding HTML Content to JavaFX Applications":
    [http://docs.oracle.com/javase/8/javafx/embedded-browser-tutorial/index.html](http://docs.oracle.com/javase/8/javafx/embedded-browser-tutorial/index.html)

*   `HTMLEditor` Class for Editing HTML Pages

    The full support of HTML editing ability comes from `HTMLEditor` class, extends `javafx.scene.control.Control`, resides in `javafx.scene.web` package. To embed a HTML editor into your JavaFX application, you simply create an instance of `HTMLEditor`, add it to a scene graph, then it is ready to interact with users. The following two methods are useful to get and set the HTML content of the editor: `getHtmlText()`, `setHtmlText(java.lang.String` htmlText`)`.

    Unlike the similar control `TextArea` that handles multiple lines of plain text, the `HTMLEditor` formats text that complies with HTML syntax.

    The usage of the HTML editor are widely required in various fields of software, For example, bloggers writing articles to post (content management system), users of an Email System composing messages (messaging system), online sellers preparing product descriptions for listing (e-commence management system),...etc.

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
Basic Image Viewer
--Developing Image Viewer V1.0

## Preface

In this chapter, we'll illustrate usages of JavaFX APIs by means of step-by-step development of an image viewing application, `ImageViewer V1.0`. From detailed descriptions and well-documented example codes excerpted from ImageViewer V1.0x, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0007.xhtml_summary) section.

The complete development process of `ImageViewer V1.0` is characterized by the following steps:

*   [1.1 Create `ImageViewer` Class as Subclass of `Application`](#part0007.xhtml_create-image-viewer)
    *   [1.1.1 JavaFX Application Thread vs. Java Launcher Thread](#part0007.xhtml_thread)
    *   [1.1.2 Catch Resize Event of Image Rendering Area](#part0007.xhtml_image-area-resize)
*   [1.2 Create Menu Bar](#part0007.xhtml_add-menu-bar)
    *   [1.2.1 Add File Menu to Menu Bar](#part0007.xhtml_add-file-menu)
    *   [1.2.2 Select Image File from File Open Dialog and Display Image on `StackPane`](#part0007.xhtml_file-chooser)
*   [1.3 Create Option Menu and View Submenu](#part0007.xhtml_add-option-menu)
    *   [1.3.1 Create Toggle Group, Radio Menu Items and Add Listener for `selectedToggle` Property](#part0007.xhtml_toggle-group)
*   [1.4 Implement Fit Width, Fit Height and Original Size Viewing Options](#part0007.xhtml_view-option)
    *   [1.4.1 Approach One: Bind `ImageView`'s `fitWidth`/`fitHeight` Properties to `Scene`'s `width`/`height` Properties Respectively](#part0007.xhtml_bind-unbind)
        *   [1.4.1.1 Implement Fit Width Viewing Option](#part0007.xhtml_bind-fit-width)
        *   [1.4.1.2 Implement Fit Height Viewing Option](#part0007.xhtml_bind-fit-height)
        *   [1.4.1.3 Implement Original Size Viewing Option](#part0007.xhtml_bind-original-size)
        *   [1.4.1.4 Complete Source Codes of `ImageViewer` Class](#part0007.xhtml_complete-source-codes-1)
    *   [1.4.2 Approach Two: Change Values for `fitWidth` Property and `fitHeight` property](#part0007.xhtml_set-fit-w-h-value)
        *   [1.4.2.1 Catch Resize Event of Scene to Adjust Viewing Size of Image](#part0007.xhtml_scene-resize)
        *   [1.4.2.2 Complete Source Codes of `ImageViewer` Class](#part0007.xhtml_complete-source-codes-2)
*   [1.5 Summary](#part0007.xhtml_summary)

## 1.1 Create `ImageViewer` Class as Subclass of `Application`

The graphical user interfaces of a JavaFX application are managed in hierarchical tree structure, called a scene graph. In `ImageViewer` application, we employ a `BorderPane` as the root node of a scene graph, and place a `StackPane` in the center of `BorderPane` as image rendering area. Both `BorderPane` and `StackPane` are among build-in layout panes, reside in `javafx.scene.layout` package and are direct subclasses of `javafx.scene.layout.Pane` class.

`BorderPane` class allows you to create graphical user interfaces featuring classic look-and-feel of main windows. In the next section you'll see a menu bar added at the top of `BorderPane`, and in the later chapter a status bar added at the bottom.

`StackPane` class lays out its children in a stack, placing the later created child at the top of previous one. In `ImageViewer` application, since only one image is viewed at one time, the `StackPane` has only one child. If the size of an image is smaller than the size of `StackPane`, the image is placed in the center of `StackPane`. If the size of an image is larger than that of `StackPane`, `StackPane` is expanded automatically to accommodate the whole image, and if the viewing space in the application window is not larger enough, only center portion of the image is visible by default. In later section, we'll demonstrate how to avoid a `StackPane` being resized by its content, see [here](#part0007.xhtml_set-min-size).

A `Scene` object is created as the container of a scene graph, given a root node as parameter. In `ImageViewer` application, the root node is a `BorderPane`, and initial width and height of the `Scene` object is set to 600 pixels and 400 pixels. Both `BorderPane` and `StackPane` are resizable layout panes; therefore, if the application window is dynamically resized by a user, the scene is resized and a resize event is passed on to its root node, resulting in re-calculation of the size of image rendering area accordingly.

You place a scene on a `Stage` to make it alive, using the `setScene` method defined in `Stage` class. `Stage` is a direct subclass of `javafx.stage.Window`; it is the top-level window of a JavaFX application.

JavaFX system creates a `Stage` object, referred as primary stage, and passed to the `start` method, an abstract method defined in `Application` class. Developers can construct additional `Stage` objects as needed for their applications.

The following codes demonstrate how to create `ImageViewer` class as a direct subclass of `Application`, and override the `start` method. Here are codes:

Listing 1-1. Create `ImageViewer` class which extends `Application` class, override `start` method, create `BorderPane` as the root node of a scene, and place `StackPane` in the center of `BorderPane` as image rendering area:

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
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 */

public class ImageViewer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    StackPane imageArea = new StackPane();
    rootPane.setCenter(imageArea);

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

### 1.1.1 JavaFX Application Thread vs. Java Launcher Thread

`Application` class is the entry point of a JavaFX application. It defines the following significant methods:

`public void init() throws Exception`

`public abstract void start(Stage` primaryStage`) throws Exception`

`public void stop() throws Exception`

The `init` method, which does nothing, is called from Java launcher thread. While the `start` method, an abstract and must be overridden, is called from JavaFX Application Thread after `init` method has returned. If you need do some initial works before `start` method, you can do that by overriding `init` method; however it is crucial to notice that nodes that are members of a live scene must be accessed from JavaFX Application Thread. And the construction of a `Scene` object or a `Stage` object must be accessed from JavaFX Application Thread as well.

### 1.1.2 Catch Resize Event of Image Rendering Area

For debugging and testing purpose at this point, we register a `ChangeListener` providing a `changed` method to be notified whenever width or height of image rendering area is changed. Width or height of image rendering area is changed when a user resizes the application window.

To register a `ChangeListener` to observe change of value for a property, we use this method:

```
 void addListener(ChangeListener<? super T> listener) 
```

defined in `javafx.beans.value.ObservableValue` interface, providing implementation of `changed(ObservableValue<? extends T>` observable`, T` oldValue`, T` newValue`)` method, to be invoked when this property's value is changed.

The same `ChangeListener` is allowed to be registered to multiple `ObservableValue`s. To avoid memory leak problem, it is a good programming practice to un-register a listener whenever the value no longer need be observed, using `removeListener(ChangeListener<? super T>` listener`)` method, which removes the link between an observable value and a listener.

`StackPane` class inherits `width` and `height` properties from `javafx.scene.layout.Region` class. Both properties are type of `ReadOnlyDoubleProperty`, an abstract class that implements `ObservableValue` interface. As the name reveals, an `ObservableValue` holds a value that are observable, you can listen to the change of value and take actions as necessary.

The following codes demonstrate how to watch the resize event of image rendering area, a `StackPane` placed in the center of a `BorderPane`.

Import Statements:

```
 import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
```

Listing 1-2. Add listeners to width property and height property of image rendering area:

```
 imageArea.widthProperty().addListener(new ChangeListener<Object>() {
  public void changed(ObservableValue o, Object oldVal,
    Object newVal) {
    System.out.format("imageArea width changed from %.1f to %.1f%n",
      oldVal, newVal);
  }
});
imageArea.heightProperty().addListener(new ChangeListener<Object>() {
  public void changed(ObservableValue o, Object oldVal,
    Object newVal) {
    System.out.format("imageArea height changed from %.1f to %.1f%n",
      oldVal, newVal);
  }
});
```

Listing 1-3. Complete source codes of `ImageViewer` class become like this:

```
 package imageviewer;

import javafx.application.Application;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.scene.Scene;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java
 * (in directory: ImageViewer1.0/src/example1/imageviewer/)
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    StackPane imageArea = new StackPane();
    rootPane.setCenter(imageArea);

    Scene scene = new Scene(rootPane, 600, 400);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
        Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
          oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
        Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
          oldVal, newVal);
     }
    });

    stage.setTitle("ImageViewer V1.0");
    stage.setScene(scene);
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 1-1. Snapshot of initial appearance of `ImageViewer V1.0`

![](Images/image00124.gif "first.gif")

Compile and run the application.

Output from Compiling and Running ImageViewer in command line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeOne\ImageViewer1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked imageviewer\*.java

jar cf imageviewer.jar imageviewer

java -cp imageviewer.jar imageviewer.ImageViewer
imageArea width changed from 0.0 to 600.0
imageArea height changed from 0.0 to 400.0
```

Now, change the size of scene by dragging the edge or corner of the application window, you will see output similar as follows:

```
 imageArea width changed from 600.0 to 437.0
imageArea height changed from 400.0 to 263.0
imageArea width changed from 437.0 to 636.0
imageArea height changed from 263.0 to 384.0
imageArea width changed from 636.0 to 587.0
imageArea height changed from 384.0 to 448.0
```

## 1.2 Create Menu Bar

In this section, we are creating a `MenuBar`, adding it at the top of `BorderPane` which is the root node of a scene graph.

Generally a `MenuBar` object contains multiple `Menu`s laying out horizontally, and each `Menu` contains multiple `MenuItem`s. Since `Menu` class extends `MenuItem` class, you can place a `Menu` within a `Menu`, the nested one is called a submenu. As a `MenuBar` is rendered on a window, what a user sees is names of menus only, the content of each menu is hidden until the mouse's left button clicked on a menu name, or the mnemonic key combination which defined as shortcut keys for the menu is hit.

The benefits for employing menu user interface include the followings:

*   Require less space

    A menu only occupies the space for its name when it is not in need by a user.

*   Organizable capability

    To facilitate the accessibility, you organize menu items in a tree structure according to functionality, grouping the menu items that are alike in a same menu, avoiding overcrowding one menu by means of submenus, and placing the more frequently requested menu items in upper levels. Usually the most important ones are placed on the top level of the tree.

*   Invoke action by one keystroke

    You can use mnemonic mechanism to navigate menus within a `MenuBar` and define shortcut keys to enable users to invoke the action of a `MenuItem` by one keystroke. For example, press Alt and F keys at the same time to show File menu and press Ctrl and S keys at the same time to perform save file action.

To add a `Menu` to a `MenuBar`, first we call the `getMenus()` method, which returns an `ObservableList` of `Menu`s. The `ObservableList` is a subinterface of `java.util.List`, thus we can use the `add` method, one of the basic utilities defined in Java `Collection` interface, to append a menu to the list. The codes are as follows:

Listing 1-4. Add a `Menu` to a `MenuBar`:

```
 MenuBar menuBar = new MenuBar();
Menu menuFile = new Menu("File");
menuBar.getMenus().add(menuFile);
```

To add a `MenuItem` to a `Menu`, we use `getItems()` method, which returns an `ObservableList` of `MenuItem`s. The rest of circumstances are similar to what we have described above. The codes are as follows:

Listing 1-5. Add a `MenuItem` to a `Menu`:

```
 MenuItem load = new MenuItem("Load");
MenuItem exit = new MenuItem("Exit");
menuFile.getItems().addAll(load, exit);
```

### 1.2.1 Add File Menu to Menu Bar

In this application at this point, `MenuBar` contains a `File` menu. The `File` menu contains two menu items: `Load` and `Exit`. The following snippets of codes show how to accomplish these tasks.

Import Statements:

```
 import javafx.application.Platform; 
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
```

Listing 1-6. Add a menu bar to `ImageViewer` application, place it at the top of root node which is a `BorderPane`:

```
 // Add menu bar
MenuBar menuBar = new MenuBar();
Menu menuFile = new Menu("File");
MenuItem load = new MenuItem("Load");
MenuItem exit = new MenuItem("Exit");
menuFile.getItems().addAll(load, exit);
menuBar.getMenus().add(menuFile);
rootPane.setTop(menuBar);

// Add action for exit menu item
exit.setOnAction(new EventHandler<ActionEvent>() {
  @Override
  public void handle(ActionEvent e) {
    Platform.exit();
  }
});
```

### 1.2.2 Select Image File from File Open Dialog and Display Image on `StackPane`

To navigate a file system, we use `FileChooser` class which provides a convenient method, `showOpenDialog(Window` ownerWindow`)` for choosing a file to open.

The action of `Load` menu item is to browse a local file system, select an image file and display the image on image rendering area.

The `setOnAction(EventHandler<ActionEvent>` value`)` method, provided in `MenuItem` class, is used to add an event handler to handle `ActionEvent` of `Load` menu item.

In order to load and display images, we use `ImageView` class in association with `Image` class. `Image` class loads an image given a url in type of `String`, and `ImageView` class displays the image on an image rendering area.

First, we create an `ImageView` added as a child of a `StackPane`. Later, when an image file is obtained, we'll create an `Image` object to load the image file and call the `setImage(Image` value`)` method provided in `ImageView` class to view the image.

The situation is elaborated as follows: When the `showOpenDialog` method of a `FileChooser` is executed, a file open dialog is popped up. When a user selects a file and clicks `Open` button in the file open dialog, the `showOpenDialog` method returns the selected file, type of `File`, to caller, it is converted to a url of `String` representation, and an `Image` object is created given the url as parameter, at this point, the image is loaded into memory, yet not showing on screen, the selected image is shown as soon as the `setImage` method of an `ImageView` is executed. For the sake of efficiency, we create `ImageView` object only once, and update its `Image` property each time a new image file is selected and opened.

The following snippets of codes accomplish these tasks:

Import Statements:

```
 import java.io.File;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.stage.FileChooser;
```

Listing 1-7. Create `FileChooser` Object, `ImageView` Object and add `EventHandler` for `Load` menu Item to load an image:

```
 // Create a file chooser
final FileChooser fileChooser = new FileChooser();
fileChooser.setTitle("Open an Image File");

// Create image view, add to image area
final ImageView imageView = new ImageView();
imageArea.getChildren().add(imageView);

// Add action for menu item Load
load.setOnAction(new EventHandler<ActionEvent>() {
  @Override
  public void handle(ActionEvent e) {
    // Open FileChooser dialog
    File file = fileChooser.showOpenDialog(stage);
    if (file != null) {
      String url = file.toURI().toString();
      Image image = new Image(url);
      imageView.setImage(image);
    }
  }
});
```

Please remember to declare the variable `stage` as `final` since it is accessed within inner class, the anonymous `EventHandler` class of `Load` menu item.

Now, we need to deal with a significant matter regarding the resizability of image rendering area, the `StakePane`. To avoid resizing the `StakePane` when displaying an image of larger size, we need to set minimum size for the `StakePane`. Here's the code to do this:

```
 imageArea.setMinSize(0, 0);
```

Without adding the above line of code, the size of `StakePane` is changeable when loading an image with size larger than the current size of `StakePane`. Here's an example:

Suppose the current size of `StakePane` is 600 by 375; after displaying an image of size 1280 by 960, the size of `StakePane` is enlarged to become 1280 by 960; however, the viewable portion is still 600 by 375.

Setting minimum size for the `StakePane` results in no size changing event occurred whenever a new image is opened, and also simplify the codes to be developed in the following chapters.

Listing 1-8. Complete source codes of `ImageViewer` class become like this:

```
 package imageviewer;

import java.io.File;
import javafx.application.Application;
import javafx.application.Platform; 
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java
 * (in directory: ImageViewer1.0/src/example2/imageviewer/)
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 *
 * Add a menu bar in the top of BorderPane
 * Create File Menu, and using FileChooser's Open Dialog to
 * select an image file, load and display the image in image rendering area.
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    Scene scene = new Scene(rootPane, 600, 400);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
          oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
          oldVal, newVal);
      }
    });

    // Add menu bar
    MenuBar menuBar = new MenuBar();
    Menu menuFile = new Menu("File");
    MenuItem load = new MenuItem("Load");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(load, exit);
    menuBar.getMenus().add(menuFile);
    rootPane.setTop(menuBar);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });

    // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageArea.getChildren().add(imageView);

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          String url = file.toURI().toString();
          Image image = new Image(url);
          imageView.setImage(image);
        }
      }
    });	

    stage.setTitle("ImageViewer V1.0");
    stage.setScene(scene);
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Compile and run the application. Click `Load` menu item in `File` menu, navigate to a directory that contains image files, select an image file, click `Open` button in `FileChooser`'s Open Dialog, the image file will be loaded and displayed in the center of application window.

Figure 1-2. Snapshot of menu bar with `File` menu when it is clicked

![](Images/image00125.gif "filemenu.gif")

Figure 1-3. Snapshot of selecting an image file from file chooser

![](Images/image00126.gif "filechooser.gif")

Figure 1-4. Snapshot of displaying a small size image in the center

![](Images/image00127.gif "small_image.gif")

Figure 1-5. Snapshot of displaying a large size image in the center

![](Images/image00128.jpeg "large_image.gif")

## 1.3 Create Option Menu and View Submenu

We need an `Option` menu allowing a user to choose preferred viewing criteria. The `Option` Menu contains a `View` submenu which contains three mutually exclusive choices, they are as follows:

`Fit Width`

Render an image on an area by scaling `fitWidth` property of an `ImageView`, while preserving original width/height ratio, to fit the width of current available image viewing space.

`Fit Height`

Render an image on an area by scaling `fitHeight` property of an `ImageView`, while preserving original width/height ratio, to fit the height of current available image viewing space.

`Original Size`

Render an image in its original size, the outer portion of image that exceeds the boundary of current available viewing space will be blocked. This is set as the initial viewing option.

Please note that the available image viewing space is determined by current width and height of the application window, called a `Stage`, which subsequently is subject to the current size of a `Scene`, the container of a scene graph. Initially the scene is set to 600 pixels by 400 pixels, thus, the size of available image rendering space will be same as the size of the scene. After we added a menu bar at the top of `BorderPane`, which is the root node of the scene, the height of available image rendering space becomes height of scene minus height of menu bar, while the width remains the same.

### 1.3.1 Create Toggle Group, Radio Menu Items and Add Listener for `selectedToggle` Property

To implement mutually exclusive choices in a menu, we create `RadioMenuItem` objects and a single `ToggleGroup` object, then associate each `RadioMenuItem` to the same `ToggleGroup`.

To watch the change of selected radio menu item, we use:

```
 void addListener(ChangeListener<? super T> listener) 
```

to register a [`ChangeListener`](#part0007.xhtml_change-listener) for `selectedToggle` property of `ToggleGroup` object.

The following snippets of codes show how to accomplish these tasks.

Import Statements:

```
 import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
```

Listing 1-9. Create `Option` menu, `ToggleGroup`, `RadioMenuItem`s, `View` submenu and add a listener for `selectedToggle` property of the `ToggleGroup`:

```
 // Create Option menu
Menu menuOption = new Menu("Option");

// Create toggle group
final ToggleGroup groupOption = new ToggleGroup();

// Create radio menu items
final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
fitWidth.setToggleGroup(groupOption);
final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
fitHeight.setToggleGroup(groupOption);
final RadioMenuItem original = new RadioMenuItem("Original Size");
original.setToggleGroup(groupOption);

// Add listener for toggle group
groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
  public void changed(ObservableValue<? extends Toggle> ov,
                      Toggle old_toggle, Toggle new_toggle) {
    if (groupOption.getSelectedToggle() != null) {
      RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
      if (choiceItem == fitWidth) {
        System.out.println("fitwidth");
      } else if (choiceItem == fitHeight) {
        System.out.println("fitheight");
      } else {
        System.out.println("original size");
      }
    } 
  }
});

// Create View submenu for Option menu
Menu menuView = new Menu("View");
menuView.getItems().addAll(fitWidth, fitHeight, original);

// Set Original Size as default choice
original.setSelected(true);

// Add option menu to menu bar
menuOption.getItems().add(menuView);
menuBar.getMenus().add(menuOption);
```

Listing 1-10. Complete source codes of ImageViewer class become like this:

```
 package imageviewer;

import java.io.File;
import javafx.application.Application;
import javafx.application.Platform; 
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java
 * (in directory: ImageViewer1.0/src/example3/imageviewer/)
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 *
 * Add a menu bar in the top of BorderPane
 * Create File Menu, and using FileChooser's Open Dialog to
 * select an image file, load and display the image in image rendering area.
 * 
 * Create Option menu contains View submenu, let a user chooses image viewing
 * criteria: Fit Width, Fit Height, or the default option Original Size.
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    Scene scene = new Scene(rootPane, 600, 400);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
          oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
          oldVal, newVal);
      }
    });

    // Add menu bar
    MenuBar menuBar = new MenuBar();
    Menu menuFile = new Menu("File");
    MenuItem load = new MenuItem("Load");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(load, exit);
    menuBar.getMenus().add(menuFile);
    rootPane.setTop(menuBar);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });

    // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageArea.getChildren().add(imageView);

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          String url = file.toURI().toString();
          Image image = new Image(url);
          imageView.setImage(image);
        }
      }
    });

    // Create Option menu
    Menu menuOption = new Menu("Option");

    // Create toggle group
    final ToggleGroup groupOption = new ToggleGroup();

    // Create radio menu items
    final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
    fitWidth.setToggleGroup(groupOption);
    final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
    fitHeight.setToggleGroup(groupOption);
    final RadioMenuItem original = new RadioMenuItem("Original Size");
    original.setToggleGroup(groupOption);

    // Add listener for toggle group
    groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
        if (groupOption.getSelectedToggle() != null) {
          RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
          if (choiceItem == fitWidth) {
            System.out.println("fitwidth");
          } else if (choiceItem == fitHeight) {
            System.out.println("fitheight");
          } else {
            System.out.println("original size");
          }
        } 
      }
    });

    // Create View submenu for Option menu
    Menu menuView = new Menu("View");
    menuView.getItems().addAll(fitWidth, fitHeight, original);

    // Set Original Size as default choice
    original.setSelected(true);

    // Add option menu to menu bar
    menuOption.getItems().add(menuView);
    menuBar.getMenus().add(menuOption);

    stage.setTitle("ImageViewer V1.0");
    stage.setScene(scene);
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 1-6. Snapshot of `Option` menu contains `View` submenu

![](Images/image00129.gif "optionmenu.gif")

Compile and run the application. Selecting different radio menu items in `View` submenu, you will see output similar as follows:

Output from Running the Program in Command Line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeOne\ImageViewer1.0\src\example3>
javac -encoding utf-8 -Xlint:unchecked imageviewer\*.java

jar cf imageviewer.jar imageviewer

java -cp imageviewer.jar imageviewer.ImageViewer
original size
imageArea width changed from 0.0 to 600.0
imageArea height changed from 0.0 to 375.0
fitheight
fitwidth
```

## 1.4 Implement Fit Width, Fit Height and Original Size Viewing Options

In this section, we demonstrate how to adjust viewing size of an image to fit the application window. The `ImageView` is created as a child of a `StackPane`, and according to `StackPane` default layout strategy, an image is positioned in the center of `StackPane`; therefore, if the size of an image is larger than the current available viewing space, which is subject to the size of a scene, outer portion of the image will be blocked, thus a user won't be able to view the whole image.

In last section, we created an `Option` menu containing three viewing choices: `Fit Width`, `Fit Height`, and `Original Size`. An image is rendered based on the viewing option currently selected, initially it is set to `Original Size`. By default, we'd like to preserve the original width to height ratio of an image when scaling is in action. To do so, we set value of `preserveRatio` property to `true` as follows:

Listing 1-11. Set value of `preserveRatio` property to `true`:

```
 final ImageView imageView = new ImageView();
imageView.setPreserveRatio(true);
```

Now, let's explore two approaches to render image according to the viewing option currently selected.

### 1.4.1 Approach One: Bind `ImageView`'s `fitWidth`/`fitHeight` Properties to Scene's `width`/`height` Properties Respectively

We use `bind` and `unbind` methods defined in `Property` interface to implement `Fit Width`, `Fit Height`, and `Original Size` viewing options.

What enticing here is that, once the binding becomes effective, an image's viewing width and/or height will be changed accordingly whenever width and/or height of `Scene` is changed dynamically.

#### 1.4.1.1 Implement Fit Width Viewing Option

If a user selects `Fit Width` as viewing option, we'll have `fitWidth` property of `ImageView` bind with `width` property of `Scene`, and unbind `fitHeight` property. Here are codes:

Listing 1-12. Bind `fitWidth` property of `ImageView` object with `width` property of `Scene`:

```
 imageView.fitWidthProperty().bind(scene.widthProperty());
imageView.fitHeightProperty().unbind();
// Besides unbind, must also set fit height to 0
imageView.setFitHeight(0);
```

#### 1.4.1.2 Implement Fit Height Viewing Option

If `Fit Height` is selected as viewing option, we'll have `fitHeight` property of `ImageView` bind with `height` property of `Scene`, subtracting height of menu bar, and unbind `fitHeight` property.

We are using `subtract` method to calculate the available viewing height for an image. The `subtract`(`double` other) method, which inherited from `DoubleExpression` class by `DoubleProperty` class, returns a new `NumberBinding` object that calculates the difference of this `NumberExpression` and the given constant value. Here are codes:

Listing 1-13. Bind `fitHeight` property of `ImageView` with `height` Property of scene, subtracting height of menu bar:

```
 // Available height for rendering image is
// subtract menubar's height from scene height
imageView.fitHeightProperty().bind(
   scene.heightProperty().subtract(menuBar.getHeight()));
imageView.fitWidthProperty().unbind();
// Besides unbind, must also set fit width to 0 
imageView.setFitWidth(0); 
```

#### 1.4.1.3 Implement Original Size Viewing Option

If `Original Size` is selected as viewing option, we'll have `fitWeight` property as well as `fitHeight` property of the `ImageView` object unbind. Here are codes:

Listing 1-14. Unbind `fitWidth` property as well as `fitHeight` property of the `ImageView` object:

```
 imageView.fitWidthProperty().unbind();
imageView.fitHeightProperty().unbind();
// Besides unbind, must also set fit height/height to 0
imageView.setFitWidth(0);
imageView.setFitHeight(0);
```

Please note that, changing values of `fitWidth`/`fitHeight` properties of an `ImageView` object doesn't affect `width`/`height` properties of the underlying `Image` object. Properties of the `Image` object, such as `width` and `height`, are staying intact while properties relevant to viewing options of the `ImageView` are altering dynamically by a user.

The advantage of approach one is that you don't need to register an event handler to response to resizing event of a `Scene`. When the application window is resized dynamically, the `Scene` is resized, accordingly the corresponding properties of the `ImageView` is changed, and the size of image rendering area, a `StackPane` object, will be re-computed automatically.

The following snippets of codes show the implementation of approach one.

Listing 1-15. Listen to the change of selection for radio menu items and use `bind` and `unbind` methods to adjust `fitWidth` and `fitHHeight` of an image view.

```
 final StackPane imageArea = new StackPane();

   ...

final Scene scene = new Scene(rootPane, 600, 400); 

   ...

final MenuBar menuBar = new MenuBar();

   ...

// Create toggle group
final ToggleGroup groupOption = new ToggleGroup();

// Create radio menu items and add to the toggle group
final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
fitWidth.setToggleGroup(groupOption);
final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
fitHeight.setToggleGroup(groupOption);
final RadioMenuItem original = new RadioMenuItem("Original Size");
original.setToggleGroup(groupOption);

groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
  public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
    if (groupOption.getSelectedToggle() != null) {
      RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
      if (choiceItem == fitWidth) {
        System.out.println("fitwidth");
        imageView.fitWidthProperty().bind(scene.widthProperty());
        imageView.fitHeightProperty().unbind();
        // Besides unbind, must also set fit height to 0
        imageView.setFitHeight(0);
      } else if (choiceItem == fitHeight) {
        System.out.println("fitheight");
        // Available height for rendering image is
        // subtract menubar's height from scene height
        imageView.fitHeightProperty().bind(
          scene.heightProperty().subtract(menuBar.getHeight()));
        imageView.fitWidthProperty().unbind();
        // Besides unbind, must also set fit width to 0 
        imageView.setFitWidth(0); 
      } else {
        System.out.println("original size");
        imageView.fitWidthProperty().unbind();
        imageView.fitHeightProperty().unbind();
        // Besides unbind, must also set fit height/height to 0
        imageView.setFitWidth(0);
        imageView.setFitHeight(0);
      }
    } 
  }
});
```

#### 1.4.1.4 Complete Source Codes of `ImageViewer` Class

Complete source codes of `ImageViewer` class for Approach One become these:

Listing 1-16. Complete source codes of ImageViewer class become like this:

```
 package imageviewer;

import java.io.File;
import javafx.application.Application;
import javafx.application.Platform; 
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java
 * (in directory: ImageViewer1.0/src/example4/imageviewer/)
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 *
 * Add a menu bar in the top of BorderPane
 * Create File Menu, and using FileChooser's Open Dialog to
 * select an image file, load and display the image in image rendering area.
 * 
 * Create Option menu contains View submenu, let a user chooses image viewing
 * criteria: Fit Width, Fit Height, or the default option Original Size.
 *
 * Adjust image viewing size using bind and unbind methods:
 * Bind fitWidth/fitHeight of image view to width/height of scene,
 * so that, size of image view will be changed automatically
 * whenever scene is resized
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    final StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageView.setPreserveRatio(true);
    imageArea.getChildren().add(imageView);

    final Scene scene = new Scene(rootPane, 600, 400);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });

    // Add menu bar
    final MenuBar menuBar = new MenuBar();
    Menu menuFile = new Menu("File");
    MenuItem load = new MenuItem("Load");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(load, exit);
    menuBar.getMenus().add(menuFile);
    rootPane.setTop(menuBar);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });

    // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          String url = file.toURI().toString();
          Image image = new Image(url);
          imageView.setImage(image);
        }
      }
    });

    // Create Option menu
    Menu menuOption = new Menu("Option");

    // Create toggle group
    final ToggleGroup groupOption = new ToggleGroup();

    // Create radio menu items
    final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
    fitWidth.setToggleGroup(groupOption);
    final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
    fitHeight.setToggleGroup(groupOption);
    final RadioMenuItem original = new RadioMenuItem("Original Size");
    original.setToggleGroup(groupOption);

    // Listen to the change of selection in the toggle group
    groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
        if (groupOption.getSelectedToggle() != null) {
          RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
          if (choiceItem == fitWidth) {
            System.out.println("fitwidth");
            imageView.fitWidthProperty().bind(scene.widthProperty());
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height to 0
            imageView.setFitHeight(0);
          } else if (choiceItem == fitHeight) {
            System.out.println("fitheight");
            // Available height for rendering image is
            // subtract menubar's height from scene height
            imageView.fitHeightProperty().bind(
                scene.heightProperty().subtract(menuBar.getHeight()));
            imageView.fitWidthProperty().unbind();
            // Besides unbind, must also set fit width to 0 
            imageView.setFitWidth(0);
          } else {
            System.out.println("original size");
            imageView.fitWidthProperty().unbind();
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height/height to 0
            imageView.setFitWidth(0);
            imageView.setFitHeight(0);
          }

        }
      }
    });

    // Create View submenu for Option menu
    Menu menuView = new Menu("View");
    menuView.getItems().addAll(fitWidth, fitHeight, original);

    // Set Original Size as default choice
    original.setSelected(true);

    // Add option menu to menu bar
    menuOption.getItems().add(menuView);
    menuBar.getMenus().add(menuOption);

    stage.setTitle("ImageViewer V1.01");
    stage.setScene(scene);
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Please notice that we upgrade version number from V1.0 to V1.01 for approach one.

Compile and run the application. Testing viewing options as follows: First, load a small size image, select all possible viewing options back and forth, also dynamically resize the application window using mouse-dragging the edge or corner of the window. Then, load a larger size image and test all the possible criteria again.

Figure 1-7. Snapshot of rendering an image in original size (320 pixels by 363 pixels).

![](Images/image00130.jpeg "jasmin_original.jpg")

Figure 1-8. Snapshot of rendering an image scaled up to fit width of scene.

![](Images/image00131.jpeg "jasmin_fit_width.jpg")

Figure 1-9. Snapshot of rendering an image scaled up to fit available viewing space of scene height.

![](Images/image00132.jpeg "jasmin_fit_height.jpg")

### 1.4.2 Approach Two: Change Values for `fitWidth` Property and `fitHeight` Property

`ImageView` class provides two properties that allow us to scale the viewing size of an image:

*   `fitWidth`
*   `fitHeight`

To change value for these two properties, we use the `setFitWidth` method and the `setFitHeight` method.

If `Fit Width` viewing option is selected, the viewing width will be set in accordance with the current width of scene. Here's the snippet of codes:

Listing 1-17. Call `setFitWidth` method to set image viewing width same as the width of scene:

```
 imageView.setFitWidth(scene.getWidth());
// Besides setFitWidth, must also set fit height to 0
imageView.setFitHeight(0);
```

If `Fit Height` viewing option is selected, the viewing height will be set in accordance with the current height of scene, subtracting the height of menu bar. Here's snippet of code:

Listing 1-18. Call `setFitHeight` method to set the image viewing height same as the height of scene minus the height of menu bar:

```
 imageView.setFitHeight(scene.getHeight() - menuBar.getHeight());
// Besides setFitHeight, must also set fit width to 0 
imageView.setFitWidth(0); 
```

If `Original Size` option is selected, we need to clear values set previously by giving `0` as value to both `fitWidth` property and `fitHeight` property. Here's the snippet of codes:

Listing 1-19. Call `setFitHeight` and `setFitHeight` methods, given `0` as the value:

```
 // Clear previous set value
imageView.setFitWidth(0);
imageView.setFitHeight(0);
```

The following codes show the implementation of approach two so far.

Listing 1-20. Listen to the change of selection for radio menu items in toggle group, adjust values for `fitWidth` and `fitHeight` properties of image view:

```
 // Listen to the change of selection in the toggle group
groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
  public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
    if (groupOption.getSelectedToggle() != null) {
      RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
      if (choiceItem == fitWidth) {
        imageView.setFitWidth(scene.getWidth());
        // Besides setFitWidth, must also set fit height to 0
        imageView.setFitHeight(0);
      } else if (choiceItem == fitHeight) {
        imageView.setFitHeight(scene.getHeight() - menuBar.getHeight());
        // Besides setFitHeight, must also set fit width to 0 
        imageView.setFitWidth(0); 
      } else {
        // Clear previous set value
        imageView.setFitWidth(0);
        imageView.setFitHeight(0);
      }
    } 
  }
}); 
```

#### 1.4.2.1 Catch Resize Event of Scene to Adjust Viewing Size of Image

To complete approach two, there is one more issue to be resolved: the viewing size of image is subject to the size of scene, initially set to 600 pixels by 400 pixels, which might be changed dynamically. When a user drags the edge or corner of the application window, the scene is resized. We need to catch this resize event to adjust the viewing size of an image accordingly. That is, if current selected viewing option is `Fit Width`, the new width of scene will be adopted as the value of `fitWidth` property of the image view object. And, if `Fit Height` is the selected one, the new height of scene minus height of menu bar will be adopted as the value of `fitHeight` property.

To response to the change of scene's size, we add a listener for `width` Property and `height` property respectively to catch the resize event of scene.

The following snippets of codes accomplish these tasks:

Listing 1-21. Listen to the change of scene's `width` and `height`, adjust `fitWidth` and `fitHeight` of an image view:

```
 // Listen to the width change of scene and adjust fitWidth of image view
scene.widthProperty().addListener(new ChangeListener<Object>() {
  public void changed(ObservableValue o, Object oldVal, Object newVal) {
    if (fitWidth.isSelected()) {
      imageView.setFitWidth((double)newVal);
    }
  }
});
// Listen to the height change of scene and adjust fitHeight of image view   
scene.heightProperty().addListener(new ChangeListener<Object>() {
  public void changed(ObservableValue o, Object oldVal, Object newVal) {
    if (fitHeight.isSelected()) {
      imageView.setFitHeight((double) newVal - menuBar.getHeight());
    }
  }
});
```

#### 1.4.2.2 Complete Source Codes of `ImageViewer` Class

Complete source codes of `ImageViewer` class for Approach Two become these:

Listing 1-22. Complete source codes of ImageViewer become as follows:

```
 package imageviewer;

import java.io.File;
import javafx.application.Application;
import javafx.application.Platform; 
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java
 * (in directory: ImageViewer1.0/src/example5/imageviewer/)
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 *
 * Add a menu bar in the top of BorderPane
 * Create File Menu, and using FileChooser's Open Dialog to
 * select an image file, load and display the image in image rendering area.
 * 
 * Create Option menu contains View submenu, let a user chooses image viewing
 * criteria: Fit Width, Fit Height, or the default option Original Size.
 *
 * Adjust image viewing size using setFitWidth method and setFitHeight method
 * provided in ImageView class 
 * Add listeners for scene's width property and height property
 * Responds to the dynamic resize event of scene by scaling the image view when
 * viewing option is set as Fit Width or Fit Height
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    final StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageView.setPreserveRatio(true);
    imageArea.getChildren().add(imageView);

    final Scene scene = new Scene(rootPane, 600, 400);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });

    // Add menu bar
    final MenuBar menuBar = new MenuBar();
    Menu menuFile = new Menu("File");
    MenuItem load = new MenuItem("Load");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(load, exit);
    menuBar.getMenus().add(menuFile);
    rootPane.setTop(menuBar);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });

    // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          String url = file.toURI().toString();
          Image image = new Image(url);
          imageView.setImage(image);
        }
      }
    });

    // Create Option menu
    Menu menuOption = new Menu("Option");

    // Create toggle group
    final ToggleGroup groupOption = new ToggleGroup();

    // Create radio menu items
    final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
    fitWidth.setToggleGroup(groupOption);
    final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
    fitHeight.setToggleGroup(groupOption);
    final RadioMenuItem original = new RadioMenuItem("Original Size");
    original.setToggleGroup(groupOption);

    // Listen to the change of selection in the toggle group
    groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
        if (groupOption.getSelectedToggle() != null) {
          RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
          if (choiceItem == fitWidth) {
            System.out.println("fitwidth");
            imageView.setFitWidth(scene.getWidth());
            // Besides setFitWidth, must also set fit height to 0
            imageView.setFitHeight(0);
          } else if (choiceItem == fitHeight) {
            System.out.println("fitheight");
            imageView.setFitHeight(scene.getHeight() - menuBar.getHeight());
            // Besides setFitHeight, must also set fit width to 0 
            imageView.setFitWidth(0);
          } else {
            System.out.println("original size");
            imageView.setFitWidth(0);
            imageView.setFitHeight(0);
          }
        }
      }
    });

    // Listen to the width change of scene and adjust fitWidth of image view
    scene.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        if (fitWidth.isSelected()) {
            imageView.setFitWidth((double)newVal);
        }
      }
    });
    // Listen to the height change of scene and adjust fitHeight of image view   
    scene.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        if (fitHeight.isSelected()) {
          imageView.setFitHeight((double) newVal - menuBar.getHeight());
        }
      }
    });

    // Create View submenu for Option menu
    Menu menuView = new Menu("View");
    menuView.getItems().addAll(fitWidth, fitHeight, original);

    // Set Original Size as default choice
    original.setSelected(true);

    // Add option menu to menu bar
    menuOption.getItems().add(menuView);
    menuBar.getMenus().add(menuOption);

    stage.setTitle("ImageViewer V1.02");
    stage.setScene(scene);
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Please notice that we upgrade the version number from V1.01 to V1.02 for approach two.

Compile and run the application. Try the following steps to test the application:

1.  Load an image with size smaller than the initial scene's size (600 pixels by 400 pixels), view the image in its original size.
2.  Select `Fit Width` option, the image view is scaled up to fit the width of scene.
3.  Select `Fit Height` option, the image view is scaled up to fit the height of scene.
4.  Select `Original Size` option, the image view is back to its original size.
5.  Load a larger size image, larger than the current scene's size, since there is not enough space in the scene to view the whole image, you will only see the center portion of the image.
6.  Select `Fit Width` and `Fit height` options respectively to see the different image viewing result.
7.  Resize scene width by mouse dragging the window edge, try both enlarging and reducing width to see the different results.
8.  Resize scene height by mouse dragging the window edge, try both enlarging and reducing height to see the different results.
9.  Resize scene width and height by mouse dragging the window corner, testing all three viewing options respectively.

The approach one (V1.01) is adopted to continue the development of ImageViewer V1.1 in the following chapters.

Figure 1-10. Snapshot of viewing image in its original size (1280 pixels by 960 pixels), outer portion of image is blocked.

![](Images/image00133.jpeg "mao_original.jpg")

Figure 1-11. Snapshot of image view scaled down to fit width of scene, a few portions of image, from top and from bottom, are blocked.

![](Images/image00134.jpeg "mao_fit_width.jpg")

Figure 1-12. Snapshot of image view scaled down to fit height of available space in scene window.

![](Images/image00135.jpeg "mao_fit_height.jpg")

Figure 1-13. Snapshot of image view scaled to fit width while scene's height is enlarged dynamically.

![](Images/image00136.jpeg "mao_fit_width_resize_height.jpg")

Figure 1-14. Snapshot of image view scaled to fit height while scene's size is changed dynamically.

![](Images/image00137.jpeg "mao_fit_height_resize_both.jpg")

Output from Compiling and Running ImageViewer in command line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeOne\ImageViewer1.0\src\example5>
javac -encoding utf-8 -Xlint:unchecked imageviewer\*.java

jar cf imageviewer.jar imageviewer

java -cp imageviewer.jar imageviewer.ImageViewer
original size
imageArea width changed from 0.0 to 600.0
imageArea height changed from 0.0 to 375.0
fitwidth
fitheight
original size
fitwidth
fitheight
original size
imageArea height changed from 375.0 to 439.0
imageArea width changed from 600.0 to 615.0
imageArea width changed from 615.0 to 380.0
imageArea height changed from 439.0 to 527.0
```

## 1.5 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   Built-in JavaFX layout panes, reside in `javafx.scene.layout` package:

    `BorderPane`

    `StackPane`

    (See section [Create `ImageViewer` Class as Subclass of `Application`](#part0007.xhtml_create-image-viewer))
*   `Scene` class, resides in `javafx.scene` package﹐is the container of a scene graph.
    (See [here](#part0007.xhtml_scene-obj-1), section [Approach One: Bind `ImageView`'s `fitWidth`/`fitHeight` properties to scene's `width`/height properties Respectively](#part0007.xhtml_bind-unbind), and section [Catch Resize Event of Scene to Adjust Viewing Size of Image](#part0007.xhtml_scene-resize))
*   `Stage` class, resides in `javafx.stage` package﹐is the top-level container of a JavaFX application.
    (See [here](#part0007.xhtml_stage-obj-1))
*   `Application` class, resides in `javafx.application` package, is the entry point of a JavaFX applications.
    (See section [Create `ImageViewer` Class as Subclass of `Application`](#part0007.xhtml_create-image-viewer))
*   `void start(Stage stage)` method, an abstract method in `Application` class, must be overridden.
    (See [Listing 1-1.](#part0007.xhtml_listing1-1), and section [JavaFX Application Thread vs. Java Launcher Thread](#part0007.xhtml_thread))
*   `void addListener(ChangeListener<? super T>` listener`)` method, defined in `javafx.beans.value.ObservableValue` interface, adds a `ChangeListener` by providing `changed(ObservableValue<? extends T>` observable`, T` oldValue`, T` newValue`)` method, to be invoked when this property's value is changed.
    (See sections: [Catch Resize Event of Image Rendering Area](#part0007.xhtml_image-area-resize), and [Catch Resize Event of Scene to Adjust Viewing Size of Image](#part0007.xhtml_scene-resize))
*   `MenuBar`, `Menu`, and `MenuItem` are among fundamental JavaFX UI components, reside in `javafx.scene.control` package, for designing compact look-and-feel graphical user interfaces using less space.
    (See section [Create Menu Bar](#part0007.xhtml_add-menu-bar))
*   `java.io.File showOpenDialog(Window` ownerWindow`)` method, a convenient method provided in `javafx.stage.FileChooser` class, shows a file open dialog for navigating a local file system.
    (See section [Select Image File from File Open Dialog and Display Image on `StackPane`](#part0007.xhtml_file-chooser))
*   `void setOnAction(EventHandler<ActionEvent>` value`)` method, provided in `MenuItem` class, registers an `EventHandler` to be notified when an `ActionEvent` occurs.
    (See section [Select Image File from File Open Dialog and Display Image on `StackPane`](#part0007.xhtml_file-chooser))
*   `ImageView` and `Image` are classes, reside in `javafx.scene.image` package, for loading and viewing images.
    (See [here](#part0007.xhtml_image-view) and section [Implement Fit Width, Fit Height and Original Size Viewing Options](#part0007.xhtml_view-option))
*   `RadioMenuItem` and `ToggleGroup`, reside in `javafx.scene.control` package, for creating mutually exclusive choices in a menu.
    (See section [Create Toggle Group, Radio Menu Items and Add Listener for `selectedToggle` Property](#part0007.xhtml_toggle-group))
*   `void bind(ObservableValue<? extends T> observable)` and `void unbind()` are methods defined in `Property` interface, reside in `javafx.beans.property` package, to create/remove a unidirectional binding for this property.
    (See section [Approach One: Bind `ImageView`'s `fitWidth`/`fitHeight` properties to scene's `width`/height properties Respectively](#part0007.xhtml_bind-unbind))
*   `DoubleBinding subtract(double` other`)` method, defined in `javafx.beans.binding.DoubleExpression` class, calculates the difference of this `NumberExpression` and the given constant value.
    (See [here](#part0007.xhtml_subtract-double))
*   `fitWidth` and `fitHeight` are properties defined in `ImageView` class, resides in `javafx.scene.image` package, for adjusting the image viewing size.
    (See sections: [Approach One: Bind `ImageView`'s `fitWidth`/`fitHeight` properties to scene's `width`/height properties Respectively](#part0007.xhtml_bind-unbind) and [Approach Two: Change Values for `fitWidth` Property and `fitHeight` Property](#part0007.xhtml_set-fit-w-h-value))

# Chapter 2
Enhanced Image Viewer with Browsing Buttons
--Developing Image Viewer V1.1

## Preface

In previous chapter, we have demonstrated the incremental development of a JavaFX application, `ImageViewer V1.0`. So far it contains minimum capabilities, nevertheless is a ready-to-use and convenient accessory, easily be bundled with a variety of software. Additional functions will be added gradually throughout this chapter and the next chapter.

This chapter features the implementation of actions as well as proper placement for two buttons, `Next` and `Previous`, two custom-made buttons to open and view the next or previous available image.

The version number is upgraded to 1.1\. From detailed descriptions and well-documented example codes excerpted from ImageViewer V1.1, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0008.xhtml_summary) section.

The complete development process of `ImageViewer V1.1` is characterized by the following steps:

*   [2.1 Add `Next` Button](#part0008.xhtml_add_next)
    *   [2.1.1 Use `Group` as Parent Container](#part0008.xhtml_group-as-container)
    *   [2.1.2 Use `Shape` Class for Rendering 2D Geometric Primitives](#part0008.xhtml_shape-class)
    *   [2.1.3 Use `Rectangle` Shape as Bounding Box of Custom-Made Button](#part0008.xhtml_rectangle-as-bounding-box)
    *   [2.1.4 Paint Background and Border of `Shape`](#part0008.xhtml_paint-shape)
    *   [2.1.5 Set Value of `arcHeight` and `arcWidth` Properties to Render Rounded Rectangle](#part0008.xhtml_arc-height-arc-width)
    *   [2.1.6 Use `Polygon` Shape as Visual Sign of `Next` Icon](#part0008.xhtml_polygon-as-icon)
    *   [2.1.7 Set Value of `Cursor` Property for `Node`](#part0008.xhtml_mouse-cursor)
    *   [2.1.8 Use Convenience Methods to Register Event Handlers to Handle Mouse Events](#part0008.xhtml_event-handler)
    *   [2.1.9 Complete Source Codes of `createNextButton()` Method](#part0008.xhtml_create-next-button-codes)
    *   [2.1.10 Install `Tooltip` for `Node`](#part0008.xhtml_tooltip)
*   [2.2 Adjust `Next` Button's Default Position in `StackPane`](#part0008.xhtml_adjust_next)
*   [2.3 Add `Previous` Button and Adjust Its Position in `StackPane`](#part0008.xhtml_add_previous)
*   [2.4 Implement On Mouse Clicked Event Handlers](#part0008.xhtml_button_clicked)
    *   [2.4.1 Configure `FileChooser`](#part0008.xhtml_configure-file-chooser)
    *   [2.4.2 Create List Iterator to Iterate Existing Files in the Current Directory](#part0008.xhtml_file-iterator)
    *   [2.4.3 Define Properties in `ImageViewer` Class](#part0008.xhtml_properties)
*   [2.5 Complete Source Codes of `Image Viewer V1.1`](#part0008.xhtml_complete-source-codes)
    *   [2.5.1 Complete Source Codes of `FileUtils` Class](#part0008.xhtml_complete-source-codes-file-utils)
    *   [2.5.2 Complete Source Codes of `ImageViewer` Class](#part0008.xhtml_complete-source-codes-image-viewer)
*   [2.6 Summary](#part0008.xhtml_summary)

## 2.1 Add `Next` Button

Instead of using `Button` class from built-in JavaFX UI controls, we implement our own utilities to design a custom-made button by employing the below classes:

*   [`Group`](#part0008.xhtml_group-as-container)

    Served as the parent container.

*   [`Shape`](#part0008.xhtml_shape-class)
    *   [`Rectangle`](#part0008.xhtml_rectangle-as-bounding-box)

        Served as the bounding box.

    *   [`Polygon`](#part0008.xhtml_polygon-as-icon)

        Served as the visual sign of `Next` icon.

*   [`LinearGradient` and `Color`](#part0008.xhtml_paint-shape)

    Paints to fill background and to stroke border.

*   [`EventHandler` and `MouseEvent`](#part0008.xhtml_event-handler)

    Used for handling mouse entering, clicking, and exiting events.

### 2.1.1 Use `Group` as Parent Container

`Group` class, resides in `javafx.scene` package, is a subclass of `javafx.scene.Parent`. The capability of `Group` is straightforward. It allows you to group various nodes together without imposing automatic layout. The following snippet of codes shows how to add nodes to a `Group`:

```
 Group buttonGroup = new Group();
Rectangle rect = new Rectangle(0, 0, 25, 35);
Polygon polygon = new Polygon();
buttonGroup.getChildren().addAll(rect, polygon);
```

Learn more about the characteristics of `Group` in Volume Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS Chapter 1 Line Drawer Section 1.1.1 Add Pane as Drawing Board in the Center of BorderPane.

### 2.1.2 Use `Shape` Class for Rendering 2D Geometric Primitives

JavaFX provides a very enticing class, `Shape`, for rendering 2D geometric primitives. It is an abstract class which extends `javafx.scene.Node` class and serves as the base class of some of basic forms of 2D geometry. Here are its direct subclasses: `Arc`, `Circle`, `CubicCurve`, `Ellipse`, `Line`, `Path`, `Polygon`, `Polyline`, `QuadCurve`, `Rectangle`, `SVGPath`, `Text`. The `Shape` class defines common properties of 2D geometric primitives, such as `fill`, `stroke`, `strokeType`, `strokeWidth`, etc.

It is very common to set value of `fill` and `stroke` properties respectively for a shape. The `setFill` method is used to specify a color to render the background of a shape, and `setStroke` method is used to specify a color to render the border of a shape. Please notice that the default value of `fill` property is `null` for `Line`, `Polyline`, and `Path`, while `Color.BLACK` for the others; and default value of `stroke` property is `Color.BLACK` for `Line`, `Polyline`, and `Path`, while `null` for the others.

Now we'll show you how to exploit capacities of `Shape` to implement our custom-made `Next` button.

### 2.1.3 Use `Rectangle` Shape as Bounding Box of Custom-Made Button

Here are codes to accomplish these: a `Rectangle` is created using the constructor with parameters: x, y, width and height, and proper value is set for each desired property.

Listing 2-1. Create a `Rectangle` and set value of these properties: `fill`, `stroke`, `arcHeight`, `arcWidth`:

```
 Rectangle rect = new Rectangle(0, 0, 25, 35);

LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
        new Stop(0, Color.web("#5173A8")),
        new Stop(0.6, Color.web("#A8B9D4")),
        new Stop(1, Color.web("#87A7C6"))});
rect.setFill(lg);
rect.setStroke(Color.web("#ACD7FF"));
rect.setArcHeight(6.5);
rect.setArcWidth(6.5);
```

The following snapshot shows the rendering of a `Rectangle` from the above codes:

Figure 2-1. Snapshot of a rounded rectangle filled with `LinearGradient` color.

![](Images/image00138.gif "rounded_rectangle")

### 2.1.4 Paint Background and Border of `Shape`

`LinearGradient` and `Color`, reside in `javafx.scene.paint` package, are two of direct subclasses of `Paint` class, the base class of colors and gradients, for painting background and border of a `Shape` or a `Region`.

In Listing 2-1. we use `LinearGradient` to fill the background of a `Rectangle`. The first 4 parameters in the constructor of `LinearGradient` specify coordinates of start point and end point for processing color gradient. The given value: 0, 0, 1, 0 means the direction of gradient is horizontal, starting from (0,0) to (1,0) relative to the top left corner of the bounding box of a node. The last parameter is an array of `Stop` objects, providing a series of colors. A `Stop` object is instantiated by given an offset value and a `Color` object. We pick 3 colors from the extent of blue hues ﹘ darker blue, bluish white and lighter blue ﹘ to render a gradient.

There are various ways to construct a `Color` object, besides the constructor below:

```
 public Color(double red, double green, double blue, double opacity) 
```

In Listing 2-1. we use `Color.web("#ACD7FF")` to paint the border of a `Rectangle`. The static method,

```
 public static Color web(java.lang.String colorString) 
```

is one of many static methods provided in `Color` class for easily creating `Color` objects. These are examples of some of the supported format for the colorString parameter, they all create the same color:

```
 "#5173A8"
   "0x5173A8"
   "rgb(81,115,168)"
```

The color string "#5173A8", or "0x5173A8" is the hex representation of RGB value (81, 115,168).

A `Color` has a default alpha value, 1.0, representing completely opaque. You can explicitly specify alpha value, in the range of 0.0 to 1.0, when constructing a `Color`. An alpha value of 0.0 means the color is completely transparent. Here are many ways to create the same color with alpha value 0.5:

```
 Color color = Color.rgb(81, 115, 168, 0.5);
Color color = Color.web("#5173A8", 0.5);
Color color = Color.web("rgba(81, 115, 168, 0.5)");
```

Learn more about the topic of color in later volumes of this book series.

### 2.1.5 Set Value of `arcHeight` and `arcWidth` Properties to Render Rounded Rectangle

`arcHeight` and `arcWidth` are properties defined in `Rectangle` class, for specifying height and width diameters of arcs at four corners of a rectangle shape. Their default value is `0.0`.

The following figure illustrates how to set correct value for `arcHeight` and `arcWidth` properties for rendering a rounded rectangles. The circles and ellipses, overlapping with the arcs at the corner of rounded rectangles, are for easy comparison.

Figure 2-2. Snapshot of illustrations of rounded rectangles with circles and ellipses placed at the corner of rectangles.

![](Images/image00139.jpeg "rectangle_examples.jpg")

### 2.1.6 Use `Polygon` Shape as Visual Sign of `Next` Icon

Instead of using image as visual sign of `Next` button, a `Polygon` of arrow shape is instantiated. The `getPoints()` method is used to obtain a list which is type of `ObservableList<Double>`, then the basic utilities, defined in `Collection` interface, is used to manipulate the content of the list. A series of x and y coordinates, stored in an array of `Double` value, are added to the list, representing points of the `Polygon`.

`Color.WHITE`, one of many static fields of type `Color`, defined in `Color` class, is the color we picked to fill the background of the `Polygon`, and a dark blue color is created, using the static method `Color.web`, to paint the border of the `Polygon`.

Here is the snippet of codes to accomplish these tasks:

Listing 2-2. Create a `Polygon` and set value for properties `fill` and `stroke`:

```
 Polygon polygon = new Polygon();
Double[] dArray = {
      5.0, 2.0,
      22.0, 17.0,
      5.0, 32.0,
      5.0, 25.0,
      14.0, 17.0,
      5.0, 9.0};
polygon.getPoints().addAll(dArray);
polygon.setFill(Color.WHITE);
polygon.setStroke(Color.web("#436B8B"));
```

The following snapshot shows the rendering of a `Polygon` from the above codes:

Figure 2-3. Snapshot of the polygon as `Next` icon.

![](Images/image00140.jpeg "next_polygon.jpg")

### 2.1.7 Set Value of `Cursor` Property for `Node`

The `cursor` property, defined in `Node` class, allows you to change mouse curser for this node and all its descendants. The `Cursor` class, resides in `javafx.scene` package and extends `java.lang.Object`, defines some applicable mouse cursors as static fields of `Cursor` type such as `CLOSED_HAND`, `CROSSHAIR`, `DEFAULT`, `HAND`, `OPEN_HAND`, `TEXT`, `WAIT`, etc. If value of `cursor` property is not explicitly set, the default mouse cursor, an arrow shape, is used.

We employ `Cursor.OPEN_HAND` as mouse curser of a `Next` button. Here's the snippet of codes:

```
 Group buttonGroup = new Group();
buttonGroup.setCursor(Cursor.OPEN_HAND);
```

### 2.1.8 Use Convenience Methods to Register Event Handlers to Handle Mouse Events

`EventHandler<T extends Event>` is an interface which extends `java.util.EventListener`, and defines a `handle`(`T` event) method to be invoked when a specified event happens.

We'll use convenience methods provided in `Node` class to register event handlers to handle event types of mouse events such as `MOUSE_CLICKED`, `MOUSE_ENTERED` and `MOUSE_EXITED`, these are some of static fields of `EventType`s defined in `MouseEvent` class, a subclass of `javafx.scene.input.InputEvent`.

Here are convenience methods used to register event handlers for the mentioned events:

*   `public final void setOnMouseClicked(EventHandler<? super MouseEvent>` value`)`

    Set value of `OnMouseClicked` property defined in `Node` class, providing an implementation of `handle` method, which is called when mouse clicked on this node.

*   `public final void setOnMouseEntered(EventHandler<? super MouseEvent>` value`)`

    Set value of `OnMouseEntered` property defined in `Node` class, providing an implementation of `handle` method, which is called when mouse entered this node.

*   `public final void setOnMouseExited(EventHandler<? super MouseEvent>` value`)`

    Set value of `OnMouseExited` property defined in `Node` class. providing an implementation of `handle` method, which is called when mouse exited this node.

Here are snippets of codes show usages of these convenience methods:

Listing 2-3. Register event handlers using convenience methods:

```
 // Register mouse clicked event handler
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse clicked");
      }
    });

    // Register mouse entered event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse entered");
        rect.setFill(lgEntered);
        polygon.setFill(Color.web("#436B8B"));
        polygon.setStroke(Color.WHITE);
      }
    });

    // Register mouse exited event handler
    // Recover to original appearance when mouse exited
    buttonGroup.setOnMouseExited(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse exited");
        rect.setFill(lg);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));
      }
    }); 
```

### 2.1.9 Complete Source Codes of `createNextButton()` Method

Import Statements:

```
 import javafx.scene.Cursor;
import javafx.scene.Group;
import javafx.scene.Node;
import javafx.scene.control.Tooltip;
import javafx.scene.input.MouseEvent;
import javafx.scene.paint.Color;
import javafx.scene.paint.CycleMethod;
import javafx.scene.paint.LinearGradient;
import javafx.scene.paint.Stop;
import javafx.scene.shape.Polygon;
import javafx.scene.shape.Rectangle;
```

Listing 2-4. Define `createNextButton()` method:

```
 /**
   * Create next button using a Rectangle as background,
   * a Polygon as icon, a Group as container,
   * size of Rectangle is 25 by 35,
   * thickness of polygon is 8 pixels,
   * padding of polygon is (2, 2, 2, 5),
   * change rectangle appearance when mouse entered.
   * 
   * @return 
   */
  Node createNextButton() {

    // Create a group as button
    Group buttonGroup = new Group();

    // Create a rectangle shape as background
    final Rectangle rect = new Rectangle(0, 0, 25, 35);

    // Look and feel of the rectangle
    final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
        new Stop(0, Color.web("#5173A8")),
        new Stop(0.6, Color.web("#A8B9D4")),
        new Stop(1, Color.web("#87A7C6"))});
    rect.setFill(lg);
    rect.setStroke(Color.web("#ACD7FF"));
    rect.setArcHeight(6.5);
    rect.setArcWidth(6.5);

    // Look and feel when mouse entered the button
    final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
        new Stop(0, Color.web("#87A7C6")),
        new Stop(0.4, Color.web("#A8B9D4")),
        new Stop(1, Color.web("#5173A8"))});

    // Create a polygon shape representing visual sign of Next icon
    // 8 pixel thickness, insets is 2, 2, 2, 5
    final Polygon polygon = new Polygon();
    Double[] dArray = {
      5.0, 2.0,
      22.0, 17.0,
      5.0, 32.0,
      5.0, 25.0,
      14.0, 17.0,
      5.0, 9.0};
    polygon.getPoints().addAll(dArray);
    polygon.setFill(Color.WHITE);
    polygon.setStroke(Color.web("#436B8B"));

    // Set cursor
    buttonGroup.setCursor(Cursor.OPEN_HAND);

    // Register mouse clicked event handler
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse clicked");
      }
    });

    // Register mouse entered event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse entered");
        rect.setFill(lgEntered);
        polygon.setFill(Color.web("#436B8B"));
        polygon.setStroke(Color.WHITE);
      }
    });

    // Register mouse exited event handler
    // Recover to original appearance when mouse exited
    buttonGroup.setOnMouseExited(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse exited");
        rect.setFill(lg);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));
      }
    });

    buttonGroup.getChildren().addAll(rect, polygon);
    return buttonGroup;
  }
```

### 2.1.10 Install `Tooltip` for `Node`

`Tooltip` class, resides in `javafx.scene.control` package and extends `javafx.scene.control.PopupControl` class, is one of fundamental UI components for showing help information about a node when mouse hovers on it.

If a node is one of UI controls such as a `Button`, then you can set value of `tooltip` property, defined in `javafx.scene.control.Control` class, for the node. Here's the `setTooltip` method:

```
 public final void setTooltip(Tooltip value) 
```

Since the `Next` button is a custom-made node acting like a button, not derived from `javafx.scene.control.Control` class, we'll use `install` method, provided in `Tooltip` class, to associate a `Tooltip` with the `Next` button. Here's the `install` method:

```
 public static void install(Node node, Tooltip t) 
```

The following snippets of codes show the creation of a `Next` node by calling `createNextButton()` method, install a `Tooltip` for the node, and add it to the children list of a `StackPane` which is the image rendering area.

Import Statement:

```
 import javafx.scene.control.Tooltip;
```

Listing 2-5. Create a `Next` button, install a `Tooltip` and add the node to image rendering area:

```
 final Node nextButton = createNextButton();

...

// Install tooltip
Tooltip t = new Tooltip("Next Image");
Tooltip.install(nextButton, t);
// Add next button to stack pane
imageArea.getChildren().add(nextButton);
```

The following snapshots show a `Next` button laid out in its default location, the center of a `StackPane`.

Figure 2-4. Snapshot of a `Next` button placed in the default position.

![](Images/image00141.gif "next_button_center1.gif")

Figure 2-5. Snapshot of a `Next` button placed in the default position, it is taken as mouse entered the button, the filled color gradient of a rectangle is changed and the installed tooltip is popped up.

![](Images/image00142.gif "next_button_center2.gif")

(Figures 2-1 to 2-5 are snapshots of applications using jdk1.7.0_25 in Windows XP; the rest are using jdk1.8.0_66 in Windows 8.1)

## 2.2 Adjust `Next` Button's Default Position in `StackPane`

In this section, we will demonstrate how to place a child node of a `StackPane` in the desired location.

A `StackPane` places all its children in a stack with the center as default alignment. That is, by default StackPane's children overlap each other in the center of the pane.

Placing a `Next` button in the center of a `StackPane` is not feasible in our application. Fortunately, `StackPane` provides two static methods:

```
 public static void setAlignment(Node child, Pos value)
public static void setMargin(Node child, Insets value)
```

allowing us to adjust individual child node's position. The preferred position of a `Next` button is on the right side of the window, within the visible boundary of a scene. The following snippets of codes adjust the default location of a next button.

Import Statement:

```
 import javafx.geometry.Insets;
import javafx.geometry.Pos;
```

Listing 2-6. Use `StackPane`'s static Methods `setAlignment` and `setMargin` to adjust the default position of a `Next` button:

```
 StackPane.setAlignment(nextButton, Pos.CENTER_RIGHT);
  StackPane.setMargin(nextButton, new Insets(8));
```

The following snapshot shows a `Next` button positioned on the right side of application window.

Figure 2-6. Snapshot of a `Next` button on the right side of window, within the visible boundary of a scene.

![next_button_right.jpg](Images/image00143.jpeg "next_button_right.gif")

Remember that, we set minimum size of `StakePane` to (0, 0) to avoid the automatic changing of its size, by its child node `ImageView`. Failure to do so may lead to complex situation regarding the position of `Next` button whenever an image larger than the visible boundary of the `StackPane` is loaded and displayed. The setting simplifies the solution of adjusting the position of `Next` button.

The next snapshot shows a large size image displayed by its original size, the portions of image that exceed the boundary of `StakePane` are invisible. Had we not set minimum size for the `StakePane`, then its size would have been enlarged by its contents, and the `Next` button would have been fallen beyond the visible boundary.

Figure 2-7. Snapshot of `Next` button positioned on the right side of window after dynamically resizing the application window.

![](Images/image00144.jpeg "next_button_adjust.jpg")

## 2.3 Add `Previous` Button and Adjust Its Position in `StackPane`

In this section, a `Previous` button is added and placed on the left side of the `StakePane`. The alignment is set to `Pos.CENTER_LEFT`, and the left margin is set to 8 pixels. The procedures are similar to how we create the `Next` button and adjust its position described in previous sections.

Listing 2-7. Define `createPrevButton` method to create a `Previous` button:

```
 /**
   * Create previous button using a Rectangle as background,
   * a Polygon as icon, a Group as container,
   * size of Rectangle is 25 by 35,
   * thickness of polygon is 8 pixels,
   * padding of polygon is (2, 5, 2, 5),
   * change rectangle appearance when mouse entered.
   * 
   * @return 
   */
  Node createPrevButton() {

    // Create a group as button
    Group buttonGroup = new Group();

    // Create a rectangle shape as background
    final Rectangle rect = new Rectangle(0, 0, 25, 35);

    // Look and feel of the rectangle
    final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
      new Stop(0, Color.web("#87A7C6")),
      new Stop(0.4, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#5173A8"))});
    rect.setFill(lg);
    rect.setStroke(Color.web("#ACD7FF"));
    rect.setArcHeight(6.5);
    rect.setArcWidth(6.5);

    // Look and feel when mouse entered the button
    final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
      new Stop(0, Color.web("#5173A8")),
      new Stop(0.6, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#87A7C6"))});

    // Create a polygon shape representing visual sign of Next icon
    // 8 pixel thickness, insets is 2, 2, 2, 5
    final Polygon polygon = new Polygon();
    Double[] dArray = {
      19.0, 2.0,
      2.0, 17.0,
      19.0, 32.0,
      19.0, 25.0,
      10.0, 17.0,
      19.0, 9.0};
    polygon.getPoints().addAll(dArray);
    polygon.setFill(Color.WHITE);
    polygon.setStroke(Color.web("#436B8B"));

    // Set cursor
    buttonGroup.setCursor(Cursor.OPEN_HAND);

    // Register mouse clicked event handler
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse clicked");
      }
    });

    // Register mouse entered event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse entered");
        rect.setFill(lgEntered);
        polygon.setFill(Color.web("#436B8B"));
        polygon.setStroke(Color.WHITE);
      }
    });

    // Register mouse exited event handler
    // Recover to original appearance when mouse exited
    buttonGroup.setOnMouseExited(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse exited");
        rect.setFill(lg);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));
      }
    });

    buttonGroup.getChildren().addAll(rect, polygon);
    return buttonGroup;
  }
```

Newly added codes for creating `Previous` button are shown in bold face in the following snippets of codes.

Listing 2-8. Codes added to the entry point of `ImageViewer V1.1` for creating `Previous` button:

```
 final Node nextButton = createNextButton();
  final Node prevButton = createPrevButton();

    ...

  public void start(final Stage stage) {

      ...

    // Install tooltip for nextButton
    Tooltip t = new Tooltip("Next Image");
    Tooltip.install(nextButton, t);

    // Install tooltip for prevButton
    Tooltip t2 = new Tooltip("Previous Image");
    Tooltip.install(prevButton, t2);

    // Adjust next button's position to the right side of StackPane
    StackPane.setAlignment(nextButton, Pos.CENTER_RIGHT);
    StackPane.setMargin(nextButton, new Insets(8));

    // Adjust previous button's position to the right side of StackPane
    StackPane.setAlignment(prevButton, Pos.CENTER_LEFT);
    StackPane.setMargin(prevButton, new Insets(8));

    // Add next button and previous button to stack pane
    imageArea.getChildren().addAll(nextButton, prevButton);

      ...

  }
```

Figure 2-8. Snapshot of ImageViewer with `Next` button and `Previous` button, positioned within the visible boundary of a `StackPane`

![](Images/image00145.jpeg "next_prev_buttons.jpg")

## 2.4 Implement On Mouse Clicked Event Handlers

In section [Use Convenience Methods to Register Event Handlers to Handle Mouse Events](#part0008.xhtml_convenience-methods-mouse-event), we have demonstrated how to register an event handler for mouse clicked events. In this section, we'll register the event handlers and implement the `handle` methods which are invoked when mouse clicked on the buttons. If `Next` button is clicked, the image file next to the current loaded file will be loaded, and if `Previous` button is clicked, the image file before the current loaded file will be loaded.

Before we proceed these tasks properly, we'll configure a `FileChooser` to show only files whose extensions matching the specified filters, and establish a list of files existing in the current directory, the list is created whenever an image file is opened from the File Open Dialog of a `FileChooser`.

### 2.4.1 Configure `FileChooser`

To configure a `FileChooser`, we use `FileChooser.ExtensionFilter` class to define file extension filters to show files with the following extensions: "*.bmp", "*.gif", "*.jpeg", "*.jpg", "*.png".

The `getExtensionFilters` method provided in `FileChooser` class is called to obtain a list of type `ObservableList<FileChooser.ExtensionFilter>`, then using the `addAll` method to add as many filters as needed. We define a `FileUtils` class to tackle the problem. Codes are as follows:

Listing 2-9. Define `FileUtils` class, providing a static method `configure` to add file extension filters for a given `FileChooser`:

```
 package imageviewer;

import javafx.stage.FileChooser;

/**
 * File Name: FileUtils.java
 * (in directory: ImageViewer1.1/src/example4/imageviewer/)
 *
 * @author Shufen Kuo
 */

public class FileUtils {

  /**
   * Define file extension filters to filtering supported image files,
   * matching files whose extensions are:
   * .bmp, .gif, .jpeg, .jpg and .png
   * @param fileChooser 
   */
  static void configure(FileChooser fileChooser) {
    fileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("All Images",
          "*.bmp", "*.gif", "*.jpeg", "*.jpg", "*.png"),
        new FileChooser.ExtensionFilter("All Files", "*.*"),
        new FileChooser.ExtensionFilter("BMP", "*.bmp"),
        new FileChooser.ExtensionFilter("GIF", "*.gif"),
        new FileChooser.ExtensionFilter("JPEG", "*.jpeg"),
        new FileChooser.ExtensionFilter("JPG", "*.jpg"),
        new FileChooser.ExtensionFilter("PNG", "*.png"));    
    // Set "." as default dir
    fileChooser.setInitialDirectory(new File("."));
  }  
}
```

The constructor of `FileChooser.ExtensionFilter` we use in above codes takes two parameters, the first one is the description to be shown in the field `"Files of types:"` when a File Open Dialog is popped up, the second one is a variable length parameter of `String` type, each specified a string in compliance with syntax of regular expressions.

Inside the `FileUtils.configure` method, besides adding file extension filters, we also set current directory as initial directory:

fileChooser.setInitialDirectory(new File("."));

The `configure` method, a static method defined in the `FileUtils` class, is called from here:

```
 // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");
    FileUtils.configure(fileChooser);
```

The functionality of a `FileChooser` and its appearance depend on the operation system. Figure 2-9 shows a `FileChooser` in Windows XP, and Figure 2-10 shows a `FileChooser` in Windows 8.1.

Figure 2-9. Snapshot of a File Open Dialog (in Windows XP), the first filter added in the list of extension filters, `"All Images"`, is shown in the field `"Files of types:"` when the ComboBox is clicked.

![](Images/image00146.jpeg "file_chooser_filter.jpg")

Figure 2-10. Snapshot of a File Open Dialog (in Windows 8.1), the name `"GIF"`, which is associated with regular expression "*.gif" in the codes, is shown in the field follows the file name when the item is clicked.

![](Images/image00147.gif "file_chooser_filter_win81.gif")

Generally, the application's users would appreciate a `FileChooser` remembers its last visited directory. Here's how to do this:

Listing 2-10. Set last visited directory as initial directory of `FileChooser` inside the `handle` method of event handler registered for `Load` menu item:

```
 // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          // Set last visited dir as initial directory
         File lastDir = file.getParentFile();
         fileChooser.setInitialDirectory(lastDir);
          String url = file.toURI().toString();
          Image image = new Image(url);
          imageView.setImage(image);
        }
      }
    });
```

### 2.4.2 Create List Iterator to Iterate Existing Files in the Current Directory

To establish a list of files exists in the current directory whenever an image file is opened from a File Open Dialog, we'll use API's provided in `java.nio.file` package which is introduced in the JDK 7 release.

The following static method provided in `java.nio.file.Files` class,

```
static DirectoryStream<Path> newDirectoryStream(Path dir, String glob) 
```

opens a given directory, returning a `DirectoryStream<Path>`. The type `DirectoryStream` is an interface which extends `iterable`, thus can be applied with the for-each syntax to iterate files in a directory.

Here's the snippet of codes to read a directory and add file one by one to a list:

```
 List<Path> list = new ArrayList<>();

    try (DirectoryStream<Path> stream = Files.newDirectoryStream(dir,
        "*.{bmp,gif,jpeg,jpg,png}")) {
      for (Path entry : stream) {
        // ignore subdir inside dir
        if (Files.isDirectory(entry, LinkOption.NOFOLLOW_LINKS))
          continue;
        list.add(entry);
      }
    } catch (DirectoryIteratorException de) {
      throw de.getCause();
    }
```

The followings are the complete codes of the static method `listIterator` which reads a directory, adds file one by one to a `List`, sort files in alphabetical order, and return a `ListIterator` that points to the next available file in the directory. The method is defined in `FileUtils` class.

Import Statements:

```
 import java.io.IOException;
import java.nio.file.DirectoryIteratorException;
import java.nio.file.DirectoryStream;
import java.nio.file.Files;
import java.nio.file.LinkOption;
import java.nio.file.Path;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
import java.util.ListIterator;
import javafx.stage.FileChooser;
```

Listing 2-11. The static method `listIterator` defined in `FileUtils` class, reads a directory, adds file one by one to list, sorts the list, and returns an instance of `ListIterator`:

```
 /**
   * Using Files.newDirectoryStream(Path, String) to read directory,
   * add files to a list, return the listIteratior that points to
   * the file specified in argument, that is, the first call of next()
   * returns the specified file,
   * the file list is sorted in alphabetical order,
   * the second argument in newDirectoryStreamis method is
   * glob pattern for filtering files matching the pattern:
   *   "*.{bmp,gif,jpeg,jpg,png}",
   * we are only interested in files ending with:
   *  .bmp, .gif, .jpeg, .jpg and .png.
   * 
   * @param file
   * @return
   * @throws IOException 
   */
  static ListIterator<Path> listIterator(Path file) throws IOException {
    Path dir = file.getParent();
    List<Path> list = new ArrayList<>();

    try (DirectoryStream<Path> stream = Files.newDirectoryStream(dir,
        "*.{bmp,gif,jpeg,jpg,png}")) {
      for (Path entry : stream) {
        // ignore subdir inside dir
        if (Files.isDirectory(entry, LinkOption.NOFOLLOW_LINKS))
          continue;
        list.add(entry);
      }
    } catch (DirectoryIteratorException de) {
      throw de.getCause();
    }

    // compareTo method in Path compares two abstract paths lexicographically.
    Collections.sort(list, new Comparator<Path>() {
      public int compare(Path o1, Path o2) {
        return o1.getFileName().compareTo(o2.getFileName());
      }
    });

    int index = 0; // index in the list for current file
    // Search index for selected file
    for (Path entry : list) {
       if (entry.equals(file)) break;
       index++;
    }
    if (index == list.size()) {
      // file not in the list
      index = 0;
    } 
    return list.listIterator(index); 
  }
```

We will describe usage of the `FileUtils.listIterator(Path` file`)` method in the following section.

### 2.4.3 Define Properties in `ImageViewer` Class

In this section we'll demonstrate how to define properties in a class. In the entry point of the application, `ImageViewer` class, we define three properties as follows:

`listIterator`

This is type of `ObjectProperty<ListIterator<Path>>`. The `listIterator(Path` file`)` method, a static method defined in `FileUtils` class, is called from the action handler of `Load` menu item to get an instance of `ListIterator` and to set as the value of this property.

`lastClickedButton`

This is type of `StringProperty` for keeping track of last clicked button so that we can properly move the cursor of a `ListIterator` specified in `listIterator` property. You'll see how the value of `lastClickedButton` property, either `NEXT` or `PREVIOUS`, effecting the calls of `next()` method and `previous()` method within mouse clicked event handlers registered for `Next` button and `Previous` button.

`curImage`

This is type of `ObjectProperty<Image>` and binds to `image` property of an `ImageView`, the value of the property is the current loaded image.

Here's the snippet of codes defines these properties:

Listing 2-12. Define properties in `ImageViewer` Class:

```
 // For traverse files in current selected directory
  final ObjectProperty<ListIterator<java.nio.file.Path>> listIterator =
      new SimpleObjectProperty<>();

  final String NEXT = "NEXT";
  final String PREVIOUS = "PREVIOUS";
  // For keep track of last clicked button
  final StringProperty lastClickedButton = new SimpleStringProperty();

  final ObjectProperty<Image> curImage = new SimpleObjectProperty<>();
```

Properties usually work in connection with binding mechanism. This is the `bind` method defined in `Property<T>` interface,

```
 void bind(ObservableValue<? extends T> observable)
```

to create a unidirectional binding for this property. The parameter `observable` is type of `ObservableValue`. Both `ObjectProperty` and `StringProperty` implement `Property`, a subinterface of `ObservableValue`.

Here's the snippet of codes to create a binding for `image` property of an `ImageView` using the `bind` method:

Listing 2-13. Bind `image` property of an `ImageView` to `curImage` property:

```
 final ImageView imageView = new ImageView();
    imageView.imageProperty().bind(curImage);
```

Once the binding is created, then whenever the value of `curImage` property is changed, the value of `image` property in `ImageView` is changed as well.

The `set` method or the `setValue` method can be used to set value for properties. Here's the snippet of codes excerpted from the `handle` method within an event handler registered to handle `ActionEvent` of `Load` menu item:

Listing 2-14. Set values to `listIterator` property, `curImage` property and `lastClickedButton` property :

```
 ListIterator<java.nio.file.Path> it = FileUtils.listIterator(file.toPath());
            listIterator.set(it);
            file = it.next().toFile();
            String url = file.toURI().toString();          
            curImage.set(new Image(url));
            lastClickedButton.setValue(NEXT);
```

Please notice that the value of `curImage` property is set when one of the following actions occurs:

*   Loading a selected image from a File Open Dialog of `FileChooser`.
*   Loading the next image when `Next` button is clicked.
*   Loading the previous image when `Previous` button is clicked.

As we mentioned above, once the value of `curImage` property is changed, the value of `image` property of `ImageView` is changed as well.

The changes of codes made in `ImageViewer` class, the entry point of application, are shown in bold face as follows:

Import Statements:

```
 import java.io.IOException;
import java.util.ListIterator;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
```

Listing 2-15. Codes added to `ImageViewer` class, the entry point of application, shown in bold face:

```
 public class ImageViewer extends Application {

      ...

  // For traverse files in current selected directory
  final ObjectProperty<ListIterator<java.nio.file.Path>> listIterator =
      new SimpleObjectProperty<>();

  final String NEXT = "NEXT";
  final String PREVIOUS = "PREVIOUS";
  // For keep track of last clicked button
  final StringProperty lastClickedButton = new SimpleStringProperty();

  final ObjectProperty<Image> curImage = new SimpleObjectProperty<>();

      ...

  @Override
  public void start(final Stage stage) {

      ...

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageView.imageProperty().bind(curImage);
    imageView.setPreserveRatio(true);
    imageArea.getChildren().add(imageView);

      ...

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          // Set last visited dir as initial directory
          File lastDir = file.getParentFile();
          fileChooser.setInitialDirectory(lastDir);
          // Create a list iterator when a file is opened from File Chooser
          try {
            ListIterator<java.nio.file.Path> it = FileUtils.listIterator(file.toPath());
            listIterator.set(it);
            file = it.next().toFile();
            String url = file.toURI().toString();          
            curImage.set(new Image(url));
            // Set to NEXT because the cursor in iterator is pointing to 
            // the next available file
            lastClickedButton.setValue(NEXT);
          } catch (IOException ex) {} 
        }
      }
    }); 
```

Listing 2-16. Codes of mouse clicked event handler for `Next` button becomes:

```
 Node createNextButton() {
    // Create a group as button
    Group buttonGroup = new Group();

    ...

    // Register mouse clicked event handler for nextButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasNext()) {
          java.nio.file.Path path = iterator.next();
          if (lastClickedButton.get().equals(PREVIOUS)) {
            // If last clicked button is prevButton
            // the first call of next() is the current image, 
            // must move cursor one step forward.
            if (iterator.hasNext())
              path = iterator.next();
            else
              return;
          }
          System.out.format("Next button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          lastClickedButton.set(NEXT);
        }
      }
    });

    ...
}
```

Listing 2-17. Codes of mouse clicked event handler for `Previous` button becomes:

```
 Node createPrevButton() {
    // Create a group as button
    Group buttonGroup = new Group();

    ...

    // Register mouse clicked event handler for prevButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get list iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasPrevious()) {
          java.nio.file.Path path = iterator.previous();
          if (lastClickedButton.get().equals(NEXT)) {
            // If the last clicked button is nextButton
            // the first call of previous() is the current image,
            // must move cursor one step backward
            if (iterator.hasPrevious())
              path = iterator.previous();
            else
              return;
          }
          System.out.format("Prev button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          lastClickedButton.set(PREVIOUS);
        }
      }
    });

    ...
}
```

## 2.5 Complete Source Codes of `Image Viewer V1.1`

### 2.5.1 Complete Source Codes of `FileUtils` Class

Listing 2-18. Complete source codes of `FileUtils` class:

```
 package imageviewer;

import java.io.File;
import java.io.IOException;
import java.nio.file.DirectoryIteratorException;
import java.nio.file.DirectoryStream;
import java.nio.file.Files;
import java.nio.file.LinkOption;
import java.nio.file.Path;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
import java.util.ListIterator;
import javafx.stage.FileChooser;

/**
 * File Name: FileUtils.java
 * (in directory: ImageViewer1.1/src/example4/imageviewer/)
 *
 * @author Shufen Kuo
 */

public class FileUtils {

  /**
   * Define file extension filters to filtering supported image files,
   * matching files whose extensions are:
   * .bmp, .gif, .jpeg, .jpg and .png
   * @param fileChooser 
   */
  static void configure(FileChooser fileChooser) {
    fileChooser.getExtensionFilters().addAll(
        new FileChooser.ExtensionFilter("All Images",
          "*.bmp", "*.gif", "*.jpeg", "*.jpg", "*.png"),
        new FileChooser.ExtensionFilter("All Files", "*.*"),
        new FileChooser.ExtensionFilter("BMP", "*.bmp"),
        new FileChooser.ExtensionFilter("GIF", "*.gif"),
        new FileChooser.ExtensionFilter("JPEG", "*.jpeg"),
        new FileChooser.ExtensionFilter("JPG", "*.jpg"),
        new FileChooser.ExtensionFilter("PNG", "*.png"));    
    // Set "." as default dir
    fileChooser.setInitialDirectory(new File("."));
  }

  /**
   * Using Files.newDirectoryStream(Path, String) to read directory,
   * add files to a list, return the listIteratior that points to
   * the file specified in argument, that is, the first call of next()
   * returns the specified file,
   * the file list is sorted in alphabetical order,
   * the second argument in newDirectoryStreamis method is
   * glob pattern for filtering files matching the pattern:
   *   "*.{bmp,gif,jpeg,jpg,png}",
   * we are only interested in files ending with:
   *  .bmp, .gif, .jpeg, .jpg and .png.
   * 
   * @param file
   * @return
   * @throws IOException 
   */
  static ListIterator<Path> listIterator(Path file) throws IOException {
    Path dir = file.getParent();
    List<Path> list = new ArrayList<>();

    try (DirectoryStream<Path> stream = Files.newDirectoryStream(dir,
        "*.{bmp,gif,jpeg,jpg,png}")) {
      for (Path entry : stream) {
        // ignore subdir inside dir
        if (Files.isDirectory(entry, LinkOption.NOFOLLOW_LINKS))
          continue;
        list.add(entry);
      }
    } catch (DirectoryIteratorException de) {
      throw de.getCause();
    }

    // compareTo method in Path compares two abstract paths lexicographically.
    Collections.sort(list, new Comparator<Path>() {
      public int compare(Path o1, Path o2) {
        return o1.getFileName().compareTo(o2.getFileName());
      }
    });

    int index = 0; // index in the list for current file
    // Search index for selected file
    for (Path entry : list) {
       if (entry.equals(file)) break;
       index++;
    }
    if (index == list.size()) {
      // file not in the list
      index = 0;
    } 
    return list.listIterator(index); 
  }
}
```

### 2.5.2 Complete Source Codes of `ImageViewer` Class

Listing 2-19. Complete source codes of `ImageViewer` class:

```
 package imageviewer;

import java.io.File;
import java.io.IOException;
import java.util.ListIterator;
import javafx.application.Application;
import javafx.application.Platform; 
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Insets;
import javafx.geometry.Pos;
import javafx.scene.Cursor;
import javafx.scene.Group;
import javafx.scene.Node;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.control.Tooltip;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.paint.CycleMethod;
import javafx.scene.paint.LinearGradient;
import javafx.scene.paint.Stop;
import javafx.scene.shape.Polygon;
import javafx.scene.shape.Rectangle;
import javafx.stage.FileChooser;
import javafx.stage.Stage;

/**
 * File Name: ImageViewer.java V1.1
 * (in directory: ImageViewer1.1/src/example4/imageviewer/)
 * This application creates a BorderPane as root node of a scene, and
 * add a StackPane in the center of BorderPane
 * The initial size of the scene is set to 600 by 400
 * The size of StackPane will be automatically set to fit the size of scene.
 * StackPane will be resized when window size is adjusted by a user
 *
 * Add a menu bar in the top of BorderPane
 * Create File Menu, and using FileChooser's Open Dialog to
 * select an image file, load and display the image in image rendering area.
 * 
 * Create Option menu contains View submenu, let a user chooses image viewing
 * criteria: Fit Width, Fit Height, or the default option Original Size.
 *
 * Adjust image viewing size using bind and unbind methods:
 * Bind fitWidth/fitHeight properties of an image view to
 * width/height properties of a scene,
 * so that, size of the image view will be changed automatically
 * whenever the scene is resized. 
 * 
 * Add Next and Previous buttons to a scene, then
 * after the first image is loaded, a user can use these buttons to
 * view next or preview image without opening FileChoose again.
 * 
 * Adjust Next button's default position in StackPane
 *
 * Add Previous button and adjust its position in a StackPane
 *
 * Implement on mouse clicked event Handlers for Next and Previous buttons
 *
 * @author Shufen Kuo
 */

public class ImageViewer extends Application {
  final Node nextButton = createNextButton();
  final Node prevButton = createPrevButton();

  // Create toggle group
  final ToggleGroup groupOption = new ToggleGroup();
  final String FIT_WIDTH = "Fit Width";
  final String FIT_HEIGHT = "Fit Height";
  final String ORIGINAL_SIZE = "Original Size";

  // For traverse files in current selected directory
  final ObjectProperty<ListIterator<java.nio.file.Path>> listIterator =
      new SimpleObjectProperty<>();

  final String NEXT = "NEXT";
  final String PREVIOUS = "PREVIOUS";
  // For keep track of last clicked button
  final StringProperty lastClickedButton = new SimpleStringProperty();

  final ObjectProperty<Image> curImage = new SimpleObjectProperty<>();

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    final StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageView.imageProperty().bind(curImage);
    imageView.setPreserveRatio(true);
    imageArea.getChildren().add(imageView);

    final Scene scene = new Scene(rootPane, 600, 400);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });

    // Add menu bar
    final MenuBar menuBar = new MenuBar();
    Menu menuFile = new Menu("File");
    MenuItem load = new MenuItem("Load");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(load, exit);
    menuBar.getMenus().add(menuFile);
    rootPane.setTop(menuBar);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });

    // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");
    FileUtils.configure(fileChooser);

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          // Set last visited dir as initial directory
          File lastDir = file.getParentFile();
          fileChooser.setInitialDirectory(lastDir);
          // Create a list iterator when a file is opened from File Chooser
          try {
            ListIterator<java.nio.file.Path> it =
                FileUtils.listIterator(file.toPath());
            listIterator.set(it);
            file = it.next().toFile();
            String url = file.toURI().toString();          
            curImage.set(new Image(url));
            // Set to NEXT because the cursor in iterator is pointing to 
            // the next available file
            lastClickedButton.setValue(NEXT);
          } catch (IOException ex) {}
        }
      }
    });

    // Create Option menu
    Menu menuOption = new Menu("Option");

    // Create radio menu items
    final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
    fitWidth.setToggleGroup(groupOption);
    final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
    fitHeight.setToggleGroup(groupOption);
    final RadioMenuItem original = new RadioMenuItem("Original Size");
    original.setToggleGroup(groupOption);

    // Listen to the change of selection in the toggle group
    groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
        if (groupOption.getSelectedToggle() != null) {
          RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
          if (choiceItem == fitWidth) {
            System.out.println("fitwidth");
            imageView.fitWidthProperty().bind(scene.widthProperty());
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height to 0
            imageView.setFitHeight(0);
          } else if (choiceItem == fitHeight) {
            System.out.println("fitheight");
            // Available height for rendering image is
            // subtract menubar's height from scene height
            imageView.fitHeightProperty().bind(
                scene.heightProperty().subtract(menuBar.getHeight()));
            imageView.fitWidthProperty().unbind();
            // Besides unbind, must also set fit width to 0 
            imageView.setFitWidth(0);
          } else {
            System.out.println("original size");
            imageView.fitWidthProperty().unbind();
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height/height to 0
            imageView.setFitWidth(0);
            imageView.setFitHeight(0);
          }
        }
      }
    });

    // Create View submenu for Option menu
    Menu menuView = new Menu("View");
    menuView.getItems().addAll(fitWidth, fitHeight, original);

    // Set Original Size as default choice
    original.setSelected(true);

    // Add option menu to menu bar
    menuOption.getItems().add(menuView);
    menuBar.getMenus().add(menuOption);

    // Install tooltip
    Tooltip t = new Tooltip("Next Image");
    Tooltip.install(nextButton, t);

    // Install tooltip for prevButton
    Tooltip t2 = new Tooltip("Previous Image");
    Tooltip.install(prevButton, t2);

    // Adjust next button's position to the right side of StackPane
    StackPane.setAlignment(nextButton, Pos.CENTER_RIGHT);
    StackPane.setMargin(nextButton, new Insets(8));

    // Adjust previous button's position to the right side of StackPane
    StackPane.setAlignment(prevButton, Pos.CENTER_LEFT);
    StackPane.setMargin(prevButton, new Insets(8));

    // Add next button and previous button to stack pane
    imageArea.getChildren().addAll(nextButton, prevButton);

    // Listen to the width change of scene
    scene.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("Scene width changed from %.1f to %.1f%n",
            (double) oldVal, (double) newVal);
      }
    });

    // Listen to the height change of scene   
    scene.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("Scene height changed from %.1f to %.1f%n",
            (double) oldVal, (double) newVal);
      }
    });

    stage.setTitle("ImageViewer V1.1");
    stage.setScene(scene);
    stage.show();
  }

  /**
   * Create next button using a Rectangle as background,
   * a Polygon as icon, a Group as container,
   * size of Rectangle is 25 by 35,
   * thickness of polygon is 8 pixels,
   * padding of polygon is (2, 2, 2, 5),
   * change rectangle appearance when mouse entered.
   *
   * @return
   */
  Node createNextButton() {

    // Create a group as button
    Group buttonGroup = new Group();

    // Create a rectangle shape as background
    final Rectangle rect = new Rectangle(0, 0, 25, 35);

    // Look and feel of the rectangle
    final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[]{
      new Stop(0, Color.web("#5173A8")),
      new Stop(0.6, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#87A7C6"))});
    rect.setFill(lg);
    rect.setStroke(Color.web("#ACD7FF"));
    rect.setArcHeight(6.5);
    rect.setArcWidth(6.5);

    // Look and feel when mouse entered the button
    final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[]{
      new Stop(0, Color.web("#87A7C6")),
      new Stop(0.4, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#5173A8"))});

    // Create a polygon shape representing visual sign of Next icon
    // 8 pixel thickness, insets is 2, 2, 2, 5
    final Polygon polygon = new Polygon();
    Double[] dArray = {
      5.0, 2.0,
      22.0, 17.0,
      5.0, 32.0,
      5.0, 25.0,
      14.0, 17.0,
      5.0, 9.0};
    polygon.getPoints().addAll(dArray);
    polygon.setFill(Color.WHITE);
    polygon.setStroke(Color.web("#436B8B"));

    // Set cursor
    buttonGroup.setCursor(Cursor.OPEN_HAND);

    // Register mouse clicked event handler for nextButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasNext()) {
          java.nio.file.Path path = iterator.next();
          if (lastClickedButton.get().equals(PREVIOUS)) {
            // If last clicked button is prevButton
            // the first call of next() is the current image, 
            // must move cursor one step forward.
            if (iterator.hasNext())
              path = iterator.next();
            else
              return;
          }
          System.out.format("Next button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          lastClickedButton.set(NEXT);
        }
      }
    });

    // Register mouse entered event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse entered");
        rect.setFill(lgEntered);
        polygon.setFill(Color.web("#436B8B"));
        polygon.setStroke(Color.WHITE);
      }
    });

    // Register mouse exited event handler
    // Recover to original appearance when mouse exited
    buttonGroup.setOnMouseExited(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse exited");
        rect.setFill(lg);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));
      }
    });

    buttonGroup.getChildren().addAll(rect, polygon);
    return buttonGroup;
  }

  /**
   * Create previous button using a Rectangle as background,
   * a Polygon as icon, a Group as container,
   * size of Rectangle is 25 by 35,
   * thickness of polygon is 8 pixels,
   * padding of polygon is (2, 5, 2, 5),
   * change rectangle appearance when mouse entered.
   * 
   * @return 
   */
  Node createPrevButton() {

    // Create a group as button
    Group buttonGroup = new Group();

    // Create a rectangle shape as background
    final Rectangle rect = new Rectangle(0, 0, 25, 35);

    // Look and feel of the rectangle
    final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
      new Stop(0, Color.web("#87A7C6")),
      new Stop(0.4, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#5173A8"))});
    rect.setFill(lg);
    rect.setStroke(Color.web("#ACD7FF"));
    rect.setArcHeight(6.5);
    rect.setArcWidth(6.5);

    // Look and feel when mouse entered the button
    final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
      new Stop(0, Color.web("#5173A8")),
      new Stop(0.6, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#87A7C6"))});

    // Create a polygon shape representing visual sign of Next icon
    // 8 pixel thickness, insets is 2, 2, 2, 5
    final Polygon polygon = new Polygon();
    Double[] dArray = {
      19.0, 2.0,
      2.0, 17.0,
      19.0, 32.0,
      19.0, 25.0,
      10.0, 17.0,
      19.0, 9.0};
    polygon.getPoints().addAll(dArray);
    polygon.setFill(Color.WHITE);
    polygon.setStroke(Color.web("#436B8B"));

    // Set cursor
    buttonGroup.setCursor(Cursor.OPEN_HAND);

    // Register mouse clicked event handler for prevButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasPrevious()) {
          java.nio.file.Path path = iterator.previous();
          if (lastClickedButton.get().equals(NEXT)) {
            // If the last clicked button is nextButton
            // the first call of previous() is the current image,
            // must move cursor one step backward
            if (iterator.hasPrevious())
              path = iterator.previous();
            else
              return;
          }
          System.out.format("Prev button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          lastClickedButton.set(PREVIOUS);
        }
      }
    });

    // Register mouse entered event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse entered");
        rect.setFill(lgEntered);
        polygon.setFill(Color.web("#436B8B"));
        polygon.setStroke(Color.WHITE);
      }
    });

    // Register mouse exited event handler
    // Recover to original appearance when mouse exited
    buttonGroup.setOnMouseExited(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse exited");
        rect.setFill(lg);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));
      }
    });

    buttonGroup.getChildren().addAll(rect, polygon);
    return buttonGroup;
  }

  public static void main(String[] args) {
    launch(args);
  }

}
```

Figure 2-11. Snapshot of `Image Viewer V1.1`, mouse hovers over `Previous` button.

![](Images/image00148.jpeg "next_prev_finish.jpg")

Compile and run the program from command line, testing the program by loading both large size and smaller size images from `FileChooser`'s File Open Dialog, selecting different view options, resizing the application window dynamically, clicking on `Next` button to load next image, clicking on `Previous` button to load previous image, ..., etc. The output is similar as follows:

Output from Compiling and Running ImageViewer in command line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeOne\ImageViewer1.1\src\example4>
javac  -encoding utf-8 -Xlint:unchecked imageviewer\*.java

jar cf imageviewer.jar imageviewer

java -cp imageviewer.jar imageviewer.ImageViewer
original size
imageArea width changed from 0.0 to 600.0
imageArea height changed from 0.0 to 375.0
fitwidth
fitheight
original size
Mouse entered
Next button clicked: jasmin.bmp
Mouse exited
Mouse entered
Next button clicked: Shufen2009_11 306.jpg
Mouse exited
Mouse entered
Prev button clicked: Shufen2009_11 305.jpg
Mouse exited
Scene height changed from 400.0 to 501.0
imageArea height changed from 375.0 to 476.0
Scene width changed from 600.0 to 691.0
imageArea width changed from 600.0 to 691.0
Mouse entered
Next button clicked: Shufen2010_01 420.jpg
Mouse exited
```

## 2.6 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Group` class, resides in `javafx.scene.Group` package, is a subclass of `javafx.scene.Parent`.
    (See section [Use `Group` as Parent Container](#part0008.xhtml_group-as-container))
*   `Shape` class, resides in `javafx.scene.shape` package, provides functionality for rendering 2D geometric primitives such as rectangle, polygon, etc.
    (See section [Use `Shape` Class for Rendering 2D Geometric Primitives](#part0008.xhtml_shape-class))
*   `Rectangle` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw rectangle shapes with specified properties, such as `x`, `y`, `width`, `height`, etc.
    (See sections: [Use `Shape` Class for Rendering 2D Geometric Primitives](#part0008.xhtml_shape-class), and [Use `Rectangle` Shape as Bounding Box of Custom-Made Button](#part0008.xhtml_rectangle-as-bounding-box))
*   `Polygon`, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. Use the `getPoints()` method to obtain a list which is type of `ObservableList<Double>`, then use the basic utilities, defined in `Collection` interface, to add a series of x and y coordinates, stored in an array of `Double` value, to the list, representing points of a `Polygon`.
    (See sections: [Use `Shape` Class for Rendering 2D Geometric Primitives](#part0008.xhtml_shape-class), and [Use `Polygon` Shape as Visual Sign of `Next` Icon](#part0008.xhtml_polygon-as-icon))
*   `LinearGradient` and `Color`, reside in `javafx.scene.paint` package, are two of direct subclasses of `Paint` class.
    (See section [Paint Background and Border of `Shape`](#part0008.xhtml_paint-shape))
*   `CycleMethod` and `Stop`, reside in `javafx.scene.paint` package, are classes used along with `LinearGradient` and `RadialGradient` classes:

    `CycleMethod`

    An enumerated type which defines constants: `CycleMethod.NO_CYCLE`, `CycleMethod.REFLECT`, and `CycleMethod.REPEAT`.

    `Stop`

    Define an offset and a color to be applied to color gradient.

    (See sections: [Use `Rectangle` Shape as Bounding Box of Custom-Made Button](#part0008.xhtml_rectangle-as-bounding-box), and [Paint Background and Border of `Shape`](#part0008.xhtml_paint-shape))
*   `arcHeight` and `arcWidth` are properties defined in `Rectangle` class, for rendering rounded rectangles.
    (See section [Set Value of `arcHeight` and `arcWidth` Properties to Render Rounded Rectangle](#part0008.xhtml_arc-height-arc-width))
*   `Cursor` class, resides in `javafx.scene` package and extends `java.lang.Object`, defines some useful mouse cursors as static fields of `Cursor` type such as `CLOSED_HAND`, `CROSSHAIR`, `HAND`, `OPEN_HAND`, `TEXT`, `WAIT`, etc.
    (See section [Set Value of `Cursor` Property for `Node`](#part0008.xhtml_mouse-cursor))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See section [Use Convenience Methods to Register Event Handlers to Handle Mouse Events](#part0008.xhtml_event-handler))
*   `MouseEvent`, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `MOUSE_CLICKED`, `MOUSE_DRAGGED`, `MOUSE_ENTERED`, `MOUSE_EXITED`, `MOUSE_MOVED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, etc., and provides methods such as `getX()`, `getY()`, etc., to get position of mouse cursor while event occurs.
    (See section [Use Convenience Methods to Register Event Handlers to Handle Mouse Events](#part0008.xhtml_event-handler))
*   Some of convenience methods provided in `Node` class to register `EventHandler`s to handle mouse events.

    `public final void setOnMouseClicked(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnMouseEntered(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnMouseExited(EventHandler<? super MouseEvent>` value`)`

    (See section [Use Convenience Methods to Register Event Handlers to Handle Mouse Events](#part0008.xhtml_event-handler))
*   `static void install(Node` node`, Tooltip` t`)` method, provided in `Tooltip` class which resides in `javafx.scene.control` package and extends `javafx.scene.control.PopupControl` class, shows help information when mouse hovers on the given `Node`.
    (See section [Install `Tooltip` for `Node`](#part0008.xhtml_tooltip))
*   Static methods, provided in `StackPane`, for customizing layout constraints on the specified child node:

    `static void setAlignment(Node` child`, Pos` value`)`

    `static void setMargin(Node` child`, Insets` value`)`

    (See sections: [Adjust `Next` Button's Default Position in `StackPane`](#part0008.xhtml_adjust_next), and [Add `Previous` Button and Adjust Its Position in `StackPane`](#part0008.xhtml_add_previous))
*   `Pos`, resides in `javafx.geometry` package, is an enumerated type defines constants for position and alignment such as `CENTER`, `CENTER_RIGHT`, `TOP_RIGHT`, etc.
    (See sections: [Adjust `Next` Button's Default Position in `StackPane`](#part0008.xhtml_adjust_next), and [Add `Previous` Button and Adjust Its Position in `StackPane`](#part0008.xhtml_add_previous))
*   `Insets` class, resides in `javafx.geometry` package, is often used in the `setMargin` method or in the `setPadding` method for specifying offset of 4 sides: top, right, bottom and left of a rectangle area.
    (See section [Adjust `Next` Button's Default Position in `StackPane`](#part0008.xhtml_adjust_next), and [here](#part0008.xhtml_prev-button-set-margin-codes))
*   `FileChooser.ExtensionFilter` is the nested class defined in the `FileChooser` class, for defining filters to show only files whose extensions matching the given filters.
    (See section [Configure `FileChooser`](#part0008.xhtml_configure-file-chooser))
*   Some of Classes reside in `javafx.beans.property` package:

    `ObjectProperty<T>`

    is an abstract class, derived from `javafx.beans.binding.ObjectExpression<T>` class, implements `Property<T>` and `WritableObjectValue<T>`.

    `SimpleObjectProperty<T>`

    derived from `ObjectProperty<T>` class.

    `StringProperty`

    is an abstract class, derived from `javafx.beans.binding.StringExpression` class, implements `Property<java.lang.String>` and `WritableStringValue`.
    `WritableStringValue` extends `WritableObjectValue<java.lang.String>`.

    `SimpleStringProperty`

    derived from `StringProperty` class.

    (See section [Define Properties in `ImageViewer` Class](#part0008.xhtml_properties))
*   `Property<T>` interface, resides in `javafx.beans.property` package, defines methods which are common to all properties such as the followings:

    `void bind(ObservableValue<? extends T>` observable`)`

    Bind this property unidirectional to the given `ObservableValue`.

    `void unbind()`

    Unbind for this property.

    (See section [Define Properties in `ImageViewer` Class](#part0008.xhtml_properties))
*   `WritableObjectValue<T>` interface, resides in `javafx.beans.value` package and extends `WritableValue<T>`, defines the following methods:

    `T get()`

    Get the wrapped value.

    `void set(T value)`

    Set the wrapped value.

    (See [here](#part0008.xhtml_property-set-method))

# Chapter 3
Enhanced Image Viewer with Slide Show Capacity
--Developing Image Viewer V1.2

## Preface

At this stage, the `ImageViewer` application has contained adequate abilities as an effective image viewing tool. Based on the fundamental structure built so far, more functionality may be incrementally developed with ease.

This chapter features the implementation of slide show capabilities as well as fine-tuning overall look and feel of GUIs. We'll demonstrate how to develop a multi-threaded JavaFX application using classes for concurrency, reside in `javafx.concurrent` package.

The version number of `ImageViewer` is upgraded to 1.2. From detailed descriptions and well-documented example codes excerpted from ImageViewer V1.2, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0009.xhtml_summary) section.

The complete development process of ImageViewer V1.2 is characterized by the following steps:

*   [3.1 Add Status Bar at the Bottom of `BorderPane`](#part0009.xhtml_add-footer)
    *   [3.1.1 Create `HBox` Pane as Status Bar and `Text` Node to Show Image Name](#part0009.xhtml_create-hbox-text)
    *   [3.1.2 Set Value of `imageName` Property](#part0009.xhtml_set-value-image-name)
*   [3.2 Improve Button's Reaction Aspect](#part0009.xhtml_improve-button)
    *   [3.2.1 Disable Button to Indicate No More Image to Open](#part0009.xhtml_disable-button)
    *   [3.2.2 Change Button Appearance When Mouse Is Pressed](#part0009.xhtml_pressed-button)
*   [3.3 Add Slide Show Capabilities](#part0009.xhtml_add-slideshow)
    *   [3.3.1 Add `Start Slideshow` and `Stop Slideshow` Menu Items](#part0009.xhtml_add-slideshow-menu-item)
        *   [3.3.1.1 Bind Disable Property of Menu Item](#part0009.xhtml_slideshow-disable-bind)
    *   [3.3.2 Execute Slide Show on Another Thread](#part0009.xhtml_slideshow-thread)
        *   [3.3.2.1 Create `SlideshowService` Class that Extends `Service` Class](#part0009.xhtml_slideshow-service)
        *   [3.3.2.2 Configure Slide Show Service Object](#part0009.xhtml_configure-slideshow)
        *   [3.3.2.3 Implement Event Handlers of Action Events for `Start Slideshow` and `Stop Slideshow` Menu Items](#part0009.xhtml_slideshow-action)
    *   [3.3.3 The Complete `start(Stage` stage`)` Method of `ImageViewer` Application](#part0009.xhtml_complete-start)
    *   [3.3.4 Coordinate with Event Handlers of `Load` Menu Item and `Previous` Button](#part0009.xhtml_coordinate)
*   [3.4 Add Fade Transition between Slides](#part0009.xhtml_fade-transition)
    *   [3.4.1 Complete Source Codes of `SlideshowService` Class](#part0009.xhtml_complete-slide-show-service)
*   [3.5 Complete Source Codes of `Image Viewer V1.2`](#part0009.xhtml_complete-source-codes)
*   [3.6 Summary](#part0009.xhtml_summary)

## 3.1 Add Status Bar at the Bottom of `BorderPane`

Prior to the implementation of slide show feature, we'll add a status bar at the bottom of the root pane which is a `BorderPane`. The status bar is for displaying image name, the file name of the current image.

### 3.1.1 Create `HBox` Pane as Status Bar and `Text` Node to Show Image Name

An `HBox`, one of build-in layout panes, placing its children in one row horizontally, is created as status bar. And a `Text` node is created to display image name. Here's the snippet of codes to do these:

```
 BorderPane rootPane = new BorderPane();
    HBox statusBar = new HBox();
    Text statusText = new Text("");
    statusBar.getChildren().add(statusText);
    rootPane.setBottom(statusBar);
```

Please notice that `Text` class derives from `Node` class, and is one of direct subclasses of `Shape` class that carries out common needs for rendering geometric primitives.

A `Text` being considered a `Node` as well as a `Shape` comes with significant benefits. All features common to JavaFX nodes can be applied to `Text` objects. They can be placed in a layout pane utilizing the automatic placement capabilities, applying transformations and transitions, customizing the presentation style using CSS, etc. Also they possess common properties defined in `Shape` class such as `fill`, `stroke`, `strokeType`, `strokeWidth`, etc.

We'd like to set preferred value of properties as below for the `HBox` created as a status bar:

`padding`

The `padding` property, inherited from `Region` class, defines padding of top, right, bottom and left for a region. The `void setPadding(Insets` value`)` method is called to set value for this property.

`spacing`

The `spacing` property, defined in `HBox` class, specifies the horizontal space between children in an `HBox` pane. The `void setSpacing(double` value`)` method is called to set value for this property.

`style`

The `style` property, defined in `Node` class, specifies CSS style for this node. The value of this property is a string complying with the format used in the `style` attribute of a HTML element. The `void setStyle(String` value`)` method is called to set the background color of a status bar, specifying a property-value pair in a string with format like this:

```
 "-fx-background-color: linear-gradient(#F0FFFF, #708090)" 
```

Here's the snippet of codes to do these:

```
 HBox statusBar = new HBox();
    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(#F0FFFF, #708090)");
```

As for the `Text` object, values for `font` property and `fill` property are set. Here's the snippet of codes to do these:

```
 Text statusText = new Text("");
    statusText.setFont(Font.font("Verdana", FontWeight.BOLD, 12));
    statusText.setFill(Color.DARKSLATEBLUE);
```

To make a scene in vivid contrast against an image rendered in a `StackPane`, we prefer the background of the scene be `Color.BLACK`. The constructor that allows specifying color is employed:

```
 Scene scene = new Scene(rootPane, 600, 400, Color.BLACK);
```

Please notice that, there's an unusual aspect in JavaFX 8 (JDK 8u66 running on Windows 8.1), regarding background of a `Scene`; to see through the background color of a `Scene`, we need set root pane's background color to transparent. Here's the line of code:

```
 rootPane.setStyle("-fx-background-color: transparent;");
```

The status bar, a region added at the bottom of the root pane, affects the height of image rendering area, a `StackPane`. Thus the line of code which binds `fitHeight` property of an `ImageView` with `height` property of a `Scene` need be changed to this:

```
 imageView.fitHeightProperty().bind(
                scene.heightProperty().subtract(
                  menuBar.getHeight() + statusBar.getHeight()));
```

In previous chapters, we have demonstrated usages of Properties and Binding in various situations. Here's one more case. The `text` property of the `Text` node binds with `imageName`, a class field of type `StringProperty` defined in `ImageViewer` class. Here's the snippet of codes to do these:

```
 StringProperty imageName = new SimpleStringProperty();
    Text statusText = new Text("");
    statusText.textProperty().bind(imageName);
```

When do we set value of `imageName` property will be described in next section.

Up to this stage, all of the changes made in `ImageViewer` class are shown in bold face in the following snippets of codes:

Import Statements:

```
 import javafx.scene.layout.HBox;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.Text;
```

Listing 3-1. Add an `HBox`, the status bar, with a `Text` node in it for displaying image name, specify background color for the `Scene`, and alter codes that bind `fitHeight` property:

```
 public class ImageViewer extends Application {

      ...

    final StringProperty imageName = new SimpleStringProperty();

      ...

@Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    final StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    // Add status bar and status text
    final HBox statusBar = new HBox();
    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(#F0FFFF, #708090)");
    final Text statusText = new Text("");
    statusText.textProperty().bind(imageName);
    statusText.setFont(Font.font("Verdana", FontWeight.BOLD, 12));
    statusText.setFill(Color.DARKSLATEBLUE);

    statusBar.getChildren().add(statusText);
    rootPane.setBottom(statusBar);

      ...

    rootPane.setStyle("-fx-background-color: transparent;");
    final Scene scene = new Scene(rootPane, 600, 400, Color.BLACK);

      ...

    // Listen to the change of selection in the toggle group
    groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
        if (groupOption.getSelectedToggle() != null) {
          RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
          if (choiceItem == fitWidth) {
            System.out.println("fitwidth");
            imageView.fitWidthProperty().bind(scene.widthProperty());
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height to 0
            imageView.setFitHeight(0);
          } else if (choiceItem == fitHeight) {
            System.out.println("fitheight");
            // Available height for rendering image is
            // subtract sum of menubar's height and statusBar's height
            // from scene height
            imageView.fitHeightProperty().bind(
                scene.heightProperty().subtract(
                  menuBar.getHeight() + statusBar.getHeight()));
            imageView.fitWidthProperty().unbind();
            // Besides unbind, must also set fit width to 0 
            imageView.setFitWidth(0);
          } else {
            System.out.println("original size");
            imageView.fitWidthProperty().unbind();
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height/height to 0
            imageView.setFitWidth(0);
            imageView.setFitHeight(0);
          }
        }
      }
    });

      ...
  }
```

### 3.1.2 Set Value of `imageName` Property

The `text` property of a `Text` node, created for displaying image name in a status bar, binds with the `imageName` property defined in `ImageViewer` class. Whenever a new image file is opened and displayed on image rendering area, an image name is obtained from a `File` object, and set as value of `imageName` property. Here's the snippet of codes to do these:

```
 File file = fileChooser.showOpenDialog(stage);
String url = file.toURI().toString();
imageName.set(url.substring(url.lastIndexOf("/")+1).replaceAll("%20", " "));
```

The following line of code, obtaining an image name from a url of string representation,

```
 imageName.set(url.substring(url.lastIndexOf("/")+1).replaceAll("%20", " "));
```

is inserted to the action handler of `Load` menu item as well as mouse clicked event handlers of `Next` and `Previous` buttons. Since the `text` property of `statusText`, a `Text` object, binds with `imageName` property, whenever value of `imageName` property is changed, the text rendered on a status bar will be changed accordingly.

Listing 3-2. Action handler for `Load` menu item becomes like this:

```
 // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          // Set last visited dir as initial directory
          File lastDir = file.getParentFile();
          fileChooser.setInitialDirectory(lastDir);
          // Create a list iterator when a file is opened from File Chooser
          try {
            ListIterator<java.nio.file.Path> it =
                FileUtils.listIterator(file.toPath());
            listIterator.set(it);
            file = it.next().toFile();
            String url = file.toURI().toString();          
            curImage.set(new Image(url));
            imageName.set(url.substring(
              url.lastIndexOf("/")+1).replaceAll("%20", " "));
            // Set to NEXT because the cursor in iterator is pointing to 
            // the next available file
            lastClickedButton.setValue(NEXT);
          } catch (IOException ex) {}
        }
      }
    }); 
```

Listing 3-3. Mouse clicked handler for `Next` button becomes this:

```
 // Register mouse clicked event handler for nextButton
    buttonGroup.setOnMouseClicked(new EventHandler() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasNext()) {
          java.nio.file.Path path = iterator.next();
          if (lastClickedButton.get().equals(PREVIOUS)) {
            // If last clicked button is prevButton
            // the first call of next() is the current image, 
            // must move cursor one step forward.
            if (iterator.hasNext())
              path = iterator.next();
            else
              return;
          }
          System.out.format("Next button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          imageName.set(url.substring(
              url.lastIndexOf("/")+1).replaceAll("%20", " "));

          lastClickedButton.set(NEXT);
        }
      }
    });
```

Listing 3-4. Mouse clicked handler for `Previous` button becomes this:

```
 // Register mouse clicked event handler for prevButton
    buttonGroup.setOnMouseClicked(new EventHandler() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasPrevious()) {
          java.nio.file.Path path = iterator.previous();
          if (lastClickedButton.get().equals(NEXT)) {
            // If the last clicked button is nextButton
            // the first call of previous() is the current image,
            // must move cursor one step backward
            if (iterator.hasPrevious())
              path = iterator.previous();
            else
              return;
          }
          System.out.format("Prev button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          imageName.set(url.substring(
              url.lastIndexOf("/")+1).replaceAll("%20", " "));

          lastClickedButton.set(PREVIOUS);
        }
      }
    });
```

The following snapshot is taken when `Fit Height` is the selected view option, the current image file name is displayed on a status bar and the background color of a scene is black.

Figure 3-1. Snapshot of current image file name displayed on the status bar located at the bottom of scene window.

![](Images/image00149.jpeg "status_bar.jpg")

## 3.2 Improve Button's Reaction Aspect

In this section, we take a little effort to fine-tune buttons' look and feel, also to enhance the user-friendliness.

### 3.2.1 Disable Button to Indicate No More Image to Open

First, we'll set button's disable status to true when there is no next or previous image to open. Once a button is disabled, it will not receive any mouse or keyboard event. A button's disable status is initialized to false immediately after it is created.

Listing 3-5. Initialize buttons' disable status:

```
 public class ImageViewer extends Application {
  final Node nextButton = createNextButton();
  final Node prevButton = createPrevButton();
  {
    disableButton(nextButton, true);
    disableButton(prevButton, true);
  }

    ...

}
```

The `disable` property defined in `Node` class is type of `BooleanProperty`, it specifies the disable status of this node. Setting this node's `disable` property to `true` also results in the value of `disabled` property of this node as well as that of its entire descendant become `true`. Please notice that it is possible that a node's `disabled` property is true while its `disable` property is not true.

The `opacity` property defined in `Node` class is type of `DoubleProperty`, specifying the extent of transparency of this node. Its value is ≧ 0 and ≦1\. A node with opacity value of 0 means it is totally transparent.

The following codes demonstrate how to render a button in disabled status by leveraging the `opacity` property of a node.

Listing 3-6. Define `disableButton` method:

```
 /**
   * This method takes advantage of node's opacity property to
   * distinguish disable status, 
   * set opacity value to 0.4 if it is disabled.
   * 
   * @param button
   * @param isDisable 
   */
  void disableButton(Node button, boolean isDisable) {
    // Change the opacity value to 0.4 if no more image to open
    double opacity = (isDisable) ? 0.4 : 1;
    button.setOpacity(opacity);
    button.setDisable(isDisable);
  }
```

Now, the initial screen looks like this.

Figure 3-2. Snapshot of the initial application window, buttons are disabled.

![](Images/image00150.jpeg "initial_scene.jpg")

To determine whether next image or previous image is available or not, `hasNext()` and `hasPrevious()` methods defined in `ListIterator` interface are called to do the verification during the following occasions:

*   When a list of files that exist in the current directory is first created from the action event handler of `Load` menu item.
*   When an image is loaded as a mouse clicked event occurred on `Next` or `Previous` button.

We'll define a `loadFile(File` file`)` method to modularize the tasks that deal with the action event of `Load` menu item:

Listing 3-7. Define `loadFile` method to create a list iterator, load the specified file and update button status:

```
 /**
   * Static method FileUtils.listIterator(Path) is called to 
   * get a list iterator to iterate over files in the directory,
   * disable buttons if no more files to open.
   *
   * @param file 
   */
  void loadFile(File file) {
    // Create list iterator
    try {
      ListIterator<java.nio.file.Path> it =
        FileUtils.listIterator(file.toPath());

      // Update value of listIterator property
      listIterator.set(it);

      // Disable prevButton if there's no previous file,
      // check hasPrevious() before next() is called
      disableButton(prevButton, !it.hasPrevious());

      file = it.next().toFile();
      String url = file.toURI().toString();
      curImage.set(new Image(url));
      imageName.set(url.substring(
          url.lastIndexOf("/") + 1).replaceAll("%20", " "));

      // Check hasNext, disable nextButton if there's no next file
      disableButton(nextButton, !it.hasNext());

      lastClickedButton.setValue(NEXT);
    } catch (IOException ex) {
    }
  } 
```

The above `loadFile` method is called from the action event handler of `load` menu item. Changes are shown in bold face in the following Listing.

Listing 3-8. `loadFile` method is called when a file is selected and opened from `FileChooser`'s File Open Dialog:

```
 // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          // Set last visited dir as initial directory
          File lastDir = file.getParentFile();
          fileChooser.setInitialDirectory(lastDir);
          loadFile(file);
        }
      }
    });
```

When mouse clicked event occurs on the `Next` button, the next available image is loaded and displayed on the image rendering area. In the mean time, we need to check if there is no more next image to be loaded. Here are snippets of codes, changes are shown in bold face:

Listing 3-9. Update `Next` button's disable status inside mouse clicked event handler:

```
 Node createNextButton() {

    ...

     // Register mouse clicked event handler for nextButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasNext()) {
          java.nio.file.Path path = iterator.next();
          if (lastClickedButton.get().equals(PREVIOUS)) {
            // If last clicked button is prevButton
            // the first call of next() is the current image, 
            // must move cursor one step forward.
            if (iterator.hasNext())
              path = iterator.next();
            else {
              // There is no next image, disable next buttons
              disableButton(nextButton, true);
              return;
            }
          }
          System.out.format("Next button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          imageName.set(url.substring(
            url.lastIndexOf("/")+1).replaceAll("%20", " "));  
          curImage.set(new Image(url));
          lastClickedButton.set(NEXT);
          // Disable next button when there's no next image
          disableButton(nextButton, !iterator.hasNext());
          if (prevButton.isDisable())
            disableButton(prevButton, false);
        }
      }
    });

    ...
  }
```

When mouse clicked event occurs on the `Previous` button, the previous available image is loaded and displayed on the image rendering area. In the mean time, we need to check if there is no more previous image to be loaded. Here are snippets of codes, changes are shown in bold face:

Listing 3-10. Update `Previous` button's disable status inside mouse clicked event handler:

```
 Node createPrevButton() {

    ...

     // Register mouse clicked event handler for prevButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasPrevious()) {
          java.nio.file.Path path = iterator.previous();
          if (lastClickedButton.get().equals(NEXT)) {
            // If the last clicked button is nextButton
            // the first call of previous() is the current image,
            // must move cursor one step backward
            if (iterator.hasPrevious())
              path = iterator.previous();
            else {
              // There is no previous image, disable prevButton
              disableButton(prevButton, true);
              return;
            }
          }
          System.out.format("Prev button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          imageName.set(url.substring(
            url.lastIndexOf("/")+1).replaceAll("%20", " "));  
          curImage.set(new Image(url));
          lastClickedButton.set(PREVIOUS);
          // Disable previous button when there's no previous image
          disableButton(prevButton, !iterator.hasPrevious());
          if (nextButton.isDisabled()) 
            disableButton(nextButton, false); 
        }
      }
    });

    ...
  }
```

Figure 3-3. Snapshot of `Previous` button disabled when there's no previous file to open.

![](Images/image00151.jpeg "button_disable.jpg")

Figure 3-4. Snapshot of `Next` button disabled when there's no next file to open.

![](Images/image00152.jpeg "next_button_disable.jpg")

### 3.2.2 Change Button Appearance When Mouse Is Pressed

Now, we'll change buttons' background paint when mouse pressed event occurred on them. In the mean time, codes for creating `Next` button and `Previous` button are tidied up by modularized codes for mouse event handling. The `registerButtonEvent` method is defined to register event handlers for the following `EventType`s: `MOUSE_ENTERED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, and `MOUSE_EXITED`.

When mouse pressed on a button, the paint to fill a rectangle is changed, the paint to fill polygon is same as the one used when mouse entered. The fill and stroke restores to original values when mouse released or exited a button.

Import Statements:

```
 import javafx.scene.paint.Paint;
import javafx.scene.shape.Shape;
```

Listing 3-11. Define `registerButtonEvent` method:

```
 /**
   * This method registers mouse entered/pressed/released/exited events for button,
   * look and feel of the button is changed to distinguish between different event types.
   * 
   * @param buttonGroup
   * @param rect
   * @param polygon
   * @param bg
   * @param entered
   * @param pressed 
   */
  void registerButtonEvent(Node buttonGroup,
    final Shape rect, final Shape polygon,
    final Paint bg, final Paint entered, final Paint pressed) {

    // Register mouse entered event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse entered");
        // Check if left mouse button is pressed
        rect.setFill(me.isPrimaryButtonDown()? pressed : entered);
        polygon.setFill(Color.web("#436B8B"));
        polygon.setStroke(Color.WHITE);
      }
    });

    // Register mouse pressed event handler
    // Change the appearance of button when mouse entered
    buttonGroup.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse pressed");
        if (me.isPrimaryButtonDown()) {
          rect.setFill(pressed);
          polygon.setFill(Color.web("#436B8B"));
          polygon.setStroke(Color.WHITE);
        }
      }
    });

    // Mouse exited event handler
    // Recover to original appearance when mouse exited
    EventHandler<MouseEvent> exited = new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        System.out.println("Mouse exited/released");
        rect.setFill(bg);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));
      }
    };

    buttonGroup.setOnMouseExited(exited);

    // Register mouse released event handler
    // Recover to original appearance when mouse released
    // the appearance is same as mouse exited
    buttonGroup.setOnMouseReleased(exited);
  }
```

Listing 3-12. The `createNextButton` method becomes like this:

```
 /**
   * Create next button using a Rectangle as background,
   * a Polygon as icon, a Group as container,
   * size of Rectangle is 25 by 35,
   * thickness of polygon is 8 pixels,
   * padding of polygon is (2, 2, 2, 5),
   * change button appearance when mouse entered/pressed/released/exited.
   *
   * @return
   */
  Node createNextButton() {

    // Create a group as button
    Group buttonGroup = new Group();

    // Create a rectangle shape as background
    final Rectangle rect = new Rectangle(0, 0, 25, 35);

    // Use linear gradient to fill the rectangle of next button
    final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[]{
      new Stop(0, Color.web("#5173A8")),
      new Stop(0.6, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#87A7C6"))});
    rect.setFill(lg);
    rect.setStroke(Color.web("#ACD7FF"));
    rect.setArcHeight(6.5);
    rect.setArcWidth(6.5);

    // Paint to fill rectangle when mouse entered the next button
    final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[]{
      new Stop(0, Color.web("#87A7C6")),
      new Stop(0.4, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#5173A8"))});

    // Paint to fill rectangle when mouse pressed on the next button
    final LinearGradient lgPressed = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[]{
      new Stop(0, Color.web("#87A7C6")),
      new Stop(0.4, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#2F4F4F"))});

    // Create a polygon shape representing visual sign of Next icon
    // 8 pixel thickness, insets is 2, 2, 2, 5
    final Polygon polygon = new Polygon();
    Double[] dArray = {
      5.0, 2.0,
      22.0, 17.0,
      5.0, 32.0,
      5.0, 25.0,
      14.0, 17.0,
      5.0, 9.0};
    polygon.getPoints().addAll(dArray);
    polygon.setFill(Color.WHITE);
    polygon.setStroke(Color.web("#436B8B"));

    // Set cursor
    buttonGroup.setCursor(Cursor.OPEN_HAND);

    // Register mouse clicked event handler for nextButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (me.getButton() != MouseButton.PRIMARY)
          return;
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasNext()) {
          java.nio.file.Path path = iterator.next();
          if (lastClickedButton.get().equals(PREVIOUS)) {
            // If last clicked button is prevButton
            // the first call of next() is the current image, 
            // must move cursor one step forward.
            if (iterator.hasNext())
              path = iterator.next();
            else{
              // There is no next image, disable next buttons
              disableButton(nextButton, true);
              return;
            }
          }
          System.out.format("Next button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          imageName.set(url.substring(
              url.lastIndexOf("/")+1).replaceAll("%20", " "));

          lastClickedButton.set(NEXT);
          // Disable next button when there's no next image
          disableButton(nextButton, !iterator.hasNext());
          if (prevButton.isDisable())
            disableButton(prevButton, false);
        }
      }
    });

    registerButtonEvent(buttonGroup, rect, polygon, lg, lgEntered, lgPressed);

    buttonGroup.getChildren().addAll(rect, polygon);
    return buttonGroup;
  }
```

Listing 3-13. The `createPrevButton` method becomes like this:

```
 /**
   * Create previous button using a Rectangle as background,
   * a Polygon as icon, a Group as container,
   * size of Rectangle is 25 by 35,
   * thickness of polygon is 8 pixels,
   * padding of polygon is (2, 5, 2, 5),
   * change button appearance when mouse entered/pressed/released/exited.
   * 
   * @return 
   */
  Node createPrevButton() {

    // Create a group as button
    Group buttonGroup = new Group();

    // Create a rectangle shape as background
    final Rectangle rect = new Rectangle(0, 0, 25, 35);

    // Using linear gradient to fill rectangle of previous button
    final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
      new Stop(0, Color.web("#87A7C6")),
      new Stop(0.4, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#5173A8"))});
    rect.setFill(lg);
    rect.setStroke(Color.web("#ACD7FF"));
    rect.setArcHeight(6.5);
    rect.setArcWidth(6.5);

    // Paint to fill rectangle when mouse entered the previous button
    final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[] { 
      new Stop(0, Color.web("#5173A8")),
      new Stop(0.6, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#87A7C6"))});

    // Paint to fill rectangle when mouse pressed on the previous button
    final LinearGradient lgPressed = new LinearGradient(0, 0, 1, 0, true,
        CycleMethod.NO_CYCLE, new Stop[]{
      new Stop(0, Color.web("#2F4F4F")),
      new Stop(0.6, Color.web("#A8B9D4")),
      new Stop(1, Color.web("#87A7C6"))});

    // Create a polygon shape representing visual sign of Next icon
    // 8 pixel thickness, insets is 2, 2, 2, 5
    final Polygon polygon = new Polygon();
    Double[] dArray = {
      19.0, 2.0,
      2.0, 17.0,
      19.0, 32.0,
      19.0, 25.0,
      10.0, 17.0,
      19.0, 9.0};
    polygon.getPoints().addAll(dArray);
    polygon.setFill(Color.WHITE);
    polygon.setStroke(Color.web("#436B8B"));

    // Set cursor
    buttonGroup.setCursor(Cursor.OPEN_HAND);

    // Register mouse clicked event handler for prevButton
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (me.getButton() != MouseButton.PRIMARY)
          return;
        // Get iterator
        ListIterator<java.nio.file.Path> iterator = listIterator.get();
        if (iterator != null && iterator.hasPrevious()) {
          java.nio.file.Path path = iterator.previous();
          if (lastClickedButton.get().equals(NEXT)) {
            // If the last clicked button is nextButton
            // the first call of previous() is the current image,
            // must move cursor one step backward
            if (iterator.hasPrevious())
              path = iterator.previous();
            else{
              // There is no previous image, disable prevButton
              disableButton(prevButton, true);
              return;
            }
          }
          System.out.format("Prev button clicked: %s%n", path.getFileName());
          String url = path.toUri().toString();
          curImage.set(new Image(url));
          imageName.set(url.substring(
              url.lastIndexOf("/")+1).replaceAll("%20", " "));

          lastClickedButton.set(PREVIOUS);
          // Disable previous button when there's no previous image
          disableButton(prevButton, !iterator.hasPrevious());
          if (nextButton.isDisabled()) 
            disableButton(nextButton, false); 
        }
      }
    });

    registerButtonEvent(buttonGroup, rect, polygon, lg, lgEntered, lgPressed);

    buttonGroup.getChildren().addAll(rect, polygon);
    return buttonGroup;
  }
```

Figure 3-5. Snapshot of `Previous` button's appearance during mouse entered event.

![](Images/image00153.jpeg "prev_button_entered.jpg")

Figure 3-6. Snapshot of `Previous` button's appearance during mouse pressed event.

![](Images/image00154.jpeg "prev_button_pressed.jpg")

Figure 3-7. Snapshot of `Next` button's appearance during mouse entered event.

![](Images/image00155.jpeg "next_button_entered.jpg")

Figure 3-8. Snapshot of `Next` button's appearance during mouse pressed event.

![](Images/image00156.jpeg "next_button_pressed.jpg")

## 3.3 Add Slide Show Capabilities

Once an image file is opened from a `FileChooser`'s File Open Dialog, the application obtains a list of image files that exist in the current directory. One favorable feature is to allow users to browse over these images one by one without manually clicking the `Next` button. The steps to implement slide show mechanism are illustrated as follows.

### 3.3.1 Add `Start Slideshow` and `Stop Slideshow` Menu Items

The simplest GUI employed here is `MenuItem`. Two menu items, `Start Slideshow` and `Stop Slideshow`, are added to `Option` menu of a menu bar, initially they are both disabled. To distinguish if there is a slide show running or not, a variable `isSlideshowOn` of type `BooleanProperty` is defined as class field of `ImageViewer` class and is initialized to `false`. The following snippets of codes show how to accomplish these:

Import Statements:

```
 import javafx.beans.property.BooleanProperty;
import javafx.beans.property.SimpleBooleanProperty;
```

Listing 3-14. Add `Start Slideshow` and `Stop Slideshow` menu items:

```
 public class ImageViewer extends Application {

    ...

  final BooleanProperty isSlideshowOn = new SimpleBooleanProperty(false);

    ...

  @Override
  public void start(final Stage stage) {

    ...

    // Create start/stop slideshow menu items
    final MenuItem startSlide = new MenuItem("Start Slideshow");
    final MenuItem stopSlide = new MenuItem("Stop Slideshow");

    startSlide.disableProperty().bind(isSlideshowOn.or(
        nextButton.disableProperty()));
    stopSlide.disableProperty().bind(isSlideshowOn.not().or(
        nextButton.disableProperty()));

    // Add action handler for Start Slideshow menu item
    startSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Start Slideshow...");
      }
    });

    // Add action handler for Stop Slideshow menu item
    stopSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Stop Slideshow...");
      }
    });    

    // Add option menu to menu bar
    menuOption.getItems().addAll(menuView, startSlide, stopSlide);

      ... 
```

#### 3.3.1.1 Bind Disable Property of Menu Item

Initially `startSlide` and `stopSlide` menu items are disabled because of the following `bind` statements.

```
 startSlide.disableProperty().bind(isSlideshowOn.or(
        nextButton.disableProperty()));
    stopSlide.disableProperty().bind(isSlideshowOn.not().or(
        nextButton.disableProperty())); 
```

In above binding statements, two logical operations--`or` and `not`--are used to compute value for disable property. The `javafx.beans.binding.BooleanExpression` class, an abstract class that implements `ObservableBooleanValue`, provides these methods:

`public BooleanBinding not()` method

performs a logical NOT operation on this `BooleanExpression`, and returns an object of type `BooleanBinding` which is a direct subclass of `BooleanExpression`.

`public BooleanBinding or(ObservableBooleanValue` other`)` method

performs a logical OR operation on this `BooleanExpression` and a given `ObservableBooleanValue`, and returns an object of type `BooleanBinding` which is a direct subclass of `BooleanExpression`.

The `Start Slideshow` menu item is disabled if either a slide show is currently running or the `Next` button is disabled. Similarly, the `Stop Slideshow` menu item is disabled if either a slide show is not running or the `Next` button is disabled. Remember that the `Next` button is disabled when there is no next image to view.

Figure 3-9. Snapshot of initial `Option` menu's appearance, both `Start Slideshow` and `Stop Slideshow` menu items are disabled.

![](Images/image00157.jpeg "start_stop_disabled.jpg")

Figure 3-10. Snapshot of `Option` menu's appearance after an image file is loaded, `Start Slideshow` menu item is enabled because a slide show is not on and there is at lease one next file to view, and `Stop Slideshow` menu item is disabled because a slide show is not on.

![](Images/image00158.jpeg "start_slideshow_enabled.jpg")

### 3.3.2 Execute Slide Show on Another Thread

It's a good programming practice to delegate a long-running task to another thread so that the UI thread (also called Java FX Application thread) is always responsive to user's actions.

`javafx.concurrent` package provides classes, `Task` and `Service` both of which implement `Worker` interface, for developing multi-threaded JavaFX applications with ease.

Here are classes for concurrency, reside in `javafx.concurrent` package:

`Task`

An abstract class that extends `java.util.concurrent.FutureTask` and implements `Worker<`V`>` interface, is a one-time `Worker` object, cannot be reused. It's also a `Runnable` object since its superclass `FutureTask` implements `Runnable` interface.

To start executing a `Task`, you use either APIs from `java.lang.Thread` class or APIs that are derived from `Executor` and `ExecutorService` interfaces, both reside in `java.util.concurrent` package. You create a `Thread` object given a `Task` as parameter, and call `start()` method to start this thread. Or, use the `submit(Runnable` task`)` method defined in `ExecutorService` to submit a task.

Override the `call()` method while creating a `Task` object, or creating a subclass of which. The `call()` method is invoked when a task is started.

`Service`

An abstract class that extends `java.lang.Object` and implements `Worker<`V`>` interface, is a reusable `Worker` object. The `Service` class provides methods such as `start()`, `cancel()`, `reset()`, and `restart()` to manipulate this service when needed.

Override the `createTask()` method while creating a `Service` object, or creating a subclass of which. The `createTask()` method is invoked when a service is started.

`ScheduledService`

A direct subclass of `Service` class, allows specifying the duration of delay to start and restart a service automatically.

`WorkerStateEvent`

A subclass of `javafx.event.Event`, defines static fields of `EventType`s such as `WORKER_STATE_CANCELLED`, `WORKER_STATE_FAILED`, `WORKER_STATE_READY`, `WORKER_STATE_RUNNING`, `WORKER_STATE_SUCCEEDED`, etc. A `WorkerStateEvent` occurs when the state of a `Worker` is changed.

Consider our situation: a file list is created when a file is first loaded, suppose the file list contains one or more next file(s) to view, then the `Start Slideshow` menu item is enabled, a user can start a slide show, cancel it while the slide show is on, and later restart it again. To fulfill this scenario, we prefer a reusable `Service` object to a one-time `Task` object.

#### 3.3.2.1 Create `SlideshowService` Class that Extends `Service` Class

We need to create a class that extends `Service<V>` class. When a `Service` is started, it executes a `Task`. The `createTask` method below need be overridden:

```
 protected abstract Task<V> createTask() 
```

In the `createTask()` method, the `call()` method is overridden while a `Task` object is created to be returned to the caller.

The `call()` method in a `Task`, undertakes the task of a slide show, basically contains a `while` loop that loads images one by one until either one of the following conditions becomes true: there's no more next image in the file list, or the slide show is canceled by a user.

The following listing demonstrates how to create a reusable `SlideshowService`, a subclass of `Service` class, to carry on a slide show task.

Listing 3-15. Create `SlideshowService` class:

```
 package imageviewer;

import java.nio.file.Path;
import java.util.ListIterator;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.concurrent.Service;
import javafx.concurrent.Task;
import javafx.scene.image.Image;

/**
 * File Name: SlideshowService.java
 * (in directory: ImageViewer1.2/src/example4/imageviewer/)
 *
 * @author Shufen Kuo
 */

public class SlideshowService extends Service<Void> {
  private ObjectProperty<Image> image;
  private ObjectProperty<ListIterator<Path>> iterator;
  private StringProperty imageName;
  private ListIterator<Path> it;

  public SlideshowService() {
    this(new SimpleObjectProperty<ListIterator<Path>>(),
        new SimpleObjectProperty<Image>(),
        new SimpleStringProperty());
  }

  public SlideshowService(ObjectProperty<ListIterator<Path>> iterator,
      ObjectProperty<Image> image, StringProperty imageName) {
    this.image = image;
    this.imageName = imageName;
    this.iterator = iterator;
    iterator.addListener(new ChangeListener<ListIterator<Path>>() {
      @Override
      public void changed(ObservableValue<? extends ListIterator<Path>> o,
          ListIterator<Path> oldVal, ListIterator<Path> newVal) {
        it = newVal;
      }
    });    
  }

  public Image getImage() {
    return image.get();
  }

  public void setImage(Image value) {
    image.set(value);
  }

  public ObjectProperty<Image> imageProperty() {
    return image;
  }

  public ListIterator<Path> getIterator() {
    return iterator.get();
  }

  public void setListIterator(ListIterator<Path> value) {
    iterator.set(value);
  }

  public ObjectProperty<ListIterator<Path>> iteratorProperty() {
    return iterator;
  }

  public String getImageName() {
    return imageName.get();
  }

  public void setImageName(String value) {
    imageName.set(value);
  }

  public StringProperty imageNameProperty() {
    return imageName;
  }

  @Override
  protected Task<Void> createTask() {
    return new Task<Void>() {
      @Override
      protected Void call() {
        if (it == null) return null;
        while (it.hasNext()) {
          if (isCancelled()) {
            updateMessage("Cancelled");
            break;
          }
          String url = it.next().toUri().toString();
          setImage(new Image(url));
          setImageName(url.substring(
              url.lastIndexOf("/") + 1).replaceAll("%20", " "));
          // Pause for 3000 ms
          try {
            Thread.sleep(3000);
          } catch (InterruptedException ex) {
            if (isCancelled()) {
              updateMessage("Cancelled");
              break;
            }
          }
        }
        return null;
      }
    };
  }  
}
```

The following statement creates a `SlideshowService` object.

```
 // Create a reusable Worker object
  final SlideshowService service = new SlideshowService(listIterator,
      curImage, imageName);
```

Three arguments are passed to the constructor of `SlideshowService` class:

`listIterator`

Type of `ObjectProperty<ListIterator<Path>>`, specifies a `ListIterator` that iterates the file list created when an image file is opened from a File Chooser's File Open Dialog.

`curImage`

Type of `ObjectProperty<Image>`, binds with the `image` property of an `ImageView` object.

`imageName`

Type of `StringProperty`, binds with the `text` property of a `Text` object, `statusText`, for displaying image name in a status bar.

#### 3.3.2.2 Configure Slide Show Service Object

We define a `configureSlideshow` method to do configurations. Once a service object is created, the method is called to perform these works:

2.  Bind the `isSlideshowOn` property defined in `ImageViewer` class with the `running` property of a `service`. The value of `isSlideshowOn` property is true if and only if the service is running.

    ```
     BooleanProperty isSlideshowOn = new SimpleBooleanProperty(false);
        SlideshowService service = new SlideshowService(listIterator,
          curImage, imageName);
        isSlideshowOn.bind(service.runningProperty());
    ```

3.  Register event handlers to handle `WorkerStateEvent`s of the following event types: `WORKER_STATE_RUNNING`, `WORKER_STATE_SUCCEEDED`, `WORKER_STATE_FAILED` and `WORKER_STATE_CANCELLED`.

    Here are convenience methods, defined in `Service` class, to register event handlers for the mentioned event types:

    *   `public final void setOnRunning(EventHandler<WorkerStateEvent>` value`)`

        Set value of `onRunning` property, providing the implementation of `handle` method which is called when `Worker`'s state is transited to `RUNNING`.

    *   `public final void setOnSucceeded(EventHandler<WorkerStateEvent>` value`)`

        Set value of `onSucceeded` property, providing the implementation of `handle` method which is called when `Worker`'s state is transited to `SUCCEEDED`.

    *   `public final void setOnFailed(EventHandler<WorkerStateEvent>` value`)`

        Set value of `onFailed` property, providing the implementation of `handle` method which is called when `Worker`'s state is transited to `FAILED`.

    *   `public final void setOnCancelled(EventHandler<WorkerStateEvent>` value`)`

        Set value of `onCancelled` property, providing the implementation of `handle` method which is called when `Worker`'s state is transited to `CANCELLED`.

`Worker.State`, a nested class from `javafx.concurrent.Worker` interface, is an enumerated type defines constants for states of a `Worker`, they are: `CANCELLED`, `FAILED`, `READY`, `RUNNING`, `SCHEDULED`, and `SUCCEEDED`.

Initially, a `Worker` object is in `READY` state. And when the `Worker` starts executing a task, it is transited to `SCHEDULED` state, then enters `RUNNING` state shortly after, and stays in `RUNNING` state until one of the following occasions occurs:

The task is accomplished successfully:

The `Worker` is transited to `SUCCEEDED` state.

An exception is thrown:

The `Worker` is transited to `FAILED` state.

The task is canceled:

The `Worker` is transited to `CANCELLED` state. A `Worker` can be canceled by calling the `boolean cancel()` method defined in `Worker` interface. It returns true if the canceling is successful.

The tasks performed in an event handler that handles `WORKER_STATE_RUNNING` event type are trivial:

1.  Set value of `lastClickedButton` property as `NEXT` since a slide show being running implies that the `Next` button is clicked automatically and continuously.
2.  Check if the `Previous` button is disabled, if it is, enable it.

And one single `EventHandler` is created to handle Worker State Event of multiple event types. The same event handler registered to handle `WORKER_STATE_SUCCEEDED` is also registered to handle `WORKER_STATE_FAILED` and `WORKER_STATE_CANCELLED`. The tasks to be performed while the `Worker`'s state transited to `SUCCEEDED`, `FAILED`, or `CANCELLED` are:

1.  Disable `Next` button if there is no next file in the list iterator, Otherwise, enable it.
2.  Enable `Previous` button if it is disabled.

The following is the implementation of `configureSlideshow` method:

Import Statement:

```
 import javafx.concurrent.WorkerStateEvent;
```

Listing 3-16. `configureSlideshow` method:

```
 /**
   * 
   */
  void configureSlideshow() {
    // If service is running, then value of isSlideshowOn is true,
    // otherwise, it's false 
    isSlideshowOn.bind(service.runningProperty());

    service.setOnRunning(new EventHandler<WorkerStateEvent>() {
      @Override
      public void handle(WorkerStateEvent we) {
        System.out.println("Service is transited to running status");
        lastClickedButton.set(NEXT);
        if (prevButton.isDisable()) {
          disableButton(prevButton, false);
        }
      }
    });

    EventHandler<WorkerStateEvent> taskDone = new EventHandler<WorkerStateEvent>() {
      @Override
      public void handle(WorkerStateEvent we) {
        disableButton(nextButton, !listIterator.get().hasNext());
        if (prevButton.isDisable()) {
          disableButton(prevButton, false);
        }
      }
    };

    service.setOnSucceeded(taskDone);
    service.setOnFailed(taskDone);
    service.setOnCancelled(taskDone);    
  }
```

#### 3.3.2.3 Implement Event Handlers of Action Events for `Start Slideshow` and `Stop Slideshow` Menu Items

The scenario follows the action of `Start Slideshow` is like this: when a user clicks the `Start Slideshow` menu item, the service is started, its state transits from READY to SCHEDULED to RUNNING, the value of `isSlideshowOn` property is changed to `true` as soon as the state is transited to `RUNNING`(see [here](#part0009.xhtml_is-slideshow-on-bind)), and `Stop Slideshow` menu item's disable status is changed to `false` as a result(see [here](#part0009.xhtml_slideshow-disable-bind)).

We are using the `void start()` method provided in `Service` class to start a service. It is called from the event handler that handles action event of `Start Slideshow` menu item. It is important to check the state of a service before invoking the `start()` method, this is to assure a service is in `READY` state.

The `Worker.State getState()` method defined in `javafx.concurrent.Worker` interface, is used to check the state of a service. A service can only be started successfully when it is in `READY` state. if it is not ready, reset it first, then start the service.

Here's the snippet of codes to do these:

```
 startSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Start Slideshow...");
        if (service.getState() != Worker.State.READY)
          service.reset(); // transit to READY
        service.start();
      }
    });
```

A user can cancel a slide show while the slide show service is running. The `boolean cancel()` method is called from the event handler that handles action event of `Stop Slideshow` menu item.

The following codes demonstrate how to implement event handlers of action event for `Start Slideshow` and `Stop Slideshow` menu items.

Import Statement:

```
 import javafx.concurrent.Worker;
```

Listing 3-17. Implement event handlers of action events for `Start Slideshow` and `Stop Slideshow` menu items:

```
 startSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Start Slideshow...");
        if (service.getState() != Worker.State.READY)
          service.reset(); // transit to READY
        // If last clicked button is previous button,
        // then next() image is current image,
        // must move cursor one step forward before starting service
        if (lastClickedButton.get().equals(PREVIOUS) &&
            listIterator.get().hasNext()) {
          listIterator.get().next();
        }
        service.start();
      }
    });
    stopSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Stop Slideshow...");
        service.cancel();
      }
    }); 
```

### 3.3.3 The Complete `start(Stage` stage`)` Method of `ImageViewer` Application

Following listing shows the complete `start` method of `ImageViewer` V1.2 at this phase, changes are in bold type face.

Listing 3-18. `start` method of `ImageViewer` V1.2 becomes like this:

```
 public class ImageViewer extends Application {

    ...

  final BooleanProperty isSlideshowOn = new SimpleBooleanProperty(false);
  // Create a reusable Worker object
  final SlideshowService service = new SlideshowService(listIterator,
      curImage, imageName);

  @Override
  public void start(final Stage stage) {
    BorderPane rootPane = new BorderPane();
    final StackPane imageArea = new StackPane();
    // Set min size for StackPane to avoid resizing
    // when loading large size image
    imageArea.setMinSize(0, 0);
    rootPane.setCenter(imageArea);

    // Add status bar and status text
    final HBox statusBar = new HBox();
    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(#F0FFFF, #708090)");
    final Text statusText = new Text("");
    statusText.textProperty().bind(imageName);
    statusText.setFont(Font.font("Verdana", FontWeight.BOLD, 12));
    statusText.setFill(Color.DARKSLATEBLUE);

    statusBar.getChildren().add(statusText);
    rootPane.setBottom(statusBar);

    // Create image view, add to image area
    final ImageView imageView = new ImageView();
    imageView.imageProperty().bind(curImage);
    imageView.setPreserveRatio(true);
    imageArea.getChildren().add(imageView);

    // Since JavaFX 8, to see through background color of scene,
    // must set root pane's background to transparent
    rootPane.setStyle("-fx-background-color: transparent;");
    final Scene scene = new Scene(rootPane, 600, 400, Color.BLACK);

    imageArea.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea width changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });
    imageArea.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("imageArea height changed from %.1f to %.1f%n",
            oldVal, newVal);
      }
    });

    // Add menu bar
    final MenuBar menuBar = new MenuBar();
    Menu menuFile = new Menu("File");
    MenuItem load = new MenuItem("Load");
    MenuItem exit = new MenuItem("Exit");
    menuFile.getItems().addAll(load, exit);
    menuBar.getMenus().add(menuFile);
    rootPane.setTop(menuBar);

    // Add action for exit menu item
    exit.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        Platform.exit();
      }
    });

    // Create a file chooser
    final FileChooser fileChooser = new FileChooser();
    fileChooser.setTitle("Open an Image File");
    FileUtils.configure(fileChooser);

    // Add action for menu item Load
    load.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent e) {
        // Open FileChooser dialog
        File file = fileChooser.showOpenDialog(stage);
        if (file != null) {
          // Set last visited dir as initial directory
          File lastDir = file.getParentFile();
          fileChooser.setInitialDirectory(lastDir);
          loadFile(file);
        }
      }
    });

    // Create Option menu
    Menu menuOption = new Menu("Option");

    // Create radio menu items
    final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
    fitWidth.setToggleGroup(groupOption);
    final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
    fitHeight.setToggleGroup(groupOption);
    final RadioMenuItem original = new RadioMenuItem("Original Size");
    original.setToggleGroup(groupOption);

    // Listen to the change of selection in the toggle group
    groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      public void changed(ObservableValue<? extends Toggle> ov,
          Toggle old_toggle, Toggle new_toggle) {
        if (groupOption.getSelectedToggle() != null) {
          RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
          if (choiceItem == fitWidth) {
            System.out.println("fitwidth");
            imageView.fitWidthProperty().bind(scene.widthProperty());
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height to 0
            imageView.setFitHeight(0);
          } else if (choiceItem == fitHeight) {
            System.out.println("fitheight");
            // Available height for rendering image is
            // subtract sum of menubar's height and statusBar's height
            // from scene height
            imageView.fitHeightProperty().bind(
                scene.heightProperty().subtract(
                  menuBar.getHeight() + statusBar.getHeight()));
            imageView.fitWidthProperty().unbind();
            // Besides unbind, must also set fit width to 0 
            imageView.setFitWidth(0);
          } else {
            System.out.println("original size");
            imageView.fitWidthProperty().unbind();
            imageView.fitHeightProperty().unbind();
            // Besides unbind, must also set fit height/height to 0
            imageView.setFitWidth(0);
            imageView.setFitHeight(0);
          }
        }
      }
    });

    // Create View submenu for Option menu
    Menu menuView = new Menu("View");
    menuView.getItems().addAll(fitWidth, fitHeight, original);

    // Set Original Size as default choice
    original.setSelected(true);

    // Create start/stop slideshow menu items
    final MenuItem startSlide = new MenuItem("Start Slideshow");
    final MenuItem stopSlide = new MenuItem("Stop Slideshow");

    startSlide.disableProperty().bind(isSlideshowOn.or(
        nextButton.disableProperty()));
    stopSlide.disableProperty().bind(isSlideshowOn.not().or(
        nextButton.disableProperty()));

    configureSlideshow();

    // Add action handler for Start Slideshow menu item
    startSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Start Slideshow...");
        if (service.getState() != Worker.State.READY)
          service.reset(); // transition to READY
        // If last clicked button is previous button,
        // then next() image is current image,
        // must move cursor one step forward before starting service
        if (lastClickedButton.get().equals(PREVIOUS) &&
            listIterator.get().hasNext()) {
          listIterator.get().next();
        }
        service.start();
      }
    });

    // Add action handler for Stop Slideshow menu item
    stopSlide.setOnAction(new EventHandler<ActionEvent>() {
      @Override
      public void handle(ActionEvent ae) {
        System.out.println("Stop Slideshow...");
        service.cancel();
      }
    });    

    // Add option menu to menu bar
    menuOption.getItems().addAll(menuView, startSlide, stopSlide);
    menuBar.getMenus().add(menuOption);

    // Install tooltip
    Tooltip t = new Tooltip("Next Image");
    Tooltip.install(nextButton, t);

    // Install tooltip for prevButton
    Tooltip t2 = new Tooltip("Previous Image");
    Tooltip.install(prevButton, t2);

    // Adjust next button's position to the right side of StackPane
    StackPane.setAlignment(nextButton, Pos.CENTER_RIGHT);
    StackPane.setMargin(nextButton, new Insets(8));

    // Adjust previous button's position to the right side of StackPane
    StackPane.setAlignment(prevButton, Pos.CENTER_LEFT);
    StackPane.setMargin(prevButton, new Insets(8));

    // Add next button and previous button to stack pane
    imageArea.getChildren().addAll(nextButton, prevButton);

    // Listen to the width change of scene
    scene.widthProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("Scene width changed from %.1f to %.1f%n",
            (double) oldVal, (double) newVal);
      }
    });

    // Listen to the height change of scene   
    scene.heightProperty().addListener(new ChangeListener<Object>() {
      public void changed(ObservableValue o, Object oldVal,
          Object newVal) {
        System.out.format("Scene height changed from %.1f to %.1f%n",
            (double) oldVal, (double) newVal);
      }
    });

    stage.setTitle("ImageViewer V1.2");
    stage.setScene(scene);
    stage.show();
  }
```

### 3.3.4 Coordinate with Event Handlers of `Load` Menu Item and `Previous` Button

Since a slide show is running on its own thread, the application remains responsive to user's actions such as mouse clicked on `Load` menu item or `Previous` button.

To make a slide show running smoothly, we'll refine the action handler of `Load` menu item as well as the mouse clicked event handler of `Previous` button. That is, we'll proceed to the loading of current selected file or previous file only if a slide show is not running. Changes are shown in bold type face in the following listings.

Please note that if a user clicks the `Next` button while a slide show is running, the overall flow of image rendering doesn't look too awkward, therefore no extra care is imposed on it.

Listing 3-19. `loadFile` method becomes like this:

```
 /**
   * 
   * @param file 
   */
  void loadFile(File file) {
    // Create iterator
    try {
      ListIterator<java.nio.file.Path> it =
        FileUtils.listIterator(file.toPath());

      // Update value of listIterator property
      listIterator.set(it);

      // If slideshow is not on, load the file
      // otherwise, do nothing here,
      // because slideshow service will do the task
      if (!isSlideshowOn.get()) {
        // Disable prevButton if there's no previous file,
        // check hasPrevious() before next() is called
        disableButton(prevButton, !it.hasPrevious());

        file = it.next().toFile();
        String url = file.toURI().toString();
        curImage.set(new Image(url));
        imageName.set(url.substring(
            url.lastIndexOf("/") + 1).replaceAll("%20", " "));

        // Check hasNext, disable nextButton if there's no next file
        disableButton(nextButton, !it.hasNext());

        lastClickedButton.setValue(NEXT);
      }
    } catch (IOException ex) {
    }
  }
```

The following snippet of codes is excerpted from the `createPrevButton` method.

Listing 3-20. Mouse clicked event handler of `Previous` button becomes this:

```
 // Register mouse clicked event handler for previous button
    buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (me.getButton() != MouseButton.PRIMARY)
          return;
        ListIterator<java.nio.file.Path> iterator = (ListIterator)listIterator.get();
        if (iterator != null && iterator.hasPrevious()) {
          java.nio.file.Path path = iterator.previous();
          if (lastClickedButton.get().equals(NEXT)) {
            // If the last clicked button is nextButton
            // the first call of previous() is the current image,
            // must move cursor one step backward
            if (iterator.hasPrevious())
              path = iterator.previous();
            else {
              // There is no previous image, disable prevButton
              disableButton(prevButton, true);
              return;
            }
          }
          System.out.format("Prev button clicked: %s%n", path.getFileName());
          // if slideshow is not on, load file here
          // otherwise, do nothing here,
          // because slideshow service will do the task,
          if (!isSlideshowOn.get()) {
            String url = path.toUri().toString();
            curImage.set(new Image(url));
            imageName.set(url.substring(
              url.lastIndexOf("/")+1).replaceAll("%20", " "));

            lastClickedButton.set(PREVIOUS);
            disableButton(prevButton, !iterator.hasPrevious());
            if (nextButton.isDisabled()) 
              disableButton(nextButton, false);
          }
        }    
      }
    });
```

Compile and run the program, testing the followings to apprehend how the application deals with concurrency of events:

*   Load an image file in an image directory from a `FileChooser`'s File Open Dialog.
*   Start slide show.
*   While a slide show is running, do below actions:
    *   Select different `View` options back and forth.
    *   Click `Previous` button or `Next` button.
    *   Load another image file in different image directory from a `FileChooser`'s File Open Dialog.

Figure 3-11. Snapshot of `Option` menu's appearance when a slide show is running, `Start Slideshow` menu item is disabled and `Stop Slideshow` menu item is enabled.

![](Images/image00159.jpeg "slideshow_on.jpg")

## 3.4 Add Fade Transition between Slides

To accent the movement of a slide show, we'll add fade transition between slides. Here are classes from `javafx.animation` package for animations of fade transitions:

*   `Animation`

    An abstract class extends `java.lang.Object`, provides common properties and methods required among animations.

*   `Transition`

    An abstract class extends `Animation`, provides common properties and methods required among transition animations. Here are available transitions: `FadeTransition`, `FillTransition`, `ParallelTransition`, `PathTransition`, `PauseTransition`, `RotateTransition`, `ScaleTransition`, `SequentialTransition`, `StrokeTransition`, `TranslateTransition`.

*   `FadeTransition`

    A direct subclass of `Transition`﹐changes the opacity of a node over the given duration.

*   `ParallelTransition`

    A direct subclass of `Transition`, conducts transitions over a list of `Animation` objects, type of `ObservableList<Animation>`, in a parallel manner.

    This is the constructor we'll use to create `FadeTransition` objects:

    ```
     public FadeTransition(Duration duration, Node node) 
    ```

    `Duration` class, resides in `javafx.util` package, provides several factory methods for creating duration objects. Here's the one employed:

    ```
     public static Duration millis(double ms) 
    ```

    The above method creates a `Duration` of given milliseconds for a `FadeTransition`.

    A `FadeTransition` looks into the following properties:

    *   `duration`

        Type of `ObjectProperty<Duration>`, holds the duration of transiting the opacity from `fromValue` to `toValue`. The value of this property is specified as the first argument of the constructor.

    *   `node`

        Type of `ObjectProperty<Node>`, holds the target node conducted for this fade transition. The value of this property is specified as the second argument of the constructor.

    *   `fromValue`

        Type of `DoubleProperty`, holds the starting value of opacity for this fade transition.

    *   `toValue`

        Type of `DoubleProperty`, holds the end value of opacity for this fade transition.

    Here's the snippet of codes to create a `FadeTransition` for an image to fade in, the value of opacity for this image is changing from 0 to 1 through the duration of 2000 milliseconds:

    ```
     FadeTransition fadein = new FadeTransition(Duration.millis(2000), inView);
              fadein.setFromValue(0.0);
              fadein.setToValue(1.0);
    ```

    Similarly, here's the snippet of codes to create a `FadeTransition` for an image to fade out, the value of opacity for this image is changing from 1 to 0 through the duration of 2000 milliseconds:

    ```
     FadeTransition fadeout = new FadeTransition(Duration.millis(2000), outView);
              fadeout.setFromValue(1.0);
              fadeout.setToValue(0.0);
    ```

    Now, we have two `FadeTransition` objects, one for performing fade in transition, another for performing fade out transition, we prefer both transitions to process in parallel. Since each transition has its own target node, the following constructor of `ParallelTransition` is employed:

    ```
     public ParallelTransition(Animation... children) 
    ```

    Here's the snippet of codes to create a `ParallelTransition` and start the animation using the `playFromStart()` method provided in `Animation` class:

    ```
     Transition animate = new ParallelTransition(fadein, fadeout);
              animate.playFromStart(); 
    ```

    The requester of a `SlideshowService` need provide two `ImageView` objects, one for fade in transition, and another for fade out transition.

    The snippets of codes below demonstrate how the requester of a `SlideshowService` provides two `ImageView` objects using the `setImageView` mehtod and the `setFadeOutImageView` method.

    Listing 3-21. Provide two `ImageView` objects for fade transitions between slides performed within a `SlideshowService`:

    ```
     public class ImageViewer extends Application {

        ...

      final StringProperty imageName = new SimpleStringProperty();

      final ObjectProperty<Image> curImage = new SimpleObjectProperty<>();

      // Create a reusable Worker object
      final SlideshowService service = new SlideshowService(listIterator,
          curImage, imageName);

        ...

      @Override
      public void start(final Stage stage) {
        BorderPane rootPane = new BorderPane();
        final StackPane imageArea = new StackPane();
        // Set min size for StackPane to avoid resizing
        // when loading large size image
        imageArea.setMinSize(0, 0);
        rootPane.setCenter(imageArea);

          ...

        // add image view to image area    
        final ImageView imageView = new ImageView();
        imageView.imageProperty().bind(curImage);
        imageView.setPreserveRatio(true);
        imageArea.getChildren().add(imageView);

        // For fade transition in slideshow
        ImageView outView = new ImageView();
        outView.preserveRatioProperty().bind(imageView.preserveRatioProperty());
        outView.fitWidthProperty().bind(imageView.fitWidthProperty());
        outView.fitHeightProperty().bind(imageView.fitHeightProperty());
        imageArea.getChildren().add(outView);
        service.setImageView(imageView);
        service.setFadeOutImageView(outView);

          ... 
    ```

    ### 3.4.1 Complete Source Codes of `SlideshowService` Class

    The following listing shows the complete source codes of `SlideshowService` class at this phase, in which changes are shown in bold type face.

    Listing 3-22. `SlideshowService` class becomes like this:

    ```
     package imageviewer;

    import java.nio.file.Path;
    import java.util.ListIterator;
    import javafx.animation.FadeTransition;
    import javafx.animation.ParallelTransition;
    import javafx.animation.Transition;
    import javafx.beans.property.ObjectProperty;
    import javafx.beans.property.SimpleObjectProperty;
    import javafx.beans.property.SimpleStringProperty;
    import javafx.beans.property.StringProperty;
    import javafx.beans.value.ChangeListener;
    import javafx.beans.value.ObservableValue;
    import javafx.concurrent.Service;
    import javafx.concurrent.Task;
    import javafx.scene.image.Image;
    import javafx.scene.image.ImageView;
    import javafx.util.Duration;

    /**
     * File Name: SlideshowService.java
     * (in directory: ImageViewer1.2/src/example5/imageviewer/)
     *
     * Add fade transition between slides
     *
     * @author Shufen Kuo
     */

    public class SlideshowService extends Service<Void> {
      private ObjectProperty<ImageView> imageView = new SimpleObjectProperty<>();
      private ObjectProperty<ImageView> fadeOutIV = new SimpleObjectProperty<>();
      private ObjectProperty<Image> image;
      private ObjectProperty<ListIterator<Path>> iterator;
      private StringProperty imageName;
      private ListIterator<Path> it;

      public SlideshowService() {
        this(new SimpleObjectProperty<ListIterator<Path>>(),
            new SimpleObjectProperty<Image>(),
            new SimpleStringProperty());
      }

      public SlideshowService(ObjectProperty<ListIterator<Path>> iterator,
          ObjectProperty<Image> image, StringProperty imageName) {
        this.image = image;
        this.imageName = imageName;
        this.iterator = iterator;
        iterator.addListener(new ChangeListener<ListIterator<Path>>() {
          @Override
          public void changed(ObservableValue<? extends ListIterator<Path>> o,
              ListIterator<Path> oldVal, ListIterator<Path> newVal) {
            it = newVal;
          }
        });    
      }

      public ImageView getImageView() {
        return imageView.get();
      }

      public void setImageView(ImageView value) {
        imageView.set(value);
      }

      public ObjectProperty<ImageView> imageViewProperty() {
        return imageView;
      }

      public ImageView getFadeOutImageView() {
        return fadeOutIV.get();
      }

      public void setFadeOutImageView(ImageView value) {
        fadeOutIV.set(value);
      }

      public ObjectProperty<ImageView> fadeOutImageViewProperty() {
        return fadeOutIV;
      }

      public Image getImage() {
        return image.get();
      }

      public void setImage(Image value) {
        image.set(value);
      }

      public ObjectProperty<Image> imageProperty() {
        return image;
      }

      public ListIterator<Path> getIterator() {
        return iterator.get();
      }

      public void setListIterator(ListIterator<Path> value) {
        iterator.set(value);
      }

      public ObjectProperty<ListIterator<Path>> iteratorProperty() {
        return iterator;
      }

      public String getImageName() {
        return imageName.get();
      }

      public void setImageName(String value) {
        imageName.set(value);
      }

      public StringProperty imageNameProperty() {
        return imageName;
      }

      @Override
      protected Task<Void> createTask() {
        return new Task<Void>() {
          @Override
          protected Void call() {
            if (it == null) return null;

            Transition animate = null;
            ImageView inView = imageView.get();
            ImageView outView = fadeOutIV.get();
            if (inView != null && outView != null) {
              FadeTransition fadein = new FadeTransition(Duration.millis(2000), inView);
              fadein.setFromValue(0.0);
              fadein.setToValue(1.0);

              FadeTransition fadeout = new FadeTransition(Duration.millis(2000), outView);
              fadeout.setFromValue(1.0);
              fadeout.setToValue(0.0);

              animate = new ParallelTransition(fadein, fadeout);
            }

            while (it.hasNext()) {
              if (isCancelled()) {
                updateMessage("Cancelled");
                break;
              }

              if (inView != null && outView != null) {
                Image prevImage = getImage();
                outView.setImage(prevImage);
                // Must reset opacity's from value for outView
                outView.setOpacity(1); 
                // Must reset opacity's from value for inView
                inView.setOpacity(0);            
              }        

              String url = it.next().toUri().toString();
              setImage(new Image(url));
              setImageName(url.substring(
                  url.lastIndexOf("/") + 1).replaceAll("%20", " "));

              // Start fadein fadeout animation before pause
              if (animate != null) 
                animate.playFromStart();

              // Pause for 3000 ms
              try {
                Thread.sleep(3000);
              } catch (InterruptedException ex) {
                if (isCancelled()) {
                  updateMessage("Cancelled");
                  break;
                }
              }
            }

            // reset outView before return
            if (outView != null) {
              outView.setImage(null);
            }

            return null;
          }
        };
      }  
    }
    ```

    ## 3.5 Complete Source Codes of `Image Viewer V1.2`

    Listing 3-23. Complete source codes of `ImageViewer` class:

    ```
     package imageviewer;

    import java.io.File;
    import java.io.IOException;
    import java.util.ListIterator;
    import javafx.application.Application;
    import javafx.application.Platform; 
    import javafx.beans.property.BooleanProperty;
    import javafx.beans.property.ObjectProperty;
    import javafx.beans.property.SimpleBooleanProperty;
    import javafx.beans.property.SimpleObjectProperty;
    import javafx.beans.property.SimpleStringProperty;
    import javafx.beans.property.StringProperty;
    import javafx.beans.value.ChangeListener;
    import javafx.beans.value.ObservableValue;
    import javafx.concurrent.Worker;
    import javafx.concurrent.WorkerStateEvent;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.geometry.Insets;
    import javafx.geometry.Pos;
    import javafx.scene.Cursor;
    import javafx.scene.Group;
    import javafx.scene.Node;
    import javafx.scene.Scene;
    import javafx.scene.control.Menu;
    import javafx.scene.control.MenuBar;
    import javafx.scene.control.MenuItem;
    import javafx.scene.control.RadioMenuItem;
    import javafx.scene.control.Toggle;
    import javafx.scene.control.ToggleGroup;
    import javafx.scene.control.Tooltip;
    import javafx.scene.image.Image;
    import javafx.scene.image.ImageView;
    import javafx.scene.input.MouseButton;
    import javafx.scene.input.MouseEvent;
    import javafx.scene.layout.BorderPane;
    import javafx.scene.layout.HBox;
    import javafx.scene.layout.StackPane;
    import javafx.scene.paint.Color;
    import javafx.scene.paint.CycleMethod;
    import javafx.scene.paint.LinearGradient;
    import javafx.scene.paint.Paint;
    import javafx.scene.paint.Stop;
    import javafx.scene.shape.Polygon;
    import javafx.scene.shape.Rectangle;
    import javafx.scene.shape.Shape;
    import javafx.scene.text.Font;
    import javafx.scene.text.FontWeight;
    import javafx.scene.text.Text;
    import javafx.stage.FileChooser;
    import javafx.stage.Stage;

    /**
     * File Name: ImageViewer.java V1.2
     * (in directory: ImageViewer1.2/src/example5/imageviewer/)
     * This application creates a BorderPane as root node of a scene, and
     * add a StackPane in the center of BorderPane
     * The initial size of the scene is set to 600 by 400
     * The size of StackPane will be automatically set to fit the size of scene.
     * StackPane will be resized when window size is adjusted by a user
     *
     * Add a menu bar in the top of BorderPane
     * Create File Menu, and using FileChooser's Open Dialog to
     * select an image file, load and display the image in image rendering area.
     * 
     * Create Option menu contains View submenu, let a user chooses image viewing
     * criteria: Fit Width, Fit Height, or the default option Original Size.
     *
     * Adjust image viewing size using bind and unbind methods:
     * Bind fitWidth/fitHeight properties of an image view to
     * width/height properties of a scene,
     * so that, size of the image view will be changed automatically
     * whenever the scene is resized. 
     * 
     * Add Next and Previous buttons to a scene, then
     * after the first image is loaded, a user can use these buttons to
     * view next or preview image without opening FileChoose again.
     * 
     * Adjust Next button's default position in  StackPane
     * Add Previous button and adjust its position in a StackPane
     * Implement on mouse clicked event Handlers for Next and Previous buttons
     * 
     * Add status bar to show image name
     * Disable buttons to indicate no more image to open
     * Distinguish button's appearance between different event types:
     *   entered/pressed/released/exited
     * Execute slideshow on thread
     * Coordinate with event handlers for Load menu item and Previous button 
     * Add fade transition for slideshow
     *
     * @author Shufen Kuo
     */

    public class ImageViewer extends Application {
      final Node nextButton = createNextButton();
      final Node prevButton = createPrevButton();
      {
        disableButton(nextButton, true);
        disableButton(prevButton, true);
      }

      // Create toggle group
      final ToggleGroup groupOption = new ToggleGroup();
      final String FIT_WIDTH = "Fit Width";
      final String FIT_HEIGHT = "Fit Height";
      final String ORIGINAL_SIZE = "Original Size";

      // For traverse files in current selected directory
      final ObjectProperty<ListIterator<java.nio.file.Path>> listIterator =
          new SimpleObjectProperty<>();

      final String NEXT = "NEXT";
      final String PREVIOUS = "PREVIOUS";
      // For keep track of last clicked button
      final StringProperty lastClickedButton = new SimpleStringProperty();

      final ObjectProperty<Image> curImage = new SimpleObjectProperty<>();

      final StringProperty imageName = new SimpleStringProperty();

      final BooleanProperty isSlideshowOn = new SimpleBooleanProperty(false);
      // Create a reusable Worker object
      final SlideshowService service = new SlideshowService(listIterator,
          curImage, imageName);

      @Override
      public void start(final Stage stage) {
        BorderPane rootPane = new BorderPane();
        final StackPane imageArea = new StackPane();
        // Set min size for StackPane to avoid resizing
        // when loading large size image
        imageArea.setMinSize(0, 0);
        rootPane.setCenter(imageArea);

        // Add status bar and status text
        final HBox statusBar = new HBox();
        statusBar.setPadding(new Insets(4, 12, 4, 12));
        statusBar.setSpacing(4);
        statusBar.setStyle(
            "-fx-background-color: linear-gradient(#F0FFFF, #708090)");
        final Text statusText = new Text("");
        statusText.textProperty().bind(imageName);
        statusText.setFont(Font.font("Verdana", FontWeight.BOLD, 12));
        statusText.setFill(Color.DARKSLATEBLUE);

        statusBar.getChildren().add(statusText);
        rootPane.setBottom(statusBar);

        // Create image view, add to image area
        final ImageView imageView = new ImageView();
        imageView.imageProperty().bind(curImage);
        imageView.setPreserveRatio(true);
        imageArea.getChildren().add(imageView);

        // For fade transition in slideshow
        ImageView outView = new ImageView();
        outView.preserveRatioProperty().bind(imageView.preserveRatioProperty());
        outView.fitWidthProperty().bind(imageView.fitWidthProperty());
        outView.fitHeightProperty().bind(imageView.fitHeightProperty());
        imageArea.getChildren().add(outView);
        service.setImageView(imageView);
        service.setFadeOutImageView(outView);

        // Since JavaFX 8, to see through background color of scene,
        // must set root pane's background to transparent
        rootPane.setStyle("-fx-background-color: transparent;");
        final Scene scene = new Scene(rootPane, 600, 400, Color.BLACK);

        imageArea.widthProperty().addListener(new ChangeListener<Object>() {
          public void changed(ObservableValue o, Object oldVal,
              Object newVal) {
            System.out.format("imageArea width changed from %.1f to %.1f%n",
                oldVal, newVal);
          }
        });
        imageArea.heightProperty().addListener(new ChangeListener<Object>() {
          public void changed(ObservableValue o, Object oldVal,
              Object newVal) {
            System.out.format("imageArea height changed from %.1f to %.1f%n",
                oldVal, newVal);
          }
        });

        // Add menu bar
        final MenuBar menuBar = new MenuBar();
        Menu menuFile = new Menu("File");
        MenuItem load = new MenuItem("Load");
        MenuItem exit = new MenuItem("Exit");
        menuFile.getItems().addAll(load, exit);
        menuBar.getMenus().add(menuFile);
        rootPane.setTop(menuBar);

        // Add action for exit menu item
        exit.setOnAction(new EventHandler<ActionEvent>() {
          @Override
          public void handle(ActionEvent e) {
            Platform.exit();
          }
        });

        // Create a file chooser
        final FileChooser fileChooser = new FileChooser();
        fileChooser.setTitle("Open an Image File");
        FileUtils.configure(fileChooser);

        // Add action for menu item Load
        load.setOnAction(new EventHandler<ActionEvent>() {
          @Override
          public void handle(ActionEvent e) {
            // Open FileChooser dialog
            File file = fileChooser.showOpenDialog(stage);
            if (file != null) {
              // Set last visited dir as initial directory
              File lastDir = file.getParentFile();
              fileChooser.setInitialDirectory(lastDir);
              loadFile(file);
            }
          }
        });

        // Create Option menu
        Menu menuOption = new Menu("Option");

        // Create radio menu items
        final RadioMenuItem fitWidth = new RadioMenuItem("Fit Width");
        fitWidth.setToggleGroup(groupOption);
        final RadioMenuItem fitHeight = new RadioMenuItem("Fit Height");
        fitHeight.setToggleGroup(groupOption);
        final RadioMenuItem original = new RadioMenuItem("Original Size");
        original.setToggleGroup(groupOption);

        // Listen to the change of selection in the toggle group
        groupOption.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
          public void changed(ObservableValue<? extends Toggle> ov,
              Toggle old_toggle, Toggle new_toggle) {
            if (groupOption.getSelectedToggle() != null) {
              RadioMenuItem choiceItem = (RadioMenuItem) groupOption.getSelectedToggle();
              if (choiceItem == fitWidth) {
                System.out.println("fitwidth");
                imageView.fitWidthProperty().bind(scene.widthProperty());
                imageView.fitHeightProperty().unbind();
                // Besides unbind, must also set fit height to 0
                imageView.setFitHeight(0);
              } else if (choiceItem == fitHeight) {
                System.out.println("fitheight");
                // Available height for rendering image is
                // subtract sum of menubar's height and statusBar's height
                // from scene height
                imageView.fitHeightProperty().bind(
                    scene.heightProperty().subtract(
                      menuBar.getHeight() + statusBar.getHeight()));
                imageView.fitWidthProperty().unbind();
                // Besides unbind, must also set fit width to 0 
                imageView.setFitWidth(0);
              } else {
                System.out.println("original size");
                imageView.fitWidthProperty().unbind();
                imageView.fitHeightProperty().unbind();
                // Besides unbind, must also set fit height/height to 0
                imageView.setFitWidth(0);
                imageView.setFitHeight(0);
              }
            }
          }
        });

        // Create View submenu for Option menu
        Menu menuView = new Menu("View");
        menuView.getItems().addAll(fitWidth, fitHeight, original);

        // Set Original Size as default choice
        original.setSelected(true);

        // Create start/stop slideshow menu items
        final MenuItem startSlide = new MenuItem("Start Slideshow");
        final MenuItem stopSlide = new MenuItem("Stop Slideshow");

        startSlide.disableProperty().bind(isSlideshowOn.or(
            nextButton.disableProperty()));
        stopSlide.disableProperty().bind(isSlideshowOn.not().or(
            nextButton.disableProperty()));

        configureSlideshow();

        // Add action handler for Start Slideshow menu item
        startSlide.setOnAction(new EventHandler<ActionEvent>() {
          @Override
          public void handle(ActionEvent ae) {
            System.out.println("Start Slideshow...");
            if (service.getState() != Worker.State.READY)
              service.reset(); // transit to READY
            // If last clicked button is previous button,
            // then next() image is current image,
            // must move cursor one step forward before starting service
            if (lastClickedButton.get().equals(PREVIOUS) &&
                listIterator.get().hasNext()) {
              listIterator.get().next();
            }
            service.start();
          }
        });

        // Add action handler for Stop Slideshow menu item
        stopSlide.setOnAction(new EventHandler<ActionEvent>() {
          @Override
          public void handle(ActionEvent ae) {
            System.out.println("Stop Slideshow...");
            service.cancel();
          }
        });    

        // Add option menu to menu bar
        menuOption.getItems().addAll(menuView, startSlide, stopSlide);
        menuBar.getMenus().add(menuOption);

        // Install tooltip
        Tooltip t = new Tooltip("Next Image");
        Tooltip.install(nextButton, t);

        // Install tooltip for prevButton
        Tooltip t2 = new Tooltip("Previous Image");
        Tooltip.install(prevButton, t2);

        // Adjust next button's position to the right side of StackPane
        StackPane.setAlignment(nextButton, Pos.CENTER_RIGHT);
        StackPane.setMargin(nextButton, new Insets(8));

        // Adjust previous button's position to the right side of StackPane
        StackPane.setAlignment(prevButton, Pos.CENTER_LEFT);
        StackPane.setMargin(prevButton, new Insets(8));

        // Add next button and previous button to stack pane
        imageArea.getChildren().addAll(nextButton, prevButton);

        // Listen to the width change of scene
        scene.widthProperty().addListener(new ChangeListener<Object>() {
          public void changed(ObservableValue o, Object oldVal,
              Object newVal) {
            System.out.format("Scene width changed from %.1f to %.1f%n",
                (double) oldVal, (double) newVal);
          }
        });

        // Listen to the height change of scene   
        scene.heightProperty().addListener(new ChangeListener<Object>() {
          public void changed(ObservableValue o, Object oldVal,
              Object newVal) {
            System.out.format("Scene height changed from %.1f to %.1f%n",
                (double) oldVal, (double) newVal);
          }
        });

        stage.setTitle("ImageViewer V1.2");
        stage.setScene(scene);
        stage.show();
      }

      /**
       * Create next button using a Rectangle as background,
       * a Polygon as icon, a Group as container,
       * size of Rectangle is 25 by 35,
       * thickness of polygon is 8 pixels,
       * padding of polygon is (2, 2, 2, 5),
       * change button appearance when mouse entered/pressed/released/exited.
       *
       * @return
       */
      Node createNextButton() {

        // Create a group as button
        Group buttonGroup = new Group();

        // Create a rectangle shape as background
        final Rectangle rect = new Rectangle(0, 0, 25, 35);

        // Look and feel of the rectangle
        final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
            CycleMethod.NO_CYCLE, new Stop[]{
          new Stop(0, Color.web("#5173A8")),
          new Stop(0.6, Color.web("#A8B9D4")),
          new Stop(1, Color.web("#87A7C6"))});
        rect.setFill(lg);
        rect.setStroke(Color.web("#ACD7FF"));
        rect.setArcHeight(6.5);
        rect.setArcWidth(6.5);

        // Paint to fill rectangle when mouse entered the next button
        final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
            CycleMethod.NO_CYCLE, new Stop[]{
          new Stop(0, Color.web("#87A7C6")),
          new Stop(0.4, Color.web("#A8B9D4")),
          new Stop(1, Color.web("#5173A8"))});

        // Paint to fill rectangle when mouse pressed on the next button
        final LinearGradient lgPressed = new LinearGradient(0, 0, 1, 0, true,
            CycleMethod.NO_CYCLE, new Stop[]{
          new Stop(0, Color.web("#87A7C6")),
          new Stop(0.4, Color.web("#A8B9D4")),
          new Stop(1, Color.web("#2F4F4F"))});

        // Create a polygon shape representing visual sign of Next icon
        // 8 pixel thickness, insets is 2, 2, 2, 5
        final Polygon polygon = new Polygon();
        Double[] dArray = {
          5.0, 2.0,
          22.0, 17.0,
          5.0, 32.0,
          5.0, 25.0,
          14.0, 17.0,
          5.0, 9.0};
        polygon.getPoints().addAll(dArray);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));

        // Set cursor
        buttonGroup.setCursor(Cursor.OPEN_HAND);

        // Register mouse clicked event handler for nextButton
        buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
          @Override
          public void handle(MouseEvent me) {
            if (me.getButton() != MouseButton.PRIMARY)
              return;
            // Get iterator
            ListIterator<java.nio.file.Path> iterator = listIterator.get();
            if (iterator != null && iterator.hasNext()) {
              java.nio.file.Path path = iterator.next();
              if (lastClickedButton.get().equals(PREVIOUS)) {
                // If last clicked button is prevButton
                // the first call of next() is the current image, 
                // must move cursor one step forward.
                if (iterator.hasNext())
                  path = iterator.next();
                else{
                  // There is no next image, disable next buttons
                  disableButton(nextButton, true);
                  return;
                }
              }
              System.out.format("Next button clicked: %s%n", path.getFileName());
              String url = path.toUri().toString();
              curImage.set(new Image(url));
              imageName.set(url.substring(
                  url.lastIndexOf("/")+1).replaceAll("%20", " "));

              lastClickedButton.set(NEXT);
              // Disable next button when there's no next image
              disableButton(nextButton, !iterator.hasNext());
              if (prevButton.isDisable())
                disableButton(prevButton, false);
            }
          }
        });

        registerButtonEvent(buttonGroup, rect, polygon, lg, lgEntered, lgPressed);

        buttonGroup.getChildren().addAll(rect, polygon);
        return buttonGroup;
      }

      /**
       * Create previous button using a Rectangle as background,
       * a Polygon as icon, a Group as container,
       * size of Rectangle is 25 by 35,
       * thickness of polygon is 8 pixels,
       * padding of polygon is (2, 5, 2, 5),
       * change button appearance when mouse entered/pressed/released/exited.
       * 
       * @return 
       */
      Node createPrevButton() {

        // Create a group as button
        Group buttonGroup = new Group();

        // Create a rectangle shape as background
        final Rectangle rect = new Rectangle(0, 0, 25, 35);

        // Look and feel of the rectangle
        final LinearGradient lg = new LinearGradient(0, 0, 1, 0, true,
            CycleMethod.NO_CYCLE, new Stop[] { 
          new Stop(0, Color.web("#87A7C6")),
          new Stop(0.4, Color.web("#A8B9D4")),
          new Stop(1, Color.web("#5173A8"))});
        rect.setFill(lg);
        rect.setStroke(Color.web("#ACD7FF"));
        rect.setArcHeight(6.5);
        rect.setArcWidth(6.5);

        // Paint to fill rectangle when mouse entered the previous button
        final LinearGradient lgEntered = new LinearGradient(0, 0, 1, 0, true,
            CycleMethod.NO_CYCLE, new Stop[] { 
          new Stop(0, Color.web("#5173A8")),
          new Stop(0.6, Color.web("#A8B9D4")),
          new Stop(1, Color.web("#87A7C6"))});

        // Paint to fill rectangle when mouse pressed on the previous button
        final LinearGradient lgPressed = new LinearGradient(0, 0, 1, 0, true,
            CycleMethod.NO_CYCLE, new Stop[]{
          new Stop(0, Color.web("#2F4F4F")),
          new Stop(0.6, Color.web("#A8B9D4")),
          new Stop(1, Color.web("#87A7C6"))});

        // Create a polygon shape representing visual sign of Next icon
        // 8 pixel thickness, insets is 2, 2, 2, 5
        final Polygon polygon = new Polygon();
        Double[] dArray = {
          19.0, 2.0,
          2.0, 17.0,
          19.0, 32.0,
          19.0, 25.0,
          10.0, 17.0,
          19.0, 9.0};
        polygon.getPoints().addAll(dArray);
        polygon.setFill(Color.WHITE);
        polygon.setStroke(Color.web("#436B8B"));

        // Set cursor
        buttonGroup.setCursor(Cursor.OPEN_HAND);

        // Register mouse clicked event handler for prevButton
        buttonGroup.setOnMouseClicked(new EventHandler<MouseEvent>() {
          @Override
          public void handle(MouseEvent me) {
            if (me.getButton() != MouseButton.PRIMARY)
              return;
            // Get iterator
            ListIterator<java.nio.file.Path> iterator = listIterator.get();
            if (iterator != null && iterator.hasPrevious()) {
              java.nio.file.Path path = iterator.previous();
              if (lastClickedButton.get().equals(NEXT)) {
                // If the last clicked button is nextButton
                // the first call of previous() is the current image,
                // must move cursor one step backward
                if (iterator.hasPrevious())
                  path = iterator.previous();
                else{
                  // There is no previous image, disable prevButton
                  disableButton(prevButton, true);
                  return;
                }
              }
              System.out.format("Prev button clicked: %s%n", path.getFileName());
              // if slideshow is not on, load file here
              // otherwise, do nothing here,
              // because slideshow service will do the task,
              if (!isSlideshowOn.get()) {
                String url = path.toUri().toString();
                curImage.set(new Image(url));
                imageName.set(url.substring(
                  url.lastIndexOf("/")+1).replaceAll("%20", " "));

                lastClickedButton.set(PREVIOUS);
                disableButton(prevButton, !iterator.hasPrevious());
                if (nextButton.isDisabled()) 
                  disableButton(nextButton, false);
              }
            }
          }
        });

        registerButtonEvent(buttonGroup, rect, polygon, lg, lgEntered, lgPressed);

        buttonGroup.getChildren().addAll(rect, polygon);
        return buttonGroup;
      }

      /**
       * This method takes advantage of node's opacity property to
       * distinguish disable status, 
       * set opacity value to 0.4 if it is disabled.
       * 
       * @param button
       * @param isDisable 
       */
      void disableButton(Node button, boolean isDisable) {
        // Change the opacity value to 0.4 if no more image to open
        double opacity = (isDisable) ? 0.4 : 1;
        button.setOpacity(opacity);
        button.setDisable(isDisable);
      }

      /**
       * Static method FileUtils.listIterator(Path) is called to 
       * get a list iterator to iterate over files in the directory,
       * disable buttons if no more files to open.
       *
       * @param file 
       */
      void loadFile(File file) {
        // Create list iterator
        try {
          ListIterator<java.nio.file.Path> it =
            FileUtils.listIterator(file.toPath());

          // Update value of listIterator property
          listIterator.set(it);

          // If slideshow is not on, load the file
          // otherwise, do nothing here,
          // because slideshow service will do the task
          if (!isSlideshowOn.get()) {
            // Disable prevButton if there's no previous file,
            // check hasPrevious() before next() is called
            disableButton(prevButton, !it.hasPrevious());

            file = it.next().toFile();
            String url = file.toURI().toString();
            curImage.set(new Image(url));
            imageName.set(url.substring(
                url.lastIndexOf("/") + 1).replaceAll("%20", " "));

            // Check hasNext, disable nextButton if there's no next file
            disableButton(nextButton, !it.hasNext());

            lastClickedButton.setValue(NEXT);
          }
        } catch (IOException ex) {
        }
      }

      /**
       * This method registers mouse entered/pressed/released/exited events for button,
       * look and feel of the button is changed to distinguish between different event types.
       * 
       * @param buttonGroup
       * @param rect
       * @param polygon
       * @param bg
       * @param entered
       * @param pressed 
       */
      void registerButtonEvent(Node buttonGroup,
        final Shape rect, final Shape polygon,
        final Paint bg, final Paint entered, final Paint pressed) {

        // Register mouse entered event handler
        // Change the appearance of button when mouse entered
        buttonGroup.setOnMouseEntered(new EventHandler<MouseEvent>() {
          @Override
          public void handle(MouseEvent me) {
            System.out.println("Mouse entered");
            // Check if left mouse button is pressed
            rect.setFill(me.isPrimaryButtonDown()? pressed : entered);
            polygon.setFill(Color.web("#436B8B"));
            polygon.setStroke(Color.WHITE);
          }
        });

        // Register mouse pressed event handler
        // Change the appearance of button when mouse entered
        buttonGroup.setOnMousePressed(new EventHandler<MouseEvent>() {
          @Override
          public void handle(MouseEvent me) {
            System.out.println("Mouse pressed");
            if (me.isPrimaryButtonDown()) {
              rect.setFill(pressed);
              polygon.setFill(Color.web("#436B8B"));
              polygon.setStroke(Color.WHITE);
            }
          }
        });

        // Mouse exited event handler
        // Recover to original appearance when mouse exited
        EventHandler<MouseEvent> exited = new EventHandler<MouseEvent>() {
          @Override
          public void handle(MouseEvent me) {
            System.out.println("Mouse exited/released");
            rect.setFill(bg);
            polygon.setFill(Color.WHITE);
            polygon.setStroke(Color.web("#436B8B"));
          }
        };

        buttonGroup.setOnMouseExited(exited);

        // Register mouse released event handler
        // Recover to original appearance when mouse released
        // the appearance is same as mouse exited
        buttonGroup.setOnMouseReleased(exited);
      }
      /**
       * 
       */
      void configureSlideshow() {
        // If service is running, then value of isSlideshowOn is true,
        // otherwise, it's false 
        isSlideshowOn.bind(service.runningProperty());

        service.setOnRunning(new EventHandler<WorkerStateEvent>() {
          @Override
          public void handle(WorkerStateEvent we) {
            System.out.println("Service is transited to running status");
            lastClickedButton.set(NEXT);
            if (prevButton.isDisable()) {
              disableButton(prevButton, false);
            }
          }
        });

        EventHandler<WorkerStateEvent> taskDone = new EventHandler<WorkerStateEvent>() {
          @Override
          public void handle(WorkerStateEvent we) {
            disableButton(nextButton, !listIterator.get().hasNext());
            if (prevButton.isDisable()) {
              disableButton(prevButton, false);
            }
          }
        };

        service.setOnSucceeded(taskDone);
        service.setOnFailed(taskDone);
        service.setOnCancelled(taskDone);    
      }

      public static void main(String[] args) {
        launch(args);
      }

    }
    ```

    The following snapshots show fade in/fade out transition. Since we use `ParallelTransition` instead of `SequentialTransition`, you'll see the fade out image blending with the fade in image.

    Figure 3-12. Snapshot of an image to be faded out

    ![](Images/image00160.jpeg "fadeout.jpg")

    Figure 3-13. Snapshot of fade in and fade out transitions executed in parallel manner.

    ![](Images/image00161.jpeg "fade_transition.jpg")

    Figure 3-14. Snapshot of an image that is faded in.

    ![](Images/image00162.jpeg "fadein.jpg")

    Compile and run the application. Try these steps to test it:

    *   Load an image file in an image directory from a `FileChooser`'s File Open Dialog.
    *   Start slide show.
    *   While a slide show is running, do below actions:
        *   Select different `View` options back and forth.
        *   Click `Previous` button or `Next` button.
        *   Load another image file in different image directory from a `FileChooser`'s File Open Dialog.
    *   Stop slide show.

    Output from Compiling and Running ImageViewer in command line:

    ```
     Microsoft Windows [Version 6.3.9600]
    (c) 2013 Microsoft Corporation. All rights reserved.

    F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeOne\ImageViewer1.2\src\example5>
    javac  -encoding utf-8 -Xlint:unchecked imageviewer\*.java

    jar cf imageviewer.jar imageviewer

    java -cp imageviewer.jar imageviewer.ImageViewer
    original size
    imageArea width changed from 0.0 to 600.0
    imageArea height changed from 0.0 to 352.0
    Start Slideshow...
    Service is transited to running status
    Mouse entered
    Mouse exited/released
    fitwidth
    fitheight
    original size
    Mouse entered
    Mouse pressed
    Mouse exited/released
    Next button clicked: Shufen2010_05 1091.jpg
    Mouse pressed
    Mouse exited/released
    Next button clicked: Shufen2010_05 1166.jpg
    Mouse exited/released
    Mouse entered
    Mouse pressed
    Mouse exited/released
    Prev button clicked: Shufen2010_05 1166.jpg
    Mouse pressed
    Mouse exited/released
    Prev button clicked: Shufen2010_05 1166.jpg
    Mouse pressed
    Mouse exited/released
    Prev button clicked: Shufen2010_05 1142.jpg
    Mouse exited/released
    Mouse entered
    Mouse exited/released
    Mouse entered
    Mouse pressed
    Mouse exited/released
    Next button clicked: jasmin.gif
    Mouse pressed
    Mouse exited/released
    Next button clicked: Jasmin_1.jpg
    Mouse exited/released
    Mouse entered
    Mouse exited/released
    Mouse entered
    Mouse pressed
    Mouse exited/released
    Prev button clicked: Jasmin_1_320x363.jpg
    Mouse exited/released
    Stop Slideshow...
    ```

    ## 3.6 Summary

    This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

    *   `HBox` class, one of built-in JavaFX layout panes﹐resides in `javafx.scene.layout` package, is a direct subclass of `javafx.scene.layout.Pane`, placing its children in one row horizonally.
        (See section [Add Status Bar at the Bottom of `BorderPane`](#part0009.xhtml_add-footer))
    *   `Text` class, resides in `javafx.scene.text` package, is one of direct subclasses of `javafx.scene.shape.Shape` class which takes care of common needs for rendering geometric primitives.
        (See section [Add Status Bar at the Bottom of `BorderPane`](#part0009.xhtml_add-footer))
    *   `void setPadding(Insets` value`)` method, provided in `Region` class, defines the top, right, bottom, left padding for a region. (See [here](#part0009.xhtml_set-padding))
    *   `void setSpacing(double` value`)` method, provided in `HBox` class, specifies the horizontal space between children in an HBox pane. (See [here](#part0009.xhtml_set-spacing))
    *   `void setStyle(String` value`)` method, provided in `Node` class, specifies CSS style for this node. (See [here](#part0009.xhtml_set-style))
    *   `static Font font(java.lang.String` family`, FontWeight` weight`, double` size`)` method is provided in `javafx.scene.text.Font` class, for obtaining a font to render text. (See [here](#part0009.xhtml_set-font))
    *   `Scene(Parent` root`, double` width`, double` height`, Paint` fill`)` is one of constructors of `Scene` class for creating a `Scene` with the specified background color. (See [here](#part0009.xhtml_create-scene-with-color))
    *   Some of Classes reside in `javafx.beans.property` package:

        `StringProperty`

        is an abstract class, derived from `javafx.beans.binding.StringExpression` class, implements `Property<java.lang.String>` and `WritableStringValue`.
        `WritableStringValue` extends `WritableObjectValue<java.lang.String>`.

        `SimpleStringProperty`

        is derived from `StringProperty` class.

        (See [here](#part0009.xhtml_properties-binding1))
    *   `void bind(ObservableValue<? extends T>` observable`)` method defined in `Property` interface, resides in `javafx.beans.property` package, to bind this property unidirectional to the given `ObservableValue`.
        (See [here](#part0009.xhtml_fit-height-bind) | [here](#part0009.xhtml_slideshow-disable-bind) | [here](#part0009.xhtml_is-slideshow-on-bind))
    *   `DoubleBinding subtract(double` other`)` method, defined in `javafx.beans.binding.DoubleExpression` class, calculates the difference of this `NumberExpression` and the given constant value.
        (See [here](#part0009.xhtml_height-subtract))
    *   `void setDisable(boolean` value`)` method, provided in `Node` class, specifies the `disable` status of this node.
        (See section [Disable Button to Indicate No More Image to Open](#part0009.xhtml_disable-button) and [here](#part0009.xhtml_disable-property))
    *   `void setOpacity(double` value`)` method, provided in `Node` class, specifies the extent of transparency of this node. (See [here](#part0009.xhtml_opacity-property))
    *   `MouseEvent`, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `MOUSE_CLICKED`, `MOUSE_DRAGGED`, `MOUSE_ENTERED`, `MOUSE_EXITED`, `MOUSE_MOVED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, etc., and provides methods such as `getX()`, `getY()`, etc., to get position of mouse event.
        (See section [Change Button Appearance When Mouse Is Pressed](#part0009.xhtml_pressed-button))
    *   `void setOnMousePressed(EventHandler<? super MouseEvent>` value`)`, a convenience method provided in `Node` class, registers an `EventHandler` to handle `MOUSE_PRESSED` event type of `MouseEvent`.
        (See section [Change Button Appearance When Mouse Is Pressed](#part0009.xhtml_pressed-button))
    *   `MenuBar`, `Menu`, and `MenuItem` are among fundamental JavaFX UI components, reside in `javafx.scene.control` package, for designing compact look-and-feel graphical user interfaces using less space.
        (See section [Add Start Slideshow and Stop Slideshow Menu Items](#part0009.xhtml_add-slideshow-menu-item))
    *   Some classes from `javafx.beans.property` package:

        `BooleanProperty`

        is an abstract class, derived from `javafx.beans.binding.BooleanExpression` class, implements `Property<java.lang.Boolean>` and `WritableBooleanValue`.
        `WritableBooleanValue` extends `WritableValue<java.lang.Boolean>`.

        `SimpleBooleanProperty`

        derived from `BooleanProperty` class.

        (See section [Add Start Slideshow and Stop Slideshow Menu Items](#part0009.xhtml_add-slideshow-menu-item) and [here](#part0009.xhtml_is-slideshow-on-bind))
    *   `BooleanBinding` class is an abstract class resides in `javafx.beans.binding` package, it extends `BooleanExpression` class and implements `Binding<java.lang.Boolean>`.
        (See [here](#part0009.xhtml_slideshow-not-or))
    *   `BooleanExpression` class, resides in `javafx.beans.binding` package, is an abstract class that implements `ObservableBooleanValue`, an interface that extends `ObservableValue<java.lang.Boolean>`. Convenience methods that performs logical operations like AND, OR, and NOT are provided in `BooleanExpression` class.
        (See [here](#part0009.xhtml_slideshow-not-or))
    *   Some convenience methods from `BooleanExpression` class:

        `BooleanBinding not()`

        performs the logical NOT operation on this `BooleanExpression`, and returns an object of type `BooleanBinding` which is a direct subclass of `BooleanExpression`

        `BooleanBinding or(ObservableBooleanValue` other`)`

        performs the logical OR operation on this `BooleanExpression` and the given `ObservableBooleanValue`, and returns an object of type `BooleanBinding` which is a direct subclass of `BooleanExpression`

        (See [here](#part0009.xhtml_slideshow-not-or))
    *   `Worker<V>` is an interface resides in `javafx.concurrent` package, it defines common APIs for implementation of concurrency.
        (See section [Execute Slide Show on Thread](#part0009.xhtml_slideshow-thread))
    *   Classes for concurrency, reside in `javafx.concurrent` package:

        `Task`

        An abstract class implements `Worker<`V`>` interface, is a one-time `Worker` object.

        `Service`

        An abstract class implements `Worker<`V`>` interface, is a reusable `Worker` object.

        `ScheduledService`

        A direct subclass of `Service` class, allows specifying the duration of delay to start and restart a service automatically.

        `WorkerStateEvent`

        A subclass of `javafx.event.Event`, defines static fields of event types such as `WORKER_STATE_CANCELLED`, `WORKER_STATE_FAILED`, `WORKER_STATE_READY`, `WORKER_STATE_RUNNING`, `WORKER_STATE_SUCCEEDED`, etc. A `WorkerStateEvent` occurs when the state of a `Worker` is transited.

        (See section [Execute Slide Show on Thread](#part0009.xhtml_slideshow-thread))
    *   `protected abstract V call()` method, defined in `Task` class, must be overridden, is invoked when the task is executed. (See [here](#part0009.xhtml_call-method-in-task) | [here](#part0009.xhtml_call-method-in-create-task) | [here](#part0009.xhtml_call-method-codes))
    *   `protected abstract Task<V> createTask()` method, defined in `Service` class, must be overridden, is invoked when the service is started. (See [here](#part0009.xhtml_create-task-in-service) | [here](#part0009.xhtml_create-task-method) | [here](#part0009.xhtml_create-task-codes))
    *   Some of convenience methods provided in `Service` class to register `EventHandler`s to handle Worker State Events:

        `public final void setOnRunning(EventHandler<WorkerStateEvent>` value`)`

        `public final void setOnSucceeded(EventHandler<WorkerStateEvent>` value`)`

        `public final void setOnFailed(EventHandler<WorkerStateEvent>` value`)`

        `public final void setOnCancelled(EventHandler<WorkerStateEvent>` value`)`

        (See section [Configure Slide Show Service Object](#part0009.xhtml_configure-slideshow))
    *   `Worker.State`, nested class from `javafx.concurrent.Worker` interface, is an enumerated type defines constants for states of a `Worker`, they are: `CANCELLED`, `FAILED`, `READY`, `RUNNING`, `SCHEDULED`, and `SUCCEEDED`.
        (See [here](#part0009.xhtml_register-worker-state-event) and [here](#part0009.xhtml_worker-state))
    *   Some of methods provided in `Service` class, reside in `javafx.concurrent` package:

        `public void start()`

        Start this service; a service can only be started successfully if it is in `READY` state.

        `public void reset()`

        Reset this service; the state of service is transited to `READY` state as a result.

        `Worker.State getState()`

        Defined in `Worker` interface, get the value of `state` property which represents the current state of the `Worker`.

        `public boolean cancel()`

        Defined in `Worker` interface, cancel this service, return `true` if the service is canceled successfully.

        (See section [Implement Event Handlers of Action Events for `Start Slideshow` and `Stop Slideshow` Menu Items](#part0009.xhtml_slideshow-action))
    *   Some of classes from `javafx.animation` package for conducting transition animations of fade in and fade out effects between slides in parallel:

        `Animation`

        `Transition`

        `FadeTransition`

        `ParallelTransition`

        (See section [Add Fade Transition between Slides](#part0009.xhtml_fade-transition))
    *   `javafx.util.Duration` class, implements `java.lang.Comparable<Duration>`, holds the duration of time. (See [here](#part0009.xhtml_fade-transition-duration))
    *   `public void playFromStart()` method, provided in `Animation` class, plays an animation from the starting position. (See [here](#part0009.xhtml_play-from-start-animation))

#   EPILOGUE

The authors are working on the rest of volumes of this book series, to be released one by one soon. Let's have a sneak peek of coming features besides others revealed in the PREFACE section:

*   More interactive sketching tools: Free Hand Drawer, Rubber Band Drawer, Text Writer, Color Gradienter, Arc Drawer, Cursor Key Mover, etc.
*   Color palette tools
*   Image clipping tools
*   Path transition animater
*   Dynamic context menu controller
*   And more...

Wish you a happy, healthy, and prosperous year of the Monkey.